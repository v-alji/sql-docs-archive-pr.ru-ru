---
title: Использование XML в вычисляемых столбцах | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- computed columns, XML
- XML [SQL Server], computed columns
ms.assetid: 1313b889-69b4-4018-9868-0496dd83bf44
author: rothja
ms.author: jroth
ms.openlocfilehash: 33a7549823dc3e4a23cecfa97d7345a6421cb1b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728086"
---
# <a name="use-xml-in-computed-columns"></a><span data-ttu-id="61dea-102">Использование XML в вычисляемых столбцах</span><span class="sxs-lookup"><span data-stu-id="61dea-102">Use XML in Computed Columns</span></span>
  <span data-ttu-id="61dea-103">Экземпляры XML могут встречаться в исходных данных для вычисляемого столбца и могут быть типом значений вычисляемого столбца.</span><span class="sxs-lookup"><span data-stu-id="61dea-103">XML instances can appear as a source for a computed column, or as a type of computed column.</span></span> <span data-ttu-id="61dea-104">Примеры в этом разделе демонстрируют использование XML в вычисляемых столбцах.</span><span class="sxs-lookup"><span data-stu-id="61dea-104">The examples in this topic show how to use XML with computed columns.</span></span>  
  
## <a name="creating-computed-columns-from-xml-columns"></a><span data-ttu-id="61dea-105">Создание вычисляемых столбцов из XML-столбцов</span><span class="sxs-lookup"><span data-stu-id="61dea-105">Creating Computed Columns from XML Columns</span></span>  
 <span data-ttu-id="61dea-106">В следующей инструкции `CREATE TABLE` столбец типа `xml` (`col2`) вычисляется из столбца `col1`:</span><span class="sxs-lookup"><span data-stu-id="61dea-106">In the following `CREATE TABLE` statement, an `xml` type column (`col2`) is computed from `col1`:</span></span>  
  
```  
CREATE TABLE T(col1 varchar(max), col2 AS CAST(col1 AS xml) )    
```  
  
 <span data-ttu-id="61dea-107">Тип данных `xml` может присутствовать в исходных данных при создании вычисляемого столбца, что демонстрирует следующая инструкция `CREATE TABLE` :</span><span class="sxs-lookup"><span data-stu-id="61dea-107">The `xml` data type can also appear as a source in creating a computed column, as shown in the following `CREATE TABLE` statement:</span></span>  
  
```  
CREATE TABLE T (col1 xml, col2 as cast(col1 as varchar(1000) ))   
```  
  
 <span data-ttu-id="61dea-108">Пример создания вычисляемого столбца, получающего значение из столбца типа `xml` , приводится ниже.</span><span class="sxs-lookup"><span data-stu-id="61dea-108">You can create a computed column by extracting a value from an `xml` type column as shown in the following example.</span></span> <span data-ttu-id="61dea-109">Поскольку методы типа данных `xml` нельзя прямо использовать при создании вычисляемых столбцов, в примере сначала определяется функция (`my_udf`), возвращающая значение для экземпляра XML.</span><span class="sxs-lookup"><span data-stu-id="61dea-109">Because the `xml` data type methods cannot be used directly in creating computed columns, the example first defines a function (`my_udf`) that returns a value from an XML instance.</span></span> <span data-ttu-id="61dea-110">Функция является интерфейсом к методу `value()` типа `xml` .</span><span class="sxs-lookup"><span data-stu-id="61dea-110">The function wraps the `value()` method of the `xml` type.</span></span> <span data-ttu-id="61dea-111">Имя функции затем указывается в инструкции `CREATE TABLE` в части, соответствующей вычисляемому столбцу.</span><span class="sxs-lookup"><span data-stu-id="61dea-111">The function name is then specified in the `CREATE TABLE` statement for the computed column.</span></span>  
  
```  
CREATE FUNCTION my_udf(@var xml) returns int  
AS BEGIN   
RETURN @var.value('(/ProductDescription/@ProductModelID)[1]' , 'int')  
END  
GO  
-- Use the function in CREATE TABLE.  
CREATE TABLE T (col1 xml, col2 as dbo.my_udf(col1) )  
GO  
-- Try adding a row.   
INSERT INTO T values('<ProductDescription ProductModelID="1" />')  
GO  
-- Verify results.  
SELECT col2, col1  
FROM T  
  
```  
  
 <span data-ttu-id="61dea-112">Как и в предыдущем примере, в этом примере определяется функция, возвращающая экземпляр типа `xml` для вычисляемого столбца.</span><span class="sxs-lookup"><span data-stu-id="61dea-112">As in the previous example, the following example defines a function to return an `xml` type instance for a computed column.</span></span> <span data-ttu-id="61dea-113">В функции вызывается метод `query()` типа данных `xml` , получающий значение из параметра типа `xml` .</span><span class="sxs-lookup"><span data-stu-id="61dea-113">Inside the function, the `query()` method of the `xml` data type retrieves a value from an `xml` type parameter.</span></span>  
  
```  
CREATE FUNCTION my_udf(@var xml)   
  RETURNS xml AS   
BEGIN   
   RETURN @var.query('ProductDescription/Features')  
END  
```  
  
 <span data-ttu-id="61dea-114">В следующей инструкции `CREATE TABLE` столбец `Col2` является вычисляемым столбцом, использующим XML-данные (элемент`<Features>` ), возвращаемые функцией:</span><span class="sxs-lookup"><span data-stu-id="61dea-114">In the following `CREATE TABLE` statement, `Col2` is a computed column that uses the XML data (`<Features>` element) that is returned by the function:</span></span>  
  
```  
CREATE TABLE T (Col1 xml, Col2 as dbo.my_udf(Col1) )  
-- Insert a row in table T.  
INSERT INTO T VALUES('  
<ProductDescription ProductModelID="1" >  
  <Features>  
    <Feature1>description</Feature1>  
    <Feature2>description</Feature2>  
  </Features>  
</ProductDescription>')  
-- Verify the results.  
SELECT *  
FROM T  
```  
  
### <a name="in-this-section"></a><span data-ttu-id="61dea-115">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="61dea-115">In This Section</span></span>  
  
|<span data-ttu-id="61dea-116">Раздел</span><span class="sxs-lookup"><span data-stu-id="61dea-116">Topic</span></span>|<span data-ttu-id="61dea-117">Описание</span><span class="sxs-lookup"><span data-stu-id="61dea-117">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="61dea-118">Продвижение часто используемых значений XML с помощью вычисляемых столбцов</span><span class="sxs-lookup"><span data-stu-id="61dea-118">Promote Frequently Used XML Values with Computed Columns</span></span>](promote-frequently-used-xml-values-with-computed-columns.md)|<span data-ttu-id="61dea-119">Описывает использование продвижения свойств в вычисляемых столбцах и таблицах свойств.</span><span class="sxs-lookup"><span data-stu-id="61dea-119">Describes how to use property promotion with computed columns and property tables.</span></span>|  
  
  
