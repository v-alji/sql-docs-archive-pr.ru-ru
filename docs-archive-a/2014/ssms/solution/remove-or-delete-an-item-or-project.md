---
title: Перемещение или удаление элемента или проекта | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- deleting project items
- projects [SQL Server Management Studio], item removal
- removing project items
ms.assetid: 3fd92434-70f5-466e-bef0-7e0fd73ddb1c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 679911f15d6c47f4274180602a5376c4ec03c77b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658027"
---
# <a name="remove-or-delete-an-item-or-project"></a><span data-ttu-id="db720-102">Перемещение или удаление элемента или проекта</span><span class="sxs-lookup"><span data-stu-id="db720-102">Remove or Delete an Item or Project</span></span>
  <span data-ttu-id="db720-103">Элементами проекта в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] являются очереди, соединения и различные файлы.</span><span class="sxs-lookup"><span data-stu-id="db720-103">Project items in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] projects are Queries, Connections, and Miscellaneous files.</span></span> <span data-ttu-id="db720-104">Запросы и прочие файлы проектов можно удалять из решения без удаления соответствующих им файлов из хранилища.</span><span class="sxs-lookup"><span data-stu-id="db720-104">You can remove project queries and miscellaneous files from your solution without erasing the files from storage.</span></span> <span data-ttu-id="db720-105">Переместите проект или элемент, если он не нужен в текущем решении, но его надо использовать в другом решении.</span><span class="sxs-lookup"><span data-stu-id="db720-105">Remove a project or item when it is not useful in the current solution but you want to include it in another solution.</span></span>  
  
### <a name="to-remove-a-project-item"></a><span data-ttu-id="db720-106">Исключение элемента проекта</span><span class="sxs-lookup"><span data-stu-id="db720-106">To remove a project item</span></span>  
  
1.  <span data-ttu-id="db720-107">В обозревателе решений выберите элемент проекта, который требуется исключить.</span><span class="sxs-lookup"><span data-stu-id="db720-107">In Solution Explorer, select the project item you want to remove.</span></span>  
  
2.  <span data-ttu-id="db720-108">В меню **Правка** выберите пункт **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="db720-108">On the **Edit** menu, click **Remove**.</span></span>  
  
3.  <span data-ttu-id="db720-109">В диалоговом окне подтверждения нажмите кнопку **Удалить** для исключения элемента из проекта.</span><span class="sxs-lookup"><span data-stu-id="db720-109">On the confirmation dialog, click **Remove** to remove the item from the project.</span></span>  
  
 <span data-ttu-id="db720-110">Исключенный элемент продолжает существовать в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="db720-110">A removed item still exists on the file system.</span></span> <span data-ttu-id="db720-111">Поэтому исключенный элемент можно вновь добавить в исходное или другое решение.</span><span class="sxs-lookup"><span data-stu-id="db720-111">Therefore, you can add a removed item to its original solution or to another solution.</span></span>  
  
#### <a name="to-remove-a-project"></a><span data-ttu-id="db720-112">Исключение проекта</span><span class="sxs-lookup"><span data-stu-id="db720-112">To remove a project</span></span>  
  
1.  <span data-ttu-id="db720-113">В обозревателе решений выберите проект, который требуется исключить.</span><span class="sxs-lookup"><span data-stu-id="db720-113">In Solution Explorer, select the project you want to remove.</span></span>  
  
2.  <span data-ttu-id="db720-114">В меню **Правка** выберите пункт **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="db720-114">On the **Edit** menu, click **Remove**.</span></span>  
  
3.  <span data-ttu-id="db720-115">В диалоговом окне подтверждения нажмите кнопку **ОК**для исключения проекта из решения.</span><span class="sxs-lookup"><span data-stu-id="db720-115">On the confirmation dialog, click **OK**, to remove the project from the solution.</span></span>  
  
 <span data-ttu-id="db720-116">Проект можно удалить окончательно, но для этого сначала необходимо удалить все ссылки на проект из решений среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , а затем с помощью проводника [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows окончательно удалить связанные с проектом файлы из хранилища.</span><span class="sxs-lookup"><span data-stu-id="db720-116">You can delete a project permanently, but you first need to remove any references to the project from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] solutions, and then use [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Explorer to permanently delete the associated files from storage.</span></span>  
  
#### <a name="to-delete-a-project"></a><span data-ttu-id="db720-117">Удаление проекта</span><span class="sxs-lookup"><span data-stu-id="db720-117">To delete a project</span></span>  
  
1.  <span data-ttu-id="db720-118">В обозревателе решений исключите из решения проект, который требуется удалить окончательно.</span><span class="sxs-lookup"><span data-stu-id="db720-118">In Solution Explorer, remove the project you want to delete from the solution.</span></span>  
  
2.  <span data-ttu-id="db720-119">В проводнике Windows найдите и выделите файлы, связанные с проектом или элементом, который требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="db720-119">In Windows Explorer, locate and select the files associated with the project or item you want to delete.</span></span>  
  
3.  <span data-ttu-id="db720-120">В меню **Файл** выберите пункт **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="db720-120">On the **File** menu, click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db720-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="db720-121">See Also</span></span>  
 <span data-ttu-id="db720-122">[обозреватель решений](solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="db720-122">[Solution Explorer](solution-explorer.md) </span></span>  
 <span data-ttu-id="db720-123">[Добавление новых элементов в проект](add-new-items-to-a-project.md) </span><span class="sxs-lookup"><span data-stu-id="db720-123">[Add New Items to a Project](add-new-items-to-a-project.md) </span></span>  
 [<span data-ttu-id="db720-124">Добавление существующих элементов в проект</span><span class="sxs-lookup"><span data-stu-id="db720-124">Add Existing Items to a Project</span></span>](add-existing-items-to-a-project.md)  
  
  
