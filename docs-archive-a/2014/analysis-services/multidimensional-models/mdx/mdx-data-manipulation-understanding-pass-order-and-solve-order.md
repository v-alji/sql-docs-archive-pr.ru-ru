---
title: Основные сведения о порядке прохода и порядке вычисления (многомерные выражения) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- evaluation order [MDX]
- calculation order [MDX]
- SOLVE_ORDER property
- queries [MDX], solve orders
- solve orders [MDX]
- pass orders [MDX]
- expressions [MDX], solve orders
ms.assetid: 7ed7d4ee-4644-4c5d-99a4-c4b429d0203c
author: minewiskan
ms.author: owend
ms.openlocfilehash: d92ccd9d1eeb05272a95c6f429f8c756bcb0022e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658451"
---
# <a name="understanding-pass-order-and-solve-order-mdx"></a><span data-ttu-id="ed7a8-102">Основные сведения о порядке этапов и порядке вычисления (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="ed7a8-102">Understanding Pass Order and Solve Order (MDX)</span></span>
  <span data-ttu-id="ed7a8-103">В ходе вычисления куба в скрипте многомерных выражений вычисление происходит за несколько шагов, в зависимости от того, для какой цели используются те или иные вычислительные функции.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-103">When a cube is calculated as the result of an MDX script, it can go through many stages of computation depending on the use of various calculation-related features.</span></span> <span data-ttu-id="ed7a8-104">Каждый из этих шагов называется этапом вычисления.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-104">Each of these stages is referred to as a calculation pass.</span></span>  
  
 <span data-ttu-id="ed7a8-105">Этап вычисления можно идентифицировать по его порядковому номеру — номеру этапа вычислений.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-105">A calculation pass can be referred to by an ordinal position, called the calculation pass number.</span></span> <span data-ttu-id="ed7a8-106">Количество этапов, необходимых для полного вычисления всех ячеек куба, называется глубиной вычисления куба.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-106">The count of calculation passes that are required to fully compute all the cells of a cube is referred to as the calculation pass depth of the cube.</span></span>  
  
 <span data-ttu-id="ed7a8-107">Таблица фактов и данные обратной записи обрабатываются только на этапе 0.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-107">Fact table and writeback data only impact pass 0.</span></span> <span data-ttu-id="ed7a8-108">Для каждой операции присваивания и каждой инструкции вычисления в скрипте создается новый этап.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-108">Scripts populate data after pass 0; each assignment and calculate statement in a script creates a new pass.</span></span> <span data-ttu-id="ed7a8-109">За пределами скрипта многомерных выражений обращения к этапу с абсолютным номером 0 указывают на последний этап, созданный скриптом для куба.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-109">Outside the MDX script, references to absolute pass 0 refer to the last pass created by the script for the cube.</span></span>  
  
 <span data-ttu-id="ed7a8-110">Вычисляемые элементы создаются на всех этапах, но выражение применяется к текущему этапу.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-110">Calculated members are created at all passes, but the expression is applied at the current pass.</span></span> <span data-ttu-id="ed7a8-111">Предыдущие этапы содержат вычисляемую меру, но со значением NULL.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-111">Prior passes contain the calculated measure, but with a null value.</span></span>  
  
## <a name="solve-order"></a><span data-ttu-id="ed7a8-112">Порядок вычисления</span><span class="sxs-lookup"><span data-stu-id="ed7a8-112">Solve Order</span></span>  
 <span data-ttu-id="ed7a8-113">Порядок вычисления определяет приоритет вычисления конкурирующих выражений.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-113">Solve order determines the priority of calculation in the event of competing expressions.</span></span> <span data-ttu-id="ed7a8-114">В рамках одного этапа порядок вычисления определяет две вещи.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-114">Within a single pass, solve order determines two things:</span></span>  
  
-   <span data-ttu-id="ed7a8-115">Порядок, в котором [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] оцениваются измерения, элементы, вычисляемые элементы, пользовательские свертки и вычисляемые ячейки.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-115">The order in which [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] evaluates dimensions, members, calculated members, custom rollups, and calculated cells.</span></span>  
  
-   <span data-ttu-id="ed7a8-116">Порядок вычисления пользовательских элементов, вычисляемых элементов, пользовательских сверток и вычисляемых ячеек службами [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ed7a8-116">The order in which [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] calculates custom members, calculated members, custom rollup, and calculated cells.</span></span>  
  
 <span data-ttu-id="ed7a8-117">Приоритет имеет элемент с наивысшим порядком вычисления.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-117">The member with the highest solve order takes precedence.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ed7a8-118">Исключением из этого правила является агрегатная функция.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-118">The exception to this precedence is the Aggregate function.</span></span> <span data-ttu-id="ed7a8-119">Порядок разрешения вычисляемых элементов с агрегатной функцией меньше, чем порядок разрешения любой пересекающейся вычисляемой меры</span><span class="sxs-lookup"><span data-stu-id="ed7a8-119">Calculated members with the Aggregate function have a lower solve order than any intersecting calculated measure.</span></span>  
  
## <a name="solve-order-values-and-precedence"></a><span data-ttu-id="ed7a8-120">Значение и приоритет порядка разрешения</span><span class="sxs-lookup"><span data-stu-id="ed7a8-120">Solve Order Values and Precedence</span></span>  
 <span data-ttu-id="ed7a8-121">Порядок вычисления может принимать значения от -8181 до 65535.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-121">Solve order values can range from -8181 to 65535.</span></span> <span data-ttu-id="ed7a8-122">Некоторые значения этого диапазона соответствуют определенным типам вычислений (см. следующую таблицу).</span><span class="sxs-lookup"><span data-stu-id="ed7a8-122">In this range, some solve order values correspond to specific kinds of calculations, as shown in the following table.</span></span>  
  
|<span data-ttu-id="ed7a8-123">Вычисление</span><span class="sxs-lookup"><span data-stu-id="ed7a8-123">Calculation</span></span>|<span data-ttu-id="ed7a8-124">Порядок вычисления</span><span class="sxs-lookup"><span data-stu-id="ed7a8-124">Solve Order</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="ed7a8-125">Нестандартные формулы элементов</span><span class="sxs-lookup"><span data-stu-id="ed7a8-125">Custom member formulas</span></span>|<span data-ttu-id="ed7a8-126">-5119</span><span class="sxs-lookup"><span data-stu-id="ed7a8-126">-5119</span></span>|  
|<span data-ttu-id="ed7a8-127">Унарные операторы</span><span class="sxs-lookup"><span data-stu-id="ed7a8-127">Unary operators</span></span>|<span data-ttu-id="ed7a8-128">-5119</span><span class="sxs-lookup"><span data-stu-id="ed7a8-128">-5119</span></span>|  
|<span data-ttu-id="ed7a8-129">Вычисление визуальных сумм</span><span class="sxs-lookup"><span data-stu-id="ed7a8-129">Visual totals calculation</span></span>|<span data-ttu-id="ed7a8-130">-4096</span><span class="sxs-lookup"><span data-stu-id="ed7a8-130">-4096</span></span>|  
|<span data-ttu-id="ed7a8-131">Другие вычисления (если не указано иное)</span><span class="sxs-lookup"><span data-stu-id="ed7a8-131">All other calculations (if not otherwise specified)</span></span>|<span data-ttu-id="ed7a8-132">0</span><span class="sxs-lookup"><span data-stu-id="ed7a8-132">0</span></span>|  
  
 <span data-ttu-id="ed7a8-133">Настоятельно рекомендуется в качестве порядка вычисления использовать только положительные целочисленные значения.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-133">It is highly recommended that you use only positive integers when setting solve order values.</span></span> <span data-ttu-id="ed7a8-134">При указании значений, меньших, чем значения порядка вычисления из предыдущей таблицы, выполнение этапа вычисления может стать непредсказуемым.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-134">If you assign values that are lower than the solve order values shown in the previous table, the calculation pass can become unpredictable.</span></span> <span data-ttu-id="ed7a8-135">Пусть расчет вычисляемого элемента имеет меньшее значение порядка вычисления, чем значение по умолчанию для пользовательской формулы свертки (-5119).</span><span class="sxs-lookup"><span data-stu-id="ed7a8-135">For example, the calculation for a calculated member receives a solve order value that is lower than the default custom rollup formula value of -5119.</span></span> <span data-ttu-id="ed7a8-136">Из-за более низкого значения порядка вычисления вычисляемые элементы будут рассчитываться перед пользовательскими формулами свертки, что может привести к неверному результату.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-136">Such a low solve order value causes the calculated members to be calculated before the custom rollup formulas, and can produce incorrect results.</span></span>  
  
### <a name="creating-and-changing-solve-order"></a><span data-ttu-id="ed7a8-137">Создание и изменение порядка вычисления</span><span class="sxs-lookup"><span data-stu-id="ed7a8-137">Creating and Changing Solve Order</span></span>  
 <span data-ttu-id="ed7a8-138">Порядок вычисления для вычисляемых элементов и вычисляемых ячеек можно задать в конструкторе кубов на панели **Вычисления**, изменив порядок следования расчетов.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-138">In Cube Designer, on the **Calculations Pane**, you can change the solve order for calculated members and calculated cells by changing the order of the calculations.</span></span>  
  
 <span data-ttu-id="ed7a8-139">В многомерных выражениях для создания и изменения вычисляемых элементов и ячеек используется ключевое слово `SOLVE_ORDER`.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-139">In MDX, you can use the `SOLVE_ORDER` keyword to create or change calculated members and calculated cells.</span></span>  
  
## <a name="solve-order-examples"></a><span data-ttu-id="ed7a8-140">Примеры порядка вычисления</span><span class="sxs-lookup"><span data-stu-id="ed7a8-140">Solve Order Examples</span></span>  
 <span data-ttu-id="ed7a8-141">Чтобы проиллюстрировать потенциальную сложность работы с порядком вычисления, начнем с двух запросов, в каждом из которых проблемы определения порядка вычисления не возникает.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-141">To illustrate the potential complexities of solve order, the following series of MDX queries starts with two queries that each individually have no solve order issues.</span></span> <span data-ttu-id="ed7a8-142">Затем оба запроса объединяются в один, в котором требуется указание порядка вычисления.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-142">These two queries are then combined into a query that requires solve order.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ed7a8-143">Вы можете использовать следующие запросы многомерных выражений в образце многомерной базы данных Adventure Works.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-143">You can run these MDX queries against the Adventure Works sample multidimensional database.</span></span> <span data-ttu-id="ed7a8-144">Загрузить образец [Многомерные модели AdventureWorks SQL Server 2012](https://msftdbprodsamples.codeplex.com/releases/view/55330) вы можете с веб-сайта Codeplex.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-144">You can download the [AdventureWorks Multidimensional Models SQL Server 2012](https://msftdbprodsamples.codeplex.com/releases/view/55330) sample from the codeplex site.</span></span>  
  
### <a name="query-1-differences-in-income-and-expenses"></a><span data-ttu-id="ed7a8-145">Запрос 1 — различия в доходах и расходах</span><span class="sxs-lookup"><span data-stu-id="ed7a8-145">Query 1-Differences in Income and Expenses</span></span>  
 <span data-ttu-id="ed7a8-146">Для следующего запроса многомерных выражений вычислите разницу в продажах и ценах по каждому году, создав простой запрос многомерных выражений на основе следующего примера:</span><span class="sxs-lookup"><span data-stu-id="ed7a8-146">For the first MDX query, calculate the difference in sales and costs for each year by constructing a simple MDX query similar to the following example:</span></span>  
  
```  
WITH   
MEMBER  
[Date].[Calendar].[Year Difference] AS ([Date].[Calendar].[Calendar Year].&[2008] - [Date].[Calendar].[Calendar Year].&[2007] )  
SELECT   
{[Measures].[Internet Sales Amount], [Measures].[Internet Total Product Cost] }  
ON COLUMNS ,  
{ [Date].[Calendar].[Calendar Year].&[2007], [Date].[Calendar].[Calendar Year].&[2008], [Date].[Year Difference] }  
ON ROWS  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="ed7a8-147">В этом запросе есть только один вычисляемый элемент — `Year Difference`.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-147">In this query, there is only one calculated member, `Year Difference`.</span></span> <span data-ttu-id="ed7a8-148">Поскольку вычисляемый элемент только один, указание порядка вычисления не требуется, если только в кубе не используются другие вычисляемые элементы.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-148">Because there is only one calculated member, solve order is not an issue, as long as the cube does not use any calculated members.</span></span>  
  
 <span data-ttu-id="ed7a8-149">Запрос многомерных выражений возвращает примерно следующую результирующую таблицу.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-149">This MDX query produces a result set similar to the following table.</span></span>  
  
||<span data-ttu-id="ed7a8-150">Internet Sales Amount</span><span class="sxs-lookup"><span data-stu-id="ed7a8-150">Internet Sales Amount</span></span>|<span data-ttu-id="ed7a8-151">Общая себестоимость продукции для заказов в Интернете</span><span class="sxs-lookup"><span data-stu-id="ed7a8-151">Internet Total Product Cost</span></span>|  
|-|---------------------------|---------------------------------|  
|<span data-ttu-id="ed7a8-152">**CY 2007**</span><span class="sxs-lookup"><span data-stu-id="ed7a8-152">**CY 2007**</span></span>|<span data-ttu-id="ed7a8-153">$9,791,060.30</span><span class="sxs-lookup"><span data-stu-id="ed7a8-153">$9,791,060.30</span></span>|<span data-ttu-id="ed7a8-154">$5,718,327.17</span><span class="sxs-lookup"><span data-stu-id="ed7a8-154">$5,718,327.17</span></span>|  
|<span data-ttu-id="ed7a8-155">**CY 2008**</span><span class="sxs-lookup"><span data-stu-id="ed7a8-155">**CY 2008**</span></span>|<span data-ttu-id="ed7a8-156">$9,770,899.74</span><span class="sxs-lookup"><span data-stu-id="ed7a8-156">$9,770,899.74</span></span>|<span data-ttu-id="ed7a8-157">$5,721,205.24</span><span class="sxs-lookup"><span data-stu-id="ed7a8-157">$5,721,205.24</span></span>|  
|<span data-ttu-id="ed7a8-158">**Разность за год**</span><span class="sxs-lookup"><span data-stu-id="ed7a8-158">**Year Difference**</span></span>|<span data-ttu-id="ed7a8-159">($ 20 160,56)</span><span class="sxs-lookup"><span data-stu-id="ed7a8-159">($20,160.56)</span></span>|<span data-ttu-id="ed7a8-160">$2,878.06</span><span class="sxs-lookup"><span data-stu-id="ed7a8-160">$2,878.06</span></span>|  
  
### <a name="query-2-percentage-of-income-after-expenses"></a><span data-ttu-id="ed7a8-161">Запрос 2 — процент дохода после расходов</span><span class="sxs-lookup"><span data-stu-id="ed7a8-161">Query 2-Percentage of Income after Expenses</span></span>  
 <span data-ttu-id="ed7a8-162">Второй запрос позволяет вычислить процент чистой прибыли за каждый год. Используется следующий запрос многомерных выражений:</span><span class="sxs-lookup"><span data-stu-id="ed7a8-162">For the second query, calculate the percentage of income after expenses for each year using the following MDX query:</span></span>  
  
```  
WITH   
MEMBER  
[Measures].[Profit Margin] AS   
([Measures].[Internet Sales Amount] - [Measures].[Internet Total Product Cost] ) / [Measures].[Internet Sales Amount] ,  
FORMAT_STRING="Percent"  
SELECT   
{[Measures].[Internet Sales Amount], [Measures].[Internet Total Product Cost], [Measures].[Profit Margin] }  
ON COLUMNS ,  
{ [Date].[Calendar].[Calendar Year].&[2007], [Date].[Calendar].[Calendar Year].&[2008] }  
ON ROWS  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="ed7a8-163">Этот запрос многомерных выражений, как и предыдущий, имеет только один вычисляемый элемент `Profit Margin`, поэтому сложностей с порядком вычисления не возникает.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-163">This MDX query, like the previous one, has only a single calculated member, `Profit Margin`, and therefore does not have any solve order complications.</span></span>  
  
 <span data-ttu-id="ed7a8-164">Запрос многомерных выражений возвращает немного другая результирующая таблица наподобие следующей.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-164">This MDX query produces a slightly different result set, similar to the following table.</span></span>  
  
||<span data-ttu-id="ed7a8-165">Internet Sales Amount</span><span class="sxs-lookup"><span data-stu-id="ed7a8-165">Internet Sales Amount</span></span>|<span data-ttu-id="ed7a8-166">Общая себестоимость продукции для заказов в Интернете</span><span class="sxs-lookup"><span data-stu-id="ed7a8-166">Internet Total Product Cost</span></span>|<span data-ttu-id="ed7a8-167">Коэффициент прибыли</span><span class="sxs-lookup"><span data-stu-id="ed7a8-167">Profit Margin</span></span>|  
|-|---------------------------|---------------------------------|-------------------|  
|<span data-ttu-id="ed7a8-168">**CY 2007**</span><span class="sxs-lookup"><span data-stu-id="ed7a8-168">**CY 2007**</span></span>|<span data-ttu-id="ed7a8-169">$9,791,060.30</span><span class="sxs-lookup"><span data-stu-id="ed7a8-169">$9,791,060.30</span></span>|<span data-ttu-id="ed7a8-170">$5,718,327.17</span><span class="sxs-lookup"><span data-stu-id="ed7a8-170">$5,718,327.17</span></span>|<span data-ttu-id="ed7a8-171">41.60%</span><span class="sxs-lookup"><span data-stu-id="ed7a8-171">41.60%</span></span>|  
|<span data-ttu-id="ed7a8-172">**CY 2008**</span><span class="sxs-lookup"><span data-stu-id="ed7a8-172">**CY 2008**</span></span>|<span data-ttu-id="ed7a8-173">$9,770,899.74</span><span class="sxs-lookup"><span data-stu-id="ed7a8-173">$9,770,899.74</span></span>|<span data-ttu-id="ed7a8-174">$5,721,205.24</span><span class="sxs-lookup"><span data-stu-id="ed7a8-174">$5,721,205.24</span></span>|<span data-ttu-id="ed7a8-175">41.45%</span><span class="sxs-lookup"><span data-stu-id="ed7a8-175">41.45%</span></span>|  
  
 <span data-ttu-id="ed7a8-176">Отличия результирующих наборов первого и второго запросов обусловлены тем, что вычисляемый элемент в них размещен по-разному.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-176">The difference in result sets between the first query and the second query comes from the difference in placement of the calculated member.</span></span> <span data-ttu-id="ed7a8-177">В первом запросе вычисляемый элемент является частью оси ROWS, а во втором — оси COLUMNS.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-177">In the first query, the calculated member is part of the ROWS axis, not the COLUMNS axis shown in the second query.</span></span> <span data-ttu-id="ed7a8-178">Это отличие становится важным в следующем запросе, при объединении вычисляемых элементов в одном запросе многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-178">This difference in placement becomes important in the next query, which combines the two calculated members in a single MDX query.</span></span>  
  
### <a name="query-3-combined-year-difference-and-net-income-calculations"></a><span data-ttu-id="ed7a8-179">Запрос 3. комбинированное годовое различие и вычисления чистого дохода</span><span class="sxs-lookup"><span data-stu-id="ed7a8-179">Query 3-Combined Year Difference and Net Income Calculations</span></span>  
 <span data-ttu-id="ed7a8-180">В последнем запросе, который объединяет два предыдущих в один запрос многомерных выражений, порядок вычисления становится существенным, поскольку вычисления производятся как в столбцах, так и в строках.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-180">In this final query combining both of the previous examples into a single MDX query, solve order becomes important because of the calculations on both columns and rows.</span></span> <span data-ttu-id="ed7a8-181">Чтобы гарантировать верную последовательность вычислений, ее необходимо определить с помощью ключевого слова `SOLVE_ORDER`.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-181">To make sure that the calculations occur in the correct sequence, define the sequence in which the calculations occur by using the `SOLVE_ORDER` keyword.</span></span>  
  
 <span data-ttu-id="ed7a8-182">Ключевое слово `SOLVE_ORDER` указывает порядок вычисления вычисляемых элементов в запросе многомерных выражений или в команде `CREATE MEMBER`.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-182">The `SOLVE_ORDER` keyword specifies the solve order of calculated members in an MDX query or a `CREATE MEMBER` command.</span></span> <span data-ttu-id="ed7a8-183">Целые значения, заданные при помощи ключевого слова `SOLVE_ORDER`, являются относительными, они не обязательно должны начинаться с нуля и следовать друг за другом.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-183">The integer values used with the `SOLVE_ORDER` keyword are relative, do not need to start at zero, and do not need to be consecutive.</span></span> <span data-ttu-id="ed7a8-184">В многомерных выражениях они лишь сообщают, что элементы следует рассчитывать на основе значений, полученных при расчете других элементов с более высоким порядком разрешения.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-184">The value simply tells MDX to calculate a member based on values derived from calculating members with a higher value.</span></span> <span data-ttu-id="ed7a8-185">Если в определении вычисляемого элемента не указано ключевое слово `SOLVE_ORDER`, значением порядка разрешения по умолчанию для этого вычисляемого элемента является ноль.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-185">If a calculated member is defined without the `SOLVE_ORDER` keyword, the default value of that calculated member is zero.</span></span>  
  
 <span data-ttu-id="ed7a8-186">Например, если объединить вычисления двух первых запросов многомерных выражений, то два вычисляемых элемента — `Year Difference` и `Profit Margin`— пересекаются в одной ячейке результирующего набора данных в примере запроса многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-186">For example, if you combine the calculations used in the first two example queries, the two calculated members, `Year Difference` and `Profit Margin`, intersect at a single cell in the result dataset of the MDX query example.</span></span> <span data-ttu-id="ed7a8-187">Единственным способом определения последовательности вычисления службами [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] значения этой ячейки является указание порядка вычисления.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-187">The only way to determine how [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] will evaluate this cell is by the solve order.</span></span> <span data-ttu-id="ed7a8-188">Формулы, используемые для расчета значения этой ячейки, возвращают различные результаты в зависимости от указанного порядка вычисления данных вычисляемых элементов.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-188">The formulas that are used to construct this cell will produce different results depending upon the solve order of the two calculated members.</span></span>  
  
 <span data-ttu-id="ed7a8-189">Для начала объединим вычисления из предыдущих двух примеров в следующий запрос многомерных выражений:</span><span class="sxs-lookup"><span data-stu-id="ed7a8-189">First, try combining the calculations used in the first two queries in the following MDX query:</span></span>  
  
```  
WITH   
MEMBER  
[Date].[Calendar].[Year Difference] AS ([Date].[Calendar].[Calendar Year].&[2008] - [Date].[Calendar].[Calendar Year].&[2007] ) ,  
SOLVE_ORDER = 1  
MEMBER  
[Measures].[Profit Margin] AS   
( [Measures].[Internet Sales Amount] - [Measures].[Internet Total Product Cost] ) / [Measures].[Internet Sales Amount] ,  
FORMAT_STRING="Percent" ,  
SOLVE_ORDER = 2  
SELECT   
{[Measures].[Internet Sales Amount], [Measures].[Internet Total Product Cost], [Measures].[Profit Margin] }  
ON COLUMNS ,  
{ [Date].[Calendar].[Calendar Year].&[2007], [Date].[Calendar].[Calendar Year].&[2008], [Date].[Year Difference] }  
ON ROWS  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="ed7a8-190">В этом совмещенном запросе многомерных выражений формула `Profit Margin` имеет наивысший порядок вычисления, поэтому она будет приоритетной при пересечении двух выражений.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-190">In this combined MDX query example, `Profit Margin` has the highest solve order, so it takes precedence when the two expressions interact.</span></span> [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] <span data-ttu-id="ed7a8-191">вычисляют значение рассматриваемой ячейки по формуле `Profit Margin` .</span><span class="sxs-lookup"><span data-stu-id="ed7a8-191">evaluates the cell in question by using the `Profit Margin` formula.</span></span> <span data-ttu-id="ed7a8-192">Результат этих вложенных вычислений приведен в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-192">The results of this nested calculation, as shown in the following table.</span></span>  
  
||<span data-ttu-id="ed7a8-193">Internet Sales Amount</span><span class="sxs-lookup"><span data-stu-id="ed7a8-193">Internet Sales Amount</span></span>|<span data-ttu-id="ed7a8-194">Общая себестоимость продукции для заказов в Интернете</span><span class="sxs-lookup"><span data-stu-id="ed7a8-194">Internet Total Product Cost</span></span>|<span data-ttu-id="ed7a8-195">Коэффициент прибыли</span><span class="sxs-lookup"><span data-stu-id="ed7a8-195">Profit Margin</span></span>|  
|-|---------------------------|---------------------------------|-------------------|  
|<span data-ttu-id="ed7a8-196">**CY 2007**</span><span class="sxs-lookup"><span data-stu-id="ed7a8-196">**CY 2007**</span></span>|<span data-ttu-id="ed7a8-197">$9,791,060.30</span><span class="sxs-lookup"><span data-stu-id="ed7a8-197">$9,791,060.30</span></span>|<span data-ttu-id="ed7a8-198">$5,718,327.17</span><span class="sxs-lookup"><span data-stu-id="ed7a8-198">$5,718,327.17</span></span>|<span data-ttu-id="ed7a8-199">41.60%</span><span class="sxs-lookup"><span data-stu-id="ed7a8-199">41.60%</span></span>|  
|<span data-ttu-id="ed7a8-200">**CY 2008**</span><span class="sxs-lookup"><span data-stu-id="ed7a8-200">**CY 2008**</span></span>|<span data-ttu-id="ed7a8-201">$9,770,899.74</span><span class="sxs-lookup"><span data-stu-id="ed7a8-201">$9,770,899.74</span></span>|<span data-ttu-id="ed7a8-202">$5,721,205.24</span><span class="sxs-lookup"><span data-stu-id="ed7a8-202">$5,721,205.24</span></span>|<span data-ttu-id="ed7a8-203">41.45%</span><span class="sxs-lookup"><span data-stu-id="ed7a8-203">41.45%</span></span>|  
|<span data-ttu-id="ed7a8-204">**Разность за год**</span><span class="sxs-lookup"><span data-stu-id="ed7a8-204">**Year Difference**</span></span>|<span data-ttu-id="ed7a8-205">($ 20 160,56)</span><span class="sxs-lookup"><span data-stu-id="ed7a8-205">($20,160.56)</span></span>|<span data-ttu-id="ed7a8-206">$2,878.06</span><span class="sxs-lookup"><span data-stu-id="ed7a8-206">$2,878.06</span></span>|<span data-ttu-id="ed7a8-207">114,28 %</span><span class="sxs-lookup"><span data-stu-id="ed7a8-207">114.28%</span></span>|  
  
 <span data-ttu-id="ed7a8-208">Результат в общей ячейке вычисляется по формуле `Profit Margin`.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-208">The result in the shared cell is based on the formula for `Profit Margin`.</span></span> <span data-ttu-id="ed7a8-209">Иными словами, службы [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] вычисляют результат общей ячейки с данными `Year Difference` по следующей формуле (для удобства результат округляется):</span><span class="sxs-lookup"><span data-stu-id="ed7a8-209">That is, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] calculates the result in the shared cell with the `Year Difference` data, producing the following formula (the result is rounded for clarity):</span></span>  
  
```  
((9,770,899.74 - 9,791,060.30) - (5,721,205.24 - 5,718,327.17)) / (9,770,899.74 - 9,791,060.30) = 1.14275744   
```  
  
 <span data-ttu-id="ed7a8-210">,</span><span class="sxs-lookup"><span data-stu-id="ed7a8-210">or</span></span>  
  
```  
(23,038.63) / (20,160.56) = 114.28%  
```  
  
 <span data-ttu-id="ed7a8-211">Это в корне неверно.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-211">This is clearly incorrect.</span></span> <span data-ttu-id="ed7a8-212">Однако если в запросе многомерных выражений будет изменен порядок вычисления вычисляемых элементов, то службы [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] вычислят результат в общей ячейке иначе.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-212">However, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] calculates the result in the shared cell differently if you switch the solve orders for the calculated members in the MDX query.</span></span> <span data-ttu-id="ed7a8-213">В следующем объединенном запросе многомерных выражений порядок вычисления вычисляемых элементов изменен на обратный.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-213">The following combined MDX query reverses the solve order for the calculated members:</span></span>  
  
```  
WITH   
MEMBER  
[Date].[Calendar].[Year Difference] AS ([Date].[Calendar].[Calendar Year].&[2008] - [Date].[Calendar].[Calendar Year].&[2007] ) ,  
SOLVE_ORDER = 2  
MEMBER  
[Measures].[Profit Margin] AS   
( [Measures].[Internet Sales Amount] - [Measures].[Internet Total Product Cost] ) / [Measures].[Internet Sales Amount] ,  
FORMAT_STRING="Percent" ,  
SOLVE_ORDER = 1  
SELECT   
{[Measures].[Internet Sales Amount], [Measures].[Internet Total Product Cost], [Measures].[Profit Margin] }  
ON COLUMNS ,  
{ [Date].[Calendar].[Calendar Year].&[2007], [Date].[Calendar].[Calendar Year].&[2008], [Date].[Year Difference] }  
ON ROWS  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="ed7a8-214">Поскольку порядок разрешения вычисляемых элементов изменился, для вычисления значения ячейки службы [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] будут использовать формулу `Year Difference` , что приведет к следующим результатам.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-214">As the order of the calculated members has been switched, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] uses the `Year Difference` formula to evaluate the cell, as shown in the following table.</span></span>  
  
||<span data-ttu-id="ed7a8-215">Internet Sales Amount</span><span class="sxs-lookup"><span data-stu-id="ed7a8-215">Internet Sales Amount</span></span>|<span data-ttu-id="ed7a8-216">Общая себестоимость продукции для заказов в Интернете</span><span class="sxs-lookup"><span data-stu-id="ed7a8-216">Internet Total Product Cost</span></span>|<span data-ttu-id="ed7a8-217">Коэффициент прибыли</span><span class="sxs-lookup"><span data-stu-id="ed7a8-217">Profit Margin</span></span>|  
|-|---------------------------|---------------------------------|-------------------|  
|<span data-ttu-id="ed7a8-218">**CY 2007**</span><span class="sxs-lookup"><span data-stu-id="ed7a8-218">**CY 2007**</span></span>|<span data-ttu-id="ed7a8-219">$9,791,060.30</span><span class="sxs-lookup"><span data-stu-id="ed7a8-219">$9,791,060.30</span></span>|<span data-ttu-id="ed7a8-220">$5,718,327.17</span><span class="sxs-lookup"><span data-stu-id="ed7a8-220">$5,718,327.17</span></span>|<span data-ttu-id="ed7a8-221">41.60%</span><span class="sxs-lookup"><span data-stu-id="ed7a8-221">41.60%</span></span>|  
|<span data-ttu-id="ed7a8-222">**CY 2008**</span><span class="sxs-lookup"><span data-stu-id="ed7a8-222">**CY 2008**</span></span>|<span data-ttu-id="ed7a8-223">$9,770,899.74</span><span class="sxs-lookup"><span data-stu-id="ed7a8-223">$9,770,899.74</span></span>|<span data-ttu-id="ed7a8-224">$5,721,205.24</span><span class="sxs-lookup"><span data-stu-id="ed7a8-224">$5,721,205.24</span></span>|<span data-ttu-id="ed7a8-225">41.45%</span><span class="sxs-lookup"><span data-stu-id="ed7a8-225">41.45%</span></span>|  
|<span data-ttu-id="ed7a8-226">**Разность за год**</span><span class="sxs-lookup"><span data-stu-id="ed7a8-226">**Year Difference**</span></span>|<span data-ttu-id="ed7a8-227">($ 20 160,56)</span><span class="sxs-lookup"><span data-stu-id="ed7a8-227">($20,160.56)</span></span>|<span data-ttu-id="ed7a8-228">$2,878.06</span><span class="sxs-lookup"><span data-stu-id="ed7a8-228">$2,878.06</span></span>|<span data-ttu-id="ed7a8-229">(0.15%)</span><span class="sxs-lookup"><span data-stu-id="ed7a8-229">(0.15%)</span></span>|  
  
 <span data-ttu-id="ed7a8-230">Поскольку в этом запросе используется формула `Year Difference` с данными `Profit Margin` , то формулу для общей ячейки можно записать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ed7a8-230">Because this query uses the `Year Difference` formula with the `Profit Margin` data, the formula for the shared cell resembles the following calculation:</span></span>  
  
```  
(($9,770,899.74 - 5,721,205.24) / $9,770,899.74) - ((9,791,060.30 - 5,718,327.17) / 9,791,060.30) = -0.15   
```  
  
 <span data-ttu-id="ed7a8-231">Или</span><span class="sxs-lookup"><span data-stu-id="ed7a8-231">Or</span></span>  
  
```  
0.4145 - 0.4160= -0.15  
```  
  
## <a name="additional-considerations"></a><span data-ttu-id="ed7a8-232">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="ed7a8-232">Additional Considerations</span></span>  
 <span data-ttu-id="ed7a8-233">Работать с порядками вычисления весьма сложно, особенно в кубах с большим количеством измерений, содержащих вычисляемые элементы, пользовательские формулы сверток и вычисляемые ячейки.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-233">Solve order can be a very complex issue to deal with, especially in cubes with a high number of dimensions involving calculated member, custom rollup formulas, or calculated cells.</span></span> <span data-ttu-id="ed7a8-234">При выполнении службами [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] запроса многомерных выражений [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] принимает во внимание порядок вычисления всех элементов, рассчитываемых на данном этапе, включая измерения куба, указанные в запросе.</span><span class="sxs-lookup"><span data-stu-id="ed7a8-234">When [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] evaluates an MDX query, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] takes into account the solve order values for everything involved within a given pass, including the dimensions of the cube specified in the MDX query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed7a8-235">См. также:</span><span class="sxs-lookup"><span data-stu-id="ed7a8-235">See Also</span></span>  
 <span data-ttu-id="ed7a8-236">[CalculationCurrentPass &#40;&#41;многомерных выражений](/sql/mdx/calculationcurrentpass-mdx) </span><span class="sxs-lookup"><span data-stu-id="ed7a8-236">[CalculationCurrentPass &#40;MDX&#41;](/sql/mdx/calculationcurrentpass-mdx) </span></span>  
 <span data-ttu-id="ed7a8-237">[CalculationPassValue &#40;&#41;многомерных выражений](/sql/mdx/calculationpassvalue-mdx) </span><span class="sxs-lookup"><span data-stu-id="ed7a8-237">[CalculationPassValue &#40;MDX&#41;](/sql/mdx/calculationpassvalue-mdx) </span></span>  
 <span data-ttu-id="ed7a8-238">[Инструкция CREATE MEMBER &#40;&#41;многомерных выражений](/sql/mdx/mdx-data-definition-create-member) </span><span class="sxs-lookup"><span data-stu-id="ed7a8-238">[CREATE MEMBER Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-member) </span></span>  
 [<span data-ttu-id="ed7a8-239">Манипулирование данными (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="ed7a8-239">Manipulating Data &#40;MDX&#41;</span></span>](mdx-data-manipulation-manipulating-data.md)  
  
