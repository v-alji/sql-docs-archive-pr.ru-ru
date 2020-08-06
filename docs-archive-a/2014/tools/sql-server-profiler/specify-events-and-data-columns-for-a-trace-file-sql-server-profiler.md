---
title: Задание столбцов данных и событий для файла трассировки (приложение SQL Server Profiler) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- adding events
- traces [SQL Server], data columns
- deleting events
- removing events
- traces [SQL Server], events
ms.assetid: 7da715a3-2f03-4063-b6a4-20fd7b44e675
author: stevestein
ms.author: sstein
ms.openlocfilehash: ffb8639a187f1e7e091e382031886659bd47d7d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87653980"
---
# <a name="specify-events-and-data-columns-for-a-trace-file-sql-server-profiler"></a><span data-ttu-id="e904b-102">указать столбцы событий и данных для файла трассировки (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="e904b-102">Specify Events and Data Columns for a Trace File (SQL Server Profiler)</span></span>
  <span data-ttu-id="e904b-103">Данный раздел содержит информацию об указании классов событий и столбцов данных для трассировок при помощи [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e904b-103">This topic describes how to specify event classes and data columns for traces by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-specify-events-and-data-columns-for-a-trace"></a><span data-ttu-id="e904b-104">Указание событий и столбцов данных для трассировки</span><span class="sxs-lookup"><span data-stu-id="e904b-104">To specify events and data columns for a trace</span></span>  
  
1.  <span data-ttu-id="e904b-105">В диалоговом окне **Свойства трассировки** или **Свойства шаблона трассировки** выберите вкладку **Выбор событий** .</span><span class="sxs-lookup"><span data-stu-id="e904b-105">On the **Trace Properties** or **Trace Template Properties** dialog box, click the **Events Selection** tab.</span></span>  
  
     <span data-ttu-id="e904b-106">Вкладка **Выбор событий** содержит сетку.</span><span class="sxs-lookup"><span data-stu-id="e904b-106">The **Events Selection** tab contains a grid control.</span></span> <span data-ttu-id="e904b-107">Сетка — это таблица, которая содержит каждый из классов событий, доступных для трассировки.</span><span class="sxs-lookup"><span data-stu-id="e904b-107">The grid control is a table that contains each of the traceable event classes.</span></span> <span data-ttu-id="e904b-108">На каждый класс событий в таблице приходится по одной строке.</span><span class="sxs-lookup"><span data-stu-id="e904b-108">The table contains one row for each event class.</span></span> <span data-ttu-id="e904b-109">Классы событий могут незначительно различаться в зависимости от типа и версии сервера, к которому они подключены.</span><span class="sxs-lookup"><span data-stu-id="e904b-109">The event classes can differ slightly depending on the type and version of server to which you are connected.</span></span> <span data-ttu-id="e904b-110">Классы событий идентифицируются в столбце **События**сетки и группируются по категориям событий.</span><span class="sxs-lookup"><span data-stu-id="e904b-110">The event classes are identified in the **Events**column of the grid and are grouped by event category.</span></span> <span data-ttu-id="e904b-111">В оставшихся столбцах перечислены столбцы данных, которые могут быть возвращены для каждого класса событий.</span><span class="sxs-lookup"><span data-stu-id="e904b-111">The remaining columns list the data columns that can be returned for each event class.</span></span>  
  
2.  <span data-ttu-id="e904b-112">В диалоговом окне **Выбор событий**.</span><span class="sxs-lookup"><span data-stu-id="e904b-112">On the **Events Selection**tab, use the grid control to add or remove events and data columns from the trace file.</span></span>  
  
3.  <span data-ttu-id="e904b-113">Чтобы переместить события из трассировки, снимите флажок в столбце **События** для каждого класса событий.</span><span class="sxs-lookup"><span data-stu-id="e904b-113">To remove events from the trace, clear the check box in the **Events** column for each event class.</span></span>  
  
4.  <span data-ttu-id="e904b-114">Чтобы включить события в трассировку, установите флажок в столбце **События** для каждого класса событий или проверьте столбец данных, который соответствует событию.</span><span class="sxs-lookup"><span data-stu-id="e904b-114">To include events in a trace, check the box in the **Events** column for each event class, or check a data column that corresponds to an event.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e904b-115">Если трассировка будет коррелировать с данными системного монитора или монитора производительности, то столбцы данных **Время начала** и **Время окончания** должны быть включены в трассировку.</span><span class="sxs-lookup"><span data-stu-id="e904b-115">If the trace is going be correlated with System Monitor or Performance Monitor data, both **Start Time** and **End Time** data columns must be included in the trace.</span></span>  
  
 <span data-ttu-id="e904b-116">Если произведена проверка окна, соответствующего событию, то при внесении класса событий каждый связанный столбец данных также включается в трассировку.</span><span class="sxs-lookup"><span data-stu-id="e904b-116">When you include an event class, every associated data column is also included to the trace, if you have checked the box corresponding to an event.</span></span> <span data-ttu-id="e904b-117">Если проверялось окно для определенного столбца, то в трассировку включается только этот столбец.</span><span class="sxs-lookup"><span data-stu-id="e904b-117">If you checked the box for a particular column, only that column is included in the trace.</span></span>  
  
1.  <span data-ttu-id="e904b-118">Чтобы удалить столбцы данных из класса событий, снимите флажки со столбца данных в строке класса событий либо щелкните правой кнопкой мыши заголовок столбца и выберите **Снять выделение столбца** .</span><span class="sxs-lookup"><span data-stu-id="e904b-118">To remove data columns from an event class, clear the check boxes from the data column in the event class row, or right-click on the column header and select the **Deselect column** option.</span></span>  
  
2.  <span data-ttu-id="e904b-119">При необходимости примените фильтры к трассировке.</span><span class="sxs-lookup"><span data-stu-id="e904b-119">Optionally, apply filters to the trace.</span></span> <span data-ttu-id="e904b-120">Дополнительные сведения см. в статье [Создание трассировки(приложение SQL Server Profiler)](filter-events-in-a-trace-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="e904b-120">For more information, see [Filter Events in a Trace &#40;SQL Server Profiler&#41;](filter-events-in-a-trace-sql-server-profiler.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e904b-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="e904b-121">See Also</span></span>  
 [<span data-ttu-id="e904b-122">Приложение SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="e904b-122">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
