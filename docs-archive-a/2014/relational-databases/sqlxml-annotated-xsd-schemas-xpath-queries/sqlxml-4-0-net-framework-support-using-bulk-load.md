---
title: Использование групповой загрузки SQLXML в среде .NET | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXML, XML Bulk Load
- XML Bulk Load [SQLXML], .NET environment
- .NET Framework [SQLXML], XML Bulk Load
- bulk load [SQLXML], .NET environment
ms.assetid: b85df83b-ba56-43bf-bcdf-b2a6fca43276
author: rothja
ms.author: jroth
ms.openlocfilehash: 6bd1c44a8b56bc5129aeb9843ed9ba814d45742a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738174"
---
# <a name="using-sqlxml-bulk-load-in-the-net-environment"></a><span data-ttu-id="5cc87-102">Использование массовой загрузки SQLXML в среде .NET</span><span class="sxs-lookup"><span data-stu-id="5cc87-102">Using SQLXML Bulk Load in the .NET Environment</span></span>
  <span data-ttu-id="5cc87-103">В этом разделе объясняется, как можно использовать функциональность массовой загрузки XML в среде .NET.</span><span class="sxs-lookup"><span data-stu-id="5cc87-103">This topic explains how the XML Bulk Load functionality can be used in the .NET environment.</span></span> <span data-ttu-id="5cc87-104">Подробные сведения о групповой загрузке XML см. в разделе [выполнение групповой загрузки XML-данных &#40;SQLXML 4,0&#41;](bulk-load-xml/performing-bulk-load-of-xml-data-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="5cc87-104">For detailed information about XML Bulk Load, see [Performing Bulk Load of XML Data &#40;SQLXML 4.0&#41;](bulk-load-xml/performing-bulk-load-of-xml-data-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="5cc87-105">Для использования объекта COM массовой загрузки SQLXML в управляемой среде необходимо добавить в этот объект ссылку на проект.</span><span class="sxs-lookup"><span data-stu-id="5cc87-105">To use the SQLXML Bulk Load COM object from a managed environment, you need to add a project reference to this object.</span></span> <span data-ttu-id="5cc87-106">Это сформирует управляемый интерфейс оболочки объекта массовой загрузки COM.</span><span class="sxs-lookup"><span data-stu-id="5cc87-106">This generates a managed wrapper interface around the Bulk Load COM object.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5cc87-107">Управляемая массовая загрузка XML не работает с управляемыми потоками и требует оболочки собственных потоков.</span><span class="sxs-lookup"><span data-stu-id="5cc87-107">Managed XML Bulk load does not work with managed streams and requires a wrapper around native streams.</span></span> <span data-ttu-id="5cc87-108">Компонент массовой загрузки SQLXML не будет запущен в многопоточной среде (атрибут '[MTAThread]').</span><span class="sxs-lookup"><span data-stu-id="5cc87-108">The SQLXML Bulk Load component will not run in a multi-threaded environment ('[MTAThread]' attribute).</span></span> <span data-ttu-id="5cc87-109">При попытке запустить компонент с массовыми загрузками в многопотоковой среде возникает исключение InvalidCastException со следующими дополнительными сведениями: "QueryInterface для интерфейса SQLXMLBULKLOADLib. Исклксмлбулклоад Failed".</span><span class="sxs-lookup"><span data-stu-id="5cc87-109">If you attempt to run the Bulk Load component in a multi-thread environment, you get an InvalidCastException exception with the following additional information: "QueryInterface for interface SQLXMLBULKLOADLib.ISQLXMLBulkLoad failed."</span></span> <span data-ttu-id="5cc87-110">Обходной путь состоит в том, чтобы сделать объект, содержащий объект групповой загрузки, доступный для одного потока (например, с помощью атрибута **[STAThread]** , как показано в примере).</span><span class="sxs-lookup"><span data-stu-id="5cc87-110">The workaround is to make the object that contains the Bulk Load object single-thread accessible (for example, by using the **[STAThread]** attribute as shown in the sample).</span></span>  
  
 <span data-ttu-id="5cc87-111">Этот раздел содержит образец реализации приложения на языке C# для массовой загрузки XML-данных в базу данных.</span><span class="sxs-lookup"><span data-stu-id="5cc87-111">This topic provides a working C# sample application to bulk load XML data in the database.</span></span> <span data-ttu-id="5cc87-112">Чтобы создать образец реализации, выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="5cc87-112">To create a working sample, follow these steps:</span></span>  
  
1.  <span data-ttu-id="5cc87-113">Создайте следующие таблицы:</span><span class="sxs-lookup"><span data-stu-id="5cc87-113">Create the following tables:</span></span>  
  
    ```  
    CREATE TABLE Ord (  
             OrderID     int identity(1,1)  PRIMARY KEY,  
             CustomerID  varchar(5))  
    GO  
    CREATE TABLE Product (  
             ProductID   int identity(1,1) PRIMARY KEY,  
             ProductName varchar(20))  
    GO  
    CREATE TABLE OrderDetail (  
           OrderID     int FOREIGN KEY REFERENCES Ord(OrderID),  
           ProductID   int FOREIGN KEY REFERENCES Product(ProductID),  
                       CONSTRAINT OD_key PRIMARY KEY (OrderID, ProductID))  
    GO  
    ```  
  
2.  <span data-ttu-id="5cc87-114">Сохраните в файле (schema.xml) следующую схему:</span><span class="sxs-lookup"><span data-stu-id="5cc87-114">Save the following schema in a file (schema.xml):</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
    <xsd:annotation>  
      <xsd:appinfo>  
        <sql:relationship name="OrderOD"  
              parent="Ord"  
              parent-key="OrderID"  
              child="OrderDetail"  
              child-key="OrderID" />  
  
        <sql:relationship name="ODProduct"  
              parent="OrderDetail"  
              parent-key="ProductID"  
              child="Product"  
              child-key="ProductID"   
              inverse="true"/>  
      </xsd:appinfo>  
    </xsd:annotation>  
  
      <xsd:element name="Order" sql:relation="Ord"   
                                sql:key-fields="OrderID" >  
       <xsd:complexType>  
         <xsd:sequence>  
            <xsd:element name="Product" sql:relation="Product"   
                         sql:key-fields="ProductID"  
                         sql:relationship="OrderOD ODProduct">  
              <xsd:complexType>  
                 <xsd:attribute name="ProductID" type="xsd:int" />  
                 <xsd:attribute name="ProductName" type="xsd:string" />  
              </xsd:complexType>  
            </xsd:element>  
         </xsd:sequence>  
            <xsd:attribute name="OrderID"   type="xsd:integer" />   
            <xsd:attribute name="CustomerID"   type="xsd:string" />  
        </xsd:complexType>  
      </xsd:element>  
    </xsd:schema>  
    ```  
  
3.  <span data-ttu-id="5cc87-115">Сохраните в файле (data.xml) следующий образец XML-документа:</span><span class="sxs-lookup"><span data-stu-id="5cc87-115">Save the following sample XML document in a file (data.xml):</span></span>  
  
    ```  
    <ROOT>    
      <Order OrderID="11" CustomerID="ALFKI">  
        <Product ProductID="11" ProductName="Chai" />  
        <Product ProductID="22" ProductName="Chang" />  
      </Order>  
      <Order OrderID="22" CustomerID="ANATR">  
         <Product ProductID="33" ProductName="Aniseed Syrup" />  
        <Product ProductID="44" ProductName="Gumbo Mix" />  
      </Order>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="5cc87-116">Запустите среду Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5cc87-116">Start Visual Studio.</span></span>  
  
5.  <span data-ttu-id="5cc87-117">Создайте консольное приложение C#.</span><span class="sxs-lookup"><span data-stu-id="5cc87-117">Create a C# console application.</span></span>  
  
6.  <span data-ttu-id="5cc87-118">В меню **проект** выберите команду **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="5cc87-118">From the **Project** menu, select **Add Reference**.</span></span>  
  
7.  <span data-ttu-id="5cc87-119">На вкладке **com** выберите **БИБЛИОТЕКУ типов Microsoft SQLXML Bulkload 4,0** (xblkld4.dll) и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5cc87-119">In the **COM** tab, select **Microsoft SQLXML Bulkload 4.0 Type Library** (xblkld4.dll) and click **OK**.</span></span> <span data-ttu-id="5cc87-120">Вы увидите сборку **Interop. SQLXMLBULKLOADLib** , созданную в проекте.</span><span class="sxs-lookup"><span data-stu-id="5cc87-120">You will see the **Interop.SQLXMLBULKLOADLib** assembly created in the project.</span></span>  
  
8.  <span data-ttu-id="5cc87-121">Замените метод Main() на следующий код.</span><span class="sxs-lookup"><span data-stu-id="5cc87-121">Replace the Main() method with the following code.</span></span> <span data-ttu-id="5cc87-122">Обновите свойство **ConnectionString** и путь к файлу схемы и файлов данных.</span><span class="sxs-lookup"><span data-stu-id="5cc87-122">Update the **ConnectionString** property and the file path to the schema and data files.</span></span>  
  
    ```  
    [STAThread]  
       static void Main(string[] args)  
       {     
             try  
             {  
                SQLXMLBULKLOADLib.SQLXMLBulkLoad4Class objBL = new SQLXMLBULKLOADLib.SQLXMLBulkLoad4Class();  
                objBL.ConnectionString = "Provider=sqloledb;server=server;database=databaseName;integrated security=SSPI";  
                objBL.ErrorLogFile = "error.xml";  
                objBL.KeepIdentity = false;  
                objBL.Execute ("schema.xml","data.xml");  
             }  
             catch(Exception e)  
             {  
             Console.WriteLine(e.ToString());  
             }  
       }  
    ```  
  
9. <span data-ttu-id="5cc87-123">Для загрузки XML в создаваемую таблицу постройте и запустите проект.</span><span class="sxs-lookup"><span data-stu-id="5cc87-123">To load the XML in the table you created, build and run the project.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5cc87-124">Ссылку на компонент массовой загрузки (xblkld4.dll) можно также добавить при помощи средства tlbimp.exe, которое доступно как часть платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5cc87-124">The reference to the Bulk Load component (xblkld4.dll) can also be added using the tlbimp.exe tool, which is available as part of .NET framework.</span></span> <span data-ttu-id="5cc87-125">Это средство создает управляемую оболочку для собственной DLL-библиотеки (xblkld4.dll), которую затем можно использовать в любом проекте .NET.</span><span class="sxs-lookup"><span data-stu-id="5cc87-125">This tool creates a managed wrapper for the native DLL (xblkld4.dll), which can then be used in any .NET project.</span></span> <span data-ttu-id="5cc87-126">Пример:</span><span class="sxs-lookup"><span data-stu-id="5cc87-126">For example:</span></span>  
  
    ```  
    c:\>tlbimp xblkld4.dll  
    ```  
  
     <span data-ttu-id="5cc87-127">Это средство создает DLL-библиотеку управляемой оболочки (SQLXMLBULKLOADLib.dll), которую можно использовать в проекте платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5cc87-127">This creates the managed wrapper DLL (SQLXMLBULKLOADLib.dll) that you can use in the .NET Framework project.</span></span> <span data-ttu-id="5cc87-128">В .NET Framework ссылка на проект добавляется к вновь созданной DLL-библиотеке.</span><span class="sxs-lookup"><span data-stu-id="5cc87-128">In the .NET Framework, you add project reference to the newly created DLL.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cc87-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="5cc87-129">See Also</span></span>  
 [<span data-ttu-id="5cc87-130">Выполнение массовой загрузки XML-данных &#40;SQLXML 4.0&#41;</span><span class="sxs-lookup"><span data-stu-id="5cc87-130">Performing Bulk Load of XML Data &#40;SQLXML 4.0&#41;</span></span>](bulk-load-xml/performing-bulk-load-of-xml-data-sqlxml-4-0.md)  
  
  
