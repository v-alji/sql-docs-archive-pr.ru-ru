---
title: Преобразование "Сортировка" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sorttrans.f1
helpviewer_keywords:
- Sort transformation
- descending sorts
- ascending sorts
- sorting data [Integration Services]
- multiple sorts
- duplicate data [Integration Services]
ms.assetid: 728c9351-84a8-4a89-be4d-d50d4adc04e0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7039d02b6cc55355c3b27e5694474df4666570ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665451"
---
# <a name="sort-transformation"></a><span data-ttu-id="48065-102">преобразование «Сортировка»</span><span class="sxs-lookup"><span data-stu-id="48065-102">Sort Transformation</span></span>
  <span data-ttu-id="48065-103">Это преобразование сортирует входные данные по возрастанию или убыванию и копирует отсортированные данные на выход преобразования.</span><span class="sxs-lookup"><span data-stu-id="48065-103">The Sort transformation sorts input data in ascending or descending order and copies the sorted data to the transformation output.</span></span> <span data-ttu-id="48065-104">К входным данным можно применять несколько сортировок, при этом каждая сортировка будет иметь свой номер, определяющий ее последовательность.</span><span class="sxs-lookup"><span data-stu-id="48065-104">You can apply multiple sorts to an input; each sort is identified by a numeral that determines the sort order.</span></span> <span data-ttu-id="48065-105">Данные будут сначала упорядочены по столбцу с наименьшим номером, затем по столбцу со следующим наименьшим номером и т. д.</span><span class="sxs-lookup"><span data-stu-id="48065-105">The column with the lowest number is sorted first, the sort column with the second lowest number is sorted next, and so on.</span></span> <span data-ttu-id="48065-106">Например, если у столбца **Страна** номер сортировки 1, а у столбца **Город** номер сортировки 2, выходные данные будут отсортированы сначала по названиям стран, а затем по названиям городов.</span><span class="sxs-lookup"><span data-stu-id="48065-106">For example, if a column named **CountryRegion** has a sort order of 1 and a column named **City** has a sort order of 2, the output is sorted by country/region and then by city.</span></span> <span data-ttu-id="48065-107">Положительный номер сортировки означает, что данные будут упорядочены по возрастанию, а отрицательный — по убыванию.</span><span class="sxs-lookup"><span data-stu-id="48065-107">A positive number denotes that the sort is ascending, and a negative number denotes that the sort is descending.</span></span> <span data-ttu-id="48065-108">У столбцов, по которым сортировка производиться не будет, номер сортировки равен 0.</span><span class="sxs-lookup"><span data-stu-id="48065-108">Columns that are not sorted have a sort order of 0.</span></span> <span data-ttu-id="48065-109">Такие столбцы автоматически копируются на выход преобразования вместе с отсортированными столбцами.</span><span class="sxs-lookup"><span data-stu-id="48065-109">Columns that are not selected for sorting are automatically copied to the transformation output together with the sorted columns.</span></span>  
  
 <span data-ttu-id="48065-110">Преобразование «Сортировка» включает набор параметров сравнения, согласно которым будут обрабатываться данные в столбце.</span><span class="sxs-lookup"><span data-stu-id="48065-110">The Sort transformation includes a set of comparison options to define how the transformation handles the string data in a column.</span></span> <span data-ttu-id="48065-111">Дополнительные сведения см. в статье [Comparing String Data](../comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="48065-111">For more information, see [Comparing String Data](../comparing-string-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="48065-112">Преобразование «Сортировка» не сортирует идентификаторы GUID в том же порядке, что и предложение ORDER BY языка Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="48065-112">The Sort transformation does not sort GUIDs in the same order as the ORDER BY clause does in Transact-SQL.</span></span> <span data-ttu-id="48065-113">Преобразование «Сортировка» сортирует идентификаторы GUID, начинающиеся с символов с 0 по 9, перед идентификаторами GUID, начинающимися с символов с A по F, а предложение ORDER BY в реализации [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)]выполняет сортировку наоборот.</span><span class="sxs-lookup"><span data-stu-id="48065-113">While the Sort transformation sorts GUIDs that start with 0-9 before GUIDs that start with A-F, the ORDER BY clause, as implemented in the [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)], sorts them differently.</span></span> <span data-ttu-id="48065-114">Дополнительные сведения см. в разделе [Предложение ORDER BY (Transact-SQL)](/sql/t-sql/queries/select-order-by-clause-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="48065-114">For more information, see [ORDER BY Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-order-by-clause-transact-sql).</span></span>  
  
 <span data-ttu-id="48065-115">В процессе сортировки это преобразование может удалять повторяющиеся строки.</span><span class="sxs-lookup"><span data-stu-id="48065-115">The Sort transformation can also remove duplicate rows as part of its sort.</span></span> <span data-ttu-id="48065-116">Повторяющимися являются строки с одинаковым значением ключа сортировки.</span><span class="sxs-lookup"><span data-stu-id="48065-116">Duplicate rows are rows with the same sort key values.</span></span> <span data-ttu-id="48065-117">Значение ключа сортировки формируется на основе использующихся параметров сравнения строк, то есть у разных строковых литералов могут быть одинаковые значения ключа сортировки.</span><span class="sxs-lookup"><span data-stu-id="48065-117">The sort key value is generated based on the string comparison options being used, which means that different literal strings may have the same sort key values.</span></span> <span data-ttu-id="48065-118">Строки во входных столбцах с разными значениями, но одинаковыми ключами сортировки определяются преобразованием как повторяющиеся.</span><span class="sxs-lookup"><span data-stu-id="48065-118">The transformation identifies rows in the input columns that have different values but the same sort key as duplicates.</span></span>  
  
 <span data-ttu-id="48065-119">Преобразование «Сортировка» включает пользовательское свойство `MaximumThreads`, которое может быть обновлено выражением свойства при загрузке пакета.</span><span class="sxs-lookup"><span data-stu-id="48065-119">The Sort transformation includes the `MaximumThreads` custom property that can be updated by a property expression when the package is loaded.</span></span> <span data-ttu-id="48065-120">Дополнительные сведения см. в разделах [Выражения служб Integration Services (SSIS)](../../expressions/integration-services-ssis-expressions.md), [Использование выражений свойств в пакетах](../../expressions/use-property-expressions-in-packages.md) и [Пользовательские свойства преобразований](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="48065-120">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../../expressions/integration-services-ssis-expressions.md), [Use Property Expressions in Packages](../../expressions/use-property-expressions-in-packages.md), and [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="48065-121">Это преобразование имеет один вход и один выход.</span><span class="sxs-lookup"><span data-stu-id="48065-121">This transformation has one input and one output.</span></span> <span data-ttu-id="48065-122">Оно не поддерживает выход ошибок.</span><span class="sxs-lookup"><span data-stu-id="48065-122">It does not support error outputs.</span></span>  
  
## <a name="configuration-of-the-sort-transformation"></a><span data-ttu-id="48065-123">Настройка преобразования «Сортировка»</span><span class="sxs-lookup"><span data-stu-id="48065-123">Configuration of the Sort Transformation</span></span>  
 <span data-ttu-id="48065-124">Свойства могут устанавливаться через конструктор служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] или с помощью программных средств.</span><span class="sxs-lookup"><span data-stu-id="48065-124">You can set properties through the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="48065-125">Сведения о свойствах, которые можно установить в диалоговом окне **Редактор преобразования «Сортировка»** , см. в разделе [Sort Transformation Editor](../../sort-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="48065-125">For information about the properties that you can set in the **Sort Transformation Editor** dialog box, see [Sort Transformation Editor](../../sort-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="48065-126">Диалоговое окно **Расширенный редактор** содержит свойства, которые можно установить с помощью программных средств.</span><span class="sxs-lookup"><span data-stu-id="48065-126">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="48065-127">Дополнительные сведения о свойствах, которые вы можете задать в диалоговом окне **Расширенный редактор** или программными средствами, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="48065-127">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="48065-128">Общие свойства</span><span class="sxs-lookup"><span data-stu-id="48065-128">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="48065-129">Пользовательские свойства преобразований</span><span class="sxs-lookup"><span data-stu-id="48065-129">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="48065-130">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="48065-130">Related Tasks</span></span>  
 <span data-ttu-id="48065-131">Дополнительные сведения о настройке свойств компонента см. в разделе [Установление свойств компонента потока данных](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="48065-131">For more information about how to set properties of the component, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="48065-132">См. также</span><span class="sxs-lookup"><span data-stu-id="48065-132">Related Content</span></span>  
 <span data-ttu-id="48065-133">Образец [Пользовательский компонент SortDeDuplicateDelimitedString служб SSIS](https://go.microsoft.com/fwlink/?LinkId=220821)на сайте codeplex.com.</span><span class="sxs-lookup"><span data-stu-id="48065-133">Sample, [SortDeDuplicateDelimitedString Custom SSIS Component](https://go.microsoft.com/fwlink/?LinkId=220821), on codeplex.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48065-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="48065-134">See Also</span></span>  
 <span data-ttu-id="48065-135">[Поток данных](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="48065-135">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="48065-136">Преобразования служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="48065-136">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
