---
title: Авторизация в службах Reporting Services | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- authorization [Reporting Services]
ms.assetid: 15fc1c7b-560c-4737-b126-e0d428a1b530
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7420b45175ca0b0a5fc66da4a7939b07b79c75b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664735"
---
# <a name="authorization-in-reporting-services"></a><span data-ttu-id="d1eaf-102">Авторизация в службах Reporting Services</span><span class="sxs-lookup"><span data-stu-id="d1eaf-102">Authorization in Reporting Services</span></span>
  <span data-ttu-id="d1eaf-103">Авторизация является процессом определения, должен ли быть предоставлен идентификатору запрошенный тип доступа к конкретному ресурсу в базе данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="d1eaf-103">Authorization is the process of determining whether an identity should be granted the requested type of access to a given resource in the report server database.</span></span> <span data-ttu-id="d1eaf-104">Службы [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] используют архитектуру авторизации на основе ролей, которая предоставляет пользователю доступ к конкретному ресурсу на основании назначенной этому пользователю роли в данном приложении.</span><span class="sxs-lookup"><span data-stu-id="d1eaf-104">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] uses a role-based authorization architecture that grants a user access to a given resource based on the user's role assignment for the application.</span></span> <span data-ttu-id="d1eaf-105">Модули безопасности для служб [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] содержат реализацию компонента авторизации, который используется для предоставления доступа пользователям после прохождения ими проверки подлинности на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="d1eaf-105">Security extensions for [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] contain an implementation of an authorization component that is used to grant access to users once they are authenticated on the report server.</span></span> <span data-ttu-id="d1eaf-106">Авторизация вызывается, когда пользователь пытается выполнить операцию в системе или на элементе сервера через API-интерфейс SOAP, либо посредством доступа по URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="d1eaf-106">Authorization is invoked when a user attempts to perform an operation on the system or a report server item through the SOAP API and via URL access.</span></span> <span data-ttu-id="d1eaf-107">Это стало возможным благодаря интерфейсу модуля безопасности **IAuthorizationExtension**.</span><span class="sxs-lookup"><span data-stu-id="d1eaf-107">This is made possible through the security extension interface **IAuthorizationExtension**.</span></span> <span data-ttu-id="d1eaf-108">Как указывалось выше, все развертываемые модули наследуют от базового интерфейса **IExtension** .</span><span class="sxs-lookup"><span data-stu-id="d1eaf-108">As stated previously, all extensions inherit from **IExtension** the base interface for any extension that you deploy.</span></span> <span data-ttu-id="d1eaf-109">Интерфейсы**IExtension** и **IAuthorizationExtension** являются членами пространства имен **Microsoft.ReportingServices.Interfaces** .</span><span class="sxs-lookup"><span data-stu-id="d1eaf-109">**IExtension** and **IAuthorizationExtension** are members of the **Microsoft.ReportingServices.Interfaces** namespace.</span></span>

## <a name="checking-access"></a><span data-ttu-id="d1eaf-110">Проверка доступа</span><span class="sxs-lookup"><span data-stu-id="d1eaf-110">Checking Access</span></span>
 <span data-ttu-id="d1eaf-111">При авторизации необходимым условием пользовательской реализации безопасности является проверка доступа, реализованная в методе <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A>.</span><span class="sxs-lookup"><span data-stu-id="d1eaf-111">In authorization, the key to any custom security implementation is the access check, which is implemented in the <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> method.</span></span> <span data-ttu-id="d1eaf-112">Метод <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> вызывается при каждой попытке пользователя выполнить операцию на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="d1eaf-112"><xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> is called each time a user attempts an operation on the report server.</span></span> <span data-ttu-id="d1eaf-113">Метод <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> перегружается для всех типов операций.</span><span class="sxs-lookup"><span data-stu-id="d1eaf-113">The <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> method is overloaded for each operation type.</span></span> <span data-ttu-id="d1eaf-114">Для операций с папками пример проверки доступа может выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d1eaf-114">For folder operations, an example of an access check might look like the following:</span></span>

```
// Overload for Folder operations
public bool CheckAccess(
   string userName, 
   IntPtr userToken, 
   byte[] secDesc, 
   FolderOperation requiredOperation)
{
   // If the user is the administrator, allow unrestricted access.
   if (userName == m_adminUserName) 
      return true;

   AceCollection acl = DeserializeAcl(secDesc);
   foreach(AceStruct ace in acl)
   {
         if (userName == ace.PrincipalName)
         {
            foreach(FolderOperation aclOperation in 
               ace.FolderOperations)
            {
               if (aclOperation == requiredOperation)
                     return true;
            }
         }
   }
   return false;
}
```

 <span data-ttu-id="d1eaf-115">Сервер отчетов вызывает метод <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A>, передавая имя зарегистрированного пользователя, токен пользователя, дескриптор безопасности для элемента и запрошенную операцию.</span><span class="sxs-lookup"><span data-stu-id="d1eaf-115">The report server calls the <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> method by passing in the name of the logged-on user, a user token, the security descriptor for the item, and the requested operation.</span></span> <span data-ttu-id="d1eaf-116">Здесь проводится проверка дескриптора безопасности для имени пользователя и наличия должного разрешения на выполнение запроса, в результате чего возвращается значение `true` для указания, что доступ предоставлен или `false` для указания, что в доступе отказано.</span><span class="sxs-lookup"><span data-stu-id="d1eaf-116">Here you would check the security descriptor for the user name and the appropriate permission to complete the request, then return `true` to signify that access is granted or `false` to signify access is denied.</span></span>

## <a name="security-descriptors"></a><span data-ttu-id="d1eaf-117">Дескрипторы безопасности</span><span class="sxs-lookup"><span data-stu-id="d1eaf-117">Security Descriptors</span></span>
 <span data-ttu-id="d1eaf-118">При установке политик авторизации для элементов в базе данных сервера отчетов, клиентское приложение (такое как диспетчер отчетов) передает сведения о пользователе в модуль безопасности вместе с политикой безопасности для данного элемента.</span><span class="sxs-lookup"><span data-stu-id="d1eaf-118">When setting authorization policies on items in the report server database, a client application (such as Report Manager) submits the user information to the security extension along with a security policy for the item.</span></span> <span data-ttu-id="d1eaf-119">Эта политика безопасности и сведения о пользователях вместе называются дескриптором безопасности.</span><span class="sxs-lookup"><span data-stu-id="d1eaf-119">This security policy and user information are known collectively as a security descriptor.</span></span> <span data-ttu-id="d1eaf-120">Дескриптор безопасности содержит следующие сведения для элемента в базе данных сервера отчетов:</span><span class="sxs-lookup"><span data-stu-id="d1eaf-120">A security descriptor contains the following information for an item in the report server database:</span></span>

-   <span data-ttu-id="d1eaf-121">Группа или пользователь, имеющие определенный тип разрешений на выполнение операций с этим элементом.</span><span class="sxs-lookup"><span data-stu-id="d1eaf-121">The group or user that has some type of permission to perform operations on the item.</span></span>

-   <span data-ttu-id="d1eaf-122">Тип данного элемента.</span><span class="sxs-lookup"><span data-stu-id="d1eaf-122">The item's type.</span></span>

-   <span data-ttu-id="d1eaf-123">Список управления доступом, управляющий доступом к этому элементу.</span><span class="sxs-lookup"><span data-stu-id="d1eaf-123">A discretionary access control list controlling access to the item.</span></span>

 <span data-ttu-id="d1eaf-124">Дескрипторы безопасности создаются при помощи методов <xref:ReportService2010.ReportingService2010.SetPolicies%2A> и <xref:ReportService2010.ReportingService2010.SetSystemPolicies%2A> веб-службы.</span><span class="sxs-lookup"><span data-stu-id="d1eaf-124">Security descriptors are created using the Web service <xref:ReportService2010.ReportingService2010.SetPolicies%2A> and <xref:ReportService2010.ReportingService2010.SetSystemPolicies%2A> methods.</span></span>

### <a name="authorization-flow"></a><span data-ttu-id="d1eaf-125">Поток авторизации</span><span class="sxs-lookup"><span data-stu-id="d1eaf-125">Authorization Flow</span></span>
 <span data-ttu-id="d1eaf-126">Авторизация служб [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] управляется модулем безопасности, настроенным в настоящее время для выполнения на сервере.</span><span class="sxs-lookup"><span data-stu-id="d1eaf-126">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] authorization is controlled by the security extension currently configured to run on the server.</span></span> <span data-ttu-id="d1eaf-127">Авторизация основана на ролях и ограничена разрешениями и операциями, предоставляемыми архитектурой безопасности служб [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d1eaf-127">Authorization is role-based and limited to the permissions and operations supplied by the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] security architecture.</span></span> <span data-ttu-id="d1eaf-128">На следующей диаграмме показан процесс авторизации пользователей для работы с элементами в базе данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="d1eaf-128">The following diagram depicts the process of authorizing users to operate on items in the report server database:</span></span>

 <span data-ttu-id="d1eaf-129">![Поток авторизации в системе безопасности Reporting Services](../../media/rosettasecurityextensionauthorizationflow.gif "Поток авторизации в системе безопасности Reporting Services")</span><span class="sxs-lookup"><span data-stu-id="d1eaf-129">![Reporting Services security authorization flow](../../media/rosettasecurityextensionauthorizationflow.gif "Reporting Services security authorization flow")</span></span>

 <span data-ttu-id="d1eaf-130">Как показано на этой диаграмме, авторизация выполняется в следующей последовательности.</span><span class="sxs-lookup"><span data-stu-id="d1eaf-130">As shown in this diagram, authorization follows this sequence:</span></span>

1.  <span data-ttu-id="d1eaf-131">После прохождения проверки подлинности клиентские приложения делают запросы серверу отчетов, используя методы веб-служб Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="d1eaf-131">Once authenticated, client applications make requests to the report server through the Reporting Services Web service methods.</span></span> <span data-ttu-id="d1eaf-132">Билет проверки подлинности передается серверу отчетов в форме куки-файла в заголовке HTTP каждого веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="d1eaf-132">An authentication ticket is passed to the report server in the form of a cookie in the HTTP header of each Web request.</span></span>

2.  <span data-ttu-id="d1eaf-133">Перед любой проверкой доступа проводится проверка куки-файла.</span><span class="sxs-lookup"><span data-stu-id="d1eaf-133">The cookie is validated prior to any access check.</span></span>

3.  <span data-ttu-id="d1eaf-134">После проверки куки-файла сервер отчетов вызывает метод <xref:Microsoft.ReportingServices.Interfaces.IAuthenticationExtension.GetUserInfo%2A> и пользователю дается идентификатор.</span><span class="sxs-lookup"><span data-stu-id="d1eaf-134">Once the cookie is validated, the report server calls <xref:Microsoft.ReportingServices.Interfaces.IAuthenticationExtension.GetUserInfo%2A> and the user is given an identity.</span></span>

4.  <span data-ttu-id="d1eaf-135">Пользователь пытается выполнить операцию с использованием веб-службы Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="d1eaf-135">The user attempts an operation through the Reporting Services Web service.</span></span>

5.  <span data-ttu-id="d1eaf-136">Сервер отчетов вызывает метод <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A>.</span><span class="sxs-lookup"><span data-stu-id="d1eaf-136">The report server calls the <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> method.</span></span>

6.  <span data-ttu-id="d1eaf-137">Дескриптор безопасности получается и передается настраиваемой реализации модуля безопасности <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A>.</span><span class="sxs-lookup"><span data-stu-id="d1eaf-137">The security descriptor is retrieved and passed to a custom security extension implementation of <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A>.</span></span> <span data-ttu-id="d1eaf-138">В этот момент пользователь, группа или компьютер сравниваются с дескриптором безопасности элемента, к которому выполняется доступ, и они авторизуются для выполнения запрошенной операции.</span><span class="sxs-lookup"><span data-stu-id="d1eaf-138">At this point, the user, group, or computer is compared to the security descriptor of the item being accessed and is authorized to perform the requested operation.</span></span>

7.  <span data-ttu-id="d1eaf-139">Если пользователь авторизован, веб-служба выполняет запрашиваемую операцию и возвращает ответ вызывающему приложению.</span><span class="sxs-lookup"><span data-stu-id="d1eaf-139">If the user is authorized, the Web service performs the operation and returns a response to the calling application.</span></span>


