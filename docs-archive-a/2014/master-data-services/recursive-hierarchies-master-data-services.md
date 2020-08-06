---
title: Рекурсивные иерархии (Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- recursive hierarchies [Master Data Services]
- hierarchies [Master Data Services], recursive hierarchies
ms.assetid: 9408c6ea-d9c4-4a0b-8a1b-1457fb6944af
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 3c149d500ce1499ad36247d5e32bb6f2d55b4250
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667756"
---
# <a name="recursive-hierarchies-master-data-services"></a><span data-ttu-id="3b4b5-102">Рекурсивные иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="3b4b5-102">Recursive Hierarchies (Master Data Services)</span></span>
  <span data-ttu-id="3b4b5-103">В [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]рекурсивная иерархия — это производная иерархия, которая содержит рекурсивную связь.</span><span class="sxs-lookup"><span data-stu-id="3b4b5-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], a recursive hierarchy is a derived hierarchy that includes a recursive relationship.</span></span> <span data-ttu-id="3b4b5-104">Рекурсивная связь возникает, когда у сущности есть атрибут, который базируется на самой сущности, на основе домена.</span><span class="sxs-lookup"><span data-stu-id="3b4b5-104">A recursive relationship exists when an entity has a domain-based attribute based on the entity itself.</span></span>

## <a name="recursive-hierarchy-example"></a><span data-ttu-id="3b4b5-105">Образец рекурсивной иерархии</span><span class="sxs-lookup"><span data-stu-id="3b4b5-105">Recursive Hierarchy Example</span></span>
 <span data-ttu-id="3b4b5-106">Типичным примером рекурсивной иерархии может служить организационная структура.</span><span class="sxs-lookup"><span data-stu-id="3b4b5-106">A typical recursive hierarchy example is an organizational structure.</span></span> <span data-ttu-id="3b4b5-107">В [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]для этого создается сущность «Сотрудник» с основанным на домене атрибутом «Менеджер».</span><span class="sxs-lookup"><span data-stu-id="3b4b5-107">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you would do this by creating an Employee entity with a domain-based attribute called Manager.</span></span> <span data-ttu-id="3b4b5-108">Атрибут «Менеджер» заполняется из списка сотрудников.</span><span class="sxs-lookup"><span data-stu-id="3b4b5-108">The Manager attribute is populated from the list of employees.</span></span> <span data-ttu-id="3b4b5-109">В организации, взятой для образца, все сотрудники могут быть менеджерами.</span><span class="sxs-lookup"><span data-stu-id="3b4b5-109">In this sample organization, all employees can be managers.</span></span>

 <span data-ttu-id="3b4b5-110">![mds_conc_recursive_table_w_data](../../2014/master-data-services/media/mds-conc-recursive-table-w-data.gif "mds_conc_recursive_table_w_data")</span><span class="sxs-lookup"><span data-stu-id="3b4b5-110">![mds_conc_recursive_table_w_data](../../2014/master-data-services/media/mds-conc-recursive-table-w-data.gif "mds_conc_recursive_table_w_data")</span></span>

 <span data-ttu-id="3b4b5-111">Можно создать производную иерархию, в которой выделяется связь между сущностью «Сотрудник» и атрибутом «Менеджер» на основе домена.</span><span class="sxs-lookup"><span data-stu-id="3b4b5-111">You can create a derived hierarchy that highlights the relationship between the Employee entity and the Manager domain-based attribute.</span></span>

 <span data-ttu-id="3b4b5-112">![mds_conc_recursive_UI_structure](../../2014/master-data-services/media/mds-conc-recursive-ui-structure.gif "mds_conc_recursive_UI_structure")</span><span class="sxs-lookup"><span data-stu-id="3b4b5-112">![mds_conc_recursive_UI_structure](../../2014/master-data-services/media/mds-conc-recursive-ui-structure.gif "mds_conc_recursive_UI_structure")</span></span>

 <span data-ttu-id="3b4b5-113">Чтобы включить каждый элемент в иерархию только один раз, можно закрепить нулевые связи.</span><span class="sxs-lookup"><span data-stu-id="3b4b5-113">To include each member in the hierarchy only once, you can anchor null relationships.</span></span> <span data-ttu-id="3b4b5-114">При этом элементы с пустыми значениями атрибутов на основе домена отображаются на высшем уровне иерархии.</span><span class="sxs-lookup"><span data-stu-id="3b4b5-114">When you do, members with blank domain-based attribute values are displayed at the top level of the hierarchy.</span></span>

 <span data-ttu-id="3b4b5-115">![mds_conc_recursive_UI_example_anchored](../../2014/master-data-services/media/mds-conc-recursive-ui-example-anchored.gif "mds_conc_recursive_UI_example_anchored")</span><span class="sxs-lookup"><span data-stu-id="3b4b5-115">![mds_conc_recursive_UI_example_anchored](../../2014/master-data-services/media/mds-conc-recursive-ui-example-anchored.gif "mds_conc_recursive_UI_example_anchored")</span></span>

 <span data-ttu-id="3b4b5-116">Если не закрепить нулевые связи, то элементы будут включаться несколько раз.</span><span class="sxs-lookup"><span data-stu-id="3b4b5-116">If you do not anchor null relationships, members are included multiple times.</span></span> <span data-ttu-id="3b4b5-117">Все элементы отображаются на высшем уровне.</span><span class="sxs-lookup"><span data-stu-id="3b4b5-117">All members are displayed at the top level.</span></span> <span data-ttu-id="3b4b5-118">Они также отображаются под теми элементами, атрибутами которых являются.</span><span class="sxs-lookup"><span data-stu-id="3b4b5-118">They are also displayed under members of which they are attributes.</span></span>

 <span data-ttu-id="3b4b5-119">![mds_conc_recursive_UI_example_nonanchored](../../2014/master-data-services/media/mds-conc-recursive-ui-example-nonanchored.gif "mds_conc_recursive_UI_example_nonanchored")</span><span class="sxs-lookup"><span data-stu-id="3b4b5-119">![mds_conc_recursive_UI_example_nonanchored](../../2014/master-data-services/media/mds-conc-recursive-ui-example-nonanchored.gif "mds_conc_recursive_UI_example_nonanchored")</span></span>

 <span data-ttu-id="3b4b5-120">В данном примере Марсия находится на высшем уровне.</span><span class="sxs-lookup"><span data-stu-id="3b4b5-120">In this example, Marcia is at the top level.</span></span> <span data-ttu-id="3b4b5-121">Она не является менеджером ни для кого из сотрудников, поскольку она не используется как значение атрибута на основе домена для какого-либо другого элемента сущности «Сотрудник».</span><span class="sxs-lookup"><span data-stu-id="3b4b5-121">She is not the manager of any employees because she is not used as a domain-based attribute value for any other Employee members.</span></span> <span data-ttu-id="3b4b5-122">У Роберта, с другой стороны, есть более низкий уровень, поскольку для Марсии Роберт является значением ее атрибута «Менеджер».</span><span class="sxs-lookup"><span data-stu-id="3b4b5-122">Robert, in contrast, has a level beneath him because Marcia has Robert as her Manager attribute value.</span></span>

## <a name="rules"></a><span data-ttu-id="3b4b5-123">Правила</span><span class="sxs-lookup"><span data-stu-id="3b4b5-123">Rules</span></span>

-   <span data-ttu-id="3b4b5-124">Производная иерархия не может содержать более одной рекурсивной связи.</span><span class="sxs-lookup"><span data-stu-id="3b4b5-124">A derived hierarchy cannot contain more than one recursive relationship.</span></span> <span data-ttu-id="3b4b5-125">Однако эта иерархия может содержать другие производные связи (например, производная иерархия, содержащая рекурсивную связь «Менеджер-Сотрудник», также может иметь связи «Страна-Менеджер» и «Сотрудник-Магазин»).</span><span class="sxs-lookup"><span data-stu-id="3b4b5-125">It can, however, have other derived relationships (for example, a derived hierarchy that contains a recursive Manager to Employee relationship can also have Country to Manager and Employee to Store relationships).</span></span>

-   <span data-ttu-id="3b4b5-126">Нельзя назначать разрешения элементам (на вкладке **Элементы иерархии** ) в рекурсивной иерархии.</span><span class="sxs-lookup"><span data-stu-id="3b4b5-126">You cannot assign member permissions (on the **Hierarchy Members** tab) to members in a recursive hierarchy.</span></span>

-   <span data-ttu-id="3b4b5-127">В рекурсивные иерархии не могут включаться циклические связи.</span><span class="sxs-lookup"><span data-stu-id="3b4b5-127">Recursive hierarchies cannot include circular relationships.</span></span> <span data-ttu-id="3b4b5-128">Например, Катерина не может быть менеджером Сэндип, если Сэндип — ее менеджер.</span><span class="sxs-lookup"><span data-stu-id="3b4b5-128">For example, Katherine cannot be Sandeep's manager if Sandeep is her manager.</span></span> <span data-ttu-id="3b4b5-129">Также Катерина не может быть своим собственным менеджером.</span><span class="sxs-lookup"><span data-stu-id="3b4b5-129">Also, Katherine cannot manage herself.</span></span>

## <a name="related-tasks"></a><span data-ttu-id="3b4b5-130">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="3b4b5-130">Related Tasks</span></span>

|<span data-ttu-id="3b4b5-131">Описание задачи</span><span class="sxs-lookup"><span data-stu-id="3b4b5-131">Task Description</span></span>|<span data-ttu-id="3b4b5-132">Раздел</span><span class="sxs-lookup"><span data-stu-id="3b4b5-132">Topic</span></span>|
|----------------------|-----------|
|<span data-ttu-id="3b4b5-133">Создание производной иерархии.</span><span class="sxs-lookup"><span data-stu-id="3b4b5-133">Create a derived hierarchy.</span></span>|[<span data-ttu-id="3b4b5-134">Создание производной иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="3b4b5-134">Create a Derived Hierarchy &#40;Master Data Services&#41;</span></span>](create-a-derived-hierarchy-master-data-services.md)|
|<span data-ttu-id="3b4b5-135">Изменение имени существующей производной иерархии.</span><span class="sxs-lookup"><span data-stu-id="3b4b5-135">Change the name of an existing derived hierarchy.</span></span>|[<span data-ttu-id="3b4b5-136">Изменение имени производной иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="3b4b5-136">Change a Derived Hierarchy Name &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/change-a-derived-hierarchy-name-master-data-services.md)|
|<span data-ttu-id="3b4b5-137">Удаление существующей производной иерархии.</span><span class="sxs-lookup"><span data-stu-id="3b4b5-137">Delete an existing derived hierarchy.</span></span>|[<span data-ttu-id="3b4b5-138">Удаление производной иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="3b4b5-138">Delete a Derived Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-a-derived-hierarchy-master-data-services.md)|

## <a name="related-content"></a><span data-ttu-id="3b4b5-139">См. также</span><span class="sxs-lookup"><span data-stu-id="3b4b5-139">Related Content</span></span>

-   [<span data-ttu-id="3b4b5-140">Атрибуты на основе домена (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="3b4b5-140">Domain-Based Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/domain-based-attributes-master-data-services.md)

-   [<span data-ttu-id="3b4b5-141">Производные иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="3b4b5-141">Derived Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/derived-hierarchies-master-data-services.md)


