---
title: Настройка параметра конфигурации и сервера scan for startup procs | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- scan for startup procs option
ms.assetid: 6bf9d252-e766-458d-9dcd-23d895f032a2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: fbf46fc7476e6e879991cfe3f649fd5617f3275e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657881"
---
# <a name="configure-the-scan-for-startup-procs-server-configuration-option"></a><span data-ttu-id="5d484-102">Настройка параметра конфигураци и сервера scan for startup procs</span><span class="sxs-lookup"><span data-stu-id="5d484-102">Configure the scan for startup procs Server Configuration Option</span></span>
  <span data-ttu-id="5d484-103">В этом разделе описываются способы настройки параметра конфигурации сервера **scan for startup procs** в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5d484-103">This topic describes how to configure the **scan for startup procs** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="5d484-104">Параметр **scan for startup procs** предназначен для просмотра хранимых процедур, автоматически выполняемых при запуске [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5d484-104">Use the **scan for startup procs** option to scan for automatic execution of stored procedures at [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] startup time.</span></span> <span data-ttu-id="5d484-105">Если этому параметру присвоено значение 1, сервер [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] просматривает и выполняет все автоматически запускаемые хранимые процедуры, которые определены на сервере.</span><span class="sxs-lookup"><span data-stu-id="5d484-105">If this option is set to 1, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] scans for and runs all automatically run stored procedures that are defined on the server.</span></span> <span data-ttu-id="5d484-106">По умолчанию параметр **scan for startup procs** имеет значение 0 (не искать).</span><span class="sxs-lookup"><span data-stu-id="5d484-106">The default value for **scan for startup procs** is 0 (do not scan).</span></span>  
  
 <span data-ttu-id="5d484-107">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="5d484-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5d484-108">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="5d484-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5d484-109">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="5d484-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="5d484-110">Безопасность</span><span class="sxs-lookup"><span data-stu-id="5d484-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5d484-111">**Настройка параметра scan for startup procs с использованием следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="5d484-111">**To configure the scan for startup procs option, using:**</span></span>  
  
     [<span data-ttu-id="5d484-112">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5d484-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5d484-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5d484-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="5d484-114">**Дальнейшие действия.**  [После настройки параметра scan for startup procs](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="5d484-114">**Follow Up:**  [After you configure the scan for startup procs option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5d484-115">Перед началом</span><span class="sxs-lookup"><span data-stu-id="5d484-115">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="5d484-116">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="5d484-116">Recommendations</span></span>  
  
-   <span data-ttu-id="5d484-117">Этот параметр является дополнительным и его следует изменять только опытным администраторам баз данных или сертифицированным техническим специалистам [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5d484-117">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="5d484-118">Значение этого параметра можно устанавливать с помощью процедуры **sp_configure**; однако оно будет задано автоматически, если используется процедура **sp_procoption**, применяемая для установки или снятия меток с автоматически выполняемых хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="5d484-118">The value for this option can be set by using **sp_configure**; however, it will be set automatically if you use **sp_procoption**, which is used to mark or unmark automatically run stored procedures.</span></span> <span data-ttu-id="5d484-119">Если с помощью процедуры **sp_procoption** первая хранимая процедура помечается как автоматически выполняемая, этому параметру автоматически присваивается значение 1.</span><span class="sxs-lookup"><span data-stu-id="5d484-119">When **sp_procoption** is used to mark the first stored procedure as an autoproc, this option is set automatically to a value of 1.</span></span> <span data-ttu-id="5d484-120">Если процедура **sp_procoption** используется для снятия метки с последней хранимой процедуры как автоматически выполняемой, этому параметру автоматически присваивается значение 0.</span><span class="sxs-lookup"><span data-stu-id="5d484-120">When **sp_procoption** is used to unmark the last stored procedure as an autoproc, this option is automatically set to a value of 0.</span></span> <span data-ttu-id="5d484-121">Если процедура **sp_procoption** используется для установления и снятия меток автоматически выполняемых процедур, а перед удалением процедур с них всегда снимаются метки автоматически выполняемых, нет необходимости устанавливать этот параметр вручную.</span><span class="sxs-lookup"><span data-stu-id="5d484-121">If you use **sp_procoption** to mark and unmark autoprocs, and if you always unmark autoprocs before dropping them, there is no need to set this option manually.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5d484-122">безопасность</span><span class="sxs-lookup"><span data-stu-id="5d484-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5d484-123">Permissions</span><span class="sxs-lookup"><span data-stu-id="5d484-123">Permissions</span></span>  
 <span data-ttu-id="5d484-124">Разрешения на выполнение хранимой процедуры **sp_configure** без параметров или только с первым параметром по умолчанию предоставляются всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="5d484-124">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="5d484-125">Для выполнения процедуры **sp_configure** с обоими параметрами для изменения параметра конфигурации или запуска инструкции RECONFIGURE необходимо иметь разрешение ALTER SETTINGS на уровне сервера.</span><span class="sxs-lookup"><span data-stu-id="5d484-125">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="5d484-126">Разрешение ALTER SETTINGS неявным образом предоставлено предопределенным ролям сервера **sysadmin** и **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="5d484-126">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5d484-127">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5d484-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-scan-for-startup-procs-option"></a><span data-ttu-id="5d484-128">Настройка параметра scan for startup procs</span><span class="sxs-lookup"><span data-stu-id="5d484-128">To configure the scan for startup procs option</span></span>  
  
1.  <span data-ttu-id="5d484-129">В обозревателе объектов щелкните правой кнопкой мыши сервер и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="5d484-129">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="5d484-130">Щелкните узел **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="5d484-130">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="5d484-131">В разделе **Разное**для параметра **Scan for Startup Procs** выберите значение True или False в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="5d484-131">Under **Miscellaneous**, change the **Scan for Startup Procs** option to True or False by selecting the value you want from the drop-down list box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5d484-132">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5d484-132">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-scan-for-startup-procs-option"></a><span data-ttu-id="5d484-133">Настройка параметра scan for startup procs</span><span class="sxs-lookup"><span data-stu-id="5d484-133">To configure the scan for startup procs option</span></span>  
  
1.  <span data-ttu-id="5d484-134">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5d484-134">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5d484-135">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="5d484-135">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5d484-136">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="5d484-136">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="5d484-137">В этом примере описывается использование процедуры [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) для задания значения параметра `scan for startup procs` равным `1`.</span><span class="sxs-lookup"><span data-stu-id="5d484-137">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `scan for startup procs` option to `1`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1 ;  
GO  
RECONFIGURE  
GO  
EXEC sp_configure 'scan for startup procs', 1 ;  
GO  
RECONFIGURE  
GO  
  
```  
  
##  <a name="follow-up-after-you-configure-the-scan-for-startup-procs-option"></a><a name="FollowUp"></a> <span data-ttu-id="5d484-138">Дальнейшие действия. После настройки параметра scan for startup procs</span><span class="sxs-lookup"><span data-stu-id="5d484-138">Follow Up: After you configure the scan for startup procs option</span></span>  
 <span data-ttu-id="5d484-139">Чтобы изменения вступили в силу, необходимо перезапустить сервер.</span><span class="sxs-lookup"><span data-stu-id="5d484-139">The server must be restarted before the setting can take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d484-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="5d484-140">See Also</span></span>  
 <span data-ttu-id="5d484-141">[RECONFIGURE (Transact-SQL)](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5d484-141">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="5d484-142">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5d484-142">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="5d484-143">[sp_configure (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5d484-143">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="5d484-144">sp_procoption (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="5d484-144">sp_procoption &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql)  
  
  
