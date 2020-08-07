---
title: Типы репликации | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], types
ms.assetid: c1655e8d-d14c-455a-a7f9-9d2f43e88ab4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5576331004eca44bc32dbde8f430284f75e6eb70
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733845"
---
# <a name="types-of-replication"></a><span data-ttu-id="4ee74-102">Типы репликации</span><span class="sxs-lookup"><span data-stu-id="4ee74-102">Types of Replication</span></span>
  [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="4ee74-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поддерживает следующие типы репликации для использования в распределенных приложениях.</span><span class="sxs-lookup"><span data-stu-id="4ee74-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides the following types of replication for use in distributed applications:</span></span>  
  
-   <span data-ttu-id="4ee74-104">Репликация транзакций.</span><span class="sxs-lookup"><span data-stu-id="4ee74-104">Transactional replication.</span></span> <span data-ttu-id="4ee74-105">Дополнительные сведения см. в статье [Репликация транзакций](transactional/transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="4ee74-105">For more information, see [Transactional Replication](transactional/transactional-replication.md).</span></span>  
  
-   <span data-ttu-id="4ee74-106">Репликация слиянием.</span><span class="sxs-lookup"><span data-stu-id="4ee74-106">Merge replication.</span></span> <span data-ttu-id="4ee74-107">Дополнительные сведения см. в статье [Репликация слиянием](merge/merge-replication.md).</span><span class="sxs-lookup"><span data-stu-id="4ee74-107">For more information, see [Merge Replication](merge/merge-replication.md).</span></span>  
  
-   <span data-ttu-id="4ee74-108">Репликация моментальных снимков.</span><span class="sxs-lookup"><span data-stu-id="4ee74-108">Snapshot replication.</span></span> <span data-ttu-id="4ee74-109">Дополнительные сведения см. в статье [Репликация моментальных снимков](snapshot-replication.md).</span><span class="sxs-lookup"><span data-stu-id="4ee74-109">For more information, see [Snapshot Replication](snapshot-replication.md).</span></span>  
  
 <span data-ttu-id="4ee74-110">Тип репликации, которая выбирается для приложения, зависит от многих факторов, в том числе от физической среды репликации, типа и объема реплицируемых данных, а также от того, обновляются данные на подписчике или нет.</span><span class="sxs-lookup"><span data-stu-id="4ee74-110">The type of replication you choose for an application depends on many factors, including the physical replication environment, the type and quantity of data to be replicated, and whether the data is updated at the Subscriber.</span></span> <span data-ttu-id="4ee74-111">Физическая среда включает в себя количество и расположение компьютеров, участвующих в репликации, и зависит от того, являются эти компьютеры клиентами (рабочие станции, переносные или карманные компьютеры) или серверами.</span><span class="sxs-lookup"><span data-stu-id="4ee74-111">The physical environment includes the number and location of computers involved in replication and whether these computers are clients (workstations, laptops, or handheld devices) or servers.</span></span>  
  
 <span data-ttu-id="4ee74-112">Репликация любого типа обычно начинается с начальной синхронизации опубликованных объектов между издателем и подписчиками.</span><span class="sxs-lookup"><span data-stu-id="4ee74-112">Each type of replication typically begins with an initial synchronization of the published objects between the Publisher and Subscribers.</span></span> <span data-ttu-id="4ee74-113">Эта начальная синхронизация может быть выполнена репликацией при помощи *моментального снимка*, который является копией всех объектов и данных, заданных публикацией.</span><span class="sxs-lookup"><span data-stu-id="4ee74-113">This initial synchronization can be performed by replication with a *snapshot*, which is a copy of all of the objects and data specified by a publication.</span></span> <span data-ttu-id="4ee74-114">После создания моментального снимка он доставляется подписчикам.</span><span class="sxs-lookup"><span data-stu-id="4ee74-114">After the snapshot is created, it is delivered to the Subscribers.</span></span> <span data-ttu-id="4ee74-115">Для некоторых приложений репликация моментальных снимков полностью покрывает их потребности.</span><span class="sxs-lookup"><span data-stu-id="4ee74-115">For some applications, snapshot replication is all that is required.</span></span> <span data-ttu-id="4ee74-116">Для приложений других типов важно, чтобы последующие изменения данных доставлялись подписчику дополнительными порциями с течением времени.</span><span class="sxs-lookup"><span data-stu-id="4ee74-116">For other types of applications, it is important that subsequent data changes flow to the Subscriber incrementally over time.</span></span> <span data-ttu-id="4ee74-117">Для некоторых приложений также нужно, чтобы изменения переносились также от подписчика обратно к издателю.</span><span class="sxs-lookup"><span data-stu-id="4ee74-117">Some applications also require that changes flow from the Subscriber back to the Publisher.</span></span> <span data-ttu-id="4ee74-118">Такие приложения могут использовать как репликацию транзакций, так и репликацию слиянием.</span><span class="sxs-lookup"><span data-stu-id="4ee74-118">Transactional replication and merge replication provide options for these types of applications.</span></span>  
  
 <span data-ttu-id="4ee74-119">В репликации моментальных снимков изменения данных не отслеживаются. При каждом применении моментального снимка он полностью переписывает существующие данные.</span><span class="sxs-lookup"><span data-stu-id="4ee74-119">Data changes are not tracked for snapshot replication; each time a snapshot is applied, it completely overwrites the existing data.</span></span> <span data-ttu-id="4ee74-120">Репликации транзакций отслеживают изменения при помощи журнала транзакций [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , а репликации слиянием отслеживают изменения при помощи триггеров и таблиц метаданных.</span><span class="sxs-lookup"><span data-stu-id="4ee74-120">Transactional replication tracks changes through the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] transaction log, and merge replication tracks changes through triggers and metadata tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ee74-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="4ee74-121">See Also</span></span>  
 [<span data-ttu-id="4ee74-122">Replication Agents Overview</span><span class="sxs-lookup"><span data-stu-id="4ee74-122">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
