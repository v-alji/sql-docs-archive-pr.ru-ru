---
title: Данные XML (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XML [SQL Server]
- XML [SQL Server], about XML
ms.assetid: 6a1793c9-9856-485c-aac5-88fda62f61a8
author: rothja
ms.author: jroth
ms.openlocfilehash: 48ddec1de8492c86aecfd80ea960c4a01673c24f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656263"
---
# <a name="xml-data-sql-server"></a><span data-ttu-id="a4336-102">XML-данные (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a4336-102">XML Data (SQL Server)</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a4336-103">предоставляет эффективную платформу для разработки многофункциональных приложений для управления частично структурированными данными.</span><span class="sxs-lookup"><span data-stu-id="a4336-103">provides a powerful platform for developing rich applications for semi-structured data management.</span></span> <span data-ttu-id="a4336-104">Поддержка языка XML встроена во все компоненты [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и включает следующее:</span><span class="sxs-lookup"><span data-stu-id="a4336-104">Support for XML is integrated into all the components in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and includes the following:</span></span>  
  
-   <span data-ttu-id="a4336-105">Тип данных `xml`.</span><span class="sxs-lookup"><span data-stu-id="a4336-105">The `xml` data type.</span></span> <span data-ttu-id="a4336-106">Значения XML можно естественным образом хранить в столбце типа `xml`, который можно типизировать в соответствии с коллекцией схем XML или оставить нетипизированным.</span><span class="sxs-lookup"><span data-stu-id="a4336-106">XML values can be stored natively in an `xml` data type column that can be typed according to a collection of XML schemas, or left untyped.</span></span> <span data-ttu-id="a4336-107">XML-столбец можно индексировать.</span><span class="sxs-lookup"><span data-stu-id="a4336-107">You can index the XML column.</span></span>  
  
-   <span data-ttu-id="a4336-108">возможность указывать запросы XQuery к XML-данным, хранящимся в столбцах и переменных типа `xml`;</span><span class="sxs-lookup"><span data-stu-id="a4336-108">The ability to specify an XQuery query against XML data stored in columns and variables of the `xml` type.</span></span>  
  
-   <span data-ttu-id="a4336-109">Расширения в инструкции OPENROWSET, позволяющие выполнять массовую загрузку XML-данных.</span><span class="sxs-lookup"><span data-stu-id="a4336-109">Enhancements to OPENROWSET to allow bulk loading of XML data.</span></span>  
  
-   <span data-ttu-id="a4336-110">Предложение FOR XML для получения реляционных данных в формате XML.</span><span class="sxs-lookup"><span data-stu-id="a4336-110">The FOR XML clause, to retrieve relational data in XML format.</span></span>  
  
-   <span data-ttu-id="a4336-111">Функция OPENXML для получения данных XML в реляционном формате.</span><span class="sxs-lookup"><span data-stu-id="a4336-111">The OPENXML function, to retrieve XML data in relational format.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a4336-112">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="a4336-112">In This Section</span></span>  
 [<span data-ttu-id="a4336-113">Столбцы и типы данных XML (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a4336-113">XML Data Type and Columns &#40;SQL Server&#41;</span></span>](xml-data-type-and-columns-sql-server.md)  
 [<span data-ttu-id="a4336-114">XML-индексы (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a4336-114">XML Indexes &#40;SQL Server&#41;</span></span>](xml-indexes-sql-server.md)  
 [<span data-ttu-id="a4336-115">Коллекции XML-схем (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a4336-115">XML Schema Collections &#40;SQL Server&#41;</span></span>](xml-schema-collections-sql-server.md)  
 [<span data-ttu-id="a4336-116">FOR XML (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a4336-116">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
 [<span data-ttu-id="a4336-117">OPENXML (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="a4336-117">OPENXML &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/openxml-transact-sql)  
  
## <a name="related-content"></a><span data-ttu-id="a4336-118">См. также</span><span class="sxs-lookup"><span data-stu-id="a4336-118">Related Content</span></span>  
 [<span data-ttu-id="a4336-119">Примеры массового импорта и экспорта XML-документов (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a4336-119">Examples of Bulk Import and Export of XML Documents &#40;SQL Server&#41;</span></span>](../import-export/examples-of-bulk-import-and-export-of-xml-documents-sql-server.md)  
 [<span data-ttu-id="a4336-120">Справочник по языку XQuery (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a4336-120">XQuery Language Reference &#40;SQL Server&#41;</span></span>](/sql/xquery/xquery-language-reference-sql-server)  
  
