---
title: Изменение шагов главного задания агента SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 8f1a0ee6-49ff-4080-94ca-d661daeff2a6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7a9defc17b5b39ab8a322b6da29960eb9968c2e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668604"
---
# <a name="change-steps-of-a-sql-server-agent-master-job"></a><span data-ttu-id="97ec1-102">Change Steps of a SQL Server Agent Master Job</span><span class="sxs-lookup"><span data-stu-id="97ec1-102">Change Steps of a SQL Server Agent Master Job</span></span>
  <span data-ttu-id="97ec1-103">В этом разделе описано внесение изменений в шаги главного задания агента SQL Server в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="97ec1-103">This topic describes how to make changes to the steps of a SQL Server Agent master job in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="97ec1-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="97ec1-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="97ec1-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="97ec1-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="97ec1-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="97ec1-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="97ec1-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="97ec1-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="97ec1-108">**Внесение изменений в шаги главного задания агента SQL Server с помощью:**</span><span class="sxs-lookup"><span data-stu-id="97ec1-108">**To make changes to the steps of a SQL Server Agent master job, using:**</span></span>  
  
     [<span data-ttu-id="97ec1-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="97ec1-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="97ec1-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="97ec1-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="97ec1-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="97ec1-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="97ec1-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="97ec1-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="97ec1-113">Главное задание агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не может быть ориентировано как на локальный, так и на удаленный сервер.</span><span class="sxs-lookup"><span data-stu-id="97ec1-113">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent master job cannot be targeted at both local and remote servers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="97ec1-114">безопасность</span><span class="sxs-lookup"><span data-stu-id="97ec1-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="97ec1-115">Permissions</span><span class="sxs-lookup"><span data-stu-id="97ec1-115">Permissions</span></span>  
 <span data-ttu-id="97ec1-116">Если пользователь не является членом предопределенной роли сервера **sysadmin** , он может изменять только свои собственные задания.</span><span class="sxs-lookup"><span data-stu-id="97ec1-116">Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own.</span></span> <span data-ttu-id="97ec1-117">Дополнительные сведения см. в разделе [Обеспечение безопасности агента SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="97ec1-117">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="97ec1-118">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="97ec1-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-make-changes-to-the-steps-of-a-sql-server-agent-master-job"></a><span data-ttu-id="97ec1-119">Внесение изменений в шаги главного задания агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="97ec1-119">To make changes to the steps of a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="97ec1-120">В **обозревателе объектов** щелкните знак «плюс», чтобы развернуть сервер, содержащий задание, в котором нужно изменить шаги.</span><span class="sxs-lookup"><span data-stu-id="97ec1-120">In **Object Explorer,** click the plus sign to expand the server that contains the job where you want to modify steps.</span></span>  
  
2.  <span data-ttu-id="97ec1-121">Щелкните знак "плюс", чтобы развернуть **Агент SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="97ec1-121">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="97ec1-122">Чтобы развернуть папку **Задания** , щелкните значок «плюс».</span><span class="sxs-lookup"><span data-stu-id="97ec1-122">Click the plus sign to expand the **Jobs** folder.</span></span>  
  
4.  <span data-ttu-id="97ec1-123">Щелкните правой кнопкой мыши задание, шаги которого требуется изменить, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="97ec1-123">Right-click the job where you want to modify steps and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="97ec1-124">В диалоговом окне **Свойства задания —**_Job_name_ в разделе **Выбор страницы**выберите **шаги**.</span><span class="sxs-lookup"><span data-stu-id="97ec1-124">In the **Job Properties -**_job_name_ dialog box, under **Select a page**, select **Steps**.</span></span>  
  
6.  <span data-ttu-id="97ec1-125">Нажмите кнопку **изменить** , чтобы открыть диалоговое окно **Свойства шага задания —**_job_step_name_ .</span><span class="sxs-lookup"><span data-stu-id="97ec1-125">Click **Edit** to open the **Job Step Properties -**_job_step_name_ dialog box.</span></span> <span data-ttu-id="97ec1-126">Дополнительные сведения о параметрах, доступных в этом диалоговом окне, см. в разделе [Свойства шага задания: новый шаг задания &#40;общие&#41;страницы](../../integration-services/general-page-of-integration-services-designers-options.md) и [Свойства шага задания: новый шаг задания &#40;дополнительные&#41;страницы ](job-step-properties-new-job-step-advanced-page.md).</span><span class="sxs-lookup"><span data-stu-id="97ec1-126">For more information on the available options in this dialog box, see [Job Step Properties: New Job Step &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md) and [Job Step Properties: New Job Step &#40;Advanced Page&#41;](job-step-properties-new-job-step-advanced-page.md).</span></span>  
  
7.  <span data-ttu-id="97ec1-127">После завершения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="97ec1-127">When finished, click **OK**.</span></span>  
  
8.  <span data-ttu-id="97ec1-128">В диалоговом окне **Свойства задания —**_Job_name_ нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="97ec1-128">In the **Job Properties -**_job_name_ dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="97ec1-129">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="97ec1-129">Using Transact-SQL</span></span>  
  
#### <a name="to-make-changes-to-the-steps-of-a-sql-server-agent-master-job"></a><span data-ttu-id="97ec1-130">Внесение изменений в шаги главного задания агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="97ec1-130">To make changes to the steps of a SQL Server Agent master job</span></span>  
  
1.  <span data-ttu-id="97ec1-131">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="97ec1-131">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="97ec1-132">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="97ec1-132">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="97ec1-133">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="97ec1-133">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- changes the number of retry attempts for the first step of the Weekly Sales Data Backup job.   
    -- After running this example, the number of retry attempts is 10   
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_id = 1,  
        @retry_attempts = 10 ;  
    GO  
    ```  
  
 <span data-ttu-id="97ec1-134">Дополнительные сведения см. в разделе [sp_update_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="97ec1-134">For more information, see [sp_update_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql).</span></span>  
  
  
