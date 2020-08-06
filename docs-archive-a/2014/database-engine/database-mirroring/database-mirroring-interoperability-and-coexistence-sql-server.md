---
title: 'Зеркальное отображение базы данных: взаимодействие и сосуществование (SQL Server) | Документы Майкрософт'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- high availability [SQL Server], interoperability and coexistence
- Database Engine [SQL Server], high availability
ms.assetid: 89fef397-e0cf-4e08-b598-25b8d4170523
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 057392842974c3342fc57d0ec113f8b1bb58b9dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658402"
---
# <a name="database-mirroring-interoperability-and-coexistence-sql-server"></a><span data-ttu-id="a2fb4-102">Зеркальное отображение базы данных. Взаимодействие и сосуществование (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a2fb4-102">Database Mirroring: Interoperability and Coexistence (SQL Server)</span></span>
  <span data-ttu-id="a2fb4-103">Зеркальное отображение базы данных можно использовать со следующими возможностями и компонентами [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="a2fb4-103">Database mirroring can be used with the following features or components of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   [<span data-ttu-id="a2fb4-104">Экземпляры отказоустойчивой кластеризации AlwaysOn (отказоустойчивый кластер SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a2fb4-104">AlwaysOn Failover Cluster Instances (SQL Server Failover Clustering)</span></span>](database-mirroring-and-sql-server-failover-cluster-instances.md)  
  
-   [<span data-ttu-id="a2fb4-105">Отслеживание измененных данных (и отслеживание изменений)</span><span class="sxs-lookup"><span data-stu-id="a2fb4-105">Change data capture (and change tracking)</span></span>](../../relational-databases/track-changes/change-data-capture-and-other-sql-server-features.md)  
  
-   [<span data-ttu-id="a2fb4-106">Моментальные снимки базы данных</span><span class="sxs-lookup"><span data-stu-id="a2fb4-106">Database snapshots</span></span>](../../relational-databases/databases/database-snapshots-sql-server.md)  
  
-   [<span data-ttu-id="a2fb4-107">Полнотекстовые каталоги</span><span class="sxs-lookup"><span data-stu-id="a2fb4-107">Full-text catalogs</span></span>](database-mirroring-and-full-text-catalogs-sql-server.md)  
  
-   [<span data-ttu-id="a2fb4-108">Доставка журналов</span><span class="sxs-lookup"><span data-stu-id="a2fb4-108">Log shipping</span></span>](database-mirroring-and-log-shipping-sql-server.md)  
  
-   [<span data-ttu-id="a2fb4-109">Репликация</span><span class="sxs-lookup"><span data-stu-id="a2fb4-109">Replication</span></span>](database-mirroring-and-replication-sql-server.md)  
  
 <span data-ttu-id="a2fb4-110">Зеркальное отображение базы данных не работает совместно со следующими функциями.</span><span class="sxs-lookup"><span data-stu-id="a2fb4-110">Database mirroring does not interoperate with the following:</span></span>  
  
-   <span data-ttu-id="a2fb4-111">Транзакции между разными базами данных или распределенные транзакции</span><span class="sxs-lookup"><span data-stu-id="a2fb4-111">Cross-database transactions/distributed transactions</span></span>  
  
     <span data-ttu-id="a2fb4-112">Сведения о том, почему не поддерживаются такие транзакции, см. в разделе [Транзакции между базами данных не поддерживаются при зеркальном отображении баз данных или в группах доступности AlwaysOn (SQL Server)](../availability-groups/windows/transactions-always-on-availability-and-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="a2fb4-112">For information about why such transactions are not supported, see [Cross-Database Transactions Not Supported For Database Mirroring or AlwaysOn Availability Groups &#40;SQL Server&#41;](../availability-groups/windows/transactions-always-on-availability-and-database-mirroring.md).</span></span>  
  
-   [!INCLUDE[ssHADR](../../includes/sshadr-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a2fb4-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="a2fb4-113">See Also</span></span>  
 [<span data-ttu-id="a2fb4-114">Зеркальное отображение базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a2fb4-114">Database Mirroring &#40;SQL Server&#41;</span></span>](database-mirroring-sql-server.md)  
  
  
