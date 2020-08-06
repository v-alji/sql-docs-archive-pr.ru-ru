---
title: Свойства шаблона трассировки (вкладка «Выбор событий») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.tracetemplateproperties.eventsselection.f1
helpviewer_keywords:
- Trace Template Properties dialog box
ms.assetid: 5b202457-ab42-4902-8012-7f3f40aa09f5
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: da497db6e9373c63836753dc2be96deb3ce90244
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740289"
---
# <a name="trace-template-properties-events-selection-tab"></a><span data-ttu-id="5830c-102">Свойства шаблона трассировки (вкладка «Выбор событий»)</span><span class="sxs-lookup"><span data-stu-id="5830c-102">Trace Template Properties (Events Selection Tab)</span></span>
  <span data-ttu-id="5830c-103">С помощью вкладки **Выбор событий** в окне **Свойства шаблона трассировки** просмотрите, измените или задайте классы событий и столбцы данных, которые будут включены в шаблон трассировки приложения [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5830c-103">Use the **Events Selection** tab of the **Trace Template Properties** dialog box to view, edit, or specify event classes and data columns to include in a [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] trace template.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5830c-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="5830c-104">Options</span></span>  
 <span data-ttu-id="5830c-105">Столбец**События**</span><span class="sxs-lookup"><span data-stu-id="5830c-105">**Events** column</span></span>  
 <span data-ttu-id="5830c-106">С помощью установки или снятия флажка в столбце событий укажите события для трассировки.</span><span class="sxs-lookup"><span data-stu-id="5830c-106">Specify events that should be traced by selecting or clearing the check box in the event column.</span></span> <span data-ttu-id="5830c-107">События упорядочиваются по категориям событий.</span><span class="sxs-lookup"><span data-stu-id="5830c-107">Events are organized by event category.</span></span>  
  
 <span data-ttu-id="5830c-108">Если выбран параметр **Использовать существующий шаблон в качестве основы** на вкладке **Общие** , то события автоматически выбираются в соответствии с указанным шаблоном.</span><span class="sxs-lookup"><span data-stu-id="5830c-108">If you selected **Base new template on existing one** on the **General** tab, events are automatically selected according to the specified template.</span></span> <span data-ttu-id="5830c-109">Дополнительные сведения о классах событий см. в разделе [SQL Server Event Class Reference](../relational-databases/event-classes/sql-server-event-class-reference.md).</span><span class="sxs-lookup"><span data-stu-id="5830c-109">For more information about event classes, see [SQL Server Event Class Reference](../relational-databases/event-classes/sql-server-event-class-reference.md).</span></span>  
  
 <span data-ttu-id="5830c-110">Столбцы данных</span><span class="sxs-lookup"><span data-stu-id="5830c-110">Data columns</span></span>  
 <span data-ttu-id="5830c-111">С помощью установки флажка, соответствующего нужному событию и столбцу данных, укажите столбцы данных для трассировки.</span><span class="sxs-lookup"><span data-stu-id="5830c-111">Specify data columns that should be traced by checking the box that corresponds with the event and the data column you need.</span></span> <span data-ttu-id="5830c-112">Для каждого трассируемого события по умолчанию выбираются все соответствующие столбцы событий, если установлен флажок, соответствующий этому событию.</span><span class="sxs-lookup"><span data-stu-id="5830c-112">All relevant event columns are checked by default for each event included in the trace, if the checkbox corresponding to the event is checked.</span></span> <span data-ttu-id="5830c-113">Если установлен флажок **Использовать существующий шаблон в качестве основы** на вкладке **Общие** , то столбцы данных и фильтры автоматически выбираются в соответствии с указанным шаблоном.</span><span class="sxs-lookup"><span data-stu-id="5830c-113">If you checked **Base new template on existing one** on the **General** tab, data columns and filters are automatically selected according to the specified template.</span></span>  
  
 <span data-ttu-id="5830c-114">Для определения фильтра щелкните заголовок столбца данных и введите критерии фильтра.</span><span class="sxs-lookup"><span data-stu-id="5830c-114">Specify filters by clicking the data column heading and entering the filter criteria.</span></span> <span data-ttu-id="5830c-115">Отфильтрованные столбцы данных отображаются значком фильтра слева от метки столбца в диалоговом окне **Изменение фильтра** .</span><span class="sxs-lookup"><span data-stu-id="5830c-115">Filtered data columns are indicated by a filter icon to the left of the column label in the **Edit Filter** dialog box.</span></span>  
  
 <span data-ttu-id="5830c-116">**Показать все события**</span><span class="sxs-lookup"><span data-stu-id="5830c-116">**Show all events**</span></span>  
 <span data-ttu-id="5830c-117">Показать все доступные события.</span><span class="sxs-lookup"><span data-stu-id="5830c-117">Show all available events.</span></span> <span data-ttu-id="5830c-118">Этот параметр включен по умолчанию при создании нового шаблона, не основанного на существующем шаблоне.</span><span class="sxs-lookup"><span data-stu-id="5830c-118">This option is checked by default if you are creating a new template that is not based on an existing template.</span></span> <span data-ttu-id="5830c-119">Снимите флажок, чтобы скрыть все события, не выбранные в сетке **Выбор событий** .</span><span class="sxs-lookup"><span data-stu-id="5830c-119">Uncheck to hide all unselected events in the **Events Selection** grid.</span></span>  
  
 <span data-ttu-id="5830c-120">**Показать все столбцы**</span><span class="sxs-lookup"><span data-stu-id="5830c-120">**Show all columns**</span></span>  
 <span data-ttu-id="5830c-121">Показать все доступные столбцы данных.</span><span class="sxs-lookup"><span data-stu-id="5830c-121">Show all available data columns.</span></span> <span data-ttu-id="5830c-122">Этот параметр включен по умолчанию при создании нового шаблона, не основанного на существующем шаблоне.</span><span class="sxs-lookup"><span data-stu-id="5830c-122">This option is checked by default if you are creating a new template that is not based on an existing template.</span></span> <span data-ttu-id="5830c-123">Снимите флажок, чтобы скрыть все столбцы данных, не выбранные в сетке **Выбор событий** .</span><span class="sxs-lookup"><span data-stu-id="5830c-123">Uncheck to hide all unselected data columns in the **Events Selection** grid.</span></span>  
  
 <span data-ttu-id="5830c-124">**Фильтры столбцов**</span><span class="sxs-lookup"><span data-stu-id="5830c-124">**Column Filters**</span></span>  
 <span data-ttu-id="5830c-125">Открывает окно **Изменение фильтра**, в котором слева от метки столбца данных показан значок фильтра.</span><span class="sxs-lookup"><span data-stu-id="5830c-125">Launches the **Edit Filter** dialog box, which displays a filter icon to the left of the data column label.</span></span> <span data-ttu-id="5830c-126">Используйте диалоговое окно **Изменение фильтра** для изменения фильтров столбцов.</span><span class="sxs-lookup"><span data-stu-id="5830c-126">Use the **Edit Filter** dialog box to edit data column filters.</span></span>  
  
 <span data-ttu-id="5830c-127">**Систематизировать столбцы**</span><span class="sxs-lookup"><span data-stu-id="5830c-127">**Organize Columns**</span></span>  
 <span data-ttu-id="5830c-128">Изменяет порядок следования столбцов в трассировке и группирует результаты по одному или нескольким столбцам.</span><span class="sxs-lookup"><span data-stu-id="5830c-128">Changes the order of columns in the trace and groups results by one or more columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5830c-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="5830c-129">See Also</span></span>  
 <span data-ttu-id="5830c-130">[Укажите события и столбцы данных для файла трассировки &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="5830c-130">[Specify Events and Data Columns for a Trace File &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="5830c-131">[Упорядочение столбцов, отображаемых в &#40;трассировки SQL Server Profiler&#41;](../tools/sql-server-profiler/organize-columns-displayed-in-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="5830c-131">[Organize Columns Displayed in a Trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/organize-columns-displayed-in-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="5830c-132">[Фильтрация событий в SQL Server Profiler &#40;трассировки&#41;](../tools/sql-server-profiler/filter-events-in-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="5830c-132">[Filter Events in a Trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/filter-events-in-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="5830c-133">[Просмотр сведений о фильтре &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/view-filter-information-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="5830c-133">[View Filter Information &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/view-filter-information-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="5830c-134">[Изменение &#40;фильтра SQL Server Profiler&#41;](../tools/sql-server-profiler/modify-a-filter-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="5830c-134">[Modify a Filter &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/modify-a-filter-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="5830c-135">[Шаблоны и разрешения приложения SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="5830c-135">[SQL Server Profiler Templates and Permissions](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="5830c-136">Приложение SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="5830c-136">SQL Server Profiler</span></span>](../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
