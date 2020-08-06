---
title: Страница "Свойства безопасности", элементы (диспетчер отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 351b8503-354f-4b1b-a7ac-f1245d978da0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 297ae2ceefad89d64c59b5da25d51d541917c894
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658083"
---
# <a name="security-properties-page-items-report-manager"></a><span data-ttu-id="2e9cf-102">Страница свойств «Безопасность», элементы (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="2e9cf-102">Security Properties Page, Items (Report Manager)</span></span>
  <span data-ttu-id="2e9cf-103">Страница «Свойства безопасности» используется для просмотра или изменения настроек безопасности, определяющих доступ к папкам, отчетам, моделям, ресурсам и общим источникам данных.</span><span class="sxs-lookup"><span data-stu-id="2e9cf-103">Use the Security properties page to view or modify the security settings that determine access to folders, reports, models, resources, and shared data sources.</span></span> <span data-ttu-id="2e9cf-104">Эта страница доступна для тех элементов, для защиты которых имеется разрешение.</span><span class="sxs-lookup"><span data-stu-id="2e9cf-104">This page is available for items that you have permission to secure.</span></span>  
  
 <span data-ttu-id="2e9cf-105">Доступ к элементам определяется посредством назначения ролей, который определяют задачи, которые может выполнять группа или пользователь.</span><span class="sxs-lookup"><span data-stu-id="2e9cf-105">Access to items is defined through role assignments that specify the tasks that a group or user can perform.</span></span> <span data-ttu-id="2e9cf-106">Назначение роли состоит из одного имени пользователя или группы и одного или нескольких определений ролей, задающих коллекцию задач.</span><span class="sxs-lookup"><span data-stu-id="2e9cf-106">A role assignment consists of one user or group name and one or more role definitions that specify a collection of tasks.</span></span>  
  
 <span data-ttu-id="2e9cf-107">Настройки безопасности наследуются от корневой папки к вложенным папкам и элементам в этих папках.</span><span class="sxs-lookup"><span data-stu-id="2e9cf-107">Security settings are inherited from the root folder down to subfolders and items within those folders.</span></span> <span data-ttu-id="2e9cf-108">Если наследование безопасности не отменено явно, вложенные папки и элементы наследуют контекст безопасности родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="2e9cf-108">Unless you explicitly break inherited security, subfolders and items inherit the security context of a parent item.</span></span> <span data-ttu-id="2e9cf-109">При переопределении политики безопасности для папки, находящейся в середине иерархии, все подчиненные ей элементы, включая вложенные папки, принимают новые настройки безопасности.</span><span class="sxs-lookup"><span data-stu-id="2e9cf-109">If you redefine a security policy for a folder in the middle of the hierarchy, all its child items, including subfolders, assume the new security settings.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="2e9cf-110">Навигация</span><span class="sxs-lookup"><span data-stu-id="2e9cf-110">Navigation</span></span>  
 <span data-ttu-id="2e9cf-111">Чтобы перейти к этому местоположению в пользовательском интерфейсе, используйте следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="2e9cf-111">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-security-page-for-an-item"></a><span data-ttu-id="2e9cf-112">Открытие страницы «Безопасность» элемента</span><span class="sxs-lookup"><span data-stu-id="2e9cf-112">To open the Security page for an item</span></span>  
  
1.  <span data-ttu-id="2e9cf-113">Откройте диспетчер отчетов и найдите элемент, для которого необходимо настроить параметры безопасности.</span><span class="sxs-lookup"><span data-stu-id="2e9cf-113">Open Report Manager, and locate the item for which you want to configure security settings.</span></span>  
  
2.  <span data-ttu-id="2e9cf-114">Подведите курсор к элементу и щелкните стрелку раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="2e9cf-114">Hover over the item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="2e9cf-115">В раскрывающемся меню выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="2e9cf-115">In the drop-down menu, perform one of the following steps:</span></span>  
  
    -   <span data-ttu-id="2e9cf-116">Перейдите на вкладку **Безопасность**.</span><span class="sxs-lookup"><span data-stu-id="2e9cf-116">Click **Security**.</span></span> <span data-ttu-id="2e9cf-117">Откроется страница «Свойства безопасности» элемента.</span><span class="sxs-lookup"><span data-stu-id="2e9cf-117">This opens the Security properties page for the item.</span></span>  
  
    -   <span data-ttu-id="2e9cf-118">Выберите **Управление** , чтобы открыть страницу свойств элемента «Общие».</span><span class="sxs-lookup"><span data-stu-id="2e9cf-118">Click **Manage** to open the General properties page for the item.</span></span> <span data-ttu-id="2e9cf-119">Затем перейдите на вкладку **Безопасность** .</span><span class="sxs-lookup"><span data-stu-id="2e9cf-119">Then select the **Security** tab.</span></span>  
  
 <span data-ttu-id="2e9cf-120">**Изменение параметров безопасности элемента**</span><span class="sxs-lookup"><span data-stu-id="2e9cf-120">**Edit Item Security**</span></span>  
 <span data-ttu-id="2e9cf-121">Нажмите, чтобы изменить способ защиты, определенный для текущего элемента.</span><span class="sxs-lookup"><span data-stu-id="2e9cf-121">Click to change how security is defined for the current item.</span></span> <span data-ttu-id="2e9cf-122">При редактировании безопасности для папки внесенные изменения применяются к содержимому текущей папки и всех вложенных в нее папок.</span><span class="sxs-lookup"><span data-stu-id="2e9cf-122">If you are editing security for a folder, your changes apply to the contents of the current folder and any subfolders.</span></span>  
  
 <span data-ttu-id="2e9cf-123">Эта кнопка недоступна для корневой папки.</span><span class="sxs-lookup"><span data-stu-id="2e9cf-123">This button is not available for the Home folder.</span></span>  
  
 <span data-ttu-id="2e9cf-124">При изменении параметров безопасности элемента становятся доступными следующие кнопки.</span><span class="sxs-lookup"><span data-stu-id="2e9cf-124">The following buttons become available when you edit item security.</span></span>  
  
 <span data-ttu-id="2e9cf-125">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="2e9cf-125">**Delete**</span></span>  
 <span data-ttu-id="2e9cf-126">Установите флажок рядом с именем группы или пользователя, которого нужно удалить, и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="2e9cf-126">Select the check box next to the group or user name that you want to delete and click **Delete**.</span></span> <span data-ttu-id="2e9cf-127">Нельзя удалить последнее оставшееся назначение роли, а также встроенное назначение роли (например, «Встроенные\Администраторы»), которое определяет базовые настройки безопасности для сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="2e9cf-127">You cannot delete a role assignment if it is the only one remaining, or if it is a built-in role assignment (for example, "Built-in\Administrators") that defines the security baseline for the report server.</span></span> <span data-ttu-id="2e9cf-128">При удалении назначения роли учетная запись группы или пользователя либо определения роли не удаляются.</span><span class="sxs-lookup"><span data-stu-id="2e9cf-128">Deleting a role assignment does not delete a group or user account or role definitions.</span></span>  
  
 <span data-ttu-id="2e9cf-129">**Новое назначение ролей**</span><span class="sxs-lookup"><span data-stu-id="2e9cf-129">**New Role Assignment**</span></span>  
 <span data-ttu-id="2e9cf-130">Нажмите, чтобы открыть страницу «Создание назначения ролей», позволяющую создать для текущего элемента дополнительные назначения ролей.</span><span class="sxs-lookup"><span data-stu-id="2e9cf-130">Click to open the New Role Assignment page, which is used to create additional role assignments for the current item.</span></span> <span data-ttu-id="2e9cf-131">Дополнительные сведения см. в разделе [Создание назначения ролей: страница "изменение назначения ролей" &#40;диспетчер отчетов&#41;](../../2014/reporting-services/new-role-assignment-edit-role-assignment-page-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="2e9cf-131">For more information, see [New Role Assignment: Edit Role Assignment Page &#40;Report Manager&#41;](../../2014/reporting-services/new-role-assignment-edit-role-assignment-page-report-manager.md).</span></span>  
  
 <span data-ttu-id="2e9cf-132">**Вернуться к родительским параметрам безопасности**</span><span class="sxs-lookup"><span data-stu-id="2e9cf-132">**Revert to Parent Security**</span></span>  
 <span data-ttu-id="2e9cf-133">Нажмите, чтобы присвоить параметрам безопасности значения, используемые для промежуточной родительской папки.</span><span class="sxs-lookup"><span data-stu-id="2e9cf-133">Click to reset the security settings to that of the immediate parent folder.</span></span> <span data-ttu-id="2e9cf-134">Если наследование непрерывно по иерархии папок сервера отчетов, то используются настройки безопасности папки самого высокого уровня, то есть корневой папки.</span><span class="sxs-lookup"><span data-stu-id="2e9cf-134">If inheritance is unbroken throughout the report server folder hierarchy, the security settings of the top-level folder, Home, are used.</span></span>  
  
 <span data-ttu-id="2e9cf-135">**Группа или пользователь**</span><span class="sxs-lookup"><span data-stu-id="2e9cf-135">**Group or User**</span></span>  
 <span data-ttu-id="2e9cf-136">Содержит список групп и пользователей, входящих в существующее назначение ролей для текущего элемента.</span><span class="sxs-lookup"><span data-stu-id="2e9cf-136">Lists the groups and users that are part of an existing role assignment for the current item.</span></span> <span data-ttu-id="2e9cf-137">Существующие назначения ролей для текущей папки определяются для групп и пользователей, которые выводятся в этом столбце.</span><span class="sxs-lookup"><span data-stu-id="2e9cf-137">Existing role assignments for the current folder are defined for the groups and users that appear in this column.</span></span> <span data-ttu-id="2e9cf-138">Для просмотра или редактирования назначения ролей можно щелкнуть на имени группы или пользователя.</span><span class="sxs-lookup"><span data-stu-id="2e9cf-138">You can click a group or user name to view or edit role assignment details.</span></span>  
  
 <span data-ttu-id="2e9cf-139">**Роли**</span><span class="sxs-lookup"><span data-stu-id="2e9cf-139">**Roles**</span></span>  
 <span data-ttu-id="2e9cf-140">Приводится одно или несколько определений роли, являющихся частью существующего назначения ролей.</span><span class="sxs-lookup"><span data-stu-id="2e9cf-140">Lists one or more role definitions that are part of an existing role assignment.</span></span> <span data-ttu-id="2e9cf-141">При присвоении нескольких ролей группе или учетной записи пользователя эта группа или пользователь могут выполнять все задачи, принадлежащие этим ролям.</span><span class="sxs-lookup"><span data-stu-id="2e9cf-141">If multiple roles are assigned to a group or user account, that group or user can perform all tasks that belong to those roles.</span></span> <span data-ttu-id="2e9cf-142">Чтобы просмотреть задачи, связанные с ролью, в среде SQL Server Management Studio просмотрите задачи в определении каждой роли.</span><span class="sxs-lookup"><span data-stu-id="2e9cf-142">To view the tasks that are associated with a role, use SQL Server Management Studio to view the tasks in each role definition.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e9cf-143">См. также:</span><span class="sxs-lookup"><span data-stu-id="2e9cf-143">See Also</span></span>  
 <span data-ttu-id="2e9cf-144">[Справка F1 диспетчер отчетов](../../2014/reporting-services/report-manager-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="2e9cf-144">[Report Manager F1 Help](../../2014/reporting-services/report-manager-f1-help.md) </span></span>  
 <span data-ttu-id="2e9cf-145">[Стандартные роли](security/role-definitions-predefined-roles.md) </span><span class="sxs-lookup"><span data-stu-id="2e9cf-145">[Predefined Roles](security/role-definitions-predefined-roles.md) </span></span>  
 <span data-ttu-id="2e9cf-146">[Предоставление разрешений на сервер отчетов в собственном режиме](security/granting-permissions-on-a-native-mode-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="2e9cf-146">[Granting Permissions on a Native Mode Report Server](security/granting-permissions-on-a-native-mode-report-server.md) </span></span>  
 <span data-ttu-id="2e9cf-147">[Назначения ролей](security/role-assignments.md) </span><span class="sxs-lookup"><span data-stu-id="2e9cf-147">[Role Assignments](security/role-assignments.md) </span></span>  
 [<span data-ttu-id="2e9cf-148">Определения ролей</span><span class="sxs-lookup"><span data-stu-id="2e9cf-148">Role Definitions</span></span>](security/role-definitions.md)  
  
  
