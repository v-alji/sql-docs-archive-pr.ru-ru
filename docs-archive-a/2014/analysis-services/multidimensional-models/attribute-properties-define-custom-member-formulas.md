---
title: Определение нестандартных формул элементов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- members [Analysis Services], custom
- custom rollup formulas [Analysis Services]
- MDX [Analysis Services], custom rollup formulas
- custom member formulas [Analysis Services]
ms.assetid: 258304e2-d900-4013-97e3-871f51dfdce2
author: minewiskan
ms.author: owend
ms.openlocfilehash: 51649bea0c4134971b342b779c778b857343e62b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750340"
---
# <a name="define-custom-member-formulas"></a><span data-ttu-id="e96b9-102">Определение нестандартных формул элементов</span><span class="sxs-lookup"><span data-stu-id="e96b9-102">Define Custom Member Formulas</span></span>
  <span data-ttu-id="e96b9-103">Нестандартные формулы элемента — это многомерные выражения, предоставляющие значения для элементов указанного атрибута.</span><span class="sxs-lookup"><span data-stu-id="e96b9-103">You can define a Multidimensional Expressions (MDX) expression, called a custom member formula, to supply the values for the members of a specified attribute.</span></span> <span data-ttu-id="e96b9-104">Столбец таблицы из представления источников данных содержит выражение для каждого элемента атрибута, предоставляющее значение для этого элемента.</span><span class="sxs-lookup"><span data-stu-id="e96b9-104">A column in a table from a data source view provides, for each member in an attribute, the expression used to supply the value for that member.</span></span>  
  
 <span data-ttu-id="e96b9-105">Нестандартные формулы элементов определяют значения ячеек, которые связаны с элементами, и заменяют агрегатные функции мер.</span><span class="sxs-lookup"><span data-stu-id="e96b9-105">Custom member formulas determine the cell values that are associated with members and override the aggregate functions of measures.</span></span> <span data-ttu-id="e96b9-106">Нестандартные формулы элементов записаны в многомерных выражениях.</span><span class="sxs-lookup"><span data-stu-id="e96b9-106">Custom member formulas are written in MDX.</span></span> <span data-ttu-id="e96b9-107">Каждая нестандартная формула элемента применяется к одному элементу.</span><span class="sxs-lookup"><span data-stu-id="e96b9-107">Each custom member formula applies to a single member.</span></span> <span data-ttu-id="e96b9-108">Нестандартные формулы элементов хранятся в таблице измерения или в другой таблице, имеющей связь по внешнему ключу с таблицей измерения.</span><span class="sxs-lookup"><span data-stu-id="e96b9-108">Custom member formulas are stored in the dimension table or in another table that has a foreign key relationship with the dimension table.</span></span>  
  
 <span data-ttu-id="e96b9-109">Свойство атрибута `CustomRollupColumn` указывает столбец, содержащий нестандартные формулы элементов для элементов атрибута.</span><span class="sxs-lookup"><span data-stu-id="e96b9-109">The `CustomRollupColumn` property on an attribute specifies the column that contains custom member formulas for members of the attribute.</span></span> <span data-ttu-id="e96b9-110">Если строка в столбце является пустой, значение ячейки для элемента возвращается обычным способом.</span><span class="sxs-lookup"><span data-stu-id="e96b9-110">If a row in the column is empty, the cell value for the member is returned normally.</span></span> <span data-ttu-id="e96b9-111">Если формула в столбце не является допустимой, при извлечении значения ячейки, которая использует элемент, возникает ошибка времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="e96b9-111">If the formula in the column is not valid, a run-time error occurs whenever a cell value that uses the member is retrieved.</span></span>  
  
 <span data-ttu-id="e96b9-112">Перед указанием нестандартной формулы элемента для атрибута убедитесь, что таблица измерения, содержащая атрибут, или непосредственно связанная таблица, содержит строковый столбец для хранения нестандартных формул элементов.</span><span class="sxs-lookup"><span data-stu-id="e96b9-112">Before you can specify custom member formulas for an attribute, make sure that the dimension table that contains the attribute, or a directly related table, has a string column to store the custom member formulas.</span></span> <span data-ttu-id="e96b9-113">В этом случае можно либо задать `CustomRollupColumn` свойство для атрибута вручную, либо воспользоваться расширением «установка нестандартной формулы элемента» мастера бизнес-аналитики, чтобы включить нестандартную формулу элемента для атрибута.</span><span class="sxs-lookup"><span data-stu-id="e96b9-113">If this is the case, you can either set the `CustomRollupColumn` property on an attribute manually or use the Set Custom Member Formula enhancement of the Business Intelligence Wizard to enable a custom member formula on an attribute.</span></span> <span data-ttu-id="e96b9-114">Дополнительные сведения об использовании этой возможности см. в разделе [Настройка нестандартных формул элементов для атрибутов в измерении](bi-wizard-custom-member-formulas-for-attributes-in-a-dimension.md).</span><span class="sxs-lookup"><span data-stu-id="e96b9-114">For more information about how to use this enhancement, see [Set Custom Member Formulas for Attributes in a Dimension](bi-wizard-custom-member-formulas-for-attributes-in-a-dimension.md).</span></span>  
  
## <a name="evaluating-custom-member-formulas"></a><span data-ttu-id="e96b9-115">Вычисление нестандартных формул элементов</span><span class="sxs-lookup"><span data-stu-id="e96b9-115">Evaluating Custom Member Formulas</span></span>  
 <span data-ttu-id="e96b9-116">Нестандартные формулы элементов отличаются от вычисляемых элементов.</span><span class="sxs-lookup"><span data-stu-id="e96b9-116">Custom member formulas differ from calculated members.</span></span> <span data-ttu-id="e96b9-117">Нестандартные формулы элементов применяются к элементам, которые содержатся в таблице измерения, и только предоставляют значение для них.</span><span class="sxs-lookup"><span data-stu-id="e96b9-117">Custom member formulas apply to members that exist in dimension tables, and only provide the value of the member.</span></span> <span data-ttu-id="e96b9-118">В отличие от пользовательских формул, вычисляемые элементы не хранятся в таблицах измерения, а выражения вычисляемых элементов определяют данные и метаданные дополнительных элементов измерения или иерархии.</span><span class="sxs-lookup"><span data-stu-id="e96b9-118">In contrast, calculated members are not stored in dimension tables, and calculated member expressions define both data and metadata for additional members included in a dimension or hierarchy.</span></span>  
  
 <span data-ttu-id="e96b9-119">Нестандартные формулы элементов заменяют агрегатные функции, связанные с мерами.</span><span class="sxs-lookup"><span data-stu-id="e96b9-119">Custom member formulas override the aggregate functions associated with measures.</span></span> <span data-ttu-id="e96b9-120">Например, перед тем как была задана нестандартная формула элемента, мера, использующая агрегатную функцию `Sum`, принимала следующие значения для элементов измерения «Время»:</span><span class="sxs-lookup"><span data-stu-id="e96b9-120">For example, before a custom member formula is specified, a measure using the `Sum` aggregate function has the following values for the following members of the Time dimension:</span></span>  
  
-   <span data-ttu-id="e96b9-121">2003: 2100</span><span class="sxs-lookup"><span data-stu-id="e96b9-121">2003: 2100</span></span>  
  
    -   <span data-ttu-id="e96b9-122">Квартал 1: 700</span><span class="sxs-lookup"><span data-stu-id="e96b9-122">Quarter 1: 700</span></span>  
  
    -   <span data-ttu-id="e96b9-123">Квартал 2: 500</span><span class="sxs-lookup"><span data-stu-id="e96b9-123">Quarter 2: 500</span></span>  
  
    -   <span data-ttu-id="e96b9-124">Квартал 3: 100</span><span class="sxs-lookup"><span data-stu-id="e96b9-124">Quarter 3: 100</span></span>  
  
    -   <span data-ttu-id="e96b9-125">Квартал 4: 800</span><span class="sxs-lookup"><span data-stu-id="e96b9-125">Quarter 4: 800</span></span>  
  
-   <span data-ttu-id="e96b9-126">2004: 1500</span><span class="sxs-lookup"><span data-stu-id="e96b9-126">2004: 1500</span></span>  
  
    -   <span data-ttu-id="e96b9-127">Квартал 1: 600</span><span class="sxs-lookup"><span data-stu-id="e96b9-127">Quarter 1: 600</span></span>  
  
    -   <span data-ttu-id="e96b9-128">Квартал 2: 200</span><span class="sxs-lookup"><span data-stu-id="e96b9-128">Quarter 2: 200</span></span>  
  
    -   <span data-ttu-id="e96b9-129">Квартал 3: 300</span><span class="sxs-lookup"><span data-stu-id="e96b9-129">Quarter 3: 300</span></span>  
  
    -   <span data-ttu-id="e96b9-130">Квартал 4: 400</span><span class="sxs-lookup"><span data-stu-id="e96b9-130">Quarter 4: 400</span></span>  
  
 <span data-ttu-id="e96b9-131">После задания нестандартной формулы элемента значение элемента стало определяться формулой пользовательской свертки.</span><span class="sxs-lookup"><span data-stu-id="e96b9-131">With a custom member formula, the value of the member is instead supplied by the custom rollup formula.</span></span> <span data-ttu-id="e96b9-132">Например, следующая нестандартная формула элемента предоставляет значение 450 для дочернего элемента «Квартал 4» элемента «2004» измерения Time.</span><span class="sxs-lookup"><span data-stu-id="e96b9-132">For example, the following custom member formula can be used to supply the value for the Quarter 4 child member of the 2004 member in the Time dimension as 450.</span></span>  
  
```  
Time.[Quarter 3] * 1.5  
```  
  
 <span data-ttu-id="e96b9-133">Нестандартные формулы элементов хранятся в столбце таблицы измерения.</span><span class="sxs-lookup"><span data-stu-id="e96b9-133">Custom member formulas are stored in a column of the dimension table.</span></span> <span data-ttu-id="e96b9-134">Чтобы включить формулы пользовательской свертки, необходимо установить свойство `CustomRollupColumn` нужного атрибута.</span><span class="sxs-lookup"><span data-stu-id="e96b9-134">You enable custom rollup formulas by setting the `CustomRollupColumn` property on an attribute.</span></span>  
  
 <span data-ttu-id="e96b9-135">Чтобы применить многомерное выражение ко всем элементам атрибута, создайте в таблице измерения именованное вычисление, возвращающее многомерное выражение в виде символьной строки.</span><span class="sxs-lookup"><span data-stu-id="e96b9-135">To apply a single MDX expression to all members of an attribute, create a named calculation on the dimension table that returns an MDX expression as a literal string.</span></span> <span data-ttu-id="e96b9-136">Затем присвойте имя вычисления свойству `CustomRollupColumn` нужного атрибута.</span><span class="sxs-lookup"><span data-stu-id="e96b9-136">Then, specify the named calculation with the `CustomRollupColumn` property setting on the attribute that you want to configure.</span></span> <span data-ttu-id="e96b9-137">Именованное вычисление — это столбец в таблице представления источника дынных, который возвращает значения строк, определенные выражением SQL.</span><span class="sxs-lookup"><span data-stu-id="e96b9-137">A named calculation is a column in a data source view table that returns row values defined by a SQL expression.</span></span> <span data-ttu-id="e96b9-138">Дополнительные сведения о составлении именованных вычислений см. в разделе [Определение именованных вычислений в представлении источника данных (службы Analysis Services)](define-named-calculations-in-a-data-source-view-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="e96b9-138">For more information about constructing named calculations, see [Define Named Calculations in a Data Source View &#40;Analysis Services&#41;](define-named-calculations-in-a-data-source-view-analysis-services.md)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e96b9-139">Чтобы применить многомерное выражение не ко всем элементам атрибута, а только к членам определенного уровня, необходимо определить выражение в виде скрипта многомерного выражения для данного уровня.</span><span class="sxs-lookup"><span data-stu-id="e96b9-139">To apply an MDX expression to members of a particular level instead of to members of all levels based on a particular attribute, you can define the expression as an MDX script on the level.</span></span> <span data-ttu-id="e96b9-140">Дополнительные сведения см. в статье [Основные принципы создания скриптов многомерных выражений (службы Analysis Services)](mdx/mdx-scripting-fundamentals-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="e96b9-140">For more information, see [MDX Scripting Fundamentals &#40;Analysis Services&#41;](mdx/mdx-scripting-fundamentals-analysis-services.md).</span></span>  
  
 <span data-ttu-id="e96b9-141">При одновременном использовании вычисляемых элементов и формул пользовательской свертки следует помнить о порядке вычислений.</span><span class="sxs-lookup"><span data-stu-id="e96b9-141">If you use both calculated members and custom rollup formulas for members of an attribute, you should be aware of the order of evaluation.</span></span> <span data-ttu-id="e96b9-142">Вычисляемые элементы разрешаются до формул пользовательской свертки.</span><span class="sxs-lookup"><span data-stu-id="e96b9-142">Calculated members are resolved before custom rollup formulas are resolved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e96b9-143">См. также:</span><span class="sxs-lookup"><span data-stu-id="e96b9-143">See Also</span></span>  
 <span data-ttu-id="e96b9-144">[Атрибуты и иерархии атрибутов](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="e96b9-144">[Attributes and Attribute Hierarchies](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md) </span></span>  
 [<span data-ttu-id="e96b9-145">Настройка нестандартных формул элементов для атрибутов в измерении</span><span class="sxs-lookup"><span data-stu-id="e96b9-145">Set Custom Member Formulas for Attributes in a Dimension</span></span>](bi-wizard-custom-member-formulas-for-attributes-in-a-dimension.md)  
  
  
