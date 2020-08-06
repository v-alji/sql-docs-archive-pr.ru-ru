---
title: MSSQL_ENG004929 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG004929 error
ms.assetid: 1d9b1d88-1fbf-4089-b392-687d3b0220ca
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b202b28eabe1feb1ed180bda0d58d2e84c7d10d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655080"
---
# <a name="mssql_eng004929"></a><span data-ttu-id="cca03-102">MSSQL_ENG004929</span><span class="sxs-lookup"><span data-stu-id="cca03-102">MSSQL_ENG004929</span></span>
    
## <a name="message-details"></a><span data-ttu-id="cca03-103">Сведения о сообщении</span><span class="sxs-lookup"><span data-stu-id="cca03-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cca03-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="cca03-104">Product Name</span></span>|<span data-ttu-id="cca03-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="cca03-105">SQL Server</span></span>|  
|<span data-ttu-id="cca03-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="cca03-106">Event ID</span></span>|<span data-ttu-id="cca03-107">4929</span><span class="sxs-lookup"><span data-stu-id="cca03-107">4929</span></span>|  
|<span data-ttu-id="cca03-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="cca03-108">Event Source</span></span>|<span data-ttu-id="cca03-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="cca03-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="cca03-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="cca03-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="cca03-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="cca03-111">Symbolic Name</span></span>||  
|<span data-ttu-id="cca03-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="cca03-112">Message Text</span></span>|<span data-ttu-id="cca03-113">Невозможно изменить %S_MSG "%.\*ls", так как выполняется публикация для репликации.</span><span class="sxs-lookup"><span data-stu-id="cca03-113">Cannot alter the %S_MSG '%.\*ls' because it is being published for replication.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="cca03-114">Объяснение</span><span class="sxs-lookup"><span data-stu-id="cca03-114">Explanation</span></span>  
 <span data-ttu-id="cca03-115">Указанная ошибка обычно возникает при попытке удалить ограничение первичного ключа, действующее в отношении таблицы, опубликованной для репликации транзакций.</span><span class="sxs-lookup"><span data-stu-id="cca03-115">This error typically occurs if you attempt to drop the primary key constraint on a table that is published for transactional replication.</span></span> <span data-ttu-id="cca03-116">Репликация транзакций требует первичный ключ для каждой опубликованной таблицы; следовательно, ограничение нельзя удалить.</span><span class="sxs-lookup"><span data-stu-id="cca03-116">Transactional replication requires a primary key for each published table; therefore the constraint cannot be dropped.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cca03-117">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="cca03-117">User Action</span></span>  
 <span data-ttu-id="cca03-118">Чтобы удалить ограничение, сначала удалите статью, связанную с таблицей.</span><span class="sxs-lookup"><span data-stu-id="cca03-118">To drop the constraint, first drop the article associated with the table.</span></span> <span data-ttu-id="cca03-119">Дополнительные сведения см. в статье [Добавление и удаление статей в существующих публикациях](publish/add-articles-to-and-drop-articles-from-existing-publications.md).</span><span class="sxs-lookup"><span data-stu-id="cca03-119">For more information, see [Add Articles to and Drop Articles from Existing Publications](publish/add-articles-to-and-drop-articles-from-existing-publications.md).</span></span> <span data-ttu-id="cca03-120">При возникновении ошибки в нереплицированной базе данных запустите [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql), чтобы снять все отметки о репликации для объектов базы данных.</span><span class="sxs-lookup"><span data-stu-id="cca03-120">If this error occurs in a database that is not replicated, execute [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) to ensure objects in the database are not marked as replicated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cca03-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="cca03-121">See Also</span></span>  
 [<span data-ttu-id="cca03-122">Справочник по ошибкам и событиям (репликация)</span><span class="sxs-lookup"><span data-stu-id="cca03-122">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
