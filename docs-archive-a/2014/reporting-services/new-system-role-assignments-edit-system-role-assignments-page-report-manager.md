---
title: 'Страница "Создание назначения системной роли": "изменение назначения системных ролей" (диспетчер отчетов) | Документация Майкрософт'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 62a22ab9-1eb4-4ce5-8dd7-06b5ed2d9a2a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6e04ec18b8ee27c5897156753c1e4f7991991eae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656214"
---
# <a name="new-system-role-assignments-edit-system-role-assignments-page-report-manager"></a><span data-ttu-id="ee929-102">Страница "Создание назначения системной роли": "Изменение назначения системных ролей" (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="ee929-102">New System Role Assignments: Edit System Role Assignments Page (Report Manager)</span></span>
  <span data-ttu-id="ee929-103">Используйте страницу «Создание назначений системной роли» или «Изменение назначений системной роли», чтобы определить параметры безопасности сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="ee929-103">Use the New System Role Assignments or Edit System Role Assignments page to define security for the report server.</span></span> <span data-ttu-id="ee929-104">Все параметры безопасности определяются через назначение ролей, которое позволяет сопоставить отдельных пользователей и группы с задачами, которые те могут выполнять.</span><span class="sxs-lookup"><span data-stu-id="ee929-104">All security is defined through role assignments that map specific users or groups to the tasks that they can perform.</span></span> <span data-ttu-id="ee929-105">Список задач представлен в виде определения роли, которое выбирается при назначении ролей.</span><span class="sxs-lookup"><span data-stu-id="ee929-105">The task list is represented as a role definition that you select when making the role assignment.</span></span>  
  
 <span data-ttu-id="ee929-106">На уровне системы создаваемые или редактируемые назначения ролей относятся ко всему серверу отчетов.</span><span class="sxs-lookup"><span data-stu-id="ee929-106">At the system level, the role assignments that you create or modify apply to the report server as a whole.</span></span> <span data-ttu-id="ee929-107">Например, способность создавать общие расписания задается на уровне системы, поскольку общие расписания применяются во всей системе.</span><span class="sxs-lookup"><span data-stu-id="ee929-107">For example, the ability to create shared schedules is specified at the system level because shared schedules are used throughout the system.</span></span>  
  
 <span data-ttu-id="ee929-108">По умолчанию службы Reporting Services предоставляют две стандартные системные роли.</span><span class="sxs-lookup"><span data-stu-id="ee929-108">By default, Reporting Services provides two predefined system level roles:</span></span>  
  
-   <span data-ttu-id="ee929-109">Задачи роли «Системный пользователь» позволяют пользователям просматривать свойства серверов отчетов и общие расписания, а также выполнять определения отчетов, что обеспечивает для пользователей возможность просмотра отчетов с дополнительной информацией, опубликованных на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="ee929-109">System User includes tasks that allow users to view report server properties and shared schedules, and to execute report definitions, which allows users to view clickthrough reports that have been published to the report server.</span></span> <span data-ttu-id="ee929-110">Эта роль должна быть назначена большинству пользователей.</span><span class="sxs-lookup"><span data-stu-id="ee929-110">Most users should be assigned to this role.</span></span>  
  
-   <span data-ttu-id="ee929-111">Роль «Системный администратор» содержит задачи по созданию общих расписаний и управлению ими, настройке свойств сервера и созданию назначений системных ролей для других пользователей.</span><span class="sxs-lookup"><span data-stu-id="ee929-111">System Administrator includes tasks for creating and managing shared schedules, setting server properties, and creating system-level role assignments for other users.</span></span> <span data-ttu-id="ee929-112">Такой уровень разрешений требуется лишь некоторым пользователям.</span><span class="sxs-lookup"><span data-stu-id="ee929-112">Few users require permissions at this level.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="ee929-113">Навигация</span><span class="sxs-lookup"><span data-stu-id="ee929-113">Navigation</span></span>  
 <span data-ttu-id="ee929-114">Чтобы перейти к этому местоположению в пользовательском интерфейсе, используйте следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="ee929-114">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-new-system-role-assignments-or-edit-system-role-assignments-page"></a><span data-ttu-id="ee929-115">Открытие страницы «Создание назначений системной роли» или «Редактирование назначений системной роли»</span><span class="sxs-lookup"><span data-stu-id="ee929-115">To open the New System Role Assignments or Edit System Role Assignments page</span></span>  
  
1.  <span data-ttu-id="ee929-116">Откройте диспетчер отчетов.</span><span class="sxs-lookup"><span data-stu-id="ee929-116">Open Report Manager.</span></span>  
  
2.  <span data-ttu-id="ee929-117">В верхнем правом углу страницы нажмите кнопку **Настройки сайта**.</span><span class="sxs-lookup"><span data-stu-id="ee929-117">At the top of the page, in the right-hand corner, click **Site Settings**.</span></span> <span data-ttu-id="ee929-118">Откроется страница свойств сайта «Общие».</span><span class="sxs-lookup"><span data-stu-id="ee929-118">This opens the General properties page for the site.</span></span>  
  
3.  <span data-ttu-id="ee929-119">Перейдите на вкладку **Безопасность** . Для доступа к этой странице необходимо иметь разрешения диспетчера содержимого и системного администратора.</span><span class="sxs-lookup"><span data-stu-id="ee929-119">Select the **Security** tab. You must have Content Manager and System Administrator permissions to access this page.</span></span>  
  
4.  <span data-ttu-id="ee929-120">Чтобы создать новое назначение роли, на панели инструментов щелкните **Создание назначения ролей** .</span><span class="sxs-lookup"><span data-stu-id="ee929-120">To create a new role assignment, click **New Role Assignment** in the toolbar.</span></span> <span data-ttu-id="ee929-121">Чтобы изменить назначение роли, щелкните **Изменить** рядом с именем группы или пользователя на странице свойств «Безопасность».</span><span class="sxs-lookup"><span data-stu-id="ee929-121">To edit an existing role assignment, click **Edit** next to a group or user on the Security properties page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ee929-122">Варианты</span><span class="sxs-lookup"><span data-stu-id="ee929-122">Options</span></span>  
 <span data-ttu-id="ee929-123">**Группа или пользователь**</span><span class="sxs-lookup"><span data-stu-id="ee929-123">**Group or User**</span></span>  
 <span data-ttu-id="ee929-124">Введите имя группы или учетной записи пользователя в своем домене.</span><span class="sxs-lookup"><span data-stu-id="ee929-124">Type the name of a group or user account in your domain.</span></span> <span data-ttu-id="ee929-125">Если сервер отчетов выполняется под локальной учетной записью, необходимо задать локальные группы или пользователей.</span><span class="sxs-lookup"><span data-stu-id="ee929-125">If the report server is running under a local account, you must specify local groups or users.</span></span> <span data-ttu-id="ee929-126">Если сервер отчетов выполняется под учетной записью домена, необходимо задать доменные группы или пользователей.</span><span class="sxs-lookup"><span data-stu-id="ee929-126">If the report server is running under a domain account, you must specify domain groups or users.</span></span> <span data-ttu-id="ee929-127">Введите учетную запись в следующем формате: \<domain> \\<учетная запись \> .</span><span class="sxs-lookup"><span data-stu-id="ee929-127">Enter the account in this format: \<domain>\\<account\>.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ee929-128">Это поле доступно только на странице «Создание назначения ролей».</span><span class="sxs-lookup"><span data-stu-id="ee929-128">This box is available only on the New Role Assignment page.</span></span>  
  
 <span data-ttu-id="ee929-129">**Роли**</span><span class="sxs-lookup"><span data-stu-id="ee929-129">**Roles**</span></span>  
 <span data-ttu-id="ee929-130">Предоставляет список системных ролей, которые можно назначить другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="ee929-130">Provides a list of system-level roles that you can assign to other users.</span></span> <span data-ttu-id="ee929-131">Для одного назначения ролей можно указать несколько ролей.</span><span class="sxs-lookup"><span data-stu-id="ee929-131">You can specify multiple roles for a single role assignment.</span></span>  
  
 <span data-ttu-id="ee929-132">В диспетчере отчетов не отображаются задачи каждой роли и не предусмотрено способа добавления или изменения задач.</span><span class="sxs-lookup"><span data-stu-id="ee929-132">Report Manager does not display the tasks in each role or provide a way to add or modify the tasks.</span></span> <span data-ttu-id="ee929-133">Роли следует использовать в том виде, в каком они были определены.</span><span class="sxs-lookup"><span data-stu-id="ee929-133">You must use the roles as they are defined.</span></span> <span data-ttu-id="ee929-134">Для создания, изменения или удаления ролей используйте [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ee929-134">To create, modify, or delete roles, use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="ee929-135">Дополнительные сведения см. в статье [Создание, удаление и изменение ролей (среда Management Studio)](security/role-definitions-create-delete-or-modify.md).</span><span class="sxs-lookup"><span data-stu-id="ee929-135">For more information, see [Create, Delete, or Modify a Role &#40;Management Studio&#41;](security/role-definitions-create-delete-or-modify.md).</span></span>  
  
 <span data-ttu-id="ee929-136">Имейте в виду, что при работе с выпуском [!INCLUDE[ssExpressEd2005](../includes/ssexpressed2005-md.md)] with Advanced Services можно использовать только предоставленные роли по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ee929-136">Note that if you are using [!INCLUDE[ssExpressEd2005](../includes/ssexpressed2005-md.md)] with Advanced Services, you must use the default roles that are provided.</span></span>  
  
 <span data-ttu-id="ee929-137">**Описания**</span><span class="sxs-lookup"><span data-stu-id="ee929-137">**Descriptions**</span></span>  
 <span data-ttu-id="ee929-138">Отображает дополнительные сведения о роли.</span><span class="sxs-lookup"><span data-stu-id="ee929-138">Shows additional information about the role.</span></span> <span data-ttu-id="ee929-139">Для таких предопределенных ролей, как, например «Системный пользователь» или «Системный администратор», в описании приведена сводка задач, поддерживаемых каждой ролью.</span><span class="sxs-lookup"><span data-stu-id="ee929-139">For predefined roles such as System User or System Administrator, the description summarizes the tasks that each role supports.</span></span>  
  
 <span data-ttu-id="ee929-140">**Удаление назначения роли**</span><span class="sxs-lookup"><span data-stu-id="ee929-140">**Delete Role Assignment**</span></span>  
 <span data-ttu-id="ee929-141">Щелкните, чтобы удалить существующее назначение роли пользователя или группы.</span><span class="sxs-lookup"><span data-stu-id="ee929-141">Click to delete an existing role assignment for a user or a group.</span></span> <span data-ttu-id="ee929-142">Нельзя удалять последнее оставшееся назначение ролей (каждый элемент должен иметь минимум одно назначение ролей).</span><span class="sxs-lookup"><span data-stu-id="ee929-142">You cannot delete a role assignment if it is the only one left (each item must have a minimum of one role assignment).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ee929-143">Эта кнопка доступна только на странице «Изменение назначения ролей».</span><span class="sxs-lookup"><span data-stu-id="ee929-143">This button is available only on the Edit Role Assignment page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee929-144">См. также:</span><span class="sxs-lookup"><span data-stu-id="ee929-144">See Also</span></span>  
 <span data-ttu-id="ee929-145">[Справка F1 диспетчер отчетов](../../2014/reporting-services/report-manager-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="ee929-145">[Report Manager F1 Help](../../2014/reporting-services/report-manager-f1-help.md) </span></span>  
 <span data-ttu-id="ee929-146">[Назначения ролей](security/role-assignments.md) </span><span class="sxs-lookup"><span data-stu-id="ee929-146">[Role Assignments](security/role-assignments.md) </span></span>  
 [<span data-ttu-id="ee929-147">Определения ролей</span><span class="sxs-lookup"><span data-stu-id="ee929-147">Role Definitions</span></span>](security/role-definitions.md)  
  
  
