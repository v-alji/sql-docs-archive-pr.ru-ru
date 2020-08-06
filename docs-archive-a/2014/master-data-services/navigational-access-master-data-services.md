---
title: Навигационный доступ (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- navigational access [Master Data Services]
- security [Master Data Services], navigational access
ms.assetid: 3403b7b0-44e2-48c3-a1b7-9c4612b874b8
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 7af3c16d98320b6fea3d4611e9e4c6d37c6015bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654371"
---
# <a name="navigational-access-master-data-services"></a><span data-ttu-id="58b5d-102">Навигационный доступ (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="58b5d-102">Navigational Access (Master Data Services)</span></span>
  <span data-ttu-id="58b5d-103">Навигационный доступ применяется к модели объекта безопасности, которая назначается на вкладке **Модель** .</span><span class="sxs-lookup"><span data-stu-id="58b5d-103">Navigational access applies to model object security, which is assigned on the **Models** tab.</span></span>  
  
 <span data-ttu-id="58b5d-104">Навигационный доступ — это доступ к уровням выше того, который был назначен системой безопасности.</span><span class="sxs-lookup"><span data-stu-id="58b5d-104">Navigational access is the access you get to levels higher than where you've assigned security.</span></span>  
  
 <span data-ttu-id="58b5d-105">В этом примере разрешения назначаются на сущность, поэтому навигационный доступ предоставляется на уровне модели.</span><span class="sxs-lookup"><span data-stu-id="58b5d-105">In this example, permissions are assigned to an entity, and so navigational access is granted at the model level.</span></span>  
  
 <span data-ttu-id="58b5d-106">![mds_conc_inheritance_model](../../2014/master-data-services/media/mds-conc-inheritance-model.gif "mds_conc_inheritance_model")</span><span class="sxs-lookup"><span data-stu-id="58b5d-106">![mds_conc_inheritance_model](../../2014/master-data-services/media/mds-conc-inheritance-model.gif "mds_conc_inheritance_model")</span></span>  
  
 <span data-ttu-id="58b5d-107">**Сущности**</span><span class="sxs-lookup"><span data-stu-id="58b5d-107">**Entities**</span></span>  
  
 <span data-ttu-id="58b5d-108">При назначении разрешения на сущность, ее конечные или консолидированные элементы, навигационный доступ означает возможность чтения и обновления имени и кода для всех элементов.</span><span class="sxs-lookup"><span data-stu-id="58b5d-108">When you assign permission to an entity, its leaf members, or its consolidated members, navigational access means you can read or update the name and code for all members.</span></span> <span data-ttu-id="58b5d-109">Предоставляется также возможность считывать имя модели.</span><span class="sxs-lookup"><span data-stu-id="58b5d-109">You can also read the model name.</span></span>  
  
 <span data-ttu-id="58b5d-110">**Атрибуты**</span><span class="sxs-lookup"><span data-stu-id="58b5d-110">**Attributes**</span></span>  
  
 <span data-ttu-id="58b5d-111">При назначении разрешения на атрибут навигационный доступ означает возможность чтения и обновления имени и кода для всех элементов сущности.</span><span class="sxs-lookup"><span data-stu-id="58b5d-111">When you assign permission to an attribute, navigational access means you can read or update the name and code for all members in the entity.</span></span> <span data-ttu-id="58b5d-112">Предоставляется также возможность считывать имя модели.</span><span class="sxs-lookup"><span data-stu-id="58b5d-112">You can also read the model name.</span></span>  
  
 <span data-ttu-id="58b5d-113">**Коллекции**</span><span class="sxs-lookup"><span data-stu-id="58b5d-113">**Collections**</span></span>  
  
 <span data-ttu-id="58b5d-114">При назначении разрешений на коллекции это будет возможность чтения и обновления имени, кода, описания и идентификатора владельца.</span><span class="sxs-lookup"><span data-stu-id="58b5d-114">When you assign permissions to collections, you can read or update the name, code, description and owner ID.</span></span> <span data-ttu-id="58b5d-115">Предоставляется также возможность считывать имя модели.</span><span class="sxs-lookup"><span data-stu-id="58b5d-115">You can also read the model name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58b5d-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="58b5d-116">See Also</span></span>  
 [<span data-ttu-id="58b5d-117">Способ определения разрешений (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="58b5d-117">How Permissions Are Determined &#40;Master Data Services&#41;</span></span>](how-permissions-are-determined-master-data-services.md)  
  
  
