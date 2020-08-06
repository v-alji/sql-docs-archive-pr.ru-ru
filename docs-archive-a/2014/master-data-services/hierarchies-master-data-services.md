---
title: Иерархии (Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- hierarchies [Master Data Services]
- hierarchies [Master Data Services], about hierarchies
ms.assetid: 70dbb1fc-ead7-45be-9552-a45e3ccd8d21
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 126a01c03134c6859426c09fda398408694795f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665401"
---
# <a name="hierarchies-master-data-services"></a><span data-ttu-id="0280b-102">Иерархии (службы основных данных)</span><span class="sxs-lookup"><span data-stu-id="0280b-102">Hierarchies (Master Data Services)</span></span>
  <span data-ttu-id="0280b-103">Иерархия в [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]— древовидная структура, которую можно использовать:</span><span class="sxs-lookup"><span data-stu-id="0280b-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], a hierarchy is a tree structure that you can use to:</span></span>

-   <span data-ttu-id="0280b-104">для группировки схожих элементов с целью систематизации;</span><span class="sxs-lookup"><span data-stu-id="0280b-104">Group similar members for organizational purposes.</span></span>

-   <span data-ttu-id="0280b-105">объединения и сведения элементов для отчетов или анализа.</span><span class="sxs-lookup"><span data-stu-id="0280b-105">Consolidate and summarize members for reporting and analysis.</span></span>

## <a name="what-hierarchies-contain"></a><span data-ttu-id="0280b-106">Что содержится в иерархиях</span><span class="sxs-lookup"><span data-stu-id="0280b-106">What Hierarchies Contain</span></span>
 <span data-ttu-id="0280b-107">Каждая иерархия содержит элементы из одной или нескольких сущностей.</span><span class="sxs-lookup"><span data-stu-id="0280b-107">Each hierarchy contains members from one or more entities.</span></span> <span data-ttu-id="0280b-108">При добавлении, изменении или удалении элемента все иерархии обновляются.</span><span class="sxs-lookup"><span data-stu-id="0280b-108">When a member is added, changed, or deleted, all hierarchies are updated.</span></span> <span data-ttu-id="0280b-109">Это гарантирует, что данные будут точными во всех иерархиях.</span><span class="sxs-lookup"><span data-stu-id="0280b-109">This ensures that the data is accurate in all hierarchies.</span></span> <span data-ttu-id="0280b-110">Иерархии также гарантируют, что каждый элемент будет учитываться ровно один раз.</span><span class="sxs-lookup"><span data-stu-id="0280b-110">Hierarchies also help ensure that each member is counted once and only once.</span></span>

 <span data-ttu-id="0280b-111">Если необходимо создать группирование подмножества элементов, рассмотрите возможность использования коллекции.</span><span class="sxs-lookup"><span data-stu-id="0280b-111">If you want to create a grouping of a subset of members, consider using a collection.</span></span> <span data-ttu-id="0280b-112">Дополнительные сведения см. в разделе [Коллекции (службы Master Data Services)](collections-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="0280b-112">For more information, see [Collections &#40;Master Data Services&#41;](collections-master-data-services.md).</span></span>

## <a name="kinds-of-hierarchies"></a><span data-ttu-id="0280b-113">Виды иерархий</span><span class="sxs-lookup"><span data-stu-id="0280b-113">Kinds of Hierarchies</span></span>
 <span data-ttu-id="0280b-114">Можно создавать разные иерархии для просмотра и систематизации элементов разными способами.</span><span class="sxs-lookup"><span data-stu-id="0280b-114">You can create multiple hierarchies to view and organize your members in different ways.</span></span> <span data-ttu-id="0280b-115">Можно создавать:</span><span class="sxs-lookup"><span data-stu-id="0280b-115">You can create:</span></span>

-   <span data-ttu-id="0280b-116">Неоднородные иерархии из единой сущности, которые называются явными иерархиями.</span><span class="sxs-lookup"><span data-stu-id="0280b-116">Ragged hierarchies from a single entity, which are called explicit hierarchies.</span></span> <span data-ttu-id="0280b-117">Дополнительные сведения см. в разделе [Явные иерархии (службы Master Data Services)](../../2014/master-data-services/explicit-hierarchies-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="0280b-117">For more information, see [Explicit Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md).</span></span>

-   <span data-ttu-id="0280b-118">Иерархии на основе уровней, состоящие из многих сущностей и основанные на существующих связях между сущностями и их атрибутами, которые называются производными иерархиями.</span><span class="sxs-lookup"><span data-stu-id="0280b-118">Level-based hierarchies from multiple entities, based on the existing relationships between entities and their attributes, which are called derived hierarchies.</span></span> <span data-ttu-id="0280b-119">Дополнительные сведения см. в разделе [Производные иерархии (службы Master Data Services)](../../2014/master-data-services/derived-hierarchies-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="0280b-119">For more information, see [Derived Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-master-data-services.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="0280b-120">Все элементы в иерархии должны быть в одной модели.</span><span class="sxs-lookup"><span data-stu-id="0280b-120">All members in a hierarchy must be within the same model.</span></span>

## <a name="hierarchies-are-not-taxonomies"></a><span data-ttu-id="0280b-121">Иерархии не являются классификациями</span><span class="sxs-lookup"><span data-stu-id="0280b-121">Hierarchies Are Not Taxonomies</span></span>
 <span data-ttu-id="0280b-122">Иерархия отличается от классификации.</span><span class="sxs-lookup"><span data-stu-id="0280b-122">A hierarchy is different from a taxonomy.</span></span> <span data-ttu-id="0280b-123">В классификации элементы упорядочены в соответствии с несколькими атрибутами одновременно, а в иерархии — только по одному атрибуту.</span><span class="sxs-lookup"><span data-stu-id="0280b-123">A taxonomy organizes members by multiple attributes at the same time, while a hierarchy organizes members by one attribute at a time.</span></span> <span data-ttu-id="0280b-124">Классификации может включать один элемент несколько раз, а иерархия имеет только одно вхождение элемента.</span><span class="sxs-lookup"><span data-stu-id="0280b-124">A taxonomy can include the same member multiple times, while a hierarchy includes a member only once.</span></span>

 <span data-ttu-id="0280b-125">Например, один велосипед может быть упомянут в классификации дважды: один раз, потому что его цвет красный, и один раз, потому что его размер равен 38.</span><span class="sxs-lookup"><span data-stu-id="0280b-125">For example, the same bike can be included in a taxonomy twice: once because it's red, and once because it's a size 38.</span></span> <span data-ttu-id="0280b-126">В иерархии велосипед включен только один раз, поэтому нужно определить, в соответствии с чем он будет отображаться: с цветом или размером.</span><span class="sxs-lookup"><span data-stu-id="0280b-126">In a hierarchy, the bike is included only once, so you must decide whether to show it in relation to its color or its size.</span></span>

## <a name="hierarchy-example"></a><span data-ttu-id="0280b-127">Пример иерархии</span><span class="sxs-lookup"><span data-stu-id="0280b-127">Hierarchy Example</span></span>
 <span data-ttu-id="0280b-128">В следующем примере в иерархии элементы продуктов группируются по элементам подкатегории.</span><span class="sxs-lookup"><span data-stu-id="0280b-128">In the following example, product members are grouped by subcategory members.</span></span>

 <span data-ttu-id="0280b-129">![Пример иерархии, сгруппированной по подкатегории](../../2014/master-data-services/media/mds-conc-hierarchy.gif "Пример иерархии, сгруппированной по подкатегории")</span><span class="sxs-lookup"><span data-stu-id="0280b-129">![Hierarchy Grouped by Subcategory Example](../../2014/master-data-services/media/mds-conc-hierarchy.gif "Hierarchy Grouped by Subcategory Example")</span></span>

## <a name="related-tasks"></a><span data-ttu-id="0280b-130">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="0280b-130">Related Tasks</span></span>

|<span data-ttu-id="0280b-131">Описание задачи</span><span class="sxs-lookup"><span data-stu-id="0280b-131">Task Description</span></span>|<span data-ttu-id="0280b-132">Раздел</span><span class="sxs-lookup"><span data-stu-id="0280b-132">Topic</span></span>|
|----------------------|-----------|
|<span data-ttu-id="0280b-133">Включение сущности для явных иерархий и коллекций.</span><span class="sxs-lookup"><span data-stu-id="0280b-133">Enable an entity for explicit hierarchies and collections.</span></span>|[<span data-ttu-id="0280b-134">Включение сущности для явных иерархий и коллекций &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0280b-134">Enable an Entity for Explicit Hierarchies and Collections &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md)|
|<span data-ttu-id="0280b-135">Создание явной иерархии.</span><span class="sxs-lookup"><span data-stu-id="0280b-135">Create a explicit hierarchy.</span></span>|[<span data-ttu-id="0280b-136">Создание явной иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="0280b-136">Create an Explicit Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md)|
|<span data-ttu-id="0280b-137">Создание производной иерархии.</span><span class="sxs-lookup"><span data-stu-id="0280b-137">Create a derived hierarchy.</span></span>|[<span data-ttu-id="0280b-138">Создание производной иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="0280b-138">Create a Derived Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-derived-hierarchy-master-data-services.md)|
|<span data-ttu-id="0280b-139">Скрытие или удаление уровней в существующей производной иерархии.</span><span class="sxs-lookup"><span data-stu-id="0280b-139">Hide or delete levels in an existing derived hierarchy.</span></span>|[<span data-ttu-id="0280b-140">Скрытие или удаление уровней в производной иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="0280b-140">Hide or Delete Levels in a Derived Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/hide-or-delete-levels-in-a-derived-hierarchy-master-data-services.md)|

## <a name="related-content"></a><span data-ttu-id="0280b-141">См. также</span><span class="sxs-lookup"><span data-stu-id="0280b-141">Related Content</span></span>

-   [<span data-ttu-id="0280b-142">Явные иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="0280b-142">Explicit Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/explicit-hierarchies-master-data-services.md)

-   [<span data-ttu-id="0280b-143">Производные иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="0280b-143">Derived Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/derived-hierarchies-master-data-services.md)

-   [<span data-ttu-id="0280b-144">Рекурсивные иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="0280b-144">Recursive Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/recursive-hierarchies-master-data-services.md)

-   [<span data-ttu-id="0280b-145">Производные иерархии с явными ограничениями (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="0280b-145">Derived Hierarchies with Explicit Caps &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/derived-hierarchies-with-explicit-caps-master-data-services.md)

-   [<span data-ttu-id="0280b-146">Коллекции (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="0280b-146">Collections &#40;Master Data Services&#41;</span></span>](collections-master-data-services.md)


