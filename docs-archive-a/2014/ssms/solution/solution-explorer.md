---
title: Обозреватель решений | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], solutions
- projects [SQL Server Management Studio], about projects
- SQL Server Management Studio [SQL Server], projects
- solutions [SQL Server Management Studio], about solutions
- SQL Server Management Studio [SQL Server], items
- items [SQL Server]
ms.assetid: 0df09843-0d4f-4925-bc6c-99265035a0c1
author: stevestein
ms.author: sstein
ms.openlocfilehash: fa312f5e097fa1c59b9ba545709dc964a184c3f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658022"
---
# <a name="solution-explorer"></a><span data-ttu-id="2fd4f-102">Обозреватель решений</span><span class="sxs-lookup"><span data-stu-id="2fd4f-102">Solution Explorer</span></span>
  <span data-ttu-id="2fd4f-103">Панель обозревателя решений в среде [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] содержит контейнеры (проекты) для управления такими элементами, как скрипты базы данных, запросы, подключения к данным и файлы.</span><span class="sxs-lookup"><span data-stu-id="2fd4f-103">The Solution Explorer pane in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] provides containers called projects for managing items such as database scripts, queries, data connections, and files.</span></span> <span data-ttu-id="2fd4f-104">Один или несколько связанных между собой проектов могут быть объединены в контейнер, который называется решением.</span><span class="sxs-lookup"><span data-stu-id="2fd4f-104">One or more projects that are related to each other can be combined in a container called a solution.</span></span>  
  
 <span data-ttu-id="2fd4f-105">Решение содержит один или несколько проектов, а также файлы и метаданные, которые позволяют определить решение как единое целое.</span><span class="sxs-lookup"><span data-stu-id="2fd4f-105">A solution includes one or more projects, plus files and metadata that help define the solution as a whole.</span></span> <span data-ttu-id="2fd4f-106">Проект — это набор файлов и относящихся к ним метаданных, например сведений о соединении.</span><span class="sxs-lookup"><span data-stu-id="2fd4f-106">A project is a set of files, plus related metadata such as connection information.</span></span> <span data-ttu-id="2fd4f-107">Решения и проекты содержат элементы, которые представляют собой скрипты, запросы, сведения о соединениях и файлы, необходимые для создания решения базы данных.</span><span class="sxs-lookup"><span data-stu-id="2fd4f-107">Solutions and projects contain items that represent the scripts, queries, connection information and files that you need to create your database solution.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]  
  
## <a name="benefits-of-using-solutions"></a><span data-ttu-id="2fd4f-108">Преимущества использования решений</span><span class="sxs-lookup"><span data-stu-id="2fd4f-108">Benefits of Using Solutions</span></span>  
 <span data-ttu-id="2fd4f-109">Эти контейнеры позволяют:</span><span class="sxs-lookup"><span data-stu-id="2fd4f-109">Use these containers to:</span></span>  
  
-   <span data-ttu-id="2fd4f-110">реализовать систему управление версиями для запросов и скриптов;</span><span class="sxs-lookup"><span data-stu-id="2fd4f-110">Implement source control on queries and scripts.</span></span>  
  
-   <span data-ttu-id="2fd4f-111">управлять параметрами как решения в целом, так и конкретных проектов;</span><span class="sxs-lookup"><span data-stu-id="2fd4f-111">Manage settings for your solution as a whole or for individual projects.</span></span>  
  
-   <span data-ttu-id="2fd4f-112">облегчить работу с файлами и позволить сосредоточиться на работе с элементами, которые составляют решение базы данных;</span><span class="sxs-lookup"><span data-stu-id="2fd4f-112">Handle the details of file management while you focus on items that make up your database solution.</span></span>  
  
-   <span data-ttu-id="2fd4f-113">добавлять элементы одновременно к нескольким проектам решения либо ко всему решению, не указывая элемент в каждом из проектов;</span><span class="sxs-lookup"><span data-stu-id="2fd4f-113">Add items that are useful to multiple projects in the solution or to the solution without referencing the item in each project.</span></span>  
  
-   <span data-ttu-id="2fd4f-114">работать с различными файлами, формат которых не зависит от решений и проектов.</span><span class="sxs-lookup"><span data-stu-id="2fd4f-114">Work on miscellaneous files that are independent from solutions or projects.</span></span>  
  
 <span data-ttu-id="2fd4f-115">Элементы, содержащиеся в проектах, зависят от типа проекта и от того, используется ли среда [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2fd4f-115">The items contained in projects depend on the project type and whether you are using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="2fd4f-116">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="2fd4f-116">Related Tasks</span></span>  
 <span data-ttu-id="2fd4f-117">Используйте следующие разделы для начала работы с решениями SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2fd4f-117">Use the following topics to get started with SQL Server Solutions:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2fd4f-118">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2fd4f-118">**Description**</span></span>|<span data-ttu-id="2fd4f-119">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="2fd4f-119">**Topic**</span></span>|  
|<span data-ttu-id="2fd4f-120">Описывает, как добавить один или несколько проектов в решение.</span><span class="sxs-lookup"><span data-stu-id="2fd4f-120">Describes how to collect one or more projects in a solution.</span></span>|[<span data-ttu-id="2fd4f-121">Решения (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="2fd4f-121">Solutions &#40;SQL Server Management Studio&#41;</span></span>](solutions-sql-server-management-studio.md)|  
|<span data-ttu-id="2fd4f-122">Описывает, как создать проект и добавить элементы, например скрипты и соединения.</span><span class="sxs-lookup"><span data-stu-id="2fd4f-122">Describes how to create a project and add items like scripts and connections.</span></span>|[<span data-ttu-id="2fd4f-123">Проекты (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="2fd4f-123">Projects &#40;SQL Server Management Studio&#41;</span></span>](projects-sql-server-management-studio.md)|  
|<span data-ttu-id="2fd4f-124">Описывает, как интегрировать решения или отдельные проекты в систему управления исходными кодами.</span><span class="sxs-lookup"><span data-stu-id="2fd4f-124">Describes how to integrate solutions or individual projects into a source code control system.</span></span>|[<span data-ttu-id="2fd4f-125">Обозреватель решений для системы управления версиями</span><span class="sxs-lookup"><span data-stu-id="2fd4f-125">Solution Explorer Source Control</span></span>](../../database-engine/solution-explorer-source-control.md)|  
|<span data-ttu-id="2fd4f-126">Сведения о файлах, используемых средой [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] для управления решениями и файлами.</span><span class="sxs-lookup"><span data-stu-id="2fd4f-126">Provides information about the files used by [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to manage solutions and files.</span></span>|[<span data-ttu-id="2fd4f-127">Файлы для управления решениями и проектами</span><span class="sxs-lookup"><span data-stu-id="2fd4f-127">Files That Manage Solutions and Projects</span></span>](files-that-manage-solutions-and-projects.md)|  
  
  
