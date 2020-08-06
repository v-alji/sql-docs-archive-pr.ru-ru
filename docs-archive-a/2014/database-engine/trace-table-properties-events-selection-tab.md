---
title: Свойства таблицы трассировки (вкладка «Выбор событий») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.tracetableproperties.eventsselection.f1
helpviewer_keywords:
- Trace Table Properties dialog box
ms.assetid: fa21df6a-b6b5-4b15-9104-957385821594
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: a2e72f299c9d83762876ce250f750924430ba2f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750108"
---
# <a name="trace-table-properties-events-selection-tab"></a><span data-ttu-id="4978d-102">Свойства таблицы трассировки (вкладка «Выбор событий»)</span><span class="sxs-lookup"><span data-stu-id="4978d-102">Trace Table Properties (Events Selection Tab)</span></span>
  <span data-ttu-id="4978d-103">Используйте вкладку **Выбор событий** в диалоговом окне **Свойства таблицы трассировки** для просмотра событий и свойств столбца данных трассировки или для удаления событий или столбцов из трассировки.</span><span class="sxs-lookup"><span data-stu-id="4978d-103">Use the **Events Selection** tab of the **Trace Table Properties** dialog box to view the events and data column properties of the trace or to remove events or columns from the trace.</span></span>  
  
 <span data-ttu-id="4978d-104">Для просмотра данного окна используйте приложение [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] , чтобы открыть таблицу трассировки.</span><span class="sxs-lookup"><span data-stu-id="4978d-104">To view this window, use [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] to open a trace table.</span></span> <span data-ttu-id="4978d-105">Затем в меню **файл** выберите пункт **свойства**, а затем перейдите на вкладку **Выбор событий** .</span><span class="sxs-lookup"><span data-stu-id="4978d-105">Then on the **File** menu, click **Properties**, and then click the **Events Selection** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4978d-106">Варианты</span><span class="sxs-lookup"><span data-stu-id="4978d-106">Options</span></span>  
 <span data-ttu-id="4978d-107">Столбец**События**</span><span class="sxs-lookup"><span data-stu-id="4978d-107">**Events** column</span></span>  
 <span data-ttu-id="4978d-108">Просмотр событий трассировки, систематизированных по категориям событий.</span><span class="sxs-lookup"><span data-stu-id="4978d-108">View traced events which are organized by event category.</span></span> <span data-ttu-id="4978d-109">Выбор событий может быть осуществлен путем установки флажка для поля или столбца события.</span><span class="sxs-lookup"><span data-stu-id="4978d-109">Events can be selected by checking the box or by checking a data column for an event.</span></span> <span data-ttu-id="4978d-110">При установке флажка выбираются все столбцы данных, доступные для этого события.</span><span class="sxs-lookup"><span data-stu-id="4978d-110">If the event box is checked, all data columns available for that event are selected.</span></span> <span data-ttu-id="4978d-111">Если флажок установлен для столбца данных, автоматически устанавливается флажок для события, а также для всех других необходимых столбцов данных.</span><span class="sxs-lookup"><span data-stu-id="4978d-111">If the data column for an event is checked, the event is checked and any other required column is also automatically checked.</span></span> <span data-ttu-id="4978d-112">При просмотре файла трассировки или таблицы снятие флажков событий и столбцов данных уменьшает количество видимых в окне трассировки данных, что облегчает их анализ.</span><span class="sxs-lookup"><span data-stu-id="4978d-112">If you are viewing a trace file or table, clearing check boxes for events or data columns reduces the amount of visible data in the trace window for easier analysis.</span></span> <span data-ttu-id="4978d-113">Существует также возможность изменения фильтров столбцов, что позволяет уменьшить количество видимых в окне трассировки данных.</span><span class="sxs-lookup"><span data-stu-id="4978d-113">You can also change column filters to reduce the amount of visible data in the trace window.</span></span> <span data-ttu-id="4978d-114">Дополнительные сведения о классах событий см. в разделе [SQL Server Event Class Reference](../relational-databases/event-classes/sql-server-event-class-reference.md).</span><span class="sxs-lookup"><span data-stu-id="4978d-114">For more information about event classes, see [SQL Server Event Class Reference](../relational-databases/event-classes/sql-server-event-class-reference.md).</span></span>  
  
 <span data-ttu-id="4978d-115">Иные столбцы данных</span><span class="sxs-lookup"><span data-stu-id="4978d-115">Other data columns</span></span>  
 <span data-ttu-id="4978d-116">Просмотр столбцов данных трассировки.</span><span class="sxs-lookup"><span data-stu-id="4978d-116">View traced data columns.</span></span> <span data-ttu-id="4978d-117">По умолчанию для каждого события, включенного в трассировку, помечаются все относящиеся к нему столбцы данных трассировки.</span><span class="sxs-lookup"><span data-stu-id="4978d-117">All relevant data columns in the trace are checked by default for each event included in the trace.</span></span>  
  
 <span data-ttu-id="4978d-118">Для определения фильтра щелкните заголовок столбца данных и введите критерии фильтра.</span><span class="sxs-lookup"><span data-stu-id="4978d-118">Specify filters by clicking the data column heading and entering the filter criteria.</span></span> <span data-ttu-id="4978d-119">Отфильтрованные столбцы данных отображаются значком фильтра слева от метки столбца в диалоговом окне **Изменение фильтра** .</span><span class="sxs-lookup"><span data-stu-id="4978d-119">Filtered data columns are indicated by a filter icon to the left of the column label in the **Edit Filter** dialog box.</span></span>  
  
 <span data-ttu-id="4978d-120">**Показать все события**</span><span class="sxs-lookup"><span data-stu-id="4978d-120">**Show all events**</span></span>  
 <span data-ttu-id="4978d-121">Показать все доступные события.</span><span class="sxs-lookup"><span data-stu-id="4978d-121">Show all available events.</span></span> <span data-ttu-id="4978d-122">По умолчанию отображаются только те строки, которые отмечены в сетке **Выбор событий** .</span><span class="sxs-lookup"><span data-stu-id="4978d-122">By default, only rows in the **Events Selection** grid that are selected display.</span></span> <span data-ttu-id="4978d-123">Снимите этот флажок, чтобы скрыть все события, не выбранные в сетке **Выбор событий** .</span><span class="sxs-lookup"><span data-stu-id="4978d-123">Uncheck this box to hide all unselected events in the **Events Selection** grid.</span></span> <span data-ttu-id="4978d-124">Если установлен флажок **Показать все события** и идет просмотр файла или таблицы трассировки, то все события, фиксировавшиеся в ходе трассировки, отображаются в окне трассировки.</span><span class="sxs-lookup"><span data-stu-id="4978d-124">If **Show all events** is checked and you are viewing a trace file or table, all events that were recorded in the trace display in the trace window.</span></span>  
  
 <span data-ttu-id="4978d-125">**Показать все столбцы**</span><span class="sxs-lookup"><span data-stu-id="4978d-125">**Show all columns**</span></span>  
 <span data-ttu-id="4978d-126">Показать все доступные столбцы данных.</span><span class="sxs-lookup"><span data-stu-id="4978d-126">Show all available data columns.</span></span> <span data-ttu-id="4978d-127">По умолчанию отображаются только выбранные столбцы данных.</span><span class="sxs-lookup"><span data-stu-id="4978d-127">By default, only data columns that are selected display.</span></span> <span data-ttu-id="4978d-128">Снимите этот флажок, чтобы скрыть все невыбранные столбцы данных в сетке **Выбор событий** .</span><span class="sxs-lookup"><span data-stu-id="4978d-128">Uncheck this box to hide all unselected data columns in the **Events Selection** grid.</span></span>  
  
 <span data-ttu-id="4978d-129">**Фильтры столбцов**</span><span class="sxs-lookup"><span data-stu-id="4978d-129">**Column Filters**</span></span>  
 <span data-ttu-id="4978d-130">Запускает диалоговое окно **Изменение фильтра**, которое показывает значок фильтра слева от метки столбца.</span><span class="sxs-lookup"><span data-stu-id="4978d-130">Launches the **Edit Filter** dialog box, which displays a filter icon to the left of the column label.</span></span> <span data-ttu-id="4978d-131">Используйте это диалоговое окно для редактирования фильтров столбцов.</span><span class="sxs-lookup"><span data-stu-id="4978d-131">You can use this dialog box to edit data column filters.</span></span>  
  
 <span data-ttu-id="4978d-132">**Систематизировать столбцы**</span><span class="sxs-lookup"><span data-stu-id="4978d-132">**Organize Columns**</span></span>  
 <span data-ttu-id="4978d-133">После выбора **событий** и столбцов данных для трассировки нажмите кнопку **Упорядочить столбцы**, чтобы принудительно переупорядочить столбцы в окне результатов трассировки.</span><span class="sxs-lookup"><span data-stu-id="4978d-133">After selecting **Events** and data columns to trace, click **Organize Columns** to force the grid to reorder the column in the trace results window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4978d-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="4978d-134">See Also</span></span>  
 <span data-ttu-id="4978d-135">[Откройте таблицу трассировки &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/open-a-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="4978d-135">[Open a Trace Table &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/open-a-trace-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="4978d-136">[Шаблоны и разрешения приложения SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="4978d-136">[SQL Server Profiler Templates and Permissions](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="4978d-137">Приложение SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="4978d-137">SQL Server Profiler</span></span>](../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
