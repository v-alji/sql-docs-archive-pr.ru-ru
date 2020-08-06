---
title: Пошаговое руководство по диаграмме дерева принятия решений (надстройки интеллектуального анализа данных) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- shapes, data mining
- diagram, decision tree
- Visio shapes, decision tree
- decision tree [data mining]
ms.assetid: 9566f6a2-c750-4125-ba5e-42c7251a78c7
author: minewiskan
ms.author: owend
ms.openlocfilehash: bbe54db1ab3d00d074917db770a9a731f884f49a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658531"
---
# <a name="decision-tree-diagram-walkthrough--data-mining-add-ins"></a><span data-ttu-id="0b6ad-102">Пошаговое руководство по диаграмме дерева принятия решений (надстройки интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="0b6ad-102">Decision Tree Diagram Walkthrough  (Data Mining Add-ins)</span></span>
  <span data-ttu-id="0b6ad-103">При создании модели дерева принятия решений, можно создать настраиваемую диаграмму в Visio при помощи либо фигуры дерева принятия решений, либо фигуры сети зависимостей.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-103">If you have created a decision tree model, you can create a customized diagram in Visio by using either the Decision Tree shape or the Dependency Network shape.</span></span> <span data-ttu-id="0b6ad-104">В этом разделе описываются настройки, которые можно выполнять с помощью формы **дерева принятия решений** и следующих элементов управления.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-104">This topic describes the customizations you can perform using the **Decision Tree** shape and these controls:</span></span>  
  
-   <span data-ttu-id="0b6ad-105">элементов управления отрисовкой диаграммы дерева принятия решений.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-105">Rendering controls for the decision tree diagram</span></span>  
  
     <span data-ttu-id="0b6ad-106">Эти параметры являются частью **мастера дерева принятия решений** , который запускается при перетаскивании фигуры в рабочую область Visio.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-106">These options are part of the **Decision Tree Wizard** that is launched when you drop a shape into the Visio workspace.</span></span>  
  
-   <span data-ttu-id="0b6ad-107">Панель инструментов **макета интеллектуального анализа данных**</span><span class="sxs-lookup"><span data-stu-id="0b6ad-107">**Data Mining Layout** toolbar</span></span>  
  
     <span data-ttu-id="0b6ad-108">Эти параметры добавляется в рабочую область Visio для последующей работы с фигурой.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-108">These options are added to the Visio workspace to help you interact with the shape.</span></span>  
  
## <a name="build-a-decision-tree-diagram"></a><span data-ttu-id="0b6ad-109">Создайте диаграмму дерева принятия решений</span><span class="sxs-lookup"><span data-stu-id="0b6ad-109">Build a Decision Tree Diagram</span></span>  
 <span data-ttu-id="0b6ad-110">Фигуру дерева принятия решений можно перетащить на страницу Visio, чтобы запустить **Мастер фигур Visio в дереве решений** и задать параметры схемы.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-110">You drop the Decision Tree shape onto the Visio page to launch the **Decision Tree Visio Shape Wizard** and set diagram options.</span></span>  
  
#### <a name="use-the-decision-tree-wizard"></a><span data-ttu-id="0b6ad-111">Используйте мастер дерева принятия решений</span><span class="sxs-lookup"><span data-stu-id="0b6ad-111">Use the Decision Tree Wizard</span></span>  
  
1.  <span data-ttu-id="0b6ad-112">Если в списке **фигур** не отображаются **фигуры интеллектуального анализа данных Майкрософт** , щелкните **другие фигуры**, выберите **Открыть набор элементов**и откройте шаблон из расположения установки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-112">If you do not see **Microsoft Data Mining Shapes** in the **Shapes** list, click **More Shapes**, select **Open Stencil**, and open the template from the default installation location.</span></span>  
  
     <span data-ttu-id="0b6ad-113">\<drive>: \Program Files (x85) \Microsoft SQL Server 2012 надстройки DM</span><span class="sxs-lookup"><span data-stu-id="0b6ad-113">\<drive>:\Program files (x85)\Microsoft SQL Server 2012 DM Add-Ins</span></span>  
  
2.  <span data-ttu-id="0b6ad-114">Перетащите на страницу фигуру **дерева принятия решений** .</span><span class="sxs-lookup"><span data-stu-id="0b6ad-114">Drag the **Decision Tree** shape onto the page.</span></span>  
  
3.  <span data-ttu-id="0b6ad-115">На странице приветствия **мастера фигур Visio в дереве решений**нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-115">On the welcome page of the **Decision Tree Visio Shape Wizard**, click **Next**.</span></span>  
  
4.  <span data-ttu-id="0b6ad-116">На странице **Выбор источника данных** **мастера кластеров**выберите соединение с [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] сервером, на котором находится модель, которую необходимо визуализировать.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-116">On the **Select a Data Source** page of the **Cluster Wizard**, choose a connection to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server that has the model you want to visualize.</span></span>  
  
5.  <span data-ttu-id="0b6ad-117">Выберите подходящую модель интеллектуального анализа данных и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-117">Select an appropriate mining model, and click **Next**.</span></span>  
  
     <span data-ttu-id="0b6ad-118">Этот тип диаграммы поддерживает модели, созданные с использованием дерева принятия решений и алгоритма линейной регрессии.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-118">This diagram type supports models created using the Decision Trees or Linear Regression algorithm.</span></span>  
  
6.  <span data-ttu-id="0b6ad-119">На странице **Выбор дерева решений** выберите отдельное дерево для просмотра.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-119">On the **Select Decision Tree** page, choose an individual tree to display.</span></span>  
  
     <span data-ttu-id="0b6ad-120">Дерево моделирует взаимодействия, ведущие к определенному результату, который вы моделируете. Таким образом, даже если модель содержит несколько результатов, в каждый момент времени можно отобразить только одно дерево.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-120">A tree models the interactions that lead to a particular outcome you've modeled; therefore, even if your model contains multiple outcomes, you can display only one tree at a time.</span></span>  
  
7.  <span data-ttu-id="0b6ad-121">В диалоговом окне **Выбор дерева решений** можно также задать следующие параметры подготовки к просмотру:</span><span class="sxs-lookup"><span data-stu-id="0b6ad-121">In the **Select Decision Tree** dialog box, you can also set these rendering options:</span></span>  
  
     <span data-ttu-id="0b6ad-122">**Максимальная глубина отрисовки**</span><span class="sxs-lookup"><span data-stu-id="0b6ad-122">**Maximum Rendering Depth**</span></span>  
     <span data-ttu-id="0b6ad-123">Используйте этот параметр, чтобы назначить отображаемое количество узлов.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-123">Use this option to control how many nodes are displayed.</span></span>  
  
     <span data-ttu-id="0b6ad-124">Дерево принятия решений может быть очень большим, и его диаграмма может не поместиться на странице.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-124">A decision tree might go very deep, creating a diagram that does not fit on the page.</span></span> <span data-ttu-id="0b6ad-125">Используйте этот элемент управления для фокусировки на узлах в крайнем левом положении, которые являются наиболее важными.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-125">Use this control to focus on the leftmost nodes, which are more important.</span></span>  
  
     <span data-ttu-id="0b6ad-126">По умолчанию отображаются 3 уровня узлов.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-126">The default is three levels of nodes.</span></span>  
  
     <span data-ttu-id="0b6ad-127">**Выберите цвет и отобразите текст для значений**</span><span class="sxs-lookup"><span data-stu-id="0b6ad-127">**Select color and display text for values**</span></span>  
     <span data-ttu-id="0b6ad-128">Выберите цвет, который будет означать каждый из результатов.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-128">Choose the color that will represent each one of the outcomes.</span></span> <span data-ttu-id="0b6ad-129">Если не указать цвета, они автоматически создаются с использованием текущих цветов видеотемы.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-129">If you do not specify colors, they are automatically generated using the current video theme colors.</span></span>  
  
8.  <span data-ttu-id="0b6ad-130">Нажмите кнопку **Дополнительно** , чтобы настроить следующие параметры для каждого узла в схеме дерева принятия решений.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-130">Click **Advanced** to customize the following options for each of the nodes in the decision tree diagram.</span></span>  
  
     <span data-ttu-id="0b6ad-131">Изменение переменной и **состояния** **заливки**</span><span class="sxs-lookup"><span data-stu-id="0b6ad-131">**Shading Variable** and **State**</span></span>  
     <span data-ttu-id="0b6ad-132">Выберите целевой результат, который будет отображаться в дереве.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-132">Choose the target outcome that you want to show in the tree diagram.</span></span>  
  
     <span data-ttu-id="0b6ad-133">**Показать гистограмму**</span><span class="sxs-lookup"><span data-stu-id="0b6ad-133">**Show Histogram**</span></span>  
     <span data-ttu-id="0b6ad-134">К каждому узлу добавляется диаграмма, показывающая правила, которые определяют этот узел.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-134">Adds a chart to each node that shows the rules that define that node.</span></span>  
  
     <span data-ttu-id="0b6ad-135">**Показать метку**</span><span class="sxs-lookup"><span data-stu-id="0b6ad-135">**Show Label**</span></span>  
     <span data-ttu-id="0b6ad-136">Добавляет в гистограмму имена столбцов.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-136">Adds column names to the histogram.</span></span>  
  
     <span data-ttu-id="0b6ad-137">**Показать вероятность**</span><span class="sxs-lookup"><span data-stu-id="0b6ad-137">**Show Probability**</span></span>  
     <span data-ttu-id="0b6ad-138">Показывает вероятность каждого значения.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-138">Displays the probability of each value.</span></span>  
  
     <span data-ttu-id="0b6ad-139">**Показать несущее множество**</span><span class="sxs-lookup"><span data-stu-id="0b6ad-139">**Show Support**</span></span>  
     <span data-ttu-id="0b6ad-140">Показывает несущее множество для каждого значения.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-140">Displays the support for each value.</span></span>  
  
     <span data-ttu-id="0b6ad-141">**Показать нижний колонтитул**</span><span class="sxs-lookup"><span data-stu-id="0b6ad-141">**Show Footer**</span></span>  
     <span data-ttu-id="0b6ad-142">Добавляет нижний колонтитул, в котором перечисляются все отображаемые значения.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-142">Adds a footer that sums all displayed values.</span></span>  
  
     <span data-ttu-id="0b6ad-143">**Показать верхний колонтитул**</span><span class="sxs-lookup"><span data-stu-id="0b6ad-143">**Show Header**</span></span>  
     <span data-ttu-id="0b6ad-144">Добавляет заголовки столбцов.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-144">Adds column headings.</span></span>  
  
     <span data-ttu-id="0b6ad-145">**Показать состояния с пустым несущим множеством**</span><span class="sxs-lookup"><span data-stu-id="0b6ad-145">**Show states with zero support**</span></span>  
     <span data-ttu-id="0b6ad-146">Позволяет отобразить отсутствующие значения.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-146">Lets you display missing values.</span></span>  
  
9. <span data-ttu-id="0b6ad-147">Нажмите кнопку **Готово** , чтобы создать диаграмму.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-147">Click **Finish** to create the graph.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="0b6ad-148">В некоторых средах соединители на диаграмме могут не отрисовываться в Office 2013.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-148">In some environments, connectors in the chart might fail to render in Office 2013.</span></span>  
  
## <a name="explore-and-modify-the-finished-diagram"></a><span data-ttu-id="0b6ad-149">Просмотр и изменение законченной диаграммы</span><span class="sxs-lookup"><span data-stu-id="0b6ad-149">Explore and Modify the Finished Diagram</span></span>  
 <span data-ttu-id="0b6ad-150">После завершения работы **мастера фигур Visio в дереве решений**Visio создает на странице древовидную диаграмму, которая отображает правила, ведущие к прогнозируемому результату.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-150">After you have completed the **Decision Tree Visio Shape Wizard**, Visio creates a tree diagram on the page that graphically displays the rules that lead to the predicted outcome.</span></span>  
  
 <span data-ttu-id="0b6ad-151">Вы можете продолжить изменять форму при помощи следующих элементов управления диаграммами дерева принятия решений.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-151">You can continue to modify the shape by using the following controls for decision tree diagrams:</span></span>  
  
#### <a name="using-the-decision-tree-option-menus"></a><span data-ttu-id="0b6ad-152">Использование меню параметров дерева принятия решений</span><span class="sxs-lookup"><span data-stu-id="0b6ad-152">Using the decision tree option menus</span></span>  
  
1.  <span data-ttu-id="0b6ad-153">Щелкните ленту **надстройки** , а затем откройте одну из настраиваемых панелей инструментов, используемых для работы с диаграммами интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-153">Click the **Add-Ins** ribbon, and then display one of the custom toolbars used for working with data mining diagrams:</span></span>  
  
     <span data-ttu-id="0b6ad-154">**Макет**</span><span class="sxs-lookup"><span data-stu-id="0b6ad-154">**Layout**</span></span>  
     <span data-ttu-id="0b6ad-155">Улучшает размещение дерева, в соответствии с текущей страницей.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-155">Optimizes the arrangement of the tree to fit the current page.</span></span>  
  
     <span data-ttu-id="0b6ad-156">**Изменение размера страницы**</span><span class="sxs-lookup"><span data-stu-id="0b6ad-156">**Resize Page**</span></span>  
     <span data-ttu-id="0b6ad-157">Этот элемент управления был предназначен для предыдущих версий HTML.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-157">This control was intended for earlier HTML versions.</span></span> <span data-ttu-id="0b6ad-158">Используйте элементы управления изменением размера страницы Visio.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-158">Use the Visio page resizing controls instead,</span></span>  
  
     <span data-ttu-id="0b6ad-159">**Описание**</span><span class="sxs-lookup"><span data-stu-id="0b6ad-159">**Description**</span></span>  
     <span data-ttu-id="0b6ad-160">Если выбран узел дерева, выберите этот параметр, чтобы отобразить подробные сведения о вариантах в узле.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-160">When a node of the tree is selected, click this option to display details about the cases in the node.</span></span>  
  
2.  <span data-ttu-id="0b6ad-161">Используйте параметр **страница изменить макет** на ленте **конструктора** Visio, чтобы поэкспериментировать с различными макетами дерева.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-161">Use the **Re-Layout Page** option in the Visio **Design** ribbon to experiment with different tree layouts.</span></span>  
  
3.  <span data-ttu-id="0b6ad-162">Используйте параметр **соединители** на вкладке **конструктор** , чтобы изменить соединители, используемые между узлами в дереве.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-162">Use the **Connectors** option on the **Design** tab to change the connectors used between nodes in the tree.</span></span>  
  
4.  <span data-ttu-id="0b6ad-163">Используйте элемент управления **панорамой и масштабом** в области **задач** на ленте **представления** Visio, чтобы сосредоточиться на определенной области схемы.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-163">Use the **Pan and Zoom** control, in the **Task Pane** area of the Visio **View** ribbon, to focus on a particular area of the diagram.</span></span>  
  
5.  <span data-ttu-id="0b6ad-164">Щелкните правой кнопкой любой узел дерева и выберите один из параметров контекстного меню, связанный с диаграммой дерева принятия решений.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-164">Right-click any node in the tree, and choose from these shortcut menu options specific to decision tree diagrams:</span></span>  
  
     <span data-ttu-id="0b6ad-165">**Улучшить макет страницы**</span><span class="sxs-lookup"><span data-stu-id="0b6ad-165">**Improve Page Layout**</span></span>  
     <span data-ttu-id="0b6ad-166">Распределяет узлы равномерно по странице и настраивает представление страницы таким образом, чтобы на ней отображались все узлы.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-166">Distributes the nodes evenly on the page and adjusts the page view to see all nodes.</span></span>  
  
     <span data-ttu-id="0b6ad-167">**Переместить дочерние элементы на новую страницу**</span><span class="sxs-lookup"><span data-stu-id="0b6ad-167">**Move Children to New Page**</span></span>  
     <span data-ttu-id="0b6ad-168">Перемещает дочерние узлы того узла, который выбран в настоящее время, на новую страницу.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-168">Moves the children of the currently selected node to a new page.</span></span>  
  
     <span data-ttu-id="0b6ad-169">**Свернуть дочерние узлы**</span><span class="sxs-lookup"><span data-stu-id="0b6ad-169">**Collapse Child Nodes**</span></span>  
     <span data-ttu-id="0b6ad-170">Скрывает дочерние узлы для выбранного узла.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-170">Hides the children of the currently selected node.</span></span>  
  
     <span data-ttu-id="0b6ad-171">**Развернуть дочерние узлы**</span><span class="sxs-lookup"><span data-stu-id="0b6ad-171">**Expand Child Nodes**</span></span>  
     <span data-ttu-id="0b6ad-172">Отображает дочерние узлы выбранного узла.</span><span class="sxs-lookup"><span data-stu-id="0b6ad-172">Displays the children of the currently selected node.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b6ad-173">См. также:</span><span class="sxs-lookup"><span data-stu-id="0b6ad-173">See Also</span></span>  
 [<span data-ttu-id="0b6ad-174">Устранение неполадок диаграмм интеллектуального анализа данных Visio &#40;SQL Server надстроек интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="0b6ad-174">Troubleshooting Visio Data Mining Diagrams &#40;SQL Server Data Mining Add-ins&#41;</span></span>](troubleshooting-visio-data-mining-diagrams-sql-server-data-mining-add-ins.md)  
  
  
