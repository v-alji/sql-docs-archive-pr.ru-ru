---
title: Создание аудита сервера и спецификаций для аудита базы данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.sqlaudit.dbaudit.general.f1
helpviewer_keywords:
- audits [SQL Server], creating database specification
- database audit [SQL Server]
ms.assetid: 26ee85de-6e97-4318-b526-900924d96e62
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 0cad01eae45d534f0f74911ce8f57827858cc920
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732518"
---
# <a name="create-a-server-audit-and-database-audit-specification"></a><span data-ttu-id="a89f5-102">Создание спецификация аудита для сервера и базы данных</span><span class="sxs-lookup"><span data-stu-id="a89f5-102">Create a Server Audit and Database Audit Specification</span></span>
  <span data-ttu-id="a89f5-103">В этом разделе описано, как создать аудит сервера и спецификацию аудита базы данных в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a89f5-103">This topic describes how to create a server audit and database audit specification in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="a89f5-104">*Аудит* экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] или базы данных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] включает в себя отслеживание и протоколирование событий, происходящих в системе.</span><span class="sxs-lookup"><span data-stu-id="a89f5-104">*Auditing* an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database involves tracking and logging events that occur on the system.</span></span> <span data-ttu-id="a89f5-105">Объект *Подсистема аудита SQL Server* объединяет отдельные экземпляры действий или групп действий уровня сервера или базы данных, за которыми нужно проводить наблюдение.</span><span class="sxs-lookup"><span data-stu-id="a89f5-105">The *SQL Server Audit* object collects a single instance of server- or database-level actions and groups of actions to monitor.</span></span> <span data-ttu-id="a89f5-106">Аудит работает на уровне экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a89f5-106">The audit is at the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance level.</span></span> <span data-ttu-id="a89f5-107">На одном экземпляре [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] может существовать несколько аудитов.</span><span class="sxs-lookup"><span data-stu-id="a89f5-107">You can have multiple audits per [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="a89f5-108">Объект *Спецификация аудита на уровне базы данных* также принадлежит подсистеме аудита.</span><span class="sxs-lookup"><span data-stu-id="a89f5-108">The *Database-Level Audit Specification* object belongs to an audit.</span></span> <span data-ttu-id="a89f5-109">Для аудита вы можете создать одну спецификацию аудита базы данных для каждой базы данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a89f5-109">You can create one database audit specification per SQL Server database per audit.</span></span> <span data-ttu-id="a89f5-110">Дополнительные сведения см. в статье [Подсистема аудита SQL Server (ядро СУБД)](sql-server-audit-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="a89f5-110">For more information, see [SQL Server Audit &#40;Database Engine&#41;](sql-server-audit-database-engine.md).</span></span>  
  
 <span data-ttu-id="a89f5-111">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="a89f5-111">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a89f5-112">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="a89f5-112">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a89f5-113">Ограничения</span><span class="sxs-lookup"><span data-stu-id="a89f5-113">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="a89f5-114">Безопасность</span><span class="sxs-lookup"><span data-stu-id="a89f5-114">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a89f5-115">**Создание аудита сервера и спецификация аудита базы данных**</span><span class="sxs-lookup"><span data-stu-id="a89f5-115">**To create a server audit and database audit specification, using:**</span></span>  
  
     [<span data-ttu-id="a89f5-116">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a89f5-116">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a89f5-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a89f5-117">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a89f5-118">Перед началом</span><span class="sxs-lookup"><span data-stu-id="a89f5-118">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="a89f5-119">Ограничения</span><span class="sxs-lookup"><span data-stu-id="a89f5-119">Limitations and Restrictions</span></span>  
 <span data-ttu-id="a89f5-120">Спецификации аудита базы данных являются незащищаемыми объектами, которые находятся в определенной базе данных.</span><span class="sxs-lookup"><span data-stu-id="a89f5-120">Database audit specifications are non-securable objects that reside in a given database.</span></span> <span data-ttu-id="a89f5-121">После создания спецификация аудита базы данных находится в отключенном состоянии.</span><span class="sxs-lookup"><span data-stu-id="a89f5-121">When a database audit specification is created, it is in a disabled state.</span></span>  
  
 <span data-ttu-id="a89f5-122">Если спецификация аудита базы данных создается или изменяется в пользовательской базе данных, не включайте действия аудита для объектов области сервера, таких как системные представления.</span><span class="sxs-lookup"><span data-stu-id="a89f5-122">When you are creating or modifying a database audit specification in a user database, do not include audit actions on server-scope objects, such as the system views.</span></span> <span data-ttu-id="a89f5-123">Если включаются объекты области сервера, аудит будет создан,</span><span class="sxs-lookup"><span data-stu-id="a89f5-123">If server-scoped objects are included, the audit will be created.</span></span> <span data-ttu-id="a89f5-124">однако объекты области сервера не будут включены и при этом не будет возвращаться ошибка.</span><span class="sxs-lookup"><span data-stu-id="a89f5-124">However, the server-scoped objects will not be included, and no error will be returned.</span></span> <span data-ttu-id="a89f5-125">Для аудита объектов области сервера используйте спецификацию аудита базы данных в базе данных master.</span><span class="sxs-lookup"><span data-stu-id="a89f5-125">To audit server-scope objects, use a database audit specification in the master database.</span></span>  
  
 <span data-ttu-id="a89f5-126">Спецификации аудита базы данных размещаются в базе данных, где они были созданы, за исключением системной базы данных `tempdb`.</span><span class="sxs-lookup"><span data-stu-id="a89f5-126">Database audit specifications reside in the database where they are created, with the exception of the `tempdb` system database.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a89f5-127">безопасность</span><span class="sxs-lookup"><span data-stu-id="a89f5-127">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a89f5-128">Permissions</span><span class="sxs-lookup"><span data-stu-id="a89f5-128">Permissions</span></span>  
  
-   <span data-ttu-id="a89f5-129">Пользователи с разрешением ALTER ANY DATABASE AUDIT могут создавать спецификации аудита базы данных и привязывать их к любому аудиту.</span><span class="sxs-lookup"><span data-stu-id="a89f5-129">Users with the ALTER ANY DATABASE AUDIT permission can create database audit specifications and bind them to any audit.</span></span>  
  
-   <span data-ttu-id="a89f5-130">После создания спецификации аудита базы данных ее могут просматривать участники с разрешениями CONTROL SERVER или ALTER ANY DATABASE AUDIT либо с учетной записью sysadmin.</span><span class="sxs-lookup"><span data-stu-id="a89f5-130">After a database audit specification is created, it can be viewed by principals with the CONTROL SERVER,  ALTER ANY DATABASE AUDIT permissions, or the sysadmin account.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a89f5-131">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a89f5-131">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-server-audit"></a><span data-ttu-id="a89f5-132">Создание аудита сервера</span><span class="sxs-lookup"><span data-stu-id="a89f5-132">To create a server audit</span></span>  
  
1.  <span data-ttu-id="a89f5-133">В обозревателе объектов раскройте папку **Безопасность** .</span><span class="sxs-lookup"><span data-stu-id="a89f5-133">In Object Explorer, expand the **Security** folder.</span></span>  
  
2.  <span data-ttu-id="a89f5-134">Щелкните правой кнопкой мыши папку **аудиты** и выберите пункт **создать аудит...**. Дополнительные сведения см. [в разделе Создание аудита сервера и спецификации аудита сервера](create-a-server-audit-and-server-audit-specification.md).</span><span class="sxs-lookup"><span data-stu-id="a89f5-134">Right-click the **Audits** folder and select **New Audit...**. For more information, see [Create a Server Audit and Server Audit Specification](create-a-server-audit-and-server-audit-specification.md).</span></span>  
  
3.  <span data-ttu-id="a89f5-135">После завершения выбора параметров нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a89f5-135">When you are finished selecting options, click **OK**.</span></span>  
  
#### <a name="to-create-a-database-level-audit-specification"></a><span data-ttu-id="a89f5-136">Создание спецификации аудита на уровне базы данных</span><span class="sxs-lookup"><span data-stu-id="a89f5-136">To create a database-level audit specification</span></span>  
  
1.  <span data-ttu-id="a89f5-137">В обозревателе объектов разверните базу данных, в которой необходимо создать спецификацию аудита.</span><span class="sxs-lookup"><span data-stu-id="a89f5-137">In Object Explorer, expand the database where you want to create an audit specification.</span></span>  
  
2.  <span data-ttu-id="a89f5-138">Разверните папку **Безопасность** .</span><span class="sxs-lookup"><span data-stu-id="a89f5-138">Expand the **Security** folder.</span></span>  
  
3.  <span data-ttu-id="a89f5-139">Щелкните правой кнопкой мыши папку **спецификации аудита базы данных** и выберите **создать спецификацию аудита базы данных.**...</span><span class="sxs-lookup"><span data-stu-id="a89f5-139">Right-click the **Database Audit Specifications** folder and select **New Database Audit Specification...**.</span></span>  
  
     <span data-ttu-id="a89f5-140">В диалоговом окне **Создание спецификации аудита базы данных** доступны следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="a89f5-140">The following options are available on the **Create Database Audit Specification** dialog box.</span></span>  
  
     <span data-ttu-id="a89f5-141">**имя**;</span><span class="sxs-lookup"><span data-stu-id="a89f5-141">**Name**</span></span>  
     <span data-ttu-id="a89f5-142">Имя спецификации аудита базы данных.</span><span class="sxs-lookup"><span data-stu-id="a89f5-142">The name of the database audit specification.</span></span> <span data-ttu-id="a89f5-143">Этот текст формируется автоматически во время создания новой спецификации аудита сервера, однако он доступен для изменения.</span><span class="sxs-lookup"><span data-stu-id="a89f5-143">This is generated automatically when you create a new server audit specification but is editable.</span></span>  
  
     <span data-ttu-id="a89f5-144">**Аудит**</span><span class="sxs-lookup"><span data-stu-id="a89f5-144">**Audit**</span></span>  
     <span data-ttu-id="a89f5-145">Имя спецификации существующего аудита базы данных.</span><span class="sxs-lookup"><span data-stu-id="a89f5-145">The name of an existing database audit.</span></span> <span data-ttu-id="a89f5-146">Введите имя аудита или выберите его из списка.</span><span class="sxs-lookup"><span data-stu-id="a89f5-146">Either type in the name of the audit or select it from the list.</span></span>  
  
     <span data-ttu-id="a89f5-147">**Тип действия аудита**</span><span class="sxs-lookup"><span data-stu-id="a89f5-147">**Audit Action Type**</span></span>  
     <span data-ttu-id="a89f5-148">Указывает группы действий аудита на уровне базы данных и действия аудита для захвата.</span><span class="sxs-lookup"><span data-stu-id="a89f5-148">Specifies the database-level audit action groups and audit actions to capture.</span></span> <span data-ttu-id="a89f5-149">Список групп действий аудита на уровне базы данных, действия аудита и описание содержащихся в них событий см. в статье [Действия и группы действий подсистемы аудита SQL Server](sql-server-audit-action-groups-and-actions.md).</span><span class="sxs-lookup"><span data-stu-id="a89f5-149">For the list of database-level audit action groups and audit actions and a description of the events they contain, see [SQL Server Audit Action Groups and Actions](sql-server-audit-action-groups-and-actions.md).</span></span>  
  
     <span data-ttu-id="a89f5-150">**Схема объекта**</span><span class="sxs-lookup"><span data-stu-id="a89f5-150">**Object Schema**</span></span>  
     <span data-ttu-id="a89f5-151">Отображает схему для указанного **Имени объекта**.</span><span class="sxs-lookup"><span data-stu-id="a89f5-151">Displays the schema for the specified **Object Name**.</span></span>  
  
     <span data-ttu-id="a89f5-152">**Имени объекта**</span><span class="sxs-lookup"><span data-stu-id="a89f5-152">**Object Name**</span></span>  
     <span data-ttu-id="a89f5-153">Имя объекта для аудита.</span><span class="sxs-lookup"><span data-stu-id="a89f5-153">The name of the object to audit.</span></span> <span data-ttu-id="a89f5-154">Доступно только для действий аудита и неприменимо к группам аудита.</span><span class="sxs-lookup"><span data-stu-id="a89f5-154">This is only available for audit actions; it does not apply to audit groups.</span></span>  
  
     <span data-ttu-id="a89f5-155">**Кнопка с многоточием (...)**</span><span class="sxs-lookup"><span data-stu-id="a89f5-155">**Ellipsis (...)**</span></span>  
     <span data-ttu-id="a89f5-156">Открывает диалоговое окно **Выбор объектов** для просмотра и выбора доступного объекта на основе указанного **Типа действия аудита**.</span><span class="sxs-lookup"><span data-stu-id="a89f5-156">Opens the **Select Objects** dialog to browse for and select an available object, based on the specified **Audit Action Type**.</span></span>  
  
     <span data-ttu-id="a89f5-157">**Имя участника**</span><span class="sxs-lookup"><span data-stu-id="a89f5-157">**Principal Name**</span></span>  
     <span data-ttu-id="a89f5-158">Учетная запись для фильтрации аудита для объекта, подвергнутого аудиту.</span><span class="sxs-lookup"><span data-stu-id="a89f5-158">The account to filter the audit by for the object being audited.</span></span>  
  
     <span data-ttu-id="a89f5-159">**Кнопка с многоточием (...)**</span><span class="sxs-lookup"><span data-stu-id="a89f5-159">**Ellipsis (...)**</span></span>  
     <span data-ttu-id="a89f5-160">Открывает диалоговое окно **Выбор объектов** для просмотра и выбора доступного объекта с учетом указанного параметра **Имя объекта**.</span><span class="sxs-lookup"><span data-stu-id="a89f5-160">Opens the **Select Objects** dialog to browse for and select an available object, based on the specified **Object Name**.</span></span>  
  
4.  <span data-ttu-id="a89f5-161">После завершения выбора параметра нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a89f5-161">When you are finished selecting option, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a89f5-162">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a89f5-162">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-server-audit"></a><span data-ttu-id="a89f5-163">Создание аудита сервера</span><span class="sxs-lookup"><span data-stu-id="a89f5-163">To create a server audit</span></span>  
  
1.  <span data-ttu-id="a89f5-164">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a89f5-164">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a89f5-165">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="a89f5-165">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a89f5-166">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="a89f5-166">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE master ;  
    GO  
    -- Create the server audit.   
    CREATE SERVER AUDIT Payrole_Security_Audit  
        TO FILE ( FILEPATH =   
    'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA' ) ;   
    GO  
    -- Enable the server audit.   
    ALTER SERVER AUDIT Payrole_Security_Audit   
    WITH (STATE = ON) ;  
    ```  
  
#### <a name="to-create-a-database-level-audit-specification"></a><span data-ttu-id="a89f5-167">Создание спецификации аудита на уровне базы данных</span><span class="sxs-lookup"><span data-stu-id="a89f5-167">To create a database-level audit specification</span></span>  
  
1.  <span data-ttu-id="a89f5-168">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a89f5-168">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a89f5-169">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="a89f5-169">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a89f5-170">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="a89f5-170">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="a89f5-171">В следующем примере создается спецификация аудита базы данных с именем `Audit_Pay_Tables`, которая выполняет аудит инструкций SELECT и INSERT пользователя `dbo` для таблицы `HumanResources.EmployeePayHistory` на основе аудита сервера, заданного выше.</span><span class="sxs-lookup"><span data-stu-id="a89f5-171">The example creates a database audit specification called `Audit_Pay_Tables` that audits SELECT and INSERT statements by the `dbo` user, for the `HumanResources.EmployeePayHistory` table based on the server audit defined above.</span></span>  
  
    ```  
    USE AdventureWorks2012 ;   
    GO  
    -- Create the database audit specification.   
    CREATE DATABASE AUDIT SPECIFICATION Audit_Pay_Tables  
    FOR SERVER AUDIT Payrole_Security_Audit  
    ADD (SELECT , INSERT  
         ON HumanResources.EmployeePayHistory BY dbo )   
    WITH (STATE = ON) ;   
    GO  
  
    ```  
  
 <span data-ttu-id="a89f5-172">Дополнительные сведения см. в статьях [CREATE SERVER AUDIT (Transact-SQL)](/sql/t-sql/statements/create-server-audit-transact-sql) и [CREATE DATABASE AUDIT SPECIFICATION (Transact-SQL)](/sql/t-sql/statements/create-database-audit-specification-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a89f5-172">For more information, see [CREATE SERVER AUDIT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-audit-transact-sql) and [CREATE DATABASE AUDIT SPECIFICATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-database-audit-specification-transact-sql).</span></span>  
  
  
