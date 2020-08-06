---
title: Настройка брандмауэра для доступа к серверу отчетов | Документы Майкрософт
ms.custom: ''
ms.date: 08/10/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- firewall systems [Reporting Services]
- configuring servers [Reporting Services]
ms.assetid: 04dae07a-a3a4-424c-9bcb-a8000e20dc93
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b578c980522d24f5a24a73fdfd080ec425335aac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665826"
---
# <a name="configure-a-firewall-for-report-server-access"></a><span data-ttu-id="0b7f2-102">Configure a Firewall for Report Server Access</span><span class="sxs-lookup"><span data-stu-id="0b7f2-102">Configure a Firewall for Report Server Access</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="0b7f2-103">и опубликованным отчетам производится по URL-адресам, которые состоят из IP-адреса, номера порта и имени виртуального каталога.</span><span class="sxs-lookup"><span data-stu-id="0b7f2-103">Report server applications and published reports are accessed through URLs that specify an IP address, port, and virtual directory.</span></span> <span data-ttu-id="0b7f2-104">Если включен брандмауэр Windows, то порт, на который настроен сервер отчетов, скорее всего, закрыт.</span><span class="sxs-lookup"><span data-stu-id="0b7f2-104">If Windows Firewall is turned on, the port that the report server is configured to use is most likely closed.</span></span> <span data-ttu-id="0b7f2-105">Обычно это выражается в том, что при обращении с удаленного клиентского компьютера к отчету или к диспетчеру отчетов выдается пустая страница.</span><span class="sxs-lookup"><span data-stu-id="0b7f2-105">Indications that a port might be closed are the appearance of a blank Web page after requesting a report, or a blank page when you attempt to open Report Manager from a remote client computer.</span></span>  
  
 <span data-ttu-id="0b7f2-106">Открыть порт можно при помощи брандмауэра Windows на компьютере сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="0b7f2-106">To open a port, you must use the Windows Firewall utility on the report server computer.</span></span> <span data-ttu-id="0b7f2-107">Службы Reporting Services не открывают порты автоматически, этот шаг необходимо выполнить вручную.</span><span class="sxs-lookup"><span data-stu-id="0b7f2-107">Reporting Services will not open ports for you; you must perform this step manually.</span></span>  
  
 <span data-ttu-id="0b7f2-108">По умолчанию сервер отчетов слушает HTTP-запросы для порта 80.</span><span class="sxs-lookup"><span data-stu-id="0b7f2-108">By default, the report server listens for HTTP requests on port 80.</span></span> <span data-ttu-id="0b7f2-109">Следующие пошаговые инструкции позволяют настроить порт.</span><span class="sxs-lookup"><span data-stu-id="0b7f2-109">As such, the following instructions include steps that specify that port.</span></span> <span data-ttu-id="0b7f2-110">Если URL-адреса сервера отчетов настроены на другой порт, при выполнении описанных ниже инструкций необходимо указывать его номер.</span><span class="sxs-lookup"><span data-stu-id="0b7f2-110">If you configured the report server URLs to use a different port, you must specify that port number when following the instructions below.</span></span>  
  
 <span data-ttu-id="0b7f2-111">При обращении к реляционным базам данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на внешних компьютерах или в случае, если база данных сервера отчетов находится на внешнем экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , необходимо открыть порт 1433 и 1434 на внешнем компьютере.</span><span class="sxs-lookup"><span data-stu-id="0b7f2-111">If you are accessing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] relational databases on external computers, or if the report server database is on an external [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance, you must open port 1433 and 1434 on the external computer.</span></span> <span data-ttu-id="0b7f2-112">Дополнительные сведения о брандмауэре Windows см. в статье [Настройка брандмауэра Windows для доступа к компоненту Database Engine](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) в электронной документации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0b7f2-112">For more information, see [Configure a Windows Firewall for Database Engine Access](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span> <span data-ttu-id="0b7f2-113">Дополнительные сведения о настройках брандмауэра Windows по умолчанию и описание портов TCP, влияющих на компоненты [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]и [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], см. в разделе [Настройка брандмауэра Windows для разрешения доступа к SQL Server](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md) электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0b7f2-113">For more information about the default Windows firewall settings, and a description of the TCP ports that affect the [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], and [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], see [Configure the Windows Firewall to Allow SQL Server Access](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0b7f2-114">предварительные требования</span><span class="sxs-lookup"><span data-stu-id="0b7f2-114">Prerequisites</span></span>  
 <span data-ttu-id="0b7f2-115">Выполнение следующих инструкций предполагает, что создана база данных сервера отчетов, настроена учетная запись службы и URL-адреса диспетчера отчетов и веб-службы сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="0b7f2-115">These instructions assume that you already configured the service account, created the report server database, and configured URLs for the Report Server Web service and Report Manager.</span></span> <span data-ttu-id="0b7f2-116">Дополнительные сведения см. в разделе [Управление сервером отчетов служб Reporting Services в собственном режиме](manage-a-reporting-services-native-mode-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="0b7f2-116">For more information, see [Manage a Reporting Services Native Mode Report Server](manage-a-reporting-services-native-mode-report-server.md).</span></span>  
  
 <span data-ttu-id="0b7f2-117">Кроме этого, необходимо проверить доступность экземпляра сервера отчетов из веб-браузера через локальное соединение.</span><span class="sxs-lookup"><span data-stu-id="0b7f2-117">You should also have verified that the report server is accessible over a local Web browser connection to the local report server instance.</span></span> <span data-ttu-id="0b7f2-118">Этот шаг необходим для проверки работоспособности установки.</span><span class="sxs-lookup"><span data-stu-id="0b7f2-118">This step establishes that you have a working installation.</span></span> <span data-ttu-id="0b7f2-119">Прежде чем приступать к открытию портов, необходимо проверить правильность настройки установки.</span><span class="sxs-lookup"><span data-stu-id="0b7f2-119">You should verify that the installation is configured correctly before you begin opening ports.</span></span> <span data-ttu-id="0b7f2-120">Чтобы выполнить этот шаг в Windows Server, потребуется также добавить сервер отчетов к доверенным сайтам.</span><span class="sxs-lookup"><span data-stu-id="0b7f2-120">To complete this step on  Windows Server, you must have also added the report server site to Trusted Sites.</span></span> <span data-ttu-id="0b7f2-121">Дополнительные сведения см. в разделе [Настройка сервера отчетов, работающего в основном режиме, для локального администрирования (службы SSRS)](configure-a-native-mode-report-server-for-local-administration-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0b7f2-121">For more information, see [Configure a Native Mode Report Server for Local Administration &#40;SSRS&#41;](configure-a-native-mode-report-server-for-local-administration-ssrs.md).</span></span>  
  
## <a name="opening-ports-in-windows-firewall"></a><span data-ttu-id="0b7f2-122">Открытие портов в брандмауэре Windows</span><span class="sxs-lookup"><span data-stu-id="0b7f2-122">Opening Ports in Windows Firewall</span></span>  
 <span data-ttu-id="0b7f2-123">В разных версиях брандмауэра Windows эта процедура выполняется по-разному.</span><span class="sxs-lookup"><span data-stu-id="0b7f2-123">There are separate instructions for different versions of Windows Firewall.</span></span>  
  
#### <a name="to-open-port-80-on-windows-7-windows-server-2008-r2-windows-server-2012-and-2012-r2"></a><span data-ttu-id="0b7f2-124">Открытие порта 80 в Windows 7, Windows Server 2008 R2, Windows Server 2012 и 2012 R2</span><span class="sxs-lookup"><span data-stu-id="0b7f2-124">To open port 80 on Windows 7, Windows Server 2008 R2, Windows Server 2012 and 2012 R2</span></span>  
  
1.  <span data-ttu-id="0b7f2-125">В меню **Пуск** выберите **Панель управления**, **Система и безопасность**и **Брандмауэр Windows**.</span><span class="sxs-lookup"><span data-stu-id="0b7f2-125">From the **Start** menu, click **Control Panel**, click **System and Security**, and then click **Windows Firewall**.</span></span> <span data-ttu-id="0b7f2-126">Если на панели управления не включено представление по категориям, сразу выберите **Брандмауэр Windows**.</span><span class="sxs-lookup"><span data-stu-id="0b7f2-126">Control Panel is not configured for 'Category' view, you only need to select **Windows Firewall.**</span></span>  
  
2.  <span data-ttu-id="0b7f2-127">Нажмите кнопку **Дополнительные параметры**.</span><span class="sxs-lookup"><span data-stu-id="0b7f2-127">Click **Advanced Settings**.</span></span>  
  
3.  <span data-ttu-id="0b7f2-128">Выберите **Правила для входящих подключений.**</span><span class="sxs-lookup"><span data-stu-id="0b7f2-128">Click **Inbound Rules.**</span></span>  
  
4.  <span data-ttu-id="0b7f2-129">Выберите **Создать правило** в окне **Действия\*\*\*\*.**</span><span class="sxs-lookup"><span data-stu-id="0b7f2-129">Click **New Rule** in the **Actions** window **.**</span></span>  
  
5.  <span data-ttu-id="0b7f2-130">Выберите **Тип правила** в разделе **Порт**.</span><span class="sxs-lookup"><span data-stu-id="0b7f2-130">Click **Rule Type** of **Port.**</span></span>  
  
6.  <span data-ttu-id="0b7f2-131">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0b7f2-131">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="0b7f2-132">На странице **Протокол и порты** выберите **TCP**.</span><span class="sxs-lookup"><span data-stu-id="0b7f2-132">On the **Protocol and Ports** page click **TCP**.</span></span>  
  
8.  <span data-ttu-id="0b7f2-133">Выберите **Указанные локальные порты** и введите значение **80**.</span><span class="sxs-lookup"><span data-stu-id="0b7f2-133">Select **Specific Local Ports** and type a value of **80**.</span></span>  
  
9. <span data-ttu-id="0b7f2-134">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0b7f2-134">Click **Next**.</span></span>  
  
10. <span data-ttu-id="0b7f2-135">На странице **Действие** выберите **Разрешить соединение**.</span><span class="sxs-lookup"><span data-stu-id="0b7f2-135">On the **Action** page click **Allow the connection**.</span></span>  
  
11. <span data-ttu-id="0b7f2-136">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0b7f2-136">Click **Next**.</span></span>  
  
12. <span data-ttu-id="0b7f2-137">На странице **Профиль** выберите необходимые параметры для среды.</span><span class="sxs-lookup"><span data-stu-id="0b7f2-137">On the **Profile** page click the appropriate options for your environment.</span></span>  
  
13. <span data-ttu-id="0b7f2-138">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0b7f2-138">Click **Next**.</span></span>  
  
14. <span data-ttu-id="0b7f2-139">На странице **Имя** введите имя**ReportServer (TCP через порт 80)**.</span><span class="sxs-lookup"><span data-stu-id="0b7f2-139">On the **Name** page enter a name of**ReportServer (TCP on port 80)**</span></span>  
  
15. <span data-ttu-id="0b7f2-140">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="0b7f2-140">Click **Finish**.</span></span>  
  
16. <span data-ttu-id="0b7f2-141">Перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="0b7f2-141">Restart the computer.</span></span>  
  
#### <a name="to-open-port-80-on-windows-vista-or-windows-server-2008"></a><span data-ttu-id="0b7f2-142">Открытие порта 80 в Windows Vista или Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="0b7f2-142">To open port 80 on Windows Vista or Windows Server 2008</span></span>  
  
1.  <span data-ttu-id="0b7f2-143">В меню **Пуск** выберите пункт **Панель управления**, щелкните **Безопасность**, а затем щелкните **Брандмауэр Windows**.</span><span class="sxs-lookup"><span data-stu-id="0b7f2-143">From the **Start** menu, click **Control Panel**, click **Security**, and then click **Windows Firewall**.</span></span>  
  
2.  <span data-ttu-id="0b7f2-144">Выберите элемент **Разрешение запуска программы через брандмауэр Windows**.</span><span class="sxs-lookup"><span data-stu-id="0b7f2-144">Click **Allow a program through Windows Firewall**.</span></span>  
  
3.  <span data-ttu-id="0b7f2-145">Нажмите кнопку **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="0b7f2-145">Click **Continue**.</span></span>  
  
4.  <span data-ttu-id="0b7f2-146">На вкладке Исключения нажмите кнопку **Добавить порт**.</span><span class="sxs-lookup"><span data-stu-id="0b7f2-146">On the Exceptions tab, click **Add Port**.</span></span>  
  
5.  <span data-ttu-id="0b7f2-147">В окне Имя введите **ReportServer (TCP через порт 80)**.</span><span class="sxs-lookup"><span data-stu-id="0b7f2-147">In Name, type **ReportServer (TCP on port 80)**.</span></span>  
  
6.  <span data-ttu-id="0b7f2-148">В списке номер порта введите **80**.</span><span class="sxs-lookup"><span data-stu-id="0b7f2-148">In Port number, type **80**.</span></span>  
  
7.  <span data-ttu-id="0b7f2-149">Убедитесь, что выбран параметр **TCP** .</span><span class="sxs-lookup"><span data-stu-id="0b7f2-149">Verify that **TCP** is selected.</span></span>  
  
8.  <span data-ttu-id="0b7f2-150">Щелкните **изменить область**.</span><span class="sxs-lookup"><span data-stu-id="0b7f2-150">Click **Change Scope**.</span></span>  
  
9. <span data-ttu-id="0b7f2-151">Щелкните **только мою сеть (подсеть)** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0b7f2-151">Click **My network (subnet) only**, and then click **OK**.</span></span>  
  
10. <span data-ttu-id="0b7f2-152">Чтобы закрыть диалоговое окно, нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="0b7f2-152">Click **OK** to close the dialog box.</span></span>  
  
11. <span data-ttu-id="0b7f2-153">Перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="0b7f2-153">Restart the computer.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="0b7f2-154">Next Steps</span><span class="sxs-lookup"><span data-stu-id="0b7f2-154">Next Steps</span></span>  
 <span data-ttu-id="0b7f2-155">После открытия порта, прежде чем удаленные пользователи смогут производить доступ к серверу отчетов, им необходимо предоставить доступ к корневой папке и на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="0b7f2-155">After you open the port and before you confirm whether remote users can access the report server on the port that you open, you must grant user access to the report server through role assignments on Home and at the site level.</span></span> <span data-ttu-id="0b7f2-156">Даже если порт правильно открыт, пользователи не смогут соединяться с сервером отчетов, если им не предоставлены необходимые разрешения.</span><span class="sxs-lookup"><span data-stu-id="0b7f2-156">You can open a port correctly and still have report server connections fail if users do not have sufficient permissions.</span></span> <span data-ttu-id="0b7f2-157">Дополнительные сведения см. в разделе [Предоставление пользователям доступа к серверу отчетов (диспетчер отчетов)](../security/grant-user-access-to-a-report-server.md) электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0b7f2-157">For more information, see [Grant User Access to a Report Server &#40;Report Manager&#41;](../security/grant-user-access-to-a-report-server.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="0b7f2-158">Правильность открытия порта можно также проверить, открыв диспетчер отчетов с другого компьютера.</span><span class="sxs-lookup"><span data-stu-id="0b7f2-158">You can also verify that the port is opened correctly by starting Report Manager on a different computer.</span></span> <span data-ttu-id="0b7f2-159">Дополнительные сведения см. в разделе [Диспетчер отчетов (службы SSRS в собственном режиме)](../report-manager-ssrs-native-mode.md) электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0b7f2-159">For more information, see [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b7f2-160">См. также:</span><span class="sxs-lookup"><span data-stu-id="0b7f2-160">See Also</span></span>  
 <span data-ttu-id="0b7f2-161">[Настройка учетной записи службы сервера отчетов (диспетчер конфигурации служб SSRS)](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="0b7f2-161">[Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="0b7f2-162">[Настройка URL-адресов сервера отчетов (диспетчер конфигурации служб SSRS)](../install-windows/configure-report-server-urls-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="0b7f2-162">[Configure Report Server URLs  &#40;SSRS Configuration Manager&#41;](../install-windows/configure-report-server-urls-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="0b7f2-163">[Создание базы данных сервера отчетов &#40;службы SSRS Configuration Manager&#41;](../../sql-server/install/create-a-report-server-database-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="0b7f2-163">[Create a Report Server Database  &#40;SSRS Configuration Manager&#41;](../../sql-server/install/create-a-report-server-database-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="0b7f2-164">[Настройка учетной записи службы сервера отчетов (диспетчер конфигурации служб SSRS)](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="0b7f2-164">[Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span></span>  
 [<span data-ttu-id="0b7f2-165">Управление сервером отчетов Reporting Services в собственном режиме</span><span class="sxs-lookup"><span data-stu-id="0b7f2-165">Manage a Reporting Services Native Mode Report Server</span></span>](manage-a-reporting-services-native-mode-report-server.md)  
  
  
