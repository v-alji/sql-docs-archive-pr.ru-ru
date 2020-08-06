---
title: Подготовка данных для отображения в области данных табликса (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: fbb00dc6-7887-480c-b771-cab6fecb8dcc
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 72ac150f2dcd227b1e3afb624a5ca5866fb4c360
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667572"
---
# <a name="preparing-data-for-display-in-a-tablix-data-region-report-builder-and-ssrs"></a><span data-ttu-id="bb44a-102">Подготовка данных для отображения в области данных табликса (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="bb44a-102">Preparing Data for Display in a Tablix Data Region (Report Builder and SSRS)</span></span>
  <span data-ttu-id="bb44a-103">Область данных табликса отображает данные из набора данных.</span><span class="sxs-lookup"><span data-stu-id="bb44a-103">A tablix data region displays data from a dataset.</span></span> <span data-ttu-id="bb44a-104">Существует возможность как просматривать все данные, полученные из набора данных, так и создавать фильтры, позволяющие просматривать подмножество этих данных.</span><span class="sxs-lookup"><span data-stu-id="bb44a-104">You can view all the data retrieved for the dataset or you can create filters so that you see only a subset of the data.</span></span> <span data-ttu-id="bb44a-105">Можно также добавить условные выражения для заполнения пустых значений или изменить запрос к набору данных, включив в него столбцы, определяющие порядок сортировки для существующих столбцов.</span><span class="sxs-lookup"><span data-stu-id="bb44a-105">You can also add conditional expressions to fill in null values or modify the query for a dataset to include columns that define the sort order for an existing column.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="working-with-nulls-and-blanks-in-field-values"></a><span data-ttu-id="bb44a-106">Работа с пустыми значениями и значениями NULL в полях</span><span class="sxs-lookup"><span data-stu-id="bb44a-106">Working with Nulls and Blanks in Field Values</span></span>  
 <span data-ttu-id="bb44a-107">Данные коллекции полей набора данных включают все значения, полученные из источника данных во время выполнения, в том числе значения NULL и пустые значения.</span><span class="sxs-lookup"><span data-stu-id="bb44a-107">Data for the field collection in a dataset includes all values retrieved from the data source at run time, including null values and blanks.</span></span> <span data-ttu-id="bb44a-108">Обычно эти два значения неотличимы.</span><span class="sxs-lookup"><span data-stu-id="bb44a-108">Normally null values and blanks are indistinguishable.</span></span> <span data-ttu-id="bb44a-109">В большинстве случаев это приемлемо.</span><span class="sxs-lookup"><span data-stu-id="bb44a-109">In most cases, this is the desired behavior.</span></span> <span data-ttu-id="bb44a-110">Например, числовые агрегатные функции [Sum](report-builder-functions-sum-function.md) и [Avg](report-builder-functions-avg-function.md) не учитывают значения NULL.</span><span class="sxs-lookup"><span data-stu-id="bb44a-110">For example, Numeric aggregate functions like [Sum](report-builder-functions-sum-function.md) and [Avg](report-builder-functions-avg-function.md) ignore null values.</span></span> <span data-ttu-id="bb44a-111">Дополнительные сведения см. в разделах [Справочник по агрегатным функциям (построитель отчетов и службы SSRS)](report-builder-functions-aggregate-functions-reference.md).</span><span class="sxs-lookup"><span data-stu-id="bb44a-111">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md).</span></span>  
  
 <span data-ttu-id="bb44a-112">Если значения NULL необходимо обрабатывать каким-либо иным образом, то можно воспользоваться условными выражениями или пользовательским кодом для замены NULL другим значением.</span><span class="sxs-lookup"><span data-stu-id="bb44a-112">If you do want to handle null values differently, you can use conditional expressions or custom code to substitute a custom value for the null value.</span></span> <span data-ttu-id="bb44a-113">Например, следующее выражение производит подстановку текста `Null` вместо значений NULL в столбце `[Size]`.</span><span class="sxs-lookup"><span data-stu-id="bb44a-113">For example, the following expression substitutes the text `Null` wherever a null value occurs in the field `[Size]`.</span></span>  
  
```  
=IIF(Fields!Size.Value IS NOTHING,"Null",Fields!Size.Value)  
```  
  
 <span data-ttu-id="bb44a-114">Дополнительные сведения об обработке значений NULL при получении данных из источника данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] при помощи запросов [!INCLUDE[tsql](../../includes/tsql-md.md)] см. в разделах «Значения NULL» и «Значения NULL и соединения» в документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в [электронной документации по SQL Server](https://go.microsoft.com/fwlink/?linkid=120955).</span><span class="sxs-lookup"><span data-stu-id="bb44a-114">For more information about eliminating nulls in your data before retrieving the data from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data source using [!INCLUDE[tsql](../../includes/tsql-md.md)] queries, see "Null Values" and "Null Values and Joins" in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] documentation in [SQL Server Books Online](https://go.microsoft.com/fwlink/?linkid=120955).</span></span>  
  
## <a name="handling-null-field-names"></a><span data-ttu-id="bb44a-115">Обработка имен полей со значением NULL</span><span class="sxs-lookup"><span data-stu-id="bb44a-115">Handling Null Field Names</span></span>  
 <span data-ttu-id="bb44a-116">Прекрасным решением будет проверка на значения NULL в выражении, поскольку в таком случае поле будет существовать в результирующем наборе запроса.</span><span class="sxs-lookup"><span data-stu-id="bb44a-116">Testing for null values in an expression is fine as long as the field itself exists in the query result set.</span></span> <span data-ttu-id="bb44a-117">В пользовательском коде придется во время выполнения проверять, существует ли поле в коллекции полей, возвращенных источником данных.</span><span class="sxs-lookup"><span data-stu-id="bb44a-117">From custom code, you can test whether the field itself is present in the collection fields returned from the data source at run time.</span></span> <span data-ttu-id="bb44a-118">Дополнительные сведения см. в разделе [Ссылки на коллекцию полей набора данных (построитель отчетов и службы SSRS)](built-in-collections-dataset-fields-collection-references-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="bb44a-118">For more information, see [Dataset Fields Collection References &#40;Report Builder and SSRS&#41;](built-in-collections-dataset-fields-collection-references-report-builder.md).</span></span>  
  
## <a name="adding-a-sort-order-column"></a><span data-ttu-id="bb44a-119">Добавление столбца порядка сортировки</span><span class="sxs-lookup"><span data-stu-id="bb44a-119">Adding a Sort Order Column</span></span>  
 <span data-ttu-id="bb44a-120">По умолчанию значения поля набора данных сортируются по алфавиту.</span><span class="sxs-lookup"><span data-stu-id="bb44a-120">By default, you can alphabetically sort values in a dataset field.</span></span> <span data-ttu-id="bb44a-121">Чтобы сортировка выполнялась в другом порядке, необходимо добавить в набор данных новый столбец, определяющий необходимый порядок сортировки области данных.</span><span class="sxs-lookup"><span data-stu-id="bb44a-121">To sort in a different order, you can add a new column to your dataset that defines the sort order you want in a data region.</span></span> <span data-ttu-id="bb44a-122">Например, чтобы выполнить сортировку по полю `[Color]` таким образом, чтобы сначала шли белые и черные предметы, необходимо добавить столбец `[ColorSortOrder]`, показанный в следующем запросе.</span><span class="sxs-lookup"><span data-stu-id="bb44a-122">For example, to sort on the field `[Color]` and sort white and black items first, you can add a column `[ColorSortOrder]`, shown in the following query:</span></span>  
  
```  
SELECT ProductID, p.Name, Color,  
   CASE  
      WHEN p.Color = 'White' THEN 1  
      WHEN p.Color = 'Black' THEN 2  
      WHEN p.Color = 'Blue' THEN 3  
      WHEN p.Color = 'Yellow' THEN 4  
      ELSE 5  
   END As ColorSortOrder  
FROM Production.Product p  
```  
  
 <span data-ttu-id="bb44a-123">Чтобы отсортировать область данных таблицы в соответствии с этим порядком сортировки, задайте для группы сведений выражение `=Fields!ColorSortOrder.Value`.</span><span class="sxs-lookup"><span data-stu-id="bb44a-123">To sort a table data region according to this sort order, set the sort expression on the detail group to `=Fields!ColorSortOrder.Value`.</span></span> <span data-ttu-id="bb44a-124">Дополнительные сведения см. в разделе [Сортировка данных в области данных (построитель отчетов и службы SSRS)](sort-data-in-a-data-region-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="bb44a-124">For more information, see [Sort Data in a Data Region &#40;Report Builder and SSRS&#41;](sort-data-in-a-data-region-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb44a-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="bb44a-125">See Also</span></span>  
 <span data-ttu-id="bb44a-126">[Коллекция полей набора данных (построитель отчетов и службы SSRS)](../report-data/dataset-fields-collection-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bb44a-126">[Dataset Fields Collection &#40;Report Builder and SSRS&#41;](../report-data/dataset-fields-collection-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="bb44a-127">[Выражения (построитель отчетов и службы SSRS)](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bb44a-127">[Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="bb44a-128">Фильтрация, группирование и сортировка данных (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="bb44a-128">Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;</span></span>](filter-group-and-sort-data-report-builder-and-ssrs.md)  
  
  
