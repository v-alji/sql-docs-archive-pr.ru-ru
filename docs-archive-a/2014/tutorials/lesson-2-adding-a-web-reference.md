---
title: Занятие 2. Добавление веб-ссылки | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a2c2b8b8-6b13-45ca-ab3b-1582447b6807
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 02ca614cb042211ac468246c3003efaa5f2e8fb5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733385"
---
# <a name="lesson-2-adding-a-web-reference"></a><span data-ttu-id="cc17e-102">Урок 2. Добавление веб-ссылки</span><span class="sxs-lookup"><span data-stu-id="cc17e-102">Lesson 2: Adding a Web Reference</span></span>
  <span data-ttu-id="cc17e-103">Поиск веб-службы — это процесс, с помощью которого пользователь находит веб-службу и получает ее описание службы.</span><span class="sxs-lookup"><span data-stu-id="cc17e-103">Web service discovery is the process by which a client locates a Web service and obtains its service description.</span></span> <span data-ttu-id="cc17e-104">Процесс поиска веб-службы в среде [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] заключается в опрашивании веб-сайта по определенному алгоритму.</span><span class="sxs-lookup"><span data-stu-id="cc17e-104">The process of Web service discovery in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] involves interrogating a Web site following a predetermined algorithm.</span></span> <span data-ttu-id="cc17e-105">Целью процесса является обнаружение описания службы в виде XML-документа, составленного на языке описания веб-служб (WDSL).</span><span class="sxs-lookup"><span data-stu-id="cc17e-105">The goal of the process is to locate the service description, which is an XML document that uses the Web Services Description Language (WSDL).</span></span>  
  
 <span data-ttu-id="cc17e-106">Описание службы содержит список доступных служб, а также способы взаимодействия с ними.</span><span class="sxs-lookup"><span data-stu-id="cc17e-106">The service description describes what services are available and how to interact with those services.</span></span> <span data-ttu-id="cc17e-107">Невозможно программно взаимодействовать с веб-службой, не имея ее описания службы.</span><span class="sxs-lookup"><span data-stu-id="cc17e-107">Without a service description, it is impossible to programmatically interact with a Web service.</span></span>  
  
 <span data-ttu-id="cc17e-108">Создаваемое приложение должно обладать средствами обнаружения веб-службы в ходе выполнения, а также средствами взаимодействия с этой веб-службой.</span><span class="sxs-lookup"><span data-stu-id="cc17e-108">Your application must have a means to communicate with the Web service and to locate it at run time.</span></span> <span data-ttu-id="cc17e-109">При добавлении к проекту ссылки на веб-службу происходит создание класса-посредника, с помощью которого ведется взаимодействие с веб-службой и обеспечивается ее локальное представление.</span><span class="sxs-lookup"><span data-stu-id="cc17e-109">Adding a Web reference to your project for the Web service does this by generating a proxy class that interfaces with the Web service and provides a local representation of the Web service.</span></span> <span data-ttu-id="cc17e-110">Дополнительные сведения см. в разделе «инструкции. Создание прокси-службы XML» в [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] документации.</span><span class="sxs-lookup"><span data-stu-id="cc17e-110">For more information, see "How to: Generate an XML Web Service Proxy" in your [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] documentation.</span></span>  
  
### <a name="to-add-a-web-reference"></a><span data-ttu-id="cc17e-111">Добавление веб-ссылки</span><span class="sxs-lookup"><span data-stu-id="cc17e-111">To add a Web reference</span></span>  
  
1.  <span data-ttu-id="cc17e-112">В меню **проект** выберите пункт **Добавление ссылки на службу**.</span><span class="sxs-lookup"><span data-stu-id="cc17e-112">On the **Project** menu, click **Add Service Reference**.</span></span>  
  
2.  <span data-ttu-id="cc17e-113">В диалоговом окне **Добавление ссылки на службу** нажмите кнопку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="cc17e-113">In the **Add Service Reference** dialog box, click **Advanced**.</span></span>  
  
3.  <span data-ttu-id="cc17e-114">В диалоговом окне **Параметры ссылки на службу** нажмите кнопку **Добавить веб-ссылку**.</span><span class="sxs-lookup"><span data-stu-id="cc17e-114">In the **Service Reference Settings** dialog box, click **Add Web Reference**.</span></span>  
  
4.  <span data-ttu-id="cc17e-115">В поле **URL-адрес** диалогового окна **Добавление веб-ссылки** введите URL-адрес, чтобы получить описание службы сервера отчетов, например http://localhost/reportserver/reportservice2010.asmx .</span><span class="sxs-lookup"><span data-stu-id="cc17e-115">In the **URL** box of the **Add Web Reference** dialog box, type the URL to obtain the service description of the Report Server Web service, such as http://localhost/reportserver/reportservice2010.asmx.</span></span> <span data-ttu-id="cc17e-116">Затем нажмите кнопку **Go (найти** ), чтобы получить сведения о веб-службе.</span><span class="sxs-lookup"><span data-stu-id="cc17e-116">Then click the **Go** button to retrieve information about the Web service.</span></span>  
  
     <span data-ttu-id="cc17e-117">\- или -</span><span class="sxs-lookup"><span data-stu-id="cc17e-117">\- or -</span></span>  
  
     <span data-ttu-id="cc17e-118">Если веб-служба сервера отчетов существует на локальном компьютере, щелкните ссылку **веб-службы на локальном компьютере** в области браузера.</span><span class="sxs-lookup"><span data-stu-id="cc17e-118">If the Report Server Web service exists on the local machine, click the **Web services on the local machine** link in the browser pane.</span></span> <span data-ttu-id="cc17e-119">Затем щелкните ссылку на веб-службу ReportService2010 из приведенного ниже списка.</span><span class="sxs-lookup"><span data-stu-id="cc17e-119">Then click the link for the ReportService2010 Web service from the list provided.</span></span>  
  
5.  <span data-ttu-id="cc17e-120">В поле **имя веб-ссылки** переименуйте веб-ссылку на ReportService2010, то есть пространство имен, которое будет использоваться для этой веб-ссылки.</span><span class="sxs-lookup"><span data-stu-id="cc17e-120">In the **Web reference name** box, rename the Web reference to ReportService2010, which is the namespace you will use for this Web reference.</span></span>  
  
6.  <span data-ttu-id="cc17e-121">Щелкните **Добавить ссылку** , чтобы добавить веб-ссылку на целевую веб – службу.</span><span class="sxs-lookup"><span data-stu-id="cc17e-121">Click **Add Reference** to add a Web reference for the target Web service.</span></span>  
  
     <span data-ttu-id="cc17e-122">В среде [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] будет загружено описание службы и создан класс-посредник для взаимодействия приложения с веб-службой сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="cc17e-122">[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] downloads the service description and generates a proxy class to interface between your application and the Report Server Web service.</span></span> <span data-ttu-id="cc17e-123">Также для обеспечения работоспособности веб-ссылки необходимо добавить ссылку на пространство имен <xref:System.Web.Services>.</span><span class="sxs-lookup"><span data-stu-id="cc17e-123">You will also need to add a reference to the <xref:System.Web.Services> namespace for your Web reference to work.</span></span>  
  
7.  <span data-ttu-id="cc17e-124">В меню Проект щелкните команду **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="cc17e-124">On the Project menu, click **Add Reference**.</span></span>  
  
8.  <span data-ttu-id="cc17e-125">В диалоговом окне **Добавить ссылку** на вкладке **.NET** выберите **System.Web.Services**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="cc17e-125">In the **Add Reference** dialog box, in the **.NET** tab, select **System.Web.Services**, then click **OK**.</span></span>  
  
 <span data-ttu-id="cc17e-126">Дополнительные сведения см. в разделе [Доступ к API-интерфейсу SOAP](../reporting-services/report-server-web-service/accessing-the-soap-api.md).</span><span class="sxs-lookup"><span data-stu-id="cc17e-126">For more information, see [Accessing the SOAP API](../reporting-services/report-server-web-service/accessing-the-soap-api.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc17e-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="cc17e-127">See Also</span></span>  
 <span data-ttu-id="cc17e-128">[Веб-служба сервера отчетов](../reporting-services/report-server-web-service/report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="cc17e-128">[Report Server Web Service](../reporting-services/report-server-web-service/report-server-web-service.md) </span></span>  
 <span data-ttu-id="cc17e-129">[Занятие 3. доступ к веб-службе](../../2014/tutorials/lesson-3-accessing-the-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="cc17e-129">[Lesson 3: Accessing the Web Service](../../2014/tutorials/lesson-3-accessing-the-web-service.md) </span></span>  
 [<span data-ttu-id="cc17e-130">Доступ к веб-службе сервера отчетов с помощью Visual Basic или учебника по Visual C&#35; &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="cc17e-130">Accessing the Report Server Web Service Using Visual Basic or Visual C&#35; &#40;SSRS Tutorial&#41;</span></span>](../../2014/tutorials/access-report-server-web-service-vb-vcsharp-ssrs-tutorial.md)  
  
  
