---
title: Средство просмотра деревьев содержимого общего вида (Майкрософт) (интеллектуальный анализ данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.contentviewer.f1
ms.assetid: 751b4393-f6fd-48c1-bcef-bdca589ce34c
author: minewiskan
ms.author: owend
ms.openlocfilehash: b0dab06d6af8f2c5af029d9ce831f518faa4067e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740571"
---
# <a name="microsoft-generic-content-tree-viewer-data-mining"></a><span data-ttu-id="356ff-102">Средство просмотра деревьев содержимого общего вида (Майкрософт) (интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="356ff-102">Microsoft Generic Content Tree Viewer (Data Mining)</span></span>
  <span data-ttu-id="356ff-103">**Средство просмотра деревьев содержимого общего вида (Майкрософт)** отображает подробные сведения о содержимом модели интеллектуального анализа данных в стандартизованном табличном формате HTML.</span><span class="sxs-lookup"><span data-stu-id="356ff-103">The **Microsoft Generic Content Tree Viewer** displays detailed information about the contents of a data mining mode in a standardized HTML table format.</span></span> <span data-ttu-id="356ff-104">Это представление полезно, так как показывает фундаментальную структуру модели, а также сообщает подробности о коэффициентах, распределении значений и многом другом.</span><span class="sxs-lookup"><span data-stu-id="356ff-104">This view is useful because it exposes the underlying structure of the model, as well details about coefficients, the distribution of values, and much more.</span></span>  
  
 <span data-ttu-id="356ff-105">Собственно содержимое, отображаемое в таблице, различается в зависимости от применяемого алгоритма и может включать сведения о столбцах, правилах, свойствах, атрибутах, узлах и формулах.</span><span class="sxs-lookup"><span data-stu-id="356ff-105">The actual content displayed in the table varies depending on the algorithm that was used and might include columns, rules, properties, attributes, nodes, and formulas.</span></span> <span data-ttu-id="356ff-106">Дополнительные сведения о содержимом модели и об интерпретации сведений для каждого типа модели см. в разделе [Содержимое модели интеллектуального анализа данных (службы Analysis Services — интеллектуальный анализ данных)](data-mining/mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="356ff-106">For more information about model content, and how to interpret the information for each model type, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](data-mining/mining-model-content-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="356ff-107">Сведения, которые отображаются в средстве просмотра, имеют общую структуру, основанную на наборе строк схемы для моделей интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="356ff-107">The information that is displayed in the viewer uses a common structure that is based on the content schema rowset for mining models.</span></span> <span data-ttu-id="356ff-108">Набор строк схемы содержимого представляет собой общую платформу, предназначенную для сохранения шаблонов, статистики и другого содержимого модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="356ff-108">The content schema rowset is a generic framework for storing patterns, statistics, and other contents of a data mining model.</span></span> <span data-ttu-id="356ff-109">Список всех столбцов в наборе строк схемы интеллектуального анализа данных для моделей интеллектуального анализа данных см. в разделе [Набор данных DMSCHEMA_MINING_MODEL_CONTENT](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset).</span><span class="sxs-lookup"><span data-stu-id="356ff-109">For a list of the columns in the data mining schema rowset for mining models, see [DMSCHEMA_MINING_MODEL_CONTENT Rowset](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset).</span></span>  
  
## <a name="options"></a><span data-ttu-id="356ff-110">Варианты</span><span class="sxs-lookup"><span data-stu-id="356ff-110">Options</span></span>  
 <span data-ttu-id="356ff-111">**Заголовок узла (уникальный идентификатор)**</span><span class="sxs-lookup"><span data-stu-id="356ff-111">**Node caption (Unique ID)**</span></span>  
 <span data-ttu-id="356ff-112">Эта панель отображает список всех узлов в выбранной модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="356ff-112">This pane displays a list of all the nodes in the selected mining model.</span></span> <span data-ttu-id="356ff-113">Способ упорядочения узлов в дереве различается в зависимости от типа просматриваемой модели.</span><span class="sxs-lookup"><span data-stu-id="356ff-113">The way the nodes are arranged in the tree is different depending on the type of model you are viewing.</span></span>  
  
 <span data-ttu-id="356ff-114">Можно щелкнуть каждый узел, чтобы вывести подробные сведения об этом узле на панели **Сведения об узле** .</span><span class="sxs-lookup"><span data-stu-id="356ff-114">You can click each node to display details about the node in the **Node details** pane.</span></span>  
  
 <span data-ttu-id="356ff-115">**Сведения об узле**</span><span class="sxs-lookup"><span data-stu-id="356ff-115">**Node details**</span></span>  
 <span data-ttu-id="356ff-116">Отображает подробную информацию о содержимом выбранного узла.</span><span class="sxs-lookup"><span data-stu-id="356ff-116">Displays detailed information about the content of the selected node.</span></span> <span data-ttu-id="356ff-117">В каждом узле хранятся данные в стандартизированном формате, но содержимое и важность каждой строки таблицы зависит от типа просматриваемой модели или типа просматриваемого узла.</span><span class="sxs-lookup"><span data-stu-id="356ff-117">Each node stores its information in a standardized format, but the contents and significance of each line of the table depends on the type of model or type of node that you are viewing.</span></span> <span data-ttu-id="356ff-118">Например, сведения, сохраненные для узла, представляющего правило в модели взаимосвязей, содержат данные, отличные от узла, представляющего дерево в модели деревьев принятия решений.</span><span class="sxs-lookup"><span data-stu-id="356ff-118">For example, the information stored for a node that represents a rule in an association model contains different information than a node that represents a tree in a decision trees model.</span></span>  
  
 <span data-ttu-id="356ff-119">Дополнительные сведения об интерпретации сведений об узле для каждого типа модели см. в разделе [Содержимое модели интеллектуального анализа данных (службы Analysis Services — интеллектуальный анализ данных)](data-mining/mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="356ff-119">For information about how to interpret the node information for a specific model type, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](data-mining/mining-model-content-analysis-services-data-mining.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="356ff-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="356ff-120">See Also</span></span>  
 <span data-ttu-id="356ff-121">[Алгоритмы интеллектуального анализа данных &#40;Analysis Services — интеллектуальный анализ данных&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="356ff-121">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="356ff-122">[Средства просмотра моделей интеллектуального анализа &#40;конструктор моделей интеллектуального анализа данных&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="356ff-122">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="356ff-123">Запросы интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="356ff-123">Data Mining Queries</span></span>](data-mining/data-mining-queries.md)  
  
  
