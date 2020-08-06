---
title: Проверка подлинности веб-службы | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Web service [Reporting Services], authentication
- XML Web service [Reporting Services], authentication
- Report Server Web service, authentication
ms.assetid: 852b4947-a090-4e54-8555-5a503945ceab
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0c7836d6eba8c6ab3f0a8e705ebb79c7ed73eb17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739203"
---
# <a name="web-service-authentication"></a><span data-ttu-id="0c181-102">Проверка подлинности веб-службы</span><span class="sxs-lookup"><span data-stu-id="0c181-102">Web Service Authentication</span></span>
  <span data-ttu-id="0c181-103">Для проверки подлинности запросов, поступающих веб-службе сервера отчетов, можно использовать как проверку подлинности Windows, так и обычную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="0c181-103">You can use either Windows Authentication or Basic authentication to authenticate the calls made to the Report Server Web service.</span></span> <span data-ttu-id="0c181-104">Любой клиент, отправляющий SOAP-запросы на сервер отчетов должен реализовать клиентскую часть одного из поддерживаемых протоколов проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="0c181-104">Any client that makes SOAP requests to the report server must implement the client portion of one of the supported authentication protocols.</span></span> <span data-ttu-id="0c181-105">При использовании можно [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] использовать классы HTTP управляемого кода для реализации проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="0c181-105">If you are using the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], you can use the managed code HTTP classes to implement authentication.</span></span> <span data-ttu-id="0c181-106">Использование данных API-интерфейсов облегчает пересылку данных проверки подлинности вместе с SOAP-запросами.</span><span class="sxs-lookup"><span data-stu-id="0c181-106">Using these APIs makes it easy to send authentication information along with the SOAP requests.</span></span>  
  
 <span data-ttu-id="0c181-107">Если пользователь не обладает необходимыми учетными данными для вызова веб-службы сервера отчетов, то вызов завершится с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="0c181-107">If you do not have appropriate credentials before you make a call to the Report Server Web service, the call fails.</span></span> <span data-ttu-id="0c181-108">Во время выполнения учетные данные можно передать веб-службе путем настройки свойства **Credentials** объекта на стороне клиента, представляющего веб-службу. Это следует выполнить перед вызовом методов веб-службы.</span><span class="sxs-lookup"><span data-stu-id="0c181-108">At run time, you can pass credentials to the Web service by setting the **Credentials** property of the client-side object that represents the Web service before you call its methods.</span></span>  
  
 <span data-ttu-id="0c181-109">В следующих разделах содержится пример кода, отправляющий учетные данные с помощью платформы [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c181-109">The following sections contain example code that sends credentials using the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span>  
  
## <a name="windows-authentication"></a><span data-ttu-id="0c181-110">Проверка подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="0c181-110">Windows Authentication</span></span>  
 <span data-ttu-id="0c181-111">Следующий код отправляет учетные данные проверки подлинности Windows веб-службе.</span><span class="sxs-lookup"><span data-stu-id="0c181-111">The following code passes Windows credentials to the Web service.</span></span>  
  
```vb  
Dim rs As New ReportingService()  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
```  
  
```csharp  
ReportingService rs = new ReportingService();  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials;  
```  
  
## <a name="basic-authentication"></a><span data-ttu-id="0c181-112">Обычная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="0c181-112">Basic Authentication</span></span>  
 <span data-ttu-id="0c181-113">Следующий код отправляет учетные данные обычной проверки подлинности веб-службе.</span><span class="sxs-lookup"><span data-stu-id="0c181-113">The following code passes Basic credentials to the Web service.</span></span>  
  
```vb  
Dim rs As New ReportingService()  
rs.Credentials = New System.Net.NetworkCredential("username", "password", "domain")  
```  
  
```csharp  
ReportingService service = new ReportingService();  
service.Credentials = new System.Net.NetworkCredential("username", "password", "domain");  
```  
  
 <span data-ttu-id="0c181-114">Учетные данные следует задать до вызова любых методов веб-службы сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="0c181-114">The credentials must be set before you call any of the methods of the Report Server Web service.</span></span> <span data-ttu-id="0c181-115">Если учетные данные не были заданы, то будет выведена ошибка с кодом HTTP 401: "В доступе отказано".</span><span class="sxs-lookup"><span data-stu-id="0c181-115">If you do not set the credentials, you receive the error code an HTTP 401 Error: Access Denied.</span></span> <span data-ttu-id="0c181-116">Перед использованием службы необходимо выполнить проверку подлинности, однако после того как учетные данные были заданы, нет необходимости задавать их повторно, пока используется та же переменная службы (например, *rs*).</span><span class="sxs-lookup"><span data-stu-id="0c181-116">You must authenticate the service before you use it, but after you have set the credentials, you do not need to set them again as long as you continue to use the same service variable (such as *rs*).</span></span>  
  
## <a name="custom-authentication"></a><span data-ttu-id="0c181-117">Нестандартная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="0c181-117">Custom Authentication</span></span>  
 <span data-ttu-id="0c181-118">В службы [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] включен API-интерфейс программирования, обеспечивающий разработчикам возможность проектирования и разработки нестандартных модулей проверки подлинности, также известных как модули безопасности.</span><span class="sxs-lookup"><span data-stu-id="0c181-118">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] includes a programming API that provides developers with the opportunity to design and develop custom authentication extensions, known as security extensions.</span></span> <span data-ttu-id="0c181-119">Дополнительные сведения см. в разделе [Implementing a Security Extension](../../extensions/security-extension/implementing-a-security-extension.md).</span><span class="sxs-lookup"><span data-stu-id="0c181-119">For more information, see [Implementing a Security Extension](../../extensions/security-extension/implementing-a-security-extension.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c181-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="0c181-120">See Also</span></span>  
 <span data-ttu-id="0c181-121">[Создание приложений с помощью веб-службы и .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="0c181-121">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 [<span data-ttu-id="0c181-122">Веб-службы сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="0c181-122">Report Server Web Service</span></span>](../report-server-web-service.md)  
  
  
