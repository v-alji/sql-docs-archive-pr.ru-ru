---
title: Разнородная репликация базы данных | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- heterogeneous database replication, about heterogeneous database replication
- replication [SQL Server], heterogeneous database replication
- heterogeneous database replication
ms.assetid: 3fd983ad-e206-45db-9054-417c9b5bb815
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d8988a425bc9519d43b8100e4cd34418114edae1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736181"
---
# <a name="heterogeneous-database-replication"></a><span data-ttu-id="66cdf-102">разнородная репликация базы данных</span><span class="sxs-lookup"><span data-stu-id="66cdf-102">Heterogeneous Database Replication</span></span>
  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="66cdf-103">поддерживает следующие разнородные сценарии для репликации транзакций и репликации моментальных снимков.</span><span class="sxs-lookup"><span data-stu-id="66cdf-103">supports the following heterogeneous scenarios for transactional and snapshot replication:</span></span>  
  
-   <span data-ttu-id="66cdf-104">Публикация данных из Oracle в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="66cdf-104">Publishing data from Oracle to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="66cdf-105">Публикация данных с подписчиков [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] на подписчики, отличные от[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="66cdf-105">Publishing data from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Subscribers.</span></span>  
  
 <span data-ttu-id="66cdf-106">Разнородная репликация на подписчики, отличные от подписчика SQL Server, устарела.</span><span class="sxs-lookup"><span data-stu-id="66cdf-106">Heterogeneous replication to non-SQL Server subscribers is deprecated.</span></span> <span data-ttu-id="66cdf-107">Публикация Oracle устарела.</span><span class="sxs-lookup"><span data-stu-id="66cdf-107">Oracle Publishing is deprecated.</span></span> <span data-ttu-id="66cdf-108">Для перемещения данных создайте решения с помощью системы отслеживания измененных данных и служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="66cdf-108">To move data, create solutions using change data capture and [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span></span>  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../../includes/ssnotedepfutureavoid-md.md)]  
  
## <a name="publishing-data-from-oracle"></a><span data-ttu-id="66cdf-109">Публикация данных из Oracle</span><span class="sxs-lookup"><span data-stu-id="66cdf-109">Publishing Data from Oracle</span></span>  
 <span data-ttu-id="66cdf-110">Для публикации данных из Oracle можно использовать [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , причем большинство функций и простота их использования такие же, как и в случае репликации моментальных снимков и репликации транзакций [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="66cdf-110">You can use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to publish data from Oracle with most of the same features and ease-of-use as [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] snapshot and transactional replication.</span></span> <span data-ttu-id="66cdf-111">Публикация данных из Oracle идеально подходит для следующих сценариев:</span><span class="sxs-lookup"><span data-stu-id="66cdf-111">Publishing data from Oracle is ideal for the following scenarios:</span></span>  
  
|<span data-ttu-id="66cdf-112">Сценарий</span><span class="sxs-lookup"><span data-stu-id="66cdf-112">Scenario</span></span>|<span data-ttu-id="66cdf-113">Описание</span><span class="sxs-lookup"><span data-stu-id="66cdf-113">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="66cdf-114">Развертывание приложений на платформе[!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework</span><span class="sxs-lookup"><span data-stu-id="66cdf-114">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework application deployments</span></span>|<span data-ttu-id="66cdf-115">Ведите разработку с помощью [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio и [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] при работе с данными, реплицируемыми из базы данных, отличной от[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="66cdf-115">Develop with [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] while operating on data replicated from a non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database.</span></span>|  
|<span data-ttu-id="66cdf-116">Серверы промежуточного хранения данных</span><span class="sxs-lookup"><span data-stu-id="66cdf-116">Data warehousing staging servers</span></span>|<span data-ttu-id="66cdf-117">Поддерживайте синхронизацию промежуточных баз данных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] с базой данных, отличной от[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="66cdf-117">Keep [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] staging databases synchronized with a non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database.</span></span>|  
|<span data-ttu-id="66cdf-118">Переход на [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66cdf-118">Migration to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span></span>|<span data-ttu-id="66cdf-119">Протестируйте приложения в реальном времени совместно с [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] при репликации изменений исходной системы.</span><span class="sxs-lookup"><span data-stu-id="66cdf-119">Test your application in real time against [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] while replicating the source system's changes.</span></span> <span data-ttu-id="66cdf-120">Переключение на [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] при успешном испытании миграции.</span><span class="sxs-lookup"><span data-stu-id="66cdf-120">Switch to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] when satisfied with the migration.</span></span>|  
  
 <span data-ttu-id="66cdf-121">Дополнительные сведения см. в статье [Обзор публикации Oracle](oracle-publishing-overview.md).</span><span class="sxs-lookup"><span data-stu-id="66cdf-121">For more information, see [Oracle Publishing Overview](oracle-publishing-overview.md).</span></span>  
  
## <a name="publishing-data-to-non-sql-server-subscribers"></a><span data-ttu-id="66cdf-122">Публикация данных на подписчиках, отличных от подписчиков SQL Server</span><span class="sxs-lookup"><span data-stu-id="66cdf-122">Publishing Data to Non-SQL Server Subscribers</span></span>  
 <span data-ttu-id="66cdf-123">Следующие базы данных, отличные от баз данных[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , поддерживаются в качестве подписчиков для публикации моментальных снимков и публикации транзакций.</span><span class="sxs-lookup"><span data-stu-id="66cdf-123">The following non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] databases are supported as Subscribers to snapshot and transactional publications:</span></span>  
  
-   <span data-ttu-id="66cdf-124">Oracle для всех платформ с поддержкой Oracle.</span><span class="sxs-lookup"><span data-stu-id="66cdf-124">Oracle for all platforms that Oracle supports.</span></span>  
  
-   <span data-ttu-id="66cdf-125">IBM DB2 для AS400, MVS, Unix, Linux и Windows.</span><span class="sxs-lookup"><span data-stu-id="66cdf-125">IBM DB2 for AS400, MVS, Unix, Linux, and Windows.</span></span>  
  
 <span data-ttu-id="66cdf-126">Дополнительные сведения см. в статье [Non-SQL Server Subscribers](non-sql-server-subscribers.md).</span><span class="sxs-lookup"><span data-stu-id="66cdf-126">For more information, see [Non-SQL Server Subscribers](non-sql-server-subscribers.md).</span></span>  
  
  
