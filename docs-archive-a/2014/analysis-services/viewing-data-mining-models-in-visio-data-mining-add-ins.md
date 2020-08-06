---
title: Просмотр моделей интеллектуального анализа данных в Visio (надстройки интеллектуального анализа данных) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- diagram, modifying
- templates [Visio]
- shapes, data mining
- diagram
ms.assetid: 5841adea-6650-4fae-8526-26af33edbede
author: minewiskan
ms.author: owend
ms.openlocfilehash: f3c1e63c058295b93e2562c64a6df90a30273a10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657909"
---
# <a name="viewing-data-mining-models-in-visio-data-mining-add-ins"></a><span data-ttu-id="4a745-102">Просмотр моделей интеллектуального анализа данных в Visio (надстройки интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="4a745-102">Viewing Data Mining Models in Visio (Data Mining Add-ins)</span></span>
  <span data-ttu-id="4a745-103">Фигуры Visio для интеллектуального анализа данных позволяют подключаться к серверу и создавать диаграммы, представляющие существующую модель интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="4a745-103">The Visio shapes for data mining let you connect to a server and create a diagram representing an existing data mining model.</span></span> <span data-ttu-id="4a745-104">Затем диаграммы можно настроить с помощью элементов управления Visio, но можно также выполнять детализацию данных, выводить некоторые данные статистики, на которой она основывается, и работать с базовой моделью.</span><span class="sxs-lookup"><span data-stu-id="4a745-104">The diagrams can then be customized using Visio controls, but you can also drill down into data, expose some of the underlying statistics, and work with the underlying model.</span></span>  
  
## <a name="building-a-model-diagram"></a><span data-ttu-id="4a745-105">Создание диаграммы модели</span><span class="sxs-lookup"><span data-stu-id="4a745-105">Building a Model Diagram</span></span>  
 <span data-ttu-id="4a745-106">При открытии файла, содержащего фигуры Visio для интеллектуального анализа данных, на панели « **фигуры** » отображаются следующие фигуры.</span><span class="sxs-lookup"><span data-stu-id="4a745-106">When you open the file containing the Visio shapes for data mining, the **Shapes** pane shows the following shapes.</span></span>  
  
 <span data-ttu-id="4a745-107">Если при открытии Visio фигуры интеллектуального анализа данных не отображаются, откройте файл шаблона, расположенный в папке установки.</span><span class="sxs-lookup"><span data-stu-id="4a745-107">If you do not see the data mining shapes when you open Visio, open the template file from the installation folder.</span></span>  
  
 <span data-ttu-id="4a745-108">![DM](media/dm-stencil.gif "DM")</span><span class="sxs-lookup"><span data-stu-id="4a745-108">![DM](media/dm-stencil.gif "DM")</span></span>  
  
 <span data-ttu-id="4a745-109">Для использования фигуры перетащите ее на лист.</span><span class="sxs-lookup"><span data-stu-id="4a745-109">To use a shape, drag it to the page.</span></span> <span data-ttu-id="4a745-110">Для каждой фигуры запускается отдельный мастер, который помогает выбрать исходные данные, задать параметры для определенного типа схемы и определить заливку и другие параметры отображения.</span><span class="sxs-lookup"><span data-stu-id="4a745-110">Each of the shapes opens a different wizard, which helps you select source data, set options for the specific diagram type, and specify shading and other display options.</span></span>  
  
 <span data-ttu-id="4a745-111">В следующей таблице перечислены типы моделей, которые можно использовать для каждого типа диаграмм.</span><span class="sxs-lookup"><span data-stu-id="4a745-111">The following table lists the types of models that you can use with each type of diagram.</span></span>  
  
|<span data-ttu-id="4a745-112">Фигура Visio</span><span class="sxs-lookup"><span data-stu-id="4a745-112">Visio shape</span></span>|<span data-ttu-id="4a745-113">Поддерживаемые модели</span><span class="sxs-lookup"><span data-stu-id="4a745-113">Supported models</span></span>|  
|-----------------|----------------------|  
|<span data-ttu-id="4a745-114">Дерево принятия решений</span><span class="sxs-lookup"><span data-stu-id="4a745-114">Decision Tree</span></span>|<span data-ttu-id="4a745-115">Используйте эту фигуру для моделей на основе дерева принятия решений или алгоритма линейной регрессии.</span><span class="sxs-lookup"><span data-stu-id="4a745-115">Use this shape for models based on the decision tree or linear regression algorithms.</span></span>|  
|<span data-ttu-id="4a745-116">Сеть зависимостей</span><span class="sxs-lookup"><span data-stu-id="4a745-116">Dependency Network</span></span>|<span data-ttu-id="4a745-117">Используйте эту фигуру для моделей на основе любого из следующих алгоритмов: упрощенный алгоритм Байеса, деревья принятия решений или правила взаимосвязей.</span><span class="sxs-lookup"><span data-stu-id="4a745-117">Use this shape for models based on any of the following algorithms: Naive Bayes, Decision Trees, or Association Rules.</span></span>|  
|<span data-ttu-id="4a745-118">Кластер</span><span class="sxs-lookup"><span data-stu-id="4a745-118">Cluster</span></span>|<span data-ttu-id="4a745-119">Используйте эту фигуру для моделей, основанных на алгоритмах кластеризации.</span><span class="sxs-lookup"><span data-stu-id="4a745-119">Use this shape for models based on clustering algorithms.</span></span>|  
  
 <span data-ttu-id="4a745-120">В зависимости от типа данных модели интеллектуального анализа данных, мастер может предлагать различные параметры.</span><span class="sxs-lookup"><span data-stu-id="4a745-120">Depending on the type of data in your mining model, the wizard may offer different options.</span></span> <span data-ttu-id="4a745-121">Например, столбцы, содержащие непрерывные числа отображаются иначе, чем категориальные переменные.</span><span class="sxs-lookup"><span data-stu-id="4a745-121">For example, columns that contain continuous numbers are visualized differently than categorical variables.</span></span>  
  
## <a name="working-with-completed-shapes"></a><span data-ttu-id="4a745-122">Работа с завершенными фигурами</span><span class="sxs-lookup"><span data-stu-id="4a745-122">Working with Completed Shapes</span></span>  
 <span data-ttu-id="4a745-123">После создания диаграммы вы можете использовать ее для изучения модели интеллектуального анализа данных или улучшения диаграммы для использования ее в презентациях.</span><span class="sxs-lookup"><span data-stu-id="4a745-123">After the diagram is complete, you can use it to browse the data mining model or enhance the diagram for use in presentations.</span></span>  
  
### <a name="visio-menus"></a><span data-ttu-id="4a745-124">Меню Visio</span><span class="sxs-lookup"><span data-stu-id="4a745-124">Visio Menus</span></span>  
 <span data-ttu-id="4a745-125">Visio содержит разнообразные элементы управления отрисовкой, темы и контекстные меню для улучшения диаграмм.</span><span class="sxs-lookup"><span data-stu-id="4a745-125">Visio provides a variety of rendering controls, themes, and shortcut menus to help enhance a diagram.</span></span>  
  
-   <span data-ttu-id="4a745-126">Используйте темы Visio для изменения цветов диаграммы.</span><span class="sxs-lookup"><span data-stu-id="4a745-126">Use Visio themes to alter diagram colors.</span></span>  
  
-   <span data-ttu-id="4a745-127">Изменение соединителей или макета диаграммы.</span><span class="sxs-lookup"><span data-stu-id="4a745-127">Change connectors or diagram layout.</span></span>  
  
### <a name="data-mining-menus"></a><span data-ttu-id="4a745-128">Меню интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="4a745-128">Data Mining Menus</span></span>  
 <span data-ttu-id="4a745-129">Эти панели инструментов и элементы меню предоставляются в составе настроек, которые соответствуют каждой фигуре или типу модели.</span><span class="sxs-lookup"><span data-stu-id="4a745-129">These toolbars and menu items are provided by the add-ins that are specific to each shape or model type</span></span>  
  
-   <span data-ttu-id="4a745-130">У диаграммы каждого типа есть контекстное меню для фигуры, предоставляющее доступ к специальным параметрам.</span><span class="sxs-lookup"><span data-stu-id="4a745-130">Each diagram type has a shortcut menu for the shape that lets you access special options.</span></span> <span data-ttu-id="4a745-131">Хотя многие параметры в этом меню доступны для всех фигур Visio, некоторые из них предоставляются только для шаблонов интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="4a745-131">Although many options in this menu are common to all Visio shapes, some options are unique to the data mining templates</span></span>  
  
     <span data-ttu-id="4a745-132">Например, на схеме дерева решений можно щелкнуть отдельный узел и затем развернуть дочерние узлы, чтобы упростить схему или переместить их на отдельный лист.</span><span class="sxs-lookup"><span data-stu-id="4a745-132">For example, in a decision tree diagram, you can click an individual node and then collapse the child nodes to make the diagram simpler, or move child nodes to a separate page.</span></span>  
  
-   <span data-ttu-id="4a745-133">Поскольку форма привязана к данным модели, можно также выполнить некоторое количество исследований при помощи диаграммы.</span><span class="sxs-lookup"><span data-stu-id="4a745-133">Because the shape is bound to the model data, you can also do some amount of exploration using the diagram:</span></span>  
  
     <span data-ttu-id="4a745-134">Фильтрация отображаемых узлов или изменение уровня дерева или глубины диаграммы.</span><span class="sxs-lookup"><span data-stu-id="4a745-134">Filter the nodes that are displayed, or change the level of the tree or depth of the graph.</span></span>  
  
     <span data-ttu-id="4a745-135">Увеличение определенных разделов, поиск узлов, содержащих определенный атрибут, или фильтрация диаграммы зависимостей по ребрам (вероятность).</span><span class="sxs-lookup"><span data-stu-id="4a745-135">Zoom in on specific sections, search for nodes that contain a certain attribute, or filter a dependency graph by its edges (probability).</span></span>  
  
## <a name="walkthroughs"></a><span data-ttu-id="4a745-136">Пошаговые руководства</span><span class="sxs-lookup"><span data-stu-id="4a745-136">Walkthroughs</span></span>  
 <span data-ttu-id="4a745-137">Примеры работы с законченной диаграммой и ее интерпретации см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="4a745-137">For examples of how to work with and interpret a completed diagram, see these topics:</span></span>  
  
 [<span data-ttu-id="4a745-138">Пошаговое руководство по диаграмме кластеров</span><span class="sxs-lookup"><span data-stu-id="4a745-138">Cluster Diagram Walkthrough</span></span>](cluster-diagram-walkthrough-data-mining-add-ins.md)  
  
 [<span data-ttu-id="4a745-139">Пошаговое руководство по диаграмме сети зависимостей</span><span class="sxs-lookup"><span data-stu-id="4a745-139">Dependency Net Diagram Walkthrough</span></span>](dependency-network-diagram-walkthrough-data-mining-add-ins.md)  
  
 [<span data-ttu-id="4a745-140">Пошаговое руководство по диаграмме дерева принятия решений</span><span class="sxs-lookup"><span data-stu-id="4a745-140">Decision Tree Diagram Walkthrough</span></span>](decision-tree-diagram-walkthrough-data-mining-add-ins.md)  
  
## <a name="see-also"></a><span data-ttu-id="4a745-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="4a745-141">See Also</span></span>  
 [<span data-ttu-id="4a745-142">Просмотр моделей в Excel &#40;SQL Server надстройки интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="4a745-142">Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](browsing-models-in-excel-sql-server-data-mining-add-ins.md)  
  
  
