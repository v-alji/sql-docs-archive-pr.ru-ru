---
title: Поиск слов близких к другим с использованием оператора NEAR | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- word searches [full-text search]
- NEAR option [full-text search]
- phrase searches [full-text search]
- proximity searches [full-text search]
- full-text search [SQL Server], proximity searches
- full-text queries [SQL Server], proximity
- queries [full-text search], proximity
ms.assetid: 87520646-4865-49ae-8790-f766b80a41f3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8c2d187ea3ed951ac6f17eb4babc5f4f77451d4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735189"
---
# <a name="search-for-words-close-to-another-word-with-near"></a><span data-ttu-id="87d5d-102">Поиск слов близких к другим с использованием оператора NEAR</span><span class="sxs-lookup"><span data-stu-id="87d5d-102">Search for Words Close to Another Word with NEAR</span></span>
  <span data-ttu-id="87d5d-103">Выражение с учетом расположения (NEAR) может применяться в предикате [CONTAINS](/sql/t-sql/queries/contains-transact-sql) или функции [CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) для поиска слов или фраз, расположенных рядом.</span><span class="sxs-lookup"><span data-stu-id="87d5d-103">You can use a proximity term (NEAR) in a [CONTAINS](/sql/t-sql/queries/contains-transact-sql) predicate or [CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) function to search for words or phrases near one another.</span></span> <span data-ttu-id="87d5d-104">Также можно указать максимальное количество слов, которые не включаются в поиск и разделяют первое и последнее из искомых слов.</span><span class="sxs-lookup"><span data-stu-id="87d5d-104">You can also specify the maximum number of non-search terms that separate the first and last search terms.</span></span> <span data-ttu-id="87d5d-105">Кроме того, можно искать два слова или две фразы в любом порядке или в порядке, в котором они указаны.</span><span class="sxs-lookup"><span data-stu-id="87d5d-105">In addition, you can search for words or phrases in any order, or you can search for words and phrases in the order in which you specify them.</span></span> [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]<span data-ttu-id="87d5d-106">поддерживает как более раннее [универсальное выражение](#Generic_NEAR)с учетом расположения, которое теперь является устаревшим, так и [настраиваемое выражение](#Custom_NEAR)с учетом расположения, которое является новым в [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="87d5d-106">supports both the earlier [generic proximity term](#Generic_NEAR), which is now deprecated, and the [custom proximity term](#Custom_NEAR), which is new in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)].</span></span>  
  
##  <a name="the-custom-proximity-term"></a><a name="Custom_NEAR"></a><span data-ttu-id="87d5d-107">Настраиваемое выражение с учетом расположения</span><span class="sxs-lookup"><span data-stu-id="87d5d-107">The Custom Proximity Term</span></span>  
 <span data-ttu-id="87d5d-108">Настраиваемое выражение с учетом расположения дает следующие новые возможности.</span><span class="sxs-lookup"><span data-stu-id="87d5d-108">The custom proximity term introduces the following new capabilities:</span></span>  
  
-   <span data-ttu-id="87d5d-109">Можно указывать максимальное число слов, которые не включаются в поиск, или *максимальное расстояние*, которое может разделять первое и последнее слово поиска для возвращения результата.</span><span class="sxs-lookup"><span data-stu-id="87d5d-109">You can specify the maximum number of non-search terms, or *maximum distance*, that separates the first and last search terms in order to constitute a match.</span></span>  
  
-   <span data-ttu-id="87d5d-110">Если указать максимальное число слов, также можно указать, что слова поиска должны присутствовать в результате в заданном порядке.</span><span class="sxs-lookup"><span data-stu-id="87d5d-110">If you specify the maximum number of terms, you can also specify that matches must contain the search terms in the specified order.</span></span>  
  
 <span data-ttu-id="87d5d-111">Строка текста должна выполнять следующие условия.</span><span class="sxs-lookup"><span data-stu-id="87d5d-111">To qualify as a match, a string of text must:</span></span>  
  
-   <span data-ttu-id="87d5d-112">Начинаться с одного из указанных слов поиска и заканчиваться одним из других указанных слов поиска.</span><span class="sxs-lookup"><span data-stu-id="87d5d-112">Start with one of the specified search terms and end with the one of the other specified search terms.</span></span>  
  
-   <span data-ttu-id="87d5d-113">Содержать все указанные слова поиска.</span><span class="sxs-lookup"><span data-stu-id="87d5d-113">Contain all of the specified search terms.</span></span>  
  
-   <span data-ttu-id="87d5d-114">Число слов, которые не включаются в поиск, включая стоп-слова, которые могут разделять первое и последнее слово поиска, должно быть меньше максимального расстояния или равно ему, если оно указано.</span><span class="sxs-lookup"><span data-stu-id="87d5d-114">The number of non-search terms, including stopwords, that occur between the first and last search terms must be less than or equal to the maximum distance, if specified.</span></span>  
  
 <span data-ttu-id="87d5d-115">Базовый синтаксис:</span><span class="sxs-lookup"><span data-stu-id="87d5d-115">The basic syntax is:</span></span>  
  
 <span data-ttu-id="87d5d-116">NEAR (</span><span class="sxs-lookup"><span data-stu-id="87d5d-116">NEAR (</span></span>  
  
 <span data-ttu-id="87d5d-117">{</span><span class="sxs-lookup"><span data-stu-id="87d5d-117">{</span></span>  
  
 <span data-ttu-id="87d5d-118">*search_term* [,... *n* ]</span><span class="sxs-lookup"><span data-stu-id="87d5d-118">*search_term* [ ,...*n* ]</span></span>  
  
 |  
  
 <span data-ttu-id="87d5d-119">(*search_term* [,... *n* ]) [, <maximum_distance> [, <match_order>]]</span><span class="sxs-lookup"><span data-stu-id="87d5d-119">(*search_term* [ ,...*n* ] ) [, <maximum_distance> [, <match_order> ] ]</span></span>  
  
 <span data-ttu-id="87d5d-120">}</span><span class="sxs-lookup"><span data-stu-id="87d5d-120">}</span></span>  
  
 <span data-ttu-id="87d5d-121">)</span><span class="sxs-lookup"><span data-stu-id="87d5d-121">)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="87d5d-122">Дополнительные сведения о синтаксисе <custom_proximity_term> см. в разделе [CONTAINS (Transact-SQL)](/sql/t-sql/queries/contains-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="87d5d-122">For more information about the <custom_proximity_term> syntax, see [CONTAINS &#40;Transact-SQL&#41;](/sql/t-sql/queries/contains-transact-sql).</span></span>  
  
 <span data-ttu-id="87d5d-123">Например, можно искать слово «John», расположенное не далее двух слов от слова «Smith», следующим образом.</span><span class="sxs-lookup"><span data-stu-id="87d5d-123">For example, you could search for 'John' within two terms of 'Smith', as follows:</span></span>  
  
```  
CONTAINS(column_name, 'NEAR((John, Smith), 2)')  
```  
  
 <span data-ttu-id="87d5d-124">Примеры строк, удовлетворяющих этому запросу: «`John Jacob Smith`» и «`Smith, John`».</span><span class="sxs-lookup"><span data-stu-id="87d5d-124">Some examples of strings that match are "`John Jacob Smith`" and "`Smith, John`".</span></span> <span data-ttu-id="87d5d-125">В строке «`John Jones knows Fred Smith`» слова поиска разделены тремя другими словами, поэтому она не является результатом.</span><span class="sxs-lookup"><span data-stu-id="87d5d-125">The string "`John Jones knows Fred Smith`" contains three intervening non-search terms, so it is not a match.</span></span>  
  
 <span data-ttu-id="87d5d-126">Чтобы задать необходимый порядок слов, нужно изменить выражение с учетом расположения из примера на `NEAR((John, Smith),2, TRUE).` В этом случае слово`John`должно располагаться не далее двух слов от слова`Smith`, но только в случае, если слово`John`стоит перед словом`Smith`.</span><span class="sxs-lookup"><span data-stu-id="87d5d-126">To require that the terms be found in the specified order, you would change the example proximity term to `NEAR((John, Smith),2, TRUE).` This searches for "`John`" within two terms of "`Smith`" but only when "`John`" precedes "`Smith`".</span></span> <span data-ttu-id="87d5d-127">В языке с направлением чтения слева направо (например, в английском) этому запросу отвечает, например, строка`John Jacob Smith`.</span><span class="sxs-lookup"><span data-stu-id="87d5d-127">In a language that reads from left to right, such as English, an example of a string that matches is "`John Jacob Smith`".</span></span>  
  
 <span data-ttu-id="87d5d-128">Для языка с направлением чтения справа налево (например, арабского или иврита) средство полнотекстового поиска применяет заданные выражения в обратном порядке.</span><span class="sxs-lookup"><span data-stu-id="87d5d-128">Note that for a language that reads from right to left, such as Arabic or Hebrew, the Full-Text Engine applies the specified terms in reverse order.</span></span> <span data-ttu-id="87d5d-129">Кроме того, обозреватель объектов в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] автоматически меняет порядок отображения для слов, заданных на языках с направлением чтения справа налево.</span><span class="sxs-lookup"><span data-stu-id="87d5d-129">Also, Object Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] automatically reverses the display order of words specified in right-to-left languages.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="87d5d-130">Дополнительные сведения см. в подразделе [Дополнительные сведения о поиске по сходству](#Additional_Considerations) далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="87d5d-130">For more information, see "[Additional Considerations about Proximity Searches](#Additional_Considerations)," later in this topic.</span></span>  
  
### <a name="how-maximum-distance-is-measured"></a><span data-ttu-id="87d5d-131">Измерение максимального расстояния</span><span class="sxs-lookup"><span data-stu-id="87d5d-131">How Maximum Distance Is Measured</span></span>  
 <span data-ttu-id="87d5d-132">Максимальное расстояние, например 10 или 25, определяет, сколько слов, которые не включаются в поиск, включая стоп-слова, могут разделять первое и последнее слово поиска в заданной строке.</span><span class="sxs-lookup"><span data-stu-id="87d5d-132">A specific maximum distance, such as 10 or 25, determines how many non-search terms, including stopwords, can occur between the first and last search terms in a given string.</span></span> <span data-ttu-id="87d5d-133">Например, выражение `NEAR((dogs, cats, "hunting mice"), 3)` возвращает следующую строку, в которой общее число слов, которые не включаются в поиск, равно трем (`enjoy`,`but`и`avoid`):</span><span class="sxs-lookup"><span data-stu-id="87d5d-133">For example, `NEAR((dogs, cats, "hunting mice"), 3)` would return the following row, in which the total number of non-search terms is three ("`enjoy`", "`but`", and "`avoid`"):</span></span>  
  
 <span data-ttu-id="87d5d-134">"`Cats` `enjoy` `hunting mice``, but avoid` `dogs``.`"</span><span class="sxs-lookup"><span data-stu-id="87d5d-134">"`Cats` `enjoy` `hunting mice``, but avoid` `dogs``.`"</span></span>  
  
 <span data-ttu-id="87d5d-135">То же выражение с учетом расположения не вернет следующую строку, поскольку число слов, которые не включаются в поиск, равно четырем (`enjoy`,`but`,`usually`и`avoid`), что превышает максимальное расстояние:</span><span class="sxs-lookup"><span data-stu-id="87d5d-135">The same proximity term would not return the following row, because the maximum distance is exceeded by the four non-search terms ("`enjoy`", "`but`", "`usually`", and "`avoid`"):</span></span>  
  
 <span data-ttu-id="87d5d-136">"`Cats` `enjoy` `hunting mice``, but usually avoid` `dogs``.`"</span><span class="sxs-lookup"><span data-stu-id="87d5d-136">"`Cats` `enjoy` `hunting mice``, but usually avoid` `dogs``.`"</span></span>  
  
### <a name="combining-a-custom-proximity-term-with-other-terms"></a><span data-ttu-id="87d5d-137">Сочетание настраиваемого выражения с учетом расположения и других выражений</span><span class="sxs-lookup"><span data-stu-id="87d5d-137">Combining a Custom Proximity Term with Other Terms</span></span>  
 <span data-ttu-id="87d5d-138">Настраиваемое выражение с учетом расположения можно сочетать с некоторыми другими выражениями.</span><span class="sxs-lookup"><span data-stu-id="87d5d-138">You can combine a custom proximity term with some other terms.</span></span> <span data-ttu-id="87d5d-139">Операторы AND (&), OR (|) и AND NOT (&!) позволяют сочетать настраиваемое выражение с учетом расположения с другим настраиваемым выражением с учетом расположения, простым выражением или префиксным выражением.</span><span class="sxs-lookup"><span data-stu-id="87d5d-139">You can use AND (&), OR (|), or AND NOT (&!) to combine a custom proximity term with another custom proximity term, a simple term, or a prefix term.</span></span> <span data-ttu-id="87d5d-140">Пример:</span><span class="sxs-lookup"><span data-stu-id="87d5d-140">For example:</span></span>  
  
-   <span data-ttu-id="87d5d-141">CONTAINS('NEAR((*выражение1*,*выражение2*),5) AND *выражение3*')</span><span class="sxs-lookup"><span data-stu-id="87d5d-141">CONTAINS('NEAR((*term1*,*term2*),5) AND *term3*')</span></span>  
  
-   <span data-ttu-id="87d5d-142">CONTAINS('NEAR((*выражение1*,*выражение2*),5) OR *выражение3*')</span><span class="sxs-lookup"><span data-stu-id="87d5d-142">CONTAINS('NEAR((*term1*,*term2*),5) OR *term3*')</span></span>  
  
-   <span data-ttu-id="87d5d-143">CONTAINS('NEAR((*выражение1*,*выражение2*),5) AND NOT *выражение3*')</span><span class="sxs-lookup"><span data-stu-id="87d5d-143">CONTAINS('NEAR((*term1*,*term2*),5) AND NOT *term3*')</span></span>  
  
-   <span data-ttu-id="87d5d-144">CONTAINS('NEAR((*выражение1*,*выражение2*),5) AND NEAR((*выражение3*,*выражение4*),2)')</span><span class="sxs-lookup"><span data-stu-id="87d5d-144">CONTAINS('NEAR((*term1*,*term2*),5) AND NEAR((*term3*,*term4*),2)')</span></span>  
  
-   <span data-ttu-id="87d5d-145">CONTAINS('NEAR((*выражение1*,*выражение2*),5) OR NEAR((*выражение3*,*выражение4*),2, TRUE)')</span><span class="sxs-lookup"><span data-stu-id="87d5d-145">CONTAINS('NEAR((*term1*,*term2*),5) OR NEAR((*term3*,*term4*),2, TRUE)')</span></span>  
  
 <span data-ttu-id="87d5d-146">например следующие.</span><span class="sxs-lookup"><span data-stu-id="87d5d-146">For example,</span></span>  
  
```  
CONTAINS(column_name, 'NEAR((term1, term2), 5, TRUE) AND term3')  
```  
  
 <span data-ttu-id="87d5d-147">Нельзя сочетать настраиваемое выражение с учетом расположения с универсальным выражением с учетом расположения (*Выражение1* Near *выражение2*), термом поколения (...) или взвешенным выражением (FORMSOF...).</span><span class="sxs-lookup"><span data-stu-id="87d5d-147">You cannot combine a custom proximity term with a generic proximity term (*term1* NEAR *term2*), a generation term (ISABOUT ...), or a weighted term (FORMSOF ...).</span></span>  
  
### <a name="example-using-the-custom-proximity-term"></a><span data-ttu-id="87d5d-148">Пример. Использование настраиваемого выражения с учетом расположения</span><span class="sxs-lookup"><span data-stu-id="87d5d-148">Example: Using the Custom Proximity Term</span></span>  
 <span data-ttu-id="87d5d-149">В следующем примере в таблице `Production.Document` образца базы данных `AdventureWorks2012` выполняется поиск всех сводок по документам, где слово reflector содержится в одном документе со словом bracket.</span><span class="sxs-lookup"><span data-stu-id="87d5d-149">The following example searches the `Production.Document` table of the `AdventureWorks2012` sample database for all document summaries that contain the word "reflector" in the same document as the word "bracket".</span></span>  
  
```  
SELECT DocumentNode, Title, DocumentSummary  
FROM Production.Document AS DocTable   
INNER JOIN CONTAINSTABLE(Production.Document, Document,  
  'NEAR(bracket, reflector)' ) AS KEY_TBL  
  ON DocTable.DocumentNode = KEY_TBL.[KEY]  
WHERE KEY_TBL.RANK > 50  
ORDER BY KEY_TBL.RANK DESC;  
GO  
```  
  

  
##  <a name="additional-considerations-for-proximity-searches"></a><a name="Additional_Considerations"></a><span data-ttu-id="87d5d-150">Дополнительные рекомендации по поиску с учетом расположения</span><span class="sxs-lookup"><span data-stu-id="87d5d-150">Additional Considerations for Proximity Searches</span></span>  
 <span data-ttu-id="87d5d-151">В этом разделе описываются вопросы, касающиеся универсальных и настраиваемых поисковых запросов с учетом расположения.</span><span class="sxs-lookup"><span data-stu-id="87d5d-151">This section discusses consideration that affect both generic and custom proximity searches:</span></span>  
  
-   <span data-ttu-id="87d5d-152">Перекрывающиеся экземпляры слов поиска</span><span class="sxs-lookup"><span data-stu-id="87d5d-152">Overlapping occurrences of search terms</span></span>  
  
     <span data-ttu-id="87d5d-153">В запросе с учетом расположения всегда ищутся только неперекрывающиеся экземпляры.</span><span class="sxs-lookup"><span data-stu-id="87d5d-153">All proximity searches always look for only non-overlapping occurrences.</span></span> <span data-ttu-id="87d5d-154">Перекрывающиеся экземпляры слов поиска никогда не включаются в результаты.</span><span class="sxs-lookup"><span data-stu-id="87d5d-154">Overlapping occurrences of search terms never qualify as matches.</span></span> <span data-ttu-id="87d5d-155">Например, рассмотрим следующие выражение с учетом расположения, которое ищет слова`A`и`AA`в заданном порядке на расстоянии не более двух слов:</span><span class="sxs-lookup"><span data-stu-id="87d5d-155">For example, consider the following proximity term, which searches "`A`" and "`AA`" in this order with a maximum distance of two terms:</span></span>  
  
    ```  
    CONTAINS(column_name, 'NEAR((A,AA),2, TRUE')  
    ```  
  
     <span data-ttu-id="87d5d-156">Возможные результаты:`AAA`,`A.AA`и`A..AA`.</span><span class="sxs-lookup"><span data-stu-id="87d5d-156">The possible matches are as "`AAA`", "`A.AA`", and "`A..AA`".</span></span> <span data-ttu-id="87d5d-157">Строки, содержащие только`AA`, не будут результатом.</span><span class="sxs-lookup"><span data-stu-id="87d5d-157">Rows containing just "`AA`" would not match.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="87d5d-158">Можно указывать перекрывающиеся выражения, например `NEAR("mountain bike", "bike trails")` или `(NEAR(comfort*, comfortable), 5)`.</span><span class="sxs-lookup"><span data-stu-id="87d5d-158">You can specify terms that overlap, for example, `NEAR("mountain bike", "bike trails")` or `(NEAR(comfort*, comfortable), 5)`.</span></span> <span data-ttu-id="87d5d-159">Указание перекрывающихся выражений повышает сложность запроса за счет увеличения числа возможных перестановок.</span><span class="sxs-lookup"><span data-stu-id="87d5d-159">Specifying a overlapping terms increases the complexity of the query by increasing the possible match permutations.</span></span> <span data-ttu-id="87d5d-160">Если указать большое число таких перекрывающихся выражений, запрос может исчерпать ресурсы и завершиться с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="87d5d-160">If you specify a large number of such overlapping terms, the query can run out of resources and fail.</span></span> <span data-ttu-id="87d5d-161">В этом случае упростите запрос и повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="87d5d-161">If this occurs, simplify the query and try again.</span></span>  
  
-   <span data-ttu-id="87d5d-162">В универсальных и настраиваемых выражениях NEAR (независимо от указания максимального расстояния) указывается логическое, а не абсолютное расстояние между выражениями.</span><span class="sxs-lookup"><span data-stu-id="87d5d-162">Both generic NEAR and custom NEAR (regardless of whether a maximum distance is specified) indicate the logical distance between terms, rather than the absolute distance between them.</span></span> <span data-ttu-id="87d5d-163">Например, выражения, находящиеся в различных фразах и выражениях в пределах абзаца, считаются более удаленными друг от друга, чем фразы, находящиеся в одной фразе или в одном предложении, независимо от фактического расстояния между ними, поскольку предполагается, что в первом случае выражения в меньшей степени связаны.</span><span class="sxs-lookup"><span data-stu-id="87d5d-163">For example, terms within different phrases or sentences within a paragraph are treated as farther apart than terms in the same phrase or sentence, regardless of their actual proximity, on the assumption that they are less related.</span></span> <span data-ttu-id="87d5d-164">Аналогично выражения из различных абзацев считаются еще более удаленными друг от друга.</span><span class="sxs-lookup"><span data-stu-id="87d5d-164">Likewise, terms in different paragraphs are treated as being even farther apart.</span></span> <span data-ttu-id="87d5d-165">Если в результат входит конец предложения, абзаца или главы, то интервал, используемый для определения ранга документа, увеличивается соответственно на 8, 128 или 1024.</span><span class="sxs-lookup"><span data-stu-id="87d5d-165">If a match spans the end of a sentence, paragraph, or chapter, the gap used for ranking a document is increased by 8, 128, or 1024, respectively.</span></span>  
  
-   <span data-ttu-id="87d5d-166">Влияние выражений с учетом расположения на ранжирование, выполняемое функцией CONTAINSTABLE</span><span class="sxs-lookup"><span data-stu-id="87d5d-166">Impact of proximity terms on ranking by the CONTAINSTABLE function</span></span>  
  
     <span data-ttu-id="87d5d-167">Если выражение NEAR используется в функции CONTAINSTABLE, то на ранг документа влияет число совпадений в документе относительно его длины, а также расстояние между первым и последним выражением поиска в каждом совпадении.</span><span class="sxs-lookup"><span data-stu-id="87d5d-167">When NEAR is used in the CONTAINSTABLE function, the number of hits in a document relative to its length as well as the distance between the first and last search terms in each of the hits affects the ranking of each document.</span></span> <span data-ttu-id="87d5d-168">Для универсального выражения с учетом расположения, если искомые выражения находятся на расстоянии более >50 логических выражений, то для документа возвращается ранг 0.</span><span class="sxs-lookup"><span data-stu-id="87d5d-168">For a generic proximity term, if the matched search terms are >50 logical terms apart, the rank returned on a document is 0.</span></span> <span data-ttu-id="87d5d-169">Для настраиваемого выражения с учетом расположения, в котором не указано целочисленное значение максимального расстояния, документ, содержащий только совпадения с интервалом >100 логических выражений, получит ранг 0.</span><span class="sxs-lookup"><span data-stu-id="87d5d-169">For a custom proximity term that does not specify an integer as the maximum distance, a document that contains only hits whose gap is >100 logical terms will receive a ranking of 0.</span></span> <span data-ttu-id="87d5d-170">Дополнительные сведения о ранжировании настраиваемых поисковых запросов с учетом расположения см. в разделе [Ограничение количества результатов поиска с использованием функции RANK](limit-search-results-with-rank.md).</span><span class="sxs-lookup"><span data-stu-id="87d5d-170">For more information about ranking of custom proximity searches, see [Limit Search Results with RANK](limit-search-results-with-rank.md).</span></span>  
  
-   <span data-ttu-id="87d5d-171">Параметр сервера **transform noise words**</span><span class="sxs-lookup"><span data-stu-id="87d5d-171">The **transform noise words** server option</span></span>  
  
     <span data-ttu-id="87d5d-172">Значение параметра **transform noise words** влияет на обработку в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] стоп-слов, указанных в поисковых запросах с учетом расположения.</span><span class="sxs-lookup"><span data-stu-id="87d5d-172">The value of **transform noise words** impacts how [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] treats stopwords if they are specified in proximity searches.</span></span> <span data-ttu-id="87d5d-173">Дополнительные сведения см. в разделе [transform noise words Server Configuration Option](../../database-engine/configure-windows/transform-noise-words-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="87d5d-173">For more information, see [transform noise words Server Configuration Option](../../database-engine/configure-windows/transform-noise-words-server-configuration-option.md).</span></span>  
  

  
##  <a name="the-deprecated-generic-proximity-term"></a><a name="Generic_NEAR"></a><span data-ttu-id="87d5d-174">Нерекомендуемое универсальное выражение с учетом расположения</span><span class="sxs-lookup"><span data-stu-id="87d5d-174">The Deprecated Generic Proximity Term</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]<span data-ttu-id="87d5d-175">Рекомендуется использовать [настраиваемое выражение](#Custom_NEAR)с учетом расположения.</span><span class="sxs-lookup"><span data-stu-id="87d5d-175">We recommend that you use the [custom proximity term](#Custom_NEAR).</span></span>  
  
 <span data-ttu-id="87d5d-176">Универсальное выражение с учетом расположения показывает, что для возвращения результата все указанные слова поиска должны встречаться в документе независимо от числа прочих слов ( *расстояния*) между словами поиска.</span><span class="sxs-lookup"><span data-stu-id="87d5d-176">A generic proximity term indicates that the specified search terms must all occur in a document for a match to be returned, regardless of the number of non-search terms (the *distance*) between the search terms.</span></span> <span data-ttu-id="87d5d-177">Базовый синтаксис:</span><span class="sxs-lookup"><span data-stu-id="87d5d-177">The basic syntax is:</span></span>  
  
 <span data-ttu-id="87d5d-178">{ *search_term* {Near | ~} *search_term* } [ ,... *n* ]</span><span class="sxs-lookup"><span data-stu-id="87d5d-178">{ *search_term* { NEAR | ~ } *search_term* } [ ,...*n* ]</span></span>  
  
 <span data-ttu-id="87d5d-179">Например, в следующем примере для получения результата должны встречаться оба слова (fox и chicken) в любом порядке:</span><span class="sxs-lookup"><span data-stu-id="87d5d-179">For example, in the following examples, the words 'fox' and 'chicken' must both appear, in either order, to produce a match:</span></span>  
  
-   `CONTAINS(column_name, 'fox NEAR chicken')`  
  
-   `CONTAINSTABLE(table_name, column_name, 'fox ~ chicken')`  
  
> [!NOTE]  
>  <span data-ttu-id="87d5d-180">Сведения о синтаксисе <generic_proximity_term> см. в разделе [CONTAINS (Transact-SQL)](/sql/t-sql/queries/contains-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="87d5d-180">For information about the <generic_proximity_term> syntax, see [CONTAINS &#40;Transact-SQL&#41;](/sql/t-sql/queries/contains-transact-sql).</span></span>  
  
 <span data-ttu-id="87d5d-181">Дополнительные сведения см. в подразделе [Дополнительные сведения о поиске по сходству](#Additional_Considerations) далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="87d5d-181">For more information, see "[Additional Considerations about Proximity Searches](#Additional_Considerations)," later in this topic.</span></span>  
  
### <a name="combining-a-generic-proximity-term-with-other-terms"></a><span data-ttu-id="87d5d-182">Сочетание универсального выражения с учетом расположения и других выражений</span><span class="sxs-lookup"><span data-stu-id="87d5d-182">Combining a Generic Proximity Term with Other Terms</span></span>  
 <span data-ttu-id="87d5d-183">Операторы AND (&), OR (|) и AND NOT (&!) позволяют сочетать универсальное выражение с учетом расположения с другим универсальным выражением с учетом расположения, простым выражением или префиксным выражением.</span><span class="sxs-lookup"><span data-stu-id="87d5d-183">You can use AND (&), OR (|), or AND NOT (&!) to combine a generic proximity term with another generic proximity term, a simple term, or a prefix term.</span></span> <span data-ttu-id="87d5d-184">Пример:</span><span class="sxs-lookup"><span data-stu-id="87d5d-184">For example:</span></span>  
  
```  
CONTAINSTABLE (Production.ProductDescription,  
   Description,   
   '(light NEAR aluminum) OR  
   (lightweight NEAR aluminum)'  
)  
```  
  
 <span data-ttu-id="87d5d-185">Универсальное выражение с учетом расположения нельзя сочетать с настраиваемым выражением с учетом расположения, таким как `NEAR((term1,term2),5)` , взвешенное выражение (FORMSOF...) или выражение с более весомым сроком.</span><span class="sxs-lookup"><span data-stu-id="87d5d-185">You cannot combine a generic proximity term with a custom proximity term, such as `NEAR((term1,term2),5)`, a weighted term (ISABOUT ...), or a generational term (FORMSOF ...).</span></span>  
  
### <a name="example-using-the-generic-proximity-term"></a><span data-ttu-id="87d5d-186">Пример. Использование универсального выражения с учетом расположения</span><span class="sxs-lookup"><span data-stu-id="87d5d-186">Example: Using the Generic Proximity Term</span></span>  
 <span data-ttu-id="87d5d-187">В следующем примере универсальное выражение с учетом расположения используется для поиска слова «reflector» в одном документе со словом «bracket».</span><span class="sxs-lookup"><span data-stu-id="87d5d-187">The following example uses the generic proximity term to search for the word "reflector" in the same document as the word "bracket".</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
  
SELECT DocumentNode, Title, DocumentSummary  
FROM Production.Document AS DocTable INNER JOIN  
  CONTAINSTABLE(Production.Document, Document,  
  '(reflector NEAR bracket)' ) AS KEY_TBL  
  ON DocTable.DocumentNode = KEY_TBL.[KEY]  
ORDER BY KEY_TBL.RANK DESC;  
GO  
```  
  
 <span data-ttu-id="87d5d-188">Обратите внимание, что для достижения такого же результата можно поменять местами термы в функции CONTAINSTABLE:</span><span class="sxs-lookup"><span data-stu-id="87d5d-188">Notice that you can also reverse the terms in CONTAINSTABLE to get the same result:</span></span>  
  
```  
CONTAINSTABLE(Production.Document, Document, '(bracket NEAR reflector)' ) AS KEY_TBL  
```  
  
 <span data-ttu-id="87d5d-189">Вместо ключевого слова NEAR в предыдущем запросе можно использовать «тильду» (~) и получить те же результаты:</span><span class="sxs-lookup"><span data-stu-id="87d5d-189">You can use the tilde character (~) in place of the NEAR keyword in the earlier query, and get the same results:</span></span>  
  
```  
CONTAINSTABLE(Production.Document, Document, '(reflector ~ bracket)' ) AS KEY_TBL  
```  
  
 <span data-ttu-id="87d5d-190">В условиях поиска можно указать более двух слов или фраз.</span><span class="sxs-lookup"><span data-stu-id="87d5d-190">More than two words or phrases can be specified in the search conditions.</span></span> <span data-ttu-id="87d5d-191">Например, можно написать:</span><span class="sxs-lookup"><span data-stu-id="87d5d-191">For example, it is possible to write:</span></span>  
  
```  
CONTAINSTABLE(Production.Document, Document, '(reflector ~ bracket ~ installation)' ) AS KEY_TBL  
```  
  
 <span data-ttu-id="87d5d-192">Это значит, что слово «reflector» должно находиться в одном документе со словом «bracket», а слово «bracket» должно находиться в одном документе со словом «installation».</span><span class="sxs-lookup"><span data-stu-id="87d5d-192">This means that "reflector" must be in the same document as "bracket", and "bracket" must be in the same document as "installation".</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="87d5d-193">См. также:</span><span class="sxs-lookup"><span data-stu-id="87d5d-193">See Also</span></span>  
 <span data-ttu-id="87d5d-194">[CONTAINSTABLE (Transact-SQL)](/sql/relational-databases/system-functions/containstable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="87d5d-194">[CONTAINSTABLE &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/containstable-transact-sql) </span></span>  
 <span data-ttu-id="87d5d-195">[Запрос с полнотекстовым поиском](query-with-full-text-search.md) </span><span class="sxs-lookup"><span data-stu-id="87d5d-195">[Query with Full-Text Search](query-with-full-text-search.md) </span></span>  
 [<span data-ttu-id="87d5d-196">CONTAINS (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="87d5d-196">CONTAINS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/contains-transact-sql)  
  
  
