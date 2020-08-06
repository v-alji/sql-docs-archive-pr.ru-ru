---
title: Управление извлечением | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- source controls [SQL Server Management Studio], checkouts
- checkouts [SQL Server Management Studio]
- checking out files
ms.assetid: ddd4adba-d432-4005-9cb2-bb9ee3163d8e
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cdfa25cdc27e707d4be705e66b215130c9d70ce1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669036"
---
# <a name="manage-checkouts"></a><span data-ttu-id="c85ac-102">Управление извлечениями</span><span class="sxs-lookup"><span data-stu-id="c85ac-102">Manage Checkouts</span></span>
  <span data-ttu-id="c85ac-103">После того как файл был добавлен к системе управления версиями, для изменения этого файла его нужно извлечь.</span><span class="sxs-lookup"><span data-stu-id="c85ac-103">After a file has been added to source control, you must check out the file before you can modify it.</span></span> <span data-ttu-id="c85ac-104">Когда извлекается файл из управления версиями, поставщик управления версиями создает его последнюю версию на локальном диске и снимает с этого файла атрибут «Только для чтения».</span><span class="sxs-lookup"><span data-stu-id="c85ac-104">When you check a file out of source control, the source control provider creates a copy of the latest version on your local disk and removes the read-only attribute of the file.</span></span> <span data-ttu-id="c85ac-105">В некоторых случаях нужно изменить файл, не извлекая его.</span><span class="sxs-lookup"><span data-stu-id="c85ac-105">In some circumstances you might need to edit a file without checking out the file.</span></span> <span data-ttu-id="c85ac-106">Дополнительные сведения об изменении файла без проверки файла см. [в разделе изменение возвращенных файлов](../../2014/database-engine/edit-checked-in-files.md).</span><span class="sxs-lookup"><span data-stu-id="c85ac-106">For more information about editing a file without checking the file out, see [Edit Checked-In Files](../../2014/database-engine/edit-checked-in-files.md).</span></span>  
  
 <span data-ttu-id="c85ac-107">Можно использовать [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] для извлечения файлов вручную или автоматически.</span><span class="sxs-lookup"><span data-stu-id="c85ac-107">You can use [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to check out files manually or automatically.</span></span> <span data-ttu-id="c85ac-108">Вы извлекаете файлы вручную, открыв решение, содержащее файлы в [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] среде, и выбрав команду **извлечь** .</span><span class="sxs-lookup"><span data-stu-id="c85ac-108">You check out files manually by opening the solution that contains the files in the [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environment, and then clicking the **Check Out** command.</span></span> <span data-ttu-id="c85ac-109">Файлы будут извлекаться автоматически, если настроить среду [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] для автоматического извлечения файлов.</span><span class="sxs-lookup"><span data-stu-id="c85ac-109">You can check out files automatically if you configure the [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environment to do so.</span></span>  
  
 <span data-ttu-id="c85ac-110">В зависимости от параметров, которые администратор устанавливает для поставщика управления источниками, файлы можно извлекать в монопольном режиме или в режиме общего доступа.</span><span class="sxs-lookup"><span data-stu-id="c85ac-110">Depending on the options that your administrator sets on your source control provider, you can also check out files in exclusive or shared mode.</span></span> <span data-ttu-id="c85ac-111">Если вы извлекаете файл для исключительного доступа, то изменить его можете только вы, и ни один другой пользователь не может извлечь этот файл, пока он не будет возвращен.</span><span class="sxs-lookup"><span data-stu-id="c85ac-111">When you check out a file exclusively, only you can modify it, and no other user can check out the file until you check it in.</span></span> <span data-ttu-id="c85ac-112">Если файл извлекается в режиме общего доступа, то извлечь этот файл может любое количество пользователей.</span><span class="sxs-lookup"><span data-stu-id="c85ac-112">When you check out a file in shared mode, any number of users can check out the same file.</span></span> <span data-ttu-id="c85ac-113">Когда каждый пользователь возвращает файл, поставщик управления версиями пытается выполнить его слияние с последней серверной версией этого файла.</span><span class="sxs-lookup"><span data-stu-id="c85ac-113">As each user checks in the file, the source control provider attempts to merge the file with the latest server version of the file.</span></span> <span data-ttu-id="c85ac-114">Если возникают конфликты между возвращаемой версией файла и его последней версией, поставщик управления версиями предлагает пользователю разрешить этот конфликт.</span><span class="sxs-lookup"><span data-stu-id="c85ac-114">If conflicts arise between the version that is being checked in and the latest version, the source control provider prompts the user to resolve the conflicts.</span></span>  
  
 <span data-ttu-id="c85ac-115">В следующей таблице описаны подразделы, содержащиеся в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="c85ac-115">The following table describes the topics in this section.</span></span>  
  
|<span data-ttu-id="c85ac-116">Раздел</span><span class="sxs-lookup"><span data-stu-id="c85ac-116">Topic</span></span>|<span data-ttu-id="c85ac-117">Описание</span><span class="sxs-lookup"><span data-stu-id="c85ac-117">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="c85ac-118">Извлечение файлов</span><span class="sxs-lookup"><span data-stu-id="c85ac-118">Check Out Files</span></span>](../../2014/database-engine/check-out-files.md)|<span data-ttu-id="c85ac-119">Инструкции по извлечению файла для его изменения.</span><span class="sxs-lookup"><span data-stu-id="c85ac-119">Provides instructions on how to check out a file so you can modify it.</span></span>|  
|[<span data-ttu-id="c85ac-120">Отмена извлечения</span><span class="sxs-lookup"><span data-stu-id="c85ac-120">Undo Checkouts</span></span>](../../2014/database-engine/undo-checkouts.md)|<span data-ttu-id="c85ac-121">Отмена существующего извлечения.</span><span class="sxs-lookup"><span data-stu-id="c85ac-121">Explains how to cancel an existing checkout.</span></span>|  
|[<span data-ttu-id="c85ac-122">Автоматическое извлечение файлов при изменении</span><span class="sxs-lookup"><span data-stu-id="c85ac-122">Automatically Check Out Files Upon Edit</span></span>](../../2014/database-engine/automatically-check-out-files-upon-edit.md)|<span data-ttu-id="c85ac-123">Конфигурирование системы управления версиями для извлечения файла, если его начинают изменять.</span><span class="sxs-lookup"><span data-stu-id="c85ac-123">Explains how to configure source control to check out a file when you start to edit it.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c85ac-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="c85ac-124">See Also</span></span>  
 <span data-ttu-id="c85ac-125">[Управление возвратами](../../2014/database-engine/manage-checkins.md) </span><span class="sxs-lookup"><span data-stu-id="c85ac-125">[Manage Checkins](../../2014/database-engine/manage-checkins.md) </span></span>  
 [<span data-ttu-id="c85ac-126">Изменение возвращенных файлов</span><span class="sxs-lookup"><span data-stu-id="c85ac-126">Edit Checked-In Files</span></span>](../../2014/database-engine/edit-checked-in-files.md)  
  
  
