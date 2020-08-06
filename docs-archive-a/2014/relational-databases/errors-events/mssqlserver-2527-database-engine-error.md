---
title: MSSQLSERVER_2527 | | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2527 (Database Engine error)
ms.assetid: 1cef90ef-9c39-44e6-bc7f-316c8f53c10c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 900707634a016ecfd29f9f676e68b4d2f557ccea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657799"
---
# <a name="mssqlserver_2527"></a><span data-ttu-id="83f63-102">MSSQLSERVER_2527</span><span class="sxs-lookup"><span data-stu-id="83f63-102">MSSQLSERVER_2527</span></span>
    
## <a name="details"></a><span data-ttu-id="83f63-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="83f63-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="83f63-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="83f63-104">Product Name</span></span>|<span data-ttu-id="83f63-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="83f63-105">SQL Server</span></span>|  
|<span data-ttu-id="83f63-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="83f63-106">Event ID</span></span>|<span data-ttu-id="83f63-107">2527</span><span class="sxs-lookup"><span data-stu-id="83f63-107">2527</span></span>|  
|<span data-ttu-id="83f63-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="83f63-108">Event Source</span></span>|<span data-ttu-id="83f63-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="83f63-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="83f63-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="83f63-110">Component</span></span>|<span data-ttu-id="83f63-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="83f63-111">SQLEngine</span></span>|  
|<span data-ttu-id="83f63-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="83f63-112">Symbolic Name</span></span>|<span data-ttu-id="83f63-113">DBCC_INDEX_FILEGROUP_IS_OFFLINE</span><span class="sxs-lookup"><span data-stu-id="83f63-113">DBCC_INDEX_FILEGROUP_IS_OFFLINE</span></span>|  
|<span data-ttu-id="83f63-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="83f63-114">Message Text</span></span>|<span data-ttu-id="83f63-115">Невозможно обработать индекс I_NAME таблицы O_NAME, так как файловая группа F_NAME находится в режиме «вне сети».</span><span class="sxs-lookup"><span data-stu-id="83f63-115">Unable to process index I_NAME of table O_NAME because filegroup F_NAME is offline.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="83f63-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="83f63-116">Explanation</span></span>  
 <span data-ttu-id="83f63-117">Это информационное сообщение указывает, что индекс невозможно проверить, поскольку одна из файловых групп, в которой хранятся данные индекса, находится в режиме «вне сети».</span><span class="sxs-lookup"><span data-stu-id="83f63-117">This informational message indicates that the index cannot be checked because one of the filegroups that stores data for the index is offline.</span></span> <span data-ttu-id="83f63-118">Состояние файлов в файловой группе определяет доступность всей файловой группы.</span><span class="sxs-lookup"><span data-stu-id="83f63-118">The state of the files in a filegroup determines the availability of the whole filegroup.</span></span> <span data-ttu-id="83f63-119">Чтобы файловая группа была доступна, необходимо, чтобы все файлы в файловой группе находились в режиме в сети.</span><span class="sxs-lookup"><span data-stu-id="83f63-119">For a filegroup to be available, all files within the filegroup must be online.</span></span> <span data-ttu-id="83f63-120">Если других проблем нет, будут проверяться все остальные индексы того же объекта.</span><span class="sxs-lookup"><span data-stu-id="83f63-120">If there are no other problems, all other indexes of the same object will be checked.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="83f63-121">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="83f63-121">User Action</span></span>  
 <span data-ttu-id="83f63-122">Чтобы просмотреть текущее состояние файлов указанной файловой группы, выполните запрос к представлению каталога **sys.database_files** или**sys.master_files**.</span><span class="sxs-lookup"><span data-stu-id="83f63-122">To view the state of the files for the specified filegroup, query either the **sys.database_files** or **sys.master_files** catalog view.</span></span>  
  
 <span data-ttu-id="83f63-123">Восстановите автономный файл из резервной копии.</span><span class="sxs-lookup"><span data-stu-id="83f63-123">Restore the offline file from a backup.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83f63-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="83f63-124">See Also</span></span>  
 <span data-ttu-id="83f63-125">[sys.database_files (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="83f63-125">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span></span>  
 <span data-ttu-id="83f63-126">[sys. master_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="83f63-126">[sys.master_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql) </span></span>  
 [<span data-ttu-id="83f63-127">RESTORE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="83f63-127">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
