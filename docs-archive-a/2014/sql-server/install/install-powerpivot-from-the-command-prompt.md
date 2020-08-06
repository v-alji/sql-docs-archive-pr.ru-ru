---
title: Установка PowerPivot из командной строки | Документация Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 7f1f2b28-c9f5-49ad-934b-02f2fa6b9328
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 54f30142cdc2e39b3ec565d4f965fdad675405e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668044"
---
# <a name="install-powerpivot-from-the-command-prompt"></a><span data-ttu-id="a2837-102">Установка PowerPivot из командной строки</span><span class="sxs-lookup"><span data-stu-id="a2837-102">Install PowerPivot from the Command Prompt</span></span>
  <span data-ttu-id="a2837-103">Программу установки SQL Server PowerPivot для SharePoint можно запустить из командной строки.</span><span class="sxs-lookup"><span data-stu-id="a2837-103">You can run Setup from the command line to install SQL Server PowerPivot for SharePoint.</span></span> <span data-ttu-id="a2837-104">В команду необходимо включить параметр `/ROLE` и исключить из нее параметр `/FEATURES`.</span><span class="sxs-lookup"><span data-stu-id="a2837-104">You must include the `/ROLE` parameter in your command and exclude the `/FEATURES` parameter.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a2837-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="a2837-105">Prerequisites</span></span>  
 <span data-ttu-id="a2837-106">Необходимо установить выпуск SharePoint Server 2010 Enterprise Edition с пакетом обновления 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="a2837-106">SharePoint Server 2010 enterprise edition with Service Pack 1 (SP1) must be installed.</span></span>  
  
 <span data-ttu-id="a2837-107">Для подготовки к работе служб Analysis Services необходимо использовать учетные записи пользователей домена.</span><span class="sxs-lookup"><span data-stu-id="a2837-107">You must use domain accounts to provision Analysis Services.</span></span>  
  
 <span data-ttu-id="a2837-108">Компьютер должен быть присоединен к тому же домену, что и ферма SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a2837-108">The computer must be joined to the same domain as the SharePoint farm.</span></span>  
  
##  <a name="role-based-installation-options"></a><a name="Commands"></a><span data-ttu-id="a2837-109">Параметры установки на основе/ROLE</span><span class="sxs-lookup"><span data-stu-id="a2837-109">/ROLE based installation options</span></span>  
 <span data-ttu-id="a2837-110">При развертывании PowerPivot для SharePoint используется параметр `/ROLE` вместо параметра `/FEATURES`.</span><span class="sxs-lookup"><span data-stu-id="a2837-110">For PowerPivot for SharePoint deployments, the `/ROLE` parameter is used in place of the `/FEATURES` parameter.</span></span> <span data-ttu-id="a2837-111">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="a2837-111">Valid values include:</span></span>  
  
-   `SPI_AS_ExistingFarm`  
  
-   `SPI_AS_NewFarm`  
  
 <span data-ttu-id="a2837-112">При использовании обеих ролей устанавливаются файлы приложения, конфигурации и развертывания, позволяющие PowerPivot для SharePoint работать в ферме SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a2837-112">Both roles install application, configuration, and deployment files that enable a PowerPivot for SharePoint to run in a SharePoint farm.</span></span> <span data-ttu-id="a2837-113">При выборе любой роли программа установки проверит соответствие требованиям к программному и аппаратному обеспечению, которые должны быть удовлетворены для интеграции с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a2837-113">Specifying either role will cause Setup to check for hardware and software requirements necessary for SharePoint integration.</span></span>  
  
 <span data-ttu-id="a2837-114">Параметр «Существующая ферма» предполагает, что ферма SharePoint уже сконфигурирована.</span><span class="sxs-lookup"><span data-stu-id="a2837-114">The existing farm option assumes that a SharePoint farm is already in place.</span></span> <span data-ttu-id="a2837-115">При выборе варианта Новая ферма предполагается, что вы создадите новую ферму. Он поддерживает добавление ядро СУБД экземпляра в синтаксисе командной строки, чтобы можно было использовать экземпляр ядро СУБД в качестве сервера базы данных фермы.</span><span class="sxs-lookup"><span data-stu-id="a2837-115">The new farm option assumes that you will create a new farm; it supports the addition of a Database Engine instance in the command line syntax so that you can use the Database Engine instance as the farm's database server.</span></span>  
  
 <span data-ttu-id="a2837-116">В отличие от предыдущих выпусков, все задачи настройки сервера выполняются как задачи после установки.</span><span class="sxs-lookup"><span data-stu-id="a2837-116">In contrast with the previous releases, all server configuration tasks are performed as post-installation tasks.</span></span> <span data-ttu-id="a2837-117">В целях автоматизации шагов по установке и настройке для настройки сервера можно использовать PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a2837-117">If you are automating installation and configuration steps, you can use PowerShell to configure the server.</span></span> <span data-ttu-id="a2837-118">Дополнительные сведения см. в статье [Настройка PowerPivot с помощью Windows PowerShell](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/power-pivot-configuration-using-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="a2837-118">For more information, see [PowerPivot Configuration using Windows PowerShell](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/power-pivot-configuration-using-windows-powershell).</span></span>  
  
## <a name="example-commands"></a><span data-ttu-id="a2837-119">Примеры команд</span><span class="sxs-lookup"><span data-stu-id="a2837-119">Example Commands</span></span>  
 <span data-ttu-id="a2837-120">В следующих примерах демонстрируется применение каждого из вариантов.</span><span class="sxs-lookup"><span data-stu-id="a2837-120">The following examples illustrate the usage of each option.</span></span> <span data-ttu-id="a2837-121">В примере 1 показано `SPI_AS_ExistingFarm` .</span><span class="sxs-lookup"><span data-stu-id="a2837-121">Example 1 shows `SPI_AS_ExistingFarm`.</span></span>  
  
```cmd
Setup.exe /q /IAcceptSQLServerLicenseTerms /ACTION=install /ROLE=SPI_AS_ExistingFarm /INSTANCENAME=PowerPivot /INDICATEPROGRESS/ASSVCACCOUNT=<DomainName\UserName> /ASSVCPASSWORD=<StrongPassword> /ASSYSADMINACCOUNTS=<DomainName\UserName>   
```  
  
 <span data-ttu-id="a2837-122">Пример 2 иллюстрирует вариант `SPI_AS_NewFarm`.</span><span class="sxs-lookup"><span data-stu-id="a2837-122">Example 2 shows `SPI_AS_NewFarm`.</span></span> <span data-ttu-id="a2837-123">Обратите внимание, что он включает параметры для провизионирования компонента Database Engine.</span><span class="sxs-lookup"><span data-stu-id="a2837-123">Notice that it includes parameters for provisioning the Database Engine.</span></span>  
  
```cmd
Setup.exe /q /IAcceptSQLServerLicenseTerms /ACTION=install /ROLE=SPI_AS_NewFarm /INSTANCENAME=PowerPivot /INDICATEPROGRESS/SQLSVCACCOUNT=<DomainName\UserName> /SQLSVCPASSWORD=<StrongPassword> /SQLSYSADMINACCOUNTS=<DomainName\UserName> /AGTSVCACCOUNT=<DomainName\UserName> /AGTSVCPASSWORD=<StrongPassword> /ASSVCACCOUNT=<DomainName\UserName> /ASSVCPASSWORD=<StrongPassword> /ASSYSADMINACCOUNTS=<DomainName\UserName>   
```  
  
##  <a name="modifying-the-command-syntax"></a><a name="Join"></a><span data-ttu-id="a2837-124">Изменение синтаксиса команды</span><span class="sxs-lookup"><span data-stu-id="a2837-124">Modifying the command syntax</span></span>  
 <span data-ttu-id="a2837-125">Используйте следующие шаги для изменения примера синтаксиса команды.</span><span class="sxs-lookup"><span data-stu-id="a2837-125">Use the following steps to modify the example command syntax.</span></span>  
  
1.  <span data-ttu-id="a2837-126">Скопируйте следующую команду в Блокнот:</span><span class="sxs-lookup"><span data-stu-id="a2837-126">Copy the following command into Notepad:</span></span>  
  
    ```cmd
    Setup.exe /q /IAcceptSQLServerLicenseTerms /ACTION=install /ROLE=SPI_AS_ExistingFarm /INSTANCENAME=PowerPivot /INDICATEPROGRESS/ASSVCACCOUNT=<DomainName\UserName> /ASSVCPASSWORD=<StrongPassword> /ASSYSADMINACCOUNTS=<DomainName\UserName>   
    ```  
  
     <span data-ttu-id="a2837-127">Параметр `/q` запускает программу установки в «тихом» режиме, в котором пользовательский интерфейс не задействуется.</span><span class="sxs-lookup"><span data-stu-id="a2837-127">The `/q` parameter runs Setup in quiet mode, which suppresses the user interface.</span></span>  
  
     <span data-ttu-id="a2837-128">Когда параметр `/IAcceptSQLServerLicenseTerms` или `/q` задан для автоматических установок, требуется `/qs`.</span><span class="sxs-lookup"><span data-stu-id="a2837-128">The `/IAcceptSQLServerLicenseTerms` is required when the `/q` or `/qs` parameter is specified for un-attended installations.</span></span>  
  
     <span data-ttu-id="a2837-129">Параметр `/action` дает указание программе установки выполнить установку.</span><span class="sxs-lookup"><span data-stu-id="a2837-129">The `/action` parameter instructs Setup to perform an installation.</span></span>  
  
     <span data-ttu-id="a2837-130">Параметр `/role` дает указание программе установки установить службы Analysis Services и файлы конфигурации, необходимые для работы PowerPivot для SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a2837-130">The `/role` parameter instructs Setup to install the Analysis Services program and configuration files required for PowerPivot for SharePoint.</span></span> <span data-ttu-id="a2837-131">Эта роль также определяет и использует сведения о соединении существующей фермы для доступа к базе данных конфигурации SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a2837-131">This role also detects and uses the existing farm connectivity information to access the SharePoint configuration database.</span></span> <span data-ttu-id="a2837-132">Это обязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="a2837-132">This parameter is required.</span></span> <span data-ttu-id="a2837-133">Используйте его вместо параметра `/features`, чтобы указать компоненты для установки.</span><span class="sxs-lookup"><span data-stu-id="a2837-133">Use it instead of the `/features` parameter to specify the components to install.</span></span>  
  
     <span data-ttu-id="a2837-134">Параметр `/instancename` указывает «PowerPivot» в качестве именованного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="a2837-134">The `/instancename` parameter specifies 'PowerPivot' as a named instance.</span></span> <span data-ttu-id="a2837-135">Это значение задано жестко, его невозможно изменить.</span><span class="sxs-lookup"><span data-stu-id="a2837-135">This value is hard-coded and cannot be changed.</span></span> <span data-ttu-id="a2837-136">Оно указывается в команде в образовательных целях с тем, чтобы пользователь знал, как устанавливается служба.</span><span class="sxs-lookup"><span data-stu-id="a2837-136">It is specified in the command for educational purposes so that you know how the service is installed.</span></span>  
  
     <span data-ttu-id="a2837-137">С помощью параметра `/indicateprogress` можно отслеживать ход выполнения в окне командной строки.</span><span class="sxs-lookup"><span data-stu-id="a2837-137">The `/indicateprogress` parameter allows you to monitor progress in the command prompt window.</span></span>  
  
2.  <span data-ttu-id="a2837-138">Параметр `PID` в команде не указывается, в результате чего устанавливается выпуск Evaluation.</span><span class="sxs-lookup"><span data-stu-id="a2837-138">The `PID` parameter is omitted from the command, which causes the Evaluation edition to be installed.</span></span> <span data-ttu-id="a2837-139">Если требуется установить выпуск Enterprise Edition, добавьте параметр PID в команду запуска программы установки и укажите действительный ключ продукта.</span><span class="sxs-lookup"><span data-stu-id="a2837-139">If you want to install the Enterprise edition, add the PID to your Setup command and provide a valid product key.</span></span>  
  
    ```  
    /PID=<product key for an Enterprise installation>  
    ```  
  
3.  <span data-ttu-id="a2837-140">Замените заполнители для \<domain\username> и \<StrongPassword> на действительные учетные записи пользователей и пароли.</span><span class="sxs-lookup"><span data-stu-id="a2837-140">Replace the placeholders for \<domain\username> and \<StrongPassword>with valid user accounts and passwords.</span></span>  
  
     <span data-ttu-id="a2837-141">`/assvaccount`Параметры и **/ассвкпассворд** используются для настройки [!INCLUDE[ssGeminiSrv](../../includes/ssgeminisrv-md.md)] экземпляра на сервере приложений.</span><span class="sxs-lookup"><span data-stu-id="a2837-141">The `/assvaccount` and **/assvcpassword** parameters are used to configure the [!INCLUDE[ssGeminiSrv](../../includes/ssgeminisrv-md.md)] instance on the application server.</span></span> <span data-ttu-id="a2837-142">Замените эти заполнители на допустимые сведения учетной записи.</span><span class="sxs-lookup"><span data-stu-id="a2837-142">Replace these placeholders with valid account information.</span></span>  
  
     <span data-ttu-id="a2837-143">Для параметра **/ассисадминаккаунтс** необходимо задать идентификатор пользователя, выполняющего программу установки SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a2837-143">The **/assysadminaccounts** parameter must be set to the identity of the user who is running SQL Server Setup.</span></span> <span data-ttu-id="a2837-144">Для служб необходимо указать хотя бы одного системного администратора.</span><span class="sxs-lookup"><span data-stu-id="a2837-144">You must specify at least one system administrator.</span></span> <span data-ttu-id="a2837-145">Следует отметить, что программа установки SQL Server больше не предоставляет автоматически разрешения sysadmin членам встроенной группы «Администраторы».</span><span class="sxs-lookup"><span data-stu-id="a2837-145">Note that SQL Server Setup no long grants automatic sysadmin permissions to members of the built-in Administrators group.</span></span>  
  
4.  <span data-ttu-id="a2837-146">Удалите разрывы строк.</span><span class="sxs-lookup"><span data-stu-id="a2837-146">Remove line breaks.</span></span>  
  
5.  <span data-ttu-id="a2837-147">Выделите всю команду и выберите команду **Копировать** в меню Правка.</span><span class="sxs-lookup"><span data-stu-id="a2837-147">Select the entire command and then click **Copy** on the Edit menu.</span></span>  
  
6.  <span data-ttu-id="a2837-148">Откройте командную строку от имени учетной записи администратора.</span><span class="sxs-lookup"><span data-stu-id="a2837-148">Open an administrator command prompt.</span></span> <span data-ttu-id="a2837-149">Для этого нажмите кнопку **Пуск**, щелкните правой кнопкой мыши командную строку и выберите **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="a2837-149">To do this, click **Start**, right-click the command prompt, and select **Run as administrator**.</span></span>  
  
7.  <span data-ttu-id="a2837-150">Перейдите в папку на диске или общую папку, которая содержит установочный носитель SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a2837-150">Navigate to the drive or shared folder that contains the SQL Server installation media.</span></span>  
  
8.  <span data-ttu-id="a2837-151">Вставьте измененную команду в командную строку.</span><span class="sxs-lookup"><span data-stu-id="a2837-151">Paste the revised command into the command line.</span></span> <span data-ttu-id="a2837-152">Для этого щелкните значок в левом верхнем углу окна командной строки, наведите указатель мыши на пункт **изменить**и выберите команду **Вставить**.</span><span class="sxs-lookup"><span data-stu-id="a2837-152">To do this, click the icon in the top left corner of the command prompt window, point to **Edit**, and then click **Paste**.</span></span>  
  
9. <span data-ttu-id="a2837-153">Нажмите клавишу **Ввод** , чтобы выполнить команду.</span><span class="sxs-lookup"><span data-stu-id="a2837-153">Press **Enter** to run the command.</span></span> <span data-ttu-id="a2837-154">Подождите завершения работы программы установки.</span><span class="sxs-lookup"><span data-stu-id="a2837-154">Wait for setup to complete.</span></span> <span data-ttu-id="a2837-155">В окне командной строки можно наблюдать за ходом выполнения.</span><span class="sxs-lookup"><span data-stu-id="a2837-155">You can monitor Setup's progress in the command prompt window.</span></span>  
  
10. <span data-ttu-id="a2837-156">Чтобы проверить установку, в папке \Program Files\SQL Server\120\Setup Bootstrap\Log откройте файл summary.txt.</span><span class="sxs-lookup"><span data-stu-id="a2837-156">To verify installation, check the summary.txt file at \Program Files\SQL Server\120\Setup Bootstrap\Log.</span></span> <span data-ttu-id="a2837-157">Если сервер был установлен без ошибок, то окончательный результат должен содержать текст «Выполнено».</span><span class="sxs-lookup"><span data-stu-id="a2837-157">Final result should say "Passed" if the server installed without errors.</span></span>  
  
11. <span data-ttu-id="a2837-158">Настройте сервер.</span><span class="sxs-lookup"><span data-stu-id="a2837-158">Configure the server.</span></span> <span data-ttu-id="a2837-159">Как минимум необходимо развернуть решения, создать приложение службы и включить этот компонент для каждого семейства веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="a2837-159">At a minimum, you must deploy solutions, create a service application, and enable the feature for each site collection.</span></span> <span data-ttu-id="a2837-160">Дополнительные сведения см. в статьях [Настройка или восстановление PowerPivot для SharePoint 2010 &#40;средства настройки powerpivot&#41;](../../../2014/analysis-services/configure-repair-powerpivot-sharepoint-2010.md) или [Администрирование сервера PowerPivot и настройка в центре администрирования](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/power-pivot-server-administration-and-configuration-in-central-administration).</span><span class="sxs-lookup"><span data-stu-id="a2837-160">For more information, see [Configure or Repair PowerPivot for SharePoint 2010 &#40;PowerPivot Configuration Tool&#41;](../../../2014/analysis-services/configure-repair-powerpivot-sharepoint-2010.md) or [PowerPivot Server Administration and Configuration in Central Administration](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/power-pivot-server-administration-and-configuration-in-central-administration).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2837-161">См. также:</span><span class="sxs-lookup"><span data-stu-id="a2837-161">See Also</span></span>  
 <span data-ttu-id="a2837-162">[Настройка учетных записей служб PowerPivot](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/configure-power-pivot-service-accounts) </span><span class="sxs-lookup"><span data-stu-id="a2837-162">[Configure PowerPivot Service Accounts](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/configure-power-pivot-service-accounts) </span></span>  
 [<span data-ttu-id="a2837-163">Установка PowerPivot для SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="a2837-163">PowerPivot for SharePoint 2010 Installation</span></span>](../../../2014/sql-server/install/powerpivot-for-sharepoint-2010-installation.md)  
