---
title: Страница "Разрешения" или "Защищаемые объекты" | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.common.permissions.f1
- sql12.swb.SecurableAndEffectPermissions.f1
- sql12.swb.availabilitygroupproperties.permission.f1
- sql12.swb.common.columnperm.f1
- sql12.swb.SecurableAndEffectivePermission.f1
ms.assetid: b3bf077a-bec2-4161-ac0c-460586199906
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 80417c720258833850f07eb67f83f5c47f487ad2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730350"
---
# <a name="permissions-or-securables-page"></a><span data-ttu-id="62346-102">Страница «Разрешения» или «Защищаемые объекты»</span><span class="sxs-lookup"><span data-stu-id="62346-102">Permissions or Securables Page</span></span>
  <span data-ttu-id="62346-103">Страница **Разрешения** или **Защищаемые объекты** используется для просмотра или установки разрешений для защищаемых объектов.</span><span class="sxs-lookup"><span data-stu-id="62346-103">Use the **Permissions** page or the **Securables** page to view or set the permissions for securables.</span></span> <span data-ttu-id="62346-104">Эта страница может быть открыта из нескольких мест.</span><span class="sxs-lookup"><span data-stu-id="62346-104">This page can be opened from many locations.</span></span> <span data-ttu-id="62346-105">Содержимое страницы может немного измениться в зависимости от того, как открыта страница и ее содержимого.</span><span class="sxs-lookup"><span data-stu-id="62346-105">The contents of the page can change slightly, depending on how the page is opened and what it contains.</span></span> <span data-ttu-id="62346-106">Верхняя сетка страницы может быть заполнена при открытии страницы или может быть пустой.</span><span class="sxs-lookup"><span data-stu-id="62346-106">The top grid of the page might be populated when the page opens, or it might be empty.</span></span> <span data-ttu-id="62346-107">Нажмите кнопку **Поиск**для добавления элементов в верхнюю сетку.</span><span class="sxs-lookup"><span data-stu-id="62346-107">To add items to the upper grid, click **Search**.</span></span> <span data-ttu-id="62346-108">Выберите элемент в верхней сетке, затем установите нужные разрешения на вкладке **Явное** . Чтобы увидеть суммарные разрешения, используйте вкладку **Действующие** .</span><span class="sxs-lookup"><span data-stu-id="62346-108">In the upper grid, select an item, and then set the appropriate permissions on the **Explicit** tab. To view aggregated permissions, use the **Effective** tab.</span></span>  
  
 <span data-ttu-id="62346-109">Для понимания возможных сочетаний защищаемых объектов и участников см. специальные синтаксические ссылки для защищаемых объектов в разделе [GRANT (Transact-SQL)](/sql/t-sql/statements/grant-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="62346-109">To understand the possible combinations of securables and principals, see the securable-specific syntax links in the topic [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql).</span></span> <span data-ttu-id="62346-110">Дополнительные сведения см. в статье [Securables](securables.md).</span><span class="sxs-lookup"><span data-stu-id="62346-110">For more information, see [Securables](securables.md).</span></span>  
  
## <a name="page-header"></a><span data-ttu-id="62346-111">Заголовок страницы</span><span class="sxs-lookup"><span data-stu-id="62346-111">Page Header</span></span>  
 <span data-ttu-id="62346-112">Заголовок страницы **Разрешения** или **Защищаемые объекты** изменяется в зависимости от защищаемого объекта или участника.</span><span class="sxs-lookup"><span data-stu-id="62346-112">The header of the **Permissions** or **Securables** page varies depending on the securable or principal.</span></span> <span data-ttu-id="62346-113">В нем отображаются данные, соответствующие элементу, такие как имя.</span><span class="sxs-lookup"><span data-stu-id="62346-113">It displays information relevant to the item, such as its name.</span></span>  
  
## <a name="upper-grid"></a><span data-ttu-id="62346-114">Верхняя сетка</span><span class="sxs-lookup"><span data-stu-id="62346-114">Upper Grid</span></span>  
 <span data-ttu-id="62346-115">Верхняя сетка содержит один или несколько элементов, для которых могут быть установлены разрешения.</span><span class="sxs-lookup"><span data-stu-id="62346-115">The upper grid contains one or more items for which permissions can be set.</span></span> <span data-ttu-id="62346-116">В этом диалоговом окне есть кнопка **Поиск** для выбора объектов или участников, добавляемых в верхнюю сетку.</span><span class="sxs-lookup"><span data-stu-id="62346-116">This dialog box provides the **Search** button for selecting objects or principals to add to the upper grid.</span></span> <span data-ttu-id="62346-117">Имя верхней сетки может содержать **Защищаемые объекты** , или один или более типов защищаемых объектов или участников.</span><span class="sxs-lookup"><span data-stu-id="62346-117">The name of the grid might display **Securables** or one or more types of securables or principals.</span></span> <span data-ttu-id="62346-118">Отображаемые в верхней сетке столбцы меняются в зависимости от участника или защищаемого объекта.</span><span class="sxs-lookup"><span data-stu-id="62346-118">The columns that are displayed in the upper grid vary depending on the principal or securable.</span></span>  
  
 <span data-ttu-id="62346-119">**имя**;</span><span class="sxs-lookup"><span data-stu-id="62346-119">**Name**</span></span>  
 <span data-ttu-id="62346-120">Имя каждого участника или защищаемого объекта, добавляемого в сетку.</span><span class="sxs-lookup"><span data-stu-id="62346-120">The name of each principal or securable that is added to the grid.</span></span>  
  
 <span data-ttu-id="62346-121">**Тип**</span><span class="sxs-lookup"><span data-stu-id="62346-121">**Type**</span></span>  
 <span data-ttu-id="62346-122">Описывает тип каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="62346-122">Describes the type of each item.</span></span>  
  
## <a name="explicit-tab"></a><span data-ttu-id="62346-123">Вкладка «Явное»</span><span class="sxs-lookup"><span data-stu-id="62346-123">Explicit Tab</span></span>  
 <span data-ttu-id="62346-124">На вкладке **Явное** приводятся возможные разрешения для защищаемого объекта, выбранного в верхней сетке.</span><span class="sxs-lookup"><span data-stu-id="62346-124">The **Explicit** tab lists the possible permissions for the securable that are selected in the upper grid.</span></span> <span data-ttu-id="62346-125">Для настройки разрешений установите или снимите флажки **Предоставить** (или **Разрешить**), **Право передачи**и **Запретить** .</span><span class="sxs-lookup"><span data-stu-id="62346-125">To configure the permissions, select or clear the **Grant** (or **Allow**), **With Grant**, and **Deny** check boxes.</span></span> <span data-ttu-id="62346-126">Эти параметры доступны не для всех явно указанных разрешений.</span><span class="sxs-lookup"><span data-stu-id="62346-126">All options are not available for all explicit permissions.</span></span>  
  
 <span data-ttu-id="62346-127">**Разрешения**</span><span class="sxs-lookup"><span data-stu-id="62346-127">**Permissions**</span></span>  
 <span data-ttu-id="62346-128">Имя разрешения.</span><span class="sxs-lookup"><span data-stu-id="62346-128">The name of the permission.</span></span>  
  
 <span data-ttu-id="62346-129">**Grantor**</span><span class="sxs-lookup"><span data-stu-id="62346-129">**Grantor**</span></span>  
 <span data-ttu-id="62346-130">Участник, предоставивший разрешение.</span><span class="sxs-lookup"><span data-stu-id="62346-130">The principal that granted the permission.</span></span>  
  
 <span data-ttu-id="62346-131">**Право предоставил**</span><span class="sxs-lookup"><span data-stu-id="62346-131">**Grant**</span></span>  
 <span data-ttu-id="62346-132">Выберите, чтобы предоставить имени входа данное разрешение.</span><span class="sxs-lookup"><span data-stu-id="62346-132">Select to grant this permission to the login.</span></span> <span data-ttu-id="62346-133">Снимите флажок, чтобы отменить это разрешение.</span><span class="sxs-lookup"><span data-stu-id="62346-133">Clear to revoke this permission.</span></span>  
  
 <span data-ttu-id="62346-134">**Право передачи**</span><span class="sxs-lookup"><span data-stu-id="62346-134">**With Grant**</span></span>  
 <span data-ttu-id="62346-135">Отражает состояние параметра WITH GRANT для разрешения, указанного в списке.</span><span class="sxs-lookup"><span data-stu-id="62346-135">Reflects the state of the WITH GRANT option for the listed permission.</span></span> <span data-ttu-id="62346-136">Поле доступно только для чтения.</span><span class="sxs-lookup"><span data-stu-id="62346-136">This box is read-only.</span></span> <span data-ttu-id="62346-137">Для применения данного разрешения используйте инструкцию [GRANT](/sql/t-sql/statements/grant-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="62346-137">To apply this permission, use the [GRANT](/sql/t-sql/statements/grant-transact-sql) statement.</span></span>  
  
 <span data-ttu-id="62346-138">**Запретить**</span><span class="sxs-lookup"><span data-stu-id="62346-138">**Deny**</span></span>  
 <span data-ttu-id="62346-139">Выберите, чтобы запретить имени входа в данном разрешении.</span><span class="sxs-lookup"><span data-stu-id="62346-139">Select to deny this permission to the login.</span></span> <span data-ttu-id="62346-140">Снимите флажок, чтобы отменить это разрешение.</span><span class="sxs-lookup"><span data-stu-id="62346-140">Clear to revoke this permission.</span></span>  
  
 <span data-ttu-id="62346-141">**Разрешения на столбцы**</span><span class="sxs-lookup"><span data-stu-id="62346-141">**Column Permissions**</span></span>  
 <span data-ttu-id="62346-142">Для объектов, которые содержат столбцы (такие как таблицы, представления или функции, возвращающие табличные значения), кнопка **Разрешения на доступ к столбцу** открывает диалоговое окно **Разрешения на доступ к столбцу** .</span><span class="sxs-lookup"><span data-stu-id="62346-142">For objects that contain columns (such as tables, views, or table-valued functions), the **Column Permissions** button opens the **Column Permissions** dialog box.</span></span> <span data-ttu-id="62346-143">В этом диалоговом окне можно установить разрешения **Право предоставил**, **Разрешить**и **Запретить** для отдельных столбцов таблицы или представления.</span><span class="sxs-lookup"><span data-stu-id="62346-143">In this dialog box, you can set **Grant**, **Allow**, or **Deny** permissions on individual columns of a table or view.</span></span> <span data-ttu-id="62346-144">Этот параметр доступен не для всех объектов или разрешений.</span><span class="sxs-lookup"><span data-stu-id="62346-144">This option is not available for all object types or permissions.</span></span>  
  
## <a name="effective-tab"></a><span data-ttu-id="62346-145">Вкладка «Действующие»</span><span class="sxs-lookup"><span data-stu-id="62346-145">Effective Tab</span></span>  
 <span data-ttu-id="62346-146">Разрешения, которые участник связал с защищаемым объектом, могут исходить от разрешений, установленным для нескольких нескольких разных участников.</span><span class="sxs-lookup"><span data-stu-id="62346-146">The permissions that a principal has related to a securable may come from permissions that are set for several different principals.</span></span> <span data-ttu-id="62346-147">Например, имени входа разрешения могут быть предоставлены индивидуально и как члену группы.</span><span class="sxs-lookup"><span data-stu-id="62346-147">For example, a login might be granted permissions individually and also as a member of a group.</span></span> <span data-ttu-id="62346-148">Вкладка **Действующее** показывает результат объединения явных разрешений и разрешений, полученных через членство в группах и ролях.</span><span class="sxs-lookup"><span data-stu-id="62346-148">The **Effective** tab shows the result of combining explicit permissions and the permissions that are received from group or role memberships.</span></span> <span data-ttu-id="62346-149">Предоставленные разрешения объединяются.</span><span class="sxs-lookup"><span data-stu-id="62346-149">Grant permissions are aggregated.</span></span> <span data-ttu-id="62346-150">Запрет в разрешениях переопределяет все предоставленные разрешения.</span><span class="sxs-lookup"><span data-stu-id="62346-150">A deny permission overrides all grant permissions.</span></span>  
  
 <span data-ttu-id="62346-151">**Разрешения**</span><span class="sxs-lookup"><span data-stu-id="62346-151">**Permissions**</span></span>  
 <span data-ttu-id="62346-152">Имя разрешения.</span><span class="sxs-lookup"><span data-stu-id="62346-152">The name of the permission.</span></span>  
  
 <span data-ttu-id="62346-153">**Столбец**</span><span class="sxs-lookup"><span data-stu-id="62346-153">**Column**</span></span>  
 <span data-ttu-id="62346-154">Имена столбцов, на которые воздействует разрешение.</span><span class="sxs-lookup"><span data-stu-id="62346-154">The names of columns that are affected by the permission.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62346-155">См. также:</span><span class="sxs-lookup"><span data-stu-id="62346-155">See Also</span></span>  
 <span data-ttu-id="62346-156">[Роли уровня базы данных](authentication-access/database-level-roles.md) </span><span class="sxs-lookup"><span data-stu-id="62346-156">[Database-Level Roles](authentication-access/database-level-roles.md) </span></span>  
 [<span data-ttu-id="62346-157">Центр безопасности для ядра СУБД SQL Server и Базы данных Azure SQL</span><span class="sxs-lookup"><span data-stu-id="62346-157">Security Center for SQL Server Database Engine and Azure SQL Database</span></span>](security-center-for-sql-server-database-engine-and-azure-sql-database.md)  
  
  
