---
title: Двунаправленная репликация транзакций | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- bidirectional replication
- transactional replication, bidirectional replication
- bidirectional transactional replication
ms.assetid: 98772e95-67ed-4010-8108-5113dbe709ff
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 57b18dde2e7134e0ba9eb6a9b2e8f5357d171a55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664854"
---
# <a name="bidirectional-transactional-replication"></a><span data-ttu-id="d5170-102">двунаправленная репликация транзакций</span><span class="sxs-lookup"><span data-stu-id="d5170-102">Bidirectional Transactional Replication</span></span>
  <span data-ttu-id="d5170-103">Двунаправленная репликация транзакций представляет собой особую топологию репликации транзакций, которая позволяет двум серверам обмениваться изменениями друг с другом: каждый сервер публикует данные, после чего подписывается на публикацию с теми же данными от другого сервера.</span><span class="sxs-lookup"><span data-stu-id="d5170-103">Bidirectional transactional replication is a specific transactional replication topology that allows two servers to exchange changes with each other: each server publishes data and then subscribes to a publication with the same data from the other server.</span></span> <span data-ttu-id="d5170-104">**@loopback_detection**Параметру [Sp_addsubscription &#40;TRANSACT-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addsubscription-transact-sql) присваивается значение true, чтобы гарантировать, что изменения отправляются только подписчику и не приводят к тому, что изменения отправляются обратно издателю.</span><span class="sxs-lookup"><span data-stu-id="d5170-104">The **@loopback_detection** parameter of [sp_addsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addsubscription-transact-sql) is set to TRUE to ensure that changes are only sent to the Subscriber and do not result in the change being sent back to the Publisher.</span></span>  
  
 <span data-ttu-id="d5170-105">В [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] и более поздних версиях такая топология поддерживается также одноранговой репликацией транзакций, но двунаправленная репликация позволяет увеличить производительность.</span><span class="sxs-lookup"><span data-stu-id="d5170-105">In [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] and later versions, this topology is also supported by peer-to-peer transactional replication, but bidirectional replication can provide improved performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5170-106">См. также:</span><span class="sxs-lookup"><span data-stu-id="d5170-106">See Also</span></span>  
 [<span data-ttu-id="d5170-107">Peer-to-Peer Transactional Replication</span><span class="sxs-lookup"><span data-stu-id="d5170-107">Peer-to-Peer Transactional Replication</span></span>](peer-to-peer-transactional-replication.md)  
  
  
