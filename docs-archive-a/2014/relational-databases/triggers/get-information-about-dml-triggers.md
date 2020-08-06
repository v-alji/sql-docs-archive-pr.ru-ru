---
title: Получение сведений о триггерах DML | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- metadata [SQL Server], triggers
- viewing DML triggers
- DML triggers, metadata
- displaying DML triggers
- status information [SQL Server], triggers
- DML triggers, viewing
ms.assetid: 37574aac-181d-4aca-a2cc-8abff64237dc
author: rothja
ms.author: jroth
ms.openlocfilehash: 2f65976d2f517137e23bd9e5e1c98cc76324bc49
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668148"
---
# <a name="get-information-about-dml-triggers"></a><span data-ttu-id="c8c3b-102">Получение сведений о триггерах DML</span><span class="sxs-lookup"><span data-stu-id="c8c3b-102">Get Information About DML Triggers</span></span>
  <span data-ttu-id="c8c3b-103">В этом разделе описывается получение сведений о триггерах DML в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8c3b-103">This topic describes how to get information about DML triggers in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="c8c3b-104">К таким сведениям относятся типы триггеров для таблицы, имя триггера, владелец триггера и дата создания или изменения триггера.</span><span class="sxs-lookup"><span data-stu-id="c8c3b-104">This information can include the types of triggers on a table, the name of a trigger, its owner and the date it was created or modified.</span></span> <span data-ttu-id="c8c3b-105">Если триггер не был зашифрован во время создания, то можно получить его определение.</span><span class="sxs-lookup"><span data-stu-id="c8c3b-105">If the trigger was not encrypted when it was created, you obtain the definition of the trigger.</span></span> <span data-ttu-id="c8c3b-106">По определению вы можете понять, каким образом триггер влияет на таблицу, для которой он определен.</span><span class="sxs-lookup"><span data-stu-id="c8c3b-106">You can use the definition to help you understand how a trigger affects the table up on which it is defined.</span></span> <span data-ttu-id="c8c3b-107">Кроме того, можно определить, какие объекты используются данным триггером.</span><span class="sxs-lookup"><span data-stu-id="c8c3b-107">Also, you can find out the objects that a specific trigger uses.</span></span> <span data-ttu-id="c8c3b-108">Эти сведения могут быть использованы для выявления объектов, которые воздействуют на триггер, если они изменяются или удаляются из базы данных.</span><span class="sxs-lookup"><span data-stu-id="c8c3b-108">With this information, you can identify the objects that affect the trigger if they are changed or deleted in the database.</span></span>  
  
 <span data-ttu-id="c8c3b-109">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="c8c3b-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c8c3b-110">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="c8c3b-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c8c3b-111">Безопасность</span><span class="sxs-lookup"><span data-stu-id="c8c3b-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c8c3b-112">**Для получения сведений о триггерах DML используется:**</span><span class="sxs-lookup"><span data-stu-id="c8c3b-112">**To get information about DML triggers, using:**</span></span>  
  
     [<span data-ttu-id="c8c3b-113">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c8c3b-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c8c3b-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c8c3b-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c8c3b-115">Перед началом</span><span class="sxs-lookup"><span data-stu-id="c8c3b-115">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c8c3b-116">безопасность</span><span class="sxs-lookup"><span data-stu-id="c8c3b-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c8c3b-117">Permissions</span><span class="sxs-lookup"><span data-stu-id="c8c3b-117">Permissions</span></span>  
 <span data-ttu-id="c8c3b-118">**sys.sql.modules**, **sys.object**, **sys.triggers**, **sys.events**, **sys.trigger_events**</span><span class="sxs-lookup"><span data-stu-id="c8c3b-118">**sys.sql.modules**, **sys.object**, **sys.triggers**, **sys.events**, **sys.trigger_events**</span></span>  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] <span data-ttu-id="c8c3b-119">Дополнительные сведения см. в разделе [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="c8c3b-119">For more information, see [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span></span>  
  
 <span data-ttu-id="c8c3b-120">OBJECT_DEFINITION, OBJECTPROPERTY, **sp_helptext**</span><span class="sxs-lookup"><span data-stu-id="c8c3b-120">OBJECT_DEFINITION, OBJECTPROPERTY, **sp_helptext**</span></span>  
 <span data-ttu-id="c8c3b-121">Необходимо быть членом роли **public**.</span><span class="sxs-lookup"><span data-stu-id="c8c3b-121">Requires membership in the **public** role.</span></span> <span data-ttu-id="c8c3b-122">Определения пользовательских объектов видимы владельцу объекта или получателям, которым предоставлено одно из следующих разрешений: ALTER, CONTROL, TAKE OWNERSHIP или VIEW DEFINITION.</span><span class="sxs-lookup"><span data-stu-id="c8c3b-122">The definition of user objects is visible to the object owner or grantees that have any one of the following permissions: ALTER, CONTROL, TAKE OWNERSHIP, or VIEW DEFINITION.</span></span> <span data-ttu-id="c8c3b-123">Эти разрешения неявно предоставляются членам предопределенных ролей базы данных **db_owner**, **db_ddladmin**и **db_securityadmin** .</span><span class="sxs-lookup"><span data-stu-id="c8c3b-123">These permissions are implicitly held by members of the **db_owner**, **db_ddladmin**, and **db_securityadmin** fixed database roles.</span></span>  
  
 <span data-ttu-id="c8c3b-124">**sys.sql_expression_dependencies**</span><span class="sxs-lookup"><span data-stu-id="c8c3b-124">**sys.sql_expression_dependencies**</span></span>  
 <span data-ttu-id="c8c3b-125">Необходимо разрешение VIEW DEFINITION в базе данных и разрешение SELECT на представление **sys.sql_expression_dependencies** в базе данных.</span><span class="sxs-lookup"><span data-stu-id="c8c3b-125">Requires VIEW DEFINITION permission on the database and SELECT permission on **sys.sql_expression_dependencies** for the database.</span></span> <span data-ttu-id="c8c3b-126">По умолчанию разрешение SELECT предоставляется только членам предопределенной роли базы данных **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="c8c3b-126">By default, SELECT permission is granted only to members of the **db_owner** fixed database role.</span></span> <span data-ttu-id="c8c3b-127">Если разрешения SELECT и VIEW DEFINITION предоставлены другому пользователю, он может просматривать все зависимости в базе данных.</span><span class="sxs-lookup"><span data-stu-id="c8c3b-127">When SELECT and VIEW DEFINITION permissions are granted to another user, the grantee can view all dependencies in the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c8c3b-128">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c8c3b-128">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-definition-of-a-dml-trigger"></a><span data-ttu-id="c8c3b-129">Просмотр определения триггера DML</span><span class="sxs-lookup"><span data-stu-id="c8c3b-129">To view the definition of a DML trigger</span></span>  
  
1.  <span data-ttu-id="c8c3b-130">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] и разверните его.</span><span class="sxs-lookup"><span data-stu-id="c8c3b-130">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="c8c3b-131">Разверните нужную базу данных, разверните узел **Таблицы**, а затем разверните таблицу, содержащую триггер, для которого нужно просмотреть определение.</span><span class="sxs-lookup"><span data-stu-id="c8c3b-131">Expand the database that you want, expand **Tables**, and then expand the table that contains the trigger for which you want to view the definition.</span></span>  
  
3.  <span data-ttu-id="c8c3b-132">Разверните узел **Триггеры**, щелкните правой кнопкой мыши нужный триггер и выберите команду **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="c8c3b-132">Expand **Triggers**, right-click the trigger you want, and then click **Modify**.</span></span> <span data-ttu-id="c8c3b-133">В окне запроса появится определение триггера DML.</span><span class="sxs-lookup"><span data-stu-id="c8c3b-133">The definition of the DML trigger appears in the query window.</span></span>  
  
#### <a name="to-view-the-dependencies-of-a-dml-trigger"></a><span data-ttu-id="c8c3b-134">Просмотр зависимостей триггера DML</span><span class="sxs-lookup"><span data-stu-id="c8c3b-134">To view the dependencies of a DML trigger</span></span>  
  
1.  <span data-ttu-id="c8c3b-135">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] и разверните его.</span><span class="sxs-lookup"><span data-stu-id="c8c3b-135">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="c8c3b-136">Разверните нужную базу данных, разверните узел **Таблицы**, а затем разверните таблицу, содержащую триггер и зависимости, которые нужно просмотреть.</span><span class="sxs-lookup"><span data-stu-id="c8c3b-136">Expand the database that you want, expand **Tables**, and then expand the table that contains the trigger and its dependencies that you want to view.</span></span>  
  
3.  <span data-ttu-id="c8c3b-137">Разверните узел **Триггеры**, щелкните правой кнопкой мыши нужный триггер и выберите команду **Просмотреть зависимости**.</span><span class="sxs-lookup"><span data-stu-id="c8c3b-137">Expand **Triggers**, right-click the trigger you want, and then click **View Dependencies**.</span></span>  
  
4.  <span data-ttu-id="c8c3b-138">Для просмотра объектов, зависящих от триггера DML, в окне **Зависимости объектов** выберите **Объекты, зависящие от \<DML trigger name>** .</span><span class="sxs-lookup"><span data-stu-id="c8c3b-138">In the **Object Dependencies** window, to view the objects that depend on the DML trigger, select **Objects that depend on \<DML trigger name>**.</span></span> <span data-ttu-id="c8c3b-139">Объекты отображаются в области **Зависимости** .</span><span class="sxs-lookup"><span data-stu-id="c8c3b-139">The objects appear in the **Dependencies** area.</span></span>  
  
     <span data-ttu-id="c8c3b-140">Чтобы просмотреть объекты, от которых зависит триггер DML, выберите пункт **Объекты, от которых зависит \<DML trigger name>** .</span><span class="sxs-lookup"><span data-stu-id="c8c3b-140">To view the objects on which the DML depends, select **Objects on which \<DML trigger name> depends**.</span></span> <span data-ttu-id="c8c3b-141">Объекты отображаются в области **Зависимости** .</span><span class="sxs-lookup"><span data-stu-id="c8c3b-141">The objects appear in the **Dependencies** area.</span></span> <span data-ttu-id="c8c3b-142">Разверните каждый узел, чтобы просмотреть все объекты.</span><span class="sxs-lookup"><span data-stu-id="c8c3b-142">Expand each node to see all the objects.</span></span>  
  
5.  <span data-ttu-id="c8c3b-143">Чтобы получить сведения об объекте, который появляется в области **Зависимости** , щелкните его.</span><span class="sxs-lookup"><span data-stu-id="c8c3b-143">To obtain information about an object that appears in the **Dependencies** area, click the object.</span></span> <span data-ttu-id="c8c3b-144">В поле **Выбранный объект** сведения указываются в полях **Имя**, **Тип**и **Тип зависимости** .</span><span class="sxs-lookup"><span data-stu-id="c8c3b-144">In the **Selected object** field, information is provided in the **Name**, **Type**, and **Dependency type** boxes.</span></span>  
  
6.  <span data-ttu-id="c8c3b-145">Нажмите кнопку **ОК** , чтобы закрыть окно **Зависимости объекта**.</span><span class="sxs-lookup"><span data-stu-id="c8c3b-145">To close the **Object Dependencies** window, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c8c3b-146">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c8c3b-146">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-definition-of-a-dml-trigger"></a><span data-ttu-id="c8c3b-147">Просмотр определения триггера DML</span><span class="sxs-lookup"><span data-stu-id="c8c3b-147">To view the definition of a DML trigger</span></span>  
  
1.  <span data-ttu-id="c8c3b-148">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8c3b-148">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c8c3b-149">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="c8c3b-149">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c8c3b-150">Скопируйте и вставьте один из следующих примеров в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="c8c3b-150">Copy and paste one of the following examples into the query window and click **Execute**.</span></span> <span data-ttu-id="c8c3b-151">В каждом примере показано, как можно просмотреть определение триггера `iuPerson` .</span><span class="sxs-lookup"><span data-stu-id="c8c3b-151">Each example shows how you can view the definition of the `iuPerson` trigger.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
SELECT definition   
FROM sys.sql_modules  
WHERE object_id = OBJECT_ID(N'Person.iuPerson');   
GO  
```  
  
```sql  
USE AdventureWorks2012;   
GO  
SELECT OBJECT_DEFINITION (OBJECT_ID(N'Person.iuPerson')) AS ObjectDefinition;   
GO  
  
```  
  
```sql  
USE AdventureWorks2012;   
GO  
EXEC sp_helptext 'Person.iuPerson'  
GO  
  
```  
  
#### <a name="to-view-the-dependencies-of-a-dml-trigger"></a><span data-ttu-id="c8c3b-152">Просмотр зависимостей триггера DML</span><span class="sxs-lookup"><span data-stu-id="c8c3b-152">To view the dependencies of a DML trigger</span></span>  
  
1.  <span data-ttu-id="c8c3b-153">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8c3b-153">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c8c3b-154">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="c8c3b-154">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c8c3b-155">Скопируйте и вставьте один из следующих примеров в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="c8c3b-155">Copy and paste one of the following examples into the query window and click **Execute**.</span></span> <span data-ttu-id="c8c3b-156">В каждом примере показано, как можно просмотреть зависимости триггера `iuPerson` .</span><span class="sxs-lookup"><span data-stu-id="c8c3b-156">Each example shows how you can view the dependencies of `iuPerson` trigger.</span></span>  
  
```  
USE AdventureWorks2012;   
GO  
SELECT OBJECT_NAME(referencing_id) AS referencing_entity_name,   
    o.type_desc AS referencing_desciption,   
    COALESCE(COL_NAME(referencing_id, referencing_minor_id), '(n/a)') AS referencing_minor_id,   
    referencing_class_desc, referenced_class_desc,   
    referenced_server_name, referenced_database_name, referenced_schema_name,   
    referenced_entity_name,   
    COALESCE(COL_NAME(referenced_id, referenced_minor_id), '(n/a)') AS referenced_column_name,   
    is_caller_dependent, is_ambiguous  
FROM sys.sql_expression_dependencies AS sed  
INNER JOIN sys.objects AS o ON sed.referencing_id = o.object_id  
WHERE referencing_id = OBJECT_ID(N'Person.iuPerson');   
GO  
  
```  
  
#### <a name="to-view-information-about-dml-triggers-in-the-database"></a><span data-ttu-id="c8c3b-157">Просмотр сведений о триггерах DML в базе данных</span><span class="sxs-lookup"><span data-stu-id="c8c3b-157">To view information about DML triggers in the database</span></span>  
  
1.  <span data-ttu-id="c8c3b-158">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8c3b-158">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c8c3b-159">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="c8c3b-159">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c8c3b-160">Скопируйте и вставьте один из следующих примеров в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="c8c3b-160">Copy and paste one of the following examples into the query window and click **Execute**.</span></span> <span data-ttu-id="c8c3b-161">В каждом примере показано, как можно просмотреть сведения о триггерах DML (`TR`) в базе данных.</span><span class="sxs-lookup"><span data-stu-id="c8c3b-161">Each example shows how you can view information about DML triggers (`TR`) in the database.</span></span>  
  
```  
USE AdventureWorks2012;   
GO  
SELECT  name, parent_id, create_date, modify_date, is_instead_of_trigger  
FROM sys.triggers  
WHERE type = 'TR';   
GO  
  
```  
  
```sql  
USE AdventureWorks2012;   
GO  
SELECT  name, object_id, schema_id, parent_object_id, type_desc, create_date, modify_date, is_published  
FROM sys.objects  
WHERE type = 'TR';   
GO  
  
```  
  
```sql  
USE AdventureWorks2012;   
GO  
SELECT OBJECTPROPERTY(OBJECT_ID(N'Person.iuPerson'), 'ExecIsInsteadOfTrigger');   
GO  
  
```  
  
#### <a name="to-view-information-about-events-that-fire-a-dml-trigger"></a><span data-ttu-id="c8c3b-162">Просмотр сведений о событиях, которые вызывают срабатывание триггера DML</span><span class="sxs-lookup"><span data-stu-id="c8c3b-162">To view information about events that fire a DML trigger</span></span>  
  
1.  <span data-ttu-id="c8c3b-163">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8c3b-163">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c8c3b-164">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="c8c3b-164">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c8c3b-165">Скопируйте и вставьте один из следующих примеров в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="c8c3b-165">Copy and paste one of the following examples into the query window and click **Execute**.</span></span> <span data-ttu-id="c8c3b-166">В каждом примере показано, как можно просмотреть события, которые вызывают срабатывание триггера `iuPerson` .</span><span class="sxs-lookup"><span data-stu-id="c8c3b-166">Each example shows how you can view the events that fire the `iuPerson` trigger.</span></span>  
  
```sql  
USE AdventureWorks2012;   
GO  
SELECT object_id, type, type_desc, is_trigger_event, event_group_type, event_group_type_desc   
FROM sys.events  
WHERE object_id = OBJECT_ID('Person.iuPerson');   
GO  
```  
  
```sql  
USE AdventureWorks2012;   
GO   
SELECT object_id, type,is_first, is_last  
FROM sys.trigger_events  
WHERE object_id = OBJECT_ID('Person.iuPerson');   
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="c8c3b-167">См. также:</span><span class="sxs-lookup"><span data-stu-id="c8c3b-167">See Also</span></span>  
 <span data-ttu-id="c8c3b-168">[CREATE TRIGGER (Transact-SQL)](/sql/t-sql/statements/create-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c8c3b-168">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span></span>  
 <span data-ttu-id="c8c3b-169">[DROP TRIGGER (Transact-SQL)](/sql/t-sql/statements/drop-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c8c3b-169">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span></span>  
 <span data-ttu-id="c8c3b-170">[ENABLE TRIGGER (Transact-SQL)](/sql/t-sql/statements/enable-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c8c3b-170">[ENABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/enable-trigger-transact-sql) </span></span>  
 <span data-ttu-id="c8c3b-171">[DISABLE TRIGGER (Transact-SQL)](/sql/t-sql/statements/disable-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c8c3b-171">[DISABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/disable-trigger-transact-sql) </span></span>  
 <span data-ttu-id="c8c3b-172">[EVENTDATA (Transact-SQL)](/sql/t-sql/functions/eventdata-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c8c3b-172">[EVENTDATA &#40;Transact-SQL&#41;](/sql/t-sql/functions/eventdata-transact-sql) </span></span>  
 <span data-ttu-id="c8c3b-173">[sp_rename (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c8c3b-173">[sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql) </span></span>  
 <span data-ttu-id="c8c3b-174">[ALTER TRIGGER (Transact-SQL)](/sql/t-sql/statements/alter-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c8c3b-174">[ALTER TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-trigger-transact-sql) </span></span>  
 <span data-ttu-id="c8c3b-175">[sp_help (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-help-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c8c3b-175">[sp_help &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-transact-sql) </span></span>  
 <span data-ttu-id="c8c3b-176">[sp_helptrigger (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-helptrigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c8c3b-176">[sp_helptrigger &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptrigger-transact-sql) </span></span>  
 <span data-ttu-id="c8c3b-177">[sys.triggers (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c8c3b-177">[sys.triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) </span></span>  
 <span data-ttu-id="c8c3b-178">[sys.trigger_events (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-trigger-events-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c8c3b-178">[sys.trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-trigger-events-transact-sql) </span></span>  
 <span data-ttu-id="c8c3b-179">[sys.sql_modules (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c8c3b-179">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span></span>  
 <span data-ttu-id="c8c3b-180">[sys.assembly_modules (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c8c3b-180">[sys.assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql) </span></span>  
 <span data-ttu-id="c8c3b-181">[sys.server_triggers (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c8c3b-181">[sys.server_triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) </span></span>  
 <span data-ttu-id="c8c3b-182">[sys.server_trigger_events (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c8c3b-182">[sys.server_trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql) </span></span>  
 <span data-ttu-id="c8c3b-183">[sys.server_sql_modules (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c8c3b-183">[sys.server_sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql) </span></span>  
 <span data-ttu-id="c8c3b-184">[sys.server_assembly_modules (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-server-assembly-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c8c3b-184">[sys.server_assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-assembly-modules-transact-sql) </span></span>  
 <span data-ttu-id="c8c3b-185">[OBJECTPROPERTY (Transact-SQL)](/sql/t-sql/functions/objectpropertyex-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c8c3b-185">[OBJECTPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectpropertyex-transact-sql) </span></span>  
 [<span data-ttu-id="c8c3b-186">OBJECT_DEFINITION (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c8c3b-186">OBJECT_DEFINITION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/object-definition-transact-sql)  
  
  
