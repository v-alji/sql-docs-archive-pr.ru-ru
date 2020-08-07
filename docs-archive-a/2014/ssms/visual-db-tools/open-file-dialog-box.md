---
title: Диалоговое окно "Открытие файла" | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vs.openfile
ms.assetid: 3e01b9f5-2b0a-4fb3-9da8-984d27d17b8a
author: stevestein
ms.author: sstein
ms.openlocfilehash: e95797edf2c47b93cea4c730006aa8991374dcbe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727737"
---
# <a name="open-file-dialog-box"></a><span data-ttu-id="69752-102">Диалоговое окно «Открытие файла»</span><span class="sxs-lookup"><span data-stu-id="69752-102">Open File Dialog Box</span></span>
  <span data-ttu-id="69752-103">Используйте диалоговое окно **Открытие файла** для открытия существующего файла.</span><span class="sxs-lookup"><span data-stu-id="69752-103">Use the **Open File** dialog box to open an existing file from disk.</span></span> <span data-ttu-id="69752-104">Это диалоговое окно можно также использовать для повторного открытия уже открытого файла с другими параметрами языковой кодировки.</span><span class="sxs-lookup"><span data-stu-id="69752-104">You can also use this dialog box to open an already opened file using different language encoding options.</span></span>  
  
 <span data-ttu-id="69752-105">Для доступа к этому диалоговому окну выберите пункт **Открыть** в меню **Файл** , а затем выберите **Файл**.</span><span class="sxs-lookup"><span data-stu-id="69752-105">To access this dialog box, select **Open** from the **File** menu and then choose **File**.</span></span> <span data-ttu-id="69752-106">Это диалоговое окно отображается также при открытии файлов с помощью других элементов интерфейса, например диалогового окна **Внешние средства** .</span><span class="sxs-lookup"><span data-stu-id="69752-106">This dialog box also appears when you are opening files from other elements, such as the **External Tools** dialog box.</span></span> <span data-ttu-id="69752-107">В меню **Файл** выберите команду **Открыть**и пункт **Решение или проект** , чтобы открыть похожее диалоговое окно **Открытие проекта** .</span><span class="sxs-lookup"><span data-stu-id="69752-107">From the **File** menu, select **Open**, and then choose **Project/Solution** to open the similar **Open Project** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="69752-108">Прежде чем открыть проект или компонент в среде [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], определите, заслуживает ли его код доверия.</span><span class="sxs-lookup"><span data-stu-id="69752-108">Before opening a project or component in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], determine the trustworthiness of its code.</span></span> <span data-ttu-id="69752-109">Даже само действие по открытию проекта или компонента в среде [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] может привести к выполнению его кода в доверенном процессе на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="69752-109">The act of opening the project or component in a [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] may execute its code in a trusted process on your local machine.</span></span>  
  
## <a name="option"></a><span data-ttu-id="69752-110">Параметр</span><span class="sxs-lookup"><span data-stu-id="69752-110">Option</span></span>  
 <span data-ttu-id="69752-111">**Look in**</span><span class="sxs-lookup"><span data-stu-id="69752-111">**Look in**</span></span>  
 <span data-ttu-id="69752-112">Найти существующую папку проектов в выпадающем меню.</span><span class="sxs-lookup"><span data-stu-id="69752-112">Locate the existing project folder from this drop-down menu.</span></span> <span data-ttu-id="69752-113">Если выбрать папку в этом списке, в основной панели отображается содержимое папки.</span><span class="sxs-lookup"><span data-stu-id="69752-113">Selecting a folder from this list displays the contents of the folder in the primary pane.</span></span>  
  
## <a name="my-places-bar"></a><span data-ttu-id="69752-114">Моя панель позиций</span><span class="sxs-lookup"><span data-stu-id="69752-114">My Places Bar</span></span>  
 <span data-ttu-id="69752-115">**Рабочий стол**</span><span class="sxs-lookup"><span data-stu-id="69752-115">**Desktop**</span></span>  
 <span data-ttu-id="69752-116">Отображает файлы и папки, находящиеся на рабочем столе.</span><span class="sxs-lookup"><span data-stu-id="69752-116">Displays the files and folders located on the desktop.</span></span>  
  
 <span data-ttu-id="69752-117">**Мои проекты**</span><span class="sxs-lookup"><span data-stu-id="69752-117">**My Projects**</span></span>  
 <span data-ttu-id="69752-118">Отображает файлы и папки, находящиеся в папке **Проекты** текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="69752-118">Displays the files and folders in the users **Projects** folder.</span></span>  
  
 <span data-ttu-id="69752-119">**Мой компьютер**</span><span class="sxs-lookup"><span data-stu-id="69752-119">**My Computer**</span></span>  
 <span data-ttu-id="69752-120">Отображает содержимое гибкого, жесткого дисков и дисковода для компакт-дисков.</span><span class="sxs-lookup"><span data-stu-id="69752-120">Displays the contents of your floppy disk, hard disk, and CD-ROM drive.</span></span>  
  
## <a name="folder-list"></a><span data-ttu-id="69752-121">Список папок</span><span class="sxs-lookup"><span data-stu-id="69752-121">Folder List</span></span>  
 <span data-ttu-id="69752-122">**Имя файла**</span><span class="sxs-lookup"><span data-stu-id="69752-122">**File name**</span></span>  
 <span data-ttu-id="69752-123">Используйте этот параметр для фильтрации отображаемых файлов и папок.</span><span class="sxs-lookup"><span data-stu-id="69752-123">Use this option to filter the files and folders that are displayed.</span></span> <span data-ttu-id="69752-124">Введите полное или частичное имя файла, которое будет использоваться фильтром.</span><span class="sxs-lookup"><span data-stu-id="69752-124">Enter a full or partial file name on which to filter.</span></span> <span data-ttu-id="69752-125">В качестве символа-шаблона можно использовать символ звездочки (\*).</span><span class="sxs-lookup"><span data-stu-id="69752-125">You can use the asterisk (\*) as a wildcard.</span></span>  
  
 <span data-ttu-id="69752-126">**Тип файлов**</span><span class="sxs-lookup"><span data-stu-id="69752-126">**Files of type**</span></span>  
 <span data-ttu-id="69752-127">Используйте этот параметр для фильтрации содержимого папки или каталога, выбранного в списке «Папки», по определенному типу файлов.</span><span class="sxs-lookup"><span data-stu-id="69752-127">Use this option to filter the contents of the folder or directory selected in Look in for a particular file type.</span></span>  
  
 <span data-ttu-id="69752-128">**Параметры диалоговых окон «Открыть с помощью» и «Кодировка»**</span><span class="sxs-lookup"><span data-stu-id="69752-128">**Open With and Encoding Options**</span></span>  
 <span data-ttu-id="69752-129">Чтобы воспользоваться диалоговым окном **Открыть с помощью** для указания редактора целевого файла, щелкните маленький прямоугольник справа от кнопки **Открыть** и выберите команду **Открыть с помощью**.</span><span class="sxs-lookup"><span data-stu-id="69752-129">To use the **Open With Dialog Box** to specify an editor for the target file, select the small rectangle at the right of the **Open** button and choose **Open With**.</span></span> <span data-ttu-id="69752-130">В случае необходимости можно также указать схему языковой кодировки, применяемую при открытии выбранного файла.</span><span class="sxs-lookup"><span data-stu-id="69752-130">If necessary, you can also specify a language-encoding scheme to apply when opening the selected file.</span></span> <span data-ttu-id="69752-131">Для этого выберите одну из программ в списке, который содержит слова «**в кодировке**», и выберите команду **Открыть** , чтобы отобразить диалоговое окно **Кодировка**.</span><span class="sxs-lookup"><span data-stu-id="69752-131">To do so, select a program in the list that contains "**with Encoding**" and choose **Open** to display the **Encoding Dialog Box**.</span></span> <span data-ttu-id="69752-132">Эта кнопка доступна не всегда.</span><span class="sxs-lookup"><span data-stu-id="69752-132">This button is not always available.</span></span>  
  
## <a name="toolbar"></a><span data-ttu-id="69752-133">Панель инструментов</span><span class="sxs-lookup"><span data-stu-id="69752-133">Toolbar</span></span>  
 <span data-ttu-id="69752-134">**Назад**</span><span class="sxs-lookup"><span data-stu-id="69752-134">**Navigate Back**</span></span>  
 <span data-ttu-id="69752-135">Позволяет вернуться к последней просмотренной папке, дисководу или расположению в Интернете.</span><span class="sxs-lookup"><span data-stu-id="69752-135">Returns the most recently viewed folder, drive, or internet location.</span></span>  
  
 <span data-ttu-id="69752-136">**На один уровень вверх**</span><span class="sxs-lookup"><span data-stu-id="69752-136">**Up One Level**</span></span>  
 <span data-ttu-id="69752-137">Позволяет перейти в дереве к папке, находящейся на ближайшем вышестоящем уровне в древовидном представлении.</span><span class="sxs-lookup"><span data-stu-id="69752-137">Navigates the tree to the next highest folder in the tree view.</span></span>  
  
 <span data-ttu-id="69752-138">**Выполнить поиск на веб-узлах**</span><span class="sxs-lookup"><span data-stu-id="69752-138">**Search the Web**</span></span>  
 <span data-ttu-id="69752-139">Эта кнопка недоступна.</span><span class="sxs-lookup"><span data-stu-id="69752-139">This button is not available.</span></span>  
  
 <span data-ttu-id="69752-140">**Удаление**</span><span class="sxs-lookup"><span data-stu-id="69752-140">**Delete**</span></span>  
 <span data-ttu-id="69752-141">Удаляет выбранные файлы и папки из хранилища.</span><span class="sxs-lookup"><span data-stu-id="69752-141">Deletes the selected files or folders from storage.</span></span>  
  
 <span data-ttu-id="69752-142">**Создать папку**</span><span class="sxs-lookup"><span data-stu-id="69752-142">**New Folder**</span></span>  
 <span data-ttu-id="69752-143">Отображает диалоговое окно **Создать папку** .</span><span class="sxs-lookup"><span data-stu-id="69752-143">Displays the **New Folder** dialog box.</span></span> <span data-ttu-id="69752-144">Используйте этот параметр, чтобы создать новую вложенную папку в папке, выбранной в раскрывающемся списке **Папка** .</span><span class="sxs-lookup"><span data-stu-id="69752-144">Use this option to create a new child folder under the folder selected in the **Look in** drop-down list box.</span></span>  
  
## <a name="views"></a><span data-ttu-id="69752-145">Представления</span><span class="sxs-lookup"><span data-stu-id="69752-145">Views</span></span>  
 <span data-ttu-id="69752-146">Содержит варианты упорядочивания и просмотра содержимого элемента в раскрывающемся списке **Представления** .</span><span class="sxs-lookup"><span data-stu-id="69752-146">Provides options for arranging and viewing the contents of the item selected in the **Views** drop-down list box.</span></span>  
  
 <span data-ttu-id="69752-147">**Эскизы страниц**</span><span class="sxs-lookup"><span data-stu-id="69752-147">**Thumbnails**</span></span>  
 <span data-ttu-id="69752-148">Отображает уменьшенные представления элементов, находящихся на панели отображения.</span><span class="sxs-lookup"><span data-stu-id="69752-148">Displays thumbnails for items in the display pane.</span></span>  
  
 <span data-ttu-id="69752-149">**Плитка**</span><span class="sxs-lookup"><span data-stu-id="69752-149">**Tiles**</span></span>  
 <span data-ttu-id="69752-150">Отображает файлы и папки в виде крупных значков.</span><span class="sxs-lookup"><span data-stu-id="69752-150">Displays files and folders as large icons.</span></span>  
  
 <span data-ttu-id="69752-151">**Значки**</span><span class="sxs-lookup"><span data-stu-id="69752-151">**Icons**</span></span>  
 <span data-ttu-id="69752-152">Отображает файлы и папки в виде мелких значков.</span><span class="sxs-lookup"><span data-stu-id="69752-152">Displays files and folders as small icons.</span></span>  
  
 <span data-ttu-id="69752-153">**Список**</span><span class="sxs-lookup"><span data-stu-id="69752-153">**List**</span></span>  
 <span data-ttu-id="69752-154">Отображает файлы и папки в формате списка.</span><span class="sxs-lookup"><span data-stu-id="69752-154">Displays files and folders in a list format.</span></span>  
  
 <span data-ttu-id="69752-155">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="69752-155">**Details**</span></span>  
 <span data-ttu-id="69752-156">Отображает для файлов и папок имя, размер, тип и дату последнего изменения в формате списка.</span><span class="sxs-lookup"><span data-stu-id="69752-156">Displays the name, size, type, and last-modified date of files and folders in a list format.</span></span> <span data-ttu-id="69752-157">Чтобы отсортировать список по конкретной характеристике, щелкните заголовок относящегося к ней столбца.</span><span class="sxs-lookup"><span data-stu-id="69752-157">To sort by a particular detail, click its column header.</span></span>  
  
 <span data-ttu-id="69752-158">**Веб-представление**</span><span class="sxs-lookup"><span data-stu-id="69752-158">**WebView**</span></span>  
 <span data-ttu-id="69752-159">Эта команда недоступна.</span><span class="sxs-lookup"><span data-stu-id="69752-159">This command is not available.</span></span>  
  
## <a name="tools"></a><span data-ttu-id="69752-160">Инструменты</span><span class="sxs-lookup"><span data-stu-id="69752-160">Tools</span></span>  
 <span data-ttu-id="69752-161">Выберите действие, применяемое к элементу, выделенному на панели «Содержимое».</span><span class="sxs-lookup"><span data-stu-id="69752-161">Select a tool to apply to the item selected in the contents pane.</span></span>  
  
 <span data-ttu-id="69752-162">**Удаление**</span><span class="sxs-lookup"><span data-stu-id="69752-162">**Delete**</span></span>  
 <span data-ttu-id="69752-163">Удаляет выбранные файлы или папки из хранилища.</span><span class="sxs-lookup"><span data-stu-id="69752-163">Deletes the selected file or folder from storage.</span></span>  
  
 <span data-ttu-id="69752-164">**Подключить сетевой диск**</span><span class="sxs-lookup"><span data-stu-id="69752-164">**Map Network Drive**</span></span>  
 <span data-ttu-id="69752-165">Открывает диалоговое окно **Подключить сетевой диск** .</span><span class="sxs-lookup"><span data-stu-id="69752-165">Opens the **Map Network Drive** dialog box.</span></span>  
