---
title: Использование программирования веб-части обозревателя в режиме интеграции с SharePoint | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
ms.assetid: 714017b7-1bd6-4950-a3c6-d0df8450a877
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 494ebc3e6668e4d95480019e522caf46b83a6c4d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734993"
---
# <a name="report-viewer-web-part-programmability-in-sharepoint-integration"></a><span data-ttu-id="8f860-102">Использование программирования веб-части обозревателя в интеграции с SharePoint</span><span class="sxs-lookup"><span data-stu-id="8f860-102">Report Viewer Web Part Programmability in SharePoint Integration</span></span>
  <span data-ttu-id="8f860-103">Веб-часть средства просмотра отчетов ― это серверный элемент управления `T:Microsoft.ReportingServices.SharePoint.UI.WebParts.ReportViewerWebPart`, который содержит набор открытых API, позволяющих разработчикам создавать пользовательские приложения SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8f860-103">The Report Viewer Web Part is a `T:Microsoft.ReportingServices.SharePoint.UI.WebParts.ReportViewerWebPart` server control, which contains a set of public application programming interfaces (API) that enables developers to create custom SharePoint applications.</span></span> <span data-ttu-id="8f860-104">Пользователь может создавать веб-части, предоставляющие путь к отчету и параметры для веб-части средства просмотра отчетов с помощью соединений веб-частей.</span><span class="sxs-lookup"><span data-stu-id="8f860-104">You can create custom Web Parts that supply report path and parameters to Report Viewer Web Part using Web Part connections.</span></span> <span data-ttu-id="8f860-105">Также можно внедрить веб-часть в пользовательскую страницу веб-части SharePoint и модифицировать ее с помощью открытого API-интерфейса.</span><span class="sxs-lookup"><span data-stu-id="8f860-105">You can also embed the Web Part in a custom SharePoint Web Part page and customize it using the public API.</span></span>  
  
## <a name="connecting-to-report-viewer-web-part-with-custom-web-parts"></a><span data-ttu-id="8f860-106">Соединение с веб-частью средства просмотра отчетов с пользовательскими веб-частями</span><span class="sxs-lookup"><span data-stu-id="8f860-106">Connecting to Report Viewer Web Part with Custom Web Parts</span></span>  
 <span data-ttu-id="8f860-107">Веб-часть средства просмотра отчетов ― это потребитель соединения с веб-частями SharePoint, реализующими интерфейс <xref:System.Web.UI.WebControls.WebParts.IWebPartRow> или `T:Microsoft.SharePoint.WebPartPages.IFilterValues`.</span><span class="sxs-lookup"><span data-stu-id="8f860-107">The Report Viewer Web Part is a connection consumer to SharePoint Web Parts that implement <xref:System.Web.UI.WebControls.WebParts.IWebPartRow> or `T:Microsoft.SharePoint.WebPartPages.IFilterValues`.</span></span> <span data-ttu-id="8f860-108">Веб-часть <xref:System.Web.UI.WebControls.WebParts.IWebPartRow>, например веб-часть **Документы**, может предоставлять веб-части средства просмотра отчетов путь к отчету, если она помещается на той же странице веб-части, что и веб-часть средства просмотра отчетов.</span><span class="sxs-lookup"><span data-stu-id="8f860-108">An <xref:System.Web.UI.WebControls.WebParts.IWebPartRow> Web Part, such as the **Documents** Web Part can supply a report path to a Report Viewer Web Part when placed on the same Web Part page as the Report Viewer Web Part.</span></span> <span data-ttu-id="8f860-109">Аналогично, `T:Microsoft.SharePoint.WebPartPages.IFilterValues` веб-часть, например **Фильтр текста** или **Фильтр выбора**, может предоставить параметр отчета веб-части средства просмотра отчетов, если она размещена на той же странице веб-части, что и веб-часть средства просмотра отчетов.</span><span class="sxs-lookup"><span data-stu-id="8f860-109">Likewise, an `T:Microsoft.SharePoint.WebPartPages.IFilterValues` Web Part, such as the **Text Filter** or the **Choice Filter**, can supply a report parameter to a Report Viewer Web Part when placed on the same Web Part page as the Report Viewer Web Part.</span></span>  
  
### <a name="implementing-a-report-path-provider-with-iwebpartrow"></a><span data-ttu-id="8f860-110">Реализация поставщика путей отчетов с интерфейсом IWebPartRow</span><span class="sxs-lookup"><span data-stu-id="8f860-110">Implementing a Report Path Provider with IWebPartRow</span></span>  
 <span data-ttu-id="8f860-111">Чтобы указать путь к отчету для веб-части средства просмотра отчетов через соединения веб-части, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="8f860-111">To supply a report path to the Report Viewer Web Part through Web Part connections, do the following:</span></span>  
  
1.  <span data-ttu-id="8f860-112">Создайте веб-часть, реализующую интерфейс <xref:System.Web.UI.WebControls.WebParts.IWebPartRow>.</span><span class="sxs-lookup"><span data-stu-id="8f860-112">Create a Web Part that implements the <xref:System.Web.UI.WebControls.WebParts.IWebPartRow> interface.</span></span>  
  
2.  <span data-ttu-id="8f860-113">Добавьте веб-часть на страницу веб-части, на которой расположена веб-часть средства просмотра отчетов.</span><span class="sxs-lookup"><span data-stu-id="8f860-113">Add the Web Part to the same Web Part page as the Report Viewer Web Part.</span></span>  
  
3.  <span data-ttu-id="8f860-114">Подключите веб-часть к веб-части средства просмотра отчетов в пользовательском интерфейсе проектирования веб-частей.</span><span class="sxs-lookup"><span data-stu-id="8f860-114">Connect your Web Part to the Report Viewer Web Part in the Web-based Web Part design user interface.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8f860-115">Можно подключить только одну веб-часть <xref:System.Web.UI.WebControls.WebParts.IWebPartRow> к веб-части средства просмотра отчетов одновременно, и нельзя подключить одновременно веб-часть <xref:System.Web.UI.WebControls.WebParts.IWebPartRow> и веб-часть `T:Microsoft.SharePoint.WebPartPages.IFilterValues` к веб-части средства просмотра отчетов.</span><span class="sxs-lookup"><span data-stu-id="8f860-115">You can only connect one <xref:System.Web.UI.WebControls.WebParts.IWebPartRow> Web Part to the Report Viewer Web Part at a time, and you cannot connect both an <xref:System.Web.UI.WebControls.WebParts.IWebPartRow> Web Part and an `T:Microsoft.SharePoint.WebPartPages.IFilterValues` Web Part to the Report Viewer Web Part at the same time.</span></span>  
  
 <span data-ttu-id="8f860-116">Чтобы веб-часть <xref:System.Web.UI.WebControls.WebParts.IWebPartRow> правильно работала с частью `T:Microsoft.ReportingServices.SharePoint.UI.WebParts.ReportViewerWebPart`, в методе <xref:System.Web.UI.WebControls.WebParts.IWebPartRow.GetRowData%2A> необходимо сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="8f860-116">For your <xref:System.Web.UI.WebControls.WebParts.IWebPartRow> Web Part to work properly with the `T:Microsoft.ReportingServices.SharePoint.UI.WebParts.ReportViewerWebPart`, you must do the following in the <xref:System.Web.UI.WebControls.WebParts.IWebPartRow.GetRowData%2A> method:</span></span>  
  
-   <span data-ttu-id="8f860-117">Вызовите метод обратного вызова при помощи объекта <xref:System.Data.DataRowView> в качестве параметра входа.</span><span class="sxs-lookup"><span data-stu-id="8f860-117">Invoke the callback method with a <xref:System.Data.DataRowView> object as the input parameter.</span></span>  
  
-   <span data-ttu-id="8f860-118">Убедитесь, что объект <xref:System.Data.DataRowView> содержит столбец «DocUrl», содержащий путь к отчету.</span><span class="sxs-lookup"><span data-stu-id="8f860-118">Make sure that the <xref:System.Data.DataRowView> object contains a column called "DocUrl" that contains the report path.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8f860-119">Веб-часть средства просмотра отчетов в надстройке для [!INCLUDE[offSPServ](../includes/offspserv-md.md)] 2010 также поддерживает получение сведений о пути к отчету через столбец «FileRef».</span><span class="sxs-lookup"><span data-stu-id="8f860-119">The Report Viewer Web Part in the add-in for [!INCLUDE[offSPServ](../includes/offspserv-md.md)] 2010 also supports receiving the report path using the "FileRef" column.</span></span>  
  
### <a name="implementing-a-report-parameter-provider-with-ifiltervalues"></a><span data-ttu-id="8f860-120">Реализация поставщика параметров отчета с интерфейсом IFilterValues</span><span class="sxs-lookup"><span data-stu-id="8f860-120">Implementing a Report Parameter Provider with IFilterValues</span></span>  
 <span data-ttu-id="8f860-121">Веб-часть, реализующая интерфейс `T:Microsoft.SharePoint.WebPartPages.IFilterValues`, может предоставлять одно значение параметра веб-части средства просмотра отчетов.</span><span class="sxs-lookup"><span data-stu-id="8f860-121">A Web Part that implements `T:Microsoft.SharePoint.WebPartPages.IFilterValues` can provide one parameter value to the Report Viewer Web Part.</span></span> <span data-ttu-id="8f860-122">Значение параметра, отправляемое веб-части средства просмотра отчетов, попадает под действие тех же ограничений, которые применяются к параметрам отчета в соответствии с определением отчета, включая тип данных, допустимые значения и т. п.</span><span class="sxs-lookup"><span data-stu-id="8f860-122">The parameter value sent to the Report Viewer Web Part is subject to the same restrictions placed on the report parameter as specified in the report definition, such as data type, valid values, and so on</span></span>  
  
 <span data-ttu-id="8f860-123">Чтобы указать параметр отчета для веб-части средства просмотра отчетов, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="8f860-123">To supply a report parameter to the Report Viewer Web Part, do the following:</span></span>  
  
1.  <span data-ttu-id="8f860-124">Создайте веб-часть, реализующую интерфейс `T:Microsoft.SharePoint.WebPartPages.IFilterValues`.</span><span class="sxs-lookup"><span data-stu-id="8f860-124">Create a Web Part that implements the `T:Microsoft.SharePoint.WebPartPages.IFilterValues` interface.</span></span>  
  
2.  <span data-ttu-id="8f860-125">Добавьте веб-часть на ту же страницу, где расположена веб-часть `T:Microsoft.ReportingServices.SharePoint.UI.WebParts.ReportViewerWebPart`</span><span class="sxs-lookup"><span data-stu-id="8f860-125">Add the Web Part to the same page as the `T:Microsoft.ReportingServices.SharePoint.UI.WebParts.ReportViewerWebPart`.</span></span>  
  
3.  <span data-ttu-id="8f860-126">Подключите веб-часть `T:Microsoft.SharePoint.WebPartPages.IFilterValues` к веб-части средства просмотра отчетов в пользовательском интерфейсе проектирования веб-частей.</span><span class="sxs-lookup"><span data-stu-id="8f860-126">Connect your `T:Microsoft.SharePoint.WebPartPages.IFilterValues` Web Part to the Report Viewer Web Part in the Web-based Web Part design user interface.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8f860-127">Можно подключить одновременно несколько веб-частей `T:Microsoft.SharePoint.WebPartPages.IFilterValues` к веб-части средства просмотра отчетов.</span><span class="sxs-lookup"><span data-stu-id="8f860-127">You can connect multiple `T:Microsoft.SharePoint.WebPartPages.IFilterValues` Web Parts to the Report Viewer Web Part at a time.</span></span> <span data-ttu-id="8f860-128">Однако нельзя одновременно подключить веб-часть <xref:System.Web.UI.WebControls.WebParts.IWebPartRow> и веб-часть `T:Microsoft.SharePoint.WebPartPages.IFilterValues` к веб-части средства просмотра отчетов.</span><span class="sxs-lookup"><span data-stu-id="8f860-128">However, you cannot connect both an <xref:System.Web.UI.WebControls.WebParts.IWebPartRow> Web Part and an `T:Microsoft.SharePoint.WebPartPages.IFilterValues` Web Part to the Report Viewer Web Part at the same time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f860-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="8f860-129">See Also</span></span>  
 <span data-ttu-id="8f860-130">[Интерфейс IFilterValues](https://msdn.microsoft.com/library/office/microsoft.sharepoint.webpartpages.ifiltervalues\(v=office.15\).aspx)</span><span class="sxs-lookup"><span data-stu-id="8f860-130">[IFilterValues interface](https://msdn.microsoft.com/library/office/microsoft.sharepoint.webpartpages.ifiltervalues\(v=office.15\).aspx)</span></span>  
  
  
