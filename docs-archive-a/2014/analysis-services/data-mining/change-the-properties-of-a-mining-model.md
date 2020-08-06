---
title: Изменение свойств модели интеллектуального анализа данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models [Analysis Services], properties
- properties [data mining]
ms.assetid: aefaeb7f-d174-48d1-a188-0987a3b1196b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 395e6a4cb9c0f0dac0f0c717dfe0695033cad050
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655443"
---
# <a name="change-the-properties-of-a-mining-model"></a><span data-ttu-id="3f80b-102">Изменение свойств модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="3f80b-102">Change the Properties of a Mining Model</span></span>
  <span data-ttu-id="3f80b-103">Некоторые свойства моделей интеллектуального анализа данных могут применяться ко всей модели, другие действуют только на отдельные столбцы.</span><span class="sxs-lookup"><span data-stu-id="3f80b-103">Some mining model properties apply to the model as a whole, and other model properties apply to individual columns.</span></span> <span data-ttu-id="3f80b-104">Примеры свойств, которые применяются ко всей модели: свойство `Drillthrough`, задающее доступность данных вариантов для запросов, а также свойство `Description`.</span><span class="sxs-lookup"><span data-stu-id="3f80b-104">Examples of properties that apply to the entire model would be the `Drillthrough` property, which specifies whether the case data should be available for querying, and the `Description` property.</span></span> <span data-ttu-id="3f80b-105">Свойства, действующие только на определенные столбцы: `Usage` и `ModelingFlags`, управляющие использованием данных в столбце внутри модели.</span><span class="sxs-lookup"><span data-stu-id="3f80b-105">Properties that apply to the column include `Usage` and `ModelingFlags`, which control how data in the column is used within the model.</span></span>  
  
 <span data-ttu-id="3f80b-106">Для следующих свойств модели предусмотрены расширенные редакторы, с помощью которых можно создавать выражения или настраивать сложные свойства моделей.</span><span class="sxs-lookup"><span data-stu-id="3f80b-106">The following model properties have advanced editors that you can use to create expressions or configure complex model properties.</span></span> <span data-ttu-id="3f80b-107">Следующие свойства предоставляют:</span><span class="sxs-lookup"><span data-stu-id="3f80b-107">The following properties provide:</span></span>  
  
-   <span data-ttu-id="3f80b-108">`Filter`свойство: открывает [диалоговое окно Фильтр набора данных или фильтр модели](../data-set-filter-or-model-filter-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="3f80b-108">`Filter` property: Opens the [Data Set Filter or Model Filter Dialog Box](../data-set-filter-or-model-filter-dialog-box.md).</span></span>  
  
-   <span data-ttu-id="3f80b-109">`AlgorithmParameters`свойство: открывает [диалоговое окно "Параметры алгоритма" &#40;представление моделей интеллектуального анализа данных&#41;](../algorithm-parameters-dialog-box-mining-models-view.md).</span><span class="sxs-lookup"><span data-stu-id="3f80b-109">`AlgorithmParameters` property: Opens the [Algorithm Parameters Dialog Box &#40;Mining Models View&#41;](../algorithm-parameters-dialog-box-mining-models-view.md).</span></span>  
  
 <span data-ttu-id="3f80b-110">Дополнительные сведения о задании свойств в модели интеллектуального анализа данных см. в разделе [Столбцы модели интеллектуального анализа данных](mining-model-columns.md).</span><span class="sxs-lookup"><span data-stu-id="3f80b-110">For information about how to set the properties in a mining model, see [Mining Model Columns](mining-model-columns.md).</span></span>  
  
### <a name="to-change-the-properties-of-a-mining-model"></a><span data-ttu-id="3f80b-111">Изменение свойств модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="3f80b-111">To change the properties of a mining model</span></span>  
  
1.  <span data-ttu-id="3f80b-112">На вкладке **Модели интеллектуального анализа данных** в конструкторе интеллектуального анализа данных щелкните правой кнопкой мыши либо заголовок столбца, содержащего имя модели интеллектуального анализа данных, либо строку, содержащую имя алгоритма. Потом выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="3f80b-112">In the **Mining Models** tab in Data Mining Designer, right-click either the column header that contains the name of the mining model, or the row in the grid that contains the name of the mining algorithm, and then select **Properties**.</span></span>  
  
2.  <span data-ttu-id="3f80b-113">В окне **Свойства** в правой части экрана выделите значение, соответствующее свойству, которое необходимо изменить, и введите новое значение.</span><span class="sxs-lookup"><span data-stu-id="3f80b-113">In the **Properties** window on the right side of the screen, highlight the value that corresponds to the property that you want to change, and enter the new value.</span></span>  
  
     <span data-ttu-id="3f80b-114">Новое значение вступает в силу после выбора другого элемента в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="3f80b-114">The new value will take effect when you select a different element in the designer.</span></span>  
  
### <a name="to-change-the-properties-of-a-mining-model-column"></a><span data-ttu-id="3f80b-115">Изменение свойств столбца модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="3f80b-115">To change the properties of a mining model column</span></span>  
  
1.  <span data-ttu-id="3f80b-116">На вкладке **Модели интеллектуального анализа данных** конструктора моделей интеллектуального анализа данных щелкните правой кнопкой мыши ячейку на пересечении модели интеллектуального анализа данных и столбца структуры интеллектуального анализа данных, которую нужно изменить, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="3f80b-116">In the **Mining Models** tab in Data Mining Designer, right-click the cell in the grid at the intersection of the mining structure column and the mining model, and then select **Properties**.</span></span>  
  
2.  <span data-ttu-id="3f80b-117">В окне **Свойства** в правой части экрана выделите значение, соответствующее свойству, которое необходимо изменить, и введите новое значение.</span><span class="sxs-lookup"><span data-stu-id="3f80b-117">In the **Properties** window on the right side of the screen, highlight the value that corresponds to the property that you want to change, and enter the new value.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3f80b-118">Если для столбца задано значение `Ignore` , окно **свойств** столбца остается пустым.</span><span class="sxs-lookup"><span data-stu-id="3f80b-118">If the column usage is set to `Ignore`, the **Properties** window for the column is blank.</span></span>  
  
     <span data-ttu-id="3f80b-119">Новое значение вступает в силу после выбора другого элемента в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="3f80b-119">The new value will take effect when you select a different element in the designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f80b-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="3f80b-120">See Also</span></span>  
 [<span data-ttu-id="3f80b-121">Задачи и инструкции по модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="3f80b-121">Mining Model Tasks and How-tos</span></span>](mining-model-tasks-and-how-tos.md)  
  
  
