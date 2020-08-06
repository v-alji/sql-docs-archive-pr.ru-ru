---
title: Поиск похожих и связанных документов с помощью семантического поиска | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- semantic search [SQL Server], document similarity queries
ms.assetid: 9f527883-031b-442f-8e95-24bc0151ecbf
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b11493b5b04fa9308e3afbe56176251225248338
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668734"
---
# <a name="find-similar-and-related-documents-with-semantic-search"></a><span data-ttu-id="ade24-102">Поиск похожих и связанных документов с использованием семантического поиска</span><span class="sxs-lookup"><span data-stu-id="ade24-102">Find Similar and Related Documents with Semantic Search</span></span>
  <span data-ttu-id="ade24-103">Описывает процесс поиска схожих или связанных документов или текстовых значений и сведений об их сходстве или связи в столбцах, настроенных для статистического семантического индексирования.</span><span class="sxs-lookup"><span data-stu-id="ade24-103">Describes how to find similar or related documents or text values, and information about how they are similar or related, in columns that are configured for statistical semantic indexing.</span></span>  
  
##  <a name="finding-similar-or-related-documents"></a><a name="BasicsQuerySimilar"></a><span data-ttu-id="ade24-104">Поиск схожих или связанных документов</span><span class="sxs-lookup"><span data-stu-id="ade24-104">Finding Similar or Related Documents</span></span>  
  
###  <a name="how-to-find-similar-or-related-documents-with-semanticsimilaritytable"></a><a name="HowToQuerySimilar"></a><span data-ttu-id="ade24-105">Как найти похожие или связанные документы с помощью SEMANTICSIMILARITYTABLE</span><span class="sxs-lookup"><span data-stu-id="ade24-105">How To: Find Similar or Related Documents with SEMANTICSIMILARITYTABLE</span></span>  
 <span data-ttu-id="ade24-106">Чтобы найти схожие или связанные документы в данном столбце, запросите функцию [semanticsimilaritytable (Transact-SQL)](/sql/relational-databases/system-functions/semanticsimilaritytable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ade24-106">To identify similar or related documents in a specific column, query the function [semanticsimilaritytable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritytable-transact-sql).</span></span>  
  
 <span data-ttu-id="ade24-107">Функция**SEMANTICSIMILARITYTABLE** возвращает таблицу, состоящую из нуля, одной или нескольких строк, содержимое которых в указанном столбце семантически схоже с заданным документом.</span><span class="sxs-lookup"><span data-stu-id="ade24-107">**SEMANTICSIMILARITYTABLE** returns a table of zero, one, or more rows whose content in the specified column is semantically similar to the specified document.</span></span> <span data-ttu-id="ade24-108">На эту функцию набора строк можно ссылаться в предложении FROM инструкции SELECT как на обычное имя таблицы.</span><span class="sxs-lookup"><span data-stu-id="ade24-108">This rowset function can be referenced in the FROM clause of a SELECT statement like a regular table name.</span></span>  
  
 <span data-ttu-id="ade24-109">Искать схожие документы по разным столбцам невозможно.</span><span class="sxs-lookup"><span data-stu-id="ade24-109">You cannot query across columns for similar documents.</span></span> <span data-ttu-id="ade24-110">Функция **SEMANTICSIMILARITYTABLE** извлекает результаты только из столбца, совпадающего с исходным столбцом, определяемым аргументом **source_key** .</span><span class="sxs-lookup"><span data-stu-id="ade24-110">The **SEMANTICSIMILARITYTABLE** function only retrieves results from the same column as the source column, which is identified by the **source_key** argument.</span></span>  
  
 <span data-ttu-id="ade24-111">Подробные сведения о параметрах функции **SEMANTICSIMILARITYTABLE** и о возвращаемой таблице результатов см. в статье [semanticsimilaritytable (Transact-SQL)](/sql/relational-databases/system-functions/semanticsimilaritytable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ade24-111">For detailed information about the parameters required by the **SEMANTICSIMILARITYTABLE** function, and about the table of results that it returns, see [semanticsimilaritytable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritytable-transact-sql).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ade24-112">Для целевых столбцов должно быть включено полнотекстовое и семантическое индексирование.</span><span class="sxs-lookup"><span data-stu-id="ade24-112">The columns that you target must have full-text and semantic indexing enabled.</span></span>  
  
###  <a name="example-find-the-top-documents-that-are-similar-to-another-document"></a><a name="HowToIdentifySimilar"></a><span data-ttu-id="ade24-113">Пример. Поиск лучших документов, которые похожи на другой документ</span><span class="sxs-lookup"><span data-stu-id="ade24-113">Example: Find the Top Documents That Are Similar to Another Document</span></span>  
 <span data-ttu-id="ade24-114">В следующем примере извлекаются 10 лучших кандидатов, которые похожи на кандидат, указанный в *@CandidateID* таблице HumanResources. JobCandidate в образце базы данных AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="ade24-114">The following example retrieves the top 10 candidates who are similar to the candidate specified by *@CandidateID* from the HumanResources.JobCandidate table in the AdventureWorks2012 sample database.</span></span>  
  
```scr  
SELECT TOP(10) KEY_TBL.matched_document_key AS Candidate_ID  
FROM SEMANTICSIMILARITYTABLE  
    (  
    HumanResources.JobCandidate,  
    Resume,  
    @CandidateID  
    ) AS KEY_TBL  
ORDER BY KEY_TBL.score DESC;  
GO  
```  
  
##  <a name="finding-information-about-how-documents-are-similar-or-related"></a><a name="BasicsQuerySimilarity"></a><span data-ttu-id="ade24-115">Поиск сведений о схожих и связанных документах</span><span class="sxs-lookup"><span data-stu-id="ade24-115">Finding Information about How Documents Are Similar or Related</span></span>  
  
###  <a name="how-to-find-information-about-how-documents-are-similar-or-related-with-semanticsimilaritydetailstable"></a><a name="HowToQuerySimilarity"></a><span data-ttu-id="ade24-116">Инструкции. Поиск сведений о том, как документы похожи или связаны с SEMANTICSIMILARITYDETAILSTABLE</span><span class="sxs-lookup"><span data-stu-id="ade24-116">How To: Find Information about How Documents Are Similar or Related with SEMANTICSIMILARITYDETAILSTABLE</span></span>  
 <span data-ttu-id="ade24-117">Чтобы получить дополнительные сведения о ключевых фразах, которые делают документы схожими или связанными, вызовите функцию [semanticsimilaritydetailstable (Transact-SQL)](/sql/relational-databases/system-functions/semanticsimilaritydetailstable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ade24-117">To get information about the key phrases that make documents similar or related, you can query the function [semanticsimilaritydetailstable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritydetailstable-transact-sql).</span></span>  
  
 <span data-ttu-id="ade24-118">Функция **SEMANTICSIMILARITYDETAILSTABLE** возвращает таблицу из нуля, одной или нескольких строк с ключевыми фразами, общими для двух документов (исходного документа и сопоставленного документа), содержимое которых семантически схоже.</span><span class="sxs-lookup"><span data-stu-id="ade24-118">**SEMANTICSIMILARITYDETAILSTABLE** returns a table of zero, one, or more rows of key phrases common across two documents (a source document and a matched document) whose content is semantically similar.</span></span> <span data-ttu-id="ade24-119">На эту функцию набора строк можно ссылаться в предложении FROM инструкции SELECT как на обычное имя таблицы.</span><span class="sxs-lookup"><span data-stu-id="ade24-119">This rowset function can be referenced in the FROM clause of a SELECT statement like a regular table name.</span></span>  
  
 <span data-ttu-id="ade24-120">Подробные сведения о параметрах функции **SEMANTICSIMILARITYDETAILSTABLE** и о возвращаемой таблице результатов см. в статье [semanticsimilaritydetailstable (Transact-SQL)](/sql/relational-databases/system-functions/semanticsimilaritydetailstable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ade24-120">For detailed information about the parameters required by the **SEMANTICSIMILARITYDETAILSTABLE** function, and about the table of results that it returns, see [semanticsimilaritydetailstable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritydetailstable-transact-sql).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ade24-121">Для целевых столбцов должно быть включено полнотекстовое и семантическое индексирование.</span><span class="sxs-lookup"><span data-stu-id="ade24-121">The columns that you target must have full-text and semantic indexing enabled.</span></span>  
  
###  <a name="example-find-the-top-key-phrases-that-are-similar-between-documents"></a><a name="HowToSimilarPhrases"></a><span data-ttu-id="ade24-122">Пример. Поиск основных ключевых фраз, которые похожи на документы</span><span class="sxs-lookup"><span data-stu-id="ade24-122">Example: Find the Top Key Phrases That Are Similar between Documents</span></span>  
 <span data-ttu-id="ade24-123">В следующем примере производится извлечение 5 ключевых фраз, имеющих высший показатель подобия среди указанных кандидатов в таблице **HumanResources.JobCandidate** образца базы данных AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="ade24-123">The following example retrieves the 5 key phrases that have the highest similarity score between the specified candidates in **HumanResources.JobCandidate** table of the AdventureWorks2012 sample database.</span></span>  
  
```sql  
SELECT TOP(5) KEY_TBL.keyphrase, KEY_TBL.score  
FROM SEMANTICSIMILARITYDETAILSTABLE  
    (  
    HumanResources.JobCandidate,  
    Resume, @CandidateID,  
    Resume, @MatchedID  
    ) AS KEY_TBL  
ORDER BY KEY_TBL.score DESC;  
GO  
```  
  
  
