---
title: Производные иерархии с явными ограничениями (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- hierarchies [Master Data Services], derived hierarchies with explicit caps
- explicit hierarchies, derived hierarchies with explicit caps
- derived hierarchies, derived hierarchies with explicit caps
ms.assetid: 6a82ff66-c137-4757-99bb-787d189b4295
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: d2460ddf098f0547c2876dd9689f5d2bf9b461a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656437"
---
# <a name="derived-hierarchies-with-explicit-caps-master-data-services"></a><span data-ttu-id="9f865-102">Производные иерархии с явными ограничениями (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="9f865-102">Derived Hierarchies with Explicit Caps (Master Data Services)</span></span>
  <span data-ttu-id="9f865-103">В [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]использование уровней явной иерархии в качестве высших уровней производной иерархии называется «производной иерархией с явным ограничением».</span><span class="sxs-lookup"><span data-stu-id="9f865-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], when the levels from an explicit hierarchy are used as the top levels of a derived hierarchy, this is called a derived hierarchy with an explicit cap.</span></span>

 <span data-ttu-id="9f865-104">Явная иерархия должна быть основана на той же сущности, что и сущность на вершине производной иерархии.</span><span class="sxs-lookup"><span data-stu-id="9f865-104">The explicit hierarchy must be based on the same entity as the entity at the top of the derived hierarchy.</span></span>

 <span data-ttu-id="9f865-105">В пользовательском интерфейсе [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] такой тип иерархии можно создать, перетащив явную иерархию на вершину производной иерархии.</span><span class="sxs-lookup"><span data-stu-id="9f865-105">In the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] user interface (UI), you create this type of hierarchy by dragging an explicit hierarchy to the top of a derived hierarchy.</span></span>

 <span data-ttu-id="9f865-106">![mds_conc_explicit_cap_UI_structure](../../2014/master-data-services/media/mds-conc-explicit-cap-ui-structure.gif "mds_conc_explicit_cap_UI_structure")</span><span class="sxs-lookup"><span data-stu-id="9f865-106">![mds_conc_explicit_cap_UI_structure](../../2014/master-data-services/media/mds-conc-explicit-cap-ui-structure.gif "mds_conc_explicit_cap_UI_structure")</span></span>

## <a name="derived-hierarchy-with-explicit-cap-example"></a><span data-ttu-id="9f865-107">Образец производной иерархии с явным ограничением</span><span class="sxs-lookup"><span data-stu-id="9f865-107">Derived Hierarchy with Explicit Cap Example</span></span>
 <span data-ttu-id="9f865-108">В данном примере элементы явной иерархии происходят из сущности «Подкатегория».</span><span class="sxs-lookup"><span data-stu-id="9f865-108">In this example, the members in the explicit hierarchy are from the Subcategory entity.</span></span> <span data-ttu-id="9f865-109">В производной иерархии элементы высшего уровня также происходят из сущности «Подкатегория».</span><span class="sxs-lookup"><span data-stu-id="9f865-109">In the derived hierarchy, the top-level members are also from the Subcategory entity.</span></span>

 <span data-ttu-id="9f865-110">![mds_conc_explicit_cap_UI_example](../../2014/master-data-services/media/mds-conc-explicit-cap-ui-example.gif "mds_conc_explicit_cap_UI_example")</span><span class="sxs-lookup"><span data-stu-id="9f865-110">![mds_conc_explicit_cap_UI_example](../../2014/master-data-services/media/mds-conc-explicit-cap-ui-example.gif "mds_conc_explicit_cap_UI_example")</span></span>

 <span data-ttu-id="9f865-111">При использовании явной иерархии на вершине производной иерархии производная иерархия становится неоднородной.</span><span class="sxs-lookup"><span data-stu-id="9f865-111">By using the explicit hierarchy at the top of a derived hierarchy, the derived hierarchy becomes ragged.</span></span>

## <a name="rules"></a><span data-ttu-id="9f865-112">Правила</span><span class="sxs-lookup"><span data-stu-id="9f865-112">Rules</span></span>

-   <span data-ttu-id="9f865-113">В производной иерархии с явным ограничением не может быть больше одной явной иерархии.</span><span class="sxs-lookup"><span data-stu-id="9f865-113">You cannot have more than one explicit hierarchy in a derived hierarchy with explicit cap.</span></span>

-   <span data-ttu-id="9f865-114">Одну и ту же явную иерархию можно использовать как ограничение для нескольких производных иерархий.</span><span class="sxs-lookup"><span data-stu-id="9f865-114">You can use the same explicit hierarchy as a cap for multiple derived hierarchies.</span></span>

-   <span data-ttu-id="9f865-115">Нельзя назначить разрешения на элементы иерархии производным иерархиям с явными ограничениями.</span><span class="sxs-lookup"><span data-stu-id="9f865-115">You cannot assign hierarchy member permissions to derived hierarchies with explicit caps.</span></span> <span data-ttu-id="9f865-116">Если назначить разрешение явной иерархии или производной иерархии индивидуально, то разрешение затронет обе иерархии.</span><span class="sxs-lookup"><span data-stu-id="9f865-116">If you assign permissions to either the explicit hierarchy or the derived hierarchy individually, the permissions affect both hierarchies.</span></span>

## <a name="related-tasks"></a><span data-ttu-id="9f865-117">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="9f865-117">Related Tasks</span></span>

|<span data-ttu-id="9f865-118">Описание задачи</span><span class="sxs-lookup"><span data-stu-id="9f865-118">Task Description</span></span>|<span data-ttu-id="9f865-119">Раздел</span><span class="sxs-lookup"><span data-stu-id="9f865-119">Topic</span></span>|
|----------------------|-----------|
|<span data-ttu-id="9f865-120">Создание производной иерархии.</span><span class="sxs-lookup"><span data-stu-id="9f865-120">Create a derived hierarchy.</span></span>|[<span data-ttu-id="9f865-121">Создание производной иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="9f865-121">Create a Derived Hierarchy &#40;Master Data Services&#41;</span></span>](create-a-derived-hierarchy-master-data-services.md)|
|<span data-ttu-id="9f865-122">Создание явной иерархии.</span><span class="sxs-lookup"><span data-stu-id="9f865-122">Create an explicit hierarchy.</span></span>|[<span data-ttu-id="9f865-123">Создание явной иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="9f865-123">Create an Explicit Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md)|
|<span data-ttu-id="9f865-124">Удаление существующей производной иерархии.</span><span class="sxs-lookup"><span data-stu-id="9f865-124">Delete an existing derived hierarchy.</span></span>|[<span data-ttu-id="9f865-125">Удаление производной иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="9f865-125">Delete a Derived Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-a-derived-hierarchy-master-data-services.md)|
|||

## <a name="related-content"></a><span data-ttu-id="9f865-126">См. также</span><span class="sxs-lookup"><span data-stu-id="9f865-126">Related Content</span></span>

-   [<span data-ttu-id="9f865-127">Производные иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="9f865-127">Derived Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/derived-hierarchies-master-data-services.md)

-   [<span data-ttu-id="9f865-128">Явные иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="9f865-128">Explicit Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/explicit-hierarchies-master-data-services.md)


