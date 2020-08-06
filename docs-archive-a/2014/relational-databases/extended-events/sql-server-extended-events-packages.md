---
title: Пакеты обработки расширенных событий SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
helpviewer_keywords:
- extended events [SQL Server], packages
- xe
ms.assetid: 6bcb04fc-ca04-48f4-b96a-20b604973447
author: rothja
ms.author: jroth
ms.openlocfilehash: 45c452300c008d486bd1f4ab4c92b5f76b96ecd8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655170"
---
# <a name="sql-server-extended-events-packages"></a><span data-ttu-id="6af6f-102">Пакеты обработки расширенных событий SQL Server</span><span class="sxs-lookup"><span data-stu-id="6af6f-102">SQL Server Extended Events Packages</span></span>
  <span data-ttu-id="6af6f-103">Пакет представляет собой контейнер для объектов средства обработки расширенных событий [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6af6f-103">A package is a container for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Extended Events objects.</span></span> <span data-ttu-id="6af6f-104">Существуют три типа пакетов расширенных событий.</span><span class="sxs-lookup"><span data-stu-id="6af6f-104">There are three kinds of Extended Events packages, which include the following:</span></span>  
  
-   <span data-ttu-id="6af6f-105">package0 — системные объекты расширенных событий.</span><span class="sxs-lookup"><span data-stu-id="6af6f-105">package0 - Extended Events system objects.</span></span> <span data-ttu-id="6af6f-106">Это пакет по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6af6f-106">This is the default package.</span></span>  
  
-   <span data-ttu-id="6af6f-107">sqlserver — объекты, связанные с [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6af6f-107">sqlserver - [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] related objects.</span></span>  
  
-   <span data-ttu-id="6af6f-108">sqlos — объекты, связанные с операционной системой [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (SQLOS).</span><span class="sxs-lookup"><span data-stu-id="6af6f-108">sqlos - [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Operating System (SQLOS) related objects.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6af6f-109">Пакет SecAudit используется аудитом [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6af6f-109">The SecAudit package is used by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Audit.</span></span> <span data-ttu-id="6af6f-110">Объекты в пакете недоступны для языка описания данных DDL расширенных событий.</span><span class="sxs-lookup"><span data-stu-id="6af6f-110">None of the objects in the package are available through the Extended Events data definition language (DDL).</span></span>  
  
 <span data-ttu-id="6af6f-111">Пакеты определяются по имени, идентификатору GUID и двоичному модулю, содержащему этот пакет.</span><span class="sxs-lookup"><span data-stu-id="6af6f-111">Packages are identified by a name, a GUID, and the binary module that contains the package.</span></span> <span data-ttu-id="6af6f-112">Дополнительные сведения см. в статье [sys.dm_xe_packages (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-packages-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6af6f-112">For more information, see [sys.dm_xe_packages &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-packages-transact-sql).</span></span>  
  
 <span data-ttu-id="6af6f-113">Пакет может содержать любой из следующих объектов или все эти объекты, которые подробно рассматриваются ниже в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="6af6f-113">A package can contain any or all of the following objects, which are discussed in greater detail later in this topic:</span></span>  
  
-   <span data-ttu-id="6af6f-114">События</span><span class="sxs-lookup"><span data-stu-id="6af6f-114">Events</span></span>  
  
-   <span data-ttu-id="6af6f-115">Целевые объекты</span><span class="sxs-lookup"><span data-stu-id="6af6f-115">Targets</span></span>  
  
-   <span data-ttu-id="6af6f-116">Действия</span><span class="sxs-lookup"><span data-stu-id="6af6f-116">Actions</span></span>  
  
-   <span data-ttu-id="6af6f-117">Типы</span><span class="sxs-lookup"><span data-stu-id="6af6f-117">Types</span></span>  
  
-   <span data-ttu-id="6af6f-118">Предикаты</span><span class="sxs-lookup"><span data-stu-id="6af6f-118">Predicates</span></span>  
  
-   <span data-ttu-id="6af6f-119">Maps</span><span class="sxs-lookup"><span data-stu-id="6af6f-119">Maps</span></span>  
  
 <span data-ttu-id="6af6f-120">В сеансе событий могут содержаться объекты из разных пакетов.</span><span class="sxs-lookup"><span data-stu-id="6af6f-120">Objects from different packages can be mixed in an event session.</span></span> <span data-ttu-id="6af6f-121">Дополнительные сведения см. в разделе [SQL Server Extended Events Sessions](sql-server-extended-events-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="6af6f-121">For more information, see [SQL Server Extended Events Sessions](sql-server-extended-events-sessions.md).</span></span>  
  
## <a name="package-contents"></a><span data-ttu-id="6af6f-122">Содержимое пакета</span><span class="sxs-lookup"><span data-stu-id="6af6f-122">Package Contents</span></span>  
 <span data-ttu-id="6af6f-123">На следующем рисунке показаны объекты, которые имеются в пакете, содержащемся в модуле.</span><span class="sxs-lookup"><span data-stu-id="6af6f-123">The following illustration shows the objects that can exist in packages, which are contained in a module.</span></span> <span data-ttu-id="6af6f-124">Модуль может быть исполняемым файлом или динамической библиотекой.</span><span class="sxs-lookup"><span data-stu-id="6af6f-124">A module can be an executable or a dynamic link library.</span></span>  
  
 <span data-ttu-id="6af6f-125">![Связь между модулем, пакетами и объектом](../../database-engine/media/xepackagesobjects.gif "Связь между модулем, пакетами и объектом")</span><span class="sxs-lookup"><span data-stu-id="6af6f-125">![The relationship of a module, packages, and object](../../database-engine/media/xepackagesobjects.gif "The relationship of a module, packages, and object")</span></span>  
  
### <a name="events"></a><span data-ttu-id="6af6f-126">События</span><span class="sxs-lookup"><span data-stu-id="6af6f-126">Events</span></span>  
 <span data-ttu-id="6af6f-127">События представляют собой точки наблюдения в пути выполнения программы, например [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6af6f-127">Events are monitoring points of interest in the execution path of a program, such as [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6af6f-128">Возникновение события означает тот факт, что была достигнута точка наблюдения и был запущен сбор сведений о состоянии.</span><span class="sxs-lookup"><span data-stu-id="6af6f-128">An event firing carries with it the fact that the point of interest was reached, and state information from the time the event was fired.</span></span>  
  
 <span data-ttu-id="6af6f-129">События можно использовать только в целях отслеживания или для запуска действий.</span><span class="sxs-lookup"><span data-stu-id="6af6f-129">Events can be used solely for tracing purposes or for triggering actions.</span></span> <span data-ttu-id="6af6f-130">Эти действия могут быть синхронными или асинхронными.</span><span class="sxs-lookup"><span data-stu-id="6af6f-130">These actions can either be synchronous or asynchronous.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6af6f-131">Событие не осведомлено о действиях, которые могут быть предприняты в ответ на запуск события.</span><span class="sxs-lookup"><span data-stu-id="6af6f-131">An event does not have any knowledge of the actions that may be triggered in response to the event firing.</span></span>  
  
 <span data-ttu-id="6af6f-132">Набор событий в пакете нельзя изменить после регистрации пакета расширенных событий.</span><span class="sxs-lookup"><span data-stu-id="6af6f-132">A set of events in a package cannot change after the package is registered with Extended Events.</span></span>  
  
 <span data-ttu-id="6af6f-133">Все события имеют вариант схемы, определяющей их содержимое.</span><span class="sxs-lookup"><span data-stu-id="6af6f-133">All events have a versioned schema which defines their contents.</span></span> <span data-ttu-id="6af6f-134">Эта схема состоит из столбцов событий с явно определенными типами.</span><span class="sxs-lookup"><span data-stu-id="6af6f-134">This schema is composed of event columns with well defined types.</span></span> <span data-ttu-id="6af6f-135">Событие конкретного типа должно всегда предоставлять свои данные точно в том порядке, который задан в схеме.</span><span class="sxs-lookup"><span data-stu-id="6af6f-135">An event of a specific type must always provide its data in exactly the same order that is specified in the schema.</span></span> <span data-ttu-id="6af6f-136">Тем не менее цель события не должна использовать все предоставляемые ей данные.</span><span class="sxs-lookup"><span data-stu-id="6af6f-136">However, an event target does not have to consume all the data that is provided.</span></span>  
  
#### <a name="event-categorization"></a><span data-ttu-id="6af6f-137">Категоризация событий</span><span class="sxs-lookup"><span data-stu-id="6af6f-137">Event Categorization</span></span>  
 <span data-ttu-id="6af6f-138">При обработке расширенных событий используется модель категоризации событий, подобная отслеживанию событий для Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="6af6f-138">Extended Events uses an event categorization model similar to Event Tracing for Windows (ETW).</span></span> <span data-ttu-id="6af6f-139">Для категоризации событий используются два свойства, канал и ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="6af6f-139">Two event properties are used for categorization, channel and keyword.</span></span> <span data-ttu-id="6af6f-140">Тем самым поддерживается интеграция обработки расширенных событий с ETW и его средствами.</span><span class="sxs-lookup"><span data-stu-id="6af6f-140">Using these properties supports the integration of Extended Events with ETW and its tools.</span></span>  
  
 <span data-ttu-id="6af6f-141">**Канал**</span><span class="sxs-lookup"><span data-stu-id="6af6f-141">**Channel**</span></span>  
  
 <span data-ttu-id="6af6f-142">Канал определяет аудиторию события.</span><span class="sxs-lookup"><span data-stu-id="6af6f-142">A channel identifies the audience for an event.</span></span> <span data-ttu-id="6af6f-143">Объяснения каналов приводятся в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="6af6f-143">These channels are described in the following table.</span></span>  
  
|<span data-ttu-id="6af6f-144">Термин</span><span class="sxs-lookup"><span data-stu-id="6af6f-144">Term</span></span>|<span data-ttu-id="6af6f-145">Определение</span><span class="sxs-lookup"><span data-stu-id="6af6f-145">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="6af6f-146">Административный</span><span class="sxs-lookup"><span data-stu-id="6af6f-146">Admin</span></span>|<span data-ttu-id="6af6f-147">События административного канала предназначены, прежде всего, для конечных пользователей, администраторов и службы поддержки.</span><span class="sxs-lookup"><span data-stu-id="6af6f-147">Admin events are primarily targeted to the end users, administrators, and support.</span></span> <span data-ttu-id="6af6f-148">События в канале «Административный» указывают на неполадку с явно определенным решением, которую может устранить администратор.</span><span class="sxs-lookup"><span data-stu-id="6af6f-148">The events that are found in the admin channels indicate a problem with a well-defined solution that an administrator can act on.</span></span> <span data-ttu-id="6af6f-149">Примером события административного канала может служить отказ приложения подключиться к принтеру.</span><span class="sxs-lookup"><span data-stu-id="6af6f-149">An example of an admin event is when an application fails to connect to a printer.</span></span> <span data-ttu-id="6af6f-150">Такие события хорошо документированы или имеют связанное с ними сообщение, объясняющее пользователю, что нужно сделать для решения проблемы.</span><span class="sxs-lookup"><span data-stu-id="6af6f-150">These events are either well-documented or have a message associated with them that tells the reader what to do to rectify the problem.</span></span>|  
|<span data-ttu-id="6af6f-151">Операционный</span><span class="sxs-lookup"><span data-stu-id="6af6f-151">Operational</span></span>|<span data-ttu-id="6af6f-152">События операционного канала используются для анализа и диагностики проблемы или наступления события.</span><span class="sxs-lookup"><span data-stu-id="6af6f-152">Operational events are used for analyzing and diagnosing a problem or occurrence.</span></span> <span data-ttu-id="6af6f-153">Они могут использоваться для запуска инструментальных средств или задач, исходя из проблемы или происхождения события.</span><span class="sxs-lookup"><span data-stu-id="6af6f-153">They can be used to trigger tools or tasks based on the problem or occurrence.</span></span> <span data-ttu-id="6af6f-154">Примером оперативного события может служить добавление или удаление принтера из системы.</span><span class="sxs-lookup"><span data-stu-id="6af6f-154">An example of an operational event is when a printer is added or removed from a system.</span></span>|  
|<span data-ttu-id="6af6f-155">Аналитический</span><span class="sxs-lookup"><span data-stu-id="6af6f-155">Analytic</span></span>|<span data-ttu-id="6af6f-156">События аналитического канала публикуются в больших объемах.</span><span class="sxs-lookup"><span data-stu-id="6af6f-156">Analytic events are published in high volume.</span></span> <span data-ttu-id="6af6f-157">Они описывают функционирование программы и обычно используются для изучения производительности.</span><span class="sxs-lookup"><span data-stu-id="6af6f-157">They describe program operation and are typically used in performance investigations.</span></span>|  
|<span data-ttu-id="6af6f-158">Отладка</span><span class="sxs-lookup"><span data-stu-id="6af6f-158">Debug</span></span>|<span data-ttu-id="6af6f-159">Отладочные события используются только разработчиками для диагностики проблемы при отладке.</span><span class="sxs-lookup"><span data-stu-id="6af6f-159">Debug events are used solely by developers to diagnose a problem for debugging.</span></span><br /><br /> <span data-ttu-id="6af6f-160">Примечание. события в канале отладки возвращают внутренние данные о состоянии для конкретной реализации.</span><span class="sxs-lookup"><span data-stu-id="6af6f-160">Note: Events in the Debug channel return internal implementation-specific state data.</span></span> <span data-ttu-id="6af6f-161">Схемы и данные, возвращаемые событиями, могут измениться или стать недопустимыми в следующих выпусках SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6af6f-161">The schemas and data that the events return may change or become invalid in future versions of SQL Server.</span></span> <span data-ttu-id="6af6f-162">Поэтому события в канале отладки в следующих выпусках SQL Server могут быть изменены или удалены без уведомления.</span><span class="sxs-lookup"><span data-stu-id="6af6f-162">Therefore, events in the Debug channel may change or be removed in future versions of SQL Server without notice.</span></span>|  
  
 <span data-ttu-id="6af6f-163">**Ключевое слово**</span><span class="sxs-lookup"><span data-stu-id="6af6f-163">**Keyword**</span></span>  
  
 <span data-ttu-id="6af6f-164">Канал «Ключевое слово» зависит от приложения, оно позволяет выполнять высокодетализированное группирование связанных событий, облегчающее определение и получение событий, которые нужно использовать в сеансе.</span><span class="sxs-lookup"><span data-stu-id="6af6f-164">A keyword is application specific and enables a finer-grained grouping of related events, which makes it easier for you to specify and retrieve an event that you want to use in a session.</span></span> <span data-ttu-id="6af6f-165">Для получения сведений о ключевых словах можно выполнить следующий запрос.</span><span class="sxs-lookup"><span data-stu-id="6af6f-165">You can use the following query to obtain keyword information.</span></span>  
  
```  
select map_value Keyword from sys.dm_xe_map_values  
where name = 'keyword_map'  
```  
  
> [!NOTE]  
>  <span data-ttu-id="6af6f-166">Ключевые слова наиболее точно соответствуют текущему группированию событий трассировки SQL.</span><span class="sxs-lookup"><span data-stu-id="6af6f-166">Keywords map closely to the current grouping of SQL Trace events.</span></span>  
  
### <a name="targets"></a><span data-ttu-id="6af6f-167">Целевые объекты</span><span class="sxs-lookup"><span data-stu-id="6af6f-167">Targets</span></span>  
 <span data-ttu-id="6af6f-168">Цели являются объектами-получателями событий.</span><span class="sxs-lookup"><span data-stu-id="6af6f-168">Targets are event consumers.</span></span> <span data-ttu-id="6af6f-169">Цели обрабатывают события или синхронно в потоке, запускающем событие, или асинхронно в потоке, предоставленном системой.</span><span class="sxs-lookup"><span data-stu-id="6af6f-169">Targets process events, either synchronously on the thread that fires the event or asynchronously on a system provided thread.</span></span> <span data-ttu-id="6af6f-170">Расширенные события предоставляют несколько целей, которые можно использовать по собственному усмотрению для направления выхода событий.</span><span class="sxs-lookup"><span data-stu-id="6af6f-170">Extended Events provides several targets that you can use as appropriate for directing event output.</span></span> <span data-ttu-id="6af6f-171">Дополнительные сведения см. в статье [SQL Server Extended Events Targets](../../database-engine/sql-server-extended-events-targets.md).</span><span class="sxs-lookup"><span data-stu-id="6af6f-171">For more information, see [SQL Server Extended Events Targets](../../database-engine/sql-server-extended-events-targets.md).</span></span>  
  
### <a name="actions"></a><span data-ttu-id="6af6f-172">Действия</span><span class="sxs-lookup"><span data-stu-id="6af6f-172">Actions</span></span>  
 <span data-ttu-id="6af6f-173">Действие — это программный ответ или серия ответов на событие.</span><span class="sxs-lookup"><span data-stu-id="6af6f-173">An action is a programmatic response or series of responses to an event.</span></span> <span data-ttu-id="6af6f-174">Действия привязаны к событию, и каждое событие может иметь уникальный набор действий.</span><span class="sxs-lookup"><span data-stu-id="6af6f-174">Actions are bound to an event, and each event may have a unique set of actions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6af6f-175">Действия, предназначенные для конкретного набора событий, не могут быть привязаны к неизвестным событиям.</span><span class="sxs-lookup"><span data-stu-id="6af6f-175">Actions that are intended for a specific set of events cannot bind to unknown events.</span></span>  
  
 <span data-ttu-id="6af6f-176">Действие, связанное с событием, вызывается синхронно в потоке, запустившем это событие.</span><span class="sxs-lookup"><span data-stu-id="6af6f-176">An action bound to an event is invoked synchronously on the thread that fired the event.</span></span> <span data-ttu-id="6af6f-177">Существует много типов действий, имеющих широкий диапазон возможностей.</span><span class="sxs-lookup"><span data-stu-id="6af6f-177">There are many types of actions and they have a wide range of capabilities.</span></span> <span data-ttu-id="6af6f-178">Действия могут выполнять следующие функции.</span><span class="sxs-lookup"><span data-stu-id="6af6f-178">Actions can:</span></span>  
  
-   <span data-ttu-id="6af6f-179">Собирать дампы стека и просматривать данные.</span><span class="sxs-lookup"><span data-stu-id="6af6f-179">Capture a stack dump and inspect data.</span></span>  
  
-   <span data-ttu-id="6af6f-180">Сохранять сведения о состоянии хранения в локальном контексте, используя различные хранилища.</span><span class="sxs-lookup"><span data-stu-id="6af6f-180">Store state information in a local context using variable storage.</span></span>  
  
-   <span data-ttu-id="6af6f-181">Собирать статистические данные о событиях.</span><span class="sxs-lookup"><span data-stu-id="6af6f-181">Aggregate event data.</span></span>  
  
-   <span data-ttu-id="6af6f-182">Присоединять данные к данным события.</span><span class="sxs-lookup"><span data-stu-id="6af6f-182">Append data to event data.</span></span>  
  
 <span data-ttu-id="6af6f-183">Ниже проводятся несколько типичных, хорошо известных примеров.</span><span class="sxs-lookup"><span data-stu-id="6af6f-183">Some typical and well known examples of actions are:</span></span>  
  
-   <span data-ttu-id="6af6f-184">Сборщик данных стека</span><span class="sxs-lookup"><span data-stu-id="6af6f-184">Stack dumper</span></span>  
  
-   <span data-ttu-id="6af6f-185">Определение плана выполнения (только для[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="6af6f-185">Execution plan detection ([!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] only)</span></span>  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="6af6f-186">Сбор данных стека (только для[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="6af6f-186">stack collection ([!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] only)</span></span>  
  
-   <span data-ttu-id="6af6f-187">Вычисление статистики времени выполнения</span><span class="sxs-lookup"><span data-stu-id="6af6f-187">Run time statistics calculation</span></span>  
  
-   <span data-ttu-id="6af6f-188">Сбор пользовательского ввода для обработки исключений</span><span class="sxs-lookup"><span data-stu-id="6af6f-188">Gather user input on exception</span></span>  
  
### <a name="predicates"></a><span data-ttu-id="6af6f-189">Предикаты</span><span class="sxs-lookup"><span data-stu-id="6af6f-189">Predicates</span></span>  
 <span data-ttu-id="6af6f-190">Предикаты представляют собой набор логических правил, которые используются для оценки событий при их обработке.</span><span class="sxs-lookup"><span data-stu-id="6af6f-190">Predicates are a set of logical rules that are used to evaluate events when they are processed.</span></span> <span data-ttu-id="6af6f-191">Благодаря этому пользователь подсистемы расширенных событий получает возможность избирательно получать данные события на основе заданных критериев.</span><span class="sxs-lookup"><span data-stu-id="6af6f-191">This enables the Extended Events user to selectively capture event data based on specific criteria.</span></span>  
  
 <span data-ttu-id="6af6f-192">Предикаты могут сохранять данные в локальном контексте, который можно использовать для создания предикатов, возвращающих значение TRUE каждые *n* минут или каждые *n* раз при запуске события.</span><span class="sxs-lookup"><span data-stu-id="6af6f-192">Predicates can store data in a local context that can be used for creating predicates that return true once every *n* minutes or every *n* times that an event fires.</span></span> <span data-ttu-id="6af6f-193">С помощью такого хранилища в локальном контексте можно динамически обновлять предикаты, тем самым подавляя последующий запуск событий, содержащих подобные данные.</span><span class="sxs-lookup"><span data-stu-id="6af6f-193">This local context storage can also be used to dynamically update the predicate, thereby suppressing future event firing if the events contain similar data.</span></span>  
  
 <span data-ttu-id="6af6f-194">Предикаты имеют способность получать сведения о контексте, например идентификатор потока, а также определенные данные события.</span><span class="sxs-lookup"><span data-stu-id="6af6f-194">Predicates have the ability to retrieve context information, such as the thread ID, as well as event specific data.</span></span> <span data-ttu-id="6af6f-195">Предикаты оцениваются как полноценные логические выражения и поддерживают сокращенное вычисление в первой точке, в которой все выражение оказывается ложным.</span><span class="sxs-lookup"><span data-stu-id="6af6f-195">Predicates are evaluated as full Boolean expressions, and support short circuiting at the first point where the entire expression is found to be false.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6af6f-196">Предикаты с побочными эффектами могут не оцениваться, если проверка предыдущего предиката завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="6af6f-196">Predicates with side effects may not be evaluated if an earlier predicate check fails.</span></span>  
  
### <a name="types"></a><span data-ttu-id="6af6f-197">Типы</span><span class="sxs-lookup"><span data-stu-id="6af6f-197">Types</span></span>  
 <span data-ttu-id="6af6f-198">Поскольку данные являются набором связанных байтов, для интерпретации данных необходимы длина и характеристики набора байтов.</span><span class="sxs-lookup"><span data-stu-id="6af6f-198">Because data is a collection of bytes strung together, the length and characteristics of the byte collection are required in order to interpret the data.</span></span> <span data-ttu-id="6af6f-199">Следующие сведения содержатся в объекте Type.</span><span class="sxs-lookup"><span data-stu-id="6af6f-199">This information is encapsulated in the Type object.</span></span> <span data-ttu-id="6af6f-200">Для объектов пакета представлены следующие типы:</span><span class="sxs-lookup"><span data-stu-id="6af6f-200">The following types are provided for package objects:</span></span>  
  
-   <span data-ttu-id="6af6f-201">event</span><span class="sxs-lookup"><span data-stu-id="6af6f-201">event</span></span>  
  
-   <span data-ttu-id="6af6f-202">action</span><span class="sxs-lookup"><span data-stu-id="6af6f-202">action</span></span>  
  
-   <span data-ttu-id="6af6f-203">target</span><span class="sxs-lookup"><span data-stu-id="6af6f-203">target</span></span>  
  
-   <span data-ttu-id="6af6f-204">pred_source;</span><span class="sxs-lookup"><span data-stu-id="6af6f-204">pred_source</span></span>  
  
-   <span data-ttu-id="6af6f-205">pred_compare;</span><span class="sxs-lookup"><span data-stu-id="6af6f-205">pred_compare</span></span>  
  
-   <span data-ttu-id="6af6f-206">тип</span><span class="sxs-lookup"><span data-stu-id="6af6f-206">type</span></span>  
  
 <span data-ttu-id="6af6f-207">Дополнительные сведения см. в разделе [sys.dm_xe_objects (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6af6f-207">For more information, see [sys.dm_xe_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-objects-transact-sql).</span></span>  
  
### <a name="maps"></a><span data-ttu-id="6af6f-208">Maps</span><span class="sxs-lookup"><span data-stu-id="6af6f-208">Maps</span></span>  
 <span data-ttu-id="6af6f-209">Таблица соответствий устанавливает соответствие внутреннего значения строке, что дает пользователю возможность узнать, что именно представляет это значение.</span><span class="sxs-lookup"><span data-stu-id="6af6f-209">A map table maps an internal value to a string, which enables a user to know what the value represents.</span></span> <span data-ttu-id="6af6f-210">В результате пользователь может получить значимое описание внутреннего значения, а не числовое значение.</span><span class="sxs-lookup"><span data-stu-id="6af6f-210">Instead of only being able to obtain a numeric value, a user can get a meaningful description of the internal value.</span></span> <span data-ttu-id="6af6f-211">В следующем запросе показан способ установки соответствий.</span><span class="sxs-lookup"><span data-stu-id="6af6f-211">The following query shows how to obtain map values.</span></span>  
  
```  
select map_key, map_value from sys.dm_xe_map_values  
where name = 'lock_mode'  
```  
  
 <span data-ttu-id="6af6f-212">Предыдущий запрос представил следующий вывод.</span><span class="sxs-lookup"><span data-stu-id="6af6f-212">The preceding query produces the following output.</span></span>  
  
 `map_key     map_value`  
  
 `---------------------`  
  
 `0           NL`  
  
 `1           SCH_S`  
  
 `2           SCH_M`  
  
 `3           S`  
  
 `4           U`  
  
 `5           X`  
  
 `6           IS`  
  
 `7           IU`  
  
 `8           IX`  
  
 `9           SIU`  
  
 `10          SIX`  
  
 `11          UIX`  
  
 `12          BU`  
  
 `13          RS_S`  
  
 `14          RS_U`  
  
 `15          RI_NL`  
  
 `16          RI_S`  
  
 `17          RI_U`  
  
 `18          RI_X`  
  
 `19          RX_S`  
  
 `20          RX_U`  
  
 `21          RX_X`  
  
 `21          RX_X`  
  
 <span data-ttu-id="6af6f-213">Используя эту таблицу в качестве примера, предположим, что имеется столбец с именем mode и значением 5.</span><span class="sxs-lookup"><span data-stu-id="6af6f-213">Using this table as an example, assume that you have a column named mode, and its value is 5.</span></span> <span data-ttu-id="6af6f-214">В таблице указано, что значение 5 соответствует X, а это означает тип блокировки «Монопольная».</span><span class="sxs-lookup"><span data-stu-id="6af6f-214">The table indicates that 5 maps to X, which means the lock type is Exclusive.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6af6f-215">См. также:</span><span class="sxs-lookup"><span data-stu-id="6af6f-215">See Also</span></span>  
 <span data-ttu-id="6af6f-216">[Сеансы расширенных событий SQL Server](sql-server-extended-events-sessions.md) </span><span class="sxs-lookup"><span data-stu-id="6af6f-216">[SQL Server Extended Events Sessions](sql-server-extended-events-sessions.md) </span></span>  
 <span data-ttu-id="6af6f-217">[Подсистема расширенных событий SQL Server](sql-server-extended-events-engine.md) </span><span class="sxs-lookup"><span data-stu-id="6af6f-217">[SQL Server Extended Events Engine](sql-server-extended-events-engine.md) </span></span>  
 [<span data-ttu-id="6af6f-218">Цели расширенных событий SQL Server</span><span class="sxs-lookup"><span data-stu-id="6af6f-218">SQL Server Extended Events Targets</span></span>](../../database-engine/sql-server-extended-events-targets.md)  
  
  
