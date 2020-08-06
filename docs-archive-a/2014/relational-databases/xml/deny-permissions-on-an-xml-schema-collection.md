---
title: Запрет разрешения на коллекцию схем XML | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- denying permissions [SQL Server], XML server collections
ms.assetid: e2b300b0-e734-4c43-a4da-c78e6e5d4fba
author: rothja
ms.author: jroth
ms.openlocfilehash: 0791a9bd9c7f6b323886a38bed27bea84940770d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654945"
---
# <a name="deny-permissions-on-an-xml-schema-collection"></a><span data-ttu-id="21d08-102">Запрещает разрешения на коллекцию схем XML.</span><span class="sxs-lookup"><span data-stu-id="21d08-102">Deny Permissions on an XML Schema Collection</span></span>
  <span data-ttu-id="21d08-103">Можно запретить разрешение либо на создание новой коллекции XML-схем, либо на использование уже существующей.</span><span class="sxs-lookup"><span data-stu-id="21d08-103">Permission can be denied to either create a new XML schema collection or use an existing one.</span></span>  
  
## <a name="denying-permission-to-create-an-xml-schema-collection"></a><span data-ttu-id="21d08-104">Запрет разрешений на создание коллекции XML-схем</span><span class="sxs-lookup"><span data-stu-id="21d08-104">Denying Permission to Create an XML Schema Collection</span></span>  
 <span data-ttu-id="21d08-105">Запретить разрешение на создание коллекции XML-схем можно одним из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="21d08-105">You can deny permission to create an XML schema collection in the following ways:</span></span>  
  
-   <span data-ttu-id="21d08-106">Запретите разрешение ALTER на реляционную схему.</span><span class="sxs-lookup"><span data-stu-id="21d08-106">Deny ALTER permission on the relational schema.</span></span>  
  
-   <span data-ttu-id="21d08-107">Запретите разрешение CONTROL на реляционную схему, чтобы запретить все разрешения на реляционную схему и на все содержащиеся в ней объекты.</span><span class="sxs-lookup"><span data-stu-id="21d08-107">Deny CONTROL on the relational schema to deny all permissions on the relational schema and on all the contained objects.</span></span>  
  
-   <span data-ttu-id="21d08-108">Запретите разрешение ALTER ANY SCHEMA на базу данных.</span><span class="sxs-lookup"><span data-stu-id="21d08-108">Deny ALTER ANY SCHEMA on the database.</span></span> <span data-ttu-id="21d08-109">В этом случае участник не может создать коллекцию XML-схемы в базе данных.</span><span class="sxs-lookup"><span data-stu-id="21d08-109">In this case, the principal cannot create an XML schema collection anywhere in the database.</span></span> <span data-ttu-id="21d08-110">Обратите внимание на то, что при запрете разрешений ALTER или CONTROL на базу данных происходит запрет всех разрешений на все объекты базы данных.</span><span class="sxs-lookup"><span data-stu-id="21d08-110">Note also that denying ALTER or CONTROL permission on the database denies all permissions on all objects in the database.</span></span>  
  
## <a name="denying-permissions-on-an-xml-schema-collection-object"></a><span data-ttu-id="21d08-111">Запрет разрешений на объект коллекции XML-схем</span><span class="sxs-lookup"><span data-stu-id="21d08-111">Denying Permissions on an XML Schema Collection Object</span></span>  
 <span data-ttu-id="21d08-112">Далее приводятся разрешения, которые могут быть запрещены на существующие коллекции XML-схем, а также последствия таких запретов.</span><span class="sxs-lookup"><span data-stu-id="21d08-112">Following are the permission that can be denied on an existing XML schema collection and the results:</span></span>  
  
-   <span data-ttu-id="21d08-113">Запрет разрешения ALTER запрещает участнику изменять содержание коллекции XML-схем.</span><span class="sxs-lookup"><span data-stu-id="21d08-113">Denying the ALTER permission denies the principal the ability to modify the contents of the XML schema collection.</span></span>  
  
-   <span data-ttu-id="21d08-114">Запрет разрешения CONTROL запрещает участнику выполнять любые действия с коллекцией XML-схем.</span><span class="sxs-lookup"><span data-stu-id="21d08-114">Denying the CONTROL permission denies the principal the ability to perform any operation on the XML schema collection.</span></span>  
  
-   <span data-ttu-id="21d08-115">Запрет разрешения REFERENCES запрещает участнику вводить или ограничивать параметры и столбцы xml ввода при помощи коллекции XML-схем.</span><span class="sxs-lookup"><span data-stu-id="21d08-115">Denying the REFERENCES permission denies the principal the ability to type or constrain xml type columns and parameters using the XML schema collection.</span></span> <span data-ttu-id="21d08-116">При этом участнику запрещается ссылаться на эту коллекцию XML-схем из других коллекций XML-схем.</span><span class="sxs-lookup"><span data-stu-id="21d08-116">It also denies the principal the ability to refer to this XML schema collection from other XML schema collections.</span></span>  
  
-   <span data-ttu-id="21d08-117">Запрет разрешения VIEW DEFINITION запрещает участнику просматривать содержание коллекции XML-схем.</span><span class="sxs-lookup"><span data-stu-id="21d08-117">Denying the VIEW DEFINITION permission denies the principal the ability to view the contents of an XML schema collection.</span></span>  
  
-   <span data-ttu-id="21d08-118">Запрет разрешения EXECUTE запрещает участнику вставлять или обновлять значения в столбцах, переменные и параметры, типизированные или ограниченные коллекцией XML-схем.</span><span class="sxs-lookup"><span data-stu-id="21d08-118">Denying the EXECUTE permission denies the principal the ability to insert or update the values in columns, variables, and parameters that are typed or constrained by the XML schema collection.</span></span> <span data-ttu-id="21d08-119">При этом участнику запрещается запрашивать значения в тех же столбцах типа xml и xml-переменных.</span><span class="sxs-lookup"><span data-stu-id="21d08-119">It also denies the principal the ability to query the values in those same xml type columns and variables.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="21d08-120">Примеры</span><span class="sxs-lookup"><span data-stu-id="21d08-120">Examples</span></span>  
 <span data-ttu-id="21d08-121">В следующих примерах показан принцип работы разрешений на XML-схемы.</span><span class="sxs-lookup"><span data-stu-id="21d08-121">The scenarios in the following examples show how XML schema permissions work.</span></span> <span data-ttu-id="21d08-122">В каждом примере создается соответствующая тестовая база данных, реляционные схемы и имена входа.</span><span class="sxs-lookup"><span data-stu-id="21d08-122">Each example creates the necessary test database, relational schemas, and logins.</span></span> <span data-ttu-id="21d08-123">Этим именам входа предоставляются необходимые разрешения на коллекции XML-схем.</span><span class="sxs-lookup"><span data-stu-id="21d08-123">These logins are granted the necessary XML schema collection permissions.</span></span> <span data-ttu-id="21d08-124">После завершения работы каждый пример выполняет необходимые действия по очистке.</span><span class="sxs-lookup"><span data-stu-id="21d08-124">Each example does the necessary cleanup at the end.</span></span>  
  
### <a name="a-preventing-a-user-from-creating-an-xml-schema-collection"></a><span data-ttu-id="21d08-125">A.</span><span class="sxs-lookup"><span data-stu-id="21d08-125">A.</span></span> <span data-ttu-id="21d08-126">Запрет пользователю создавать коллекции схем XML</span><span class="sxs-lookup"><span data-stu-id="21d08-126">Preventing a user from creating an XML schema collection</span></span>  
 <span data-ttu-id="21d08-127">Одним из способов запретить пользователю создавать коллекции XML-схем является запрет разрешения ALTER на реляционную схему.</span><span class="sxs-lookup"><span data-stu-id="21d08-127">One of the ways to prevent a user from creating an XML schema collection is by denying the ALTER permission on a relational schema.</span></span> <span data-ttu-id="21d08-128">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="21d08-128">This is shown in the following example.</span></span>  
  
 <span data-ttu-id="21d08-129">В данном примере создается пользователь `TestLogin1`и база данных.</span><span class="sxs-lookup"><span data-stu-id="21d08-129">The example creates a user, `TestLogin1`, and a database.</span></span> <span data-ttu-id="21d08-130">Кроме того, в дополнение к схеме `dbo` в базе данных создается реляционная схема.</span><span class="sxs-lookup"><span data-stu-id="21d08-130">It also creates a relational schema, in addition to the `dbo` schema, in the database.</span></span> <span data-ttu-id="21d08-131">Поначалу разрешение `CREATE XML SCHEMA` позволяет пользователю создавать коллекцию схем в любом месте базы данных.</span><span class="sxs-lookup"><span data-stu-id="21d08-131">Initially, the `CREATE XML SCHEMA` permission allows the user to create a schema collection anywhere in the database.</span></span> <span data-ttu-id="21d08-132">В примере запрещается разрешение `ALTER` для пользователя на одну из реляционных схем.</span><span class="sxs-lookup"><span data-stu-id="21d08-132">The example then denies `ALTER` permission to the user on one of the relational schemas.</span></span> <span data-ttu-id="21d08-133">При этом пользователю запрещается создавать коллекции XML-схем в этой реляционной схеме.</span><span class="sxs-lookup"><span data-stu-id="21d08-133">This prevents the user from creating an XML schema collection in that relational schema.</span></span>  
  
```  
CREATE LOGIN TestLogin1 WITH password='SQLSvrPwd1'  
GO  
CREATE DATABASE SampleDBForSchemaPermissions  
GO  
USE SampleDBForSchemaPermissions  
GO  
-- Create another relational schema in the database.  
CREATE SCHEMA myOtherDBSchema  
GO  
CREATE USER TestLogin1  
GO  
-- For TestLogin1 to create/import XML schema collection, following  
-- permission needed.  
-- Database-level permissions  
GRANT CREATE XML SCHEMA COLLECTION TO TestLogin1  
GO  
GRANT ALTER ANY SCHEMA TO TestLogin1  
GO  
-- Now TestLogin1 can import an XML schema collection.  
SETUSER 'TestLogin1'  
GO  
CREATE XML SCHEMA COLLECTION myOtherDBSchema.myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
GO  
DROP XML SCHEMA COLLECTION myOtherDBSchema.myTestSchemaCollection  
GO  
-- Now deny permission from TestLogin1 to alter myOtherDBSchema.  
setuser  
GO  
DENY ALTER ON SCHEMA::myOtherDBSchema TO TestLogin1  
GO  
-- Now TestLogin1 cannot create xml schema collection.  
SETUSER 'TestLogin1'  
GO  
CREATE XML SCHEMA COLLECTION myOtherDBSchema.myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
<xsd:element name="telephone" type="xsd:string" />  
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
  
### <a name="b-denying-permissions-on-an-xml-schema-collection"></a><span data-ttu-id="21d08-134">Б.</span><span class="sxs-lookup"><span data-stu-id="21d08-134">B.</span></span> <span data-ttu-id="21d08-135">Запрет разрешений на коллекцию схем XML</span><span class="sxs-lookup"><span data-stu-id="21d08-135">Denying permissions on an XML schema collection</span></span>  
 <span data-ttu-id="21d08-136">В следующем примере показано, как запретить разрешение для имени входа на существующую коллекцию XML-схем.</span><span class="sxs-lookup"><span data-stu-id="21d08-136">The following example shows how a specific permission on an existing XML schema collection can be denied to a login.</span></span> <span data-ttu-id="21d08-137">В этом примере запрещается разрешение REFERENCES для тестового имени входа на существующую коллекцию XML-схем.</span><span class="sxs-lookup"><span data-stu-id="21d08-137">In this example, a test login is denied REFERENCES permission on an existing XML schema collection.</span></span>  
  
 <span data-ttu-id="21d08-138">В данном примере создается пользователь `TestLogin1`и база данных.</span><span class="sxs-lookup"><span data-stu-id="21d08-138">The example creates a user, `TestLogin1`, and a database.</span></span> <span data-ttu-id="21d08-139">Кроме того, в дополнение к схеме `dbo` в базе данных создается реляционная схема.</span><span class="sxs-lookup"><span data-stu-id="21d08-139">It also creates a relational schema, in addition to the `dbo` schema, in the database.</span></span> <span data-ttu-id="21d08-140">Поначалу разрешение `CREATE XML SCHEMA` позволяет пользователю создавать коллекцию схем в любом месте базы данных.</span><span class="sxs-lookup"><span data-stu-id="21d08-140">Initially, the `CREATE XML SCHEMA` permission allows the user to create a schema collection anywhere in the database.</span></span>  
  
 <span data-ttu-id="21d08-141">Разрешение `REFERENCES` на коллекцию XML-схем позволяет учетной записи `TestLogin1` использовать схему при создании типизированного столбца `xml` в таблице.</span><span class="sxs-lookup"><span data-stu-id="21d08-141">The `REFERENCES` permission on the XML schema collection lets `TestLogin1` use the schema in creating a typed `xml` column in a table.</span></span> <span data-ttu-id="21d08-142">Если разрешение `REFERENCES` коллекции XML-схем запрещено, то пользователь `TestLogin1` не может использовать ее.</span><span class="sxs-lookup"><span data-stu-id="21d08-142">If the `REFERENCES` permission on the XML schema collection is denied, it prevents the `TestLogin1` from using the XML schema collection.</span></span>  
  
```  
CREATE LOGIN TestLogin1 WITH password='SQLSvrPwd1'  
GO  
CREATE DATABASE SampleDBForSchemaPermissions  
GO  
USE SampleDBForSchemaPermissions  
GO  
-- Create another relational schema in the database.  
CREATE SCHEMA myOtherDBSchema  
GO  
CREATE USER TestLogin1  
GO  
-- For TestLogin1 to create/import XML schema collection, the following  
-- permission is required.  
-- Database-level permissions  
GRANT CREATE XML SCHEMA COLLECTION TO TestLogin1  
GO  
GRANT ALTER ANY SCHEMA TO TestLogin1  
GO  
-- Now TestLogin1 can import an XML schema collection.  
SETUSER 'TestLogin1'  
GO  
CREATE XML SCHEMA COLLECTION myOtherDBSchema.myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
GO  
-- Grant permission to TestLogin1 to create a table and reference the XML schema collection.  
SETUSER  
GO  
GRANT CREATE TABLE TO TestLogin1  
GO  
-- The user also needs REFERENCES permission to use the XML schema collection  
-- to create a typed XML column (REFERENCES permission on the schema   
-- collection is not needed).  
GRANT REFERENCES ON XML SCHEMA COLLECTION::myOtherDBSchema.myTestSchemaCollection   
TO TestLogin1  
GO  
  
--TestLogin1 can use the schema.  
CREATE TABLE T(i int, x xml (myOtherDBSchema.myTestSchemaCollection))  
GO  
-- Drop the table.  
DROP TABLE T  
GO  
-- Now deny REFERENCES permission to TestLogin1 on the schema created previously.  
SETUSER  
GO  
DENY REFERENCES ON XML SCHEMA COLLECTION::myOtherDBSchema.myTestSchemaCollection TO TestLogin1  
  
GO  
-- Now TestLogin1 cannot create xml schema collection  
SETUSER 'TestLogin1'  
GO  
-- Following statement fails. TestLogin1 does not have REFERENCES   
-- permission on the XML schema collection.  
CREATE TABLE T(i int, x xml (myOtherDBSchema.myTestSchemaCollection))  
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
  
## <a name="see-also"></a><span data-ttu-id="21d08-143">См. также:</span><span class="sxs-lookup"><span data-stu-id="21d08-143">See Also</span></span>  
 <span data-ttu-id="21d08-144">[Сравнение типизированного и нетипизированного XML](compare-typed-xml-to-untyped-xml.md) </span><span class="sxs-lookup"><span data-stu-id="21d08-144">[Compare Typed XML to Untyped XML](compare-typed-xml-to-untyped-xml.md) </span></span>  
 <span data-ttu-id="21d08-145">[Коллекции XML-схем (SQL Server)](xml-schema-collections-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="21d08-145">[XML Schema Collections &#40;SQL Server&#41;](xml-schema-collections-sql-server.md) </span></span>  
 <span data-ttu-id="21d08-146">[Требования и ограничения для коллекций XML-схем на сервере](requirements-and-limitations-for-xml-schema-collections-on-the-server.md) </span><span class="sxs-lookup"><span data-stu-id="21d08-146">[Requirements and Limitations for XML Schema Collections on the Server](requirements-and-limitations-for-xml-schema-collections-on-the-server.md) </span></span>  
 <span data-ttu-id="21d08-147">[DENY, предоставление разрешений на объект (Transact-SQL)](/sql/t-sql/statements/deny-object-permissions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="21d08-147">[DENY Object Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/deny-object-permissions-transact-sql) </span></span>  
 <span data-ttu-id="21d08-148">[GRANT, предоставление разрешений на объект (Transact-SQL)](/sql/t-sql/statements/grant-object-permissions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="21d08-148">[GRANT Object Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql) </span></span>  
 [<span data-ttu-id="21d08-149">Данные XML (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="21d08-149">XML Data &#40;SQL Server&#41;</span></span>](xml-data-sql-server.md)  
  
  
