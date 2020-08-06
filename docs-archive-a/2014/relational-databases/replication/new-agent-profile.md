---
title: Создать профиль агента | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.profiles.newperfprofile.f1
helpviewer_keywords:
- New Agent Profile dialog box
ms.assetid: ebf59330-a421-45a5-9020-0484a96852bc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1d7848e44585fd35a5b5a33cf431e15de96c9375
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736205"
---
# <a name="new-agent-profile"></a><span data-ttu-id="13396-102">Создать профиль агента</span><span class="sxs-lookup"><span data-stu-id="13396-102">New Agent Profile</span></span>
  <span data-ttu-id="13396-103">Диалоговое окно **Создать профиль агента** позволяет создать новый профиль.</span><span class="sxs-lookup"><span data-stu-id="13396-103">Use the **New Agent Profile** dialog box to create a new profile.</span></span> <span data-ttu-id="13396-104">Новые профили всегда основываются на существующих, но их можно изменить для соответствия требованиям приложения.</span><span class="sxs-lookup"><span data-stu-id="13396-104">New profiles are always based on existing profiles, but they can be modified to meet application requirements.</span></span> <span data-ttu-id="13396-105">После создания профиля его можно применить к текущим и будущим заданиям агента в диалоговом окне **Профили агента** .</span><span class="sxs-lookup"><span data-stu-id="13396-105">After a profile has been created, it can be applied to existing and future agent jobs in the **Agent Profiles** dialog box.</span></span> <span data-ttu-id="13396-106">Значения параметров агента можно изменить в диалоговом окне \<**AgentProfileName>Свойства\*\*.</span><span class="sxs-lookup"><span data-stu-id="13396-106">Agent parameter values can be edited in the \<**AgentProfileName> Properties\*\* dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="13396-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="13396-107">Options</span></span>  
 <span data-ttu-id="13396-108">**имя**;</span><span class="sxs-lookup"><span data-stu-id="13396-108">**Name**</span></span>  
 <span data-ttu-id="13396-109">Введите имя профиля.</span><span class="sxs-lookup"><span data-stu-id="13396-109">Enter a name for the profile.</span></span>  
  
 <span data-ttu-id="13396-110">**Описание**</span><span class="sxs-lookup"><span data-stu-id="13396-110">**Description**</span></span>  
 <span data-ttu-id="13396-111">Введите описание профиля.</span><span class="sxs-lookup"><span data-stu-id="13396-111">Enter a description for the profile.</span></span>  
  
 <span data-ttu-id="13396-112">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="13396-112">**Parameter**</span></span>  
 <span data-ttu-id="13396-113">Параметры агента, включенные в профиль.</span><span class="sxs-lookup"><span data-stu-id="13396-113">The agent parameters included in the profile.</span></span> <span data-ttu-id="13396-114">Профиль, на котором основан новый профиль, не обязательно указывает значения всех параметров.</span><span class="sxs-lookup"><span data-stu-id="13396-114">The profile on which the new profile is based does not necessarily specify a value for each parameter.</span></span> <span data-ttu-id="13396-115">Для просмотра всех допустимых для данного агента параметров снимите флажок **Показывать только параметры, используемые в этом профиле** .</span><span class="sxs-lookup"><span data-stu-id="13396-115">To see all parameters that are valid for a given agent, clear the **Show only parameters used in this profile** check box.</span></span> <span data-ttu-id="13396-116">Описание каждого параметра см. в разделах:</span><span class="sxs-lookup"><span data-stu-id="13396-116">For descriptions of each parameter, see:</span></span>  
  
-   [<span data-ttu-id="13396-117">Replication Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="13396-117">Replication Snapshot Agent</span></span>](agents/replication-snapshot-agent.md)  
  
-   [<span data-ttu-id="13396-118">Агент чтения журнала репликации</span><span class="sxs-lookup"><span data-stu-id="13396-118">Replication Log Reader Agent</span></span>](agents/replication-log-reader-agent.md)  
  
-   [<span data-ttu-id="13396-119">Replication Distribution Agent</span><span class="sxs-lookup"><span data-stu-id="13396-119">Replication Distribution Agent</span></span>](agents/replication-distribution-agent.md)  
  
-   [<span data-ttu-id="13396-120">Replication Merge Agent</span><span class="sxs-lookup"><span data-stu-id="13396-120">Replication Merge Agent</span></span>](agents/replication-merge-agent.md)  
  
-   [<span data-ttu-id="13396-121">Replication Queue Reader Agent</span><span class="sxs-lookup"><span data-stu-id="13396-121">Replication Queue Reader Agent</span></span>](agents/replication-queue-reader-agent.md)  
  
 <span data-ttu-id="13396-122">**Значение по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="13396-122">**Default Value**</span></span>  
 <span data-ttu-id="13396-123">Значение по умолчанию для каждого параметра агента.</span><span class="sxs-lookup"><span data-stu-id="13396-123">The default value for each agent parameter.</span></span>  
  
 <span data-ttu-id="13396-124">**Значение**</span><span class="sxs-lookup"><span data-stu-id="13396-124">**Value**</span></span>  
 <span data-ttu-id="13396-125">Значение, указанное для параметра в профиле, на котором основан новый профиль.</span><span class="sxs-lookup"><span data-stu-id="13396-125">The value specified for the parameter in the profile on which the new profile is based.</span></span> <span data-ttu-id="13396-126">Измените это поле, чтобы внести изменения в значения параметров.</span><span class="sxs-lookup"><span data-stu-id="13396-126">Edit this field for any parameter values you want to change.</span></span>  
  
 <span data-ttu-id="13396-127">**Показывать только параметры, используемые в этом профиле**</span><span class="sxs-lookup"><span data-stu-id="13396-127">**Show only parameters used in this profile**</span></span>  
 <span data-ttu-id="13396-128">Снимите флажок, чтобы отобразить все корректные параметры для данного агента.</span><span class="sxs-lookup"><span data-stu-id="13396-128">Clear to show all valid parameters for a given agent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13396-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="13396-129">See Also</span></span>  
 <span data-ttu-id="13396-130">[Работа с профилями агента репликации](agents/work-with-replication-agent-profiles.md) </span><span class="sxs-lookup"><span data-stu-id="13396-130">[Work with Replication Agent Profiles](agents/work-with-replication-agent-profiles.md) </span></span>  
 <span data-ttu-id="13396-131">[Обзор агентов репликации](agents/replication-agents-overview.md) </span><span class="sxs-lookup"><span data-stu-id="13396-131">[Replication Agents Overview](agents/replication-agents-overview.md) </span></span>  
 [<span data-ttu-id="13396-132">Профили агента репликации</span><span class="sxs-lookup"><span data-stu-id="13396-132">Replication Agent Profiles</span></span>](agents/replication-agent-profiles.md)  
  
  
