---
title: Создание шага задания со службами Analysis Services | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- job steps [Analysis Services]
ms.assetid: 03d4bb86-514b-4a55-97b9-c2c0fa08b428
author: stevestein
ms.author: sstein
ms.openlocfilehash: ed0e63c22d4cad270bcb544b03decba269e4f43a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731382"
---
# <a name="create-an-analysis-services-job-step"></a><span data-ttu-id="4d224-102">Create an Analysis Services Job Step</span><span class="sxs-lookup"><span data-stu-id="4d224-102">Create an Analysis Services Job Step</span></span>
  <span data-ttu-id="4d224-103">В этом разделе описан процесс создания и определения в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] шагов заданий агента [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , которые выполняют команды и запросы служб [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Analysis Services с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] или управляющих объектов SQL Server (SMO).</span><span class="sxs-lookup"><span data-stu-id="4d224-103">This topic describes how to create and define [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job steps in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] that execute [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Analysis Services commands and queries by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] or SQL Server Management Objects.</span></span>  
  
-   <span data-ttu-id="4d224-104">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="4d224-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4d224-105">Ограничения</span><span class="sxs-lookup"><span data-stu-id="4d224-105">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="4d224-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="4d224-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4d224-107">**Создание шагов заданий SQL Server с помощью команд или запросов служб Analysis Services с использованием следующих средств.**</span><span class="sxs-lookup"><span data-stu-id="4d224-107">**To create a SQL Server job steps using Analysis Services commands and/or queries, with:**</span></span>  
  
     [<span data-ttu-id="4d224-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4d224-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="4d224-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4d224-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="4d224-110">Управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="4d224-110">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4d224-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="4d224-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="4d224-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="4d224-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="4d224-113">Если шаг задания использует команду служб Analysis Services, то инструкция команды должна быть методом XMLA **Execute** .</span><span class="sxs-lookup"><span data-stu-id="4d224-113">If the job step uses an Analysis Services command, the command statement must be an XML for Analysis Services **Execute** method.</span></span> <span data-ttu-id="4d224-114">Инструкция не может содержать полный конверт SOAP или метод **Discover** XML для аналитики.</span><span class="sxs-lookup"><span data-stu-id="4d224-114">The statement may not contain a complete Simple Object Access Protocol (SOAP) envelope or an XML for Analysis **Discover** method.</span></span> <span data-ttu-id="4d224-115">Хотя в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] поддерживаются полные конверты SOAP и метод **Discover** , шаги заданий агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в ней не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="4d224-115">While [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] supports complete SOAP envelopes and the **Discover** method, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job steps do not.</span></span> <span data-ttu-id="4d224-116">Дополнительные сведения о XML для служб Analysis Services см. в разделе [Общие сведения о XML для аналитики (XMLA)](https://msdn.microsoft.com/library/ms187190.aspx).</span><span class="sxs-lookup"><span data-stu-id="4d224-116">For more information about XML for Analysis Services, see [XML for Analysis Overview (XMLA)](https://msdn.microsoft.com/library/ms187190.aspx).</span></span>  
  
-   <span data-ttu-id="4d224-117">Если шаг задания использует запрос служб Analysis Services, то инструкция запроса команды должна быть запросом многомерных выражений (MDX).</span><span class="sxs-lookup"><span data-stu-id="4d224-117">If the job step uses an Analysis Services query, the query statement must be a multidimensional expressions (MDX) query.</span></span> <span data-ttu-id="4d224-118">Дополнительные сведения о многомерных выражениях см. в разделе [основные принципы запросов многомерных выражений &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/mdx/mdx-query-fundamentals-analysis-services).</span><span class="sxs-lookup"><span data-stu-id="4d224-118">For more information about MDX, see [MDX Query Fundamentals &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/mdx/mdx-query-fundamentals-analysis-services).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4d224-119">безопасность</span><span class="sxs-lookup"><span data-stu-id="4d224-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4d224-120">Permissions</span><span class="sxs-lookup"><span data-stu-id="4d224-120">Permissions</span></span>  
  
-   <span data-ttu-id="4d224-121">Чтобы запустить шаг задания, использующий подсистему служб Analysis Services, пользователь должен быть членом предопределенной роли сервера **sysadmin** или обладать правом доступа к правильной учетной записи-посреднику, определенной для использования этой подсистемы.</span><span class="sxs-lookup"><span data-stu-id="4d224-121">To run a job step that uses the Analysis Services subsystem, a user must be a member of the **sysadmin** fixed server role or have access to a valid proxy account defined to use this subsystem.</span></span> <span data-ttu-id="4d224-122">К тому же учетная запись службы агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или его учетная запись-посредник должна быть учетной записью администратора служб Analysis Services и правильной учетной записью домена Windows.</span><span class="sxs-lookup"><span data-stu-id="4d224-122">In addition, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account or the proxy must be an Analysis Services administrator and a valid Windows domain account.</span></span>  
  
-   <span data-ttu-id="4d224-123">Записывать выходные данные шага задания в файл могут только элементы предопределенной роли сервера **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="4d224-123">Only members of the **sysadmin** fixed server role can write job step output to a file.</span></span> <span data-ttu-id="4d224-124">Если шаги задания выполняются пользователями, которые являются элементами роли базы данных **SQLAgentUserRole** в базе данных **msdb** , то выходные данные можно записать только в таблицу.</span><span class="sxs-lookup"><span data-stu-id="4d224-124">If the job step is run by users who are members of the **SQLAgentUserRole** database role in the **msdb** database, then the output can be written only to a table.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="4d224-125">записывает выходные данные шага задания в таблицу **sysjobstepslog** базы данных **msdb** .</span><span class="sxs-lookup"><span data-stu-id="4d224-125">Agent writes job step output to the **sysjobstepslog** table in the **msdb** database.</span></span>  
  
-   <span data-ttu-id="4d224-126">Дополнительные сведения см. в разделе [Обеспечение безопасности агента SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="4d224-126">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="4d224-127">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4d224-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-an-analysis-services-command-job-step"></a><span data-ttu-id="4d224-128">Создание шага задания команды службы Analysis Services</span><span class="sxs-lookup"><span data-stu-id="4d224-128">To create an Analysis Services command job step</span></span>  
  
1.  <span data-ttu-id="4d224-129">В **обозревателе объектов** подключитесь к экземпляру [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , а затем разверните этот экземпляр.</span><span class="sxs-lookup"><span data-stu-id="4d224-129">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="4d224-130">Разверните **Агент SQL Server**, создайте задание или щелкните правой кнопкой мыши существующее задание и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="4d224-130">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span> <span data-ttu-id="4d224-131">Дополнительные сведения о создании заданий см. в разделе [Создание заданий](create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="4d224-131">For more information on creating a job, see [Create Jobs](create-jobs.md).</span></span>  
  
3.  <span data-ttu-id="4d224-132">В диалоговом окне **Свойства задания** выберите страницу **Шаги** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="4d224-132">In the **Job Properties** dialog box, click the **Steps** page, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="4d224-133">В диалоговом окне **Новый шаг задания** введите **Имя шага**задания.</span><span class="sxs-lookup"><span data-stu-id="4d224-133">In the **New Job Step** dialog box, type a job **Step name**.</span></span>  
  
5.  <span data-ttu-id="4d224-134">В списке **Типы** выберите **Команда служб SQL Server Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="4d224-134">In the **Type** list, click **SQL Server Analysis Services Command**.</span></span>  
  
6.  <span data-ttu-id="4d224-135">В списке **Выполнять как** выберите учетную запись-посредник, определенную для использования подсистемы команд служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="4d224-135">In the **Run as** list, select a proxy that has been defined to use the Analysis Services Command subsystem.</span></span> <span data-ttu-id="4d224-136">Пользователь, являющийся членом предопределенной роли сервера **sysadmin** , также может выбрать **Учетную запись службы агента SQL Server** , чтобы запустить этот шаг задания.</span><span class="sxs-lookup"><span data-stu-id="4d224-136">A user who is a member of the **sysadmin** fixed server role can also select **SQL Agent Service Account** to run this job step.</span></span>  
  
7.  <span data-ttu-id="4d224-137">Выберите **Сервер** , на котором будет выполняться шаг задания, или введите имя сервера.</span><span class="sxs-lookup"><span data-stu-id="4d224-137">Select the **Server** where the job step will run, or type the server name.</span></span>  
  
8.  <span data-ttu-id="4d224-138">Введите инструкцию в поле **Команда** или нажмите кнопку **Открыть** , чтобы выбрать инструкцию.</span><span class="sxs-lookup"><span data-stu-id="4d224-138">In the **Command** box, type the statement to execute, or click **Open** to select a statement.</span></span>  
  
9. <span data-ttu-id="4d224-139">Перейдите на страницу **Дополнительно** , чтобы определить параметры данного шага задания, например действия, которые должны быть выполнены агентом [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в случае успешного или неуспешного выполнения этого шага, количество попыток выполнения шага задания, а также место записи результатов шага задания.</span><span class="sxs-lookup"><span data-stu-id="4d224-139">Click the **Advanced** page to define options for this job step, such as what action [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent should take if the job step succeeds or fails, how many times the job step should be attempted, and where the job step output should be written.</span></span>  
  
#### <a name="to-create-an-analysis-services-query-job-step"></a><span data-ttu-id="4d224-140">Создание шага задания запроса служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="4d224-140">To create an Analysis Services query job step</span></span>  
  
1.  <span data-ttu-id="4d224-141">В **обозревателе объектов** подключитесь к экземпляру [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , а затем разверните этот экземпляр.</span><span class="sxs-lookup"><span data-stu-id="4d224-141">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="4d224-142">Разверните **Агент SQL Server**, создайте задание или щелкните правой кнопкой мыши существующее задание и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="4d224-142">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span> <span data-ttu-id="4d224-143">Дополнительные сведения о создании заданий см. в разделе [Создание заданий](create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="4d224-143">For more information on creating a job, see [Create Jobs](create-jobs.md).</span></span>  
  
3.  <span data-ttu-id="4d224-144">В диалоговом окне **Свойства задания** выберите страницу **Шаги** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="4d224-144">In the **Job Properties** dialog, click the **Steps** page, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="4d224-145">В диалоговом окне **Новый шаг задания** введите **имя шага**задания.</span><span class="sxs-lookup"><span data-stu-id="4d224-145">In the **New Job Step** dialog, type a job **Step name**.</span></span>  
  
5.  <span data-ttu-id="4d224-146">В списке **Типы** выберите **Запрос служб SQL Server Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="4d224-146">In the **Type** list, click **SQL Server Analysis Services Query**.</span></span>  
  
6.  <span data-ttu-id="4d224-147">В списке **Выполнять как** выберите учетную запись-посредник, определенную для использования подсистемы Query служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="4d224-147">In the **Run as** list, select a proxy that has been defined to use the Analysis Services Query subsystem.</span></span> <span data-ttu-id="4d224-148">Пользователь, являющийся членом предопределенной роли сервера **sysadmin** , также может выбрать **Учетную запись службы агента SQL Server** , чтобы запустить этот шаг задания.</span><span class="sxs-lookup"><span data-stu-id="4d224-148">A user who is a member of the **sysadmin** fixed server role can also select **SQL Agent Service Account** to run this job step.</span></span>  
  
7.  <span data-ttu-id="4d224-149">Выберите пункты **Сервер** и **База данных** , на которых будет выполняться шаг задания, или введите имя сервера или базы данных.</span><span class="sxs-lookup"><span data-stu-id="4d224-149">Select the **Server** and the **Database** where the job step will run, or type the server or database name.</span></span>  
  
8.  <span data-ttu-id="4d224-150">Введите инструкцию в поле **Команда** или нажмите кнопку **Открыть** , чтобы выбрать инструкцию.</span><span class="sxs-lookup"><span data-stu-id="4d224-150">In the **Command** box, type the statement to execute, or click **Open** to select a statement.</span></span>  
  
9. <span data-ttu-id="4d224-151">Перейдите на страницу **Дополнительно** , чтобы определить параметры данного шага задания, например действия, которые должны быть выполнены агентом [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в случае успешного или неуспешного выполнения этого шага, количество попыток выполнения шага задания, а также место записи результатов шага задания.</span><span class="sxs-lookup"><span data-stu-id="4d224-151">Click the **Advanced** page to define options for this job step, such as what action [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent should take if the job step succeeds or fails, how many times the job step should be attempted, and where the job step output should be written.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="4d224-152">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4d224-152">Using Transact-SQL</span></span>  
  
#### <a name="to-create-an-analysis-services-command-job-step"></a><span data-ttu-id="4d224-153">Создание шага задания команды службы Analysis Services</span><span class="sxs-lookup"><span data-stu-id="4d224-153">To create an Analysis Services command job step</span></span>  
  
1.  <span data-ttu-id="4d224-154">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4d224-154">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4d224-155">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="4d224-155">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4d224-156">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="4d224-156">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- Creates a job step that uses XMLA to create a relational data source that references the AdventureWorks2012 Microsoft SQL Server database  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Create a relational data source that references the AdventureWorks2012 Microsoft SQL Server database ',  
        @subsystem = N'ANALYSISCOMMAND',  
        @command = N' <Create xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
        <ParentObject>  
            <DatabaseID>AdventureWorks2012</DatabaseID>  
        </ParentObject>  
        <ObjectDefinition>  
            <DataSource xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="RelationalDataSource">  
                <ID>AdventureWorks2012</ID>  
                <Name>Adventure Works 2012</Name>  
                <ConnectionString>Data Source=localhost;Initial Catalog=AdventureWorks2012;Integrated Security=True</ConnectionString>  
                <ImpersonationInfo>  
                    <ImpersonationMode>ImpersonateServiceAccount</ImpersonationMode>  
                </ImpersonationInfo>  
                <ManagedProvider>System.Data.SqlClient</ManagedProvider>  
                <Timeout>PT0S</Timeout>  
            </DataSource>  
        </ObjectDefinition>  
    </Create>', ;  
    GO  
    ```  
  
 <span data-ttu-id="4d224-157">Дополнительные сведения см. в разделе [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4d224-157">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span></span>  
  
#### <a name="to-create-an-analysis-services-query-job-step"></a><span data-ttu-id="4d224-158">Создание шага задания запроса служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="4d224-158">To create an Analysis Services query job step</span></span>  
  
1.  <span data-ttu-id="4d224-159">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4d224-159">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4d224-160">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="4d224-160">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4d224-161">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="4d224-161">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- Creates a job step that uses MDX to return data  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Returns the Internet sales amount by state',  
        @subsystem = N'ANALYSISQUERY',  
        @command = N' SELECT  
       [Measures].[Internet Sales Amount] ON COLUMNS,  
       [Customer].[State-Province].Members ON ROWS  
    FROM [AdventureWorks2012]',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    ```  
  
 <span data-ttu-id="4d224-162">Дополнительные сведения см. в разделе [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4d224-162">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="4d224-163">Использование управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="4d224-163">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="4d224-164">**Создание шага задания скрипта PowerShell**</span><span class="sxs-lookup"><span data-stu-id="4d224-164">**To create a PowerShell Script job step**</span></span>  
  
 <span data-ttu-id="4d224-165">Используйте класс `JobStep` в выбранном языке программирования, например XMLA или MDX.</span><span class="sxs-lookup"><span data-stu-id="4d224-165">Use the `JobStep` class by using a programming language that you choose, such as XMLA or MDX.</span></span> <span data-ttu-id="4d224-166">Дополнительные сведения см. в статье [Управляющие объекты SQL Server (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="4d224-166">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
