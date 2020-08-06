---
title: Добавление бизнес-логики для данных XML | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- business logic [XML]
ms.assetid: 0877fb38-f1a2-43d8-86cf-4754be224dc1
author: rothja
ms.author: jroth
ms.openlocfilehash: 5bf8e9edc36e9c420faa92f2db1a92c311194e99
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657589"
---
# <a name="add-business-logic-to-xml-data"></a><span data-ttu-id="3cca5-102">Добавление бизнес-логики для XML-данных</span><span class="sxs-lookup"><span data-stu-id="3cca5-102">Add Business Logic to XML Data</span></span>
  <span data-ttu-id="3cca5-103">Бизнес-логику можно добавить в XML-данные несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="3cca5-103">Your business logic can be added to XML data in several ways:</span></span>  
  
-   <span data-ttu-id="3cca5-104">Можно создать ограничения строк или столбцов, чтобы наложить ограничения, специфические для домена, во время вставки и модификации XML-данных.</span><span class="sxs-lookup"><span data-stu-id="3cca5-104">You can write row or column constraints to enforce domain-specific constraints during insertion and modification of XML data.</span></span>  
  
-   <span data-ttu-id="3cca5-105">Можно написать для XML-столбца триггер, срабатывающий при вставке значений в столбец или при их обновлении.</span><span class="sxs-lookup"><span data-stu-id="3cca5-105">You can write a trigger on the XML column that fires when you insert or update values in the column.</span></span> <span data-ttu-id="3cca5-106">Этот триггер может определять специфические для домена правила проверки или заполнять таблицы свойств.</span><span class="sxs-lookup"><span data-stu-id="3cca5-106">The trigger can contain domain-specific validation rules or populate property tables.</span></span>  
  
-   <span data-ttu-id="3cca5-107">Компонент Database Engine может выполнять управляемый код.</span><span class="sxs-lookup"><span data-stu-id="3cca5-107">The Database Engine includes the ability execute managed code.</span></span> <span data-ttu-id="3cca5-108">Эту интеграцию со средой CLR можно использовать для написания в управляемом коде функций, принимающих XML-значения, и использовать средства обработки XML-данных, предоставляемые пространством имен System.Xml.</span><span class="sxs-lookup"><span data-stu-id="3cca5-108">You can use this common language runtime (CLR) integration to write functions in managed code to which you pass XML values, and use XML processing capabilities provided by the System.Xml namespace.</span></span> <span data-ttu-id="3cca5-109">Примером может служить применение преобразования XSL к XML-данным.</span><span class="sxs-lookup"><span data-stu-id="3cca5-109">An example is to apply XSL transformation to XML data.</span></span> <span data-ttu-id="3cca5-110">Также можно десериализовать XML-данные в один или несколько управляемых классов и обработать их в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="3cca5-110">Alternatively, you can deserialize the XML into one or more managed classes and operate on them by using managed code.</span></span>  
  
-   <span data-ttu-id="3cca5-111">Можно создать хранимые процедуры и функции Transact-SQL, инициирующие обработку XML-столбца в соответствии с бизнес-потребностями.</span><span class="sxs-lookup"><span data-stu-id="3cca5-111">You can write Transact-SQL stored procedures and functions that start the processing on the XML column for your business needs.</span></span>  
  
## <a name="example-applying-xsl-transformation"></a><span data-ttu-id="3cca5-112">Пример Применение преобразования XSL</span><span class="sxs-lookup"><span data-stu-id="3cca5-112">Example: Applying XSL Transformation</span></span>  
 <span data-ttu-id="3cca5-113">Рассмотрим функцию CLR **TransformXml ()** , которая принимает `xml` экземпляр типа данных и преобразование XSL, хранящиеся в файле, применяет преобразование к XML-данным, а затем ВОЗВРАЩАЕТ преобразованный XML в результат.</span><span class="sxs-lookup"><span data-stu-id="3cca5-113">Consider a CLR function **TransformXml()** that accepts an `xml` data type instance and an XSL transformation stored in a file, applies the transformation to the XML data, and then returns the transformed XML in the result.</span></span> <span data-ttu-id="3cca5-114">Вот ее основа, написанная на C#:</span><span class="sxs-lookup"><span data-stu-id="3cca5-114">Following is a skeleton function that is written in C#:</span></span>  
  
```  
public static SqlXml TransformXml (SqlXml XmlData, string xslPath) {  
   // Load XSL transformation  
   XslCompiledTransform xform = new XslCompiledTransform();  
   XPathDocument xslDoc = new XPathDocument (xslPath);  
   xform.Load(xslDoc);  
  
   // Load XML data   
   XPathDocument xDoc = new XPathDocument (XmlData.CreateReader());  
  
   // Return the transformed value  
   MemoryStream xsltResult = new MemoryStream();  
   xform.Transform(xDoc, null, xsltResult);  
   SqlXml retSqlXml = new SqlXml(xsltResult);  
   return (retSqlXml);  
}   
```  
  
 <span data-ttu-id="3cca5-115">После регистрации сборки и создания пользовательской функции [!INCLUDE[tsql](../../includes/tsql-md.md)]**SqlXslTransform()** , соответствующей **TransformXml()** , эту функцию можно вызывать из кода Transact-SQL, как показано в следующем запросе:</span><span class="sxs-lookup"><span data-stu-id="3cca5-115">After the assembly is registered and a user-defined [!INCLUDE[tsql](../../includes/tsql-md.md)] function is created, **SqlXslTransform()** corresponding to **TransformXml()**, the function can be invoked from Transact-SQL as shown in the following query:</span></span>  
  
```  
SELECT SqlXslTransform (xCol, 'C:\MyFile\xsltransform.xsl')  
FROM    T  
WHERE  xCol.exist('/book/title/text()[contains(.,"custom")]') =1;  
```  
  
 <span data-ttu-id="3cca5-116">Результат выполнения этого запроса содержит набор строк преобразованных XML-данных.</span><span class="sxs-lookup"><span data-stu-id="3cca5-116">The query result contains a rowset of the transformed XML.</span></span>  
  
 <span data-ttu-id="3cca5-117">Интеграция со средой CLR в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] расширяет возможности продвижения свойств и декомпозиции XML-данных в таблицы, а также средства запроса XML-данных с использованием управляемых классов из пространства имен System.Xml.</span><span class="sxs-lookup"><span data-stu-id="3cca5-117">The CLR integration into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] expands the possibilities for decomposing XML data into tables or property promotion, and querying XML data by using managed classes in the System.Xml namespace.</span></span> <span data-ttu-id="3cca5-118">Дополнительные сведения см в разделе [Данные XML (SQL Server)](xml-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="3cca5-118">For more information, see [XML Data &#40;SQL Server&#41;](xml-data-sql-server.md).</span></span>  
  
  
