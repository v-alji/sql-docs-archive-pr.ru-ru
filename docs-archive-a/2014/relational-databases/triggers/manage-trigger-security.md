---
title: Управление безопасностью триггеров | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- triggers [SQL Server], security
ms.assetid: e94720a8-a3a2-4364-b0a3-bbe86e3ce4d5
author: rothja
ms.author: jroth
ms.openlocfilehash: fdc176dcad50c3bf28f058c3724a01267975bfc5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668136"
---
# <a name="manage-trigger-security"></a><span data-ttu-id="ac087-102">Управление безопасностью триггеров</span><span class="sxs-lookup"><span data-stu-id="ac087-102">Manage Trigger Security</span></span>
  <span data-ttu-id="ac087-103">Как триггеры DML, так и триггеры DDL по умолчанию выполняются в контексте того пользователя, который вызывает триггер.</span><span class="sxs-lookup"><span data-stu-id="ac087-103">By default, both DML and DDL triggers execute under the context of the user that calls the trigger.</span></span> <span data-ttu-id="ac087-104">Это пользователь, который выполняет инструкцию, вызывающую запуск триггера.</span><span class="sxs-lookup"><span data-stu-id="ac087-104">The caller of a trigger is the user that executes the statement that causes the trigger to run.</span></span> <span data-ttu-id="ac087-105">Например, если пользователь **Mary** выполняет инструкцию DELETE, которая запускает триггер DML **DML_trigMary** , то код внутри **DML_trigMary** выполняется в контексте прав доступа пользователя **Mary**.</span><span class="sxs-lookup"><span data-stu-id="ac087-105">For example, if user **Mary** executes a DELETE statement that causes DML trigger **DML_trigMary** to run, the code inside **DML_trigMary** executes in the context of the user privileges for **Mary**.</span></span> <span data-ttu-id="ac087-106">Этим поведением по умолчанию могут воспользоваться те пользователи, которые хотят внести небезопасный код в экземпляр базы данных или сервера.</span><span class="sxs-lookup"><span data-stu-id="ac087-106">This default behavior can be exploited by users who want to introduce malicious code in the database or server instance.</span></span> <span data-ttu-id="ac087-107">Например, следующий триггер DDL создан пользователем `JohnDoe`:</span><span class="sxs-lookup"><span data-stu-id="ac087-107">For example, the following DDL trigger is created by user `JohnDoe`:</span></span>  
  
 `CREATE TRIGGER DDL_trigJohnDoe`  
  
 `ON DATABASE`  
  
 `FOR ALTER_TABLE`  
  
 `AS`  
  
 `GRANT CONTROL SERVER TO JohnDoe ;`  
  
 `GO`  
  
 <span data-ttu-id="ac087-108">В этом триггере подразумевается, что как только пользователь с разрешением на выполнение инструкции `GRANT CONTROL SERVER` , например член предопределенной роли сервера **sysadmin** , выполнит инструкцию `ALTER TABLE` , пользователь `JohnDoe` получит права `CONTROL SERVER` .</span><span class="sxs-lookup"><span data-stu-id="ac087-108">What this trigger means is that as soon as a user that has permission to execute a `GRANT CONTROL SERVER` statement, such as a member of the **sysadmin** fixed server role, executes an `ALTER TABLE` statement, `JohnDoe` is granted `CONTROL SERVER` permission.</span></span> <span data-ttu-id="ac087-109">Другими словами, хотя `JohnDoe` не может предоставить права `CONTROL SERVER` самому себе, он создал код триггера, который предоставит ему разрешение работать с повышенными правами доступа.</span><span class="sxs-lookup"><span data-stu-id="ac087-109">In other words, although `JohnDoe` cannot grant `CONTROL SERVER` permission to himself, he enabled the trigger code that grants him this permission to execute under escalated privileges.</span></span> <span data-ttu-id="ac087-110">Эта уязвимость относится как к триггерам DML, так и к триггерам DDL.</span><span class="sxs-lookup"><span data-stu-id="ac087-110">Both DML and DDL triggers are open to this kind of security threat.</span></span>  
  
## <a name="trigger-security-best-practices"></a><span data-ttu-id="ac087-111">Способы защиты триггеров</span><span class="sxs-lookup"><span data-stu-id="ac087-111">Trigger Security Best Practices</span></span>  
 <span data-ttu-id="ac087-112">Чтобы предотвратить выполнение кода триггера с повышенными правами доступа, примите следующие меры.</span><span class="sxs-lookup"><span data-stu-id="ac087-112">You can take the following measures to prevent trigger code from executing under escalated privileges:</span></span>  
  
-   <span data-ttu-id="ac087-113">Проверьте базу данных и экземпляр сервера на наличие триггеров DDL и DDL. Для этого выполните соответствующие запросы к представлениям каталогов [sys.triggers](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) и [sys.server_triggers](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="ac087-113">Be aware of the DML and DDL triggers that exist in the database and on the server instance by querying the [sys.triggers](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) and [sys.server_triggers](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) catalog views.</span></span> <span data-ttu-id="ac087-114">Следующий запрос возвращает все триггеры DML и DDL уровня базы данных в текущей базе данных, а также все триггеры DDL уровня сервера на экземпляре сервера.</span><span class="sxs-lookup"><span data-stu-id="ac087-114">The following query returns all DML and database-level DDL triggers in the current database, and all server-level DDL triggers on the server instance:</span></span>  
  
    ```  
    SELECT type, name, parent_class_desc FROM sys.triggers  
    UNION  
    SELECT type, name, parent_class_desc FROM sys.server_triggers ;  
    ```  
  
-   <span data-ttu-id="ac087-115">С помощью инструкции [DISABLE TRIGGER](/sql/t-sql/statements/disable-trigger-transact-sql) запретите триггеры, которые могут нарушить целостность базы данных или сервера при выполнении с повышенными правами доступа.</span><span class="sxs-lookup"><span data-stu-id="ac087-115">Use [DISABLE TRIGGER](/sql/t-sql/statements/disable-trigger-transact-sql) to disable triggers that can harm the integrity of the database or server if the triggers execute under escalated privileges.</span></span> <span data-ttu-id="ac087-116">Следующая инструкция отключает все триггеры DDL уровня базы данных в текущей базе данных:</span><span class="sxs-lookup"><span data-stu-id="ac087-116">The following statement disables all database-level DDL triggers in the current database:</span></span>  
  
    ```  
    DISABLE TRIGGER ALL ON DATABASE  
    ```  
  
     <span data-ttu-id="ac087-117">Эта инструкция отключает все триггеры DDL уровня сервера на экземпляре сервера:</span><span class="sxs-lookup"><span data-stu-id="ac087-117">This statement disables all server-level DDL triggers on the server instance:</span></span>  
  
    ```  
    DISABLE TRIGGER ALL ON ALL SERVER  
    ```  
  
     <span data-ttu-id="ac087-118">Эта инструкция отключает все триггеры DML в текущей базе данных:</span><span class="sxs-lookup"><span data-stu-id="ac087-118">This statement disables all DML triggers in the current database:</span></span>  
  
    ```  
    DECLARE @schema_name sysname, @trigger_name sysname, @object_name sysname ;  
    DECLARE @sql nvarchar(max) ;  
    DECLARE trig_cur CURSOR FORWARD_ONLY READ_ONLY FOR  
        SELECT SCHEMA_NAME(schema_id) AS schema_name,  
            name AS trigger_name,  
            OBJECT_NAME(parent_object_id) as object_name  
        FROM sys.objects WHERE type in ('TR', 'TA') ;  
  
    OPEN trig_cur ;  
    FETCH NEXT FROM trig_cur INTO @schema_name, @trigger_name, @object_name ;  
  
    WHILE @@FETCH_STATUS = 0  
    BEGIN  
        SELECT @sql = 'DISABLE TRIGGER ' + QUOTENAME(@schema_name) + '.'  
            + QUOTENAME(@trigger_name) +  
            ' ON ' + QUOTENAME(@schema_name) + '.'   
            + QUOTENAME(@object_name) + ' ; ' ;  
        EXEC (@sql) ;  
        FETCH NEXT FROM trig_cur INTO @schema_name, @trigger_name, @object_name ;  
    END  
    GO  
  
    -- Verify triggers are disabled. Should return an empty result set.  
    SELECT * FROM sys.triggers WHERE is_disabled = 0 ;  
    GO  
  
    CLOSE trig_cur ;  
    DEALLOCATE trig_cur;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ac087-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="ac087-119">See Also</span></span>  
 <span data-ttu-id="ac087-120">[CREATE TRIGGER (Transact-SQL)](/sql/t-sql/statements/create-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ac087-120">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span></span>  
 <span data-ttu-id="ac087-121">[Триггеры DML](../triggers/dml-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="ac087-121">[DML Triggers](../triggers/dml-triggers.md) </span></span>  
 [<span data-ttu-id="ac087-122">Триггеры DDL</span><span class="sxs-lookup"><span data-stu-id="ac087-122">DDL Triggers</span></span>](../triggers/ddl-triggers.md)  
  
  
