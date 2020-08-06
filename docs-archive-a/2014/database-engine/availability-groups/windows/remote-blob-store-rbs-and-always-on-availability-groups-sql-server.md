---
title: Удаленное хранилище больших двоичных объектов (RBS) и группы доступности AlwaysOn (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
ms.assetid: 01a70258-d4fd-40bc-bc44-c490b5d6c420
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f12a11162d286731b2b510a9051183e6c3025b2a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657321"
---
# <a name="remote-blob-store-rbs-and-alwayson-availability-groups-sql-server"></a><span data-ttu-id="13ab5-102">Удаленное хранилище больших двоичных объектов (RBS) и группы доступности AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="13ab5-102">Remote Blob Store (RBS) and AlwaysOn Availability Groups (SQL Server)</span></span>
  [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)]<span data-ttu-id="13ab5-103">может предоставить решение для обеспечения высокого уровня доступности и аварийного восстановления для [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] объектов BLOB (BLOB) [удаленного хранилища BLOB](../../../relational-databases/blob/remote-blob-store-rbs-sql-server.md) .</span><span class="sxs-lookup"><span data-stu-id="13ab5-103">can provide a high-availability and disaster recovery solution for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)][Remote Blob Store (RBS)](../../../relational-databases/blob/remote-blob-store-rbs-sql-server.md) BLOB objects (blobs).</span></span> [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] <span data-ttu-id="13ab5-104">защищает все метаданные и схемы удаленного хранилища больших двоичных объектов, хранящиеся в базе данных доступности, копируя их на вторичные реплики.</span><span class="sxs-lookup"><span data-stu-id="13ab5-104">protects any RBS metadata and schemas stored in an availability database by replicating them to the secondary replicas.</span></span> <span data-ttu-id="13ab5-105">Эта база данных содержимого SharePoint.</span><span class="sxs-lookup"><span data-stu-id="13ab5-105">This is the SharePoint Content Database.</span></span> <span data-ttu-id="13ab5-106">В целом [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] хранит метаданные этого удаленного хранилища больших двоичных объектов независимо от больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="13ab5-106">Generally speaking, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] stores this RBS metadata independently from the blob.</span></span>  
  
 <span data-ttu-id="13ab5-107">Защита BLOB-данных в RBD зависит от расположения больших двоичных объектов следующим образом.</span><span class="sxs-lookup"><span data-stu-id="13ab5-107">The protection for RBD BLOB data depends on the BLOB Store Location, as follows:</span></span>  
  
|<span data-ttu-id="13ab5-108">Место хранения большого двоичного объекта</span><span class="sxs-lookup"><span data-stu-id="13ab5-108">BLOB Store Location</span></span>|<span data-ttu-id="13ab5-109">Могут ли группы доступности защищать данные этого большого двоичного объекта?</span><span class="sxs-lookup"><span data-stu-id="13ab5-109">Can Availability Groups Protect This BLOB Data?</span></span>|  
|-------------------------|-----------------------------------------------------|  
|<span data-ttu-id="13ab5-110">Та же база данных, содержащая метаданные удаленного хранилища больших двоичных объектов (хранимая с помощью удаленного поставщика FILESTREAM хранилища RBS)</span><span class="sxs-lookup"><span data-stu-id="13ab5-110">The same database that contains the RBS metadata  (stored using a RBS remote FILESTREAM provider)</span></span>|<span data-ttu-id="13ab5-111">Да</span><span class="sxs-lookup"><span data-stu-id="13ab5-111">Yes</span></span>|  
|<span data-ttu-id="13ab5-112">Другая база данных в том же экземпляре [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (хранимая с помощью удаленного поставщика FILESTREAM хранилища RBS)</span><span class="sxs-lookup"><span data-stu-id="13ab5-112">Another database in the same instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (stored using a RBS remote FILESTREAM provider)</span></span>|<span data-ttu-id="13ab5-113">Да</span><span class="sxs-lookup"><span data-stu-id="13ab5-113">Yes</span></span><br /><br /> <span data-ttu-id="13ab5-114">Рекомендуется поместить эту базу данных в ту же группу доступности, что и базу данных, содержащую метаданные удаленного хранилища больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="13ab5-114">We recommend that you put this database in the same availability group as the database that contains the RBS metadata.</span></span>|  
|<span data-ttu-id="13ab5-115">Другая база данных находится на другом экземпляре [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (хранимая с помощью удаленного поставщика FILESTREAM хранилища RBS)</span><span class="sxs-lookup"><span data-stu-id="13ab5-115">Another database in a different instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (stored using a RBS remote FILESTREAM provider)</span></span>|<span data-ttu-id="13ab5-116">Да</span><span class="sxs-lookup"><span data-stu-id="13ab5-116">Yes</span></span><br /><br /> <span data-ttu-id="13ab5-117">Эта база данных должна находиться в отдельной группе доступности.</span><span class="sxs-lookup"><span data-stu-id="13ab5-117">This database must be in a separate availability group.</span></span>|  
|<span data-ttu-id="13ab5-118">Стороннее хранилище больших двоичных объектов</span><span class="sxs-lookup"><span data-stu-id="13ab5-118">A third-party BLOB store</span></span>|<span data-ttu-id="13ab5-119">Нет</span><span class="sxs-lookup"><span data-stu-id="13ab5-119">No</span></span><br /><br /> <span data-ttu-id="13ab5-120">Чтобы защитить эти BLOB-данные, воспользуйтесь механизмами высокого уровня доступности поставщика хранилища больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="13ab5-120">To protect this BLOB data, use the high-availability mechanisms of the BLOB store provider.</span></span>|  
  
##  <a name="limitations"></a><a name="Limitations"></a> <span data-ttu-id="13ab5-121">Ограничения</span><span class="sxs-lookup"><span data-stu-id="13ab5-121">Limitations</span></span>  
  
-   <span data-ttu-id="13ab5-122">Программы обслуживания хранилища RBS должны быть нацелены на первичную реплику.</span><span class="sxs-lookup"><span data-stu-id="13ab5-122">RBS maintainers need to be targeted on the primary replica.</span></span>  
  
##  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="13ab5-123">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="13ab5-123">Recommendations</span></span>  
  
-   <span data-ttu-id="13ab5-124">Используйте прослушивателя группы доступности.</span><span class="sxs-lookup"><span data-stu-id="13ab5-124">Use an availability group listener.</span></span> <span data-ttu-id="13ab5-125">Дополнительные сведения см. в разделе [Прослушиватели групп доступности, возможность подключения клиентов и отработка отказа приложений (SQL Server)](../../listeners-client-connectivity-application-failover.md).</span><span class="sxs-lookup"><span data-stu-id="13ab5-125">For more information, see [Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md).</span></span>  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="13ab5-126">См. также</span><span class="sxs-lookup"><span data-stu-id="13ab5-126">Related Content</span></span>  
  
-   <span data-ttu-id="13ab5-127">[Обслуживание удаленного хранилища больших двоичных объектов](https://msdn.microsoft.com/library/gg316773\(SQL.105\).aspx) (в электронной документации [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="13ab5-127">[Maintaining Remote BLOB Store](https://msdn.microsoft.com/library/gg316773\(SQL.105\).aspx) (in [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] Books Online)</span></span>  
  
-   <span data-ttu-id="13ab5-128">[Запуск программы обслуживания удаленного хранилища больших двоичных объектов](https://blogs.msdn.com/b/sqlrbs/archive/2010/03/19/running-rbs-maintainer.aspx) (блог)</span><span class="sxs-lookup"><span data-stu-id="13ab5-128">[Running RBS Maintainer](https://blogs.msdn.com/b/sqlrbs/archive/2010/03/19/running-rbs-maintainer.aspx) (blog)</span></span>  
  
-   <span data-ttu-id="13ab5-129">[Настройка удаленного хранилища больших двоичных объектов (RBS) с поставщиком FILESTREAM (SharePoint 2010)](https://blogs.msdn.com/b/mvpawardprogram/archive/2012/04/02/configure-remote-blob-storage-rbs-with-the-filestream-provider-sharepoint-2010.aspx) (блог)</span><span class="sxs-lookup"><span data-stu-id="13ab5-129">[Configure Remote BLOB Storage (RBS) with the FILESTREAM provider (SharePoint 2010)](https://blogs.msdn.com/b/mvpawardprogram/archive/2012/04/02/configure-remote-blob-storage-rbs-with-the-filestream-provider-sharepoint-2010.aspx) (blog)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13ab5-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="13ab5-130">See Also</span></span>  
 <span data-ttu-id="13ab5-131">[&#40;SQL Server подключения клиента AlwaysOn&#41;](always-on-client-connectivity-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="13ab5-131">[AlwaysOn Client Connectivity &#40;SQL Server&#41;](always-on-client-connectivity-sql-server.md) </span></span>  
 [<span data-ttu-id="13ab5-132">Удаленное хранилище больших двоичных объектов (RBS) (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="13ab5-132">Remote Blob Store &#40;RBS&#41; &#40;SQL Server&#41;</span></span>](../../../relational-databases/blob/remote-blob-store-rbs-sql-server.md)  
  
  
