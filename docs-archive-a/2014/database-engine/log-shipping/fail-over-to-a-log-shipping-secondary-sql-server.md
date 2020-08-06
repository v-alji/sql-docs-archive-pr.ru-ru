---
title: Переход на вторичный сервер доставки журналов (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- primary databases [SQL Server]
- secondary data files [SQL Server], manual fail over
- log shipping [SQL Server], failover
- failover [SQL Server], log shipping
ms.assetid: edfe5d59-4287-49c1-96c9-dd56212027bc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 164e2809e4eff5a14ef54124df7c7ca9077793ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734418"
---
# <a name="fail-over-to-a-log-shipping-secondary-sql-server"></a><span data-ttu-id="afeee-102">Переход на вторичный сервер доставки журналов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="afeee-102">Fail Over to a Log Shipping Secondary (SQL Server)</span></span>
  <span data-ttu-id="afeee-103">Переход на вторичный сервер доставки журналов может быть полезен в случаях, когда происходит сбой экземпляра сервера-источника или требуется его обслуживание.</span><span class="sxs-lookup"><span data-stu-id="afeee-103">Failing over to a log shipping secondary is useful if the primary server instance fails or requires maintenance.</span></span>  
  
## <a name="preparing-for-a-controlled-failover"></a><span data-ttu-id="afeee-104">Подготовка к управляемой отработке отказа</span><span class="sxs-lookup"><span data-stu-id="afeee-104">Preparing for a Controlled Failover</span></span>  
 <span data-ttu-id="afeee-105">Обычно базы данных-источник и получатель не синхронизированы, так как обновление первой продолжается и после завершения последнего задания резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="afeee-105">Typically, the primary and secondary databases are unsynchronized, because the primary database continues to be updated after its latest backup job.</span></span> <span data-ttu-id="afeee-106">Также в некоторых случаях последние резервные копии журнала транзакций не скопированы на экземпляры сервера-получателя или же некоторые из этих копий еще не применены к базе данных-получателю.</span><span class="sxs-lookup"><span data-stu-id="afeee-106">Also, in some cases, recent transaction log backups have not been copied to the secondary server instances, or some copied log backups might still not have been applied to the secondary database.</span></span> <span data-ttu-id="afeee-107">Рекомендуется начать с синхронизации всех баз данных-получателей с базой данных-источником, если это возможно.</span><span class="sxs-lookup"><span data-stu-id="afeee-107">We recommend that you begin by synchronizing all of the secondary databases with the primary database, if possible.</span></span>  
  
 <span data-ttu-id="afeee-108">Сведения о заданиях доставки журналов см. в разделе [Сведения о доставке журналов (SQL Server)](about-log-shipping-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="afeee-108">For information about log shipping jobs, see [About Log Shipping &#40;SQL Server&#41;](about-log-shipping-sql-server.md).</span></span>  
  
## <a name="failing-over"></a><span data-ttu-id="afeee-109">Переход на другой ресурс</span><span class="sxs-lookup"><span data-stu-id="afeee-109">Failing Over</span></span>  
 <span data-ttu-id="afeee-110">Для перехода на базу данных-получатель:</span><span class="sxs-lookup"><span data-stu-id="afeee-110">To fail over to a secondary database:</span></span>  
  
1.  <span data-ttu-id="afeee-111">Скопируйте все нескопированные файлы резервных копий из ресурса резервных копий в папку назначения на каждом из серверов-получателей.</span><span class="sxs-lookup"><span data-stu-id="afeee-111">Copy any uncopied backup files from the backup share to the copy destination folder of each secondary server.</span></span>  
  
2.  <span data-ttu-id="afeee-112">Примените все непримененные резервные копии журнала транзакций последовательно к каждой из баз данных-получателей.</span><span class="sxs-lookup"><span data-stu-id="afeee-112">Apply any unapplied transaction log backups in sequence to each secondary database.</span></span> <span data-ttu-id="afeee-113">Дополнительные сведения см. в разделе [Применение резервных копий журналов транзакций (SQL Server)](../../relational-databases/backup-restore/apply-transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="afeee-113">For more information, see [Apply Transaction Log Backups &#40;SQL Server&#41;](../../relational-databases/backup-restore/apply-transaction-log-backups-sql-server.md).</span></span>  
  
3.  <span data-ttu-id="afeee-114">Если база данных-источник доступна, выполните резервное копирование активного журнала транзакций и примените полученную копию к базам данных-получателям.</span><span class="sxs-lookup"><span data-stu-id="afeee-114">If the primary database is accessible, back up the active transaction log and apply the log backup to the secondary databases.</span></span>  
  
     <span data-ttu-id="afeee-115">Если исходный экземпляр сервера-источника не поврежден, выполните резервное копирование заключительного фрагмента журнала транзакций базы данных-источника с параметром WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="afeee-115">If the original primary server instance is not damaged, back up the tail of the transaction log of the primary database using WITH NORECOVERY.</span></span> <span data-ttu-id="afeee-116">Это действие оставляет базу данных в состоянии восстановления из копии и, следовательно, недоступной для пользователей.</span><span class="sxs-lookup"><span data-stu-id="afeee-116">This leaves the database in the restoring state and therefore unavailable to users.</span></span> <span data-ttu-id="afeee-117">Со временем можно будет выполнить накат этой базы данных путем применения резервных копий журнала транзакций из заменяющей базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="afeee-117">Eventually you will be able to roll this database forward by applying transaction log backups from the replacement primary database.</span></span>  
  
     <span data-ttu-id="afeee-118">Дополнительные сведения см. в разделе [Резервные копии журналов транзакций (SQL Server)](../../relational-databases/backup-restore/transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="afeee-118">For more information, see [Transaction Log Backups &#40;SQL Server&#41;](../../relational-databases/backup-restore/transaction-log-backups-sql-server.md).</span></span>  
  
4.  <span data-ttu-id="afeee-119">После синхронизации серверов-получателей можно выполнить переход на любой из них путем восстановления его базы данных-получателя и перенаправления клиентов на этот экземпляр сервера.</span><span class="sxs-lookup"><span data-stu-id="afeee-119">After the secondary servers are synchronized, you can fail over to whichever one you prefer by recovering its secondary database and redirecting clients to that server instance.</span></span> <span data-ttu-id="afeee-120">При восстановлении база данных помещается в согласованное состояние и переводится в режим в сети.</span><span class="sxs-lookup"><span data-stu-id="afeee-120">Recovering puts the database into a consistent state and brings it online.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="afeee-121">При переводе базы данных-получателя в доступный режим следует убедиться, что ее метаданные согласованы с метаданными исходной базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="afeee-121">When you make a secondary database available, you should ensure that its metadata is consistent with the metadata of the original primary database.</span></span> <span data-ttu-id="afeee-122">Дополнительные сведения см. в статье [Управление метаданными при обеспечении доступности базы данных на другом экземпляре сервера (SQL Server)](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md).</span><span class="sxs-lookup"><span data-stu-id="afeee-122">For more information, see [Manage Metadata When Making a Database Available on Another Server Instance &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md).</span></span>  
  
5.  <span data-ttu-id="afeee-123">После восстановления базы данных-получателя можно перенастроить ее для работы в качестве базы данных-источника для других баз данных-получателей.</span><span class="sxs-lookup"><span data-stu-id="afeee-123">After you have recovered a secondary database, you can reconfigure it to act as a primary database for other secondary databases.</span></span>  
  
     <span data-ttu-id="afeee-124">Если нет другой доступной базы данных-получателя, см. раздел [Настройка доставки журналов (SQL Server)](configure-log-shipping-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="afeee-124">If no other secondary database is available, see [Configure Log Shipping &#40;SQL Server&#41;](configure-log-shipping-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="afeee-125">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="afeee-125">Related Tasks</span></span>  
  
-   [<span data-ttu-id="afeee-126">Обмен ролями между сервером-источником и сервером-получателем доставки журналов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="afeee-126">Change Roles Between Primary and Secondary Log Shipping Servers &#40;SQL Server&#41;</span></span>](change-roles-between-primary-and-secondary-log-shipping-servers-sql-server.md)  
  
-   [<span data-ttu-id="afeee-127">Управление именами входа и заданиями после переключения ролей (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="afeee-127">Management of Logins and Jobs After Role Switching &#40;SQL Server&#41;</span></span>](../../sql-server/failover-clusters/management-of-logins-and-jobs-after-role-switching-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="afeee-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="afeee-128">See Also</span></span>  
 <span data-ttu-id="afeee-129">[Таблицы доставки журналов и хранимые процедуры](log-shipping-tables-and-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="afeee-129">[Log Shipping Tables and Stored Procedures](log-shipping-tables-and-stored-procedures.md) </span></span>  
 <span data-ttu-id="afeee-130">[Сведения о доставке журналов (SQL Server)](about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="afeee-130">[About Log Shipping &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span></span>  
 [<span data-ttu-id="afeee-131">Резервные копии заключительного фрагмента журнала (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="afeee-131">Tail-Log Backups &#40;SQL Server&#41;</span></span>](../../relational-databases/backup-restore/tail-log-backups-sql-server.md)  
  
  
