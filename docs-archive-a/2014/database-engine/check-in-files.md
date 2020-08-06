---
title: Возврат файлов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- VisualStudio.SourceControl.CheckInDialog
helpviewer_keywords:
- checking in files
ms.assetid: 0657a387-8411-4406-bef9-d262a5bfa269
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 070c1dfa5dd057cf777980f7022752a97a4dc84c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665584"
---
# <a name="check-in-files"></a><span data-ttu-id="c46ed-102">Возврат файлов</span><span class="sxs-lookup"><span data-stu-id="c46ed-102">Check In Files</span></span>
  <span data-ttu-id="c46ed-103">Чтобы изменения в файлах стали доступны другим пользователям, файлы нужно вернуть системе управления версиями.</span><span class="sxs-lookup"><span data-stu-id="c46ed-103">To make source-controlled files that you have modified available to other users, you must check the files into source control.</span></span> <span data-ttu-id="c46ed-104">При возврате файла данная его версия сохраняется поставщиком управления версиями и становится последней версией файла.</span><span class="sxs-lookup"><span data-stu-id="c46ed-104">When you check in a file, the version you check in is written to the source control provider and becomes the latest version of the file.</span></span>  
  
 <span data-ttu-id="c46ed-105">Для возврата файлов можно применить команду **Вернуть** .</span><span class="sxs-lookup"><span data-stu-id="c46ed-105">You can use the **Check In** command to check in files.</span></span> <span data-ttu-id="c46ed-106">Если эта команда используется для проверки решения или проекта, проверяются все файлы проекта или решения.</span><span class="sxs-lookup"><span data-stu-id="c46ed-106">If you use this command to check in a solution or project, all the files in the solution or project are also checked in.</span></span> <span data-ttu-id="c46ed-107">Однако проверка отдельного файла с исходным кодом не приводит к проверке проекта или решения, к которому относится этот файл.</span><span class="sxs-lookup"><span data-stu-id="c46ed-107">However, checking in an individual source code file does not result in the check-in of the project or solution to which it belongs.</span></span>  
  
### <a name="to-check-in-a-file"></a><span data-ttu-id="c46ed-108">Возвращение файла</span><span class="sxs-lookup"><span data-stu-id="c46ed-108">To check in a file</span></span>  
  
1.  <span data-ttu-id="c46ed-109">В обозревателе решений щелкните правой кнопкой мыши нужный файл и выберите **Вернуть**.</span><span class="sxs-lookup"><span data-stu-id="c46ed-109">In Solution Explorer, right-click the file to check in, and then click **Check In**.</span></span>  
  
2.  <span data-ttu-id="c46ed-110">В открывшемся диалоговом окне **Возврат** выберите соответствующие параметры и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c46ed-110">If the **Check In** dialog box appears, select the appropriate options, and then click **OK**.</span></span>  
  
     <span data-ttu-id="c46ed-111">**Зарегистрируйся**</span><span class="sxs-lookup"><span data-stu-id="c46ed-111">**Check In**</span></span>  
     <span data-ttu-id="c46ed-112">Возврат всех выбранных элементов.</span><span class="sxs-lookup"><span data-stu-id="c46ed-112">Check in all the selected items.</span></span>  
  
     <span data-ttu-id="c46ed-113">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="c46ed-113">**Columns**</span></span>  
     <span data-ttu-id="c46ed-114">Определите отображаемые столбцы и порядок, в котором они будут отображаться.</span><span class="sxs-lookup"><span data-stu-id="c46ed-114">Identify the columns to display and the order in which they are displayed.</span></span>  
  
     <span data-ttu-id="c46ed-115">**Комментарии**</span><span class="sxs-lookup"><span data-stu-id="c46ed-115">**Comments**</span></span>  
     <span data-ttu-id="c46ed-116">Добавьте комментарий, связанный с операцией возврата.</span><span class="sxs-lookup"><span data-stu-id="c46ed-116">Add a comment to associate with the check-in operation.</span></span>  
  
     <span data-ttu-id="c46ed-117">**Во время возврата элементов не показывать диалоговое окно «Возврат»**</span><span class="sxs-lookup"><span data-stu-id="c46ed-117">**Don't show Check in dialog box when checking in items**</span></span>  
     <span data-ttu-id="c46ed-118">Подавлять во время выполнения операций возврата диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="c46ed-118">Suppress the dialog box during check-in operations.</span></span>  
  
     <span data-ttu-id="c46ed-119">**Плоское представление**</span><span class="sxs-lookup"><span data-stu-id="c46ed-119">**Flat View**</span></span>  
     <span data-ttu-id="c46ed-120">Отображать возвращаемые файлы в виде плоских списков под их соединением с системой управления версиями.</span><span class="sxs-lookup"><span data-stu-id="c46ed-120">Display the files you are checking in as flat lists under their source control connection.</span></span>  
  
     <span data-ttu-id="c46ed-121">**имя**;</span><span class="sxs-lookup"><span data-stu-id="c46ed-121">**Name**</span></span>  
     <span data-ttu-id="c46ed-122">Отображает имена возвращаемых элементов.</span><span class="sxs-lookup"><span data-stu-id="c46ed-122">Displays the names of the items to check in.</span></span> <span data-ttu-id="c46ed-123">Напротив элементов отображаются флажки, которые установлены.</span><span class="sxs-lookup"><span data-stu-id="c46ed-123">Items appear with the check boxes next to them selected.</span></span> <span data-ttu-id="c46ed-124">Если какой-либо элемент не нужно возвращать, снимите его флажок.</span><span class="sxs-lookup"><span data-stu-id="c46ed-124">If you do not want to check in a particular item, clear its check box.</span></span>  
  
     <span data-ttu-id="c46ed-125">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="c46ed-125">**Options**</span></span>  
     <span data-ttu-id="c46ed-126">При нажатии стрелки справа от кнопки отображает зависящие от подключения параметры возврата системы управления версиями.</span><span class="sxs-lookup"><span data-stu-id="c46ed-126">Displays source control plug-in-specific check-in options when the arrow to the right of the button is clicked.</span></span>  
  
     <span data-ttu-id="c46ed-127">**Sort**</span><span class="sxs-lookup"><span data-stu-id="c46ed-127">**Sort**</span></span>  
     <span data-ttu-id="c46ed-128">Отсортируйте порядок отображаемых столбцов.</span><span class="sxs-lookup"><span data-stu-id="c46ed-128">Sort the order of the display columns.</span></span>  
  
     <span data-ttu-id="c46ed-129">**Представление в виде дерева**</span><span class="sxs-lookup"><span data-stu-id="c46ed-129">**Tree View**</span></span>  
     <span data-ttu-id="c46ed-130">Отображение папки и иерархии файлов для возвращаемых элементов.</span><span class="sxs-lookup"><span data-stu-id="c46ed-130">Display the folder and file hierarchy for the items you are checking in.</span></span>  
  
 <span data-ttu-id="c46ed-131">Если этот файл не был извлечен сразу несколькими пользователями, то среда [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] сразу же выполняет его возврат.</span><span class="sxs-lookup"><span data-stu-id="c46ed-131">If the file you have checked in is not part of a shared checkout, the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] environment checks in the file immediately.</span></span> <span data-ttu-id="c46ed-132">В противном случае появится запрос на слияние данной версии с версиями, созданными другими пользователями.</span><span class="sxs-lookup"><span data-stu-id="c46ed-132">Otherwise, it may prompt you to merge your version with versions created by other users.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c46ed-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="c46ed-133">See Also</span></span>  
 <span data-ttu-id="c46ed-134">[Просмотр списка измененных файлов](../../2014/database-engine/view-a-list-of-modified-files.md) </span><span class="sxs-lookup"><span data-stu-id="c46ed-134">[View a List of Modified Files](../../2014/database-engine/view-a-list-of-modified-files.md) </span></span>  
 [<span data-ttu-id="c46ed-135">Управление возвратами</span><span class="sxs-lookup"><span data-stu-id="c46ed-135">Manage Checkins</span></span>](../../2014/database-engine/manage-checkins.md)  
  
  
