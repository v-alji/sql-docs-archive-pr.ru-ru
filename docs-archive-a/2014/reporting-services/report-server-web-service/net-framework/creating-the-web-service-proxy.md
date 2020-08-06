---
title: Создание прокси веб-службы | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Report Server Web service, proxies
- proxies [Reporting Services]
- XML Web service [Reporting Services], proxies
- Web service [Reporting Services], proxies
- Web references [Reporting Services]
ms.assetid: b1217843-8d3d-49f3-a0d2-d35b0db5b2df
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0d080b96fa29e906c044561a684d58275af9f61e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730138"
---
# <a name="creating-the-web-service-proxy"></a><span data-ttu-id="a5049-102">Создание учетной записи-посредника веб-службы</span><span class="sxs-lookup"><span data-stu-id="a5049-102">Creating the Web Service Proxy</span></span>
  <span data-ttu-id="a5049-103">Клиент и веб-служба могут обмениваться данными с помощью сообщений SOAP, в который входные и выходные параметры инкапсулируются в формате XML.</span><span class="sxs-lookup"><span data-stu-id="a5049-103">A client and a Web service can communicate using SOAP messages, which encapsulate the input and output parameters as XML.</span></span> <span data-ttu-id="a5049-104">Класс-посредник сопоставляет параметры с XML-элементами, а затем отправляет сообщения SOAP по сети.</span><span class="sxs-lookup"><span data-stu-id="a5049-104">A proxy class maps parameters to XML elements and then sends the SOAP messages over a network.</span></span> <span data-ttu-id="a5049-105">Таким образом класс-посредник устраняет необходимость связываться с веб-службой на уровне SOAP и позволяет вызывать методы веб-службы в любой среде разработки, которая поддерживает протокол SOAP и прокси для веб-служб.</span><span class="sxs-lookup"><span data-stu-id="a5049-105">In this way, the proxy class frees you from having to communicate with the Web service at the SOAP level and allows you to invoke Web service methods in any development environment that supports SOAP and Web service proxies.</span></span>  
  
 <span data-ttu-id="a5049-106">Существует два способа добавления класса-посредника в проект разработки с использованием [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] : с помощью средства WSDL в [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] , а также путем добавления веб-ссылки в [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a5049-106">There are two ways to add a proxy class to your development project using the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]: with the WSDL tool in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], and by adding a Web reference in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="a5049-107">В следующих подразделах эта тема описана более подробно.</span><span class="sxs-lookup"><span data-stu-id="a5049-107">The following sections discuss this subject in further detail.</span></span>  
  
## <a name="adding-the-proxy-using-the-wsdl-tool"></a><span data-ttu-id="a5049-108">Добавление класса-посредника с помощью программы WSDL</span><span class="sxs-lookup"><span data-stu-id="a5049-108">Adding the Proxy Using the WSDL Tool</span></span>  
 <span data-ttu-id="a5049-109">Пакет SDK для [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] включает программу Wsdl.exe для работы с языком WSDL, которая позволяет создать прокси-класс веб-службы для использования в среде разработки [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a5049-109">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK includes the Web Services Description Language tool (Wsdl.exe), which enables you to generate a Web service proxy for use in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] development environment.</span></span> <span data-ttu-id="a5049-110">Наиболее распространенным способом создания прокси клиента на языках, поддерживающих веб-службы (в настоящее время это C# и [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] ), является использование средства WSDL.</span><span class="sxs-lookup"><span data-stu-id="a5049-110">The most common way to create a client proxy in languages that support Web services (currently C# and [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) is to use the WSDL tool.</span></span>  
  
 <span data-ttu-id="a5049-111">**Добавление прокси-класса в проект с помощью Wsdl.exe**</span><span class="sxs-lookup"><span data-stu-id="a5049-111">**To add a proxy class to your project using Wsdl.exe**</span></span>  
  
1.  <span data-ttu-id="a5049-112">Запустите программу Wsdl.exe из командной строки, чтобы создать класс-посредник, указав (по крайней мере) URL-адрес для веб-службы сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="a5049-112">From a command prompt, use Wsdl.exe to create a proxy class, specifying (at a minimum) the URL to the Report Server Web service.</span></span>  
  
     <span data-ttu-id="a5049-113">Например, следующая инструкция командной строки указывает URL-адрес для конечной точки управления в веб-службе сервера отчетов:</span><span class="sxs-lookup"><span data-stu-id="a5049-113">For example, the following command prompt statement specifies a URL for the management endpoint of the Report Server Web service:</span></span>  
  
    ```  
    wsdl /language:CS /n:"Microsoft.SqlServer.ReportingServices2010" http://<Server Name>/reportserver/reportservice2010.asmx?wsdl  
    ```  
  
     <span data-ttu-id="a5049-114">Программа WSDL принимает ряд аргументов командной строки для создания прокси-класса.</span><span class="sxs-lookup"><span data-stu-id="a5049-114">The WSDL tool accepts a number of command-prompt arguments for generating a proxy.</span></span> <span data-ttu-id="a5049-115">В предыдущем примере для использования в классе-посреднике указывается язык C# и рекомендуемое пространство имен (чтобы предотвратить конфликт имен в случае использования нескольких конечных точек веб-службы), а затем создается файл кода C# с именем ReportingService2010.cs.</span><span class="sxs-lookup"><span data-stu-id="a5049-115">The preceding example specifies the language C#, a suggested namespace to use in the proxy (to prevent name collision if using more than one Web service endpoint), and generates a C# file called ReportingService2010.cs.</span></span> <span data-ttu-id="a5049-116">Если в примере указать язык [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)], будет создан прокси-файл с именем ReportingService2010.vb.</span><span class="sxs-lookup"><span data-stu-id="a5049-116">If the example had specified [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)], the example would have generated a proxy file with the name ReportingService2010.vb.</span></span> <span data-ttu-id="a5049-117">Этот файл создается в каталоге, из которого запущена команда.</span><span class="sxs-lookup"><span data-stu-id="a5049-117">This file is created in the directory from which you run the command.</span></span>  
  
2.  <span data-ttu-id="a5049-118">Скомпилируйте класс-посредник в файл сборки (с расширением DLL) и создайте в проекте ссылку на сборку или добавьте класс в качестве элемента проекта.</span><span class="sxs-lookup"><span data-stu-id="a5049-118">Compile the proxy class into an assembly file (with the extension .dll) and reference it in your project, or add the class as a project item.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a5049-119">Если класс-посредник добавляется в проект вручную, необходимо добавить ссылку на библиотеку System.Web.Services.dll.</span><span class="sxs-lookup"><span data-stu-id="a5049-119">When you add a proxy class to your project manually, you need to add a reference to System.Web.Services.dll.</span></span> <span data-ttu-id="a5049-120">Если прокси-класс добавляется с помощью веб-ссылки в Visual Studio .NET, то ссылка создается автоматически.</span><span class="sxs-lookup"><span data-stu-id="a5049-120">If you add the proxy using a Web reference in Visual Studio .NET, the reference is automatically created for you.</span></span> <span data-ttu-id="a5049-121">Дополнительные сведения см. в подразделе «Добавление класса-посредника с помощью веб-ссылки в Visual Studio» далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="a5049-121">For more information, see "Adding the Proxy Using a Web Reference in Visual Studio" later in this topic.</span></span>  
  
     <span data-ttu-id="a5049-122">После добавления класса-посредника в качестве элемента проекта в обозревателе решений появляется соответствующий файл.</span><span class="sxs-lookup"><span data-stu-id="a5049-122">After you add the proxy class as an item to your project, the associated file appears in Solution Explorer.</span></span>  
  
3.  <span data-ttu-id="a5049-123">Чтобы вызвать службу программным образом, создайте экземпляр класса-посредника.</span><span class="sxs-lookup"><span data-stu-id="a5049-123">To call the service programmatically, create an instance of the proxy class.</span></span>  
  
     <span data-ttu-id="a5049-124">В следующем примере кода показан синтаксис для создания в проекте экземпляра класса-посредника <xref:ReportService2010.ReportingService2010>.</span><span class="sxs-lookup"><span data-stu-id="a5049-124">The following code example shows the syntax for creating an instance of the <xref:ReportService2010.ReportingService2010> proxy class in a project:</span></span>  
  
```vb  
Dim service As New ReportingService2010()  
```  
  
```csharp  
ReportingService2010 service = new ReportingService2010();  
  
```  
  
 <span data-ttu-id="a5049-125">Дополнительные сведения о программе Wsdl.exe, включая полный синтаксис, см. в разделе «Программа WSDL» документации по пакету SDK для [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a5049-125">For more information about the Wsdl.exe tool, including its full syntax, see "Web Services Description Language Tool" in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK documentation.</span></span> <span data-ttu-id="a5049-126">Полное описание прокси для веб-служб см. в разделе «Создание прокси для веб-служб с поддержкой XML» документации по пакету SDK для [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a5049-126">For a full explanation of Web service proxies, see "Creating an XML Web Service Proxy" in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK documentation.</span></span>  
  
## <a name="adding-the-proxy-using-a-web-reference-in-visual-studio"></a><span data-ttu-id="a5049-127">Добавление учетной записи-посредника с помощью веб-ссылки в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a5049-127">Adding the Proxy Using a Web Reference in Visual Studio</span></span>  
 <span data-ttu-id="a5049-128">Веб-ссылка позволяет проекту использовать одну или несколько веб-служб.</span><span class="sxs-lookup"><span data-stu-id="a5049-128">A Web reference enables a project to consume one or more Web services.</span></span> <span data-ttu-id="a5049-129">Среда [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] позволяет пользователям добавлять в проекты ссылки на веб-службы с помощью нескольких простых действий.</span><span class="sxs-lookup"><span data-stu-id="a5049-129">[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] enables users to add Web service references to projects by following a few simple steps.</span></span>  
  
 <span data-ttu-id="a5049-130">**Добавление веб-ссылки в проект**</span><span class="sxs-lookup"><span data-stu-id="a5049-130">**To add a Web reference to a project**</span></span>  
  
1.  <span data-ttu-id="a5049-131">В **обозревателе решений** выберите проект, который будет использовать веб-службу.</span><span class="sxs-lookup"><span data-stu-id="a5049-131">In **Solution Explorer**, select the project that will consume the Web service.</span></span>  
  
2.  <span data-ttu-id="a5049-132">В меню **Проект** выберите пункт **Добавить веб-ссылку**.</span><span class="sxs-lookup"><span data-stu-id="a5049-132">On the **Project** menu, click **Add Web Reference**.</span></span>  
  
     <span data-ttu-id="a5049-133">Откроется диалоговое окно **Добавление веб-ссылки**.</span><span class="sxs-lookup"><span data-stu-id="a5049-133">The **Add Web Reference** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="a5049-134">В поле **URL-адрес** введите полный путь к веб-службе сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="a5049-134">In the **URL** field, enter the complete path to the Report Server Web service.</span></span>  
  
     <span data-ttu-id="a5049-135">Упрощенный URL-адрес конечной точки выполнения отчета для веб-службы сервера отчетов может иметь следующий вид:</span><span class="sxs-lookup"><span data-stu-id="a5049-135">A simplified URL for the report execution endpoint of the Report Server Web service might look like this:</span></span>  
  
    ```  
    http://<Server Name>/reportserver/reportexecution2005.asmx  
    ```  
  
     <span data-ttu-id="a5049-136">URL-адрес содержит домен, в котором развернута веб-служба сервера отчетов, имя папки, содержащей службу, и имя файла обнаружения для службы.</span><span class="sxs-lookup"><span data-stu-id="a5049-136">The URL contains the domain in which the Report Server Web service is deployed, the name of the folder containing the service, and the name of the discovery file for the service.</span></span> <span data-ttu-id="a5049-137">Полное описание различных элементов URL-адреса см. в разделе [Доступ к API-интерфейсу SOAP](../accessing-the-soap-api.md).</span><span class="sxs-lookup"><span data-stu-id="a5049-137">For a complete description of the different URL elements, see [Accessing the SOAP API](../accessing-the-soap-api.md).</span></span>  
  
     <span data-ttu-id="a5049-138">Описание методов и свойств, предоставляемых веб-службой, появляется слева в панели браузера.</span><span class="sxs-lookup"><span data-stu-id="a5049-138">A description of the methods and properties provided by the Web service appears in the Browser pane on the left.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a5049-139">Дополнительные сведения об элементах, связанных с веб-службой сервера отчетов, см. в разделе [Методы веб-службы сервера отчетов](../methods/report-server-web-service-methods.md).</span><span class="sxs-lookup"><span data-stu-id="a5049-139">For more information about the items associated with the Report Server Web service, see [Report Server Web Service Methods](../methods/report-server-web-service-methods.md).</span></span>  
  
4.  <span data-ttu-id="a5049-140">Убедитесь, что проект может использовать веб-службу сервера отчетов, а также в наличии необходимых разрешений для доступа к серверу отчетов.</span><span class="sxs-lookup"><span data-stu-id="a5049-140">Verify that your project can use the Report Server Web service, and that you have appropriate permission to access the report server.</span></span>  
  
5.  <span data-ttu-id="a5049-141">В поле **Имя веб-ссылки** введите имя, которое будет использоваться в коде для программного доступа к веб-службе сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="a5049-141">In the **Web reference name** field, enter a name that you will use in your code to access the Report Server Web service programmatically.</span></span>  
  
6.  <span data-ttu-id="a5049-142">Нажмите кнопку **Добавить ссылку**, чтобы создать в приложении ссылку на веб-службу.</span><span class="sxs-lookup"><span data-stu-id="a5049-142">Select the **Add Reference** button to create a reference in your application to the Web service.</span></span>  
  
     <span data-ttu-id="a5049-143">Новая ссылка появится в **обозревателе решений** в узле "Веб-ссылки" для активного проекта и будет иметь имя, указанное в поле **Имя веб-ссылки**.</span><span class="sxs-lookup"><span data-stu-id="a5049-143">The new reference appears in **Solution Explorer** under the Web References node for the active project, named as specified in the **Web reference name** field.</span></span>  
  
7.  <span data-ttu-id="a5049-144">В **обозревателе решений** разверните папку "Веб-ссылки", чтобы показать пространство имен для классов веб-ссылки, которые доступны элементам проекта.</span><span class="sxs-lookup"><span data-stu-id="a5049-144">In **Solution Explorer**, expand the Web References folder to note the namespace for the Web reference classes that are available to the items in your project.</span></span>  
  
     <span data-ttu-id="a5049-145">После добавления веб-ссылки в проект соответствующие файлы отображаются в папке, входящей в папку "Веб-ссылки" **обозревателя решений**.</span><span class="sxs-lookup"><span data-stu-id="a5049-145">After adding a Web reference to your project, the associated files are displayed in a folder within the Web References folder of **Solution Explorer**.</span></span>  
  
 <span data-ttu-id="a5049-146">После добавления веб-ссылки используйте следующий код для создания экземпляра класса-посредника:</span><span class="sxs-lookup"><span data-stu-id="a5049-146">After you add the Web reference, use the following syntax to create an instance of the proxy class:</span></span>  
  
```vb  
Dim rs As New myNamespace.myReferenceName.ReportExecutionService()  
rs.Url = "http://<Server Name>/reportserver/reportexecution2005.asmx?wsdl"  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
```  
  
```csharp  
myNamespace.myReferenceName.ReportExecutionService rs = new myNamespace.myReferenceName.ReportExecutionService();  
rs.Url = "http://<Server Name>/reportserver/reportexecution2005.asmx?wsdl"  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
  
```  
  
 <span data-ttu-id="a5049-147">Также можно добавить директиву **using** (**Import** в [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) в ссылку на веб-службу сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="a5049-147">You can also add a **using** (**Import** in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) directive to the Report Server Web service reference.</span></span> <span data-ttu-id="a5049-148">Если применить эту директиву, нет необходимости полностью уточнять типы пространства имен.</span><span class="sxs-lookup"><span data-stu-id="a5049-148">If you use this directive, you do not need to fully qualify the types in the namespace.</span></span> <span data-ttu-id="a5049-149">Для этого добавьте в файл следующий код:</span><span class="sxs-lookup"><span data-stu-id="a5049-149">To do this, add the following code to your file:</span></span>  
  
```vb  
Import myNamespace.myReferenceName  
```  
  
```csharp  
using myNamespace.myReferenceName;  
```  
  
## <a name="see-also"></a><span data-ttu-id="a5049-150">См. также:</span><span class="sxs-lookup"><span data-stu-id="a5049-150">See Also</span></span>  
 <span data-ttu-id="a5049-151">[Веб-служба сервера отчетов](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="a5049-151">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 <span data-ttu-id="a5049-152">[Создание приложений с помощью веб-службы и .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="a5049-152">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 [<span data-ttu-id="a5049-153">Технический справочник (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="a5049-153">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
