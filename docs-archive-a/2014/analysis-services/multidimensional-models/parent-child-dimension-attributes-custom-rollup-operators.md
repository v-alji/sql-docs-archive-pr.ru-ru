---
title: Операторы пользовательской свертки в измерениях «родители-потомки» | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- child rollup operations
- UnaryOperatorColumn property
- custom rollup operators [Analysis Services]
- unary operators
- parent-child dimensions [Analysis Services]
ms.assetid: a3ddd9fc-5fa3-4227-9322-8c45a5b5c2c3
author: minewiskan
ms.author: owend
ms.openlocfilehash: db12ccc6703ee4863dd3b6bd598d2317b54fce6a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665626"
---
# <a name="custom-rollup-operators-in-parent-child-dimensions"></a><span data-ttu-id="5d127-102">Операторы пользовательской свертки в измерениях типа «родители-потомки»</span><span class="sxs-lookup"><span data-stu-id="5d127-102">Custom Rollup Operators in Parent-Child Dimensions</span></span>
  <span data-ttu-id="5d127-103">Операторы пользовательской свертки предоставляют простой способ контроля свертки значений элементов в значения родительских элементов в иерархии типа «родители-потомки».</span><span class="sxs-lookup"><span data-stu-id="5d127-103">Custom rollup operators provide a simple way to control how member values are rolled up into parent values in a parent-child hierarchy.</span></span> <span data-ttu-id="5d127-104">В измерении, содержащем связь типа «родители-потомки», указывается столбец, содержащий унарные операторы, указывающие свертку для всех невычисляемых элементов родительского атрибута.</span><span class="sxs-lookup"><span data-stu-id="5d127-104">In a dimension containing a parent-child relationship, you specify a column that contains unary operators that specify rollup for all noncalculated members of the parent attribute.</span></span> <span data-ttu-id="5d127-105">Унарный оператор применяется к элементам каждый раз, когда оцениваются значения родительских элементов.</span><span class="sxs-lookup"><span data-stu-id="5d127-105">The unary operator is applied to members whenever the values of the parent members are evaluated.</span></span>  
  
 <span data-ttu-id="5d127-106">Унарные операторы хранятся в столбце, определенном свойством `UnaryOperatorColumn` родительского атрибута, и они применяются к каждому элементу атрибута.</span><span class="sxs-lookup"><span data-stu-id="5d127-106">The unary operators are stored in column defined by the `UnaryOperatorColumn` property of the parent attribute, and they are applied to each member of the attribute.</span></span> <span data-ttu-id="5d127-107">Столбец, заданный этим свойством, может находиться либо в таблице измерения, либо в таблице, связанной с таблицей измерения внешним ключом в таблице измерения.</span><span class="sxs-lookup"><span data-stu-id="5d127-107">The column specified by this property can reside either in the dimension table or in a table related to the dimension table by a foreign key in the dimension table.</span></span>  
  
 <span data-ttu-id="5d127-108">Операторы пользовательской свертки предоставляют функционал, аналогичный, но более простой по сравнению с нестандартными формулами элементов.</span><span class="sxs-lookup"><span data-stu-id="5d127-108">Custom rollup operators provide functionality similar to, but more simplified than, custom member formulas.</span></span> <span data-ttu-id="5d127-109">В нестандартной формуле элемента используются многомерные выражения для определения способа свертки элементов.</span><span class="sxs-lookup"><span data-stu-id="5d127-109">A custom member formula uses Multidimensional Expressions (MDX) expressions to determine how the members are rolled up.</span></span> <span data-ttu-id="5d127-110">В противоположность этому оператор пользовательской свертки использует простой унарный оператор для определения того, как значение элемента влияет на «родительский» элемент.</span><span class="sxs-lookup"><span data-stu-id="5d127-110">In contrast, a custom rollup operator uses a simple unary operator to determine how the value of a member affects the parent.</span></span> <span data-ttu-id="5d127-111">Нестандартные формулы элементов предыдущего уровня имеют более высокий приоритет по сравнению с оператором пользовательской свертки уровня.</span><span class="sxs-lookup"><span data-stu-id="5d127-111">Custom member formulas of the preceding level in a dimension override a level's custom rollup operator.</span></span>  
  
## <a name="custom-rollup-precedence"></a><span data-ttu-id="5d127-112">Приоритет пользовательской свертки</span><span class="sxs-lookup"><span data-stu-id="5d127-112">Custom Rollup Precedence</span></span>  
 <span data-ttu-id="5d127-113">С точки зрения приоритетов, операторы пользовательской свертки атрибута источника для уровня в иерархии имеют более высокий приоритет, чем нестандартные формулы элементов предыдущего уровня.</span><span class="sxs-lookup"><span data-stu-id="5d127-113">In terms of precedence, the custom rollup operators of the source attribute for a level in a hierarchy override the custom member formulas of the previous level.</span></span> <span data-ttu-id="5d127-114">Однако нестандартные формулы элементов предыдущего уровня имеют более высокий приоритет, чем операторы пользовательской свертки уровня.</span><span class="sxs-lookup"><span data-stu-id="5d127-114">However, the custom member formulas of the preceding level override the custom rollup operators of a level.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d127-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="5d127-115">See Also</span></span>  
 <span data-ttu-id="5d127-116">[Определение нестандартных формул элементов](attribute-properties-define-custom-member-formulas.md) </span><span class="sxs-lookup"><span data-stu-id="5d127-116">[Define Custom Member Formulas](attribute-properties-define-custom-member-formulas.md) </span></span>  
 [<span data-ttu-id="5d127-117">Унарные операторы в измерениях типа «родители-потомки»</span><span class="sxs-lookup"><span data-stu-id="5d127-117">Unary Operators in Parent-Child Dimensions</span></span>](parent-child-dimension-attributes-unary-operators.md)  
  
  