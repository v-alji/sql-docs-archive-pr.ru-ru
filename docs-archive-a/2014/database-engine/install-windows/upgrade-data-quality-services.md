---
title: Обновление служб Data Quality Services | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: f396666b-7754-4efc-9507-0fd114cc32d5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9d2544df341a831f2f676ec58150ed64a800fb96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657876"
---
# <a name="upgrade-data-quality-services"></a><span data-ttu-id="3a3b9-102">Обновление служб Data Quality Services</span><span class="sxs-lookup"><span data-stu-id="3a3b9-102">Upgrade Data Quality Services</span></span>
  <span data-ttu-id="3a3b9-103">Этот раздел предоставляет сведения о том, как обновить существующую установку служб Data Quality Services (DQS) в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] версии CTP2.</span><span class="sxs-lookup"><span data-stu-id="3a3b9-103">This topic provides information on how to upgrade your existing installation of Data Quality Services (DQS) to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] CTP2.</span></span> <span data-ttu-id="3a3b9-104">В процессе обновления сервера служб DQS в службах DQS в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], необходимо обновить схему базы данных служб DQS.</span><span class="sxs-lookup"><span data-stu-id="3a3b9-104">As part of upgrading your Data Quality Server in DQS to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], you must also upgrade the DQS databases schema.</span></span>  
  
> [!IMPORTANT]
>  -   <span data-ttu-id="3a3b9-105">Необходимо создать резервную копию баз данных DQS, прежде чем обновлять DQS, чтобы предотвратить любую случайную потерю данных при обновлении схемы.</span><span class="sxs-lookup"><span data-stu-id="3a3b9-105">You must back up your DQS databases before upgrading DQS to prevent any accidental data loss during the schema upgrade.</span></span> <span data-ttu-id="3a3b9-106">Дополнительные сведения о создании резервной копии баз данных DQS см. в разделе [Backing Up and Restoring DQS Databases](../../data-quality-services/backing-up-and-restoring-dqs-databases.md).</span><span class="sxs-lookup"><span data-stu-id="3a3b9-106">For information about backing up DQS databases, see [Backing Up and Restoring DQS Databases](../../data-quality-services/backing-up-and-restoring-dqs-databases.md).</span></span>  
> -   <span data-ttu-id="3a3b9-107">Для выполнения задач по обеспечению качества данных вы можете подключиться к версии [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] сервера DQS, используя текущую или более раннюю версию клиента DQS или [преобразование "Очистка DQS"](../../integration-services/data-flow/transformations/dqs-cleansing-transformation.md) в службах Integration Services.</span><span class="sxs-lookup"><span data-stu-id="3a3b9-107">You can connect to the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] version of Data Quality Server by using the current or an earlier version of Data Quality Client or the [DQS Cleansing Transformation](../../integration-services/data-flow/transformations/dqs-cleansing-transformation.md) in Integration Services to perform your data quality tasks.</span></span>  
> -   <span data-ttu-id="3a3b9-108">Можно продолжить использование надстройки служб Master Data Services для Excel версии [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] с пакетом обновления 1 (SP1) после обновления служб Data Quality Services и Master Data Services до версии [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] CTP2.</span><span class="sxs-lookup"><span data-stu-id="3a3b9-108">You can continue using the [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] SP1 version of Master Data Services Add-In for Excel after upgrading Data Quality Services and Master Data Services to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] CTP2.</span></span> <span data-ttu-id="3a3b9-109">Однако любая более ранняя версия надстройки служб Master Data Services для Excel перестанет работать после обновления до версии SQL Server 2014 CTP2.</span><span class="sxs-lookup"><span data-stu-id="3a3b9-109">However, any earlier version of the Master Data Services Add-In for Excel will not work after upgrading to SQL Server 2014 CTP2.</span></span> <span data-ttu-id="3a3b9-110">Можно загрузить надстройку служб Master Data Services для Excel версии [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] с пакетом обновления 1 (SP1) по [этой ссылке](https://go.microsoft.com/fwlink/?LinkId=328664).</span><span class="sxs-lookup"><span data-stu-id="3a3b9-110">You can download the [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] SP1 version of Master Data Services Add-In for Excel from [here](https://go.microsoft.com/fwlink/?LinkId=328664).</span></span>  
  
##  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="3a3b9-111">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="3a3b9-111">Prerequisites</span></span>  
  
-   <span data-ttu-id="3a3b9-112">Необходимо выполнить вход от имени члена группы администраторов на компьютере [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3a3b9-112">You must be logged on as a member of the Administrators group on the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] computer.</span></span>  
  
-   <span data-ttu-id="3a3b9-113">Учетная запись пользователя Windows должна входить в предопределенную роль сервера sysadmin на экземпляре SQL Server, где установлен сервер [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3a3b9-113">Your Windows user account must be a member of the sysadmin fixed server role in the SQL Server instance where [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] is installed.</span></span>  
  
##  <a name="upgrading-dqs"></a><a name="Upgrade"></a> <span data-ttu-id="3a3b9-114">Обновление DQS</span><span class="sxs-lookup"><span data-stu-id="3a3b9-114">Upgrading DQS</span></span>  
 <span data-ttu-id="3a3b9-115">Обновление DQS:</span><span class="sxs-lookup"><span data-stu-id="3a3b9-115">To upgrade DQS:</span></span>  
  
1.  <span data-ttu-id="3a3b9-116">Создайте резервные копии баз данных DQS перед началом процесса обновления.</span><span class="sxs-lookup"><span data-stu-id="3a3b9-116">Back up your DQS databases before you start the upgrade process.</span></span> <span data-ttu-id="3a3b9-117">Дополнительные сведения о создании резервной копии баз данных DQS см. в разделе [Backing Up and Restoring DQS Databases](../../data-quality-services/backing-up-and-restoring-dqs-databases.md).</span><span class="sxs-lookup"><span data-stu-id="3a3b9-117">For information about backing up DQS databases, see [Backing Up and Restoring DQS Databases](../../data-quality-services/backing-up-and-restoring-dqs-databases.md).</span></span>  
  
2.  <span data-ttu-id="3a3b9-118">Обновите экземпляр SQL Server, на котором установлен компонент DQS для служб [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a3b9-118">Upgrade the SQL Server instance where DQS is installed to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
    1.  <span data-ttu-id="3a3b9-119">Запустите мастер установки [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3a3b9-119">Run the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Setup wizard.</span></span>  
  
    2.  <span data-ttu-id="3a3b9-120">На панели слева щелкните **Установка**.</span><span class="sxs-lookup"><span data-stu-id="3a3b9-120">In the left pane, click **Installation**.</span></span>  
  
    3.  <span data-ttu-id="3a3b9-121">На правой панели щелкните **обновить с SQL Server 2005, SQL Server 2008, SQL Server 2008 R2 или SQL Server 2012**.</span><span class="sxs-lookup"><span data-stu-id="3a3b9-121">In the right pane, click **Upgrade from SQL Server 2005, SQL Server 2008, SQL Server 2008 R2 or SQL Server 2012**.</span></span>  
  
    4.  <span data-ttu-id="3a3b9-122">Завершите работу мастера установки.</span><span class="sxs-lookup"><span data-stu-id="3a3b9-122">Complete the Setup wizard.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="3a3b9-123">Это обновит экземпляр SQL Server в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , а также задает последнюю Data Quality Client, если клиент DQS был ранее установлен на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="3a3b9-123">This will upgrade your SQL Server instance to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] and also install the latest Data Quality Client, if Data Quality Client was previously installed on this computer.</span></span> <span data-ttu-id="3a3b9-124">При наличии клиента служб DQS установлены на других компьютерах, необходимо выполнить шаги по в шаге 2 на этих компьютерах, чтобы установить текущую версию клиента служб DQS.</span><span class="sxs-lookup"><span data-stu-id="3a3b9-124">If you have Data Quality Client installed on other computers, you must run the sub steps in Step 2 on those computers to install the current version of Data Quality Client.</span></span> <span data-ttu-id="3a3b9-125">Мастер установки установит текущую версию служб Data Quality Client вместе с текущей версией клиента служб DQS.</span><span class="sxs-lookup"><span data-stu-id="3a3b9-125">The Setup wizard installs the current version of Data Quality Client alongside the existing version of Data Quality Client.</span></span> <span data-ttu-id="3a3b9-126">После обновления схемы баз данных DQS можно подключиться к [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] версию сервера служб DQS с помощью текущего или более ранней версией клиента служб DQS.</span><span class="sxs-lookup"><span data-stu-id="3a3b9-126">After you upgrade the DQS databases schema, you can connect to the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] version of Data Quality Server by using the current or an earlier version of Data Quality Client.</span></span>  
  
3.  <span data-ttu-id="3a3b9-127">Обновите схему баз данных DQS.</span><span class="sxs-lookup"><span data-stu-id="3a3b9-127">Upgrade the DQS databases schema.</span></span>  
  
    1.  <span data-ttu-id="3a3b9-128">Откройте командную строку от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="3a3b9-128">Start Command Prompt as an administrator.</span></span>  
  
    2.  <span data-ttu-id="3a3b9-129">В командной строке перейдите в папку, где находится файл DQSInstaller.exe.</span><span class="sxs-lookup"><span data-stu-id="3a3b9-129">At the command prompt, change your directory to the location where DQSInstaller.exe is available.</span></span> <span data-ttu-id="3a3b9-130">Для экземпляра SQL Server по умолчанию файл DQSInstaller.exe будет находиться в папке «C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn».</span><span class="sxs-lookup"><span data-stu-id="3a3b9-130">For the default instance of SQL Server, the DQSInstaller.exe file is available at C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn:</span></span>  
  
        ```  
        cd C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn  
        ```  
  
    3.  <span data-ttu-id="3a3b9-131">В командной строке введите следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="3a3b9-131">At the command prompt, type the following command, and press ENTER:</span></span>  
  
        ```  
        dqsinstaller.exe -upgrade  
        ```  
  
    4.  <span data-ttu-id="3a3b9-132">Установщик предложит создать резервную копию базы данных DQS, прежде чем продолжить.</span><span class="sxs-lookup"><span data-stu-id="3a3b9-132">The installer prompts you for backing up the DQS databases before proceeding.</span></span> <span data-ttu-id="3a3b9-133">Если резервное копирование баз данных DQS уже выполнено, введите `Y` или `Yes` и нажмите клавишу ВВОД, чтобы продолжить обновление.</span><span class="sxs-lookup"><span data-stu-id="3a3b9-133">If you have already backed up your DQS databases, type `Y` or `Yes`, and then press ENTER to continue with the upgrade.</span></span>  
  
    5.  <span data-ttu-id="3a3b9-134">После успешного обновления схемы баз данных DQS отображается сообщение о завершении.</span><span class="sxs-lookup"><span data-stu-id="3a3b9-134">A completion message is displayed after successful upgrade of the DQS databases schema.</span></span>  
  
##  <a name="verifying-the-dqs-databases-schema-upgrade"></a><a name="Verify"></a> <span data-ttu-id="3a3b9-135">Проверка обновления баз данных DQS схемы</span><span class="sxs-lookup"><span data-stu-id="3a3b9-135">Verifying the DQS Databases Schema Upgrade</span></span>  
 <span data-ttu-id="3a3b9-136">Для проверки, что схема баз данных DQS обновлена успешно, можно проверить в текущей версии базы данных DQS_MAIN и DQS_PROJECTS с помощью запроса к таблице A_DB_VERSION в каждой базе данных.</span><span class="sxs-lookup"><span data-stu-id="3a3b9-136">To verify that DQS databases schema have successfully upgraded, you can check the current version in the DQS_MAIN and DQS_PROJECTS databases by querying the A_DB_VERSION table in each database.</span></span> <span data-ttu-id="3a3b9-137">Для этого:</span><span class="sxs-lookup"><span data-stu-id="3a3b9-137">To do so:</span></span>  
  
1.  <span data-ttu-id="3a3b9-138">Запустите среду SQL Server Management Studio и установите соединение с экземпляром SQL Server, содержащий обновленные базы данных DQS схемы.</span><span class="sxs-lookup"><span data-stu-id="3a3b9-138">Start SQL Server Management Studio, and connect to the SQL Server instance that contains the upgraded DQS databases schema.</span></span>  
  
2.  <span data-ttu-id="3a3b9-139">Выполните следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="3a3b9-139">Run the following query:</span></span>  
  
    ```  
    SELECT * FROM DQS_MAIN.dbo.A_DB_VERSION WHERE STATUS=2;  
    SELECT * FROM DQS_PROJECTS.dbo.A_DB_VERSION WHERE STATUS=2;  
    ```  
  
3.  <span data-ttu-id="3a3b9-140">Выводится запись для каждой операции обновления, а также дата создания обновления.</span><span class="sxs-lookup"><span data-stu-id="3a3b9-140">The output will display an entry for each upgrade along with the date of the upgrade.</span></span> <span data-ttu-id="3a3b9-141">Максимальное VERSION_ID и ASSEMBLY_VERSION на самой последней даты текущую версию.</span><span class="sxs-lookup"><span data-stu-id="3a3b9-141">The maximum VERSION_ID and ASSEMBLY_VERSION on the latest date is the current version.</span></span> <span data-ttu-id="3a3b9-142">Значение 2 в столбце STATUS означает успешное выполнение процедуры.</span><span class="sxs-lookup"><span data-stu-id="3a3b9-142">A value of 2 in the STATUS column indicates success.</span></span> <span data-ttu-id="3a3b9-143">Если возникла ошибка, то ОШИБКА перечисляются в столбец.</span><span class="sxs-lookup"><span data-stu-id="3a3b9-143">If an error has occurred, the error will be listed in the ERROR column.</span></span> <span data-ttu-id="3a3b9-144">Образец вывода:</span><span class="sxs-lookup"><span data-stu-id="3a3b9-144">A sample output:</span></span>  
  
    |<span data-ttu-id="3a3b9-145">ID</span><span class="sxs-lookup"><span data-stu-id="3a3b9-145">ID</span></span>|<span data-ttu-id="3a3b9-146">UPGRADE_DATE</span><span class="sxs-lookup"><span data-stu-id="3a3b9-146">UPGRADE_DATE</span></span>|<span data-ttu-id="3a3b9-147">VERSION_ID</span><span class="sxs-lookup"><span data-stu-id="3a3b9-147">VERSION_ID</span></span>|<span data-ttu-id="3a3b9-148">ASSEMBLY_VERSION</span><span class="sxs-lookup"><span data-stu-id="3a3b9-148">ASSEMBLY_VERSION</span></span>|<span data-ttu-id="3a3b9-149">USER_NAME</span><span class="sxs-lookup"><span data-stu-id="3a3b9-149">USER_NAME</span></span>|<span data-ttu-id="3a3b9-150">Состояние</span><span class="sxs-lookup"><span data-stu-id="3a3b9-150">STATUS</span></span>|<span data-ttu-id="3a3b9-151">ошибка</span><span class="sxs-lookup"><span data-stu-id="3a3b9-151">ERROR</span></span>|  
    |--------|-------------------|-----------------|-----------------------|----------------|------------|-----------|  
    |<span data-ttu-id="3a3b9-152">1000</span><span class="sxs-lookup"><span data-stu-id="3a3b9-152">1000</span></span>|<span data-ttu-id="3a3b9-153">2013-08-11 05:26:39.567</span><span class="sxs-lookup"><span data-stu-id="3a3b9-153">2013-08-11 05:26:39.567</span></span>|<span data-ttu-id="3a3b9-154">1200</span><span class="sxs-lookup"><span data-stu-id="3a3b9-154">1200</span></span>|<span data-ttu-id="3a3b9-155">11.0.3000.0</span><span class="sxs-lookup"><span data-stu-id="3a3b9-155">11.0.3000.0</span></span>|\<DOMAIN\UserName>|<span data-ttu-id="3a3b9-156">2</span><span class="sxs-lookup"><span data-stu-id="3a3b9-156">2</span></span>||  
    |<span data-ttu-id="3a3b9-157">1001</span><span class="sxs-lookup"><span data-stu-id="3a3b9-157">1001</span></span>|<span data-ttu-id="3a3b9-158">2013-09-19 15:09:37.750</span><span class="sxs-lookup"><span data-stu-id="3a3b9-158">2013-09-19 15:09:37.750</span></span>|<span data-ttu-id="3a3b9-159">1600</span><span class="sxs-lookup"><span data-stu-id="3a3b9-159">1600</span></span>|<span data-ttu-id="3a3b9-160">12.0.xxxx.0</span><span class="sxs-lookup"><span data-stu-id="3a3b9-160">12.0.xxxx.0</span></span>|\<DOMAIN\UserName>|<span data-ttu-id="3a3b9-161">2</span><span class="sxs-lookup"><span data-stu-id="3a3b9-161">2</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="3a3b9-162">См. также:</span><span class="sxs-lookup"><span data-stu-id="3a3b9-162">See Also</span></span>  
 <span data-ttu-id="3a3b9-163">[Install Data Quality Services](../../data-quality-services/install-windows/install-data-quality-services.md) </span><span class="sxs-lookup"><span data-stu-id="3a3b9-163">[Install Data Quality Services](../../data-quality-services/install-windows/install-data-quality-services.md) </span></span>  
 <span data-ttu-id="3a3b9-164">[Удаление объектов сервера служб Data Quality](../../sql-server/install/remove-data-quality-server-objects.md) </span><span class="sxs-lookup"><span data-stu-id="3a3b9-164">[Remove Data Quality Server Objects](../../sql-server/install/remove-data-quality-server-objects.md) </span></span>  
 [<span data-ttu-id="3a3b9-165">Обновление до SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="3a3b9-165">Upgrade to SQL Server 2014</span></span>](upgrade-sql-server.md)  
  
  
