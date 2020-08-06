---
title: MSSQL_ENG021286 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021286 error
ms.assetid: b63620b7-1c6d-46f7-90ea-3a8e99af8de4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 592c788b563046e5949217c94006de2d4755f049
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730501"
---
# <a name="mssql_eng021286"></a><span data-ttu-id="5fc69-102">MSSQL_ENG021286</span><span class="sxs-lookup"><span data-stu-id="5fc69-102">MSSQL_ENG021286</span></span>
    
## <a name="message-details"></a><span data-ttu-id="5fc69-103">Сведения о сообщении</span><span class="sxs-lookup"><span data-stu-id="5fc69-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5fc69-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="5fc69-104">Product Name</span></span>|<span data-ttu-id="5fc69-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5fc69-105">SQL Server</span></span>|  
|<span data-ttu-id="5fc69-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="5fc69-106">Event ID</span></span>|<span data-ttu-id="5fc69-107">21286</span><span class="sxs-lookup"><span data-stu-id="5fc69-107">21286</span></span>|  
|<span data-ttu-id="5fc69-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="5fc69-108">Event Source</span></span>|<span data-ttu-id="5fc69-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5fc69-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5fc69-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="5fc69-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="5fc69-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="5fc69-111">Symbolic Name</span></span>||  
|<span data-ttu-id="5fc69-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="5fc69-112">Message Text</span></span>|<span data-ttu-id="5fc69-113">Таблица конфликтов "%s" не существует.</span><span class="sxs-lookup"><span data-stu-id="5fc69-113">Conflict table '%s' does not exist.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5fc69-114">Объяснение</span><span class="sxs-lookup"><span data-stu-id="5fc69-114">Explanation</span></span>  
 <span data-ttu-id="5fc69-115">Эта ошибка возникает, если для статьи, указанной в [sysmergearticles (Transact-SQL)](/sql/relational-databases/system-tables/sysmergearticles-transact-sql), не существует таблица конфликтов.</span><span class="sxs-lookup"><span data-stu-id="5fc69-115">This error is raised if the conflict table for an article listed in [sysmergearticles &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/sysmergearticles-transact-sql) does not actually exist.</span></span> <span data-ttu-id="5fc69-116">Эта ошибка может возникнуть при попытке добавить или удалить столбец в таблице, опубликованной для репликации слиянием.</span><span class="sxs-lookup"><span data-stu-id="5fc69-116">The error can occur when you attempt to add a column to or drop a column from a table published for merge replication.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5fc69-117">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="5fc69-117">User Action</span></span>  
 <span data-ttu-id="5fc69-118">Выполните инструкцию [DBCC CHECKDB (Transact-SQL)](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) в базе данных с отсутствующей таблицей конфликтов, чтобы убедиться в отсутствии проблем согласованности данных.</span><span class="sxs-lookup"><span data-stu-id="5fc69-118">Execute [DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) on the database with the missing conflict table to verify there are no data consistency issues.</span></span>  
  
 <span data-ttu-id="5fc69-119">Если таблица конфликтов отсутствует на подписчике, удалите подписку и создайте ее заново.</span><span class="sxs-lookup"><span data-stu-id="5fc69-119">If the conflict table is missing on a Subscriber, drop the subscription and recreate it.</span></span> <span data-ttu-id="5fc69-120">Если таблица конфликтов отсутствует на издателе, удалите все подписки, удалите публикацию, а затем заново создайте публикацию и все подписки.</span><span class="sxs-lookup"><span data-stu-id="5fc69-120">If the conflict table is missing on a Publisher, drop all subscriptions, drop the publication, and then recreate the publication and all subscriptions.</span></span> <span data-ttu-id="5fc69-121">Дополнительные сведения см. в статьях [Публикация данных и объектов базы данных](publish/publish-data-and-database-objects.md) и [Подписка на публикации](subscribe-to-publications.md).</span><span class="sxs-lookup"><span data-stu-id="5fc69-121">For more information, see [Publish Data and Database Objects](publish/publish-data-and-database-objects.md) and [Subscribe to Publications](subscribe-to-publications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fc69-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="5fc69-122">See Also</span></span>  
 [<span data-ttu-id="5fc69-123">Справочник по ошибкам и событиям (репликация)</span><span class="sxs-lookup"><span data-stu-id="5fc69-123">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
