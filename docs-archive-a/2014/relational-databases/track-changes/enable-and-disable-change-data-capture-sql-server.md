---
title: Включение и отключение отслеживания измененных данных (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- change data capture [SQL Server], enabling tables
- change data capture [SQL Server], enabling databases
- change data capture [SQL Server], disabling databases
- change data capture [SQL Server], disabling tables
ms.assetid: b741894f-d267-4b10-adfe-cbc14aa6caeb
author: rothja
ms.author: jroth
ms.openlocfilehash: df0a2fd4a2c6ffb2de58d6b52360d1730d0fa7df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664081"
---
# <a name="enable-and-disable-change-data-capture-sql-server"></a><span data-ttu-id="2878b-102">Включение и отключение отслеживания измененных данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2878b-102">Enable and Disable Change Data Capture (SQL Server)</span></span>
  <span data-ttu-id="2878b-103">В этом разделе описано, как включить или отключить систему отслеживания измененных данных для базы данных и таблицы.</span><span class="sxs-lookup"><span data-stu-id="2878b-103">This topic describes how to enable and disable change data capture for a database and a table.</span></span>  
  
## <a name="enable-change-data-capture-for-a-database"></a><span data-ttu-id="2878b-104">Включение системы отслеживания измененных данных для базы данных</span><span class="sxs-lookup"><span data-stu-id="2878b-104">Enable Change Data Capture for a Database</span></span>  
 <span data-ttu-id="2878b-105">Прежде чем можно будет создавать экземпляры отслеживания для отдельных таблиц, член предопределенной роли сервера `sysadmin` должен включить отслеживание измененных данных для базы данных.</span><span class="sxs-lookup"><span data-stu-id="2878b-105">Before a capture instance can be created for individual tables, a member of the `sysadmin` fixed server role must first enable the database for change data capture.</span></span> <span data-ttu-id="2878b-106">Это выполняется запуском хранимой процедуры [sys.sp_cdc_enable_db (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sys-sp-cdc-enable-db-transact-sql) в контексте базы данных.</span><span class="sxs-lookup"><span data-stu-id="2878b-106">This is done by running the stored procedure [sys.sp_cdc_enable_db &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-cdc-enable-db-transact-sql) in the database context.</span></span> <span data-ttu-id="2878b-107">Определить, включено ли отслеживание для базы данных, можно путем выполнения запроса к столбцу `is_cdc_enabled` в представлении каталога `sys.databases`.</span><span class="sxs-lookup"><span data-stu-id="2878b-107">To determine if a database is already enabled, query the `is_cdc_enabled` column in the `sys.databases` catalog view.</span></span>  
  
 <span data-ttu-id="2878b-108">Когда для базы данных включается отслеживание измененных данных, для нее создаются: схема `cdc`, пользователь `cdc`, таблицы метаданных и другие системные объекты.</span><span class="sxs-lookup"><span data-stu-id="2878b-108">When a database is enabled for change data capture, the `cdc` schema, `cdc` user, metadata tables, and other system objects are created for the database.</span></span> <span data-ttu-id="2878b-109">Схема `cdc` содержит таблицы метаданных для системы отслеживания измененных данных; после того как для исходных таблиц будет включено отслеживание измененных данных, в этой схеме также будут храниться отдельные таблицы изменений, служащие репозиторием информации об изменениях.</span><span class="sxs-lookup"><span data-stu-id="2878b-109">The `cdc` schema contains the change data capture metadata tables and, after source tables are enabled for change data capture, the individual change tables serve as a repository for change data.</span></span> <span data-ttu-id="2878b-110">Схема `cdc` также содержит связанные системные функции, используемые для выполнения запросов для получения информации об изменениях.</span><span class="sxs-lookup"><span data-stu-id="2878b-110">The `cdc` schema also contains associated system functions used to query for change data.</span></span>  
  
 <span data-ttu-id="2878b-111">Система отслеживания измененных данных требует монопольного использования схемы `cdc` и пользователя `cdc`.</span><span class="sxs-lookup"><span data-stu-id="2878b-111">Change data capture requires exclusive use of the `cdc` schema and `cdc` user.</span></span> <span data-ttu-id="2878b-112">Если в базе данных уже существует схема или пользователь с именем *cdc* , то базу данных нельзя будет включить для отслеживания измененных данных, пока эта схема или пользователь не будут удалены или переименованы.</span><span class="sxs-lookup"><span data-stu-id="2878b-112">If either a schema or a database user named *cdc* currently exists in a database, the database cannot be enabled for change data capture until the schema and or user are dropped or renamed.</span></span>  
  
 <span data-ttu-id="2878b-113">Примером включения базы данных является шаблон включения отслеживания измененных данных в базе данных.</span><span class="sxs-lookup"><span data-stu-id="2878b-113">See the Enable Database for Change Data Capture template for an example of enabling a database.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2878b-114">Найти шаблоны в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]можно, открыв меню **Вид**, щелкнув пункт **Обозреватель шаблонов**, а затем выбрав **Шаблоны SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="2878b-114">To locate the templates in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], go to **View**, click **Template Explorer**, and then select **SQL Server Templates**.</span></span> <span data-ttu-id="2878b-115">**Система отслеживания измененных данных** — это вложенная папка.</span><span class="sxs-lookup"><span data-stu-id="2878b-115">**Change Data Capture** is a sub-folder.</span></span> <span data-ttu-id="2878b-116">В этой папке можно найти все шаблоны, упоминаемые в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="2878b-116">Under this folder, you will find all the templates referenced in this topic.</span></span> <span data-ttu-id="2878b-117">Значок **Обозреватель шаблонов** также присутствует на панели инструментов среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2878b-117">There is also a **Template Explorer** icon on the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] toolbar.</span></span>  
  
```sql  
-- ====  
-- Enable Database for CDC template   
-- ====  
USE MyDB  
GO  
EXEC sys.sp_cdc_enable_db  
GO  
```  
  
## <a name="disable-change-data-capture-for-a-database"></a><span data-ttu-id="2878b-118">Отключение системы отслеживания измененных данных для базы данных</span><span class="sxs-lookup"><span data-stu-id="2878b-118">Disable Change Data Capture for a Database</span></span>  
 <span data-ttu-id="2878b-119">Член `sysadmin` предопределенной роли сервера может выполнить хранимую процедуру [sys. Sp_cdc_disable_db &#40;TRANSACT-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-cdc-disable-db-transact-sql) в контексте базы данных, чтобы отключить систему отслеживания измененных данных для базы данных.</span><span class="sxs-lookup"><span data-stu-id="2878b-119">A member of the `sysadmin` fixed server role can run the stored procedure [sys.sp_cdc_disable_db &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-cdc-disable-db-transact-sql) in the database context to disable change data capture for a database.</span></span> <span data-ttu-id="2878b-120">Нет необходимости отключать отдельные таблицы, прежде чем будет выполнено отключение базы данных.</span><span class="sxs-lookup"><span data-stu-id="2878b-120">It is not necessary to disable individual tables before you disable the database.</span></span> <span data-ttu-id="2878b-121">Отключение базы данных приводит к удалению всех соответствующих метаданных системы отслеживания измененных данных, включая пользователя `cdc` и схему, а также задания отслеживания измененных данных.</span><span class="sxs-lookup"><span data-stu-id="2878b-121">Disabling the database removes all associated change data capture metadata, including the `cdc` user and schema and the change data capture jobs.</span></span> <span data-ttu-id="2878b-122">Но любые шлюзовые роли, созданные системой отслеживания измененных данных, не будут удалены автоматически, поэтому необходимо выполнить их явное удаление.</span><span class="sxs-lookup"><span data-stu-id="2878b-122">However, any gating roles created by change data capture will not be removed automatically and must be explicitly deleted.</span></span> <span data-ttu-id="2878b-123">Чтобы определить, включена ли база данных, выполните запрос к столбцу `is_cdc_enabled` в представлении каталога sys.databases.</span><span class="sxs-lookup"><span data-stu-id="2878b-123">To determine if a database is enabled, query the `is_cdc_enabled` column in the sys.databases catalog view.</span></span>  
  
 <span data-ttu-id="2878b-124">После удаления базы данных, в которой включена система отслеживания измененных данных, автоматически удаляются задания отслеживания измененных данных.</span><span class="sxs-lookup"><span data-stu-id="2878b-124">If a change data capture enabled database is dropped, change data capture jobs are automatically removed.</span></span>  
  
 <span data-ttu-id="2878b-125">Пример отключения базы данных см. в шаблоне отключения системы отслеживания измененных данных в базе данных».</span><span class="sxs-lookup"><span data-stu-id="2878b-125">See the Disable Database for Change Data Capture template for an example of disabling a database.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2878b-126">Чтобы найти шаблоны в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], перейдите к элементу **Просмотр**, нажмите кнопку **Обозреватель шаблонов**, а затем нажмите кнопку **Шаблоны SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="2878b-126">To locate the templates in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], go to **View**, click **Template Explorer**, and then click **SQL Server Templates**.</span></span> <span data-ttu-id="2878b-127">**Система отслеживания измененных данных** — это подпапка, в которой можно найти все шаблоны, упомянутые в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="2878b-127">**Change Data Capture** is a sub-folder where you will find all the templates that are referenced in this topic.</span></span> <span data-ttu-id="2878b-128">Значок **Обозреватель шаблонов** также присутствует на панели инструментов среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2878b-128">There is also a **Template Explorer** icon on the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] toolbar.</span></span>  
  
```sql  
-- =======  
-- Disable Database for Change Data Capture template   
-- =======  
USE MyDB  
GO  
EXEC sys.sp_cdc_disable_db  
GO  
```  
  
## <a name="enable-change-data-capture-for-a-table"></a><span data-ttu-id="2878b-129">Включение отслеживания измененных данных для таблицы</span><span class="sxs-lookup"><span data-stu-id="2878b-129">Enable Change Data Capture for a Table</span></span>  
 <span data-ttu-id="2878b-130">После того как для базы данных было включено отслеживание измененных данных, члены предопределенной роли базы данных `db_owner` могут создавать экземпляры системы отслеживания для отдельных исходных таблиц, используя хранимую процедуру `sys.sp_cdc_enable_table`.</span><span class="sxs-lookup"><span data-stu-id="2878b-130">After a database has been enabled for change data capture, members of the `db_owner` fixed database role can create a capture instance for individual source tables by using the stored procedure `sys.sp_cdc_enable_table`.</span></span> <span data-ttu-id="2878b-131">Чтобы определить, была ли включена исходная таблица для отслеживания измененных данных, запросите значение столбца is_tracked_by_cdc в представлении каталога `sys.tables`.</span><span class="sxs-lookup"><span data-stu-id="2878b-131">To determine whether a source table has already been enabled for change data capture, examine the is_tracked_by_cdc column in the `sys.tables` catalog view.</span></span>  
  
 <span data-ttu-id="2878b-132">При создании экземпляра отслеживания можно указать следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="2878b-132">The following options can be specified when creating a capture instance:</span></span>  
  
 <span data-ttu-id="2878b-133">`Columns in the source table to be captured`.</span><span class="sxs-lookup"><span data-stu-id="2878b-133">`Columns in the source table to be captured`.</span></span>  
  
 <span data-ttu-id="2878b-134">По умолчанию все столбцы исходной таблицы определяются как отслеживаемые.</span><span class="sxs-lookup"><span data-stu-id="2878b-134">By default, all of the columns in the source table are identified as captured columns.</span></span> <span data-ttu-id="2878b-135">Если необходимо отслеживание только подмножества столбцов, например для обеспечения конфиденциальности или повышения производительности, используйте *@captured_column_list* параметр, чтобы указать подмножество столбцов.</span><span class="sxs-lookup"><span data-stu-id="2878b-135">If only a subset of columns need to be tracked, such as for privacy or performance reasons, use the *@captured_column_list* parameter to specify the subset of columns.</span></span>  
  
 `A filegroup to contain the change table.`  
  
 <span data-ttu-id="2878b-136">По умолчанию таблица изменений расположена в файловой группе по умолчанию для базы данных.</span><span class="sxs-lookup"><span data-stu-id="2878b-136">By default, the change table is located in the default filegroup of the database.</span></span> <span data-ttu-id="2878b-137">Владельцы баз данных, которым требуется управлять размещением отдельных таблиц изменений, могут использовать *@filegroup_name* параметр, чтобы указать определенную файловую группу для таблицы изменений, связанной с экземпляром отслеживания.</span><span class="sxs-lookup"><span data-stu-id="2878b-137">Database owners who want to control the placement of individual change tables can use the *@filegroup_name* parameter to specify a particular filegroup for the change table associated with the capture instance.</span></span> <span data-ttu-id="2878b-138">Именованная файловая группа уже должна существовать.</span><span class="sxs-lookup"><span data-stu-id="2878b-138">The named filegroup must already exist.</span></span> <span data-ttu-id="2878b-139">Обычно рекомендуется, чтобы таблицы изменений располагались не в той файловой группе, где содержатся исходные таблицы.</span><span class="sxs-lookup"><span data-stu-id="2878b-139">Generally, it is recommended that change tables be placed in a filegroup separate from source tables.</span></span> <span data-ttu-id="2878b-140">`Enable a Table Specifying Filegroup Option`Пример использования параметра см. в шаблоне *@filegroup_name* .</span><span class="sxs-lookup"><span data-stu-id="2878b-140">See the `Enable a Table Specifying Filegroup Option` template for an example showing use of the *@filegroup_name* parameter.</span></span>  
  
```sql  
-- =========  
-- Enable a Table Specifying Filegroup Option Template  
-- =========  
USE MyDB  
GO  
  
EXEC sys.sp_cdc_enable_table  
@source_schema = N'dbo',  
@source_name   = N'MyTable',  
@role_name     = N'MyRole',  
@filegroup_name = N'MyDB_CT',  
@supports_net_changes = 1  
GO  
```  
  
 `A role for controlling access to a change table.`  
  
 <span data-ttu-id="2878b-141">Именованные роли используются для управления доступом к информации об изменениях.</span><span class="sxs-lookup"><span data-stu-id="2878b-141">The purpose of the named role is to control access to the change data.</span></span> <span data-ttu-id="2878b-142">Указана может быть существующая предопределенная роль сервера или роль базы данных.</span><span class="sxs-lookup"><span data-stu-id="2878b-142">The specified role can be an existing fixed server role or a database role.</span></span> <span data-ttu-id="2878b-143">Если указанной роли не существует, то роль базы данных с таким именем будет создана автоматически.</span><span class="sxs-lookup"><span data-stu-id="2878b-143">If the specified role does not already exist, a database role of that name is created automatically.</span></span> <span data-ttu-id="2878b-144">Члены ролей `sysadmin` и `db_owner` имеют полный доступ к данным в таблицах изменений.</span><span class="sxs-lookup"><span data-stu-id="2878b-144">Members of either the `sysadmin` or `db_owner` role have full access to the data in the change tables.</span></span> <span data-ttu-id="2878b-145">Все другие пользователи должны иметь разрешение SELECT на все отслеживаемые столбцы исходной таблицы.</span><span class="sxs-lookup"><span data-stu-id="2878b-145">All other users must have SELECT permission on all the captured columns of the source table.</span></span> <span data-ttu-id="2878b-146">Кроме того, если указана роль, то пользователи, не являющиеся членами ролей `sysadmin` и `db_owner`, также должны быть участниками указанной роли.</span><span class="sxs-lookup"><span data-stu-id="2878b-146">In addition, when a role is specified, users who are not members of either the `sysadmin` or `db_owner` role must also be members of the specified role.</span></span>  
  
 <span data-ttu-id="2878b-147">Если вы не хотите использовать роль ограничения, явно присвойте *@role_name* параметру значение null.</span><span class="sxs-lookup"><span data-stu-id="2878b-147">If you do not want to use a gating role, explicitly set the *@role_name* parameter to NULL.</span></span> <span data-ttu-id="2878b-148">Пример включения таблицы без шлюзовой роли см. в шаблоне `Enable a Table Without Using a Gating Role`.</span><span class="sxs-lookup"><span data-stu-id="2878b-148">See the `Enable a Table Without Using a Gating Role` template for an example of enabling a table without a gating role.</span></span>  
  
```sql  
-- =========  
-- Enable a Table Without Using a Gating Role template   
-- =========  
USE MyDB  
GO  
EXEC sys.sp_cdc_enable_table  
@source_schema = N'dbo',  
@source_name   = N'MyTable',  
@role_name     = NULL,  
@supports_net_changes = 1  
GO  
  
```  
  
 `A function to query for net changes.`  
  
 <span data-ttu-id="2878b-149">В экземпляр системы отслеживания всегда будет включена возвращающая табличное значение функция, используемая для возвращения всех записей таблицы изменений, произошедших в течение определенного интервала.</span><span class="sxs-lookup"><span data-stu-id="2878b-149">A capture instance will always include a table valued function for returning all change table entries that occurred within a defined interval.</span></span> <span data-ttu-id="2878b-150">Имя этой функции образуется путем добавления имени экземпляра отслеживания к строке «cdc.fn_cdc_get_all_changes_».</span><span class="sxs-lookup"><span data-stu-id="2878b-150">This function is named by appending the capture instance name to "cdc.fn_cdc_get_all_changes_".</span></span> <span data-ttu-id="2878b-151">Дополнительные сведения см. в разделе [cdc.fn_cdc_get_all_changes_&#60;capture_instance&#62; (Transact-SQL)](/sql/relational-databases/system-functions/cdc-fn-cdc-get-all-changes-capture-instance-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2878b-151">For more information, see [cdc.fn_cdc_get_all_changes_&#60;capture_instance&#62;  &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-all-changes-capture-instance-transact-sql).</span></span>  
  
 <span data-ttu-id="2878b-152">Если параметр *@supports_net_changes* имеет значение 1, то для экземпляра отслеживания также создается функция net changes.</span><span class="sxs-lookup"><span data-stu-id="2878b-152">If the parameter *@supports_net_changes* is set to 1, a net changes function is also generated for the capture instance.</span></span> <span data-ttu-id="2878b-153">Эта функция возвращает только одно изменение для каждой отдельной строки, измененной в течение интервала, указанного в вызове.</span><span class="sxs-lookup"><span data-stu-id="2878b-153">This function returns only one change for each distinct row changed in the interval specified in the call.</span></span> <span data-ttu-id="2878b-154">Дополнительные сведения см. в разделе [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; (Transact-SQL)](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2878b-154">For more information, see [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span></span>  
  
 <span data-ttu-id="2878b-155">Для поддержки запросов суммарных изменений исходная таблица должна иметь первичный ключ или уникальный индекс для идентификации строк.</span><span class="sxs-lookup"><span data-stu-id="2878b-155">To support net changes queries, the source table must have a primary key or unique index to uniquely identify rows.</span></span> <span data-ttu-id="2878b-156">Если используется уникальный индекс, имя индекса должно быть указано с помощью *@index_name* параметра.</span><span class="sxs-lookup"><span data-stu-id="2878b-156">If a unique index is used, the name of the index must be specified using the *@index_name* parameter.</span></span> <span data-ttu-id="2878b-157">Для отслеживания столбцов, определенных в первичном ключе или в уникальном индексе, они должны быть включены в список исходных столбцов.</span><span class="sxs-lookup"><span data-stu-id="2878b-157">The columns defined in the primary key or unique index must be included in the list of source columns to be captured.</span></span>  
  
 <span data-ttu-id="2878b-158">Пример создания экземпляра системы отслеживания с обеими функциями см. в шаблоне `Enable a Table for All and Net Changes Queries`.</span><span class="sxs-lookup"><span data-stu-id="2878b-158">See the `Enable a Table for All and Net Changes Queries` template for an example demonstrating the creation of a capture instance with both query functions.</span></span>  
  
```sql  
-- =============  
-- Enable a Table for All and Net Changes Queries template   
-- =============  
USE MyDB  
GO  
EXEC sys.sp_cdc_enable_table  
@source_schema = N'dbo',  
@source_name   = N'MyTable',  
@role_name     = N'MyRole',  
@supports_net_changes = 1  
GO  
```  
  
> [!NOTE]
>  <span data-ttu-id="2878b-159">Если система отслеживания измененных данных включена для таблицы с существующим первичным ключом, а *@index_name* параметр не используется для поиска альтернативного уникального индекса, то функция отслеживания измененных данных будет использовать первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="2878b-159">If change data capture is enabled on a table with an existing primary key, and the *@index_name* parameter is not used to identify an alternative unique index, the change data capture feature will use the primary key.</span></span> <span data-ttu-id="2878b-160">Все последующие изменения первичного ключа будут запрещены, пока для таблицы не будет отключена система отслеживания измененных данных.</span><span class="sxs-lookup"><span data-stu-id="2878b-160">Subsequent changes to the primary key will not be allowed without first disabling change data capture for the table.</span></span> <span data-ttu-id="2878b-161">Это справедливо независимо от того, была ли запрошена поддержка запросов суммарных изменений при настройке системы отслеживания измененных данных.</span><span class="sxs-lookup"><span data-stu-id="2878b-161">This is true regardless of whether support for net changes queries was requested when change data capture was configured.</span></span> <span data-ttu-id="2878b-162">Если во время включения таблицы для отслеживания измененных данных в ней не существовало первичного ключа, то, если впоследствии он будет добавлен, он будет пропускаться системой отслеживания измененных данных.</span><span class="sxs-lookup"><span data-stu-id="2878b-162">If there is no primary key on a table at the time it is enabled for change data capture, the subsequent addition of a primary key is ignored by change data capture.</span></span> <span data-ttu-id="2878b-163">Поскольку первичный ключ, созданный после включения таблицы, не будет использоваться системой отслеживания измененных данных, то данный ключ и ключевые столбцы могут быть удалены без ограничений.</span><span class="sxs-lookup"><span data-stu-id="2878b-163">Because change data capture will not use a primary key that is created after the table was enabled, the key and key columns can be removed without restrictions.</span></span>  
  
## <a name="disable-change-data-capture-for-a-table"></a><span data-ttu-id="2878b-164">Отключение системы отслеживания измененных данных для таблицы</span><span class="sxs-lookup"><span data-stu-id="2878b-164">Disable Change Data Capture for a Table</span></span>  
 <span data-ttu-id="2878b-165">Члены предопределенной роли базы данных `db_owner` могут удалять экземпляр системы отслеживания для отдельных исходных таблиц с помощью хранимой процедуры `sys.sp_cdc_disable_table`.</span><span class="sxs-lookup"><span data-stu-id="2878b-165">Members of the `db_owner` fixed database role can remove a capture instance for individual source tables by using the stored procedure `sys.sp_cdc_disable_table`.</span></span> <span data-ttu-id="2878b-166">Чтобы определить, включена ли в настоящее время для исходной таблицы система отслеживания измененных данных, рассмотрите столбец `is_tracked_by_cdc` в представлении каталога `sys.tables`.</span><span class="sxs-lookup"><span data-stu-id="2878b-166">To determine whether a source table is currently enabled for change data capture, examine the `is_tracked_by_cdc` column in the `sys.tables` catalog view.</span></span> <span data-ttu-id="2878b-167">Если после того, как имело место отключение, отсутствуют какие-либо таблицы, включенные для базы данных, также происходит удаление заданий отслеживания измененных данных.</span><span class="sxs-lookup"><span data-stu-id="2878b-167">If there are no tables enabled for the database after the disabling takes place, the change data capture jobs are also removed.</span></span>  
  
 <span data-ttu-id="2878b-168">Если удаляется информация об изменениях в таблице с включенным отслеживанием измененных данных, то автоматически удаляются метаданные системы отслеживания измененных данных, которые связаны с этой таблицей.</span><span class="sxs-lookup"><span data-stu-id="2878b-168">If a change data capture-enabled table is dropped, change data capture metadata that is associated with the table is automatically removed.</span></span>  
  
 <span data-ttu-id="2878b-169">Пример отключения таблицы см. в шаблоне отключения экземпляра системы отслеживания для таблицы.</span><span class="sxs-lookup"><span data-stu-id="2878b-169">See the Disable a Capture Instance for a Table template for an example of disabling a table.</span></span>  
  
```sql  
-- =====  
-- Disable a Capture Instance for a Table template   
-- =====  
USE MyDB  
GO  
EXEC sys.sp_cdc_disable_table  
@source_schema = N'dbo',  
@source_name   = N'MyTable',  
@capture_instance = N'dbo_MyTable'  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="2878b-170">См. также:</span><span class="sxs-lookup"><span data-stu-id="2878b-170">See Also</span></span>  
 <span data-ttu-id="2878b-171">[Отслеживание измененных данных (SQL Server)](track-data-changes-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2878b-171">[Track Data Changes &#40;SQL Server&#41;](track-data-changes-sql-server.md) </span></span>  
 <span data-ttu-id="2878b-172">[О фиксации измененных данных (SQL Server)](../track-changes/about-change-data-capture-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2878b-172">[About Change Data Capture &#40;SQL Server&#41;](../track-changes/about-change-data-capture-sql-server.md) </span></span>  
 <span data-ttu-id="2878b-173">[Работа с информацией об изменениях (SQL Server)](work-with-change-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2878b-173">[Work with Change Data &#40;SQL Server&#41;](work-with-change-data-sql-server.md) </span></span>  
 [<span data-ttu-id="2878b-174">Администрирование и наблюдение за отслеживанием измененных данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2878b-174">Administer and Monitor Change Data Capture &#40;SQL Server&#41;</span></span>](../track-changes/administer-and-monitor-change-data-capture-sql-server.md)  
  
  
