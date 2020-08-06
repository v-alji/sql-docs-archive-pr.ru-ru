---
title: Извлечение файлов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- Visual Studio.SourceControl.CheckOutDialog
helpviewer_keywords:
- checking out files
ms.assetid: cc033727-51bb-4b58-a12b-8977ce61ff56
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 151f554742bd6c381b27b58155d3f0e40e9eeb0e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665583"
---
# <a name="check-out-files"></a><span data-ttu-id="deb1a-102">Извлечение файлов</span><span class="sxs-lookup"><span data-stu-id="deb1a-102">Check Out Files</span></span>
  <span data-ttu-id="deb1a-103">Если в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] не разрешено изменение возвращенных файлов, то перед изменением файла его необходимо извлечь.</span><span class="sxs-lookup"><span data-stu-id="deb1a-103">Unless you have configured the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] environment to permit checked-in files to be edited, you must check out a file before you can modify it.</span></span> <span data-ttu-id="deb1a-104">После извлечения файла его версия копируется на локальный диск, а атрибут файла «Только для чтения» снимается.</span><span class="sxs-lookup"><span data-stu-id="deb1a-104">When you check out a file, a copy of the file version is copied to your local disk, and the read-only attribute of the file is removed.</span></span>  
  
 <span data-ttu-id="deb1a-105">Файлы можно извлекать в монопольном режиме или в режиме общего доступа.</span><span class="sxs-lookup"><span data-stu-id="deb1a-105">You can check files out either exclusively or in shared mode.</span></span> <span data-ttu-id="deb1a-106">Если вы извлекаете файл для исключительного доступа, ни один другой пользователь не может извлечь этот файл, пока вы его не вернете.</span><span class="sxs-lookup"><span data-stu-id="deb1a-106">When you check out a file exclusively, no other user can check out the file until you check it in.</span></span> <span data-ttu-id="deb1a-107">Если вы извлекаете файл в режиме общего доступа, другие пользователи могут извлекать и изменять его, но может потребоваться слияние версии, извлеченной вами, с версиями, созданными другими пользователями.</span><span class="sxs-lookup"><span data-stu-id="deb1a-107">When you check out a file in shared mode, other users can check out and modify the file, and when you check it in, you may need to merge the version you have checked out with the versions created by other users.</span></span>  
  
 <span data-ttu-id="deb1a-108">Для извлечения проектов и файлов, контролируемых системой управления версиями, служит команда **Извлечь** .</span><span class="sxs-lookup"><span data-stu-id="deb1a-108">Use the **Check Out** command to check out source-controlled projects and files.</span></span> <span data-ttu-id="deb1a-109">Если вы используете эту команду для извлечения решения или проекта, все файлы в решении или проекте также будут извлечены. Однако извлечение отдельного файла исходного кода не приводит к извлечению проекта или решения, к которому он относится.</span><span class="sxs-lookup"><span data-stu-id="deb1a-109">If you use this command to check out a solution or project, all the files in the solution or project are also checked out. However, checking out an individual source code file does not result in the check out of the project or solution to which it belongs.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="deb1a-110">Если настройки базы данных [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe для данного проекта разрешают несколько одновременных извлечений, а файл нужно извлечь в монопольном режиме, то перед его извлечением необходимо снять флажок **Разрешить одновременные извлечения** в диалоговом окне **Дополнительные параметры извлечения** .</span><span class="sxs-lookup"><span data-stu-id="deb1a-110">If the [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe database for your project is configured to allow multiple checkouts, and you want to check out a file exclusively, you must clear the **Allow multiple checkouts** option in the **Advanced Check Out Options** dialog box before checking out the file.</span></span> <span data-ttu-id="deb1a-111">Чтобы изменение вступило в силу, необходимо перезапустить среду [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="deb1a-111">You must restart the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] for this setting to take effect.</span></span>  
  
### <a name="to-check-out-a-file"></a><span data-ttu-id="deb1a-112">Извлечение файла</span><span class="sxs-lookup"><span data-stu-id="deb1a-112">To check out a file</span></span>  
  
1.  <span data-ttu-id="deb1a-113">В обозревателе решений выберите проект или файл.</span><span class="sxs-lookup"><span data-stu-id="deb1a-113">In Solution Explorer, select the project or file.</span></span>  
  
2.  <span data-ttu-id="deb1a-114">В меню **Файл** укажите пункт **Управление версиями**, затем выберите **Извлечь для изменения**.</span><span class="sxs-lookup"><span data-stu-id="deb1a-114">On the **File** menu, point to **Source Control**, and then click **Check Out for Edit**.</span></span>  
  
3.  <span data-ttu-id="deb1a-115">Если отображается диалоговое окно **Извлечение для изменения** , выберите нужные элементы и нажмите кнопку **извлечь**. Если в [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] окружении не отображается диалоговое окно Извлечение, **Check Out** элементы, выбранные в Обозреватель решений и все дочерние объекты, которые они могут иметь, будут извлечены немедленно.</span><span class="sxs-lookup"><span data-stu-id="deb1a-115">If the **Check Out for Edit** dialog box is displayed, select the items you want, and click **Check Out**. If you have configured the [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environment not to display the **Check Out** dialog box, the items selected in Solution Explorer and any children they might have are checked out immediately.</span></span>  
  
     <span data-ttu-id="deb1a-116">**Извлечь**</span><span class="sxs-lookup"><span data-stu-id="deb1a-116">**Check Out**</span></span>  
     <span data-ttu-id="deb1a-117">Извлечение всех выбранных элементов.</span><span class="sxs-lookup"><span data-stu-id="deb1a-117">Check out all the selected items.</span></span>  
  
     <span data-ttu-id="deb1a-118">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="deb1a-118">**Columns**</span></span>  
     <span data-ttu-id="deb1a-119">Определите отображаемые столбцы и порядок, в котором они будут отображаться.</span><span class="sxs-lookup"><span data-stu-id="deb1a-119">Identify the columns to display and the order in which they are displayed.</span></span>  
  
     <span data-ttu-id="deb1a-120">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="deb1a-120">**Comments**</span></span>  
     <span data-ttu-id="deb1a-121">Задайте комментарий, связанный с операцией извлечения.</span><span class="sxs-lookup"><span data-stu-id="deb1a-121">Specify a comment to associate with the checkout operation.</span></span>  
  
     <span data-ttu-id="deb1a-122">**В ходе извлечения элементов не показывать диалоговое окно извлечения**</span><span class="sxs-lookup"><span data-stu-id="deb1a-122">**Don't Show Check Out dialog box when checking out items**</span></span>  
     <span data-ttu-id="deb1a-123">При выполнении операций извлечения подавить появление диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="deb1a-123">Suppress the dialog box during checkout operations.</span></span>  
  
     <span data-ttu-id="deb1a-124">**Плоское представление**</span><span class="sxs-lookup"><span data-stu-id="deb1a-124">**Flat View**</span></span>  
     <span data-ttu-id="deb1a-125">Отображать отмеченные файлы в виде плоских списков под их подключением к системе управления версиями.</span><span class="sxs-lookup"><span data-stu-id="deb1a-125">Display the items you are checking out as flat lists under their source control connection.</span></span>  
  
     <span data-ttu-id="deb1a-126">**Edit** (Изменение)</span><span class="sxs-lookup"><span data-stu-id="deb1a-126">**Edit**</span></span>  
     <span data-ttu-id="deb1a-127">Изменение элемента без его извлечения. Кнопка **изменить** появляется только в том случае, если [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] настроена поддержка редактирования возвращенных файлов.</span><span class="sxs-lookup"><span data-stu-id="deb1a-127">Modify an item without checking it out. The **Edit** button appears only if you have [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] configured to support the editing of checked-in files.</span></span>  
  
     <span data-ttu-id="deb1a-128">**имя**;</span><span class="sxs-lookup"><span data-stu-id="deb1a-128">**Name**</span></span>  
     <span data-ttu-id="deb1a-129">Отображает имена элементов, доступных для извлечения.</span><span class="sxs-lookup"><span data-stu-id="deb1a-129">Displays the names of the items available for checkout.</span></span> <span data-ttu-id="deb1a-130">Рядом с выбранными элементами отображаются флажки отметки.</span><span class="sxs-lookup"><span data-stu-id="deb1a-130">Items that are selected appear with check boxes next to them.</span></span> <span data-ttu-id="deb1a-131">Если какой-либо элемент не надо извлекать, снимите его флажок.</span><span class="sxs-lookup"><span data-stu-id="deb1a-131">If you do not want to check out a particular item, clear its check box.</span></span>  
  
     <span data-ttu-id="deb1a-132">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="deb1a-132">**Options**</span></span>  
     <span data-ttu-id="deb1a-133">При щелчке стрелки справа от кнопки отображаются зависящие от подключения параметры извлечения средств системы управления версиями.</span><span class="sxs-lookup"><span data-stu-id="deb1a-133">Displays source control plug-in-specific checkout options when the arrow to the right of the button is clicked.</span></span>  
  
     <span data-ttu-id="deb1a-134">**Sort**</span><span class="sxs-lookup"><span data-stu-id="deb1a-134">**Sort**</span></span>  
     <span data-ttu-id="deb1a-135">Сортировка порядка отображаемых столбцов.</span><span class="sxs-lookup"><span data-stu-id="deb1a-135">Sort the order of the displayed columns.</span></span>  
  
     <span data-ttu-id="deb1a-136">**Представление в виде дерева**</span><span class="sxs-lookup"><span data-stu-id="deb1a-136">**Tree View**</span></span>  
     <span data-ttu-id="deb1a-137">Отображение иерархии файлов и папок для извлекаемого элемента.</span><span class="sxs-lookup"><span data-stu-id="deb1a-137">Display the folder and file hierarchy for the item you are checking out.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="deb1a-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="deb1a-138">See Also</span></span>  
 <span data-ttu-id="deb1a-139">[Изменение возвращенных файлов](../../2014/database-engine/edit-checked-in-files.md) </span><span class="sxs-lookup"><span data-stu-id="deb1a-139">[Edit Checked-In Files](../../2014/database-engine/edit-checked-in-files.md) </span></span>  
 <span data-ttu-id="deb1a-140">[Автоматически извлекать файлы после изменения](../../2014/database-engine/automatically-check-out-files-upon-edit.md) </span><span class="sxs-lookup"><span data-stu-id="deb1a-140">[Automatically Check Out Files Upon Edit](../../2014/database-engine/automatically-check-out-files-upon-edit.md) </span></span>  
 <span data-ttu-id="deb1a-141">[Отменить извлечение](../../2014/database-engine/undo-checkouts.md) </span><span class="sxs-lookup"><span data-stu-id="deb1a-141">[Undo Checkouts](../../2014/database-engine/undo-checkouts.md) </span></span>  
 [<span data-ttu-id="deb1a-142">Управление извлечениями</span><span class="sxs-lookup"><span data-stu-id="deb1a-142">Manage Checkouts</span></span>](../../2014/database-engine/manage-checkouts.md)  
  
  
