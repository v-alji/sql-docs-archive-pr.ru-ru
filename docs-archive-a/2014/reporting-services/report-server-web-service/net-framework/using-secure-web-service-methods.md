---
title: Использование защищенных методов веб-службы | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- SOAP [Reporting Services], secure connections
- Web service [Reporting Services], SOAP
- Report Server Web service, SOAP
- XML Web service [Reporting Services], SOAP
ms.assetid: 87329299-c2ea-4517-9148-d855726768a9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e88a164602f9bbe6ad42c3897285a484cac94466
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739218"
---
# <a name="using-secure-web-service-methods"></a><span data-ttu-id="3c31a-102">Использование защищенных методов веб-службы</span><span class="sxs-lookup"><span data-stu-id="3c31a-102">Using Secure Web Service Methods</span></span>
  <span data-ttu-id="3c31a-103">При вызове некоторых из методов веб-служб сервера отчетов может потребоваться наличие безопасного соединения.</span><span class="sxs-lookup"><span data-stu-id="3c31a-103">Certain Report Server Web service methods may require a secure connection when you invoke them.</span></span> <span data-ttu-id="3c31a-104">То, для каких из методов требуется наличие безопасного соединения, определяется значением параметра `SecureConnectionLevel` в файле RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="3c31a-104">The methods that require a secure connection are determined by the `SecureConnectionLevel` setting in the RSReportServer.config file.</span></span> <span data-ttu-id="3c31a-105">Значение этого параметра должно быть целым числом и находиться в диапазоне от 0 и выше.</span><span class="sxs-lookup"><span data-stu-id="3c31a-105">The value of the setting is an integer value with a valid range of 0 and higher.</span></span> <span data-ttu-id="3c31a-106">Данные значения описываются в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="3c31a-106">The following table describes these values.</span></span>  
  
|<span data-ttu-id="3c31a-107">Level</span><span class="sxs-lookup"><span data-stu-id="3c31a-107">Level</span></span>|<span data-ttu-id="3c31a-108">Описание</span><span class="sxs-lookup"><span data-stu-id="3c31a-108">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3c31a-109">**0**</span><span class="sxs-lookup"><span data-stu-id="3c31a-109">**0**</span></span>|<span data-ttu-id="3c31a-110">Небезопасный.</span><span class="sxs-lookup"><span data-stu-id="3c31a-110">Not secure.</span></span> <span data-ttu-id="3c31a-111">Для вызовов к API SOAP служб Reporting Services не требуется безопасное соединение.</span><span class="sxs-lookup"><span data-stu-id="3c31a-111">Calls made to the Reporting Services SOAP API do not require a secure connection.</span></span>|  
|<span data-ttu-id="3c31a-112">Больше **0**</span><span class="sxs-lookup"><span data-stu-id="3c31a-112">Greater than **0**</span></span>|<span data-ttu-id="3c31a-113">Безопасный уровень.</span><span class="sxs-lookup"><span data-stu-id="3c31a-113">Secure.</span></span> <span data-ttu-id="3c31a-114">Для всех вызовов к API-интерфейсу SOAP служб Reporting Services необходимо наличие безопасного соединения.</span><span class="sxs-lookup"><span data-stu-id="3c31a-114">All calls made to the Reporting Services SOAP API require a secure connection.</span></span>|  
  
 <span data-ttu-id="3c31a-115">Метод <xref:ReportExecution2005.ReportExecutionService.ListSecureMethods%2A> веб-службы можно использовать для возвращения списка всех методов веб-службы, для которых необходимо наличие безопасного соединения, в соответствии с текущей конфигурацией сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="3c31a-115">You can use the <xref:ReportExecution2005.ReportExecutionService.ListSecureMethods%2A> method of the Web service to return a list of Web service methods that require a secure connection according to the current configuration of the report server.</span></span> <span data-ttu-id="3c31a-116">При работе с SSL пользователю необходимо оценить список методов, возвращаемых методом <xref:ReportExecution2005.ReportExecutionService.ListSecureMethods%2A>, и изменить имя схемы URI веб-службы на «https» или «http» в зависимости от вызываемого метода.</span><span class="sxs-lookup"><span data-stu-id="3c31a-116">In an SSL scenario, you should evaluate the list of methods that are returned by <xref:ReportExecution2005.ReportExecutionService.ListSecureMethods%2A> and change the scheme name of the Web service URI to "https" or "http" depending on the method being called.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c31a-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="3c31a-117">See Also</span></span>  
 <span data-ttu-id="3c31a-118">[Создание приложений с помощью веб-службы и .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="3c31a-118">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 [<span data-ttu-id="3c31a-119">Веб-службы сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="3c31a-119">Report Server Web Service</span></span>](../report-server-web-service.md)  
  
  
