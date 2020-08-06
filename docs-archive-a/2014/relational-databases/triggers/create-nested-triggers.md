---
title: Создание вложенных триггеров | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- recursive DML triggers [SQL Server]
- DML triggers, nested
- triggers [SQL Server], nested
- direct recursion [SQL Server]
- triggers [SQL Server], recursive
- DML triggers, recursive
- RECURSIVE_TRIGGERS option
- indirect recursion [SQL Server]
- nested DML triggers
ms.assetid: cd522dda-b4ab-41b8-82b0-02445bdba7af
author: rothja
ms.author: jroth
ms.openlocfilehash: c0016fc3cdd93ea78ceed56efa076a01bd85be50
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668157"
---
# <a name="create-nested-triggers"></a><span data-ttu-id="3c0ff-102">Создание вложенных триггеров</span><span class="sxs-lookup"><span data-stu-id="3c0ff-102">Create Nested Triggers</span></span>
  <span data-ttu-id="3c0ff-103">При выполнении триггером действия, инициирующего другой триггер, триггеры DML и DDL становятся вложенными.</span><span class="sxs-lookup"><span data-stu-id="3c0ff-103">Both DML and DDL triggers are nested when a trigger performs an action that initiates another trigger.</span></span> <span data-ttu-id="3c0ff-104">Эти действия могут инициировать другие триггеры и т.д.</span><span class="sxs-lookup"><span data-stu-id="3c0ff-104">These actions can initiate other triggers, and so on.</span></span> <span data-ttu-id="3c0ff-105">Вложенность триггеров DML и DDL может составлять до 32 уровней.</span><span class="sxs-lookup"><span data-stu-id="3c0ff-105">DML and DDL triggers can be nested up to 32 levels.</span></span> <span data-ttu-id="3c0ff-106">Можно разрешать или запрещать вложенность триггеров AFTER с помощью параметра конфигурации сервера **nested triggers** .</span><span class="sxs-lookup"><span data-stu-id="3c0ff-106">You can control whether AFTER triggers can be nested through the **nested triggers** server configuration option.</span></span> <span data-ttu-id="3c0ff-107">Вложенность триггеров INSTEAD OF (только триггеры DML могут быть триггерами INSTEAD OF) не зависит от этого параметра.</span><span class="sxs-lookup"><span data-stu-id="3c0ff-107">INSTEAD OF triggers (only DML triggers can be INSTEAD OF triggers) can be nested regardless of this setting.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3c0ff-108">Любая ссылка на управляемый код из триггера [!INCLUDE[tsql](../../includes/tsql-md.md)] считается одним уровнем (предел вложенности равен 32 уровням).</span><span class="sxs-lookup"><span data-stu-id="3c0ff-108">Any reference to managed code from a [!INCLUDE[tsql](../../includes/tsql-md.md)] trigger counts as one level against the 32-level nesting limit.</span></span> <span data-ttu-id="3c0ff-109">Методы, вызываемые из управляемого кода, под это ограничение не подпадают.</span><span class="sxs-lookup"><span data-stu-id="3c0ff-109">Methods invoked from within managed code do not count against this limit.</span></span>  
  
 <span data-ttu-id="3c0ff-110">Если вложенные триггеры разрешены и триггер в цепочке начинает бесконечный цикл, это превышает предел уровней вложенности и триггер завершается.</span><span class="sxs-lookup"><span data-stu-id="3c0ff-110">If nested triggers are allowed and a trigger in the chain starts an infinite loop, the nesting level is exceeded and the trigger terminates.</span></span>  
  
 <span data-ttu-id="3c0ff-111">Можно использовать вложенные триггеры для выполнения полезных функций по обслуживанию, например для сохранения резервной копии строк, затронутых предыдущим триггером.</span><span class="sxs-lookup"><span data-stu-id="3c0ff-111">You can use nested triggers to perform useful housekeeping functions such as storing a backup copy of rows affected by a previous trigger.</span></span> <span data-ttu-id="3c0ff-112">Например, можно создать триггер для таблицы `PurchaseOrderDetail` , который будет сохранять резервную копию строк `PurchaseOrderDetail` , удаленных триггером `delcascadetrig` .</span><span class="sxs-lookup"><span data-stu-id="3c0ff-112">For example, you can create a trigger on `PurchaseOrderDetail` that saves a backup copy of the `PurchaseOrderDetail` rows that the `delcascadetrig` trigger deleted.</span></span> <span data-ttu-id="3c0ff-113">Если действует триггер `delcascadetrig` , удаление `PurchaseOrderID` 1965 из таблицы `PurchaseOrderHeader` также повлечет удаление соответствующей строки или строк из таблицы `PurchaseOrderDetail`.</span><span class="sxs-lookup"><span data-stu-id="3c0ff-113">With the `delcascadetrig` trigger in effect, deleting `PurchaseOrderID` 1965 from `PurchaseOrderHeader` deletes the corresponding row or rows from `PurchaseOrderDetail`.</span></span> <span data-ttu-id="3c0ff-114">Чтобы сохранить данные, можно создать триггер DELETE для таблицы `PurchaseOrderDetail` , который запишет удаленные данные в другую, отдельно созданную таблицу `del_save`.</span><span class="sxs-lookup"><span data-stu-id="3c0ff-114">To save the data, you can create a DELETE trigger on `PurchaseOrderDetail` that saves the deleted data into another separately created table, `del_save`.</span></span> <span data-ttu-id="3c0ff-115">Пример:</span><span class="sxs-lookup"><span data-stu-id="3c0ff-115">For example:</span></span>  
  
```  
CREATE TRIGGER Purchasing.savedel  
   ON Purchasing.PurchaseOrderDetail  
FOR DELETE  
AS  
   INSERT del_save;  
   SELECT * FROM deleted;  
```  
  
 <span data-ttu-id="3c0ff-116">Не рекомендуется использовать вложенные триггеры в последовательностях, зависящих от порядка следования.</span><span class="sxs-lookup"><span data-stu-id="3c0ff-116">We do not recommend using nested triggers in an order-dependent sequence.</span></span> <span data-ttu-id="3c0ff-117">Используйте отдельные триггеры для каскадной модификации данных.</span><span class="sxs-lookup"><span data-stu-id="3c0ff-117">Use separate triggers to cascade data modifications.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3c0ff-118">Так как триггеры исполняются в пределах транзакции, сбой на любом уровне набора вложенных триггеров приведет к отмене всей транзакции, а также будет выполнен откат всех изменений данных.</span><span class="sxs-lookup"><span data-stu-id="3c0ff-118">Because triggers execute within a transaction, a failure at any level of a set of nested triggers cancels the entire transaction, and all data modifications are rolled back.</span></span> <span data-ttu-id="3c0ff-119">Включите инструкции PRINT в триггеры, чтобы определить, где происходит сбой.</span><span class="sxs-lookup"><span data-stu-id="3c0ff-119">Include PRINT statements in your triggers so that you can determine where the failure has occurred.</span></span>  
  
## <a name="recursive-triggers"></a><span data-ttu-id="3c0ff-120">Рекурсивные триггеры</span><span class="sxs-lookup"><span data-stu-id="3c0ff-120">Recursive Triggers</span></span>  
 <span data-ttu-id="3c0ff-121">Триггер AFTER не вызывает самого себя рекурсивно, если только не установлен параметр базы данных RECURSIVE_TRIGGERS.</span><span class="sxs-lookup"><span data-stu-id="3c0ff-121">An AFTER trigger does not call itself recursively unless the RECURSIVE_TRIGGERS database option is set.</span></span>  
  
 <span data-ttu-id="3c0ff-122">Существует два типа рекурсии.</span><span class="sxs-lookup"><span data-stu-id="3c0ff-122">There are two types of recursion:</span></span>  
  
-   <span data-ttu-id="3c0ff-123">Прямая рекурсия</span><span class="sxs-lookup"><span data-stu-id="3c0ff-123">Direct recursion</span></span>  
  
     <span data-ttu-id="3c0ff-124">Такая рекурсия происходит, когда триггер срабатывает и выполняет действие, вызывающее повторное срабатывание того же триггера.</span><span class="sxs-lookup"><span data-stu-id="3c0ff-124">This recursion occurs when a trigger fires and performs an action that causes the same trigger to fire again.</span></span> <span data-ttu-id="3c0ff-125">Например, приложение обновляет таблицу **T3**; это вызывает срабатывание триггера **Trig3** .</span><span class="sxs-lookup"><span data-stu-id="3c0ff-125">For example, an application updates table **T3**; this causes trigger **Trig3** to fire.</span></span> <span data-ttu-id="3c0ff-126">Триггер**Trig3** снова обновляет таблицу **T3** , при этом триггер **Trig3** срабатывает еще раз.</span><span class="sxs-lookup"><span data-stu-id="3c0ff-126">**Trig3** updates table **T3** again; this causes trigger **Trig3** to fire again.</span></span>  
  
     <span data-ttu-id="3c0ff-127">Прямая рекурсия может также возникать, когда повторно вызывается тот же триггер, но лишь после того, как вызван триггер другого типа (AFTER или INSTEAD OF).</span><span class="sxs-lookup"><span data-stu-id="3c0ff-127">Direct recursion can also occur when the same trigger is called again, but after a trigger of a different type (AFTER or INSTEAD OF) is called.</span></span> <span data-ttu-id="3c0ff-128">Другими словами, прямая рекурсия триггера INSTEAD OF может возникать, когда один и тот же триггер INSTEAD OF вызывается второй раз, даже если между двумя его вызовами вызывается один или несколько триггеров AFTER.</span><span class="sxs-lookup"><span data-stu-id="3c0ff-128">In other words, direct recursion of an INSTEAD OF trigger can occur when the same INSTEAD OF trigger is called for a second time, even if one or more AFTER triggers are called in between.</span></span> <span data-ttu-id="3c0ff-129">Аналогичным образом прямая рекурсия триггера AFTER может возникать, когда один и тот же триггер AFTER вызывается второй раз, даже если между двумя его вызовами вызывается один или несколько триггеров INSTEAD OF.</span><span class="sxs-lookup"><span data-stu-id="3c0ff-129">Likewise, direct recursion of an AFTER trigger can occur when the same AFTER trigger is called for a second time, even if one or more INSTEAD OF triggers are called in between.</span></span> <span data-ttu-id="3c0ff-130">Например, пусть приложение использует таблицу **T4**.</span><span class="sxs-lookup"><span data-stu-id="3c0ff-130">For example, an application updates table **T4**.</span></span> <span data-ttu-id="3c0ff-131">Данное обновление приводит к срабатыванию триггера **Trig4** типа INSTEAD OF.</span><span class="sxs-lookup"><span data-stu-id="3c0ff-131">This update causes INSTEAD OF trigger **Trig4** to fire.</span></span> <span data-ttu-id="3c0ff-132">**Trig4** обновляет таблицу **T5**.</span><span class="sxs-lookup"><span data-stu-id="3c0ff-132">**Trig4** updates table **T5**.</span></span> <span data-ttu-id="3c0ff-133">Данное обновление приводит к срабатыванию триггера **Trig5** типа AFTER.</span><span class="sxs-lookup"><span data-stu-id="3c0ff-133">This update causes AFTER trigger **Trig5** to fire.</span></span> <span data-ttu-id="3c0ff-134">**Trig5** обновляет таблицу **T4**, и это обновление приводит к повторному срабатыванию триггера **Trig4** типа INSTEAD OF.</span><span class="sxs-lookup"><span data-stu-id="3c0ff-134">**Trig5** updates table **T4**, and this update causes INSTEAD OF trigger **Trig4** to fire again.</span></span> <span data-ttu-id="3c0ff-135">Данная цепь событий считается прямой рекурсией триггера **Trig4**.</span><span class="sxs-lookup"><span data-stu-id="3c0ff-135">This chain of events is considered direct recursion for **Trig4**.</span></span>  
  
-   <span data-ttu-id="3c0ff-136">Косвенная рекурсия</span><span class="sxs-lookup"><span data-stu-id="3c0ff-136">Indirect recursion</span></span>  
  
     <span data-ttu-id="3c0ff-137">Косвенная рекурсия возникает, когда триггер срабатывает и выполняет действие, которое вызывает срабатывание другого триггера того же типа (AFTER или INSTEAD OF).</span><span class="sxs-lookup"><span data-stu-id="3c0ff-137">This recursion occurs when a trigger fires and performs an action that causes another trigger of the same type (AFTER or INSTEAD OF) to fire.</span></span> <span data-ttu-id="3c0ff-138">Второй триггер выполняет действие, вызывающее повторное срабатывание исходного триггера.</span><span class="sxs-lookup"><span data-stu-id="3c0ff-138">This second trigger performs an action that causes the original trigger to fire again.</span></span> <span data-ttu-id="3c0ff-139">Другими словами, косвенная рекурсия может возникать, когда триггер INSTEAD OF вызывается второй раз, но лишь после того, как между этими двумя вызовами вызывается другой триггер того же типа INSTEAD OF.</span><span class="sxs-lookup"><span data-stu-id="3c0ff-139">In other words, indirect recursion can occur when an INSTEAD OF trigger is called for a second time, but not until another INSTEAD OF trigger is called in between.</span></span> <span data-ttu-id="3c0ff-140">Аналогичным образом косвенная рекурсия может возникать, когда триггер AFTER вызывается второй раз, но лишь после того, как между этими двумя вызовами вызывается другой триггер того же типа AFTER.</span><span class="sxs-lookup"><span data-stu-id="3c0ff-140">Likewise, indirect recursion can occur when an AFTER trigger is called for a second time, but not until another AFTER trigger is called in between.</span></span> <span data-ttu-id="3c0ff-141">Например, пусть приложение использует таблицу **T1**.</span><span class="sxs-lookup"><span data-stu-id="3c0ff-141">For example, an application updates table **T1**.</span></span> <span data-ttu-id="3c0ff-142">Данное обновление приводит к срабатыванию триггера **Trig1** типа AFTER.</span><span class="sxs-lookup"><span data-stu-id="3c0ff-142">This update causes AFTER trigger **Trig1** to fire.</span></span> <span data-ttu-id="3c0ff-143">Триггер**Trig1** обновляет таблицу **T2**; при этом обновлении срабатывает триггер **Trig2** типа AFTER.</span><span class="sxs-lookup"><span data-stu-id="3c0ff-143">**Trig1** updates table **T2**, and this update causes AFTER trigger **Trig2** to fire.</span></span> <span data-ttu-id="3c0ff-144">Триггер**Trig2** , в свою очередь, обновляет таблицу **T1** , что приводит к повторному срабатыванию триггера **Trig1** типа AFTER.</span><span class="sxs-lookup"><span data-stu-id="3c0ff-144">**Trig2** in turn updates table **T1** that causes AFTER trigger **Trig1** to fire again.</span></span>  
  
 <span data-ttu-id="3c0ff-145">Когда для параметра базы данных RECURSIVE_TRIGGERS устанавливается значение OFF, предотвращается только прямая рекурсия триггеров AFTER.</span><span class="sxs-lookup"><span data-stu-id="3c0ff-145">Only direct recursion of AFTER triggers is prevented when the RECURSIVE_TRIGGERS database option is set to OFF.</span></span> <span data-ttu-id="3c0ff-146">Чтобы отключить косвенную рекурсию триггеров AFTER, присвойте параметру сервера **nested triggers** значение **0**.</span><span class="sxs-lookup"><span data-stu-id="3c0ff-146">To disable indirect recursion of AFTER triggers, also set the **nested triggers** server option to **0**.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="3c0ff-147">Примеры</span><span class="sxs-lookup"><span data-stu-id="3c0ff-147">Examples</span></span>  
 <span data-ttu-id="3c0ff-148">Следующий пример демонстрирует использование рекурсивных триггеров для разрешения ссылающейся на себя связи (также называемой транзитивным закрытием).</span><span class="sxs-lookup"><span data-stu-id="3c0ff-148">The following example shows using recursive triggers to solve a self-referencing relationship (also known as transitive closure).</span></span> <span data-ttu-id="3c0ff-149">Например, таблица `emp_mgr` определяет:</span><span class="sxs-lookup"><span data-stu-id="3c0ff-149">For example, the table `emp_mgr` defines the following:</span></span>  
  
-   <span data-ttu-id="3c0ff-150">сотрудника (`emp`) компании;</span><span class="sxs-lookup"><span data-stu-id="3c0ff-150">An employee (`emp`) in a company.</span></span>  
  
-   <span data-ttu-id="3c0ff-151">менеджера каждого сотрудника (`mgr`);</span><span class="sxs-lookup"><span data-stu-id="3c0ff-151">The manager for each employee (`mgr`).</span></span>  
  
-   <span data-ttu-id="3c0ff-152">общее число сотрудников в организационном дереве, отправляющих отчеты каждому сотруднику (`NoOfReports`).</span><span class="sxs-lookup"><span data-stu-id="3c0ff-152">The total number of employees in the organizational tree reporting to each employee (`NoOfReports`).</span></span>  
  
 <span data-ttu-id="3c0ff-153">Рекурсивный триггер UPDATE можно использовать для поддержания столбца `NoOfReports` в актуальном состоянии при добавлении новых записей сотрудников.</span><span class="sxs-lookup"><span data-stu-id="3c0ff-153">A recursive UPDATE trigger can be used to keep the `NoOfReports` column up-to-date as new employee records are inserted.</span></span> <span data-ttu-id="3c0ff-154">Триггер INSERT обновляет столбец `NoOfReports` записи менеджера, что приводит к рекурсивному обновлению столбца `NoOfReports` других записей, находящихся выше по иерархии менеджмента.</span><span class="sxs-lookup"><span data-stu-id="3c0ff-154">The INSERT trigger updates the `NoOfReports` column of the manager record, which recursively updates the `NoOfReports` column of other records up the management hierarchy.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
-- Turn recursive triggers ON in the database.  
ALTER DATABASE AdventureWorks2012  
   SET RECURSIVE_TRIGGERS ON;  
GO  
CREATE TABLE dbo.emp_mgr (  
   emp char(30) PRIMARY KEY,  
    mgr char(30) NULL FOREIGN KEY REFERENCES emp_mgr(emp),  
    NoOfReports int DEFAULT 0  
);  
GO  
CREATE TRIGGER dbo.emp_mgrins ON dbo.emp_mgr  
FOR INSERT  
AS  
DECLARE @e char(30), @m char(30);  
DECLARE c1 CURSOR FOR  
   SELECT emp_mgr.emp  
   FROM   emp_mgr, inserted  
   WHERE emp_mgr.emp = inserted.mgr;  
  
OPEN c1;  
FETCH NEXT FROM c1 INTO @e;  
WHILE @@fetch_status = 0  
BEGIN  
   UPDATE dbo.emp_mgr  
   SET emp_mgr.NoOfReports = emp_mgr.NoOfReports + 1 -- Add 1 for newly  
   WHERE emp_mgr.emp = @e ;                           -- added employee.  
  
   FETCH NEXT FROM c1 INTO @e;  
END  
CLOSE c1;  
DEALLOCATE c1;  
GO  
-- This recursive UPDATE trigger works assuming:  
--   1. Only singleton updates on emp_mgr.  
--   2. No inserts in the middle of the org tree.  
CREATE TRIGGER dbo.emp_mgrupd ON dbo.emp_mgr FOR UPDATE  
AS  
IF UPDATE (mgr)  
BEGIN  
   UPDATE dbo.emp_mgr  
   SET emp_mgr.NoOfReports = emp_mgr.NoOfReports + 1 -- Increment mgr's  
   FROM inserted                            -- (no. of reports) by  
   WHERE emp_mgr.emp = inserted.mgr;         -- 1 for the new report.  
  
   UPDATE dbo.emp_mgr  
   SET emp_mgr.NoOfReports = emp_mgr.NoOfReports - 1 -- Decrement mgr's  
   FROM deleted                             -- (no. of reports) by 1  
   WHERE emp_mgr.emp = deleted.mgr;          -- for the new report.  
END  
GO  
-- Insert some test data rows.  
INSERT dbo.emp_mgr(emp, mgr) VALUES  
    ('Harry', NULL)  
    ,('Alice', 'Harry')  
    ,('Paul', 'Alice')  
    ,('Joe', 'Alice')  
    ,('Dave', 'Joe');  
GO  
SELECT emp,mgr,NoOfReports  
FROM dbo.emp_mgr;  
GO  
-- Change Dave's manager from Joe to Harry  
UPDATE dbo.emp_mgr SET mgr = 'Harry'  
WHERE emp = 'Dave';  
GO  
SELECT emp,mgr,NoOfReports FROM emp_mgr;  
  
GO  
```  
  
 <span data-ttu-id="3c0ff-155">Результаты до обновления.</span><span class="sxs-lookup"><span data-stu-id="3c0ff-155">Here are the results before the update.</span></span>  
  
```  
emp                            mgr                           NoOfReports  
------------------------------ ----------------------------- -----------  
Alice                          Harry                          2  
Dave                           Joe                            0  
Harry                          NULL                           1  
Joe                            Alice                          1  
Paul                           Alice                          0  
```  
  
 <span data-ttu-id="3c0ff-156">Результаты после обновления.</span><span class="sxs-lookup"><span data-stu-id="3c0ff-156">Here are the results after the update.</span></span>  
  
```  
emp                            mgr                           NoOfReports  
------------------------------ ----------------------------- -----------  
Alice                          Harry                          2  
Dave                           Harry                          0  
Harry                          NULL                           2  
Joe                            Alice                          0  
Paul                           Alice                          0  
```  
  
 <span data-ttu-id="3c0ff-157">**Установка параметра nested triggers**</span><span class="sxs-lookup"><span data-stu-id="3c0ff-157">**To set the nested triggers option**</span></span>  
  
-   [<span data-ttu-id="3c0ff-158">sp_configure (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="3c0ff-158">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
 <span data-ttu-id="3c0ff-159">**Установка параметра базы данных RECURSIVE_TRIGGERS**</span><span class="sxs-lookup"><span data-stu-id="3c0ff-159">**To set the RECURSIVE_TRIGGERS database option**</span></span>  
  
-   [<span data-ttu-id="3c0ff-160">Параметры ALTER DATABASE SET &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3c0ff-160">ALTER DATABASE SET Options &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql-set-options)  
  
## <a name="see-also"></a><span data-ttu-id="3c0ff-161">См. также:</span><span class="sxs-lookup"><span data-stu-id="3c0ff-161">See Also</span></span>  
 <span data-ttu-id="3c0ff-162">[CREATE TRIGGER (Transact-SQL)](/sql/t-sql/statements/create-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3c0ff-162">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span></span>  
 [<span data-ttu-id="3c0ff-163">Настройка конфигурации сервера nested triggers</span><span class="sxs-lookup"><span data-stu-id="3c0ff-163">Configure the nested triggers Server Configuration Option</span></span>](../../database-engine/configure-windows/configure-the-nested-triggers-server-configuration-option.md)  
  
  
