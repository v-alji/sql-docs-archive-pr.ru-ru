---
title: MSSQLSERVER_41030 | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41030 (Database Engine error)
ms.assetid: c85341ae-0fbf-42ae-9275-4cfe678238f0
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b137b739d4c1641b88983708df62d2e52fd0eab5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736371"
---
# <a name="mssqlserver_41030"></a><span data-ttu-id="6012d-102">MSSQLSERVER_41030</span><span class="sxs-lookup"><span data-stu-id="6012d-102">MSSQLSERVER_41030</span></span>
    
## <a name="details"></a><span data-ttu-id="6012d-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="6012d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6012d-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="6012d-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="6012d-105">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="6012d-105">Event ID</span></span>|<span data-ttu-id="6012d-106">41030</span><span class="sxs-lookup"><span data-stu-id="6012d-106">41030</span></span>|  
|<span data-ttu-id="6012d-107">Источник события</span><span class="sxs-lookup"><span data-stu-id="6012d-107">Event Source</span></span>|<span data-ttu-id="6012d-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6012d-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6012d-109">Компонент</span><span class="sxs-lookup"><span data-stu-id="6012d-109">Component</span></span>|<span data-ttu-id="6012d-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="6012d-110">SQLEngine</span></span>|  
|<span data-ttu-id="6012d-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="6012d-111">Symbolic Name</span></span>|<span data-ttu-id="6012d-112">OPEN_CLUSTER_SUB_KEY</span><span class="sxs-lookup"><span data-stu-id="6012d-112">OPEN_CLUSTER_SUB_KEY</span></span>|  
|<span data-ttu-id="6012d-113">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="6012d-113">Message Text</span></span>|<span data-ttu-id="6012d-114">Не удалось открыть подраздел реестра отказоустойчивой кластеризации Windows Server «%.\*ls» (код ошибки: %d).</span><span class="sxs-lookup"><span data-stu-id="6012d-114">Failed to open the Windows Server Failover Clustering registry subkey '%.\*ls' (Error code %d).</span></span>  <span data-ttu-id="6012d-115">Родительский ключ — это корневой ключ кластера.</span><span class="sxs-lookup"><span data-stu-id="6012d-115">The parent key is the cluster root key.</span></span>  <span data-ttu-id="6012d-116">Возможно, что служба WSFC не работает или недоступна в текущем состоянии либо указанные аргументы недопустимы.</span><span class="sxs-lookup"><span data-stu-id="6012d-116">The WSFC service may not be running or may not be accessible in its current state, or the specified arguments are invalid.</span></span> <span data-ttu-id="6012d-117">Если соответствующие группы доступности удалены, это ожидаемая ошибка.</span><span class="sxs-lookup"><span data-stu-id="6012d-117">If the corresponding availability group has been dropped, this error is expected.</span></span> <span data-ttu-id="6012d-118">Дополнительные сведения о коде ошибки см. в разделе «Системные коды ошибок» в документации по разработке для Windows.</span><span class="sxs-lookup"><span data-stu-id="6012d-118">For information about this error code, see "System Error Codes" in the Windows Development documentation.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6012d-119">Объяснение</span><span class="sxs-lookup"><span data-stu-id="6012d-119">Explanation</span></span>  
 <span data-ttu-id="6012d-120">Если кластер WSFC разрушается, удаляются все разделы реестра, связанные с [!INCLUDE[ssHADR](../../includes/sshadr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6012d-120">If a WSFC cluster is destroyed, it removes all registry keys related to [!INCLUDE[ssHADR](../../includes/sshadr-md.md)].</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6012d-121">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="6012d-121">User Action</span></span>  
 <span data-ttu-id="6012d-122">После повторного создания кластера WSFC необходимо отключить и повторно включить группы доступности AlwaysOn на каждом узле кластера, на котором для AlwaysOn включен экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6012d-122">After re-creating a WSFC cluster, disable and then re-enable AlwaysOn on every cluster node on which an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is enabled for AlwaysOn.</span></span> <span data-ttu-id="6012d-123">Для этой задачи вы можете использовать диспетчер конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6012d-123">You can use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager for this task.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6012d-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="6012d-124">See Also</span></span>  
 <span data-ttu-id="6012d-125">[Включение и отключение группы доступности AlwaysOn &#40;SQL Server&#41;](../../database-engine/availability-groups/windows/enable-and-disable-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6012d-125">[Enable and Disable AlwaysOn Availability Groups &#40;SQL Server&#41;](../../database-engine/availability-groups/windows/enable-and-disable-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="6012d-126">Отказоустойчивая кластеризация Windows Server (WSFC) с SQL Server</span><span class="sxs-lookup"><span data-stu-id="6012d-126">Windows Server Failover Clustering &#40;WSFC&#41; with SQL Server</span></span>](../../sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server.md)  
  
  
