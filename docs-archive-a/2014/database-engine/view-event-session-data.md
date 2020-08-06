---
title: Просмотр данных сеанса событий | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: ac742a01-2a95-42c7-b65e-ad565020dc49
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: eaeb5fd22b95b8f1056b8dce9e3c7d683b52602f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750103"
---
# <a name="view-event-session-data"></a><span data-ttu-id="9b734-102">Просмотр данных о сеансе событий</span><span class="sxs-lookup"><span data-stu-id="9b734-102">View Event Session Data</span></span>
  <span data-ttu-id="9b734-103">В этом разделе описывается использование пользовательского интерфейса для просмотра и анализа данных расширенных событий.</span><span class="sxs-lookup"><span data-stu-id="9b734-103">This topic describes using the display user interface to see and analyze extended event data:</span></span>  
  
-   <span data-ttu-id="9b734-104">Просмотр целевых данных</span><span class="sxs-lookup"><span data-stu-id="9b734-104">View Target Data</span></span>  
  
-   <span data-ttu-id="9b734-105">Работа с данными</span><span class="sxs-lookup"><span data-stu-id="9b734-105">Working With Data</span></span>  
  
## <a name="view-target-data"></a><span data-ttu-id="9b734-106">Просмотр целевых данных</span><span class="sxs-lookup"><span data-stu-id="9b734-106">View Target Data</span></span>  
 <span data-ttu-id="9b734-107">Собранные данные можно отобразить в указанном целевом объекте в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9b734-107">You can display the data collected into the specified target within [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
### <a name="view-target-data"></a><span data-ttu-id="9b734-108">Просмотр целевых данных</span><span class="sxs-lookup"><span data-stu-id="9b734-108">View Target Data</span></span>  
 <span data-ttu-id="9b734-109">Для просмотра целевых данных выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="9b734-109">To view target data:</span></span>  
  
1.  <span data-ttu-id="9b734-110">В обозревателе объектов разверните узлы **Управление**, **Расширенные события**и **Сеансы**, а затем разверните сеанс.</span><span class="sxs-lookup"><span data-stu-id="9b734-110">In Object Explorer, expand **Management**, **Extended Events**, **Sessions**, and then a session.</span></span>  
  
2.  <span data-ttu-id="9b734-111">Щелкните правой кнопкой мыши целевое имя, затем выберите **Просмотр целевых данных** , чтобы отобразить целевые данные.</span><span class="sxs-lookup"><span data-stu-id="9b734-111">Right-click the target name, and then click **View Target Data** to display the target data.</span></span>  
  
     <span data-ttu-id="9b734-112">В представлении по умолчанию отобразится окно целевых данных с целевыми данными.</span><span class="sxs-lookup"><span data-stu-id="9b734-112">The target data window appears in default view and displays the target data.</span></span>  
  
 <span data-ttu-id="9b734-113">Примечания по просмотру целевых данных.</span><span class="sxs-lookup"><span data-stu-id="9b734-113">Notes on viewing target data:</span></span>  
  
-   <span data-ttu-id="9b734-114">Целевые данные недоступны для цели трассировки событий Windows.</span><span class="sxs-lookup"><span data-stu-id="9b734-114">Target data is not available for the ETW target.</span></span>  
  
-   <span data-ttu-id="9b734-115">Чтобы просматривать данные ring_buffer в формате XML, выберите в окне целевых данных ссылку **целевые данные ring_buffer** .</span><span class="sxs-lookup"><span data-stu-id="9b734-115">To view the ring_buffer data in xml format, in the target data window click the **ring_buffer target data** link.</span></span> <span data-ttu-id="9b734-116">Файл ring_buffer.xml откроется в редакторе XML.</span><span class="sxs-lookup"><span data-stu-id="9b734-116">The ring_buffer.xml file appears in the xml editor.</span></span>  
  
-   <span data-ttu-id="9b734-117">Для целевого объекта event_file XEL-файл с данными можно просматривать одним из следующих методов.</span><span class="sxs-lookup"><span data-stu-id="9b734-117">For an event_file target, view the file target data (.XEL file) using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="9b734-118">Используйте файловый > открыть в [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9b734-118">Use File -> Open in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>
    
    -   <span data-ttu-id="9b734-119">Перетащите файл в [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9b734-119">Drag and drop the file into [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> 
    
    -   <span data-ttu-id="9b734-120">Дважды щелкнуть XEL-файл.</span><span class="sxs-lookup"><span data-stu-id="9b734-120">Double click the .XEL file.</span></span>  
    
    -   <span data-ttu-id="9b734-121">В среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]щелкните правой кнопкой мыши работающий сеанс расширенных событий и выберите пункт «Просмотр целевых данных».</span><span class="sxs-lookup"><span data-stu-id="9b734-121">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], right click on a running Extended Events session and select View Target Data.</span></span> 
    
    -   <span data-ttu-id="9b734-122">[fn_xe_file_target_read_file](/sql/relational-databases/system-functions/sys-fn-xe-file-target-read-file-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9b734-122">[fn_xe_file_target_read_file](/sql/relational-databases/system-functions/sys-fn-xe-file-target-read-file-transact-sql).</span></span>
    
    -   <span data-ttu-id="9b734-123">Используйте PowerShell Read-Склксевент в [модуле SQLServer. XEvent](https://www.powershellgallery.com/packages/SqlServer.XEvent).</span><span class="sxs-lookup"><span data-stu-id="9b734-123">Use Powershell Read-SQLXevent in [SQLServer.XEvent module](https://www.powershellgallery.com/packages/SqlServer.XEvent).</span></span>
    
    -   <span data-ttu-id="9b734-124">Программное использование XEvents с помощью [Кселите NuGet](https://www.nuget.org/packages/Microsoft.SqlServer.XEvent.XELite).</span><span class="sxs-lookup"><span data-stu-id="9b734-124">Programmatically consume XEvents by using the [XELite NuGet](https://www.nuget.org/packages/Microsoft.SqlServer.XEvent.XELite).</span></span>
    
    -   <span data-ttu-id="9b734-125">Можно просмотреть более одного. XEL-файл, выбрав команду **объединить файлы расширенных событий** в меню файл-> открыть.</span><span class="sxs-lookup"><span data-stu-id="9b734-125">You can view more than one .XEL file by selecting **Merge Extended Event Files** from the File -> Open menu.</span></span>

### <a name="watching-live-data"></a><span data-ttu-id="9b734-126">Просмотр данных, передаваемых в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="9b734-126">Watching Live Data</span></span>  
 <span data-ttu-id="9b734-127">Можно просматривать данные, передаваемые в режиме реального времени, в ходе их записи.</span><span class="sxs-lookup"><span data-stu-id="9b734-127">You can watch live data as it is being captured.</span></span>  
  
-   <span data-ttu-id="9b734-128">В обозревателе объектов разверните узлы **Управление**, **Расширенные события**и **сеансы** .</span><span class="sxs-lookup"><span data-stu-id="9b734-128">In Object Explorer, expand the **Management**, **Extended Events**, and then **Sessions** nodes.</span></span>  

-   <span data-ttu-id="9b734-129">Щелкните правой кнопкой мыши имя сеанса, а затем выберите пункт **Просмотр данных, передаваемых в режиме реального времени** для начала отображения данных трассировки.</span><span class="sxs-lookup"><span data-stu-id="9b734-129">Right-click the session name and then click **Watch Live Data** to start displaying the tracing data.</span></span>  
  
     <span data-ttu-id="9b734-130">По умолчанию отображаются столбцы **Имя события** и **Отметка времени**.</span><span class="sxs-lookup"><span data-stu-id="9b734-130">The default display columns are **Event Name** and **TimeStamp**.</span></span>  
  
     <span data-ttu-id="9b734-131">Для добавления дополнительных столбцов к окну трассировки нажмите кнопку **Выбрать столбцы** на панели инструментов «Расширенные события».</span><span class="sxs-lookup"><span data-stu-id="9b734-131">To add additional columns to the trace window, click the **Choose Columns** button on the Extended Events toolbar.</span></span> <span data-ttu-id="9b734-132">На вкладке **Сведения** отображаются все сведения о событии для выбранного события.</span><span class="sxs-lookup"><span data-stu-id="9b734-132">The **Details** tab shows all of the event details for the selected event.</span></span>  
  
     <span data-ttu-id="9b734-133">Обычно события отображаются приблизительно через 30 секунд.</span><span class="sxs-lookup"><span data-stu-id="9b734-133">Events are usually displayed in approximately 30 seconds.</span></span> <span data-ttu-id="9b734-134">Если требуется изменить период задержки, то можно изменить параметр **Максимальная задержка диспетчера** на странице **Расширенные** в диалоговом окне **Новый сеанс** .</span><span class="sxs-lookup"><span data-stu-id="9b734-134">If you want to change the latency period, you can change the **Maximum dispatch latency** on the **Advanced** page of the of the **New Session** dialog.</span></span>  
     
-    <span data-ttu-id="9b734-135">Данные в реальном времени могут передаваться [модулем PowerShell SQLServer. XEvent](https://www.powershellgallery.com/packages/SqlServer.XEvent).</span><span class="sxs-lookup"><span data-stu-id="9b734-135">Live data can be streamed by the [SqlServer.XEvent PowerShell module](https://www.powershellgallery.com/packages/SqlServer.XEvent).</span></span>
     
### <a name="to-refresh-target-data"></a><span data-ttu-id="9b734-136">Обновление целевых данных</span><span class="sxs-lookup"><span data-stu-id="9b734-136">To Refresh Target Data</span></span>  
 <span data-ttu-id="9b734-137">Обновление целевых данных не поддерживается для объектов event_files.</span><span class="sxs-lookup"><span data-stu-id="9b734-137">Refreshing target data is not supported for event_files targets:</span></span>  
  
1.  <span data-ttu-id="9b734-138">Чтобы целевые данные обновлялись автоматически, щелкните их правой кнопкой мыши, выберите **Интервал обновления**, затем выберите нужный интервал из списка.</span><span class="sxs-lookup"><span data-stu-id="9b734-138">To refresh the target data automatically, right click the target data, select **Refresh Interval**, and then select the refresh interval from the interval list.</span></span>  
  
2.  <span data-ttu-id="9b734-139">Чтобы приостановить и возобновить автоматическое обновление, щелкните правой кнопкой мыши целевые данные и выберите **Пауза** или **Возобновить**.</span><span class="sxs-lookup"><span data-stu-id="9b734-139">To pause and resume the automatic refresh, right-click the target data and then select **Pause** or **Resume**.</span></span>  
  
3.  <span data-ttu-id="9b734-140">Чтобы обновить целевые данные вручную, щелкните их правой кнопкой мыши и выберите **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="9b734-140">To refresh the target data manually, right click the target data, and then select **Refresh**.</span></span>  
  
## <a name="working-with-data"></a><span data-ttu-id="9b734-141">Работа с данными</span><span class="sxs-lookup"><span data-stu-id="9b734-141">Working With Data</span></span>  
 <span data-ttu-id="9b734-142">Возможности анализа, доступные в пользовательском интерфейсе расширенных событий, позволяют выявлять проблемы.</span><span class="sxs-lookup"><span data-stu-id="9b734-142">You can use the analysis capabilities of the Extended Events user interface to identify problems.</span></span>  
  
### <a name="details-pane"></a><span data-ttu-id="9b734-143">Панель сведений</span><span class="sxs-lookup"><span data-stu-id="9b734-143">Details Pane</span></span>  
 <span data-ttu-id="9b734-144">В области **Сведения** показаны все столбцы для выбранного события, включая поля и действия.</span><span class="sxs-lookup"><span data-stu-id="9b734-144">The **Details** pane shows all the columns for the selected event, including fields and actions.</span></span> <span data-ttu-id="9b734-145">Чтобы добавить столбец в таблицу целевых данных, щелкните правой кнопкой мыши строку в области **Сведения** и выберите пункт **Показать столбец в таблице**.</span><span class="sxs-lookup"><span data-stu-id="9b734-145">You can add a column to the target data table by right-clicking a row in the **Details** pane and selecting **Show Column in Table**.</span></span>  
  
### <a name="create-modify-or-delete-merged-columns"></a><span data-ttu-id="9b734-146">Создание, изменение и удаление объединенных столбцов</span><span class="sxs-lookup"><span data-stu-id="9b734-146">Create, Modify, or Delete Merged Columns</span></span>  
 <span data-ttu-id="9b734-147">Объединенный столбец позволяет объединить набор полей и отображать их в одном столбце.</span><span class="sxs-lookup"><span data-stu-id="9b734-147">A merged column allows you to combine a set of fields to be displayed in a single column.</span></span> <span data-ttu-id="9b734-148">В объединенном столбце данные показываются, начиная с первого поля со значением, отличным от NULL, в порядке добавления в список полей.</span><span class="sxs-lookup"><span data-stu-id="9b734-148">The merged column will show the data from the first non-NULL field based on the order they are added to the field list.</span></span> <span data-ttu-id="9b734-149">Это аналогично представлению в приложении [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Profiler, где данные в некотором столбце могут отображаться по-разному в зависимости от события (наиболее распространенным примером служит поле TextData в приложении [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Profiler).</span><span class="sxs-lookup"><span data-stu-id="9b734-149">This is similar to what you see in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Profiler, where a specific column may show different data depending on the event (the most common example of this is the TextData field in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Profiler).</span></span> <span data-ttu-id="9b734-150">Например, можно объединить поля statement и batch_text из событий sql_statement_completed и sql_batch_completed в поле с именем myStatement.</span><span class="sxs-lookup"><span data-stu-id="9b734-150">For an example, you could merge the statement and batch_text fields from the sql_statement_completed and sql_batch_completed events, respectively, into a field named myStatement.</span></span> <span data-ttu-id="9b734-151">В столбце myStatement, отображаемом в таблице, будут показаны данные, соответствующие связанному событию.</span><span class="sxs-lookup"><span data-stu-id="9b734-151">When you display the myStatement column in the table it will show the appropriate data for the associated event.</span></span>  
  
 <span data-ttu-id="9b734-152">Объединенные столбцы можно создавать, изменять и удалять.</span><span class="sxs-lookup"><span data-stu-id="9b734-152">You can create, modify, or delete merged columns:</span></span>  
  
1.  <span data-ttu-id="9b734-153">Откройте XEL-файл для просмотра результатов трассировки.</span><span class="sxs-lookup"><span data-stu-id="9b734-153">Open a .XEL file to view the trace results.</span></span> <span data-ttu-id="9b734-154">(Также можно щелкнуть правой кнопкой мыши имя сеанса и выбрать пункт **Показать данные, передаваемые в режиме реального времени**.)</span><span class="sxs-lookup"><span data-stu-id="9b734-154">(You can also right click the session name, and then select **Watch Live Data**.)</span></span>  
  
2.  <span data-ttu-id="9b734-155">В окне результатов трассировки щелкните правой кнопкой мыши заголовок столбца и выберите команду **Выбрать столбцы**.</span><span class="sxs-lookup"><span data-stu-id="9b734-155">In the trace results window, right-click the column header, and then click **Choose Columns**.</span></span>  
  
 <span data-ttu-id="9b734-156">Чтобы создать объединенный столбец, нажмите кнопку **Создать** в диалоговом окне **Выбор столбцов** .</span><span class="sxs-lookup"><span data-stu-id="9b734-156">To create a merged column, click **New** in the **Choose Columns** dialog box.</span></span>  <span data-ttu-id="9b734-157">В диалоговом окне **Новый объединенный столбец** задайте имя для столбца и выберите исходные столбцы для включения в объединенный столбец.</span><span class="sxs-lookup"><span data-stu-id="9b734-157">In the **New Merged Column** dialog, name the merged column and select the original columns to be included in the merged column.</span></span>  
  
 <span data-ttu-id="9b734-158">Чтобы изменить объединенный столбец, выберите его в диалоговом окне **Выбор столбцов** и нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="9b734-158">To edit a merged column, select a merged column in the **Choose Columns** dialog and click **Edit**.</span></span> <span data-ttu-id="9b734-159">В диалоговом окне **Изменение объединенного столбца** измените имя столбца или измените исходные столбцы для включения в объединенный столбец.</span><span class="sxs-lookup"><span data-stu-id="9b734-159">In the **Edit Merged Column** dialog, rename the merged column or modify the original columns to be included in the merged column.</span></span>  
  
 <span data-ttu-id="9b734-160">Чтобы удалить объединенный столбец, выберите его в диалоговом окне **Выбор столбцов** и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="9b734-160">To delete a merged column, select a merged column in the **Choose Columns** dialog and click **Delete**.</span></span>  
  
### <a name="filter-results"></a><span data-ttu-id="9b734-161">Фильтрация результатов</span><span class="sxs-lookup"><span data-stu-id="9b734-161">Filter Results</span></span>  
 <span data-ttu-id="9b734-162">Можно просмотреть результаты трассировки и применить фильтры, чтобы уменьшить объем результатов, отображаемых в окне трассировки.</span><span class="sxs-lookup"><span data-stu-id="9b734-162">You can view trace results, and then apply filters to narrow down the trace results that are displayed in the trace window.</span></span> <span data-ttu-id="9b734-163">Фильтр отображения включает в себя фильтр времени и расширенный фильтр.</span><span class="sxs-lookup"><span data-stu-id="9b734-163">The display filter includes a time filter and an advanced filter.</span></span> <span data-ttu-id="9b734-164">Для фильтрации результатов трассировки по отметкам времени событий используется фильтр времени, а для создания условий фильтра с использованием полей события и действий — дополнительный фильтр.</span><span class="sxs-lookup"><span data-stu-id="9b734-164">You use the time filter to filter the trace results by event timestamp, and you use the advanced filter to construct filter conditions using the event fields and actions.</span></span> <span data-ttu-id="9b734-165">Между фильтрами времени и дополнительными фильтрами определено отношение И.</span><span class="sxs-lookup"><span data-stu-id="9b734-165">There is an "and" relationship between the time and advanced filters.</span></span>  
  
 <span data-ttu-id="9b734-166">Чтобы создать фильтр, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="9b734-166">To create a filter:</span></span>  
  
1.  <span data-ttu-id="9b734-167">Откройте XEL-файл для просмотра результатов трассировки.</span><span class="sxs-lookup"><span data-stu-id="9b734-167">Open a .XEL file to view the trace results.</span></span> <span data-ttu-id="9b734-168">(Также можно щелкнуть правой кнопкой мыши имя сеанса и выбрать пункт **Показать данные, передаваемые в режиме реального времени**.)</span><span class="sxs-lookup"><span data-stu-id="9b734-168">(You can also right click the session name, and then select **Watch Live Data**.)</span></span>  
  
2.  <span data-ttu-id="9b734-169">В окне результатов трассировки выберите результаты, которые необходимо отфильтровать, а затем на панели инструментов **Расширенные события** нажмите кнопку **Фильтры**.</span><span class="sxs-lookup"><span data-stu-id="9b734-169">In the trace results window, select the results you want to filter, and then on the **Extended Events** toolbar, click **Filters**.</span></span>  
  
3.  <span data-ttu-id="9b734-170">В диалоговом окне **Фильтры** выберите команду **Задать фильтр времени** , чтобы установить фильтр времени, перетаскивая ползунки или изменяя время в поле ввода.</span><span class="sxs-lookup"><span data-stu-id="9b734-170">In the **Filters** dialog box, select **Set time filter** to set the time filter by dragging the slider bars or modifying the time in the edit box.</span></span>  
  
4.  <span data-ttu-id="9b734-171">В разделе **Дополнительные фильтры** примените требуемые условия фильтра и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="9b734-171">In the **Additional filters** section, apply your filter criteria, and then click **Apply**.</span></span>  
  
### <a name="sort-results"></a><span data-ttu-id="9b734-172">Сортировка результатов</span><span class="sxs-lookup"><span data-stu-id="9b734-172">Sort Results</span></span>  
 <span data-ttu-id="9b734-173">Сортировка результатов по возрастанию или убыванию</span><span class="sxs-lookup"><span data-stu-id="9b734-173">To sort results either in ascending or descending order:</span></span>  
  
1.  <span data-ttu-id="9b734-174">Откройте XEL-файл для просмотра результатов трассировки.</span><span class="sxs-lookup"><span data-stu-id="9b734-174">Open a .XEL file to view the trace results.</span></span> <span data-ttu-id="9b734-175">(Также можно щелкнуть правой кнопкой мыши имя сеанса, выбрать пункт **Просмотр данных, передаваемых в режиме реального времени**, а затем нажать кнопку **Остановить поток данных** на панели инструментов.)</span><span class="sxs-lookup"><span data-stu-id="9b734-175">(You can also right click the session name, select **Watch Live Data**, and then click the **Stop Data Feed** button on the toolbar.)</span></span>  
  
2.  <span data-ttu-id="9b734-176">В окне с результатами трассировки щелкните правой кнопкой мыши заголовок столбца, который нужно отсортировать, и выберите пункт **Сортировка по возрастанию** или **Сортировка по убыванию**.</span><span class="sxs-lookup"><span data-stu-id="9b734-176">In the trace results window, right-click the column heading you want to sort and click **Sort Ascending** or **Sort Descending**.</span></span>  
  
 <span data-ttu-id="9b734-177">Можно также щелкнуть любой заголовок столбца, чтобы изменить порядок сортировки.</span><span class="sxs-lookup"><span data-stu-id="9b734-177">You can also click the column header to reverse the sort order.</span></span>  
  
 <span data-ttu-id="9b734-178">Если имеются сгруппированные столбцы, то сортировка столбца приводит лишь к сортировке данных в пределах группы.</span><span class="sxs-lookup"><span data-stu-id="9b734-178">If you have grouped columns, sorting the column will only sort data within the group.</span></span>  
  
### <a name="group-results"></a><span data-ttu-id="9b734-179">Группирование результатов</span><span class="sxs-lookup"><span data-stu-id="9b734-179">Group Results</span></span>  
 <span data-ttu-id="9b734-180">Возможности группировки результатов эквивалентны функциям предложения `GROUP BY` в [!INCLUDE[tsql](../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9b734-180">Grouped results are equivalent to the functionality of the `GROUP BY` clause in [!INCLUDE[tsql](../includes/tsql-md.md)].</span></span> <span data-ttu-id="9b734-181">В таблице целевых данных данные будут сгруппированы с возможностью разворачивания и сворачивания.</span><span class="sxs-lookup"><span data-stu-id="9b734-181">The target data table will show the data grouped together, allowing you to expand and collapse the data.</span></span>  
  
 <span data-ttu-id="9b734-182">Перед агрегатной обработкой данные необходимо сгруппировать.</span><span class="sxs-lookup"><span data-stu-id="9b734-182">You must group data before you can aggregate it.</span></span> <span data-ttu-id="9b734-183">Например, можно выполнить группирование по значению query_hash, отсортировать по убыванию продолжительности, получить среднюю продолжительность для каждой группы, а затем отсортировать по убыванию агрегатного значения.</span><span class="sxs-lookup"><span data-stu-id="9b734-183">For example, you can group on the query_hash value, sort descending by duration, get the average duration for each group, and then sort descending on the aggregation.</span></span>  <span data-ttu-id="9b734-184">В результате получится список уникальных инструкций, идущих от самой большой до самой маленькой средней продолжительности.</span><span class="sxs-lookup"><span data-stu-id="9b734-184">This will produce a list that shows the list of unique statements from longest to shortest average duration.</span></span> <span data-ttu-id="9b734-185">После развертывания верхней группы отображаются отдельные выполнения заданного запроса, отсортированные от самого длительного к самому короткому.</span><span class="sxs-lookup"><span data-stu-id="9b734-185">When you expand the top group you will see the individual executions of that specific query sorted from longest to shortest.</span></span>  
  
 <span data-ttu-id="9b734-186">Результаты можно группировать по одному или по нескольким столбцам.</span><span class="sxs-lookup"><span data-stu-id="9b734-186">You can group results by a single column or by multiple columns.</span></span>  
  
 <span data-ttu-id="9b734-187">Откройте XEL-файл для просмотра результатов трассировки.</span><span class="sxs-lookup"><span data-stu-id="9b734-187">Open a .XEL file to view the trace results.</span></span> <span data-ttu-id="9b734-188">(Также можно щелкнуть правой кнопкой мыши имя сеанса, выбрать пункт **Просмотр данных, передаваемых в режиме реального времени**, а затем нажать кнопку **Остановить поток данных** на панели инструментов.)</span><span class="sxs-lookup"><span data-stu-id="9b734-188">(You can also right click the session name, select **Watch Live Data**, and then click the **Stop Data Feed** button on the toolbar.)</span></span>  
  
 <span data-ttu-id="9b734-189">Чтобы сгруппировать результаты по одному столбцу, щелкните правой кнопкой мыши заголовок столбца в окне результатов трассировки и выберите пункт **Группировать по этому столбцу**.</span><span class="sxs-lookup"><span data-stu-id="9b734-189">To group results by a single column, right-click the column heading in the trace results window, and click **Group by this Column**.</span></span> <span data-ttu-id="9b734-190">Чтобы отменить группирование, выберите одну из строк и нажмите кнопку **Отменить все группирование**.</span><span class="sxs-lookup"><span data-stu-id="9b734-190">To undo the grouping, select one of the rows and click **Remove All Groupings**.</span></span>  
  
 <span data-ttu-id="9b734-191">Чтобы сгруппировать результаты по нескольким столбцам, нажмите кнопку **Группирование** на панели инструментов **Расширенные события** .</span><span class="sxs-lookup"><span data-stu-id="9b734-191">To group results by a multiple columns, click the **Grouping** button on the **Extended Events** toolbar.</span></span> <span data-ttu-id="9b734-192">В поле **Доступные столбцы** диалогового окна **Группирование** выберите столбцы, которые нужно сгруппировать, и переместите их в поле **Столбцы, сгруппированные по** .</span><span class="sxs-lookup"><span data-stu-id="9b734-192">In the **Available columns** box of the **Grouping** dialog, select the columns you want to group, and move them into the **Columns grouped on** box.</span></span> <span data-ttu-id="9b734-193">Чтобы изменить порядок группирования в поле **Столбцы, сгруппированные по** , используйте кнопки со стрелками вверх и вниз.</span><span class="sxs-lookup"><span data-stu-id="9b734-193">To change the order in the **Columns grouped on** box, click the up or down arrows.</span></span>  
  
### <a name="aggregate-results"></a><span data-ttu-id="9b734-194">Агрегатная обработка результатов</span><span class="sxs-lookup"><span data-stu-id="9b734-194">Aggregate Results</span></span>  
 <span data-ttu-id="9b734-195">Можно просматривать результаты трассировки, а затем подвергать дополнительному анализу данные события, применяя статистическую обработку к столбцам в результатах.</span><span class="sxs-lookup"><span data-stu-id="9b734-195">You can view the trace results, and then further analyze your event data by aggregating columns in your results.</span></span> <span data-ttu-id="9b734-196">Расширенные события поддерживают пять агрегатных функций:</span><span class="sxs-lookup"><span data-stu-id="9b734-196">Extended Events supports five aggregation functions:</span></span>  
  
-   <span data-ttu-id="9b734-197">Sum</span><span class="sxs-lookup"><span data-stu-id="9b734-197">sum</span></span>  
  
-   <span data-ttu-id="9b734-198">Min</span><span class="sxs-lookup"><span data-stu-id="9b734-198">min</span></span>  
  
-   <span data-ttu-id="9b734-199">max</span><span class="sxs-lookup"><span data-stu-id="9b734-199">max</span></span>  
  
-   <span data-ttu-id="9b734-200">average</span><span class="sxs-lookup"><span data-stu-id="9b734-200">average</span></span>  
  
-   <span data-ttu-id="9b734-201">count (счетчик)</span><span class="sxs-lookup"><span data-stu-id="9b734-201">count</span></span>  
  
 <span data-ttu-id="9b734-202">Функции sum, min, max и average можно использовать только для числовых столбцов.</span><span class="sxs-lookup"><span data-stu-id="9b734-202">Sum, min, max, and average can only be used with numeric columns.</span></span> <span data-ttu-id="9b734-203">Count — это количество не равных NULL значений, имеющихся в выбранном столбце в группе.</span><span class="sxs-lookup"><span data-stu-id="9b734-203">Count is the number of non-null values that exist for the selected column in the group.</span></span>  
  
 <span data-ttu-id="9b734-204">Агрегатная обработка применяется к группе, поэтому перед ней необходимо сгруппировать результаты.</span><span class="sxs-lookup"><span data-stu-id="9b734-204">Aggregation is performed on a group, so you must group the results before you can perform the aggregation.</span></span> <span data-ttu-id="9b734-205">Агрегатная обработка результатов</span><span class="sxs-lookup"><span data-stu-id="9b734-205">To aggregate results:</span></span>  
  
1.  <span data-ttu-id="9b734-206">Откройте XEL-файл для просмотра результатов трассировки.</span><span class="sxs-lookup"><span data-stu-id="9b734-206">Open a .XEL file to view the trace results.</span></span> <span data-ttu-id="9b734-207">(Также можно щелкнуть правой кнопкой мыши имя сеанса, выбрать пункт **Просмотр данных, передаваемых в режиме реального времени**, а затем нажать кнопку **Остановить поток данных** на панели инструментов.)</span><span class="sxs-lookup"><span data-stu-id="9b734-207">(You can also right click the session name, select **Watch Live Data**, and then click the **Stop Data Feed** button on the toolbar.)</span></span>  
  
2.  <span data-ttu-id="9b734-208">На панели инструментов **Расширенные события** нажмите кнопку **Статистическая обработка** .</span><span class="sxs-lookup"><span data-stu-id="9b734-208">On the **Extended Events** toolbar, click the **Aggregation** button.</span></span> <span data-ttu-id="9b734-209">В диалоговом окне «Статистическая обработка» появятся столбцы, доступные для агрегатной обработки.</span><span class="sxs-lookup"><span data-stu-id="9b734-209">The Aggregation dialog box will display the columns available for aggregation.</span></span>  
  
3.  <span data-ttu-id="9b734-210">В столбце **Тип статистической обработки** выберите тип обработки.</span><span class="sxs-lookup"><span data-stu-id="9b734-210">In the **Aggregation Type** column, select the aggregation type.</span></span>  
  
4.  <span data-ttu-id="9b734-211">В поле **Сортировать результаты статистической обработки по** выберите столбец для сортировки.</span><span class="sxs-lookup"><span data-stu-id="9b734-211">In the **Sort aggregation by** box, select the sort column.</span></span> <span data-ttu-id="9b734-212">Затем выберите порядок: по возрастанию или по убыванию.</span><span class="sxs-lookup"><span data-stu-id="9b734-212">Then select ascending or descending order.</span></span>  
  
### <a name="search-for-text-in-columns"></a><span data-ttu-id="9b734-213">Поиск текста в столбцах</span><span class="sxs-lookup"><span data-stu-id="9b734-213">Search for Text in Columns</span></span>  
 <span data-ttu-id="9b734-214">В столбцах можно искать текст.</span><span class="sxs-lookup"><span data-stu-id="9b734-214">You can search for text in columns:</span></span>  
  
1.  <span data-ttu-id="9b734-215">Откройте XEL-файл для просмотра результатов трассировки.</span><span class="sxs-lookup"><span data-stu-id="9b734-215">Open a .XEL file to view the trace results.</span></span> <span data-ttu-id="9b734-216">(Также можно щелкнуть правой кнопкой мыши имя сеанса и выбрать пункт **Показать данные, передаваемые в режиме реального времени**.)</span><span class="sxs-lookup"><span data-stu-id="9b734-216">(You can also right click the session name, select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="9b734-217">Нажмите кнопку **Найти** на панели инструментов **Расширенные события** .</span><span class="sxs-lookup"><span data-stu-id="9b734-217">Click **Find** on the **Extended Events** toolbar.</span></span>  
  
3.  <span data-ttu-id="9b734-218">В поле **Найти** диалогового окна **Найти в расширенных событиях** введите текст для поиска.</span><span class="sxs-lookup"><span data-stu-id="9b734-218">In the **Find what** box of the **Find in Extended Events** dialog box, enter the search text.</span></span> <span data-ttu-id="9b734-219">В раскрывающемся списке можно выбрать одну из 20 последних строк поиска.</span><span class="sxs-lookup"><span data-stu-id="9b734-219">You can select one of your last 20 search strings from the drop-down list.</span></span>  
  
4.  <span data-ttu-id="9b734-220">В поле **Искать в** выберите расположение для поиска указанного текста.</span><span class="sxs-lookup"><span data-stu-id="9b734-220">In the **Look in** box, select the location to search for the specified text.</span></span> <span data-ttu-id="9b734-221">Можно использовать следующие параметры для поиска:</span><span class="sxs-lookup"><span data-stu-id="9b734-221">Use the following options for searching:</span></span>  
  
    -   <span data-ttu-id="9b734-222">Столбцы таблицы.</span><span class="sxs-lookup"><span data-stu-id="9b734-222">Table Columns.</span></span> <span data-ttu-id="9b734-223">Этот параметр служит для поиска всех видимых столбцов в окне трассировки.</span><span class="sxs-lookup"><span data-stu-id="9b734-223">Use this option to search all visible columns in the trace window.</span></span>  
  
    -   <span data-ttu-id="9b734-224">Сведения.</span><span class="sxs-lookup"><span data-stu-id="9b734-224">Details.</span></span> <span data-ttu-id="9b734-225">Этот параметр используется для поиска в окне трассировки всех столбцов (повышенных и неповышенных), которые были выбраны перед открытием диалогового окна **найти в расширенных событиях** .</span><span class="sxs-lookup"><span data-stu-id="9b734-225">Use this option to search all columns (promoted and non-promoted) in the trace window that were selected before opening the **Find in Extended Events** dialog box.</span></span>  
  
    -   <span data-ttu-id="9b734-226">*Event_column_name*.</span><span class="sxs-lookup"><span data-stu-id="9b734-226">*Event_column_name*.</span></span> <span data-ttu-id="9b734-227">Этот параметр служит для поиска в столбце определенного события из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="9b734-227">Use this option to search in a specific event column from the drop-down list.</span></span>  
  
5.  <span data-ttu-id="9b734-228">Чтобы указать, как должен быть определен поиск, можно также задать следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="9b734-228">Use the following options to specify how you want to define the search:</span></span>  
  
    -   <span data-ttu-id="9b734-229">Учитывать регистр.</span><span class="sxs-lookup"><span data-stu-id="9b734-229">Match case.</span></span> <span data-ttu-id="9b734-230">Этот параметр используется для отображения результатов поиска текста, введенного в поле Найти, которые согласуются с ним и по содержанию, и по регистру.</span><span class="sxs-lookup"><span data-stu-id="9b734-230">Use this option to display the search results for the text you entered in the Find what box that are matched both by content and by case.</span></span>  
  
    -   <span data-ttu-id="9b734-231">Слово целиком.</span><span class="sxs-lookup"><span data-stu-id="9b734-231">Match whole word.</span></span> <span data-ttu-id="9b734-232">Этот параметр служит для отображения результатов поиска введенного текста, которые согласуются с полными словами.</span><span class="sxs-lookup"><span data-stu-id="9b734-232">Use this option to display only the search results for the text you entered that match complete words.</span></span>  
  
    -   <span data-ttu-id="9b734-233">Поиск назад.</span><span class="sxs-lookup"><span data-stu-id="9b734-233">Search up.</span></span> <span data-ttu-id="9b734-234">Этот параметр используется для поиска от местоположения курсора к началу результатов.</span><span class="sxs-lookup"><span data-stu-id="9b734-234">Use this option to search from your cursor location to the beginning of the results.</span></span>  
  
    -   <span data-ttu-id="9b734-235">Назначение.</span><span class="sxs-lookup"><span data-stu-id="9b734-235">Use.</span></span> <span data-ttu-id="9b734-236">Этот параметр указывает, каким образом следует интерпретировать специальные символы и регулярные выражения, введенные в поле Найти.</span><span class="sxs-lookup"><span data-stu-id="9b734-236">Use this option to interpret the special characters and the regular expressions you entered in the Find what box.</span></span> <span data-ttu-id="9b734-237">Специальные символы — это символы-шаблоны (\*) и (?), представляющие один или нескольких символов.</span><span class="sxs-lookup"><span data-stu-id="9b734-237">Special characters include the wildcard characters (\*) and (?) to represent one or more characters.</span></span> <span data-ttu-id="9b734-238">Регулярные выражения представляют собой специальные обозначения, используемые для определения искомого текста с помощью шаблонов.</span><span class="sxs-lookup"><span data-stu-id="9b734-238">Regular expressions are special notations used to define patterns of search text.</span></span>  
  
    -   <span data-ttu-id="9b734-239">Щелкните **Найти далее** , чтобы найти следующее вхождение текста, введенного в поле **Найти** .</span><span class="sxs-lookup"><span data-stu-id="9b734-239">Click **Find Next** to search for the next text that you entered in the **Find what** box.</span></span>  
  
### <a name="bookmarks"></a><span data-ttu-id="9b734-240">Закладки</span><span class="sxs-lookup"><span data-stu-id="9b734-240">Bookmarks</span></span>  
 <span data-ttu-id="9b734-241">Чтобы упростить возврат к строке, можно создать закладку для одной или нескольких строк в целевых данных.</span><span class="sxs-lookup"><span data-stu-id="9b734-241">To make it easier to return to a row, you can bookmark one or more row(s) in the target data.</span></span> <span data-ttu-id="9b734-242">Чтобы изменить закладку, щелкните строку правой кнопкой мыши.</span><span class="sxs-lookup"><span data-stu-id="9b734-242">Right click on a row to change the bookmark.</span></span> <span data-ttu-id="9b734-243">Для перехода к строкам с закладками используйте кнопки «Назад» и «Далее» на панели инструментов **Расширенные события** .</span><span class="sxs-lookup"><span data-stu-id="9b734-243">Use the previous and next buttons on the **Extended Events** toolbar to navigate to bookmarked rows.</span></span>  
  
### <a name="change-display-settings"></a><span data-ttu-id="9b734-244">Изменение параметров отображения</span><span class="sxs-lookup"><span data-stu-id="9b734-244">Change Display Settings</span></span>  
 <span data-ttu-id="9b734-245">Можно сохранить сведения о столбцах (порядок столбцов, объединенный столбец и ширина столбца) и отфильтрованные результаты трассировки в файле параметров представления «Расширенные события» (VIEWSETTING-файл).</span><span class="sxs-lookup"><span data-stu-id="9b734-245">You can save column information (column order, merge column, and column width) and filter information of a trace result into an Extended Events display setting file (.viewsetting file).</span></span> <span data-ttu-id="9b734-246">После сохранения файла можно его использовать для трассировки результатов и изменения представления.</span><span class="sxs-lookup"><span data-stu-id="9b734-246">After saving the file, you can apply it to your trace results to change the view.</span></span>  
  
 <span data-ttu-id="9b734-247">Изменение параметров отображения</span><span class="sxs-lookup"><span data-stu-id="9b734-247">To change the display settings:</span></span>  
  
1.  <span data-ttu-id="9b734-248">Откройте XEL-файл для просмотра результатов трассировки.</span><span class="sxs-lookup"><span data-stu-id="9b734-248">Open a .XEL file to view the trace results.</span></span> <span data-ttu-id="9b734-249">(Также можно щелкнуть правой кнопкой мыши имя сеанса и выбрать пункт **Показать данные, передаваемые в режиме реального времени**.)</span><span class="sxs-lookup"><span data-stu-id="9b734-249">(You can also right click the session name, select **Watch Live Data**.</span></span>  
  
2.  <span data-ttu-id="9b734-250">На панели инструментов **Расширенные события** нажмите кнопку **Параметры отображения**.</span><span class="sxs-lookup"><span data-stu-id="9b734-250">On the **Extended Events** toolbar, select **Display Settings**.</span></span> <span data-ttu-id="9b734-251">Выберите один из следующих параметров из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="9b734-251">From the drop-down list, select one of the following options:</span></span>  
  
    -   <span data-ttu-id="9b734-252">Сохранить как.</span><span class="sxs-lookup"><span data-stu-id="9b734-252">Save as.</span></span> <span data-ttu-id="9b734-253">Сохраните столбцы и сведения о результатах трассировки в файле .viewsetting.</span><span class="sxs-lookup"><span data-stu-id="9b734-253">Save the columns and filter information of a trace result to a .viewsetting file.</span></span>  
  
    -   <span data-ttu-id="9b734-254">Открытие.</span><span class="sxs-lookup"><span data-stu-id="9b734-254">Open.</span></span> <span data-ttu-id="9b734-255">Открыть существующий VIEWSETTING-файл.</span><span class="sxs-lookup"><span data-stu-id="9b734-255">Open an existing .viewsetting file.</span></span>  
  
    -   <span data-ttu-id="9b734-256">Открыть последний.</span><span class="sxs-lookup"><span data-stu-id="9b734-256">Open recent.</span></span> <span data-ttu-id="9b734-257">Открыть недавно сохраненный VIEWSETTING-файл.</span><span class="sxs-lookup"><span data-stu-id="9b734-257">Open a recently saved .viewsetting file.</span></span>  
  
### <a name="copy-or-export-trace-results"></a><span data-ttu-id="9b734-258">Копирование или экспорт результатов трассировки</span><span class="sxs-lookup"><span data-stu-id="9b734-258">Copy or Export Trace Results</span></span>  
 <span data-ttu-id="9b734-259">Можно копировать ячейки, строки и подробные сведения в выбранные строки из результатов трассировки.</span><span class="sxs-lookup"><span data-stu-id="9b734-259">You can copy cells, rows, and details to selected rows from your trace results.</span></span> <span data-ttu-id="9b734-260">Кроме того, можно экспортировать результаты трассировки следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9b734-260">You can also export your trace results to the following:</span></span>  
  
-   <span data-ttu-id="9b734-261">в XEL-файл</span><span class="sxs-lookup"><span data-stu-id="9b734-261">.XEL file</span></span>  
  
-   <span data-ttu-id="9b734-262">table</span><span class="sxs-lookup"><span data-stu-id="9b734-262">table</span></span>  
  
-   <span data-ttu-id="9b734-263">в CSV-файл</span><span class="sxs-lookup"><span data-stu-id="9b734-263">.CSV file</span></span>  
  
 <span data-ttu-id="9b734-264">Чтобы скопировать результаты трассировки, выделите ячейку, строку или строки, щелкните правой кнопкой мыши, выберите команду **Копировать** , а затем выберите пункт **Ячейка**, **Строка**или **Сведения**.</span><span class="sxs-lookup"><span data-stu-id="9b734-264">To copy trace results, select a cell, row, or rows, right click, select **Copy** and then **Cell**, **Row**, or **Details**.</span></span> <span data-ttu-id="9b734-265">Расширенные события поддерживают копирование максимум 1000 строк.</span><span class="sxs-lookup"><span data-stu-id="9b734-265">Extended Events supports copying up to a maximum of 1000 rows.</span></span>  
  
 <span data-ttu-id="9b734-266">Результаты трассировки можно экспортировать в XEL-файл, в таблицу или в CSV-файл, выбрав команду **Экспорт** в меню **Расширенные события** среды [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9b734-266">You can export trace results to a .XEL file, table, or .CSV file by selecting **Export to** from the **Extended Events** menu option in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
### <a name="view-a-deadlock-graph-and-query-plans"></a><span data-ttu-id="9b734-267">Просмотр графика взаимоблокировок и планов запроса</span><span class="sxs-lookup"><span data-stu-id="9b734-267">View a Deadlock Graph and Query Plans</span></span>  
 <span data-ttu-id="9b734-268">Для устранения неполадок с взаимоблокировками можно просматривать график взаимоблокировки для **xml_deadlock_report** на панели «Сведения».</span><span class="sxs-lookup"><span data-stu-id="9b734-268">You can view the deadlock graph for **xml_deadlock_report** in the Details pane to help you troubleshoot deadlocks.</span></span> <span data-ttu-id="9b734-269">Можно также просматривать графики плана запросов для следующих событий:</span><span class="sxs-lookup"><span data-stu-id="9b734-269">You can also view query plan graphs for the following events:</span></span>  
  
-   <span data-ttu-id="9b734-270">query_post_compilation_showplan</span><span class="sxs-lookup"><span data-stu-id="9b734-270">query_post_compilation_showplan</span></span>  
  
-   <span data-ttu-id="9b734-271">query_pre_execution_showplan</span><span class="sxs-lookup"><span data-stu-id="9b734-271">query_pre_execution_showplan</span></span>  
  
-   <span data-ttu-id="9b734-272">query_post_execution_showplan</span><span class="sxs-lookup"><span data-stu-id="9b734-272">query_post_execution_showplan</span></span>  
  
 <span data-ttu-id="9b734-273">Просмотр графика взаимоблокировок</span><span class="sxs-lookup"><span data-stu-id="9b734-273">To view the deadlock graph:</span></span>  
  
-   <span data-ttu-id="9b734-274">В обозревателе объектов разверните узлы **Управление**, **Расширенные события**и **сеансы** .</span><span class="sxs-lookup"><span data-stu-id="9b734-274">In Object Explorer, expand the **Management**, **Extended Events**, and then **Sessions** nodes.</span></span>  
  
-   <span data-ttu-id="9b734-275">Щелкните правой кнопкой мыши сеанс, содержащий настроенное событие взаимоблокировки, которые необходимо просматривать, а затем выберите пункт **Просмотр данных, передаваемых в режиме реального времени**.</span><span class="sxs-lookup"><span data-stu-id="9b734-275">Right-click the session that contains the configured deadlock event that you want to view, and select **Watch Live Data**.</span></span>  
  
-   <span data-ttu-id="9b734-276">Выберите событие взаимоблокировки и просмотрите график на вкладке **Взаимоблокировка** в области сведений.</span><span class="sxs-lookup"><span data-stu-id="9b734-276">Select the deadlock event and view the graph on the **Deadlock** tab in the Details pane.</span></span>  
  
 <span data-ttu-id="9b734-277">Просмотр графиков плана запроса</span><span class="sxs-lookup"><span data-stu-id="9b734-277">To view query plan graphs:</span></span>  
  
1.  <span data-ttu-id="9b734-278">В обозревателе объектов разверните узлы **Управление**, **Расширенные события**и **сеансы** .</span><span class="sxs-lookup"><span data-stu-id="9b734-278">In Object Explorer, expand the **Management**, **Extended Events**, and then **Sessions** nodes.</span></span>  
  
2.  <span data-ttu-id="9b734-279">Щелкните правой кнопкой мыши сеанс, содержащий график плана запроса, который необходимо просматривать (например, query_post_compilation_showplan), а затем выберите пункт **Просмотр данных, передаваемых в режиме реального времени**.</span><span class="sxs-lookup"><span data-stu-id="9b734-279">Right-click the session that contains the query plan graph that you want to view (for example, query_post_compilation_showplan), and then select **Watch Live Data**.</span></span>  
  
3.  <span data-ttu-id="9b734-280">Выберите событие графика плана запроса (например, query_post_compilation_showplan) и просмотрите график на вкладке **План запроса** в области сведений.</span><span class="sxs-lookup"><span data-stu-id="9b734-280">Select the query plan graph event (for example, query_post_compilation_showplan) and view the graph on the **Query plan** tab in the Details pane.</span></span>  
  
  
