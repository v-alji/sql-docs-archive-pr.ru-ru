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
# <a name="create-views-over-xml-columns"></a>Создание представления для XML-столбцов
  Чтобы создавать представления, можно использовать столбец типа `xml`. В следующем примере создается представление, в котором для получения значения из столбца типа `xml` используется метод `value()` типа данных `xml`.  
  
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
  
 Выполните следующий запрос к представлению:  
  
```  
SELECT *   
FROM   MyView  
```  
  
 Результат:  
  
```  
ProductID   PName        
----------- ------------  
1           SomeName   
```  
  
 Обратите внимание на следующие аспекты использования типа данных `xml` при создании представлений:  
  
-   тип данных xml может быть создан в материализованном представлении. Материализованное представление не может быть основано на методе типа данных xml. Однако они могут быть приведены к коллекции XML-схем, отличающейся от столбца типа xml базовой таблицы;  
  
-   тип данных `xml` нельзя использовать в распределенных секционированных представлениях;  
  
-   выполнение предикатов SQL по отношению к представлению не будет включено в выражения XQuery определения этого представления;  
  
-   обновление методов типа данных xml в представлениях невозможно.  
  
  
