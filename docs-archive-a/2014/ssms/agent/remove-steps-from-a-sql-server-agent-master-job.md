---
title: Удаление шагов из главного задания агента SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 871e6162-1221-464d-8f7f-7e454dcd9edb
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5996971225ee0b300b307c5af24dec464dbfd43c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668572"
---
# <a name="remove-steps-from-a-sql-server-agent-master-job"></a><span data-ttu-id="b387a-102">Remove Steps from a SQL Server Agent Master Job</span><span class="sxs-lookup"><span data-stu-id="b387a-102">Remove Steps from a SQL Server Agent Master Job</span></span>
  <span data-ttu-id="b387a-103">В этом разделе описывается удаление шагов из главного задания агента SQL Server в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b387a-103">This topic describes how to remove steps from a SQL Server Agent master job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="b387a-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="b387a-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b387a-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="b387a-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b387a-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="b387a-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="b387a-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="b387a-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b387a-108">**Удаление шагов из главного задания агента SQL Server с помощью:**</span><span class="sxs-lookup"><span data-stu-id="b387a-108">**To remove steps from a SQL Server Agent master job, using:**</span></span>  
  
     [<span data-ttu-id="b387a-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b387a-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b387a-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b387a-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b387a-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="b387a-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b387a-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="b387a-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="b387a-113">Главное задание агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не может быть ориентировано как на локальный, так и на удаленный сервер.</span><span class="sxs-lookup"><span data-stu-id="b387a-113">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent master job cannot be targeted at both local and remote servers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b387a-114">безопасность</span><span class="sxs-lookup"><span data-stu-id="b387a-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b387a-115">Permissions</span><span class="sxs-lookup"><span data-stu-id="b387a-115">Permissions</span></span>  
 <span data-ttu-id="b387a-116">Если пользователь не является членом предопределенной роли сервера **sysadmin** , он может изменять только свои собственные задания.</span><span class="sxs-lookup"><span data-stu-id="b387a-116">Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own.</span></span> <span data-ttu-id="b387a-117">Дополнительные сведения см. в разделе [Обеспечение безопасности агента SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="b387a-117">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b387a-118">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b387a-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-remove-steps-from-a-sql-server-agent-master-job"></a><span data-ttu-id="b387a-119">Удаление шагов из главного задания агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="b387a-119">To remove steps from a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="b387a-120">В **обозревателе объектов** щелкните знак «плюс», чтобы развернуть сервер, содержащий задание, в котором нужно удалить шаги.</span><span class="sxs-lookup"><span data-stu-id="b387a-120">In **Object Explorer,** click the plus sign to expand the server that contains the job where you want to delete steps.</span></span>  
  
2.  <span data-ttu-id="b387a-121">Щелкните знак "плюс", чтобы развернуть **Агент SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="b387a-121">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="b387a-122">Чтобы развернуть папку **Задания** , щелкните значок «плюс».</span><span class="sxs-lookup"><span data-stu-id="b387a-122">Click the plus sign to expand the **Jobs** folder.</span></span>  
  
4.  <span data-ttu-id="b387a-123">Щелкните правой кнопкой мыши задание, шаги которого требуется удалить, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="b387a-123">Right-click the job where you want to delete steps and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="b387a-124">В диалоговом окне **Свойства задания —**_Job_name_ в разделе **Выбор страницы**выберите **шаги**.</span><span class="sxs-lookup"><span data-stu-id="b387a-124">In the **Job Properties -**_job_name_ dialog box, under **Select a page**, select **Steps**.</span></span>  
  
6.  <span data-ttu-id="b387a-125">В списке **Список шагов задания**выберите шаг задания, который необходимо удалить, и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="b387a-125">Under **Job step list**, select the job step you want to delete and click **Delete**.</span></span>  
  
7.  <span data-ttu-id="b387a-126">После завершения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b387a-126">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b387a-127">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b387a-127">Using Transact-SQL</span></span>  
  
#### <a name="to-remove-steps-from-a-sql-server-agent-master-job"></a><span data-ttu-id="b387a-128">Удаление шагов из главного задания агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="b387a-128">To remove steps from a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="b387a-129">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b387a-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b387a-130">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="b387a-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b387a-131">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="b387a-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- removes job step 1 from the job Weekly Sales Data Backup   
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_delete_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_id = 1 ;  
    GO  
    ```  
  
 <span data-ttu-id="b387a-132">Дополнительные сведения см. в разделе [sp_delete_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b387a-132">For more information, see [sp_delete_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-jobstep-transact-sql).</span></span>  
  
  
