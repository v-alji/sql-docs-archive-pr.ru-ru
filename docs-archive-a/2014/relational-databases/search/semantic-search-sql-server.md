---
title: Семантический поиск (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- semantic search [SQL Server]
- semantic search [SQL Server], overview
- statistical semantic search [SQL Server]
- statistical semantic search [SQL Server], overview
ms.assetid: cd8faa9d-07db-420d-93f4-a2ea7c974b97
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 91062864b77ba3c62a87d66b8ff93068f9c10c8c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735181"
---
# <a name="semantic-search-sql-server"></a><span data-ttu-id="54d9b-102">Семантический поиск (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="54d9b-102">Semantic Search (SQL Server)</span></span>
  <span data-ttu-id="54d9b-103">Статистический семантический поиск обеспечивает глубокий анализ неструктурированных документов, хранящихся в базах данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] путем извлечения и индексирования статистически соответствующих *ключевых фраз*.</span><span class="sxs-lookup"><span data-stu-id="54d9b-103">Statistical Semantic Search provides deep insight into unstructured documents stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases by extracting and indexing statistically relevant *key phrases*.</span></span> <span data-ttu-id="54d9b-104">Эти ключевые фразы используются также для идентификации и индексирования *схожих или связанных документов*.</span><span class="sxs-lookup"><span data-stu-id="54d9b-104">Then it also uses these key phrases to identify and index *documents that are similar or related*.</span></span>  
  
 <span data-ttu-id="54d9b-105">Запросы к этим семантическим индексам создаются с помощью трех функций наборов строк языка Transact-SQL для получения результатов в виде структурированных данных.</span><span class="sxs-lookup"><span data-stu-id="54d9b-105">You query these semantic indexes by using three Transact-SQL rowset functions to retrieve the results as structured data.</span></span>  
  
##  <a name="what-can-i-do-with-semantic-search"></a><a name="whatcanido"></a><span data-ttu-id="54d9b-106">Что можно сделать с помощью семантического поиска?</span><span class="sxs-lookup"><span data-stu-id="54d9b-106">What Can I Do with Semantic Search?</span></span>  
 <span data-ttu-id="54d9b-107">Семантический поиск основан на существующей функции полнотекстового поиска в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], но дает новые возможности, выходящие за пределы поиска ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="54d9b-107">Semantic search builds upon the existing full-text search feature in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], but enables new scenarios that extend beyond keyword searches.</span></span> <span data-ttu-id="54d9b-108">Полнотекстовый поиск позволяет запрашивать *слова* в документе, а семантический поиск позволяет запрашивать *значение* документа.</span><span class="sxs-lookup"><span data-stu-id="54d9b-108">While full-text search lets you query the *words* in a document, semantic search lets you query the *meaning* of the document.</span></span> <span data-ttu-id="54d9b-109">Среди новых возможностей автоматическое извлечение тегов, обнаружение связанного содержимого и иерархическая навигация по схожему содержимому.</span><span class="sxs-lookup"><span data-stu-id="54d9b-109">Solutions that are now possible include automatic tag extraction, related content discovery, and hierarchical navigation across similar content.</span></span> <span data-ttu-id="54d9b-110">Например, можно запросить индекс ключевых фраз, чтобы создать классификацию для организации или совокупности документов.</span><span class="sxs-lookup"><span data-stu-id="54d9b-110">For example, you can query the index of key phrases to build the taxonomy for an organization, or for a corpus of documents.</span></span> <span data-ttu-id="54d9b-111">Или можно запросить индекс сходства документов для выявления резюме, соответствующих описанию вакансии.</span><span class="sxs-lookup"><span data-stu-id="54d9b-111">Or, you can query the document similarity index to identify resumes that match a job description.</span></span>  
  
 <span data-ttu-id="54d9b-112">Следующие примеры демонстрируют возможности семантического поиска.</span><span class="sxs-lookup"><span data-stu-id="54d9b-112">The following examples demonstrate the capabilities of Semantic Search.</span></span>  
  
###  <a name="find-the-key-phrases-in-a-document"></a><a name="find1"></a><span data-ttu-id="54d9b-113">Поиск ключевых фраз в документе</span><span class="sxs-lookup"><span data-stu-id="54d9b-113">Find the Key Phrases in a Document</span></span>  
 <span data-ttu-id="54d9b-114">Следующий запрос получает ключевые фразы, которые были определены в образце документа.</span><span class="sxs-lookup"><span data-stu-id="54d9b-114">The following query gets the key phrases that were identified in the sample document.</span></span> <span data-ttu-id="54d9b-115">Он возвращает список результаты в порядке убывания показателя, обозначающего статистическую значимость каждой ключевой фразы.</span><span class="sxs-lookup"><span data-stu-id="54d9b-115">It presents the results in descending order by the score that ranks the statistical significance of each key phrase.</span></span> <span data-ttu-id="54d9b-116">Этот запрос вызывает функцию [semantickeyphrasetable (Transact-SQL)](/sql/relational-databases/system-functions/semantickeyphrasetable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="54d9b-116">This query calls the [semantickeyphrasetable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semantickeyphrasetable-transact-sql) function.</span></span>  
  
```sql  
SET @Title = 'Sample Document.docx'  
  
SELECT @DocID = DocumentID  
    FROM Documents  
    WHERE DocumentTitle = @Title  
  
SELECT @Title AS Title, keyphrase, score  
    FROM SEMANTICKEYPHRASETABLE(Documents, *, @DocID)  
    ORDER BY score DESC  
  
```  
  
  
  
###  <a name="find-similar-or-related-documents"></a><a name="find2"></a><span data-ttu-id="54d9b-117">Поиск похожих или связанных документов</span><span class="sxs-lookup"><span data-stu-id="54d9b-117">Find Similar or Related Documents</span></span>  
 <span data-ttu-id="54d9b-118">Следующий запрос возвращает документы, которые были определены как схожие с образцом документа или связанные.</span><span class="sxs-lookup"><span data-stu-id="54d9b-118">The following query gets the documents that were identified as similar or related to the sample document.</span></span> <span data-ttu-id="54d9b-119">Он возвращает результаты в порядке убывания показателя, обозначающего схожесть двух документов.</span><span class="sxs-lookup"><span data-stu-id="54d9b-119">It presents the results in descending order by the score that ranks the similarity of the 2 documents.</span></span> <span data-ttu-id="54d9b-120">Этот запрос вызывает функцию [semanticsimilaritytable (Transact-SQL)](/sql/relational-databases/system-functions/semanticsimilaritytable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="54d9b-120">This query calls the [semanticsimilaritytable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritytable-transact-sql) function.</span></span>  
  
```vb  
SET @Title = 'Sample Document.docx'  
  
SELECT @DocID = DocumentID  
    FROM Documents  
    WHERE DocumentTitle = @Title  
  
SELECT @Title AS SourceTitle, DocumentTitle AS MatchedTitle,  
        DocumentID, score  
    FROM SEMANTICSIMILARITYTABLE(Documents, *, @DocID)  
    INNER JOIN Documents ON DocumentID = matched_document_key  
    ORDER BY score DESC  
  
```  
  
  
  
###  <a name="find-the-key-phrases-that-make-documents-similar-or-related"></a><a name="find3"></a><span data-ttu-id="54d9b-121">Поиск ключевых фраз, которые делают документы схожими или связанными</span><span class="sxs-lookup"><span data-stu-id="54d9b-121">Find the Key Phrases That Make Documents Similar or Related</span></span>  
 <span data-ttu-id="54d9b-122">Следующий запрос возвращает ключевые фразы, которые делают два документа схожими или связанными.</span><span class="sxs-lookup"><span data-stu-id="54d9b-122">The following query gets the key phrases that make the 2 sample documents similar or related to one another.</span></span> <span data-ttu-id="54d9b-123">Он возвращает результаты в порядке убывания показателя, обозначающего вес каждой ключевой фразы.</span><span class="sxs-lookup"><span data-stu-id="54d9b-123">It presents the results in descending order by the score that ranks the weight of each key phrase.</span></span> <span data-ttu-id="54d9b-124">Этот запрос вызывает функцию [semanticsimilaritydetailstable (Transact-SQL)](/sql/relational-databases/system-functions/semanticsimilaritydetailstable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="54d9b-124">This query calls the [semanticsimilaritydetailstable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritydetailstable-transact-sql) function.</span></span>  
  
```sql  
SET @SourceTitle = 'first.docx'  
SET @MatchedTitle = 'second.docx'  
  
SELECT @SourceDocID = DocumentID FROM Documents WHERE DocumentTitle = @SourceTitle  
SELECT @MatchedDocID = DocumentID FROM Documents WHERE DocumentTitle = @MatchedTitle  
  
SELECT @SourceTitle AS SourceTitle, @MatchedTitle AS MatchedTitle, keyphrase, score  
    FROM semanticsimilaritydetailstable(Documents, DocumentContent,  
        @SourceDocID, DocumentContent, @MatchedDocID)  
    ORDER BY score DESC  
  
```  
  
  
  
##  <a name="storing-documents-in-sql-server"></a><a name="store"></a><span data-ttu-id="54d9b-125">Хранение документов в SQL Server</span><span class="sxs-lookup"><span data-stu-id="54d9b-125">Storing Documents in SQL Server</span></span>  
 <span data-ttu-id="54d9b-126">Прежде чем индексировать документы с семантическим поиском, необходимо сохранить их в базе данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="54d9b-126">Before you can index documents with Semantic Search, you have to store the documents in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="54d9b-127">Функция FileTable в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] делает неструктурированные файлы и документы первоклассным содержимым реляционной базы данных.</span><span class="sxs-lookup"><span data-stu-id="54d9b-127">The FileTable feature in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] makes unstructured files and documents first-class citizens of the relational database.</span></span> <span data-ttu-id="54d9b-128">С их помощью разработчики баз данных могут управлять документами вместе со структурированными данными с использованием набора операций Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="54d9b-128">As a result, database developers can manipulate documents together with structured data in Transact-SQL set-based operations.</span></span>  
  
 <span data-ttu-id="54d9b-129">Дополнительные сведения о таблицах FileTable см. в разделе [Таблицы FileTable (SQL Server)](../blob/filetables-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="54d9b-129">For more information about the FileTable feature, see [FileTables &#40;SQL Server&#41;](../blob/filetables-sql-server.md).</span></span> <span data-ttu-id="54d9b-130">Дополнительные сведения о функции FILESTREAM, являющейся еще одним вариантом сохранения документов в базе данных, см. в разделе [FILESTREAM (SQL Server)](../blob/filestream-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="54d9b-130">For information about the FILESTREAM feature, which is another option for storing documents in the database, see [FILESTREAM &#40;SQL Server&#41;](../blob/filestream-sql-server.md).</span></span>  
  
  
  
##  <a name="related-tasks"></a><a name="reltasks"></a> <span data-ttu-id="54d9b-131">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="54d9b-131">Related Tasks</span></span>  
 [<span data-ttu-id="54d9b-132">Установка и настройка семантического поиска</span><span class="sxs-lookup"><span data-stu-id="54d9b-132">Install and Configure Semantic Search</span></span>](install-and-configure-semantic-search.md)  
 <span data-ttu-id="54d9b-133">Описывает компоненты, необходимые для статистического семантического поиска, и способы их установки и проверки.</span><span class="sxs-lookup"><span data-stu-id="54d9b-133">Describes the prerequisites for statistical semantic search and how to install or check them.</span></span>  
  
 [<span data-ttu-id="54d9b-134">Включение семантического поиска по таблицам и столбцам</span><span class="sxs-lookup"><span data-stu-id="54d9b-134">Enable Semantic Search on Tables and Columns</span></span>](enable-semantic-search-on-tables-and-columns.md)  
 <span data-ttu-id="54d9b-135">Описывает способ включения или отключения статистического семантического индексирования в выбранных столбцах, содержащих документы или текст.</span><span class="sxs-lookup"><span data-stu-id="54d9b-135">Describes how to enable or disable statistical semantic indexing on selected columns that contain documents or text.</span></span>  
  
 [<span data-ttu-id="54d9b-136">Поиск ключевых фраз в документах с помощью семантического поиска</span><span class="sxs-lookup"><span data-stu-id="54d9b-136">Find Key Phrases in Documents with Semantic Search</span></span>](find-key-phrases-in-documents-with-semantic-search.md)  
 <span data-ttu-id="54d9b-137">Описывает способ поиска ключевых фраз в документах или текстовых столбцах, настроенных для статистического семантического индексирования.</span><span class="sxs-lookup"><span data-stu-id="54d9b-137">Describes how to find the key phrases in documents or text columns that are configured for statistical semantic indexing.</span></span>  
  
 [<span data-ttu-id="54d9b-138">Поиск похожих и связанных документов с помощью семантического поиска</span><span class="sxs-lookup"><span data-stu-id="54d9b-138">Find Similar and Related Documents with Semantic Search</span></span>](find-similar-and-related-documents-with-semantic-search.md)  
 <span data-ttu-id="54d9b-139">Описывает процесс поиска схожих или связанных документов или текстовых значений и сведений об их сходстве или связи в столбцах, настроенных для статистического семантического индексирования.</span><span class="sxs-lookup"><span data-stu-id="54d9b-139">Describes how to find similar or related documents or text values, and information about how they are similar or related, in columns that are configured for statistical semantic indexing.</span></span>  
  
 [<span data-ttu-id="54d9b-140">Управление семантическим поиском и наблюдение за ним</span><span class="sxs-lookup"><span data-stu-id="54d9b-140">Manage and Monitor Semantic Search</span></span>](manage-and-monitor-semantic-search.md)  
 <span data-ttu-id="54d9b-141">Описывается процесс семантического индексирования и задачи, связанные с наблюдением за индексами и управлением ими.</span><span class="sxs-lookup"><span data-stu-id="54d9b-141">Describes the process of semantic indexing and the tasks related to monitoring and managing the indexes.</span></span>  
  
##  <a name="related-content"></a><a name="relcontent"></a> <span data-ttu-id="54d9b-142">См. также</span><span class="sxs-lookup"><span data-stu-id="54d9b-142">Related Content</span></span>  
 [<span data-ttu-id="54d9b-143">Инструкции DDL, функции, хранимые процедуры и представления для семантического поиска</span><span class="sxs-lookup"><span data-stu-id="54d9b-143">Semantic Search DDL, Functions, Stored Procedures, and Views</span></span>](../views/views.md)  
 <span data-ttu-id="54d9b-144">Содержит список инструкций Transact-SQL и объектов базы данных SQL Server, добавленных или измененных для поддержки статистического семантического поиска.</span><span class="sxs-lookup"><span data-stu-id="54d9b-144">Lists the Transact-SQL statements and the SQL Server database objects added or changed to support statistical semantic search.</span></span>  
  
  
