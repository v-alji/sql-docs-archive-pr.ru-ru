---
title: MSSQLSERVER_3176 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3176 (Database Engine error)
ms.assetid: 4be24c64-2d52-4cb4-b4d7-36efbe4555b6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 64e1a836995fe8738bb5c2ff0cb4de10d84d1f29
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664239"
---
# <a name="mssqlserver_3176"></a><span data-ttu-id="db9b4-102">MSSQLSERVER_3176</span><span class="sxs-lookup"><span data-stu-id="db9b4-102">MSSQLSERVER_3176</span></span>
    
## <a name="details"></a><span data-ttu-id="db9b4-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="db9b4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="db9b4-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="db9b4-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="db9b4-105">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="db9b4-105">Event ID</span></span>|<span data-ttu-id="db9b4-106">3176</span><span class="sxs-lookup"><span data-stu-id="db9b4-106">3176</span></span>|  
|<span data-ttu-id="db9b4-107">Источник события</span><span class="sxs-lookup"><span data-stu-id="db9b4-107">Event Source</span></span>|<span data-ttu-id="db9b4-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="db9b4-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="db9b4-109">Компонент</span><span class="sxs-lookup"><span data-stu-id="db9b4-109">Component</span></span>|<span data-ttu-id="db9b4-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="db9b4-110">SQLEngine</span></span>|  
|<span data-ttu-id="db9b4-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="db9b4-111">Symbolic Name</span></span>|<span data-ttu-id="db9b4-112">LDDB_FILE_CLAIM</span><span class="sxs-lookup"><span data-stu-id="db9b4-112">LDDB_FILE_CLAIM</span></span>|  
|<span data-ttu-id="db9b4-113">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="db9b4-113">Message Text</span></span>|<span data-ttu-id="db9b4-114">Файл «%ls» запрошен «%ls»(%d) и «%ls»(%d).</span><span class="sxs-lookup"><span data-stu-id="db9b4-114">File '%ls' is claimed by '%ls'(%d) and '%ls'(%d).</span></span> <span data-ttu-id="db9b4-115">Переместить один или несколько файлов можно с помощью предложения WITH MOVE.</span><span class="sxs-lookup"><span data-stu-id="db9b4-115">The WITH MOVE clause can be used to relocate one or more files.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="db9b4-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="db9b4-116">Explanation</span></span>  
 <span data-ttu-id="db9b4-117">Попытка использовать файл для нескольких целей.</span><span class="sxs-lookup"><span data-stu-id="db9b4-117">Attempting to use a file for more than one purpose.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="db9b4-118">Возможные причины</span><span class="sxs-lookup"><span data-stu-id="db9b4-118">Possible Causes</span></span>  
 <span data-ttu-id="db9b4-119">В другой базе данных уже используется это имя файла.</span><span class="sxs-lookup"><span data-stu-id="db9b4-119">Another database is already using the file name.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="db9b4-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="db9b4-120">User Action</span></span>  
 <span data-ttu-id="db9b4-121">Восстановите файлы базы данных в другое место.</span><span class="sxs-lookup"><span data-stu-id="db9b4-121">Restore the database files to a different location.</span></span> <span data-ttu-id="db9b4-122">Переместите каждый файл с помощью предложения WITH MOVE инструкции RESTORE.</span><span class="sxs-lookup"><span data-stu-id="db9b4-122">In a RESTORE statement, use a WITH MOVE clause to move each file.</span></span> <span data-ttu-id="db9b4-123">В [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] измените расположения файлов в сетке **Восстановить файлы базы данных как** диалогового окна **Параметры восстановления базы данных**.</span><span class="sxs-lookup"><span data-stu-id="db9b4-123">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], change the file locations in the **Restore the database files as** grid of the **Restore Database Options** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db9b4-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="db9b4-124">See Also</span></span>  
 <span data-ttu-id="db9b4-125">[Восстановление базы данных в новое место (SQL Server)](../backup-restore/restore-a-database-to-a-new-location-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="db9b4-125">[Restore a Database to a New Location &#40;SQL Server&#41;](../backup-restore/restore-a-database-to-a-new-location-sql-server.md) </span></span>  
 <span data-ttu-id="db9b4-126">[Восстановление файлов в новое расположение &#40;SQL Server&#41;](../backup-restore/restore-files-to-a-new-location-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="db9b4-126">[Restore Files to a New Location &#40;SQL Server&#41;](../backup-restore/restore-files-to-a-new-location-sql-server.md) </span></span>  
 [<span data-ttu-id="db9b4-127">RESTORE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="db9b4-127">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
