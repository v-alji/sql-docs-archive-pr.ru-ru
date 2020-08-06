---
title: MSSQLSERVER_3156 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3156 (Database Engine error)
ms.assetid: 345d8ed4-177e-4ec3-bab3-25d30000e323
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 25b5a037012a6d6b47b91e763a49cfb67b89f43c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664243"
---
# <a name="mssqlserver_3156"></a><span data-ttu-id="0a721-102">MSSQLSERVER_3156</span><span class="sxs-lookup"><span data-stu-id="0a721-102">MSSQLSERVER_3156</span></span>
    
## <a name="details"></a><span data-ttu-id="0a721-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="0a721-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0a721-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="0a721-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="0a721-105">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="0a721-105">Event ID</span></span>|<span data-ttu-id="0a721-106">3156</span><span class="sxs-lookup"><span data-stu-id="0a721-106">3156</span></span>|  
|<span data-ttu-id="0a721-107">Источник события</span><span class="sxs-lookup"><span data-stu-id="0a721-107">Event Source</span></span>|<span data-ttu-id="0a721-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0a721-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0a721-109">Компонент</span><span class="sxs-lookup"><span data-stu-id="0a721-109">Component</span></span>|<span data-ttu-id="0a721-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0a721-110">SQLEngine</span></span>|  
|<span data-ttu-id="0a721-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="0a721-111">Symbolic Name</span></span>|<span data-ttu-id="0a721-112">LDDB_CANT_WRITE</span><span class="sxs-lookup"><span data-stu-id="0a721-112">LDDB_CANT_WRITE</span></span>|  
|<span data-ttu-id="0a721-113">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="0a721-113">Message Text</span></span>|<span data-ttu-id="0a721-114">Невозможно восстановить файл «%ls» до «%ls».</span><span class="sxs-lookup"><span data-stu-id="0a721-114">File '%ls' cannot be restored to '%ls'.</span></span> <span data-ttu-id="0a721-115">Укажите допустимое расположение для файла с помощью предложения WITH MOVE.</span><span class="sxs-lookup"><span data-stu-id="0a721-115">Use WITH MOVE to identify a valid location for the file.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0a721-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="0a721-116">Explanation</span></span>  
 <span data-ttu-id="0a721-117">Это общее сообщение идентифицирует логические или физические имена файлов, которые не удалось восстановить из-за ошибок в заданном расположении.</span><span class="sxs-lookup"><span data-stu-id="0a721-117">This general message identifies the logical or physical file names of files that could not be restored because of a problem with the specified location.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="0a721-118">Возможные причины</span><span class="sxs-lookup"><span data-stu-id="0a721-118">Possible Causes</span></span>  
 <span data-ttu-id="0a721-119">Ниже приведены возможные причины.</span><span class="sxs-lookup"><span data-stu-id="0a721-119">The possible causes include the following:</span></span>  
  
-   <span data-ttu-id="0a721-120">Возможно, необходим доступ к указанному каталогу Windows.</span><span class="sxs-lookup"><span data-stu-id="0a721-120">You might need access to the specified Windows directory.</span></span>  
  
-   <span data-ttu-id="0a721-121">Возможно, введен или указан несуществующий путь.</span><span class="sxs-lookup"><span data-stu-id="0a721-121">You might have mistyped the path or specified a path that does not exist.</span></span>  
  
-   <span data-ttu-id="0a721-122">Указано имя файла, который недоступен для перезаписи.</span><span class="sxs-lookup"><span data-stu-id="0a721-122">The file name might be being used by a file that cannot be overwritten.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0a721-123">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="0a721-123">User Action</span></span>  
 <span data-ttu-id="0a721-124">Найдите в журналах ошибок другие сообщения, содержащие дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="0a721-124">Look at the error logs for other messages that provide more details.</span></span>  
  
 <span data-ttu-id="0a721-125">Устраните неполадку, связанную с указанным расположением. Для этого, например, предоставьте необходимые права доступа или измените расположение файла с помощью параметра WITH MOVE предложения RESTORE.</span><span class="sxs-lookup"><span data-stu-id="0a721-125">Correct the problem with the specified location, for example, by granting access, or use the WITH MOVE option in your RESTORE statement to relocate the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a721-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="0a721-126">See Also</span></span>  
 <span data-ttu-id="0a721-127">[Восстановление базы данных в новое место (SQL Server)](../backup-restore/restore-a-database-to-a-new-location-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0a721-127">[Restore a Database to a New Location &#40;SQL Server&#41;](../backup-restore/restore-a-database-to-a-new-location-sql-server.md) </span></span>  
 <span data-ttu-id="0a721-128">[Восстановление файлов в новое расположение &#40;SQL Server&#41;](../backup-restore/restore-files-to-a-new-location-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0a721-128">[Restore Files to a New Location &#40;SQL Server&#41;](../backup-restore/restore-files-to-a-new-location-sql-server.md) </span></span>  
 [<span data-ttu-id="0a721-129">RESTORE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0a721-129">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
