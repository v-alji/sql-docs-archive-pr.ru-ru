---
title: Пример Указание директивы XMLTEXT | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XMLTEXT directive
ms.assetid: e78008ec-51e8-4fd1-b86f-1058a781de17
author: rothja
ms.author: jroth
ms.openlocfilehash: d14299ad3e989c6600434b857a650fbbddd7a590
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667605"
---
# <a name="example-specifying-the-xmltext-directive"></a><span data-ttu-id="2c1cb-102">Пример Определение директивы XMLTEXT</span><span class="sxs-lookup"><span data-stu-id="2c1cb-102">Example: Specifying the XMLTEXT Directive</span></span>
  <span data-ttu-id="2c1cb-103">Этот пример иллюстрирует, как при помощи директивы `XMLTEXT` в инструкции `SELECT`, использующей режим EXPLICIT, осуществляется обращение к данным столбца Overflow.</span><span class="sxs-lookup"><span data-stu-id="2c1cb-103">This example illustrates how data in the overflow column is addressed by using the `XMLTEXT` directive in a `SELECT` statement using EXPLICIT mode.</span></span>  
  
 <span data-ttu-id="2c1cb-104">Рассмотрим таблицу `Person` .</span><span class="sxs-lookup"><span data-stu-id="2c1cb-104">Consider the `Person` table.</span></span> <span data-ttu-id="2c1cb-105">В этой таблице имеется столбец `Overflow` , в котором хранится неиспользуемая часть XML-документа.</span><span class="sxs-lookup"><span data-stu-id="2c1cb-105">This table has an `Overflow` column that stores the unconsumed part of the XML document.</span></span>  
  
```  
USE tempdb;  
GO  
CREATE TABLE Person(PersonID varchar(5), PersonName varchar(20), Overflow nvarchar(200));  
GO  
INSERT INTO Person VALUES   
    ('P1','Joe',N'<SomeTag attr1="data">content</SomeTag>')  
   ,('P2','Joe',N'<SomeTag attr2="data"/>')  
   ,('P3','Joe',N'<SomeTag attr3="data" PersonID="P">content</SomeTag>');  
```  
  
 <span data-ttu-id="2c1cb-106">Этот запрос извлекает столбцы из таблицы `Person` .</span><span class="sxs-lookup"><span data-stu-id="2c1cb-106">This query retrieves columns from the `Person` table.</span></span> <span data-ttu-id="2c1cb-107">Для столбца `Overflow` значение *AttributeName* не задано, но значение *directive* установлено в `XMLTEXT` как часть, предоставляющая имя столбца универсальной таблицы.</span><span class="sxs-lookup"><span data-stu-id="2c1cb-107">For the `Overflow` column, *AttributeName* is not specified, but *directive* is set to `XMLTEXT` as part of providing a universal table column name.</span></span>  
  
```  
SELECT 1 as Tag, NULL as parent,  
       PersonID as [Parent!1!PersonID],  
       PersonName as [Parent!1!PersonName],  
       Overflow as [Parent!1!!XMLTEST] -- No AttributeName; XMLTEXT directive  
FROM Person  
FOR XML EXPLICIT;  
```  
  
 <span data-ttu-id="2c1cb-108">В результирующем XML-документе:</span><span class="sxs-lookup"><span data-stu-id="2c1cb-108">In the resulting XML document:</span></span>  
  
-   <span data-ttu-id="2c1cb-109">Так как значение *AttributeName* для столбца `Overflow` не указано, а директива `xmltext` указана, атрибуты элемента <`overflow`> добавляются в список атрибутов содержащего его элемента <`Parent`>.</span><span class="sxs-lookup"><span data-stu-id="2c1cb-109">Because *AttributeName* is not specified for the `Overflow` column and the `xmltext` directive is specified, the attributes in the <`overflow`> element are appended to the attribute list of the enclosing <`Parent`> element.</span></span>  
  
-   <span data-ttu-id="2c1cb-110">Так как атрибут `PersonID` элемента <`xmltext`> конфликтует с атрибутом `PersonID`, извлеченным на том же уровне элемента, атрибут элемента <`xmltext`> не учитывается, даже если `PersonID` имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="2c1cb-110">Because the `PersonID`attribute in the <`xmltext`> element conflicts with the `PersonID` attribute retrieved on the same element level, the attribute in the <`xmltext`> element is ignored, even if `PersonID` is NULL.</span></span> <span data-ttu-id="2c1cb-111">Обычно атрибут замещает атрибут с тем же именем при переполнении.</span><span class="sxs-lookup"><span data-stu-id="2c1cb-111">Generally, an attribute overrides an attribute of the same name in the overflow.</span></span>  
  
 <span data-ttu-id="2c1cb-112">Результат:</span><span class="sxs-lookup"><span data-stu-id="2c1cb-112">This is the result:</span></span>  
  
 `<Parent PersonID="P1" PersonName="Joe" attr1="data">content</Parent>`  
  
 `<Parent PersonID="P2" PersonName="Joe" attr2="data"></Parent>`  
  
 `<Parent PersonID="P3" PersonName="Joe" attr3="data">content</Parent>`  
  
 <span data-ttu-id="2c1cb-113">Если элементы Overflow имеют вложенные элементы и указан тот же запрос, вложенные элементы в столбце `Overflow` добавляются как вложенные элементы содержащего его элемента <`Parent`>.</span><span class="sxs-lookup"><span data-stu-id="2c1cb-113">If the overflow data has subelements and the same query is specified, the subelements in the `Overflow` column are added as the subelements of the enclosing <`Parent`> element.</span></span>  
  
 <span data-ttu-id="2c1cb-114">Например, можно изменить данные в таблице `Person` так, чтобы столбец `Overflow` имел вложенные элементы.</span><span class="sxs-lookup"><span data-stu-id="2c1cb-114">For example, change the data in the `Person` table so that the `Overflow` column now has subelements.</span></span>  
  
```  
USE tempdb;  
GO  
TRUNCATE TABLE Person;  
GO  
INSERT INTO Person VALUES   
    ('P1','Joe',N'<SomeTag attr1="data">content</SomeTag>')  
   ,('P2','Joe',N'<SomeTag attr2="data"/>')  
    ,('P3','Joe',N'<SomeTag attr3="data" PersonID="P"><name>PersonName</name></SomeTag>');  
```  
  
 <span data-ttu-id="2c1cb-115">Если выполнен тот же запрос, вложенные элементы элемента <`xmltext`> добавляются как вложенные элементы содержащего его элемента <`Parent`>:</span><span class="sxs-lookup"><span data-stu-id="2c1cb-115">If the same query is executed, the subelements in the <`xmltext`> element are added as subelements of the enclosing <`Parent`> element:</span></span>  
  
```  
SELECT 1 as Tag, NULL as parent,  
       PersonID as [Parent!1!PersonID],  
       PersonName as [Parent!1!PersonName],  
       Overflow as [Parent!1!!XMLTEXT] -- no AttributeName, XMLTEXT directive  
FROM Person  
FOR XML EXPLICIT;  
```  
  
 <span data-ttu-id="2c1cb-116">Результат:</span><span class="sxs-lookup"><span data-stu-id="2c1cb-116">This is the result:</span></span>  
  
 `<Parent PersonID="P1" PersonName="Joe" attr1="data">content</Parent>`  
  
 `<Parent PersonID="P2" PersonName="Joe" attr2="data"></Parent>`  
  
 `<Parent PersonID="P3" PersonName="Joe" attr3="data">`  
  
 `<name>PersonName</name>`  
  
 `</Parent>`  
  
 <span data-ttu-id="2c1cb-117">Если указано значение *AttributeName* вместе с директивой `xmltext`, атрибуты элемента <`overflow`> добавляются как атрибуты вложенных элементов содержащего его элемента <`Parent`>.</span><span class="sxs-lookup"><span data-stu-id="2c1cb-117">If *AttributeName* is specified with the `xmltext` directive, the attributes of the <`overflow`> element are added as attributes of the subelements of the enclosing <`Parent`> element.</span></span> <span data-ttu-id="2c1cb-118">Имя, указанное для *attributeName* , преобразуется в имя подэлемента.</span><span class="sxs-lookup"><span data-stu-id="2c1cb-118">The name specified for *AttributeName* becomes the name of the subelement.</span></span>  
  
 <span data-ttu-id="2c1cb-119">В этом запросе, *attributeName*, <`overflow`>, указывается вместе с `xmltext` директивой:</span><span class="sxs-lookup"><span data-stu-id="2c1cb-119">In this query, *AttributeName*, <`overflow`>, is specified together with the `xmltext` directive:</span></span>  
  
```  
SELECT 1 as Tag, NULL as parent,  
       PersonID as [Parent!1!PersonID],  
       PersonName as [Parent!1!PersonName],  
       Overflow as [Parent!1!overflow!XMLTEXT] -- Overflow is AttributeName  
                      -- XMLTEXT is a directive  
FROM Person  
FOR XML EXPLICIT  
```  
  
 <span data-ttu-id="2c1cb-120">Результат:</span><span class="sxs-lookup"><span data-stu-id="2c1cb-120">This is the result:</span></span>  
  
 `<Parent PersonID="P1" PersonName="Joe">`  
  
 `<overflow attr1="data">content</overflow>`  
  
 `</Parent>`  
  
 `<Parent PersonID="P2" PersonName="Joe">`  
  
 `<overflow attr2="data" />`  
  
 `</Parent>`  
  
 `<Parent PersonID="P3" PersonName="Joe">`  
  
 `<overflow attr3="data" PersonID="P">`  
  
 `<name>PersonName</name>`  
  
 `</overflow>`  
  
 `</Parent>`  
  
 <span data-ttu-id="2c1cb-121">В этом элементе запроса значение *directive* задано для атрибута `PersonName` .</span><span class="sxs-lookup"><span data-stu-id="2c1cb-121">In this query element, *directive* is specified for `PersonName` attribute.</span></span> <span data-ttu-id="2c1cb-122">Это приводит к тому, что элемент `PersonName` добавляется в качестве вложенного элемента в содержащий его элемент <`Parent`>.</span><span class="sxs-lookup"><span data-stu-id="2c1cb-122">This results in `PersonName` being added as a subelement of the enclosing <`Parent`> element.</span></span> <span data-ttu-id="2c1cb-123">Атрибуты <`xmltext`> все так же добавляются к окружению элемента <`Parent`>.</span><span class="sxs-lookup"><span data-stu-id="2c1cb-123">The attributes of the <`xmltext`> are still appended to the enclosing <`Parent`> element.</span></span> <span data-ttu-id="2c1cb-124">Содержание элемента <`overflow`> и вложенные элементы добавляются в начало других вложенных элементов содержащих их элементов <`Parent`>.</span><span class="sxs-lookup"><span data-stu-id="2c1cb-124">The contents of the <`overflow`> element, subelements, are prepended to the other subelements of the enclosing <`Parent`> elements.</span></span>  
  
```  
SELECT 1      AS Tag, NULL as parent,  
       PersonID   AS [Parent!1!PersonID],  
       PersonName AS [Parent!1!PersonName!element], -- element directive  
       Overflow   AS [Parent!1!!XMLTEXT]  
FROM Person  
FOR XML EXPLICIT;  
```  
  
 <span data-ttu-id="2c1cb-125">Результат:</span><span class="sxs-lookup"><span data-stu-id="2c1cb-125">This is the result:</span></span>  
  
 `<Parent PersonID="P1" attr1="data">content<PersonName>Joe</PersonName>`  
  
 `</Parent>`  
  
 `<Parent PersonID="P2" attr2="data">`  
  
 `<PersonName>Joe</PersonName>`  
  
 `</Parent>`  
  
 `<Parent PersonID="P3" attr3="data">`  
  
 `<name>PersonName</name>`  
  
 `<PersonName>Joe</PersonName>`  
  
 `</Parent>`  
  
 <span data-ttu-id="2c1cb-126">Если в данных столбца `XMLTEXT` содержатся атрибуты корневого элемента, эти атрибуты не показываются в XML-схеме данных, а средство синтаксического анализа MSXML не проверяет результирующий фрагмент XML-документа.</span><span class="sxs-lookup"><span data-stu-id="2c1cb-126">If the `XMLTEXT` column data contains attributes on the root element, these attributes are not shown in the XML data schema and the MSXML parser does not validate the resulting XML document fragment.</span></span> <span data-ttu-id="2c1cb-127">Пример:</span><span class="sxs-lookup"><span data-stu-id="2c1cb-127">For example:</span></span>  
  
```  
SELECT 1 AS Tag,  
       0 ASParent,  
       N'<overflow a="1"/>' AS 'overflow!1!!xmltext'  
FOR XML EXPLICIT, xmldata;  
```  
  
 <span data-ttu-id="2c1cb-128">Результат.</span><span class="sxs-lookup"><span data-stu-id="2c1cb-128">This is the result.</span></span> <span data-ttu-id="2c1cb-129">Обратите внимание, что в возвращаемой схеме атрибут переполнения `a` отсутствует:</span><span class="sxs-lookup"><span data-stu-id="2c1cb-129">Note that in the returned schema, the overflow attribute `a` is missing from the schema:</span></span>  
  
 `<Schema name="Schema2"`  
  
 `xmlns="urn:schemas-microsoft-com:xml-data"`  
  
 `xmlns:dt="urn:schemas-microsoft-com:datatypes">`  
  
 `<ElementType name="overflow" content="mixed" model="open">`  
  
 `</ElementType>`  
  
 `</Schema>`  
  
 `<overflow xmlns="x-schema:#Schema2" a="1">`  
  
 `</overflow>`  
  
## <a name="see-also"></a><span data-ttu-id="2c1cb-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="2c1cb-130">See Also</span></span>  
 [<span data-ttu-id="2c1cb-131">Использование режима EXPLICIT с предложением FOR XML</span><span class="sxs-lookup"><span data-stu-id="2c1cb-131">Use EXPLICIT Mode with FOR XML</span></span>](use-explicit-mode-with-for-xml.md)  
  
  
