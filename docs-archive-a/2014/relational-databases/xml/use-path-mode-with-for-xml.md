---
title: Использование режима PATH для FOR XML | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- PATH FOR XML mode
- characters [SQL Server], XML
- aliases [SQL Server], XML
- FOR XML clause, PATH mode
- FOR XML PATH mode
- column names [SQL Server]
- XPath queries [SQL Server]
ms.assetid: a685a9ad-3d28-4596-aa72-119202df3976
author: rothja
ms.author: jroth
ms.openlocfilehash: ce0cf811f1e610d14a94993b54c51ea079f613e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664777"
---
# <a name="use-path-mode-with-for-xml"></a><span data-ttu-id="8eeb9-102">Использование режима PATH совместно с FOR XML</span><span class="sxs-lookup"><span data-stu-id="8eeb9-102">Use PATH Mode with FOR XML</span></span>
  <span data-ttu-id="8eeb9-103">Как описано в разделе [Создание XML с помощью предложения FOR XML](for-xml-sql-server.md), режим PATH является простым способом смешивания элементов и атрибутов.</span><span class="sxs-lookup"><span data-stu-id="8eeb9-103">As described in [Constructing XML Using FOR XML](for-xml-sql-server.md), the PATH mode provides a simpler way to mix elements and attributes.</span></span> <span data-ttu-id="8eeb9-104">Режим PATH является также простым способом создания дополнительных вложенных объектов для отражения сложных свойств.</span><span class="sxs-lookup"><span data-stu-id="8eeb9-104">PATH mode is also a simpler way to introduce additional nesting for representing complex properties.</span></span> <span data-ttu-id="8eeb9-105">Для построения таких XML-документов из набора строк можно использовать запросы FOR XML в режиме EXPLICIT, но режим PATH является более простой альтернативой зачастую громоздким запросам в режиме EXPLICIT.</span><span class="sxs-lookup"><span data-stu-id="8eeb9-105">You can use FOR XML EXPLICIT mode queries to construct such XML from a rowset, but the PATH mode provides a simpler alternative to the potentially cumbersome EXPLICIT mode queries.</span></span> <span data-ttu-id="8eeb9-106">Режим PATH дополнительно к возможности записи вложенных запросов FOR XML и возвращения экземпляров типа **xml** с помощью директивы TYPE позволяет писать менее сложные запросы.</span><span class="sxs-lookup"><span data-stu-id="8eeb9-106">PATH mode, together with the ability to write nested FOR XML queries and the TYPE directive to return **xml** type instances, allows you to write queries with less complexity.</span></span>  
  
 <span data-ttu-id="8eeb9-107">В режиме PATH имена или псевдонимы столбцов обрабатываются как выражения XPath.</span><span class="sxs-lookup"><span data-stu-id="8eeb9-107">In PATH mode, column names or column aliases are treated as XPath expressions.</span></span> <span data-ttu-id="8eeb9-108">Эти выражения показывают, как значения сопоставляются с XML-данными.</span><span class="sxs-lookup"><span data-stu-id="8eeb9-108">These expressions indicate how the values are being mapped to XML.</span></span> <span data-ttu-id="8eeb9-109">Каждое выражение на языке XPath является относительным элементом XPath, предоставляющим такие сведения, как атрибут, элемент, скалярное значение, а также имя и иерархию узла, который будет сформирован в связи с элементом строки.</span><span class="sxs-lookup"><span data-stu-id="8eeb9-109">Each XPath expression is a relative XPath that provides the item type., such as the attribute, element, and scalar value, and the name and hierarchy of the node that will be generated relative to the row element.</span></span>  
  
 <span data-ttu-id="8eeb9-110">В этом разделе описано сопоставление столбцов в наборе строк в различных условиях и представлены соответствующие примеры.</span><span class="sxs-lookup"><span data-stu-id="8eeb9-110">This section describes mapping columns in a rowset under various conditions, and provides examples.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8eeb9-111">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="8eeb9-111">In This Section</span></span>  
  
-   [<span data-ttu-id="8eeb9-112">Столбцы без имени</span><span class="sxs-lookup"><span data-stu-id="8eeb9-112">Columns without a Name</span></span>](columns-without-a-name.md)  
  
-   [<span data-ttu-id="8eeb9-113">Столбцы с именем</span><span class="sxs-lookup"><span data-stu-id="8eeb9-113">Columns with a Name</span></span>](columns-with-a-name.md)  
  
-   [<span data-ttu-id="8eeb9-114">Столбцы с именем, заданным в виде символа-шаблона</span><span class="sxs-lookup"><span data-stu-id="8eeb9-114">Columns with a Name Specified as a Wildcard Character</span></span>](columns-with-a-name-specified-as-a-wildcard-character.md)  
  
-   [<span data-ttu-id="8eeb9-115">Столбцы с именем XPath-функции проверки узла</span><span class="sxs-lookup"><span data-stu-id="8eeb9-115">Columns with the Name of an XPath Node Test</span></span>](columns-with-the-name-of-an-xpath-node-test.md)  
  
-   [<span data-ttu-id="8eeb9-116">Имена столбцов с путем, указанным как data()</span><span class="sxs-lookup"><span data-stu-id="8eeb9-116">Column Names with the Path Specified as data&#40;&#41;</span></span>](column-names-with-the-path-specified-as-data.md)  
  
-   [<span data-ttu-id="8eeb9-117">Столбцы, по умолчанию содержащие значение NULL</span><span class="sxs-lookup"><span data-stu-id="8eeb9-117">Columns that Contain a Null Value By Default</span></span>](columns-that-contain-a-null-value-by-default.md)  
  
-   [<span data-ttu-id="8eeb9-118">Поддержка пространства имен в режиме PATH</span><span class="sxs-lookup"><span data-stu-id="8eeb9-118">Namespace Support in PATH Mode</span></span>](namespace-support-in-path-mode.md)  
  
-   [<span data-ttu-id="8eeb9-119">Примеры. Использование режима PATH</span><span class="sxs-lookup"><span data-stu-id="8eeb9-119">Examples: Using PATH Mode</span></span>](examples-using-path-mode.md)  
  
## <a name="see-also"></a><span data-ttu-id="8eeb9-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="8eeb9-120">See Also</span></span>  
 <span data-ttu-id="8eeb9-121">[Добавление пространств имен в запросы с WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md) </span><span class="sxs-lookup"><span data-stu-id="8eeb9-121">[Add Namespaces to Queries with WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md) </span></span>  
 <span data-ttu-id="8eeb9-122">[SELECT (Transact-SQL)](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8eeb9-122">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 [<span data-ttu-id="8eeb9-123">FOR XML (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="8eeb9-123">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
  
  
