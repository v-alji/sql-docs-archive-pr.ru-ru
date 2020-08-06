---
title: Включение семантического поиска по таблицам и столбцам | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- semantic search [SQL Server], enabling
ms.assetid: 895d220c-6749-4954-9dd3-2ea4c6a321ff
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f11ba654f7cc34f521990e8c420d41885d3c55b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733813"
---
# <a name="enable-semantic-search-on-tables-and-columns"></a><span data-ttu-id="897f9-102">Включение семантического поиска на таблицы и столбцы</span><span class="sxs-lookup"><span data-stu-id="897f9-102">Enable Semantic Search on Tables and Columns</span></span>
  <span data-ttu-id="897f9-103">Описывает способ включения или отключения статистического семантического индексирования в выбранных столбцах, содержащих документы или текст.</span><span class="sxs-lookup"><span data-stu-id="897f9-103">Describes how to enable or disable statistical semantic indexing on selected columns that contain documents or text.</span></span>  
  
 <span data-ttu-id="897f9-104">При выполнении статистического семантического поиска используются индексы, полученные при полнотекстовом поиске, а также создаются дополнительные индексы.</span><span class="sxs-lookup"><span data-stu-id="897f9-104">Statistical Semantic Search uses the indexes that are created by Full-Text Search, and creates additional indexes.</span></span> <span data-ttu-id="897f9-105">Из-за этой зависимости от полнотекстового поиска приходится создавать при определении нового или изменении существующего полнотекстового индекса новый семантический индекс.</span><span class="sxs-lookup"><span data-stu-id="897f9-105">As a result of this dependency on full-text search, you create a new semantic index when you define a new full-text index, or when you alter an existing full-text index.</span></span> <span data-ttu-id="897f9-106">Вы можете создать новый семантический индекс с помощью инструкций [!INCLUDE[tsql](../../includes/tsql-md.md)] или с помощью мастера полнотекстового индексирования и других диалоговых окон среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], как описано в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="897f9-106">You can create a new semantic index by using [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, or by using the Full-Text Indexing Wizard and other dialog boxes in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], as described in this topic.</span></span>  
  
##  <a name="creating-a-semantic-index"></a><a name="BasicEnabling"></a><span data-ttu-id="897f9-107">Создание семантического индекса</span><span class="sxs-lookup"><span data-stu-id="897f9-107">Creating a Semantic Index</span></span>  
  
###  <a name="requirements-and-restrictions-for-creating-a-semantic-index"></a><a name="reqenable"></a><span data-ttu-id="897f9-108">Требования и ограничения для создания семантического индекса</span><span class="sxs-lookup"><span data-stu-id="897f9-108">Requirements and Restrictions for Creating a Semantic Index</span></span>  
  
-   <span data-ttu-id="897f9-109">Можно создать индекс для любых объектов базы данных, поддерживаемых для полнотекстового индексирования, включая таблицы и индексированные представления.</span><span class="sxs-lookup"><span data-stu-id="897f9-109">You can create an index on any of the database objects that are supported for full-text indexing, including tables and indexed views.</span></span>  
  
-   <span data-ttu-id="897f9-110">Прежде чем можно будет включить семантическое индексирование для определенных столбцов, должны быть выполнены следующие предварительные условия:</span><span class="sxs-lookup"><span data-stu-id="897f9-110">Before you can enable semantic indexing for specific columns, the following prerequisites must exist:</span></span>  
  
    -   <span data-ttu-id="897f9-111">Для базы данных должен существовать полнотекстовый каталог.</span><span class="sxs-lookup"><span data-stu-id="897f9-111">A full-text catalog must exist for the database.</span></span>  
  
    -   <span data-ttu-id="897f9-112">Таблица должна содержать полнотекстовый индекс.</span><span class="sxs-lookup"><span data-stu-id="897f9-112">The table must have a full-text index.</span></span>  
  
    -   <span data-ttu-id="897f9-113">Выбранные столбцы должны быть включены в полнотекстовый индекс.</span><span class="sxs-lookup"><span data-stu-id="897f9-113">The selected columns must participate in the full-text index.</span></span>  
  
     <span data-ttu-id="897f9-114">Можно создать и включить эти требования одновременно.</span><span class="sxs-lookup"><span data-stu-id="897f9-114">You can create and enable all these requirements at the same time.</span></span>  
  
-   <span data-ttu-id="897f9-115">Можно создать семантический индекс по столбцам с любым типом данных, поддерживаемым для полнотекстового индексирования.</span><span class="sxs-lookup"><span data-stu-id="897f9-115">You can create a semantic index on columns that have any of the data types that are supported for full-text indexing.</span></span> <span data-ttu-id="897f9-116">Дополнительные сведения см. в разделе [Создание полнотекстовых индексов и управление ими](create-and-manage-full-text-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="897f9-116">For more information, see [Create and Manage Full-Text Indexes](create-and-manage-full-text-indexes.md).</span></span>  
  
-   <span data-ttu-id="897f9-117">Для столбцов типа `varbinary(max)` можно указать любой тип документа, поддерживаемый для полнотекстового индексирования.</span><span class="sxs-lookup"><span data-stu-id="897f9-117">You can specify any document type that is supported for full-text indexing for `varbinary(max)` columns.</span></span> <span data-ttu-id="897f9-118">Дополнительные сведения см. в подразделе [Практическое руководство. Определение того, какие типы документов могут быть проиндексированы](#doctypes) этого раздела.</span><span class="sxs-lookup"><span data-stu-id="897f9-118">For more information, see [How To: Determine Which Document Types Can Be Indexed](#doctypes) in this topic.</span></span>  
  
-   <span data-ttu-id="897f9-119">При семантическом индексировании для выбранных столбцов создаются индексы двух типов — индекс ключевых фраз и индекс подобия документов.</span><span class="sxs-lookup"><span data-stu-id="897f9-119">Semantic indexing creates two types of indexes for the columns that you select - an index of key phrases, and an index of document similarity.</span></span> <span data-ttu-id="897f9-120">При включении семантического индексирования нельзя выбрать только один тип индекса из этих двух.</span><span class="sxs-lookup"><span data-stu-id="897f9-120">You cannot select only one type of index or the other when you enable semantic indexing.</span></span> <span data-ttu-id="897f9-121">Однако можно запрашивать эти индексы по отдельности.</span><span class="sxs-lookup"><span data-stu-id="897f9-121">However you can query these two indexes independently.</span></span> <span data-ttu-id="897f9-122">Дополнительные сведения см. в разделе [Поиск ключевых фраз в документах с использованием семантического поиска](find-key-phrases-in-documents-with-semantic-search.md) и [Поиск похожих и связанных документов с использованием семантического поиска](find-similar-and-related-documents-with-semantic-search.md).</span><span class="sxs-lookup"><span data-stu-id="897f9-122">For more information, see [Find Key Phrases in Documents with Semantic Search](find-key-phrases-in-documents-with-semantic-search.md) and [Find Similar and Related Documents with Semantic Search](find-similar-and-related-documents-with-semantic-search.md).</span></span>  
  
-   <span data-ttu-id="897f9-123">Если код языка для семантического индекса не указан явно, при семантическом индексировании будет использоваться только основной язык и связанная с ним статистика.</span><span class="sxs-lookup"><span data-stu-id="897f9-123">If you do not explicitly specify an LCID for a semantic index, then only the primary language and its associated language statistics are used for semantic indexing.</span></span>  
  
-   <span data-ttu-id="897f9-124">В случае указания языка для столбца, для которого недоступна языковая модель, создание индекса завершится ошибкой и будет возвращено соответствующее сообщение.</span><span class="sxs-lookup"><span data-stu-id="897f9-124">If you specify a language for a column for which the language model is not available, the creation of the index fails and returns an error message.</span></span>  
  
###  <a name="how-to-create-a-semantic-index-when-there-is-no-full-text-index"></a><a name="HowToEnableCreate"></a><span data-ttu-id="897f9-125">Как создать семантический индекс при отсутствии полнотекстового индекса</span><span class="sxs-lookup"><span data-stu-id="897f9-125">How To: Create a Semantic Index When There Is No Full-Text Index</span></span>  
 <span data-ttu-id="897f9-126">При создании нового полнотекстового индекса с помощью инструкции **CREATE FULLTEXT INDEX** семантическое индексирование на уровне столбца включается путем указания в определении столбца ключевого слова **STATISTICAL_SEMANTICS** .</span><span class="sxs-lookup"><span data-stu-id="897f9-126">When you create a new full-text index with the **CREATE FULLTEXT INDEX** statement, you can enable semantic indexing at the column level by specifying the keyword **STATISTICAL_SEMANTICS** as part of the column definition.</span></span> <span data-ttu-id="897f9-127">Семантическое индексирование также можно включить при создании полнотекстового индекса с помощью мастера полнотекстового индексирования.</span><span class="sxs-lookup"><span data-stu-id="897f9-127">You can also enable semantic indexing when you use the Full-Text Indexing Wizard to create a new full-text index.</span></span>  
  
 <span data-ttu-id="897f9-128">**Создание нового семантического индекса с помощью Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="897f9-128">**Create a new semantic index by using Transact-SQL**</span></span>  
 <span data-ttu-id="897f9-129">Вызовите инструкцию **CREATE FULLTEXT INDEX** и укажите параметр **STATISTICAL_SEMANTICS** для каждого столбца, на котором требуется создать семантический индекс.</span><span class="sxs-lookup"><span data-stu-id="897f9-129">Call the **CREATE FULLTEXT INDEX** statement and specify **STATISTICAL_SEMANTICS** for each column on which you want to create a semantic index.</span></span> <span data-ttu-id="897f9-130">Дополнительные сведения обо всех параметрах этой инструкции см. в разделе [CREATE FULLTEXT INDEX (Transact-SQL)](/sql/t-sql/statements/create-fulltext-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="897f9-130">For more information about all the options for this statement, see [CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql).</span></span>  
  
 <span data-ttu-id="897f9-131">**Пример 1. Создание уникального индекса, полнотекстового и семантического индекса**</span><span class="sxs-lookup"><span data-stu-id="897f9-131">**Example 1: Create a unique index, full-text index, and semantic index**</span></span>  
  
 <span data-ttu-id="897f9-132">В следующем примере создается полнотекстовый каталог по умолчанию **ft**. Затем в примере создается уникальный индекс на столбце **JobCandidateID** таблицы **HumanResources.JobCandidate** образца базы данных AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="897f9-132">The following example creates a default full-text catalog, **ft**. The example then creates a unique index on the **JobCandidateID** column of the **HumanResources.JobCandidate** table of the AdventureWorks2012 sample database.</span></span> <span data-ttu-id="897f9-133">Данный уникальный индекс используется в качестве ключевого столбца полнотекстового индекса.</span><span class="sxs-lookup"><span data-stu-id="897f9-133">This unique index is required as the key column for a full-text index.</span></span> <span data-ttu-id="897f9-134">Затем в примере создается полнотекстовый и семантический индексы на столбце **Resume** .</span><span class="sxs-lookup"><span data-stu-id="897f9-134">The example then creates a full-text index and a semantic index on the **Resume** column.</span></span>  
  
```sql  
CREATE FULLTEXT CATALOG ft AS DEFAULT  
GO  
  
CREATE UNIQUE INDEX ui_ukJobCand  
    ON HumanResources.JobCandidate(JobCandidateID)  
GO  
  
CREATE FULLTEXT INDEX ON HumanResources.JobCandidate  
    (Resume  
        Language 1033  
        Statistical_Semantics  
    )   
    KEY INDEX JobCandidateID   
    WITH STOPLIST = SYSTEM  
GO  
```  
  
 <span data-ttu-id="897f9-135">**Пример 2. Создание полнотекстового и семантического индексов на нескольких столбцах с отложенным заполнением**</span><span class="sxs-lookup"><span data-stu-id="897f9-135">**Example 2: Create a full-text and semantic index on several columns with delayed index population**</span></span>  
  
 <span data-ttu-id="897f9-136">В следующем примере в образце базы данных AdventureWorks2012 создается полнотекстовый каталог **documents_catalog**.</span><span class="sxs-lookup"><span data-stu-id="897f9-136">The following example creates a full-text catalog, **documents_catalog**, in the AdventureWorks2012 sample database.</span></span> <span data-ttu-id="897f9-137">Следующий пример создает полнотекстовый индекс, который использует этот новый каталог.</span><span class="sxs-lookup"><span data-stu-id="897f9-137">The example then creates a full-text index that uses this new catalog.</span></span> <span data-ttu-id="897f9-138">Полнотекстовый индекс создан на столбцах **Title**, **DocumentSummary**и **Document** таблицы **Production.Document** , а семантических индекс — только на столбце **Document** .</span><span class="sxs-lookup"><span data-stu-id="897f9-138">The full-text index is created on the **Title**, **DocumentSummary**, and **Document** columns of the **Production.Document** table, while the semantic index is only created on the **Document** column.</span></span> <span data-ttu-id="897f9-139">Этот полнотекстовый индекс использует вновь созданный полнотекстовый каталог и существующий индекс уникального ключа **PK_Document_DocumentID**.</span><span class="sxs-lookup"><span data-stu-id="897f9-139">This full-text index uses the newly-created full-text catalog and an existing unique key index, **PK_Document_DocumentID**.</span></span> <span data-ttu-id="897f9-140">Согласно рекомендациям этот ключ индекса построен на целочисленном столбце **DocumentID**.</span><span class="sxs-lookup"><span data-stu-id="897f9-140">As recommended, this index key is created on an integer column, **DocumentID**.</span></span> <span data-ttu-id="897f9-141">В примере указан код (LCID) для английского языка 1033, который является языком данных в столбцах.</span><span class="sxs-lookup"><span data-stu-id="897f9-141">The example specifies the LCID for English, 1033, which is the language of the data in the columns.</span></span>  
  
 <span data-ttu-id="897f9-142">В примере также указано, что отслеживание изменений отключено (без заполнения).</span><span class="sxs-lookup"><span data-stu-id="897f9-142">This example also specifies that change tracking is off with no population.</span></span> <span data-ttu-id="897f9-143">Позже, в часы с наименьшей загрузкой, будет запущено полное заполнение нового индекса и включено автоматическое отслеживание изменений с помощью инструкции **ALTER FULLTEXT INDEX** .</span><span class="sxs-lookup"><span data-stu-id="897f9-143">Later, during off-peak hours, the example uses an **ALTER FULLTEXT INDEX** statement to start a full population on the new index and enable automatic change tracking.</span></span>  
  
```sql  
CREATE FULLTEXT CATALOG documents_catalog  
GO  
  
CREATE FULLTEXT INDEX ON Production.Document  
    (   
    Title  
        Language 1033,   
    DocumentSummary  
        Language 1033,   
    Document   
        TYPE COLUMN FileExtension  
        Language 1033  
        Statistical_Semantics  
    )  
    KEY INDEX PK_Document_DocumentID  
        ON documents_catalog  
        WITH CHANGE_TRACKING OFF, NO POPULATION  
GO  
```  
  
 <span data-ttu-id="897f9-144">Позже, в часы с наименьшей загрузкой, выполняется заполнение индекса:</span><span class="sxs-lookup"><span data-stu-id="897f9-144">Later, at an off-peak time, the index is populated:</span></span>  
  
```sql  
ALTER FULLTEXT INDEX ON Production.Document SET CHANGE_TRACKING AUTO  
GO  
```  
  
 <span data-ttu-id="897f9-145">**Создание нового семантического индекса с помощью среды SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="897f9-145">**Create a new semantic index by using SQL Server Management Studio**</span></span>  
 <span data-ttu-id="897f9-146">Запустите мастер полнотекстового индексирования и включите параметр **Статистическая семантика** на странице **Выбор столбцов таблицы** для каждого столбца, на котором требуется создать семантический индекс.</span><span class="sxs-lookup"><span data-stu-id="897f9-146">Run the Full-Text Indexing Wizard and enable **Statistical Semantics** on the **Select Table Columns** page for each column on which you want to create a semantic index.</span></span> <span data-ttu-id="897f9-147">Дополнительные сведения, в том числе о запуске мастера полнотекстового индексирования, см. в разделе [Использование мастера полнотекстового индексирования](use-the-full-text-indexing-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="897f9-147">For more information, including information about how to start the Full-Text Indexing Wizard, see [Use the Full-Text Indexing Wizard](use-the-full-text-indexing-wizard.md).</span></span>  
  
###  <a name="how-to-create-a-semantic-index-when-there-is-an-existing-full-text-index"></a><a name="HowToEnableAlter"></a><span data-ttu-id="897f9-148">Пошаговое руководство. Создание семантического индекса при наличии существующего полнотекстового индекса</span><span class="sxs-lookup"><span data-stu-id="897f9-148">How To: Create a Semantic Index When There Is an Existing Full-Text Index</span></span>  
 <span data-ttu-id="897f9-149">Для добавления семантического индексирования при изменении существующего полнотекстового индекса используется инструкция **ALTER FULLTEXT INDEX** .</span><span class="sxs-lookup"><span data-stu-id="897f9-149">You can add semantic indexing when you alter an existing full-text index with the **ALTER FULLTEXT INDEX** statement.</span></span> <span data-ttu-id="897f9-150">Также можно добавить семантическое индексирование с помощью различных диалоговых окон в [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="897f9-150">You can also add semantic indexing by using various dialog boxes in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="897f9-151">**Добавление семантического индекса с помощью Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="897f9-151">**Add a semantic index by using Transact-SQL**</span></span>  
 <span data-ttu-id="897f9-152">Вызовите инструкцию **ALTER FULLTEXT INDEX** с описанными далее параметрами для каждого столбца, для которого требуется добавить семантический индекс.</span><span class="sxs-lookup"><span data-stu-id="897f9-152">Call the **ALTER FULLTEXT INDEX** statement with the options described below for each column on which you want to add a semantic index.</span></span> <span data-ttu-id="897f9-153">Дополнительные сведения обо всех параметрах этой инструкции см. в разделе [ALTER FULLTEXT INDEX (Transact-SQL)](/sql/t-sql/statements/alter-fulltext-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="897f9-153">For more information about all the options for this statement, see [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql).</span></span>  
  
 <span data-ttu-id="897f9-154">Если не указано иное, полнотекстовый и семантический индексы после вызова инструкции **ALTER** повторно заполняются.</span><span class="sxs-lookup"><span data-stu-id="897f9-154">Both full-text and semantic indexes are repopulated after a call to **ALTER**, unless you specify otherwise.</span></span>  
  
-   <span data-ttu-id="897f9-155">Чтобы добавить в столбец только полнотекстовое индексирование, используйте синтаксис **ADD** .</span><span class="sxs-lookup"><span data-stu-id="897f9-155">To add full-text indexing only to a column, use the **ADD** syntax.</span></span>  
  
-   <span data-ttu-id="897f9-156">Чтобы добавить в столбец и полнотекстовое и семантическое индексирование, используйте синтаксис **ADD** с параметром **STATISTICAL_SEMANTICS** .</span><span class="sxs-lookup"><span data-stu-id="897f9-156">To add both full-text and semantic indexing to a column, use the **ADD** syntax with the **STATISTICAL_SEMANTICS** option.</span></span>  
  
-   <span data-ttu-id="897f9-157">Чтобы добавить семантическое индексирование в столбец, для которого уже включено полнотекстовое индексирование, укажите параметр **ADD STATISTICAL_SEMANTICS** .</span><span class="sxs-lookup"><span data-stu-id="897f9-157">To add semantic indexing to a column that is already enabled for full-text indexing, use the **ADD STATISTICAL_SEMANTICS** option.</span></span> <span data-ttu-id="897f9-158">В рамках одной инструкции **ALTER** семантический индекс можно добавить только в один столбец.</span><span class="sxs-lookup"><span data-stu-id="897f9-158">You can only add semantic indexing to one column in a single **ALTER** statement.</span></span>  
  
 <span data-ttu-id="897f9-159">**Пример. Добавление семантического индексирования в столбец, в котором уже есть полнотекстовое индексирование**</span><span class="sxs-lookup"><span data-stu-id="897f9-159">**Example: Add semantic indexing to a column that already has full-text indexing**</span></span>  
  
 <span data-ttu-id="897f9-160">В следующем примере выполняется изменение существующего полнотекстового индекса в таблице **Production.Document** из образца базы данных AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="897f9-160">The following example alters an existing full-text index on **Production.Document** table in AdventureWorks2012 sample database.</span></span> <span data-ttu-id="897f9-161">Пример добавляет семантический индекс для столбца **Document** таблицы **Production.Document** , для которого уже существует полнотекстовый индекс.</span><span class="sxs-lookup"><span data-stu-id="897f9-161">The example adds a semantic index on the **Document** column of the **Production.Document** table, which already has a full-text index.</span></span> <span data-ttu-id="897f9-162">В примере указывается, что повторное заполнение индекса не будет выполняться автоматически.</span><span class="sxs-lookup"><span data-stu-id="897f9-162">The example specifies that the index will not be repopulated automatically.</span></span>  
  
```sql  
ALTER FULLTEXT INDEX ON Production.Document  
    ALTER COLUMN Document  
        ADD Statistical_Semantics  
    WITH NO POPULATION  
GO  
```  
  
 <span data-ttu-id="897f9-163">**Добавить семантический индекс с помощью среды SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="897f9-163">**Add a semantic index by using SQL Server Management Studio**</span></span>  
 <span data-ttu-id="897f9-164">Изменение столбцов, для которых включен семантический или полнотекстовый индекс, выполняется на странице **Столбцы полнотекстового индекса** диалогового окна **Свойства полнотекстового индекса** .</span><span class="sxs-lookup"><span data-stu-id="897f9-164">You can change the columns that are enabled for semantic and full-text indexing on the **Full-Text Index Columns** page of the **Full-Text Index Properties** dialog box.</span></span> <span data-ttu-id="897f9-165">Дополнительные сведения см. в разделе [Управление полнотекстовыми индексами](../../database-engine/manage-full-text-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="897f9-165">For more information, see [Manage Full-Text Indexes](../../database-engine/manage-full-text-indexes.md).</span></span>  
  
###  <a name="requirements-and-restrictions-for-altering-an-existing-index"></a><a name="addreq"></a><span data-ttu-id="897f9-166">Требования и ограничения для изменения существующего индекса</span><span class="sxs-lookup"><span data-stu-id="897f9-166">Requirements and Restrictions for Altering an Existing Index</span></span>  
  
-   <span data-ttu-id="897f9-167">В процессе заполнения индекса изменять существующий индекс нельзя.</span><span class="sxs-lookup"><span data-stu-id="897f9-167">You cannot alter an existing index while population of the index is in progress.</span></span> <span data-ttu-id="897f9-168">Дополнительные сведения о наблюдении за ходом заполнения индекса см. в разделе [Мониторинг семантического поиска и управление им](manage-and-monitor-semantic-search.md).</span><span class="sxs-lookup"><span data-stu-id="897f9-168">For more information on monitoring the progress of index population, see [Manage and Monitor Semantic Search](manage-and-monitor-semantic-search.md).</span></span>  
  
-   <span data-ttu-id="897f9-169">Нельзя добавить индексирование в столбец и изменить или удалить индексирование из этого же столбца в рамках одного вызова инструкции **ALTER FULLTEXT INDEX** .</span><span class="sxs-lookup"><span data-stu-id="897f9-169">You cannot add indexing to a column, and alter or drop indexing for the same column, in a single call to the **ALTER FULLTEXT INDEX** statement.</span></span>  
  
##  <a name="dropping-a-semantic-index"></a><a name="dropping"></a><span data-ttu-id="897f9-170">Удаление семантического индекса</span><span class="sxs-lookup"><span data-stu-id="897f9-170">Dropping a Semantic Index</span></span>  
  
###  <a name="how-to-drop-a-semantic-index"></a><a name="drophow"></a><span data-ttu-id="897f9-171">Как удалить семантический индекс</span><span class="sxs-lookup"><span data-stu-id="897f9-171">How to: Drop a Semantic Index</span></span>  
 <span data-ttu-id="897f9-172">Для удаления семантического индексирования при изменении существующего полнотекстового индекса используется инструкция **ALTER FULLTEXT INDEX** .</span><span class="sxs-lookup"><span data-stu-id="897f9-172">You can drop semantic indexing when you alter an existing full-text index with the **ALTER FULLTEXT INDEX** statement.</span></span> <span data-ttu-id="897f9-173">Также можно удалить семантическое индексирование с помощью различных диалоговых окон в [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="897f9-173">You can also drop semantic indexing by using various dialog boxes in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="897f9-174">**Удалите семантический индекс с помощью Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="897f9-174">**Drop a semantic index by using Transact-SQL**</span></span>  
 -   <span data-ttu-id="897f9-175">Для удаления семантического индексирования только из столбца или столбцов вызовите инструкцию **ALTER FULLTEXT INDEX** с параметром **ALTER COLUMN***column_name***DROP STATISTICAL_SEMANTICS** .</span><span class="sxs-lookup"><span data-stu-id="897f9-175">To drop semantic indexing only from a column or columns, call the **ALTER FULLTEXT INDEX** statement with the **ALTER COLUMN***column_name***DROP STATISTICAL_SEMANTICS** option.</span></span> <span data-ttu-id="897f9-176">С помощью одной инструкции **ALTER** можно удалить индексирование из нескольких столбцов.</span><span class="sxs-lookup"><span data-stu-id="897f9-176">You can drop the indexing from multiple columns in a single **ALTER** statement.</span></span>  
  
    ```sql  
    USE database_name  
    GO  
  
    ALTER FULLTEXT INDEX  
        ALTER COLUMN column_name  
        DROP STATISTICAL_SEMANTICS  
    GO  
    ```  
  
-   <span data-ttu-id="897f9-177">Чтобы удалить как полнотекстовое, так и семантическое индексирование из столбца, вызовите инструкцию **ALTER FULLTEXT INDEX** с параметром **ALTER COLUMN***column_name***Drop** .</span><span class="sxs-lookup"><span data-stu-id="897f9-177">To drop both full-text and semantic indexing from a column, call the **ALTER FULLTEXT INDEX** statement with the **ALTER COLUMN***column_name***DROP** option.</span></span>  
  
    ```sql  
    USE database_name  
    GO  
  
    ALTER FULLTEXT INDEX  
        ALTER COLUMN column_name  
        DROP  
    GO  
    ```  
  
 <span data-ttu-id="897f9-178">**Удалите семантический индекс с помощью среды SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="897f9-178">**Drop a semantic index by using SQL Server Management Studio**</span></span>  
 <span data-ttu-id="897f9-179">Изменение столбцов, для которых включен семантический или полнотекстовый индекс, выполняется на странице **Столбцы полнотекстового индекса** диалогового окна **Свойства полнотекстового индекса** .</span><span class="sxs-lookup"><span data-stu-id="897f9-179">You can change the columns that are enabled for semantic and full-text indexing on the **Full-Text Index Columns** page of the **Full-Text Index Properties** dialog box.</span></span> <span data-ttu-id="897f9-180">Дополнительные сведения см. в разделе [Управление полнотекстовыми индексами](../../database-engine/manage-full-text-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="897f9-180">For more information, see [Manage Full-Text Indexes](../../database-engine/manage-full-text-indexes.md).</span></span>  
  
###  <a name="requirements-and-restrictions-for-dropping-a-semantic-index"></a><a name="dropreq"></a><span data-ttu-id="897f9-181">Требования и ограничения для удаления семантического индекса</span><span class="sxs-lookup"><span data-stu-id="897f9-181">Requirements and Restrictions for Dropping a Semantic Index</span></span>  
  
-   <span data-ttu-id="897f9-182">Удалить полнотекстовое индексирование из столбца, сохранив при этом семантическое индексирование, невозможно.</span><span class="sxs-lookup"><span data-stu-id="897f9-182">You cannot drop full-text indexing from a column while retaining semantic indexing.</span></span> <span data-ttu-id="897f9-183">Для получения результатов о подобии документов семантическое индексирование основывается на полнотекстовом индексировании.</span><span class="sxs-lookup"><span data-stu-id="897f9-183">Semantic indexing depends on full-text indexing for document similarity results.</span></span>  
  
-   <span data-ttu-id="897f9-184">Задать параметр **NO POPULATION** при удалении семантического индексирования из последнего столбца таблицы, для которой было включено семантическое индексирование, невозможно.</span><span class="sxs-lookup"><span data-stu-id="897f9-184">You cannot specify the **NO POPULATION** option when you drop semantic indexing from the last column in a table for which semantic indexing was enabled.</span></span> <span data-ttu-id="897f9-185">Для удаления ранее индексированных результатов требуется цикл заполнения.</span><span class="sxs-lookup"><span data-stu-id="897f9-185">A population cycle is required to remove the results that were indexed previously.</span></span>  
  
## <a name="checking-whether-semantic-search-is-enabled-on-database-objects"></a><span data-ttu-id="897f9-186">Проверка включения семантического поиска по объектам базы данных</span><span class="sxs-lookup"><span data-stu-id="897f9-186">Checking Whether Semantic Search Is Enabled on Database Objects</span></span>  
  
###  <a name="how-to-check-whether-semantic-search-is-enabled-on-database-objects"></a><a name="HowToCheckEnabled"></a><span data-ttu-id="897f9-187">Как проверить, включен ли семантический поиск для объектов базы данных</span><span class="sxs-lookup"><span data-stu-id="897f9-187">How To: Check Whether Semantic Search Is Enabled on Database Objects</span></span>  
 <span data-ttu-id="897f9-188">**Включен ли семантический поиск для базы данных?**</span><span class="sxs-lookup"><span data-stu-id="897f9-188">**Is semantic search enabled for a database?**</span></span>  
 <span data-ttu-id="897f9-189">Отправьте запрос к свойству **IsFullTextEnabled** функции метаданных [SERVERPROPERTY (Transact-SQL)](/sql/t-sql/functions/databasepropertyex-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="897f9-189">Query the **IsFullTextEnabled** property of the [DATABASEPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/databasepropertyex-transact-sql) metadata function.</span></span>  
  
 <span data-ttu-id="897f9-190">Возвращаемое значение 1 указывает, что полнотекстовый поиск и семантический поиск для базы данных включены; возвращаемое значение 0 указывает, что они не включены.</span><span class="sxs-lookup"><span data-stu-id="897f9-190">A return value of 1 indicates that full-text search and semantic search are enabled for the database; a return value of 0 indicates that they are not enabled.</span></span>  
  
```sql  
SELECT DATABASEPROPERTYEX('database_name', 'IsFullTextEnabled')  
GO  
```  
  
 <span data-ttu-id="897f9-191">**Включен ли семантический поиск для таблицы?**</span><span class="sxs-lookup"><span data-stu-id="897f9-191">**Is semantic search enabled for a table?**</span></span>  
 <span data-ttu-id="897f9-192">Выполните запрос к свойству **TableFullTextSemanticExtraction** функции метаданных [OBJECTPROPERTYEX (Transact-SQL)](/sql/t-sql/functions/objectproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="897f9-192">Query the **TableFullTextSemanticExtraction** property of the [OBJECTPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectproperty-transact-sql) metadata function.</span></span>  
  
 <span data-ttu-id="897f9-193">Возвращаемое значение 1 указывает, что семантический поиск для таблицы включен; возвращаемое значение 0 указывает, что он не включен.</span><span class="sxs-lookup"><span data-stu-id="897f9-193">A return value of 1 indicates that semantic search is enabled for the table; a return value of 0 indicates that it is not enabled.</span></span>  
  
```scr  
SELECT OBJECTPROPERTYEX(OBJECT_ID('table_name'), 'TableFullTextSemanticExtraction')  
GO  
```  
  
 <span data-ttu-id="897f9-194">**Включен ли семантический поиск для столбца?**</span><span class="sxs-lookup"><span data-stu-id="897f9-194">**Is semantic search enabled for a column?**</span></span>  
 <span data-ttu-id="897f9-195">Чтобы определить, включен ли семантический поиск для определенного столбца, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="897f9-195">To determine whether semantic search is enabled for a specific column:</span></span>  
  
-   <span data-ttu-id="897f9-196">Выполните запрос к свойству **StatisticalSemantics** функции метаданных [COLUMNPROPERTY (Transact-SQL)](/sql/t-sql/functions/columnproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="897f9-196">Query the **StatisticalSemantics** property of the [COLUMNPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/columnproperty-transact-sql) metadata function.</span></span>  
  
     <span data-ttu-id="897f9-197">Возвращаемое значение 1 указывает, что семантический поиск для столбца включен; возвращаемое значение 0 указывает, что он не включен.</span><span class="sxs-lookup"><span data-stu-id="897f9-197">A return value of 1 indicates that semantic search is enabled for the column; a return value of 0 indicates that it is not enabled.</span></span>  
  
    ```sql  
    SELECT COLUMNPROPERTY(OBJECT_ID('table_name'), 'column_name', 'StatisticalSemantics')  
    GO  
    ```  
  
-   <span data-ttu-id="897f9-198">Запрос к представлению каталога [sys.fulltext_index_columns (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-fulltext-index-columns-transact-sql) для полнотекстового индекса.</span><span class="sxs-lookup"><span data-stu-id="897f9-198">Query the catalog view [sys.fulltext_index_columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-index-columns-transact-sql) for the full-text index.</span></span>  
  
     <span data-ttu-id="897f9-199">Значение 1 в столбце **statistical_semantics** указывает, что для данного столбца, кроме полнотекстового индексирования, включено и семантическое индексирование.</span><span class="sxs-lookup"><span data-stu-id="897f9-199">A value of 1 in the **statistical_semantics** column indicates that the specified column is enabled for semantic indexing in addition to full-text indexing.</span></span>  
  
    ```sql  
    SELECT * FROM sys.fulltext_index_columns WHERE object_id = OBJECT_ID('table_name')  
    GO  
    ```  
  
-   <span data-ttu-id="897f9-200">В обозревателе объектов [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]щелкните правой кнопкой мыши столбец и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="897f9-200">In Object Explorer in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], right-click on a column and select **Properties**.</span></span> <span data-ttu-id="897f9-201">На странице **Общие** диалогового окна **Свойства столбца** проверьте значение свойства **Статистическая семантика** .</span><span class="sxs-lookup"><span data-stu-id="897f9-201">On the **General** page of the **Column Properties** dialog box, check the value of the **Statistical Semantics** property.</span></span>  
  
     <span data-ttu-id="897f9-202">Значение True указывает, что для данного столбца, кроме полнотекстового индексирования, включено и семантическое индексирование.</span><span class="sxs-lookup"><span data-stu-id="897f9-202">A value of True indicates that the specified column is enabled for semantic indexing in addition to full-text indexing.</span></span>  
  
## <a name="determining-what-can-be-indexed-for-semantic-search"></a><span data-ttu-id="897f9-203">Определение возможности индексирования для семантического поиска</span><span class="sxs-lookup"><span data-stu-id="897f9-203">Determining What Can Be Indexed for Semantic Search</span></span>  
  
###  <a name="how-to-check-which-languages-are-supported-for-semantic-search"></a><a name="HowToCheckLanguages"></a><span data-ttu-id="897f9-204">Как проверить, какие языки поддерживаются для семантического поиска</span><span class="sxs-lookup"><span data-stu-id="897f9-204">How To: Check Which Languages Are Supported for Semantic Search</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="897f9-205">Для семантического индексирования поддерживается меньше языков, чем для полнотекстового индексирования.</span><span class="sxs-lookup"><span data-stu-id="897f9-205">Fewer languages are supported for semantic indexing than for full-text indexing.</span></span> <span data-ttu-id="897f9-206">В результате могут существовать столбцы, индексируемые для полнотекстового поиска, но не для семантического поиска.</span><span class="sxs-lookup"><span data-stu-id="897f9-206">As a result, there may be columns that you can index for full-text search, but not for semantic search.</span></span>  
  
 <span data-ttu-id="897f9-207">Отправьте запрос в представление каталога [sys.fulltext_semantic_languages (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-fulltext-semantic-languages-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="897f9-207">Query the catalog view [sys.fulltext_semantic_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-semantic-languages-transact-sql).</span></span>  
  
```sql  
SELECT * FROM sys.fulltext_semantic_languages  
GO  
```  
  
 <span data-ttu-id="897f9-208">Для семантического индексирования поддерживаются следующие языки.</span><span class="sxs-lookup"><span data-stu-id="897f9-208">The following languages are supported for semantic indexing.</span></span> <span data-ttu-id="897f9-209">Этот список представляет выходные данные представления каталога [sys.fulltext_semantic_languages (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-fulltext-semantic-languages-transact-sql), упорядоченные по LCID.</span><span class="sxs-lookup"><span data-stu-id="897f9-209">This list represents the output of the catalog view [sys.fulltext_semantic_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-semantic-languages-transact-sql), ordered by LCID.</span></span>  
  
|<span data-ttu-id="897f9-210">Язык</span><span class="sxs-lookup"><span data-stu-id="897f9-210">Language</span></span>|<span data-ttu-id="897f9-211">LCID</span><span class="sxs-lookup"><span data-stu-id="897f9-211">LCID</span></span>|  
|--------------|----------|  
|<span data-ttu-id="897f9-212">Немецкий</span><span class="sxs-lookup"><span data-stu-id="897f9-212">German</span></span>|<span data-ttu-id="897f9-213">1031</span><span class="sxs-lookup"><span data-stu-id="897f9-213">1031</span></span>|  
|<span data-ttu-id="897f9-214">Английский (США)</span><span class="sxs-lookup"><span data-stu-id="897f9-214">English (US)</span></span>|<span data-ttu-id="897f9-215">1033</span><span class="sxs-lookup"><span data-stu-id="897f9-215">1033</span></span>|  
|<span data-ttu-id="897f9-216">Французский</span><span class="sxs-lookup"><span data-stu-id="897f9-216">French</span></span>|<span data-ttu-id="897f9-217">1036</span><span class="sxs-lookup"><span data-stu-id="897f9-217">1036</span></span>|  
|<span data-ttu-id="897f9-218">Итальянский</span><span class="sxs-lookup"><span data-stu-id="897f9-218">Italian</span></span>|<span data-ttu-id="897f9-219">1040</span><span class="sxs-lookup"><span data-stu-id="897f9-219">1040</span></span>|  
|<span data-ttu-id="897f9-220">Португальский (Бразилия)</span><span class="sxs-lookup"><span data-stu-id="897f9-220">Portuguese (Brazil)</span></span>|<span data-ttu-id="897f9-221">1046</span><span class="sxs-lookup"><span data-stu-id="897f9-221">1046</span></span>|  
|<span data-ttu-id="897f9-222">Русский</span><span class="sxs-lookup"><span data-stu-id="897f9-222">Russian</span></span>|<span data-ttu-id="897f9-223">1049</span><span class="sxs-lookup"><span data-stu-id="897f9-223">1049</span></span>|  
|<span data-ttu-id="897f9-224">Шведский</span><span class="sxs-lookup"><span data-stu-id="897f9-224">Swedish</span></span>|<span data-ttu-id="897f9-225">1053</span><span class="sxs-lookup"><span data-stu-id="897f9-225">1053</span></span>|  
|<span data-ttu-id="897f9-226">Английский (Великобритания)</span><span class="sxs-lookup"><span data-stu-id="897f9-226">English (UK)</span></span>|<span data-ttu-id="897f9-227">2057</span><span class="sxs-lookup"><span data-stu-id="897f9-227">2057</span></span>|  
|<span data-ttu-id="897f9-228">Португальский (Португалия)</span><span class="sxs-lookup"><span data-stu-id="897f9-228">Portuguese (Portugal)</span></span>|<span data-ttu-id="897f9-229">2070</span><span class="sxs-lookup"><span data-stu-id="897f9-229">2070</span></span>|  
|<span data-ttu-id="897f9-230">Испанский</span><span class="sxs-lookup"><span data-stu-id="897f9-230">Spanish</span></span>|<span data-ttu-id="897f9-231">3082</span><span class="sxs-lookup"><span data-stu-id="897f9-231">3082</span></span>|  
  
###  <a name="how-to-determine-which-document-types-can-be-indexed"></a><a name="doctypes"></a><span data-ttu-id="897f9-232">Как определить, какие типы документов можно индексировать</span><span class="sxs-lookup"><span data-stu-id="897f9-232">How To: Determine Which Document Types Can Be Indexed</span></span>  
 <span data-ttu-id="897f9-233">Отправьте запрос в представление каталога [sys.fulltext_document_types (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-fulltext-document-types-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="897f9-233">Query the catalog view [sys.fulltext_document_types &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-document-types-transact-sql).</span></span>  
  
 <span data-ttu-id="897f9-234">Если тип документа, который необходимо проиндексировать, отсутствует в списке поддерживаемых типов, то может потребоваться поиск, загрузка и установка дополнительных фильтров.</span><span class="sxs-lookup"><span data-stu-id="897f9-234">If the document type that you want to index is not in the list of supported types, then you may have to locate, download, and install additional filters.</span></span> <span data-ttu-id="897f9-235">Дополнительные сведения см. в статье [Просмотр или изменение зарегистрированных фильтры и разделители слов](view-or-change-registered-filters-and-word-breakers.md).</span><span class="sxs-lookup"><span data-stu-id="897f9-235">For more information, see [View or Change Registered Filters and Word Breakers](view-or-change-registered-filters-and-word-breakers.md).</span></span>  
  
##  <a name="best-practice-consider-creating-a-separate-filegroup-for-the-full-text-and-semantic-indexes"></a><a name="BestPracticeFilegroup"></a><span data-ttu-id="897f9-236">Рекомендация. Рассмотрите возможность создания отдельной файловой группы для полнотекстовых и семантических индексов</span><span class="sxs-lookup"><span data-stu-id="897f9-236">Best Practice: Consider Creating a Separate Filegroup for the Full-Text and Semantic Indexes</span></span>  
 <span data-ttu-id="897f9-237">Если выделение места на диске является серьезной проблемой, рассмотрите возможность создания отдельных файловых групп для полнотекстового и семантического индексов.</span><span class="sxs-lookup"><span data-stu-id="897f9-237">Consider creating a separate filegroup for the full-text and semantic indexes if disk space allocation is a concern.</span></span> <span data-ttu-id="897f9-238">Семантические индексы создаются в той же файловой группе, что и полнотекстовый индекс.</span><span class="sxs-lookup"><span data-stu-id="897f9-238">The semantic indexes are created in the same filegroup as the full-text index.</span></span> <span data-ttu-id="897f9-239">Полностью заполненный семантический индекс может содержать большой объем данных.</span><span class="sxs-lookup"><span data-stu-id="897f9-239">A fully populated semantic index may contain large amount of data.</span></span>  
  
##  <a name="BestPracticeUnderstand"></a>   
##  <a name="problem-searching-on-specific-column-returns-no-results"></a><a name="IssueNoResults"></a><span data-ttu-id="897f9-240">Проблема. Поиск в определенном столбце не возвращает результатов</span><span class="sxs-lookup"><span data-stu-id="897f9-240">Problem: Searching on Specific Column Returns No Results</span></span>  
 <span data-ttu-id="897f9-241">**Возможно, для языка в Юникоде был указан код языка не в Юникоде.**</span><span class="sxs-lookup"><span data-stu-id="897f9-241">**Was a non-Unicode LCID specified for a Unicode language?**</span></span>  
 <span data-ttu-id="897f9-242">Имеется возможность включить семантическое индексирование на столбцах не в Юникоде с помощью кода языка, содержащего только слова в Юникоде, например кода 1049, обозначающего русский язык.</span><span class="sxs-lookup"><span data-stu-id="897f9-242">It is possible to enable semantic indexing on a non-Unicode column type with an LCID for a language that only has Unicode words, such as LCID 1049 for Russian.</span></span> <span data-ttu-id="897f9-243">В этом случае семантические индексы на этом столбце никогда не возвратят каких-либо результатов.</span><span class="sxs-lookup"><span data-stu-id="897f9-243">In this case, no results will ever be returned from the semantic indexes on this column.</span></span>  
  
  
