---
title: Подсистема расширенных событий SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
helpviewer_keywords:
- extended events [SQL Server], engine
ms.assetid: d74642a5-42b9-4a15-aa3d-f98bfe695050
author: rothja
ms.author: jroth
ms.openlocfilehash: ef11ac8e2cfaf39d2bca90f1d5d52439989ee327
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655172"
---
# <a name="sql-server-extended-events-engine"></a><span data-ttu-id="57fce-102">Подсистема расширенных событий SQL Server</span><span class="sxs-lookup"><span data-stu-id="57fce-102">SQL Server Extended Events Engine</span></span>
  <span data-ttu-id="57fce-103">Подсистема расширенных событий [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] представляет собой набор служб и объектов, которые выполняют следующие действия.</span><span class="sxs-lookup"><span data-stu-id="57fce-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Extended Events engine is a collection of services and objects that:</span></span>  
  
-   <span data-ttu-id="57fce-104">Включает определения событий.</span><span class="sxs-lookup"><span data-stu-id="57fce-104">Enable the definition of events.</span></span>  
  
-   <span data-ttu-id="57fce-105">Включает обработку данных событий.</span><span class="sxs-lookup"><span data-stu-id="57fce-105">Enable processing event data.</span></span>  
  
-   <span data-ttu-id="57fce-106">Управляет службами и объектами расширенных событий в системе.</span><span class="sxs-lookup"><span data-stu-id="57fce-106">Manage Extended Events services and objects in the system.</span></span>  
  
-   <span data-ttu-id="57fce-107">Поддерживает список сеансов расширенных событий и управляет доступом к этому списку.</span><span class="sxs-lookup"><span data-stu-id="57fce-107">Maintain a list of Extended Events sessions and manage access to that list.</span></span>  
  
 <span data-ttu-id="57fce-108">Сама подсистема расширенных событий не предоставляет никаких событий или действий при запуске события.</span><span class="sxs-lookup"><span data-stu-id="57fce-108">The Extended Events engine itself does not provide any events or actions to take when an event fires.</span></span> <span data-ttu-id="57fce-109">Взаимодействие с подсистемой расширенных событий определяют процессы, использующие ее.</span><span class="sxs-lookup"><span data-stu-id="57fce-109">The processes that use the Extended Events engine define interaction with the engine.</span></span> <span data-ttu-id="57fce-110">Процессы добавляют точки событий и предоставляют действия, которые необходимо предпринять при возникновении события.</span><span class="sxs-lookup"><span data-stu-id="57fce-110">These processes add event points and supply the actions to take in response to event firing.</span></span>  
  
 <span data-ttu-id="57fce-111">На следующем рисунке показан упрощенный вид сеанса расширенных событий.</span><span class="sxs-lookup"><span data-stu-id="57fce-111">The following illustration shows a simplified view of an Extended Events session.</span></span> <span data-ttu-id="57fce-112">Дополнительные сведения см. в разделе [SQL Server Extended Events Sessions](sql-server-extended-events-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="57fce-112">For more information, see [SQL Server Extended Events Sessions](sql-server-extended-events-sessions.md).</span></span>  
  
 <span data-ttu-id="57fce-113">![Подробная архитектура расширенных событий](../../database-engine/media/xearchitecturedetailed.gif "Подробная архитектура расширенных событий")</span><span class="sxs-lookup"><span data-stu-id="57fce-113">![Detailed extended events architecture](../../database-engine/media/xearchitecturedetailed.gif "Detailed extended events architecture")</span></span>  
  
 <span data-ttu-id="57fce-114">Следует отметить следующее.</span><span class="sxs-lookup"><span data-stu-id="57fce-114">Note the following:</span></span>  
  
-   <span data-ttu-id="57fce-115">Каждому процессу Windows соответствует один или несколько модулей (**процесс Win32**, **модуль Win32**).</span><span class="sxs-lookup"><span data-stu-id="57fce-115">Each Windows process can have one or more modules (**Win32 process**, **Win32 module**).</span></span> <span data-ttu-id="57fce-116">Они называются *двоичными* или *исполняемыми модулями*.</span><span class="sxs-lookup"><span data-stu-id="57fce-116">These are also known as *binaries* or *executable modules*.</span></span>  
  
-   <span data-ttu-id="57fce-117">Каждый модуль процесса Windows содержит один или несколько пакетов расширенных событий (**пакет**), который содержит один или несколько объектов расширенных событий (**тип**, **цель**, **действие**, **сопоставление**, **предикат**и **событие**).</span><span class="sxs-lookup"><span data-stu-id="57fce-117">Each of the Windows process modules can contain one or more Extended Events packages (**Package**), which contain one or more Extended Events objects (**Type**, **Target**, **Action**, **Map**, **Predicate**, and **Event**).</span></span>  
  
-   <span data-ttu-id="57fce-118">Процесс может содержать только один экземпляр подсистемы расширенных событий (**подсистема расширенных событий**), который выполняет указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="57fce-118">Inside a host process there can only be one instance of the Extended Events engine (**Extended event engine**), which:</span></span>  
  
    -   <span data-ttu-id="57fce-119">Управляет некоторыми аспектами сеанса (например перечислением сеансов).</span><span class="sxs-lookup"><span data-stu-id="57fce-119">Manages some aspects of the session (for example, enumerating sessions).</span></span>  
  
    -   <span data-ttu-id="57fce-120">Обрабатывает доставку (**диспетчер**).</span><span class="sxs-lookup"><span data-stu-id="57fce-120">Handles dispatching (**Dispatcher**).</span></span> <span data-ttu-id="57fce-121">(подобно пулу потоков).</span><span class="sxs-lookup"><span data-stu-id="57fce-121">This is similar to a thread pool.</span></span>  
  
    -   <span data-ttu-id="57fce-122">Управляет буферами памяти (**буфер**) событий.</span><span class="sxs-lookup"><span data-stu-id="57fce-122">Handles memory buffers (**Buffer**) for events.</span></span> <span data-ttu-id="57fce-123">Когда буфер заполняется, он отправляется цели.</span><span class="sxs-lookup"><span data-stu-id="57fce-123">When buffers are filled, the buffers are dispatched to targets.</span></span>  
  
-   <span data-ttu-id="57fce-124">После создания сеанса к нему можно привязать события (**контекст сеанса**):</span><span class="sxs-lookup"><span data-stu-id="57fce-124">After a session is created and events are optionally bound to the session (**Session context**):</span></span>  
  
    -   <span data-ttu-id="57fce-125">Экземпляры целей (**целевой экземпляр**) также можно создавать и добавлять к сеансу.</span><span class="sxs-lookup"><span data-stu-id="57fce-125">Instances of targets (**Target instance**) may be also be created and added to the session.</span></span>  
  
    -   <span data-ttu-id="57fce-126">Когда буферы заполняются, они отправляются целям.</span><span class="sxs-lookup"><span data-stu-id="57fce-126">When buffers are filled, those buffers are dispatched to targets.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57fce-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="57fce-127">See Also</span></span>  
 [<span data-ttu-id="57fce-128">Расширенные события</span><span class="sxs-lookup"><span data-stu-id="57fce-128">Extended Events</span></span>](extended-events.md)  
  
  
