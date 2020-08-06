---
title: Категория событий Performance | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- SQL Server event classes, Performance event category
- Performance event category [SQL Server]
- event classes [SQL Server], Performance event category
ms.assetid: 708f3585-d8be-4980-bbff-672d7c59397e
author: stevestein
ms.author: sstein
ms.openlocfilehash: b0c076a4132298797313ecbf0874d9d2d4e453cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666032"
---
# <a name="performance-event-category"></a><span data-ttu-id="df1b3-102">Категория событий Performance</span><span class="sxs-lookup"><span data-stu-id="df1b3-102">Performance Event Category</span></span>
  <span data-ttu-id="df1b3-103">Категория событий **Performance** используется для контроля классов событий **Showplan** и классов событий, формируемых при выполнении операторов SQL языка DML.</span><span class="sxs-lookup"><span data-stu-id="df1b3-103">Use the **Performance** event category to monitor **Showplan** event classes and event classes that are produced from the execution of SQL data manipulation language (DML) operators.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="df1b3-104">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="df1b3-104">In This Section</span></span>  
  
|<span data-ttu-id="df1b3-105">Раздел</span><span class="sxs-lookup"><span data-stu-id="df1b3-105">Topic</span></span>|<span data-ttu-id="df1b3-106">Description</span><span class="sxs-lookup"><span data-stu-id="df1b3-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="df1b3-107">Класс событий Auto Stats</span><span class="sxs-lookup"><span data-stu-id="df1b3-107">Auto Stats Event Class</span></span>](auto-stats-event-class.md)|<span data-ttu-id="df1b3-108">Указывает, что произошло автоматическое обновление статистики индекса и столбца.</span><span class="sxs-lookup"><span data-stu-id="df1b3-108">Indicates that an automatic updating of index and column statistics has occurred.</span></span>|  
|[<span data-ttu-id="df1b3-109">Класс событий Degree of Parallelism (7.0 Insert)</span><span class="sxs-lookup"><span data-stu-id="df1b3-109">Degree of Parallelism &#40;7.0 Insert&#41; Event Class</span></span>](degree-of-parallelism-7-0-insert-event-class.md)|<span data-ttu-id="df1b3-110">Указывает, что в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] инструкции SELECT, INSERT, UPDATE или DELETE были выполнены с использованием последовательного или параллельного плана.</span><span class="sxs-lookup"><span data-stu-id="df1b3-110">Indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has executed a SELECT, INSERT, UPDATE, or DELETE statement using either a serial or parallel plan.</span></span> <span data-ttu-id="df1b3-111">В отчет также включается количество ЦП, использованных для выполнения операции.</span><span class="sxs-lookup"><span data-stu-id="df1b3-111">The number of CPUs used to perform the operation is also reported.</span></span>|  
|[<span data-ttu-id="df1b3-112">Класс событий Performance Statistics</span><span class="sxs-lookup"><span data-stu-id="df1b3-112">Performance Statistics Event Class</span></span>](performance-statistics-event-class.md)|<span data-ttu-id="df1b3-113">Наблюдает за производительностью выполняемых запросов.</span><span class="sxs-lookup"><span data-stu-id="df1b3-113">Monitors performance of the queries that are being executed.</span></span>|  
|[<span data-ttu-id="df1b3-114">Класс событий Showplan All</span><span class="sxs-lookup"><span data-stu-id="df1b3-114">Showplan All Event Class</span></span>](showplan-all-event-class.md)|<span data-ttu-id="df1b3-115">Идентифицирует операторы **Showplan** в инструкции SQL.</span><span class="sxs-lookup"><span data-stu-id="df1b3-115">Identifies **Showplan** operators within a SQL statement.</span></span>|  
|[<span data-ttu-id="df1b3-116">Класс событий Showplan All for Query Compile</span><span class="sxs-lookup"><span data-stu-id="df1b3-116">Showplan All for Query Compile Event Class</span></span>](showplan-all-for-query-compile-event-class.md)|<span data-ttu-id="df1b3-117">Отображает данные компиляции для операторов **Showplan** .</span><span class="sxs-lookup"><span data-stu-id="df1b3-117">Displays compile time data for **Showplan** operators.</span></span>|  
|[<span data-ttu-id="df1b3-118">Класс событий Showplan Statistics Profile</span><span class="sxs-lookup"><span data-stu-id="df1b3-118">Showplan Statistics Profile Event Class</span></span>](showplan-statistics-profile-event-class.md)|<span data-ttu-id="df1b3-119">Отображает предполагаемую стоимость запроса.</span><span class="sxs-lookup"><span data-stu-id="df1b3-119">Displays the estimated cost of a query.</span></span>|  
|[<span data-ttu-id="df1b3-120">Класс событий Showplan XML</span><span class="sxs-lookup"><span data-stu-id="df1b3-120">Showplan XML Event Class</span></span>](showplan-xml-event-class.md)|<span data-ttu-id="df1b3-121">Идентифицирует операторы **Showplan** в инструкции SQL.</span><span class="sxs-lookup"><span data-stu-id="df1b3-121">Identifies the **Showplan** operators in a SQL statement.</span></span> <span data-ttu-id="df1b3-122">Класс событий хранит описание каждого события как правильный XML-документ.</span><span class="sxs-lookup"><span data-stu-id="df1b3-122">The event class stores each event as a well defined XML document.</span></span>|  
|[<span data-ttu-id="df1b3-123">Класс событий Showplan XML for Query Compile</span><span class="sxs-lookup"><span data-stu-id="df1b3-123">Showplan XML for Query Compile Event Class</span></span>](showplan-xml-for-query-compile-event-class.md)|<span data-ttu-id="df1b3-124">Отображает данные компиляции для операторов **Showplan** в формате XML.</span><span class="sxs-lookup"><span data-stu-id="df1b3-124">Displays compile time data for **Showplan** operators in XML format.</span></span>|  
|[<span data-ttu-id="df1b3-125">Класс событий Showplan XML Statistics Profile</span><span class="sxs-lookup"><span data-stu-id="df1b3-125">Showplan XML Statistics Profile Event Class</span></span>](showplan-xml-statistics-profile-event-class.md)|<span data-ttu-id="df1b3-126">Идентифицирует операторы **Showplan** , связанные с инструкцией SQL.</span><span class="sxs-lookup"><span data-stu-id="df1b3-126">Identifies the **Showplan** operators associated with a SQL statement.</span></span> <span data-ttu-id="df1b3-127">Выходом является XML-документ.</span><span class="sxs-lookup"><span data-stu-id="df1b3-127">The output is an XML document.</span></span>|  
|[<span data-ttu-id="df1b3-128">Класс событий SQL:FullTextQuery</span><span class="sxs-lookup"><span data-stu-id="df1b3-128">SQL:FullTextQuery Event Class</span></span>](sql-fulltextquery-event-class.md)|<span data-ttu-id="df1b3-129">Указывает на то, что [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] завершил выполнение полнотекстового запроса.</span><span class="sxs-lookup"><span data-stu-id="df1b3-129">Indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has executed a full-text query.</span></span>|  
|[<span data-ttu-id="df1b3-130">Класс событий Plan Guide Successful</span><span class="sxs-lookup"><span data-stu-id="df1b3-130">Plan Guide Successful Event Class</span></span>](plan-guide-successful-event-class.md)|<span data-ttu-id="df1b3-131">Указывает, что в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] успешно создан план выполнения для запроса или пакета, в котором содержится структура плана.</span><span class="sxs-lookup"><span data-stu-id="df1b3-131">Indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] successfully produced an execution plan for a query or batch that contained a plan guide.</span></span>|  
|[<span data-ttu-id="df1b3-132">Класс событий Plan Guide Unsuccessful</span><span class="sxs-lookup"><span data-stu-id="df1b3-132">Plan Guide Unsuccessful Event Class</span></span>](plan-guide-unsuccessful-event-class.md)|<span data-ttu-id="df1b3-133">Указывает, что [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не удалось создать план выполнения для запроса или пакета, в котором содержится структура плана.</span><span class="sxs-lookup"><span data-stu-id="df1b3-133">Indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] could not produce an execution plan for a query or batch that contained a plan guide.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="df1b3-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="df1b3-134">See Also</span></span>  
 [<span data-ttu-id="df1b3-135">Расширенные события</span><span class="sxs-lookup"><span data-stu-id="df1b3-135">Extended Events</span></span>](../extended-events/extended-events.md)  
  
  
