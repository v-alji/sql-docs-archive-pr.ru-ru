---
title: Атрибуты на основе домена (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- domain-based attributes [Master Data Services], about domain-based attributes
- domain-based attributes [Master Data Services]
- attributes [Master Data Services], domain-based attributes
ms.assetid: df6f33ff-97f6-466c-af74-9780b2247473
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 9182974923848d49ed3e9ecfb58a14949784a2c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669434"
---
# <a name="domain-based-attributes-master-data-services"></a><span data-ttu-id="f1750-102">Атрибуты на основе домена (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="f1750-102">Domain-Based Attributes (Master Data Services)</span></span>
  <span data-ttu-id="f1750-103">В [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]атрибут на основе домена — это атрибут, значения которого заполняются элементами другой сущности.</span><span class="sxs-lookup"><span data-stu-id="f1750-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], a domain-based attribute is an attribute with values that are populated by members from another entity.</span></span> <span data-ttu-id="f1750-104">Атрибут на основе домена можно представить как ограниченный список. Атрибуты на основе домена не позволяют пользователям вводить недопустимые значения атрибутов.</span><span class="sxs-lookup"><span data-stu-id="f1750-104">You can think of a domain-based attribute as a constrained list; domain-based attributes prevent users from entering attribute values that are not valid.</span></span> <span data-ttu-id="f1750-105">Для задания значения атрибута пользователь должен выбрать его из списка.</span><span class="sxs-lookup"><span data-stu-id="f1750-105">To select an attribute value, the user must pick from a list.</span></span>

## <a name="domain-based-attribute-example"></a><span data-ttu-id="f1750-106">Пример атрибута на основе домена</span><span class="sxs-lookup"><span data-stu-id="f1750-106">Domain-Based Attribute Example</span></span>
 <span data-ttu-id="f1750-107">На следующем рисунке сущность Product имеет атрибут на основе домена с именем Subcategory.</span><span class="sxs-lookup"><span data-stu-id="f1750-107">In the following image, the Product entity has a domain-based attribute called Subcategory.</span></span> <span data-ttu-id="f1750-108">Атрибут «Подкатегория» заполняется значениями из сущности «Подкатегория».</span><span class="sxs-lookup"><span data-stu-id="f1750-108">The Subcategory attribute is populated by values from the Subcategory entity.</span></span>

 <span data-ttu-id="f1750-109">Сущность «Подкатегория» имеет атрибут на основе домена с именем «Категория».</span><span class="sxs-lookup"><span data-stu-id="f1750-109">The Subcategory entity has a domain-based attribute called Category.</span></span> <span data-ttu-id="f1750-110">Атрибут «Категория» заполняется значениями из сущности «Категория».</span><span class="sxs-lookup"><span data-stu-id="f1750-110">The Category attribute is populated by values from the Category entity.</span></span>

 <span data-ttu-id="f1750-111">![Атрибуты на основе домена в сущности](../../2014/master-data-services/media/mds-conc-domain-based-attribute-conceptual.gif "Атрибуты на основе домена в сущности")</span><span class="sxs-lookup"><span data-stu-id="f1750-111">![Domain-Based Attributes in an Entity](../../2014/master-data-services/media/mds-conc-domain-based-attribute-conceptual.gif "Domain-Based Attributes in an Entity")</span></span>

## <a name="use-same-entity-for-multiple-domain-based-attributes"></a><span data-ttu-id="f1750-112">Использование одной и той же сущности для нескольких атрибутов на основе домена</span><span class="sxs-lookup"><span data-stu-id="f1750-112">Use Same Entity for Multiple Domain-Based Attributes</span></span>
 <span data-ttu-id="f1750-113">Одну и ту же сущность можно использовать в качестве атрибута на основе домена для нескольких других сущностей.</span><span class="sxs-lookup"><span data-stu-id="f1750-113">You can use the same entity as a domain-based attribute of multiple entities.</span></span> <span data-ttu-id="f1750-114">Например, можно создать сущность "ИндикаторДаНет" со следующими элементами: "Да", "Нет" и "Может быть".</span><span class="sxs-lookup"><span data-stu-id="f1750-114">For example, you can create an entity called YesNoIndicator with the members: Yes, No, and Maybe.</span></span> <span data-ttu-id="f1750-115">Можно создать атрибут «ВНаличии» на основе домена и использовать сущность «ИндикаторДаНет» как источник.</span><span class="sxs-lookup"><span data-stu-id="f1750-115">You can create a domain-based attribute named InStock and use the YesNoIndicator entity as the source.</span></span> <span data-ttu-id="f1750-116">Также можно создать другой атрибут на основе домена под названием Approved и использовать сущность YesNoIndicator в качестве источника.</span><span class="sxs-lookup"><span data-stu-id="f1750-116">You can also create another domain-based attribute named Approved and use the YesNoIndicator entity as a source.</span></span> <span data-ttu-id="f1750-117">Каждый раз, когда пользователи должны выбирать из списка членов сущности «ИндикаторДаНет», можно использовать сущность как атрибут на основе домена.</span><span class="sxs-lookup"><span data-stu-id="f1750-117">Any time you want users to choose from a list of the YesNoIndicator entity's members, you can use the entity as a domain-based attribute.</span></span>

## <a name="domain-based-attributes-form-derived-hierarchies"></a><span data-ttu-id="f1750-118">Атрибуты на основе домена формируют производные иерархии</span><span class="sxs-lookup"><span data-stu-id="f1750-118">Domain-Based Attributes Form Derived Hierarchies</span></span>
 <span data-ttu-id="f1750-119">Связи между атрибутами на основе домена служат основой для производных иерархий.</span><span class="sxs-lookup"><span data-stu-id="f1750-119">Domain-based attribute relationships are the basis for derived hierarchies.</span></span> <span data-ttu-id="f1750-120">Дополнительные сведения см. в разделе [Производные иерархии (службы Master Data Services)](derived-hierarchies-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="f1750-120">For more information, see [Derived Hierarchies &#40;Master Data Services&#41;](derived-hierarchies-master-data-services.md).</span></span>

## <a name="related-tasks"></a><span data-ttu-id="f1750-121">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="f1750-121">Related Tasks</span></span>

|<span data-ttu-id="f1750-122">Описание задачи</span><span class="sxs-lookup"><span data-stu-id="f1750-122">Task Description</span></span>|<span data-ttu-id="f1750-123">Раздел</span><span class="sxs-lookup"><span data-stu-id="f1750-123">Topic</span></span>|
|----------------------|-----------|
|<span data-ttu-id="f1750-124">Создание нового атрибута на основе домена, источником для которого является существующая сущность.</span><span class="sxs-lookup"><span data-stu-id="f1750-124">Create a new domain-based attribute that is sourced from an existing entity.</span></span>|[<span data-ttu-id="f1750-125">Создание атрибута на основе домена (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="f1750-125">Create a Domain-Based Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md)|
|<span data-ttu-id="f1750-126">Создание новой сущности.</span><span class="sxs-lookup"><span data-stu-id="f1750-126">Create a new entity.</span></span>|[<span data-ttu-id="f1750-127">Создание сущности (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="f1750-127">Create an Entity &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-entity-master-data-services.md)|

## <a name="related-content"></a><span data-ttu-id="f1750-128">См. также</span><span class="sxs-lookup"><span data-stu-id="f1750-128">Related Content</span></span>

-   [<span data-ttu-id="f1750-129">Производные иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="f1750-129">Derived Hierarchies &#40;Master Data Services&#41;</span></span>](derived-hierarchies-master-data-services.md)

-   [<span data-ttu-id="f1750-130">Атрибуты (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="f1750-130">Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/attributes-master-data-services.md)

-   [<span data-ttu-id="f1750-131">Сущности (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="f1750-131">Entities &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/entities-master-data-services.md)


