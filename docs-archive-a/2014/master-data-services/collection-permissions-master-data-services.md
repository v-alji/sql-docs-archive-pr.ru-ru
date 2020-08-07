---
title: Разрешения коллекции (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- collections [Master Data Services], permissions
- permissions [Master Data Services], collections
ms.assetid: 703e1bf5-4b4b-4830-8a5b-f979b09f677d
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: a47c6937ace51d20986ccf04bb7d1f39fed9954c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732725"
---
# <a name="collection-permissions-master-data-services"></a><span data-ttu-id="e972c-102">Разрешения коллекции (службы основных данных)</span><span class="sxs-lookup"><span data-stu-id="e972c-102">Collection Permissions (Master Data Services)</span></span>
  <span data-ttu-id="e972c-103">Разрешения коллекции применяются ко всем коллекциям для сущности.</span><span class="sxs-lookup"><span data-stu-id="e972c-103">Collection permissions apply to all collections for an entity.</span></span> <span data-ttu-id="e972c-104">Нельзя назначить разрешение конкретной коллекции. Разрешения применяются ко всем коллекциям.</span><span class="sxs-lookup"><span data-stu-id="e972c-104">You cannot give permission to a specific collection; permissions apply to all collections.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e972c-105">Эти разрешения применяются только к функциональной области **Обозреватель** пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="e972c-105">These permissions apply to the **Explorer** functional area of the user interface only.</span></span>  
  
|<span data-ttu-id="e972c-106">Разрешение</span><span class="sxs-lookup"><span data-stu-id="e972c-106">Permission</span></span>|<span data-ttu-id="e972c-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e972c-107">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="e972c-108">**Только для чтения**</span><span class="sxs-lookup"><span data-stu-id="e972c-108">**Read-only**</span></span>|<span data-ttu-id="e972c-109">Отображаются все коллекции и элементы коллекции.</span><span class="sxs-lookup"><span data-stu-id="e972c-109">All collections and collection members are displayed.</span></span><br /><br /> <span data-ttu-id="e972c-110">Пользователь не может добавлять или удалять коллекции и не может добавлять элементы в коллекцию или удалять элементы из нее.</span><span class="sxs-lookup"><span data-stu-id="e972c-110">The user cannot add or remove collections, and cannot add members to the collection or remove members from it.</span></span>|  
|<span data-ttu-id="e972c-111">**Обновление**</span><span class="sxs-lookup"><span data-stu-id="e972c-111">**Update**</span></span>|<span data-ttu-id="e972c-112">Отображаются все коллекции, и пользователь может добавлять и удалять коллекции.</span><span class="sxs-lookup"><span data-stu-id="e972c-112">All collections are displayed and the user can add and remove collections.</span></span><br /><br /> <span data-ttu-id="e972c-113">Пользователь также может добавлять и удалять элементы из коллекции.</span><span class="sxs-lookup"><span data-stu-id="e972c-113">The user can also add and remove members from the collection.</span></span>|  
|<span data-ttu-id="e972c-114">**Запретить**</span><span class="sxs-lookup"><span data-stu-id="e972c-114">**Deny**</span></span>|<span data-ttu-id="e972c-115">Для сущности не отображается ни одна коллекция.</span><span class="sxs-lookup"><span data-stu-id="e972c-115">All collections for the entity are not displayed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e972c-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="e972c-116">See Also</span></span>  
 <span data-ttu-id="e972c-117">[Назначение разрешений объекта модели &#40;Master Data Services&#41;](assign-model-object-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="e972c-117">[Assign Model Object Permissions &#40;Master Data Services&#41;](assign-model-object-permissions-master-data-services.md) </span></span>  
 <span data-ttu-id="e972c-118">[&#40;коллекций Master Data Services&#41;](../../2014/master-data-services/collections-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="e972c-118">[Collections &#40;Master Data Services&#41;](../../2014/master-data-services/collections-master-data-services.md) </span></span>  
 [<span data-ttu-id="e972c-119">Разрешения объекта модели (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="e972c-119">Model Object Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/model-object-permissions-master-data-services.md)  
  
  
