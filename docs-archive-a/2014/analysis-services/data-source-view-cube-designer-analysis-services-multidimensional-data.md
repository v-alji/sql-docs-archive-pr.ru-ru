---
title: Представление источника данных (вкладка «Структура куба», конструктор кубов) (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.cubebuilder.datasourcepane.f1
ms.assetid: 1e39c910-5c10-4624-be27-ca02a461b46b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8c949eaa17ec9d8bf585a5d595f31779382c41ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733306"
---
# <a name="data-source-view-cube-structure-tab-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="ae26d-102">Представление источника данных (вкладка «Структура куба» конструктора кубов) (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="ae26d-102">Data Source View (Cube Structure Tab, Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="ae26d-103">Панель **Представление источника данных** позволяет просматривать таблицы и столбцы из представления источников данных, связанного с данным кубом.</span><span class="sxs-lookup"><span data-stu-id="ae26d-103">Use the **Data Source View** pane to view tables and columns from the data source view associated with the selected cube.</span></span> <span data-ttu-id="ae26d-104">Эта панель позволяет создавать группы мер и меры путем перетаскивания столбцов из панели **Представление источника данных** в панель **Меры** .</span><span class="sxs-lookup"><span data-stu-id="ae26d-104">This pane is used to create measure groups and measures by dragging columns from the **Data Source View** pane to the **Measures** pane.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ae26d-105">Варианты</span><span class="sxs-lookup"><span data-stu-id="ae26d-105">Options</span></span>  
 <span data-ttu-id="ae26d-106">**Представление источника данных**</span><span class="sxs-lookup"><span data-stu-id="ae26d-106">**Data Source View**</span></span>  
 <span data-ttu-id="ae26d-107">Выводит представление источника данных, связанного с выбранным кубом.</span><span class="sxs-lookup"><span data-stu-id="ae26d-107">Displays the data source view associated with the selected cube.</span></span>  
  
 <span data-ttu-id="ae26d-108">**(Перенести точку обзора)**</span><span class="sxs-lookup"><span data-stu-id="ae26d-108">**(Move viewpoint)**</span></span>  
 <span data-ttu-id="ae26d-109">Щелкните нижний правый угол панели между полосами прокрутки, чтобы выбрать для просмотра область панели **Представление источника данных** .</span><span class="sxs-lookup"><span data-stu-id="ae26d-109">Click the lower right corner of the pane, between the scrollbars, to select an area of the **Data Source View** pane to view.</span></span>  
  
## <a name="diagram-context-menu"></a><span data-ttu-id="ae26d-110">Контекстное меню диаграммы</span><span class="sxs-lookup"><span data-stu-id="ae26d-110">Diagram Context Menu</span></span>  
 <span data-ttu-id="ae26d-111">Следующие пункты доступны в контекстном меню, которое появляется, если щелкнуть правой кнопкой фон диаграммы на панели **Представление источника данных** :</span><span class="sxs-lookup"><span data-stu-id="ae26d-111">The following options are available in the context menu displayed by right-clicking the diagram background of the **Data Source View** pane:</span></span>  
  
 <span data-ttu-id="ae26d-112">**Show Tables**</span><span class="sxs-lookup"><span data-stu-id="ae26d-112">**Show Tables**</span></span>  
 <span data-ttu-id="ae26d-113">Открывает диалоговое окно **Отображение таблицы**.</span><span class="sxs-lookup"><span data-stu-id="ae26d-113">Displays the **Show Table** dialog box.</span></span> <span data-ttu-id="ae26d-114">Дополнительные сведения о диалоговом окне **Отображение таблицы** см. в разделе [Диалоговое окно "Отображение таблицы" (службы Analysis Services — многомерные данные)](show-table-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="ae26d-114">For more information about the **Show Table** dialog box, see [Show Table Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](show-table-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="ae26d-115">**Показать все таблицы**</span><span class="sxs-lookup"><span data-stu-id="ae26d-115">**Show All Tables**</span></span>  
 <span data-ttu-id="ae26d-116">Выводит в данной панели все таблицы, включенные в это представление источника данных, связанное с выбранным кубом.</span><span class="sxs-lookup"><span data-stu-id="ae26d-116">Displays in the pane all tables included in the data source view associated with the cube.</span></span>  
  
 <span data-ttu-id="ae26d-117">**Показывать только используемые таблицы**</span><span class="sxs-lookup"><span data-stu-id="ae26d-117">**Show Only Used Tables**</span></span>  
 <span data-ttu-id="ae26d-118">Выводит в данной панели только таблицы, используемые кубом из связанного представления источников данных.</span><span class="sxs-lookup"><span data-stu-id="ae26d-118">Displays in the pane only those tables used by the cube from the associated data source view.</span></span>  
  
 <span data-ttu-id="ae26d-119">**Показывать понятные имена**</span><span class="sxs-lookup"><span data-stu-id="ae26d-119">**Show Friendly Names**</span></span>  
 <span data-ttu-id="ae26d-120">Устанавливает режим отображения понятных имен для объектов в данной панели.</span><span class="sxs-lookup"><span data-stu-id="ae26d-120">Selects to show friendly names for the objects in the pane.</span></span>  
  
 <span data-ttu-id="ae26d-121">**Выделить все**</span><span class="sxs-lookup"><span data-stu-id="ae26d-121">**Select All**</span></span>  
 <span data-ttu-id="ae26d-122">Выделяет все объекты на панели.</span><span class="sxs-lookup"><span data-stu-id="ae26d-122">Selects all of the objects in the pane.</span></span>  
  
 <span data-ttu-id="ae26d-123">**Найти таблицу**</span><span class="sxs-lookup"><span data-stu-id="ae26d-123">**Find Table**</span></span>  
 <span data-ttu-id="ae26d-124">Открывает диалоговое окно **Поиск таблицы**.</span><span class="sxs-lookup"><span data-stu-id="ae26d-124">Displays the **Find Table** dialog box.</span></span> <span data-ttu-id="ae26d-125">Дополнительные сведения о диалоговом окне **Поиск таблицы** см. в разделе [Диалоговое окно "Поиск таблицы" (службы Analysis Services — многомерные данные)](find-table-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="ae26d-125">For more information about the **Find Table** dialog box, see [Find Table Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](find-table-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="ae26d-126">**Упорядочить таблицы**</span><span class="sxs-lookup"><span data-stu-id="ae26d-126">**Arrange Tables**</span></span>  
 <span data-ttu-id="ae26d-127">Упорядочивает объекты на панели в соответствии с макетом, указанным в параметре **Переключиться на диагональный макет** или **Переключиться на прямоугольный макет**.</span><span class="sxs-lookup"><span data-stu-id="ae26d-127">Arranges the objects in the pane according to the layout specified by selecting either **Switch to Diagonal Layout** or **Switch to Rectangular Layout**.</span></span>  
  
 <span data-ttu-id="ae26d-128">**Переключиться на диагональный макет**</span><span class="sxs-lookup"><span data-stu-id="ae26d-128">**Switch to Diagonal Layout**</span></span>  
 <span data-ttu-id="ae26d-129">Выберите для упорядочивания объектов по диагональному шаблону.</span><span class="sxs-lookup"><span data-stu-id="ae26d-129">Select to arrange objects in a diagonal pattern.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ae26d-130">Данный параметр отображается, только если выбран режим **Переключиться на прямоугольный макет** .</span><span class="sxs-lookup"><span data-stu-id="ae26d-130">This option is displayed only if **Switch to Rectangular Layout** is selected.</span></span>  
  
 <span data-ttu-id="ae26d-131">**Переключиться на прямоугольный макет**</span><span class="sxs-lookup"><span data-stu-id="ae26d-131">**Switch to Rectangular Layout**</span></span>  
 <span data-ttu-id="ae26d-132">Выберите для упорядочивания объектов по прямоугольному шаблону.</span><span class="sxs-lookup"><span data-stu-id="ae26d-132">Select to arrange objects in a rectangular pattern.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ae26d-133">Данный параметр отображается, только если выбран режим **Переключиться на диагональный макет** .</span><span class="sxs-lookup"><span data-stu-id="ae26d-133">This option is displayed only if **Switch to Diagonal Layout** is selected.</span></span>  
  
 <span data-ttu-id="ae26d-134">**Изменить представление источника данных**</span><span class="sxs-lookup"><span data-stu-id="ae26d-134">**Edit Data Source View**</span></span>  
 <span data-ttu-id="ae26d-135">Выводит конструктор для представления источников данных, связанного с данным объектом.</span><span class="sxs-lookup"><span data-stu-id="ae26d-135">Displays Data Source View Designer for the data source view associated with the object.</span></span> <span data-ttu-id="ae26d-136">Дополнительные сведения о конструкторе представлений источников данных см. в разделе [Конструктор представлений источников данных (службы Analysis Services — многомерные данные)](data-source-view-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="ae26d-136">For more information about Data Source View Designer, see [Data Source View Designer &#40;Analysis Services - Multidimensional Data&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="ae26d-137">**Показать представление источника данных в**</span><span class="sxs-lookup"><span data-stu-id="ae26d-137">**Show Data Source View In**</span></span>  
 <span data-ttu-id="ae26d-138">Выберите один из следующих параметров, чтобы переключаться между режимами просмотра панели **Представление источника данных** :</span><span class="sxs-lookup"><span data-stu-id="ae26d-138">Select one of the following options to toggle between viewing the **Data Source View** pane in the following modes:</span></span>  
  
-   <span data-ttu-id="ae26d-139">Схема</span><span class="sxs-lookup"><span data-stu-id="ae26d-139">Diagram</span></span>  
  
     <span data-ttu-id="ae26d-140">Выводит диаграмму таблиц и столбцов, связанных с текущим кубом.</span><span class="sxs-lookup"><span data-stu-id="ae26d-140">Displays a diagram of the tables and columns associated with the current cube.</span></span>  
  
-   <span data-ttu-id="ae26d-141">Дерево</span><span class="sxs-lookup"><span data-stu-id="ae26d-141">Tree</span></span>  
  
     <span data-ttu-id="ae26d-142">Выводит представление дерева, которое содержит диаграмму таблиц и столбцов, связанных с текущим кубом.</span><span class="sxs-lookup"><span data-stu-id="ae26d-142">Displays a tree view containing the tables and columns associated with the current cube.</span></span>  
  
 <span data-ttu-id="ae26d-143">**Копировать диаграмму из**</span><span class="sxs-lookup"><span data-stu-id="ae26d-143">**Copy Diagram From**</span></span>  
 <span data-ttu-id="ae26d-144">Выберите одну из диаграмм, включенных в это представление данных, связанное с выбранным кубом, для отображения на панели **Представление источника данных** .</span><span class="sxs-lookup"><span data-stu-id="ae26d-144">Select one of the diagrams included in the data source view associated with the cube to display it in the **Data Source View** pane.</span></span>  
  
 <span data-ttu-id="ae26d-145">**Масштаб**</span><span class="sxs-lookup"><span data-stu-id="ae26d-145">**Zoom**</span></span>  
 <span data-ttu-id="ae26d-146">Выберите доступный вариант масштаба.</span><span class="sxs-lookup"><span data-stu-id="ae26d-146">Select an available zoom option.</span></span>  
  
 <span data-ttu-id="ae26d-147">**Свойства**</span><span class="sxs-lookup"><span data-stu-id="ae26d-147">**Properties**</span></span>  
 <span data-ttu-id="ae26d-148">Выводит окно **Свойства** в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] для представления источников данных, связанного с выбранным кубом.</span><span class="sxs-lookup"><span data-stu-id="ae26d-148">Displays the **Properties** window in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] for the data source view associated with the cube.</span></span>  
  
## <a name="table-context-menu"></a><span data-ttu-id="ae26d-149">Контекстное меню таблицы</span><span class="sxs-lookup"><span data-stu-id="ae26d-149">Table Context Menu</span></span>  
 <span data-ttu-id="ae26d-150">Следующие пункты доступны в контекстном меню, которое выводится, если щелкнуть правой кнопкой мыши имя таблицы или представление на панели **Представление источника данных** :</span><span class="sxs-lookup"><span data-stu-id="ae26d-150">The following options are available in the context menu displayed by right-clicking the name of a table or view in the **Data Source View** pane:</span></span>  
  
 <span data-ttu-id="ae26d-151">**Показывать связанные таблицы**</span><span class="sxs-lookup"><span data-stu-id="ae26d-151">**Show Related Tables**</span></span>  
 <span data-ttu-id="ae26d-152">Отображает на панели таблицы, связанные с таблицей, выбранной в представлении источника данных.</span><span class="sxs-lookup"><span data-stu-id="ae26d-152">Displays in the pane the tables related to the selected table in the data source view.</span></span>  
  
 <span data-ttu-id="ae26d-153">**Скрыть таблицу**</span><span class="sxs-lookup"><span data-stu-id="ae26d-153">**Hide Table**</span></span>  
 <span data-ttu-id="ae26d-154">Удаляет таблицу с панели.</span><span class="sxs-lookup"><span data-stu-id="ae26d-154">Removes the table from the pane.</span></span>  
  
 <span data-ttu-id="ae26d-155">**Просмотр данных**</span><span class="sxs-lookup"><span data-stu-id="ae26d-155">**Explore Data**</span></span>  
 <span data-ttu-id="ae26d-156">Открывает для выбранной таблицы диалоговое окно **Просмотр данных** .</span><span class="sxs-lookup"><span data-stu-id="ae26d-156">Display the **Explore Data** dialog box for the selected table.</span></span>  
  
 <span data-ttu-id="ae26d-157">**Изменить представление источника данных**</span><span class="sxs-lookup"><span data-stu-id="ae26d-157">**Edit Data Source View**</span></span>  
 <span data-ttu-id="ae26d-158">Отображает конструктор представлений источников данных для представления источников данных, содержащего выбранную таблицу.</span><span class="sxs-lookup"><span data-stu-id="ae26d-158">Displays Data Source View Designer for the data source view that contains the selected table.</span></span> <span data-ttu-id="ae26d-159">Дополнительные сведения о конструкторе представлений источников данных см. в разделе [Конструктор представлений источников данных (службы Analysis Services — многомерные данные)](data-source-view-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="ae26d-159">For more information about Data Source View Designer, see [Data Source View Designer &#40;Analysis Services - Multidimensional Data&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="ae26d-160">**Создать группу мер из таблицы**</span><span class="sxs-lookup"><span data-stu-id="ae26d-160">**New Measure Group from Table**</span></span>  
 <span data-ttu-id="ae26d-161">Определяет новую группу мер на панели **Меры** на основании выбранной таблицы.</span><span class="sxs-lookup"><span data-stu-id="ae26d-161">Defines a new measure group in the **Measures** pane based on the selected table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ae26d-162">Этот параметр доступен, только если на данную таблицу нет ссылок в группе мер на панели **Меры** .</span><span class="sxs-lookup"><span data-stu-id="ae26d-162">This option is enabled only if the table is not yet referenced by a measure group in the **Measures** pane.</span></span>  
  
 <span data-ttu-id="ae26d-163">**Свойства**</span><span class="sxs-lookup"><span data-stu-id="ae26d-163">**Properties**</span></span>  
 <span data-ttu-id="ae26d-164">Отображает окно **Свойства** в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] для выбранной таблицы.</span><span class="sxs-lookup"><span data-stu-id="ae26d-164">Displays the **Properties** window in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] for the selected table.</span></span>  
  
## <a name="column-context-menu"></a><span data-ttu-id="ae26d-165">Контекстное меню столбца</span><span class="sxs-lookup"><span data-stu-id="ae26d-165">Column Context Menu</span></span>  
 <span data-ttu-id="ae26d-166">Следующие пункты доступны в контекстном меню, которое выводится, если щелкнуть правой кнопкой мыши имя столбца таблицы или представление на панели **Представление источника данных** :</span><span class="sxs-lookup"><span data-stu-id="ae26d-166">The following options are available in the context menu displayed by right-clicking the name of a column in a table or view in the **Data Source View** pane:</span></span>  
  
 <span data-ttu-id="ae26d-167">**Создать меру из столбца**</span><span class="sxs-lookup"><span data-stu-id="ae26d-167">**New Measure from Column**</span></span>  
 <span data-ttu-id="ae26d-168">Определяет новую меру на панели **Меры** на основании выбранного столбца.</span><span class="sxs-lookup"><span data-stu-id="ae26d-168">Defines a new measure in the **Measures** pane based on the selected column.</span></span>  
  
 <span data-ttu-id="ae26d-169">**Просмотр данных**</span><span class="sxs-lookup"><span data-stu-id="ae26d-169">**Explore Data**</span></span>  
 <span data-ttu-id="ae26d-170">Открывает диалоговое окно **Просмотр данных** для таблицы, которая содержит выбранный столбец.</span><span class="sxs-lookup"><span data-stu-id="ae26d-170">Display the **Explore Data** dialog box for the table that contains the selected column.</span></span>  
  
 <span data-ttu-id="ae26d-171">**Изменить представление источника данных**</span><span class="sxs-lookup"><span data-stu-id="ae26d-171">**Edit Data Source View**</span></span>  
 <span data-ttu-id="ae26d-172">Отображает конструктор представлений источников данных для представления источников данных, содержащего данный столбец.</span><span class="sxs-lookup"><span data-stu-id="ae26d-172">Displays Data Source View Designer for the data source view that contains the selected column.</span></span> <span data-ttu-id="ae26d-173">Дополнительные сведения о конструкторе представлений источников данных см. в разделе [Конструктор представлений источников данных (службы Analysis Services — многомерные данные)](data-source-view-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="ae26d-173">For more information about Data Source View Designer, see [Data Source View Designer &#40;Analysis Services - Multidimensional Data&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="ae26d-174">**Свойства**</span><span class="sxs-lookup"><span data-stu-id="ae26d-174">**Properties**</span></span>  
 <span data-ttu-id="ae26d-175">Отображает окно **Свойства** в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] для выбранного столбца.</span><span class="sxs-lookup"><span data-stu-id="ae26d-175">Displays the **Properties** window in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] for the selected column.</span></span>  
  
## <a name="relationship-context-menu"></a><span data-ttu-id="ae26d-176">Контекстное меню связей</span><span class="sxs-lookup"><span data-stu-id="ae26d-176">Relationship Context Menu</span></span>  
 <span data-ttu-id="ae26d-177">Следующие пункты доступны в контекстном меню, которое выводится, если щелкнуть правой кнопкой мыши связь на панели **Представление источника данных** :</span><span class="sxs-lookup"><span data-stu-id="ae26d-177">The following options are available in the context menu displayed by right-clicking a relationship in the **Data Source View** pane:</span></span>  
  
 <span data-ttu-id="ae26d-178">**Изменить представление источника данных**</span><span class="sxs-lookup"><span data-stu-id="ae26d-178">**Edit Data Source View**</span></span>  
 <span data-ttu-id="ae26d-179">Выводит конструктор представления источников данных, содержащий выбранную связь.</span><span class="sxs-lookup"><span data-stu-id="ae26d-179">Displays Data Source View Designer for the data source view that contains the selected relationship.</span></span> <span data-ttu-id="ae26d-180">Дополнительные сведения о конструкторе представлений источников данных см. в разделе [Конструктор представлений источников данных (службы Analysis Services — многомерные данные)](data-source-view-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="ae26d-180">For more information about Data Source View Designer, see [Data Source View Designer &#40;Analysis Services - Multidimensional Data&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="ae26d-181">**Свойства**</span><span class="sxs-lookup"><span data-stu-id="ae26d-181">**Properties**</span></span>  
 <span data-ttu-id="ae26d-182">Отображает окно **Свойства** в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] для выбранной связи.</span><span class="sxs-lookup"><span data-stu-id="ae26d-182">Displays the **Properties** window in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] for the selected relationship.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae26d-183">См. также:</span><span class="sxs-lookup"><span data-stu-id="ae26d-183">See Also</span></span>  
 <span data-ttu-id="ae26d-184">[Панель инструментов &#40;вкладка «Структура куба», конструктор кубов&#41; &#40;Analysis Services многомерных данных&#41;](toolbar-cube-structure-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="ae26d-184">[Toolbar &#40;Cube Structure Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-cube-structure-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="ae26d-185">[Меры &#40;вкладка «Структура куба», конструктор кубов&#41; &#40;Analysis Services многомерных данных&#41;](measures-cube-structure-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="ae26d-185">[Measures &#40;Cube Structure Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](measures-cube-structure-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="ae26d-186">[Измерения &#40;вкладка «Структура куба», конструктор кубов&#41; &#40;Analysis Services многомерных данных&#41;](dimensions-cube-structure-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="ae26d-186">[Dimensions &#40;Cube Structure Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](dimensions-cube-structure-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="ae26d-187">Структура куба &#40;конструктор кубов&#41; &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="ae26d-187">Cube Structure &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](cube-structure-cube-designer-analysis-services-multidimensional-data.md)  
  
  
