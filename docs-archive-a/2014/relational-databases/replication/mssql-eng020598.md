---
title: MSSQL_ENG020598 | Документация Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG020598 error
ms.assetid: 1c3032f2-23d1-4ead-94ee-16ac4d75cd0c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8cef26001c353dea94ec9b658dfb38285231bc20
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730510"
---
# <a name="mssql_eng020598"></a><span data-ttu-id="72308-102">MSSQL_ENG020598</span><span class="sxs-lookup"><span data-stu-id="72308-102">MSSQL_ENG020598</span></span>
    
## <a name="message-details"></a><span data-ttu-id="72308-103">Сведения о сообщении</span><span class="sxs-lookup"><span data-stu-id="72308-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="72308-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="72308-104">Product Name</span></span>|<span data-ttu-id="72308-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="72308-105">SQL Server</span></span>|  
|<span data-ttu-id="72308-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="72308-106">Event ID</span></span>|<span data-ttu-id="72308-107">20598</span><span class="sxs-lookup"><span data-stu-id="72308-107">20598</span></span>|  
|<span data-ttu-id="72308-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="72308-108">Event Source</span></span>|<span data-ttu-id="72308-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="72308-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="72308-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="72308-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="72308-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="72308-111">Symbolic Name</span></span>||  
|<span data-ttu-id="72308-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="72308-112">Message Text</span></span>|<span data-ttu-id="72308-113">При применении реплицированной команды строка на подписчике не была найдена.</span><span class="sxs-lookup"><span data-stu-id="72308-113">The row was not found at the Subscriber when applying the replicated command.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="72308-114">Объяснение</span><span class="sxs-lookup"><span data-stu-id="72308-114">Explanation</span></span>  
 <span data-ttu-id="72308-115">Данная ошибка возникает в репликации транзакций, если строка, которую агент распространителя пытается обновить на подписчике, была удалена или ее первичный ключ был изменен.</span><span class="sxs-lookup"><span data-stu-id="72308-115">This error is raised in transactional replication if the Distribution Agent attempts to update a row at the Subscriber, but the row has been deleted or the primary key of the row has been changed.</span></span> <span data-ttu-id="72308-116">По умолчанию для подписчиков все подписки на публикацию транзакций доступны только для чтения, так как все изменения нельзя применить на издателе.</span><span class="sxs-lookup"><span data-stu-id="72308-116">By default, Subscribers to transactional publications should be treated as read-only, because changes are not propagated back to the Publisher.</span></span> <span data-ttu-id="72308-117">В случае с репликацией транзакций пользователь должен вносить изменения на подписчике только при использовании обновляемых подписок или одноранговой репликации.</span><span class="sxs-lookup"><span data-stu-id="72308-117">For transactional replication, user changes should be made at the Subscriber only if updatable subscriptions or peer-to-peer replication is used.</span></span> <span data-ttu-id="72308-118">Сведения об этих параметрах см. в разделе [Updatable Subscriptions for Transactional Replication](transactional/updatable-subscriptions-for-transactional-replication.md) и [Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="72308-118">For information about these options, see [Updatable Subscriptions for Transactional Replication](transactional/updatable-subscriptions-for-transactional-replication.md) and [Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="72308-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="72308-119">User Action</span></span>  
 <span data-ttu-id="72308-120">**Чтобы разрешить эту проблему:**</span><span class="sxs-lookup"><span data-stu-id="72308-120">**To resolve this problem:**</span></span>  
  
1.  <span data-ttu-id="72308-121">Если в ходе репликации был обнаружен источник ошибки, но репликация при этом должна быть продолжена, укажите параметр **-SkipErrors 20598** для агента распространителя.</span><span class="sxs-lookup"><span data-stu-id="72308-121">If replication must continue while you identify the source of the error, specify the parameter **-SkipErrors 20598** for the Distribution Agent.</span></span> <span data-ttu-id="72308-122">Это позволит агенту пропустить изменения, приведшие к ошибке 20598, но разрешит при этом репликацию других изменений.</span><span class="sxs-lookup"><span data-stu-id="72308-122">This allows the agent to skip changes that result in error 20598, while allowing other changes to be replicated.</span></span>  
  
2.  <span data-ttu-id="72308-123">Определите на подписчике строки, которые были удалены или имеют первичный ключ, отличный от первичного ключа соответствующих строк на издателе.</span><span class="sxs-lookup"><span data-stu-id="72308-123">Identify which rows at the Subscriber have been deleted or have a different primary key than the corresponding rows at the Publisher.</span></span> <span data-ttu-id="72308-124">При помощи [tablediff Utility](../../tools/tablediff-utility.md) можно определить, какие строки в базах данных публикации и подписки отличаются.</span><span class="sxs-lookup"><span data-stu-id="72308-124">You can use the [tablediff Utility](../../tools/tablediff-utility.md) to determine which rows are different in the publication and subscription databases.</span></span> <span data-ttu-id="72308-125">Сведения об использовании этой программы с реплицированными базами данных см. в статье [Сравнение реплицируемых таблиц на предмет различий (программирование репликации)](administration/compare-replicated-tables-for-differences-replication-programming.md).</span><span class="sxs-lookup"><span data-stu-id="72308-125">For information about using this utility with replicated databases, see [Compare Replicated Tables for Differences &#40;Replication Programming&#41;](administration/compare-replicated-tables-for-differences-replication-programming.md).</span></span>  
  
3.  <span data-ttu-id="72308-126">Используя программу **tablediff** или другой способ, внесите необходимые исправления в строки подписчика.</span><span class="sxs-lookup"><span data-stu-id="72308-126">Correct the rows at the Subscriber using the **tablediff** utility or another method.</span></span>  
  
4.  <span data-ttu-id="72308-127">Удалите параметр **-SkipErrors** (необязательно).</span><span class="sxs-lookup"><span data-stu-id="72308-127">(Optional) Remove the **-SkipErrors** parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72308-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="72308-128">See Also</span></span>  
 [<span data-ttu-id="72308-129">Справочник по ошибкам и событиям (репликация)</span><span class="sxs-lookup"><span data-stu-id="72308-129">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
