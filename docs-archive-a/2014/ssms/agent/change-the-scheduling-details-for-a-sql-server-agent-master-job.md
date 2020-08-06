---
title: Изменение параметров расписания для главного задания агента SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: f5414451-4d8e-464b-bd9e-f2b70c6899b3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 85546bc93e6626bfcc85a28f06a4c2fe24fe9fd1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668602"
---
# <a name="change-the-scheduling-details-for-a-sql-server-agent-master-job"></a><span data-ttu-id="999c1-102">Change the Scheduling Details for a SQL Server Agent Master Job</span><span class="sxs-lookup"><span data-stu-id="999c1-102">Change the Scheduling Details for a SQL Server Agent Master Job</span></span>
  <span data-ttu-id="999c1-103">В этом разделе описывается изменение параметров расписания для определения задания в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="999c1-103">This topic describes how to change the scheduling details for a job definition in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="999c1-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="999c1-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="999c1-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="999c1-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="999c1-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="999c1-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="999c1-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="999c1-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="999c1-108">**Изменение параметров расписания для определения задания с помощью:**</span><span class="sxs-lookup"><span data-stu-id="999c1-108">**To change the scheduling details for a job definition, using:**</span></span>  
  
     [<span data-ttu-id="999c1-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="999c1-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="999c1-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="999c1-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="999c1-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="999c1-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="999c1-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="999c1-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="999c1-113">Главное задание агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не может быть ориентировано как на локальный, так и на удаленный сервер.</span><span class="sxs-lookup"><span data-stu-id="999c1-113">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent master job cannot be targeted at both local and remote servers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="999c1-114">безопасность</span><span class="sxs-lookup"><span data-stu-id="999c1-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="999c1-115">Permissions</span><span class="sxs-lookup"><span data-stu-id="999c1-115">Permissions</span></span>  
 <span data-ttu-id="999c1-116">Если пользователь не является членом предопределенной роли сервера **sysadmin** , он может изменять только свои собственные задания.</span><span class="sxs-lookup"><span data-stu-id="999c1-116">Unless you are a member of the **sysadmin** fixed server role, you can only modify jobs that you own.</span></span> <span data-ttu-id="999c1-117">Дополнительные сведения см. в разделе [Обеспечение безопасности агента SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="999c1-117">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="999c1-118">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="999c1-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-change-the-scheduling-details-for-a-job-definition"></a><span data-ttu-id="999c1-119">Изменение параметров расписания для определения задания</span><span class="sxs-lookup"><span data-stu-id="999c1-119">To change the scheduling details for a job definition</span></span>  
  
1.  <span data-ttu-id="999c1-120">В **обозревателе объектов** щелкните знак «плюс», чтобы развернуть сервер, содержащий задание, для которого нужно изменить расписание.</span><span class="sxs-lookup"><span data-stu-id="999c1-120">In **Object Explorer,** click the plus sign to expand the server that contains the job whose schedule you want to edit.</span></span>  
  
2.  <span data-ttu-id="999c1-121">Щелкните знак "плюс", чтобы развернуть **Агент SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="999c1-121">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="999c1-122">Чтобы развернуть папку **Задания** , щелкните значок «плюс».</span><span class="sxs-lookup"><span data-stu-id="999c1-122">Click the plus sign to expand the **Jobs** folder.</span></span>  
  
4.  <span data-ttu-id="999c1-123">Щелкните правой кнопкой мыши задание, расписание которого необходимо изменить, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="999c1-123">Right-click the job whose schedule you want to edit and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="999c1-124">В диалоговом окне **Свойства задания —**_Job_name_ в разделе **Выбор страницы**выберите пункт **расписания**.</span><span class="sxs-lookup"><span data-stu-id="999c1-124">In the **Job Properties -**_job_name_ dialog box, under **Select a page**, select **Schedules**.</span></span> <span data-ttu-id="999c1-125">Дополнительные сведения о параметрах, доступных на этой странице, см. в разделе [Свойства задания: создание задания &#40;расписания&#41;](job-properties-new-job-schedules-page.md).</span><span class="sxs-lookup"><span data-stu-id="999c1-125">For more information on the available options on this page, see [Job Properties: New Job &#40;Schedules Page&#41;](job-properties-new-job-schedules-page.md).</span></span>  
  
6.  <span data-ttu-id="999c1-126">После завершения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="999c1-126">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="999c1-127">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="999c1-127">Using Transact-SQL</span></span>  
  
#### <a name="to-change-the-scheduling-details-for-a-job-definition"></a><span data-ttu-id="999c1-128">Изменение параметров расписания для определения задания</span><span class="sxs-lookup"><span data-stu-id="999c1-128">To change the scheduling details for a job definition</span></span>  
  
1.  <span data-ttu-id="999c1-129">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="999c1-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="999c1-130">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="999c1-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="999c1-131">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="999c1-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- changes the enabled status of the NightlyJobs schedule to 0   
    -- and sets the owner to terrid.   
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_schedule  
        @name = 'NightlyJobs',  
        @enabled = 0,  
        @owner_login_name = 'terrid' ;  
    GO  
    ```  
  
 <span data-ttu-id="999c1-132">Дополнительные сведения см. в разделе [sp_update_schedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-schedule-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="999c1-132">For more information, see [sp_update_schedule &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-schedule-transact-sql).</span></span>  
  
  
