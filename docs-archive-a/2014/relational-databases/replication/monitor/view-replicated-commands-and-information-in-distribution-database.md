---
title: Просмотр реплицированных команд и другой информации в базе данных распространителя (программирование репликации на языке Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- sp_browsereplcmds
- transactional replication, monitoring
- distribution databases [SQL Server replication], viewing replicated commands
- viewing replicated commands
ms.assetid: 9c20acec-8fab-4483-b9c1-dfe3768f85dd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: fb5850277d685f2ecf6471fa4bf9814579b2843e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750704"
---
# <a name="view-replicated-commands-and-other-information-in-the-distribution-database-replication-transact-sql-programming"></a><span data-ttu-id="09614-102">Просмотр реплицированных команд и другой информации в базе данных распространителя (программирование репликации на языке Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="09614-102">View Replicated Commands and Other Information in the Distribution Database (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="09614-103">Если используется репликация транзакций, команды транзакций хранятся в базе данных распространителя, пока агент распространителя не передаст их всем подписчикам или пока агент распространителя на подписчике не получит изменения по запросу.</span><span class="sxs-lookup"><span data-stu-id="09614-103">When using transactional replication, transaction commands are stored in the distribution database until the Distribution Agent propagates them to all Subscribers or a Distribution Agent at the Subscriber pulls the changes.</span></span> <span data-ttu-id="09614-104">Эти ждущие команды в базе данных распространителя можно просматривать программным способом с помощью хранимых процедур репликации.</span><span class="sxs-lookup"><span data-stu-id="09614-104">These pending commands in the distribution database can be viewed programmatically using replication stored procedures.</span></span> <span data-ttu-id="09614-105">Дополнительные сведения см. в статье [Хранимые процедуры репликации (Transact-SQL)](/sql/relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="09614-105">For more information, see [Replication Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql).</span></span>  
  
### <a name="to-view-replicated-commands-from-all-transactional-publications-in-the-distribution-database"></a><span data-ttu-id="09614-106">Просмотр реплицируемых команд из всех публикаций транзакций в базе данных распространителя</span><span class="sxs-lookup"><span data-stu-id="09614-106">To view replicated commands from all transactional publications in the distribution database</span></span>  
  
1.  <span data-ttu-id="09614-107">В базе данных на распространителе выполните процедуру [sp_browsereplcmds](/sql/relational-databases/system-stored-procedures/sp-browsemergesnapshotfolder-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="09614-107">At the Distributor on the distribution database, execute [sp_browsereplcmds](/sql/relational-databases/system-stored-procedures/sp-browsemergesnapshotfolder-transact-sql).</span></span>  
  
### <a name="to-view-replicated-commands-in-the-distribution-database-from-a-specific-article-or-from-a-specific-database-published-using-transactional-replication"></a><span data-ttu-id="09614-108">Просмотр реплицируемых команд в базе данных распространителя из определенной статьи или определенной базы данных, опубликованной с помощью репликации транзакций</span><span class="sxs-lookup"><span data-stu-id="09614-108">To view replicated commands in the distribution database from a specific article or from a specific database published using transactional replication</span></span>  
  
1.  <span data-ttu-id="09614-109">В базе данных публикации на издателе выполните процедуру [sp_helparticle](/sql/relational-databases/system-stored-procedures/sp-helparticle-transact-sql)(необязательно).</span><span class="sxs-lookup"><span data-stu-id="09614-109">(Optional) At the Publisher on the publication database, execute [sp_helparticle](/sql/relational-databases/system-stored-procedures/sp-helparticle-transact-sql).</span></span> <span data-ttu-id="09614-110">Укажите \*\* \@ публикацию\*\* и \*\* \@ статью\*\*.</span><span class="sxs-lookup"><span data-stu-id="09614-110">Specify **\@publication** and **\@article**.</span></span> <span data-ttu-id="09614-111">Запомните значение параметра **article id** в результирующем наборе.</span><span class="sxs-lookup"><span data-stu-id="09614-111">Note the value of **article id** in the result set.</span></span>  
  
2.  <span data-ttu-id="09614-112">В базе данных на распространителе выполните процедуру [sp_browsereplcmds](/sql/relational-databases/system-stored-procedures/sp-browsemergesnapshotfolder-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="09614-112">At the Distributor on the distribution database, execute [sp_browsereplcmds](/sql/relational-databases/system-stored-procedures/sp-browsemergesnapshotfolder-transact-sql).</span></span> <span data-ttu-id="09614-113">Используемых Укажите идентификатор статьи из шага 2 для \*\* \@ article_id\*\*.</span><span class="sxs-lookup"><span data-stu-id="09614-113">(Optional) Specify the article ID from step 2 for **\@article_id**.</span></span> <span data-ttu-id="09614-114">Используемых Укажите идентификатор базы данных публикации для \*\* \@ publisher_database_id\*\*, которую можно получить из столбца **database_id** представления каталога [sys. databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="09614-114">(Optional) Specify the ID of the publication database for **\@publisher_database_id**, which can be obtained from the **database_id** column in the [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) catalog view.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09614-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="09614-115">See Also</span></span>  
 [<span data-ttu-id="09614-116">Наблюдение за репликацией программным образом</span><span class="sxs-lookup"><span data-stu-id="09614-116">Programmatically Monitor Replication</span></span>](../monitoring-replication.md)  
  
  
