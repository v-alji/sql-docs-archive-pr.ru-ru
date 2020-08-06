---
title: Настройка стоп-слов и списков стоп-слов для полнотекстового поиска и управление ими | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- stoplists [full-text search]
- full-text search [SQL Server], stoplists
- full-text search [SQL Server], noise words
- noise words [full-text search]
- full-text search [SQL Server], stopwords
- stopwords [full-text search]
ms.assetid: 43b5ce7b-9f09-4443-8a5b-c3da6eb28bcc
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 103b5024368c5ca239856580e9b45473aabf6a92
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750647"
---
# <a name="configure-and-manage-stopwords-and-stoplists-for-full-text-search"></a><span data-ttu-id="6ae0a-102">Настройка и управление стоп-словами и списками стоп-слов для полнотекстового поиска</span><span class="sxs-lookup"><span data-stu-id="6ae0a-102">Configure and Manage Stopwords and Stoplists for Full-Text Search</span></span>
  <span data-ttu-id="6ae0a-103">Чтобы предотвратить чрезмерное увеличение полнотекстового индекса, в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] реализован механизм, отбрасывающий часто встречающиеся строки, не повышающие эффективность поиска.</span><span class="sxs-lookup"><span data-stu-id="6ae0a-103">To prevent a full-text index from becoming bloated, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has a mechanism that discards commonly occurring strings that do not help the search.</span></span> <span data-ttu-id="6ae0a-104">Эти отброшенные строки называются *стоп-словами*.</span><span class="sxs-lookup"><span data-stu-id="6ae0a-104">These discarded strings are called *stopwords*.</span></span> <span data-ttu-id="6ae0a-105">Во время создания индекса средство полнотекстового поиска не включает стоп-слова в полнотекстовый индекс.</span><span class="sxs-lookup"><span data-stu-id="6ae0a-105">During index creation, the Full-Text Engine omits stopwords from the full-text index.</span></span> <span data-ttu-id="6ae0a-106">Это значит, что полнотекстовые запросы не будут выполнять поиск по стоп-словам.</span><span class="sxs-lookup"><span data-stu-id="6ae0a-106">This means that full-text queries will not search on stopwords.</span></span>  
  
##  <a name="understanding-stopwords-and-stoplists"></a><a name="understand"></a><span data-ttu-id="6ae0a-107">Основные сведения о стоп-слова и списков</span><span class="sxs-lookup"><span data-stu-id="6ae0a-107">Understanding Stopwords and Stoplists</span></span>  
 <span data-ttu-id="6ae0a-108">Стоп-слово может быть словом конкретного языка или *токеном* , не имеющим лингвистического значения.</span><span class="sxs-lookup"><span data-stu-id="6ae0a-108">A stopword can be a word with meaning in a specific language, or it can be a *token* that does not have linguistic meaning.</span></span> <span data-ttu-id="6ae0a-109">Например, в английском языке такие слова, как «a», «and», «is» и «the», не включаются в полнотекстовый индекс, потому что при поиске они бесполезны.</span><span class="sxs-lookup"><span data-stu-id="6ae0a-109">For example, in the English language, words such as "a," "and," "is," and "the" are left out of the full-text index since they are known to be useless to a search.</span></span>  
  
 <span data-ttu-id="6ae0a-110">Хотя стоп-слова при поиске не учитываются, полнотекстовый индекс принимает во внимание расположение таких слов.</span><span class="sxs-lookup"><span data-stu-id="6ae0a-110">Although it ignores the inclusion of stopwords, the full-text index does take into account their position.</span></span> <span data-ttu-id="6ae0a-111">Рассмотрим для примера фразу «Instructions are applicable to these Adventure Works Cycles models».</span><span class="sxs-lookup"><span data-stu-id="6ae0a-111">For example, consider the phrase, "Instructions are applicable to these Adventure Works Cycles models".</span></span> <span data-ttu-id="6ae0a-112">Позиции слов в этой фразе приведены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="6ae0a-112">The following table depicts the position of the words in the phrase:</span></span>  
  
|<span data-ttu-id="6ae0a-113">Word</span><span class="sxs-lookup"><span data-stu-id="6ae0a-113">Word</span></span>|<span data-ttu-id="6ae0a-114">Положение</span><span class="sxs-lookup"><span data-stu-id="6ae0a-114">Position</span></span>|  
|----------|--------------|  
|<span data-ttu-id="6ae0a-115">Instructions</span><span class="sxs-lookup"><span data-stu-id="6ae0a-115">Instructions</span></span>|<span data-ttu-id="6ae0a-116">1</span><span class="sxs-lookup"><span data-stu-id="6ae0a-116">1</span></span>|  
|<span data-ttu-id="6ae0a-117">are</span><span class="sxs-lookup"><span data-stu-id="6ae0a-117">are</span></span>|<span data-ttu-id="6ae0a-118">2</span><span class="sxs-lookup"><span data-stu-id="6ae0a-118">2</span></span>|  
|<span data-ttu-id="6ae0a-119">applicable</span><span class="sxs-lookup"><span data-stu-id="6ae0a-119">applicable</span></span>|<span data-ttu-id="6ae0a-120">3</span><span class="sxs-lookup"><span data-stu-id="6ae0a-120">3</span></span>|  
|<span data-ttu-id="6ae0a-121">значение</span><span class="sxs-lookup"><span data-stu-id="6ae0a-121">to</span></span>|<span data-ttu-id="6ae0a-122">4</span><span class="sxs-lookup"><span data-stu-id="6ae0a-122">4</span></span>|  
|<span data-ttu-id="6ae0a-123">these</span><span class="sxs-lookup"><span data-stu-id="6ae0a-123">these</span></span>|<span data-ttu-id="6ae0a-124">5</span><span class="sxs-lookup"><span data-stu-id="6ae0a-124">5</span></span>|  
|<span data-ttu-id="6ae0a-125">Adventure</span><span class="sxs-lookup"><span data-stu-id="6ae0a-125">Adventure</span></span>|<span data-ttu-id="6ae0a-126">6</span><span class="sxs-lookup"><span data-stu-id="6ae0a-126">6</span></span>|  
|<span data-ttu-id="6ae0a-127">Works</span><span class="sxs-lookup"><span data-stu-id="6ae0a-127">Works</span></span>|<span data-ttu-id="6ae0a-128">7</span><span class="sxs-lookup"><span data-stu-id="6ae0a-128">7</span></span>|  
|<span data-ttu-id="6ae0a-129">Cycles</span><span class="sxs-lookup"><span data-stu-id="6ae0a-129">Cycles</span></span>|<span data-ttu-id="6ae0a-130">8</span><span class="sxs-lookup"><span data-stu-id="6ae0a-130">8</span></span>|  
|<span data-ttu-id="6ae0a-131">модели</span><span class="sxs-lookup"><span data-stu-id="6ae0a-131">models</span></span>|<span data-ttu-id="6ae0a-132">9</span><span class="sxs-lookup"><span data-stu-id="6ae0a-132">9</span></span>|  
  
 <span data-ttu-id="6ae0a-133">Стоп-слова «are», «to» и «these», занимающие позиции 2, 4 и 5, в полнотекстовый индекс не включаются.</span><span class="sxs-lookup"><span data-stu-id="6ae0a-133">The stopwords "are", "to", and "these" that are in positions 2, 4, and 5 are left out of the full-text index.</span></span> <span data-ttu-id="6ae0a-134">Однако данные об их позициях сохраняются, благодаря чему позиции других слов в фразе остаются неизменными.</span><span class="sxs-lookup"><span data-stu-id="6ae0a-134">However, their positional information is maintained, thereby leaving the position of the other words in the phrase unaffected.</span></span>  
  
 <span data-ttu-id="6ae0a-135">Управление стоп-словами в базе данных производится через объекты, называемые списками стоп-слов.</span><span class="sxs-lookup"><span data-stu-id="6ae0a-135">Stopwords are managed in databases using objects called stoplists.</span></span> <span data-ttu-id="6ae0a-136">*Список стоп-слов* связан с полнотекстовым индексом и применяется к полнотекстовым запросам по этому индексу.</span><span class="sxs-lookup"><span data-stu-id="6ae0a-136">A *stoplist* is a list of stopwords that, when associated with a full-text index, is applied to full-text queries on that index.</span></span>  
  
  
##  <a name="creating-a-stoplist"></a><a name="creating"></a><span data-ttu-id="6ae0a-137">Создание списка стоп-слов</span><span class="sxs-lookup"><span data-stu-id="6ae0a-137">Creating a Stoplist</span></span>  
 <span data-ttu-id="6ae0a-138">Списки стоп-слов можно создать любым из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="6ae0a-138">You can create a stoplist in any of the following ways:</span></span>  
  
-   <span data-ttu-id="6ae0a-139">Использование поддерживаемого системой списка стоп-слов в базе данных.</span><span class="sxs-lookup"><span data-stu-id="6ae0a-139">Using the system-supplied stoplist in the database.</span></span> <span data-ttu-id="6ae0a-140">В составе [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поставляется системный список стоп-слов, который содержит наиболее часто используемые стоп-слова для каждого поддерживаемого языка, то есть для любого языка, связанного по умолчанию с предложенными конкретными средствами разбиения по словам.</span><span class="sxs-lookup"><span data-stu-id="6ae0a-140">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ships with a system stoplist that contains the most commonly used stopwords for each supported language, that is for every language that is associated with given word breakers by default.</span></span> <span data-ttu-id="6ae0a-141">Системный список стоп-слов содержит общие стоп-слова для всех поддерживаемых языков.</span><span class="sxs-lookup"><span data-stu-id="6ae0a-141">The system stoplist contains common stopwords for all supported languages.</span></span>  <span data-ttu-id="6ae0a-142">Можно скопировать системный список стоп-слов и внести необходимые изменения в созданную копию, добавляя и удаляя стоп-слова.</span><span class="sxs-lookup"><span data-stu-id="6ae0a-142">You can copy the system stoplist, and customize your copy by adding and removing stopwords.</span></span>  
  
     <span data-ttu-id="6ae0a-143">Системный список стоп-слов содержится в базе данных [Resource](../databases/resource-database.md) .</span><span class="sxs-lookup"><span data-stu-id="6ae0a-143">The system stoplist is installed in the [Resource](../databases/resource-database.md) database.</span></span>  
  
-   <span data-ttu-id="6ae0a-144">Создание собственного списка стоп-слов, а затем добавление к нему стоп-слов, относящихся к любому заданному языку.</span><span class="sxs-lookup"><span data-stu-id="6ae0a-144">Creating your own stoplist, and then adding stopwords to it for any language that you specify.</span></span> <span data-ttu-id="6ae0a-145">При необходимости можно удалять стоп-слова из этого списка.</span><span class="sxs-lookup"><span data-stu-id="6ae0a-145">You can also drop stopwords from your stoplist when necessary.</span></span>  
  
-   <span data-ttu-id="6ae0a-146">Использование существующего пользовательского списка стоп-слов из другой базы данных в текущем экземпляре сервера и затем (при необходимости) добавление и удаление стоп-слов.</span><span class="sxs-lookup"><span data-stu-id="6ae0a-146">Using an existing custom stoplist from any other database in the current server instance and then adding and dropping stopwords as necessary.</span></span>  
  
 <span data-ttu-id="6ae0a-147">**Создание списка стоп-слов**</span><span class="sxs-lookup"><span data-stu-id="6ae0a-147">**To create a stoplist**</span></span>  
  
-   [<span data-ttu-id="6ae0a-148">CREATE FULLTEXT STOPLIST (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="6ae0a-148">CREATE FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-fulltext-stoplist-transact-sql)  
  
#### <a name="to-create-a-full-text-stoplist-in-management-studio"></a><span data-ttu-id="6ae0a-149">Для создания полнотекстового списка стоп-слов в Management Studio</span><span class="sxs-lookup"><span data-stu-id="6ae0a-149">To create a full-text stoplist in Management Studio</span></span>  
  
1.  <span data-ttu-id="6ae0a-150">В обозревателе объектов разверните узел сервера.</span><span class="sxs-lookup"><span data-stu-id="6ae0a-150">In Object Explorer, expand the server.</span></span>  
  
2.  <span data-ttu-id="6ae0a-151">Разверните узел **Базы данных**, а затем разверните базу данных, в которой нужно создать список полнотекстовых стоп-слов.</span><span class="sxs-lookup"><span data-stu-id="6ae0a-151">Expand **Databases**, and then expand the database in which you want to create the full-text stoplist.</span></span>  
  
3.  <span data-ttu-id="6ae0a-152">Разверните узел **Хранилище**, а затем щелкните правой кнопкой мыши узел **Полнотекстовые списки стоп-слов**.</span><span class="sxs-lookup"><span data-stu-id="6ae0a-152">Expand **Storage**, and then right-click **Full-Text Stoplists**.</span></span>  
  
4.  <span data-ttu-id="6ae0a-153">Выберите пункт **Создание полнотекстового списка стоп-слов**.</span><span class="sxs-lookup"><span data-stu-id="6ae0a-153">Select **New Full-Text Stoplist**.</span></span>  
  
5.  <span data-ttu-id="6ae0a-154">Укажите имя списка стоп-слов.</span><span class="sxs-lookup"><span data-stu-id="6ae0a-154">Specify the stoplist name.</span></span>  
  
6.  <span data-ttu-id="6ae0a-155">Дополнительно можно указать владельца списка стоп-слов.</span><span class="sxs-lookup"><span data-stu-id="6ae0a-155">Optionally, specify someone else as the stoplist owner.</span></span>  
  
7.  <span data-ttu-id="6ae0a-156">Выберите один из следующих вариантов создания списка стоп-слов.</span><span class="sxs-lookup"><span data-stu-id="6ae0a-156">Select one of the following create stoplist options:</span></span>  
  
    -   <span data-ttu-id="6ae0a-157">**Создать пустой список стоп-слов**</span><span class="sxs-lookup"><span data-stu-id="6ae0a-157">**Create an empty stoplist**</span></span>  
  
    -   <span data-ttu-id="6ae0a-158">**Создать из системного списка стоп-слов**</span><span class="sxs-lookup"><span data-stu-id="6ae0a-158">**Create from the system stoplist**</span></span>  
  
    -   <span data-ttu-id="6ae0a-159">**Создать из существующего полнотекстового списка стоп-слов**</span><span class="sxs-lookup"><span data-stu-id="6ae0a-159">**Create from an existing full-text stoplist**</span></span>  
  
     <span data-ttu-id="6ae0a-160">Дополнительные сведения см. в разделе [Создание списка полнотекстовых стоп-слов (страница "Общие")](../../integration-services/general-page-of-integration-services-designers-options.md).</span><span class="sxs-lookup"><span data-stu-id="6ae0a-160">For more information, see [New Full-Text Stoplist &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md).</span></span>  
  
8.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
 <span data-ttu-id="6ae0a-161">**Удаление списка стоп-слов**</span><span class="sxs-lookup"><span data-stu-id="6ae0a-161">**To drop a stoplist**</span></span>  
  
-   [<span data-ttu-id="6ae0a-162">DROP FULLTEXT STOPLIST (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="6ae0a-162">DROP FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-fulltext-stoplist-transact-sql)  
  
  
##  <a name="using-a-stoplist-in-full-text-queries"></a><a name="queries"></a><span data-ttu-id="6ae0a-163">Использование списка стоп-слов в полнотекстовых запросах</span><span class="sxs-lookup"><span data-stu-id="6ae0a-163">Using a Stoplist in Full-Text Queries</span></span>  
 <span data-ttu-id="6ae0a-164">Чтобы использовать список стоп-слов в запросах, нужно связать его с полнотекстовым индексом.</span><span class="sxs-lookup"><span data-stu-id="6ae0a-164">To make use of a stoplist in queries, you must associate it with a full-text index.</span></span> <span data-ttu-id="6ae0a-165">Можно добавить список стоп-слов к полнотекстовому индексу при создании индекса или изменить индекс позже, добавив список стоп-слов.</span><span class="sxs-lookup"><span data-stu-id="6ae0a-165">You can attach a stoplist to a full-text index when you create the index, or you can alter the index later to add a stoplist.</span></span>  
  
 <span data-ttu-id="6ae0a-166">**Создание полнотекстового индекса и его связь со списком стоп-слов**</span><span class="sxs-lookup"><span data-stu-id="6ae0a-166">**To create a full-text index and associate a stoplist with it**</span></span>  
  
-   [<span data-ttu-id="6ae0a-167">CREATE FULLTEXT INDEX (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="6ae0a-167">CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-fulltext-index-transact-sql)  
  
 <span data-ttu-id="6ae0a-168">**Связывание или разъединение списка стоп-слов с существующим полнотекстовым индексом**</span><span class="sxs-lookup"><span data-stu-id="6ae0a-168">**To associate or disassociate a stoplist with an existing full-text index**</span></span>  
  
-   [<span data-ttu-id="6ae0a-169">ALTER FULLTEXT INDEX (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="6ae0a-169">ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-fulltext-index-transact-sql)  
  
 <span data-ttu-id="6ae0a-170">**Подавление сообщения об ошибке при неуспешном завершении логической операции, применяемой к полнотекстовому запросу, из-за стоп-слов**</span><span class="sxs-lookup"><span data-stu-id="6ae0a-170">**To suppress an error message if stopwords cause a Boolean operation on a full-text query to fail**</span></span>  
  
-   [<span data-ttu-id="6ae0a-171">Параметр конфигурации сервера «transform noise words»</span><span class="sxs-lookup"><span data-stu-id="6ae0a-171">transform noise words Server Configuration Option</span></span>](../../database-engine/configure-windows/transform-noise-words-server-configuration-option.md)  
  
  
##  <a name="viewing-stoplists-and-stoplist-metadata"></a><a name="viewing"></a><span data-ttu-id="6ae0a-172">Просмотр метаданных списков и списка стоп-слов</span><span class="sxs-lookup"><span data-stu-id="6ae0a-172">Viewing Stoplists and Stoplist Metadata</span></span>  
 <span data-ttu-id="6ae0a-173">**Для просмотра всех стоп-слов из списка стоп-слов**</span><span class="sxs-lookup"><span data-stu-id="6ae0a-173">**To view all the stopwords of a stoplist**</span></span>  
  
-   [<span data-ttu-id="6ae0a-174">sys.fulltext_stopwords (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="6ae0a-174">sys.fulltext_stopwords &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-stopwords-transact-sql)  
  
 <span data-ttu-id="6ae0a-175">**Получение сведений обо всех списках стоп-слов в текущей базе данных**</span><span class="sxs-lookup"><span data-stu-id="6ae0a-175">**To get information about all the stoplists in the current database**</span></span>  
  
-   [<span data-ttu-id="6ae0a-176">sys.fulltext_stoplists (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="6ae0a-176">sys.fulltext_stoplists &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-stoplists-transact-sql)  
  
-   [<span data-ttu-id="6ae0a-177">sys.fulltext_stopwords (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="6ae0a-177">sys.fulltext_stopwords &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-stopwords-transact-sql)  
  
 <span data-ttu-id="6ae0a-178">**Просмотр разметки, полученной в результате применения средства разбиения по словам, тезауруса и списка стоп-слов**</span><span class="sxs-lookup"><span data-stu-id="6ae0a-178">**To view the tokenization result of a word breaker, thesaurus, and stoplist combination**</span></span>  
  
-   [<span data-ttu-id="6ae0a-179">sys. dm_fts_parser &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6ae0a-179">sys.dm_fts_parser &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-parser-transact-sql)  
  
  
##  <a name="changing-the-stopwords-in-a-stoplist"></a><a name="change"></a><span data-ttu-id="6ae0a-180">Изменение стоп-слова в списке стоп-слов</span><span class="sxs-lookup"><span data-stu-id="6ae0a-180">Changing the Stopwords in a Stoplist</span></span>  
 <span data-ttu-id="6ae0a-181">**Добавление или удаление стоп-слов из списка стоп-слов**</span><span class="sxs-lookup"><span data-stu-id="6ae0a-181">**To add or drop stopwords from a stoplist**</span></span>  
  
-   [<span data-ttu-id="6ae0a-182">ALTER FULLTEXT STOPLIST (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="6ae0a-182">ALTER FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-fulltext-stoplist-transact-sql)  
  
#### <a name="to-change-the-stopwords-in-a-stoplist-in-management-studio"></a><span data-ttu-id="6ae0a-183">Изменение стоп-слов в списке стоп-слов в Management Studio</span><span class="sxs-lookup"><span data-stu-id="6ae0a-183">To change the stopwords in a stoplist in Management Studio</span></span>  
  
1.  <span data-ttu-id="6ae0a-184">В обозревателе объектов разверните узел сервера.</span><span class="sxs-lookup"><span data-stu-id="6ae0a-184">In Object Explorer, expand the server.</span></span>  
  
2.  <span data-ttu-id="6ae0a-185">Раскройте узел **Базы данных**, а затем — соответствующую базу данных.</span><span class="sxs-lookup"><span data-stu-id="6ae0a-185">Expand **Databases**, and then expand the database.</span></span>  
  
3.  <span data-ttu-id="6ae0a-186">Разверните узел **Хранилище**и выберите **Полнотекстовые списки стоп-слов**.</span><span class="sxs-lookup"><span data-stu-id="6ae0a-186">Expand **Storage**, and then select **Full Text Stoplists**.</span></span>  
  
4.  <span data-ttu-id="6ae0a-187">Щелкните правой кнопкой мыши список стоп-слов, свойства которого необходимо изменить, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="6ae0a-187">Right-click the stoplist whose properties you want to change, and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="6ae0a-188">В диалоговом окне [Свойства полнотекстового списка стоп-слов](../../database-engine/full-text-stoplist-properties.md) выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="6ae0a-188">In the [Full-Text Stoplist Properties](../../database-engine/full-text-stoplist-properties.md) dialog box:</span></span>  
  
    1.  <span data-ttu-id="6ae0a-189">В списке **Действия** выберите одно из следующих действий: **Добавить стоп-слово**, **Удалить стоп-слово**, **Удалить все стоп-слова**или **Очистить список стоп-слов**.</span><span class="sxs-lookup"><span data-stu-id="6ae0a-189">In the **Action** list box, select one of the following actions: **Add stopword**, **Delete stopword**, **Delete all stopwords**, or **Clear stoplist**.</span></span>  
  
    2.  <span data-ttu-id="6ae0a-190">Если для выбранного действия доступно текстовое поле **Стоп-слово** , введите одно стоп-слово.</span><span class="sxs-lookup"><span data-stu-id="6ae0a-190">If the **Stopword** text box is enabled for the selected action, enter a single stopword.</span></span> <span data-ttu-id="6ae0a-191">Это стоп-слово должно быть уникальным; иными словами, оно еще не должно присутствовать в списке стоп-слов для выбранного языка.</span><span class="sxs-lookup"><span data-stu-id="6ae0a-191">This stopword must be unique; that is, not yet in this stoplist for the language that you select.</span></span>  
  
    3.  <span data-ttu-id="6ae0a-192">Если для выбранного действия доступен список **Язык полнотекстового поиска** , выберите язык.</span><span class="sxs-lookup"><span data-stu-id="6ae0a-192">If the **Full-text language** list box is enabled for the selected action, select a language.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
##  <a name="upgrading-noise-words-from-sql-server-2005"></a><a name="upgrade"></a><span data-ttu-id="6ae0a-193">Обновление пропускаемых слов с SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="6ae0a-193">Upgrading Noise Words from SQL Server 2005</span></span>  
 [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] <span data-ttu-id="6ae0a-194">пропускаемые слова были заменены стоп-словами.</span><span class="sxs-lookup"><span data-stu-id="6ae0a-194">noise words have been replaced by stopwords.</span></span> <span data-ttu-id="6ae0a-195">При обновлении базы данных с версии [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]файлы пропускаемых слов более не используются.</span><span class="sxs-lookup"><span data-stu-id="6ae0a-195">When a database is upgraded from [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], the noise-word files are no longer used.</span></span> <span data-ttu-id="6ae0a-196">Однако файлы пропускаемых слов хранятся в папке FTDATA\FTNoiseThresaurusBak, и их можно использовать в дальнейшем при обновлении или построении соответствующих списков стоп-слов.</span><span class="sxs-lookup"><span data-stu-id="6ae0a-196">However, the noise-word files are stored in the FTDATA\ FTNoiseThesaurusBak folder, and you can use them later when updating or building the corresponding stoplists.</span></span> <span data-ttu-id="6ae0a-197">Сведения об обновлении файлов пропускаемых слов с переходом к спискам стоп-слов см. в разделе [Обновление полнотекстового поиска](upgrade-full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="6ae0a-197">For information about upgrading noise-word files to stoplists, see [Upgrade Full-Text Search](upgrade-full-text-search.md).</span></span>  
  
  
  
