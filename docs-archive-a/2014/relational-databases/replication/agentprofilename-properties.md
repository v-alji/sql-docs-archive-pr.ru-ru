---
title: Свойства &lt;AgentProfileName&gt; | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.profiles.perfprofileprops.f1
helpviewer_keywords:
- Agent Profile Properties dialog box
ms.assetid: 01a992d2-e4ff-417c-93f0-dc43ab2d1624
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 561f55353b7e40d168266cf5ba531519c8225053
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668819"
---
# <a name="ltagentprofilenamegt-properties"></a><span data-ttu-id="fb6d1-102">Свойства &lt;AgentProfileName&gt;</span><span class="sxs-lookup"><span data-stu-id="fb6d1-102">&lt;AgentProfileName&gt; Properties</span></span>
  <span data-ttu-id="fb6d1-103">Диалоговое окно **Свойства профиля агента** позволяет просматривать значения всех параметров агента, указанных в профиле, и изменять эти значения для пользовательских профилей.</span><span class="sxs-lookup"><span data-stu-id="fb6d1-103">Use the **Agent Profiles Properties** dialog box to view the values specified for each agent parameter in a profile and to modify the values for user-defined profiles.</span></span>  
  
## <a name="options"></a><span data-ttu-id="fb6d1-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="fb6d1-104">Options</span></span>  
 <span data-ttu-id="fb6d1-105">**Название**</span><span class="sxs-lookup"><span data-stu-id="fb6d1-105">**Name**</span></span>  
 <span data-ttu-id="fb6d1-106">Имя профиля.</span><span class="sxs-lookup"><span data-stu-id="fb6d1-106">The name of the profile.</span></span>  
  
 <span data-ttu-id="fb6d1-107">**Описание**</span><span class="sxs-lookup"><span data-stu-id="fb6d1-107">**Description**</span></span>  
 <span data-ttu-id="fb6d1-108">Описание профиля.</span><span class="sxs-lookup"><span data-stu-id="fb6d1-108">A description of the profile.</span></span>  
  
 <span data-ttu-id="fb6d1-109">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="fb6d1-109">**Parameter**</span></span>  
 <span data-ttu-id="fb6d1-110">Параметры агента, включенные в профиль.</span><span class="sxs-lookup"><span data-stu-id="fb6d1-110">The agent parameters included in the profile.</span></span> <span data-ttu-id="fb6d1-111">Профили не должны задавать значения для каждого параметра.</span><span class="sxs-lookup"><span data-stu-id="fb6d1-111">Profiles do not necessarily specify a value for each parameter.</span></span> <span data-ttu-id="fb6d1-112">Для просмотра всех допустимых для данного агента параметров снимите флажок **Показывать только параметры, используемые в этом профиле** .</span><span class="sxs-lookup"><span data-stu-id="fb6d1-112">To see all parameters that are valid for a given agent, clear the **Show only parameters used in this profile** check box.</span></span> <span data-ttu-id="fb6d1-113">Описание каждого параметра см. в разделах:</span><span class="sxs-lookup"><span data-stu-id="fb6d1-113">For descriptions of each parameter, see:</span></span>  
  
-   [<span data-ttu-id="fb6d1-114">Replication Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="fb6d1-114">Replication Snapshot Agent</span></span>](agents/replication-snapshot-agent.md)  
  
-   [<span data-ttu-id="fb6d1-115">Агент чтения журнала репликации</span><span class="sxs-lookup"><span data-stu-id="fb6d1-115">Replication Log Reader Agent</span></span>](agents/replication-log-reader-agent.md)  
  
-   [<span data-ttu-id="fb6d1-116">Replication Distribution Agent</span><span class="sxs-lookup"><span data-stu-id="fb6d1-116">Replication Distribution Agent</span></span>](agents/replication-distribution-agent.md)  
  
-   [<span data-ttu-id="fb6d1-117">Replication Merge Agent</span><span class="sxs-lookup"><span data-stu-id="fb6d1-117">Replication Merge Agent</span></span>](agents/replication-merge-agent.md)  
  
-   [<span data-ttu-id="fb6d1-118">Replication Queue Reader Agent</span><span class="sxs-lookup"><span data-stu-id="fb6d1-118">Replication Queue Reader Agent</span></span>](agents/replication-queue-reader-agent.md)  
  
 <span data-ttu-id="fb6d1-119">**Значение по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="fb6d1-119">**Default Value**</span></span>  
 <span data-ttu-id="fb6d1-120">Значение по умолчанию для каждого параметра агента.</span><span class="sxs-lookup"><span data-stu-id="fb6d1-120">The default value for each agent parameter.</span></span>  
  
 <span data-ttu-id="fb6d1-121">**Value**</span><span class="sxs-lookup"><span data-stu-id="fb6d1-121">**Value**</span></span>  
 <span data-ttu-id="fb6d1-122">Значение, заданное для данного параметра в профиле.</span><span class="sxs-lookup"><span data-stu-id="fb6d1-122">The value specified for the parameter in the profile.</span></span> <span data-ttu-id="fb6d1-123">Для пользовательских профилей это поле можно изменять.</span><span class="sxs-lookup"><span data-stu-id="fb6d1-123">This field is editable for user-defined profiles.</span></span>  
  
 <span data-ttu-id="fb6d1-124">**Показывать только параметры, используемые в этом профиле**</span><span class="sxs-lookup"><span data-stu-id="fb6d1-124">**Show only parameters used in this profile**</span></span>  
 <span data-ttu-id="fb6d1-125">Снимите флажок, чтобы отобразить все корректные параметры для данного агента.</span><span class="sxs-lookup"><span data-stu-id="fb6d1-125">Clear to show all valid parameters for a given agent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb6d1-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="fb6d1-126">See Also</span></span>  
 <span data-ttu-id="fb6d1-127">[Работа с профилями агента репликации](agents/work-with-replication-agent-profiles.md) </span><span class="sxs-lookup"><span data-stu-id="fb6d1-127">[Work with Replication Agent Profiles](agents/work-with-replication-agent-profiles.md) </span></span>  
 <span data-ttu-id="fb6d1-128">[Обзор агентов репликации](agents/replication-agents-overview.md) </span><span class="sxs-lookup"><span data-stu-id="fb6d1-128">[Replication Agents Overview](agents/replication-agents-overview.md) </span></span>  
 [<span data-ttu-id="fb6d1-129">Профили агента репликации</span><span class="sxs-lookup"><span data-stu-id="fb6d1-129">Replication Agent Profiles</span></span>](agents/replication-agent-profiles.md)  
  
  
