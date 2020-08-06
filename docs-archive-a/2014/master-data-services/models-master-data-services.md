---
title: Модели (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- models [Master Data Services], about models
- models [Master Data Services]
ms.assetid: 9f862a3d-25ab-41e9-b833-1db99959e825
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 1d5a4a431d3ca7b6fa499de68a2bc4c5033cd086
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668393"
---
# <a name="models-master-data-services"></a><span data-ttu-id="93246-102">Модели (службы основных данных)</span><span class="sxs-lookup"><span data-stu-id="93246-102">Models (Master Data Services)</span></span>
  <span data-ttu-id="93246-103">Модели — это самый высокий уровень организации данных в [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93246-103">Models are the highest level of data organization in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span></span> <span data-ttu-id="93246-104">Модель определяет структуру данных в решении управления основными данными.</span><span class="sxs-lookup"><span data-stu-id="93246-104">A model defines the structure of data in your master data management solution.</span></span> <span data-ttu-id="93246-105">Модель содержит следующие объекты:</span><span class="sxs-lookup"><span data-stu-id="93246-105">A model contains the following objects:</span></span>  
  
-   <span data-ttu-id="93246-106">Сущности</span><span class="sxs-lookup"><span data-stu-id="93246-106">Entities</span></span>  
  
-   <span data-ttu-id="93246-107">Атрибуты и группы атрибутов</span><span class="sxs-lookup"><span data-stu-id="93246-107">Attributes and attribute groups</span></span>  
  
-   <span data-ttu-id="93246-108">Производные и явные иерархии</span><span class="sxs-lookup"><span data-stu-id="93246-108">Explicit and derived hierarchies</span></span>  
  
-   <span data-ttu-id="93246-109">Коллекции</span><span class="sxs-lookup"><span data-stu-id="93246-109">Collections</span></span>  
  
 <span data-ttu-id="93246-110">Модели организуют структуру основных данных.</span><span class="sxs-lookup"><span data-stu-id="93246-110">Models organize the structure of your master data.</span></span> <span data-ttu-id="93246-111">Реализация [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] может иметь одну или несколько моделей, которые объединяют схожие данные.</span><span class="sxs-lookup"><span data-stu-id="93246-111">Your [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] implementation can have one or many models that each group similar kinds of data.</span></span> <span data-ttu-id="93246-112">В общем случае основные понятия могут быть сгруппированы одним из четырех способов: по лицам, местам, предметам или понятиям.</span><span class="sxs-lookup"><span data-stu-id="93246-112">In general, master data can be categorized in one of four ways: people, places, things, or concepts.</span></span> <span data-ttu-id="93246-113">Например, можно создать модель «Продукт» для данных, связанных с продуктами, или модель «Клиент»для данных, связанных с клиентами.</span><span class="sxs-lookup"><span data-stu-id="93246-113">For example, you can create a Product model to contain product-related data or a Customer model to contain customer-related data.</span></span>  
  
 <span data-ttu-id="93246-114">Пользователям и группам можно давать разрешения на просмотр и обновление объектов внутри модели.</span><span class="sxs-lookup"><span data-stu-id="93246-114">You can assign users and groups permission to view and update objects within the model.</span></span> <span data-ttu-id="93246-115">Если модели не назначено разрешение, она не отображается.</span><span class="sxs-lookup"><span data-stu-id="93246-115">If you do not give permission to the model, it is not displayed.</span></span>  
  
 <span data-ttu-id="93246-116">В любой момент времени можно создать копии основных данных в модели.</span><span class="sxs-lookup"><span data-stu-id="93246-116">At any given time, you can create copies of the master data within a model.</span></span> <span data-ttu-id="93246-117">Эти копии называются версиями.</span><span class="sxs-lookup"><span data-stu-id="93246-117">These copies are called versions.</span></span>  
  
 <span data-ttu-id="93246-118">При определении модели в тестовой среде ее можно развернуть с соответствующими данными или без них в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="93246-118">When you have defined a model in a test environment, you can deploy it, with or without the corresponding data, from the test environment to a production environment.</span></span> <span data-ttu-id="93246-119">Это устраняет необходимость повторного создания моделей в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="93246-119">This eliminates the need to recreate your models in your production environment.</span></span>  
  
## <a name="how-models-relate-to-other-objects"></a><span data-ttu-id="93246-120">Связь моделей с другими объектами</span><span class="sxs-lookup"><span data-stu-id="93246-120">How Models Relate to Other Objects</span></span>  
 <span data-ttu-id="93246-121">В модели содержатся сущности.</span><span class="sxs-lookup"><span data-stu-id="93246-121">A model contains entities.</span></span> <span data-ttu-id="93246-122">Сущности содержат атрибуты, явные иерархии и коллекции.</span><span class="sxs-lookup"><span data-stu-id="93246-122">Entities contain attributes, explicit hierarchies, and collections.</span></span> <span data-ttu-id="93246-123">Атрибуты можно объединять в группы.</span><span class="sxs-lookup"><span data-stu-id="93246-123">Attributes can be contained in attribute groups.</span></span> <span data-ttu-id="93246-124">Атрибуты на основе домена существуют, когда сущность используется как атрибут для другой сущности.</span><span class="sxs-lookup"><span data-stu-id="93246-124">Domain-based attributes exist when an entity is used as an attribute for another entity.</span></span>  
  
 <span data-ttu-id="93246-125">На рисунке отображены связи между объектами модели.</span><span class="sxs-lookup"><span data-stu-id="93246-125">This image shows the relationships among the objects in a model.</span></span>  
  
 <span data-ttu-id="93246-126">![Объекты в модели служб Master Data Services](../../2014/master-data-services/media/mds-conc-model-circles.gif "Объекты в модели служб Master Data Services")</span><span class="sxs-lookup"><span data-stu-id="93246-126">![Objects in a Master Data Services Model](../../2014/master-data-services/media/mds-conc-model-circles.gif "Objects in a Master Data Services Model")</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="93246-127">Производные иерархии — это тоже объекты модели, но на рисунке они не показаны.</span><span class="sxs-lookup"><span data-stu-id="93246-127">Derived hierarchies are also model objects, but they are not shown in the image.</span></span> <span data-ttu-id="93246-128">Производные иерархии происходят от связей атрибутов на основе домена, существующих между сущностями.</span><span class="sxs-lookup"><span data-stu-id="93246-128">Derived hierarchies are derived from the domain-based attribute relationships that exist between entities.</span></span> <span data-ttu-id="93246-129">Дополнительные сведения см. в разделе [Производные иерархии (службы Master Data Services)](derived-hierarchies-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="93246-129">See [Derived Hierarchies &#40;Master Data Services&#41;](derived-hierarchies-master-data-services.md) for more information.</span></span>  
  
 <span data-ttu-id="93246-130">Основные данные — это данные, содержащиеся в объектах модели.</span><span class="sxs-lookup"><span data-stu-id="93246-130">Master data is the data that is contained in the model objects.</span></span> <span data-ttu-id="93246-131">В среде [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]основные данные хранятся в виде элементов сущностей.</span><span class="sxs-lookup"><span data-stu-id="93246-131">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], master data is stored as members in an entity.</span></span>  
  
 <span data-ttu-id="93246-132">Объекты моделей находятся в функциональной области **Администрирование системы** пользовательского интерфейса [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="93246-132">Model objects are maintained in the **System Administration** functional area of the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] user interface.</span></span>  
  
## <a name="model-example"></a><span data-ttu-id="93246-133">Пример модели</span><span class="sxs-lookup"><span data-stu-id="93246-133">Model Example</span></span>  
 <span data-ttu-id="93246-134">В следующем примере объекты в модели «Продукт» логически группируют данные, связанные с продуктом.</span><span class="sxs-lookup"><span data-stu-id="93246-134">In the following example, the objects in the Product model logically group product-related data.</span></span>  
  
 <span data-ttu-id="93246-135">![Пример основных данных модели «Продукт»](../../2014/master-data-services/media/mds-conc-model.gif "Пример основных данных модели «Продукт»")</span><span class="sxs-lookup"><span data-stu-id="93246-135">![Product Model Master Data Example](../../2014/master-data-services/media/mds-conc-model.gif "Product Model Master Data Example")</span></span>  
  
 <span data-ttu-id="93246-136">Другие распространенные модели:</span><span class="sxs-lookup"><span data-stu-id="93246-136">Other common models are:</span></span>  
  
-   <span data-ttu-id="93246-137">«Счета» — может включать такие сущности, как балансы, счета прибылей, статистика и тип счета;</span><span class="sxs-lookup"><span data-stu-id="93246-137">Accounts, which could include entities such as balance sheet accounts, income statement accounts, statistics, and account type.</span></span>  
  
-   <span data-ttu-id="93246-138">клиенты — может включать в себя такие сущности, как пол, образование, занятость и семейное положение;</span><span class="sxs-lookup"><span data-stu-id="93246-138">Customer, which could include entities such as gender, education, occupation, and marital status.</span></span>  
  
-   <span data-ttu-id="93246-139">географический регион — может включать в себя такие сущности, как почтовые коды, города, округа, районы, республики, края, страны и континенты.</span><span class="sxs-lookup"><span data-stu-id="93246-139">Geography, which could include entities such as postal codes, cities, counties, states, provinces, regions, territories, countries, and continents.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="93246-140">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="93246-140">Related Tasks</span></span>  
  
|<span data-ttu-id="93246-141">Описание задачи</span><span class="sxs-lookup"><span data-stu-id="93246-141">Task Description</span></span>|<span data-ttu-id="93246-142">Раздел</span><span class="sxs-lookup"><span data-stu-id="93246-142">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="93246-143">Создание модели для организации основных данных.</span><span class="sxs-lookup"><span data-stu-id="93246-143">Create a model to organize your master data.</span></span>|[<span data-ttu-id="93246-144">Создание модели (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="93246-144">Create a Model &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-model-master-data-services.md)|  
|<span data-ttu-id="93246-145">Изменение имени существующей модели.</span><span class="sxs-lookup"><span data-stu-id="93246-145">Change the name of an existing model.</span></span>|[<span data-ttu-id="93246-146">Измените имя модели &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="93246-146">Change a Model Name &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/change-a-model-name-master-data-services.md)|  
|<span data-ttu-id="93246-147">Удаление существующей модели.</span><span class="sxs-lookup"><span data-stu-id="93246-147">Delete an existing model.</span></span>|[<span data-ttu-id="93246-148">Удаление модели (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="93246-148">Delete a Model &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-a-model-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="93246-149">См. также</span><span class="sxs-lookup"><span data-stu-id="93246-149">Related Content</span></span>  
  
-   [<span data-ttu-id="93246-150">Обзор Master Data Services</span><span class="sxs-lookup"><span data-stu-id="93246-150">Master Data Services Overview</span></span>](master-data-services-overview-mds.md)  
  
-   [<span data-ttu-id="93246-151">Сущности (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="93246-151">Entities &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/entities-master-data-services.md)  
  
-   [<span data-ttu-id="93246-152">Атрибуты (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="93246-152">Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/attributes-master-data-services.md)  
  
-   [<span data-ttu-id="93246-153">Развертывание моделей (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="93246-153">Deploying Models &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/deploying-models-master-data-services.md)  
  
-   [<span data-ttu-id="93246-154">Разрешения объекта модели (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="93246-154">Model Object Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/model-object-permissions-master-data-services.md)  
  
  
