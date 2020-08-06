---
title: обозреватель решений система управления версиями | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Visual SourceSafe
- SQL Server Management Studio [SQL Server], source control services
- source-controlled files [SQL Server]
- source controls [SQL Server Management Studio], services
- version control services [SQL Server]
- file source control services [SQL Server]
- VSS [Visual SourceSafe]
ms.assetid: 6373adb8-3d81-4945-a9fc-1d0d5799d29a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 46471ba8149c26f80e78006bc3a8befc2e81b416
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666204"
---
# <a name="solution-explorer-source-control"></a><span data-ttu-id="5444c-102">Обозреватель решений системы управления версиями</span><span class="sxs-lookup"><span data-stu-id="5444c-102">Solution Explorer Source Control</span></span>
  [!INCLUDE[msCoName](../includes/msconame-md.md)]<span data-ttu-id="5444c-103">[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]Обозреватель решений можно интегрировать в отдельную систему управления версиями.</span><span class="sxs-lookup"><span data-stu-id="5444c-103">[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] Solution Explorer can be integrated into a separate source control system.</span></span> <span data-ttu-id="5444c-104">После того как решение или проект будет интегрированы в систему управления версиями, появится возможность управлять доступом к файлам и версиями скриптов и запросов в проекте.</span><span class="sxs-lookup"><span data-stu-id="5444c-104">Once a solution or project is integrated into a source control system, you can control file access and versioning for the scripts and queries in your projects.</span></span>  
  
## <a name="solution-and-project-source-control"></a><span data-ttu-id="5444c-105">Система управления версиями решений и проектов</span><span class="sxs-lookup"><span data-stu-id="5444c-105">Solution and Project Source Control</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../includes/ssnotedepfutureavoid-md.md)]  
  
 <span data-ttu-id="5444c-106">Система управления версиями осуществляется в системе, в которой центральная часть программного обеспечения сервера реализует хранение и отслеживание версий файлов, а также управляет доступом к файлам.</span><span class="sxs-lookup"><span data-stu-id="5444c-106">Source control refers to a system in which a central piece of server software stores and tracks file versions, and also controls access to files.</span></span> <span data-ttu-id="5444c-107">Обычная система управления версиями включает поставщика управления версиями и несколько клиентов управления версиями.</span><span class="sxs-lookup"><span data-stu-id="5444c-107">A typical source control system includes a source control provider and two or more source control clients.</span></span> [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="5444c-108">может быть интегрирована в систему управления версиями.</span><span class="sxs-lookup"><span data-stu-id="5444c-108">can be integrated with a source control service.</span></span> <span data-ttu-id="5444c-109">Это означает возможность использования данного инструмента в качестве клиента для существующего поставщика системы управления версиями.</span><span class="sxs-lookup"><span data-stu-id="5444c-109">This means you can use the tool as a client for your source control provider.</span></span> <span data-ttu-id="5444c-110">Не покидая среду, можно легко управлять индивидуальными проектами и работать над проектом в команде.</span><span class="sxs-lookup"><span data-stu-id="5444c-110">Without leaving the environment, you can manage your individual and team projects easily.</span></span> <span data-ttu-id="5444c-111">Система управления версиями не включена в среду [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5444c-111">The source control provider is not included with [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span>  
  
#### <a name="to-select-a-source-control-provider"></a><span data-ttu-id="5444c-112">Выбор системы управления версиями</span><span class="sxs-lookup"><span data-stu-id="5444c-112">To select a source control provider</span></span>  
  
1.  <span data-ttu-id="5444c-113">Установите клиентскую часть своей системы управления версиями.</span><span class="sxs-lookup"><span data-stu-id="5444c-113">Install the client portion of your source control provider.</span></span>  
  
2.  <span data-ttu-id="5444c-114">В среде [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]в меню **Сервис** выберите **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="5444c-114">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], on the **Tools** menu, click **Options**.</span></span>  
  
3.  <span data-ttu-id="5444c-115">В диалоговом окне **Параметры** разверните узел **система управления версиями**и выберите страницу **Выбор подключаемого модуля** .</span><span class="sxs-lookup"><span data-stu-id="5444c-115">In the **Options** dialog box, expand **Source Control**, and then click the **Plug-in Selection** page.</span></span>  
  
4.  <span data-ttu-id="5444c-116">В поле **текущий подключаемый модуль системы управления** версиями выберите подключаемый модуль системы управления версиями.</span><span class="sxs-lookup"><span data-stu-id="5444c-116">In the **Current source control plug-in** box, select the source control plug-in.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5444c-117">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="5444c-117">In This Section</span></span>  
  
|<span data-ttu-id="5444c-118">Раздел</span><span class="sxs-lookup"><span data-stu-id="5444c-118">Topic</span></span>|<span data-ttu-id="5444c-119">Описание</span><span class="sxs-lookup"><span data-stu-id="5444c-119">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="5444c-120">Основы системы управления версиями</span><span class="sxs-lookup"><span data-stu-id="5444c-120">Source Control Basics</span></span>](../../2014/database-engine/source-control-basics.md)|<span data-ttu-id="5444c-121">Определение базовой терминологии, относящейся к системе управления версиями, и описание преимуществ использования этих систем в проекте.</span><span class="sxs-lookup"><span data-stu-id="5444c-121">Defines basic source control terminology, and explains how your project can benefit from using source control services.</span></span>|  
|[<span data-ttu-id="5444c-122">Добавление решений и проектов в систему управления версиями</span><span class="sxs-lookup"><span data-stu-id="5444c-122">Add Solutions and Projects to Source Control</span></span>](../../2014/database-engine/add-solutions-and-projects-to-source-control.md)|<span data-ttu-id="5444c-123">Добавление решений и проектов в систему управления версиями в среде [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5444c-123">Explains how to use the [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environment to add solutions and projects to source control.</span></span>|  
|[<span data-ttu-id="5444c-124">Открытие решений и проектов из системы управления версиями</span><span class="sxs-lookup"><span data-stu-id="5444c-124">Open Solutions and Projects from Source Control</span></span>](../../2014/database-engine/open-solutions-and-projects-from-source-control.md)|<span data-ttu-id="5444c-125">Открытие в среде [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] решений и проектов, контролируемых системой управления версиями.</span><span class="sxs-lookup"><span data-stu-id="5444c-125">Explains how to use the [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environment to open source-controlled solutions and projects.</span></span>|  
|[<span data-ttu-id="5444c-126">Управление извлечениями</span><span class="sxs-lookup"><span data-stu-id="5444c-126">Manage Checkouts</span></span>](../../2014/database-engine/manage-checkouts.md)|<span data-ttu-id="5444c-127">Извлечение решений и файлов из системы управления версиями.</span><span class="sxs-lookup"><span data-stu-id="5444c-127">Explains how to check out solutions and files from source control.</span></span>|  
|[<span data-ttu-id="5444c-128">Управление возвратами</span><span class="sxs-lookup"><span data-stu-id="5444c-128">Manage Checkins</span></span>](../../2014/database-engine/manage-checkins.md)|<span data-ttu-id="5444c-129">Возврат решений и файлов в систему управления версиями.</span><span class="sxs-lookup"><span data-stu-id="5444c-129">Explains how to check solutions and files into source control.</span></span>|  
|[<span data-ttu-id="5444c-130">Задание и получение сведений о версии</span><span class="sxs-lookup"><span data-stu-id="5444c-130">Set and Retrieve Version Information</span></span>](../../2014/database-engine/set-and-retrieve-version-information.md)|<span data-ttu-id="5444c-131">Получение журнала проекта или элемента, получение локальной копии элемента и сравнение двух версий элемента.</span><span class="sxs-lookup"><span data-stu-id="5444c-131">Explains how to retrieve the history of a project or item, retrieve a local copy of an item, or compare two item versions.</span></span>|  
|||  
  
## <a name="see-also"></a><span data-ttu-id="5444c-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="5444c-132">See Also</span></span>  
 <span data-ttu-id="5444c-133">[обозреватель решений](../ssms/solution/solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="5444c-133">[Solution Explorer](../ssms/solution/solution-explorer.md) </span></span>  
 <span data-ttu-id="5444c-134">[Решения &#40;SQL Server Management Studio&#41;](../ssms/sql-server-management-studio-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="5444c-134">[Solutions &#40;SQL Server Management Studio&#41;](../ssms/sql-server-management-studio-ssms.md) </span></span>  
 <span data-ttu-id="5444c-135">[Проекты &#40;SQL Server Management Studio&#41;](../ssms/solution/projects-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="5444c-135">[Projects &#40;SQL Server Management Studio&#41;](../ssms/solution/projects-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="5444c-136">Файлы для управления решениями и проектами</span><span class="sxs-lookup"><span data-stu-id="5444c-136">Files That Manage Solutions and Projects</span></span>](../ssms/solution/files-that-manage-solutions-and-projects.md)  
  
  
