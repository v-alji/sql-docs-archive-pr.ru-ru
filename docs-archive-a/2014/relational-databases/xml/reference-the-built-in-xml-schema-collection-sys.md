---
title: Создание ссылки на встроенную коллекцию схем XML (sys) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- sys XML schema collections [SQL Server]
- schema collections [SQL Server], predefined
- predefined XML schema collections [SQL Server]
- XML schema collections [SQL Server], predefined
- built-in XML schema collections [SQL Server]
ms.assetid: 1e118303-5df0-4ee4-bd8d-14ced7544144
author: rothja
ms.author: jroth
ms.openlocfilehash: 7fa30107e1746b33e3f9b8eb1cfa53d1f4d25fb8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730242"
---
# <a name="reference-the-built-in-xml-schema-collection-sys"></a><span data-ttu-id="1db6e-102">Создание ссылки на встроенную коллекцию XML-схем (sys)</span><span class="sxs-lookup"><span data-stu-id="1db6e-102">Reference the Built-in XML Schema Collection (sys)</span></span>
  <span data-ttu-id="1db6e-103">Любая созданная база данных содержит предопределенную коллекцию XML-схем **sys** в реляционной схеме **sys** .</span><span class="sxs-lookup"><span data-stu-id="1db6e-103">Every database you create has a predefined **sys** XML schema collection in the **sys** relational schema.</span></span> <span data-ttu-id="1db6e-104">Она содержит эти предопределенные схемы, к которым можно получить доступ из любой другой созданной пользователем коллекции XML-схем.</span><span class="sxs-lookup"><span data-stu-id="1db6e-104">It reserves these predefined schemas, and they can be accessed from any other user-created XML schema collection.</span></span> <span data-ttu-id="1db6e-105">В языке XQuery имеют значение префиксы, используемые для предопределенных схем.</span><span class="sxs-lookup"><span data-stu-id="1db6e-105">The prefixes used in these predefined schemas are meaningful in XQuery.</span></span> <span data-ttu-id="1db6e-106">К зарезервированным относится только префикс **xml** .</span><span class="sxs-lookup"><span data-stu-id="1db6e-106">Only **xml** is a reserved prefix.</span></span>  
  
```  
xml = http://www.w3.org/XML/1998/namespace  
xs = http://www.w3.org/2001/XMLSchema  
xsi = http://www.w3.org/2001/XMLSchema-instance  
fn = http://www.w3.org/2004/07/xpath-functions  
sqltypes = https://schemas.microsoft.com/sqlserver/2004/sqltypes  
xdt = http://www.w3.org/2004/07/xpath-datatypes  
(no prefix) = urn:schemas-microsoft-com:xml-sql  
(no prefix) = https://schemas.microsoft.com/sqlserver/2004/SOAP  
```  
  
 <span data-ttu-id="1db6e-107">Заметим, что пространство имен **sqltypes** содержит компоненты, на которые возможны ссылки из любой определенной пользователем коллекции схем XML.</span><span class="sxs-lookup"><span data-stu-id="1db6e-107">Note that the **sqltypes** namespace contains components that can be referenced from any user-created XML schema collection.</span></span> <span data-ttu-id="1db6e-108">Можно загрузить схему **sqltypes** с [сайта Майкрософт](https://go.microsoft.com/fwlink/?linkid=31850).</span><span class="sxs-lookup"><span data-stu-id="1db6e-108">You can download the **sqltypes** schema from this [Microsoft Web site](https://go.microsoft.com/fwlink/?linkid=31850).</span></span> <span data-ttu-id="1db6e-109">К встроенным компонентам относятся:</span><span class="sxs-lookup"><span data-stu-id="1db6e-109">The built-in components include the following:</span></span>  
  
-   <span data-ttu-id="1db6e-110">типы XSD;</span><span class="sxs-lookup"><span data-stu-id="1db6e-110">XSD types</span></span>  
  
-   <span data-ttu-id="1db6e-111">XML-атрибуты **lang**, **base**и **space**;</span><span class="sxs-lookup"><span data-stu-id="1db6e-111">XML attributes **lang**, **base**, and **space**</span></span>  
  
-   <span data-ttu-id="1db6e-112">компоненты пространства имен **sqltypes** .</span><span class="sxs-lookup"><span data-stu-id="1db6e-112">Components of the **sqltypes** namespace</span></span>  
  
 <span data-ttu-id="1db6e-113">Следующий запрос возвращает встроенные компоненты, на которые возможны ссылки из созданной пользователем коллекции XML-схем.</span><span class="sxs-lookup"><span data-stu-id="1db6e-113">The following query returns built-in components that can be referenced from a user-created XML schema collection:</span></span>  
  
```  
SELECT C.name, N.name, C.symbol_space_desc from sys.xml_schema_components C join sys.xml_schema_namespaces N  
on ((C.xml_namespace_id = N.xml_namespace_id) AND (C.xml_collection_id = N.xml_collection_id))  
join sys.xml_schema_collections SC  
on SC.xml_collection_id = C.xml_collection_id  
where ((C.xml_collection_id = 1) AND (C.name is not null) AND (C.scoping_xml_component_id is null)   
AND (SC.schema_id = 4))  
GO  
```  
  
 <span data-ttu-id="1db6e-114">В следующем примере показано, как заданы ссылки на эти компоненты в пользовательской схеме.</span><span class="sxs-lookup"><span data-stu-id="1db6e-114">The following example shows how these components are referenced in a user schema.</span></span> <span data-ttu-id="1db6e-115">`CREATE XML SCHEMA COLLECTION` создает коллекцию схем XML, которая ссылается на тип `varchar` , определенный в пространстве имен `sqltypes` .</span><span class="sxs-lookup"><span data-stu-id="1db6e-115">`CREATE XML SCHEMA COLLECTION` creates an XML schema collection that references the `varchar` type defined in the `sqltypes` namespace.</span></span> <span data-ttu-id="1db6e-116">В примере также производится ссылка на атрибут `lang` , определенный в пространстве имен `xml` .</span><span class="sxs-lookup"><span data-stu-id="1db6e-116">The example also references the `lang` attribute that is defined in the `xml` namespace.</span></span>  
  
```  
CREATE XML SCHEMA COLLECTION SC AS '  
<schema   
   xmlns="http://www.w3.org/2001/XMLSchema"   
   targetNamespace="myNS"  
   xmlns:ns="myNS"  
   xmlns:s="https://schemas.microsoft.com/sqlserver/2004/sqltypes" >   
   <import namespace="http://www.w3.org/XML/1998/namespace"/>  
   <import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes"/>  
   <element name="root">  
      <complexType>  
          <sequence>  
             <element name="a" type="string"/>  
             <element name="b" type="string"/>  
             <!-- varchar type is defined in the sys.sys collection and   
                  can be referenced in any user-defined schema -->  
             <element name="c" type="s:varchar"/>  
          </sequence>  
          <attribute name="att" type="int"/>  
          <!-- xml:lang attribute is defined in the sys.sys collection   
               and can be referenced in any user-defined schema -->  
          <attribute ref="xml:lang"/>  
      </complexType>  
    </element>  
 </schema>'  
GO  
 -- Cleanup  
DROP xml schema collection SC   
GO  
```  
  
 <span data-ttu-id="1db6e-117">Обратите внимание на следующее.</span><span class="sxs-lookup"><span data-stu-id="1db6e-117">You should note the following:</span></span>  
  
-   <span data-ttu-id="1db6e-118">Нельзя модифицировать XML-схемы с данными пространствами имен в пользовательской коллекции XML-схем.</span><span class="sxs-lookup"><span data-stu-id="1db6e-118">You cannot modify XML schemas with these namespaces in any user-defined XML schema collection.</span></span> <span data-ttu-id="1db6e-119">Например, следующая коллекция XML-схем завершается неудачно, так как она добавляет компонент в защищенное пространство имен `sqltypes` :</span><span class="sxs-lookup"><span data-stu-id="1db6e-119">For example, the following XML schema collection fails, because it is adding a component to the `sqltypes` protected namespace:</span></span>  
  
    ```  
    CREATE XML SCHEMA COLLECTION SC AS '  
    <schema xmlns="http://www.w3.org/2001/XMLSchema"   
    targetNamespace    
        ="https://schemas.microsoft.com/sqlserver/2004/sqltypes" >   
          <element name="root" type="string"/>  
    </schema>'  
    GO  
    ```  
  
-   <span data-ttu-id="1db6e-120">Нельзя использовать коллекцию XML-схем `sys` для ввода столбцов, переменных или параметров `xml` .</span><span class="sxs-lookup"><span data-stu-id="1db6e-120">You cannot use the `sys` XML schema collection to type `xml` columns, variables, or parameters.</span></span> <span data-ttu-id="1db6e-121">Например, следующий код возвращает ошибку:</span><span class="sxs-lookup"><span data-stu-id="1db6e-121">For example, the following code returns an error:</span></span>  
  
    ```  
    DECLARE @x xml (sys.sys)  
    ```  
  
-   <span data-ttu-id="1db6e-122">Сериализация встроенных схем не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="1db6e-122">Serialization of these built-in schemas is not supported.</span></span> <span data-ttu-id="1db6e-123">Например, следующий код возвращает ошибку:</span><span class="sxs-lookup"><span data-stu-id="1db6e-123">For example, the following code returns an error:</span></span>  
  
    ```  
    SELECT XML_SCHEMA_NAMESPACE(N'sys',N'sys')  
    GO  
    ```  
  
 <span data-ttu-id="1db6e-124">Следующий код является еще одним примером, в котором создается коллекция XML-схем, использующая тип данных `varchar`, определенный в пространстве имен `sqltypes`:</span><span class="sxs-lookup"><span data-stu-id="1db6e-124">The following code is another example in which you create an XML schema collection that uses the `varchar` type defined in the `sqltypes` namespace:</span></span>  
  
```  
CREATE XML SCHEMA COLLECTION SC AS '  
<schema xmlns="http://www.w3.org/2001/XMLSchema"   
        targetNamespace="myNS" xmlns:ns="myNS"  
        xmlns:s="https://schemas.microsoft.com/sqlserver/2004/sqltypes">  
   <import     
     namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes"/>  
      <simpleType name="myType">  
            <restriction base="s:varchar">  
                  <maxLength value="20"/>  
            </restriction>  
      </simpleType>  
      <element name="root" type="ns:myType"/>  
</schema>'  
go  
```  
  
 <span data-ttu-id="1db6e-125">Как показано ниже, можно создать переменную `XML`, обладающую типом данных, присвоить ей экземпляр XML и проверить, является ли значение типа элемента <`root`> типом данных `varchar`.</span><span class="sxs-lookup"><span data-stu-id="1db6e-125">As shown in the following, you can create a typed `XML` variable, assign an XML instance to it, and verify that the value of the <`root`> element type is a `varchar` type.</span></span>  
  
```  
DECLARE @var XML(SC)  
SET @var = '<root xmlns="myNS">My data</root>'  
SELECT @var.query('declare namespace sqltypes = "https://schemas.microsoft.com/sqlserver/2004/sqltypes";  
declare namespace ns="myNS";   
data(/ns:root[1]) instance of sqltypes:varchar?')  
GO  
```  
  
 <span data-ttu-id="1db6e-126">Выражение `instance of sqltypes:varchar?` возвращает значение TRUE, потому что значение элемента <`root`> имеет тип данных, производный от типа данных **varchar** в соответствии со схемой, связанной с переменной `@var`.</span><span class="sxs-lookup"><span data-stu-id="1db6e-126">The `instance of sqltypes:varchar?` expression returns TRUE, because the <`root`> element value is of a type derived from **varchar** according to the schema that is associated with the `@var` variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1db6e-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="1db6e-127">See Also</span></span>  
 [<span data-ttu-id="1db6e-128">Коллекции XML-схем (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1db6e-128">XML Schema Collections &#40;SQL Server&#41;</span></span>](xml-schema-collections-sql-server.md)  
  
  
