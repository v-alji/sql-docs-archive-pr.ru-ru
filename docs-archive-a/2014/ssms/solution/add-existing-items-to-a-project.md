---
title: Добавление существующих элементов в проект | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- projects [SQL Server Management Studio], item additions
- adding project items
ms.assetid: 084b3879-e96b-45a7-b421-6a4b0db2b92b
author: stevestein
ms.author: sstein
ms.openlocfilehash: cffa683bfa2a2c81c059d887231531f03d5c892b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668548"
---
# <a name="add-existing-items-to-a-project"></a><span data-ttu-id="6ba92-102">Добавление существующих элементов в проект</span><span class="sxs-lookup"><span data-stu-id="6ba92-102">Add Existing Items to a Project</span></span>
  <span data-ttu-id="6ba92-103">Для расширения возможностей приложения в проект можно добавлять новые элементы.</span><span class="sxs-lookup"><span data-stu-id="6ba92-103">Add new items to a project to extend application functionality.</span></span> <span data-ttu-id="6ba92-104">Существующий элемент может быть запросом или произвольным файлом.</span><span class="sxs-lookup"><span data-stu-id="6ba92-104">An existing item can be a query or a miscellaneous file.</span></span> [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="6ba92-105">имеет два типа проектов: проект скрипта [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и проект скрипта служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="6ba92-105">has two project types: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Script Project, and Analysis Services Script Project.</span></span> <span data-ttu-id="6ba92-106">Тип проекта определяет типы файлов запросов, которые могут быть добавлены в проект.</span><span class="sxs-lookup"><span data-stu-id="6ba92-106">The project type determines the query files that you can add to the project.</span></span> <span data-ttu-id="6ba92-107">Например, запрос [!INCLUDE[tsql](../../includes/tsql-md.md)] (SQL-файл) можно добавить в проект скрипта [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , но нельзя добавить в проект скрипта служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="6ba92-107">For example, you can add a [!INCLUDE[tsql](../../includes/tsql-md.md)] query (a file with a .sql extension) to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Script project, but you cannot add it to an Analysis Services Script Project.</span></span> <span data-ttu-id="6ba92-108">Сведения о связывании дополнительных расширений файлов с типом проекта см. в разделе [связывание расширений файлов с редактором кода](../../relational-databases/scripting/associate-file-extensions-to-a-code-editor.md).</span><span class="sxs-lookup"><span data-stu-id="6ba92-108">To associate additional file extensions to a project type, see [Associate File Extensions to a Code Editor](../../relational-databases/scripting/associate-file-extensions-to-a-code-editor.md).</span></span>  
  
### <a name="to-add-an-existing-query-or-a-miscellaneous-file-to-a-project"></a><span data-ttu-id="6ba92-109">Добавление существующего запроса или произвольного файла в проект</span><span class="sxs-lookup"><span data-stu-id="6ba92-109">To add an existing query or a miscellaneous file to a project</span></span>  
  
1.  <span data-ttu-id="6ba92-110">Выберите целевой проект в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="6ba92-110">In Solution Explorer, select a target project.</span></span>  
  
2.  <span data-ttu-id="6ba92-111">В меню **Проект** выберите пункт **Добавить существующий элемент**.</span><span class="sxs-lookup"><span data-stu-id="6ba92-111">On the **Project** menu, click **Add Existing Item**.</span></span>  
  
     <span data-ttu-id="6ba92-112">**Look in**</span><span class="sxs-lookup"><span data-stu-id="6ba92-112">**Look in**</span></span>  
     <span data-ttu-id="6ba92-113">Определите расположение файлов или папок, которые будут добавлены в проект из этого списка.</span><span class="sxs-lookup"><span data-stu-id="6ba92-113">Locate the files or folders to add to your project from this list.</span></span> <span data-ttu-id="6ba92-114">Для веб-служб XML и веб-приложений ASP.NET файлы размещаются на веб-сервере.</span><span class="sxs-lookup"><span data-stu-id="6ba92-114">For XML Web services and ASP.NET Web applications, the files are located on the Web server.</span></span>  
  
     <span data-ttu-id="6ba92-115">**Рабочий стол**</span><span class="sxs-lookup"><span data-stu-id="6ba92-115">**Desktop**</span></span>  
     <span data-ttu-id="6ba92-116">Отображает файлы и папки, находящиеся на рабочем столе.</span><span class="sxs-lookup"><span data-stu-id="6ba92-116">Displays the files and folders located on the desktop.</span></span>  
  
     <span data-ttu-id="6ba92-117">**Мои проекты**</span><span class="sxs-lookup"><span data-stu-id="6ba92-117">**My Projects**</span></span>  
     <span data-ttu-id="6ba92-118">Отображает файлы и папки, размещенные в каталоге по умолчанию **Мои проекты** .</span><span class="sxs-lookup"><span data-stu-id="6ba92-118">Displays the files and folders at the default **My Projects** location.</span></span>  
  
     <span data-ttu-id="6ba92-119">**Мой компьютер**</span><span class="sxs-lookup"><span data-stu-id="6ba92-119">**My Computer**</span></span>  
     <span data-ttu-id="6ba92-120">Отображает содержимое папки **Мой компьютер** .</span><span class="sxs-lookup"><span data-stu-id="6ba92-120">Displays the contents of your **My Computer** folder.</span></span>  
  
     <span data-ttu-id="6ba92-121">**Имя файла**</span><span class="sxs-lookup"><span data-stu-id="6ba92-121">**File name**</span></span>  
     <span data-ttu-id="6ba92-122">Используйте этот параметр для фильтрации отображаемых файлов и папок.</span><span class="sxs-lookup"><span data-stu-id="6ba92-122">Use this option to filter the files and folders that are displayed.</span></span> <span data-ttu-id="6ba92-123">Введите полное или частичное имя файла для фильтра. Используйте знак звездочки (`*`) в шаблоне имени.</span><span class="sxs-lookup"><span data-stu-id="6ba92-123">Enter the full or partial file name on which to filter; use an asterisk (`*`) as a wildcard.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6ba92-124">Просмотрите сетевые и веб-узлы, вводя сетевой путь или URL-адрес в поле **Имя файла** .</span><span class="sxs-lookup"><span data-stu-id="6ba92-124">Navigate to Web and network locations by entering the URL or network path in the **File name** box.</span></span> <span data-ttu-id="6ba92-125">Например, при вводе **http://mywebsite** отобразятся файлы, доступные на веб-сайте mywebsite, а при вводе **\\\myserver\myshare** — файлы, расположенные в папке myshare на сервере myserver.</span><span class="sxs-lookup"><span data-stu-id="6ba92-125">For example, **http://mywebsite** displays the files available at the mywebsite Web location, and **\\\myserver\myshare** displays the files available at the myshare location on myserver.</span></span>  
  
     <span data-ttu-id="6ba92-126">**Тип файлов**</span><span class="sxs-lookup"><span data-stu-id="6ba92-126">**Files of type**</span></span>  
     <span data-ttu-id="6ba92-127">Используйте этот параметра для фильтрации файлов по расширению.</span><span class="sxs-lookup"><span data-stu-id="6ba92-127">Use this option to filter files based on file extension.</span></span> <span data-ttu-id="6ba92-128">Предлагается список из наиболее употребляемых типов файлов.</span><span class="sxs-lookup"><span data-stu-id="6ba92-128">Each product lists default filters of the most common file types.</span></span>  
  
     <span data-ttu-id="6ba92-129">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="6ba92-129">**Add**</span></span>  
     <span data-ttu-id="6ba92-130">Используйте эту кнопку, чтобы добавить элемент в проект и открыть его в редакторе по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6ba92-130">Use this drop-down button to add the item to the project and open the item in its default editor.</span></span>  
  
    -   <span data-ttu-id="6ba92-131">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="6ba92-131">**Add**</span></span>  
  
         <span data-ttu-id="6ba92-132">Происходит копирование существующего элемента в каталог проекта на диске и добавление элемента в выбранный проект в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="6ba92-132">Copies the existing item to your project folder on disk and adds the item under the selected project in Solution Explorer.</span></span> <span data-ttu-id="6ba92-133">Все изменения, выполняемые над элементом, не отражаются на элементе в исходном расположении.</span><span class="sxs-lookup"><span data-stu-id="6ba92-133">Any changes made to the item are not reflected in the item at the original location.</span></span> <span data-ttu-id="6ba92-134">Это редактор, используемый по умолчанию для заданного типа файлов.</span><span class="sxs-lookup"><span data-stu-id="6ba92-134">This is the default editor for the file type.</span></span>  
  
    -   <span data-ttu-id="6ba92-135">**Добавить как ссылку**</span><span class="sxs-lookup"><span data-stu-id="6ba92-135">**Add As Link**</span></span>  
  
         <span data-ttu-id="6ba92-136">Добавляет выбранный файл в проект и открывает его в редакторе, используемом по умолчанию для заданного типа файлов.</span><span class="sxs-lookup"><span data-stu-id="6ba92-136">Adds the selected file to the project and opens it with the default editor for the file type.</span></span> <span data-ttu-id="6ba92-137">Этот параметр открывает первоначально выбранный файл и не копирует файл в папку проекта.</span><span class="sxs-lookup"><span data-stu-id="6ba92-137">This option opens the originally selected file and does not copy the file to the project folder.</span></span>  
  
3.  <span data-ttu-id="6ba92-138">При добавлении файла запроса в диалоговом окне соединения будет предложено указать соединение для данного запроса.</span><span class="sxs-lookup"><span data-stu-id="6ba92-138">If you are adding query files, the connection dialog will prompt you to specify a connection for the query.</span></span> <span data-ttu-id="6ba92-139">Нажмите кнопку **Отмена** , если не нужно связывать запрос с соединением.</span><span class="sxs-lookup"><span data-stu-id="6ba92-139">You can click **Cancel** on the connection dialog if you do not want to associate a connection to the query.</span></span>  
  
4.  <span data-ttu-id="6ba92-140">Файл будет добавлен в папку **Запросы** или **Прочие файлы** проекта.</span><span class="sxs-lookup"><span data-stu-id="6ba92-140">The file will be added to the **Queries** or **Miscellaneous Files** folder of the project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ba92-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="6ba92-141">See Also</span></span>  
 <span data-ttu-id="6ba92-142">[обозреватель решений](solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="6ba92-142">[Solution Explorer](solution-explorer.md) </span></span>  
 <span data-ttu-id="6ba92-143">[Добавление новых элементов в проект](add-new-items-to-a-project.md) </span><span class="sxs-lookup"><span data-stu-id="6ba92-143">[Add New Items to a Project](add-new-items-to-a-project.md) </span></span>  
 [<span data-ttu-id="6ba92-144">Перемещение или удаление элемента или проекта</span><span class="sxs-lookup"><span data-stu-id="6ba92-144">Remove or Delete an Item or Project</span></span>](remove-or-delete-an-item-or-project.md)  
  
  
