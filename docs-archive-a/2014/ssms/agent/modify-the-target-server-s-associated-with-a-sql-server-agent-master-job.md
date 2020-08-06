---
title: Изменение целевых серверов, связанных с агент SQL Server главным заданием | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 176e73b6-08aa-48ec-b349-e84b431e65cc
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6b7b5ab114366cdafe40b7a70f523fef43eb11d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668588"
---
# <a name="modify-the-target-servers-associated-with-a-sql-server-agent-master-job"></a><span data-ttu-id="5c33d-102">Modify the Target Server(s) Associated with a SQL Server Agent Master Job</span><span class="sxs-lookup"><span data-stu-id="5c33d-102">Modify the Target Server(s) Associated with a SQL Server Agent Master Job</span></span>
  <span data-ttu-id="5c33d-103">В этом разделе описывается, как изменить целевые серверы, связанные с главным заданием агента SQL Server, в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c33d-103">This topic describes how to modify the target server(s) associated with a SQL Server Agent master job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="5c33d-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="5c33d-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5c33d-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="5c33d-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5c33d-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="5c33d-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="5c33d-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="5c33d-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5c33d-108">**Изменение целевых серверов, связанных с главным заданием агента SQL Server, с помощью:**</span><span class="sxs-lookup"><span data-stu-id="5c33d-108">**To modify the target server(s) associated with a SQL Server Agent master job, using:**</span></span>  
  
     [<span data-ttu-id="5c33d-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5c33d-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5c33d-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5c33d-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5c33d-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="5c33d-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="5c33d-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="5c33d-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="5c33d-113">Главное задание агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не может быть ориентировано как на локальный, так и на удаленный сервер.</span><span class="sxs-lookup"><span data-stu-id="5c33d-113">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent master job cannot be targeted at both local and remote servers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5c33d-114">безопасность</span><span class="sxs-lookup"><span data-stu-id="5c33d-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5c33d-115">Permissions</span><span class="sxs-lookup"><span data-stu-id="5c33d-115">Permissions</span></span>  
 <span data-ttu-id="5c33d-116">Если пользователь не является членом предопределенной роли сервера **sysadmin** , он может изменять только свои собственные задания.</span><span class="sxs-lookup"><span data-stu-id="5c33d-116">Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own.</span></span> <span data-ttu-id="5c33d-117">Дополнительные сведения см. в разделе [Обеспечение безопасности агента SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="5c33d-117">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5c33d-118">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5c33d-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-the-target-servers-associated-with-a-sql-server-agent-master-job"></a><span data-ttu-id="5c33d-119">Изменение целевых серверов, связанных с главным заданием агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="5c33d-119">To modify the target server(s) associated with a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="5c33d-120">В **обозревателе объектов** щелкните знак «плюс», чтобы развернуть сервер, содержащий задание, в котором нужно изменить целевой сервер.</span><span class="sxs-lookup"><span data-stu-id="5c33d-120">In **Object Explorer,** click the plus sign to expand the server that contains the job where you want to modify the target server.</span></span>  
  
2.  <span data-ttu-id="5c33d-121">Щелкните знак "плюс", чтобы развернуть **Агент SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="5c33d-121">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="5c33d-122">Чтобы развернуть папку **Задания** , щелкните значок «плюс».</span><span class="sxs-lookup"><span data-stu-id="5c33d-122">Click the plus sign to expand the **Jobs** folder.</span></span>  
  
4.  <span data-ttu-id="5c33d-123">Щелкните правой кнопкой мыши задание, для которого требуется изменить целевой сервер, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="5c33d-123">Right-click the job where you want to modify the target server and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="5c33d-124">В диалоговом окне **Свойства задания —**_Job_name_ в разделе **выберите страницу**выберите **целевые объекты**.</span><span class="sxs-lookup"><span data-stu-id="5c33d-124">In the **Job Properties -**_job_name_ dialog box, under **Select a page**, select **Targets**.</span></span> <span data-ttu-id="5c33d-125">Дополнительные сведения о параметрах, доступных на этой странице, см. в разделе [Свойства задания: страница создание &#40;целевые объекты задания&#41;](job-properties-new-job-targets-page.md).</span><span class="sxs-lookup"><span data-stu-id="5c33d-125">For more information on the available options on this page, see [Job Properties: New Job &#40;Targets Page&#41;](job-properties-new-job-targets-page.md).</span></span>  
  
6.  <span data-ttu-id="5c33d-126">После завершения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5c33d-126">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5c33d-127">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5c33d-127">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-target-server-currently-associated-with-a-sql-server-agent-master-job"></a><span data-ttu-id="5c33d-128">Удаление целевого сервера, связанного с главным заданием агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="5c33d-128">To delete a target server currently associated with a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="5c33d-129">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c33d-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5c33d-130">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="5c33d-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5c33d-131">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="5c33d-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- removes the server SEATTLE2 from processing the Weekly Sales Backupsjob   
    -- assumes that the Weekly Sales Backups job exists  
    USE msdb ;  
    GO  
  
    EXEC sp_delete_jobserver  
        @job_name = N'Weekly Sales Backups',  
        @server_name = N'SEATTLE2' ;  
    GO  
    ```  
  
 <span data-ttu-id="5c33d-132">Дополнительные сведения см. в разделе [sp_delete_jobserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-jobserver-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5c33d-132">For more information, see [sp_delete_jobserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-jobserver-transact-sql).</span></span>  
  
#### <a name="to-associate-a-target-server-with-the-current-sql-server-agent-master-job"></a><span data-ttu-id="5c33d-133">Связывание целевого сервера с текущим главным заданием агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="5c33d-133">To associate a target server with the current SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="5c33d-134">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c33d-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5c33d-135">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="5c33d-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5c33d-136">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="5c33d-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- assigns the multiserver job Weekly Sales Backups to the server SEATTLE2   
    -- assumes that the Weekly Sales Backups job already exists and that   
    -- SEATTLE2 is registered as a target server for the current instance  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_jobserver  
        @job_name = N'Weekly Sales Backups',  
        @server_name = N'SEATTLE2' ;  
    GO  
    ```  
  
 <span data-ttu-id="5c33d-137">Дополнительные сведения см. в разделе [sp_add_jobserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5c33d-137">For more information, see [sp_add_jobserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql).</span></span>  
  
  
