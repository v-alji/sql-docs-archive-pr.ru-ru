---
title: Свойства ролей пользователей (Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.userroleproperties.f1
ms.assetid: c8b22236-a8b1-4e15-b1ff-4e1909b602d3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6f79953abdf5e3d1cdb03de8c5feeb6b2de34ab7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732317"
---
# <a name="user-role-properties-management-studio"></a><span data-ttu-id="71083-102">Свойства пользовательской роли (среда Management Studio)</span><span class="sxs-lookup"><span data-stu-id="71083-102">User Role Properties (Management Studio)</span></span>
  <span data-ttu-id="71083-103">На этой странице можно просмотреть задачи, выбранные для определения роли на уровне элемента.</span><span class="sxs-lookup"><span data-stu-id="71083-103">Use this page to view which tasks are included in an item-level role definition.</span></span> <span data-ttu-id="71083-104">Эту страницу также можно использовать для изменения списка задач или модификации описания роли.</span><span class="sxs-lookup"><span data-stu-id="71083-104">You can also use this page to change the task list or modify a role description.</span></span>  
  
 <span data-ttu-id="71083-105">Определение роли на уровне элемента является именованной коллекцией задач, выполняемых пользователем относительно определенного элемента (например, папки, отчета, ресурса или общего источника данных).</span><span class="sxs-lookup"><span data-stu-id="71083-105">An item-level role definition is a named collection of tasks that users perform relative to a specific item (that is, a folder, report, resource, or shared data source).</span></span> <span data-ttu-id="71083-106">Определения ролей назначаются пользователю или группе для создания назначения роли в диспетчере отчетов.</span><span class="sxs-lookup"><span data-stu-id="71083-106">Role definitions are assigned to a user or group to create a role assignment in Report Manager.</span></span> <span data-ttu-id="71083-107">Задачи в определении роли описывают, что пользователь или группа могут делать.</span><span class="sxs-lookup"><span data-stu-id="71083-107">The tasks in the role definition describe what the user or group can do.</span></span>  
  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="71083-108">включают в себя несколько заранее заданных определений ролей на уровне элемента, с которыми может работать пользователь.</span><span class="sxs-lookup"><span data-stu-id="71083-108">includes a number of predefined item-level role definitions that you can work with.</span></span> <span data-ttu-id="71083-109">Определения ролей можно изменить, изменив список задач для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="71083-109">You can modify the role definitions by changing the task list of each one.</span></span> <span data-ttu-id="71083-110">Изменение определения роли влияет на все назначения ролей, включенные в ее определение.</span><span class="sxs-lookup"><span data-stu-id="71083-110">Editing a role definition affects all role assignments that include the role definition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="71083-111">Пользовательские назначения ролей применяются только на сервере отчетов, который работает в собственном режиме.</span><span class="sxs-lookup"><span data-stu-id="71083-111">User role assignments are used only on a report server that runs in native mode.</span></span> <span data-ttu-id="71083-112">Если сервер отчетов настроен для работы в режиме интеграции с SharePoint, то на этой странице отображаются сведения только для чтения о ролях и уровнях разрешений, которые определены на сайте SharePoint.</span><span class="sxs-lookup"><span data-stu-id="71083-112">If the report server is configured for SharePoint integration, this page displays read-only information about the roles and permission levels that are defined on the SharePoint site.</span></span>  
  
## <a name="options"></a><span data-ttu-id="71083-113">Параметры</span><span class="sxs-lookup"><span data-stu-id="71083-113">Options</span></span>  
 <span data-ttu-id="71083-114">**Название**</span><span class="sxs-lookup"><span data-stu-id="71083-114">**Name**</span></span>  
 <span data-ttu-id="71083-115">Название определения роли.</span><span class="sxs-lookup"><span data-stu-id="71083-115">Specifies the name of the role definition.</span></span>  
  
 <span data-ttu-id="71083-116">**Описание**</span><span class="sxs-lookup"><span data-stu-id="71083-116">**Description**</span></span>  
 <span data-ttu-id="71083-117">Описание определения системной роли.</span><span class="sxs-lookup"><span data-stu-id="71083-117">Shows a description of the role definition.</span></span> <span data-ttu-id="71083-118">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]это описание отображается только на данной странице.</span><span class="sxs-lookup"><span data-stu-id="71083-118">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], this description is only visible in this page.</span></span> <span data-ttu-id="71083-119">В диспетчере отчетов это описание позволяет пользователям решить, следует ли использовать роль в назначении роли.</span><span class="sxs-lookup"><span data-stu-id="71083-119">In Report Manager, this description helps users decide whether to use the role in a role assignment.</span></span>  
  
 <span data-ttu-id="71083-120">**Задача**</span><span class="sxs-lookup"><span data-stu-id="71083-120">**Task**</span></span>  
 <span data-ttu-id="71083-121">Выводит список задач на уровне элемента, которые можно выбрать для данного определения роли.</span><span class="sxs-lookup"><span data-stu-id="71083-121">Lists all item-level tasks that can be selected for this role definition.</span></span> <span data-ttu-id="71083-122">Можно добавлять или удалять элементы из списка предопределенных задач, чтобы определить, какой доступ к данному элементу будет у пользователей с данной ролью.</span><span class="sxs-lookup"><span data-stu-id="71083-122">You can add or remove items from the predefined task list to define how users access a given item through this role.</span></span> <span data-ttu-id="71083-123">Нельзя создавать новые задачи или изменять уже существующие.</span><span class="sxs-lookup"><span data-stu-id="71083-123">You cannot create new tasks, and you cannot modify existing tasks.</span></span> <span data-ttu-id="71083-124">Список задач определения ролей появляется только в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="71083-124">The task list of a role definition appears only in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="71083-125">**Описание задачи**</span><span class="sxs-lookup"><span data-stu-id="71083-125">**Task Description**</span></span>  
 <span data-ttu-id="71083-126">Выводит сведения по каждой из задач.</span><span class="sxs-lookup"><span data-stu-id="71083-126">Provides information about each task.</span></span> <span data-ttu-id="71083-127">Нельзя изменять описания задач.</span><span class="sxs-lookup"><span data-stu-id="71083-127">You cannot modify task descriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71083-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="71083-128">See Also</span></span>  
 <span data-ttu-id="71083-129">[Задачи уровня элемента](../security/tasks-and-permissions-item-level-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="71083-129">[Item-Level Tasks](../security/tasks-and-permissions-item-level-tasks.md) </span></span>  
 <span data-ttu-id="71083-130">[Определение ролей](../security/role-definitions.md) </span><span class="sxs-lookup"><span data-stu-id="71083-130">[Role Definitions](../security/role-definitions.md) </span></span>  
 <span data-ttu-id="71083-131">[Справка F1 по использованию сервера отчетов среде Management Studio](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="71083-131">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 <span data-ttu-id="71083-132">[Задачи и разрешения](../security/tasks-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="71083-132">[Tasks and Permissions](../security/tasks-and-permissions.md) </span></span>  
 [<span data-ttu-id="71083-133">Предопределенные роли</span><span class="sxs-lookup"><span data-stu-id="71083-133">Predefined Roles</span></span>](../security/role-definitions-predefined-roles.md)  
  
  
