---
title: Задачи уровня системы | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- system-level tasks [Reporting Services]
ms.assetid: 7023b388-40b2-4590-b227-115cf380a1e7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 98f9390664064cd293b80d094d65c903869bc709
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739158"
---
# <a name="system-level-tasks"></a><span data-ttu-id="dbd95-102">Задачи системного уровня</span><span class="sxs-lookup"><span data-stu-id="dbd95-102">System-Level Tasks</span></span>
  <span data-ttu-id="dbd95-103">Задача системного уровня представляет собой коллекцию разрешений, касающихся операций, применяемых ко всему сайту сервера отчетов в целом.</span><span class="sxs-lookup"><span data-stu-id="dbd95-103">A system-level task is a collection of permissions that relate to operations that apply to the report server site as a whole.</span></span> [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="dbd95-104">включают также задачи уровня элемента, которые относятся к конкретным элементам.</span><span class="sxs-lookup"><span data-stu-id="dbd95-104">also includes item-level tasks that apply to specific items.</span></span> <span data-ttu-id="dbd95-105">Дополнительные сведения см. в разделе [Задачи уровня элемента](tasks-and-permissions-item-level-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="dbd95-105">For more information, see [Item-Level Tasks](tasks-and-permissions-item-level-tasks.md).</span></span> <span data-ttu-id="dbd95-106">Дополнительные сведения о задачах и правах в целом см. в разделе [Tasks and Permissions](tasks-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="dbd95-106">For more information about tasks and permissions in general, see [Tasks and Permissions](tasks-and-permissions.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dbd95-107">При работе с такими задачами программно необходимо использовать методы, которые поддерживают задачи системного уровня.</span><span class="sxs-lookup"><span data-stu-id="dbd95-107">If you are working with these tasks programmatically, you must use methods that support system-level tasks.</span></span> <span data-ttu-id="dbd95-108">Дополнительные сведения см. в разделе <xref:ReportService2010.ReportingService2010.ListTasks%2A> и <xref:ReportService2010.ReportingService2010.ListRoles%2A>.</span><span class="sxs-lookup"><span data-stu-id="dbd95-108">For more information, see <xref:ReportService2010.ReportingService2010.ListTasks%2A> and <xref:ReportService2010.ReportingService2010.ListRoles%2A>.</span></span>  
  
## <a name="permissions-in-system-level-tasks"></a><span data-ttu-id="dbd95-109">Разрешения в задачах системного уровня</span><span class="sxs-lookup"><span data-stu-id="dbd95-109">Permissions in System-Level Tasks</span></span>  
 <span data-ttu-id="dbd95-110">Следующая таблица указывает совокупность разрешений для каждой системной задачи.</span><span class="sxs-lookup"><span data-stu-id="dbd95-110">The following table identifies the collection of permissions for each system task.</span></span> <span data-ttu-id="dbd95-111">Разрешения перечисляются только в справочных целях, чтобы обеспечить более детальное описание функций, доступных с помощью каждой задачи.</span><span class="sxs-lookup"><span data-stu-id="dbd95-111">Permissions are listed for informational purposes only, to provide a more exact description of the functionality available through each task.</span></span>  
  
|<span data-ttu-id="dbd95-112">Задача</span><span class="sxs-lookup"><span data-stu-id="dbd95-112">Task</span></span>|<span data-ttu-id="dbd95-113">Разрешения</span><span class="sxs-lookup"><span data-stu-id="dbd95-113">Permissions</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="dbd95-114">Выполнение определений отчета</span><span class="sxs-lookup"><span data-stu-id="dbd95-114">Execute report definitions</span></span>|<span data-ttu-id="dbd95-115">Выполнение определений отчетов (имена разрешения и задачи одинаковы)</span><span class="sxs-lookup"><span data-stu-id="dbd95-115">Execute Report Definitions (the permission and task name are the same)</span></span>|  
|<span data-ttu-id="dbd95-116">Создание событий</span><span class="sxs-lookup"><span data-stu-id="dbd95-116">Generate events</span></span>|<span data-ttu-id="dbd95-117">Создание событий</span><span class="sxs-lookup"><span data-stu-id="dbd95-117">Generate Events</span></span>|  
|<span data-ttu-id="dbd95-118">Управление заданиями</span><span class="sxs-lookup"><span data-stu-id="dbd95-118">Manage jobs</span></span>|<span data-ttu-id="dbd95-119">Считывание системных свойств</span><span class="sxs-lookup"><span data-stu-id="dbd95-119">Read System Properties</span></span><br /><br /> <span data-ttu-id="dbd95-120">Обновление системных свойств</span><span class="sxs-lookup"><span data-stu-id="dbd95-120">Update System Properties</span></span>|  
|<span data-ttu-id="dbd95-121">Управление свойствами сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="dbd95-121">Manage report server properties</span></span>|<span data-ttu-id="dbd95-122">Считывание системных свойств</span><span class="sxs-lookup"><span data-stu-id="dbd95-122">Read System Properties</span></span><br /><br /> <span data-ttu-id="dbd95-123">Обновление системных свойств</span><span class="sxs-lookup"><span data-stu-id="dbd95-123">Update System Properties</span></span>|  
|<span data-ttu-id="dbd95-124">Управление ролями</span><span class="sxs-lookup"><span data-stu-id="dbd95-124">Manage roles</span></span>|<span data-ttu-id="dbd95-125">Создание ролей</span><span class="sxs-lookup"><span data-stu-id="dbd95-125">Create Roles</span></span><br /><br /> <span data-ttu-id="dbd95-126">Удаление ролей</span><span class="sxs-lookup"><span data-stu-id="dbd95-126">Delete Roles</span></span><br /><br /> <span data-ttu-id="dbd95-127">Считывание свойств роли</span><span class="sxs-lookup"><span data-stu-id="dbd95-127">Read Role Properties</span></span><br /><br /> <span data-ttu-id="dbd95-128">Обновление свойств роли</span><span class="sxs-lookup"><span data-stu-id="dbd95-128">Update Role Properties</span></span>|  
|<span data-ttu-id="dbd95-129">Управление общими расписаниями</span><span class="sxs-lookup"><span data-stu-id="dbd95-129">Manage shared schedules</span></span>|<span data-ttu-id="dbd95-130">Создание расписаний</span><span class="sxs-lookup"><span data-stu-id="dbd95-130">Create Schedules</span></span>|  
|<span data-ttu-id="dbd95-131">Управление безопасностью сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="dbd95-131">Manage report server security</span></span>|<span data-ttu-id="dbd95-132">Считывание правил безопасности системы</span><span class="sxs-lookup"><span data-stu-id="dbd95-132">Read System Security Policies</span></span><br /><br /> <span data-ttu-id="dbd95-133">Обновление правил безопасности системы</span><span class="sxs-lookup"><span data-stu-id="dbd95-133">Update System Security Policies</span></span>|  
|<span data-ttu-id="dbd95-134">Просмотр свойств сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="dbd95-134">View report server properties</span></span>|<span data-ttu-id="dbd95-135">Считывание системных свойств</span><span class="sxs-lookup"><span data-stu-id="dbd95-135">Read System Properties</span></span>|  
|<span data-ttu-id="dbd95-136">Просмотр общих расписаний</span><span class="sxs-lookup"><span data-stu-id="dbd95-136">View shared schedules</span></span>|<span data-ttu-id="dbd95-137">Считывание расписаний</span><span class="sxs-lookup"><span data-stu-id="dbd95-137">Read Schedules</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dbd95-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="dbd95-138">See Also</span></span>  
 [<span data-ttu-id="dbd95-139">Предоставление разрешений на сервер отчетов в собственном режиме</span><span class="sxs-lookup"><span data-stu-id="dbd95-139">Granting Permissions on a Native Mode Report Server</span></span>](granting-permissions-on-a-native-mode-report-server.md)  
  
  
