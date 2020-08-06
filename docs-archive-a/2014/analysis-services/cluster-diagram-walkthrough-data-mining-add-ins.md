---
title: Пошаговое руководство по диаграмме кластера (надстройки интеллектуального анализа данных) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Visio shapes, cluster
- diagram, cluster
- shapes, data mining
- shapes, cluster
- data mining layout toolbar
ms.assetid: 761bef6a-37d4-4b19-944e-f2aadc75a242
author: minewiskan
ms.author: owend
ms.openlocfilehash: 44ee8cce3cd2498d765c9b69e7f352b49cb0f115
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657402"
---
# <a name="cluster-diagram-walkthrough-data-mining-add-ins"></a><span data-ttu-id="fbdcb-102">Пошаговое руководство по диаграмме кластеров (надстройки интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="fbdcb-102">Cluster Diagram Walkthrough (Data Mining Add-ins)</span></span>
  <span data-ttu-id="fbdcb-103">После создания модели кластеризации ее можно импортировать в Visio с помощью фигуры **кластера** , а затем продолжить настройку и расширение макета.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-103">After you have created a clustering model, you can import it into Visio using the **Cluster** shape and then continue to customize and enhance the layout.</span></span> <span data-ttu-id="fbdcb-104">**Фигуры интеллектуального анализа данных для Visio** включают следующие пользовательские элементы управления для работы с диаграммами интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-104">The **Data Mining Shapes for Visio** include the following custom controls for working with data mining diagrams:</span></span>  
  
-   <span data-ttu-id="fbdcb-105">создание элементов управления для диаграммы кластеров.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-105">Rendering controls for the cluster diagram</span></span>  
  
     <span data-ttu-id="fbdcb-106">Эти параметры являются частью **мастера кластеров** , который запускается при перетаскивании фигуры в рабочую область Visio.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-106">These options are part of the **Cluster Wizard** that is launched when you drop a shape into the Visio workspace.</span></span>  
  
-   <span data-ttu-id="fbdcb-107">Панель инструментов **макета интеллектуального анализа данных**</span><span class="sxs-lookup"><span data-stu-id="fbdcb-107">**Data Mining Layout** toolbar</span></span>  
  
     <span data-ttu-id="fbdcb-108">Эти параметры добавляется в рабочую область Visio для последующей работы с фигурами интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-108">These options are added to the Visio workspace to help you interact with the data mining shape.</span></span> <span data-ttu-id="fbdcb-109">Параметры различаются в зависимости от используемого типа модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-109">The options are different depending on which type of data mining model you are using.</span></span>  
  
## <a name="build-a-cluster-diagram"></a><span data-ttu-id="fbdcb-110">Создание диаграммы кластеров</span><span class="sxs-lookup"><span data-stu-id="fbdcb-110">Build a Cluster Diagram</span></span>  
 <span data-ttu-id="fbdcb-111">Это пошаговое руководство демонстрирует, как можно создать и настроить диаграмму кластеризации в Visio.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-111">This walkthrough demonstrates how to build and customize a clustering diagram in Visio.</span></span>  
  
 <span data-ttu-id="fbdcb-112">Чтобы следовать описанным шагам, следует иметь готовую модель кластеризации.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-112">To follow along, you should have a clustering model already available.</span></span> <span data-ttu-id="fbdcb-113">Если модель отсутствует, используйте [Мастер кластеров &#40;мастере надстроек интеллектуального анализа данных для Excel&#41;](cluster-wizard-data-mining-add-ins-for-excel.md) и создайте модель с помощью набора обучающих данных в образце книги, используя все значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-113">If you do not have a model, use the [Cluster Wizard &#40;Data Mining Add-ins for Excel&#41;](cluster-wizard-data-mining-add-ins-for-excel.md) wizard and create a model using the Training data set in the sample workbook, using all the defaults.</span></span>  
  
#### <a name="use-the-cluster-visio-shape-wizard"></a><span data-ttu-id="fbdcb-114">Используйте мастер фигур Visio в кластере</span><span class="sxs-lookup"><span data-stu-id="fbdcb-114">Use the Cluster Visio Shape Wizard</span></span>  
  
1.  <span data-ttu-id="fbdcb-115">Если в списке **фигур** не отображаются **фигуры интеллектуального анализа данных Майкрософт** , щелкните **другие фигуры**, выберите **Открыть набор элементов**и откройте шаблон из расположения установки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-115">If you do not see **Microsoft Data Mining Shapes** in the **Shapes** list, click **More Shapes**, select **Open Stencil**, and open the template from the default installation location.</span></span>  
  
     <span data-ttu-id="fbdcb-116">\<drive>: \Program files\Microsoft SQL Server 2012, надстройки DM</span><span class="sxs-lookup"><span data-stu-id="fbdcb-116">\<drive>:\Program files\Microsoft SQL Server 2012 DM Add-Ins</span></span>  
  
2.  <span data-ttu-id="fbdcb-117">Перетащите фигуру **кластера** на страницу.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-117">Drag the **Cluster** shape onto the page.</span></span>  
  
3.  <span data-ttu-id="fbdcb-118">На странице приветствия **мастера фигур Visio в кластере**нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-118">On the welcome page of the **Cluster Visio Shape Wizard**, click **Next**.</span></span>  
  
4.  <span data-ttu-id="fbdcb-119">На странице **Выбор источника данных** **мастера кластеров**выберите подключение к [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] серверу, содержащему модели интеллектуального анализа данных, которые необходимо визуализировать.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-119">On the **Select a Data Source** page of the **Cluster Wizard**, choose a connection to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server that contains the data mining models you want to visualize.</span></span>  
  
5.  <span data-ttu-id="fbdcb-120">Выберите подходящую модель интеллектуального анализа данных и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-120">Select an appropriate mining model, and click **Next**.</span></span>  
  
     <span data-ttu-id="fbdcb-121">Чтобы убедиться, что выбрана модель кластеризации, проверьте описание на панели **свойств** .</span><span class="sxs-lookup"><span data-stu-id="fbdcb-121">To make sure you choose a clustering model, review the description in the **Properties** pane.</span></span>  
  
6.  <span data-ttu-id="fbdcb-122">Если подключение установлено успешно, на странице **Параметры диаграммы кластеров**выберите тип диаграммы кластеров для включения в презентацию Visio:</span><span class="sxs-lookup"><span data-stu-id="fbdcb-122">If the connection is successful, on the page, **Options for cluster diagram**, you decide which type of cluster diagram to include in your Visio presentation:</span></span>  
  
     <span data-ttu-id="fbdcb-123">**Отображать только фигуры кластеров**</span><span class="sxs-lookup"><span data-stu-id="fbdcb-123">**Show cluster shapes only**</span></span>  
     <span data-ttu-id="fbdcb-124">Данный параметр создает простую диаграмму кластеров, при этом каждый кластер может отображаться в виде прямоугольника или любой другой формы, которую вы можете выбрать.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-124">This option creates a simple cluster diagram, with each cluster represented by a rectangle or other shape you choose</span></span>  
  
     <span data-ttu-id="fbdcb-125">**Отображать кластеры с диаграммой характеристик**</span><span class="sxs-lookup"><span data-stu-id="fbdcb-125">**Show clusters with characteristics chart**</span></span>  
     <span data-ttu-id="fbdcb-126">Этот параметр позволяет создать диаграмму, аналогичную предыдущей, однако внутри ее форм представлены гистограммы, описывающие характеристики кластера.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-126">This option creates the same chart as above, but inside the shapes are histograms that describe the characteristics of the cluster.</span></span>  
  
     <span data-ttu-id="fbdcb-127">![Пример диаграммы характеристик кластера в Visio](media/dm13-visio-cluster-samplecharshape.gif "Пример диаграммы характеристик кластера в Visio")</span><span class="sxs-lookup"><span data-stu-id="fbdcb-127">![Example of cluster characteristics chart in Visio](media/dm13-visio-cluster-samplecharshape.gif "Example of cluster characteristics chart in Visio")</span></span>  
  
     <span data-ttu-id="fbdcb-128">**Отображать кластеры с диаграммой сравнения**</span><span class="sxs-lookup"><span data-stu-id="fbdcb-128">**Show clusters with discrimination chart**</span></span>  
     <span data-ttu-id="fbdcb-129">Этот параметр создает точно такую же схему, что и диаграмма кластеров, однако в ней приводится список характеристик текущего кластера, которыми он наиболее сильно отличается от других кластеров.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-129">This option creates the same chart as the cluster diagram, but instead lists the characteristics of the current cluster that most strongly distinguish it from other clusters.</span></span>  
  
     <span data-ttu-id="fbdcb-130">Можно переключиться на другой тип диаграммы после того, как мастер создаст диаграмму. Для этого щелкните кластер правой кнопкой мыши и выберите новый тип диаграммы.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-130">You can switch to another chart type after the wizard has built the diagram, by right-clicking a cluster and selecting a new chart type.</span></span> <span data-ttu-id="fbdcb-131">Пока выберите параметр **Показывать кластеры с диаграммой характеристик**.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-131">For now, choose the option, **Show clusters with characteristics chart**.</span></span>  
  
7.  <span data-ttu-id="fbdcb-132">Оставьте параметр, **число строк в диаграмме**, равное 5.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-132">Leave the option, **Number of rows in the chart**, as 5.</span></span>  
  
     <span data-ttu-id="fbdcb-133">Этот параметр не изменяет число кластеров в модели. Он просто ограничивает количество атрибутов, которые могут отображаться как функции каждого кластера.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-133">This option doesn't change the number of clusters in the model; it simply limits the number of attributes that can be displayed as features of each cluster.</span></span>  
  
     <span data-ttu-id="fbdcb-134">Однако этот параметр действует как фильтр для данных диаграммы, поэтому вы не можете увеличить число элементов позже.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-134">However, the option acts as a filter on the chart data, so you can't increase the number of items later.</span></span>  
  
8.  <span data-ttu-id="fbdcb-135">Нажмите кнопку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-135">Click **Advanced**.</span></span>  
  
     <span data-ttu-id="fbdcb-136">Диалоговое окно **Параметры кластера** используется для настройки внешнего вида фигур, используемых на схеме.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-136">The **Cluster Options** dialog box is where you customize the visual appearance of shapes used in the diagram.</span></span> <span data-ttu-id="fbdcb-137">Можно изменить цвета, используемые на диаграмме, и фигуру, используемую для кластеров.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-137">You can change the colors used in the graph, and the shape used for clusters.</span></span>  
  
     <span data-ttu-id="fbdcb-138">Элемент управления " **Переменная заливки** " не работает в Office 2013.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-138">The **Shading Variable** control does not work in Office 2013.</span></span>  
  
     <span data-ttu-id="fbdcb-139">![нажмите кнопку «Дополнительно», чтобы выбрать цвета фигуры](media/dm13-visio-clusteroptions-advanced.gif "нажмите кнопку «Дополнительно», чтобы выбрать цвета фигуры")</span><span class="sxs-lookup"><span data-stu-id="fbdcb-139">![click Advanced to choose shape colors](media/dm13-visio-clusteroptions-advanced.gif "click Advanced to choose shape colors")</span></span>  
  
     <span data-ttu-id="fbdcb-140">**Совет.** Некоторые цвета можно изменить позже с помощью тем Visio и элементов управления редактированием фигур.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-140">**Tip:** Some colors can be altered later by using Visio themes and shape editing controls.</span></span> <span data-ttu-id="fbdcb-141">Однако темы Visio также переопределяют некоторые из выбранных цветов, поэтому рекомендуется начать с цветами по умолчанию и применять изменения постепенно.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-141">However, Visio themes will also override some of these color selections, so we recommend starting with the default colors and gradually applying changes.</span></span>  
  
9. <span data-ttu-id="fbdcb-142">Нажмите кнопку **Готово** , чтобы создать диаграмму.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-142">Click **Finish** to create the graph.</span></span>  
  
     <span data-ttu-id="fbdcb-143">Мастер извлекает сведения из модели интеллектуального анализа данных, отображает фигуры и заполняет каждый кластер атрибутами и значениями.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-143">The wizard retrieves information from the data mining model, renders the shapes, and populates each cluster with attributes and values.</span></span>  
  
     <span data-ttu-id="fbdcb-144">![сеть зависимостей](media/dm13-visiodepnet-defaultgraph.gif "сеть зависимостей")</span><span class="sxs-lookup"><span data-stu-id="fbdcb-144">![a dependency network](media/dm13-visiodepnet-defaultgraph.gif "a dependency network")</span></span>  
  
## <a name="explore-and-modify-the-finished-diagram"></a><span data-ttu-id="fbdcb-145">Просмотр и изменение законченной диаграммы</span><span class="sxs-lookup"><span data-stu-id="fbdcb-145">Explore and Modify the Finished Diagram</span></span>  
 <span data-ttu-id="fbdcb-146">После завершения создания диаграммы можно продолжить настройку внешнего вида с помощью элементов управления Visio, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-146">After the diagram is complete, you can continue to customize the appearance using the Visio controls, as shown in the following example.</span></span>  
  
 <span data-ttu-id="fbdcb-147">![диаграмма кластеров, настроенная с помощью Visio](media/dm13-visio-clustercomplete1.gif "диаграмма кластеров, настроенная с помощью Visio")</span><span class="sxs-lookup"><span data-stu-id="fbdcb-147">![cluster diagram customized using Visio](media/dm13-visio-clustercomplete1.gif "cluster diagram customized using Visio")</span></span>  
  
 <span data-ttu-id="fbdcb-148">Все основные формы кластеров формируются мастером. Используйте следующие средства для обновления и персонализации диаграммы.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-148">All of the basic cluster shapes are generated by the wizard; use the following tools to update and personalize the diagram:</span></span>  
  
1.  <span data-ttu-id="fbdcb-149">Перетащите ползунок в элементе управления " **Параметры кластера** ", чтобы отфильтровать более слабые связи и упростить диаграмму.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-149">Drag the slider in the **Cluster Options** control, to filter out weaker relationships and simplify the diagram.</span></span>  
  
2.  <span data-ttu-id="fbdcb-150">Используйте параметр **страница повторного макета** Visio, чтобы поэкспериментировать с различными структурами кластеров.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-150">Use the Visio **Re-Layout Page** option to experiment with different cluster layouts.</span></span>  
  
3.  <span data-ttu-id="fbdcb-151">Используйте параметр **соединители** на вкладке **конструктор** , чтобы изменить стиль соединителя так, чтобы строки пересекается с кластерами.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-151">Use the **Connectors** option on the **Design** tab to change the connector style to keep lines from crossing over clusters.</span></span>  
  
4.  <span data-ttu-id="fbdcb-152">Щелкните ленту **надстройки** , а затем откройте одну из настраиваемых панелей инструментов, используемых для работы с диаграммами интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-152">Click the **Add-Ins** ribbon, and then display one of the custom toolbars used for working with data mining diagrams:</span></span>  
  
     <span data-ttu-id="fbdcb-153">**Макет**</span><span class="sxs-lookup"><span data-stu-id="fbdcb-153">**Layout**</span></span>  
     <span data-ttu-id="fbdcb-154">Оптимизирует расположение кластеров для улучшения их размещения на текущей странице.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-154">Optimizes the arrangement of clusters to fit in the current page.</span></span>  
  
     <span data-ttu-id="fbdcb-155">**Изменение размера страницы**</span><span class="sxs-lookup"><span data-stu-id="fbdcb-155">**Resize Page**</span></span>  
     <span data-ttu-id="fbdcb-156">Этот элемент управления был предназначен для предыдущих версий HTML.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-156">This control was intended for earlier HTML versions.</span></span> <span data-ttu-id="fbdcb-157">Используйте элементы управления изменением размера страницы Visio.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-157">Use the Visio page resizing controls instead.</span></span>  
  
     <span data-ttu-id="fbdcb-158">**Описание**</span><span class="sxs-lookup"><span data-stu-id="fbdcb-158">**Description**</span></span>  
     <span data-ttu-id="fbdcb-159">Если выбран кластер, щелкните этот параметр, чтобы отобразить сведения о кластере.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-159">If a cluster is selected, click this option to display details about the cluster.</span></span>  
  
     <span data-ttu-id="fbdcb-160">![щелкните «Описание», чтобы получить подробные сведения о кластере](media/dm13-visio-cluster-description-control.gif "щелкните «Описание», чтобы получить подробные сведения о кластере")</span><span class="sxs-lookup"><span data-stu-id="fbdcb-160">![click Description to get details about the cluster](media/dm13-visio-cluster-description-control.gif "click Description to get details about the cluster")</span></span>  
  
     <span data-ttu-id="fbdcb-161">**Интенсивность ребра**</span><span class="sxs-lookup"><span data-stu-id="fbdcb-161">**Edge Strength**</span></span>  
     <span data-ttu-id="fbdcb-162">Указывает степень достоверности для линий, соединяющих кластеры.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-162">Displays confidence scores on the lines connecting clusters.</span></span>  
  
     <span data-ttu-id="fbdcb-163">Однако, если вы примените любое особое форматирование, отличное от форматирования по умолчанию мастера, в том числе с использованием некоторых фонов, возможно, эти цифры будут невидимы.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-163">However, if you apply any special formatting other than the default generated by the wizard, including some backgrounds, these numbers might not be visible.</span></span>  
  
     <span data-ttu-id="fbdcb-164">**Ползунок**</span><span class="sxs-lookup"><span data-stu-id="fbdcb-164">**Slider**</span></span>  
     <span data-ttu-id="fbdcb-165">Фильтрует строки между кластерами.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-165">Filters the lines between clusters.</span></span> <span data-ttu-id="fbdcb-166">Перемещение ползунка вверх удаляет все, кроме наиболее важных взаимосвязей.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-166">Moving the slider up removes all but the most important associations.</span></span>  
  
     <span data-ttu-id="fbdcb-167">**Заливка**</span><span class="sxs-lookup"><span data-stu-id="fbdcb-167">**Shading**</span></span>  
     <span data-ttu-id="fbdcb-168">Этот элемент управления не работает в Office 2013.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-168">This control does not work in Office 2013.</span></span>  
  
5.  <span data-ttu-id="fbdcb-169">Используйте элемент управления **панорамой и масштабом** в области **задач** на ленте **представления** Visio, чтобы сосредоточиться на наборе кластеров и перемещаться по схеме.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-169">Use the **Pan and Zoom** control, in the **Task Pane** area of the Visio **View** ribbon, to focus on a set of clusters and move around the diagram.</span></span>  
  
6.  <span data-ttu-id="fbdcb-170">Щелкните правой кнопкой мыши любой кластер, чтобы увидеть параметры, характерные для формы кластера.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-170">Right-click any cluster to see options specific to the cluster shape:</span></span>  
  
    -   <span data-ttu-id="fbdcb-171">Изменение стиля диаграммы.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-171">Change the chart style.</span></span>  
  
    -   <span data-ttu-id="fbdcb-172">Добавление диаграммы характеристик кластера.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-172">Add a cluster characteristics chart.</span></span>  
  
    -   <span data-ttu-id="fbdcb-173">Добавление диаграммы сравнения кластеров.</span><span class="sxs-lookup"><span data-stu-id="fbdcb-173">Add a cluster discrimination chart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbdcb-174">См. также:</span><span class="sxs-lookup"><span data-stu-id="fbdcb-174">See Also</span></span>  
 [<span data-ttu-id="fbdcb-175">Устранение неполадок диаграмм интеллектуального анализа данных Visio &#40;SQL Server надстроек интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="fbdcb-175">Troubleshooting Visio Data Mining Diagrams &#40;SQL Server Data Mining Add-ins&#41;</span></span>](troubleshooting-visio-data-mining-diagrams-sql-server-data-mining-add-ins.md)  
  
  
