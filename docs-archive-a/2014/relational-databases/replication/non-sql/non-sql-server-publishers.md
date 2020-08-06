---
title: Издатели, отличные от издателей SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- heterogeneous database replication, non-SQL Server Publishers
- non-SQL Server Publishers
- heterogeneous data sources, non-SQL Server Publishers
- Publishers [SQL Server replication], Oracle
ms.assetid: 08a160a6-33be-46b5-bc7b-d53180d8bdf1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f15f07dbf294d697afd385318f3dbf1447c8e2d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655066"
---
# <a name="non-sql-server-publishers"></a><span data-ttu-id="d5c00-102">издатели, отличные от издателей SQL Server</span><span class="sxs-lookup"><span data-stu-id="d5c00-102">Non-SQL Server Publishers</span></span>
  <span data-ttu-id="d5c00-103">Публикация данных из источников, не являющихся [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] источниками, позволяет консолидировать данные в [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d5c00-103">Publishing data from non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sources allows you to consolidate data in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="d5c00-104">может использовать подписку на моментальные снимки или транзакционные данные, публикуемые из базы данных Oracle.</span><span class="sxs-lookup"><span data-stu-id="d5c00-104">can subscribe to snapshot or transactional data published from an Oracle database.</span></span> <span data-ttu-id="d5c00-105">Дополнительные сведения о публикациях из Oracle см. в статье [Обзор публикации Oracle](oracle-publishing-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d5c00-105">For more information about publishing from Oracle, see [Oracle Publishing Overview](oracle-publishing-overview.md).</span></span>  
  
 <span data-ttu-id="d5c00-106">Разнородная репликация на подписчики, отличные от подписчика SQL Server, устарела.</span><span class="sxs-lookup"><span data-stu-id="d5c00-106">Heterogeneous replication to non-SQL Server subscribers is deprecated.</span></span> <span data-ttu-id="d5c00-107">Публикация Oracle устарела.</span><span class="sxs-lookup"><span data-stu-id="d5c00-107">Oracle Publishing is deprecated.</span></span> <span data-ttu-id="d5c00-108">Для перемещения данных создайте решения с помощью системы отслеживания измененных данных и служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d5c00-108">To move data, create solutions using change data capture and [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span></span>  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../../includes/ssnotedepfutureavoid-md.md)]  
  
 <span data-ttu-id="d5c00-109">Публикация из баз данных, отличных от баз данных[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , прекрасно подходит для следующих сценариев:</span><span class="sxs-lookup"><span data-stu-id="d5c00-109">Publishing from non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] databases is ideal for the following scenarios:</span></span>  
  
|<span data-ttu-id="d5c00-110">Сценарий</span><span class="sxs-lookup"><span data-stu-id="d5c00-110">Scenario</span></span>|<span data-ttu-id="d5c00-111">Описание</span><span class="sxs-lookup"><span data-stu-id="d5c00-111">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="d5c00-112">Развертывание приложений на платформе[!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d5c00-112">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework application deployments</span></span>|<span data-ttu-id="d5c00-113">Ведите разработку с помощью [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio и [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] при работе с данными, реплицируемыми из базы данных, отличной от[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d5c00-113">Develop with [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] while operating on data replicated from a non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database.</span></span>|  
|<span data-ttu-id="d5c00-114">Серверы промежуточного хранения данных</span><span class="sxs-lookup"><span data-stu-id="d5c00-114">Data warehousing staging servers</span></span>|<span data-ttu-id="d5c00-115">Поддерживайте синхронизацию промежуточных баз данных [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] с базой данных, отличной от[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d5c00-115">Keep [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] staging databases synchronized with a non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database.</span></span>|  
|<span data-ttu-id="d5c00-116">Переход на [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5c00-116">Migration to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span></span>|<span data-ttu-id="d5c00-117">Протестируйте приложения в реальном времени совместно с [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] при репликации изменений исходной системы.</span><span class="sxs-lookup"><span data-stu-id="d5c00-117">Test your application in real time against [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] while replicating the source system's changes.</span></span> <span data-ttu-id="d5c00-118">Переключение на [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] при успешном испытании миграции.</span><span class="sxs-lookup"><span data-stu-id="d5c00-118">Switch to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] when satisfied with the migration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d5c00-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="d5c00-119">See Also</span></span>  
 [<span data-ttu-id="d5c00-120">Разнородная репликация базы данных</span><span class="sxs-lookup"><span data-stu-id="d5c00-120">Heterogeneous Database Replication</span></span>](heterogeneous-database-replication.md)  
  
  
