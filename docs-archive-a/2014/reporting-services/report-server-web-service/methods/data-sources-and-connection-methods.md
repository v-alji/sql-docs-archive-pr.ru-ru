---
title: Источники данных и способы подключения | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- connections [Reporting Services], data sources
- reports [Reporting Services], data
- data sources [Reporting Services], methods
ms.assetid: 50999b52-fc7c-4333-9fb0-d04c37a4c90f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 29dd8dd1c002ab3b7d4594a4e25ec44bdb2cc8ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736041"
---
# <a name="data-sources-and-connection-methods"></a><span data-ttu-id="ae3e3-102">Источники данных и методы соединения</span><span class="sxs-lookup"><span data-stu-id="ae3e3-102">Data Sources and Connection Methods</span></span>
  <span data-ttu-id="ae3e3-103">Эти методы можно использовать для установления и управления соединениями с источниками данных, а также учетными данными.</span><span class="sxs-lookup"><span data-stu-id="ae3e3-103">You can use these methods to set and manage data source connections and credentials.</span></span>  
  
|<span data-ttu-id="ae3e3-104">Метод</span><span class="sxs-lookup"><span data-stu-id="ae3e3-104">Method</span></span>|<span data-ttu-id="ae3e3-105">Действие</span><span class="sxs-lookup"><span data-stu-id="ae3e3-105">Action</span></span>|  
|------------|------------|  
|<xref:ReportService2010.ReportingService2010.CreateDataSource%2A>|<span data-ttu-id="ae3e3-106">Создает новый источник данных в базе данных сервера отчетов или библиотеке SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ae3e3-106">Creates a new data source in the report server database or SharePoint library.</span></span>|  
|<xref:ReportService2010.ReportingService2010.DisableDataSource%2A>|<span data-ttu-id="ae3e3-107">Отключает включенный источник данных.</span><span class="sxs-lookup"><span data-stu-id="ae3e3-107">Disables a data source that is enabled.</span></span>|  
|<xref:ReportService2010.ReportingService2010.EnableDataSource%2A>|<span data-ttu-id="ae3e3-108">Включает отключенный источник данных.</span><span class="sxs-lookup"><span data-stu-id="ae3e3-108">Enables a data source that is disabled.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetDataSourceContents%2A>|<span data-ttu-id="ae3e3-109">Возвращает содержимое источника данных.</span><span class="sxs-lookup"><span data-stu-id="ae3e3-109">Returns the contents of a data source.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetItemDataSourcePrompts%2A>|<span data-ttu-id="ae3e3-110">Возвращает подсказку источника данных для указанного элемента.</span><span class="sxs-lookup"><span data-stu-id="ae3e3-110">Gets the data source prompts for a specified item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetItemDataSources%2A>|<span data-ttu-id="ae3e3-111">Возвращает источники данных для элемента в каталоге.</span><span class="sxs-lookup"><span data-stu-id="ae3e3-111">Returns the data sources for an item in the catalog.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListDependentItems%2A>|<span data-ttu-id="ae3e3-112">Возвращает список элементов каталога, который ссылается на указанный элемент каталога.</span><span class="sxs-lookup"><span data-stu-id="ae3e3-112">Returns a list of catalog items that reference a specified catalog item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListSubscriptionsUsingDataSource%2A>|<span data-ttu-id="ae3e3-113">Возвращает список подписок, связанных с данным источником данных.</span><span class="sxs-lookup"><span data-stu-id="ae3e3-113">Returns a list of subscriptions that are associated with a given data source.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetDataSourceContents%2A>|<span data-ttu-id="ae3e3-114">Задает свойства соединения, связанные с источником данных.</span><span class="sxs-lookup"><span data-stu-id="ae3e3-114">Sets the connection properties that are associated with a data source.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetItemDataSources%2A>|<span data-ttu-id="ae3e3-115">Задает источники данных для элемента в базе данных сервера отчетов или библиотеке SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ae3e3-115">Sets the data sources for an item in a report server database or SharePoint library.</span></span>|  
|<xref:ReportService2010.ReportingService2010.TestConnectForDataSourceDefinition%2A>|<span data-ttu-id="ae3e3-116">Проверяет соединение с источником данных.</span><span class="sxs-lookup"><span data-stu-id="ae3e3-116">Tests the connection for a data source.</span></span> <span data-ttu-id="ae3e3-117">Этот метод поддерживает непосредственную проверку источника данных.</span><span class="sxs-lookup"><span data-stu-id="ae3e3-117">This method supports the direct testing of the data source.</span></span>|  
|<xref:ReportService2010.ReportingService2010.TestConnectForItemDataSource%2A>|<span data-ttu-id="ae3e3-118">Проверяет соединение с источником данных.</span><span class="sxs-lookup"><span data-stu-id="ae3e3-118">Tests the connection for a data source.</span></span> <span data-ttu-id="ae3e3-119">Этот метод поддерживает проверку опубликованных источников данных, используемых отчетами или моделями и общими источниками данных.</span><span class="sxs-lookup"><span data-stu-id="ae3e3-119">This method supports the testing of published data sources that are used by reports or models and shared data sources.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ae3e3-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="ae3e3-120">See Also</span></span>  
 <span data-ttu-id="ae3e3-121">[Создание приложений с помощью веб-службы и .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="ae3e3-121">[Building Applications Using the Web Service and the .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="ae3e3-122">[Веб-служба сервера отчетов](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="ae3e3-122">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 <span data-ttu-id="ae3e3-123">[Методы веб-службы сервера отчетов](report-server-web-service-methods.md) </span><span class="sxs-lookup"><span data-stu-id="ae3e3-123">[Report Server Web Service Methods](report-server-web-service-methods.md) </span></span>  
 [<span data-ttu-id="ae3e3-124">Технический справочник (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="ae3e3-124">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
