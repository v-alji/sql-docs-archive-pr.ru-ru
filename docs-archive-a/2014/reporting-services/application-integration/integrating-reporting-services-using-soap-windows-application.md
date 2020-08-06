---
title: Использование API SOAP в приложении Windows | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- rendered reports [Reporting Services]
- Windows applications [Reporting Services]
- Windows Forms [Reporting Services]
- SOAP [Reporting Services], Windows applications
ms.assetid: e4804792-20cd-4df2-9257-fb958ff447b4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 115ce02da69a8adb2c7a3de4175e528f281eb2b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654070"
---
# <a name="using-the-soap-api-in-a-windows-application"></a><span data-ttu-id="7f6ee-102">Использование API SOAP в приложении Windows</span><span class="sxs-lookup"><span data-stu-id="7f6ee-102">Using the SOAP API in a Windows Application</span></span>
  <span data-ttu-id="7f6ee-103">С помощью API SOAP служб Reporting Services можно получить доступ ко всем функциональным возможностям сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-103">You can access the full functionality of the report server through the Reporting Services SOAP API.</span></span> <span data-ttu-id="7f6ee-104">Поскольку API SOAP является веб-службой, к нему легко получить доступ, чтобы предоставить для пользовательских бизнес-приложений функции создания отчетов в масштабе предприятия.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-104">The SOAP API is a Web service and, as such, can be easily accessed to provide enterprise reporting features to your custom business applications.</span></span> <span data-ttu-id="7f6ee-105">Чтобы получить доступ к веб-службе в приложении Windows, можно просто написать код, который вызывает службу.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-105">You can access the Web service in a Windows application simply by writing code that makes calls to the service.</span></span> <span data-ttu-id="7f6ee-106">С помощью [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] можно создать класс-посредник, который предоставляет доступ к свойствам и методам веб-службы и позволяет использовать знакомую инфраструктуру и средства для создания бизнес-приложений на основе [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] технологий.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-106">Using the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], you can generate a proxy class that exposes the properties and methods of the Web service and enables you to use a familiar infrastructure and tools to build business applications built on [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] technology.</span></span>  
  
## <a name="integrating-report-management-functionality-using-windows-forms"></a><span data-ttu-id="7f6ee-107">Интеграция функций управления отчетами с помощью Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7f6ee-107">Integrating Report Management Functionality Using Windows Forms</span></span>  
 <span data-ttu-id="7f6ee-108">В отличие от доступа по URL-адресу, API SOAP дает доступ к полному набору функций управления, доступных на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-108">Unlike URL access, the SOAP API exposes the complete set of management functions that are available through the report server.</span></span> <span data-ttu-id="7f6ee-109">Это значит, что все административные функции диспетчера отчетов становятся доступными для разработчиков по протоколу SOAP.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-109">This means that the entire administrative functionality of Report Manager is available to developers through SOAP.</span></span> <span data-ttu-id="7f6ee-110">Таким образом, с помощью Windows Forms можно разработать законченное средство по управлению и администрированию.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-110">As such, you can develop a complete management and administration tool using Windows Forms.</span></span> <span data-ttu-id="7f6ee-111">Например, в приложении Windows может понадобиться разрешить пользователям получать содержимое пространства имен для сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-111">For example, in your Windows application, you might want to enable your users to retrieve the contents of the report server namespace.</span></span> <span data-ttu-id="7f6ee-112">Чтобы вывести список всех элементов в базе данных сервера отчетов, можно использовать метод веб-службы <xref:ReportService2010.ReportingService2010.ListChildren%2A>, а затем представить эти элементы пользователям в списке, в поле со списком или в элементе управления иерархического представления.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-112">To do this, you could use the Web service <xref:ReportService2010.ReportingService2010.ListChildren%2A> method to list all the items in the report server database and then use a Listview, Treeview, or Combobox control to display those items to your users.</span></span> <span data-ttu-id="7f6ee-113">С помощью следующего кода веб-службы можно получить текущий список доступных отчетов в пользовательской папке My Reports, когда пользователь нажимает кнопку на форме:</span><span class="sxs-lookup"><span data-stu-id="7f6ee-113">The following Web service code might be used to retrieve the current list of available reports in a user's My Reports folder when a user clicks a button on a form:</span></span>  
  
```vb  
' Button click event that retrieves a list of reports from  
' the My Reports folder and displays them in a combo box  
Private Sub listReportsButton_Click(sender As Object, e As System.EventArgs)  
   ' Create a new Web service object and set credentials  
   ' to Windows Authentication  
   Dim rs As New ReportingService2010()  
   rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
  
   ' Return the list of items in My Reports  
   Dim items As CatalogItem() = rs.ListChildren("/Adventureworks 2008 Sample Reports", False)  
  
   Dim ci As CatalogItem  
   For Each ci In  items  
      ' If the item is a report, add it to   
      ' a combo box  
      If ci.TypeName = "Report" Then  
         catalogComboBox.Items.Add(ci.Name)  
      End If  
   Next ci  
End Sub 'listReportsButton_Click  
```  
  
```csharp  
// Button click event that retrieves a list of reports from  
// the My Reports folder and displays them in a combo box  
private void listReportsButton_Click(object sender, System.EventArgs e)  
{  
   // Create a new Web service object and set credentials  
   // to Windows Authentication  
   ReportingService2010 rs = new ReportingService2010();  
   rs.Credentials = System.Net.CredentialCache.DefaultCredentials;  
  
   // Return the list of items in My Reports  
   CatalogItem[] items = rs.ListChildren("/Adventureworks 2008 Sample Reports", false);  
  
   foreach (CatalogItem ci in items)  
   {  
      // If the item is a report, add it to   
      // a combo box  
      if (ci.TypeName == "Report")  
         catalogComboBox.Items.Add(ci.Name);  
   }  
}  
```  
  
 <span data-ttu-id="7f6ee-114">Затем можно разрешить пользователям выбрать отчет из поля со списком и просмотреть отчет на форме с помощью элемента управления веб-браузера или элемента управления «Изображение».</span><span class="sxs-lookup"><span data-stu-id="7f6ee-114">From there, you might enable users to select the report from the Combo box and preview the report on the form either using a Web browser control or an image control.</span></span>  
  
## <a name="enabling-report-viewing-and-navigation-using-windows-forms"></a><span data-ttu-id="7f6ee-115">Включение просмотра отчетов и перехода по отчетам с помощью Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7f6ee-115">Enabling Report Viewing and Navigation Using Windows Forms</span></span>  
 <span data-ttu-id="7f6ee-116">Для интеграции отчетов в приложения Windows Forms доступно два метода.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-116">There are two methods available for integrating reports into your Windows Forms applications.</span></span>  
  
 <span data-ttu-id="7f6ee-117">Можно использовать API SOAP для подготовки отчетов к просмотру в любом из поддерживаемых форматов с помощью метода <xref:ReportExecution2005.ReportExecutionService.Render%2A>.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-117">You can use the SOAP API to render reports to any of the supported rendering formats using the <xref:ReportExecution2005.ReportExecutionService.Render%2A> method.</span></span> <span data-ttu-id="7f6ee-118">Включение просмотра отчетов и переходов по отчетов с помощью протокола SOAP сопряжено с некоторыми недостатками.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-118">There are slight disadvantages to enabling report viewing and navigation through SOAP:</span></span>  
  
-   <span data-ttu-id="7f6ee-119">Нельзя воспользоваться встроенными функциями панели инструментов отчета, которая доступна в средстве просмотра HTML-страниц при доступе по URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-119">You cannot take advantage of the built-in functionality of the report toolbar that is included with the HTML Viewer through URL access.</span></span>  
  
-   <span data-ttu-id="7f6ee-120">При подготовке к просмотру в формате HTML изображения или ресурсы необходимо обрабатывать в отдельных потоках с помощью метода <xref:ReportExecution2005.ReportExecutionService.RenderStream%2A>.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-120">If you render to HTML, you must separately render any images or resources as additional streams using the <xref:ReportExecution2005.ReportExecutionService.RenderStream%2A> method.</span></span>  
  
-   <span data-ttu-id="7f6ee-121">Использование доступа по URL-адресу для подготовки отчетов к просмотру дает небольшое преимущество в производительности по сравнению с API SOAP.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-121">There is a slight performance advantage to rendering reports using URL access over using the SOAP API.</span></span>  
  
 <span data-ttu-id="7f6ee-122">Однако метод <xref:ReportExecution2005.ReportExecutionService.Render%2A> API SOAP позволяет готовить отчеты к просмотру и сохранять их в различных выходных форматах программным образом.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-122">However, the <xref:ReportExecution2005.ReportExecutionService.Render%2A> method of the SOAP API can be used to render reports and save them to various output formats programmatically.</span></span> <span data-ttu-id="7f6ee-123">Такая возможность дает преимущество над доступом по URL-адресу, для которого необходимо участие пользователя.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-123">This is an advantage over URL access, which requires user interaction.</span></span> <span data-ttu-id="7f6ee-124">С помощью метода <xref:ReportExecution2005.ReportExecutionService.Render%2A> API SOAP отчет можно подготовить к просмотру в любом из поддерживаемых выходных форматов.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-124">When you render a report using the SOAP API <xref:ReportExecution2005.ReportExecutionService.Render%2A> method, you can render to any of the supported output formats.</span></span>  
  
 <span data-ttu-id="7f6ee-125">Можно также использовать свободно распространяемые элементы управления ReportViewer, входящие в состав [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7f6ee-125">You can also use the freely distributable ReportViewer controls that are included with [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)].</span></span> <span data-ttu-id="7f6ee-126">Элементы управления ReportViewer упрощают внедрение функций служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] в пользовательские приложения.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-126">The ReportViewer controls make it easy to embed [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] functionality into custom applications.</span></span> <span data-ttu-id="7f6ee-127">Элементы управления ReportViewer предназначены для разработчиков, которым нужно встроить в приложения заранее спроектированные отчеты. Например, приложение, предназначенное для управления веб-сайтом, может содержать отчеты, отображающие анализ посещений различных разделов веб-сайта компании.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-127">The ReportViewer controls are intended for developers who want to provide predesigned, fully authored reports as part of an application feature set (for example, a Web site management application might include reports that show click-stream analysis on company Web sites).</span></span> <span data-ttu-id="7f6ee-128">Элементы управления, внедряемые в приложение, служат простой альтернативой включению серверных компонентов служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] на этапе развертывания приложения.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-128">Embedding the controls in an application provides a streamlined alternative to including the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] server components in your application deployment.</span></span> <span data-ttu-id="7f6ee-129">Эти элементы управления обеспечивают функциональные возможности отчетов, но не поддерживают дополнительные возможности создания, публикации, распространения и доставки отчетов, доступные в службах [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7f6ee-129">The controls provide report functionality, but without the additional report authoring, publication, or distribution and delivery support that you find in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="7f6ee-130">Существует две версии элементов управления ReportViewer: одна предназначена для многофункциональных клиентских приложений Windows, а вторая — для приложений [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7f6ee-130">There are two versions of the ReportViewer controls, one for rich Windows client applications and one for [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] applications.</span></span> <span data-ttu-id="7f6ee-131">Элементы управления поддерживают режимы локальной и удаленной обработки.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-131">The controls support both local processing and remote processing modes.</span></span> <span data-ttu-id="7f6ee-132">В режиме локальной обработки приложение предоставляет определения отчетов, наборы данных и триггерную обработку отчетов.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-132">In local processing mode, your application provides the report definition and datasets and triggers report processing.</span></span> <span data-ttu-id="7f6ee-133">В режиме удаленной обработки получение данных и обработка отчетов выполняется на сервере отчетов, а элементы управления используются для отображения и навигации по отчету.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-133">In remote processing mode, data retrieval and report processing happen on the report server and the control is used for display and report navigation.</span></span> <span data-ttu-id="7f6ee-134">Такая модель позволяет разрабатывать мощные, легкомасштабируемые приложения.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-134">This model allows you to build rich applications that can be scaled from desktop to the enterprise.</span></span>  
  
 <span data-ttu-id="7f6ee-135">Документацию по элементам управления ReportViewer см. в справке по среде [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] в Интернете.</span><span class="sxs-lookup"><span data-stu-id="7f6ee-135">ReportViewer controls are documented in [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] online Help.</span></span> <span data-ttu-id="7f6ee-136">Дополнительные сведения см. в документации по продукту [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7f6ee-136">For more information, see the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] product documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f6ee-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="7f6ee-137">See Also</span></span>  
 <span data-ttu-id="7f6ee-138">[Создание приложений с помощью веб-службы и .NET Framework](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="7f6ee-138">[Building Applications Using the Web Service and the .NET Framework](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="7f6ee-139">[Интеграция Reporting Services в приложения](../application-integration/integrating-reporting-services-into-applications.md) </span><span class="sxs-lookup"><span data-stu-id="7f6ee-139">[Integrating Reporting Services into Applications](../application-integration/integrating-reporting-services-into-applications.md) </span></span>  
 [<span data-ttu-id="7f6ee-140">Использование API SOAP в веб-приложении</span><span class="sxs-lookup"><span data-stu-id="7f6ee-140">Using the SOAP API in a Web Application</span></span>](integrating-reporting-services-using-soap-web-application.md)  
  
  
