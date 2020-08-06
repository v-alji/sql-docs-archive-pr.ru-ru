---
title: Методы отрисовки и выполнения | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- rendered reports [Reporting Services]
- reports [Reporting Services], execution options
- methods [Reporting Services], execution options
- methods [Reporting Services], rendering
ms.assetid: 12626aad-f0be-4653-87d0-60eb3a3fff78
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d0bc793e9a18e993989563fd3526ff12272f775c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736026"
---
# <a name="rendering-and-execution-methods"></a><span data-ttu-id="735bf-102">Методы подготовки к просмотру и выполнения</span><span class="sxs-lookup"><span data-stu-id="735bf-102">Rendering and Execution Methods</span></span>
  <span data-ttu-id="735bf-103">Эти методы можно использовать для управления выполнением и кэшированием элементов и подготовкой отчетов к просмотру.</span><span class="sxs-lookup"><span data-stu-id="735bf-103">You can use these methods to manage item execution and caching, and report rendering.</span></span>  
  
|<span data-ttu-id="735bf-104">Метод</span><span class="sxs-lookup"><span data-stu-id="735bf-104">Method</span></span>|<span data-ttu-id="735bf-105">Действие</span><span class="sxs-lookup"><span data-stu-id="735bf-105">Action</span></span>|  
|------------|------------|  
|<xref:ReportService2010.ReportingService2010.FlushCache%2A>|<span data-ttu-id="735bf-106">Делает недействительным кэш для элемента.</span><span class="sxs-lookup"><span data-stu-id="735bf-106">Invalidates the cache for an item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetCacheOptions%2A>|<span data-ttu-id="735bf-107">Возвращает конфигурацию кэширования для элемента и параметры, которые описывают, когда истекает срок действия кэшированной копии элемента.</span><span class="sxs-lookup"><span data-stu-id="735bf-107">Returns the cache configuration for an item and the settings that describe when the cached copy of the item expires.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetExecutionOptions%2A>|<span data-ttu-id="735bf-108">Возвращает параметр выполнения и соответствующие настройки для отдельного элемента.</span><span class="sxs-lookup"><span data-stu-id="735bf-108">Returns the execution option and associated settings for an individual item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListExecutionSettings%2A>|<span data-ttu-id="735bf-109">Возвращает список поддерживаемых настроек выполнения.</span><span class="sxs-lookup"><span data-stu-id="735bf-109">Returns a list of supported execution settings.</span></span>|  
|<xref:ReportExecution2005.ReportExecutionService.Render%2A>|<span data-ttu-id="735bf-110">Обрабатывает указанный отчет и готовит его к просмотру в заданном формате.</span><span class="sxs-lookup"><span data-stu-id="735bf-110">Processes the specified report and renders it in a specified format.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetCacheOptions%2A>|<span data-ttu-id="735bf-111">Настраивает элемент для кэширования и предоставляет настройки, указывающие, когда истекает срок действия кэшированной копии элемента.</span><span class="sxs-lookup"><span data-stu-id="735bf-111">Configures an item to be cached and provides settings that specify when the cached copy of the item expires.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetExecutionOptions%2A>|<span data-ttu-id="735bf-112">Устанавливает параметры выполнения и соответствующие свойства выполнения для указанного элемента.</span><span class="sxs-lookup"><span data-stu-id="735bf-112">Sets execution options and associated execution properties for a specified item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.UpdateItemExecutionSnapshot%2A>|<span data-ttu-id="735bf-113">Создает моментальный снимок состояния выполнения элемента для указанного элемента.</span><span class="sxs-lookup"><span data-stu-id="735bf-113">Generates an item execution snapshot for a specified item.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="735bf-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="735bf-114">See Also</span></span>  
 <span data-ttu-id="735bf-115">[Создание приложений с помощью веб-службы и .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="735bf-115">[Building Applications Using the Web Service and the .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="735bf-116">[Веб-служба сервера отчетов](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="735bf-116">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 <span data-ttu-id="735bf-117">[Методы веб-службы сервера отчетов](report-server-web-service-methods.md) </span><span class="sxs-lookup"><span data-stu-id="735bf-117">[Report Server Web Service Methods](report-server-web-service-methods.md) </span></span>  
 [<span data-ttu-id="735bf-118">Технический справочник (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="735bf-118">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
