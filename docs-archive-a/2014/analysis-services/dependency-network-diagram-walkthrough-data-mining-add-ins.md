---
title: Пошаговое руководство по диаграмме сети зависимостей (надстройки интеллектуального анализа данных) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Visio shapes, dependency network
- shapes, data mining
- shapes, network
- dependencies
- diagram, dependency network
- data mining layout toolbar
- dependency network
ms.assetid: aac732a8-5262-4649-b7d7-3ccf6f9cfa8b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 07f97dac7ffb0211f0ff1e1b58c2e0792d026174
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667947"
---
# <a name="dependency-network-diagram-walkthrough-data-mining-add-ins"></a><span data-ttu-id="350d4-102">Пошаговое руководство по диаграмме сети зависимостей (надстройки интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="350d4-102">Dependency Network Diagram Walkthrough (Data Mining Add-ins)</span></span>
  <span data-ttu-id="350d4-103">В нескольких разных типах моделей интеллектуального анализа данных используется диаграмма сети как способ исследовать связи в данных.</span><span class="sxs-lookup"><span data-stu-id="350d4-103">Several different types of data mining models use a network graph as a way of exploring relationships in the data.</span></span> <span data-ttu-id="350d4-104">Вы можете импортировать эти модели в Visio, используя фигуру **сети зависимостей** , а затем продолжить настройку и расширение макета.</span><span class="sxs-lookup"><span data-stu-id="350d4-104">You can import these models into Visio using the **Dependency Network** shape and then continue to customize and enhance the layout.</span></span> <span data-ttu-id="350d4-105">**Фигуры интеллектуального анализа данных для Visio** включают следующие пользовательские элементы управления для работы с диаграммами сети зависимостей.</span><span class="sxs-lookup"><span data-stu-id="350d4-105">The **Data Mining Shapes for Visio** include the following custom controls for working with dependency network diagrams:</span></span>  
  
-   <span data-ttu-id="350d4-106">Элементы управления для диаграммы сети</span><span class="sxs-lookup"><span data-stu-id="350d4-106">Rendering controls for the network graph</span></span>  
  
     <span data-ttu-id="350d4-107">Эти параметры являются частью мастера, который запускается при перемещении формы в рабочее пространство Visio.</span><span class="sxs-lookup"><span data-stu-id="350d4-107">These options are part of the wizard that is launched when you drop a shape into the Visio workspace.</span></span>  
  
-   <span data-ttu-id="350d4-108">Панель инструментов **макета интеллектуального анализа данных**</span><span class="sxs-lookup"><span data-stu-id="350d4-108">**Data Mining Layout** toolbar</span></span>  
  
     <span data-ttu-id="350d4-109">Эти параметры добавляется в рабочую область Visio и позволяют взаимодействовать с диаграммой сети зависимостей.</span><span class="sxs-lookup"><span data-stu-id="350d4-109">These options are added to the Visio workspace to help you interact with the dependency network graph.</span></span>  
  
## <a name="build-a-dependency-network-graph"></a><span data-ttu-id="350d4-110">Создание диаграммы сети зависимостей</span><span class="sxs-lookup"><span data-stu-id="350d4-110">Build a Dependency Network Graph</span></span>  
 <span data-ttu-id="350d4-111">Перетащите фигуру на страницу Visio, чтобы запустить **Мастер фигур Visio в сети зависимостей** и задать параметры схемы.</span><span class="sxs-lookup"><span data-stu-id="350d4-111">You drop a shape onto the Visio page to launch the **Dependency Net Visio Shape Wizard** and set diagram options.</span></span>  
  
#### <a name="use-the-dependency-net-visio-shape-wizard"></a><span data-ttu-id="350d4-112">Используйте мастер фигур сети зависимостей Visio</span><span class="sxs-lookup"><span data-stu-id="350d4-112">Use the Dependency Net Visio Shape Wizard</span></span>  
  
1.  <span data-ttu-id="350d4-113">Если в списке **фигур** не отображаются **фигуры интеллектуального анализа данных Майкрософт** , щелкните **другие фигуры**, выберите **Открыть набор элементов**и откройте шаблон из расположения установки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="350d4-113">If you do not see **Microsoft Data Mining Shapes** in the **Shapes** list, click **More Shapes**, select **Open Stencil**, and open the template from the default installation location.</span></span>  
  
     <span data-ttu-id="350d4-114">\<drive>: \Program Files (x85) \Microsoft SQL Server 2012 надстройки DM</span><span class="sxs-lookup"><span data-stu-id="350d4-114">\<drive>:\Program files (x85)\Microsoft SQL Server 2012 DM Add-Ins</span></span>  
  
2.  <span data-ttu-id="350d4-115">Перетащите фигуру **Сеть зависимостей** на страницу, чтобы запустить мастер.</span><span class="sxs-lookup"><span data-stu-id="350d4-115">Drag the **Dependency Network** shape onto the page to start the wizard.</span></span> <span data-ttu-id="350d4-116">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="350d4-116">Click **Next**.</span></span>  
  
3.  <span data-ttu-id="350d4-117">На странице приветствия **мастера фигур сети зависимостей Visio**нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="350d4-117">On the welcome page of the **Dependency Network Visio Shape Wizard**, click **Next**.</span></span>  
  
4.  <span data-ttu-id="350d4-118">На странице **Выбор источника данных** **мастера фигур Visio в сети зависимостей**выберите соединение с [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] сервером, на котором находится модель, которую необходимо визуализировать.</span><span class="sxs-lookup"><span data-stu-id="350d4-118">On the **Select a Data Source** page of the **Dependency Network Visio Shape Wizard**, choose a connection to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server that has the model you want to visualize.</span></span>  
  
5.  <span data-ttu-id="350d4-119">Выберите подходящую модель интеллектуального анализа данных и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="350d4-119">Select an appropriate mining model, and click **Next**.</span></span>  
  
     <span data-ttu-id="350d4-120">Чтобы выбрать подходящую модель, можно проверить имя, описание, столбцы и тип данных на панели « **Свойства** ».</span><span class="sxs-lookup"><span data-stu-id="350d4-120">To select an appropriate model, you can review the name, description, columns, and type of data in the **Properties** pane.</span></span>  
  
     <span data-ttu-id="350d4-121">Эта фигура поддерживает модели, созданные с помощью следующих алгоритмов:</span><span class="sxs-lookup"><span data-stu-id="350d4-121">This shape supports models created by using these algorithms:</span></span>  
  
    -   <span data-ttu-id="350d4-122">Упрощенный алгоритм Байеса</span><span class="sxs-lookup"><span data-stu-id="350d4-122">Naïve Bayes</span></span>  
  
    -   <span data-ttu-id="350d4-123">Деревья решений</span><span class="sxs-lookup"><span data-stu-id="350d4-123">Decision Trees</span></span>  
  
    -   <span data-ttu-id="350d4-124">Правила взаимосвязей</span><span class="sxs-lookup"><span data-stu-id="350d4-124">Association Rules</span></span>  
  
6.  <span data-ttu-id="350d4-125">На странице **выберите узлы для подготовки к просмотру**, настройте размер диаграммы и при необходимости фильтр для включения только определенных узлов.</span><span class="sxs-lookup"><span data-stu-id="350d4-125">On the page, **Select Nodes to Render**, customize the size of the graph, and optionally filter to only include certain nodes.</span></span>  
  
     <span data-ttu-id="350d4-126">При наличии большого набора данных граф зависимостей может стать огромным и содержать множество связанных объектов, представленных в виде *узлов*.</span><span class="sxs-lookup"><span data-stu-id="350d4-126">With a large dataset, a dependency graph can become huge, and contain many related objects, represented as *nodes*.</span></span> <span data-ttu-id="350d4-127">С помощью этого диалогового окна можно создать пользовательскую диаграмму сети, которая будет включать только интересные узлы.</span><span class="sxs-lookup"><span data-stu-id="350d4-127">By using this dialog box, you can create a custom network graph that includes only the nodes of interest.</span></span>  
  
     <span data-ttu-id="350d4-128">[заполнитель рисунка]</span><span class="sxs-lookup"><span data-stu-id="350d4-128">[art placeholder]</span></span>  
  
     <span data-ttu-id="350d4-129">**Количество извлекаемых узлов**</span><span class="sxs-lookup"><span data-stu-id="350d4-129">**Number of nodes to fetch**</span></span>  
     <span data-ttu-id="350d4-130">Если в модели содержится меньшее количество узлов, чем указано, то такая установка не имеет действия.</span><span class="sxs-lookup"><span data-stu-id="350d4-130">If the model contains fewer than the specified number of nodes, this setting has no effect.</span></span> <span data-ttu-id="350d4-131">Если в модели содержится большее количество узлов, чем указано, то отображаются только самые стабильные узлы.</span><span class="sxs-lookup"><span data-stu-id="350d4-131">If the model contains more nodes than the specified number, only the strongest nodes are displayed.</span></span>  
  
     <span data-ttu-id="350d4-132">**Имя содержит**</span><span class="sxs-lookup"><span data-stu-id="350d4-132">**Name contains**</span></span>  
     <span data-ttu-id="350d4-133">Оставьте это поле пустым и нажмите зеленую стрелку, чтобы получить все узлы, содержащиеся в модели.</span><span class="sxs-lookup"><span data-stu-id="350d4-133">Leave this box blank and click the green arrow to retrieve all nodes in the model.</span></span>  
  
     <span data-ttu-id="350d4-134">Или введите строку и нажмите зеленую стрелку, чтобы вывести только те узлы, которые содержат введенную строку.</span><span class="sxs-lookup"><span data-stu-id="350d4-134">Or, type a string and click the green arrow to return only those nodes that contain the specified string.</span></span>  
  
     <span data-ttu-id="350d4-135">Большинство моделей, которые можно создать при помощи образцов данных не велики, поэтому в данном примере увеличим количество узлов до 10 и щелкнем зеленую стрелку, чтобы выполнить запрос и получить список всех узлов.</span><span class="sxs-lookup"><span data-stu-id="350d4-135">Most of the models that you can create with the sample data are not big, so for this example, increase the number of nodes to 10, and then click the green arrow to run a query and get the list of all nodes.</span></span>  
  
7.  <span data-ttu-id="350d4-136">Нажмите кнопку **Дополнительно** , чтобы задать параметры заливки и фигур для диаграммы.</span><span class="sxs-lookup"><span data-stu-id="350d4-136">Click **Advanced** to set shading and shape options for the graph.</span></span>  
  
8.  <span data-ttu-id="350d4-137">Нажмите кнопку **Закрыть** , чтобы закрыть диалоговое окно **Дополнительные** параметры, а затем нажмите кнопку **Готово** , чтобы создать диаграмму.</span><span class="sxs-lookup"><span data-stu-id="350d4-137">Click **Close** to exit the **Advanced** options dialog box, and then click **Finish** to create the graph.</span></span>  
  
## <a name="explore-and-modify-the-finished-diagram"></a><span data-ttu-id="350d4-138">Просмотр и изменение законченной диаграммы</span><span class="sxs-lookup"><span data-stu-id="350d4-138">Explore and Modify the Finished Diagram</span></span>  
 <span data-ttu-id="350d4-139">После того как Visio создаст диаграмму сети зависимостей, можно будет изменять и улучшать диаграмму при помощи функций Visio.</span><span class="sxs-lookup"><span data-stu-id="350d4-139">After Visio has created the network dependency graph, you can continue to modify and enhance the graph by using the features in Visio.</span></span>  
  
 <span data-ttu-id="350d4-140">На следующем рисунке показан макет по умолчанию диаграммы сети зависимостей.</span><span class="sxs-lookup"><span data-stu-id="350d4-140">The following graphic shows the default layout of a dependency network graph.</span></span>  
  
 <span data-ttu-id="350d4-141">[заполнитель рисунка]</span><span class="sxs-lookup"><span data-stu-id="350d4-141">[art placeholder]</span></span>  
  
1.  <span data-ttu-id="350d4-142">Используйте элемент управления **панорамой и масштабом** в области **задач** на ленте **представления** Visio, чтобы сосредоточиться на области диаграммы и перемещаться по диаграмме.</span><span class="sxs-lookup"><span data-stu-id="350d4-142">Use the **Pan and Zoom** control, in the **Task Pane** area of the Visio **View** ribbon, to focus on a section of the graph and move around the diagram.</span></span>  
  
2.  <span data-ttu-id="350d4-143">Поэкспериментируйте с различными макетами графов, предоставляемыми параметром Visio на **странице повторного макета** .</span><span class="sxs-lookup"><span data-stu-id="350d4-143">Experiment with different graph layouts provided by the Visio **Re-Layout Page** option.</span></span>  
  
3.  <span data-ttu-id="350d4-144">Щелкните ленту **надстройки** , а затем откройте одну из настраиваемых панелей инструментов, используемых для работы с диаграммами интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="350d4-144">Click the **Add-Ins** ribbon, and then display one of the custom toolbars used for working with data mining diagrams:</span></span>  
  
     <span data-ttu-id="350d4-145">**Макет**</span><span class="sxs-lookup"><span data-stu-id="350d4-145">**Layout**</span></span>  
     <span data-ttu-id="350d4-146">Оптимизирует макет узлов на странице и изменяет представление, чтобы были видны все узлы.</span><span class="sxs-lookup"><span data-stu-id="350d4-146">Optimizes the layout of nodes on the page, and changes the view so that all nodes are visible.</span></span>  
  
     <span data-ttu-id="350d4-147">**Изменение размера страницы**</span><span class="sxs-lookup"><span data-stu-id="350d4-147">**Resize Page**</span></span>  
     <span data-ttu-id="350d4-148">Изменяет размер страницы таким образом, чтобы все узлы были видны.</span><span class="sxs-lookup"><span data-stu-id="350d4-148">Changes the size of the page so that all nodes are visible.</span></span>  
  
     <span data-ttu-id="350d4-149">**Интенсивность ребра**</span><span class="sxs-lookup"><span data-stu-id="350d4-149">**Edge Strength**</span></span>  
     <span data-ttu-id="350d4-150">Переключает отображение интенсивности контуров во всей диаграмме.</span><span class="sxs-lookup"><span data-stu-id="350d4-150">Toggles display of edge strength for the entire graph.</span></span> <span data-ttu-id="350d4-151">Контур представляет собой соединение между узлами.</span><span class="sxs-lookup"><span data-stu-id="350d4-151">An edge is a connection between nodes.</span></span> <span data-ttu-id="350d4-152">Чтобы отфильтровать слабые связи, воспользуйтесь ползунком.</span><span class="sxs-lookup"><span data-stu-id="350d4-152">You can use the slider control to filter out connections that are not strong.</span></span>  
  
     <span data-ttu-id="350d4-153">**Ползунок**</span><span class="sxs-lookup"><span data-stu-id="350d4-153">**Slider**</span></span>  
     <span data-ttu-id="350d4-154">**Ползунок** помогает управлять интенсивностью связей, отображаемых на схеме сети зависимостей.</span><span class="sxs-lookup"><span data-stu-id="350d4-154">The **Slider** helps you control the strength of the relationships that are displayed in the dependency network diagram.</span></span>  
  
     <span data-ttu-id="350d4-155">Каждый узел этой диаграммы представляет одно состояние.</span><span class="sxs-lookup"><span data-stu-id="350d4-155">Each node in the graph represents a state.</span></span> <span data-ttu-id="350d4-156">Стрелка представляет переход между двумя состояниями и вероятность, связанную с этим переходом.</span><span class="sxs-lookup"><span data-stu-id="350d4-156">An arrow represents a transition between two states and the probability that is associated with the transition.</span></span> <span data-ttu-id="350d4-157">Чтобы уменьшить количество узлов в диаграмме, переместите ползунок вверх.</span><span class="sxs-lookup"><span data-stu-id="350d4-157">To reduce the number of nodes in the graph, move the slider bar up.</span></span>  
  
     <span data-ttu-id="350d4-158">Чтобы увеличить количество узлов в диаграмме, переместите ползунок вниз.</span><span class="sxs-lookup"><span data-stu-id="350d4-158">To increase the number of nodes in the graph, move the slider bar down.</span></span>  
  
     <span data-ttu-id="350d4-159">**Добавить элементы**</span><span class="sxs-lookup"><span data-stu-id="350d4-159">**Add Items**</span></span>  
     <span data-ttu-id="350d4-160">Открывает диалоговое окно **Выбор узлов для подготовки к просмотру** , в котором можно выбрать новые узлы для добавления в граф.</span><span class="sxs-lookup"><span data-stu-id="350d4-160">Opens the **Select Nodes to Render** dialog box so that you can select new nodes to add to the graph.</span></span>  
  
4.  <span data-ttu-id="350d4-161">Вы можете упростить или усложнить диаграммы по желанию, а также добавлять заметки, одновременно сохраняя подключение к модели.</span><span class="sxs-lookup"><span data-stu-id="350d4-161">You can make the graphs as simple or elaborate as you like, and add annotations, while staying connected to the model.</span></span>  
  
     <span data-ttu-id="350d4-162">[местозаполнитель для рисунка]</span><span class="sxs-lookup"><span data-stu-id="350d4-162">[ art placeholder]</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="350d4-163">Выделение зависимых узлов и другие параметры контекстного меню, которые были доступны в предыдущих версиях надстройки, не работают в Office 2013.</span><span class="sxs-lookup"><span data-stu-id="350d4-163">Highlighting of dependent nodes and other shortcut menu options that were available in previous versions of the Add-Ins do not work in Office 2013.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="350d4-164">См. также:</span><span class="sxs-lookup"><span data-stu-id="350d4-164">See Also</span></span>  
 [<span data-ttu-id="350d4-165">Устранение неполадок диаграмм интеллектуального анализа данных Visio &#40;SQL Server надстроек интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="350d4-165">Troubleshooting Visio Data Mining Diagrams &#40;SQL Server Data Mining Add-ins&#41;</span></span>](troubleshooting-visio-data-mining-diagrams-sql-server-data-mining-add-ins.md)  
  
  
