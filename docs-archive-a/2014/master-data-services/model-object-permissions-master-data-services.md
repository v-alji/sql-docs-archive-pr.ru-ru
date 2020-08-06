---
title: Разрешения объекта модели (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- permissions [Master Data Services], model objects
- models [Master Data Services], object permissions
ms.assetid: fab6335b-4cae-47de-ae7c-6c4743e0680f
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 4cc64d753b680cfabc3707a29c6d9de631708c20
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667762"
---
# <a name="model-object-permissions-master-data-services"></a><span data-ttu-id="d97f7-102">Разрешения объекта модели (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="d97f7-102">Model Object Permissions (Master Data Services)</span></span>
  <span data-ttu-id="d97f7-103">Разрешения объекта модели являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="d97f7-103">Model object permissions are mandatory.</span></span> <span data-ttu-id="d97f7-104">Они определяют атрибуты, к которым пользователь может получить доступ в функциональной области **Обозреватель** пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="d97f7-104">They determine the attributes a user can access in the **Explorer** functional area of the UI.</span></span>  
  
 <span data-ttu-id="d97f7-105">Например, если пользователь имеет разрешение **Обновление** в сущности «Продукт», то пользователь может обновлять все атрибуты этой сущности.</span><span class="sxs-lookup"><span data-stu-id="d97f7-105">For example, if you assign a user **Update** permission to the Product entity, the user can update all of the attributes of the Product entity.</span></span> <span data-ttu-id="d97f7-106">Если назначено разрешение **Обновление** для одного атрибута, то пользователь может обновлять только этот атрибут.</span><span class="sxs-lookup"><span data-stu-id="d97f7-106">If you assign **Update** permission to a single attribute, the user can update that attribute only.</span></span>  
  
 <span data-ttu-id="d97f7-107">Для определения безопасности, назначенной каждому индивидуальному значению атрибута, разрешения объектов модели можно сочетать с разрешениями элементов иерархии, к которым пользователь может получить доступ.</span><span class="sxs-lookup"><span data-stu-id="d97f7-107">To determine security assigned on each individual attribute value, model object permissions are combined with hierarchy member permissions, which determine the members a user can access.</span></span>  
  
 <span data-ttu-id="d97f7-108">Чтобы предоставить пользователю доступ к функциональной области, отличной от **Explorer**, пользователь должен быть администратором модели, который также включает в себя назначение разрешений на объекты модели.</span><span class="sxs-lookup"><span data-stu-id="d97f7-108">To give a user access to a functional area other than **Explorer**, the user must be a model administrator, which also involves assigning model object permissions.</span></span> <span data-ttu-id="d97f7-109">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d97f7-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
 <span data-ttu-id="d97f7-110">Разрешения объекта модели назначаются в [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] пользовательском интерфейсе в функциональной области **разрешения пользователей и групп** на вкладке **модели** . На этой вкладке Модель представлена в виде древовидной структуры.</span><span class="sxs-lookup"><span data-stu-id="d97f7-110">Model object permissions are assigned in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] user interface (UI), in the **User and Group Permissions** functional area on the **Models** tab. On this tab, the model is represented as a tree structure.</span></span> <span data-ttu-id="d97f7-111">При назначении разрешения для объекта дерева это разрешение наследуют все объекты, находящиеся ниже данного узла.</span><span class="sxs-lookup"><span data-stu-id="d97f7-111">When you assign permission to an object in the tree, all objects below inherit that permission.</span></span> <span data-ttu-id="d97f7-112">Чтобы переопределить наследование разрешений, нужно назначить разрешение отдельным объектам.</span><span class="sxs-lookup"><span data-stu-id="d97f7-112">You can override that inheritance by assigning permission to individual objects.</span></span>  
  
 <span data-ttu-id="d97f7-113">Разрешение на доступ к объектам модели можно назначить **только для чтения**, **обновления**или **запрета** .</span><span class="sxs-lookup"><span data-stu-id="d97f7-113">You can assign **Read-only**, **Update**, or **Deny** permission to model objects.</span></span> <span data-ttu-id="d97f7-114">Если на вкладке **Модели** не будут назначены никакие разрешения, то пользователь не сможет просматривать модели и данные в среде [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d97f7-114">If you do not assign any permissions on the **Models** tab, the user cannot view any models or data in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
## <a name="best-practice"></a><span data-ttu-id="d97f7-115">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="d97f7-115">Best Practice</span></span>  
 <span data-ttu-id="d97f7-116">В общем случае следует назначить разрешение **Update** объекту модели, а затем явным образом назначить разрешение для объектов под ним.</span><span class="sxs-lookup"><span data-stu-id="d97f7-116">In general, you should assign **Update** permission to the model object, and then explicitly assign permission to objects underneath.</span></span> <span data-ttu-id="d97f7-117">Если объектам на нижнем уровне не назначить разрешение, то разрешения будут унаследованы, а пользователь станет администратором.</span><span class="sxs-lookup"><span data-stu-id="d97f7-117">If you do not assign permission to objects underneath, the permissions are inherited and the user is an administrator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d97f7-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="d97f7-118">See Also</span></span>  
 <span data-ttu-id="d97f7-119">[Назначение разрешений объекта модели &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="d97f7-119">[Assign Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="d97f7-120">[Разрешения модели &#40;Master Data Services&#41;](../../2014/master-data-services/model-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="d97f7-120">[Model Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="d97f7-121">[Разрешения функциональной области &#40;Master Data Services&#41;](../../2014/master-data-services/functional-area-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="d97f7-121">[Functional Area Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/functional-area-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="d97f7-122">[Разрешения элемента иерархии &#40;Master Data Services&#41;](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="d97f7-122">[Hierarchy Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="d97f7-123">Способ определения разрешений (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="d97f7-123">How Permissions Are Determined &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/how-permissions-are-determined-master-data-services.md)  
  
  
