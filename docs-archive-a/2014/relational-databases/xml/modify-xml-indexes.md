---
title: Изменение XML-индексов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XML indexes [SQL Server], modifying
- modifying indexes
ms.assetid: 24d50fe1-c6ec-49e6-91a3-9791851ba53d
author: rothja
ms.author: jroth
ms.openlocfilehash: c5c67470fc9aaaeefe49e5ccb1a8602e082c4054
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729154"
---
# <a name="modify-xml-indexes"></a><span data-ttu-id="c0e75-102">Изменение XML-индексов</span><span class="sxs-lookup"><span data-stu-id="c0e75-102">Modify XML Indexes</span></span>
  <span data-ttu-id="c0e75-103">Для изменения существующих XML-индексов и индексов других типов можно использовать DDL-инструкцию [ALTER INDEX (Transact-SQL)](/sql/t-sql/statements/alter-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c0e75-103">The [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] DDL statement can be used to modify existing XML and non-XML indexes.</span></span> <span data-ttu-id="c0e75-104">Однако к XML-индексам могут применяться не все параметры ALTER INDEX.</span><span class="sxs-lookup"><span data-stu-id="c0e75-104">However, not all the ALTER INDEX options are available to XML indexes.</span></span> <span data-ttu-id="c0e75-105">В частности, недопустимо использование следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="c0e75-105">The following options are not valid when modifying XML indexes:</span></span>  
  
-   <span data-ttu-id="c0e75-106">Параметр повторного создания и установки IGNORE_DUP_KEY для XML-индексов недопустим.</span><span class="sxs-lookup"><span data-stu-id="c0e75-106">The rebuild and set option IGNORE_DUP_KEY is not valid for XML indexes.</span></span> <span data-ttu-id="c0e75-107">Для вторичных XML-индексов параметр повторного создания ONLINE должен быть установлен в OFF.</span><span class="sxs-lookup"><span data-stu-id="c0e75-107">The rebuild option ONLINE must be set to OFF for secondary XML indexes.</span></span> <span data-ttu-id="c0e75-108">В инструкции ALTER INDEX недопустим параметр DROP_EXISTING.</span><span class="sxs-lookup"><span data-stu-id="c0e75-108">The option DROP_EXISTING is not permitted in the ALTER INDEX statement.</span></span>  
  
-   <span data-ttu-id="c0e75-109">Изменения ограничения первичного ключа в пользовательской таблице на XML-индексы автоматически не распространяются.</span><span class="sxs-lookup"><span data-stu-id="c0e75-109">The modifications of the primary key constraint in the user table are not automatically propagated to XML indexes.</span></span> <span data-ttu-id="c0e75-110">Пользователь должен вначале удалить, а затем вновь создать XML-индекс.</span><span class="sxs-lookup"><span data-stu-id="c0e75-110">The user must drop the XML indexes first and then re-create them.</span></span>  
  
-   <span data-ttu-id="c0e75-111">Инструкция ALTER INDEX ALL применяется как к обычным, так и к XML-индексам.</span><span class="sxs-lookup"><span data-stu-id="c0e75-111">If ALTER INDEX ALL is specified, it applies to both non-XML and XML indexes.</span></span> <span data-ttu-id="c0e75-112">Если заданы параметры индексирования, недопустимые для обоих типов индексов,</span><span class="sxs-lookup"><span data-stu-id="c0e75-112">Indexing options may be specified that are not valid for both types of indexes.</span></span> <span data-ttu-id="c0e75-113">то вся инструкция завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="c0e75-113">In this case, the whole statement fails.</span></span>  
  
## <a name="example-modifying-an-xml-index"></a><span data-ttu-id="c0e75-114">Пример Изменение XML-индекса</span><span class="sxs-lookup"><span data-stu-id="c0e75-114">Example: Modifying an XML Index</span></span>  
 <span data-ttu-id="c0e75-115">В следующем примере создается XML-индекс, после чего производится его изменение — установка параметра `ALLOW_ROW_LOCKS` в значение `OFF`.</span><span class="sxs-lookup"><span data-stu-id="c0e75-115">In the following example, an XML index is created and then modified by setting the option `ALLOW_ROW_LOCKS` to `OFF`.</span></span> <span data-ttu-id="c0e75-116">Когда параметр `ALLOW_ROW_LOCKS` установлен в значение `OFF`, строки не блокируются и доступ к указанным индексам осуществляется при помощи блокировок уровня страницы и таблицы.</span><span class="sxs-lookup"><span data-stu-id="c0e75-116">When `ALLOW_ROW_LOCKS` is `OFF`, rows are not locked and access to the specified indexes is obtained by using page-and table-level locks.</span></span>  
  
```  
CREATE TABLE T (Col1 INT PRIMARY KEY, XmlCol XML)  
GO  
-- Create primary XML index.   
CREATE PRIMARY XML INDEX PIdx_T_XmlCol   
ON T(XmlCol)  
GO  
-- Note the type 3 is index on XML type.  
SELECT *  
FROM sys.xml_indexes  
WHERE object_id = object_id('T')  
AND name='PIdx_T_XmlCol'  
  
-- Modify and set an index option.  
ALTER INDEX PIdx_T_XmlCol on T   
SET (ALLOW_ROW_LOCKS = OFF)  
```  
  
## <a name="example-disabling-and-enabling-an-xml-index"></a><span data-ttu-id="c0e75-117">Пример Отключение и включение XML-индекса</span><span class="sxs-lookup"><span data-stu-id="c0e75-117">Example: Disabling and Enabling an XML Index</span></span>  
 <span data-ttu-id="c0e75-118">По умолчанию XML-индекс включен.</span><span class="sxs-lookup"><span data-stu-id="c0e75-118">By default, an XML index is enabled.</span></span> <span data-ttu-id="c0e75-119">Если XML-индекс отключен, то запросы, выполняемые для XML-столбца, не пользуются им.</span><span class="sxs-lookup"><span data-stu-id="c0e75-119">If an XML index is disabled, the queries running against the XML column do not use the XML index.</span></span> <span data-ttu-id="c0e75-120">Для включения XML-индекса используется инструкция `ALTER INDEX` с параметром `REBUILD` .</span><span class="sxs-lookup"><span data-stu-id="c0e75-120">To enable an XML index, use `ALTER INDEX` with the `REBUILD` option.</span></span>  
  
```  
CREATE TABLE T (Col1 INT PRIMARY KEY, XmlCol XML)  
GO  
CREATE PRIMARY XML INDEX PIdx_T_XmlCol ON T(XmlCol)  
GO  
ALTER INDEX PIdx_T_XmlCol on T DISABLE  
Go  
-- Verify index is disabled.  
SELECT *  
FROM sys.xml_indexes  
WHERE object_id = object_id('T')  
AND name='PIdx_T_XmlCol'  
-- Rebuild the index.  
ALTER INDEX PIdx_T_XmlCol on T REBUILD  
Go  
```  
  
## <a name="see-also"></a><span data-ttu-id="c0e75-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="c0e75-121">See Also</span></span>  
 [<span data-ttu-id="c0e75-122">XML-индексы (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c0e75-122">XML Indexes &#40;SQL Server&#41;</span></span>](xml-indexes-sql-server.md)  
  
  
