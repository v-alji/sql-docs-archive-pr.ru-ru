---
title: Передача аргументов метода веб-службы | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Report Server Web service, methods
- Web service [Reporting Services], methods
- methods [Reporting Services], arguments
- XML Web service [Reporting Services], methods
ms.assetid: f7b9ca05-fc4c-4b30-8e5d-172dd0f4a832
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3ef5188934628589751fe92d1839da0efb265766
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739212"
---
# <a name="supplying-web-service-method-arguments"></a><span data-ttu-id="fb02b-102">Передача аргументов методу веб-службы</span><span class="sxs-lookup"><span data-stu-id="fb02b-102">Supplying Web Service Method Arguments</span></span>
  <span data-ttu-id="fb02b-103">Метод веб-службы сервера отчетов отправляет запрос в службу по заданному URL-адресу с помощью протокола SOAP по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="fb02b-103">A Report Server Web service method sends a request to the service at a given URL using SOAP over HTTP.</span></span> <span data-ttu-id="fb02b-104">Служба получает запрос, обрабатывает его, а затем возвращает ответное сообщение.</span><span class="sxs-lookup"><span data-stu-id="fb02b-104">The service receives the request, processes it, and then returns a response.</span></span> <span data-ttu-id="fb02b-105">Такие запросы и ответы на них имеют форму XML-документов.</span><span class="sxs-lookup"><span data-stu-id="fb02b-105">These requests and responses are in the form of XML documents.</span></span>  
  
## <a name="optional-parameters"></a><span data-ttu-id="fb02b-106">Необязательные параметры</span><span class="sxs-lookup"><span data-stu-id="fb02b-106">Optional Parameters</span></span>  
 <span data-ttu-id="fb02b-107">В некоторых случаях метод веб-службы может иметь необязательные входные параметры.</span><span class="sxs-lookup"><span data-stu-id="fb02b-107">In some cases, a Web service method can have optional input parameters.</span></span> <span data-ttu-id="fb02b-108">Даже если входной параметр метода веб-службы является необязательным, его все равно нужно указать и установить для него значение `null` (`Nothing` в [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="fb02b-108">Even if an input parameter for a Web service method is optional, you must still include it and set the parameter value to `null` (`Nothing` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]).</span></span> <span data-ttu-id="fb02b-109">Если для параметра задать значение `null`, то элемент для этого параметра в SOAP-запросе также будет иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="fb02b-109">Setting a parameter value to `null` sets the element value for that parameter in the SOAP request to `null`.</span></span>  
  
 <span data-ttu-id="fb02b-110">В следующем примере используется метод <xref:ReportService2010.ReportingService2010.CreateFolder%2A>, чтобы создать новую папку с именем Product Sales в папке Sales.</span><span class="sxs-lookup"><span data-stu-id="fb02b-110">The following example uses the <xref:ReportService2010.ReportingService2010.CreateFolder%2A> method to create a new folder named Product Sales in the Sales folder.</span></span> <span data-ttu-id="fb02b-111">Если для свойств папки задать значение `null`, то для папки не передаются пользовательские свойства:</span><span class="sxs-lookup"><span data-stu-id="fb02b-111">By supplying a `null` value for the folder properties, no user-specific properties are supplied for the folder:</span></span>  
  
```  
// C#  
rs.CreateFolder("Product Sales", "/Sales", null);  
```  
  
## <a name="complex-data-types"></a><span data-ttu-id="fb02b-112">Сложные типы данных</span><span class="sxs-lookup"><span data-stu-id="fb02b-112">Complex Data Types</span></span>  
 <span data-ttu-id="fb02b-113">Основным классом веб-службы сервера отчетов является <xref:ReportService2010.ReportingService2010>, который используется для вызова операций SOAP или веб-методов класса-посредника.</span><span class="sxs-lookup"><span data-stu-id="fb02b-113">The core class of the Report Server Web service is <xref:ReportService2010.ReportingService2010>, which you use to invoke the SOAP operations or Web methods of the proxy class.</span></span> <span data-ttu-id="fb02b-114">Чтобы обеспечить поддержку этого класса и его методов, службы [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] включают определяемые пользователем сложные типы данных, относящиеся к входным и выходным параметрам методов веб-службы.</span><span class="sxs-lookup"><span data-stu-id="fb02b-114">To support this class and its methods, [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] includes user-defined, complex data types that are specific to the input and output parameters of the Web service methods.</span></span> <span data-ttu-id="fb02b-115">Эти сложные типы данных являются частью созданного класса прокси, который можно использовать при разработке в [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] среде.</span><span class="sxs-lookup"><span data-stu-id="fb02b-115">These complex data types are part of the generated proxy class, which you can use when developing in the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] environment.</span></span>  
  
 <span data-ttu-id="fb02b-116">Во время создания класса-посредника сложные типы данных, определенные в WSDL-файле, представляются классами-посредниками, которые включают свойства, соответствующие различным элементам SOAP в сложных типах данных.</span><span class="sxs-lookup"><span data-stu-id="fb02b-116">When you generate a proxy class, the complex data types that are defined in the WSDL file are represented by the classes of the proxy, which include properties that correspond to the various SOAP elements of the complex data types.</span></span> <span data-ttu-id="fb02b-117">Последовательности таких типов данных становятся массивами объектов, которые можно перечислять в коде.</span><span class="sxs-lookup"><span data-stu-id="fb02b-117">Sequences of these data types become arrays of objects that you can enumerate through in your code.</span></span> <span data-ttu-id="fb02b-118">Это устраняет необходимость непосредственной работы с XML-структурами, отправляемыми в сообщениях SOAP.</span><span class="sxs-lookup"><span data-stu-id="fb02b-118">This eliminates the need to work directly with the XML structures sent in SOAP messages.</span></span> <span data-ttu-id="fb02b-119">Платформа [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] выполняет необходимые преобразования.</span><span class="sxs-lookup"><span data-stu-id="fb02b-119">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] handles that translation for you.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb02b-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="fb02b-120">See Also</span></span>  
 <span data-ttu-id="fb02b-121">[Создание приложений с помощью веб-службы и .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="fb02b-121">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="fb02b-122">[Веб-служба сервера отчетов](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="fb02b-122">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 [<span data-ttu-id="fb02b-123">Технический справочник (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="fb02b-123">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
