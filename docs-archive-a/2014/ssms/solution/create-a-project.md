---
title: Создание проекта | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- projects [SQL Server Management Studio], creating
ms.assetid: 7897be19-365b-4b06-bcf0-8a669f67a673
author: stevestein
ms.author: sstein
ms.openlocfilehash: 269feee7225ceb09b1c2ed86419b19ec4001c1f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665740"
---
# <a name="create-a-project"></a><span data-ttu-id="067f2-102">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="067f2-102">Create a Project</span></span>
  <span data-ttu-id="067f2-103">В существующем решении можно создать один или несколько проектов.</span><span class="sxs-lookup"><span data-stu-id="067f2-103">You can create one or more projects within an existing solution.</span></span>  
  
### <a name="to-create-a-new-project-and-add-it-to-a-solution"></a><span data-ttu-id="067f2-104">Создание нового проекта и добавление его к решению</span><span class="sxs-lookup"><span data-stu-id="067f2-104">To create a new project and add it to a solution</span></span>  
  
1.  <span data-ttu-id="067f2-105">Выберите решение в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="067f2-105">In Solution Explorer, select the solution.</span></span>  
  
2.  <span data-ttu-id="067f2-106">В меню **Файл** выберите пункт **Добавить**, затем щелкните **Создание проекта**.</span><span class="sxs-lookup"><span data-stu-id="067f2-106">On the **File** menu, point to **Add**, and click **New Project**.</span></span>  
  
3.  <span data-ttu-id="067f2-107">В диалоговом окне  **Создание проекта** выберите тип проекта.</span><span class="sxs-lookup"><span data-stu-id="067f2-107">In the  **New Project** dialog box, click a type of project.</span></span>  
  
     <span data-ttu-id="067f2-108">**Шаблоны**</span><span class="sxs-lookup"><span data-stu-id="067f2-108">**Templates**</span></span>  
     <span data-ttu-id="067f2-109">В поле **Шаблоны** выберите шаблон.</span><span class="sxs-lookup"><span data-stu-id="067f2-109">In the **Templates** box, select a template.</span></span> <span data-ttu-id="067f2-110">Краткое описание выбранного шаблона проекта появляется под полем **Шаблоны** .</span><span class="sxs-lookup"><span data-stu-id="067f2-110">A brief description of the selected project template appears beneath the **Templates** box.</span></span>  
  
     <span data-ttu-id="067f2-111">**Название**</span><span class="sxs-lookup"><span data-stu-id="067f2-111">**Name**</span></span>  
     <span data-ttu-id="067f2-112">Введите имя создаваемого проекта скрипта.</span><span class="sxs-lookup"><span data-stu-id="067f2-112">Enter the name of the script project you want to create.</span></span> <span data-ttu-id="067f2-113">Папка с именем проекта создается в месте, указанном в поле **Расположение** .</span><span class="sxs-lookup"><span data-stu-id="067f2-113">A folder with the same name as the project is also created in the location displayed in the **Location** field.</span></span> <span data-ttu-id="067f2-114">Для некоторых проектов в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] создаются исходные и прочие вспомогательные файлы, которые добавляются в папку нового проекта.</span><span class="sxs-lookup"><span data-stu-id="067f2-114">For some projects, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] creates source and other supporting files and adds them to the new project folder.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="067f2-115">Для некоторых типов проектов текстовое поле **Имя** недоступно, поскольку при указании расположения задается имя проекта.</span><span class="sxs-lookup"><span data-stu-id="067f2-115">For some project types, the **Name** text box is unavailable because specifying the location sets the name.</span></span> <span data-ttu-id="067f2-116">Например, веб-приложения и веб-службы расположены на веб-сервере и получают свое имя от виртуального каталога, указанного на этом сервере.</span><span class="sxs-lookup"><span data-stu-id="067f2-116">For example, Web applications and Web services are located on a Web server and derive their name from the virtual directory specified on that server.</span></span>  
  
     <span data-ttu-id="067f2-117">Имена не могут содержать следующие символы:</span><span class="sxs-lookup"><span data-stu-id="067f2-117">Names cannot contain the following characters:</span></span>  
  
    -   <span data-ttu-id="067f2-118">Решетка (#)</span><span class="sxs-lookup"><span data-stu-id="067f2-118">Pound (#)</span></span>  
  
    -   <span data-ttu-id="067f2-119">Процент (%)</span><span class="sxs-lookup"><span data-stu-id="067f2-119">Percent (%)</span></span>  
  
    -   <span data-ttu-id="067f2-120">Амперсанд (&)</span><span class="sxs-lookup"><span data-stu-id="067f2-120">Ampersand (&)</span></span>  
  
    -   <span data-ttu-id="067f2-121">Звездочка (\*)</span><span class="sxs-lookup"><span data-stu-id="067f2-121">Asterisk (\*)</span></span>  
  
    -   <span data-ttu-id="067f2-122">Вертикальная черта (|)</span><span class="sxs-lookup"><span data-stu-id="067f2-122">Vertical bar (|)</span></span>  
  
    -   <span data-ttu-id="067f2-123">Обратная косая черта (\\)</span><span class="sxs-lookup"><span data-stu-id="067f2-123">Backslash (\\)</span></span>  
  
    -   <span data-ttu-id="067f2-124">Двоеточие (:)</span><span class="sxs-lookup"><span data-stu-id="067f2-124">Colon (:)</span></span>  
  
    -   <span data-ttu-id="067f2-125">Кавычки («»)</span><span class="sxs-lookup"><span data-stu-id="067f2-125">Quotation mark (")</span></span>  
  
    -   <span data-ttu-id="067f2-126">Знак "меньше" (\<)</span><span class="sxs-lookup"><span data-stu-id="067f2-126">Less than (\<)</span></span>  
  
    -   <span data-ttu-id="067f2-127">Знак «больше» >)</span><span class="sxs-lookup"><span data-stu-id="067f2-127">Greater than (>)</span></span>  
  
    -   <span data-ttu-id="067f2-128">Вопросительный знак (?)</span><span class="sxs-lookup"><span data-stu-id="067f2-128">Question mark (?)</span></span>  
  
    -   <span data-ttu-id="067f2-129">Косая черта (/)</span><span class="sxs-lookup"><span data-stu-id="067f2-129">Forward slash (/)</span></span>  
  
    -   <span data-ttu-id="067f2-130">Начальные и конечные пробелы (' ')</span><span class="sxs-lookup"><span data-stu-id="067f2-130">Leading or trailing spaces (' ')</span></span>  
  
    -   <span data-ttu-id="067f2-131">Имена, зарезервированные для Microsoft Windows или MS-DOS, такие как ("nul", "aux", "con", "com1", "lpt1" и так далее)</span><span class="sxs-lookup"><span data-stu-id="067f2-131">Names reserved for Microsoft Windows or MS-DOS, such as ("nul", "aux", "con", "com1", "lpt1", and so on)</span></span>  
  
     <span data-ttu-id="067f2-132">**Местоположение**</span><span class="sxs-lookup"><span data-stu-id="067f2-132">**Location**</span></span>  
     <span data-ttu-id="067f2-133">Укажите расположение, где нужно создать проект, либо выберите его из списка.</span><span class="sxs-lookup"><span data-stu-id="067f2-133">Enter the location where you want to create your project, or choose one from the list.</span></span>  
  
     <span data-ttu-id="067f2-134">**Обзор**</span><span class="sxs-lookup"><span data-stu-id="067f2-134">**Browse**</span></span>  
     <span data-ttu-id="067f2-135">Отображает диалоговое окно **Расположение проекта** , позволяющее визуально выбрать каталог, в котором нужно сохранить проект.</span><span class="sxs-lookup"><span data-stu-id="067f2-135">Displays the **Project Location** dialog box, allowing you to navigate to a new directory in which to save the project.</span></span>  
  
     <span data-ttu-id="067f2-136">**Решение**</span><span class="sxs-lookup"><span data-stu-id="067f2-136">**Solution**</span></span>  
     <span data-ttu-id="067f2-137">Выберите **Создать новое решение** для создания решения в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="067f2-137">Select **Create new Solution** to create a solution in Solution Explorer.</span></span> <span data-ttu-id="067f2-138">Выберите **Добавить к решению** для добавления нового проекта к решению, отрытому в данный момент в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="067f2-138">Select **Add to Solution** to add the new project to the solution currently open in Solution Explorer.</span></span>  
  
     <span data-ttu-id="067f2-139">**Создать каталог для решения**</span><span class="sxs-lookup"><span data-stu-id="067f2-139">**Create directory for Solution**</span></span>  
     <span data-ttu-id="067f2-140">Выберите для доступа к текстовому полю **Имя (решения)** .</span><span class="sxs-lookup"><span data-stu-id="067f2-140">Select to enable the **(Solution) Name** text box.</span></span> <span data-ttu-id="067f2-141">Этот параметр приведет к созданию нового каталога с именем, выбранным для проекта или решения.</span><span class="sxs-lookup"><span data-stu-id="067f2-141">This option creates a new directory of the name you choose for your project and solution.</span></span>  
  
     <span data-ttu-id="067f2-142">**Имя решения**</span><span class="sxs-lookup"><span data-stu-id="067f2-142">**Solution Name**</span></span>  
     <span data-ttu-id="067f2-143">Введите имя нового решения, в котором нужно создать проект.</span><span class="sxs-lookup"><span data-stu-id="067f2-143">Enter the name of the new solution in which you want your project to be created.</span></span> <span data-ttu-id="067f2-144">По умолчанию это поле использует имя, введенное в поле **Имя** .</span><span class="sxs-lookup"><span data-stu-id="067f2-144">By default, this field uses the same name as entered in the **Name** field.</span></span>  
  
     <span data-ttu-id="067f2-145">**Примечание** . Для доступа к этому параметру нужно установить флажки **Создать новое решение** в области **Решение** и **Создать каталог для решения** .</span><span class="sxs-lookup"><span data-stu-id="067f2-145">**Note** To access this option, you must select both the **Create New Solution** in the **Solution** and the **Create directory for Solution** check boxes.</span></span> <span data-ttu-id="067f2-146">Некоторые шаблоны проекта не поддерживают этот параметр, например веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="067f2-146">Some project templates do not support this option, such as Web applications.</span></span>  
  
     <span data-ttu-id="067f2-147">**Добавить к системе управления версиями**</span><span class="sxs-lookup"><span data-stu-id="067f2-147">**Add to Source Control**</span></span>  
     <span data-ttu-id="067f2-148">Если данный флажок установлен, приложение системы управления версиями откроется при нажатии кнопки **ОК**.</span><span class="sxs-lookup"><span data-stu-id="067f2-148">When this check box is selected, your source control application opens when you click **OK**.</span></span> <span data-ttu-id="067f2-149">Для продолжения задайте все сведения, необходимые приложению системы управления версиями.</span><span class="sxs-lookup"><span data-stu-id="067f2-149">Complete any information required by your source control application to continue.</span></span> <span data-ttu-id="067f2-150">Для использования этого параметра необходимо установить клиентское приложение системы управления версиями.</span><span class="sxs-lookup"><span data-stu-id="067f2-150">You must have a source control client application installed to use this option.</span></span>  
  
4.  <span data-ttu-id="067f2-151">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="067f2-151">Click **OK**.</span></span>  
  
 <span data-ttu-id="067f2-152">Проекту скрипта можно назначить имя, но имена папок задаются средой [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] и не могут быть изменены.</span><span class="sxs-lookup"><span data-stu-id="067f2-152">You can set a name for the script project, but the folder names are established by [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and cannot be changed.</span></span> <span data-ttu-id="067f2-153">Можно определить букву диска и путь для общего набора папок, используя диалоговое окно **Добавить новый проект** .</span><span class="sxs-lookup"><span data-stu-id="067f2-153">You can configure the drive and path specification for the common set of folders by using the **Add New Project** dialog box.</span></span> <span data-ttu-id="067f2-154">Щелкните правой кнопкой мыши значок решения в **обозревателе решений**, а затем щелкните **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="067f2-154">Right-click the solution icon in **Solution Explorer**, and then click **Add**.</span></span> <span data-ttu-id="067f2-155">По умолчанию папка проекта скриптов размещена по пути: "C:\Documents and Settings\\*имя_пользователя*\My Documents\SQL Server Management Studio\Projects\\\".</span><span class="sxs-lookup"><span data-stu-id="067f2-155">The default location for script project folders is: C:\Documents and Settings\\*username*\My Documents\SQL Server Management Studio\Projects\\.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="067f2-156">См. также:</span><span class="sxs-lookup"><span data-stu-id="067f2-156">See Also</span></span>  
 <span data-ttu-id="067f2-157">[обозреватель решений](solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="067f2-157">[Solution Explorer](solution-explorer.md) </span></span>  
 <span data-ttu-id="067f2-158">[Добавление существующего проекта в решение](add-an-existing-project-to-a-solution.md) </span><span class="sxs-lookup"><span data-stu-id="067f2-158">[Add an Existing Project to a Solution](add-an-existing-project-to-a-solution.md) </span></span>  
 <span data-ttu-id="067f2-159">[Добавление новых элементов в проект](add-new-items-to-a-project.md) </span><span class="sxs-lookup"><span data-stu-id="067f2-159">[Add New Items to a Project](add-new-items-to-a-project.md) </span></span>  
 <span data-ttu-id="067f2-160">[Добавление существующих элементов в проект](add-existing-items-to-a-project.md) </span><span class="sxs-lookup"><span data-stu-id="067f2-160">[Add Existing Items to a Project](add-existing-items-to-a-project.md) </span></span>  
 <span data-ttu-id="067f2-161">[Изменение расположения проектов по умолчанию](change-the-default-location-for-projects.md) </span><span class="sxs-lookup"><span data-stu-id="067f2-161">[Change the Default Location for Projects](change-the-default-location-for-projects.md) </span></span>  
 <span data-ttu-id="067f2-162">[Удаление или удаление элемента или проекта](remove-or-delete-an-item-or-project.md) </span><span class="sxs-lookup"><span data-stu-id="067f2-162">[Remove or Delete an Item or Project](remove-or-delete-an-item-or-project.md) </span></span>  
 [<span data-ttu-id="067f2-163">Удаление решения</span><span class="sxs-lookup"><span data-stu-id="067f2-163">Delete a Solution</span></span>](delete-a-solution.md)  
  
  
