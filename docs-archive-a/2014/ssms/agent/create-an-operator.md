---
title: Создание оператора | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, operators
- jobs [SQL Server Agent], notification options
- operators (users) [Database Engine], creating with Management Studio
- SQL Server Agent jobs, notification options
- jobs [SQL Server Agent], operators
- notifications [SQL Server], job status
ms.assetid: 1359d790-5905-4927-a208-e7155e7768a2
author: stevestein
ms.author: sstein
ms.openlocfilehash: dfe07042f9a4b8ac595ada8b86e7bad131032700
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731378"
---
# <a name="create-an-operator"></a><span data-ttu-id="38292-102">Create an Operator</span><span class="sxs-lookup"><span data-stu-id="38292-102">Create an Operator</span></span>
  <span data-ttu-id="38292-103">В этом разделе описывается настройка пользователя для получения уведомлений о [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] заданиях агента в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="38292-103">This topic describes how to configure a user to receive notifications about [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="38292-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="38292-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="38292-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="38292-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="38292-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="38292-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="38292-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="38292-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="38292-108">**Создание оператора**</span><span class="sxs-lookup"><span data-stu-id="38292-108">**To create an operator, using:**</span></span>  
  
     [<span data-ttu-id="38292-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="38292-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="38292-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="38292-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="38292-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="38292-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="38292-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="38292-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="38292-113">Режимы отправки уведомлений с помощью пейджера и команды **net send** будут удалены из агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в следующей версии [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="38292-113">The Pager and **net send** options will be removed from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in a future version of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="38292-114">Старайтесь не использовать эти функции в новых разработках и предусмотрите соответствующие изменения в приложениях, которые используют их в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="38292-114">Avoid using these features in new development work, and plan to modify applications that currently use these features.</span></span>  
  
-   <span data-ttu-id="38292-115">Обратите внимание, что для использования компонента Database Mail для отправки операторам уведомлений по электронной почте и на пейджер агент SQL Server необходимо настроить для использования компонента Database Mail.</span><span class="sxs-lookup"><span data-stu-id="38292-115">Note that SQL Server Agent must be configured to use Database Mail to send e-mail and pager notifications to operators.</span></span> <span data-ttu-id="38292-116">Дополнительные сведения см. в разделе [Назначить предупреждения для оператора](assign-alerts-to-an-operator.md).</span><span class="sxs-lookup"><span data-stu-id="38292-116">For more information, see [Assign Alerts to an Operator](assign-alerts-to-an-operator.md).</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="38292-117">обеспечивает доступный графический способ управления заданиями и рекомендуется для создания и управления инфраструктурой заданий.</span><span class="sxs-lookup"><span data-stu-id="38292-117">provides an easy, graphical way to manage jobs, and is the recommended way to create and manage the job infrastructure.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="38292-118">безопасность</span><span class="sxs-lookup"><span data-stu-id="38292-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="38292-119">Permissions</span><span class="sxs-lookup"><span data-stu-id="38292-119">Permissions</span></span>  
 <span data-ttu-id="38292-120">Создавать операторов могут только члены предопределенной роли сервера **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="38292-120">Only members of the **sysadmin** fixed server role can create operators.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="38292-121">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="38292-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-an-operator"></a><span data-ttu-id="38292-122">Создание оператора</span><span class="sxs-lookup"><span data-stu-id="38292-122">To create an operator</span></span>  
  
1.  <span data-ttu-id="38292-123">В **обозревателе объектов**щелкните значок «плюс», чтобы развернуть сервер, на котором необходимо создать оператора агента SQL Server.</span><span class="sxs-lookup"><span data-stu-id="38292-123">In **Object Explorer**, click the plus sign to expand the server where you want to create a SQL Server Agent operator.</span></span>  
  
2.  <span data-ttu-id="38292-124">Щелкните знак "плюс", чтобы развернуть **Агент SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="38292-124">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="38292-125">Щелкните правой кнопкой мыши папку **Операторы** и выберите пункт **Создать оператора**.</span><span class="sxs-lookup"><span data-stu-id="38292-125">Right-click the **Operators** folder and select **New Operator**.</span></span>  
  
     <span data-ttu-id="38292-126">На странице **Общие** диалогового окна **Создание оператора** доступны следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="38292-126">The following options are available on the **General** page of the **New Operator** dialog box:</span></span>  
  
     <span data-ttu-id="38292-127">**имя**;</span><span class="sxs-lookup"><span data-stu-id="38292-127">**Name**</span></span>  
     <span data-ttu-id="38292-128">Изменить имя оператора.</span><span class="sxs-lookup"><span data-stu-id="38292-128">Change the name of the operator.</span></span>  
  
     <span data-ttu-id="38292-129">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="38292-129">**Enabled**</span></span>  
     <span data-ttu-id="38292-130">Разрешить оператор.</span><span class="sxs-lookup"><span data-stu-id="38292-130">Enable the operator.</span></span> <span data-ttu-id="38292-131">Если он не включен, то уведомления оператору не отправляются.</span><span class="sxs-lookup"><span data-stu-id="38292-131">When not enabled, no notifications are sent to the operator.</span></span>  
  
     <span data-ttu-id="38292-132">**Имя для электронной почты**</span><span class="sxs-lookup"><span data-stu-id="38292-132">**E-mail name**</span></span>  
     <span data-ttu-id="38292-133">Определяет адрес электронной почты оператора.</span><span class="sxs-lookup"><span data-stu-id="38292-133">Specifies the e-mail address for the operator.</span></span>  
  
     <span data-ttu-id="38292-134">**Адрес для команды net send**</span><span class="sxs-lookup"><span data-stu-id="38292-134">**Net send address**</span></span>  
     <span data-ttu-id="38292-135">Задает адрес, используемый для **net send**.</span><span class="sxs-lookup"><span data-stu-id="38292-135">Specify the address to use for **net send**.</span></span>  
  
     <span data-ttu-id="38292-136">**Имя для сообщения на пейджер**</span><span class="sxs-lookup"><span data-stu-id="38292-136">**Pager e-mail name**</span></span>  
     <span data-ttu-id="38292-137">Определяет адрес электронной почты пейджера оператора.</span><span class="sxs-lookup"><span data-stu-id="38292-137">Specifies the e-mail address to use for the operator's pager.</span></span>  
  
     <span data-ttu-id="38292-138">**Расписание работы для пейджера**</span><span class="sxs-lookup"><span data-stu-id="38292-138">**Pager on duty schedule**</span></span>  
     <span data-ttu-id="38292-139">Указывает время, когда пейджер активен.</span><span class="sxs-lookup"><span data-stu-id="38292-139">Sets the times at which the pager is active.</span></span>  
  
     <span data-ttu-id="38292-140">**Понедельник — воскресенье**</span><span class="sxs-lookup"><span data-stu-id="38292-140">**Monday - Sunday**</span></span>  
     <span data-ttu-id="38292-141">Выберите дни, когда пейджер активен.</span><span class="sxs-lookup"><span data-stu-id="38292-141">Select the days that the pager is active.</span></span>  
  
     <span data-ttu-id="38292-142">**Начало рабочего дня**</span><span class="sxs-lookup"><span data-stu-id="38292-142">**Workday begin**</span></span>  
     <span data-ttu-id="38292-143">Выберите время суток, после которого агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] отправляет сообщения на пейджер.</span><span class="sxs-lookup"><span data-stu-id="38292-143">Select the time of day after which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent sends messages to the pager.</span></span>  
  
     <span data-ttu-id="38292-144">**Конец рабочего дня**</span><span class="sxs-lookup"><span data-stu-id="38292-144">**Workday end**</span></span>  
     <span data-ttu-id="38292-145">Выберите время суток, после которого агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] перестает отправлять сообщения на пейджер.</span><span class="sxs-lookup"><span data-stu-id="38292-145">Select the time of day after which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent no longer sends messages to the pager.</span></span>  
  
     <span data-ttu-id="38292-146">На странице **Уведомления** диалогового окна **Создание оператора** доступны следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="38292-146">The following options are available on the **Notifications** page of the **New Operator** dialog box:</span></span>  
  
     <span data-ttu-id="38292-147">**Оповещения**</span><span class="sxs-lookup"><span data-stu-id="38292-147">**Alerts**</span></span>  
     <span data-ttu-id="38292-148">Просмотреть предупреждения в экземпляре.</span><span class="sxs-lookup"><span data-stu-id="38292-148">View the alerts in the instance.</span></span>  
  
     <span data-ttu-id="38292-149">**Задания**</span><span class="sxs-lookup"><span data-stu-id="38292-149">**Jobs**</span></span>  
     <span data-ttu-id="38292-150">Просмотреть задания в экземпляре.</span><span class="sxs-lookup"><span data-stu-id="38292-150">View the jobs in the instance.</span></span>  
  
     <span data-ttu-id="38292-151">**Список предупреждений**</span><span class="sxs-lookup"><span data-stu-id="38292-151">**Alert list**</span></span>  
     <span data-ttu-id="38292-152">Содержит список предупреждений в экземпляре.</span><span class="sxs-lookup"><span data-stu-id="38292-152">Lists the alerts in the instance.</span></span>  
  
     <span data-ttu-id="38292-153">**Список заданий**</span><span class="sxs-lookup"><span data-stu-id="38292-153">**Job list**</span></span>  
     <span data-ttu-id="38292-154">Содержит список заданий в экземпляре.</span><span class="sxs-lookup"><span data-stu-id="38292-154">Lists the jobs in the instance.</span></span>  
  
     <span data-ttu-id="38292-155">**Электронных**</span><span class="sxs-lookup"><span data-stu-id="38292-155">**E-mail**</span></span>  
     <span data-ttu-id="38292-156">Уведомить этого оператора, используя электронную почту.</span><span class="sxs-lookup"><span data-stu-id="38292-156">Notify this operator using e-mail.</span></span>  
  
     <span data-ttu-id="38292-157">**Пейджер**</span><span class="sxs-lookup"><span data-stu-id="38292-157">**Pager**</span></span>  
     <span data-ttu-id="38292-158">Уведомить этого оператора, отправив сообщение электронной почты на адрес пейджера.</span><span class="sxs-lookup"><span data-stu-id="38292-158">Notify this operator by sending e-mail to the pager address.</span></span>  
  
     <span data-ttu-id="38292-159">**NET SEND**</span><span class="sxs-lookup"><span data-stu-id="38292-159">**Net send**</span></span>  
     <span data-ttu-id="38292-160">Уведомить этого оператора, используя **net send**.</span><span class="sxs-lookup"><span data-stu-id="38292-160">Notify this operator using **net send**.</span></span>  
  
4.  <span data-ttu-id="38292-161">После завершения создания оператора нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="38292-161">When finished creating the new operator, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="38292-162">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="38292-162">Using Transact-SQL</span></span>  
  
#### <a name="to-create-an-operator"></a><span data-ttu-id="38292-163">Создание оператора</span><span class="sxs-lookup"><span data-stu-id="38292-163">To create an operator</span></span>  
  
1.  <span data-ttu-id="38292-164">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="38292-164">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="38292-165">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="38292-165">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="38292-166">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="38292-166">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- sets up the operator information for user 'danwi.' The operator is enabled.   
    -- SQL Server Agent sends notifications by pager from Monday through Friday from 8 A.M. to 5 P.M.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_operator  
        @name = N'Dan Wilson',  
        @enabled = 1,  
        @email_address = N'danwi',  
        @pager_address = N'5551290AW@pager.Adventure-Works.com',  
        @weekday_pager_start_time = 080000,  
        @weekday_pager_end_time = 170000,  
        @pager_days = 62 ;  
    GO  
    ```  
  
 <span data-ttu-id="38292-167">Дополнительные сведения см. в разделе [sp_add_operator &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-operator-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="38292-167">For more information, see [sp_add_operator &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-operator-transact-sql).</span></span>  
  
  
