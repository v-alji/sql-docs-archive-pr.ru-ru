---
title: Выполнение групповой загрузки XML-данных (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XML Bulk Load [SQLXML]
- bulk load [SQLXML]
- data insertions [SQLXML]
- SQLXML, bulk loading
- XSD schemas [SQLXML], XML Bulk Load
- XDR schemas [SQLXML], XML Bulk Load
- inserting data
ms.assetid: 3708b493-322e-4f3c-9b27-441d0c0ee346
author: rothja
ms.author: jroth
ms.openlocfilehash: ec540ff082b02fa43b9abd9f294752073eb68d5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728142"
---
# <a name="performing-bulk-load-of-xml-data-sqlxml-40"></a><span data-ttu-id="4ce45-102">Выполнение массовой загрузки XML-данных (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="4ce45-102">Performing Bulk Load of XML Data (SQLXML 4.0)</span></span>
  <span data-ttu-id="4ce45-103">Массовая загрузка XML является самостоятельным объектом COM, который позволяет загрузить частично структурированные XML-данные в таблицы Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4ce45-103">XML Bulk Load is a standalone COM object that allows you to load semistructured XML data into Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tables.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4ce45-104">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="4ce45-104">In This Section</span></span>  
 [<span data-ttu-id="4ce45-105">Общие сведения о групповой загрузке XML &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="4ce45-105">Introduction to XML Bulk Load &#40;SQLXML 4.0&#41;</span></span>](introduction-to-xml-bulk-load-sqlxml-4-0.md)  
 <span data-ttu-id="4ce45-106">Содержит основные сведения о массовой загрузке XML-данных при помощи программы XML Bulk Load.</span><span class="sxs-lookup"><span data-stu-id="4ce45-106">Provides general information about bulk loading XML data with the XML Bulk Load utility.</span></span> <span data-ttu-id="4ce45-107">Разделы включают в себя описание потоковых XML-данных, а также синхронные и асинхронные операции массовой загрузки.</span><span class="sxs-lookup"><span data-stu-id="4ce45-107">Topics include XML data streaming and transacted vs. nontransacted bulk load operations.</span></span>  
  
 [<span data-ttu-id="4ce45-108">Процесс создания записей &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="4ce45-108">Record Generation Process &#40;SQLXML 4.0&#41;</span></span>](record-generation-process-sqlxml-4-0.md)  
 <span data-ttu-id="4ce45-109">Содержит описание процесса и правил, посредством которых создаются записи для массовой загрузки XML.</span><span class="sxs-lookup"><span data-stu-id="4ce45-109">Describes the process and rules by which records are generated for XML Bulk Load.</span></span>  
  
 [<span data-ttu-id="4ce45-110">Интерпретация аннотации &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="4ce45-110">Annotation Interpretation &#40;SQLXML 4.0&#41;</span></span>](annotation-interpretation-sqlxml-4-0.md)  
 <span data-ttu-id="4ce45-111">Содержит описание того, как массовая загрузка XML интерпретирует заметки в схемах XSD и XDR.</span><span class="sxs-lookup"><span data-stu-id="4ce45-111">Describes how XML Bulk Load interprets annotations in XSD and XDR schemas.</span></span>  
  
 [<span data-ttu-id="4ce45-112">SQL Server модели объектов XML для групповой загрузки &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="4ce45-112">SQL Server XML Bulk Load Object Model &#40;SQLXML 4.0&#41;</span></span>](sql-server-xml-bulk-load-object-model-sqlxml-4-0.md)  
 <span data-ttu-id="4ce45-113">Описывает объект Склксмлбулклоад, его методы и свойства.</span><span class="sxs-lookup"><span data-stu-id="4ce45-113">Describes the SQLXMLBulkLoad object and its methods and properties.</span></span>  
  
 [<span data-ttu-id="4ce45-114">Примеры групповой загрузки XML &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="4ce45-114">XML Bulk Load Examples &#40;SQLXML 4.0&#41;</span></span>](xml-bulk-load-examples-sqlxml-4-0.md)  
 <span data-ttu-id="4ce45-115">Содержит пример кода, использующего массовую загрузку XML.</span><span class="sxs-lookup"><span data-stu-id="4ce45-115">Provides example code that uses XML Bulk Load.</span></span>  
  
 [<span data-ttu-id="4ce45-116">Типы данных и поведение при выполнении групповой загрузки XML &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="4ce45-116">Data Types and XML Bulk Load Behavior &#40;SQLXML 4.0&#41;</span></span>](data-types-and-xml-bulk-load-behavior-sqlxml-4-0.md)  
 <span data-ttu-id="4ce45-117">Содержит описание поведения массовой загрузки XML при различных типах в XSD и XDR.</span><span class="sxs-lookup"><span data-stu-id="4ce45-117">Describes XML Bulk Load Behavior with different types in XSD and XDR.</span></span>  
  
 [<span data-ttu-id="4ce45-118">Рекомендации и ограничения для групповой загрузки XML &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="4ce45-118">Guidelines and Limitations of XML Bulk Load &#40;SQLXML 4.0&#41;</span></span>](guidelines-and-limitations-of-xml-bulk-load-sqlxml-4-0.md)  
 <span data-ttu-id="4ce45-119">Содержит список проблем, которые необходимо учитывать при работе с массовой загрузкой XML.</span><span class="sxs-lookup"><span data-stu-id="4ce45-119">Lists some issues to be aware of when working with XML Bulk Load.</span></span>  
  
  
