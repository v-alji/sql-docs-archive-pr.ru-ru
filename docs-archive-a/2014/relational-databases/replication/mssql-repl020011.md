---
title: MSSQL_REPL020011 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_REPL020011 error
ms.assetid: f72072d7-bbb6-48ad-ac88-afa74aeb4d58
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 646f25740ebb007f8d04a89690d3b712781efcc8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736209"
---
# <a name="mssql_repl020011"></a><span data-ttu-id="25408-102">MSSQL_REPL020011</span><span class="sxs-lookup"><span data-stu-id="25408-102">MSSQL_REPL020011</span></span>
    
## <a name="message-details"></a><span data-ttu-id="25408-103">Сведения о сообщении</span><span class="sxs-lookup"><span data-stu-id="25408-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="25408-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="25408-104">Product Name</span></span>|<span data-ttu-id="25408-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="25408-105">SQL Server</span></span>|  
|<span data-ttu-id="25408-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="25408-106">Event ID</span></span>|<span data-ttu-id="25408-107">20011</span><span class="sxs-lookup"><span data-stu-id="25408-107">20011</span></span>|  
|<span data-ttu-id="25408-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="25408-108">Event Source</span></span>|<span data-ttu-id="25408-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="25408-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="25408-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="25408-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="25408-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="25408-111">Symbolic Name</span></span>||  
|<span data-ttu-id="25408-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="25408-112">Message Text</span></span>|<span data-ttu-id="25408-113">Процессу не удалось выполнить '%1' на '%2'.</span><span class="sxs-lookup"><span data-stu-id="25408-113">The process could not execute '%1' on '%2'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="25408-114">Объяснение</span><span class="sxs-lookup"><span data-stu-id="25408-114">Explanation</span></span>  
 <span data-ttu-id="25408-115">Эта ошибка может возникать в ряде случаев во время обработки репликации транзакций, например, когда агент чтения журнала выполняет хранимую процедуру **sp_replcmds** (Процесс не смог выполнить 'sp_replcmds' на \<ServerName>) или **sp_repldone** (Процесс не смог выполнить 'sp_repldone' на \<ServerName>).</span><span class="sxs-lookup"><span data-stu-id="25408-115">This error can be raised in a number of circumstances during transactional replication processing, such as when the Log Reader Agent executes **sp_replcmds** (The process could not execute 'sp_replcmds' on \<ServerName>) or **sp_repldone** (The process could not execute 'sp_repldone' on \<ServerName>).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="25408-116">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="25408-116">User Action</span></span>  
 <span data-ttu-id="25408-117">Если эта ошибка возникает в базе данных, которая только что была восстановлена из резервной копии, убедитесь, что были соблюдены инструкции, приведенные в документации по резервному копированию и восстановлению, включая выполнение хранимой процедуры **sp_replrestart** , если она необходима.</span><span class="sxs-lookup"><span data-stu-id="25408-117">If this error is raised in a database that you have just restored from a backup, ensure you have followed the steps outlined in the backup and restore documentation, including executing **sp_replrestart** if appropriate.</span></span> <span data-ttu-id="25408-118">Дополнительные сведения см. в статье [Стратегии резервного копирования и восстановления из копии репликации моментальных снимков и репликации транзакций](administration/strategies-for-backing-up-and-restoring-snapshot-and-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="25408-118">For more information, see [Strategies for Backing Up and Restoring Snapshot and Transactional Replication](administration/strategies-for-backing-up-and-restoring-snapshot-and-transactional-replication.md).</span></span>  
  
 <span data-ttu-id="25408-119">Эта ошибка является внутренней ошибкой обработки, и если она возникает в ситуациях, отличных от восстановления, то она обычно указывает на необходимость удаления и перенастройки репликации.</span><span class="sxs-lookup"><span data-stu-id="25408-119">This error is an internal processing error and if it is raised in circumstances other than a restore, it typically indicates that replication must be removed and reconfigured.</span></span> <span data-ttu-id="25408-120">Если не удается удалить репликацию, обратитесь за консультацией в службу поддержки пользователей.</span><span class="sxs-lookup"><span data-stu-id="25408-120">If you cannot remove replication, contact customer support for assistance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25408-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="25408-121">See Also</span></span>  
 <span data-ttu-id="25408-122">[Справочник по ошибкам и событиям (репликация)](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="25408-122">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 <span data-ttu-id="25408-123">[sp_replcmds (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-replcmds-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="25408-123">[sp_replcmds &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replcmds-transact-sql) </span></span>  
 [<span data-ttu-id="25408-124">sp_repldone &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="25408-124">sp_repldone &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-repldone-transact-sql)  
  
  
