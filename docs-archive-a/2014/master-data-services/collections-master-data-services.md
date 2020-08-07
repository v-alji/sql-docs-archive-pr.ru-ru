---
title: Коллекции (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- collections [Master Data Services]
- collections [Master Data Services], about collections
ms.assetid: 5aa1d1e0-b4e5-4897-8e74-01dcf418df73
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ce49c57aad5da52dabba32a0f3fb9b6f4f45b209
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731873"
---
# <a name="collections-master-data-services"></a><span data-ttu-id="eabfd-102">Коллекции (службы основных данных)</span><span class="sxs-lookup"><span data-stu-id="eabfd-102">Collections (Master Data Services)</span></span>
  <span data-ttu-id="eabfd-103">Коллекция — это группа конечных или консолидированных элементов из одной сущности.</span><span class="sxs-lookup"><span data-stu-id="eabfd-103">A collection is a group of leaf and consolidated members from a single entity.</span></span> <span data-ttu-id="eabfd-104">Коллекции используются, когда нет необходимости в полной иерархии и нужно просмотреть разные группы элементов для отчетов или анализа или когда необходимо создать классификацию.</span><span class="sxs-lookup"><span data-stu-id="eabfd-104">Use collections when you do not need a complete hierarchy and you want to view different groupings of members for reporting or analysis, or when you need to create a taxonomy.</span></span>  
  
## <a name="what-collections-contain"></a><span data-ttu-id="eabfd-105">Содержимое коллекций</span><span class="sxs-lookup"><span data-stu-id="eabfd-105">What Collections Contain</span></span>  
 <span data-ttu-id="eabfd-106">Коллекции не накладывают ограничений на число или тип включаемых элементов, пока эти элементы находятся в одной сущности.</span><span class="sxs-lookup"><span data-stu-id="eabfd-106">Collections do not limit the number or type of members you can include, as long as the members are within the same entity.</span></span> <span data-ttu-id="eabfd-107">Коллекция может содержать конечные и консолидированные элементы из нескольких обязательных и необязательных явных иерархий.</span><span class="sxs-lookup"><span data-stu-id="eabfd-107">A collection can contain leaf and consolidated members from multiple mandatory and non-mandatory explicit hierarchies.</span></span>  
  
 <span data-ttu-id="eabfd-108">При создании коллекции создается не иерархическая структура, а плоский список элементов.</span><span class="sxs-lookup"><span data-stu-id="eabfd-108">When you create a collection, you are not creating a hierarchical structure; you are creating a flat list of members.</span></span> <span data-ttu-id="eabfd-109">При выборе узла из иерархии и добавлении его в коллекцию выделенный объединенный элемент является единственным элементом, который добавляется в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="eabfd-109">When you select a node from a hierarchy and add it to the collection, the consolidated member you selected is the only member added to the collection.</span></span>  
  
 <span data-ttu-id="eabfd-110">Коллекция также может содержать другие коллекции.</span><span class="sxs-lookup"><span data-stu-id="eabfd-110">A collection can also contain other collections.</span></span> <span data-ttu-id="eabfd-111">Можно использовать коллекции коллекций для создания классификаций.</span><span class="sxs-lookup"><span data-stu-id="eabfd-111">You can use collections of collections to create taxonomies.</span></span>  
  
 <span data-ttu-id="eabfd-112">Пользователь, создающий коллекцию, автоматически вносится в список ее владельцев.</span><span class="sxs-lookup"><span data-stu-id="eabfd-112">When you create a collection you are automatically listed as the owner.</span></span> <span data-ttu-id="eabfd-113">Если вы являетесь администратором, то при необходимости можете создавать другие атрибуты коллекции.</span><span class="sxs-lookup"><span data-stu-id="eabfd-113">If you are an administrator, you can create other attributes for your collection as needed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="eabfd-114">Перед созданием коллекции для сущности необходимо разрешить использование явных иерархий.</span><span class="sxs-lookup"><span data-stu-id="eabfd-114">Before you can create a collection, the entity must be enabled for explicit hierarchies.</span></span> <span data-ttu-id="eabfd-115">Дополнительные сведения см. в разделе [Включение сущности для явных иерархий и коллекций &#40;Master Data Services&#41;](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="eabfd-115">For more information, see [Enable an Entity for Explicit Hierarchies and Collections &#40;Master Data Services&#41;](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span></span>  
  
## <a name="subscription-views-for-collections"></a><span data-ttu-id="eabfd-116">Представления подписки для коллекций</span><span class="sxs-lookup"><span data-stu-id="eabfd-116">Subscription Views for Collections</span></span>  
 <span data-ttu-id="eabfd-117">Есть два типа представлений подписки, которые отображают коллекции.</span><span class="sxs-lookup"><span data-stu-id="eabfd-117">There are two types of subscription views that show collections.</span></span> <span data-ttu-id="eabfd-118">Формат **Атрибуты коллекций** отображает список коллекций и другие атрибуты, связанные с коллекциями, например описание или владельца.</span><span class="sxs-lookup"><span data-stu-id="eabfd-118">The **Collection attributes** format shows a list of collections and any attributes related to the collections (like description or owner).</span></span> <span data-ttu-id="eabfd-119">Формат **Коллекции** отображает все элементы во всех коллекциях, а также вес и порядок сортировки каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="eabfd-119">The **Collections** format shows all members in all collections, as well as each members weight and sort order.</span></span> <span data-ttu-id="eabfd-120">Дополнительные сведения см. в разделе [Экспорт данных &#40;Master Data Services&#41;](overview-exporting-data-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="eabfd-120">For more information, see [Exporting Data &#40;Master Data Services&#41;](overview-exporting-data-master-data-services.md).</span></span>  
  
 <span data-ttu-id="eabfd-121">Если для определенных элементов в коллекции установлены взвешенные значения, такие значения доступны в связанных представлениях подписки.</span><span class="sxs-lookup"><span data-stu-id="eabfd-121">If you set weight values for specific members in a collection, these values are available in related subscription views.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="eabfd-122">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="eabfd-122">Related Tasks</span></span>  
  
|<span data-ttu-id="eabfd-123">Описание задачи</span><span class="sxs-lookup"><span data-stu-id="eabfd-123">Task Description</span></span>|<span data-ttu-id="eabfd-124">Раздел</span><span class="sxs-lookup"><span data-stu-id="eabfd-124">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="eabfd-125">Включение сущности для явных иерархий и коллекций.</span><span class="sxs-lookup"><span data-stu-id="eabfd-125">Enable an entity for explicit hierarchies and collections.</span></span>|[<span data-ttu-id="eabfd-126">Включение сущности для явных иерархий и коллекций &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="eabfd-126">Enable an Entity for Explicit Hierarchies and Collections &#40;Master Data Services&#41;</span></span>](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md)|  
|<span data-ttu-id="eabfd-127">Создание новой коллекции.</span><span class="sxs-lookup"><span data-stu-id="eabfd-127">Create a new collection.</span></span>|[<span data-ttu-id="eabfd-128">Создание коллекции (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="eabfd-128">Create a Collection &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-collection-master-data-services.md)|  
|<span data-ttu-id="eabfd-129">Добавление элементов в существующую коллекцию.</span><span class="sxs-lookup"><span data-stu-id="eabfd-129">Add members to an existing collection.</span></span>|[<span data-ttu-id="eabfd-130">Добавление элементов в коллекцию (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="eabfd-130">Add Members to a Collection &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/add-members-to-a-collection-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="eabfd-131">См. также</span><span class="sxs-lookup"><span data-stu-id="eabfd-131">Related Content</span></span>  
  
-   [<span data-ttu-id="eabfd-132">Явные иерархии (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="eabfd-132">Explicit Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/explicit-hierarchies-master-data-services.md)  
  
-   [<span data-ttu-id="eabfd-133">Экспорт Master Data Services &#40;данных&#41;</span><span class="sxs-lookup"><span data-stu-id="eabfd-133">Exporting Data &#40;Master Data Services&#41;</span></span>](overview-exporting-data-master-data-services.md)  
  
  
