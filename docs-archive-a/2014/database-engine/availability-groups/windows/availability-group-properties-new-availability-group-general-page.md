---
title: Свойства группы доступности и новая группа доступности (страница "Общие") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroupproperties.general.f1
ms.assetid: 9af5379f-91b8-4729-9f75-4a80242a30e9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 876b9d0948b7cd0d01c21b0ec1d64c51a55fa157
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655373"
---
# <a name="availability-group-properties-and-new-availability-group-general-page"></a><span data-ttu-id="0b497-102">Свойства группы доступности и создание группы доступности (страница "Общие")</span><span class="sxs-lookup"><span data-stu-id="0b497-102">Availability Group Properties and New Availability Group (General Page)</span></span>
  <span data-ttu-id="0b497-103">Приведенные в этом разделе сведения относятся к вкладке **Общие** диалоговых окон **Создание группы доступности** и **Свойства группы доступности** .</span><span class="sxs-lookup"><span data-stu-id="0b497-103">This topic applies to the **General** tab of both the **New Availability Group** dialog box and the **Availability Group Properties** dialog box.</span></span>  <span data-ttu-id="0b497-104">Диалоговое окно **Создание группы доступности** позволяет создать новую группу доступности, не прибегая к использованию [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0b497-104">The **New Availability Group** dialog box enables you to create a new availability group without using the [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)].</span></span> <span data-ttu-id="0b497-105">Диалоговое окно **Свойства группы доступности** позволяет просматривать и изменять конфигурацию существующей группы доступности.</span><span class="sxs-lookup"><span data-stu-id="0b497-105">The **Availability Group Properties** dialog box enables you to view and alter the configuration of an existing availability group.</span></span>  
  
 <span data-ttu-id="0b497-106">**Просмотр свойств группы доступности**</span><span class="sxs-lookup"><span data-stu-id="0b497-106">**To view availability group properties**</span></span>  
  
-   [<span data-ttu-id="0b497-107">Просмотр свойств группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="0b497-107">View Availability Group Properties &#40;SQL Server&#41;</span></span>](view-availability-group-properties-sql-server.md)  
  
-   [<span data-ttu-id="0b497-108">Использование панели мониторинга AlwaysOn (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="0b497-108">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
## <a name="ui-element-list"></a><span data-ttu-id="0b497-109">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="0b497-109">UI element list</span></span>  
 <span data-ttu-id="0b497-110">**Имя группы доступности**</span><span class="sxs-lookup"><span data-stu-id="0b497-110">**Availability group name**</span></span>  
 <span data-ttu-id="0b497-111">Имя группы доступности.</span><span class="sxs-lookup"><span data-stu-id="0b497-111">Name of the availability group.</span></span> <span data-ttu-id="0b497-112">Определяемое пользователем имя, которое должно быть уникальным в отказоустойчивом кластере Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="0b497-112">This is a user-specified name that must be unique within the Windows Server Failover Cluster (WSFC).</span></span>  
  
## <a name="availability-databases"></a><span data-ttu-id="0b497-113">Базы данных доступности</span><span class="sxs-lookup"><span data-stu-id="0b497-113">Availability Databases</span></span>  
 <span data-ttu-id="0b497-114">**Имя базы данных**</span><span class="sxs-lookup"><span data-stu-id="0b497-114">**Database Name**</span></span>  
 <span data-ttu-id="0b497-115">Имя базы данных, добавленной к группе доступности.</span><span class="sxs-lookup"><span data-stu-id="0b497-115">Name of a database that has been added to the availability group.</span></span>  
  
 <span data-ttu-id="0b497-116">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="0b497-116">**Add**</span></span>  
 <span data-ttu-id="0b497-117">Нажмите, чтобы добавить новую базу данных в группу доступности.</span><span class="sxs-lookup"><span data-stu-id="0b497-117">Click to add a database to the availability group.</span></span>  
  
 <span data-ttu-id="0b497-118">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="0b497-118">**Remove**</span></span>  
 <span data-ttu-id="0b497-119">Нажмите, чтобы удалить выбранную базу данных из группы доступности.</span><span class="sxs-lookup"><span data-stu-id="0b497-119">Click to remove a selected database from the availability group.</span></span>  
  
## <a name="availability-replicas"></a><span data-ttu-id="0b497-120">Реплики доступности</span><span class="sxs-lookup"><span data-stu-id="0b497-120">Availability Replicas</span></span>  
 <span data-ttu-id="0b497-121">**Экземпляр сервера**</span><span class="sxs-lookup"><span data-stu-id="0b497-121">**Server instance**</span></span>  
 <span data-ttu-id="0b497-122">Имя сервера экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , на котором размещена данная реплика, а также имя экземпляра, если экземпляр не является используемым по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0b497-122">Server name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that is hosting this replica and, for a non-default instance, its instance name.</span></span>  
  
 <span data-ttu-id="0b497-123">**Роль**</span><span class="sxs-lookup"><span data-stu-id="0b497-123">**Role**</span></span>  
 <span data-ttu-id="0b497-124">**Источник**</span><span class="sxs-lookup"><span data-stu-id="0b497-124">**Primary**</span></span>  
 <span data-ttu-id="0b497-125">В настоящее время — первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="0b497-125">Currently the primary replica.</span></span>  
  
 <span data-ttu-id="0b497-126">**Получатель**</span><span class="sxs-lookup"><span data-stu-id="0b497-126">**Secondary**</span></span>  
 <span data-ttu-id="0b497-127">В настоящее время — вторичная реплика.</span><span class="sxs-lookup"><span data-stu-id="0b497-127">Currently a secondary replica.</span></span>  
  
 <span data-ttu-id="0b497-128">**Разрешение**</span><span class="sxs-lookup"><span data-stu-id="0b497-128">**Resolving**</span></span>  
 <span data-ttu-id="0b497-129">В настоящее время определяется, будет реплика выступать в роли основной или вторичной.</span><span class="sxs-lookup"><span data-stu-id="0b497-129">Currently the replica role is in the process of being resolved to either the primary or secondary role.</span></span>  
  
 <span data-ttu-id="0b497-130">**Режим доступности**</span><span class="sxs-lookup"><span data-stu-id="0b497-130">**Availability Mode**</span></span>  
 <span data-ttu-id="0b497-131">Режим доступности реплики может быть одним из следующих.</span><span class="sxs-lookup"><span data-stu-id="0b497-131">The availability mode of the replica, one of:</span></span>  
  
 <span data-ttu-id="0b497-132">**Асинхронная фиксация**</span><span class="sxs-lookup"><span data-stu-id="0b497-132">**Asynchronous commit**</span></span>  
 <span data-ttu-id="0b497-133">Первичная реплика может фиксировать транзакции, не ожидая, пока вторичная реплика запишет запись журнала транзакций на диск.</span><span class="sxs-lookup"><span data-stu-id="0b497-133">The primary replica can commit transactions without waiting for the secondary to write the log to disk.</span></span>  
  
 <span data-ttu-id="0b497-134">**Синхронная фиксация**</span><span class="sxs-lookup"><span data-stu-id="0b497-134">**Synchronous commit**</span></span>  
 <span data-ttu-id="0b497-135">Первичная реплика ожидает возможности выполнения фиксации транзакции, пока вторичная реплика записывает транзакцию на диск.</span><span class="sxs-lookup"><span data-stu-id="0b497-135">The primary replica waits to commit a given transaction until the secondary replica has written the transaction to disk.</span></span>  
  
 <span data-ttu-id="0b497-136">Дополнительные сведения см. в разделе [режимы доступности (группы доступности AlwaysOn)](availability-modes-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="0b497-136">For more information, see [Availability Modes (AlwaysOn Availability Groups)](availability-modes-always-on-availability-groups.md).</span></span>  
  
 <span data-ttu-id="0b497-137">**Режим отработки отказа**</span><span class="sxs-lookup"><span data-stu-id="0b497-137">**Failover Mode**</span></span>  
 <span data-ttu-id="0b497-138">Режим отработки отказа реплики доступности, одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="0b497-138">The failover mode of the replica, one of:</span></span>  
  
 <span data-ttu-id="0b497-139">**Автоматически**</span><span class="sxs-lookup"><span data-stu-id="0b497-139">**Automatic**</span></span>  
 <span data-ttu-id="0b497-140">Автоматический переход на другой ресурс.</span><span class="sxs-lookup"><span data-stu-id="0b497-140">Automatic failover.</span></span> <span data-ttu-id="0b497-141">Реплика является целью для автоматического перехода на другой ресурс.</span><span class="sxs-lookup"><span data-stu-id="0b497-141">The replica is a target for automatic failovers.</span></span> <span data-ttu-id="0b497-142">Эта функция поддерживается только при использовании режима доступности с синхронной фиксацией.</span><span class="sxs-lookup"><span data-stu-id="0b497-142">This is supported only if the availability mode is set to synchronous commit.</span></span>  
  
 <span data-ttu-id="0b497-143">**Вручную**</span><span class="sxs-lookup"><span data-stu-id="0b497-143">**Manual**</span></span>  
 <span data-ttu-id="0b497-144">Переход на другой ресурс вручную.</span><span class="sxs-lookup"><span data-stu-id="0b497-144">Manual failover.</span></span> <span data-ttu-id="0b497-145">Отработка отказа для этой реплики может быть выполнена только администратором базы данных.</span><span class="sxs-lookup"><span data-stu-id="0b497-145">The replica can only be failed over to manually by the database administrator.</span></span>  
  
 <span data-ttu-id="0b497-146">**Подключения в первичной роли**</span><span class="sxs-lookup"><span data-stu-id="0b497-146">**Connections in Primary Role**</span></span>  
 <span data-ttu-id="0b497-147">Тип клиентских подключений, поддерживаемый тогда, когда реплика является первичной.</span><span class="sxs-lookup"><span data-stu-id="0b497-147">The type of client connections supported when the replica owns the primary role.</span></span>  
  
 <span data-ttu-id="0b497-148">**разрешить все соединения.**</span><span class="sxs-lookup"><span data-stu-id="0b497-148">**Allow all connections**</span></span>  
 <span data-ttu-id="0b497-149">Разрешаются все соединения с базами данных в первичной реплике.</span><span class="sxs-lookup"><span data-stu-id="0b497-149">All connections are allowed to the databases in the primary replica.</span></span> <span data-ttu-id="0b497-150">Это параметр по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0b497-150">This is the default setting.</span></span>  
  
 <span data-ttu-id="0b497-151">**разрешить соединения с доступом на чтение и запись;**</span><span class="sxs-lookup"><span data-stu-id="0b497-151">**Allow read/write connections**</span></span>  
 <span data-ttu-id="0b497-152">Соединения, у которых свойство "Назначение приложения" равно **ReadOnly** , не разрешены.</span><span class="sxs-lookup"><span data-stu-id="0b497-152">Connections where the Application Intent connection property is set to **ReadOnly** are disallowed.</span></span> <span data-ttu-id="0b497-153">Если свойство «Назначение приложения» имеет значение **ReadWrite** или не задано, то соединение разрешено.</span><span class="sxs-lookup"><span data-stu-id="0b497-153">When the Application Intent property is set to **ReadWrite** or the Application Intent connection property is not set, the connection is allowed.</span></span> <span data-ttu-id="0b497-154">Дополнительные сведения о свойстве соединения «Назначение приложения» см. в разделе [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="0b497-154">For more information about Application Intent connection property, see [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
 <span data-ttu-id="0b497-155">**Доступные для чтения вторичные**</span><span class="sxs-lookup"><span data-stu-id="0b497-155">**Readable Secondary**</span></span>  
 <span data-ttu-id="0b497-156">Указывает, могут ли базы данных заданной реплики доступности, играющей роль вторичной (т. е. служащей вторичной репликой), принимать соединения от клиентов. Может принимать одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="0b497-156">Whether an availability replica that is performing the secondary role (that is, a secondary replica) can accept connections from clients, one of:</span></span>  
  
 <span data-ttu-id="0b497-157">**Нет**</span><span class="sxs-lookup"><span data-stu-id="0b497-157">**No**</span></span>  
 <span data-ttu-id="0b497-158">Прямые подключения для баз данных-получателей этой реплики не разрешаются.</span><span class="sxs-lookup"><span data-stu-id="0b497-158">No direct connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="0b497-159">Для них не разрешен доступ для чтения.</span><span class="sxs-lookup"><span data-stu-id="0b497-159">They are not available for read access.</span></span> <span data-ttu-id="0b497-160">Это параметр по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0b497-160">This is the default setting.</span></span>  
  
 <span data-ttu-id="0b497-161">**Назначение — только чтение**</span><span class="sxs-lookup"><span data-stu-id="0b497-161">**Read-intent only**</span></span>  
 <span data-ttu-id="0b497-162">Для баз данных-получателей этой реплики разрешены исключительно прямые подключения только для чтения.</span><span class="sxs-lookup"><span data-stu-id="0b497-162">Only direct read-only connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="0b497-163">Для всех баз данных-получателей разрешен доступ для чтения.</span><span class="sxs-lookup"><span data-stu-id="0b497-163">The secondary database(s) are all available for read access.</span></span>  
  
 <span data-ttu-id="0b497-164">**Да**</span><span class="sxs-lookup"><span data-stu-id="0b497-164">**Yes**</span></span>  
 <span data-ttu-id="0b497-165">Для баз данных-получателей этой реплики разрешены все соединения, но только с доступом для чтения.</span><span class="sxs-lookup"><span data-stu-id="0b497-165">All connections are allowed to secondary databases of this replica, but only for read access.</span></span> <span data-ttu-id="0b497-166">Для всех баз данных-получателей разрешен доступ для чтения.</span><span class="sxs-lookup"><span data-stu-id="0b497-166">The secondary database(s) are all available for read access.</span></span>  
  
 <span data-ttu-id="0b497-167">**Время ожидания сеанса (секунды)**</span><span class="sxs-lookup"><span data-stu-id="0b497-167">**Session Timeout (seconds)**</span></span>  
 <span data-ttu-id="0b497-168">Количество секунд, составляющее время ожидания сеанса для этой реплики.</span><span class="sxs-lookup"><span data-stu-id="0b497-168">The number of seconds for the session-timeout period on this replica.</span></span>  
  
 <span data-ttu-id="0b497-169">**URL-адрес конечной точки**</span><span class="sxs-lookup"><span data-stu-id="0b497-169">**Endpoint URL**</span></span>  
 <span data-ttu-id="0b497-170">URL-адрес конечной точки.</span><span class="sxs-lookup"><span data-stu-id="0b497-170">The URL of the endpoint.</span></span> <span data-ttu-id="0b497-171">Сведения о формате этих URL-адресов см. в разделе [Указание URL-адреса конечной точки при добавлении или изменении реплики доступности (SQL Server)](specify-endpoint-url-adding-or-modifying-availability-replica.md).</span><span class="sxs-lookup"><span data-stu-id="0b497-171">For information the format of these URLs, see [Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;](specify-endpoint-url-adding-or-modifying-availability-replica.md).</span></span>  
  
 <span data-ttu-id="0b497-172">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="0b497-172">**Add**</span></span>  
 <span data-ttu-id="0b497-173">Выберите, чтобы добавить новую вторичную реплику в группу доступности.</span><span class="sxs-lookup"><span data-stu-id="0b497-173">Click to add a secondary replica to the availability group.</span></span>  
  
 <span data-ttu-id="0b497-174">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="0b497-174">**Remove**</span></span>  
 <span data-ttu-id="0b497-175">Нажмите, чтобы удалить вторичную реплику из группы доступности.</span><span class="sxs-lookup"><span data-stu-id="0b497-175">Click to remove a secondary replica from the availability group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b497-176">См. также:</span><span class="sxs-lookup"><span data-stu-id="0b497-176">See Also</span></span>  
 [<span data-ttu-id="0b497-177">Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0b497-177">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
  
  
