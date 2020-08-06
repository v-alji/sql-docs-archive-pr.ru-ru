---
title: Способ определения разрешений (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- permissions [Master Data Services], determining permissions
ms.assetid: 1dc0b43a-d023-4e7d-b027-8b1459fd058c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 3ea3306b772224bc8602659c7e17e8dc1634f0d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665397"
---
# <a name="how-permissions-are-determined-master-data-services"></a><span data-ttu-id="e87bf-102">Способ определения разрешений (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="e87bf-102">How Permissions Are Determined (Master Data Services)</span></span>
  <span data-ttu-id="e87bf-103">Простейшим способом настройки безопасности служб [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]является назначение разрешений на объекты модели для группы, членом которой является пользователь.</span><span class="sxs-lookup"><span data-stu-id="e87bf-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], the simplest way to configure security is to assign model object permissions to a group that the user is a member of.</span></span>

 <span data-ttu-id="e87bf-104">Настройка безопасности становится более сложной в следующих случаях.</span><span class="sxs-lookup"><span data-stu-id="e87bf-104">Security becomes more complex when:</span></span>

-   <span data-ttu-id="e87bf-105">Назначены разрешения как для объектов модели, так и для элементов иерархии.</span><span class="sxs-lookup"><span data-stu-id="e87bf-105">Both model object and hierarchy member permissions are assigned.</span></span>

-   <span data-ttu-id="e87bf-106">Пользователь принадлежит к группам, причем разрешения назначены как для пользователя, так и для групп.</span><span class="sxs-lookup"><span data-stu-id="e87bf-106">The user belongs to groups and permission is assigned to both the user and groups.</span></span>

-   <span data-ttu-id="e87bf-107">Пользователь принадлежит к группам, причем разрешения назначены для нескольких групп.</span><span class="sxs-lookup"><span data-stu-id="e87bf-107">The user belongs to groups and permission is assigned to multiple groups.</span></span>

## <a name="permissions-assigned-to-a-single-group-or-user"></a><span data-ttu-id="e87bf-108">Разрешения, назначенные одной группе или одному пользователю</span><span class="sxs-lookup"><span data-stu-id="e87bf-108">Permissions assigned to a single group or user</span></span>
 <span data-ttu-id="e87bf-109">Если разрешения назначаются одной группе или одному пользователю, они определяются на основании следующего рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="e87bf-109">If you assign permissions to a single group or user, permissions are determined based on the following workflow.</span></span>

 <span data-ttu-id="e87bf-110">![mds_conc_security_no_overlap](../../2014/master-data-services/media/mds-conc-security-no-overlap.gif "mds_conc_security_no_overlap")</span><span class="sxs-lookup"><span data-stu-id="e87bf-110">![mds_conc_security_no_overlap](../../2014/master-data-services/media/mds-conc-security-no-overlap.gif "mds_conc_security_no_overlap")</span></span>

### <a name="step-1-effective-attribute-permissions-are-determined"></a><span data-ttu-id="e87bf-111">Шаг 1. Определяются действующие разрешения для атрибутов.</span><span class="sxs-lookup"><span data-stu-id="e87bf-111">Step 1: Effective attribute permissions are determined.</span></span>
 <span data-ttu-id="e87bf-112">Следующий список показывает, как определяются действующие разрешения для атрибутов.</span><span class="sxs-lookup"><span data-stu-id="e87bf-112">The following list describes how effective attribute permissions are determined:</span></span>

-   <span data-ttu-id="e87bf-113">Разрешения, назначенные для объектов модели, определяют, к каким атрибутам имеет доступ пользователь.</span><span class="sxs-lookup"><span data-stu-id="e87bf-113">Permissions assigned to model objects determine which attributes a user can access.</span></span>

-   <span data-ttu-id="e87bf-114">Все объекты модели автоматически наследуют разрешение от ближайшего объекта на более высоком уровне в структуре модели.</span><span class="sxs-lookup"><span data-stu-id="e87bf-114">All model objects automatically inherit permission from the closest object at a higher level in the model structure.</span></span>

-   <span data-ttu-id="e87bf-115">Всем объектам на том же уровне, на котором находится сущность, в разрешении неявно отказывается.</span><span class="sxs-lookup"><span data-stu-id="e87bf-115">Any objects at the same level as the entity are implicitly denied.</span></span>

-   <span data-ttu-id="e87bf-116">Всем объектам на более высоком уровне предоставляется навигационный доступ.</span><span class="sxs-lookup"><span data-stu-id="e87bf-116">Any objects at a higher level are given navigational access.</span></span> <span data-ttu-id="e87bf-117">Дополнительные сведения о навигационном доступе см. в разделе [навигационные &#40;Master Data Services&#41;](navigational-access-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="e87bf-117">For more information about navigational access, see [Navigational Access &#40;Master Data Services&#41;](navigational-access-master-data-services.md).</span></span>

 <span data-ttu-id="e87bf-118">В этом примере разрешение **только для чтения** назначается сущности, и это разрешение наследуется его атрибутом, который находится на более низком уровне структуры модели.</span><span class="sxs-lookup"><span data-stu-id="e87bf-118">In this example, **Read-only** permission is assigned to an entity and that permission is inherited by its attribute, which is at a lower level in the model structure.</span></span> <span data-ttu-id="e87bf-119">Модель предоставляет навигационный доступ к данной сущности и ее атрибуту.</span><span class="sxs-lookup"><span data-stu-id="e87bf-119">The model provides navigational access to this entity and its attribute.</span></span> <span data-ttu-id="e87bf-120">Другая сущность модели не имеет явно назначенного разрешения и не наследует никаких разрешений, поэтому доступ для нее неявно закрыт.</span><span class="sxs-lookup"><span data-stu-id="e87bf-120">The other entity in the model has no explicit permission assigned and does not inherit any permissions, so it is implicitly denied.</span></span>

 <span data-ttu-id="e87bf-121">![mds_conc_inheritance_model](../../2014/master-data-services/media/mds-conc-inheritance-model.gif "mds_conc_inheritance_model")</span><span class="sxs-lookup"><span data-stu-id="e87bf-121">![mds_conc_inheritance_model](../../2014/master-data-services/media/mds-conc-inheritance-model.gif "mds_conc_inheritance_model")</span></span>

### <a name="step-2-if-hierarchy-member-permissions-are-assigned-effective-member-permissions-are-determined"></a><span data-ttu-id="e87bf-122">Шаг 2. Если назначены разрешения для элементов иерархии, определяются действующие разрешения для элементов.</span><span class="sxs-lookup"><span data-stu-id="e87bf-122">Step 2: If hierarchy member permissions are assigned, effective member permissions are determined.</span></span>
 <span data-ttu-id="e87bf-123">Следующий список показывает, как определяются действующие разрешения для элементов иерархии.</span><span class="sxs-lookup"><span data-stu-id="e87bf-123">The following list describes how effective hierarchy member permissions are determined:</span></span>

-   <span data-ttu-id="e87bf-124">Разрешения, назначенные для узлов иерархии, определяют, к каким элементам имеет доступ пользователь.</span><span class="sxs-lookup"><span data-stu-id="e87bf-124">Permissions assigned to hierarchy nodes determine which members a user can access.</span></span>

-   <span data-ttu-id="e87bf-125">Все узлы иерархии автоматически наследуют разрешение от ближайшего объекта на более высоком уровне в структуре иерархии.</span><span class="sxs-lookup"><span data-stu-id="e87bf-125">All nodes in a hierarchy automatically inherit permission from the closest object at a higher level in the hierarchy structure.</span></span>

-   <span data-ttu-id="e87bf-126">Всем узлам того же уровня в разрешении неявно отказывается.</span><span class="sxs-lookup"><span data-stu-id="e87bf-126">Any nodes at the same level are implicitly denied.</span></span>

-   <span data-ttu-id="e87bf-127">Любым узлам на более высоких уровнях, которые не имеют явно назначенных разрешений, в разрешении неявно отказывается.</span><span class="sxs-lookup"><span data-stu-id="e87bf-127">Any nodes at higher levels that do not have permissions assigned are implicitly denied.</span></span>

 <span data-ttu-id="e87bf-128">В этом примере разрешение **только на чтение** назначается одному узлу иерархии, и это разрешение наследуется узлом нижнего уровня в структуре иерархии.</span><span class="sxs-lookup"><span data-stu-id="e87bf-128">In this example, **Read-only** permission is assigned to one node of the hierarchy and that permission is inherited by a node at a lower level in the hierarchy structure.</span></span> <span data-ttu-id="e87bf-129">Корневому узлу разрешения не назначены, поэтому в разрешении ему неявно отказано.</span><span class="sxs-lookup"><span data-stu-id="e87bf-129">The root has no permission assigned, so it is implicitly denied.</span></span> <span data-ttu-id="e87bf-130">Другой узел в структуре иерархии не имеет явно назначенного разрешения и не наследует никаких разрешений, поэтому доступ для него неявно закрыт.</span><span class="sxs-lookup"><span data-stu-id="e87bf-130">The other node in the hierarchy structure has no explicit permission assigned and does not inherit any permissions, so it is implicitly denied.</span></span>

 <span data-ttu-id="e87bf-131">![mds_conc_inheritance_hierarchy](../../2014/master-data-services/media/mds-conc-inheritance-hierarchy.gif "mds_conc_inheritance_hierarchy")</span><span class="sxs-lookup"><span data-stu-id="e87bf-131">![mds_conc_inheritance_hierarchy](../../2014/master-data-services/media/mds-conc-inheritance-hierarchy.gif "mds_conc_inheritance_hierarchy")</span></span>

### <a name="step-3-the-intersection-of-attribute-and-member-permissions-is-determined"></a><span data-ttu-id="e87bf-132">Шаг 3. Определяется пересечение разрешений для атрибутов и элементов.</span><span class="sxs-lookup"><span data-stu-id="e87bf-132">Step 3: The intersection of attribute and member permissions is determined.</span></span>
 <span data-ttu-id="e87bf-133">Если действующие разрешения для атрибутов отличаются от действующих разрешений для элементов, разрешения должны определяться для каждого отдельного значения атрибута.</span><span class="sxs-lookup"><span data-stu-id="e87bf-133">If the effective attribute permissions are different than the effective member permissions, permissions must be determined for each individual attribute value.</span></span> <span data-ttu-id="e87bf-134">Дополнительные сведения см. в разделе [Перекрытие разрешений моделей и элементов (службы основных данных)](../../2014/master-data-services/overlapping-model-and-member-permissions-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="e87bf-134">For more information, see [Overlapping Model and Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-model-and-member-permissions-master-data-services.md).</span></span>

## <a name="permissions-assigned-to-multiple-groups"></a><span data-ttu-id="e87bf-135">Разрешения, назначенные нескольким группам</span><span class="sxs-lookup"><span data-stu-id="e87bf-135">Permissions assigned to multiple groups</span></span>
 <span data-ttu-id="e87bf-136">Если пользователь принадлежит одной или более группам и разрешения назначены как пользователю, так и группам, рабочий процесс определения усложняется.</span><span class="sxs-lookup"><span data-stu-id="e87bf-136">If a user belongs to one or more groups and permissions are assigned to both the user and the groups, the workflow becomes more complex.</span></span>

 <span data-ttu-id="e87bf-137">![mds_conc_security_group_overlap](../../2014/master-data-services/media/mds-conc-security-group-overlap.gif "mds_conc_security_group_overlap")</span><span class="sxs-lookup"><span data-stu-id="e87bf-137">![mds_conc_security_group_overlap](../../2014/master-data-services/media/mds-conc-security-group-overlap.gif "mds_conc_security_group_overlap")</span></span>

 <span data-ttu-id="e87bf-138">В этом случае пересечения разрешений пользователя и группы должны определяться, прежде чем можно будет сравнивать разрешения для объектов модели и элементов иерархии.</span><span class="sxs-lookup"><span data-stu-id="e87bf-138">In this case, overlapping user and group permissions must be resolved before model object and hierarchy member permissions can be compared.</span></span> <span data-ttu-id="e87bf-139">Дополнительные сведения см. в разделе [Перекрытие разрешений пользователей и групп (службы основных данных)](../../2014/master-data-services/overlapping-user-and-group-permissions-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="e87bf-139">For more information, see [Overlapping User and Group Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-user-and-group-permissions-master-data-services.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e87bf-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="e87bf-140">See Also</span></span>
 <span data-ttu-id="e87bf-141">[Перекрывающиеся разрешения пользователя и группы &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-user-and-group-permissions-master-data-services.md) [перекрытие разрешений модели и элемента &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-model-and-member-permissions-master-data-services.md)</span><span class="sxs-lookup"><span data-stu-id="e87bf-141">[Overlapping User and Group Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-user-and-group-permissions-master-data-services.md) [Overlapping Model and Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/overlapping-model-and-member-permissions-master-data-services.md)</span></span>


