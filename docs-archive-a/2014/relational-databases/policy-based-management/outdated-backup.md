---
title: Устаревшая резервная копия | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 307a4ad0-675a-4f97-9a3c-cedd61bdfae5
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c6a944b08b15d591a9bbce47a0c0c6a8de3eb54a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665991"
---
# <a name="outdated-backup"></a><span data-ttu-id="7f60b-102">Устаревшая резервная копия</span><span class="sxs-lookup"><span data-stu-id="7f60b-102">Outdated Backup</span></span>
  <span data-ttu-id="7f60b-103">Это правило обеспечивает наличие последних резервных копий.</span><span class="sxs-lookup"><span data-stu-id="7f60b-103">This rule checks that a database has recent backups.</span></span> <span data-ttu-id="7f60b-104">Регулярное создание резервных копий предохраняет базу данных от потери данных и различных сбоев.</span><span class="sxs-lookup"><span data-stu-id="7f60b-104">Scheduling regular backups is important for protecting your databases against data loss from many different failures.</span></span> <span data-ttu-id="7f60b-105">Частоту создания резервных копий разумно выбирать в зависимости от модели восстановления базы данных, частоты ее обновления и потребностей организации в отношении возможной потери данных.</span><span class="sxs-lookup"><span data-stu-id="7f60b-105">The appropriate frequency for backing up data depends on the recovery model of the database, on business requirements about potential data loss, and on how frequently the database is updated.</span></span> <span data-ttu-id="7f60b-106">В часто обновляемой базе данных относительно быстро растет объем рабочих данных, которые не защищены между моментами создания резервных копий.</span><span class="sxs-lookup"><span data-stu-id="7f60b-106">In a frequently updated database, the work-loss exposure increases fairly quickly between backups.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="7f60b-107">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="7f60b-107">Best Practices Recommendations</span></span>  
 <span data-ttu-id="7f60b-108">Рекомендуется достаточно часто создавать резервные копии, чтобы защитить базу данных от потери данных.</span><span class="sxs-lookup"><span data-stu-id="7f60b-108">We recommend that you perform backups frequently enough to protect databases against data loss.</span></span>  
  
 <span data-ttu-id="7f60b-109">Создавать резервные копии данных необходимо и в простой модели восстановления, и в модели полного восстановления.</span><span class="sxs-lookup"><span data-stu-id="7f60b-109">The simple recovery model and full recovery model both require data backups.</span></span> <span data-ttu-id="7f60b-110">В любой модели восстановления полные резервные копии можно дополнять разностными резервными копиями. Это позволяет дополнительно снизить риск потери данных.</span><span class="sxs-lookup"><span data-stu-id="7f60b-110">For either recovery model, you can supplement your full backups with differential backups to efficiently reduce the risk of data loss.</span></span>  
  
 <span data-ttu-id="7f60b-111">Для базы данных, использующей модель полного восстановления, рекомендуется достаточно часто создавать резервные копии журналов.</span><span class="sxs-lookup"><span data-stu-id="7f60b-111">For a database that uses the full recovery model, we recommend that you take frequent log backups.</span></span> <span data-ttu-id="7f60b-112">Для рабочих баз данных, содержащих важные сведения, интервал создания резервных копий журналов обычно колеблется от одной до пятнадцати минут.</span><span class="sxs-lookup"><span data-stu-id="7f60b-112">For a production database that contains very important data, log backups would typically be taken every one to fifteen minutes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7f60b-113">Для создания расписания резервного копирования рекомендуется пользоваться планом обслуживания базы данных.</span><span class="sxs-lookup"><span data-stu-id="7f60b-113">The recommended method for scheduling backups is a database maintenance plan.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="7f60b-114">Дополнительные сведения см. в разделе</span><span class="sxs-lookup"><span data-stu-id="7f60b-114">For More Information</span></span>  
 [<span data-ttu-id="7f60b-115">Резервное копирование и восстановление системных баз данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7f60b-115">Back Up and Restore of System Databases &#40;SQL Server&#41;</span></span>](../backup-restore/back-up-and-restore-of-system-databases-sql-server.md)  
  
 [<span data-ttu-id="7f60b-116">Модели восстановления (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7f60b-116">Recovery Models &#40;SQL Server&#41;</span></span>](../backup-restore/recovery-models-sql-server.md)  
  
 [<span data-ttu-id="7f60b-117">Создание разностной резервной копии базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7f60b-117">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](../backup-restore/create-a-differential-database-backup-sql-server.md)  
  
 [<span data-ttu-id="7f60b-118">Создание полной резервной копии базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7f60b-118">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](../backup-restore/create-a-full-database-backup-sql-server.md)  
  
 [<span data-ttu-id="7f60b-119">Планы обслуживания</span><span class="sxs-lookup"><span data-stu-id="7f60b-119">Maintenance Plans</span></span>](../maintenance-plans/maintenance-plans.md)  
  
 [<span data-ttu-id="7f60b-120">Резервные копии журналов транзакций (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7f60b-120">Transaction Log Backups &#40;SQL Server&#41;</span></span>](../backup-restore/transaction-log-backups-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="7f60b-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="7f60b-121">See Also</span></span>  
 [<span data-ttu-id="7f60b-122">Наблюдение с помощью управления на основе политик и принудительное применение рекомендаций с помощью управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="7f60b-122">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
