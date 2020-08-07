---
title: Рекомендации и ограничения XML диаграмм обновления (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- updategrams [SQLXML], about updategrams
ms.assetid: b5231859-14e2-4276-bc17-db2817b6f235
author: rothja
ms.author: jroth
ms.openlocfilehash: 6e01e366edc2889691862de639f69220ac4bb439
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732457"
---
# <a name="guidelines-and-limitations-of-xml-updategrams-sqlxml-40"></a><span data-ttu-id="2faae-102">Правила и ограничения диаграмм обновления XML (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="2faae-102">Guidelines and Limitations of XML Updategrams (SQLXML 4.0)</span></span>
  <span data-ttu-id="2faae-103">При использовании диаграмм обновления XML следует помнить следующее.</span><span class="sxs-lookup"><span data-stu-id="2faae-103">Remember the following when using XML updategrams:</span></span>  
  
-   <span data-ttu-id="2faae-104">Если вы используете диаграмма обновления для операции вставки только с одной парой **\<before>** **\<after>** блоков и, этот **\<before>** блок можно опустить.</span><span class="sxs-lookup"><span data-stu-id="2faae-104">If you are using an updategram for an insert operation with only a single pair of **\<before>** and **\<after>** blocks, the **\<before>** block can be omitted.</span></span> <span data-ttu-id="2faae-105">И наоборот, в случае операции удаления **\<after>** блок можно опустить.</span><span class="sxs-lookup"><span data-stu-id="2faae-105">Conversely, in case of a delete operation, the **\<after>** block can be omitted.</span></span>  
  
-   <span data-ttu-id="2faae-106">Если вы используете диаграмма обновления с несколькими **\<before>** **\<after>** блоками и в **\<sync>** теге, то оба **\<before>** блока и блока **\<after>** должны быть заданы как формы **\<before>** и **\<after>** пары.</span><span class="sxs-lookup"><span data-stu-id="2faae-106">If you are using an updategram with multiple **\<before>** and **\<after>** blocks in the **\<sync>** tag, both **\<before>** blocks and **\<after>** blocks must be specified to form **\<before>** and **\<after>** pairs.</span></span>  
  
-   <span data-ttu-id="2faae-107">Обновления в диаграммах обновления применяются к XML-представлению, предоставленному схемой XML.</span><span class="sxs-lookup"><span data-stu-id="2faae-107">The updates in an updategram are applied to the XML view that is provided by the XML schema.</span></span> <span data-ttu-id="2faae-108">Поэтому для успешного сопоставления по умолчанию следует либо указать имя файла схемы в диаграмме обновления, либо, если имя файла не указано, имена элемента и атрибута должны совпадать с именами таблицы и столбца базы данных.</span><span class="sxs-lookup"><span data-stu-id="2faae-108">Therefore, for the default mapping to succeed either you must specify the schema file name in the updategram or, if the file name is not provided, the element and attribute names must match the table and column names in the database.</span></span>  
  
-   <span data-ttu-id="2faae-109">SQLXML 4.0 требует, чтобы все значения столбцов в диаграмме обновления были бы явно сопоставлены в схеме (XDR или XSD), предоставленной для создания XML-представления для дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="2faae-109">SQLXML 4.0 requires that all column values in an updategram must be explicitly mapped in the schema (either XDR or XSD) provided to compose the XML view for its child elements.</span></span> <span data-ttu-id="2faae-110">Такое поведение отличается от более ранних версий SQLXML, которые допускали отсутствие сопоставления для значения столбца в схеме, если оно являлось частью внешнего ключа заметки `sql:relationship`.</span><span class="sxs-lookup"><span data-stu-id="2faae-110">This behavior differs from earlier versions of SQLXML, which allowed a value for a column not mapped in the schema if it was implied as part of the foreign Key in a `sql:relationship` annotation.</span></span> <span data-ttu-id="2faae-111">(Следует отметить, что подобное изменение не повлияет на распространение значений первичного ключа на дочерние элементы, которое по-прежнему происходит в SQLXML 4.0, если явно не указано значение для дочернего элемента.</span><span class="sxs-lookup"><span data-stu-id="2faae-111">(Note that this change does not affect propagation of primary key values to child elements, which still occurs for SQLXML 4.0 if no value is explicitly specified for the child element.</span></span>  
  
-   <span data-ttu-id="2faae-112">Если вы используете диаграмма обновления для изменения данных в двоичном столбце (например, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `image` тип данных), необходимо указать схему сопоставления, в которой [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] должен быть указан тип данных (например, `sql:datatype="image"` ) и тип данных XML (например, `dt:type="binhex"` или `dt:type="binbase64` ).</span><span class="sxs-lookup"><span data-stu-id="2faae-112">If you are using an updategram to modify data in a binary column (such as the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `image` data type), you must provide a mapping schema in which the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data type (for example, `sql:datatype="image"`) and the XML data type (for example, `dt:type="binhex"` or `dt:type="binbase64`) must be specified.</span></span> <span data-ttu-id="2faae-113">Данные для двоичного столбца должны быть указаны в диаграмме обновления; заметка `sql:url-encode`, указанная в схеме сопоставления, не учитывается в диаграмме обновления.</span><span class="sxs-lookup"><span data-stu-id="2faae-113">The data for the binary column must be specified in the updategram; the `sql:url-encode` annotation that is specified in the mapping schema is ignored by the updategram.</span></span>  
  
-   <span data-ttu-id="2faae-114">Если при написании схемы XSD указываемое для заметки `sql:relation` или `sql:field` значение включает в себя специальный символ, такой как символ пробела (например, в имени таблицы «Order Details»), это значение должно быть заключено в скобки (например, «[Order Details]»).</span><span class="sxs-lookup"><span data-stu-id="2faae-114">When you are writing an XSD schema, if the value you specify for the `sql:relation` or `sql:field` annotation includes a special character, such as a space character (for example, in the "Order Details" table name), this value must be enclosed in brackets (for example, "[Order Details]").</span></span>  
  
-   <span data-ttu-id="2faae-115">При использовании диаграмм обновления цепочки связей не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="2faae-115">When using updategrams, chain relationships are not supported.</span></span> <span data-ttu-id="2faae-116">Например, если таблицы А и С связаны через цепочку связей, которая использует таблицу В, при попытке запустить и выполнить диаграмму обновления возникнет следующая ошибка:</span><span class="sxs-lookup"><span data-stu-id="2faae-116">For example, if tables A and C are related through a chain relationship that uses table B, the following error will occur when attempting to run and execute the updategram:</span></span>  
  
    ```  
    There is an inconsistency in the schema provided.  
    ```  
  
     <span data-ttu-id="2faae-117">Даже если как схема, так и диаграмма обновления верны и правильно оформлены, эта ошибка возникнет, если имеется цепочка связей.</span><span class="sxs-lookup"><span data-stu-id="2faae-117">Even if both schema and updategram are otherwise correct and validly formed, this error will occur if a chain relationship is present.</span></span>  
  
-   <span data-ttu-id="2faae-118">Диаграммы обновления не допускают передачи данных типа `image` как параметров в процессе обновления.</span><span class="sxs-lookup"><span data-stu-id="2faae-118">Updategrams do not permit the passing of `image` type data as parameters during updates.</span></span>  
  
-   <span data-ttu-id="2faae-119">Типы больших двоичных объектов (BLOB) `text/ntext` , такие как и изображения, не следует использовать в **\<before>** блоке в при работе с диаграмм обновления, так как в этом случае они будут включены в управление параллелизмом.</span><span class="sxs-lookup"><span data-stu-id="2faae-119">Binary large object (BLOB) types like `text/ntext` and images should not be used in the **\<before>** block in when working with updategrams, because this will include them for use in concurrency control.</span></span> <span data-ttu-id="2faae-120">Это может вызвать проблемы в работе [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] из-за ограничений, налагаемых на сравнение для типов больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="2faae-120">This can cause problems with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] because of the limitations on comparison for BLOB types.</span></span> <span data-ttu-id="2faae-121">Например, ключевое слово LIKE используется в предложении WHERE для сравнения столбцов типа данных `text`; однако, в случае с типами больших двоичных объектов, когда размер данных превышает 8 КБ, такое сравнение завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="2faae-121">For example, the LIKE keyword is used in the WHERE clause for comparing between columns of the `text` data type; however, comparisons will fail in the case of BLOB types where the size of the data is greater than 8K.</span></span>  
  
-   <span data-ttu-id="2faae-122">Специальные символы в данных типа `ntext` могут вызывать проблемы в работе SQLXML 4.0 из-за ограничений, налагаемых на сравнение типов больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="2faae-122">Special characters in `ntext` data can cause problems with SQLXML 4.0 because of the limitations on comparison for BLOB types.</span></span> <span data-ttu-id="2faae-123">Например, использование "[Serializable]" в **\<before>** блоке диаграмм обновления при использовании в проверке параллелизма столбца `ntext` типа приведет к сбою со следующим описанием ошибки SQLOLEDB:</span><span class="sxs-lookup"><span data-stu-id="2faae-123">For example, the use of "[Serializable]" in the **\<before>** block of an updategrams when used in concurrency checking of a column of `ntext` type will fail with the following SQLOLEDB error description:</span></span>  
  
    ```  
    Empty update, no updatable rows found   Transaction aborted  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2faae-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="2faae-124">See Also</span></span>  
 [<span data-ttu-id="2faae-125">Вопросы безопасности диаграмма обновления &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="2faae-125">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
