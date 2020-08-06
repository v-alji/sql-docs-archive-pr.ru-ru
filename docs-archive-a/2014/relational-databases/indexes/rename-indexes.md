---
title: Переименование индексов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- renaming indexes
- index names [SQL Server]
- indexes [SQL Server], renaming
ms.assetid: d3d612a1-ea1b-4d99-85d2-0a2ad54f4b0e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 184d6e20f7857c5ea3535e77e21a0630ffc7b678
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668307"
---
# <a name="rename-indexes"></a><span data-ttu-id="f67c0-102">Переименование индексов</span><span class="sxs-lookup"><span data-stu-id="f67c0-102">Rename Indexes</span></span>
  <span data-ttu-id="f67c0-103">В этом разделе описывается процедура переименования индекса в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f67c0-103">This topic describes how to rename an index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="f67c0-104">При переименовании индекса его текущее имя заменяется на предоставленное новое.</span><span class="sxs-lookup"><span data-stu-id="f67c0-104">Renaming an index replaces the current index name with the new name that you provide.</span></span> <span data-ttu-id="f67c0-105">Указанное имя должно быть уникальным в рамках таблицы или представления.</span><span class="sxs-lookup"><span data-stu-id="f67c0-105">The specified name must be unique within the table or view.</span></span> <span data-ttu-id="f67c0-106">Например, две таблицы могут иметь индекс с именем **XPK_1**, но для одной таблицы не может быть двух индексов с именем **XPK_1**.</span><span class="sxs-lookup"><span data-stu-id="f67c0-106">For example, two tables can have an index named **XPK_1**, but the same table cannot have two indexes named **XPK_1**.</span></span> <span data-ttu-id="f67c0-107">Нельзя создавать индекс с тем же именем, что и существующий отключенный индекс.</span><span class="sxs-lookup"><span data-stu-id="f67c0-107">You cannot create an index with the same name as an existing disabled index.</span></span> <span data-ttu-id="f67c0-108">Переименование индекса не приводит к его перестройке.</span><span class="sxs-lookup"><span data-stu-id="f67c0-108">Renaming an index does not cause the index to be rebuilt.</span></span>  
  
 <span data-ttu-id="f67c0-109">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="f67c0-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f67c0-110">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="f67c0-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f67c0-111">Ограничения</span><span class="sxs-lookup"><span data-stu-id="f67c0-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="f67c0-112">Безопасность</span><span class="sxs-lookup"><span data-stu-id="f67c0-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f67c0-113">**Переименование индекса с помощью различных средств.**</span><span class="sxs-lookup"><span data-stu-id="f67c0-113">**To rename an index, using:**</span></span>  
  
     [<span data-ttu-id="f67c0-114">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f67c0-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="f67c0-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f67c0-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f67c0-116">Перед началом</span><span class="sxs-lookup"><span data-stu-id="f67c0-116">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f67c0-117">Ограничения</span><span class="sxs-lookup"><span data-stu-id="f67c0-117">Limitations and Restrictions</span></span>  
 <span data-ttu-id="f67c0-118">При создании ограничения PRIMARY KEY или UNIQUE для таблицы автоматически создается индекс с таким же именем, что и имя ограничения.</span><span class="sxs-lookup"><span data-stu-id="f67c0-118">When you create a PRIMARY KEY or UNIQUE constraint on a table, an index with the same name as the constraint is automatically created for the table.</span></span> <span data-ttu-id="f67c0-119">Поскольку имена индексов должны быть уникальны в пределах таблицы, нельзя создавать или переименовывать индекс, присваивая ему такое же имя, что и у существующего в таблице ограничения PRIMARY KEY или UNIQUE.</span><span class="sxs-lookup"><span data-stu-id="f67c0-119">Because index names must be unique within the table, you cannot create or rename an index to have the same name as an existing PRIMARY KEY or UNIQUE constraint on the table.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f67c0-120">безопасность</span><span class="sxs-lookup"><span data-stu-id="f67c0-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f67c0-121">Permissions</span><span class="sxs-lookup"><span data-stu-id="f67c0-121">Permissions</span></span>  
 <span data-ttu-id="f67c0-122">Требуется разрешение ALTER для индекса.</span><span class="sxs-lookup"><span data-stu-id="f67c0-122">Requires ALTER permission on the index.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f67c0-123">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f67c0-123">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-an-index-by-using-the-table-designer"></a><span data-ttu-id="f67c0-124">Переименование индекса при помощи конструктора таблиц</span><span class="sxs-lookup"><span data-stu-id="f67c0-124">To rename an index by using the Table Designer</span></span>  
  
1.  <span data-ttu-id="f67c0-125">В обозревателе объектов щелкните знак «плюс», чтобы развернуть базу данных, содержащую таблицу, в которой необходимо переименовать индекс.</span><span class="sxs-lookup"><span data-stu-id="f67c0-125">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to rename an index.</span></span>  
  
2.  <span data-ttu-id="f67c0-126">Чтобы развернуть папку **Таблицы** , щелкните значок «плюс».</span><span class="sxs-lookup"><span data-stu-id="f67c0-126">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="f67c0-127">Щелкните правой кнопкой мыши таблицу, в которой нужно переименовать индекс, и выберите пункт **Конструктор**.</span><span class="sxs-lookup"><span data-stu-id="f67c0-127">Right-click the table on which you want to rename an index and select **Design**.</span></span>  
  
4.  <span data-ttu-id="f67c0-128">В меню **Конструктор таблиц** выберите пункт **Индексы и ключи**.</span><span class="sxs-lookup"><span data-stu-id="f67c0-128">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
5.  <span data-ttu-id="f67c0-129">В текстовом поле **Выбранный первичный (уникальный) ключ или индекс** выберите индекс, который нужно переименовать.</span><span class="sxs-lookup"><span data-stu-id="f67c0-129">Select the index you want to rename in the **Selected Primary/Unique Key or Index** text box.</span></span>  
  
6.  <span data-ttu-id="f67c0-130">В сетке выберите **Имя** и введите новое имя в текстовое поле.</span><span class="sxs-lookup"><span data-stu-id="f67c0-130">In the grid, click **Name** and type a new name into the text box.</span></span>  
  
7.  <span data-ttu-id="f67c0-131">Щелкните **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="f67c0-131">Click **Close**.</span></span>  
  
8.  <span data-ttu-id="f67c0-132">В меню **Файл** выберите пункт **Сохранить**_имя_таблицы_.</span><span class="sxs-lookup"><span data-stu-id="f67c0-132">On the **File** menu, click **Save**_table_name_.</span></span>  
  
#### <a name="to-rename-an-index-by-using-object-explorer"></a><span data-ttu-id="f67c0-133">Переименование индекса при помощи обозревателя объектов</span><span class="sxs-lookup"><span data-stu-id="f67c0-133">To rename an index by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="f67c0-134">В обозревателе объектов щелкните знак «плюс», чтобы развернуть базу данных, содержащую таблицу, в которой необходимо переименовать индекс.</span><span class="sxs-lookup"><span data-stu-id="f67c0-134">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to rename an index.</span></span>  
  
2.  <span data-ttu-id="f67c0-135">Чтобы развернуть папку **Таблицы** , щелкните значок «плюс».</span><span class="sxs-lookup"><span data-stu-id="f67c0-135">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="f67c0-136">Щелкните знак «плюс», чтобы развернуть таблицу, в которой необходимо переименовать индекс.</span><span class="sxs-lookup"><span data-stu-id="f67c0-136">Click the plus sign to expand the table on which you want to rename an index.</span></span>  
  
4.  <span data-ttu-id="f67c0-137">Чтобы развернуть папку **Индексы** , щелкните знак «плюс» (+).</span><span class="sxs-lookup"><span data-stu-id="f67c0-137">Click the plus sign to expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="f67c0-138">Щелкните правой кнопкой мыши индекс, который нужно переименовать, и выберите пункт **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="f67c0-138">Right-click the index you want to rename and select **Rename**.</span></span>  
  
6.  <span data-ttu-id="f67c0-139">Введите новое имя индекса и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="f67c0-139">Type the index's new name and press Enter.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f67c0-140">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f67c0-140">Using Transact-SQL</span></span>  
  
#### <a name="to-rename-an-index"></a><span data-ttu-id="f67c0-141">Переименование индекса</span><span class="sxs-lookup"><span data-stu-id="f67c0-141">To rename an index</span></span>  
  
1.  <span data-ttu-id="f67c0-142">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f67c0-142">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f67c0-143">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="f67c0-143">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f67c0-144">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="f67c0-144">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    --Renames the IX_ProductVendor_VendorID index on the Purchasing.ProductVendor table to IX_VendorID.   
  
    EXEC sp_rename N'Purchasing.ProductVendor.IX_ProductVendor_VendorID', N'IX_VendorID', N'INDEX';   
    GO  
    ```  
  
 <span data-ttu-id="f67c0-145">Дополнительные сведения см. в разделе [sp_rename (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f67c0-145">For more information, see  [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span></span>  
  
  
