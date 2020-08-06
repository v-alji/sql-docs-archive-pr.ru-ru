---
title: Использование API SOAP в веб-приложении | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- SOAP [Reporting Services], Web applications
- impersonation [Reporting Services]
- user impersonation [Reporting Services]
- report servers [Reporting Services], SOAP
- Web applications [Reporting Services]
ms.assetid: e8ca4455-0dc3-4741-8872-3636114938ad
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e228f01915df633f50b23bf93e892446863c28ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729149"
---
# <a name="using-the-soap-api-in-a-web-application"></a><span data-ttu-id="35e1b-102">Использование API SOAP в веб-приложении</span><span class="sxs-lookup"><span data-stu-id="35e1b-102">Using the SOAP API in a Web Application</span></span>
  <span data-ttu-id="35e1b-103">С помощью API SOAP служб Reporting Services можно получить доступ ко всем функциональным возможностям сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="35e1b-103">You can access the full functionality of the report server through the Reporting Services SOAP API.</span></span> <span data-ttu-id="35e1b-104">Поскольку API SOAP является веб-службой, к нему легко получить доступ, чтобы предоставить для пользовательских бизнес-приложений функции создания отчетов в масштабе предприятия.</span><span class="sxs-lookup"><span data-stu-id="35e1b-104">Because it's a Web service, the SOAP API can be easily accessed to provide enterprise reporting features to your custom business applications.</span></span> <span data-ttu-id="35e1b-105">Доступ к веб-службе сервера отчетов из веб-приложения осуществляется во многом аналогично доступу к API SOAP из приложения [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="35e1b-105">You access the Report Server Web service from a Web application in much the same way that you access the SOAP API from a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows application.</span></span> <span data-ttu-id="35e1b-106">С помощью [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] можно создать класс-посредник, который предоставляет доступ к свойствам и методам веб-службы сервера отчетов и позволяет использовать знакомую инфраструктуру и средства для создания бизнес-приложений на основе [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] технологий.</span><span class="sxs-lookup"><span data-stu-id="35e1b-106">Using the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], you can generate a proxy class that exposes the properties and methods of the Report Server Web service and enables you to use a familiar infrastructure and tools to build business applications on [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] technology.</span></span>  
  
 <span data-ttu-id="35e1b-107">Функции служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] по управлению отчетами доступны из веб-приложения так же легко, как из приложения Windows.</span><span class="sxs-lookup"><span data-stu-id="35e1b-107">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report management functionality is just as easily accessed from a Web application as from a Windows application.</span></span> <span data-ttu-id="35e1b-108">Из веб-приложения можно добавлять элементы в базу данных сервера отчетов и удалять из нее элементы, задавать параметры безопасности элемента, изменять элементы базы данных сервера отчетов, управлять планированием и доставкой, а также выполнять другие действия.</span><span class="sxs-lookup"><span data-stu-id="35e1b-108">From a Web application, you can add and remove items from the report server database, set item security, modify report server database items, manage scheduling and delivery, and more.</span></span>  
  
## <a name="enabling-impersonation"></a><span data-ttu-id="35e1b-109">Включение олицетворения</span><span class="sxs-lookup"><span data-stu-id="35e1b-109">Enabling Impersonation</span></span>  
 <span data-ttu-id="35e1b-110">Первым шагом в настройке веб-приложения является включение олицетворения со стороны клиента веб-службы.</span><span class="sxs-lookup"><span data-stu-id="35e1b-110">The first step in configuring your Web application is to enable impersonation from the Web service client.</span></span> <span data-ttu-id="35e1b-111">Олицетворение позволяет приложениям [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] выполняться с удостоверением клиента, от имени которого они работают.</span><span class="sxs-lookup"><span data-stu-id="35e1b-111">With impersonation, [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] applications can execute with the identity of the client on whose behalf they are operating.</span></span> [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] <span data-ttu-id="35e1b-112">с помощью служб [!INCLUDE[msCoName](../../includes/msconame-md.md)] IIS проверяет подлинность пользователя и передает в приложение [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] проверенный токен или (если не удалось проверить подлинность пользователя) непроверенный токен.</span><span class="sxs-lookup"><span data-stu-id="35e1b-112">relies on [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services (IIS) to authenticate the user and either pass an authenticated token to the [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] application or, if unable to authenticate the user, pass an unauthenticated token.</span></span> <span data-ttu-id="35e1b-113">Если включено олицетворение, приложение [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] в любом случае выполняет олицетворение любого полученного токена.</span><span class="sxs-lookup"><span data-stu-id="35e1b-113">In either case, the [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] application impersonates whichever token is received if impersonation is enabled.</span></span> <span data-ttu-id="35e1b-114">Можно включить олицетворение на клиенте, изменив файл Web.config клиентского приложения следующим образом:</span><span class="sxs-lookup"><span data-stu-id="35e1b-114">You can enable impersonation on the client, by modifying the Web.config file of the client application as follows:</span></span>  
  
```  
<!-- Web.config file. -->  
<identity impersonate="true"/>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="35e1b-115">По умолчанию олицетворение отключено.</span><span class="sxs-lookup"><span data-stu-id="35e1b-115">Impersonation is disabled by default.</span></span>  
  
 <span data-ttu-id="35e1b-116">Дополнительные сведения об [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] олицетворении см [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] . в документации по пакету SDK.</span><span class="sxs-lookup"><span data-stu-id="35e1b-116">For more information about [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] impersonation, see the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK documentation.</span></span>  
  
## <a name="managing-the-report-server-using-soap-api"></a><span data-ttu-id="35e1b-117">Управление сервером отчетов с помощью API SOAP</span><span class="sxs-lookup"><span data-stu-id="35e1b-117">Managing the Report Server using SOAP API</span></span>  
 <span data-ttu-id="35e1b-118">С помощью веб-приложения также можно управлять сервером отчетов и его содержимым.</span><span class="sxs-lookup"><span data-stu-id="35e1b-118">You can also use your Web application to manage a report server and its contents.</span></span> <span data-ttu-id="35e1b-119">Диспетчер отчетов, входящий в состав служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], служит примером веб-приложения, которое целиком построено с помощью [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] и API SOAP служб Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="35e1b-119">Report Manager, included with [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], is an example of a Web application that is completely built using [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] and the Reporting Services SOAP API.</span></span> <span data-ttu-id="35e1b-120">Можно добавить функции управления отчетами, доступные в диспетчере отчетов, в пользовательские веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="35e1b-120">You can add the report management functionality of Report Manager to your custom Web applications.</span></span> <span data-ttu-id="35e1b-121">Например, может потребоваться возвратить список доступных отчетов в базе данных сервера отчетов и отображать их в [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] `Listbox` элементе управления для выбора пользователями.</span><span class="sxs-lookup"><span data-stu-id="35e1b-121">For example, you might want to return a list of available reports in the report server database and display them in a [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] `Listbox` control for your users to choose from.</span></span> <span data-ttu-id="35e1b-122">В следующем коде устанавливается соединение с базой данных сервера отчетов и возвращается список элементов в базе данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="35e1b-122">The following code connects to the report server database and returns a list of items in the report server database.</span></span> <span data-ttu-id="35e1b-123">Затем доступные отчеты добавляются в элемент управления Listbox, в котором отображается путь к каждому отчету.</span><span class="sxs-lookup"><span data-stu-id="35e1b-123">The available reports are then added to a Listbox control, which displays the path of each report.</span></span>  
  
```vb  
Private Sub Page_Load(sender As Object, e As System.EventArgs)  
   ' Create a Web service proxy object and set credentials  
   Dim rs As New ReportingService2005()  
   rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
  
   ' Return a list of catalog items in the report server database  
   Dim items As CatalogItem() = rs.ListChildren("/", True)  
  
   ' For each report, display the path of the report in a Listbox  
   Dim ci As CatalogItem  
   For Each ci In  items  
      If ci.Type = ItemTypeEnum.Report Then  
         catalogListBox.Items.Add(ci.Path)  
      End If  
   Next ci  
End Sub ' Page_Load   
```  
  
```csharp  
private void Page_Load(object sender, System.EventArgs e)  
{  
   // Create a Web service proxy object and set credentials  
   ReportingService2005 rs = new ReportingService2005();  
   rs.Credentials = System.Net.CredentialCache.DefaultCredentials;  
  
   // Return a list of catalog items in the report server database  
   CatalogItem[] items = rs.ListChildren("/", true);  
  
   // For each report, display the path of the report in a Listbox  
   foreach(CatalogItem ci in items)  
   {  
      if (ci.Type == ItemTypeEnum.Report)  
         catalogListBox.Items.Add(ci.Path);  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="35e1b-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="35e1b-124">See Also</span></span>  
 <span data-ttu-id="35e1b-125">[Создание приложений с помощью веб-службы и .NET Framework](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="35e1b-125">[Building Applications Using the Web Service and the .NET Framework](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="35e1b-126">[Интеграция Reporting Services в приложения](../application-integration/integrating-reporting-services-into-applications.md) </span><span class="sxs-lookup"><span data-stu-id="35e1b-126">[Integrating Reporting Services into Applications](../application-integration/integrating-reporting-services-into-applications.md) </span></span>  
 <span data-ttu-id="35e1b-127">[Диспетчер отчетов (службы Reporting Services в основном режиме)](../report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="35e1b-127">[Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md) </span></span>  
 [<span data-ttu-id="35e1b-128">Использование API SOAP в приложении Windows</span><span class="sxs-lookup"><span data-stu-id="35e1b-128">Using the SOAP API in a Windows Application</span></span>](integrating-reporting-services-using-soap-windows-application.md)  
  
  
