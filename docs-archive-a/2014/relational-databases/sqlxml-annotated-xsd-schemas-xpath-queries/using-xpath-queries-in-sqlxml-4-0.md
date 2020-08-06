---
title: Использование запросов XPath в SQLXML 4,0 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML]
- annotated XSD schemas, XPath queries
- queries [SQLXML], XPath
- XML views [SQLXML]
ms.assetid: 7814d099-81ec-4fb8-894a-729cdbb5015a
author: rothja
ms.author: jroth
ms.openlocfilehash: 80d82513b22d2a50aedb37955a210dd33746db86
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665953"
---
# <a name="using-xpath-queries-in-sqlxml-40"></a><span data-ttu-id="1249b-102">Использование запросов XPath в SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="1249b-102">Using XPath Queries in SQLXML 4.0</span></span>
  <span data-ttu-id="1249b-103">Поддержка Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] аннотированных схем XSD позволяет создавать XML-представления реляционных данных, хранящихся в базе данных.</span><span class="sxs-lookup"><span data-stu-id="1249b-103">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] support for annotated XSD schemas allows you to create XML views of the relational data stored in the database.</span></span> <span data-ttu-id="1249b-104">Можно использовать подмножество языка XPath для запроса XML-представлений, созданных аннотированными схемами XSD.</span><span class="sxs-lookup"><span data-stu-id="1249b-104">You can use a subset of the XPath language to query the XML views created by an annotated XSD schema.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1249b-105">Чтобы получить представление о запросах XPath в SQLXML 4.0, необходим опыт работы с XML-представлениями и другими связанными основными понятиями — шаблонами и схемами сопоставления.</span><span class="sxs-lookup"><span data-stu-id="1249b-105">To understand XPath queries in SQLXML 4.0, you must be familiar with XML views and related concepts such as templates and mapping schema.</span></span> <span data-ttu-id="1249b-106">Дополнительные сведения см. [в разделе Введение в схемы XSD с Заметками &#40;SQLXML 4,0&#41;](../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="1249b-106">For more information, see [Introduction to Annotated XSD Schemas &#40;SQLXML 4.0&#41;](../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md).</span></span> <span data-ttu-id="1249b-107">Дополнительные сведения о XPath см. в стандарте XPath, определенном консорциум W3C (W3C) по адресу http://www.w3.org/TR/xpath .</span><span class="sxs-lookup"><span data-stu-id="1249b-107">For more information about XPath, see the XPath standard defined by the World Wide Web Consortium (W3C) at http://www.w3.org/TR/xpath.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1249b-108">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="1249b-108">In This Section</span></span>  
 [<span data-ttu-id="1249b-109">Общие сведения об использовании запросов XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="1249b-109">Introduction to Using XPath Queries &#40;SQLXML 4.0&#41;</span></span>](introduction-to-using-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="1249b-110">Содержит вводные сведения о запросах XPath в SQLXML 4.0 (в том числе поддерживаемые и неподдерживаемые возможности из спецификации XPath консорциума W3C).</span><span class="sxs-lookup"><span data-stu-id="1249b-110">Provides introductory information about XPath queries in SQLXML 4.0, including supported and unsupported functionality from the W3C XPath specification.</span></span>  
  
 [<span data-ttu-id="1249b-111">Указание пути расположения &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="1249b-111">Specifying a Location Path &#40;SQLXML 4.0&#41;</span></span>](location-path/specifying-a-location-path-sqlxml-4-0.md)  
 <span data-ttu-id="1249b-112">Содержит способы указания путей доступа в запросах XPath.</span><span class="sxs-lookup"><span data-stu-id="1249b-112">Describes how to specify location paths in XPath queries.</span></span>  
  
 [<span data-ttu-id="1249b-113">Примеры запросов XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="1249b-113">Sample XPath Queries &#40;SQLXML 4.0&#41;</span></span>](samples/sample-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="1249b-114">Содержит образцы запросов XPath для SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="1249b-114">Provides sample XPath queries for SQLXML 4.0.</span></span>  
  
 [<span data-ttu-id="1249b-115">Типы данных XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="1249b-115">XPath Data Types &#40;SQLXML 4.0&#41;</span></span>](xpath-data-types-sqlxml-4-0.md)  
 <span data-ttu-id="1249b-116">Содержит описание типов данных XPath, которые значительно отличаются от типов данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и XSD.</span><span class="sxs-lookup"><span data-stu-id="1249b-116">Describes XPath data types, which are significantly different from those of both [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and XSD.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1249b-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="1249b-117">See Also</span></span>  
 [<span data-ttu-id="1249b-118">Форматирование XML на стороне клиента &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="1249b-118">Client-side XML Formatting &#40;SQLXML 4.0&#41;</span></span>](../sqlxml/formatting/client-side-xml-formatting-sqlxml-4-0.md)  
  
  
