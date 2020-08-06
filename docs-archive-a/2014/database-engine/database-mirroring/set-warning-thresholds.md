---
title: Установка порогов предупреждений | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.dbmmonitor.setwarningthreshold.f1
ms.assetid: 17f93147-e7d9-4092-b4c2-c11b38051171
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2d5fd9c0213d74f3a6b5d0d4cb2f11d3531d336d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733037"
---
# <a name="set-warning-thresholds"></a><span data-ttu-id="158d8-102">Установка порогов предупреждений</span><span class="sxs-lookup"><span data-stu-id="158d8-102">Set Warning Thresholds</span></span>
  <span data-ttu-id="158d8-103">Это диалоговое окно позволяет разрешить и настроить один или несколько пороговых значений предупреждений для базы данных, выбранной в дереве навигации диалогового окна **Монитор зеркального отображения баз данных** .</span><span class="sxs-lookup"><span data-stu-id="158d8-103">Use this dialog box to enable and configure one or more warning thresholds for the database selected in the navigation tree of the **Database Mirroring Monitor** dialog box.</span></span>  
  
 <span data-ttu-id="158d8-104">В этом диалоговом окне предпринимается попытка подключиться к обоим экземплярам сервера.</span><span class="sxs-lookup"><span data-stu-id="158d8-104">The dialog box tries to connect to both server instances.</span></span> <span data-ttu-id="158d8-105">Эти соединения устанавливаются асинхронно.</span><span class="sxs-lookup"><span data-stu-id="158d8-105">These connections are established asynchronously.</span></span> <span data-ttu-id="158d8-106">Диалоговое окно показывает состояние соединения каждого сервера-участника.</span><span class="sxs-lookup"><span data-stu-id="158d8-106">The dialog shows the connection status of each partner.</span></span> <span data-ttu-id="158d8-107">Если сервер-участник не подключен, можно нажать кнопку **Соединить**.</span><span class="sxs-lookup"><span data-stu-id="158d8-107">If the partner is not connected, you can click **Connect**.</span></span>  
  
 <span data-ttu-id="158d8-108">**Наблюдение за зеркальным отображением базы данных с помощью среды SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="158d8-108">**To use SQL Server Management Studio to monitor database mirroring**</span></span>  
  
-   [<span data-ttu-id="158d8-109">Запуск монитора зеркального отображения баз данных (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="158d8-109">Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;</span></span>](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md)  
  
## <a name="options"></a><span data-ttu-id="158d8-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="158d8-110">Options</span></span>  
 <span data-ttu-id="158d8-111">*Экземпляр сервера и состояние его соединения*</span><span class="sxs-lookup"><span data-stu-id="158d8-111">*Server instance and its connection status*</span></span>  
 <span data-ttu-id="158d8-112">Имя экземпляра сервера-участника в форме _System_ **\\** _INSTANCE_NAME_.</span><span class="sxs-lookup"><span data-stu-id="158d8-112">Name of a partner server instance in the form _SYSTEM_**\\**_INSTANCE_NAME_.</span></span> <span data-ttu-id="158d8-113">Для экземпляра сервера по умолчанию отображается только имя системы.</span><span class="sxs-lookup"><span data-stu-id="158d8-113">For a default server instance, only the system name is displayed.</span></span>  
  
 <span data-ttu-id="158d8-114">Это поле также показывает, подключен ли в настоящее время монитор к этому экземпляру сервера.</span><span class="sxs-lookup"><span data-stu-id="158d8-114">This field also indicates whether the monitor is currently connected to this server instance.</span></span> <span data-ttu-id="158d8-115">Возможные значения состояния соединения являются таковыми:</span><span class="sxs-lookup"><span data-stu-id="158d8-115">The possible connection statuses are:</span></span>  
  
-   <span data-ttu-id="158d8-116">**Не подключено к** *имя_экземпляра_сервера*</span><span class="sxs-lookup"><span data-stu-id="158d8-116">**Not connected to**  *server_instance_name*</span></span>  
  
-   <span data-ttu-id="158d8-117">**Выполняется попытка подключения к** *имя_экземпляра_сервера*</span><span class="sxs-lookup"><span data-stu-id="158d8-117">**Trying to connect to**  *server_instance_name*</span></span>  
  
-   <span data-ttu-id="158d8-118">**Подключено к** *имя_экземпляра_сервера*</span><span class="sxs-lookup"><span data-stu-id="158d8-118">**Connected to**  *server_instance_name*</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="158d8-119">Для пользователей, не являющихся элементами предопределенной роли сервера **sysadmin**, это значение состояния принимает вид **Подключен к** *имя_экземпляра_сервера* **(ограниченные разрешения)** .</span><span class="sxs-lookup"><span data-stu-id="158d8-119">If you do are not a member of the **sysadmin** fixed server role, this status is **Connected to** *server_instance_name* **(Limited permissions)**.</span></span>  
  
 <span data-ttu-id="158d8-120">Имя каждого экземпляра сервера-участника отображается в отдельном поле *Экземпляр сервера и состояние его соединения* .</span><span class="sxs-lookup"><span data-stu-id="158d8-120">The name of each of the partner server instances is displayed in a separate *Server instance and its connection status* field.</span></span> <span data-ttu-id="158d8-121">В верхнем поле со времени начала работы монитора отображается имя основного сервера.</span><span class="sxs-lookup"><span data-stu-id="158d8-121">The top field lists the principal server when the monitor started running.</span></span>  
  
 <span data-ttu-id="158d8-122">**Подключение**/**Отмена**</span><span class="sxs-lookup"><span data-stu-id="158d8-122">**Connect**/**Cancel**</span></span>  
 <span data-ttu-id="158d8-123">Кнопка **Подключение**/**Отмена** связана с каждым из полей *Экземпляр сервера и состояние его соединения* .</span><span class="sxs-lookup"><span data-stu-id="158d8-123">A **Connect**/**Cancel** button is associated with each *Server instance and its connection status* fields.</span></span> <span data-ttu-id="158d8-124">Текст надписи на этой кнопке зависит от состояния соединения:</span><span class="sxs-lookup"><span data-stu-id="158d8-124">The state of the button depends on the connection status:</span></span>  
  
-   <span data-ttu-id="158d8-125">Если соединение с экземпляром сервера отсутствует, на кнопке отображается надпись **Соединить**.</span><span class="sxs-lookup"><span data-stu-id="158d8-125">If there is no connection to the server instance, the button text is **Connect**.</span></span> <span data-ttu-id="158d8-126">Нажмите кнопку, чтобы подключиться к экземпляру сервера.</span><span class="sxs-lookup"><span data-stu-id="158d8-126">Click to connect to the server instance.</span></span>  
  
-   <span data-ttu-id="158d8-127">Если осуществляется попытка соединения, на кнопке отображается надпись **Отмена**.</span><span class="sxs-lookup"><span data-stu-id="158d8-127">When a connection attempt is in progress, the button text is **Cancel**.</span></span> <span data-ttu-id="158d8-128">Нажмите кнопку, чтобы отменить попытку соединения.</span><span class="sxs-lookup"><span data-stu-id="158d8-128">Click to cancel the connection attempt.</span></span>  
  
-   <span data-ttu-id="158d8-129">Если сервер подключен, на кнопке отображается надпись **Подключен**и кнопка затемнена.</span><span class="sxs-lookup"><span data-stu-id="158d8-129">If the server is connected, the button text is **Connected**, and the button is dimmed.</span></span>  
  
 <span data-ttu-id="158d8-130">**Пороги**</span><span class="sxs-lookup"><span data-stu-id="158d8-130">**Thresholds**</span></span>  
 <span data-ttu-id="158d8-131">В сетке **Пороги** отображаются параметры предупреждений для двух экземпляров сервера.</span><span class="sxs-lookup"><span data-stu-id="158d8-131">The **Thresholds** grid displays the warnings settings for the two server instances.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="158d8-132">Если экземпляр сервера не подключен, относящиеся к нему столбцы отображаются с пустыми ячейками на сером фоне.</span><span class="sxs-lookup"><span data-stu-id="158d8-132">If a server instance is not connected, its columns are displayed with empty cells and a gray background.</span></span> <span data-ttu-id="158d8-133">После открытия соединения в сетке автоматически отображается содержимое, полученное от подключенного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="158d8-133">When the connection opens, the grid automatically displays the content from the instance.</span></span>  
  
 <span data-ttu-id="158d8-134">Сетка содержит следующие столбцы:</span><span class="sxs-lookup"><span data-stu-id="158d8-134">The grid contains the following columns:</span></span>  
  
 <span data-ttu-id="158d8-135">**Предупреждения**</span><span class="sxs-lookup"><span data-stu-id="158d8-135">**Warnings**</span></span>  
 <span data-ttu-id="158d8-136">Отображает поддерживаемые предупреждения:</span><span class="sxs-lookup"><span data-stu-id="158d8-136">Lists the supported warnings:</span></span>  
  
|<span data-ttu-id="158d8-137">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="158d8-137">Warning</span></span>|<span data-ttu-id="158d8-138">Описание</span><span class="sxs-lookup"><span data-stu-id="158d8-138">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="158d8-139">**Предупреждать, если размер неотправленного журнала превышает пороговое значение.**</span><span class="sxs-lookup"><span data-stu-id="158d8-139">**Warn if the unsent log exceeds the threshold**</span></span>|<span data-ttu-id="158d8-140">Это пороговое значение показывает размер в килобайтах (КБ) неотправленного журнала в очереди отправки на экземпляре основного сервера.</span><span class="sxs-lookup"><span data-stu-id="158d8-140">The threshold indicates the number of kilobytes (KB) of the unsent log in the send queue on the principal.</span></span>|  
|<span data-ttu-id="158d8-141">**Предупреждать, если размер невосстановленного журнала превысил пороговое значение.**</span><span class="sxs-lookup"><span data-stu-id="158d8-141">**Warn if the unrestored log exceeds the threshold**</span></span>|<span data-ttu-id="158d8-142">Это пороговое значение показывает размер в КБ очереди повторного выполнения на экземпляре зеркального сервера.</span><span class="sxs-lookup"><span data-stu-id="158d8-142">The threshold indicates the number of KB of the redo queue on the mirror server instance.</span></span>|  
|<span data-ttu-id="158d8-143">**Предупреждать, если время хранения самой старой неотправленной транзакции превысило пороговое значение.**</span><span class="sxs-lookup"><span data-stu-id="158d8-143">**Warn if the age of the oldest unsent transaction exceeds the threshold**</span></span>|<span data-ttu-id="158d8-144">Это пороговое значение показывает продолжительность времени в минутах, в течение которого сведения о транзакциях еще не были отправлены из очереди отправки на экземпляр зеркального сервера.</span><span class="sxs-lookup"><span data-stu-id="158d8-144">The threshold indicates the number of minutes of transactions that have not yet been sent from the send queue to the mirror server instance.</span></span> <span data-ttu-id="158d8-145">Это значение позволяет оценить потенциальные потери данных по времени.</span><span class="sxs-lookup"><span data-stu-id="158d8-145">This value helps measure the potential for data loss in terms of time.</span></span>|  
|<span data-ttu-id="158d8-146">**Предупреждать, если затраты на фиксирование изменений на зеркальном сервере превысили пороговое значение.**</span><span class="sxs-lookup"><span data-stu-id="158d8-146">**Warn if the mirror commit overhead exceeds the threshold**</span></span>|<span data-ttu-id="158d8-147">Это пороговое значение показывает продолжительность задержки в расчете на одну транзакцию в миллисекундах (имеет смысл только в режиме высокой безопасности).</span><span class="sxs-lookup"><span data-stu-id="158d8-147">The threshold indicates the number of milliseconds of delay per transaction (relevant only in high-safety mode).</span></span> <span data-ttu-id="158d8-148">Задержка — это объем дополнительной нагрузки во время ожидания экземпляром основного сервера экземпляра зеркального сервера для добавления записи журнала транзакции в очередь повтора.</span><span class="sxs-lookup"><span data-stu-id="158d8-148">This delay is the amount of overhead incurred while the principal server instance waits for the mirror server instance to write the transaction's log record into the redo queue.</span></span>|  
  
 <span data-ttu-id="158d8-149">**Включено в "** *\<server instance>* **"**</span><span class="sxs-lookup"><span data-stu-id="158d8-149">**Enabled at '** *\<server instance>* **'**</span></span>  
 <span data-ttu-id="158d8-150">Неустановленный флажок указывает, что это предупреждение в настоящее время отменено на данном экземпляре сервера.</span><span class="sxs-lookup"><span data-stu-id="158d8-150">A blank check box indicates that the warning is currently disabled on the server instance.</span></span> <span data-ttu-id="158d8-151">Чтобы включить предупреждение, установите относящийся к нему флажок.</span><span class="sxs-lookup"><span data-stu-id="158d8-151">To enable a warning, click its check box.</span></span>  
  
 <span data-ttu-id="158d8-152">**Пороговое значение в "** *\<server instance>* **"**</span><span class="sxs-lookup"><span data-stu-id="158d8-152">**Threshold at '** *\<server instance>* **'**</span></span>  
 <span data-ttu-id="158d8-153">Если предупреждение включено, задайте пороговое значение слева от этого столбца.</span><span class="sxs-lookup"><span data-stu-id="158d8-153">When a warning is enabled, set the threshold on the left side of this column.</span></span> <span data-ttu-id="158d8-154">Если при обновлении таблицы состояния достигается указанное пороговое значение, активируется определенное событие.</span><span class="sxs-lookup"><span data-stu-id="158d8-154">An event occurs if the specified threshold has been reached when the status table is updated.</span></span> <span data-ttu-id="158d8-155">Если отслеживание порогового значения будет отменено после ввода в настройку некоторого значения, это значение останется в указанном поле для дальнейшего использования в случае повторного ввода предупреждения в действие.</span><span class="sxs-lookup"><span data-stu-id="158d8-155">If you disable a threshold after configuring a value, your value remains in this field and will be used if you re-enable the warning.</span></span>  
  
 <span data-ttu-id="158d8-156">Если предупреждение не включено, это поле неактивно.</span><span class="sxs-lookup"><span data-stu-id="158d8-156">When a warning is not enabled, this field is inactive.</span></span>  
  
 <span data-ttu-id="158d8-157">**OK**</span><span class="sxs-lookup"><span data-stu-id="158d8-157">**OK**</span></span>  
 <span data-ttu-id="158d8-158">После нажатия кнопки **ОК** это диалоговое окно закрывается и заданные в настоящее время пороговые значения предупреждений отображаются в сетке **Пороги** страницы с вкладками **Предупреждения**.</span><span class="sxs-lookup"><span data-stu-id="158d8-158">Clicking **OK** closes this dialog box and displays the currently specified values of warning thresholds in the **Thresholds** grid on the **Warnings**tabbed page.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="158d8-159">Remarks</span><span class="sxs-lookup"><span data-stu-id="158d8-159">Remarks</span></span>  
 <span data-ttu-id="158d8-160">Пороговое значение может применяться одновременно только на одном сервере-участнике, но мы рекомендуем задавать пороговое значение для каждого конкретного события на обоих серверах-участниках, чтобы обеспечить сохранение настройки предупреждения даже в случае переключения на другую базу данных.</span><span class="sxs-lookup"><span data-stu-id="158d8-160">A threshold is only applicable at one partner at a time, but we recommend that you set a threshold for a given event on both partners to ensure that the warning persists if the database fails over.</span></span> <span data-ttu-id="158d8-161">Соответствующий порог для каждого участника зависит от возможностей производительности системы участника.</span><span class="sxs-lookup"><span data-stu-id="158d8-161">The appropriate threshold for each partner depends on the performance capabilities of that partner's system.</span></span>  
  
 <span data-ttu-id="158d8-162">Событие записывается в журнал событий по производительности только в случае, если его значение находится на границе порога или над порогом и если таблица состояния обновляется.</span><span class="sxs-lookup"><span data-stu-id="158d8-162">An event is written to the event log for a performance only if its value is at or above its threshold when the status table is being updated.</span></span> <span data-ttu-id="158d8-163">Если пиковое значение немедленно достигает порога между обновлениями состояния, то данный пик опускается.</span><span class="sxs-lookup"><span data-stu-id="158d8-163">If a peak value reaches the threshold momentarily between status updates that peak is missed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="158d8-164">См. также:</span><span class="sxs-lookup"><span data-stu-id="158d8-164">See Also</span></span>  
 <span data-ttu-id="158d8-165">[Запуск монитора зеркального отображения баз данных (среда SQL Server Management Studio)](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="158d8-165">[Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span></span>  
 <span data-ttu-id="158d8-166">[Мониторинг зеркального отображения базы данных (SQL Server)](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="158d8-166">[Monitoring Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="158d8-167">Запуск мастера настройки безопасности зеркального отображения баз данных (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="158d8-167">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
  
