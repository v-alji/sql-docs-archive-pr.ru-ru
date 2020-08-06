---
title: Заполнение полнотекстовых индексов | Документация Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- index populations [full-text search]
- incremental populations [full-text search]
- populations [full-text search]
- full-text search [SQL Server], populations
- crawls [full-text search]
- automatic full-text index updates
- change tracking-based populations [full-text search]
- manual updates [full-text search]
- manual populations [full-text search]
- auto populations [full-text search]
- full-text indexes [SQL Server], key column
- full populations [full-text search]
- full-text indexes [SQL Server], populations
ms.assetid: 76767b20-ef55-49ce-8dc4-e77cb8ff618a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9ab93a3514fa260c8c3836da85c767da3c3051a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667006"
---
# <a name="populate-full-text-indexes"></a><span data-ttu-id="6702e-102">Заполнение полнотекстовых индексов</span><span class="sxs-lookup"><span data-stu-id="6702e-102">Populate Full-Text Indexes</span></span>
  <span data-ttu-id="6702e-103">Создание и обслуживание полнотекстового индекса включает процесс *заполнения* индекса (которое также называется *сканированием*).</span><span class="sxs-lookup"><span data-stu-id="6702e-103">Creating and maintaining a full-text index involves populating the index by using a process called a *population* (also known as a *crawl*).</span></span>  
  
##  <a name="types-of-population"></a><a name="types"></a><span data-ttu-id="6702e-104">Типы населения</span><span class="sxs-lookup"><span data-stu-id="6702e-104">Types of Population</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="6702e-105">поддерживает следующие типы заполнения: полное заполнение, автоматическое или ручное заполнение на основе отслеживания изменений и добавочное заполнение на основе меток времени.</span><span class="sxs-lookup"><span data-stu-id="6702e-105">supports the following types of population: full population, change tracking-based automatic or manual population, and incremental timestamp-based population.</span></span>  
  
### <a name="full-population"></a><span data-ttu-id="6702e-106">Полное заполнение</span><span class="sxs-lookup"><span data-stu-id="6702e-106">Full Population</span></span>  
 <span data-ttu-id="6702e-107">Во время полного заполнения индексные записи строятся для всех строк таблицы или индексированного представления.</span><span class="sxs-lookup"><span data-stu-id="6702e-107">During a full population, index entries are built for all the rows of a table or indexed view.</span></span> <span data-ttu-id="6702e-108">Во время полного заполнения полнотекстового индекса индексные записи строятся для всех строк базовой таблицы или индексированного представления.</span><span class="sxs-lookup"><span data-stu-id="6702e-108">A full population of a full-text index, builds index entries for all the rows of the base table or indexed view.</span></span>  
  
 <span data-ttu-id="6702e-109">По умолчанию [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] полностью заполняет новый полнотекстовый индекс сразу после его создания.</span><span class="sxs-lookup"><span data-stu-id="6702e-109">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] populates a new full-text index fully as soon as it is created.</span></span> <span data-ttu-id="6702e-110">Однако полное заполнение может потреблять значительный объем ресурсов.</span><span class="sxs-lookup"><span data-stu-id="6702e-110">However, a full population can consume a significant amount of resources.</span></span> <span data-ttu-id="6702e-111">Поэтому при создании полнотекстовых индексов во время периодов наибольшей потребности в ресурсах часто полезно бывает отложить полное заполнение на период наименьшего потребления ресурсов, особенно если базовая таблица полнотекстового индекса имеет большой размер.</span><span class="sxs-lookup"><span data-stu-id="6702e-111">Therefore, when creating a full-text index during peak periods, it is often a best practice to delay the full population until an off-peak time, particularly if the base table of an full-text index is large.</span></span> <span data-ttu-id="6702e-112">Однако полнотекстовый каталог, к которому относится индекс, нельзя использовать, пока не будут заполнены все его полнотекстовые индексы.</span><span class="sxs-lookup"><span data-stu-id="6702e-112">However, the full-text catalog to which the index belongs is not usable until all of its full-text indexes are populated.</span></span> <span data-ttu-id="6702e-113">Чтобы создать полнотекстовый индекс, но не заполнять его немедленно, укажите в инструкции  CREATE FULLTEXT INDEX предложение CHANGE_TRACKING OFF, NO POPULATION.</span><span class="sxs-lookup"><span data-stu-id="6702e-113">To create a full-text index without populating it immediately, specify the CHANGE_TRACKING OFF, NO POPULATION clause in the CREATE FULLTEXT INDEX statement.</span></span> <span data-ttu-id="6702e-114">Если указан параметр CHANGE_TRACKING MANUAL, то средство полнотекстового поиска использует инструкцию.</span><span class="sxs-lookup"><span data-stu-id="6702e-114">If you specify CHANGE_TRACKING MANUAL, the Full-Text Engine uses statement.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="6702e-115">не заполнит новый полнотекстовый индекс до тех пор, пока не будет выполнена инструкция ALTER FULLTEXT INDEX с предложением запустить полное ЗАПОЛНЕНие или начать ДОБАВОЧное ЗАПОЛНЕНие.</span><span class="sxs-lookup"><span data-stu-id="6702e-115">will not populate the new full-text index until you execute an ALTER FULLTEXT INDEX statement using the START FULL POPULATION or START INCREMENTAL POPULATION clause.</span></span> <span data-ttu-id="6702e-116">Дополнительные сведения см. в примерах «А.</span><span class="sxs-lookup"><span data-stu-id="6702e-116">For more information, see examples "A.</span></span> <span data-ttu-id="6702e-117">Создание полнотекстового индекса без выполнения полного заполнения» и «Б.</span><span class="sxs-lookup"><span data-stu-id="6702e-117">Creating a full-text index without running a full population" and "B.</span></span> <span data-ttu-id="6702e-118">Выполнение полного заполнения в таблице», приведенных далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="6702e-118">Running a full population on table," later in this topic.</span></span>  
  

  
### <a name="change-tracking-based-population"></a><span data-ttu-id="6702e-119">Заполнение на основе отслеживания изменений</span><span class="sxs-lookup"><span data-stu-id="6702e-119">Change Tracking-Based Population</span></span>  
 <span data-ttu-id="6702e-120">Можно также использовать отслеживание изменений для обслуживания полнотекстового индекса после его первоначального полного заполнения.</span><span class="sxs-lookup"><span data-stu-id="6702e-120">Optionally, you can use change tracking to maintain a full-text index after its initial full population.</span></span> <span data-ttu-id="6702e-121">Это вызывает небольшую нагрузку, связанную с отслеживанием изменений, поскольку [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поддерживает таблицу, в которой выполняется отслеживание изменений в базовой таблице со времени последнего заполнения.</span><span class="sxs-lookup"><span data-stu-id="6702e-121">There is a small overhead associated with change tracking because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] maintains a table in which it tracks changes to the base table since the last population.</span></span> <span data-ttu-id="6702e-122">При использовании отслеживания изменений [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поддерживает запись строк базовой таблицы или индексированного представления, измененного операциями обновления, удаления или вставки.</span><span class="sxs-lookup"><span data-stu-id="6702e-122">When change tracking is used, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] maintains a record of the rows in the base table or indexed view that have been modified by updates, deletes, or inserts.</span></span> <span data-ttu-id="6702e-123">Изменения данных, внесенные с помощью инструкций WRITETEXT и UPDATETEXT, не отражаются в полнотекстовом индексе и не отмечаются при отслеживании изменений.</span><span class="sxs-lookup"><span data-stu-id="6702e-123">Data changes through WRITETEXT and UPDATETEXT are not reflected in the full-text index, and are not picked up with change tracking.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6702e-124">Для таблиц, содержащих столбец `timestamp`, можно использовать добавочное заполнение.</span><span class="sxs-lookup"><span data-stu-id="6702e-124">For tables containing a `timestamp` column, you can use incremental populations.</span></span>  
  
 <span data-ttu-id="6702e-125">При включении отслеживания изменений во время создания индекса [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] полностью заполняет новый полнотекстовый индекс сразу же после его создания.</span><span class="sxs-lookup"><span data-stu-id="6702e-125">When change tracking is enabled during index creation, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fully populates the new full-text index immediately after it is created.</span></span> <span data-ttu-id="6702e-126">Таким образом, изменения отслеживаются и распространяются в полнотекстовый индекс.</span><span class="sxs-lookup"><span data-stu-id="6702e-126">Thereafter, changes are tracked and propagated to the full-text index.</span></span> <span data-ttu-id="6702e-127">Отслеживания изменений выполняется двумя способами: автоматически (параметр CHANGE_TRACKING AUTO) и вручную (параметр CHANGE_TRACKING MANUAL).</span><span class="sxs-lookup"><span data-stu-id="6702e-127">There are two types of change tracking, automatic (CHANGE_TRACKING AUTO option) and manual (CHANGE_TRACKING MANUAL option).</span></span> <span data-ttu-id="6702e-128">По умолчанию используется автоматическое отслеживание изменений.</span><span class="sxs-lookup"><span data-stu-id="6702e-128">Automatic change tracking is the default behavior.</span></span>  
  
 <span data-ttu-id="6702e-129">Способ заполнения полнотекстового индекса определяется типом отслеживания изменений.</span><span class="sxs-lookup"><span data-stu-id="6702e-129">The type of change tracking determines how the full-text index is populated, as follows:</span></span>  
  
-   <span data-ttu-id="6702e-130">Автоматическое заполнение</span><span class="sxs-lookup"><span data-stu-id="6702e-130">Automatic population</span></span>  
  
     <span data-ttu-id="6702e-131">По умолчанию (либо если задан параметр CHANGE_TRACKING AUTO) средство полнотекстового поиска использует автоматическое заполнение полнотекстового индекса.</span><span class="sxs-lookup"><span data-stu-id="6702e-131">By default, or if you specify CHANGE_TRACKING AUTO, the Full-Text Engine uses automatic population on the full-text index.</span></span> <span data-ttu-id="6702e-132">После завершения первоначального полного заполнения изменения отслеживаются по мере изменений данных в базовой таблице, а зарегистрированные изменения распространяются автоматически.</span><span class="sxs-lookup"><span data-stu-id="6702e-132">After the initial full population completes, changes are tracked as data is modified in the base table, and the tracked changes are propagated automatically.</span></span> <span data-ttu-id="6702e-133">Полнотекстовый индекс обновляется в режиме вне сети, однако изменения, распространяемые таким образом, могут не отражаться в индексе сразу.</span><span class="sxs-lookup"><span data-stu-id="6702e-133">The full-text index is updated in the background, however, so propagated changes might not be reflected immediately in the index.</span></span>  
  
     <span data-ttu-id="6702e-134">**Настройка отслеживания изменений с автоматическим заполнением**</span><span class="sxs-lookup"><span data-stu-id="6702e-134">**To set up tracking changes with automatic population**</span></span>  
  
    -   <span data-ttu-id="6702e-135">[CREATE FULLTEXT INDEX](/sql/t-sql/statements/create-fulltext-index-transact-sql) ... WITH CHANGE_TRACKING AUTO</span><span class="sxs-lookup"><span data-stu-id="6702e-135">[CREATE FULLTEXT INDEX](/sql/t-sql/statements/create-fulltext-index-transact-sql) ... WITH CHANGE_TRACKING AUTO</span></span>  
  
    -   <span data-ttu-id="6702e-136">[ALTER FULLTEXT INDEX](/sql/t-sql/statements/alter-fulltext-index-transact-sql) ... SET CHANGE_TRACKING AUTO</span><span class="sxs-lookup"><span data-stu-id="6702e-136">[ALTER FULLTEXT INDEX](/sql/t-sql/statements/alter-fulltext-index-transact-sql) ... SET CHANGE_TRACKING AUTO</span></span>  
  
     <span data-ttu-id="6702e-137">Дополнительные сведения см. в примере «Д.</span><span class="sxs-lookup"><span data-stu-id="6702e-137">For more information, see example "E.</span></span> <span data-ttu-id="6702e-138">Переключение полнотекстового индекса на автоматическое отслеживание изменений» далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="6702e-138">Altering a full-text index to use automatic change tracking," later in this topic.</span></span>  
  
-   <span data-ttu-id="6702e-139">Заполнение вручную</span><span class="sxs-lookup"><span data-stu-id="6702e-139">Manual population</span></span>  
  
     <span data-ttu-id="6702e-140">Если задан параметр CHANGE_TRACKING MANUAL, то средство полнотекстового поиска использует заполнение полнотекстового индекса вручную.</span><span class="sxs-lookup"><span data-stu-id="6702e-140">If you specify CHANGE_TRACKING MANUAL, the Full-Text Engine uses manual population on the full-text index.</span></span> <span data-ttu-id="6702e-141">После завершения первоначального полного заполнения изменения отслеживаются по мере изменения данных в базовой таблице.</span><span class="sxs-lookup"><span data-stu-id="6702e-141">After the initial full population completes, changes are tracked as data is modified in the base table.</span></span> <span data-ttu-id="6702e-142">Но изменения не добавляются в полнотекстовый индекс, пока не будет выполнена инструкция ALTER FULLTEXT INDEX … START UPDATE POPULATION .</span><span class="sxs-lookup"><span data-stu-id="6702e-142">However, they are not propagated to the full-text index until you execute an ALTER FULLTEXT INDEX ... START UPDATE POPULATION statement.</span></span> <span data-ttu-id="6702e-143">Агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] можно использовать для периодического вызова инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6702e-143">You can use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to call this [!INCLUDE[tsql](../../includes/tsql-md.md)] statement periodically.</span></span>  
  
     <span data-ttu-id="6702e-144">**Запуск отслеживания изменений с заполнением вручную**</span><span class="sxs-lookup"><span data-stu-id="6702e-144">**To start tracking changes with manual population**</span></span>  
  
    -   <span data-ttu-id="6702e-145">[CREATE FULLTEXT INDEX](/sql/t-sql/statements/create-fulltext-index-transact-sql) ... WITH CHANGE_TRACKING MANUAL</span><span class="sxs-lookup"><span data-stu-id="6702e-145">[CREATE FULLTEXT INDEX](/sql/t-sql/statements/create-fulltext-index-transact-sql) ... WITH CHANGE_TRACKING MANUAL</span></span>  
  
    -   <span data-ttu-id="6702e-146">[ALTER FULLTEXT INDEX](/sql/t-sql/statements/alter-fulltext-index-transact-sql) ... SET CHANGE_TRACKING MANUAL</span><span class="sxs-lookup"><span data-stu-id="6702e-146">[ALTER FULLTEXT INDEX](/sql/t-sql/statements/alter-fulltext-index-transact-sql) ... SET CHANGE_TRACKING MANUAL</span></span>  
  
     <span data-ttu-id="6702e-147">Дополнительные сведения см. в примерах «В.</span><span class="sxs-lookup"><span data-stu-id="6702e-147">For more information, see examples "C.</span></span> <span data-ttu-id="6702e-148">Создание полнотекстового индекса с отслеживанием изменений вручную» и «Г.</span><span class="sxs-lookup"><span data-stu-id="6702e-148">Creating a full-text index with manual change tracking" and "D.</span></span> <span data-ttu-id="6702e-149">Выполнение заполнения вручную» далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="6702e-149">Running a manual population," later in this topic.</span></span>  
  
 <span data-ttu-id="6702e-150">**Отключение отслеживания изменений**</span><span class="sxs-lookup"><span data-stu-id="6702e-150">**To turn off change tracking**</span></span>  
  
-   <span data-ttu-id="6702e-151">[CREATE FULLTEXT INDEX](/sql/t-sql/statements/create-fulltext-index-transact-sql) ... WITH CHANGE_TRACKING OFF</span><span class="sxs-lookup"><span data-stu-id="6702e-151">[CREATE FULLTEXT INDEX](/sql/t-sql/statements/create-fulltext-index-transact-sql) ... WITH CHANGE_TRACKING OFF</span></span>  
  
-   <span data-ttu-id="6702e-152">[ALTER FULLTEXT INDEX](/sql/t-sql/statements/alter-fulltext-index-transact-sql) ... SET CHANGE_TRACKING OFF</span><span class="sxs-lookup"><span data-stu-id="6702e-152">[ALTER FULLTEXT INDEX](/sql/t-sql/statements/alter-fulltext-index-transact-sql) ... SET CHANGE_TRACKING OFF</span></span>  
  

  
### <a name="incremental-timestamp-based-population"></a><span data-ttu-id="6702e-153">Добавочное заполнение с использованием отметок времени</span><span class="sxs-lookup"><span data-stu-id="6702e-153">Incremental Timestamp-Based Population</span></span>  
 <span data-ttu-id="6702e-154">Добавочное заполнение является альтернативным механизмом по отношению к заполнению полнотекстового индекса вручную.</span><span class="sxs-lookup"><span data-stu-id="6702e-154">An incremental population is an alternative mechanism for manually populating a full-text index.</span></span> <span data-ttu-id="6702e-155">Можно запустить добавочное заполнение для полнотекстового индекса, у которого параметру CHANGE_TRACKING присвоено значение MANUAL или OFF.</span><span class="sxs-lookup"><span data-stu-id="6702e-155">You can run an incremental population for a full-text index that has CHANGE_TRACKING set to MANUAL or OFF.</span></span> <span data-ttu-id="6702e-156">Если первое заполнение полнотекстового индекса является добавочным, то производится индексирование всех строк, что является эквивалентом полного заполнения.</span><span class="sxs-lookup"><span data-stu-id="6702e-156">If the first population on a full-text index is an incremental population, it indexes all rows, making it equivalent to a full population.</span></span>  
  
 <span data-ttu-id="6702e-157">Для выполнения добавочного заполнения проиндексированная таблица должна включать столбец типа `timestamp`.</span><span class="sxs-lookup"><span data-stu-id="6702e-157">The requirement for incremental population is that the indexed table must have a column of the `timestamp` data type.</span></span> <span data-ttu-id="6702e-158">Если столбца типа `timestamp` в таблице нет, добавочное заполнение невозможно.</span><span class="sxs-lookup"><span data-stu-id="6702e-158">If a `timestamp` column does not exist, incremental population cannot be performed.</span></span> <span data-ttu-id="6702e-159">Попытка выполнить добавочное заполнение для таблицы, не содержащей столбец типа `timestamp`, приведет к полному заполнению.</span><span class="sxs-lookup"><span data-stu-id="6702e-159">A request for incremental population on a table without a `timestamp` column results in a full population operation.</span></span> <span data-ttu-id="6702e-160">Кроме того, если за время, прошедшее с момента последнего заполнения, изменились какие-либо метаданные, влияющие на полнотекстовый индекс таблицы, то запросы добавочного заполнения реализуются как полное заполнение.</span><span class="sxs-lookup"><span data-stu-id="6702e-160">Also, if any metadata that affects the full-text index for the table has changed since the last population, incremental population requests are implemented as full populations.</span></span> <span data-ttu-id="6702e-161">Сюда относятся и изменения в метаданных, вызванные изменениями в определениях любых столбцов, индексов или полнотекстовых индексов.</span><span class="sxs-lookup"><span data-stu-id="6702e-161">This includes metadata changes caused by altering any column, index, or full-text index definitions.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6702e-162">определяет строки, которые изменились со времени последнего заполнения, с помощью столбца `timestamp`.</span><span class="sxs-lookup"><span data-stu-id="6702e-162">uses the `timestamp` column to identify rows that have changed since the last population.</span></span> <span data-ttu-id="6702e-163">Затем операция добавочного заполнения обновляет полнотекстовый индекс для строк, добавленных, удаленных или измененных после или во время последнего заполнения.</span><span class="sxs-lookup"><span data-stu-id="6702e-163">The incremental population then updates the full-text index for rows added, deleted, or modified after the last population, or while the last population was in progress.</span></span> <span data-ttu-id="6702e-164">Если выполняется большое количество операций вставки в таблицу, то использование добавочного заполнения может быть более эффективным, чем использование заполнения вручную.</span><span class="sxs-lookup"><span data-stu-id="6702e-164">If a table experiences a high volume of inserts, using incremental population can be more efficient that using manual population.</span></span>  
  
 <span data-ttu-id="6702e-165">По окончании заполнения служба полнотекстового поиска сохраняет новое значение `timestamp`.</span><span class="sxs-lookup"><span data-stu-id="6702e-165">At the end of a population, the Full-Text Engine records a new `timestamp` value.</span></span> <span data-ttu-id="6702e-166">Это значение — самое большое значение `timestamp`, которое встретилось средству сбора данных SQL.</span><span class="sxs-lookup"><span data-stu-id="6702e-166">This value is the largest `timestamp` value that SQL Gatherer has encountered.</span></span> <span data-ttu-id="6702e-167">Это значение будет использовано в начале последующего добавочного заполнения.</span><span class="sxs-lookup"><span data-stu-id="6702e-167">This value will be used when a subsequent incremental population starts.</span></span>  
  
 <span data-ttu-id="6702e-168">Для запуска добавочного заполнения выполните инструкцию ALTER FULLTEXT INDEX с использованием предложения START INCREMENTAL POPULATION.</span><span class="sxs-lookup"><span data-stu-id="6702e-168">To run an incremental population, execute an ALTER FULLTEXT INDEX statement using the START INCREMENTAL POPULATION clause.</span></span>  
  

  
##  <a name="examples-of-populating-full-text-indexes"></a><a name="examples"></a><span data-ttu-id="6702e-169">Примеры заполнения полнотекстовых индексов</span><span class="sxs-lookup"><span data-stu-id="6702e-169">Examples of Populating Full-Text Indexes</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6702e-170">В примерах этого раздела используется таблица `Production.Document` или `HumanResources.JobCandidate` образца базы данных `AdventureWorks` .</span><span class="sxs-lookup"><span data-stu-id="6702e-170">The examples in this section use the `Production.Document` or `HumanResources.JobCandidate` table of the `AdventureWorks` sample database.</span></span>  
  
### <a name="a-creating-a-full-text-index-without-running-a-full-population"></a><span data-ttu-id="6702e-171">A.</span><span class="sxs-lookup"><span data-stu-id="6702e-171">A.</span></span> <span data-ttu-id="6702e-172">Создание полнотекстового индекса без выполнения полного заполнения</span><span class="sxs-lookup"><span data-stu-id="6702e-172">Creating a full-text index without running a full population</span></span>  
 <span data-ttu-id="6702e-173">В следующем примере создается полнотекстовый индекс для таблицы `Production.Document` образца базы данных `AdventureWorks` .</span><span class="sxs-lookup"><span data-stu-id="6702e-173">The following example creates a full-text index on the `Production.Document` table of the `AdventureWorks` sample database.</span></span> <span data-ttu-id="6702e-174">В этом примере используется параметр WITH CHANGE_TRACKING OFF, NO POPULATION для задержки первоначального полного заполнения.</span><span class="sxs-lookup"><span data-stu-id="6702e-174">This example uses WITH CHANGE_TRACKING OFF, NO POPULATION to delay the initial full population.</span></span>  
  
```  
CREATE UNIQUE INDEX ui_ukDoc ON Production.Document(DocumentID);  
CREATE FULLTEXT CATALOG AW_Production_FTCat;  
CREATE FULLTEXT INDEX ON Production.Document  
(  
    Document                         --Full-text index column name   
        TYPE COLUMN FileExtension    --Name of column that contains file type information  
        Language 1033                 --1033 is LCID for the English language  
)  
    KEY INDEX ui_ukDoc  
    ON AW_Production_FTCat  
    WITH CHANGE_TRACKING OFF, NO POPULATION;  
GO  
  
```  
  
### <a name="b-running-a-full-population-on-table"></a><span data-ttu-id="6702e-175">Б.</span><span class="sxs-lookup"><span data-stu-id="6702e-175">B.</span></span> <span data-ttu-id="6702e-176">Выполнение полного заполнения в таблице</span><span class="sxs-lookup"><span data-stu-id="6702e-176">Running a full population on table</span></span>  
 <span data-ttu-id="6702e-177">В следующем примере полное заполнение выполняется в таблице `Production.Document` образца базы данных `AdventureWorks` .</span><span class="sxs-lookup"><span data-stu-id="6702e-177">The following example runs a full population on the `Production.Document` table of the `AdventureWorks` sample database.</span></span>  
  
```  
ALTER FULLTEXT INDEX ON Production.Document  
   START FULL POPULATION;  
```  
  
### <a name="c-creating-a-full-text-index-with-manual-change-tracking"></a><span data-ttu-id="6702e-178">В.</span><span class="sxs-lookup"><span data-stu-id="6702e-178">C.</span></span> <span data-ttu-id="6702e-179">Создание полнотекстового индекса с отслеживанием изменений вручную</span><span class="sxs-lookup"><span data-stu-id="6702e-179">Creating a full-text index with manual change tracking</span></span>  
 <span data-ttu-id="6702e-180">В следующем примере создается полнотекстовый индекс, который будет использовать отслеживание изменений с заполнением вручную в таблице `HumanResources.JobCandidate` образца базы данных `AdventureWorks` .</span><span class="sxs-lookup"><span data-stu-id="6702e-180">The following example creates a full-text index that will use change tracking with manual population on the `HumanResources.JobCandidate` table of the `AdventureWorks` sample database.</span></span>  
  
```  
USE AdventureWorks;  
GO  
CREATE UNIQUE INDEX ui_ukJobCand ON HumanResources.JobCandidate(JobCandidateID);  
CREATE FULLTEXT CATALOG ft AS DEFAULT;  
CREATE FULLTEXT INDEX ON HumanResources.JobCandidate(Resume)   
   KEY INDEX ui_ukJobCand   
   WITH CHANGE_TRACKING=MANUAL;  
GO  
```  
  
### <a name="d-running-a-manual-population"></a><span data-ttu-id="6702e-181">Г.</span><span class="sxs-lookup"><span data-stu-id="6702e-181">D.</span></span> <span data-ttu-id="6702e-182">Выполнение заполнения вручную</span><span class="sxs-lookup"><span data-stu-id="6702e-182">Running a manual population</span></span>  
 <span data-ttu-id="6702e-183">В следующем примере выполняется заполнение вручную на полнотекстовом индексе с отслеживанием изменений для таблицы `HumanResources.JobCandidate` образца базы данных `AdventureWorks` .</span><span class="sxs-lookup"><span data-stu-id="6702e-183">The following example runs a manual population on the change-tracked full-text index of the `HumanResources.JobCandidate` table of the `AdventureWorks` sample database.</span></span>  
  
```  
USE AdventureWorks;  
GO  
ALTER FULLTEXT INDEX ON HumanResources.JobCandidate START UPDATE POPULATION;  
GO  
```  
  
### <a name="e-altering-a-full-text-index-to-use-automatic-change-tracking"></a><span data-ttu-id="6702e-184">Д.</span><span class="sxs-lookup"><span data-stu-id="6702e-184">E.</span></span> <span data-ttu-id="6702e-185">Переключение полнотекстового индекса на автоматическое отслеживание изменений</span><span class="sxs-lookup"><span data-stu-id="6702e-185">Altering a full-text index to use automatic change tracking</span></span>  
 <span data-ttu-id="6702e-186">В следующем примере полнотекстовый индекс таблицы `HumanResources.JobCandidate` образца базы данных `AdventureWorks` переключается на отслеживание изменений с автоматическим заполнением.</span><span class="sxs-lookup"><span data-stu-id="6702e-186">The following example changes the full-text index of the `HumanResources.JobCandidate` table of the `AdventureWorks` sample database to use change tracking with automatic population.</span></span>  
  
```  
USE AdventureWorks;  
GO  
ALTER FULLTEXT INDEX ON HumanResources.JobCandidate SET CHANGE_TRACKING AUTO;  
GO   
```  
  

  
##  <a name="creating-or-changing-a-schedule-for-incremental-population"></a><a name="create"></a><span data-ttu-id="6702e-187">Создание или изменение расписания для добавочного заполнения</span><span class="sxs-lookup"><span data-stu-id="6702e-187">Creating or Changing a Schedule for Incremental Population</span></span>  
  
#### <a name="to-create-or-change-a-schedule-for-incremental-population-in-management-studio"></a><span data-ttu-id="6702e-188">Создание или изменение расписания добавочных заполнений в Management Studio</span><span class="sxs-lookup"><span data-stu-id="6702e-188">To create or change a schedule for incremental population in Management Studio</span></span>  
  
1.  <span data-ttu-id="6702e-189">В обозревателе объектов разверните узел сервера.</span><span class="sxs-lookup"><span data-stu-id="6702e-189">In Object Explorer, expand the server.</span></span>  
  
2.  <span data-ttu-id="6702e-190">Разверните узел **Базы данных**, а затем базу данных, которая содержит полнотекстовый индекс.</span><span class="sxs-lookup"><span data-stu-id="6702e-190">Expand **Databases**, and then expand the database that contains the full-text index.</span></span>  
  
3.  <span data-ttu-id="6702e-191">Раскройте узел **Таблицы**.</span><span class="sxs-lookup"><span data-stu-id="6702e-191">Expand **Tables**.</span></span>  
  
 <span data-ttu-id="6702e-192">Правой кнопкой мыши щелкните таблицу, в которой определен полнотекстовый индекс, выберите **Полнотекстовый индекс**, затем в контекстном меню **Полнотекстовый индекс** выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="6702e-192">Right-click the table on which the full-text index is defined, select **Full-Text index**, and on the **Full-Text index** context menu, click **Properties**.</span></span> <span data-ttu-id="6702e-193">Откроется диалоговое окно **Свойства полнотекстового индекса** .</span><span class="sxs-lookup"><span data-stu-id="6702e-193">This opens the **Full-text index Properties** dialog box.</span></span>  
  
1.  <span data-ttu-id="6702e-194">На панели **Выбор страницы** выберите пункт расписания.</span><span class="sxs-lookup"><span data-stu-id="6702e-194">In the **Select a page** pane, select Schedules.</span></span>  
  
     <span data-ttu-id="6702e-195">Эта страница используется для создания расписания задания агента SQL Server, которое запускает добавочное заполнение базовой таблицы или индексированного представления полнотекстового индекса, а также для управления таким расписанием.</span><span class="sxs-lookup"><span data-stu-id="6702e-195">Use this page to create or manage schedules for a SQL Server Agent job that starts an incremental table population on the base table or indexed view of the full-text index.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="6702e-196">Если базовая таблица или представление не содержат столбец типа данных `timestamp`, то выполняется полное заполнение.</span><span class="sxs-lookup"><span data-stu-id="6702e-196">If the base table or view does not contain a column of the `timestamp` data type, a full population is performed.</span></span>  
  
     <span data-ttu-id="6702e-197">Существуют следующие варианты выбора.</span><span class="sxs-lookup"><span data-stu-id="6702e-197">The options are as follows:</span></span>  
  
    -   <span data-ttu-id="6702e-198">Чтобы создать новое расписание, щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="6702e-198">To create a new schedule, click **New**.</span></span>  
  
         <span data-ttu-id="6702e-199">Откроется диалоговое окно **Создание расписания полнотекстового индексирования таблицы** , в котором можно создать расписание.</span><span class="sxs-lookup"><span data-stu-id="6702e-199">This opens the **New Full-Text Indexing Table Schedule** dialog box, where you can create a schedule.</span></span> <span data-ttu-id="6702e-200">Чтобы сохранить расписание, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6702e-200">To save the schedule, click **OK**.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="6702e-201">Задание агента SQL Server (запуск добавочного заполнения таблицы на *имя_базы_данных*.*имя_таблицы*) связывается с новым расписанием после выхода из диалогового окна **Свойства полнотекстового индекса** .</span><span class="sxs-lookup"><span data-stu-id="6702e-201">A SQL Server Agent job (Start Incremental Table Population on *database_name*.*table_name*) is associated with a new schedule after you exit the **Full-Text Index Properties** dialog box.</span></span> <span data-ttu-id="6702e-202">Если создается несколько расписаний для полнотекстового индекса, то все они используют одно и то же задание.</span><span class="sxs-lookup"><span data-stu-id="6702e-202">If you create multiple schedules for the full-text index, they all use the same job.</span></span>  
  
    -   <span data-ttu-id="6702e-203">Чтобы изменить расписание, выделите его и нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="6702e-203">To change a schedule, select it and click **Edit**.</span></span>  
  
         <span data-ttu-id="6702e-204">Откроется диалоговое окно **Создание расписания полнотекстового индексирования таблицы** , в котором можно изменить расписание.</span><span class="sxs-lookup"><span data-stu-id="6702e-204">This opens the **New Full-Text Indexing Table Schedule** dialog box, where you can modify the schedule.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="6702e-205">Сведения об изменении задания см. в статье [Изменение задания](../../ssms/agent/modify-a-job.md).</span><span class="sxs-lookup"><span data-stu-id="6702e-205">For information about modifying a job, see [Modify a Job](../../ssms/agent/modify-a-job.md).</span></span>  
  
    -   <span data-ttu-id="6702e-206">Чтобы удалить расписание, выделите его и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="6702e-206">To remove a schedule, select it and click **Delete**.</span></span>  
  
2.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  

  
##  <a name="troubleshooting-errors-in-a-full-text-population-crawl"></a><a name="crawl"></a><span data-ttu-id="6702e-207">Устранение ошибок полнотекстового заполнения (сканирование)</span><span class="sxs-lookup"><span data-stu-id="6702e-207">Troubleshooting Errors in a Full-Text Population (Crawl)</span></span>  
 <span data-ttu-id="6702e-208">При возникновении ошибки во время сканирования модуль протоколирования сканирования, входящий в механизм полнотекстового поиска, создает и обновляет журнал сканирования, хранящийся в текстовом файле.</span><span class="sxs-lookup"><span data-stu-id="6702e-208">When an error occurs during a crawl, the Full-Text Search crawl logging facility creates and maintains a crawl log, which is a plain text file.</span></span> <span data-ttu-id="6702e-209">Каждый журнал сканирования соответствует конкретному полнотекстовому каталогу.</span><span class="sxs-lookup"><span data-stu-id="6702e-209">Each crawl log corresponds to a particular full-text catalog.</span></span> <span data-ttu-id="6702e-210">По умолчанию журналы сканирования, соответствующие конкретному экземпляру — в данном случае первому экземпляру, — располагаются в папке «%ProgramFiles%\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\LOG».</span><span class="sxs-lookup"><span data-stu-id="6702e-210">By default crawl logs for a given instance, in this case, the first instance, are located in %ProgramFiles%\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\LOG folder.</span></span> <span data-ttu-id="6702e-211">Имена файлов журналов сканирования имеют следующий формат.</span><span class="sxs-lookup"><span data-stu-id="6702e-211">The crawl log file follows the following naming scheme:</span></span>  
  
 <span data-ttu-id="6702e-212">SQLFT \<DatabaseID> \<FullTextCatalogID> . LOG [ \<n> ]</span><span class="sxs-lookup"><span data-stu-id="6702e-212">SQLFT\<DatabaseID>\<FullTextCatalogID>.LOG[\<n>]</span></span>  
  
 <`DatabaseID`>  
 <span data-ttu-id="6702e-213">Идентификатор базы данных.</span><span class="sxs-lookup"><span data-stu-id="6702e-213">The ID of a database.</span></span><span data-ttu-id="6702e-214"> <`dbid`> — это пять цифр с нулем в начале.</span><span class="sxs-lookup"><span data-stu-id="6702e-214"> <`dbid`> is a five digit number with leading zeros.</span></span>  
  
 <`FullTextCatalogID`>  
 <span data-ttu-id="6702e-215">Идентификатор полнотекстового каталога.</span><span class="sxs-lookup"><span data-stu-id="6702e-215">Full-text catalog ID.</span></span><span data-ttu-id="6702e-216"> <`catid`> — это пять цифр с нулем в начале.</span><span class="sxs-lookup"><span data-stu-id="6702e-216"> <`catid`> is a five digit number with leading zeros.</span></span>  
  
 <`n`>  
 <span data-ttu-id="6702e-217">Целое число, свидетельствующее о существовании одного или нескольких журналов сканирования одного полнотекстового каталога.</span><span class="sxs-lookup"><span data-stu-id="6702e-217">Is an integer that indicates one or more crawl logs of the same full-text catalog exist.</span></span>  
  
 <span data-ttu-id="6702e-218">Например, SQLFT0000500008.2 является файлом журнала сканирования для базы данных с идентификатором базы данных 5 и идентификатором полнотекстового каталога 8.</span><span class="sxs-lookup"><span data-stu-id="6702e-218">For example, SQLFT0000500008.2 is the crawl log file for a database with database ID = 5, and full-text catalog ID = 8.</span></span> <span data-ttu-id="6702e-219">Двойка в конце имени файла показывает, что этой паре базы данных и каталога соответствуют два файла журналов сканирования.</span><span class="sxs-lookup"><span data-stu-id="6702e-219">The 2 at the end of the file name indicates that there are two crawl log files for this database/catalog pair.</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="6702e-220">См. также:</span><span class="sxs-lookup"><span data-stu-id="6702e-220">See Also</span></span>  
 <span data-ttu-id="6702e-221">[sys.dm_fts_index_population (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-index-population-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6702e-221">[sys.dm_fts_index_population &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-index-population-transact-sql) </span></span>  
 <span data-ttu-id="6702e-222">[Приступая к работе с компонентом Full-Text Search](get-started-with-full-text-search.md) </span><span class="sxs-lookup"><span data-stu-id="6702e-222">[Get Started with Full-Text Search](get-started-with-full-text-search.md) </span></span>  
 <span data-ttu-id="6702e-223">[Создание и управление полнотекстовыми индексами](create-and-manage-full-text-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="6702e-223">[Create and Manage Full-Text Indexes](create-and-manage-full-text-indexes.md) </span></span>  
 <span data-ttu-id="6702e-224">[CREATE FULLTEXT INDEX (Transact-SQL)](/sql/t-sql/statements/create-fulltext-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6702e-224">[CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql) </span></span>  
 [<span data-ttu-id="6702e-225">ALTER FULLTEXT INDEX (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="6702e-225">ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-fulltext-index-transact-sql)  
  
  
