---
title: Разрешения конечного элемента (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attribute groups [Master Data Services], permissions
- members [Master Data Services], leaf member permissions
- permissions [Master Data Services], leaf members
- leaf members [Master Data Services], attribute permissions
- attributes [Master Data Services], leaf member attribute permissions
ms.assetid: bde16e8c-bcd4-4041-8130-55c5450e5f72
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 794e1d138b91e896b8df16765ae8984c6e60aca7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738462"
---
# <a name="leaf-permissions-master-data-services"></a><span data-ttu-id="799a5-102">Разрешения конечного элемента (службы основных данных)</span><span class="sxs-lookup"><span data-stu-id="799a5-102">Leaf Permissions (Master Data Services)</span></span>
  <span data-ttu-id="799a5-103">Разрешения конечного элемента применяются к значениям атрибутов для всех конечных элементов сущности.</span><span class="sxs-lookup"><span data-stu-id="799a5-103">Leaf permissions apply to the attribute values for all leaf members of an entity.</span></span>  
  
 <span data-ttu-id="799a5-104">Для сущностей, у которых нет явных иерархий, назначение разрешения **Конечный** равнозначно назначению разрешения сущности.</span><span class="sxs-lookup"><span data-stu-id="799a5-104">For entities without explicit hierarchies enabled, assigning permission to **Leaf** is the same as assigning permission to the entity.</span></span>  
  
 <span data-ttu-id="799a5-105">**Примечания.**</span><span class="sxs-lookup"><span data-stu-id="799a5-105">**Notes:**</span></span>  
  
-   <span data-ttu-id="799a5-106">Разрешения конечного элемента применяются только к функциональной области **Обозреватель** пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="799a5-106">Leaf permissions apply to the **Explorer** functional area of the user interface only.</span></span>  
  
-   <span data-ttu-id="799a5-107">Разрешения, назначенные для атрибутов **Имя** и **Код** , не применяются.</span><span class="sxs-lookup"><span data-stu-id="799a5-107">Permissions assigned to **Name** and **Code** attributes are not enforced.</span></span>  
  
|<span data-ttu-id="799a5-108">Разрешение</span><span class="sxs-lookup"><span data-stu-id="799a5-108">Permission</span></span>|<span data-ttu-id="799a5-109">Описание</span><span class="sxs-lookup"><span data-stu-id="799a5-109">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="799a5-110">**Только для чтения**</span><span class="sxs-lookup"><span data-stu-id="799a5-110">**Read-only**</span></span>|<span data-ttu-id="799a5-111">Конечные элементы отображаются, но пользователь не может добавлять, удалять или изменять их.</span><span class="sxs-lookup"><span data-stu-id="799a5-111">Leaf members are displayed but the user cannot add, remove, or change them.</span></span><br /><br /> <span data-ttu-id="799a5-112">Если имеются консолидированные элементы, имена и коды отображаются, но пользователь не может добавлять, удалять или изменять их.</span><span class="sxs-lookup"><span data-stu-id="799a5-112">If consolidated members exist, the names and codes are displayed but the user cannot add, remove, or change them.</span></span>|  
|<span data-ttu-id="799a5-113">**Обновление**</span><span class="sxs-lookup"><span data-stu-id="799a5-113">**Update**</span></span>|<span data-ttu-id="799a5-114">Конечные элементы отображаются, и пользователь может добавлять, удалять и изменять их.</span><span class="sxs-lookup"><span data-stu-id="799a5-114">Leaf members are displayed and the user can add, remove, and change them.</span></span><br /><br /> <span data-ttu-id="799a5-115">Если имеются консолидированные элементы, имена и коды отображаются, но пользователь не может добавлять, удалять или изменять их.</span><span class="sxs-lookup"><span data-stu-id="799a5-115">If consolidated members exist, the names and codes are displayed but the user cannot add, remove, or change them.</span></span>|  
|<span data-ttu-id="799a5-116">**Запретить**</span><span class="sxs-lookup"><span data-stu-id="799a5-116">**Deny**</span></span>|<span data-ttu-id="799a5-117">Конечные элементы для сущности не отображаются.</span><span class="sxs-lookup"><span data-stu-id="799a5-117">Leaf members for the entity are not displayed.</span></span>|  
  
## <a name="attribute-permissions"></a><span data-ttu-id="799a5-118">Разрешения атрибута</span><span class="sxs-lookup"><span data-stu-id="799a5-118">Attribute Permissions</span></span>  
 <span data-ttu-id="799a5-119">Разрешения атрибута применимы только к значениям атрибута указанной сущности.</span><span class="sxs-lookup"><span data-stu-id="799a5-119">Attribute permissions apply to the attribute's values for the specific entity.</span></span> <span data-ttu-id="799a5-120">Пользователи с разрешениями только для атрибутов не могут добавлять или удалять элементы.</span><span class="sxs-lookup"><span data-stu-id="799a5-120">Users with attribute permissions only cannot add or remove members.</span></span>  
  
|<span data-ttu-id="799a5-121">Разрешение</span><span class="sxs-lookup"><span data-stu-id="799a5-121">Permission</span></span>|<span data-ttu-id="799a5-122">Описание</span><span class="sxs-lookup"><span data-stu-id="799a5-122">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="799a5-123">**Только для чтения**</span><span class="sxs-lookup"><span data-stu-id="799a5-123">**Read-only**</span></span>|<span data-ttu-id="799a5-124">Атрибут отображается, но пользователь не может изменить его значений.</span><span class="sxs-lookup"><span data-stu-id="799a5-124">The attribute is displayed but the user cannot change attribute values.</span></span>|  
|<span data-ttu-id="799a5-125">**Обновление**</span><span class="sxs-lookup"><span data-stu-id="799a5-125">**Update**</span></span>|<span data-ttu-id="799a5-126">Атрибут отображается, и пользователь может изменить его значения.</span><span class="sxs-lookup"><span data-stu-id="799a5-126">The attribute is displayed and the user can change attribute values.</span></span>|  
|<span data-ttu-id="799a5-127">**Запретить**</span><span class="sxs-lookup"><span data-stu-id="799a5-127">**Deny**</span></span>|<span data-ttu-id="799a5-128">Атрибут не отображается.</span><span class="sxs-lookup"><span data-stu-id="799a5-128">The attribute is not displayed.</span></span><br /><br /> <span data-ttu-id="799a5-129">Примечание. Нельзя явно запретить доступ к атрибутам "Имя" и "Код".</span><span class="sxs-lookup"><span data-stu-id="799a5-129">Note: You cannot explicitly deny access to Name and Code attributes.</span></span>|  
  
### <a name="example"></a><span data-ttu-id="799a5-130">Пример</span><span class="sxs-lookup"><span data-stu-id="799a5-130">Example</span></span>  
 <span data-ttu-id="799a5-131">Сущности "Продукт" назначьте разрешение **Обновление** для атрибута Subcategory.</span><span class="sxs-lookup"><span data-stu-id="799a5-131">For the Product entity, assign **Update** permission to Subcategory attribute.</span></span> <span data-ttu-id="799a5-132">Отмените разрешения для всех остальных атрибутов.</span><span class="sxs-lookup"><span data-stu-id="799a5-132">Deny permission to all other attributes.</span></span>  
  
|<span data-ttu-id="799a5-133">Имя</span><span class="sxs-lookup"><span data-stu-id="799a5-133">Name</span></span>|<span data-ttu-id="799a5-134">Код</span><span class="sxs-lookup"><span data-stu-id="799a5-134">Code</span></span>|<span data-ttu-id="799a5-135">Подкатегория (Обновление)</span><span class="sxs-lookup"><span data-stu-id="799a5-135">Subcategory (Update)</span></span>|  
|----------|----------|----------------------------|  
|<span data-ttu-id="799a5-136">Mountain-100</span><span class="sxs-lookup"><span data-stu-id="799a5-136">Mountain-100</span></span>|<span data-ttu-id="799a5-137">BK-M101</span><span class="sxs-lookup"><span data-stu-id="799a5-137">BK-M101</span></span>|<span data-ttu-id="799a5-138">{5} Mountain Bikes</span><span class="sxs-lookup"><span data-stu-id="799a5-138">{5} Mountain Bikes</span></span>|  
|<span data-ttu-id="799a5-139">Mountain-100</span><span class="sxs-lookup"><span data-stu-id="799a5-139">Mountain-100</span></span>|<span data-ttu-id="799a5-140">BK-M201</span><span class="sxs-lookup"><span data-stu-id="799a5-140">BK-M201</span></span>|<span data-ttu-id="799a5-141">{5} Mountain Bikes</span><span class="sxs-lookup"><span data-stu-id="799a5-141">{5} Mountain Bikes</span></span>|  
  
 <span data-ttu-id="799a5-142">В **обозревателе**можно обновить любое значение атрибута в столбце "Subcategory".</span><span class="sxs-lookup"><span data-stu-id="799a5-142">In **Explorer**, you can update any attribute value in the Subcategory column.</span></span> <span data-ttu-id="799a5-143">Если у пользователя нет разрешения для атрибута, атрибут не отображается.</span><span class="sxs-lookup"><span data-stu-id="799a5-143">If you do not have permission to an attribute, the attribute is not displayed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="799a5-144">В этом примере «Подкатегория» является доменным атрибутом на основе сущности SubcategoryList.</span><span class="sxs-lookup"><span data-stu-id="799a5-144">In this example, Subcategory is a domain-based attribute, based on the SubcategoryList entity.</span></span> <span data-ttu-id="799a5-145">Можно выбрать другую подкатегорию для Mountain-100, но нельзя добавлять элементы или удалять элементы из сущности SubcategoryList.</span><span class="sxs-lookup"><span data-stu-id="799a5-145">You can select a different subcategory for Mountain-100 but you cannot add members to or delete members from the SubcategoryList entity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="799a5-146">См. также:</span><span class="sxs-lookup"><span data-stu-id="799a5-146">See Also</span></span>  
 <span data-ttu-id="799a5-147">[Назначение разрешений объекта модели &#40;Master Data Services&#41;](assign-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="799a5-147">[Assign Model Object Permissions &#40;Master Data Services&#41;](assign-model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="799a5-148">[Объединенные разрешения &#40;Master Data Services&#41;](../../2014/master-data-services/consolidated-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="799a5-148">[Consolidated Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/consolidated-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="799a5-149">[Разрешения объекта модели &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="799a5-149">[Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="799a5-150">[Master Data Services &#40;членов&#41;](../../2014/master-data-services/members-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="799a5-150">[Members &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) </span></span>  
 [<span data-ttu-id="799a5-151">Атрибуты (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="799a5-151">Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/attributes-master-data-services.md)  
  
  
