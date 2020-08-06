---
title: Просмотр и настройка параметров соединения с удаленным сервером (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- remote servers [SQL Server], connection options
- servers [SQL Server], remote
- connections [SQL Server], remote servers
ms.assetid: 356d3e6b-8514-4bd2-a683-9de147949b2b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 73fe5e484d62cde025d1a560937e8cbcf5ec361d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729786"
---
# <a name="view-or-configure-remote-server-connection-options-sql-server"></a><span data-ttu-id="72166-102">Просмотр и настройка параметров соединения с удаленным сервером (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="72166-102">View or Configure Remote Server Connection Options (SQL Server)</span></span>
  <span data-ttu-id="72166-103">В этом разделе описываются способы просмотра и настройки параметров подключения к удаленному серверу на уровне сервера в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72166-103">This topic describes how to view or configure remote server connection options at the server level in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="72166-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="72166-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="72166-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="72166-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="72166-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="72166-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="72166-107">**Просмотр и настройка параметров соединения с удаленным сервером с использованием**</span><span class="sxs-lookup"><span data-stu-id="72166-107">**To view or configure remote server connection options, using:**</span></span>  
  
     [<span data-ttu-id="72166-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="72166-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="72166-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="72166-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="72166-110">**Дальнейшие действия.**  [После настройки параметров соединения с удаленным сервером](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="72166-110">**Follow Up:**  [After you configure remote server connection options](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="72166-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="72166-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="72166-112">безопасность</span><span class="sxs-lookup"><span data-stu-id="72166-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="72166-113">Permissions</span><span class="sxs-lookup"><span data-stu-id="72166-113">Permissions</span></span>  
 <span data-ttu-id="72166-114">Для выполнения хранимой процедуры **sp_serveroption** необходимо разрешение ALTER ANY LINKED SERVER на сервер.</span><span class="sxs-lookup"><span data-stu-id="72166-114">Executing **sp_serveroption** requires ALTER ANY LINKED SERVER permission on the server.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="72166-115">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="72166-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-configure-remote-server-connection-options"></a><span data-ttu-id="72166-116">Просмотр и настройка параметров соединения с удаленным сервером</span><span class="sxs-lookup"><span data-stu-id="72166-116">To view or configure remote server connection options</span></span>  
  
1.  <span data-ttu-id="72166-117">В обозревателе объектов щелкните правой кнопкой мыши сервер и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="72166-117">In Object Explorer, right-click a server, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="72166-118">В диалоговом окне **Свойства SQL Server — \<***server_name***>** щелкните **Соединения**.</span><span class="sxs-lookup"><span data-stu-id="72166-118">In the **SQL Server Properties - \<***server_name***>** dialog box, click **Connections**.</span></span>  
  
3.  <span data-ttu-id="72166-119">На странице **Соединения** просмотрите параметры **Соединения с удаленными серверами** и измените их при необходимости.</span><span class="sxs-lookup"><span data-stu-id="72166-119">On the **Connections** page, review the **Remote server connections** settings, and modify them if necessary.</span></span>  
  
4.  <span data-ttu-id="72166-120">Повторите шаги 1-3 на другом сервере данной пары серверов.</span><span class="sxs-lookup"><span data-stu-id="72166-120">Repeat steps 1 through 3 on the other server of the remote server pair.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="72166-121">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="72166-121">Using Transact-SQL</span></span>  
  
#### <a name="to-view-remote-server-connection-options"></a><span data-ttu-id="72166-122">Просмотр параметров соединения удаленным сервером</span><span class="sxs-lookup"><span data-stu-id="72166-122">To view remote server connection options</span></span>  
  
1.  <span data-ttu-id="72166-123">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72166-123">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="72166-124">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="72166-124">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="72166-125">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="72166-125">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="72166-126">В этом примере хранимая процедура [sp_helpserver](/sql/relational-databases/system-stored-procedures/sp-helpserver-transact-sql) используется для возврата сведений обо всех удаленных серверах.</span><span class="sxs-lookup"><span data-stu-id="72166-126">This example uses [sp_helpserver](/sql/relational-databases/system-stored-procedures/sp-helpserver-transact-sql) to return information about all remote servers.</span></span>  
  
```sql  
USE master;  
GO  
EXEC sp_helpserver ;  
```  
  
#### <a name="to-configure-remote-server-connection-options"></a><span data-ttu-id="72166-127">Настройка параметров соединения с удаленным сервером</span><span class="sxs-lookup"><span data-stu-id="72166-127">To configure remote server connection options</span></span>  
  
1.  <span data-ttu-id="72166-128">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72166-128">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="72166-129">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="72166-129">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="72166-130">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="72166-130">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="72166-131">В этом примере показано использование хранимой процедуры [sp_configure](/sql/relational-databases/system-stored-procedures/sp-serveroption-transact-sql) для настройки удаленного сервера.</span><span class="sxs-lookup"><span data-stu-id="72166-131">This example shows how to use [sp_serveroption](/sql/relational-databases/system-stored-procedures/sp-serveroption-transact-sql) to configure a remote server.</span></span> <span data-ttu-id="72166-132">В следующем примере удаленный сервер настраивается в соответствии с другим экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], `SEATTLE3`, для совместимости параметров сортировки с локальным экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72166-132">The example configures a remote server corresponding to another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], `SEATTLE3`, to be collation compatible with the local instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
```sql  
USE master;  
EXEC sp_serveroption 'SEATTLE3', 'collation compatible', 'true';  
```  
  
##  <a name="follow-up-after-you-configure-remote-server-connection-options"></a><a name="FollowUp"></a> <span data-ttu-id="72166-133">Дальнейшие действия. После настройки параметров соединения с удаленным сервером</span><span class="sxs-lookup"><span data-stu-id="72166-133">Follow Up: After you configure remote server connection options</span></span>  
 <span data-ttu-id="72166-134">Чтобы изменения вступили в силу, необходимо остановить и перезапустить удаленный сервер.</span><span class="sxs-lookup"><span data-stu-id="72166-134">The remote server must be stopped and restarted before the setting can take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72166-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="72166-135">See Also</span></span>  
 <span data-ttu-id="72166-136">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="72166-136">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="72166-137">[Удаленные серверы](remote-servers.md) </span><span class="sxs-lookup"><span data-stu-id="72166-137">[Remote Servers](remote-servers.md) </span></span>  
 <span data-ttu-id="72166-138">[Связанные серверы (компонент Database Engine)](../../relational-databases/linked-servers/linked-servers-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="72166-138">[Linked Servers &#40;Database Engine&#41;](../../relational-databases/linked-servers/linked-servers-database-engine.md) </span></span>  
 <span data-ttu-id="72166-139">[sp_linkedservers (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-linkedservers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="72166-139">[sp_linkedservers &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-linkedservers-transact-sql) </span></span>  
 <span data-ttu-id="72166-140">[sp_helpserver (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-helpserver-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="72166-140">[sp_helpserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpserver-transact-sql) </span></span>  
 [<span data-ttu-id="72166-141">sp_serveroption (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="72166-141">sp_serveroption &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-serveroption-transact-sql)  
  
  
