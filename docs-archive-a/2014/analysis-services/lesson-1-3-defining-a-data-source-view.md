---
title: Определение представления источника данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: af00938a-5a06-4fae-b2fc-f3fb0ca3cea5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7d59c5fbe5fd4a07596745447567a72499ddabd4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654565"
---
# <a name="defining-a-data-source-view"></a><span data-ttu-id="2e1cc-102">Определение представления источников данных</span><span class="sxs-lookup"><span data-stu-id="2e1cc-102">Defining a Data Source View</span></span>
  <span data-ttu-id="2e1cc-103">После определения источников данных, используемых в проекте служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , на следующем этапе, как правило, определяется представление источника данных для этого проекта.</span><span class="sxs-lookup"><span data-stu-id="2e1cc-103">After you define the data sources that you will use in an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, the next step is generally to define a data source view for the project.</span></span> <span data-ttu-id="2e1cc-104">Представление источника данных является отдельным единым представлением метаданных из указанных таблиц и представлений, определяемых источником данных для проекта.</span><span class="sxs-lookup"><span data-stu-id="2e1cc-104">A data source view is a single, unified view of the metadata from the specified tables and views that the data source defines in the project.</span></span> <span data-ttu-id="2e1cc-105">Хранение метаданных в представлении источника данных позволяет работать с метаданными в процессе разработки, не устанавливая соединений с базовыми источниками данных.</span><span class="sxs-lookup"><span data-stu-id="2e1cc-105">Storing the metadata in the data source view enables you to work with the metadata during development without an open connection to any underlying data source.</span></span> <span data-ttu-id="2e1cc-106">Дополнительные сведения см. в разделе [Представления источников данных в многомерных моделях](multidimensional-models/data-source-views-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="2e1cc-106">For more information, see [Data Source Views in Multidimensional Models](multidimensional-models/data-source-views-in-multidimensional-models.md).</span></span>  
  
 <span data-ttu-id="2e1cc-107">В следующей задаче будет определено представление источника данных, которое содержит пять таблиц из источника данных **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="2e1cc-107">In the following task, you define a data source view that includes five tables from the **AdventureWorksDW2012** data source.</span></span>  
  
### <a name="to-define-a-new-data-source-view"></a><span data-ttu-id="2e1cc-108">Определение нового представления источников данных</span><span class="sxs-lookup"><span data-stu-id="2e1cc-108">To define a new data source view</span></span>  
  
1.  <span data-ttu-id="2e1cc-109">В обозревателе решений (в правой части окна Microsoft Visual Studio) щелкните правой кнопкой мыши папку **Представления источников данных**и выберите пункт **Создать представление источника данных**.</span><span class="sxs-lookup"><span data-stu-id="2e1cc-109">In Solution Explorer (on the right of the Microsoft Visual Studio window), right-click **Data Source Views**, and then click **New Data Source View**.</span></span>  
  
2.  <span data-ttu-id="2e1cc-110">На странице **Мастер представления источника данных** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2e1cc-110">On the **Welcome to the Data Source View Wizard** page, click **Next**.</span></span> <span data-ttu-id="2e1cc-111">Откроется страница **Выбор источника данных** .</span><span class="sxs-lookup"><span data-stu-id="2e1cc-111">The **Select a Data Source** page appears.</span></span>  
  
3.  <span data-ttu-id="2e1cc-112">В группе **Реляционные источники данных**выбран источник данных **Adventure Works DW 2012** .</span><span class="sxs-lookup"><span data-stu-id="2e1cc-112">Under **Relational data sources**, the **Adventure Works DW 2012** data source is selected.</span></span> <span data-ttu-id="2e1cc-113">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2e1cc-113">Click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2e1cc-114">Чтобы создать представление источника данных, в основе которого лежат несколько источников данных, необходимо предварительно определить представление источника данных, основанное на одном источнике данных.</span><span class="sxs-lookup"><span data-stu-id="2e1cc-114">To create a data source view that is based on multiple data sources, first define a data source view that is based on a single data source.</span></span> <span data-ttu-id="2e1cc-115">Этот источник данных впоследствии считается первичным источником данных.</span><span class="sxs-lookup"><span data-stu-id="2e1cc-115">This data source is then called the primary data source.</span></span> <span data-ttu-id="2e1cc-116">Затем можно добавить таблицы и представления из вторичного источника данных.</span><span class="sxs-lookup"><span data-stu-id="2e1cc-116">You can then add tables and views from a secondary data source.</span></span> <span data-ttu-id="2e1cc-117">При проектировании измерений с атрибутами, основанными на связанных таблицах нескольких источников данных, может потребоваться определить источник данных [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] как основной источник данных, чтобы использовать его возможности обработки распределенных запросов.</span><span class="sxs-lookup"><span data-stu-id="2e1cc-117">When designing dimensions that contain attributes based on related tables in multiple data sources, you might need to define a [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] data source as the primary data source to use its distributed query engine capabilities.</span></span>  
  
4.  <span data-ttu-id="2e1cc-118">На странице **Выбор таблиц и представлений** выберите таблицы и представления из списка объектов, доступных в выбранном источнике данных.</span><span class="sxs-lookup"><span data-stu-id="2e1cc-118">On the **Select Tables and Views** page, select tables and views from the list of objects that are available from the selected data source.</span></span> <span data-ttu-id="2e1cc-119">Можно установить для этого списка фильтр, который поможет отобрать нужные таблицы и представления.</span><span class="sxs-lookup"><span data-stu-id="2e1cc-119">You can filter this list to help you select tables and views.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2e1cc-120">Нажмите кнопку разворачивания в верхнем правом углу, чтобы окно заняло весь экран.</span><span class="sxs-lookup"><span data-stu-id="2e1cc-120">Click the maximize button in the upper-right corner so that the window covers the full screen.</span></span> <span data-ttu-id="2e1cc-121">Это облегчит просмотр полного списка доступных объектов.</span><span class="sxs-lookup"><span data-stu-id="2e1cc-121">This makes it easier to see the complete list of available objects.</span></span>  
  
     <span data-ttu-id="2e1cc-122">В списке **Доступные объекты** выберите перечисленные ниже объекты.</span><span class="sxs-lookup"><span data-stu-id="2e1cc-122">In the **Available objects** list, select the following objects.</span></span> <span data-ttu-id="2e1cc-123">Несколько таблиц можно выбрать, удерживая клавишу CTRL при выборе.</span><span class="sxs-lookup"><span data-stu-id="2e1cc-123">You can select multiple tables by clicking each while holding down the CTRL key:</span></span>  
  
    -   <span data-ttu-id="2e1cc-124">**DimCustomer (dbo)**</span><span class="sxs-lookup"><span data-stu-id="2e1cc-124">**DimCustomer (dbo)**</span></span>  
  
    -   <span data-ttu-id="2e1cc-125">**DimDate (dbo)**</span><span class="sxs-lookup"><span data-stu-id="2e1cc-125">**DimDate (dbo)**</span></span>  
  
    -   <span data-ttu-id="2e1cc-126">**DimGeography (dbo)**</span><span class="sxs-lookup"><span data-stu-id="2e1cc-126">**DimGeography (dbo)**</span></span>  
  
    -   <span data-ttu-id="2e1cc-127">**DimProduct (dbo)**</span><span class="sxs-lookup"><span data-stu-id="2e1cc-127">**DimProduct (dbo)**</span></span>  
  
    -   <span data-ttu-id="2e1cc-128">**FactInternetSales (dbo)**</span><span class="sxs-lookup"><span data-stu-id="2e1cc-128">**FactInternetSales (dbo)**</span></span>  
  
5.  <span data-ttu-id="2e1cc-129">Нажмите **>** , чтобы добавить выбранные таблицы в список **Включенные объекты** .</span><span class="sxs-lookup"><span data-stu-id="2e1cc-129">Click **>** to add the selected tables to the **Included objects** list.</span></span>  
  
6.  <span data-ttu-id="2e1cc-130">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2e1cc-130">Click **Next.**</span></span>  
  
7.  <span data-ttu-id="2e1cc-131">Убедитесь в том, что в поле "Имя" введено **Adventure Works DW 2012** , а затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="2e1cc-131">In the Name field, make sure **Adventure Works DW 2012** displays, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="2e1cc-132">Представление источника данных **Adventure Works DW 2012** будет выведено в папке **Представления источников данных** обозревателя решений.</span><span class="sxs-lookup"><span data-stu-id="2e1cc-132">The **Adventure Works DW 2012** data source view appears in the **Data Source Views** folder in Solution Explorer.</span></span> <span data-ttu-id="2e1cc-133">Содержимое представления источников данных также отображается в конструкторе представлений источников данных в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e1cc-133">The content of the data source view is also displayed in Data Source View Designer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="2e1cc-134">В этом конструкторе содержатся следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="2e1cc-134">This designer contains the following elements:</span></span>  
  
    -   <span data-ttu-id="2e1cc-135">Панель **Диаграмма** , на которой представлены в графическом виде таблицы и их связи.</span><span class="sxs-lookup"><span data-stu-id="2e1cc-135">A **Diagram** pane in which the tables and their relationships are represented graphically.</span></span>  
  
    -   <span data-ttu-id="2e1cc-136">Панель **Таблицы** , на которой представлены в виде дерева таблицы и их элементы схем.</span><span class="sxs-lookup"><span data-stu-id="2e1cc-136">A **Tables** pane in which the tables and their schema elements are displayed in a tree view.</span></span>  
  
    -   <span data-ttu-id="2e1cc-137">Панель **Организатор схем** , на которой можно создавать вложенные диаграммы, позволяющие просматривать поднаборы этого представления источников данных.</span><span class="sxs-lookup"><span data-stu-id="2e1cc-137">A **Diagram Organizer** pane in which you can create subdiagrams so that you can view subsets of the data source view.</span></span>  
  
    -   <span data-ttu-id="2e1cc-138">Панель инструментов конструктора представлений источников данных.</span><span class="sxs-lookup"><span data-stu-id="2e1cc-138">A toolbar that is specific to Data Source View Designer.</span></span>  
  
8.  <span data-ttu-id="2e1cc-139">Нажмите кнопку [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] development environment, click the **Maximize** button.</span><span class="sxs-lookup"><span data-stu-id="2e1cc-139">To maximize the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] development environment, click the **Maximize** button.</span></span>  
  
9. <span data-ttu-id="2e1cc-140">На панели инструментов в верхней части конструктора представлений источников данных щелкните значок **Масштаб** , чтобы просмотреть таблицы на панели **Диаграмма** в масштабе 50 %.</span><span class="sxs-lookup"><span data-stu-id="2e1cc-140">To view the tables in the **Diagram** pane at 50 percent, click the **Zoom** icon on the Data Source View Designer toolbar.</span></span> <span data-ttu-id="2e1cc-141">При этом будут скрыты подробные сведения в столбцах таблиц.</span><span class="sxs-lookup"><span data-stu-id="2e1cc-141">This will hide the column details of each table.</span></span>  
  
10. <span data-ttu-id="2e1cc-142">Чтобы скрыть обозреватель решений, нажмите кнопку **Автоматически скрывать** , на которой изображен значок кнопки, в заголовке обозревателя решений.</span><span class="sxs-lookup"><span data-stu-id="2e1cc-142">To hide Solution Explorer, click the **Auto Hide** button, which is the pushpin icon on the title bar.</span></span> <span data-ttu-id="2e1cc-143">Чтобы вернуться в обозреватель решений, установите указатель над вкладкой «Обозреватель решений» в правой части среды разработки.</span><span class="sxs-lookup"><span data-stu-id="2e1cc-143">To view Solution Explorer again, position your pointer over the Solution Explorer tab along the right side of the development environment.</span></span> <span data-ttu-id="2e1cc-144">Чтобы отобразить обозреватель решений, вновь нажмите кнопку **Автоматически скрывать** .</span><span class="sxs-lookup"><span data-stu-id="2e1cc-144">To unhide Solution Explorer, click the **Auto Hide** button again.</span></span>  
  
11. <span data-ttu-id="2e1cc-145">Если окна не скрыты по умолчанию, нажмите кнопку **Автоматически скрывать** в заголовке окна свойств или обозревателя решений.</span><span class="sxs-lookup"><span data-stu-id="2e1cc-145">If the windows are not hidden by default, click **Auto Hide** on the title bar of the Properties and Solution Explorer windows.</span></span>  
  
     <span data-ttu-id="2e1cc-146">Теперь все таблицы и связи между ними можно легко просматривать на панели **Диаграмма** .</span><span class="sxs-lookup"><span data-stu-id="2e1cc-146">You can now view all the tables and their relationships in the **Diagram** pane.</span></span> <span data-ttu-id="2e1cc-147">Обратите внимание, что между таблицами FactInternetSales и DimDate имеются три связи.</span><span class="sxs-lookup"><span data-stu-id="2e1cc-147">Notice that there are three relationships between the FactInternetSales table and the DimDate table.</span></span> <span data-ttu-id="2e1cc-148">С каждой продажей связано три даты: дата заказа, дата оплаты и дата отгрузки.</span><span class="sxs-lookup"><span data-stu-id="2e1cc-148">Each sale has three dates associated with the sale: an order date, a due date, and a ship date.</span></span> <span data-ttu-id="2e1cc-149">Чтобы просмотреть подробные сведения по связи, дважды щелкните стрелку этой связи на панели **Диаграмма** .</span><span class="sxs-lookup"><span data-stu-id="2e1cc-149">To view the details of any relationship, double-click the relationship arrow in the **Diagram** pane.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="2e1cc-150">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="2e1cc-150">Next Task in Lesson</span></span>  
 [<span data-ttu-id="2e1cc-151">Изменение имен таблиц по умолчанию</span><span class="sxs-lookup"><span data-stu-id="2e1cc-151">Modifying Default Table Names</span></span>](lesson-1-4-modifying-default-table-names.md)  
  
## <a name="see-also"></a><span data-ttu-id="2e1cc-152">См. также:</span><span class="sxs-lookup"><span data-stu-id="2e1cc-152">See Also</span></span>  
 [<span data-ttu-id="2e1cc-153">Представления источников данных в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="2e1cc-153">Data Source Views in Multidimensional Models</span></span>](multidimensional-models/data-source-views-in-multidimensional-models.md)  
  
  
