---
title: Настройка параметра конфигурации сервера index create memory | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- index create memory option
ms.assetid: 3d722d9b-bada-4bf5-a9d7-bfc556bb4915
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6cd0aeb93d3fb68089338335068fdaaae19919fa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732018"
---
# <a name="configure-the-index-create-memory-server-configuration-option"></a><span data-ttu-id="bb7ae-102">Настройка параметра конфигурации сервера index create memory</span><span class="sxs-lookup"><span data-stu-id="bb7ae-102">Configure the index create memory Server Configuration Option</span></span>
  <span data-ttu-id="bb7ae-103">В этом разделе описываются способы настройки параметра конфигурации сервера **index create memory** в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb7ae-103">This topic describes how to configure the **index create memory** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="bb7ae-104">Параметр **index create memory** управляет максимальным объемом памяти, изначально выделенным для создания индексов.</span><span class="sxs-lookup"><span data-stu-id="bb7ae-104">The **index create memory** option controls the maximum amount of memory initially allocated for creating indexes.</span></span> <span data-ttu-id="bb7ae-105">Значение этого параметра по умолчанию равно 0 (настраивается автоматически).</span><span class="sxs-lookup"><span data-stu-id="bb7ae-105">The default value for this option is 0 (self-configuring).</span></span> <span data-ttu-id="bb7ae-106">Если в дальнейшем для создания индекса потребуется больший объем памяти и такой объем будет доступен, то сервер будет его использовать, тем самым превысив установку этого параметра.</span><span class="sxs-lookup"><span data-stu-id="bb7ae-106">If more memory is later needed for index creation and the memory is available, the server will use it; thereby, exceeding the setting of this option.</span></span> <span data-ttu-id="bb7ae-107">Если не будет доступной дополнительной памяти, то создание индекса продолжится с использованием уже выделенной памяти.</span><span class="sxs-lookup"><span data-stu-id="bb7ae-107">If additional memory is not available, the index creation will continue using the memory already allocated.</span></span>  
  
 <span data-ttu-id="bb7ae-108">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="bb7ae-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="bb7ae-109">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="bb7ae-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="bb7ae-110">Ограничения</span><span class="sxs-lookup"><span data-stu-id="bb7ae-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="bb7ae-111">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="bb7ae-111">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="bb7ae-112">Безопасность</span><span class="sxs-lookup"><span data-stu-id="bb7ae-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="bb7ae-113">**Настройка значения параметра index create memory с помощью следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="bb7ae-113">**To configure the index create memory option, using:**</span></span>  
  
     [<span data-ttu-id="bb7ae-114">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bb7ae-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="bb7ae-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bb7ae-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="bb7ae-116">**Дальнейшие действия.**  [После настройки параметра index create memory](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="bb7ae-116">**Follow Up:**  [After you configure the index create memory option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="bb7ae-117">Перед началом</span><span class="sxs-lookup"><span data-stu-id="bb7ae-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="bb7ae-118">Ограничения</span><span class="sxs-lookup"><span data-stu-id="bb7ae-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="bb7ae-119">Параметр **min memory per query** имеет приоритет над параметром **index create memory**.</span><span class="sxs-lookup"><span data-stu-id="bb7ae-119">The setting of the **min memory per query** option has precedence over the **index create memory** option.</span></span> <span data-ttu-id="bb7ae-120">Если изменяются оба параметра и значение параметра **index create memory** меньше значения **min memory per query**, то в системе отобразится предупреждающее сообщение, но это значение будет установлено.</span><span class="sxs-lookup"><span data-stu-id="bb7ae-120">If you change both options and the **index create memory** is less than **min memory per query**, you receive a warning message, but the value is set.</span></span> <span data-ttu-id="bb7ae-121">При выполнении запроса система выдаст такое же сообщение.</span><span class="sxs-lookup"><span data-stu-id="bb7ae-121">During query execution, you receive a similar warning.</span></span>  
  
-   <span data-ttu-id="bb7ae-122">При использовании секционированных таблиц и индексов требования к минимальному объему памяти для создания индексов могут быть значительно увеличены при наличии несвязанных секционированных индексов и большой степени параллелизма.</span><span class="sxs-lookup"><span data-stu-id="bb7ae-122">When using partitioned tables and indexes, the minimum memory requirements for index creation may increase significantly if there are non-aligned partitioned indexes and a high degree of parallelism.</span></span> <span data-ttu-id="bb7ae-123">Этот параметр управляет общим начальным объемом памяти, выделенным для всех секций индекса в одной операции создания индекса.</span><span class="sxs-lookup"><span data-stu-id="bb7ae-123">This option controls the total initial amount of memory allocated for all index partitions in a single index creation operation.</span></span> <span data-ttu-id="bb7ae-124">Если объем, установленный данным параметром меньше, чем минимально необходимый для выполнения запроса, то выполнение запроса прервется с сообщением об ошибке.</span><span class="sxs-lookup"><span data-stu-id="bb7ae-124">The query will terminate with an error message if the amount set by this option is less than the minimum required to run the query.</span></span>  
  
-   <span data-ttu-id="bb7ae-125">Рабочее значение этого параметра не будет превышать фактический объем памяти, используемый операционной системой и платформой оборудования, на которой выполняется [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bb7ae-125">The run value for this option will not exceed the actual amount of memory that can be used for the operating system and hardware platform on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running.</span></span> <span data-ttu-id="bb7ae-126">В 32-разрядных версиях операционных систем это значение не превышает 3 гигабайт (ГБ).</span><span class="sxs-lookup"><span data-stu-id="bb7ae-126">On 32-bit operating systems, the run value will be less than 3 gigabytes (GB).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="bb7ae-127">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="bb7ae-127">Recommendations</span></span>  
  
-   <span data-ttu-id="bb7ae-128">Этот параметр является дополнительным и его следует изменять только опытным администраторам баз данных или сертифицированным техническим специалистам [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bb7ae-128">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="bb7ae-129">Параметр **index create memory** настраивается автоматически, и, как правило, дополнительная настройка не требуется.</span><span class="sxs-lookup"><span data-stu-id="bb7ae-129">The **index create memory** option is self-configuring and usually works without requiring adjustment.</span></span> <span data-ttu-id="bb7ae-130">Однако при возникновении затруднений при создании индексов можно попробовать увеличить значение этого параметра.</span><span class="sxs-lookup"><span data-stu-id="bb7ae-130">However, if you experience difficulties creating indexes, consider increasing the value of this option from its run value.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="bb7ae-131">безопасность</span><span class="sxs-lookup"><span data-stu-id="bb7ae-131">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="bb7ae-132">Permissions</span><span class="sxs-lookup"><span data-stu-id="bb7ae-132">Permissions</span></span>  
 <span data-ttu-id="bb7ae-133">Разрешения на выполнение хранимой процедуры **sp_configure** без параметров или только с первым параметром по умолчанию предоставляются всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="bb7ae-133">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="bb7ae-134">Для выполнения процедуры **sp_configure** с обоими параметрами для изменения параметра конфигурации или запуска инструкции RECONFIGURE необходимо иметь разрешение ALTER SETTINGS на уровне сервера.</span><span class="sxs-lookup"><span data-stu-id="bb7ae-134">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="bb7ae-135">Разрешение ALTER SETTINGS неявным образом предоставлено предопределенным ролям сервера **sysadmin** и **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="bb7ae-135">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="bb7ae-136">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bb7ae-136">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-index-create-memory-option"></a><span data-ttu-id="bb7ae-137">Настройка параметра index create memory</span><span class="sxs-lookup"><span data-stu-id="bb7ae-137">To configure the index create memory option</span></span>  
  
1.  <span data-ttu-id="bb7ae-138">В обозревателе объектов щелкните правой кнопкой мыши сервер и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="bb7ae-138">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="bb7ae-139">Щелкните узел **Память** .</span><span class="sxs-lookup"><span data-stu-id="bb7ae-139">Click the **Memory** node.</span></span>  
  
3.  <span data-ttu-id="bb7ae-140">В свойстве **Память для создания индекса**введите или выберите необходимое значение параметра.</span><span class="sxs-lookup"><span data-stu-id="bb7ae-140">Under **Index creation memory**, type or select the desired value for the index create memory option.</span></span>  
  
     <span data-ttu-id="bb7ae-141">Параметр **index create memory** предназначен для управления объемом памяти, используемой операциями сортировки при создании индексов.</span><span class="sxs-lookup"><span data-stu-id="bb7ae-141">Use the **index create memory** option to control the amount of memory used by index creation sorts.</span></span> <span data-ttu-id="bb7ae-142">Параметр **Память при создании индекса** конфигурируется автоматически, и в большинстве случаев его дополнительная настройка не требуется.</span><span class="sxs-lookup"><span data-stu-id="bb7ae-142">The **index create memory** option is self-configuring and should work in most cases without requiring adjustment.</span></span> <span data-ttu-id="bb7ae-143">Однако при возникновении затруднений при создании индексов можно попробовать увеличить значение этого параметра.</span><span class="sxs-lookup"><span data-stu-id="bb7ae-143">However, if you experience difficulties creating indexes, consider increasing the value of this option from its run value.</span></span> <span data-ttu-id="bb7ae-144">Операции сортировки в запросах управляются параметром **min memory per query** .</span><span class="sxs-lookup"><span data-stu-id="bb7ae-144">Query sorts are controlled through the **min memory per query** option.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="bb7ae-145">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bb7ae-145">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-index-create-memory-option"></a><span data-ttu-id="bb7ae-146">Настройка параметра index create memory</span><span class="sxs-lookup"><span data-stu-id="bb7ae-146">To configure the index create memory option</span></span>  
  
1.  <span data-ttu-id="bb7ae-147">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb7ae-147">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="bb7ae-148">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="bb7ae-148">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="bb7ae-149">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="bb7ae-149">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="bb7ae-150">В этом примере описывается использование процедуры [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) для задания значения параметра `index create memory` равным `4096`.</span><span class="sxs-lookup"><span data-stu-id="bb7ae-150">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `index create memory` option to `4096`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
EXEC sp_configure 'index create memory', 4096  
GO  
RECONFIGURE;  
GO  
```  
  
 <span data-ttu-id="bb7ae-151">Дополнительные сведения см. в разделе [Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="bb7ae-151">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-index-create-memory-option"></a><a name="FollowUp"></a> <span data-ttu-id="bb7ae-152">Дальнейшие действия. После настройки параметра index create memory</span><span class="sxs-lookup"><span data-stu-id="bb7ae-152">Follow Up: After you configure the index create memory option</span></span>  
 <span data-ttu-id="bb7ae-153">Параметр вступает в силу немедленно, без перезапуска сервера.</span><span class="sxs-lookup"><span data-stu-id="bb7ae-153">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb7ae-154">См. также:</span><span class="sxs-lookup"><span data-stu-id="bb7ae-154">See Also</span></span>  
 <span data-ttu-id="bb7ae-155">[sys.configurations (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bb7ae-155">[sys.configurations &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) </span></span>  
 <span data-ttu-id="bb7ae-156">[RECONFIGURE (Transact-SQL)](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bb7ae-156">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="bb7ae-157">[Параметры конфигурации сервера «Server Memory»](server-memory-server-configuration-options.md) </span><span class="sxs-lookup"><span data-stu-id="bb7ae-157">[Server Memory Server Configuration Options](server-memory-server-configuration-options.md) </span></span>  
 <span data-ttu-id="bb7ae-158">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="bb7ae-158">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="bb7ae-159">sp_configure (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="bb7ae-159">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
