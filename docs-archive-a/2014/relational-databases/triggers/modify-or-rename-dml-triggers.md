---
title: Изменение или переименование триггеров DML | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- renaming triggers
- modifying triggers
- DML triggers, modifying
ms.assetid: c7317eec-c0e9-479e-a4a7-83b6b6c58d59
author: rothja
ms.author: jroth
ms.openlocfilehash: 65bb13552b552d54b5547eadedc412977e423a57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668135"
---
# <a name="modify-or-rename-dml-triggers"></a><span data-ttu-id="8532c-102">Изменение или переименование триггеров DML</span><span class="sxs-lookup"><span data-stu-id="8532c-102">Modify or Rename DML Triggers</span></span>
  <span data-ttu-id="8532c-103">В этом разделе описывается процедура изменения или переименования триггера DML в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8532c-103">This topic describes how to modify or rename a DML trigger in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="8532c-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="8532c-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8532c-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="8532c-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8532c-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="8532c-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="8532c-107">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="8532c-107">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="8532c-108">Безопасность</span><span class="sxs-lookup"><span data-stu-id="8532c-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8532c-109">**Для изменения или переименования триггера DML используется:**</span><span class="sxs-lookup"><span data-stu-id="8532c-109">**To modify or rename a DML trigger, using:**</span></span>  
  
     [<span data-ttu-id="8532c-110">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8532c-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8532c-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8532c-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8532c-112">Перед началом</span><span class="sxs-lookup"><span data-stu-id="8532c-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="8532c-113">Ограничения</span><span class="sxs-lookup"><span data-stu-id="8532c-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="8532c-114">Во время переименования триггер должен находиться в текущей базе данных, а новое имя должно удовлетворять правилам для [идентификаторов](../databases/database-identifiers.md).</span><span class="sxs-lookup"><span data-stu-id="8532c-114">When you rename a trigger, the trigger must be in the current database, and the new name must follow the rules for [identifiers](../databases/database-identifiers.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="8532c-115">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="8532c-115">Recommendations</span></span>  
  
-   <span data-ttu-id="8532c-116">Не рекомендуется использовать для переименования триггера хранимую процедуру [sp_rename](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="8532c-116">We recommend you do not use the [sp_rename](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql) stored procedure to rename a trigger.</span></span> <span data-ttu-id="8532c-117">Изменение любой части имени объекта может разрушить скрипты и хранимые процедуры.</span><span class="sxs-lookup"><span data-stu-id="8532c-117">Changing any part of an object name can break scripts and stored procedures.</span></span> <span data-ttu-id="8532c-118">При переименовании триггера не изменяется имя соответствующего объекта в определении столбца представления каталога [sys.sql_modules](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="8532c-118">Renaming a trigger does not change the name of the corresponding object name in the definition column of the [sys.sql_modules](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) catalog view.</span></span> <span data-ttu-id="8532c-119">Вместо этого мы рекомендуем удалить триггер и снова создать его.</span><span class="sxs-lookup"><span data-stu-id="8532c-119">We recommend that you drop and re-create the trigger instead.</span></span>  
  
-   <span data-ttu-id="8532c-120">Если изменилось имя объекта, на который ссылается триггер, текст триггера необходимо соответствующим образом изменить.</span><span class="sxs-lookup"><span data-stu-id="8532c-120">If you change the name of an object referenced by a DML trigger, you must modify the trigger so that its text reflects the new name.</span></span> <span data-ttu-id="8532c-121">Поэтому перед переименованием объекта вначале отобразите зависимости объекта, чтобы определить, не повлияет ли предлагаемое изменение на работу каких-либо триггеров.</span><span class="sxs-lookup"><span data-stu-id="8532c-121">Therefore, before you rename an object, display the dependencies of the object first to determine whether any triggers are affected by the proposed change.</span></span>  
  
-   <span data-ttu-id="8532c-122">Кроме того, триггер DML можно изменить, чтобы зашифровать его определение.</span><span class="sxs-lookup"><span data-stu-id="8532c-122">A DML trigger can also be modified to encrypt its definition.</span></span>  
  
-   <span data-ttu-id="8532c-123">Для просмотра зависимостей триггера можно использовать среду [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или следующую функцию и представления каталога:</span><span class="sxs-lookup"><span data-stu-id="8532c-123">To view the dependencies of a trigger, you can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or the following function and catalog views:</span></span>  
  
    -   [<span data-ttu-id="8532c-124">sys.sql_expression_dependencies (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="8532c-124">sys.sql_expression_dependencies &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql)  
  
    -   [<span data-ttu-id="8532c-125">Функция динамического управления sys.dm_sql_referenced_entities (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="8532c-125">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referenced-entities-transact-sql)  
  
    -   [<span data-ttu-id="8532c-126">sys.dm_sql_referencing_entities (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="8532c-126">sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referencing-entities-transact-sql)  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8532c-127">безопасность</span><span class="sxs-lookup"><span data-stu-id="8532c-127">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8532c-128">Permissions</span><span class="sxs-lookup"><span data-stu-id="8532c-128">Permissions</span></span>  
 <span data-ttu-id="8532c-129">Для изменения триггера DML требуется разрешение ALTER в таблице или представлении, в котором определен триггер.</span><span class="sxs-lookup"><span data-stu-id="8532c-129">To alter a DML trigger requires ALTER permission on the table or view on which the trigger is defined.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8532c-130">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8532c-130">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-dml-trigger"></a><span data-ttu-id="8532c-131">Изменение триггера DML</span><span class="sxs-lookup"><span data-stu-id="8532c-131">To modify a DML trigger</span></span>  
  
1.  <span data-ttu-id="8532c-132">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)] и разверните его.</span><span class="sxs-lookup"><span data-stu-id="8532c-132">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="8532c-133">Разверните нужную базу данных, разверните узел **Таблицы**, а затем разверните таблицу, которая содержит изменяемый триггер.</span><span class="sxs-lookup"><span data-stu-id="8532c-133">Expand the database that you want, expand **Tables**, and then expand the table that contains the trigger that you want to modify.</span></span>  
  
3.  <span data-ttu-id="8532c-134">Разверните узел **Триггеры**, щелкните правой кнопкой мыши изменяемый триггер и выберите команду **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="8532c-134">Expand **Triggers**, right-click the trigger to modify, and then click **Modify**.</span></span>  
  
4.  <span data-ttu-id="8532c-135">Измените триггер и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="8532c-135">Modify the trigger, and then click **Execute**.</span></span>  
  
#### <a name="to-rename-a-dml-trigger"></a><span data-ttu-id="8532c-136">Переименование триггера DML</span><span class="sxs-lookup"><span data-stu-id="8532c-136">To rename a DML trigger</span></span>  
  
1.  <span data-ttu-id="8532c-137">[Удалите триггер](../triggers/dml-triggers.md) , который нужно переименовать.</span><span class="sxs-lookup"><span data-stu-id="8532c-137">[Delete the trigger](../triggers/dml-triggers.md) that you want to rename.</span></span>  
  
2.  <span data-ttu-id="8532c-138">[Повторно создайте триггер](../triggers/create-dml-triggers.md), указав новое имя.</span><span class="sxs-lookup"><span data-stu-id="8532c-138">[Re-create the trigger](../triggers/create-dml-triggers.md), specifying the new name.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8532c-139">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8532c-139">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-a-trigger-using-alter-trigger"></a><span data-ttu-id="8532c-140">Изменение триггера с помощью ALTER TRIGGER</span><span class="sxs-lookup"><span data-stu-id="8532c-140">To modify a trigger using ALTER TRIGGER</span></span>  
  
1.  <span data-ttu-id="8532c-141">Установите соединение с компонентом [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8532c-141">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8532c-142">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="8532c-142">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8532c-143">Скопируйте следующие примеры в запрос.</span><span class="sxs-lookup"><span data-stu-id="8532c-143">Copy and paste the following examples into the query.</span></span> <span data-ttu-id="8532c-144">Выполните первый пример, чтобы создать триггер DML, который выводит на клиент определяемое пользователем сообщение, когда пользователь пытается добавить или изменить данные в таблице `SalesPersonQuotaHistory` .</span><span class="sxs-lookup"><span data-stu-id="8532c-144">Execute the first example to create a DML trigger that prints a user-defined message to the client when a user tries to add or change data in the `SalesPersonQuotaHistory` table.</span></span> <span data-ttu-id="8532c-145">Выполните инструкцию [ALTER TRIGGER](/sql/t-sql/statements/alter-trigger-transact-sql) , чтобы изменить триггер так, чтобы он срабатывал только на операции `INSERT` .</span><span class="sxs-lookup"><span data-stu-id="8532c-145">Execute the [ALTER TRIGGER](/sql/t-sql/statements/alter-trigger-transact-sql) statement to modify the trigger to fire only on `INSERT` activities.</span></span> <span data-ttu-id="8532c-146">Этот триггер полезен, так как он напоминает пользователям, что при обновлениях и вставках строк в эту таблицу необходимо направить уведомление в отдел `Compensation`.</span><span class="sxs-lookup"><span data-stu-id="8532c-146">This trigger is helpful because it reminds the user that updates or inserts rows into this table to also notify the `Compensation` department.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID(N'Sales.bonus_reminder', N'TR') IS NOT NULL  
    DROP TRIGGER Sales.bonus_reminder;  
GO  
CREATE TRIGGER Sales.bonus_reminder  
ON Sales.SalesPersonQuotaHistory  
WITH ENCRYPTION  
AFTER INSERT, UPDATE   
AS RAISERROR ('Notify Compensation', 16, 10);  
GO  
  
```  
  
```sql  
USE AdventureWorks2012;  
GO  
ALTER TRIGGER Sales.bonus_reminder  
ON Sales.SalesPersonQuotaHistory  
AFTER INSERT  
AS RAISERROR ('Notify Compensation', 16, 10);  
GO  
  
```  
  
#### <a name="to-rename-a-trigger-using-drop-trigger-and-alter-trigger"></a><span data-ttu-id="8532c-147">Переименование триггера с помощью инструкций DROP TRIGGER и ALTER TRIGGER</span><span class="sxs-lookup"><span data-stu-id="8532c-147">To rename a trigger using DROP TRIGGER and ALTER TRIGGER</span></span>  
  
1.  <span data-ttu-id="8532c-148">Установите соединение с компонентом [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8532c-148">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8532c-149">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="8532c-149">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8532c-150">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="8532c-150">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="8532c-151">В этом примере инструкции [DROP TRIGGER](/sql/t-sql/statements/drop-trigger-transact-sql) и [ALTER TRIGGER](/sql/t-sql/statements/alter-trigger-transact-sql) используются для переименования триггера `Sales.bonus_reminder` в `Sales.bonus_reminder_2`.</span><span class="sxs-lookup"><span data-stu-id="8532c-151">This example use the [DROP TRIGGER](/sql/t-sql/statements/drop-trigger-transact-sql) and [ALTER TRIGGER](/sql/t-sql/statements/alter-trigger-transact-sql) statements to rename the `Sales.bonus_reminder` trigger to `Sales.bonus_reminder_2`.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID(N'Sales.bonus_reminder', N'TR') IS NOT NULL  
    DROP TRIGGER Sales.bonus_reminder;  
GO  
CREATE TRIGGER Sales.bonus_reminder_2  
ON Sales.SalesPersonQuotaHistory  
WITH ENCRYPTION  
AFTER INSERT, UPDATE   
AS RAISERROR ('Notify Compensation', 16, 10);  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="8532c-152">См. также:</span><span class="sxs-lookup"><span data-stu-id="8532c-152">See Also</span></span>  
 <span data-ttu-id="8532c-153">[CREATE TRIGGER (Transact-SQL)](/sql/t-sql/statements/create-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8532c-153">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span></span>  
 <span data-ttu-id="8532c-154">[DROP TRIGGER (Transact-SQL)](/sql/t-sql/statements/drop-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8532c-154">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span></span>  
 <span data-ttu-id="8532c-155">[ENABLE TRIGGER (Transact-SQL)](/sql/t-sql/statements/enable-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8532c-155">[ENABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/enable-trigger-transact-sql) </span></span>  
 <span data-ttu-id="8532c-156">[DISABLE TRIGGER (Transact-SQL)](/sql/t-sql/statements/disable-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8532c-156">[DISABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/disable-trigger-transact-sql) </span></span>  
 <span data-ttu-id="8532c-157">[EVENTDATA (Transact-SQL)](/sql/t-sql/functions/eventdata-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8532c-157">[EVENTDATA &#40;Transact-SQL&#41;](/sql/t-sql/functions/eventdata-transact-sql) </span></span>  
 <span data-ttu-id="8532c-158">[sp_rename (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8532c-158">[sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql) </span></span>  
 <span data-ttu-id="8532c-159">[ALTER TRIGGER (Transact-SQL)](/sql/t-sql/statements/alter-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8532c-159">[ALTER TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-trigger-transact-sql) </span></span>  
 <span data-ttu-id="8532c-160">[Получение сведений о триггерах DML](../triggers/get-information-about-dml-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="8532c-160">[Get Information About DML Triggers](../triggers/get-information-about-dml-triggers.md) </span></span>  
 <span data-ttu-id="8532c-161">[sp_help (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-help-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8532c-161">[sp_help &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-transact-sql) </span></span>  
 <span data-ttu-id="8532c-162">[sp_helptrigger (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-helptrigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8532c-162">[sp_helptrigger &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptrigger-transact-sql) </span></span>  
 <span data-ttu-id="8532c-163">[sys.triggers (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8532c-163">[sys.triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) </span></span>  
 <span data-ttu-id="8532c-164">[sys.trigger_events (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-trigger-events-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8532c-164">[sys.trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-trigger-events-transact-sql) </span></span>  
 <span data-ttu-id="8532c-165">[sys.sql_modules (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8532c-165">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span></span>  
 <span data-ttu-id="8532c-166">[sys.assembly_modules (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8532c-166">[sys.assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql) </span></span>  
 <span data-ttu-id="8532c-167">[sys.server_triggers (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8532c-167">[sys.server_triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) </span></span>  
 <span data-ttu-id="8532c-168">[sys.server_trigger_events (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8532c-168">[sys.server_trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql) </span></span>  
 <span data-ttu-id="8532c-169">[sys.server_sql_modules (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8532c-169">[sys.server_sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql) </span></span>  
 [<span data-ttu-id="8532c-170">sys.server_assembly_modules (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="8532c-170">sys.server_assembly_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-assembly-modules-transact-sql)  
  
  
