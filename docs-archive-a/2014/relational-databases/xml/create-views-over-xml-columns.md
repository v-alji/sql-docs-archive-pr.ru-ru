---
title: Создание представлений для столбцов XML | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- views [XML in SQL Server]
ms.assetid: eb5f0439-1f69-49c2-8759-e59bda1633b7
author: rothja
ms.author: jroth
ms.openlocfilehash: bf06f1107cbf4875eb63fe6747775b5c5c04810c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738078"
---
# <a name="create-views-over-xml-columns"></a><span data-ttu-id="db7a6-102">Создание представления для XML-столбцов</span><span class="sxs-lookup"><span data-stu-id="db7a6-102">Create Views over XML Columns</span></span>
  <span data-ttu-id="db7a6-103">Чтобы создавать представления, можно использовать столбец типа `xml`.</span><span class="sxs-lookup"><span data-stu-id="db7a6-103">You can use an `xml` type column to create views.</span></span> <span data-ttu-id="db7a6-104">В следующем примере создается представление, в котором для получения значения из столбца типа `xml` используется метод `value()` типа данных `xml`.</span><span class="sxs-lookup"><span data-stu-id="db7a6-104">The following example creates a view in which the value from an `xml` type column is retrieved using the `value()` method of the `xml` data type.</span></span>  
  
```  
-- Create the table.  
CREATE TABLE T (  
    ProductID          int primary key,   
    CatalogDescription xml)  
GO  
-- Insert sample data.  
INSERT INTO T values(1,'<ProductDescription ProductID="1" ProductName="SomeName" />')  
GO  
-- Create view (note the value() method used to retrieve ProductName   
-- attribute value from the XML).  
CREATE VIEW MyView AS   
  SELECT ProductID,  
         CatalogDescription.value('(/ProductDescription/@ProductName)[1]', 'varchar(40)') AS PName  
  FROM T  
GO   
```  
  
 <span data-ttu-id="db7a6-105">Выполните следующий запрос к представлению:</span><span class="sxs-lookup"><span data-stu-id="db7a6-105">Execute the following query against the view:</span></span>  
  
```  
SELECT *   
FROM   MyView  
```  
  
 <span data-ttu-id="db7a6-106">Результат:</span><span class="sxs-lookup"><span data-stu-id="db7a6-106">This is the result:</span></span>  
  
```  
ProductID   PName        
----------- ------------  
1           SomeName   
```  
  
 <span data-ttu-id="db7a6-107">Обратите внимание на следующие аспекты использования типа данных `xml` при создании представлений:</span><span class="sxs-lookup"><span data-stu-id="db7a6-107">Note the following points about using the `xml` data type to create views:</span></span>  
  
-   <span data-ttu-id="db7a6-108">тип данных xml может быть создан в материализованном представлении.</span><span class="sxs-lookup"><span data-stu-id="db7a6-108">The xml data type can be created in a materialized view.</span></span> <span data-ttu-id="db7a6-109">Материализованное представление не может быть основано на методе типа данных xml.</span><span class="sxs-lookup"><span data-stu-id="db7a6-109">The materialized view cannot be based on an xml data type method.</span></span> <span data-ttu-id="db7a6-110">Однако они могут быть приведены к коллекции XML-схем, отличающейся от столбца типа xml базовой таблицы;</span><span class="sxs-lookup"><span data-stu-id="db7a6-110">However, it can be cast to an XML schema collection that is different from the xml type column in the base table.</span></span>  
  
-   <span data-ttu-id="db7a6-111">тип данных `xml` нельзя использовать в распределенных секционированных представлениях;</span><span class="sxs-lookup"><span data-stu-id="db7a6-111">The `xml` data type cannot be used in Distributed Partitioned Views.</span></span>  
  
-   <span data-ttu-id="db7a6-112">выполнение предикатов SQL по отношению к представлению не будет включено в выражения XQuery определения этого представления;</span><span class="sxs-lookup"><span data-stu-id="db7a6-112">SQL predicates running against the view will not be pushed into the XQuery of the view definition.</span></span>  
  
-   <span data-ttu-id="db7a6-113">обновление методов типа данных xml в представлениях невозможно.</span><span class="sxs-lookup"><span data-stu-id="db7a6-113">XML data type methods in a view are not updatable.</span></span>  
  
  
