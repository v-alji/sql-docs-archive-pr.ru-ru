---
title: Диалоговое окно "Детализация" (средство просмотра моделей интеллектуального анализа данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.drillthrough.f1
ms.assetid: 42b78399-143d-4f44-90e0-b545ffb79e10
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1b00c62017de5a26c4507a04aeaf59aba7522146
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667466"
---
# <a name="drill-through-dialog-box-mining-model-viewer"></a><span data-ttu-id="7e2d8-102">Диалоговое окно «Детализация» (средство просмотра моделей интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="7e2d8-102">Drill Through Dialog Box (Mining Model Viewer)</span></span>
  <span data-ttu-id="7e2d8-103">При просмотре модели интеллектуального анализа данных с помощью вкладки **Средство просмотра моделей интеллектуального анализа данных** конструктора интеллектуального анализа данных можно раскрывать более подробные сведения о данных вариантов, предоставляемые моделью с включенной детализацией.</span><span class="sxs-lookup"><span data-stu-id="7e2d8-103">When you view a mining model by using the **Mining Model Viewer** tab of Data Mining Designer, you can drill through into details about the case data, provided the model has drillthrough enabled.</span></span> <span data-ttu-id="7e2d8-104">Более того, если для базовой структуры интеллектуального анализа данных включена детализация, также можно просматривать столбцы в структуре интеллектуального анализа данных, даже если эти столбцы не включены в модель интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="7e2d8-104">Moreover, if the underlying mining structure has drillthrough enabled, you can also see columns in the mining structure, even if those columns were not included in the mining model.</span></span> <span data-ttu-id="7e2d8-105">В списке столбцов столбцы структуры имеют префикс в виде метки</span><span class="sxs-lookup"><span data-stu-id="7e2d8-105">In the column list, the structure columns are prefixed by the "Structure."</span></span> <span data-ttu-id="7e2d8-106">"Structure.".</span><span class="sxs-lookup"><span data-stu-id="7e2d8-106">label.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7e2d8-107">Для существующей структуры интеллектуального анализа данных нельзя включить детализацию.</span><span class="sxs-lookup"><span data-stu-id="7e2d8-107">You cannot enable drillthrough on an existing mining structure.</span></span> <span data-ttu-id="7e2d8-108">Вместо этого следует создать повторно структуру интеллектуального анализа данных и включить детализацию в процессе создания.</span><span class="sxs-lookup"><span data-stu-id="7e2d8-108">Instead, you must re-create the mining structure and enable drillthrough during the creation process.</span></span>  
  
 <span data-ttu-id="7e2d8-109">Дополнительные сведения о доступе к данным вариантов из каждого средства просмотра моделей интеллектуального анализа данных, в которых поддерживается детализация, **см. в разделе** [Выполнение детализации до данных вариантов из модели интеллектуального анализа данных](data-mining/drill-through-to-case-data-from-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="7e2d8-109">For information about how to access case data from each of the mining model viewers that support drillthrough, **see** [Drill Through to Case Data from a Mining Model](data-mining/drill-through-to-case-data-from-a-mining-model.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="7e2d8-110">Варианты</span><span class="sxs-lookup"><span data-stu-id="7e2d8-110">Options</span></span>  
 <span data-ttu-id="7e2d8-111">**Варианты систематизированы как**</span><span class="sxs-lookup"><span data-stu-id="7e2d8-111">**Cases Classified To**</span></span>  
 <span data-ttu-id="7e2d8-112">Отображает определение правила, набора элементов и кластера, содержащихся в выбранном узле.</span><span class="sxs-lookup"><span data-stu-id="7e2d8-112">Displays the definition of the rule, itemset, and cluster that are contained in the selected node.</span></span>  
  
 <span data-ttu-id="7e2d8-113">**Список столбцов**</span><span class="sxs-lookup"><span data-stu-id="7e2d8-113">**Column list**</span></span>  
 <span data-ttu-id="7e2d8-114">Отображает столбцы модели, за которыми следуют столбцы структуры.</span><span class="sxs-lookup"><span data-stu-id="7e2d8-114">Displays the columns in the model, followed by the structure columns.</span></span>  
  
 <span data-ttu-id="7e2d8-115">**ПРИМЕЧАНИЕ.** Столбцы структуры отображаются, только если в структуре интеллектуального анализа данных включена детализация и выбран параметр **Столбцы модели и структуры**.</span><span class="sxs-lookup"><span data-stu-id="7e2d8-115">**Note** Structure columns are displayed only if drillthrough is enabled on the mining structure, and if you selected the option, **Model and Structure Columns**.</span></span> <span data-ttu-id="7e2d8-116">Более того, чтобы просмотреть столбцы необходимо обладать разрешениями на детализацию как для модели, так и для структуры интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="7e2d8-116">Moreover, you must have drillthrough permissions on both the mining model and the mining structure to view the columns.</span></span>  
  
 <span data-ttu-id="7e2d8-117">Столбцы структуры, не входящие в модель, отображаются в виде \*\*структуры. \<column name> \*\*</span><span class="sxs-lookup"><span data-stu-id="7e2d8-117">Structure columns that are not included in the model appear as **Structure.\<column name>**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7e2d8-118">Чтобы скопировать данные детализации в буфер обмена в формате с разделителями — знаками табуляции, можно щелкнуть правой кнопкой мыши любое место сетки столбцов и выбрать команду **Копировать все**.</span><span class="sxs-lookup"><span data-stu-id="7e2d8-118">You can right-click anywhere in the column grid and select **Copy All** to copy the drillthrough data, in tab-delimited format, to the Clipboard.</span></span> <span data-ttu-id="7e2d8-119">Будут скопированы только данные вариантов, но не определение узла.</span><span class="sxs-lookup"><span data-stu-id="7e2d8-119">The copied data includes only the case data, not the node definition.</span></span>  
  
 <span data-ttu-id="7e2d8-120">**Воспроизведение**</span><span class="sxs-lookup"><span data-stu-id="7e2d8-120">**Play**</span></span>  
 <span data-ttu-id="7e2d8-121">Нажмите кнопку с зеленой стрелкой, чтобы обновить данные.</span><span class="sxs-lookup"><span data-stu-id="7e2d8-121">Click the green arrow button to refresh the data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e2d8-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="7e2d8-122">See Also</span></span>  
 <span data-ttu-id="7e2d8-123">[Запросы детализации &#40;&#41;интеллектуального анализа данных](data-mining/drillthrough-queries-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="7e2d8-123">[Drillthrough Queries &#40;Data Mining&#41;](data-mining/drillthrough-queries-data-mining.md) </span></span>  
 <span data-ttu-id="7e2d8-124">[Средства просмотра моделей интеллектуального анализа &#40;конструктор моделей интеллектуального анализа данных&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="7e2d8-124">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="7e2d8-125">Задачи и инструкции средства просмотра моделей интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="7e2d8-125">Mining Model Viewer Tasks and How-tos</span></span>](data-mining/mining-model-viewer-tasks-and-how-tos.md)  
  
  
