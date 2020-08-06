---
title: SQL Server управляемого резервного копирования в Azure — параметры хранения и хранения | Документация Майкрософт
description: В этом разделе описывается настройка SQL Server управляемого резервного копирования для Microsoft Azure для базы данных и Настройка параметров по умолчанию для экземпляра.
ms.custom: ''
ms.date: 08/23/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: c4aa26ea-5465-40cc-8b83-f50603cb9db1
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 8ebdb81f8aa9edb9cd9326bcb1d286d5d3fe632c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736743"
---
# <a name="sql-server-managed-backup-to-azure---retention-and-storage-settings"></a><span data-ttu-id="b6091-103">Управляемое резервное копирование SQL Server в Azure — настройки периода хранения и хранилища</span><span class="sxs-lookup"><span data-stu-id="b6091-103">SQL Server Managed Backup to Azure - Retention and Storage Settings</span></span>
  <span data-ttu-id="b6091-104">В этом разделе описаны базовые шаги настройки [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] для базы данных, а также настройки параметров экземпляра по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b6091-104">This topic describes the basic steps to configure [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for a database and to configure default settings for the instance.</span></span> <span data-ttu-id="b6091-105">Здесь также описываются действия, необходимые для приостановки и возобновления служб [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] для экземпляра.</span><span class="sxs-lookup"><span data-stu-id="b6091-105">The topic also describes the steps necessary to pause and resume [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] services for the instance.</span></span>  
  
 <span data-ttu-id="b6091-106">Полное пошаговое руководство по настройке [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] см. в статье [Настройка SQL Server управляемого резервного копирования в Azure](../relational-databases/backup-restore/enable-sql-server-managed-backup-to-microsoft-azure.md) и [Настройка SQL Server управляемого резервного копирования в Azure для групп доступности](../../2014/database-engine/setting-up-sql-server-managed-backup-to-windows-azure-for-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="b6091-106">For a complete walkthrough of setting up [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] see [Setting up SQL Server Managed Backup to Azure](../relational-databases/backup-restore/enable-sql-server-managed-backup-to-microsoft-azure.md) and [Setting up SQL Server Managed Backup to Azure for Availability Groups](../../2014/database-engine/setting-up-sql-server-managed-backup-to-windows-azure-for-availability-groups.md).</span></span>  
  
 
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b6091-107">Перед началом</span><span class="sxs-lookup"><span data-stu-id="b6091-107">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b6091-108">Ограничения</span><span class="sxs-lookup"><span data-stu-id="b6091-108">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="b6091-109">Не включайте [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] в базах данных, где используются планы обслуживания или доставка журналов.</span><span class="sxs-lookup"><span data-stu-id="b6091-109">Do not enable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] on databases that are currently using maintenance plans or log shipping.</span></span> <span data-ttu-id="b6091-110">Дополнительные сведения о взаимодействии и сосуществовании с другими SQL Serverными функциями см [. в статье SQL Server управляемое резервное копирование в Azure: взаимодействие и сосуществование.](../../2014/database-engine/sql-server-managed-backup-to-windows-azure-interoperability-and-coexistence.md)</span><span class="sxs-lookup"><span data-stu-id="b6091-110">For more information on interoperability and coexistence with other SQL Server features, see [SQL Server Managed Backup to Azure: Interoperability and Coexistence](../../2014/database-engine/sql-server-managed-backup-to-windows-azure-interoperability-and-coexistence.md)</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="b6091-111">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="b6091-111">Prerequisites</span></span>  
  
-   <span data-ttu-id="b6091-112">Агент SQL Server должен быть запущен.</span><span class="sxs-lookup"><span data-stu-id="b6091-112">SQL Server Agent should be running.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="b6091-113">Если агент SQL Server останавливаются на какой-то срок, а затем перезапускается, то можно видеть увеличение числа операций резервного копирования в зависимости от длительности промежутка времени между остановкой и запуском SQL Server Agent, а также может возникнуть очередь ожидающих выполнения операций резервного копирования журнала.</span><span class="sxs-lookup"><span data-stu-id="b6091-113">If SQL Server Agent is stopped for a period of time and then restarted, you may see an increased backup activity depending on the length of time elapsed between the stop and start of SQL Agent, and there might be a backlog of log backups waiting to run.</span></span> <span data-ttu-id="b6091-114">Рекомендуется настроить автоматический запуск SQL Server Agent при включении системы.</span><span class="sxs-lookup"><span data-stu-id="b6091-114">Consider configuring SQL Server Agent to start automatically on start up.</span></span>  
  
-   <span data-ttu-id="b6091-115">Учетная запись хранения Azure и учетные данные SQL, в которых хранятся данные проверки подлинности в учетной записи хранения, должны быть созданы перед настройкой [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b6091-115">A Azure storage account and a SQL Credential that stores the authentication information to the storage account should both be created before configuring [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)].</span></span> <span data-ttu-id="b6091-116">Дополнительные сведения см. в разделе [Introduction to Key Components and Concepts](../relational-databases/backup-restore/sql-server-backup-to-url.md#intorkeyconcepts) статьи **Резервное копирование SQL Server в URL** и [Lesson 2: Create a SQL Server Credential](../../2014/tutorials/lesson-2-create-a-sql-server-credential.md).</span><span class="sxs-lookup"><span data-stu-id="b6091-116">For more information see [Introduction to Key Components and Concepts](../relational-databases/backup-restore/sql-server-backup-to-url.md#intorkeyconcepts) section of the **SQL Server Backup to URL** topic, and [Lesson 2: Create a SQL Server Credential](../../2014/tutorials/lesson-2-create-a-sql-server-credential.md).</span></span>  
  
    > [!IMPORTANT]  
    >  [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] <span data-ttu-id="b6091-117">создает необходимые контейнеры для хранения резервных копий.</span><span class="sxs-lookup"><span data-stu-id="b6091-117">creates the necessary containers to store the backups.</span></span> <span data-ttu-id="b6091-118">Имя контейнера создается в формате "имя компьютера-имя экземпляра".</span><span class="sxs-lookup"><span data-stu-id="b6091-118">The container name is created using 'machine name-instance name' format.</span></span> <span data-ttu-id="b6091-119">Для групп доступности AlwaysOn имя контейнера формируется с использованием GUID группы доступности.</span><span class="sxs-lookup"><span data-stu-id="b6091-119">For AlwaysOn Availability Groups the container is named using the GUID of the availability group.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b6091-120">безопасность</span><span class="sxs-lookup"><span data-stu-id="b6091-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b6091-121">Permissions</span><span class="sxs-lookup"><span data-stu-id="b6091-121">Permissions</span></span>  
 <span data-ttu-id="b6091-122">Для запуска хранимых процедур, которые включают [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] , необходимо быть `System Administrator` членом или в роли базы данных **db_backupoperator** с разрешениями **ALTER ANY CREDENTIAL** , а также `EXECUTE` разрешениями на **sp_delete_backuphistory**и `smart_admin.sp_backup_master_switch` хранимых процедурах.</span><span class="sxs-lookup"><span data-stu-id="b6091-122">To run the stored procedures that enable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)], you must be a  either a `System Administrator` or  member  in the **db_backupoperator** database role with **ALTER ANY CREDENTIAL** permissions, and `EXECUTE` permissions on the **sp_delete_backuphistory**, and `smart_admin.sp_backup_master_switch` stored procedures.</span></span>  <span data-ttu-id="b6091-123">Для хранимых процедур и функций, используемых для просмотра имеющихся параметров, обычно требуются разрешения `Execute` для хранимой процедуры и `Select` для функции соответственно.</span><span class="sxs-lookup"><span data-stu-id="b6091-123">Stored procedures and functions used to review the existing settings typically require `Execute` permissions on the stored procedure and `Select` on the function respectively.</span></span>  
  

  
###  <a name="considerations-for-enabling-ss_smartbackup-for-databases-and-instances"></a><a name="Considerations"></a><span data-ttu-id="b6091-124">Рекомендации по включению [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] для баз данных и экземпляров</span><span class="sxs-lookup"><span data-stu-id="b6091-124">Considerations for enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for Databases and Instances</span></span>  
 [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] <span data-ttu-id="b6091-125">можно включить для отдельных баз данных или для всего экземпляра.</span><span class="sxs-lookup"><span data-stu-id="b6091-125">can be enabled for individual databases separately or for the entire instance.</span></span> <span data-ttu-id="b6091-126">Выбор зависит от требований к восстановлению баз данных в экземпляре, требований к управлению несколькими базами данных и экземплярами, а также стратегическим использованием службы хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="b6091-126">The choices depend on the recoverability requirements for the databases on the instance, requirements for managing multiple databases and instances, and using Azure storage strategically.</span></span>  
  
#### <a name="enabling-ss_smartbackup-at-the-database-level"></a><span data-ttu-id="b6091-127">Включение [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] на уровне базы данных</span><span class="sxs-lookup"><span data-stu-id="b6091-127">Enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] at the Database Level</span></span>  
 <span data-ttu-id="b6091-128">Если в базе данных применяются определенные требования для резервного копирования и срока хранения (соглашение об уровне обслуживания для восстановления), отличные от других баз данных в экземпляре, настройте для нее [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] на уровне базы данных.</span><span class="sxs-lookup"><span data-stu-id="b6091-128">If a database has specific requirements for backup and retention period (recoverability SLA) that is different from other databases on the instance, configure [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] at the database level for this database.</span></span> <span data-ttu-id="b6091-129">Настройки на уровне базы данных переопределяют настройки на уровне экземпляра.</span><span class="sxs-lookup"><span data-stu-id="b6091-129">Database level settings override instance level configuration settings.</span></span> <span data-ttu-id="b6091-130">Однако оба этих параметра можно использовать совместно в одном и том же экземпляре.</span><span class="sxs-lookup"><span data-stu-id="b6091-130">However both these options can be used together on the same instance.</span></span> <span data-ttu-id="b6091-131">Далее представлен список преимуществ и рекомендаций, связанных с включением [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] на уровне базы данных.</span><span class="sxs-lookup"><span data-stu-id="b6091-131">Following is a list of advantages and considerations when enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] at the database level.</span></span>  
  
-   <span data-ttu-id="b6091-132">Повышенная точность: раздельные параметры конфигурации для каждой базы данных.</span><span class="sxs-lookup"><span data-stu-id="b6091-132">More granular: Separate configuration settings for each database.</span></span> <span data-ttu-id="b6091-133">Возможность поддержки различных сроков хранения для отдельных баз данных.</span><span class="sxs-lookup"><span data-stu-id="b6091-133">Can support different retention periods for individual databases.</span></span>  
  
-   <span data-ttu-id="b6091-134">Переопределяет параметры уровня экземпляра для базы данных.</span><span class="sxs-lookup"><span data-stu-id="b6091-134">Overrides instance level settings for the database.</span></span>  
  
-   <span data-ttu-id="b6091-135">Может использоваться для сокращения расходов на хранение за счет выбора отдельных баз данных для резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="b6091-135">Can be used to reduce storage costs by selecting individual databases to be backed up.</span></span>  
  
-   <span data-ttu-id="b6091-136">Требует управления каждой базой данных</span><span class="sxs-lookup"><span data-stu-id="b6091-136">Requires managing each database</span></span>  
  
#### <a name="enabling-ss_smartbackup-at-the-instance-level-with-default-settings"></a><span data-ttu-id="b6091-137">Включение [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] на уровне экземпляра с параметрами по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b6091-137">Enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] at the Instance Level with Default Settings</span></span>  
 <span data-ttu-id="b6091-138">Указывайте этот параметр, если большинство баз данных экземпляра имеют одинаковые требования к политикам резервного копирования и хранения или если нужно, чтобы при создании новых экземпляров баз данных для них автоматически создавались резервные копии.</span><span class="sxs-lookup"><span data-stu-id="b6091-138">Use this setting if most of the databases in the instance have the same requirements for backup and retention policies, or if you want new database instances to automatically be backed up on creation.</span></span> <span data-ttu-id="b6091-139">Несколько баз данных, являющихся исключением для политики, по-прежнему можно настроить отдельно.</span><span class="sxs-lookup"><span data-stu-id="b6091-139">A few databases that are exception to the policy can still be configured individually.</span></span> <span data-ttu-id="b6091-140">Далее представлен список преимуществ и рекомендаций, связанных с включением [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] на уровне экземпляра.</span><span class="sxs-lookup"><span data-stu-id="b6091-140">Following is a list of advantages and considerations when enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] at the instance level.</span></span>  
  
-   <span data-ttu-id="b6091-141">Автоматизация на уровне экземпляра: общие параметры применяются автоматически после добавления новых баз данных.</span><span class="sxs-lookup"><span data-stu-id="b6091-141">Automation at the instance level: Common settings applied to automatically for new databases added thereafter.</span></span>  
  
-   <span data-ttu-id="b6091-142">После создания новых баз данных в экземплярах для них автоматически создаются резервные копии</span><span class="sxs-lookup"><span data-stu-id="b6091-142">New databases will be automatically backed up soon after they are created on the instances</span></span>  
  
-   <span data-ttu-id="b6091-143">Можно применять к базам данных с одинаковыми требованиями срока хранения.</span><span class="sxs-lookup"><span data-stu-id="b6091-143">Can be applied to databases that have the same retention period requirements.</span></span>  
  
-   <span data-ttu-id="b6091-144">Можно настроить отдельные базы данных с разными сроками хранения, даже если функция [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] включена на уровне экземпляра с параметрами по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b6091-144">You can still configure individual databases that require a different retention period even with [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] backup enabled at in instance level with default settings.</span></span> <span data-ttu-id="b6091-145">Вы также можете отключить [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] для баз данных, если вы не планируете использовать службу хранилища Azure для резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="b6091-145">You can also disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for databases if you do not intend to use Azure storage for the backups.</span></span>  
  
##  <a name="enable-and-configure-ss_smartbackup-for-a-database"></a><a name="DatabaseConfigure"></a><span data-ttu-id="b6091-146">Включение и настройка [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] для базы данных</span><span class="sxs-lookup"><span data-stu-id="b6091-146">Enable and Configure [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for a Database</span></span>  
 <span data-ttu-id="b6091-147">Системная хранимая процедура `smart_admin.sp_set_db_backup` используется для включения компонента [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] в указанной базе данных.</span><span class="sxs-lookup"><span data-stu-id="b6091-147">The system stored procedure `smart_admin.sp_set_db_backup` is used to enable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for a specific database.</span></span> <span data-ttu-id="b6091-148">При первом включении компонента [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] в базе данных необходимо, помимо включения [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)], указать следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="b6091-148">When [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is enabled for the first time on the database, the following information must be specified in addition to enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]:</span></span>  
  
-   <span data-ttu-id="b6091-149">Имя базы данных.</span><span class="sxs-lookup"><span data-stu-id="b6091-149">The name of the database.</span></span>  
  
-   <span data-ttu-id="b6091-150">Срок хранения.</span><span class="sxs-lookup"><span data-stu-id="b6091-150">The retention period.</span></span>  
  
-   <span data-ttu-id="b6091-151">Учетные данные SQL, используемые для проверки подлинности в учетной записи хранения Azure.</span><span class="sxs-lookup"><span data-stu-id="b6091-151">SQL Credential used to authenticate to the Azure storage account.</span></span>  
  
-   <span data-ttu-id="b6091-152">Либо укажите не шифровать с помощью \* \@ encryption_algorithm\*  =  **NO_ENCRYPTION** , либо укажите поддерживаемый алгоритм шифрования.</span><span class="sxs-lookup"><span data-stu-id="b6091-152">Either specify not to encrypt using *\@encryption_algorithm* = **NO_ENCRYPTION** or specify a supported encryption algorithm.</span></span> <span data-ttu-id="b6091-153">Дополнительные сведения о шифровании см. в разделе [Backup Encryption](../relational-databases/backup-restore/backup-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="b6091-153">For more information on encryption, see [Backup Encryption](../relational-databases/backup-restore/backup-encryption.md).</span></span>  
  
 [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] <span data-ttu-id="b6091-154">для настройки на уровне базы данных поддерживается только через Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="b6091-154">for database level configuration is only supported through Transact-SQL.</span></span>  
  
 <span data-ttu-id="b6091-155">После включения [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] для базы данных эти сведения сохраняются.</span><span class="sxs-lookup"><span data-stu-id="b6091-155">Once [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is enabled for a database this information is persisted.</span></span> <span data-ttu-id="b6091-156">При изменении конфигурации необходимы только имя базы данных и изменяемый параметр; службы [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] сохраняют существующие значения для прочих параметров, если они не указаны.</span><span class="sxs-lookup"><span data-stu-id="b6091-156">If you are changing the configuration, only the database name and the setting you want to change is required, [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] retains the existing values for other parameters when not specified.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b6091-157">Перед настройкой функции [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] для базы данных может быть полезно проверить наличие существующей конфигурации, если таковая имеется.</span><span class="sxs-lookup"><span data-stu-id="b6091-157">Before configuring [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] on a database it might be useful to existing configuration if any.</span></span> <span data-ttu-id="b6091-158">Анализ параметров конфигурации для базы данных описывается далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="b6091-158">The step to reviewing configuration settings for a database is explained later in this section.</span></span>  
  
-   <span data-ttu-id="b6091-159">**Использование Transact-SQL:**</span><span class="sxs-lookup"><span data-stu-id="b6091-159">**Using Transact-SQL:**</span></span>  
  
     <span data-ttu-id="b6091-160">При первом включении [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] обязательных параметров являются: \* \@ database_name*, \* \@ credential_name*, \* \@ encryption_algorithm*, \* \@ enable_backup* параметр \* \@ storage_url\* является необязательным.</span><span class="sxs-lookup"><span data-stu-id="b6091-160">If you are enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for the first time, the required parameters are: *\@database_name*, *\@credential_name*, *\@encryption_algorithm*,  *\@enable_backup* The *\@storage_url* parameter is optional.</span></span> <span data-ttu-id="b6091-161">Если не указать значение для @storage_url параметра, значение будет получено с использованием сведений об учетной записи хранения из учетных данных SQL.</span><span class="sxs-lookup"><span data-stu-id="b6091-161">If you do not provide a value for  the @storage_url parameter, the value is derived using the storage account information from the SQL Credential.</span></span> <span data-ttu-id="b6091-162">При предоставлении URL-адреса хранилища следует предоставлять только корневой URL-адрес для учетной записи хранения, который должен соответствовать предоставленным учетным данным SQL.</span><span class="sxs-lookup"><span data-stu-id="b6091-162">If you provide the storage URL you should only provide the URL for the root of the storage account, and must match the information in the SQL Credential you specified.</span></span>  
  
    1.  <span data-ttu-id="b6091-163">Установите соединение с компонентом [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6091-163">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
    2.  <span data-ttu-id="b6091-164">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="b6091-164">From the Standard bar, click **New Query**.</span></span>  
  
    3.  <span data-ttu-id="b6091-165">Скопируйте и вставьте следующий пример в окно запроса и нажмите кнопку `Execute` .</span><span class="sxs-lookup"><span data-stu-id="b6091-165">Copy and paste the following example into the query window and click `Execute`.</span></span> <span data-ttu-id="b6091-166">Этот пример включает [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] для базы данных "TestDB".</span><span class="sxs-lookup"><span data-stu-id="b6091-166">This example enables [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for the database 'TestDB'.</span></span> <span data-ttu-id="b6091-167">Срок хранения — 30 дней.</span><span class="sxs-lookup"><span data-stu-id="b6091-167">The retention period is set to 30 days.</span></span> <span data-ttu-id="b6091-168">Этот пример использует параметр шифрования с указанием алгоритма шифрования и сведений о шифраторе.</span><span class="sxs-lookup"><span data-stu-id="b6091-168">This sample uses the encryption option by specifying the encryption algorithm and the encryptor information.</span></span>  
  
    ```sql
    Use msdb;  
    GO  
    EXEC smart_admin.sp_set_db_backup   
                    @database_name='TestDB'   
                    ,@enable_backup=1  
                    ,@retention_days =30   
                    ,@credential_name ='MyCredential'  
                    ,@encryption_algorithm ='AES_256'  
                    ,@encryptor_type= 'Certificate'  
                    ,@encryptor_name='MyBackupCert'  
    GO
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="b6091-169">Для срока хранения может быть задано любое значение от 1 до 30 дней.</span><span class="sxs-lookup"><span data-stu-id="b6091-169">The retention period can be set to any value from 1 to 30 days.</span></span>  
    >   
    >  <span data-ttu-id="b6091-170">Дополнительные сведения о создании сертификата для шифрования см. в пункте «Создание резервной копии сертификата» в разделе [Create an Encrypted Backup](../relational-databases/backup-restore/create-an-encrypted-backup.md).</span><span class="sxs-lookup"><span data-stu-id="b6091-170">For more information on creating a certificate for encryption, see the Create a Backup Certificate step in [Create an Encrypted Backup](../relational-databases/backup-restore/create-an-encrypted-backup.md).</span></span>  
  
     <span data-ttu-id="b6091-171">Дополнительные сведения об этой хранимой процедуре см. в разделе [smart_admin. set_db_backup &#40;Transact-SQL&#41;](https://msdn.microsoft.com/library/dn451013(v=sql.120).aspx)</span><span class="sxs-lookup"><span data-stu-id="b6091-171">For more information on this stored procedure, see [smart_admin.set_db_backup &#40;Transact-SQL&#41;](https://msdn.microsoft.com/library/dn451013(v=sql.120).aspx)</span></span>  
  
     <span data-ttu-id="b6091-172">Чтобы просмотреть параметры конфигурации базы данных, используйте следующий запрос.</span><span class="sxs-lookup"><span data-stu-id="b6091-172">To review the configuration settings for a database use the following query:</span></span>  
  
    ```sql
    Use msdb  
    GO  
    SELECT * FROM smart_admin.fn_backup_db_config('TestDB')  
    ```  
  
##  <a name="enable-and-configure-default-ss_smartbackup-settings-for-the-instance"></a><a name="InstanceConfigure"></a><span data-ttu-id="b6091-173">Включение и Настройка параметров по умолчанию [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] для экземпляра</span><span class="sxs-lookup"><span data-stu-id="b6091-173">Enable and Configure Default [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] settings for the Instance</span></span>  
 <span data-ttu-id="b6091-174">Включить и настроить параметры по умолчанию [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] на уровне экземпляра можно двумя способами: с помощью системной хранимой процедуры `smart_admin.set_instance_backup` или **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="b6091-174">You can enable and configure default [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] settings at the instance level in two ways:  By using the system stored procedure `smart_admin.set_instance_backup` or **SQL Server Management Studio**.</span></span> <span data-ttu-id="b6091-175">Далее описаны два этих способа.</span><span class="sxs-lookup"><span data-stu-id="b6091-175">The two methods are explained below:</span></span>  
  
 <span data-ttu-id="b6091-176">**smart_admin. set_instance_backup:**.</span><span class="sxs-lookup"><span data-stu-id="b6091-176">**smart_admin.set_instance_backup:**.</span></span> <span data-ttu-id="b6091-177">Указав значение **1** для параметра \* \@ enable_backup\* , можно включить резервное копирование и задать конфигурации по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b6091-177">By specifying the value **1** for *\@enable_backup* parameter, you can enable backup and set the default configurations.</span></span> <span data-ttu-id="b6091-178">После применения параметров по умолчанию на уровне экземпляра они применяются к новой базе данных, добавляемой к этому экземпляру.</span><span class="sxs-lookup"><span data-stu-id="b6091-178">Once applied at the instance level, these default settings are applied to any new database that is added to this instance.</span></span>  <span data-ttu-id="b6091-179">При первом включении компонента [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] необходимо, помимо включения [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] в экземпляре, указать следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="b6091-179">When [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is enabled for the first time, the following information must be provided in addition to enabling [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] on the instance:</span></span>  
  
-   <span data-ttu-id="b6091-180">Срок хранения.</span><span class="sxs-lookup"><span data-stu-id="b6091-180">The retention period.</span></span>  
  
-   <span data-ttu-id="b6091-181">Учетные данные SQL, используемые для проверки подлинности в учетной записи хранения Azure.</span><span class="sxs-lookup"><span data-stu-id="b6091-181">SQL Credential used to authenticate to the Azure storage account.</span></span>  
  
-   <span data-ttu-id="b6091-182">Параметр Encryption.</span><span class="sxs-lookup"><span data-stu-id="b6091-182">The encryption option.</span></span> <span data-ttu-id="b6091-183">Либо укажите не шифровать с помощью \* \@ encryption_algorithm\*  =  **NO_ENCRYPTION** , либо укажите поддерживаемый алгоритм шифрования.</span><span class="sxs-lookup"><span data-stu-id="b6091-183">Either specify not to encrypt using *\@encryption_algorithm* = **NO_ENCRYPTION** or specify a supported encryption algorithm.</span></span> <span data-ttu-id="b6091-184">Дополнительные сведения о шифровании см. в разделе [Backup Encryption](../relational-databases/backup-restore/backup-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="b6091-184">For more information on encryption, see [Backup Encryption](../relational-databases/backup-restore/backup-encryption.md).</span></span>  
  
 <span data-ttu-id="b6091-185">После активации эти настройки сохраняются.</span><span class="sxs-lookup"><span data-stu-id="b6091-185">Once enabled these settings are persisted.</span></span> <span data-ttu-id="b6091-186">При изменении конфигурации необходимо указать только имя базы данных и имя настраиваемого параметра.</span><span class="sxs-lookup"><span data-stu-id="b6091-186">If you are changing the configuration, only the database name and the setting you want to change is required.</span></span> [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] <span data-ttu-id="b6091-187">сохраняет существующие значения, если не заданы новые.</span><span class="sxs-lookup"><span data-stu-id="b6091-187">retains the existing values when not specified.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b6091-188">Перед настройкой функции [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] для экземпляра может быть полезно проверить наличие существующей конфигурации, если таковая имеется.</span><span class="sxs-lookup"><span data-stu-id="b6091-188">Before configuring [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] on an instance, it might be useful to check for existing configuration, if any.</span></span> <span data-ttu-id="b6091-189">Анализ параметров конфигурации для базы данных описывается далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="b6091-189">The step to reviewing configuration settings for a database is explained later in this section.</span></span>  
  
 <span data-ttu-id="b6091-190">**SQL Server Management Studio:** для выполнения этой задачи в среде SQL Server Management Studio перейдите в обозреватель объектов, разверните узел **Управление** и нажмите правой кнопкой мыши **Управляемое резервное копирование**.</span><span class="sxs-lookup"><span data-stu-id="b6091-190">**SQL Server Management Studio:** To do this task in SQL Server Management Studio, go the object explorer, expand the **Management** node, and right click on **Managed Backup**.</span></span> <span data-ttu-id="b6091-191">Нажмите кнопку **Настроить**.</span><span class="sxs-lookup"><span data-stu-id="b6091-191">Select **Configure**.</span></span> <span data-ttu-id="b6091-192">Откроется диалоговое окно **Управляемое резервное копирование** .</span><span class="sxs-lookup"><span data-stu-id="b6091-192">This opens the **Managed Backup** dialog.</span></span> <span data-ttu-id="b6091-193">В этом диалоговом окне укажите срок хранения, учетные данные SQL, URL-адрес хранилища и параметры шифрования.</span><span class="sxs-lookup"><span data-stu-id="b6091-193">Use this dialog to specify the retention period, SQL Credential, Storage URL, and the encryption settings.</span></span> <span data-ttu-id="b6091-194">Конкретная Справка по этому диалоговому окну см. в статье [Настройка управляемого &#40;резервного копирования SQL Server Management Studio&#41;](configure-managed-backup-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="b6091-194">For specific help with this dialog, see [Configure Managed Backup &#40;SQL Server Management Studio&#41;](configure-managed-backup-sql-server-management-studio.md).</span></span>  
  
#### <a name="using-transact-sql"></a><span data-ttu-id="b6091-195">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b6091-195">Using Transact-SQL</span></span>  
  
1.  <span data-ttu-id="b6091-196">Установите соединение с компонентом [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6091-196">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b6091-197">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="b6091-197">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b6091-198">Скопируйте и вставьте следующий пример в окно запроса и нажмите кнопку `Execute` .</span><span class="sxs-lookup"><span data-stu-id="b6091-198">Copy and paste the following example into the query window and click `Execute`.</span></span>  
  
```sql
Use msdb;  
Go  
   EXEC smart_admin.sp_set_instance_backup  
                @retention_days=30   
                ,@credential_name='sqlbackuptoURL'  
                ,@encryption_algorithm ='AES_128'  
                ,@encryptor_type= 'Certificate'  
                ,@encryptor_name='MyBackupCert'  
                ,@enable_backup=1;  
GO  
  
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b6091-199">Для срока хранения может быть задано любое значение от 1 до 30 дней.</span><span class="sxs-lookup"><span data-stu-id="b6091-199">The retention period can be set to any value from 1 to 30 days.</span></span>  
>   
>  <span data-ttu-id="b6091-200">Дополнительные сведения о создании сертификата для шифрования см. в пункте «Создание резервной копии сертификата» в разделе [Create an Encrypted Backup](../relational-databases/backup-restore/create-an-encrypted-backup.md).</span><span class="sxs-lookup"><span data-stu-id="b6091-200">For more information on creating a certificate for encryption, see the Create a Backup Certificate step in [Create an Encrypted Backup](../relational-databases/backup-restore/create-an-encrypted-backup.md).</span></span>  
  
 <span data-ttu-id="b6091-201">Чтобы просмотреть параметры конфигурации по умолчанию для экземпляра, используйте следующий запрос.</span><span class="sxs-lookup"><span data-stu-id="b6091-201">To view the default configuration settings for the instance, use the following query:</span></span>  
  
```sql
Use msdb;  
GO  
SELECT * FROM smart_admin.fn_backup_instance_config ();
```  
  
#### <a name="using-powershell"></a><span data-ttu-id="b6091-202">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="b6091-202">Using PowerShell</span></span>  
  
1.  <span data-ttu-id="b6091-203">Запуск экземпляра PowerShell</span><span class="sxs-lookup"><span data-stu-id="b6091-203">Start a PowerShell Instance</span></span>  
  
2.  <span data-ttu-id="b6091-204">Запустите следующий скрипт, изменив его в соответствии с собственными настройками</span><span class="sxs-lookup"><span data-stu-id="b6091-204">Run the following script after modifying it to suit your settings</span></span>  
  
    ```powershell
    cd SQLSERVER:\SQL\Computer\MyInstance
    $encryptionOption = New-SqlBackupEncryptionOption -EncryptionAlgorithm Aes128 -EncryptorType ServerCertificate -EncryptorName "MyBackupCert"  
    Get-SqlSmartAdmin | Set-SqlSmartAdmin -BackupEnabled $True -BackupRetentionPeriodInDays 10 -EncryptionOption $encryptionOption  
    ```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b6091-205">При создании базы данных после настройки параметров по умолчанию для их применения может потребоваться до 15 минут.</span><span class="sxs-lookup"><span data-stu-id="b6091-205">When you create a new database after configuring the default settings, it may take up to 15 minutes for the database to be configured with the default settings.</span></span> <span data-ttu-id="b6091-206">Это также применимо к базам данных, измененных с **Simple** на **Full** модель восстановления или на **Bulk-Logged** .</span><span class="sxs-lookup"><span data-stu-id="b6091-206">This also applies to databases that are changed from **Simple** to **Full** or **Bulk-Logged** recovery model.</span></span>  
  
##  <a name="disable-ss_smartbackup-for-a-database"></a><a name="DatabaseDisable"></a> <span data-ttu-id="b6091-207">Отключение [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] для базы данных</span><span class="sxs-lookup"><span data-stu-id="b6091-207">Disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for a database</span></span>  
 <span data-ttu-id="b6091-208">Настройки [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] можно отключить с помощью системной хранимой процедуры `sp_set_db_backup`.</span><span class="sxs-lookup"><span data-stu-id="b6091-208">You can disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] settings by using the `sp_set_db_backup` system stored procedure.</span></span> <span data-ttu-id="b6091-209">\* \@ Enableparameter служит\* используется для включения и отключения [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] конфигураций для конкретной базы данных, где 1 включает и 0 отключает параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b6091-209">The *\@enableparameter* is used to enable and disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] configurations for a specific database, where 1 enables and 0 disables the configuration settings.</span></span>  
  
#### <a name="to-disable-ss_smartbackup-for-a-specific-database"></a><span data-ttu-id="b6091-210">Чтобы отключить [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] для конкретной базы данных, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="b6091-210">To Disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for a specific database:</span></span>  
  
1.  <span data-ttu-id="b6091-211">Установите соединение с компонентом [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6091-211">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b6091-212">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="b6091-212">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b6091-213">Скопируйте и вставьте следующий пример в окно запроса и нажмите кнопку `Execute` .</span><span class="sxs-lookup"><span data-stu-id="b6091-213">Copy and paste the following example into the query window and click `Execute`.</span></span>  
  
```sql
Use msdb;  
Go  
EXEC smart_admin.sp_set_db_backup   
                @database_name='TestDB'   
                ,@enable_backup=0;  
GO
```  
  
##  <a name="disable-ss_smartbackup-for-all-the-databases-on-the-instance"></a><a name="DatabaseAllDisable"></a> <span data-ttu-id="b6091-214">Отключение [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] для всех баз данных в экземпляре</span><span class="sxs-lookup"><span data-stu-id="b6091-214">Disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] for all the databases on the Instance</span></span>  
 <span data-ttu-id="b6091-215">Следующая процедура позволяет отключить параметры конфигурации [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] для всех баз данных, для которых функция [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] включена в экземпляре.</span><span class="sxs-lookup"><span data-stu-id="b6091-215">The following procedure is for when you want to disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] configuration settings from all the databases that currently have [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] enabled on the instance.</span></span>  <span data-ttu-id="b6091-216">Такие параметры конфигурации, как URL-адрес хранилища, политика хранения и учетные данные SQL, сохранятся в метаданных, и их можно будет использовать, если функция [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] будет включена для базы данных в дальнейшем.</span><span class="sxs-lookup"><span data-stu-id="b6091-216">The configuration settings like the storage URL, retention, and the SQL Credential will remain in the metadata and can be used  if [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is enabled for the database at a later time.</span></span> <span data-ttu-id="b6091-217">Если нужно просто временно приостановить службы [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] , то можно вызвать основной переключатель, описанный далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="b6091-217">If you want to just pause [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] services temporarily, you can use the master switch explained in the following sections later in this topic.</span></span>  
  
#### <a name="to-disable-ss_smartbackupfor-all-the-databases"></a><span data-ttu-id="b6091-218">Чтобы отключить [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]для всех баз данных, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="b6091-218">To disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)]for all the databases:</span></span>  
  
1.  <span data-ttu-id="b6091-219">Установите соединение с компонентом [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6091-219">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b6091-220">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="b6091-220">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b6091-221">Скопируйте и вставьте следующий пример в окно запроса и нажмите кнопку `Execute` .</span><span class="sxs-lookup"><span data-stu-id="b6091-221">Copy and paste the following example into the query window and click `Execute`.</span></span> <span data-ttu-id="b6091-222">Следующий пример определяет, настроена ли функция [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] на уровне экземпляра и во всех базах данных с активированной функцией [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)], а затем выполняет хранимую процедуру `sp_set_db_backup` для отключения [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6091-222">The following example identifies if [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is configured at the instance level and all the [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] enabled databases on the instance, and executes the system stored procedure `sp_set_db_backup` to disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)].</span></span>  
  
```sql
-- Create a working table to store the database names  
Declare @DBNames TABLE  
  
       (  
             RowID int IDENTITY PRIMARY KEY  
             ,DBName varchar(500)  
  
       )  
-- Define the variables  
DECLARE @rowid int  
DECLARE @dbname varchar(500)  
DECLARE @SQL varchar(2000)  
-- Get the database names from the system function  
  
INSERT INTO @DBNames (DBName)  
  
SELECT db_name  
       FROM
  
       smart_admin.fn_backup_db_config (NULL)  
       WHERE is_smart_backup_enabled = 1  
  
       --Select DBName from @DBNames 
       select @rowid = min(RowID) FROM @DBNames  
  
       WHILE @rowID IS NOT NULL  
       Begin
             Set @dbname = (Select DBName From @DBNames Where RowID = @rowid)  
             Begin  
             Set @SQL = 'EXEC smart_admin.sp_set_db_backup    
                @database_name= '''+'' + @dbname+ ''+''',   
                @enable_backup=0'  
  
            EXECUTE (@SQL)  
  
             END  
             Select @rowid = min(RowID)  
             From @DBNames Where RowID > @rowid  
  
       END
```  
  
 <span data-ttu-id="b6091-223">Чтобы просмотреть параметры конфигурации для всех баз данных в экземпляре, выполните следующий запрос.</span><span class="sxs-lookup"><span data-stu-id="b6091-223">To review the configuration settings for all the databases on the instance, use the following query:</span></span>  
  
```sql
Use msdb;  
GO  
SELECT * FROM smart_admin.fn_backup_db_config (NULL);  
GO
```  
  
##  <a name="disable-default-ss_smartbackup-settings-for-the-instance"></a><a name="InstanceDisable"></a> <span data-ttu-id="b6091-224">Отключение параметров [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] по умолчанию для экземпляра</span><span class="sxs-lookup"><span data-stu-id="b6091-224">Disable Default [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] settings for the Instance</span></span>  
 <span data-ttu-id="b6091-225">Параметры по умолчанию на уровне экземпляра применяются ко всем новым базам данных, созданным в этом экземпляре.</span><span class="sxs-lookup"><span data-stu-id="b6091-225">Default settings at the instance level apply to all new databases created on that instance.</span></span>  <span data-ttu-id="b6091-226">Если параметры по умолчанию больше не нужны, то можно отключить эту конфигурацию с помощью системной хранимой процедуры **smart_admin.sp_set_instance_backup** .</span><span class="sxs-lookup"><span data-stu-id="b6091-226">If you no longer need or require default settings, you can disable this configuration by using the **smart_admin.sp_set_instance_backup** System stored procedure.</span></span> <span data-ttu-id="b6091-227">При отключении остальные параметры конфигурации, такие как URL-адрес хранилища, политика хранения или учетные данные SQL, не удаляются.</span><span class="sxs-lookup"><span data-stu-id="b6091-227">Disabling does not remove the other configuration settings like the storage URL, retention setting, or the SQL Credential name.</span></span> <span data-ttu-id="b6091-228">Эти настройки используются в том случае, если функция [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] будет включена для экземпляра позднее.</span><span class="sxs-lookup"><span data-stu-id="b6091-228">These settings will be used if [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] is enabled for the instance at a later time.</span></span>  
  
#### <a name="to-disable-ss_smartbackup-default-configuration-settings"></a><span data-ttu-id="b6091-229">Чтобы отключить параметры конфигурации [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] по умолчанию, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="b6091-229">To disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] default configuration settings:</span></span>  
  
1.  <span data-ttu-id="b6091-230">Установите соединение с компонентом [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6091-230">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b6091-231">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="b6091-231">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b6091-232">Скопируйте и вставьте следующий пример в окно запроса и нажмите кнопку `Execute` .</span><span class="sxs-lookup"><span data-stu-id="b6091-232">Copy and paste the following example into the query window and click `Execute`.</span></span>  
  
    ```sql
    Use msdb;  
    Go  
    EXEC smart_admin.sp_set_instance_backup  
                    @enable_backup=0;  
    GO
    ```  
  
#### <a name="using-powershell"></a><span data-ttu-id="b6091-233">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="b6091-233">Using PowerShell</span></span>  
  
1.  <span data-ttu-id="b6091-234">Запуск экземпляра PowerShell</span><span class="sxs-lookup"><span data-stu-id="b6091-234">Start a PowerShell Instance</span></span>  
  
2.  <span data-ttu-id="b6091-235">Выполните следующий скрипт:</span><span class="sxs-lookup"><span data-stu-id="b6091-235">Run the following script:</span></span>  
  
    ```powershell
    cd SQLSERVER:\SQL\Computer\MyInstance
    Set-SqlSmartAdmin -BackupEnabled $False  
    ```  
  
##  <a name="pause-ss_smartbackup-at-the-instance-level"></a><a name="InstancePause"></a> <span data-ttu-id="b6091-236">Приостановка [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] на уровне экземпляра</span><span class="sxs-lookup"><span data-stu-id="b6091-236">Pause [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] at the Instance Level</span></span>  
 <span data-ttu-id="b6091-237">Возможны ситуации, когда требуется приостановить службы [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] на короткий период времени.</span><span class="sxs-lookup"><span data-stu-id="b6091-237">There might be times when you need to temporarily pause the [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] services for a short period time.</span></span>  <span data-ttu-id="b6091-238">Системная хранимая процедура `smart_admin.sp_backup_master_switch` позволяет отключить службу [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] на уровне экземпляра.</span><span class="sxs-lookup"><span data-stu-id="b6091-238">The `smart_admin.sp_backup_master_switch` system stored procedure allows you to disable [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] service at the instance level.</span></span>  <span data-ttu-id="b6091-239">Та же хранимая процедура используется для возобновления [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6091-239">The same stored procedure is used to resume [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)].</span></span> <span data-ttu-id="b6091-240">Параметр @state определяет, следует ли включить или отключить [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6091-240">The @state parameter is used to define whether [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] should be turned off or on.</span></span>  
  
#### <a name="to-pause-ss_smartbackup-services-using-transact-sql"></a><span data-ttu-id="b6091-241">Чтобы приостановить службы [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] с помощью Transact-SQL, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="b6091-241">To Pause [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] Services Using Transact-SQL:</span></span>  
  
1.  <span data-ttu-id="b6091-242">Установите соединение с компонентом [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6091-242">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b6091-243">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="b6091-243">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b6091-244">Скопируйте и вставьте следующий пример в окно запроса, а затем нажмите кнопку`Execute`</span><span class="sxs-lookup"><span data-stu-id="b6091-244">Copy and paste the following example into the query window and then click `Execute`</span></span>  
  
```sql
Use msdb;  
GO  
EXEC smart_admin.sp_backup_master_switch @new_state=0;  
Go  
  
```  
  
#### <a name="to-pause-ss_smartbackup-using-powershell"></a><span data-ttu-id="b6091-245">Приостановка [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="b6091-245">To pause [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] Using PowerShell</span></span>  
  
1.  <span data-ttu-id="b6091-246">Запуск экземпляра PowerShell</span><span class="sxs-lookup"><span data-stu-id="b6091-246">Start a PowerShell Instance</span></span>  
  
2.  <span data-ttu-id="b6091-247">Запустите следующий скрипт, изменив его в соответствии с собственными настройками</span><span class="sxs-lookup"><span data-stu-id="b6091-247">Run the following script after you modify it to suit your settings</span></span>  
  
    ```powershell
    cd SQLSERVER:\SQL\Computer\MyInstance
    Get-SqlSmartAdmin | Set-SqlSmartAdmin -MasterSwitch $False  
    ```  
  
#### <a name="to-resume-ss_smartbackup-using-transact-sql"></a><span data-ttu-id="b6091-248">Возобновление работы [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] с помощью Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b6091-248">To resume [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] Using Transact-SQL</span></span>  
  
1.  <span data-ttu-id="b6091-249">Установите соединение с компонентом [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6091-249">Connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b6091-250">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="b6091-250">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b6091-251">Скопируйте и вставьте следующий пример в окно запроса и нажмите кнопку `Execute` .</span><span class="sxs-lookup"><span data-stu-id="b6091-251">Copy and paste the following example into the query window and then click `Execute`.</span></span>  
  
```sql
Use msdb;  
Go  
EXEC smart_admin. sp_backup_master_switch @new_state=1;  
GO
```  
  
#### <a name="to-resume-ss_smartbackup-using-powershell"></a><span data-ttu-id="b6091-252">Возобновление [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="b6091-252">To resume [!INCLUDE[ss_smartbackup](../includes/ss-smartbackup-md.md)] Using PowerShell</span></span>  
  
1.  <span data-ttu-id="b6091-253">Запуск экземпляра PowerShell</span><span class="sxs-lookup"><span data-stu-id="b6091-253">Start a PowerShell Instance</span></span>  
  
2.  <span data-ttu-id="b6091-254">Запустите следующий скрипт, изменив его в соответствии с собственными настройками</span><span class="sxs-lookup"><span data-stu-id="b6091-254">Run the following script after you modify it to suit your settings</span></span>  
  
    ```powershell
    cd SQLSERVER:\SQL\Computer\MyInstance
    Get-SqlSmartAdmin | Set-SqlSmartAdmin -MasterSwitch $True  
    ```  
