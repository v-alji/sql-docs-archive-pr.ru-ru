---
title: Использование результатов FOR XML в коде приложений | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, application code usage
- XML [SQL Server], FOR XML clause
- ASP.NET [SQL Server]
- .NET Framework [SQL Server], FOR XML data
- ADO [SQL Server]
- XML data islands [SQL Server]
- data islands [SQL Server]
ms.assetid: 41ae67bd-ece9-49ea-8062-c8d658ab4154
author: rothja
ms.author: jroth
ms.openlocfilehash: 3cabe7e65cb53a28a370615ed84e38ba2b8db44c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667604"
---
# <a name="use-for-xml-results-in-application-code"></a><span data-ttu-id="e5851-102">Использование результатов FOR XML в коде приложений</span><span class="sxs-lookup"><span data-stu-id="e5851-102">Use FOR XML Results in Application Code</span></span>
  <span data-ttu-id="e5851-103">При помощи предложения FOR XML в SQL-запросах можно получать и даже преобразовывать результаты запросов в формат XML.</span><span class="sxs-lookup"><span data-stu-id="e5851-103">By using FOR XML clauses with SQL queries, you can retrieve and even cast query results as XML data.</span></span> <span data-ttu-id="e5851-104">Если приложение способно обрабатывать XML-данные, эта возможность позволяет выполнять следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="e5851-104">This functionality allows you to do the following when FOR XML query results can be used in XML application code:</span></span>  
  
-   <span data-ttu-id="e5851-105">Запрашивать из таблиц SQL экземпляры значений [данных XML (SQL Server)](xml-data-sql-server.md)</span><span class="sxs-lookup"><span data-stu-id="e5851-105">Query SQL tables for instances of [XML Data &#40;SQL Server&#41;](xml-data-sql-server.md) values</span></span>  
  
-   <span data-ttu-id="e5851-106">Применять [TYPE Directive in FOR XML Queries](type-directive-in-for-xml-queries.md) для возврата результата запроса, содержащего текст или двоичные данные, в формате XML</span><span class="sxs-lookup"><span data-stu-id="e5851-106">Apply the [TYPE Directive in FOR XML Queries](type-directive-in-for-xml-queries.md) to return the result of queries that contain text or image typed data as XML</span></span>  
  
 <span data-ttu-id="e5851-107">В этом подразделе содержатся примеры, демонстрирующие перечисленные возможности.</span><span class="sxs-lookup"><span data-stu-id="e5851-107">This topic provides examples that demonstrate these approaches.</span></span>  
  
## <a name="retrieving-for-xml-data-with-ado-and-xml-data-islands"></a><span data-ttu-id="e5851-108">Получение данных FOR XML при использовании ADO и островов XML-данных</span><span class="sxs-lookup"><span data-stu-id="e5851-108">Retrieving FOR XML Data with ADO and XML Data Islands</span></span>  
 <span data-ttu-id="e5851-109">Результаты, возвращаемые запросами FOR XML, могут быть сохранены объектом `Stream` ADO или другим объектом, поддерживающим COM-интерфейс `IStream` (например, объектами ASP `Request` и `Response`).</span><span class="sxs-lookup"><span data-stu-id="e5851-109">The ADO `Stream` object or other objects that support the COM `IStream` interface, such as the Active Server Pages (ASP) `Request` and `Response` objects, can be used to contain the results when you are working with FOR XML queries.</span></span>  
  
 <span data-ttu-id="e5851-110">Например, следующий код ASP отображает результаты запроса к столбцу Demographics типа `xml` таблицы Sales.Store в образце в базе данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="e5851-110">For example, the following ASP code shows the results of querying an `xml` data type column, Demographics, in the Sales.Store table of the AdventureWorks sample database.</span></span> <span data-ttu-id="e5851-111">В частности, запрос производит поиск значения столбца для строки, в которой значение CustomerID равно 3.</span><span class="sxs-lookup"><span data-stu-id="e5851-111">Specifically, the query looks for the instance value of this column for the row where the CustomerID is equal to 3.</span></span>  
  
```  
<!-- BeginRecordAndStreamVBS -->  
<%@ LANGUAGE = VBScript %>  
<!-- %  Option Explicit      % -->  
<!-- 'Request.ServerVariables("SERVER_NAME") & ";" & _ -->  
<HTML>  
<HEAD>  
<META NAME="GENERATOR" Content="Microsoft Developer Studio"/>  
<META HTTP-EQUIV="Content-Type" content="text/html"; charset="iso-8859-1">  
<TITLE>FOR XML Query Example</TITLE>  
<STYLE>  
   BODY  
   {  
      FONT-FAMILY: Tahoma;  
      FONT-SIZE: 8pt;  
      OVERFLOW: auto  
   }  
   H3  
   {  
      FONT-FAMILY: Tahoma;  
      FONT-SIZE: 8pt;  
      OVERFLOW: auto  
   }  
</STYLE>  
  
<!-- #include file="adovbs.inc" -->  
<%  
   Response.Write "<H3>Server-side processing</H3>"  
   Response.Write "Page Generated @ " & Now() & "<BR/>"  
   Dim adoConn  
   Set adoConn = Server.CreateObject("ADODB.Connection")  
   Dim sConn  
   sConn = "Provider=SQLOLEDB;Data Source=(local);" & _  
            "Initial Catalog=AdventureWorks;Integrated Security=SSPI;"  
   Response.write "Connect String = " & sConn & "<BR/>"  
   adoConn.ConnectionString = sConn  
   adoConn.CursorLocation = adUseClient  
   adoConn.Open  
   Response.write "ADO Version = " & adoConn.Version & "<BR/>"  
   Response.write "adoConn.State = " & adoConn.State & "<BR/>"  
   Dim adoCmd  
   Set adoCmd = Server.CreateObject("ADODB.Command")  
   Set adoCmd.ActiveConnection = adoConn  
   Dim sQuery  
   sQuery = "<ROOT xmlns:sql='urn:schemas-microsoft-com:xml-sql'><sql:query>SELECT Demographics from Sales.Store WHERE CustomerID = 3 FOR XML AUTO</sql:query></ROOT>"  
   Response.write "Query String = " & sQuery & "<BR/>"  
   Dim adoStreamQuery  
   Set adoStreamQuery = Server.CreateObject("ADODB.Stream")  
   adoStreamQuery.Open  
   adoStreamQuery.WriteText sQuery, adWriteChar  
   adoStreamQuery.Position = 0  
   adoCmd.CommandStream = adoStreamQuery  
   adoCmd.Dialect = "{5D531CB2-E6Ed-11D2-B252-00C04F681B71}"  
   Response.write "Pushing XML to client for processing "  & "<BR/>"  
   adoCmd.Properties("Output Stream") = Response  
   Response.write "<XML ID='MyDataIsle'>"  
   adoCmd.Execute , , 1024  
   Response.write "</XML>"  
%>  
<SCRIPT language="VBScript" For="window" Event="onload">  
   Dim xmlDoc  
   Set xmlDoc = MyDataIsle.XMLDocument  
   Dim root  
   Set root = xmlDoc.documentElement.childNodes.Item(0).childNodes.Item(0).childNodes.Item(0)  
   For each child in root.childNodes  
      dim OutputXML  
      OutputXML = document.all("log").innerHTML  
      document.all("log").innerHTML = OutputXML & "<LI><B>" & child.nodeName &  ":</B>  " & child.Text  & "</LI>"  
   Next  
   MsgBox xmlDoc.xml  
</SCRIPT>  
</HEAD>  
<BODY>  
   <H3>Client-side processing of XML Document MyDataIsle</H3>  
   <UL id=log>  
   </UL>  
</BODY>  
</HTML>  
<!-- EndRecordAndStreamVBS -->  
```  
  
 <span data-ttu-id="e5851-112">Этот пример ASP-страницы содержит работающий на стороне сервера скрипт VBScript, выполняющий запрос FOR XML через ADO и возвращающий результат в виде острова XML-данных с именем MyDataIsle.</span><span class="sxs-lookup"><span data-stu-id="e5851-112">This example ASP page contains server-side VBScript that uses ADO to execute the FOR XML query and return the XML results in an XML data island, MyDataIsle.</span></span> <span data-ttu-id="e5851-113">Затем этот остров XML-данных возвращается браузеру и подвергается дополнительной обработке на стороне клиента</span><span class="sxs-lookup"><span data-stu-id="e5851-113">This XML data island is then returned in the browser for additional client-side processing.</span></span> <span data-ttu-id="e5851-114">После этого на стороне клиента дополнительный код скрипта VBScript используется для обработки содержимого острова XML-данных.</span><span class="sxs-lookup"><span data-stu-id="e5851-114">Additional client-side VBScript code is then used to process the contents of the XML data island.</span></span> <span data-ttu-id="e5851-115">После этого этапа обработки содержимое отображается в виде результирующего DHTML и открывается окно сообщения, где отображается обработанное содержимое острова XML-данных.</span><span class="sxs-lookup"><span data-stu-id="e5851-115">This process is performed before displaying the contents as part of the resultant DHTML and opening a message box to show the preprocessed contents of the XML data island.</span></span>  
  
#### <a name="to-test-this-example"></a><span data-ttu-id="e5851-116">Проверка этого примера</span><span class="sxs-lookup"><span data-stu-id="e5851-116">To test this example</span></span>  
  
1.  <span data-ttu-id="e5851-117">Убедитесь, что установлены службы IIS и образец базы данных AdventureWorks для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e5851-117">Verify that IIS is installed and that the AdventureWorks sample database for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has been installed.</span></span>  
  
     <span data-ttu-id="e5851-118">Данному примеру требуются службы IIS версии 5.0 или более поздней, с включенной поддержкой ASP.</span><span class="sxs-lookup"><span data-stu-id="e5851-118">This example requires that Internet Information Services (IIS) version 5.0, or later versions, are installed with ASP support enabled.</span></span> <span data-ttu-id="e5851-119">Кроме того, необходимо установить образец базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="e5851-119">Also, the AdventureWorks sample database has to be installed.</span></span>  
  
2.  <span data-ttu-id="e5851-120">Скопируйте код приведенного выше примера и вставьте его в редактор текста или XML.</span><span class="sxs-lookup"><span data-stu-id="e5851-120">Copy the code example that was previously provided and paste it into the XML or text editor that you use.</span></span> <span data-ttu-id="e5851-121">Сохраните файл под именем RetrieveResults.asp в корневой каталог документов IIS.</span><span class="sxs-lookup"><span data-stu-id="e5851-121">Save the file as RetrieveResults.asp in the root directory that is used for IIS.</span></span> <span data-ttu-id="e5851-122">Обычно это каталог «C:\Inetpub\wwwroot».</span><span class="sxs-lookup"><span data-stu-id="e5851-122">Typically, this is C:Inetpub\wwwroot.</span></span>  
  
3.  <span data-ttu-id="e5851-123">Откройте страницу ASP в окне браузера, указав следующий URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="e5851-123">Open the ASP page in a browser window by using the following URL.</span></span> <span data-ttu-id="e5851-124">Замените «MyServer» на «localhost» или на действительное имя сервера, на котором установлены службы IIS и [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e5851-124">First, replace 'MyServer' with either "localhost" or the actual name of the server where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and IIS are installed.</span></span>  
  
    ```  
    http://MyServer/RetrieveResults.asp  
    ```  
  
 <span data-ttu-id="e5851-125">Результаты, сформированные в виде страниц HTML, будут выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e5851-125">The generated HTML page results that appear will be similar to the following sample output:</span></span>  
  
##### <a name="server-side-processing"></a><span data-ttu-id="e5851-126">Обработка на стороне сервера</span><span class="sxs-lookup"><span data-stu-id="e5851-126">Server-side processing</span></span>  
 <span data-ttu-id="e5851-127">Page Generated \@ 3/11/2006 3:36:02 PM</span><span class="sxs-lookup"><span data-stu-id="e5851-127">Page Generated \@ 3/11/2006 3:36:02 PM</span></span>  
  
 <span data-ttu-id="e5851-128">Connect String = Provider=SQLOLEDB;Data Source=MyServer;Initial Catalog=AdventureWorks;Integrated Security=SSPI;</span><span class="sxs-lookup"><span data-stu-id="e5851-128">Connect String = Provider=SQLOLEDB;Data Source=MyServer;Initial Catalog=AdventureWorks;Integrated Security=SSPI;</span></span>  
  
 <span data-ttu-id="e5851-129">ADO Version = 2.8</span><span class="sxs-lookup"><span data-stu-id="e5851-129">ADO Version = 2.8</span></span>  
  
 <span data-ttu-id="e5851-130">adoConn.State = 1</span><span class="sxs-lookup"><span data-stu-id="e5851-130">adoConn.State = 1</span></span>  
  
 <span data-ttu-id="e5851-131">Query String = SELECT Demographics from Sales.Store WHERE CustomerID = 3 FOR XML AUTO</span><span class="sxs-lookup"><span data-stu-id="e5851-131">Query String = SELECT Demographics from Sales.Store WHERE CustomerID = 3 FOR XML AUTO</span></span>  
  
 <span data-ttu-id="e5851-132">Передача кода XML для обработки на клиенте.</span><span class="sxs-lookup"><span data-stu-id="e5851-132">Pushing XML to client for processing</span></span>  
  
##### <a name="client-side-processing-of-xml-document-mydataisle"></a><span data-ttu-id="e5851-133">Обработка XML-документа MyDataIsle на стороне клиента</span><span class="sxs-lookup"><span data-stu-id="e5851-133">Client-side processing of XML Document MyDataIsle</span></span>  
  
-   <span data-ttu-id="e5851-134">**AnnualSales:** 1500000</span><span class="sxs-lookup"><span data-stu-id="e5851-134">**AnnualSales:** 1500000</span></span>  
  
-   <span data-ttu-id="e5851-135">**AnnualRevenue:** 150000</span><span class="sxs-lookup"><span data-stu-id="e5851-135">**AnnualRevenue:** 150000</span></span>  
  
-   <span data-ttu-id="e5851-136">**BankName:** Primary International</span><span class="sxs-lookup"><span data-stu-id="e5851-136">**BankName:** Primary International</span></span>  
  
-   <span data-ttu-id="e5851-137">**BusinessType:** OS</span><span class="sxs-lookup"><span data-stu-id="e5851-137">**BusinessType:** OS</span></span>  
  
-   <span data-ttu-id="e5851-138">**YearOpened:** 1974</span><span class="sxs-lookup"><span data-stu-id="e5851-138">**YearOpened:** 1974</span></span>  
  
-   <span data-ttu-id="e5851-139">**Specialty:** Дорога</span><span class="sxs-lookup"><span data-stu-id="e5851-139">**Specialty:** Road</span></span>  
  
-   <span data-ttu-id="e5851-140">**SquareFeet:** 38000</span><span class="sxs-lookup"><span data-stu-id="e5851-140">**SquareFeet:** 38000</span></span>  
  
-   <span data-ttu-id="e5851-141">**Brands:** 3</span><span class="sxs-lookup"><span data-stu-id="e5851-141">**Brands:** 3</span></span>  
  
-   <span data-ttu-id="e5851-142">**Internet:** DSL</span><span class="sxs-lookup"><span data-stu-id="e5851-142">**Internet:** DSL</span></span>  
  
-   <span data-ttu-id="e5851-143">**NumberEmployees:** 40</span><span class="sxs-lookup"><span data-stu-id="e5851-143">**NumberEmployees:** 40</span></span>  
  
 <span data-ttu-id="e5851-144">Затем окно сообщения VBScript отобразит следующее содержимое исходного, нефильтрованного массива XML-данных, который был возвращен по запросу FOR XML.</span><span class="sxs-lookup"><span data-stu-id="e5851-144">The VBScript message box will then show the following original, unfiltered XML data island contents that were returned by the FOR XML query results.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Sales.Store>  
    <Demographics>  
      <StoreSurvey xmlns="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/StoreSurvey">  
        <AnnualSales>1500000</AnnualSales>  
        <AnnualRevenue>150000</AnnualRevenue>  
        <BankName>Primary International</BankName>  
        <BusinessType>OS</BusinessType>  
        <YearOpened>1974</YearOpened>  
        <Specialty>Road</Specialty>  
        <SquareFeet>38000</SquareFeet>  
        <Brands>3</Brands>  
        <Internet>DSL</Internet>  
        <NumberEmployees>40</NumberEmployees>  
      </StoreSurvey>  
    </Demographics>  
  </Sales.Store>  
</ROOT>  
```  
  
## <a name="retrieving-for-xml-data-with-aspnet-and-the-net-framework"></a><span data-ttu-id="e5851-145">Получение данных FOR XML при использовании ASP.NET и .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e5851-145">Retrieving FOR XML Data with ASP.NET and the .NET Framework</span></span>  
 <span data-ttu-id="e5851-146">Как и в предыдущем примере, код ASP.NET отображает результаты запроса столбца Demographics типа `xml` из таблицы Sales.Store в образце базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="e5851-146">As in the previous example, the following ASP.NET code shows the results of querying an `xml` data type column, Demographics, in the Sales.Store table of the AdventureWorks sample database.</span></span> <span data-ttu-id="e5851-147">Как и в предыдущем случае, запрос ищет значение этого столбца, соответствующее строке, в которой CustomerID равен значению 3.</span><span class="sxs-lookup"><span data-stu-id="e5851-147">As in the previous example, the query looks for the instance value of this column for the row where the CustomerID is equal to 3.</span></span>  
  
 <span data-ttu-id="e5851-148">В этом примере применяются следующие управляемые интерфейсы прикладных программ (API) Microsoft .NET Framework для возврата и подготовки просмотра результатов запроса FOR XML:</span><span class="sxs-lookup"><span data-stu-id="e5851-148">In this example, the following Microsoft .NET Framework managed APIs are used to accomplish the return and rendering of the FOR XML query results:</span></span>  
  
1.  <span data-ttu-id="e5851-149">Соединение с SQL Server производится через `SqlConnection` по строке соединения, содержащейся в символьной переменной, strConn.</span><span class="sxs-lookup"><span data-stu-id="e5851-149">`SqlConnection` is used to open a connection to SQL Server, based on the contents of a specified connection string variable, strConn.</span></span>  
  
2.  <span data-ttu-id="e5851-150">После этого `SqlDataAdapter`, используя соединение SQL и указанную строку SQL-запроса, выполняет запрос FOR XML.</span><span class="sxs-lookup"><span data-stu-id="e5851-150">`SqlDataAdapter` is then used as the data adapter and it uses the SQL connection and a specified SQL query string to execute the FOR XML query.</span></span>  
  
3.  <span data-ttu-id="e5851-151">После выполнения запроса вызывается метод `SqlDataAdapter.Fill`, который передает экземпляр `DataSet,` MyDataSet, чтобы заполнить набор данных результатами выполнения запроса FOR XML.</span><span class="sxs-lookup"><span data-stu-id="e5851-151">After the query has executed, the `SqlDataAdapter.Fill` method is then called and passed an instance of a `DataSet,` MyDataSet, in order to fill the data set with the output of the FOR XML query.</span></span>  
  
4.  <span data-ttu-id="e5851-152">Затем вызывается метод `DataSet.GetXml`, чтобы вернуть результаты запроса в виде строки, отображаемой на странице HTML, формируемой на сервере.</span><span class="sxs-lookup"><span data-stu-id="e5851-152">The `DataSet.GetXml` method is then called to return the query results as a string that can be displayed in the server-generated HTML page.</span></span>  
  
    ```  
    <%@ Page Language="VB" %>  
    <HTML>  
    <HEAD>  
    <TITLE>FOR XML Query Example</TITLE>  
    <STYLE>  
       BODY  
       {  
          FONT-FAMILY: Tahoma;  
          FONT-SIZE: 8pt;  
          OVERFLOW: auto  
       }  
       H3  
       {  
          FONT-FAMILY: Tahoma;  
          FONT-SIZE: 8pt;  
          OVERFLOW: auto  
       }  
    </STYLE>  
    </HEAD>  
    <BODY>  
    <%  
    Dim s as String  
    s = "<H3>Server-side processing</H3>" & _  
        "Page Generated @ " & Now() & "<BR/>"  
  
    Dim SQL As String   
    SQL = "SELECT Demographics from Sales.Store WHERE CustomerID = 3 FOR XML AUTO"  
  
    Dim strConn As String   
    strConn = "Server=(local);Database=AdventureWorks;Integrated Security=SSPI;"  
  
    Dim MySqlConn As New System.Data.SqlClient.SqlConnection(strConn)  
    Dim MySqlAdapter As New System.Data.SqlClient.SqlDataAdapter(SQL,MySqlConn)  
    Dim MyDataSet As New System.Data.DataSet  
  
    MySqlConn.Open()  
    s = s & "<P>SqlConnection opened.</P>"   
  
    MySqlAdapter.Fill(MyDataSet)  
    s = s & "<P>" & MyDataSet.GetXml  & "</P>"  
  
    MySqlConn.Close()  
    s = s & "<P>SqlConnection closed.</P>"   
  
    Message.InnerHtml=s  
    %>  
    <SPAN id="Message" runat=server />  
    </BODY>  
    </HTML>  
    ```  
  
#### <a name="to-test-this-example"></a><span data-ttu-id="e5851-153">Проверка этого примера</span><span class="sxs-lookup"><span data-stu-id="e5851-153">To test this example</span></span>  
  
1.  <span data-ttu-id="e5851-154">Убедитесь, что установлены службы IIS и образец базы данных AdventureWorks для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e5851-154">Verify that IIS is installed and that the AdventureWorks sample database for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has been installed.</span></span>  
  
     <span data-ttu-id="e5851-155">Данному примеру требуются службы IIS версии 5.0 или более поздней, с включенной поддержкой ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="e5851-155">This example requires that Internet Information Services (IIS) version 5.0, or later versions, are installed with ASP.NET support enabled.</span></span> <span data-ttu-id="e5851-156">Кроме того, необходимо установить образец базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="e5851-156">Also, the AdventureWorks sample database has to be installed.</span></span>  
  
2.  <span data-ttu-id="e5851-157">Скопируйте код приведенного выше примера и вставьте его в редактор текста или XML.</span><span class="sxs-lookup"><span data-stu-id="e5851-157">Copy the code that was previously provided and paste it into the XML or text editor that you use.</span></span> <span data-ttu-id="e5851-158">Сохраните файл под именем RetrieveResults.aspx в корневой каталог документов IIS.</span><span class="sxs-lookup"><span data-stu-id="e5851-158">Save the file as RetrieveResults.aspx in the root directory used for IIS.</span></span> <span data-ttu-id="e5851-159">Обычно это каталог «C:\Inetpub\wwwroot».</span><span class="sxs-lookup"><span data-stu-id="e5851-159">Typically, this is C:Inetpub\wwwroot.</span></span>  
  
3.  <span data-ttu-id="e5851-160">Откройте страницу ASP.NET в окне браузера, указав следующий URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="e5851-160">Open the ASP.NET page in a browser window using the following URL.</span></span> <span data-ttu-id="e5851-161">Замените «MyServer» на «localhost» или на действительное имя сервера, на котором установлены службы IIS и [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e5851-161">First, replace 'MyServer' with either "localhost" or the actual name of the server where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and IIS are installed.</span></span>  
  
    ```  
    http://MyServer/RetrieveResults.aspx  
    ```  
  
 <span data-ttu-id="e5851-162">Результаты, сформированные в виде страниц HTML, будут выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e5851-162">The generated HTML page results that appear will be similar to the following sample output:</span></span>  
  
##### <a name="server-side-processing"></a><span data-ttu-id="e5851-163">Обработка на стороне сервера</span><span class="sxs-lookup"><span data-stu-id="e5851-163">Server-side processing</span></span>  
  
```  
Page Generated @ 3/11/2006 3:36:02 PM  
  
SqlConnection opened.  
  
<Sales.Store><Demographics><StoreSurvey xmlns="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/StoreSurvey"><AnnualSales>1500000</AnnualSales><AnnualRevenue>150000</AnnualRevenue><BankName>Primary International</BankName><BusinessType>OS</BusinessType><YearOpened>1974</YearOpened><Specialty>Road</Specialty><SquareFeet>38000</SquareFeet><Brands>3</Brands><Internet>DSL</Internet><NumberEmployees>40</NumberEmployees></StoreSurvey></Demographics></Sales.Store>  
  
SqlConnection closed.  
```  
  
> [!NOTE]  
>  <span data-ttu-id="e5851-164">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `xml` Поддержка типа данных позволяет запросить возврат результата запроса FOR XML в виде `xml` типа данных вместо строковых или графических данных, указав [директиву Type](type-directive-in-for-xml-queries.md).</span><span class="sxs-lookup"><span data-stu-id="e5851-164">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]`xml` data type support lets you request that the result of a FOR XML query be returned as `xml` data type, instead of as string or image typed data, by specifying the [TYPE directive](type-directive-in-for-xml-queries.md).</span></span> <span data-ttu-id="e5851-165">Если в запросе FOR XML указана директива TYPE, она предоставляет программный доступ к результатам FOR XML, как описано в разделе [Использование XML-данных в приложениях](use-xml-data-in-applications.md).</span><span class="sxs-lookup"><span data-stu-id="e5851-165">When the TYPE directive is used in FOR XML queries, it provides programmatic access to the FOR XML results similar to that shown in [Use XML Data in Applications](use-xml-data-in-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5851-166">См. также:</span><span class="sxs-lookup"><span data-stu-id="e5851-166">See Also</span></span>  
 [<span data-ttu-id="e5851-167">FOR XML (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="e5851-167">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
  
  
