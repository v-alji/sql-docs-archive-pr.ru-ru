---
title: Удаление индекса | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- removing indexes
- deleting indexes
- dropping indexes
- indexes [SQL Server], dropping
- index deletions [SQL Server]
ms.assetid: fd38a0ed-26c4-4c76-9ef7-e0a16147329d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4552ba701782e5790f95f54c0c1c66f82573f1e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749831"
---
# <a name="delete-an-index"></a><span data-ttu-id="f969c-102">Удаление индекса</span><span class="sxs-lookup"><span data-stu-id="f969c-102">Delete an Index</span></span>
  <span data-ttu-id="f969c-103">В этом разделе описано удаление индекса в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f969c-103">This topic describes how to delete (drop) an index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="f969c-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="f969c-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f969c-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="f969c-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f969c-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="f969c-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="f969c-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="f969c-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f969c-108">**Удаление индекса с помощью**</span><span class="sxs-lookup"><span data-stu-id="f969c-108">**To delete an index, using:**</span></span>  
  
     [<span data-ttu-id="f969c-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f969c-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="f969c-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f969c-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f969c-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="f969c-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f969c-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="f969c-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="f969c-113">Индексы, созданные с помощью ограничений уникальности и первичных ключей, нельзя удалить этим способом.</span><span class="sxs-lookup"><span data-stu-id="f969c-113">Indexes created as the result of a PRIMARY KEY or UNIQUE constraint cannot be deleted by using this method.</span></span> <span data-ttu-id="f969c-114">Вместо этого следует удалять сами ограничения.</span><span class="sxs-lookup"><span data-stu-id="f969c-114">Instead, the constraint must be deleted.</span></span> <span data-ttu-id="f969c-115">Для удаления ограничения и соответствующего индекса используется инструкция [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) с предложением DROP CONSTRAINT на языке [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f969c-115">To remove the constraint and corresponding index, use [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) with the DROP CONSTRAINT clause in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="f969c-116">Дополнительные сведения см. в статье [Delete Primary Keys](../tables/delete-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="f969c-116">For more information, see [Delete Primary Keys](../tables/delete-primary-keys.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f969c-117">безопасность</span><span class="sxs-lookup"><span data-stu-id="f969c-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f969c-118">Permissions</span><span class="sxs-lookup"><span data-stu-id="f969c-118">Permissions</span></span>  
 <span data-ttu-id="f969c-119">Необходимо разрешение ALTER для таблицы или представления.</span><span class="sxs-lookup"><span data-stu-id="f969c-119">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="f969c-120">По умолчанию это разрешение предоставляется предопределенной роли сервера **sysadmin** и предопределенным ролям базы данных **db_ddladmin** и **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="f969c-120">This permission is granted by default to the **sysadmin** fixed server role and the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f969c-121">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f969c-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-an-index-by-using-object-explorer"></a><span data-ttu-id="f969c-122">Удаление индекса в обозревателе объектов</span><span class="sxs-lookup"><span data-stu-id="f969c-122">To delete an index by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="f969c-123">В обозревателе объектов разверните базу данных, содержащую таблицу, в которой необходимо удалить индекс.</span><span class="sxs-lookup"><span data-stu-id="f969c-123">In Object Explorer, expand the database that contains the table on which you want to delete an index.</span></span>  
  
2.  <span data-ttu-id="f969c-124">Разверните папку **Таблицы**.</span><span class="sxs-lookup"><span data-stu-id="f969c-124">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="f969c-125">Разверните таблицу, содержащую индекс, который нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="f969c-125">Expand the table that contains the index you want to delete.</span></span>  
  
4.  <span data-ttu-id="f969c-126">Разверните папку **Индексы**.</span><span class="sxs-lookup"><span data-stu-id="f969c-126">Expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="f969c-127">Щелкните правой кнопкой мыши индекс, который необходимо удалить, и выберите пункт **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="f969c-127">Right-click the index you want to delete and select **Delete**.</span></span>  
  
6.  <span data-ttu-id="f969c-128">В диалоговом окне **Удаление объекта** убедитесь, что в сетке **Объекты для удаления** указан нужный индекс, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f969c-128">In the **Delete Object** dialog box, verify that the correct index is in the **Object to be deleted** grid and click **OK**.</span></span>  
  
#### <a name="to-delete-an-index-using-table-designer"></a><span data-ttu-id="f969c-129">Удаление индекса при помощи конструктора таблиц</span><span class="sxs-lookup"><span data-stu-id="f969c-129">To delete an index using Table Designer</span></span>  
  
1.  <span data-ttu-id="f969c-130">В обозревателе объектов разверните базу данных, содержащую таблицу, в которой необходимо удалить индекс.</span><span class="sxs-lookup"><span data-stu-id="f969c-130">In Object Explorer, expand the database that contains the table on which you want to delete an index.</span></span>  
  
2.  <span data-ttu-id="f969c-131">Разверните папку **Таблицы**.</span><span class="sxs-lookup"><span data-stu-id="f969c-131">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="f969c-132">Правой кнопкой мыши щелкните таблицу, содержащую индекс, который необходимо удалить, и выберите «Конструктор».</span><span class="sxs-lookup"><span data-stu-id="f969c-132">Right-click the table that contains the index you want to delete and click Design.</span></span>  
  
4.  <span data-ttu-id="f969c-133">В меню **Конструктор таблиц** выберите пункт **Индексы и ключи**.</span><span class="sxs-lookup"><span data-stu-id="f969c-133">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
5.  <span data-ttu-id="f969c-134">В диалоговом окне **Индексы и ключи** выберите индекс, который хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="f969c-134">In the **Indexes/Keys** dialog box, select the index you want to delete.</span></span>  
  
6.  <span data-ttu-id="f969c-135">Щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="f969c-135">Click **Delete**.</span></span>  
  
7.  <span data-ttu-id="f969c-136">Щелкните **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="f969c-136">Click **Close**.</span></span>  
  
8.  <span data-ttu-id="f969c-137">В меню **Файл** выберите пункт **Сохранить**_имя_таблицы_.</span><span class="sxs-lookup"><span data-stu-id="f969c-137">On the **File** menu, select **Save**_table_name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f969c-138">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f969c-138">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-an-index"></a><span data-ttu-id="f969c-139">Удаление индекса</span><span class="sxs-lookup"><span data-stu-id="f969c-139">To delete an index</span></span>  
  
1.  <span data-ttu-id="f969c-140">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f969c-140">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f969c-141">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="f969c-141">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f969c-142">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="f969c-142">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- delete the IX_ProductVendor_BusinessEntityID index  
    -- from the Purchasing.ProductVendor table  
    DROP INDEX IX_ProductVendor_BusinessEntityID   
        ON Purchasing.ProductVendor;  
    GO  
    ```  
  
 <span data-ttu-id="f969c-143">Дополнительные сведения см. в статье [DROP INDEX (Transact-SQL)](/sql/t-sql/statements/drop-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f969c-143">For more information, see [DROP INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-index-transact-sql).</span></span>  
  
  
