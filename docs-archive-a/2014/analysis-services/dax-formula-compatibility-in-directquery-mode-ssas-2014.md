---
title: Совместимость формул DAX в режиме DirectQuery (SSAS 2014) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: de83cfa9-9ffe-4e24-9c74-96a3876cb4bd
author: minewiskan
ms.author: owend
ms.openlocfilehash: acaac82d6930787a45281c0e942def8df764f4f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658532"
---
# <a name="dax-formula-compatibility-in-directquery-mode-ssas-2014"></a><span data-ttu-id="b13bf-102">Совместимость формул DAX в режиме DirectQuery (SSAS 2014)</span><span class="sxs-lookup"><span data-stu-id="b13bf-102">DAX Formula Compatibility in DirectQuery Mode (SSAS 2014)</span></span>
<span data-ttu-id="b13bf-103">Язык выражений анализа данных (DAX) можно использовать для создания мер и других пользовательских формул для использования в Analysis Services табличных моделях, [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] моделях данных в книгах Excel и Power BI Desktop моделях данных.</span><span class="sxs-lookup"><span data-stu-id="b13bf-103">The Data Analysis Expression language (DAX) can be used to create measures and other custom formulas for use in Analysis Services Tabular models, [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] data models in Excel workbooks, and Power BI Desktop data models.</span></span> <span data-ttu-id="b13bf-104">В большинстве случаев модели, создаваемые в этих средах, идентичны, и вы можете использовать одни и те же меры, отношения и ключевые показатели эффективности и т. д. Однако при создании Analysis Services табличной модели и развертывании ее в режиме DirectQuery существуют некоторые ограничения на формулы, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="b13bf-104">In most respects, the models you create in these environments are identical, and you can use the same measures, relationships, and KPIs, etc. However, if you author an Analysis Services Tabular model and deploy it in DirectQuery mode, there are some restrictions on the formulas that you can use.</span></span> <span data-ttu-id="b13bf-105">В этом разделе представлен обзор этих различий, перечислены функции, которые не поддерживаются в SQL Server 2014 Analysis Services табличной модели на уровне совместимости 1100 или 1103 и в режиме DirectQuery, а также перечислены поддерживаемые функции, но могут возвращать различные результаты.</span><span class="sxs-lookup"><span data-stu-id="b13bf-105">This topic provides an overview of those differences, lists the functions that are not supported in SQL Server 2014 Analysis Services tabulars model at compatibility level 1100 or 1103 and in DirectQuery mode, and lists the functions that are supported but might return different results.</span></span>  
  
<span data-ttu-id="b13bf-106">В этом разделе мы используем термин « *модель в памяти* » для ссылки на табличные модели, которые являются полностью размещенными в памяти кэшированными данными на Analysis Services сервере, работающем в табличном режиме.</span><span class="sxs-lookup"><span data-stu-id="b13bf-106">Within this topic, we use the term *in-memory model* to refer to  Tabular models, which are fully hosted in-memory cached data on an Analysis Services server running in Tabular mode.</span></span> <span data-ttu-id="b13bf-107">Мы используем *модели DirectQuery* для обращения к табличным моделям, которые были созданы и (или) развернуты в режиме DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="b13bf-107">We use *DirectQuery models* to refer to Tabular models that have been authored and/or deployed in DirectQuery mode.</span></span> <span data-ttu-id="b13bf-108">Сведения о режиме DirectQuery см. в разделе [режим DirectQuery (табличные службы SSAS)](https://msdn.microsoft.com/45ad2965-05ec-4fb1-a164-d8060b562ea5).</span><span class="sxs-lookup"><span data-stu-id="b13bf-108">For information about DirectQuery mode, see [DirectQuery Mode (SSAS Tabular)](https://msdn.microsoft.com/45ad2965-05ec-4fb1-a164-d8060b562ea5).</span></span>  
  
  
## <a name="differences-between-in-memory-and-directquery-mode"></a><a name="bkmk_SemanticDifferences"></a><span data-ttu-id="b13bf-109">Различия между режимами в памяти и DirectQuery</span><span class="sxs-lookup"><span data-stu-id="b13bf-109">Differences between in-memory and DirectQuery mode</span></span>  
<span data-ttu-id="b13bf-110">При опросе модели, развернутой в режиме DirectQuery, могут возвращаться результаты, отличные от результатов, получаемых при развертывании той же самой модели в памяти.</span><span class="sxs-lookup"><span data-stu-id="b13bf-110">Queries on a model deployed in DirectQuery mode can return different results than the same model deployed in in-memory mode.</span></span> <span data-ttu-id="b13bf-111">Это обусловлено тем, что при использовании DirectQuery данные запрашиваются непосредственно из реляционного хранилища данных, а агрегаты, необходимые для формул, выполняются с помощью соответствующего реляционного механизма, а не с помощью подсистемы аналитики в памяти xVelocity (VertiPaq) для хранения и вычисления.</span><span class="sxs-lookup"><span data-stu-id="b13bf-111">This is because with DirectQuery, data is queried directly from a relational data store and aggregations required by formulas are performed using the relevant relational engine, rather than using the xVelocity in-memory analytics engine (VertiPaq) for storage and calculation.</span></span>  
  
<span data-ttu-id="b13bf-112">Например, существуют различия между тем, как некоторые реляционные хранилища данных обрабатывают цифровые значения, даты, значения NULL и т. п.</span><span class="sxs-lookup"><span data-stu-id="b13bf-112">For example, there are differences in the way that certain relational data stores handle numeric values, dates, nulls, and so forth.</span></span>  
  
<span data-ttu-id="b13bf-113">По контрасту язык DAX предназначен для максимально приближенной эмуляции функций Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="b13bf-113">In contrast, the DAX language is intended to emulate as closely as possible the behavior of functions in Microsoft Excel.</span></span> <span data-ttu-id="b13bf-114">Например, при обработке значений NULL, пустых строк и нулевых значений Excel выполняет попытку найти лучший ответ вне зависимости от точного типа данных, поэтому механизм xVelocity выполняет это же действие.</span><span class="sxs-lookup"><span data-stu-id="b13bf-114">For example, when handling nulls, empty strings and zero values, Excel attempts to provide the best answer regardless of the precise data type, and therefore the xVelocity engine does the same.</span></span> <span data-ttu-id="b13bf-115">Однако когда табличная модель развертывается в режиме DirectQuery и происходит передача формул в реляционный источник данных для их оценки, данные должны обрабатываться в соответствии с семантикой реляционного источника данных, в которой обычно требуется точно определенная обработка пустых строк, в отличие от значений NULL.</span><span class="sxs-lookup"><span data-stu-id="b13bf-115">However, when a tabular model is deployed in DirectQuery mode and passes formulas to a relational data source for evaluation, the data must be handled according to the semantics of the relational data source, which typically require distinct handling of empty strings vs. nulls.</span></span> <span data-ttu-id="b13bf-116">По этой причине при обработке одной и той же формулы могут получаться различные результаты при оценке кэшируемых данных и данных, получаемых непосредственно от реляционного источника.</span><span class="sxs-lookup"><span data-stu-id="b13bf-116">For this reason, the same formula might return a different result when evaluated against cached data and against data returned solely from the relational store.</span></span>  
  
<span data-ttu-id="b13bf-117">Кроме того, некоторые функции нельзя использовать в режиме DirectQuery, поскольку вычисление потребует, чтобы данные в текущем контексте отправлялись в реляционный источник данных в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="b13bf-117">Additionally, some functions cannot be used at all in DirectQuery mode because the calculation would require the data in the current context be sent to the relational data source as a parameter.</span></span> <span data-ttu-id="b13bf-118">Например, меры в [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] книге часто используют функции логики операций со временем, которые ссылаются на диапазоны дат, доступные в книге.</span><span class="sxs-lookup"><span data-stu-id="b13bf-118">For example, measures in a [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] workbook often use time-intelligence functions that reference date ranges available within the workbook.</span></span> <span data-ttu-id="b13bf-119">Такие формулы, как правило, не могут использоваться в режиме DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="b13bf-119">Such formulas generally cannot be used in DirectQuery mode.</span></span>  
  
## <a name="semantic-differences"></a><span data-ttu-id="b13bf-120">Семантические различия</span><span class="sxs-lookup"><span data-stu-id="b13bf-120">Semantic differences</span></span>  
<span data-ttu-id="b13bf-121">В этом разделе приведен список типов возможных семантических различий, а также описаны ограничения, применимые к способу использования функций или к результатам запроса.</span><span class="sxs-lookup"><span data-stu-id="b13bf-121">This section lists the types of semantic differences that you can expect, and describes any limitations that might apply to the usage of functions or to query results.</span></span>  
  
### <a name="comparisons"></a><a name="bkmk_Comparisons"></a><span data-ttu-id="b13bf-122">Сравнение</span><span class="sxs-lookup"><span data-stu-id="b13bf-122">Comparisons</span></span>  
<span data-ttu-id="b13bf-123">Язык DAX в моделях, находящихся в памяти, поддерживает сравнения двух выражений, разрешающихся в скалярные значения различных типов данных.</span><span class="sxs-lookup"><span data-stu-id="b13bf-123">DAX in in-memory models support comparisons of two expressions that resolve to scalar values of different data types.</span></span> <span data-ttu-id="b13bf-124">Однако модели, развертываемые в режиме DirectQuery, используют типы данных и операторы сравнения, заданные в реляционном механизме. Это может привести к различиям в результатах.</span><span class="sxs-lookup"><span data-stu-id="b13bf-124">However, models that are deployed in DirectQuery mode use the data types and comparison operators of the relational engine, and therefore might return different results.</span></span>  
  
<span data-ttu-id="b13bf-125">В следующих примерах сравнения всегда будет выводиться ошибка при вычислении средствами источника данных DirectQuery:</span><span class="sxs-lookup"><span data-stu-id="b13bf-125">The following comparisons will always return an error when used in a calculation on a DirectQuery data source:</span></span>  
  
-   <span data-ttu-id="b13bf-126">Числовой тип данных и любой тип строковых данных</span><span class="sxs-lookup"><span data-stu-id="b13bf-126">Numeric data type compared to any string data type</span></span>  
  
-   <span data-ttu-id="b13bf-127">Числовой тип данных и логическое значение</span><span class="sxs-lookup"><span data-stu-id="b13bf-127">Numeric data type compared to a Boolean value</span></span>  
  
-   <span data-ttu-id="b13bf-128">Любой строковый тип данных и логическое значение</span><span class="sxs-lookup"><span data-stu-id="b13bf-128">Any string data type compared to a Boolean value</span></span>  
  
<span data-ttu-id="b13bf-129">В общем и целом язык DAX более терпим по отношению к несовпадениям типов данных в моделях в памяти. Будет выполнена попытка имплицитного приведения значений до двух раз, как описано в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="b13bf-129">In general, DAX is more forgiving of data type mismatches in in-memory models and will attempt an implicit cast of values up to two times, as described in this section.</span></span> <span data-ttu-id="b13bf-130">Однако формулы, отправленные в реляционное хранилище данных в режиме DirectQuery, оцениваются более строго, согласно правилам реляционного механизма, при этом вероятность ошибки при их обработке более высока.</span><span class="sxs-lookup"><span data-stu-id="b13bf-130">However, formulas sent to a relational data store in DirectQuery mode are evaluated more strictly, following the rules of the relational engine, and are more likely to fail.</span></span>  
  
<span data-ttu-id="b13bf-131">**Сравнение строк и чисел**</span><span class="sxs-lookup"><span data-stu-id="b13bf-131">**Comparisons of strings and numbers**</span></span>  
<span data-ttu-id="b13bf-132">ПРИМЕР: `"2" < 3`</span><span class="sxs-lookup"><span data-stu-id="b13bf-132">EXAMPLE: `"2" < 3`</span></span>  
  
<span data-ttu-id="b13bf-133">Выполняется сравнение текстовой строки и числа при помощи формулы.</span><span class="sxs-lookup"><span data-stu-id="b13bf-133">The formula compares a text string to a number.</span></span> <span data-ttu-id="b13bf-134">Как в режиме DirectQuery, так и в модели в памяти выражение имеет значение **true** .</span><span class="sxs-lookup"><span data-stu-id="b13bf-134">The expression is **true** in both DirectQuery mode and in-memory models.</span></span>  
  
<span data-ttu-id="b13bf-135">В модели в памяти результат — **true** , поскольку результаты в виде строк неявно приводятся к численному типу данных для сравнения с другими числами.</span><span class="sxs-lookup"><span data-stu-id="b13bf-135">In an in-memory model, the result is **true** because numbers as strings are implicitly cast to a numerical data type for comparisons with other numbers.</span></span> <span data-ttu-id="b13bf-136">SQL также неявно приводит текстовые числа как числа для сравнения с числовыми типами данных.</span><span class="sxs-lookup"><span data-stu-id="b13bf-136">SQL also implicitly casts text numbers as numbers for comparison to numerical data types.</span></span>  
  
<span data-ttu-id="b13bf-137">Обратите внимание, что это приводит к изменению поведения первой версии [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] , что возвращало бы **значение false**, поскольку текст "2" всегда будет считаться больше, чем любое число.</span><span class="sxs-lookup"><span data-stu-id="b13bf-137">Note that this represents a change in behavior from the first version of [!INCLUDE[ssGemini](../includes/ssgemini-md.md)], which would return **false**, because the text "2" would always be considered larger than any number.</span></span>  
  
<span data-ttu-id="b13bf-138">**Сравнение текстовых и булевых значений**</span><span class="sxs-lookup"><span data-stu-id="b13bf-138">**Comparison of text with Boolean**</span></span>  
<span data-ttu-id="b13bf-139">ПРИМЕР: `"VERDADERO" = TRUE`</span><span class="sxs-lookup"><span data-stu-id="b13bf-139">EXAMPLE: `"VERDADERO" = TRUE`</span></span>  
  
<span data-ttu-id="b13bf-140">В этом выражении сравнивается текстовая строка с логическим значением.</span><span class="sxs-lookup"><span data-stu-id="b13bf-140">This expression compares a text string with a Boolean value.</span></span> <span data-ttu-id="b13bf-141">Главным образом для моделей DirectQuery или моделей в памяти сравнение строкового значения с логическим значением приводит к ошибке.</span><span class="sxs-lookup"><span data-stu-id="b13bf-141">In general, for DirectQuery or In-Memory models, comparing a string value to a Boolean value results in an error.</span></span> <span data-ttu-id="b13bf-142">Единственным исключением для данного правила являются случаи, когда строка содержит слово **true** или слово **false**. Если строка содержит любые значения true или false, выполняются преобразование в логическое значение и сравнение, приводящее к итоговому логическому результату.</span><span class="sxs-lookup"><span data-stu-id="b13bf-142">The only exceptions to the rule are when the string contains the word **true** or the word **false**; if the string contains any of true or false values, a conversion to Boolean is made and the comparison takes place giving the logical result.</span></span>  
  
<span data-ttu-id="b13bf-143">**Сравнение значений NULL**</span><span class="sxs-lookup"><span data-stu-id="b13bf-143">**Comparison of nulls**</span></span>  
<span data-ttu-id="b13bf-144">ПРИМЕР: `EVALUATE ROW("X", BLANK() = BLANK())`</span><span class="sxs-lookup"><span data-stu-id="b13bf-144">EXAMPLE: `EVALUATE ROW("X", BLANK() = BLANK())`</span></span>  
  
<span data-ttu-id="b13bf-145">В этой формуле сравнивается эквивалент значения NULL в SQL со значением NULL.</span><span class="sxs-lookup"><span data-stu-id="b13bf-145">This formula compares the SQL equivalent of a null to a null.</span></span> <span data-ttu-id="b13bf-146">Возвращается значение **true** для модели в памяти и модели DirectQuery. Затем выполняется подготовка в модели DirectQuery, необходимая для того, чтобы гарантировать похожее поведение модели в памяти.</span><span class="sxs-lookup"><span data-stu-id="b13bf-146">It returns **true** in in-memory and DirectQuery models; a provision is made in DirectQuery model to guarantee similar behavior to in-memory model.</span></span>  
  
<span data-ttu-id="b13bf-147">Обратите внимание, что в Transact-SQL значение NULL никогда не равно NULL.</span><span class="sxs-lookup"><span data-stu-id="b13bf-147">Note that in Transact-SQL, a null is never equal to a null.</span></span> <span data-ttu-id="b13bf-148">Однако в DAX пустое значение равно другому пустому значению.</span><span class="sxs-lookup"><span data-stu-id="b13bf-148">However, in DAX, a blank is equal to another blank.</span></span> <span data-ttu-id="b13bf-149">Такое поведение является одинаковым для всех моделей в памяти.</span><span class="sxs-lookup"><span data-stu-id="b13bf-149">This behavior is the same for all in-memory models.</span></span> <span data-ttu-id="b13bf-150">Важно заметить, что в режиме DirectQuery используется по большей части семантика SQL Server. Однако в этом случае она отделена от него так, что сравнения со значением NULL действуют по-другому.</span><span class="sxs-lookup"><span data-stu-id="b13bf-150">It is important to note that DirectQuery mode uses, most of, the semantics of SQL Server; but, in this case it separates from it giving a new behavior to NULL comparisons.</span></span>  
  
### <a name="casts"></a><a name="bkmk_Casts"></a><span data-ttu-id="b13bf-151">Приведения</span><span class="sxs-lookup"><span data-stu-id="b13bf-151">Casts</span></span>  
  
<span data-ttu-id="b13bf-152">В языке DAX нет функции приведения как таковой, однако в ходе многих операций сравнения и арифметических операций выполняются неявные приведения.</span><span class="sxs-lookup"><span data-stu-id="b13bf-152">There is no cast function as such in DAX, but implicit casts are performed in many comparison and arithmetic operations.</span></span> <span data-ttu-id="b13bf-153">Сравнение или арифметическая операция определяет тип данных для полученного результата.</span><span class="sxs-lookup"><span data-stu-id="b13bf-153">It is the comparison or arithmetic operation that determines the data type of the result.</span></span> <span data-ttu-id="b13bf-154">например следующие.</span><span class="sxs-lookup"><span data-stu-id="b13bf-154">For example,</span></span>  
  
-   <span data-ttu-id="b13bf-155">Логические значения обрабатываются как численные в ходе арифметических операций, например в виде TRUE + 1 или с применением функции к столбцу логических значений.</span><span class="sxs-lookup"><span data-stu-id="b13bf-155">Boolean values are treated as numeric in arithmetic operations, such as TRUE + 1, or the function MIN applied to a column of Boolean values.</span></span> <span data-ttu-id="b13bf-156">Операция НЕ также возвращает числовое значение.</span><span class="sxs-lookup"><span data-stu-id="b13bf-156">A NOT operation also returns a numeric value.</span></span>  
  
-   <span data-ttu-id="b13bf-157">Логические значения при сравнениях или с операторами EXACT, AND, OR, &amp;&amp;или || всегда обрабатываются как логические значения.</span><span class="sxs-lookup"><span data-stu-id="b13bf-157">Boolean values are always treated as logical values in comparisons and when used with EXACT, AND, OR, &amp;&amp;, or ||.</span></span>  
  
<span data-ttu-id="b13bf-158">**Приведение строковых данных в логические**</span><span class="sxs-lookup"><span data-stu-id="b13bf-158">**Cast from string to Boolean**</span></span>  
<span data-ttu-id="b13bf-159">В моделях в памяти и DirectQuery приведение разрешено к логическим значениям только из следующих строк: **""** (пустая строка), **"true"**, **"false"**; , где пустая строка приводится к значению false.</span><span class="sxs-lookup"><span data-stu-id="b13bf-159">In in-memory and DirectQuery models, casts are permitted to Boolean values from these strings only: **""** (empty string), **"true"**, **"false"**; where an empty string casts to false value.</span></span>  
  
<span data-ttu-id="b13bf-160">Приведение к логическому типу данных любой другой строки приводит к ошибке.</span><span class="sxs-lookup"><span data-stu-id="b13bf-160">Casts to the Boolean data type of any other string results in an error.</span></span>  
  
<span data-ttu-id="b13bf-161">**Преобразование из строки в дату и время**</span><span class="sxs-lookup"><span data-stu-id="b13bf-161">**Cast from string to date/time**</span></span>  
<span data-ttu-id="b13bf-162">В режиме DirectQuery преобразования из строковых представлений дат и времени в фактические значения **datetime** ведут себя так же, как и в сервере SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b13bf-162">In DirectQuery mode, casts from string representations of dates and times to actual **datetime** values behave the same way as they do in SQL Server.</span></span>  
  
<span data-ttu-id="b13bf-163">Сведения о правилах, регулирующих приведение строковых значений к типам данных **DateTime** в [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] моделях, см. в [справочнике по синтаксису DAX](/dax/dax-syntax-reference).</span><span class="sxs-lookup"><span data-stu-id="b13bf-163">For information about the rules governing casts from string to **datetime** data types in [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] models, see the [DAX Syntax Reference](/dax/dax-syntax-reference).</span></span>
  
<span data-ttu-id="b13bf-164">Модели, в которых используется хранение данных в памяти, поддерживают более ограниченный диапазон текстовых форматов для дат, чем строковые форматы для дат, поддерживаемые в SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b13bf-164">Models that use the in-memory data store support a more limited range of text formats for dates than the string formats for dates that are supported by SQL Server.</span></span> <span data-ttu-id="b13bf-165">Однако язык DAX поддерживает настраиваемые форматы даты и времени.</span><span class="sxs-lookup"><span data-stu-id="b13bf-165">However, DAX supports custom date and time formats.</span></span>  
  
<span data-ttu-id="b13bf-166">**Преобразование из строки в другие нелогические значения**</span><span class="sxs-lookup"><span data-stu-id="b13bf-166">**Cast from string to other non Boolean values**</span></span>  
<span data-ttu-id="b13bf-167">При преобразовании из строк в нелогические значения режим DirectQuery ведет себя так же, как SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b13bf-167">When casting from strings to non-Boolean values, DirectQuery mode behaves the same as SQL Server.</span></span> <span data-ttu-id="b13bf-168">Дополнительные сведения см. в разделе [Функции CAST и CONVERT (Transact-SQL)](https://msdn.microsoft.com/a87d0850-c670-4720-9ad5-6f5a22343ea8).</span><span class="sxs-lookup"><span data-stu-id="b13bf-168">For more information, see [CAST and CONVERT (Transact-SQL)](https://msdn.microsoft.com/a87d0850-c670-4720-9ad5-6f5a22343ea8).</span></span>  
  
<span data-ttu-id="b13bf-169">**Преобразование из чисел в строку не разрешено**</span><span class="sxs-lookup"><span data-stu-id="b13bf-169">**Cast from numbers to string not allowed**</span></span>  
<span data-ttu-id="b13bf-170">ПРИМЕР: `CONCATENATE(102,",345")`</span><span class="sxs-lookup"><span data-stu-id="b13bf-170">EXAMPLE: `CONCATENATE(102,",345")`</span></span>  
  
<span data-ttu-id="b13bf-171">Преобразование из чисел в строки в SQL Server не допускается.</span><span class="sxs-lookup"><span data-stu-id="b13bf-171">Casting from numbers to strings is not allowed in SQL Server.</span></span>  
  
<span data-ttu-id="b13bf-172">Эта формула возвращает ошибку в табличных моделях и в режиме DirectQuery. Однако в [!INCLUDE[ssGemini](../includes/ssgemini-md.md)]она дает результат.</span><span class="sxs-lookup"><span data-stu-id="b13bf-172">This formula returns an error in tabular models and in DirectQuery mode; however, the formula produces a result in [!INCLUDE[ssGemini](../includes/ssgemini-md.md)].</span></span>  
  
<span data-ttu-id="b13bf-173">**Две попытки преобразования не поддерживаются в DirectQuery**</span><span class="sxs-lookup"><span data-stu-id="b13bf-173">**No support for two-try casts in DirectQuery**</span></span>  
<span data-ttu-id="b13bf-174">Модели в памяти часто пытаются выполнить вторую попытку преобразования после первой неудачной попытки.</span><span class="sxs-lookup"><span data-stu-id="b13bf-174">In-memory models often attempt a second cast when the first one fails.</span></span> <span data-ttu-id="b13bf-175">Этого никогда не происходит в режиме DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="b13bf-175">This never happens in DirectQuery mode.</span></span>  
  
<span data-ttu-id="b13bf-176">ПРИМЕР: `TODAY() + "13:14:15"`</span><span class="sxs-lookup"><span data-stu-id="b13bf-176">EXAMPLE: `TODAY() + "13:14:15"`</span></span>  
  
<span data-ttu-id="b13bf-177">В этом выражении первый параметр принадлежит к типу **datetime** , а второй параметр принадлежит к типу **string**.</span><span class="sxs-lookup"><span data-stu-id="b13bf-177">In this expression, the first parameter has type **datetime** and second parameter has type **string**.</span></span> <span data-ttu-id="b13bf-178">Однако преобразования при комбинировании операндов обрабатываются по-разному.</span><span class="sxs-lookup"><span data-stu-id="b13bf-178">However, the casts when combining the operands are handled differently.</span></span> <span data-ttu-id="b13bf-179">DAX выполняет неявное преобразование из **string** в **double**.</span><span class="sxs-lookup"><span data-stu-id="b13bf-179">DAX will perform an implicit cast from **string** to **double**.</span></span> <span data-ttu-id="b13bf-180">В моделях в памяти в ядре формулы предпринимается попытка преобразования в **double**напрямую и при неудачной попытке последует попытка преобразования в **datetime**.</span><span class="sxs-lookup"><span data-stu-id="b13bf-180">In in-memory models, the formula engine attempts to cast directly to **double**, and if that fails, it will try to cast the string to **datetime**.</span></span>  
  
<span data-ttu-id="b13bf-181">В режиме DirectQuery будут применены только преобразования из **string** в **double** .</span><span class="sxs-lookup"><span data-stu-id="b13bf-181">In DirectQuery mode, only the direct cast from **string** to **double** will be applied.</span></span> <span data-ttu-id="b13bf-182">Если такое преобразование завершается неудачно, при использовании формулы будет возвращена ошибка.</span><span class="sxs-lookup"><span data-stu-id="b13bf-182">If this cast fails, the formula will return an error.</span></span>  
  
### <a name="math-functions-and-arithmetic-operations"></a><a name="bkmk_Math"></a><span data-ttu-id="b13bf-183">Математические функции и арифметические операции</span><span class="sxs-lookup"><span data-stu-id="b13bf-183">Math functions and arithmetic operations</span></span>  
<span data-ttu-id="b13bf-184">При использовании некоторых математических функций в режиме DirectQuery будут возвращены другие результаты. Это происходит из-за различий в базовом типе данных или преобразований, которые применяются во время операций.</span><span class="sxs-lookup"><span data-stu-id="b13bf-184">Some mathematical functions will return different results in DirectQuery mode because of differences in the underlying data type or the casts that can be applied in operations.</span></span> <span data-ttu-id="b13bf-185">Также вышеописанные ограничения в пределах допустимых значений могут отразиться на результате арифметических операций.</span><span class="sxs-lookup"><span data-stu-id="b13bf-185">Also, the restrictions described above on the allowed range of values might affect the outcome of arithmetic operations.</span></span>  
  
<span data-ttu-id="b13bf-186">**Порядок сложения**</span><span class="sxs-lookup"><span data-stu-id="b13bf-186">**Order of addition**</span></span>  
<span data-ttu-id="b13bf-187">При создании формулы, в которой происходит сложение последовательности чисел, модель в памяти может обработать эти числа в ином порядке, чем модель DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="b13bf-187">When you create a formula that adds a series of numbers, an in-memory model might process the numbers in a different order than a DirectQuery model.</span></span>  <span data-ttu-id="b13bf-188">Поэтому при совершении операций с очень большими положительными и отрицательными числами может произойти ошибка в одной операции, хотя в другой может быть выдан результат.</span><span class="sxs-lookup"><span data-stu-id="b13bf-188">Therefore, when you have many very large positive numbers and very large negative numbers, you may get an error in one operation and results in another operation.</span></span>  
  
<span data-ttu-id="b13bf-189">**Использование функции возведения в степень**</span><span class="sxs-lookup"><span data-stu-id="b13bf-189">**Use of the POWER function**</span></span>  
<span data-ttu-id="b13bf-190">ПРИМЕР: `POWER(-64, 1/3)`</span><span class="sxs-lookup"><span data-stu-id="b13bf-190">EXAMPLE: `POWER(-64, 1/3)`</span></span>  
  
<span data-ttu-id="b13bf-191">В режиме DirectQuery при использовании функции возведения в степень не допускается использование отрицательных значений в качестве основания при возведении в дробную степень.</span><span class="sxs-lookup"><span data-stu-id="b13bf-191">In DirectQuery mode, the POWER function cannot use negative values as the base when raised to a fractional exponent.</span></span> <span data-ttu-id="b13bf-192">В SQL Server такое поведение ожидаемо.</span><span class="sxs-lookup"><span data-stu-id="b13bf-192">This is the expected behavior in SQL Server.</span></span>  
  
<span data-ttu-id="b13bf-193">В модели в памяти формула возвращает -4.</span><span class="sxs-lookup"><span data-stu-id="b13bf-193">In an in-memory model, the formula returns -4.</span></span>  
  
<span data-ttu-id="b13bf-194">**Операции численного переполнения**</span><span class="sxs-lookup"><span data-stu-id="b13bf-194">**Numerical overflow operations**</span></span>  
<span data-ttu-id="b13bf-195">В Transact-SQL операции, приводящие к численному переполнению, возвращают ошибку переполнения, поэтому формулы, которые приводят к переполнению, также выдают ошибку в режиме DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="b13bf-195">In Transact-SQL, operations that result in a numerical overflow return an overflow error; therefore, formulas that result in an overflow also raise an error in DirectQuery mode.</span></span>  
  
<span data-ttu-id="b13bf-196">Однако эта же формула при использовании в модели в памяти возвращает 8-байтовое целое.</span><span class="sxs-lookup"><span data-stu-id="b13bf-196">However, the same formula when used in an in-memory model returns an eight-byte integer.</span></span> <span data-ttu-id="b13bf-197">Это происходит потому, что механизм обработки формул не выполняет проверок в случае численного переполнения.</span><span class="sxs-lookup"><span data-stu-id="b13bf-197">That is because the formula engine does not perform checks for numerical overflows.</span></span>  
  
<span data-ttu-id="b13bf-198">**Функции LOG с пробелами возвращают другие результаты**</span><span class="sxs-lookup"><span data-stu-id="b13bf-198">**LOG functions with blanks return different results**</span></span>  
<span data-ttu-id="b13bf-199">SQL Server обрабатывает значения NULL и пустые значения иначе, чем механизм xVelocity.</span><span class="sxs-lookup"><span data-stu-id="b13bf-199">SQL Server handles nulls and blanks differently than the xVelocity engine.</span></span> <span data-ttu-id="b13bf-200">В результате Следующая формула возвращает ошибку в режиме DirectQuery, но возвращают бесконечное значение (-INF) в режиме в памяти.</span><span class="sxs-lookup"><span data-stu-id="b13bf-200">As a result, the following formula returns an error in DirectQuery mode, but return infinity (-inf) in in-memory mode.</span></span>  
  
`EXAMPLE: LOG(blank())`  
  
<span data-ttu-id="b13bf-201">Те же ограничения применяются к другим логарифмическим функциям, LOG10 и LN.</span><span class="sxs-lookup"><span data-stu-id="b13bf-201">The same limitations apply to the other logarithmic functions: LOG10 and LN.</span></span>  
  
<span data-ttu-id="b13bf-202">Дополнительные сведения о типе данных **blank** в DAX см. в разделе [Справочник по синтаксису DAX](/dax/dax-syntax-reference).</span><span class="sxs-lookup"><span data-stu-id="b13bf-202">For more information about the **blank** data type in DAX, see [DAX Syntax Reference](/dax/dax-syntax-reference).</span></span>
  
<span data-ttu-id="b13bf-203">**Деление на 0 и деление на пустые данные**</span><span class="sxs-lookup"><span data-stu-id="b13bf-203">**Division by 0 and division by Blank**</span></span>  
<span data-ttu-id="b13bf-204">В режиме DirectQuery при делении на нуль (0) или при делении на пустые данные (BLANK) всегда выдается ошибка.</span><span class="sxs-lookup"><span data-stu-id="b13bf-204">In DirectQuery mode, division by zero (0) or division by BLANK will always result in an error.</span></span> <span data-ttu-id="b13bf-205">SQL Server не поддерживает концепцию бесконечности, и, поскольку естественным результатом при делении на нуль становится бесконечность, происходит ошибка.</span><span class="sxs-lookup"><span data-stu-id="b13bf-205">SQL Server does not support the notion of infinity, and because the natural result of any division by 0 is infinity, the result is an error.</span></span> <span data-ttu-id="b13bf-206">Однако SQL Server поддерживает деление на значения NULL, а результат всегда должно равняться NULL.</span><span class="sxs-lookup"><span data-stu-id="b13bf-206">However, SQL Server supports division by nulls, and the result must always equal null.</span></span>  
  
<span data-ttu-id="b13bf-207">Вместо того чтобы возвращать различные результаты для этих операций, в режиме DirectQuery оба типа операций (деление на нуль и деление на значение NULL) возвращают ошибку.</span><span class="sxs-lookup"><span data-stu-id="b13bf-207">Rather than return different results for these operations, in DirectQuery mode, both types of operations (division by zero and division by null) return an error.</span></span>  
  
<span data-ttu-id="b13bf-208">Обратите внимание, что в моделях [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] и PowerPivot при делении на нуль также возвращается ошибка.</span><span class="sxs-lookup"><span data-stu-id="b13bf-208">Note that, in Excel and in [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] models, division by zero also returns an error.</span></span> <span data-ttu-id="b13bf-209">При делении на пустые данные возвращаются пустые данные.</span><span class="sxs-lookup"><span data-stu-id="b13bf-209">Division by a blank returns a blank.</span></span>  
  
<span data-ttu-id="b13bf-210">Все следующие выражения допустимы для моделей в памяти, однако при их обработке в режиме DirectQuery произойдет ошибка:</span><span class="sxs-lookup"><span data-stu-id="b13bf-210">The following expressions are all valid in in-memory models, but will fail in DirectQuery mode:</span></span>  
  
`1/BLANK`  
  
`1/0`  
  
`0.0/BLANK`  
  
`0/0`  
  
<span data-ttu-id="b13bf-211">Выражение `BLANK/BLANK` — особый вариант, при котором возвращается `BLANK` как в модели в памяти, так и в режиме DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="b13bf-211">The expression `BLANK/BLANK` is a special case that returns `BLANK` in both for in-memory models, and in DirectQuery mode.</span></span>  
  
### <a name="supported-numeric-and-date-time-ranges"></a><a name="bkmk_Ranges"></a><span data-ttu-id="b13bf-212">Поддерживаемые числовые диапазоны и диапазоны даты и времени</span><span class="sxs-lookup"><span data-stu-id="b13bf-212">Supported numeric and date-time ranges</span></span>  
<span data-ttu-id="b13bf-213">В формулах [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] и табличных моделях в памяти действуют те же ограничения, что и в Excel, в отношении максимально допустимого числа и дат.</span><span class="sxs-lookup"><span data-stu-id="b13bf-213">Formulas in [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] and tabular models in-memory are subject to the same limitations as Excel with regard to maximum allowed values for real numbers and dates.</span></span> <span data-ttu-id="b13bf-214">Однако при возврате максимального значения при операции вычисления или запроса или при преобразовании, приведении, округлении или усечении значений.</span><span class="sxs-lookup"><span data-stu-id="b13bf-214">However, differences can arise when the maximum value is returned from a calculation or query, or when values are converted, cast, rounded, or truncated.</span></span>  
  
-   <span data-ttu-id="b13bf-215">При умножении значений типов **Currency** и **Real** , когда результат превышает максимально допустимое значение, в режиме DirectQuery это не приводит к ошибке и возвращается значение NULL.</span><span class="sxs-lookup"><span data-stu-id="b13bf-215">If values of types **Currency** and **Real** are multiplied, and the result is larger than the maximum possible value, in DirectQuery mode, no error is raised, and a null is returned.</span></span>  
  
-   <span data-ttu-id="b13bf-216">При использовании модели в памяти ошибка не возникает и возвращается максимальное значение.</span><span class="sxs-lookup"><span data-stu-id="b13bf-216">In in-memory models, no error is raised, but the maximum value is returned.</span></span>  
  
<span data-ttu-id="b13bf-217">В общем, поскольку приемлемый диапазон дат различается для Excel и SQL Server, совпадение результатов можно гарантировать только тогда, когда даты находятся в схожих допустимых пределах, что справедливо и по отношению к следующим датам:</span><span class="sxs-lookup"><span data-stu-id="b13bf-217">In general, because the accepted date ranges are different for Excel and SQL Server, results can be guaranteed to match only when dates are within the common date range, which is inclusive of the following dates:</span></span>  
  
-   <span data-ttu-id="b13bf-218">Наиболее ранняя дата: 1 марта 1990 года</span><span class="sxs-lookup"><span data-stu-id="b13bf-218">Earliest date: March 1, 1990</span></span>  
  
-   <span data-ttu-id="b13bf-219">Наиболее поздняя дата: 31 декабря 9999 года</span><span class="sxs-lookup"><span data-stu-id="b13bf-219">Latest date: December 31, 9999</span></span>  
  
<span data-ttu-id="b13bf-220">Если любые даты, используемые в формулах, не попадают в этот диапазон, при выполнении формулы либо произойдет ошибка, либо результаты не будут одинаковыми для двух описываемых случаев.</span><span class="sxs-lookup"><span data-stu-id="b13bf-220">If any dates used in formulas fall outside this range, either the formula will result in an error, or the results will not match.</span></span>  
  
<span data-ttu-id="b13bf-221">**Поддержка функции CEILING для вычислений с плавающей запятой**</span><span class="sxs-lookup"><span data-stu-id="b13bf-221">**Floating point values supported by CEILING**</span></span>  
<span data-ttu-id="b13bf-222">ПРИМЕР: `EVALUATE ROW("x", CEILING(-4.398488E+30, 1))`</span><span class="sxs-lookup"><span data-stu-id="b13bf-222">EXAMPLE: `EVALUATE ROW("x", CEILING(-4.398488E+30, 1))`</span></span>  
  
<span data-ttu-id="b13bf-223">Эквивалент Transact-SQL для функции DAX CEILING поддерживает вычисления с числами 10^19 или меньшими.</span><span class="sxs-lookup"><span data-stu-id="b13bf-223">The Transact-SQL equivalent of the DAX CEILING function only supports values with magnitude of 10^19 or less.</span></span> <span data-ttu-id="b13bf-224">Основное правило состоит в том, что значения с плавающей запятой должны подходить для **bigint**.</span><span class="sxs-lookup"><span data-stu-id="b13bf-224">A rule of thumb is that floating point values should be able to fit into **bigint**.</span></span>  
  
<span data-ttu-id="b13bf-225">**Функции datepart с датами вне диапазона**</span><span class="sxs-lookup"><span data-stu-id="b13bf-225">**Datepart functions with dates that are out of range**</span></span>  
<span data-ttu-id="b13bf-226">Результаты обработки данных в режиме DirectQuery гарантированно совпадают с аналогичными результатами для моделей в памяти только тогда, когда дата, используемая в качестве аргумента, принадлежит диапазону допустимых дат.</span><span class="sxs-lookup"><span data-stu-id="b13bf-226">Results in DirectQuery mode are guaranteed to match those in in-memory models only when the date used as the argument is in the valid date range.</span></span> <span data-ttu-id="b13bf-227">Если эти условия не удовлетворяются, либо возникает ошибка, либо при обработке формулы в режиме DirectQuery и в модели в памяти будут получены разные результаты.</span><span class="sxs-lookup"><span data-stu-id="b13bf-227">If these conditions are not satisfied, either an error will be raised, or the formula will return different results in DirectQuery than in in-memory mode.</span></span>  
  
<span data-ttu-id="b13bf-228">Пример: `MONTH(0)` или `YEAR(0)`</span><span class="sxs-lookup"><span data-stu-id="b13bf-228">EXAMPLE: `MONTH(0)` or `YEAR(0)`</span></span>  
  
<span data-ttu-id="b13bf-229">В режиме DirectQuery выражения возвращают 12 и 1899 соответственно.</span><span class="sxs-lookup"><span data-stu-id="b13bf-229">In DirectQuery mode, the expressions return 12 and 1899, respectively.</span></span>  
  
<span data-ttu-id="b13bf-230">В моделях в памяти выражения возвращают 1 и 1900 соответственно.</span><span class="sxs-lookup"><span data-stu-id="b13bf-230">In in-memory models, the expressions return 1 and 1900, respectively.</span></span>  
  
<span data-ttu-id="b13bf-231">ПРИМЕР:  `EOMONTH(0.0001, 1)`</span><span class="sxs-lookup"><span data-stu-id="b13bf-231">EXAMPLE:  `EOMONTH(0.0001, 1)`</span></span>  
  
<span data-ttu-id="b13bf-232">Результаты этих выражений будут совпадать, только если переданные в качестве параметра данные принадлежат диапазону допустимых дат.</span><span class="sxs-lookup"><span data-stu-id="b13bf-232">The results of this expression will match only when the data supplied as a parameter is within the valid date range.</span></span>  
  
<span data-ttu-id="b13bf-233">Пример: `EOMONTH(blank(), blank())` или `EDATE(blank(), blank())`</span><span class="sxs-lookup"><span data-stu-id="b13bf-233">EXAMPLE: `EOMONTH(blank(), blank())` or `EDATE(blank(), blank())`</span></span>  
  
<span data-ttu-id="b13bf-234">Результаты этого выражения должны совпадать в режиме DirectQuery и в режиме в памяти.</span><span class="sxs-lookup"><span data-stu-id="b13bf-234">The results of this expression should be the same in DirectQuery mode and in-memory mode.</span></span>  
  
<span data-ttu-id="b13bf-235">**Усечение временных значений**</span><span class="sxs-lookup"><span data-stu-id="b13bf-235">**Truncation of time values**</span></span>  
<span data-ttu-id="b13bf-236">ПРИМЕР: `SECOND(1231.04097222222)`</span><span class="sxs-lookup"><span data-stu-id="b13bf-236">EXAMPLE: `SECOND(1231.04097222222)`</span></span>  
  
<span data-ttu-id="b13bf-237">В режиме DirectQuery результат усекается в соответствии с правилами SQL Server и результатом выполнения выражения будет 59.</span><span class="sxs-lookup"><span data-stu-id="b13bf-237">In DirectQuery mode, the result is truncated, following the rules of SQL Server, and the expression evaluates to 59.</span></span>  
  
<span data-ttu-id="b13bf-238">В моделях в памяти результаты каждой промежуточной операции округляются, поэтому выражение принимает значение 0.</span><span class="sxs-lookup"><span data-stu-id="b13bf-238">In in-memory models, the results of each interim operation are rounded; therefore, the expression evaluates to 0.</span></span>  
  
<span data-ttu-id="b13bf-239">В следующем примере показано, как вычисляется это значение:</span><span class="sxs-lookup"><span data-stu-id="b13bf-239">The following example demonstrates how this value is calculated:</span></span>  
  
1.  <span data-ttu-id="b13bf-240">Дробный ввод (0,04097222222) умножается на 24.</span><span class="sxs-lookup"><span data-stu-id="b13bf-240">The fraction of the input (0.04097222222) is multiplied by 24.</span></span>  
  
2.  <span data-ttu-id="b13bf-241">Результирующее значение часа (0,98333333328) умножается на 60.</span><span class="sxs-lookup"><span data-stu-id="b13bf-241">The resulting hour value (0.98333333328) is multiplied by 60.</span></span>  
  
3.  <span data-ttu-id="b13bf-242">Полученное значение в минутах — 58,9999999968.</span><span class="sxs-lookup"><span data-stu-id="b13bf-242">The resulting minute value is 58.9999999968.</span></span>  
  
4.  <span data-ttu-id="b13bf-243">Дробное значение в минутах (0,9999999968) умножается на 60.</span><span class="sxs-lookup"><span data-stu-id="b13bf-243">The fraction of the minute value (0.9999999968) is multiplied by 60.</span></span>  
  
5.  <span data-ttu-id="b13bf-244">Полученное второе значение (59,999999808) округляется до 60.</span><span class="sxs-lookup"><span data-stu-id="b13bf-244">The resulting second value (59.999999808) rounds up to 60.</span></span>  
  
6.  <span data-ttu-id="b13bf-245">60 является эквивалентом 0.</span><span class="sxs-lookup"><span data-stu-id="b13bf-245">60 is equivalent to 0.</span></span>  
  
<span data-ttu-id="b13bf-246">**Тип данных SQL Time не поддерживается**</span><span class="sxs-lookup"><span data-stu-id="b13bf-246">**SQL Time data type not supported**</span></span>  
<span data-ttu-id="b13bf-247">Для моделей в памяти не поддерживается использование нового типа данных SQL **Time** .</span><span class="sxs-lookup"><span data-stu-id="b13bf-247">In-memory models do not support use of the new SQL **Time** data type.</span></span> <span data-ttu-id="b13bf-248">В режиме DirectQuery формулы, которые ссылаются на столбцы с этим типом данных, будут возвращать ошибку.</span><span class="sxs-lookup"><span data-stu-id="b13bf-248">In DirectQuery mode, formulas that reference columns with this data type will return an error.</span></span> <span data-ttu-id="b13bf-249">Столбцы данных времени не могут быть импортированы в модель в памяти.</span><span class="sxs-lookup"><span data-stu-id="b13bf-249">Time data columns cannot be imported into an in-memory model.</span></span>  
  
<span data-ttu-id="b13bf-250">Однако в [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] и в кэшированных моделях иногда подсистема приводит значение времени к допустимому типу данных, а формула возвращает результат.</span><span class="sxs-lookup"><span data-stu-id="b13bf-250">However, in [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] and in cached models, sometimes the engine casts the time value to an acceptable data type, and the formula returns a result.</span></span>  
  
<span data-ttu-id="b13bf-251">Такое поведение затрагивает все функции, которые используют столбец дат в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="b13bf-251">This behavior affects all functions that use a date column as a parameter.</span></span>  
  
### <a name="currency"></a><a name="bkmk_Currency"></a><span data-ttu-id="b13bf-252">Режиме</span><span class="sxs-lookup"><span data-stu-id="b13bf-252">Currency</span></span>  
<span data-ttu-id="b13bf-253">В режиме DirectQuery, если результат арифметической операции имеет тип **Currency**, значение должно принадлежать следующему диапазону:</span><span class="sxs-lookup"><span data-stu-id="b13bf-253">In DirectQuery mode, if the result of an arithmetic operation has the type **Currency**, the value must be within the following range:</span></span>  
  
-   <span data-ttu-id="b13bf-254">Минимум: -922337203685477,5808</span><span class="sxs-lookup"><span data-stu-id="b13bf-254">Minimum: -922337203685477.5808</span></span>  
  
-   <span data-ttu-id="b13bf-255">Максимум: 922337203685477,5807</span><span class="sxs-lookup"><span data-stu-id="b13bf-255">Maximum: 922337203685477.5807</span></span>  
  
<span data-ttu-id="b13bf-256">**Сочетание типов данных «Валюта» и «REAL»**</span><span class="sxs-lookup"><span data-stu-id="b13bf-256">**Combining currency and REAL data types**</span></span>  
<span data-ttu-id="b13bf-257">ПРИМЕР: `Currency sample 1`</span><span class="sxs-lookup"><span data-stu-id="b13bf-257">EXAMPLE: `Currency sample 1`</span></span>  
  
<span data-ttu-id="b13bf-258">Если умножить типы данных **Currency** и **Real** и результат окажется выше значения 9223372036854774784 (0x7ffffffffffffc00), в режиме DirectQuery не произойдет ошибки.</span><span class="sxs-lookup"><span data-stu-id="b13bf-258">If **Currency** and **Real** types are multiplied, and the result is larger than 9223372036854774784 (0x7ffffffffffffc00), DirectQuery mode will not raise an error.</span></span>  
  
<span data-ttu-id="b13bf-259">В модели в памяти происходит ошибка, если абсолютное значение результата превышает 922337203685477,4784.</span><span class="sxs-lookup"><span data-stu-id="b13bf-259">In an in-memory model, an error is raised if the absolute value of the result is larger than 922337203685477.4784.</span></span>  
  
<span data-ttu-id="b13bf-260">**Выполнение операции приводит к возникновению значения, не принадлежащего допустимому диапазону**</span><span class="sxs-lookup"><span data-stu-id="b13bf-260">**Operation results in an out-of-range value**</span></span>  
<span data-ttu-id="b13bf-261">ПРИМЕР: `Currency sample 2`</span><span class="sxs-lookup"><span data-stu-id="b13bf-261">EXAMPLE: `Currency sample 2`</span></span>  
  
<span data-ttu-id="b13bf-262">Если операции с любыми двумя значениями типа «Валюта» приводят к значению, не принадлежащему указанному диапазону, в моделях в памяти возникает ошибка, которой, однако, не возникает в случае с моделями DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="b13bf-262">If operations on any two currency values result in a value that is outside the specified range, an error is raised in in-memory models, but not in DirectQuery models.</span></span>  
  
<span data-ttu-id="b13bf-263">**Сочетание типа данных «Валюта» с другими типами данных**</span><span class="sxs-lookup"><span data-stu-id="b13bf-263">**Combining currency with other data types**</span></span>  
<span data-ttu-id="b13bf-264">Деление значений валюты на значения другого числового типа может привести к различным результатам.</span><span class="sxs-lookup"><span data-stu-id="b13bf-264">Division of currency values by values of other numeric types can result in different results.</span></span>  
  
### <a name="aggregation-functions"></a><a name="bkmk_Aggregations"></a><span data-ttu-id="b13bf-265">Агрегатные функции</span><span class="sxs-lookup"><span data-stu-id="b13bf-265">Aggregation functions</span></span>  
<span data-ttu-id="b13bf-266">Статистические функции в таблице с одной строкой возвращают разные результаты.</span><span class="sxs-lookup"><span data-stu-id="b13bf-266">Statistical functions on a table with one row return different results.</span></span> <span data-ttu-id="b13bf-267">Поведение агрегатных функций, выполняемых в отношении пустых таблиц, также отличается для моделей в памяти и моделей DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="b13bf-267">Aggregation functions over empty tables also behave differently in in-memory models than they do in DirectQuery mode.</span></span>  
  
<span data-ttu-id="b13bf-268">**Статистические функции, выполняемые в таблице с одной строкой**</span><span class="sxs-lookup"><span data-stu-id="b13bf-268">**Statistical functions over a table with a single row**</span></span>  
<span data-ttu-id="b13bf-269">Если таблица, используемая в качестве аргумента, содержит один ряд, в режиме DirectQuery статистические функции, такие как STDEV и VAR, возвращают значение NULL.</span><span class="sxs-lookup"><span data-stu-id="b13bf-269">If the table that is used as argument contains a single row, in DirectQuery mode, statistical functions such as STDEV and VAR return null.</span></span>  
  
<span data-ttu-id="b13bf-270">В модели в памяти формула, в которой используются функции STDEV или VAR для таблицы с одним рядом, возвращает ошибку деления на нуль.</span><span class="sxs-lookup"><span data-stu-id="b13bf-270">In an in-memory model, a formula that uses STDEV or VAR over a table with a single row returns a division by zero error.</span></span>  
  
### <a name="text-functions"></a><a name="bkmk_Text"></a><span data-ttu-id="b13bf-271">Текстовые функции</span><span class="sxs-lookup"><span data-stu-id="b13bf-271">Text functions</span></span>  
<span data-ttu-id="b13bf-272">Поскольку реляционные хранилища данных предоставляют типы текстовых данных, отличные от Excel, могут получиться другие результаты при поиске строк либо при работе с подстроками.</span><span class="sxs-lookup"><span data-stu-id="b13bf-272">Because relational data stores provide different text data types than does Excel, you may see different results when searching strings or working with substrings.</span></span> <span data-ttu-id="b13bf-273">Длина строк также может отличаться.</span><span class="sxs-lookup"><span data-stu-id="b13bf-273">The length of strings also can be different.</span></span>  
  
<span data-ttu-id="b13bf-274">В общем, любые функции работы со строками, в которых в качестве аргументов используются столбцы фиксированного размера, могут возвращать различные результаты.</span><span class="sxs-lookup"><span data-stu-id="b13bf-274">In general, any string manipulation functions that use fixed-size columns as arguments can have different results.</span></span>  
  
<span data-ttu-id="b13bf-275">Кроме того, в SQL Server некоторые текстовые функции поддерживают дополнительные аргументы, которые отсутствуют в Excel.</span><span class="sxs-lookup"><span data-stu-id="b13bf-275">Additionally, in SQL Server, some text functions support additional arguments that are not provided in Excel.</span></span> <span data-ttu-id="b13bf-276">Если формула требует отсутствующего аргумента, при использовании модели в памяти можно получить различные результаты или ошибки.</span><span class="sxs-lookup"><span data-stu-id="b13bf-276">If the formula requires the missing argument you can get different results or errors in the in-memory model.</span></span>  
  
<span data-ttu-id="b13bf-277">**В операциях, символ в которых возвращается с помощью функций LEFT, RIGHT и т. п., возможен возврат верного символа, но в другом регистре или результатов может не получиться.**</span><span class="sxs-lookup"><span data-stu-id="b13bf-277">**Operations that return a character using LEFT, RIGHT, etc. may return the correct character but in a different case, or no results**</span></span>  
<span data-ttu-id="b13bf-278">ПРИМЕР: `LEFT(["text"], 2)`</span><span class="sxs-lookup"><span data-stu-id="b13bf-278">EXAMPLE: `LEFT(["text"], 2)`</span></span>  
  
<span data-ttu-id="b13bf-279">В режиме DirectQuery регистр возвращаемого символа всегда точно такой же, как у буквы, сохраненной в базе данных.</span><span class="sxs-lookup"><span data-stu-id="b13bf-279">In DirectQuery mode, the case of the character that is returned is always exactly the same as the letter that is stored in the database.</span></span> <span data-ttu-id="b13bf-280">Однако подсистема xVelocity использует другой алгоритм для сжатия и индексирования значений с целью улучшения производительности.</span><span class="sxs-lookup"><span data-stu-id="b13bf-280">However, the xVelocity engine uses a different algorithm for compression and indexing of values, to improve performance.</span></span>  
  
<span data-ttu-id="b13bf-281">По умолчанию используются параметры сортировки Latin1_General, которые не учитывают регистр, однако учитывают диакритические знаки.</span><span class="sxs-lookup"><span data-stu-id="b13bf-281">By default, the Latin1_General collation is used, which is case-insensitive but accent-sensitive.</span></span> <span data-ttu-id="b13bf-282">Поэтому при наличии нескольких экземпляров текста в нижнем регистре, верхнем регистре или в смешанном регистре все экземпляры считаются одной и той же строкой, а в индексе сохраняется только первый экземпляр строки.</span><span class="sxs-lookup"><span data-stu-id="b13bf-282">Therefore, if there are multiple instances of a text string in lower case, upper case, or mixed case, all instances are considered the same string, and only the first instance of the string is stored in the index.</span></span> <span data-ttu-id="b13bf-283">Все текстовые функции, выполняемые для сохраненных строк, будут получать указанную порцию проиндексированной формы.</span><span class="sxs-lookup"><span data-stu-id="b13bf-283">All text functions that operate on stored strings will retrieve the specified portion of the indexed form.</span></span> <span data-ttu-id="b13bf-284">Потому при использовании формулы-примера будет возвращено одно значение для всего столбца с использованием первого экземпляра в качестве входа.</span><span class="sxs-lookup"><span data-stu-id="b13bf-284">Therefore, the example formula would return the same value for the entire column, using the first instance as the input.</span></span>  
  
[<span data-ttu-id="b13bf-285">Хранение строк и параметры сортировки в табличных моделях</span><span class="sxs-lookup"><span data-stu-id="b13bf-285">String Storage and Collation in Tabular Models</span></span>](https://msdn.microsoft.com/8516f0ad-32ee-4688-a304-e705143642ca)  
  
<span data-ttu-id="b13bf-286">Это также относится к другим текстовым функции, в том числе к функциям RIGHT, MID и т. п.</span><span class="sxs-lookup"><span data-stu-id="b13bf-286">This behavior also applies to other text functions, including RIGHT, MID, and so forth.</span></span>  
  
<span data-ttu-id="b13bf-287">**Длина строки влияет на результаты**</span><span class="sxs-lookup"><span data-stu-id="b13bf-287">**String length affects results**</span></span>  
<span data-ttu-id="b13bf-288">ПРИМЕР: `SEARCH("within string", "sample target  text", 1, 1)`</span><span class="sxs-lookup"><span data-stu-id="b13bf-288">EXAMPLE: `SEARCH("within string", "sample target  text", 1, 1)`</span></span>  
  
<span data-ttu-id="b13bf-289">При поиске строки с использованием функции SEARCH (поиск), при котором искомая строка длиннее внутренней строки, в режиме DirectQuery возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="b13bf-289">If you search for a string using the SEARCH function, and the target string is longer than the within string, DirectQuery mode raises an error.</span></span>  
  
<span data-ttu-id="b13bf-290">Для модели в памяти возвращается искомая строка, однако ее длина усекается до длины строки &lt;внутри текста&gt;.</span><span class="sxs-lookup"><span data-stu-id="b13bf-290">In an in-memory model, the searched string is returned, but with its length truncated to the length of &lt;within text&gt;.</span></span>  
  
<span data-ttu-id="b13bf-291">ПРИМЕР: `EVALUATE ROW("X", REPLACE("CA", 3, 2, "California") )`</span><span class="sxs-lookup"><span data-stu-id="b13bf-291">EXAMPLE: `EVALUATE ROW("X", REPLACE("CA", 3, 2, "California") )`</span></span>  
  
<span data-ttu-id="b13bf-292">Если длина строки-заменителя превышает длину первоначальной строки в режиме DirectQuery, формула возвратит значение NULL.</span><span class="sxs-lookup"><span data-stu-id="b13bf-292">If the length of the replacement string is greater than the length of the original string, in DirectQuery mode, the formula returns null.</span></span>  
  
<span data-ttu-id="b13bf-293">В моделях в памяти формула повторяет режим работы в Excel, в котором исходная строка объединяется со строкой для замены, причем возвращается значение CACalifornia.</span><span class="sxs-lookup"><span data-stu-id="b13bf-293">In in-memory models, the formula follows the behavior of Excel, which concatenates the source string and the replacement string, which returns CACalifornia.</span></span>  
  
<span data-ttu-id="b13bf-294">**Неявное выполнение функции TRIM в середине строк**</span><span class="sxs-lookup"><span data-stu-id="b13bf-294">**Implicit TRIM in the middle of strings**</span></span>  
<span data-ttu-id="b13bf-295">ПРИМЕР: `TRIM(" A sample sentence with leading white space")`</span><span class="sxs-lookup"><span data-stu-id="b13bf-295">EXAMPLE: `TRIM(" A sample sentence with leading white space")`</span></span>  
  
<span data-ttu-id="b13bf-296">В режиме DirectQuery функция DAX TRIM переводится в инструкцию SQL `LTRIM(RTRIM(<column>))`.</span><span class="sxs-lookup"><span data-stu-id="b13bf-296">DirectQuery mode translates the DAX TRIM function to the SQL statement `LTRIM(RTRIM(<column>))`.</span></span> <span data-ttu-id="b13bf-297">В результате удаляется только ведущий и замыкающий пробелы.</span><span class="sxs-lookup"><span data-stu-id="b13bf-297">As a result, only leading and trailing white space is removed.</span></span>  
  
<span data-ttu-id="b13bf-298">Однако та же формула в модели в памяти удалит пробелы внутри строки, подобно поведению Excel.</span><span class="sxs-lookup"><span data-stu-id="b13bf-298">In contrast, the same formula in an in-memory model removes spaces within the string, following the behavior of Excel.</span></span>  
  
<span data-ttu-id="b13bf-299">**Неявное выполнение функции RTRIM с использованием функции LEN**</span><span class="sxs-lookup"><span data-stu-id="b13bf-299">**Implicit RTRIM with use of LEN function**</span></span>  
<span data-ttu-id="b13bf-300">ПРИМЕР: `LEN('string_column')`</span><span class="sxs-lookup"><span data-stu-id="b13bf-300">EXAMPLE: `LEN('string_column')`</span></span>  
  
<span data-ttu-id="b13bf-301">Как и в SQL Server, в режиме DirectQuery автоматически удаляются пробелы в конце строковых столбцов, то есть выполняется неявная функция RTRIM.</span><span class="sxs-lookup"><span data-stu-id="b13bf-301">Like SQL Server, DirectQuery mode automatically removes white space from the end of string columns: that is, it performs an implicit RTRIM.</span></span> <span data-ttu-id="b13bf-302">Поэтому формулы, использующие функцию LEN, могут возвращать различные значения при наличии конечных пробелов в строке.</span><span class="sxs-lookup"><span data-stu-id="b13bf-302">Therefore, formulas that use the LEN function can return different values if the string has trailing spaces.</span></span>  
  
<span data-ttu-id="b13bf-303">**Подсистема в памяти поддерживает дополнительные параметры функции SUBSTITUTE**</span><span class="sxs-lookup"><span data-stu-id="b13bf-303">**In-memory supports additional parameters for SUBSTITUTE**</span></span>  
<span data-ttu-id="b13bf-304">ПРИМЕР: `SUBSTITUTE([Title],"Doctor","Dr.")`</span><span class="sxs-lookup"><span data-stu-id="b13bf-304">EXAMPLE: `SUBSTITUTE([Title],"Doctor","Dr.")`</span></span>  
  
<span data-ttu-id="b13bf-305">ПРИМЕР: `SUBSTITUTE([Title],"Doctor","Dr.", 2)`</span><span class="sxs-lookup"><span data-stu-id="b13bf-305">EXAMPLE: `SUBSTITUTE([Title],"Doctor","Dr.", 2)`</span></span>  
  
<span data-ttu-id="b13bf-306">В режиме DirectQuery можно использовать только версию этой функции, которая содержит три (3) параметра: ссылку на столбец, старый текст и новый текст.</span><span class="sxs-lookup"><span data-stu-id="b13bf-306">In DirectQuery mode, you can use only the version of this function that has three (3) parameters: a reference to a column, the old text, and the new text.</span></span> <span data-ttu-id="b13bf-307">Если использовать вторую формулу, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="b13bf-307">If you use the second formula, an error is raised.</span></span>  
  
<span data-ttu-id="b13bf-308">При использовании моделей в памяти можно использовать дополнительный четвертый параметр для указания номера экземпляра для строки, которую необходимо заменить.</span><span class="sxs-lookup"><span data-stu-id="b13bf-308">In in-memory models, you can use an optional fourth parameter to specify the instance number of the string to replace.</span></span> <span data-ttu-id="b13bf-309">Например, можно заменить только второй экземпляр и т. п.</span><span class="sxs-lookup"><span data-stu-id="b13bf-309">For example, you can replace only the second instance, etc.</span></span>  
  
<span data-ttu-id="b13bf-310">**Ограничения длины строки для операций REPT**</span><span class="sxs-lookup"><span data-stu-id="b13bf-310">**Restrictions on string lengths for REPT operations**</span></span>  
<span data-ttu-id="b13bf-311">В моделях в памяти длина строки, получаемой при выполнении операции, использующей функцию REPT, не должна превышать 32 767 символов.</span><span class="sxs-lookup"><span data-stu-id="b13bf-311">In in-memory models, the length of a string resulting from an operation using REPT must be less than 32,767 characters.</span></span>  
  
<span data-ttu-id="b13bf-312">Это ограничение не применяется в режиме DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="b13bf-312">This limitation does not apply in DirectQuery mode.</span></span>  
  
<span data-ttu-id="b13bf-313">**Операции с подстроками возвращают различные результаты в зависимости от типа символов**</span><span class="sxs-lookup"><span data-stu-id="b13bf-313">**Substring operations return different results depending on character type**</span></span>  
<span data-ttu-id="b13bf-314">ПРИМЕР: `MID([col], 2, 5)`</span><span class="sxs-lookup"><span data-stu-id="b13bf-314">EXAMPLE: `MID([col], 2, 5)`</span></span>  
  
<span data-ttu-id="b13bf-315">Если вводимый текст принадлежит к типам **varchar** или **nvarchar**, результат формулы всегда один и тот же.</span><span class="sxs-lookup"><span data-stu-id="b13bf-315">If the input text is **varchar** or **nvarchar**, the result of the formula is always the same.</span></span>  
  
<span data-ttu-id="b13bf-316">Однако если текст является символом фиксированной длины, а значение \* &lt; num_chars &gt; \* больше длины целевой строки, в режиме DirectQuery добавляется пустая строка в конец результирующей строки.</span><span class="sxs-lookup"><span data-stu-id="b13bf-316">However, if the text is a fixed-length character and the value for *&lt;num_chars&gt;* is greater than the length of the target string, in DirectQuery mode, a blank is added at the end of the result string.</span></span>  
  
<span data-ttu-id="b13bf-317">В модели в памяти результат завершается на последнем строковом символе без заполнения.</span><span class="sxs-lookup"><span data-stu-id="b13bf-317">In an in-memory model, the result terminates at the last string character, with no padding.</span></span>  
  
## <a name="functions-supported-in-directquery-mode"></a><a name="bkmk_SupportedFunc"></a><span data-ttu-id="b13bf-318">Функции, поддерживаемые в режиме DirectQuery</span><span class="sxs-lookup"><span data-stu-id="b13bf-318">Functions supported in DirectQuery mode</span></span>  
<span data-ttu-id="b13bf-319">С учетом условий, описанных в предыдущем разделе, следующие функции DAX можно использовать в режиме DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="b13bf-319">The following DAX functions can be used in DirectQuery mode, but with the qualifications as described in the preceding section.</span></span>  
  
<span data-ttu-id="b13bf-320">**Текстовые функции**</span><span class="sxs-lookup"><span data-stu-id="b13bf-320">**Text functions**</span></span>  
  
<span data-ttu-id="b13bf-321">CONCATENATE</span><span class="sxs-lookup"><span data-stu-id="b13bf-321">CONCATENATE</span></span>  
  
<span data-ttu-id="b13bf-322">FIND</span><span class="sxs-lookup"><span data-stu-id="b13bf-322">FIND</span></span>  
  
<span data-ttu-id="b13bf-323">LEFT</span><span class="sxs-lookup"><span data-stu-id="b13bf-323">LEFT</span></span>  
  
<span data-ttu-id="b13bf-324">LEN</span><span class="sxs-lookup"><span data-stu-id="b13bf-324">LEN</span></span>  
  
<span data-ttu-id="b13bf-325">MID</span><span class="sxs-lookup"><span data-stu-id="b13bf-325">MID</span></span>  
  
<span data-ttu-id="b13bf-326">REPLACE</span><span class="sxs-lookup"><span data-stu-id="b13bf-326">REPLACE</span></span>  
  
<span data-ttu-id="b13bf-327">REPT</span><span class="sxs-lookup"><span data-stu-id="b13bf-327">REPT</span></span>  
  
<span data-ttu-id="b13bf-328">RIGHT</span><span class="sxs-lookup"><span data-stu-id="b13bf-328">RIGHT</span></span>  
  
<span data-ttu-id="b13bf-329">SUBSTITUTE</span><span class="sxs-lookup"><span data-stu-id="b13bf-329">SUBSTITUTE</span></span>  
  
<span data-ttu-id="b13bf-330">TRIM</span><span class="sxs-lookup"><span data-stu-id="b13bf-330">TRIM</span></span>  
  
<span data-ttu-id="b13bf-331">**Статистические функции**</span><span class="sxs-lookup"><span data-stu-id="b13bf-331">**Statistical functions**</span></span>  
  
<span data-ttu-id="b13bf-332">COUNT</span><span class="sxs-lookup"><span data-stu-id="b13bf-332">COUNT</span></span>  
  
<span data-ttu-id="b13bf-333">STDEV.P</span><span class="sxs-lookup"><span data-stu-id="b13bf-333">STDEV.P</span></span>  
  
<span data-ttu-id="b13bf-334">STDEV.S</span><span class="sxs-lookup"><span data-stu-id="b13bf-334">STDEV.S</span></span>  
  
<span data-ttu-id="b13bf-335">STDEVX.P</span><span class="sxs-lookup"><span data-stu-id="b13bf-335">STDEVX.P</span></span>  
  
<span data-ttu-id="b13bf-336">STDEVX.S</span><span class="sxs-lookup"><span data-stu-id="b13bf-336">STDEVX.S</span></span>  
  
<span data-ttu-id="b13bf-337">VAR.P</span><span class="sxs-lookup"><span data-stu-id="b13bf-337">VAR.P</span></span>  
  
<span data-ttu-id="b13bf-338">VAR.S</span><span class="sxs-lookup"><span data-stu-id="b13bf-338">VAR.S</span></span>  
  
<span data-ttu-id="b13bf-339">VARX.P</span><span class="sxs-lookup"><span data-stu-id="b13bf-339">VARX.P</span></span>  
  
<span data-ttu-id="b13bf-340">VARX.S</span><span class="sxs-lookup"><span data-stu-id="b13bf-340">VARX.S</span></span>  
  
<span data-ttu-id="b13bf-341">**Функции даты и времени**</span><span class="sxs-lookup"><span data-stu-id="b13bf-341">**Date/time functions**</span></span>  
  
<span data-ttu-id="b13bf-342">DATE</span><span class="sxs-lookup"><span data-stu-id="b13bf-342">DATE</span></span>  
  
<span data-ttu-id="b13bf-343">EDATE</span><span class="sxs-lookup"><span data-stu-id="b13bf-343">EDATE</span></span>  
  
<span data-ttu-id="b13bf-344">EOMONTH</span><span class="sxs-lookup"><span data-stu-id="b13bf-344">EOMONTH</span></span>  
  
<span data-ttu-id="b13bf-345">DATE</span><span class="sxs-lookup"><span data-stu-id="b13bf-345">DATE</span></span>  
  
<span data-ttu-id="b13bf-346">TIME</span><span class="sxs-lookup"><span data-stu-id="b13bf-346">TIME</span></span>  
  
<span data-ttu-id="b13bf-347">SECOND</span><span class="sxs-lookup"><span data-stu-id="b13bf-347">SECOND</span></span>  
  
<span data-ttu-id="b13bf-348">**Математические и численные функции**</span><span class="sxs-lookup"><span data-stu-id="b13bf-348">**Math and number functions**</span></span>  
  
<span data-ttu-id="b13bf-349">CEILING</span><span class="sxs-lookup"><span data-stu-id="b13bf-349">CEILING</span></span>  
  
<span data-ttu-id="b13bf-350">LN</span><span class="sxs-lookup"><span data-stu-id="b13bf-350">LN</span></span>  
  
<span data-ttu-id="b13bf-351">LOG</span><span class="sxs-lookup"><span data-stu-id="b13bf-351">LOG</span></span>  
  
<span data-ttu-id="b13bf-352">LOG10</span><span class="sxs-lookup"><span data-stu-id="b13bf-352">LOG10</span></span>  
  
<span data-ttu-id="b13bf-353">POWER</span><span class="sxs-lookup"><span data-stu-id="b13bf-353">POWER</span></span>  
  
<span data-ttu-id="b13bf-354">**Запросы к таблицам DAX**</span><span class="sxs-lookup"><span data-stu-id="b13bf-354">**DAX Table queries**</span></span>  
  
<span data-ttu-id="b13bf-355">При оценке формул для модели DirectQuery при помощи запросов к таблицам в DAX существуют некоторые ограничения.</span><span class="sxs-lookup"><span data-stu-id="b13bf-355">There are some limitations when you evaluate formulas against a DirectQuery model by using DAX Table queries.</span></span> <span data-ttu-id="b13bf-356">DirectQuery не поддерживает ссылок на тот же столбец дважды в предложении ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="b13bf-356">DirectQuery does not support referring to the same column twice in an ORDER BY clause.</span></span> <span data-ttu-id="b13bf-357">В этой ситуации не удастся создать эквивалентную инструкцию Transact-SQL, поэтому запрос завершится неудачей.</span><span class="sxs-lookup"><span data-stu-id="b13bf-357">The equivalent Transact-SQL statement cannot be created and the query fails.</span></span>  
  
<span data-ttu-id="b13bf-358">Для модели в памяти повтор предложения ORDER BY на результаты не повлияет.</span><span class="sxs-lookup"><span data-stu-id="b13bf-358">In an in-memory model, repeating the ORDER by clause has no effect on the results.</span></span>  
  
## <a name="functions-not-supported-in-directquery-mode"></a><a name="bkmk_NotSupportedFunc"></a><span data-ttu-id="b13bf-359">Функции, не поддерживаемые в режиме DirectQuery</span><span class="sxs-lookup"><span data-stu-id="b13bf-359">Functions not supported in DirectQuery Mode</span></span>  
<span data-ttu-id="b13bf-360">Некоторые функции DAX не поддерживаются в моделях, развернутых в режиме DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="b13bf-360">Some DAX functions are not supported in models that are deployed in DirectQuery mode.</span></span> <span data-ttu-id="b13bf-361">Среди причин отсутствия поддержки той или иной функции могут быть следующие, как в отдельности, так и в сочетании:</span><span class="sxs-lookup"><span data-stu-id="b13bf-361">The reasons that a particular function is not supported can include any or a combination of these reasons:</span></span>  
  
-   <span data-ttu-id="b13bf-362">Базовый реляционный механизм не может выполнять вычисления, эквивалентные функциям подсистемы xVelocity.</span><span class="sxs-lookup"><span data-stu-id="b13bf-362">The underlying relational engine cannot perform calculations equivalent to those performed by the xVelocity engine.</span></span>  
  
-   <span data-ttu-id="b13bf-363">Формула не может быть преобразована в эквивалент выражения SQL.</span><span class="sxs-lookup"><span data-stu-id="b13bf-363">The formula cannot be converted to en equivalent SQL expression.</span></span>  
  
-   <span data-ttu-id="b13bf-364">Производительность преобразованного выражения и итог вычислений будут неприемлемыми.</span><span class="sxs-lookup"><span data-stu-id="b13bf-364">The performance of the converted expression and the resulting calculations would be unacceptable.</span></span>  
  
<span data-ttu-id="b13bf-365">Следующие функции DAX не могут использоваться в моделях DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="b13bf-365">The following DAX functions cannot be used in DirectQuery models.</span></span>  
  
<span data-ttu-id="b13bf-366">**Функции пути**</span><span class="sxs-lookup"><span data-stu-id="b13bf-366">**Path functions**</span></span>  
  
<span data-ttu-id="b13bf-367">PATH</span><span class="sxs-lookup"><span data-stu-id="b13bf-367">PATH</span></span>  
  
<span data-ttu-id="b13bf-368">PATHCONTAINS</span><span class="sxs-lookup"><span data-stu-id="b13bf-368">PATHCONTAINS</span></span>  
  
<span data-ttu-id="b13bf-369">PATHITEM</span><span class="sxs-lookup"><span data-stu-id="b13bf-369">PATHITEM</span></span>  
  
<span data-ttu-id="b13bf-370">PATHITEMREVERSE</span><span class="sxs-lookup"><span data-stu-id="b13bf-370">PATHITEMREVERSE</span></span>  
  
<span data-ttu-id="b13bf-371">PATHLENGTH</span><span class="sxs-lookup"><span data-stu-id="b13bf-371">PATHLENGTH</span></span>  
  
<span data-ttu-id="b13bf-372">**Прочие функции**</span><span class="sxs-lookup"><span data-stu-id="b13bf-372">**Misc functions**</span></span>  
  
<span data-ttu-id="b13bf-373">COUNTBLANK</span><span class="sxs-lookup"><span data-stu-id="b13bf-373">COUNTBLANK</span></span>  
  
<span data-ttu-id="b13bf-374">FIXED</span><span class="sxs-lookup"><span data-stu-id="b13bf-374">FIXED</span></span>  
  
<span data-ttu-id="b13bf-375">FORMAT</span><span class="sxs-lookup"><span data-stu-id="b13bf-375">FORMAT</span></span>  
  
<span data-ttu-id="b13bf-376">RAND</span><span class="sxs-lookup"><span data-stu-id="b13bf-376">RAND</span></span>  
  
<span data-ttu-id="b13bf-377">RANDBETWEEN</span><span class="sxs-lookup"><span data-stu-id="b13bf-377">RANDBETWEEN</span></span>  
  
<span data-ttu-id="b13bf-378">**Функции логики операций со временем: даты начала и окончания**</span><span class="sxs-lookup"><span data-stu-id="b13bf-378">**Time intelligence functions: Start and end dates**</span></span>  
  
<span data-ttu-id="b13bf-379">DATESQTD</span><span class="sxs-lookup"><span data-stu-id="b13bf-379">DATESQTD</span></span>  
  
<span data-ttu-id="b13bf-380">DATESYTD</span><span class="sxs-lookup"><span data-stu-id="b13bf-380">DATESYTD</span></span>  
  
<span data-ttu-id="b13bf-381">DATESMTD</span><span class="sxs-lookup"><span data-stu-id="b13bf-381">DATESMTD</span></span>  
  
<span data-ttu-id="b13bf-382">DATESQTD</span><span class="sxs-lookup"><span data-stu-id="b13bf-382">DATESQTD</span></span>  
  
<span data-ttu-id="b13bf-383">DATESINPERIOD</span><span class="sxs-lookup"><span data-stu-id="b13bf-383">DATESINPERIOD</span></span>  
  
<span data-ttu-id="b13bf-384">TOTALMTD</span><span class="sxs-lookup"><span data-stu-id="b13bf-384">TOTALMTD</span></span>  
  
<span data-ttu-id="b13bf-385">TOTALQTD</span><span class="sxs-lookup"><span data-stu-id="b13bf-385">TOTALQTD</span></span>  
  
<span data-ttu-id="b13bf-386">TOTALYTD</span><span class="sxs-lookup"><span data-stu-id="b13bf-386">TOTALYTD</span></span>  
  
<span data-ttu-id="b13bf-387">DATESINPERIOD</span><span class="sxs-lookup"><span data-stu-id="b13bf-387">DATESINPERIOD</span></span>  
  
<span data-ttu-id="b13bf-388">SAMEPERIODLASTYEAR</span><span class="sxs-lookup"><span data-stu-id="b13bf-388">SAMEPERIODLASTYEAR</span></span>  
  
<span data-ttu-id="b13bf-389">PARALLELPERIOD</span><span class="sxs-lookup"><span data-stu-id="b13bf-389">PARALLELPERIOD</span></span>  
  
<span data-ttu-id="b13bf-390">**Функции логики операций со временем: балансы**</span><span class="sxs-lookup"><span data-stu-id="b13bf-390">**Time-intelligence functions: Balances**</span></span>  
  
<span data-ttu-id="b13bf-391">OPENINGBALANCEMONTH</span><span class="sxs-lookup"><span data-stu-id="b13bf-391">OPENINGBALANCEMONTH</span></span>  
  
<span data-ttu-id="b13bf-392">OPENINGBALANCEQUARTER</span><span class="sxs-lookup"><span data-stu-id="b13bf-392">OPENINGBALANCEQUARTER</span></span>  
  
<span data-ttu-id="b13bf-393">OPENINGBALANCEYEAR</span><span class="sxs-lookup"><span data-stu-id="b13bf-393">OPENINGBALANCEYEAR</span></span>  
  
<span data-ttu-id="b13bf-394">CLOSINGBALANCEMONTH</span><span class="sxs-lookup"><span data-stu-id="b13bf-394">CLOSINGBALANCEMONTH</span></span>  
  
<span data-ttu-id="b13bf-395">CLOSINGBALANCEQUARTER</span><span class="sxs-lookup"><span data-stu-id="b13bf-395">CLOSINGBALANCEQUARTER</span></span>  
  
<span data-ttu-id="b13bf-396">CLOSINGBALANCEYEAR</span><span class="sxs-lookup"><span data-stu-id="b13bf-396">CLOSINGBALANCEYEAR</span></span>  
  
<span data-ttu-id="b13bf-397">**Функции логики операций со временем: предыдущий и следующий периоды**</span><span class="sxs-lookup"><span data-stu-id="b13bf-397">**Time intelligence functions: Previous and next periods**</span></span>  
  
<span data-ttu-id="b13bf-398">PREVIOUSDAY</span><span class="sxs-lookup"><span data-stu-id="b13bf-398">PREVIOUSDAY</span></span>  
  
<span data-ttu-id="b13bf-399">PREVIOUSMONTH</span><span class="sxs-lookup"><span data-stu-id="b13bf-399">PREVIOUSMONTH</span></span>  
  
<span data-ttu-id="b13bf-400">PREVIOUSQUARTER</span><span class="sxs-lookup"><span data-stu-id="b13bf-400">PREVIOUSQUARTER</span></span>  
  
<span data-ttu-id="b13bf-401">PREVIOUSYEAR</span><span class="sxs-lookup"><span data-stu-id="b13bf-401">PREVIOUSYEAR</span></span>  
  
<span data-ttu-id="b13bf-402">NEXTDAY</span><span class="sxs-lookup"><span data-stu-id="b13bf-402">NEXTDAY</span></span>  
  
<span data-ttu-id="b13bf-403">NEXTMONTH</span><span class="sxs-lookup"><span data-stu-id="b13bf-403">NEXTMONTH</span></span>  
  
<span data-ttu-id="b13bf-404">NEXTQUARTER</span><span class="sxs-lookup"><span data-stu-id="b13bf-404">NEXTQUARTER</span></span>  
  
<span data-ttu-id="b13bf-405">NEXTYEAR</span><span class="sxs-lookup"><span data-stu-id="b13bf-405">NEXTYEAR</span></span>  
  
<span data-ttu-id="b13bf-406">**Функции логики операций со временем: периоды и вычисления для периодов**</span><span class="sxs-lookup"><span data-stu-id="b13bf-406">**Time intelligence functions: Periods and calculations over periods**</span></span>  
  
<span data-ttu-id="b13bf-407">STARTOFMONTH</span><span class="sxs-lookup"><span data-stu-id="b13bf-407">STARTOFMONTH</span></span>  
  
<span data-ttu-id="b13bf-408">STARTOFQUARTER</span><span class="sxs-lookup"><span data-stu-id="b13bf-408">STARTOFQUARTER</span></span>  
  
<span data-ttu-id="b13bf-409">STARTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="b13bf-409">STARTOFYEAR</span></span>  
  
<span data-ttu-id="b13bf-410">ENDOFMONTH</span><span class="sxs-lookup"><span data-stu-id="b13bf-410">ENDOFMONTH</span></span>  
  
<span data-ttu-id="b13bf-411">ENDOFQUARTER</span><span class="sxs-lookup"><span data-stu-id="b13bf-411">ENDOFQUARTER</span></span>  
  
<span data-ttu-id="b13bf-412">ENDOFYEAR</span><span class="sxs-lookup"><span data-stu-id="b13bf-412">ENDOFYEAR</span></span>  
  
<span data-ttu-id="b13bf-413">FIRSTDATE</span><span class="sxs-lookup"><span data-stu-id="b13bf-413">FIRSTDATE</span></span>  
  
<span data-ttu-id="b13bf-414">LASTDATE</span><span class="sxs-lookup"><span data-stu-id="b13bf-414">LASTDATE</span></span>  
  
<span data-ttu-id="b13bf-415">DATEADD</span><span class="sxs-lookup"><span data-stu-id="b13bf-415">DATEADD</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b13bf-416">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b13bf-416">See also</span></span>  
[<span data-ttu-id="b13bf-417">Режим DirectQuery (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="b13bf-417">DirectQuery Mode (SSAS Tabular)</span></span>](https://msdn.microsoft.com/45ad2965-05ec-4fb1-a164-d8060b562ea5)  
  

