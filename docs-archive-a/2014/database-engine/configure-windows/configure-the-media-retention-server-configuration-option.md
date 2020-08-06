---
title: Настройка параметра конфигурации сервера "media retention" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- backup retention duration [SQL Server]
- backup sets [SQL Server], retention duration
- media retention option
ms.assetid: 12e9fe6a-20a5-4c6e-9cc9-d500c003b70a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 092e0a2b5cfc30fd2d2362645fc1242bf4a1651e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657890"
---
# <a name="configure-the-media-retention-server-configuration-option"></a><span data-ttu-id="451ad-102">Настройка параметра сервера media retention</span><span class="sxs-lookup"><span data-stu-id="451ad-102">Configure the media retention Server Configuration Option</span></span>
  <span data-ttu-id="451ad-103">В этом разделе описывается настройка параметра конфигурации сервера **media retention** в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="451ad-103">This topic describes how to configure the **media retention** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="451ad-104">Параметр **media retention** используется для указания времени хранения каждого резервного набора данных.</span><span class="sxs-lookup"><span data-stu-id="451ad-104">The **media retention** option specifies the length of time to retain each backup set.</span></span> <span data-ttu-id="451ad-105">Этот параметр обеспечивает защиту резервных копий от перезаписи до истечения установленного числа суток.</span><span class="sxs-lookup"><span data-stu-id="451ad-105">The option helps protect backups from being overwritten until the specified number of days has elapsed.</span></span> <span data-ttu-id="451ad-106">После настройки параметра **media retention** не нужно определять длительность хранения резервных копий системы каждый раз, когда выполняется резервное копирование.</span><span class="sxs-lookup"><span data-stu-id="451ad-106">After you configure **media retention** option, you do not have to specify the length of time to retain system backups each time you perform a backup.</span></span> <span data-ttu-id="451ad-107">Значение по умолчанию — 0 дней, максимальное — 365 дней.</span><span class="sxs-lookup"><span data-stu-id="451ad-107">The default value is 0 days, and the maximum value is 365 days.</span></span>  
  
 <span data-ttu-id="451ad-108">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="451ad-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="451ad-109">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="451ad-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="451ad-110">Ограничения</span><span class="sxs-lookup"><span data-stu-id="451ad-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="451ad-111">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="451ad-111">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="451ad-112">Безопасность</span><span class="sxs-lookup"><span data-stu-id="451ad-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="451ad-113">**Настройка параметра media retention с помощью следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="451ad-113">**To configure the media retention option, using:**</span></span>  
  
     [<span data-ttu-id="451ad-114">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="451ad-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="451ad-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="451ad-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="451ad-116">**Дальнейшие действия.**  [После настройки параметра media retention](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="451ad-116">**Follow Up:**  [After you configure the media retention option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="451ad-117">Перед началом</span><span class="sxs-lookup"><span data-stu-id="451ad-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="451ad-118">Ограничения</span><span class="sxs-lookup"><span data-stu-id="451ad-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="451ad-119">При использовании носителя данных резервных копий до истечения установленного количества суток служба [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] выдает предупреждающее сообщение.</span><span class="sxs-lookup"><span data-stu-id="451ad-119">If you use the backup medium before the set number of days has passed, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] issues a warning message.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="451ad-120">не выдает предупреждений, если настройки по умолчанию не были изменены.</span><span class="sxs-lookup"><span data-stu-id="451ad-120">does not issue a warning unless you change the default.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="451ad-121">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="451ad-121">Recommendations</span></span>  
  
-   <span data-ttu-id="451ad-122">Этот параметр является дополнительным и его следует изменять только опытным администраторам баз данных или сертифицированным техническим специалистам [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="451ad-122">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="451ad-123">Параметр **media retention** можно переопределить с помощью предложения RETAINDAYS инструкции [BACKUP](/sql/t-sql/statements/backup-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="451ad-123">The **media retention** option can be overridden by using the RETAINDAYS clause of the [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="451ad-124">безопасность</span><span class="sxs-lookup"><span data-stu-id="451ad-124">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="451ad-125">Permissions</span><span class="sxs-lookup"><span data-stu-id="451ad-125">Permissions</span></span>  
 <span data-ttu-id="451ad-126">Разрешения на выполнение хранимой процедуры **sp_configure** без параметров или только с первым параметром по умолчанию предоставляются всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="451ad-126">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="451ad-127">Для выполнения процедуры **sp_configure** с обоими параметрами для изменения параметра конфигурации или запуска инструкции RECONFIGURE необходимо иметь разрешение ALTER SETTINGS на уровне сервера.</span><span class="sxs-lookup"><span data-stu-id="451ad-127">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="451ad-128">Разрешение ALTER SETTINGS неявным образом предоставлено предопределенным ролям сервера **sysadmin** и **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="451ad-128">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="451ad-129">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="451ad-129">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-media-retention-option"></a><span data-ttu-id="451ad-130">Настройка параметра media retention</span><span class="sxs-lookup"><span data-stu-id="451ad-130">To configure the media retention option</span></span>  
  
1.  <span data-ttu-id="451ad-131">В обозревателе объектов щелкните правой кнопкой мыши сервер и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="451ad-131">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="451ad-132">Щелкните узел **Параметры базы данных** .</span><span class="sxs-lookup"><span data-stu-id="451ad-132">Click the **Database settings** node.</span></span>  
  
3.  <span data-ttu-id="451ad-133">В области **Резервное копирование и восстановление**в поле **Срок хранения носителей резервных копий по умолчанию** введите или выберите значение от 0 до 365, чтобы установить время в сутках, в течение которого будут храниться носители данных резервных копий после создания резервной копии журнала транзакций или базы данных.</span><span class="sxs-lookup"><span data-stu-id="451ad-133">Under **Backup/Restore**, in the **Default backup media retention** box, type or select a value from 0 through 365 to set the number of days the backup medium will be retained after a database or transaction log backup.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="451ad-134">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="451ad-134">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-media-retention-option"></a><span data-ttu-id="451ad-135">Настройка параметра media retention</span><span class="sxs-lookup"><span data-stu-id="451ad-135">To configure the media retention option</span></span>  
  
1.  <span data-ttu-id="451ad-136">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="451ad-136">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="451ad-137">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="451ad-137">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="451ad-138">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="451ad-138">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="451ad-139">В этом примере описывается использование хранимой процедуры [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) для задания значения параметра `media retention` равным `60` дням.</span><span class="sxs-lookup"><span data-stu-id="451ad-139">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `media retention` option to `60` days.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'media retention', 60 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="451ad-140">Дополнительные сведения см. в разделе [Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="451ad-140">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-media-retention-option"></a><a name="FollowUp"></a> <span data-ttu-id="451ad-141">Дальнейшие действия. После настройки параметра media retention</span><span class="sxs-lookup"><span data-stu-id="451ad-141">Follow Up: After you configure the media retention option</span></span>  
 <span data-ttu-id="451ad-142">Параметр вступает в силу немедленно, без перезапуска сервера.</span><span class="sxs-lookup"><span data-stu-id="451ad-142">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="451ad-143">См. также:</span><span class="sxs-lookup"><span data-stu-id="451ad-143">See Also</span></span>  
 <span data-ttu-id="451ad-144">[Резервное копирование и восстановление баз данных SQL Server](../../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="451ad-144">[Back Up and Restore of SQL Server Databases](../../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md) </span></span>  
 <span data-ttu-id="451ad-145">[BACKUP (Transact-SQL)](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="451ad-145">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="451ad-146">[RECONFIGURE (Transact-SQL)](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="451ad-146">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="451ad-147">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="451ad-147">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="451ad-148">sp_configure (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="451ad-148">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
