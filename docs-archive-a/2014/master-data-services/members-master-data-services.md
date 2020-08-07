---
title: Элементы (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- leaf members [Master Data Services]
- consolidated members [Master Data Services]
- consolidated members [Master Data Services], about consolidated members
- members [Master Data Services], about members
- leaf members [Master Data Services], about leaf members
- members [Master Data Services]
ms.assetid: 0fda32b9-677d-4ba2-bb28-f76f2383a30f
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 89d2edb21b58575dffc21d9a6470171251889cc0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730817"
---
# <a name="members-master-data-services"></a><span data-ttu-id="92aaa-102">Элементы (службы основных данных)</span><span class="sxs-lookup"><span data-stu-id="92aaa-102">Members (Master Data Services)</span></span>
  <span data-ttu-id="92aaa-103">В [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]элементы являются физическими основными данными.</span><span class="sxs-lookup"><span data-stu-id="92aaa-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], members are the physical master data.</span></span> <span data-ttu-id="92aaa-104">Например, элемент может быть велосипедом «Road-150» в сущности «Product» или конкретным клиентом в сущности «Customer».</span><span class="sxs-lookup"><span data-stu-id="92aaa-104">For example, a member can be a Road-150 bike in a Product entity or a specific customer in a Customer entity.</span></span>

## <a name="how-members-relate-to-other-model-objects"></a><span data-ttu-id="92aaa-105">Связь элементов с другими объектами модели</span><span class="sxs-lookup"><span data-stu-id="92aaa-105">How Members Relate to Other Model Objects</span></span>
 <span data-ttu-id="92aaa-106">Элементы можно представить как строки в таблице.</span><span class="sxs-lookup"><span data-stu-id="92aaa-106">You can think of members as rows in a table.</span></span> <span data-ttu-id="92aaa-107">Связанные элементы содержатся в сущности, а каждый элемент определен значениями атрибутов.</span><span class="sxs-lookup"><span data-stu-id="92aaa-107">Related members are contained in an entity, and each member is defined by attribute values.</span></span>

 <span data-ttu-id="92aaa-108">В этом примере таблица представляет собой сущность, строки в таблице представляют элементы, а столбцы — атрибуты.</span><span class="sxs-lookup"><span data-stu-id="92aaa-108">In this example, the table represents an entity, the rows in the table represent members, and the columns in the table represent attributes.</span></span> <span data-ttu-id="92aaa-109">Каждая ячейка представляет значение атрибута для определенного элемента.</span><span class="sxs-lookup"><span data-stu-id="92aaa-109">Each cell represents an attribute value for a specific member.</span></span>

 <span data-ttu-id="92aaa-110">![Сущность служб Master Data Services, представленная в виде таблицы](../../2014/master-data-services/media/mds-conc-entity-table.gif "Сущность служб Master Data Services, представленная в виде таблицы")</span><span class="sxs-lookup"><span data-stu-id="92aaa-110">![Master Data Services Entity Represented as Table](../../2014/master-data-services/media/mds-conc-entity-table.gif "Master Data Services Entity Represented as Table")</span></span>

## <a name="member-types"></a><span data-ttu-id="92aaa-111">Типы элементов</span><span class="sxs-lookup"><span data-stu-id="92aaa-111">Member Types</span></span>
 <span data-ttu-id="92aaa-112">Существует три типа элементов: конечные элементы, консолидированные элементы и элементы коллекции.</span><span class="sxs-lookup"><span data-stu-id="92aaa-112">There are three types of members: leaf members, consolidated members, and collection members.</span></span>

 <span data-ttu-id="92aaa-113">Конечные элементы являются элементами по умолчанию в сущности.</span><span class="sxs-lookup"><span data-stu-id="92aaa-113">Leaf members are the default members in an entity.</span></span>

-   <span data-ttu-id="92aaa-114">В производных иерархиях единственный тип элементов — конечные элементы.</span><span class="sxs-lookup"><span data-stu-id="92aaa-114">In derived hierarchies, leaf members are the only type of member.</span></span> <span data-ttu-id="92aaa-115">Конечные элементы одной сущности используются как родительские элементы для конечных элементов другой сущности.</span><span class="sxs-lookup"><span data-stu-id="92aaa-115">Leaf members from one entity are used as parents of leaf members from another entity.</span></span>

-   <span data-ttu-id="92aaa-116">В явных иерархиях конечные элементы находятся на низшем уровне и не могут иметь дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="92aaa-116">In explicit hierarchies, leaf members are the lowest level and cannot have children.</span></span>

 <span data-ttu-id="92aaa-117">Консолидированные элементы существуют, только если для сущности допускаются явные иерархии и коллекции.</span><span class="sxs-lookup"><span data-stu-id="92aaa-117">Consolidated members exist only when explicit hierarchies and collections are enabled for the entity.</span></span>

-   <span data-ttu-id="92aaa-118">Производные иерархии не содержат консолидированных элементов.</span><span class="sxs-lookup"><span data-stu-id="92aaa-118">Derived hierarchies do not contain consolidated members.</span></span>

-   <span data-ttu-id="92aaa-119">В явных иерархиях консолидированные элементы могут быть родителями других элементов в иерархии, а также дочерними элементами.</span><span class="sxs-lookup"><span data-stu-id="92aaa-119">In explicit hierarchies, consolidated members can be parents of other members within the hierarchy, or they can be children.</span></span>

## <a name="use-hierarchies-and-collections-to-organize-members"></a><span data-ttu-id="92aaa-120">Использование иерархии и коллекций для организации элементов</span><span class="sxs-lookup"><span data-stu-id="92aaa-120">Use Hierarchies and Collections to Organize Members</span></span>
 <span data-ttu-id="92aaa-121">Иерархии и коллекции можно использовать для группировки элементов для отчетов или анализа.</span><span class="sxs-lookup"><span data-stu-id="92aaa-121">Hierarchies and collections can be used to group members for reporting or analysis.</span></span> <span data-ttu-id="92aaa-122">Дополнительные сведения см. в разделах [Иерархии (службы Master Data Services)](hierarchies-master-data-services.md) и [Коллекции (службы Master Data Services)](../../2014/master-data-services/collections-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="92aaa-122">For more information, see [Hierarchies &#40;Master Data Services&#41;](hierarchies-master-data-services.md) and [Collections &#40;Master Data Services&#41;](../../2014/master-data-services/collections-master-data-services.md).</span></span>

## <a name="member-example"></a><span data-ttu-id="92aaa-123">Пример элемента</span><span class="sxs-lookup"><span data-stu-id="92aaa-123">Member Example</span></span>
 <span data-ttu-id="92aaa-124">В следующем примере каждый элемент состоит из значений атрибутов Name, Code, Subcategory, StandardCost, ListPrice и FilePhoto.</span><span class="sxs-lookup"><span data-stu-id="92aaa-124">In the following example, each member is made up of a Name, Code, Subcategory, StandardCost, ListPrice, and FilePhoto attribute value.</span></span>

 <span data-ttu-id="92aaa-125">![Таблица продукта «Велосипед»](../../2014/master-data-services/media/mds-conc-entity-table-w-data.gif "Таблица продукта «Велосипед»")</span><span class="sxs-lookup"><span data-stu-id="92aaa-125">![Bike Product Entity Table](../../2014/master-data-services/media/mds-conc-entity-table-w-data.gif "Bike Product Entity Table")</span></span>

## <a name="related-tasks"></a><span data-ttu-id="92aaa-126">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="92aaa-126">Related Tasks</span></span>

|<span data-ttu-id="92aaa-127">Описание задачи</span><span class="sxs-lookup"><span data-stu-id="92aaa-127">Task Description</span></span>|<span data-ttu-id="92aaa-128">Раздел</span><span class="sxs-lookup"><span data-stu-id="92aaa-128">Topic</span></span>|
|----------------------|-----------|
|<span data-ttu-id="92aaa-129">Создание нового конечного элемента.</span><span class="sxs-lookup"><span data-stu-id="92aaa-129">Create a new leaf member.</span></span>|[<span data-ttu-id="92aaa-130">Создание конечного элемента (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="92aaa-130">Create a Leaf Member &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-leaf-member-master-data-services.md)|
|<span data-ttu-id="92aaa-131">Создание нового объединенного элемента.</span><span class="sxs-lookup"><span data-stu-id="92aaa-131">Create a new consolidated member.</span></span>|[<span data-ttu-id="92aaa-132">Создание объединенного элемента (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="92aaa-132">Create a Consolidated Member &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-consolidated-member-master-data-services.md)|
|<span data-ttu-id="92aaa-133">Удаление существующего элемента или коллекции.</span><span class="sxs-lookup"><span data-stu-id="92aaa-133">Delete an existing member or collection.</span></span>|[<span data-ttu-id="92aaa-134">Удаление элемента или коллекции (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="92aaa-134">Delete a Member or Collection &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-a-member-or-collection-master-data-services.md)|
|<span data-ttu-id="92aaa-135">Повторная активация удаленного элемента или коллекции.</span><span class="sxs-lookup"><span data-stu-id="92aaa-135">Reactivate a deleted member or collection.</span></span>|[<span data-ttu-id="92aaa-136">Повторная активация элемента или коллекции (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="92aaa-136">Reactivate a Member or Collection &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/reactivate-a-member-or-collection-master-data-services.md)|
|<span data-ttu-id="92aaa-137">Обновление значений атрибутов элемента.</span><span class="sxs-lookup"><span data-stu-id="92aaa-137">Update the attribute values of a member.</span></span>|[<span data-ttu-id="92aaa-138">Изменение типа атрибута (надстройка MDS для Excel)</span><span class="sxs-lookup"><span data-stu-id="92aaa-138">Change the Attribute Type &#40;MDS Add-in for Excel&#41;</span></span>](microsoft-excel-add-in/change-the-attribute-type-mds-add-in-for-excel.md)|
|<span data-ttu-id="92aaa-139">Перемещение элементов в иерархии.</span><span class="sxs-lookup"><span data-stu-id="92aaa-139">Move members within a hierarchy.</span></span>|[<span data-ttu-id="92aaa-140">Перемещение элементов в иерархии &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="92aaa-140">Move Members within a Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/move-members-within-a-hierarchy-master-data-services.md)|

## <a name="related-content"></a><span data-ttu-id="92aaa-141">См. также</span><span class="sxs-lookup"><span data-stu-id="92aaa-141">Related Content</span></span>

-   [<span data-ttu-id="92aaa-142">Обзор Master Data Services</span><span class="sxs-lookup"><span data-stu-id="92aaa-142">Master Data Services Overview</span></span>](master-data-services-overview-mds.md)

-   [<span data-ttu-id="92aaa-143">Сущности (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="92aaa-143">Entities &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/entities-master-data-services.md)

-   [<span data-ttu-id="92aaa-144">Атрибуты (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="92aaa-144">Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/attributes-master-data-services.md)

-   [<span data-ttu-id="92aaa-145">Иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="92aaa-145">Hierarchies &#40;Master Data Services&#41;</span></span>](hierarchies-master-data-services.md)

-   [<span data-ttu-id="92aaa-146">Коллекции (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="92aaa-146">Collections &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/collections-master-data-services.md)

-   [<span data-ttu-id="92aaa-147">Разрешения конечного элемента (службы основных данных)</span><span class="sxs-lookup"><span data-stu-id="92aaa-147">Leaf Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/leaf-permissions-master-data-services.md)

-   [<span data-ttu-id="92aaa-148">Объединенные разрешения &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="92aaa-148">Consolidated Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/consolidated-permissions-master-data-services.md)

-   [<span data-ttu-id="92aaa-149">Операторы фильтров (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="92aaa-149">Filter Operators &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/filter-operators-master-data-services.md)


