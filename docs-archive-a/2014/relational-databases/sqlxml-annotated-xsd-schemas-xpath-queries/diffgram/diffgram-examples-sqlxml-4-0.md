---
title: Примеры DiffGram (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- DiffGrams [SQLXML], examples
- examples [SQLXML], DiffGram
- diffgr:parentID
- parentID annotation
ms.assetid: fc148583-dfd3-4efb-a413-f47b150b0975
author: rothja
ms.author: jroth
ms.openlocfilehash: 04fb355af01f9853149a84af72471375d9135468
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664819"
---
# <a name="diffgram-examples-sqlxml-40"></a><span data-ttu-id="7438a-102">Примеры дельт (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="7438a-102">DiffGram Examples (SQLXML 4.0)</span></span>
  <span data-ttu-id="7438a-103">Примеры в данном разделе состоят из нескольких дельт (DiffGram), которые выполняют операции вставки, обновления и удаления в базе данных.</span><span class="sxs-lookup"><span data-stu-id="7438a-103">The examples in this topic consist of DiffGrams that perform insert, update, and delete operations to the database.</span></span> <span data-ttu-id="7438a-104">При использовании этих примеров необходимо учитывать следующие моменты.</span><span class="sxs-lookup"><span data-stu-id="7438a-104">Before using the examples, note the following:</span></span>  
  
-   <span data-ttu-id="7438a-105">Примеры используют две таблицы (Cust и Ord), которые необходимо создать, если требуется проверить примеры дельт:</span><span class="sxs-lookup"><span data-stu-id="7438a-105">The examples use two tables (Cust and Ord) that must be created if you want to test the DiffGram examples:</span></span>  
  
    ```  
    Cust(CustomerID, CompanyName, ContactName)  
    Ord(OrderID, CustomerID)  
    ```  
  
-   <span data-ttu-id="7438a-106">Большинство примеров в данном разделе используют следующую схему XSD:</span><span class="sxs-lookup"><span data-stu-id="7438a-106">Most of the examples in this topic use the following XSD Schema:</span></span>  
  
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
  
     <span data-ttu-id="7438a-107">Сохраните данную схему под именем DiffGramSchema.xml в той же папке, где находятся остальные файлы, используемые в примерах.</span><span class="sxs-lookup"><span data-stu-id="7438a-107">Save this schema as DiffGramSchema.xml in the same folder where you save other files used in the examples.</span></span>  
  
## <a name="a-deleting-a-record-by-using-a-diffgram"></a><span data-ttu-id="7438a-108">A.</span><span class="sxs-lookup"><span data-stu-id="7438a-108">A.</span></span> <span data-ttu-id="7438a-109">Удаление записи с помощью дельты</span><span class="sxs-lookup"><span data-stu-id="7438a-109">Deleting a record by using a DiffGram</span></span>  
 <span data-ttu-id="7438a-110">Дельта в этом примере удаляет запись пользователя (с атрибутом CustomerID, имеющим значение ALFKI) из таблицы Cust и удаляет соответствующую запись заказа (с атрибутом OrderID со значением 1) из таблицы Ord.</span><span class="sxs-lookup"><span data-stu-id="7438a-110">The DiffGram in this example deletes a customer (whose CustomerID is ALFKI) record from the Cust table and deletes the corresponding order record (whose OrderID is 1) from the Ord table.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql" sql:mapping-schema="DiffGramSchema.xml">  
  <diffgr:diffgram   
           xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"   
           xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
    <DataInstance/>  
  
    <diffgr:before>  
        <Order diffgr:id="Order1"   
               msdata:rowOrder="0"   
               CustomerID="ALFKI"   
               OrderID="1"/>  
        <Customer diffgr:id="Customer1"   
                  msdata:rowOrder="0"   
                  CustomerID="ALFKI">  
           <CompanyName>Alfreds Futterkiste</CompanyName>  
           <ContactName>Maria Anders</ContactName>  
        </Customer>  
    </diffgr:before>  
    <msdata:errors/>  
  </diffgr:diffgram>  
</ROOT>  
```  
  
 <span data-ttu-id="7438a-111">В **\<before>** блоке есть **\<Order>** элемент (**diffgr: ID = "Order1"**) и **\<Customer>** элемент (**diffgr: ID = "Customer1"**).</span><span class="sxs-lookup"><span data-stu-id="7438a-111">In the **\<before>** block, there is an **\<Order>** element (**diffgr:id="Order1"**) and a **\<Customer>** element (**diffgr:id="Customer1"**).</span></span> <span data-ttu-id="7438a-112">Данные элементы представляют существующие записи в базе данных.</span><span class="sxs-lookup"><span data-stu-id="7438a-112">These elements represent existing records in the database.</span></span> <span data-ttu-id="7438a-113">**\<DataInstance>** Элемент не имеет соответствующих записей (с тем же **идентификатором diffgr: ID**).</span><span class="sxs-lookup"><span data-stu-id="7438a-113">The **\<DataInstance>** element does not have the corresponding records (with the same **diffgr:id**).</span></span> <span data-ttu-id="7438a-114">Это указывает на операцию удаления.</span><span class="sxs-lookup"><span data-stu-id="7438a-114">This indicates a delete operation.</span></span>  
  
#### <a name="to-test-the-diffgram"></a><span data-ttu-id="7438a-115">Проверка дельты</span><span class="sxs-lookup"><span data-stu-id="7438a-115">To test the DiffGram</span></span>  
  
1.  <span data-ttu-id="7438a-116">Создайте эти таблицы в базе данных **tempdb** .</span><span class="sxs-lookup"><span data-stu-id="7438a-116">Create these tables in the **tempdb** database.</span></span>  
  
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
  
2.  <span data-ttu-id="7438a-117">Добавьте следующий образец данных:</span><span class="sxs-lookup"><span data-stu-id="7438a-117">Add this sample data:</span></span>  
  
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
  
3.  <span data-ttu-id="7438a-118">Скопируйте приведенную выше дельту и вставьте ее в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="7438a-118">Copy the DiffGram above and paste it into a text file.</span></span> <span data-ttu-id="7438a-119">Сохраните файл с именем MyDiffGram.xml в папке, которая использовалась на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="7438a-119">Save the file as MyDiffGram.xml in the same folder used in the previous step.</span></span>  
  
4.  <span data-ttu-id="7438a-120">Скопируйте схему DiffGramSchema, приведенную ранее в этом разделе, и вставьте ее в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="7438a-120">Copy the DiffGramSchema provided earlier in this topic and paste it into a text file.</span></span> <span data-ttu-id="7438a-121">Сохраните файл с именем DiffGramSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="7438a-121">Save the file as DiffGramSchema.xml.</span></span>  
  
5.  <span data-ttu-id="7438a-122">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить дельту.</span><span class="sxs-lookup"><span data-stu-id="7438a-122">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the DiffGram.</span></span>  
  
     <span data-ttu-id="7438a-123">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="7438a-123">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
## <a name="b-inserting-a-record-by-using-a-diffgram"></a><span data-ttu-id="7438a-124">Б.</span><span class="sxs-lookup"><span data-stu-id="7438a-124">B.</span></span> <span data-ttu-id="7438a-125">Вставка записи с помощью дельты</span><span class="sxs-lookup"><span data-stu-id="7438a-125">Inserting a record by using a DiffGram</span></span>  
 <span data-ttu-id="7438a-126">В этом примере дельта вставляет по одной записи в таблицы Cust и Ord.</span><span class="sxs-lookup"><span data-stu-id="7438a-126">In this example, the DiffGram inserts a record in the Cust table and a record in the Ord table.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql"   
      sql:mapping-schema="DiffGramSchema.xml">  
  <diffgr:diffgram   
          xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"   
          xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
    <DataInstance>  
       <Customer diffgr:id="Customer1" msdata:rowOrder="0"    
                 diffgr:hasChanges="inserted" CustomerID="ALFKI">  
        <CompanyName>C3Company</CompanyName>  
        <ContactName>C3Contact</ContactName>  
        <Order diffgr:id="Order1"   
               msdata:rowOrder="0"  
               diffgr:hasChanges="inserted"   
               CustomerID="ALFKI" OrderID="1"/>  
      </Customer>  
    </DataInstance>  
  
  </diffgr:diffgram>  
</ROOT>  
```  
  
 <span data-ttu-id="7438a-127">В этом DiffGram **\<before>** блок не задан (не определены существующие записи базы данных).</span><span class="sxs-lookup"><span data-stu-id="7438a-127">In this DiffGram the **\<before>** block is not specified (no existing database records identified).</span></span> <span data-ttu-id="7438a-128">Существуют два экземпляра записи (определяемые **\<Customer>** **\<Order>** элементами и в **\<DataInstance>** блоке), которые сопоставляются с таблицами Cust и намерены соответственно.</span><span class="sxs-lookup"><span data-stu-id="7438a-128">There are two record instances (identified by the **\<Customer>** and **\<Order>** elements in the **\<DataInstance>** block) that map to Cust and Ord tables, respectively.</span></span> <span data-ttu-id="7438a-129">Оба этих элемента указывают атрибут **diffgr: hasChanges** (**HasChanges = "inserted"**).</span><span class="sxs-lookup"><span data-stu-id="7438a-129">Both of these elements specify the **diffgr:hasChanges** attribute (**hasChanges="inserted"**).</span></span> <span data-ttu-id="7438a-130">Это указывает на операцию вставки.</span><span class="sxs-lookup"><span data-stu-id="7438a-130">This indicates an insert operation.</span></span> <span data-ttu-id="7438a-131">В этом DiffGram при указании **HasChanges = "Modified"** вы указываете, что хотите изменить несуществующую запись, что приведет к ошибке.</span><span class="sxs-lookup"><span data-stu-id="7438a-131">In this DiffGram, if you specify **hasChanges="modified"**, you are indicating that you want to modify a record that does not exist, which results in an error.</span></span>  
  
#### <a name="to-test-the-diffgram"></a><span data-ttu-id="7438a-132">Проверка дельты</span><span class="sxs-lookup"><span data-stu-id="7438a-132">To test the DiffGram</span></span>  
  
1.  <span data-ttu-id="7438a-133">Создайте эти таблицы в базе данных **tempdb** .</span><span class="sxs-lookup"><span data-stu-id="7438a-133">Create these tables in the **tempdb** database.</span></span>  
  
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
  
2.  <span data-ttu-id="7438a-134">Добавьте следующий образец данных:</span><span class="sxs-lookup"><span data-stu-id="7438a-134">Add this sample data:</span></span>  
  
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
  
3.  <span data-ttu-id="7438a-135">Скопируйте приведенную выше дельту и вставьте ее в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="7438a-135">Copy the DiffGram above and paste it into a text file.</span></span> <span data-ttu-id="7438a-136">Сохраните файл с именем MyDiffGram.xml в папке, которая использовалась на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="7438a-136">Save the file as MyDiffGram.xml in the same folder used in the previous step.</span></span>  
  
4.  <span data-ttu-id="7438a-137">Скопируйте схему DiffGramSchema, приведенную ранее в этом разделе, и вставьте ее в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="7438a-137">Copy the DiffGramSchema provided earlier in this topic and paste it into a text file.</span></span> <span data-ttu-id="7438a-138">Сохраните файл с именем DiffGramSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="7438a-138">Save the file as DiffGramSchema.xml.</span></span>  
  
5.  <span data-ttu-id="7438a-139">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить дельту.</span><span class="sxs-lookup"><span data-stu-id="7438a-139">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the DiffGram.</span></span>  
  
     <span data-ttu-id="7438a-140">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="7438a-140">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
## <a name="c-updating-an-existing-record-by-using-a-diffgram"></a><span data-ttu-id="7438a-141">В.</span><span class="sxs-lookup"><span data-stu-id="7438a-141">C.</span></span> <span data-ttu-id="7438a-142">Обновление существующей записи с помощью дельты</span><span class="sxs-lookup"><span data-stu-id="7438a-142">Updating an existing record by using a DiffGram</span></span>  
 <span data-ttu-id="7438a-143">В этом примере дельта обновляет CompanyName и ContactName для клиента ALFKI.</span><span class="sxs-lookup"><span data-stu-id="7438a-143">In this example, the DiffGram updates customer information (CompanyName and ContactName) for customer ALFKI.</span></span>  
  
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
  
 <span data-ttu-id="7438a-144">**\<before>** Блок включает **\<Customer>** элемент (**diffgr: ID = "Customer1"**).</span><span class="sxs-lookup"><span data-stu-id="7438a-144">The **\<before>** block includes a **\<Customer>** element (**diffgr:id="Customer1"**).</span></span> <span data-ttu-id="7438a-145">**\<DataInstance>** Блок включает соответствующий **\<Customer>** элемент с тем же **идентификатором**. **\<customer>** Элемент в **\<NewDataSet>** также указывает **diffgr: hasChanges = "Modified"**.</span><span class="sxs-lookup"><span data-stu-id="7438a-145">The **\<DataInstance>** block includes the corresponding **\<Customer>** element with same **id**. The **\<customer>** element in the **\<NewDataSet>** also specifies **diffgr:hasChanges="modified"**.</span></span> <span data-ttu-id="7438a-146">Это указывает на операцию обновления, и запись клиента в таблице **cust** соответствующим образом обновляется.</span><span class="sxs-lookup"><span data-stu-id="7438a-146">This indicates an update operation, and the customer record in the **Cust** table is updated accordingly.</span></span> <span data-ttu-id="7438a-147">Обратите внимание, что если атрибут **diffgr: hasChanges** не указан, логика обработки DiffGram игнорирует этот элемент и обновления не выполняются.</span><span class="sxs-lookup"><span data-stu-id="7438a-147">Note that if the **diffgr:hasChanges** attribute is not specified, the DiffGram processing logic ignores this element and no updates are performed.</span></span>  
  
#### <a name="to-test-the-diffgram"></a><span data-ttu-id="7438a-148">Проверка дельты</span><span class="sxs-lookup"><span data-stu-id="7438a-148">To test the DiffGram</span></span>  
  
1.  <span data-ttu-id="7438a-149">Создайте эти таблицы в базе данных **tempdb** .</span><span class="sxs-lookup"><span data-stu-id="7438a-149">Create these tables in the **tempdb** database.</span></span>  
  
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
  
2.  <span data-ttu-id="7438a-150">Добавьте следующий образец данных:</span><span class="sxs-lookup"><span data-stu-id="7438a-150">Add this sample data:</span></span>  
  
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
  
3.  <span data-ttu-id="7438a-151">Скопируйте приведенную выше дельту и вставьте ее в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="7438a-151">Copy the DiffGram above and paste it into a text file.</span></span> <span data-ttu-id="7438a-152">Сохраните файл с именем MyDiffGram.xml в папке, которая использовалась на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="7438a-152">Save the file as MyDiffGram.xml in the same folder used in the previous step.</span></span>  
  
4.  <span data-ttu-id="7438a-153">Скопируйте схему DiffGramSchema, приведенную ранее в этом разделе, и вставьте ее в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="7438a-153">Copy the DiffGramSchema provided earlier in this topic and paste it into a text file.</span></span> <span data-ttu-id="7438a-154">Сохраните файл с именем DiffGramSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="7438a-154">Save the file as DiffGramSchema.xml.</span></span>  
  
5.  <span data-ttu-id="7438a-155">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить дельту.</span><span class="sxs-lookup"><span data-stu-id="7438a-155">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the DiffGram.</span></span>  
  
     <span data-ttu-id="7438a-156">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="7438a-156">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
## <a name="d-inserting-updating-and-deleting-records-by-using-a-diffgram"></a><span data-ttu-id="7438a-157">Г.</span><span class="sxs-lookup"><span data-stu-id="7438a-157">D.</span></span> <span data-ttu-id="7438a-158">Вставка, обновление и удаление записей с помощью дельты</span><span class="sxs-lookup"><span data-stu-id="7438a-158">Inserting, updating, and deleting records by using a DiffGram</span></span>  
 <span data-ttu-id="7438a-159">В этом примере относительно сложная дельта используется для выполнения операций вставки, обновления и удаления.</span><span class="sxs-lookup"><span data-stu-id="7438a-159">In this example, a relatively complex DiffGram is used to perform insert, update, and delete operations.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql" sql:mapping-schema="DiffGramSchema.xml">  
  <diffgr:diffgram   
         xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"   
         xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
    <DataInstance>  
      <Customer diffgr:id="Customer2" msdata:rowOrder="1"   
                diffgr:hasChanges="modified"   
                CustomerID="ANATR">  
          <CompanyName>Bottom Dollar Markets</CompanyName>  
          <ContactName>Elizabeth Lincoln</ContactName>  
          <Order diffgr:id="Order2" msdata:rowOrder="1"   
               msdata:hiddenCustomerID="ANATR"   
               CustomerID="ANATR" OrderID="2"/>  
      </Customer>  
  
      <Customer diffgr:id="Customer3" msdata:rowOrder="2"   
                CustomerID="ANTON">  
         <CompanyName>Chop-suey Chinese</CompanyName>  
         <ContactName>Yang Wang</ContactName>  
         <Order diffgr:id="Order3" msdata:rowOrder="2"   
               msdata:hiddenCustomerID="ANTON"   
               CustomerID="ANTON" OrderID="3"/>  
      </Customer>  
      <Customer diffgr:id="Customer4" msdata:rowOrder="3"   
                diffgr:hasChanges="inserted"   
                CustomerID="AROUT">  
         <CompanyName>Around the Horn</CompanyName>  
         <ContactName>Thomas Hardy</ContactName>  
         <Order diffgr:id="Order4" msdata:rowOrder="3"   
                diffgr:hasChanges="inserted"   
                msdata:hiddenCustomerID="AROUT"   
               CustomerID="AROUT" OrderID="4"/>  
      </Customer>  
    </DataInstance>  
    <diffgr:before>  
      <Order diffgr:id="Order1" msdata:rowOrder="0"   
             msdata:hiddenCustomerID="ALFKI"   
             CustomerID="ALFKI" OrderID="1"/>  
      <Customer diffgr:id="Customer1" msdata:rowOrder="0"   
                CustomerID="ALFKI">  
        <CompanyName>Alfreds Futterkiste</CompanyName>  
        <ContactName>Maria Anders</ContactName>  
      </Customer>  
      <Customer diffgr:id="Customer2" msdata:rowOrder="1"   
                CustomerID="ANATR">  
        <CompanyName>Ana Trujillo Emparedados y helados</CompanyName>  
        <ContactName>Ana Trujillo</ContactName>  
      </Customer>  
    </diffgr:before>  
  </diffgr:diffgram>  
</ROOT>  
```  
  
 <span data-ttu-id="7438a-160">Логика работы с дельтами обрабатывает эту дельту следующим образом.</span><span class="sxs-lookup"><span data-stu-id="7438a-160">The DiffGram logic processes this DiffGram as follows:</span></span>  
  
-   <span data-ttu-id="7438a-161">В соответствии с логикой обработки DiffGram все элементы верхнего уровня в **\<before>** блоке сопоставлены с соответствующими таблицами, как описано в схеме сопоставления.</span><span class="sxs-lookup"><span data-stu-id="7438a-161">In accordance with DiffGram processing logic, all the top-level elements in the **\<before>** block map to corresponding tables, as described in the mapping schema.</span></span>  
  
-   <span data-ttu-id="7438a-162">**\<before>** Блок содержит **\<Order>** элемент (**дффгр: ID = "Order1"**) и **\<Customer>** элемент (**diffgr: ID = "Customer1"**), для которого нет соответствующего элемента в **\<DataInstance>** блоке (с таким же идентификатором).</span><span class="sxs-lookup"><span data-stu-id="7438a-162">The **\<before>** block has an **\<Order>** element (**dffgr:id="Order1"**) and a **\<Customer>** element (**diffgr:id="Customer1"**) for which there is no corresponding element in the **\<DataInstance>** block (with the same ID).</span></span> <span data-ttu-id="7438a-163">Это указывает на операцию удаления, во время которой записи удаляются из таблиц Cust и Ord.</span><span class="sxs-lookup"><span data-stu-id="7438a-163">This indicates a delete operation, and the records are deleted from the Cust and Ord tables.</span></span>  
  
-   <span data-ttu-id="7438a-164">**\<before>** Блок содержит **\<Customer>** элемент (**diffgr: ID = "Customer2"**), для которого имеется соответствующий **\<Customer>** элемент в **\<DataInstance>** БЛОКе (с таким же идентификатором).</span><span class="sxs-lookup"><span data-stu-id="7438a-164">The **\<before>** block has a **\<Customer>** element (**diffgr:id="Customer2"**) for which there is a corresponding **\<Customer>** element in the **\<DataInstance>** block (with the same ID).</span></span> <span data-ttu-id="7438a-165">Элемент в **\<DataInstance>** блоке указывает **diffgr: hasChanges = "Modified"**.</span><span class="sxs-lookup"><span data-stu-id="7438a-165">The element in the **\<DataInstance>** block specifies **diffgr:hasChanges="modified"**.</span></span> <span data-ttu-id="7438a-166">Это операция обновления, в которой для АНАТР клиента сведения о CompanyName и ContactName обновляются в таблице Cust с использованием значений, указанных в **\<DataInstance>** блоке.</span><span class="sxs-lookup"><span data-stu-id="7438a-166">This is an update operation in which for customer ANATR, the CompanyName and ContactName information is updated in the Cust table using values that are specified in the **\<DataInstance>** block.</span></span>  
  
-   <span data-ttu-id="7438a-167">**\<DataInstance>** Блок содержит **\<Customer>** элемент (**diffgr: ID = "Customer3"**) и **\<Order>** элемент (**diffgr: ID = "Order3"**).</span><span class="sxs-lookup"><span data-stu-id="7438a-167">The **\<DataInstance>** block has a **\<Customer>** element (**diffgr:id="Customer3"**) and an **\<Order>** element (**diffgr:id="Order3"**).</span></span> <span data-ttu-id="7438a-168">Ни один из этих элементов не указал атрибут **diffgr: hasChanges** .</span><span class="sxs-lookup"><span data-stu-id="7438a-168">Neither of these elements specify the **diffgr:hasChanges** attribute.</span></span> <span data-ttu-id="7438a-169">Таким образом, логика обработки дельт не учитывает эти элементы.</span><span class="sxs-lookup"><span data-stu-id="7438a-169">Therefore, the DiffGram processing logic ignores these elements.</span></span>  
  
-   <span data-ttu-id="7438a-170">**\<DataInstance>** Блок содержит **\<Customer>** элемент (**diffgr: ID = "Customer4"**) и **\<Order>** элемент (**diffgr: ID = "Order4"**), для которого нет соответствующих элементов в \<before> блоке.</span><span class="sxs-lookup"><span data-stu-id="7438a-170">The **\<DataInstance>** block has a **\<Customer>** element (**diffgr:id="Customer4"**) and an **\<Order>** element (**diffgr:id="Order4"**) for which there are no corresponding elements in the \<before> block.</span></span> <span data-ttu-id="7438a-171">Эти элементы в **\<DataInstance>** блоке указывают **diffgr: hasChanges = "inserted"**.</span><span class="sxs-lookup"><span data-stu-id="7438a-171">These elements in the **\<DataInstance>** block specify **diffgr:hasChanges="inserted"**.</span></span> <span data-ttu-id="7438a-172">Таким образом, в таблицы Cust и Ord добавляется новая запись.</span><span class="sxs-lookup"><span data-stu-id="7438a-172">Therefore, a new record is added in the Cust table and in the Ord table.</span></span>  
  
#### <a name="to-test-the-diffgram"></a><span data-ttu-id="7438a-173">Проверка дельты</span><span class="sxs-lookup"><span data-stu-id="7438a-173">To test the DiffGram</span></span>  
  
1.  <span data-ttu-id="7438a-174">Создайте следующие таблицы в базе данных **tempdb** .</span><span class="sxs-lookup"><span data-stu-id="7438a-174">Create the following tables in the **tempdb** database.</span></span>  
  
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
  
2.  <span data-ttu-id="7438a-175">Добавьте следующий образец данных:</span><span class="sxs-lookup"><span data-stu-id="7438a-175">Add this sample data:</span></span>  
  
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
  
3.  <span data-ttu-id="7438a-176">Скопируйте приведенную выше дельту и вставьте ее в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="7438a-176">Copy the DiffGram above and paste it into a text file.</span></span> <span data-ttu-id="7438a-177">Сохраните файл с именем MyDiffGram.xml в папке, которая использовалась на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="7438a-177">Save the file as MyDiffGram.xml in the same folder used in the previous step.</span></span>  
  
4.  <span data-ttu-id="7438a-178">Скопируйте схему DiffGramSchema, приведенную ранее в этом разделе, и вставьте ее в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="7438a-178">Copy the DiffGramSchema provided earlier in this topic and paste it into a text file.</span></span> <span data-ttu-id="7438a-179">Сохраните файл с именем DiffGramSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="7438a-179">Save the file as DiffGramSchema.xml.</span></span>  
  
5.  <span data-ttu-id="7438a-180">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить дельту.</span><span class="sxs-lookup"><span data-stu-id="7438a-180">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the DiffGram.</span></span>  
  
     <span data-ttu-id="7438a-181">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="7438a-181">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
## <a name="e-applying-updates-by-using-a-diffgram-with-the-diffgrparentid-annotation"></a><span data-ttu-id="7438a-182">Д.</span><span class="sxs-lookup"><span data-stu-id="7438a-182">E.</span></span> <span data-ttu-id="7438a-183">Применение обновлений с помощью дельты с заметкой diffgr:parentID</span><span class="sxs-lookup"><span data-stu-id="7438a-183">Applying updates by using a DiffGram with the diffgr:parentID annotation</span></span>  
 <span data-ttu-id="7438a-184">В этом примере показано, как заметка **ParentID** , указанная в **\<before>** блоке DiffGram, используется при применении обновлений.</span><span class="sxs-lookup"><span data-stu-id="7438a-184">This example illustrates how the **parentID** annotation that is specified in the **\<before>** block of the DiffGram is used in applying the updates.</span></span>  
  
```  
<NewDataSet />  
<diffgr:before>  
   <Order diffgr:id="Order1" msdata:rowOrder="0" OrderID="2" />  
   <Order diffgr:id="Order3" msdata:rowOrder="2" OrderID="4" />  
  
   <OrderDetail diffgr:id="OrderDetail1"   
                diffgr:parentId="Order1"   
                msdata:rowOrder="0"   
                ProductID="13"   
                OrderID="2" />  
   <OrderDetail diffgr:id="OrderDetail3"   
                diffgr:parentId="Order3"  
                ProductID="77"  
                OrderID="4"/>  
</diffgr:before>  
</diffgr:diffgram>  
```  
  
 <span data-ttu-id="7438a-185">Этот DiffGram указывает операцию удаления, так как существует только **\<before>** блок.</span><span class="sxs-lookup"><span data-stu-id="7438a-185">This DiffGram specifies a delete operation because there is only a **\<before>** block.</span></span> <span data-ttu-id="7438a-186">В DiffGram заметка **ParentID** используется для указания связи типа «родители-потомки» между заказами и сведениями о заказе.</span><span class="sxs-lookup"><span data-stu-id="7438a-186">In the DiffGram, the **parentID** annotation is used to specify a parent-child relationship between the orders and order details.</span></span> <span data-ttu-id="7438a-187">При удалении записей посредством SQLXML они удаляются из дочерней таблицы, указанной этой связью, а после этого из соответствующей родительской таблицы.</span><span class="sxs-lookup"><span data-stu-id="7438a-187">When SQLXML deletes the records, it deletes records from the child table that is identified by this relationship and then deletes the records from the corresponding parent table.</span></span>  
  
  
