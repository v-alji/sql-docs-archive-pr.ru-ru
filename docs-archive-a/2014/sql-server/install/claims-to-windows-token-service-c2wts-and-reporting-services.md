---
title: Служба Claims to Windows Token Service (C2WTS) и Reporting Services | Документация Майкрософт
ms.custom: ''
ms.date: 03/25/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- c2wts.exe.config
- SharePoint mode
- C2WTS
- WSS_WPG
ms.assetid: 4d380509-deed-4b4b-a9c1-a9134cc40641
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: cf2e245dfae17556bdb906c134ba0d53898a8631
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659223"
---
# <a name="claims-to-windows-token-service-c2wts-and-reporting-services"></a><span data-ttu-id="9fd3a-102">Служба Claims to Windows Token Service (C2WTS) и службы Reporting Services</span><span class="sxs-lookup"><span data-stu-id="9fd3a-102">Claims to Windows Token Service (C2WTS) and Reporting Services</span></span>
  <span data-ttu-id="9fd3a-103">Служба SharePoint Claims to Windows Token Service (c2WTS) необходима в [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] режиме интеграции с SharePoint, если требуется использовать проверку подлинности Windows для источников данных, находящихся за пределами фермы SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9fd3a-103">The SharePoint Claims to Windows Token Service (c2WTS) is required with [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode if you want to use windows authentication for Data Sources that are outside the SharePoint farm.</span></span> <span data-ttu-id="9fd3a-104">Это верно, даже если пользователь получает доступ к источникам данных с использованием проверки подлинности Windows, поскольку для связи между клиентским веб-интерфейсом и общей службой [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] всегда используется проверка подлинности Claims.</span><span class="sxs-lookup"><span data-stu-id="9fd3a-104">This is true even if the user accesses the data sources with Windows Authentication because the communication between the web front-end (WFE) and the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] shared service will always be Claims authentication.</span></span>  
  
 <span data-ttu-id="9fd3a-105">Служба c2WTS необходима, даже если источники данных находятся на одном компьютере с общей службой.</span><span class="sxs-lookup"><span data-stu-id="9fd3a-105">c2WTS is needed even if your data source(s) are on the same computer as the shared service.</span></span> <span data-ttu-id="9fd3a-106">Однако в этом случае ограниченное делегирование не требуется.</span><span class="sxs-lookup"><span data-stu-id="9fd3a-106">However in this scenario, constrained delegation is not needed.</span></span>  
  
 <span data-ttu-id="9fd3a-107">Токены, созданные службой c2WTS, работают только при наличии ограниченного делегирования (ограничение набором определенных служб) и заданном параметре "Использовать любой протокол проверки подлинности".</span><span class="sxs-lookup"><span data-stu-id="9fd3a-107">The tokens created by c2WTS will only work with constrained delegation (constrains to specific services) and the configuration option "using any authentication protocol".</span></span> <span data-ttu-id="9fd3a-108">Как уже отмечалось, если источники данных находятся на одном компьютере с общей службой, ограниченное делегирование не требуется.</span><span class="sxs-lookup"><span data-stu-id="9fd3a-108">As noted earlier, if your data sources are on the same computer as the shared service, then constrained delegation is not needed.</span></span>  
  
 <span data-ttu-id="9fd3a-109">Если в среде используется делегирование, ограниченное Kerberos, то внешние источники данных и служба SharePoint Server должны находиться в одном домене Windows.</span><span class="sxs-lookup"><span data-stu-id="9fd3a-109">If your environment will use Kerberos constrained delegation, then the SharePoint Server service and external data sources need to reside in the same Windows domain.</span></span> <span data-ttu-id="9fd3a-110">Любая служба, использующая службу токенов Claims to Windows Service (c2WTS), должна применять делегирование, **ограниченное** Kerberos, чтобы разрешить c2WTS использовать передачу протокола Kerberos для перевода утверждений в учетные данные Windows.</span><span class="sxs-lookup"><span data-stu-id="9fd3a-110">Any service that relies on the Claims to Windows token service (c2WTS) must use Kerberos **constrained** delegation to allow c2WTS to use Kerberos protocol transition to translate claims into Windows credentials.</span></span> <span data-ttu-id="9fd3a-111">Эти требования являются достоверными для всех общих служб SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9fd3a-111">These requirements are true for all SharePoint Shared Services.</span></span> <span data-ttu-id="9fd3a-112">Дополнительные сведения см. в [статье Обзор проверки подлинности Kerberos для продуктов Microsoft https://technet.microsoft.com/library/gg502594.aspx) SharePoint 2010 (](https://technet.microsoft.com/library/gg502594.aspx).</span><span class="sxs-lookup"><span data-stu-id="9fd3a-112">For more information, see [Overview of Kerberos authentication for Microsoft SharePoint 2010 Products  (https://technet.microsoft.com/library/gg502594.aspx)](https://technet.microsoft.com/library/gg502594.aspx).</span></span>  
  
 <span data-ttu-id="9fd3a-113">Эта процедура описана в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="9fd3a-113">The procedure is summarized in this topic.</span></span>  
  
||  
|-|  
|<span data-ttu-id="9fd3a-114">**[!INCLUDE[applies](../../includes/applies-md.md)]** SharePoint 2013 &#124; SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="9fd3a-114">**[!INCLUDE[applies](../../includes/applies-md.md)]**  SharePoint 2013 &#124; SharePoint 2010</span></span>|  
  
## <a name="prerequisites"></a><span data-ttu-id="9fd3a-115">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="9fd3a-115">Prerequisites</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9fd3a-116">Примечание. Некоторые шаги настройки могут отличаться или могут не работать в определенных топологиях фермы.</span><span class="sxs-lookup"><span data-stu-id="9fd3a-116">Note: Some of the configuration steps may change, or may not work in certain farm topologies.</span></span> <span data-ttu-id="9fd3a-117">Например, установка одиночного сервера не поддерживает службы c2WTS Windows Identity Foundation, поэтому в этой конфигурации фермы требования сценариев делегирования токенов Windows невозможны.</span><span class="sxs-lookup"><span data-stu-id="9fd3a-117">For instance, a single server install does not support the Windows Identity Foundation c2WTS services so claims to windows token delegation scenarios are not possible with this farm configuration.</span></span>  
  
### <a name="basic-steps-needed-to-configure-c2wts"></a><span data-ttu-id="9fd3a-118">Основные шаги для настройки службы c2WTS</span><span class="sxs-lookup"><span data-stu-id="9fd3a-118">Basic steps needed to configure c2WTS</span></span>  
  
1.  <span data-ttu-id="9fd3a-119">Настройка учетной записи службы c2WTS.</span><span class="sxs-lookup"><span data-stu-id="9fd3a-119">Configure the c2WTS service account.</span></span> <span data-ttu-id="9fd3a-120">Добавьте учетную запись службы к группе локальных администраторов на каждом сервере приложений с c2WTS.</span><span class="sxs-lookup"><span data-stu-id="9fd3a-120">Add the service account to the local Administrators group on each application server running c2WTS.</span></span> <span data-ttu-id="9fd3a-121">Кроме того, убедитесь, что учетная запись имеет следующие права локальной политики безопасности:</span><span class="sxs-lookup"><span data-stu-id="9fd3a-121">In addition, verify that the account has the following local security policy rights:</span></span>  
  
    -   <span data-ttu-id="9fd3a-122">работа в качества части операционной системы;</span><span class="sxs-lookup"><span data-stu-id="9fd3a-122">Act as part of the operating system</span></span>  
  
    -   <span data-ttu-id="9fd3a-123">олицетворение клиента после проверки подлинности;</span><span class="sxs-lookup"><span data-stu-id="9fd3a-123">Impersonate a client after authentication</span></span>  
  
    -   <span data-ttu-id="9fd3a-124">Вход в систему в качестве службы.</span><span class="sxs-lookup"><span data-stu-id="9fd3a-124">Log on as a service</span></span>  
  
     <span data-ttu-id="9fd3a-125">Учетная запись, используемая для c2WTS, также должна быть настроена для ограниченного делегирования с переходом по протоколу и требует разрешений для делегирования службам, с которыми он должен взаимодействовать (т. е. SQL Server подсистеме SQL Server Analysis Services). Для настройки делегирования можно использовать оснастку Active Directory пользователи и компьютеры.</span><span class="sxs-lookup"><span data-stu-id="9fd3a-125">The account you use for c2WTS also needs to be configured for Constrained Delegation with Protocol Transitioning and needs permissions to delegate to the Services it is required to communicate with (i.e. SQL Server Engine, SQL Server Analysis Services).To configure delegation you can use the Active Directory Users and Computer snap-in.</span></span>  
  
    1.  <span data-ttu-id="9fd3a-126">Щелкните правой кнопкой мыши каждую учетную запись службы и откройте диалоговое окно свойств.</span><span class="sxs-lookup"><span data-stu-id="9fd3a-126">Right-click each service account and open the properties dialog.</span></span> <span data-ttu-id="9fd3a-127">В диалоговом окне перейдите на вкладку **Делегирование** .</span><span class="sxs-lookup"><span data-stu-id="9fd3a-127">In the dialog click the **Delegation** tab.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="9fd3a-128">Примечание. Вкладка делегирования отображается, только если объекту назначено имя участника-службы.</span><span class="sxs-lookup"><span data-stu-id="9fd3a-128">Note: the delegation tab is only visible if the object has an SPN assigned to it.</span></span> <span data-ttu-id="9fd3a-129">c2WTS не требует наличия имени субъекта-службы в учетной записи c2WTS, но без имени субъекта-службы, вкладка **делегирования** не будет отображаться.</span><span class="sxs-lookup"><span data-stu-id="9fd3a-129">c2WTS does not require an SPN on the c2WTS Account, however, without an SPN, the **Delegation** tab will not be visible.</span></span> <span data-ttu-id="9fd3a-130">Другой способ настройки ограниченного делегирования заключается в использовании специальной программы, например **ADSIEdit**.</span><span class="sxs-lookup"><span data-stu-id="9fd3a-130">An alternative way to configure constrained delegation is to use a utility such as **ADSIEdit**.</span></span>  
  
    2.  <span data-ttu-id="9fd3a-131">Основными параметрами, приведенными на вкладке делегирования, являются следующие:</span><span class="sxs-lookup"><span data-stu-id="9fd3a-131">Key configuration options on the delegation tab are the following:</span></span>  
  
        -   <span data-ttu-id="9fd3a-132">Установите флажок "доверять этому пользователю делегирование только указанных служб".</span><span class="sxs-lookup"><span data-stu-id="9fd3a-132">Select "Trust this user for delegation to specified services only"</span></span>  
  
        -   <span data-ttu-id="9fd3a-133">Выберите "использовать любой протокол проверки подлинности".</span><span class="sxs-lookup"><span data-stu-id="9fd3a-133">Select "Use any authentication protocol"</span></span>  
  
         <span data-ttu-id="9fd3a-134">Дополнительные сведения см. в разделе "Настройка ограниченного делегирования Kerberos для компьютеров и учетных записей служб" в следующем техническом документе [Настройка проверки подлинности Kerberos для продуктов SharePoint 2010 и SQL Server 2008 R2](https://docs.microsoft.com/archive/blogs/tothesharepoint/white-paper-configuring-kerberos-authentication-for-sharepoint-2010-and-sql-server-2008-r2-products)</span><span class="sxs-lookup"><span data-stu-id="9fd3a-134">For more information, see the "configure Kerberos constrained delegation for computers and service accounts" section of the following white paper, [Configuring Kerberos authentication for SharePoint 2010 and SQL Server 2008 R2 products](https://docs.microsoft.com/archive/blogs/tothesharepoint/white-paper-configuring-kerberos-authentication-for-sharepoint-2010-and-sql-server-2008-r2-products)</span></span>  
  
2.  <span data-ttu-id="9fd3a-135">Настройка c2WTS "AllowedCallers"</span><span class="sxs-lookup"><span data-stu-id="9fd3a-135">Configure c2WTS 'AllowedCallers'</span></span>  
  
     <span data-ttu-id="9fd3a-136">c2WTS требует явного перечисления удостоверений "Calls" в файле конфигурации **c2wtshost.exe.config**. c2WTS не принимает запросы от всех пользователей, прошедших проверку подлинности в системе, если это не настроено.</span><span class="sxs-lookup"><span data-stu-id="9fd3a-136">c2WTS requires the 'callers' identities explicitly listed in the configuration file, **c2wtshost.exe.config**. c2WTS does not accept requests from all authenticated users in the system unless it is configured to do so.</span></span> <span data-ttu-id="9fd3a-137">В этом случае вызывающим является группа Windows WSS_WPG.</span><span class="sxs-lookup"><span data-stu-id="9fd3a-137">In this case the 'caller' is the WSS_WPG Windows group.</span></span> <span data-ttu-id="9fd3a-138">Файл c2wtshost.exe.confi хранится в следующем расположении:</span><span class="sxs-lookup"><span data-stu-id="9fd3a-138">The c2wtshost.exe.confi file is saved in the following location:</span></span>  
  
     <span data-ttu-id="9fd3a-139">**\Program Files\Windows Identity Foundation\v3.5\c2wtshost.exe.config**</span><span class="sxs-lookup"><span data-stu-id="9fd3a-139">**\Program Files\Windows Identity Foundation\v3.5\c2wtshost.exe.config**</span></span>  
  
     <span data-ttu-id="9fd3a-140">В следующем примере показан файл конфигурации:</span><span class="sxs-lookup"><span data-stu-id="9fd3a-140">The following is an example of the configuration file:</span></span>  
  
    ```  
    <configuration>  
      <windowsTokenService>  
        <!--  
            By default no callers are allowed to use the Windows Identity Foundation Claims To NT Token Service.  
            Add the identities you wish to allow below.  
          -->  
        <allowedCallers>  
          <clear/>  
          <add value="WSS_WPG" />  
        </allowedCallers>  
      </windowsTokenService>  
    </configuration>  
    ```  
  
3.  <span data-ttu-id="9fd3a-141">Запустите службу c2WTS операционной системы:</span><span class="sxs-lookup"><span data-stu-id="9fd3a-141">Start the operating system c2WTS service:</span></span>  
  
    1.  <span data-ttu-id="9fd3a-142">Задайте использование службой учетной записи, настроенной в предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="9fd3a-142">Configure the service to use the service account you configured in the previous step.</span></span>  
  
    2.  <span data-ttu-id="9fd3a-143">Измените тип запуска на "**автоматически**" и запустите службу.</span><span class="sxs-lookup"><span data-stu-id="9fd3a-143">Change the Startup type to "**Automatic**" and start the service.</span></span>  
  
4.  <span data-ttu-id="9fd3a-144">Запустите SharePoint "Claims to Windows Token Service": запустите службу Claims to Windows Token Service через центр администрирования SharePoint на странице **Управление службами на сервере** .</span><span class="sxs-lookup"><span data-stu-id="9fd3a-144">Start the SharePoint 'Claims to Windows Token Service': Start the Claims to Windows Token Service through SharePoint Central Administration on the **Manage Services on Server** page.</span></span> <span data-ttu-id="9fd3a-145">Служба должна быть запущена на сервере, который будет выполнять действие.</span><span class="sxs-lookup"><span data-stu-id="9fd3a-145">The service should be started on the server that will be performing the action.</span></span> <span data-ttu-id="9fd3a-146">Например, при наличии сервера, который является интерфейсным веб-сервером, и другого сервера, который служит сервером приложений, где работает общая служба служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , службу c2WTS необходимо запустить только на сервере приложений.</span><span class="sxs-lookup"><span data-stu-id="9fd3a-146">For example if you have a server that is a WFE and another server that is an Application Server that has the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] shared service running, you only need to start c2WTS on the Application Server.</span></span> <span data-ttu-id="9fd3a-147">Служба c2WTS не требуется на интерфейсном веб-сервере.</span><span class="sxs-lookup"><span data-stu-id="9fd3a-147">c2WTS is not needed on the WFE.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fd3a-148">См. также:</span><span class="sxs-lookup"><span data-stu-id="9fd3a-148">See Also</span></span>  
 <span data-ttu-id="9fd3a-149">[Обзор службы Claims to Windows Token Service (c2WTS) (https://msdn.microsoft.com/library/ee517278.aspx)](https://msdn.microsoft.com/library/ee517278.aspx) </span><span class="sxs-lookup"><span data-stu-id="9fd3a-149">[Claims to Windows Token Service (c2WTS) Overview (https://msdn.microsoft.com/library/ee517278.aspx)](https://msdn.microsoft.com/library/ee517278.aspx) </span></span>  
 [<span data-ttu-id="9fd3a-150">Общие сведения о проверке подлинности Kerberos для продуктов Microsoft SharePoint 2010 (https://technet.microsoft.com/library/gg502594.aspx)</span><span class="sxs-lookup"><span data-stu-id="9fd3a-150">Overview of Kerberos authentication for Microsoft SharePoint 2010 Products (https://technet.microsoft.com/library/gg502594.aspx)</span></span>](https://technet.microsoft.com/library/gg502594.aspx)  
  
