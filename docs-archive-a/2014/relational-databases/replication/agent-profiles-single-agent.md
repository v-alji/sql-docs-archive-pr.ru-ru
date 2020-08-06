---
title: Профили агента (один агент) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.profiles.perfprofileagentname.f1
helpviewer_keywords:
- Agent Profile dialog box
ms.assetid: 22713555-c496-4ce1-8ec7-4ae75cfadca8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7def9a6fef4e7e66076ee18552705c6071dab134
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657675"
---
# <a name="agent-profiles-single-agent"></a><span data-ttu-id="3c04f-102">Профили агента (один агент)</span><span class="sxs-lookup"><span data-stu-id="3c04f-102">Agent Profiles (single agent)</span></span>
  <span data-ttu-id="3c04f-103">Диалоговое окно **Профили агентов** служит для управления профилями агента.</span><span class="sxs-lookup"><span data-stu-id="3c04f-103">Use the **Agent Profiles** dialog box to manage profiles for an agent.</span></span> <span data-ttu-id="3c04f-104">Профили агентов предоставляют удобный способ управления параметрами среды выполнения для каждого агента.</span><span class="sxs-lookup"><span data-stu-id="3c04f-104">Agent profiles provide a convenient way to manage the runtime parameters for each agent.</span></span> <span data-ttu-id="3c04f-105">Каждый агент имеет профиль по умолчанию, а некоторые агенты имеют и дополнительные предопределенные профили.</span><span class="sxs-lookup"><span data-stu-id="3c04f-105">Each agent has a default profile, and some agents have additional predefined profiles.</span></span> <span data-ttu-id="3c04f-106">Например, агент слияния имеет профиль «медленной связи», предназначенный для соединений с низкой пропускной способностью.</span><span class="sxs-lookup"><span data-stu-id="3c04f-106">For example, the Merge Agent has a "slow link" profile designed for low bandwidth connections.</span></span> <span data-ttu-id="3c04f-107">Предопределенных профилей достаточно для создания большинства приложений, однако существует возможность создания пользовательских профилей, позволяющих настроить поведение агента.</span><span class="sxs-lookup"><span data-stu-id="3c04f-107">Predefined profiles are sufficient for most applications, but you can also create user-defined profiles, allowing you to customize agent behavior.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3c04f-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="3c04f-108">Options</span></span>  
 <span data-ttu-id="3c04f-109">**По умолчанию для нового**</span><span class="sxs-lookup"><span data-stu-id="3c04f-109">**Default for New**</span></span>  
 <span data-ttu-id="3c04f-110">Выберите профиль, который будет использован при создании заданий для агента заданного типа.</span><span class="sxs-lookup"><span data-stu-id="3c04f-110">Select the profile that will be used when jobs are created for an agent of a given type.</span></span> <span data-ttu-id="3c04f-111">Например, при создании подписок для публикации слиянием задание агента слияния для каждой подписки будет использовать выбранный профиль.</span><span class="sxs-lookup"><span data-stu-id="3c04f-111">For example, if you create a number of subscriptions to a merge publication, the Merge Agent job for each subscription will use the profile selected.</span></span> <span data-ttu-id="3c04f-112">Если нужно изменить профиль существующих заданий, выберите профиль и нажмите **Изменить существующие агенты**.</span><span class="sxs-lookup"><span data-stu-id="3c04f-112">If you want to change the profile for existing jobs, select a profile, and then click **Change Existing Agents**.</span></span>  
  
 <span data-ttu-id="3c04f-113">**Название**</span><span class="sxs-lookup"><span data-stu-id="3c04f-113">**Name**</span></span>  
 <span data-ttu-id="3c04f-114">Имя профиля.</span><span class="sxs-lookup"><span data-stu-id="3c04f-114">The name of the profile.</span></span>  
  
 <span data-ttu-id="3c04f-115">**Тип**</span><span class="sxs-lookup"><span data-stu-id="3c04f-115">**Type**</span></span>  
 <span data-ttu-id="3c04f-116">Тип профиля: **Пользовательский** (определяемый пользователем) или **Системный** (предустановленный).</span><span class="sxs-lookup"><span data-stu-id="3c04f-116">The type of profile: **User** (user-defined) or **System** (predefined).</span></span>  
  
 <span data-ttu-id="3c04f-117">**Свойства (...)**</span><span class="sxs-lookup"><span data-stu-id="3c04f-117">**Properties (...)**</span></span>  
 <span data-ttu-id="3c04f-118">Нажмите для просмотра значений каждого параметра в профиле агента.</span><span class="sxs-lookup"><span data-stu-id="3c04f-118">Click to view the values used for each parameter in the agent profile.</span></span>  
  
 <span data-ttu-id="3c04f-119">**Создать**</span><span class="sxs-lookup"><span data-stu-id="3c04f-119">**New**</span></span>  
 <span data-ttu-id="3c04f-120">Нажмите для создания нового профиля.</span><span class="sxs-lookup"><span data-stu-id="3c04f-120">Click to create a new profile.</span></span>  
  
 <span data-ttu-id="3c04f-121">**Удаление**</span><span class="sxs-lookup"><span data-stu-id="3c04f-121">**Delete**</span></span>  
 <span data-ttu-id="3c04f-122">Выберите пользовательский профиль и нажмите кнопку **Удалить** , чтобы удалить его.</span><span class="sxs-lookup"><span data-stu-id="3c04f-122">Select a user-defined profile, and then click **Delete** to delete that profile.</span></span> <span data-ttu-id="3c04f-123">Предопределенные профили удалить нельзя.</span><span class="sxs-lookup"><span data-stu-id="3c04f-123">Predefined profiles cannot be deleted.</span></span>  
  
 <span data-ttu-id="3c04f-124">**Изменить существующие агенты**</span><span class="sxs-lookup"><span data-stu-id="3c04f-124">**Change Existing Agents**</span></span>  
 <span data-ttu-id="3c04f-125">Выберите профиль и нажмите **Изменить существующие агенты** , чтобы указать, что все существующие задания для агента данного типа должны использовать выбранный профиль.</span><span class="sxs-lookup"><span data-stu-id="3c04f-125">Select a profile, and then click **Change Existing Agents** to specify that all existing jobs for an agent of a given type should use the selected profile.</span></span> <span data-ttu-id="3c04f-126">Например, если создано несколько подписок на публикацию слиянием и нужно изменить профиль, чтобы указать, что задание агента слияния для каждой из этих подписок должно использовать **Профиль агента медленного канала связи**, то выберите этот профиль и нажмите **Изменить существующие агенты**.</span><span class="sxs-lookup"><span data-stu-id="3c04f-126">For example, if you have created a number of subscriptions to a merge publication, and you want to change the profile to specify that the Merge Agent job for each of these subscriptions should use the **Slow link agent profile**, select that profile, and then click **Change Existing Agents**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c04f-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="3c04f-127">See Also</span></span>  
 <span data-ttu-id="3c04f-128">[Работа с профилями агента репликации](agents/work-with-replication-agent-profiles.md) </span><span class="sxs-lookup"><span data-stu-id="3c04f-128">[Work with Replication Agent Profiles](agents/work-with-replication-agent-profiles.md) </span></span>  
 <span data-ttu-id="3c04f-129">[Обзор агентов репликации](agents/replication-agents-overview.md) </span><span class="sxs-lookup"><span data-stu-id="3c04f-129">[Replication Agents Overview](agents/replication-agents-overview.md) </span></span>  
 [<span data-ttu-id="3c04f-130">Профили агента репликации</span><span class="sxs-lookup"><span data-stu-id="3c04f-130">Replication Agent Profiles</span></span>](agents/replication-agent-profiles.md)  
  
  
