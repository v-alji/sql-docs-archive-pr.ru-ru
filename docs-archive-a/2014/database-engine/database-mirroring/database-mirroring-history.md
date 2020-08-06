---
title: Журнал зеркального отображения базы данных | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.dbmmonitor.databasemirroringhistory.f1
ms.assetid: 1d6e4b10-4a23-47d7-9918-c417992f09d3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3e32ad9bfdce15413d89fbd5ba3d79a5ef14f7a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666729"
---
# <a name="database-mirroring-history"></a><span data-ttu-id="160b3-102">Журнал зеркального отображения базы данных</span><span class="sxs-lookup"><span data-stu-id="160b3-102">Database Mirroring History</span></span>
  <span data-ttu-id="160b3-103">Это диалоговое окно используется для просмотра журнала о состоянии зеркального отображения для зеркально отображаемой базы данных на указанном экземпляре сервера.</span><span class="sxs-lookup"><span data-stu-id="160b3-103">Use this dialog box to view the history of mirroring status for a mirrored database on a specified server instance.</span></span>  
  
 <span data-ttu-id="160b3-104">**Наблюдение за зеркальным отображением базы данных с помощью среды SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="160b3-104">**To use SQL Server Management Studio to monitor database mirroring**</span></span>  
  
-   [<span data-ttu-id="160b3-105">Запуск монитора зеркального отображения баз данных (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="160b3-105">Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;</span></span>](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md)  
  
## <a name="options"></a><span data-ttu-id="160b3-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="160b3-106">Options</span></span>  
 <span data-ttu-id="160b3-107">**Экземпляр сервера**</span><span class="sxs-lookup"><span data-stu-id="160b3-107">**Server instance**</span></span>  
 <span data-ttu-id="160b3-108">Имя экземпляра сервера, по журналу которого формируется отчет.</span><span class="sxs-lookup"><span data-stu-id="160b3-108">Name of the server instance from which the history is being reported.</span></span>  
  
 <span data-ttu-id="160b3-109">**База данных**</span><span class="sxs-lookup"><span data-stu-id="160b3-109">**Database**</span></span>  
 <span data-ttu-id="160b3-110">Имя базы данных, по журналу которой формируется отчет.</span><span class="sxs-lookup"><span data-stu-id="160b3-110">Name of the database whose history is being reported.</span></span>  
  
 <span data-ttu-id="160b3-111">**Фильтровать список по**</span><span class="sxs-lookup"><span data-stu-id="160b3-111">**Filter list by**</span></span>  
 <span data-ttu-id="160b3-112">Позволяет получить список значений фильтра.</span><span class="sxs-lookup"><span data-stu-id="160b3-112">Lists filter values.</span></span> <span data-ttu-id="160b3-113">После выбора нового значения содержимое сетки обновляется автоматически.</span><span class="sxs-lookup"><span data-stu-id="160b3-113">Choosing a new value refreshes the grid automatically.</span></span>  
  
 <span data-ttu-id="160b3-114">Возможные значения фильтра:</span><span class="sxs-lookup"><span data-stu-id="160b3-114">The possible filter values are:</span></span>  
  
-   <span data-ttu-id="160b3-115">Последние два часа</span><span class="sxs-lookup"><span data-stu-id="160b3-115">Last two hours</span></span>  
  
-   <span data-ttu-id="160b3-116">Последние четыре часа</span><span class="sxs-lookup"><span data-stu-id="160b3-116">Last four hours</span></span>  
  
-   <span data-ttu-id="160b3-117">Последние восемь часов</span><span class="sxs-lookup"><span data-stu-id="160b3-117">Last eight hours</span></span>  
  
-   <span data-ttu-id="160b3-118">Последний день</span><span class="sxs-lookup"><span data-stu-id="160b3-118">Last day</span></span>  
  
-   <span data-ttu-id="160b3-119">Последние два дня</span><span class="sxs-lookup"><span data-stu-id="160b3-119">Last two days</span></span>  
  
-   <span data-ttu-id="160b3-120">Последние 100 записей</span><span class="sxs-lookup"><span data-stu-id="160b3-120">Last 100 records</span></span>  
  
-   <span data-ttu-id="160b3-121">Последние 500 записей</span><span class="sxs-lookup"><span data-stu-id="160b3-121">Last 500 records</span></span>  
  
-   <span data-ttu-id="160b3-122">Последние 1000 записей</span><span class="sxs-lookup"><span data-stu-id="160b3-122">Last 1000 records</span></span>  
  
-   <span data-ttu-id="160b3-123">Все записи</span><span class="sxs-lookup"><span data-stu-id="160b3-123">All records</span></span>  
  
 <span data-ttu-id="160b3-124">**Обновить**</span><span class="sxs-lookup"><span data-stu-id="160b3-124">**Refresh**</span></span>  
 <span data-ttu-id="160b3-125">Нажмите для обновления списка журнала.</span><span class="sxs-lookup"><span data-stu-id="160b3-125">Click to refresh the history list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="160b3-126">При использовании этого диалогового окна автоматическое обновление списка журнала не происходит.</span><span class="sxs-lookup"><span data-stu-id="160b3-126">This dialog box does not automatically refresh the history list.</span></span> <span data-ttu-id="160b3-127">Чтобы обновить список, необходимо либо нажать кнопку **Обновить** , либо выбрать другой параметр фильтрации.</span><span class="sxs-lookup"><span data-stu-id="160b3-127">To refresh the list, either click **Refresh** or choose another filter option.</span></span> <span data-ttu-id="160b3-128">Обновление журнала зеркального отображения могут осуществлять только члены предопределенной роли сервера **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="160b3-128">Only members of the **sysadmin** fixed server role can update the mirroring history.</span></span>  
  
 <span data-ttu-id="160b3-129">**Журнал**</span><span class="sxs-lookup"><span data-stu-id="160b3-129">**History**</span></span>  
 <span data-ttu-id="160b3-130">Отображает список журнала.</span><span class="sxs-lookup"><span data-stu-id="160b3-130">Displays the history list.</span></span> <span data-ttu-id="160b3-131">Щелкните заголовок столбца для сортировки сетки по этому столбцу.</span><span class="sxs-lookup"><span data-stu-id="160b3-131">Clicking on a column header sorts the grid by that column.</span></span> <span data-ttu-id="160b3-132">Список содержит следующие столбцы.</span><span class="sxs-lookup"><span data-stu-id="160b3-132">The list contains the following columns:</span></span>  
  
|<span data-ttu-id="160b3-133">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="160b3-133">Column name</span></span>|<span data-ttu-id="160b3-134">Описание</span><span class="sxs-lookup"><span data-stu-id="160b3-134">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="160b3-135">**Время записи**</span><span class="sxs-lookup"><span data-stu-id="160b3-135">**Time Recorded**</span></span>|<span data-ttu-id="160b3-136">Отметка времени строки журнала.</span><span class="sxs-lookup"><span data-stu-id="160b3-136">Timestamp of the history row.</span></span>|  
|<span data-ttu-id="160b3-137">**Роль**</span><span class="sxs-lookup"><span data-stu-id="160b3-137">**Role**</span></span>|<span data-ttu-id="160b3-138">Текущая роль в зеркальном отображении, выполняемая экземпляром сервера применительно к этой базе данных, либо «Основной», либо «Зеркальный».</span><span class="sxs-lookup"><span data-stu-id="160b3-138">Current mirroring role of the server instance for this database, either Principal or Mirror.</span></span>|  
|<span data-ttu-id="160b3-139">**Состояние зеркального отображения**</span><span class="sxs-lookup"><span data-stu-id="160b3-139">**Mirroring State**</span></span>|<span data-ttu-id="160b3-140">Состояние базы данных:</span><span class="sxs-lookup"><span data-stu-id="160b3-140">State of the database:</span></span><br /><br /> <span data-ttu-id="160b3-141">Отключено</span><span class="sxs-lookup"><span data-stu-id="160b3-141">Disconnected</span></span><br /><br /> <span data-ttu-id="160b3-142">Ожидание отработки отказа</span><span class="sxs-lookup"><span data-stu-id="160b3-142">Pending Failover</span></span><br /><br /> <span data-ttu-id="160b3-143">Приостановлена</span><span class="sxs-lookup"><span data-stu-id="160b3-143">Suspended</span></span><br /><br /> <span data-ttu-id="160b3-144">синхронизировано;</span><span class="sxs-lookup"><span data-stu-id="160b3-144">Synchronized</span></span><br /><br /> <span data-ttu-id="160b3-145">Синхронизация</span><span class="sxs-lookup"><span data-stu-id="160b3-145">Synchronizing</span></span><br /><br /> <span data-ttu-id="160b3-146">Неизвестно</span><span class="sxs-lookup"><span data-stu-id="160b3-146">Unknown</span></span>|  
|<span data-ttu-id="160b3-147">**Соединение следящего сервера**</span><span class="sxs-lookup"><span data-stu-id="160b3-147">**Witness Connection**</span></span>|<span data-ttu-id="160b3-148">Состояние соединения следящего сервера в данном сеансе зеркального отображения базы данных либо «Соединен», либо «Отсоединен».</span><span class="sxs-lookup"><span data-stu-id="160b3-148">State of the witness connection in the mirroring session of the database, either Connected or Disconnected.</span></span> <span data-ttu-id="160b3-149">Если следящий сервер отсутствует, это значение установлено в NULL.</span><span class="sxs-lookup"><span data-stu-id="160b3-149">If there is no witness, the value is NULL.</span></span>|  
|<span data-ttu-id="160b3-150">**Неотправленный журнал**</span><span class="sxs-lookup"><span data-stu-id="160b3-150">**Unsent Log**</span></span>|<span data-ttu-id="160b3-151">Размер в килобайтах (КБ) неотправленного журнала в очереди отправки основного экземпляра сервера.</span><span class="sxs-lookup"><span data-stu-id="160b3-151">Size, in kilobytes (KB), of the unsent log in the send queue on the principal server instance.</span></span>|  
|<span data-ttu-id="160b3-152">**Время отправки**</span><span class="sxs-lookup"><span data-stu-id="160b3-152">**Time to Send**</span></span>|<span data-ttu-id="160b3-153">Приблизительное количество времени, которое потребуется экземпляру основного сервера для отправки журнала, находящегося в настоящее время в очереди отправки, на экземпляр зеркального сервера ( *скорость отправки*).</span><span class="sxs-lookup"><span data-stu-id="160b3-153">Approximate amount of time the principal server instance will require to send the log that is currently in the send queue to the mirror server instance (the *send rate*).</span></span> <span data-ttu-id="160b3-154">Поскольку скорость входящих транзакций может значительно меняться, время отправки журнала является предполагаемым.</span><span class="sxs-lookup"><span data-stu-id="160b3-154">Because the rate of incoming transactions can vary significantly, the time to send log is an estimate.</span></span> <span data-ttu-id="160b3-155">Тем не менее скорость отправки может оказаться полезной для грубого подсчета времени, требующегося для отработки отказа вручную.</span><span class="sxs-lookup"><span data-stu-id="160b3-155">However, the send rate can be useful for roughly estimating the time required for a manual failover.</span></span>|  
|<span data-ttu-id="160b3-156">**Send Rate**</span><span class="sxs-lookup"><span data-stu-id="160b3-156">**Send Rate**</span></span>|<span data-ttu-id="160b3-157">Скорость, с которой информация о транзакциях передается на экземпляр зеркального сервера, КБ в секунду.</span><span class="sxs-lookup"><span data-stu-id="160b3-157">Rate at which transactions are being sent to the mirror server instance, in KB per second.</span></span>|  
|<span data-ttu-id="160b3-158">**Скорость новых транзакций**</span><span class="sxs-lookup"><span data-stu-id="160b3-158">**New Transaction Rate**</span></span>|<span data-ttu-id="160b3-159">Скорость, с которой информация о поступающих транзакциях вводится в журнал экземпляра основного сервера, КБ в секунду.</span><span class="sxs-lookup"><span data-stu-id="160b3-159">Rate at which incoming transactions are being entered into the principal's log, in KB per second.</span></span> <span data-ttu-id="160b3-160">Сравнение значения этого показателя со значением показателя **Время отправки** позволяет определить, что средства зеркального отображения не успевают поддерживать синхронизацию, или же своевременно справляются со своей работой, или даже постепенно восстанавливают синхронизацию.</span><span class="sxs-lookup"><span data-stu-id="160b3-160">To determine whether mirroring is falling behind, staying up, or catching up, compare this value to the **Time to Send** value.</span></span>|  
|<span data-ttu-id="160b3-161">**Самая старая неотправленная транзакция**</span><span class="sxs-lookup"><span data-stu-id="160b3-161">**Oldest Unsent Transaction**</span></span>|<span data-ttu-id="160b3-162">Возраст самой старой неотправленной транзакции в очереди на отправку.</span><span class="sxs-lookup"><span data-stu-id="160b3-162">Age of the oldest unsent transaction in the send queue.</span></span> <span data-ttu-id="160b3-163">Этот срок указывает, сколько минут транзакции не отправлялись на экземпляр зеркального сервера.</span><span class="sxs-lookup"><span data-stu-id="160b3-163">The age of this transaction indicates how many minutes of transactions have not yet been sent to the mirror server instance.</span></span> <span data-ttu-id="160b3-164">Это значение позволяет оценить потенциальные потери данных по времени.</span><span class="sxs-lookup"><span data-stu-id="160b3-164">This value helps measure the potential for data loss in terms of time.</span></span>|  
|<span data-ttu-id="160b3-165">**Невосстановленный журнал**</span><span class="sxs-lookup"><span data-stu-id="160b3-165">**Unrestored Log**</span></span>|<span data-ttu-id="160b3-166">Размер журнала, ожидающего в очереди повторного выполнения, КБ.</span><span class="sxs-lookup"><span data-stu-id="160b3-166">The amount of log waiting in the redo queue, in KB.</span></span>|  
|<span data-ttu-id="160b3-167">**Время восстановления**</span><span class="sxs-lookup"><span data-stu-id="160b3-167">**Time to Restore**</span></span>|<span data-ttu-id="160b3-168">Приблизительное количество минут, необходимых для применения журнала, находящегося в очереди повторов, к зеркальной базе данных.</span><span class="sxs-lookup"><span data-stu-id="160b3-168">Approximate number of minutes required for the log currently in the redo queue to be applied to the mirror database.</span></span>|  
|<span data-ttu-id="160b3-169">**Скорость восстановления**</span><span class="sxs-lookup"><span data-stu-id="160b3-169">**Restore Rate**</span></span>|<span data-ttu-id="160b3-170">Скорость, с которой транзакции восстанавливаются в зеркальной базе данных, КБ в секунду.</span><span class="sxs-lookup"><span data-stu-id="160b3-170">Rate at which transactions are being restored into the mirror database, in KB per second.</span></span>|  
|<span data-ttu-id="160b3-171">**Затраты на фиксирование изменений на зеркальном сервере**</span><span class="sxs-lookup"><span data-stu-id="160b3-171">**Mirror Commit Overhead**</span></span>|<span data-ttu-id="160b3-172">Средняя задержка в расчете на одну транзакцию, миллисекунды (только в синхронных режимах).</span><span class="sxs-lookup"><span data-stu-id="160b3-172">Average delay per transaction in milliseconds (only in synchronous modes).</span></span> <span data-ttu-id="160b3-173">Задержка — это объем дополнительной нагрузки во время ожидания экземпляром основного сервера экземпляра зеркального сервера для добавления записи журнала транзакции в очередь повтора.</span><span class="sxs-lookup"><span data-stu-id="160b3-173">This delay is the amount of overhead incurred while the principal server instance waits for the mirror server instance to write the transaction's log record into the redo queue.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="160b3-174">См. также:</span><span class="sxs-lookup"><span data-stu-id="160b3-174">See Also</span></span>  
 <span data-ttu-id="160b3-175">[Запуск монитора зеркального отображения баз данных (среда SQL Server Management Studio)](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="160b3-175">[Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span></span>  
 <span data-ttu-id="160b3-176">[Мониторинг зеркального отображения базы данных (SQL Server)](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="160b3-176">[Monitoring Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="160b3-177">Запуск мастера настройки безопасности зеркального отображения баз данных (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="160b3-177">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
  
