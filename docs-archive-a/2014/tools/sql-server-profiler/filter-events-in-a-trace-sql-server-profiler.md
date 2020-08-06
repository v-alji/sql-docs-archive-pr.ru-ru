---
title: Фильтрация событий в трассировке (SQL Server Profiler) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- filters [SQL Server], traces
- traces [SQL Server], filters
- traces [SQL Server], events
ms.assetid: 0fd63573-3b35-4f67-9e1e-ed9aabee11a8
author: stevestein
ms.author: sstein
ms.openlocfilehash: fef9dd6956d407011261c54f796a751a0bf94941
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739029"
---
# <a name="filter-events-in-a-trace-sql-server-profiler"></a><span data-ttu-id="dfff9-102">фильтровать события в трассировке (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="dfff9-102">Filter Events in a Trace (SQL Server Profiler)</span></span>
  <span data-ttu-id="dfff9-103">Фильтры ограничивают накопление событий в трассировке.</span><span class="sxs-lookup"><span data-stu-id="dfff9-103">Filters limit the events collected in a trace.</span></span> <span data-ttu-id="dfff9-104">Если фильтр не установлен, то на выход трассировки возвращаются все события выбранных классов событий.</span><span class="sxs-lookup"><span data-stu-id="dfff9-104">If a filter is not set, all events of the selected event classes are returned in the trace output.</span></span> <span data-ttu-id="dfff9-105">Установка фильтра трассировки необязательна.</span><span class="sxs-lookup"><span data-stu-id="dfff9-105">It is not mandatory to set a filter for a trace.</span></span> <span data-ttu-id="dfff9-106">Однако фильтр минимизирует затраты ресурсов при трассировке.</span><span class="sxs-lookup"><span data-stu-id="dfff9-106">However, a filter minimizes the overhead that is incurred during tracing.</span></span>  
  
 <span data-ttu-id="dfff9-107">Фильтры для определений трассировки добавляются на вкладке **Выбор событий** в диалоговом окне **Свойства трассировки** или **Свойства шаблона трассировки** .</span><span class="sxs-lookup"><span data-stu-id="dfff9-107">You add filters to trace definitions by using the **Events Selection** tab of the **Trace Properties** or **Trace Template Properties** dialog box.</span></span>  
  
### <a name="to-filter-events-in-a-trace"></a><span data-ttu-id="dfff9-108">Фильтрация событий в трассировке</span><span class="sxs-lookup"><span data-stu-id="dfff9-108">To filter events in a trace</span></span>  
  
1.  <span data-ttu-id="dfff9-109">В диалоговом окне **Свойства трассировки** или **Свойства шаблона трассировки** перейдите на вкладку **Выбор событий** .</span><span class="sxs-lookup"><span data-stu-id="dfff9-109">In the **Trace Properties** or **Trace Template Properties** dialog box, click the **Events Selection** tab.</span></span>  
  
     <span data-ttu-id="dfff9-110">Вкладка **Выбор событий** содержит сетку.</span><span class="sxs-lookup"><span data-stu-id="dfff9-110">The **Events Selection** tab contains a grid control.</span></span> <span data-ttu-id="dfff9-111">Сетка — это таблица, которая содержит каждый из классов событий, доступных для трассировки.</span><span class="sxs-lookup"><span data-stu-id="dfff9-111">The grid control is a table that contains each of the traceable event classes.</span></span> <span data-ttu-id="dfff9-112">На каждый класс событий в таблице приходится по одной строке.</span><span class="sxs-lookup"><span data-stu-id="dfff9-112">The table contains one row for each event class.</span></span> <span data-ttu-id="dfff9-113">Классы событий могут незначительно различаться в зависимости от типа и версии сервера, к которому они подключены.</span><span class="sxs-lookup"><span data-stu-id="dfff9-113">The event classes may differ slightly, depending on the type and version of server to which you are connected.</span></span> <span data-ttu-id="dfff9-114">Классы событий идентифицируются в столбце **События**сетки и группируются по категориям событий.</span><span class="sxs-lookup"><span data-stu-id="dfff9-114">The event classes are identified in the **Events**column of the grid and are grouped by event category.</span></span> <span data-ttu-id="dfff9-115">В оставшихся столбцах перечислены столбцы данных, которые могут быть возвращены для каждого класса событий.</span><span class="sxs-lookup"><span data-stu-id="dfff9-115">The remaining columns list the data columns that can be returned for each event class.</span></span>  
  
2.  <span data-ttu-id="dfff9-116">Выберите пункт **Фильтры столбцов.**</span><span class="sxs-lookup"><span data-stu-id="dfff9-116">Click **Column Filters.**</span></span>  
  
     <span data-ttu-id="dfff9-117">Открывается диалоговое окно **Изменение фильтра**.</span><span class="sxs-lookup"><span data-stu-id="dfff9-117">The **Edit Filter**dialog box appears.</span></span> <span data-ttu-id="dfff9-118">Окно **Изменение фильтра**содержит список операторов сравнения, которые можно использовать для фильтрации событий в трассировке.</span><span class="sxs-lookup"><span data-stu-id="dfff9-118">The **Edit Filter**dialog box contains a list of comparison operators that you can use to filter events in a trace.</span></span>  
  
3.  <span data-ttu-id="dfff9-119">Чтобы применить фильтр, щелкните оператор сравнения и введите необходимое значение.</span><span class="sxs-lookup"><span data-stu-id="dfff9-119">To apply a filter, click the comparison operator, and type a value to use for the filter.</span></span>  
  
4.  <span data-ttu-id="dfff9-120">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="dfff9-120">Click **OK**.</span></span>  
  
 <span data-ttu-id="dfff9-121">**Рекомендации**</span><span class="sxs-lookup"><span data-stu-id="dfff9-121">**Considerations:**</span></span>  
  
-   <span data-ttu-id="dfff9-122">Если условия фильтрации установлены в столбцах данных **StartTime** и **EndTime** на вкладке «Выбор событий», убедитесь в том, что выполняются следующие условия:</span><span class="sxs-lookup"><span data-stu-id="dfff9-122">If you set filter conditions on the **StartTime** and **EndTime** data columns of the Events Selection tab, then make sure that:</span></span>  
  
    -   <span data-ttu-id="dfff9-123">Дата введена в формате `YYYY/MM/DD HH:mm:sec`.</span><span class="sxs-lookup"><span data-stu-id="dfff9-123">The date you enter matches this format: `YYYY/MM/DD HH:mm:sec`.</span></span>  
  
         <span data-ttu-id="dfff9-124">-или-</span><span class="sxs-lookup"><span data-stu-id="dfff9-124">-OR-</span></span>  
  
    -   <span data-ttu-id="dfff9-125">В диалоговом окне**Общие параметры** выбран параметр **Применять региональные настройки для отображения даты и времени** .</span><span class="sxs-lookup"><span data-stu-id="dfff9-125">**Use regional settings to display date and time values** is checked in the **General Options** dialog box.</span></span> <span data-ttu-id="dfff9-126">Чтобы открыть диалоговое окно **Общие параметры**, в меню [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]Инструменты**в** выберите пункт **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="dfff9-126">To view the **General Options** dialog box, on the [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] **Tools** menu, click **Option**.</span></span>  
  
         <span data-ttu-id="dfff9-127">и</span><span class="sxs-lookup"><span data-stu-id="dfff9-127">-AND-</span></span>  
  
    -   <span data-ttu-id="dfff9-128">Должна быть введена дата между 1 января 1753 г. и 31 декабря 9999 г.</span><span class="sxs-lookup"><span data-stu-id="dfff9-128">The date you enter is between January 1, 1753 and December 31, 9999.</span></span>  
  
-   <span data-ttu-id="dfff9-129">Если события трассируются из программы **osql** или **sqlcmd** , то всегда добавляйте **%** к фильтрам для столбца данных **TextData** .</span><span class="sxs-lookup"><span data-stu-id="dfff9-129">If tracing events from the **osql** utility or from the **sqlcmd** utility, always append **%** to filters on the **TextData** data column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfff9-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="dfff9-130">See Also</span></span>  
 [<span data-ttu-id="dfff9-131">Приложение SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="dfff9-131">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
