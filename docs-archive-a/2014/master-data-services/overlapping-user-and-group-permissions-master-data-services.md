---
title: Перекрытие разрешений пользователей и групп (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- users [Master Data Services], resolving permissions
- permissions [Master Data Services], user and group overlaps
- groups [Master Data Services], resolving permissions
ms.assetid: 31c3cf7d-17d4-4474-b6a7-ffcb9fc45b37
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 7044bf6260170cbc598719ec204ddb6f861f6301
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730781"
---
# <a name="overlapping-user-and-group-permissions-master-data-services"></a><span data-ttu-id="f3a00-102">Перекрытие разрешений пользователей и групп (службы основных данных)</span><span class="sxs-lookup"><span data-stu-id="f3a00-102">Overlapping User and Group Permissions (Master Data Services)</span></span>
  <span data-ttu-id="f3a00-103">Разрешения пользователя основаны:</span><span class="sxs-lookup"><span data-stu-id="f3a00-103">A user's permissions are based on:</span></span>  
  
-   <span data-ttu-id="f3a00-104">Разрешения, унаследованные от членства в группах.</span><span class="sxs-lookup"><span data-stu-id="f3a00-104">Permissions from group memberships.</span></span>  
  
-   <span data-ttu-id="f3a00-105">разрешениях, явно назначенных пользователю.</span><span class="sxs-lookup"><span data-stu-id="f3a00-105">Permissions assigned explicitly to the user.</span></span>  
  
 <span data-ttu-id="f3a00-106">Если пользователь является членом нескольких групп и эти группы имеют доступ к диспетчеру основных данных, то применяются следующие правила.</span><span class="sxs-lookup"><span data-stu-id="f3a00-106">If a user is a member of multiple groups, and those groups have access to Master Data Manager, the following rules apply:</span></span>  
  
-   <span data-ttu-id="f3a00-107">**Запретить** переопределяет все остальные разрешения.</span><span class="sxs-lookup"><span data-stu-id="f3a00-107">**Deny** overrides all other permissions.</span></span>  
  
-   <span data-ttu-id="f3a00-108">**Обновление** переопределяет **только чтение**.</span><span class="sxs-lookup"><span data-stu-id="f3a00-108">**Update** overrides **Read-only**.</span></span>  
  
 <span data-ttu-id="f3a00-109">Эти правила применяются к вкладкам **Модели** и **Элементы иерархии** .</span><span class="sxs-lookup"><span data-stu-id="f3a00-109">These rules apply to both the **Models** and **Hierarchy Members** tabs.</span></span> <span data-ttu-id="f3a00-110">Разрешения определяются для каждой вкладки, после чего объединяются.</span><span class="sxs-lookup"><span data-stu-id="f3a00-110">Permissions are resolved for each tab and then combined.</span></span> <span data-ttu-id="f3a00-111">Дополнительные сведения см. в разделе [Способ определения разрешений (службы Master Data Services)](how-permissions-are-determined-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="f3a00-111">For more information, see [How Permissions Are Determined &#40;Master Data Services&#41;](how-permissions-are-determined-master-data-services.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f3a00-112">Просмотреть разрешение перекрытия разрешений пользователя и группы можно в пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="f3a00-112">You can view the resolution of user and group overlapping permissions in the user interface.</span></span> <span data-ttu-id="f3a00-113">На вкладках **Модели** и **Элементы иерархии** есть раскрывающийся список, в котором можно выбрать **Действующие** для просмотра действующих разрешений.</span><span class="sxs-lookup"><span data-stu-id="f3a00-113">Both the **Models** and **Hierarchy Members** tab have a drop-down list from which you can choose **Effective** to view effective permissions.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="f3a00-114">Пример 1</span><span class="sxs-lookup"><span data-stu-id="f3a00-114">Example 1</span></span>  
 <span data-ttu-id="f3a00-115">![mds_conc_user_group_ex_1](../../2014/master-data-services/media/mds-conc-user-group-ex-1.gif "mds_conc_user_group_ex_1")</span><span class="sxs-lookup"><span data-stu-id="f3a00-115">![mds_conc_user_group_ex_1](../../2014/master-data-services/media/mds-conc-user-group-ex-1.gif "mds_conc_user_group_ex_1")</span></span>  
  
 <span data-ttu-id="f3a00-116">Пользователь принадлежит к группе 1 и группе 2.</span><span class="sxs-lookup"><span data-stu-id="f3a00-116">The user belongs to Group 1 and Group 2.</span></span>  
  
 <span data-ttu-id="f3a00-117">Пользователь имеет разрешение **только на чтение** сущности Product.</span><span class="sxs-lookup"><span data-stu-id="f3a00-117">The user has **Read-only** permission to the Product entity.</span></span>  
  
 <span data-ttu-id="f3a00-118">Группа 1 имеет разрешение **Обновить** для сущности Product.</span><span class="sxs-lookup"><span data-stu-id="f3a00-118">Group 1 has **Update** permission to the Product entity.</span></span>  
  
 <span data-ttu-id="f3a00-119">Группа 2 имеет разрешение **только на чтение** сущности Product.</span><span class="sxs-lookup"><span data-stu-id="f3a00-119">Group 2 has **Read-only** permission to the Product entity.</span></span>  
  
 <span data-ttu-id="f3a00-120">Результат: действующим разрешением пользователя для сущности Product будет **Обновить** .</span><span class="sxs-lookup"><span data-stu-id="f3a00-120">Result: The user's effective permission is **Update** to the Product entity.</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="f3a00-121">Пример 2</span><span class="sxs-lookup"><span data-stu-id="f3a00-121">Example 2</span></span>  
 <span data-ttu-id="f3a00-122">![mds_conc_user_group_ex_2](../../2014/master-data-services/media/mds-conc-user-group-ex-2.gif "mds_conc_user_group_ex_2")</span><span class="sxs-lookup"><span data-stu-id="f3a00-122">![mds_conc_user_group_ex_2](../../2014/master-data-services/media/mds-conc-user-group-ex-2.gif "mds_conc_user_group_ex_2")</span></span>  
  
 <span data-ttu-id="f3a00-123">Пользователь принадлежит к группе 1 и группе 2.</span><span class="sxs-lookup"><span data-stu-id="f3a00-123">The user belongs to Group 1 and Group 2.</span></span>  
  
 <span data-ttu-id="f3a00-124">Пользователь имеет разрешение **только на чтение** сущности Product.</span><span class="sxs-lookup"><span data-stu-id="f3a00-124">The user has **Read-only** permission to the Product entity.</span></span>  
  
 <span data-ttu-id="f3a00-125">Группа 1 имеет разрешение **Обновить** для сущности Product.</span><span class="sxs-lookup"><span data-stu-id="f3a00-125">Group 1 has **Update** permission to Product entity.</span></span>  
  
 <span data-ttu-id="f3a00-126">Группа 2 имеет разрешение **Запретить** для сущности Product.</span><span class="sxs-lookup"><span data-stu-id="f3a00-126">Group 2 has **Deny** permission to the Product entity.</span></span>  
  
 <span data-ttu-id="f3a00-127">Результат: действующим разрешением пользователя для сущности Product будет **Запретить** .</span><span class="sxs-lookup"><span data-stu-id="f3a00-127">Result: The user's effective permission is **Deny** to the Product entity.</span></span>  
  
## <a name="example-3"></a><span data-ttu-id="f3a00-128">Пример 3</span><span class="sxs-lookup"><span data-stu-id="f3a00-128">Example 3</span></span>  
 <span data-ttu-id="f3a00-129">![mds_conc_user_group_ex_3](../../2014/master-data-services/media/mds-conc-user-group-ex-3.gif "mds_conc_user_group_ex_3")</span><span class="sxs-lookup"><span data-stu-id="f3a00-129">![mds_conc_user_group_ex_3](../../2014/master-data-services/media/mds-conc-user-group-ex-3.gif "mds_conc_user_group_ex_3")</span></span>  
  
 <span data-ttu-id="f3a00-130">Пользователь принадлежит к группе 1 и группе 2.</span><span class="sxs-lookup"><span data-stu-id="f3a00-130">The user belongs to Group 1 and Group 2.</span></span>  
  
 <span data-ttu-id="f3a00-131">Пользователь имеет разрешение **Обновить** для группы элементов в узле иерархии.</span><span class="sxs-lookup"><span data-stu-id="f3a00-131">The user has **Update** permission to a group of members in a hierarchy node.</span></span>  
  
 <span data-ttu-id="f3a00-132">Группа 1 имеет разрешение **только на чтение** для группы элементов в узле иерархии.</span><span class="sxs-lookup"><span data-stu-id="f3a00-132">Group 1 has **Read-only** permission to a group of members in a hierarchy node.</span></span>  
  
 <span data-ttu-id="f3a00-133">Группа 2 имеет разрешение **только на чтение** для группы элементов в узле иерархии.</span><span class="sxs-lookup"><span data-stu-id="f3a00-133">Group 2 has **Read-only** permission to a group of members in a hierarchy node.</span></span>  
  
 <span data-ttu-id="f3a00-134">Результат: действующее разрешение пользователя для элементов — **Обновить** .</span><span class="sxs-lookup"><span data-stu-id="f3a00-134">Result: The user's effective permission is **Update** to the members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3a00-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="f3a00-135">See Also</span></span>  
 <span data-ttu-id="f3a00-136">[Как определяются разрешения &#40;Master Data Services&#41;](how-permissions-are-determined-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="f3a00-136">[How Permissions Are Determined &#40;Master Data Services&#41;](how-permissions-are-determined-master-data-services.md) </span></span>  
 [<span data-ttu-id="f3a00-137">Перекрытие разрешений моделей и элементов (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="f3a00-137">Overlapping Model and Member Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/overlapping-model-and-member-permissions-master-data-services.md)  
  
  
