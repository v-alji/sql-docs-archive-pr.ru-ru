---
title: Представление источника данных (вкладка «Структура измерения», конструктор измерений) (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql.asvs.dimensiondesigner.dbv.datasourcepane.f1
ms.assetid: c4bd3c5e-8986-448f-b9db-3551f50f0696
author: minewiskan
ms.author: owend
ms.openlocfilehash: fb2529e1835829bc84eec77c18b7ec05da5c4220
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668504"
---
# <a name="data-source-view-dimension-structure-tab-dimension-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="fef3f-102">Представление источника данных (вкладка «Структура измерения» конструктора измерений) (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="fef3f-102">Data Source View (Dimension Structure Tab, Dimension Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="fef3f-103">Панель **Представление источника данных** используется для просмотра таблиц и столбцов в представлении источника данных, связанном с выбранным измерением.</span><span class="sxs-lookup"><span data-stu-id="fef3f-103">Use the **Data Source View** pane to view tables and columns from the data source view associated with the selected dimension.</span></span> <span data-ttu-id="fef3f-104">На панели можно создавать атрибуты, свойства элементов, иерархии и уровни, перетаскивая столбцы из панели **Представление источника данных** на панель **Атрибуты** или **Иерархии и уровни** .</span><span class="sxs-lookup"><span data-stu-id="fef3f-104">This pane is used to create attributes, member properties, hierarchies, and levels, by dragging columns from the **Data Source View** pane to the **Attributes** or **Hierarchies and Levels** pane.</span></span>  
  
## <a name="options"></a><span data-ttu-id="fef3f-105">Варианты</span><span class="sxs-lookup"><span data-stu-id="fef3f-105">Options</span></span>  
 <span data-ttu-id="fef3f-106">**Представление источника данных**</span><span class="sxs-lookup"><span data-stu-id="fef3f-106">**Data Source View**</span></span>  
 <span data-ttu-id="fef3f-107">Выводит представление источника данных, связанного с выбранным измерением.</span><span class="sxs-lookup"><span data-stu-id="fef3f-107">Displays the data source view associated with the selected dimension.</span></span>  
  
 <span data-ttu-id="fef3f-108">**(Перенести точку обзора)**</span><span class="sxs-lookup"><span data-stu-id="fef3f-108">**(Move viewpoint)**</span></span>  
 <span data-ttu-id="fef3f-109">Щелкните нижний правый угол панели между полосами прокрутки, чтобы выбрать для просмотра область панели **Представление источника данных** .</span><span class="sxs-lookup"><span data-stu-id="fef3f-109">Click the lower right corner of the pane, between the scrollbars, to select an area of the **Data Source View** pane to view.</span></span>  
  
## <a name="diagram-context-menu"></a><span data-ttu-id="fef3f-110">Контекстное меню диаграммы</span><span class="sxs-lookup"><span data-stu-id="fef3f-110">Diagram Context Menu</span></span>  
 <span data-ttu-id="fef3f-111">Команды, перечисленные в следующей таблице, находятся в контекстном меню, которое открывается, если щелкнуть правой кнопкой мыши фон диаграммы на панели **Представление источника данных** .</span><span class="sxs-lookup"><span data-stu-id="fef3f-111">The options listed in the following table are available in the context menu displayed by right-clicking the diagram background of the **Data Source View** pane.</span></span>  
  
 <span data-ttu-id="fef3f-112">**Show Tables**</span><span class="sxs-lookup"><span data-stu-id="fef3f-112">**Show Tables**</span></span>  
 <span data-ttu-id="fef3f-113">Открывает диалоговое окно **Отображение таблицы**.</span><span class="sxs-lookup"><span data-stu-id="fef3f-113">Displays the **Show Table** dialog box.</span></span> <span data-ttu-id="fef3f-114">Дополнительные сведения о диалоговом окне **Отображение таблицы** см. в разделе [Диалоговое окно "Отображение таблицы" (службы Analysis Services — многомерные данные)](show-table-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="fef3f-114">For more information about the **Show Table** dialog box, see [Show Table Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](show-table-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="fef3f-115">**Показать все таблицы**</span><span class="sxs-lookup"><span data-stu-id="fef3f-115">**Show All Tables**</span></span>  
 <span data-ttu-id="fef3f-116">Выводит в данной панели все таблицы, включенные в это представление источника данных, связанное с выбранным измерением.</span><span class="sxs-lookup"><span data-stu-id="fef3f-116">Displays in the pane all tables included in the data source view associated with the dimension.</span></span>  
  
 <span data-ttu-id="fef3f-117">**Показывать только используемые таблицы**</span><span class="sxs-lookup"><span data-stu-id="fef3f-117">**Show Only Used Tables**</span></span>  
 <span data-ttu-id="fef3f-118">Выводит в данной панели только таблицы, используемые измерением из связанного представления источников данных.</span><span class="sxs-lookup"><span data-stu-id="fef3f-118">Displays in the pane only those tables used by the dimension from the associated data source view.</span></span>  
  
 <span data-ttu-id="fef3f-119">**Показывать понятные имена**</span><span class="sxs-lookup"><span data-stu-id="fef3f-119">**Show Friendly Names**</span></span>  
 <span data-ttu-id="fef3f-120">Устанавливает режим отображения понятных имен для объектов в данной панели.</span><span class="sxs-lookup"><span data-stu-id="fef3f-120">Select to show friendly names for the objects in the pane.</span></span>  
  
 <span data-ttu-id="fef3f-121">**Выделить все**</span><span class="sxs-lookup"><span data-stu-id="fef3f-121">**Select All**</span></span>  
 <span data-ttu-id="fef3f-122">Выделяет все объекты на панели.</span><span class="sxs-lookup"><span data-stu-id="fef3f-122">Selects all of the objects in the pane.</span></span>  
  
 <span data-ttu-id="fef3f-123">**Найти таблицу**</span><span class="sxs-lookup"><span data-stu-id="fef3f-123">**Find Table**</span></span>  
 <span data-ttu-id="fef3f-124">Открывает диалоговое окно **Поиск таблицы**.</span><span class="sxs-lookup"><span data-stu-id="fef3f-124">Displays the **Find Table** dialog box.</span></span> <span data-ttu-id="fef3f-125">Дополнительные сведения о диалоговом окне **Поиск таблицы** см. в разделе [Диалоговое окно "Поиск таблицы" (службы Analysis Services — многомерные данные)](find-table-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="fef3f-125">For more information about the **Find Table** dialog box, see [Find Table Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](find-table-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="fef3f-126">**Упорядочить таблицы**</span><span class="sxs-lookup"><span data-stu-id="fef3f-126">**Arrange Tables**</span></span>  
 <span data-ttu-id="fef3f-127">Упорядочивает объекты на панели в соответствии с макетом, указанным в параметре **Переключиться на диагональный макет** или **Переключиться на прямоугольный макет**.</span><span class="sxs-lookup"><span data-stu-id="fef3f-127">Arranges the objects in the pane according to the layout specified by selecting either **Switch to Diagonal Layout** or **Switch to Rectangular Layout**.</span></span>  
  
 <span data-ttu-id="fef3f-128">**Переключиться на диагональный макет**</span><span class="sxs-lookup"><span data-stu-id="fef3f-128">**Switch to Diagonal Layout**</span></span>  
 <span data-ttu-id="fef3f-129">Выберите для упорядочивания объектов по диагональному шаблону.</span><span class="sxs-lookup"><span data-stu-id="fef3f-129">Select to arrange objects in a diagonal pattern.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fef3f-130">Данный параметр отображается, только если выбран режим **Переключиться на прямоугольный макет** .</span><span class="sxs-lookup"><span data-stu-id="fef3f-130">This option is displayed only if **Switch to Rectangular Layout** is selected.</span></span>  
  
 <span data-ttu-id="fef3f-131">**Переключиться на прямоугольный макет**</span><span class="sxs-lookup"><span data-stu-id="fef3f-131">**Switch to Rectangular Layout**</span></span>  
 <span data-ttu-id="fef3f-132">Выберите для упорядочивания объектов по прямоугольному шаблону.</span><span class="sxs-lookup"><span data-stu-id="fef3f-132">Select to arrange objects in a rectangular pattern.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fef3f-133">Данный параметр отображается, только если выбран режим **Переключиться на диагональный макет** .</span><span class="sxs-lookup"><span data-stu-id="fef3f-133">This option is displayed only if **Switch to Diagonal Layout** is selected.</span></span>  
  
 <span data-ttu-id="fef3f-134">**Изменить представление источника данных**</span><span class="sxs-lookup"><span data-stu-id="fef3f-134">**Edit Data Source View**</span></span>  
 <span data-ttu-id="fef3f-135">Выводит окно **Конструктор представлений источника данных** для представления источников данных, связанного с данным измерением.</span><span class="sxs-lookup"><span data-stu-id="fef3f-135">Displays **Data Source View Designer** for the data source view associated with the dimension.</span></span> <span data-ttu-id="fef3f-136">Дополнительные сведения о **конструкторе представлений источников данных** см. в разделе [Конструктор представлений источников данных (службы Analysis Services — многомерные данные)](data-source-view-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="fef3f-136">For more information about **Data Source View Designe**r, see [Data Source View Designer &#40;Analysis Services - Multidimensional Data&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="fef3f-137">**Показать представление источника данных в**</span><span class="sxs-lookup"><span data-stu-id="fef3f-137">**Show Data Source View In**</span></span>  
 <span data-ttu-id="fef3f-138">Выберите один из следующих параметров, чтобы переключаться между режимами просмотра панели **Представление источника данных** :</span><span class="sxs-lookup"><span data-stu-id="fef3f-138">Select one of the following options to toggle between viewing the **Data Source View** pane in the following modes:</span></span>  
  
-   <span data-ttu-id="fef3f-139">Схема</span><span class="sxs-lookup"><span data-stu-id="fef3f-139">Diagram</span></span>  
  
     <span data-ttu-id="fef3f-140">Выводит диаграмму таблиц и столбцов, связанных с текущим измерением.</span><span class="sxs-lookup"><span data-stu-id="fef3f-140">Displays a diagram of the tables and columns associated with the current dimension.</span></span>  
  
-   <span data-ttu-id="fef3f-141">Дерево</span><span class="sxs-lookup"><span data-stu-id="fef3f-141">Tree</span></span>  
  
     <span data-ttu-id="fef3f-142">Выводит представление в виде дерева, которое содержит диаграмму таблиц и столбцов, связанных с текущим измерением.</span><span class="sxs-lookup"><span data-stu-id="fef3f-142">Displays a tree view that contains the tables and columns associated with the current dimension.</span></span>  
  
 <span data-ttu-id="fef3f-143">**Копировать диаграмму из**</span><span class="sxs-lookup"><span data-stu-id="fef3f-143">**Copy Diagram From**</span></span>  
 <span data-ttu-id="fef3f-144">Выберите одну из диаграмм, включенных в это представление данных, связанное с выбранным измерением, для отображения на панели **Представление источника данных** .</span><span class="sxs-lookup"><span data-stu-id="fef3f-144">Select one of the diagrams included in the data source view associated with the dimension to display it in the **Data Source View** pane.</span></span>  
  
 <span data-ttu-id="fef3f-145">**Масштаб**</span><span class="sxs-lookup"><span data-stu-id="fef3f-145">**Zoom**</span></span>  
 <span data-ttu-id="fef3f-146">Выберите доступный вариант масштаба.</span><span class="sxs-lookup"><span data-stu-id="fef3f-146">Select an available zoom option.</span></span>  
  
 <span data-ttu-id="fef3f-147">**Свойства**</span><span class="sxs-lookup"><span data-stu-id="fef3f-147">**Properties**</span></span>  
 <span data-ttu-id="fef3f-148">Отображает в **SQL Server Data Tools** окно **Свойства** для представления источников данных, связанного с измерением.</span><span class="sxs-lookup"><span data-stu-id="fef3f-148">Displays the **Properties** window in **SQL Server Data Tools** for the data source view associated with the dimension.</span></span>  
  
## <a name="table-context-menu"></a><span data-ttu-id="fef3f-149">Контекстное меню таблицы</span><span class="sxs-lookup"><span data-stu-id="fef3f-149">Table Context Menu</span></span>  
 <span data-ttu-id="fef3f-150">Команды, перечисленные в следующей таблице, находятся в контекстном меню, которое открывается, если щелкнуть правой кнопкой мыши имя таблицы или представлении на панели **Представление источника данных** .</span><span class="sxs-lookup"><span data-stu-id="fef3f-150">The options listed in the following table are available in the context menu displayed by right-clicking the name of a table or view in the **Data Source View** pane.</span></span>  
  
 <span data-ttu-id="fef3f-151">**Показывать связанные таблицы**</span><span class="sxs-lookup"><span data-stu-id="fef3f-151">**Show Related Tables**</span></span>  
 <span data-ttu-id="fef3f-152">Отображает на панели таблицы, связанные с таблицей, выбранной в представлении источника данных.</span><span class="sxs-lookup"><span data-stu-id="fef3f-152">Displays in the pane the tables related to the selected table in the data source view.</span></span>  
  
 <span data-ttu-id="fef3f-153">**Скрыть таблицу**</span><span class="sxs-lookup"><span data-stu-id="fef3f-153">**Hide Table**</span></span>  
 <span data-ttu-id="fef3f-154">Удаляет таблицу с панели.</span><span class="sxs-lookup"><span data-stu-id="fef3f-154">Removes the table from the pane.</span></span>  
  
 <span data-ttu-id="fef3f-155">**Просмотр данных**</span><span class="sxs-lookup"><span data-stu-id="fef3f-155">**Explore Data**</span></span>  
 <span data-ttu-id="fef3f-156">Открывает для выбранной таблицы диалоговое окно **Просмотр данных** .</span><span class="sxs-lookup"><span data-stu-id="fef3f-156">Displays the **Explore Data** dialog box for the selected table.</span></span>  
  
 <span data-ttu-id="fef3f-157">**Изменить представление источника данных**</span><span class="sxs-lookup"><span data-stu-id="fef3f-157">**Edit Data Source View**</span></span>  
 <span data-ttu-id="fef3f-158">Отображает **Конструктор представлений источников данных** для представления источников данных, содержащего выбранную таблицу.</span><span class="sxs-lookup"><span data-stu-id="fef3f-158">Displays **Data Source View Designer** for the data source view that contains the selected table.</span></span> <span data-ttu-id="fef3f-159">Дополнительные сведения о **конструкторе представлений источников данных** см. в разделе [Конструктор представлений источников данных (службы Analysis Services — многомерные данные)](data-source-view-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="fef3f-159">For more information about **Data Source View Designe**r, see [Data Source View Designer &#40;Analysis Services - Multidimensional Data&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="fef3f-160">**Свойства**</span><span class="sxs-lookup"><span data-stu-id="fef3f-160">**Properties**</span></span>  
 <span data-ttu-id="fef3f-161">Отображает окно **Свойства** для выбранной таблицы в **SQL Server Data Tools** .</span><span class="sxs-lookup"><span data-stu-id="fef3f-161">Displays the **Properties** window in **SQL Server Data Tools** for the selected table.</span></span>  
  
## <a name="column-context-menu"></a><span data-ttu-id="fef3f-162">Контекстное меню столбца</span><span class="sxs-lookup"><span data-stu-id="fef3f-162">Column Context Menu</span></span>  
 <span data-ttu-id="fef3f-163">Команды, перечисленные в следующей таблице, находятся в контекстном меню, которое открывается при щелчке правой кнопкой мыши по имени столбца в таблице или представления на панели **Представление источника данных** .</span><span class="sxs-lookup"><span data-stu-id="fef3f-163">The options listed in the following table are available in the context menu displayed by right-clicking the name of a column in a table or view in the **Data Source View** pane.</span></span>  
  
 <span data-ttu-id="fef3f-164">**Создать атрибут из столбца**</span><span class="sxs-lookup"><span data-stu-id="fef3f-164">**New Attribute from Column**</span></span>  
 <span data-ttu-id="fef3f-165">Отображает на панели таблицы, связанные с таблицей, выбранной в представлении источника данных.</span><span class="sxs-lookup"><span data-stu-id="fef3f-165">Displays in the pane the tables related to the selected table in the data source view.</span></span>  
  
 <span data-ttu-id="fef3f-166">**Просмотр данных**</span><span class="sxs-lookup"><span data-stu-id="fef3f-166">**Explore Data**</span></span>  
 <span data-ttu-id="fef3f-167">Открывает диалоговое окно **Просмотр данных** для таблицы, которая содержит выбранный столбец.</span><span class="sxs-lookup"><span data-stu-id="fef3f-167">Display the **Explore Data** dialog box for the table that contains the selected column.</span></span>  
  
 <span data-ttu-id="fef3f-168">**Изменить представление источника данных**</span><span class="sxs-lookup"><span data-stu-id="fef3f-168">**Edit Data Source View**</span></span>  
 <span data-ttu-id="fef3f-169">Отображает **Конструктор представлений источников данных** для представления источников данных, содержащего выбранный столбец.</span><span class="sxs-lookup"><span data-stu-id="fef3f-169">Displays **Data Source View Designer** for the data source view that contains the selected column.</span></span> <span data-ttu-id="fef3f-170">Дополнительные сведения о **конструкторе представлений источников данных** см. в разделе [Конструктор представлений источников данных (службы Analysis Services — многомерные данные)](data-source-view-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="fef3f-170">For more information about **Data Source View Designe**r, see [Data Source View Designer &#40;Analysis Services - Multidimensional Data&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="fef3f-171">**Свойства**</span><span class="sxs-lookup"><span data-stu-id="fef3f-171">**Properties**</span></span>  
 <span data-ttu-id="fef3f-172">Отображает в **SQL Server Data Tools** окно **Свойства** для выбранного столбца.</span><span class="sxs-lookup"><span data-stu-id="fef3f-172">Displays the **Properties** window in **SQL Server Data Tools** for the selected column.</span></span>  
  
## <a name="relationship-context-menu"></a><span data-ttu-id="fef3f-173">Контекстное меню связей</span><span class="sxs-lookup"><span data-stu-id="fef3f-173">Relationship Context Menu</span></span>  
 <span data-ttu-id="fef3f-174">Команды, перечисленные в следующей таблице, находятся в контекстном меню, которое открывается при щелчке правой кнопкой мыши по панели **Представление источника данных** .</span><span class="sxs-lookup"><span data-stu-id="fef3f-174">The options listed in the following table are available in the context menu displayed by right-clicking a relationship in the **Data Source View** pane.</span></span>  
  
 <span data-ttu-id="fef3f-175">**Изменить представление источника данных**</span><span class="sxs-lookup"><span data-stu-id="fef3f-175">**Edit Data Source View**</span></span>  
 <span data-ttu-id="fef3f-176">Отображает **Конструктор представлений источников данных** для представления источников данных, содержащего выбранную связь.</span><span class="sxs-lookup"><span data-stu-id="fef3f-176">Displays **Data Source View Designer** for the data source view that contains the selected relationship.</span></span> <span data-ttu-id="fef3f-177">Дополнительные сведения о **конструкторе представлений источников данных** см. в разделе [Конструктор представлений источников данных (службы Analysis Services — многомерные данные)](data-source-view-designer-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="fef3f-177">For more information about **Data Source View Designe**r, see [Data Source View Designer &#40;Analysis Services - Multidimensional Data&#41;](data-source-view-designer-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="fef3f-178">**Свойства**</span><span class="sxs-lookup"><span data-stu-id="fef3f-178">**Properties**</span></span>  
 <span data-ttu-id="fef3f-179">Отображает окно **Свойства** в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] для выбранной связи.</span><span class="sxs-lookup"><span data-stu-id="fef3f-179">Displays the **Properties** window in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] for the selected relationship.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fef3f-180">См. также:</span><span class="sxs-lookup"><span data-stu-id="fef3f-180">See Also</span></span>  
 <span data-ttu-id="fef3f-181">[Структура измерения &#40;конструктор измерений&#41; &#40;Analysis Services многомерных данных&#41;](dimension-structure-dimension-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="fef3f-181">[Dimension Structure &#40;Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](dimension-structure-dimension-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="fef3f-182">[Панель инструментов &#40;вкладка «Структура измерения», конструктор измерений&#41; &#40;Analysis Services многомерных данных&#41;](toolbar-dimension-structure-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="fef3f-182">[Toolbar &#40;Dimension Structure Tab, Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-dimension-structure-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="fef3f-183">[Атрибуты &#40;вкладка «Структура измерения», конструктор измерений&#41; &#40;Analysis Services многомерных данных&#41;](attributes-dimension-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="fef3f-183">[Attributes &#40;Dimension Structure Tab, Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](attributes-dimension-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="fef3f-184">Иерархии &#40;вкладка «Структура измерения», конструктор измерений&#41; &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="fef3f-184">Hierarchies &#40;Dimension Structure Tab, Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](hierarchies-dimension-designer-analysis-services-multidimensional-data.md)  
  
  
