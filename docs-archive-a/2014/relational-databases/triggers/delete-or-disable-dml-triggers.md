---
title: Удаление или отключение триггеров DML | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- DML triggers, disabling
- removing DML triggers
- disabling DML triggers
- dropping DML triggers
- deleting DML triggers
- DML triggers, removing
ms.assetid: 0f97f953-33c5-4b26-afeb-db2a26ce38b4
author: rothja
ms.author: jroth
ms.openlocfilehash: 39b345ade1258987df06938791ac0024e8612365
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668152"
---
# <a name="delete-or-disable-dml-triggers"></a><span data-ttu-id="4cc02-102">Удаление или отключение триггеров DML</span><span class="sxs-lookup"><span data-stu-id="4cc02-102">Delete or Disable DML Triggers</span></span>
  <span data-ttu-id="4cc02-103">В этом разделе описывается удаление или отключение триггера DML в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4cc02-103">This topic describes how to delete or disable a DML trigger in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="4cc02-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="4cc02-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4cc02-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="4cc02-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4cc02-106">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="4cc02-106">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="4cc02-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="4cc02-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4cc02-108">**Для удаления или отключения триггера DML используется:**</span><span class="sxs-lookup"><span data-stu-id="4cc02-108">**To delete or disable a DML trigger, using:**</span></span>  
  
     [<span data-ttu-id="4cc02-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4cc02-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4cc02-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4cc02-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4cc02-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="4cc02-111">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="4cc02-112">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="4cc02-112">Recommendations</span></span>  
  
-   <span data-ttu-id="4cc02-113">После удаления триггер удаляется из текущей базы данных.</span><span class="sxs-lookup"><span data-stu-id="4cc02-113">When a trigger is deleted, it is dropped from the current database.</span></span> <span data-ttu-id="4cc02-114">Это не повлияет на таблицу и данные, на которых он основан.</span><span class="sxs-lookup"><span data-stu-id="4cc02-114">The table and the data upon which it is based are not affected.</span></span> <span data-ttu-id="4cc02-115">При удалении таблицы автоматически удаляются все триггеры в ней.</span><span class="sxs-lookup"><span data-stu-id="4cc02-115">Deleting a table automatically deletes any triggers on the table.</span></span>  
  
-   <span data-ttu-id="4cc02-116">По умолчанию при создании триггер включается.</span><span class="sxs-lookup"><span data-stu-id="4cc02-116">A trigger is enabled by default when it is created.</span></span>  
  
-   <span data-ttu-id="4cc02-117">Отключение триггера не сбрасывает его.</span><span class="sxs-lookup"><span data-stu-id="4cc02-117">Disabling a trigger does not drop it.</span></span> <span data-ttu-id="4cc02-118">Триггер все еще существует как объект в текущей базе данных.</span><span class="sxs-lookup"><span data-stu-id="4cc02-118">The trigger still exists as an object in the current database.</span></span> <span data-ttu-id="4cc02-119">Впрочем, триггер в инструкциях INSERT, UPDATE или DELETE не сработает при выполнении любой из них.</span><span class="sxs-lookup"><span data-stu-id="4cc02-119">However, the trigger will not fire when any INSERT, UPDATE, or DELETE statement on which it was programmed is executed.</span></span> <span data-ttu-id="4cc02-120">Отключенные триггеры можно повторно включать.</span><span class="sxs-lookup"><span data-stu-id="4cc02-120">Triggers that are disabled can be reenabled.</span></span> <span data-ttu-id="4cc02-121">При включении триггера он не создается повторно.</span><span class="sxs-lookup"><span data-stu-id="4cc02-121">Enabling a trigger does not re-create it.</span></span> <span data-ttu-id="4cc02-122">Он срабатывает так же, как после создания.</span><span class="sxs-lookup"><span data-stu-id="4cc02-122">The trigger fires in the same manner as when it was originally created.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4cc02-123">безопасность</span><span class="sxs-lookup"><span data-stu-id="4cc02-123">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4cc02-124">Permissions</span><span class="sxs-lookup"><span data-stu-id="4cc02-124">Permissions</span></span>  
 <span data-ttu-id="4cc02-125">Чтобы удалить триггер DML, необходимо разрешение ALTER для таблицы или представления, в которых определен данный триггер.</span><span class="sxs-lookup"><span data-stu-id="4cc02-125">To delete a DML trigger requires ALTER permission on the table or view on which the trigger is defined.</span></span>  
  
 <span data-ttu-id="4cc02-126">Для отключения или включения триггера DML пользователь должен обладать как минимум разрешением ALTER для таблицы или представления, где создан триггер.</span><span class="sxs-lookup"><span data-stu-id="4cc02-126">To disable or enable a DML trigger, at a minimum, a user must have ALTER permission on the table or view on which the trigger was created.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4cc02-127">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4cc02-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-dml-trigger"></a><span data-ttu-id="4cc02-128">Удаление триггера DML</span><span class="sxs-lookup"><span data-stu-id="4cc02-128">To delete a DML trigger</span></span>  
  
1.  <span data-ttu-id="4cc02-129">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] и разверните его.</span><span class="sxs-lookup"><span data-stu-id="4cc02-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="4cc02-130">Разверните нужную базу данных, разверните узел **Таблицы**, а затем разверните таблицу, которая содержит удаляемый триггер.</span><span class="sxs-lookup"><span data-stu-id="4cc02-130">Expand the database that you want, expand **Tables**, and then expand the table that contains the trigger that you want to delete.</span></span>  
  
3.  <span data-ttu-id="4cc02-131">Разверните узел **Триггеры**, щелкните правой кнопкой мыши нужный триггер и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="4cc02-131">Expand **Triggers**, right-click the trigger to delete, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="4cc02-132">В диалоговом окне **Удаление объекта** проверьте триггер и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="4cc02-132">In the **Delete Object** dialog box, verify the trigger to delete, and then click **OK**.</span></span>  
  
#### <a name="to-disable-and-enable-a-dml-trigger"></a><span data-ttu-id="4cc02-133">Отключение и включение триггера DML</span><span class="sxs-lookup"><span data-stu-id="4cc02-133">To disable and enable a DML trigger</span></span>  
  
1.  <span data-ttu-id="4cc02-134">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] и разверните его.</span><span class="sxs-lookup"><span data-stu-id="4cc02-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="4cc02-135">Разверните нужную базу данных, разверните узел **Таблицы**, а затем разверните таблицу, которая содержит отключаемый триггер.</span><span class="sxs-lookup"><span data-stu-id="4cc02-135">Expand the database that you want, expand **Tables**, and then expand the table that contains the trigger that you want to disable.</span></span>  
  
3.  <span data-ttu-id="4cc02-136">Разверните узел **Триггеры**, щелкните правой кнопкой мыши нужный триггер и выберите команду **Отключить**.</span><span class="sxs-lookup"><span data-stu-id="4cc02-136">Expand **Triggers**, right-click the trigger to disable, and then click **Disable**.</span></span>  
  
4.  <span data-ttu-id="4cc02-137">Чтобы включить триггер, выберите команду **Включить**.</span><span class="sxs-lookup"><span data-stu-id="4cc02-137">To enable the trigger, click **Enable**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4cc02-138">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4cc02-138">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-dml-trigger"></a><span data-ttu-id="4cc02-139">Удаление триггера DML</span><span class="sxs-lookup"><span data-stu-id="4cc02-139">To delete a DML trigger</span></span>  
  
1.  <span data-ttu-id="4cc02-140">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4cc02-140">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4cc02-141">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="4cc02-141">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4cc02-142">Скопируйте и вставьте следующие примеры в окно запроса.</span><span class="sxs-lookup"><span data-stu-id="4cc02-142">Copy and paste the following examples into the query window.</span></span> <span data-ttu-id="4cc02-143">Выполните инструкцию [CREATE TRIGGER](/sql/t-sql/statements/create-trigger-transact-sql) , чтобы создать триггер `Sales.bonus_reminder` .</span><span class="sxs-lookup"><span data-stu-id="4cc02-143">Execute the [CREATE TRIGGER](/sql/t-sql/statements/create-trigger-transact-sql) statement to create the `Sales.bonus_reminder` trigger.</span></span> <span data-ttu-id="4cc02-144">Чтобы удалить триггер, выполните инструкцию [DROP TRIGGER](/sql/t-sql/statements/drop-trigger-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="4cc02-144">To delete the trigger, execute the [DROP TRIGGER](/sql/t-sql/statements/drop-trigger-transact-sql) statement.</span></span>  
  
```sql  
--Create the trigger.  
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
--Delete the trigger.  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID ('Sales.bonus_reminder', 'TR') IS NOT NULL  
   DROP TRIGGER Sales.bonus_reminder;  
GO  
  
```  
  
#### <a name="to-disable-and-enable-a-dml-trigger"></a><span data-ttu-id="4cc02-145">Отключение и включение триггера DML</span><span class="sxs-lookup"><span data-stu-id="4cc02-145">To disable and enable a DML trigger</span></span>  
  
1.  <span data-ttu-id="4cc02-146">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4cc02-146">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4cc02-147">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="4cc02-147">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4cc02-148">Скопируйте и вставьте следующие примеры в окно запроса.</span><span class="sxs-lookup"><span data-stu-id="4cc02-148">Copy and paste the following examples into the query window.</span></span> <span data-ttu-id="4cc02-149">Выполните инструкцию [CREATE TRIGGER](/sql/t-sql/statements/create-trigger-transact-sql) , чтобы создать триггер `Sales.bonus_reminder` .</span><span class="sxs-lookup"><span data-stu-id="4cc02-149">Execute the [CREATE TRIGGER](/sql/t-sql/statements/create-trigger-transact-sql) statement to create the `Sales.bonus_reminder` trigger.</span></span> <span data-ttu-id="4cc02-150">Чтобы отключить или включить триггер, выполните соответственно инструкцию [DISABLE TRIGGER](/sql/t-sql/statements/disable-trigger-transact-sql) или [ENABLE TRIGGER](/sql/t-sql/statements/enable-trigger-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="4cc02-150">To disable and enable the trigger, execute the [DISABLE TRIGGER](/sql/t-sql/statements/disable-trigger-transact-sql) and [ENABLE TRIGGER](/sql/t-sql/statements/enable-trigger-transact-sql) statements, respectively.</span></span>  
  
```sql  
--Create the trigger.  
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
--Disable the trigger.  
USE AdventureWorks2012;  
GO  
DISABLE TRIGGER Sales.bonus_reminder ON Sales.SalesPersonQuotaHistory;  
GO  
  
```  
  
```sql  
--Enable the trigger.  
USE AdventureWorks2012;  
GO  
ENABLE TRIGGER Sales.bonus_reminder ON Sales.SalesPersonQuotaHistory;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="4cc02-151">См. также:</span><span class="sxs-lookup"><span data-stu-id="4cc02-151">See Also</span></span>  
 <span data-ttu-id="4cc02-152">[ALTER TRIGGER (Transact-SQL)](/sql/t-sql/statements/alter-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4cc02-152">[ALTER TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-trigger-transact-sql) </span></span>  
 <span data-ttu-id="4cc02-153">[CREATE TRIGGER (Transact-SQL)](/sql/t-sql/statements/create-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4cc02-153">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span></span>  
 <span data-ttu-id="4cc02-154">[DROP TRIGGER (Transact-SQL)](/sql/t-sql/statements/drop-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4cc02-154">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span></span>  
 <span data-ttu-id="4cc02-155">[ENABLE TRIGGER (Transact-SQL)](/sql/t-sql/statements/enable-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4cc02-155">[ENABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/enable-trigger-transact-sql) </span></span>  
 <span data-ttu-id="4cc02-156">[DISABLE TRIGGER (Transact-SQL)](/sql/t-sql/statements/disable-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4cc02-156">[DISABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/disable-trigger-transact-sql) </span></span>  
 <span data-ttu-id="4cc02-157">[EVENTDATA (Transact-SQL)](/sql/t-sql/functions/eventdata-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4cc02-157">[EVENTDATA &#40;Transact-SQL&#41;](/sql/t-sql/functions/eventdata-transact-sql) </span></span>  
 <span data-ttu-id="4cc02-158">[Получение сведений о триггерах DML](dml-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="4cc02-158">[Get Information About DML Triggers](dml-triggers.md) </span></span>  
 <span data-ttu-id="4cc02-159">[sp_help (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-help-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4cc02-159">[sp_help &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-transact-sql) </span></span>  
 <span data-ttu-id="4cc02-160">[sp_helptrigger (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-helptrigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4cc02-160">[sp_helptrigger &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptrigger-transact-sql) </span></span>  
 <span data-ttu-id="4cc02-161">[sys.triggers (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4cc02-161">[sys.triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) </span></span>  
 <span data-ttu-id="4cc02-162">[sys.trigger_events (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-trigger-events-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4cc02-162">[sys.trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-trigger-events-transact-sql) </span></span>  
 <span data-ttu-id="4cc02-163">[sys.sql_modules (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4cc02-163">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span></span>  
 <span data-ttu-id="4cc02-164">[sys.assembly_modules (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4cc02-164">[sys.assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql) </span></span>  
 <span data-ttu-id="4cc02-165">[sys.server_triggers (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4cc02-165">[sys.server_triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) </span></span>  
 <span data-ttu-id="4cc02-166">[sys.server_trigger_events (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4cc02-166">[sys.server_trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql) </span></span>  
 <span data-ttu-id="4cc02-167">[sys.server_sql_modules (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4cc02-167">[sys.server_sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql) </span></span>  
 [<span data-ttu-id="4cc02-168">sys.server_assembly_modules (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4cc02-168">sys.server_assembly_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-assembly-modules-transact-sql)  
  
  
