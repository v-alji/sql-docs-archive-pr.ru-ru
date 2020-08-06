---
title: Разрешения сущности (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- entities [Master Data Services], permissions
- permissions [Master Data Services], entities
ms.assetid: 22785062-4faf-46ee-bffa-01cbd6d5a5b3
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: eaec809cb0f9dea3f760958bcf95015edd5a490e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728385"
---
# <a name="entity-permissions-master-data-services"></a><span data-ttu-id="e448f-102">Разрешения сущности (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="e448f-102">Entity Permissions (Master Data Services)</span></span>
  <span data-ttu-id="e448f-103">Разрешения сущности применяются:</span><span class="sxs-lookup"><span data-stu-id="e448f-103">Entity permissions apply to:</span></span>  
  
-   <span data-ttu-id="e448f-104">ко всем атрибутам сущности, в том числе к атрибутам **Имя** и **Code**, для конечных и для консолидированных элементов;</span><span class="sxs-lookup"><span data-stu-id="e448f-104">All of the entity's attributes, including **Name** and **Code**, for both leaf and consolidated members.</span></span>  
  
-   <span data-ttu-id="e448f-105">ко всем коллекциям сущности;</span><span class="sxs-lookup"><span data-stu-id="e448f-105">All of the entity's collections.</span></span>  
  
-   <span data-ttu-id="e448f-106">к членству и связям явной иерархии.</span><span class="sxs-lookup"><span data-stu-id="e448f-106">Explicit hierarchy memberships and relationships.</span></span>  
  
 <span data-ttu-id="e448f-107">При наличии разрешения для сущности пользователь может добавлять и удалять элементы из сущности, ее явных иерархий и коллекций.</span><span class="sxs-lookup"><span data-stu-id="e448f-107">When you have permission to an entity, you can add and remove members from the entity, its explicit hierarchies, and its collections.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e448f-108">Эти разрешения применяются только к функциональной области **Обозреватель** пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="e448f-108">These permissions apply to the **Explorer** functional area of the user interface only.</span></span>  
  
|<span data-ttu-id="e448f-109">Разрешение</span><span class="sxs-lookup"><span data-stu-id="e448f-109">Permission</span></span>|<span data-ttu-id="e448f-110">Описание</span><span class="sxs-lookup"><span data-stu-id="e448f-110">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="e448f-111">**Только для чтения**</span><span class="sxs-lookup"><span data-stu-id="e448f-111">**Read-only**</span></span>|<span data-ttu-id="e448f-112">Сущность отображается, но пользователь не может добавлять, удалять или изменять элементы.</span><span class="sxs-lookup"><span data-stu-id="e448f-112">The entity is displayed but the user cannot add, remove, or change members.</span></span>|  
|<span data-ttu-id="e448f-113">**Обновление**</span><span class="sxs-lookup"><span data-stu-id="e448f-113">**Update**</span></span>|<span data-ttu-id="e448f-114">Сущность отображается, пользователь может добавлять, удалять и изменять элементы.</span><span class="sxs-lookup"><span data-stu-id="e448f-114">The entity is displayed and the user can add, remove, and change members.</span></span>|  
|<span data-ttu-id="e448f-115">**Запретить**</span><span class="sxs-lookup"><span data-stu-id="e448f-115">**Deny**</span></span>|<span data-ttu-id="e448f-116">Сущность не отображается.</span><span class="sxs-lookup"><span data-stu-id="e448f-116">The entity is not displayed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e448f-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="e448f-117">See Also</span></span>  
 <span data-ttu-id="e448f-118">[Назначение разрешений объекта модели &#40;Master Data Services&#41;](assign-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="e448f-118">[Assign Model Object Permissions &#40;Master Data Services&#41;](assign-model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="e448f-119">[Разрешения объекта модели &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="e448f-119">[Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="e448f-120">Сущности (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="e448f-120">Entities &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/entities-master-data-services.md)  
  
  
