---
title: Назначение срока хранения резервной копии (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backing up databases [SQL Server], expiration dates
- expiration [SQL Server]
- database backups [SQL Server], expiration dates
ms.assetid: 76e814df-6487-4893-9f09-7759f1863a5c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9185222df93e0a1150256535526ba910c593cf6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657823"
---
# <a name="set-the-expiration-date-on-a-backup-sql-server"></a><span data-ttu-id="330ce-102">Назначение срока хранения резервной копии (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="330ce-102">Set the Expiration Date on a Backup (SQL Server)</span></span>
  <span data-ttu-id="330ce-103">В этом разделе описано, как задать срок хранения для устройства резервного копирования в среде [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="330ce-103">This topic describes how to set the expiration date on a backup in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="330ce-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="330ce-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="330ce-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="330ce-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="330ce-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="330ce-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="330ce-107">**Задание срока хранения резервной копии с помощью:**</span><span class="sxs-lookup"><span data-stu-id="330ce-107">**To set the expiration date on a backup, using:**</span></span>  
  
     [<span data-ttu-id="330ce-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="330ce-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="330ce-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="330ce-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="330ce-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="330ce-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="330ce-111">безопасность</span><span class="sxs-lookup"><span data-stu-id="330ce-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="330ce-112">Permissions</span><span class="sxs-lookup"><span data-stu-id="330ce-112">Permissions</span></span>  
 <span data-ttu-id="330ce-113">Разрешения BACKUP DATABASE и BACKUP LOG назначены по умолчанию членам предопределенной роли сервера **sysadmin** и предопределенным ролям базы данных **db_owner** и **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="330ce-113">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="330ce-114">Проблемы, связанные с владельцем и разрешениями у физических файлов на устройстве резервного копирования, могут помешать операции резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="330ce-114">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="330ce-115">должен иметь возможность считывать и записывать данные на устройстве; учетная запись, от имени которой выполняется служба [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , должна иметь разрешения на запись.</span><span class="sxs-lookup"><span data-stu-id="330ce-115">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="330ce-116">Однако процедура [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), добавляющая запись для устройства резервного копирования в системные таблицы, не проверяет разрешения на доступ к файлу.</span><span class="sxs-lookup"><span data-stu-id="330ce-116">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="330ce-117">Проблемы физического файла устройства резервного копирования могут не проявляться до момента доступа к физическому ресурсу во время операции резервного копирования или восстановления.</span><span class="sxs-lookup"><span data-stu-id="330ce-117">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="330ce-118">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="330ce-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-the-expiration-date-on-a-backup"></a><span data-ttu-id="330ce-119">Назначение срока хранения резервной копии</span><span class="sxs-lookup"><span data-stu-id="330ce-119">To set the expiration date on a backup</span></span>  
  
1.  <span data-ttu-id="330ce-120">После подключения к соответствующему экземпляру [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] в обозревателе объектов разверните дерево сервера, щелкнув его имя.</span><span class="sxs-lookup"><span data-stu-id="330ce-120">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="330ce-121">Раскройте узел **Базы данных**и в зависимости от типа восстанавливаемой базы данных выберите пользовательскую базу данных или раскройте узел **Системные базы данных** и выберите системную базу данных.</span><span class="sxs-lookup"><span data-stu-id="330ce-121">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="330ce-122">Щелкните правой кнопкой мыши базу данных, выберите пункт **Задачи**, а затем команду **Создать резервную копию**.</span><span class="sxs-lookup"><span data-stu-id="330ce-122">Right-click the database, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="330ce-123">Откроется диалоговое окно **Резервное копирование базы данных** .</span><span class="sxs-lookup"><span data-stu-id="330ce-123">The **Back Up Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="330ce-124">На странице **Общие** в поле **Срок действия резервного набора данных истекает**укажите дату истечения срока, чтобы определить, когда резервный набор данных можно будет перезаписать другой резервной копией:</span><span class="sxs-lookup"><span data-stu-id="330ce-124">On the **General** page, for **Backup set will expire**, specify an expiration date to indicate when the backup set can be overwritten by another backup:</span></span>  
  
    -   <span data-ttu-id="330ce-125">Чтобы задать срок действия резервного набора данных, выберите пункт **После** (параметр по умолчанию) и введите срок действия набора в днях с момента его создания.</span><span class="sxs-lookup"><span data-stu-id="330ce-125">To have the backup set expire after a specific number of days, click **After** (the default option), and enter the number of days after set creation that the set will expire.</span></span> <span data-ttu-id="330ce-126">Это значение может быть задано в диапазоне от 0 до 99 999 дней. Значение 0 означает, что срок действия резервного набора данных не ограничен.</span><span class="sxs-lookup"><span data-stu-id="330ce-126">This value can be from 0 to 99999 days; a value of 0 days means that the backup set will never expire.</span></span>  
  
         <span data-ttu-id="330ce-127">Значение по умолчанию задается в параметре **Срок хранения носителей резервных копий по умолчанию (дней)** диалогового окна **Свойства сервера** (страница**Параметры базы данных** ).</span><span class="sxs-lookup"><span data-stu-id="330ce-127">The default value is set in the **Default backup media retention (in days)** option of the **Server Properties** dialog box (**Database Settings** page).</span></span> <span data-ttu-id="330ce-128">Чтобы получить доступ к этому параметру, щелкните правой кнопкой мыши имя сервера в обозревателе объектов и выберите пункт "Свойства", а затем выберите страницу **Настройки базы данных** .</span><span class="sxs-lookup"><span data-stu-id="330ce-128">To access this, right-click the server name in Object Explorer and select properties; then select the **Database Settings** page.</span></span>  
  
    -   <span data-ttu-id="330ce-129">Чтобы указать дату истечения срока действия резервного набора данных, выберите пункт **На**и введите дату истечения срока действия резервного набора данных.</span><span class="sxs-lookup"><span data-stu-id="330ce-129">To have the backup set expire on a specific date, click **On**, and enter the date on which the set will expire.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="330ce-130">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="330ce-130">Using Transact-SQL</span></span>  
  
#### <a name="to-set-the-expiration-date-on-a-backup"></a><span data-ttu-id="330ce-131">Назначение срока хранения резервной копии</span><span class="sxs-lookup"><span data-stu-id="330ce-131">To set the expiration date on a backup</span></span>  
  
1.  <span data-ttu-id="330ce-132">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="330ce-132">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="330ce-133">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="330ce-133">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="330ce-134">В инструкции [BACKUP](/sql/t-sql/statements/backup-transact-sql) укажите параметр EXPIREDATE или RETAINDAYS, чтобы определить, когда компоненту [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] можно будет перезаписать резервную копию.</span><span class="sxs-lookup"><span data-stu-id="330ce-134">In the [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement, specify either the EXPIREDATE or RETAINDAYS option to determine when the [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] can overwrite the backup.</span></span> <span data-ttu-id="330ce-135">Если ни один из этих параметров не указан, то срок хранения определяется параметром конфигурации [media retention](../../database-engine/configure-windows/configure-the-media-retention-server-configuration-option.md) .</span><span class="sxs-lookup"><span data-stu-id="330ce-135">If neither option is specified, the expiration date is determined by the [media retention](../../database-engine/configure-windows/configure-the-media-retention-server-configuration-option.md) server configuration setting.</span></span> <span data-ttu-id="330ce-136">В следующем примере параметр `EXPIREDATE` задает срок истечения хранения 30 июня 2015 г. (`6/30/2015`).</span><span class="sxs-lookup"><span data-stu-id="330ce-136">This example uses the `EXPIREDATE` option to specify an expiration date of June 30, 2015 (`6/30/2015`).</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
BACKUP DATABASE AdventureWorks2012  
 TO DISK = 'Z:\SQLServerBackups\AdventureWorks2012.Bak'  
   WITH EXPIREDATE = '6/30/2015' ;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="330ce-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="330ce-137">See Also</span></span>  
 <span data-ttu-id="330ce-138">[Создание полной резервной копии базы данных (SQL Server)](create-a-full-database-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="330ce-138">[Create a Full Database Backup &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md) </span></span>  
 <span data-ttu-id="330ce-139">[Создание резервных копий файлов и файловых групп (SQL Server)](back-up-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="330ce-139">[Back Up Files and Filegroups &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span></span>  
 <span data-ttu-id="330ce-140">[Создание резервной копии журнала транзакций (SQL Server)](back-up-a-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="330ce-140">[Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span></span>  
 [<span data-ttu-id="330ce-141">Создание разностной резервной копии базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="330ce-141">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
  
