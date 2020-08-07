---
title: Восстановление резервной копии базы данных в простой модели восстановления (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full backups [SQL Server]
- database restores [SQL Server], full backups
- backing up databases [SQL Server], full backups
- database backups [SQL Server], full backups
- restoring databases [SQL Server], full backups
ms.assetid: a928fa36-e285-476f-9a7b-6840a8bb7283
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e264dd380c3dff40dacc4eb576d34af5195dec01
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730761"
---
# <a name="restore-a-database-backup-under-the-simple-recovery-model-transact-sql"></a><span data-ttu-id="cb1cb-102">Восстановление резервной копии базы данных в простой модели восстановления (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="cb1cb-102">Restore a Database Backup Under the Simple Recovery Model (Transact-SQL)</span></span>
  <span data-ttu-id="cb1cb-103">Этот раздел содержит сведения о восстановлении полной резервной копии базы данных.</span><span class="sxs-lookup"><span data-stu-id="cb1cb-103">This topic explains how to restore a full database backup.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="cb1cb-104">При восстановлении базы данных из полной резервной копии системный администратор должен быть единственным пользователем, работающим с базой данных.</span><span class="sxs-lookup"><span data-stu-id="cb1cb-104">The system administrator restoring the full database backup must be the only person currently using the database to be restored.</span></span>  
  
## <a name="prerequisites-and-recommendations"></a><span data-ttu-id="cb1cb-105">Предварительные требования и рекомендации</span><span class="sxs-lookup"><span data-stu-id="cb1cb-105">Prerequisites and Recommendations</span></span>  
  
-   <span data-ttu-id="cb1cb-106">Чтобы восстановить зашифрованную базу данных, необходимо иметь доступ к сертификату или асимметричному ключу, который использовался для шифрования базы данных.</span><span class="sxs-lookup"><span data-stu-id="cb1cb-106">To restore a database that is encrypted, you must have access to the certificate or asymmetric key that was used to encrypt the database.</span></span> <span data-ttu-id="cb1cb-107">Без сертификата или асимметричного ключа восстановить базу данных нельзя.</span><span class="sxs-lookup"><span data-stu-id="cb1cb-107">Without the certificate or asymmetric key, the database cannot be restored.</span></span> <span data-ttu-id="cb1cb-108">Поэтому сертификат, используемый для шифрования ключа шифрования базы данных, должен храниться в течение всего времени, пока есть необходимость в резервной копии.</span><span class="sxs-lookup"><span data-stu-id="cb1cb-108">As a result, the certificate that is used to encrypt the database encryption key must be retained as long as the backup is needed.</span></span> <span data-ttu-id="cb1cb-109">Дополнительные сведения см. в статье [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="cb1cb-109">For more information, see [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span></span>  
  
-   <span data-ttu-id="cb1cb-110">В целях безопасности рекомендуется не присоединять и не восстанавливать базы данных, полученные из неизвестных или ненадежных источников.</span><span class="sxs-lookup"><span data-stu-id="cb1cb-110">For security purposes, we recommend that you do not attach or restore databases from unknown or untrusted sources.</span></span> <span data-ttu-id="cb1cb-111">В этих базах данных может содержаться вредоносный код, вызывающий выполнение непредусмотренных инструкций [!INCLUDE[tsql](../../includes/tsql-md.md)] или появление ошибок из-за изменения схемы или физической структуры базы данных.</span><span class="sxs-lookup"><span data-stu-id="cb1cb-111">Such databases could contain malicious code that might execute unintended [!INCLUDE[tsql](../../includes/tsql-md.md)] code or cause errors by modifying the schema or the physical database structure.</span></span> <span data-ttu-id="cb1cb-112">Перед тем как использовать базу данных, полученную из неизвестного или ненадежного источника, выполните на тестовом сервере инструкцию [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) для этой базы данных, а также изучите исходный код в базе данных, например хранимые процедуры и другой пользовательский код.</span><span class="sxs-lookup"><span data-stu-id="cb1cb-112">Before you use a database from an unknown or untrusted source, run [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) on the database on a nonproduction server and also examine the code, such as stored procedures or other user-defined code, in the database.</span></span>  
  
## <a name="database-compatibility-level-after-upgrade"></a><span data-ttu-id="cb1cb-113">Уровень совместимости баз данных после обновления</span><span class="sxs-lookup"><span data-stu-id="cb1cb-113">Database Compatibility Level After Upgrade</span></span>  
 <span data-ttu-id="cb1cb-114">После обновления для уровней совместимости баз данных **tempdb**, **model**, **msdb** and **Resource** задается значение [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cb1cb-114">The compatibility levels of the **tempdb**, **model**, **msdb** and **Resource** databases are set to the compatibility level of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] after upgrade.</span></span> <span data-ttu-id="cb1cb-115">Системная база данных **master** сохраняет уровень совместимости, существовавший до обновления, кроме тех случаев, когда этот уровень был ниже 100.</span><span class="sxs-lookup"><span data-stu-id="cb1cb-115">The **master** system database retains the compatibility level it had before upgrade, unless that level was less than 100.</span></span> <span data-ttu-id="cb1cb-116">Если перед обновлением уровень совместимости базы данных **master** был менее 100, то после обновления он становится равным 100.</span><span class="sxs-lookup"><span data-stu-id="cb1cb-116">If the compatibility level of **master** was less than 100 before upgrade, it is set to 100 after upgrade.</span></span>  
  
 <span data-ttu-id="cb1cb-117">Если уровень совместимости пользовательской базы данных до обновления был 100 или выше, после обновления он останется таким же.</span><span class="sxs-lookup"><span data-stu-id="cb1cb-117">If the compatibility level of a user database was 100 or higher before upgrade, it remains the same after upgrade.</span></span> <span data-ttu-id="cb1cb-118">Если уровень совместимости до обновления был 90, в обновленной базе данных он устанавливается в значение 100, что является минимально поддерживаемым уровнем совместимости в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cb1cb-118">If the compatibility level was 90 before upgrade, in the upgraded database, the compatibility level is set to 100, which is the lowest supported compatibility level in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cb1cb-119">Новые пользовательские базы данных наследуют уровень совместимости базы данных **model** .</span><span class="sxs-lookup"><span data-stu-id="cb1cb-119">New user databases will inherit the compatibility level of the **model** database.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="cb1cb-120">Процедуры</span><span class="sxs-lookup"><span data-stu-id="cb1cb-120">Procedures</span></span>  
  
#### <a name="to-restore-a-full-database-backup"></a><span data-ttu-id="cb1cb-121">Восстановление полной резервной копии базы данных</span><span class="sxs-lookup"><span data-stu-id="cb1cb-121">To restore a full database backup</span></span>  
  
1.  <span data-ttu-id="cb1cb-122">Для восстановления полной резервной копии базы данных выполните инструкцию RESTORE DATABASE, указав:</span><span class="sxs-lookup"><span data-stu-id="cb1cb-122">Execute the RESTORE DATABASE statement to restore the full database backup, specifying:</span></span>  
  
    -   <span data-ttu-id="cb1cb-123">Имя базы данных для восстановления.</span><span class="sxs-lookup"><span data-stu-id="cb1cb-123">The name of the database to restore.</span></span>  
  
    -   <span data-ttu-id="cb1cb-124">устройство резервного копирования, с которого происходит восстановление полной резервной копии базы данных;</span><span class="sxs-lookup"><span data-stu-id="cb1cb-124">The backup device from where the full database backup is restored.</span></span>  
  
    -   <span data-ttu-id="cb1cb-125">предложение NORECOVERY при наличии журнала транзакций или разностной резервной копии, которые необходимо применить после восстановления полной резервной копии.</span><span class="sxs-lookup"><span data-stu-id="cb1cb-125">The NORECOVERY clause if you have a transaction log or differential database backup to apply after restoring the full database backup.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="cb1cb-126">Чтобы восстановить зашифрованную базу данных, необходимо иметь доступ к сертификату или асимметричному ключу, который использовался для шифрования базы данных.</span><span class="sxs-lookup"><span data-stu-id="cb1cb-126">To restore a database that is encrypted, you must have access to the certificate or asymmetric key that was used to encrypt the database.</span></span> <span data-ttu-id="cb1cb-127">Без сертификата или асимметричного ключа восстановить базу данных нельзя.</span><span class="sxs-lookup"><span data-stu-id="cb1cb-127">Without the certificate or asymmetric key, the database cannot be restored.</span></span> <span data-ttu-id="cb1cb-128">Поэтому сертификат, используемый для шифрования ключа шифрования базы данных, должен храниться в течение всего времени, пока есть необходимость в резервной копии.</span><span class="sxs-lookup"><span data-stu-id="cb1cb-128">As a result, the certificate that is used to encrypt the database encryption key must be retained as long as the backup is needed.</span></span> <span data-ttu-id="cb1cb-129">Дополнительные сведения см. в статье [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="cb1cb-129">For more information, see [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span></span>  
  
2.  <span data-ttu-id="cb1cb-130">Дополнительно можно указать следующее.</span><span class="sxs-lookup"><span data-stu-id="cb1cb-130">Optionally, specify:</span></span>  
  
    -   <span data-ttu-id="cb1cb-131">Предложение FILE, определяющее, из какого резервного набора, содержащегося на устройстве резервного копирования, будет выполнено восстановление.</span><span class="sxs-lookup"><span data-stu-id="cb1cb-131">The FILE clause to identify the backup set on the backup device to restore.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cb1cb-132">Обратите внимание, что если восстановить базу данных предыдущей версии до [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], то эта база данных будет автоматически обновлена.</span><span class="sxs-lookup"><span data-stu-id="cb1cb-132">If you restore an earlier version database to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], the database is automatically upgraded.</span></span> <span data-ttu-id="cb1cb-133">Как правило, база данных сразу становится доступной.</span><span class="sxs-lookup"><span data-stu-id="cb1cb-133">Typically, the database becomes available immediately.</span></span> <span data-ttu-id="cb1cb-134">Но если база данных [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] содержит полнотекстовые индексы, при обновлении будет произведен их импорт, сброс или повторное создание в зависимости от установленного значения свойства сервера  **upgrade_option** .</span><span class="sxs-lookup"><span data-stu-id="cb1cb-134">However, if a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] database has full-text indexes, the upgrade process either imports, resets, or rebuilds them, depending on the setting of the  **upgrade_option** server property.</span></span> <span data-ttu-id="cb1cb-135">Если при обновлении выбран режим импорта (**upgrade_option** = 2) или перестроения (**upgrade_option** = 0), полнотекстовые индексы во время обновления будут недоступны.</span><span class="sxs-lookup"><span data-stu-id="cb1cb-135">If the upgrade option is set to import (**upgrade_option** = 2) or rebuild (**upgrade_option** = 0), the full-text indexes will be unavailable during the upgrade.</span></span> <span data-ttu-id="cb1cb-136">В зависимости от объема индексируемых данных процесс импорта может занять несколько часов, а перестроение — в несколько (до десяти) раз больше.</span><span class="sxs-lookup"><span data-stu-id="cb1cb-136">Depending the amount of data being indexed, importing can take several hours, and rebuilding can take up to ten times longer.</span></span> <span data-ttu-id="cb1cb-137">Обратите внимание, что если для обновления выбран режим «Импортировать», а полнотекстовый каталог недоступен, то связанные с ним полнотекстовые индексы будут перестроены.</span><span class="sxs-lookup"><span data-stu-id="cb1cb-137">Note also that when the upgrade option is set to import, the associated full-text indexes are rebuilt if a full-text catalog is not available.</span></span> <span data-ttu-id="cb1cb-138">Чтобы изменить значение свойства сервера **upgrade_option** , следует использовать процедуру [sp_fulltext_service](/sql/relational-databases/system-stored-procedures/sp-fulltext-service-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="cb1cb-138">To change the setting of the **upgrade_option** server property, use [sp_fulltext_service](/sql/relational-databases/system-stored-procedures/sp-fulltext-service-transact-sql).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb1cb-139">Пример</span><span class="sxs-lookup"><span data-stu-id="cb1cb-139">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="cb1cb-140">Описание</span><span class="sxs-lookup"><span data-stu-id="cb1cb-140">Description</span></span>  
 <span data-ttu-id="cb1cb-141">В следующем примере восстанавливается полная резервная копия базы [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] с магнитной ленты.</span><span class="sxs-lookup"><span data-stu-id="cb1cb-141">This example restores the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] full database backup from tape.</span></span>  
  
### <a name="example"></a><span data-ttu-id="cb1cb-142">Пример</span><span class="sxs-lookup"><span data-stu-id="cb1cb-142">Example</span></span>  
  
```  
USE master;  
GO  
RESTORE DATABASE AdventureWorks2012  
   FROM TAPE = '\\.\Tape0';  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="cb1cb-143">См. также:</span><span class="sxs-lookup"><span data-stu-id="cb1cb-143">See Also</span></span>  
 <span data-ttu-id="cb1cb-144">[Выполнение полного восстановления базы данных (модель полного восстановления)](complete-database-restores-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="cb1cb-144">[Complete Database Restores &#40;Full Recovery Model&#41;](complete-database-restores-full-recovery-model.md) </span></span>  
 <span data-ttu-id="cb1cb-145">[Выполнение полного восстановления базы данных (простая модель восстановления)](complete-database-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="cb1cb-145">[Complete Database Restores &#40;Simple Recovery Model&#41;](complete-database-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="cb1cb-146">[Полные резервные копии баз данных (SQL Server)](full-database-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="cb1cb-146">[Full Database Backups &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span></span>  
 <span data-ttu-id="cb1cb-147">[RESTORE (Transact-SQL)](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cb1cb-147">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="cb1cb-148">[Журнал и сведения о заголовке резервной копии (SQL Server)](backup-history-and-header-information-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="cb1cb-148">[Backup History and Header Information &#40;SQL Server&#41;](backup-history-and-header-information-sql-server.md) </span></span>  
 [<span data-ttu-id="cb1cb-149">Перестроение системных баз данных</span><span class="sxs-lookup"><span data-stu-id="cb1cb-149">Rebuild System Databases</span></span>](../databases/system-databases.md)  
  
  
