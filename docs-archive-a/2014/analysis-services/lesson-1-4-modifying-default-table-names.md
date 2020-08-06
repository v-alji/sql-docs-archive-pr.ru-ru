---
title: Изменение имен таблиц по умолчанию | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: ddd97483-a76d-43c1-8b40-fc7cc57fb0c2
author: minewiskan
ms.author: owend
ms.openlocfilehash: 254f797be95f60211983400b019415431d4cf39c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654564"
---
# <a name="modifying-default-table-names"></a><span data-ttu-id="fde28-102">Изменение имен таблиц по умолчанию</span><span class="sxs-lookup"><span data-stu-id="fde28-102">Modifying Default Table Names</span></span>
  <span data-ttu-id="fde28-103">Значение свойства **FriendlyName** для объектов в представлении источника данных можно изменить, сделав его имя более понятным и простым в использовании.</span><span class="sxs-lookup"><span data-stu-id="fde28-103">You can change the value of the **FriendlyName** property for objects in the data source view to make them easier to notice and use.</span></span>  
  
 <span data-ttu-id="fde28-104">В следующей задаче будет изменено понятное имя каждой из таблиц в представлении источника данных посредством удаления из их имен префиксов**Dim**и**Fact**.</span><span class="sxs-lookup"><span data-stu-id="fde28-104">In the following task, you will change the friendly name of each table in the data source view by removing the "**Dim**" and "**Fact**" prefixes from these tables.</span></span> <span data-ttu-id="fde28-105">Это сделает более понятными имена объектов куба и измерений, которые будут определены на следующем занятии.</span><span class="sxs-lookup"><span data-stu-id="fde28-105">This will make the cube and dimension objects (that you will define in the next lesson) easier to notice and use.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fde28-106">Также в представлении источника данных можно присваивать понятные имена столбцам, определять вычисляемые столбцы, а также соединять таблицы и представления, чтобы сделать их более удобными в работе.</span><span class="sxs-lookup"><span data-stu-id="fde28-106">You can also change the friendly names of columns, define calculated columns, and join tables or views in the data source view to make them easier to use.</span></span>  
  
### <a name="to-modify-the-default-name-of-a-table"></a><span data-ttu-id="fde28-107">Изменение имени таблицы по умолчанию</span><span class="sxs-lookup"><span data-stu-id="fde28-107">To modify the default name of a table</span></span>  
  
1.  <span data-ttu-id="fde28-108">На панели **Таблицы\*\*\*\*конструктора представлений источников данных**щелкните правой кнопкой мыши таблицу **FactInternetSales** и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="fde28-108">In the **Tables** pane of **Data Source View Designer**, right-click the **FactInternetSales** table, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="fde28-109">Если окно свойств не отображается в правой части окна Microsoft Visual Studio, нажмите кнопку **Автоматически скрывать** в строке заголовка окна свойств, чтобы окно оставалось видимым.</span><span class="sxs-lookup"><span data-stu-id="fde28-109">If the Properties window on the right side of the Microsoft Visual Studio window is not displayed, click the **Auto Hide** button on the title bar of the Properties window so that this window remains visible.</span></span>  
  
     <span data-ttu-id="fde28-110">Когда окно свойств открыто, проще изменять свойства каждой таблицы в представлении источника данных.</span><span class="sxs-lookup"><span data-stu-id="fde28-110">It is easier to change the properties for each table in the data source view when the Properties window remains open.</span></span> <span data-ttu-id="fde28-111">Если окно не закреплено в открытом состоянии с помощью кнопки **Автоматически скрывать** , оно будет закрыто, как только будет выбран другой объект на панели **Диаграмма** .</span><span class="sxs-lookup"><span data-stu-id="fde28-111">If you do not pin the window open by using the **Auto Hide** button, the window will close when you click a different object in the **Diagram** pane.</span></span>  
  
3.  <span data-ttu-id="fde28-112">Измените свойство **FriendlyName** для объекта **FactInternetSales** на *`InternetSales`* .</span><span class="sxs-lookup"><span data-stu-id="fde28-112">Change the **FriendlyName** property for the **FactInternetSales** object to *`InternetSales`*.</span></span>  
  
     <span data-ttu-id="fde28-113">Изменение будет применено, если щелкнуть вне ячейки свойства **FriendlyName** .</span><span class="sxs-lookup"><span data-stu-id="fde28-113">When you click away from the cell for the **FriendlyName** property, the change is applied.</span></span> <span data-ttu-id="fde28-114">На следующем занятии будет рассмотрено определение группы мер на основе этой таблицы фактов.</span><span class="sxs-lookup"><span data-stu-id="fde28-114">In the next lesson, you will define a measure group that is based on this fact table.</span></span> <span data-ttu-id="fde28-115">Из-за сделанных на этом занятии изменений она будет называться не FactInternetSales, а InternetSales.</span><span class="sxs-lookup"><span data-stu-id="fde28-115">The name of the fact table will be InternetSales instead of FactInternetSales because of the change you made in this lesson.</span></span>  
  
4.  <span data-ttu-id="fde28-116">На панели **Таблицы** выберите таблицу **DimProduct** .</span><span class="sxs-lookup"><span data-stu-id="fde28-116">Click **DimProduct** in the **Tables** pane.</span></span> <span data-ttu-id="fde28-117">В окно свойств измените свойство **FriendlyName** на *`Product`* .</span><span class="sxs-lookup"><span data-stu-id="fde28-117">In the Properties window, change the **FriendlyName** property to *`Product`*.</span></span>  
  
5.  <span data-ttu-id="fde28-118">Точно таким же образом измените значения свойства **FriendlyName** для всех оставшихся таблиц в представлении источника данных, удалив префикс**Dim**.</span><span class="sxs-lookup"><span data-stu-id="fde28-118">Change the **FriendlyName** property of each remaining table in the data source view in the same way, to remove the "**Dim**" prefix.</span></span>  
  
6.  <span data-ttu-id="fde28-119">Затем нажмите кнопку **Автоматически скрывать** , чтобы снова скрыть окно свойств.</span><span class="sxs-lookup"><span data-stu-id="fde28-119">When you have finished, click the **Auto Hide** button to hide the Properties window again.</span></span>  
  
7.  <span data-ttu-id="fde28-120">В меню **Файл** выберите пункт [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]Сохранить все **(или нажмите соответствующую кнопку на панели инструментов среды** ), чтобы сохранить изменения, внесенные в проект учебника по службам [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fde28-120">On the **File** menu, or on the toolbar of [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click **Save All** to save the changes you have made to this point in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project.</span></span> <span data-ttu-id="fde28-121">Если необходимо, здесь можно прервать работу с учебником, чтобы продолжить ее позже.</span><span class="sxs-lookup"><span data-stu-id="fde28-121">You can stop the tutorial here if you want and resume it later.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="fde28-122">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="fde28-122">Next Lesson</span></span>  
 [<span data-ttu-id="fde28-123">Урок 2. Определение и развертывание куба</span><span class="sxs-lookup"><span data-stu-id="fde28-123">Lesson 2: Defining and Deploying a Cube</span></span>](lesson-2-defining-and-deploying-a-cube.md)  
  
## <a name="see-also"></a><span data-ttu-id="fde28-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="fde28-124">See Also</span></span>  
 <span data-ttu-id="fde28-125">[Представления источников данных в многомерных моделях](multidimensional-models/data-source-views-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="fde28-125">[Data Source Views in Multidimensional Models](multidimensional-models/data-source-views-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="fde28-126">Изменение свойств в представлении источника данных (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="fde28-126">Change Properties in a Data Source View &#40;Analysis Services&#41;</span></span>](multidimensional-models/change-properties-in-a-data-source-view-analysis-services.md)  
  
  
