---
title: Просмотр зависимостей таблицы | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- table dependencies [SQL Server]
- dependencies [SQL Server], tables
- displaying dependences
- viewing dependencies
ms.assetid: c4351ef5-e7d0-46e7-8367-88695e9974f8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 20f54b913124cdaa8a7dfeebac01ba070cc37d88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669342"
---
# <a name="view-the-dependencies-of-a-table"></a><span data-ttu-id="eec5e-102">Просмотр зависимостей таблицы</span><span class="sxs-lookup"><span data-stu-id="eec5e-102">View the Dependencies of a Table</span></span>
  <span data-ttu-id="eec5e-103">Зависимости таблицы в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] можно просмотреть в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или с помощью [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eec5e-103">You can view a table's dependencies in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="eec5e-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="eec5e-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="eec5e-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="eec5e-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="eec5e-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="eec5e-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="eec5e-107">**Просмотр зависимостей таблицы с помощью следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="eec5e-107">**To view a table's dependencies, using:**</span></span>  
  
     [<span data-ttu-id="eec5e-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="eec5e-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="eec5e-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="eec5e-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="eec5e-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="eec5e-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="eec5e-111">безопасность</span><span class="sxs-lookup"><span data-stu-id="eec5e-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="eec5e-112">Permissions</span><span class="sxs-lookup"><span data-stu-id="eec5e-112">Permissions</span></span>  
 <span data-ttu-id="eec5e-113">Необходимо разрешение VIEW DEFINITION в базе данных и разрешение SELECT на представление sys.sql_expression_dependencies в базе данных.</span><span class="sxs-lookup"><span data-stu-id="eec5e-113">Requires VIEW DEFINITION permission on the database and SELECT permission on sys.sql_expression_dependencies for the database.</span></span> <span data-ttu-id="eec5e-114">По умолчанию разрешение SELECT предоставляется только членам предопределенной роли базы данных db_owner.</span><span class="sxs-lookup"><span data-stu-id="eec5e-114">By default, SELECT permission is granted only to members of the db_owner fixed database role.</span></span> <span data-ttu-id="eec5e-115">Если разрешения SELECT и VIEW DEFINITION предоставлены другому пользователю, он может просматривать все зависимости в базе данных.</span><span class="sxs-lookup"><span data-stu-id="eec5e-115">When SELECT and VIEW DEFINITION permissions are granted to another user, the grantee can view all dependencies in the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="eec5e-116">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="eec5e-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-dependencies-of-a-table"></a><span data-ttu-id="eec5e-117">Просмотр зависимостей таблицы</span><span class="sxs-lookup"><span data-stu-id="eec5e-117">To view the dependencies of a table</span></span>  
  
1.  <span data-ttu-id="eec5e-118">В **Обозревателе объектов**разверните узел **Базы данных**, разверните саму базу данных, а затем разверните узел **Таблицы**.</span><span class="sxs-lookup"><span data-stu-id="eec5e-118">In **Object Explorer**, expand **Databases**, expand a database, and then expand **Tables**.</span></span>  
  
2.  <span data-ttu-id="eec5e-119">Щелкните таблицу правой кнопкой мыши и выберите **Просмотр зависимостей**.</span><span class="sxs-lookup"><span data-stu-id="eec5e-119">Right-click a table, and then click **View Dependencies**.</span></span>  
  
3.  <span data-ttu-id="eec5e-120">В диалоговом окне **Зависимости объектов** _\<object name>_ выберите либо вариант **Объекты, которые зависят от** _\<object name>_ , либо вариант **Объекты, от которых зависит** _\<object name>_ .</span><span class="sxs-lookup"><span data-stu-id="eec5e-120">In the **Object Dependencies**_\<object name>_ dialog box, select either **Objects that depend on** _\<object name>_, or **Objects on which**_\<object name>_**depends**.</span></span>  
  
4.  <span data-ttu-id="eec5e-121">Выберите объект в сетке **Зависимости** .</span><span class="sxs-lookup"><span data-stu-id="eec5e-121">Select an object in the **Dependencies** grid.</span></span> <span data-ttu-id="eec5e-122">Тип объекта (например, "Триггер" или "Хранимая процедура") появится в поле **Тип** .</span><span class="sxs-lookup"><span data-stu-id="eec5e-122">The type of object (such as "Trigger" or "Stored Procedure"), appears in the **Type** box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="eec5e-123">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="eec5e-123">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-objects-that-depend-on-a-table"></a><span data-ttu-id="eec5e-124">Просмотр объектов, зависящих от таблицы</span><span class="sxs-lookup"><span data-stu-id="eec5e-124">To view the objects that depend on a table</span></span>  
  
1.  <span data-ttu-id="eec5e-125">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eec5e-125">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="eec5e-126">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="eec5e-126">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="eec5e-127">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="eec5e-127">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT * FROM sys.sql_expression_dependencies  
    WHERE referencing_id = OBJECT_ID(N'Production.vProductAndDescription');   
    GO  
  
    ```  
  
#### <a name="to-view-the-objects-on-which-a-table-depends"></a><span data-ttu-id="eec5e-128">Просмотр объектов, от которых зависит таблица</span><span class="sxs-lookup"><span data-stu-id="eec5e-128">To view the objects on which a table depends</span></span>  
  
1.  <span data-ttu-id="eec5e-129">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eec5e-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="eec5e-130">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="eec5e-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="eec5e-131">Следующий пример возвращает объекты, которые зависят от таблицы `Production.Product`.</span><span class="sxs-lookup"><span data-stu-id="eec5e-131">The following example returns the objects that depend on the table `Production.Product`.</span></span> <span data-ttu-id="eec5e-132">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="eec5e-132">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    SELECT * FROM sys.sql_expression_dependencies  
    WHERE referenced_id = OBJECT_ID(N'Production.Product');   
    GO  
  
    ```  
  
 <span data-ttu-id="eec5e-133">Дополнительные сведения см. в разделе [sys.sql_expression_dependencies (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="eec5e-133">For additional information, see [sys.sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql)</span></span>  
  
  
