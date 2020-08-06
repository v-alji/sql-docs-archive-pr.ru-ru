---
title: Использование предложения FOR XML для создания XML на основе набора строк | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, generating XML from rowsets
ms.assetid: d061c0f1-3de9-4ad1-bbca-ce45d064b6c8
author: rothja
ms.author: jroth
ms.openlocfilehash: dcf9feb4dab9ad1149ab433c9d9b4999c96c1cdd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751956"
---
# <a name="generate-xml-from-rowsets-with-for-xml"></a><span data-ttu-id="38cd8-102">Использование предложения XML FOR для создания XML на основе набора строк</span><span class="sxs-lookup"><span data-stu-id="38cd8-102">Generate XML from Rowsets with FOR XML</span></span>
  <span data-ttu-id="38cd8-103">Вы можете создать `xml` экземпляр типа данных из набора строк, используя for XML с новой директивой **Type** .</span><span class="sxs-lookup"><span data-stu-id="38cd8-103">You can generate an `xml` data type instance from a rowset by using FOR XML with the new **TYPE** directive.</span></span>  
  
 <span data-ttu-id="38cd8-104">Результат может быть присвоен `xml` столбцу, переменной или параметру типа данных.</span><span class="sxs-lookup"><span data-stu-id="38cd8-104">The result can be assigned to an `xml` data type column, variable, or parameter.</span></span> <span data-ttu-id="38cd8-105">Кроме того, инструкции FOR XML могут быть вложены друг в друга, создавая произвольные иерархические структуры.</span><span class="sxs-lookup"><span data-stu-id="38cd8-105">Also, FOR XML can be nested to generate any hierarchical structure.</span></span> <span data-ttu-id="38cd8-106">Благодаря этому создавать вложенные инструкции FOR XML намного проще, чем FOR XML EXPLICIT, но при большой глубине иерархии они могут оказаться менее эффективными.</span><span class="sxs-lookup"><span data-stu-id="38cd8-106">This makes nested FOR XML much more convenient to write than FOR XML EXPLICIT, but it may not perform as well for deep hierarchies.</span></span> <span data-ttu-id="38cd8-107">Предложение FOR XML поддерживает также новый режим PATH.</span><span class="sxs-lookup"><span data-stu-id="38cd8-107">FOR XML also introduces a new PATH mode.</span></span> <span data-ttu-id="38cd8-108">Этот режим определяет в дереве XML путь к значению столбца.</span><span class="sxs-lookup"><span data-stu-id="38cd8-108">This new mode specifies the path in the XML tree where a column's value appears.</span></span>  
  
 <span data-ttu-id="38cd8-109">Новая директива **FOR XML TYPE** позволяет определять для реляционных данных XML-представления, поддерживающие только чтение, используя синтаксис SQL.</span><span class="sxs-lookup"><span data-stu-id="38cd8-109">The new **FOR XML TYPE** directive can be used to define read-only XML views over relational data with SQL syntax.</span></span> <span data-ttu-id="38cd8-110">Как показано в следующих примерах, представление можно запрашивать при помощи инструкций SQL и встроенного механизма XQuery.</span><span class="sxs-lookup"><span data-stu-id="38cd8-110">The view can be queried with SQL statements and embedded XQuery, as shown in the following example.</span></span> <span data-ttu-id="38cd8-111">К этим SQL-представлениям можно также обращаться в хранимых процедурах.</span><span class="sxs-lookup"><span data-stu-id="38cd8-111">You can also refer to these SQL views in stored procedures.</span></span>  
  
## <a name="example-sql-view-returning-generated-xml-data-type"></a><span data-ttu-id="38cd8-112">Пример SQL-представление, возвращающее сформированный тип данных XML</span><span class="sxs-lookup"><span data-stu-id="38cd8-112">Example: SQL View Returning Generated xml Data Type</span></span>  
 <span data-ttu-id="38cd8-113">Следующий код создает XML-представление для реляционного столбца pk и заносит в него информацию об авторах, извлекаемую из XML-столбца:</span><span class="sxs-lookup"><span data-stu-id="38cd8-113">The following SQL view definition creates an XML view over a relational column, pk, and book authors retrieved from an XML column:</span></span>  
  
```  
CREATE VIEW V (xmlVal) AS  
SELECT pk, xCol.query('/book/author')  
FROM   T  
FOR XML AUTO, TYPE  
```  
  
 <span data-ttu-id="38cd8-114">Представление V содержит одну строку с одним Колумнксмлвал типа XML, к которой `.` можно обращаться как к обычному `xml` экземпляру типа данных.</span><span class="sxs-lookup"><span data-stu-id="38cd8-114">The V view contains a single row with a single columnxmlVal of XML type`.` It can be queried like a regular `xml` data type instance.</span></span> <span data-ttu-id="38cd8-115">Например, следующий запрос возвращает сведения об авторе по имени «David»:</span><span class="sxs-lookup"><span data-stu-id="38cd8-115">For example, the following query returns the author whose first name is "David":</span></span>  
  
```  
SELECT xmlVal.query('//author[first-name = "David"]')  
FROM   V  
```  
  
 <span data-ttu-id="38cd8-116">Определения SQL-представлений в чем-то похожи на XML-представления, создаваемые с использованием аннотированных схем.</span><span class="sxs-lookup"><span data-stu-id="38cd8-116">SQL view definitions are somewhat similar to XML views that are created by using annotated schemas.</span></span> <span data-ttu-id="38cd8-117">Однако между ними есть важные различия.</span><span class="sxs-lookup"><span data-stu-id="38cd8-117">However, there are important differences.</span></span> <span data-ttu-id="38cd8-118">Определение SQL-представления поддерживает только чтение, а работать с ним нужно, используя встроенный механизм XQuery.</span><span class="sxs-lookup"><span data-stu-id="38cd8-118">The SQL view definition is read-only and must be manipulated with embedded XQuery.</span></span> <span data-ttu-id="38cd8-119">XML-представления создаются при помощи аннотированной схемы.</span><span class="sxs-lookup"><span data-stu-id="38cd8-119">The XML views are created by using annotated schema.</span></span> <span data-ttu-id="38cd8-120">Кроме того, SQL-представление материализует XML-результаты перед применением выражения XQuery, тогда как при запросах XPath для XML-представлений выполняются SQL-запросы базовых таблиц.</span><span class="sxs-lookup"><span data-stu-id="38cd8-120">Additionally, the SQL view materializes the XML result before applying the XQuery expression, while the XPath queries on XML views evaluate SQL queries on the underlying tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38cd8-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="38cd8-121">See Also</span></span>  
 [<span data-ttu-id="38cd8-122">FOR XML (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="38cd8-122">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
  
  
