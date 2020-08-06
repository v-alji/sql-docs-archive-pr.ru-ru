---
title: Удаление зеркального отображения базы данных (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], removing
- stopping database mirroring [SQL Server]
- removing database mirroring [SQL Server]
ms.assetid: 40c72091-8f03-4037-8b55-5e95309fe145
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8044fcef9d9f9bfc1fb41c1faa17b76c827da5a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733070"
---
# <a name="removing-database-mirroring-sql-server"></a><span data-ttu-id="5f043-102">Удаление зеркального отображения базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5f043-102">Removing Database Mirroring (SQL Server)</span></span>
  <span data-ttu-id="5f043-103">Владелец базы данных может в любое время и на любом из участников вручную остановить сеанс зеркального отображения базы данных.</span><span class="sxs-lookup"><span data-stu-id="5f043-103">The database owner can manually stop a database mirroring session at any time, at either partner.</span></span>  
  
## <a name="impact-of-removing-mirroring"></a><span data-ttu-id="5f043-104">Последствия удаления зеркального отображения</span><span class="sxs-lookup"><span data-stu-id="5f043-104">Impact of Removing Mirroring</span></span>  
 <span data-ttu-id="5f043-105">При удалении зеркального отображения происходит следующее:</span><span class="sxs-lookup"><span data-stu-id="5f043-105">When mirroring is removed, the following occurs:</span></span>  
  
-   <span data-ttu-id="5f043-106">Прерывается связь между участниками, а также между каждым из участников и следящим сервером, если такая связь существует.</span><span class="sxs-lookup"><span data-stu-id="5f043-106">The relationship between the partners and between each partner and the witness breaks permanently, if any relationship exists.</span></span>  
  
     <span data-ttu-id="5f043-107">Если участники в момент остановки сеанса обмениваются данными друг с другом, их связь немедленно обрывается на обоих компьютерах.</span><span class="sxs-lookup"><span data-stu-id="5f043-107">If the partners are communicating with each other when the session is stopped, their relationship is immediately broken on both computers.</span></span> <span data-ttu-id="5f043-108">Если участники не обмениваются данными (база данных во время остановки находится в состоянии DISCONNECTED), связь немедленно обрывается на участнике, с которого останавливается зеркальное отображение. Когда другой участник пытается восстановить соединение, он обнаруживает, что сеанс зеркального отображения завершен.</span><span class="sxs-lookup"><span data-stu-id="5f043-108">If the partners are not communicating (the database is in a DISCONNECTED state at the time of stopping), the relationship is broken immediately on the partner from which mirroring is stopped; when the other partner tries to reconnect, it discovers that the database mirroring session has ended.</span></span>  
  
-   <span data-ttu-id="5f043-109">Удаляются сведения о сеансе зеркального отображения (в этом заключается отличие от приостановки сеанса).</span><span class="sxs-lookup"><span data-stu-id="5f043-109">Information about the mirroring session is dropped, unlike when pausing a session.</span></span> <span data-ttu-id="5f043-110">Зеркальное отображение удаляется и на основной, и на зеркальной базе данных.</span><span class="sxs-lookup"><span data-stu-id="5f043-110">Mirroring is removed on both the principal database and the mirror database.</span></span> <span data-ttu-id="5f043-111">В представлении **sys.databases** столбец **mirroring_state** и все остальные столбцы зеркального отображения получают значение NULL.</span><span class="sxs-lookup"><span data-stu-id="5f043-111">In **sys.databases**, the **mirroring_state** column and all other mirroring columns are set to NULL.</span></span> <span data-ttu-id="5f043-112">Дополнительные сведения см. в разделе [sys.database_mirroring (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-database-mirroring-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5f043-112">For more information, see [sys.database_mirroring &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-mirroring-transact-sql).</span></span>  
  
-   <span data-ttu-id="5f043-113">На каждом из экземпляров серверов-партнеров остается собственная копия базы данных.</span><span class="sxs-lookup"><span data-stu-id="5f043-113">Each partner server instance is left with a separate copy of the database.</span></span>  
  
-   <span data-ttu-id="5f043-114">Зеркальная база данных остается в состоянии RESTORING (см. столбец **state** в представлении **sys.databases**), так как зеркальная база данных создавалась с помощью RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="5f043-114">The mirror database is left in the RESTORING state (see the **state** column of **sys.databases**), because the mirror database was created by using RESTORE WITH NORECOVERY.</span></span> <span data-ttu-id="5f043-115">В этот момент можно удалить бывшую зеркальную базу данных или восстановить ее с параметром WITH RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="5f043-115">At this point, you can drop the former mirror database or restore it using WITH RECOVERY.</span></span> <span data-ttu-id="5f043-116">Если база данных восстанавливается, она будет иметь расхождения с бывшей основной базой данных, так как восстановление начинает новую вилку восстановления.</span><span class="sxs-lookup"><span data-stu-id="5f043-116">When you recover the database, it will have diverged from the former principal database because the recovery starts a new recovery fork.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5f043-117">Чтобы продолжить зеркальное отображение после остановки сеанса, необходимо установить новый сеанс зеркального отображения базы данных.</span><span class="sxs-lookup"><span data-stu-id="5f043-117">To continue mirroring after stopping a session, you must establish a new database mirroring session.</span></span> <span data-ttu-id="5f043-118">Если резервная копия журнала создана после остановки зеркального отображения, то перед возобновлением зеркального отображения ее необходимо применить к зеркальной базе данных.</span><span class="sxs-lookup"><span data-stu-id="5f043-118">If you create a log backup after stopping mirroring, you must apply it to the mirror database before restarting mirroring.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="5f043-119">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="5f043-119">Related Tasks</span></span>  
 <span data-ttu-id="5f043-120">**Удаление зеркального отображения базы данных**</span><span class="sxs-lookup"><span data-stu-id="5f043-120">**To remove database mirroring**</span></span>  
  
-   [<span data-ttu-id="5f043-121">Удаление зеркального отображения базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5f043-121">Remove Database Mirroring &#40;SQL Server&#41;</span></span>](database-mirroring-sql-server.md)  
  
 <span data-ttu-id="5f043-122">**Запуск зеркального отображения базы данных**</span><span class="sxs-lookup"><span data-stu-id="5f043-122">**To start database mirroring**</span></span>  
  
-   [<span data-ttu-id="5f043-123">Создание сеанса зеркального отображения базы данных с использованием проверки подлинности Windows (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="5f043-123">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="5f043-124">Создание сеанса зеркального отображения базы данных с использованием проверки подлинности Windows (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="5f043-124">Establish a Database Mirroring Session Using Windows Authentication &#40;Transact-SQL&#41;</span></span>](database-mirroring-establish-session-windows-authentication.md)  
  

  
## <a name="see-also"></a><span data-ttu-id="5f043-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="5f043-125">See Also</span></span>  
 <span data-ttu-id="5f043-126">[Зеркальное отображение базы данных ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span><span class="sxs-lookup"><span data-stu-id="5f043-126">[ALTER DATABASE Database Mirroring &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span></span>  
 <span data-ttu-id="5f043-127">[Зеркальное отображение базы данных (SQL Server)](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5f043-127">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="5f043-128">[Приостановка и возобновление зеркального отображения базы данных (SQL Server)](pausing-and-resuming-database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5f043-128">[Pausing and Resuming Database Mirroring &#40;SQL Server&#41;](pausing-and-resuming-database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="5f043-129">sys.databases (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="5f043-129">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
