---
title: Регистрация имени субъекта-службы для сервера отчетов | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: dda91d4f-77cc-4898-ad03-810ece5f8e74
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 502170f16aad66757e8f44419ccbac3017072449
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668650"
---
# <a name="register-a-service-principal-name-spn-for-a-report-server"></a><span data-ttu-id="4b6ef-102">зарегистрировать имя участника-службы для сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="4b6ef-102">Register a Service Principal Name (SPN) for a Report Server</span></span>
  <span data-ttu-id="4b6ef-103">При развертывании служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] в сети, где для взаимной проверки подлинности используется протокол Kerberos, а сервер отчетов настроен для запуска от учетной записи пользователя домена, необходимо создать для службы сервера отчетов имя участника-службы (SPN).</span><span class="sxs-lookup"><span data-stu-id="4b6ef-103">If you are deploying [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in a network that uses the Kerberos protocol for mutual authentication, you must create a Service Principal Name (SPN) for the Report Server service if you configure it to run as a domain user account.</span></span>  
  
## <a name="about-spns"></a><span data-ttu-id="4b6ef-104">Сведения об именах участников-служб</span><span class="sxs-lookup"><span data-stu-id="4b6ef-104">About SPNs</span></span>  
 <span data-ttu-id="4b6ef-105">Имя участника-службы представляет собой уникальный идентификатор службы в сети, использующей проверку подлинности по протоколу Kerberos.</span><span class="sxs-lookup"><span data-stu-id="4b6ef-105">An SPN is a unique identifier for a service on a network that uses Kerberos authentication.</span></span> <span data-ttu-id="4b6ef-106">Оно состоит из класса службы, имени узла и номера порта.</span><span class="sxs-lookup"><span data-stu-id="4b6ef-106">It consists of a service class, a host name, and a port.</span></span> <span data-ttu-id="4b6ef-107">В сети с проверкой подлинности по протоколу Kerberos имя участника-службы для сервера должно быть зарегистрировано либо со встроенной учетной записью компьютера (например, «Сетевая служба» или «Локальная система»), либо с учетной записью пользователя.</span><span class="sxs-lookup"><span data-stu-id="4b6ef-107">On a network that uses Kerberos authentication, an SPN for the server must be registered under either a built-in computer account (such as NetworkService or LocalSystem) or user account.</span></span> <span data-ttu-id="4b6ef-108">Регистрация имен участников-служб для встроенных учетных записей производится автоматически.</span><span class="sxs-lookup"><span data-stu-id="4b6ef-108">SPNs are registered for built-in accounts automatically.</span></span> <span data-ttu-id="4b6ef-109">Если же служба запускается от учетной записи пользователя домена, необходимо вручную зарегистрировать имя участника-службы для применяемого типа учетной записи.</span><span class="sxs-lookup"><span data-stu-id="4b6ef-109">However, when you run a service under a domain user account, you must manually register the SPN for the account you want to use.</span></span>  
  
 <span data-ttu-id="4b6ef-110">Чтобы создать имя субъекта-службы, можно воспользоваться программой командной строки **SetSPN** .</span><span class="sxs-lookup"><span data-stu-id="4b6ef-110">To create an SPN, you can use the **SetSPN** command line utility.</span></span> <span data-ttu-id="4b6ef-111">Дополнительные сведения см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="4b6ef-111">For more information, see the following:</span></span>  
  
-   <span data-ttu-id="4b6ef-112">[Setspn](https://technet.microsoft.com/library/cc731241\(WS.10\).aspx) ( https://technet.microsoft.com/library/cc731241(WS.10).aspx) .</span><span class="sxs-lookup"><span data-stu-id="4b6ef-112">[Setspn](https://technet.microsoft.com/library/cc731241\(WS.10\).aspx) (https://technet.microsoft.com/library/cc731241(WS.10).aspx).</span></span>  
  
-   <span data-ttu-id="4b6ef-113">[Синтаксис имен субъектов-служб (SPN) SetSPN (Setspn.exe)](https://social.technet.microsoft.com/wiki/contents/articles/717.service-principal-names-spns-setspn-syntax-setspn-exe.aspx) ( https://social.technet.microsoft.com/wiki/contents/articles/717.service-principal-names-spns-setspn-syntax-setspn-exe.aspx) .</span><span class="sxs-lookup"><span data-stu-id="4b6ef-113">[Service Principal Names (SPNs) SetSPN Syntax (Setspn.exe)](https://social.technet.microsoft.com/wiki/contents/articles/717.service-principal-names-spns-setspn-syntax-setspn-exe.aspx) (https://social.technet.microsoft.com/wiki/contents/articles/717.service-principal-names-spns-setspn-syntax-setspn-exe.aspx).</span></span>  
  
 <span data-ttu-id="4b6ef-114">Для ее запуска на контроллере домена необходимо быть администратором домена.</span><span class="sxs-lookup"><span data-stu-id="4b6ef-114">You must be a domain administrator to run the utility on the domain controller.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b6ef-115">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4b6ef-115">Syntax</span></span>  
 <span data-ttu-id="4b6ef-116">Синтаксис команд, применяющийся в программе SetSPN для создания имени участника-службы для сервера отчетов, выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="4b6ef-116">The command syntax for using SetSPN utility to create an SPN for the report server resembles the following:</span></span>  
  
```  
Setspn -s http/<computername>.<domainname>:<port> <domain-user-account>  
```  
  
 <span data-ttu-id="4b6ef-117">**SetSPN** входит в комплект Windows Server.</span><span class="sxs-lookup"><span data-stu-id="4b6ef-117">**SetSPN** is available with Windows Server.</span></span> <span data-ttu-id="4b6ef-118">Аргумент `-s` добавляет имена участников-служб после проверки на отсутствие дубликатов.</span><span class="sxs-lookup"><span data-stu-id="4b6ef-118">The `-s` argument adds a SPN after validating no duplicate exists.</span></span> <span data-ttu-id="4b6ef-119">**Примечание. -s** доступен в Windows Server, начиная с Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="4b6ef-119">**NOTE:-s** is available in Windows Server starting with Windows Server 2008.</span></span>  
  
 <span data-ttu-id="4b6ef-120">`HTTP`— класс службы.</span><span class="sxs-lookup"><span data-stu-id="4b6ef-120">`HTTP` is the service class.</span></span> <span data-ttu-id="4b6ef-121">Веб-служба сервера отчетов работает в компоненте HTTP.SYS.</span><span class="sxs-lookup"><span data-stu-id="4b6ef-121">The Report Server Web service runs in HTTP.SYS.</span></span> <span data-ttu-id="4b6ef-122">Создание имени участника-службы для компонента HTTP имеет один побочный эффект: всем веб-приложениям, запускаемым компонентом HTTP.SYS (включая размещенные в службе IIS), будут предоставляться билеты на основе учетной записи пользователя домена.</span><span class="sxs-lookup"><span data-stu-id="4b6ef-122">A by-product of creating an SPN for HTTP is that all Web applications on the same computer that run in HTTP.SYS (including applications hosted in IIS) will be granted tickets based on the domain user account.</span></span> <span data-ttu-id="4b6ef-123">Если эти службы запускаются от имени других учетных записей, то запросы на проверку подлинности будут завершаться ошибкой.</span><span class="sxs-lookup"><span data-stu-id="4b6ef-123">If those services run under a different account, the authentication requests will fail.</span></span> <span data-ttu-id="4b6ef-124">Чтобы избежать этой проблемы, необходимо настроить все HTTP-приложения для запуска от одной и той же учетной записи либо назначить для каждого из приложений заголовок, а для каждого из узлов создать отдельное имя участника-службы.</span><span class="sxs-lookup"><span data-stu-id="4b6ef-124">To avoid this problem, be sure to configure all HTTP applications to run under the same account, or consider creating host headers for each application and then creating separate SPNs for each host header.</span></span> <span data-ttu-id="4b6ef-125">При настройке заголовков узлов изменения в DNS придется вносить вне зависимости от настройки служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4b6ef-125">When you configure host headers, DNS changes are required regardless of the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] configuration.</span></span>  
  
 <span data-ttu-id="4b6ef-126">Значения, указываемые для \<*computername*> , \<*domainname*> и \<*port*> определяют уникальный сетевой адрес компьютера, на котором размещен сервер отчетов.</span><span class="sxs-lookup"><span data-stu-id="4b6ef-126">The values that you specify for \<*computername*>, \<*domainname*>, and \<*port*> identify the unique network address of the computer that hosts the report server.</span></span> <span data-ttu-id="4b6ef-127">Это может быть как локальное имя узла, так и полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="4b6ef-127">This can be a local host name or a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="4b6ef-128">Если у вас есть только один домен и используется порт 80, можно опустить \<*domainname*> и \<*port*> из командной строки.</span><span class="sxs-lookup"><span data-stu-id="4b6ef-128">If you only have one domain and are using port 80, you can omit \<*domainname*> and \<*port*> from your command line.</span></span> <span data-ttu-id="4b6ef-129">\<*domain-user-account*>Учетная запись пользователя, под которой выполняется служба сервера отчетов, для которой должно быть зарегистрировано имя субъекта-службы.</span><span class="sxs-lookup"><span data-stu-id="4b6ef-129">\<*domain-user-account*> is the user account under which the Report Server service runs and for which the SPN must be registered.</span></span>  
  
## <a name="register-an-spn-for-domain-user-account"></a><span data-ttu-id="4b6ef-130">Регистрация имени участника-службы для учетной записи пользователя домена</span><span class="sxs-lookup"><span data-stu-id="4b6ef-130">Register an SPN for Domain User Account</span></span>  
  
#### <a name="to-register-an-spn-for-a-report-server-service-running-as-a-domain-user"></a><span data-ttu-id="4b6ef-131">Регистрация имени участника-службы для службы сервера отчетов, которая запускается от имени пользователя домена</span><span class="sxs-lookup"><span data-stu-id="4b6ef-131">To register an SPN for a Report Server service running as a domain user</span></span>  
  
1.  <span data-ttu-id="4b6ef-132">Установите службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] и настройте службу сервера отчетов для запуска от учетной записи пользователя домена.</span><span class="sxs-lookup"><span data-stu-id="4b6ef-132">Install [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] and configure the Report Server service to run as a domain user account.</span></span> <span data-ttu-id="4b6ef-133">Не забывайте, что пользователи не смогут соединиться с сервером отчетов до тех пор, пока не будут выполнены все описанные ниже шаги.</span><span class="sxs-lookup"><span data-stu-id="4b6ef-133">Note that users will not be able to connect to the report server until you complete the following steps.</span></span>  
  
2.  <span data-ttu-id="4b6ef-134">Войдите на контроллер домена как администратор домена.</span><span class="sxs-lookup"><span data-stu-id="4b6ef-134">Log on to the domain controller as domain administrator.</span></span>  
  
3.  <span data-ttu-id="4b6ef-135">Откройте окно командной строки и</span><span class="sxs-lookup"><span data-stu-id="4b6ef-135">Open a Command Prompt window.</span></span>  
  
4.  <span data-ttu-id="4b6ef-136">Скопируйте следующую команду, заменив заполнители значениями для конкретной сети:</span><span class="sxs-lookup"><span data-stu-id="4b6ef-136">Copy the following command, replacing placeholder values with actual values that are valid for your network:</span></span>  
  
    ```  
    Setspn -s http/<computer-name>.<domain-name>:<port> <domain-user-account>  
    ```  
  
     <span data-ttu-id="4b6ef-137">Пример: `Setspn -s http/MyReportServer.MyDomain.com:80 MyDomainUser`</span><span class="sxs-lookup"><span data-stu-id="4b6ef-137">For example: `Setspn -s http/MyReportServer.MyDomain.com:80 MyDomainUser`</span></span>  
  
5.  <span data-ttu-id="4b6ef-138">Выполните команду.</span><span class="sxs-lookup"><span data-stu-id="4b6ef-138">Run the command.</span></span>  
  
6.  <span data-ttu-id="4b6ef-139">Откройте файл **RsReportServer.config** и найдите раздел `<AuthenticationTypes>` .</span><span class="sxs-lookup"><span data-stu-id="4b6ef-139">Open the **RsReportServer.config** file and locate the `<AuthenticationTypes>` section.</span></span>  
  
7.  <span data-ttu-id="4b6ef-140">Добавьте `<RSWindowsNegotiate/>` в качестве первой записи этого раздела для включения NTLM.</span><span class="sxs-lookup"><span data-stu-id="4b6ef-140">Add `<RSWindowsNegotiate/>` as the first entry in this section to enable NTLM.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b6ef-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="4b6ef-141">See Also</span></span>  
 <span data-ttu-id="4b6ef-142">[Настройка учетной записи службы &#40;служб SSRS Configuration Manager&#41;](../../sql-server/install/configure-a-service-account-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="4b6ef-142">[Configure a Service Account &#40;SSRS Configuration Manager&#41;](../../sql-server/install/configure-a-service-account-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="4b6ef-143">[Настройка учетной записи службы сервера отчетов (диспетчер конфигурации служб SSRS)](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="4b6ef-143">[Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span></span>  
 [<span data-ttu-id="4b6ef-144">Управление сервером отчетов Reporting Services в собственном режиме</span><span class="sxs-lookup"><span data-stu-id="4b6ef-144">Manage a Reporting Services Native Mode Report Server</span></span>](manage-a-reporting-services-native-mode-report-server.md)  
  
  
