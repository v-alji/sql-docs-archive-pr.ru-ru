---
title: Поиск ключевых фраз в документах с использованием семантического поиска | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- semantic search [SQL Server], key phrase queries
ms.assetid: 6ee3676e-ed5d-43ec-aeca-1eed78967111
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8388fb704bf13f44d025e6e32a1450d537f61832
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730450"
---
# <a name="find-key-phrases-in-documents-with-semantic-search"></a><span data-ttu-id="4b7a6-102">Поиск ключевых фраз в документах с использованием семантического поиска</span><span class="sxs-lookup"><span data-stu-id="4b7a6-102">Find Key Phrases in Documents with Semantic Search</span></span>
  <span data-ttu-id="4b7a6-103">Описывает способ поиска ключевых фраз в документах или текстовых столбцах, настроенных для статистического семантического индексирования.</span><span class="sxs-lookup"><span data-stu-id="4b7a6-103">Describes how to find the key phrases in documents or text columns that are configured for statistical semantic indexing.</span></span>  
  
##  <a name="finding-key-phrases-in-documents"></a><a name="BasicsQueryKey"></a><span data-ttu-id="4b7a6-104">Поиск ключевых фраз в документах</span><span class="sxs-lookup"><span data-stu-id="4b7a6-104">Finding Key Phrases in Documents</span></span>  
  
###  <a name="how-to-find-the-key-phrases-in-documents-with-semantickeyphrasetable"></a><a name="howtofind"></a><span data-ttu-id="4b7a6-105">Как найти ключевые фразы в документах с помощью SEMANTICKEYPHRASETABLE</span><span class="sxs-lookup"><span data-stu-id="4b7a6-105">How to: Find the Key Phrases in Documents with SEMANTICKEYPHRASETABLE</span></span>  
 <span data-ttu-id="4b7a6-106">Для поиска ключевых фраз в определенных документах или для поиска документов, содержащих определенные ключевые фразы, можно запросить функцию [semantickeyphrasetable (Transact-SQL)](/sql/relational-databases/system-functions/semantickeyphrasetable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4b7a6-106">To identify the key phrases in specific documents, or to identify documents that contain specific key phrases, query the function [semantickeyphrasetable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semantickeyphrasetable-transact-sql).</span></span>  
  
 <span data-ttu-id="4b7a6-107">Функция SEMANTICKEYPHRASETABLE возвращает таблицу с нулем, одной или несколькими строками для ключевых фраз, связанных со столбцами в указанной таблице.</span><span class="sxs-lookup"><span data-stu-id="4b7a6-107">SEMANTICKEYPHRASETABLE returns a table with zero, one, or more rows for those key phrases associated with columns in the specified table.</span></span> <span data-ttu-id="4b7a6-108">На эту функцию набора строк можно ссылаться из предложения FROM инструкции SELECT так же, как и на обычное имя таблицы.</span><span class="sxs-lookup"><span data-stu-id="4b7a6-108">This rowset function can be referenced in the FROM clause of a SELECT statement as if it were a regular table name.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4b7a6-109">В [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]только отдельные слова индексируются для семантического поиска. Фразы из нескольких слов (n-граммы) не индексируются.</span><span class="sxs-lookup"><span data-stu-id="4b7a6-109">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], only single words are indexed for semantic search; multi-word phrases (ngrams) are not indexed.</span></span> <span data-ttu-id="4b7a6-110">Кроме того, различные формы одного и того же слова индексируются отдельно. Например, «компьютер» и «компьютеры» индексируются отдельно.</span><span class="sxs-lookup"><span data-stu-id="4b7a6-110">Also, various forms of the same word are indexed separately; for example, "computer" and "computers" are indexed separately.</span></span>  
  
 <span data-ttu-id="4b7a6-111">Подробные сведения о параметрах, необходимых для функции SEMANTICKEYPHRASETABLE, и о таблице возвращаемых ей результатов см. в разделе [semantickeyphrasetable (Transact-SQL)](/sql/relational-databases/system-functions/semantickeyphrasetable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4b7a6-111">For detailed information about the parameters required by the SEMANTICKEYPHRASETABLE function, and about the table of results that it returns, see [semantickeyphrasetable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semantickeyphrasetable-transact-sql).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4b7a6-112">Для целевых столбцов должно быть включено полнотекстовое и семантическое индексирование.</span><span class="sxs-lookup"><span data-stu-id="4b7a6-112">The columns that you target must have full-text and semantic indexing enabled.</span></span>  
  
###  <a name="example-1-find-the-top-key-phrases-in-a-specific-document"></a><a name="HowToTopPhrases"></a><span data-ttu-id="4b7a6-113">Пример 1. Поиск наиболее важных ключевых фраз в определенном документе</span><span class="sxs-lookup"><span data-stu-id="4b7a6-113">Example 1: Find the Top Key Phrases in a Specific Document</span></span>  
 <span data-ttu-id="4b7a6-114">В следующем примере извлекаются 10 первых ключевых фраз из документа, указанного в переменной @DocumentId в столбце Document таблицы Production.Document в тестовой базе данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="4b7a6-114">The following example retrieves the top 10 key phrases from the document specified by the @DocumentId variable in the Document column of the Production.Document table of the AdventureWorks sample database.</span></span> <span data-ttu-id="4b7a6-115">Переменная @DocumentId представляет значение из ключевого столбца полнотекстового индекса.</span><span class="sxs-lookup"><span data-stu-id="4b7a6-115">The @DocumentId variable represents a value from the key column of the full-text index.</span></span>  
  
```sql  
SELECT TOP(10) KEYP_TBL.keyphrase  
FROM SEMANTICKEYPHRASETABLE  
    (  
    Production.Document,  
    Document,  
    @DocumentId  
    ) AS KEYP_TBL  
ORDER BY KEYP_TBL.score DESC;  
GO  
```  
  
 <span data-ttu-id="4b7a6-116">Функция **SEMANTICKEYPHRASETABLE** эффективно извлекает эти результаты поиском по индексу, а не путем просмотра таблицы.</span><span class="sxs-lookup"><span data-stu-id="4b7a6-116">The **SEMANTICKEYPHRASETABLE** function retrieves these results efficiently by using an index seek instead of a table scan.</span></span>  
  
###  <a name="example-2-find-the-top-documents-that-contain-a-specific-key-phrase"></a><a name="HowToTopDocuments"></a><span data-ttu-id="4b7a6-117">Пример 2. Поиск лучших документов, содержащих определенную ключевую фразу</span><span class="sxs-lookup"><span data-stu-id="4b7a6-117">Example 2: Find the Top Documents that Contain a Specific Key Phrase</span></span>  
 <span data-ttu-id="4b7a6-118">В следующем примере извлекаются 25 первых документов, содержащих ключевую фразу Bracket в столбце Document таблицы Production.Document примера базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="4b7a6-118">The following example retrieves the top 25 documents that contain the key phrase "Bracket" from the Document column of the Production.Document table of the AdventureWorks sample database.</span></span>  
  
```sql  
SELECT TOP (25) DOC_TBL.DocumentID, DOC_TBL.DocumentSummary  
FROM Production.Document AS DOC_TBL  
    INNER JOIN SEMANTICKEYPHRASETABLE  
    (  
    Production.Document,  
    Document  
    ) AS KEYP_TBL  
ON DOC_TBL.DocumentID = KEYP_TBL.document_key  
WHERE KEYP_TBL.keyphrase = 'Bracket'  
ORDER BY KEYP_TBL.Score DESC;  
GO  
```  
  
  
