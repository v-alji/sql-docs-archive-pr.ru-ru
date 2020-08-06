---
title: Зеркальное отображение баз данных и полнотекстовые каталоги (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], interoperability
- full-text catalogs [SQL Server], database mirroring
- catalogs [SQL Server], database mirroring
ms.assetid: e34072ae-fe8a-462d-bb03-02fa0987f793
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 39929f4bed6edbd1e8ec5c1b72dbe8f7aefeec68
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657285"
---
# <a name="database-mirroring-and-full-text-catalogs-sql-server"></a><span data-ttu-id="dc976-102">Зеркальное отображение баз данных и полнотекстовые каталоги (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="dc976-102">Database Mirroring and Full-Text Catalogs (SQL Server)</span></span>
  <span data-ttu-id="dc976-103">Чтобы создать зеркало базы данных с полнотекстовым каталогом, воспользуйтесь, как обычно, резервным копированием и восстановлением, чтобы создать полную резервную копию основной базы данных, и скопируйте ее на зеркальный сервер.</span><span class="sxs-lookup"><span data-stu-id="dc976-103">To mirror a database that has a full-text catalog, use backup as usual to create a full database backup of the principal database, and then restore the backup to copy the database to the mirror server.</span></span> <span data-ttu-id="dc976-104">Дополнительные сведения см. в статье [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="dc976-104">For more information, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
## <a name="full-text-catalog-and-indexes-before-failover"></a><span data-ttu-id="dc976-105">Полнотекстовой каталог и индексы до отработки отказа</span><span class="sxs-lookup"><span data-stu-id="dc976-105">Full-Text Catalog and Indexes Before Failover</span></span>  
 <span data-ttu-id="dc976-106">В новой зеркальной базе данных полнотекстовый каталог будет таким же, как и во время резервного копирования базы данных.</span><span class="sxs-lookup"><span data-stu-id="dc976-106">In a newly created mirror database, the full-text catalog is the same as when the database was backed up.</span></span> <span data-ttu-id="dc976-107">После включения зеркального отображения базы данных, любые сделанные инструкциями DDL изменения на уровне каталогов (CREATE FULLTEXT CATALOG, ALTER FULLTEXT CATALOG, DROP FULLTEXT CATALOG) протоколируются, отправляются на зеркальный сервер и воспроизводятся в зеркальной базе данных.</span><span class="sxs-lookup"><span data-stu-id="dc976-107">After database mirroring starts, any catalog-level changes that were made by DDL statements (CREATE FULLTEXT CATALOG, ALTER FULLTEXT CATALOG, DROP FULLTEXT CATALOG) are logged and sent to the mirror server to be replayed on the mirror database.</span></span> <span data-ttu-id="dc976-108">Однако изменения на уровне индексов не воспроизводятся в зеркальной базе данных, так как протоколирование этого на основном сервере не ведется.</span><span class="sxs-lookup"><span data-stu-id="dc976-108">However, index-level changes are not reproduced on the mirror database because it is not logged on to the principal server.</span></span> <span data-ttu-id="dc976-109">Таким образом, при изменении содержимого полнотекстового каталога основной базы содержимое полнотекстового каталога зеркальной базы становится несинхронизированным.</span><span class="sxs-lookup"><span data-stu-id="dc976-109">Therefore, as the contents of the full-text catalog change on the principal database, the contents of the full-text catalog on the mirror database are unsynchronized.</span></span>  
  
## <a name="full-text-indexes-after-failover"></a><span data-ttu-id="dc976-110">Полнотекстовые индексы после отработки отказа</span><span class="sxs-lookup"><span data-stu-id="dc976-110">Full-Text Indexes After Failover</span></span>  
 <span data-ttu-id="dc976-111">После отработки отказа полное сканирование полнотекстового индекса нового основного сервера может быть необходимо или полезно в следующих ситуациях.</span><span class="sxs-lookup"><span data-stu-id="dc976-111">After a failover, a full crawl of a full-text index on the new principal server might be required or useful in the following situations:</span></span>  
  
-   <span data-ttu-id="dc976-112">Если выключено слежение за изменениями в полнотекстовом индексе, необходимо запустить полное сканирование индекса при помощи следующей инструкции:</span><span class="sxs-lookup"><span data-stu-id="dc976-112">If change-tracking is turned OFF on a full text index, you must start a full crawl on that index by using the following statement:</span></span>  
  
     <span data-ttu-id="dc976-113">ALTER FULLTEXT INDEX ON *имя_таблицы* START FULL POPULATION</span><span class="sxs-lookup"><span data-stu-id="dc976-113">ALTER FULLTEXT INDEX ON *table_name* START FULL POPULATION</span></span>  
  
-   <span data-ttu-id="dc976-114">Если полнотекстовой индекс настроен для автоматического отслеживания изменений, то происходит автоматическая синхронизация полнотекстового индекса.</span><span class="sxs-lookup"><span data-stu-id="dc976-114">If a full-text index is configured for automatic change tracking, the full-text index is automatically synchronized.</span></span> <span data-ttu-id="dc976-115">Однако синхронизация замедляет полнотекстовую производительность.</span><span class="sxs-lookup"><span data-stu-id="dc976-115">However, synchronization slows full-text performance somewhat.</span></span> <span data-ttu-id="dc976-116">Если производительность становится слишком низкой, можно запустить полное сканирование путем отключения отслеживания изменений, а затем снова установить отслеживание изменений в автоматический режим:</span><span class="sxs-lookup"><span data-stu-id="dc976-116">If performance is too slow, you can cause a full crawl by setting change tracking off and then resetting it to automatic:</span></span>  
  
    -   <span data-ttu-id="dc976-117">Отключение отслеживания изменений:</span><span class="sxs-lookup"><span data-stu-id="dc976-117">To set change tracking off:</span></span>  
  
         <span data-ttu-id="dc976-118">ALTER FULLTEXT INDEX ON *имя_таблицы* SET CHANGE_TRACKING OFF</span><span class="sxs-lookup"><span data-stu-id="dc976-118">ALTER FULLTEXT INDEX ON *table_name* SET CHANGE_TRACKING OFF</span></span>  
  
    -   <span data-ttu-id="dc976-119">Переключение автоматического отслеживания изменений в автоматический режим:</span><span class="sxs-lookup"><span data-stu-id="dc976-119">To set on automatic change tracking to automatic:</span></span>  
  
         <span data-ttu-id="dc976-120">ALTER FULLTEXT INDEX ON *имя_таблицы* SET CHANGE_TRACKING AUTO</span><span class="sxs-lookup"><span data-stu-id="dc976-120">ALTER FULLTEXT INDEX ON *table_name* SET CHANGE_TRACKING AUTO</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dc976-121">Чтобы проверить, включено ли автоматическое отслеживание изменений, можно воспользоваться функцией [OBJECTPROPERTYEX](/sql/t-sql/functions/objectproperty-transact-sql) для запроса свойства **TableFullTextBackgroundUpdateIndexOn** таблицы.</span><span class="sxs-lookup"><span data-stu-id="dc976-121">To see whether auto change tracking is on, you can use the [OBJECTPROPERTYEX](/sql/t-sql/functions/objectproperty-transact-sql) function to query the **TableFullTextBackgroundUpdateIndexOn** property of the table.</span></span>  
  
 <span data-ttu-id="dc976-122">Дополнительные сведения см. в статье [ALTER FULLTEXT INDEX (Transact-SQL)](/sql/t-sql/statements/alter-fulltext-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dc976-122">For more information, see [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dc976-123">Запуск сканирования после отработки отказа работает так же, как и после восстановления.</span><span class="sxs-lookup"><span data-stu-id="dc976-123">Starting a crawl after failover works the same as starting a crawl after a restore.</span></span>  
  
## <a name="after-forcing-service"></a><span data-ttu-id="dc976-124">После принудительного запуска службы</span><span class="sxs-lookup"><span data-stu-id="dc976-124">After Forcing Service</span></span>  
 <span data-ttu-id="dc976-125">После того, как обслуживание принудительно переключилось на зеркальный сервер (с возможностью потери данных), запустите полное сканирование.</span><span class="sxs-lookup"><span data-stu-id="dc976-125">After service is forced to the mirror server (with possible data loss), start a full crawl.</span></span> <span data-ttu-id="dc976-126">Используемый для запуска полного сканирования метод зависит от слежения за изменениями полнотекстового индекса.</span><span class="sxs-lookup"><span data-stu-id="dc976-126">The method to use for starting a full crawl depends on whether the full-text index is change tracked.</span></span> <span data-ttu-id="dc976-127">Дополнительные сведения см. в подразделе «Полнотекстовые индексы после отработки отказа» ранее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="dc976-127">For more information, see "Full-Text Indexes After Failover," earlier in this topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc976-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="dc976-128">See Also</span></span>  
 <span data-ttu-id="dc976-129">[ALTER FULLTEXT INDEX (Transact-SQL)](/sql/t-sql/statements/alter-fulltext-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dc976-129">[ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql) </span></span>  
 <span data-ttu-id="dc976-130">[CREATE FULLTEXT INDEX (Transact-SQL)](/sql/t-sql/statements/create-fulltext-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dc976-130">[CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql) </span></span>  
 <span data-ttu-id="dc976-131">[DROP FULLTEXT INDEX (Transact-SQL)](/sql/t-sql/statements/drop-fulltext-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dc976-131">[DROP FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-fulltext-index-transact-sql) </span></span>  
 <span data-ttu-id="dc976-132">[Зеркальное отображение базы данных (SQL Server)](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="dc976-132">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="dc976-133">Создание резервных копий и восстановление полнотекстовых каталогов и индексов</span><span class="sxs-lookup"><span data-stu-id="dc976-133">Back Up and Restore Full-Text Catalogs and Indexes</span></span>](../../relational-databases/indexes/indexes.md)  
  
  
