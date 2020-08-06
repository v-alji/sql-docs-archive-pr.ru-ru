---
title: Использование режима RAW для FOR XML | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML RAW mode
- XMLSCHEMA option
- FOR XML clause, RAW mode
- RAW FOR XML mode
- ELEMENTS directive
- RAW mode
- XMLDATA option
ms.assetid: 02c1bc0b-760c-4589-9ab1-6927c6d9c734
author: rothja
ms.author: jroth
ms.openlocfilehash: b2908a98336ec8a6e12029ad471f22a33d7a4dcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738066"
---
# <a name="use-raw-mode-with-for-xml"></a><span data-ttu-id="4715e-102">Использование с RAW Mode для FOR XML</span><span class="sxs-lookup"><span data-stu-id="4715e-102">Use RAW Mode with FOR XML</span></span>
  <span data-ttu-id="4715e-103">Режим RAW преобразует каждую строку из результирующего набора запроса в XML-элемент и присваивает ему универсальный идентификатор \<row> или необязательное имя элемента.</span><span class="sxs-lookup"><span data-stu-id="4715e-103">RAW mode transforms each row in the query result set into an XML element that has the generic identifier \<row>, or the optionally provided element name.</span></span> <span data-ttu-id="4715e-104">По умолчанию каждое значение столбца в наборе строк, отличное от NULL, сопоставляется с определенным атрибутом элемента \<row>.</span><span class="sxs-lookup"><span data-stu-id="4715e-104">By default, each column value in the rowset that is not NULL is mapped to an attribute of the \<row> element.</span></span> <span data-ttu-id="4715e-105">Если директива ELEMENTS добавляется в предложение FOR XML, то каждому значению столбца сопоставляется дочерний элемент элемента \<row>.</span><span class="sxs-lookup"><span data-stu-id="4715e-105">If the ELEMENTS directive is added to the FOR XML clause, each column value is mapped to a subelement of the \<row> element.</span></span> <span data-ttu-id="4715e-106">Вместе с директивой ELEMENTS можно дополнительно определить параметр XSINIL для сопоставления значений NULL столбца в результирующем наборе с элементом, обладающим атрибутом xsi:nil=`"`true`"`.</span><span class="sxs-lookup"><span data-stu-id="4715e-106">Together with the ELEMENTS directive, you can optionally specify the XSINIL option to map NULL column values in the result set to an element that has the attribute, xsi:nil=`"`true`"`.</span></span>  
  
 <span data-ttu-id="4715e-107">Есть возможность сделать запрос схемы итогового XML.</span><span class="sxs-lookup"><span data-stu-id="4715e-107">You can request a schema for the resulting XML.</span></span> <span data-ttu-id="4715e-108">При определении параметра XMLDATA возвращается встроенная схема XDR.</span><span class="sxs-lookup"><span data-stu-id="4715e-108">Specifying the XMLDATA option returns an in-line XDR schema.</span></span> <span data-ttu-id="4715e-109">При задании параметра XMLSCHEMA возвращается встроенная XSD-схема.</span><span class="sxs-lookup"><span data-stu-id="4715e-109">Specifying the XMLSCHEMA option returns an in-line XSD schema.</span></span> <span data-ttu-id="4715e-110">Схема появляется в начале данных.</span><span class="sxs-lookup"><span data-stu-id="4715e-110">The schema appears at the start of the data.</span></span> <span data-ttu-id="4715e-111">В итоге ссылка на пространство имен схемы будет повторяться для каждого элемента высшего уровня.</span><span class="sxs-lookup"><span data-stu-id="4715e-111">In the result, the schema namespace reference is repeated for every top-level element.</span></span>  
  
 <span data-ttu-id="4715e-112">Параметр BINARY BASE64 необходимо определить в предложении FOR XML для возвращения двоичных данных в base64-кодированном формате.</span><span class="sxs-lookup"><span data-stu-id="4715e-112">The BINARY BASE64 option must be specified in the FOR XML clause to return the binary data in base64-encoded format.</span></span> <span data-ttu-id="4715e-113">В режиме RAW извлечение двоичных данных без определения параметра BINARY BASE64 приводит к ошибке.</span><span class="sxs-lookup"><span data-stu-id="4715e-113">In RAW mode, retrieving binary data without specifying the BINARY BASE64 option will result in an error.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4715e-114">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="4715e-114">In This Section</span></span>  
 <span data-ttu-id="4715e-115">Этот раздел содержит следующие примеры.</span><span class="sxs-lookup"><span data-stu-id="4715e-115">This section contains the following examples:</span></span>  
  
-   [<span data-ttu-id="4715e-116">Пример. Получение сведений о модели продукта в формате XML</span><span class="sxs-lookup"><span data-stu-id="4715e-116">Example: Retrieving Product Model Information as XML</span></span>](example-retrieving-product-model-information-as-xml.md)  
  
-   [<span data-ttu-id="4715e-117">Пример. Указание XSINIL с директивой ELEMENTS</span><span class="sxs-lookup"><span data-stu-id="4715e-117">Example: Specifying XSINIL with the ELEMENTS Directive</span></span>](example-specifying-xsinil-with-the-elements-directive.md)  
  
-   [<span data-ttu-id="4715e-118">Пример Запросы к схемам как к результатам с помощью параметров XMLDATA и XMLSCHEMA</span><span class="sxs-lookup"><span data-stu-id="4715e-118">Example: Requesting Schemas as Results with the XMLDATA and XMLSCHEMA Options</span></span>](example-requesting-schemas-as-results-with-the-xmldata-and-xmlschema-options.md)  
  
-   [<span data-ttu-id="4715e-119">Пример. Получение двоичных данных</span><span class="sxs-lookup"><span data-stu-id="4715e-119">Example: Retrieving Binary Data</span></span>](example-retrieving-binary-data.md)  
  
-   [<span data-ttu-id="4715e-120">Пример. Переименование элемента &#60;row&#62;</span><span class="sxs-lookup"><span data-stu-id="4715e-120">Example: Renaming the &#60;row&#62; Element</span></span>](example-renaming-the-row-element.md)  
  
-   [<span data-ttu-id="4715e-121">Пример. Задание корневого элемента для XML-документа, сформированного предложением FOR XML</span><span class="sxs-lookup"><span data-stu-id="4715e-121">Example: Specifying a Root Element for the XML Generated by FOR XML</span></span>](example-specifying-a-root-element-for-the-xml-generated-by-for-xml.md)  
  
-   [<span data-ttu-id="4715e-122">Пример. Запросы к столбцам XMLType</span><span class="sxs-lookup"><span data-stu-id="4715e-122">Example: Querying XMLType Columns</span></span>](example-querying-xmltype-columns.md)  
  
## <a name="see-also"></a><span data-ttu-id="4715e-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="4715e-123">See Also</span></span>  
 <span data-ttu-id="4715e-124">[Добавление пространств имен в запросы с WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md) </span><span class="sxs-lookup"><span data-stu-id="4715e-124">[Add Namespaces to Queries with WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md) </span></span>  
 <span data-ttu-id="4715e-125">[Использование режима AUTO совместно с FOR XML](use-auto-mode-with-for-xml.md) </span><span class="sxs-lookup"><span data-stu-id="4715e-125">[Use AUTO Mode with FOR XML](use-auto-mode-with-for-xml.md) </span></span>  
 <span data-ttu-id="4715e-126">[Использование режима EXPLICIT совместно с предложением FOR XML](use-explicit-mode-with-for-xml.md) </span><span class="sxs-lookup"><span data-stu-id="4715e-126">[Use EXPLICIT Mode with FOR XML](use-explicit-mode-with-for-xml.md) </span></span>  
 <span data-ttu-id="4715e-127">[Использование режима PATH совместно с FOR XML](use-path-mode-with-for-xml.md) </span><span class="sxs-lookup"><span data-stu-id="4715e-127">[Use PATH Mode with FOR XML](use-path-mode-with-for-xml.md) </span></span>  
 <span data-ttu-id="4715e-128">[SELECT (Transact-SQL)](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4715e-128">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 [<span data-ttu-id="4715e-129">FOR XML (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="4715e-129">FOR XML &#40;SQL Server&#41;</span></span>](../xml/for-xml-sql-server.md)  
  
  
