---
title: Синтаксис запроса XML для XML-данных отчета (службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- namespaces [Reporting Services]
- data processing extensions [Reporting Services], data sources
- xmldp [Reporting Services]
- XML [Reporting Services], data retrieval
ms.assetid: d203886f-faa1-4a02-88f5-dd4c217181ef
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 62dde2b3ab18b5edb5c3786d39173fea3a0854ac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654819"
---
# <a name="xml-query-syntax-for-xml-report-data-ssrs"></a><span data-ttu-id="0d2c8-102">Синтаксис запроса XML для XML-данных отчета (SSRS)</span><span class="sxs-lookup"><span data-stu-id="0d2c8-102">XML Query Syntax for XML Report Data (SSRS)</span></span>
  <span data-ttu-id="0d2c8-103">В службах [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]можно создавать наборы данных для источников XML-данных.</span><span class="sxs-lookup"><span data-stu-id="0d2c8-103">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can create datasets for XML data sources.</span></span> <span data-ttu-id="0d2c8-104">После определения источника данных можно создать запрос для получения набора данных.</span><span class="sxs-lookup"><span data-stu-id="0d2c8-104">After you define a data source, you create a query for the dataset.</span></span> <span data-ttu-id="0d2c8-105">В зависимости от типа XML-данных, на которые указывает источник данных, этот запрос создается путем включения либо элемента XML `Query`, либо пути к элементу.</span><span class="sxs-lookup"><span data-stu-id="0d2c8-105">Depending on the type of XML data pointed to by the data source, you create the dataset query by including an XML `Query` or an element path.</span></span> <span data-ttu-id="0d2c8-106">XML `Query` начинается с **\<Query>** тега и включает пространства имен и XML-элементы, которые зависят от источника данных.</span><span class="sxs-lookup"><span data-stu-id="0d2c8-106">An XML `Query` starts with a **\<Query>** tag and includes namespaces and XML elements that vary depending on the data source.</span></span> <span data-ttu-id="0d2c8-107">Путь к элементу не зависит от пространства имен и указывает необходимые узлы и атрибуты узлов в базовых XML-данных при помощи XPath-подобного синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="0d2c8-107">An element path is namespace-independent and specifies which nodes and node attributes to use from the underlying XML data with an XPath-like syntax.</span></span> <span data-ttu-id="0d2c8-108">Дополнительные сведения о путях к элементу см. в разделе [Синтаксис пути к элементу для XML-данных отчета (службы SSRS)](report-data-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0d2c8-108">For more information about element paths, see [Element Path Syntax for XML Report Data &#40;SSRS&#41;](report-data-ssrs.md).</span></span>  
  
 <span data-ttu-id="0d2c8-109">Источник данных XML можно создать для следующих типов XML-данных:</span><span class="sxs-lookup"><span data-stu-id="0d2c8-109">You can create an XML data source for the following types of XML data:</span></span>  
  
-   <span data-ttu-id="0d2c8-110">XML-документы, на которые указывает URL-адрес по протоколу HTTP;</span><span class="sxs-lookup"><span data-stu-id="0d2c8-110">Xml documents pointed to by a URL using http protocol</span></span>  
  
-   <span data-ttu-id="0d2c8-111">конечные точки веб-службы, возвращающей XML-данные;</span><span class="sxs-lookup"><span data-stu-id="0d2c8-111">Web service endpoints that return XML data</span></span>  
  
-   <span data-ttu-id="0d2c8-112">встроенные XML-данные.</span><span class="sxs-lookup"><span data-stu-id="0d2c8-112">Embedded XML data</span></span>  
  
 <span data-ttu-id="0d2c8-113">Способ указания элемента XML `Query` или пути к элементу зависит от типа XML-данных.</span><span class="sxs-lookup"><span data-stu-id="0d2c8-113">How you specify an XML `Query` or an element path depends on the type of XML data.</span></span>  
  
 <span data-ttu-id="0d2c8-114">Для XML-документа элемент XML `Query` необязателен.</span><span class="sxs-lookup"><span data-stu-id="0d2c8-114">For an XML document, the XML `Query` is optional.</span></span> <span data-ttu-id="0d2c8-115">Если он включен, то может содержать необязательный элемент XML `ElementPath`.</span><span class="sxs-lookup"><span data-stu-id="0d2c8-115">If it is included, it can contain an optional XML `ElementPath`.</span></span> <span data-ttu-id="0d2c8-116">В значении элемента XML `ElementPath` используется синтаксис пути к элементу.</span><span class="sxs-lookup"><span data-stu-id="0d2c8-116">The value of the XML `ElementPath` uses the element path syntax.</span></span> <span data-ttu-id="0d2c8-117">Элементы XML `Query` и XML `ElementPath` включаются, чтобы обеспечить правильную обработку пространства имен, если это нужно для XML-данных источника данных.</span><span class="sxs-lookup"><span data-stu-id="0d2c8-117">You include the XML `Query` and XML `ElementPath` to process namespaces correctly when it is needed by the XML data from the data source.</span></span>  
  
 <span data-ttu-id="0d2c8-118">Для конечной точки веб-службы, на которую указывает URL-адрес строки соединения, элемент XML `Query` определяет метод веб-службы, действие SOAP или и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="0d2c8-118">For a Web service endpoint pointed to by a connection string URL, the XML `Query` defines either the Web service method, the SOAP action, or both.</span></span> <span data-ttu-id="0d2c8-119">Поставщик XML-данных создает запрос веб-службы, который получает XML-данные для отчета.</span><span class="sxs-lookup"><span data-stu-id="0d2c8-119">The XML data provider creates a Web service request that retrieves XML data to use for the report.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0d2c8-120">Если пространство имен веб-службы содержит символ косой черты (`/)`, включите как метод веб-службы, так и действие SOAP, чтобы модуль обработки XML-данных мог правильно определить пространство имен.</span><span class="sxs-lookup"><span data-stu-id="0d2c8-120">When a Web service namespace includes a forward slash (`/)` character, include both the Web service method and the SOAP action so that the XML data processing extension can derive the namespace correctly.</span></span>  
  
 <span data-ttu-id="0d2c8-121">Для встроенных XML-документов элемент XML `Query` определяет встроенные XML-данные, включает дополнительные пространства имен и содержит необязательный элемент XML `ElementPath`.</span><span class="sxs-lookup"><span data-stu-id="0d2c8-121">For an embedded XML document, the XML `Query` defines the embedded XML data to use, includes optional namespaces, and contains an optional XML `ElementPath`..</span></span>  
  
## <a name="specifying-query-parameters-for-xml-data"></a><span data-ttu-id="0d2c8-122">Указание параметров запроса XML-данных</span><span class="sxs-lookup"><span data-stu-id="0d2c8-122">Specifying Query Parameters for XML Data</span></span>  
 <span data-ttu-id="0d2c8-123">Для XML-документов можно указать параметры запроса.</span><span class="sxs-lookup"><span data-stu-id="0d2c8-123">You can specify query parameters for XML documents.</span></span>  
  
-   <span data-ttu-id="0d2c8-124">Параметры включаются в URL-адрес как стандартные URL-параметры.</span><span class="sxs-lookup"><span data-stu-id="0d2c8-124">For URL requests, the query parameters are included as standard URL parameters.</span></span>  
  
-   <span data-ttu-id="0d2c8-125">В случае запросов к веб-службе параметры запросов передаются методу веб-службы.</span><span class="sxs-lookup"><span data-stu-id="0d2c8-125">For Web service requests, query parameters are passed to the Web service method.</span></span> <span data-ttu-id="0d2c8-126">Для определения параметра запроса используется страница **Параметры** диалогового окна **Свойства набора данных** .</span><span class="sxs-lookup"><span data-stu-id="0d2c8-126">To define a query parameter, use the **Parameters** page of the **Dataset Properties** dialog box.</span></span> <span data-ttu-id="0d2c8-127">Дополнительные сведения см. в статье [Диалоговое окно "Свойства набора данных" — "Параметры"](dataset-properties-dialog-box-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="0d2c8-127">For more information, see [Dataset Properties Dialog Box, Parameters](dataset-properties-dialog-box-parameters.md).</span></span>  
  
### <a name="example"></a><span data-ttu-id="0d2c8-128">Пример</span><span class="sxs-lookup"><span data-stu-id="0d2c8-128">Example</span></span>  
 <span data-ttu-id="0d2c8-129">Примеры, представленные в следующей таблице, иллюстрируют получение данных от веб-службы сервера отчетов, из XML-документа, а также встроенных XML-данных.</span><span class="sxs-lookup"><span data-stu-id="0d2c8-129">The examples in the following table illustrate how to retrieve data from the Report Server Web service, an XML document, and embedded XML data.</span></span>  
  
|<span data-ttu-id="0d2c8-130">Источник данных XML</span><span class="sxs-lookup"><span data-stu-id="0d2c8-130">XML data source</span></span>|<span data-ttu-id="0d2c8-131">Пример запроса</span><span class="sxs-lookup"><span data-stu-id="0d2c8-131">Query example</span></span>|  
|---------------------|-------------------|  
|<span data-ttu-id="0d2c8-132">XML-данные веб-службы с помощью метода ListChildren .</span><span class="sxs-lookup"><span data-stu-id="0d2c8-132">Web service XML data from ListChildren method.</span></span>|`<Query>`<br /><br /> `<Method Name="ListChildren" Namespace="https://schemas.microsoft.com/sqlserver/2005/06/30/reporting/reportingservices" />`<br /><br /> `</Query>`|  
|<span data-ttu-id="0d2c8-133">XML-данные веб-службы при помощи действия SoapAction.</span><span class="sxs-lookup"><span data-stu-id="0d2c8-133">Web service XML data from SoapAction.</span></span>|`<Query xmlns=namespace>`<br /><br /> `<SoapAction>http://schemas/microsoft.com/sqlserver/2005/03/23/reporting/reportingservices/ListChildren</SoapAction>`<br /><br /> `</Query>`|  
|<span data-ttu-id="0d2c8-134">XML-документ или внедренные XML-данные, использующие пространства имен.</span><span class="sxs-lookup"><span data-stu-id="0d2c8-134">XML Document or embedded XML data that uses namespaces.</span></span><br /><br /> <span data-ttu-id="0d2c8-135">Элемент запроса, задающий пространства имен для пути к элементу.</span><span class="sxs-lookup"><span data-stu-id="0d2c8-135">Query element specifying namespaces for an element path.</span></span>|`<Query xmlns:es="https://schemas.microsoft.com/StandardSchemas/ExtendedSales">`<br /><br /> `<ElementPath>/Customers/Customer/Orders/Order/es:LineItems/es:LineItem</ElementPath>`<br /><br /> `</Query>`|  
|<span data-ttu-id="0d2c8-136">Встроенный XML-документ.</span><span class="sxs-lookup"><span data-stu-id="0d2c8-136">Embedded XML document.</span></span>|`<Query>`<br /><br /> `<XmlData>`<br /><br /> `<Customers>`<br /><br /> `<Customer ID="1">Bobby</Customer>`<br /><br /> `</Customers>`<br /><br /> `</XmlData>`<br /><br /> `<ElementPath>Customer {@}</ElementPath>`<br /><br /> `</Query>`|  
|<span data-ttu-id="0d2c8-137">XML-документ, использующий значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0d2c8-137">XML document that uses default.</span></span>|<span data-ttu-id="0d2c8-138">*No query*.</span><span class="sxs-lookup"><span data-stu-id="0d2c8-138">*No query*.</span></span><br /><br /> <span data-ttu-id="0d2c8-139">Путь к элементу определяется на основе самого XML-документа и не зависит от пространства имен.</span><span class="sxs-lookup"><span data-stu-id="0d2c8-139">The element path is derived from the XML document itself and is namespace-independent.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="0d2c8-140">Первый пример веб-службы перечисляет содержимое сервера отчетов, применяющего метод <xref:ReportService2006.ReportingService2006.ListChildren%2A> .</span><span class="sxs-lookup"><span data-stu-id="0d2c8-140">The first Web service example lists the contents of the report server that uses the <xref:ReportService2006.ReportingService2006.ListChildren%2A> method.</span></span> <span data-ttu-id="0d2c8-141">Для выполнения этого запроса необходимо создать новый источник данных и задать строку подключения: http://localhost/reportserver/reportservice2006.asmx.</span><span class="sxs-lookup"><span data-stu-id="0d2c8-141">To run this query, you must create a new data source and set the connection string to http://localhost/reportserver/reportservice2006.asmx.</span></span> <span data-ttu-id="0d2c8-142">Метод <xref:ReportService2006.ReportingService2006.ListChildren%2A> имеет два параметра: `Item` и `Recursive`.</span><span class="sxs-lookup"><span data-stu-id="0d2c8-142">The <xref:ReportService2006.ReportingService2006.ListChildren%2A> method takes two parameters: `Item` and `Recursive`.</span></span> <span data-ttu-id="0d2c8-143">Для `Item` установите значение по умолчанию `/`, а для параметра `Recursive` — значение `1`.</span><span class="sxs-lookup"><span data-stu-id="0d2c8-143">Set the default value for `Item` to `/` and `Recursive` to `1`.</span></span>  
  
## <a name="specifying-namespaces"></a><span data-ttu-id="0d2c8-144">Указание пространств имен</span><span class="sxs-lookup"><span data-stu-id="0d2c8-144">Specifying Namespaces</span></span>  
 <span data-ttu-id="0d2c8-145">Для указания пространств имен, используемых XML-данными из источника данных, используется элемент XML `Query`.</span><span class="sxs-lookup"><span data-stu-id="0d2c8-145">Use the XML `Query` element to specify the namespaces that are used in the XML data from the data source.</span></span> <span data-ttu-id="0d2c8-146">Следующий XML-запрос использует пространство имен `sales`.</span><span class="sxs-lookup"><span data-stu-id="0d2c8-146">The following XML query uses the namespace `sales`.</span></span> <span data-ttu-id="0d2c8-147">Узлы XML `ElementPath` для элементов `sales:LineItems` и `sales:LineItem` используют пространство имен `sales`.</span><span class="sxs-lookup"><span data-stu-id="0d2c8-147">The XML `ElementPath` nodes for `sales:LineItems` and `sales:LineItem` use the namespace `sales`.</span></span>  
  
```  
<Query xmlns:sales=  
"https://schemas.microsoft.com/StandardSchemas/ExtendedSales">  
   <SoapAction>  
      https://schemas.microsoft.com/SalesWebService/ListOrders   
   </SoapAction>  
   <ElementPath>  
      Customers/Customer/Orders/Order/sales:LineItems/sales:LineItem  
   </ElementPath>  
</Query>  
```  
  
 <span data-ttu-id="0d2c8-148">Чтобы указать пространство имен поставщика данных, оставив пространство имен по умолчанию пустым, используется `xmldp`.</span><span class="sxs-lookup"><span data-stu-id="0d2c8-148">To specify the data provider namespace so that the default namespace remains empty, use `xmldp`.</span></span> <span data-ttu-id="0d2c8-149">Эти действия показаны в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="0d2c8-149">This is shown in the following example.</span></span>  
  
### <a name="example"></a><span data-ttu-id="0d2c8-150">Пример</span><span class="sxs-lookup"><span data-stu-id="0d2c8-150">Example</span></span>  
 <span data-ttu-id="0d2c8-151">В следующих примерах используется XML-документ DPNamespace.xml, который для наглядности приводится после таблицы.</span><span class="sxs-lookup"><span data-stu-id="0d2c8-151">The following examples use the XML document DPNamespace.xml, which is provided for illustration after the table.</span></span> <span data-ttu-id="0d2c8-152">В таблице представлены два примера синтаксиса пути XML ElementPath, включающие префиксы пространства имен.</span><span class="sxs-lookup"><span data-stu-id="0d2c8-152">This table shows two examples of XML ElementPath syntax that includes namespace prefixes.</span></span>  
  
|<span data-ttu-id="0d2c8-153">Элемент XML-запроса</span><span class="sxs-lookup"><span data-stu-id="0d2c8-153">XML Query Element</span></span>|<span data-ttu-id="0d2c8-154">Полученные в результате поля набора данных</span><span class="sxs-lookup"><span data-stu-id="0d2c8-154">Resulting fields in the dataset</span></span>|  
|-----------------------|-------------------------------------|  
|\<Query/>|<span data-ttu-id="0d2c8-155">Значение A: `https://schemas.microsoft.com/..` .</span><span class="sxs-lookup"><span data-stu-id="0d2c8-155">Value A: `https://schemas.microsoft.com/..`.</span></span><br /><br /> <span data-ttu-id="0d2c8-156">Значение б: `https://schemas.microsoft.com/..` .</span><span class="sxs-lookup"><span data-stu-id="0d2c8-156">Value B: `https://schemas.microsoft.com/..`.</span></span><br /><br /> <span data-ttu-id="0d2c8-157">Значение C: `https://schemas.microsoft.com/.` ..</span><span class="sxs-lookup"><span data-stu-id="0d2c8-157">Value C: `https://schemas.microsoft.com/.`..</span></span>|  
|\<xmldp:Query xmlns:xmldp="https://schemas.microsoft.com/sqlserver/2005/02/reporting/XmlDPQuery" xmlns:ns="https://schemas.microsoft.com/..."><br /><br /> <span data-ttu-id="0d2c8-158">\<xmldp:ElementPath>Корневой {} /НС: Element2/node\</xmldp:ElementPath></span><span class="sxs-lookup"><span data-stu-id="0d2c8-158">\<xmldp:ElementPath>Root {}/ns:Element2/Node\</xmldp:ElementPath></span></span><br /><br /> \</xmldp:Query>|<span data-ttu-id="0d2c8-159">Значение D</span><span class="sxs-lookup"><span data-stu-id="0d2c8-159">Value D</span></span><br /><br /> <span data-ttu-id="0d2c8-160">Значение E</span><span class="sxs-lookup"><span data-stu-id="0d2c8-160">Value E</span></span><br /><br /> <span data-ttu-id="0d2c8-161">Значение F</span><span class="sxs-lookup"><span data-stu-id="0d2c8-161">Value F</span></span>|  
  
#### <a name="xml-document-dpnamespacexml"></a><span data-ttu-id="0d2c8-162">XML-документ: DPNamespace.xml</span><span class="sxs-lookup"><span data-stu-id="0d2c8-162">XML document: DPNamespace.xml</span></span>  
 <span data-ttu-id="0d2c8-163">Можно скопировать этот XML-документ и сохранить его по URL-адресу, который конструктор отчетов будет использовать в качестве источника XML-данных, например http://localhost/DPNamespace.xml.</span><span class="sxs-lookup"><span data-stu-id="0d2c8-163">You can copy this XML and save it to a URL available for Report Designer to use as an XML data source: for example, http://localhost/DPNamespace.xml.</span></span>  
  
```  
<Root xmlns:ns="https://schemas.microsoft.com/...">  
   <ns:Element1>  
      <Node>Value A</Node>  
      <Node>Value B</Node>  
      <Node>Value C</Node>  
   </ns:Element1>  
   <ns:Element2>  
      <Node>Value D</Node>  
      <Node>Value E</Node>  
      <Node>Value F</Node>  
   </ns:Element2>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0d2c8-164">См. также:</span><span class="sxs-lookup"><span data-stu-id="0d2c8-164">See Also</span></span>  
 <span data-ttu-id="0d2c8-165">[Тип подключения XML &#40;SSRS&#41;](xml-connection-type-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0d2c8-165">[XML Connection Type &#40;SSRS&#41;](xml-connection-type-ssrs.md) </span></span>  
 [<span data-ttu-id="0d2c8-166">Учебники по службам Reporting Services (SSRS)</span><span class="sxs-lookup"><span data-stu-id="0d2c8-166">Reporting Services Tutorials &#40;SSRS&#41;</span></span>](../reporting-services-tutorials-ssrs.md)  
  
  
