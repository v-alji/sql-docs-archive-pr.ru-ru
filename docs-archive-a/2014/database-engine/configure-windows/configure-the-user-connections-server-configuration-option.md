---
title: Настройка параметра конфигурации сервера user connections | Документы Майкрософт
ms.custom: ''
ms.date: 12/02/2015
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- simultaneous connections [SQL Server]
- user connections option [SQL Server]
- users [SQL Server], simultaneous connections
- maximum number of simultaneous user connections
- connections [SQL Server], simultaneous
ms.assetid: 53beee6e-59fe-4276-9abb-8f1cec2a3508
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 68fbb4a17de131c128b5b1bb7cfb35a33b9d0037
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655353"
---
# <a name="configure-the-user-connections-server-configuration-option"></a><span data-ttu-id="ccc29-102">Настройка параметра конфигурации сервера user connections</span><span class="sxs-lookup"><span data-stu-id="ccc29-102">Configure the user connections Server Configuration Option</span></span>
  <span data-ttu-id="ccc29-103">В этом разделе описывается задание параметра конфигурации сервера **user connections** в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ccc29-103">This topic describes how to set the **user connections** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="ccc29-104">Параметр **user connections** указывает максимальное количество одновременных пользовательских соединений, допустимых в экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ccc29-104">The **user connections** option specifies the maximum number of simultaneous user connections that are allowed on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ccc29-105">Допустимое количество пользовательских соединений также зависит от используемой версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и возможностей приложений или оборудования.</span><span class="sxs-lookup"><span data-stu-id="ccc29-105">The actual number of user connections allowed also depends on the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you are using, and also the limits of your application or applications and hardware.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ccc29-106">допускает максимально 32 767 одновременных соединений пользователей.</span><span class="sxs-lookup"><span data-stu-id="ccc29-106">allows a maximum of 32,767 user connections.</span></span> <span data-ttu-id="ccc29-107">Поскольку параметр **user connections** является динамическим (самонастраиваемым), [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] автоматически регулирует максимальное число пользовательских соединений по мере необходимости, до достижения максимального значения.</span><span class="sxs-lookup"><span data-stu-id="ccc29-107">Because **user connections** is a dynamic (self-configuring) option, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] adjusts the maximum number of user connections automatically as needed, up to the maximum value allowable.</span></span> <span data-ttu-id="ccc29-108">Например, если к серверу подключилось 10 пользователей, будет выделено 10 объектов пользовательских соединений.</span><span class="sxs-lookup"><span data-stu-id="ccc29-108">For example, if only 10 users are logged in, 10 user connection objects are allocated.</span></span> <span data-ttu-id="ccc29-109">В большинстве случаев не требуется изменять значение этого параметра.</span><span class="sxs-lookup"><span data-stu-id="ccc29-109">In most cases, you do not have to change the value for this option.</span></span> <span data-ttu-id="ccc29-110">По умолчанию его значение равно нулю, то есть разрешено  максимальное число соединений (32 767).</span><span class="sxs-lookup"><span data-stu-id="ccc29-110">The default is 0, which means that the maximum (32,767) user connections are allowed.</span></span>  
  
 <span data-ttu-id="ccc29-111">Чтобы определить максимальное количество пользовательских соединений, допустимых в системе, можно выполнить команду [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) или воспользоваться запросом представления каталога [sys.configuration](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="ccc29-111">To determine the maximum number of user connections that your system allows, you can execute [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) or query the [sys.configuration](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) catalog view.</span></span>  
  
 <span data-ttu-id="ccc29-112">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="ccc29-112">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ccc29-113">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="ccc29-113">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ccc29-114">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="ccc29-114">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="ccc29-115">Безопасность</span><span class="sxs-lookup"><span data-stu-id="ccc29-115">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ccc29-116">**Настройка параметра пользовательских соединений с помощью следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="ccc29-116">**To configure the user connections option, using:**</span></span>  
  
     [<span data-ttu-id="ccc29-117">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ccc29-117">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ccc29-118">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ccc29-118">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="ccc29-119">**Дальнейшие действия.**  [После настройки параметра user connections](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="ccc29-119">**Follow Up:**  [After you configure the user connections option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ccc29-120">Перед началом</span><span class="sxs-lookup"><span data-stu-id="ccc29-120">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="ccc29-121">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="ccc29-121">Recommendations</span></span>  
  
-   <span data-ttu-id="ccc29-122">Этот параметр является дополнительным и его следует изменять только опытным администраторам баз данных или сертифицированным техническим специалистам [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ccc29-122">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="ccc29-123">Параметр **user connections** позволяет избежать перегрузки сервера в ситуации, когда слишком много пользователей одновременно пытаются соединиться с системой.</span><span class="sxs-lookup"><span data-stu-id="ccc29-123">Using the **user connections** option helps avoid overloading the server with too many concurrent connections.</span></span> <span data-ttu-id="ccc29-124">При оценке количества соединений следует учитывать возможности системы и требования пользователей.</span><span class="sxs-lookup"><span data-stu-id="ccc29-124">You can estimate the number of connections based on system and user requirements.</span></span> <span data-ttu-id="ccc29-125">Например, в системе с большим количеством пользователей обычно не всем из них требуется уникальное соединение.</span><span class="sxs-lookup"><span data-stu-id="ccc29-125">For example, on a system with many users, each user would not usually require a unique connection.</span></span> <span data-ttu-id="ccc29-126">Несколько пользователей могут совместно использовать одно соединение.</span><span class="sxs-lookup"><span data-stu-id="ccc29-126">Connections can be shared among users.</span></span> <span data-ttu-id="ccc29-127">Приложениям OLE DB требуется отдельное соединение для каждого открытого объекта соединения, приложениям ODBC — соединение для каждого активного дескриптора соединения в приложении и, наконец, приложениям, работающим с DB-Library, — соединение для каждого запущенного процесса, вызывающего функцию **dbopen** из DB-Library.</span><span class="sxs-lookup"><span data-stu-id="ccc29-127">Users running OLE DB applications need a connection for each open connection object, users running Open Database Connectivity (ODBC) applications need a connection for each active connection handle in the application, and users running DB-Library applications need one connection for each process started that calls the DB-Library **dbopen** function.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="ccc29-128">Если параметр необходимо использовать, не устанавливайте слишком большое значение, поскольку каждое соединение требует затрат независимо от того, используется оно или нет.</span><span class="sxs-lookup"><span data-stu-id="ccc29-128">If you must use this option, do not set the value too high, because each connection has overhead regardless of whether the connection is being used.</span></span> <span data-ttu-id="ccc29-129">При превышении максимального количества пользовательских соединений отображается сообщение об ошибке и к серверу нельзя подключиться, пока соединения не станут доступными.</span><span class="sxs-lookup"><span data-stu-id="ccc29-129">If you exceed the maximum number of user connections, you receive an error message and are not able to connect until another connection becomes available.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ccc29-130">безопасность</span><span class="sxs-lookup"><span data-stu-id="ccc29-130">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ccc29-131">Permissions</span><span class="sxs-lookup"><span data-stu-id="ccc29-131">Permissions</span></span>  
 <span data-ttu-id="ccc29-132">Разрешения на выполнение хранимой процедуры **sp_configure** без параметров или только с первым параметром по умолчанию предоставляются всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="ccc29-132">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="ccc29-133">Для выполнения процедуры **sp_configure** с обоими параметрами для изменения параметра конфигурации или запуска инструкции RECONFIGURE необходимо иметь разрешение ALTER SETTINGS на уровне сервера.</span><span class="sxs-lookup"><span data-stu-id="ccc29-133">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="ccc29-134">Разрешение ALTER SETTINGS неявным образом предоставлено предопределенным ролям сервера **sysadmin** и **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="ccc29-134">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ccc29-135">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ccc29-135">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-user-connections-option"></a><span data-ttu-id="ccc29-136">Настройка параметра пользовательских соединений</span><span class="sxs-lookup"><span data-stu-id="ccc29-136">To configure the user connections option</span></span>  
  
1.  <span data-ttu-id="ccc29-137">В обозревателе объектов щелкните правой кнопкой мыши сервер и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="ccc29-137">In Object Explorer, right-click a server and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="ccc29-138">Выберите узел **Соединения** .</span><span class="sxs-lookup"><span data-stu-id="ccc29-138">Click the **Connections** node.</span></span>  
  
3.  <span data-ttu-id="ccc29-139">В разделе **Соединения**в поле **Максимальное число одновременных соединений** введите или выберите значение от 0 до 32 767, чтобы задать максимальное число пользователей, которые смогут одновременно подключиться к экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ccc29-139">Under **Connections**, in the **Max number of concurrent connections** box, type or select a value from 0 through 32767 to set the maximum number of users that are allowed to connect simultaneously to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
4.  <span data-ttu-id="ccc29-140">Перезапустите [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ccc29-140">Restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ccc29-141">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ccc29-141">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-user-connections-option"></a><span data-ttu-id="ccc29-142">Настройка параметра пользовательских соединений</span><span class="sxs-lookup"><span data-stu-id="ccc29-142">To configure the user connections option</span></span>  
  
1.  <span data-ttu-id="ccc29-143">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ccc29-143">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ccc29-144">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="ccc29-144">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ccc29-145">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="ccc29-145">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="ccc29-146">В этом примере показано использование процедуры [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) для задания значения параметра `user connections` равным `325` пользователям.</span><span class="sxs-lookup"><span data-stu-id="ccc29-146">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to configure the value of the `user connections` option to `325` users.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'user connections', 325 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="ccc29-147">Дополнительные сведения см. в разделе [Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ccc29-147">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-user-connections-option"></a><a name="FollowUp"></a> <span data-ttu-id="ccc29-148">Дальнейшие действия. После настройки параметра user connections</span><span class="sxs-lookup"><span data-stu-id="ccc29-148">Follow Up: After you configure the user connections option</span></span>  
 <span data-ttu-id="ccc29-149">Чтобы изменения вступили в силу, необходимо перезапустить сервер.</span><span class="sxs-lookup"><span data-stu-id="ccc29-149">The server must be restarted before the setting can take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccc29-150">См. также:</span><span class="sxs-lookup"><span data-stu-id="ccc29-150">See Also</span></span>  
 <span data-ttu-id="ccc29-151">[RECONFIGURE (Transact-SQL)](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ccc29-151">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="ccc29-152">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ccc29-152">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="ccc29-153">sp_configure (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="ccc29-153">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
