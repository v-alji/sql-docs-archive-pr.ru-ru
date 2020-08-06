---
title: Параметр конфигурации сервера cost threshold for parallelism | Документы Майкрософт
ms.custom: ''
ms.date: 10/26/2015
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- cost threshold for parallelism option
ms.assetid: dad21bee-fe28-41f6-9d2f-e6ababfaf9db
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 675055a753e84ace3a4fcb44b41b8c914326c5c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655957"
---
# <a name="configure-the-cost-threshold-for-parallelism-server-configuration-option"></a><span data-ttu-id="2e7a3-102">Параметр конфигурации сервера cost threshold for parallelism</span><span class="sxs-lookup"><span data-stu-id="2e7a3-102">Configure the cost threshold for parallelism Server Configuration Option</span></span>
  <span data-ttu-id="2e7a3-103">В этом разделе описываются способы настройки параметра конфигурации сервера **cost threshold for parallelism** в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e7a3-103">This topic describes how to configure the **cost threshold for parallelism** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="2e7a3-104">Параметр **cost threshold for parallelism** позволяет указать пороговое значение, при котором [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] создает и выполняет параллельные планы для запросов.</span><span class="sxs-lookup"><span data-stu-id="2e7a3-104">The **cost threshold for parallelism** option specifies the threshold at which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] creates and runs parallel plans for queries.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2e7a3-105">создает и выполняет параллельный план для запроса только в случае, если оценочная стоимость выполнения последовательного плана для этого запроса выше значения, заданного параметром **cost threshold for parallelism**.</span><span class="sxs-lookup"><span data-stu-id="2e7a3-105">creates and runs a parallel plan for a query only when the estimated cost to run a serial plan for the same query is higher than the value set in **cost threshold for parallelism**.</span></span> <span data-ttu-id="2e7a3-106">Стоимость представляет предполагаемое затраченное время в секундах, необходимое для выполнения последовательного плана в определенной конфигурации оборудования.</span><span class="sxs-lookup"><span data-stu-id="2e7a3-106">The cost refers to an estimated elapsed time in seconds required to run the serial plan on a specific hardware configuration.</span></span> <span data-ttu-id="2e7a3-107">Параметру **cost threshold for parallelism** можно присвоить любое значение от 0 до 32 767.</span><span class="sxs-lookup"><span data-stu-id="2e7a3-107">The **cost threshold for parallelism** option can be set to any value from 0 through 32767.</span></span> <span data-ttu-id="2e7a3-108">Значение по умолчанию — 5.</span><span class="sxs-lookup"><span data-stu-id="2e7a3-108">The default value is 5.</span></span>  
  
 <span data-ttu-id="2e7a3-109">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="2e7a3-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2e7a3-110">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="2e7a3-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2e7a3-111">Ограничения</span><span class="sxs-lookup"><span data-stu-id="2e7a3-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="2e7a3-112">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="2e7a3-112">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="2e7a3-113">Безопасность</span><span class="sxs-lookup"><span data-stu-id="2e7a3-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2e7a3-114">**Настройка параметра cost threshold for parallelism**</span><span class="sxs-lookup"><span data-stu-id="2e7a3-114">**To configure the cost threshold for parallelism option, using:**</span></span>  
  
     [<span data-ttu-id="2e7a3-115">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2e7a3-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2e7a3-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2e7a3-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="2e7a3-117">**Дальнейшие действия.**  [После настройки параметра cost threshold for parallelism](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="2e7a3-117">**Follow Up:**  [After you configure the cost threshold for parallelism option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2e7a3-118">Перед началом</span><span class="sxs-lookup"><span data-stu-id="2e7a3-118">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="2e7a3-119">Ограничения</span><span class="sxs-lookup"><span data-stu-id="2e7a3-119">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="2e7a3-120">Стоимость представляет предполагаемое затраченное время в секундах, необходимое для выполнения последовательного плана в определенной конфигурации оборудования.</span><span class="sxs-lookup"><span data-stu-id="2e7a3-120">The cost refers to an estimated elapsed time in seconds required to run the serial plan on a specific hardware configuration.</span></span> <span data-ttu-id="2e7a3-121">Устанавливайте параметр **cost threshold for parallelism** только на симметричных мультипроцессорах.</span><span class="sxs-lookup"><span data-stu-id="2e7a3-121">Only set **cost threshold for parallelism** on symmetric multiprocessors.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2e7a3-122">не учитывает значение параметра **cost threshold for parallelism** при следующих условиях.</span><span class="sxs-lookup"><span data-stu-id="2e7a3-122">ignores the **cost threshold for parallelism** value under the following conditions:</span></span>  
  
    -   <span data-ttu-id="2e7a3-123">В компьютере имеется только один логический процессор.</span><span class="sxs-lookup"><span data-stu-id="2e7a3-123">Your computer has only one logical processor.</span></span>  
  
    -   <span data-ttu-id="2e7a3-124">Только один логический процессор доступен для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в соответствии с параметром конфигурации **affinity mask** .</span><span class="sxs-lookup"><span data-stu-id="2e7a3-124">Only a single logical processor is available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] because of the **affinity mask** configuration option.</span></span>  
  
    -   <span data-ttu-id="2e7a3-125">Параметру **max degree of parallelism** присвоено значение 1.</span><span class="sxs-lookup"><span data-stu-id="2e7a3-125">The **max degree of parallelism** option is set to 1.</span></span>  
  
 <span data-ttu-id="2e7a3-126">Логический процессор является базовой единицей процессора, которая позволяет операционной системе перенаправлять задачи или выполнить поток.</span><span class="sxs-lookup"><span data-stu-id="2e7a3-126">A logical processor is the basic unit of processor hardware that allows the operating system to dispatch a task or execute a thread context.</span></span> <span data-ttu-id="2e7a3-127">Каждый логический процессор одновременно может выполнять только один поток.</span><span class="sxs-lookup"><span data-stu-id="2e7a3-127">Each logical processor can execute only one thread context at a time.</span></span> <span data-ttu-id="2e7a3-128">Процессорное ядро — это схема, которая обеспечивает возможность расшифровки и выполнения инструкций.</span><span class="sxs-lookup"><span data-stu-id="2e7a3-128">The processor core is the circuitry that provides ability to decode and execute instructions.</span></span> <span data-ttu-id="2e7a3-129">Процессорное ядро может содержать один или более логических процессоров.</span><span class="sxs-lookup"><span data-stu-id="2e7a3-129">A processor core may contain one or more logical processors.</span></span> <span data-ttu-id="2e7a3-130">Следующие запросы [!INCLUDE[tsql](../../includes/tsql-md.md)] можно использовать для получения сведений о ЦП системы.</span><span class="sxs-lookup"><span data-stu-id="2e7a3-130">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] query can be used for obtaining CPU information for the system.</span></span>  
  
```  
SELECT (cpu_count / hyperthread_ratio) AS PhysicalCPUs,   
cpu_count AS logicalCPUs   
FROM sys.dm_os_sys_info  
```  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="2e7a3-131">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="2e7a3-131">Recommendations</span></span>  
  
-   <span data-ttu-id="2e7a3-132">Этот параметр является дополнительным и его следует изменять только опытным администраторам баз данных или сертифицированным техническим специалистам [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2e7a3-132">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="2e7a3-133">В определенных случаях может быть выбран параллельный план, даже если стоимость плана запроса меньше текущего значения параметра **cost threshold for parallelism** .</span><span class="sxs-lookup"><span data-stu-id="2e7a3-133">In certain cases, a parallel plan may be chosen even though the query's cost plan is less than the current **cost threshold for parallelism** value.</span></span> <span data-ttu-id="2e7a3-134">Такое возможно, поскольку решение использовать параллельный или последовательный план основывается на ожидаемой стоимости, полученной до завершения полной оптимизации.</span><span class="sxs-lookup"><span data-stu-id="2e7a3-134">This can happen because the decision to use a parallel or serial plan is based on a cost estimate provided before the full optimization is complete.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2e7a3-135">безопасность</span><span class="sxs-lookup"><span data-stu-id="2e7a3-135">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2e7a3-136">Permissions</span><span class="sxs-lookup"><span data-stu-id="2e7a3-136">Permissions</span></span>  
 <span data-ttu-id="2e7a3-137">Разрешения на выполнение хранимой процедуры **sp_configure** без параметров или только с первым параметром по умолчанию предоставляются всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="2e7a3-137">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="2e7a3-138">Для выполнения процедуры **sp_configure** с обоими параметрами для изменения параметра конфигурации или запуска инструкции RECONFIGURE необходимо иметь разрешение ALTER SETTINGS на уровне сервера.</span><span class="sxs-lookup"><span data-stu-id="2e7a3-138">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="2e7a3-139">Разрешение ALTER SETTINGS неявным образом предоставлено предопределенным ролям сервера **sysadmin** и **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="2e7a3-139">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2e7a3-140">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2e7a3-140">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-cost-threshold-for-parallelism-option"></a><span data-ttu-id="2e7a3-141">Настройка параметра cost threshold for parallelism</span><span class="sxs-lookup"><span data-stu-id="2e7a3-141">To configure the cost threshold for parallelism option</span></span>  
  
1.  <span data-ttu-id="2e7a3-142">В обозревателе объектов щелкните правой кнопкой мыши сервер и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="2e7a3-142">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="2e7a3-143">Щелкните узел **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="2e7a3-143">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="2e7a3-144">В области **Параллелизм**измените параметр **CostThresholdForParallelism** на желаемое значение.</span><span class="sxs-lookup"><span data-stu-id="2e7a3-144">Under **Parallelism**, change the **CostThresholdForParallelism** option to the value you want.</span></span> <span data-ttu-id="2e7a3-145">Введите или выберите значение в диапазоне от 0 до 32767.</span><span class="sxs-lookup"><span data-stu-id="2e7a3-145">Type or select a value from 0 to 32767.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2e7a3-146">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2e7a3-146">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-cost-threshold-for-parallelism-option"></a><span data-ttu-id="2e7a3-147">Настройка параметра cost threshold for parallelism</span><span class="sxs-lookup"><span data-stu-id="2e7a3-147">To configure the cost threshold for parallelism option</span></span>  
  
1.  <span data-ttu-id="2e7a3-148">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e7a3-148">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2e7a3-149">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="2e7a3-149">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2e7a3-150">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="2e7a3-150">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="2e7a3-151">В этом примере описывается использование процедуры [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) для задания значения параметра `cost threshold for parallelism` равным `10`.</span><span class="sxs-lookup"><span data-stu-id="2e7a3-151">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `cost threshold for parallelism` option to `10`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1 ;  
GO  
RECONFIGURE  
GO  
EXEC sp_configure 'cost threshold for parallelism', 10 ;  
GO  
RECONFIGURE  
GO  
```  
  
 <span data-ttu-id="2e7a3-152">Дополнительные сведения см. в разделе [Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="2e7a3-152">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-cost-threshold-for-parallelism-option"></a><a name="FollowUp"></a> <span data-ttu-id="2e7a3-153">Дальнейшие действия. После настройки параметра cost threshold for parallelism</span><span class="sxs-lookup"><span data-stu-id="2e7a3-153">Follow Up: After you configure the cost threshold for parallelism option</span></span>  
 <span data-ttu-id="2e7a3-154">Параметр вступает в силу немедленно, без перезапуска сервера.</span><span class="sxs-lookup"><span data-stu-id="2e7a3-154">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e7a3-155">См. также:</span><span class="sxs-lookup"><span data-stu-id="2e7a3-155">See Also</span></span>  
 <span data-ttu-id="2e7a3-156">[Настройка параллельных операций с индексами](../../relational-databases/indexes/configure-parallel-index-operations.md) </span><span class="sxs-lookup"><span data-stu-id="2e7a3-156">[Configure Parallel Index Operations](../../relational-databases/indexes/configure-parallel-index-operations.md) </span></span>  
 <span data-ttu-id="2e7a3-157">[Указания запросов (Transact-SQL)](/sql/t-sql/queries/hints-transact-sql-query) </span><span class="sxs-lookup"><span data-stu-id="2e7a3-157">[Query Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span></span>  
 <span data-ttu-id="2e7a3-158">[ALTER WORKLOAD GROUP (Transact-SQL)](/sql/t-sql/statements/alter-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2e7a3-158">[ALTER WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-workload-group-transact-sql) </span></span>  
 <span data-ttu-id="2e7a3-159">[Параметр конфигурации сервера «affinity mask»](affinity-mask-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="2e7a3-159">[affinity mask Server Configuration Option](affinity-mask-server-configuration-option.md) </span></span>  
 <span data-ttu-id="2e7a3-160">[RECONFIGURE (Transact-SQL)](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2e7a3-160">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="2e7a3-161">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2e7a3-161">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="2e7a3-162">sp_configure (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="2e7a3-162">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
