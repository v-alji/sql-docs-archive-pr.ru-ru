---
title: Решения (среда SQL Server Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- solutions [SQL Server Management Studio]
- SQL Server Management Studio [SQL Server], solutions
- projects [SQL Server Management Studio], about projects
- SQL Server Management Studio [SQL Server], projects
- scripts [SQL Server], SQL Server Management Studio
ms.assetid: d06a8a05-7201-4055-8cf3-21bcb4e82c25
author: stevestein
ms.author: sstein
ms.openlocfilehash: 836d3b3002d72541ad88ae55eac6d951530e0ca2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658020"
---
# <a name="solutions-sql-server-management-studio"></a><span data-ttu-id="cd7fa-102">Решения (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="cd7fa-102">Solutions (SQL Server Management Studio)</span></span>
  <span data-ttu-id="cd7fa-103">Решение [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] — это набор из одного или нескольких взаимосвязанных проектов.</span><span class="sxs-lookup"><span data-stu-id="cd7fa-103">A [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] solution is a collection of one or more related projects.</span></span> <span data-ttu-id="cd7fa-104">Проекты — это контейнеры, используемые разработчиками для организации взаимосвязанных файлов (например, для создания наборов широко используемых скриптов администрирования).</span><span class="sxs-lookup"><span data-stu-id="cd7fa-104">Projects are containers that developers use to organize related files, such as sets of commonly used administration scripts.</span></span>  
  
## <a name="solution-overview"></a><span data-ttu-id="cd7fa-105">Общие сведения о решении</span><span class="sxs-lookup"><span data-stu-id="cd7fa-105">Solution Overview</span></span>  
 <span data-ttu-id="cd7fa-106">[!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] может использоваться как платформа для разработки скриптов для компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] и служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cd7fa-106">You can use [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] as a script development platform for [!INCLUDE[ssDE](../../includes/ssde-md.md)] and [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="cd7fa-107">Используйте редакторы кода [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] для разработки скриптов и запросов для реляционных и многомерных баз данных, а также для создания наборов взаимосвязанных скриптов и запросов.</span><span class="sxs-lookup"><span data-stu-id="cd7fa-107">Use the [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] code editors to develop scripts and queries for relational and multidimensional databases, and collect related scripts and queries together in projects.</span></span>  
  
 <span data-ttu-id="cd7fa-108">Проекты могут включать:</span><span class="sxs-lookup"><span data-stu-id="cd7fa-108">Projects can contain:</span></span>  
  
-   <span data-ttu-id="cd7fa-109">Запросы и скрипты для реализации производственных процессов.</span><span class="sxs-lookup"><span data-stu-id="cd7fa-109">Queries and scripts that implement production processes.</span></span>  
  
-   <span data-ttu-id="cd7fa-110">Сведения о соединении и файлы, используемые запросами и скриптами.</span><span class="sxs-lookup"><span data-stu-id="cd7fa-110">Connection information and files used by the queries and scripts.</span></span>  
  
 <span data-ttu-id="cd7fa-111">Один или несколько взаимосвязанных проектов могут составлять решение.</span><span class="sxs-lookup"><span data-stu-id="cd7fa-111">One or more related projects can be combined in a solution.</span></span> <span data-ttu-id="cd7fa-112">Управлять решениями и проектами можно с помощью панели обозревателя решений в [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cd7fa-112">Solutions and projects can be managed by using the Solution Explorer pane in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
 <span data-ttu-id="cd7fa-113">Решения и проекты могут интегрироваться в базы данных Visual SourceSafe (VSS) [!INCLUDE[msCoName](../../includes/msconame-md.md)] или сторонних поставщиков систем управления версиями для отслеживания изменений при разработке и управления жизненным циклом.</span><span class="sxs-lookup"><span data-stu-id="cd7fa-113">Solutions and projects can be integrated into a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual SourceSafe (VSS) database or other third-party source control providers, for development change tracking and life-cycle management.</span></span>  
  
## <a name="solution-tasks"></a><span data-ttu-id="cd7fa-114">Задачи решения</span><span class="sxs-lookup"><span data-stu-id="cd7fa-114">Solution Tasks</span></span>  
  
|<span data-ttu-id="cd7fa-115">Описание задачи</span><span class="sxs-lookup"><span data-stu-id="cd7fa-115">Task Description</span></span>|<span data-ttu-id="cd7fa-116">Раздел</span><span class="sxs-lookup"><span data-stu-id="cd7fa-116">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="cd7fa-117">Описывает создание нового решения, которое будет служить контейнером для одного или нескольких проектов.</span><span class="sxs-lookup"><span data-stu-id="cd7fa-117">Describes how to create a new solution that can then be used to contain one or more projects.</span></span>|[<span data-ttu-id="cd7fa-118">Создание нового решения</span><span class="sxs-lookup"><span data-stu-id="cd7fa-118">Create a New Solution</span></span>](create-a-new-solution.md)|  
|<span data-ttu-id="cd7fa-119">Описывает добавления существующего решения в обозреватель решений.</span><span class="sxs-lookup"><span data-stu-id="cd7fa-119">Describes how to open an existing solution in Solution Explorer.</span></span>|[<span data-ttu-id="cd7fa-120">Открытие существующего решения</span><span class="sxs-lookup"><span data-stu-id="cd7fa-120">Open an Existing Solution</span></span>](open-an-existing-solution.md)|  
|<span data-ttu-id="cd7fa-121">Описывает закрытие решения.</span><span class="sxs-lookup"><span data-stu-id="cd7fa-121">Describes how to close a solution.</span></span>|[<span data-ttu-id="cd7fa-122">Закрытие решения</span><span class="sxs-lookup"><span data-stu-id="cd7fa-122">Close a Solution</span></span>](close-a-solution.md)|  
|<span data-ttu-id="cd7fa-123">Описывает удаление решения.</span><span class="sxs-lookup"><span data-stu-id="cd7fa-123">Describes how to delete a solution.</span></span>|[<span data-ttu-id="cd7fa-124">Удаление решения</span><span class="sxs-lookup"><span data-stu-id="cd7fa-124">Delete a Solution</span></span>](delete-a-solution.md)|  
|<span data-ttu-id="cd7fa-125">Описывает копирование элементов между проектами.</span><span class="sxs-lookup"><span data-stu-id="cd7fa-125">Describes how to copy items between projects.</span></span>|[<span data-ttu-id="cd7fa-126">Копирование элементов в решении</span><span class="sxs-lookup"><span data-stu-id="cd7fa-126">Copy Items in a Solution</span></span>](copy-items-in-a-solution.md)|  
|<span data-ttu-id="cd7fa-127">Описывает удаление элементов проекта или всего проекта.</span><span class="sxs-lookup"><span data-stu-id="cd7fa-127">Describes how to delete items in a project, or an entire project.</span></span>|[<span data-ttu-id="cd7fa-128">Перемещение или удаление элемента или проекта</span><span class="sxs-lookup"><span data-stu-id="cd7fa-128">Remove or Delete an Item or Project</span></span>](remove-or-delete-an-item-or-project.md)|  
|<span data-ttu-id="cd7fa-129">Описывает перемещение элементов между проектами в решении.</span><span class="sxs-lookup"><span data-stu-id="cd7fa-129">Describes how to move items between projects in a solution.</span></span>|[<span data-ttu-id="cd7fa-130">Перемещение элементов в решении</span><span class="sxs-lookup"><span data-stu-id="cd7fa-130">Move Items in a Solution</span></span>](move-items-in-a-solution.md)|  
|<span data-ttu-id="cd7fa-131">Описывает переименование решения или элементов в решении.</span><span class="sxs-lookup"><span data-stu-id="cd7fa-131">Describes how to rename a solution or the items in the solution.</span></span>|[<span data-ttu-id="cd7fa-132">Переименование элементов решений и проектов</span><span class="sxs-lookup"><span data-stu-id="cd7fa-132">Rename Solutions and Project Items</span></span>](rename-solutions-and-project-items.md)|  
  
## <a name="see-also"></a><span data-ttu-id="cd7fa-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="cd7fa-133">See Also</span></span>  
 <span data-ttu-id="cd7fa-134">[обозреватель решений](solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="cd7fa-134">[Solution Explorer](solution-explorer.md) </span></span>  
 <span data-ttu-id="cd7fa-135">[Проекты &#40;SQL Server Management Studio&#41;](projects-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="cd7fa-135">[Projects &#40;SQL Server Management Studio&#41;](projects-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="cd7fa-136">Обозреватель решений системы управления версиями</span><span class="sxs-lookup"><span data-stu-id="cd7fa-136">Solution Explorer Source Control</span></span>](../../database-engine/solution-explorer-source-control.md)  
  
  
