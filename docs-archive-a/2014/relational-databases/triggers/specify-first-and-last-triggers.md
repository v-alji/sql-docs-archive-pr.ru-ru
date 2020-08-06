---
title: Указание первого и последнего триггеров | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- first triggers [SQL Server]
- last triggers
- DML triggers, first or last triggers
- INSTEAD OF triggers
- AFTER triggers
ms.assetid: 9e6c7684-3dd3-46bb-b7be-523b33fae4d5
author: rothja
ms.author: jroth
ms.openlocfilehash: 8ddb352b00dc759362c8f6ef1e861e55b6f184f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668133"
---
# <a name="specify-first-and-last-triggers"></a><span data-ttu-id="e87ee-102">Указание первого и последнего триггеров</span><span class="sxs-lookup"><span data-stu-id="e87ee-102">Specify First and Last Triggers</span></span>
  <span data-ttu-id="e87ee-103">Возможно указать, что один из триггеров AFTER, связанных с таблицей, является либо первым триггером AFTER, либо последним триггером AFTER, срабатывающим для каждого запускающего действия INSERT, DELETE и UPDATE.</span><span class="sxs-lookup"><span data-stu-id="e87ee-103">You can specify that one of the AFTER triggers associated with a table be either the first AFTER trigger or the last AFTER trigger that is fired for each INSERT, DELETE, and UPDATE triggering actions.</span></span> <span data-ttu-id="e87ee-104">Порядок запуска триггеров AFTER, срабатывающих в промежутке между первым и последним триггерами, не определен.</span><span class="sxs-lookup"><span data-stu-id="e87ee-104">The AFTER triggers that are fired between the first and last triggers are executed in undefined order.</span></span>  
  
 <span data-ttu-id="e87ee-105">Задать порядок срабатывания для триггера AFTER можно с помощью хранимой процедуры **sp_settriggerorder** .</span><span class="sxs-lookup"><span data-stu-id="e87ee-105">To specify the order for an AFTER trigger, use the **sp_settriggerorder** stored procedure.</span></span> <span data-ttu-id="e87ee-106">Хранимая процедура**sp_settriggerorder** имеет следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="e87ee-106">**sp_settriggerorder** has the following options.</span></span>  
  
|<span data-ttu-id="e87ee-107">Параметр</span><span class="sxs-lookup"><span data-stu-id="e87ee-107">Option</span></span>|<span data-ttu-id="e87ee-108">Description</span><span class="sxs-lookup"><span data-stu-id="e87ee-108">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="e87ee-109">**Первая**</span><span class="sxs-lookup"><span data-stu-id="e87ee-109">**First**</span></span>|<span data-ttu-id="e87ee-110">Указывает, что триггер DML является первым триггером AFTER, срабатывающим для запускающего действия.</span><span class="sxs-lookup"><span data-stu-id="e87ee-110">Specifies that the DML trigger is the first AFTER trigger fired for a triggering action.</span></span>|  
|<span data-ttu-id="e87ee-111">**Последняя**</span><span class="sxs-lookup"><span data-stu-id="e87ee-111">**Last**</span></span>|<span data-ttu-id="e87ee-112">Указывает, что триггер DML является последним триггером AFTER, срабатывающим для запускающего действия.</span><span class="sxs-lookup"><span data-stu-id="e87ee-112">Specifies that the DML trigger is the last AFTER trigger fired for a triggering action.</span></span>|  
|<span data-ttu-id="e87ee-113">**None**</span><span class="sxs-lookup"><span data-stu-id="e87ee-113">**None**</span></span>|<span data-ttu-id="e87ee-114">Указывает, что не существует определенного порядка, в соответствии с которым триггер DML должен срабатывать.</span><span class="sxs-lookup"><span data-stu-id="e87ee-114">Specifies that there is no specific order in which the DML trigger should be fired.</span></span> <span data-ttu-id="e87ee-115">Используется главным образом для смещения триггера с позиции первого или последнего.</span><span class="sxs-lookup"><span data-stu-id="e87ee-115">Used mainly to reset a trigger from being either first or last.</span></span>|  
  
 <span data-ttu-id="e87ee-116">В нижеследующем примере показано использование **sp_settriggerorder**:</span><span class="sxs-lookup"><span data-stu-id="e87ee-116">The following example shows using **sp_settriggerorder**:</span></span>  
  
```  
sp_settriggerorder @triggername = 'MyTrigger', @order = 'first', @stmttype = 'UPDATE'  
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e87ee-117">Первый и последний триггеры должны быть двумя различными триггерами DML.</span><span class="sxs-lookup"><span data-stu-id="e87ee-117">The first and last triggers must be two different DML triggers.</span></span>  
  
 <span data-ttu-id="e87ee-118">Для таблицы могут быть в одно и то же время определены триггеры INSERT, UPDATE и DELETE.</span><span class="sxs-lookup"><span data-stu-id="e87ee-118">A table can have INSERT, UPDATE, and DELETE triggers defined on it at the same time.</span></span> <span data-ttu-id="e87ee-119">Каждый тип инструкции может иметь свои собственные первый и последний триггеры, но они не могут быть одними и теми же триггерами.</span><span class="sxs-lookup"><span data-stu-id="e87ee-119">Each statement type can have its own first and last triggers, but they cannot be the same triggers.</span></span>  
  
 <span data-ttu-id="e87ee-120">Если первый или последний триггер, определенный для таблицы, не охватывает запускающее действие, то есть если он не охватывает FOR UPDATE, FOR DELETE или FOR INSERT, не существует первого или последнего триггера для отсутствующих действий.</span><span class="sxs-lookup"><span data-stu-id="e87ee-120">If the first or last trigger defined for a table does not cover a triggering action, such as not covering FOR UPDATE, FOR DELETE, or FOR INSERT, there is no first or last trigger for the missing actions.</span></span>  
  
 <span data-ttu-id="e87ee-121">Триггеры INSTEAD OF не могут быть указаны в качестве первого или последнего триггеров.</span><span class="sxs-lookup"><span data-stu-id="e87ee-121">INSTEAD OF triggers cannot be specified as first or last triggers.</span></span> <span data-ttu-id="e87ee-122">Триггеры INSTEAD OF срабатывают до выполнения обновлений в базовых таблицах.</span><span class="sxs-lookup"><span data-stu-id="e87ee-122">INSTEAD OF triggers are fired before updates are made to the underlying tables.</span></span> <span data-ttu-id="e87ee-123">Если обновления в базовых таблицах выполняются триггером INSTEAD OF, то эти обновления происходят прежде, чем срабатывают какие-либо триггеры AFTER, определенные для таблицы.</span><span class="sxs-lookup"><span data-stu-id="e87ee-123">If updates are made by an INSTEAD OF trigger to underlying tables, the updates occur before any AFTER triggers defined on the table are fired.</span></span> <span data-ttu-id="e87ee-124">Например, если триггер INSTEAD OF INSERT по представлению вставляет данные в базовую таблицу, а сама базовая таблица содержит триггер INSTEAD OF INSERT и три триггера AFTER INSERT, то триггер INSTEAD OF INSERT по базовой таблице срабатывает вместо действия вставки, а триггеры AFTER по базовой таблице срабатывают после выполнения любого действия вставки в базовой таблице.</span><span class="sxs-lookup"><span data-stu-id="e87ee-124">For example, if an INSTEAD OF INSERT trigger on a view inserts data into a base table and the base table itself contains an INSTEAD OF INSERT trigger and three AFTER INSERT triggers, the INSTEAD OF INSERT trigger on the base table is fired instead of the inserting action, and the AFTER triggers on the base table are fired after any inserting action on the base table.</span></span> <span data-ttu-id="e87ee-125">Дополнительные сведения см. в разделе [DML Triggers](dml-triggers.md).</span><span class="sxs-lookup"><span data-stu-id="e87ee-125">For more information, see [DML Triggers](dml-triggers.md).</span></span>  
  
 <span data-ttu-id="e87ee-126">Если инструкция ALTER TRIGGER изменяет первый или последний триггер, атрибут **First** или **Last** удаляется и в качестве значения порядка указывается **None**.</span><span class="sxs-lookup"><span data-stu-id="e87ee-126">If an ALTER TRIGGER statement changes a first or last trigger, the **First** or **Last** attribute is dropped and the order value is set to **None**.</span></span> <span data-ttu-id="e87ee-127">Порядок должен быть изменен с использованием свойства **sp_settriggerorder**.</span><span class="sxs-lookup"><span data-stu-id="e87ee-127">The order must be reset by using **sp_settriggerorder**.</span></span>  
  
 <span data-ttu-id="e87ee-128">Функция OBJECTPROPERTY сообщает, является ли триггер первым или последним триггером, используя свойства **ExecIsFirstTrigger** и **ExecIsLastTrigger**.</span><span class="sxs-lookup"><span data-stu-id="e87ee-128">The OBJECTPROPERTY function reports whether a trigger is a first or last trigger by using the properties **ExecIsFirstTrigger** and **ExecIsLastTrigger**.</span></span>  
  
 <span data-ttu-id="e87ee-129">Репликация автоматически создает первый триггер для любой таблицы, включенной в подписку немедленным обновлением или обновлением с постановкой в очередь.</span><span class="sxs-lookup"><span data-stu-id="e87ee-129">Replication automatically generates a first trigger for any table that is included in an immediate updating or queued updating subscription.</span></span> <span data-ttu-id="e87ee-130">Репликация требует, чтобы ее триггер был первым.</span><span class="sxs-lookup"><span data-stu-id="e87ee-130">Replication requires that its trigger be the first trigger.</span></span> <span data-ttu-id="e87ee-131">При попытке вставить таблицу с указанным первым триггером в немедленно обновляемую подписку или подписку, обновляемую посредством очередей, репликация инициирует ошибку.</span><span class="sxs-lookup"><span data-stu-id="e87ee-131">Replication raises an error when you try to include a table with a first trigger in an immediate updating or queued updating subscription.</span></span> <span data-ttu-id="e87ee-132">При попытке сделать триггер первым триггером после включения таблицы в подписку **sp_settriggerorder** возвращает ошибку.</span><span class="sxs-lookup"><span data-stu-id="e87ee-132">If you try to make a trigger a first trigger after a table has been included in a subscription, **sp_settriggerorder** returns an error.</span></span> <span data-ttu-id="e87ee-133">В случае использования ALTER для триггера репликации или использования **sp_settriggerorder** , чтобы сделать триггер репликации последним или триггером вне порядка, подписка не будет функционировать должным образом.</span><span class="sxs-lookup"><span data-stu-id="e87ee-133">If you use ALTER on the replication trigger or use **sp_settriggerorder** to change the replication trigger to a last or none trigger, the subscription will not function correctly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e87ee-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="e87ee-134">See Also</span></span>  
 <span data-ttu-id="e87ee-135">[OBJECTPROPERTY (Transact-SQL)](/sql/t-sql/functions/objectpropertyex-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e87ee-135">[OBJECTPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectpropertyex-transact-sql) </span></span>  
 [<span data-ttu-id="e87ee-136">sp_settriggerorder (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e87ee-136">sp_settriggerorder &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-settriggerorder-transact-sql)  
  
  
