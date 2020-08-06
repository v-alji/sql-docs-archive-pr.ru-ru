---
title: Создание триггеров DML для обработки нескольких строк данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- multiple row DML triggers
- UPDATE statement [SQL Server], DML triggers
- DELETE statement [SQL Server], DML triggers
- multirow DML triggers [SQL Server]
- INSERT statement [SQL Server], DML triggers
- DML triggers, multirow
ms.assetid: d476c124-596b-4b27-a883-812b6b50a735
author: rothja
ms.author: jroth
ms.openlocfilehash: 11ea7aa457a5cdfcafd4a8c4e0ac170ae0e3b9c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668160"
---
# <a name="create-dml-triggers-to-handle-multiple-rows-of-data"></a><span data-ttu-id="2665a-102">Создание триггеров DML для обработки нескольких строк данных</span><span class="sxs-lookup"><span data-stu-id="2665a-102">Create DML Triggers to Handle Multiple Rows of Data</span></span>
  <span data-ttu-id="2665a-103">При написании кода для триггера DML следует учитывать, что инициирующая триггер отдельная инструкция может влиять на несколько строк, а не на одну строку данных.</span><span class="sxs-lookup"><span data-stu-id="2665a-103">When you write the code for a DML trigger, consider that the statement that causes the trigger to fire can be a single statement that affects multiple rows of data, instead of a single row.</span></span> <span data-ttu-id="2665a-104">Такой режим работы является стандартным для триггеров UPDATE и DELETE, поскольку эти инструкции зачастую касаются нескольких строк,</span><span class="sxs-lookup"><span data-stu-id="2665a-104">This behavior is common for UPDATE and DELETE triggers because these statements frequently affect multiple rows.</span></span> <span data-ttu-id="2665a-105">и в меньшей степени распространен для триггеров INSERT, поскольку базовая инструкция INSERT добавляет только одну строку.</span><span class="sxs-lookup"><span data-stu-id="2665a-105">The behavior is less common for INSERT triggers because the basic INSERT statement adds only a single row.</span></span> <span data-ttu-id="2665a-106">Тем не менее, так как допускается запуск триггера инструкцией INSERT INTO (*table_name*) SELECT, вставка множества строк может привести к вызову одного триггера.</span><span class="sxs-lookup"><span data-stu-id="2665a-106">However, because an INSERT trigger can be fired by an INSERT INTO (*table_name*) SELECT statement, the insertion of many rows may cause a single trigger invocation.</span></span>  
  
 <span data-ttu-id="2665a-107">Учет особенностей работы с несколькими строками особенно важен в случаях, когда функция триггера DML автоматически пересчитывает сводные значения из одной таблицы и помещает результаты в другую таблицу для временных итогов.</span><span class="sxs-lookup"><span data-stu-id="2665a-107">Multirow considerations are especially important when the function of a DML trigger is to automatically recalculate summary values from one table and store the results in another for ongoing tallies.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2665a-108">Не рекомендуется использовать курсоры в триггерах, поскольку они потенциально могут приводить к снижению производительности.</span><span class="sxs-lookup"><span data-stu-id="2665a-108">We do not recommend using cursors in triggers because they could potentially reduce performance.</span></span> <span data-ttu-id="2665a-109">Чтобы создать триггер, влияющий на несколько строк, вместо курсоров следует использовать логику, основанную на наборах строк.</span><span class="sxs-lookup"><span data-stu-id="2665a-109">To design a trigger that affects multiple rows, use rowset-based logic instead of cursors.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="2665a-110">Примеры</span><span class="sxs-lookup"><span data-stu-id="2665a-110">Examples</span></span>  
 <span data-ttu-id="2665a-111">Триггеры DML в нижеприведенных примерах предназначены для хранения промежуточных итогов по столбцу в другой таблице образца базы данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2665a-111">The DML triggers in the following examples are designed to store a running total of a column in another table of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
### <a name="a-storing-a-running-total-for-a-single-row-insert"></a><span data-ttu-id="2665a-112">A.</span><span class="sxs-lookup"><span data-stu-id="2665a-112">A.</span></span> <span data-ttu-id="2665a-113">Сохранение промежуточных итогов при вставке одной строки</span><span class="sxs-lookup"><span data-stu-id="2665a-113">Storing a running total for a single-row insert</span></span>  
 <span data-ttu-id="2665a-114">Первая версия триггера DML подходит для вставки одной строки данных, которая загружается в таблицу `PurchaseOrderDetail` .</span><span class="sxs-lookup"><span data-stu-id="2665a-114">The first version of the DML trigger works well for a single-row insert when a row of data is loaded into the `PurchaseOrderDetail` table.</span></span> <span data-ttu-id="2665a-115">Инструкция INSERT активирует триггер DML, и новая строка добавляется в таблицу **inserted** на время выполнения триггера.</span><span class="sxs-lookup"><span data-stu-id="2665a-115">An INSERT statement fires the DML trigger, and the new row is loaded into the **inserted** table for the duration of the trigger execution.</span></span> <span data-ttu-id="2665a-116">Инструкция `UPDATE` считывает значение столбца `LineTotal` по строке и добавляет его к текущему значению в столбце `SubTotal` таблицы `PurchaseOrderHeader` .</span><span class="sxs-lookup"><span data-stu-id="2665a-116">The `UPDATE` statement reads the `LineTotal` column value for the row and adds that value to the existing value in the `SubTotal` column in the `PurchaseOrderHeader` table.</span></span> <span data-ttu-id="2665a-117">Предложение `WHERE` служит для проверки того, что обновленная строка в таблице `PurchaseOrderDetail` соответствует столбцу `PurchaseOrderID` строки в таблице **inserted** .</span><span class="sxs-lookup"><span data-stu-id="2665a-117">The `WHERE` clause makes sure that the updated row in the `PurchaseOrderDetail` table matches the `PurchaseOrderID` of the row in the **inserted** table.</span></span>  
  
```  
-- Trigger is valid for single-row inserts.  
USE AdventureWorks2012;  
GO  
CREATE TRIGGER NewPODetail  
ON Purchasing.PurchaseOrderDetail  
AFTER INSERT AS  
   UPDATE PurchaseOrderHeader  
   SET SubTotal = SubTotal + LineTotal  
   FROM inserted  
   WHERE PurchaseOrderHeader.PurchaseOrderID = inserted.PurchaseOrderID ;  
```  
  
### <a name="b-storing-a-running-total-for-a-multirow-or-single-row-insert"></a><span data-ttu-id="2665a-118">Б.</span><span class="sxs-lookup"><span data-stu-id="2665a-118">B.</span></span> <span data-ttu-id="2665a-119">Сохранение промежуточных итогов при вставке нескольких строк или одной строки</span><span class="sxs-lookup"><span data-stu-id="2665a-119">Storing a running total for a multirow or single-row insert</span></span>  
 <span data-ttu-id="2665a-120">При вставке нескольких строк триггер DML в примере A может завершаться ошибкой; выражение справа от выражения присваивания в инструкции UPDATE (`SubTotal` + `LineTotal`) может быть только одним значением, а не списком значений.</span><span class="sxs-lookup"><span data-stu-id="2665a-120">For a multirow insert, the DML trigger in example A might not operate correctly; the expression to the right of an assignment expression in an UPDATE statement (`SubTotal` + `LineTotal`) can be only a single value, not a list of values.</span></span> <span data-ttu-id="2665a-121">Следовательно, триггер должен извлечь значение из любой отдельной строки таблицы **inserted** и добавить его к текущему значению `SubTotal` таблицы `PurchaseOrderHeader` для конкретного значения `PurchaseOrderID` .</span><span class="sxs-lookup"><span data-stu-id="2665a-121">Therefore, the effect of the trigger is to retrieve a value from any single row in the **inserted** table and add that value to the existing `SubTotal` value in the `PurchaseOrderHeader` table for a specific `PurchaseOrderID` value.</span></span> <span data-ttu-id="2665a-122">Эта операция может не иметь ожидаемого эффекта, если отдельное значение `PurchaseOrderID` встречается несколько раз в таблице **inserted** .</span><span class="sxs-lookup"><span data-stu-id="2665a-122">This operation might not have the expected effect if a single `PurchaseOrderID` value occurred more than one time in the **inserted** table.</span></span>  
  
 <span data-ttu-id="2665a-123">Для правильного обновления таблицы `PurchaseOrderHeader` триггер должен поддерживать работу с несколькими строками в таблице **inserted** .</span><span class="sxs-lookup"><span data-stu-id="2665a-123">To correctly update the `PurchaseOrderHeader` table, the trigger must allow for the chance of multiple rows in the **inserted** table.</span></span> <span data-ttu-id="2665a-124">Этого можно добиться с помощью функции `SUM` , которая вычисляет итог `LineTotal` по группе строк таблицы **inserted** для каждого значения `PurchaseOrderID`.</span><span class="sxs-lookup"><span data-stu-id="2665a-124">You can do this by using the `SUM` function that calculates the total `LineTotal` for a group of rows in the **inserted** table for each `PurchaseOrderID`.</span></span> <span data-ttu-id="2665a-125">Функция `SUM` включена в коррелированный вложенный запрос (инструкцию `SELECT` в круглых скобках).</span><span class="sxs-lookup"><span data-stu-id="2665a-125">The `SUM` function is included in a correlated subquery (the `SELECT` statement in parentheses).</span></span> <span data-ttu-id="2665a-126">Этот вложенный запрос возвращает одно значение для каждого значения `PurchaseOrderID` таблицы **inserted** , которое соответствует или коррелирует со значением `PurchaseOrderID` таблицы `PurchaseOrderHeader` .</span><span class="sxs-lookup"><span data-stu-id="2665a-126">This subquery returns a single value for each `PurchaseOrderID` in the **inserted** table that matches or is correlated with a `PurchaseOrderID` in the `PurchaseOrderHeader` table.</span></span>  
  
```  
-- Trigger is valid for multirow and single-row inserts.  
USE AdventureWorks2012;  
GO  
CREATE TRIGGER NewPODetail2  
ON Purchasing.PurchaseOrderDetail  
AFTER INSERT AS  
   UPDATE Purchasing.PurchaseOrderHeader  
   SET SubTotal = SubTotal +   
      (SELECT SUM(LineTotal)  
      FROM inserted  
      WHERE PurchaseOrderHeader.PurchaseOrderID  
       = inserted.PurchaseOrderID)  
   WHERE PurchaseOrderHeader.PurchaseOrderID IN  
      (SELECT PurchaseOrderID FROM inserted);  
```  
  
 <span data-ttu-id="2665a-127">Этот триггер также правильно выполняется при вставке одной строки, при этом сумма столбца значений `LineTotal` является суммой одной строки.</span><span class="sxs-lookup"><span data-stu-id="2665a-127">This trigger also works correctly in a single-row insert; the sum of the `LineTotal` value column is the sum of a single row.</span></span> <span data-ttu-id="2665a-128">Однако при работе с этим триггером требуется дополнительная обработка средствами `IN` коррелированного вложенного запроса и оператора `WHERE` , используемого в предложении [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2665a-128">However, with this trigger the correlated subquery and the `IN` operator that is used in the `WHERE` clause require additional processing from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="2665a-129">Это необязательно для вставки одной строки.</span><span class="sxs-lookup"><span data-stu-id="2665a-129">This is unnecessary for a single-row insert.</span></span>  
  
### <a name="c-storing-a-running-total-based-on-the-type-of-insert"></a><span data-ttu-id="2665a-130">В.</span><span class="sxs-lookup"><span data-stu-id="2665a-130">C.</span></span> <span data-ttu-id="2665a-131">Сохранение промежуточных итогов в зависимости типа вставки</span><span class="sxs-lookup"><span data-stu-id="2665a-131">Storing a running total based on the type of insert</span></span>  
 <span data-ttu-id="2665a-132">В триггер можно вносить изменения для подбора способа, оптимального при работе с несколькими строками.</span><span class="sxs-lookup"><span data-stu-id="2665a-132">You can change the trigger to use the method optimal for the number of rows.</span></span> <span data-ttu-id="2665a-133">Например, в логике триггера можно использовать функцию `@@ROWCOUNT` , чтобы различать вставку одной и нескольких строк.</span><span class="sxs-lookup"><span data-stu-id="2665a-133">For example, the `@@ROWCOUNT` function can be used in the logic of the trigger to distinguish between a single and a multirow insert.</span></span>  
  
```  
-- Trigger valid for multirow and single row inserts  
-- and optimal for single row inserts.  
USE AdventureWorks2012;  
GO  
CREATE TRIGGER NewPODetail3  
ON Purchasing.PurchaseOrderDetail  
FOR INSERT AS  
IF @@ROWCOUNT = 1  
BEGIN  
   UPDATE Purchasing.PurchaseOrderHeader  
   SET SubTotal = SubTotal + LineTotal  
   FROM inserted  
   WHERE PurchaseOrderHeader.PurchaseOrderID = inserted.PurchaseOrderID  
END  
ELSE  
BEGIN  
      UPDATE Purchasing.PurchaseOrderHeader  
   SET SubTotal = SubTotal +   
      (SELECT SUM(LineTotal)  
      FROM inserted  
      WHERE PurchaseOrderHeader.PurchaseOrderID  
       = inserted.PurchaseOrderID)  
   WHERE PurchaseOrderHeader.PurchaseOrderID IN  
      (SELECT PurchaseOrderID FROM inserted)  
END;  
```  
  
## <a name="see-also"></a><span data-ttu-id="2665a-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="2665a-134">See Also</span></span>  
 [<span data-ttu-id="2665a-135">Триггеры DML</span><span class="sxs-lookup"><span data-stu-id="2665a-135">DML Triggers</span></span>](dml-triggers.md)  
  
  
