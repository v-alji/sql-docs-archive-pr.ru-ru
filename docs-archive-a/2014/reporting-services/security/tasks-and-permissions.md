---
title: Задачи и разрешения | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- permissions [Reporting Services], tasks
- role-based security [Reporting Services], permissions
- security [Reporting Services], tasks
- security [Reporting Services], permissions
- role-based security [Reporting Services], tasks
- predefined tasks [Reporting Services]
- tasks [Reporting Services]
ms.assetid: d7ff90b5-b976-4270-b9ad-9d7b801d8263
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 01cbf00850c5dd57e7ca1575a1a0cb826c009714
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739146"
---
# <a name="tasks-and-permissions"></a><span data-ttu-id="cc7b7-102">Задачи и разрешения</span><span class="sxs-lookup"><span data-stu-id="cc7b7-102">Tasks and Permissions</span></span>
  <span data-ttu-id="cc7b7-103">В службах [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]под *задачами* понимаются действия, которые может выполнить пользователь или администратор.</span><span class="sxs-lookup"><span data-stu-id="cc7b7-103">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], *tasks* are actions that a user or administrator can perform.</span></span> <span data-ttu-id="cc7b7-104">Набор задач предопределен заранее.</span><span class="sxs-lookup"><span data-stu-id="cc7b7-104">Tasks are predefined.</span></span> <span data-ttu-id="cc7b7-105">Создавать пользовательские задачи или изменять существующие задачи нельзя ни программным способом, ни с помощью инструментальных средств.</span><span class="sxs-lookup"><span data-stu-id="cc7b7-105">You cannot create custom tasks or modify the ones provided either programmatically or through a tool.</span></span> <span data-ttu-id="cc7b7-106">Всего существует двадцать пять задач.</span><span class="sxs-lookup"><span data-stu-id="cc7b7-106">There are twenty-five tasks in all.</span></span> <span data-ttu-id="cc7b7-107">Они охватывают весь набор операций, доступных в рамках безопасности, основанной на ролях.</span><span class="sxs-lookup"><span data-stu-id="cc7b7-107">These tasks comprise the entire set of operations that are available in role-based security.</span></span> <span data-ttu-id="cc7b7-108">В качестве примеров задач можно привести «Просмотр отчетов», «Управление отчетами», «Управление свойствами сервера отчетов».</span><span class="sxs-lookup"><span data-stu-id="cc7b7-108">Some examples of tasks include "View reports," "Manage reports," and "Manage report server properties."</span></span>  
  
 <span data-ttu-id="cc7b7-109">Каждая задача состоит из набора разрешений, которые также заранее определены.</span><span class="sxs-lookup"><span data-stu-id="cc7b7-109">Each task consists of a set of permissions, which are also predefined.</span></span> <span data-ttu-id="cc7b7-110">Например задача «Управление папками» содержит разрешения на создание и удаление папок, а также на просмотр и изменение их свойств.</span><span class="sxs-lookup"><span data-stu-id="cc7b7-110">For example, the "Manage folders" task contains permissions to create and delete folders and view and update folder properties.</span></span> <span data-ttu-id="cc7b7-111">Для полноты описания задач для каждой из них в документацию включены разрешения.</span><span class="sxs-lookup"><span data-stu-id="cc7b7-111">Permissions for each task are documented to provide a more exact description of each task.</span></span> <span data-ttu-id="cc7b7-112">Прямой доступ к разрешениям или их указание в назначениях ролей невозможно.</span><span class="sxs-lookup"><span data-stu-id="cc7b7-112">It is not possible to interact with permissions directly or to specify them in role assignments.</span></span> <span data-ttu-id="cc7b7-113">Разрешения предоставляются пользователям косвенным образом, через задачи, включенные в определения ролей.</span><span class="sxs-lookup"><span data-stu-id="cc7b7-113">Users are granted permissions indirectly through the tasks that are included in role definitions.</span></span>  
  
 <span data-ttu-id="cc7b7-114">Задача может быть выполнена только в том случае, если она является частью роли, а эта роль включена в назначение ролей.</span><span class="sxs-lookup"><span data-stu-id="cc7b7-114">Tasks can be performed only if they are part of a role and that role is included in a role assignment.</span></span> <span data-ttu-id="cc7b7-115">Таким образом, если задача «Просмотр моделей» не включена в роль либо если эта роль не включена в назначение ролей, пользователи не могут просматривать модели отчетов.</span><span class="sxs-lookup"><span data-stu-id="cc7b7-115">Thus, if the View Models task is not included in a role, or that role is not included in a role assignment, users cannot view report models.</span></span> <span data-ttu-id="cc7b7-116">Следующая диаграмма показывает, каким образом разрешения объединяются в задачи, а задачи — в роли, которые могут быть использованы для конкретных назначений ролей.</span><span class="sxs-lookup"><span data-stu-id="cc7b7-116">The following diagram shows how permissions are combined into tasks, and how tasks are combined into roles that can be used for specific role assignments.</span></span>  
  
 <span data-ttu-id="cc7b7-117">![Диаграмма разрешений и задач](../media/report-securityobjects.gif "Диаграмма разрешений и задач")</span><span class="sxs-lookup"><span data-stu-id="cc7b7-117">![Permissions and task diagram](../media/report-securityobjects.gif "Permissions and task diagram")</span></span>  
<span data-ttu-id="cc7b7-118">Диаграмма разрешений и задач</span><span class="sxs-lookup"><span data-stu-id="cc7b7-118">Permissions and task diagram</span></span>  
  
## <a name="system-and-item-level-tasks"></a><span data-ttu-id="cc7b7-119">Задачи системного уровня и задачи уровня элемента</span><span class="sxs-lookup"><span data-stu-id="cc7b7-119">System and Item Level Tasks</span></span>  
 <span data-ttu-id="cc7b7-120">Задачи делятся на две категории: задачи системного уровня и задачи уровня элемента.</span><span class="sxs-lookup"><span data-stu-id="cc7b7-120">Tasks fall into two categories: system level and item level.</span></span> <span data-ttu-id="cc7b7-121">Роль может включать задачи только одной категории.</span><span class="sxs-lookup"><span data-stu-id="cc7b7-121">A role can include tasks only from a single category.</span></span> <span data-ttu-id="cc7b7-122">В следующей таблице описана каждая из категорий задач.</span><span class="sxs-lookup"><span data-stu-id="cc7b7-122">The following table describes each category of tasks.</span></span>  
  
|<span data-ttu-id="cc7b7-123">Категория</span><span class="sxs-lookup"><span data-stu-id="cc7b7-123">Category</span></span>|<span data-ttu-id="cc7b7-124">Description</span><span class="sxs-lookup"><span data-stu-id="cc7b7-124">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="cc7b7-125">Задачи уровня элемента</span><span class="sxs-lookup"><span data-stu-id="cc7b7-125">Item-Level Tasks</span></span>](tasks-and-permissions-item-level-tasks.md)|<span data-ttu-id="cc7b7-126">Действия, выполняемые над управляемыми сервером отчетов элементами (папками, отчетами, моделями отчетов и ресурсами).</span><span class="sxs-lookup"><span data-stu-id="cc7b7-126">Actions that are performed on items managed by a report server, such as folders, reports, report models, and resources.</span></span><br /><br /> <span data-ttu-id="cc7b7-127">Задачи уровня элемента выполняются в пространстве имен папок сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="cc7b7-127">Item-level tasks are scoped to the report server folder namespace.</span></span> <span data-ttu-id="cc7b7-128">Для всех элементов, к которым доступ осуществляется через папки на сервере отчетов или по URL-адресу, защищены с помощью назначений ролей, включающих задачи уровня элемента.</span><span class="sxs-lookup"><span data-stu-id="cc7b7-128">All items that you access through the folders on a report server or through URL access are secured by role assignments that include item-level tasks.</span></span>|  
|[<span data-ttu-id="cc7b7-129">Задачи системного уровня</span><span class="sxs-lookup"><span data-stu-id="cc7b7-129">System-Level Tasks</span></span>](tasks-and-permissions-system-level-tasks.md)|<span data-ttu-id="cc7b7-130">Действия, выполняемые на уровне системы (например, управление заданиями или общими расписаниями), которые могут использоваться со многими элементами.</span><span class="sxs-lookup"><span data-stu-id="cc7b7-130">Actions that are performed at the system level, such as managing jobs or shared schedules that can be used with many items.</span></span> <span data-ttu-id="cc7b7-131">Задачи системного уровня выполняются вне пространства имен папок сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="cc7b7-131">System-level tasks are scoped outside of the report server folder namespace.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cc7b7-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="cc7b7-132">See Also</span></span>  
 <span data-ttu-id="cc7b7-133">[Определение ролей](role-definitions.md) </span><span class="sxs-lookup"><span data-stu-id="cc7b7-133">[Role Definitions](role-definitions.md) </span></span>  
 <span data-ttu-id="cc7b7-134">[Стандартные роли](role-definitions-predefined-roles.md) </span><span class="sxs-lookup"><span data-stu-id="cc7b7-134">[Predefined Roles](role-definitions-predefined-roles.md) </span></span>  
 [<span data-ttu-id="cc7b7-135">Предоставление разрешений на сервер отчетов в собственном режиме</span><span class="sxs-lookup"><span data-stu-id="cc7b7-135">Granting Permissions on a Native Mode Report Server</span></span>](granting-permissions-on-a-native-mode-report-server.md)  
  
  
