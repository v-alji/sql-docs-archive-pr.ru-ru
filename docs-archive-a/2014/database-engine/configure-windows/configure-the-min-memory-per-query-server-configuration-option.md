---
title: Настройка параметра конфигурации сервера "min memory per query" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- memory [SQL Server], queries
- minimum query memory
- queries [SQL Server], memory
- min memory per query option
ms.assetid: ecd3fb79-b4a6-432f-9ef5-530e0d42d5a6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 56d85f36840f0900c8b5e986334a99ba610d3930
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665556"
---
# <a name="configure-the-min-memory-per-query-server-configuration-option"></a><span data-ttu-id="67027-102">Настройка параметра конфигурации сервера min memory per query</span><span class="sxs-lookup"><span data-stu-id="67027-102">Configure the min memory per query Server Configuration Option</span></span>
  <span data-ttu-id="67027-103">В этом разделе описывается настройка `min memory per query` параметра конфигурации сервера в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="67027-103">This topic describes how to configure the `min memory per query` server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="67027-104">`min memory per query`Параметр задает минимальный объем памяти (в килобайтах), который будет выделен для выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="67027-104">The `min memory per query` option specifies the minimum amount of memory (in kilobytes) that will be allocated for the execution of a query.</span></span> <span data-ttu-id="67027-105">Например, если `min memory per query` для задано значение 2 048 КБ, то запрос гарантированно получит по крайней мере такой большой объем памяти.</span><span class="sxs-lookup"><span data-stu-id="67027-105">For example, if `min memory per query` is set to 2,048 KB, the query is guaranteed to get at least that much total memory.</span></span> <span data-ttu-id="67027-106">Значение по умолчанию — 1 024 КБ.</span><span class="sxs-lookup"><span data-stu-id="67027-106">The default value is 1,024 KB.</span></span> <span data-ttu-id="67027-107">Минимальное значение — 512 КБ, максимальное — 2 147 483 647 KB (2 ГБ).</span><span class="sxs-lookup"><span data-stu-id="67027-107">The minimum value 512 KB, and the maximum is 2,147,483,647 KB (2 GB).</span></span>  
  
 <span data-ttu-id="67027-108">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="67027-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="67027-109">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="67027-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="67027-110">Ограничения</span><span class="sxs-lookup"><span data-stu-id="67027-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="67027-111">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="67027-111">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="67027-112">Безопасность</span><span class="sxs-lookup"><span data-stu-id="67027-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="67027-113">**Настройка параметра min memory per query с помощью**</span><span class="sxs-lookup"><span data-stu-id="67027-113">**To configure the min memory per query option, using:**</span></span>  
  
     [<span data-ttu-id="67027-114">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="67027-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="67027-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="67027-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="67027-116">**Дальнейшие действия.**  [После настройки параметра min memory per query](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="67027-116">**Follow Up:**  [After you configure the min memory per query option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="67027-117">Перед началом</span><span class="sxs-lookup"><span data-stu-id="67027-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="67027-118">Ограничения</span><span class="sxs-lookup"><span data-stu-id="67027-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="67027-119">Уровень минимального объема памяти для запроса имеет приоритет над [параметром индекс создания памяти](configure-the-index-create-memory-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="67027-119">The amount of min memory per query has precedence over the [index create memory Option](configure-the-index-create-memory-server-configuration-option.md).</span></span> <span data-ttu-id="67027-120">Если изменяются оба параметра и значение параметра index create memory меньше значения min memory per query, то в системе отобразится предупреждающее сообщение, но это значение будет установлено.</span><span class="sxs-lookup"><span data-stu-id="67027-120">If you modify both options and the index create memory is less than min memory per query, you receive a warning message, but the value is set.</span></span> <span data-ttu-id="67027-121">При выполнении запроса будет выдано еще одно аналогичное предупреждение.</span><span class="sxs-lookup"><span data-stu-id="67027-121">During query execution you receive another similar warning.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="67027-122">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="67027-122">Recommendations</span></span>  
  
-   <span data-ttu-id="67027-123">Этот параметр является дополнительным и его следует изменять только опытным администраторам баз данных или сертифицированным техническим специалистам [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="67027-123">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="67027-124">Обработчик запросов [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] пытается определить оптимальный объем памяти, выделяемой запросу.</span><span class="sxs-lookup"><span data-stu-id="67027-124">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] query processor tries to determine the optimal amount of memory to allocate to a query.</span></span> <span data-ttu-id="67027-125">Параметр min memory per query позволяет администратору указать минимальный размер памяти, который получает каждый запрос.</span><span class="sxs-lookup"><span data-stu-id="67027-125">The min memory per query option lets the administrator specify the minimum amount of memory any single query receives.</span></span> <span data-ttu-id="67027-126">Запросы обычно получают объем памяти больше указанного значения, если выполняют хэширование или сортировку больших объемов данных.</span><span class="sxs-lookup"><span data-stu-id="67027-126">Queries generally receive more memory than this if they have hash and sort operations on a large volume of data.</span></span> <span data-ttu-id="67027-127">Увеличение значения параметра min memory per query может повысить производительность для малых и средних запросов, однако это может привести к повышению конкуренции за память.</span><span class="sxs-lookup"><span data-stu-id="67027-127">Increasing the value of min memory per query may improve performance for some small to medium-sized queries, but doing so could lead to increased competition for memory resources.</span></span> <span data-ttu-id="67027-128">Параметр min memory per query включает память, выделенную для сортировки.</span><span class="sxs-lookup"><span data-stu-id="67027-128">The min memory per query option includes memory allocated for sorting.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="67027-129">безопасность</span><span class="sxs-lookup"><span data-stu-id="67027-129">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="67027-130">Permissions</span><span class="sxs-lookup"><span data-stu-id="67027-130">Permissions</span></span>  
 <span data-ttu-id="67027-131">Разрешения на выполнение хранимой процедуры **sp_configure** без параметров или только с первым параметром по умолчанию предоставляются всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="67027-131">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="67027-132">Для выполнения процедуры **sp_configure** с обоими параметрами для изменения параметра конфигурации или запуска инструкции RECONFIGURE необходимо иметь разрешение ALTER SETTINGS на уровне сервера.</span><span class="sxs-lookup"><span data-stu-id="67027-132">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="67027-133">Разрешение ALTER SETTINGS неявным образом предоставлено предопределенным ролям сервера **sysadmin** и **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="67027-133">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="67027-134">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="67027-134">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-min-memory-per-query-option"></a><span data-ttu-id="67027-135">Настройка параметра min memory per query</span><span class="sxs-lookup"><span data-stu-id="67027-135">To configure the min memory per query option</span></span>  
  
1.  <span data-ttu-id="67027-136">В обозревателе объектов щелкните правой кнопкой мыши сервер и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="67027-136">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="67027-137">Щелкните узел **Память** .</span><span class="sxs-lookup"><span data-stu-id="67027-137">Click the **Memory** node.</span></span>  
  
3.  <span data-ttu-id="67027-138">В поле **Минимальный объем памяти для запроса** введите минимальный объем памяти (в килобайтах), который будет выделен запросу для выполнения.</span><span class="sxs-lookup"><span data-stu-id="67027-138">In the **Minimum memory per query** box, enter the minimum amount of memory (in kilobytes) that will be allocated for the execution of a query.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="67027-139">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="67027-139">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-min-memory-per-query-option"></a><span data-ttu-id="67027-140">Настройка параметра min memory per query</span><span class="sxs-lookup"><span data-stu-id="67027-140">To configure the min memory per query option</span></span>  
  
1.  <span data-ttu-id="67027-141">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="67027-141">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="67027-142">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="67027-142">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="67027-143">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="67027-143">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="67027-144">В этом примере показано использование хранимой процедуры [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) для задания значения параметра `min memory per query` равным `3500` КБ.</span><span class="sxs-lookup"><span data-stu-id="67027-144">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `min memory per query` option to `3500` KB.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'min memory per query', 3500 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
##  <a name="follow-up-after-you-configure-the-min-memory-per-query-option"></a><a name="FollowUp"></a> <span data-ttu-id="67027-145">Дальнейшие действия. После настройки параметра min memory per query</span><span class="sxs-lookup"><span data-stu-id="67027-145">Follow Up: After you configure the min memory per query option</span></span>  
 <span data-ttu-id="67027-146">Параметр вступает в силу немедленно, без перезапуска сервера.</span><span class="sxs-lookup"><span data-stu-id="67027-146">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67027-147">См. также:</span><span class="sxs-lookup"><span data-stu-id="67027-147">See Also</span></span>  
 <span data-ttu-id="67027-148">[RECONFIGURE (Transact-SQL)](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="67027-148">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="67027-149">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="67027-149">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="67027-150">[sp_configure (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="67027-150">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="67027-151">Настройка параметра конфигурации сервера index create memory</span><span class="sxs-lookup"><span data-stu-id="67027-151">Configure the index create memory Server Configuration Option</span></span>](configure-the-index-create-memory-server-configuration-option.md)  
  
  
