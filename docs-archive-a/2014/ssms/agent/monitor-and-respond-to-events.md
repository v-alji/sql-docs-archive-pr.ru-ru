---
title: Наблюдение за событиями и их обработка | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- notifications [SQL Server], alert
- events [SQL Server], alerts
- alerts [SQL Server]
- notifications [SQL Server]
- events [SQL Server], automatically responding to
- administrator notifications [SQL Server Agent]
- automatic event responses
- SQL Server Agent alerts
- monitoring [SQL Server], events
- responding to events automatically
ms.assetid: f7fbe155-5b68-4777-bc71-a47637471f32
author: stevestein
ms.author: sstein
ms.openlocfilehash: afdf1beffd6099fce84f03a8ba65f7de9abb8f0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731329"
---
# <a name="monitor-and-respond-to-events"></a><span data-ttu-id="c55ac-102">Наблюдение и обработка событий</span><span class="sxs-lookup"><span data-stu-id="c55ac-102">Monitor and Respond to Events</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c55ac-103">Агент производит мониторинг и автоматическую обработку различных *событий*: сообщений от [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], некоторых условий производительности и событий инструментария управления Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="c55ac-103">Agent can monitor and automatically respond to *events*, such as messages from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], specific performance conditions, and Windows Management Instrumentation (WMI) events.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c55ac-104">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="c55ac-104">In This Section</span></span>  
 [<span data-ttu-id="c55ac-105">Оповещения</span><span class="sxs-lookup"><span data-stu-id="c55ac-105">Alerts</span></span>](alerts.md)  
 <span data-ttu-id="c55ac-106">Содержит сведения об именовании предупреждений и о выборе событий или условий производительности, которые обрабатываются предупреждениями.</span><span class="sxs-lookup"><span data-stu-id="c55ac-106">Contains information about naming an alert and selecting the events or performance conditions to which alerts respond.</span></span>  
  
 [<span data-ttu-id="c55ac-107">Создание пользовательского события</span><span class="sxs-lookup"><span data-stu-id="c55ac-107">Create a User-Defined Event</span></span>](create-a-user-defined-event.md)  
 <span data-ttu-id="c55ac-108">Содержит сведения о том, как создать событие, отличное от стандартного для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c55ac-108">Contains information about how to create events other than those that are predefined by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="c55ac-109">Операторы</span><span class="sxs-lookup"><span data-stu-id="c55ac-109">Operators</span></span>](operators.md)  
 <span data-ttu-id="c55ac-110">Содержит сведения о создании псевдонимов для администраторов, которым агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] рассылает уведомления при успешном или неуспешном выполнении заданий.</span><span class="sxs-lookup"><span data-stu-id="c55ac-110">Contains information about creating aliases for administrators that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent can use to send notifications when jobs fail or succeed.</span></span>  
  
## <a name="about-monitoring-and-responding-to-events"></a><span data-ttu-id="c55ac-111">О мониторинге и обработке событий</span><span class="sxs-lookup"><span data-stu-id="c55ac-111">About Monitoring and Responding to Events</span></span>  
 <span data-ttu-id="c55ac-112">Автоматические отклики на события называются *предупреждениями*.</span><span class="sxs-lookup"><span data-stu-id="c55ac-112">Automated responses to events are called *alerts*.</span></span> <span data-ttu-id="c55ac-113">Можно назначить предупреждение на одно или несколько событий, определив, каким образом должен реагировать агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на его возникновение.</span><span class="sxs-lookup"><span data-stu-id="c55ac-113">You can define an alert on one or more events to specify how you want [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to respond to their occurrence.</span></span> <span data-ttu-id="c55ac-114">При обработке события предупреждение может отправить уведомление администратору, выполнить какое-либо задание, либо то и другое.</span><span class="sxs-lookup"><span data-stu-id="c55ac-114">An alert can respond to an event by notifying an administrator or running a job, or both.</span></span> <span data-ttu-id="c55ac-115">Предупреждение может также переслать событие в журнал приложений Microsoft Windows на другом компьютере.</span><span class="sxs-lookup"><span data-stu-id="c55ac-115">An alert can also forward an event to the Microsoft Windows application log on a different computer.</span></span> <span data-ttu-id="c55ac-116">Например, можно задать немедленное уведомление оператора при возникновении события с уровнем серьезности 19.</span><span class="sxs-lookup"><span data-stu-id="c55ac-116">For example, you can specify that an operator be notified immediately if an event of severity 19 occurs.</span></span> <span data-ttu-id="c55ac-117">Использование предупреждений позволяет администраторам базы данных более эффективно производить мониторинг и управление [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c55ac-117">By defining alerts, database administrators can more effectively monitor and manage [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c55ac-118">Агент обрабатывает только те события, для которых назначены предупреждения.</span><span class="sxs-lookup"><span data-stu-id="c55ac-118">Agent only responds to events for which an alert is defined.</span></span> <span data-ttu-id="c55ac-119">Метод, применяемый агентом [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для мониторинга событий, зависит от их типа.</span><span class="sxs-lookup"><span data-stu-id="c55ac-119">The method that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent uses to monitor events depends on the type of event.</span></span>  
  
 <span data-ttu-id="c55ac-120">Если предупреждение агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] определено для счетчика производительности, агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] непосредственно его отслеживает.</span><span class="sxs-lookup"><span data-stu-id="c55ac-120">When a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert is defined for a performance counter, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent directly monitors the performance counter.</span></span> <span data-ttu-id="c55ac-121">Для отслеживания событий WMI агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] регистрирует запрос события WMI.</span><span class="sxs-lookup"><span data-stu-id="c55ac-121">For a WMI event, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent registers an event query for the WMI event.</span></span>  
  
 <span data-ttu-id="c55ac-122">Для отслеживания сообщений [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] производит мониторинг журнала приложений Windows.</span><span class="sxs-lookup"><span data-stu-id="c55ac-122">To respond to messages from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent monitors the Windows application log.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c55ac-123">Агент может обрабатывать только те сообщения, которые появляются в этом журнале.</span><span class="sxs-lookup"><span data-stu-id="c55ac-123">Agent can only respond to messages that appear in this log.</span></span> <span data-ttu-id="c55ac-124">По умолчанию SQL Server протоколирует в журнале приложений Windows следующие сообщения.</span><span class="sxs-lookup"><span data-stu-id="c55ac-124">By default, SQL Server logs the following messages in the Windows application log:</span></span>  
  
-   <span data-ttu-id="c55ac-125">Ошибки из таблицы sysmessages с уровнем серьезности 19 и выше.</span><span class="sxs-lookup"><span data-stu-id="c55ac-125">Severity 19 or higher sysmessages errors.</span></span>  
  
     <span data-ttu-id="c55ac-126">Если необходимо протоколировать и другие ошибки из таблицы sysmessages, которые имеют уровень серьезности ниже 19, с помощью хранимой процедуры sp_altermessage можно обозначить такие ошибки как «протоколируемые всегда».</span><span class="sxs-lookup"><span data-stu-id="c55ac-126">If you also want to log specific sysmessages errors that have a severity lower than 19, use the sp_altermessage stored procedure to designate such errors as "always logged".</span></span>  
  
-   <span data-ttu-id="c55ac-127">Инструкции RAISERROR, вызываемые при использовании синтаксиса WITH LOG.</span><span class="sxs-lookup"><span data-stu-id="c55ac-127">Any RAISERROR statement invoked by using the WITH LOG syntax.</span></span>  
  
     <span data-ttu-id="c55ac-128">Этот способ рекомендуется для записи в журнал приложений Windows из экземпляра сервера SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c55ac-128">Using RAISERROR WITH LOG is the recommended way to write to the Windows application log from an instance of SQL Server.</span></span>  
  
-   <span data-ttu-id="c55ac-129">Любые события приложения, протоколируемые при помощи процедуры xp_logevent.</span><span class="sxs-lookup"><span data-stu-id="c55ac-129">Any application event that is logged by using xp_logevent.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c55ac-130">Протоколирование событий приложений занимает место в журнале, в результате чего может произойти превышение его максимально допустимого размера.</span><span class="sxs-lookup"><span data-stu-id="c55ac-130">Logging application events consumes log space and can cause the Windows application log to exceed its maximum size.</span></span> <span data-ttu-id="c55ac-131">Чтобы предотвратить потери данных о событиях SQL Server, необходимо установить в качестве максимального размера журнала приложений Windows достаточно большое значение.</span><span class="sxs-lookup"><span data-stu-id="c55ac-131">Make sure that the maximum Windows application log size is large enough to avoid loss of SQL Server event information.</span></span>  
  
 <span data-ttu-id="c55ac-132">После того, как [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] записал сообщение в журнал, служба агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] сравнивает его с предупреждениями, определенными администратором [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c55ac-132">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logs a message, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service compares the message against the alerts defined by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] administrator.</span></span>  
  
 <span data-ttu-id="c55ac-133">Независимо от источника события, служба агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] обрабатывает его, выполняя задачи, заданные в предупреждении для данного события.</span><span class="sxs-lookup"><span data-stu-id="c55ac-133">Regardless of the source of the event, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service responds to the event by performing the tasks specified in the alert for the event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c55ac-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="c55ac-134">See Also</span></span>  
 [<span data-ttu-id="c55ac-135">sp_altermessage &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c55ac-135">sp_altermessage &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-altermessage-transact-sql)  
  
  
