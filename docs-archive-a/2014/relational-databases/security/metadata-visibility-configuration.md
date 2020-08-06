---
title: Настройка видимости метаданных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- subcomponents visibility [SQL Server]
- metadata [SQL Server], visibility
- permissions [SQL Server], metadata access
- viewing metadata
- objects [SQL Server], metadata
- displaying metadata
- database metadata [SQL Server]
- metadata [SQL Server], permissions
ms.assetid: 50d2e015-05ae-4014-a1cd-4de7866ad651
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 5198dc4ba4e81bc1d7a8dd2411da59da81596102
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664826"
---
# <a name="metadata-visibility-configuration"></a><span data-ttu-id="c4e76-102">Настройка видимости метаданных</span><span class="sxs-lookup"><span data-stu-id="c4e76-102">Metadata Visibility Configuration</span></span>
  <span data-ttu-id="c4e76-103">Видимость метаданных ограничивается защищаемыми объектами, которыми пользователь владеет или на которые пользователю предоставлено разрешение.</span><span class="sxs-lookup"><span data-stu-id="c4e76-103">The visibility of metadata is limited to securables that a user either owns or on which the user has been granted some permission.</span></span> <span data-ttu-id="c4e76-104">Например, следующий запрос возвращает строку, если пользователю было предоставлено разрешение SELECT или INSERT на таблицу `myTable`.</span><span class="sxs-lookup"><span data-stu-id="c4e76-104">For example, the following query returns a row if the user has been granted a permission such as SELECT or INSERT on the table `myTable`.</span></span>  
  
```  
SELECT name, object_id  
FROM sys.tables  
WHERE name = 'myTable';  
GO  
```  
  
 <span data-ttu-id="c4e76-105">Однако если пользователь не имеет никаких разрешений на `myTable`, запрос возвращает пустой результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="c4e76-105">However, if the user does not have any permission on `myTable`, the query returns an empty result set.</span></span>  
  
## <a name="scope-and-impact-of-metadata-visibility-configuration"></a><span data-ttu-id="c4e76-106">Область и влияние настроек видимости метаданных</span><span class="sxs-lookup"><span data-stu-id="c4e76-106">Scope and Impact of Metadata Visibility Configuration</span></span>  
 <span data-ttu-id="c4e76-107">Настройка видимости метаданных применяется только к следующим защищаемым объектам:</span><span class="sxs-lookup"><span data-stu-id="c4e76-107">Metadata visibility configuration only applies to the following securables.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c4e76-108">Представления каталога</span><span class="sxs-lookup"><span data-stu-id="c4e76-108">Catalog views</span></span>|<span data-ttu-id="c4e76-109">Хранимые процедуры компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] **sp_help**</span><span class="sxs-lookup"><span data-stu-id="c4e76-109">[!INCLUDE[ssDE](../../includes/ssde-md.md)] **sp_help** stored procedures</span></span>|  
|<span data-ttu-id="c4e76-110">Метаданные, предоставляющие встроенные функции</span><span class="sxs-lookup"><span data-stu-id="c4e76-110">Metadata exposing built-in functions</span></span>|<span data-ttu-id="c4e76-111">Представления информационной схемы</span><span class="sxs-lookup"><span data-stu-id="c4e76-111">Information schema views</span></span>|  
|<span data-ttu-id="c4e76-112">представлений совместимости;</span><span class="sxs-lookup"><span data-stu-id="c4e76-112">Compatibility views</span></span>|<span data-ttu-id="c4e76-113">Расширенные свойства</span><span class="sxs-lookup"><span data-stu-id="c4e76-113">Extended properties</span></span>|  
  
 <span data-ttu-id="c4e76-114">Настройка видимости метаданных не применяется к следующим защищаемым объектам:</span><span class="sxs-lookup"><span data-stu-id="c4e76-114">Metadata visibility configuration does not apply to the following securables.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c4e76-115">Системные таблицы доставки журналов</span><span class="sxs-lookup"><span data-stu-id="c4e76-115">Log shipping system tables</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c4e76-116">Системные таблицы агента</span><span class="sxs-lookup"><span data-stu-id="c4e76-116">Agent system tables</span></span>|  
|<span data-ttu-id="c4e76-117">Системные таблицы плана обслуживания базы данных</span><span class="sxs-lookup"><span data-stu-id="c4e76-117">Database maintenance plan system tables</span></span>|<span data-ttu-id="c4e76-118">Системные таблицы резервных копий</span><span class="sxs-lookup"><span data-stu-id="c4e76-118">Backup system tables</span></span>|  
|<span data-ttu-id="c4e76-119">Системные таблицы репликации</span><span class="sxs-lookup"><span data-stu-id="c4e76-119">Replication system tables</span></span>|<span data-ttu-id="c4e76-120">Репликация и хранимые процедуры [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sp_help **агента**</span><span class="sxs-lookup"><span data-stu-id="c4e76-120">Replication and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent **sp_help** stored procedures</span></span>|  
  
 <span data-ttu-id="c4e76-121">Ограниченная возможность доступа к метаданным означает следующее.</span><span class="sxs-lookup"><span data-stu-id="c4e76-121">Limited metadata accessibility means the following:</span></span>  
  
-   <span data-ttu-id="c4e76-122">Приложения, предполагающие **общий** доступ к метаданным, разорвутся.</span><span class="sxs-lookup"><span data-stu-id="c4e76-122">Applications that assume **public** metadata access will break.</span></span>  
  
-   <span data-ttu-id="c4e76-123">Запросы на системные представления смогут вернуть только подмножество строк или иногда пустой результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="c4e76-123">Queries on system views might only return a subset of rows, or sometimes an empty result set.</span></span>  
  
-   <span data-ttu-id="c4e76-124">Встроенные функции по формированию метаданных, например OBJECTPROPERTYEX, могут вернуть значение NULL.</span><span class="sxs-lookup"><span data-stu-id="c4e76-124">Metadata-emitting, built-in functions such as OBJECTPROPERTYEX may return NULL.</span></span>  
  
-   <span data-ttu-id="c4e76-125">Хранимые процедуры [!INCLUDE[ssDE](../../includes/ssde-md.md)] **sp_help** могут возвращать только подмножество строк или значение NULL.</span><span class="sxs-lookup"><span data-stu-id="c4e76-125">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] **sp_help** stored procedures might return only a subset of rows, or NULL.</span></span>  
  
 <span data-ttu-id="c4e76-126">SQL модули, например хранимые процедуры и триггеры, выполняются в контексте безопасности участника и поэтому имеют ограниченный доступ к метаданным.</span><span class="sxs-lookup"><span data-stu-id="c4e76-126">SQL modules, such as stored procedures and triggers, run under the security context of the caller and, therefore, have limited metadata accessibility.</span></span> <span data-ttu-id="c4e76-127">Например, в следующем коде, когда хранимая процедура пытается получить доступ к метаданным для таблицы `myTable` , на который участник не имеет прав, возвращается пустой результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="c4e76-127">For example, in the following code, when the stored procedure tries to access metadata for the table `myTable` on which the caller has no rights, an empty result set is returned.</span></span> <span data-ttu-id="c4e76-128">В ранних версиях [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]возвращается строка.</span><span class="sxs-lookup"><span data-stu-id="c4e76-128">In earlier releases of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a row is returned.</span></span>  
  
```  
CREATE PROCEDURE assumes_caller_can_access_metadata  
BEGIN  
SELECT name, id   
FROM sysobjects   
WHERE name = 'myTable';  
END;  
GO  
```  
  
 <span data-ttu-id="c4e76-129">Чтобы позволить участникам просмотреть метаданные, можно предоставить им разрешение VIEW DEFINITION на соответствующую область: уровень объекта, уровень базы данных или уровень сервера.</span><span class="sxs-lookup"><span data-stu-id="c4e76-129">To allow callers to view metadata, you can grant the callers VIEW DEFINITION permission at an appropriate scope: object level, database level or server level.</span></span> <span data-ttu-id="c4e76-130">Таким образом, если в предыдущем примере участник имеет разрешение VIEW DEFINITION на таблицу `myTable`, хранимая процедура возвращает строку.</span><span class="sxs-lookup"><span data-stu-id="c4e76-130">Therefore, in the previous example, if the caller has VIEW DEFINITION permission on `myTable`, the stored procedure returns a row.</span></span> <span data-ttu-id="c4e76-131">Дополнительные сведения см. в статьях [GRANT (Transact-SQL)](/sql/t-sql/statements/grant-transact-sql) и [GRANT Database Permissions (Transact-SQL)](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c4e76-131">For more information, see [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) and [GRANT Database Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span></span>  
  
 <span data-ttu-id="c4e76-132">Также можно изменить хранимую процедуру таким образом, что она будет выполняться под учетными данными владельца.</span><span class="sxs-lookup"><span data-stu-id="c4e76-132">You can also modify the stored procedure so that it executes under the credentials of the owner.</span></span> <span data-ttu-id="c4e76-133">Если владелец процедуры и владелец таблицы один и тот же, применяются цепочки владения, и контекст безопасности владельца процедуры открывает доступ к метаданным таблицы `myTable`.</span><span class="sxs-lookup"><span data-stu-id="c4e76-133">When the procedure owner and the table owner are the same owner, ownership chaining applies, and the security context of the procedure owner enables access to the metadata for `myTable`.</span></span> <span data-ttu-id="c4e76-134">Под таким сценарием следующий код возвращает строку метаданных участнику.</span><span class="sxs-lookup"><span data-stu-id="c4e76-134">Under this scenario, the following code returns a row of metadata to the caller.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c4e76-135">В следующем примере использования представление каталога [sys.objects](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql) применяется вместо представления совместимости [sys.sysobjects](/sql/relational-databases/system-compatibility-views/sys-sysobjects-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="c4e76-135">The following example uses the [sys.objects](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql) catalog view instead of the [sys.sysobjects](/sql/relational-databases/system-compatibility-views/sys-sysobjects-transact-sql) compatibility view.</span></span>  
  
```  
CREATE PROCEDURE does_not_assume_caller_can_access_metadata  
WITH EXECUTE AS OWNER  
AS  
BEGIN  
SELECT name, id  
FROM sys.objects   
WHERE name = 'myTable'   
END;  
GO  
```  
  
> [!NOTE]  
>  <span data-ttu-id="c4e76-136">Можно использовать EXECUTE AS, чтобы временно переключиться на контекст безопасности участника.</span><span class="sxs-lookup"><span data-stu-id="c4e76-136">You can use EXECUTE AS to temporarily switch to the security context of the caller.</span></span> <span data-ttu-id="c4e76-137">Дополнительные сведения см. в разделе [EXECUTE AS (Transact-SQL)](/sql/t-sql/statements/execute-as-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c4e76-137">For more information, see [EXECUTE AS &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-transact-sql).</span></span>  
  
## <a name="benefits-and-limits-of-metadata-visibility-configuration"></a><span data-ttu-id="c4e76-138">Преимущества и ограничения настроек видимости метаданных</span><span class="sxs-lookup"><span data-stu-id="c4e76-138">Benefits and Limits of Metadata Visibility Configuration</span></span>  
 <span data-ttu-id="c4e76-139">Настройка видимости метаданных может играть очень важную роль в общем плане безопасности.</span><span class="sxs-lookup"><span data-stu-id="c4e76-139">Metadata visibility configuration can play an important role in your overall security plan.</span></span> <span data-ttu-id="c4e76-140">Однако иногда даже опытный пользователь может форсировать раскрытие некоторых метаданных.</span><span class="sxs-lookup"><span data-stu-id="c4e76-140">However, there are cases in which a skilled and determined user can force the disclosure of some metadata.</span></span> <span data-ttu-id="c4e76-141">Рекомендуется развертывание разрешений метаданных как одной из многих глубоко эшелонированных защит.</span><span class="sxs-lookup"><span data-stu-id="c4e76-141">We recommend that you deploy metadata permissions as one of many defenses-in-depth.</span></span>  
  
 <span data-ttu-id="c4e76-142">Теоретически возможно принудительно вызвать выброс метаданных в сообщениях об ошибках, манипулируя порядком оценки предикатов в запросах.</span><span class="sxs-lookup"><span data-stu-id="c4e76-142">It is theoretically possible to force the emission of metadata in error messages by manipulating the order of predicate evaluation in queries.</span></span> <span data-ttu-id="c4e76-143">Возможность таких *атак методом проб и ошибок* относится не только к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c4e76-143">The possibility of such *trial-and-error attacks* is not specific to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c4e76-144">Это подразумевается ассоциативными и коммуникативными преобразованиями, разрешенными в реляционной алгебре.</span><span class="sxs-lookup"><span data-stu-id="c4e76-144">It is implied by the associative and commutative transformations permitted in relational algebra.</span></span> <span data-ttu-id="c4e76-145">Можно снизить эту угрозу ограничением объема сведений, возвращаемых в сообщениях об ошибках.</span><span class="sxs-lookup"><span data-stu-id="c4e76-145">You can mitigate this risk by limiting the information returned in error messages.</span></span> <span data-ttu-id="c4e76-146">Также, чтобы ограничить видимость метаданных таким образом, можно запустить сервер с флагом трассировки 3625.</span><span class="sxs-lookup"><span data-stu-id="c4e76-146">To further restrict the visibility of metadata in this way, you can start the server with trace flag 3625.</span></span> <span data-ttu-id="c4e76-147">Этот флаг трассировки ограничивает объем сведений, отображаемых в сообщениях об ошибках.</span><span class="sxs-lookup"><span data-stu-id="c4e76-147">This trace flag limits the amount of information shown in error messages.</span></span> <span data-ttu-id="c4e76-148">В свою очередь, это помогает предотвратить форсированное раскрытие.</span><span class="sxs-lookup"><span data-stu-id="c4e76-148">In turn, this helps to prevent forced disclosures.</span></span> <span data-ttu-id="c4e76-149">Компромисс заключается в том, что сообщения об ошибках будут в сжатом виде и могут вызвать сложности при использовании для отладки.</span><span class="sxs-lookup"><span data-stu-id="c4e76-149">The tradeoff is that error messages will be terse and might be difficult to use for debugging purposes.</span></span> <span data-ttu-id="c4e76-150">Дополнительные сведения см. в разделах [Параметры запуска службы Database Engine](../../database-engine/configure-windows/database-engine-service-startup-options.md) и [Флаги трассировки (Transact-SQL)](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c4e76-150">For more information, see [Database Engine Service Startup Options](../../database-engine/configure-windows/database-engine-service-startup-options.md) and [Trace Flags &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span></span>  
  
 <span data-ttu-id="c4e76-151">Следующие метаданные не подвергаются форсированному раскрытию.</span><span class="sxs-lookup"><span data-stu-id="c4e76-151">The following metadata is not subject to forced disclosure:</span></span>  
  
-   <span data-ttu-id="c4e76-152">Значение, хранимое в столбце **provider_string** объекта **sys.servers**.</span><span class="sxs-lookup"><span data-stu-id="c4e76-152">The value stored in the **provider_string** column of **sys.servers**.</span></span> <span data-ttu-id="c4e76-153">Пользователь, не имеющий разрешения ALTER ANY LINKED SERVER, в данном столбце получит значение NULL.</span><span class="sxs-lookup"><span data-stu-id="c4e76-153">A user that does not have ALTER ANY LINKED SERVER permission will see a NULL value in this column.</span></span>  
  
-   <span data-ttu-id="c4e76-154">Определение источника пользовательского объекта, например хранимой процедуры или триггера.</span><span class="sxs-lookup"><span data-stu-id="c4e76-154">Source definition of a user-defined object such as a stored procedure or trigger.</span></span> <span data-ttu-id="c4e76-155">Код источника видим только в том случае, когда выполняется одно из следующих условий.</span><span class="sxs-lookup"><span data-stu-id="c4e76-155">The source code is visible only when one of the following is true:</span></span>  
  
    -   <span data-ttu-id="c4e76-156">Пользователь имеет разрешение VIEW DEFINITION на объект.</span><span class="sxs-lookup"><span data-stu-id="c4e76-156">The user has VIEW DEFINITION permission on the object.</span></span>  
  
    -   <span data-ttu-id="c4e76-157">Пользователю не было запрещено получение разрешения VIEW DEFINITION на объект и он имеет разрешения CONTROL, ALTER или TAKE OWNERSHIP.</span><span class="sxs-lookup"><span data-stu-id="c4e76-157">The user has not been denied VIEW DEFINITION permission on the object and has CONTROL, ALTER, or TAKE OWNERSHIP permission on the object.</span></span> <span data-ttu-id="c4e76-158">Все остальные пользователи получат значение NULL.</span><span class="sxs-lookup"><span data-stu-id="c4e76-158">All other users will see NULL.</span></span>  
  
-   <span data-ttu-id="c4e76-159">Столбцы определений, найденные в следующих представлениях каталога:</span><span class="sxs-lookup"><span data-stu-id="c4e76-159">The definition columns found in the following catalog views:</span></span>  
  
    |||  
    |-|-|  
    |<span data-ttu-id="c4e76-160">**sys.all_sql_modules**</span><span class="sxs-lookup"><span data-stu-id="c4e76-160">**sys.all_sql_modules**</span></span>|<span data-ttu-id="c4e76-161">**sys.sql_modules**</span><span class="sxs-lookup"><span data-stu-id="c4e76-161">**sys.sql_modules**</span></span>|  
    |<span data-ttu-id="c4e76-162">**sys.server_sql_modules**</span><span class="sxs-lookup"><span data-stu-id="c4e76-162">**sys.server_sql_modules**</span></span>|<span data-ttu-id="c4e76-163">**sys.check_constraints**</span><span class="sxs-lookup"><span data-stu-id="c4e76-163">**sys.check_constraints**</span></span>|  
    |<span data-ttu-id="c4e76-164">**sys.default_constraints**</span><span class="sxs-lookup"><span data-stu-id="c4e76-164">**sys.default_constraints**</span></span>|<span data-ttu-id="c4e76-165">**sys.computed_columns**</span><span class="sxs-lookup"><span data-stu-id="c4e76-165">**sys.computed_columns**</span></span>|  
    |<span data-ttu-id="c4e76-166">**sys.numbered_procedures**</span><span class="sxs-lookup"><span data-stu-id="c4e76-166">**sys.numbered_procedures**</span></span>||  
  
-   <span data-ttu-id="c4e76-167">Столбец **ctext** в представлении совместимости **syscomments** .</span><span class="sxs-lookup"><span data-stu-id="c4e76-167">The **ctext** column in the **syscomments** compatibility view.</span></span>  
  
-   <span data-ttu-id="c4e76-168">Выходные данные процедуры **sp_helptext** .</span><span class="sxs-lookup"><span data-stu-id="c4e76-168">The output of the **sp_helptext** procedure.</span></span>  
  
-   <span data-ttu-id="c4e76-169">Следующие столбцы в представлениях информационной схемы:</span><span class="sxs-lookup"><span data-stu-id="c4e76-169">The following columns in the information schema views:</span></span>  
  
    |||  
    |-|-|  
    |<span data-ttu-id="c4e76-170">INFORMATION_SCHEMA.CHECK_CONSTRAINTS.CHECK_CLAUSE</span><span class="sxs-lookup"><span data-stu-id="c4e76-170">INFORMATION_SCHEMA.CHECK_CONSTRAINTS.CHECK_CLAUSE</span></span>|<span data-ttu-id="c4e76-171">INFORMATION_SCHEMA.COLUMNS.COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="c4e76-171">INFORMATION_SCHEMA.COLUMNS.COLUMN_DEFAULT</span></span>|  
    |<span data-ttu-id="c4e76-172">INFORMATION_SCHEMA.DOMAINS.DOMAIN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="c4e76-172">INFORMATION_SCHEMA.DOMAINS.DOMAIN_DEFAULT</span></span>|<span data-ttu-id="c4e76-173">INFORMATION_SCHEMA.ROUTINE_COLUMNS.COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="c4e76-173">INFORMATION_SCHEMA.ROUTINE_COLUMNS.COLUMN_DEFAULT</span></span>|  
    |<span data-ttu-id="c4e76-174">INFORMATION_SCHEMA.ROUTINES.ROUTINE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="c4e76-174">INFORMATION_SCHEMA.ROUTINES.ROUTINE_DEFINITION</span></span>|<span data-ttu-id="c4e76-175">INFORMATION_SCHEMA.VIEWS.VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="c4e76-175">INFORMATION_SCHEMA.VIEWS.VIEW_DEFINITION</span></span>|  
  
-   <span data-ttu-id="c4e76-176">Функция OBJECT_DEFINITION().</span><span class="sxs-lookup"><span data-stu-id="c4e76-176">OBJECT_DEFINITION() function</span></span>  
  
-   <span data-ttu-id="c4e76-177">Значение, хранимое в столбце password_hash объекта **sys.sql_logins**.</span><span class="sxs-lookup"><span data-stu-id="c4e76-177">The value stored in the password_hash column of **sys.sql_logins**.</span></span>  <span data-ttu-id="c4e76-178">Пользователь, не имеющий разрешения CONTROL SERVER, в данном столбце получит значение NULL.</span><span class="sxs-lookup"><span data-stu-id="c4e76-178">A user that does not have CONTROL SERVER permission will see a NULL value in this column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c4e76-179">Определения SQL встроенных системных процедур и функций видимы для всех пользователей через представление каталога **sys.system_sql_modules** , хранимую процедуру **sp_helptext** и функцию OBJECT_DEFINITION().</span><span class="sxs-lookup"><span data-stu-id="c4e76-179">The SQL definitions of built-in system procedures and functions are publicly visible through the **sys.system_sql_modules** catalog view, the **sp_helptext** stored procedure, and the OBJECT_DEFINITION() function.</span></span>  
  
## <a name="general-principles-of-metadata-visibility"></a><span data-ttu-id="c4e76-180">Общие принципы видимости метаданных</span><span class="sxs-lookup"><span data-stu-id="c4e76-180">General Principles of Metadata Visibility</span></span>  
 <span data-ttu-id="c4e76-181">Ниже представлены некоторые общие принципы, относящиеся к видимости метаданных.</span><span class="sxs-lookup"><span data-stu-id="c4e76-181">The following are some general principles to consider regarding metadata visibility:</span></span>  
  
-   <span data-ttu-id="c4e76-182">Неявные разрешения предопределенных ролей.</span><span class="sxs-lookup"><span data-stu-id="c4e76-182">Fixed roles implicit permissions</span></span>  
  
-   <span data-ttu-id="c4e76-183">Область разрешений.</span><span class="sxs-lookup"><span data-stu-id="c4e76-183">Scope of permissions</span></span>  
  
-   <span data-ttu-id="c4e76-184">Приоритет инструкции DENY</span><span class="sxs-lookup"><span data-stu-id="c4e76-184">Precedence of DENY</span></span>  
  
-   <span data-ttu-id="c4e76-185">Видимость метаданных вспомогательных компонентов.</span><span class="sxs-lookup"><span data-stu-id="c4e76-185">Visibility of subcomponent metadata</span></span>  
  
### <a name="fixed-roles-and-implicit-permissions"></a><span data-ttu-id="c4e76-186">Предопределенные роли и неявные разрешения</span><span class="sxs-lookup"><span data-stu-id="c4e76-186">Fixed Roles and Implicit Permissions</span></span>  
 <span data-ttu-id="c4e76-187">Доступ предопределенных ролей к метаданным зависит от соответствующих неявных разрешений.</span><span class="sxs-lookup"><span data-stu-id="c4e76-187">Metadata that can be accessed by fixed roles depends upon their corresponding implicit permissions.</span></span>  
  
### <a name="scope-of-permissions"></a><span data-ttu-id="c4e76-188">Область разрешений.</span><span class="sxs-lookup"><span data-stu-id="c4e76-188">Scope of Permissions</span></span>  
 <span data-ttu-id="c4e76-189">Разрешения на одну область дают возможность видеть метаданные в этой области и на всех включенных областях.</span><span class="sxs-lookup"><span data-stu-id="c4e76-189">Permissions at one scope imply the ability to see metadata at that scope and at all enclosed scopes.</span></span> <span data-ttu-id="c4e76-190">Например, разрешение SELECT на схему предполагает, что участник разрешения имеет разрешение SELECT на все защищаемые объекты, содержащиеся в этой схеме.</span><span class="sxs-lookup"><span data-stu-id="c4e76-190">For example, SELECT permission on a schema implies that the grantee has SELECT permission on all securables that are contained by that schema.</span></span> <span data-ttu-id="c4e76-191">Таким образом, предоставление разрешения SELECT на схему позволяет пользователю видеть метаданные схемы, а также все находящиеся в ней таблицы, представления, функции, процедуры, очереди, синонимы, типы и коллекции XML-схем.</span><span class="sxs-lookup"><span data-stu-id="c4e76-191">The granting of SELECT permission on a schema therefore enables a user to see the metadata of the schema and also all tables, views, functions, procedures, queues, synonyms, types, and XML schema collections within it.</span></span> <span data-ttu-id="c4e76-192">Дополнительные сведения об областях см. в разделе [Иерархия разрешений (компонент Database Engine)](permissions-hierarchy-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="c4e76-192">For more information about scopes, see [Permissions Hierarchy &#40;Database Engine&#41;](permissions-hierarchy-database-engine.md).</span></span>  
  
### <a name="precedence-of-deny"></a><span data-ttu-id="c4e76-193">Приоритет инструкции DENY</span><span class="sxs-lookup"><span data-stu-id="c4e76-193">Precedence of DENY</span></span>  
 <span data-ttu-id="c4e76-194">Инструкция DENY обычно является приоритетной по отношению к другим разрешениям.</span><span class="sxs-lookup"><span data-stu-id="c4e76-194">DENY typically takes precedence over other permissions.</span></span> <span data-ttu-id="c4e76-195">Например, если пользователю базы данных на схему было предоставлено разрешение EXECUTE, но это разрешение было запрещено на хранимую процедуру схемы, он не сможет просмотреть метаданные для этой хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="c4e76-195">For example, if a database user is granted EXECUTE permission on a schema but has been denied EXECUTE permission on a stored procedure in that schema, the user cannot view the metadata for that stored procedure.</span></span>  
  
 <span data-ttu-id="c4e76-196">К тому же, если пользователю было запрещено разрешение EXECUTE на схему, но была предоставлена инструкция EXECUTE на хранимую процедуру данной схемы, он также не сможет просмотреть метаданные для этой хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="c4e76-196">Additionally, if a user is denied EXECUTE permission on a schema but has been granted EXECUTE permission on a stored procedure in that schema, the user cannot view the metadata for that stored procedure.</span></span>  
  
 <span data-ttu-id="c4e76-197">Другой пример: если пользователю разрешение EXECUTE на хранимую процедуру было и предоставлено, и запрещено, что возможно благодаря членству в различных ролях, то преимущество имеет инструкция DENY, и пользователь не сможет просмотреть метаданные хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="c4e76-197">For another example, if a user has been granted and denied EXECUTE permission on a stored procedure, which is possible through your various role memberships, DENY takes precedence and the user cannot view the metadata of the stored procedure.</span></span>  
  
### <a name="visibility-of-subcomponent-metadata"></a><span data-ttu-id="c4e76-198">Видимость метаданных вспомогательных компонентов.</span><span class="sxs-lookup"><span data-stu-id="c4e76-198">Visibility of Subcomponent Metadata</span></span>  
 <span data-ttu-id="c4e76-199">Видимость вспомогательных компонентов, таких как индексы, проверочные ограничения и триггеры, определяется разрешениями на родительский объект.</span><span class="sxs-lookup"><span data-stu-id="c4e76-199">The visibility of subcomponents, such as indexes, check constraints, and triggers is determined by permissions on the parent.</span></span> <span data-ttu-id="c4e76-200">Эти вспомогательные компоненты не имеют предоставляемых разрешений.</span><span class="sxs-lookup"><span data-stu-id="c4e76-200">These subcomponents do not have grantable permissions.</span></span> <span data-ttu-id="c4e76-201">Например, если пользователю предоставлено какое-то разрешение на таблицу, он может просмотреть метаданные для столбцов таблицы, индексов, проверочных ограничений, триггеров и других подобных вспомогательных компонентов.</span><span class="sxs-lookup"><span data-stu-id="c4e76-201">For example, if a user has been granted some permission on a table, the user can view the metadata for the tables, columns, indexes, check constraints, triggers, and other such subcomponents.</span></span>  
  
#### <a name="metadata-that-is-accessible-to-all-database-users"></a><span data-ttu-id="c4e76-202">Метаданные, доступные для всех пользователей базы данных</span><span class="sxs-lookup"><span data-stu-id="c4e76-202">Metadata That Is Accessible to All Database Users</span></span>  
 <span data-ttu-id="c4e76-203">Некоторые метаданные должны быть доступны для всех пользователей в указанной базе данных.</span><span class="sxs-lookup"><span data-stu-id="c4e76-203">Some metadata must be accessible to all users in a specific database.</span></span> <span data-ttu-id="c4e76-204">Например, файловые группы не имеют присвоенных разрешений; поэтому пользователю не может быть предоставлено разрешение на просмотр метаданных файловой группы.</span><span class="sxs-lookup"><span data-stu-id="c4e76-204">For example, filegroups do not have conferrable permissions; therefore, a user cannot be granted permission to view the metadata of a filegroup.</span></span> <span data-ttu-id="c4e76-205">Однако любой пользователь, который может создать таблицу, должен иметь доступ к метаданным файловой группы, чтобы использовать предложения ON *filegroup* или TEXTIMAGE_ON *filegroup* инструкции CREATE TABLE.</span><span class="sxs-lookup"><span data-stu-id="c4e76-205">However, any user that can create a table must be able to access filegroup metadata to use the ON *filegroup* or TEXTIMAGE_ON *filegroup* clauses of the CREATE TABLE statement.</span></span>  
  
 <span data-ttu-id="c4e76-206">Метаданные, возвращаемые функциями DB_ID() и DB_NAME(), видимы всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="c4e76-206">The metadata that is returned by the DB_ID() and DB_NAME() functions is visible to all users.</span></span>  
  
 <span data-ttu-id="c4e76-207">В следующей таблице приведены представления каталога, видимые для **общей** роли.</span><span class="sxs-lookup"><span data-stu-id="c4e76-207">The following table lists the catalog views that are visible to the **public** role.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c4e76-208">**sys.partition_functions**</span><span class="sxs-lookup"><span data-stu-id="c4e76-208">**sys.partition_functions**</span></span>|<span data-ttu-id="c4e76-209">**sys.partition_range_values**</span><span class="sxs-lookup"><span data-stu-id="c4e76-209">**sys.partition_range_values**</span></span>|  
|<span data-ttu-id="c4e76-210">**sys.partition_schemes**</span><span class="sxs-lookup"><span data-stu-id="c4e76-210">**sys.partition_schemes**</span></span>|<span data-ttu-id="c4e76-211">**sys.data_spaces**</span><span class="sxs-lookup"><span data-stu-id="c4e76-211">**sys.data_spaces**</span></span>|  
|<span data-ttu-id="c4e76-212">**sys.filegroups**</span><span class="sxs-lookup"><span data-stu-id="c4e76-212">**sys.filegroups**</span></span>|<span data-ttu-id="c4e76-213">**sys.destination_data_spaces**</span><span class="sxs-lookup"><span data-stu-id="c4e76-213">**sys.destination_data_spaces**</span></span>|  
|<span data-ttu-id="c4e76-214">**sys.database_files**</span><span class="sxs-lookup"><span data-stu-id="c4e76-214">**sys.database_files**</span></span>|<span data-ttu-id="c4e76-215">**sys.allocation_units**</span><span class="sxs-lookup"><span data-stu-id="c4e76-215">**sys.allocation_units**</span></span>|  
|<span data-ttu-id="c4e76-216">**sys.partitions**</span><span class="sxs-lookup"><span data-stu-id="c4e76-216">**sys.partitions**</span></span>|<span data-ttu-id="c4e76-217">**sys.messages**</span><span class="sxs-lookup"><span data-stu-id="c4e76-217">**sys.messages**</span></span>|  
|<span data-ttu-id="c4e76-218">**sys.schemas**</span><span class="sxs-lookup"><span data-stu-id="c4e76-218">**sys.schemas**</span></span>|<span data-ttu-id="c4e76-219">**sys.configurations**</span><span class="sxs-lookup"><span data-stu-id="c4e76-219">**sys.configurations**</span></span>|  
|<span data-ttu-id="c4e76-220">**sys.sql_dependencies**</span><span class="sxs-lookup"><span data-stu-id="c4e76-220">**sys.sql_dependencies**</span></span>|<span data-ttu-id="c4e76-221">**sys.type_assembly_usages**</span><span class="sxs-lookup"><span data-stu-id="c4e76-221">**sys.type_assembly_usages**</span></span>|  
|<span data-ttu-id="c4e76-222">**sys.parameter_type_usages**</span><span class="sxs-lookup"><span data-stu-id="c4e76-222">**sys.parameter_type_usages**</span></span>|<span data-ttu-id="c4e76-223">**sys.column_type_usages**</span><span class="sxs-lookup"><span data-stu-id="c4e76-223">**sys.column_type_usages**</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c4e76-224">См. также:</span><span class="sxs-lookup"><span data-stu-id="c4e76-224">See Also</span></span>  
 <span data-ttu-id="c4e76-225">[GRANT (Transact-SQL)](/sql/t-sql/statements/grant-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c4e76-225">[GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) </span></span>  
 <span data-ttu-id="c4e76-226">[DENY (Transact-SQL)](/sql/t-sql/statements/deny-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c4e76-226">[DENY &#40;Transact-SQL&#41;](/sql/t-sql/statements/deny-transact-sql) </span></span>  
 <span data-ttu-id="c4e76-227">[REVOKE (Transact-SQL)](/sql/t-sql/statements/revoke-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c4e76-227">[REVOKE &#40;Transact-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql) </span></span>  
 <span data-ttu-id="c4e76-228">[Предложение EXECUTE AS (Transact-SQL)](/sql/t-sql/statements/execute-as-clause-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c4e76-228">[EXECUTE AS Clause &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-clause-transact-sql) </span></span>  
 <span data-ttu-id="c4e76-229">[Представления каталога (Transact-SQL)](/sql/relational-databases/system-catalog-views/catalog-views-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c4e76-229">[Catalog Views &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/catalog-views-transact-sql) </span></span>  
 [<span data-ttu-id="c4e76-230">Представления совместимости (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c4e76-230">Compatibility Views &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-compatibility-views/system-compatibility-views-transact-sql)  
  
  
