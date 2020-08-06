---
title: Команда "Сохранить как" | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vs.saveas
helpviewer_keywords:
- Save As dialog box
ms.assetid: 61347757-f5a3-481d-8b05-1fed086629b6
author: stevestein
ms.author: sstein
ms.openlocfilehash: e47d9c37371283fc6fba2754896d77b51d26cef0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669218"
---
# <a name="save-as"></a><span data-ttu-id="a1c26-102">Сохранить как</span><span class="sxs-lookup"><span data-stu-id="a1c26-102">Save As</span></span>
  <span data-ttu-id="a1c26-103">Используйте это диалоговое окно, чтобы сохранить экземпляр текущего элемента в указанном расположении и в файле указанного формата.</span><span class="sxs-lookup"><span data-stu-id="a1c26-103">Use this dialog box to save an instance of the current item at a specified location in a specified file format.</span></span> <span data-ttu-id="a1c26-104">Чтобы открыть это диалоговое окно, нажмите кнопку **сохранить** *\<file>* **как** в меню **файл** (где *\<file>* — имя текущего элемента) или нажмите клавиши ALT + F, а затем в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="a1c26-104">To display this dialog box, click **Save** *\<file>* **As** on the **File** menu (where *\<file>* is the name of the current item), or press ALT+F, A in the Code Editor.</span></span>  
  
## <a name="central-panel"></a><span data-ttu-id="a1c26-105">Центральная панель</span><span class="sxs-lookup"><span data-stu-id="a1c26-105">Central Panel</span></span>  
 <span data-ttu-id="a1c26-106">**Сохранить в**</span><span class="sxs-lookup"><span data-stu-id="a1c26-106">**Save in**</span></span>  
 <span data-ttu-id="a1c26-107">Найти существующую папку проектов в выпадающем меню.</span><span class="sxs-lookup"><span data-stu-id="a1c26-107">Locate the existing project folder from this drop-down menu.</span></span> <span data-ttu-id="a1c26-108">При выборе папки из этого списка в основной панели ниже в основной части экрана будет отображаться ее содержимое.</span><span class="sxs-lookup"><span data-stu-id="a1c26-108">Selecting a folder from this list displays the contents of the folder in the primary pane below.</span></span>  
  
 <span data-ttu-id="a1c26-109">**Имя файла**</span><span class="sxs-lookup"><span data-stu-id="a1c26-109">**File name**</span></span>  
 <span data-ttu-id="a1c26-110">Используйте этот параметр для просмотра, изменения имени файла, либо фильтрации отображаемых файлов и папок.</span><span class="sxs-lookup"><span data-stu-id="a1c26-110">Use this option to view the current file name, change the file name, or filter the files and folders that are displayed.</span></span> <span data-ttu-id="a1c26-111">Для фильтрации отображаемых файлов и папок введите полное или частичное имя файла для фильтрации.</span><span class="sxs-lookup"><span data-stu-id="a1c26-111">To filter the files and folders that are displayed, enter a full or partial file name on which to filter.</span></span> <span data-ttu-id="a1c26-112">В качестве символа-шаблона можно использовать символ звездочки (`*`).</span><span class="sxs-lookup"><span data-stu-id="a1c26-112">You can use the asterisk (`*`) as a wildcard.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="a1c26-113">Чтобы отобразились файлы, расположенные в Интернете или в сети, введите URL-адрес или сетевой путь в поле **Имя файла** .</span><span class="sxs-lookup"><span data-stu-id="a1c26-113">To display files on Web and network locations, enter a URL or network path in the **File name** box.</span></span> <span data-ttu-id="a1c26-114">Например, при вводе "<http://mywebsite>" отобразятся файлы, доступные на веб-сайте "mywebsite", а при вводе "\\\myserver\myshare" — файлы, расположенные в папке "myshare" на сервере "myserver".</span><span class="sxs-lookup"><span data-stu-id="a1c26-114">For example, "<http://mywebsite>" displays the files available at the "mywebsite" Web location and "\\\myserver\myshare" displays the files available at the "myshare" location on "myserver".</span></span>  
  
 <span data-ttu-id="a1c26-115">**Сохранить в файле типа**</span><span class="sxs-lookup"><span data-stu-id="a1c26-115">**Save as type**</span></span>  
 <span data-ttu-id="a1c26-116">Используйте этот параметр для сохранения выбранного элемента в файле другого типа.</span><span class="sxs-lookup"><span data-stu-id="a1c26-116">Use this option to select a new file type for the selected item.</span></span> <span data-ttu-id="a1c26-117">Отображаются все типы файлов, в которые можно преобразовать выбранный элемент.</span><span class="sxs-lookup"><span data-stu-id="a1c26-117">The file types displayed include all available file types to which the selected item can be converted.</span></span>  
  
 <span data-ttu-id="a1c26-118">**Дополнительные параметры сохранения**</span><span class="sxs-lookup"><span data-stu-id="a1c26-118">**Advanced Save Options**</span></span>  
 <span data-ttu-id="a1c26-119">Чтобы открыть **диалоговое окно "Дополнительные параметры сохранения"** , щелкните маленький прямоугольник справа от кнопки **Сохранить** и нажмите **Выбор кодировки для сохранения**.</span><span class="sxs-lookup"><span data-stu-id="a1c26-119">To access the **Advanced Save Options Dialog Box**, select the small rectangle at the right of the **Save** button and then click **Save with Encoding**.</span></span> <span data-ttu-id="a1c26-120">В этом диалоговом окне задайте кодировку для файла, а также символы, применяемые в качестве разделителей строк.</span><span class="sxs-lookup"><span data-stu-id="a1c26-120">Use this dialog box to specify an encoding for the file and the characters to use at Line endings.</span></span>  
  
## <a name="left-panel"></a><span data-ttu-id="a1c26-121">Левая панель</span><span class="sxs-lookup"><span data-stu-id="a1c26-121">Left Panel</span></span>  
 <span data-ttu-id="a1c26-122">**Рабочий стол**</span><span class="sxs-lookup"><span data-stu-id="a1c26-122">**Desktop**</span></span>  
 <span data-ttu-id="a1c26-123">Отображает все файлы и папки, расположенные на рабочем столе.</span><span class="sxs-lookup"><span data-stu-id="a1c26-123">Displays any files and folders located on the desktop.</span></span>  
  
 <span data-ttu-id="a1c26-124">**Мои проекты**</span><span class="sxs-lookup"><span data-stu-id="a1c26-124">**My Projects**</span></span>  
 <span data-ttu-id="a1c26-125">Показывает файлы и папки в каталоге **Мои проекты** либо последнее открытое расположение.</span><span class="sxs-lookup"><span data-stu-id="a1c26-125">Displays files and folders at the **My Projects** or the most recently visited location.</span></span>  
  
 <span data-ttu-id="a1c26-126">**Мой компьютер**</span><span class="sxs-lookup"><span data-stu-id="a1c26-126">**My Computer**</span></span>  
 <span data-ttu-id="a1c26-127">Показывает папку **Мой компьютер** на компьютере.</span><span class="sxs-lookup"><span data-stu-id="a1c26-127">Displays the **My Computer** location on your computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1c26-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="a1c26-128">See Also</span></span>  
 <span data-ttu-id="a1c26-129">[Дополнительные параметры сохранения](advanced-save-options.md) </span><span class="sxs-lookup"><span data-stu-id="a1c26-129">[Advanced Save Options](advanced-save-options.md) </span></span>  
 [<span data-ttu-id="a1c26-130">Управление файлами с помощью кодировок</span><span class="sxs-lookup"><span data-stu-id="a1c26-130">Manage Files with Encoding</span></span>](../solution/manage-files-with-encoding.md)  
  
  
