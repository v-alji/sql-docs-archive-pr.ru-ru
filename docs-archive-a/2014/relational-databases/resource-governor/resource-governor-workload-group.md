---
title: Группа рабочей нагрузки регулятора ресурсов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, workload group
- workload groups [SQL Server]
- workload groups [SQL Server], overview
ms.assetid: a84c3c3f-55b6-4a30-9c42-13f082d9281e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6c6fa8f6fe960571f10d6a8505329fbe8f400e6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731458"
---
# <a name="resource-governor-workload-group"></a><span data-ttu-id="d82d8-102">Группа рабочей нагрузки регулятора ресурсов</span><span class="sxs-lookup"><span data-stu-id="d82d8-102">Resource Governor Workload Group</span></span>
  <span data-ttu-id="d82d8-103">В регуляторе ресурсов [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] группа рабочей нагрузки выступает в качестве контейнера для запросов сеансов, имеющих подобные критерии классификации.</span><span class="sxs-lookup"><span data-stu-id="d82d8-103">In the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Resource Governor, a workload group serves as a container for session requests that have similar classification criteria.</span></span> <span data-ttu-id="d82d8-104">Рабочая нагрузка обеспечивает статистический мониторинг сеансов и определяет политики для сеансов.</span><span class="sxs-lookup"><span data-stu-id="d82d8-104">A workload allows for aggregate monitoring of the sessions, and defines policies for the sessions.</span></span> <span data-ttu-id="d82d8-105">Каждая группа рабочей нагрузки находится в пуле ресурсов, который представляет подмножество физических ресурсов экземпляра компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d82d8-105">Each workload group is in a resource pool, which represents a subset of the physical resources of an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="d82d8-106">После запуска сеанса классификатор регулятора ресурсов назначает этот сеанс конкретной группе рабочей нагрузки, и этот сеанс должен функционировать с использованием политик, назначенных этой группе рабочей нагрузки, и ресурсов, определенных для пула ресурсов.</span><span class="sxs-lookup"><span data-stu-id="d82d8-106">When a session is started, the Resource Governor classifier assigns the session to a specific workload group, and the session must run using the policies assigned to the workload group and the resources defined for the resource pool.</span></span>  
  
## <a name="workload-group-concepts"></a><span data-ttu-id="d82d8-107">Основные понятия группы рабочей нагрузки</span><span class="sxs-lookup"><span data-stu-id="d82d8-107">Workload Group Concepts</span></span>  
 <span data-ttu-id="d82d8-108">Группа рабочей нагрузки выступает в качестве контейнера для запросов сеансов, которые являются подобными в соответствии с критериями классификации, применяемыми к каждому из запросов.</span><span class="sxs-lookup"><span data-stu-id="d82d8-108">A workload group serves as a container for session requests that are similar according to the classification criteria that are applied to each request.</span></span> <span data-ttu-id="d82d8-109">Группа рабочей нагрузки позволяет вести статистический контроль потребления ресурсов и приложения в рамках единообразной политики для всех запросов в группе.</span><span class="sxs-lookup"><span data-stu-id="d82d8-109">A workload group allows the aggregate monitoring of resource consumption and the application of a uniform policy to all the requests in the group.</span></span> <span data-ttu-id="d82d8-110">Группа определяет политики для ее членов.</span><span class="sxs-lookup"><span data-stu-id="d82d8-110">A group defines the policies for its members.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d82d8-111">Определяемые пользователем группы рабочей нагрузки можно перемещать из одного пула ресурсов в другой.</span><span class="sxs-lookup"><span data-stu-id="d82d8-111">User-defined workload groups can be moved from one resource pool to another.</span></span>  
  
 <span data-ttu-id="d82d8-112">В регуляторе ресурсов есть две стандартные группы рабочей нагрузки: внутренняя группа и группа по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d82d8-112">Resource Governor predefines two workload groups: the internal group and the default group.</span></span> <span data-ttu-id="d82d8-113">Пользователь не может изменить ничего из того, что классифицировано как внутренняя группа, но может вести за ней наблюдение.</span><span class="sxs-lookup"><span data-stu-id="d82d8-113">A user cannot change anything classified as an internal group, but can monitor it.</span></span> <span data-ttu-id="d82d8-114">Запросы классифицируются в группу по умолчанию при выполнении следующих условий.</span><span class="sxs-lookup"><span data-stu-id="d82d8-114">Requests are classified into the default group when the following conditions exist:</span></span>  
  
-   <span data-ttu-id="d82d8-115">Отсутствуют критерии классификации запроса.</span><span class="sxs-lookup"><span data-stu-id="d82d8-115">There are no criteria to classify a request.</span></span>  
  
-   <span data-ttu-id="d82d8-116">Предпринимается попытка классифицировать запрос в несуществующую группу.</span><span class="sxs-lookup"><span data-stu-id="d82d8-116">There is an attempt to classify the request into a non-existent group.</span></span>  
  
-   <span data-ttu-id="d82d8-117">Происходит общий сбой классификации.</span><span class="sxs-lookup"><span data-stu-id="d82d8-117">There is a general classification failure.</span></span>  
  
 <span data-ttu-id="d82d8-118">В регуляторе ресурсов предусмотрены инструкции DDL для создания, изменения и удаления групп рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="d82d8-118">Resource Governor also provides DDL statements for creating, changing, and dropping workload groups.</span></span>  
  
## <a name="workload-group-tasks"></a><span data-ttu-id="d82d8-119">Задачи группы рабочей нагрузки</span><span class="sxs-lookup"><span data-stu-id="d82d8-119">Workload Group Tasks</span></span>  
  
|<span data-ttu-id="d82d8-120">Описание задачи</span><span class="sxs-lookup"><span data-stu-id="d82d8-120">Task Description</span></span>|<span data-ttu-id="d82d8-121">Раздел</span><span class="sxs-lookup"><span data-stu-id="d82d8-121">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="d82d8-122">Описывает, как создать группу рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="d82d8-122">Describes how to create a workload group.</span></span>|[<span data-ttu-id="d82d8-123">Создание группы рабочей нагрузки</span><span class="sxs-lookup"><span data-stu-id="d82d8-123">Create a Workload Group</span></span>](create-a-workload-group.md)|  
|<span data-ttu-id="d82d8-124">Описывает, как изменить параметры группы рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="d82d8-124">Describes how to change workload group settings.</span></span>|[<span data-ttu-id="d82d8-125">Изменение параметров группы рабочей нагрузки</span><span class="sxs-lookup"><span data-stu-id="d82d8-125">Change Workload Group Settings</span></span>](change-workload-group-settings.md)|  
|<span data-ttu-id="d82d8-126">Описывает, как удалить группу рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="d82d8-126">Describes how to delete a workload group.</span></span>|[<span data-ttu-id="d82d8-127">Удаление группы рабочей нагрузки</span><span class="sxs-lookup"><span data-stu-id="d82d8-127">Delete a Workload Group</span></span>](delete-a-workload-group.md)|  
  
## <a name="see-also"></a><span data-ttu-id="d82d8-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="d82d8-128">See Also</span></span>  
 <span data-ttu-id="d82d8-129">[регулятор ресурсов](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="d82d8-129">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="d82d8-130">[Активация регулятора ресурсов](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="d82d8-130">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="d82d8-131">[Пул ресурсов регулятора ресурсов](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="d82d8-131">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="d82d8-132">[Функция-классификатор регулятора ресурсов](resource-governor-classifier-function.md) </span><span class="sxs-lookup"><span data-stu-id="d82d8-132">[Resource Governor Classifier Function](resource-governor-classifier-function.md) </span></span>  
 <span data-ttu-id="d82d8-133">[Настройка регулятора ресурсов с помощью шаблона](configure-resource-governor-using-a-template.md) </span><span class="sxs-lookup"><span data-stu-id="d82d8-133">[Configure Resource Governor Using a Template](configure-resource-governor-using-a-template.md) </span></span>  
 [<span data-ttu-id="d82d8-134">Просмотр свойств регулятора ресурсов</span><span class="sxs-lookup"><span data-stu-id="d82d8-134">View Resource Governor Properties</span></span>](view-resource-governor-properties.md)  
  
  
