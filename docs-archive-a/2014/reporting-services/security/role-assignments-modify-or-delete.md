---
title: Изменение или удаление назначения ролей (диспетчер отчетов) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- removing role assignments
- roles [Reporting Services], assignments
- system roles [Reporting Services]
- modifying role assignments
- deleting role assignments
ms.assetid: 523bdd32-92cb-4b48-a3a9-d58b2385bde7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d67c5cdb7647d50008f72890e4ac3e3c7eed456e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732393"
---
# <a name="modify-or-delete-a-role-assignment-report-manager"></a><span data-ttu-id="d6bb1-102">Изменение или удаление назначения ролей (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="d6bb1-102">Modify or Delete a Role Assignment (Report Manager)</span></span>
  <span data-ttu-id="d6bb1-103">Назначение ролей сопоставляет учетную запись группы или пользователя со стандартным определением роли, включающим задачи, которые могут быть выполнены.</span><span class="sxs-lookup"><span data-stu-id="d6bb1-103">A role assignment maps a group or user account to a predefined role definition that includes tasks that can be performed.</span></span> <span data-ttu-id="d6bb1-104">Оно определяет типы операций, которые пользователь может выполнять с папками, отчетами, моделями и другим типом содержимого.</span><span class="sxs-lookup"><span data-stu-id="d6bb1-104">It determines the types of operations that a user can perform relative to a folder, report, model, or other content type.</span></span> <span data-ttu-id="d6bb1-105">Чтобы создать, изменить или удалить назначения ролей, используется диспетчер отчетов.</span><span class="sxs-lookup"><span data-stu-id="d6bb1-105">To create, modify, or delete role assignments, you use Report Manager.</span></span> <span data-ttu-id="d6bb1-106">После создания назначения ролей для конкретного пользователя или группы ее можно изменить, выбрав другую роль.</span><span class="sxs-lookup"><span data-stu-id="d6bb1-106">After you create a role assignment for a particular user or group, you can modify it later by selecting a different role.</span></span> <span data-ttu-id="d6bb1-107">Если нужно отменить разрешения на сервер отчетов, можно удалить на нем назначение ролей.</span><span class="sxs-lookup"><span data-stu-id="d6bb1-107">If you want to revoke permissions to a report server, you can delete a role assignment from the report server.</span></span>  
  
 <span data-ttu-id="d6bb1-108">В зависимости от цели работы можно использовать другие методы.</span><span class="sxs-lookup"><span data-stu-id="d6bb1-108">Depending on your objective, alternative approaches might be more appropriate.</span></span> <span data-ttu-id="d6bb1-109">Например, настроить определение ролей или создать новое либо изменить членство учетной записи группы в Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d6bb1-109">Examples include customizing or creating a new role definition, or modifying the membership of a group account in Active Directory.</span></span>  
  
 <span data-ttu-id="d6bb1-110">Предположим, что существует группа пользователей, для которой необходим полный доступ к серверу отчетов и управление содержимым, но она не должна иметь полный набор разрешений, связанных с диспетчером содержимого.</span><span class="sxs-lookup"><span data-stu-id="d6bb1-110">For example, suppose you have a group of users who need to fully manage their content, but should not have the full set of permissions associated with Content Manager.</span></span> <span data-ttu-id="d6bb1-111">В этом случае можно создать новое определение ролей с именем «Диспетчера содержимого отдела», включающее все задачи диспетчера содержимого, кроме задачи **Установка политики безопасности для элементов**.</span><span class="sxs-lookup"><span data-stu-id="d6bb1-111">In this case, you could create a new role definition called Department Content Manager that includes all of the tasks in Content Manager except **Set security policies for items**.</span></span>  
  
 <span data-ttu-id="d6bb1-112">Точно так же, поскольку системному администратору или администратору сети легче управлять учетными записями группы Active Directory, чем назначениями ролей в диспетчере отчетов, можно снизить издержки управления назначениями ролей, создав единое назначение ролей для учетной записи группы, а затем настраивать членство в группе, если пользователям больше не требуется доступ к отчетам.</span><span class="sxs-lookup"><span data-stu-id="d6bb1-112">Similarly, if you are a system or network administrator and it is easier for you to manage Active Directory group accounts than role assignments in Report Manager, you could reduce the overhead of managing role assignments by creating a single role assignment for a group account, and then adjust group membership when users no longer require access to reports.</span></span>  
  
 <span data-ttu-id="d6bb1-113">Если обнаружите, что лучшим подходом является изменение или удаление назначения ролей, не забывайте проверять как назначения системных ролей, так и назначения ролей на уровне элементов.</span><span class="sxs-lookup"><span data-stu-id="d6bb1-113">If you determine that modifying or deleting a role assignment is the best approach, remember to check for both system role assignments and item role assignments.</span></span> <span data-ttu-id="d6bb1-114">Каждый тип назначения ролей настраивается на разных страницах диспетчера отчетов.</span><span class="sxs-lookup"><span data-stu-id="d6bb1-114">Each type of role assignment is configured through different pages in Report Manager.</span></span>  
  
### <a name="to-modify-or-delete-a-system-role-assignment"></a><span data-ttu-id="d6bb1-115">Удаление или изменение назначения системной роли</span><span class="sxs-lookup"><span data-stu-id="d6bb1-115">To modify or delete a system role assignment</span></span>  
  
1.  <span data-ttu-id="d6bb1-116">Запустите [Диспетчер отчетов (службы Reporting Services в основном режиме)](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="d6bb1-116">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="d6bb1-117">Щелкните элемент **Настройки сайта**.</span><span class="sxs-lookup"><span data-stu-id="d6bb1-117">Click **Site Settings**.</span></span>  
  
3.  <span data-ttu-id="d6bb1-118">Перейдите на вкладку **Безопасность**.</span><span class="sxs-lookup"><span data-stu-id="d6bb1-118">Click **Security**.</span></span> <span data-ttu-id="d6bb1-119">Все системные назначения ролей, определенные для сервера или масштабного развертывания, перечислены по имени учетной записи.</span><span class="sxs-lookup"><span data-stu-id="d6bb1-119">All system-level role assignments currently defined for the server or scale-out deployment are listed by account name.</span></span>  
  
4.  <span data-ttu-id="d6bb1-120">Найдите назначение ролей, которое необходимо изменить или удалить.</span><span class="sxs-lookup"><span data-stu-id="d6bb1-120">Find the role assignment that you want to modify or delete.</span></span>  
  
5.  <span data-ttu-id="d6bb1-121">Чтобы добавить или удалить роль для конкретного пользователя или группы, нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="d6bb1-121">To add or remove the role for a particular user or group, click **Edit**.</span></span>  
  
6.  <span data-ttu-id="d6bb1-122">Чтобы удалить назначение ролей, установите флажок рядом с пользователем или группой, а затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="d6bb1-122">To delete a role assignment, click the check box next to the user or group name, and then click **Delete**.</span></span>  
  
### <a name="to-modify-or-delete-an-item-role-assignment"></a><span data-ttu-id="d6bb1-123">Изменение или удаление назначения ролей на уровне элементов</span><span class="sxs-lookup"><span data-stu-id="d6bb1-123">To modify or delete an item role assignment</span></span>  
  
1.  <span data-ttu-id="d6bb1-124">Запустите **Диспетчер отчетов** и найдите элемент, для которого необходимо изменить или удалить назначение ролей.</span><span class="sxs-lookup"><span data-stu-id="d6bb1-124">Start **Report Manager** and locate the item for which you want to edit or delete a role assignment.</span></span>  
  
2.  <span data-ttu-id="d6bb1-125">Подведите курсор к элементу и щелкните стрелку раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="d6bb1-125">Hover over the item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="d6bb1-126">В раскрывающемся меню выберите **Безопасность**.</span><span class="sxs-lookup"><span data-stu-id="d6bb1-126">In the drop-down menu, click **Security**.</span></span>  
  
4.  <span data-ttu-id="d6bb1-127">Найдите назначение ролей, которое необходимо изменить или удалить.</span><span class="sxs-lookup"><span data-stu-id="d6bb1-127">Find the role assignment that you want to modify or delete.</span></span>  
  
5.  <span data-ttu-id="d6bb1-128">Чтобы добавить или удалить роль для конкретного пользователя или группы, нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="d6bb1-128">To add or remove the role for a particular user or group, click **Edit**.</span></span>  
  
6.  <span data-ttu-id="d6bb1-129">Чтобы удалить назначение ролей, установите флажок рядом с пользователем или группой, а затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="d6bb1-129">To delete a role assignment, click the check box next to the user or group name, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6bb1-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="d6bb1-130">See Also</span></span>  
 <span data-ttu-id="d6bb1-131">(create-and-manage-role-assignments.md)</span><span class="sxs-lookup"><span data-stu-id="d6bb1-131">(create-and-manage-role-assignments.md)</span></span>   
 <span data-ttu-id="d6bb1-132">[Назначения ролей](role-assignments.md) </span><span class="sxs-lookup"><span data-stu-id="d6bb1-132">[Role Assignments](role-assignments.md) </span></span>  
 <span data-ttu-id="d6bb1-133">[Страница "Параметры сайта" &#40;диспетчер отчетов&#41;](../site-settings-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="d6bb1-133">[Site Settings Page &#40;Report Manager&#41;](../site-settings-page-report-manager.md) </span></span>  
 [<span data-ttu-id="d6bb1-134">Страница "Создание назначения системной роли": "изменение назначения системных ролей" (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="d6bb1-134">New System Role Assignments: Edit System Role Assignments Page &#40;Report Manager&#41;</span></span>](../new-system-role-assignments-edit-system-role-assignments-page-report-manager.md)  
  
  
