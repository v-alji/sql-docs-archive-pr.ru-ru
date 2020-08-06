---
title: Очистка метаданных слияния (программирование репликации на языке Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- metadata [SQL Server replication]
- sp_mergemetadataretentioncleanup
ms.assetid: 9b88baea-b7c6-4e5d-88f9-93d6a0ff0368
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5a2306db72fd3f0098e18ff058796a5498eafcac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736260"
---
# <a name="clean-up-merge-metadata-replication-transact-sql-programming"></a><span data-ttu-id="206cb-102">очистить метаданные слияния (программирование репликации на языке Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="206cb-102">Clean Up Merge Metadata (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="206cb-103">Агент слияния периодически чистит метаданные репликации слиянием в зависимости от заданного срока хранения публикации.</span><span class="sxs-lookup"><span data-stu-id="206cb-103">Merge replication metadata is cleaned up periodically by the Merge Agent based on the retention setting for the publication.</span></span> <span data-ttu-id="206cb-104">Это происходит на издателе и подписчике в системных таблицах [MSmerge_genhistory](/sql/relational-databases/system-tables/msmerge-genhistory-transact-sql), [MSmerge_contents](/sql/relational-databases/system-tables/msmerge-contents-transact-sql), [MSmerge_tombstone](/sql/relational-databases/system-tables/msmerge-tombstone-transact-sql), [MSmerge_past_partition_mappings](/sql/relational-databases/system-tables/msmerge-past-partition-mappings-transact-sql)и [MSmerge_current_partition_mappings](/sql/relational-databases/system-tables/msmerge-current-partition-mappings) .</span><span class="sxs-lookup"><span data-stu-id="206cb-104">This occurs at the Publisher and Subscriber in the [MSmerge_genhistory](/sql/relational-databases/system-tables/msmerge-genhistory-transact-sql), [MSmerge_contents](/sql/relational-databases/system-tables/msmerge-contents-transact-sql), [MSmerge_tombstone](/sql/relational-databases/system-tables/msmerge-tombstone-transact-sql), [MSmerge_past_partition_mappings](/sql/relational-databases/system-tables/msmerge-past-partition-mappings-transact-sql), and [MSmerge_current_partition_mappings](/sql/relational-databases/system-tables/msmerge-current-partition-mappings) system tables.</span></span> <span data-ttu-id="206cb-105">Данные в этих таблицах могут чиститься и программным путем с помощью хранимых процедур репликации.</span><span class="sxs-lookup"><span data-stu-id="206cb-105">You can also programmatically clean up the data in these tables using replication stored procedures.</span></span>  
  
### <a name="to-manually-clean-up-merge-metadata"></a><span data-ttu-id="206cb-106">Очистка метаданных слияния вручную</span><span class="sxs-lookup"><span data-stu-id="206cb-106">To manually clean up merge metadata</span></span>  
  
1.  <span data-ttu-id="206cb-107">В базе данных публикации на издателе выполните хранимую процедуру [sp_mergemetadataretentioncleanup](/sql/relational-databases/system-stored-procedures/sp-mergemetadataretentioncleanup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="206cb-107">At the Publisher on the publication database, execute [sp_mergemetadataretentioncleanup](/sql/relational-databases/system-stored-procedures/sp-mergemetadataretentioncleanup-transact-sql).</span></span>  
  
2.  <span data-ttu-id="206cb-108">Используемых Обратите внимание на количество строк, удаленных на шаге 1 из системных таблиц [MSmerge_genhistory](/sql/relational-databases/system-tables/msmerge-genhistory-transact-sql), [MSmerge_contents](/sql/relational-databases/system-tables/msmerge-contents-transact-sql)и [MSmerge_tombstone](/sql/relational-databases/system-tables/msmerge-tombstone-transact-sql) , возвращаемых соответственно в **@num_genhistory_rows** **@num_contents_rows** **@num_tombstone_rows** выходных параметрах, и.</span><span class="sxs-lookup"><span data-stu-id="206cb-108">(Optional) Note the number of rows removed in step 1 from the [MSmerge_genhistory](/sql/relational-databases/system-tables/msmerge-genhistory-transact-sql), [MSmerge_contents](/sql/relational-databases/system-tables/msmerge-contents-transact-sql), and [MSmerge_tombstone](/sql/relational-databases/system-tables/msmerge-tombstone-transact-sql) system tables, returned respectively in the **@num_genhistory_rows**, **@num_contents_rows**, and **@num_tombstone_rows** output parameters.</span></span>  
  
3.  <span data-ttu-id="206cb-109">Повторите шаги 1 и 2 на подписчике для очистки метаданных в базе данных подписки.</span><span class="sxs-lookup"><span data-stu-id="206cb-109">Repeat steps 1 and 2 at the Subscriber to clean up metadata on the subscription database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="206cb-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="206cb-110">See Also</span></span>  
 [<span data-ttu-id="206cb-111">Окончание срока действия и отключение подписки</span><span class="sxs-lookup"><span data-stu-id="206cb-111">Subscription Expiration and Deactivation</span></span>](../subscription-expiration-and-deactivation.md)  
  
  
