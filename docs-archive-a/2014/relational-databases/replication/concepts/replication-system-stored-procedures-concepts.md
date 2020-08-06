---
title: Основные понятия системных хранимых процедур репликации | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
dev_langs:
- TSQL
helpviewer_keywords:
- stored procedures [SQL Server replication], programming
- programming [SQL Server replication], system stored procedures
- programming interfaces [SQL Server replication]
- system stored procedures [SQL Server replication]
- replication [SQL Server], how-to topics
ms.assetid: 816d2bda-ed72-43ec-aa4d-7ee3dc25fd8a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 50536e5b6816c84dff26c9c9f99c46d02272b7de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750751"
---
# <a name="replication-system-stored-procedures-concepts"></a><span data-ttu-id="88cf4-102">Replication System Stored Procedures Concepts</span><span class="sxs-lookup"><span data-stu-id="88cf4-102">Replication System Stored Procedures Concepts</span></span>
  <span data-ttu-id="88cf4-103">В [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] программный доступ ко всем настраиваемым пользователями функциональным возможностям в топологии репликации предоставляется системными хранимыми процедурами.</span><span class="sxs-lookup"><span data-stu-id="88cf4-103">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], programmatic access to all of the user-configurable functionality in a replication topology is provided by system stored procedures.</span></span> <span data-ttu-id="88cf4-104">Безусловно, хранимые процедуры могут выполняться отдельно с использованием среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] или программы командной строки sqlcmd, но может оказаться более удобным написание файлов скриптов [!INCLUDE[tsql](../../../includes/tsql-md.md)], предназначенных для выполнения задач репликации в логической последовательности.</span><span class="sxs-lookup"><span data-stu-id="88cf4-104">While stored procedures may be executed individually using the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or the sqlcmd command-line utility, it may be beneficial to write [!INCLUDE[tsql](../../../includes/tsql-md.md)] script files that can be executed to perform a logical sequence of replication tasks.</span></span>  
  
 <span data-ttu-id="88cf4-105">Задачи репликации со сценарной поддержкой предоставляют следующие преимущества:</span><span class="sxs-lookup"><span data-stu-id="88cf4-105">Scripting replication tasks provides the following benefits:</span></span>  
  
-   <span data-ttu-id="88cf4-106">Сохраняется постоянная копия шагов, выполненных при развертывании топологии репликации.</span><span class="sxs-lookup"><span data-stu-id="88cf4-106">Keeps a permanent copy of the steps used to deploy your replication topology.</span></span>  
  
-   <span data-ttu-id="88cf4-107">Используется единственный скрипт для настройки нескольких подписчиков.</span><span class="sxs-lookup"><span data-stu-id="88cf4-107">Uses a single script to configure multiple Subscribers.</span></span>  
  
-   <span data-ttu-id="88cf4-108">Обучение новых администраторов базы данных ускоряется, поскольку им предоставляется возможность оценивать, изучать, изменять существующий код или диагностировать нарушения в его работе.</span><span class="sxs-lookup"><span data-stu-id="88cf4-108">Quickly educates new database administrators by enabling them to evaluate, understand, change, or troubleshoot the code.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="88cf4-109">Скрипты могут стать источниками уязвимости системы безопасности, могут вызывать системные функции без уведомления пользователя и его вмешательства и могут содержать учетные данные безопасности в обычном тексте.</span><span class="sxs-lookup"><span data-stu-id="88cf4-109">Scripts can be the source of security vulnerabilities; they can invoke system functions without user knowledge or intervention and may contain security credentials in plain text.</span></span> <span data-ttu-id="88cf4-110">Просмотрите скрипты с точки зрения наличия связанных с ними проблем безопасности, прежде чем их использовать.</span><span class="sxs-lookup"><span data-stu-id="88cf4-110">Review scripts for security issues before you use them.</span></span>  
  
## <a name="creating-replication-scripts"></a><span data-ttu-id="88cf4-111">Создание скриптов репликации</span><span class="sxs-lookup"><span data-stu-id="88cf4-111">Creating Replication Scripts</span></span>  
 <span data-ttu-id="88cf4-112">С точки зрения репликации скрипт представляет собой ряд, состоящий из одной или нескольких инструкций [!INCLUDE[tsql](../../../includes/tsql-md.md)], в котором каждая инструкция выполняет хранимую процедуру репликации.</span><span class="sxs-lookup"><span data-stu-id="88cf4-112">From the standpoint of replication, a script is a series of one or more [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements where each statement executes a replication stored procedure.</span></span> <span data-ttu-id="88cf4-113">Скрипты — это текстовые файлы, часто имеющие такое расширение файла, как SQL, которые могут быть вызваны на выполнение с помощью программы sqlcmd.</span><span class="sxs-lookup"><span data-stu-id="88cf4-113">Scripts are text files, often with a .sql file extension, that can be run using the sqlcmd utility.</span></span> <span data-ttu-id="88cf4-114">После вызова файла скрипта эта программа выполняет инструкции SQL, хранящиеся в файле.</span><span class="sxs-lookup"><span data-stu-id="88cf4-114">When a script file is run, the utility executes the SQL statements stored in the file.</span></span> <span data-ttu-id="88cf4-115">Аналогичным образом скрипт может храниться как объект запроса в проекте среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="88cf4-115">Similarly, a script can be stored as a query object in a [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] project.</span></span>  
  
 <span data-ttu-id="88cf4-116">Для создания скриптов репликации могут применяться следующие способы.</span><span class="sxs-lookup"><span data-stu-id="88cf4-116">Replication scripts can be created in the following ways:</span></span>  
  
-   <span data-ttu-id="88cf4-117">Создание скрипта вручную.</span><span class="sxs-lookup"><span data-stu-id="88cf4-117">Manually create the script.</span></span>  
  
-   <span data-ttu-id="88cf4-118">Использование средств создания скриптов, предусмотренных в мастерах репликации.</span><span class="sxs-lookup"><span data-stu-id="88cf4-118">Use the script generation features that are provided in the replication wizards or</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]<span data-ttu-id="88cf4-119">.</span><span class="sxs-lookup"><span data-stu-id="88cf4-119">.</span></span> <span data-ttu-id="88cf4-120">Дополнительные сведения см. в разделе [Scripting Replication](../scripting-replication.md).</span><span class="sxs-lookup"><span data-stu-id="88cf4-120">For more information, see [Scripting Replication](../scripting-replication.md).</span></span>  
  
-   <span data-ttu-id="88cf4-121">использование объектов RMO для формирования программным путем скрипта создания объекта RMO.</span><span class="sxs-lookup"><span data-stu-id="88cf4-121">Use Replication Management Objects (RMOs) to programmatically generate the script to create an RMO object.</span></span>  
  
 <span data-ttu-id="88cf4-122">При создании скриптов репликации вручную необходимо учитывать следующие соображения.</span><span class="sxs-lookup"><span data-stu-id="88cf4-122">When you manually create replication scripts, keep the following considerations in mind:</span></span>  
  
-   <span data-ttu-id="88cf4-123">Скрипты языка [!INCLUDE[tsql](../../../includes/tsql-md.md)] содержат один или несколько пакетов.</span><span class="sxs-lookup"><span data-stu-id="88cf4-123">[!INCLUDE[tsql](../../../includes/tsql-md.md)] scripts have one or more batches.</span></span> <span data-ttu-id="88cf4-124">Команда GO означает конец пакета.</span><span class="sxs-lookup"><span data-stu-id="88cf4-124">The GO command signals the end of a batch.</span></span> <span data-ttu-id="88cf4-125">Если скрипт языка [!INCLUDE[tsql](../../../includes/tsql-md.md)] не содержит команд GO, то он выполняется как единый пакет.</span><span class="sxs-lookup"><span data-stu-id="88cf4-125">If a [!INCLUDE[tsql](../../../includes/tsql-md.md)] script does not have any GO commands, it is executed as a single batch.</span></span>  
  
-   <span data-ttu-id="88cf4-126">Если в одном пакете должно быть выполнено несколько хранимых процедур репликации, то после первой процедуры все последующие процедуры в пакете должны быть указаны с предшествующим ключевым словом EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="88cf4-126">When executing multiple replication stored procedures in a single batch, after the first procedure, all subsequent procedures in the batch must be preceded by the EXECUTE keyword.</span></span>  
  
-   <span data-ttu-id="88cf4-127">Все хранимые процедуры в пакете должны быть откомпилированы до выполнения пакета.</span><span class="sxs-lookup"><span data-stu-id="88cf4-127">All stored procedures in a batch must compile before a batch will execute.</span></span> <span data-ttu-id="88cf4-128">Но после компиляции пакета и создания плана выполнения ошибки времени выполнения могут происходить или не происходить.</span><span class="sxs-lookup"><span data-stu-id="88cf4-128">However, once the batch has been compiled, and an execution plan has been created, a run-time error may or may not occur.</span></span>  
  
-   <span data-ttu-id="88cf4-129">Если скрипты создаются для настройки конфигурации репликации, то должна использоваться проверка подлинности Windows для исключения необходимости хранить учетные данные безопасности в файле скрипта.</span><span class="sxs-lookup"><span data-stu-id="88cf4-129">When creating scripts to configure replication, you should use Windows Authentication to avoid storing security credentials in the script file.</span></span> <span data-ttu-id="88cf4-130">В случае необходимости хранения учетных данных в файле скрипта этот файл следует защищать во избежание несанкционированного доступа.</span><span class="sxs-lookup"><span data-stu-id="88cf4-130">If you must store credentials in a script file, you must secure the file to prevent unauthorized access.</span></span>  
  
## <a name="sample-replication-script"></a><span data-ttu-id="88cf4-131">Образец скрипта репликации</span><span class="sxs-lookup"><span data-stu-id="88cf4-131">Sample Replication Script</span></span>  
 <span data-ttu-id="88cf4-132">Следующий скрипт может быть выполнен для установки на сервере средств публикации и распределения.</span><span class="sxs-lookup"><span data-stu-id="88cf4-132">The following script can be executed to setup publishing and distribution on a server.</span></span>  
  
```  
-- This script uses sqlcmd scripting variables. They are in the form  
-- $(MyVariable). For information about how to use scripting variables    
-- on the command line and in SQL Server Management Studio, see the   
-- "Executing Replication Scripts" section in the topic  
-- "Programming Replication Using System Stored Procedures".  
  
-- Install the Distributor and the distribution database.  
DECLARE @distributor AS sysname;  
DECLARE @distributionDB AS sysname;  
DECLARE @publisher AS sysname;  
DECLARE @directory AS nvarchar(500);  
DECLARE @publicationDB AS sysname;  
-- Specify the Distributor name.  
SET @distributor = $(DistPubServer);  
-- Specify the distribution database.  
SET @distributionDB = N'distribution';  
-- Specify the Publisher name.  
SET @publisher = $(DistPubServer);  
-- Specify the replication working directory.  
SET @directory = N'\\' + $(DistPubServer) + '\repldata';  
-- Specify the publication database.  
SET @publicationDB = N'AdventureWorks2012';   
  
-- Install the server MYDISTPUB as a Distributor using the defaults,  
-- including autogenerating the distributor password.  
USE master  
EXEC sp_adddistributor @distributor = @distributor;  
  
-- Create a new distribution database using the defaults, including  
-- using Windows Authentication.  
USE master  
EXEC sp_adddistributiondb @database = @distributionDB,   
    @security_mode = 1;  
GO  
  
-- Create a Publisher and enable AdventureWorks2012 for replication.  
-- Add MYDISTPUB as a publisher with MYDISTPUB as a local distributor  
-- and use Windows Authentication.  
DECLARE @distributionDB AS sysname;  
DECLARE @publisher AS sysname;  
-- Specify the distribution database.  
SET @distributionDB = N'distribution';  
-- Specify the Publisher name.  
SET @publisher = $(DistPubServer);  
  
USE [distribution]  
EXEC sp_adddistpublisher @publisher=@publisher,   
    @distribution_db=@distributionDB,   
    @security_mode = 1;  
GO  
  
```  
  
 <span data-ttu-id="88cf4-133">Затем этот скрипт может быть сохранен локально в качестве `instdistpub.sql`, чтобы его можно было выполнить один или несколько раз, если это потребуется.</span><span class="sxs-lookup"><span data-stu-id="88cf4-133">This script can then be saved locally as `instdistpub.sql` so that it can be run or rerun when needed.</span></span>  
  
 <span data-ttu-id="88cf4-134">Предыдущий скрипт включает переменные скрипта **sqlcmd**, которые используются во многих примерах кода репликации в электронной документации по [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="88cf4-134">The previous script includes **sqlcmd** scripting variables, which are used in many of the replication code samples in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Books Online.</span></span> <span data-ttu-id="88cf4-135">Переменные скрипта определяются с использованием синтаксиса `$(MyVariable)`.</span><span class="sxs-lookup"><span data-stu-id="88cf4-135">Scripting variables are defined by using `$(MyVariable)` syntax.</span></span> <span data-ttu-id="88cf4-136">Значения переменных могут быть переданы в скрипт в командной строке или в среде [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="88cf4-136">Values for variables can be passed to a script at the command line or in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="88cf4-137">Дополнительные сведения см. в следующем подразделе данного раздела, «Выполнение скриптов репликации».</span><span class="sxs-lookup"><span data-stu-id="88cf4-137">For more information, see the next section in this topic, "Executing Replication Scripts."</span></span>  
  
## <a name="executing-replication-scripts"></a><span data-ttu-id="88cf4-138">Выполнение скриптов репликации</span><span class="sxs-lookup"><span data-stu-id="88cf4-138">Executing Replication Scripts</span></span>  
 <span data-ttu-id="88cf4-139">Для выполнения скрипта репликации после его создания может быть использован один из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="88cf4-139">Once created, a replication script can be executed in one of the following ways:</span></span>  
  
### <a name="creating-a-sql-query-file-in-sql-server-management-studio"></a><span data-ttu-id="88cf4-140">Создание файла SQL-запроса в среде SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="88cf4-140">Creating a SQL Query File in SQL Server Management Studio</span></span>  
 <span data-ttu-id="88cf4-141">Файл скрипта репликации [!INCLUDE[tsql](../../../includes/tsql-md.md)] может быть создан в проекте среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] как файл SQL-запроса.</span><span class="sxs-lookup"><span data-stu-id="88cf4-141">A replication [!INCLUDE[tsql](../../../includes/tsql-md.md)] script file can be created as a SQL Query file in a [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] project.</span></span> <span data-ttu-id="88cf4-142">После записи скрипта может быть создано соединение с базой данных для этого файла запроса и скрипт вызван на выполнение.</span><span class="sxs-lookup"><span data-stu-id="88cf4-142">After the script is written, a connection can be made to the database for this query file and the script can be executed.</span></span> <span data-ttu-id="88cf4-143">Дополнительные сведения о создании [!INCLUDE[tsql](../../../includes/tsql-md.md)] скриптов с помощью [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] см. в разделе [редакторы запросов и текста &#40;SQL Server Management Studio&#41;](../../scripting/query-and-text-editors-sql-server-management-studio.md)).</span><span class="sxs-lookup"><span data-stu-id="88cf4-143">For more information about how to create [!INCLUDE[tsql](../../../includes/tsql-md.md)] scripts by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], see [Query and Text Editors &#40;SQL Server Management Studio&#41;](../../scripting/query-and-text-editors-sql-server-management-studio.md)).</span></span>  
  
 <span data-ttu-id="88cf4-144">Чтобы использовать скрипт с переменными скрипта, необходимо запустить среду [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] в режиме **sqlcmd**.</span><span class="sxs-lookup"><span data-stu-id="88cf4-144">To use a script that includes scripting variables, [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] must be running in **sqlcmd** mode.</span></span> <span data-ttu-id="88cf4-145">В режиме **sqlcmd** редактор запросов распознает дополнительный синтаксис, характерный для **sqlcmd**, например обозначение `:setvar` для значений переменных.</span><span class="sxs-lookup"><span data-stu-id="88cf4-145">In **sqlcmd** mode, the Query Editor accepts additional syntax specific to **sqlcmd**, such as `:setvar`, which is used to a value for a variable.</span></span> <span data-ttu-id="88cf4-146">Дополнительные сведения о режиме **sqlcmd** см. в разделе об [изменении скриптов SQLCMD при помощи редактора запросов](../../scripting/edit-sqlcmd-scripts-with-query-editor.md).</span><span class="sxs-lookup"><span data-stu-id="88cf4-146">For more information about **sqlcmd** mode, see [Edit SQLCMD Scripts with Query Editor](../../scripting/edit-sqlcmd-scripts-with-query-editor.md).</span></span> <span data-ttu-id="88cf4-147">В следующем скрипте `:setvar` используется для предоставления значения переменной `$(DistPubServer)`.</span><span class="sxs-lookup"><span data-stu-id="88cf4-147">In the following script, `:setvar` is used to provide a value for the `$(DistPubServer)` variable.</span></span>  
  
```  
:setvar DistPubServer N'MyPublisherAndDistributor';  
  
-- Install the Distributor and the distribution database.  
DECLARE @distributor AS sysname;  
DECLARE @distributionDB AS sysname;  
DECLARE @publisher AS sysname;  
DECLARE @directory AS nvarchar(500);  
DECLARE @publicationDB AS sysname;  
-- Specify the Distributor name.  
SET @distributor = $(DistPubServer);  
-- Specify the distribution database.  
SET @distributionDB = N'distribution';  
-- Specify the Publisher name.  
SET @publisher = $(DistPubServer);  
  
--  
-- Additional code goes here  
--  
```  
  
### <a name="using-the-sqlcmd-utility-from-the-command-line"></a><span data-ttu-id="88cf4-148">Использование программы sqlcmd в командной строке</span><span class="sxs-lookup"><span data-stu-id="88cf4-148">Using the sqlcmd Utility from the Command Line</span></span>  
 <span data-ttu-id="88cf4-149">Следующий пример показывает, как выполнить файл скрипта `instdistpub.sql` из командной строки с применением [программы sqlcmd](../../../tools/sqlcmd-utility.md):</span><span class="sxs-lookup"><span data-stu-id="88cf4-149">The following example shows how the command line is used to execute the `instdistpub.sql` script file using the [sqlcmd utility](../../../tools/sqlcmd-utility.md):</span></span>  
  
```  
sqlcmd.exe -E -S sqlserverinstance -i C:\instdistpub.sql -o C:\output.log -v DistPubServer="N'MyDistributorAndPublisher'"  
```  
  
 <span data-ttu-id="88cf4-150">В этом примере параметр `-E` указывает, что используется проверка подлинности Windows при соединении с [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="88cf4-150">In this example, the `-E` switch indicates that Windows Authentication is used when connecting to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="88cf4-151">Если используется проверка подлинности Windows, то отсутствует необходимость хранить имя пользователя и пароль в файле скрипта.</span><span class="sxs-lookup"><span data-stu-id="88cf4-151">When using Windows Authentication, there is no need to store a username and password in the script file.</span></span> <span data-ttu-id="88cf4-152">Имя и путь к файлу скрипта задаются параметром `-i`, а имя выходного файла — параметром `-o` (если используется этот параметр, то вывод программы [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] записывается в указанный файл, а не на консоль).</span><span class="sxs-lookup"><span data-stu-id="88cf4-152">The name and path of the script file is specified by the `-i` switch and the name of the output file is specified by the `-o` switch (output from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is written to this file instead of the console when this switch is used).</span></span> <span data-ttu-id="88cf4-153">Программа `sqlcmd` позволяет передавать переменные скрипта в скрипт [!INCLUDE[tsql](../../../includes/tsql-md.md)] во время выполнения с помощью параметра `-v`.</span><span class="sxs-lookup"><span data-stu-id="88cf4-153">The `sqlcmd` utility enables you to pass scripting variables to a [!INCLUDE[tsql](../../../includes/tsql-md.md)] script at runtime using the `-v` switch.</span></span> <span data-ttu-id="88cf4-154">В этом примере программа `sqlcmd` заменяет каждое вхождение переменной `$(DistPubServer)` в скрипте значением `N'MyDistributorAndPublisher'` перед выполнением.</span><span class="sxs-lookup"><span data-stu-id="88cf4-154">In this example, `sqlcmd` replaces every instance of `$(DistPubServer)` in the script with the value `N'MyDistributorAndPublisher'` before execution.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="88cf4-155">Параметр `-X` позволяет запретить использование переменных сценария.</span><span class="sxs-lookup"><span data-stu-id="88cf4-155">The `-X` switch disables scripting variables.</span></span>  
  
### <a name="automating-tasks-in-a-batch-file"></a><span data-ttu-id="88cf4-156">Автоматизация задач с применением пакетного файла</span><span class="sxs-lookup"><span data-stu-id="88cf4-156">Automating Tasks in a Batch File</span></span>  
 <span data-ttu-id="88cf4-157">Применение пакетного файла позволяет автоматизировать задачи администрирования репликации, задачи синхронизации репликации и другие задачи с помощью одного и того же пакетного файла.</span><span class="sxs-lookup"><span data-stu-id="88cf4-157">By using a batch file, replication administration tasks, replication synchronization tasks, and other tasks can be automated in the same batch file.</span></span> <span data-ttu-id="88cf4-158">Следующий пакетный файл с помощью программы **sqlcmd** удаляет и заново создает базу данных подписки, а затем добавляет подписку слиянием по запросу.</span><span class="sxs-lookup"><span data-stu-id="88cf4-158">The following batch file uses the **sqlcmd** utility to drop and recreate the subscription database and add a merge pull subscription.</span></span> <span data-ttu-id="88cf4-159">Затем в этом файле предусмотрен вызов агента слияния для синхронизации новой подписки:</span><span class="sxs-lookup"><span data-stu-id="88cf4-159">Then the file invokes the merge agent to synchronize the new subscription:</span></span>  
  
```  
REM ----------------------Script to synchronize merge subscription ----------------------  
REM -- Creates subscription database and   
REM -- synchronizes the subscription to MergeSalesPerson.  
REM -- Current computer acts as both Publisher and Subscriber.  
REM -------------------------------------------------------------------------------------  
  
SET Publisher=%computername%  
SET Subscriber=%computername%  
SET PubDb=AdventureWorks  
SET SubDb=AdventureWorksReplica  
SET PubName=AdvWorksSalesOrdersMerge  
  
REM -- Drop and recreate the subscription database at the Subscriber  
sqlcmd /S%Subscriber% /E /Q"USE master IF EXISTS (SELECT * FROM sysdatabases WHERE name='%SubDb%' ) DROP DATABASE %SubDb%"  
sqlcmd /S%Subscriber% /E /Q"USE master CREATE DATABASE %SubDb%"  
  
REM -- Add a pull subscription at the Subscriber  
sqlcmd /S%Subscriber% /E /Q"USE %SubDb% EXEC sp_addmergepullsubscription @publisher = %Publisher%, @publication = %PubName%, @publisher_db = %PubDb%"  
sqlcmd /S%Subscriber% /E /Q"USE %SubDb%  EXEC sp_addmergepullsubscription_agent @publisher = %Publisher%, @publisher_db = %PubDb%, @publication = %PubName%, @subscriber = %Subscriber%, @subscriber_db = %SubDb%, @distributor = %Publisher%"  
  
REM -- This batch file starts the merge agent at the Subscriber to   
REM -- synchronize a pull subscription to a merge publication.  
REM -- The following must be supplied on one line.  
"\Program Files\Microsoft SQL Server\120\COM\REPLMERG.EXE"  -Publisher  %Publisher% -Subscriber  %Subscriber%  -Distributor %Publisher%  -PublisherDB  %PubDb% -SubscriberDB %SubDb% -Publication %PubName% -PublisherSecurityMode 1 -OutputVerboseLevel 1  -Output  -SubscriberSecurityMode 1  -SubscriptionType 1 -DistributorSecurityMode 1 -Validate 3  
  
```  
  
## <a name="scripting-common-replication-tasks"></a><span data-ttu-id="88cf4-160">Сценарная поддержка общих задач репликации</span><span class="sxs-lookup"><span data-stu-id="88cf4-160">Scripting Common Replication Tasks</span></span>  
 <span data-ttu-id="88cf4-161">Ниже перечислены некоторые из наиболее распространенных задач репликации, которые могут быть реализованы в виде сценариев с использованием системных хранимых процедур:</span><span class="sxs-lookup"><span data-stu-id="88cf4-161">The following are some of the most common replication tasks can be scripted using system stored procedures:</span></span>  
  
-   <span data-ttu-id="88cf4-162">Настройка публикации и распределения</span><span class="sxs-lookup"><span data-stu-id="88cf4-162">Configuring publishing and distribution</span></span>  
  
-   <span data-ttu-id="88cf4-163">Изменение свойств издателя и распространителя</span><span class="sxs-lookup"><span data-stu-id="88cf4-163">Modifying Publisher and Distributor properties</span></span>  
  
-   <span data-ttu-id="88cf4-164">Отключение публикации и распространения</span><span class="sxs-lookup"><span data-stu-id="88cf4-164">Disabling publishing and distribution</span></span>  
  
-   <span data-ttu-id="88cf4-165">Создание публикаций и определение статей</span><span class="sxs-lookup"><span data-stu-id="88cf4-165">Creating publications and defining articles</span></span>  
  
-   <span data-ttu-id="88cf4-166">Удаление публикаций и статей</span><span class="sxs-lookup"><span data-stu-id="88cf4-166">Deleting publications and articles</span></span>  
  
-   <span data-ttu-id="88cf4-167">Создание подписки по запросу</span><span class="sxs-lookup"><span data-stu-id="88cf4-167">Creating a pull subscription</span></span>  
  
-   <span data-ttu-id="88cf4-168">Изменение подписки по запросу</span><span class="sxs-lookup"><span data-stu-id="88cf4-168">Modifying a pull subscription</span></span>  
  
-   <span data-ttu-id="88cf4-169">Удаление подписки по запросу</span><span class="sxs-lookup"><span data-stu-id="88cf4-169">Deleting a pull subscription</span></span>  
  
-   <span data-ttu-id="88cf4-170">Создание принудительной подписки</span><span class="sxs-lookup"><span data-stu-id="88cf4-170">Creating a push subscription</span></span>  
  
-   <span data-ttu-id="88cf4-171">Изменение принудительной подписки</span><span class="sxs-lookup"><span data-stu-id="88cf4-171">Modifying a push subscription</span></span>  
  
-   <span data-ttu-id="88cf4-172">Удаление принудительной подписки</span><span class="sxs-lookup"><span data-stu-id="88cf4-172">Deleting a push subscription</span></span>  
  
-   <span data-ttu-id="88cf4-173">Синхронизация подписки по запросу</span><span class="sxs-lookup"><span data-stu-id="88cf4-173">Synchronizing a pull subscription</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88cf4-174">См. также:</span><span class="sxs-lookup"><span data-stu-id="88cf4-174">See Also</span></span>  
 <span data-ttu-id="88cf4-175">[Основные понятия для программирования репликации](replication-programming-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="88cf4-175">[Replication Programming Concepts](replication-programming-concepts.md) </span></span>  
 <span data-ttu-id="88cf4-176">[Хранимые процедуры репликации (Transact-SQL)](/sql/relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="88cf4-176">[Replication Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql) </span></span>  
 [<span data-ttu-id="88cf4-177">Создание скриптов репликации</span><span class="sxs-lookup"><span data-stu-id="88cf4-177">Scripting Replication</span></span>](../scripting-replication.md)  
  
  
