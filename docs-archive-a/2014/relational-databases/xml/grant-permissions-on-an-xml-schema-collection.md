---
title: Предоставление разрешений на коллекцию схем XML | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- granting permissions [SQL Server], XML schema collections
- ALTER permission
ms.assetid: ffbb829c-3b8f-4e5d-97d9-ab4059aab0db
author: rothja
ms.author: jroth
ms.openlocfilehash: 2dc6384acb2f079245c80923e683ebe2c03d2562
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729162"
---
# <a name="grant-permissions-on-an-xml-schema-collection"></a><span data-ttu-id="559e0-102">Предоставление разрешений на коллекции схем XML</span><span class="sxs-lookup"><span data-stu-id="559e0-102">Grant Permissions on an XML Schema Collection</span></span>
  <span data-ttu-id="559e0-103">На создание коллекции схем XML, а также на объекты коллекции схем XML можно предоставлять разрешения.</span><span class="sxs-lookup"><span data-stu-id="559e0-103">You can grant permissions to create an XML schema collection and also grant permissions on an XML schema collection object.</span></span>  
  
## <a name="granting-permission-to-create-an-xml-schema-collection"></a><span data-ttu-id="559e0-104">Предоставление разрешений на создание коллекции XML-схем</span><span class="sxs-lookup"><span data-stu-id="559e0-104">Granting Permission to Create an XML Schema Collection</span></span>  
 <span data-ttu-id="559e0-105">Для создания коллекции XML-схем требуются следующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="559e0-105">To create an XML schema collection, the following permissions are required:</span></span>  
  
-   <span data-ttu-id="559e0-106">Участнику требуется разрешение CREATE XML SCHEMA COLLECTION на уровне базы данных.</span><span class="sxs-lookup"><span data-stu-id="559e0-106">The principal requires CREATE XML SCHEMA COLLECTION permission at the database-level.</span></span>  
  
-   <span data-ttu-id="559e0-107">Поскольку областью действия коллекции XML-схем является реляционная схема, участнику требуется разрешение ALTER на реляционную схему.</span><span class="sxs-lookup"><span data-stu-id="559e0-107">Because the XML schema collections are relational schema-scoped, the principal must also have ALTER permission on the relational schema.</span></span>  
  
 <span data-ttu-id="559e0-108">Следующие разрешения позволяют участнику создавать коллекцию XML-схем в реляционной схеме в базе данных сервера:</span><span class="sxs-lookup"><span data-stu-id="559e0-108">The following permissions let a principal create an XML schema collection in a relational schema in a database on a server:</span></span>  
  
-   <span data-ttu-id="559e0-109">разрешение CONTROL на сервере;</span><span class="sxs-lookup"><span data-stu-id="559e0-109">CONTROL permission on the server</span></span>  
  
-   <span data-ttu-id="559e0-110">разрешение ALTER ANY DATABASE на сервере;</span><span class="sxs-lookup"><span data-stu-id="559e0-110">ALTER ANY DATABASE permission on the server</span></span>  
  
-   <span data-ttu-id="559e0-111">разрешение ALTER в базе данных;</span><span class="sxs-lookup"><span data-stu-id="559e0-111">ALTER permission on the database</span></span>  
  
-   <span data-ttu-id="559e0-112">разрешение CONTROL в базе данных;</span><span class="sxs-lookup"><span data-stu-id="559e0-112">CONTROL permission in the database</span></span>  
  
-   <span data-ttu-id="559e0-113">разрешения ALTER ANY SCHEMA и CREATE XML SCHEMA COLLECTION в базе данных;</span><span class="sxs-lookup"><span data-stu-id="559e0-113">ALTER ANY SCHEMA permission and CREATE XML SCHEMA COLLECTION permission in the database</span></span>  
  
-   <span data-ttu-id="559e0-114">разрешение ALTER или CONTROL в реляционной схеме и разрешение CREATE XML SCHEMA COLLECTION в базе данных.</span><span class="sxs-lookup"><span data-stu-id="559e0-114">ALTER or CONTROL permission on the relational schema and CREATE XML SCHEMA COLLECTION permission in the database</span></span>  
  
 <span data-ttu-id="559e0-115">Этот метод разрешений используется в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="559e0-115">This last method of permissions is used in the following example.</span></span>  
  
 <span data-ttu-id="559e0-116">Владелец реляционной схемы становится владельцем коллекции XML-схем, созданной в данной схеме.</span><span class="sxs-lookup"><span data-stu-id="559e0-116">The owner of the relational schema becomes the owner of the XML schema collection created in that schema.</span></span> <span data-ttu-id="559e0-117">Этот владелец получает полный контроль над коллекцией XML-схем.</span><span class="sxs-lookup"><span data-stu-id="559e0-117">This owner then has full control over the XML schema collection.</span></span> <span data-ttu-id="559e0-118">Поэтому он может изменять коллекцию XML-схем, вводить XML-столбец и удалять коллекцию XML-схем.</span><span class="sxs-lookup"><span data-stu-id="559e0-118">Therefore, this owner can modify the XML schema collection, type an xml column, or drop the XML schema collection.</span></span>  
  
## <a name="granting-permissions-on-an-xml-schema-collection-object"></a><span data-ttu-id="559e0-119">Предоставление разрешений на объект коллекции XML-схем</span><span class="sxs-lookup"><span data-stu-id="559e0-119">Granting Permissions on an XML Schema Collection Object</span></span>  
 <span data-ttu-id="559e0-120">В коллекции XML-схем допускаются следующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="559e0-120">The following permissions are allowed on the XML schema collection:</span></span>  
  
-   <span data-ttu-id="559e0-121">Разрешение ALTER требуется при изменении содержимого существующей коллекции XML-схем с помощью инструкции ALTER XML SCHEMA COLLECTION.</span><span class="sxs-lookup"><span data-stu-id="559e0-121">The ALTER permission is required when modifying contents of an existing XML schema collection by using the ALTER XML SCHEMA COLLECTION statement.</span></span>  
  
-   <span data-ttu-id="559e0-122">Разрешение CONTROL дает возможность пользователю выполнять любые операции в коллекции XML-схем.</span><span class="sxs-lookup"><span data-stu-id="559e0-122">The CONTROL permission lets a user perform any operation on the XML schema collection.</span></span>  
  
-   <span data-ttu-id="559e0-123">Разрешение TAKE OWNERSHIP необходимо для передачи прав на обладание коллекцией схем XML от одного участника к другому.</span><span class="sxs-lookup"><span data-stu-id="559e0-123">The TAKE OWNERSHIP permission is required to transfer ownership of the XML schema collection from one principal to another.</span></span>  
  
-   <span data-ttu-id="559e0-124">Разрешение REFERENCES дает участнику право на использование коллекции схем XML для типизации или ограничения типа столбцов `xml` в таблицах, представлениях и параметрах.</span><span class="sxs-lookup"><span data-stu-id="559e0-124">The REFERENCES permission authorizes the principal to use the XML schema collection to type or constrain `xml` type columns, in tables and views and parameters.</span></span> <span data-ttu-id="559e0-125">Кроме того, разрешение REFERENCES необходимо, если одна коллекция схем XML ссылается на другую.</span><span class="sxs-lookup"><span data-stu-id="559e0-125">The REFERENCES permission is also required when one XML schema collection refers to another.</span></span>  
  
-   <span data-ttu-id="559e0-126">Разрешение VIEW DEFINITION позволяет участнику выполнять запрос к содержимому коллекции XML-схем через XML_SCHEMA_NAMESPACE или представления каталогов при условии, что этот участник также имеет разрешение ALTER, REFERENCES или CONTROL на эту коллекцию.</span><span class="sxs-lookup"><span data-stu-id="559e0-126">The VIEW DEFINITION permission allows the principal to query the contents of an XML schema collection either through XML_SCHEMA_NAMESPACE or through the catalog views, provided this principal also has one of the ALTER, REFERENCES, or CONTROL permissions on the collection.</span></span>  
  
-   <span data-ttu-id="559e0-127">Разрешение EXECUTE необходимо для проверки значений, вставленных или обновленных участником, по коллекции схем XML, которая типизирует или ограничивает столбцы, переменные и параметры типа `xml`.</span><span class="sxs-lookup"><span data-stu-id="559e0-127">The EXECUTE permission is required to validate values inserted or updated by the principal against the XML schema collection that is typing or constraining the `xml` type columns, variables, and parameters.</span></span> <span data-ttu-id="559e0-128">Это разрешение требуется также для запросов к XML-данным, хранящимся в этих столбцах и переменных.</span><span class="sxs-lookup"><span data-stu-id="559e0-128">You also need this permission when you are querying the XML stored in these columns and variables.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="559e0-129">Примеры</span><span class="sxs-lookup"><span data-stu-id="559e0-129">Examples</span></span>  
 <span data-ttu-id="559e0-130">Представленные в следующих примерах сценарии отображают организацию разрешений на XML-схемы.</span><span class="sxs-lookup"><span data-stu-id="559e0-130">The scenarios in the following examples illustrate how XML schema permissions work.</span></span> <span data-ttu-id="559e0-131">В каждом примере создается соответствующая тестовая база данных, реляционные схемы и имена входа.</span><span class="sxs-lookup"><span data-stu-id="559e0-131">Each example creates the necessary test database, relational schemas, and logins.</span></span> <span data-ttu-id="559e0-132">Этим именам входа предоставляются необходимые разрешения на коллекции XML-схем.</span><span class="sxs-lookup"><span data-stu-id="559e0-132">These logins are granted the necessary XML schema collection permissions.</span></span> <span data-ttu-id="559e0-133">После завершения работы в каждом примере выполняются действия по очистке.</span><span class="sxs-lookup"><span data-stu-id="559e0-133">Each example does the necessary clean up at the end.</span></span>  
  
### <a name="a-granting-permissions-to-create-an-xml-schema-collection"></a><span data-ttu-id="559e0-134">A.</span><span class="sxs-lookup"><span data-stu-id="559e0-134">A.</span></span> <span data-ttu-id="559e0-135">Предоставление разрешений на создание коллекции схем XML</span><span class="sxs-lookup"><span data-stu-id="559e0-135">Granting permissions to create an XML schema collection</span></span>  
 <span data-ttu-id="559e0-136">В следующем примере показано предоставление разрешений на создание участником коллекции схем XML.</span><span class="sxs-lookup"><span data-stu-id="559e0-136">The following example shows how to grant permissions so that a principal can create an XML schema collection.</span></span> <span data-ttu-id="559e0-137">В примере создается образец базы данных и пользователь `TestLogin1`.</span><span class="sxs-lookup"><span data-stu-id="559e0-137">The example creates a sample database and a test user, `TestLogin1`.</span></span> <span data-ttu-id="559e0-138">`TestLogin1` предоставляется разрешение `ALTER` в реляционной схеме и разрешение `CREATE XML SCHEMA COLLECTION` в базе данных.</span><span class="sxs-lookup"><span data-stu-id="559e0-138">`TestLogin1` is then given `ALTER` permission on the relational schema and given `CREATE XML SCHEMA COLLECTION` permission on the database.</span></span> <span data-ttu-id="559e0-139">С этими разрешениями пользователь `TestLogin1` успешно создает образец коллекции схем XML.</span><span class="sxs-lookup"><span data-stu-id="559e0-139">With these permissions, `TestLogin1` succeeds in creating a sample XML schema collection.</span></span>  
  
```  
SETUSER  
GO  
USE master  
GO  
CREATE LOGIN TestLogin1 WITH password='SQLSvrPwd1'  
GO  
CREATE DATABASE SampleDBForSchemaPermissions  
GO  
USE SampleDBForSchemaPermissions  
GO  
CREATE USER TestLogin1  
GO  
-- User must have ALTER permission on the relational schema in the database.  
GRANT ALTER ON SCHEMA::dbo TO TestLogin1  
GO  
-- User also must have permission to create XML schema collections in the database.  
GRANT CREATE XML SCHEMA COLLECTION   
TO TestLogin1  
GO  
-- Execute CREATE XML SCHEMA COLLECTION.  
SETUSER 'TestLogin1'  
GO  
CREATE XML SCHEMA COLLECTION myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
<xsd:element name="AdditionalContactInfo" >  
  <xsd:complexType mixed="true" >  
    <xsd:sequence>  
      <xsd:any processContents="strict"    
               namespace="http://schemas.adventure-works.com/Contact/Record   
                          http://schemas.adventure-works.com/AdditionalContactTypes"  
               minOccurs="0" maxOccurs="unbounded" />  
    </xsd:sequence>  
  </xsd:complexType>  
</xsd:element>  
<xsd:element name="root" type="xsd:byte"/>  
</xsd:schema>'  
GO  
-- Final cleanup  
SETUSER  
GO  
USE master  
GO  
DROP DATABASE SampleDBForSchemaPermissions  
GO  
DROP LOGIN TestLogin1  
GO  
```  
  
### <a name="b-granting-permission-to-use-an-existing-xml-schema-collection"></a><span data-ttu-id="559e0-140">Б.</span><span class="sxs-lookup"><span data-stu-id="559e0-140">B.</span></span> <span data-ttu-id="559e0-141">Предоставление разрешений на использование существующей коллекции схем XML</span><span class="sxs-lookup"><span data-stu-id="559e0-141">Granting permission to use an existing XML schema collection</span></span>  
 <span data-ttu-id="559e0-142">Следующий пример далее иллюстрирует модель разрешений для коллекции схем XML.</span><span class="sxs-lookup"><span data-stu-id="559e0-142">The following example further shows the permission model for the XML schema collection.</span></span> <span data-ttu-id="559e0-143">В нем показаны различные разрешения, необходимые для создания коллекции схем XML и работы с ней.</span><span class="sxs-lookup"><span data-stu-id="559e0-143">The example shows how different permissions are required to create and use the XML schema collection.</span></span>  
  
 <span data-ttu-id="559e0-144">В примере создается образец базы данных и имя входа `TestLogin1`.</span><span class="sxs-lookup"><span data-stu-id="559e0-144">The example creates a test database and a login, `TestLogin1`.</span></span> <span data-ttu-id="559e0-145">`TestLogin1` создает коллекцию схем XML в базе данных.</span><span class="sxs-lookup"><span data-stu-id="559e0-145">`TestLogin1` creates an XML schema collection in the database.</span></span> <span data-ttu-id="559e0-146">Имя входа создает таблицу и с помощью коллекции схем XML создает типизированный XML-столбец.</span><span class="sxs-lookup"><span data-stu-id="559e0-146">The login then creates a table and uses the XML schema collection to create a typed xml column.</span></span> <span data-ttu-id="559e0-147">Затем пользователь вставляет данные и выполняет к ним запрос.</span><span class="sxs-lookup"><span data-stu-id="559e0-147">The user then inserts data and queries it.</span></span> <span data-ttu-id="559e0-148">Для всех этих шагов необходимы соответствующие разрешения схемы, что отражается в программном коде.</span><span class="sxs-lookup"><span data-stu-id="559e0-148">All these steps require the necessary schema permissions, as shown in the code.</span></span>  
  
```  
SETUSER  
GO  
USE master  
GO  
CREATE LOGIN TestLogin1 WITH password='SQLSvrPwd1'  
GO  
CREATE DATABASE SampleDBForSchemaPermissions  
GO  
USE SampleDBForSchemaPermissions  
GO  
CREATE USER TestLogin1  
GO  
-- Grant permission to the user.  
SETUSER  
GO  
-- User must have ALTER permission on the relational schema in the database.  
GRANT ALTER ON SCHEMA::dbo TO TestLogin1  
GO  
-- User also must have permission to create XML schema collections in the database.  
GRANT CREATE XML SCHEMA COLLECTION   
TO TestLogin1  
GO  
-- Now user can execute the previous CREATE XML SCHEMA COLLECTION statement.  
SETUSER 'TestLogin1'  
GO  
CREATE XML SCHEMA COLLECTION myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
  
<xsd:element name="AdditionalContactInfo" >  
  <xsd:complexType mixed="true" >  
    <xsd:sequence>  
      <xsd:any processContents="strict"    
               namespace="http://schemas.adventure-works.com/Contact/Record   
                          http://schemas.adventure-works.com/AdditionalContactTypes"  
               minOccurs="0" maxOccurs="unbounded" />  
    </xsd:sequence>  
  </xsd:complexType>  
</xsd:element>  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
GO  
  
-- Create a table by using the collection to type an XML column.   
--TestLogin1 must have permission to create a table.  
SETUSER  
GO  
GRANT CREATE TABLE TO TestLogin1  
GO  
-- The user also must have REFERENCES permission to use the XML schema collection  
-- to create a typed XML column (REFERENCES permission on schema   
-- collection is not needed).  
GRANT REFERENCES ON XML SCHEMA COLLECTION::myTestSchemaCollection   
TO TestLogin1  
GO  
-- Now user can create a table and use the XML schema collection to create   
-- a typed XML column.  
SETUSER 'TestLogin1'  
GO  
CREATE TABLE MyTestTable (xmlCol xml (dbo.myTestSchemaCollection))  
GO  
-- To insert data in the table, the user needs EXECUTE permission on the XML schema collection.  
-- GRANT EXECUTE permission to TestLogin2 on the xml schema collection.  
SETUSER  
GO  
GRANT EXECUTE ON XML SCHEMA COLLECTION::myTestSchemaCollection   
TO TestLogin1  
GO  
-- TestLogin1 does not own the dbo schema. This user must have INSERT permission.  
GRANT INSERT TO TestLogin1  
GO  
-- Now the user can insert data into the table.  
SETUSER 'TestLogin1'  
GO  
INSERT INTO MyTestTable VALUES('  
<telephone xmlns="http://schemas.adventure-works.com/Additional/ContactInfo">111-1111</telephone>  
')  
GO  
-- To query the table, TestLogin1 must have permissions: SELECT on the table and EXECUTE on the XML schema collection.  
SETUSER  
GO  
GRANT SELECT TO TestLogin1  
GO  
-- TestLogin1 already has EXECUTE permission on the schema (granted before inserting a record in the table).  
SELECT xmlCol.query('declare default element namespace "http://schemas.adventure-works.com/Additional/ContactInfo" /telephone[1]')  
FROM MyTestTable  
GO  
-- To show that the user must have EXECUTE permission to query, revoke the  
-- previously granted permission and return the query.  
SETUSER  
GO  
REVOKE EXECUTE ON XML SCHEMA COLLECTION::myTestSchemaCollection to TestLogin1  
Go  
-- Now TestLogin1 cannot execute the query.  
SETUSER 'TestLogin1'  
GO  
SELECT xmlCol.query('declare default element namespace "http://schemas.adventure-works.com/Additional/ContactInfo" /telephone[1]')  
FROM MyTestTable  
GO  
-- Final cleanup   
SETUSER  
GO  
USE master  
GO  
DROP DATABASE SampleDBForSchemaPermissions  
GO  
DROP LOGIN TestLogin1  
GO  
```  
  
### <a name="c-granting-alter-permission-on-an-xml-schema-collection"></a><span data-ttu-id="559e0-149">В.</span><span class="sxs-lookup"><span data-stu-id="559e0-149">C.</span></span> <span data-ttu-id="559e0-150">Предоставление разрешения ALTER на коллекцию схем XML</span><span class="sxs-lookup"><span data-stu-id="559e0-150">Granting ALTER permission on an XML schema collection</span></span>  
 <span data-ttu-id="559e0-151">Для изменения существующей коллекции схем XML в базе данных пользователю необходимо разрешение ALTER.</span><span class="sxs-lookup"><span data-stu-id="559e0-151">A user must have ALTER permission to modify an existing XML schema collection in the database.</span></span> <span data-ttu-id="559e0-152">В следующем примере показано предоставление разрешения `ALTER` .</span><span class="sxs-lookup"><span data-stu-id="559e0-152">The following example shows how to grant `ALTER` permission.</span></span>  
  
```  
SETUSER  
GO  
USE master  
GO  
CREATE LOGIN TestLogin1 WITH password='SQLSvrPwd1'  
GO  
CREATE DATABASE SampleDBForSchemaPermissions  
GO  
USE SampleDBForSchemaPermissions  
GO  
CREATE USER TestLogin1  
GO  
-- Grant permission to the user.  
SETUSER  
GO  
-- User must have ALTER permission on the relational schema in the database.  
GRANT ALTER ON SCHEMA::dbo TO TestLogin1  
GO  
-- User also must have permission to create XML schema collections in the database.  
GRANT CREATE XML SCHEMA COLLECTION   
TO TestLogin1  
GO  
-- Now user can execute the previous CREATE XML SCHEMA COLLECTION statement.  
SETUSER 'TestLogin1'  
GO  
CREATE XML SCHEMA COLLECTION myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
  
<xsd:element name="AdditionalContactInfo" >  
  <xsd:complexType mixed="true" >  
    <xsd:sequence>  
      <xsd:any processContents="strict"    
               namespace="http://schemas.adventure-works.com/Contact/Record   
                          http://schemas.adventure-works.com/AdditionalContactTypes"  
               minOccurs="0" maxOccurs="unbounded" />  
    </xsd:sequence>  
  </xsd:complexType>  
</xsd:element>  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
GO  
-- Grant ALTER permission to TestLogin1.  
setuser  
GO  
GRANT ALTER ON XML SCHEMA COLLECTION::myTestSchemaCollection TO TestLogin1  
GO  
-- TestLogin1 should be able to add components to the collection.  
SETUSER 'TestLogin1'  
GO  
ALTER XML SCHEMA COLLECTION myTestSchemaCollection ADD '  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns="http://schemas.adventure-works.com/Additional/ContactInfo"   
elementFormDefault="qualified">  
 <xsd:element name="pager" type="xsd:string"/>  
</xsd:schema>  
'  
Go  
-- Final cleanup   
SETUSER  
GO  
USE master  
GO  
DROP DATABASE SampleDBForSchemaPermissions  
GO  
DROP LOGIN TestLogin1  
GO  
```  
  
### <a name="d-granting-take-ownership-permission-on-an-xml-schema-collection"></a><span data-ttu-id="559e0-153">Г.</span><span class="sxs-lookup"><span data-stu-id="559e0-153">D.</span></span> <span data-ttu-id="559e0-154">Предоставление разрешения TAKE OWNERSHIP на коллекцию схем XML</span><span class="sxs-lookup"><span data-stu-id="559e0-154">Granting TAKE OWNERSHIP permission on an XML schema collection</span></span>  
 <span data-ttu-id="559e0-155">В следующем примере показано, как права владельца коллекции схем XML могут передаваться от одного пользователя другому.</span><span class="sxs-lookup"><span data-stu-id="559e0-155">The following example shows how to transfer XML schema ownership from one user to another.</span></span> <span data-ttu-id="559e0-156">Чтобы пример был более интересным, пользователи работают в разных реляционных схемах.</span><span class="sxs-lookup"><span data-stu-id="559e0-156">To make the example more interesting, the users in this example work in different default relational schemas.</span></span>  
  
 <span data-ttu-id="559e0-157">Код в примере выполняет следующие действия.</span><span class="sxs-lookup"><span data-stu-id="559e0-157">This example does the following:</span></span>  
  
-   <span data-ttu-id="559e0-158">Создается база данных с двумя реляционными схемами — `dbo` и `myOtherDBSchema`.</span><span class="sxs-lookup"><span data-stu-id="559e0-158">Creates a database with two relational schemas, `dbo` and `myOtherDBSchema`).</span></span>  
  
-   <span data-ttu-id="559e0-159">Создаются два пользователя, `TestLogin1` и `TestLogin2`.</span><span class="sxs-lookup"><span data-stu-id="559e0-159">Creates two users, `TestLogin1` and `TestLogin2`.</span></span> <span data-ttu-id="559e0-160">`TestLogin2` назначается владельцем реляционной схемы `myOtherDBSchema` .</span><span class="sxs-lookup"><span data-stu-id="559e0-160">`TestLogin2` is made the owner of the `myOtherDBSchema` relational schema.</span></span>  
  
-   <span data-ttu-id="559e0-161">`TestLogin1` создает коллекцию схем XML в реляционной схеме `dbo` .</span><span class="sxs-lookup"><span data-stu-id="559e0-161">`TestLogin1` creates an XML schema collection in the `dbo` relational schema.</span></span>  
  
-   <span data-ttu-id="559e0-162">`TestLogin1` предоставляет пользователю `TAKE OWNERSHIP` разрешение `TestLogin2`.</span><span class="sxs-lookup"><span data-stu-id="559e0-162">`TestLogin1` then gives `TAKE OWNERSHIP` permission on the XML schema collection to `TestLogin2`.</span></span>  
  
-   <span data-ttu-id="559e0-163">`TestLogin2` становится владельцем коллекции схем XML в схеме `myOtherDBSchema`, реляционная схема коллекции схем XML не изменяется.</span><span class="sxs-lookup"><span data-stu-id="559e0-163">`TestLogin2` becomes the owner of the XML schema collection in `myOtherDBSchema`, without changing the relational schema of the XML schema collection.</span></span>  
  
```  
CREATE LOGIN TestLogin1 with password='SQLSvrPwd1'  
GO  
CREATE LOGIN TestLogin2 with password='SQLSvrPwd2'  
GO  
CREATE DATABASE SampleDBForSchemaPermissions  
GO  
USE SampleDBForSchemaPermissions  
GO  
-- Create another relational schema in the database.  
CREATE SCHEMA myOtherDBSchema  
GO  
-- Create users in the database. Note TestLogin2's default schema is  
-- myOtherDBSchema.  
CREATE USER TestLogin1  
GO  
CREATE USER TestLogin2 WITH DEFAULT_SCHEMA=myOtherDBSchema  
GO  
-- TestLogin2 will own myOtherDBSchema relational schema.  
ALTER AUTHORIZATION ON SCHEMA::myOtherDBSchema TO TestLogin2  
GO  
  
-- For TestLogin1 to create XML schema collection, the following  
-- permission is required.  
GRANT CREATE XML SCHEMA COLLECTION   
TO TestLogin1  
GO  
GRANT ALTER ON SCHEMA::dbo TO TestLogin1  
GO  
-- Now TestLogin1 can create an XML schema collection.  
setuser 'TestLogin1'  
GO  
CREATE XML SCHEMA COLLECTION myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
  
<xsd:element name="AdditionalContactInfo" >  
 <xsd:complexType mixed="true" >  
    <xsd:sequence>  
      <xsd:any processContents="strict"   
               namespace="http://schemas.adventure-works.com/Contact/Record   
                          http://schemas.adventure-works.com/AdditionalContactTypes"  
               minOccurs="0" maxOccurs="unbounded" />  
    </xsd:sequence>  
 </xsd:complexType>  
</xsd:element>  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
GO  
  
-- Grant TAKE OWNERSHIP to TestLogin2.  
SETUSER  
GO  
GRANT TAKE OWNERSHIP ON XML SCHEMA COLLECTION::dbo.myTestSchemaCollection   
TO TestLogin2  
GO  
-- Verify the owner. Note the UserName and Principal_id is null.   
SELECT user_name(sys.xml_schema_collections.principal_id) as UserName,   
       sys.schemas.name as RelSchemaName,*   
FROM   sys.xml_schema_collections   
      JOIN sys.schemas   
      ON sys.schemas.schema_id=sys.xml_schema_collections.schema_id  
GO  
-- TestLogin2 can take ownership now.  
setuser 'TestLogin2'  
GO  
ALTER AUTHORIZATION ON XML SCHEMA COLLECTION::dbo.myTestSchemaCollection   
TO TestLogin2  
GO  
-- Note that although TestLogin2 is the owner,the XML schema collection   
-- is still in dbo.  
SELECT user_name(sys.xml_schema_collections.principal_id) as UserName,   
      sys.schemas.name as RelSchemaName,*   
FROM sys.xml_schema_collections JOIN sys.schemas   
     ON sys.schemas.schema_id=sys.xml_schema_collections.schema_id  
GO  
  
-- TestLogin2 moves the collection from dbo to myOtherDBSchema relational schema.  
-- TestLogin2 already has all necessary permissions.  
-- 1) TestLogin2 owns the destination relational schema so he can alter it.  
-- 2) TestLogin2 owns the XML schema collection (therefore, has CONTROL permission).  
ALTER SCHEMA myOtherDBSchema  
TRANSFER XML SCHEMA COLLECTION::dbo.myTestSchemaCollection  
GO  
  
SELECT user_name(sys.xml_schema_collections.principal_id) as UserName,   
       sys.schemas.name as RelSchemaName,*   
FROM   sys.xml_schema_collections JOIN sys.schemas   
       ON sys.schemas.schema_id=sys.xml_schema_collections.schema_id  
GO  
-- Final cleanup   
SETUSER  
GO  
USE master  
GO  
DROP DATABASE SampleDBForSchemaPermissions  
GO  
DROP LOGIN TestLogin1  
DROP LOGIN TestLogin2  
go   
```  
  
### <a name="e-granting-view-definition-permission-on-an-xml-schema-collection"></a><span data-ttu-id="559e0-164">Д.</span><span class="sxs-lookup"><span data-stu-id="559e0-164">E.</span></span> <span data-ttu-id="559e0-165">Предоставление разрешения VIEW DEFINITION на коллекцию схем XML</span><span class="sxs-lookup"><span data-stu-id="559e0-165">Granting VIEW DEFINITION permission on an XML schema collection</span></span>  
 <span data-ttu-id="559e0-166">В примере показано, каким образом предоставляются разрешения VIEW DEFINITION на коллекцию схем XML.</span><span class="sxs-lookup"><span data-stu-id="559e0-166">The following example shows how to grant VIEW DEFINITION permissions for an XML schema collection.</span></span>  
  
```  
SETUSER  
GO  
USE master  
GO  
IF EXISTS( SELECT * FROM sysdatabases WHERE name='permissionsDB' )  
   DROP DATABASE permissionsDB  
GO  
IF EXISTS( SELECT * FROM sys.sql_logins WHERE name='schemaUser' )  
   DROP LOGIN schemaUser  
GO  
CREATE DATABASE permissionsDB  
GO  
CREATE LOGIN schemaUser WITH PASSWORD='Pass#123',DEFAULT_DATABASE=permissionsDB  
GO  
GRANT CONNECT SQL TO schemaUser  
GO  
USE permissionsDB  
GO  
CREATE USER schemaUser WITH DEFAULT_SCHEMA=dbo  
GO  
CREATE XML SCHEMA COLLECTION MySC AS '  
<schema xmlns="http://www.w3.org/2001/XMLSchema" targetNamespace="http://ns"  
xmlns:ns="http://ns">  
  
   <simpleType name="ListOfIntegers">  
      <list itemType="integer"/>  
   </simpleType>  
  
   <element name="root" type="ns:ListOfIntegers"/>  
  
   <element name="gRoot" type="gMonth"/>  
  
</schema>  
'  
GO  
-- schemaUser cannot see the contents of the collection.  
SETUSER 'schemaUser'  
GO  
SELECT XML_SCHEMA_NAMESPACE(N'dbo',N'MySC')  
GO  
  
-- Grant schemaUser VIEW DEFINITION and REFERENCES permissions  
-- on the XML schema collection.  
SETUSER  
GO  
GRANT VIEW DEFINITION ON XML SCHEMA COLLECTION::dbo.MySC TO schemaUser  
GO  
GRANT REFERENCES ON XML SCHEMA COLLECTION::dbo.MySC TO schemaUser  
GO  
-- Now schemaUser can see the content of the collection.  
SETUSER 'schemaUser'  
GO  
SELECT XML_SCHEMA_NAMESPACE(N'dbo',N'MySC')  
GO  
-- Revoke schemaUser VIEW DEFINITION permissions  
-- on the XML schema collection.  
SETUSER  
GO  
REVOKE VIEW DEFINITION ON XML SCHEMA COLLECTION::dbo.MySC FROM schemaUser  
GO  
-- Now schemaUser cannot see the contents of   
-- the collection.  
setuser 'schemaUser'  
GO  
SELECT XML_SCHEMA_NAMESPACE(N'dbo',N'MySC')  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="559e0-167">См. также:</span><span class="sxs-lookup"><span data-stu-id="559e0-167">See Also</span></span>  
 <span data-ttu-id="559e0-168">[Данные XML (SQL Server)](xml-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="559e0-168">[XML Data &#40;SQL Server&#41;](xml-data-sql-server.md) </span></span>  
 <span data-ttu-id="559e0-169">[Сравнение типизированного и нетипизированного XML](compare-typed-xml-to-untyped-xml.md) </span><span class="sxs-lookup"><span data-stu-id="559e0-169">[Compare Typed XML to Untyped XML](compare-typed-xml-to-untyped-xml.md) </span></span>  
 <span data-ttu-id="559e0-170">[Коллекции XML-схем (SQL Server)](xml-schema-collections-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="559e0-170">[XML Schema Collections &#40;SQL Server&#41;](xml-schema-collections-sql-server.md) </span></span>  
 [<span data-ttu-id="559e0-171">Требования и ограничения для коллекций схем XML на сервере</span><span class="sxs-lookup"><span data-stu-id="559e0-171">Requirements and Limitations for XML Schema Collections on the Server</span></span>](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
