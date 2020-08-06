---
title: Зеркальное отображение и моментальные снимки баз данных (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], interoperability
- snapshots [SQL Server database snapshots], database mirroring
- database snapshots [SQL Server], database mirroring
ms.assetid: 0bf1be90-7ce4-484c-aaa7-f8a782f57c5f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9df0b74270280bf2315c6a35a80d4b009b75a908
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657287"
---
# <a name="database-mirroring-and-database-snapshots-sql-server"></a><span data-ttu-id="336b0-102">Зеркальное отображение и моментальные снимки баз данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="336b0-102">Database Mirroring and Database Snapshots (SQL Server)</span></span>
  <span data-ttu-id="336b0-103">Преимущество зеркальной базы данных проявляется в возможности использовать ее для разгрузки при формировании отчетов.</span><span class="sxs-lookup"><span data-stu-id="336b0-103">You can take advantage of a mirror database that you are maintaining for availability purposes to offload reporting.</span></span> <span data-ttu-id="336b0-104">Чтобы использовать зеркальную базу данных для выполнения отчетов, можно создавать моментальные снимки базы данных и направлять запросы клиентских соединений к самому позднему снимку.</span><span class="sxs-lookup"><span data-stu-id="336b0-104">To use a mirror database for reporting, you can create a database snapshot on the mirror database and direct client connection requests to the most recent snapshot.</span></span> <span data-ttu-id="336b0-105">Моментальный снимок базы данных представляет собой статичный, доступный только для чтения, согласованный по транзакциям моментальный снимок состояния базы данных-источника на момент создания снимка.</span><span class="sxs-lookup"><span data-stu-id="336b0-105">A database snapshot is a static, read-only, transaction-consistent snapshot of its source database as it existed at the moment of the snapshot's creation.</span></span> <span data-ttu-id="336b0-106">Для создания моментального снимка в зеркальной базе данных, эта база данных должна быть в синхронизированном состоянии зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="336b0-106">To create a database snapshot on a mirror database, the database must be in the synchronized mirroring state.</span></span>  
  
 <span data-ttu-id="336b0-107">В отличие от самой зеркальной базы данных, моментальный снимок базы данных доступен клиентам.</span><span class="sxs-lookup"><span data-stu-id="336b0-107">Unlike the mirror database itself, a database snapshot is accessible to clients.</span></span> <span data-ttu-id="336b0-108">Пока зеркальный сервер соединен с основным сервером, можно направлять запрашивающих отчеты клиентов на подключение к моментальному снимку.</span><span class="sxs-lookup"><span data-stu-id="336b0-108">As long as the mirror server is communicating with the principal server, you can direct reporting clients to connect to a snapshot.</span></span> <span data-ttu-id="336b0-109">Имейте в виду, что так как моментальный снимок базы данных является статичным, новые данные недоступны.</span><span class="sxs-lookup"><span data-stu-id="336b0-109">Note that because a database snapshot is static, new data is not available.</span></span> <span data-ttu-id="336b0-110">Чтобы относительно новые данные были доступными для пользователей, необходимо периодически создавать новый моментальный снимок базы данных, а приложения должны устанавливать входящие клиентские соединения с наиболее поздним снимком.</span><span class="sxs-lookup"><span data-stu-id="336b0-110">To make relatively recent data available to your users, you must create a new database snapshot periodically and have applications direct incoming client connections to the newest snapshot.</span></span>  
  
 <span data-ttu-id="336b0-111">Новый моментальный снимок базы данных почти пустой, но по мере того, как новые страницы базы данных впервые обновляются, снимок растет.</span><span class="sxs-lookup"><span data-stu-id="336b0-111">A new database snapshot is almost empty, but it grows over time as more and more database pages are updated for the first time.</span></span> <span data-ttu-id="336b0-112">Так как каждый моментальный снимок базы данных увеличивается, каждый снимок потребляет столько же ресурсов, как и обычная база данных.</span><span class="sxs-lookup"><span data-stu-id="336b0-112">Because every snapshot on a database grows incrementally in this way, each database snapshot consumes as much resources as a normal database.</span></span> <span data-ttu-id="336b0-113">В зависимости от конфигураций зеркального и основного сервера, избыточное число моментальных снимков базы данных в зеркальной базе данных может уменьшить производительность основной базы данных.</span><span class="sxs-lookup"><span data-stu-id="336b0-113">Depending on the configurations of the mirror server and principal server, having an excessive number of database snapshots on a mirror database might decrease performance on the principal database.</span></span> <span data-ttu-id="336b0-114">Поэтому, рекомендуется хранить лишь несколько относительно новых моментальных снимков зеркальной базы данных.</span><span class="sxs-lookup"><span data-stu-id="336b0-114">Therefore, we recommend that you keep only a few relatively recent snapshots on your mirror databases.</span></span> <span data-ttu-id="336b0-115">Обычно после создания замещающего моментального снимка следует перенаправить входящие запросы на новый моментальный снимок, а после завершения текущих запросов удалить предыдущий снимок.</span><span class="sxs-lookup"><span data-stu-id="336b0-115">Typically, after you create a replacement snapshot, you should redirect incoming queries to the new snapshot and drop the earlier snapshot after any current queries complete.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="336b0-116">Дополнительные сведения о моментальных снимках базы данных см. в разделе [Моментальные снимки базы данных (SQL Server)](../../relational-databases/databases/database-snapshots-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="336b0-116">For more information about database snapshots, see [Database Snapshots &#40;SQL Server&#41;](../../relational-databases/databases/database-snapshots-sql-server.md).</span></span>  
  
 <span data-ttu-id="336b0-117">Если происходит переключение ролей, то база данных и ее моментальные снимки перезапускаются, при этом пользователи временно отключаются.</span><span class="sxs-lookup"><span data-stu-id="336b0-117">If role switching occurs, the database and its snapshots are restarted, temporarily disconnecting users.</span></span> <span data-ttu-id="336b0-118">Впоследствии моментальные снимки базы данных остаются на экземпляре сервера, где они были созданы, который стал новой основной базой данных.</span><span class="sxs-lookup"><span data-stu-id="336b0-118">Afterwards, the database snapshots remain on the server instance where they were created, which has become the new principal database.</span></span> <span data-ttu-id="336b0-119">Пользователям эти снимки будут доступны и после отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="336b0-119">Users can continue to use the snapshots after the failover.</span></span> <span data-ttu-id="336b0-120">Однако при этом появляется дополнительная нагрузка на новый основной сервер.</span><span class="sxs-lookup"><span data-stu-id="336b0-120">However, this places an additional load on the new principal server.</span></span> <span data-ttu-id="336b0-121">Если в среде важна производительность, рекомендуется создавать моментальный снимок новой зеркальной базы данных, когда она становится доступной, и перенаправлять клиентов на новый снимок, а все моментальные снимки бывшей зеркальной базы данных удалять.</span><span class="sxs-lookup"><span data-stu-id="336b0-121">If performance is a concern in your environment, we recommend that you create a snapshot on the new mirror database when it becomes available, redirect clients to the new snapshot, and drop all of the database snapshots from the former mirror database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="336b0-122">В качестве специального решения для отчетов, обладающих достаточной масштабируемостью, можно рассмотреть репликацию.</span><span class="sxs-lookup"><span data-stu-id="336b0-122">For a dedicated reporting solution that scales out well, consider replication.</span></span> <span data-ttu-id="336b0-123">Дополнительные сведения см. в статье [SQL Server Replication](../install-windows/install-sql-server-replication.md).</span><span class="sxs-lookup"><span data-stu-id="336b0-123">For more information, see [SQL Server Replication](../install-windows/install-sql-server-replication.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="336b0-124">Пример</span><span class="sxs-lookup"><span data-stu-id="336b0-124">Example</span></span>  
 <span data-ttu-id="336b0-125">В данном примере создаются моментальные снимки зеркальной базы данных.</span><span class="sxs-lookup"><span data-stu-id="336b0-125">This example creates snapshots on a mirrored database.</span></span>  
  
 <span data-ttu-id="336b0-126">Предполагается, что в сеансе зеркального отображения используется база данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="336b0-126">Assume that the database of a database mirroring session is [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span> <span data-ttu-id="336b0-127">В данном примере создаются три моментальных снимка на зеркальной копии базы данных `AdventureWorks` , которая находится на диске `F` .</span><span class="sxs-lookup"><span data-stu-id="336b0-127">This example creates three database snapshots on the mirror copy of the `AdventureWorks` database, which resides on the `F` drive.</span></span> <span data-ttu-id="336b0-128">Моментальные снимки называются `AdventureWorks_0600`, `AdventureWorks_1200`и `AdventureWorks_1800` , имена означают приблизительное время создания снимков.</span><span class="sxs-lookup"><span data-stu-id="336b0-128">The snapshots are named `AdventureWorks_0600`, `AdventureWorks_1200`, and `AdventureWorks_1800` to identify their approximate creation times.</span></span>  
  
1.  <span data-ttu-id="336b0-129">Создается первый моментальный снимок базы данных на зеркальной копии [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="336b0-129">Create the first database snapshot on the mirror of [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span>  
  
    ```  
    CREATE DATABASE AdventureWorks_0600  
    ON (NAME = 'datafile', FILENAME = 'F:\AdventureWorks_0600.SNP')  
       AS SNAPSHOT OF AdventureWorks2012  
    ```  
  
2.  <span data-ttu-id="336b0-130">Создается второй моментальный снимок базы данных на зеркальной копии [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="336b0-130">Create the second database snapshot on the mirror of [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span> <span data-ttu-id="336b0-131">Пользователи, которые все еще работают со снимком `AdventureWorks_0600` , продолжают его использовать.</span><span class="sxs-lookup"><span data-stu-id="336b0-131">Users who are still using `AdventureWorks_0600` can continue to use it.</span></span>  
  
    ```  
    CREATE DATABASE AdventureWorks_1200  
    ON (NAME = 'datafile', FILENAME = 'F:\AdventureWorks_1200.SNP')  
       AS SNAPSHOT OF AdventureWorks2012  
    ```  
  
     <span data-ttu-id="336b0-132">На этом этапе новые клиентские соединения можно программно направлять на последний моментальный снимок.</span><span class="sxs-lookup"><span data-stu-id="336b0-132">At this point, new client connections can be programmatically directed to the latest snapshot.</span></span>  
  
3.  <span data-ttu-id="336b0-133">Создается третий моментальный снимок на зеркальной копии [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="336b0-133">Create the third snapshot on the mirror [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span> <span data-ttu-id="336b0-134">Пользователи, которые все еще работают со снимками `AdventureWorks_0600` и `AdventureWorks_1200` , могут продолжать их использовать.</span><span class="sxs-lookup"><span data-stu-id="336b0-134">Users who are still using `AdventureWorks_0600` or `AdventureWorks_1200` can continue to use them.</span></span>  
  
    ```  
    CREATE DATABASE AdventureWorks_1800  
    ON (NAME = 'datafile', FILENAME = 'F:\AdventureWorks_1800.SNP')  
        AS SNAPSHOT OF AdventureWorks2012  
    ```  
  
     <span data-ttu-id="336b0-135">На этом этапе новые клиентские соединения можно программно направлять на последний моментальный снимок.</span><span class="sxs-lookup"><span data-stu-id="336b0-135">At this point, new client connections can be programmatically directed to the latest snapshot.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="336b0-136">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="336b0-136">Related Tasks</span></span>  
  
-   [<span data-ttu-id="336b0-137">Создание моментального снимка базы данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="336b0-137">Create a Database Snapshot &#40;Transact-SQL&#41;</span></span>](../../relational-databases/databases/create-a-database-snapshot-transact-sql.md)  
  
-   [<span data-ttu-id="336b0-138">Просмотр моментального снимка базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="336b0-138">View a Database Snapshot &#40;SQL Server&#41;</span></span>](../../relational-databases/databases/view-a-database-snapshot-sql-server.md)  
  
-   [<span data-ttu-id="336b0-139">Удаление моментального снимка базы данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="336b0-139">Drop a Database Snapshot &#40;Transact-SQL&#41;</span></span>](../../relational-databases/databases/drop-a-database-snapshot-transact-sql.md)  

  
## <a name="see-also"></a><span data-ttu-id="336b0-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="336b0-140">See Also</span></span>  
 <span data-ttu-id="336b0-141">[Моментальные снимки базы данных (SQL Server)](../../relational-databases/databases/database-snapshots-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="336b0-141">[Database Snapshots &#40;SQL Server&#41;](../../relational-databases/databases/database-snapshots-sql-server.md) </span></span>  
 [<span data-ttu-id="336b0-142">Подключение клиентов к сеансу зеркального отображения базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="336b0-142">Connect Clients to a Database Mirroring Session &#40;SQL Server&#41;</span></span>](connect-clients-to-a-database-mirroring-session-sql-server.md)  
  
  
