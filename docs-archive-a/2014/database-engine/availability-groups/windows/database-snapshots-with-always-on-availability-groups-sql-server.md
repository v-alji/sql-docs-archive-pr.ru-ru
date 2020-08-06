---
title: Моментальные снимки базы данных с группы доступности AlwaysOn (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database snapshots [SQL Server], AlwaysOn Availability Groups
- Availability Groups [SQL Server], interoperability
ms.assetid: 7432da1c-ce2f-4cd9-af41-54c97744166b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e1e4307653b5b8150d71019a373ee073d15123f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736794"
---
# <a name="database-snapshots-with-alwayson-availability-groups-sql-server"></a><span data-ttu-id="3aefd-102">Моментальные снимки баз данных для групп доступности AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="3aefd-102">Database Snapshots with AlwaysOn Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="3aefd-103">Моментальный снимок базы данных можно создать в базе данных-источнике или базе данных-получателе в группе доступности.</span><span class="sxs-lookup"><span data-stu-id="3aefd-103">You can create a database snapshot on an primary or secondary database in an availability group.</span></span> <span data-ttu-id="3aefd-104">Ролью реплики должна быть PRIMARY или SECONDARY, она не может находиться в состоянии RESOLVING.</span><span class="sxs-lookup"><span data-stu-id="3aefd-104">The replica role must be either PRIMARY or SECONDARY, not in the RESOLVING state.</span></span>  
  
 <span data-ttu-id="3aefd-105">Для создания моментального снимка рекомендуется, чтобы состояние синхронизации базы данных было SYNCHRONIZING или SYNCHRONIZED.</span><span class="sxs-lookup"><span data-stu-id="3aefd-105">We recommend that the database synchronization state be SYNCHRONIZING or SYNCHRONIZED when you create a database snapshot.</span></span> <span data-ttu-id="3aefd-106">Однако моментальные снимки базы данных могут создаваться и в состоянии синхронизации базы данных NOT SYNCHRONIZING.</span><span class="sxs-lookup"><span data-stu-id="3aefd-106">However, database snapshots can be created when the database synchronization state is NOT SYNCHRONIZING.</span></span>  
  
 <span data-ttu-id="3aefd-107">Моментальный снимок базы данных дополнительной реплики должен продолжить работу в случае, если она находится в состоянии DISCONNECTED от основной реплики.</span><span class="sxs-lookup"><span data-stu-id="3aefd-107">A database snapshot on a secondary replica should continue to work if the replica is DISCONNECTED from the primary replica.</span></span>  
  
 <span data-ttu-id="3aefd-108">Некоторые условия [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] могут вызвать перезапуск как базы данных-источника, так и ее моментальных снимков базы данных, вызвав временное отключение пользователей.</span><span class="sxs-lookup"><span data-stu-id="3aefd-108">Some [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] conditions cause both the source database and its database snapshots to be restarted, temporarily disconnecting users.</span></span> <span data-ttu-id="3aefd-109">Ниже приведены эти условия.</span><span class="sxs-lookup"><span data-stu-id="3aefd-109">These conditions are as follows:</span></span>  
  
-   <span data-ttu-id="3aefd-110">Основная реплика изменяет роли либо из-за того, что текущая основная реплика отключается и снова включается на том же экземпляра сервера, либо из-за того, что группа доступности выполнила переход на другой ресурс.</span><span class="sxs-lookup"><span data-stu-id="3aefd-110">The primary replica changes roles, whether because the current primary replica goes off line and comes back online on the same server instance or because the availability group fails over.</span></span>  
  
-   <span data-ttu-id="3aefd-111">База данных переходит в роль получателя.</span><span class="sxs-lookup"><span data-stu-id="3aefd-111">The database enters the secondary role.</span></span>  
  
 <span data-ttu-id="3aefd-112">Если реплика доступности, на которой размещен моментальный снимок базы данных, выполнила переход на другой ресурс, моментальные снимки базы данных остаются на экземпляре сервера, где они были созданы.</span><span class="sxs-lookup"><span data-stu-id="3aefd-112">If the availability replica that hosts database snapshots is failed over, the database snapshots remain on the server instance where they were created.</span></span> <span data-ttu-id="3aefd-113">Эти снимки будут доступны пользователям и после перехода на другой ресурс. Если для вашей среды важна производительность, рекомендуется создавать моментальные снимки баз данных только в базах данных-получателях, размещенных в дополнительной реплике, настроенной на режим ручного перехода на другой ресурс.</span><span class="sxs-lookup"><span data-stu-id="3aefd-113">Users can continue to use the snapshots after the failover.If performance is a concern in your environment, we recommend that you create database snapshots only on secondary databases that are hosted by a secondary replica that is configured for manual failover mode.</span></span>  <span data-ttu-id="3aefd-114">Если потребуется вручную перевести группу доступности на другой ресурс в данной дополнительной реплике, можно будет создать новый набор моментальных снимков базы данных в другой дополнительной реплике, перенаправить клиентов к новым моментальным снимкам базы данных, а затем удалить все моментальные снимки баз данных, ставших базами данных-источниками.</span><span class="sxs-lookup"><span data-stu-id="3aefd-114">If you ever manually fail over the availability group to this secondary replica, you can create a new set of database snapshots on another secondary replica, redirect clients to the new database snapshots, and drop all of the database snapshots from the now primary databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3aefd-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="3aefd-115">See Also</span></span>  
 <span data-ttu-id="3aefd-116">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3aefd-116">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="3aefd-117">Моментальные снимки базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="3aefd-117">Database Snapshots &#40;SQL Server&#41;</span></span>](../../../relational-databases/databases/database-snapshots-sql-server.md)  
  
  
