---
title: Создание схемы базы данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.schemas.general.f1
helpviewer_keywords:
- creating schemas with Management Studio
- CREATE SCHEMA [Management Studio]
- database schemas
- schemas [SQL Server], creating
ms.assetid: ed2a5522-f4d2-4111-95a4-d3e1e5081739
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 3ac0c00768db6501c7d786c35758c1a9d75a5a7b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730389"
---
# <a name="create-a-database-schema"></a><span data-ttu-id="8cdab-102">Создание схемы базы данных</span><span class="sxs-lookup"><span data-stu-id="8cdab-102">Create a Database Schema</span></span>
  <span data-ttu-id="8cdab-103">В этом разделе описывается создание схемы в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8cdab-103">This topic describes how to create a schema in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="8cdab-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="8cdab-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8cdab-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="8cdab-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8cdab-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="8cdab-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="8cdab-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="8cdab-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8cdab-108">**Создание схемы с помощью следующих средств**</span><span class="sxs-lookup"><span data-stu-id="8cdab-108">**To create a schema, using:**</span></span>  
  
     [<span data-ttu-id="8cdab-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8cdab-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8cdab-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8cdab-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8cdab-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="8cdab-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="8cdab-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="8cdab-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="8cdab-113">Новая схема принадлежит одному из следующих участников уровня базы данных: пользователю базы данных, роли базы данных или роли приложения.</span><span class="sxs-lookup"><span data-stu-id="8cdab-113">The new schema is owned by one of the following database-level principals: database user, database role, or application role.</span></span> <span data-ttu-id="8cdab-114">Объекты, создаваемые в схеме, принадлежат владельцу схемы и имеют значение NULL для **principal_id** в **sys.objects**.</span><span class="sxs-lookup"><span data-stu-id="8cdab-114">Objects created within a schema are owned by the owner of the schema, and have a NULL **principal_id** in **sys.objects**.</span></span> <span data-ttu-id="8cdab-115">Владение объектами, содержащимися в схеме, можно передать любому участнику уровня базы данных, однако у владельца схемы всегда остается разрешение CONTROL на объекты в схеме.</span><span class="sxs-lookup"><span data-stu-id="8cdab-115">Ownership of schema-contained objects can be transferred to any database-level principal, but the schema owner always retains CONTROL permission on objects within the schema.</span></span>  
  
-   <span data-ttu-id="8cdab-116">Если при создании объекта базы данных указать допустимого участника домена (пользователя или группу) в качестве владельца объекта, то этот участник будет добавлен в базу данных в качестве схемы.</span><span class="sxs-lookup"><span data-stu-id="8cdab-116">When creating a database object, if you specify a valid domain principal (user or group) as the object owner, the domain principal will be added to the database as a schema.</span></span> <span data-ttu-id="8cdab-117">Новая схема будет принадлежать этому участнику домена.</span><span class="sxs-lookup"><span data-stu-id="8cdab-117">The new schema will be owned by that domain principal.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8cdab-118">безопасность</span><span class="sxs-lookup"><span data-stu-id="8cdab-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8cdab-119">Permissions</span><span class="sxs-lookup"><span data-stu-id="8cdab-119">Permissions</span></span>  
  
-   <span data-ttu-id="8cdab-120">Требует разрешения CREATE SCHEMA в базе данных.</span><span class="sxs-lookup"><span data-stu-id="8cdab-120">Requires CREATE SCHEMA permission on the database.</span></span>  
  
-   <span data-ttu-id="8cdab-121">Чтобы назначить другого пользователя владельцем создаваемой схемы, у участника должно быть разрешение IMPERSONATE на этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="8cdab-121">To specify another user as the owner of the schema being created, the caller must have IMPERSONATE permission on that user.</span></span> <span data-ttu-id="8cdab-122">Если роль базы данных указана в качестве владельца, то вызывающий объект должен входить в роль или иметь на нее разрешение ALTER.</span><span class="sxs-lookup"><span data-stu-id="8cdab-122">If a database role is specified as the owner, the caller must have one of the following: membership in the role or ALTER permission on the role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8cdab-123">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8cdab-123">Using SQL Server Management Studio</span></span>  
  
##### <a name="to-create-a-schema"></a><span data-ttu-id="8cdab-124">Создание схемы</span><span class="sxs-lookup"><span data-stu-id="8cdab-124">To create a schema</span></span>  
  
1.  <span data-ttu-id="8cdab-125">В обозревателе объектов раскройте папку **Базы данных** .</span><span class="sxs-lookup"><span data-stu-id="8cdab-125">In Object Explorer, expand the **Databases** folder.</span></span>  
  
2.  <span data-ttu-id="8cdab-126">Разверните базу данных, в которой создается новая схема базы данных.</span><span class="sxs-lookup"><span data-stu-id="8cdab-126">Expand the database in which to create the new database schema.</span></span>  
  
3.  <span data-ttu-id="8cdab-127">Щелкните правой кнопкой мыши папку **Безопасность** , укажите на пункт **Создать**и выберите **Схема**.</span><span class="sxs-lookup"><span data-stu-id="8cdab-127">Right-click the **Security** folder, point to **New**, and select **Schema**.</span></span>  
  
4.  <span data-ttu-id="8cdab-128">В диалоговом окне **Схема — создать** на странице **Общие** введите имя новой схемы в поле **Имя схемы** .</span><span class="sxs-lookup"><span data-stu-id="8cdab-128">In the **Schema - New** dialog box, on the **General** page, enter a name for the new schema in the **Schema name** box.</span></span>  
  
5.  <span data-ttu-id="8cdab-129">В поле **Владелец схемы** введите имя пользователя или роли базы данных, которые будут владельцем схемы.</span><span class="sxs-lookup"><span data-stu-id="8cdab-129">In the **Schema owner** box, enter the name of a database user or role to own the schema.</span></span> <span data-ttu-id="8cdab-130">Также можно нажать кнопку **Поиск** , чтобы открыть диалоговое окно **Поиск ролей и пользователей** .</span><span class="sxs-lookup"><span data-stu-id="8cdab-130">Alternately, click **Search** to open the **Search Roles and Users** dialog box.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="additional-options"></a><span data-ttu-id="8cdab-131">Дополнительные параметры</span><span class="sxs-lookup"><span data-stu-id="8cdab-131">Additional Options</span></span>  
 <span data-ttu-id="8cdab-132">Диалоговое окно **Схема — создать** также содержит параметры на двух дополнительных страницах: **Разрешения** и **Расширенные свойства**.</span><span class="sxs-lookup"><span data-stu-id="8cdab-132">The **Schema- New** dialog box also offers options on two additional pages: **Permissions** and **Extended Properties**.</span></span>  
  
-   <span data-ttu-id="8cdab-133">На странице **Разрешения** перечислены все возможные защищаемые объекты и разрешения на эти объекты, которые могут быть предоставлены для имени входа.</span><span class="sxs-lookup"><span data-stu-id="8cdab-133">The **Permissions** page lists all possible securables and the permissions on those securables that can be granted to the login.</span></span>  
  
-   <span data-ttu-id="8cdab-134">Страница **Расширенные свойства** позволяет добавлять пользовательские свойства пользователям базы данных.</span><span class="sxs-lookup"><span data-stu-id="8cdab-134">The **Extended properties** page allows you to add custom properties to database users.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8cdab-135">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8cdab-135">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-schema"></a><span data-ttu-id="8cdab-136">Создание схемы</span><span class="sxs-lookup"><span data-stu-id="8cdab-136">To create a schema</span></span>  
  
1.  <span data-ttu-id="8cdab-137">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8cdab-137">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8cdab-138">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="8cdab-138">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8cdab-139">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="8cdab-139">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Creates the schema Sprockets owned by Annik that contains table NineProngs.   
    -- The statement grants SELECT to Mandar and denies SELECT to Prasanna.  
  
    CREATE SCHEMA Sprockets AUTHORIZATION Annik  
        CREATE TABLE NineProngs (source int, cost int, partnumber int)  
        GRANT SELECT ON SCHEMA::Sprockets TO Mandar  
        DENY SELECT ON SCHEMA::Sprockets TO Prasanna;  
    GO  
    ```  
  
 <span data-ttu-id="8cdab-140">Дополнительные сведения см. в разделе [CREATE SCHEMA (Transact-SQL)](/sql/t-sql/statements/create-schema-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8cdab-140">For more information, see [CREATE SCHEMA &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-schema-transact-sql).</span></span>  
  
  
