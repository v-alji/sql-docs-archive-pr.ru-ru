---
title: MSSQLSERVER_3961 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3961 (Database Engine error)
ms.assetid: 3bbc6965-6445-400c-940a-2d85b037513f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f55be9288b3c2e559633d0f67709829466fc8815
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667734"
---
# <a name="mssqlserver_3961"></a><span data-ttu-id="c520a-102">MSSQLSERVER_3961</span><span class="sxs-lookup"><span data-stu-id="c520a-102">MSSQLSERVER_3961</span></span>
    
## <a name="details"></a><span data-ttu-id="c520a-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="c520a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c520a-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="c520a-104">Product Name</span></span>|<span data-ttu-id="c520a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c520a-105">SQL Server</span></span>|  
|<span data-ttu-id="c520a-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="c520a-106">Event ID</span></span>|<span data-ttu-id="c520a-107">3961</span><span class="sxs-lookup"><span data-stu-id="c520a-107">3961</span></span>|  
|<span data-ttu-id="c520a-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="c520a-108">Event Source</span></span>|<span data-ttu-id="c520a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c520a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c520a-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="c520a-110">Component</span></span>|<span data-ttu-id="c520a-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="c520a-111">SQLEngine</span></span>|  
|<span data-ttu-id="c520a-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="c520a-112">Symbolic Name</span></span>|<span data-ttu-id="c520a-113">XACT_METADATA_INVALID</span><span class="sxs-lookup"><span data-stu-id="c520a-113">XACT_METADATA_INVALID</span></span>|  
|<span data-ttu-id="c520a-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="c520a-114">Message Text</span></span>|<span data-ttu-id="c520a-115">Ошибка транзакции в режиме изоляции моментального снимка в базе данных «%.\*ls»: объект, к которому производится обращение в данной инструкции, был изменен инструкцией DDL другой, параллельной транзакции после начала данной транзакции.</span><span class="sxs-lookup"><span data-stu-id="c520a-115">Snapshot isolation transaction failed in database '%.\*ls' because the object accessed by the statement has been modified by a DDL statement in another concurrent transaction since the start of this transaction.</span></span>  <span data-ttu-id="c520a-116">Это запрещено, так как управление версиями метаданных не осуществляется.</span><span class="sxs-lookup"><span data-stu-id="c520a-116">It is disallowed because the metadata is not versioned.</span></span> <span data-ttu-id="c520a-117">Одновременное обновление метаданных может привести к несогласованности при выполнении вместе с изоляцией моментального снимка.</span><span class="sxs-lookup"><span data-stu-id="c520a-117">A concurrent update to metadata can lead to inconsistency if mixed with snapshot isolation.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c520a-118">Объяснение</span><span class="sxs-lookup"><span data-stu-id="c520a-118">Explanation</span></span>  
 <span data-ttu-id="c520a-119">Эта ошибка может возникнуть при запросе метаданных во время изоляции моментального снимка, когда выполняется параллельная инструкция DDL, обновляющая метаданные, к которым выполняется обращение при изоляции моментального снимка.</span><span class="sxs-lookup"><span data-stu-id="c520a-119">This error can occur if you are querying metadata under snapshot isolation and there is a concurrent DDL statement that updates the metadata that is being accessed under snapshot isolation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c520a-120">не поддерживает управление версиями метаданных.</span><span class="sxs-lookup"><span data-stu-id="c520a-120">does not support versioning of metadata.</span></span> <span data-ttu-id="c520a-121">По этой причине существуют ограничения для операций DDL, которые могут выполняться в явной транзакции, выполняющийся при изоляции моментальных снимков.</span><span class="sxs-lookup"><span data-stu-id="c520a-121">For this reason, there are restrictions on what DDL operations can be performed within an explicit transaction running under snapshot isolation.</span></span> <span data-ttu-id="c520a-122">Неявная транзакция, по определению, — это отдельная инструкция, которая может принудительно выполнять семантику изоляции моментального снимка даже при наличии инструкций DDL.</span><span class="sxs-lookup"><span data-stu-id="c520a-122">An implicit transaction, by definition, is a single statement which makes it possible to enforce the semantics of snapshot isolation even with DDL statements.</span></span> <span data-ttu-id="c520a-123">Следующие инструкции DDL недопустимы в транзакции, работающей при изоляции моментального снимка, после инструкции BEGIN TRANSACTION: ALTER TABLE, CREATE INDEX, CREATE XML INDEX, ALTER INDEX, DROP INDEX, DBCC REINDEX, ALTER PARTITION FUNCTION, ALTER PARTITION SCHEME и любые инструкции DDL среды CLR.</span><span class="sxs-lookup"><span data-stu-id="c520a-123">The following DDL statements are not permitted under snapshot isolation after a BEGIN TRANSACTION statement: ALTER TABLE, CREATE INDEX, CREATE XML INDEX, ALTER INDEX, DROP INDEX, DBCC REINDEX, ALTER PARTITION FUNCTION, ALTER PARTITION SCHEME, or any common language runtime (CLR) DDL statement.</span></span> <span data-ttu-id="c520a-124">Эти инструкции разрешены при использовании изоляции моментального снимка в неявных транзакциях.</span><span class="sxs-lookup"><span data-stu-id="c520a-124">These statements are permitted when you are using snapshot isolation within implicit transactions.</span></span> <span data-ttu-id="c520a-125">Неявная транзакция, по определению, — это отдельная инструкция, которая может принудительно выполнять семантику изоляции моментального снимка даже при наличии инструкций DDL.</span><span class="sxs-lookup"><span data-stu-id="c520a-125">An implicit transaction, by definition, is a single statement which makes it possible to enforce the semantics of snapshot isolation even with DDL statements.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c520a-126">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="c520a-126">User Action</span></span>  
 <span data-ttu-id="c520a-127">Перед запросом метаданных измените уровень изоляции моментального снимка на другой уровень изоляции, например на уровень изоляции зафиксированной операции чтения.</span><span class="sxs-lookup"><span data-stu-id="c520a-127">Change the snapshot isolation level to a non-snapshot isolation level such as read committed before querying metadata.</span></span>  
  
  
