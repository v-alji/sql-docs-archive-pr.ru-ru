---
title: Устранение неполадок полнотекстового индексирования | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- indexes [full-text search]
- troubleshooting [SQL Server], full-text search
- troubleshooting [full-text search]
ms.assetid: 964c43a8-5019-4179-82aa-63cd0ef592ef
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: eaca5fcf2dfbac57fc6d3ba6178251927d15aba9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668733"
---
# <a name="troubleshoot-full-text-indexing"></a><span data-ttu-id="99dfa-102">Устранение неполадок полнотекстового индексирования</span><span class="sxs-lookup"><span data-stu-id="99dfa-102">Troubleshoot Full-Text Indexing</span></span>
     
##  <a name="troubleshoot-full-text-indexing-failures"></a><a name="failure"></a> <span data-ttu-id="99dfa-103">Устранение неполадок при неудачном завершении полнотекстового индексирования</span><span class="sxs-lookup"><span data-stu-id="99dfa-103">Troubleshoot Full-Text Indexing Failures</span></span>  
 <span data-ttu-id="99dfa-104">При заполнении или обслуживании полнотекстового индекса полнотекстовый индексатор по изложенным ниже причинам может пропустить одну или несколько строк.</span><span class="sxs-lookup"><span data-stu-id="99dfa-104">While populating or maintaining a full-text index, the full-text indexer, for reasons described below, might fail to index one or more rows.</span></span> <span data-ttu-id="99dfa-105">Данные ошибки на уровне строк не препятствуют завершению заполнения.</span><span class="sxs-lookup"><span data-stu-id="99dfa-105">These row-level errors do not prevent the population from completing.</span></span> <span data-ttu-id="99dfa-106">Индексатор просто пропускает эти строки, что означает, что их содержимое останется недосягаемым для запросов.</span><span class="sxs-lookup"><span data-stu-id="99dfa-106">The indexer skips these rows, which means that you are not able to query for content contained in these rows.</span></span>  
  
 <span data-ttu-id="99dfa-107">Ошибки индексирования могут возникать в следующих случаях.</span><span class="sxs-lookup"><span data-stu-id="99dfa-107">Indexing failures can occur when:</span></span>  
  
-   <span data-ttu-id="99dfa-108">Индексатор не смог найти или загрузить фильтр либо средство разбиения по словам.</span><span class="sxs-lookup"><span data-stu-id="99dfa-108">The indexer cannot find or load a filter or word breaker component.</span></span> <span data-ttu-id="99dfa-109">Данная ошибка может возникать, если строка таблицы содержит формат документа или содержимое на языке, не зарегистрированном в экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="99dfa-109">This failure can occur if the table row contains a document format or content in a language that has not been registered with the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="99dfa-110">Данная ошибка также может возникать, если зарегистрированный компонент средства разбиения по словам или фильтрации не подписан либо не прошел проверку подписи при загрузке.</span><span class="sxs-lookup"><span data-stu-id="99dfa-110">This failure can also happen if the registered word breaker or filter component was not signed or failed signature verification when it was being loaded.</span></span>  
  
-   <span data-ttu-id="99dfa-111">Возникает ошибка в компоненте, например в средстве разбиения по словам или фильтре, возвращаемая индексатору.</span><span class="sxs-lookup"><span data-stu-id="99dfa-111">A component, such as a word breaker or filter, fails and returns an error to the indexer.</span></span> <span data-ttu-id="99dfa-112">Это может происходить, если индексируемый документ испорчен и фильтр не может извлечь из него текст.</span><span class="sxs-lookup"><span data-stu-id="99dfa-112">This can happen if the document being indexed is corrupt and the filter is unable to extract text from the document.</span></span> <span data-ttu-id="99dfa-113">Это также может происходить, если компонент вследствие ограничения памяти, установленного в узле управляющей программы полнотекстовой фильтрации (fdhost.exe), не может обработать содержимое одной строки, превышающее определенный размер.</span><span class="sxs-lookup"><span data-stu-id="99dfa-113">This can also occur when a component is unable to handle the content of a single row above a certain size, due to memory limits on the full-text filter daemon host (fdhost.exe).</span></span>  
  
 <span data-ttu-id="99dfa-114">Подробное описание причин каждой ошибки на уровне строк регистрируется в журнале сканирования.</span><span class="sxs-lookup"><span data-stu-id="99dfa-114">For each row-level failure, the crawl log contains details on the reason for the failure.</span></span> <span data-ttu-id="99dfa-115">Итоговое количество ошибок определяется после полного или добавочного заполнения.</span><span class="sxs-lookup"><span data-stu-id="99dfa-115">The error counts are summarized at the end of a full or incremental population.</span></span>  
  
 <span data-ttu-id="99dfa-116">Существуют и другие ошибки, которые могут повлиять на индексирование как таковое и препятствовать завершению заполнения:</span><span class="sxs-lookup"><span data-stu-id="99dfa-116">There are other failures that can impact the indexing process itself and prevent the population from completing:</span></span>  
  
-   <span data-ttu-id="99dfa-117">Размер полнотекстового индекса превышает ограничение на количество строк, которые могут находиться в полнотекстовом каталоге.</span><span class="sxs-lookup"><span data-stu-id="99dfa-117">The full-text index exceeds the limit for the number of rows that can be contained in a full-text catalog.</span></span>  
  
-   <span data-ttu-id="99dfa-118">Кластеризованный индекс или индекс полнотекстового ключа в индексируемой таблице изменяется, удаляется или перестраивается.</span><span class="sxs-lookup"><span data-stu-id="99dfa-118">A clustered index or full-text key index on the table being indexed gets altered, dropped, or rebuilt.</span></span>  
  
-   <span data-ttu-id="99dfa-119">Сбой оборудования или повреждение жесткого диска, вызывающее повреждение полнотекстового каталога.</span><span class="sxs-lookup"><span data-stu-id="99dfa-119">A hardware failure or disk corruption results in the corruption of the full-text catalog.</span></span>  
  
-   <span data-ttu-id="99dfa-120">Файловая группа, содержащая таблицу, в которой выполняется полнотекстовое индексирование, становится вне сети или доступной только для чтения.</span><span class="sxs-lookup"><span data-stu-id="99dfa-120">A file group that contains the table being full-text indexed goes offline, or is made read-only.</span></span>  
  
 <span data-ttu-id="99dfa-121">По окончании любой крупной операции заполнения полнотекстового индекса или в случае обнаружения незавершенной операции заполнения рекомендуется изучить журнал сканирования.</span><span class="sxs-lookup"><span data-stu-id="99dfa-121">You should view the crawl log at the end of any significant full-text index population operation, or when you find that a population did not complete.</span></span>  
  
### <a name="unsigned-components"></a><span data-ttu-id="99dfa-122">Неподписанные компоненты</span><span class="sxs-lookup"><span data-stu-id="99dfa-122">Unsigned Components</span></span>  
 <span data-ttu-id="99dfa-123">По умолчанию полнотекстовый индексатор требует, чтобы загружаемые им фильтры и средства разбиения по словам были подписаны.</span><span class="sxs-lookup"><span data-stu-id="99dfa-123">By default, the full-text indexer requires the filters and word breakers that it loads to be signed.</span></span> <span data-ttu-id="99dfa-124">Если они не подписаны, что иногда случается при установке пользовательских компонентов, необходимо настроить полнотекстовый индексатор так, чтобы он пропускал проверку подписей.</span><span class="sxs-lookup"><span data-stu-id="99dfa-124">If they are not signed, which is the case sometimes when custom components are installed, you must configure the full-text indexer to ignore signature verification.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="99dfa-125">Игнорирование проверки подписей снижает защищенность экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="99dfa-125">Ignoring signature verification makes the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] less secure.</span></span> <span data-ttu-id="99dfa-126">Рекомендуется подписывать все самостоятельно внедряемые компоненты либо контролировать наличие подписей у всех приобретаемых компонентов.</span><span class="sxs-lookup"><span data-stu-id="99dfa-126">We recommend that you sign any components that you implement or ensure that any components that you acquire are signed.</span></span> <span data-ttu-id="99dfa-127">Дополнительные сведения о подписании компонентов см. в разделе [sp_fulltext_service (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-fulltext-service-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="99dfa-127">For information about signing components, see [sp_fulltext_service &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-fulltext-service-transact-sql).</span></span>  
  

  
##  <a name="full-text-index-in-inconsistent-state-after-transaction-log-restored"></a><a name="state"></a> <span data-ttu-id="99dfa-128">Полнотекстовый индекс в несогласованном состоянии после восстановления журнала транзакций</span><span class="sxs-lookup"><span data-stu-id="99dfa-128">Full-Text Index in Inconsistent State after Transaction Log Restored</span></span>  
 <span data-ttu-id="99dfa-129">При восстановлении журнала транзакций базы данных может появиться предупреждение о том, что полнотекстовый индекс находится в рассогласованном состоянии.</span><span class="sxs-lookup"><span data-stu-id="99dfa-129">When restoring the transaction log of a database, you might see a warning indicating that the full-text index is not in a consistent state.</span></span> <span data-ttu-id="99dfa-130">Причина заключается в том, что этот полнотекстовый индекс в таблице был изменен после резервного копирования базы данных.</span><span class="sxs-lookup"><span data-stu-id="99dfa-130">The reason for this is that the full-text index on a table was modified after the database was backed up.</span></span> <span data-ttu-id="99dfa-131">Чтобы привести полнотекстовый индекс в согласованное состояние, необходимо выполнить в таблице полное заполнение (сканирование).</span><span class="sxs-lookup"><span data-stu-id="99dfa-131">To bring the full-text index to a consistent state, you must run a full population (crawl) on the table.</span></span> <span data-ttu-id="99dfa-132">Дополнительные сведения см. в разделе [Заполнение полнотекстовых индексов](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="99dfa-132">For more information, see [Populate Full-Text Indexes](../indexes/indexes.md).</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="99dfa-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="99dfa-133">See Also</span></span>  
 <span data-ttu-id="99dfa-134">[ALTER FULLTEXT CATALOG (Transact-SQL)](/sql/t-sql/statements/alter-fulltext-catalog-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="99dfa-134">[ALTER FULLTEXT CATALOG &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-catalog-transact-sql) </span></span>  
 [<span data-ttu-id="99dfa-135">Заполнение полнотекстовых индексов</span><span class="sxs-lookup"><span data-stu-id="99dfa-135">Populate Full-Text Indexes</span></span>](../indexes/indexes.md)  
  
  
