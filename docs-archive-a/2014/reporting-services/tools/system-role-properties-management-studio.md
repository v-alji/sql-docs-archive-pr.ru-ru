---
title: Свойства ролей системы (Management Studio) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.systemroleproperties.f1
ms.assetid: 0210fc2a-74fb-41dd-8e39-4830047ec417
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b37ebb1cb95d6628884d81156c9c1bc29bff86fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656972"
---
# <a name="system-role-properties-management-studio"></a><span data-ttu-id="7f166-102">Свойства системной роли (среда Management Studio)</span><span class="sxs-lookup"><span data-stu-id="7f166-102">System Role Properties (Management Studio)</span></span>
  <span data-ttu-id="7f166-103">Страница «Системные роли» используется для просмотра определений системных ролей, определенных в настоящее время для сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="7f166-103">Use the System Roles page to view the system role definitions that are currently defined for the report server.</span></span> <span data-ttu-id="7f166-104">Определение системной роли содержит именованную коллекцию задач, которые выполняются применительно ко всему сайту, а не к отдельному объекту.</span><span class="sxs-lookup"><span data-stu-id="7f166-104">A system role definition contains a named collection of tasks that are performed relative to the entire site, instead of an individual item.</span></span> <span data-ttu-id="7f166-105">Определения ролей присваиваются пользователям или группам для создания назначения ролей.</span><span class="sxs-lookup"><span data-stu-id="7f166-105">Role definitions are assigned to a user or groups to create a resulting role assignment.</span></span> <span data-ttu-id="7f166-106">Задачи в определении ролей задают, какие действия может выполнять пользователь или группа.</span><span class="sxs-lookup"><span data-stu-id="7f166-106">The tasks in the role definition specify what the user or group can do.</span></span>  
  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="7f166-107">есть две стандартные системные роли: **Системный администратор** и **Системный пользователь**.</span><span class="sxs-lookup"><span data-stu-id="7f166-107">has two predefined system role definitions: **System Administrator** and **System User**.</span></span> <span data-ttu-id="7f166-108">Можно изменять эти определения ролей, изменяя список задач, или создать новую системную роль, поддерживающую другую комбинацию задач.</span><span class="sxs-lookup"><span data-stu-id="7f166-108">You can modify these role definitions by changing the task list, or you can create a new system role that supports a different combination of tasks.</span></span> <span data-ttu-id="7f166-109">Изменение определения роли влияет на все назначения ролей, включенные в ее определение.</span><span class="sxs-lookup"><span data-stu-id="7f166-109">Editing a role definition affects all role assignments that include the role definition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7f166-110">Назначения системных ролей используются только на сервере отчетов, который работает в собственном режиме.</span><span class="sxs-lookup"><span data-stu-id="7f166-110">System role assignments are used only on a report server that runs in native mode.</span></span> <span data-ttu-id="7f166-111">Если сервер отчетов настроен для интеграции с SharePoint, эта страница недоступна.</span><span class="sxs-lookup"><span data-stu-id="7f166-111">If the report server is configured for SharePoint integration, this page is not available.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7f166-112">Параметры</span><span class="sxs-lookup"><span data-stu-id="7f166-112">Options</span></span>  
 <span data-ttu-id="7f166-113">**Название**</span><span class="sxs-lookup"><span data-stu-id="7f166-113">**Name**</span></span>  
 <span data-ttu-id="7f166-114">Определяет имя определения системной роли.</span><span class="sxs-lookup"><span data-stu-id="7f166-114">Specifies the name of the system role definition.</span></span>  
  
 <span data-ttu-id="7f166-115">**Описание**</span><span class="sxs-lookup"><span data-stu-id="7f166-115">**Description**</span></span>  
 <span data-ttu-id="7f166-116">Отображает описание определения системной роли.</span><span class="sxs-lookup"><span data-stu-id="7f166-116">Shows a description of the system role definition.</span></span> <span data-ttu-id="7f166-117">В [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] это описание отображается только на этой странице.</span><span class="sxs-lookup"><span data-stu-id="7f166-117">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], this description is only visible in this page.</span></span> <span data-ttu-id="7f166-118">Пользователи, просматривающие этот элемент с помощью диспетчера отчетов, могут видеть это описание при просмотре данной иерархии папок.</span><span class="sxs-lookup"><span data-stu-id="7f166-118">Users who view this item through Report Manager may see this description when browsing the folder hierarchy.</span></span>  
  
 <span data-ttu-id="7f166-119">**Задача**</span><span class="sxs-lookup"><span data-stu-id="7f166-119">**Task**</span></span>  
 <span data-ttu-id="7f166-120">Выводит список задач на уровне системы, которые можно выбрать для данного определения роли.</span><span class="sxs-lookup"><span data-stu-id="7f166-120">Lists all system-level tasks that can be selected for this role definition.</span></span> <span data-ttu-id="7f166-121">Можно добавлять или удалять элементы из списка предопределенных задач, чтобы определить, какой доступ к данному элементу будет у пользователей с данной ролью.</span><span class="sxs-lookup"><span data-stu-id="7f166-121">You can add or remove items from the predefined task list to define how users access a given item through this role.</span></span> <span data-ttu-id="7f166-122">Нельзя создавать новые задачи или изменять уже существующие.</span><span class="sxs-lookup"><span data-stu-id="7f166-122">You cannot create new tasks, and you cannot modify existing tasks.</span></span>  
  
 <span data-ttu-id="7f166-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="7f166-123">**Description**</span></span>  
 <span data-ttu-id="7f166-124">Выводит сведения по каждой из задач.</span><span class="sxs-lookup"><span data-stu-id="7f166-124">Provides information about each task.</span></span> <span data-ttu-id="7f166-125">Нельзя изменять описания задач.</span><span class="sxs-lookup"><span data-stu-id="7f166-125">You cannot modify task descriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f166-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="7f166-126">See Also</span></span>  
 <span data-ttu-id="7f166-127">[Справка F1 по использованию сервера отчетов среде Management Studio](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="7f166-127">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 <span data-ttu-id="7f166-128">[Задачи системного уровня](../security/tasks-and-permissions-system-level-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="7f166-128">[System-Level Tasks](../security/tasks-and-permissions-system-level-tasks.md) </span></span>  
 <span data-ttu-id="7f166-129">[Задачи и разрешения](../security/tasks-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="7f166-129">[Tasks and Permissions](../security/tasks-and-permissions.md) </span></span>  
 [<span data-ttu-id="7f166-130">Предопределенные роли</span><span class="sxs-lookup"><span data-stu-id="7f166-130">Predefined Roles</span></span>](../security/role-definitions-predefined-roles.md)  
  
  
