---
title: Метаданные (Master Data Services) | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- user-defined metadata [Master Data Services], about user-defined metadata
- metadata [Master Data Services], about metadata
- metadata [Master Data Services]
- user-defined metadata [Master Data Services]
ms.assetid: ac1aabe3-d8d4-4d7a-8954-50ee3c185d81
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 39ab95b7925306febb551962495da7ec9751589b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730810"
---
# <a name="metadata-master-data-services"></a><span data-ttu-id="60ce2-102">Метаданные (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="60ce2-102">Metadata (Master Data Services)</span></span>
  <span data-ttu-id="60ce2-103">В службах [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] определяемые пользователем метаданные — это данные, которые служат для описания объектов модели.</span><span class="sxs-lookup"><span data-stu-id="60ce2-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], user-defined metadata is information that you use to describe model objects.</span></span> <span data-ttu-id="60ce2-104">Например, может потребоваться отслеживать владельцев определенной модели или сущности либо отслеживать системы-источники, которые поставляют данные сущности.</span><span class="sxs-lookup"><span data-stu-id="60ce2-104">For example, you may want to track the owners of a particular model or entity, or track the source systems that supply data to an entity.</span></span>  
  
 <span data-ttu-id="60ce2-105">Определяемые пользователем метаданные управляются моделью с именем **Metadata**.</span><span class="sxs-lookup"><span data-stu-id="60ce2-105">User-defined metadata is managed by a model called **Metadata**.</span></span> <span data-ttu-id="60ce2-106">Эта модель автоматически включается при [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] установке и аналогична остальным моделям MDS, за исключением того, что вы не можете создавать их версии.</span><span class="sxs-lookup"><span data-stu-id="60ce2-106">This model is automatically included when [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] is installed, and it is similar to all other MDS models, except that you cannot create versions of it.</span></span>  
  
 <span data-ttu-id="60ce2-107">После того как модель метаданных будет заполнена определяемыми пользователем метаданными, ее можно будет включить в представления подписки, чтобы она стала доступна для систем подписки.</span><span class="sxs-lookup"><span data-stu-id="60ce2-107">After you populate the Metadata model with user-defined metadata, you can include it in subscription views, so it can be consumed by subscribing systems.</span></span>  
  
## <a name="metadata-entities"></a><span data-ttu-id="60ce2-108">Сущности метаданных</span><span class="sxs-lookup"><span data-stu-id="60ce2-108">Metadata Entities</span></span>  
 <span data-ttu-id="60ce2-109">Модель «Метаданные» включает пять сущностей, каждая из которых представляет некоторый тип объекта модели основных данных, поддерживающий определяемые пользователем метаданные.</span><span class="sxs-lookup"><span data-stu-id="60ce2-109">The Metadata model includes five entities, each of which represents a type of master data model object that supports user-defined metadata.</span></span> <span data-ttu-id="60ce2-110">Например, сущность **определения метаданных модели** содержит члены, представляющие модели, а сущность **определения метаданных атрибута** содержит члены, которые представляют все атрибуты во всех моделях.</span><span class="sxs-lookup"><span data-stu-id="60ce2-110">For example, the **Model Metadata Definition** entity contains members that represent models, and the **Attribute Metadata Definition** entity has members that represent all attributes in all models.</span></span>  
  
 <span data-ttu-id="60ce2-111">Чтобы определить метаданные для объекта модели, необходимо заполнить один из атрибутов этого элемента.</span><span class="sxs-lookup"><span data-stu-id="60ce2-111">To define metadata for a model object, you populate one of these member's attributes.</span></span> <span data-ttu-id="60ce2-112">Например, в сущности **определения метаданных сущности** можно заполнить атрибут Description элемента price текстом: **Цена продукта, если она продана клиенту**.</span><span class="sxs-lookup"><span data-stu-id="60ce2-112">For example, in the **Entity Metadata Definition** entity, you can populate the Price member's Description attribute with the text: **The product price when sold to a customer**.</span></span>  
  
 <span data-ttu-id="60ce2-113">Элементы модели «Метаданные» автоматически обновляются при каждом добавлении и удалении объектов модели, поддерживающих определяемые пользователем метаданные.</span><span class="sxs-lookup"><span data-stu-id="60ce2-113">The members in the Metadata model are automatically updated whenever model objects that support user-defined metadata are added or deleted.</span></span>  
  
 <span data-ttu-id="60ce2-114">Для модели «Метаданные» нельзя создавать версии, добавлять или удалять флаги версий. Эту модель нельзя сохранять в виде пакета развертывания модели.</span><span class="sxs-lookup"><span data-stu-id="60ce2-114">The Metadata model cannot be versioned, have version flags added or changed, or be saved as a model deployment package.</span></span> <span data-ttu-id="60ce2-115">Однако в остальном эта модель имеет ту же функциональность, что и другие модели основных данных.</span><span class="sxs-lookup"><span data-stu-id="60ce2-115">However, it has all the same other functionality available to other master data models.</span></span> <span data-ttu-id="60ce2-116">Например, для модели Метаданные можно принудительно применить набор бизнес-правил для обеспечения соответствия данных политикам.</span><span class="sxs-lookup"><span data-stu-id="60ce2-116">For example, you might implement a set of business rules on the Metadata model to enforce data policies.</span></span>  
  
## <a name="customizing-your-metadata-model"></a><span data-ttu-id="60ce2-117">Настройка модели метаданных</span><span class="sxs-lookup"><span data-stu-id="60ce2-117">Customizing Your Metadata Model</span></span>  
 <span data-ttu-id="60ce2-118">Каждая сущность определения метаданных включает атрибуты «Имя», «Код» и «Описание».</span><span class="sxs-lookup"><span data-stu-id="60ce2-118">Each metadata definition entity includes Name, Code, and Description attributes.</span></span> <span data-ttu-id="60ce2-119">Для расширенного описания объектов модели можно создать дополнительные атрибуты.</span><span class="sxs-lookup"><span data-stu-id="60ce2-119">You may want to create additional attributes to further describe your model objects.</span></span>  
  
 <span data-ttu-id="60ce2-120">Например, могут быть созданы следующие атрибуты.</span><span class="sxs-lookup"><span data-stu-id="60ce2-120">For example, you might create:</span></span>  
  
-   <span data-ttu-id="60ce2-121">Атрибут на основе домена «Владелец», который будет использоваться для отслеживания владельца каждого объекта модели.</span><span class="sxs-lookup"><span data-stu-id="60ce2-121">A domain-based attribute named Owner, which you use to track the owner of each model object.</span></span>  
  
-   <span data-ttu-id="60ce2-122">Атрибут в свободной форме «Дата последнего просмотра», который будет использоваться для отслеживания даты последнего просмотра объекта владельцем.</span><span class="sxs-lookup"><span data-stu-id="60ce2-122">A free-form attribute named Last Review Date, which you use to track the date that an object was last reviewed by the owner.</span></span>  
  
-   <span data-ttu-id="60ce2-123">Атрибут на основе домена с именем Sources, который используется для мониторинга исходных систем, взаимодействующих с экземпляром, и управления ими [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="60ce2-123">A domain-based attribute named Sources, which you use to track and manage the source systems that interact with the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] instance.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="60ce2-124">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="60ce2-124">Related Tasks</span></span>  
  
|<span data-ttu-id="60ce2-125">Описание задачи</span><span class="sxs-lookup"><span data-stu-id="60ce2-125">Task Description</span></span>|<span data-ttu-id="60ce2-126">Раздел</span><span class="sxs-lookup"><span data-stu-id="60ce2-126">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="60ce2-127">Добавление метаданных к объекту модели.</span><span class="sxs-lookup"><span data-stu-id="60ce2-127">Add metadata to a model object.</span></span>|[<span data-ttu-id="60ce2-128">Добавление Master Data Services &#40;метаданных&#41;</span><span class="sxs-lookup"><span data-stu-id="60ce2-128">Add Metadata &#40;Master Data Services&#41;</span></span>](add-metadata-master-data-services.md)
|&nbsp;|&nbsp;|
  
## <a name="related-content"></a><span data-ttu-id="60ce2-129">См. также</span><span class="sxs-lookup"><span data-stu-id="60ce2-129">Related Content</span></span>  
  
-   [<span data-ttu-id="60ce2-130">Экспорт Master Data Services &#40;данных&#41;</span><span class="sxs-lookup"><span data-stu-id="60ce2-130">Exporting Data &#40;Master Data Services&#41;</span></span>](overview-exporting-data-master-data-services.md)  
  
  
