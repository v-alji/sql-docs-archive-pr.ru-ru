---
title: Использование параметра BINARY BASE64 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- AUTO FOR XML mode, BINARY BASE64 option
ms.assetid: 86a7bb85-7f83-412a-b775-d2c379702fe9
author: rothja
ms.author: jroth
ms.openlocfilehash: 090d6a91ee56707a4eb1d545aa5a05bc25999fab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738036"
---
# <a name="use-the-binary-base64-option"></a><span data-ttu-id="cbb61-102">Использование параметра BINARY BASE64</span><span class="sxs-lookup"><span data-stu-id="cbb61-102">Use the BINARY BASE64 Option</span></span>
  <span data-ttu-id="cbb61-103">Если в запросе задан аргумент BINARY BASE64, двоичные данные возвращаются в формате кодирования base64.</span><span class="sxs-lookup"><span data-stu-id="cbb61-103">If the BINARY BASE64 option is specified in the query, the binary data is returned in base64 encoding format.</span></span> <span data-ttu-id="cbb61-104">По умолчанию, если аргумент BINARY BASE64 не задан, режим AUTO поддерживает кодирование URL-адресов двоичных данных.</span><span class="sxs-lookup"><span data-stu-id="cbb61-104">By default, if the BINARY BASE64 option is not specified, AUTO mode supports URL encoding of binary data.</span></span> <span data-ttu-id="cbb61-105">Это означает, что вместо двоичных данных возвращается ссылка на относительный URL-адрес виртуального корня базы данных, в которой выполнялся запрос.</span><span class="sxs-lookup"><span data-stu-id="cbb61-105">That is, instead of binary data, a reference to a relative URL to the virtual root of the database where the query was executed is returned.</span></span> <span data-ttu-id="cbb61-106">Эта ссылка может использоваться для доступа к действительным двоичным данным в последующих операциях при помощи запроса объекта базы данных SQLXML ISAPI.</span><span class="sxs-lookup"><span data-stu-id="cbb61-106">This reference can be used to access the actual binary data in subsequent operations by using the SQLXML ISAPI dbobject query.</span></span> <span data-ttu-id="cbb61-107">Для идентификации изображения запрос должен предоставить достаточно данных, например первичные ключевые столбцы.</span><span class="sxs-lookup"><span data-stu-id="cbb61-107">The query must provide enough information, such as primary key columns, to identify the image.</span></span>  
  
 <span data-ttu-id="cbb61-108">При задании запроса, если используется псевдоним для двоичного столбца представления, псевдоним возвращается в виде URL-адреса двоичных данных.</span><span class="sxs-lookup"><span data-stu-id="cbb61-108">In specifying a query, if an alias is used for the binary column of the view, the alias is returned in the URL encoding of the binary data.</span></span> <span data-ttu-id="cbb61-109">В последующих операциях псевдоним не имеет смысла, и URL-адрес не может использоваться для получения изображения.</span><span class="sxs-lookup"><span data-stu-id="cbb61-109">In subsequent operations, the alias is meaningless, and the URL encoding cannot be used to retrieve the image.</span></span> <span data-ttu-id="cbb61-110">Поэтому не используйте псевдонимы при запросе представления в режиме FOR XML AUTO.</span><span class="sxs-lookup"><span data-stu-id="cbb61-110">Therefore, do not use aliases when querying a view using FOR XML AUTO mode.</span></span>  
  
 <span data-ttu-id="cbb61-111">Например, в запросе SELECT приведение любого столбца к большому двоичному объекту (BLOB) делает этот столбец временной сущностью, которая теряет связанные с ней имя таблицы и имя столбца.</span><span class="sxs-lookup"><span data-stu-id="cbb61-111">For example, in a SELECT query, casting any column to a binary large object (BLOB) makes it a temporary entity in that it loses its associated table name and column name.</span></span> <span data-ttu-id="cbb61-112">Поэтому запросы в режиме AUTO будут формировать ошибки, так как они не будут знать, куда поместить этот объект в иерархии XML.</span><span class="sxs-lookup"><span data-stu-id="cbb61-112">This causes AUTO mode queries to generate an error, because it does not know where to put this value in the XML hierarchy.</span></span> <span data-ttu-id="cbb61-113">Пример:</span><span class="sxs-lookup"><span data-stu-id="cbb61-113">For example:</span></span>  
  
```  
CREATE TABLE MyTable (Col1 int PRIMARY KEY, Col2 binary)  
INSERT INTO MyTable VALUES (1, 0x7);  
```  
  
 <span data-ttu-id="cbb61-114">Следующий запрос вернет ошибку из-за приведения к типу BLOB:</span><span class="sxs-lookup"><span data-stu-id="cbb61-114">This query produces an error, because of the casting to a binary large object (BLOB):</span></span>  
  
```  
SELECT Col1,  
CAST(Col2 as image) as Col2  
FROM MyTable  
FOR XML AUTO;  
```  
  
 <span data-ttu-id="cbb61-115">Решение этой проблемы заключается в добавлении параметра BINARY BASE64 к предложению FOR XML.</span><span class="sxs-lookup"><span data-stu-id="cbb61-115">The solution is to add the BINARY BASE64 option to the FOR XML clause.</span></span> <span data-ttu-id="cbb61-116">Если удалено приведение типов, запрос вернет ожидаемый результат:</span><span class="sxs-lookup"><span data-stu-id="cbb61-116">If you remove the casting, the query produces the results as expected:</span></span>  
  
```  
SELECT Col1,  
CAST(Col2 as image) as Col2  
FROM MyTable  
FOR XML AUTO, BINARY BASE64;  
```  
  
 <span data-ttu-id="cbb61-117">Результат:</span><span class="sxs-lookup"><span data-stu-id="cbb61-117">This is the result:</span></span>  
  
```  
<MyTable Col1="1" Col2="Bw==" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="cbb61-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="cbb61-118">See Also</span></span>  
 [<span data-ttu-id="cbb61-119">Использование AUTO Mode с FOR XML</span><span class="sxs-lookup"><span data-stu-id="cbb61-119">Use AUTO Mode with FOR XML</span></span>](use-auto-mode-with-for-xml.md)  
  
  
