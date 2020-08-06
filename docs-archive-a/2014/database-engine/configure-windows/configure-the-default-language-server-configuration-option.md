---
title: Настройка параметра конфигурации сервера "default language" | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- default language option
ms.assetid: c08c26d8-5a62-487e-a4ee-4c529e4f9287
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b0e62fef112dad2c6c307946bc720adf1f14d82b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750151"
---
# <a name="configure-the-default-language-server-configuration-option"></a><span data-ttu-id="f5190-102">Настройка параметра конфигурации сервера «язык по умолчанию»</span><span class="sxs-lookup"><span data-stu-id="f5190-102">Configure the default language Server Configuration Option</span></span>
  <span data-ttu-id="f5190-103">В этом разделе описываются способы настройки параметра конфигурации сервера **default language** в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5190-103">This topic describes how to configure the **default language** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="f5190-104">Параметр **default language** определяет язык по умолчанию для всех вновь создаваемых имен входа.</span><span class="sxs-lookup"><span data-stu-id="f5190-104">The **default language** option specifies the default language for all newly created logins.</span></span> <span data-ttu-id="f5190-105">Чтобы задать язык по умолчанию, укажите значение **langid** нужного языка.</span><span class="sxs-lookup"><span data-stu-id="f5190-105">To set default language, specify the **langid** value of the language you want.</span></span> <span data-ttu-id="f5190-106">Значение параметра **langid** может быть получено путем выполнения запроса к представлению совместимости **sys.syslanguages** .</span><span class="sxs-lookup"><span data-stu-id="f5190-106">The **langid** value can be obtained by querying the **sys.syslanguages** compatibility view.</span></span>  
  
 <span data-ttu-id="f5190-107">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="f5190-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f5190-108">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="f5190-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f5190-109">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="f5190-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="f5190-110">Безопасность</span><span class="sxs-lookup"><span data-stu-id="f5190-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f5190-111">**Настройка параметра default language с помощью различных средств.**</span><span class="sxs-lookup"><span data-stu-id="f5190-111">**To configure the default language option, using:**</span></span>  
  
     [<span data-ttu-id="f5190-112">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f5190-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="f5190-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f5190-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="f5190-114">**Дальнейшие действия.**  [После настройки параметра default language](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="f5190-114">**Follow Up:**  [After you configure the default language option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f5190-115">Перед началом</span><span class="sxs-lookup"><span data-stu-id="f5190-115">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="f5190-116">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="f5190-116">Recommendations</span></span>  
  
-   <span data-ttu-id="f5190-117">Язык по умолчанию для имени входа может быть переопределен при помощи инструкции CREATE LOGIN или ALTER LOGIN.</span><span class="sxs-lookup"><span data-stu-id="f5190-117">The default language for a login can be overridden by using CREATE LOGIN or ALTER LOGIN.</span></span> <span data-ttu-id="f5190-118">Для сеанса языком по умолчанию является язык имени входа, используемого этим сеансом, если только он не был переопределен в сеансе при помощи интерфейса ODBC или OLE DB.</span><span class="sxs-lookup"><span data-stu-id="f5190-118">The default language for a session is the language for that session's login, unless overridden on a per-session basis by using the Open Database Connectivity (ODBC) or OLE DB APIs.</span></span> <span data-ttu-id="f5190-119">Следует отметить, что параметру **default language** может быть присвоен только идентификатор языка, определенный в представлении совместимости [sys.syslanguages](/sql/relational-databases/system-compatibility-views/sys-syslanguages-transact-sql) (0–32).</span><span class="sxs-lookup"><span data-stu-id="f5190-119">Note that you can only set the **default language** option to a language ID defined in [sys.syslanguages](/sql/relational-databases/system-compatibility-views/sys-syslanguages-transact-sql) (0-32).</span></span> <span data-ttu-id="f5190-120">При использовании автономных баз данных для базы данных можно задать язык по умолчанию с помощью инструкции CREATE DATABASE или ALTER DATABASE, а для пользователей автономной базы данных можно использовать инструкцию CREATE USER или ALTER USER.</span><span class="sxs-lookup"><span data-stu-id="f5190-120">When you are using contained databases, a default language can be set for a database by using CREATE DATABASE or ALTER DATABASE, and for contained database users by using CREATE USER or ALTER USER.</span></span> <span data-ttu-id="f5190-121">При настройке языков по умолчанию в автономной базе данных принимается значение **langid** , имена или псевдонимы языков, приведенные в представлении совместимости **sys.syslanguages**.</span><span class="sxs-lookup"><span data-stu-id="f5190-121">Setting default languages in a contained database accepts **langid** value, the language name, or a language alias as listed in **sys.syslanguages**.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f5190-122">безопасность</span><span class="sxs-lookup"><span data-stu-id="f5190-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f5190-123">Permissions</span><span class="sxs-lookup"><span data-stu-id="f5190-123">Permissions</span></span>  
 <span data-ttu-id="f5190-124">Разрешения на выполнение хранимой процедуры **sp_configure** без параметров или только с первым параметром по умолчанию предоставляются всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="f5190-124">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="f5190-125">Для выполнения процедуры **sp_configure** с обоими параметрами для изменения параметра конфигурации или запуска инструкции RECONFIGURE необходимо иметь разрешение ALTER SETTINGS на уровне сервера.</span><span class="sxs-lookup"><span data-stu-id="f5190-125">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="f5190-126">Разрешение ALTER SETTINGS неявным образом предоставлено предопределенным ролям сервера **sysadmin** и **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="f5190-126">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f5190-127">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f5190-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-default-language-option"></a><span data-ttu-id="f5190-128">Настройка параметра default language</span><span class="sxs-lookup"><span data-stu-id="f5190-128">To configure the default language option</span></span>  
  
1.  <span data-ttu-id="f5190-129">В обозревателе объектов щелкните правой кнопкой мыши сервер и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="f5190-129">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="f5190-130">Щелкните узел **Прочие параметры сервера** .</span><span class="sxs-lookup"><span data-stu-id="f5190-130">Click the **Misc server settings** node.</span></span>  
  
3.  <span data-ttu-id="f5190-131">В поле **Язык пользователей по умолчанию** выберите язык, на котором [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] будет отображать системные сообщения.</span><span class="sxs-lookup"><span data-stu-id="f5190-131">In the **Default language for users** box, choose the language in which [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should display system messages.</span></span>  
  
     <span data-ttu-id="f5190-132">По умолчанию используется английский язык.</span><span class="sxs-lookup"><span data-stu-id="f5190-132">The default language is English.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f5190-133">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f5190-133">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-default-language-option"></a><span data-ttu-id="f5190-134">Настройка параметра default language</span><span class="sxs-lookup"><span data-stu-id="f5190-134">To configure the default language option</span></span>  
  
1.  <span data-ttu-id="f5190-135">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5190-135">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f5190-136">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="f5190-136">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f5190-137">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="f5190-137">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="f5190-138">В этом примере описывается использование процедуры [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) для задания значения параметра `default language` равным "Французский" (`2`).</span><span class="sxs-lookup"><span data-stu-id="f5190-138">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to configure the `default language` option to French (`2`).</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'default language', 2 ;  
GO  
RECONFIGURE ;  
GO  
```  
  
 <span data-ttu-id="f5190-139">Дополнительные сведения см. в разделе [Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f5190-139">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-default-language-option"></a><a name="FollowUp"></a> <span data-ttu-id="f5190-140">Дальнейшие действия. После настройки параметра default language</span><span class="sxs-lookup"><span data-stu-id="f5190-140">Follow Up: After you configure the default language option</span></span>  
 <span data-ttu-id="f5190-141">Параметр вступает в силу немедленно, без перезапуска сервера.</span><span class="sxs-lookup"><span data-stu-id="f5190-141">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5190-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="f5190-142">See Also</span></span>  
 <span data-ttu-id="f5190-143">[CREATE LOGIN (Transact-SQL)](/sql/t-sql/statements/create-login-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f5190-143">[CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql) </span></span>  
 <span data-ttu-id="f5190-144">[ALTER LOGIN (Transact-SQL)](/sql/t-sql/statements/alter-login-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f5190-144">[ALTER LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-login-transact-sql) </span></span>  
 <span data-ttu-id="f5190-145">[CREATE USER (Transact-SQL)](/sql/t-sql/statements/create-user-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f5190-145">[CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql) </span></span>  
 <span data-ttu-id="f5190-146">[ALTER USER (Transact-SQL)](/sql/t-sql/statements/alter-user-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f5190-146">[ALTER USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-user-transact-sql) </span></span>  
 <span data-ttu-id="f5190-147">[CREATE DATABASE (SQL Server Transact-SQL)](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f5190-147">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 <span data-ttu-id="f5190-148">[ALTER DATABASE (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f5190-148">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="f5190-149">[RECONFIGURE (Transact-SQL)](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f5190-149">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="f5190-150">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f5190-150">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="f5190-151">sp_configure (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f5190-151">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
