---
title: Использование данных XML в приложениях | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- parameters [XML in SQL Server]
- XML [SQL Server], ADO
- columns [XML in SQL Server], ADO.NET
- ADO [XML in SQL Server]
- columns [XML in SQL Server], SQL Server Native Client
- xml data type [SQL Server], ADO
- SQLNCLI, XML
- xml data type [SQL Server], SQL Server Native Client
- SQL Server Native Client, XML
- ADO.NET [XML in SQL Server]
- XML [SQL Server], ADO.NET
- columns [XML in SQL Server], ADO
- xml data type [SQL Server], ADO.NET
- XML [SQL Server], SQL Server Native Client
ms.assetid: 5dabf7e0-c6df-451d-a070-4661f84607fd
author: rothja
ms.author: jroth
ms.openlocfilehash: 79dd4f4d2ff3cd61bc33c632f499bfb8e8817f0f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728089"
---
# <a name="use-xml-data-in-applications"></a><span data-ttu-id="99c97-102">Использование XML-данных в приложениях</span><span class="sxs-lookup"><span data-stu-id="99c97-102">Use XML Data in Applications</span></span>
  <span data-ttu-id="99c97-103">В этом подразделе описываются параметры, доступные при работе с типом данных `xml` в приложениях.</span><span class="sxs-lookup"><span data-stu-id="99c97-103">This topic describes the options that are available to you for working with the `xml` data type in your application.</span></span> <span data-ttu-id="99c97-104">Он содержит следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="99c97-104">The topic includes information about the following:</span></span>  
  
-   <span data-ttu-id="99c97-105">Обработка XML в столбцах типа `xml` с помощью ADO и собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99c97-105">Handling XML from an `xml` type column by using ADO and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client</span></span>  
  
-   <span data-ttu-id="99c97-106">Обработка XML в столбцах типа `xml` с помощью ADO.NET</span><span class="sxs-lookup"><span data-stu-id="99c97-106">Handling XML from an `xml` type column by using ADO.NET</span></span>  
  
-   <span data-ttu-id="99c97-107">Обработка типа `xml` в параметрах с помощью ADO.NET</span><span class="sxs-lookup"><span data-stu-id="99c97-107">Handling `xml` type in parameters by using ADO.NET</span></span>  
  
## <a name="handling-xml-from-an-xml-type-column-by-using-ado-and-sql-server-native-client"></a><span data-ttu-id="99c97-108">Обработка XML в столбцах типа xml с помощью ADO и собственного клиента SQL Server</span><span class="sxs-lookup"><span data-stu-id="99c97-108">Handling XML from an xml Type Column by Using ADO and SQL Server Native Client</span></span>  
 <span data-ttu-id="99c97-109">Чтобы при помощи компонентов MDAC получить доступ к типам и возможностям, появившимся в [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], в строке соединения ADO необходимо указать свойство инициализации, DataTypeCompatibility.</span><span class="sxs-lookup"><span data-stu-id="99c97-109">To use MDAC components to access the types and features that were introduced in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], you must set the DataTypeCompatibility initialization property in the ADO connection string.</span></span>  
  
 <span data-ttu-id="99c97-110">Например, в следующем образце скрипта Visual Basic Scripting Edition (VBScript) выдается результат запроса столбца `Demographics`, содержащего данные типа `xml`, из таблицы `Sales.Store` образца базы данных `AdventureWorks2012`.</span><span class="sxs-lookup"><span data-stu-id="99c97-110">For example, the following Visual Basic Scripting Edition (VBScript) sample shows the results of querying an `xml` data type column, `Demographics`, in the `Sales.Store` table of the `AdventureWorks2012` sample database.</span></span> <span data-ttu-id="99c97-111">В частности, запрос производит поиск значения столбца для строки, в которой значение `CustomerID` равно `3`.</span><span class="sxs-lookup"><span data-stu-id="99c97-111">Specifically, the query looks for the instance value of this column for the row where the `CustomerID` is equal to `3`.</span></span>  
  
```  
Const DS = "MyServer"  
Const DB = "AdventureWorks2012"  
  
Set objConn = CreateObject("ADODB.Connection")  
Set objRs = CreateObject("ADODB.Recordset")  
  
CommandText = "SELECT Demographics" & _  
              " FROM Sales.Store" & _  
              " INNER JOIN Sales.Customer" & _  
              " ON Sales.Store.BusinessEntityID = sales.customer.StoreID" & _  
              " WHERE Sales.Customer.CustomerID = 3" & _  
              " OR Sales.Customer.CustomerID = 4"  
  
ConnectionString = "Provider=SQLNCLI11" & _  
                   ";Data Source=" & DS & _  
                   ";Initial Catalog=" & DB & _  
                   ";Integrated Security=SSPI;" & _  
                   "DataTypeCompatibility=80"  
  
'Connect to the data source.  
objConn.Open ConnectionString  
  
'Execute command through the connection and display  
Set objRs = objConn.Execute(CommandText)  
  
Dim rowcount  
rowcount = 0  
Do While Not objRs.EOF  
   rowcount = rowcount + 1  
   MsgBox "Row " & rowcount & _  
           vbCrLf & vbCrLf & objRs(0)  
   objRs.MoveNext  
Loop  
  
'Clean up.  
objRs.Close  
objConn.Close  
Set objRs = Nothing  
Set objConn = Nothing  
```  
  
 <span data-ttu-id="99c97-112">В этом примере показано, как настроить свойство совместимости типов данных.</span><span class="sxs-lookup"><span data-stu-id="99c97-112">This example shows how to set the data type compatibility property.</span></span> <span data-ttu-id="99c97-113">По умолчанию, при использовании собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] это свойство принимает значение 0.</span><span class="sxs-lookup"><span data-stu-id="99c97-113">By default, this is set to 0 when you are using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span> <span data-ttu-id="99c97-114">Если этому свойству присвоить значение 80, то поставщик собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] представляет столбцы типа данных `xml` и определяемого пользователем типа в виде типов данных [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span><span class="sxs-lookup"><span data-stu-id="99c97-114">If you set the value to 80, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client provider will make `xml` and user-defined type columns appear as [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] data types.</span></span> <span data-ttu-id="99c97-115">то есть DBTYPE_WSTR и DBTYPE_BYTES соответственно.</span><span class="sxs-lookup"><span data-stu-id="99c97-115">This would be DBTYPE_WSTR and DBTYPE_BYTES, respectively.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="99c97-116">должен быть установлен на клиентском компьютере, а в строке соединения он должен быть указан в качестве поставщика данных: "`Provider=SQLNCLI11;...`".</span><span class="sxs-lookup"><span data-stu-id="99c97-116">Native Client must also be installed on the client computer and the connection string must specify it for use as the data provider with "`Provider=SQLNCLI11;...`".</span></span>  
  
#### <a name="to-test-this-example"></a><span data-ttu-id="99c97-117">Проверка этого примера</span><span class="sxs-lookup"><span data-stu-id="99c97-117">To test this example</span></span>  
  
1.  <span data-ttu-id="99c97-118">Убедитесь, что на компьютере клиента установлен собственный клиент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и доступны компоненты MDAC 2.6.0 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="99c97-118">Verify that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client is installed and that MDAC 2.6.0or later is available on the client computer.</span></span>  
  
     <span data-ttu-id="99c97-119">Дополнительные сведения см. в статье [Программирование SQL Server Native Client](../native-client/sql-server-native-client-programming.md).</span><span class="sxs-lookup"><span data-stu-id="99c97-119">For more information, see [SQL Server Native Client Programming](../native-client/sql-server-native-client-programming.md).</span></span>  
  
2.  <span data-ttu-id="99c97-120">Убедитесь, что образец базы данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] установлен в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="99c97-120">Verify that the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed.</span></span>  
  
     <span data-ttu-id="99c97-121">Для этого примера требуется образец базы данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="99c97-121">This example requires the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
3.  <span data-ttu-id="99c97-122">Скопируйте код, приведенный ранее в этом подразделе, и вставьте его в текстовый редактор или редактор кода.</span><span class="sxs-lookup"><span data-stu-id="99c97-122">Copy the code shown previously in this topic and paste the code into your text or code editor.</span></span> <span data-ttu-id="99c97-123">Сохраните файл под именем HandlingXmlDataType.vbs.</span><span class="sxs-lookup"><span data-stu-id="99c97-123">Save the file as HandlingXmlDataType.vbs.</span></span>  
  
4.  <span data-ttu-id="99c97-124">Измените скрипт так, как необходимо для вашей установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , и сохраните изменения.</span><span class="sxs-lookup"><span data-stu-id="99c97-124">Modify the script as required for your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation and save your changes.</span></span>  
  
     <span data-ttu-id="99c97-125">В частности, вместо `MyServer` необходимо указать либо `(local)` , либо действительное имя сервера, на котором установлен [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="99c97-125">For example, where `MyServer` is specified, you should replace it with either `(local)` or the actual name of the server on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed.</span></span>  
  
5.  <span data-ttu-id="99c97-126">Запустите файл скрипта HandlingXmlDataType.vbs на выполнение.</span><span class="sxs-lookup"><span data-stu-id="99c97-126">Run HandlingXmlDataType.vbs and execute the script.</span></span>  
  
 <span data-ttu-id="99c97-127">Результат должен примерно соответствовать следующему:</span><span class="sxs-lookup"><span data-stu-id="99c97-127">The results should be similar to the following sample output:</span></span>  
  
```  
Row 1  
  
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
  
Row 2  
  
<StoreSurvey xmlns="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/StoreSurvey">  
  <AnnualSales>300000</AnnualSales>  
  <AnnualRevenue>30000</AnnualRevenue>  
  <BankName>United Security</BankName>  
  <BusinessType>BM</BusinessType>  
  <YearOpened>1976</YearOpened>  
  <Specialty>Road</Specialty>  
  <SquareFeet>6000</SquareFeet>  
  <Brands>2</Brands>  
  <Internet>DSL</Internet>  
  <NumberEmployees>5</NumberEmployees>  
</StoreSurvey>  
```  
  
## <a name="handling-xml-from-an-xml-type-column-by-using-adonet"></a><span data-ttu-id="99c97-128">Обработка XML-данных в столбцах типа xml с помощью ADO.NET</span><span class="sxs-lookup"><span data-stu-id="99c97-128">Handling XML from an xml Type Column by Using ADO.NET</span></span>  
 <span data-ttu-id="99c97-129">Для обработки XML из `xml` столбца типа данных с помощью ADO.NET и [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] можно использовать стандартное поведение `SqlCommand` класса.</span><span class="sxs-lookup"><span data-stu-id="99c97-129">To handle XML from an `xml` data type column by using ADO.NET and the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] you can use the standard behavior of the `SqlCommand` class.</span></span> <span data-ttu-id="99c97-130">Например, столбец с данными типа `xml` и его значения могут быть запрошены таким же образом, как и любые столбцы SQL, с помощью `SqlDataReader`. Но если необходимо работать со столбцами типа `xml` как с XML-данными, то сначала необходимо связать содержимое с типом `XmlReader`.</span><span class="sxs-lookup"><span data-stu-id="99c97-130">For example, an `xml` data type column and its values can be retrieved in the same way any SQL column is retrieved by using a `SqlDataReader`.However, if you want to work with the contents of an `xml` data type column as XML, you will first have to assign the contents to an `XmlReader` type.</span></span>  
  
 <span data-ttu-id="99c97-131">Дополнительные сведения и примеры кода см. в разделе "Значения XML-столбцов в модуле чтения данных" в документации по пакету [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnlong](../../includes/dnprdnlong-md.md)] SDK.</span><span class="sxs-lookup"><span data-stu-id="99c97-131">For more information and example code, see "XML Column Values in a Data Reader" in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnlong](../../includes/dnprdnlong-md.md)] SDK documentation.</span></span>  
  
## <a name="handling-an-xml-type-column-in-parameters-by-using-adonet"></a><span data-ttu-id="99c97-132">Обработка столбцов типа xml в параметрах с помощью ADO.NET</span><span class="sxs-lookup"><span data-stu-id="99c97-132">Handling an xml Type Column in Parameters by Using ADO.NET</span></span>  
 <span data-ttu-id="99c97-133">Для обработки XML-данных, переданных в качестве параметра в ADO.NET и [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], значение можно представить в виде экземпляра данных типа `SqlXml`.</span><span class="sxs-lookup"><span data-stu-id="99c97-133">To handle an xml data type passed as a parameter in ADO.NET and the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], you can supply the value as an instance of the `SqlXml` data type.</span></span> <span data-ttu-id="99c97-134">Специальная обработка не производится, поскольку для столбцов типа `xml` в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] допустимы такие же значения параметров, как и для любых других столбцов и типов данных, например `string` или `integer`.</span><span class="sxs-lookup"><span data-stu-id="99c97-134">No special handling is involved, because `xml` data type columns in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can accept parameter values in the same way as other columns and data types, such as `string` or `integer`.</span></span>  
  
 <span data-ttu-id="99c97-135">Дополнительные сведения и примеры кода см. в разделе "XML-значения в качестве параметров" в документации по пакету [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnlong](../../includes/dnprdnlong-md.md)] SDK.</span><span class="sxs-lookup"><span data-stu-id="99c97-135">For more information and example code, see "XML Values as Command Parameters" in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnlong](../../includes/dnprdnlong-md.md)] SDK documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99c97-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="99c97-136">See Also</span></span>  
 [<span data-ttu-id="99c97-137">Данные XML (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="99c97-137">XML Data &#40;SQL Server&#41;</span></span>](xml-data-sql-server.md)  
  
  
