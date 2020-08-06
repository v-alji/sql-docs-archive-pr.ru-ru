---
title: Указание проверки узла в пути расположения (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], location paths
- principal node types [SQLXML]
- node tests [SQLXML]
- location path for XPath query
ms.assetid: f46c30bf-1e24-4435-9ac2-f8ba43a8ff94
author: rothja
ms.author: jroth
ms.openlocfilehash: 9d8535154f4b481c8a47bfdb8b801e3136a1ef0f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664805"
---
# <a name="specifying-a-node-test-in-the-location-path-sqlxml-40"></a><span data-ttu-id="3b723-102">Задание проверки узла в пути доступа (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="3b723-102">Specifying a Node Test in the Location Path (SQLXML 4.0)</span></span>
  <span data-ttu-id="3b723-103">Проверка узла задает тип узла, выбранного на шаге доступа.</span><span class="sxs-lookup"><span data-stu-id="3b723-103">A node test specifies the node type selected by the location step.</span></span> <span data-ttu-id="3b723-104">Каждая ось (`child`, `parent`, `attribute` или `self`) имеет тип узла участника.</span><span class="sxs-lookup"><span data-stu-id="3b723-104">Every axis (`child`, `parent`, `attribute`, or `self`) has a principal node type.</span></span> <span data-ttu-id="3b723-105">Для `attribute` оси тип основного узла — **\<attribute>** .</span><span class="sxs-lookup"><span data-stu-id="3b723-105">For the `attribute` axis, the principal node type is **\<attribute>**.</span></span> <span data-ttu-id="3b723-106">Для `parent` осей, `child` и `self` Тип основного узла — **\<element>** .</span><span class="sxs-lookup"><span data-stu-id="3b723-106">For the `parent`, `child`, and `self` axes, the principal node type is **\<element>**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3b723-107">Шаблон проверки узла \* (например `child::*`) не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="3b723-107">The wildcard node test \* (for example, `child::*`) is not supported.</span></span>  
  
## <a name="node-test-example-1"></a><span data-ttu-id="3b723-108">Проверка узла: Пример 1</span><span class="sxs-lookup"><span data-stu-id="3b723-108">Node Test: Example 1</span></span>  
 <span data-ttu-id="3b723-109">Путь к расположению `child::Customer` выбирает **\<Customer>** дочерние элементы узла контекста.</span><span class="sxs-lookup"><span data-stu-id="3b723-109">The location path `child::Customer` selects **\<Customer>** element children of the context node.</span></span>  
  
 <span data-ttu-id="3b723-110">В следующем примере элемент `child` является осью, а `Customer` является проверкой узла.</span><span class="sxs-lookup"><span data-stu-id="3b723-110">In this example, `child` is the axis and `Customer` is the node test.</span></span> <span data-ttu-id="3b723-111">Тип основного узла для `child` оси — **\<element>** .</span><span class="sxs-lookup"><span data-stu-id="3b723-111">The principal node type for the `child` axis is **\<element>**.</span></span> <span data-ttu-id="3b723-112">Поэтому проверка узла имеет значение TRUE, если **\<Customer>** узел является **\<element>** узлом.</span><span class="sxs-lookup"><span data-stu-id="3b723-112">Therefore, the node test is TRUE if the **\<Customer>** node is an **\<element>** node.</span></span> <span data-ttu-id="3b723-113">Если узел контекста не имеет **\<Customer>** дочерних элементов, возвращается пустой набор узлов.</span><span class="sxs-lookup"><span data-stu-id="3b723-113">If the context node has no **\<Customer>** children, an empty set of nodes is returned.</span></span>  
  
## <a name="node-test-example-2"></a><span data-ttu-id="3b723-114">Проверка узла: пример 2</span><span class="sxs-lookup"><span data-stu-id="3b723-114">Node Test: Example 2</span></span>  
 <span data-ttu-id="3b723-115">Путь к расположению `attribute::CustomerID` выбирает атрибут **CustomerID** узла контекста.</span><span class="sxs-lookup"><span data-stu-id="3b723-115">The location path `attribute::CustomerID` selects the **CustomerID** attribute of the context node.</span></span>  
  
 <span data-ttu-id="3b723-116">В этом примере элемент `attribute` является осью, а `CustomerID` является проверкой узла.</span><span class="sxs-lookup"><span data-stu-id="3b723-116">In the example, `attribute` is the axis and `CustomerID` is the node test.</span></span> <span data-ttu-id="3b723-117">Тип основного узла `attribute` оси — **\<attribute>** .</span><span class="sxs-lookup"><span data-stu-id="3b723-117">The principal node type of the `attribute` axis is **\<attribute>**.</span></span> <span data-ttu-id="3b723-118">Поэтому проверка узла имеет значение TRUE, если **CustomerID** является **\<attribute>** узлом.</span><span class="sxs-lookup"><span data-stu-id="3b723-118">Therefore, the node test is TRUE if **CustomerID** is an **\<attribute>** node.</span></span> <span data-ttu-id="3b723-119">Если узел контекста не имеет **CustomerID**, возвращается пустой набор узлов.</span><span class="sxs-lookup"><span data-stu-id="3b723-119">If the context node has no **CustomerID**, an empty set of nodes is returned.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3b723-120">В этой реализации XPath, если шаг расположения ссылается на **\<element>** или **\<attribute>** тип, который не объявлен в схеме, создается ошибка.</span><span class="sxs-lookup"><span data-stu-id="3b723-120">In this implementation of XPath, if a location step refers to an **\<element>** or an **\<attribute>** type that is not declared in the schema, an error is generated.</span></span> <span data-ttu-id="3b723-121">Это отличается от реализации XPath в MSXML, где возвращается пустое множество узлов.</span><span class="sxs-lookup"><span data-stu-id="3b723-121">This is different from the implementation of XPath in MSXML, which returns an empty node set.</span></span>  
  
## <a name="abbreviated-syntax-for-the-axes"></a><span data-ttu-id="3b723-122">Сокращенный синтаксис осей</span><span class="sxs-lookup"><span data-stu-id="3b723-122">Abbreviated Syntax for the Axes</span></span>  
 <span data-ttu-id="3b723-123">Поддерживается следующий сокращенный синтаксис пути доступа.</span><span class="sxs-lookup"><span data-stu-id="3b723-123">The following abbreviated syntax for the location path is supported:</span></span>  
  
-   <span data-ttu-id="3b723-124">`attribute::` можно сократить до `@`.</span><span class="sxs-lookup"><span data-stu-id="3b723-124">`attribute::` can be abbreviated to `@`.</span></span>  
  
     <span data-ttu-id="3b723-125">Путь доступа `Customer[@CustomerID="ALFKI"]` аналогичен выражению `child::Customer[attribute::CustomerID="ALFKI"]`.</span><span class="sxs-lookup"><span data-stu-id="3b723-125">The location path `Customer[@CustomerID="ALFKI"]` is the same as `child::Customer[attribute::CustomerID="ALFKI"]`.</span></span>  
  
-   <span data-ttu-id="3b723-126">`child::` можно исключить из шага определения расположения данных.</span><span class="sxs-lookup"><span data-stu-id="3b723-126">`child::` can be omitted from a location step.</span></span>  
  
     <span data-ttu-id="3b723-127">Таким образом, ось `child` является осью по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3b723-127">Thus, `child` is the default axis.</span></span> <span data-ttu-id="3b723-128">Путь доступа `Customer/Order` аналогичен выражению `child::Customer/child::Order`.</span><span class="sxs-lookup"><span data-stu-id="3b723-128">The location path `Customer/Order` is the same as `child::Customer/child::Order`.</span></span>  
  
-   <span data-ttu-id="3b723-129">`self::node()` можно сократить до одной точки (.), а `parent::node()` можно сократить до двух точек (..).</span><span class="sxs-lookup"><span data-stu-id="3b723-129">`self::node()` can be abbreviated to one period (.), and `parent::node()` can be abbreviated to two periods (..).</span></span>  
  
  
