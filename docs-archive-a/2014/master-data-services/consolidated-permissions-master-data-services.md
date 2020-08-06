---
title: Объединенные разрешения (Master Data Services) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attributes [Master Data Services], consolidated member attribute permissions
- consolidated members [Master Data Services], attribute permissions
- permissions [Master Data Services], consolidated members
- members [Master Data Services], consolidated member permissions
ms.assetid: 084055a3-5fd3-43f3-b620-ac6afab42a3d
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c4c93e74acc84d6e742139263bedc011c4028efb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669457"
---
# <a name="consolidated-permissions-master-data-services"></a><span data-ttu-id="37222-102">Объединенные разрешения (службы основных данных)</span><span class="sxs-lookup"><span data-stu-id="37222-102">Consolidated Permissions (Master Data Services)</span></span>
  <span data-ttu-id="37222-103">Объединенные разрешения применяются к значениям атрибутов для всех консолидированных элементов сущности.</span><span class="sxs-lookup"><span data-stu-id="37222-103">Consolidated permissions apply to the attribute values for all consolidated members of an entity.</span></span>  
  
 <span data-ttu-id="37222-104">Объединенные разрешения применяются только к сущностям, разрешенным для явных иерархий и коллекций.</span><span class="sxs-lookup"><span data-stu-id="37222-104">Consolidated permissions apply only to entities that are enabled for explicit hierarchies and collections.</span></span>  
  
 <span data-ttu-id="37222-105">**Примечания.**</span><span class="sxs-lookup"><span data-stu-id="37222-105">**Notes:**</span></span>  
  
-   <span data-ttu-id="37222-106">Разрешения конечного элемента применяются только к функциональной области **Обозреватель** пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="37222-106">Leaf permissions apply to the **Explorer** functional area of the user interface only.</span></span>  
  
-   <span data-ttu-id="37222-107">Разрешения, назначенные для атрибутов **Имя** и **Код** , не применяются.</span><span class="sxs-lookup"><span data-stu-id="37222-107">Permissions assigned to **Name** and **Code** attributes are not enforced.</span></span>  
  
|<span data-ttu-id="37222-108">Разрешение</span><span class="sxs-lookup"><span data-stu-id="37222-108">Permission</span></span>|<span data-ttu-id="37222-109">Описание</span><span class="sxs-lookup"><span data-stu-id="37222-109">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="37222-110">**Только для чтения**</span><span class="sxs-lookup"><span data-stu-id="37222-110">**Read-only**</span></span>|<span data-ttu-id="37222-111">Консолидированные элементы отображаются, но пользователь не может добавлять, удалять или изменять их.</span><span class="sxs-lookup"><span data-stu-id="37222-111">Consolidated members are displayed but the user cannot add, remove, or change them.</span></span>|  
|<span data-ttu-id="37222-112">**Обновление**</span><span class="sxs-lookup"><span data-stu-id="37222-112">**Update**</span></span>|<span data-ttu-id="37222-113">Консолидированные элементы отображаются, и пользователь может добавлять, удалять и изменять их.</span><span class="sxs-lookup"><span data-stu-id="37222-113">Consolidated members are displayed and the user can add, remove, and change them.</span></span>|  
|<span data-ttu-id="37222-114">**Запретить**</span><span class="sxs-lookup"><span data-stu-id="37222-114">**Deny**</span></span>|<span data-ttu-id="37222-115">Консолидированные элементы для сущности не отображаются.</span><span class="sxs-lookup"><span data-stu-id="37222-115">Consolidated members for the entity are not displayed.</span></span>|  
  
## <a name="attribute-permissions"></a><span data-ttu-id="37222-116">Разрешения атрибута</span><span class="sxs-lookup"><span data-stu-id="37222-116">Attribute Permissions</span></span>  
 <span data-ttu-id="37222-117">Разрешения атрибута применимы только к значениям атрибута указанной сущности.</span><span class="sxs-lookup"><span data-stu-id="37222-117">Attribute permissions apply to the attribute's values for the specific entity.</span></span> <span data-ttu-id="37222-118">Пользователи с разрешениями только для атрибутов не могут добавлять или удалять элементы.</span><span class="sxs-lookup"><span data-stu-id="37222-118">Users with only attribute permissions cannot add or remove members.</span></span>  
  
|<span data-ttu-id="37222-119">Разрешение</span><span class="sxs-lookup"><span data-stu-id="37222-119">Permission</span></span>|<span data-ttu-id="37222-120">Описание</span><span class="sxs-lookup"><span data-stu-id="37222-120">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="37222-121">**Только для чтения**</span><span class="sxs-lookup"><span data-stu-id="37222-121">**Read-only**</span></span>|<span data-ttu-id="37222-122">Атрибут отображается, но пользователь не может изменить его значений.</span><span class="sxs-lookup"><span data-stu-id="37222-122">The attribute is displayed but the user cannot change attribute values.</span></span>|  
|<span data-ttu-id="37222-123">**Обновление**</span><span class="sxs-lookup"><span data-stu-id="37222-123">**Update**</span></span>|<span data-ttu-id="37222-124">Атрибут отображается, и пользователь может изменить его значения.</span><span class="sxs-lookup"><span data-stu-id="37222-124">The attribute is displayed and the user can change attribute values.</span></span>|  
|<span data-ttu-id="37222-125">**Запретить**</span><span class="sxs-lookup"><span data-stu-id="37222-125">**Deny**</span></span>|<span data-ttu-id="37222-126">Атрибут не отображается.</span><span class="sxs-lookup"><span data-stu-id="37222-126">The attribute is not displayed.</span></span><br /><br /> <span data-ttu-id="37222-127">Примечание. Нельзя явно запретить доступ к атрибутам "Имя" и "Код".</span><span class="sxs-lookup"><span data-stu-id="37222-127">Note: You cannot explicitly deny access to Name and Code attributes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="37222-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="37222-128">See Also</span></span>  
 <span data-ttu-id="37222-129">[Назначение разрешений объекта модели &#40;Master Data Services&#41;](assign-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="37222-129">[Assign Model Object Permissions &#40;Master Data Services&#41;](assign-model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="37222-130">[Конечные разрешения &#40;Master Data Services&#41;](../../2014/master-data-services/leaf-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="37222-130">[Leaf Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/leaf-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="37222-131">[Разрешения объекта модели &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="37222-131">[Model Object Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="37222-132">[Master Data Services &#40;членов&#41;](../../2014/master-data-services/members-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="37222-132">[Members &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) </span></span>  
 [<span data-ttu-id="37222-133">Атрибуты (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="37222-133">Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/attributes-master-data-services.md)  
  
  
