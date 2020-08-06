---
title: Группы атрибутов (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attribute groups [Master Data Services]
- attribute groups [Master Data Services], about attribute groups
ms.assetid: 648b3d0b-e15a-45f9-8292-3a54a072e62c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 390b402489799639e66a44992da1e20b0d0c1bbf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664981"
---
# <a name="attribute-groups-master-data-services"></a><span data-ttu-id="07a13-102">Группы атрибутов (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="07a13-102">Attribute Groups (Master Data Services)</span></span>
  <span data-ttu-id="07a13-103">В [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]группы атрибутов помогают организовать атрибуты в сущности.</span><span class="sxs-lookup"><span data-stu-id="07a13-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], attribute groups help organize attributes in an entity.</span></span> <span data-ttu-id="07a13-104">Если сущность имеет множество атрибутов, то использование групп атрибутов улучшает отображение сущности в веб-приложении [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="07a13-104">When an entity has lots of attributes, attribute groups improve the way an entity is displayed in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application.</span></span>  
  
## <a name="how-attribute-groups-change-the-display"></a><span data-ttu-id="07a13-105">Изменение отображения при использовании групп атрибутов</span><span class="sxs-lookup"><span data-stu-id="07a13-105">How Attribute Groups Change the Display</span></span>  
 <span data-ttu-id="07a13-106">Группы атрибутов отображаются как вкладки над сеткой в функциональной области **обозревателя** в веб-приложении [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="07a13-106">Attribute groups are displayed as tabs above the grid in the **Explorer** functional area of [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
 <span data-ttu-id="07a13-107">Если атрибутов у сущности много и эта сущность просматривается в сетке в **Обозревателе**, то для их просмотра нужно прокручивать экран вправо.</span><span class="sxs-lookup"><span data-stu-id="07a13-107">When an entity has a large number of attributes and you view that entity in a grid in **Explorer**, you must scroll to the right to view all of the attributes.</span></span> <span data-ttu-id="07a13-108">Чтобы не нужно было прокручивать экран, можно объединить атрибуты в группы.</span><span class="sxs-lookup"><span data-stu-id="07a13-108">To prevent this scrolling, you can create attribute groups.</span></span>  
  
-   <span data-ttu-id="07a13-109">Группы атрибутов всегда автоматически включают атрибуты «Имя» и «Код».</span><span class="sxs-lookup"><span data-stu-id="07a13-109">Attribute groups always include the Name and Code attributes.</span></span>  
  
-   <span data-ttu-id="07a13-110">Каждый атрибут сущности может принадлежать к нескольким группам.</span><span class="sxs-lookup"><span data-stu-id="07a13-110">Each attribute for an entity can belong to one or more attribute groups.</span></span>  
  
-   <span data-ttu-id="07a13-111">Все атрибуты автоматически включаются во вкладку **Все атрибуты** в **обозревателе**.</span><span class="sxs-lookup"><span data-stu-id="07a13-111">All attributes are automatically included on the **All Attributes** tab in **Explorer**.</span></span>  
  
-   <span data-ttu-id="07a13-112">Нельзя скрыть вкладку **Все атрибуты** .</span><span class="sxs-lookup"><span data-stu-id="07a13-112">There is no way to hide the **All Attributes** tab.</span></span>  
  
 <span data-ttu-id="07a13-113">Управление группами атрибутов осуществляется в функциональной области **Администрирование системы** в веб-приложении [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="07a13-113">Attribute groups are administered in the **System Administration** functional area of [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
## <a name="show-or-hide-attribute-groups"></a><span data-ttu-id="07a13-114">Отображение или скрытие групп атрибутов</span><span class="sxs-lookup"><span data-stu-id="07a13-114">Show or Hide Attribute Groups</span></span>  
 <span data-ttu-id="07a13-115">При создании группы атрибутов она автоматически скрыта от всех пользователей, кроме того, кто ее создал.</span><span class="sxs-lookup"><span data-stu-id="07a13-115">When you create an attribute group, it is automatically hidden from all users except the one who created it.</span></span> <span data-ttu-id="07a13-116">Дополнительные сведения о назначении видимости группе см. в разделе [Превращение группы атрибутов в видимую для пользователей (службы Master Data Services)](make-an-attribute-group-visible-to-users-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="07a13-116">For more information about making the group visible, see [Make an Attribute Group Visible to Users &#40;Master Data Services&#41;](make-an-attribute-group-visible-to-users-master-data-services.md).</span></span>  
  
 <span data-ttu-id="07a13-117">При необходимости скрыть определенный атрибут внутри группы вы можете назначить атрибуту разрешение **Запрещено** .</span><span class="sxs-lookup"><span data-stu-id="07a13-117">If you want to hide a specific attribute within a group, you can assign **Deny** permission to the attribute.</span></span> <span data-ttu-id="07a13-118">Дополнительные сведения см. в разделе [Разрешения конечного элемента (службы основных данных)](../../2014/master-data-services/leaf-permissions-master-data-services.md) или [Объединенные разрешения (службы основных данных)](../../2014/master-data-services/consolidated-permissions-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="07a13-118">For more information, see [Leaf Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/leaf-permissions-master-data-services.md) or [Consolidated Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/consolidated-permissions-master-data-services.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="07a13-119">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="07a13-119">Related Tasks</span></span>  
  
|<span data-ttu-id="07a13-120">Описание задачи</span><span class="sxs-lookup"><span data-stu-id="07a13-120">Task Description</span></span>|<span data-ttu-id="07a13-121">Раздел</span><span class="sxs-lookup"><span data-stu-id="07a13-121">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="07a13-122">Создание новой группы атрибутов и добавление к ней атрибутов.</span><span class="sxs-lookup"><span data-stu-id="07a13-122">Create a new attribute group and add attributes to it.</span></span>|[<span data-ttu-id="07a13-123">Создание группы атрибутов (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="07a13-123">Create an Attribute Group &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-attribute-group-master-data-services.md)|  
|<span data-ttu-id="07a13-124">Превращение группы атрибутов в видимую для пользователей</span><span class="sxs-lookup"><span data-stu-id="07a13-124">Make an attribute group visible to users.</span></span>|[<span data-ttu-id="07a13-125">Превращение группы атрибутов в видимую для пользователей (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="07a13-125">Make an Attribute Group Visible to Users &#40;Master Data Services&#41;</span></span>](make-an-attribute-group-visible-to-users-master-data-services.md)|  
|<span data-ttu-id="07a13-126">Изменение имени существующей группы атрибутов.</span><span class="sxs-lookup"><span data-stu-id="07a13-126">Change the name of an existing attribute group.</span></span>|[<span data-ttu-id="07a13-127">Изменение имени группы атрибутов (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="07a13-127">Change an Attribute Group Name &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/change-an-attribute-group-name-master-data-services.md)|  
|<span data-ttu-id="07a13-128">Удаление существующей группы атрибутов.</span><span class="sxs-lookup"><span data-stu-id="07a13-128">Delete an existing attribute group.</span></span>|[<span data-ttu-id="07a13-129">Удаление группы атрибутов (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="07a13-129">Delete an Attribute Group &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-an-attribute-group-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="07a13-130">См. также</span><span class="sxs-lookup"><span data-stu-id="07a13-130">Related Content</span></span>  
  
-   [<span data-ttu-id="07a13-131">Атрибуты (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="07a13-131">Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/attributes-master-data-services.md)  
  
  
