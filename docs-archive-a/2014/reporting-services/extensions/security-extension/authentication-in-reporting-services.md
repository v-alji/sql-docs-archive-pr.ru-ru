---
title: Проверка подлинности в службах Reporting Services | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- security [Reporting Services], authentication
- forms-based authentication [Reporting Services]
- authentication [Reporting Services]
- custom authentication [Reporting Services]
ms.assetid: 103ce1f9-31d8-44bb-b540-2752e4dcf60b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 59e97ba6ef849d8b4bfddfd6953c85826e351d6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664744"
---
# <a name="authentication-in-reporting-services"></a><span data-ttu-id="037eb-102">Проверка подлинности в службах Reporting Services</span><span class="sxs-lookup"><span data-stu-id="037eb-102">Authentication in Reporting Services</span></span>
  <span data-ttu-id="037eb-103">Проверка подлинности — это процесс определения прав пользователя на удостоверение.</span><span class="sxs-lookup"><span data-stu-id="037eb-103">Authentication is the process of establishing a user's right to an identity.</span></span> <span data-ttu-id="037eb-104">Чтобы проверить подлинность, можно использовать много методов.</span><span class="sxs-lookup"><span data-stu-id="037eb-104">There are many techniques that you can use to authenticate a user.</span></span> <span data-ttu-id="037eb-105">Самым распространенным является использование паролей.</span><span class="sxs-lookup"><span data-stu-id="037eb-105">The most common way is to use passwords.</span></span> <span data-ttu-id="037eb-106">Например, если разрабатывается проверка подлинности с помощью форм, необходима реализация, которая запрашивает у пользователей учетные данные (обычно с помощью интерфейса, который запрашивает имя и пароль), а затем проверяет пользователей по хранилищу данных, которым может быть таблица, база данных или файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="037eb-106">When you implement Forms Authentication, for example, you want an implementation that queries users for credentials (usually by some interface that requests a login name and password) and then validates users against a data store, such as a database table or configuration file.</span></span> <span data-ttu-id="037eb-107">Если не удается проверить учетные данные, то процесс проверки подлинности завершается неуспешно и для пользователя принимается анонимное удостоверение.</span><span class="sxs-lookup"><span data-stu-id="037eb-107">If the credentials can't be validated, the authentication process fails and the user will assume an anonymous identity.</span></span>  
  
## <a name="custom-authentication-in-reporting-services"></a><span data-ttu-id="037eb-108">Нестандартная проверка подлинности в службах Reporting Services</span><span class="sxs-lookup"><span data-stu-id="037eb-108">Custom Authentication in Reporting Services</span></span>  
 <span data-ttu-id="037eb-109">Операционная система Windows в службах [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] выполняет проверку подлинности пользователей с помощью встроенной безопасности Windows или путем явного получения и проверки учетных данных пользователя.</span><span class="sxs-lookup"><span data-stu-id="037eb-109">In [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], the Windows operating system handles the authentication of users either through integrated security or through the explicit reception and validation of user credentials.</span></span> <span data-ttu-id="037eb-110">В службах [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] можно разработать нестандартную проверку подлинности, чтобы обеспечить поддержку дополнительных схем проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="037eb-110">Custom authentication can be developed in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] to support additional authentication schemes.</span></span> <span data-ttu-id="037eb-111">Это возможно с помощью интерфейса модуля безопасности <xref:Microsoft.ReportingServices.Interfaces.IAuthenticationExtension>.</span><span class="sxs-lookup"><span data-stu-id="037eb-111">This is made possible through the security extension interface <xref:Microsoft.ReportingServices.Interfaces.IAuthenticationExtension>.</span></span> <span data-ttu-id="037eb-112">Все модули, развертываемые и используемые на сервере отчетов, наследуют базовый интерфейс <xref:Microsoft.ReportingServices.Interfaces.IExtension>.</span><span class="sxs-lookup"><span data-stu-id="037eb-112">All extensions inherit from the <xref:Microsoft.ReportingServices.Interfaces.IExtension> base interface for any extension deployed and used by the report server.</span></span> <span data-ttu-id="037eb-113">Интерфейсы <xref:Microsoft.ReportingServices.Interfaces.IExtension> и <xref:Microsoft.ReportingServices.Interfaces.IAuthenticationExtension> входят в пространство имен <xref:Microsoft.ReportingServices.Interfaces>.</span><span class="sxs-lookup"><span data-stu-id="037eb-113"><xref:Microsoft.ReportingServices.Interfaces.IExtension>, as well as <xref:Microsoft.ReportingServices.Interfaces.IAuthenticationExtension>, are members of the <xref:Microsoft.ReportingServices.Interfaces> namespace.</span></span>  
  
 <span data-ttu-id="037eb-114">Основным способом проверки подлинности на сервере отчетов в службах [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] служит метод <xref:ReportService2010.ReportingService2010.LogonUser%2A>.</span><span class="sxs-lookup"><span data-stu-id="037eb-114">The primary way to authenticate against a report server in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] is the <xref:ReportService2010.ReportingService2010.LogonUser%2A> method.</span></span> <span data-ttu-id="037eb-115">Этот элемент веб-службы Reporting Services можно использовать для передачи учетных данных пользователя на сервер отчетов для проверки.</span><span class="sxs-lookup"><span data-stu-id="037eb-115">This member of the Reporting Services Web service can be used to pass user credentials to a report server for validation.</span></span> <span data-ttu-id="037eb-116">Базовый модуль безопасности реализует **иаусентикатионекстенсион. LogonUser** , который содержит пользовательский код проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="037eb-116">Your underlying security extension implements **IAuthenticationExtension.LogonUser** which contains your custom authentication code.</span></span> <span data-ttu-id="037eb-117">В образце проверки подлинности с помощью форм метод **LogonUser** выполняет проверку подлинности по переданным учетным данным и хранилищу пользователей в базе данных.</span><span class="sxs-lookup"><span data-stu-id="037eb-117">In the Forms Authentication sample, **LogonUser**, which performs an authentication check against the supplied credentials and a custom user store in a database.</span></span> <span data-ttu-id="037eb-118">Пример реализации метода **LogonUser** имеет следующий вид:</span><span class="sxs-lookup"><span data-stu-id="037eb-118">An example of an implementation of **LogonUser** looks like this:</span></span>  
  
```  
public bool LogonUser(string userName, string password, string authority)  
{  
   return AuthenticationUtilities.VerifyPassword(userName, password);  
}  
  
```  
  
 <span data-ttu-id="037eb-119">Следующий образец функции используется для проверки переданных учетных данных:</span><span class="sxs-lookup"><span data-stu-id="037eb-119">The following sample function is used to verify the supplied credentials:</span></span>  
  
```  
  
internal static bool VerifyPassword(string suppliedUserName,  
   string suppliedPassword)  
{   
   bool passwordMatch = false;  
   // Get the salt and pwd from the database based on the user name.  
   // See "How To: Use DPAPI (Machine Store) from ASP.NET," "How To:  
   // Use DPAPI (User Store) from Enterprise Services," and "How To:  
   // Create a DPAPI Library" for more information about how to use  
   // DPAPI to securely store connection strings.  
   SqlConnection conn = new SqlConnection(  
      "Server=localhost;" +   
      "Integrated Security=SSPI;" +  
      "database=UserAccounts");  
   SqlCommand cmd = new SqlCommand("LookupUser", conn);  
   cmd.CommandType = CommandType.StoredProcedure;  
  
   SqlParameter sqlParam = cmd.Parameters.Add("@userName",  
       SqlDbType.VarChar,  
       255);  
   sqlParam.Value = suppliedUserName;  
   try  
   {  
      conn.Open();  
      SqlDataReader reader = cmd.ExecuteReader();  
      reader.Read(); // Advance to the one and only row  
      // Return output parameters from returned data stream  
      string dbPasswordHash = reader.GetString(0);  
      string salt = reader.GetString(1);  
      reader.Close();  
      // Now take the salt and the password entered by the user  
      // and concatenate them together.  
      string passwordAndSalt = String.Concat(suppliedPassword, salt);  
      // Now hash them  
      string hashedPasswordAndSalt =  
         FormsAuthentication.HashPasswordForStoringInConfigFile(  
         passwordAndSalt,  
         "SHA1");  
      // Now verify them. Returns true if they are equal.  
      passwordMatch = hashedPasswordAndSalt.Equals(dbPasswordHash);  
   }  
   catch (Exception ex)  
   {  
       throw new Exception("Exception verifying password. " +  
          ex.Message);  
   }  
   finally  
   {  
       conn.Close();  
   }  
   return passwordMatch;  
}  
```  
  
## <a name="authentication-flow"></a><span data-ttu-id="037eb-120">Поток аутентификации</span><span class="sxs-lookup"><span data-stu-id="037eb-120">Authentication Flow</span></span>  
 <span data-ttu-id="037eb-121">Веб-служба Reporting Services предоставляет нестандартные модули проверки подлинности, позволяющие реализовать проверку подлинности с помощью форм в диспетчере отчетов и на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="037eb-121">The Reporting Services Web service provides custom authentication extensions to enable Forms Authentication by Report Manager and the report server.</span></span>  
  
 <span data-ttu-id="037eb-122">Метод <xref:ReportService2010.ReportingService2010.LogonUser%2A> веб-службы Reporting Services позволяет отправлять учетные данные на сервер отчетов для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="037eb-122">The <xref:ReportService2010.ReportingService2010.LogonUser%2A> method of the Reporting Services Web service is used to submit credentials to the report server for authentication.</span></span> <span data-ttu-id="037eb-123">Веб-служба использует заголовки HTTP для передачи билета проверки подлинности (называемого куки-файлом) с сервера на клиент для проверяемых запросов входа в систему.</span><span class="sxs-lookup"><span data-stu-id="037eb-123">The Web service uses HTTP headers to pass an authentication ticket (known as a "cookie") from the server to the client for validated logon requests.</span></span>  
  
 <span data-ttu-id="037eb-124">На следующем рисунке представлен метод проверки подлинности пользователей в веб-службе, где приложение развернуто на сервере отчетов, настроенном для использования нестандартного модуля проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="037eb-124">The following illustration depicts the method of authenticating users to the Web service when your application is deployed with a report server configured to use a custom authentication extension.</span></span>  
  
 <span data-ttu-id="037eb-125">![Поток аутентификации в системе безопасности Reporting Services](../../media/rosettasecurityextensionauthenticationflow.gif "Поток аутентификации в системе безопасности Reporting Services")</span><span class="sxs-lookup"><span data-stu-id="037eb-125">![Reporting Services security authentication flow](../../media/rosettasecurityextensionauthenticationflow.gif "Reporting Services security authentication flow")</span></span>  
  
 <span data-ttu-id="037eb-126">На рис. 1 процесс проверки подлинности представлен следующим образом.</span><span class="sxs-lookup"><span data-stu-id="037eb-126">As shown in Figure 2, the authentication process is as follows:</span></span>  
  
1.  <span data-ttu-id="037eb-127">Клиентское приложение вызывает метод <xref:ReportService2010.ReportingService2010.LogonUser%2A> веб-службы для проверки подлинности пользователя.</span><span class="sxs-lookup"><span data-stu-id="037eb-127">A client application calls the Web service <xref:ReportService2010.ReportingService2010.LogonUser%2A> method to authenticate a user.</span></span>  
  
2.  <span data-ttu-id="037eb-128">Веб-служба выполняет вызов <xref:ReportService2010.ReportingService2010.LogonUser%2A> метода модуля безопасности, в частности класс, реализующий **иаусентикатионекстенсион**.</span><span class="sxs-lookup"><span data-stu-id="037eb-128">The Web service makes a call to the <xref:ReportService2010.ReportingService2010.LogonUser%2A> method of your security extension, specifically, the class that implements **IAuthenticationExtension**.</span></span>  
  
3.  <span data-ttu-id="037eb-129">Реализация метода <xref:ReportService2010.ReportingService2010.LogonUser%2A> проверяет имя пользователя и пароль в хранилище пользователей или в центре безопасности.</span><span class="sxs-lookup"><span data-stu-id="037eb-129">Your implementation of <xref:ReportService2010.ReportingService2010.LogonUser%2A> validates the user name and password in the user store or security authority.</span></span>  
  
4.  <span data-ttu-id="037eb-130">После успешной проверки подлинности веб-служба создает куки-файл и управляет им в ходе сеанса.</span><span class="sxs-lookup"><span data-stu-id="037eb-130">Upon successful authentication, the Web service creates a cookie and manages it for the session.</span></span>  
  
5.  <span data-ttu-id="037eb-131">Веб-служба возвращает билет проверки подлинности в вызывающее приложение с помощью заголовка HTTP.</span><span class="sxs-lookup"><span data-stu-id="037eb-131">The Web service returns the authentication ticket to the calling application on the HTTP header.</span></span>  
  
 <span data-ttu-id="037eb-132">При успешной проверке подлинности пользователя с помощью модуля безопасности веб-служба создает куки-файл, который используется для последующих запросов.</span><span class="sxs-lookup"><span data-stu-id="037eb-132">When the Web service successfully authenticates a user through the security extension, it generates a cookie that is used for subsequent requests.</span></span> <span data-ttu-id="037eb-133">Куки-файл не может сохраняться в пользовательском центре безопасности, поскольку сервер отчетов не владеет центром безопасности.</span><span class="sxs-lookup"><span data-stu-id="037eb-133">The cookie may not persist within the custom security authority because the report server does not own the security authority.</span></span> <span data-ttu-id="037eb-134">Куки-файл возвращается из метода веб-службы <xref:ReportService2010.ReportingService2010.LogonUser%2A> и используется в последующих вызовах метода веб-службы и при доступе по URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="037eb-134">The cookie is returned from the <xref:ReportService2010.ReportingService2010.LogonUser%2A> Web service method and is used in subsequent Web service method calls and in URL access.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="037eb-135">Чтобы предотвратить несанкционированный доступ к куки-файлу во время передачи, файлы cookie, используемые для проверки подлинности, возвращаемые методом <xref:ReportService2010.ReportingService2010.LogonUser%2A>, должны передаваться безопасным способом с помощью шифрования по протоколу SSL.</span><span class="sxs-lookup"><span data-stu-id="037eb-135">In order to avoid compromising the cookie during transmission, authentication cookies returned from <xref:ReportService2010.ReportingService2010.LogonUser%2A> should be transmitted securely using Secure Sockets Layer (SSL) encryption.</span></span>  
  
 <span data-ttu-id="037eb-136">Во время доступа к серверу отчетов по URL-адресу, если установлен настраиваемый модуль безопасности, службы IIS и [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] автоматически управляют передачей билета проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="037eb-136">If you access the report server through URL access when a custom security extension is installed, Internet Information Services (IIS) and [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] automatically manage the transmission of the authentication ticket.</span></span> <span data-ttu-id="037eb-137">Если доступ к серверу отчетов выполняется через API SOAP, в реализацию класса-посредника необходимо включить дополнительную поддержку управления билетом проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="037eb-137">If you are accessing the report server through the SOAP API, your implementation of the proxy class must include additional support for managing the authentication ticket.</span></span> <span data-ttu-id="037eb-138">Дополнительные сведения об использовании API SOAP и управлении билетом проверки подлинности см. в разделе «Использование веб-служб с пользовательской безопасностью».</span><span class="sxs-lookup"><span data-stu-id="037eb-138">For more information about using the SOAP API and managing the authentication ticket, see "Using the Web Service with Custom Security."</span></span>  
  
## <a name="forms-authentication"></a><span data-ttu-id="037eb-139">Проверка подлинности с помощью форм</span><span class="sxs-lookup"><span data-stu-id="037eb-139">Forms Authentication</span></span>  
 <span data-ttu-id="037eb-140">Проверка подлинности с помощью форм — это тип проверки подлинности [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], в котором пользователь, не прошедший проверку, направляется в HTML-форму.</span><span class="sxs-lookup"><span data-stu-id="037eb-140">Forms Authentication is a type of [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] authentication in which an unauthenticated user is directed to an HTML form.</span></span> <span data-ttu-id="037eb-141">Когда пользователь предоставляет учетные данные, система создает куки-файл, содержащий билет проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="037eb-141">Once the user provides credentials, the system issues a cookie containing an authentication ticket.</span></span> <span data-ttu-id="037eb-142">При последующих запросах система сначала проверяет куки-файл, чтобы определить, прошел ли пользователь проверку подлинности на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="037eb-142">On later requests, the system first checks the cookie to see if the user was already authenticated by the report server.</span></span>  
  
 <span data-ttu-id="037eb-143">Можно расширить службы [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] для поддержки проверки подлинности с помощью форм, используя интерфейсы расширения системы безопасности, доступные через API служб Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="037eb-143">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] can be extended to support Forms Authentication using the security extensibility interfaces available through the Reporting Services API.</span></span> <span data-ttu-id="037eb-144">При расширении служб [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] для использования проверки подлинности с помощью форм используйте для всех каналов связи с сервером отчетов протокол SSL, чтобы предотвратить возможность доступа злоумышленника к куки-файлу другого пользователя.</span><span class="sxs-lookup"><span data-stu-id="037eb-144">If you extend [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] to use Forms Authentication, use Secure Sockets Layer (SSL) for all communications with the report server to prevent malicious users from gaining access to another user's cookie.</span></span> <span data-ttu-id="037eb-145">Протокол SSL позволяет клиентам и серверу отчетов проверять подлинность друг друга и обеспечивать невозможность считывания содержимого, передаваемого между двумя компьютерами, с других компьютеров.</span><span class="sxs-lookup"><span data-stu-id="037eb-145">SSL enables clients and a report server to authenticate each other and to ensure that no other computers can read the contents of communications between the two computers.</span></span> <span data-ttu-id="037eb-146">Все данные, отправляемые с клиента через SSL-соединению, шифруются, чтобы исключить возможность перехвата злоумышленником паролей или данных, отправляемых на сервер отчетов.</span><span class="sxs-lookup"><span data-stu-id="037eb-146">All data sent from a client through an SSL connection is encrypted so that malicious users cannot intercept passwords or data sent to a report server.</span></span>  
  
 <span data-ttu-id="037eb-147">Проверка подлинности с помощью форм обычно реализуется для поддержки учетных записей и проверки подлинности на платформах, отличных от Windows.</span><span class="sxs-lookup"><span data-stu-id="037eb-147">Forms Authentication is generally implemented to support accounts and authentication for platforms other than Windows.</span></span> <span data-ttu-id="037eb-148">Для пользователя, запрашивающего доступ к серверу отчетов, выводится графический интерфейс, а введенные учетные данные отправляются в центр безопасности для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="037eb-148">A graphical interface is presented to a user who requests access to a report server, and the supplied credentials are submitted to a security authority for authentication.</span></span>  
  
 <span data-ttu-id="037eb-149">Для проверки подлинности с помощью форм необходимо присутствие пользователя, вводящего учетные данные.</span><span class="sxs-lookup"><span data-stu-id="037eb-149">Forms Authentication requires that a person is present to enter credentials.</span></span> <span data-ttu-id="037eb-150">Для приложений, которые работают в автоматическом режиме и связываются непосредственно с веб-службами служб Reporting Services, проверку подлинности с помощью форм необходимо сочетать со схемой нестандартной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="037eb-150">For unattended applications that communicate directly with the Reporting Services Web service, Forms Authentication must be combined with a custom authentication scheme.</span></span>  
  
 <span data-ttu-id="037eb-151">Использование проверки подлинности с помощью форм в службах [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] оправдано в следующих случаях.</span><span class="sxs-lookup"><span data-stu-id="037eb-151">Forms Authentication is appropriate for [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] when:</span></span>  
  
-   <span data-ttu-id="037eb-152">Необходимо сохранять и проверять подлинность пользователей, не обладающих учетными записями [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="037eb-152">You need to store and authenticate users that do not have [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows accounts, and</span></span>  
  
-   <span data-ttu-id="037eb-153">Необходимо предоставлять собственную форму пользовательского интерфейса в виде страницы входа между различными страницами на веб-сайте.</span><span class="sxs-lookup"><span data-stu-id="037eb-153">You need to provide your own user interface form as a logon page between different pages on a Web site.</span></span>  
  
 <span data-ttu-id="037eb-154">При создании настраиваемого модуля безопасности, поддерживающего проверку подлинности с помощью форм, учитывайте следующие факторы.</span><span class="sxs-lookup"><span data-stu-id="037eb-154">Consider the following when writing a custom security extension that supports Forms Authentication:</span></span>  
  
-   <span data-ttu-id="037eb-155">Если используется проверка подлинности с помощью форм, необходимо включить анонимный доступ для виртуального каталога сервера отчетов в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="037eb-155">If you use Forms Authentication, anonymous access must be enabled on the report server virtual directory in Internet Information Services (IIS).</span></span>  
  
-   <span data-ttu-id="037eb-156">Для [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] необходимо установить проверку подлинности с помощью форм.</span><span class="sxs-lookup"><span data-stu-id="037eb-156">[!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] authentication must be set to Forms.</span></span> <span data-ttu-id="037eb-157">Проверка подлинности [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] для сервера отчетов настраивается в файле Web.config.</span><span class="sxs-lookup"><span data-stu-id="037eb-157">You configure [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] authentication in the Web.config file for the report server.</span></span>  
  
-   <span data-ttu-id="037eb-158">Службы [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] могут проверять подлинность и авторизовывать пользователей с помощью проверки подлинности Windows или нестандартной проверки подлинности, но оба метода не могут использоваться одновременно.</span><span class="sxs-lookup"><span data-stu-id="037eb-158">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] can authenticate and authorize users with either Windows Authentication or custom authentication, but not both.</span></span> <span data-ttu-id="037eb-159">Службы [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] не поддерживают одновременное использование нескольких модулей безопасности.</span><span class="sxs-lookup"><span data-stu-id="037eb-159">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] does not support simultaneous use of multiple security extensions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="037eb-160">См. также:</span><span class="sxs-lookup"><span data-stu-id="037eb-160">See Also</span></span>  
 [<span data-ttu-id="037eb-161">Реализация модуля безопасности</span><span class="sxs-lookup"><span data-stu-id="037eb-161">Implementing a Security Extension</span></span>](../security-extension/implementing-a-security-extension.md)  
  
  
