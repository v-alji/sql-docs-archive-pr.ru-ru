---
title: Настройка репликации для групп доступности AlwaysOn (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], interoperability
- replication [SQL Server], AlwaysOn Availability Groups
ms.assetid: 4e001426-5ae0-4876-85ef-088d6e3fb61c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 916458d2d6b8fbba81940257ee85ffe014d1f12e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729830"
---
# <a name="configure-replication-for-always-on-availability-groups-sql-server"></a><span data-ttu-id="74855-102">Настройка репликации для групп доступности AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="74855-102">Configure Replication for Always On Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="74855-103">Настройка репликации [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] и групп доступности AlwaysOn включает в себя семь шагов.</span><span class="sxs-lookup"><span data-stu-id="74855-103">Configuring [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] replication and AlwaysOn availability groups involves seven steps.</span></span> <span data-ttu-id="74855-104">Каждый шаг более подробно описывается в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="74855-104">Each step is described in more detail in the following sections.</span></span>  

##  <a name="1-configure-the-database-publications-and-subscriptions"></a><a name="step1"></a> <span data-ttu-id="74855-105">1. Настройка публикаций и подписок баз данных</span><span class="sxs-lookup"><span data-stu-id="74855-105">1. Configure the Database Publications and Subscriptions</span></span>  

### <a name="configure-the-distributor"></a><span data-ttu-id="74855-106">Настройка распространителя</span><span class="sxs-lookup"><span data-stu-id="74855-106">Configure the distributor</span></span>
  
 <span data-ttu-id="74855-107">Распространитель не должен являться узлом для любых существующих (или будущих) реплик группы доступности, членом которых является (или будет) база данных публикации.</span><span class="sxs-lookup"><span data-stu-id="74855-107">The distributor should not be a host for any of the current (or intended) replicas of the availability group that the publishing database is (or will become) a member of.</span></span>  
  
1.  <span data-ttu-id="74855-108">Настройка распространения на распространителе.</span><span class="sxs-lookup"><span data-stu-id="74855-108">Configure distribution at the distributor.</span></span> <span data-ttu-id="74855-109">Если хранимые процедуры используются для настройки, запустите `sp_adddistributor`.</span><span class="sxs-lookup"><span data-stu-id="74855-109">If stored procedures are being used for configuration, run `sp_adddistributor`.</span></span> <span data-ttu-id="74855-110">Используйте *@password* параметр, чтобы указать пароль, который будет использоваться при подключении удаленного издателя к распространителю.</span><span class="sxs-lookup"><span data-stu-id="74855-110">Use the *@password* parameter to identify the password that will be used when a remote publisher connects to the distributor.</span></span> <span data-ttu-id="74855-111">Кроме того, пароль понадобится для каждого удаленного издателя при настройке удаленного распространителя.</span><span class="sxs-lookup"><span data-stu-id="74855-111">The password will also be needed at each remote publisher when the remote distributor is set up.</span></span>  
  
    ```sql
    USE master;  
    GO  
    EXEC sys.sp_adddistributor  
        @distributor = 'MyDistributor',  
        @password = '**Strong password for distributor**';  
    ```  
  
2.  <span data-ttu-id="74855-112">Создайте базу данных распространителя на распространителе.</span><span class="sxs-lookup"><span data-stu-id="74855-112">Create the distribution database at the distributor.</span></span> <span data-ttu-id="74855-113">Если хранимые процедуры используются для настройки, запустите `sp_adddistributiondb`.</span><span class="sxs-lookup"><span data-stu-id="74855-113">If stored procedures are being used for configuration, run `sp_adddistributiondb`.</span></span>  
  
    ```  
    USE master;  
    GO  
    EXEC sys.sp_adddistributiondb  
        @database = 'distribution',  
        @security_mode = 1;  
    ```  
  
3.  <span data-ttu-id="74855-114">Настройка удаленного издателя.</span><span class="sxs-lookup"><span data-stu-id="74855-114">Configure the remote publisher.</span></span> <span data-ttu-id="74855-115">Если хранимые процедуры используются для настройки распространителя, запустите `sp_adddistpublisher`.</span><span class="sxs-lookup"><span data-stu-id="74855-115">If stored procedures are being used to configure the distributor, run `sp_adddistpublisher`.</span></span> <span data-ttu-id="74855-116">*@security_mode*Параметр используется для определения того, как хранимая процедура проверки издателя, выполняемая из агентов репликации, подключается к текущей первичной реплике.</span><span class="sxs-lookup"><span data-stu-id="74855-116">The *@security_mode* parameter is used to determine how the publisher validation stored procedure that is run from the replication agents, connects to the current primary.</span></span> <span data-ttu-id="74855-117">Если значение равно 1, то для подключения к текущей первичной реплике будет использоваться проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="74855-117">If set to 1 Windows authentication is used to connect to the current primary.</span></span> <span data-ttu-id="74855-118">Если задано значение 0, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] используется проверка подлинности с указанными *@login* *@password* значениями и.</span><span class="sxs-lookup"><span data-stu-id="74855-118">If set to 0, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] authentication is used with the specified *@login* and *@password* values.</span></span> <span data-ttu-id="74855-119">Указанное имя входа и пароль должны быть действительными на каждой вторичной реплике для хранимой процедуры проверки в целях успешного подключения к этой реплике.</span><span class="sxs-lookup"><span data-stu-id="74855-119">The login and password specified must be valid at each secondary replica for the validation stored procedure to successfully connect to that replica.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="74855-120">Если какие-либо измененные агенты репликации будут работать на компьютере, отличном от распространителя, использование проверки подлинности Windows для подключения к первичной реплике потребует проверки подлинности Kerberos, настроенной для передачи данных между главными компьютерами реплик.</span><span class="sxs-lookup"><span data-stu-id="74855-120">If any modified replication agents run on a computer other than the distributor, use of Windows authentication for the connection to the primary will require Kerberos authentication to be configured for the communication between the replica host computers.</span></span> <span data-ttu-id="74855-121">Использование имени входа [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] для соединения с текущей первичной репликой не потребует проверки подлинности Kerberos.</span><span class="sxs-lookup"><span data-stu-id="74855-121">Use of a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] login for the connection to the current primary will not require Kerberos authentication.</span></span>  
  
    ```sql
    USE master;  
    GO  
    EXEC sys.sp_adddistpublisher  
        @publisher = 'AGPrimaryReplicaHost',  
        @distribution_db = 'distribution',  
        @working_directory = '\\MyReplShare\WorkingDir',  
        @login = 'MyPubLogin',  
        @password = '**Strong password for publisher**';  
    ```  
  
 <span data-ttu-id="74855-122">Дополнительные сведения см. в статье [sp_adddistpublisher (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-adddistpublisher-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="74855-122">For more information, see [sp_adddistpublisher &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-adddistpublisher-transact-sql).</span></span>  
  
### <a name="configure-the-publisher-at-the-original-publisher"></a><span data-ttu-id="74855-123">Настройка издателя на первоначальном издателе</span><span class="sxs-lookup"><span data-stu-id="74855-123">Configure the publisher at the original publisher</span></span>
  
1.  <span data-ttu-id="74855-124">Настройка удаленного распространения.</span><span class="sxs-lookup"><span data-stu-id="74855-124">Configure remote distribution.</span></span> <span data-ttu-id="74855-125">Если для настройки издателя используются хранимые процедуры, выполните хранимую процедуру `sp_adddistributor`.</span><span class="sxs-lookup"><span data-stu-id="74855-125">If stored procedures are being used to configure the publisher, run `sp_adddistributor`.</span></span> <span data-ttu-id="74855-126">Укажите то же значение *@password* , которое использовалось при `sp_adddistrbutor` выполнении на распространителе для настройки распространения.</span><span class="sxs-lookup"><span data-stu-id="74855-126">Specify the same value for *@password* as that used when `sp_adddistrbutor` was run at the distributor to set up distribution.</span></span>  
  
    ```sql
    exec sys.sp_adddistributor  
        @distributor = 'MyDistributor',  
        @password = 'MyDistPass'  
    ```  
  
2.  <span data-ttu-id="74855-127">Включите базу данных для репликации.</span><span class="sxs-lookup"><span data-stu-id="74855-127">Enable the database for replication.</span></span> <span data-ttu-id="74855-128">Если для настройки издателя используются хранимые процедуры, выполните хранимую процедуру `sp_replicationdboption`.</span><span class="sxs-lookup"><span data-stu-id="74855-128">If stored procedures are being used to configure the publisher, run `sp_replicationdboption`.</span></span> <span data-ttu-id="74855-129">Если для базы данных должны быть настроены и репликация транзакций, и репликация слиянием, необходимо включить каждую из них.</span><span class="sxs-lookup"><span data-stu-id="74855-129">If both transactional and merge replication are to be configured for the database, each must be enabled.</span></span>  
  
    ```sql
    USE master;  
    GO  
    EXEC sys.sp_replicationdboption  
        @dbname = 'MyDBName',  
        @optname = 'publish',  
        @value = 'true';  
  
    EXEC sys.sp_replicationdboption  
        @dbname = 'MyDBName',  
        @optname = 'merge publish',  
        @value = 'true';  
    ```  
  
3.  <span data-ttu-id="74855-130">Создайте публикацию, статьи и подписки репликации.</span><span class="sxs-lookup"><span data-stu-id="74855-130">Create the replication publication, articles, and subscriptions.</span></span> <span data-ttu-id="74855-131">Дополнительные сведения о том, как настроить репликацию, см. в разделе «Публикация данных и объектов базы данных».</span><span class="sxs-lookup"><span data-stu-id="74855-131">For more information about how to configure replication, see Publishing Data and Database objects.</span></span>  
  
##  <a name="2-configure-the-alwayson-availability-group"></a><a name="step2"></a><span data-ttu-id="74855-132">2. Настройка группы доступности AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="74855-132">2. Configure the AlwaysOn Availability Group</span></span>  
 <span data-ttu-id="74855-133">В будущей первичной реплике создайте группу доступности с опубликованной (или которой предстоит публикация) базой данных в качестве базы данных-участника.</span><span class="sxs-lookup"><span data-stu-id="74855-133">At the intended primary, create the availability group with the published (or to be published) database as a member database.</span></span> <span data-ttu-id="74855-134">При использовании мастера группы доступности можно либо разрешить мастеру выполнить первоначальную синхронизацию базы данных вторичной реплики, либо выполнить инициализацию вручную при помощи резервного копирования и восстановления.</span><span class="sxs-lookup"><span data-stu-id="74855-134">If using the Availability Group Wizard, you can either allow the wizard to initially synchronize the secondary replica databases or you can perform the initialization manually by using backup and restore.</span></span>  
  
 <span data-ttu-id="74855-135">Создайте прослушиватель DNS для группы доступности, которая будет использоваться агентами репликации для подключения к текущей первичной реплике.</span><span class="sxs-lookup"><span data-stu-id="74855-135">Create a DNS listener for the availability group that will be used by the replication agents to connect to the current primary.</span></span> <span data-ttu-id="74855-136">Указанное имя прослушивателя будет использоваться в качестве цели перенаправления для первоначального издателя и опубликованной базы данных.</span><span class="sxs-lookup"><span data-stu-id="74855-136">The listener name that is specified will be used as the target of redirection for the original publisher/published database pair.</span></span> <span data-ttu-id="74855-137">Например, если настройка группы доступности выполняется с помощью языка DDL, можно использовать следующий пример кода, чтобы указать прослушиватель для существующей группы доступности с именем `MyAG`:</span><span class="sxs-lookup"><span data-stu-id="74855-137">For example, if you are using DDL to configure the availability group, the following code example can be used to specify an availability group listener for an existing availability group named `MyAG`:</span></span>  
  
```sql
ALTER AVAILABILITY GROUP 'MyAG'   
    ADD LISTENER 'MyAGListenerName' (WITH IP (('10.120.19.155', '255.255.254.0')));  
```  
  
 <span data-ttu-id="74855-138">Дополнительные сведения см. в статье [Создание и настройка групп доступности (SQL Server)](creation-and-configuration-of-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="74855-138">For more information, see [Creation and Configuration of Availability Groups &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md).</span></span>  
  
##  <a name="3-insure-that-all-of-the-secondary-replica-hosts-are-configured-for-replication"></a><a name="step3"></a><span data-ttu-id="74855-139">3. Убедитесь, что все узлы вторичной реплики настроены для репликации.</span><span class="sxs-lookup"><span data-stu-id="74855-139">3. Insure that all of the Secondary Replica Hosts are Configured for Replication</span></span>  
 <span data-ttu-id="74855-140">На каждом узле вторичной реплики убедитесь, что служба [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] настроена для поддержки репликации.</span><span class="sxs-lookup"><span data-stu-id="74855-140">At each secondary replica host, verify that [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] has been configured to support replication.</span></span> <span data-ttu-id="74855-141">Следующий запрос можно запустить на каждом узле вторичной реплики, чтобы определить, установлена ли репликация:</span><span class="sxs-lookup"><span data-stu-id="74855-141">The following query can be run at each secondary replica host to determine whether replication is installed:</span></span>  
  
```sql
USE master;  
GO  
DECLARE @installed int;  
EXEC @installed = sys.sp_MS_replication_installed;  
SELECT @installed;  
```  
  
 <span data-ttu-id="74855-142">Если *@installed* значение равно 0, то репликация должна быть добавлена в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] установку.</span><span class="sxs-lookup"><span data-stu-id="74855-142">If *@installed* is 0, replication must be added to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] installation.</span></span>  
  
##  <a name="4-configure-the-secondary-replica-hosts-as-replication-publishers"></a><a name="step4"></a> <span data-ttu-id="74855-143">4. Настройка узлов вторичной реплики в качестве издателей репликации</span><span class="sxs-lookup"><span data-stu-id="74855-143">4. Configure the Secondary Replica Hosts as Replication Publishers</span></span>  
 <span data-ttu-id="74855-144">Вторичная реплика не может выступать в роли издателя репликации или переиздающего подписчика, однако репликацию необходимо настроить так, чтобы вторичная реплика могла взять на себя нагрузку после отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="74855-144">A secondary replica cannot act as a replication publisher or republisher but replication must be configured so that the secondary can take over after a failover.</span></span> <span data-ttu-id="74855-145">На распространителе настройте распространение для каждого узла вторичной реплики.</span><span class="sxs-lookup"><span data-stu-id="74855-145">At the distributor, configure distribution for each secondary replica host.</span></span> <span data-ttu-id="74855-146">Укажите ту же базу данных распространителя и рабочий каталог, что и при добавлении первоначального издателя к распространителю.</span><span class="sxs-lookup"><span data-stu-id="74855-146">Specify the same distribution database and working directory as was specified when the original publisher was added to the distributor.</span></span> <span data-ttu-id="74855-147">При использовании хранимых процедур для настройки распространения примените `sp_adddistpublisher` для связи удаленных издателей с распространителем.</span><span class="sxs-lookup"><span data-stu-id="74855-147">If you are using stored procedures to configure distribution, use `sp_adddistpublisher` to associate the remote publishers with the distributor.</span></span> <span data-ttu-id="74855-148">Если *@login* и использовались *@password* для первоначального издателя, укажите одинаковые значения для каждого при добавлении узлов вторичной реплики в качестве издателей.</span><span class="sxs-lookup"><span data-stu-id="74855-148">If *@login* and *@password* were used for the original publisher, specify the same values for each when you add the secondary replica hosts as publishers.</span></span>  
  
```sql
EXEC sys.sp_adddistpublisher  
    @publisher = 'AGSecondaryReplicaHost',  
    @distribution_db = 'distribution',  
    @working_directory = '\\MyReplShare\WorkingDir',  
    @login = 'MyPubLogin',  
    @password = '**Strong password for publisher**';  
```  
  
 <span data-ttu-id="74855-149">На каждом узле вторичной реплики настройте распространение.</span><span class="sxs-lookup"><span data-stu-id="74855-149">At each secondary replica host, configure distribution.</span></span> <span data-ttu-id="74855-150">Укажите распространителя оригинального издателя в качестве удаленного распространителя.</span><span class="sxs-lookup"><span data-stu-id="74855-150">Identify the distributor of the original publisher as the remote distributor.</span></span> <span data-ttu-id="74855-151">Используйте тот же пароль, который применялся при первоначальном запуске `sp_adddistributor` на распространителе.</span><span class="sxs-lookup"><span data-stu-id="74855-151">Use the same password as that used when `sp_adddistributor` was run originally at the distributor.</span></span> <span data-ttu-id="74855-152">Если для настройки распространения используются хранимые процедуры, параметр используется *@password* `sp_adddistributor` для указания пароля.</span><span class="sxs-lookup"><span data-stu-id="74855-152">If stored procedures are being used to configure distribution, the *@password* parameter of `sp_adddistributor` is used to specify the password.</span></span>  
  
```sql
EXEC sp_adddistributor   
    @distributor = 'MyDistributor',  
    @password = '**Strong password for distributor**';  
```  
  
 <span data-ttu-id="74855-153">На каждом узле вторичной реплики убедитесь, что подписчики по запросу на публикации базы данных отображаются как связанные серверы.</span><span class="sxs-lookup"><span data-stu-id="74855-153">At each secondary replica host, make sure that the push subscribers of the database publications appear as linked servers.</span></span> <span data-ttu-id="74855-154">Если для настройки удаленных издателей используются хранимые процедуры, используйте `sp_addlinkedserver` для добавления подписчиков (если они еще не установлены) в качестве связанных серверов для издателей.</span><span class="sxs-lookup"><span data-stu-id="74855-154">If stored procedures are being used to configure the remote publishers, use `sp_addlinkedserver` to add the subscribers (if not already present) as linked servers to the publishers.</span></span>  
  
```sql
EXEC sys.sp_addlinkedserver   
    @server = 'MySubscriber';  
```  
  
##  <a name="5-redirect-the-original-publisher-to-the-ag-listener-name"></a><a name="step5"></a> <span data-ttu-id="74855-155">5. Перенаправление первоначального издателя на имя прослушивателя группы доступности</span><span class="sxs-lookup"><span data-stu-id="74855-155">5. Redirect the Original Publisher to the AG Listener Name</span></span>  
 <span data-ttu-id="74855-156">На распространителе, в базе данных распространителя, запустите хранимую процедуру `sp_redirect_publisher`, чтобы связать первоначального издателя и опубликованную базу данных с именем прослушивателя группы доступности.</span><span class="sxs-lookup"><span data-stu-id="74855-156">At the distributor, in the distribution database, run the stored procedure `sp_redirect_publisher` to associate the original publisher and the published database with the availability group listener name of the availability group.</span></span>  
  
```sql
USE distribution;  
GO  
EXEC sys.sp_redirect_publisher   
@original_publisher = 'MyPublisher',  
    @publisher_db = 'MyPublishedDB',  
    @redirected_publisher = 'MyAGListenerName';  
```  
  
##  <a name="6-run-the-replication-validation-stored-procedure-to-verify-the-configuration"></a><a name="step6"></a> <span data-ttu-id="74855-157">6. Запуск хранимой процедуры проверки репликации для проверки конфигурации</span><span class="sxs-lookup"><span data-stu-id="74855-157">6. Run the Replication Validation Stored Procedure to Verify the Configuration</span></span>  
 <span data-ttu-id="74855-158">На распространителе в базе данных распространителя запустите хранимую процедуру `sp_validate_replica_hosts_as_publishers` для проверки настройки всех узлов реплики для работы в качестве издателей опубликованной базы данных.</span><span class="sxs-lookup"><span data-stu-id="74855-158">At the distributor, in the distribution database, run the stored procedure `sp_validate_replica_hosts_as_publishers` to verify that all replica hosts are now configured to serve as publishers for the published database.</span></span>  
  
```sql
USE distribution;  
GO  
DECLARE @redirected_publisher sysname;  
EXEC sys.sp_validate_replica_hosts_as_publishers  
    @original_publisher = 'MyPublisher',  
    @publisher_db = 'MyPublishedDB',  
    @redirected_publisher = @redirected_publisher output;  
```  
  
 <span data-ttu-id="74855-159">Хранимая процедура `sp_validate_replica_hosts_as_publishers` должна быть запущена от имени входа с достаточными правами авторизации на каждом узле реплики группы доступности для выполнения запроса сведений о группе доступности.</span><span class="sxs-lookup"><span data-stu-id="74855-159">The stored procedure `sp_validate_replica_hosts_as_publishers` should be run from a login with sufficient authorization at each availability group replica host to query for information about the availability group.</span></span> <span data-ttu-id="74855-160">В отличие от этого `sp_validate_redirected_publisher` , он использует учетные данные вызывающей стороны и не использует имя входа, сохраняемое в msdb. dbo. MSdistpublishers для подключения к репликам группы доступности.</span><span class="sxs-lookup"><span data-stu-id="74855-160">Unlike `sp_validate_redirected_publisher`, it uses the credentials of the caller and does not use the login retained in msdb.dbo.MSdistpublishers to connect to the availability group replicas.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="74855-161">Работа `sp_validate_replica_hosts_as_publishers` завершится сбоем со следующей ошибкой при проверке узлов вторичной реплики, которые не допускают доступ для чтения либо требуют указания намерения чтения.</span><span class="sxs-lookup"><span data-stu-id="74855-161">`sp_validate_replica_hosts_as_publishers` will fail with the following error when validating secondary replica hosts that do not allow read access, or require read intent to be specified.</span></span>  
>   
>  <span data-ttu-id="74855-162">Сообщение 21899, уровень 11, состояние 1, процедура `sp_hadr_verify_subscribers_at_publisher`, строка 109</span><span class="sxs-lookup"><span data-stu-id="74855-162">Msg 21899, Level 11, State 1, Procedure `sp_hadr_verify_subscribers_at_publisher`, Line 109</span></span>  
>   
>  <span data-ttu-id="74855-163">Запрос на перенаправленном издателе "MyReplicaHostName" для определения того, были ли там записи sysserver для подписчиков оригинального издателя "MyOriginalPublisher", завершился с ошибкой "976", сообщение об ошибке "Ошибка 976, уровень 14, состояние 1, сообщение: Целевая база данных "MyPublishedDB" участвует в группе доступности и в настоящее время недоступна для запросов.</span><span class="sxs-lookup"><span data-stu-id="74855-163">The query at the redirected publisher 'MyReplicaHostName' to determine whether there were sysserver entries for the subscribers of the original publisher 'MyOriginalPublisher' failed with error '976', error message 'Error 976, Level 14, State 1, Message: The target database, 'MyPublishedDB', is participating in an availability group and is currently not accessible for queries.</span></span> <span data-ttu-id="74855-164">Либо перемещение данных приостанавливается, либо реплика доступности не разрешена для чтения.</span><span class="sxs-lookup"><span data-stu-id="74855-164">Either data movement is suspended or the availability replica is not enabled for read access.</span></span> <span data-ttu-id="74855-165">Чтобы разрешить доступ только для чтения к этой и другим базам данных в группе доступности, задайте доступ для чтения одной или нескольким вторичным репликам доступности в группе.</span><span class="sxs-lookup"><span data-stu-id="74855-165">To allow read-only access to this and other databases in the availability group, enable read access to one or more secondary availability replicas in the group.</span></span>  <span data-ttu-id="74855-166">Дополнительные сведения см. в инструкции `ALTER AVAILABILITY GROUP` электронной документации по [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="74855-166">For more information, see the `ALTER AVAILABILITY GROUP` statement in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Books Online.'.</span></span>  
>   
>  <span data-ttu-id="74855-167">Произошла одна или несколько ошибок проверки издателя для узла реплики «MyReplicaHostName».</span><span class="sxs-lookup"><span data-stu-id="74855-167">One or more publisher validation errors were encountered for replica host 'MyReplicaHostName'.</span></span>  
  
 <span data-ttu-id="74855-168">Это ожидаемое поведение.</span><span class="sxs-lookup"><span data-stu-id="74855-168">This is expected behavior.</span></span> <span data-ttu-id="74855-169">Необходимо проверить наличие записей сервера подписчика на данных узлах вторичной реплики, выполнив запрос записей sysserver непосредственно на узле.</span><span class="sxs-lookup"><span data-stu-id="74855-169">You must verify the presence of the subscriber server entries at these secondary replica hosts by querying for the sysserver entries directly at the host.</span></span>  
  
##  <a name="7-add-the-original-publisher-to-replication-monitor"></a><a name="step7"></a> <span data-ttu-id="74855-170">7. Добавление первоначального издателя в монитор репликации</span><span class="sxs-lookup"><span data-stu-id="74855-170">7. Add the Original Publisher to Replication Monitor</span></span>  
 <span data-ttu-id="74855-171">В каждой реплике группы доступности добавьте оригинального издателя в монитор репликации.</span><span class="sxs-lookup"><span data-stu-id="74855-171">At each availability group replica, add the original publisher to Replication Monitor.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="74855-172">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="74855-172">Related Tasks</span></span>  
 <span data-ttu-id="74855-173">**Репликация**</span><span class="sxs-lookup"><span data-stu-id="74855-173">**Replication**</span></span>  
  
-   [<span data-ttu-id="74855-174">Обслуживание базы данных публикации AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="74855-174">Maintaining an AlwaysOn Publication Database &#40;SQL Server&#41;</span></span>](maintaining-an-always-on-publication-database-sql-server.md)  
  
-   [<span data-ttu-id="74855-175">Репликация, Отслеживание изменений, система отслеживания измененных данных и группы доступности AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="74855-175">Replication, Change Tracking, Change Data Capture, and AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](replicate-track-change-data-capture-always-on-availability.md)  
  
-   [<span data-ttu-id="74855-176">Вопросы и ответы об администрировании репликации</span><span class="sxs-lookup"><span data-stu-id="74855-176">Replication Administration FAQ</span></span>](../../../relational-databases/replication/administration/frequently-asked-questions-for-replication-administrators.md)  
  
 <span data-ttu-id="74855-177">**Создание и настройка группы доступности**</span><span class="sxs-lookup"><span data-stu-id="74855-177">**To create and configure an availability group**</span></span>  
  
-   [<span data-ttu-id="74855-178">Использование мастера групп доступности (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="74855-178">Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="74855-179">Использование диалогового окна "Создание группы доступности" (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="74855-179">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="74855-180">Создание группы доступности (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="74855-180">Create an Availability Group &#40;Transact-SQL&#41;</span></span>](create-an-availability-group-transact-sql.md)  
  
-   [<span data-ttu-id="74855-181">Создание группы доступности (SQL Server PowerShell)</span><span class="sxs-lookup"><span data-stu-id="74855-181">Create an Availability Group &#40;SQL Server PowerShell&#41;</span></span>](../../../powershell/sql-server-powershell.md)  
  
-   [<span data-ttu-id="74855-182">Укажите URL-адрес конечной точки при добавлении или изменении реплики доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="74855-182">Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;</span></span>](specify-endpoint-url-adding-or-modifying-availability-replica.md)  
  
-   [<span data-ttu-id="74855-183">Создание конечной точки зеркального отображения базы данных для группы доступности AlwaysOn &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="74855-183">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups &#40;SQL Server PowerShell&#41;</span></span>](database-mirroring-always-on-availability-groups-powershell.md)  
  
-   [<span data-ttu-id="74855-184">Присоединение вторичной реплики к группе доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="74855-184">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="74855-185">Подготовка базы данных-получателя для присоединения к группе доступности вручную (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="74855-185">Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;</span></span>](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="74855-186">Присоединение базы данных-получателя к группе доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="74855-186">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="74855-187">Создание или настройка прослушивателя группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="74855-187">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="74855-188">См. также:</span><span class="sxs-lookup"><span data-stu-id="74855-188">See Also</span></span>  
 <span data-ttu-id="74855-189">[Предварительные требования, ограничения и рекомендации для группы доступности AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="74855-189">[Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span></span>  
 <span data-ttu-id="74855-190">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="74855-190">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="74855-191">[Группы доступности AlwaysOn: взаимодействие (SQL Server)](always-on-availability-groups-interoperability-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="74855-191">[AlwaysOn Availability Groups: Interoperability (SQL Server)](always-on-availability-groups-interoperability-sql-server.md) </span></span>  
 [<span data-ttu-id="74855-192">Репликация SQL Server</span><span class="sxs-lookup"><span data-stu-id="74855-192">SQL Server Replication</span></span>](../../../relational-databases/replication/sql-server-replication.md)  
