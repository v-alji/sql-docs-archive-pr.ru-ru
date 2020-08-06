---
title: Свойства реплики доступности (страница "Общие") | Документы Майкрософт
ms.custom: ''
ms.date: 10/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilityreplicaproperties.general.f1
ms.assetid: 8318fefb-e045-4fab-8507-e1951fc7cec6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 313314baf009cdfb6109e63e9b65e369ac314f60
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750224"
---
# <a name="availability-replica-properties-general-page"></a><span data-ttu-id="e0d32-102">Свойства реплики доступности (страница «Общие»)</span><span class="sxs-lookup"><span data-stu-id="e0d32-102">Availability Replica Properties (General Page)</span></span>
  <span data-ttu-id="e0d32-103">Используйте это диалоговое окно для просмотра свойств реплики доступности.</span><span class="sxs-lookup"><span data-stu-id="e0d32-103">Use this dialog box to viewthe properties of an availability replica.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="e0d32-104">Список задач</span><span class="sxs-lookup"><span data-stu-id="e0d32-104">Task List</span></span>  
 <span data-ttu-id="e0d32-105">**Просмотр свойств реплики доступности**</span><span class="sxs-lookup"><span data-stu-id="e0d32-105">**To view availability replica properties**</span></span>  
  
-   [<span data-ttu-id="e0d32-106">Просмотр свойств реплики доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="e0d32-106">View Availability Replica Properties &#40;SQL Server&#41;</span></span>](view-availability-replica-properties-sql-server.md)  
  
-   [<span data-ttu-id="e0d32-107">Использование панели мониторинга AlwaysOn (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="e0d32-107">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
## <a name="ui-element-list"></a><span data-ttu-id="e0d32-108">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="e0d32-108">UI element list</span></span>  
 <span data-ttu-id="e0d32-109">**Имя группы доступности**</span><span class="sxs-lookup"><span data-stu-id="e0d32-109">**Availability group name**</span></span>  
 <span data-ttu-id="e0d32-110">Имя группы доступности.</span><span class="sxs-lookup"><span data-stu-id="e0d32-110">Name of the availability group.</span></span> <span data-ttu-id="e0d32-111">Определяемое пользователем имя, которое должно быть уникальным в отказоустойчивом кластере Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="e0d32-111">This is a user-specified name that must be unique within the Windows Server Failover Cluster (WSFC).</span></span>  
  
 <span data-ttu-id="e0d32-112">**Экземпляр сервера**</span><span class="sxs-lookup"><span data-stu-id="e0d32-112">**Server instance**</span></span>  
 <span data-ttu-id="e0d32-113">Имя сервера экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , на котором размещена данная реплика, а также имя экземпляра, если экземпляр не является используемым по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e0d32-113">Server name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that is hosting this replica and, for a non-default instance, its instance name.</span></span>  
  
 <span data-ttu-id="e0d32-114">**Роль**</span><span class="sxs-lookup"><span data-stu-id="e0d32-114">**Role**</span></span>  
 <span data-ttu-id="e0d32-115">**Источник**</span><span class="sxs-lookup"><span data-stu-id="e0d32-115">**Primary**</span></span>  
 <span data-ttu-id="e0d32-116">В настоящее время — первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="e0d32-116">Currently the primary replica.</span></span>  
  
 <span data-ttu-id="e0d32-117">**Получатель**</span><span class="sxs-lookup"><span data-stu-id="e0d32-117">**Secondary**</span></span>  
 <span data-ttu-id="e0d32-118">В настоящее время — вторичная реплика.</span><span class="sxs-lookup"><span data-stu-id="e0d32-118">Currently a secondary replica.</span></span>  
  
 <span data-ttu-id="e0d32-119">**Разрешение**</span><span class="sxs-lookup"><span data-stu-id="e0d32-119">**Resolving**</span></span>  
 <span data-ttu-id="e0d32-120">В настоящее время определяется, будет реплика выступать в роли основной или вторичной.</span><span class="sxs-lookup"><span data-stu-id="e0d32-120">Currently the replica role is in the process of being resolved to either the primary or secondary role.</span></span>  
  
 <span data-ttu-id="e0d32-121">**Режим доступности**</span><span class="sxs-lookup"><span data-stu-id="e0d32-121">**Availability mode**</span></span>  
 <span data-ttu-id="e0d32-122">Режим доступности реплики может быть одним из следующих.</span><span class="sxs-lookup"><span data-stu-id="e0d32-122">The availability mode of the replica, one of:</span></span>  
  
 <span data-ttu-id="e0d32-123">**Асинхронная фиксация**</span><span class="sxs-lookup"><span data-stu-id="e0d32-123">**Asynchronous commit**</span></span>  
 <span data-ttu-id="e0d32-124">Первичная реплика может фиксировать транзакции, не ожидая, пока вторичная реплика запишет запись журнала транзакций на диск.</span><span class="sxs-lookup"><span data-stu-id="e0d32-124">The primary replica can commit transactions without waiting for the secondary to write the log to disk.</span></span>  
  
 <span data-ttu-id="e0d32-125">**Синхронная фиксация**</span><span class="sxs-lookup"><span data-stu-id="e0d32-125">**Synchronous commit**</span></span>  
 <span data-ttu-id="e0d32-126">Первичная реплика ожидает возможности выполнения фиксации транзакции, пока вторичная реплика записывает транзакцию на диск.</span><span class="sxs-lookup"><span data-stu-id="e0d32-126">The primary replica waits to commit a given transaction until the secondary replica has written the transaction to disk.</span></span>  
  
 <span data-ttu-id="e0d32-127">Дополнительные сведения см. в разделе [режимы доступности (группы доступности AlwaysOn)](availability-modes-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="e0d32-127">For more information, see [Availability Modes (AlwaysOn Availability Groups)](availability-modes-always-on-availability-groups.md).</span></span>  
  
 <span data-ttu-id="e0d32-128">**Failover mode**</span><span class="sxs-lookup"><span data-stu-id="e0d32-128">**Failover mode**</span></span>  
 <span data-ttu-id="e0d32-129">Режим отработки отказа реплики доступности, одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="e0d32-129">The failover mode of the replica, one of:</span></span>  
  
 <span data-ttu-id="e0d32-130">**Автоматически**</span><span class="sxs-lookup"><span data-stu-id="e0d32-130">**Automatic**</span></span>  
 <span data-ttu-id="e0d32-131">Автоматический переход на другой ресурс.</span><span class="sxs-lookup"><span data-stu-id="e0d32-131">Automatic failover.</span></span> <span data-ttu-id="e0d32-132">Реплика является целью для автоматического перехода на другой ресурс.</span><span class="sxs-lookup"><span data-stu-id="e0d32-132">The replica is a target for automatic failovers.</span></span> <span data-ttu-id="e0d32-133">Эта функция поддерживается только при использовании режима доступности с синхронной фиксацией.</span><span class="sxs-lookup"><span data-stu-id="e0d32-133">This is supported only if the availability mode is set to synchronous commit.</span></span>  
  
 <span data-ttu-id="e0d32-134">**Вручную**</span><span class="sxs-lookup"><span data-stu-id="e0d32-134">**Manual**</span></span>  
 <span data-ttu-id="e0d32-135">Переход на другой ресурс вручную.</span><span class="sxs-lookup"><span data-stu-id="e0d32-135">Manual failover.</span></span> <span data-ttu-id="e0d32-136">Отработка отказа для этой реплики может быть выполнена только администратором базы данных.</span><span class="sxs-lookup"><span data-stu-id="e0d32-136">The replica can only be failed over to manually by the database administrator.</span></span>  
  
 <span data-ttu-id="e0d32-137">**Подключения в первичной роли**</span><span class="sxs-lookup"><span data-stu-id="e0d32-137">**Connections in primary role**</span></span>  
 <span data-ttu-id="e0d32-138">Тип клиентских подключений, поддерживаемый тогда, когда реплика является первичной.</span><span class="sxs-lookup"><span data-stu-id="e0d32-138">The type of client connections supported when the replica owns the primary role.</span></span>  
  
 <span data-ttu-id="e0d32-139">**разрешить все соединения.**</span><span class="sxs-lookup"><span data-stu-id="e0d32-139">**Allow all connections**</span></span>  
 <span data-ttu-id="e0d32-140">Разрешаются все соединения с базами данных в первичной реплике.</span><span class="sxs-lookup"><span data-stu-id="e0d32-140">All connections are allowed to the databases in the primary replica.</span></span> <span data-ttu-id="e0d32-141">Это параметр по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e0d32-141">This is the default setting.</span></span>  
  
 <span data-ttu-id="e0d32-142">**разрешить соединения с доступом на чтение и запись;**</span><span class="sxs-lookup"><span data-stu-id="e0d32-142">**Allow read/write connections**</span></span>  
 <span data-ttu-id="e0d32-143">Соединения, у которых свойство "Назначение приложения" равно **ReadOnly** , не разрешены.</span><span class="sxs-lookup"><span data-stu-id="e0d32-143">Connections where the Application Intent connection property is set to **ReadOnly** are disallowed.</span></span> <span data-ttu-id="e0d32-144">Если свойство «Назначение приложения» имеет значение **ReadWrite** либо оно не задано, то соединение разрешено.</span><span class="sxs-lookup"><span data-stu-id="e0d32-144">When the Application Intent property is set to **ReadWrite** or the application intent connection property is not set, the connection is allowed.</span></span>  
  
 <span data-ttu-id="e0d32-145">**Доступные для чтения вторичные**</span><span class="sxs-lookup"><span data-stu-id="e0d32-145">**Readable Secondary**</span></span>  
 <span data-ttu-id="e0d32-146">Указывает, могут ли базы данных заданной реплики доступности, играющей роль вторичной (т. е. служащей вторичной репликой), принимать соединения от клиентов. Может принимать одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="e0d32-146">Whether an availability replica that is performing the secondary role (that is, a secondary replica) can accept connections from clients, one of:</span></span>  
  
 <span data-ttu-id="e0d32-147">**Нет**</span><span class="sxs-lookup"><span data-stu-id="e0d32-147">**No**</span></span>  
 <span data-ttu-id="e0d32-148">Прямые подключения для баз данных-получателей этой реплики не разрешаются.</span><span class="sxs-lookup"><span data-stu-id="e0d32-148">No direct connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="e0d32-149">Для них не разрешен доступ для чтения.</span><span class="sxs-lookup"><span data-stu-id="e0d32-149">They are not available for read access.</span></span> <span data-ttu-id="e0d32-150">Это параметр по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e0d32-150">This is the default setting.</span></span>  
  
 <span data-ttu-id="e0d32-151">**Назначение — только чтение**</span><span class="sxs-lookup"><span data-stu-id="e0d32-151">**Read-intent only**</span></span>  
 <span data-ttu-id="e0d32-152">Для баз данных-получателей этой реплики разрешены исключительно прямые подключения только для чтения.</span><span class="sxs-lookup"><span data-stu-id="e0d32-152">Only direct read-only connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="e0d32-153">Для всех баз данных-получателей разрешен доступ для чтения.</span><span class="sxs-lookup"><span data-stu-id="e0d32-153">The secondary database(s) are all available for read access.</span></span>  
  
 <span data-ttu-id="e0d32-154">**Да**</span><span class="sxs-lookup"><span data-stu-id="e0d32-154">**Yes**</span></span>  
 <span data-ttu-id="e0d32-155">Для баз данных-получателей этой реплики разрешены все соединения, но только с доступом для чтения.</span><span class="sxs-lookup"><span data-stu-id="e0d32-155">All connections are allowed to secondary databases of this replica, but only for read access.</span></span> <span data-ttu-id="e0d32-156">Для всех баз данных-получателей разрешен доступ для чтения.</span><span class="sxs-lookup"><span data-stu-id="e0d32-156">The secondary database(s) are all available for read access.</span></span>  
  
 <span data-ttu-id="e0d32-157">Дополнительные сведения см. в разделе активные базы данных [-получатели: вторичные реплики для чтения (группы доступности AlwaysOn)](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="e0d32-157">For more information, see [Active Secondaries: Readable Secondary Replicas (AlwaysOn Availability Groups)](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md).</span></span>  
  
 <span data-ttu-id="e0d32-158">**Время ожидания сеанса (секунды)**</span><span class="sxs-lookup"><span data-stu-id="e0d32-158">**Session timeout (seconds)**</span></span>  
 <span data-ttu-id="e0d32-159">Интервал времени ожидания в секундах.</span><span class="sxs-lookup"><span data-stu-id="e0d32-159">The time-out period, in seconds.</span></span> <span data-ttu-id="e0d32-160">Интервал времени ожидания — это максимальное время, в течение которого реплика ожидает получения сообщения от другой реплики перед тем, как соединение между первичной и вторичной репликой будет признано несостоявшимся.</span><span class="sxs-lookup"><span data-stu-id="e0d32-160">The time-out period is the maximum time that the replica waits to receive a message from another replica before considering connection between the primary and secondary replica have failed.</span></span> <span data-ttu-id="e0d32-161">Время ожидания сеанса определяет, связаны ли вторичные реплики с первичной.</span><span class="sxs-lookup"><span data-stu-id="e0d32-161">Session timeout detects whether secondaries are connected the primary replica.</span></span> <span data-ttu-id="e0d32-162">При обнаружении ошибки соединения с вторичной репликой первичная реплика признает вторичную как NOT_SYNCHRONIZED.</span><span class="sxs-lookup"><span data-stu-id="e0d32-162">On detecting a failed connection with a secondary replica, the primary replica considers the secondary replica to be NOT_SYNCHRONIZED.</span></span> <span data-ttu-id="e0d32-163">При обнаружении ошибки соединения с первичной репликой вторичная реплика просто пытается установить соединение повторно.</span><span class="sxs-lookup"><span data-stu-id="e0d32-163">On detecting a failed connection with the primary replica, a secondary replica simply attempts to reconnect.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e0d32-164">Промежутки времени ожидания сеанса не вызывают автоматический переход на другой ресурс.</span><span class="sxs-lookup"><span data-stu-id="e0d32-164">Session timeouts do not cause automatic failovers.</span></span>  
  
 <span data-ttu-id="e0d32-165">**URL-адрес конечной точки**</span><span class="sxs-lookup"><span data-stu-id="e0d32-165">**Endpoint URL**</span></span>  
 <span data-ttu-id="e0d32-166">Строковое представление определяемой пользователем конечной точки зеркального отображения базы данных, которое используется соединениями первичной реплики со вторичной для синхронизации данных.</span><span class="sxs-lookup"><span data-stu-id="e0d32-166">String representation of the user-specified database mirroring endpoint that is used by connections between primary and secondary replicas for data synchronization.</span></span> <span data-ttu-id="e0d32-167">Сведения о синтаксисе конечной точки URL-адресов см. в разделе [Указание URL-адреса конечной точки при добавлении или изменении реплики доступности (SQL Server)](specify-endpoint-url-adding-or-modifying-availability-replica.md).</span><span class="sxs-lookup"><span data-stu-id="e0d32-167">For information about the syntax of endpoint URLs, see [Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;](specify-endpoint-url-adding-or-modifying-availability-replica.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0d32-168">См. также:</span><span class="sxs-lookup"><span data-stu-id="e0d32-168">See Also</span></span>  
 [<span data-ttu-id="e0d32-169">Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e0d32-169">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
  
  
