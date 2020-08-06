---
title: Рекомендации по обработке исключений в службах Reporting Services | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- exceptions [Reporting Services], best practices
ms.assetid: 72fecf28-f02e-4338-b50f-0b21f520302d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2e0561c19fbd3e709a0440a55f023f938eabf692
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658649"
---
# <a name="best-practices-for-reporting-services-exception-handling"></a><span data-ttu-id="93c85-102">Рекомендации по обработке исключений в службах Reporting Services</span><span class="sxs-lookup"><span data-stu-id="93c85-102">Best Practices for Reporting Services Exception Handling</span></span>
  <span data-ttu-id="93c85-103">При разработке приложений служб [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] существует несколько методик, которые можно использовать для избежания возникновения исключений или сокращения их количества.</span><span class="sxs-lookup"><span data-stu-id="93c85-103">When developing [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] applications, there are several methodologies you can use to eliminate or reduce the occurrence of exceptions.</span></span> <span data-ttu-id="93c85-104">При возникновении исключений пользователю следует выводить ясное и четкое сообщение об ошибке; кроме того, следует добавить обработку исключений, чтобы приложения не завершались неожиданно.</span><span class="sxs-lookup"><span data-stu-id="93c85-104">When exceptions do occur, provide clear and concise error messages to the user, and add adequate exception handling to prevent your applications from ending unexpectedly.</span></span>  
  
 <span data-ttu-id="93c85-105">Приложение, посылающее запросы веб-службе сервера отчетов должно выполнять следующие действия.</span><span class="sxs-lookup"><span data-stu-id="93c85-105">An application that sends requests to the Report Server Web service should do the following:</span></span>  
  
-   <span data-ttu-id="93c85-106">Оно должно избегать вызова исключений методом предотвращения создания как можно большего количества недопустимых запросов.</span><span class="sxs-lookup"><span data-stu-id="93c85-106">Avoid causing exceptions by preventing as many invalid requests as possible.</span></span>  
  
-   <span data-ttu-id="93c85-107">Оно должно по возможности перехватывать исключения и предоставлять определенные коды обработки ошибок.</span><span class="sxs-lookup"><span data-stu-id="93c85-107">Catch exceptions and provide specific error-handling code whenever possible.</span></span>  
  
-   <span data-ttu-id="93c85-108">Оно должно обрабатывать варианты ошибок, не выдающие исключений.</span><span class="sxs-lookup"><span data-stu-id="93c85-108">Deal with error cases that do not throw exceptions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="93c85-109">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="93c85-109">In This Section</span></span>  
  
|<span data-ttu-id="93c85-110">Раздел</span><span class="sxs-lookup"><span data-stu-id="93c85-110">Topic</span></span>|<span data-ttu-id="93c85-111">Описание</span><span class="sxs-lookup"><span data-stu-id="93c85-111">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="93c85-112">Предотвращение недопустимых запросов</span><span class="sxs-lookup"><span data-stu-id="93c85-112">Preventing Invalid Requests</span></span>](preventing-invalid-requests.md)|<span data-ttu-id="93c85-113">Описывает методики предотвращения отправки недопустимых запросов на сервер отчетов.</span><span class="sxs-lookup"><span data-stu-id="93c85-113">Describes techniques for preventing requests that are not valid from being sent to the report server.</span></span>|  
|[<span data-ttu-id="93c85-114">Использование блоков Try-Catch</span><span class="sxs-lookup"><span data-stu-id="93c85-114">Using Try and Catch Blocks</span></span>](using-try-and-catch-blocks.md)|<span data-ttu-id="93c85-115">Описывает, как можно увеличить надежность приложения с использованием блоков TRY и CATCH.</span><span class="sxs-lookup"><span data-stu-id="93c85-115">Describes how to further enhance the reliability of your application with try/catch blocks.</span></span>|  
|[<span data-ttu-id="93c85-116">Обработка предупреждений и ситуаций, не вызывающих исключения</span><span class="sxs-lookup"><span data-stu-id="93c85-116">Handling Warnings and Cases That Do Not Cause Exceptions</span></span>](handling-warnings-and-cases-that-do-not-cause-exceptions.md)|<span data-ttu-id="93c85-117">Объясняет, как следует обрабатывать ошибки, которые не приводят к формированию исключения службами [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93c85-117">Explains how to handle errors that do not result in an exception being thrown by [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="93c85-118">Использование свойства Detail для обработки определенных ошибок</span><span class="sxs-lookup"><span data-stu-id="93c85-118">Using the Detail Property to Handle Specific Errors</span></span>](using-the-detail-property-to-handle-specific-errors.md)|<span data-ttu-id="93c85-119">Описывает, как можно программным образом обрабатывать определенные ошибки с помощью свойства **Detail** объекта **SoapException**.</span><span class="sxs-lookup"><span data-stu-id="93c85-119">Explains how to programmatically handle specific errors by using the **Detail** property of the **SoapException** object.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="93c85-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="93c85-120">See Also</span></span>  
 <span data-ttu-id="93c85-121">[Свойство Detail](../soapexception-class/detail-property.md) </span><span class="sxs-lookup"><span data-stu-id="93c85-121">[Detail Property](../soapexception-class/detail-property.md) </span></span>  
 <span data-ttu-id="93c85-122">[Введение в обработку исключений в Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="93c85-122">[Introducing Exception Handling in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span></span>  
 [<span data-ttu-id="93c85-123">Класс SoapException в службах Reporting Services</span><span class="sxs-lookup"><span data-stu-id="93c85-123">Reporting Services SoapException Class</span></span>](../soapexception-class/reporting-services-soapexception-class.md)  
  
  
