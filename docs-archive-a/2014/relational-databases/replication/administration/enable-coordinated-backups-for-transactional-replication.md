---
title: Включить скоординированное резервное копирование для репликации транзакций (программирование репликации на языке Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- transactional replication, backup and restore
- sp_replicationdboption
- sync with backup [SQL Server replication]
- coordinated backups [SQL Server replication]
- backups [SQL Server replication], transactional replication
ms.assetid: 73a914ba-8b2d-4f4d-ac1b-db9bac676a30
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 77405cd968fa917c3ccc799eb7d168782443eee9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750783"
---
# <a name="enable-coordinated-backups-for-transactional-replication-replication-transact-sql-programming"></a><span data-ttu-id="80b7b-102">включить скоординированное создание резервных копий для репликации транзакций (программирование репликации на языке Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="80b7b-102">Enable Coordinated Backups for Transactional Replication (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="80b7b-103">При подготовке базы данных к репликации транзакций можно указать, что перед отправкой в базу данных распространителя со всех транзакций должны быть сняты резервные копии.</span><span class="sxs-lookup"><span data-stu-id="80b7b-103">When enabling a database for transactional replication, you can specify that all transactions must be backed up before being delivered to the distribution database.</span></span> <span data-ttu-id="80b7b-104">Кроме того, существует возможность включения в базе данных распространителя функции скоординированного резервного копирования, при которой журнал транзакций в базе данных публикации не подвергается усечению до получения резервных копий транзакций, переданных распространителю.</span><span class="sxs-lookup"><span data-stu-id="80b7b-104">You can also enable coordinated backup on the distribution database so that the transaction log for the publication database is not truncated until transactions that have been propagated to the Distributor have been backed up.</span></span> <span data-ttu-id="80b7b-105">Дополнительные сведения см. в статье [Стратегии резервного копирования и восстановления из копии репликации моментальных снимков и репликации транзакций](strategies-for-backing-up-and-restoring-snapshot-and-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="80b7b-105">For more information, see [Strategies for Backing Up and Restoring Snapshot and Transactional Replication](strategies-for-backing-up-and-restoring-snapshot-and-transactional-replication.md).</span></span>  
  
### <a name="to-enable-coordinated-backups-for-a-database-published-with-transactional-replication"></a><span data-ttu-id="80b7b-106">Включение функции скоординированного резервного копирования для базы данных, опубликованной с использованием репликации транзакций</span><span class="sxs-lookup"><span data-stu-id="80b7b-106">To enable coordinated backups for a database published with transactional replication</span></span>  
  
1.  <span data-ttu-id="80b7b-107">В издателе с помощью функции[DATABASEPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/databasepropertyex-transact-sql) получите значение свойства **IsSyncWithBackup** для базы данных издателя.</span><span class="sxs-lookup"><span data-stu-id="80b7b-107">At the Publisher, use the [DATABASEPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/databasepropertyex-transact-sql) function to return the **IsSyncWithBackup** property of the publication database.</span></span> <span data-ttu-id="80b7b-108">Если функция возвратила значение **1**, то это означает, что скоординированное резервное копирование опубликованной базы данных уже включено.</span><span class="sxs-lookup"><span data-stu-id="80b7b-108">If the function returns **1**, coordinated backups are already enabled for the published database.</span></span>  
  
2.  <span data-ttu-id="80b7b-109">Если функция, выполненная на шаге 1, возвратила значение **0**, выполните хранимую процедуру [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) в базе данных издателя в издателе.</span><span class="sxs-lookup"><span data-stu-id="80b7b-109">If the function in step 1 returns **0**, execute [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) at the Publisher on the publication database.</span></span> <span data-ttu-id="80b7b-110">Укажите значение **sync with backup** в параметре **\@optname** и значение **true** в параметре **\@value**.</span><span class="sxs-lookup"><span data-stu-id="80b7b-110">Specify a value of **sync with backup** for **\@optname**, and **true** for **\@value**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="80b7b-111">Если значение параметра **sync with backup** заменить на **false**, то точка усечения базы данных публикации будет обновлена после запуска агента чтения журнала или по истечении определенного интервала в случае, если агент чтения журнала выполняется постоянно.</span><span class="sxs-lookup"><span data-stu-id="80b7b-111">If you change the **sync with backup** option to **false**, the truncation point of the publication database will be updated after the Log Reader Agent runs, or after an interval if the Log Reader Agent is running continuously.</span></span> <span data-ttu-id="80b7b-112">Максимальное значение интервала управляется параметром агента **-MessageInterval**, значение которого по умолчанию составляет 30 секунд.</span><span class="sxs-lookup"><span data-stu-id="80b7b-112">The maximum interval is controlled by the **-MessageInterval** agent parameter (which has a default of 30 seconds).</span></span>  
  
### <a name="to-enable-coordinated-backups-for-a-distribution-database"></a><span data-ttu-id="80b7b-113">Включение скоординированного резервного копирования базы данных распространителя</span><span class="sxs-lookup"><span data-stu-id="80b7b-113">To enable coordinated backups for a distribution database</span></span>  
  
1.  <span data-ttu-id="80b7b-114">На распространителе с помощью функции[DATABASEPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/databasepropertyex-transact-sql) получите значение свойства **IsSyncWithBackup** для базы данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="80b7b-114">At the Distributor, use the [DATABASEPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/databasepropertyex-transact-sql) function to return the **IsSyncWithBackup** property of the distribution database.</span></span> <span data-ttu-id="80b7b-115">Если функция возвратила значение **1**, то это означает, что скоординированное резервное копирование базы данных распространителя уже включено.</span><span class="sxs-lookup"><span data-stu-id="80b7b-115">If the function returns **1**, coordinated backups are already enabled for the distribution database.</span></span>  
  
2.  <span data-ttu-id="80b7b-116">Если функция, выполненная на шаге 1, возвратила значение **0**, выполните хранимую процедуру [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) в базе данных распространителя на распространителе.</span><span class="sxs-lookup"><span data-stu-id="80b7b-116">If the function in step 1 returns **0**, execute [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) at the Distributor on the distribution database.</span></span> <span data-ttu-id="80b7b-117">Укажите значение **Sync с Backup** для \*\* \@ optname\*\* и значение **true** в качестве \*\* \@ значения\*\*.</span><span class="sxs-lookup"><span data-stu-id="80b7b-117">Specify a value of **sync with backup** for **\@optname** and **true** for **\@value**.</span></span>  
  
### <a name="to-disable-coordinated-backups"></a><span data-ttu-id="80b7b-118">Отключение скоординированного резервного копирования</span><span class="sxs-lookup"><span data-stu-id="80b7b-118">To disable coordinated backups</span></span>  
  
1.  <span data-ttu-id="80b7b-119">В издателе в базе данных публикации или в распространителе в базе данных распространителя выполните хранимую процедуру [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="80b7b-119">At either the Publisher on the publication database or at the Distributor on the distribution database, execute [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql).</span></span> <span data-ttu-id="80b7b-120">Укажите значение **sync with backup** в параметре **\@optname** и значение **false** в параметре **\@value**.</span><span class="sxs-lookup"><span data-stu-id="80b7b-120">Specify a value of **sync with backup** for **\@optname** and **false** for **\@value**.</span></span>  
  
  
