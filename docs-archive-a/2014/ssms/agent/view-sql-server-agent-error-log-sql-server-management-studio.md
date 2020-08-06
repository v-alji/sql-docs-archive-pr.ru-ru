---
title: Просмотр журнала ошибок агента SQL Server (среда SQL Server Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], SQL Server Agent
- viewing SQL Server Agent error logs
- displaying SQL Server Agent error logs
- SQL Server Agent, errors
- errors [SQL Server Agent]
ms.assetid: de920425-fa44-469f-b83d-49e3f97e97f4
author: stevestein
ms.author: sstein
ms.openlocfilehash: b88214a158a970a754c5f313bde3d53f2652ae73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734901"
---
# <a name="view-sql-server-agent-error-log-sql-server-management-studio"></a><span data-ttu-id="cfe5a-102">View SQL Server Agent Error Log (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="cfe5a-102">View SQL Server Agent Error Log (SQL Server Management Studio)</span></span>
  <span data-ttu-id="cfe5a-103">В этом разделе содержатся сведения о просмотре журнала ошибок агента  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cfe5a-103">This topic describes how to view the  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="cfe5a-104">Средство просмотра журнала позволяет просматривать многие журналы различных компонентов.</span><span class="sxs-lookup"><span data-stu-id="cfe5a-104">Log File Viewer displays log information from many different components.</span></span> <span data-ttu-id="cfe5a-105">Когда средство просмотра журнала открыто, нужный журнал можно выбрать при помощи панели **Выбор журналов** .</span><span class="sxs-lookup"><span data-stu-id="cfe5a-105">When Log File Viewer is open, use the **Select logs** pane to select the logs you want to display.</span></span> <span data-ttu-id="cfe5a-106">В каждом журнале отображаются столбцы, соответствующие типу журнала.</span><span class="sxs-lookup"><span data-stu-id="cfe5a-106">Each log displays columns appropriate to that kind of log.</span></span> <span data-ttu-id="cfe5a-107">Список доступных журналов зависит от того, каким способом было открыто средство просмотра журнала.</span><span class="sxs-lookup"><span data-stu-id="cfe5a-107">The logs that are available depend on how Log File Viewer is opened.</span></span>  
  
 <span data-ttu-id="cfe5a-108">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="cfe5a-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="cfe5a-109">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="cfe5a-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="cfe5a-110">Ограничения</span><span class="sxs-lookup"><span data-stu-id="cfe5a-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="cfe5a-111">Безопасность</span><span class="sxs-lookup"><span data-stu-id="cfe5a-111">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="cfe5a-112">Просмотр журнала ошибок агента SQL Server с помощью среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cfe5a-112">To view the SQL Server Agent error log, using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="cfe5a-113">Перед началом</span><span class="sxs-lookup"><span data-stu-id="cfe5a-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="cfe5a-114">Ограничения</span><span class="sxs-lookup"><span data-stu-id="cfe5a-114">Limitations and Restrictions</span></span>  
 <span data-ttu-id="cfe5a-115">Узел агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] отображается в обозревателе объектов только при наличии у пользователя разрешения на использование узла.</span><span class="sxs-lookup"><span data-stu-id="cfe5a-115">Object Explorer only displays the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node if you have permission to use it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="cfe5a-116">безопасность</span><span class="sxs-lookup"><span data-stu-id="cfe5a-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="cfe5a-117">Permissions</span><span class="sxs-lookup"><span data-stu-id="cfe5a-117">Permissions</span></span>  
 <span data-ttu-id="cfe5a-118">Для выполнения своих функций агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] должен быть настроен на использование учетных данных записи, которая является членом предопределенной роли сервера **sysadmin** в среде [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cfe5a-118">To perform its functions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to use the credentials of an account that is a member of the **sysadmin** fixed server role in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="cfe5a-119">Эта учетная запись должна иметь следующие разрешения Windows.</span><span class="sxs-lookup"><span data-stu-id="cfe5a-119">The account must have the following Windows permissions:</span></span>  
  
-   <span data-ttu-id="cfe5a-120">Вход в систему в качестве службы (SeServiceLogonRight)</span><span class="sxs-lookup"><span data-stu-id="cfe5a-120">Log on as a service (SeServiceLogonRight)</span></span>  
  
-   <span data-ttu-id="cfe5a-121">Замена токена уровня процесса (SeAssignPrimaryTokenPrivilege)</span><span class="sxs-lookup"><span data-stu-id="cfe5a-121">Replace a process-level token (SeAssignPrimaryTokenPrivilege)</span></span>  
  
-   <span data-ttu-id="cfe5a-122">Обход проходной проверки (SeChangeNotifyPrivilege)</span><span class="sxs-lookup"><span data-stu-id="cfe5a-122">Bypass traverse checking (SeChangeNotifyPrivilege)</span></span>  
  
-   <span data-ttu-id="cfe5a-123">Назначение квот памяти процессам (SeIncreaseQuotaPrivilege)</span><span class="sxs-lookup"><span data-stu-id="cfe5a-123">Adjust memory quotas for a process (SeIncreaseQuotaPrivilege)</span></span>  
  
 <span data-ttu-id="cfe5a-124">Дополнительные сведения о разрешениях Windows, необходимых для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] учетной записи службы агента, см. в разделе [Выбор учетной записи для службы агент SQL Server](select-an-account-for-the-sql-server-agent-service.md) и [Настройка учетных записей службы Windows и разрешений](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="cfe5a-124">For more information about the Windows permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md) and [Configure Windows Service Accounts and Permissions](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="cfe5a-125">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cfe5a-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-ssnoversion-agent-error-log"></a><span data-ttu-id="cfe5a-126">Просмотр журнала ошибок агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfe5a-126">To view the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log</span></span>  
  
1.  <span data-ttu-id="cfe5a-127">В **обозревателе объектов**щелкните значок «плюс», чтобы развернуть сервер, содержащий журнал агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , который необходимо просмотреть.</span><span class="sxs-lookup"><span data-stu-id="cfe5a-127">In **Object Explorer**, click the plus sign to expand the server that contains the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log that you want to view.</span></span>  
  
2.  <span data-ttu-id="cfe5a-128">Щелкните знак "плюс", чтобы развернуть **Агент SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="cfe5a-128">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="cfe5a-129">Щелкните значок «плюс», чтобы развернуть папку **Журналы ошибок** .</span><span class="sxs-lookup"><span data-stu-id="cfe5a-129">Click the plus sign to expand the **Error Logs** folder.</span></span>  
  
4.  <span data-ttu-id="cfe5a-130">Щелкните правой кнопкой журнал ошибок, который необходимо просмотреть, и выберите **Просмотреть журнал агента**.</span><span class="sxs-lookup"><span data-stu-id="cfe5a-130">Right-click the error log you want to view and select **View Agent Log**.</span></span>  
  
     <span data-ttu-id="cfe5a-131">В диалоговом окне **Просмотр файла журнала —**_server_name_ доступны следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="cfe5a-131">The following options are available in the **Log File Viewer -**_server_name_ dialog box:</span></span>  
  
     <span data-ttu-id="cfe5a-132">**Загрузить журнал**</span><span class="sxs-lookup"><span data-stu-id="cfe5a-132">**Load Log**</span></span>  
     <span data-ttu-id="cfe5a-133">Открывает диалоговое окно, в котором можно указать загружаемый файл журнала.</span><span class="sxs-lookup"><span data-stu-id="cfe5a-133">Open a dialog box where you can specify a log file to load.</span></span>  
  
     <span data-ttu-id="cfe5a-134">**Экспорт**</span><span class="sxs-lookup"><span data-stu-id="cfe5a-134">**Export**</span></span>  
     <span data-ttu-id="cfe5a-135">Открывает диалоговое окно, позволяющее экспортировать данные из сетки **Сведения о файле журнала** в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="cfe5a-135">Open a dialog box that lets you export the information that is shown in the **Log file summary** grid to a text file.</span></span>  
  
     <span data-ttu-id="cfe5a-136">**Обновить**</span><span class="sxs-lookup"><span data-stu-id="cfe5a-136">**Refresh**</span></span>  
     <span data-ttu-id="cfe5a-137">Позволяет обновить представление выбранных журналов.</span><span class="sxs-lookup"><span data-stu-id="cfe5a-137">Refresh the view of the selected logs.</span></span> <span data-ttu-id="cfe5a-138">При нажатии кнопки **Обновить** выбранные журналы заново считываются с целевого сервера с применением параметров фильтра.</span><span class="sxs-lookup"><span data-stu-id="cfe5a-138">The **Refresh** button rereads the selected logs from the target server while applying any filter settings.</span></span>  
  
     <span data-ttu-id="cfe5a-139">**Filter**</span><span class="sxs-lookup"><span data-stu-id="cfe5a-139">**Filter**</span></span>  
     <span data-ttu-id="cfe5a-140">Открывает диалоговое окно, позволяющее указывать параметры фильтрации файла журнала, например **Соединение**и **Дата**или другие **Общие** условия фильтра.</span><span class="sxs-lookup"><span data-stu-id="cfe5a-140">Open a dialog box that lets you specify settings that are used to filter the log file, such as **Connection**, **Date**, or other **General** filter criteria.</span></span>  
  
     <span data-ttu-id="cfe5a-141">**Поиск**</span><span class="sxs-lookup"><span data-stu-id="cfe5a-141">**Search**</span></span>  
     <span data-ttu-id="cfe5a-142">Позволяет найти определенный текст в файле журнала.</span><span class="sxs-lookup"><span data-stu-id="cfe5a-142">Search the log file for specific text.</span></span> <span data-ttu-id="cfe5a-143">Поиск с символами-шаблонами не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="cfe5a-143">Searching with wildcard characters is not supported.</span></span>  
  
     <span data-ttu-id="cfe5a-144">**Остановить**</span><span class="sxs-lookup"><span data-stu-id="cfe5a-144">**Stop**</span></span>  
     <span data-ttu-id="cfe5a-145">Прекращает загрузку записей файла журнала.</span><span class="sxs-lookup"><span data-stu-id="cfe5a-145">Stops loading the log file entries.</span></span> <span data-ttu-id="cfe5a-146">Например, можно использовать этот параметр, если загрузка удаленного файла или файла журнала вне сети занимает длительное время, а нужно просмотреть лишь наиболее свежие записи.</span><span class="sxs-lookup"><span data-stu-id="cfe5a-146">For example, you can use this option if a remote or offline log file takes a long time to load, and you only want to view the most recent entries.</span></span>  
  
     <span data-ttu-id="cfe5a-147">**Сведения о файле журнала**</span><span class="sxs-lookup"><span data-stu-id="cfe5a-147">**Log file summary**</span></span>  
     <span data-ttu-id="cfe5a-148">Эта информационная панель содержит сводку данных по фильтрации файла журнала.</span><span class="sxs-lookup"><span data-stu-id="cfe5a-148">This information panel displays a summary of the log file filtering.</span></span> <span data-ttu-id="cfe5a-149">Если файл не фильтруется, на панели отображается текст **без фильтров**.</span><span class="sxs-lookup"><span data-stu-id="cfe5a-149">If the file is not filtered, you will see the following text, **No filter applied**.</span></span> <span data-ttu-id="cfe5a-150">Если фильтр применяется к журналу, отображается следующий текст: **Критерий отбора:** \<filter criteria>.</span><span class="sxs-lookup"><span data-stu-id="cfe5a-150">If a filter is applied to the log, you will see the following text, **Filter log entries where:** \<filter criteria>.</span></span>  
  
     <span data-ttu-id="cfe5a-151">**Сведения о выбранной строке**</span><span class="sxs-lookup"><span data-stu-id="cfe5a-151">**Selected row details**</span></span>  
     <span data-ttu-id="cfe5a-152">Выберите строку для отображения дополнительных сведений о выбранной строке события внизу страницы.</span><span class="sxs-lookup"><span data-stu-id="cfe5a-152">Select a row to display additional details about the selected event row at the bottom of the page.</span></span> <span data-ttu-id="cfe5a-153">Порядок столбцов можно менять, перетаскивая их в нужное место сетки.</span><span class="sxs-lookup"><span data-stu-id="cfe5a-153">The columns can be reordered by dragging them to new locations in the grid.</span></span> <span data-ttu-id="cfe5a-154">Размер столбцов можно менять, перетаскивая разделители столбцов в заголовке сетки вправо или влево.</span><span class="sxs-lookup"><span data-stu-id="cfe5a-154">The columns can be resized by dragging the column separator bars in the grid header to the left or right.</span></span> <span data-ttu-id="cfe5a-155">Если дважды щелкнуть разделитель столбцов в заголовке сетки, ширина столбца будет автоматически подогнана под его содержимое.</span><span class="sxs-lookup"><span data-stu-id="cfe5a-155">Double-click the column separator bars in the grid header to automatically size the column to the content width.</span></span>  
  
     <span data-ttu-id="cfe5a-156">**Экземпляр**</span><span class="sxs-lookup"><span data-stu-id="cfe5a-156">**Instance**</span></span>  
     <span data-ttu-id="cfe5a-157">Имя экземпляра, к которому относится происшедшее событие.</span><span class="sxs-lookup"><span data-stu-id="cfe5a-157">The name of the instance on which the event occurred.</span></span> <span data-ttu-id="cfe5a-158">Отображается как *имя_компьютера*\\*имя_экземпляра*.</span><span class="sxs-lookup"><span data-stu-id="cfe5a-158">This is displayed as *computer name*\\*instance name*.</span></span>  
  
     <span data-ttu-id="cfe5a-159">**Дата**</span><span class="sxs-lookup"><span data-stu-id="cfe5a-159">**Date**</span></span>  
     <span data-ttu-id="cfe5a-160">Дата события.</span><span class="sxs-lookup"><span data-stu-id="cfe5a-160">Displays the date of the event.</span></span>  
  
     <span data-ttu-id="cfe5a-161">**Source**</span><span class="sxs-lookup"><span data-stu-id="cfe5a-161">**Source**</span></span>  
     <span data-ttu-id="cfe5a-162">Исходная функция, создавшая событие, например имя службы (MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="cfe5a-162">Displays the source feature from which the event is created, such as the name of the service (MSSQLSERVER, for example).</span></span> <span data-ttu-id="cfe5a-163">Отображается не для всех типов журнала.</span><span class="sxs-lookup"><span data-stu-id="cfe5a-163">This does not appear for all log types.</span></span>  
  
     <span data-ttu-id="cfe5a-164">**Сообщение**</span><span class="sxs-lookup"><span data-stu-id="cfe5a-164">**Message**</span></span>  
     <span data-ttu-id="cfe5a-165">Сообщение, связанное с событием.</span><span class="sxs-lookup"><span data-stu-id="cfe5a-165">Displays any messages associated with the event.</span></span>  
  
     <span data-ttu-id="cfe5a-166">**Log Type**</span><span class="sxs-lookup"><span data-stu-id="cfe5a-166">**Log Type**</span></span>  
     <span data-ttu-id="cfe5a-167">Отображает тип журнала, которому принадлежит событие.</span><span class="sxs-lookup"><span data-stu-id="cfe5a-167">Displays the type of log to which the event belongs.</span></span> <span data-ttu-id="cfe5a-168">Все выбранные журналы отображаются в окне сводки файла журнала.</span><span class="sxs-lookup"><span data-stu-id="cfe5a-168">All selected logs appear in the log file summary window.</span></span>  
  
     <span data-ttu-id="cfe5a-169">**Log Source**</span><span class="sxs-lookup"><span data-stu-id="cfe5a-169">**Log Source**</span></span>  
     <span data-ttu-id="cfe5a-170">Отображает описание исходного журнала, в котором зарегистрировано событие.</span><span class="sxs-lookup"><span data-stu-id="cfe5a-170">Displays a description of the source log in which the event is captured.</span></span>  
  
5.  <span data-ttu-id="cfe5a-171">После завершения нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="cfe5a-171">When finished, click **Close**.</span></span>  
  
  
