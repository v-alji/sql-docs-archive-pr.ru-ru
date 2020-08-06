---
title: Общие сведения о модулях безопасности | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- security [Reporting Services], extensions
ms.assetid: 24ccd795-6506-457c-93ac-6a9dd6bb9a46
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9cd6c2a1518b724a7faafecdb2926505694e9707
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664728"
---
# <a name="security-extensions-overview"></a><span data-ttu-id="45cf0-102">Общие сведения о модулях безопасности</span><span class="sxs-lookup"><span data-stu-id="45cf0-102">Security Extensions Overview</span></span>
  <span data-ttu-id="45cf0-103">Модуль безопасности служб [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] позволяет проводить проверку подлинности и авторизацию пользователей и групп, то есть этот модуль позволяет пользователям входить на сервер отчетов и в соответствии с их удостоверениями выполнять различные задачи и операции.</span><span class="sxs-lookup"><span data-stu-id="45cf0-103">A [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] security extension enables the authentication and authorization of users or groups; that is, it enables different users to log on to a report server and, based on their identities, perform different tasks or operations.</span></span> <span data-ttu-id="45cf0-104">По умолчанию службы [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] используют модуль проверки подлинности Windows, который в свою очередь использует протоколы учетных записей Windows для проверки удостоверений пользователей, которые заявляют, что имеют учетные записи в системе.</span><span class="sxs-lookup"><span data-stu-id="45cf0-104">By default, [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] uses a Windows-based authentication extension, which uses Windows account protocols to verify the identities of users who claim to have accounts on the system.</span></span> <span data-ttu-id="45cf0-105">Службы [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] используют систему безопасности на основе ролей для авторизации пользователей.</span><span class="sxs-lookup"><span data-stu-id="45cf0-105">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] uses a role-based security system to authorize users.</span></span> <span data-ttu-id="45cf0-106">Модель безопасности служб [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] на основе ролей похожа на модели безопасности на основе ролей других технологий.</span><span class="sxs-lookup"><span data-stu-id="45cf0-106">The [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] role-based security model is similar to the role-based security models of other technologies.</span></span>

 <span data-ttu-id="45cf0-107">Поскольку модули безопасности основываются на открытом и дополняемом API-интерфейсе, в службах [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]можно создавать новые модули проверки подлинности и авторизации.</span><span class="sxs-lookup"><span data-stu-id="45cf0-107">Because security extensions are based on an open and extensible API, you can create new authentication and authorization extensions in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="45cf0-108">Ниже проводится пример реализации типичного модуля безопасности, использующего проверку подлинности и авторизацию на основе форм:</span><span class="sxs-lookup"><span data-stu-id="45cf0-108">The following is an example of a typical security extension implementation that uses Forms-based authentication and authorization:</span></span>

 <span data-ttu-id="45cf0-109">![Процесс модуля безопасности Reporting Services](../../media/rosettasecurityextensionflow.gif "Процесс модуля безопасности Reporting Services")</span><span class="sxs-lookup"><span data-stu-id="45cf0-109">![Reporting Services security extension process](../../media/rosettasecurityextensionflow.gif "Reporting Services security extension process")</span></span>

 <span data-ttu-id="45cf0-110">Как показано на иллюстрации, проверка подлинности и авторизация происходит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="45cf0-110">As shown in the illustration, authentication and authorization occur as follows:</span></span>

1.  <span data-ttu-id="45cf0-111">Пользователь пытается получить доступ к диспетчеру отчетов при помощи URL-адреса, в результате чего он перенаправляется к форме, которая собирает учетные данные о пользователе для клиентского приложения.</span><span class="sxs-lookup"><span data-stu-id="45cf0-111">A user tries to access Report Manager by using a URL and is redirected to a form that collects user credentials for the client application.</span></span>

2.  <span data-ttu-id="45cf0-112">Пользователь вносит учетные данные в форму.</span><span class="sxs-lookup"><span data-stu-id="45cf0-112">The user submits credentials to the form.</span></span>

3.  <span data-ttu-id="45cf0-113">Учетные данные пользователя передаются в веб-службу Reporting Services с помощью метода <xref:ReportService2010.ReportingService2010.LogonUser%2A>.</span><span class="sxs-lookup"><span data-stu-id="45cf0-113">The user credentials are submitted to the Reporting Services Web service through the <xref:ReportService2010.ReportingService2010.LogonUser%2A> method.</span></span>

4.  <span data-ttu-id="45cf0-114">Веб-служба вызывает предоставляемый пользователем модуль безопасности и проверяет, существуют ли имя пользователя и пароль в пользовательском центре безопасности.</span><span class="sxs-lookup"><span data-stu-id="45cf0-114">The Web service calls the customer-supplied security extension and verifies that the user name and password exist in the custom security authority.</span></span>

5.  <span data-ttu-id="45cf0-115">После проверки подлинности веб-служба создает билет проверки подлинности (известный как куки-файл), управляет этим билетом и проверяет роль пользователя на домашней странице диспетчера отчетов.</span><span class="sxs-lookup"><span data-stu-id="45cf0-115">After authentication, the Web service creates an authentication ticket (known as a "cookie"), manages the ticket, and verifies the user's role for the Home page of Report Manager.</span></span>

6.  <span data-ttu-id="45cf0-116">Веб-служба возвращает куки-файл браузеру и отображает интерфейс соответствующего пользователя в диспетчере отчетов.</span><span class="sxs-lookup"><span data-stu-id="45cf0-116">The Web service returns the cookie to the browser and displays the appropriate user interface in Report Manager.</span></span>

7.  <span data-ttu-id="45cf0-117">После проверки подлинности пользователя браузер отправляет запрос диспетчеру отчетов, вставляя куки-файл в заголовок HTTP.</span><span class="sxs-lookup"><span data-stu-id="45cf0-117">After the user is authenticated, the browser makes requests to Report Manager while transmitting the cookie in the HTTP header.</span></span> <span data-ttu-id="45cf0-118">Эти запросы выполняются в ответ на действия пользователя внутри приложения диспетчера отчетов.</span><span class="sxs-lookup"><span data-stu-id="45cf0-118">These requests are in response to user actions within the Report Manager application.</span></span>

8.  <span data-ttu-id="45cf0-119">Куки-файл в заголовке HTTP передается веб-службе вместе с запрошенной пользователем операцией.</span><span class="sxs-lookup"><span data-stu-id="45cf0-119">The cookie is transmitted in the HTTP header to the Web service along with the requested user operation.</span></span>

9. <span data-ttu-id="45cf0-120">Куки-файл проверяется, и, если проверка проходит успешно, сервер отчетов возвращает дескриптор безопасности и другие сведения, связанные с запрашиваемой операцией, из базы данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="45cf0-120">The cookie is validated, and if it is valid, the report server returns the security descriptor and other information relating to the requested operation from the report server database.</span></span>

10. <span data-ttu-id="45cf0-121">Если куки-файл проходит проверку, сервер отчетов вызывает модуль безопасности, чтобы проверить, имеет ли пользователь разрешение для выполнения определенной операции.</span><span class="sxs-lookup"><span data-stu-id="45cf0-121">If the cookie is valid, the report server makes a call to the security extension to check if the user is authorized to perform the specific operation.</span></span>

11. <span data-ttu-id="45cf0-122">Если пользователь имеет такое разрешение, сервер отчетов выполняет запрошенную операцию и возвращает управление вызывавшему объекту.</span><span class="sxs-lookup"><span data-stu-id="45cf0-122">If the user is authorized, the report server performs the requested operation and returns control to the caller.</span></span>

12. <span data-ttu-id="45cf0-123">После проверки подлинности пользователя во время доступа по URL-адресу к серверу отчетов используется тот же куки-файл.</span><span class="sxs-lookup"><span data-stu-id="45cf0-123">After the user is authenticated, URL access to the report server uses the same cookie.</span></span> <span data-ttu-id="45cf0-124">Куки-файл передается в заголовке HTTP.</span><span class="sxs-lookup"><span data-stu-id="45cf0-124">The cookie is transmitted in the HTTP header.</span></span>

13. <span data-ttu-id="45cf0-125">Пользователь продолжает запрашивать операции на сервере отчетов до завершения сеанса.</span><span class="sxs-lookup"><span data-stu-id="45cf0-125">The user continues to request operations on the report server until the session has ended.</span></span>

## <a name="when-to-implement-a-security-extension"></a><span data-ttu-id="45cf0-126">Целесообразность реализации модуля безопасности</span><span class="sxs-lookup"><span data-stu-id="45cf0-126">When to Implement a Security Extension</span></span>
 <span data-ttu-id="45cf0-127">Рекомендуется использовать проверку подлинности Windows, если это возможно.</span><span class="sxs-lookup"><span data-stu-id="45cf0-127">We recommend that you use Windows Authentication if at all possible.</span></span> <span data-ttu-id="45cf0-128">Однако пользовательская проверка подлинности и авторизация для служб [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] может быть предпочтительнее в следующих двух случаях.</span><span class="sxs-lookup"><span data-stu-id="45cf0-128">However, custom authentication and authorization for [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] may be appropriate in the following two cases:</span></span>

-   <span data-ttu-id="45cf0-129">Имеется приложение для Интернета или корпоративной сети, которое не может использовать учетные записи Windows.</span><span class="sxs-lookup"><span data-stu-id="45cf0-129">You have an Internet or extranet application that cannot use Windows accounts.</span></span>

-   <span data-ttu-id="45cf0-130">Имеются определяемые пользователем пользователи и роли, и необходимо предоставить подходящую схему авторизации в службах [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="45cf0-130">You have custom-defined users and roles and need to provide a matching authorization scheme in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="45cf0-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="45cf0-131">See Also</span></span>
 <span data-ttu-id="45cf0-132">[Реализация модуля безопасности](../security-extension/implementing-a-security-extension.md) [Настройка диспетчер отчетов для передачи файлов cookie для пользовательской проверки подлинности](../../security/configure-the-web-portal-to-pass-custom-authentication-cookies.md)</span><span class="sxs-lookup"><span data-stu-id="45cf0-132">[Implementing a Security Extension](../security-extension/implementing-a-security-extension.md) [Configure Report Manager to Pass Custom Authentication Cookies](../../security/configure-the-web-portal-to-pass-custom-authentication-cookies.md)</span></span>


