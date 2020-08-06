---
title: MSSQL_ENG014005 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014005 error
ms.assetid: f168f0d6-cb11-45d4-9781-c374d7f388ee
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d820fd26cceee72b0d08204d6f6ce73a76508e9c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655078"
---
# <a name="mssql_eng014005"></a><span data-ttu-id="66c72-102">MSSQL_ENG014005</span><span class="sxs-lookup"><span data-stu-id="66c72-102">MSSQL_ENG014005</span></span>
    
## <a name="message-details"></a><span data-ttu-id="66c72-103">Сведения о сообщении</span><span class="sxs-lookup"><span data-stu-id="66c72-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="66c72-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="66c72-104">Product Name</span></span>|<span data-ttu-id="66c72-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="66c72-105">SQL Server</span></span>|  
|<span data-ttu-id="66c72-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="66c72-106">Event ID</span></span>|<span data-ttu-id="66c72-107">14005</span><span class="sxs-lookup"><span data-stu-id="66c72-107">14005</span></span>|  
|<span data-ttu-id="66c72-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="66c72-108">Event Source</span></span>|<span data-ttu-id="66c72-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="66c72-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="66c72-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="66c72-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="66c72-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="66c72-111">Symbolic Name</span></span>||  
|<span data-ttu-id="66c72-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="66c72-112">Message Text</span></span>|<span data-ttu-id="66c72-113">Не удалось удалить публикацию.</span><span class="sxs-lookup"><span data-stu-id="66c72-113">Could not drop publication.</span></span> <span data-ttu-id="66c72-114">На нее существует подписка.</span><span class="sxs-lookup"><span data-stu-id="66c72-114">A subscription exists to it.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="66c72-115">Объяснение</span><span class="sxs-lookup"><span data-stu-id="66c72-115">Explanation</span></span>  
 <span data-ttu-id="66c72-116">Была предпринята попытка удалить публикацию, для которой существуют связанные с ней подписки.</span><span class="sxs-lookup"><span data-stu-id="66c72-116">You have tried to drop a publication which has one or more associated subscriptions.</span></span> <span data-ttu-id="66c72-117">Публикация может быть удалена, только если нет подписок, связанных с нею.</span><span class="sxs-lookup"><span data-stu-id="66c72-117">A publication can only be dropped if there are no associated subscriptions.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="66c72-118">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="66c72-118">User Action</span></span>  
 <span data-ttu-id="66c72-119">Прежде чем удалять публикацию, необходимо удалить подписки.</span><span class="sxs-lookup"><span data-stu-id="66c72-119">Drop the subscriptions before dropping the publication.</span></span> <span data-ttu-id="66c72-120">Если для удаления публикации используется среда [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , то существует возможность автоматического удаления всех подписок, связанных с публикацией.</span><span class="sxs-lookup"><span data-stu-id="66c72-120">If you use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to drop the publication, it will give you the option to automatically drop all associated subscriptions before dropping the publication.</span></span> <span data-ttu-id="66c72-121">При использовании хранимых процедур необходимо сначала удалить подписки явным образом.</span><span class="sxs-lookup"><span data-stu-id="66c72-121">If you use stored procedures, you must explicitly drop the subscriptions first.</span></span> <span data-ttu-id="66c72-122">Дополнительные сведения см. в разделах [Delete a Push Subscription](delete-a-push-subscription.md) и [Delete a Pull Subscription](delete-a-pull-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="66c72-122">For more information, see [Delete a Push Subscription](delete-a-push-subscription.md) and [Delete a Pull Subscription](delete-a-pull-subscription.md).</span></span>  
  
 <span data-ttu-id="66c72-123">Если для данной публикации нет подписок или если данная ошибка возникает на стадии создания публикации, это может свидетельствовать о существовании подписки, которая не была полностью очищена при ее удалении.</span><span class="sxs-lookup"><span data-stu-id="66c72-123">If no subscriptions appear to exist for the publication or if you see this error when you create a publication, you might have a previous subscription that was not completely cleaned up when it was removed.</span></span> <span data-ttu-id="66c72-124">Выполните хранимую процедуру [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) в базе данных, чтобы удалить все объекты и настройки, связанные с репликацией.</span><span class="sxs-lookup"><span data-stu-id="66c72-124">Execute [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) on the database to remove all objects and settings related to replication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66c72-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="66c72-125">See Also</span></span>  
 [<span data-ttu-id="66c72-126">Справочник по ошибкам и событиям (репликация)</span><span class="sxs-lookup"><span data-stu-id="66c72-126">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
