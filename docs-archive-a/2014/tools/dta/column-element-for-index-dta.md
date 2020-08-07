---
title: Элемент Column для index (DTA) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Column element
ms.assetid: ba9fac20-26bd-4333-940e-842c15241b46
author: stevestein
ms.author: sstein
ms.openlocfilehash: 67853dc7d1193d3a0f80e56023846bc55a20bdaa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727682"
---
# <a name="column-element-for-index-dta"></a><span data-ttu-id="13349-102">Элемент Column описания индекса (DTA)</span><span class="sxs-lookup"><span data-stu-id="13349-102">Column Element for Index (DTA)</span></span>
  <span data-ttu-id="13349-103">Указывает столбцы, по которым создается индекс для пользовательской конфигурации.</span><span class="sxs-lookup"><span data-stu-id="13349-103">Specifies the columns on which the index is created for a user-specified configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13349-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="13349-104">Syntax</span></span>  
  
```  
  
<Create>  
  <Index>  
    <Name>...</Name>  
    <Column [Type | SortOrder]>  
     ...code removed here...  
     </Column>  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="13349-105">Атрибуты элемента</span><span class="sxs-lookup"><span data-stu-id="13349-105">Element Attributes</span></span>  
  
|<span data-ttu-id="13349-106">Атрибут столбца</span><span class="sxs-lookup"><span data-stu-id="13349-106">Column Attribute</span></span>|<span data-ttu-id="13349-107">Описание</span><span class="sxs-lookup"><span data-stu-id="13349-107">Description</span></span>|  
|----------------------|-----------------|  
|`Type`|<span data-ttu-id="13349-108">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="13349-108">Optional.</span></span> <span data-ttu-id="13349-109">Указывает тип столбца индекса.</span><span class="sxs-lookup"><span data-stu-id="13349-109">Specifies the index column type.</span></span> <span data-ttu-id="13349-110">Используйте тип данных **string** для указания этого атрибута при помощи следующих допустимых значений:</span><span class="sxs-lookup"><span data-stu-id="13349-110">Use a **string** data type to specify this attribute with one of the following allowed values:</span></span><br /><br /> <span data-ttu-id="13349-111">`KeyColumn`:</span><span class="sxs-lookup"><span data-stu-id="13349-111">`KeyColumn`:</span></span><br />                  <span data-ttu-id="13349-112">Указывает, что на столбец ссылается ключ индекса.</span><span class="sxs-lookup"><span data-stu-id="13349-112">Specifies that the column is referenced by an index key.</span></span> <span data-ttu-id="13349-113">Для установки этого атрибута используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="13349-113">Use the following syntax to set this attribute:</span></span><br />`<Column Type="KeyColumn">`<br /><span data-ttu-id="13349-114">Дополнительные сведения о ключевых столбцах см. в разделе [Описания кластеризованных и некластеризованных индексов](../../relational-databases/indexes/clustered-and-nonclustered-indexes-described.md).</span><span class="sxs-lookup"><span data-stu-id="13349-114">For more information about key columns, see [Clustered and Nonclustered Indexes Described](../../relational-databases/indexes/clustered-and-nonclustered-indexes-described.md).</span></span><br /><br /> <span data-ttu-id="13349-115">`IncludedColumn`: Указывает, что столбец является включенным столбцом (а не ключевым столбцом).</span><span class="sxs-lookup"><span data-stu-id="13349-115">`IncludedColumn`: Specifies that the column is an included column (instead of a key column).</span></span> <span data-ttu-id="13349-116">Для установки этого атрибута используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="13349-116">Use the following syntax to set this attribute:</span></span><br />`<Column Type="IncludedColumn">`<br /><span data-ttu-id="13349-117">Дополнительные сведения о включенных столбцах см. в разделе [Создание индексов с включенными столбцами](../../relational-databases/indexes/create-indexes-with-included-columns.md).</span><span class="sxs-lookup"><span data-stu-id="13349-117">For more information about included columns, see [Create Indexes with Included Columns](../../relational-databases/indexes/create-indexes-with-included-columns.md).</span></span>|  
|`SortOrder`|<span data-ttu-id="13349-118">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="13349-118">Optional.</span></span> <span data-ttu-id="13349-119">Указывает порядок сортировки столбца.</span><span class="sxs-lookup"><span data-stu-id="13349-119">Specifies the sorting order of the column.</span></span> <span data-ttu-id="13349-120">Используйте тип данных **string** для указания порядка сортировки **по возрастанию** или **по убыванию** , как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="13349-120">Use a **string** data type to specify either an **"Ascending"** or **"Descending"** sorting order as follows:</span></span><br /><br /> `<Column SortOrder="Ascending">`|  
  
## <a name="element-characteristics"></a><span data-ttu-id="13349-121">Характеристики элемента</span><span class="sxs-lookup"><span data-stu-id="13349-121">Element Characteristics</span></span>  
  
|<span data-ttu-id="13349-122">Характеристика</span><span class="sxs-lookup"><span data-stu-id="13349-122">Characteristic</span></span>|<span data-ttu-id="13349-123">Описание</span><span class="sxs-lookup"><span data-stu-id="13349-123">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="13349-124">**Тип данных и длина**</span><span class="sxs-lookup"><span data-stu-id="13349-124">**Data type and length**</span></span>|<span data-ttu-id="13349-125">Нет.</span><span class="sxs-lookup"><span data-stu-id="13349-125">None.</span></span>|  
|<span data-ttu-id="13349-126">**Значение по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="13349-126">**Default value**</span></span>|<span data-ttu-id="13349-127">Нет.</span><span class="sxs-lookup"><span data-stu-id="13349-127">None.</span></span>|  
|<span data-ttu-id="13349-128">**Наличие**</span><span class="sxs-lookup"><span data-stu-id="13349-128">**Occurrence**</span></span>|<span data-ttu-id="13349-129">Для элемента `Index` можно задать не более 1 024 столбцов.</span><span class="sxs-lookup"><span data-stu-id="13349-129">Can specify up to 1024 columns for the `Index` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="13349-130">Связи элемента</span><span class="sxs-lookup"><span data-stu-id="13349-130">Element Relationships</span></span>  
  
|<span data-ttu-id="13349-131">Связь</span><span class="sxs-lookup"><span data-stu-id="13349-131">Relationship</span></span>|<span data-ttu-id="13349-132">Элементы</span><span class="sxs-lookup"><span data-stu-id="13349-132">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="13349-133">**Родительский элемент**</span><span class="sxs-lookup"><span data-stu-id="13349-133">**Parent element**</span></span>|[<span data-ttu-id="13349-134">Элемент Index (DTA)</span><span class="sxs-lookup"><span data-stu-id="13349-134">Index Element &#40;DTA&#41;</span></span>](index-element-dta.md)|  
|<span data-ttu-id="13349-135">**Дочерние элементы**</span><span class="sxs-lookup"><span data-stu-id="13349-135">**Child elements**</span></span>|[<span data-ttu-id="13349-136">Элемент Name описания столбца (DTA)</span><span class="sxs-lookup"><span data-stu-id="13349-136">Name Element for Column &#40;DTA&#41;</span></span>](name-element-for-column-dta.md)|  
  
## <a name="example"></a><span data-ttu-id="13349-137">Пример</span><span class="sxs-lookup"><span data-stu-id="13349-137">Example</span></span>  
 <span data-ttu-id="13349-138">Пример использования этого элемента см. в разделе [Образец входного XML-файла с пользовательской конфигурацией (DTA)](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="13349-138">For a usage example of this element, see the [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13349-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="13349-139">See Also</span></span>  
 [<span data-ttu-id="13349-140">Справочник по входным XML-файлам (помощник по настройке ядра СУБД)</span><span class="sxs-lookup"><span data-stu-id="13349-140">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
