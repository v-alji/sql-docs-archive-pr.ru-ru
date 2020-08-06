---
title: Типы подписчиков | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newpubwizard.subscribertypes.f1
ms.assetid: a70656cb-21c9-4489-be77-ccd396747e3b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4d356377dec1f5307fa136c94ea682c0824479a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668254"
---
# <a name="subscriber-types"></a><span data-ttu-id="38499-102">Типы подписчиков</span><span class="sxs-lookup"><span data-stu-id="38499-102">Subscriber Types</span></span>
  <span data-ttu-id="38499-103">Репликация слиянием позволяет задавать типы подписчиков, которые должна поддерживать публикация.</span><span class="sxs-lookup"><span data-stu-id="38499-103">Merge replication allows you to specify the types of Subscribers that a publication must support.</span></span> <span data-ttu-id="38499-104">Выбор типов подписчиков устанавливает *уровень совместимости публикации*, который определяет, какие возможности будут использоваться публикацией.</span><span class="sxs-lookup"><span data-stu-id="38499-104">Selecting Subscriber types sets the *publication compatibility level*, which determines which features can be used by a publication.</span></span>  
  
 <span data-ttu-id="38499-105">После создания моментального снимка публикации можно повысить ее уровень совместимости (еще более ограничить ее совместимость) на странице **Общие** диалогового окна **Свойства публикации** . Понизить уровень совместимости нельзя.</span><span class="sxs-lookup"><span data-stu-id="38499-105">After a publication snapshot is created, the publication compatibility level can be increased (made more restrictive) on the **General** page of the **Publication Properties** dialog box; the compatibility level cannot be decreased.</span></span>  
  
## <a name="options"></a><span data-ttu-id="38499-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="38499-106">Options</span></span>  
 <span data-ttu-id="38499-107">Выберите тип подписчика, который должна поддерживать эта публикация.</span><span class="sxs-lookup"><span data-stu-id="38499-107">Select each Subscriber type that this publication must support.</span></span>  
  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]  
 <span data-ttu-id="38499-108">Публикация может использовать все возможности.</span><span class="sxs-lookup"><span data-stu-id="38499-108">The publication can use all features.</span></span>  
  
 [!INCLUDE[ssEW](../../includes/ssew-md.md)]  
 <span data-ttu-id="38499-109">Публикации требуется, чтобы файлы моментального снимка имели символьный формат (агент моментальных снимков выполняет это автоматически).</span><span class="sxs-lookup"><span data-stu-id="38499-109">The publication requires snapshot files to be in character format (this is handled automatically by the Snapshot Agent).</span></span> [!INCLUDE[ssEW](../../includes/ssew-md.md)] <span data-ttu-id="38499-110">также имеет ряд ограничений, не связанных с уровнем совместимости.</span><span class="sxs-lookup"><span data-stu-id="38499-110">also has a number of restrictions not related to compatibility level.</span></span>  
  
 <span data-ttu-id="38499-111">Если выбран этот параметр, то для публикации включается параметр веб-синхронизации.</span><span class="sxs-lookup"><span data-stu-id="38499-111">If this option is selected, the Web synchronization option is enabled for the publication.</span></span> <span data-ttu-id="38499-112">Дополнительные сведения о веб-синхронизации см. в разделе [Web Synchronization for Merge Replication](web-synchronization-for-merge-replication.md).</span><span class="sxs-lookup"><span data-stu-id="38499-112">For more information about Web synchronization, see [Web Synchronization for Merge Replication](web-synchronization-for-merge-replication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38499-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="38499-113">See Also</span></span>  
 <span data-ttu-id="38499-114">[Публикация данных и объектов базы данных](publish/publish-data-and-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="38499-114">[Publish Data and Database Objects](publish/publish-data-and-database-objects.md) </span></span>  
 <span data-ttu-id="38499-115">[Create a Publication](publish/create-a-publication.md) </span><span class="sxs-lookup"><span data-stu-id="38499-115">[Create a Publication](publish/create-a-publication.md) </span></span>  
 [<span data-ttu-id="38499-116">Просмотр и изменение свойств издателя и распространителя</span><span class="sxs-lookup"><span data-stu-id="38499-116">View and Modify Distributor and Publisher Properties</span></span>](view-and-modify-distributor-and-publisher-properties.md)   

  
