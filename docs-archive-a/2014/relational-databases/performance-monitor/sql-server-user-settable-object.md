---
title: SQL Server, объект User Settable | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- User Settable object
- SQLServer:User Settable
ms.assetid: 633de3ef-533c-4f0c-9c7b-c105129d8e94
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7243ab4767c8de93dccf4556f136a94b47554d3d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729390"
---
# <a name="sql-server-user-settable-object"></a><span data-ttu-id="56cd8-102">SQL Server, объект User Settable</span><span class="sxs-lookup"><span data-stu-id="56cd8-102">SQL Server, User Settable Object</span></span>
  <span data-ttu-id="56cd8-103">В Microsoft **объект** User Settable [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] позволяет создавать пользовательские экземпляры счетчиков,</span><span class="sxs-lookup"><span data-stu-id="56cd8-103">The **User Settable** object in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] allows you to create custom counter instances.</span></span> <span data-ttu-id="56cd8-104">которые используются для контроля тех характеристик сервера, которые нельзя отследить при использовании существующих счетчиков, какими являются, например компоненты, уникальные для вашей базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] : число зарегистрированных заказов или опись продукции.</span><span class="sxs-lookup"><span data-stu-id="56cd8-104">Use custom counter instances to monitor aspects of the server not monitored by existing counters, such as components unique to your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database (for example, the number of customer orders logged or the product inventory).</span></span>  
  
 <span data-ttu-id="56cd8-105">В объекте **User Settable** содержится 10 экземпляров счетчиков запросов: с **User counter 1** по **User counter 10**.</span><span class="sxs-lookup"><span data-stu-id="56cd8-105">The **User Settable** object contains 10 instances of the query counter: **User counter 1** through **User counter 10**.</span></span> <span data-ttu-id="56cd8-106">Этим счетчикам соответствуют хранимые процедуры [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] от **sp_user_counter1** до **sp_user_counter10**.</span><span class="sxs-lookup"><span data-stu-id="56cd8-106">These counters map to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures **sp_user_counter1** through **sp_user_counter10**.</span></span> <span data-ttu-id="56cd8-107">Поскольку эти хранимые процедуры выполняются пользовательскими приложениями, значения, получаемые в результате выполнения хранимых процедур, отображаются в системном мониторе.</span><span class="sxs-lookup"><span data-stu-id="56cd8-107">As these stored procedures are executed by user applications, the values set by the stored procedures are displayed in System Monitor.</span></span> <span data-ttu-id="56cd8-108">Счетчик может контролировать любое целочисленное значение (например, хранимая процедура может подсчитывать, сколько заказов конкретного продукта было совершено за один день).</span><span class="sxs-lookup"><span data-stu-id="56cd8-108">A counter can monitor any single integer value (for example, a stored procedure that counts how many orders for a particular product have occurred in one day).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="56cd8-109">Хранимые процедуры пользовательских счетчиков системным монитором автоматически не опрашиваются.</span><span class="sxs-lookup"><span data-stu-id="56cd8-109">The user counter stored procedures are not polled automatically by System Monitor.</span></span> <span data-ttu-id="56cd8-110">Чтобы значения счетчика обновлялись, эти процедуры должны явным образом вызываться пользовательским приложением.</span><span class="sxs-lookup"><span data-stu-id="56cd8-110">They must be explicitly executed by a user application for the counter values to be updated.</span></span> <span data-ttu-id="56cd8-111">Для автоматического обновления значений счетчиков используйте триггеры.</span><span class="sxs-lookup"><span data-stu-id="56cd8-111">Use a trigger to update the value of the counter automatically.</span></span> <span data-ttu-id="56cd8-112">Например, для создания счетчика, который отслеживает число строк в таблице, создайте для этой таблицы триггер INSERT и DELETE, выполняющий следующую инструкцию: `SELECT COUNT(*) FROM table`.</span><span class="sxs-lookup"><span data-stu-id="56cd8-112">For example, to create a counter that monitors the number of rows in a table, create an INSERT and DELETE trigger on the table that executes the following statement: `SELECT COUNT(*) FROM table`.</span></span> <span data-ttu-id="56cd8-113">При каждом срабатывании триггера в результате выполнения в таблице операций INSERT или DELETE происходит автоматическое обновление счетчика в системном мониторе.</span><span class="sxs-lookup"><span data-stu-id="56cd8-113">Whenever the trigger is fired because of an INSERT or DELETE operation occurring on the table, the System Monitor counter is automatically updated.</span></span>  
  
 <span data-ttu-id="56cd8-114">В этой таблице приводится описание объекта [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **User Settable**.</span><span class="sxs-lookup"><span data-stu-id="56cd8-114">This table describes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **User Settable** object.</span></span>  
  
|<span data-ttu-id="56cd8-115">SQL Server, счетчики User Settable</span><span class="sxs-lookup"><span data-stu-id="56cd8-115">SQL Server User Settable counters</span></span>|<span data-ttu-id="56cd8-116">Описание</span><span class="sxs-lookup"><span data-stu-id="56cd8-116">Description</span></span>|  
|---------------------------------------|-----------------|  
|<span data-ttu-id="56cd8-117">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="56cd8-117">**Query**</span></span>|<span data-ttu-id="56cd8-118">Объект **User Settable** содержит счетчик запроса.</span><span class="sxs-lookup"><span data-stu-id="56cd8-118">The **User Settable** object contains the query counter.</span></span> <span data-ttu-id="56cd8-119">Пользователи настраивают **User counters** в рамках объекта запроса.</span><span class="sxs-lookup"><span data-stu-id="56cd8-119">Users configure the **User counters** within the query object.</span></span>|  
  
 <span data-ttu-id="56cd8-120">В данной таблице приводится описание **экземпляров** счетчика **Query** .</span><span class="sxs-lookup"><span data-stu-id="56cd8-120">This table describes the **instances** of the **Query** counter.</span></span>  
  
|<span data-ttu-id="56cd8-121">Экземпляры счетчиков запросов</span><span class="sxs-lookup"><span data-stu-id="56cd8-121">Query counter instances</span></span>|<span data-ttu-id="56cd8-122">Описание</span><span class="sxs-lookup"><span data-stu-id="56cd8-122">Description</span></span>|  
|-----------------------------|-----------------|  
|<span data-ttu-id="56cd8-123">**User counter 1**</span><span class="sxs-lookup"><span data-stu-id="56cd8-123">**User counter 1**</span></span>|<span data-ttu-id="56cd8-124">Определяется хранимой процедурой **sp_user_counter1**.</span><span class="sxs-lookup"><span data-stu-id="56cd8-124">Defined using **sp_user_counter1**.</span></span>|  
|<span data-ttu-id="56cd8-125">**User counter 2**</span><span class="sxs-lookup"><span data-stu-id="56cd8-125">**User counter 2**</span></span>|<span data-ttu-id="56cd8-126">Определяется хранимой процедурой **sp_user_counter2**.</span><span class="sxs-lookup"><span data-stu-id="56cd8-126">Defined using **sp_user_counter2**.</span></span>|  
|<span data-ttu-id="56cd8-127">**User counter 3**</span><span class="sxs-lookup"><span data-stu-id="56cd8-127">**User counter 3**</span></span>|<span data-ttu-id="56cd8-128">Определяется хранимой процедурой **sp_user_counter3**.</span><span class="sxs-lookup"><span data-stu-id="56cd8-128">Defined using **sp_user_counter3**.</span></span>|  
|<span data-ttu-id="56cd8-129">...</span><span class="sxs-lookup"><span data-stu-id="56cd8-129">...</span></span>||  
|<span data-ttu-id="56cd8-130">**User counter 10**</span><span class="sxs-lookup"><span data-stu-id="56cd8-130">**User counter 10**</span></span>|<span data-ttu-id="56cd8-131">Определяется хранимой процедурой **sp_user_counter10**.</span><span class="sxs-lookup"><span data-stu-id="56cd8-131">Defined using **sp_user_counter10**.</span></span>|  
  
 <span data-ttu-id="56cd8-132">Хранимые процедуры пользовательских счетчиков запускаются из приложения с одним целочисленным параметром, представляющим новое значение счетчика.</span><span class="sxs-lookup"><span data-stu-id="56cd8-132">To make use of the user counter stored procedures, execute them from your own application with a single integer parameter representing the new value for the counter.</span></span> <span data-ttu-id="56cd8-133">Например, чтобы задать значение 10 для объекта **User counter 1** , выполните следующую инструкцию Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="56cd8-133">For example, to set **User counter 1** to the value 10, execute this Transact-SQL statement:</span></span>  
  
```  
EXECUTE sp_user_counter1 10  
```  
  
 <span data-ttu-id="56cd8-134">Хранимые процедуры пользовательских счетчиков можно вызывать из любого места, где могут быть вызваны любые другие (например пользовательские) хранимые процедуры.</span><span class="sxs-lookup"><span data-stu-id="56cd8-134">The user counter stored procedures can be called from anywhere other stored procedures can be called, such as your own stored procedures.</span></span> <span data-ttu-id="56cd8-135">Например, можно создать следующую хранимую процедуру для подсчета числа и попыток соединений с момента запуска экземпляра сервера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="56cd8-135">For example, you can create the following stored procedure to count the number of connections and attempted connections since an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] was started:</span></span>  
  
```  
DROP PROC My_Proc  
GO  
CREATE PROC My_Proc  
AS   
   EXECUTE sp_user_counter1 @@CONNECTIONS  
GO  
```  
  
 <span data-ttu-id="56cd8-136">Функция @@CONNECTIONS возвращает число соединений или попыток соединений, осуществленных с момента запуска экземпляра сервера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="56cd8-136">The @@CONNECTIONS function returns the number of connections or attempted connections since an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] started.</span></span> <span data-ttu-id="56cd8-137">Это значение передается в качестве параметра хранимой процедуре **sp_user_counter1** .</span><span class="sxs-lookup"><span data-stu-id="56cd8-137">This value is passed to the **sp_user_counter1** stored procedure as the parameter.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="56cd8-138">Делайте запросы, определяемые в хранимых процедурах пользовательских счетчиков, как можно более простыми.</span><span class="sxs-lookup"><span data-stu-id="56cd8-138">Make the queries defined in the user counter stored procedures as simple as possible.</span></span> <span data-ttu-id="56cd8-139">Ресурсоемкие запросы, выполняющие ресурсоемкую сортировку или хэш-операции, либо задействующие большое количество операций ввода-вывода, являются очень затратными и могут повлиять на производительность.</span><span class="sxs-lookup"><span data-stu-id="56cd8-139">Memory-intensive queries that perform substantial sort or hash operations or queries that perform large amounts of I/O are expensive to execute and can impact performance.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="56cd8-140">Разрешения</span><span class="sxs-lookup"><span data-stu-id="56cd8-140">Permissions</span></span>  
 <span data-ttu-id="56cd8-141">Хранимая процедура**sp_user_counter** доступна всем пользователям, но доступ к любому из счетчиков запросов может быть ограничен.</span><span class="sxs-lookup"><span data-stu-id="56cd8-141">**sp_user_counter** is available for all users but can be restricted for any query counter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56cd8-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="56cd8-142">See Also</span></span>  
 [<span data-ttu-id="56cd8-143">Наблюдение за использованием ресурсов (системный монитор)</span><span class="sxs-lookup"><span data-stu-id="56cd8-143">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
