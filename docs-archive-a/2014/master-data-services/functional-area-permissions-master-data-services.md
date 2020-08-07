---
title: Разрешения функциональной области (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- functional area permissions [Master Data Services], about functional area permissions
- functional area permissions [Master Data Services]
- permissions [Master Data Services], functional areas
ms.assetid: a80b87b3-b904-4cda-8582-0761c2617c57
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 3f1f2639f83f63c135daab2214614e93c3926d3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731822"
---
# <a name="functional-area-permissions-master-data-services"></a><span data-ttu-id="9242c-102">Разрешения функциональной области (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="9242c-102">Functional Area Permissions (Master Data Services)</span></span>
  <span data-ttu-id="9242c-103">Разрешения можно назначать функциональным областям пользовательского интерфейса [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9242c-103">You can assign permission to each of the functional areas of the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] user interface (UI).</span></span> <span data-ttu-id="9242c-104">Существует пять функциональных областей:</span><span class="sxs-lookup"><span data-stu-id="9242c-104">There are five functional areas:</span></span>  
  
-   <span data-ttu-id="9242c-105">**Обозреватель**</span><span class="sxs-lookup"><span data-stu-id="9242c-105">**Explorer**</span></span>  
  
-   <span data-ttu-id="9242c-106">**Управление версиями**</span><span class="sxs-lookup"><span data-stu-id="9242c-106">**Version Management**</span></span>  
  
-   <span data-ttu-id="9242c-107">**Управление интеграцией**</span><span class="sxs-lookup"><span data-stu-id="9242c-107">**Integration Management**</span></span>  
  
-   <span data-ttu-id="9242c-108">**Системное администрирование**</span><span class="sxs-lookup"><span data-stu-id="9242c-108">**System Administration**</span></span>  
  
-   <span data-ttu-id="9242c-109">**Разрешения пользователей и групп**</span><span class="sxs-lookup"><span data-stu-id="9242c-109">**User and Group Permissions**</span></span>  
  
 <span data-ttu-id="9242c-110">Если предоставляется разрешение на работу в функциональной области, эта область пользовательского интерфейса становится видимой для пользователя или группы.</span><span class="sxs-lookup"><span data-stu-id="9242c-110">When you assign permission to a functional area, you are making an area of the UI visible to the user or group.</span></span>  
  
 <span data-ttu-id="9242c-111">Внутри функциональной области **Обозреватель** дополнительные разрешения на объекты модели и члены иерархии определяют, какие данные доступны пользователю.</span><span class="sxs-lookup"><span data-stu-id="9242c-111">Within the **Explorer** functional area, additional permissions assigned to model objects and hierarchy members determine which data a user can access.</span></span> <span data-ttu-id="9242c-112">В остальных функциональных областях пользователь должен быть администратором модели, чтобы просматривать или использовать модель.</span><span class="sxs-lookup"><span data-stu-id="9242c-112">Within all other functional areas, a user must be a model administrator to view a model and act on it.</span></span> <span data-ttu-id="9242c-113">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="9242c-113">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
 <span data-ttu-id="9242c-114">Чтобы иметь доступ к **, пользователь или группа должны иметь разрешение хотя бы для одной функциональной области и одной модели на вкладке** Модели [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9242c-114">A user or group must have permission to at least one functional area and one model on the **Models** tab in order to access [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9242c-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="9242c-115">See Also</span></span>  
 <span data-ttu-id="9242c-116">[Назначение разрешений функциональной области &#40;Master Data Services&#41;](../../2014/master-data-services/assign-functional-area-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="9242c-116">[Assign Functional Area Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/assign-functional-area-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="9242c-117">[Разрешения объекта модели &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="9242c-117">[Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="9242c-118">[Разрешения элемента иерархии &#40;Master Data Services&#41;](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="9242c-118">[Hierarchy Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="9242c-119">Способ определения разрешений (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="9242c-119">How Permissions Are Determined &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/how-permissions-are-determined-master-data-services.md)  
  
  
