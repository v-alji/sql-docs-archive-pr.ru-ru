---
title: Использование мастера полнотекстового индексирования | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextindexingwizard.selecttablecolumns.f1
- sql12.swb.fulltextindexingwizard.welcome.f1
- sql12.swb.fulltextindexingwizard.selectacatalog.f1
- sql12.swb.fulltextindexingwizard.progress.f1
- sql12.swb.fulltextindexingwizard.selectorcreatepopschedules.f1
- sql12.swb.fulltextindexingwizard.selectatableorview.f1
- sql12.swb.fulltextindexingwizard.selectchangetracking.f1
- sql12.swb.fulltextindexingwizard.selectanindex.f1
- sql12.swb.fulltextindexingwizard.summary.f1
helpviewer_keywords:
- Full-Text Indexing Wizard
- full-text search [SQL Server], Full-Text Indexing Wizard
ms.assetid: 3e9d9605-6525-4781-9168-fdaa06db3459
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5ef8a23c4d85cbe47bf6bdb47eb3f45723f1559d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730421"
---
# <a name="use-the-full-text-indexing-wizard"></a><span data-ttu-id="291f1-102">Использование мастера полнотекстового индексирования</span><span class="sxs-lookup"><span data-stu-id="291f1-102">Use the Full-Text Indexing Wizard</span></span>
  <span data-ttu-id="291f1-103">Мастер полнотекстового индексирования поможет выполнить ряд шагов, спланированных для создания полнотекстового индекса.</span><span class="sxs-lookup"><span data-stu-id="291f1-103">The Full-Text Indexing Wizard walks you through a series of steps designed to help you create a full-text index.</span></span>  
  
#### <a name="to-use-the-full-text-indexing-wizard"></a><span data-ttu-id="291f1-104">Использование мастера полнотекстового индексирования</span><span class="sxs-lookup"><span data-stu-id="291f1-104">To use the Full-Text Indexing wizard</span></span>  
  
1.  <span data-ttu-id="291f1-105">В обозревателе объектов щелкните правой кнопкой мыши таблицу, для которой необходимо создать полнотекстовый индекс, укажите **Полнотекстовый индекс**и щелкните **Определить полнотекстовый индекс**.</span><span class="sxs-lookup"><span data-stu-id="291f1-105">In Object Explorer, right-click the table on which you want to create a full-text index, point to **Full-Text index**, and then click **Define Full-Text Index**.</span></span>  
  
     <span data-ttu-id="291f1-106">**Уникальный индекс**</span><span class="sxs-lookup"><span data-stu-id="291f1-106">**Unique Index**</span></span>  
     <span data-ttu-id="291f1-107">Выберите индекс из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="291f1-107">Select an index from the drop down list.</span></span> <span data-ttu-id="291f1-108">Индекс должен иметь один ключевой столбец, быть уникальным и не допускающим значения NULL.</span><span class="sxs-lookup"><span data-stu-id="291f1-108">The index must be a single-key-column, unique, non-nullable index.</span></span> <span data-ttu-id="291f1-109">Выбрать минимально возможный индекс ключа для полнотекстового уникального ключа.</span><span class="sxs-lookup"><span data-stu-id="291f1-109">Select the smallest unique key index for the full-text unique key.</span></span> <span data-ttu-id="291f1-110">Для улучшения производительности рекомендуется использовать кластеризованный индекс.</span><span class="sxs-lookup"><span data-stu-id="291f1-110">For best performance, a clustered index is recommended.</span></span>  
  
     <span data-ttu-id="291f1-111">**Доступные столбцы**</span><span class="sxs-lookup"><span data-stu-id="291f1-111">**Available Columns**</span></span>  
     <span data-ttu-id="291f1-112">Чтобы включить столбец в индекс, установите флажок напротив имени столбца.</span><span class="sxs-lookup"><span data-stu-id="291f1-112">To include a column in the index, select the check box next to the column name.</span></span> <span data-ttu-id="291f1-113">Столбцы, не подлежащие полнотекстовому индексированию, отображаются серым цветом, а соответствующие им флажки отключаются.</span><span class="sxs-lookup"><span data-stu-id="291f1-113">Columns that are not eligible for full-text indexing appear in grey with their check boxes disabled.</span></span>  
  
     <span data-ttu-id="291f1-114">**Язык для средства разбиения по словам**</span><span class="sxs-lookup"><span data-stu-id="291f1-114">**Language for Word Breaker**</span></span>  
     <span data-ttu-id="291f1-115">Выберите язык из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="291f1-115">Select a language from the drop-down list.</span></span> <span data-ttu-id="291f1-116">Выбранный язык будет использоваться [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для идентификации правильных средств разбиения по словам для индекса.</span><span class="sxs-lookup"><span data-stu-id="291f1-116">This choice will be used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to identify the correct word breakers for the index.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="291f1-117">использует средства разбиения по словам для определения границ слов в данных, подвергаемых полнотекстовому индексированию.</span><span class="sxs-lookup"><span data-stu-id="291f1-117">uses word breakers to identify word boundaries in the full-text indexed data.</span></span>  
  
     <span data-ttu-id="291f1-118">**Столбец типа**</span><span class="sxs-lookup"><span data-stu-id="291f1-118">**Type Column**</span></span>  
     <span data-ttu-id="291f1-119">Выберите имя столбца, содержащего тип документа столбца, подвергаемого полнотекстовому индексированию.</span><span class="sxs-lookup"><span data-stu-id="291f1-119">Select the name of the column that holds the document type of column being full-text indexed.</span></span>  
  
     <span data-ttu-id="291f1-120">**Столбец Type** доступен только в том случае, если столбец, указанный в столбце **Доступные столбцы** , имеет `varbinary(max)` тип `image` или.</span><span class="sxs-lookup"><span data-stu-id="291f1-120">The  **Type Column** is only enabled when the column named in the **Available Columns** column is of type `varbinary(max)` or `image`.</span></span>  
  
     <span data-ttu-id="291f1-121">**Статистическая семантика**</span><span class="sxs-lookup"><span data-stu-id="291f1-121">**Statistical Semantics**</span></span>  
     <span data-ttu-id="291f1-122">Укажите, следует ли включить статистическое семантическое индексирование для выбранного столбца.</span><span class="sxs-lookup"><span data-stu-id="291f1-122">Select whether to enable semantic indexing for the selected column.</span></span> <span data-ttu-id="291f1-123">Дополнительные сведения см. в разделе [Семантический поиск (SQL Server)](semantic-search-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="291f1-123">For more information, see [Semantic Search &#40;SQL Server&#41;](semantic-search-sql-server.md).</span></span>  
  
     <span data-ttu-id="291f1-124">Если **Язык** выбран до выбора режима **Статистическая семантика**и выбранный язык не имеет связанной семантической модели языка, флажок **Статистическая семантика** будет недоступным.</span><span class="sxs-lookup"><span data-stu-id="291f1-124">If you select a **Language** prior to selecting **Statistical Semantics**, and the selected language does not have an associated Semantic Language Model, then the **Statistical Semantics** checkbox is disabled.</span></span> <span data-ttu-id="291f1-125">Если режим **Статистическая семантика** выбран до выбора **Языка**, в раскрывающемся поле со списком будут доступны только языки, имеющие семантическую модель языка.</span><span class="sxs-lookup"><span data-stu-id="291f1-125">If you select **Statistical Semantics** prior to selecting a **Language**, the languages available in the drop-down combo box will be restricted to those for which there is Semantic Language Model support.</span></span>  
  
2.  <span data-ttu-id="291f1-126">Выбор параметров отслеживания изменений.</span><span class="sxs-lookup"><span data-stu-id="291f1-126">Select the change tracking options.</span></span>  
  
     <span data-ttu-id="291f1-127">**Автоматически**</span><span class="sxs-lookup"><span data-stu-id="291f1-127">**Automatically**</span></span>  
     <span data-ttu-id="291f1-128">Выберите этот переключатель, чтобы обновление полнотекстового индекса осуществлялось автоматически по мере внесения изменений в базовые данные.</span><span class="sxs-lookup"><span data-stu-id="291f1-128">Select this radio button to have the full-text index updated automatically as changes occur to the underlying data.</span></span>  
  
     <span data-ttu-id="291f1-129">**Необходимости**</span><span class="sxs-lookup"><span data-stu-id="291f1-129">**Manually**</span></span>  
     <span data-ttu-id="291f1-130">Выберите этот переключатель, если не нужно, чтобы обновление полнотекстового индекса осуществлялось автоматически по мере внесения изменений в базовые данные.</span><span class="sxs-lookup"><span data-stu-id="291f1-130">Select this radio button if you do not want the full-text index to be updated automatically as changes occur to the underlying data.</span></span> <span data-ttu-id="291f1-131">Изменения, внесенные в базовые данные, сохраняются.</span><span class="sxs-lookup"><span data-stu-id="291f1-131">Changes to the underlying data are maintained.</span></span> <span data-ttu-id="291f1-132">Однако, чтобы применить изменения к полнотекстовому индексу, необходимо запустить или запланировать запуск этого процесса вручную.</span><span class="sxs-lookup"><span data-stu-id="291f1-132">However, to apply the changes to the full-text index you must start or schedule this process manually.</span></span>  
  
     <span data-ttu-id="291f1-133">**Не отслеживать изменения**</span><span class="sxs-lookup"><span data-stu-id="291f1-133">**Do not track changes**</span></span>  
     <span data-ttu-id="291f1-134">Выберите этот переключатель, если не нужно, чтобы полнотекстовый индекс обновлялся в соответствии с изменениями, внесенными в базовые данные.</span><span class="sxs-lookup"><span data-stu-id="291f1-134">Select this radio button if you do not want the full-text index to be updated with changes to the underlying data.</span></span>  
  
     <span data-ttu-id="291f1-135">**Начать полное заполнение индекса сразу после его создания**</span><span class="sxs-lookup"><span data-stu-id="291f1-135">**Start full population when index is created**</span></span>  
     <span data-ttu-id="291f1-136">Выберите этот переключатель, чтобы запустить полное заполнение после успешного завершения работы мастера.</span><span class="sxs-lookup"><span data-stu-id="291f1-136">Select this radio button to kick off a full population at the successful completion of this wizard.</span></span> <span data-ttu-id="291f1-137">Процесс будет состоять из создания структуры полнотекстового индекса в каталоге и заполнения его полнотекстовыми индексированными данными.</span><span class="sxs-lookup"><span data-stu-id="291f1-137">This will consist of creating the full-text index structure in the catalog and populating it with full-text indexed data.</span></span>  
  
3.  <span data-ttu-id="291f1-138">Выбор каталога, файловой группы индекса и списка стоп-слов.</span><span class="sxs-lookup"><span data-stu-id="291f1-138">Select the catalog, index filegroup and stoplist.</span></span>  
  
     <span data-ttu-id="291f1-139">**Выбрать полнотекстовый каталог**</span><span class="sxs-lookup"><span data-stu-id="291f1-139">**Select full-text catalog**</span></span>  
     <span data-ttu-id="291f1-140">Выбор полнотекстового каталога из списка.</span><span class="sxs-lookup"><span data-stu-id="291f1-140">Select a full-text catalog from the list.</span></span> <span data-ttu-id="291f1-141">Каталогом по умолчанию для базы данных будет выбранный по умолчанию элемент в списке.</span><span class="sxs-lookup"><span data-stu-id="291f1-141">The default catalog for the database will be the selected item by default in the list.</span></span> <span data-ttu-id="291f1-142">Если нет доступных каталогов, список будет недоступен, а также будет установлен и недоступен флажок **Создать новый каталог** .</span><span class="sxs-lookup"><span data-stu-id="291f1-142">If no catalogs are available, the list will be disabled, and the **Create a new catalog** checkbox will be checked and disabled.</span></span>  
  
    |||  
    |-|-|  
    |<span data-ttu-id="291f1-143">**Создать новый каталог**</span><span class="sxs-lookup"><span data-stu-id="291f1-143">**Create a new catalog**</span></span>|<span data-ttu-id="291f1-144">Установите флажок для того, чтобы создать новый полнотекстовый каталог.</span><span class="sxs-lookup"><span data-stu-id="291f1-144">Select to create a new full-text catalog.</span></span>|  
  
     <span data-ttu-id="291f1-145">**имя**;</span><span class="sxs-lookup"><span data-stu-id="291f1-145">**Name**</span></span>  
     <span data-ttu-id="291f1-146">Введите имя нового полнотекстового каталога.</span><span class="sxs-lookup"><span data-stu-id="291f1-146">Enter a name for the new full-text catalog.</span></span>  
  
     <span data-ttu-id="291f1-147">**Назначить каталогом по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="291f1-147">**Set as default catalog**</span></span>  
     <span data-ttu-id="291f1-148">Установите флажок, чтобы сделать каталог используемым по умолчанию для этой базы данных.</span><span class="sxs-lookup"><span data-stu-id="291f1-148">Select to make the catalog the default for this database.</span></span>  
  
     <span data-ttu-id="291f1-149">**Учитывать диакритические знаки**</span><span class="sxs-lookup"><span data-stu-id="291f1-149">**Accent sensitivity**</span></span>  
     <span data-ttu-id="291f1-150">Укажите, будет ли новый каталог учитывать диакритические знаки или не будет.</span><span class="sxs-lookup"><span data-stu-id="291f1-150">Specify whether the new catalog will be accent-sensitive or accent-insensitive.</span></span> <span data-ttu-id="291f1-151">Если база данных учитывает диакритические знаки, флажок **Учитывать** по умолчанию будет установлен.</span><span class="sxs-lookup"><span data-stu-id="291f1-151">If the database is accent-sensitive, **Sensitive** will be selected by default.</span></span>  
  
     <span data-ttu-id="291f1-152">**Выберите файловую группу индекса**</span><span class="sxs-lookup"><span data-stu-id="291f1-152">**Select index filegroup**</span></span>  
     <span data-ttu-id="291f1-153">Укажите файловую группу, на основе которой будет создан полнотекстовый индекс.</span><span class="sxs-lookup"><span data-stu-id="291f1-153">Specify the filegroup on which to create the full-text index.</span></span>  
  
     <span data-ttu-id="291f1-154">Выберите одно из следующих значений.</span><span class="sxs-lookup"><span data-stu-id="291f1-154">Select one of the following values:</span></span>  
  
    |<span data-ttu-id="291f1-155">Значение</span><span class="sxs-lookup"><span data-stu-id="291f1-155">Value</span></span>|<span data-ttu-id="291f1-156">Описание</span><span class="sxs-lookup"><span data-stu-id="291f1-156">Description</span></span>|  
    |-----------|-----------------|  
    |**\<default>**|<span data-ttu-id="291f1-157">Если таблица или представление не секционированы, выберите это значение, чтобы использовать ту же файловую группу, что и в базовой таблице или представлении.</span><span class="sxs-lookup"><span data-stu-id="291f1-157">If the table or view is not partitioned, select to use the same filegroup as the underlying table or view.</span></span> <span data-ttu-id="291f1-158">Если таблица или представление не секционированы, то используется первичная файловая группа.</span><span class="sxs-lookup"><span data-stu-id="291f1-158">If the table or view is partitioned, the primary filegroup is used.</span></span>|  
    |<span data-ttu-id="291f1-159">**PRIMARY**</span><span class="sxs-lookup"><span data-stu-id="291f1-159">**PRIMARY**</span></span>|<span data-ttu-id="291f1-160">Выберите это значение, чтобы назначить для нового полнотекстового индекса первичную файловую группу.</span><span class="sxs-lookup"><span data-stu-id="291f1-160">Select to use the primary filegroup for the new full-text index.</span></span>|  
    |<span data-ttu-id="291f1-161">*определенная пользователем файловая группа по умолчанию*</span><span class="sxs-lookup"><span data-stu-id="291f1-161">*user-specified default filegroup*</span></span>|<span data-ttu-id="291f1-162">Если существует определенный пользователем список стоп-слов, выберите его имя из списка, чтобы использовать эту файловую группу для нового полнотекстового индекса.</span><span class="sxs-lookup"><span data-stu-id="291f1-162">If a user-defined default stoplist exists, select its name from the list to use that filegroup for the new full-text index.</span></span>|  
  
     <span data-ttu-id="291f1-163">**Выберите полнотекстовый список стоп-слов**</span><span class="sxs-lookup"><span data-stu-id="291f1-163">**Select full-text stoplist**</span></span>  
     <span data-ttu-id="291f1-164">Укажите список стоп-слов для использования в полнотекстовом индексе или отключите использование этого списка.</span><span class="sxs-lookup"><span data-stu-id="291f1-164">Specify a stoplist to use for the full-text index, or disable stoplist use.</span></span>  
  
     <span data-ttu-id="291f1-165">В [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] и более поздних версиях стоп-слова в базах данных управляются с помощью объектов, называемых списками стоп-слов.</span><span class="sxs-lookup"><span data-stu-id="291f1-165">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions, stopwords are managed in databases using objects called stoplists.</span></span> <span data-ttu-id="291f1-166">*Список стоп-слов* связан с полнотекстовым индексом и применяется к полнотекстовым запросам по этому индексу.</span><span class="sxs-lookup"><span data-stu-id="291f1-166">A *stoplist* is a list of stopwords that, when associated with a full-text index, is applied to full-text queries on that index.</span></span> <span data-ttu-id="291f1-167">Дополнительные сведения см. в разделе [Настройка стоп-слов и списков стоп-слов для полнотекстового поиска и управление ими](configure-and-manage-stopwords-and-stoplists-for-full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="291f1-167">For more information, see [Configure and Manage Stopwords and Stoplists for Full-Text Search](configure-and-manage-stopwords-and-stoplists-for-full-text-search.md).</span></span>  
  
     <span data-ttu-id="291f1-168">Выберите одно из следующих значений.</span><span class="sxs-lookup"><span data-stu-id="291f1-168">Select one of the following values:</span></span>  
  
    |<span data-ttu-id="291f1-169">Значение</span><span class="sxs-lookup"><span data-stu-id="291f1-169">Value</span></span>|<span data-ttu-id="291f1-170">Описание</span><span class="sxs-lookup"><span data-stu-id="291f1-170">Description</span></span>|  
    |-----------|-----------------|  
    |**\<system>**|<span data-ttu-id="291f1-171">Выберите это значение, чтобы использовать в новом полнотекстовом индексе системный список стоп-слов.</span><span class="sxs-lookup"><span data-stu-id="291f1-171">Select to use the system stoplist on the new full-text index.</span></span> <span data-ttu-id="291f1-172">Это значение установлено по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="291f1-172">This is the default</span></span>|  
    |**\<off>**|<span data-ttu-id="291f1-173">Выберите это значение, чтобы отключить списки стоп-слов в новом полнотекстовом индексе.</span><span class="sxs-lookup"><span data-stu-id="291f1-173">Select to disable stoplists for the new full-text index.</span></span>|  
    |<span data-ttu-id="291f1-174">*определенный пользователем список стоп-слов*</span><span class="sxs-lookup"><span data-stu-id="291f1-174">*user-defined-stoplist-name*</span></span>|<span data-ttu-id="291f1-175">В списке отображается имя каждого из определенных пользователем списков стоп-слов, созданных для базы данных, если таковые существуют.</span><span class="sxs-lookup"><span data-stu-id="291f1-175">The list displays the name of each user-defined stoplist, if any, that has been created on the database.</span></span> <span data-ttu-id="291f1-176">Выберите какой-либо определенный пользователем список стоп-слов для использования в новом полнотекстовом индексе.</span><span class="sxs-lookup"><span data-stu-id="291f1-176">Select any user-defined stoplist to use for the new full-text index.</span></span>|  
  
4.  <span data-ttu-id="291f1-177">При необходимости определите расписание заполнения.</span><span class="sxs-lookup"><span data-stu-id="291f1-177">Optionally, define the population schedule.</span></span> <span data-ttu-id="291f1-178">Операции индексирования начнутся немедленно, если только для них не было задано расписание для выполнения в будущем.</span><span class="sxs-lookup"><span data-stu-id="291f1-178">Indexing operations will begin immediately unless they have been scheduled for future execution.</span></span> <span data-ttu-id="291f1-179">Расписания будут созданы немедленно, хотя они не будут выполнены до заданного времени.</span><span class="sxs-lookup"><span data-stu-id="291f1-179">Schedules will be created immediately, although they will not run until their scheduled time.</span></span>  
  
     <span data-ttu-id="291f1-180">**Создание расписания для таблицы**</span><span class="sxs-lookup"><span data-stu-id="291f1-180">**New Table Schedule**</span></span>  
     <span data-ttu-id="291f1-181">Позволяет определить расписание заполнений для таблицы.</span><span class="sxs-lookup"><span data-stu-id="291f1-181">Define a population schedule for a table.</span></span>  
  
     <span data-ttu-id="291f1-182">**Создание расписания для каталога**</span><span class="sxs-lookup"><span data-stu-id="291f1-182">**New Catalog Schedule**</span></span>  
     <span data-ttu-id="291f1-183">Позволяет определить расписание заполнений для полнотекстового каталога.</span><span class="sxs-lookup"><span data-stu-id="291f1-183">Define a population schedule for a full-text catalog.</span></span>  
  
     <span data-ttu-id="291f1-184">**Edit** (Изменение)</span><span class="sxs-lookup"><span data-stu-id="291f1-184">**Edit**</span></span>  
     <span data-ttu-id="291f1-185">Позволяет изменить расписание.</span><span class="sxs-lookup"><span data-stu-id="291f1-185">Edit a schedule.</span></span>  
  
     <span data-ttu-id="291f1-186">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="291f1-186">**Delete**</span></span>  
     <span data-ttu-id="291f1-187">Позволяет удалить расписание.</span><span class="sxs-lookup"><span data-stu-id="291f1-187">Delete a schedule.</span></span>  
  
5.  <span data-ttu-id="291f1-188">Просмотр и управление выполнением мастера полнотекстового индексирования.</span><span class="sxs-lookup"><span data-stu-id="291f1-188">View or control the progress of the Full-Text Indexing Wizard.</span></span>  
  
     <span data-ttu-id="291f1-189">**Остановить**</span><span class="sxs-lookup"><span data-stu-id="291f1-189">**Stop**</span></span>  
     <span data-ttu-id="291f1-190">Прерывает текущую операцию и блокирует выполнение мастером последующих полнотекстовых операций в течение этого сеанса.</span><span class="sxs-lookup"><span data-stu-id="291f1-190">Interrupts the current operation and prevents subsequent full-text operations from being performed by the wizard during this session.</span></span>  
  
     <span data-ttu-id="291f1-191">**Отчет**</span><span class="sxs-lookup"><span data-stu-id="291f1-191">**Report**</span></span>  
     <span data-ttu-id="291f1-192">Когда выполнение всех операций завершено, нажмите эту кнопку, чтобы получить доступ к отчету о выполненных операциях.</span><span class="sxs-lookup"><span data-stu-id="291f1-192">When all of the operations have finished executing, click this button to access a report on the operations performed.</span></span> <span data-ttu-id="291f1-193">Можно просмотреть отчет, распечатать его в файл, скопировать в буфер обмена или отправить по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="291f1-193">You can view the report, print it to a file, copy it to the clipboard, or e-mail the report.</span></span>  
  
  
