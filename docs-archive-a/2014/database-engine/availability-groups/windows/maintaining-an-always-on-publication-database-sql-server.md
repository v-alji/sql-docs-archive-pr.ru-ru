---
title: Обслуживание базы данных публикации AlwaysOn (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], interoperability
- replication [SQL Server], AlwaysOn Availability Groups
ms.assetid: 55b345fe-2eb9-4b04-a900-63d858eec360
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e8f36d29049140b6e5bbdfc1a4e716d41a766a06
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658978"
---
# <a name="maintaining-an-alwayson-publication-database-sql-server"></a><span data-ttu-id="91c83-102">Обслуживание базы данных публикации AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="91c83-102">Maintaining an AlwaysOn Publication Database (SQL Server)</span></span>
  <span data-ttu-id="91c83-103">В этом разделе рассматриваются специальные рекомендации в отношении обслуживания базы данных публикации при использовании групп доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="91c83-103">This topic discusses special considerations for maintaining a publication database when you use AlwaysOn availability groups.</span></span>  
  
 
  
##  <a name="maintaining-a-published-database-in-an-availability-group"></a><a name="MaintainPublDb"></a><span data-ttu-id="91c83-104">Обслуживание опубликованной базы данных в группе доступности</span><span class="sxs-lookup"><span data-stu-id="91c83-104">Maintaining a Published Database in an Availability Group</span></span>  
 <span data-ttu-id="91c83-105">Обслуживание опубликованной базы данных AlwaysOn существенно не отличается от обслуживания стандартной базы данных публикации со следующими оговорками.</span><span class="sxs-lookup"><span data-stu-id="91c83-105">Maintaining an AlwaysOn publication database is basically the same as maintaining a standard publication database, with the following considerations:</span></span>  
  
-   <span data-ttu-id="91c83-106">Администрирование выполняется на узле первичной реплики.</span><span class="sxs-lookup"><span data-stu-id="91c83-106">Administration must occur at the primary replica host.</span></span> <span data-ttu-id="91c83-107">В среде [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]публикации появляются в папке **Локальные публикации** для узла первичной реплики и для вторичных реплик, доступных для чтения.</span><span class="sxs-lookup"><span data-stu-id="91c83-107">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], publications appear under the **Local Publications** folder for the primary replica host and also for readable secondary replicas.</span></span> <span data-ttu-id="91c83-108">После отработки отказа может потребоваться обновление [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] вручную для отражения изменений, если вторичная реплика, ставшая первичной, была недоступна для чтения.</span><span class="sxs-lookup"><span data-stu-id="91c83-108">After failover, you might have to manually refresh [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] for the change to be reflected if the secondary that was promoted to primary was not readable.</span></span>  
  
-   <span data-ttu-id="91c83-109">Монитор репликации всегда отображает сведения публикации для первоначального издателя.</span><span class="sxs-lookup"><span data-stu-id="91c83-109">Replication Monitor always displays publication information under the original publisher.</span></span> <span data-ttu-id="91c83-110">Однако эти сведения можно просмотреть в мониторе репликации из любой реплики, добавив первоначального издателя в качестве сервера.</span><span class="sxs-lookup"><span data-stu-id="91c83-110">However, this information can be viewed in Replication Monitor from any replica by adding the original publisher as a server.</span></span>  
  
-   <span data-ttu-id="91c83-111">Если для администрирования репликации на текущей первичной реплике используются хранимые процедуры или объекты RMO, то для случаев, когда указывается имя издателя, необходимо указать имя экземпляра, на котором база данных активирована для репликации (первоначальный издатель).</span><span class="sxs-lookup"><span data-stu-id="91c83-111">When using stored procedures or Replication Management Objects (RMO) to administer replication at the current primary, for cases in which you specify the Publisher name, you must specify the name of the instance on which the database was enabled for replication (the original publisher).</span></span> <span data-ttu-id="91c83-112">Чтобы определить соответствующее имя, воспользуйтесь функцией `PUBLISHINGSERVERNAME`.</span><span class="sxs-lookup"><span data-stu-id="91c83-112">To determine the appropriate name, use the `PUBLISHINGSERVERNAME` function.</span></span> <span data-ttu-id="91c83-113">Если публикуемая база данных присоединяется к группе доступности, метаданные репликации, хранимые в репликах базы данных-получателя, идентичны метаданным в первичной базе данных.</span><span class="sxs-lookup"><span data-stu-id="91c83-113">When a publishing database joins an availability group, the replication metadata stored in the secondary database replicas is identical to that at the primary.</span></span> <span data-ttu-id="91c83-114">Поэтому для баз данных публикации, активированных для репликации в первичной базе данных, имя экземпляра издателя, хранимое в системных таблицах во вторичной базе данных, является именем первичной, а не вторичной базы данных.</span><span class="sxs-lookup"><span data-stu-id="91c83-114">Consequently, for publication databases enabled for replication at the primary, the publisher instance name stored in system tables at the secondary is the name of the primary, not the secondary.</span></span> <span data-ttu-id="91c83-115">Это отрицательно повлияет на настройку и обслуживание репликации, если в результате сбоя база данных публикации перейдет на вторичный сервер.</span><span class="sxs-lookup"><span data-stu-id="91c83-115">This affects replication configuration and maintenance if the publication database fails over to a secondary.</span></span> <span data-ttu-id="91c83-116">Например, если вы настраиваете репликацию с хранимыми процедурами на вторичном этапе после отработки отказа и хотите получить подписку по запросу на базу данных публикации, которая была включена на другой реплике, необходимо указать имя исходного издателя вместо текущего издателя в качестве *@publisher* параметра `sp_addpullsubscription` или `sp_addmergepulllsubscription` .</span><span class="sxs-lookup"><span data-stu-id="91c83-116">For example, if you are configuring replication with stored procedures at a secondary after failover, and you want a pull subscription to a publication database that was enabled at a different replica, you must specify the name of the original publisher instead of the current publisher as the *@publisher* parameter of `sp_addpullsubscription` or `sp_addmergepulllsubscription`.</span></span> <span data-ttu-id="91c83-117">Тем не менее, если база данных публикации после отработки отказа включена, именем экземпляра издателя, которое хранится в системных таблицах, является имя текущего первичного узла.</span><span class="sxs-lookup"><span data-stu-id="91c83-117">However, if you enable a publication database after failover, the publisher instance name stored in the system tables is the name of the current primary host.</span></span> <span data-ttu-id="91c83-118">В этом случае для параметра будет использоваться имя узла текущей первичной реплики *@publisher* .</span><span class="sxs-lookup"><span data-stu-id="91c83-118">In this case, you would use the host name of the current primary replica for the *@publisher* parameter.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="91c83-119">Для некоторых процедур, таких как `sp_addpublication` , *@publisher* параметр поддерживается только для издателей, которые не являются экземплярами [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] . в таких случаях это не относится к [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="91c83-119">For some procedures, such as `sp_addpublication`, the *@publisher* parameter is supported only for publishers that are not instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]; in these cases, it is not relevant for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] AlwaysOn.</span></span>  
  
-   <span data-ttu-id="91c83-120">Для синхронизации подписки в среде [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] после отработки отказа необходимо синхронизировать подписки по запросу от подписчика и синхронизировать принудительные подписки от активного издателя.</span><span class="sxs-lookup"><span data-stu-id="91c83-120">To synchronize a subscription in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] after a failover, synchronize pull subscriptions from the subscriber and synchronize push subscriptions from the active publisher.</span></span>  
  
##  <a name="removing-a-published-database-from-an-availability-group"></a><a name="RemovePublDb"></a> <span data-ttu-id="91c83-121">Удаление опубликованной базы данных из группы доступности</span><span class="sxs-lookup"><span data-stu-id="91c83-121">Removing a Published Database from an Availability Group</span></span>  
 <span data-ttu-id="91c83-122">При удалении опубликованной базы данных из группы доступности или удалении группы доступности, содержащей опубликованную базу данных, необходимо учитывать следующее.</span><span class="sxs-lookup"><span data-stu-id="91c83-122">Consider the following issues if a published database is removed from an availability group, or if an availability group that has a published member database is dropped.</span></span>  
  
-   <span data-ttu-id="91c83-123">Если база данных публикации на исходном издателе удаляется из первичной реплики группы доступности, необходимо запустить `sp_redirect_publisher` без указания значения для параметра, *@redirected_publisher* чтобы удалить перенаправление для пары "издатель — база данных".</span><span class="sxs-lookup"><span data-stu-id="91c83-123">If the publication database at the original publisher is removed from an availability group primary replica, you must run `sp_redirect_publisher` without specifying a value for the *@redirected_publisher* parameter in order to remove the redirection for the publisher/database pair.</span></span>  
  
    ```  
    EXEC sys.sp_redirect_publisher   
        @original_publisher = 'MyPublisher',  
        @published_database = 'MyPublishedDB';  
    ```  
  
     <span data-ttu-id="91c83-124">База данных останется в состоянии восстановления по журналу на первичном сервере и должна быть восстановлена.</span><span class="sxs-lookup"><span data-stu-id="91c83-124">The database will be left in the recovering state at the primary and must be restored.</span></span> <span data-ttu-id="91c83-125">После этого репликация должна работать без изменений для первоначального издателя.</span><span class="sxs-lookup"><span data-stu-id="91c83-125">Once you do this, replication should work unchanged against the original Publisher.</span></span>  
  
-   <span data-ttu-id="91c83-126">Если база данных публикации переходит после отказа с первоначального издателя на реплику и база данных удаляется из первичной реплики группы доступности, воспользуйтесь хранимой процедурой `sp_redirect_publisher` для явного перенаправления первоначального издателя к новому издателю.</span><span class="sxs-lookup"><span data-stu-id="91c83-126">If the publication database fails over from the original publisher to a replica and the database is removed from the availability group primary replica, use the stored procedure `sp_redirect_publisher` to explicitly redirect the original publisher to the new publisher.</span></span> <span data-ttu-id="91c83-127">База данных останется в состоянии восстановления по журналу и подлежит восстановлению.</span><span class="sxs-lookup"><span data-stu-id="91c83-127">The database will be left in the recovering state and must be restored.</span></span> <span data-ttu-id="91c83-128">После этого репликация должна продолжить работу так же, как это было в группе доступности.</span><span class="sxs-lookup"><span data-stu-id="91c83-128">Once you do this, replication should continue to work as it did under the availability group.</span></span>  
  
    ```  
    EXEC sys.sp_redirect_publisher   
        @original_publisher = 'MyPublisher',  
        @published_database = 'MyPublishedDB',  
        @redirected_publisher = 'MyNewPublisher';  
    ```  
  
     <span data-ttu-id="91c83-129">Не удаляйте удаленный сервер первоначального издателя из распространителя, даже если уже нет доступа к серверу.</span><span class="sxs-lookup"><span data-stu-id="91c83-129">Do not remove the remote server for the original publisher from the distributor, even if the server can no longer be accessed.</span></span> <span data-ttu-id="91c83-130">Метаданные сервера первоначального издателя нужны распространителю для обработки запросов к метаданным публикации.</span><span class="sxs-lookup"><span data-stu-id="91c83-130">The server metadata for the original publisher is needed at the distributor to satisfy publication metadata queries.</span></span>  
  
-   <span data-ttu-id="91c83-131">Если удаляется вся группа доступности, поведение в отношении реплицированной базы данных-члена остается таким же, как и при удалении опубликованной базы данных из группы доступности.</span><span class="sxs-lookup"><span data-stu-id="91c83-131">If a complete availability group is removed, the behavior with regard to a member replicated database is the same as when a published database is removed from an availability group.</span></span> <span data-ttu-id="91c83-132">Репликацию можно возобновить с последнего первичного сервера, как только база данных будет восстановлена, а перенаправление изменено.</span><span class="sxs-lookup"><span data-stu-id="91c83-132">Replication can be resumed from the last primary as soon as the database has been restored and the redirection has been modified.</span></span> <span data-ttu-id="91c83-133">Если база данных восстанавливается для первоначального издателя, перенаправление должно быть удалено.</span><span class="sxs-lookup"><span data-stu-id="91c83-133">If the database is restored at its original publisher, redirection should be removed.</span></span> <span data-ttu-id="91c83-134">Если база данных восстанавливается на другой узел, необходимо явным образом осуществить перенаправление на новый узел.</span><span class="sxs-lookup"><span data-stu-id="91c83-134">If the database is restored at a different host, redirection should be explicitly directed to the new host.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="91c83-135">Если удаляется группа доступности, содержащая опубликованные базы данных, или если опубликованная база данных удаляется из группы доступности, все копии опубликованных баз данных остаются в состоянии восстановления.</span><span class="sxs-lookup"><span data-stu-id="91c83-135">When an availability group is removed that has published member databases, or a published database is removed from an availability group, all copies of the published databases will be left in the recovering state.</span></span> <span data-ttu-id="91c83-136">После восстановления каждая база данных становится опубликованной.</span><span class="sxs-lookup"><span data-stu-id="91c83-136">If restored, each will appear as a published database.</span></span> <span data-ttu-id="91c83-137">Только одна копия может быть сохранена с метаданными публикации.</span><span class="sxs-lookup"><span data-stu-id="91c83-137">Only one copy should be retained with publication metadata.</span></span> <span data-ttu-id="91c83-138">Чтобы отключить репликацию для копии опубликованной базы данных, сначала удалите все подписки и публикации из базы данных.</span><span class="sxs-lookup"><span data-stu-id="91c83-138">To disable replication for a published database copy, first remove all subscriptions and publications from the database.</span></span>  
  
     <span data-ttu-id="91c83-139">Выполните `sp_dropsubscription`, чтобы удалить подписки на публикацию.</span><span class="sxs-lookup"><span data-stu-id="91c83-139">Run `sp_dropsubscription` to remove publication subscriptions.</span></span> <span data-ttu-id="91c83-140">Убедитесь, что для параметра задано значение *@ignore_distributributor* 1, чтобы сохранить метаданные для активной базы данных публикации на распространителе.</span><span class="sxs-lookup"><span data-stu-id="91c83-140">Make sure to set the parameter *@ignore_distributributor* to 1 to preserve the metadata for the active publishing database at the distributor.</span></span>  
  
    ```  
    USE MyDBName;  
    GO  
  
    EXEC sys.sp_dropsubscription   
        @subscriber = 'MySubscriber',  
        @publication = 'MyPublication',  
        @article = 'all',  
        @ignore_distributor = 1;  
    ```  
  
     <span data-ttu-id="91c83-141">Выполните `sp_droppublication`, чтобы удалить все публикации.</span><span class="sxs-lookup"><span data-stu-id="91c83-141">Run `sp_droppublication` to remove all publications.</span></span> <span data-ttu-id="91c83-142">Опять же, присвойте параметру значение *@ignore_distributor* 1, чтобы сохранить метаданные для активной базы данных публикации на распространителе.</span><span class="sxs-lookup"><span data-stu-id="91c83-142">Again, set the parameter *@ignore_distributor* to 1 to preserve the metadata for the active publishing database at the distributor.</span></span>  
  
    ```  
    EXEC sys.sp_droppublication   
        @publication = 'MyPublication',  
        @ignore_distributor = 1;  
    ```  
  
     <span data-ttu-id="91c83-143">Выполните `sp_replicationdboption`, чтобы отключить репликацию для базы данных.</span><span class="sxs-lookup"><span data-stu-id="91c83-143">Run `sp_replicationdboption` to disable replication for the database.</span></span>  
  
    ```  
    EXEC sys.sp_replicationdboption  
        @dbname = 'MyDBName',  
        @optname = 'publish',  
        @value = 'false';  
    ```  
  
     <span data-ttu-id="91c83-144">На этом этапе копию опубликованной базы данных можно сохранить или удалить.</span><span class="sxs-lookup"><span data-stu-id="91c83-144">At this point, the copy of the published database can be retained or dropped.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="91c83-145">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="91c83-145">Related Tasks</span></span>  
  
-   [<span data-ttu-id="91c83-146">Настройка репликации для групп доступности AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="91c83-146">Configure Replication for AlwaysOn Availability Groups (SQL Server)</span></span>](always-on-availability-groups-sql-server.md)  
  
-   [<span data-ttu-id="91c83-147">Репликация, Отслеживание изменений, система отслеживания измененных данных и группы доступности AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="91c83-147">Replication, Change Tracking, Change Data Capture, and AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](replicate-track-change-data-capture-always-on-availability.md)  
  
-   [<span data-ttu-id="91c83-148">Вопросы и ответы об администрировании репликации</span><span class="sxs-lookup"><span data-stu-id="91c83-148">Replication Administration FAQ</span></span>](../../../relational-databases/replication/administration/frequently-asked-questions-for-replication-administrators.md)  
  
-   [<span data-ttu-id="91c83-149">Подписчики репликации и группы доступности AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="91c83-149">Replication Subscribers and AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](replication-subscribers-and-always-on-availability-groups-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="91c83-150">См. также:</span><span class="sxs-lookup"><span data-stu-id="91c83-150">See Also</span></span>  
 <span data-ttu-id="91c83-151">[Предварительные требования, ограничения и рекомендации для группы доступности AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="91c83-151">[Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span></span>  
 <span data-ttu-id="91c83-152">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="91c83-152">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="91c83-153">[Группы доступности AlwaysOn: взаимодействие (SQL Server)](always-on-availability-groups-interoperability-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="91c83-153">[AlwaysOn Availability Groups: Interoperability (SQL Server)](always-on-availability-groups-interoperability-sql-server.md) </span></span>  
 [<span data-ttu-id="91c83-154">Репликация SQL Server</span><span class="sxs-lookup"><span data-stu-id="91c83-154">SQL Server Replication</span></span>](../../../relational-databases/replication/sql-server-replication.md)  
  
  
