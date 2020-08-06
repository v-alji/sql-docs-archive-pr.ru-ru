---
title: Просмотр или изменение свойств сервера (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- viewing server properties
- server properties [SQL Server]
- displaying server properties
- servers [SQL Server], viewing
ms.assetid: 55f3ac04-5626-4ad2-96bd-a1f1b079659d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 415d4e2d1aaa3166ae4df2dea53b34e064544e06
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729790"
---
# <a name="view-or-change-server-properties-sql-server"></a><span data-ttu-id="c3386-102">Просмотр или изменение свойств сервера (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c3386-102">View or Change Server Properties (SQL Server)</span></span>
  <span data-ttu-id="c3386-103">В этом разделе описывается просмотр и изменение свойств экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]или диспетчера конфигурации SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c3386-103">This topic describes how to view or change the properties of an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Configuration Manager.</span></span>  
  
 <span data-ttu-id="c3386-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="c3386-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c3386-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="c3386-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c3386-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="c3386-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="c3386-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="c3386-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c3386-108">**Для просмотра или изменения свойств сервера используется:**</span><span class="sxs-lookup"><span data-stu-id="c3386-108">**To view or change server properties, using:**</span></span>  
  
     [<span data-ttu-id="c3386-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c3386-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c3386-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c3386-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="c3386-111">Диспетчер конфигурации SQL Server</span><span class="sxs-lookup"><span data-stu-id="c3386-111">SQL Server Configuration Manager</span></span>](#PowerShellProcedure)  
  
-   <span data-ttu-id="c3386-112">**Дальнейшие действия**  [После изменения свойств сервера](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="c3386-112">**Follow Up:**  [After you change server properties](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c3386-113">Перед началом</span><span class="sxs-lookup"><span data-stu-id="c3386-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="c3386-114">Ограничения</span><span class="sxs-lookup"><span data-stu-id="c3386-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="c3386-115">Используя sp_configure, необходимо выполнить инструкцию RECONFIGURE или инструкцию RECONFIGURE WITH OVERRIDE после установки параметра конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c3386-115">When using sp_configure, you must run either RECONFIGURE or RECONFIGURE WITH OVERRIDE after setting a configuration option.</span></span> <span data-ttu-id="c3386-116">Инструкция RECONFIGURE WITH OVERRIDE обычно употребляется для параметров конфигурации, которые должны использоваться с особой осторожностью.</span><span class="sxs-lookup"><span data-stu-id="c3386-116">The RECONFIGURE WITH OVERRIDE statement is usually reserved for configuration options that should be used with extreme caution.</span></span> <span data-ttu-id="c3386-117">Однако инструкция RECONFIGURE WITH OVERRIDE пригодна для всех параметров конфигурации, и ее можно использовать вместо инструкции RECONFIGURE.</span><span class="sxs-lookup"><span data-stu-id="c3386-117">However, RECONFIGURE WITH OVERRIDE works for all configuration options, and you can use it in place of RECONFIGURE.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c3386-118">Инструкция RECONFIGURE выполняется внутри транзакции.</span><span class="sxs-lookup"><span data-stu-id="c3386-118">RECONFIGURE executes within a transaction.</span></span> <span data-ttu-id="c3386-119">Если какая-либо из операций повторной настройки завершится ошибкой, ни одна из операций повторной настройки не возымеет действия.</span><span class="sxs-lookup"><span data-stu-id="c3386-119">If any of the reconfigure operations fail, none of the reconfigure operations will take effect.</span></span>  
  
-   <span data-ttu-id="c3386-120">Некоторые страницы со свойствами предоставляют сведения, полученные через инструментарий управления Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="c3386-120">Some property pages present information obtained via Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="c3386-121">Для отображения этих страниц на компьютере, где работает среда [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], должен быть установлен инструментарий WMI.</span><span class="sxs-lookup"><span data-stu-id="c3386-121">To display those pages, WMI must be installed on the computer running [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c3386-122">безопасность</span><span class="sxs-lookup"><span data-stu-id="c3386-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c3386-123">Permissions</span><span class="sxs-lookup"><span data-stu-id="c3386-123">Permissions</span></span>  
 <span data-ttu-id="c3386-124">Дополнительные сведения см. в статье [Роли уровня сервера](../../relational-databases/security/authentication-access/server-level-roles.md).</span><span class="sxs-lookup"><span data-stu-id="c3386-124">For more information, see [Server-Level Roles](../../relational-databases/security/authentication-access/server-level-roles.md).</span></span>  
  
 <span data-ttu-id="c3386-125">Разрешения на выполнение для без `sp_configure` параметров или только по первому параметру по умолчанию предоставляются всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="c3386-125">Execute permissions on `sp_configure` with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="c3386-126">Чтобы выполнить `sp_configure` с обоими параметрами для изменения параметра конфигурации или выполнения инструкции RECONFIGURE, пользователю необходимо предоставить разрешение ALTER SETTINGS на уровне сервера.</span><span class="sxs-lookup"><span data-stu-id="c3386-126">To execute `sp_configure` with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="c3386-127">Разрешение ALTER SETTINGS неявным образом предоставлено предопределенным ролям сервера **sysadmin** и **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="c3386-127">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c3386-128">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c3386-128">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-change-server-properties"></a><span data-ttu-id="c3386-129">Просмотр или изменение свойств сервера</span><span class="sxs-lookup"><span data-stu-id="c3386-129">To view or change server properties</span></span>  
  
1.  <span data-ttu-id="c3386-130">В обозревателе объектов щелкните правой кнопкой мыши сервер и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="c3386-130">In Object Explorer, right-click a server, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="c3386-131">В диалоговом окне **Свойства сервера** щелкните страницу, чтобы просмотреть или изменить содержащиеся на сервере сведения об этой странице.</span><span class="sxs-lookup"><span data-stu-id="c3386-131">In the **Server Properties** dialog box, click a page to view or change server information about that page.</span></span> <span data-ttu-id="c3386-132">Некоторые свойства доступны только для чтения.</span><span class="sxs-lookup"><span data-stu-id="c3386-132">Some properties are read-only.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c3386-133">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c3386-133">Using Transact-SQL</span></span>  
  
#### <a name="to-view-server-properties-by-using-the-serverproperty-built-in-function"></a><span data-ttu-id="c3386-134">Просмотр свойств сервера с помощью встроенной функции SERVERPROPERTY</span><span class="sxs-lookup"><span data-stu-id="c3386-134">To view server properties by using the SERVERPROPERTY built-in function</span></span>  
  
1.  <span data-ttu-id="c3386-135">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c3386-135">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c3386-136">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="c3386-136">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c3386-137">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="c3386-137">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="c3386-138">В этом примере используется встроенная функция [SERVERPROPERTY](/sql/t-sql/functions/serverproperty-transact-sql) в инструкции `SELECT` для возврата сведений о текущем сервере.</span><span class="sxs-lookup"><span data-stu-id="c3386-138">This example uses the [SERVERPROPERTY](/sql/t-sql/functions/serverproperty-transact-sql) built-in function in a `SELECT` statement to return information about the current server.</span></span> <span data-ttu-id="c3386-139">Этот сценарий полезен, когда на сервере Windows установлено несколько экземпляров [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и клиенту приходится открывать другое соединение с тем же экземпляром, который используется текущим соединением.</span><span class="sxs-lookup"><span data-stu-id="c3386-139">This scenario is useful when there are multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installed on a Windows-based server, and the client must open another connection to the same instance that is used by the current connection.</span></span>  
  
    ```sql  
    SELECT CONVERT( sysname, SERVERPROPERTY('servername'));  
    GO  
    ```  
  
#### <a name="to-view-server-properties-by-using-the-sysservers-catalog-view"></a><span data-ttu-id="c3386-140">Просмотр свойств сервера с помощью представления каталога sys.servers</span><span class="sxs-lookup"><span data-stu-id="c3386-140">To view server properties by using the sys.servers catalog view</span></span>  
  
1.  <span data-ttu-id="c3386-141">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c3386-141">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c3386-142">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="c3386-142">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c3386-143">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="c3386-143">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="c3386-144">В этом примере запрашивается представление каталога [sys.servers](/sql/relational-databases/system-catalog-views/sys-servers-transact-sql) для получения имени (`name`) и идентификатора (`server_id`) текущего сервера, а также имя поставщика OLE DB (`provider`) для подключения к связанному серверу.</span><span class="sxs-lookup"><span data-stu-id="c3386-144">This example queries the [sys.servers](/sql/relational-databases/system-catalog-views/sys-servers-transact-sql) catalog view to return the name (`name`) and ID (`server_id`) of the current server, and the name of the OLE DB provider (`provider`) for connecting to a linked server.</span></span>  
  
    ```sql  
    USE AdventureWorks2012;   
    GO  
    SELECT name, server_id, provider  
    FROM sys.servers ;   
    GO
    ```  
  
#### <a name="to-view-server-properties-by-using-the-sysconfigurations-catalog-view"></a><span data-ttu-id="c3386-145">Просмотр свойств сервера с помощью представления каталога sys.configurations</span><span class="sxs-lookup"><span data-stu-id="c3386-145">To view server properties by using the sys.configurations catalog view</span></span>  
  
1.  <span data-ttu-id="c3386-146">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c3386-146">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c3386-147">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="c3386-147">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c3386-148">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="c3386-148">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="c3386-149">В этом примере запрашивается представление каталога [sys.configurations](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) , чтобы вернуть сведения о каждом параметре конфигурации для текущего сервера.</span><span class="sxs-lookup"><span data-stu-id="c3386-149">This example queries the [sys.configurations](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) catalog view to return information about each server configuration option on the current server.</span></span> <span data-ttu-id="c3386-150">В примере возвращается имя (`name`) и описание (`description`) параметра, а также указывается, является ли параметр дополнительным (`is_advanced`).</span><span class="sxs-lookup"><span data-stu-id="c3386-150">The example returns the name (`name`) and description (`description`) of the option and whether the option is an advanced option (`is_advanced`).</span></span>  
  
    ```sql
    USE AdventureWorks2012;
    GO  
    SELECT name, description, is_advanced  
    FROM sys.configurations ;
    GO
    ```  
  
#### <a name="to-change-a-server-property-by-using-sp_configure"></a><span data-ttu-id="c3386-151">Изменение свойства сервера с помощью процедуры sp_configure</span><span class="sxs-lookup"><span data-stu-id="c3386-151">To change a server property by using sp_configure</span></span>  
  
1.  <span data-ttu-id="c3386-152">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c3386-152">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c3386-153">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="c3386-153">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c3386-154">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="c3386-154">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="c3386-155">В этом примере показано, как изменить свойство сервера с помощью процедуры [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="c3386-155">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to change a server property.</span></span> <span data-ttu-id="c3386-156">В примере значение параметра `fill factor` меняется на `100`.</span><span class="sxs-lookup"><span data-stu-id="c3386-156">The example changes the value of the `fill factor` option to `100`.</span></span> <span data-ttu-id="c3386-157">Чтобы изменение вступило в силу, необходимо перезапустить сервер.</span><span class="sxs-lookup"><span data-stu-id="c3386-157">The server must be restarted before the change can take effect.</span></span>  
  
```sql  
Use AdventureWorks2012;  
GO  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'fill factor', 100;  
GO  
RECONFIGURE;  
GO  
```  
  
 <span data-ttu-id="c3386-158">Дополнительные сведения см. в разделе [Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c3386-158">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="c3386-159">Использование диспетчера конфигурации SQL Server</span><span class="sxs-lookup"><span data-stu-id="c3386-159">Using SQL Server Configuration Manager</span></span>  
 <span data-ttu-id="c3386-160">Некоторые свойства сервера можно просматривать и изменять с помощью диспетчера конфигурации SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c3386-160">Some server properties can be viewed or changed by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="c3386-161">Например, можно просмотреть версию и выпуск экземпляра SQL Server или изменить расположение файлов журнала ошибок.</span><span class="sxs-lookup"><span data-stu-id="c3386-161">For example, you can view the version and edition of the instance of SQL Server, or change the location where error log files are stored.</span></span> <span data-ttu-id="c3386-162">Эти свойства также можно просмотреть, запросив [динамические административные представления и функции динамического управления, относящиеся к серверу](/sql/relational-databases/system-dynamic-management-views/server-related-dynamic-management-views-and-functions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c3386-162">These properties can also be viewed by querying the [Server-Related Dynamic Management Views and Functions](/sql/relational-databases/system-dynamic-management-views/server-related-dynamic-management-views-and-functions-transact-sql).</span></span>  
  
#### <a name="to-view-or-change-server-properties"></a><span data-ttu-id="c3386-163">Просмотр или изменение свойств сервера</span><span class="sxs-lookup"><span data-stu-id="c3386-163">To view or change server properties</span></span>  
  
1.  <span data-ttu-id="c3386-164">В меню **Пуск** последовательно выберите пункты **Все программы**, [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], **Средства настройки**и щелкните **Диспетчер конфигурации SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="c3386-164">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="c3386-165">В **диспетчере конфигурации SQL Server**выберите **Службы SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="c3386-165">In **SQL Server Configuration Manager**, click **SQL Server Services**.</span></span>  
  
3.  <span data-ttu-id="c3386-166">В области сведений щелкните правой кнопкой мыши **SQL Server (\<***instancename***>)** и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="c3386-166">In the details pane, right-click **SQL Server (\<***instancename***>)**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="c3386-167">В диалоговом окне **SQL Server (\<***instancename***>) Свойства** измените свойства сервера на вкладке **Служба** или на вкладке **Дополнительно** и нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="c3386-167">In the **SQL Server (\<***instancename***>) Properties** dialog box, change the server properties on the **Service** tab or the **Advanced** tab, and then click **OK**.</span></span>  
  
##  <a name="follow-up-after-you-change-server-properties"></a><a name="FollowUp"></a><span data-ttu-id="c3386-168">Дальнейшие действия. После изменения свойств сервера</span><span class="sxs-lookup"><span data-stu-id="c3386-168">Follow Up: After you change server properties</span></span>  
 <span data-ttu-id="c3386-169">Для некоторых свойств необходимо перезапустить сервер, чтобы изменения вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="c3386-169">For some properties, the server might have to be restarted before the change can take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3386-170">См. также:</span><span class="sxs-lookup"><span data-stu-id="c3386-170">See Also</span></span>  
 <span data-ttu-id="c3386-171">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c3386-171">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="c3386-172">[Инструкции SET (Transact-SQL)](/sql/t-sql/statements/set-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c3386-172">[SET Statements &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statements-transact-sql) </span></span>  
 <span data-ttu-id="c3386-173">[SERVERPROPERTY (Transact-SQL)](/sql/t-sql/functions/serverproperty-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c3386-173">[SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql) </span></span>  
 <span data-ttu-id="c3386-174">[sp_configure (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c3386-174">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="c3386-175">[RECONFIGURE (Transact-SQL)](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c3386-175">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="c3386-176">[SELECT (Transact-SQL)](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c3386-176">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 <span data-ttu-id="c3386-177">[Настройка инструментария WMI для отображения состояния сервера в инструментальных средствах SQL Server](../../ssms/configure-wmi-to-show-server-status-in-sql-server-tools.md) </span><span class="sxs-lookup"><span data-stu-id="c3386-177">[Configure WMI to Show Server Status in SQL Server Tools](../../ssms/configure-wmi-to-show-server-status-in-sql-server-tools.md) </span></span>  
 <span data-ttu-id="c3386-178">[Диспетчер конфигурации SQL Server](../../relational-databases/sql-server-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="c3386-178">[SQL Server Configuration Manager](../../relational-databases/sql-server-configuration-manager.md) </span></span>  
 <span data-ttu-id="c3386-179">[Функции настройки (Transact-SQL)](/sql/t-sql/functions/configuration-functions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c3386-179">[Configuration Functions &#40;Transact-SQL&#41;](/sql/t-sql/functions/configuration-functions-transact-sql) </span></span>  
 [<span data-ttu-id="c3386-180">Динамические административные представления и функции, связанные с сервером (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c3386-180">Server-Related Dynamic Management Views and Functions &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/server-related-dynamic-management-views-and-functions-transact-sql)  
