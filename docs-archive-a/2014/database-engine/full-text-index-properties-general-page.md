---
title: Свойства полнотекстового индекса (страница «Общие») | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextsearch.fulltextindexproperties.general.f1
ms.assetid: f4dff61c-8c2f-4ff9-abe4-70a34421448f
author: rothja
ms.author: jroth
ms.openlocfilehash: 61b9f2948df138c39230cf6f5787c395a364c695
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669059"
---
# <a name="full-text-index-properties-general-page"></a><span data-ttu-id="107e3-102">Свойства полнотекстового индекса (страница «Общие»)</span><span class="sxs-lookup"><span data-stu-id="107e3-102">Full-Text Index Properties (General Page)</span></span>
  <span data-ttu-id="107e3-103">**Просмотр или изменение изменяемых свойств полнотекстового индекса**</span><span class="sxs-lookup"><span data-stu-id="107e3-103">**To view or change the modifiable properties of a full-text index**</span></span>  
  
-   [<span data-ttu-id="107e3-104">Управление полнотекстовыми индексами</span><span class="sxs-lookup"><span data-stu-id="107e3-104">Manage Full-Text Indexes</span></span>](../relational-databases/indexes/indexes.md)  
  
## <a name="ui-element-list"></a><span data-ttu-id="107e3-105">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="107e3-105">UI element list</span></span>  
 <span data-ttu-id="107e3-106">**Полнотекстовый каталог**</span><span class="sxs-lookup"><span data-stu-id="107e3-106">**Full-Text Catalog**</span></span>  
 <span data-ttu-id="107e3-107">Отображает имя полнотекстового каталога, с которым связан полнотекстовый индекс.</span><span class="sxs-lookup"><span data-stu-id="107e3-107">Displays the name of the full-text catalog with which the full-text index is associated.</span></span>  
  
 <span data-ttu-id="107e3-108">**База данных**</span><span class="sxs-lookup"><span data-stu-id="107e3-108">**Database**</span></span>  
 <span data-ttu-id="107e3-109">Отображает имя базы данных, в которой находится полнотекстовый индекс.</span><span class="sxs-lookup"><span data-stu-id="107e3-109">Displays the name of the database in which the full-text index resides.</span></span>  
  
 <span data-ttu-id="107e3-110">**Таблица**</span><span class="sxs-lookup"><span data-stu-id="107e3-110">**Table**</span></span>  
 <span data-ttu-id="107e3-111">Позволяет отобразить имя таблицы, для которой определен полнотекстовый индекс.</span><span class="sxs-lookup"><span data-stu-id="107e3-111">Displays the name of the table on which the full-text index is defined.</span></span>  
  
 <span data-ttu-id="107e3-112">**Полнотекстовый ключ индекса**</span><span class="sxs-lookup"><span data-stu-id="107e3-112">**Full-Text Index Key**</span></span>  
 <span data-ttu-id="107e3-113">Отображает имя полнотекстового ключа индекса, который является уникальным индексом для отдельного столбца таблицы.</span><span class="sxs-lookup"><span data-stu-id="107e3-113">Displays the name of the full-text index key, which is a unique index on a single column of the table.</span></span>  
  
 <span data-ttu-id="107e3-114">**Состояние табличных заполнений полнотекстовых индексов**</span><span class="sxs-lookup"><span data-stu-id="107e3-114">**Table Full-Text Populate Status**</span></span>  
 <span data-ttu-id="107e3-115">Отображает состояние заполнения полнотекстовой индексированной таблицы.</span><span class="sxs-lookup"><span data-stu-id="107e3-115">Displays the population status of the full-text indexed table.</span></span>  
  
 <span data-ttu-id="107e3-116">Возможны следующие значения:</span><span class="sxs-lookup"><span data-stu-id="107e3-116">The possible values are as follows:</span></span>  
  
 <span data-ttu-id="107e3-117">0 = Бездействует.</span><span class="sxs-lookup"><span data-stu-id="107e3-117">0 = Idle.</span></span>  
  
 <span data-ttu-id="107e3-118">1 = Производится полное заполнение.</span><span class="sxs-lookup"><span data-stu-id="107e3-118">1 = Full population is in progress.</span></span>  
  
 <span data-ttu-id="107e3-119">2 = Производится добавочное заполнение.</span><span class="sxs-lookup"><span data-stu-id="107e3-119">2 = Incremental population is in progress.</span></span>  
  
 <span data-ttu-id="107e3-120">3 = Выполняется распространение отслеженных изменений.</span><span class="sxs-lookup"><span data-stu-id="107e3-120">3 = Propagation of tracked changes is in progress.</span></span>  
  
 <span data-ttu-id="107e3-121">4 = Выполняется индексирование фонового обновления (например, автоматическое отслеживание изменений).</span><span class="sxs-lookup"><span data-stu-id="107e3-121">4 = Background update index is in progress, such as automatic change tracking.</span></span>  
  
 <span data-ttu-id="107e3-122">5 = Полнотекстовое индексирование приостановлено, или не хватает ресурсов на его выполнение.</span><span class="sxs-lookup"><span data-stu-id="107e3-122">5 = Full-text indexing is throttled or paused.</span></span>  
  
 <span data-ttu-id="107e3-123">**Активный полнотекстовый индекс**</span><span class="sxs-lookup"><span data-stu-id="107e3-123">**Active Full-Text Index**</span></span>  
 <span data-ttu-id="107e3-124">Указывает, содержит ли таблица активный полнотекстовый индекс.</span><span class="sxs-lookup"><span data-stu-id="107e3-124">Indicates whether the table has an active full-text index.</span></span>  
  
 <span data-ttu-id="107e3-125">1 = истина</span><span class="sxs-lookup"><span data-stu-id="107e3-125">1 = True</span></span>  
  
 <span data-ttu-id="107e3-126">0 = ложь</span><span class="sxs-lookup"><span data-stu-id="107e3-126">0 = False</span></span>  
  
 <span data-ttu-id="107e3-127">**Файловая группа полнотекстового индекса**</span><span class="sxs-lookup"><span data-stu-id="107e3-127">**Full-Text Index Filegroup**</span></span>  
 <span data-ttu-id="107e3-128">Файловая группа, к которой принадлежит полнотекстовый индекс.</span><span class="sxs-lookup"><span data-stu-id="107e3-128">The filegroup to which the full-text index belongs.</span></span>  
  
 <span data-ttu-id="107e3-129">**Список стоп-слов полнотекстового индекса**.</span><span class="sxs-lookup"><span data-stu-id="107e3-129">**Full-Text Index Stoplist**</span></span>  
 <span data-ttu-id="107e3-130">Указывает список стоп-слов, который в данный момент связан с полнотекстовым индексом.</span><span class="sxs-lookup"><span data-stu-id="107e3-130">The stoplist that is currently associated with the full-text index.</span></span> <span data-ttu-id="107e3-131">Список стоп-слов содержит [стоп-слова](../relational-databases/search/full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="107e3-131">A stoplist is a list of [stopwords](../relational-databases/search/full-text-search.md).</span></span> <span data-ttu-id="107e3-132">Связанный с полнотекстовым индексом список стоп-слов (если он существует) применяется к полнотекстовым запросам к данному индексу.</span><span class="sxs-lookup"><span data-stu-id="107e3-132">The stoplist associated with a full-text index, if any, is applied to full-text queries on that index.</span></span> <span data-ttu-id="107e3-133">Список стоп-слов можно удалить из индекса, выбрав **\<OFF>** его из списка, или можно выбрать другой список стоп-слов; **\<SYSTEM>** указывает системный список.</span><span class="sxs-lookup"><span data-stu-id="107e3-133">You can remove the stoplist from the index by selecting **\<OFF>** from the list, or you can select a different stoplist; **\<SYSTEM>** indicates the system stoplist.</span></span>  
  
 <span data-ttu-id="107e3-134">**Создание списка стоп-слов**</span><span class="sxs-lookup"><span data-stu-id="107e3-134">**To create a stoplist**</span></span>  
  
-   [<span data-ttu-id="107e3-135">Настройка и управление стоп-словами и списками стоп-слов для полнотекстового поиска</span><span class="sxs-lookup"><span data-stu-id="107e3-135">Configure and Manage Stopwords and Stoplists for Full-Text Search</span></span>](../relational-databases/search/full-text-search.md)  
  
 <span data-ttu-id="107e3-136">**Поиск в списке свойств**.</span><span class="sxs-lookup"><span data-stu-id="107e3-136">**Search Property List**</span></span>  
 <span data-ttu-id="107e3-137">Список свойств поиска, в настоящее время связанный с полнотекстовым индексом, если он имеется.</span><span class="sxs-lookup"><span data-stu-id="107e3-137">The search property list that is currently associated with the full-text index, if any.</span></span> <span data-ttu-id="107e3-138">Список свойств поиска задает набор свойств документа, которые включаются в связанный полнотекстовый индекс при его заполнении.</span><span class="sxs-lookup"><span data-stu-id="107e3-138">A search property list specifies a set of document properties that are included in the associated full-text index when it is populated.</span></span> <span data-ttu-id="107e3-139">Дополнительные сведения см. в статье [Поиск свойств документа с использованием списков свойств поиска](../relational-databases/search/search-document-properties-with-search-property-lists.md).</span><span class="sxs-lookup"><span data-stu-id="107e3-139">For more information, see [Search Document Properties with Search Property Lists](../relational-databases/search/search-document-properties-with-search-property-lists.md).</span></span>  
  
 <span data-ttu-id="107e3-140">**\<Off>** Указывает, что в настоящее время отсутствует список свойств поиска, связанный с индексом.</span><span class="sxs-lookup"><span data-stu-id="107e3-140">**\<Off>** indicates that there is currently no search property list associated with the index.</span></span> <span data-ttu-id="107e3-141">Вы можете удалить текущий список свойств поиска из индекса, выбрав **\<Off>** из списка или выбрав другой список свойств поиска из списка.</span><span class="sxs-lookup"><span data-stu-id="107e3-141">You can remove the current search property list from the index by selecting **\<Off>** from the list, or you can select a different search property list from the list.</span></span> <span data-ttu-id="107e3-142">Здесь указаны только списки поиска свойств в текущей базе данных.</span><span class="sxs-lookup"><span data-stu-id="107e3-142">Only search property lists in the current database are listed here.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="107e3-143">Один список свойств поиска может быть связан с несколькими полнотекстовыми индексами в той же базе данных.</span><span class="sxs-lookup"><span data-stu-id="107e3-143">You can associate a given search property list with more than one full-text index in the same database.</span></span>  
  
 <span data-ttu-id="107e3-144">**Создание списка свойств поиска**</span><span class="sxs-lookup"><span data-stu-id="107e3-144">**To create a search property list**</span></span>  
  
-   [<span data-ttu-id="107e3-145">Поиск свойств документа с помощью списков свойств поиска</span><span class="sxs-lookup"><span data-stu-id="107e3-145">Search Document Properties with Search Property Lists</span></span>](../relational-databases/search/search-document-properties-with-search-property-lists.md)  
  
 <span data-ttu-id="107e3-146">**Счетчик табличных полнотекстовых элементов**</span><span class="sxs-lookup"><span data-stu-id="107e3-146">**Table Full-Text Item Count**</span></span>  
 <span data-ttu-id="107e3-147">Указывает число строк, которые были успешно проиндексированы.</span><span class="sxs-lookup"><span data-stu-id="107e3-147">Indicates the number of rows that were full-text indexed successfully.</span></span>  
  
 <span data-ttu-id="107e3-148">Это свойство соответствует свойству `TableFulltextItemCount`, возвращаемому функцией OBJECTPROPERTYEX [!INCLUDE[tsql](../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="107e3-148">This property corresponds to the `TableFulltextItemCount` property returned by the OBJECTPROPERTYEX [!INCLUDE[tsql](../includes/tsql-md.md)] function.</span></span>  
  
 <span data-ttu-id="107e3-149">**Обработанные табличные полнотекстовые документы**</span><span class="sxs-lookup"><span data-stu-id="107e3-149">**Table Full-Text Docs Processed**</span></span>  
 <span data-ttu-id="107e3-150">Отображает число строк, обработанных с начала полнотекстового индексирования.</span><span class="sxs-lookup"><span data-stu-id="107e3-150">Displays the number of rows that have been processed since the start of full-text indexing.</span></span> <span data-ttu-id="107e3-151">В таблице, которая индексируется для полнотекстового поиска, все столбцы одной строки рассматриваются как часть единого индексируемого документа.</span><span class="sxs-lookup"><span data-stu-id="107e3-151">In a table that is being indexed for full-text search, all the columns of one row are considered as part of one document to be indexed.</span></span> <span data-ttu-id="107e3-152">Удаленные строки не считаются.</span><span class="sxs-lookup"><span data-stu-id="107e3-152">Deleted rows are not counted.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="107e3-153">0</span><span class="sxs-lookup"><span data-stu-id="107e3-153">0</span></span>|<span data-ttu-id="107e3-154">Указывает, что полнотекстовое индексирование завершено и активное заполнение отсутствует.</span><span class="sxs-lookup"><span data-stu-id="107e3-154">Indicates that full-text indexing is completed and there is no active population.</span></span>|  
|<span data-ttu-id="107e3-155">> 0</span><span class="sxs-lookup"><span data-stu-id="107e3-155">> 0</span></span>|<span data-ttu-id="107e3-156">Для активного заполнения указывает число документов, обработанных операциями вставки или обновления со времени заполнения, включения отслеживания изменений при фоновом заполнении индекса (такого как автоматическое отслеживание изменений), изменения схемы полнотекстового индекса, повторного построения полнотекстового каталога, перезапуска экземпляра [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]и т. д.</span><span class="sxs-lookup"><span data-stu-id="107e3-156">For an active population, indicates the number of documents processed by insert or update operations since any of the following: a population, enabling of change tracking with background update index population (such as auto change tracking), changing the full-text index schema, rebuilding the full-text catalog, restarting the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], and so forth.</span></span>|  
  
 <span data-ttu-id="107e3-157">**Ожидающие табличные полнотекстовые изменения**</span><span class="sxs-lookup"><span data-stu-id="107e3-157">**Table Full-Text Pending Changes**</span></span>  
 <span data-ttu-id="107e3-158">Количество ожидающих отслеженных изменений к обработке.</span><span class="sxs-lookup"><span data-stu-id="107e3-158">Number of pending change tracking entries to process.</span></span>  
  
 <span data-ttu-id="107e3-159">0 = Отслеживание изменений не включено.</span><span class="sxs-lookup"><span data-stu-id="107e3-159">0 = change tracking is not enabled.</span></span>  
  
 <span data-ttu-id="107e3-160">NULL = Таблица не содержит полнотекстового индекса.</span><span class="sxs-lookup"><span data-stu-id="107e3-160">NULL = Table does not have a full-text index.</span></span>  
  
 <span data-ttu-id="107e3-161">**Счетчик отказов табличных полнотекстовых элементов**</span><span class="sxs-lookup"><span data-stu-id="107e3-161">**Table Full-Text Fail Count**</span></span>  
 <span data-ttu-id="107e3-162">Число строк, не проиндексированных для полнотекстового поиска.</span><span class="sxs-lookup"><span data-stu-id="107e3-162">The number of rows that full-text search did not index.</span></span>  
  
 <span data-ttu-id="107e3-163">0 = Заполнение завершено.</span><span class="sxs-lookup"><span data-stu-id="107e3-163">0 = The population has completed.</span></span>  
  
 <span data-ttu-id="107e3-164">\>0 = одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="107e3-164">\>0 = One of the following:</span></span>  
  
-   <span data-ttu-id="107e3-165">Количество документов, не индексированных с начала заполнения отслеженных изменений полного, добавочного или ручного обновления.</span><span class="sxs-lookup"><span data-stu-id="107e3-165">The number of documents that were not indexed since the start of full, incremental, or manual change tracking population.</span></span>  
  
-   <span data-ttu-id="107e3-166">Для отслеживания изменений с индексацией фонового обновления — число строк, которые не проиндексированы с начала или перезапуска заполнения.</span><span class="sxs-lookup"><span data-stu-id="107e3-166">For change tracking with background update index, the number of rows that were not indexed since the start of the population, or the restart of the population.</span></span> <span data-ttu-id="107e3-167">Это может быть вызвано изменением схемы, перестройкой каталога, перезапуском сервера и т. д.</span><span class="sxs-lookup"><span data-stu-id="107e3-167">This could be caused by a schema change, rebuild of the catalog, server restart, and so on</span></span>  
  
 <span data-ttu-id="107e3-168">**Полнотекстовое индексирование включено**.</span><span class="sxs-lookup"><span data-stu-id="107e3-168">**Full-Text Indexing Enabled**</span></span>  
 <span data-ttu-id="107e3-169">Указывает, включено ли полнотекстовое индексирование.</span><span class="sxs-lookup"><span data-stu-id="107e3-169">Specifies whether full-text indexing is enabled.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="107e3-170">**True**</span><span class="sxs-lookup"><span data-stu-id="107e3-170">**True**</span></span>|<span data-ttu-id="107e3-171">Активировано</span><span class="sxs-lookup"><span data-stu-id="107e3-171">Enabled</span></span>|  
|<span data-ttu-id="107e3-172">**False**</span><span class="sxs-lookup"><span data-stu-id="107e3-172">**False**</span></span>|<span data-ttu-id="107e3-173">Выключено</span><span class="sxs-lookup"><span data-stu-id="107e3-173">Disabled</span></span>|  
  
 <span data-ttu-id="107e3-174">**Отслеживание изменений**</span><span class="sxs-lookup"><span data-stu-id="107e3-174">**Change Tracking**</span></span>  
 <span data-ttu-id="107e3-175">Указывает, включено ли для таблицы полнотекстовое отслеживание изменений и, если да, какого типа.</span><span class="sxs-lookup"><span data-stu-id="107e3-175">Specifies whether the table has full-text change-tracking enabled, and if so, what kind.</span></span> <span data-ttu-id="107e3-176">Полнотекстовое отслеживание изменений поддерживает список всех измененных строк таблицы или индексированного представления, подлежащих полнотекстовому индексированию.</span><span class="sxs-lookup"><span data-stu-id="107e3-176">Full-text change tracking maintains a record of the rows that have been modified in a table or indexed view that has been set up for full-text indexing.</span></span> <span data-ttu-id="107e3-177">Эти изменения распространяются на полнотекстовый индекс.</span><span class="sxs-lookup"><span data-stu-id="107e3-177">These changes can be propagated to the full-text index.</span></span>  
  
 <span data-ttu-id="107e3-178">Параметр **Отслеживание изменений** имеет следующие значения.</span><span class="sxs-lookup"><span data-stu-id="107e3-178">The **Change Tracking** values are as follows:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="107e3-179">**Выключено**</span><span class="sxs-lookup"><span data-stu-id="107e3-179">**Off**</span></span>|<span data-ttu-id="107e3-180">Изменения базовых данных не отражаются в полнотекстовом индексе.</span><span class="sxs-lookup"><span data-stu-id="107e3-180">The full-text index is not updated with changes to the underlying data.</span></span>|  
|<span data-ttu-id="107e3-181">**Manual** (Вручную)</span><span class="sxs-lookup"><span data-stu-id="107e3-181">**Manual**</span></span>|<span data-ttu-id="107e3-182">Изменения базовых данных не вызывают автоматического обновления полнотекстового индекса.</span><span class="sxs-lookup"><span data-stu-id="107e3-182">The full-text index is not updated automatically as changes occur to the underlying data.</span></span> <span data-ttu-id="107e3-183">При этом изменения базовых данных сохраняются, и их можно распространить на</span><span class="sxs-lookup"><span data-stu-id="107e3-183">However, changes to the underlying data are maintained, and you can propagate them to the .</span></span> <span data-ttu-id="107e3-184">полнотекстовый индекс по расписанию с помощью агента SQL Server или вручную.</span><span class="sxs-lookup"><span data-stu-id="107e3-184">full-text index either on a schedule using SQL Server Agent or manually.</span></span>|  
|<span data-ttu-id="107e3-185">**Автоматический**</span><span class="sxs-lookup"><span data-stu-id="107e3-185">**Automatic**</span></span>|<span data-ttu-id="107e3-186">Изменения базовых данных в базовой таблице не вызывают автоматического обновления полнотекстового индекса.</span><span class="sxs-lookup"><span data-stu-id="107e3-186">The full-text index is updated automatically as changes occur to the underlying data in the base table.</span></span>|  
  
 <span data-ttu-id="107e3-187">**Повторить заполнение индекса**</span><span class="sxs-lookup"><span data-stu-id="107e3-187">**Repopulate index**</span></span>  
 <span data-ttu-id="107e3-188">Щелкните для запуска заполнения полнотекстового индекса при закрытии диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="107e3-188">Click to start a population on the full-text index on exiting the dialog box.</span></span> <span data-ttu-id="107e3-189">Выберите один из следующих типов заполнения.</span><span class="sxs-lookup"><span data-stu-id="107e3-189">Select one of the following types of population:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="107e3-190">**Полное**</span><span class="sxs-lookup"><span data-stu-id="107e3-190">**Full**</span></span>|<span data-ttu-id="107e3-191">Во время полного заполнения таблицы записи индекса создаются для всех строк.</span><span class="sxs-lookup"><span data-stu-id="107e3-191">During a full population of a table, index entries are built for all the rows.</span></span>|  
|<span data-ttu-id="107e3-192">**Присоединен**</span><span class="sxs-lookup"><span data-stu-id="107e3-192">**Incremental**</span></span>|<span data-ttu-id="107e3-193">Операция добавочного заполнения обновляет полнотекстовый индекс для строк, добавленных, удаленных или измененных после или во время последнего заполнения.</span><span class="sxs-lookup"><span data-stu-id="107e3-193">Incremental population updates the full-text index for rows added, deleted, or modified after the last population, or while the last population was in progress.</span></span> <span data-ttu-id="107e3-194">Для выполнения добавочного заполнения базовая таблица должна включать столбец с типом данных `timestamp`.</span><span class="sxs-lookup"><span data-stu-id="107e3-194">Performing an incremental population requires that the base table contain a column of the `timestamp` data type.</span></span>|  
|<span data-ttu-id="107e3-195">**Обновление**</span><span class="sxs-lookup"><span data-stu-id="107e3-195">**Update**</span></span>|<span data-ttu-id="107e3-196">Полнотекстовый индекс обновляется при изменении данных в базовой таблице.</span><span class="sxs-lookup"><span data-stu-id="107e3-196">The full-text index is updated whenever the data in the base table is modified.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="107e3-197">См. также:</span><span class="sxs-lookup"><span data-stu-id="107e3-197">See Also</span></span>  
 [<span data-ttu-id="107e3-198">Начало работы с компонентом Full-Text Search</span><span class="sxs-lookup"><span data-stu-id="107e3-198">Get Started with Full-Text Search</span></span>](../relational-databases/search/get-started-with-full-text-search.md)  
  
  
