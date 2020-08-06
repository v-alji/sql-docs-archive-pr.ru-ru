---
title: Сравнение запросов FOR XML и вложенных запросов FOR XML | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML query
- queries [XML in SQL Server], comparing query types
ms.assetid: 19225b4a-ee3f-47cf-8bcc-52699eeda32c
author: rothja
ms.author: jroth
ms.openlocfilehash: ca10060702d0c7e50f2be79310c55e177dca358d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751999"
---
# <a name="for-xml-query-compared-to-nested-for-xml-query"></a><span data-ttu-id="82569-102">Сравнение запросов FOR XML и вложенных запросов FOR XML</span><span class="sxs-lookup"><span data-stu-id="82569-102">FOR XML Query Compared to Nested FOR XML Query</span></span>
  <span data-ttu-id="82569-103">В этом разделе сравнивается одноуровневый запрос FOR XML с вложенным запросом FOR XML.</span><span class="sxs-lookup"><span data-stu-id="82569-103">This topic compares a single-level FOR XML query to a nested FOR XML query.</span></span> <span data-ttu-id="82569-104">Одним из преимуществ вложенных запросов FOR XML является то, что в них для результатов запроса можно задать сочетание XML-данных по атрибутивной или элементной модели.</span><span class="sxs-lookup"><span data-stu-id="82569-104">One of the benefits of using nested FOR XML queries is that you can specify a combination of attribute-centric and element-centric XML for query results.</span></span> <span data-ttu-id="82569-105">Это демонстрируется в примере.</span><span class="sxs-lookup"><span data-stu-id="82569-105">The example demonstrates this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="82569-106">Пример</span><span class="sxs-lookup"><span data-stu-id="82569-106">Example</span></span>  
 <span data-ttu-id="82569-107">Следующий запрос `SELECT` позволяет получить сведения о категории и подкатегории продукта в базе данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="82569-107">The following `SELECT` query retrieves product category and subcategory information in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="82569-108">В запросе нет вложенных запросов FOR XML.</span><span class="sxs-lookup"><span data-stu-id="82569-108">There is no nested FOR XML in the query.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT   ProductCategory.ProductCategoryID,   
         ProductCategory.Name as CategoryName,  
         ProductSubCategory.ProductSubCategoryID,   
         ProductSubCategory.Name  
FROM     Production.ProductCategory, Production.ProductSubCategory  
WHERE    ProductCategory.ProductCategoryID = ProductSubCategory.ProductCategoryID  
ORDER BY ProductCategoryID  
FOR XML AUTO, TYPE  
GO  
```  
  
 <span data-ttu-id="82569-109">Частичный результат:</span><span class="sxs-lookup"><span data-stu-id="82569-109">This is the partial result:</span></span>  
  
```  
<ProductCategory ProductCategoryID="1" CategoryName="Bike">  
  <ProductSubCategory ProductSubCategoryID="1" Name="Mountain Bike"/>  
  <ProductSubCategory ProductSubCategoryID="2" Name="Road Bike"/>  
  <ProductSubCategory ProductSubCategoryID="3" Name="Touring Bike"/>  
</ProductCategory>  
...  
```  
  
 <span data-ttu-id="82569-110">Если в запросе указана директива `ELEMENTS` , то результат будет представлен в элементной форме, как показано в следующем фрагменте результата:</span><span class="sxs-lookup"><span data-stu-id="82569-110">If you specify the `ELEMENTS` directive in the query, you receive an element-centric result, as shown in the following result fragment:</span></span>  
  
```  
<ProductCategory>  
  <ProductCategoryID>1</ProductCategoryID>  
  <CategoryName>Bike</CategoryName>  
  <ProductSubCategory>  
    <ProductSubCategoryID>1</ProductSubCategoryID>  
    <Name>Mountain Bike</Name>  
  </ProductSubCategory>  
  <ProductSubCategory>  
     ...  
  </ProductSubCategory>  
</ProductCategory>  
```  
  
 <span data-ttu-id="82569-111">Предположим, что нужно создать иерархию XML-данных, которая сочетает атрибутивную и элементную модели, как показано в следующем фрагменте:</span><span class="sxs-lookup"><span data-stu-id="82569-111">Next, assume that you want to generate an XML hierarchy that is a combination of attribute-centric and element-centric XML, as shown in the following fragment:</span></span>  
  
```  
<ProductCategory ProductCategoryID="1" CategoryName="Bike">  
  <ProductSubCategory>  
    <ProductSubCategoryID>1</ProductSubCategoryID>  
    <SubCategoryName>Mountain Bike</SubCategoryName></ProductSubCategory>  
  <ProductSubCategory>  
     ...  
  <ProductSubCategory>  
     ...  
</ProductCategory>  
```  
  
 <span data-ttu-id="82569-112">В этом фрагменте такие сведения о категории продукта, как идентификатор категории и имя категории, являются атрибутами.</span><span class="sxs-lookup"><span data-stu-id="82569-112">In the previous fragment, product category information such as category ID and category name are attributes.</span></span> <span data-ttu-id="82569-113">Однако сведения о подкатегории представлены с использованием элементов.</span><span class="sxs-lookup"><span data-stu-id="82569-113">However, the subcategory information is element-centric.</span></span> <span data-ttu-id="82569-114">Для конструирования элемента <`ProductCategory`> можно написать запрос `FOR XML`, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="82569-114">To construct the <`ProductCategory`> element, you can write a `FOR XML` query as shown in the following:</span></span>  
  
```  
SELECT ProductCategoryID, Name as CategoryName  
FROM Production.ProductCategory ProdCat  
ORDER BY ProductCategoryID  
FOR XML AUTO, TYPE  
```  
  
 <span data-ttu-id="82569-115">Результат:</span><span class="sxs-lookup"><span data-stu-id="82569-115">This is the result:</span></span>  
  
```  
< ProdCat ProductCategoryID="1" CategoryName="Bikes" />  
< ProdCat ProductCategoryID="2" CategoryName="Components" />  
< ProdCat ProductCategoryID="3" CategoryName="Clothing" />  
< ProdCat ProductCategoryID="4" CategoryName="Accessories" />  
```  
  
 <span data-ttu-id="82569-116">Для создания необходимых вложенных элементов <`ProductSubCategory`> необходимо после этого добавить вложенный запрос `FOR XML`, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="82569-116">To construct the nested <`ProductSubCategory`> elements in the XML you want, you then add a nested `FOR XML` query, as shown in the following:</span></span>  
  
```  
SELECT ProductCategoryID, Name as CategoryName,  
       (SELECT ProductSubCategoryID, Name SubCategoryName  
        FROM   Production.ProductSubCategory  
        WHERE ProductSubCategory.ProductCategoryID =   
              ProductCategory.ProductCategoryID  
        FOR XML AUTO, TYPE, ELEMENTS  
       )  
FROM Production.ProductCategory  
ORDER BY ProductCategoryID  
FOR XML AUTO, TYPE  
```  
  
 <span data-ttu-id="82569-117">При рассмотрении предыдущего запроса необходимо отметить следующее.</span><span class="sxs-lookup"><span data-stu-id="82569-117">Note the following in the previous query:</span></span>  
  
-   <span data-ttu-id="82569-118">Внутренний запрос `FOR XML` получает сведения о подкатегории продукта.</span><span class="sxs-lookup"><span data-stu-id="82569-118">The inner `FOR XML` query retrieves product subcategory information.</span></span> <span data-ttu-id="82569-119">Директива `ELEMENTS` добавляется во внутренний запрос `FOR XML` , создавая элементный XML, который добавляется к XML-данным, создаваемым внешним запросом.</span><span class="sxs-lookup"><span data-stu-id="82569-119">The `ELEMENTS` directive is added in the inner `FOR XML` to generate element-centric XML that is added to the XML generated by the outer query.</span></span> <span data-ttu-id="82569-120">По умолчанию внешний запрос создает XML-данные по атрибутивной модели.</span><span class="sxs-lookup"><span data-stu-id="82569-120">By default, the outer query generates attribute-centric XML.</span></span>  
  
-   <span data-ttu-id="82569-121">Во внутреннем запросе указана директива `TYPE` , поэтому результат имеет тип **xml** .</span><span class="sxs-lookup"><span data-stu-id="82569-121">In the inner query, the `TYPE` directive is specified so the result is of **xml** type.</span></span> <span data-ttu-id="82569-122">Если директива `TYPE` не указана, то возвращается результат типа `nvarchar(max)` и XML-данные возвращаются как сущности.</span><span class="sxs-lookup"><span data-stu-id="82569-122">If `TYPE` is not specified, the result is returned as `nvarchar(max)` type and the XML data is returned as entities.</span></span>  
  
-   <span data-ttu-id="82569-123">Внешний запрос также содержит директиву `TYPE` ,</span><span class="sxs-lookup"><span data-stu-id="82569-123">The outer query also specifies the `TYPE` directive.</span></span> <span data-ttu-id="82569-124">поэтому результат запроса возвращается клиенту как тип **xml** .</span><span class="sxs-lookup"><span data-stu-id="82569-124">Therefore, the result of this query is returned to the client as **xml** type.</span></span>  
  
 <span data-ttu-id="82569-125">Частичный результат:</span><span class="sxs-lookup"><span data-stu-id="82569-125">This is the partial result:</span></span>  
  
```  
<ProductCategory ProductCategoryID="1" CategoryName="Bike">  
  <ProductSubCategory>  
    <ProductSubCategoryID>1</ProductSubCategoryID>  
    <SubCategoryName>Mountain Bike</SubCategoryName></ProductSubCategory>  
  <ProductSubCategory>  
     ...  
  <ProductSubCategory>  
     ...  
</ProductCategory>  
```  
  
 <span data-ttu-id="82569-126">Следующий запрос представляет собой расширение предыдущего запроса.</span><span class="sxs-lookup"><span data-stu-id="82569-126">The following query is just an extension of the previous query.</span></span> <span data-ttu-id="82569-127">Он показывает полную иерархию продуктов в базе данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="82569-127">It shows the full product hierarchy in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="82569-128">Это включает следующие действия.</span><span class="sxs-lookup"><span data-stu-id="82569-128">This includes the following:</span></span>  
  
-   <span data-ttu-id="82569-129">Категории продукции</span><span class="sxs-lookup"><span data-stu-id="82569-129">Product categories</span></span>  
  
-   <span data-ttu-id="82569-130">Подкатегории продукции в каждой категории</span><span class="sxs-lookup"><span data-stu-id="82569-130">Product subcategories in each category</span></span>  
  
-   <span data-ttu-id="82569-131">Модели продуктов в каждой подкатегории</span><span class="sxs-lookup"><span data-stu-id="82569-131">Product models in each subcategory</span></span>  
  
-   <span data-ttu-id="82569-132">Продукты в каждой модели</span><span class="sxs-lookup"><span data-stu-id="82569-132">Products in each model</span></span>  
  
 <span data-ttu-id="82569-133">Следующий пример может быть полезен для понимания базы данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="82569-133">You might find the following query useful in understanding the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database:</span></span>  
  
```  
SELECT ProductCategoryID, Name as CategoryName,  
       (SELECT ProductSubCategoryID, Name SubCategoryName,  
               (SELECT ProductModel.ProductModelID,   
                       ProductModel.Name as ModelName,  
                       (SELECT ProductID, Name as ProductName, Color  
                        FROM   Production.Product  
                        WHERE  Product.ProductModelID =   
                               ProductModel.ProductModelID  
                        FOR XML AUTO, TYPE)  
                FROM   (SELECT distinct ProductModel.ProductModelID,   
                               ProductModel.Name  
                        FROM   Production.ProductModel,   
                               Production.Product  
                        WHERE  ProductModel.ProductModelID =   
                               Product.ProductModelID  
                        AND    Product.ProductSubCategoryID =   
                               ProductSubCategory.ProductSubCategoryID)   
                                  ProductModel  
                FOR XML AUTO, type  
               )  
        FROM Production.ProductSubCategory  
        WHERE ProductSubCategory.ProductCategoryID =   
              ProductCategory.ProductCategoryID  
        FOR XML AUTO, TYPE, ELEMENTS  
       )  
FROM Production.ProductCategory  
ORDER BY ProductCategoryID  
FOR XML AUTO, TYPE  
```  
  
 <span data-ttu-id="82569-134">Частичный результат:</span><span class="sxs-lookup"><span data-stu-id="82569-134">This is the partial result:</span></span>  
  
```  
<Production.ProductCategory ProductCategoryID="1" CategoryName="Bikes">  
  <Production.ProductSubCategory>  
    <ProductSubCategoryID>1</ProductSubCategoryID>  
    <SubCategoryName>Mountain Bikes</SubCategoryName>  
    <ProductModel ProductModelID="19" ModelName="Mountain-100">  
      <Production.Product ProductID="771"   
                ProductName="Mountain-100 Silver, 38" Color="Silver" />  
      <Production.Product ProductID="772"   
                ProductName="Mountain-100 Silver, 42" Color="Silver" />  
      <Production.Product ProductID="773"   
                ProductName="Mountain-100 Silver, 44" Color="Silver" />  
        ...  
    </ProductModel>  
     ...  
```  
  
 <span data-ttu-id="82569-135">Если удалить директиву `ELEMENTS` из вложенного запроса `FOR XML` , который создает подкатегории продуктов, то весь результат будет создан по атрибутивной модели.</span><span class="sxs-lookup"><span data-stu-id="82569-135">If you remove the `ELEMENTS` directive from the nested `FOR XML` query that generates product subcategories, the whole result is attribute-centric.</span></span> <span data-ttu-id="82569-136">Этот запрос можно составить без вложений.</span><span class="sxs-lookup"><span data-stu-id="82569-136">You can then write this query without nesting.</span></span> <span data-ttu-id="82569-137">Добавление директивы `ELEMENTS` приводит к созданию XML-документа как по атрибутивной, так и по элементной модели.</span><span class="sxs-lookup"><span data-stu-id="82569-137">The addition of `ELEMENTS` results in an XML that is partly attribute-centric and partly element-centric.</span></span> <span data-ttu-id="82569-138">Этот результат нельзя сформировать с помощью одноуровневого запроса FOR XML.</span><span class="sxs-lookup"><span data-stu-id="82569-138">This result cannot be generated by a single-level, FOR XML query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82569-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="82569-139">See Also</span></span>  
 [<span data-ttu-id="82569-140">Использование вложенных запросов FOR XML</span><span class="sxs-lookup"><span data-stu-id="82569-140">Use Nested FOR XML Queries</span></span>](use-nested-for-xml-queries.md)  
  
  
