---
title: Установка контекста куба в запросе (многомерные выражения) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- cubes [Analysis Services], MDX
- MDX [Analysis Services], cube context
- SELECT statement [MDX]
- Multidimensional Expressions [Analysis Services], cube context
- queries [MDX], cube context
ms.assetid: 79d6a1e8-2825-4eb9-97df-5071aecae8f0
author: minewiskan
ms.author: owend
ms.openlocfilehash: 72ae6e19f879651feb47841d70b444e9f845c74e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727394"
---
# <a name="establishing-cube-context-in-a-query-mdx"></a><span data-ttu-id="a2c70-102">Определение контекста куба в запросе (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="a2c70-102">Establishing Cube Context in a Query (MDX)</span></span>
  <span data-ttu-id="a2c70-103">Каждый запрос многомерных выражений выполняется в заданном контексте куба.</span><span class="sxs-lookup"><span data-stu-id="a2c70-103">Every MDX query runs within a specified cube context.</span></span> <span data-ttu-id="a2c70-104">Контекст определяет элементы, вычисляемые в выражениях запроса.</span><span class="sxs-lookup"><span data-stu-id="a2c70-104">This context defines the members that are evaluated by the expressions within the query.</span></span>  
  
 <span data-ttu-id="a2c70-105">В инструкции SELECT контекст куба определяется с помощью предложения FROM.</span><span class="sxs-lookup"><span data-stu-id="a2c70-105">In the SELECT statement, the FROM clause determines the cube context.</span></span> <span data-ttu-id="a2c70-106">В качестве контекста может выступать весь куб или его вложенный куб.</span><span class="sxs-lookup"><span data-stu-id="a2c70-106">This context can be the whole cube or just a subcube from that cube.</span></span> <span data-ttu-id="a2c70-107">Указав контекст куба при помощи предложения FROM, можно расширять или ограничивать его при помощи дополнительных функций.</span><span class="sxs-lookup"><span data-stu-id="a2c70-107">Having specified cube context through the FROM clause, you can use additional functions to expand or restrict that context.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a2c70-108">Инструкции SCOPE и CALCULATE также позволяют управлять контекстом куба в скрипте многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="a2c70-108">The SCOPE and CALCULATE statements also let you manage cube context from within an MDX script.</span></span> <span data-ttu-id="a2c70-109">Дополнительные сведения см. в статье [Основные принципы создания скриптов многомерных выражений (службы Analysis Services)](mdx-scripting-fundamentals-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="a2c70-109">For more information, see [MDX Scripting Fundamentals &#40;Analysis Services&#41;](mdx-scripting-fundamentals-analysis-services.md).</span></span>  
  
## <a name="from-clause-syntax"></a><span data-ttu-id="a2c70-110">Синтаксис предложения FROM</span><span class="sxs-lookup"><span data-stu-id="a2c70-110">FROM Clause Syntax</span></span>  
 <span data-ttu-id="a2c70-111">Предложение FROM имеет следующий синтаксис.</span><span class="sxs-lookup"><span data-stu-id="a2c70-111">The following syntax describes the FROM clause:</span></span>  
  
```  
<SELECT subcube clause> ::=  
   Cube_Identifier |   
   (SELECT [  
      * |   
      ( <SELECT query axis clause> [ , <SELECT query axis clause> ... ] ) ]   
   FROM <SELECT subcube clause> <SELECT slicer axis clause> )  
```  
  
 <span data-ttu-id="a2c70-112">Обратите внимание на то, что в этом синтаксисе куб или вложенный куб, над которым выполняется инструкция SELECT, описывается предложением `<SELECT subcube clause>` .</span><span class="sxs-lookup"><span data-stu-id="a2c70-112">In this syntax, notice that it is the `<SELECT subcube clause>` clause that describes the cube or subcube on which the SELECT statement is executed.</span></span>  
  
 <span data-ttu-id="a2c70-113">Простым примером использования предложения FROM является запрос, обрабатывающий весь образец куба Adventure Works.</span><span class="sxs-lookup"><span data-stu-id="a2c70-113">A simple example of a FROM clause would be one that runs against the entire Adventure Works sample cube.</span></span> <span data-ttu-id="a2c70-114">Предложение FROM будет иметь следующий вид:</span><span class="sxs-lookup"><span data-stu-id="a2c70-114">Such a FROM clause would have the following format:</span></span>  
  
```  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="a2c70-115">Дополнительные сведения о предложении FROM в инструкции SELECT многомерных выражений см. в разделе [Инструкция SELECT (многомерные выражения)](/sql/mdx/mdx-data-manipulation-select).</span><span class="sxs-lookup"><span data-stu-id="a2c70-115">For more information about the FROM clause in the MDX SELECT statement, see [SELECT Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select).</span></span>  
  
## <a name="refining-the-context"></a><span data-ttu-id="a2c70-116">Уточнение контекста</span><span class="sxs-lookup"><span data-stu-id="a2c70-116">Refining the Context</span></span>  
 <span data-ttu-id="a2c70-117">Хотя в предложении FROM контекст задается внутри одного куба, это не запрещает одновременно работать с данными из нескольких кубов.</span><span class="sxs-lookup"><span data-stu-id="a2c70-117">Although the FROM clause specifies the cube context as within a single cube, this does not have to limit you from working with data from more than one cube at a time.</span></span>  
  
 <span data-ttu-id="a2c70-118">Для получения данных из кубов, которые не входят в заданный контекст куба, применяется функция многомерных выражений [LookupCube](/sql/mdx/lookupcube-mdx) .</span><span class="sxs-lookup"><span data-stu-id="a2c70-118">You can use the MDX [LookupCube](/sql/mdx/lookupcube-mdx) function to retrieve data from cubes outside the cube context.</span></span> <span data-ttu-id="a2c70-119">Кроме того, для временного сужения контекста при вычислении запроса можно использовать такие функции как [Filter](/sql/mdx/filter-mdx) .</span><span class="sxs-lookup"><span data-stu-id="a2c70-119">Additionally, functions such as the [Filter](/sql/mdx/filter-mdx) function, are available that allow temporary restriction of the context while evaluating the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2c70-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="a2c70-120">See Also</span></span>  
 [<span data-ttu-id="a2c70-121">Основные принципы запросов многомерных выражений (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="a2c70-121">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-query-fundamentals-analysis-services.md)  
  
  
