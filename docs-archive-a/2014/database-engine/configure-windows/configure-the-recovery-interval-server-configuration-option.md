---
title: Настройка параметра конфигурации сервера recovery interval | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- restoring recovery interval [SQL Server]
- checkpoints [SQL Server]
- recovery interval option [SQL Server]
- default recovery interval option
- time [SQL Server], recovery interval
- interval for recovery [SQL Server]
- maximum number of minutes per database recovery
- recovery [SQL Server], recovery interval option
ms.assetid: e4734b3b-8fbe-4b65-9c48-91b5a3dd18e1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 560d514ba8dd1503b59b3b59ecf404d876e24cd2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655951"
---
# <a name="configure-the-recovery-interval-server-configuration-option"></a><span data-ttu-id="74874-102">Настройка параметра конфигурации сервера recovery interval</span><span class="sxs-lookup"><span data-stu-id="74874-102">Configure the recovery interval Server Configuration Option</span></span>
  <span data-ttu-id="74874-103">В этом разделе описываются способы настройки параметра конфигурации сервера **recovery interval** в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="74874-103">This topic describes how to configure the **recovery interval** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="74874-104">Параметр **recovery interval** определяет верхний предел времени восстановления базы данных.</span><span class="sxs-lookup"><span data-stu-id="74874-104">The **recovery interval** option defines an upper limit on the time recovering a database should take.</span></span> <span data-ttu-id="74874-105">Компонент [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] использует значение этого параметра чтобы приблизительно определить частоту выделения [автоматических контрольных точек](../../relational-databases/logs/database-checkpoints-sql-server.md) для данной базы данных.</span><span class="sxs-lookup"><span data-stu-id="74874-105">The [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] uses the value specified for this option to determine approximately how often [automatic checkpoints](../../relational-databases/logs/database-checkpoints-sql-server.md) to issue automatic checkpoints on a given database.</span></span>  
  
 <span data-ttu-id="74874-106">По умолчанию задано значение интервала восстановления 0, позволяющее компоненту [!INCLUDE[ssDE](../../includes/ssde-md.md)] автоматически настраивать интервал восстановления.</span><span class="sxs-lookup"><span data-stu-id="74874-106">The default recovery-interval value is 0, which allows the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to automatically configure the recovery interval.</span></span> <span data-ttu-id="74874-107">Обычно при интервале восстановления по умолчанию автоматические контрольные точки создаются приблизительно раз в минуту для активных баз данных, а время восстановления занимает меньше минуты.</span><span class="sxs-lookup"><span data-stu-id="74874-107">Typically, the default recovery interval results in automatic checkpoints occurring approximately once a minute for active databases and a recovery time of less than one minute.</span></span> <span data-ttu-id="74874-108">Более высокие значения указывают приблизительное максимальное время восстановления в минутах.</span><span class="sxs-lookup"><span data-stu-id="74874-108">Higher values indicate the approximate maximum recovery time, in minutes.</span></span> <span data-ttu-id="74874-109">Например, интервал восстановления, равный 3, указывает, что максимальное время восстановления равно приблизительно 3 минутам.</span><span class="sxs-lookup"><span data-stu-id="74874-109">For example, setting the recovery interval to 3 indicates a maximum recovery time of approximately three minutes.</span></span>  
  
 <span data-ttu-id="74874-110">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="74874-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="74874-111">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="74874-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="74874-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="74874-112">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="74874-113">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="74874-113">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="74874-114">Безопасность</span><span class="sxs-lookup"><span data-stu-id="74874-114">Security</span></span>](#Security)  
  
-   <span data-ttu-id="74874-115">**Настройка параметра конфигурации сервера recovery interval с помощью:**</span><span class="sxs-lookup"><span data-stu-id="74874-115">**To Configure the recovery interval Server Configuration Option, using:**</span></span>  
  
     [<span data-ttu-id="74874-116">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="74874-116">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="74874-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="74874-117">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="74874-118">**Дальнейшие действия.**  [После настройки параметра recovery interval](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="74874-118">**Follow Up:**  [After you configure the recovery interval option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="74874-119">Перед началом</span><span class="sxs-lookup"><span data-stu-id="74874-119">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="74874-120">Ограничения</span><span class="sxs-lookup"><span data-stu-id="74874-120">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="74874-121">Интервал восстановления влияет только на базы данных, использующие целевое время восстановления по умолчанию (0).</span><span class="sxs-lookup"><span data-stu-id="74874-121">The recovery interval affects only databases that use the default target recovery time (0).</span></span> <span data-ttu-id="74874-122">Чтобы переопределить интервал восстановления сервера для базы данных, следует настроить целевое время восстановления, не являющееся временем восстановления по умолчанию для этой базы данных.</span><span class="sxs-lookup"><span data-stu-id="74874-122">To override the server recovery interval on a database, configure a non-default target recovery time on the database.</span></span> <span data-ttu-id="74874-123">Дополнительные сведения см. в разделе [Изменение целевого времени восстановления базы данных (SQL Server)](../../relational-databases/logs/change-the-target-recovery-time-of-a-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="74874-123">For more information, see [Change the Target Recovery Time of a Database &#40;SQL Server&#41;](../../relational-databases/logs/change-the-target-recovery-time-of-a-database-sql-server.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="74874-124">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="74874-124">Recommendations</span></span>  
  
-   <span data-ttu-id="74874-125">Этот параметр является дополнительным и его следует изменять только опытным администраторам баз данных или сертифицированным техническим специалистам [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="74874-125">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="74874-126">Обычно рекомендуется сохранять интервал восстановления, равный 0, если нет проблем с производительностью.</span><span class="sxs-lookup"><span data-stu-id="74874-126">Typically, we recommend that you keep the recovery interval at 0, unless you experience performance problems.</span></span> <span data-ttu-id="74874-127">Если принято решение увеличить параметр интервала восстановления, рекомендуется увеличивать его постепенно с небольшими приращениями и оценивать влияние каждого приращения на производительность восстановления.</span><span class="sxs-lookup"><span data-stu-id="74874-127">If you decide to increase the recovery-interval setting, we recommend increasing it gradually by small increments and evaluating the effect of each incremental increase on recovery performance.</span></span>  
  
-   <span data-ttu-id="74874-128">При использовании хранимой процедуры **sp_configure** для изменения параметра **recovery interval** до значения, превышающего 60 минут, необходимо указать параметр RECONFIGURE WITH OVERRIDE.</span><span class="sxs-lookup"><span data-stu-id="74874-128">If you use **sp_configure** to change the value of the **recovery interval** option to more than 60 (minutes), specify RECONFIGURE WITH OVERRIDE.</span></span> <span data-ttu-id="74874-129">Параметр WITH OVERRIDE отключает проверку значения конфигурации (при которой выполняется поиск недопустимых или нерекомендованных значений).</span><span class="sxs-lookup"><span data-stu-id="74874-129">WITH OVERRIDE disables configuration value checking (for values that are not valid or are nonrecommended values).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="74874-130">безопасность</span><span class="sxs-lookup"><span data-stu-id="74874-130">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="74874-131">Permissions</span><span class="sxs-lookup"><span data-stu-id="74874-131">Permissions</span></span>  
 <span data-ttu-id="74874-132">Разрешения на выполнение хранимой процедуры **sp_configure** без параметров или только с первым параметром по умолчанию предоставляются всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="74874-132">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="74874-133">Для выполнения процедуры **sp_configure** с обоими параметрами для изменения параметра конфигурации или запуска инструкции RECONFIGURE необходимо иметь разрешение ALTER SETTINGS на уровне сервера.</span><span class="sxs-lookup"><span data-stu-id="74874-133">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="74874-134">Разрешение ALTER SETTINGS неявным образом предоставлено предопределенным ролям сервера **sysadmin** и **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="74874-134">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="74874-135">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="74874-135">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="74874-136">**Указание интервала восстановления**</span><span class="sxs-lookup"><span data-stu-id="74874-136">**To set the recovery interval**</span></span>  
  
1.  <span data-ttu-id="74874-137">В обозревателе объектов щелкните правой кнопкой мыши экземпляр сервера и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="74874-137">In Object Explorer, right-click server instance and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="74874-138">Щелкните узел **Параметры базы данных** .</span><span class="sxs-lookup"><span data-stu-id="74874-138">Click the **Database settings** node.</span></span>  
  
3.  <span data-ttu-id="74874-139">В разделе **Восстановление**в поле **Интервал восстановления (в минутах)** введите или выберите значение от 0 до 32 767 максимального интервала времени в минутах, которое [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] должен при запуске выделять на восстановление каждой базы данных.</span><span class="sxs-lookup"><span data-stu-id="74874-139">Under **Recovery**, in the **Recovery interval (minutes)** box, type or select a value from 0 through 32767 to set the maximum amount of time, in minutes, that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should spend recovering each database at startup.</span></span> <span data-ttu-id="74874-140">Если значение по умолчанию равно 0, оно означает автоматическую настройку, которую выполняет [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="74874-140">The default is 0, indicating automatic configuration by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="74874-141">На практике это означает время восстановления менее минуты и создание контрольных точек приблизительно раз в минуту для активно используемых баз данных.</span><span class="sxs-lookup"><span data-stu-id="74874-141">In practice, this means a recovery time of less than one minute and a checkpoint approximately every one minute for active databases.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="74874-142">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="74874-142">Using Transact-SQL</span></span>  
  
#### <a name="to-set-the-recovery-interval"></a><span data-ttu-id="74874-143">Указание интервала восстановления</span><span class="sxs-lookup"><span data-stu-id="74874-143">To set the recovery interval</span></span>  
  
1.  <span data-ttu-id="74874-144">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="74874-144">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="74874-145">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="74874-145">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="74874-146">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="74874-146">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="74874-147">В этом примере показано использование хранимой процедуры [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) для задания значения параметра `recovery interval` равным `3` мин.</span><span class="sxs-lookup"><span data-stu-id="74874-147">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `recovery interval` option to `3` minutes.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'recovery interval', 3 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="74874-148">Дополнительные сведения см. в разделе [Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="74874-148">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-recovery-internal-option"></a><a name="FollowUp"></a> <span data-ttu-id="74874-149">Дальнейшие действия. После настройки параметра recovery interval</span><span class="sxs-lookup"><span data-stu-id="74874-149">Follow Up: After you configure the recovery internal option</span></span>  
 <span data-ttu-id="74874-150">Параметр вступает в силу немедленно, без перезапуска сервера.</span><span class="sxs-lookup"><span data-stu-id="74874-150">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74874-151">См. также:</span><span class="sxs-lookup"><span data-stu-id="74874-151">See Also</span></span>  
 <span data-ttu-id="74874-152">[Изменение целевого времени восстановления базы данных (SQL Server)](../../relational-databases/logs/change-the-target-recovery-time-of-a-database-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="74874-152">[Change the Target Recovery Time of a Database &#40;SQL Server&#41;](../../relational-databases/logs/change-the-target-recovery-time-of-a-database-sql-server.md) </span></span>  
 <span data-ttu-id="74874-153">[Контрольные точки базы данных (SQL Server)](../../relational-databases/logs/database-checkpoints-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="74874-153">[Database Checkpoints &#40;SQL Server&#41;](../../relational-databases/logs/database-checkpoints-sql-server.md) </span></span>  
 <span data-ttu-id="74874-154">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="74874-154">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="74874-155">[sp_configure (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="74874-155">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="74874-156">[Параметр конфигурации сервера "show advanced options"](show-advanced-options-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="74874-156">[show advanced options Server Configuration Option](show-advanced-options-server-configuration-option.md) </span></span>  
 [<span data-ttu-id="74874-157">RECONFIGURE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="74874-157">RECONFIGURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/reconfigure-transact-sql)  
  
  
