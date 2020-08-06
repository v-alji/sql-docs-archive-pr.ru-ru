---
title: Параметр конфигурации сервера "Просмотр или настройка параметра сжатия резервных копий по умолчанию" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], backup compression default option
- backup compression [SQL Server], backup compression default Option
ms.assetid: 23029395-3e93-4c29-b7d6-e5a47a3526ff
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f02458c069d7c155b199e24feb7ef028ae0f258a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669093"
---
# <a name="view-or-configure-the-backup-compression-default-server-configuration-option"></a><span data-ttu-id="1d337-102">Параметр конфигурации сервера «Просмотр или настройка параметра сжатия резервных копий по умолчанию»</span><span class="sxs-lookup"><span data-stu-id="1d337-102">View or Configure the backup compression default Server Configuration Option</span></span>
  <span data-ttu-id="1d337-103">В этой статье описываются способы просмотра и настройки параметра конфигурации сервера **backup compression default** в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1d337-103">This topic describes how to view or configure the **backup compression default** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="1d337-104">Параметр **backup compression default** определяет, будут ли сжатые резервные копии создаваться в экземплярах сервера по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1d337-104">The **backup compression default** option determines whether the server instance creates compressed backups by default.</span></span> <span data-ttu-id="1d337-105">После установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] параметр **backup compression default** отключен.</span><span class="sxs-lookup"><span data-stu-id="1d337-105">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed, the **backup compression default** option is off.</span></span>  
  
 <span data-ttu-id="1d337-106">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="1d337-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1d337-107">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="1d337-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1d337-108">Ограничения</span><span class="sxs-lookup"><span data-stu-id="1d337-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="1d337-109">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="1d337-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="1d337-110">Безопасность</span><span class="sxs-lookup"><span data-stu-id="1d337-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="1d337-111">**Просмотр и настройка параметра сжатия резервных копий по умолчанию с помощью следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="1d337-111">**To view or configure the backup compression default option, using:**</span></span>  
  
     [<span data-ttu-id="1d337-112">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1d337-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="1d337-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1d337-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="1d337-114">**Дальнейшие действия.**  [После настройки параметра сжатия резервных копий по умолчанию](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="1d337-114">**Follow Up:**  [After you configure the backup compression default option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1d337-115">Перед началом</span><span class="sxs-lookup"><span data-stu-id="1d337-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="1d337-116">Ограничения</span><span class="sxs-lookup"><span data-stu-id="1d337-116">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="1d337-117">Сжатие резервных копий доступно не во всех выпусках [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1d337-117">Backup compression is not available in all editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1d337-118">Дополнительные сведения см. [в разделе функции, поддерживаемые различными Выпусками SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="1d337-118">For more information, see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
-   <span data-ttu-id="1d337-119">По умолчанию сжатие существенно повышает загрузку ЦП. Дополнительная нагрузка на ЦП может помешать выполнению других операций.</span><span class="sxs-lookup"><span data-stu-id="1d337-119">By default, compression significantly increases CPU usage, and the additional CPU consumed by the compression process might adversely impact concurrent operations.</span></span> <span data-ttu-id="1d337-120">Поэтому может потребоваться создать сжатые резервные копии с низким приоритетом в сеансе, для которого использование ЦП ограничивается [регулятором ресурсов](../../relational-databases/resource-governor/resource-governor.md).</span><span class="sxs-lookup"><span data-stu-id="1d337-120">Therefore, you might want to create low-priority compressed backups in a session whose CPU usage is limited by [Resource Governor](../../relational-databases/resource-governor/resource-governor.md).</span></span> <span data-ttu-id="1d337-121">Дополнительные сведения см. ниже в подразделе [Использование регулятора ресурсов для ограничения загрузки ЦП при сжатии резервной копии (Transact-SQL)](../../relational-databases/backup-restore/use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="1d337-121">For more information, see [Use Resource Governor to Limit CPU Usage by Backup Compression &#40;Transact-SQL&#41;](../../relational-databases/backup-restore/use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="1d337-122">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="1d337-122">Recommendations</span></span>  
  
-   <span data-ttu-id="1d337-123">При создании отдельной резервной копии, настройке конфигурации доставки журналов или создании плана обслуживания можно переопределить значения по умолчанию на уровне сервера.</span><span class="sxs-lookup"><span data-stu-id="1d337-123">When you are creating an individual backup, configuring a log shipping configuration, or creating a maintenance plan, you can override the server-level default.</span></span>  
  
-   <span data-ttu-id="1d337-124">Сжатие резервной копии поддерживается как для дисковых устройств резервного копирования, так и для устройств резервного копирования на магнитной ленте.</span><span class="sxs-lookup"><span data-stu-id="1d337-124">Backup compression is supported for both disk backup devices and tape backup devices.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1d337-125">безопасность</span><span class="sxs-lookup"><span data-stu-id="1d337-125">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1d337-126">Permissions</span><span class="sxs-lookup"><span data-stu-id="1d337-126">Permissions</span></span>  
 <span data-ttu-id="1d337-127">Разрешения на выполнение хранимой процедуры **sp_configure** без параметров или только с первым параметром по умолчанию предоставляются всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="1d337-127">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="1d337-128">Для выполнения процедуры **sp_configure** с обоими параметрами для изменения параметра конфигурации или запуска инструкции RECONFIGURE необходимо иметь разрешение ALTER SETTINGS на уровне сервера.</span><span class="sxs-lookup"><span data-stu-id="1d337-128">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="1d337-129">Разрешение ALTER SETTINGS неявным образом предоставлено предопределенным ролям сервера **sysadmin** и **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="1d337-129">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1d337-130">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1d337-130">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-configure-the-backup-compression-default-option"></a><span data-ttu-id="1d337-131">Просмотр и настройка параметра сжатия резервных копий по умолчанию</span><span class="sxs-lookup"><span data-stu-id="1d337-131">To view or configure the backup compression default option</span></span>  
  
1.  <span data-ttu-id="1d337-132">В обозревателе объектов щелкните правой кнопкой мыши сервер и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="1d337-132">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="1d337-133">Щелкните узел **Параметры базы данных** .</span><span class="sxs-lookup"><span data-stu-id="1d337-133">Click the **Database settings** node.</span></span>  
  
3.  <span data-ttu-id="1d337-134">В окне **Резервное копирование и восстановление**поле **Сжатие резервных копий** показывает текущее значение параметра **backup compression default** .</span><span class="sxs-lookup"><span data-stu-id="1d337-134">Under **Backup and restore**, **Compress backup** shows the current setting of the **backup compression default** option.</span></span> <span data-ttu-id="1d337-135">Данная настройка определяет поведение по умолчанию на уровне сервера сжатия резервных копий. Это выполняется следующим образом.</span><span class="sxs-lookup"><span data-stu-id="1d337-135">This setting determines the server-level default for compressing backups, as follows:</span></span>  
  
    -   <span data-ttu-id="1d337-136">Если флажок **Сжатие резервных копий** сброшен, то новые резервные копии по умолчанию не сжимаются.</span><span class="sxs-lookup"><span data-stu-id="1d337-136">If the **Compress backup** box is blank, new backups are uncompressed by default.</span></span>  
  
    -   <span data-ttu-id="1d337-137">Если флажок **Сжатие резервных копий** установлен, то новые резервные копии по умолчанию сжимаются.</span><span class="sxs-lookup"><span data-stu-id="1d337-137">If the **Compress backup** box is checked, new backups are compressed by default.</span></span>  
  
     <span data-ttu-id="1d337-138">Члены предопределенной роли сервера **sysadmin** или **serveradmin** могут также изменить настройку по умолчанию, щелкнув поле **Сжатие резервных копий** .</span><span class="sxs-lookup"><span data-stu-id="1d337-138">If you are a member of the **sysadmin** or **serveradmin** fixed server role, you can also change the default setting by clicking the **Compress backup** box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1d337-139">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1d337-139">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-backup-compression-default-option"></a><span data-ttu-id="1d337-140">Просмотр параметров по умолчанию для сжатия резервных копий</span><span class="sxs-lookup"><span data-stu-id="1d337-140">To view the backup compression default option</span></span>  
  
1.  <span data-ttu-id="1d337-141">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1d337-141">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="1d337-142">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="1d337-142">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1d337-143">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="1d337-143">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="1d337-144">В этом примере выполняется запрос представления каталога [sys.configurations](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) для определения значения для `backup compression default`.</span><span class="sxs-lookup"><span data-stu-id="1d337-144">This example queries the [sys.configurations](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) catalog view to determine the value for `backup compression default`.</span></span> <span data-ttu-id="1d337-145">Значение, равное 0, указывает на отключение сжатия резервных копий, а значение, равное 1, указывает на включение сжатия резервных копий.</span><span class="sxs-lookup"><span data-stu-id="1d337-145">A value of 0 means that backup compression is off, and a value of 1 means that backup compression is enabled.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
SELECT value   
FROM sys.configurations   
WHERE name = 'backup compression default' ;  
GO  
  
```  
  
#### <a name="to-configure-the-backup-compression-default-option"></a><span data-ttu-id="1d337-146">Настройка параметра сжатия резервных копий по умолчанию</span><span class="sxs-lookup"><span data-stu-id="1d337-146">To configure the backup compression default option</span></span>  
  
1.  <span data-ttu-id="1d337-147">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1d337-147">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="1d337-148">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="1d337-148">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1d337-149">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="1d337-149">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="1d337-150">В этом примере описывается использование хранимой процедуры [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) для настройки на экземпляре сервера создания сжатых резервных копий по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1d337-150">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to configure the server instance to create compressed backups by default.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
EXEC sp_configure 'backup compression default', 1 ;  
RECONFIGURE WITH OVERRIDE ;  
GO  
  
```  
  
 <span data-ttu-id="1d337-151">Дополнительные сведения см. в разделе [Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1d337-151">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-backup-compression-default-option"></a><a name="FollowUp"></a> <span data-ttu-id="1d337-152">Дальнейшие действия. После настройки параметра backup compression default</span><span class="sxs-lookup"><span data-stu-id="1d337-152">Follow Up: After you configure the backup compression default option</span></span>  
 <span data-ttu-id="1d337-153">Параметр вступает в силу немедленно, без перезапуска сервера.</span><span class="sxs-lookup"><span data-stu-id="1d337-153">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d337-154">См. также:</span><span class="sxs-lookup"><span data-stu-id="1d337-154">See Also</span></span>  
 <span data-ttu-id="1d337-155">[BACKUP (Transact-SQL)](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1d337-155">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="1d337-156">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1d337-156">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="1d337-157">[RECONFIGURE (Transact-SQL)](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1d337-157">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="1d337-158">[sp_configure (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1d337-158">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="1d337-159">Общие сведения о резервном копировании (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1d337-159">Backup Overview &#40;SQL Server&#41;</span></span>](../../relational-databases/backup-restore/backup-overview-sql-server.md)  
  
  
