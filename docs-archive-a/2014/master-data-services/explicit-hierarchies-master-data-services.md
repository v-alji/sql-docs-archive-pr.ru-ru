---
title: Явные иерархии (Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- explicit hierarchies, about explicit hierarchies
- hierarchies [Master Data Services], explicit hierarchies
- explicit hierarchies
ms.assetid: e6f44e37-e1f0-4c38-a816-1935a856d5a4
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: f37f341dc2c003683e696f2767a6b644047d5a0a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731834"
---
# <a name="explicit-hierarchies-master-data-services"></a><span data-ttu-id="e6416-102">Явные иерархии (службы основных данных)</span><span class="sxs-lookup"><span data-stu-id="e6416-102">Explicit Hierarchies (Master Data Services)</span></span>
  <span data-ttu-id="e6416-103">В явных иерархиях в [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]элементы из одной сущности упорядочиваются любым заданным способом.</span><span class="sxs-lookup"><span data-stu-id="e6416-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], an explicit hierarchy organizes members from a single entity in any way you specify.</span></span> <span data-ttu-id="e6416-104">Структура может быть неоднородной, причем, в отличие от производных иерархий, явные иерархии не основываются на связях, основанных на доменах атрибутов.</span><span class="sxs-lookup"><span data-stu-id="e6416-104">The structure can be ragged and unlike derived hierarchies, explicit hierarchies are not based on domain-based attribute relationships.</span></span>

## <a name="consolidated-members-group-other-members"></a><span data-ttu-id="e6416-105">Другие элементы группы консолидированных элементов</span><span class="sxs-lookup"><span data-stu-id="e6416-105">Consolidated Members Group Other Members</span></span>
 <span data-ttu-id="e6416-106">Явная иерархия использует консолидированные элементы, созданные с целью группирования других элементов.</span><span class="sxs-lookup"><span data-stu-id="e6416-106">An explicit hierarchy uses consolidated members that you create for the purpose of grouping other members.</span></span> <span data-ttu-id="e6416-107">Эти консолидированные элементы могут в любой момент времени принадлежать только одной явной иерархии.</span><span class="sxs-lookup"><span data-stu-id="e6416-107">These consolidated members can belong to only one explicit hierarchy at a time.</span></span> <span data-ttu-id="e6416-108">Явная иерархия также включает все конечные элементы связанной с ней сущности.</span><span class="sxs-lookup"><span data-stu-id="e6416-108">An explicit hierarchy also includes all of the leaf members from the associated entity.</span></span>

 <span data-ttu-id="e6416-109">Явная иерархия может быть неоднородной, то есть одновременно заканчиваться на нескольких разных уровнях.</span><span class="sxs-lookup"><span data-stu-id="e6416-109">An explicit hierarchy can be ragged, which means that the hierarchy can end at different levels simultaneously.</span></span> <span data-ttu-id="e6416-110">У каждого объединенного элемента может быть неограниченное количество подчиненных объединенных и конечных элементов, в том числе и ни одного.</span><span class="sxs-lookup"><span data-stu-id="e6416-110">Each consolidated member can have an unlimited number of consolidated and leaf members underneath, or can have none.</span></span> <span data-ttu-id="e6416-111">Конечный элемент может принадлежать как к одному консолидированному элементу, так и к нескольким уровням консолидированных элементов.</span><span class="sxs-lookup"><span data-stu-id="e6416-111">The leaf members can be under a single consolidated member or under multiple levels of consolidated members.</span></span>

> [!NOTE]
>  <span data-ttu-id="e6416-112">Перед созданием явной иерархии для сущности необходимо разрешить использование явных иерархий.</span><span class="sxs-lookup"><span data-stu-id="e6416-112">Before you can create an explicit hierarchy, the entity must be enabled for explicit hierarchies.</span></span> <span data-ttu-id="e6416-113">Дополнительные сведения см. в разделе [Включение сущности для явных иерархий и коллекций &#40;Master Data Services&#41;](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="e6416-113">For more information, see [Enable an Entity for Explicit Hierarchies and Collections &#40;Master Data Services&#41;](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span></span>

## <a name="types-of-explicit-hierarchies"></a><span data-ttu-id="e6416-114">Типы явных иерархий</span><span class="sxs-lookup"><span data-stu-id="e6416-114">Types of Explicit Hierarchies</span></span>
 <span data-ttu-id="e6416-115">Существует два типа явных иерархий: обязательные и необязательные.</span><span class="sxs-lookup"><span data-stu-id="e6416-115">There are two types of explicit hierarchies: mandatory and non-mandatory.</span></span>

### <a name="mandatory-explicit-hierarchy"></a><span data-ttu-id="e6416-116">Обязательная явная иерархия</span><span class="sxs-lookup"><span data-stu-id="e6416-116">Mandatory Explicit Hierarchy</span></span>
 <span data-ttu-id="e6416-117">Обязательная явная иерархия представляет собой иерархию, в которой все конечные элементы должны входить в дерево иерархии.</span><span class="sxs-lookup"><span data-stu-id="e6416-117">A mandatory explicit hierarchy is a hierarchy in which all leaf members must be included in the hierarchy tree.</span></span> <span data-ttu-id="e6416-118">По умолчанию все элементы включены в корень дерева иерархии.</span><span class="sxs-lookup"><span data-stu-id="e6416-118">By default, all members are included at the root of the tree.</span></span> <span data-ttu-id="e6416-119">Но их можно переметить так, как необходимо.</span><span class="sxs-lookup"><span data-stu-id="e6416-119">You can rearrange the members as needed.</span></span>

### <a name="non-mandatory-explicit-hierarchy"></a><span data-ttu-id="e6416-120">Необязательная явная иерархия</span><span class="sxs-lookup"><span data-stu-id="e6416-120">Non-Mandatory Explicit Hierarchy</span></span>
 <span data-ttu-id="e6416-121">Необязательная явная иерархия представляет собой иерархию, в которой все конечные элементы входят в созданный системой узел **Неиспользованные** .</span><span class="sxs-lookup"><span data-stu-id="e6416-121">A non-mandatory explicit hierarchy is a hierarchy in which all leaf members are in a system-created **Unused** node.</span></span> <span data-ttu-id="e6416-122">Можно перемещать элементы из этого узла так, как необходимо.</span><span class="sxs-lookup"><span data-stu-id="e6416-122">You can move members out of this node as you need them.</span></span> <span data-ttu-id="e6416-123">Часть элементов может оставаться в узле **Неиспользованные** .</span><span class="sxs-lookup"><span data-stu-id="e6416-123">The rest of the members can remain in the **Unused** node.</span></span>

 <span data-ttu-id="e6416-124">При использовании необязательных явных иерархий необходимо учитывать, что отчеты или результаты анализа для них будут отличаться от отчетов или результатов анализа для обязательных иерархий.</span><span class="sxs-lookup"><span data-stu-id="e6416-124">When you use non-mandatory explicit hierarchies, any reporting or analysis done on the hierarchy may not match reporting or analysis done on mandatory hierarchies.</span></span>

## <a name="rules"></a><span data-ttu-id="e6416-125">Правила</span><span class="sxs-lookup"><span data-stu-id="e6416-125">Rules</span></span>
 <span data-ttu-id="e6416-126">Следующие правила распространяются на явные иерархии (обязательные и необязательные).</span><span class="sxs-lookup"><span data-stu-id="e6416-126">The following rules apply to explicit hierarchies (both mandatory and non-mandatory).</span></span>

-   <span data-ttu-id="e6416-127">Каждый конечный элемент может быть включен в иерархию только один раз.</span><span class="sxs-lookup"><span data-stu-id="e6416-127">Each leaf member can be included in the hierarchy only once.</span></span>

-   <span data-ttu-id="e6416-128">Все консолидированные элементы должны входить в иерархию.</span><span class="sxs-lookup"><span data-stu-id="e6416-128">All consolidated members must be included in a hierarchy.</span></span>

-   <span data-ttu-id="e6416-129">Консолидированные элементы не могут входить одновременно в несколько явных иерархий.</span><span class="sxs-lookup"><span data-stu-id="e6416-129">Consolidated members cannot be in more than one explicit hierarchy.</span></span>

-   <span data-ttu-id="e6416-130">Консолидированные элементы в дереве иерархии не должны содержать конечные элементы более низкого уровня.</span><span class="sxs-lookup"><span data-stu-id="e6416-130">Consolidated members in the hierarchy tree do not have to contain leaf members underneath them.</span></span>

-   <span data-ttu-id="e6416-131">При удалении явной иерархии все консолидированные элементы в этой иерархии также удаляются.</span><span class="sxs-lookup"><span data-stu-id="e6416-131">If you delete an explicit hierarchy, all consolidated members that were used in the hierarchy are deleted.</span></span>

-   <span data-ttu-id="e6416-132">При удалении объединенных элементов из явной иерархии все конечные элементы, сгруппированные в этом консолидированном элементе, перемещаются в корень иерархии.</span><span class="sxs-lookup"><span data-stu-id="e6416-132">If you delete a consolidated member that was in an explicit hierarchy, all leaf members that were grouped by that consolidated member are moved to the root.</span></span>

## <a name="explicit-hierarchies-versus-derived-hierarchies"></a><span data-ttu-id="e6416-133">Явные иерархии или производные иерархии</span><span class="sxs-lookup"><span data-stu-id="e6416-133">Explicit Hierarchies versus Derived Hierarchies</span></span>
 <span data-ttu-id="e6416-134">В следующей таблице приведены некоторые различия между явными и производными иерархиями.</span><span class="sxs-lookup"><span data-stu-id="e6416-134">The following table shows some of the differences between explicit and derived hierarchies.</span></span>

|<span data-ttu-id="e6416-135">Явные иерархии</span><span class="sxs-lookup"><span data-stu-id="e6416-135">Explicit Hierarchies</span></span>|<span data-ttu-id="e6416-136">Производные иерархии</span><span class="sxs-lookup"><span data-stu-id="e6416-136">Derived Hierarchies</span></span>|
|--------------------------|-------------------------|
|<span data-ttu-id="e6416-137">Структура определяется пользователем</span><span class="sxs-lookup"><span data-stu-id="e6416-137">Structure is defined by the user</span></span>|<span data-ttu-id="e6416-138">Структура образуется из связей между атрибутами на основе домена</span><span class="sxs-lookup"><span data-stu-id="e6416-138">Structure is derived from the relationships between domain-based attributes</span></span>|
|<span data-ttu-id="e6416-139">Содержит элементы из одной сущности</span><span class="sxs-lookup"><span data-stu-id="e6416-139">Contains members from a single entity</span></span>|<span data-ttu-id="e6416-140">Содержит элементы из нескольких сущностей</span><span class="sxs-lookup"><span data-stu-id="e6416-140">Contains members from multiple entities</span></span>|
|<span data-ttu-id="e6416-141">Использует консолидированные элементы для группировки других элементов</span><span class="sxs-lookup"><span data-stu-id="e6416-141">Uses consolidated members to group other members</span></span>|<span data-ttu-id="e6416-142">Использует конечные элементы одной сущности для группировки конечных элементов другой сущности</span><span class="sxs-lookup"><span data-stu-id="e6416-142">Uses leaf members from one entity to group leaf members from another entity</span></span>|
|<span data-ttu-id="e6416-143">Может быть неоднородной</span><span class="sxs-lookup"><span data-stu-id="e6416-143">Can be ragged</span></span>|<span data-ttu-id="e6416-144">Всегда содержит согласованное количество уровней.</span><span class="sxs-lookup"><span data-stu-id="e6416-144">Always contains a consistent number of levels</span></span>|

## <a name="explicit-hierarchy-example"></a><span data-ttu-id="e6416-145">Пример явной иерархии</span><span class="sxs-lookup"><span data-stu-id="e6416-145">Explicit Hierarchy Example</span></span>
 <span data-ttu-id="e6416-146">В следующем примере сущность Product содержит следующие конечные элементы: BK-M101 {Mountain-100}, BK-M201 {Mountain-200}, BK-M301 {Mountain-300}, BK-R150 {Road-150}, BK-R450 {Road-450} и BK-R650 {Road-650}.</span><span class="sxs-lookup"><span data-stu-id="e6416-146">In the following example, the Product entity contains these leaf members: BK-M101 {Mountain-100}, BK-M201 {Mountain-200}, BK-M301 {Mountain-300}, BK-R150 {Road-150}, BK-R450 {Road-450}, and BK-R650 {Road-650}.</span></span>

 <span data-ttu-id="e6416-147">Для объединения этих конечных элементов в заданных точках консолидации можно создать консолидированные элементы для сущности Product.</span><span class="sxs-lookup"><span data-stu-id="e6416-147">To summarize these leaf members at specific consolidation points, you can create consolidated members in the Product entity.</span></span> <span data-ttu-id="e6416-148">Для этого надо вставить консолидированные элементы на том уровне дерева иерархии, где планируется объединить конечные элементы.</span><span class="sxs-lookup"><span data-stu-id="e6416-148">Insert the consolidated members at levels in the hierarchy tree where you want to summarize the leaf members.</span></span> <span data-ttu-id="e6416-149">Не существует никаких ограничений на то, где именно необходимо вставлять консолидированные элементы, однако каждый из них (и конечный, и объединенный) можно использовать только один раз.</span><span class="sxs-lookup"><span data-stu-id="e6416-149">There is no limitation on where you insert your consolidated members; however, each member (leaf or consolidated) can be used only once.</span></span>

 <span data-ttu-id="e6416-150">![Пример явной иерархии «Горный велосипед»](../../2014/master-data-services/media/mds-conc-explicit-hierarchy.gif "Пример явной иерархии «Горный велосипед»")</span><span class="sxs-lookup"><span data-stu-id="e6416-150">![Mountain Bike Explicit Hierarchy Example](../../2014/master-data-services/media/mds-conc-explicit-hierarchy.gif "Mountain Bike Explicit Hierarchy Example")</span></span>

 <span data-ttu-id="e6416-151">Консолидированные элементы можно использовать для группировки элементов на любом уровне, при этом консолидированные и конечные элементы сортируются в том порядке, который для них определен.</span><span class="sxs-lookup"><span data-stu-id="e6416-151">Consolidated members can be used to group members at any level, and leaf and consolidated members are sorted in the order you determine.</span></span>

## <a name="related-tasks"></a><span data-ttu-id="e6416-152">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="e6416-152">Related Tasks</span></span>

|<span data-ttu-id="e6416-153">Описание задачи</span><span class="sxs-lookup"><span data-stu-id="e6416-153">Task Description</span></span>|<span data-ttu-id="e6416-154">Раздел</span><span class="sxs-lookup"><span data-stu-id="e6416-154">Topic</span></span>|
|----------------------|-----------|
|<span data-ttu-id="e6416-155">Включение сущности для явных иерархий и коллекций.</span><span class="sxs-lookup"><span data-stu-id="e6416-155">Enable an entity for explicit hierarchies and collections.</span></span>|[<span data-ttu-id="e6416-156">Включение сущности для явных иерархий и коллекций &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="e6416-156">Enable an Entity for Explicit Hierarchies and Collections &#40;Master Data Services&#41;</span></span>](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md)|
|<span data-ttu-id="e6416-157">Создание новой явной иерархии.</span><span class="sxs-lookup"><span data-stu-id="e6416-157">Create a new explicit hierarchy.</span></span>|[<span data-ttu-id="e6416-158">Создание явной иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="e6416-158">Create an Explicit Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md)|
|<span data-ttu-id="e6416-159">Изменение имени существующей явной иерархии.</span><span class="sxs-lookup"><span data-stu-id="e6416-159">Change the name of an existing explicity hierarchy.</span></span>|[<span data-ttu-id="e6416-160">Изменение имени явной иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="e6416-160">Change an Explicit Hierarchy Name &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/change-an-explicit-hierarchy-name-master-data-services.md)|
|<span data-ttu-id="e6416-161">Удаление существующей явной иерархии.</span><span class="sxs-lookup"><span data-stu-id="e6416-161">Delete an existing explicit hierarchy.</span></span>|[<span data-ttu-id="e6416-162">Удаление явной иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="e6416-162">Delete an Explicit Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-an-explicit-hierarchy-master-data-services.md)|
|||

## <a name="related-content"></a><span data-ttu-id="e6416-163">См. также</span><span class="sxs-lookup"><span data-stu-id="e6416-163">Related Content</span></span>

-   [<span data-ttu-id="e6416-164">Производные иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="e6416-164">Derived Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/derived-hierarchies-master-data-services.md)

-   [<span data-ttu-id="e6416-165">Коллекции (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="e6416-165">Collections &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/collections-master-data-services.md)


