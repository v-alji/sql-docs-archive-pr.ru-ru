---
title: Разрешения модели (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- models [Master Data Services], permissions
- permissions [Master Data Services], models
ms.assetid: 210f440b-2cc1-4c49-94b1-3a97e2af7bc3
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 2846918b515bba16d12d48cd7058cf25863bf569
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664297"
---
# <a name="model-permissions-master-data-services"></a><span data-ttu-id="7c37e-102">Разрешения модели (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="7c37e-102">Model Permissions (Master Data Services)</span></span>
  <span data-ttu-id="7c37e-103">Разрешения модели применяются ко всем сущностям, явным и производным иерархиям и коллекциям, существующим в модели.</span><span class="sxs-lookup"><span data-stu-id="7c37e-103">Model permissions apply to all entities, derived hierarchies, explicit hierarchies, and collections that exist within the model.</span></span> <span data-ttu-id="7c37e-104">Разрешения, назначенные для модели, можно переопределить для любого отдельного объекта.</span><span class="sxs-lookup"><span data-stu-id="7c37e-104">Permissions assigned to the model can be overridden for any individual object.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7c37e-105">Если пользователь является администратором модели, то модель отображается во всех функциональных областях пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="7c37e-105">If a user is a model administrator, the model is displayed in all functional areas of the user interface.</span></span> <span data-ttu-id="7c37e-106">В противном случае модель отображается только в функциональной области **Обозреватель** .</span><span class="sxs-lookup"><span data-stu-id="7c37e-106">Otherwise, the model is displayed in the **Explorer** functional area only.</span></span> <span data-ttu-id="7c37e-107">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="7c37e-107">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
|<span data-ttu-id="7c37e-108">Разрешение</span><span class="sxs-lookup"><span data-stu-id="7c37e-108">Permission</span></span>|<span data-ttu-id="7c37e-109">Описание</span><span class="sxs-lookup"><span data-stu-id="7c37e-109">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="7c37e-110">**Только для чтения**</span><span class="sxs-lookup"><span data-stu-id="7c37e-110">**Read-only**</span></span>|<span data-ttu-id="7c37e-111">В **обозревателе**эта модель отображается, но пользователь не может добавлять или удалять элементы, а также не может обновлять значения атрибутов, членства в иерархиях и членства в коллекциях.</span><span class="sxs-lookup"><span data-stu-id="7c37e-111">In **Explorer**, the model is displayed but the user cannot add or remove members, and cannot update attribute values, hierarchy memberships, or collection memberships.</span></span>|  
|<span data-ttu-id="7c37e-112">**Обновление**</span><span class="sxs-lookup"><span data-stu-id="7c37e-112">**Update**</span></span>|<span data-ttu-id="7c37e-113">В **обозревателе**отображается модель, и пользователь может добавлять и удалять элементы, обновлять значения атрибутов, членства в иерархии и членства в коллекциях.</span><span class="sxs-lookup"><span data-stu-id="7c37e-113">In **Explorer**, the model is displayed and the user can add and remove members, can update attribute values, hierarchy memberships, and collection memberships.</span></span>|  
|<span data-ttu-id="7c37e-114">**Запретить**</span><span class="sxs-lookup"><span data-stu-id="7c37e-114">**Deny**</span></span>|<span data-ttu-id="7c37e-115">Модель не отображается.</span><span class="sxs-lookup"><span data-stu-id="7c37e-115">The model is not displayed.</span></span>|  
  
 <span data-ttu-id="7c37e-116">При назначении разрешения модели пользователь получает доступ ко всем версиям модели.</span><span class="sxs-lookup"><span data-stu-id="7c37e-116">When you assign permission to a model, the user gets access to all versions of the model.</span></span> <span data-ttu-id="7c37e-117">Нельзя назначить разрешение для отдельной версии.</span><span class="sxs-lookup"><span data-stu-id="7c37e-117">You cannot assign permission to an individual version.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c37e-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="7c37e-118">See Also</span></span>  
 <span data-ttu-id="7c37e-119">[Назначение разрешений объекта модели &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="7c37e-119">[Assign Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="7c37e-120">[Разрешения объекта модели &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="7c37e-120">[Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="7c37e-121">[Разрешения сущности &#40;Master Data Services&#41;](../../2014/master-data-services/entity-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="7c37e-121">[Entity Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/entity-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="7c37e-122">Разрешения коллекции (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="7c37e-122">Collection Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/collection-permissions-master-data-services.md)  
  
  
