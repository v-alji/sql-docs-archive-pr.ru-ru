---
title: Настройка параметра конфигурации сервера "query governor cost limit" | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- queries [SQL Server], time to execute
- query governor cost limit option [SQL Server]
- time [SQL Server], query run time
ms.assetid: e7b8f084-1052-4133-959b-cebf4add790f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4d4f8420bf8ed8c08d3626c797968c041a40f7c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655952"
---
# <a name="configure-the-query-governor-cost-limit-server-configuration-option"></a><span data-ttu-id="cda2e-102">Настройка параметра конфигурации сервера query governor cost limit</span><span class="sxs-lookup"><span data-stu-id="cda2e-102">Configure the query governor cost limit Server Configuration Option</span></span>
  <span data-ttu-id="cda2e-103">В этом разделе описывается настройка `query governor cost limit` параметра конфигурации сервера в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cda2e-103">This topic describes how to configure the `query governor cost limit` server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="cda2e-104">Используйте параметр предела стоимости регулятора запросов для того, чтобы задать верхнюю границу времени выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="cda2e-104">The query governor cost limit option specifies an upper limit on the time period in which a query can run.</span></span> <span data-ttu-id="cda2e-105">Цена запроса — это предполагаемое время в секундах, которое требуется для завершения запроса в конкретной конфигурации оборудования.</span><span class="sxs-lookup"><span data-stu-id="cda2e-105">Query cost refers to the estimated elapsed time, in seconds, that is required to complete a query on a specific hardware configuration.</span></span> <span data-ttu-id="cda2e-106">Значение по умолчанию для этого параметра — 0, при котором регулятор запросов отключен.</span><span class="sxs-lookup"><span data-stu-id="cda2e-106">The default value for this option is 0, which sets the query governor to off.</span></span> <span data-ttu-id="cda2e-107">Это позволяет обрабатывать запросы без временных ограничений.</span><span class="sxs-lookup"><span data-stu-id="cda2e-107">This allows all queries to run without any time limitation.</span></span> <span data-ttu-id="cda2e-108">Если задать значение больше нуля, регулятор запросов запрещает выполнение всех запросов, оценочная стоимость которых превышает это значение.</span><span class="sxs-lookup"><span data-stu-id="cda2e-108">If you specify a nonzero, nonnegative value, the query governor disallows execution of any query that has an estimated cost that exceeds that value.</span></span>  
  
 <span data-ttu-id="cda2e-109">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="cda2e-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="cda2e-110">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="cda2e-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="cda2e-111">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="cda2e-111">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="cda2e-112">Безопасность</span><span class="sxs-lookup"><span data-stu-id="cda2e-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="cda2e-113">**Настройка параметра query governor cost limit с помощью**</span><span class="sxs-lookup"><span data-stu-id="cda2e-113">**To configure the query governor cost limit option, using:**</span></span>  
  
     [<span data-ttu-id="cda2e-114">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cda2e-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="cda2e-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cda2e-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="cda2e-116">**Дальнейшие действия.**  [После настройки параметра query governor cost limit](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="cda2e-116">**Follow Up:**  [After you configure the query governor cost limit option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="cda2e-117">Перед началом</span><span class="sxs-lookup"><span data-stu-id="cda2e-117">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="cda2e-118">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="cda2e-118">Recommendations</span></span>  
  
-   <span data-ttu-id="cda2e-119">Этот параметр является дополнительным и его следует изменять только опытным администраторам баз данных или сертифицированным техническим специалистам [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cda2e-119">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="cda2e-120">Чтобы изменить значение параметра query governor cost limit для каждого соединения, используйте инструкцию [SET QUERY_GOVERNOR_COST_LIMIT](/sql/t-sql/statements/set-query-governor-cost-limit-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="cda2e-120">To change the value query governor cost limit on a per-connection basis, use the [SET QUERY_GOVERNOR_COST_LIMIT](/sql/t-sql/statements/set-query-governor-cost-limit-transact-sql) statement.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="cda2e-121">безопасность</span><span class="sxs-lookup"><span data-stu-id="cda2e-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="cda2e-122">Permissions</span><span class="sxs-lookup"><span data-stu-id="cda2e-122">Permissions</span></span>  
 <span data-ttu-id="cda2e-123">Разрешения на выполнение хранимой процедуры **sp_configure** без параметров или только с первым параметром по умолчанию предоставляются всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="cda2e-123">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="cda2e-124">Для выполнения процедуры **sp_configure** с обоими параметрами для изменения параметра конфигурации или запуска инструкции RECONFIGURE необходимо иметь разрешение ALTER SETTINGS на уровне сервера.</span><span class="sxs-lookup"><span data-stu-id="cda2e-124">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="cda2e-125">Разрешение ALTER SETTINGS неявным образом предоставлено предопределенным ролям сервера **sysadmin** и **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="cda2e-125">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="cda2e-126">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cda2e-126">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-query-governor-cost-limit-option"></a><span data-ttu-id="cda2e-127">Настройка параметра query governor cost limit</span><span class="sxs-lookup"><span data-stu-id="cda2e-127">To configure the query governor cost limit option</span></span>  
  
1.  <span data-ttu-id="cda2e-128">В обозревателе объектов щелкните правой кнопкой мыши сервер и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="cda2e-128">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="cda2e-129">Перейдите на страницу **Соединения** .</span><span class="sxs-lookup"><span data-stu-id="cda2e-129">Click the **Connections** page.</span></span>  
  
3.  <span data-ttu-id="cda2e-130">Установите или снимите флажок **Использовать регулятор запросов для сокращения времени их выполнения** .</span><span class="sxs-lookup"><span data-stu-id="cda2e-130">Select or clear the **Use query governor to prevent long-running queries** check box.</span></span>  
  
     <span data-ttu-id="cda2e-131">При установке этого флажка введите в поле внизу положительную величину, которую регулятор запросов использует для запрещения выполнения запросов со временем выполнения больше этой величины.</span><span class="sxs-lookup"><span data-stu-id="cda2e-131">If you select this check box, in the box below, enter a positive value, which the query governor uses to disallow execution of any query with a running length exceeding that value.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="cda2e-132">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cda2e-132">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-query-governor-cost-limit-option"></a><span data-ttu-id="cda2e-133">Настройка параметра query governor cost limit</span><span class="sxs-lookup"><span data-stu-id="cda2e-133">To configure the query governor cost limit option</span></span>  
  
1.  <span data-ttu-id="cda2e-134">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cda2e-134">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="cda2e-135">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="cda2e-135">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="cda2e-136">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="cda2e-136">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="cda2e-137">В этом примере описывается использование процедуры [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) для задания значения параметра `query governor cost limit` равным `120` секундам.</span><span class="sxs-lookup"><span data-stu-id="cda2e-137">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `query governor cost limit` option to `120` seconds.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'query governor cost limit', 120 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="cda2e-138">Дополнительные сведения см. в разделе [Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="cda2e-138">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-query-governor-cost-limit-option"></a><a name="FollowUp"></a> <span data-ttu-id="cda2e-139">Дальнейшие действия. После настройки параметра query governor cost limit</span><span class="sxs-lookup"><span data-stu-id="cda2e-139">Follow Up: After you configure the query governor cost limit option</span></span>  
 <span data-ttu-id="cda2e-140">Параметр вступает в силу немедленно, без перезапуска сервера.</span><span class="sxs-lookup"><span data-stu-id="cda2e-140">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cda2e-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="cda2e-141">See Also</span></span>  
 <span data-ttu-id="cda2e-142">[RECONFIGURE (Transact-SQL)](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cda2e-142">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="cda2e-143">[SET QUERY_GOVERNOR_COST_LIMIT (Transact-SQL)](/sql/t-sql/statements/set-query-governor-cost-limit-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cda2e-143">[SET QUERY_GOVERNOR_COST_LIMIT &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-query-governor-cost-limit-transact-sql) </span></span>  
 <span data-ttu-id="cda2e-144">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="cda2e-144">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="cda2e-145">sp_configure (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="cda2e-145">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
