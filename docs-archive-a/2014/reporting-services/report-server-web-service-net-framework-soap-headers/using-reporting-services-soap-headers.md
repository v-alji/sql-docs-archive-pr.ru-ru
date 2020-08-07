---
title: Использование заголовков SOAP служб Reporting Services | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Web service [Reporting Services], SOAP
- Report Server Web service, SOAP
- SOAP headers [Reporting Services]
- SOAP [Reporting Services], headers
- XML Web service [Reporting Services], SOAP
ms.assetid: 306d2c06-a25a-40f8-8a35-13dd32e8841e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f48be183398d4d441b5781c9f9467178c3011e32
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733557"
---
# <a name="using-reporting-services-soap-headers"></a><span data-ttu-id="23232-102">Использование заголовков SOAP служб Reporting Services</span><span class="sxs-lookup"><span data-stu-id="23232-102">Using Reporting Services SOAP Headers</span></span>
  <span data-ttu-id="23232-103">Связь с методом веб-службы по протоколу SOAP имеет стандартный формат.</span><span class="sxs-lookup"><span data-stu-id="23232-103">Communication with a Web service method using SOAP follows a standard format.</span></span> <span data-ttu-id="23232-104">Данные, закодированные в XML-документе, являются частью этого формата.</span><span class="sxs-lookup"><span data-stu-id="23232-104">Part of this format is the data that is encoded in an XML document.</span></span> <span data-ttu-id="23232-105">XML-документ состоит из корневого элемента **Envelope**, который в свою очередь состоит из обязательного элемента **Body** и дополнительного элемента **Header**.</span><span class="sxs-lookup"><span data-stu-id="23232-105">The XML document consists of a root **Envelope** element, which in turn consists of a required **Body** element and an optional **Header** element.</span></span> <span data-ttu-id="23232-106">Элемент **Body** содержит данные, соответствующие сообщению.</span><span class="sxs-lookup"><span data-stu-id="23232-106">The **Body** element contains the data specific to the message.</span></span> <span data-ttu-id="23232-107">Необязательный элемент **Header** может содержать дополнительную информацию, не связанную напрямую с конкретным сообщением.</span><span class="sxs-lookup"><span data-stu-id="23232-107">The optional **Header** element can contain additional information not directly related to the particular message.</span></span> <span data-ttu-id="23232-108">Каждый дочерний элемент **Header** называется заголовком SOAP.</span><span class="sxs-lookup"><span data-stu-id="23232-108">Each child element of the **Header** element is called a SOAP header.</span></span>  
  
 <span data-ttu-id="23232-109">Несмотря на то что заголовки SOAP могут содержать данные, связанные с сообщением, они в основном содержат информацию, обрабатываемую инфраструктурой веб-сервера.</span><span class="sxs-lookup"><span data-stu-id="23232-109">Although the SOAP headers can contain data related to the message, they typically contain information processed by the Web server infrastructure.</span></span>  
  
 <span data-ttu-id="23232-110">Веб-службы сервера отчетов определяют несколько классов для использования в заголовке SOAP: <xref:ReportService2005.BatchHeader>, <xref:ReportService2010.ItemNamespaceHeader>, <xref:ReportService2010.ServerInfoHeader>, <xref:ReportService2010.TrustedUserHeader> и <xref:ReportExecution2005.ExecutionHeader>.</span><span class="sxs-lookup"><span data-stu-id="23232-110">The Report Server Web services define several classes for use in the SOAP header: <xref:ReportService2005.BatchHeader>, <xref:ReportService2010.ItemNamespaceHeader>, <xref:ReportService2010.ServerInfoHeader>, <xref:ReportService2010.TrustedUserHeader>, and <xref:ReportExecution2005.ExecutionHeader>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="23232-111">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="23232-111">In This Section</span></span>  
  
|<span data-ttu-id="23232-112">Раздел</span><span class="sxs-lookup"><span data-stu-id="23232-112">Topic</span></span>|<span data-ttu-id="23232-113">Описание</span><span class="sxs-lookup"><span data-stu-id="23232-113">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="23232-114">Методы пакетной работы</span><span class="sxs-lookup"><span data-stu-id="23232-114">Batching Methods</span></span>](batching-methods.md)|<span data-ttu-id="23232-115">Описывает, как объединять в пакет несколько операций в одну транзакцию с помощью класса <xref:ReportService2005.BatchHeader>.</span><span class="sxs-lookup"><span data-stu-id="23232-115">Describes how to batch multiple operations into a single transaction using <xref:ReportService2005.BatchHeader>.</span></span>|  
|[<span data-ttu-id="23232-116">Определение состояния выполнения</span><span class="sxs-lookup"><span data-stu-id="23232-116">Identifying Execution State</span></span>](identifying-execution-state.md)|<span data-ttu-id="23232-117">Описывает, как управлять состоянием сеанса в службах [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] с помощью **SessionHeader**.</span><span class="sxs-lookup"><span data-stu-id="23232-117">Describes how to manage session state in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] using **SessionHeader**.</span></span>|  
|[<span data-ttu-id="23232-118">Задание пространства имен элементов для метода GetProperties</span><span class="sxs-lookup"><span data-stu-id="23232-118">Setting the Item Namespace for the GetProperties Method</span></span>](setting-the-item-namespace-for-the-getproperties-method.md)|<span data-ttu-id="23232-119">Описывает, как получить свойства, основанные либо на пути, либо на идентификаторе элемента, используя метод <xref:ReportService2010.ReportingService2010.GetProperties%2A> и заголовок SOAP <xref:ReportService2010.ItemNamespaceHeader>.</span><span class="sxs-lookup"><span data-stu-id="23232-119">Describes how to retrieve properties based on either the path or the ID of an item by using the <xref:ReportService2010.ReportingService2010.GetProperties%2A> method and the <xref:ReportService2010.ItemNamespaceHeader> SOAP header.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="23232-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="23232-120">See Also</span></span>  
 <span data-ttu-id="23232-121">[Создание приложений с помощью веб-службы и .NET Framework](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="23232-121">[Building Applications Using the Web Service and the .NET Framework](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 [<span data-ttu-id="23232-122">Технический справочник (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="23232-122">Technical Reference &#40;SSRS&#41;</span></span>](../technical-reference-ssrs.md)  
  
  
