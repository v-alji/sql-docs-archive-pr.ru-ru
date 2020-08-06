---
title: MSSQL_ENG003724 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG003724 error
ms.assetid: 10cb119d-92df-4124-b85d-cd2f2666c99c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: dbfb68575c5ffa73276b3bbe1643381c3f0cc412
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750696"
---
# <a name="mssql_eng003724"></a><span data-ttu-id="b47ba-102">MSSQL_ENG003724</span><span class="sxs-lookup"><span data-stu-id="b47ba-102">MSSQL_ENG003724</span></span>
    
## <a name="message-details"></a><span data-ttu-id="b47ba-103">Сведения о сообщении</span><span class="sxs-lookup"><span data-stu-id="b47ba-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b47ba-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="b47ba-104">Product Name</span></span>|<span data-ttu-id="b47ba-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b47ba-105">SQL Server</span></span>|  
|<span data-ttu-id="b47ba-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="b47ba-106">Event ID</span></span>|<span data-ttu-id="b47ba-107">3724</span><span class="sxs-lookup"><span data-stu-id="b47ba-107">3724</span></span>|  
|<span data-ttu-id="b47ba-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="b47ba-108">Event Source</span></span>|<span data-ttu-id="b47ba-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b47ba-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b47ba-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="b47ba-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="b47ba-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="b47ba-111">Symbolic Name</span></span>||  
|<span data-ttu-id="b47ba-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="b47ba-112">Message Text</span></span>|<span data-ttu-id="b47ba-113">Невозможно %S_MSG %S_MSG "%.\*ls", так как она используется для репликации.</span><span class="sxs-lookup"><span data-stu-id="b47ba-113">Cannot %S_MSG the %S_MSG '%.\*ls' because it is being used for replication.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b47ba-114">Объяснение</span><span class="sxs-lookup"><span data-stu-id="b47ba-114">Explanation</span></span>  
 <span data-ttu-id="b47ba-115">При репликации объектов в базе данных они помечаются как реплицированные в системной таблице **sysarticles** (для моментального снимка и публикаций транзакций) или **sysmergearticles** (для публикаций слиянием).</span><span class="sxs-lookup"><span data-stu-id="b47ba-115">When objects in a database are replicated, they are marked as replicated in the system table **sysarticles** (for snapshot and transactional publications) or **sysmergearticles** (for merge publications).</span></span> <span data-ttu-id="b47ba-116">При попытке удалить реплицированный объект возникает данная ошибка.</span><span class="sxs-lookup"><span data-stu-id="b47ba-116">If you attempt drop a replicated object, this error is raised.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b47ba-117">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="b47ba-117">User Action</span></span>  
 <span data-ttu-id="b47ba-118">Убедитесь в том, что объект базы данных не подвергался репликации, прежде чем предпримете попытку удалить его.</span><span class="sxs-lookup"><span data-stu-id="b47ba-118">Ensure the database object is not replicated before attempting to drop it.</span></span> <span data-ttu-id="b47ba-119">Пример:</span><span class="sxs-lookup"><span data-stu-id="b47ba-119">For example:</span></span>  
  
-   <span data-ttu-id="b47ba-120">Если данная ошибка появляется в базе данных публикации, удалите статью из публикации, прежде чем удалить объект.</span><span class="sxs-lookup"><span data-stu-id="b47ba-120">If the error occurs in the publication database, drop the article from the publication before dropping the object.</span></span> <span data-ttu-id="b47ba-121">Дополнительные сведения см. в статье [Добавление и удаление статей в существующих публикациях](publish/add-articles-to-and-drop-articles-from-existing-publications.md).</span><span class="sxs-lookup"><span data-stu-id="b47ba-121">For more information, see [Add Articles to and Drop Articles from Existing Publications](publish/add-articles-to-and-drop-articles-from-existing-publications.md).</span></span>  
  
-   <span data-ttu-id="b47ba-122">Если данная ошибка появляется в базе данных подписки, удалите подписку, прежде чем удалить объект.</span><span class="sxs-lookup"><span data-stu-id="b47ba-122">If the error occurs in the subscription database, drop the subscription before dropping the object.</span></span> <span data-ttu-id="b47ba-123">Дополнительные сведения см. в статье [Подписка на публикации](subscribe-to-publications.md).</span><span class="sxs-lookup"><span data-stu-id="b47ba-123">For more information, see [Subscribe to Publications](subscribe-to-publications.md).</span></span> <span data-ttu-id="b47ba-124">Для подписок на публикации транзакций имеется возможность удаления подписки на отдельную статью вместо удаления всей публикации.</span><span class="sxs-lookup"><span data-stu-id="b47ba-124">For subscriptions to transactional publications, it is possible to drop the subscription to an individual article rather than the entire publication.</span></span> <span data-ttu-id="b47ba-125">Дополнительные сведения см. в разделе [sp_dropsubscription (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-dropsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b47ba-125">For more information, see [sp_dropsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropsubscription-transact-sql).</span></span>  
  
 <span data-ttu-id="b47ba-126">При возникновении ошибки в нереплицированной базе данных запустите [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql), чтобы снять все отметки о репликации для объектов базы данных.</span><span class="sxs-lookup"><span data-stu-id="b47ba-126">If this error occurs in a database that is not replicated, execute [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) to ensure objects in the database are not marked as replicated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b47ba-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="b47ba-127">See Also</span></span>  
 [<span data-ttu-id="b47ba-128">Справочник по ошибкам и событиям (репликация)</span><span class="sxs-lookup"><span data-stu-id="b47ba-128">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
