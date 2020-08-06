---
title: Просмотр хранимой коллекции схем XML | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- schema collections [SQL Server], viewing
- XML schemas [SQL Server], viewing
- CREATE XML SCHEMA COLLECTION statement
- xml_schema_namespace function
- XML schema collections [SQL Server], viewing
- displaying XML schema collections
- viewing XML schema collections
ms.assetid: e38031af-22df-4cd9-a14e-e316b822f91b
author: rothja
ms.author: jroth
ms.openlocfilehash: 6383fb17183a991d2f83325044663cc9671e9442
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656262"
---
# <a name="view-a-stored-xml-schema-collection"></a><span data-ttu-id="b2268-102">Просмотр хранимой коллекции схем XML</span><span class="sxs-lookup"><span data-stu-id="b2268-102">View a Stored XML Schema Collection</span></span>
  <span data-ttu-id="b2268-103">После импорта коллекции XML-схем с помощью команды [Создать коллекцию схем XML](/sql/t-sql/statements/create-xml-schema-collection-transact-sql)компоненты схемы будут храниться в метаданных.</span><span class="sxs-lookup"><span data-stu-id="b2268-103">After you import an XML schema collection by using [CREATE XML SCHEMA COLLECTION](/sql/t-sql/statements/create-xml-schema-collection-transact-sql), the schema components are stored in the metadata.</span></span> <span data-ttu-id="b2268-104">Можно использовать внутреннюю функцию [xml_schema_namespace](/sql/t-sql/xml/xml-schema-namespace), чтобы повторно построить коллекцию XML-схем.</span><span class="sxs-lookup"><span data-stu-id="b2268-104">You can use the [xml_schema_namespace](/sql/t-sql/xml/xml-schema-namespace)intrinsic function to reconstruct the XML schema collection.</span></span> <span data-ttu-id="b2268-105">Эта функция возвращает экземпляр типа данных `xml`.</span><span class="sxs-lookup"><span data-stu-id="b2268-105">This function returns an `xml` data type instance.</span></span>  
  
 <span data-ttu-id="b2268-106">Например, следующий запрос извлекает коллекцию XML-схем (`ProductDescriptionSchemaCollection`) в реляционной схеме продукции в базе данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b2268-106">For example, the following query retrieves an XML schema collection (`ProductDescriptionSchemaCollection`) from the production relational schema in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
```  
SELECT xml_schema_namespace(N'Production',N'ProductDescriptionSchemaCollection')  
GO  
```  
  
 <span data-ttu-id="b2268-107">Если нужно увидеть только одну схему из коллекции, можно задать запрос XQuery для результата типа `xml`, возвращаемого функцией `xml_schema_namespace`.</span><span class="sxs-lookup"><span data-stu-id="b2268-107">If you want to see only one schema from the XML schema collection, you can specify XQuery against the `xml` type result that is returned by `xml_schema_namespace`.</span></span>  
  
```  
SELECT xml_schema_namespace(N'RelationalSchemaName',N'XmlSchemaCollectionName').query('  
/xs:schema[@targetNamespace="TargetNameSpace"]  
')  
GO  
```  
  
 <span data-ttu-id="b2268-108">Например, следующий запрос находит сведения об XML-схеме поддержки и гарантий на продукт в коллекции XML-схем `ProductDescriptionSchemaCollection` .</span><span class="sxs-lookup"><span data-stu-id="b2268-108">For example, the following query retrieves product warranty and maintenance XML schema information from the `ProductDescriptionSchemaCollection` XML schema collection.</span></span>  
  
```  
SELECT xml_schema_namespace(N'Production',N'ProductDescriptionSchemaCollection').query('  
/xs:schema[@targetNamespace="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelWarrAndMain"]  
')  
GO  
```  
  
 <span data-ttu-id="b2268-109">Также можно передать в качестве необязательного третьего параметра для `xml_schema_namespace` целевое пространство имен, чтобы получить из коллекции конкретную схему, как показано в следующем запросе:</span><span class="sxs-lookup"><span data-stu-id="b2268-109">You can also pass the optional target namespace as the third parameter to the `xml_schema_namespace` function to retrieve specific schema from the collection, as shown in the following query:</span></span>  
  
```  
SELECT xml_schema_namespace(N'Production',N'ProductDescriptionSchemaCollection', N'https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelWarrAndMain')  
GO  
```  
  
 <span data-ttu-id="b2268-110">Когда в базе данных создается коллекция XML-схем с помощью инструкции CREATE XML SCHEMA COLLECTION, она сохраняет компоненты схемы в метаданных.</span><span class="sxs-lookup"><span data-stu-id="b2268-110">When you create an XML schema collection by using CREATE XML SCHEMA COLLECTION in the database, the statement stores the schema components in the metadata.</span></span> <span data-ttu-id="b2268-111">Обратите внимание, что сохраняются только те компоненты схемы, которые понимает [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b2268-111">Note that only the schema components that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] understands are stored.</span></span> <span data-ttu-id="b2268-112">Любые комментарии, заметки или несоответствующие XSD-схеме атрибуты не сохраняются.</span><span class="sxs-lookup"><span data-stu-id="b2268-112">Any comments, annotations, or non-XSD attributes are not stored.</span></span> <span data-ttu-id="b2268-113">Следовательно, схема, повторно сконструированная посредством функции **xml_schema_namespace** , функционально эквивалентна первоначальной схеме, но не обязательно будет выглядеть так же.</span><span class="sxs-lookup"><span data-stu-id="b2268-113">Therefore, the schema reconstructed by **xml_schema_namespace** is functionally equivalent to the original schema, but it will not necessarily look the same.</span></span> <span data-ttu-id="b2268-114">Например, не будет тех же префиксов, которые были в первоначальной схеме.</span><span class="sxs-lookup"><span data-stu-id="b2268-114">For example, you will not see the same prefixes you had in the original schema.</span></span> <span data-ttu-id="b2268-115">Схема, возвращаемая функцией **xml_schema_namespace** , использует префикс **t** для целевого пространства имен и префиксы **ns1**, **ns2**и так далее для всех остальных.</span><span class="sxs-lookup"><span data-stu-id="b2268-115">The schema returned by **xml_schema_namespace** uses **t** as the prefix for the target namespace and **ns1**, **ns2**, and so on, for other namespaces.</span></span>  
  
 <span data-ttu-id="b2268-116">Если нужно сохранить точную копию XML-схем, следует сохранить схему в файл или в таблицу базы данных в столбец типа `xml`.</span><span class="sxs-lookup"><span data-stu-id="b2268-116">If you want to retain an identical copy of the XML schemas, you should save your XML schema in a file or in a database table in an `xml` type column.</span></span>  
  
 <span data-ttu-id="b2268-117">Представление каталога [sys.xml_schema_collections](/sql/relational-databases/system-catalog-views/sys-xml-schema-collections-transact-sql) также возвращает сведения о коллекциях XML-схем.</span><span class="sxs-lookup"><span data-stu-id="b2268-117">The [sys.xml_schema_collections](/sql/relational-databases/system-catalog-views/sys-xml-schema-collections-transact-sql) catalog view also returns information about XML schema collections.</span></span> <span data-ttu-id="b2268-118">Сюда входят, например сведения об имени коллекции, дате создания и владельце коллекции.</span><span class="sxs-lookup"><span data-stu-id="b2268-118">This information includes the name of the collection, the creation date, and the owner of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2268-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="b2268-119">See Also</span></span>  
 [<span data-ttu-id="b2268-120">Коллекции XML-схем (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b2268-120">XML Schema Collections &#40;SQL Server&#41;</span></span>](xml-schema-collections-sql-server.md)  
  
  
