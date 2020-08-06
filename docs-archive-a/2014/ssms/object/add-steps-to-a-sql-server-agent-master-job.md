---
title: Добавление шагов к главному заданию агента SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 9cc1e8ab-7ddc-427b-859e-203aa7e24642
author: stevestein
ms.author: sstein
ms.openlocfilehash: ccff8d6f4faa7bef549b5a179a957ce798250dbe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654037"
---
# <a name="add-steps-to-a-sql-server-agent-master-job"></a><span data-ttu-id="01318-102">Add Steps to a SQL Server Agent Master Job</span><span class="sxs-lookup"><span data-stu-id="01318-102">Add Steps to a SQL Server Agent Master Job</span></span>
  <span data-ttu-id="01318-103">В этом разделе описывается добавление шагов в главное задание агента SQL Server в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="01318-103">This topic describes how to add steps to a SQL Server Agent master job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="01318-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="01318-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="01318-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="01318-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="01318-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="01318-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="01318-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="01318-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="01318-108">**Добавление шагов в главное задание агента SQL Server с помощью:**</span><span class="sxs-lookup"><span data-stu-id="01318-108">**To add steps to a SQL Server Agent master job, using:**</span></span>  
  
     [<span data-ttu-id="01318-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="01318-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="01318-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="01318-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="01318-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="01318-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="01318-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="01318-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="01318-113">Главное задание агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не может быть ориентировано как на локальный, так и на удаленный сервер.</span><span class="sxs-lookup"><span data-stu-id="01318-113">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent master job cannot be targeted at both local and remote servers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="01318-114">безопасность</span><span class="sxs-lookup"><span data-stu-id="01318-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="01318-115">Permissions</span><span class="sxs-lookup"><span data-stu-id="01318-115">Permissions</span></span>  
 <span data-ttu-id="01318-116">Если пользователь не является членом предопределенной роли сервера **sysadmin** , он может изменять только свои собственные задания.</span><span class="sxs-lookup"><span data-stu-id="01318-116">Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own.</span></span> <span data-ttu-id="01318-117">Дополнительные сведения см. в разделе [Обеспечение безопасности агента SQL Server](../agent/implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="01318-117">For detailed information, see [Implement SQL Server Agent Security](../agent/implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="01318-118">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="01318-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-add-steps-to-a-sql-server-agent-master-job"></a><span data-ttu-id="01318-119">Добавление шагов в главное задание агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="01318-119">To add steps to a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="01318-120">В **обозревателе объектов** щелкните знак «плюс», чтобы развернуть сервер, содержащий задание, в которое нужно добавить шаги.</span><span class="sxs-lookup"><span data-stu-id="01318-120">In **Object Explorer,** click the plus sign to expand the server that contains the job to which you want to add steps.</span></span>  
  
2.  <span data-ttu-id="01318-121">Щелкните знак "плюс", чтобы развернуть **Агент SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="01318-121">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="01318-122">Чтобы развернуть папку **Задания** , щелкните значок «плюс».</span><span class="sxs-lookup"><span data-stu-id="01318-122">Click the plus sign to expand the **Jobs** folder.</span></span>  
  
4.  <span data-ttu-id="01318-123">Щелкните правой кнопкой мыши задание, в которое нужно добавить шаги, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="01318-123">Right-click the job to which you want to add steps and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="01318-124">В диалоговом окне **Свойства задания —** _имя_задания_ в разделе **Выберите страницу** выберите пункт **Шаги**.</span><span class="sxs-lookup"><span data-stu-id="01318-124">In the **Job Properties -**_job_name_ dialog box, under **Select a page**, select **Steps**.</span></span> <span data-ttu-id="01318-125">Дополнительные сведения о параметрах, доступных на этой странице, см. в разделе [Свойства задания: создание задания &#40;шаги&#41;](../agent/job-properties-new-job-steps-page.md).</span><span class="sxs-lookup"><span data-stu-id="01318-125">For more information on the available options on this page, see [Job Properties:New Job &#40;Steps Page&#41;](../agent/job-properties-new-job-steps-page.md).</span></span>  

6.  <span data-ttu-id="01318-126">После завершения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="01318-126">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="01318-127">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="01318-127">Using Transact-SQL</span></span>  
  
#### <a name="to-add-steps-to-a-sql-server-agent-master-job"></a><span data-ttu-id="01318-128">Добавление шагов в главное задание агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="01318-128">To add steps to a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="01318-129">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="01318-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="01318-130">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="01318-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="01318-131">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="01318-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- creates a job step that changes database access to read-only for the Sales database.   
    -- specifies 5 retry attempts, with each retry to occur after a 5 minute wait.   
    -- assumes that the Weekly Sales Data Backup job already exists  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Set database to read only',  
        @subsystem = N'TSQL',  
        @command = N'ALTER DATABASE SALES SET READ_ONLY',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    ```  
  
 <span data-ttu-id="01318-132">Дополнительные сведения см. в разделе [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="01318-132">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span></span>  
  
  
