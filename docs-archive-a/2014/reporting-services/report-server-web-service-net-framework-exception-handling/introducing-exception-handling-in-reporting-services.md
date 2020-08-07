---
title: Введение в обработку исключений в службах Reporting Services | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Web service [Reporting Services], exception handling
- errors [Reporting Services]
- exceptions [Reporting Services]
- Report Server Web service, exception handling
- XML Web service [Reporting Services], exception handling
ms.assetid: 54381870-ce67-482b-aa83-6a838cdbf9b9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 091b1f40d293515617e369b750a5f18dfe12951b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731421"
---
# <a name="introducing-exception-handling-in-reporting-services"></a><span data-ttu-id="57e09-102">Знакомство с обработкой исключений в службах Reporting Services</span><span class="sxs-lookup"><span data-stu-id="57e09-102">Introducing Exception Handling in Reporting Services</span></span>
  <span data-ttu-id="57e09-103">Если приложение службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] направляет веб-службе сервера отчетов запрос, который эта служба не в состоянии обработать, служба возвращает клиенту исключение SOAP.</span><span class="sxs-lookup"><span data-stu-id="57e09-103">If your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] application sends a request to the Report Server Web service that the service is unable to process, the service returns a SOAP exception to the client.</span></span> <span data-ttu-id="57e09-104">Обработка исключений, формируемых веб-службой сервера отчетов, играет важную роль в создаваемых разработчиками приложениях, поскольку при возникновении ошибок приложения могут возвращать пользователям важные сведения.</span><span class="sxs-lookup"><span data-stu-id="57e09-104">Handling exceptions thrown by the Report Server Web service is an important part of the applications that you develop because you can return useful information to users when errors occur.</span></span>  
  
 <span data-ttu-id="57e09-105">В этом разделе содержатся конкретные данные, касающиеся обработки исключений, предотвращения ввода пользователями недопустимых значений и возврата пользователям значимых сведений об ошибках.</span><span class="sxs-lookup"><span data-stu-id="57e09-105">This section contains specific information about handling exceptions, preventing user input that is not valid, and returning meaningful error information to users.</span></span> <span data-ttu-id="57e09-106">Общие сведения об обработке исключений см. в разделе «Обработка и создание исключений» [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] документации по пакету SDK.</span><span class="sxs-lookup"><span data-stu-id="57e09-106">For general information about exception handling, see "Handling and Throwing Exceptions" in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK documentation.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="57e09-107">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="57e09-107">In This Section</span></span>  
  
|<span data-ttu-id="57e09-108">Раздел</span><span class="sxs-lookup"><span data-stu-id="57e09-108">Topic</span></span>|<span data-ttu-id="57e09-109">Описание</span><span class="sxs-lookup"><span data-stu-id="57e09-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="57e09-110">Обработка исключений в службах Reporting Services</span><span class="sxs-lookup"><span data-stu-id="57e09-110">Handling Exceptions in Reporting Services</span></span>](handling-exceptions-in-reporting-services.md)|<span data-ttu-id="57e09-111">Содержит общие сведения об исключениях в службах [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] и о роли SOAP в возврате ошибок веб-служб.</span><span class="sxs-lookup"><span data-stu-id="57e09-111">Provides an overview of exceptions in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] and the role of SOAP in returning errors from a Web service.</span></span>|  
|[<span data-ttu-id="57e09-112">Рекомендации по обработке исключений в службах Reporting Services</span><span class="sxs-lookup"><span data-stu-id="57e09-112">Best Practices for Reporting Services Exception Handling</span></span>](best-practices/best-practices-for-reporting-services-exception-handling.md)|<span data-ttu-id="57e09-113">Содержит рекомендации по обработке исключений в службах [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57e09-113">Provides recommendations on how to handle exceptions in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="57e09-114">Класс SoapException в службах Reporting Services</span><span class="sxs-lookup"><span data-stu-id="57e09-114">Reporting Services SoapException Class</span></span>](soapexception-class/reporting-services-soapexception-class.md)|<span data-ttu-id="57e09-115">Описывает класс **SoapException** в службах [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57e09-115">Describes the **SoapException** class in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="57e09-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="57e09-116">See Also</span></span>  
 [<span data-ttu-id="57e09-117">Создание приложений с помощью веб-службы и .NET Framework</span><span class="sxs-lookup"><span data-stu-id="57e09-117">Building Applications Using the Web Service and the .NET Framework</span></span>](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md)  
  
  
