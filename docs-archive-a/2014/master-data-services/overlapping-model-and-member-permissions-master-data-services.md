---
title: Перекрытие разрешений моделей и элементов (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- models [Master Data Services], effective permissions
- permissions [Master Data Services], model and member overlaps
- members [Master Data Services], effective permissions
ms.assetid: 9fd7a555-43bf-4796-a8b6-1ca63a291216
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ec5f4019f25a777e4c70433bd9a7e72fca2277e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655796"
---
# <a name="overlapping-model-and-member-permissions-master-data-services"></a><span data-ttu-id="648b1-102">Перекрытие разрешений моделей и элементов (службы основных данных)</span><span class="sxs-lookup"><span data-stu-id="648b1-102">Overlapping Model and Member Permissions (Master Data Services)</span></span>
  <span data-ttu-id="648b1-103">Разрешение для элемента может переопределять разрешение для объекта модели.</span><span class="sxs-lookup"><span data-stu-id="648b1-103">Permission assigned to a member can overlap with permission assigned to a model object.</span></span> <span data-ttu-id="648b1-104">При возникновении перекрытия действует более жесткое разрешение.</span><span class="sxs-lookup"><span data-stu-id="648b1-104">When overlaps occur, the more restrictive permission takes effect.</span></span>  
  
 <span data-ttu-id="648b1-105">Если разрешение элемента отличается от разрешения соответствующего модельного объекта, то применяются следующие правила.</span><span class="sxs-lookup"><span data-stu-id="648b1-105">If a member has permission that is different than its corresponding model object, the following rules apply:</span></span>  
  
-   <span data-ttu-id="648b1-106">**Запретить** переопределяет все остальные разрешения.</span><span class="sxs-lookup"><span data-stu-id="648b1-106">**Deny** overrides all other permissions.</span></span>  
  
-   <span data-ttu-id="648b1-107">Переопределяет **Обновление** **только для чтения** .</span><span class="sxs-lookup"><span data-stu-id="648b1-107">**Read-only** overrides **Update**.</span></span>  
  
 <span data-ttu-id="648b1-108">На следующем рисунке показано, какие разрешения влияют на отдельное значение атрибута, если разрешения для атрибутов отличаются от разрешений для элементов.</span><span class="sxs-lookup"><span data-stu-id="648b1-108">The following image shows which permissions take effect on an individual attribute value when attribute permissions are different than member permissions.</span></span>  
  
 <span data-ttu-id="648b1-109">![mds_conc_security_member_overlap_table](../../2014/master-data-services/media/mds-conc-security-member-overlap-table.gif "mds_conc_security_member_overlap_table")</span><span class="sxs-lookup"><span data-stu-id="648b1-109">![mds_conc_security_member_overlap_table](../../2014/master-data-services/media/mds-conc-security-member-overlap-table.gif "mds_conc_security_member_overlap_table")</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="648b1-110">Пример 1</span><span class="sxs-lookup"><span data-stu-id="648b1-110">Example 1</span></span>  
 <span data-ttu-id="648b1-111">![mds_conc_overlap_model_1](../../2014/master-data-services/media/mds-conc-overlap-model-1.gif "mds_conc_overlap_model_1")</span><span class="sxs-lookup"><span data-stu-id="648b1-111">![mds_conc_overlap_model_1](../../2014/master-data-services/media/mds-conc-overlap-model-1.gif "mds_conc_overlap_model_1")</span></span>  
  
 <span data-ttu-id="648b1-112">На вкладке **Модели** для сущности Product назначено разрешение **Обновление** .</span><span class="sxs-lookup"><span data-stu-id="648b1-112">On the **Models** tab, the Product entity has **Update** permission assigned.</span></span> <span data-ttu-id="648b1-113">Это разрешение наследуют все атрибуты сущности.</span><span class="sxs-lookup"><span data-stu-id="648b1-113">All attributes in the entity inherit that permission.</span></span>  
  
 <span data-ttu-id="648b1-114">На вкладке **Элементы иерархии** узлу подкатегории Mountain Bikes в производной иерархии назначено разрешение **Обновление** .</span><span class="sxs-lookup"><span data-stu-id="648b1-114">On the **Hierarchy Members** tab, the Mountain Bikes subcategory node in a derived hierarchy has **Update** permission assigned.</span></span>  
  
 <span data-ttu-id="648b1-115">Результат: в **обозревателе**пользователь имеет разрешение **Обновление** для всех значений атрибутов всех элементов узла Mountain Bikes.</span><span class="sxs-lookup"><span data-stu-id="648b1-115">Result: In **Explorer**, the user has **Update** permission to all attribute values for all members in the Mountain Bikes node.</span></span> <span data-ttu-id="648b1-116">Все остальные элементы и их атрибуты скрыты.</span><span class="sxs-lookup"><span data-stu-id="648b1-116">All other members and attributes are hidden.</span></span>  
  
 <span data-ttu-id="648b1-117">![mds_conc_overlap_model_example_1](../../2014/master-data-services/media/mds-conc-overlap-model-example-1.gif "mds_conc_overlap_model_example_1")</span><span class="sxs-lookup"><span data-stu-id="648b1-117">![mds_conc_overlap_model_example_1](../../2014/master-data-services/media/mds-conc-overlap-model-example-1.gif "mds_conc_overlap_model_example_1")</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="648b1-118">Пример 2</span><span class="sxs-lookup"><span data-stu-id="648b1-118">Example 2</span></span>  
 <span data-ttu-id="648b1-119">![mds_conc_overlap_model_2](../../2014/master-data-services/media/mds-conc-overlap-model-2.gif "mds_conc_overlap_model_2")</span><span class="sxs-lookup"><span data-stu-id="648b1-119">![mds_conc_overlap_model_2](../../2014/master-data-services/media/mds-conc-overlap-model-2.gif "mds_conc_overlap_model_2")</span></span>  
  
 <span data-ttu-id="648b1-120">На вкладке **Модели** для атрибута Subcategory назначено разрешение **Обновление** .</span><span class="sxs-lookup"><span data-stu-id="648b1-120">On the **Models** tab, the Subcategory attribute has **Update** permission assigned.</span></span>  
  
 <span data-ttu-id="648b1-121">На вкладке **элементы иерархии** узлу Подкатегория горных велосипедов в производной иерархии явным образом назначается разрешение только для **чтения** .</span><span class="sxs-lookup"><span data-stu-id="648b1-121">On the **Hierarchy Members** tab, the Mountain Bikes subcategory node in a derived hierarchy is explicitly assigned **Read-only** permission.</span></span>  
  
 <span data-ttu-id="648b1-122">Результат: в **обозревателе**пользователь имеет разрешение **только на чтение** для значений атрибута Подкатегория для элементов в узле Mountain велосипедов.</span><span class="sxs-lookup"><span data-stu-id="648b1-122">Result: In **Explorer**, the user has **Read-only** permission to the Subcategory attribute values for the members in the Mountain Bikes node.</span></span> <span data-ttu-id="648b1-123">Все остальные элементы и их атрибуты скрыты.</span><span class="sxs-lookup"><span data-stu-id="648b1-123">All other members and attributes are hidden.</span></span>  
  
 <span data-ttu-id="648b1-124">![mds_conc_overlap_model_example_2](../../2014/master-data-services/media/mds-conc-overlap-model-example-2.gif "mds_conc_overlap_model_example_2")</span><span class="sxs-lookup"><span data-stu-id="648b1-124">![mds_conc_overlap_model_example_2](../../2014/master-data-services/media/mds-conc-overlap-model-example-2.gif "mds_conc_overlap_model_example_2")</span></span>  
  
## <a name="example-3"></a><span data-ttu-id="648b1-125">Пример 3</span><span class="sxs-lookup"><span data-stu-id="648b1-125">Example 3</span></span>  
 <span data-ttu-id="648b1-126">![mds_conc_overlap_model_3](../../2014/master-data-services/media/mds-conc-overlap-model-3.gif "mds_conc_overlap_model_3")</span><span class="sxs-lookup"><span data-stu-id="648b1-126">![mds_conc_overlap_model_3](../../2014/master-data-services/media/mds-conc-overlap-model-3.gif "mds_conc_overlap_model_3")</span></span>  
  
 <span data-ttu-id="648b1-127">На вкладке **модели** атрибут Подкатегория имеет разрешение **только чтение** .</span><span class="sxs-lookup"><span data-stu-id="648b1-127">On the **Models** tab, the Subcategory attribute has **Read-only** permission assigned.</span></span>  
  
 <span data-ttu-id="648b1-128">На вкладке **Элементы иерархии** узлу подкатегории Mountain Bikes в порожденной иерархии явно назначено разрешение **Обновление** .</span><span class="sxs-lookup"><span data-stu-id="648b1-128">On the **Hierarchy Members** tab, the Mountain Bikes subcategory in a derived hierarchy is explicitly assigned **Update** permission.</span></span>  
  
 <span data-ttu-id="648b1-129">Результат: в **обозревателе**пользователь имеет разрешение **только на чтение** значений атрибутов.</span><span class="sxs-lookup"><span data-stu-id="648b1-129">Result: In **Explorer**, the user has **Read-only** permission to the attribute values.</span></span> <span data-ttu-id="648b1-130">Все остальные элементы и их атрибуты скрыты.</span><span class="sxs-lookup"><span data-stu-id="648b1-130">All other members and attributes are hidden.</span></span>  
  
 <span data-ttu-id="648b1-131">![mds_conc_overlap_model_example_2](../../2014/master-data-services/media/mds-conc-overlap-model-example-2.gif "mds_conc_overlap_model_example_2")</span><span class="sxs-lookup"><span data-stu-id="648b1-131">![mds_conc_overlap_model_example_2](../../2014/master-data-services/media/mds-conc-overlap-model-example-2.gif "mds_conc_overlap_model_example_2")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="648b1-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="648b1-132">See Also</span></span>  
 <span data-ttu-id="648b1-133">[Как определяются разрешения &#40;Master Data Services&#41;](how-permissions-are-determined-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="648b1-133">[How Permissions Are Determined &#40;Master Data Services&#41;](how-permissions-are-determined-master-data-services.md) </span></span>  
 [<span data-ttu-id="648b1-134">Перекрытие разрешений пользователей и групп (службы основных данных)</span><span class="sxs-lookup"><span data-stu-id="648b1-134">Overlapping User and Group Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/overlapping-user-and-group-permissions-master-data-services.md)  
  
  
