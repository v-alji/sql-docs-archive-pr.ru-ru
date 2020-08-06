---
title: Миграция на частично автономную базу данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- contained database, migrating to
ms.assetid: 90faac38-f79e-496d-b589-e8b2fe01c562
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6142d46dc0540e5998fa66d463538d1453a17d84
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751059"
---
# <a name="migrate-to-a-partially-contained-database"></a><span data-ttu-id="1b5a4-102">Migrate to a Partially Contained Database</span><span class="sxs-lookup"><span data-stu-id="1b5a4-102">Migrate to a Partially Contained Database</span></span>
  <span data-ttu-id="1b5a4-103">В этом разделе описано, как подготовить к переходу на частично автономную модель базы данных, и приведены шаги по миграции.</span><span class="sxs-lookup"><span data-stu-id="1b5a4-103">This topic discusses how to prepare to change to the partially contained database model and then provides the migration steps.</span></span>  
  
 <span data-ttu-id="1b5a4-104">**В этом разделе:**</span><span class="sxs-lookup"><span data-stu-id="1b5a4-104">**In this topic:**</span></span>  
  
-   [<span data-ttu-id="1b5a4-105">Подготовка к миграции базы данных</span><span class="sxs-lookup"><span data-stu-id="1b5a4-105">Preparing to Migrate a Database</span></span>](#prepare)  
  
-   [<span data-ttu-id="1b5a4-106">Включение автономных баз данных</span><span class="sxs-lookup"><span data-stu-id="1b5a4-106">Enable Contained Databases</span></span>](#enable)  
  
-   [<span data-ttu-id="1b5a4-107">Преобразование базы данных в частично автономную</span><span class="sxs-lookup"><span data-stu-id="1b5a4-107">Converting a Database to Partially Contained</span></span>](#convert)  
  
-   [<span data-ttu-id="1b5a4-108">Миграция пользователей в пользователей автономной базы данных</span><span class="sxs-lookup"><span data-stu-id="1b5a4-108">Migrating Users to Contained Database Users</span></span>](#users)  
  
##  <a name="preparing-to-migrate-a-database"></a><a name="prepare"></a> <span data-ttu-id="1b5a4-109">Подготовка к миграции базы данных</span><span class="sxs-lookup"><span data-stu-id="1b5a4-109">Preparing to Migrate a Database</span></span>  
 <span data-ttu-id="1b5a4-110">Перед началом перевода базы данных в частичную автономную модель просмотрите следующие указания.</span><span class="sxs-lookup"><span data-stu-id="1b5a4-110">Review the following items when considering migrating a database to the partially contained database model.</span></span>  
  
-   <span data-ttu-id="1b5a4-111">Для этого потребуется понимание модели частично автономной базы данных.</span><span class="sxs-lookup"><span data-stu-id="1b5a4-111">You should understand the partially contained database model.</span></span> <span data-ttu-id="1b5a4-112">Дополнительные сведения см. в разделе [Contained Databases](contained-databases.md).</span><span class="sxs-lookup"><span data-stu-id="1b5a4-112">For more information, see [Contained Databases](contained-databases.md).</span></span>  
  
-   <span data-ttu-id="1b5a4-113">Необходимо понимать риски, связанные с частично автономными базами данных.</span><span class="sxs-lookup"><span data-stu-id="1b5a4-113">You should understand risks that are unique to partially contained databases.</span></span> <span data-ttu-id="1b5a4-114">Дополнительные сведения см. в разделе [Security Best Practices with Contained Databases](security-best-practices-with-contained-databases.md).</span><span class="sxs-lookup"><span data-stu-id="1b5a4-114">For more information, see [Security Best Practices with Contained Databases](security-best-practices-with-contained-databases.md).</span></span>  
  
-   <span data-ttu-id="1b5a4-115">Автономные базы данных не поддерживают репликацию, отслеживание измененных данных или отслеживание изменений.</span><span class="sxs-lookup"><span data-stu-id="1b5a4-115">Contained databases do not support replication, change data capture, or change tracking.</span></span> <span data-ttu-id="1b5a4-116">Убедитесь, что в базе данных не используются эти функции.</span><span class="sxs-lookup"><span data-stu-id="1b5a4-116">Confirm the database does not use these features.</span></span>  
  
-   <span data-ttu-id="1b5a4-117">Просмотрите список функций базы данных, которые изменились для частично автономных баз данных.</span><span class="sxs-lookup"><span data-stu-id="1b5a4-117">Review the list of database features that are modified for partially contained databases.</span></span> <span data-ttu-id="1b5a4-118">Дополнительные сведения см. в разделе [Измененные функции (автономная база данных)](modified-features-contained-database.md).</span><span class="sxs-lookup"><span data-stu-id="1b5a4-118">For more information, see [Modified Features &#40;Contained Database&#41;](modified-features-contained-database.md).</span></span>  
  
-   <span data-ttu-id="1b5a4-119">Выполнив запрос к представлению [sys.dm_db_uncontained_entities (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-uncontained-entities-transact-sql) , найдите в базе данных неавтономные объекты или функции.</span><span class="sxs-lookup"><span data-stu-id="1b5a4-119">Query [sys.dm_db_uncontained_entities &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-uncontained-entities-transact-sql) to find uncontained objects or features in the database.</span></span> <span data-ttu-id="1b5a4-120">Дополнительные сведения см. в разделе</span><span class="sxs-lookup"><span data-stu-id="1b5a4-120">For more information, see.</span></span>  
  
-   <span data-ttu-id="1b5a4-121">Мониторьте XEvent **database_uncontained_usage** , чтобы определить, когда используются неавтономные функции.</span><span class="sxs-lookup"><span data-stu-id="1b5a4-121">Monitor the **database_uncontained_usage** XEvent to see when uncontained features are used.</span></span>  
  
##  <a name="enable-contained-databases"></a><a name="enable"></a> <span data-ttu-id="1b5a4-122">Включение автономных баз данных</span><span class="sxs-lookup"><span data-stu-id="1b5a4-122">Enable Contained Databases</span></span>  
 <span data-ttu-id="1b5a4-123">Перед созданием автономных баз данных поддержка автономных баз данных должна быть включена на экземпляре [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1b5a4-123">Contained databases must be enabled on the instance of [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], before contained databases can be created.</span></span>  
  
### <a name="enabling-contained-databases-using-transact-sql"></a><span data-ttu-id="1b5a4-124">Включение автономных баз данных с помощью Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1b5a4-124">Enabling Contained Databases Using Transact-SQL</span></span>  
 <span data-ttu-id="1b5a4-125">В следующем примере в экземпляре компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]создаются автономные базы данных.</span><span class="sxs-lookup"><span data-stu-id="1b5a4-125">The following example enables contained databases on the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
```sql  
sp_configure 'contained database authentication', 1;  
GO  
RECONFIGURE ;  
GO  
```  
  
#### <a name="enabling-contained-databases-using-management-studio"></a><span data-ttu-id="1b5a4-126">Включение автономных баз данных с помощью среды Management Studio</span><span class="sxs-lookup"><span data-stu-id="1b5a4-126">Enabling Contained Databases Using Management Studio</span></span>  
 <span data-ttu-id="1b5a4-127">В следующем примере в экземпляре компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]создаются автономные базы данных.</span><span class="sxs-lookup"><span data-stu-id="1b5a4-127">The following example enables contained databases on the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
1.  <span data-ttu-id="1b5a4-128">В обозревателе объектов щелкните правой кнопкой мыши имя сервера и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="1b5a4-128">In Object Explorer, right-click the server name, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="1b5a4-129">На странице **Расширенные** в разделе **Включение** установите параметр **Включить автономные базы данных** в значение **True**.</span><span class="sxs-lookup"><span data-stu-id="1b5a4-129">On the **Advanced** page, in the **Containment** section, set the **Enable Contained Databases** option to **True**.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="converting-a-database-to-partially-contained"></a><a name="convert"></a> <span data-ttu-id="1b5a4-130">Преобразование базы данных в частично автономную</span><span class="sxs-lookup"><span data-stu-id="1b5a4-130">Converting a Database to Partially Contained</span></span>  
 <span data-ttu-id="1b5a4-131">База данных преобразуется в автономную путем изменения ее параметра **CONTAINMENT** .</span><span class="sxs-lookup"><span data-stu-id="1b5a4-131">A database is converted to a contained database by changing the **CONTAINMENT** option.</span></span>  
  
### <a name="converting-a-database-to-partially-contained-using-transact-sql"></a><span data-ttu-id="1b5a4-132">Преобразование базы данных в частично автономную с помощью Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1b5a4-132">Converting a Database to Partially Contained Using Transact-SQL</span></span>  
 <span data-ttu-id="1b5a4-133">В следующем примере база данных показано преобразование `Accounting` в частично автономную базу данных.</span><span class="sxs-lookup"><span data-stu-id="1b5a4-133">The following example converts a database named `Accounting` to a partially contained database.</span></span>  
  
```sql  
USE [master]  
GO  
ALTER DATABASE [Accounting] SET CONTAINMENT = PARTIAL  
GO  
```  
  
### <a name="converting-a-database-to-partially-contained-using-management-studio"></a><span data-ttu-id="1b5a4-134">Преобразование базы данных в частично автономную с помощью среды Management Studio</span><span class="sxs-lookup"><span data-stu-id="1b5a4-134">Converting a Database to Partially contained Using Management Studio</span></span>  
 <span data-ttu-id="1b5a4-135">В следующем примере база данных преобразуется в частично автономную базу данных.</span><span class="sxs-lookup"><span data-stu-id="1b5a4-135">The following example converts a database to a partially contained database.</span></span>  
  
1.  <span data-ttu-id="1b5a4-136">В обозревателе объектов разверните узел **Базы данных**, щелкните правой кнопкой мыши базу данных, которую нужно преобразовать, а затем выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="1b5a4-136">In Object Explorer, expand **Databases**, right-click the database to be converted, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="1b5a4-137">На странице **Параметры** измените параметр **Тип вложения** на **Частичный**.</span><span class="sxs-lookup"><span data-stu-id="1b5a4-137">On the **Options** page, change the **Containment type** option to **Partial**.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="migrating-users-to-contained-database-users"></a><a name="users"></a> <span data-ttu-id="1b5a4-138">Миграция пользователей в пользователей автономной базы данных</span><span class="sxs-lookup"><span data-stu-id="1b5a4-138">Migrating Users to Contained Database Users</span></span>  
 <span data-ttu-id="1b5a4-139">В следующем примере выполняется миграция всех пользователей, основанных на имени входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , в пользователей автономной базы данных с паролями.</span><span class="sxs-lookup"><span data-stu-id="1b5a4-139">The following example migrates all users that are based on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins to contained database users with passwords.</span></span> <span data-ttu-id="1b5a4-140">Этот пример исключает имена входа, которые не были включены.</span><span class="sxs-lookup"><span data-stu-id="1b5a4-140">The example excludes logins that are not enabled.</span></span> <span data-ttu-id="1b5a4-141">Этот пример должен выполняться в автономной базе данных.</span><span class="sxs-lookup"><span data-stu-id="1b5a4-141">The example must be executed in the contained database.</span></span>  
  
```sql  
DECLARE @username sysname ;  
DECLARE user_cursor CURSOR  
    FOR   
        SELECT dp.name   
        FROM sys.database_principals AS dp  
        JOIN sys.server_principals AS sp   
        ON dp.sid = sp.sid  
        WHERE dp.authentication_type = 1 AND sp.is_disabled = 0;  
OPEN user_cursor  
FETCH NEXT FROM user_cursor INTO @username  
    WHILE @@FETCH_STATUS = 0  
    BEGIN  
        EXECUTE sp_migrate_user_to_contained   
        @username = @username,  
        @rename = N'keep_name',  
        @disablelogin = N'disable_login';  
    FETCH NEXT FROM user_cursor INTO @username  
    END  
CLOSE user_cursor ;  
DEALLOCATE user_cursor ;  
```  
  
## <a name="see-also"></a><span data-ttu-id="1b5a4-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="1b5a4-142">See Also</span></span>  
 <span data-ttu-id="1b5a4-143">[Автономные базы данных](contained-databases.md) </span><span class="sxs-lookup"><span data-stu-id="1b5a4-143">[Contained Databases](contained-databases.md) </span></span>  
 <span data-ttu-id="1b5a4-144">[sp_migrate_user_to_contained (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-migrate-user-to-contained-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1b5a4-144">[sp_migrate_user_to_contained &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-migrate-user-to-contained-transact-sql) </span></span>  
 [<span data-ttu-id="1b5a4-145">sys.dm_db_uncontained_entities (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="1b5a4-145">sys.dm_db_uncontained_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-uncontained-entities-transact-sql)  
  
  
