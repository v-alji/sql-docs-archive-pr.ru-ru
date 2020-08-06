---
title: Свойства служб Reporting Services | Документы Майкрософт
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- report servers [Reporting Services], properties
- properties [Reporting Services], about properties
- reports [Reporting Services], properties
- Report Server Web service, properties
- report properties [Reporting Services]
- XML Web service [Reporting Services], properties
- Web service [Reporting Services], properties
- properties [Reporting Services]
ms.assetid: 8c855194-4c20-4ecc-a328-5137d54b560c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 61f1f50ea7a49acc616a36a4eaf1d3d5fcdf269a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730105"
---
# <a name="reporting-services-properties"></a><span data-ttu-id="45b48-102">Свойства служб Reporting Services</span><span class="sxs-lookup"><span data-stu-id="45b48-102">Reporting Services Properties</span></span>
  <span data-ttu-id="45b48-103">Сервер отчетов определяет набор системных свойств, являющихся глобальными для сервера отчетов, и набор свойств элементов, связанных с отдельным элементом, хранимым в базе данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="45b48-103">The report server defines a set of system properties that are global to the report server and a set of item properties that are associated with an individual item stored in the report server database.</span></span> <span data-ttu-id="45b48-104">Свойства, определенные сервером отчетов, не могут быть удалены; в некоторых случаях они доступны только для чтения.</span><span class="sxs-lookup"><span data-stu-id="45b48-104">Properties defined by the report server cannot be deleted, and in some cases they are read-only.</span></span> <span data-ttu-id="45b48-105">Приложение может расширить системные свойства и свойства элементов, добавив к ним дополнительные определяемые пользователем свойства.</span><span class="sxs-lookup"><span data-stu-id="45b48-105">An application can extend system properties and item properties by adding additional user-defined properties to the system and item properties.</span></span>  
  
 <span data-ttu-id="45b48-106">Следующие методы веб-службы извлекают и задают [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Свойства.</span><span class="sxs-lookup"><span data-stu-id="45b48-106">The following Web service methods retrieve and set [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] properties.</span></span>  
  
|<span data-ttu-id="45b48-107">Метод</span><span class="sxs-lookup"><span data-stu-id="45b48-107">Method</span></span>|<span data-ttu-id="45b48-108">Действие</span><span class="sxs-lookup"><span data-stu-id="45b48-108">Action</span></span>|  
|------------|------------|  
|<xref:ReportService2010.ReportingService2010.GetProperties%2A>|<span data-ttu-id="45b48-109">Возвращает значения одного или нескольких свойств элемента в базе данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="45b48-109">Returns the values of one or more properties on an item in the report server database.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetSystemProperties%2A>|<span data-ttu-id="45b48-110">Возвращает одно или несколько системных свойств.</span><span class="sxs-lookup"><span data-stu-id="45b48-110">Returns one or more system properties.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetProperties%2A>|<span data-ttu-id="45b48-111">Задает одно или несколько свойств элемента в базе данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="45b48-111">Sets one or more properties of an item in the report server database.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetSystemProperties%2A>|<span data-ttu-id="45b48-112">Задает одно или несколько системных свойств.</span><span class="sxs-lookup"><span data-stu-id="45b48-112">Sets one or more system properties.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="45b48-113">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="45b48-113">In This Section</span></span>  
  
|<span data-ttu-id="45b48-114">Раздел</span><span class="sxs-lookup"><span data-stu-id="45b48-114">Topic</span></span>|<span data-ttu-id="45b48-115">Описание</span><span class="sxs-lookup"><span data-stu-id="45b48-115">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="45b48-116">Свойства элемента сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="45b48-116">Report Server Item Properties</span></span>](reporting-services-properties-report-server-item-properties.md)|<span data-ttu-id="45b48-117">Описывает характерные для элементов свойства в службах [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="45b48-117">Describes the item-specific properties in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="45b48-118">Системные свойства сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="45b48-118">Report Server System Properties</span></span>](reporting-services-properties-report-server-system-properties.md)|<span data-ttu-id="45b48-119">Описывает характерные для системы свойства в службах [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="45b48-119">Describes the system-specific properties in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="45b48-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="45b48-120">See Also</span></span>  
 <span data-ttu-id="45b48-121">[Создание приложений с помощью веб-службы и .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="45b48-121">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="45b48-122">[Веб-служба сервера отчетов](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="45b48-122">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 [<span data-ttu-id="45b48-123">Технический справочник (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="45b48-123">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
