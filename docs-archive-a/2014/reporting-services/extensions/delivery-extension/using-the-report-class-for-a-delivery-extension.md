---
title: Использование класса Report в модуле доставки | Документы Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- delivery extensions [Reporting Services], report information
- Report class
ms.assetid: 1145ac63-eafd-452a-82af-16f85b1676dd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a3f750c2383253636db255cbe9f1ce0ee676a9d9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669290"
---
# <a name="using-the-report-class-for-a-delivery-extension"></a><span data-ttu-id="39de4-102">Использование класса Report в модуле доставки</span><span class="sxs-lookup"><span data-stu-id="39de4-102">Using the Report Class for a Delivery Extension</span></span>
  <span data-ttu-id="39de4-103">Класс <xref:Microsoft.ReportingServices.Interfaces.Report> представляет отчет в базе данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="39de4-103">The <xref:Microsoft.ReportingServices.Interfaces.Report> class represents a report in the report server database.</span></span> <span data-ttu-id="39de4-104">Каждая подписка связывается с определенным отчетом.</span><span class="sxs-lookup"><span data-stu-id="39de4-104">Any subscription is associated with a specific report.</span></span> <span data-ttu-id="39de4-105">Отчет содержится в уведомлении.</span><span class="sxs-lookup"><span data-stu-id="39de4-105">The report is contained in the notification.</span></span> <span data-ttu-id="39de4-106">Модули доставки могут использовать объект <xref:Microsoft.ReportingServices.Interfaces.Report>, являющийся частью уведомления, для подготовки отчета к просмотру.</span><span class="sxs-lookup"><span data-stu-id="39de4-106">Your delivery extension can use the <xref:Microsoft.ReportingServices.Interfaces.Report> object that is part of the notification to render the report.</span></span> <span data-ttu-id="39de4-107">Объект <xref:Microsoft.ReportingServices.Interfaces.Report> также содержит свойства, относящиеся к отчету, такие как URL-адреса отчета на сервере отчетов и имя отчета.</span><span class="sxs-lookup"><span data-stu-id="39de4-107">The <xref:Microsoft.ReportingServices.Interfaces.Report> object also contains report-specific properties, such as the URL to the report on the report server and the name of the report.</span></span> <span data-ttu-id="39de4-108">Все эти свойства можно использовать в составе поставщика доставки.</span><span class="sxs-lookup"><span data-stu-id="39de4-108">These properties can all be used as part of your delivery provider.</span></span>  
  
 <span data-ttu-id="39de4-109">Метод <xref:Microsoft.ReportingServices.Interfaces.Report.Render%2A> класса <xref:Microsoft.ReportingServices.Interfaces.Report> используется для подготовки отчета к просмотру.</span><span class="sxs-lookup"><span data-stu-id="39de4-109">The <xref:Microsoft.ReportingServices.Interfaces.Report.Render%2A> method of the <xref:Microsoft.ReportingServices.Interfaces.Report> class can be used to render a report.</span></span> <span data-ttu-id="39de4-110">Метод <xref:Microsoft.ReportingServices.Interfaces.Report.Render%2A> возвращает массив из одного или нескольких объектов <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile>, которые в совокупности представляют отдельный отчет, готовый для просмотра.</span><span class="sxs-lookup"><span data-stu-id="39de4-110">The <xref:Microsoft.ReportingServices.Interfaces.Report.Render%2A> method returns an array of one or more <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> objects that together comprise a single rendered report.</span></span> <span data-ttu-id="39de4-111">Первым объектом <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> является отчет, готовый для просмотра.</span><span class="sxs-lookup"><span data-stu-id="39de4-111">The first <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> object is the rendered report.</span></span> <span data-ttu-id="39de4-112">Все другие объекты <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> представляют ресурсы, которые необходимо доставить вместе с данными отчета (например, HTML-файл и связанные изображения).</span><span class="sxs-lookup"><span data-stu-id="39de4-112">Any other <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> objects are resources that must be delivered along with the report data (for example, an HTML file and associated images).</span></span> <span data-ttu-id="39de4-113">Однопоточные модули подготовки отчетов (IMAGE, PDF, MHTML и Excel) возвращают в массиве только один объект <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile>.</span><span class="sxs-lookup"><span data-stu-id="39de4-113">Rendering extensions that are single-stream rendering extensions (IMAGE, PDF, MHTML, and Excel) return only one <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> object in the array.</span></span>  
  
 <span data-ttu-id="39de4-114">В доставку можно включить объект <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile>, содержащий поток отчета.</span><span class="sxs-lookup"><span data-stu-id="39de4-114">The <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> object, which contains the report stream, can be included as part of a delivery.</span></span>  
  
 <span data-ttu-id="39de4-115">Пример использования класса <xref:Microsoft.ReportingServices.Interfaces.Report> см. в разделе [Образцы продуктов служб SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="39de4-115">For an example of how to use the <xref:Microsoft.ReportingServices.Interfaces.Report> class, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39de4-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="39de4-116">See Also</span></span>  
 <span data-ttu-id="39de4-117">[Реализация модуля доставки](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="39de4-117">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 <span data-ttu-id="39de4-118">[Библиотека модулей Reporting Services](../reporting-services-extension-library.md) </span><span class="sxs-lookup"><span data-stu-id="39de4-118">[Reporting Services Extension Library](../reporting-services-extension-library.md) </span></span>  
 [<span data-ttu-id="39de4-119">Использование класса RenderedOutputFile для модуля доставки</span><span class="sxs-lookup"><span data-stu-id="39de4-119">Using the RenderedOutputFile Class for a Delivery Extension</span></span>](using-the-renderedoutputfile-class-for-a-delivery-extension.md)  
  
  
