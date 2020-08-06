---
title: MSSQLSERVER_601 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "601"
helpviewer_keywords:
- 601 (Database Engine error)
ms.assetid: 2039cc0a-9a43-4369-a04a-935e384388b6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 459a983d72a91e628e8cc33636d3abd81998f1d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668372"
---
# <a name="mssqlserver_601"></a><span data-ttu-id="050d7-102">MSSQLSERVER_601</span><span class="sxs-lookup"><span data-stu-id="050d7-102">MSSQLSERVER_601</span></span>
    
## <a name="details"></a><span data-ttu-id="050d7-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="050d7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="050d7-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="050d7-104">Product Name</span></span>|<span data-ttu-id="050d7-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="050d7-105">SQL Server</span></span>|  
|<span data-ttu-id="050d7-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="050d7-106">Event ID</span></span>|<span data-ttu-id="050d7-107">601</span><span class="sxs-lookup"><span data-stu-id="050d7-107">601</span></span>|  
|<span data-ttu-id="050d7-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="050d7-108">Event Source</span></span>|<span data-ttu-id="050d7-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="050d7-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="050d7-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="050d7-110">Component</span></span>|<span data-ttu-id="050d7-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="050d7-111">SQLEngine</span></span>|  
|<span data-ttu-id="050d7-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="050d7-112">Symbolic Name</span></span>||  
|<span data-ttu-id="050d7-113">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="050d7-113">Message Text</span></span>|<span data-ttu-id="050d7-114">Не удалось продолжить просмотр с NOLOCK вследствие перемещения данных.</span><span class="sxs-lookup"><span data-stu-id="050d7-114">Could not continue scan with NOLOCK due to data movement.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="050d7-115">Объяснение</span><span class="sxs-lookup"><span data-stu-id="050d7-115">Explanation</span></span>  
 <span data-ttu-id="050d7-116">[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] не удается продолжить выполнение запроса, поскольку приложение пытается считать данные, обновленные или удаленные другой транзакцией.</span><span class="sxs-lookup"><span data-stu-id="050d7-116">The [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] cannot continue executing the query because it is trying to read data that was updated or deleted by another transaction.</span></span> <span data-ttu-id="050d7-117">Очередь использует указание блокировки NOLOCK или уровень изоляции транзакции READ UNCOMMITTED.</span><span class="sxs-lookup"><span data-stu-id="050d7-117">The query is using either the NOLOCK locking hint or the READ UNCOMMITTED transaction isolation level.</span></span>  
  
 <span data-ttu-id="050d7-118">Как правило, доступ к данным, которые изменяются другой операцией, запрещен из-за наложенной на них блокировки.</span><span class="sxs-lookup"><span data-stu-id="050d7-118">Typically, access to data that is being changed by another transaction is denied because of locks put on the data.</span></span> <span data-ttu-id="050d7-119">Однако указание блокировки NOLOCK и уровень изоляции транзакции READ UNCOMMITTED позволили запросу считать данные, заблокированные другой транзакцией.</span><span class="sxs-lookup"><span data-stu-id="050d7-119">However, the NOLOCK locking hint and READ UNCOMMITTED transaction isolation level let a query read data that is locked by another transaction.</span></span> <span data-ttu-id="050d7-120">Это называется «грязным» чтением, поскольку таким образом можно считать значения, которые еще не были зафиксированы и могут быть изменены.</span><span class="sxs-lookup"><span data-stu-id="050d7-120">This is referred to as a dirty read because you can read values that have not yet been committed and that are subject to change.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="050d7-121">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="050d7-121">User Action</span></span>  
 <span data-ttu-id="050d7-122">Эта ошибка отменяет запрос.</span><span class="sxs-lookup"><span data-stu-id="050d7-122">This error cancels the query.</span></span> <span data-ttu-id="050d7-123">Отправьте запрос повторно или удалите указание блокировки NOLOCK.</span><span class="sxs-lookup"><span data-stu-id="050d7-123">Either resubmit the query or remove the NOLOCK locking hint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="050d7-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="050d7-124">See Also</span></span>  
 <span data-ttu-id="050d7-125">[MSSQLSERVER_605](mssqlserver-605-database-engine-error.md) </span><span class="sxs-lookup"><span data-stu-id="050d7-125">[MSSQLSERVER_605](mssqlserver-605-database-engine-error.md) </span></span>  
 <span data-ttu-id="050d7-126">[Табличные указания (Transact-SQL)](/sql/t-sql/queries/hints-transact-sql-table) </span><span class="sxs-lookup"><span data-stu-id="050d7-126">[Table Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table) </span></span>  
 <span data-ttu-id="050d7-127">[SELECT (Transact-SQL)](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="050d7-127">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 [<span data-ttu-id="050d7-128">SET TRANSACTION ISOLATION LEVEL (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="050d7-128">SET TRANSACTION ISOLATION LEVEL &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/set-transaction-isolation-level-transact-sql)  
  
  
