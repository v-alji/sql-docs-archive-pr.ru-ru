---
title: Визуальные итоги и не визуальные итоги | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: ea9d02f2-a668-4547-ade5-e3d077a2e1bd
author: minewiskan
ms.author: owend
ms.openlocfilehash: ddff047be6a819d05276848cbeb430fb8e4c9c2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736983"
---
# <a name="visual-totals-and-non-visual-totals"></a><span data-ttu-id="5bf15-102">Визуальные и невизуальные итоги</span><span class="sxs-lookup"><span data-stu-id="5bf15-102">Visual Totals and Non Visual Totals</span></span>
  <span data-ttu-id="5bf15-103">Visual Totals — это итоги в конце столбца или строки, которые представляют собой сумму всех элементов, видимых в столбце или строке.</span><span class="sxs-lookup"><span data-stu-id="5bf15-103">Visual Totals are totals at the end of a column or row that add up all of the items visible in the column or row.</span></span> <span data-ttu-id="5bf15-104">Это поведение применяется по умолчанию при отображении большинства таблиц.</span><span class="sxs-lookup"><span data-stu-id="5bf15-104">This is the default behavior for most tables when displayed.</span></span> <span data-ttu-id="5bf15-105">Но иногда нужно, чтобы в таблице отображались только определенные столбцы, а итоги выводились для всей строки, в том числе для неотображаемых столбцов.</span><span class="sxs-lookup"><span data-stu-id="5bf15-105">However, there are times when the user wants to display only certain columns in a table but keep the totals for the entire row, including those that are not displayed.</span></span> <span data-ttu-id="5bf15-106">Такие итоги принято называть `Non Visual Totals`, поскольку они складываются из видимых и невидимых значений.</span><span class="sxs-lookup"><span data-stu-id="5bf15-106">These are called `Non Visual Totals`, because the total comes from both the visible and non-visible values.</span></span>  
  
 <span data-ttu-id="5bf15-107">Поведение итогов Non Visual демонстрируется в следующем сценарии.</span><span class="sxs-lookup"><span data-stu-id="5bf15-107">The following scenario demonstrates the behavior of Non Visual totals.</span></span> <span data-ttu-id="5bf15-108">В первом шаге показано поведение по умолчанию для Visual Totals.</span><span class="sxs-lookup"><span data-stu-id="5bf15-108">The first step shows the default behavior of Visual Totals.</span></span>  
  
 <span data-ttu-id="5bf15-109">В следующем примере приведен запрос к [Adventure Works] для получения данных [Reseller Sales Amount] из таблицы, в которой категории товаров расположены по столбцам, а типы торговых посредников — по строкам.</span><span class="sxs-lookup"><span data-stu-id="5bf15-109">The following example is a query of [Adventure Works] to obtain [Reseller Sales Amount] figures in a table where the product categories are the columns and the reseller business types are the rows.</span></span> <span data-ttu-id="5bf15-110">Обратите внимание, что в следующей инструкции SELECT предусмотрено получение итогов по товарам и по торговым посредникам:</span><span class="sxs-lookup"><span data-stu-id="5bf15-110">Note that totals are given for both products and resellers when the following SELECT statement is issued:</span></span>  
  
 `select [Category].members on 0,`  
  
 `[Business Type].members on 1`  
  
 `from [Adventure Works]`  
  
 `where [Measures].[Reseller Sales Amount]`  
  
 <span data-ttu-id="5bf15-111">Она выдает следующие результаты.</span><span class="sxs-lookup"><span data-stu-id="5bf15-111">Produces the following results:</span></span>  
  
|||||||  
|-|-|-|-|-|-|  
||<span data-ttu-id="5bf15-112">**Все продукты**</span><span class="sxs-lookup"><span data-stu-id="5bf15-112">**All Products**</span></span>|<span data-ttu-id="5bf15-113">**Принадлежности**</span><span class="sxs-lookup"><span data-stu-id="5bf15-113">**Accessories**</span></span>|<span data-ttu-id="5bf15-114">**Велосипеды**</span><span class="sxs-lookup"><span data-stu-id="5bf15-114">**Bikes**</span></span>|<span data-ttu-id="5bf15-115">**Clothing**</span><span class="sxs-lookup"><span data-stu-id="5bf15-115">**Clothing**</span></span>|<span data-ttu-id="5bf15-116">**Components**</span><span class="sxs-lookup"><span data-stu-id="5bf15-116">**Components**</span></span>|  
|<span data-ttu-id="5bf15-117">**All Resellers**</span><span class="sxs-lookup"><span data-stu-id="5bf15-117">**All Resellers**</span></span>|<span data-ttu-id="5bf15-118">**$ 80 450 596,98**</span><span class="sxs-lookup"><span data-stu-id="5bf15-118">**$80,450,596.98**</span></span>|<span data-ttu-id="5bf15-119">**$ 571 297,93**</span><span class="sxs-lookup"><span data-stu-id="5bf15-119">**$571,297.93**</span></span>|<span data-ttu-id="5bf15-120">**$ 66 302 381,56**</span><span class="sxs-lookup"><span data-stu-id="5bf15-120">**$66,302,381.56**</span></span>|<span data-ttu-id="5bf15-121">**$ 1 777 840,84**</span><span class="sxs-lookup"><span data-stu-id="5bf15-121">**$1,777,840.84**</span></span>|<span data-ttu-id="5bf15-122">**$ 11 799 076,66**</span><span class="sxs-lookup"><span data-stu-id="5bf15-122">**$11,799,076.66**</span></span>|  
|<span data-ttu-id="5bf15-123">**Specialty Bike Shop**</span><span class="sxs-lookup"><span data-stu-id="5bf15-123">**Specialty Bike Shop**</span></span>|<span data-ttu-id="5bf15-124">**$ 6 756 166,18**</span><span class="sxs-lookup"><span data-stu-id="5bf15-124">**$6,756,166.18**</span></span>|<span data-ttu-id="5bf15-125">**$ 65 125,48**</span><span class="sxs-lookup"><span data-stu-id="5bf15-125">**$65,125.48**</span></span>|<span data-ttu-id="5bf15-126">**$ 6 080 117,73**</span><span class="sxs-lookup"><span data-stu-id="5bf15-126">**$6,080,117.73**</span></span>|<span data-ttu-id="5bf15-127">**$ 252 933,91**</span><span class="sxs-lookup"><span data-stu-id="5bf15-127">**$252,933.91**</span></span>|<span data-ttu-id="5bf15-128">**$ 357 989,07**</span><span class="sxs-lookup"><span data-stu-id="5bf15-128">**$357,989.07**</span></span>|  
|<span data-ttu-id="5bf15-129">**Value Added Reseller**</span><span class="sxs-lookup"><span data-stu-id="5bf15-129">**Value Added Reseller**</span></span>|<span data-ttu-id="5bf15-130">**$ 34 967 517,33**</span><span class="sxs-lookup"><span data-stu-id="5bf15-130">**$34,967,517.33**</span></span>|<span data-ttu-id="5bf15-131">**$ 175 002,81**</span><span class="sxs-lookup"><span data-stu-id="5bf15-131">**$175,002.81**</span></span>|<span data-ttu-id="5bf15-132">**$ 30 892 354,33**</span><span class="sxs-lookup"><span data-stu-id="5bf15-132">**$30,892,354.33**</span></span>|<span data-ttu-id="5bf15-133">**$ 592 385,71**</span><span class="sxs-lookup"><span data-stu-id="5bf15-133">**$592,385.71**</span></span>|<span data-ttu-id="5bf15-134">**$ 3 307 774,48**</span><span class="sxs-lookup"><span data-stu-id="5bf15-134">**$3,307,774.48**</span></span>|  
|<span data-ttu-id="5bf15-135">**Хранилище**</span><span class="sxs-lookup"><span data-stu-id="5bf15-135">**Warehouse**</span></span>|<span data-ttu-id="5bf15-136">**$ 38 726 913,48**</span><span class="sxs-lookup"><span data-stu-id="5bf15-136">**$38,726,913.48**</span></span>|<span data-ttu-id="5bf15-137">**$ 331 169,64**</span><span class="sxs-lookup"><span data-stu-id="5bf15-137">**$331,169.64**</span></span>|<span data-ttu-id="5bf15-138">**$ 29 329 909,50**</span><span class="sxs-lookup"><span data-stu-id="5bf15-138">**$29,329,909.50**</span></span>|<span data-ttu-id="5bf15-139">**$ 932 521,23**</span><span class="sxs-lookup"><span data-stu-id="5bf15-139">**$932,521.23**</span></span>|<span data-ttu-id="5bf15-140">**$ 8 133 313,11**</span><span class="sxs-lookup"><span data-stu-id="5bf15-140">**$8,133,313.11**</span></span>|  
  
## <a name="non-visual-on-rows-and-columns"></a><span data-ttu-id="5bf15-141">Применение режима Non Visual к строкам и столбцам</span><span class="sxs-lookup"><span data-stu-id="5bf15-141">Non-Visual on rows and columns</span></span>  
 <span data-ttu-id="5bf15-142">Чтобы получить таблицу с данными только по товарам Accessories и Clothing и торговым посредникам Value Added Reseller и Warehouse, сохраняя при этом полные итоги, можно написать следующую инструкцию, содержащую предложение NON VISUAL:</span><span class="sxs-lookup"><span data-stu-id="5bf15-142">To produce a table with data only for the Accessories and Clothing products, the Value Added Reseller and Warehouse resellers, yet keeping the overall totals could be written as follows using NON VISUAL:</span></span>  
  
 `select [Category].members on 0,`  
  
 `[Business Type].members on 1`  
  
 `from NON VISUAL (Select {[Category].Accessories, [Category].Clothing} on 0,`  
  
 `{[Business Type].[Value Added Reseller], [Business Type].[Warehouse]} on 1`  
  
 `from [Adventure Works])`  
  
 `where [Measures].[Reseller Sales Amount]`  
  
 <span data-ttu-id="5bf15-143">Она выдает следующие результаты.</span><span class="sxs-lookup"><span data-stu-id="5bf15-143">Produces the following results:</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="5bf15-144">**Все продукты**</span><span class="sxs-lookup"><span data-stu-id="5bf15-144">**All Products**</span></span>|<span data-ttu-id="5bf15-145">**Принадлежности**</span><span class="sxs-lookup"><span data-stu-id="5bf15-145">**Accessories**</span></span>|<span data-ttu-id="5bf15-146">**Clothing**</span><span class="sxs-lookup"><span data-stu-id="5bf15-146">**Clothing**</span></span>|  
|<span data-ttu-id="5bf15-147">**All Resellers**</span><span class="sxs-lookup"><span data-stu-id="5bf15-147">**All Resellers**</span></span>|<span data-ttu-id="5bf15-148">**$ 80 450 596,98**</span><span class="sxs-lookup"><span data-stu-id="5bf15-148">**$80,450,596.98**</span></span>|<span data-ttu-id="5bf15-149">**$ 571 297,93**</span><span class="sxs-lookup"><span data-stu-id="5bf15-149">**$571,297.93**</span></span>|<span data-ttu-id="5bf15-150">**$ 1 777 840,84**</span><span class="sxs-lookup"><span data-stu-id="5bf15-150">**$1,777,840.84**</span></span>|  
|<span data-ttu-id="5bf15-151">**Value Added Reseller**</span><span class="sxs-lookup"><span data-stu-id="5bf15-151">**Value Added Reseller**</span></span>|<span data-ttu-id="5bf15-152">**$ 34 967 517,33**</span><span class="sxs-lookup"><span data-stu-id="5bf15-152">**$34,967,517.33**</span></span>|<span data-ttu-id="5bf15-153">**$ 175 002,81**</span><span class="sxs-lookup"><span data-stu-id="5bf15-153">**$175,002.81**</span></span>|<span data-ttu-id="5bf15-154">**$ 592 385,71**</span><span class="sxs-lookup"><span data-stu-id="5bf15-154">**$592,385.71**</span></span>|  
|<span data-ttu-id="5bf15-155">**Хранилище**</span><span class="sxs-lookup"><span data-stu-id="5bf15-155">**Warehouse**</span></span>|<span data-ttu-id="5bf15-156">**$ 38 726 913,48**</span><span class="sxs-lookup"><span data-stu-id="5bf15-156">**$38,726,913.48**</span></span>|<span data-ttu-id="5bf15-157">**$ 331 169,64**</span><span class="sxs-lookup"><span data-stu-id="5bf15-157">**$331,169.64**</span></span>|<span data-ttu-id="5bf15-158">**$ 932 521,23**</span><span class="sxs-lookup"><span data-stu-id="5bf15-158">**$932,521.23**</span></span>|  
  
## <a name="non-visual-on-rows"></a><span data-ttu-id="5bf15-159">Применение режима Non Visual к строкам</span><span class="sxs-lookup"><span data-stu-id="5bf15-159">Non-Visual on rows</span></span>  
 <span data-ttu-id="5bf15-160">Чтобы создать таблицу, которая визуально рассчитывает итоги столбцов, а для строк приводится истинный итог всех [Category], необходимо выполнить следующий запрос.</span><span class="sxs-lookup"><span data-stu-id="5bf15-160">To produce a table that visually totals the columns but for row totals brings the true total of all [Category], the following query should be issued:</span></span>  
  
 `select [Category].members on 0,`  
  
 `[Business Type].members on 1`  
  
 `from NON VISUAL (Select {[Category].Accessories, [Category].Clothing} on 0`  
  
 `from ( Select {[Business Type].[Value Added Reseller], [Business Type].[Warehouse]} on 0`  
  
 `from [Adventure Works])`  
  
 `)`  
  
 `where [Measures].[Reseller Sales Amount]`  
  
 <span data-ttu-id="5bf15-161">Обратите внимание, что NON VISUAL применяется только к [Category].</span><span class="sxs-lookup"><span data-stu-id="5bf15-161">Note how NON VISUAL is only applied to [Category].</span></span>  
  
 <span data-ttu-id="5bf15-162">Этот запрос выдаст следующий результат.</span><span class="sxs-lookup"><span data-stu-id="5bf15-162">The above query produces the following results:</span></span>  
  
|||||  
|-|-|-|-|  
||<span data-ttu-id="5bf15-163">Все продукты</span><span class="sxs-lookup"><span data-stu-id="5bf15-163">All Products</span></span>|<span data-ttu-id="5bf15-164">Принадлежности</span><span class="sxs-lookup"><span data-stu-id="5bf15-164">Accessories</span></span>|<span data-ttu-id="5bf15-165">Clothing</span><span class="sxs-lookup"><span data-stu-id="5bf15-165">Clothing</span></span>|  
|<span data-ttu-id="5bf15-166">All Resellers</span><span class="sxs-lookup"><span data-stu-id="5bf15-166">All Resellers</span></span>|<span data-ttu-id="5bf15-167">$ 73 694 430,80</span><span class="sxs-lookup"><span data-stu-id="5bf15-167">$73,694,430.80</span></span>|<span data-ttu-id="5bf15-168">$ 506 172,45</span><span class="sxs-lookup"><span data-stu-id="5bf15-168">$506,172.45</span></span>|<span data-ttu-id="5bf15-169">$ 1 524 906,93</span><span class="sxs-lookup"><span data-stu-id="5bf15-169">$1,524,906.93</span></span>|  
|<span data-ttu-id="5bf15-170">Value Added Reseller</span><span class="sxs-lookup"><span data-stu-id="5bf15-170">Value Added Reseller</span></span>|<span data-ttu-id="5bf15-171">$ 34 967 517,33</span><span class="sxs-lookup"><span data-stu-id="5bf15-171">$34,967,517.33</span></span>|<span data-ttu-id="5bf15-172">$ 175 002,81</span><span class="sxs-lookup"><span data-stu-id="5bf15-172">$175,002.81</span></span>|<span data-ttu-id="5bf15-173">$ 592 385,71</span><span class="sxs-lookup"><span data-stu-id="5bf15-173">$592,385.71</span></span>|  
|<span data-ttu-id="5bf15-174">Warehouse</span><span class="sxs-lookup"><span data-stu-id="5bf15-174">Warehouse</span></span>|<span data-ttu-id="5bf15-175">$ 38 726 913,48</span><span class="sxs-lookup"><span data-stu-id="5bf15-175">$38,726,913.48</span></span>|<span data-ttu-id="5bf15-176">$ 331 169,64</span><span class="sxs-lookup"><span data-stu-id="5bf15-176">$331,169.64</span></span>|<span data-ttu-id="5bf15-177">$ 932 521,23</span><span class="sxs-lookup"><span data-stu-id="5bf15-177">$932,521.23</span></span>|  
  
 <span data-ttu-id="5bf15-178">При сравнении с предыдущими результатами можно заметить, что в строке [All Resellers] складываются отображаемые значения [Value Added Reseller] и [Warehouse], однако столбец [All Products] отображает общее значение для всех продуктов, включая те, которые не отображаются.</span><span class="sxs-lookup"><span data-stu-id="5bf15-178">When compared with the previous results, you can observe that the [All Resellers] row now adds up to the displayed values for [Value Added Reseller] and [Warehouse] but that the [All Products] column shows the total value for all products, including those not displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bf15-179">См. также:</span><span class="sxs-lookup"><span data-stu-id="5bf15-179">See Also</span></span>  
 <span data-ttu-id="5bf15-180">[Основные понятия в Analysis Services &#40;многомерных выражений&#41;](../key-concepts-in-mdx-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="5bf15-180">[Key Concepts in MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span></span>  
 <span data-ttu-id="5bf15-181">[Автоматической проверки существования](autoexists.md) </span><span class="sxs-lookup"><span data-stu-id="5bf15-181">[Autoexists](autoexists.md) </span></span>  
 <span data-ttu-id="5bf15-182">[Работа с элементами, кортежами и наборами &#40;многомерных выражениях&#41;](working-with-members-tuples-and-sets-mdx.md) </span><span class="sxs-lookup"><span data-stu-id="5bf15-182">[Working with Members, Tuples, and Sets &#40;MDX&#41;](working-with-members-tuples-and-sets-mdx.md) </span></span>  
 <span data-ttu-id="5bf15-183">[Основные принципы запросов многомерных выражений &#40;Analysis Services&#41;](mdx-query-fundamentals-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="5bf15-183">[MDX Query Fundamentals &#40;Analysis Services&#41;](mdx-query-fundamentals-analysis-services.md) </span></span>  
 <span data-ttu-id="5bf15-184">[Базовый запрос многомерных выражений &#40;многомерные выражения&#41;](mdx-query-the-basic-query.md) </span><span class="sxs-lookup"><span data-stu-id="5bf15-184">[The Basic MDX Query &#40;MDX&#41;](mdx-query-the-basic-query.md) </span></span>  
 <span data-ttu-id="5bf15-185">[Ограничьте запрос с помощью осей запроса и среза &#40;&#41;многомерных выражений](mdx-query-and-slicer-axes-restricting-the-query.md) </span><span class="sxs-lookup"><span data-stu-id="5bf15-185">[Restricting the Query with Query and Slicer Axes &#40;MDX&#41;](mdx-query-and-slicer-axes-restricting-the-query.md) </span></span>  
 [<span data-ttu-id="5bf15-186">Определение контекста куба в запросе (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="5bf15-186">Establishing Cube Context in a Query &#40;MDX&#41;</span></span>](establishing-cube-context-in-a-query-mdx.md)  
  
  
