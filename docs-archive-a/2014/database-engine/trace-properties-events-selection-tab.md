---
title: Свойства трассировки (вкладка «Выбор событий») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.traceproperties.eventsselection.f1
helpviewer_keywords:
- Trace Properties dialog box
ms.assetid: e1892f24-7272-4d5d-8926-6150cc82b2c3
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 11f4725865d39c21e36f5fd09eaf2afd4cde3017
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734398"
---
# <a name="trace-properties-events-selection-tab"></a><span data-ttu-id="5c467-102">Свойства трассировки (вкладка «Выбор событий»)</span><span class="sxs-lookup"><span data-stu-id="5c467-102">Trace Properties (Events Selection Tab)</span></span>
  <span data-ttu-id="5c467-103">Вкладка **Выбор событий** диалогового окна **Свойства трассировки** используется для просмотра и указания трассируемых событий и столбцов данных.</span><span class="sxs-lookup"><span data-stu-id="5c467-103">Use the **Events Selection** tab of the **Trace Properties** dialog box to view or specify traced events and data columns.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5c467-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="5c467-104">Options</span></span>  
 <span data-ttu-id="5c467-105">Столбец**События**</span><span class="sxs-lookup"><span data-stu-id="5c467-105">**Events** column</span></span>  
 <span data-ttu-id="5c467-106">Укажите трассируемые события, устанавливая или снимая флажок в соответствующем столбце.</span><span class="sxs-lookup"><span data-stu-id="5c467-106">Specify traced events by selecting or clearing the check box in the event column.</span></span> <span data-ttu-id="5c467-107">**События** упорядочены по категориям событий.</span><span class="sxs-lookup"><span data-stu-id="5c467-107">**Events** are organized by event category.</span></span> <span data-ttu-id="5c467-108">Классы событий, указанные в шаблоне, выбираются автоматически.</span><span class="sxs-lookup"><span data-stu-id="5c467-108">Event classes specified in the template are automatically selected.</span></span> <span data-ttu-id="5c467-109">Дополнительные сведения см. в разделе [SQL Server Event Class Reference](../relational-databases/event-classes/sql-server-event-class-reference.md).</span><span class="sxs-lookup"><span data-stu-id="5c467-109">For more information, see [SQL Server Event Class Reference](../relational-databases/event-classes/sql-server-event-class-reference.md).</span></span>  
  
 <span data-ttu-id="5c467-110">Столбцы данных</span><span class="sxs-lookup"><span data-stu-id="5c467-110">Data columns</span></span>  
 <span data-ttu-id="5c467-111">Укажите трассируемые столбцы данных, устанавливая флажки для соответствующих событий и столбцов данных.</span><span class="sxs-lookup"><span data-stu-id="5c467-111">Specify traced data columns by checking the box that corresponds with the event and the data column you need.</span></span> <span data-ttu-id="5c467-112">Для каждого из событий, включенных в трассировку, все основные столбцы отмечены по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5c467-112">All relevant event columns are checked by default for each event included in the trace.</span></span>  
  
 <span data-ttu-id="5c467-113">Для определения фильтра щелкните заголовок столбца данных и введите критерии фильтра.</span><span class="sxs-lookup"><span data-stu-id="5c467-113">Specify filters by clicking the data column heading and entering the filter criteria.</span></span> <span data-ttu-id="5c467-114">Отфильтрованные столбцы данных отображаются значком фильтра слева от метки столбца в диалоговом окне **Изменение фильтра** .</span><span class="sxs-lookup"><span data-stu-id="5c467-114">Filtered data columns are indicated by a filter icon to the left of the column label in the **Edit Filter** dialog box.</span></span> <span data-ttu-id="5c467-115">Дополнительные сведения см. в разделе [SQL Server Profiler - Edit Filter](../../2014/database-engine/sql-server-profiler-edit-filter.md).</span><span class="sxs-lookup"><span data-stu-id="5c467-115">For more information, see [SQL Server Profiler - Edit Filter](../../2014/database-engine/sql-server-profiler-edit-filter.md).</span></span>  
  
 <span data-ttu-id="5c467-116">**Показать все события**</span><span class="sxs-lookup"><span data-stu-id="5c467-116">**Show all events**</span></span>  
 <span data-ttu-id="5c467-117">Показать все доступные события.</span><span class="sxs-lookup"><span data-stu-id="5c467-117">Show all available events.</span></span> <span data-ttu-id="5c467-118">По умолчанию отображаются только те строки, которые отмечены в сетке **Выбор событий** .</span><span class="sxs-lookup"><span data-stu-id="5c467-118">By default, only rows in the **Events Selection** grid that are selected display.</span></span> <span data-ttu-id="5c467-119">Снимите этот флажок, чтобы скрыть все события, не выбранные в сетке **Выбор событий** .</span><span class="sxs-lookup"><span data-stu-id="5c467-119">Uncheck this box to hide all unselected events in the **Events Selection** grid.</span></span>  
  
 <span data-ttu-id="5c467-120">**Показать все столбцы**</span><span class="sxs-lookup"><span data-stu-id="5c467-120">**Show all columns**</span></span>  
 <span data-ttu-id="5c467-121">Показать все доступные столбцы данных.</span><span class="sxs-lookup"><span data-stu-id="5c467-121">Show all available data columns.</span></span> <span data-ttu-id="5c467-122">По умолчанию отображаются только выбранные столбцы данных.</span><span class="sxs-lookup"><span data-stu-id="5c467-122">By default, only data columns that are selected display.</span></span> <span data-ttu-id="5c467-123">Снимите этот флажок, чтобы скрыть все невыбранные столбцы данных в сетке **Выбор событий** .</span><span class="sxs-lookup"><span data-stu-id="5c467-123">Uncheck this box to hide all unselected data columns in the **Events Selection** grid.</span></span>  
  
 <span data-ttu-id="5c467-124">**Фильтры столбцов**</span><span class="sxs-lookup"><span data-stu-id="5c467-124">**Column Filters**</span></span>  
 <span data-ttu-id="5c467-125">Открывает диалоговое окно **Изменение фильтра** .</span><span class="sxs-lookup"><span data-stu-id="5c467-125">Launches the **Edit Filter** dialog box.</span></span> <span data-ttu-id="5c467-126">Это диалоговое окно предназначено для редактирования фильтров столбцов данных.</span><span class="sxs-lookup"><span data-stu-id="5c467-126">You can use this dialog to edit data column filters.</span></span>  
  
 <span data-ttu-id="5c467-127">**Систематизировать столбцы**</span><span class="sxs-lookup"><span data-stu-id="5c467-127">**Organize Columns**</span></span>  
 <span data-ttu-id="5c467-128">Изменяет порядок следования столбцов в трассировке и группирует результаты по одному или нескольким столбцам.</span><span class="sxs-lookup"><span data-stu-id="5c467-128">Changes the order of columns in the trace and groups results by one or more columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c467-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="5c467-129">See Also</span></span>  
 <span data-ttu-id="5c467-130">[Укажите события и столбцы данных для файла трассировки &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="5c467-130">[Specify Events and Data Columns for a Trace File &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="5c467-131">[Упорядочение столбцов, отображаемых в &#40;трассировки SQL Server Profiler&#41;](../tools/sql-server-profiler/organize-columns-displayed-in-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="5c467-131">[Organize Columns Displayed in a Trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/organize-columns-displayed-in-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="5c467-132">[Фильтрация событий в SQL Server Profiler &#40;трассировки&#41;](../tools/sql-server-profiler/filter-events-in-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="5c467-132">[Filter Events in a Trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/filter-events-in-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="5c467-133">[Просмотр сведений о фильтре &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/view-filter-information-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="5c467-133">[View Filter Information &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/view-filter-information-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="5c467-134">[Изменение &#40;фильтра SQL Server Profiler&#41;](../tools/sql-server-profiler/modify-a-filter-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="5c467-134">[Modify a Filter &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/modify-a-filter-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="5c467-135">[Шаблоны и разрешения приложения SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="5c467-135">[SQL Server Profiler Templates and Permissions](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="5c467-136">Приложение SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="5c467-136">SQL Server Profiler</span></span>](../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
