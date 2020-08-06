---
title: Управление сеансами событий в обозревателе объектов | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
ms.assetid: 16849e38-d3fb-414d-8dcb-797b5ffce6ee
author: rothja
ms.author: jroth
ms.openlocfilehash: 1aa33a97137f63348898e6b1fcb7b19b2d218573
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655177"
---
# <a name="manage-event-sessions-in-the-object-explorer"></a><span data-ttu-id="022d6-102">Управление сеансами событий в обозревателе объектов</span><span class="sxs-lookup"><span data-stu-id="022d6-102">Manage Event Sessions in the Object Explorer</span></span>
  <span data-ttu-id="022d6-103">В этом разделе описываются действия, которые можно выполнять в **обозревателе объектов** и которые отражаются на расширенных событиях.</span><span class="sxs-lookup"><span data-stu-id="022d6-103">This topic discusses the actions you can take in **Object Explorer** that affect Extended Events:</span></span>  
  
-   <span data-ttu-id="022d6-104">Создание сеанса расширенных событий</span><span class="sxs-lookup"><span data-stu-id="022d6-104">Create an Extended Events Session</span></span>  
  
-   <span data-ttu-id="022d6-105">Запуск или остановка сеанса расширенных событий</span><span class="sxs-lookup"><span data-stu-id="022d6-105">Starting or Stopping an Extended Events Session</span></span>  
  
-   <span data-ttu-id="022d6-106">Экспорт сеанса расширенных событий</span><span class="sxs-lookup"><span data-stu-id="022d6-106">Export an Extended Events Session</span></span>  
  
-   <span data-ttu-id="022d6-107">Импорт шаблона сеанса расширенных событий</span><span class="sxs-lookup"><span data-stu-id="022d6-107">Import an Extended Events Session Template</span></span>  
  
-   <span data-ttu-id="022d6-108">Изменение сеанса расширенных событий</span><span class="sxs-lookup"><span data-stu-id="022d6-108">Edit an Extended Events Session</span></span>  
  
-   <span data-ttu-id="022d6-109">Удаление сеанса расширенных событий</span><span class="sxs-lookup"><span data-stu-id="022d6-109">Delete an Extended Events Session</span></span>  
  
## <a name="create-an-extended-events-session"></a><span data-ttu-id="022d6-110">Создание сеанса расширенных событий</span><span class="sxs-lookup"><span data-stu-id="022d6-110">Create an Extended Events Session</span></span>  
 <span data-ttu-id="022d6-111">Дополнительные сведения о создании сеанса расширенных событий см. в разделе [Create an Extended Events Session](../../database-engine/create-an-extended-events-session.md).</span><span class="sxs-lookup"><span data-stu-id="022d6-111">For more information about creating an Extended Events session, see [Create an Extended Events Session](../../database-engine/create-an-extended-events-session.md).</span></span>  
  
## <a name="starting-or-stopping-an-extended-events-session"></a><span data-ttu-id="022d6-112">Запуск или остановка сеанса расширенных событий</span><span class="sxs-lookup"><span data-stu-id="022d6-112">Starting or Stopping an Extended Events Session</span></span>  
 <span data-ttu-id="022d6-113">Сеанс расширенных событий можно запустить или отключить в **редакторе запросов** с помощью `ALTER EVENT SESSION` инструкции или с помощью узла **Расширенные события** **обозревателя объектов**.</span><span class="sxs-lookup"><span data-stu-id="022d6-113">You can start or stop an Extended Events session through the **Query Editor** using the `ALTER EVENT SESSION` statement, or by using the **Extended Events** node of **Object Explorer**.</span></span>  
  
 <span data-ttu-id="022d6-114">При остановке сеанса событий сеанс больше не отображается как активный в динамическом административном представлении (DMV) sys.dm_xe_sessions.</span><span class="sxs-lookup"><span data-stu-id="022d6-114">When you stop an event session, the session is no longer listed as an active session in the sys.dm_xe_sessions dynamic management view (DMV).</span></span> <span data-ttu-id="022d6-115">Однако определение сеанса не меняется, поэтому сеанс можно перезапустить.</span><span class="sxs-lookup"><span data-stu-id="022d6-115">However, the session definition remains intact, and you can restart the session.</span></span> <span data-ttu-id="022d6-116">Чтобы полностью удалить определение сеанса, необходимо удалить сеанс.</span><span class="sxs-lookup"><span data-stu-id="022d6-116">To completely remove a session definition, you must delete the session.</span></span>  
  
 <span data-ttu-id="022d6-117">Для запуска или остановки сеанса расширенных событий требуется разрешение ALTER ANY EVENT SESSION.</span><span class="sxs-lookup"><span data-stu-id="022d6-117">To start or stop an Extended Events session, you must have the ALTER ANY EVENT SESSION permission.</span></span>  
  
 <span data-ttu-id="022d6-118">После остановки сеанса, использующего целевой объект в памяти (например, кольцевой буфер, сегментацию, пары событий или синхронный счетчик событий), все данные, которые хранятся в буфере сеанса (столбец target_data динамического административного представления sys.dm_xe_session_targets), будут потеряны.</span><span class="sxs-lookup"><span data-stu-id="022d6-118">When you stop a session that uses an in-memory target, such as the ring buffer, bucketing, event pairing, or synchronous event counter targets, all the information stored in the session's buffer (the target_data column of the sys.dm_xe_session_targets DMV) will be lost.</span></span> <span data-ttu-id="022d6-119">Чтобы получить доступ к данным события после остановки сеанса, необходимо сохранить данные перед остановкой сеанса или настроить сеанс на использование файла цели.</span><span class="sxs-lookup"><span data-stu-id="022d6-119">To access event data after you stop the session, you should either save the data before you stop the session, or configure the session to use the file target.</span></span>  
  
### <a name="start-or-stop-an-extended-events-session-using-query-editor"></a><span data-ttu-id="022d6-120">Запуск или остановка сеанса расширенных событий с помощью редактора запросов</span><span class="sxs-lookup"><span data-stu-id="022d6-120">Start or Stop an Extended Events Session Using Query Editor</span></span>  
 <span data-ttu-id="022d6-121">Для запуска сеанса выполните следующие инструкции, заменив *имя_сеанса* именем сеанса расширенных событий.</span><span class="sxs-lookup"><span data-stu-id="022d6-121">To start a session, issue the following statements, replacing *session_name* with the name of the Extended Events session:</span></span>  
  
```  
ALTER EVENT SESSION [session_name]  
ON SERVER  
STATE = START  
```  
  
 <span data-ttu-id="022d6-122">Для остановки сеанса выполните следующие инструкции, заменив *имя_сеанса* именем сеанса расширенных событий.</span><span class="sxs-lookup"><span data-stu-id="022d6-122">To stop a session, issue the following statements, replacing *session_name* with the name of the Extended Events session:</span></span>  
  
```  
ALTER EVENT SESSION [session_name]  
ON SERVER  
STATE = STOP  
```  
  
### <a name="start-or-stop-an-extended-events-session-in-object-explorer"></a><span data-ttu-id="022d6-123">Запуск или остановка сеанса расширенных событий в обозревателе объектов</span><span class="sxs-lookup"><span data-stu-id="022d6-123">Start or Stop an Extended Events Session in Object Explorer</span></span>  
 <span data-ttu-id="022d6-124">Чтобы запустить или остановить сеанс расширенных событий в **обозревателе объектов**, разверните узлы **Управление**, **Расширенные события**, **Сеансы** , затем щелкните правой кнопкой сеанс и выберите пункт **Начать сеанс** или **Остановить сеанс**.</span><span class="sxs-lookup"><span data-stu-id="022d6-124">To start or stop an Extended Events session in **Object Explorer**, expand the **Management**, **Extended Events**, and then **Sessions** nodes and right click on a session and then click **Start Session** or **Stop Session**.</span></span>  
  
## <a name="export-an-extended-events-session-template"></a><span data-ttu-id="022d6-125">Экспорт шаблона сеанса расширенных событий</span><span class="sxs-lookup"><span data-stu-id="022d6-125">Export an Extended Events Session Template</span></span>  
 <span data-ttu-id="022d6-126">Можно экспортировать сеанс расширенных событий с помощью **обозревателя объектов**, а затем сохранить его в XML-файле шаблона.</span><span class="sxs-lookup"><span data-stu-id="022d6-126">You can export an Extended Events session using **Object Explorer**, and save it as an .xml template file.</span></span> <span data-ttu-id="022d6-127">Например, можно экспортировать сеанс, а затем применить шаблон к новому сеансу событий с помощью **Мастера новых сеансов** или мастера **Создать сеанс** .</span><span class="sxs-lookup"><span data-stu-id="022d6-127">For example, you may want to export a session and then apply the template to a new event session using the **New Session Wizard** or the **New Session** wizard.</span></span>  
  
 <span data-ttu-id="022d6-128">При экспорте сеанса убедитесь, что файл шаблона сохраняется в расположении с файловой системой NTFS, для которого есть возможность ограничить доступ, предоставляя его только пользователям, имеющим право просмотра конфиденциальных данных.</span><span class="sxs-lookup"><span data-stu-id="022d6-128">When you export a session, make sure that you save the template file to a location that uses the NTFS file system, and that you restrict access to users who are authorized to view the information.</span></span>  
  
 <span data-ttu-id="022d6-129">Экспорт сеанса расширенных событий с помощью **обозревателя объектов**.</span><span class="sxs-lookup"><span data-stu-id="022d6-129">To export an Extended Events session in **Object Explorer**:</span></span>  
  
1.  <span data-ttu-id="022d6-130">Разверните узлы **Управление**, **Расширенные события**и **Сеансы**</span><span class="sxs-lookup"><span data-stu-id="022d6-130">Expand the **Management**, **Extended Events**, and then **Sessions** nodes</span></span>  
  
2.  <span data-ttu-id="022d6-131">Щелкните правой кнопкой мыши сеанс, который необходимо экспортировать, а затем выберите **Экспортировать сеанс**.</span><span class="sxs-lookup"><span data-stu-id="022d6-131">Right-click the session that you want to export, and select **Export Session**.</span></span>  
  
3.  <span data-ttu-id="022d6-132">В диалоговом окне **Сохранить как** выберите расположение для сохранения файла, введите имя файла в поле **Имя файла** и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="022d6-132">In the **Save As** dialog box, select a location to save the file, type the file name in the **File name** box, and then click **Save**.</span></span>  
  
     <span data-ttu-id="022d6-133">Если файл сохраняется в место сохранения шаблона [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] по умолчанию, шаблон отобразится в раскрывающемся списке стандартных шаблонов при использовании **Мастера новых сеансов** или диалогового окна **Создание сеанса** .</span><span class="sxs-lookup"><span data-stu-id="022d6-133">If you save the file to the default [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] template location, the template will appear in the dropdown list of predefined templates when you use the **New Session Wizard** and **New Session** dialog.</span></span>  
  
## <a name="import-an-extended-events-session-template"></a><span data-ttu-id="022d6-134">Импорт шаблона сеанса расширенных событий</span><span class="sxs-lookup"><span data-stu-id="022d6-134">Import an Extended Events Session Template</span></span>  
 <span data-ttu-id="022d6-135">С помощью **обозревателя объектов**вы можете импортировать шаблон для сеанса расширенных событий.</span><span class="sxs-lookup"><span data-stu-id="022d6-135">Using **Object Explorer**, you can import a template for an Extended Events session.</span></span> <span data-ttu-id="022d6-136">Например, это может потребоваться при создании сеанса из шаблона, который был экспортирован из другого экземпляра службы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="022d6-136">For example, you may want to do this to create a session from a template that was exported from another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="022d6-137">Чтобы импортировать сеанс расширенных событий, необходимы разрешения `ALTER ANY EVENT SESSION`.</span><span class="sxs-lookup"><span data-stu-id="022d6-137">To import an Extended Events session, you must have the necessary `ALTER ANY EVENT SESSION` permissions.</span></span>  
  
 <span data-ttu-id="022d6-138">Прежде чем импортировать файл шаблона, убедитесь, что файл получен из надежного источника.</span><span class="sxs-lookup"><span data-stu-id="022d6-138">Before you import a template file, make sure that the file is from a trusted source.</span></span> <span data-ttu-id="022d6-139">Файл шаблона должен быть сохранен в расположение с файловой системой NTFS, где есть возможность ограничить доступ, предоставляя его только пользователям, имеющим право просмотра конфиденциальных данных.</span><span class="sxs-lookup"><span data-stu-id="022d6-139">Template files should be saved to a location that uses the NTFS file system and where access is restricted to users who are authorized to view the information.</span></span>  
  
 <span data-ttu-id="022d6-140">Импорт сеанса расширенных событий</span><span class="sxs-lookup"><span data-stu-id="022d6-140">To import an Extended Events session:</span></span>  
  
1.  <span data-ttu-id="022d6-141">В **обозревателе объектов**разверните узел **Управление**, а затем узел **Расширенные события** .</span><span class="sxs-lookup"><span data-stu-id="022d6-141">In **Object Explorer**, expand the **Management**, and then **Extended Events** nodes.</span></span>  
  
2.  <span data-ttu-id="022d6-142">Щелкните правой кнопкой мыши элемент **Сеансы** и выберите **Создать сеанс**.</span><span class="sxs-lookup"><span data-stu-id="022d6-142">Right-click **Sessions** and select **New Session**.</span></span>  
  
3.  <span data-ttu-id="022d6-143">Укажите имя для этого сеанса.</span><span class="sxs-lookup"><span data-stu-id="022d6-143">Specify a name for the session.</span></span>  
  
4.  <span data-ttu-id="022d6-144">Разверните раскрывающееся поле **Шаблон** .</span><span class="sxs-lookup"><span data-stu-id="022d6-144">Expand the **Template** drop down box.</span></span>  
  
5.  <span data-ttu-id="022d6-145">Нажмите **\<File From ...>Открыть** и найдите сеанс (XML-файл), который требуется импортировать.</span><span class="sxs-lookup"><span data-stu-id="022d6-145">Click **\<File From ...>Open** and browse for the session (XML file) you want to import.</span></span>  
  
 <span data-ttu-id="022d6-146">Сеанс появится в узле **Сеансы** .</span><span class="sxs-lookup"><span data-stu-id="022d6-146">The session appears under the **Sessions** node.</span></span> <span data-ttu-id="022d6-147">По умолчанию этот сеанс не запущен.</span><span class="sxs-lookup"><span data-stu-id="022d6-147">By default, the session is not started.</span></span>  
  
## <a name="edit-an-extended-events-session"></a><span data-ttu-id="022d6-148">Изменение сеанса расширенных событий</span><span class="sxs-lookup"><span data-stu-id="022d6-148">Edit an Extended Events Session</span></span>  
 <span data-ttu-id="022d6-149">Сеанс расширенных событий вы можете изменить в обозревателе объектов.</span><span class="sxs-lookup"><span data-stu-id="022d6-149">You can edit an Extended Events session in Object Explorer.</span></span>  
  
 <span data-ttu-id="022d6-150">Изменение сеанса расширенных событий</span><span class="sxs-lookup"><span data-stu-id="022d6-150">To edit an Extended Events session:</span></span>  
  
1.  <span data-ttu-id="022d6-151">В **обозревателе объектов**разверните узлы **Управление**, **Расширенные события**и **Сеансы** .</span><span class="sxs-lookup"><span data-stu-id="022d6-151">In **Object Explorer**, expand the **Management**, **Extended Events**, and then **Sessions** nodes.</span></span>  
  
2.  <span data-ttu-id="022d6-152">Щелкните правой кнопкой мыши сеанс и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="022d6-152">Right-click a session and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="022d6-153">В разделе **Выбор страницы** выберите страницу или страницы для изменения.</span><span class="sxs-lookup"><span data-stu-id="022d6-153">In the **Select a page** section, select the page or pages you want to edit.</span></span>  
  
4.  <span data-ttu-id="022d6-154">После завершения пересмотра сеанса событий нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="022d6-154">After you finish revising the event session, click **OK**.</span></span>  
  
## <a name="script-an-event-session-definition-using-tsql"></a><span data-ttu-id="022d6-155">Включение определения сеанса событий в скрипт с помощью [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="022d6-155">Script an Event Session Definition Using [!INCLUDE[tsql](../../includes/tsql-md.md)]</span></span>  
 <span data-ttu-id="022d6-156">Как в «Мастере новых сеансов», так и в диалоговом окне «Создание сеанса» имеется параметр «Скрипт», который позволяет создать код [!INCLUDE[tsql](../../includes/tsql-md.md)] , выполняющий определение сеанса расширенных событий.</span><span class="sxs-lookup"><span data-stu-id="022d6-156">Both the New Session Wizard and the New Session dialog have a Script option that generates the [!INCLUDE[tsql](../../includes/tsql-md.md)] that defines the Extended Events session.</span></span>  
  
 <span data-ttu-id="022d6-157">Доступ к [!INCLUDE[tsql](../../includes/tsql-md.md)] для существующего сеанса расширенных событий выполняется щелчком правой кнопки мыши имени сеанса с последующим выбором команд **Создать скрипт сеанса как**и **Создать на**.</span><span class="sxs-lookup"><span data-stu-id="022d6-157">You can access the [!INCLUDE[tsql](../../includes/tsql-md.md)] for an existing Extended Events session by right clicking the session name, selecting **Script Session as**, and then selecting **Create to**.</span></span>  
  
## <a name="delete-an-extended-events-session"></a><span data-ttu-id="022d6-158">Удаление сеанса расширенных событий</span><span class="sxs-lookup"><span data-stu-id="022d6-158">Delete an Extended Events Session</span></span>  
 <span data-ttu-id="022d6-159">Сеанс расширенных событий можно удалить.</span><span class="sxs-lookup"><span data-stu-id="022d6-159">You can delete an Extended Events session:</span></span>  
  
-   <span data-ttu-id="022d6-160">В редакторе запросов при помощи `DROP EVENT SESSION`.</span><span class="sxs-lookup"><span data-stu-id="022d6-160">In Query Editor using `DROP EVENT SESSION`.</span></span>  
  
-   <span data-ttu-id="022d6-161">В **обозревателе объектов**.</span><span class="sxs-lookup"><span data-stu-id="022d6-161">In **Object Explorer**.</span></span>  
  
 <span data-ttu-id="022d6-162">При удалении сеанса событий удаляются все сведения о конфигурации, а определение сеанса больше не отображается в представлении каталога sys.server_event_sessions.</span><span class="sxs-lookup"><span data-stu-id="022d6-162">When you delete an event session, all configuration information is removed and the session definition no longer appears in the sys.server_event_sessions catalog view.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="022d6-163">system_health и AlwaysOn_health включены в состав [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ; не удаляйте их.</span><span class="sxs-lookup"><span data-stu-id="022d6-163">system_health and AlwaysOn_health are included with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]; do not delete them.</span></span> <span data-ttu-id="022d6-164">Представление system_health по умолчанию включено (дополнительные сведения см. в статье [Использование сеанса system_health](use-the-ssms-xe-profiler.md)).</span><span class="sxs-lookup"><span data-stu-id="022d6-164">system_health is enabled by default (for more information, see [Use the system_health Session](use-the-ssms-xe-profiler.md)).</span></span> <span data-ttu-id="022d6-165">По умолчанию AlwaysOn_health отключен.</span><span class="sxs-lookup"><span data-stu-id="022d6-165">AlwaysOn_health is off by default.</span></span> <span data-ttu-id="022d6-166">Эти сеансы собирают данные, которые могут оказаться полезными для диагностики проблем с производительностью.</span><span class="sxs-lookup"><span data-stu-id="022d6-166">These sessions collect data that can be useful for diagnosing performance issues.</span></span>  
  
 <span data-ttu-id="022d6-167">Для удаления сеанса расширенных событий требуется разрешение ALTER ANY EVENT SESSION.</span><span class="sxs-lookup"><span data-stu-id="022d6-167">To delete an Extended Events session, you must have the ALTER ANY EVENT SESSION permission.</span></span>  
  
 <span data-ttu-id="022d6-168">Удаление сеанса расширенных событий с помощью **обозревателя объектов**.</span><span class="sxs-lookup"><span data-stu-id="022d6-168">To delete an Extended Events session in **Object Explorer**:</span></span>  
  
1.  <span data-ttu-id="022d6-169">Разверните узлы **Управление**, **Расширенные события**, а затем **Сеансы** .</span><span class="sxs-lookup"><span data-stu-id="022d6-169">Expand the **Management**, **Extended Events**, and then **Sessions** nodes.</span></span>  
  
2.  <span data-ttu-id="022d6-170">Щелкните правой кнопкой мыши сеанс и выберите пункт **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="022d6-170">Right-click a session and select **Delete**.</span></span>  
  
3.  <span data-ttu-id="022d6-171">В диалоговом окне **Удаление объекта** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="022d6-171">In the **Delete Object** dialog box, click **OK**.</span></span>  
  
4.  <span data-ttu-id="022d6-172">После завершения пересмотра сеанса событий нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="022d6-172">After you finish revising the event session, click **OK**.</span></span>  
  
 <span data-ttu-id="022d6-173">Чтобы удалить сеанс расширенных событий в **редакторе запросов**, создайте следующие инструкции, заменив *session_name* именем сеанса расширенных событий, который требуется удалить:</span><span class="sxs-lookup"><span data-stu-id="022d6-173">To delete an Extended Events session in the **Query Editor**, Issue the following statements, replacing *session_name* with the name of the Extended Events session that you want to delete:</span></span>  
  
```  
DROP EVENT SESSION [session_name]  
ON SERVER  
```  
  
  
