---
title: Включение или отключение сетевого протокола сервера | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- network protocols [SQL Server], disabling
- remote connections [SQL Server], enabling using Configuration Manager
- protocols [SQL Server], enabling using Configuration Manager
- protocols [SQL Server], disabling using Configuration Manager
- disabling network protocols, Configuration Manager
- network protocols [SQL Server], enabling
- enabling network protocols, Configuration Manager
- surface area configuration [SQL Server], connection protocols
- connections [SQL Server], enabling remote using Configuration Manager
ms.assetid: ec5ccb69-61c9-4576-8843-014b976fd46e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 737edae84ff284ed726ade69cb48e574b830611e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732017"
---
# <a name="enable-or-disable-a-server-network-protocol"></a><span data-ttu-id="9c4b5-102">Включение или отключение сетевого протокола сервера</span><span class="sxs-lookup"><span data-stu-id="9c4b5-102">Enable or Disable a Server Network Protocol</span></span>
  <span data-ttu-id="9c4b5-103">Все сетевые протоколы устанавливаются программой установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , но некоторые могут быть включены, а некоторые — нет.</span><span class="sxs-lookup"><span data-stu-id="9c4b5-103">All network protocols are installed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup, but may or may not be enabled.</span></span> <span data-ttu-id="9c4b5-104">В этом разделе описано, как включить или отключить сетевой протокол сервера в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью диспетчера конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9c4b5-104">This topic describes how to enable or disable a server network protocol in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager or PowerShell.</span></span> <span data-ttu-id="9c4b5-105">Компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] необходимо остановить и перезапустить, чтобы изменения вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="9c4b5-105">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] must be stopped and restarted for the change to take effect.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9c4b5-106">Во время установки [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] для группы BUILTIN\Users добавляется имя входа.</span><span class="sxs-lookup"><span data-stu-id="9c4b5-106">During setup of [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] a login is added for the BUILTIN\Users group.</span></span> <span data-ttu-id="9c4b5-107">Благодаря этому все прошедшие проверку подлинности пользователи компьютера получают доступ к экземпляру [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] как члены роли public.</span><span class="sxs-lookup"><span data-stu-id="9c4b5-107">This allows all authenticated users of the computer to access the instance of [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] as a member of the public role.</span></span> <span data-ttu-id="9c4b5-108">Имя входа группы BUILTIN\Users можно удалить, чтобы ограничить доступ к компоненту [!INCLUDE[ssDE](../../includes/ssde-md.md)] только пользователям компьютера, у которых есть отдельные имена входа, или членам других групп Windows с именами входа.</span><span class="sxs-lookup"><span data-stu-id="9c4b5-108">The BUILTIN\Users login can be safely removed to restrict [!INCLUDE[ssDE](../../includes/ssde-md.md)] access to computer users who have individual logins or are members of other Windows groups with logins.</span></span>  
  
> [!WARNING]  
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="9c4b5-109">и поставщики данных [!INCLUDE[msCoName](../../includes/msconame-md.md)] для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поддерживают протоколы TLS 1.0 и SSL 3.0.</span><span class="sxs-lookup"><span data-stu-id="9c4b5-109">and [!INCLUDE[msCoName](../../includes/msconame-md.md)] data providers for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] support TLS 1.0 and SSL 3.0.</span></span> <span data-ttu-id="9c4b5-110">Если применить другой протокол (например, TLS 1.1 или TLS 1.2), внеся изменения на уровне операционной системы SChannel, при подключении к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] может возникнуть ошибка.</span><span class="sxs-lookup"><span data-stu-id="9c4b5-110">If you enforce a different protocol (such as TLS 1.1 or TLS 1.2) by making changes in the operating system SChannel layer, your connections to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] might fail.</span></span>  
  
 <span data-ttu-id="9c4b5-111">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="9c4b5-111">**In This Topic**</span></span>  
  
-   <span data-ttu-id="9c4b5-112">**Включение или отключение сетевого протокола сервера с использованием следующего.**</span><span class="sxs-lookup"><span data-stu-id="9c4b5-112">**To enable or disable a server network protocol using:**</span></span>  
  
     [<span data-ttu-id="9c4b5-113">Диспетчер конфигурации SQL Server</span><span class="sxs-lookup"><span data-stu-id="9c4b5-113">SQL Server Configuration Manager</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="9c4b5-114">PowerShell</span><span class="sxs-lookup"><span data-stu-id="9c4b5-114">PowerShell</span></span>](#PowerShellProcedure)  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9c4b5-115">Использование диспетчера конфигурации SQL Server</span><span class="sxs-lookup"><span data-stu-id="9c4b5-115">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-enable-a-server-network-protocol"></a><span data-ttu-id="9c4b5-116">Включение протокола SNP</span><span class="sxs-lookup"><span data-stu-id="9c4b5-116">To enable a server network protocol</span></span>  
  
1.  <span data-ttu-id="9c4b5-117">В диспетчере конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на панели консоли раскройте **Сетевая конфигурация SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="9c4b5-117">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, in the console pane, expand **SQL Server  Network Configuration**.</span></span>  
  
2.  <span data-ttu-id="9c4b5-118">В области консоли щелкните **Протоколы для** *\<instance name>* .</span><span class="sxs-lookup"><span data-stu-id="9c4b5-118">In the console pane, click **Protocols for** *\<instance name>*.</span></span>  
  
3.  <span data-ttu-id="9c4b5-119">В области сведений щелкните правой кнопкой мыши протокол, который необходимо переключить, затем выберите **Включить** или **Отключить**.</span><span class="sxs-lookup"><span data-stu-id="9c4b5-119">In the details pane, right-click the protocol you want to change, and then click **Enable** or **Disable**.</span></span>  
  
4.  <span data-ttu-id="9c4b5-120">В области консоли выберите **Службы SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="9c4b5-120">In the console pane, click **SQL Server Services**.</span></span>  
  
5.  <span data-ttu-id="9c4b5-121">В области сведений щелкните правой кнопкой мыши **SQL Server ( ***\<instance name>*** )** и выберите команду **перезапустить**, чтобы прерывать и перезапускать [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] службу.</span><span class="sxs-lookup"><span data-stu-id="9c4b5-121">In the details pane, right-click **SQL Server (***\<instance name>***)**, and then click **Restart**, to stop and restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
##  <a name="using-sql-server-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="9c4b5-122">Использование SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="9c4b5-122">Using SQL Server PowerShell</span></span>  
  
#### <a name="to-enable-a-server-network-protocol-using-powershell"></a><span data-ttu-id="9c4b5-123">Включение сетевого протокола сервера с использованием PowerShell</span><span class="sxs-lookup"><span data-stu-id="9c4b5-123">To Enable a Server Network Protocol Using PowerShell</span></span>  
  
1.  <span data-ttu-id="9c4b5-124">Откройте командную строку с использованием разрешений администратора.</span><span class="sxs-lookup"><span data-stu-id="9c4b5-124">Using administrator permissions open a command prompt.</span></span>  
  
2.  <span data-ttu-id="9c4b5-125">Запустите c панели задач Windows PowerShell 2.0 или нажмите кнопку «Пуск», а затем последовательно выберите «Все программы», «Стандартные», «Windows PowerShell» и «Windows PowerShell».</span><span class="sxs-lookup"><span data-stu-id="9c4b5-125">Start Windows PowerShell 2.0 from the taskbar, or click Start, then All Programs, then Accessories, then Windows PowerShell, then Windows PowerShell.</span></span>  
  
3.  <span data-ttu-id="9c4b5-126">Импортируйте модуль **sqlps** , введя`Import-Module "sqlps"`</span><span class="sxs-lookup"><span data-stu-id="9c4b5-126">Import the **sqlps** module by entering `Import-Module "sqlps"`</span></span>  
  
4.  <span data-ttu-id="9c4b5-127">Выполните следующие инструкции, чтобы включить протокол TCP и протокол именованных каналов.</span><span class="sxs-lookup"><span data-stu-id="9c4b5-127">Execute the following statements to enable both the TCP and named pipes protocols.</span></span> <span data-ttu-id="9c4b5-128">Замените `<computer_name>` именем компьютера, на котором работает [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9c4b5-128">Replace `<computer_name>` with the name of the computer that is running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="9c4b5-129">Если настраивается именованный экземпляр, замените `MSSQLSERVER` именем экземпляра.</span><span class="sxs-lookup"><span data-stu-id="9c4b5-129">If you are configuring a named instance, replace `MSSQLSERVER` with the instance name.</span></span>  
  
     <span data-ttu-id="9c4b5-130">Чтобы отключить протоколы, установите для свойства `IsEnabled` значение `$false`.</span><span class="sxs-lookup"><span data-stu-id="9c4b5-130">To disable protocols, set the `IsEnabled` properties to `$false`.</span></span>  
  
    ```powershell
    $smo = 'Microsoft.SqlServer.Management.Smo.'  
    $wmi = new-object ($smo + 'Wmi.ManagedComputer').  
  
    # List the object properties, including the instance names.  
    $Wmi  
  
    # Enable the TCP protocol on the default instance.  
    $uri = "ManagedComputer[@Name='<computer_name>']/ ServerInstance[@Name='MSSQLSERVER']/ServerProtocol[@Name='Tcp']"  
    $Tcp = $wmi.GetSmoObject($uri)  
    $Tcp.IsEnabled = $true  
    $Tcp.Alter()  
    $Tcp  
  
    # Enable the named pipes protocol for the default instance.  
    $uri = "ManagedComputer[@Name='<computer_name>']/ ServerInstance[@Name='MSSQLSERVER']/ServerProtocol[@Name='Np']"  
    $Np = $wmi.GetSmoObject($uri)  
    $Np.IsEnabled = $true  
    $Np.Alter()  
    $Np  
    ```  
  
#### <a name="to-configure-the-protocols-for-the-local-computer"></a><span data-ttu-id="9c4b5-131">Настройка протоколов на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="9c4b5-131">To configure the protocols for the local computer</span></span>  
  
-   <span data-ttu-id="9c4b5-132">Если скрипт запускается локально и настраивает локальный компьютер, с помощью [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell можно сделать скрипт более гибким, динамически определяя имя локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="9c4b5-132">When the script is run locally and configures the local computer, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell can make the script more flexible by dynamically determining the local computer name.</span></span> <span data-ttu-id="9c4b5-133">Для получения имени локального компьютера замените строку, устанавливающую переменную `$uri` , следующей строкой.</span><span class="sxs-lookup"><span data-stu-id="9c4b5-133">To retrieve the local computer name, replace the line setting the `$uri` variable with the following line.</span></span>  
  
    ```powershell
    $uri = "ManagedComputer[@Name='" + (Get-Item env:\computername).Value + "']/ServerInstance[@Name='MSSQLSERVER']/ServerProtocol[@Name='Tcp']"  
    ```  
  
#### <a name="to-restart-the-database-engine-by-using-sql-server-powershell"></a><span data-ttu-id="9c4b5-134">Перезапуск компонента Database Engine с использованием SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="9c4b5-134">To restart the Database Engine by using SQL Server PowerShell</span></span>  
  
-   <span data-ttu-id="9c4b5-135">После включения или отключения протоколов необходимо остановить и перезапустить компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] , чтобы эти изменения вступили в действие.</span><span class="sxs-lookup"><span data-stu-id="9c4b5-135">After you enable or disable protocols, you must stop and restart the [!INCLUDE[ssDE](../../includes/ssde-md.md)] for the change to take effect.</span></span> <span data-ttu-id="9c4b5-136">Выполните следующие инструкции, чтобы остановить и запустить экземпляр по умолчанию с использованием [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9c4b5-136">Execute the following statements to stop and start the default instance by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell.</span></span> <span data-ttu-id="9c4b5-137">Чтобы остановить и запустить именованный экземпляр, замените `'MSSQLSERVER'` на `'MSSQL$<instance_name>'`.</span><span class="sxs-lookup"><span data-stu-id="9c4b5-137">To stop and start a named instance replace `'MSSQLSERVER'` with `'MSSQL$<instance_name>'`.</span></span>  
  
    ```powershell
    # Get a reference to the ManagedComputer class.  
    CD SQLSERVER:\SQL\<computer_name>  
    $Wmi = (Get-Item .).ManagedComputer  
    # Get a reference to the default instance of the Database Engine.  
    $DfltInstance = $Wmi.Services['MSSQLSERVER']  
    # Display the state of the service.  
    $DfltInstance  
    # Stop the service.  
    $DfltInstance.Stop();  
    # Wait until the service has time to stop.  
    # Refresh the cache.  
    $DfltInstance.Refresh();   
    # Display the state of the service.  
    $DfltInstance  
    # Start the service again.  
    $DfltInstance.Start();  
    # Wait until the service has time to start.  
    # Refresh the cache and display the state of the service.  
    $DfltInstance.Refresh(); $DfltInstance  
    ```  
