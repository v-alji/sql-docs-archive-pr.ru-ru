---
title: Профили агентов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.profiles.perfprofiles.f1
helpviewer_keywords:
- Agent Profiles dialog box
ms.assetid: 0422e99c-e688-419b-bb4c-c7bebeef1d8d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7584670088da1ac7a9c81f1f8f0cbdce8b040c7b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657674"
---
# <a name="agent-profiles"></a><span data-ttu-id="5e3e7-102">Профили агентов</span><span class="sxs-lookup"><span data-stu-id="5e3e7-102">Agent Profiles</span></span>
  <span data-ttu-id="5e3e7-103">Диалоговое окно **Профили агентов** управляет профилями агентов.</span><span class="sxs-lookup"><span data-stu-id="5e3e7-103">Use the **Agent Profiles** dialog box to manage agent profiles.</span></span> <span data-ttu-id="5e3e7-104">Профили агентов предоставляют удобный способ управления параметрами среды выполнения для каждого агента.</span><span class="sxs-lookup"><span data-stu-id="5e3e7-104">Agent profiles provide a convenient way to manage the runtime parameters for each agent.</span></span> <span data-ttu-id="5e3e7-105">Каждый агент имеет профиль по умолчанию, а некоторые агенты имеют и дополнительные предопределенные профили.</span><span class="sxs-lookup"><span data-stu-id="5e3e7-105">Each agent has a default profile, and some agents have additional predefined profiles.</span></span> <span data-ttu-id="5e3e7-106">Например, агент слияния имеет профиль «медленной связи», предназначенный для соединений с низкой пропускной способностью.</span><span class="sxs-lookup"><span data-stu-id="5e3e7-106">For example, the Merge Agent has a "slow link" profile designed for low bandwidth connections.</span></span> <span data-ttu-id="5e3e7-107">Предопределенных профилей достаточно для создания большинства приложений, однако существует возможность создания пользовательских профилей, позволяющих настроить поведение агента.</span><span class="sxs-lookup"><span data-stu-id="5e3e7-107">Predefined profiles are sufficient for most applications, but you can also create user-defined profiles, allowing you to customize agent behavior.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5e3e7-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="5e3e7-108">Options</span></span>  
 <span data-ttu-id="5e3e7-109">**Выберите страницу**</span><span class="sxs-lookup"><span data-stu-id="5e3e7-109">**Select a page**</span></span>  
 <span data-ttu-id="5e3e7-110">Выберите в левой панели агент, и профили для этого агента отобразятся в правой панели.</span><span class="sxs-lookup"><span data-stu-id="5e3e7-110">Select an agent in the left pane, and the profiles for the agent are displayed in the right pane.</span></span>  
  
 <span data-ttu-id="5e3e7-111">**По умолчанию для нового**</span><span class="sxs-lookup"><span data-stu-id="5e3e7-111">**Default for New**</span></span>  
 <span data-ttu-id="5e3e7-112">Выберите профиль, который будет использован при создании заданий для агента заданного типа.</span><span class="sxs-lookup"><span data-stu-id="5e3e7-112">Select the profile that will be used when jobs are created for an agent of a given type.</span></span> <span data-ttu-id="5e3e7-113">Например, при создании подписок для публикации слиянием задание агента слияния для каждой подписки будет использовать выбранный профиль.</span><span class="sxs-lookup"><span data-stu-id="5e3e7-113">For example, if you create a number of subscriptions to a merge publication, the Merge Agent job for each subscription will use the profile selected.</span></span> <span data-ttu-id="5e3e7-114">Если нужно изменить профиль существующих заданий, выберите профиль и нажмите **Изменить существующие агенты**.</span><span class="sxs-lookup"><span data-stu-id="5e3e7-114">If you want to change the profile for existing jobs, select a profile, and then click **Change Existing Agents**.</span></span>  
  
 <span data-ttu-id="5e3e7-115">**Название**</span><span class="sxs-lookup"><span data-stu-id="5e3e7-115">**Name**</span></span>  
 <span data-ttu-id="5e3e7-116">Имя профиля.</span><span class="sxs-lookup"><span data-stu-id="5e3e7-116">The name of the profile.</span></span>  
  
 <span data-ttu-id="5e3e7-117">**Тип**</span><span class="sxs-lookup"><span data-stu-id="5e3e7-117">**Type**</span></span>  
 <span data-ttu-id="5e3e7-118">Тип профиля: **Пользовательский** (определяемый пользователем) или **Системный** (предустановленный).</span><span class="sxs-lookup"><span data-stu-id="5e3e7-118">The type of profile: **User** (user-defined) or **System** (predefined).</span></span>  
  
 <span data-ttu-id="5e3e7-119">**Свойства (...)**</span><span class="sxs-lookup"><span data-stu-id="5e3e7-119">**Properties (...)**</span></span>  
 <span data-ttu-id="5e3e7-120">Нажмите для просмотра значений каждого параметра в профиле агента.</span><span class="sxs-lookup"><span data-stu-id="5e3e7-120">Click to view the values used for each parameter in the agent profile.</span></span>  
  
 <span data-ttu-id="5e3e7-121">**Создать**</span><span class="sxs-lookup"><span data-stu-id="5e3e7-121">**New**</span></span>  
 <span data-ttu-id="5e3e7-122">Нажмите для создания нового профиля.</span><span class="sxs-lookup"><span data-stu-id="5e3e7-122">Click to create a new profile.</span></span>  
  
 <span data-ttu-id="5e3e7-123">**Удаление**</span><span class="sxs-lookup"><span data-stu-id="5e3e7-123">**Delete**</span></span>  
 <span data-ttu-id="5e3e7-124">Выберите пользовательский профиль и нажмите кнопку **Удалить** , чтобы удалить его.</span><span class="sxs-lookup"><span data-stu-id="5e3e7-124">Select a user-defined profile, and then click **Delete** to delete that profile.</span></span> <span data-ttu-id="5e3e7-125">Предопределенные профили удалить нельзя.</span><span class="sxs-lookup"><span data-stu-id="5e3e7-125">Predefined profiles cannot be deleted.</span></span>  
  
 <span data-ttu-id="5e3e7-126">**Изменить существующие агенты**</span><span class="sxs-lookup"><span data-stu-id="5e3e7-126">**Change Existing Agents**</span></span>  
 <span data-ttu-id="5e3e7-127">Выберите профиль и нажмите **Изменить существующие агенты** , чтобы указать, что все существующие задания для агента данного типа должны использовать выбранный профиль.</span><span class="sxs-lookup"><span data-stu-id="5e3e7-127">Select a profile, and then click **Change Existing Agents** to specify that all existing jobs for an agent of a given type should use the selected profile.</span></span> <span data-ttu-id="5e3e7-128">Например, если создано несколько подписок на публикацию слиянием и нужно изменить профиль, чтобы указать, что задание агента слияния для каждой из этих подписок должно использовать **Профиль агента медленного канала связи**, то выберите этот профиль и нажмите **Изменить существующие агенты**.</span><span class="sxs-lookup"><span data-stu-id="5e3e7-128">For example, if you have created a number of subscriptions to a merge publication, and you want to change the profile to specify that the Merge Agent job for each of these subscriptions should use the **Slow link agent profile**, select that profile, and then click **Change Existing Agents**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e3e7-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="5e3e7-129">See Also</span></span>  
 <span data-ttu-id="5e3e7-130">[Работа с профилями агента репликации](agents/work-with-replication-agent-profiles.md) </span><span class="sxs-lookup"><span data-stu-id="5e3e7-130">[Work with Replication Agent Profiles](agents/work-with-replication-agent-profiles.md) </span></span>  
 <span data-ttu-id="5e3e7-131">[Обзор агентов репликации](agents/replication-agents-overview.md) </span><span class="sxs-lookup"><span data-stu-id="5e3e7-131">[Replication Agents Overview](agents/replication-agents-overview.md) </span></span>  
 [<span data-ttu-id="5e3e7-132">Профили агента репликации</span><span class="sxs-lookup"><span data-stu-id="5e3e7-132">Replication Agent Profiles</span></span>](agents/replication-agent-profiles.md)  
  
  
