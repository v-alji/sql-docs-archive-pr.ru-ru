---
title: Использование доступа по URL-адресу в веб-приложении | Документы Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- links [Reporting Services], URL access
- URL access [Reporting Services], Web applications
- POST requests
- direct addressing [Reporting Services]
- Web applications [Reporting Services]
- hyperlinks [Reporting Services]
ms.assetid: 39e7918c-ad2d-4ca6-b099-2dd4dbdb83dc
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cd31f76658f8160cbb2a576debc335588f77e72c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654065"
---
# <a name="using-url-access-in-a-web-application"></a><span data-ttu-id="f0e47-102">Использование доступа по URL-адресу в веб-приложении</span><span class="sxs-lookup"><span data-stu-id="f0e47-102">Using URL Access in a Web Application</span></span>
  <span data-ttu-id="f0e47-103">Доступ по URL-адресам в службах [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] специально разработан таким образом, чтобы можно было получить доступ по сети к отдельным отчетам.</span><span class="sxs-lookup"><span data-stu-id="f0e47-103">URL access in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is specifically designed to enable access to individual reports over a network.</span></span> <span data-ttu-id="f0e47-104">Этот тип доступа наилучшим образом подходит для интеграции средств просмотра и навигации по отчетам в пользовательских веб-приложениях.</span><span class="sxs-lookup"><span data-stu-id="f0e47-104">This type of access is best for integrating report viewing and navigation into a custom Web application.</span></span> <span data-ttu-id="f0e47-105">Использовать доступ по URL-адресам в веб-приложениях можно следующим образом.</span><span class="sxs-lookup"><span data-stu-id="f0e47-105">To use URL access in Web applications, you can:</span></span>  
  
-   <span data-ttu-id="f0e47-106">Задавать URL-адрес конкретного сервера отчетов на веб-сайте или портале.</span><span class="sxs-lookup"><span data-stu-id="f0e47-106">Address a URL to a specific report server from a Web site or portal.</span></span>  
  
-   <span data-ttu-id="f0e47-107">Применять метод формы POST и передавать параметры строки запроса по URL-адресу сервера отчетов с использованием полей формы.</span><span class="sxs-lookup"><span data-stu-id="f0e47-107">Use a form POST method and pass query string parameters to a report server URL using form fields.</span></span>  
  
## <a name="url-access-through-direct-addressing"></a><span data-ttu-id="f0e47-108">Доступ к URL-адресу с помощью прямой адресации</span><span class="sxs-lookup"><span data-stu-id="f0e47-108">URL Access Through Direct Addressing</span></span>  
 <span data-ttu-id="f0e47-109">Для доступа к серверу отчетов или элементу базы данных сервера отчетов по URL-адресу достаточно просто указать этот URL-адрес в веб-браузере или приложении.</span><span class="sxs-lookup"><span data-stu-id="f0e47-109">To access a report server or report server database item using a URL, simply provide the URL address from within a Web browser or application.</span></span> <span data-ttu-id="f0e47-110">Можно также предусмотреть использование в URL-адресе параметров, которые могут повлиять на отображение отчета или ресурса, к которому осуществляется доступ.</span><span class="sxs-lookup"><span data-stu-id="f0e47-110">You can also supply parameters to the URL that can affect the appearance of the report or resource that is being accessed.</span></span> <span data-ttu-id="f0e47-111">Конкретный сервер отчетов можно указать в URL-адресе с помощью адресной строки веб-браузера. URL-адрес можно также указать как источник объекта **IFrame**, входящего в состав более крупного веб-приложения или портала.</span><span class="sxs-lookup"><span data-stu-id="f0e47-111">A URL can target a report server through the address bar of a Web browser, or a URL can be the source of an **IFrame** that is part of a larger Web application or portal.</span></span> <span data-ttu-id="f0e47-112">Гиперссылки на отчеты можно размещать на различных веб-страницах портала, а также указывать, в каком именно фрейме страницы должен быть выведен отчет, или открывать в процессе доступа к отчету новое окно браузера.</span><span class="sxs-lookup"><span data-stu-id="f0e47-112">You can include hyperlinks to reports on various Web pages of your portal, as well as target a specific frame for the report or open a new browser window in the process.</span></span>  
  
 <span data-ttu-id="f0e47-113">В следующем примере гиперссылка указывает на фрейм с именем «main», который может отличаться от того фрейма, в котором находится гиперссылка.</span><span class="sxs-lookup"><span data-stu-id="f0e47-113">In the following example, the hyperlink targets a frame named "main", which might be different from the one that includes the hyperlink.</span></span> <span data-ttu-id="f0e47-114">Гиперссылка может входить в состав веб-портала.</span><span class="sxs-lookup"><span data-stu-id="f0e47-114">The hyperlink might be part of Web portal.</span></span>  
  
```  
<a href="http://server/reportserver?/SampleReports/Territory Sales   
Drilldown&rs:Command=Render&rc:LinkTarget=main" target="main" >  
   Click here for the Territory Sales Drilldown sample report  
</a>  
```  
  
 <span data-ttu-id="f0e47-115">В предыдущем примере параметр сведений об устройстве **LinkTarget** передается со значением "main" в строке запроса URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="f0e47-115">In the previous example, the device information setting **LinkTarget** is passed with a value of "main" in the query string of the URL.</span></span> <span data-ttu-id="f0e47-116">Это позволяет гарантировать, что любые детализирующие ссылки в отчете также будут указывать на фрейм с именем «main».</span><span class="sxs-lookup"><span data-stu-id="f0e47-116">This ensures that any drillthrough hyperlinks in the report also target the frame named "main".</span></span>  
  
 <span data-ttu-id="f0e47-117">Дополнительные сведения о параметрах сведений об устройстве см. в разделе [Передача настроек сведений об устройстве модулям подготовки отчетов к просмотру](../report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="f0e47-117">For more information about device information settings, see [Passing Device Information Settings to Rendering Extensions](../report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span></span>  
  
 <span data-ttu-id="f0e47-118">Следует отметить, что многие серверы и браузеры ограничивают допустимое число символов в URL-адресе.</span><span class="sxs-lookup"><span data-stu-id="f0e47-118">Note that many servers and browsers limit the number of characters allowed in a URL.</span></span> <span data-ttu-id="f0e47-119">В некоторых случаях длина адреса ограничена 256 символами.</span><span class="sxs-lookup"><span data-stu-id="f0e47-119">In some cases, a 256-character limit is imposed.</span></span> <span data-ttu-id="f0e47-120">Чтобы обойти это ограничение, необходимо использовать запросы POST с передачей форм.</span><span class="sxs-lookup"><span data-stu-id="f0e47-120">To get around this limitation, you can use POST requests using form submission.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f0e47-121">Максимальная длина URL-адреса в обозревателе Internet Explorer составляет 2083 символа.</span><span class="sxs-lookup"><span data-stu-id="f0e47-121">Internet Explorer has a maximum URL length of 2,083 characters.</span></span> <span data-ttu-id="f0e47-122">Это ограничение относится к запросам по URL-адресу обоих типов, POST и GET.</span><span class="sxs-lookup"><span data-stu-id="f0e47-122">This limit applies to both POST and GET request URLs.</span></span> <span data-ttu-id="f0e47-123">Тем не менее, на запрос POST не налагаются ограничения в связи с размером URL-адреса при передаче пар «имя/значение» в составе формы, поскольку они передаются в заголовке, а не в URL-адресе.</span><span class="sxs-lookup"><span data-stu-id="f0e47-123">POST, however, is not limited by the size of the URL for submitting name/value pairs as part of a form, because they are transferred in the header and not the URL.</span></span>  
  
## <a name="url-access-through-a-form-post-method"></a><span data-ttu-id="f0e47-124">Доступ по URL-адресу с помощью метода форм POST</span><span class="sxs-lookup"><span data-stu-id="f0e47-124">URL Access Through a Form POST Method</span></span>  
 <span data-ttu-id="f0e47-125">Если пользователь запрашивает данные с сервера отчетов по URL-адресу, то в HTTP-запросе используется метод GET.</span><span class="sxs-lookup"><span data-stu-id="f0e47-125">When a user requests data from a report server using URL access, the HTTP request uses the GET method.</span></span> <span data-ttu-id="f0e47-126">Это аналогично передаче формы при условии METHOD="GET".</span><span class="sxs-lookup"><span data-stu-id="f0e47-126">This is equivalent to a form submission where METHOD="GET".</span></span> <span data-ttu-id="f0e47-127">На URL-запросы или операции передачи форм с параметром METHOD="GET" налагается ограничение, определяемое максимальным количеством символов, которые может обработать сервер или веб-браузер.</span><span class="sxs-lookup"><span data-stu-id="f0e47-127">URL requests or form submissions that use METHOD="GET" are limited by the maximum number of characters that a server or Web browser can process.</span></span>  
  
 <span data-ttu-id="f0e47-128">А при использовании запросов POST (с параметром METHOD="POST" и полями ввода) пары «имя/значение» передаются в заголовке, а не в URL-адресе.</span><span class="sxs-lookup"><span data-stu-id="f0e47-128">With POST requests (METHOD="POST" and input fields), the name/value pairs are transferred in the header and not the URL.</span></span> <span data-ttu-id="f0e47-129">Поэтому пары «имя/значение» в строке запроса перестают быть частью URL-адреса, что позволяет передавать гораздо более длинные и сложные списки параметров.</span><span class="sxs-lookup"><span data-stu-id="f0e47-129">Therefore, the name/value pairs of the query string are not part of the URL, thus enabling you to provide much longer and more complex parameter lists.</span></span>  
  
 <span data-ttu-id="f0e47-130">При использовании прямого доступа пользователь может видеть URL-адрес, передаваемый на сервер отчетов, поэтому получает возможность изменить строку запроса или отметить для себя конкретный URL-запрос и параметры сервера отчетов, чтобы воспользоваться этими сведениями в дальнейшем.</span><span class="sxs-lookup"><span data-stu-id="f0e47-130">Using direct access, a user can see the URL for the report server, and may be able to modify the  query string or note the particular URL request and report server parameters for later use.</span></span>  
  
 <span data-ttu-id="f0e47-131">В приведенном ниже образце HTML-кода показана форма, которая позволяет получить доступ к серверу отчетов с помощью конкретного URL-адреса и передать параметры строки запроса в составе полей ввода формы.</span><span class="sxs-lookup"><span data-stu-id="f0e47-131">The following sample HTML demonstrates the use of a form that you can use to target a report server with a specific URL and pass query string parameters as part of the form's input fields.</span></span>  
  
```  
<FORM id="frmRender" action="http://server/reportserver?/SampleReports/  
   Territory Sales Drilldown" method="post" target="_self">  
   <INPUT type="hidden" name="rs:Command" value="Render">   
   <INPUT type="hidden" name="rc:LinkTarget" value="main">  
   <INPUT type="hidden" name="rs:Format" value="HTML4.0">  
   <INPUT type="submit" value="Button">  
</FORM>  
```  
  
 <span data-ttu-id="f0e47-132">В предыдущем примере предусмотрено, что при нажатии пользователем кнопки на форме сервер отчетов возвращает отчет, подготовленный в формате HTML, который предназначен для просмотра в текущем фрейме.</span><span class="sxs-lookup"><span data-stu-id="f0e47-132">In the previous example, if a user clicks the button on the form, the report server returns an HTML-rendered report targeted at the current frame.</span></span> <span data-ttu-id="f0e47-133">Сопоставимая строка доступа по URL-адресу может выглядеть примерно таким образом:</span><span class="sxs-lookup"><span data-stu-id="f0e47-133">A comparable URL access string might look like the following:</span></span>  
  
```  
http://server/reportserver?/SampleReports/Territory Sales   
Drilldown&rs:Command=Render&rc:LinkTarget=main&rs:Format=HTML4.0  
```  
  
## <a name="see-also"></a><span data-ttu-id="f0e47-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="f0e47-134">See Also</span></span>  
 <span data-ttu-id="f0e47-135">[Интеграция Reporting Services в приложения](../application-integration/integrating-reporting-services-into-applications.md) </span><span class="sxs-lookup"><span data-stu-id="f0e47-135">[Integrating Reporting Services into Applications](../application-integration/integrating-reporting-services-into-applications.md) </span></span>  
 <span data-ttu-id="f0e47-136">[Интеграция Reporting Services с использованием доступа по URL-адресу](integrating-reporting-services-using-url-access.md) </span><span class="sxs-lookup"><span data-stu-id="f0e47-136">[Integrating Reporting Services Using URL Access](integrating-reporting-services-using-url-access.md) </span></span>  
 <span data-ttu-id="f0e47-137">[Использование доступа по URL-адресу в приложении Windows](integrating-reporting-services-using-url-access-windows-application.md) </span><span class="sxs-lookup"><span data-stu-id="f0e47-137">[Using URL Access in a Windows Application](integrating-reporting-services-using-url-access-windows-application.md) </span></span>  
 [<span data-ttu-id="f0e47-138">Доступ по URL-адресу (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="f0e47-138">URL Access &#40;SSRS&#41;</span></span>](../url-access-ssrs.md)  
  
  
