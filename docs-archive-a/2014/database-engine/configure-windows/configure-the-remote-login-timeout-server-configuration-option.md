---
title: Настройка параметра конфигурации сервера remote login timeout | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- remote login timeout option
ms.assetid: 077adebe-0e3f-42a5-a75e-5e6d04847e2b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 58b3405f9b0e51bd43edcaa31e84c8ebbcc48547
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655944"
---
# <a name="configure-the-remote-login-timeout-server-configuration-option"></a><span data-ttu-id="69c03-102">Настройка параметра конфигурации сервера remote login timeout</span><span class="sxs-lookup"><span data-stu-id="69c03-102">Configure the remote login timeout Server Configuration Option</span></span>
  <span data-ttu-id="69c03-103">В этом разделе описываются способы настройки параметра конфигурации сервера **remote login timeout** в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69c03-103">This topic describes how to configure the **remote login timeout** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="69c03-104">Параметр **remote login timeout** указывает время ожидания в секундах до возврата после неуспешной попытки входа на удаленный сервер.</span><span class="sxs-lookup"><span data-stu-id="69c03-104">The **remote login timeout** option specifies the number of seconds to wait before returning from a failed attempt to log in to a remote server.</span></span> <span data-ttu-id="69c03-105">Например, при попытке входа на удаленный сервер, который вышел из строя, не придется ждать неопределенно долго, пока компьютер не прекратит попытки войти на сервер. Это обеспечивается заданием параметра **remote login timeout** .</span><span class="sxs-lookup"><span data-stu-id="69c03-105">For example, if you are trying to log in to a remote server and that server is down, **remote login timeout** helps make sure that you do not have to wait indefinitely before your computer stops trying to log in.</span></span> <span data-ttu-id="69c03-106">Значение по умолчанию для данного параметра равно 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="69c03-106">The default value for this option is 10 seconds.</span></span> <span data-ttu-id="69c03-107">Значение 0 означает бесконечное ожидание.</span><span class="sxs-lookup"><span data-stu-id="69c03-107">A value of 0 allows for an infinite wait.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="69c03-108">В [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]значение по умолчанию для данного параметра составляет 20 секунд.</span><span class="sxs-lookup"><span data-stu-id="69c03-108">The default value for this option is 20 seconds in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
 <span data-ttu-id="69c03-109">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="69c03-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="69c03-110">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="69c03-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="69c03-111">Ограничения</span><span class="sxs-lookup"><span data-stu-id="69c03-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="69c03-112">Безопасность</span><span class="sxs-lookup"><span data-stu-id="69c03-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="69c03-113">**Настройка параметра remote login timeout с помощью следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="69c03-113">**To configure the remote login timeout option, using:**</span></span>  
  
     [<span data-ttu-id="69c03-114">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="69c03-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="69c03-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="69c03-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="69c03-116">**Дальнейшие действия.**  [После настройки параметра remote login timeout](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="69c03-116">**Follow Up:**  [After you configure the remote login timeout option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="69c03-117">Перед началом</span><span class="sxs-lookup"><span data-stu-id="69c03-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="69c03-118">Ограничения</span><span class="sxs-lookup"><span data-stu-id="69c03-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="69c03-119">Параметр **remote login timeout** влияет на подключения к поставщикам OLE DB, выполняемые для разнородных запросов.</span><span class="sxs-lookup"><span data-stu-id="69c03-119">The **remote login timeout** option affects connections to OLE DB providers made for heterogeneous queries.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="69c03-120">безопасность</span><span class="sxs-lookup"><span data-stu-id="69c03-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="69c03-121">Permissions</span><span class="sxs-lookup"><span data-stu-id="69c03-121">Permissions</span></span>  
 <span data-ttu-id="69c03-122">Разрешения на выполнение хранимой процедуры **sp_configure** без параметров или только с первым параметром по умолчанию предоставляются всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="69c03-122">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="69c03-123">Для выполнения процедуры **sp_configure** с обоими параметрами для изменения параметра конфигурации или запуска инструкции RECONFIGURE необходимо иметь разрешение ALTER SETTINGS на уровне сервера.</span><span class="sxs-lookup"><span data-stu-id="69c03-123">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="69c03-124">Разрешение ALTER SETTINGS неявным образом предоставлено предопределенным ролям сервера **sysadmin** и **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="69c03-124">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="69c03-125">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="69c03-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-remote-login-timeout-option"></a><span data-ttu-id="69c03-126">Настройка параметра remote login timeout</span><span class="sxs-lookup"><span data-stu-id="69c03-126">To configure the remote login timeout option</span></span>  
  
1.  <span data-ttu-id="69c03-127">В обозревателе объектов щелкните правой кнопкой мыши сервер и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="69c03-127">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="69c03-128">Щелкните узел **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="69c03-128">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="69c03-129">В разделе **Сеть**выберите значение для поля **Время ожидания удаленного входа** .</span><span class="sxs-lookup"><span data-stu-id="69c03-129">Under **Network**, select a value for the **Remote Login Timeout** box.</span></span>  
  
     <span data-ttu-id="69c03-130">Используйте параметр **remote login timeout** , чтобы указать количество секунд ожидания перед возвратом сообщения о неудачной попытке входа на удаленный сервер.</span><span class="sxs-lookup"><span data-stu-id="69c03-130">Use the **remote login timeout** option to specify the number of seconds to wait before returning from a failed remote login attempt.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="69c03-131">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="69c03-131">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-remote-login-timeout-option"></a><span data-ttu-id="69c03-132">Настройка параметра remote login timeout</span><span class="sxs-lookup"><span data-stu-id="69c03-132">To configure the remote login timeout option</span></span>  
  
1.  <span data-ttu-id="69c03-133">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69c03-133">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="69c03-134">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="69c03-134">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="69c03-135">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="69c03-135">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="69c03-136">В этом примере описывается использование процедуры [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) для задания значения параметра `remote login timeout` равным `35` секундам.</span><span class="sxs-lookup"><span data-stu-id="69c03-136">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `remote login timeout` option to `35` seconds.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'remote login timeout', 35 ;  
GO  
RECONFIGURE ;  
GO  
  
```  
  
 <span data-ttu-id="69c03-137">Дополнительные сведения см. в разделе [Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="69c03-137">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-remote-login-timeout-option"></a><a name="FollowUp"></a> <span data-ttu-id="69c03-138">Дальнейшие действия. После настройки параметра remote login timeout</span><span class="sxs-lookup"><span data-stu-id="69c03-138">Follow Up: After you configure the remote login timeout option</span></span>  
 <span data-ttu-id="69c03-139">Параметр вступает в силу немедленно, без перезапуска сервера.</span><span class="sxs-lookup"><span data-stu-id="69c03-139">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69c03-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="69c03-140">See Also</span></span>  
 <span data-ttu-id="69c03-141">[RECONFIGURE (Transact-SQL)](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="69c03-141">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="69c03-142">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="69c03-142">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="69c03-143">sp_configure (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="69c03-143">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
