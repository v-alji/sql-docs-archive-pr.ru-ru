---
title: Использование класса RenderedOutputFile для модуля доставки | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- RenderedOutputFile class
- data streams [Reporting Services]
- delivery extensions [Reporting Services], data streams
ms.assetid: 8b591801-42d5-49fa-b710-bf7e6917accf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1dcbf250a367326e5cad528384e533a9ac9d945b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669293"
---
# <a name="using-the-renderedoutputfile-class-for-a-delivery-extension"></a><span data-ttu-id="5517d-102">Использование класса RenderedOutputFile для модуля доставки</span><span class="sxs-lookup"><span data-stu-id="5517d-102">Using the RenderedOutputFile Class for a Delivery Extension</span></span>
  <span data-ttu-id="5517d-103">Класс <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> представляет поток данных и сведения о свойствах, связанных с ним.</span><span class="sxs-lookup"><span data-stu-id="5517d-103">The <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> class represents a data stream and information about the data stream's associated properties.</span></span> <span data-ttu-id="5517d-104">Свойство **Data** класса <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> используется для представления подготовленного отчета или ресурса отчета в качестве объекта **Stream**.</span><span class="sxs-lookup"><span data-stu-id="5517d-104">The **Data** property of the <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> class is used to represent a rendered report or report resource as a **Stream** object.</span></span>  
  
 <span data-ttu-id="5517d-105">Метод <xref:Microsoft.ReportingServices.Interfaces.Report.Render%2A> объекта **Report** возвращает массив из одного или нескольких объектов <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile>, которые вместе составляют единый подготовленный отчет.</span><span class="sxs-lookup"><span data-stu-id="5517d-105">The <xref:Microsoft.ReportingServices.Interfaces.Report.Render%2A> method of the **Report** object returns an array of one or more <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> objects that together constitute a single rendered report.</span></span> <span data-ttu-id="5517d-106">Первым объектом <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> является отчет, готовый для просмотра.</span><span class="sxs-lookup"><span data-stu-id="5517d-106">The first <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> object is the rendered report.</span></span> <span data-ttu-id="5517d-107">Все другие объекты <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> представляют ресурсы, которые необходимо доставить вместе с данными отчета (например, HTML-файл и связанные изображения).</span><span class="sxs-lookup"><span data-stu-id="5517d-107">Any other <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> objects are resources that must be delivered along with the report data (for example, an HTML file and associated images).</span></span> <span data-ttu-id="5517d-108">Однопоточные модули подготовки отчетов (IMAGE, PDF, MHTML и EXCEL) возвращают только один объект <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> в массиве.</span><span class="sxs-lookup"><span data-stu-id="5517d-108">Rendering extensions that are single-stream rendering extensions (IMAGE, PDF, MHTML, and EXCEL) return only one <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> object in the array.</span></span>  
  
 <span data-ttu-id="5517d-109">Пример использования класса <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> см. в разделе [Образцы продуктов служб SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="5517d-109">For an example of how to use the <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> class, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5517d-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="5517d-110">See Also</span></span>  
 <span data-ttu-id="5517d-111">[Реализация модуля доставки](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="5517d-111">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 [<span data-ttu-id="5517d-112">Библиотека модулей Reporting Services</span><span class="sxs-lookup"><span data-stu-id="5517d-112">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
