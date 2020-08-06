---
title: Примеры запросов XPath (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- examples [SQLXML], XPath
- sample applications [SQLXML]
- sample XPath queries [SQLXML]
- mapping schema [SQLXML], queries
- XPath queries [SQLXML], samples
ms.assetid: 1595c2d4-0e9c-4969-84c8-a793a32df57d
author: rothja
ms.author: jroth
ms.openlocfilehash: 08ed32433e9bed4cc1542d6700ad73dc96f3c2dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655006"
---
# <a name="sample-xpath-queries-sqlxml-40"></a><span data-ttu-id="7482a-102">Образцы запросов XPath (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="7482a-102">Sample XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="7482a-103">В этом разделе содержатся образцы запросов XPath для SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="7482a-103">This section provides examples of XPath queries for SQLXML 4.0.</span></span> <span data-ttu-id="7482a-104">Для наглядности эти примеры запросов XPath задаются в шаблоне, выполняемом с помощью ADO.</span><span class="sxs-lookup"><span data-stu-id="7482a-104">For illustration purposes, these example XPath queries are specified in a template executed using ADO.</span></span> <span data-ttu-id="7482a-105">Поэтому необходимо использовать файл схемы сопоставления SampleSchema1.xml, который также содержится в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="7482a-105">Therefore, you must use a mapping schema file, SampleSchema1.xml, which is also provided in this section.</span></span> <span data-ttu-id="7482a-106">Сохраните этот файл в каталоге, где хранятся шаблоны.</span><span class="sxs-lookup"><span data-stu-id="7482a-106">Save this file in the directory where your templates are stored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7482a-107">Образцы запросов в этом разделе сгруппированы по типу операций XPath, выполняемых в запросе.</span><span class="sxs-lookup"><span data-stu-id="7482a-107">The sample queries in this section are grouped by the type of XPath operation that is performed by the query.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7482a-108">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="7482a-108">In This Section</span></span>  
 [<span data-ttu-id="7482a-109">Пример схемы XSD с заметками для примеров XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="7482a-109">Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;</span></span>](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md)  
 <span data-ttu-id="7482a-110">Используйте этот файл с примерами запросов XPath, приведенными в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="7482a-110">Use this file with the XPath query examples provided in this section.</span></span>  
  
 [<span data-ttu-id="7482a-111">Указание осей в запросах XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="7482a-111">Specifying Axes in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-axes-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="7482a-112">Показывают, как задаются оси в запросах XPath.</span><span class="sxs-lookup"><span data-stu-id="7482a-112">Illustrates how axes are specified in XPath queries.</span></span>  
  
 [<span data-ttu-id="7482a-113">Указание предикатов с логическими значениями в запросах XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="7482a-113">Specifying Boolean-Valued Predicates in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-boolean-valued-predicates-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="7482a-114">Показывает, как задаются оси в запросах XPath.</span><span class="sxs-lookup"><span data-stu-id="7482a-114">Illustrates how Boolean-valued predicates are specified in XPath queries.</span></span>  
  
 [<span data-ttu-id="7482a-115">Указание реляционных операторов в запросах XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="7482a-115">Specifying Relational Operators in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-relational-operators-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="7482a-116">Показывает, как задаются реляционные операторы в запросах XPath.</span><span class="sxs-lookup"><span data-stu-id="7482a-116">Illustrates how relational operators are specified in XPath queries.</span></span>  
  
 [<span data-ttu-id="7482a-117">Указание арифметических операторов в запросах XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="7482a-117">Specifying Arithmetic Operators in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-arithmetic-operators-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="7482a-118">Показывает, как задаются арифметические операторы в запросах XPath.</span><span class="sxs-lookup"><span data-stu-id="7482a-118">Illustrates how arithmetic operators are specified in XPath queries.</span></span>  
  
 [<span data-ttu-id="7482a-119">Указание явных функций преобразования в запросах XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="7482a-119">Specifying Explicit Conversion Functions in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-explicit-conversion-functions-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="7482a-120">Показывает, как задаются функции явного преобразования в запросах XPath.</span><span class="sxs-lookup"><span data-stu-id="7482a-120">Illustrates how explicit conversion functions are specified in XPath queries.</span></span>  
  
 [<span data-ttu-id="7482a-121">Указание логических операторов в запросах XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="7482a-121">Specifying Boolean Operators in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-boolean-operators-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="7482a-122">Показывает, как задаются логические операторы в запросах XPath.</span><span class="sxs-lookup"><span data-stu-id="7482a-122">Illustrates how Boolean operators are specified in XPath queries.</span></span>  
  
 [<span data-ttu-id="7482a-123">Указание логических функций в запросах XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="7482a-123">Specifying Boolean Functions in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-boolean-functions-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="7482a-124">Показывает, как задаются логические функции в запросах XPath.</span><span class="sxs-lookup"><span data-stu-id="7482a-124">Illustrates how Boolean functions are specified in XPath queries.</span></span>  
  
 [<span data-ttu-id="7482a-125">Указание переменных XPath в запросах XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="7482a-125">Specifying XPath Variables in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-xpath-variables-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="7482a-126">Показывают, как задаются переменные XPath в запросах XPath.</span><span class="sxs-lookup"><span data-stu-id="7482a-126">Illustrates how XPath variables are specified in XPath queries.</span></span>  
  
  
