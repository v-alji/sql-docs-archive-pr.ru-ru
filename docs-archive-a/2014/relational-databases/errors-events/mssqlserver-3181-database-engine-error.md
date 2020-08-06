---
title: MSSQLSERVER_3181 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3181 (Database Engine error)
ms.assetid: e6d2e716-5263-477c-ad0e-7bcbfef4c1f3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f18509d9a18ba8be1f4e40c93bff5abfcae3d69c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664238"
---
# <a name="mssqlserver_3181"></a><span data-ttu-id="8e101-102">MSSQLSERVER_3181</span><span class="sxs-lookup"><span data-stu-id="8e101-102">MSSQLSERVER_3181</span></span>
    
## <a name="details"></a><span data-ttu-id="8e101-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="8e101-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8e101-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="8e101-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="8e101-105">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="8e101-105">Event ID</span></span>|<span data-ttu-id="8e101-106">3181</span><span class="sxs-lookup"><span data-stu-id="8e101-106">3181</span></span>|  
|<span data-ttu-id="8e101-107">Источник события</span><span class="sxs-lookup"><span data-stu-id="8e101-107">Event Source</span></span>|<span data-ttu-id="8e101-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8e101-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8e101-109">Компонент</span><span class="sxs-lookup"><span data-stu-id="8e101-109">Component</span></span>|<span data-ttu-id="8e101-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="8e101-110">SQLEngine</span></span>|  
|<span data-ttu-id="8e101-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="8e101-111">Symbolic Name</span></span>|<span data-ttu-id="8e101-112">LDDB_STORAGE_VERIFY</span><span class="sxs-lookup"><span data-stu-id="8e101-112">LDDB_STORAGE_VERIFY</span></span>|  
|<span data-ttu-id="8e101-113">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="8e101-113">Message Text</span></span>|<span data-ttu-id="8e101-114">Попытка восстановления из этой резервной копии может привести к недостатку места на диске.</span><span class="sxs-lookup"><span data-stu-id="8e101-114">Attempting to restore this backup may encounter storage space problems.</span></span> <span data-ttu-id="8e101-115">Подробные сведения будут приведены в следующих сообщениях.</span><span class="sxs-lookup"><span data-stu-id="8e101-115">Subsequent messages will provide details.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8e101-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="8e101-116">Explanation</span></span>  
 <span data-ttu-id="8e101-117">Инструкция RESTORE VERIFYONLY проверяет доступное место на диске, где будет восстанавливаться база данных.</span><span class="sxs-lookup"><span data-stu-id="8e101-117">The RESTORE VERIFYONLY statement checks the available storage space on the disk to which the database is to be restored.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="8e101-118">Возможные причины</span><span class="sxs-lookup"><span data-stu-id="8e101-118">Possible Causes</span></span>  
 <span data-ttu-id="8e101-119">Может быть, недостаточно места на диске для восстановления проверяемой резервной копии.</span><span class="sxs-lookup"><span data-stu-id="8e101-119">The available disk space may be insufficient to restore the backup being verified.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8e101-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="8e101-120">User Action</span></span>  
 <span data-ttu-id="8e101-121">Восстановить резервную копию в расположении, где достаточно места на диске, либо обеспечить больше места на диске.</span><span class="sxs-lookup"><span data-stu-id="8e101-121">Restore the backup to a location with sufficient disk space, or provide more space on the disk.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e101-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="8e101-122">See Also</span></span>  
 <span data-ttu-id="8e101-123">[Восстановление базы данных в новое место (SQL Server)](../backup-restore/restore-a-database-to-a-new-location-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="8e101-123">[Restore a Database to a New Location &#40;SQL Server&#41;](../backup-restore/restore-a-database-to-a-new-location-sql-server.md) </span></span>  
 <span data-ttu-id="8e101-124">[Восстановление файлов в новое расположение &#40;SQL Server&#41;](../backup-restore/restore-files-to-a-new-location-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="8e101-124">[Restore Files to a New Location &#40;SQL Server&#41;](../backup-restore/restore-files-to-a-new-location-sql-server.md) </span></span>  
 <span data-ttu-id="8e101-125">[RESTORE (Transact-SQL)](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8e101-125">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="8e101-126">RESTORE VERIFYONLY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="8e101-126">RESTORE VERIFYONLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql)  
  
  
