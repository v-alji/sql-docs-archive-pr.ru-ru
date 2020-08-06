---
title: MSSQL_ENG014144 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014144 error
ms.assetid: fdc744d5-530e-48c4-9420-cca032fd482b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0d93f06a585bcc01c52438ff7b99bbd635532402
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654182"
---
# <a name="mssql_eng014144"></a><span data-ttu-id="c6c76-102">MSSQL_ENG014144</span><span class="sxs-lookup"><span data-stu-id="c6c76-102">MSSQL_ENG014144</span></span>
    
## <a name="message-details"></a><span data-ttu-id="c6c76-103">Сведения о сообщении</span><span class="sxs-lookup"><span data-stu-id="c6c76-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c6c76-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="c6c76-104">Product Name</span></span>|<span data-ttu-id="c6c76-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c6c76-105">SQL Server</span></span>|  
|<span data-ttu-id="c6c76-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="c6c76-106">Event ID</span></span>|<span data-ttu-id="c6c76-107">14144</span><span class="sxs-lookup"><span data-stu-id="c6c76-107">14144</span></span>|  
|<span data-ttu-id="c6c76-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="c6c76-108">Event Source</span></span>|<span data-ttu-id="c6c76-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c6c76-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c6c76-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="c6c76-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="c6c76-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="c6c76-111">Symbolic Name</span></span>||  
|<span data-ttu-id="c6c76-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="c6c76-112">Message Text</span></span>|<span data-ttu-id="c6c76-113">Невозможно удалить подписчик '%s'.</span><span class="sxs-lookup"><span data-stu-id="c6c76-113">Cannot drop Subscriber '%s'.</span></span> <span data-ttu-id="c6c76-114">В базе данных публикации '%s' для него есть подписки.</span><span class="sxs-lookup"><span data-stu-id="c6c76-114">There are subscriptions for it in the publication database '%s'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c6c76-115">Объяснение</span><span class="sxs-lookup"><span data-stu-id="c6c76-115">Explanation</span></span>  
 <span data-ttu-id="c6c76-116">Экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , настроенный в качестве подписчика, не может быть удален из роли подписчика до тех пор, пока есть активные подписки, настроенные для данного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="c6c76-116">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that is configured as a Subscriber cannot be removed from the role of Subscriber while there are active subscriptions configured for the instance.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c6c76-117">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="c6c76-117">User Action</span></span>  
 <span data-ttu-id="c6c76-118">Удалите все связанные подписки, прежде чем пытаться изменить состояние подписчика для экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c6c76-118">Drop all associated subscriptions before attempting to change the Subscriber status of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance:</span></span>  
  
1.  <span data-ttu-id="c6c76-119">Выполните [sp_helpsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql) в базе данных публикации в издателе, чтобы найти подписки.</span><span class="sxs-lookup"><span data-stu-id="c6c76-119">Execute [sp_helpsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql) in the publication database at the Publisher to find subscriptions.</span></span>  
  
2.  <span data-ttu-id="c6c76-120">Выполните [sp_dropsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropsubscription-transact-sql) в базе данных публикации в издателе, чтобы удалить подписки.</span><span class="sxs-lookup"><span data-stu-id="c6c76-120">Execute [sp_dropsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropsubscription-transact-sql) in the publication database to drop subscriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6c76-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="c6c76-121">See Also</span></span>  
 <span data-ttu-id="c6c76-122">[Справочник по ошибкам и событиям (репликация)](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="c6c76-122">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 [<span data-ttu-id="c6c76-123">Подписка на публикации</span><span class="sxs-lookup"><span data-stu-id="c6c76-123">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
