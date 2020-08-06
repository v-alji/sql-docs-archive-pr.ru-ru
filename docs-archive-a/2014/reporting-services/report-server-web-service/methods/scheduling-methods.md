---
title: Методы планирования | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- schedules [Reporting Services], methods
- reports [Reporting Services], scheduling
- shared schedules [Reporting Services], methods
- methods [Reporting Services], scheduling
ms.assetid: 68ae13f9-d91e-4572-a82a-8fa42001569e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 735da4f22d523fd40dd031f55e203fa9a4204f5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656142"
---
# <a name="scheduling-methods"></a><span data-ttu-id="cf75c-102">Методы планирования</span><span class="sxs-lookup"><span data-stu-id="cf75c-102">Scheduling Methods</span></span>
  <span data-ttu-id="cf75c-103">Можно использовать эти методы для создания и управления общими расписаниями выполнения и доставки отчета, а также кэшировать планы обновления, используемые сервером отчетов.</span><span class="sxs-lookup"><span data-stu-id="cf75c-103">You can use these methods to create and manage shared schedules for report execution and delivery, and to cache refresh plans utilized by the report server.</span></span>  
  
|<span data-ttu-id="cf75c-104">Метод</span><span class="sxs-lookup"><span data-stu-id="cf75c-104">Method</span></span>|<span data-ttu-id="cf75c-105">Действие</span><span class="sxs-lookup"><span data-stu-id="cf75c-105">Action</span></span>|  
|------------|------------|  
|<xref:ReportService2010.ReportingService2010.CreateCacheRefreshPlan%2A>|<span data-ttu-id="cf75c-106">Создает план обновления кэша для элемента.</span><span class="sxs-lookup"><span data-stu-id="cf75c-106">Creates a cache refresh plan for an item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.CreateSchedule%2A>|<span data-ttu-id="cf75c-107">Создание нового общего расписания.</span><span class="sxs-lookup"><span data-stu-id="cf75c-107">Creates a new shared schedule.</span></span>|  
|<xref:ReportService2010.ReportingService2010.DeleteCacheRefreshPlan%2A>|<span data-ttu-id="cf75c-108">Удаляет план обновления кэша.</span><span class="sxs-lookup"><span data-stu-id="cf75c-108">Deletes a cache refresh plan.</span></span>|  
|<xref:ReportService2010.ReportingService2010.DeleteSchedule%2A>|<span data-ttu-id="cf75c-109">Удаление общего расписания по определенному идентификатору расписания.</span><span class="sxs-lookup"><span data-stu-id="cf75c-109">Deletes a shared schedule based on a specific schedule ID.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetCacheRefreshPlanProperties%2A>|<span data-ttu-id="cf75c-110">Возвращает свойства указанного плана обновления кэша.</span><span class="sxs-lookup"><span data-stu-id="cf75c-110">Returns the properties of the specified cache refresh plan.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetScheduleProperties%2A>|<span data-ttu-id="cf75c-111">Возвращение значений свойств общего расписания.</span><span class="sxs-lookup"><span data-stu-id="cf75c-111">Returns the values of properties of a shared schedule.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListCacheRefreshPlans%2A>|<span data-ttu-id="cf75c-112">Возвращает список планов обновления кэша, связанный с элементом каталога.</span><span class="sxs-lookup"><span data-stu-id="cf75c-112">Returns a list of the cache refresh plans associated with a catalog item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListScheduledItems%2A>|<span data-ttu-id="cf75c-113">Возвращает список элементов, связанных с общим расписанием.</span><span class="sxs-lookup"><span data-stu-id="cf75c-113">Returns a list of items that are associated with a shared schedule.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListSchedules%2A>|<span data-ttu-id="cf75c-114">Возвращает список всех общих расписаний на сервер отчетов или на сайт SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cf75c-114">Returns a list of all shared schedules at the report server or the SharePoint site.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListScheduleStates%2A>|<span data-ttu-id="cf75c-115">Возвращает список поддерживаемых режимов расписания.</span><span class="sxs-lookup"><span data-stu-id="cf75c-115">Returns a list of supported schedule states.</span></span>|  
|<xref:ReportService2010.ReportingService2010.PauseSchedule%2A>|<span data-ttu-id="cf75c-116">Приостанавливает выполнение данного расписания.</span><span class="sxs-lookup"><span data-stu-id="cf75c-116">Pauses the execution of a given schedule.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ResumeSchedule%2A>|<span data-ttu-id="cf75c-117">Продолжение приостановленного общего расписания.</span><span class="sxs-lookup"><span data-stu-id="cf75c-117">Resumes a shared schedule that has been paused.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetCacheRefreshPlanProperties%2A>|<span data-ttu-id="cf75c-118">Задает свойства плана обновления кэша.</span><span class="sxs-lookup"><span data-stu-id="cf75c-118">Sets the properties of a cache refresh plan.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetScheduleProperties%2A>|<span data-ttu-id="cf75c-119">Задание значений свойств общего расписания.</span><span class="sxs-lookup"><span data-stu-id="cf75c-119">Sets the value of properties of a shared schedule.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cf75c-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="cf75c-120">See Also</span></span>  
 <span data-ttu-id="cf75c-121">[Создание приложений с помощью веб-службы и .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="cf75c-121">[Building Applications Using the Web Service and the .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="cf75c-122">[Веб-служба сервера отчетов](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="cf75c-122">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 <span data-ttu-id="cf75c-123">[Методы веб-службы сервера отчетов](report-server-web-service-methods.md) </span><span class="sxs-lookup"><span data-stu-id="cf75c-123">[Report Server Web Service Methods](report-server-web-service-methods.md) </span></span>  
 [<span data-ttu-id="cf75c-124">Технический справочник (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="cf75c-124">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
