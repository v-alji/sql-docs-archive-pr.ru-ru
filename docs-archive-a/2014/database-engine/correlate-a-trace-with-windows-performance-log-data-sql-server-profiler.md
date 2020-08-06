---
title: Сопоставить трассировку с данными журнала производительности Windows (SQL Server Profiler) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], logs
ms.assetid: e1b3072c-8daf-49a7-9895-c8cccd2adb95
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 34575cf4270d817ecfbb5b2d1824831cc99454fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664481"
---
# <a name="correlate-a-trace-with-windows-performance-log-data-sql-server-profiler"></a><span data-ttu-id="a0d48-102">согласовать трассировку с данными журнала производительности Windows (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="a0d48-102">Correlate a Trace with Windows Performance Log Data (SQL Server Profiler)</span></span>
  [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)]<span data-ttu-id="a0d48-103">может сопоставлять счетчики системного монитора Microsoft Windows с [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] событиями или.</span><span class="sxs-lookup"><span data-stu-id="a0d48-103">can correlate Microsoft Windows System Monitor counters with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] or [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] events.</span></span> <span data-ttu-id="a0d48-104">Системный монитор Windows регистрирует системную активность указанных счетчиков журнала производительности.</span><span class="sxs-lookup"><span data-stu-id="a0d48-104">Windows System Monitor logs system activity for specified counters in performance logs.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a0d48-105">Дополнительные сведения об общем доступе к журналам между различными версиями Windows приведены в конце данного подраздела.</span><span class="sxs-lookup"><span data-stu-id="a0d48-105">For information about sharing logs among different versions of Windows, see the procedure at the end of this topic.</span></span>  
  
### <a name="to-correlate-a-trace-with-performance-log-data"></a><span data-ttu-id="a0d48-106">Согласование трассировки с данными журнала производительности</span><span class="sxs-lookup"><span data-stu-id="a0d48-106">To correlate a trace with performance log data</span></span>  
  
1.  <span data-ttu-id="a0d48-107">В [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)]откройте сохраненный файл трассировки или таблицу трассировки.</span><span class="sxs-lookup"><span data-stu-id="a0d48-107">In [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)], open a saved trace file or trace table.</span></span> <span data-ttu-id="a0d48-108">Нельзя согласовывать запущенную трассировку, которая производит сбор данных события.</span><span class="sxs-lookup"><span data-stu-id="a0d48-108">You cannot correlate a running trace that is still collecting event data.</span></span> <span data-ttu-id="a0d48-109">Чтобы гарантировать точность связывания с данными системного монитора, трассировка должна содержать столбцы данных **StartTime** и **EndTime** .</span><span class="sxs-lookup"><span data-stu-id="a0d48-109">For accurate correlation with System Monitor data, the trace must contain both **StartTime** and **EndTime** data columns.</span></span>  
  
2.  <span data-ttu-id="a0d48-110">В меню  **Файл** в [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] выберите **Импорт данных производительности**.</span><span class="sxs-lookup"><span data-stu-id="a0d48-110">On the [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] **File** menu, click **Import Performance Data**.</span></span>  
  
3.  <span data-ttu-id="a0d48-111">В диалоговом окне **Открыть** выберите файл с журналом производительности.</span><span class="sxs-lookup"><span data-stu-id="a0d48-111">In the **Open** dialog box, select a file that contains a performance log.</span></span> <span data-ttu-id="a0d48-112">Чтобы данные журнала производительности можно было связать с трассировкой, они должны быть собраны в то же время, что и данные трассировки.</span><span class="sxs-lookup"><span data-stu-id="a0d48-112">The performance log data must have been captured during the same time period in which the trace data is captured.</span></span>  
  
4.  <span data-ttu-id="a0d48-113">В диалоговом окне **Ограничение счетчиков производительности** установите флажки, относящиеся к объектам и счетчикам системного монитора, которые необходимо отобразить наряду с трассировкой.</span><span class="sxs-lookup"><span data-stu-id="a0d48-113">In the **Performance Counters Limit** dialog box, select the check boxes that correspond to the System Monitor objects and counters that you want to display alongside the trace.</span></span> <span data-ttu-id="a0d48-114">Нажмите кнопку **ОК.**</span><span class="sxs-lookup"><span data-stu-id="a0d48-114">Click **OK.**</span></span>  
  
5.  <span data-ttu-id="a0d48-115">Выберите событие в окне событий трассировки или используйте клавиши со стрелками, чтобы перемещаться по строкам в окне событий трассировки.</span><span class="sxs-lookup"><span data-stu-id="a0d48-115">Select an event in the trace events window, or navigate through several adjacent rows in the trace events window by using the arrow keys.</span></span> <span data-ttu-id="a0d48-116">Красная вертикальная черта в окне **Данные системного монитора** указывает на данные журнала производительности, связанные с выбранным событием трассировки.</span><span class="sxs-lookup"><span data-stu-id="a0d48-116">The vertical red bar in the **System Monitor data** window indicates the performance log data that is correlated with the selected trace event.</span></span>  
  
6.  <span data-ttu-id="a0d48-117">Выберите интересующую точку на графике системного монитора.</span><span class="sxs-lookup"><span data-stu-id="a0d48-117">Click a point of interest in the System Monitor graph.</span></span> <span data-ttu-id="a0d48-118">Выбирается соответствующая трассировка строки, ближайшая по времени к выбранной точке.</span><span class="sxs-lookup"><span data-stu-id="a0d48-118">The corresponding trace row that is nearest in time is selected.</span></span> <span data-ttu-id="a0d48-119">Чтобы увеличить временной диапазон, удерживая клавишу мыши, перетащите ее указатель по графику системного монитора.</span><span class="sxs-lookup"><span data-stu-id="a0d48-119">To zoom in on a time range, press and drag the mouse pointer in the System Monitor graph.</span></span>  
  
### <a name="to-create-performance-logs-that-can-be-shared-among-different-versions-of-windows"></a><span data-ttu-id="a0d48-120">Создание журналов производительности, общих для различных версий Windows</span><span class="sxs-lookup"><span data-stu-id="a0d48-120">To create performance logs that can be shared among different versions of Windows</span></span>  
  
1.  <span data-ttu-id="a0d48-121">На панели управления выберите пункт **Администрирование**, а затем дважды щелкните элемент **Производительность**.</span><span class="sxs-lookup"><span data-stu-id="a0d48-121">In Control Panel, open **Administrative Tools**, and then double click **Performance**.</span></span>  
  
2.  <span data-ttu-id="a0d48-122">В диалоговом окне **Производительность** разверните **Оповещения и журналы производительности**, щелкните правой кнопкой мыши **Журналы счетчиков**и выберите **Новые параметры журнала**.</span><span class="sxs-lookup"><span data-stu-id="a0d48-122">In the **Performance** dialog box, expand **Performance Logs and Alerts**, right-click **Counter Logs**, and then click **New Log Settings**.</span></span>  
  
3.  <span data-ttu-id="a0d48-123">Введите имя журнала счетчиков и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a0d48-123">Type a name for the counter log, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="a0d48-124">На вкладке **Общие** щелкните **Добавить счетчики**.</span><span class="sxs-lookup"><span data-stu-id="a0d48-124">On the **General** tab, click **Add Counters**.</span></span>  
  
5.  <span data-ttu-id="a0d48-125">В списке **Объект производительности** выберите объект, который требуется контролировать.</span><span class="sxs-lookup"><span data-stu-id="a0d48-125">In the **Performance object** list, select a performance object you want to monitor.</span></span> <span data-ttu-id="a0d48-126">Названия объектов производительности [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] для экземпляров по умолчанию [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] начинаются с [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , а именованные экземпляры начинаются с MSSQL$*instanceName*.</span><span class="sxs-lookup"><span data-stu-id="a0d48-126">The names of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] performance objects for default instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] start with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] and named instances start with MSSQL$*instanceName*.</span></span>  
  
6.  <span data-ttu-id="a0d48-127">Добавьте к экземпляру [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] необходимое количество счетчиков и прочие важные значения, такие как процессорное время и время диска.</span><span class="sxs-lookup"><span data-stu-id="a0d48-127">Add as many counters as necessary for your [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance and other important values, such as processor time and disk time.</span></span>  
  
7.  <span data-ttu-id="a0d48-128">После завершения добавления счетчиков нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="a0d48-128">When you have finished adding counters, click **Close**.</span></span>  
  
8.  <span data-ttu-id="a0d48-129">Установите значения для интервала **Снимать показания каждые** .</span><span class="sxs-lookup"><span data-stu-id="a0d48-129">Set values for the **Sample data every** interval.</span></span> <span data-ttu-id="a0d48-130">Начинайте с интервала в 5 минут, и затем корректируйте его по необходимости.</span><span class="sxs-lookup"><span data-stu-id="a0d48-130">Start with a modest sampling interval, such as 5 minutes, and then adjust the interval if necessary.</span></span>  
  
9. <span data-ttu-id="a0d48-131">На вкладке **Файлы журналов** выберите **Текстовый файл (разделители-запятые)** в списке **Тип файла журнала** .</span><span class="sxs-lookup"><span data-stu-id="a0d48-131">On the **Log Files** tab, choose **TextFile (Comma delimited)** from the **Log file type** list.</span></span> <span data-ttu-id="a0d48-132">Текстовые файлы журнала с разделителями-запятыми подходят для различных версий Windows; кроме того, их можно просматривать при помощи таких средств, как Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="a0d48-132">Comma-delimited text log files can be shared among different versions of Windows and can be viewed later in reporting tools such as Microsoft Excel.</span></span>  
  
10. <span data-ttu-id="a0d48-133">На вкладке **Расписание** укажите расписание контроля.</span><span class="sxs-lookup"><span data-stu-id="a0d48-133">On the **Schedule** tab, specify a monitoring schedule.</span></span>  
  
11. <span data-ttu-id="a0d48-134">Нажмите кнопку **ОК** для создания журнала производительности.</span><span class="sxs-lookup"><span data-stu-id="a0d48-134">Click **OK** to create the performance log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0d48-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="a0d48-135">See Also</span></span>  
 <span data-ttu-id="a0d48-136">[Шаблоны и разрешения приложения SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="a0d48-136">[SQL Server Profiler Templates and Permissions](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="a0d48-137">Запуск приложения SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="a0d48-137">Start SQL Server Profiler</span></span>](../tools/sql-server-profiler/start-sql-server-profiler.md)  
  
  
