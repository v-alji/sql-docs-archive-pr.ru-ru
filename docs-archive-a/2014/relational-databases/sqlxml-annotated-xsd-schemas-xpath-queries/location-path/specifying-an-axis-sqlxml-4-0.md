---
title: Указание оси (SQLXML 4,0) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], axes
- XPath queries [SQLXML], location paths
- self axis
- attribute axis [SQLXML]
- axis [SQLXML]
- child axis
- parent axis
- location path for XPath query
- axes [SQLXML]
ms.assetid: 65631795-3389-40cf-90ea-85e9438956c5
author: rothja
ms.author: jroth
ms.openlocfilehash: 5e43281fe31d323a7eea19e749b80b59458752b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664803"
---
# <a name="specifying-an-axis-sqlxml-40"></a><span data-ttu-id="d79a8-102">Определение оси (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="d79a8-102">Specifying an Axis (SQLXML 4.0)</span></span>
    
-   <span data-ttu-id="d79a8-103">Ось определяет древовидную связь между узлами, которые выбираются шагом доступа, и контекстными узлами.</span><span class="sxs-lookup"><span data-stu-id="d79a8-103">The axis specifies the tree relationship between the nodes selected by the location step and the context node.</span></span> <span data-ttu-id="d79a8-104">Поддерживаются следующие оси:`child`</span><span class="sxs-lookup"><span data-stu-id="d79a8-104">The following axes are supported:  `child`</span></span>  
  
     <span data-ttu-id="d79a8-105">Содержит дочерний элемент узла контекста.</span><span class="sxs-lookup"><span data-stu-id="d79a8-105">Contains the child of the context node.</span></span>  
  
     <span data-ttu-id="d79a8-106">Следующее выражение XPath (путь расположения) выбирает из текущего контекстного узла все **\<Customer>** дочерние элементы.</span><span class="sxs-lookup"><span data-stu-id="d79a8-106">The following XPath expression (location path) selects from the current context node all the **\<Customer>** children:</span></span>  
  
    ```  
    child::Customer  
    ```  
  
     <span data-ttu-id="d79a8-107">В следующем запросе XPath `child` является осью.</span><span class="sxs-lookup"><span data-stu-id="d79a8-107">In the following XPath query, `child` is the axis.</span></span> <span data-ttu-id="d79a8-108">`Customer` является проверкой узла.</span><span class="sxs-lookup"><span data-stu-id="d79a8-108">`Customer` is the node test.</span></span>  
  
-   `parent`  
  
     <span data-ttu-id="d79a8-109">Содержит родительский элемент контекстного узла.</span><span class="sxs-lookup"><span data-stu-id="d79a8-109">Contains the parent of the context node.</span></span>  
  
     <span data-ttu-id="d79a8-110">Следующее выражение XPath выбирает все **\<Customer>** родительские **\<Order>** элементы дочерних элементов:</span><span class="sxs-lookup"><span data-stu-id="d79a8-110">The following XPath expression selects all the **\<Customer>** parents of the **\<Order>** children:</span></span>  
  
    ```  
    child::Customer/child::Order[parent::Customer/@customerID="ALFKI"]  
    ```  
  
     <span data-ttu-id="d79a8-111">Это аналогично указанию `child::Customer`.</span><span class="sxs-lookup"><span data-stu-id="d79a8-111">This is the same as specifying `child::Customer`.</span></span> <span data-ttu-id="d79a8-112">В данном запросе XPath `child` и `parent` являются осями.</span><span class="sxs-lookup"><span data-stu-id="d79a8-112">In this XPath query, `child` and `parent` are the axes.</span></span> <span data-ttu-id="d79a8-113">`Customer` и `Order` являются проверками узла.</span><span class="sxs-lookup"><span data-stu-id="d79a8-113">`Customer` and `Order` are the node tests.</span></span>  
  
-   `attribute`  
  
     <span data-ttu-id="d79a8-114">Содержит атрибут узла контекста.</span><span class="sxs-lookup"><span data-stu-id="d79a8-114">Contains the attribute of the context node.</span></span>  
  
     <span data-ttu-id="d79a8-115">Следующее выражение XPath выбирает атрибут **CustomerID** узла контекста:</span><span class="sxs-lookup"><span data-stu-id="d79a8-115">The following XPath expression selects the **CustomerID** attribute of the context node:</span></span>  
  
    ```  
    attribute::CustomerID  
    ```  
  
-   `self`  
  
     <span data-ttu-id="d79a8-116">Содержит сам узел контекста.</span><span class="sxs-lookup"><span data-stu-id="d79a8-116">Contains the context node itself.</span></span>  
  
     <span data-ttu-id="d79a8-117">Следующее выражение XPath выбирает текущий узел, если он является **\<Order>** узлом:</span><span class="sxs-lookup"><span data-stu-id="d79a8-117">The following XPath expression selects the current node if it is the **\<Order>** node:</span></span>  
  
    ```  
    self::Order  
    ```  
  
     <span data-ttu-id="d79a8-118">В следующем запросе XPath `self` является осью, а `Order` — проверкой узла.</span><span class="sxs-lookup"><span data-stu-id="d79a8-118">In this XPath query, `self` is the axis and `Order` is the node test.</span></span>  
  
  
