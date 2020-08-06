---
title: Свойства агента SQL Server (страница "Дополнительно") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.agent.advanced.f1
ms.assetid: a4d798ee-4c18-40d4-b6af-63d17503738c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8ec0d9d7fbd51f9350bf692588f90c292e54f4e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667532"
---
# <a name="sql-server-agent-properties-advanced-page"></a><span data-ttu-id="fceaf-102">Свойства агента SQL Server (страница «Дополнительно»)</span><span class="sxs-lookup"><span data-stu-id="fceaf-102">SQL Server Agent Properties (Advanced Page)</span></span>
  <span data-ttu-id="fceaf-103">Эта страница используется для просмотра и изменения дополнительных свойств [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] службы агента.</span><span class="sxs-lookup"><span data-stu-id="fceaf-103">Use this page to view and modify advanced properties of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service.</span></span>  
  
## <a name="options"></a><span data-ttu-id="fceaf-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="fceaf-104">Options</span></span>  
 <span data-ttu-id="fceaf-105">**Пересылка событий SQL Server**</span><span class="sxs-lookup"><span data-stu-id="fceaf-105">**SQL Server event forwarding**</span></span>  
 <span data-ttu-id="fceaf-106">Параметры в данной категории активируют и настраивают пересылку событий.</span><span class="sxs-lookup"><span data-stu-id="fceaf-106">The options in this category activate and configure event forwarding.</span></span>  
  
 <span data-ttu-id="fceaf-107">**Переслать события на другой сервер**</span><span class="sxs-lookup"><span data-stu-id="fceaf-107">**Forward events to a different server**</span></span>  
 <span data-ttu-id="fceaf-108">Перенаправляет события агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] другому серверу.</span><span class="sxs-lookup"><span data-stu-id="fceaf-108">Forwards [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent events to a different server.</span></span>  
  
 <span data-ttu-id="fceaf-109">**Server**</span><span class="sxs-lookup"><span data-stu-id="fceaf-109">**Server**</span></span>  
 <span data-ttu-id="fceaf-110">Выберите имя сервера, которому нужно перенаправить события.</span><span class="sxs-lookup"><span data-stu-id="fceaf-110">Select the name of the server to forward events to.</span></span>  
  
 <span data-ttu-id="fceaf-111">**Необработанные события**</span><span class="sxs-lookup"><span data-stu-id="fceaf-111">**Unhandled events**</span></span>  
 <span data-ttu-id="fceaf-112">Переправляет заданному серверу только необработанные события.</span><span class="sxs-lookup"><span data-stu-id="fceaf-112">Forwards only unhandled events to the specified server.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="fceaf-113">перенаправляет только события, на которые не реагирует ни одно предупреждение.</span><span class="sxs-lookup"><span data-stu-id="fceaf-113">Agent forwards only events that no alert responds to.</span></span>  
  
 <span data-ttu-id="fceaf-114">**Все события**</span><span class="sxs-lookup"><span data-stu-id="fceaf-114">**All events**</span></span>  
 <span data-ttu-id="fceaf-115">Переправляет все события.</span><span class="sxs-lookup"><span data-stu-id="fceaf-115">Forwards all events.</span></span> <span data-ttu-id="fceaf-116">Если предупреждение локального экземпляра реагирует на событие, агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] перенаправит этот событие и обработает предупреждение.</span><span class="sxs-lookup"><span data-stu-id="fceaf-116">When an alert in the local instance responds to the event, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agent will both forward the event and process the alert.</span></span>  
  
 <span data-ttu-id="fceaf-117">**Если серьезность события равна или превышает**</span><span class="sxs-lookup"><span data-stu-id="fceaf-117">**If event has severity at or above**</span></span>  
 <span data-ttu-id="fceaf-118">Пересылает только события, уровень серьезности которых равен указанному или превышает его.</span><span class="sxs-lookup"><span data-stu-id="fceaf-118">Forwards only events with a severity level at or above the level specified.</span></span>  
  
 <span data-ttu-id="fceaf-119">**Условие простоя ЦП**</span><span class="sxs-lookup"><span data-stu-id="fceaf-119">**Idle CPU Condition**</span></span>  
 <span data-ttu-id="fceaf-120">Параметры в данной категории определяют условия, при которых агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] запускает задания, запланированные к выполнению в расписании простоя ЦП.</span><span class="sxs-lookup"><span data-stu-id="fceaf-120">The options in this category define the conditions under which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent runs jobs scheduled to run on the Idle CPU schedule.</span></span>  
  
 <span data-ttu-id="fceaf-121">**Определить условие простоя ЦП**</span><span class="sxs-lookup"><span data-stu-id="fceaf-121">**Define idle CPU condition**</span></span>  
 <span data-ttu-id="fceaf-122">Определяет условия, при которых агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] считает, что ЦП простаивает.</span><span class="sxs-lookup"><span data-stu-id="fceaf-122">Defines the conditions under which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent considers the CPU to be idle.</span></span>  
  
 <span data-ttu-id="fceaf-123">**Среднее время использования ЦП сократилось до**</span><span class="sxs-lookup"><span data-stu-id="fceaf-123">**Average CPU usage falls below**</span></span>  
 <span data-ttu-id="fceaf-124">Процент использования ЦП сократился до уровня, при котором считается, что ЦП простаивает.</span><span class="sxs-lookup"><span data-stu-id="fceaf-124">Percentage of CPU usage below which the CPU is considered to be idle.</span></span>  
  
 <span data-ttu-id="fceaf-125">**И остается ниже этого уровня в течение**</span><span class="sxs-lookup"><span data-stu-id="fceaf-125">**And remains below this level for**</span></span>  
 <span data-ttu-id="fceaf-126">Отрезок времени, который средний ЦП должен простаивать, прежде чем агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] запустит задания по расписанию простоя ЦП.</span><span class="sxs-lookup"><span data-stu-id="fceaf-126">Amount of time that the average CPU must below the level specified before [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent runs jobs on the Idle CPU schedule.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fceaf-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="fceaf-127">See Also</span></span>  
 <span data-ttu-id="fceaf-128">[Создание и присоединение расписаний к заданиям](create-and-attach-schedules-to-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="fceaf-128">[Create and Attach Schedules to Jobs](create-and-attach-schedules-to-jobs.md) </span></span>  
 [<span data-ttu-id="fceaf-129">Управление событиями</span><span class="sxs-lookup"><span data-stu-id="fceaf-129">Manage Events</span></span>](manage-events.md)  
  
  
