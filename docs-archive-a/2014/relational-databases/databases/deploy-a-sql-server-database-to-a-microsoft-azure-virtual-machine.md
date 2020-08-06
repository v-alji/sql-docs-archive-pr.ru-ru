---
title: Развертывание базы данных SQL Server на виртуальной машине Microsoft Azure | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.swb.deploymentwizard.deploymentsettings.f1
- sql12.swb.deploymentwizard.progress.f1
- sql11.swb.usevmdialog.f1
- sql11.swb.deploymentwizard.f1
- sql12.swb.deploymentwizard.azuresignin.f1
- sql11.swb.deploymentwizard.summary.f1
- sql11.swb.deploymentwizard.azuresignin.f1
- sql12.swb.deploymentwizard.f1
- sql12.swb.sqlvmdialog.f1
- sql11.swb.newvmdialog.f1
- sql12.swb.deploymentwizard.results.f1
- sql11.swb.deploymentwizard.progress.f1
- sql12.swb.newvmdialog.f1
- sql12.swb.deploymentwizard.sourcesettings.f1
- sql12.swb.usevmdialog.f1
- sql11.swb.deploymentwizard.sourcesettings.f1
- sql11.swb.deploymentwizard.results.f1
- sql12.swb.deploymentwizard.summary.f1
- sql11.swb.deploymentwizard.deploymentsettings.f1
helpviewer_keywords:
- Deploy a database
- Deploy to Azure VM
- Migrate to Azure
- Azure virtual machine
- Migrate to Azure VM
- Migrate to the cloud
- SQL Server Management Studio
- SSMS
- Deploy database wizard
- Deploy a SQL Server database to Azure
- Azure VM
ms.assetid: 5e82e66a-262e-4d4f-aa89-39cb62696d06
author: stevestein
ms.author: sstein
ms.openlocfilehash: d48c06db038a775811cba6705fbaf1d97a960f6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736386"
---
# <a name="deploy-a-sql-server-database-to-a-microsoft-azure-virtual-machine"></a><span data-ttu-id="adc44-102">Развертывание базы данных SQL Server в виртуальной машине Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="adc44-102">Deploy a SQL Server Database to a Microsoft Azure Virtual Machine</span></span>
  <span data-ttu-id="adc44-103">Используйте мастер **развертывания SQL Server базы данных в виртуальной машине Azure** , чтобы развернуть базу данных из экземпляра в [!INCLUDE[ssDE](../../includes/ssde-md.md)] на [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] виртуальной машине Azure.</span><span class="sxs-lookup"><span data-stu-id="adc44-103">Use the **Deploy a SQL Server Database to an Azure VM** wizard to deploy a database from an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in an Azure Virtual Machine (VM).</span></span> <span data-ttu-id="adc44-104">Мастер использует операцию полного резервного копирования базы данных, поэтому он всегда копирует всю схему базы данных и данные из пользовательской базы данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="adc44-104">The wizard utilizes a full database backup operation, so it always copies the complete database schema and the data from a SQL Server user database.</span></span> <span data-ttu-id="adc44-105">Мастер также выполняет всю настройку ВМ Azure, поэтому дополнительные действия для задания параметров ВМ не требуются.</span><span class="sxs-lookup"><span data-stu-id="adc44-105">The wizard also does all of the Azure VM configuration for you, so no pre-configuration of the VM is required.</span></span>  
  
 <span data-ttu-id="adc44-106">Нельзя использовать мастер для создания разностных резервных копий, поскольку он не перезаписывает существующую базу данных, имя которой совпадает с именем обрабатываемой базы данных.</span><span class="sxs-lookup"><span data-stu-id="adc44-106">You cannot use the wizard for differential backups because the wizard will not overwrite an existing database that has the same database name.</span></span> <span data-ttu-id="adc44-107">Чтобы заменить существующую базу данных на ВМ, сначала необходимо удалить существующую базу данных или изменить имя базы данных.</span><span class="sxs-lookup"><span data-stu-id="adc44-107">To replace an existing database on the VM, you must first drop the existing database or change the database name.</span></span> <span data-ttu-id="adc44-108">В случае возникновения конфликта имен между базой данных, в отношении которой выполняется операция развертывания на лету, и существующей базой данных на виртуальной машине мастер предложит имя базы данных с добавлением определенных символов для развертываемой на лету базы данных, чтобы можно было завершить операцию.</span><span class="sxs-lookup"><span data-stu-id="adc44-108">If there is a naming conflict between the database name for an in-flight deploy operation and an existing database on the VM, the wizard will suggest an appended database name for the in-flight database to enable you to complete the operation.</span></span>  
  
##  <a name="before-you-begin"></a><a name="before_you_begin"></a> <span data-ttu-id="adc44-109">Перед началом</span><span class="sxs-lookup"><span data-stu-id="adc44-109">Before You Begin</span></span>  
 <span data-ttu-id="adc44-110">Чтобы завершить этот мастер, необходима возможность предоставить следующие сведения и назначить следующие параметры конфигурации:</span><span class="sxs-lookup"><span data-stu-id="adc44-110">To complete this wizard, you must be able to provide the following information and have these configuration settings in place:</span></span>  
  
-   <span data-ttu-id="adc44-111">Сведения о учетная запись Майкрософт, связанные с подпиской Azure.</span><span class="sxs-lookup"><span data-stu-id="adc44-111">The Microsoft account details associated with your Azure subscription.</span></span>  
  
-   <span data-ttu-id="adc44-112">Ваш профиль публикации Azure.</span><span class="sxs-lookup"><span data-stu-id="adc44-112">Your Azure publishing profile.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="adc44-113">SQL Server в настоящий момент поддерживает версию 2.0 профиля публикации.</span><span class="sxs-lookup"><span data-stu-id="adc44-113">SQL Server currently supports publishing profile version 2.0.</span></span> <span data-ttu-id="adc44-114">Для загрузки поддерживаемой версии профиля публикации см. раздел [Загрузка профиля публикации 2.0](https://go.microsoft.com/fwlink/?LinkId=396421).</span><span class="sxs-lookup"><span data-stu-id="adc44-114">To download the supported version of the publishing profile, see [Download Publishing Profile 2.0](https://go.microsoft.com/fwlink/?LinkId=396421).</span></span>  
  
-   <span data-ttu-id="adc44-115">Сертификат управления, отправленный в подписку Azure.</span><span class="sxs-lookup"><span data-stu-id="adc44-115">The management certificate uploaded to your Azure subscription.</span></span>  
  
-   <span data-ttu-id="adc44-116">Сертификат управления, сохраненный в хранилище личных сертификатов на компьютере, где запущен мастер.</span><span class="sxs-lookup"><span data-stu-id="adc44-116">The management certificate saved into the personal certificate store on the computer where the wizard is running.</span></span>  
  
-   <span data-ttu-id="adc44-117">Необходимо временное место хранения, доступное для компьютера, на котором размещается база данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="adc44-117">You must have a temporary storage location that is available to the computer where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database is hosted.</span></span> <span data-ttu-id="adc44-118">Временное место хранения также должно быть доступным для компьютера, на котором запущен мастер.</span><span class="sxs-lookup"><span data-stu-id="adc44-118">The temporary storage location must also be available to the computer where the wizard is running.</span></span>  
  
-   <span data-ttu-id="adc44-119">При развертывании базы данных на существующей виртуальной машине в экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] должно быть настроено прослушивание порта TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="adc44-119">If you are deploying the database to an existing VM, the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be configured to listen on a TCP/IP port.</span></span>  
  
-   <span data-ttu-id="adc44-120">Для виртуальной машины Azure или образа коллекции, который планируется использовать для создания виртуальной машины, необходимо настроить и запустить адаптер для облака SQL Server.</span><span class="sxs-lookup"><span data-stu-id="adc44-120">Either an Azure VM or Gallery image you plan to use for creation of the VM must have the SQL Server Cloud Adapter configured and running.</span></span>  
  
-   <span data-ttu-id="adc44-121">Необходимо настроить открытую конечную точку для SQL Server адаптер для облака в шлюзе Azure с частным портом 11435.</span><span class="sxs-lookup"><span data-stu-id="adc44-121">You must configure an open endpoint for your SQL Server Cloud Adapter on the Azure gateway with private port 11435.</span></span>  
  
 <span data-ttu-id="adc44-122">Кроме того, если вы планируете развернуть базу данных на существующей виртуальной машине Azure, необходимо также предоставить следующие возможности.</span><span class="sxs-lookup"><span data-stu-id="adc44-122">In addition, if you plan to deploy your database into an existing Azure VM, you must also be able to provide:</span></span>  
  
-   <span data-ttu-id="adc44-123">Имя DNS облачной службы, в которой размещается виртуальная машина.</span><span class="sxs-lookup"><span data-stu-id="adc44-123">The DNS name of the cloud service that hosts your VM.</span></span>  
  
-   <span data-ttu-id="adc44-124">Учетные данные администратора для виртуальной машины.</span><span class="sxs-lookup"><span data-stu-id="adc44-124">Administrator credentials for the VM.</span></span>  
  
-   <span data-ttu-id="adc44-125">Учетные данные с правами доступа для выполнения оператора резервного копирования базы данных, которую планируется развернуть из исходного экземпляра служб [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="adc44-125">Credentials with Backup operator privileges on the database you plan to deploy, from the source instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="adc44-126">Дополнительные сведения о запуске SQL Server на виртуальных машинах Azure см. в статье [Подготовка к переходу на SQL Server на виртуальных машинах Azure](https://msdn.microsoft.com/library/dn133142.aspx).</span><span class="sxs-lookup"><span data-stu-id="adc44-126">For more information about running SQL Server in Azure virtual machines, see [Getting Ready to Migrate to SQL Server in Azure Virtual Machines](https://msdn.microsoft.com/library/dn133142.aspx).</span></span>  
  
 <span data-ttu-id="adc44-127">На компьютерах, работающих под управлением операционных систем Windows Server, для запуска мастера необходимо использовать следующие параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="adc44-127">On computers running Windows Server operating systems, you must use the following configuration settings to run this wizard:</span></span>  
  
-   <span data-ttu-id="adc44-128">Отключите конфигурацию усиленной безопасности: выберите "Диспетчер серверов" > "Локальный сервер" и задайте для параметра "Конфигурация усиленной безопасности Internet Explorer" значение **ВЫКЛ**.</span><span class="sxs-lookup"><span data-stu-id="adc44-128">Turn off Enhanced Security Configuration:  Use Server Manager > Local Server to set Internet Explorer Enhanced Security Configuration (ESC) to **OFF**.</span></span>  
  
-   <span data-ttu-id="adc44-129">Включите JavaScript: Internet Explorer > Свойства обозревателя > Безопасность > Уровень пользователя > Скрипты > Активные скрипты: **Включить**.</span><span class="sxs-lookup"><span data-stu-id="adc44-129">Enable JavaScript:  Internet Explorer > Internet Options > Security > Customer Level > Scripting > Active Scripting: **Enable**.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="limitations"></a> <span data-ttu-id="adc44-130">Ограничения</span><span class="sxs-lookup"><span data-stu-id="adc44-130">Limitations and Restrictions</span></span>  
 <span data-ttu-id="adc44-131">Размер базы данных для этой операции не может превышать 1 ТБ.</span><span class="sxs-lookup"><span data-stu-id="adc44-131">The database size limitation for this operation is 1 TB.</span></span>  
  
 <span data-ttu-id="adc44-132">Эта функция развертывания доступна в среде SQL Server Management Studio для [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="adc44-132">This deployment feature is available in SQL Server Management Studio for [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)].</span></span>  
  
 <span data-ttu-id="adc44-133">Эта функция развертывания предназначена для использования только в отношении пользовательских баз данных. Развертывание системных баз данных не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="adc44-133">This deployment feature is for use only with user databases; deploying system databases is not supported.</span></span>  
  
 <span data-ttu-id="adc44-134">Функция развертывания не поддерживает размещаемые службы, связанные с группой сходства.</span><span class="sxs-lookup"><span data-stu-id="adc44-134">The deployment feature does not support hosted services that are associated with an Affinity Group.</span></span> <span data-ttu-id="adc44-135">Например, учетные записи хранения, связанные с группой сходства, нельзя выбрать для использования на странице мастера **Параметры развертывания** .</span><span class="sxs-lookup"><span data-stu-id="adc44-135">For example, storage accounts associated with an Affinity Group cannot be selected for use on the **Deployment Settings** page of this wizard.</span></span>  
  
 <span data-ttu-id="adc44-136">Версия SQL Server в виртуальной машине должна быть такой же, что и исходная версия SQL Server, или более поздней.</span><span class="sxs-lookup"><span data-stu-id="adc44-136">The SQL Server version in the VM must be the same or later than the source SQL Server version.</span></span> <span data-ttu-id="adc44-137">SQL Server версии базы данных, которые можно развернуть на виртуальной машине Azure с помощью этого мастера:</span><span class="sxs-lookup"><span data-stu-id="adc44-137">SQL Server database versions that can be deployed to an Azure VM using this wizard:</span></span>  
  
-   <span data-ttu-id="adc44-138">SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="adc44-138">SQL Server 2008</span></span>  
  
-   <span data-ttu-id="adc44-139">SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="adc44-139">SQL Server 2008 R2</span></span>  
  
-   <span data-ttu-id="adc44-140">SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="adc44-140">SQL Server 2012</span></span>  
  
-   [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]  
  
 <span data-ttu-id="adc44-141">SQL Server версии базы данных, выполняющиеся в базе данных виртуальной машины Azure, можно развернуть в:</span><span class="sxs-lookup"><span data-stu-id="adc44-141">SQL Server database versions running in an Azure VM database can be deployed to:</span></span>  
  
-   <span data-ttu-id="adc44-142">SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="adc44-142">SQL Server 2012</span></span>  
  
-   [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]  
  
 <span data-ttu-id="adc44-143">В случае возникновения конфликта имен между базой данных, в отношении которой выполняется операция развертывания на лету, и существующей базой данных на виртуальной машине мастер предложит имя базы данных с добавлением определенных символов для развертываемой на лету базы данных, чтобы можно было завершить операцию.</span><span class="sxs-lookup"><span data-stu-id="adc44-143">If there is a naming conflict between the database name for an in-flight deploy operation and an existing database on the VM, the wizard will suggest an appended database name for the in-flight database to enable you to complete the operation.</span></span>  
  
###  <a name="considerations-for-deploying-a-filestream-enabled-database-to-an-azure-vm"></a><a name="filestream"></a> <span data-ttu-id="adc44-144">Основные моменты при развертывании базы данных с поддержкой FILESTREAM на виртуальную машину SQL Azure</span><span class="sxs-lookup"><span data-stu-id="adc44-144">Considerations for Deploying a FILESTREAM-enabled Database to an Azure VM</span></span>  
 <span data-ttu-id="adc44-145">Обратите внимание на следующие правила и ограничения при развертывании баз данных с большими двоичными объектами, хранящихся в объектах FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="adc44-145">Note the following guidelines and restrictions when deploying databases that have BLOBS stored in FILESTREAM objects:</span></span>  
  
-   <span data-ttu-id="adc44-146">Функция развертывания не может развернуть базу данных с поддержкой FILESTREAM на новой виртуальной машине.</span><span class="sxs-lookup"><span data-stu-id="adc44-146">The deployment feature cannot deploy a FILESTREAM-enabled database into a new VM.</span></span> <span data-ttu-id="adc44-147">Если функция FILESTREAM отключена в виртуальной машине до запуска мастера, то операция восстановления базы данных завершится ошибкой, а операция мастера не будет завершена успешно.</span><span class="sxs-lookup"><span data-stu-id="adc44-147">If FILESTREAM is not enabled in the VM before you run the wizard, the database restore operation will fail and the wizard operation will not be able to complete successfully.</span></span> <span data-ttu-id="adc44-148">Для успешного развертывания базы данных, в которой используется FILESTREAM, перед запуском мастера включите FILESTREAM в экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на виртуальной машине основного приложения.</span><span class="sxs-lookup"><span data-stu-id="adc44-148">To successfully deploy a database that uses FILESTREAM, enable FILESTREAM in the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on the host VM before launching the wizard.</span></span> <span data-ttu-id="adc44-149">Дополнительные сведения см. в разделе [FILESTREAM (SQL Server)](https://msdn.microsoft.com/library/gg471497.aspx).</span><span class="sxs-lookup"><span data-stu-id="adc44-149">For more information, see [FILESTREAM (SQL Server)](https://msdn.microsoft.com/library/gg471497.aspx).</span></span>  
  
-   <span data-ttu-id="adc44-150">Если база данных использует функции OLTP в памяти, то можно развернуть базу данных в виртуальной машине Azure без каких-либо изменений в базе данных.</span><span class="sxs-lookup"><span data-stu-id="adc44-150">If your database utilizes In-Memory OLTP, you can deploy the database to an Azure VM without any modifications to the database.</span></span> <span data-ttu-id="adc44-151">Дополнительные сведения см. в разделе [In-Memory OLTP (оптимизация в памяти)](https://msdn.microsoft.com/library/dn133186\(SQL.120\).aspx).</span><span class="sxs-lookup"><span data-stu-id="adc44-151">For more information, see [In-Memory OLTP (In-Memory Optimization)](https://msdn.microsoft.com/library/dn133186\(SQL.120\).aspx).</span></span>  
  
###  <a name="considerations-for-geographic-distribution-of-assets"></a><a name="geography"></a><span data-ttu-id="adc44-152">Рекомендации по географическому распределению ресурсов</span><span class="sxs-lookup"><span data-stu-id="adc44-152">Considerations for Geographic Distribution of Assets</span></span>  
 <span data-ttu-id="adc44-153">Обратите внимание, что следующие активы должны находиться в одной и той же географической области.</span><span class="sxs-lookup"><span data-stu-id="adc44-153">Note that the following assets must be located in the same geographic region:</span></span>  
  
-   <span data-ttu-id="adc44-154">Облачная служба</span><span class="sxs-lookup"><span data-stu-id="adc44-154">Cloud Service</span></span>  
  
-   <span data-ttu-id="adc44-155">Расположение виртуальной машины</span><span class="sxs-lookup"><span data-stu-id="adc44-155">VM Location</span></span>  
  
-   <span data-ttu-id="adc44-156">Служба хранения диска данных</span><span class="sxs-lookup"><span data-stu-id="adc44-156">Data Disk Storage Service</span></span>  
  
 <span data-ttu-id="adc44-157">Если приведенные выше активы не находятся в одном месте, мастер не сможет завершиться успешно.</span><span class="sxs-lookup"><span data-stu-id="adc44-157">If the assets listed above are not co-located, the wizard will not be able to complete successfully.</span></span>  
  
###  <a name="wizard-configuration-settings"></a><a name="configuration_settings"></a><span data-ttu-id="adc44-158">Параметры конфигурации мастера</span><span class="sxs-lookup"><span data-stu-id="adc44-158">Wizard Configuration Settings</span></span>  
 <span data-ttu-id="adc44-159">Используйте следующие параметры конфигурации для изменения настроек для развертывания базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на виртуальной машине Azure.</span><span class="sxs-lookup"><span data-stu-id="adc44-159">Use the following configuration details to modify settings for a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database deployment to an Azure VM.</span></span>  
  
-   <span data-ttu-id="adc44-160">**Путь по умолчанию к файлу конфигурации** : "%LOCALAPPDATA%\SQL Server\Deploy to SQL in WA VM\DeploymentSettings.xml".</span><span class="sxs-lookup"><span data-stu-id="adc44-160">**Default path for the configuration file** - %LOCALAPPDATA%\SQL Server\Deploy to SQL in WA VM\DeploymentSettings.xml</span></span>  
  
-   <span data-ttu-id="adc44-161">**Структура файла конфигурации**</span><span class="sxs-lookup"><span data-stu-id="adc44-161">**Configuration file structure**</span></span>  
  
    -   \<DeploymentSettings>  
  
        -   <span data-ttu-id="adc44-162"><OtherSettings</span><span class="sxs-lookup"><span data-stu-id="adc44-162"><OtherSettings</span></span>  
  
            -   <span data-ttu-id="adc44-163">TraceLevel = "Debug"\<!-- Logging level --></span><span class="sxs-lookup"><span data-stu-id="adc44-163">TraceLevel="Debug" \<!-- Logging level --></span></span>  
  
            -   <span data-ttu-id="adc44-164">BackupPath = " \\ \\ [имя сервера] \\ [том] \\ "\<!-- The last used path for backup. Used as default in the wizard. --></span><span class="sxs-lookup"><span data-stu-id="adc44-164">BackupPath="\\\\[server name]\\[volume]\\" \<!-- The last used path for backup. Used as default in the wizard. --></span></span>  
  
            -   <span data-ttu-id="adc44-165">CleanupDisabled = false/>\<!-- Wizard will not delete intermediate files and Azure objects (VM, CS, SA). --></span><span class="sxs-lookup"><span data-stu-id="adc44-165">CleanupDisabled = False /> \<!-- Wizard will not delete intermediate files and Azure objects (VM, CS, SA). --></span></span>  
  
        -   <span data-ttu-id="adc44-166"><PublishProfile\<!-- The last used publish profile information. --></span><span class="sxs-lookup"><span data-stu-id="adc44-166"><PublishProfile \<!-- The last used publish profile information. --></span></span>  
  
            -   <span data-ttu-id="adc44-167">Certificate = "12A34B567890123ABCD4EF567A8"\<!-- The certificate for use in the wizard. --></span><span class="sxs-lookup"><span data-stu-id="adc44-167">Certificate="12A34B567890123ABCD4EF567A8" \<!-- The certificate for use in the wizard. --></span></span>  
  
            -   <span data-ttu-id="adc44-168">Subscription = "1a2b34c5-67d8-90ef-AB12-xxxxxxxxxxxxx"\<!-- The subscription for use in the wizard. --></span><span class="sxs-lookup"><span data-stu-id="adc44-168">Subscription="1a2b34c5-67d8-90ef-ab12-xxxxxxxxxxxxx" \<!-- The subscription for use in the wizard. --></span></span>  
  
            -   <span data-ttu-id="adc44-169">Name = "Моя подписка"\<!-- The name of the subscription. --></span><span class="sxs-lookup"><span data-stu-id="adc44-169">Name="My Subscription" \<!-- The name of the subscription. --></span></span>  
  
            -   <span data-ttu-id="adc44-170">Publisher="" /></span><span class="sxs-lookup"><span data-stu-id="adc44-170">Publisher="" /></span></span>  
  
    -   \</DeploymentSettings>  
  
 <span data-ttu-id="adc44-171">**Значения файла конфигурации**</span><span class="sxs-lookup"><span data-stu-id="adc44-171">**Configuration file values**</span></span>  
  
###  <a name="permissions"></a><a name="permissions"></a> <span data-ttu-id="adc44-172">Permissions</span><span class="sxs-lookup"><span data-stu-id="adc44-172">Permissions</span></span>  
 <span data-ttu-id="adc44-173">Развертываемая база данных должна находиться в нормальном состоянии, база данных должна быть доступна для учетной записи пользователя, запустившего мастер, и учетная запись должна иметь разрешения для выполнения операции резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="adc44-173">The database being deployed must be in a normal state, the database must be accessible to the user account running the wizard, and the user account must have permissions to perform a backup operation.</span></span>  
  
##  <a name="using-the-deploy-database-to-azure-vm-wizard"></a><a name="launch_wizard"></a><span data-ttu-id="adc44-174">Использование мастера развертывания базы данных в виртуальной машине Azure</span><span class="sxs-lookup"><span data-stu-id="adc44-174">Using the Deploy Database to Azure VM Wizard</span></span>  
 <span data-ttu-id="adc44-175">**Для запуска мастера выполните следующие действия.**</span><span class="sxs-lookup"><span data-stu-id="adc44-175">**To launch the wizard, use the following steps:**</span></span>  
  
1.  <span data-ttu-id="adc44-176">Использование среды SQL Server Management Studio для подключения к экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с базой данных, развертывание которой требуется выполнить.</span><span class="sxs-lookup"><span data-stu-id="adc44-176">Use SQL Server Management Studio to connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with the database you want to deploy.</span></span>  
  
2.  <span data-ttu-id="adc44-177">В **обозревателе объектов**разверните имя экземпляра, затем узел **Databases** .</span><span class="sxs-lookup"><span data-stu-id="adc44-177">In **Object Explorer**, expand the instance name, then expand the **Databases** node.</span></span>  
  
3.  <span data-ttu-id="adc44-178">Щелкните правой кнопкой мыши базу данных, которую необходимо развернуть, выберите **задачи**, а затем — **развернуть базу данных на виртуальной машине Azure...**</span><span class="sxs-lookup"><span data-stu-id="adc44-178">Right-click the database you want to deploy, select **Tasks**, and then select **Deploy Database to Azure VM...**</span></span>  
  

  
##  <a name="introduction-page"></a><a name="Introduction"></a> <span data-ttu-id="adc44-179">Вводная страница</span><span class="sxs-lookup"><span data-stu-id="adc44-179">Introduction Page</span></span>  
 <span data-ttu-id="adc44-180">На этой странице описывается мастер **развертывания SQL Server базы данных в виртуальной машине Azure** .</span><span class="sxs-lookup"><span data-stu-id="adc44-180">This page describes the **Deploy a SQL Server Database to an Azure VM** wizard.</span></span>  
  
 <span data-ttu-id="adc44-181">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="adc44-181">**Options**</span></span>  
  
-   <span data-ttu-id="adc44-182">**Больше не показывать эту страницу.**</span><span class="sxs-lookup"><span data-stu-id="adc44-182">**Do not show this page again.**</span></span> <span data-ttu-id="adc44-183">Установите этот флажок, чтобы вводная страница больше не отображалась.</span><span class="sxs-lookup"><span data-stu-id="adc44-183">- Click this check box to stop the Introduction page from being displayed in the future.</span></span>  
  
-   <span data-ttu-id="adc44-184">**Следующая** — переход к странице **Параметры источника** .</span><span class="sxs-lookup"><span data-stu-id="adc44-184">**Next** - Proceeds to the **Source Settings** page.</span></span>  
  
-   <span data-ttu-id="adc44-185">**Отмена** — отмена операции и закрытие мастера.</span><span class="sxs-lookup"><span data-stu-id="adc44-185">**Cancel** - Cancels the operation and closes the wizard.</span></span>  
  
-   <span data-ttu-id="adc44-186">**Справка** — запуск раздела справки MSDN для мастера.</span><span class="sxs-lookup"><span data-stu-id="adc44-186">**Help** - Launches the MSDN Help topic for the wizard.</span></span>  
  
##  <a name="source-settings"></a><a name="Source_settings"></a><span data-ttu-id="adc44-187">Параметры источника</span><span class="sxs-lookup"><span data-stu-id="adc44-187">Source Settings</span></span>  
 <span data-ttu-id="adc44-188">Эта страница используется для подключения к экземпляру, на котором [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] размещена база данных, которую требуется развернуть на виртуальной машине Azure.</span><span class="sxs-lookup"><span data-stu-id="adc44-188">Use this page to connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that hosts the database you want to deploy to the Azure VM.</span></span> <span data-ttu-id="adc44-189">Кроме того, необходимо указать временное расположение файлов, сохраняемых на локальном компьютере, прежде чем они будут переданы в Azure.</span><span class="sxs-lookup"><span data-stu-id="adc44-189">You will also specify a temporary location for files to be saved from the local machine before they are transferred to Azure.</span></span> <span data-ttu-id="adc44-190">Это может быть общая сетевая папка.</span><span class="sxs-lookup"><span data-stu-id="adc44-190">This can be a shared, network location.</span></span>  
  
 <span data-ttu-id="adc44-191">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="adc44-191">**Options**</span></span>  
  
-   <span data-ttu-id="adc44-192">Нажмите кнопку **Подключить...** , а затем укажите сведения о подключении для экземпляра, на котором [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] размещена база данных для развертывания.</span><span class="sxs-lookup"><span data-stu-id="adc44-192">Click **Connect...** and then specify connection details for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that hosts the database to deploy.</span></span>  
  
-   <span data-ttu-id="adc44-193">Используйте раскрывающийся список **Выбор базы данных** , чтобы указать базу данных для развертывания.</span><span class="sxs-lookup"><span data-stu-id="adc44-193">Use the **Select Database** drop-down list to specify the database to deploy.</span></span>  
  
-   <span data-ttu-id="adc44-194">В поле **другие параметры** укажите общую папку, которая будет доступна службе виртуальной машины Azure.</span><span class="sxs-lookup"><span data-stu-id="adc44-194">In the **Other Settings** field, specify a shared folder that will be accessible to the Azure VM service.</span></span>  
  
##  <a name="azure-sign-in"></a><a name="Azure_sign-in"></a><span data-ttu-id="adc44-195">Вход в Azure</span><span class="sxs-lookup"><span data-stu-id="adc44-195">Azure Sign-in</span></span>  
 <span data-ttu-id="adc44-196">Эта страница используется для подключения к Azure и предоставления сертификата управления или сведений о профиле публикации.</span><span class="sxs-lookup"><span data-stu-id="adc44-196">Use this page to connect to Azure and provide management certificate or publishing profile details.</span></span>  
  
 <span data-ttu-id="adc44-197">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="adc44-197">**Options**</span></span>  
  
-   <span data-ttu-id="adc44-198">**Сертификат управления** — используйте этот параметр, чтобы указать сертификат из локального хранилища сертификатов, который соответствует сертификату управления в Azure.</span><span class="sxs-lookup"><span data-stu-id="adc44-198">**Management Certificate** - Use this option to specify a certificate from the local certificate store that matches the management certificate from Azure.</span></span>  
  
-   <span data-ttu-id="adc44-199">**Профиль публикации** . Используйте этот параметр, если профиль публикации уже загружен на компьютер.</span><span class="sxs-lookup"><span data-stu-id="adc44-199">**Publishing Profile** - Use this option if you already have a publishing profile downloaded to your computer.</span></span>  
  
-   <span data-ttu-id="adc44-200">**Вход** . Используйте этот параметр, чтобы войти в Azure с помощью учетная запись Майкрософт (например, Live ID или учетной записи Hotmail), чтобы создать и скачать новый сертификат управления.</span><span class="sxs-lookup"><span data-stu-id="adc44-200">**Sign In** - Use this option to sign in to Azure using a Microsoft account - for example, a Live ID or Hotmail account - to generate and download a new management certificate.</span></span> <span data-ttu-id="adc44-201">Обратите внимание, что количество сертификатов на одну подписку ограниченно.</span><span class="sxs-lookup"><span data-stu-id="adc44-201">Note that the number of certificates per subscription is limited.</span></span>  
  
-   <span data-ttu-id="adc44-202">**Подписка** — выберите, введите или вставьте идентификатор подписки Azure, соответствующий сертификату управления из локального хранилища сертификатов или профиля публикации.</span><span class="sxs-lookup"><span data-stu-id="adc44-202">**Subscription** - Select, type, or paste your Azure subscription ID that matches the management certificate from the local certificate store or a publishing profile.</span></span>  
  
##  <a name="deployment-settings-page"></a><a name="Deployment_settings"></a><span data-ttu-id="adc44-203">Страница "Параметры развертывания"</span><span class="sxs-lookup"><span data-stu-id="adc44-203">Deployment Settings Page</span></span>  
 <span data-ttu-id="adc44-204">На этой странице указываются целевой сервер и подробные сведения о новой базе данных.</span><span class="sxs-lookup"><span data-stu-id="adc44-204">Use this page to specify the destination server and to provide details about your new database.</span></span>  
  
 <span data-ttu-id="adc44-205">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="adc44-205">**Options**</span></span>  
  
-   <span data-ttu-id="adc44-206">**Виртуальная машина Azure** . Укажите сведения для виртуальной машины, на которой будет размещена база данных SQL Server:</span><span class="sxs-lookup"><span data-stu-id="adc44-206">**Azure Virtual Machine** - Specify details for the VM that will host the SQL Server database:</span></span>  
  
-   <span data-ttu-id="adc44-207">**Имя облачной службы** . Укажите имя службы, в которой РАЗМЕЩЕНа виртуальная машина.</span><span class="sxs-lookup"><span data-stu-id="adc44-207">**Cloud Service name** - Specify the name of the service that hosts the VM.</span></span> <span data-ttu-id="adc44-208">Чтобы создать новую облачную службу укажите для нее имя.</span><span class="sxs-lookup"><span data-stu-id="adc44-208">To create a new Cloud Service, specify a name for the new Cloud Service.</span></span>  
  
-   <span data-ttu-id="adc44-209">**Имя виртуальной машины** — укажите имя виртуальной машины, на которой будет размещена база данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="adc44-209">**Virtual Machine name** - Specify the name of the VM that will host the SQL Server database.</span></span> <span data-ttu-id="adc44-210">Чтобы создать виртуальную машину Azure, укажите имя для новой виртуальной машины.</span><span class="sxs-lookup"><span data-stu-id="adc44-210">To create a new Azure VM, specify a name for the new VM.</span></span>  
  
-   <span data-ttu-id="adc44-211">**Параметры** . с помощью кнопки "Параметры" Создайте виртуальную машину для размещения базы данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="adc44-211">**Settings** - Use the Settings button to create a new VM to host the SQL Server database.</span></span> <span data-ttu-id="adc44-212">Если используется существующая виртуальная машина, предоставленные сведения будут использоваться для проверки подлинности учетных данных.</span><span class="sxs-lookup"><span data-stu-id="adc44-212">If you are using an existing VM, the information you provide will be used to authenticate your credentials.</span></span>  
  
-   <span data-ttu-id="adc44-213">**Учетная запись хранения** . Выберите учетную запись хранения из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="adc44-213">**Storage account** - Select the storage account from the drop-down list.</span></span> <span data-ttu-id="adc44-214">Для создания новой учетной записи хранения укажите для нее имя.</span><span class="sxs-lookup"><span data-stu-id="adc44-214">To create a new storage account, specify a name for the new account.</span></span> <span data-ttu-id="adc44-215">Обратите внимание, что учетные записи хранения, связанные с группой сходства, не будут доступны в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="adc44-215">Note that storage accounts associated with an Affinity Group will not be available in the drop-down list.</span></span>  
  
-   <span data-ttu-id="adc44-216">**Целевая база данных** — укажите сведения о целевой базе данных.</span><span class="sxs-lookup"><span data-stu-id="adc44-216">**Target Database** - Specify details for the target database.</span></span>  
  
-   <span data-ttu-id="adc44-217">**Соединение с сервером** — сведения о подключении для сервера.</span><span class="sxs-lookup"><span data-stu-id="adc44-217">**Server Connection** - Connection details for the server.</span></span>  
  
-   <span data-ttu-id="adc44-218">**База данных** — укажите или подтвердите имя новой базы данных.</span><span class="sxs-lookup"><span data-stu-id="adc44-218">**Database** - Specify or confirm the name of a new database.</span></span> <span data-ttu-id="adc44-219">Если имя базы данных уже существует на целевом экземпляре SQL Server, измените имя базы данных.</span><span class="sxs-lookup"><span data-stu-id="adc44-219">If the database name already exists on the destination SQL Server instance, we suggest that you specify a modified database name.</span></span>  
  
##  <a name="summary-page"></a><a name="Summary"></a> <span data-ttu-id="adc44-220">Страница «Сводка»</span><span class="sxs-lookup"><span data-stu-id="adc44-220">Summary Page</span></span>  
 <span data-ttu-id="adc44-221">На этой странице можно просмотреть указанные параметры операции.</span><span class="sxs-lookup"><span data-stu-id="adc44-221">Use this page to review the specified settings for the operation.</span></span> <span data-ttu-id="adc44-222">Чтобы выполнить развертывание с заданными параметрами, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="adc44-222">To complete the deploy operation using the specified settings, click **Finish**.</span></span> <span data-ttu-id="adc44-223">Чтобы отменить операцию развертывания и выйти из мастера, нажмите кнопку **"Отмена"**.</span><span class="sxs-lookup"><span data-stu-id="adc44-223">To cancel the deploy operation and exit the wizard, click **Cancel**.</span></span>  
  
 <span data-ttu-id="adc44-224">Для развертывания сведений о базе данных в SQL Server базе данных на виртуальной машине Azure могут потребоваться ручные действия.</span><span class="sxs-lookup"><span data-stu-id="adc44-224">There may be manual steps required to deploy database details to the SQL Server database on the Azure VM.</span></span> <span data-ttu-id="adc44-225">Эти действия будут подробно описаны.</span><span class="sxs-lookup"><span data-stu-id="adc44-225">These steps will be outlined in detail for you.</span></span>  
  
##  <a name="results-page"></a><a name="Results"></a><span data-ttu-id="adc44-226">Страница «результаты»</span><span class="sxs-lookup"><span data-stu-id="adc44-226">Results Page</span></span>  
 <span data-ttu-id="adc44-227">На этой странице отображаются сведения об успешности операции развертывания по результатам каждого действия.</span><span class="sxs-lookup"><span data-stu-id="adc44-227">This page reports the success or failure of the deploy operation, showing the results of each action.</span></span> <span data-ttu-id="adc44-228">Для каждого действия, в котором обнаружена ошибка, предусмотрен индикатор в столбце **Результат** .</span><span class="sxs-lookup"><span data-stu-id="adc44-228">Any action that encountered an error will have an indication in the **Result** column.</span></span> <span data-ttu-id="adc44-229">Щелкните эту ссылку, чтобы просмотреть отчет об ошибках, относящихся к данному действию.</span><span class="sxs-lookup"><span data-stu-id="adc44-229">Click the link to view a report of the error for that action.</span></span>  
  
 <span data-ttu-id="adc44-230">Чтобы завершить работу мастера, нажмите кнопку **Готово** .</span><span class="sxs-lookup"><span data-stu-id="adc44-230">Click **Finish** to close the wizard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adc44-231">См. также:</span><span class="sxs-lookup"><span data-stu-id="adc44-231">See Also</span></span>  
 <span data-ttu-id="adc44-232">[адаптер для облака для SQL Server](../../database-engine/cloud-adapter-for-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="adc44-232">[Cloud Adapter for SQL Server](../../database-engine/cloud-adapter-for-sql-server.md) </span></span>  
 <span data-ttu-id="adc44-233">[Управление жизненным циклом базы данных](../database-lifecycle-management.md) </span><span class="sxs-lookup"><span data-stu-id="adc44-233">[Database Lifecycle Management](../database-lifecycle-management.md) </span></span>  
 <span data-ttu-id="adc44-234">[Экспорт приложения уровня данных](../data-tier-applications/export-a-data-tier-application.md) </span><span class="sxs-lookup"><span data-stu-id="adc44-234">[Export a Data-tier Application](../data-tier-applications/export-a-data-tier-application.md) </span></span>  
 <span data-ttu-id="adc44-235">[Импорт BACPAC-файла для создания новой пользовательской базы данных](../data-tier-applications/import-a-bacpac-file-to-create-a-new-user-database.md) </span><span class="sxs-lookup"><span data-stu-id="adc44-235">[Import a BACPAC File to Create a New User Database](../data-tier-applications/import-a-bacpac-file-to-create-a-new-user-database.md) </span></span>  
 <span data-ttu-id="adc44-236">[Резервное копирование и восстановление базы данных SQL Azure](https://msdn.microsoft.com/library/azure/jj650016.aspx) </span><span class="sxs-lookup"><span data-stu-id="adc44-236">[Azure SQL Database Backup and Restore](https://msdn.microsoft.com/library/azure/jj650016.aspx) </span></span>  
 <span data-ttu-id="adc44-237">[Развертывание SQL Server на виртуальных машинах Azure](https://msdn.microsoft.com/library/dn133141.aspx) </span><span class="sxs-lookup"><span data-stu-id="adc44-237">[SQL Server Deployment in Azure Virtual Machines](https://msdn.microsoft.com/library/dn133141.aspx) </span></span>  
 [<span data-ttu-id="adc44-238">Подготовка к переходу на SQL Server в виртуальных машинах Azure</span><span class="sxs-lookup"><span data-stu-id="adc44-238">Getting Ready to Migrate to SQL Server in Azure Virtual Machines</span></span>](https://msdn.microsoft.com/library/dn133142.aspx)  
  
  
