---
title: Файлы для управления решениями и проектами | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- projects [SQL Server Management Studio], files
- .ssmssln files
- .ssmsmobileproj files
- .ssmsasproj files
- .ssmssqlproj files
- .sqlsuo files
- files [SQL Server Management Studio], projects
ms.assetid: e19d2859-0b97-4727-ac27-c4c226d86b2f
author: stevestein
ms.author: sstein
ms.openlocfilehash: c94f1f853263c3969961de91ec95b921f5d78ead
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732249"
---
# <a name="files-that-manage-solutions-and-projects"></a><span data-ttu-id="cfb89-102">Файлы для управления решениями и проектами</span><span class="sxs-lookup"><span data-stu-id="cfb89-102">Files That Manage Solutions and Projects</span></span>
  <span data-ttu-id="cfb89-103">В этом разделе рассматриваются типы файлов, которые используются только в [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cfb89-103">This topic describes the file types that are specific to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="cfb89-104">По умолчанию все решения и их проекты создаются в папке \My Documents\SQL Server Management Studio Projects.</span><span class="sxs-lookup"><span data-stu-id="cfb89-104">By default, all solutions and their projects are created in \My Documents\SQL Server Management Studio Projects.</span></span>  
  
## <a name="management-studio-solution-files"></a><span data-ttu-id="cfb89-105">Файлы решений среды Management Studio</span><span class="sxs-lookup"><span data-stu-id="cfb89-105">Management Studio Solution Files</span></span>  
 <span data-ttu-id="cfb89-106">В [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] используются типы файлов, отличные от тех, что используются в [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] или [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="cfb89-106">[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] uses different file types than [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] or [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio.</span></span> <span data-ttu-id="cfb89-107">Это означает, что открыть решение среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] в [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] или Visual Studio нельзя.</span><span class="sxs-lookup"><span data-stu-id="cfb89-107">This means you cannot open a [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] solution in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] or in Visual Studio.</span></span> [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="cfb89-108">файлы решений позволяют обозревателю решений открывать графический интерфейс для управления файлами.</span><span class="sxs-lookup"><span data-stu-id="cfb89-108">solution files allow Solution Explorer to display a graphical interface for managing your files.</span></span>  
  
|<span data-ttu-id="cfb89-109">Расширение</span><span class="sxs-lookup"><span data-stu-id="cfb89-109">Extension</span></span>|<span data-ttu-id="cfb89-110">Тип файла</span><span class="sxs-lookup"><span data-stu-id="cfb89-110">File type</span></span>|<span data-ttu-id="cfb89-111">Description</span><span class="sxs-lookup"><span data-stu-id="cfb89-111">Description</span></span>|<span data-ttu-id="cfb89-112">Создан</span><span class="sxs-lookup"><span data-stu-id="cfb89-112">Created by</span></span>|  
|---------------|---------------|-----------------|----------------|  
|<span data-ttu-id="cfb89-113">.ssmssln</span><span class="sxs-lookup"><span data-stu-id="cfb89-113">.ssmssln</span></span>|[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="cfb89-114">Объект решения</span><span class="sxs-lookup"><span data-stu-id="cfb89-114">Solution Object</span></span>|<span data-ttu-id="cfb89-115">Предоставляет среду со ссылками на расположение проектов, элементов проекта и решения [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на диске</span><span class="sxs-lookup"><span data-stu-id="cfb89-115">Provides the environment with references to the location on disk of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] projects, project items, and solution</span></span>|[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]|  
  
## <a name="management-studio-project-files"></a><span data-ttu-id="cfb89-116">Файлы проектов среды Management Studio</span><span class="sxs-lookup"><span data-stu-id="cfb89-116">Management Studio Project Files</span></span>  
 <span data-ttu-id="cfb89-117">Точно так же, как решения содержат файлы решений, управляющие объектами в решении, проекты содержат файлы проектов.</span><span class="sxs-lookup"><span data-stu-id="cfb89-117">In the same way that solutions contain solution files that manage objects in a solution, projects contain project files.</span></span> <span data-ttu-id="cfb89-118">Тип файла проекта, который среда [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] создает для проекта, зависит от шаблона, который использовался для создания этого проекта.</span><span class="sxs-lookup"><span data-stu-id="cfb89-118">The type of project file that [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] creates for a project depends on the template used to create the project.</span></span> <span data-ttu-id="cfb89-119">В следующей таблице приводятся типы файлов, создаваемых для каждого проекта.</span><span class="sxs-lookup"><span data-stu-id="cfb89-119">The following table describes the type of file created for each project.</span></span>  
  
|<span data-ttu-id="cfb89-120">Расширение</span><span class="sxs-lookup"><span data-stu-id="cfb89-120">Extension</span></span>|<span data-ttu-id="cfb89-121">Шаблон проекта</span><span class="sxs-lookup"><span data-stu-id="cfb89-121">Project template</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="cfb89-122">.ssmssqlproj</span><span class="sxs-lookup"><span data-stu-id="cfb89-122">.ssmssqlproj</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="cfb89-123">Проект скриптов</span><span class="sxs-lookup"><span data-stu-id="cfb89-123">Scripts Project</span></span>|  
|<span data-ttu-id="cfb89-124">.ssmsasproj</span><span class="sxs-lookup"><span data-stu-id="cfb89-124">.ssmsasproj</span></span>|[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="cfb89-125">Проект скриптов</span><span class="sxs-lookup"><span data-stu-id="cfb89-125">Scripts Project</span></span>|  
  
## <a name="location-of-solution-level-files"></a><span data-ttu-id="cfb89-126">Расположение файлов уровня решения</span><span class="sxs-lookup"><span data-stu-id="cfb89-126">Location of Solution-Level Files</span></span>  
 <span data-ttu-id="cfb89-127">По умолчанию файлы уровня решения создаются в физическом каталоге первого проекта, созданного в этом решении.</span><span class="sxs-lookup"><span data-stu-id="cfb89-127">By default, solution-level files are created in the physical directory of the first project that is created with the solution.</span></span> <span data-ttu-id="cfb89-128">Каталог для решения можно определить, создав решение или указав каталог при создании нового проекта.</span><span class="sxs-lookup"><span data-stu-id="cfb89-128">You can specify a directory for the solution by creating a solution, or you can specify the directory when you create a new project.</span></span>  
  
 <span data-ttu-id="cfb89-129">Если структура каталогов схожа с логической структурой, отображаемой в обозревателе решений, облегчается поиск файлов проектов и решений, а также предоставление доступа к ним для других разработчиков в команде.</span><span class="sxs-lookup"><span data-stu-id="cfb89-129">If you have a directory structure similar to the logical structure shown in Solution Explorer, project and solution files are easier to locate and share with other developers on a team.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfb89-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="cfb89-130">See Also</span></span>  
 <span data-ttu-id="cfb89-131">[Управление файлами с помощью кодирования](manage-files-with-encoding.md) </span><span class="sxs-lookup"><span data-stu-id="cfb89-131">[Manage Files with Encoding](manage-files-with-encoding.md) </span></span>  
 <span data-ttu-id="cfb89-132">[Прочие файлы](miscellaneous-files.md) </span><span class="sxs-lookup"><span data-stu-id="cfb89-132">[Miscellaneous Files](miscellaneous-files.md) </span></span>  
 <span data-ttu-id="cfb89-133">[обозреватель решений](solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="cfb89-133">[Solution Explorer](solution-explorer.md) </span></span>  
 <span data-ttu-id="cfb89-134">[Решения &#40;SQL Server Management Studio&#41;](solutions-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="cfb89-134">[Solutions &#40;SQL Server Management Studio&#41;](solutions-sql-server-management-studio.md) </span></span>  
 <span data-ttu-id="cfb89-135">[Проекты &#40;SQL Server Management Studio&#41;](projects-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="cfb89-135">[Projects &#40;SQL Server Management Studio&#41;](projects-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="cfb89-136">Обозреватель решений системы управления версиями</span><span class="sxs-lookup"><span data-stu-id="cfb89-136">Solution Explorer Source Control</span></span>](../../database-engine/solution-explorer-source-control.md)  
  
  
