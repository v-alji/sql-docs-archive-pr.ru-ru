---
title: Создание группы доступности (Transact-SQL) | Документы Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], creating
ms.assetid: 8b0a6301-8b79-4415-b608-b40876f30066
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 57a494af168a8f5572bafe93f8fb47b22a954a19
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752351"
---
# <a name="create-an-availability-group-transact-sql"></a><span data-ttu-id="42efc-102">Создание группы доступности (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="42efc-102">Create an Availability Group (Transact-SQL)</span></span>
  <span data-ttu-id="42efc-103">В данном разделе описывается использование [!INCLUDE[tsql](../../../includes/tsql-md.md)] для создания и настройки группы доступности на основе экземпляров [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] , на которых включена функция [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="42efc-103">This topic describes how to use [!INCLUDE[tsql](../../../includes/tsql-md.md)] to create and configure an availability group on instances of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] on which the [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] feature is enabled.</span></span> <span data-ttu-id="42efc-104">*Группа доступности* определяет набор пользовательских баз данных, которые будут действовать при сбое как единое целое, и набор партнеров по обеспечению отработки отказа, называемых *репликами доступности*и поддерживающих отработку отказа.</span><span class="sxs-lookup"><span data-stu-id="42efc-104">An *availability group* defines a set of user databases that will fail over as a single unit and a set of failover partners, known as *availability replicas*, that support failover.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="42efc-105">Базовые сведения о группах доступности см. в разделе [Обзор групп доступности AlwaysOn (SQL Server)](overview-of-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="42efc-105">For an introduction to availability groups, see [Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span></span>  

> [!NOTE]  
>  <span data-ttu-id="42efc-106">Вместо [!INCLUDE[tsql](../../../includes/tsql-md.md)]можно использовать мастер создания групп доступности или командлеты [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="42efc-106">As an alternative to using [!INCLUDE[tsql](../../../includes/tsql-md.md)], you can use the Create Availability Group wizard or [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell cmdlets.</span></span> <span data-ttu-id="42efc-107">Дополнительные сведения см. в разделе [Использование мастера групп доступности (среда SQL Server Management Studio)](use-the-availability-group-wizard-sql-server-management-studio.md), [Использование диалогового окна "Создание группы доступности" (среда SQL Server Management Studio)](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)или [Создание группы доступности (SQL Server PowerShell)](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="42efc-107">For more information, see [Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;](use-the-availability-group-wizard-sql-server-management-studio.md), [Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;](use-the-new-availability-group-dialog-box-sql-server-management-studio.md), or [Create an Availability Group &#40;SQL Server PowerShell&#41;](../../../powershell/sql-server-powershell.md).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="42efc-108">Перед началом</span><span class="sxs-lookup"><span data-stu-id="42efc-108">Before You Begin</span></span>  
 <span data-ttu-id="42efc-109">Настоятельно рекомендуется прочитать этот раздел, прежде чем пытаться настроить свою первую группу доступности.</span><span class="sxs-lookup"><span data-stu-id="42efc-109">We strongly recommend that you read this section before attempting to create your first availability group.</span></span>  
  
###  <a name="prerequisites-restrictions-and-recommendations"></a><a name="PrerequisitesRestrictions"></a><span data-ttu-id="42efc-110">Предварительные требования, ограничения и рекомендации</span><span class="sxs-lookup"><span data-stu-id="42efc-110">Prerequisites, Restrictions, and Recommendations</span></span>  
  
-   <span data-ttu-id="42efc-111">Перед созданием группы доступности необходимо, чтобы экземпляры [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , на которых находятся реплики доступности, были расположены на различных узлах одной отказоустойчивой кластеризации Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="42efc-111">Before creating an availability group, verify that the instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that host availability replicas reside on different Windows Server Failover Clustering (WSFC) node within the same WSFC failover cluster.</span></span> <span data-ttu-id="42efc-112">Кроме того, убедитесь, что каждый из экземпляров сервера соответствует всем другим обязательным условиям [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="42efc-112">Also, verify that each of the server instance meets all other [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] prerequisites.</span></span> <span data-ttu-id="42efc-113">Для получения дополнительных сведений настоятельно рекомендуется изучить раздел [Предварительные требования, ограничения и рекомендации для групп доступности AlwaysOn (SQL Server)](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="42efc-113">For more information, we strongly recommend that you read [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="42efc-114">безопасность</span><span class="sxs-lookup"><span data-stu-id="42efc-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="42efc-115">Permissions</span><span class="sxs-lookup"><span data-stu-id="42efc-115">Permissions</span></span>  
 <span data-ttu-id="42efc-116">Требуется членство в фиксированной роли сервера **sysadmin** и одно из разрешений: CREATE AVAILABILITY GROUP, ALTER ANY AVAILABILITY GROUP или CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="42efc-116">Requires membership in the **sysadmin** fixed server role and either CREATE AVAILABILITY GROUP server permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
###  <a name="summary-of-tasks-and-corresponding-transact-sql-statements"></a><a name="SummaryTsqlStatements"></a> <span data-ttu-id="42efc-117">Сводка задач и соответствующих инструкций Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="42efc-117">Summary of Tasks and Corresponding Transact-SQL Statements</span></span>  
 <span data-ttu-id="42efc-118">В следующей таблице перечислены основные задачи, связанные с созданием и настройкой группы доступности, а также инструкции [!INCLUDE[tsql](../../../includes/tsql-md.md)] , используемые при выполнении этих задач.</span><span class="sxs-lookup"><span data-stu-id="42efc-118">The following table lists the basic tasks involved in creating and configuring an availability group and indicates which [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements to use for these tasks.</span></span> <span data-ttu-id="42efc-119">Задачи [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] должны выполняться в той последовательности, в которой они перечислены в таблице.</span><span class="sxs-lookup"><span data-stu-id="42efc-119">The [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] tasks must be performed in the sequence in which they are presented in the table.</span></span>  
  
|<span data-ttu-id="42efc-120">Задача</span><span class="sxs-lookup"><span data-stu-id="42efc-120">Task</span></span>|<span data-ttu-id="42efc-121">Инструкции Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="42efc-121">Transact-SQL Statement(s)</span></span>|<span data-ttu-id="42efc-122">Место выполнения задачи**<sup>\*</sup>**</span><span class="sxs-lookup"><span data-stu-id="42efc-122">Where to Perform Task**<sup>\*</sup>**</span></span>|  
|----------|----------------------------------|-------------------------------------------|  
|<span data-ttu-id="42efc-123">Создание конечной точки зеркального отображения базы данных (одна точка на экземпляр [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="42efc-123">Create database mirroring endpoint (once per [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance)</span></span>|<span data-ttu-id="42efc-124">[Создать конечную точку](/sql/t-sql/statements/create-endpoint-transact-sql) *EndpointName* ... ДЛЯ DATABASE_MIRRORING</span><span class="sxs-lookup"><span data-stu-id="42efc-124">[CREATE ENDPOINT](/sql/t-sql/statements/create-endpoint-transact-sql) *endpointName* ... FOR DATABASE_MIRRORING</span></span>|<span data-ttu-id="42efc-125">Выполнить на каждом экземпляре сервера, у которого нет конечной точки зеркального отображения базы данных.</span><span class="sxs-lookup"><span data-stu-id="42efc-125">Execute on each server instance that lacks database mirroring endpoint.</span></span>|  
|<span data-ttu-id="42efc-126">Создание группы доступности</span><span class="sxs-lookup"><span data-stu-id="42efc-126">Create availability group</span></span>|[<span data-ttu-id="42efc-127">CREATE AVAILABILITY GROUP</span><span class="sxs-lookup"><span data-stu-id="42efc-127">CREATE AVAILABILITY GROUP</span></span>](/sql/t-sql/statements/create-availability-group-transact-sql)|<span data-ttu-id="42efc-128">Выполнить на экземпляре сервера, где будет размещена исходная первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="42efc-128">Execute on the server instance that is to host the initial primary replica.</span></span>|  
|<span data-ttu-id="42efc-129">Присоединить вторичную реплику к группе доступности</span><span class="sxs-lookup"><span data-stu-id="42efc-129">Join secondary replica to availability group</span></span>|<span data-ttu-id="42efc-130">[ALTER AVAILABILITY GROUP](join-a-secondary-replica-to-an-availability-group-sql-server.md) *имя_группы* JOIN</span><span class="sxs-lookup"><span data-stu-id="42efc-130">[ALTER AVAILABILITY GROUP](join-a-secondary-replica-to-an-availability-group-sql-server.md) *group_name* JOIN</span></span>|<span data-ttu-id="42efc-131">Выполнить на каждом экземпляре сервера, размещающем вторичную реплику.</span><span class="sxs-lookup"><span data-stu-id="42efc-131">Execute on each server instance that hosts a secondary replica.</span></span>|  
|<span data-ttu-id="42efc-132">Подготовьте базу данных-получатель</span><span class="sxs-lookup"><span data-stu-id="42efc-132">Prepare the secondary database</span></span>|<span data-ttu-id="42efc-133">[Резервное копирование](/sql/t-sql/statements/backup-transact-sql) и [Восстановление](/sql/t-sql/statements/restore-statements-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="42efc-133">[BACKUP](/sql/t-sql/statements/backup-transact-sql) and [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql).</span></span>|<span data-ttu-id="42efc-134">Создайте резервные копии на экземпляре сервера, размещающем первичную реплику.</span><span class="sxs-lookup"><span data-stu-id="42efc-134">Create backups on the server instance that hosts the primary replica.</span></span><br /><br /> <span data-ttu-id="42efc-135">Восстановить резервные копии на каждом экземпляре сервера, размещающем вторичную реплику, используя инструкцию RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="42efc-135">Restore backups on each server instance that hosts a secondary replica, using RESTORE WITH NORECOVERY.</span></span>|  
|<span data-ttu-id="42efc-136">Запуск синхронизации данных с помощью присоединения каждой базы данных-получателя к группе доступности</span><span class="sxs-lookup"><span data-stu-id="42efc-136">Start data synchronization by joining each secondary database to availability group</span></span>|<span data-ttu-id="42efc-137">[ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) *имя_базы_данных* SET HADR AVAILABILITY GROUP = *имя_группы*</span><span class="sxs-lookup"><span data-stu-id="42efc-137">[ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) *database_name* SET HADR AVAILABILITY GROUP = *group_name*</span></span>|<span data-ttu-id="42efc-138">Выполнить на каждом экземпляре сервера, размещающем вторичную реплику.</span><span class="sxs-lookup"><span data-stu-id="42efc-138">Execute on each server instance that hosts a secondary replica.</span></span>|  
  
 <span data-ttu-id="42efc-139">**<sup>\*</sup>** Чтобы выполнить данную задачу, подключитесь к указанному экземпляру сервера или экземпляра.</span><span class="sxs-lookup"><span data-stu-id="42efc-139">**<sup>\*</sup>**  To perform a given task, connect to the indicated server instance or instances.</span></span>  
  
##  <a name="using-transact-sql-to-create-and-configure-an-availability-group"></a><a name="TsqlProcedure"></a> <span data-ttu-id="42efc-140">Создание и настройка группы доступности с помощью Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="42efc-140">Using Transact-SQL to Create and Configure an Availability Group</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="42efc-141"> Пример настройки с образцами кода для каждой из этих инструкций [!INCLUDE[tsql](../../../includes/tsql-md.md)] см. в статье [Пример. Настройка группы доступности, использующей проверку подлинности Windows](#ExampleConfigAGWinAuth).</span><span class="sxs-lookup"><span data-stu-id="42efc-141">For a sample configuration procedure containing code examples of each these [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements, see [Example: Configuring an Availability Group that Uses Windows Authentication](#ExampleConfigAGWinAuth).</span></span>  
  
1.  <span data-ttu-id="42efc-142">Подключитесь к экземпляру сервера, на котором должна быть размещена первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="42efc-142">Connect to the server instance that is to host the primary replica.</span></span>  
  
2.  <span data-ttu-id="42efc-143">Создайте группу доступности с помощью инструкции [CREATE Availability Group](/sql/t-sql/statements/create-availability-group-transact-sql) [!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="42efc-143">Create the availability group by using the [CREATE AVAILABILITY GROUP](/sql/t-sql/statements/create-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span>  
  
3.  <span data-ttu-id="42efc-144">Присоедините новую вторичную реплику к группе доступности.</span><span class="sxs-lookup"><span data-stu-id="42efc-144">Join the new secondary replica to the availability group.</span></span> <span data-ttu-id="42efc-145">Дополнительные сведения см. в разделе [Присоединение вторичной реплики к группе доступности (SQL Server)](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="42efc-145">For more information, see [Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span></span>  
  
4.  <span data-ttu-id="42efc-146">Для каждой базы данных в группе доступности создайте базу данных-получатель путем восстановления последней резервной копии базы данных-источника с помощью инструкции RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="42efc-146">For each database in the availability group, create a secondary database by restoring recent backups of the primary database, using RESTORE WITH NORECOVERY.</span></span> <span data-ttu-id="42efc-147">Дополнительные сведения см. в разделе [Пример. Настройка группы доступности с использованием проверки подлинности Windows (Transact-SQL)](create-an-availability-group-transact-sql.md), начиная с шага восстановления резервной копии базы данных.</span><span class="sxs-lookup"><span data-stu-id="42efc-147">For more information, see [Example: Setting Up an Availability Group Using Windows Authentication (Transact-SQL)](create-an-availability-group-transact-sql.md), starting with the step that restores the database backup.</span></span>  
  
5.  <span data-ttu-id="42efc-148">Присоедините каждую новую базу данных-получатель к группе доступности.</span><span class="sxs-lookup"><span data-stu-id="42efc-148">Join every new secondary database to the availability group.</span></span> <span data-ttu-id="42efc-149">Дополнительные сведения см. в разделе [Присоединение вторичной реплики к группе доступности (SQL Server)](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="42efc-149">For more information, see [Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span></span>  
  
##  <a name="example-configuring-an-availability-group-that-uses-windows-authentication"></a><a name="ExampleConfigAGWinAuth"></a> <span data-ttu-id="42efc-150">Пример. Настройка группы доступности, использующей проверку подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="42efc-150">Example: Configuring an Availability Group that Uses Windows Authentication</span></span>  
 <span data-ttu-id="42efc-151">В этом примере создается образец процедуры настройки [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] , где [!INCLUDE[tsql](../../../includes/tsql-md.md)] используется для настройки конечных точек зеркального отображения базы данных, использующих проверку подлинности Windows для создания и настройки группы доступности и ее баз данных-получателей.</span><span class="sxs-lookup"><span data-stu-id="42efc-151">This example creates a sample [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] configuration procedure that uses [!INCLUDE[tsql](../../../includes/tsql-md.md)] to set up database mirroring endpoints that use Windows Authentication and to create and configure an availability group and its secondary databases.</span></span>  
  
 <span data-ttu-id="42efc-152">Этот пример содержит следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="42efc-152">This example contains the following sections:</span></span>  
  
-   [<span data-ttu-id="42efc-153">Предварительные требования для использования процедуры настройки примера</span><span class="sxs-lookup"><span data-stu-id="42efc-153">Prerequisites for Using the Sample Configuration Procedure</span></span>](#PrerequisitesForExample)  
  
-   [<span data-ttu-id="42efc-154">Образец процедуры настройки</span><span class="sxs-lookup"><span data-stu-id="42efc-154">Sample Configuration Procedure</span></span>](#SampleProcedure)  
  
-   [<span data-ttu-id="42efc-155">Выполните пример кода для процедуры настройки образца</span><span class="sxs-lookup"><span data-stu-id="42efc-155">Complete Code Example for Sample Configuration Procedure</span></span>](#CompleteCodeExample)  
  
###  <a name="prerequisites-for-using-the-sample-configuration-procedure"></a><a name="PrerequisitesForExample"></a> <span data-ttu-id="42efc-156">Предварительные требования для использования процедуры настройки образца</span><span class="sxs-lookup"><span data-stu-id="42efc-156">Prerequisites for Using the Sample Configuration Procedure</span></span>  
 <span data-ttu-id="42efc-157">Этот образец процедуры имеет следующие требования.</span><span class="sxs-lookup"><span data-stu-id="42efc-157">This sample procedure has the following requirements:</span></span>  
  
-   <span data-ttu-id="42efc-158">Экземпляры сервера должны поддерживать [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="42efc-158">The server instances must support [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span></span> <span data-ttu-id="42efc-159">Дополнительные сведения см. в разделе [Предварительные требования, ограничения и рекомендации для групп доступности AlwaysOn (SQL Server)](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="42efc-159">For more information, see [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
-   <span data-ttu-id="42efc-160">Оба образца баз данных, *MyDb1* и *MyDb2*, должны существовать на экземпляре сервера, где будет размещаться первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="42efc-160">Two sample databases, *MyDb1* and *MyDb2*, must exist on the server instance that will host the primary replica.</span></span> <span data-ttu-id="42efc-161">В следующем примере кода создаются и настраиваются эти две базы данных и создается полная резервная копия каждой из них.</span><span class="sxs-lookup"><span data-stu-id="42efc-161">The following code examples create and configure these two databases and create a full backup of each.</span></span> <span data-ttu-id="42efc-162">Выполните эти примеры кода на экземпляре сервера, где планируется создавать образец группы доступности.</span><span class="sxs-lookup"><span data-stu-id="42efc-162">Execute these code examples on the server instance on which you intend to create the sample availability group.</span></span> <span data-ttu-id="42efc-163">На этом экземпляре сервера будет размещаться первоначальная первичная реплика образца группы доступности.</span><span class="sxs-lookup"><span data-stu-id="42efc-163">This server instance will host the initial primary replica of the sample availability group.</span></span>  
  
    1.  <span data-ttu-id="42efc-164">В следующем примере [!INCLUDE[tsql](../../../includes/tsql-md.md)] эти базы данных создаются и переключаются на модель полного восстановления:</span><span class="sxs-lookup"><span data-stu-id="42efc-164">The following [!INCLUDE[tsql](../../../includes/tsql-md.md)] example creates these databases and alters them to use the full recovery model:</span></span>  
  
        ```sql
        -- Create sample databases:  
        CREATE DATABASE MyDb1;  
        GO  
        ALTER DATABASE MyDb1 SET RECOVERY FULL;  
        GO  
  
        CREATE DATABASE MyDb2;  
        GO  
        ALTER DATABASE MyDb2 SET RECOVERY FULL;  
        GO  
        ```  
  
    2.  <span data-ttu-id="42efc-165">В следующем примере кода создается полная резервная копия баз данных *MyDb1* и *MyDb2*.</span><span class="sxs-lookup"><span data-stu-id="42efc-165">The following code example creates a full database backup of *MyDb1* and *MyDb2*.</span></span> <span data-ttu-id="42efc-166">В этом примере кода используется вымышленная общая папка резервных копий, \\ \\ *файлового сервера* \\ *SQLbackups*.</span><span class="sxs-lookup"><span data-stu-id="42efc-166">This code example uses a fictional backup share, \\\\*FILESERVER*\\*SQLbackups*.</span></span>  
  
        ```sql
        -- Backup sample databases:  
        BACKUP DATABASE MyDb1   
        TO DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
            WITH FORMAT  
        GO  
  
        BACKUP DATABASE MyDb2   
        TO DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
            WITH FORMAT  
        GO
        ```  
  
###  <a name="sample-configuration-procedure"></a><a name="SampleProcedure"></a> <span data-ttu-id="42efc-167">Образец процедуры настройки</span><span class="sxs-lookup"><span data-stu-id="42efc-167">Sample Configuration Procedure</span></span>  
 <span data-ttu-id="42efc-168">В этом образце настройки реплика доступности будет создана на двух изолированных экземплярах сервера, у которых учетные записи служб выполняются в разных доверенных доменах (`DOMAIN1` и `DOMAIN2`).</span><span class="sxs-lookup"><span data-stu-id="42efc-168">In this sample configuration, the availability replica will be created on two stand-alone server instances whose service accounts run under different, but trusted, domains (`DOMAIN1` and `DOMAIN2`).</span></span>  
  
 <span data-ttu-id="42efc-169">В следующей таблице приведена сводка по значениям, использованным в этом образце конфигурации.</span><span class="sxs-lookup"><span data-stu-id="42efc-169">The following table summarizes the values used in this sample configuration.</span></span>  
  
|<span data-ttu-id="42efc-170">Первоначальная роль</span><span class="sxs-lookup"><span data-stu-id="42efc-170">Initial role</span></span>|<span data-ttu-id="42efc-171">Система</span><span class="sxs-lookup"><span data-stu-id="42efc-171">System</span></span>|<span data-ttu-id="42efc-172">Узловой экземпляр [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42efc-172">Host [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Instance</span></span>|  
|------------------|------------|---------------------------------------------|  
|<span data-ttu-id="42efc-173">Первичная</span><span class="sxs-lookup"><span data-stu-id="42efc-173">Primary</span></span>|`COMPUTER01`|`AgHostInstance`|  
|<span data-ttu-id="42efc-174">Вторичная</span><span class="sxs-lookup"><span data-stu-id="42efc-174">Secondary</span></span>|`COMPUTER02`|<span data-ttu-id="42efc-175">Экземпляр по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="42efc-175">Default instance.</span></span>|  
  
1.  <span data-ttu-id="42efc-176">Создайте конечную точку зеркального отображения базы данных с именем *dbm_endpoint* в экземпляре сервера, где планируется создать группу доступности (это экземпляр с именем `AgHostInstance` на компьютере `COMPUTER01`).</span><span class="sxs-lookup"><span data-stu-id="42efc-176">Create a database mirroring endpoint named *dbm_endpoint* on the server instance on which you plan to create the availability group (this is an instance named `AgHostInstance` on `COMPUTER01`).</span></span> <span data-ttu-id="42efc-177">Эта конечная точка использует порт 7022.</span><span class="sxs-lookup"><span data-stu-id="42efc-177">This endpoint uses port 7022.</span></span> <span data-ttu-id="42efc-178">Обратите внимание, что на экземпляре сервера, где создается группа доступности, будет размещаться первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="42efc-178">Note that the server instance on which you create the availability group will host the primary replica.</span></span>  
  
    ```sql
    -- Create endpoint on server instance that hosts the primary replica:  
    CREATE ENDPOINT dbm_endpoint  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=7022)   
        FOR DATABASE_MIRRORING (ROLE=ALL)  
    GO
    ```  
  
2.  <span data-ttu-id="42efc-179">Создайте конечную точку *dbm_endpoint* в экземпляре сервера, где будет размещаться вторичная реплика (это экземпляр сервера по умолчанию на компьютере `COMPUTER02`).</span><span class="sxs-lookup"><span data-stu-id="42efc-179">Create an endpoint *dbm_endpoint* on the server instance that will host the secondary replica (this is the default server instance on `COMPUTER02`).</span></span> <span data-ttu-id="42efc-180">Эта конечная точка использует порт 5022.</span><span class="sxs-lookup"><span data-stu-id="42efc-180">This endpoint uses port 5022.</span></span>  
  
    ```sql
    -- Create endpoint on server instance that hosts the secondary replica:   
    CREATE ENDPOINT dbm_endpoint  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=5022)   
        FOR DATABASE_MIRRORING (ROLE=ALL)  
    GO
    ```  
  
3.  > [!NOTE]  
    >  <span data-ttu-id="42efc-181">Если учетные записи служб на экземплярах серверов, где планируется размещать реплики доступности, выполняются под одной учетной записью домена, этот шаг выполнять не нужно.</span><span class="sxs-lookup"><span data-stu-id="42efc-181">If the service accounts of the server instances that are to host your availability replicas run under the same domain account this step is unnecessary.</span></span> <span data-ttu-id="42efc-182">Пропустите его и перейдите к следующему шагу.</span><span class="sxs-lookup"><span data-stu-id="42efc-182">Skip it and go directly to the next step.</span></span>  
  
     <span data-ttu-id="42efc-183">Если учетные записи служб на экземплярах серверов работают под разными пользователями домена, создайте на каждом экземпляре сервера имя входа для другого экземпляра сервера и предоставьте этому имени входа разрешение на доступ к конечной точке зеркального отображения локальной базы данных.</span><span class="sxs-lookup"><span data-stu-id="42efc-183">If the service accounts of the server instances run under different domain users, on each server instance, create a login for the other server instance and grant this login permission to access the local database mirroring endpoint.</span></span>  
  
     <span data-ttu-id="42efc-184">В следующем примере кода приведены инструкции [!INCLUDE[tsql](../../../includes/tsql-md.md)] для создания имени входа и предоставления ему разрешения для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="42efc-184">The following code example shows the [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements for creating a login and granting it permission on an endpoint.</span></span> <span data-ttu-id="42efc-185">Учетная запись домена на удаленном экземпляре сервера представлена здесь как *имя_домена*\\*имя_пользователя*.</span><span class="sxs-lookup"><span data-stu-id="42efc-185">The domain account of the remote server instance is represented here as *domain_name*\\*user_name*.</span></span>  
  
    ```sql
    -- If necessary, create a login for the service account, domain_name\user_name  
    -- of the server instance that will host the other replica:  
    USE master;  
    GO  
    CREATE LOGIN [domain_name\user_name] FROM WINDOWS;  
    GO  
    -- And Grant this login connect permissions on the endpoint:  
    GRANT CONNECT ON ENDPOINT::dbm_endpoint   
       TO [domain_name\user_name];  
    GO  
    ```  
  
4.  <span data-ttu-id="42efc-186">На экземпляре сервера, размещающем пользовательские базы данных, создайте группу доступности.</span><span class="sxs-lookup"><span data-stu-id="42efc-186">On the server instance where the user databases reside, create the availability group.</span></span>  
  
     <span data-ttu-id="42efc-187">В следующем примере кода создается группа доступности с именем *MyAG* на экземпляре сервера, на котором были созданы образцы баз данных *MyDb1* и *MyDb2*.</span><span class="sxs-lookup"><span data-stu-id="42efc-187">The following code example creates an availability group named *MyAG* on the server instance on which the sample databases, *MyDb1* and *MyDb2*, were created.</span></span> <span data-ttu-id="42efc-188">Сначала указывается локальный экземпляр сервера, `AgHostInstance`, размещенный на компьютере *COMPUTER01* .</span><span class="sxs-lookup"><span data-stu-id="42efc-188">The local server instance, `AgHostInstance`, on *COMPUTER01* is specified first.</span></span> <span data-ttu-id="42efc-189">На этом экземпляре сервера будет размещаться первоначальная первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="42efc-189">This instance will host the initial primary replica.</span></span> <span data-ttu-id="42efc-190">Указано, что на удаленном экземпляре сервера, являющемся экземпляром сервера по умолчанию, размещенном на компьютере *COMPUTER02*, размещена вторичная реплика.</span><span class="sxs-lookup"><span data-stu-id="42efc-190">A remote server instance, the default server instance on *COMPUTER02*, is specified to host a secondary replica.</span></span> <span data-ttu-id="42efc-191">Обе реплики доступности настроены для использования асинхронного режима фиксации с переходом на другой ресурс вручную (для реплик с асинхронной фиксацией переход на другой ресурс вручную означает принудительное переключение с возможной потерей данных).</span><span class="sxs-lookup"><span data-stu-id="42efc-191">Both availability replica are configured to use asynchronous-commit mode with manual failover (for asynchronous-commit replicas manual failover means  forced failover with possible data loss).</span></span>  
  
    ```sql
    -- Create the availability group, MyAG:   
    CREATE AVAILABILITY GROUP MyAG   
       FOR   
          DATABASE MyDB1, MyDB2   
       REPLICA ON   
          'COMPUTER01\AgHostInstance' WITH   
             (  
             ENDPOINT_URL = 'TCP://COMPUTER01.Adventure-Works.com:7022',   
             AVAILABILITY_MODE = ASYNCHRONOUS_COMMIT,  
             FAILOVER_MODE = MANUAL  
             ),  
          'COMPUTER02' WITH   
             (  
             ENDPOINT_URL = 'TCP://COMPUTER02.Adventure-Works.com:5022',  
             AVAILABILITY_MODE = ASYNCHRONOUS_COMMIT,  
             FAILOVER_MODE = MANUAL  
             );   
    GO  
    ```  
  
     <span data-ttu-id="42efc-192">Дополнительные примеры кода [!INCLUDE[tsql](../../../includes/tsql-md.md)], предназначенного для создания группы доступности, см. в разделе [CREATE AVAILABILITY GROUP (Transact-SQL)](/sql/t-sql/statements/create-availability-group-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="42efc-192">For additional [!INCLUDE[tsql](../../../includes/tsql-md.md)] code examples of creating an availability group, see [CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql).</span></span>  
  
5.  <span data-ttu-id="42efc-193">На экземпляре сервера, размещающем вторичную реплику, присоедините ее к группе доступности.</span><span class="sxs-lookup"><span data-stu-id="42efc-193">On the server instance that hosts the secondary replica, join the secondary replica to the availability group.</span></span>  
  
     <span data-ttu-id="42efc-194">В следующем примере кода вторичная реплика на компьютере `COMPUTER02` присоединяется к группе доступности `MyAG` .</span><span class="sxs-lookup"><span data-stu-id="42efc-194">The following code example joins the secondary replica on `COMPUTER02` to the `MyAG` availability group.</span></span>  
  
    ```sql
    -- On the server instance that hosts the secondary replica,   
    -- join the secondary replica to the availability group:  
    ALTER AVAILABILITY GROUP MyAG JOIN;  
    GO  
    ```  
  
6.  <span data-ttu-id="42efc-195">На экземпляре сервера, размещающем вторичную реплику, создайте базы данных-получатели.</span><span class="sxs-lookup"><span data-stu-id="42efc-195">On the server instance that hosts the secondary replica, create the secondary databases.</span></span>  
  
     <span data-ttu-id="42efc-196">В следующем примере кода создаются базы данных-получатели *MyDb1* и *MyDb2* путем восстановления резервных копий с помощью инструкции RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="42efc-196">The following code example creates the *MyDb1* and *MyDb2* secondary databases by restoring database backups using RESTORE WITH NORECOVERY.</span></span>  
  
    ```sql
    -- On the server instance that hosts the secondary replica,   
    -- Restore database backups using the WITH NORECOVERY option:  
    RESTORE DATABASE MyDb1   
        FROM DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
        WITH NORECOVERY  
    GO  
  
    RESTORE DATABASE MyDb2   
        FROM DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
        WITH NORECOVERY  
    GO
    ```  
  
7.  <span data-ttu-id="42efc-197">На экземпляре сервера, размещающем первичную реплику, создайте резервную копию журнала транзакций каждой из баз данных-источников.</span><span class="sxs-lookup"><span data-stu-id="42efc-197">On the server instance that hosts the primary replica, back up the transaction log on each of the primary databases.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="42efc-198">При настройке реальной группы доступности рекомендуется перед созданием такой резервной копии журнала приостановить задачи резервного копирования журнала для баз данных-источников до тех пор, пока к группе доступности не будут присоединены соответствующие базы данных-получатели.</span><span class="sxs-lookup"><span data-stu-id="42efc-198">When you are configuring a real availability group, we recommend that, before taking this log backup, you suspend log backup tasks for your primary databases until you have joined the corresponding secondary databases to the availability group.</span></span>  
  
     <span data-ttu-id="42efc-199">В следующем примере кода создается резервная копия журнала транзакций для баз данных MyDb1 и MyDb2.</span><span class="sxs-lookup"><span data-stu-id="42efc-199">The following code example creates a transaction log backup on MyDb1 and on MyDb2.</span></span>  
  
    ```sql
    -- On the server instance that hosts the primary replica,   
    -- Backup the transaction log on each primary database:  
    BACKUP LOG MyDb1   
    TO DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
        WITH NOFORMAT  
    GO  
  
    BACKUP LOG MyDb2   
    TO DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
        WITHNOFORMAT  
    GO
    ```  
  
    > [!TIP]  
    >  <span data-ttu-id="42efc-200">Как правило, резервная копия журнала должна создаваться для каждой базы данных-источника а затем восстанавливаться в соответствующей базе данных-получателе (с помощью инструкции WITH NORECOVERY).</span><span class="sxs-lookup"><span data-stu-id="42efc-200">Typically, a log backup must be taken on each primary database and then restored on the corresponding secondary database (using WITH NORECOVERY).</span></span> <span data-ttu-id="42efc-201">Однако в этой резервной копии журнала может не быть необходимости, если база данных только что создана и резервной копии журнала еще нет либо модель восстановления только что сменили с SIMPLE на FULL.</span><span class="sxs-lookup"><span data-stu-id="42efc-201">However, this log backup might be unnecessary if the database has just been created and no log backup has been taken yet or the recovery model has just been changed from SIMPLE to FULL.</span></span>  
  
8.  <span data-ttu-id="42efc-202">На экземпляре сервера, размещающем вторичную реплику, примените резервные копии журналов к базам данных-получателям.</span><span class="sxs-lookup"><span data-stu-id="42efc-202">On the server instance that hosts the secondary replica, apply log backups to the secondary databases.</span></span>  
  
     <span data-ttu-id="42efc-203">В следующем примере кода показано применение резервных копий к базам данных-получателям *MyDb1* и *MyDb2* путем восстановления резервных копий с помощью инструкции RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="42efc-203">The following code example applies backups to *MyDb1* and *MyDb2* secondary databases by restoring database backups using RESTORE WITH NORECOVERY.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="42efc-204">При подготовке производственной базы данных-получателя следует применить все резервные копии журналов, созданные после резервного копирования базы данных, из которой была создана база данных-получатель, начиная с самой ранней, обязательно с помощью инструкции RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="42efc-204">When you are preparing a real secondary database, you need to apply every log backup taken since the database backup from which you created the secondary database, starting with the earliest and always using RESTORE WITH NORECOVERY.</span></span> <span data-ttu-id="42efc-205">Естественно, при восстановлении как полной, так и разностной резервной копии потребуется применить резервные копии журналов, созданные только после разностного резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="42efc-205">Of course, if you restore both full and differential database backups, you would only need to apply the log backups taken after the differential backup.</span></span>  
  
    ```sql
    -- Restore the transaction log on each secondary database,  
    -- using the WITH NORECOVERY option:  
    RESTORE LOG MyDb1   
        FROM DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
        WITH FILE=1, NORECOVERY  
    GO  
    RESTORE LOG MyDb2   
        FROM DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
        WITH FILE=1, NORECOVERY  
    GO  
    ```  
  
9. <span data-ttu-id="42efc-206">На экземпляре сервера, размещающем вторичную реплику, присоедините новую базу данных-получателя к группе доступности.</span><span class="sxs-lookup"><span data-stu-id="42efc-206">On the server instance that hosts the secondary replica, join the new secondary databases to the availability group.</span></span>  
  
     <span data-ttu-id="42efc-207">В следующем примере кода к группе доступности *MyDb1* присоединяется база данных-получатель *MyDb2* , а затем база данных-получатель *MyAG* .</span><span class="sxs-lookup"><span data-stu-id="42efc-207">The following code example, joins the *MyDb1* secondary database and then the *MyDb2* secondary databases to the *MyAG* availability group.</span></span>  
  
    ```sql
    -- On the server instance that hosts the secondary replica,   
    -- join each secondary database to the availability group:  
    ALTER DATABASE MyDb1 SET HADR AVAILABILITY GROUP = MyAG;  
    GO  
  
    ALTER DATABASE MyDb2 SET HADR AVAILABILITY GROUP = MyAG;  
    GO
    ```  
  
###  <a name="complete-code-example-for-sample-configuration-procedure"></a><a name="CompleteCodeExample"></a> <span data-ttu-id="42efc-208">Выполните пример кода для процедуры настройки образца</span><span class="sxs-lookup"><span data-stu-id="42efc-208">Complete Code Example for Sample Configuration Procedure</span></span>  
 <span data-ttu-id="42efc-209">Следующий пример кода объединяет в себе примеры кода из всех шагов с образцом процедуры настройки.</span><span class="sxs-lookup"><span data-stu-id="42efc-209">The following example merges the code examples from all the steps of the sample configuration procedure.</span></span> <span data-ttu-id="42efc-210">В следующей таблице приведена сводка значений заполнителей, использованных в этом примере кода.</span><span class="sxs-lookup"><span data-stu-id="42efc-210">The following table summarized the placeholder values used in this code example.</span></span> <span data-ttu-id="42efc-211">Дополнительные сведения о шагах в этом примере кода см. в подразделах [Предварительные требования для использования процедуры настройки образца](#PrerequisitesForExample) и [Образец процедуры настройки](#SampleProcedure)выше в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="42efc-211">For more information about the steps in this code example, see [Prerequisites for Using the Sample Configuration Procedure](#PrerequisitesForExample) and [Sample Configuration Procedure](#SampleProcedure), earlier in this topic.</span></span>  
  
|<span data-ttu-id="42efc-212">Заполнитель</span><span class="sxs-lookup"><span data-stu-id="42efc-212">Placeholder</span></span>|<span data-ttu-id="42efc-213">Описание</span><span class="sxs-lookup"><span data-stu-id="42efc-213">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="42efc-214">\\\\*FILESERVER*\\*SQLbackups*</span><span class="sxs-lookup"><span data-stu-id="42efc-214">\\\\*FILESERVER*\\*SQLbackups*</span></span>|<span data-ttu-id="42efc-215">Вымышленная общая папка резервных копий.</span><span class="sxs-lookup"><span data-stu-id="42efc-215">Fictional backup share.</span></span>|  
|<span data-ttu-id="42efc-216">\\\\*FILESERVER*\\*SQLbackups\MyDb1.bak*</span><span class="sxs-lookup"><span data-stu-id="42efc-216">\\\\*FILESERVER*\\*SQLbackups\MyDb1.bak*</span></span>|<span data-ttu-id="42efc-217">Файл резервной копии для базы данных MyDb1.</span><span class="sxs-lookup"><span data-stu-id="42efc-217">Backup file for MyDb1.</span></span>|  
|<span data-ttu-id="42efc-218">\\\\*FILESERVER*\\*SQLbackups\MyDb2.bak*</span><span class="sxs-lookup"><span data-stu-id="42efc-218">\\\\*FILESERVER*\\*SQLbackups\MyDb2.bak*</span></span>|<span data-ttu-id="42efc-219">Файл резервной копии для базы данных MyDb2.</span><span class="sxs-lookup"><span data-stu-id="42efc-219">Backup file for MyDb2.</span></span>|  
|<span data-ttu-id="42efc-220">*7022*</span><span class="sxs-lookup"><span data-stu-id="42efc-220">*7022*</span></span>|<span data-ttu-id="42efc-221">Номер порта, присвоенный каждой конечной точке зеркального отображения базы данных.</span><span class="sxs-lookup"><span data-stu-id="42efc-221">Port number assigned to each database mirroring endpoint.</span></span>|  
|<span data-ttu-id="42efc-222">*COMPUTER01\AgHostInstance*</span><span class="sxs-lookup"><span data-stu-id="42efc-222">*COMPUTER01\AgHostInstance*</span></span>|<span data-ttu-id="42efc-223">Экземпляр сервера, на котором размещается первоначальная первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="42efc-223">Server instance that hosts the initial primary replica.</span></span>|  
|<span data-ttu-id="42efc-224">*COMPUTER02*</span><span class="sxs-lookup"><span data-stu-id="42efc-224">*COMPUTER02*</span></span>|<span data-ttu-id="42efc-225">Экземпляр сервера, на котором размещается первоначальная вторичная реплика.</span><span class="sxs-lookup"><span data-stu-id="42efc-225">Server instance that hosts the initial secondary replica.</span></span> <span data-ttu-id="42efc-226">Это экземпляр сервера по умолчанию на компьютере `COMPUTER02`.</span><span class="sxs-lookup"><span data-stu-id="42efc-226">This is the default server instance on `COMPUTER02`.</span></span>|  
|<span data-ttu-id="42efc-227">*dbm_endpoint*</span><span class="sxs-lookup"><span data-stu-id="42efc-227">*dbm_endpoint*</span></span>|<span data-ttu-id="42efc-228">Имя, заданное для каждой конечной точки зеркального отображения базы данных.</span><span class="sxs-lookup"><span data-stu-id="42efc-228">Name specified for each database mirroring endpoint.</span></span>|  
|<span data-ttu-id="42efc-229">*MyAG*</span><span class="sxs-lookup"><span data-stu-id="42efc-229">*MyAG*</span></span>|<span data-ttu-id="42efc-230">Имя образца группы доступности.</span><span class="sxs-lookup"><span data-stu-id="42efc-230">Name of sample availability group.</span></span>|  
|<span data-ttu-id="42efc-231">*MyDb1*</span><span class="sxs-lookup"><span data-stu-id="42efc-231">*MyDb1*</span></span>|<span data-ttu-id="42efc-232">Имя первого образца базы данных.</span><span class="sxs-lookup"><span data-stu-id="42efc-232">Name of first sample database.</span></span>|  
|<span data-ttu-id="42efc-233">*MyDb2*</span><span class="sxs-lookup"><span data-stu-id="42efc-233">*MyDb2*</span></span>|<span data-ttu-id="42efc-234">Имя второго образца базы данных.</span><span class="sxs-lookup"><span data-stu-id="42efc-234">Name of second sample database.</span></span>|  
|<span data-ttu-id="42efc-235">*Домен1\пользователь1*</span><span class="sxs-lookup"><span data-stu-id="42efc-235">*DOMAIN1\user1*</span></span>|<span data-ttu-id="42efc-236">Учетная запись службы экземпляра сервера, на котором планируется размещать первоначальную основную реплику.</span><span class="sxs-lookup"><span data-stu-id="42efc-236">Service account of the server instance that is to host the initial primary replica.</span></span>|  
|<span data-ttu-id="42efc-237">*Домен2\пользователь2*</span><span class="sxs-lookup"><span data-stu-id="42efc-237">*DOMAIN2\user2*</span></span>|<span data-ttu-id="42efc-238">Учетная запись службы экземпляра сервера, на котором планируется размещать первоначальную вторичную реплику.</span><span class="sxs-lookup"><span data-stu-id="42efc-238">Service account of the server instance that is to host the initial secondary replica.</span></span>|  
|<span data-ttu-id="42efc-239">TCP://*COMPUTER01.Adventure-Works.com*:*7022*</span><span class="sxs-lookup"><span data-stu-id="42efc-239">TCP://*COMPUTER01.Adventure-Works.com*:*7022*</span></span>|<span data-ttu-id="42efc-240">URL-адрес конечной точки экземпляра AgHostInstance сервера [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] на компьютере COMPUTER01.</span><span class="sxs-lookup"><span data-stu-id="42efc-240">Endpoint URL of the AgHostInstance instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on COMPUTER01.</span></span>|  
|<span data-ttu-id="42efc-241">TCP://*COMPUTER02.Adventure-Works.com*:*5022*</span><span class="sxs-lookup"><span data-stu-id="42efc-241">TCP://*COMPUTER02.Adventure-Works.com*:*5022*</span></span>|<span data-ttu-id="42efc-242">URL-адрес конечной точки экземпляра сервера [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] по умолчанию на компьютере COMPUTER02.</span><span class="sxs-lookup"><span data-stu-id="42efc-242">Endpoint URL of the default instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on COMPUTER02.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="42efc-243">Дополнительные примеры кода [!INCLUDE[tsql](../../../includes/tsql-md.md)], предназначенного для создания группы доступности, см. в разделе [CREATE AVAILABILITY GROUP (Transact-SQL)](/sql/t-sql/statements/create-availability-group-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="42efc-243">For additional [!INCLUDE[tsql](../../../includes/tsql-md.md)] code examples of creating an availability group, see [CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql).</span></span>  
  
```sql
-- on the server instance that will host the primary replica,   
-- create sample databases:  
CREATE DATABASE MyDb1;  
GO  
ALTER DATABASE MyDb1 SET RECOVERY FULL;  
GO  
  
CREATE DATABASE MyDb2;  
GO  
ALTER DATABASE MyDb2 SET RECOVERY FULL;  
GO  
  
-- Backup sample databases:  
BACKUP DATABASE MyDb1   
TO DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
    WITH FORMAT  
GO  
  
BACKUP DATABASE MyDb2   
TO DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
    WITH FORMAT  
GO  
  
-- Create the endpoint on the server instance that will host the primary replica:  
CREATE ENDPOINT dbm_endpoint  
    STATE=STARTED   
    AS TCP (LISTENER_PORT=7022)   
    FOR DATABASE_MIRRORING (ROLE=ALL)  
GO  
  
-- Create the endpoint on the server instance that will host the secondary replica:   
CREATE ENDPOINT dbm_endpoint  
    STATE=STARTED   
    AS TCP (LISTENER_PORT=7022)   
    FOR DATABASE_MIRRORING (ROLE=ALL)  
GO  
  
-- If both service accounts run under the same domain account, skip this step. Otherwise,   
-- On the server instance that will host the primary replica,   
-- create a login for the service account   
-- of the server instance that will host the secondary replica, DOMAIN2\user2,   
-- and grant this login connect permissions on the endpoint:  
USE master;  
GO  
CREATE LOGIN [DOMAIN2\user2] FROM WINDOWS;  
GO  
GRANT CONNECT ON ENDPOINT::dbm_endpoint   
   TO [DOMAIN2\user2];  
GO  
  
-- If both service accounts run under the same domain account, skip this step. Otherwise,   
-- On the server instance that will host the secondary replica,  
-- create a login for the service account   
-- of the server instance that will host the primary replica, DOMAIN1\user1,   
-- and grant this login connect permissions on the endpoint:  
USE master;  
GO  
  
CREATE LOGIN [DOMAIN1\user1] FROM WINDOWS;  
GO  
GRANT CONNECT ON ENDPOINT::dbm_endpoint   
   TO [DOMAIN1\user1];  
GO  
  
-- On the server instance that will host the primary replica,   
-- create the availability group, MyAG:  
CREATE AVAILABILITY GROUP MyAG   
   FOR   
      DATABASE MyDB1, MyDB2   
   REPLICA ON   
      'COMPUTER01\AgHostInstance' WITH   
         (  
         ENDPOINT_URL = 'TCP://COMPUTER01.Adventure-Works.com:7022',  
         AVAILABILITY_MODE = SYNCHRONOUS_COMMIT,  
         FAILOVER_MODE = AUTOMATIC  
         ),  
      'COMPUTER02' WITH   
         (  
         ENDPOINT_URL = 'TCP://COMPUTER02.Adventure-Works.com:7022',  
         AVAILABILITY_MODE = SYNCHRONOUS_COMMIT,  
         FAILOVER_MODE = AUTOMATIC  
         );   
GO  
  
-- On the server instance that hosts the secondary replica,   
-- join the secondary replica to the availability group:  
ALTER AVAILABILITY GROUP MyAG JOIN;  
GO  
  
-- Restore database backups onto this server instance, using RESTORE WITH NORECOVERY:  
RESTORE DATABASE MyDb1   
    FROM DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
    WITH NORECOVERY  
GO  
  
RESTORE DATABASE MyDb2   
    FROM DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
    WITH NORECOVERY  
GO  
  
-- Back up the transaction log on each primary database:  
BACKUP LOG MyDb1   
TO DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
    WITH NOFORMAT  
GO  
  
BACKUP LOG MyDb2   
TO DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
    WITHNOFORMAT  
GO  
  
-- Restore the transaction log on each secondary database,  
-- using the WITH NORECOVERY option:  
RESTORE LOG MyDb1   
    FROM DISK = N'\\FILESERVER\SQLbackups\MyDb1.bak'   
    WITH FILE=1, NORECOVERY  
GO  
RESTORE LOG MyDb2   
    FROM DISK = N'\\FILESERVER\SQLbackups\MyDb2.bak'   
    WITH FILE=1, NORECOVERY  
GO  
  
-- On the server instance that hosts the secondary replica,   
-- join each secondary database to the availability group:  
ALTER DATABASE MyDb1 SET HADR AVAILABILITY GROUP = MyAG;  
GO  
  
ALTER DATABASE MyDb2 SET HADR AVAILABILITY GROUP = MyAG;  
GO
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="42efc-244">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="42efc-244">Related Tasks</span></span>  
 <span data-ttu-id="42efc-245">**Настройка свойств группы доступности и реплики**</span><span class="sxs-lookup"><span data-stu-id="42efc-245">**To configure availability group and replica properties**</span></span>  
  
-   [<span data-ttu-id="42efc-246">Смена режима доступности для реплики доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="42efc-246">Change the Availability Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-availability-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="42efc-247">Смена режима отработки отказа для реплики доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="42efc-247">Change the Failover Mode of an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-failover-mode-of-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="42efc-248">Создание или настройка прослушивателя группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="42efc-248">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="42efc-249">Настройка гибкой политики отработки отказа для обеспечения контроля над автоматическим переходом на другой ресурс (группы доступности AlwaysOn)</span><span class="sxs-lookup"><span data-stu-id="42efc-249">Configure the Flexible Failover Policy to Control Conditions for Automatic Failover (AlwaysOn Availability Groups)</span></span>](configure-flexible-automatic-failover-policy.md)  
  
-   [<span data-ttu-id="42efc-250">Укажите URL-адрес конечной точки при добавлении или изменении реплики доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="42efc-250">Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;</span></span>](specify-endpoint-url-adding-or-modifying-availability-replica.md)  
  
-   [<span data-ttu-id="42efc-251">Настройка резервного копирования в репликах доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="42efc-251">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
-   [<span data-ttu-id="42efc-252">Настройка доступа только для чтения в реплике доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="42efc-252">Configure Read-Only Access on an Availability Replica &#40;SQL Server&#41;</span></span>](configure-read-only-access-on-an-availability-replica-sql-server.md)  
  
-   [<span data-ttu-id="42efc-253">Настройка маршрутизации только для чтения в группе доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="42efc-253">Configure Read-Only Routing for an Availability Group &#40;SQL Server&#41;</span></span>](configure-read-only-routing-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="42efc-254">Изменение периода ожидания сеанса для реплики доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="42efc-254">Change the Session-Timeout Period for an Availability Replica &#40;SQL Server&#41;</span></span>](change-the-session-timeout-period-for-an-availability-replica-sql-server.md)  
  
 <span data-ttu-id="42efc-255">**Завершение настройки группы доступности**</span><span class="sxs-lookup"><span data-stu-id="42efc-255">**To complete availability group configuration**</span></span>  
  
-   [<span data-ttu-id="42efc-256">Присоединение вторичной реплики к группе доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="42efc-256">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="42efc-257">Подготовка базы данных-получателя для присоединения к группе доступности вручную (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="42efc-257">Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;</span></span>](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="42efc-258">Присоединение базы данных-получателя к группе доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="42efc-258">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="42efc-259">Создание или настройка прослушивателя группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="42efc-259">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
 <span data-ttu-id="42efc-260">**Другие способы создания группы доступности**</span><span class="sxs-lookup"><span data-stu-id="42efc-260">**Alternative ways to create an availability group**</span></span>  
  
-   [<span data-ttu-id="42efc-261">Использование мастера групп доступности (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="42efc-261">Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="42efc-262">Использование диалогового окна "Создание группы доступности" (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="42efc-262">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="42efc-263">Создание группы доступности (SQL Server PowerShell)</span><span class="sxs-lookup"><span data-stu-id="42efc-263">Create an Availability Group &#40;SQL Server PowerShell&#41;</span></span>](../../../powershell/sql-server-powershell.md)  
  
 <span data-ttu-id="42efc-264">**Включение функции «Группы доступности AlwaysOn»**</span><span class="sxs-lookup"><span data-stu-id="42efc-264">**To enable AlwaysOn Availability Groups**</span></span>  
  
-   [<span data-ttu-id="42efc-265">Включение и отключение групп доступности AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="42efc-265">Enable and Disable AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](enable-and-disable-always-on-availability-groups-sql-server.md)  
  
 <span data-ttu-id="42efc-266">**Настройка конечной точки зеркального отображения базы данных**</span><span class="sxs-lookup"><span data-stu-id="42efc-266">**To configure a database mirroring endpoint**</span></span>  
  
-   [<span data-ttu-id="42efc-267">Создание конечной точки зеркального отображения базы данных для группы доступности AlwaysOn &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="42efc-267">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups &#40;SQL Server PowerShell&#41;</span></span>](database-mirroring-always-on-availability-groups-powershell.md)  
  
-   [<span data-ttu-id="42efc-268">Создание конечной точки зеркального отображения базы данных с проверкой подлинности Windows (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="42efc-268">Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md)  
  
-   [<span data-ttu-id="42efc-269">Использование сертификатов для конечной точки зеркального отображения базы данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="42efc-269">Use Certificates for a Database Mirroring Endpoint &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/use-certificates-for-a-database-mirroring-endpoint-transact-sql.md)  
  
-   [<span data-ttu-id="42efc-270">Укажите URL-адрес конечной точки при добавлении или изменении реплики доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="42efc-270">Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;</span></span>](specify-endpoint-url-adding-or-modifying-availability-replica.md)  
  
 <span data-ttu-id="42efc-271">**Устранение неполадок с конфигурацией групп доступности AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="42efc-271">**To troubleshoot AlwaysOn Availability Groups configuration**</span></span>  
  
-   [<span data-ttu-id="42efc-272">Устранение неполадок при группы доступности AlwaysOn конфигурации (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="42efc-272">Troubleshoot AlwaysOn Availability Groups Configuration (SQL Server)deleted</span></span>](troubleshoot-always-on-availability-groups-configuration-sql-server.md)  
  
-   [<span data-ttu-id="42efc-273">Устранение неполадок при &#40;операции добавления файла группы доступности AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="42efc-273">Troubleshoot a Failed Add-File Operation &#40;AlwaysOn Availability Groups&#41;</span></span>](troubleshoot-a-failed-add-file-operation-always-on-availability-groups.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="42efc-274">См. также</span><span class="sxs-lookup"><span data-stu-id="42efc-274">Related Content</span></span>  
  
-   <span data-ttu-id="42efc-275">**Блоги**</span><span class="sxs-lookup"><span data-stu-id="42efc-275">**Blogs:**</span></span>  
  
     [<span data-ttu-id="42efc-276">Обучающая серия AlwaysON — HADRON. использование пулов рабочих потоков для баз данных с HADRON</span><span class="sxs-lookup"><span data-stu-id="42efc-276">AlwaysON - HADRON Learning Series: Worker Pool Usage for HADRON Enabled Databases</span></span>](https://blogs.msdn.com/b/psssql/archive/2012/05/17/alwayson-hadron-learning-series-worker-pool-usage-for-hadron-enabled-databases.aspx)  
  
     [<span data-ttu-id="42efc-277">Блоги команды разработчиков SQL Server AlwaysOn: официальный блог по SQL Server AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="42efc-277">SQL Server AlwaysOn Team Blogs: The official SQL Server AlwaysOn Team Blog</span></span>](https://blogs.msdn.com/b/sqlalwayson/)  
  
     [<span data-ttu-id="42efc-278">Блоги инженеров CSS SQL Server</span><span class="sxs-lookup"><span data-stu-id="42efc-278">CSS SQL Server Engineers Blogs</span></span>](https://blogs.msdn.com/b/psssql/)  
  
-   <span data-ttu-id="42efc-279">**Видеоролики**</span><span class="sxs-lookup"><span data-stu-id="42efc-279">**Videos:**</span></span>  
  
     [<span data-ttu-id="42efc-280">Microsoft SQL Server с рабочим названием Denali AlwaysOn, часть 1: вводные сведения о решении следующего поколения по обеспечению высокого уровня доступности</span><span class="sxs-lookup"><span data-stu-id="42efc-280">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 1: Introducing the Next Generation High Availability Solution</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI302)  
  
     [<span data-ttu-id="42efc-281">Microsoft SQL Server с рабочим названием Denali AlwaysOn, часть 2: создание критически важного решения по обеспечению высокого уровня доступности с использованием AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="42efc-281">Microsoft SQL Server Code-Named "Denali" AlwaysOn Series,Part 2: Building a Mission-Critical High Availability Solution Using AlwaysOn</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2011/DBI404)  
  
-   <span data-ttu-id="42efc-282">**Технические документы**</span><span class="sxs-lookup"><span data-stu-id="42efc-282">**Whitepapers:**</span></span>  
  
     [<span data-ttu-id="42efc-283">Руководство по решениям режима AlwaysOn в Microsoft SQL Server для обеспечения высокой доступности и аварийного восстановления</span><span class="sxs-lookup"><span data-stu-id="42efc-283">Microsoft SQL Server AlwaysOn Solutions Guide for High Availability and Disaster Recovery</span></span>](https://go.microsoft.com/fwlink/?LinkId=227600)  
  
     [<span data-ttu-id="42efc-284">Технические документы Майкрософт Microsoft по SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="42efc-284">Microsoft White Papers for SQL Server 2012</span></span>](https://msdn.microsoft.com/library/hh403491.aspx)  
  
     [<span data-ttu-id="42efc-285">Технические документы группы консультантов по SQL Server</span><span class="sxs-lookup"><span data-stu-id="42efc-285">SQL Server Customer Advisory Team Whitepapers</span></span>](http://sqlcat.com/)  
  
## <a name="see-also"></a><span data-ttu-id="42efc-286">См. также:</span><span class="sxs-lookup"><span data-stu-id="42efc-286">See Also</span></span>  
 <span data-ttu-id="42efc-287">[Конечная точка зеркального отображения базы данных (SQL Server)](../../database-mirroring/the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="42efc-287">[The Database Mirroring Endpoint &#40;SQL Server&#41;](../../database-mirroring/the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="42efc-288">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="42efc-288">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="42efc-289">Прослушиватели групп доступности, возможность подключения клиентов и отработка отказа приложений (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="42efc-289">Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;</span></span>](../../listeners-client-connectivity-application-failover.md)   
