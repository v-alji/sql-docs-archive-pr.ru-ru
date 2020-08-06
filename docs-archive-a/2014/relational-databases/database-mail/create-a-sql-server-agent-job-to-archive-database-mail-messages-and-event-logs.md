---
title: Создание задания агента SQL Server по архивации сообщений и журналов событий компонента Database Mail | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- archiving mail messages and attachments [SQL Server]
- removing mail messages and attachements
- Database Mail [SQL Server], archiving
- saving mail messages and attachments
ms.assetid: 8f8f0fba-f750-4533-9b76-a9cdbcdc3b14
author: stevestein
ms.author: sstein
ms.openlocfilehash: b958b280c358a8aeb752600dee1c2aee31d14db1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657813"
---
# <a name="create-a-sql-server-agent-job-to-archive-database-mail-messages-and-event-logs"></a><span data-ttu-id="d0c5c-102">Создание задания агента SQL Server по архивации сообщений компонента Database Mail и журналов событий базы данных</span><span class="sxs-lookup"><span data-stu-id="d0c5c-102">Create a SQL Server Agent Job to Archive Database Mail Messages and Event Logs</span></span>
  <span data-ttu-id="d0c5c-103">Копии сообщений компонента Database Mail и их вложения хранятся в таблицах **msdb** , расположенных в журнале событий компонента Database Mail.</span><span class="sxs-lookup"><span data-stu-id="d0c5c-103">Copies of Database Mail messages and their attachments are retained in **msdb** tables along with the Database Mail event log.</span></span> <span data-ttu-id="d0c5c-104">Может возникнуть потребность периодического уменьшения объема ненужных таблиц и архивных сообщений и событий.</span><span class="sxs-lookup"><span data-stu-id="d0c5c-104">Periodically you might want to reduce the size of the tables and archive messages and events that are no longer needed.</span></span> <span data-ttu-id="d0c5c-105">Представленные ниже процедуры используются для создания задания агента SQL Server для автоматизации указанного процесса.</span><span class="sxs-lookup"><span data-stu-id="d0c5c-105">The following procedures create a SQL Server Agent job to automate the process.</span></span>  
  
-   <span data-ttu-id="d0c5c-106">**Перед началом работы:**  , [Необходимые компоненты](#Prerequisites), [Рекомендации](#Recommendations), [Разрешения](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="d0c5c-106">**Before you begin:**  , [Prerequisites](#Prerequisites), [Recommendations](#Recommendations), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="d0c5c-107">**Для архивации сообщений и журналов компонента Database Mail рекомендуется использовать:**  [агент SQL Server](#Process_Overview)</span><span class="sxs-lookup"><span data-stu-id="d0c5c-107">**To Archive Database Mail messages and logs using :**  [SQL Server Agent](#Process_Overview)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d0c5c-108">Перед началом</span><span class="sxs-lookup"><span data-stu-id="d0c5c-108">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="d0c5c-109">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="d0c5c-109">Prerequisites</span></span>  
 <span data-ttu-id="d0c5c-110">Новые таблицы для хранения архивных данных могут быть расположены в специальной архивной базе данных.</span><span class="sxs-lookup"><span data-stu-id="d0c5c-110">The new tables to store the archive data might be located in a special archive database.</span></span> <span data-ttu-id="d0c5c-111">Кроме того, строки можно экспортировать в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="d0c5c-111">Alternatively the rows could be exported to a text file.</span></span>  
 
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="d0c5c-112">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="d0c5c-112">Recommendations</span></span>  
 <span data-ttu-id="d0c5c-113">В случае сбоя задания в процессе работы, возможно, понадобится провести дополнительную проверку и отправить уведомления операторам.</span><span class="sxs-lookup"><span data-stu-id="d0c5c-113">In your production environment, you might want to add additional error checking and send an e-mail message to operators if the job fails.</span></span>  
  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d0c5c-114">Permissions</span><span class="sxs-lookup"><span data-stu-id="d0c5c-114">Permissions</span></span>  
 <span data-ttu-id="d0c5c-115">Чтобы выполнить хранимые процедуры, описанные в данном разделе, пользователь должен быть членом предопределенной роли сервера **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="d0c5c-115">You must be a member of the **sysadmin** fixed server role to execute the stored procedures described in this topic.</span></span>  
  
  
###  <a name="overview-of-the-process"></a><a name="Process_Overview"></a> <span data-ttu-id="d0c5c-116">Общие сведения о процессе</span><span class="sxs-lookup"><span data-stu-id="d0c5c-116">Overview of the Process</span></span>  
  
-   <span data-ttu-id="d0c5c-117">Первая процедура, которая создает задание с именем «Archive Database Mail», состоит из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="d0c5c-117">The first procedure creates a job named Archive Database Mail with the following steps.</span></span>  
  
    1.  <span data-ttu-id="d0c5c-118">Скопируйте все сообщения из таблиц компонента Database Mail в новую таблицу с именем прошлого месяца в формате **DBMailArchive_** _<год_месяц>_ .</span><span class="sxs-lookup"><span data-stu-id="d0c5c-118">Copy all messages from the Database Mail tables to a new table named after the previous month in the format **DBMailArchive_**_<year_month>_.</span></span>  
  
    2.  <span data-ttu-id="d0c5c-119">Скопируйте вложения, прикрепленные к сообщениям, скопированным на первом шаге из таблиц компонента Database Mail, в новую таблицу с именем прошлого месяца в формате **DBMailArchive_Attachments_** _<год_месяц>_ .</span><span class="sxs-lookup"><span data-stu-id="d0c5c-119">Copy the attachments related to the messages copied in the first step, from the Database Mail tables to a new table named after the previous month in the format **DBMailArchive_Attachments_**_<year_month>_.</span></span>  
  
    3.  <span data-ttu-id="d0c5c-120">Скопируйте из журналов событий компонента Database Mail события, имеющие отношение к сообщениям, скопированным на первом шаге, из таблиц компонента Database Mail в новую таблицу с именем прошлого месяца в формате **DBMailArchive_Log_** _<год_месяц>_ .</span><span class="sxs-lookup"><span data-stu-id="d0c5c-120">Copy the events from the Database Mail event log that are related to the messages copied in the first step, from the Database Mail tables to a new table named after the previous month in the format **DBMailArchive_Log_**_<year_month>_.</span></span>  
  
    4.  <span data-ttu-id="d0c5c-121">Удаление всех скопированных элементов из таблиц компонента Database Mail.</span><span class="sxs-lookup"><span data-stu-id="d0c5c-121">Delete the records of the transferred mail items from the Database Mail tables.</span></span>  
  
    5.  <span data-ttu-id="d0c5c-122">Удаление всех событий, связанных со скопированными элементами, хранящихся в журнале событий компонента Database Mail.</span><span class="sxs-lookup"><span data-stu-id="d0c5c-122">Delete the events related to the transferred mail items from the Database Mail event log.</span></span>  
  
-   <span data-ttu-id="d0c5c-123">Планирование задания для периодического выполнения.</span><span class="sxs-lookup"><span data-stu-id="d0c5c-123">Schedule the job to run periodically.</span></span>  
 
  
## <a name="to-create-a-sql-server-agent-job"></a><span data-ttu-id="d0c5c-124">Создание задания агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="d0c5c-124">To create a SQL Server Agent job</span></span>  
  
1.  <span data-ttu-id="d0c5c-125">В обозревателе объектов разверните узел агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , правой кнопкой мыши щелкните элемент **Задания**и выберите команду **Создать задание**.</span><span class="sxs-lookup"><span data-stu-id="d0c5c-125">In Object Explorer, expand [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, right-click **Jobs**, and then click **New Job**.</span></span>  
  
2.  <span data-ttu-id="d0c5c-126">В диалоговом окне **Создание задания** в поле **Имя** введите **Archive Database Mail**.</span><span class="sxs-lookup"><span data-stu-id="d0c5c-126">In the **New Job** dialog box, in the **Name** box, type **Archive Database Mail**.</span></span>  
  
3.  <span data-ttu-id="d0c5c-127">В окне **Владелец** подтвердите принадлежность владельца к предопределенной роли сервера **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="d0c5c-127">In the **Owner** box, confirm that the owner is a member of the **sysadmin** fixed server role.</span></span>  
  
4.  <span data-ttu-id="d0c5c-128">В окне **Категория** выберите **Обслуживание базы данных**.</span><span class="sxs-lookup"><span data-stu-id="d0c5c-128">In the **Category** box, click the **Database Maintenance**.</span></span>  
  
5.  <span data-ttu-id="d0c5c-129">В поле **Описание** введите **Archive Database Mail messages**, а затем выберите вкладку **Шаги**.</span><span class="sxs-lookup"><span data-stu-id="d0c5c-129">In the **Description** box, type **Archive Database Mail messages**, and then click **Steps**.</span></span>  
  
  
  
## <a name="to-create-a-step-to-archive-the-database-mail-messages"></a><span data-ttu-id="d0c5c-130">Создание шага по архивации сообщений компонента Database Mail</span><span class="sxs-lookup"><span data-stu-id="d0c5c-130">To create a step to archive the Database Mail messages</span></span>  
  
1.  <span data-ttu-id="d0c5c-131">На странице **Шаги** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="d0c5c-131">On the **Steps** page, click **New**.</span></span>  
  
2.  <span data-ttu-id="d0c5c-132">В текстовое поле **Имя шага** введите **Copy Database Mail Items**.</span><span class="sxs-lookup"><span data-stu-id="d0c5c-132">In the **Step name** box, type **Copy Database Mail Items**.</span></span>  
  
3.  <span data-ttu-id="d0c5c-133">В поле **Тип** выберите **Скрипт Transact-SQL (T-SQL)** .</span><span class="sxs-lookup"><span data-stu-id="d0c5c-133">In the **Type** box, select **Transact-SQL script (T-SQL)**.</span></span>  
  
4.  <span data-ttu-id="d0c5c-134">В поле **База данных** выберите **msdb**.</span><span class="sxs-lookup"><span data-stu-id="d0c5c-134">In the **Database** box, select **msdb**.</span></span>  
  
5.  <span data-ttu-id="d0c5c-135">Чтобы создать таблицу с именем прошлого месяца, в которой будут храниться все строки данных за предыдущие месяцы, в окне **Команда** введите представленную ниже инструкцию:</span><span class="sxs-lookup"><span data-stu-id="d0c5c-135">In the **Command** box, type the following statement to create a table named after the previous month, containing rows older than the start of the current month:</span></span>  
  
    ```  
    DECLARE @LastMonth nvarchar(12);  
    DECLARE @CopyDate nvarchar(20) ;  
    DECLARE @CreateTable nvarchar(250) ;  
    SET @LastMonth = (SELECT CAST(DATEPART(yyyy,GETDATE()) AS CHAR(4)) + '_' + CAST(DATEPART(mm,GETDATE())-1 AS varchar(2))) ;  
    SET @CopyDate = (SELECT CAST(CONVERT(char(8), CURRENT_TIMESTAMP- DATEPART(dd,GETDATE()-1), 112) AS datetime))  
    SET @CreateTable = 'SELECT * INTO msdb.dbo.[DBMailArchive_' + @LastMonth + '] FROM sysmail_allitems WHERE send_request_date < ''' + @CopyDate +'''';  
    EXEC sp_executesql @CreateTable ;  
    ```  
  
6.  <span data-ttu-id="d0c5c-136">Нажмите кнопку **ОК** , чтобы сохранить шаг.</span><span class="sxs-lookup"><span data-stu-id="d0c5c-136">Click **OK** to save the step.</span></span>  
  
  
  
## <a name="to-create-a-step-to-archive-the-database-mail-attachments"></a><span data-ttu-id="d0c5c-137">Создание шага по архивации вложений компонента Database Mail</span><span class="sxs-lookup"><span data-stu-id="d0c5c-137">To create a step to archive the Database Mail attachments</span></span>  
  
1.  <span data-ttu-id="d0c5c-138">На странице **Шаги** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="d0c5c-138">On the **Steps** page, click **New**.</span></span>  
  
2.  <span data-ttu-id="d0c5c-139">В текстовое поле **Имя шага** введите **Copy Database Mail Attachments**.</span><span class="sxs-lookup"><span data-stu-id="d0c5c-139">In the **Step name** box, type **Copy Database Mail Attachments**.</span></span>  
  
3.  <span data-ttu-id="d0c5c-140">В поле **Тип** выберите **Скрипт Transact-SQL (T-SQL)** .</span><span class="sxs-lookup"><span data-stu-id="d0c5c-140">In the **Type** box, select **Transact-SQL script (T-SQL)**.</span></span>  
  
4.  <span data-ttu-id="d0c5c-141">В поле **База данных** выберите **msdb**.</span><span class="sxs-lookup"><span data-stu-id="d0c5c-141">In the **Database** box, select **msdb**.</span></span>  
  
5.  <span data-ttu-id="d0c5c-142">Чтобы создать таблицу с именем прошлого месяца, в которой будут храниться все вложения, связанные с сообщениями, скопированными на предыдущем шаге, в окне **Команда** введите представленную ниже инструкцию:</span><span class="sxs-lookup"><span data-stu-id="d0c5c-142">In the **Command** box, type the following statement to create an attachments table named after the previous month, containing the attachments that correspond to the messages transferred in the previous step:</span></span>  
  
    ```  
    DECLARE @LastMonth nvarchar(12);  
    DECLARE @CopyDate nvarchar(20) ;  
    DECLARE @CreateTable nvarchar(250) ;  
    SET @LastMonth = (SELECT CAST(DATEPART(yyyy,GETDATE()) AS CHAR(4)) + '_' + CAST(DATEPART(mm,GETDATE())-1 AS varchar(2))) ;  
    SET @CopyDate = (SELECT CAST(CONVERT(char(8), CURRENT_TIMESTAMP- DATEPART(dd,GETDATE()-1), 112) AS datetime))  
    SET @CreateTable = 'SELECT * INTO msdb.dbo.[DBMailArchive_Attachments_' + @LastMonth + '] FROM sysmail_attachments   
     WHERE mailitem_id in (SELECT DISTINCT mailitem_id FROM [DBMailArchive_' + @LastMonth + '] )';  
    EXEC sp_executesql @CreateTable ;  
    ```  
  
6.  <span data-ttu-id="d0c5c-143">Нажмите кнопку **ОК** , чтобы сохранить шаг.</span><span class="sxs-lookup"><span data-stu-id="d0c5c-143">Click **OK** to save the step.</span></span>  
  
  
  
## <a name="to-create-a-step-to-archive-the-database-mail-log"></a><span data-ttu-id="d0c5c-144">Создание шага по архивации журнала компонента Database Mail</span><span class="sxs-lookup"><span data-stu-id="d0c5c-144">To create a step to archive the Database Mail log</span></span>  
  
1.  <span data-ttu-id="d0c5c-145">На странице **Шаги** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="d0c5c-145">On the **Steps** page, click **New**.</span></span>  
  
2.  <span data-ttu-id="d0c5c-146">В текстовом поле **Имя шага** введите **Copy Database Mail Log**.</span><span class="sxs-lookup"><span data-stu-id="d0c5c-146">In the **Step name** box, type **Copy Database Mail Log**.</span></span>  
  
3.  <span data-ttu-id="d0c5c-147">В поле **Тип** выберите **Скрипт Transact-SQL (T-SQL)** .</span><span class="sxs-lookup"><span data-stu-id="d0c5c-147">In the **Type** box, select **Transact-SQL script (T-SQL)**.</span></span>  
  
4.  <span data-ttu-id="d0c5c-148">В поле **База данных** выберите **msdb**.</span><span class="sxs-lookup"><span data-stu-id="d0c5c-148">In the **Database** box, select **msdb**.</span></span>  
  
5.  <span data-ttu-id="d0c5c-149">Чтобы создать таблицу с именем прошлого месяца, в которой будут храниться все записи журнала, связанные с сообщениями, скопированными на предыдущих шагах, в окне **Команда** введите представленную ниже инструкцию:</span><span class="sxs-lookup"><span data-stu-id="d0c5c-149">In the **Command** box, type the following statement to create a log table named after the previous month, containing the log entries that correspond to the messages transferred in the earlier step:</span></span>  
  
    ```  
    DECLARE @LastMonth nvarchar(12);  
    DECLARE @CopyDate nvarchar(20) ;  
    DECLARE @CreateTable nvarchar(250) ;  
    SET @LastMonth = (SELECT CAST(DATEPART(yyyy,GETDATE()) AS CHAR(4)) + '_' + CAST(DATEPART(mm,GETDATE())-1 AS varchar(2))) ;  
    SET @CopyDate = (SELECT CAST(CONVERT(char(8), CURRENT_TIMESTAMP- DATEPART(dd,GETDATE()-1), 112) AS datetime))  
    SET @CreateTable = 'SELECT * INTO msdb.dbo.[DBMailArchive_Log_' + @LastMonth + '] FROM sysmail_Event_Log   
     WHERE mailitem_id in (SELECT DISTINCT mailitem_id FROM [DBMailArchive_' + @LastMonth + '] )';  
    EXEC sp_executesql @CreateTable ;  
    ```  
  
6.  <span data-ttu-id="d0c5c-150">Нажмите кнопку **ОК** , чтобы сохранить шаг.</span><span class="sxs-lookup"><span data-stu-id="d0c5c-150">Click **OK** to save the step.</span></span>  
  
  
  
## <a name="to-create-a-step-to-remove-the-archived-rows-from-database-mail"></a><span data-ttu-id="d0c5c-151">Создание шага по удалению архивных строк из компонента Database Mail</span><span class="sxs-lookup"><span data-stu-id="d0c5c-151">To create a step to remove the archived rows from Database Mail</span></span>  
  
1.  <span data-ttu-id="d0c5c-152">На странице **Шаги** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="d0c5c-152">On the **Steps** page, click **New**.</span></span>  
  
2.  <span data-ttu-id="d0c5c-153">В текстовом поле **Имя шага** введите **Remove rows from Database Mail**.</span><span class="sxs-lookup"><span data-stu-id="d0c5c-153">In the **Step name** box, type **Remove rows from Database Mail**.</span></span>  
  
3.  <span data-ttu-id="d0c5c-154">В поле **Тип** выберите **Скрипт Transact-SQL (T-SQL)** .</span><span class="sxs-lookup"><span data-stu-id="d0c5c-154">In the **Type** box, select **Transact-SQL script (T-SQL)**.</span></span>  
  
4.  <span data-ttu-id="d0c5c-155">В поле **База данных** выберите **msdb**.</span><span class="sxs-lookup"><span data-stu-id="d0c5c-155">In the **Database** box, select **msdb**.</span></span>  
  
5.  <span data-ttu-id="d0c5c-156">Чтобы удалить из таблиц компонента Database Mail строки, созданные ранее начала текущего месяца, в окне **Команда** введите представленную ниже инструкцию:</span><span class="sxs-lookup"><span data-stu-id="d0c5c-156">In the **Command** box, type the following statement to remove rows older than the current month from the Database Mail tables:</span></span>  
  
    ```  
    DECLARE @CopyDate nvarchar(20) ;  
    SET @CopyDate = (SELECT CAST(CONVERT(char(8), CURRENT_TIMESTAMP- DATEPART(dd,GETDATE()-1), 112) AS datetime)) ;  
    EXECUTE msdb.dbo.sysmail_delete_mailitems_sp @sent_before = @CopyDate ;  
    ```  
  
6.  <span data-ttu-id="d0c5c-157">Нажмите кнопку **ОК** , чтобы сохранить шаг.</span><span class="sxs-lookup"><span data-stu-id="d0c5c-157">Click **OK** to save the step.</span></span>  
  
  
  
## <a name="to-create-a-step-to-remove-the-archived-items-from-database-mail-event-log"></a><span data-ttu-id="d0c5c-158">Создание шага по удалению архивных элементов из журнала событий компонента Database Mail</span><span class="sxs-lookup"><span data-stu-id="d0c5c-158">To create a step to remove the archived items from Database Mail event log</span></span>  
  
1.  <span data-ttu-id="d0c5c-159">На странице **Шаги** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="d0c5c-159">On the **Steps** page, click **New**.</span></span>  
  
2.  <span data-ttu-id="d0c5c-160">В текстовом поле **Имя шага** введите **Remove rows from Database Mail event log**.</span><span class="sxs-lookup"><span data-stu-id="d0c5c-160">In the **Step Name** box type **Remove rows from Database Mail event log**.</span></span>  
  
3.  <span data-ttu-id="d0c5c-161">В поле **Тип** выберите **Скрипт Transact-SQL (T-SQL)** .</span><span class="sxs-lookup"><span data-stu-id="d0c5c-161">In the **Type** box, select **Transact-SQL script (T-SQL)**.</span></span>  
  
4.  <span data-ttu-id="d0c5c-162">Чтобы удалить из журнала событий компонента Database Mail строки, созданные ранее начала текущего месяца, в окне **Команда** введите представленную ниже инструкцию:</span><span class="sxs-lookup"><span data-stu-id="d0c5c-162">In the **Command** box, type the following statement to remove rows older than the current month from the Database Mail event log:</span></span>  
  
    ```  
    DECLARE @CopyDate nvarchar(20) ;  
    SET @CopyDate = (SELECT CAST(CONVERT(char(8), CURRENT_TIMESTAMP- DATEPART(dd,GETDATE()-1), 112) AS datetime)) ;  
    EXECUTE msdb.dbo.sysmail_delete_log_sp @logged_before = @CopyDate ;  
    ```  
  
5.  <span data-ttu-id="d0c5c-163">Нажмите кнопку **ОК** , чтобы сохранить шаг.</span><span class="sxs-lookup"><span data-stu-id="d0c5c-163">Click **OK** to save the step.</span></span>  
  
  
  
## <a name="to-schedule-the-job-to-run-periodically"></a><span data-ttu-id="d0c5c-164">Планирование периодического выполнения задания</span><span class="sxs-lookup"><span data-stu-id="d0c5c-164">To schedule the job to run periodically</span></span>  
  
1.  <span data-ttu-id="d0c5c-165">В диалоговом окне **Создание задания** выберите **Расписания**.</span><span class="sxs-lookup"><span data-stu-id="d0c5c-165">In the **New Job** dialog box, click **Schedules**.</span></span>  
  
2.  <span data-ttu-id="d0c5c-166">На странице **Расписания** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="d0c5c-166">On the **Schedules** page, click **New**.</span></span>  
  
3.  <span data-ttu-id="d0c5c-167">В текстовое поле **Имя** введите **Archive Database Mail**.</span><span class="sxs-lookup"><span data-stu-id="d0c5c-167">In the **Name** box, type **Archive Database Mail**.</span></span>  
  
4.  <span data-ttu-id="d0c5c-168">В окне **Тип расписания** выберите **Циклический**.</span><span class="sxs-lookup"><span data-stu-id="d0c5c-168">In the **Schedule type** box, select **Recurring**.</span></span>  
  
5.  <span data-ttu-id="d0c5c-169">В области **Периодичность** задайте параметр выполнения периодического задания, например, первое число каждого месяца.</span><span class="sxs-lookup"><span data-stu-id="d0c5c-169">In the **Frequency** area, select the options to run the job periodically, for example once every month.</span></span>  
  
6.  <span data-ttu-id="d0c5c-170">В области **Сколько раз в день** выберите **Проводится один раз в день в \<time>** .</span><span class="sxs-lookup"><span data-stu-id="d0c5c-170">In the **Daily frequency** area, select **Occurs once at \<time>**.</span></span>  
  
7.  <span data-ttu-id="d0c5c-171">Убедитесь, что другие параметры настроены правильно, и сохраните расписание, нажав кнопку **OK** .</span><span class="sxs-lookup"><span data-stu-id="d0c5c-171">Verify that the other options are configured as you wish, and then click **OK** to save the schedule.</span></span>  
  
8.  <span data-ttu-id="d0c5c-172">Нажмите кнопку **ОК** , чтобы сохранить задание.</span><span class="sxs-lookup"><span data-stu-id="d0c5c-172">Click **OK** to save the job.</span></span>  
  
  
  
  
