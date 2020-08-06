---
title: Использование методов value() и nodes() совместно с OPENXML | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- OpenXML method [XML in SQL Server]
- value method [XML in SQL Server]
- nodes method [XML in SQL Server]
ms.assetid: c73dbe55-d685-42eb-b0ee-9f3c5b9d97f3
author: rothja
ms.author: jroth
ms.openlocfilehash: 5dccf5a7ef626d1f1a42d011d22ba77807b34eba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738030"
---
# <a name="use-the-value-and-nodes-methods-with-openxml"></a><span data-ttu-id="199b5-102">Использование методов value() и nodes() совместно с OPENXML</span><span class="sxs-lookup"><span data-stu-id="199b5-102">Use the value() and nodes() Methods with OPENXML</span></span>
  <span data-ttu-id="199b5-103">Для создания набора строк извлеченных значений можно использовать несколько методов **value ()** для `xml` типа данных в предложении **SELECT** .</span><span class="sxs-lookup"><span data-stu-id="199b5-103">You can use multiple **value()** methods on `xml` data type in a **SELECT** clause to generate a rowset of extracted values.</span></span> <span data-ttu-id="199b5-104">Метод **nodes()** позволяет получить внутреннюю ссылку на каждый выбранный узел, которую можно использовать в дополнительных запросах.</span><span class="sxs-lookup"><span data-stu-id="199b5-104">The **nodes()** method yields an internal reference for each selected node that can be used for additional query.</span></span> <span data-ttu-id="199b5-105">При создании набора строк из нескольких столбцов и, возможно, при высокой сложности используемых для этого выражений пути более эффективным подходом может оказаться сочетание методов **nodes()** и **value()** .</span><span class="sxs-lookup"><span data-stu-id="199b5-105">The combination of the **nodes()** and **value()** methods can be more efficient in generating the rowset when it has several columns and, perhaps, when the path expressions used in its generation are complex.</span></span>  
  
 <span data-ttu-id="199b5-106">Метод **nodes ()** возвращает экземпляры специального `xml` типа данных, для каждого из которых в качестве контекста задан другой выбранный узел.</span><span class="sxs-lookup"><span data-stu-id="199b5-106">The **nodes()** method yields instances of a special `xml` data type, each of which has its context set to a different selected node.</span></span> <span data-ttu-id="199b5-107">Этот вид экземпляра XML поддерживает методы **query()** , **value()** , **nodes()** и **exist()** и может быть использован в статистических функциях **count(\*)** .</span><span class="sxs-lookup"><span data-stu-id="199b5-107">This kind of XML instance supports **query()**, **value()**, **nodes()**, and **exist()** methods and can be used in **count(\*)** aggregations.</span></span> <span data-ttu-id="199b5-108">Все другие способы его использования приводят к ошибке.</span><span class="sxs-lookup"><span data-stu-id="199b5-108">All other uses cause an error.</span></span>  
  
## <a name="example-using-nodes"></a><span data-ttu-id="199b5-109">Пример Использование метода nodes()</span><span class="sxs-lookup"><span data-stu-id="199b5-109">Example: Using nodes()</span></span>  
 <span data-ttu-id="199b5-110">Предположим, что требуется извлечь имена и фамилии авторов, которых зовут не «David».</span><span class="sxs-lookup"><span data-stu-id="199b5-110">Assume that you want to extract the first and last names of authors, and the first name is not "David".</span></span> <span data-ttu-id="199b5-111">Кроме того, требуется извлечь эту информацию как набор строк, содержащий два столбца: FirstName и LastName.</span><span class="sxs-lookup"><span data-stu-id="199b5-111">Additionally, you want to extract this information as a rowset that contains two columns, FirstName and LastName.</span></span> <span data-ttu-id="199b5-112">Используя методы **nodes()** и **value()** , можно сделать это следующим образом:</span><span class="sxs-lookup"><span data-stu-id="199b5-112">By using **nodes()** and **value()** methods, you can accomplish this as shown in the following:</span></span>  
  
```  
SELECT nref.value('(first-name/text())[1]', 'nvarchar(50)') FirstName,  
       nref.value('(last-name/text())[1]', 'nvarchar(50)') LastName  
FROM   T CROSS APPLY xCol.nodes('//author') AS R(nref)  
WHERE  nref.exist('first-name[. != "David"]') = 1  
```  
  
 <span data-ttu-id="199b5-113">В данном примере метод `nodes('//author')` получает набор строковых ссылок на элементы `<author>` каждого экземпляра XML.</span><span class="sxs-lookup"><span data-stu-id="199b5-113">In this example, `nodes('//author')` yields a rowset of references to `<author>` elements for each XML instance.</span></span> <span data-ttu-id="199b5-114">Чтобы получить имена и фамилии авторов, вызываются методы **value()** относительно этих ссылок.</span><span class="sxs-lookup"><span data-stu-id="199b5-114">The first and last names of authors are obtained by evaluating **value()** methods relative to those references.</span></span>  
  
 <span data-ttu-id="199b5-115">SQL Server 2000 позволяет создать набор строк на основе экземпляра XML при помощи метода **OpenXml()** .</span><span class="sxs-lookup"><span data-stu-id="199b5-115">SQL Server 2000 provides the capability for generating a rowset from an XML instance by using **OpenXml()**.</span></span> <span data-ttu-id="199b5-116">При этом можно указать реляционную схему набора строк и способ сопоставления значений экземпляра XML со столбцами набора строк.</span><span class="sxs-lookup"><span data-stu-id="199b5-116">You can specify the relational schema for the rowset and how values inside the XML instance map to columns in the rowset.</span></span>  
  
## <a name="example-using-openxml-on-the-xml-data-type"></a><span data-ttu-id="199b5-117">Пример Использование метода OpenXml() с типом данных xml</span><span class="sxs-lookup"><span data-stu-id="199b5-117">Example: Using OpenXml() on the xml Data Type</span></span>  
 <span data-ttu-id="199b5-118">Запрос из предыдущего примера можно переписать с методом **OpenXml()** так, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="199b5-118">The query can be rewritten from the previous example by using **OpenXml()** as shown in the following.</span></span> <span data-ttu-id="199b5-119">С этой целью создается курсор, считывающий каждый экземпляр XML в переменную XML и вызывающий для нее метод OpenXml():</span><span class="sxs-lookup"><span data-stu-id="199b5-119">This is done by creating a cursor that reads each XML instance into an XML variable and then applies OpenXML to it:</span></span>  
  
```  
DECLARE name_cursor CURSOR  
FOR  
   SELECT xCol   
   FROM   T  
OPEN name_cursor  
DECLARE @xmlVal XML  
DECLARE @idoc int  
FETCH NEXT FROM name_cursor INTO @xmlVal  
  
WHILE (@@FETCH_STATUS = 0)  
BEGIN  
   EXEC sp_xml_preparedocument @idoc OUTPUT, @xmlVal  
   SELECT   *  
   FROM   OPENXML (@idoc, '//author')  
          WITH (FirstName  varchar(50) 'first-name',  
                LastName   varchar(50) 'last-name') R  
   WHERE  R.FirstName != 'David'  
  
   EXEC sp_xml_removedocument @idoc  
   FETCH NEXT FROM name_cursor INTO @xmlVal  
END  
CLOSE name_cursor  
DEALLOCATE name_cursor   
```  
  
 <span data-ttu-id="199b5-120">Метод**OpenXml()** создает представление данных в памяти и использует вместо обработчика запросов рабочие таблицы.</span><span class="sxs-lookup"><span data-stu-id="199b5-120">**OpenXml()** creates an in-memory representation and uses work tables instead of the query processor.</span></span> <span data-ttu-id="199b5-121">В основе его работы лежит процессор XPath 1.0 кода MSXML 3.0, а не ядро XQuery.</span><span class="sxs-lookup"><span data-stu-id="199b5-121">It relies on the XPath version 1.0 processor of MSXML version 3.0 instead of the XQuery engine.</span></span> <span data-ttu-id="199b5-122">Рабочие таблицы не обобщаются между несколькими вызовами метода **OpenXml()** , даже если он выполняется для одного экземпляра XML.</span><span class="sxs-lookup"><span data-stu-id="199b5-122">The work tables are not shared among multiple calls to **OpenXml()**, even on the same XML instance.</span></span> <span data-ttu-id="199b5-123">Это ограничивает его масштабируемость.</span><span class="sxs-lookup"><span data-stu-id="199b5-123">This limits its scalability.</span></span> <span data-ttu-id="199b5-124">Метод**OpenXml()** позволяет обращаться к формату краевой таблицы XML-данных без предложения WITH.</span><span class="sxs-lookup"><span data-stu-id="199b5-124">**OpenXml()** allows you to access an edge table format for the XML data when the WITH clause is not specified.</span></span> <span data-ttu-id="199b5-125">Кроме того, он позволяет использовать оставшееся XML-значение в отдельном столбце «переполнения».</span><span class="sxs-lookup"><span data-stu-id="199b5-125">Also, it allows you to use the remaining XML value in a separate, "overflow" column.</span></span>  
  
 <span data-ttu-id="199b5-126">При объединении функций **nodes()** и **value()** эффективно используются XML-индексы.</span><span class="sxs-lookup"><span data-stu-id="199b5-126">The combination of **nodes()** and **value()** functions uses XML indexes effectively.</span></span> <span data-ttu-id="199b5-127">Таким образом, эта комбинация может оказаться более масштабируемой, чем метод **OpenXml**.</span><span class="sxs-lookup"><span data-stu-id="199b5-127">As a result, this combination can exhibit more scalability than **OpenXml**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="199b5-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="199b5-128">See Also</span></span>  
 [<span data-ttu-id="199b5-129">OPENXML (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="199b5-129">OPENXML &#40;SQL Server&#41;</span></span>](openxml-sql-server.md)  
  
  
