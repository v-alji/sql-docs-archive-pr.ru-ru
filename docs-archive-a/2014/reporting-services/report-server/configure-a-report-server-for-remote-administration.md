---
title: Настройка сервера отчетов для удаленного администрирования | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services Configuration tool
- WMI provider [Reporting Services], remote configuration
- configuration management [WMI]
- report servers [Reporting Services], configuring
- remote server administration [Reporting Services]
ms.assetid: 8c7f145f-3ac2-4203-8cd6-2a4694395d09
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2c34db5299fc1b82a7896a41519e55466c3b3b79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665822"
---
# <a name="configure-a-report-server-for-remote-administration"></a><span data-ttu-id="d3ad6-102">настроить сервер отчетов для удаленного администрирования</span><span class="sxs-lookup"><span data-stu-id="d3ad6-102">Configure a Report Server for Remote Administration</span></span>
  <span data-ttu-id="d3ad6-103">В службах [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]экземпляры сервера отчетов можно настраивать локально или удаленно.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-103">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can configure report server instances locally or remotely.</span></span> <span data-ttu-id="d3ad6-104">Чтобы настроить удаленный экземпляр сервера отчетов, можно использовать программу настройки служб Reporting Services. Также можно написать пользовательский код, который будет использовать поставщик инструментария управления Windows (WMI) служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d3ad6-104">To configure a remote report server instance, you can use the Reporting Services Configuration tool or write custom code that uses the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Windows Management Instrumentation (WMI) provider.</span></span> <span data-ttu-id="d3ad6-105">Программа настройки служб Reporting Services предоставляет графический интерфейс поставщика WMI, поэтому такая настройка сервера отчетов не требует написания кода.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-105">The Reporting Services Configuration tool provides a graphical interface to the WMI provider so that you can configure a report server without having to write code.</span></span> <span data-ttu-id="d3ad6-106">При запуске программы можно указать, к какому удаленному серверу необходимо подключаться.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-106">When you start the tool, you can specify a remote server to connect to.</span></span>  
  
 <span data-ttu-id="d3ad6-107">Перед использованием программы для настройки удаленного экземпляра сервера отчетов необходимо выполнить инструкции этого раздела и включить порты в брандмауэре Windows, удаленные соединения и удаленные запросы инструментария WMI.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-107">Before you can use the tool to configure a remote report server, you must follow the instructions in this topic to enable ports in Windows Firewall, enable remote connections, and enable remote WMI requests.</span></span>  
  
 <span data-ttu-id="d3ad6-108">Правильная настройка поможет избежать следующих ошибок:</span><span class="sxs-lookup"><span data-stu-id="d3ad6-108">Proper configuration helps you avoid the following error:</span></span>  
  
 `The machine could not be found.`  
  
 `"The RPC server is unavailable. (Exception from HRESULT: 0x800706BA)".`  
  
## <a name="prerequisites"></a><span data-ttu-id="d3ad6-109">предварительные требования</span><span class="sxs-lookup"><span data-stu-id="d3ad6-109">Prerequisites</span></span>  
 <span data-ttu-id="d3ad6-110">Чтобы изменить настройки брандмауэра, нужно войти в систему локально и быть членом локальной группы «Администраторы».</span><span class="sxs-lookup"><span data-stu-id="d3ad6-110">To modify firewall settings, you must be logged on locally and you must be a member of the local Administrators group.</span></span> <span data-ttu-id="d3ad6-111">Через удаленное соединение невозможно изменить настройки брандмауэра Windows на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-111">You cannot modify the Windows firewall settings of a remote computer over a remote connection.</span></span>  
  
 <span data-ttu-id="d3ad6-112">Чтобы включить возможности удаленного администрирования для пользователя, не обладающего правами администратора, учетной записи необходимо предоставить права удаленной активации с помощью распределенной модели объектов (DCOM).</span><span class="sxs-lookup"><span data-stu-id="d3ad6-112">If you want to enable remote administration for a non-administrator user, you must grant the account Distributed Component Object Model (DCOM) Remote Activation permissions.</span></span> <span data-ttu-id="d3ad6-113">В этом разделе предоставлены инструкции по настройке сервера для доступа пользователя, не обладающего правами администратора.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-113">Instructions for configuring the server for non-administrator access are provided in this topic.</span></span>  
  
 <span data-ttu-id="d3ad6-114">В некоторых организациях настроены групповые политики, которые предотвращают доступ к администрированию удаленного сервера для определенных операционных систем или пользователей.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-114">Some organizations have group policies that prevent remote server administration for certain operating systems or users.</span></span> <span data-ttu-id="d3ad6-115">Прежде чем приступить к изменению настроек брандмауэра, выполните проверку вместе с администратором сети на наличие ограничений для удаленного администрирования.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-115">Before you begin modifying firewall settings, check with your network administrator to verify whether there are restrictions on remote administration.</span></span>  
  
 <span data-ttu-id="d3ad6-116">Дополнительные сведения см. в разделе [Подключение через брандмауэр Windows](https://go.microsoft.com/fwlink/?LinkId=63615) документации пакета Platform SDK в MSDN.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-116">For more information, see [Connecting Through Windows Firewall](https://go.microsoft.com/fwlink/?LinkId=63615) in the Platform SDK documentation on MSDN.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="d3ad6-117">Задания</span><span class="sxs-lookup"><span data-stu-id="d3ad6-117">Tasks</span></span>  
 <span data-ttu-id="d3ad6-118">Для включения возможности удаленной настройки выполняются следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-118">Tasks that enable remote report server configuration include the following:</span></span>  
  
-   <span data-ttu-id="d3ad6-119">Включение портов в брандмауэре Windows и разрешение запросов на портах, используемых сервером отчетов и экземпляром компонента SQL Server Database Engine.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-119">Enable ports in Windows Firewall to allow requests on ports used by the report server and by the SQL Server Database Engine instance.</span></span>  
  
-   <span data-ttu-id="d3ad6-120">Включение удаленных соединений с экземпляром компонента Database Engine, хранящего базу данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-120">Enable remote connections to the instance of the Database Engine instance that hosts the report server database.</span></span> <span data-ttu-id="d3ad6-121">Удаленное соединение необходимо для настройки подключения к базе данных сервера отчетов и управления ключами шифрования.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-121">A remote connection is necessary for configuring the report server database connection and managing the encryption keys.</span></span>  
  
-   <span data-ttu-id="d3ad6-122">Включение удаленных запросов инструментария WMI для передачи через брандмауэр [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-122">Enable remote WMI requests to pass through the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows firewall.</span></span>  
  
-   <span data-ttu-id="d3ad6-123">При настройке удаленного сервера отчетов для администрирования пользователями, не являющимися администраторами, необходимо установить разрешения DCOM, чтобы включить удаленный доступ инструментария WMI для стандартной учетной записи пользователя Windows.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-123">If you are configuring a remote report server for administration by a non-administrative user, you must set DCOM permissions to enable remote WMI access to a standard Windows user account.</span></span> <span data-ttu-id="d3ad6-124">Поскольку инструментарий WMI использует DCOM в качестве транспорта для удаленных вызовов, можно настроить разрешения DCOM таким образом, чтобы пользователи, не вошедшие в систему под учетной записью локального администратора, могли настраивать сервер.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-124">Because WMI uses DCOM as transport for remote calls, you must set the DCOM permissions so that users who are not logged on as the local administrator can configure the server.</span></span>  
  
-   <span data-ttu-id="d3ad6-125">При настройке удаленного сервера отчетов для администрирования пользователями, не являющимися администраторами, необходимо также установить разрешения инструментария WMI в пространстве имен WMI сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-125">If you are configuring a remote report server for administration by a non-administrative user, you must also set WMI permissions on the report server WMI namespace.</span></span> <span data-ttu-id="d3ad6-126">По умолчанию все члены локальной группы «Администраторы» имеют доступ к пространству имен WMI сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-126">By default, all members of the local Administrator group have access to the report server WMI namespace.</span></span> <span data-ttu-id="d3ad6-127">При необходимости предоставить доступ для пользователей, не обладающих правами администратора, нужно установить соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-127">If you want to grant access to non-administrators, you must set permissions.</span></span>  
  
 <span data-ttu-id="d3ad6-128">В данном разделе приведены инструкции по выполнению этих задач.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-128">Instructions on how to perform these tasks are provided in this topic.</span></span>  
  
### <a name="to-open-ports-in-windows-firewall"></a><span data-ttu-id="d3ad6-129">Открытие порта в брандмауэре Windows</span><span class="sxs-lookup"><span data-stu-id="d3ad6-129">To open ports in Windows Firewall</span></span>  
  
1.  <span data-ttu-id="d3ad6-130">[Настройте брандмауэр Windows для доступа к ядро СУБД](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md).</span><span class="sxs-lookup"><span data-stu-id="d3ad6-130">[Configure a Windows Firewall for Database Engine Access](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md).</span></span>  
  
2.  <span data-ttu-id="d3ad6-131">[Настройка брандмауэра для доступа к серверу отчетов](configure-a-firewall-for-report-server-access.md).</span><span class="sxs-lookup"><span data-stu-id="d3ad6-131">[Configure a Firewall for Report Server Access](configure-a-firewall-for-report-server-access.md).</span></span>  
  
### <a name="to-configure-remote-connections-to-the-report-server-database"></a><span data-ttu-id="d3ad6-132">Настройка удаленных соединений с базой данных сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="d3ad6-132">To configure remote connections to the report server database</span></span>  
  
1.  <span data-ttu-id="d3ad6-133">Нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы**, [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], **Средства настройки**и выберите пункт **Диспетчер конфигурации SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-133">Click **Start**, point to **Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="d3ad6-134">В левой панели разверните раздел **Сетевая конфигурация SQL Server**, затем щелкните **Протоколы** для экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d3ad6-134">In the left pane, expand **SQL Server Network Configuration**, and then click **Protocols** for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
3.  <span data-ttu-id="d3ad6-135">В панели сведений включите протокол TCP/IP и протокол именованных каналов, а затем перезапустите службу [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d3ad6-135">In the details pane, enable the TCP/IP and Named Pipes protocols, and then restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
### <a name="to-enable-remote-administration-in-windows-firewall"></a><span data-ttu-id="d3ad6-136">Активация удаленного администрирования в брандмауэре Windows</span><span class="sxs-lookup"><span data-stu-id="d3ad6-136">To enable remote administration in Windows Firewall</span></span>  
  
1.  <span data-ttu-id="d3ad6-137">Под учетной записью локального администратора войдите в систему компьютера, на котором нужно включить удаленное администрирование.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-137">Log on as a local administrator to the computer for which you want to enable remote administration.</span></span>  
  
2.  <span data-ttu-id="d3ad6-138">Если сервер отчетов запущен в Windows Vista, щелкните правой кнопкой мыши пункт **Командная строка** и выберите **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-138">If the report server is running on Windows Vista, right-click **Command Prompt** and select **Run as administrator**.</span></span> <span data-ttu-id="d3ad6-139">В других операционных системах откройте окно командной строки.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-139">For other operating systems, open a command prompt window.</span></span>  
  
3.  <span data-ttu-id="d3ad6-140">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d3ad6-140">Run the following command:</span></span>  
  
    ```  
    netsh.exe firewall set service type=REMOTEADMIN mode=ENABLE scope=ALL  
    ```  
  
     <span data-ttu-id="d3ad6-141">Для параметра «Scope» можно указать другие значения.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-141">You can specify different options for Scope.</span></span> <span data-ttu-id="d3ad6-142">Дополнительные сведения см. в документации по продукту «Брандмауэр Windows».</span><span class="sxs-lookup"><span data-stu-id="d3ad6-142">For more information, see the Windows Firewall product documentation.</span></span>  
  
4.  <span data-ttu-id="d3ad6-143">Убедитесь, что удаленное администрирование включено.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-143">Verify that remote administration is enabled.</span></span> <span data-ttu-id="d3ad6-144">Для этого можно выполнить следующую команду, отображающую состояние:</span><span class="sxs-lookup"><span data-stu-id="d3ad6-144">You can run the following command to show the status:</span></span>  
  
    ```  
    netsh.exe firewall show state  
    ```  
  
5.  <span data-ttu-id="d3ad6-145">Перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-145">Reboot the computer.</span></span>  
  
### <a name="to-set-dcom-permissions-to-enable-remote-wmi-access-for-non-administrators"></a><span data-ttu-id="d3ad6-146">Настройка разрешений DCOM для активации удаленного доступа к инструментарию WMI для пользователей, не обладающих правами администратора</span><span class="sxs-lookup"><span data-stu-id="d3ad6-146">To set DCOM permissions to enable remote WMI access for non-administrators</span></span>  
  
1.  <span data-ttu-id="d3ad6-147">В меню «Пуск» выберите пункт **Администрирование**и затем пункт **Службы компонентов**.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-147">On the Start menu, point to **Administrative Tools**, click **Component Services**.</span></span>  
  
     <span data-ttu-id="d3ad6-148">Для Windows Vista в меню Пуск последовательно выберите пункты **все программы**, **выполнить**и введите `mmc comexp.msc` .</span><span class="sxs-lookup"><span data-stu-id="d3ad6-148">For Windows Vista, on the Start menu, click **All Programs**, click **Run**, and then enter `mmc comexp.msc`.</span></span>  
  
2.  <span data-ttu-id="d3ad6-149">Откройте папку «Службы компонентов».</span><span class="sxs-lookup"><span data-stu-id="d3ad6-149">Open the Component Services folder.</span></span>  
  
3.  <span data-ttu-id="d3ad6-150">Откройте папку «Компьютеры».</span><span class="sxs-lookup"><span data-stu-id="d3ad6-150">Open the Computers folder.</span></span>  
  
4.  <span data-ttu-id="d3ad6-151">Выберите «Мой компьютер».</span><span class="sxs-lookup"><span data-stu-id="d3ad6-151">Select My Computer.</span></span>  
  
5.  <span data-ttu-id="d3ad6-152">В меню **Действие** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-152">On the **Action** menu, and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="d3ad6-153">Щелкните **Безопасность COM**.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-153">Click **COM Security**.</span></span>  
  
7.  <span data-ttu-id="d3ad6-154">В **Разрешениях на запуск и активацию**нажмите кнопку **Редактировать ограничения**.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-154">In **Launch and Activation Permissions**, click **Edit Limits**.</span></span>  
  
8.  <span data-ttu-id="d3ad6-155">Если имя пользователя не отображается в **Разрешениях на запуск**нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-155">If you do not see your name in **Launch Permission**, click **Add**.</span></span>  
  
9. <span data-ttu-id="d3ad6-156">Введите имя учетной записи пользователя и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-156">Type the name of your user account, and then click **OK**.</span></span>  
  
10. <span data-ttu-id="d3ad6-157">В поле \*\*разрешения \<User or Group> для \*\*в столбце **Разрешить** выберите **Удаленный запуск** и **Удаленная активация**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-157">In **Permissions for \<User or Group>**, in the **Allow** column, select **Remote Launch** and **Remote Activation**, and then click **OK**.</span></span>  
  
### <a name="to-set-permissions-on-the-report-server-wmi-namespace-for-non-administrators"></a><span data-ttu-id="d3ad6-158">Настройка разрешений пространства имен WMI сервера отчетов для пользователей, не обладающих правами администратора</span><span class="sxs-lookup"><span data-stu-id="d3ad6-158">To set permissions on the report server WMI namespace for non-administrators</span></span>  
  
1.  <span data-ttu-id="d3ad6-159">В меню «Пуск» выберите пункт **Администрирование**и затем пункт **Управление компьютером**.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-159">On the Start menu, point to **Administrative Tools**, click **Computer Management**.</span></span>  
  
2.  <span data-ttu-id="d3ad6-160">Откройте папку «Службы и приложения».</span><span class="sxs-lookup"><span data-stu-id="d3ad6-160">Open the Services and Applications folder.</span></span>  
  
3.  <span data-ttu-id="d3ad6-161">Щелкните правой кнопкой мыши узел **Элемент управления WMI**и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-161">Right-click **WMI Control**, and select **Properties**.</span></span>  
  
4.  <span data-ttu-id="d3ad6-162">Перейдите на вкладку **Безопасность**.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-162">Click **Security**.</span></span>  
  
5.  <span data-ttu-id="d3ad6-163">Откройте папку «Root».</span><span class="sxs-lookup"><span data-stu-id="d3ad6-163">Open the Root folder.</span></span>  
  
6.  <span data-ttu-id="d3ad6-164">Откройте папку «Microsoft».</span><span class="sxs-lookup"><span data-stu-id="d3ad6-164">Open the Microsoft folder.</span></span>  
  
7.  <span data-ttu-id="d3ad6-165">Откройте папку «SQLServer».</span><span class="sxs-lookup"><span data-stu-id="d3ad6-165">Open the SQLServer folder.</span></span>  
  
8.  <span data-ttu-id="d3ad6-166">Откройте папку «ReportServer».</span><span class="sxs-lookup"><span data-stu-id="d3ad6-166">Open the ReportServer folder.</span></span>  
  
9. <span data-ttu-id="d3ad6-167">Откройте папку экземпляра.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-167">Open instance folder.</span></span> <span data-ttu-id="d3ad6-168">Если установлен экземпляр по умолчанию, папка установки — MSSQLSERVER.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-168">If you installed the default instance, the folder is MSSQLSERVER.</span></span>  
  
10. <span data-ttu-id="d3ad6-169">Откройте папку «v10».</span><span class="sxs-lookup"><span data-stu-id="d3ad6-169">Open the v10 folder.</span></span>  
  
11. <span data-ttu-id="d3ad6-170">Выберите папку «Admin» и затем нажмите кнопку **Безопасность**.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-170">Select the Admin folder, and then click **Security**.</span></span>  
  
12. <span data-ttu-id="d3ad6-171">Нажмите кнопку **Добавить**и введите учетную запись пользователя, которая будет использоваться для управления сервером.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-171">Click **Add**, and then type the user account you will use to manage the server.</span></span>  
  
13. <span data-ttu-id="d3ad6-172">В столбце **Разрешить** установите флажки **Включить учетную запись**, **Включить удаленно**и **Прочесть безопасность**, затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-172">In the **Allow** column, select **Enable Account**, **Remote Enable**, and **Read Security**, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3ad6-173">См. также:</span><span class="sxs-lookup"><span data-stu-id="d3ad6-173">See Also</span></span>  
 [<span data-ttu-id="d3ad6-174">Использование диспетчера конфигурации служб Reporting Services (собственный режим)</span><span class="sxs-lookup"><span data-stu-id="d3ad6-174">Reporting Services Configuration Manager &#40;Native Mode&#41;</span></span>](../../sql-server/install/reporting-services-configuration-manager-native-mode.md)  
  
  
