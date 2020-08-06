---
title: Справка F1 для средства просмотра журналов | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.configurelogs.errorlog.f1
helpviewer_keywords:
- Log File Viewer
ms.assetid: 2243845c-4880-4aa0-9ee8-0a97a128996b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c6eadb4baa4a47202b40a9cde1eca896022f31d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658254"
---
# <a name="log-file-viewer-f1-help"></a><span data-ttu-id="df1c1-102">Справка средства просмотра журнала F1</span><span class="sxs-lookup"><span data-stu-id="df1c1-102">Log File Viewer F1 Help</span></span>
  <span data-ttu-id="df1c1-103">Средство просмотра журнала позволяет просматривать многие журналы различных компонентов.</span><span class="sxs-lookup"><span data-stu-id="df1c1-103">Log File Viewer displays log information from many different components.</span></span> <span data-ttu-id="df1c1-104">Когда средство просмотра журнала открыто, нужный журнал можно выбрать при помощи панели **Выбор журналов** .</span><span class="sxs-lookup"><span data-stu-id="df1c1-104">When Log File Viewer is open, use the **Select logs** pane to select the logs you want to display.</span></span> <span data-ttu-id="df1c1-105">В каждом журнале отображаются столбцы, соответствующие типу журнала.</span><span class="sxs-lookup"><span data-stu-id="df1c1-105">Each log displays columns appropriate to that kind of log.</span></span>  
  
 <span data-ttu-id="df1c1-106">Список доступных журналов зависит от того, каким способом было открыто средство просмотра журнала.</span><span class="sxs-lookup"><span data-stu-id="df1c1-106">The logs that are available depend on how Log File Viewer is opened.</span></span> <span data-ttu-id="df1c1-107">Дополнительные сведения см. в статье [Открытие средства просмотра файла журнала](open-log-file-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="df1c1-107">For more information, see [Open Log File Viewer](open-log-file-viewer.md).</span></span>  
  
 <span data-ttu-id="df1c1-108">Число строк, отображаемых в журналах аудита, можно настроить на странице **Обозреватель объектов SQL Server/Команды** диалогового окна **Сервис/Параметры** .</span><span class="sxs-lookup"><span data-stu-id="df1c1-108">The number of rows that are displayed for audit logs can be configured on the **SQL Server Object Explorer/Commands** page of the **Tools/Options** dialog box.</span></span> <span data-ttu-id="df1c1-109">Описания столбцов, отображаемых в журналах аудита, см. в разделе [sys.fn_get_audit_file (Transact-SQL)](/sql/relational-databases/system-functions/sys-fn-get-audit-file-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="df1c1-109">For descriptions of the columns that are displayed for audit logs, see [sys.fn_get_audit_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-get-audit-file-transact-sql).</span></span>  
  
## <a name="options"></a><span data-ttu-id="df1c1-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="df1c1-110">Options</span></span>  
 <span data-ttu-id="df1c1-111">**Загрузить журнал**</span><span class="sxs-lookup"><span data-stu-id="df1c1-111">**Load Log**</span></span>  
 <span data-ttu-id="df1c1-112">Открывает диалоговое окно, в котором можно указать загружаемый файл журнала.</span><span class="sxs-lookup"><span data-stu-id="df1c1-112">Open a dialog box where you can specify a log file to load.</span></span>  
  
 <span data-ttu-id="df1c1-113">**Экспорт**</span><span class="sxs-lookup"><span data-stu-id="df1c1-113">**Export**</span></span>  
 <span data-ttu-id="df1c1-114">Открывает диалоговое окно, позволяющее экспортировать данные из сетки **Сведения о файле журнала** в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="df1c1-114">Open a dialog box that lets you export the information that is shown in the **Log file summary** grid to a text file.</span></span>  
  
 <span data-ttu-id="df1c1-115">**Обновить**</span><span class="sxs-lookup"><span data-stu-id="df1c1-115">**Refresh**</span></span>  
 <span data-ttu-id="df1c1-116">Позволяет обновить представление выбранных журналов.</span><span class="sxs-lookup"><span data-stu-id="df1c1-116">Refresh the view of the selected logs.</span></span> <span data-ttu-id="df1c1-117">При нажатии кнопки **Обновить** выбранные журналы заново считываются с целевого сервера с применением параметров фильтра.</span><span class="sxs-lookup"><span data-stu-id="df1c1-117">The **Refresh** button rereads the selected logs from the target server while applying any filter settings.</span></span>  
  
 <span data-ttu-id="df1c1-118">**Filter**</span><span class="sxs-lookup"><span data-stu-id="df1c1-118">**Filter**</span></span>  
 <span data-ttu-id="df1c1-119">Открывает диалоговое окно, позволяющее указывать параметры фильтрации файла журнала, например **Соединение**и **Дата**или другие **Общие** условия фильтра.</span><span class="sxs-lookup"><span data-stu-id="df1c1-119">Open a dialog box that lets you specify settings that are used to filter the log file, such as **Connection**, **Date**, or other **General** filter criteria.</span></span>  
  
 <span data-ttu-id="df1c1-120">**Поиск**</span><span class="sxs-lookup"><span data-stu-id="df1c1-120">**Search**</span></span>  
 <span data-ttu-id="df1c1-121">Позволяет найти определенный текст в файле журнала.</span><span class="sxs-lookup"><span data-stu-id="df1c1-121">Search the log file for specific text.</span></span> <span data-ttu-id="df1c1-122">Поиск с символами-шаблонами не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="df1c1-122">Searching with wildcard characters is not supported.</span></span>  
  
 <span data-ttu-id="df1c1-123">**Остановить**</span><span class="sxs-lookup"><span data-stu-id="df1c1-123">**Stop**</span></span>  
 <span data-ttu-id="df1c1-124">Прекращает загрузку записей файла журнала.</span><span class="sxs-lookup"><span data-stu-id="df1c1-124">Stops loading the log file entries.</span></span> <span data-ttu-id="df1c1-125">Например, можно использовать этот параметр, если загрузка удаленного файла или файла журнала вне сети занимает длительное время, а нужно просмотреть лишь наиболее свежие записи.</span><span class="sxs-lookup"><span data-stu-id="df1c1-125">For example, you can use this option if a remote or offline log file takes a long time to load, and you only want to view the most recent entries.</span></span>  
  
 <span data-ttu-id="df1c1-126">**Сведения о файле журнала**</span><span class="sxs-lookup"><span data-stu-id="df1c1-126">**Log file summary**</span></span>  
 <span data-ttu-id="df1c1-127">Эта информационная панель содержит сводку данных по фильтрации файла журнала.</span><span class="sxs-lookup"><span data-stu-id="df1c1-127">This information panel displays a summary of the log file filtering.</span></span> <span data-ttu-id="df1c1-128">Если файл не фильтруется, на панели отображается текст **без фильтров**.</span><span class="sxs-lookup"><span data-stu-id="df1c1-128">If the file is not filtered, you will see the following text, **No filter applied**.</span></span> <span data-ttu-id="df1c1-129">Если фильтр применяется к журналу, отображается следующий текст: **Критерий отбора:** \<filter criteria>.</span><span class="sxs-lookup"><span data-stu-id="df1c1-129">If a filter is applied to the log, you will see the following text, **Filter log entries where:** \<filter criteria>.</span></span>  
  
 <span data-ttu-id="df1c1-130">**Сведения о выбранной строке**</span><span class="sxs-lookup"><span data-stu-id="df1c1-130">**Selected row details**</span></span>  
 <span data-ttu-id="df1c1-131">Выберите строку для отображения дополнительных сведений о выбранной строке события внизу страницы.</span><span class="sxs-lookup"><span data-stu-id="df1c1-131">Select a row to display additional details about the selected event row at the bottom of the page.</span></span> <span data-ttu-id="df1c1-132">Порядок столбцов можно менять, перетаскивая их в нужное место сетки.</span><span class="sxs-lookup"><span data-stu-id="df1c1-132">The columns can be reordered by dragging them to new locations in the grid.</span></span> <span data-ttu-id="df1c1-133">Размер столбцов можно менять, перетаскивая разделители столбцов в заголовке сетки вправо или влево.</span><span class="sxs-lookup"><span data-stu-id="df1c1-133">The columns can be resized by dragging the column separator bars in the grid header to the left or right.</span></span> <span data-ttu-id="df1c1-134">Если дважды щелкнуть разделитель столбцов в заголовке сетки, ширина столбца будет автоматически подогнана под его содержимое.</span><span class="sxs-lookup"><span data-stu-id="df1c1-134">Double-click the column separator bars in the grid header to automatically size the column to the content width.</span></span>  
  
 <span data-ttu-id="df1c1-135">**Экземпляр**</span><span class="sxs-lookup"><span data-stu-id="df1c1-135">**Instance**</span></span>  
 <span data-ttu-id="df1c1-136">Имя экземпляра, к которому относится происшедшее событие.</span><span class="sxs-lookup"><span data-stu-id="df1c1-136">The name of the instance on which the event occurred.</span></span> <span data-ttu-id="df1c1-137">Отображается как *имя_компьютера*\\*имя_экземпляра*.</span><span class="sxs-lookup"><span data-stu-id="df1c1-137">This is displayed as *computer name*\\*instance name*.</span></span>  
  
## <a name="frequently-displayed-columns"></a><span data-ttu-id="df1c1-138">Часто отображаемые столбцы</span><span class="sxs-lookup"><span data-stu-id="df1c1-138">Frequently Displayed Columns</span></span>  
 <span data-ttu-id="df1c1-139">**Дата**</span><span class="sxs-lookup"><span data-stu-id="df1c1-139">**Date**</span></span>  
 <span data-ttu-id="df1c1-140">Дата события.</span><span class="sxs-lookup"><span data-stu-id="df1c1-140">Displays the date of the event.</span></span>  
  
 <span data-ttu-id="df1c1-141">**Source**</span><span class="sxs-lookup"><span data-stu-id="df1c1-141">**Source**</span></span>  
 <span data-ttu-id="df1c1-142">Исходная функция, создавшая событие, например имя службы (MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="df1c1-142">Displays the source feature from which the event is created, such as the name of the service (MSSQLSERVER, for example).</span></span> <span data-ttu-id="df1c1-143">Отображается не для всех типов журнала.</span><span class="sxs-lookup"><span data-stu-id="df1c1-143">This does not appear for all log types.</span></span>  
  
 <span data-ttu-id="df1c1-144">**Сообщение**</span><span class="sxs-lookup"><span data-stu-id="df1c1-144">**Message**</span></span>  
 <span data-ttu-id="df1c1-145">Сообщение, связанное с событием.</span><span class="sxs-lookup"><span data-stu-id="df1c1-145">Displays any messages associated with the event.</span></span>  
  
 <span data-ttu-id="df1c1-146">**Log Type**</span><span class="sxs-lookup"><span data-stu-id="df1c1-146">**Log Type**</span></span>  
 <span data-ttu-id="df1c1-147">Отображает тип журнала, которому принадлежит событие.</span><span class="sxs-lookup"><span data-stu-id="df1c1-147">Displays the type of log to which the event belongs.</span></span> <span data-ttu-id="df1c1-148">Все выбранные журналы отображаются в окне сводки файла журнала.</span><span class="sxs-lookup"><span data-stu-id="df1c1-148">All selected logs appear in the log file summary window.</span></span>  
  
 <span data-ttu-id="df1c1-149">**Log Source**</span><span class="sxs-lookup"><span data-stu-id="df1c1-149">**Log Source**</span></span>  
 <span data-ttu-id="df1c1-150">Отображает описание исходного журнала, в котором зарегистрировано событие.</span><span class="sxs-lookup"><span data-stu-id="df1c1-150">Displays a description of the source log in which the event is captured.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="df1c1-151">Разрешения</span><span class="sxs-lookup"><span data-stu-id="df1c1-151">Permissions</span></span>  
 <span data-ttu-id="df1c1-152">Чтобы получить доступ к файлам журнала для экземпляров [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , которые находятся в сети, требуется членство в предопределенной роли сервера securityadmin.</span><span class="sxs-lookup"><span data-stu-id="df1c1-152">To access log files for instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that are online, this requires membership in the securityadmin fixed server role.</span></span>  
  
 <span data-ttu-id="df1c1-153">Чтобы получить доступ к файлам журнала для экземпляров [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , которые находятся вне сети, необходим доступ на чтение к пространству WMI **Root\Microsoft\SqlServer\ComputerManagement10** , а также к папке, в которой хранятся файлы журнала.</span><span class="sxs-lookup"><span data-stu-id="df1c1-153">To access log files for instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that are offline, you must have read access to both the **Root\Microsoft\SqlServer\ComputerManagement10** WMI namespace, and to the folder where the log files are stored.</span></span> <span data-ttu-id="df1c1-154">Дополнительные сведения см. в подразделе "Безопасность" раздела [Просмотр автономных файлов журнала](view-offline-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="df1c1-154">For more information, see the Security section of the topic [View Offline Log Files](view-offline-log-files.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df1c1-155">См. также:</span><span class="sxs-lookup"><span data-stu-id="df1c1-155">See Also</span></span>  
 <span data-ttu-id="df1c1-156">[Средство просмотра файлов журнала](log-file-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="df1c1-156">[Log File Viewer](log-file-viewer.md) </span></span>  
 <span data-ttu-id="df1c1-157">[Открытие средства просмотра файла журнала](open-log-file-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="df1c1-157">[Open Log File Viewer](open-log-file-viewer.md) </span></span>  
 [<span data-ttu-id="df1c1-158">Просмотр автономных файлов журнала</span><span class="sxs-lookup"><span data-stu-id="df1c1-158">View Offline Log Files</span></span>](view-offline-log-files.md)  
  
  
