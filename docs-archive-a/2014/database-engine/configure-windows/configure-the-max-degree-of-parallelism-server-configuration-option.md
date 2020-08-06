---
title: Настройка параметра конфигурации сервера max degree of parallelism | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- parallel queries [SQL Server]
- processors [SQL Server], parallel queries
- number of processors for parallel queries
- max degree of parallelism option
ms.assetid: 86b65bf1-a6a1-4670-afc0-cdfad1558032
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 824dc837142acc4a0898cb04b4a8687bc5be4043
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665564"
---
# <a name="configure-the-max-degree-of-parallelism-server-configuration-option"></a><span data-ttu-id="329a4-102">Настройка параметра конфигурации сервера max degree of parallelism</span><span class="sxs-lookup"><span data-stu-id="329a4-102">Configure the max degree of parallelism Server Configuration Option</span></span>
  <span data-ttu-id="329a4-103">В этом разделе описывается настройка `max degree of parallelism` параметра конфигурации сервера в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="329a4-103">This topic describes how to configure the `max degree of parallelism` server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="329a4-104">Если экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] работает на многопроцессорном компьютере, он определяет оптимальную степень параллелизма, то есть количество процессоров, задействованных для выполнения одной инструкции, для каждого из планов параллельного выполнения.</span><span class="sxs-lookup"><span data-stu-id="329a4-104">When an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] runs on a computer that has more than one microprocessor or CPU, it detects the best degree of parallelism, that is, the number of processors employed to run a single statement, for each parallel plan execution.</span></span> <span data-ttu-id="329a4-105">Можно использовать параметр `max degree of parallelism` для ограничения числа процессоров, применяемых в планах параллельного выполнения.</span><span class="sxs-lookup"><span data-stu-id="329a4-105">You can use the `max degree of parallelism` option to limit the number of processors to use in parallel plan execution.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="329a4-106">учитывает планы параллельного выполнения для запросов, операций DDL с индексами, а также заполнения статических курсоров и курсоров, управляемых набором ключей.</span><span class="sxs-lookup"><span data-stu-id="329a4-106">considers parallel execution plans for queries, index data definition language (DDL) operations, and static and keyset-driven cursor population.</span></span>  
  
 <span data-ttu-id="329a4-107">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="329a4-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="329a4-108">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="329a4-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="329a4-109">Ограничения</span><span class="sxs-lookup"><span data-stu-id="329a4-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="329a4-110">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="329a4-110">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="329a4-111">Безопасность</span><span class="sxs-lookup"><span data-stu-id="329a4-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="329a4-112">**Настройка максимальной степени параллелизма с помощью:**</span><span class="sxs-lookup"><span data-stu-id="329a4-112">**To configure the max degree of parallelism option, using:**</span></span>  
  
     [<span data-ttu-id="329a4-113">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="329a4-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="329a4-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="329a4-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="329a4-115">**Продолжение**  [после настройки параметра max degree of parallelism](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="329a4-115">**Follow Up:**  [After you configure the max degree of parallelism option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="329a4-116">Перед началом</span><span class="sxs-lookup"><span data-stu-id="329a4-116">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="329a4-117">Ограничения</span><span class="sxs-lookup"><span data-stu-id="329a4-117">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="329a4-118">Если параметр affinity mask имеет значение, отличное от значения по умолчанию, он может ограничивать число процессоров, доступных для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в симметричных многопроцессорных системах (SMP).</span><span class="sxs-lookup"><span data-stu-id="329a4-118">If the affinity mask option is not set to the default, it may restrict the number of processors available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on symmetric multiprocessing (SMP) systems.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="329a4-119">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="329a4-119">Recommendations</span></span>  
  
-   <span data-ttu-id="329a4-120">Этот параметр является дополнительным и его следует изменять только опытным администраторам баз данных или сертифицированным техническим специалистам [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="329a4-120">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="329a4-121">Чтобы разрешить серверу определять максимальную степень параллелизма, установите 0 в качестве значения данного параметра, то есть значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="329a4-121">To enable the server to determine the maximum degree of parallelism, set this option to 0, the default value.</span></span> <span data-ttu-id="329a4-122">Установка значения 0 в качестве максимальной степени параллелизма позволяет [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] использовать все доступные процессоры (до 64 процессоров).</span><span class="sxs-lookup"><span data-stu-id="329a4-122">Setting maximum degree of parallelism to 0 allows [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to use all the available processors up to 64 processors.</span></span> <span data-ttu-id="329a4-123">Чтобы отключить создание параллельных планов, присвойте параметру `max degree of parallelism` значение 1.</span><span class="sxs-lookup"><span data-stu-id="329a4-123">To suppress parallel plan generation, set `max degree of parallelism` to 1.</span></span> <span data-ttu-id="329a4-124">Задайте значение для параметра в диапазоне от 1 до 32 767, чтобы указать максимальное количество процессорных ядер, которые могут быть использованы при выполнении одного запроса.</span><span class="sxs-lookup"><span data-stu-id="329a4-124">Set the value to a number from 1 to 32,767 to specify the maximum number of processor cores that can be used by a single query execution.</span></span> <span data-ttu-id="329a4-125">Если указано значение, превышающее количество доступных процессоров, используется действительное количество доступных процессоров.</span><span class="sxs-lookup"><span data-stu-id="329a4-125">If a value greater than the number of available processors is specified, the actual number of available processors is used.</span></span> <span data-ttu-id="329a4-126">Если у компьютера только один процессор, то значение параметра `max degree of parallelism` учитываться не будет.</span><span class="sxs-lookup"><span data-stu-id="329a4-126">If the computer has only one processor, the `max degree of parallelism` value is ignored.</span></span>  
  
-   <span data-ttu-id="329a4-127">Значение параметра max degree of parallelism можно переопределить, задав в инструкции указание запроса MAXDOP.</span><span class="sxs-lookup"><span data-stu-id="329a4-127">You can override the max degree of parallelism value in queries by specifying the MAXDOP query hint in the query statement.</span></span> <span data-ttu-id="329a4-128">Дополнительные сведения см. в разделе [Указания запросов (Transact-SQL)](/sql/t-sql/queries/hints-transact-sql-query).</span><span class="sxs-lookup"><span data-stu-id="329a4-128">For more information, see [Query Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query).</span></span>  
  
-   <span data-ttu-id="329a4-129">Операции по созданию и перестройке индексов, а также по удалению кластеризованного индекса могут оказаться достаточно ресурсоемкими.</span><span class="sxs-lookup"><span data-stu-id="329a4-129">Index operations that create or rebuild an index, or that drop a clustered index, can be resource intensive.</span></span> <span data-ttu-id="329a4-130">Значение параметра max degree of parallelism для операций с индексами можно переопределить, указав в инструкции параметр индекса MAXDOP.</span><span class="sxs-lookup"><span data-stu-id="329a4-130">You can override the max degree of parallelism value for index operations by specifying the MAXDOP index option in the index statement.</span></span> <span data-ttu-id="329a4-131">Значение MAXDOP применяется к инструкции во время выполнения и в метаданных индекса не хранится.</span><span class="sxs-lookup"><span data-stu-id="329a4-131">The MAXDOP value is applied to the statement at execution time and is not stored in the index metadata.</span></span> <span data-ttu-id="329a4-132">Дополнительные сведения см. в статье [Настройка параллельных операций с индексами](../../relational-databases/indexes/configure-parallel-index-operations.md).</span><span class="sxs-lookup"><span data-stu-id="329a4-132">For more information, see [Configure Parallel Index Operations](../../relational-databases/indexes/configure-parallel-index-operations.md).</span></span>  
  
-   <span data-ttu-id="329a4-133">Помимо запросов и операций с индексами, этот параметр также управляет степенью параллелизма при выполнении инструкций DBCC CHECKTABLE, DBCC CHECKDB и DBCC CHECKFILEGROUP.</span><span class="sxs-lookup"><span data-stu-id="329a4-133">In addition to queries and index operations, this option also controls the parallelism of DBCC CHECKTABLE, DBCC CHECKDB, and DBCC CHECKFILEGROUP.</span></span> <span data-ttu-id="329a4-134">Планы параллельного выполнения для этих инструкций можно отключить с помощью флага трассировки 2528.</span><span class="sxs-lookup"><span data-stu-id="329a4-134">You can disable parallel execution plans for these statements by using trace flag 2528.</span></span> <span data-ttu-id="329a4-135">Дополнительные сведения см. в разделе [Флаги трассировки (Transact-SQL)](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="329a4-135">For more information, see [Trace Flags &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="329a4-136">безопасность</span><span class="sxs-lookup"><span data-stu-id="329a4-136">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="329a4-137">Permissions</span><span class="sxs-lookup"><span data-stu-id="329a4-137">Permissions</span></span>  
 <span data-ttu-id="329a4-138">Разрешения на выполнение хранимой процедуры **sp_configure** без параметров или только с первым параметром по умолчанию предоставляются всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="329a4-138">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="329a4-139">Для выполнения процедуры **sp_configure** с обоими параметрами для изменения параметра конфигурации или запуска инструкции RECONFIGURE необходимо иметь разрешение ALTER SETTINGS на уровне сервера.</span><span class="sxs-lookup"><span data-stu-id="329a4-139">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="329a4-140">Разрешение ALTER SETTINGS неявным образом предоставлено предопределенным ролям сервера **sysadmin** и **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="329a4-140">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="329a4-141">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="329a4-141">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-max-degree-of-parallelism-option"></a><span data-ttu-id="329a4-142">Настройка параметра максимальной степени параллелизма</span><span class="sxs-lookup"><span data-stu-id="329a4-142">To configure the max degree of parallelism option</span></span>  
  
1.  <span data-ttu-id="329a4-143">В **обозревателе объектов**щелкните правой кнопкой мыши сервер и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="329a4-143">In **Object Explorer**, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="329a4-144">Щелкните узел **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="329a4-144">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="329a4-145">В поле **Максимальная степень параллелизма** укажите максимальное число процессоров, которое может быть использовано в плане параллельного выполнения.</span><span class="sxs-lookup"><span data-stu-id="329a4-145">In the **Max Degree of Parallelism** box, select the maximum number of processors to use in parallel plan execution.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="329a4-146">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="329a4-146">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-max-degree-of-parallelism-option"></a><span data-ttu-id="329a4-147">Настройка параметра максимальной степени параллелизма</span><span class="sxs-lookup"><span data-stu-id="329a4-147">To configure the max degree of parallelism option</span></span>  
  
1.  <span data-ttu-id="329a4-148">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="329a4-148">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="329a4-149">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="329a4-149">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="329a4-150">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="329a4-150">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="329a4-151">В этом примере описывается использование процедуры [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) для задания значения параметра `max degree of parallelism` равным `8`.</span><span class="sxs-lookup"><span data-stu-id="329a4-151">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to configure the `max degree of parallelism` option to `8`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO   
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE WITH OVERRIDE;  
GO  
EXEC sp_configure 'max degree of parallelism', 8;  
GO  
RECONFIGURE WITH OVERRIDE;  
GO  
```  
  
 <span data-ttu-id="329a4-152">Дополнительные сведения см. в разделе [Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="329a4-152">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-max-degree-of-parallelism-option"></a><a name="FollowUp"></a> <span data-ttu-id="329a4-153">Дальнейшие действия. После настройки параметра max degree of parallelism</span><span class="sxs-lookup"><span data-stu-id="329a4-153">Follow Up: After you configure the max degree of parallelism option</span></span>  
 <span data-ttu-id="329a4-154">Параметр вступает в силу немедленно, без перезапуска сервера.</span><span class="sxs-lookup"><span data-stu-id="329a4-154">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="329a4-155">См. также:</span><span class="sxs-lookup"><span data-stu-id="329a4-155">See Also</span></span>  
 <span data-ttu-id="329a4-156">[Параметр конфигурации сервера «affinity mask»](affinity-mask-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="329a4-156">[affinity mask Server Configuration Option](affinity-mask-server-configuration-option.md) </span></span>  
 <span data-ttu-id="329a4-157">[RECONFIGURE (Transact-SQL)](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="329a4-157">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="329a4-158">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="329a4-158">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="329a4-159">[sp_configure (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="329a4-159">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="329a4-160">[CREATE INDEX (Transact-SQL)](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="329a4-160">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 <span data-ttu-id="329a4-161">[ALTER INDEX (Transact-SQL)](/sql/t-sql/statements/alter-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="329a4-161">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span></span>  
 <span data-ttu-id="329a4-162">[ALTER TABLE (Transact-SQL)](/sql/t-sql/statements/alter-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="329a4-162">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span></span>  
 <span data-ttu-id="329a4-163">[DBCC CHECKTABLE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checktable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="329a4-163">[DBCC CHECKTABLE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checktable-transact-sql) </span></span>  
 <span data-ttu-id="329a4-164">[DBCC CHECKDB &#40;&#41;Transact-SQL](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="329a4-164">[DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span></span>  
 <span data-ttu-id="329a4-165">[DBCC CHECKFILEGROUP &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkfilegroup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="329a4-165">[DBCC CHECKFILEGROUP &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkfilegroup-transact-sql) </span></span>  
 <span data-ttu-id="329a4-166">[Настройка параллельных операций с индексами](../../relational-databases/indexes/configure-parallel-index-operations.md) </span><span class="sxs-lookup"><span data-stu-id="329a4-166">[Configure Parallel Index Operations](../../relational-databases/indexes/configure-parallel-index-operations.md) </span></span>  
 <span data-ttu-id="329a4-167">[Указания запросов (Transact-SQL)](/sql/t-sql/queries/hints-transact-sql-query) </span><span class="sxs-lookup"><span data-stu-id="329a4-167">[Query Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span></span>  
 [<span data-ttu-id="329a4-168">Установка параметров индекса</span><span class="sxs-lookup"><span data-stu-id="329a4-168">Set Index Options</span></span>](../../relational-databases/indexes/set-index-options.md)  
  
  
