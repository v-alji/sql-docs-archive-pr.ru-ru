---
title: MSSQLSERVER_1105 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1105 (Database Engine error)
ms.assetid: e7f4ad02-8c7f-4bb9-9781-2c86253f2138
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: dea326fab7edd6a5c155c8f0182bffc044505eb5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655255"
---
# <a name="mssqlserver_1105"></a><span data-ttu-id="c3f23-102">MSSQLSERVER_1105</span><span class="sxs-lookup"><span data-stu-id="c3f23-102">MSSQLSERVER_1105</span></span>
    
## <a name="details"></a><span data-ttu-id="c3f23-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="c3f23-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c3f23-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="c3f23-104">Product Name</span></span>|<span data-ttu-id="c3f23-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c3f23-105">SQL Server</span></span>|  
|<span data-ttu-id="c3f23-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="c3f23-106">Event ID</span></span>|<span data-ttu-id="c3f23-107">1105</span><span class="sxs-lookup"><span data-stu-id="c3f23-107">1105</span></span>|  
|<span data-ttu-id="c3f23-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="c3f23-108">Event Source</span></span>|<span data-ttu-id="c3f23-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c3f23-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c3f23-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="c3f23-110">Component</span></span>|<span data-ttu-id="c3f23-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="c3f23-111">SQLEngine</span></span>|  
|<span data-ttu-id="c3f23-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="c3f23-112">Symbolic Name</span></span>|<span data-ttu-id="c3f23-113">NO_MORE_SPACE_IN_FG</span><span class="sxs-lookup"><span data-stu-id="c3f23-113">NO_MORE_SPACE_IN_FG</span></span>|  
|<span data-ttu-id="c3f23-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="c3f23-114">Message Text</span></span>|<span data-ttu-id="c3f23-115">Не удалось выделить место для объекта '%.\*ls'%.\*ls в базе данных '%.\*ls', так как файловая группа '%.\*ls' переполнена.</span><span class="sxs-lookup"><span data-stu-id="c3f23-115">Could not allocate space for object '%.\*ls'%.\*ls in database '%.\*ls' because the '%.\*ls' filegroup is full.</span></span> <span data-ttu-id="c3f23-116">Выделите место на диске, удалив ненужные файлы или объекты в файловой группе, добавив дополнительные файлы в файловую группу или указав параметр автоматического увеличения размера для существующих файлов в файловой группе.</span><span class="sxs-lookup"><span data-stu-id="c3f23-116">Create disk space by deleting unneeded files, dropping objects in the filegroup, adding additional files to the filegroup, or setting autogrowth on for existing files in the filegroup.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c3f23-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="c3f23-117">Explanation</span></span>  
 <span data-ttu-id="c3f23-118">Нет свободного места на диске в файловой группе.</span><span class="sxs-lookup"><span data-stu-id="c3f23-118">No disk space is available in a filegroup.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c3f23-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="c3f23-119">User Action</span></span>  
 <span data-ttu-id="c3f23-120">Место в файловой группе можно освободить следующим образом.</span><span class="sxs-lookup"><span data-stu-id="c3f23-120">The following actions may make space available in the filegroup:</span></span>  
  
-   <span data-ttu-id="c3f23-121">Включить автоувеличение.</span><span class="sxs-lookup"><span data-stu-id="c3f23-121">Turn on autogrow.</span></span>  
  
-   <span data-ttu-id="c3f23-122">Добавить файлы в файловую группу.</span><span class="sxs-lookup"><span data-stu-id="c3f23-122">Add more files to the file group.</span></span>  
  
-   <span data-ttu-id="c3f23-123">Освободить место на диске, удалив ненужные индексы или таблицы.</span><span class="sxs-lookup"><span data-stu-id="c3f23-123">Free disk space by dropping index or tables that are no longer needed.</span></span>  
  
-   <span data-ttu-id="c3f23-124">Дополнительные сведения см. в разделе «Диагностика недостатка места на диске» электронной документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c3f23-124">For more information, see "Troubleshooting Insufficient Data Disk Space" in SQL Server Books Online.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c3f23-125">Когда индекс располагается в нескольких файлах, `ALTER INDEX REORGANIZE` может вернуть ошибку 1105 при заполнении одного их файлов.</span><span class="sxs-lookup"><span data-stu-id="c3f23-125">When an index is located on several files, `ALTER INDEX REORGANIZE` can return error 1105 when one of the files is full.</span></span> <span data-ttu-id="c3f23-126">Процесс реорганизации блокируется, если процесс пытается переместить строки в полный файл.</span><span class="sxs-lookup"><span data-stu-id="c3f23-126">The reorganization process is blocked when the process tries to move rows to the full file.</span></span> <span data-ttu-id="c3f23-127">Чтобы обойти это ограничение, выполните `ALTER INDEX REBUILD` вместо `ALTER INDEX REORGANIZE` или увеличьте ограничение на рост файла всех заполненных файлов.</span><span class="sxs-lookup"><span data-stu-id="c3f23-127">To work around this limitation perform an `ALTER INDEX REBUILD` instead of `ALTER INDEX REORGANIZE` or increase the file growth limit of any files that are full.</span></span>  
  
  
