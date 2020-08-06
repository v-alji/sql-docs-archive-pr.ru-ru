---
title: Столбцы модели интеллектуального анализа данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- columns [data mining], mining model columns
- columns [data mining]
- REGRESSOR column
- columns [data mining], modeling flags
- modeling flags [data mining]
- MODEL_EXISTENCE_ONLY column
- usage property [data mining]
ms.assetid: fab47643-5bfd-424e-a0f7-69e665db6bab
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6f936f3f4e0b8f65326e9a6e84f75e6f4e82657f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732206"
---
# <a name="mining-model-columns"></a><span data-ttu-id="41d5e-102">Столбцы модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="41d5e-102">Mining Model Columns</span></span>
  <span data-ttu-id="41d5e-103">Модель интеллектуального анализа данных применяет алгоритм интеллектуального анализа к данным, представленным структурой интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="41d5e-103">A data mining model applies a mining model algorithm to the data that is represented by a mining structure.</span></span> <span data-ttu-id="41d5e-104">Модель интеллектуального анализа данных, как и структура интеллектуального анализа, содержит столбцы.</span><span class="sxs-lookup"><span data-stu-id="41d5e-104">Like the mining structure, the mining model contains columns.</span></span> <span data-ttu-id="41d5e-105">Модель интеллектуального анализа содержится в структуре интеллектуального анализа и наследует все значения свойств, определенных этой структурой.</span><span class="sxs-lookup"><span data-stu-id="41d5e-105">A mining model is contained within the mining structure, and inherits all the values of the properties that are defined by the mining structure.</span></span> <span data-ttu-id="41d5e-106">Модель может использовать все столбцы, содержащиеся в структуре интеллектуального анализа данных, или подмножества этих столбцов.</span><span class="sxs-lookup"><span data-stu-id="41d5e-106">The model can use all the columns that the mining structure contains or a subset of the columns.</span></span>  
  
 <span data-ttu-id="41d5e-107">В столбце модели интеллектуального анализа данных можно определить два дополнительных элемента данных: использование и флаги моделирования.</span><span class="sxs-lookup"><span data-stu-id="41d5e-107">You can define two additional pieces of information on a mining model column: usage, and modeling flags.</span></span>  
  
-   <span data-ttu-id="41d5e-108">**Использование** — это свойство, определяющее, как модель использует столбец.</span><span class="sxs-lookup"><span data-stu-id="41d5e-108">**Usage** is a property that defines how the model uses the column.</span></span> <span data-ttu-id="41d5e-109">Столбцы могут использоваться как входные, ключевые или прогнозируемые.</span><span class="sxs-lookup"><span data-stu-id="41d5e-109">Columns can be used as input columns, key columns, or predictable columns.</span></span>  
  
-   <span data-ttu-id="41d5e-110">**Флаги моделирования** обеспечивают алгоритм дополнительными сведениями о данных, определяемых в таблице вариантов, что помогает алгоритму создавать более точную модель.</span><span class="sxs-lookup"><span data-stu-id="41d5e-110">**Modeling flags** provide the algorithm with additional information about the data that is defined in the case table, so that the algorithm can build a more accurate model.</span></span> <span data-ttu-id="41d5e-111">Флаги моделирования можно определять программным способом с помощью языка расширений интеллектуального анализа данных или в **конструкторе интеллектуального анализа данных** среды [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="41d5e-111">You can define modeling flags programmatically by using the Data Mining Extensions (DMX) language, or in **Data Mining Designer** in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="41d5e-112">В следующем списке описываются флаги моделирования, которые можно определить в столбце модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="41d5e-112">The following list describes the modeling flags that you can define on a mining model column.</span></span>  
  
 `MODEL_EXISTENCE_ONLY`  
 <span data-ttu-id="41d5e-113">Указывает на то, что наличие атрибута важнее значений столбца атрибутов.</span><span class="sxs-lookup"><span data-stu-id="41d5e-113">Indicates that the presence of the attribute is more important than the values that are in the attribute column.</span></span> <span data-ttu-id="41d5e-114">Например, рассмотрим таблицу вариантов, в которой содержится список элементов заказа, связанных с определенным заказчиком.</span><span class="sxs-lookup"><span data-stu-id="41d5e-114">For example, consider a case table that contains a list of order items that are associated with a particular customer.</span></span> <span data-ttu-id="41d5e-115">В данные таблицы включается тип изделия, идентификатор и стоимость каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="41d5e-115">The table data includes the product type, ID, and cost of each item.</span></span> <span data-ttu-id="41d5e-116">Для целей моделирования факт приобретения заказчиком определенного элемента заказа может оказаться важнее стоимости самого элемента заказа.</span><span class="sxs-lookup"><span data-stu-id="41d5e-116">For modeling purposes, the fact that the customer purchased a particular order item may be more important than the cost of the order item itself.</span></span> <span data-ttu-id="41d5e-117">В таком случае столбец стоимости должен быть отмечен как `MODEL_EXISTENCE_ONLY`.</span><span class="sxs-lookup"><span data-stu-id="41d5e-117">In this case, the cost column should be marked as `MODEL_EXISTENCE_ONLY`.</span></span>  
  
 `REGRESSOR`  
 <span data-ttu-id="41d5e-118">Указывает, что алгоритм может использовать заданный столбец в формуле регрессии алгоритмов регрессии.</span><span class="sxs-lookup"><span data-stu-id="41d5e-118">Indicates that the algorithm can use the specified column in the regression formula of regression algorithms.</span></span> <span data-ttu-id="41d5e-119">Этот флаг поддерживается алгоритмом дерева принятия решений [!INCLUDE[msCoName](../../includes/msconame-md.md)] и алгоритмом временных рядов [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="41d5e-119">This flag is supported by the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Decision Trees and [!INCLUDE[msCoName](../../includes/msconame-md.md)] Time Series algorithms.</span></span>  
  
 <span data-ttu-id="41d5e-120">Дополнительные сведения об установке свойства использования и программном определении флагов моделирования с помощью расширений интеллектуального анализа данных см. в разделе [CREATE MINING MODEL (расширения интеллектуального анализа данных)](/sql/dmx/create-mining-model-dmx).</span><span class="sxs-lookup"><span data-stu-id="41d5e-120">For more information about setting the usage property and defining modeling flags programmatically with DMX, see [CREATE MINING MODEL &#40;DMX&#41;](/sql/dmx/create-mining-model-dmx).</span></span> <span data-ttu-id="41d5e-121">Дополнительные сведения об установке свойства использования и определении флагов моделирования в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]см. в разделе [Перемещение объектов интеллектуального анализа данных](moving-data-mining-objects.md).</span><span class="sxs-lookup"><span data-stu-id="41d5e-121">For more information about setting the usage property and defining modeling flags in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], see [Moving Data Mining Objects](moving-data-mining-objects.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41d5e-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="41d5e-122">See Also</span></span>  
 <span data-ttu-id="41d5e-123">[Алгоритмы интеллектуального анализа данных &#40;Analysis Services — интеллектуальный анализ данных&#41;](data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="41d5e-123">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="41d5e-124">[Структуры интеллектуального анализа данных &#40;Analysis Services — интеллектуальный анализ&#41;](mining-structures-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="41d5e-124">[Mining Structures &#40;Analysis Services - Data Mining&#41;](mining-structures-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="41d5e-125">[Изменение свойств модели интеллектуального анализа данных](change-the-properties-of-a-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="41d5e-125">[Change the Properties of a Mining Model](change-the-properties-of-a-mining-model.md) </span></span>  
 <span data-ttu-id="41d5e-126">[Исключить столбец из модели интеллектуального анализа данных](exclude-a-column-from-a-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="41d5e-126">[Exclude a Column from a Mining Model](exclude-a-column-from-a-mining-model.md) </span></span>  
 [<span data-ttu-id="41d5e-127">Столбцы структуры интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="41d5e-127">Mining Structure Columns</span></span>](mining-structure-columns.md)  
  
  
