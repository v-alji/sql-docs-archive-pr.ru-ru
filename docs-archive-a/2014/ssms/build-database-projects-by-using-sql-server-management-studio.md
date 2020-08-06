---
title: Создание проектов баз данных с использованием среды SQL Server Management Studio | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- scripts [SQL Server], database projects
- database projects [SQL Server]
- projects [SQL Server Management Studio], about projects
- projects [SQL Server Management Studio]
ms.assetid: c2e80045-894d-44cf-b65c-e547ed738947
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3ddf3f61e69623716b2987c5c4d849398e822d18
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654046"
---
# <a name="build-database-projects-by-using-sql-server-management-studio"></a><span data-ttu-id="77393-102">Создание проектов баз данных с использованием среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="77393-102">Build Database Projects by Using SQL Server Management Studio</span></span>
  <span data-ttu-id="77393-103">Проект скрипта базы данных — это организованный набор скриптов, сведений о соединении и шаблонов, связанных с базой данных или одной из частей базы данных.</span><span class="sxs-lookup"><span data-stu-id="77393-103">A database script project is an organized set of scripts, connection information, and templates that are all associated with a database or one part of a database.</span></span> [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="77393-104">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] предоставляет [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] для администрирования и проектирования баз данных [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] в контексте проекта скрипта.</span><span class="sxs-lookup"><span data-stu-id="77393-104">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provides the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] for administering and designing [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] databases within the context of a script project.</span></span> [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="77393-105">включает конструкторы, редакторы, руководства и мастера, помогающие пользователям в разработке, развертывании и обслуживании баз данных.</span><span class="sxs-lookup"><span data-stu-id="77393-105">includes designers, editors, guides and wizards to assist users in developing, deploying and maintaining databases.</span></span>  
  
## <a name="sql-server-management-studio"></a><span data-ttu-id="77393-106">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="77393-106">SQL Server Management Studio</span></span>  
 [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="77393-107">— это набор административных средств для управления компонентами, относящимися к [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="77393-107">is a suite of administrative tools for managing the components belonging to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="77393-108">Эта интегрированная среда позволяет пользователям выполнять разнообразные задачи, например резервное копирование данных, редактирование запросов и автоматизацию общих функций в одном интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="77393-108">This integrated environment allows users to perform a variety of tasks, such as backing up data, editing queries, and automating common functions within a single interface.</span></span>  
  
 [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="77393-109">включает в себя следующие средства:</span><span class="sxs-lookup"><span data-stu-id="77393-109">includes the following tools:</span></span>  
  
-   <span data-ttu-id="77393-110">Редактор кода — богатый возможностями редактор скриптов для написания и редактирования скриптов.</span><span class="sxs-lookup"><span data-stu-id="77393-110">Code Editor is a rich script editor for writing and editing scripts.</span></span> [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="77393-111">предоставляет четыре версии редактора кода: редактор запросов [!INCLUDE[ssDE](../includes/ssde-md.md)] для скриптов [!INCLUDE[tsql](../includes/tsql-md.md)] , редактор запросов многомерных выражений, редактор запросов расширения интеллектуального анализа данных и редактор запросов XML/A.</span><span class="sxs-lookup"><span data-stu-id="77393-111">provides four versions of the Code Editor; the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor for [!INCLUDE[tsql](../includes/tsql-md.md)] scripts, the DMX Query Editor, the MDX Query Editor, and the XML/A Query Editor.</span></span>  
  
-   <span data-ttu-id="77393-112">Обозреватель объектов для размещения, изменения, создания скрипта или выполнения объектов, принадлежащих экземплярам [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="77393-112">Object Explorer for locating, modifying, scripting or running objects belonging to instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="77393-113">Обозреватель шаблонов для размещения и написания сценариев шаблонов.</span><span class="sxs-lookup"><span data-stu-id="77393-113">Template Explorer for locating and scripting templates.</span></span>  
  
-   <span data-ttu-id="77393-114">Обозреватель решений для организации и хранения связанных скриптов как части проекта.</span><span class="sxs-lookup"><span data-stu-id="77393-114">Solution Explorer for organizing and storing related scripts as parts of a project.</span></span>  
  
-   <span data-ttu-id="77393-115">Окно свойств для отображения текущих свойств выбранных объектов.</span><span class="sxs-lookup"><span data-stu-id="77393-115">Properties Window for displaying the current properties of selected objects.</span></span>  
  
 [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="77393-116">обеспечивает эффективность рабочих процессов, предоставляя:</span><span class="sxs-lookup"><span data-stu-id="77393-116">supports efficient work processes by providing:</span></span>  
  
-   <span data-ttu-id="77393-117">Отключенный доступ.</span><span class="sxs-lookup"><span data-stu-id="77393-117">Disconnected access.</span></span> <span data-ttu-id="77393-118">Можно писать и изменять скрипты, не соединяясь с экземпляром [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="77393-118">You can write and edit scripts without connecting to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="77393-119">Создание сценариев из любого диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="77393-119">Scripting from any dialog box.</span></span> <span data-ttu-id="77393-120">Можно создать скрипт из любого диалогового окна, а также читать, изменять, сохранять и многократно использовать скрипты после создания.</span><span class="sxs-lookup"><span data-stu-id="77393-120">You can create a script from any dialog box so that you can read, modify, store and reuse the scripts after you create them.</span></span>  
  
-   <span data-ttu-id="77393-121">Немодальные диалоговые окна.</span><span class="sxs-lookup"><span data-stu-id="77393-121">Nonmodal dialog boxes.</span></span> <span data-ttu-id="77393-122">При обращении к диалоговому окну интерфейса можно просмотреть другие ресурсы в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] , не закрывая диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="77393-122">When you access a UI dialog box you can browse other resources in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] without closing the dialog box.</span></span>  
  
## <a name="solutions-and-script-projects"></a><span data-ttu-id="77393-123">Решения и проекты скриптов</span><span class="sxs-lookup"><span data-stu-id="77393-123">Solutions and Script Projects</span></span>  
 <span data-ttu-id="77393-124">Обозреватель решений — это программа для хранения и повторного открытия решений для базы данных.</span><span class="sxs-lookup"><span data-stu-id="77393-124">Solution Explorer is a utility to store and reopen database solutions.</span></span> <span data-ttu-id="77393-125">Решения организовывают связанные проекты скрипта и файлы.</span><span class="sxs-lookup"><span data-stu-id="77393-125">Solutions organize related script projects and files.</span></span> <span data-ttu-id="77393-126">Проекты скрипта хранят файлы скрипта [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , шаблоны SQL, сведения о соединении и другие разные файлы.</span><span class="sxs-lookup"><span data-stu-id="77393-126">Script projects store [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] script files, SQL templates, connection information and other miscellaneous files.</span></span> <span data-ttu-id="77393-127">После сохранения скрипта в проекте скриптов у пользователей появляются следующие возможности.</span><span class="sxs-lookup"><span data-stu-id="77393-127">When a script is saved in a script project, users are able to:</span></span>  
  
-   <span data-ttu-id="77393-128">Сопровождать управление версиями в скриптах.</span><span class="sxs-lookup"><span data-stu-id="77393-128">Maintain version control on scripts.</span></span>  
  
-   <span data-ttu-id="77393-129">Хранить параметры результатов со скриптом.</span><span class="sxs-lookup"><span data-stu-id="77393-129">Store results options with a script.</span></span>  
  
-   <span data-ttu-id="77393-130">Организовывать связанные скрипты в один проект скриптов.</span><span class="sxs-lookup"><span data-stu-id="77393-130">Organize related scripts in a single script project.</span></span>  
  
-   <span data-ttu-id="77393-131">Сохранять сведения о соединении со скриптами.</span><span class="sxs-lookup"><span data-stu-id="77393-131">Save connection information with scripts.</span></span>  
  
 <span data-ttu-id="77393-132">Обозреватель решений — инструмент для разработчиков, создающих и многократно использующих скрипты, связанные с одним и тем же проектом.</span><span class="sxs-lookup"><span data-stu-id="77393-132">Solution Explorer is a tool for developers who are creating and reusing scripts that are related to the same project.</span></span> <span data-ttu-id="77393-133">Если подобная задача потребуется позже, можно использовать группу скриптов, которые были сохранены в проекте.</span><span class="sxs-lookup"><span data-stu-id="77393-133">If a similar task is required later, you can use group of scripts that were stored in a project.</span></span> <span data-ttu-id="77393-134">Те, кто уже имеет опыт разработки приложений с помощью [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], сориентируются в обозревателе решений довольно легко.</span><span class="sxs-lookup"><span data-stu-id="77393-134">If you have created applications by using [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], you will find Solution Explorer very familiar.</span></span>  
  
 <span data-ttu-id="77393-135">Решение состоит из одного или более проектов скриптов.</span><span class="sxs-lookup"><span data-stu-id="77393-135">A solution consists of one or more script projects.</span></span> <span data-ttu-id="77393-136">Проект состоит из одного или более скриптов или соединений.</span><span class="sxs-lookup"><span data-stu-id="77393-136">A project consists of one or more scripts or connections.</span></span> <span data-ttu-id="77393-137">Проект может содержать не только файлы сценариев.</span><span class="sxs-lookup"><span data-stu-id="77393-137">A project may also include nonscript files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77393-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="77393-138">See Also</span></span>  
 <span data-ttu-id="77393-139">[Использование SQL Server Management Studio](../database-engine/use-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="77393-139">[Use SQL Server Management Studio](../database-engine/use-sql-server-management-studio.md) </span></span>  
 <span data-ttu-id="77393-140">[Редакторы запросов и текста &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/query-and-text-editors-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="77393-140">[Query and Text Editors &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/query-and-text-editors-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="77393-141">Решения (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="77393-141">Solutions &#40;SQL Server Management Studio&#41;</span></span>](solution/solutions-sql-server-management-studio.md)  
  
  
