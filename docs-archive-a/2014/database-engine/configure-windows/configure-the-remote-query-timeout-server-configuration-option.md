---
title: Настройка параметра конфигурации сервера remote query timeout | Документы Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- time limit for remote queries [SQL Server]
- remote query timeout option
ms.assetid: 888c8448-933b-41e3-8aa1-c206bc0cdb78
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 74f82d621d7f0375a6a3ca604abba00f83fc6024
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740430"
---
# <a name="configure-the-remote-query-timeout-server-configuration-option"></a><span data-ttu-id="99011-102">Настройка параметра конфигурации сервера remote query timeout</span><span class="sxs-lookup"><span data-stu-id="99011-102">Configure the remote query timeout Server Configuration Option</span></span>
  <span data-ttu-id="99011-103">В этом разделе описываются способы настройки параметра конфигурации сервера **remote query timeout** в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="99011-103">This topic describes how to configure the **remote query timeout** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="99011-104">Параметр **remote query timeout** позволяет задать время ожидания [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (в секундах), в течение которого может выполняться удаленная операция. Значение по умолчанию для этого параметра составляет 600, и это означает ожидание в течение 10 минут.</span><span class="sxs-lookup"><span data-stu-id="99011-104">The **remote query timeout** option specifies how long, in seconds, a remote operation can take before [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] times out. The default value for this option is 600, which allows a 10-minute wait.</span></span> <span data-ttu-id="99011-105">Это значение применяется для исходящих подключений, инициированных компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)] как удаленный запрос.</span><span class="sxs-lookup"><span data-stu-id="99011-105">This value applies to an outgoing connection initiated by the [!INCLUDE[ssDE](../../includes/ssde-md.md)] as a remote query.</span></span> <span data-ttu-id="99011-106">Это значение не влияет на запросы, получаемые ядром СУБД [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="99011-106">This value has no effect on queries received by the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="99011-107">Чтобы отключить время ожидания, установите значение 0.</span><span class="sxs-lookup"><span data-stu-id="99011-107">To disable the time-out, set the value to 0.</span></span> <span data-ttu-id="99011-108">Запрос будет ожидать до момента его завершения.</span><span class="sxs-lookup"><span data-stu-id="99011-108">A query will wait until it completes.</span></span>  
  
 <span data-ttu-id="99011-109">Для разнородных запросов параметр **remote query timeout** задает время ожидания удаленным поставщикам в секундах (инициализированное в объекте команд с помощью свойства набора строк DBPROP_COMMANDTIMEOUT) результирующих наборов. Это значение также используется, чтобы задать DBPROP_GENERALTIMEOUT, если это поддерживается удаленным поставщиком.</span><span class="sxs-lookup"><span data-stu-id="99011-109">For heterogeneous queries, **remote query timeout** specifies the number of seconds (initialized in the command object using the DBPROP_COMMANDTIMEOUT rowset property) that a remote provider should wait for result sets before the query times out. This value is also used to set DBPROP_GENERALTIMEOUT if supported by the remote provider.</span></span> <span data-ttu-id="99011-110">Это приведет к тому, что время ожидания других операций станет равно указанному числу секунд.</span><span class="sxs-lookup"><span data-stu-id="99011-110">This will cause any other operations to time out after the specified number of seconds.</span></span>  
  
 <span data-ttu-id="99011-111">Для удаленных хранимых процедур параметр **remote query timeout** задает число секунд, которое должно пройти после отправки удаленной инструкции `EXEC` перед тем, как истечет время ожидания удаленной хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="99011-111">For remote stored procedures, **remote query timeout** specifies the number of seconds that must elapse after sending a remote `EXEC` statement before the remote stored procedure times out.</span></span>  
  
 <span data-ttu-id="99011-112">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="99011-112">**In This Topic**</span></span>  
  
-   <span data-ttu-id="99011-113">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="99011-113">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="99011-114">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="99011-114">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="99011-115">Безопасность</span><span class="sxs-lookup"><span data-stu-id="99011-115">Security</span></span>](#Security)  
  
-   <span data-ttu-id="99011-116">**Настройка параметра времени ожидания удаленного запроса с помощью следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="99011-116">**To configure the remote query timeout option, using:**</span></span>  
  
     [<span data-ttu-id="99011-117">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="99011-117">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="99011-118">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="99011-118">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="99011-119">**Дальнейшие действия.**  [После настройки параметра remote query timeout](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="99011-119">**Follow Up:**  [After you configure the remote query timeout option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="99011-120">Перед началом</span><span class="sxs-lookup"><span data-stu-id="99011-120">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="99011-121">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="99011-121">Prerequisites</span></span>  
  
-   <span data-ttu-id="99011-122">Это значение можно установить только при разрешенных соединениях с удаленными серверами.</span><span class="sxs-lookup"><span data-stu-id="99011-122">Remote server connections must be allowed before this value can be set.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="99011-123">безопасность</span><span class="sxs-lookup"><span data-stu-id="99011-123">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="99011-124">Permissions</span><span class="sxs-lookup"><span data-stu-id="99011-124">Permissions</span></span>  
 <span data-ttu-id="99011-125">Разрешения на выполнение хранимой процедуры **sp_configure** без параметров или только с первым параметром по умолчанию предоставляются всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="99011-125">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="99011-126">Для выполнения процедуры **sp_configure** с обоими параметрами для изменения параметра конфигурации или запуска инструкции RECONFIGURE необходимо иметь разрешение ALTER SETTINGS на уровне сервера.</span><span class="sxs-lookup"><span data-stu-id="99011-126">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="99011-127">Разрешение ALTER SETTINGS неявным образом предоставлено предопределенным ролям сервера **sysadmin** и **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="99011-127">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="99011-128">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="99011-128">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-remote-query-timeout-option"></a><span data-ttu-id="99011-129">Настройка параметра время ожидания удаленного запроса</span><span class="sxs-lookup"><span data-stu-id="99011-129">To configure the remote query timeout option</span></span>  
  
1.  <span data-ttu-id="99011-130">В обозревателе объектов щелкните правой кнопкой мыши сервер и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="99011-130">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="99011-131">Выберите узел **Соединения** .</span><span class="sxs-lookup"><span data-stu-id="99011-131">Click the **Connections** node.</span></span>  
  
3.  <span data-ttu-id="99011-132">В поле **Подключения удаленного сервера**в области **Время ожидания удаленного запроса** введите или выберите значение от 0 до 2 147 483 647, соответствующее максимальному времени ожидания [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (в секундах).</span><span class="sxs-lookup"><span data-stu-id="99011-132">Under **Remote server connections**, in the **Remote query timeout** box, type or select a value from 0 through 2,147,483,647 to set the maximum number seconds for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to wait before timing out.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="99011-133">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="99011-133">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-remote-query-timeout-option"></a><span data-ttu-id="99011-134">Настройка параметра время ожидания удаленного запроса</span><span class="sxs-lookup"><span data-stu-id="99011-134">To configure the remote query timeout option</span></span>  
  
1.  <span data-ttu-id="99011-135">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="99011-135">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="99011-136">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="99011-136">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="99011-137">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="99011-137">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="99011-138">В этом примере описывается использование хранимой процедуры [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) для задания значения параметра `remote query timeout` равным `0` сек., чтобы отключить время ожидания.</span><span class="sxs-lookup"><span data-stu-id="99011-138">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `remote query timeout` option to `0` to disable the time-out.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'remote query timeout', 0 ;  
GO  
RECONFIGURE ;  
GO  
  
```  
  
 <span data-ttu-id="99011-139">Дополнительные сведения см. в разделе [Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="99011-139">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-remote-query-timeout-option"></a><a name="FollowUp"></a> <span data-ttu-id="99011-140">Дальнейшие действия. После настройки параметра remote query timeout</span><span class="sxs-lookup"><span data-stu-id="99011-140">Follow Up: After you configure the remote query timeout option</span></span>  
 <span data-ttu-id="99011-141">Параметр вступает в силу немедленно, без перезапуска сервера.</span><span class="sxs-lookup"><span data-stu-id="99011-141">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99011-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="99011-142">See Also</span></span>  
 <span data-ttu-id="99011-143">[RECONFIGURE (Transact-SQL)](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="99011-143">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="99011-144">[Свойства и поведение наборов строк](../../relational-databases/native-client-ole-db-rowsets/rowset-properties-and-behaviors.md) </span><span class="sxs-lookup"><span data-stu-id="99011-144">[Rowset Properties and Behaviors](../../relational-databases/native-client-ole-db-rowsets/rowset-properties-and-behaviors.md) </span></span>  
 <span data-ttu-id="99011-145">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="99011-145">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="99011-146">sp_configure (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="99011-146">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
