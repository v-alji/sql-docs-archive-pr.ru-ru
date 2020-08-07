---
title: Категория событий "Ошибки и предупреждения" (ядро СУБД) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- Errors and Warnings event category [SQL Server]
- SQL Server event classes, Errors and Warnings event category
- event classes [SQL Server], Errors and Warnings event category
ms.assetid: 249c19b5-af68-4433-80f6-337395176641
author: stevestein
ms.author: sstein
ms.openlocfilehash: d55f37f5401f60ddfeec340af1ae6d532eb6ad01
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735233"
---
# <a name="errors-and-warnings-event-category-database-engine"></a><span data-ttu-id="0086a-102">Категория событий Errors and Warnings (компонент Database Engine)</span><span class="sxs-lookup"><span data-stu-id="0086a-102">Errors and Warnings Event Category (Database Engine)</span></span>
  <span data-ttu-id="0086a-103">В категорию событий **Ошибки и предупреждения** входят общие события ошибок и предупреждений.</span><span class="sxs-lookup"><span data-stu-id="0086a-103">The **Errors and Warnings** event category contains general error and warning events.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0086a-104">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="0086a-104">In This Section</span></span>  
  
|<span data-ttu-id="0086a-105">Раздел</span><span class="sxs-lookup"><span data-stu-id="0086a-105">Topic</span></span>|<span data-ttu-id="0086a-106">Description</span><span class="sxs-lookup"><span data-stu-id="0086a-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="0086a-107">Класс событий Attention</span><span class="sxs-lookup"><span data-stu-id="0086a-107">Attention Event Class</span></span>](attention-event-class.md)|<span data-ttu-id="0086a-108">Указывает, что произошло событие **Внимание** .</span><span class="sxs-lookup"><span data-stu-id="0086a-108">Indicates that an **Attention** event has occurred.</span></span>|  
|[<span data-ttu-id="0086a-109">Класс событий Background Job Error</span><span class="sxs-lookup"><span data-stu-id="0086a-109">Background Job Error Event Class</span></span>](background-job-error-event-class.md)|<span data-ttu-id="0086a-110">Указывает, что фоновое задание завершилось ненормально.</span><span class="sxs-lookup"><span data-stu-id="0086a-110">Indicates that a background job has terminated abnormally.</span></span>|  
|[<span data-ttu-id="0086a-111">Класс событий Bitmap Warning</span><span class="sxs-lookup"><span data-stu-id="0086a-111">Bitmap Warning Event Class</span></span>](bitmap-warning-event-class.md)|<span data-ttu-id="0086a-112">Указывает, что в запросе отключена фильтрация по битовым картам.</span><span class="sxs-lookup"><span data-stu-id="0086a-112">Indicates that bitmap filtering has been disabled in a query.</span></span>|  
|[<span data-ttu-id="0086a-113">Класс событий Blocked Process Report</span><span class="sxs-lookup"><span data-stu-id="0086a-113">Blocked Process Report Event Class</span></span>](blocked-process-report-event-class.md)|<span data-ttu-id="0086a-114">Указывает, что задача заблокирована дольше указанного времени.</span><span class="sxs-lookup"><span data-stu-id="0086a-114">Indicates that a task has been blocked for more than a specified amount of time.</span></span>|  
|[<span data-ttu-id="0086a-115">Класс событий CPU Threshold Exceeded</span><span class="sxs-lookup"><span data-stu-id="0086a-115">CPU Threshold Exceeded Event Class</span></span>](cpu-threshold-exceeded-event-class.md)|<span data-ttu-id="0086a-116">Указывает, что регулятор ресурсов обнаружил запрос, превышающий заданное пороговое значение загрузки ЦП.</span><span class="sxs-lookup"><span data-stu-id="0086a-116">Indicates that the Resource Governor detects a query that exceeds the specified CPU threshold.</span></span>|  
|[<span data-ttu-id="0086a-117">Класс событий ErrorLog</span><span class="sxs-lookup"><span data-stu-id="0086a-117">ErrorLog Event Class</span></span>](errorlog-event-class.md)|<span data-ttu-id="0086a-118">Показывает, что связанные с ошибками события были записаны в журнал ошибок сервера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0086a-118">Indicates that error events have been logged in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log.</span></span>|  
|[<span data-ttu-id="0086a-119">Класс событий EventLog</span><span class="sxs-lookup"><span data-stu-id="0086a-119">EventLog Event Class</span></span>](eventlog-event-class.md)|<span data-ttu-id="0086a-120">Указывает, что события были записаны в журнал событий Windows.</span><span class="sxs-lookup"><span data-stu-id="0086a-120">Indicates that events have been logged in the Windows event log.</span></span>|  
|[<span data-ttu-id="0086a-121">Класс событий Exception</span><span class="sxs-lookup"><span data-stu-id="0086a-121">Exception Event Class</span></span>](exception-event-class.md)|<span data-ttu-id="0086a-122">Указывает, что в сервере [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]произошло исключение.</span><span class="sxs-lookup"><span data-stu-id="0086a-122">Indicates that an exception has occurred in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="0086a-123">Класс событий Exchange Spill</span><span class="sxs-lookup"><span data-stu-id="0086a-123">Exchange Spill Event Class</span></span>](exchange-spill-event-class.md)|<span data-ttu-id="0086a-124">Указывает, что буферы связи в параллельном плане запроса были записаны в базу данных tempdb.</span><span class="sxs-lookup"><span data-stu-id="0086a-124">Indicates that communication buffers in a parallel query plan have been written to the tempdb database.</span></span>|  
|[<span data-ttu-id="0086a-125">Класс событий Execution Warnings</span><span class="sxs-lookup"><span data-stu-id="0086a-125">Execution Warnings Event Class</span></span>](execution-warnings-event-class.md)|<span data-ttu-id="0086a-126">Указывает, что за время выполнения инструкции или хранимой процедуры сервера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] были выданы предупреждения предоставления памяти.</span><span class="sxs-lookup"><span data-stu-id="0086a-126">Indicates that memory grant warnings occurred during the execution of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] statement or stored procedure.</span></span>|  
|[<span data-ttu-id="0086a-127">Класс событий Hash Warning</span><span class="sxs-lookup"><span data-stu-id="0086a-127">Hash Warning Event Class</span></span>](hash-warning-event-class.md)|<span data-ttu-id="0086a-128">Указывает, что во время операции хэширования произошли рекурсия или аварийное хэширование.</span><span class="sxs-lookup"><span data-stu-id="0086a-128">Indicates that a hash recursion or hash bailout has occurred during a hashing operation.</span></span>|  
|[<span data-ttu-id="0086a-129">Класс событий Missing Column Statistics</span><span class="sxs-lookup"><span data-stu-id="0086a-129">Missing Column Statistics Event Class</span></span>](missing-column-statistics-event-class.md)|<span data-ttu-id="0086a-130">Указывает, что статистические данные столбцов, которые были бы полезны оптимизатору, недоступны.</span><span class="sxs-lookup"><span data-stu-id="0086a-130">Indicates that column statistics that could have been useful for the optimizer are not available.</span></span>|  
|[<span data-ttu-id="0086a-131">Класс событий Missing Join Predicate</span><span class="sxs-lookup"><span data-stu-id="0086a-131">Missing Join Predicate Event Class</span></span>](missing-join-predicate-event-class.md)|<span data-ttu-id="0086a-132">Указывает, что выполняется запрос, не имеющий предиката соединения.</span><span class="sxs-lookup"><span data-stu-id="0086a-132">Indicates that a query is being executed that has no join predicate.</span></span>|  
|[<span data-ttu-id="0086a-133">Класс событий Sort Warnings</span><span class="sxs-lookup"><span data-stu-id="0086a-133">Sort Warnings Event Class</span></span>](sort-warnings-event-class.md)|<span data-ttu-id="0086a-134">Указывает, что операциям сортировки не хватает памяти.</span><span class="sxs-lookup"><span data-stu-id="0086a-134">Indicates that sort operations do not fit into memory.</span></span>|  
|[<span data-ttu-id="0086a-135">Класс событий User Error Message</span><span class="sxs-lookup"><span data-stu-id="0086a-135">User Error Message Event Class</span></span>](user-error-message-event-class.md)|<span data-ttu-id="0086a-136">Отображаются сообщения об ошибках, видимые пользователю.</span><span class="sxs-lookup"><span data-stu-id="0086a-136">Displays error messages that are seen by the user.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0086a-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="0086a-137">See Also</span></span>  
 [<span data-ttu-id="0086a-138">Хранимая процедура sp_trace_setevent (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0086a-138">sp_trace_setevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  
