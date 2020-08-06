---
title: Запуск DiffGram с помощью управляемых классов SQLXML | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- DiffGrams [SQLXML], Managed Classes
- SQLXML Managed Classes, DiffGrams
- Managed Classes [SQLXML], DiffGrams
- SQLXML, Managed Classes
ms.assetid: 81c687ca-8c9f-4f58-801f-8dabcc508a06
author: rothja
ms.author: jroth
ms.openlocfilehash: f36127c37eea73a2872d4bf0aef7172a88e430a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664811"
---
# <a name="executing-a-diffgram-by-using-sqlxml-managed-classes"></a><span data-ttu-id="7d8c9-102">Выполнение дельты с использованием управляемых классов SQLXML</span><span class="sxs-lookup"><span data-stu-id="7d8c9-102">Executing a DiffGram by Using SQLXML Managed Classes</span></span>
  <span data-ttu-id="7d8c9-103">В этом примере показано, как выполнить файл DiffGram в [!INCLUDE[msCoName](../../../includes/msconame-md.md)] среде .NET Framework, чтобы применить обновления данных к [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] таблицам с помощью УПРАВЛЯЕМЫХ классов SQLXML (Microsoft. Data. SQLXML).</span><span class="sxs-lookup"><span data-stu-id="7d8c9-103">This example shows how to execute a DiffGram file in the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework environment to apply data updates to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tables using SQLXML Managed Classes (Microsoft.Data.SqlXml).</span></span>  
  
 <span data-ttu-id="7d8c9-104">В этом примере дельта обновляет CompanyName и ContactName для клиента ALFKI.</span><span class="sxs-lookup"><span data-stu-id="7d8c9-104">In this example, the DiffGram updates customer information (CompanyName and ContactName) for customer ALFKI.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql" sql:mapping-schema="DiffGramSchema.xml">  
  <diffgr:diffgram   
           xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"   
           xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
    <DataInstance>  
      <Customer diffgr:id="Customer1"   
                msdata:rowOrder="0" diffgr:hasChanges="modified"   
                CustomerID="ALFKI">  
          <CompanyName>Bottom Dollar Markets</CompanyName>  
          <ContactName>Antonio Moreno</ContactName>  
      </Customer>  
    </DataInstance>  
    <diffgr:before>  
     <Customer diffgr:id="Customer1"   
               msdata:rowOrder="0"   
               CustomerID="ALFKI">  
        <CompanyName>Alfreds Futterkiste</CompanyName>  
        <ContactName>Maria Anders</ContactName>  
      </Customer>  
    </diffgr:before>  
  </diffgr:diffgram>  
</ROOT>  
```  
  
 <span data-ttu-id="7d8c9-105">**\<before>** Блок включает **\<Customer>** элемент (**diffgr: ID = "Customer1"**).</span><span class="sxs-lookup"><span data-stu-id="7d8c9-105">The **\<before>** block includes a **\<Customer>** element (**diffgr:id="Customer1"**).</span></span> <span data-ttu-id="7d8c9-106">**\<DataInstance>** Блок включает соответствующий **\<Customer>** элемент с тем же **идентификатором**. **\<customer>** Элемент в **\<NewDataSet>** также указывает **diffgr: hasChanges = "Modified"**.</span><span class="sxs-lookup"><span data-stu-id="7d8c9-106">The **\<DataInstance>** block includes the corresponding **\<Customer>** element with same **id**. The **\<customer>** element in the **\<NewDataSet>** also specifies **diffgr:hasChanges="modified"**.</span></span> <span data-ttu-id="7d8c9-107">Это указывает на операцию по обновлению, и запись о заказчике в таблице Cust соответствующим образом обновляется.</span><span class="sxs-lookup"><span data-stu-id="7d8c9-107">This indicates an update operation, and the customer record in the Cust table is updated accordingly.</span></span> <span data-ttu-id="7d8c9-108">Обратите внимание, что если атрибут **diffgr: hasChanges** не указан, логика обработки DiffGram игнорирует этот элемент и обновления не выполняются.</span><span class="sxs-lookup"><span data-stu-id="7d8c9-108">Note that if the **diffgr:hasChanges** attribute is not specified, the DiffGram processing logic ignores this element and no updates are performed.</span></span>  
  
 <span data-ttu-id="7d8c9-109">Ниже приведен код для учебного приложения C#, в котором показано, как использовать управляемые классы SQLXML для выполнения приведенного выше DiffGram и обновления двух таблиц (Cust, пособий), которые также будут созданы в базе данных **tempdb** .</span><span class="sxs-lookup"><span data-stu-id="7d8c9-109">The following is code for a C# tutorial application that shows how to use the SQLXML Managed Classes to execute the above DiffGram and update two tables (Cust, Ord) you will also create in the **tempdb** database.</span></span>  
  
```  
using System;  
using System.Data;  
using Microsoft.Data.SqlXml;  
using System.IO;  
class Test  
{  
   static string ConnString = "Provider=SQLOLEDB;Server=MyServer;database=tempdb;Integrated Security=SSPI;";  
   public static int testParams()  
   {  
      SqlXmlAdapter ad;  
      // Need a memory stream to hold diff gram temporarily  
      MemoryStream ms = new MemoryStream();  
      SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
      cmd.RootTag = "ROOT";  
      cmd.CommandStream = new FileStream("MyDiffgram.xml", FileMode.Open, FileAccess.Read);  
      cmd.CommandType = SqlXmlCommandType.DiffGram;  
      cmd.SchemaPath = "DiffGramSchema.xml";  
      // Load data set  
      DataSet ds = new DataSet();  
      ad = new SqlXmlAdapter(cmd);  
      ad.Fill(ds);  
      ad.Update(ds);  
      return 0;  
   }  
   public static int Main(String[] args)  
   {  
      testParams();  
      return 0;  
   }  
}  
```  
  
### <a name="to-test-the-application"></a><span data-ttu-id="7d8c9-110">Тестирование приложения</span><span class="sxs-lookup"><span data-stu-id="7d8c9-110">To test the application</span></span>  
  
1.  <span data-ttu-id="7d8c9-111">Проследите за тем, чтобы на вашем компьютере была установлена инфраструктура .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7d8c9-111">Ensure that the .NET Framework is installed on your computer.</span></span>  
  
2.  <span data-ttu-id="7d8c9-112">Сохраните в папке следующую схему XSD (DiffGramSchema.xml):</span><span class="sxs-lookup"><span data-stu-id="7d8c9-112">Save the following XSD schema (DiffGramSchema.xml) in a folder:</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
     <xsd:annotation>  
      <xsd:documentation>  
        Diffgram Customers/Orders Schema.  
      </xsd:documentation>  
      <xsd:appinfo>  
           <sql:relationship name="CustomersOrders"   
                      parent="Cust"  
                      parent-key="CustomerID"  
                      child-key="CustomerID"  
                      child="Ord"/>  
      </xsd:appinfo>  
     </xsd:annotation>  
     <xsd:element name="Customer" sql:relation="Cust">  
      <xsd:complexType>  
        <xsd:sequence>  
          <xsd:element name="CompanyName"    type="xsd:string"/>  
          <xsd:element name="ContactName"    type="xsd:string"/>  
           <xsd:element name="Order" sql:relation="Ord" sql:relationship="CustomersOrders">  
            <xsd:complexType>  
              <xsd:attribute name="OrderID" type="xsd:int" sql:field="OrderID"/>  
              <xsd:attribute name="CustomerID" type="xsd:string"/>  
            </xsd:complexType>  
          </xsd:element>  
        </xsd:sequence>  
        <xsd:attribute name="CustomerID" type="xsd:string" sql:field="CustomerID"/>  
      </xsd:complexType>  
     </xsd:element>  
    </xsd:schema>  
    ```  
  
3.  <span data-ttu-id="7d8c9-113">Создайте эти таблицы в базе данных **tempdb** .</span><span class="sxs-lookup"><span data-stu-id="7d8c9-113">Create these tables in the **tempdb** database.</span></span>  
  
    ```  
    CREATE TABLE Cust(  
            CustomerID  nchar(5) Primary Key,  
            CompanyName nvarchar(40) NOT NULL ,  
            ContactName nvarchar(60) NULL)  
    GO  
  
    CREATE TABLE Ord(  
       OrderID    int Primary Key,  
       CustomerID nchar(5) Foreign Key REFERENCES Cust(CustomerID))  
    GO  
    ```  
  
4.  <span data-ttu-id="7d8c9-114">Добавьте следующий образец данных:</span><span class="sxs-lookup"><span data-stu-id="7d8c9-114">Add this sample data:</span></span>  
  
    ```  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ALFKI', N'Alfreds Futterkiste', N'Maria Anders')  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ANATR', N'Ana Trujillo Emparedados y helados', N'Ana Trujillo')  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ANTON', N'Antonio Moreno Taquer??a', N'Antonio Moreno')  
  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(1, N'ALFKI')  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(2, N'ANATR')  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(3, N'ANTON')  
    ```  
  
5.  <span data-ttu-id="7d8c9-115">Скопируйте приведенную выше дельту и вставьте ее в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="7d8c9-115">Copy the DiffGram above and paste it into a text file.</span></span> <span data-ttu-id="7d8c9-116">Сохраните файл с именем MyDiffGram.xml в папке, которая использовалась на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="7d8c9-116">Save the file as MyDiffGram.xml in the same folder used in step 1.</span></span>  
  
6.  <span data-ttu-id="7d8c9-117">Сохраните помещенный выше код на языке C# (DiffgramSample.cs) в той же папке, в которой при выполнении предшествующих шагов были сохранены файлы DiffGramSchema.xml и MyDiffGram.xml.</span><span class="sxs-lookup"><span data-stu-id="7d8c9-117">Save the C# code (DiffgramSample.cs) that is provided above in the same folder in which the DiffGramSchema.xml and MyDiffGram.xml were stored in previous steps.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7d8c9-118">При этом потребуется обновить имя экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] в строке соединения, то есть заменить имя «`MyServer`» на фактическое имя установленного экземпляра [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d8c9-118">You will need to update the name of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance in the connection string from '`MyServer`' to the actual name of your installed instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="7d8c9-119">Если сохранить файлы в разных папках, то придется изменить код, указав путь к каталогу, в котором находится схема сопоставления.</span><span class="sxs-lookup"><span data-stu-id="7d8c9-119">If you store the files in a different folder, you will have to edit the code and specify the appropriate directory path for the mapping schema.</span></span>  
  
7.  <span data-ttu-id="7d8c9-120">Скомпилируйте код.</span><span class="sxs-lookup"><span data-stu-id="7d8c9-120">Compile the code.</span></span> <span data-ttu-id="7d8c9-121">Чтобы скомпилировать код из командной строки, введите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="7d8c9-121">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DiffgramSample.cs  
    ```  
  
     <span data-ttu-id="7d8c9-122">В результате создается исполняемый файл (DiffgramSample.exe).</span><span class="sxs-lookup"><span data-stu-id="7d8c9-122">This creates an executable (DiffgramSample.exe).</span></span>  
  
8.  <span data-ttu-id="7d8c9-123">Из командной строки выполните файл DiffgramSample.exe.</span><span class="sxs-lookup"><span data-stu-id="7d8c9-123">At the command prompt, execute DiffgramSample.exe.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d8c9-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="7d8c9-124">See Also</span></span>  
 [<span data-ttu-id="7d8c9-125">Примеры DiffGram &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="7d8c9-125">DiffGram Examples &#40;SQLXML 4.0&#41;</span></span>](diffgram-examples-sqlxml-4-0.md)  
  
  
