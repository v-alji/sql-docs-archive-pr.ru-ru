---
title: Экспорт данных (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- exporting data [Master Data Services]
- subscription views [Master Data Services]
- subscription views [Master Data Services], about subscription views
ms.assetid: 8b74409a-ea70-45f8-84c7-da6905e4901a
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: edae5b996c25a1b6053231ed2f69ef511b9fbfa6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664295"
---
# <a name="exporting-data-master-data-services"></a><span data-ttu-id="61c2b-102">Экспорт данных (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="61c2b-102">Exporting Data (Master Data Services)</span></span>
  <span data-ttu-id="61c2b-103">Можно экспортировать данные [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] в системы-подписчики путем создания представлений подписки.</span><span class="sxs-lookup"><span data-stu-id="61c2b-103">You can export [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] data to subscribing systems by creating subscriptions views.</span></span> <span data-ttu-id="61c2b-104">После этого любая система-подписчик может просматривать опубликованные данные в базе данных [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="61c2b-104">Any subscribing system can then view the published data in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="61c2b-105">Дополнительные сведения о представлениях см. в разделе [Представления](../relational-databases/views/views.md).</span><span class="sxs-lookup"><span data-stu-id="61c2b-105">For more information about views, see [Views](../relational-databases/views/views.md).</span></span>  
  
## <a name="subscription-view-formats"></a><span data-ttu-id="61c2b-106">Форматы представлений подписки</span><span class="sxs-lookup"><span data-stu-id="61c2b-106">Subscription View Formats</span></span>  
 <span data-ttu-id="61c2b-107">При создании представления [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]на выбор предлагается набор стандартных форматов представлений, предоставляемых службами [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="61c2b-107">When you create a view in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], you choose from a set of standard view formats that [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] provides.</span></span> <span data-ttu-id="61c2b-108">Эти форматы используются для создания представлений, которые содержат:</span><span class="sxs-lookup"><span data-stu-id="61c2b-108">You can use these formats to create views that show:</span></span>  
  
-   <span data-ttu-id="61c2b-109">все конечные элементы и их атрибуты;</span><span class="sxs-lookup"><span data-stu-id="61c2b-109">All leaf members and their attributes.</span></span>  
  
-   <span data-ttu-id="61c2b-110">все консолидированные элементы и их атрибуты;</span><span class="sxs-lookup"><span data-stu-id="61c2b-110">All consolidated members and their attributes.</span></span>  
  
-   <span data-ttu-id="61c2b-111">все коллекции и их атрибуты;</span><span class="sxs-lookup"><span data-stu-id="61c2b-111">All collections and their attributes.</span></span>  
  
-   <span data-ttu-id="61c2b-112">элементы, явно добавленные в коллекцию;</span><span class="sxs-lookup"><span data-stu-id="61c2b-112">The members explicitly added to a collection.</span></span>  
  
-   <span data-ttu-id="61c2b-113">элементы в производной иерархии многоуровневого типа или типа «родители-потомки»;</span><span class="sxs-lookup"><span data-stu-id="61c2b-113">The members in a derived hierarchy, in either a parent child or level format.</span></span>  
  
-   <span data-ttu-id="61c2b-114">элементы во всех явных иерархиях многоуровневого типа или типа «родители-потомки» для сущности.</span><span class="sxs-lookup"><span data-stu-id="61c2b-114">The members in all explicit hierarchies for an entity, in either a parent child or level format.</span></span>  
  
## <a name="subscription-views-can-become-out-of-date"></a><span data-ttu-id="61c2b-115">Представления подписки могут устаревать</span><span class="sxs-lookup"><span data-stu-id="61c2b-115">Subscription Views Can Become Out-of-Date</span></span>  
 <span data-ttu-id="61c2b-116">После создания представления подписки для сущности или иерархии изменения связанных объектов модели не будут автоматически отображаться в представлении.</span><span class="sxs-lookup"><span data-stu-id="61c2b-116">After you create a subscription view for an entity or hierarchy, changes to the associated model objects are not automatically reflected in the view.</span></span> <span data-ttu-id="61c2b-117">Может потребоваться повторное создание представления подписки в [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , чтобы в ней отразились изменения в объектах модели.</span><span class="sxs-lookup"><span data-stu-id="61c2b-117">You might need to regenerate a subscription view in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] to reflect changes to model objects.</span></span> <span data-ttu-id="61c2b-118">При изменении объектов модели значение в столбце **Изменено** на странице **Экспорт** меняется на **True** .</span><span class="sxs-lookup"><span data-stu-id="61c2b-118">The **Changed** column on the **Export** page is updated to **True** when model objects change.</span></span> <span data-ttu-id="61c2b-119">Значение**True** указывает на необходимость изменить представление подписки и сохранить его, после чего оно будет создано повторно.</span><span class="sxs-lookup"><span data-stu-id="61c2b-119">**True** indicates that you should edit the subscription view and save it, which regenerates the view.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="61c2b-120">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="61c2b-120">Related Tasks</span></span>  
  
|<span data-ttu-id="61c2b-121">Описание задачи</span><span class="sxs-lookup"><span data-stu-id="61c2b-121">Task Description</span></span>|<span data-ttu-id="61c2b-122">Раздел</span><span class="sxs-lookup"><span data-stu-id="61c2b-122">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="61c2b-123">Создание представления подписки основных данных.</span><span class="sxs-lookup"><span data-stu-id="61c2b-123">Create a subscription view of your master data.</span></span>|[<span data-ttu-id="61c2b-124">Создание представления подписки &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="61c2b-124">Create a Subscription View &#40;Master Data Services&#41;</span></span>](create-a-subscription-view-to-export-data-master-data-services.md)|  
|<span data-ttu-id="61c2b-125">Удаление существующих представлений подписки.</span><span class="sxs-lookup"><span data-stu-id="61c2b-125">Delete an existing subscription view.</span></span>|[<span data-ttu-id="61c2b-126">Удаление представления подписки (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="61c2b-126">Delete a Subscription View &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-a-subscription-view-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="61c2b-127">См. также</span><span class="sxs-lookup"><span data-stu-id="61c2b-127">Related Content</span></span>  
  
-   [<span data-ttu-id="61c2b-128">Форматы представления подписки (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="61c2b-128">Subscription View Formats &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/subscription-view-formats-master-data-services.md)  
  
-   [<span data-ttu-id="61c2b-129">Представления</span><span class="sxs-lookup"><span data-stu-id="61c2b-129">Views</span></span>](../relational-databases/views/views.md)  
  
  
