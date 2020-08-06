---
title: Другие проблемы при обновлении репликации | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- system tables [SQL Server], replication
- passwords [SQL Server replication]
- versions [SQL Server replication]
- connections [SQL Server replication]
- scripts [SQL Server replication]
- ActiveX controls [SQL Server replication]
ms.assetid: 8a5e74be-4992-4f17-b20c-c3dce8f49329
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: e8ce3f35ead9d3322c636462f682ef391703cfe2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667541"
---
# <a name="other-replication-upgrade-issues"></a><span data-ttu-id="0eb9c-102">Другие проблемы при обновлении репликации</span><span class="sxs-lookup"><span data-stu-id="0eb9c-102">Other Replication Upgrade Issues</span></span>
  <span data-ttu-id="0eb9c-103">В данном разделе описываются некоторые проблемы, которые могут возникнуть при обновлении, но не затронуты помощником по обновлению.</span><span class="sxs-lookup"><span data-stu-id="0eb9c-103">This topic covers a number of upgrade issues that are not reported by Upgrade Advisor.</span></span>  
  
## <a name="versions-supported"></a><span data-ttu-id="0eb9c-104">Поддерживаемые версии</span><span class="sxs-lookup"><span data-stu-id="0eb9c-104">Versions Supported</span></span>  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="0eb9c-105">поддерживает обновление реплицируемых баз данных с предыдущих версий [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0eb9c-105">supports upgrading replicated databases from earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0eb9c-106">При обновлении узла нет необходимости останавливать работу других узлов.</span><span class="sxs-lookup"><span data-stu-id="0eb9c-106">You do not have to stop activity at other nodes while a node is being upgraded.</span></span> <span data-ttu-id="0eb9c-107">Соблюдайте следующие правила, определяющие допустимые версии объектов репликации в топологии.</span><span class="sxs-lookup"><span data-stu-id="0eb9c-107">Ensure that you adhere to the rules regarding which versions are supported in a topology.</span></span>  
  
 <span data-ttu-id="0eb9c-108">При репликации между различными версиями [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] функциональные возможности чаще всего ограничиваются возможностями более ранней из используемых версий.</span><span class="sxs-lookup"><span data-stu-id="0eb9c-108">When you replicate between or among different versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you are usually limited to the functionality of the earliest version that is being used.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0eb9c-109">Формат хранения данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на диске одинаков в 64-разрядной и 32-разрядной среде, поэтому в топологию репликации можно объединить экземпляры серверов, работающие в 32-разрядной и 64-разрядной средах.</span><span class="sxs-lookup"><span data-stu-id="0eb9c-109">Because the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on-disk storage format is the same in the 64-bit and 32-bit environments, a replication topology can combine server instances that run in a 32-bit environment and server instances that run in a 64-bit environment.</span></span>  
  
 <span data-ttu-id="0eb9c-110">Для всех типов репликации номер версии распространителя должен быть не ниже номера версии издателя</span><span class="sxs-lookup"><span data-stu-id="0eb9c-110">For all types of replication, the Distributor version must be no earlier than the Publisher version.</span></span> <span data-ttu-id="0eb9c-111">(часто экземпляр распространителя выступает также в роли издателя).</span><span class="sxs-lookup"><span data-stu-id="0eb9c-111">(Frequently, the Distributor is the same instance as the Publisher.)</span></span>  
  
 <span data-ttu-id="0eb9c-112">Подписчик на репликацию транзакций может иметь любую версию, отличную от версии издателя не более чем на две версии.</span><span class="sxs-lookup"><span data-stu-id="0eb9c-112">For transactional replication, a Subscriber to a transactional publication can be any version within two versions of the Publisher version.</span></span>  
  
 <span data-ttu-id="0eb9c-113">Подписчик на репликацию слиянием может иметь любую версию, но не выше, чем версия издателя.</span><span class="sxs-lookup"><span data-stu-id="0eb9c-113">For merge replication, a Subscriber to a merge publication can be any version no later than the Publisher version.</span></span>  
  
## <a name="merge-replication-batches-changes"></a><span data-ttu-id="0eb9c-114">Пакетные изменения репликации слиянием</span><span class="sxs-lookup"><span data-stu-id="0eb9c-114">Merge Replication Batches Changes</span></span>  
 <span data-ttu-id="0eb9c-115">Изменения, выполненные агентом слияния, объединяются в пакеты с целью улучшения производительности, поэтому в рамках одной инструкции можно вставить, обновить или удалить несколько строк.</span><span class="sxs-lookup"><span data-stu-id="0eb9c-115">Changes that are made by the Merge Agent are batched to improve performance; therefore, more than one row can be inserted, updated, or deleted within a single statement.</span></span> <span data-ttu-id="0eb9c-116">Если в каких-либо из опубликованных таблиц в базах данных подписки или публикации имеются триггеры, убедитесь, что эти триггеры могут обрабатывать многострочную вставку, обновления и удаления.</span><span class="sxs-lookup"><span data-stu-id="0eb9c-116">If any published tables in the publication or subscription databases have triggers, ensure that the triggers can handle multirow inserts, updates, and deletes.</span></span> <span data-ttu-id="0eb9c-117">Дополнительные сведения см. в разделе «Замечания по работе с несколькими строками в триггерах DML» электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0eb9c-117">For more information, see "Multirow Considerations for DML Triggers" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="activex-control-changes"></a><span data-ttu-id="0eb9c-118">Изменения элементов управления ActiveX</span><span class="sxs-lookup"><span data-stu-id="0eb9c-118">ActiveX Control Changes</span></span>  
 <span data-ttu-id="0eb9c-119">Репликация элементов управления ActiveX претерпела следующие изменения.</span><span class="sxs-lookup"><span data-stu-id="0eb9c-119">The following changes have been made for replication ActiveX controls:</span></span>  
  
-   <span data-ttu-id="0eb9c-120">Все элементы управления ActiveX помечаются как небезопасные для выполнения скриптов и инициализации.</span><span class="sxs-lookup"><span data-stu-id="0eb9c-120">All ActiveX controls are marked as unsafe for scripting and initialization.</span></span>  
  
-   <span data-ttu-id="0eb9c-121">Удален элемент управления ActiveX моментальными снимками SQL.</span><span class="sxs-lookup"><span data-stu-id="0eb9c-121">The Snapshot ActiveX control has been dropped.</span></span> <span data-ttu-id="0eb9c-122">Создавать и управлять моментальными снимками можно с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или программно посредством хранимых процедур репликации.</span><span class="sxs-lookup"><span data-stu-id="0eb9c-122">You can create and manage snapshots by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or programmatically by using replication stored procedures.</span></span> <span data-ttu-id="0eb9c-123">Дополнительные сведения см. в подразделах «практическое руководство. Создание и применение исходного моментального снимка ( [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] )» и «практическое руководство. Создание исходного моментального снимка (программирование репликации на языке Transact-SQL)» [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] электронной документации по.</span><span class="sxs-lookup"><span data-stu-id="0eb9c-123">For more information, see the topics "How to: Create and Apply the Initial Snapshot ([!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)])" and "How to: Create the Initial Snapshot (Replication Transact-SQL Programming)" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
-   <span data-ttu-id="0eb9c-124">Элементы управления ActiveX распространителя и слияния стали устаревшими.</span><span class="sxs-lookup"><span data-stu-id="0eb9c-124">The Distribution ActiveX control and Merge ActiveX control have been deprecated.</span></span> <span data-ttu-id="0eb9c-125">Аналогичная функциональность обеспечивается для приложений с управляемым кодом с помощью объектов RMO.</span><span class="sxs-lookup"><span data-stu-id="0eb9c-125">Similar functionality is provided for managed code applications using Replication Management Objects (RMO).</span></span> <span data-ttu-id="0eb9c-126">Дополнительные сведения см. в разделе «Синхронизация подписок (программирование объектов RMO)» электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0eb9c-126">For more information, see "Synchronizing Subscriptions (RMO Programming)" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0eb9c-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="0eb9c-127">See Also</span></span>  
 [<span data-ttu-id="0eb9c-128">Проблемы репликации при обновлении</span><span class="sxs-lookup"><span data-stu-id="0eb9c-128">Replication Upgrade Issues</span></span>](../../../2014/sql-server/install/replication-upgrade-issues.md)  
  
  
