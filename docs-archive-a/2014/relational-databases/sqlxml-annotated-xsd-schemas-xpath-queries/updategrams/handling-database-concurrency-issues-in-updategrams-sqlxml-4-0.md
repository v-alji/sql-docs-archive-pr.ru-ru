---
title: Обработка проблем параллелизма базы данных в диаграмм обновления (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- <before> block
- low concurrency protection
- database concurrency [SQLXML]
- timestamp column [SQLXML]
- updategrams [SQLXML], database concurrency
- high concurrency protection [SQLXML]
- optimistic concurrency control
- concurrency [SQLXML]
- intermediate concurrency protection [SQLXML]
ms.assetid: d4b908d1-b25b-4ad9-8478-9cd882e8c44e
author: rothja
ms.author: jroth
ms.openlocfilehash: dd808b2688e8bf05149a5454bee91123878fb2ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665965"
---
# <a name="handling-database-concurrency-issues-in-updategrams-sqlxml-40"></a><span data-ttu-id="e33f1-102">Решение проблем с параллелизмом обработки в базе данных в диаграммах обновления (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="e33f1-102">Handling Database Concurrency Issues in Updategrams (SQLXML 4.0)</span></span>
  <span data-ttu-id="e33f1-103">Как и другие механизмы обновления базы данных, диаграммы обновления должны иметь дело с одновременными обновлениями данных в многопользовательской среде.</span><span class="sxs-lookup"><span data-stu-id="e33f1-103">Like other database update mechanisms, updategrams must deal with concurrent updates to data in a multiuser environment.</span></span> <span data-ttu-id="e33f1-104">В диаграммах обновления используется оптимистическое управление параллелизмом, которое использует сравнение данных в выбранных полях как моментальных снимков, чтобы данные, которые нужно обновить, не были изменены другим пользовательским приложением после чтения из базы данных.</span><span class="sxs-lookup"><span data-stu-id="e33f1-104">Updategrams use the Optimistic Concurrency Control, which uses comparison of select field data as snapshots to ensure that the data to be updated has not been altered by another user application since it was read from the database.</span></span> <span data-ttu-id="e33f1-105">Диаграмм обновления включают эти значения моментальных снимков в **\<before>** блок диаграмм обновления.</span><span class="sxs-lookup"><span data-stu-id="e33f1-105">Updategrams include these snapshot values in the **\<before>** block of the updategrams.</span></span> <span data-ttu-id="e33f1-106">Перед обновлением базы данных диаграмма обновления проверяет значения, указанные в блоке, на **\<before>** значения, находящиеся в базе данных, чтобы убедиться, что обновление является допустимым.</span><span class="sxs-lookup"><span data-stu-id="e33f1-106">Before updating the database, the updategram checks the values that are specified in the **\<before>** block against the values currently in the database to ensure that the update is valid.</span></span>  
  
 <span data-ttu-id="e33f1-107">Управление оптимистичным параллелизмом обеспечивает три уровня защиты в диаграмме обновления: низкий (нет), промежуточный и высокий.</span><span class="sxs-lookup"><span data-stu-id="e33f1-107">The Optimistic Concurrency Control offers three levels of protection in an updategram: low (none), intermediate, and high.</span></span> <span data-ttu-id="e33f1-108">Можно выбрать нужный уровень защиты, указав соответствующую диаграмму обновления.</span><span class="sxs-lookup"><span data-stu-id="e33f1-108">You can decide what level of protection you need by specifying the updategram accordingly.</span></span>  
  
## <a name="lowest-level-of-protection"></a><span data-ttu-id="e33f1-109">Самый низкий уровень защиты</span><span class="sxs-lookup"><span data-stu-id="e33f1-109">Lowest Level of Protection</span></span>  
 <span data-ttu-id="e33f1-110">Этот уровень обеспечивает «слепое» обновление, при котором обновление обрабатывается без учета других обновлений, сделанных со времени последнего чтения базы данных.</span><span class="sxs-lookup"><span data-stu-id="e33f1-110">This level is a blind update, in which the update is processed without reference to other updates that have been made since the database was last read.</span></span> <span data-ttu-id="e33f1-111">В этом случае необходимо указать только первичные ключевые столбцы в **\<before>** блоке, чтобы определить запись, и указать обновленные сведения в **\<after>** блоке.</span><span class="sxs-lookup"><span data-stu-id="e33f1-111">In such a case, you specify only the primary key column(s) in the **\<before>** block to identify the record, and you specify the updated information in the **\<after>** block.</span></span>  
  
 <span data-ttu-id="e33f1-112">Например, новый номер телефона для связи в следующей диаграмме обновления верен, независимо от предыдущего значения телефонного номера.</span><span class="sxs-lookup"><span data-stu-id="e33f1-112">For example, the new contact phone number in the following updategram is correct, regardless of what the phone number was previously.</span></span> <span data-ttu-id="e33f1-113">Обратите внимание, что **\<before>** блок определяет только первичный ключевой столбец (ContactID).</span><span class="sxs-lookup"><span data-stu-id="e33f1-113">Notice how the **\<before>** block specifies only the primary key column (ContactID).</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
<updg:before>  
   <Person.Contact ContactID="1" />  
</updg:before>  
<updg:after>  
   <Person.Contact ContactID="1" Phone="111-111-1111" />  
</updg:after>  
</updg:sync>  
</ROOT>  
```  
  
## <a name="intermediate-level-of-protection"></a><span data-ttu-id="e33f1-114">Промежуточный уровень защиты</span><span class="sxs-lookup"><span data-stu-id="e33f1-114">Intermediate Level of Protection</span></span>  
 <span data-ttu-id="e33f1-115">На этом уровне защиты диаграмма обновления сравнивает текущие значения обновляемых данных со значениями в столбцах базы данных, чтобы проверить, что значения не были изменены другой транзакцией после чтения записи данной транзакцией.</span><span class="sxs-lookup"><span data-stu-id="e33f1-115">In this level of protection, the updategram compares the current value(s) of the data being updated with the value(s) in the database column(s) to ensure that the values have not been changed by some other transaction since the record was read by your transaction.</span></span>  
  
 <span data-ttu-id="e33f1-116">Этот уровень защиты можно получить, указав первичные ключевые столбцы и столбцы, которые обновляются в **\<before>** блоке.</span><span class="sxs-lookup"><span data-stu-id="e33f1-116">You can get this level of protection by specifying the primary key column(s) and the column(s) that you are updating in the **\<before>** block.</span></span>  
  
 <span data-ttu-id="e33f1-117">Например, данная диаграмма обновления изменяет значение в столбце Phone таблицы Person.Person для контактного лица со значением ContactID, равным 1.</span><span class="sxs-lookup"><span data-stu-id="e33f1-117">For example, this updategram changes the value in the Phone column of the Person.Contact table for the contact with ContactID of 1.</span></span> <span data-ttu-id="e33f1-118">**\<before>** Блок задает атрибут **Phone** , чтобы убедиться, что значение атрибута соответствует значению в соответствующем столбце в базе данных перед применением обновленного значения.</span><span class="sxs-lookup"><span data-stu-id="e33f1-118">The **\<before>** block specifies the **Phone** attribute to ensure that this attribute value matches the value in the corresponding column in the database before applying the updated value.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
<updg:before>  
   <Person.Contact ContactID="1" Phone="398-555-0132" />  
</updg:before>  
<updg:after>  
   <Person.Contact ContactID="1" Phone="111-111-1111" />  
</updg:after>  
</updg:sync>  
</ROOT>  
```  
  
## <a name="high-level-of-protection"></a><span data-ttu-id="e33f1-119">Высокий уровень защиты</span><span class="sxs-lookup"><span data-stu-id="e33f1-119">High Level of Protection</span></span>  
 <span data-ttu-id="e33f1-120">Высокий уровень защиты гарантирует, что запись остается неизменной со времени последнего чтения записи приложением (то есть после чтения записи приложением она не была изменена никакой другой транзакцией).</span><span class="sxs-lookup"><span data-stu-id="e33f1-120">A high level of protection ensures that the record remains the same since your application last read that record (that is, since your application has read the record, it has not been changed by any other transaction).</span></span>  
  
 <span data-ttu-id="e33f1-121">Существует два способа получить высокий уровень защиты от одновременных обновлений.</span><span class="sxs-lookup"><span data-stu-id="e33f1-121">There are two ways you can get this high level of protection against concurrent updates:</span></span>  
  
-   <span data-ttu-id="e33f1-122">Укажите дополнительные столбцы в таблице в **\<before>** блоке.</span><span class="sxs-lookup"><span data-stu-id="e33f1-122">Specify additional columns in the table in the **\<before>** block.</span></span>  
  
     <span data-ttu-id="e33f1-123">Если указать дополнительные столбцы в **\<before>** блоке, диаграмма обновления сравнивает значения, указанные для этих столбцов, со значениями, которые были в базе данных перед применением обновления.</span><span class="sxs-lookup"><span data-stu-id="e33f1-123">If you specify additional columns in the **\<before>** block, the updategram compares the values that are specified for these columns with the values that were in the database before applying the update.</span></span> <span data-ttu-id="e33f1-124">Если какие-нибудь столбцы записи изменились после чтения записи транзакцией, диаграмма обновления не выполняет обновление.</span><span class="sxs-lookup"><span data-stu-id="e33f1-124">If any of the record columns has changed since your transaction read the record, the updategram does not perform the update.</span></span>  
  
     <span data-ttu-id="e33f1-125">Например, следующий диаграмма обновления обновляет имя смены, но указывает дополнительные столбцы (StartTime, EndTime) в **\<before>** блоке, тем самым запрашивая более высокий уровень защиты от параллельных обновлений.</span><span class="sxs-lookup"><span data-stu-id="e33f1-125">For example, the following updategram updates the shift name, but specifies additional columns (StartTime,EndTime) in the **\<before>** block, thereby requesting a higher level of protection against concurrent updates.</span></span>  
  
    ```  
    <ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
    <updg:sync >  
    <updg:before>  
       <HumanResources.Shift ShiftID="1"   
                 Name="Day"   
                 StartTime="1900-01-01 07:00:00.000"   
                 EndTime="1900-01-01 15:00:00.000" />  
    </updg:before>  
    <updg:after>  
       <HumanResources.Shift Name="Morning" />  
    </updg:after>  
    </updg:sync>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="e33f1-126">Этот пример задает наивысший уровень защиты, указывая все значения столбцов для записи в **\<before>** блоке.</span><span class="sxs-lookup"><span data-stu-id="e33f1-126">This example specifies the highest level of protection by specifying all column values for the record in the **\<before>** block.</span></span>  
  
-   <span data-ttu-id="e33f1-127">Укажите столбец отметок времени (если он доступен) в **\<before>** блоке.</span><span class="sxs-lookup"><span data-stu-id="e33f1-127">Specify the timestamp column (if available) in the **\<before>** block.</span></span>  
  
     <span data-ttu-id="e33f1-128">Вместо того чтобы указывать все столбцы записи в `<before` блоке>, можно просто указать столбец timestamp (если таблица содержит одну) вместе с первичными ключевыми столбцами в **\<before>** блоке.</span><span class="sxs-lookup"><span data-stu-id="e33f1-128">Instead of specifying all the record columns in the `<before`> block, you can just specify the timestamp column (if the table has one) along with the primary key column(s) in the **\<before>** block.</span></span> <span data-ttu-id="e33f1-129">База данных обновляет столбец отметки времени уникальным значением после каждого обновления записи.</span><span class="sxs-lookup"><span data-stu-id="e33f1-129">The database updates the timestamp column to a unique value after each update of the record.</span></span> <span data-ttu-id="e33f1-130">В этом случае диаграмма обновления сравнивает значения отметок времени с соответствующим значением в базе данных.</span><span class="sxs-lookup"><span data-stu-id="e33f1-130">In this case, the updategram compares the value of the timestamp with the corresponding value in the database.</span></span> <span data-ttu-id="e33f1-131">Значение отметки времени, сохраненное в базе данных, является двоичным значением.</span><span class="sxs-lookup"><span data-stu-id="e33f1-131">The timestamp value stored in the database is a binary value.</span></span> <span data-ttu-id="e33f1-132">Поэтому столбец отметки времени в схеме должен быть указан как `dt:type="bin.hex"`, `dt:type="bin.base64"` или `sql:datatype="timestamp"`.</span><span class="sxs-lookup"><span data-stu-id="e33f1-132">Therefore, the timestamp column must be specified in the schema as `dt:type="bin.hex"`, `dt:type="bin.base64"`, or `sql:datatype="timestamp"`.</span></span> <span data-ttu-id="e33f1-133">(Можно указать либо `xml` тип данных, либо [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] тип данных.)</span><span class="sxs-lookup"><span data-stu-id="e33f1-133">(You can specify either the `xml` data type or the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data type.)</span></span>  
  
#### <a name="to-test-the-updategram"></a><span data-ttu-id="e33f1-134">Тестирование диаграммы обновления</span><span class="sxs-lookup"><span data-stu-id="e33f1-134">To test the updategram</span></span>  
  
1.  <span data-ttu-id="e33f1-135">Создайте эту таблицу в базе данных **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="e33f1-135">Create this table in the **tempdb** database:</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE Customer (  
                 CustomerID  varchar(5),  
                 ContactName varchar(20),  
                 LastUpdated timestamp)  
    ```  
  
2.  <span data-ttu-id="e33f1-136">Добавьте следующий образец записи:</span><span class="sxs-lookup"><span data-stu-id="e33f1-136">Add this sample record:</span></span>  
  
    ```  
    INSERT INTO Customer (CustomerID, ContactName) VALUES   
                         ('C1', 'Andrew Fuller')  
    ```  
  
3.  <span data-ttu-id="e33f1-137">Скопируйте и вставьте следующую схему XSD в приложение «Блокнот».</span><span class="sxs-lookup"><span data-stu-id="e33f1-137">Copy the following XSD schema and paste it into Notepad.</span></span> <span data-ttu-id="e33f1-138">Сохраните код в файл с именем ConcurrencySampleSchema.xml:</span><span class="sxs-lookup"><span data-stu-id="e33f1-138">Save it as ConcurrencySampleSchema.xml:</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
      <xsd:element name="Customer" sql:relation="Customer" >  
       <xsd:complexType>  
            <xsd:attribute name="CustomerID"    
                           sql:field="CustomerID"   
                           type="xsd:string" />   
  
            <xsd:attribute name="ContactName"    
                           sql:field="ContactName"   
                           type="xsd:string" />  
  
            <xsd:attribute name="LastUpdated"   
                           sql:field="LastUpdated"   
                           type="xsd:hexBinary"   
                 sql:datatype="timestamp" />  
  
        </xsd:complexType>  
      </xsd:element>  
    </xsd:schema>  
    ```  
  
4.  <span data-ttu-id="e33f1-139">Скопируйте следующий код диаграммы обновления в приложении «Блокнот» и сохраните его в файле с именем ConcurrencySampleTemplate.xml в том же каталоге, в котором сохранена схема, созданная на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="e33f1-139">Copy the following updategram code into Notepad and save it as ConcurrencySampleTemplate.xml in the same directory where you saved the schema created in the previous step.</span></span> <span data-ttu-id="e33f1-140">Обратите внимание, что указанное ниже значение отметки времени для столбца LastUpdated будет иным, нежели в примере таблицы Customer, поэтому скопируйте фактическое значение для LastUpdated из таблицы и вставьте его в диаграмму обновления.</span><span class="sxs-lookup"><span data-stu-id="e33f1-140">(Note the timestamp value below for LastUpdated will differ in your example Customer table, so copy the actual value for LastUpdated from the table and paste it into the updategram.)</span></span>  
  
    ```  
    <ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
    <updg:sync mapping-schema="SampleSchema.xml" >  
    <updg:before>  
       <Customer CustomerID="C1"   
                 LastUpdated = "0x00000000000007D1" />  
    </updg:before>  
    <updg:after>  
       <Customer ContactName="Robert King" />  
    </updg:after>  
    </updg:sync>  
    </ROOT>  
    ```  
  
5.  <span data-ttu-id="e33f1-141">Создайте и запустите тестовый скрипт SQLXML 4.0 (Sqlxml4test.vbs), чтобы выполнить шаблон.</span><span class="sxs-lookup"><span data-stu-id="e33f1-141">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="e33f1-142">Дополнительные сведения см. [в разделе Использование ADO для выполнения запросов SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="e33f1-142">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="e33f1-143">Эквивалентная схема XDR:</span><span class="sxs-lookup"><span data-stu-id="e33f1-143">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"  
        xmlns:dt="urn:schemas-microsoft-com:datatypes"  
        xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
<ElementType name="Customer" sql:relation="Customer" >  
    <AttributeType name="CustomerID" />  
    <AttributeType name="ContactName" />  
    <AttributeType name="LastUpdated"  dt:type="bin.hex"   
                                       sql:datatype="timestamp" />  
    <attribute type="CustomerID" />  
    <attribute type="ContactName" />  
    <attribute type="LastUpdated" />  
</ElementType>  
</Schema>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e33f1-144">См. также:</span><span class="sxs-lookup"><span data-stu-id="e33f1-144">See Also</span></span>  
 [<span data-ttu-id="e33f1-145">Вопросы безопасности диаграмма обновления &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="e33f1-145">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
