---
title: Автоматическая проверка существования | Документация Майкрософт
ms.custom: ''
ms.date: 07/17/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 56283497-624c-45b5-8a0d-036b0e331d22
author: minewiskan
ms.author: owend
ms.openlocfilehash: dd35958a364456c12d58392afe3754f6adcf97b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665638"
---
# <a name="autoexists"></a><span data-ttu-id="0aa3f-102">автоматическая проверка существования</span><span class="sxs-lookup"><span data-stu-id="0aa3f-102">Autoexists</span></span>
  <span data-ttu-id="0aa3f-103">Концепция *автоматической проверки существования* ограничивает пространство куба теми ячейками, которые фактически существуют в кубе, в противоположность тем ячейкам, которые могут существовать в результате создания всех возможных комбинаций элементов иерархии атрибута, принадлежащих одной иерархии.</span><span class="sxs-lookup"><span data-stu-id="0aa3f-103">The concept of *autoexists* limits the cube space to those cells that actually exist in the cube in contraposition to those that might exist as a result of creating all possible combinations of attribute hierarchy members from the same hierarchy.</span></span> <span data-ttu-id="0aa3f-104">Это происходит потому, что элементы одной иерархии атрибута не могут существовать в одном измерении с элементами другой иерархии атрибута.</span><span class="sxs-lookup"><span data-stu-id="0aa3f-104">This is because members of one attribute hierarchy cannot exist with members of another attribute hierarchy in the same dimension.</span></span> <span data-ttu-id="0aa3f-105">Если в инструкции SELECT используются две или более иерархии атрибута одного измерения, службы Analysis Services оценивают эти атрибуты, чтобы убедиться, что элементы этих атрибутов правильно ограничены и соответствуют критериям остальных атрибутов.</span><span class="sxs-lookup"><span data-stu-id="0aa3f-105">When two or more attribute hierarchies of the same dimension are used in a SELECT statement, Analysis Services evaluates the attributes' expressions to make sure that the members of those attributes are properly confined to meet the criteria of all other attributes.</span></span>  
  
 <span data-ttu-id="0aa3f-106">Например, предположим, что идет работа с атрибутами измерения «Geography».</span><span class="sxs-lookup"><span data-stu-id="0aa3f-106">For example, suppose you are working with attributes from the Geography dimension.</span></span> <span data-ttu-id="0aa3f-107">Если существует выражение, возвращающее все элементы атрибута «City», и другое выражение, ограничивающее элементы атрибута «Country» всеми странами Европы, то элементы атрибута «City» будут ограничены только городами, расположенным в странах Европы.</span><span class="sxs-lookup"><span data-stu-id="0aa3f-107">If you have one expression that returns all members from the City attribute and another expression that confines members from the Country attribute to all countries in Europe, then this will result in the City members being confined to only those cities that belong to countries in Europe.</span></span> <span data-ttu-id="0aa3f-108">Такое поведение определяется характеристиками автоматической проверки существования службы Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="0aa3f-108">This is because of the autoexists characteristic of Analysis Services.</span></span> <span data-ttu-id="0aa3f-109">Автоматическая проверка существования применима только к атрибутам, находящимся в одном измерении, потому что пытается предотвратить включение записей измерения, не включенных в одно выражение с атрибутом, в другое выражение с атрибутом.</span><span class="sxs-lookup"><span data-stu-id="0aa3f-109">Autoexists only applies to attributes from the same dimension because it tries to prevent the dimension records excluded in one attribute expression from being included by the other attribute expressions.</span></span> <span data-ttu-id="0aa3f-110">Автоматическую проверку существования можно также воспринимать как результат пересечения различных выражений с атрибутом по строкам измерения.</span><span class="sxs-lookup"><span data-stu-id="0aa3f-110">Autoexists can also be understood as the resulting intersection of the different attributes expressions over the dimension rows.</span></span>  
  
## <a name="cell-existence"></a><span data-ttu-id="0aa3f-111">Существование ячейки</span><span class="sxs-lookup"><span data-stu-id="0aa3f-111">Cell Existence</span></span>  
 <span data-ttu-id="0aa3f-112">Следующие ячейки существуют всегда:</span><span class="sxs-lookup"><span data-stu-id="0aa3f-112">The following cells always exist:</span></span>  
  
-   <span data-ttu-id="0aa3f-113">Элемент «(Все)» любой иерархии при пересечении с элементами других иерархий в том же измерении.</span><span class="sxs-lookup"><span data-stu-id="0aa3f-113">The (All) member, of every hierarchy, when crossed with members of other hierarchies in the same dimension.</span></span>  
  
-   <span data-ttu-id="0aa3f-114">Вычисляемые элементы при пересечении с невычисляемыми одноуровневыми элементами или с родителями или потомками своих невычисляемых одноуровневых элементов.</span><span class="sxs-lookup"><span data-stu-id="0aa3f-114">Calculated members when crossed with their non-calculated siblings, or with the parents or descendants of their non-calculated siblings.</span></span>  
  
## <a name="providing-non-existing-cells"></a><span data-ttu-id="0aa3f-115">Создание несуществующих ячеек</span><span class="sxs-lookup"><span data-stu-id="0aa3f-115">Providing Non-existing cells</span></span>  
 <span data-ttu-id="0aa3f-116">Несуществующая ячейка — это ячейка, создаваемая системой в ответ на запрос или вычисление, требующие ячейку, которая не существует в кубе.</span><span class="sxs-lookup"><span data-stu-id="0aa3f-116">A non-existing cell is a cell provided by the system as a response to a query or calculation that requests a cell that does not exist in the cube.</span></span> <span data-ttu-id="0aa3f-117">Например, пространство куба, содержащего иерархию атрибута «City» и иерархию атрибута «Country», принадлежащие измерению «Geography», и меру Internet Sales Amount, включает только те элементы, которые существуют друг с другом.</span><span class="sxs-lookup"><span data-stu-id="0aa3f-117">For example, if you have a cube that has a City attribute hierarchy and a Country attribute hierarchy that belong to the Geography dimension, and an Internet Sales Amount measure, the space of this cube only includes those members that exist with each other.</span></span> <span data-ttu-id="0aa3f-118">Например, если иерархия атрибута «City» содержит элементы «New York», «London», «Paris», «Tokyo» и «Melbourne», а иерархия атрибута «Country» содержит страны «США», «United Kingdom», «France», «Japan» и «Australia», то пространство куба не содержит ячейку на пересечении элементов «Paris» и «США».</span><span class="sxs-lookup"><span data-stu-id="0aa3f-118">For example, if the City attribute hierarchy includes the cities New York, London, Paris, Tokyo, and Melbourne; and the Country attribute hierarchy includes the countries United States, United Kingdom, France, Japan, and Australia; then the space of the cube does not include the space (cell) at the intersection of Paris and United States.</span></span>  
  
 <span data-ttu-id="0aa3f-119">Запрос к несуществующим ячейкам возвращает значение NULL, то есть они не могут содержать вычисления и нельзя определить вычисления, записывающие данные в это место пространства.</span><span class="sxs-lookup"><span data-stu-id="0aa3f-119">When querying cells that do not exist, non-existing cells return nulls; that is, they cannot contain calculations and you cannot define a calculation that writes to this space.</span></span> <span data-ttu-id="0aa3f-120">Например, следующая инструкция включает в себя несуществующие ячейки.</span><span class="sxs-lookup"><span data-stu-id="0aa3f-120">For example, the following statement includes cells that do not exist.</span></span>  
  
```  
SELECT [Customer].[Gender].[Gender].Members ON COLUMNS,  
{[Customer].[Customer].[Aaron A. Allen]  
   ,[Customer].[Customer].[Abigail Clark]} ON ROWS   
FROM [Adventure Works]  
WHERE Measures.[Internet Sales Amount]  
```  
  
> [!NOTE]  
>  <span data-ttu-id="0aa3f-121">В следующем запросе применяется функция [Members (Set) (многомерные выражения)](/sql/mdx/members-set-mdx) для получения набора элементов иерархии атрибута Gender по оси столбцов и выполняется перекрестное соединение этого набора с заданным набором элементов из иерархии атрибута Customer по оси строк.</span><span class="sxs-lookup"><span data-stu-id="0aa3f-121">This query uses the [Members (Set) (MDX)](/sql/mdx/members-set-mdx) function to return the set of members of the Gender attribute hierarchy on the column axis, and crosses this set with the specified set of members from the Customer attribute hierarchy on the row axis.</span></span>  
  
 <span data-ttu-id="0aa3f-122">При выполнении предыдущего запроса ячейка на пересечении элементов [Aaron A. Allen] и [Female] отображает значение NULL.</span><span class="sxs-lookup"><span data-stu-id="0aa3f-122">When you execute the previous query, the cell at the intersection of Aaron A. Allen and Female displays a null.</span></span> <span data-ttu-id="0aa3f-123">Аналогично, значение NULL отображается в ячейке на пересечении элементов [Abigail Clark] и [Male].</span><span class="sxs-lookup"><span data-stu-id="0aa3f-123">Similarly, the cell at the intersection of Abigail Clark and Male displays a null.</span></span> <span data-ttu-id="0aa3f-124">Эти ячейки не существуют и не могут содержать значение, но запрос может вернуть несуществующие ячейки.</span><span class="sxs-lookup"><span data-stu-id="0aa3f-124">These cells do not exist and cannot contain a value, but cells that do not exist can appear in the result returned by a query.</span></span>  
  
 <span data-ttu-id="0aa3f-125">При использовании функции [Crossjoin (многомерные выражения)](/sql/mdx/crossjoin-mdx) для получения перекрестного произведения элементов иерархий атрибутов из иерархий атрибутов одного измерения автоматическое существование ограничивает возвращаемые кортежи набором действительно существующих кортежей, а не возвращает все декартово произведение.</span><span class="sxs-lookup"><span data-stu-id="0aa3f-125">When you use the [Crossjoin (MDX)](/sql/mdx/crossjoin-mdx) function to return the cross-product of attribute hierarchy members from attribute hierarchies in the same dimension, auto-exists limits those tuples being returned to the set of tuples that actually exist, rather than returning a full Cartesian product.</span></span> <span data-ttu-id="0aa3f-126">Выполните следующий запрос и изучите его результаты.</span><span class="sxs-lookup"><span data-stu-id="0aa3f-126">For example, run and then examine the results from the execution of the following query.</span></span>  
  
```  
SELECT CROSSJOIN  
   (  
      {[Customer].[Country].[United States]},  
         [Customer].[State-Province].Members  
  ) ON 0   
FROM [Adventure Works]  
WHERE Measures.[Internet Sales Amount]  
```  
  
> [!NOTE]  
>  <span data-ttu-id="0aa3f-127">Обратите внимание, что 0 используется для обозначения оси столбцов, это сокращение для оси(0), являющейся осью столбцов.</span><span class="sxs-lookup"><span data-stu-id="0aa3f-127">Notice that 0 is used to designate the column axis, which is shorthand for axis(0) - which is the column axis.</span></span>  
  
 <span data-ttu-id="0aa3f-128">В предыдущем запросе возвращаются только ячейки для элементов каждой иерархии атрибута в запросе, которые существуют друг с другом.</span><span class="sxs-lookup"><span data-stu-id="0aa3f-128">The previous query only returns cells for members from each attribute hierarchy in the query that exist with each other.</span></span> <span data-ttu-id="0aa3f-129">Предыдущий запрос также может быть написан с помощью нового варианта \* типа функции [перекрестного набора данных (MDX)](/sql/mdx/crossjoin-mdx) .</span><span class="sxs-lookup"><span data-stu-id="0aa3f-129">The previous query can also be written using the new \* variant of the [Crossjoin (MDX)](/sql/mdx/crossjoin-mdx) function.</span></span>  
  
```  
SELECT   
   [Customer].[Country].[United States] *   
      [Customer].[State-Province].Members  
ON 0   
FROM [Adventure Works]  
WHERE Measures.[Internet Sales Amount]  
```  
  
 <span data-ttu-id="0aa3f-130">Предыдущий запрос можно переписать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="0aa3f-130">The previous query could also be written in the following manner:</span></span>  
  
```  
SELECT [Customer].[State-Province].Members  
ON 0   
FROM [Adventure Works]  
WHERE (Measures.[Internet Sales Amount],  
   [Customer].[Country].[United States])  
```  
  
 <span data-ttu-id="0aa3f-131">Значения ячеек будут совпадать, хотя метаданные в результирующем наборе будут разными.</span><span class="sxs-lookup"><span data-stu-id="0aa3f-131">The cells values returned will be identical, although the metadata in the result set will be different.</span></span> <span data-ttu-id="0aa3f-132">Например, в предыдущем запросе иерархия Country перемещена на ось среза (в предложении WHERE) и поэтому не представлена явно в результирующем наборе.</span><span class="sxs-lookup"><span data-stu-id="0aa3f-132">For example, with the previous query, the Country hierarchy was moved to the slicer axis (in the WHERE clause) and therefore does not appear explicitly in the result set.</span></span>  
  
 <span data-ttu-id="0aa3f-133">Каждый из этих трех предыдущих запросов демонстрирует результат поведения автоматического существования в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0aa3f-133">Each of these three previous queries demonstrates the effect of the auto-exists behavior in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>  
  
## <a name="deep-and-shallow-autoexists"></a><span data-ttu-id="0aa3f-134">Глубокая и поверхностная автоматические проверки существования</span><span class="sxs-lookup"><span data-stu-id="0aa3f-134">Deep and Shallow Autoexists</span></span>  
 <span data-ttu-id="0aa3f-135">Автоматическую проверку существования можно применять к выражениям глубоко или поверхностно.</span><span class="sxs-lookup"><span data-stu-id="0aa3f-135">Autoexists can be applied to the expressions as Deep or Shallow.</span></span> <span data-ttu-id="0aa3f-136">`Deep Autoexists` означает, что все выражения будут оцениваться по наибольшему из возможных пространств после применения выражений выделения среза, выражений подзапроса по оси и т. д.</span><span class="sxs-lookup"><span data-stu-id="0aa3f-136">`Deep Autoexists` means that all expressions will be evaluated to meet the deepest possible space after applying the slicer expressions, the sub select expressions in the axis, and so on.</span></span> <span data-ttu-id="0aa3f-137">`Shallow Autoexists` означает, что внешние выражения оцениваются перед текущим выражением и их результаты будут переданы в текущее выражение.</span><span class="sxs-lookup"><span data-stu-id="0aa3f-137">`Shallow Autoexists` means that external expressions are evaluated before the current expression and those results are passed to the current expression.</span></span> <span data-ttu-id="0aa3f-138">По умолчанию выполняется глубокая автоматическая проверка существования.</span><span class="sxs-lookup"><span data-stu-id="0aa3f-138">The default setting is deep autoexists.</span></span>  
  
 <span data-ttu-id="0aa3f-139">Для иллюстрации различных типов автоматической проверки существования рассмотрим следующий сценарий и соответствующие примеры.</span><span class="sxs-lookup"><span data-stu-id="0aa3f-139">The following scenario and samples will help to illustrate the different types of Autoexistss.</span></span> <span data-ttu-id="0aa3f-140">В следующих примерах будут созданы два набора: один — как вычисляемое выражение, другой — как константное выражение.</span><span class="sxs-lookup"><span data-stu-id="0aa3f-140">In the following examples two sets will be created: one as a calculated expression and the other as a constant expression.</span></span>  
  
 `//Obtain the Top 10 best reseller selling products by Name`  
  
 `with member [Measures].[PCT Discount] AS '[Measures].[Discount Amount]/[Measures].[Reseller Sales Amount]', FORMAT_STRING = 'Percent'`  
  
 `set Top10SellingProducts as 'topcount([Product].[Model Name].children, 10, [Measures].[Reseller Sales Amount])'`  
  
 `set Preferred10Products as '`  
  
 `{[Product].[Model Name].&[Mountain-200],`  
  
 `[Product].[Model Name].&[Road-250],`  
  
 `[Product].[Model Name].&[Mountain-100],`  
  
 `[Product].[Model Name].&[Road-650],`  
  
 `[Product].[Model Name].&[Touring-1000],`  
  
 `[Product].[Model Name].&[Road-550-W],`  
  
 `[Product].[Model Name].&[Road-350-W],`  
  
 `[Product].[Model Name].&[HL Mountain Frame],`  
  
 `[Product].[Model Name].&[Road-150],`  
  
 `[Product].[Model Name].&[Touring-3000]`  
  
 `}'`  
  
 `select {[Measures].[Reseller Sales Amount], [Measures].[Discount Amount], [Measures].[PCT Discount]} on 0,`  
  
 `Top10SellingProducts on 1`  
  
 `from [Adventure Works]`  
  
 <span data-ttu-id="0aa3f-141">Полученный результирующий набор выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="0aa3f-141">The obtained result set is:</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="0aa3f-142">**Reseller Sales Amount**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-142">**Reseller Sales Amount**</span></span>|<span data-ttu-id="0aa3f-143">**Discount Amount**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-143">**Discount Amount**</span></span>|<span data-ttu-id="0aa3f-144">**PCT Discount**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-144">**PCT Discount**</span></span>|  
|<span data-ttu-id="0aa3f-145">**Велосипед Mountain-200**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-145">**Mountain-200**</span></span>|<span data-ttu-id="0aa3f-146">**$ 14 356 699,36**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-146">**$14,356,699.36**</span></span>|<span data-ttu-id="0aa3f-147">**$ 19 012,71**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-147">**$19,012.71**</span></span>|<span data-ttu-id="0aa3f-148">**0,13%**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-148">**0.13%**</span></span>|  
|<span data-ttu-id="0aa3f-149">**Road-250**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-149">**Road-250**</span></span>|<span data-ttu-id="0aa3f-150">**$ 9 377 457,68**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-150">**$9,377,457.68**</span></span>|<span data-ttu-id="0aa3f-151">**$ 4 032,47**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-151">**$4,032.47**</span></span>|<span data-ttu-id="0aa3f-152">**0,04%**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-152">**0.04%**</span></span>|  
|<span data-ttu-id="0aa3f-153">**Mountain-100**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-153">**Mountain-100**</span></span>|<span data-ttu-id="0aa3f-154">**$ 8 568 958,27**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-154">**$8,568,958.27**</span></span>|<span data-ttu-id="0aa3f-155">**$ 139 393,27**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-155">**$139,393.27**</span></span>|<span data-ttu-id="0aa3f-156">**1,63%**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-156">**1.63%**</span></span>|  
|<span data-ttu-id="0aa3f-157">**Road-650**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-157">**Road-650**</span></span>|<span data-ttu-id="0aa3f-158">**$ 7 442 141,81**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-158">**$7,442,141.81**</span></span>|<span data-ttu-id="0aa3f-159">**$ 39 698,30**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-159">**$39,698.30**</span></span>|<span data-ttu-id="0aa3f-160">**0,53 %**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-160">**0.53%**</span></span>|  
|<span data-ttu-id="0aa3f-161">**Touring-1000**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-161">**Touring-1000**</span></span>|<span data-ttu-id="0aa3f-162">**$ 6 723 794,29**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-162">**$6,723,794.29**</span></span>|<span data-ttu-id="0aa3f-163">**$ 166 144,17**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-163">**$166,144.17**</span></span>|<span data-ttu-id="0aa3f-164">**2,47%**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-164">**2.47%**</span></span>|  
|<span data-ttu-id="0aa3f-165">**Road-550-W**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-165">**Road-550-W**</span></span>|<span data-ttu-id="0aa3f-166">**$ 3 668 383,88**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-166">**$3,668,383.88**</span></span>|<span data-ttu-id="0aa3f-167">**$ 1 901,97**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-167">**$1,901.97**</span></span>|<span data-ttu-id="0aa3f-168">**0,05%**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-168">**0.05%**</span></span>|  
|<span data-ttu-id="0aa3f-169">**Road-350-W**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-169">**Road-350-W**</span></span>|<span data-ttu-id="0aa3f-170">**$ 3 665 932,31**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-170">**$3,665,932.31**</span></span>|<span data-ttu-id="0aa3f-171">**$ 20 946,50**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-171">**$20,946.50**</span></span>|<span data-ttu-id="0aa3f-172">**0,57%**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-172">**0.57%**</span></span>|  
|<span data-ttu-id="0aa3f-173">**HL Mountain Frame**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-173">**HL Mountain Frame**</span></span>|<span data-ttu-id="0aa3f-174">**$ 3 365 069,27**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-174">**$3,365,069.27**</span></span>|<span data-ttu-id="0aa3f-175">**$ 174,11**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-175">**$174.11**</span></span>|<span data-ttu-id="0aa3f-176">**0,01%**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-176">**0.01%**</span></span>|  
|<span data-ttu-id="0aa3f-177">**Road-150**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-177">**Road-150**</span></span>|<span data-ttu-id="0aa3f-178">**$ 2 363 805,16**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-178">**$2,363,805.16**</span></span>|<span data-ttu-id="0aa3f-179">**$0,00**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-179">**$0.00**</span></span>|<span data-ttu-id="0aa3f-180">**0,00%**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-180">**0.00%**</span></span>|  
|<span data-ttu-id="0aa3f-181">**Touring-3000**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-181">**Touring-3000**</span></span>|<span data-ttu-id="0aa3f-182">**$ 2 046 508,26**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-182">**$2,046,508.26**</span></span>|<span data-ttu-id="0aa3f-183">**$ 79 582,15**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-183">**$79,582.15**</span></span>|<span data-ttu-id="0aa3f-184">**3,89 %**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-184">**3.89%**</span></span>|  
  
 <span data-ttu-id="0aa3f-185">Полученный набор продуктов выглядит так же, как и Preferred10Products; проверяем набор Preferred10Products:</span><span class="sxs-lookup"><span data-stu-id="0aa3f-185">The obtained set of products seems to be the same as Preferred10Products; so, verifying the Preferred10Products set:</span></span>  
  
 `with member [Measures].[PCT Discount] AS '[Measures].[Discount Amount]/[Measures].[Reseller Sales Amount]', FORMAT_STRING = 'Percent'`  
  
 `set Top10SellingProducts as 'topcount([Product].[Model Name].children, 10, [Measures].[Reseller Sales Amount])'`  
  
 `set Preferred10Products as '`  
  
 `{[Product].[Model Name].&[Mountain-200],`  
  
 `[Product].[Model Name].&[Road-250],`  
  
 `[Product].[Model Name].&[Mountain-100],`  
  
 `[Product].[Model Name].&[Road-650],`  
  
 `[Product].[Model Name].&[Touring-1000],`  
  
 `[Product].[Model Name].&[Road-550-W],`  
  
 `[Product].[Model Name].&[Road-350-W],`  
  
 `[Product].[Model Name].&[HL Mountain Frame],`  
  
 `[Product].[Model Name].&[Road-150],`  
  
 `[Product].[Model Name].&[Touring-3000]`  
  
 `}'`  
  
 `select {[Measures].[Reseller Sales Amount], [Measures].[Discount Amount], [Measures].[PCT Discount]} on 0,`  
  
 `Preferred10Products on 1`  
  
 `from [Adventure Works]`  
  
 <span data-ttu-id="0aa3f-186">Согласно полученным результатам наборы Top10SellingProducts и Preferred10Products совпадают:</span><span class="sxs-lookup"><span data-stu-id="0aa3f-186">As per the following results, both sets (Top10SellingProducts, Preferred10Products) are the same</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="0aa3f-187">**Reseller Sales Amount**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-187">**Reseller Sales Amount**</span></span>|<span data-ttu-id="0aa3f-188">**Discount Amount**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-188">**Discount Amount**</span></span>|<span data-ttu-id="0aa3f-189">**PCT Discount**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-189">**PCT Discount**</span></span>|  
|<span data-ttu-id="0aa3f-190">**Велосипед Mountain-200**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-190">**Mountain-200**</span></span>|<span data-ttu-id="0aa3f-191">**$ 14 356 699,36**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-191">**$14,356,699.36**</span></span>|<span data-ttu-id="0aa3f-192">**$ 19 012,71**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-192">**$19,012.71**</span></span>|<span data-ttu-id="0aa3f-193">**0,13%**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-193">**0.13%**</span></span>|  
|<span data-ttu-id="0aa3f-194">**Road-250**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-194">**Road-250**</span></span>|<span data-ttu-id="0aa3f-195">**$ 9 377 457,68**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-195">**$9,377,457.68**</span></span>|<span data-ttu-id="0aa3f-196">**$ 4 032,47**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-196">**$4,032.47**</span></span>|<span data-ttu-id="0aa3f-197">**0,04%**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-197">**0.04%**</span></span>|  
|<span data-ttu-id="0aa3f-198">**Mountain-100**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-198">**Mountain-100**</span></span>|<span data-ttu-id="0aa3f-199">**$ 8 568 958,27**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-199">**$8,568,958.27**</span></span>|<span data-ttu-id="0aa3f-200">**$ 139 393,27**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-200">**$139,393.27**</span></span>|<span data-ttu-id="0aa3f-201">**1,63%**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-201">**1.63%**</span></span>|  
|<span data-ttu-id="0aa3f-202">**Road-650**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-202">**Road-650**</span></span>|<span data-ttu-id="0aa3f-203">**$ 7 442 141,81**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-203">**$7,442,141.81**</span></span>|<span data-ttu-id="0aa3f-204">**$ 39 698,30**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-204">**$39,698.30**</span></span>|<span data-ttu-id="0aa3f-205">**0,53 %**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-205">**0.53%**</span></span>|  
|<span data-ttu-id="0aa3f-206">**Touring-1000**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-206">**Touring-1000**</span></span>|<span data-ttu-id="0aa3f-207">**$ 6 723 794,29**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-207">**$6,723,794.29**</span></span>|<span data-ttu-id="0aa3f-208">**$ 166 144,17**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-208">**$166,144.17**</span></span>|<span data-ttu-id="0aa3f-209">**2,47%**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-209">**2.47%**</span></span>|  
|<span data-ttu-id="0aa3f-210">**Road-550-W**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-210">**Road-550-W**</span></span>|<span data-ttu-id="0aa3f-211">**$ 3 668 383,88**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-211">**$3,668,383.88**</span></span>|<span data-ttu-id="0aa3f-212">**$ 1 901,97**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-212">**$1,901.97**</span></span>|<span data-ttu-id="0aa3f-213">**0,05%**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-213">**0.05%**</span></span>|  
|<span data-ttu-id="0aa3f-214">**Road-350-W**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-214">**Road-350-W**</span></span>|<span data-ttu-id="0aa3f-215">**$ 3 665 932,31**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-215">**$3,665,932.31**</span></span>|<span data-ttu-id="0aa3f-216">**$ 20 946,50**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-216">**$20,946.50**</span></span>|<span data-ttu-id="0aa3f-217">**0,57%**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-217">**0.57%**</span></span>|  
|<span data-ttu-id="0aa3f-218">**HL Mountain Frame**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-218">**HL Mountain Frame**</span></span>|<span data-ttu-id="0aa3f-219">**$ 3 365 069,27**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-219">**$3,365,069.27**</span></span>|<span data-ttu-id="0aa3f-220">**$ 174,11**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-220">**$174.11**</span></span>|<span data-ttu-id="0aa3f-221">**0,01%**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-221">**0.01%**</span></span>|  
|<span data-ttu-id="0aa3f-222">**Road-150**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-222">**Road-150**</span></span>|<span data-ttu-id="0aa3f-223">**$ 2 363 805,16**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-223">**$2,363,805.16**</span></span>|<span data-ttu-id="0aa3f-224">**$0,00**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-224">**$0.00**</span></span>|<span data-ttu-id="0aa3f-225">**0,00%**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-225">**0.00%**</span></span>|  
|<span data-ttu-id="0aa3f-226">**Touring-3000**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-226">**Touring-3000**</span></span>|<span data-ttu-id="0aa3f-227">**$ 2 046 508,26**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-227">**$2,046,508.26**</span></span>|<span data-ttu-id="0aa3f-228">**$ 79 582,15**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-228">**$79,582.15**</span></span>|<span data-ttu-id="0aa3f-229">**3,89 %**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-229">**3.89%**</span></span>|  
  
 <span data-ttu-id="0aa3f-230">Следующий пример демонстрирует концепцию глубокой автоматической проверки существования.</span><span class="sxs-lookup"><span data-stu-id="0aa3f-230">The following example will illustrate the concept of deep Autoexists.</span></span> <span data-ttu-id="0aa3f-231">В примере набор Top10SellingProducts фильтруется по атрибуту [Product].[Product Line] для попадающих в группу [Mountain].</span><span class="sxs-lookup"><span data-stu-id="0aa3f-231">In the example we are filtering Top10SellingProducts by [Product].[Product Line] attribute for those in [Mountain] group.</span></span> <span data-ttu-id="0aa3f-232">Обратите внимание, что оба атрибута (срез и ось) принадлежат одному измерению ([Product]).</span><span class="sxs-lookup"><span data-stu-id="0aa3f-232">Note that both attributes (slicer and axis) belong to the same dimension, [Product].</span></span>  
  
 `with member [Measures].[PCT Discount] AS '[Measures].[Discount Amount]/[Measures].[Reseller Sales Amount]', FORMAT_STRING = 'Percent'`  
  
 `set Top10SellingProducts as 'topcount([Product].[Model Name].children, 10, [Measures].[Reseller Sales Amount])'`  
  
 `// Preferred10Products set removed for clarity`  
  
 `select {[Measures].[Reseller Sales Amount], [Measures].[Discount Amount], [Measures].[PCT Discount]} on 0,`  
  
 `Top10SellingProducts on 1`  
  
 `from [Adventure Works]`  
  
 `where [Product].[Product Line].[Mountain]`  
  
 <span data-ttu-id="0aa3f-233">Создает следующий результирующий набор:</span><span class="sxs-lookup"><span data-stu-id="0aa3f-233">Produces the following result set:</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="0aa3f-234">**Reseller Sales Amount**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-234">**Reseller Sales Amount**</span></span>|<span data-ttu-id="0aa3f-235">**Discount Amount**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-235">**Discount Amount**</span></span>|<span data-ttu-id="0aa3f-236">**PCT Discount**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-236">**PCT Discount**</span></span>|  
|<span data-ttu-id="0aa3f-237">**Велосипед Mountain-200**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-237">**Mountain-200**</span></span>|<span data-ttu-id="0aa3f-238">**$ 14 356 699,36**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-238">**$14,356,699.36**</span></span>|<span data-ttu-id="0aa3f-239">**$ 19 012,71**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-239">**$19,012.71**</span></span>|<span data-ttu-id="0aa3f-240">**0,13%**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-240">**0.13%**</span></span>|  
|<span data-ttu-id="0aa3f-241">**Mountain-100**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-241">**Mountain-100**</span></span>|<span data-ttu-id="0aa3f-242">**$ 8 568 958,27**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-242">**$8,568,958.27**</span></span>|<span data-ttu-id="0aa3f-243">**$ 139 393,27**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-243">**$139,393.27**</span></span>|<span data-ttu-id="0aa3f-244">**1,63%**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-244">**1.63%**</span></span>|  
|<span data-ttu-id="0aa3f-245">**HL Mountain Frame**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-245">**HL Mountain Frame**</span></span>|<span data-ttu-id="0aa3f-246">**$ 3 365 069,27**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-246">**$3,365,069.27**</span></span>|<span data-ttu-id="0aa3f-247">**$ 174,11**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-247">**$174.11**</span></span>|<span data-ttu-id="0aa3f-248">**0,01%**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-248">**0.01%**</span></span>|  
|<span data-ttu-id="0aa3f-249">**Mountain-300**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-249">**Mountain-300**</span></span>|<span data-ttu-id="0aa3f-250">**$ 1 907 249,38**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-250">**$1,907,249.38**</span></span>|<span data-ttu-id="0aa3f-251">**$ 876,95**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-251">**$876.95**</span></span>|<span data-ttu-id="0aa3f-252">**0,05%**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-252">**0.05%**</span></span>|  
|<span data-ttu-id="0aa3f-253">**Mountain-500**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-253">**Mountain-500**</span></span>|<span data-ttu-id="0aa3f-254">**$ 1 067 327,31**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-254">**$1,067,327.31**</span></span>|<span data-ttu-id="0aa3f-255">**$ 17 266,09**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-255">**$17,266.09**</span></span>|<span data-ttu-id="0aa3f-256">**1,62 %**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-256">**1.62%**</span></span>|  
|<span data-ttu-id="0aa3f-257">**Mountain-400-W**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-257">**Mountain-400-W**</span></span>|<span data-ttu-id="0aa3f-258">**$ 592 450,05**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-258">**$592,450.05**</span></span>|<span data-ttu-id="0aa3f-259">**$ 303,49**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-259">**$303.49**</span></span>|<span data-ttu-id="0aa3f-260">**0,05%**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-260">**0.05%**</span></span>|  
|<span data-ttu-id="0aa3f-261">**LL Mountain Frame**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-261">**LL Mountain Frame**</span></span>|<span data-ttu-id="0aa3f-262">**$ 521 864,42**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-262">**$521,864.42**</span></span>|<span data-ttu-id="0aa3f-263">**$ 252,41**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-263">**$252.41**</span></span>|<span data-ttu-id="0aa3f-264">**0,05%**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-264">**0.05%**</span></span>|  
|<span data-ttu-id="0aa3f-265">**ML Mountain Frame-W**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-265">**ML Mountain Frame-W**</span></span>|<span data-ttu-id="0aa3f-266">**$ 482 953,16**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-266">**$482,953.16**</span></span>|<span data-ttu-id="0aa3f-267">**$ 206,95**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-267">**$206.95**</span></span>|<span data-ttu-id="0aa3f-268">**0,04%**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-268">**0.04%**</span></span>|  
|<span data-ttu-id="0aa3f-269">**ML Mountain Frame**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-269">**ML Mountain Frame**</span></span>|<span data-ttu-id="0aa3f-270">**$ 343 785,29**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-270">**$343,785.29**</span></span>|<span data-ttu-id="0aa3f-271">**$ 161,82**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-271">**$161.82**</span></span>|<span data-ttu-id="0aa3f-272">**0,05%**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-272">**0.05%**</span></span>|  
|<span data-ttu-id="0aa3f-273">**Женские шорты Mountain**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-273">**Women's Mountain Shorts**</span></span>|<span data-ttu-id="0aa3f-274">**$ 260 304,09**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-274">**$260,304.09**</span></span>|<span data-ttu-id="0aa3f-275">**$ 6 675,56**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-275">**$6,675.56**</span></span>|<span data-ttu-id="0aa3f-276">**2,56%**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-276">**2.56%**</span></span>|  
  
 <span data-ttu-id="0aa3f-277">Приведенный выше результирующий набор содержит в списке Top10SellingProducts семь новых элементов, а Mountain-200, Mountain-100 и HL Mountain Frame переместились в начало списка.</span><span class="sxs-lookup"><span data-stu-id="0aa3f-277">In the above result set we have seven newcomers to the list of Top10SellingProducts and Mountain-200, Mountain-100, and HL Mountain Frame have moved to the top of the list.</span></span> <span data-ttu-id="0aa3f-278">В предыдущем результирующем наборе эти три значения перемешивались с другими элементами.</span><span class="sxs-lookup"><span data-stu-id="0aa3f-278">In the previous result set those three values were interspersed.</span></span>  
  
 <span data-ttu-id="0aa3f-279">Это называется глубокой автоматической проверкой существования, так как набор Top10SellingProducts оценивается на соответствие условиям срезов в запросе.</span><span class="sxs-lookup"><span data-stu-id="0aa3f-279">This is called Deep Autoexists, because the Top10SellingProducts set is evaluated to meet the slicing conditions of the query.</span></span> <span data-ttu-id="0aa3f-280">Глубокая автоматическая проверка существования означает, что все выражения будут оцениваться для обнаружения наибольшего пространства из возможных после применения выражений выделения среза, выражений подзапроса по оси и т. д.</span><span class="sxs-lookup"><span data-stu-id="0aa3f-280">Deep Autoexists means that all expressions will be evaluated to meet the deepest possible space after applying the slicer expressions, the sub select expressions in the axis, and so on.</span></span>  
  
 <span data-ttu-id="0aa3f-281">Однако может возникнуть необходимость проведения анализа Top10SellingProducts как эквивалента Preferred10Products, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="0aa3f-281">However, one might want to be able to do the analysis over the Top10SellingProducts as equivalent to Preferred10Products, as in the following example:</span></span>  
  
 `with member [Measures].[PCT Discount] AS '[Measures].[Discount Amount]/[Measures].[Reseller Sales Amount]', FORMAT_STRING = 'Percent'`  
  
 `set Top10SellingProducts as 'topcount([Product].[Model Name].children, 10, [Measures].[Reseller Sales Amount])'`  
  
 `set Preferred10Products as '`  
  
 `{[Product].[Model Name].&[Mountain-200],`  
  
 `[Product].[Model Name].&[Road-250],`  
  
 `[Product].[Model Name].&[Mountain-100],`  
  
 `[Product].[Model Name].&[Road-650],`  
  
 `[Product].[Model Name].&[Touring-1000],`  
  
 `[Product].[Model Name].&[Road-550-W],`  
  
 `[Product].[Model Name].&[Road-350-W],`  
  
 `[Product].[Model Name].&[HL Mountain Frame],`  
  
 `[Product].[Model Name].&[Road-150],`  
  
 `[Product].[Model Name].&[Touring-3000]`  
  
 `}'`  
  
 `select {[Measures].[Reseller Sales Amount], [Measures].[Discount Amount], [Measures].[PCT Discount]} on 0,`  
  
 `Preferred10Products on 1`  
  
 `from [Adventure Works]`  
  
 `where [Product].[Product Line].[Mountain]`  
  
 <span data-ttu-id="0aa3f-282">Создает следующий результирующий набор:</span><span class="sxs-lookup"><span data-stu-id="0aa3f-282">Produces the following result set:</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="0aa3f-283">**Reseller Sales Amount**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-283">**Reseller Sales Amount**</span></span>|<span data-ttu-id="0aa3f-284">**Discount Amount**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-284">**Discount Amount**</span></span>|<span data-ttu-id="0aa3f-285">**PCT Discount**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-285">**PCT Discount**</span></span>|  
|<span data-ttu-id="0aa3f-286">**Велосипед Mountain-200**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-286">**Mountain-200**</span></span>|<span data-ttu-id="0aa3f-287">**$ 14 356 699,36**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-287">**$14,356,699.36**</span></span>|<span data-ttu-id="0aa3f-288">**$ 19 012,71**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-288">**$19,012.71**</span></span>|<span data-ttu-id="0aa3f-289">**0,13%**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-289">**0.13%**</span></span>|  
|<span data-ttu-id="0aa3f-290">**Mountain-100**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-290">**Mountain-100**</span></span>|<span data-ttu-id="0aa3f-291">**$ 8 568 958,27**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-291">**$8,568,958.27**</span></span>|<span data-ttu-id="0aa3f-292">**$ 139 393,27**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-292">**$139,393.27**</span></span>|<span data-ttu-id="0aa3f-293">**1,63%**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-293">**1.63%**</span></span>|  
|<span data-ttu-id="0aa3f-294">**HL Mountain Frame**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-294">**HL Mountain Frame**</span></span>|<span data-ttu-id="0aa3f-295">**$ 3 365 069,27**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-295">**$3,365,069.27**</span></span>|<span data-ttu-id="0aa3f-296">**$ 174,11**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-296">**$174.11**</span></span>|<span data-ttu-id="0aa3f-297">**0,01%**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-297">**0.01%**</span></span>|  
  
 <span data-ttu-id="0aa3f-298">В результатах, приведенных выше, срез дает результат, содержащий только те продукты из набора Preferred10Products, которые являются частью группы [Mountain] атрибута [Product].[Product Line], потому что Preferred10Products является константным выражением.</span><span class="sxs-lookup"><span data-stu-id="0aa3f-298">In the above results, the slicing gives a result that contains only those products from Preferred10Products that are part of the [Mountain] group in [Product].[Product Line]; as expected, because Preferred10Products is a constant expression.</span></span>  
  
 <span data-ttu-id="0aa3f-299">Результирующий набор можно также представить как поверхностную автоматическую проверку существования.</span><span class="sxs-lookup"><span data-stu-id="0aa3f-299">This result set is also understood as Shallow Autoexists.</span></span> <span data-ttu-id="0aa3f-300">Это связано с тем, что выражение оценивается перед предложением среза.</span><span class="sxs-lookup"><span data-stu-id="0aa3f-300">This is because the expression is evaluated before the slicing clause.</span></span> <span data-ttu-id="0aa3f-301">В предыдущем примере выражение было константным для демонстрации особенностей в целях представления о концепции.</span><span class="sxs-lookup"><span data-stu-id="0aa3f-301">In the previous example, the expression was a constant expression for illustration purposes in order to introduce the concept.</span></span>  
  
 <span data-ttu-id="0aa3f-302">Поведение автоматической проверки существования может изменяться на уровне сеанса при помощи свойства `Autoexists` строки подключения.</span><span class="sxs-lookup"><span data-stu-id="0aa3f-302">Autoexists behavior can be modified at the session level using the `Autoexists` connection string property.</span></span> <span data-ttu-id="0aa3f-303">В следующих примерах открывается новый сеанс и добавляется свойство *Autoexists=3* в строку подключения.</span><span class="sxs-lookup"><span data-stu-id="0aa3f-303">The following example begins by opening a new session and adding the *Autoexists=3* property to the connection string.</span></span> <span data-ttu-id="0aa3f-304">Для выполнения примера необходимо создать новое соединение.</span><span class="sxs-lookup"><span data-stu-id="0aa3f-304">You must open a new connection in order to do the example.</span></span> <span data-ttu-id="0aa3f-305">После установки соединения с параметром автоматической проверки существования (Autoexist) эта проверка будет выполняться до самого закрытия соединения.</span><span class="sxs-lookup"><span data-stu-id="0aa3f-305">Once the connection is established with the Autoexist setting it will remain in effect until that connection is finished.</span></span>  
  
 `with member [Measures].[PCT Discount] AS '[Measures].[Discount Amount]/[Measures].[Reseller Sales Amount]', FORMAT_STRING = 'Percent'`  
  
 `set Top10SellingProducts as 'topcount([Product].[Model Name].children, 10, [Measures].[Reseller Sales Amount])'`  
  
 `//Preferred10Products set removed for clarity`  
  
 `select {[Measures].[Reseller Sales Amount], [Measures].[Discount Amount], [Measures].[PCT Discount]} on 0,`  
  
 `Top10SellingProducts on 1`  
  
 `from [Adventure Works]`  
  
 `where [Product].[Product Line].[Mountain]`  
  
 <span data-ttu-id="0aa3f-306">Следующий результирующий набор демонстрирует поведение поверхностной автоматической проверки существования.</span><span class="sxs-lookup"><span data-stu-id="0aa3f-306">The following result set now shows the shallow behavior of Autoexists.</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="0aa3f-307">**Reseller Sales Amount**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-307">**Reseller Sales Amount**</span></span>|<span data-ttu-id="0aa3f-308">**Discount Amount**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-308">**Discount Amount**</span></span>|<span data-ttu-id="0aa3f-309">**PCT Discount**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-309">**PCT Discount**</span></span>|  
|<span data-ttu-id="0aa3f-310">**Велосипед Mountain-200**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-310">**Mountain-200**</span></span>|<span data-ttu-id="0aa3f-311">**$ 14 356 699,36**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-311">**$14,356,699.36**</span></span>|<span data-ttu-id="0aa3f-312">**$ 19 012,71**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-312">**$19,012.71**</span></span>|<span data-ttu-id="0aa3f-313">**0,13%**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-313">**0.13%**</span></span>|  
|<span data-ttu-id="0aa3f-314">**Mountain-100**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-314">**Mountain-100**</span></span>|<span data-ttu-id="0aa3f-315">**$ 8 568 958,27**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-315">**$8,568,958.27**</span></span>|<span data-ttu-id="0aa3f-316">**$ 139 393,27**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-316">**$139,393.27**</span></span>|<span data-ttu-id="0aa3f-317">**1,63%**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-317">**1.63%**</span></span>|  
|<span data-ttu-id="0aa3f-318">**HL Mountain Frame**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-318">**HL Mountain Frame**</span></span>|<span data-ttu-id="0aa3f-319">**$ 3 365 069,27**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-319">**$3,365,069.27**</span></span>|<span data-ttu-id="0aa3f-320">**$ 174,11**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-320">**$174.11**</span></span>|<span data-ttu-id="0aa3f-321">**0,01%**</span><span class="sxs-lookup"><span data-stu-id="0aa3f-321">**0.01%**</span></span>|  
  
 <span data-ttu-id="0aa3f-322">Поведение автоматической проверки существования можно изменить с помощью параметра "автосуществование = [1 | 2 | 3]" в строке подключения. см. раздел [Поддерживаемые свойства xmla &#40;xmla&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/propertylist-element-supported-xmla-properties) и <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.ConnectionString%2A> сведения об использовании параметров.</span><span class="sxs-lookup"><span data-stu-id="0aa3f-322">Autoexists behavior can be modified by using the AUTOEXISTS=[1|2|3] parameter in the connection string; see [Supported XMLA Properties &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/propertylist-element-supported-xmla-properties) and <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection.ConnectionString%2A> for parameter usage.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0aa3f-323">См. также:</span><span class="sxs-lookup"><span data-stu-id="0aa3f-323">See Also</span></span>  
 <span data-ttu-id="0aa3f-324">[Основные понятия в Analysis Services &#40;многомерных выражений&#41;](../key-concepts-in-mdx-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="0aa3f-324">[Key Concepts in MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span></span>  
 <span data-ttu-id="0aa3f-325">[Пространство куба](cube-space.md) </span><span class="sxs-lookup"><span data-stu-id="0aa3f-325">[Cube Space](cube-space.md) </span></span>  
 <span data-ttu-id="0aa3f-326">[Кортежей](tuples.md) </span><span class="sxs-lookup"><span data-stu-id="0aa3f-326">[Tuples](tuples.md) </span></span>  
 <span data-ttu-id="0aa3f-327">[Работа с элементами, кортежами и наборами &#40;многомерных выражениях&#41;](working-with-members-tuples-and-sets-mdx.md) </span><span class="sxs-lookup"><span data-stu-id="0aa3f-327">[Working with Members, Tuples, and Sets &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md) </span></span>  
 <span data-ttu-id="0aa3f-328">[Визуальные итоги и невизуальные итоги](visual-totals-and-non-visual-totals.md) </span><span class="sxs-lookup"><span data-stu-id="0aa3f-328">[Visual Totals and Non Visual Totals](visual-totals-and-non-visual-totals.md) </span></span>  
 <span data-ttu-id="0aa3f-329">[Справочник по языку многомерных выражений &#40;&#41;многомерных выражений](/sql/mdx/mdx-language-reference-mdx) </span><span class="sxs-lookup"><span data-stu-id="0aa3f-329">[MDX Language Reference &#40;MDX&#41;](/sql/mdx/mdx-language-reference-mdx) </span></span>  
 [<span data-ttu-id="0aa3f-330">Справочник по многомерным выражениям (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="0aa3f-330">Multidimensional Expressions &#40;MDX&#41; Reference</span></span>](/sql/mdx/multidimensional-expressions-mdx-reference)  
  
  
