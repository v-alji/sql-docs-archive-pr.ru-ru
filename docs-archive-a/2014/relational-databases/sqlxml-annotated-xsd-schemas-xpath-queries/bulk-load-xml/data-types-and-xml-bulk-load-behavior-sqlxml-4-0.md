---
title: Типы данных и поведение при выполнении групповой загрузки XML (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- bulk load [SQLXML], data types
- data types [SQLXML], XML Bulk Load
- XML Bulk Load [SQLXML], data types
ms.assetid: d1ac1939-1f6c-4398-b7a7-a79ca608a4f1
author: rothja
ms.author: jroth
ms.openlocfilehash: 34b03423f3bb88166d0d9ce5b0df450d4455e7ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665969"
---
# <a name="data-types-and-xml-bulk-load-behavior-sqlxml-40"></a><span data-ttu-id="921df-102">Типы данных и массовая загрузка XML (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="921df-102">Data Types and XML Bulk Load Behavior (SQLXML 4.0)</span></span>
  <span data-ttu-id="921df-103">Типы данных, заданные в схеме сопоставления (тип XSD, XDR и `sql:datatype`), как правило, пропускаются, за исключением следующих случаев.</span><span class="sxs-lookup"><span data-stu-id="921df-103">The data types that are specified in the mapping schema (XSD or XDR type and `sql:datatype`) are generally ignored, except in the following cases:</span></span>  
  
 <span data-ttu-id="921df-104">В XSD.</span><span class="sxs-lookup"><span data-stu-id="921df-104">In XSD:</span></span>  
  
-   <span data-ttu-id="921df-105">Если данные имеют тип `dateTime` или `time`, необходимо задать `sql:datatype`, поскольку в ходе массовой загрузки XML выполняется преобразование данных перед их отправкой в Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="921df-105">If the type is `dateTime` or `time`, you must specify the `sql:datatype` because XML Bulk Load performs data conversion before sending the data to Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="921df-106">При выполнении групповой загрузки в столбец `uniqueidentifier` типа в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , а значение XSD — это идентификатор GUID, включающий фигурные скобки ({и}), необходимо указать **SQL: datatype = "uniqueidentifier"** , чтобы удалить фигурные скобки перед вставкой значения в столбец.</span><span class="sxs-lookup"><span data-stu-id="921df-106">When you are bulk loading into a column of `uniqueidentifier` type in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and the XSD value is a GUID that includes braces ({ and }), you must specify **sql:datatype="uniqueidentifier"** to remove the braces before the value is inserted into the column.</span></span> <span data-ttu-id="921df-107">Если атрибут `sql:datatype` не задан, то значение передается вместе с фигурными скобками и вставка завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="921df-107">If `sql:datatype` is not specified, the value is sent with the braces and the insert fails.</span></span>  
  
 <span data-ttu-id="921df-108">Дополнительные сведения о см `sql:datatype` . [в разделе приведение типов данных и аннотация SQL: datatype &#40;&#41;SQLXML 4,0 ](../../sqlxml-annotated-xsd-schemas-using/data-type-coercions-and-the-sql-datatype-annotation-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="921df-108">For more information about `sql:datatype`, see [Data Type Coercions and the sql:datatype Annotation &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-using/data-type-coercions-and-the-sql-datatype-annotation-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="921df-109">В XDR:</span><span class="sxs-lookup"><span data-stu-id="921df-109">In XDR:</span></span>  
  
-   <span data-ttu-id="921df-110">Если `dt:type` имеет тип `datetime`, `time`, `dateTime.tz` или `time.tz`, необходимо задать типы данных `dt:type` и `sql:datatype`, поскольку при массовой загрузке XML выполняется преобразование данных перед отправкой в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="921df-110">If the `dt:type` is `datetime`, `time`, `dateTime.tz`, or `time.tz`, you must specify both the `dt:type` and `sql:datatype` data types because XML Bulk Load performs data conversion before it sends the data to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="921df-111">Если XML-данные имеют тип `uuid` , `sql:datatype` необходимо указать. **DT: Type = "UUID"** также требуется, если только данные не являются строковыми данными.</span><span class="sxs-lookup"><span data-stu-id="921df-111">If your XML data is of type `uuid`, `sql:datatype` must be specified; **dt:type="uuid"** is also required, unless the data is string data.</span></span> <span data-ttu-id="921df-112">Если атрибут `dt:uuid` не задан, то при массовой загрузке XML строки с фигурными скобками принимаются (фигурные скобки при необходимости удаляются).</span><span class="sxs-lookup"><span data-stu-id="921df-112">If you do not specify `dt:uuid`, XML Bulk Load accepts strings with braces (and removes them if needed).</span></span>  
  
-   <span data-ttu-id="921df-113">Если данные XML имеют тип `bin.base64` или `bin.hex`, необходимо указать тип данных XML с атрибутом `dt:type`.</span><span class="sxs-lookup"><span data-stu-id="921df-113">If the XML data is `bin.base64` or `bin.hex`, you must specify the XML data type with `dt:type`.</span></span> <span data-ttu-id="921df-114">В таком случае при массовой загрузке XML данные загружаются в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] в шестнадцатеричном представлении.</span><span class="sxs-lookup"><span data-stu-id="921df-114">XML Bulk Load then loads the data into [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] as a hexadecimal representation of the data.</span></span>  
  
  
