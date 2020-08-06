---
title: Ограничение количества результатов поиска с помощью RANK | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- row ranking [full-text search]
- relevance ranking values [full-text search]
- full-text search [SQL Server], rankings
- index rankings [full-text search]
- ranked results [full-text search]
- rankings [full-text search]
- per-row rank values [full-text search]
ms.assetid: 06a776e6-296c-4ec7-9fa5-0794709ccb17
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ab1b930b3238cb541965e1984d1561f1a1c22d87
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733777"
---
# <a name="limit-search-results-with-rank"></a><span data-ttu-id="9558b-102">Ограничение количества результатов поиска с использованием функции RANK</span><span class="sxs-lookup"><span data-stu-id="9558b-102">Limit Search Results with RANK</span></span>
  <span data-ttu-id="9558b-103">Функции [CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) и [FREETEXTTABLE](/sql/relational-databases/system-functions/freetexttable-transact-sql) возвращают столбец с именем RANK, содержащий порядковые номера от 0 до 1000 (ранжирующие значения).</span><span class="sxs-lookup"><span data-stu-id="9558b-103">The [CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) and [FREETEXTTABLE](/sql/relational-databases/system-functions/freetexttable-transact-sql) functions return a column named RANK that contains ordinal values from 0 through 1000 (rank values).</span></span> <span data-ttu-id="9558b-104">Эти значения используются для ранжирования возвращенных строк согласно их соответствию критерию выбора.</span><span class="sxs-lookup"><span data-stu-id="9558b-104">These values are used to rank the rows returned according to how well they match the selection criteria.</span></span> <span data-ttu-id="9558b-105">Ранжирующие значения указывают только относительный порядок релевантности строк в результирующем наборе, при этом чем меньше значение, тем меньше релевантность.</span><span class="sxs-lookup"><span data-stu-id="9558b-105">The rank values indicate only a relative order of relevance of the rows in the result set, with a lower value indicating lower relevance.</span></span> <span data-ttu-id="9558b-106">Фактические значения несущественны и, как правило, различны для каждого выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="9558b-106">The actual values are unimportant and typically differ each time the query is run.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9558b-107">Запросы, использующие предикаты CONTAINS и FREETEXT, не возвращают ранжирующие значения.</span><span class="sxs-lookup"><span data-stu-id="9558b-107">The CONTAINS and FREETEXT predicates do not return any rank values.</span></span>  
  
 <span data-ttu-id="9558b-108">Число элементов, совпадающих с условиями поиска, часто бывает очень велико.</span><span class="sxs-lookup"><span data-stu-id="9558b-108">The number of items matching a search condition is often very large.</span></span> <span data-ttu-id="9558b-109">Чтобы запросы CONTAINSTABLE или FREETEXTTABLE не возвращали слишком много соответствий, следует использовать необязательный параметр *top_n_by_rank* , в результате чего будет возвращаться только подмножество строк.</span><span class="sxs-lookup"><span data-stu-id="9558b-109">To prevent CONTAINSTABLE or FREETEXTTABLE queries from returning too many matches, use the optional *top_n_by_rank* parameter, which returns only a subset of rows.</span></span> <span data-ttu-id="9558b-110">*top_n_by_rank* — это целочисленное значение *n*, указывающее, что следует возвратить только *n* совпадений с самым высоким рангом в нисходящем порядке.</span><span class="sxs-lookup"><span data-stu-id="9558b-110">*top_n_by_rank* is an integer value, *n*, that specifies that only the *n* highest ranked matches are to be returned, in descending order.</span></span> <span data-ttu-id="9558b-111">Если параметр *top_n_by_rank* скомбинирован с другими параметрами, то запрос может вернуть меньше строк, чем фактически соответствует всем предикатам.</span><span class="sxs-lookup"><span data-stu-id="9558b-111">If *top_n_by_rank* is combined with other parameters, the query could return fewer rows than the number of rows that actually match all the predicates.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="9558b-112">упорядочивает соответствия по рангу и возвращает заданное число строк.</span><span class="sxs-lookup"><span data-stu-id="9558b-112">orders the matches by rank and returns only up to the specified number of rows.</span></span> <span data-ttu-id="9558b-113">Это может привести к значительному повышению производительности.</span><span class="sxs-lookup"><span data-stu-id="9558b-113">This choice can result in a dramatic increase in performance.</span></span> <span data-ttu-id="9558b-114">Например, запрос, обычно возвращающий 100 000 строк из таблицы с миллионом строк, обрабатывается гораздо быстрее, если запросить всего 100 строк с наивысшими ранжирующими значениями.</span><span class="sxs-lookup"><span data-stu-id="9558b-114">For example, a query that would normally return 100,000 rows from a table of one million rows are processed more quickly if only the top 100 rows are requested.</span></span>  
  
##  <a name="examples-of-using-rank-to-limit-search-results"></a><a name="examples"></a> <span data-ttu-id="9558b-115">Примеры использования параметра RANK для ограничения результатов поиска</span><span class="sxs-lookup"><span data-stu-id="9558b-115">Examples of Using RANK to Limit Search Results</span></span>  
  
### <a name="example-a-searching-for-only-the-top-three-matches"></a><span data-ttu-id="9558b-116">Пример А. Поиск только трех соответствий с максимальным рангом</span><span class="sxs-lookup"><span data-stu-id="9558b-116">Example A: Searching for only the top three matches</span></span>  
 <span data-ttu-id="9558b-117">В следующем примере инструкция CONTAINSTABLE используется для возвращения только трех строк с максимальным рангом.</span><span class="sxs-lookup"><span data-stu-id="9558b-117">The following example uses CONTAINSTABLE to return only the top three matches.</span></span>  
  
```  
USE AdventureWorks2012  
GO  
  
SELECT K.RANK, AddressLine1, City  
FROM Person.Address AS A  
  INNER JOIN  
  CONTAINSTABLE(Person.Address, AddressLine1, 'ISABOUT ("des*",  
    Rue WEIGHT(0.5),  
    Bouchers WEIGHT(0.9))',  
    3) AS K  
  ON A.AddressID = K.[KEY]  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
RANK        Address                          City  
----------- -------------------------------- ------------------------------  
172         9005, rue des Bouchers           Paris  
172         5, rue des Bouchers              Orleans  
172         5, rue des Bouchers              Metz  
  
(3 row(s) affected)  
```  
  
  
### <a name="example-b-searching-for-the-top-ten-matches"></a><span data-ttu-id="9558b-118">Пример Б. Поиск десяти соответствий с максимальным рангом</span><span class="sxs-lookup"><span data-stu-id="9558b-118">Example B: Searching for the top ten matches</span></span>  
 <span data-ttu-id="9558b-119">В следующем примере с помощью CONTAINSTABLE возвращается описание первых 5 товаров, где столбец `Description` содержит слово «aluminum» рядом со словом «light» или «lightweight».</span><span class="sxs-lookup"><span data-stu-id="9558b-119">The following example uses CONTAINSTABLE to return the description of the top 5 products where the `Description` column contains the word "aluminum" near either the word "light" or the word "lightweight".</span></span>  
  
```  
USE AdventureWorks2012  
GO  
  
SELECT FT_TBL.ProductDescriptionID,  
   FT_TBL.Description,   
   KEY_TBL.RANK  
FROM Production.ProductDescription AS FT_TBL INNER JOIN  
   CONTAINSTABLE (Production.ProductDescription,  
      Description,   
      '(light NEAR aluminum) OR  
      (lightweight NEAR aluminum)',  
      5  
   ) AS KEY_TBL  
   ON FT_TBL.ProductDescriptionID = KEY_TBL.[KEY]  
GO  
```  
  
  
##  <a name="how-search-query-results-are-ranked"></a><a name="how"></a> <span data-ttu-id="9558b-120">Как ранжируются результаты поискового запроса</span><span class="sxs-lookup"><span data-stu-id="9558b-120">How Search Query Results Are Ranked</span></span>  
 <span data-ttu-id="9558b-121">Полнотекстовый поиск в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] может формировать дополнительную оценку (или значение ранга), которая обозначает релевантность данных, возвращенных полнотекстовым запросом.</span><span class="sxs-lookup"><span data-stu-id="9558b-121">Full-text search in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] can generate an optional score (or rank value) that indicates the relevance of the data returned by a full-text query.</span></span> <span data-ttu-id="9558b-122">Это ранжирующее значение вычисляется для каждой строки и может использоваться как критерий упорядочения для сортировки результирующего набора данного запроса по релевантности.</span><span class="sxs-lookup"><span data-stu-id="9558b-122">This rank value is calculated on every row and can be used as an ordering criteria to sort the result set of a given query by relevance.</span></span> <span data-ttu-id="9558b-123">Ранжирующие значения показывают только относительный порядок релевантности строк в результирующем наборе.</span><span class="sxs-lookup"><span data-stu-id="9558b-123">The rank values indicate only a relative order of relevance of the rows in the result set.</span></span> <span data-ttu-id="9558b-124">Фактические значения несущественны и, как правило, различны для каждого выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="9558b-124">The actual values are unimportant and typically differ each time the query is run.</span></span> <span data-ttu-id="9558b-125">Сохранение ранжирующего значения между запросами не играет роли.</span><span class="sxs-lookup"><span data-stu-id="9558b-125">The rank value does not hold any significance across queries.</span></span>  
  
### <a name="statistics-for-ranking"></a><span data-ttu-id="9558b-126">Статистические данные для ранжирования</span><span class="sxs-lookup"><span data-stu-id="9558b-126">Statistics for Ranking</span></span>  
 <span data-ttu-id="9558b-127">При построении индекса собираются статистические данные, которые будут использоваться в ранжировании.</span><span class="sxs-lookup"><span data-stu-id="9558b-127">When an index is built, statistics are collected for use in ranking.</span></span> <span data-ttu-id="9558b-128">Процесс построения полнотекстового каталога не приводит напрямую к созданию одной индексной структуры.</span><span class="sxs-lookup"><span data-stu-id="9558b-128">The process of building a full-text catalog does not directly result in a single index structure.</span></span> <span data-ttu-id="9558b-129">Средство полнотекстового поиска для [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] при индексировании данных создает промежуточные индексы.</span><span class="sxs-lookup"><span data-stu-id="9558b-129">Instead, the Full-Text Engine for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] creates intermediate indexes as data is indexed.</span></span> <span data-ttu-id="9558b-130">Затем средство полнотекстового поиска выполняет слияние этих индексов в больший индекс по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="9558b-130">The Full-Text Engine then merges these indexes into a larger index as needed.</span></span> <span data-ttu-id="9558b-131">Этот процесс может повторяться много раз.</span><span class="sxs-lookup"><span data-stu-id="9558b-131">This process can be repeated many times.</span></span> <span data-ttu-id="9558b-132">После этого средство полнотекстового поиска выполняет слияние в единый файл, объединяющее все промежуточные индексы в один большой главный индекс.</span><span class="sxs-lookup"><span data-stu-id="9558b-132">The Full-Text Engine then conducts a "master merge" that combines all of the intermediate indexes into one large master index.</span></span>  
  
 <span data-ttu-id="9558b-133">Статистические данные собираются на каждом уровне промежуточных индексов.</span><span class="sxs-lookup"><span data-stu-id="9558b-133">Statistics are collected at each intermediate index level.</span></span> <span data-ttu-id="9558b-134">Слияние этих данных производится при слиянии индексов.</span><span class="sxs-lookup"><span data-stu-id="9558b-134">The statistics are merged when the indexes are merged.</span></span> <span data-ttu-id="9558b-135">Некоторые статистические значения могут формироваться только в процессе создания главного индекса.</span><span class="sxs-lookup"><span data-stu-id="9558b-135">Some statistical values can only be generated during the master merging process.</span></span>  
  
 <span data-ttu-id="9558b-136">При ранжировании результирующего набора запроса [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] использует статистические данные из самого большого промежуточного индекса.</span><span class="sxs-lookup"><span data-stu-id="9558b-136">While ranking a query result set, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] uses statistics from the largest intermediate index.</span></span> <span data-ttu-id="9558b-137">Это зависит от того, было ли выполнено слияние промежуточных индексов.</span><span class="sxs-lookup"><span data-stu-id="9558b-137">This depends on whether intermediate indexes have been merged or not.</span></span> <span data-ttu-id="9558b-138">Если слияние промежуточных индексов не выполнялось, точность статистических данных ранжирования может быть различной.</span><span class="sxs-lookup"><span data-stu-id="9558b-138">As a result, ranking statistics can vary in accuracy if the intermediate indexes have not been merged.</span></span> <span data-ttu-id="9558b-139">По этой причине один и тот же запрос в разное время может возвращать различные результаты ранжирования по мере добавления, изменения и удаления данных, а также по мере слияния небольших индексов.</span><span class="sxs-lookup"><span data-stu-id="9558b-139">This explains why the same query can return different rank results over time as full-text indexed data is added, modified, and deleted, and as the smaller indexes are merged.</span></span>  
  
 <span data-ttu-id="9558b-140">Чтобы свести к минимуму размер индекса и сложность вычислений, статистические данные часто округляются.</span><span class="sxs-lookup"><span data-stu-id="9558b-140">To minimize the size of the index and computational complexity, statistics are often rounded.</span></span>  
  
 <span data-ttu-id="9558b-141">В следующем списке приводятся часто используемые термины и статистические значения, важные при вычислении ранга.</span><span class="sxs-lookup"><span data-stu-id="9558b-141">The list below includes some commonly used terms and statistical values that are important in calculating rank.</span></span>  
  
 <span data-ttu-id="9558b-142">Свойство</span><span class="sxs-lookup"><span data-stu-id="9558b-142">Property</span></span>  
 <span data-ttu-id="9558b-143">Полнотекстовый индексированный столбец строки.</span><span class="sxs-lookup"><span data-stu-id="9558b-143">A full-text indexed column of the row.</span></span>  
  
 <span data-ttu-id="9558b-144">Документ</span><span class="sxs-lookup"><span data-stu-id="9558b-144">Document</span></span>  
 <span data-ttu-id="9558b-145">Сущность, возвращаемая в запросах.</span><span class="sxs-lookup"><span data-stu-id="9558b-145">The entity that is returned in queries.</span></span> <span data-ttu-id="9558b-146">В [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ей соответствует строка.</span><span class="sxs-lookup"><span data-stu-id="9558b-146">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] this corresponds to a row.</span></span> <span data-ttu-id="9558b-147">Документ может иметь несколько свойств точно так же, как и строка может иметь несколько полнотекстовых индексированных столбцов.</span><span class="sxs-lookup"><span data-stu-id="9558b-147">A document can have multiple properties, just as a row can have multiple full-text indexed columns.</span></span>  
  
 <span data-ttu-id="9558b-148">Индекс</span><span class="sxs-lookup"><span data-stu-id="9558b-148">Index</span></span>  
 <span data-ttu-id="9558b-149">Один инвертированный индекс одного или нескольких документов.</span><span class="sxs-lookup"><span data-stu-id="9558b-149">A single inverted index of one or more documents.</span></span> <span data-ttu-id="9558b-150">Может полностью находиться в памяти или храниться на диске.</span><span class="sxs-lookup"><span data-stu-id="9558b-150">This may be entirely in memory or on disk.</span></span> <span data-ttu-id="9558b-151">Многие статистические данные относятся к конкретному индексу, в котором было обнаружено соответствие.</span><span class="sxs-lookup"><span data-stu-id="9558b-151">Many query statistics are relative to the individual index where the match occurred.</span></span>  
  
 <span data-ttu-id="9558b-152">Полнотекстовый каталог</span><span class="sxs-lookup"><span data-stu-id="9558b-152">Full-Text Catalog</span></span>  
 <span data-ttu-id="9558b-153">Коллекция промежуточных индексов, которые для запросов считаются одной сущностью.</span><span class="sxs-lookup"><span data-stu-id="9558b-153">A collection of intermediate indexes treated as one entity for queries.</span></span> <span data-ttu-id="9558b-154">Каталоги являются организационными единицами, видимыми администратору [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9558b-154">Catalogs are the unit of organization visible to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] administrator.</span></span>  
  
 <span data-ttu-id="9558b-155">Слово, токен или элемент</span><span class="sxs-lookup"><span data-stu-id="9558b-155">Word, token or item</span></span>  
 <span data-ttu-id="9558b-156">Единица проверки соответствия в средстве полнотекстового поиска.</span><span class="sxs-lookup"><span data-stu-id="9558b-156">The unit of matching in the full-text engine.</span></span> <span data-ttu-id="9558b-157">Потоки текста из документов формируются в слова или в токены согласно правилам конкретного языка.</span><span class="sxs-lookup"><span data-stu-id="9558b-157">Streams of text from documents are tokenized into words, or tokens by language-specific word breakers.</span></span>  
  
 <span data-ttu-id="9558b-158">Наличие</span><span class="sxs-lookup"><span data-stu-id="9558b-158">Occurrence</span></span>  
 <span data-ttu-id="9558b-159">Смещение слова в свойстве документа, определенное средством разбиения по словам.</span><span class="sxs-lookup"><span data-stu-id="9558b-159">The word offset in a document property as determined by the word breaker.</span></span> <span data-ttu-id="9558b-160">Первое слово имеет вхождение в позиции 1, следующее — в позиции 2 и т.д.</span><span class="sxs-lookup"><span data-stu-id="9558b-160">The first word is at occurrence 1, the next at 2, and so on.</span></span> <span data-ttu-id="9558b-161">Чтобы избежать ложных положительных результатов в запросах по сходству и запросах фраз, в конце предложения и абзаца используется увеличенный промежуток между вхождениями.</span><span class="sxs-lookup"><span data-stu-id="9558b-161">In order to avoid false positives in phrase and proximity queries, end-of-sentence and end-of-paragraph introduce larger occurrence gaps.</span></span>  
  
 <span data-ttu-id="9558b-162">TermFrequency</span><span class="sxs-lookup"><span data-stu-id="9558b-162">TermFrequency</span></span>  
 <span data-ttu-id="9558b-163">Количество вхождений значения ключа в строку.</span><span class="sxs-lookup"><span data-stu-id="9558b-163">The number times the key value occurs in a row.</span></span>  
  
 <span data-ttu-id="9558b-164">IndexedRowCount</span><span class="sxs-lookup"><span data-stu-id="9558b-164">IndexedRowCount</span></span>  
 <span data-ttu-id="9558b-165">Общее число индексированных строк.</span><span class="sxs-lookup"><span data-stu-id="9558b-165">Total number of rows indexed.</span></span> <span data-ttu-id="9558b-166">Вычисляется на основе счетчиков в промежуточных индексах.</span><span class="sxs-lookup"><span data-stu-id="9558b-166">This is computed, based on counts maintained in the intermediate indexes.</span></span> <span data-ttu-id="9558b-167">Точность этого числа может быть различной.</span><span class="sxs-lookup"><span data-stu-id="9558b-167">This number can vary in accuracy.</span></span>  
  
 <span data-ttu-id="9558b-168">KeyRowCount</span><span class="sxs-lookup"><span data-stu-id="9558b-168">KeyRowCount</span></span>  
 <span data-ttu-id="9558b-169">Общее число строк в полнотекстовом каталоге, содержащем конкретный ключ.</span><span class="sxs-lookup"><span data-stu-id="9558b-169">Total number of rows in the full-text catalog that contain a given key.</span></span>  
  
 <span data-ttu-id="9558b-170">MaxOccurrence</span><span class="sxs-lookup"><span data-stu-id="9558b-170">MaxOccurrence</span></span>  
 <span data-ttu-id="9558b-171">Наибольшее число вхождений для конкретного свойства в строке, хранящееся в полнотекстовом каталоге.</span><span class="sxs-lookup"><span data-stu-id="9558b-171">The largest occurrence stored in a full-text catalog for a given property in a row.</span></span>  
  
 <span data-ttu-id="9558b-172">MaxQueryRank</span><span class="sxs-lookup"><span data-stu-id="9558b-172">MaxQueryRank</span></span>  
 <span data-ttu-id="9558b-173">Максимальный ранг (1000), возвращенный средством полнотекстового поиска.</span><span class="sxs-lookup"><span data-stu-id="9558b-173">The maximum rank, 1000, returned by the Full-Text Engine.</span></span>  
  
  
### <a name="rank-computation-issues"></a><span data-ttu-id="9558b-174">Проблемы при вычислении ранга</span><span class="sxs-lookup"><span data-stu-id="9558b-174">Rank Computation Issues</span></span>  
 <span data-ttu-id="9558b-175">Процесс вычисления ранга зависит от нескольких факторов.</span><span class="sxs-lookup"><span data-stu-id="9558b-175">The process of computing rank, depends on a number of factors.</span></span>  <span data-ttu-id="9558b-176">Средства разбиения по словам в различных языках по-разному разбивают текст на лексемы.</span><span class="sxs-lookup"><span data-stu-id="9558b-176">Different language word breakers tokenize text differently.</span></span> <span data-ttu-id="9558b-177">Например, строку «dog-house» одно средство разбиения по словам может разбить на «dog» и «house», а другое — на «dog-house».</span><span class="sxs-lookup"><span data-stu-id="9558b-177">For example, the string "dog-house" could be broken into "dog" "house" by one word breaker and into "dog-house" by another.</span></span> <span data-ttu-id="9558b-178">Это означает, что соответствие и ранжирование будут зависеть от заданного языка, потому что в разных языках различаются не только слова, но и длина документа.</span><span class="sxs-lookup"><span data-stu-id="9558b-178">This means that matching and ranking will vary based on the language specified, because not only are the words different, but so is the document length.</span></span> <span data-ttu-id="9558b-179">Разница в длине документа может повлиять на ранжирование во всех запросах.</span><span class="sxs-lookup"><span data-stu-id="9558b-179">The document length difference can affect ranking for all queries.</span></span>  
  
 <span data-ttu-id="9558b-180">Такие статистические данные, как `IndexRowCount`, могут различаться в широких пределах.</span><span class="sxs-lookup"><span data-stu-id="9558b-180">Statistics such as `IndexRowCount` can vary widely.</span></span> <span data-ttu-id="9558b-181">Например, если каталог имеет 2 миллиарда строк в главном индексе, то новый документ индексируется хранящимся в памяти индексом. Поэтому ранги для этого документа, вычисленные на основе количества документов в индексе, хранящемся в памяти, могут отличаться от рангов для документов из главного индекса.</span><span class="sxs-lookup"><span data-stu-id="9558b-181">For example, if a catalog has 2 billion rows in the master index, then one new document is indexed into an in-memory intermediate index, and ranks for that document based on the number of documents in the in-memory index could be skewed compared with ranks for documents from the master index.</span></span> <span data-ttu-id="9558b-182">По этой причине рекомендуется после любого заполнения, приводящего к большому числу индексированных или переиндексированных строк, выполнять объединение индексов в главный индекс с помощью DDL-инструкции ALTER FULLTEXT CATALOG... Инструкция REORGANIZE языка [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9558b-182">For this reason, it is recommended that after any population that results in large number of rows being indexed or re-indexed the indexes be merged into a master index using the ALTER FULLTEXT CATALOG ... REORGANIZE [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="9558b-183">Средство полнотекстового поиска также автоматически объединит индексы на основе таких параметров, как количество промежуточных индексов и их размер.</span><span class="sxs-lookup"><span data-stu-id="9558b-183">The Full-Text Engine will also automatically merge the indexes based on parameters such as the number and size of intermediate indexes.</span></span>  
  
 <span data-ttu-id="9558b-184">Значения `MaxOccurrence` нормализуются в один из 32 диапазонов.</span><span class="sxs-lookup"><span data-stu-id="9558b-184">`MaxOccurrence` values are normalized into 1 of 32 ranges.</span></span> <span data-ttu-id="9558b-185">Это означает, например, что документ из 50 слов обрабатывается так же, как и документ из 100 слов.</span><span class="sxs-lookup"><span data-stu-id="9558b-185">This means, for example, that a document 50 words long is treated the same as a document 100 words long.</span></span> <span data-ttu-id="9558b-186">Ниже приведена используемая для нормализации таблица.</span><span class="sxs-lookup"><span data-stu-id="9558b-186">Below is the table used for normalization.</span></span> <span data-ttu-id="9558b-187">Поскольку длины документов находятся в диапазоне между смежными значениями таблицы 32 и 128, они фактически обрабатываются как имеющие одинаковую длину, 128 (32 < `docLength` <= 128).</span><span class="sxs-lookup"><span data-stu-id="9558b-187">Because the document lengths are in the range between adjacent table values 32 and 128, they are effectively treated as having the same length, 128 (32 < `docLength` <= 128).</span></span>  
  
```  
{ 16, 32, 128, 256, 512, 725, 1024, 1450, 2048, 2896, 4096, 5792, 8192, 11585,   
16384, 23170, 28000, 32768, 39554, 46340, 55938, 65536, 92681, 131072, 185363,   
262144, 370727, 524288, 741455, 1048576, 2097152, 4194304 };  
  
```  
  
  
### <a name="ranking-of-containstable"></a><span data-ttu-id="9558b-188">Ранжирование CONTAINSTABLE</span><span class="sxs-lookup"><span data-stu-id="9558b-188">Ranking of CONTAINSTABLE</span></span>  
 <span data-ttu-id="9558b-189">Ранжирование[CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) использует следующий алгоритм:</span><span class="sxs-lookup"><span data-stu-id="9558b-189">[CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) ranking uses the following algorithm:</span></span>  
  
```  
StatisticalWeight = Log2( ( 2 + IndexedRowCount ) / KeyRowCount )  
Rank = min( MaxQueryRank, HitCount * 16 * StatisticalWeight / MaxOccurrence )  
```  
  
 <span data-ttu-id="9558b-190">Фразовые соответствия ранжируются как отдельные ключи, за исключением того, что значение `KeyRowCount` (количество строк, содержащих эту фразу) является приближением — оно может быть неточным и выше фактического значения.</span><span class="sxs-lookup"><span data-stu-id="9558b-190">Phrase matches are ranked just like individual keys except that `KeyRowCount` (the number of rows containing the phrase) is estimated and can be inaccurate and higher than the actual number.</span></span>  
  
 <span data-ttu-id="9558b-191">**Ранжирование NEAR**</span><span class="sxs-lookup"><span data-stu-id="9558b-191">**Ranking of NEAR**</span></span>  
  
 <span data-ttu-id="9558b-192">Инструкция CONTAINSTABLE поддерживает выполнение запросов для двух и более выражений поиска с помощью параметра NEAR.</span><span class="sxs-lookup"><span data-stu-id="9558b-192">CONTAINSTABLE supports querying for two or more search terms in proximity to each other by using the NEAR option.</span></span> <span data-ttu-id="9558b-193">Ранжирующее значение для каждой из возвращаемых строк зависит от нескольких параметров.</span><span class="sxs-lookup"><span data-stu-id="9558b-193">The rank value of each returned row is based on several parameters.</span></span> <span data-ttu-id="9558b-194">Одним из основных факторов ранжирования является общее количество совпадений (или *попаданий*) по отношению к длине документа.</span><span class="sxs-lookup"><span data-stu-id="9558b-194">One major ranking factor is the total number of matches (or *hits*) relative to the length of the document.</span></span> <span data-ttu-id="9558b-195">Таким образом, например, если у документа из 100 слов и документа из 900 слов будет идентичный набор совпадений, то документ из 100 слов получит более высокий ранг.</span><span class="sxs-lookup"><span data-stu-id="9558b-195">Thus, for example, if a 100-word document and a 900-word document contain identical matches, the 100-word document is ranked higher.</span></span>  
  
 <span data-ttu-id="9558b-196">Суммарная длина каждого из попаданий в строке также учитывается в ранжировании этой строки (в зависимости от расстояния между первым и последним выражениями поиска для данного попадания).</span><span class="sxs-lookup"><span data-stu-id="9558b-196">The total length of each hit in a row will also contribute to the ranking of that row based on the distance between the first and last search terms of that hit.</span></span> <span data-ttu-id="9558b-197">Чем меньше расстояние, тем больше попадание увеличивает ранжирующее значение строки.</span><span class="sxs-lookup"><span data-stu-id="9558b-197">The smaller the distance, the more the hit contributes to the rank value of the row.</span></span> <span data-ttu-id="9558b-198">Если в полнотекстовом запросе не указывается целочисленное максимальное расстояние, то документ, содержащий лишь попадания с расстояниями, превышающими 100 логических выражений, получит ранг 0.</span><span class="sxs-lookup"><span data-stu-id="9558b-198">If a full-text query does not specify an integer as the maximum distance, a document that contains only hits whose distances are greater than 100 logical terms apart, will have a ranking of 0.</span></span>  
  
 <span data-ttu-id="9558b-199">**Ранжирование ISABOUT**</span><span class="sxs-lookup"><span data-stu-id="9558b-199">**Ranking of ISABOUT**</span></span>  
  
 <span data-ttu-id="9558b-200">CONTAINSTABLE поддерживает выполнение запросов для взвешенных выражений за счет использования параметра ISABOUT.</span><span class="sxs-lookup"><span data-stu-id="9558b-200">CONTAINSTABLE supports querying for weighted terms by using the ISABOUT option.</span></span> <span data-ttu-id="9558b-201">ISABOUT — это запрос в векторном пространстве, если пользоваться традиционной терминологией извлечения данных.</span><span class="sxs-lookup"><span data-stu-id="9558b-201">ISABOUT is a vector-space query in traditional information retrieval terminology.</span></span> <span data-ttu-id="9558b-202">В качестве алгоритма ранжирования по умолчанию используется широко известная формула Жаккарда.</span><span class="sxs-lookup"><span data-stu-id="9558b-202">The default ranking algorithm used is Jaccard, a widely known formula.</span></span> <span data-ttu-id="9558b-203">Ранжирование вычисляется для каждого термина в запросе, а затем результаты объединяются, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="9558b-203">The ranking is computed for each term in the query and then combined as described below.</span></span>  
  
```  
ContainsRank = same formula used for CONTAINSTABLE ranking of a single term (above).  
Weight = the weight specified in the query for each term. Default weight is 1.  
WeightedSum = ??[key=1 to n] ContainsRankKey * WeightKey  
Rank =  ( MaxQueryRank * WeightedSum ) / ( ( ??[key=1 to n] ContainsRankKey^2 )   
      + ( ??[key=1 to n] WeightKey^2 ) - ( WeightedSum ) )  
  
```  
  
  
### <a name="ranking-of-freetexttable"></a><span data-ttu-id="9558b-204">Ранжирование FREETEXTTABLE</span><span class="sxs-lookup"><span data-stu-id="9558b-204">Ranking of FREETEXTTABLE</span></span>  
 <span data-ttu-id="9558b-205">Ранжирование[FREETEXTTABLE](/sql/relational-databases/system-functions/freetexttable-transact-sql) основано на формуле ранжирования OKAPI BM25.</span><span class="sxs-lookup"><span data-stu-id="9558b-205">[FREETEXTTABLE](/sql/relational-databases/system-functions/freetexttable-transact-sql) ranking is based on the OKAPI BM25 ranking formula.</span></span> <span data-ttu-id="9558b-206">Запросы FREETEXTTABLE добавляют к запросу словоформы, полученные по исходным словам запроса. Эти слова обрабатываются как отдельные и независимые, не относящиеся к словам, производными которых они являются.</span><span class="sxs-lookup"><span data-stu-id="9558b-206">FREETEXTTABLE queries will add words to the query via inflectional generation (inflected forms of the original query words); these words are treated as separate words with no special relationship to the words from which they were generated.</span></span> <span data-ttu-id="9558b-207">Синонимы, сформированные с помощью тезауруса, обрабатываются как отдельные, независимые и взвешенные выражения.</span><span class="sxs-lookup"><span data-stu-id="9558b-207">Synonyms generated from the Thesaurus feature are treated as separate, equally weighted terms.</span></span> <span data-ttu-id="9558b-208">Каждое слово в запросе вносит свой вклад в ранжирование.</span><span class="sxs-lookup"><span data-stu-id="9558b-208">Each word in the query contributes to the rank.</span></span>  
  
```  
Rank = ??[Terms in Query] w ( ( ( k1 + 1 ) tf ) / ( K + tf ) ) * ( ( k3 + 1 ) qtf / ( k3 + qtf ) ) )  
Where:   
w is the Robertson-Sparck Jones weight.   
In simplified form, w is defined as:   
w = log10 ( ( ( r + 0.5 ) * ( N - R + r + 0.5 ) ) / ( ( R - r + 0.5 ) * ( n - r + 0.5 ) )  
N is the number of indexed rows for the property being queried.   
n is the number of rows containing the word.   
K is ( k1 * ( ( 1 - b ) + ( b * dl / avdl ) ) ).   
dl is the property length, in word occurrences.   
avdl is the average length of the property being queried, in word occurrences.   
k1, b, and k3 are the constants 1.2, 0.75, and 8.0, respectively.   
tf is the frequency of the word in the queried property in a specific row.   
qtf is the frequency of the term in the query.   
```  
  
  
## <a name="see-also"></a><span data-ttu-id="9558b-209">См. также:</span><span class="sxs-lookup"><span data-stu-id="9558b-209">See Also</span></span>  
 [<span data-ttu-id="9558b-210">Запросы с полнотекстовым поиском</span><span class="sxs-lookup"><span data-stu-id="9558b-210">Query with Full-Text Search</span></span>](query-with-full-text-search.md)  
  
  
