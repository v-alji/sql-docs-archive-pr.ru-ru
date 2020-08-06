---
title: Просмотр списка измененных файлов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- VisualStudio.SourceControl.CheckinWindow
helpviewer_keywords:
- listing modified files
- modified files list [SQL Server]
- checking in files
ms.assetid: 1b053719-8500-4300-a169-fffca5801dd0
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: a2899ab9889908089d17b3c929e7bf4b2dfe2185
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666723"
---
# <a name="view-a-list-of-modified-files"></a><span data-ttu-id="2703b-102">Просмотр списка измененных файлов</span><span class="sxs-lookup"><span data-stu-id="2703b-102">View a List of Modified Files</span></span>
  <span data-ttu-id="2703b-103">Можно использовать окно « **возвраты** », чтобы в любое время отобразить список извлеченных файлов в текущем решении, а затем вернуть эти файлы одним нажатием кнопки.</span><span class="sxs-lookup"><span data-stu-id="2703b-103">You can use the **Pending Checkins** window to display at all times a list of the checked-out files in the current solution, and to check in these files with a single button click.</span></span>  
  
### <a name="to-view-a-list-of-modified-files"></a><span data-ttu-id="2703b-104">Просмотр списка измененных файлов</span><span class="sxs-lookup"><span data-stu-id="2703b-104">To view a list of modified files</span></span>  
  
1.  <span data-ttu-id="2703b-105">В меню **вид** выберите пункт **отложенные возвраты**.</span><span class="sxs-lookup"><span data-stu-id="2703b-105">On the **View** menu, click **Pending Checkins**.</span></span>  
  
2.  <span data-ttu-id="2703b-106">Чтобы вернуть выбранные файлы, нажмите кнопку **вернуть**.</span><span class="sxs-lookup"><span data-stu-id="2703b-106">To check in the selected files, click **Check In**.</span></span> <span data-ttu-id="2703b-107">Кроме того, можно закрепить окно **извлеченных** элементов в правой части [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] среды, чтобы после завершения работы можно было вернуть файлы.</span><span class="sxs-lookup"><span data-stu-id="2703b-107">Alternatively, you can dock the **Pending Checkins** window on the right side of the [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environment so that you can check in the files when you are finished working.</span></span>  
  
     <span data-ttu-id="2703b-108">**Зарегистрируйся**</span><span class="sxs-lookup"><span data-stu-id="2703b-108">**Check In**</span></span>  
     <span data-ttu-id="2703b-109">Возвраты в решении.</span><span class="sxs-lookup"><span data-stu-id="2703b-109">Checks in the solution.</span></span>  
  
     <span data-ttu-id="2703b-110">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="2703b-110">**Comments**</span></span>  
     <span data-ttu-id="2703b-111">Сопровождает предстоящий возврат простым текстовым комментарием.</span><span class="sxs-lookup"><span data-stu-id="2703b-111">Associates a plain text comment with the pending check in.</span></span> <span data-ttu-id="2703b-112">Комментарий создается и ассоциируется с каждой версией проекта и хранится в базе данных системы управления версиями.</span><span class="sxs-lookup"><span data-stu-id="2703b-112">A comment is created and associated with each version of a project, and stored in the source control database.</span></span>  
  
     <span data-ttu-id="2703b-113">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="2703b-113">**Options**</span></span>  
     <span data-ttu-id="2703b-114">Указывает действия, которые должны выполняться системой управления версиями при нажатии кнопки " **вернуть** ".</span><span class="sxs-lookup"><span data-stu-id="2703b-114">Specifies the actions that source control should take when you click the **Check In** button.</span></span>  
  
    -   <span data-ttu-id="2703b-115">**Оставить все незарегистрированным**</span><span class="sxs-lookup"><span data-stu-id="2703b-115">**Keep All Checked Out**</span></span>  
  
         <span data-ttu-id="2703b-116">Указывает на то, что произведенные изменения должны записываться поставщиком системы управления версиями, но файлы должны оставаться извлеченными.</span><span class="sxs-lookup"><span data-stu-id="2703b-116">Specifies that your changes should be written to the source control provider but that the files should remain checked out.</span></span>  
  
     <span data-ttu-id="2703b-117">**Sort**</span><span class="sxs-lookup"><span data-stu-id="2703b-117">**Sort**</span></span>  
     <span data-ttu-id="2703b-118">Указывает порядок сортировки для столбцов, отображаемых в списке элементов.</span><span class="sxs-lookup"><span data-stu-id="2703b-118">Specifies the sort order for the columns displayed in the Items list.</span></span>  
  
     <span data-ttu-id="2703b-119">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="2703b-119">**Columns**</span></span>  
     <span data-ttu-id="2703b-120">Отображает список столбцов, которые возможно добавить в список элементов в этом окне.</span><span class="sxs-lookup"><span data-stu-id="2703b-120">Displays a list of the columns you can add to the window's Items list.</span></span>  
  
     <span data-ttu-id="2703b-121">**Представление в виде дерева**</span><span class="sxs-lookup"><span data-stu-id="2703b-121">**Tree View**</span></span>  
     <span data-ttu-id="2703b-122">Отображает иерархию папок и файлов для решения или проекта, возвращаемого пользователем.</span><span class="sxs-lookup"><span data-stu-id="2703b-122">Displays the folder and file hierarchy for the solution or project you are checking in.</span></span>  
  
     <span data-ttu-id="2703b-123">**Плоское представление**</span><span class="sxs-lookup"><span data-stu-id="2703b-123">**Flat View**</span></span>  
     <span data-ttu-id="2703b-124">Отображает возвращаемые файлы как плоские списки при соединении с их системой управления версиями.</span><span class="sxs-lookup"><span data-stu-id="2703b-124">Displays the files you are checking in as flat lists under their source control connection.</span></span>  
  
     <span data-ttu-id="2703b-125">**Сравнить версии**</span><span class="sxs-lookup"><span data-stu-id="2703b-125">**Compare Versions**</span></span>  
     <span data-ttu-id="2703b-126">Открывает диалоговое окно **Параметры разницы** в Visual SourceSafe, которое сравнивает выбранный файл в проекте среды разработки с любым другим выбранным файлом и показывает различия, если они есть.</span><span class="sxs-lookup"><span data-stu-id="2703b-126">Opens the Visual SourceSafe **Difference Options** dialog box, which compares a selected file in your development environment project to any other selected file and shows you the differences, if any.</span></span>  
  
     <span data-ttu-id="2703b-127">**Отменить извлечение**</span><span class="sxs-lookup"><span data-stu-id="2703b-127">**Undo checkout**</span></span>  
     <span data-ttu-id="2703b-128">Отменяет извлечение всех элементов, выбранных в окне " **незавершенные возвраты** ".</span><span class="sxs-lookup"><span data-stu-id="2703b-128">Reverses the checkout of all items selected in the **Pending Checkins** window.</span></span>  
  
     <span data-ttu-id="2703b-129">**имя**;</span><span class="sxs-lookup"><span data-stu-id="2703b-129">**Name**</span></span>  
     <span data-ttu-id="2703b-130">Отображает список имен элементов, доступных для возврата.</span><span class="sxs-lookup"><span data-stu-id="2703b-130">Displays a list of the items available for check in.</span></span> <span data-ttu-id="2703b-131">Напротив элементов отображаются установленные флажки.</span><span class="sxs-lookup"><span data-stu-id="2703b-131">Items appear with the check box next to them selected.</span></span> <span data-ttu-id="2703b-132">Если необходимо возвращать конкретный элемент, снимите флажок рядом с ним.</span><span class="sxs-lookup"><span data-stu-id="2703b-132">If you do not want to check in a particular item, clear the check box next to it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2703b-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="2703b-133">See Also</span></span>  
 <span data-ttu-id="2703b-134">[Управление возвратами](../../2014/database-engine/manage-checkins.md) </span><span class="sxs-lookup"><span data-stu-id="2703b-134">[Manage Checkins](../../2014/database-engine/manage-checkins.md) </span></span>  
 [<span data-ttu-id="2703b-135">Управление извлечениями</span><span class="sxs-lookup"><span data-stu-id="2703b-135">Manage Checkouts</span></span>](../../2014/database-engine/manage-checkouts.md)  
  
  
