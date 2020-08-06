---
title: Определение и изменение параметризованного фильтра строк для статьи публикации слиянием | Документация Майкрософт
ms.custom: ''
ms.date: 06/02/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- parameterized filters [SQL Server replication], defining
- parameterized filters [SQL Server replication], modifying
- merge replication [SQL Server replication], dynamic filters
- merge replication parameterized filters [SQL Server replication]
- filters [SQL Server replication], parameterized
- modifying filters, parameterized row
- dynamic filters [SQL Server replication]
ms.assetid: de0482a2-3cc8-4030-8a4a-14364549ac9f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d80ad53661aced22795220507398e2fcc510edd3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736166"
---
# <a name="define-and-modify-a-parameterized-row-filter-for-a-merge-article"></a><span data-ttu-id="39b09-102">Определение и изменение параметризованного фильтра строк для статьи публикации слиянием</span><span class="sxs-lookup"><span data-stu-id="39b09-102">Define and Modify a Parameterized Row Filter for a Merge Article</span></span>
  <span data-ttu-id="39b09-103">В этом разделе описывается определение и изменение параметризованного фильтра строк в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] при помощи среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39b09-103">This topic describes how to define and modify a parameterized row filter in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="39b09-104">При создании статей таблицы можно применять параметризованные фильтры строк.</span><span class="sxs-lookup"><span data-stu-id="39b09-104">When creating table articles, you can use parameterized row filters.</span></span> <span data-ttu-id="39b09-105">Эти фильтры используют предложение [WHERE](/sql/t-sql/queries/where-transact-sql) , чтобы выбрать необходимые данные для публикации.</span><span class="sxs-lookup"><span data-stu-id="39b09-105">These filters use a [WHERE](/sql/t-sql/queries/where-transact-sql) clause to select the appropriate data to be published.</span></span> <span data-ttu-id="39b09-106">Вместо того чтобы задавать буквенное значение в предложении (так, как в случае статического фильтра строк), вы указываете одну или обе следующие системные функции: [SUSER_SNAME](/sql/t-sql/functions/suser-sname-transact-sql) и [HOST_NAME](/sql/t-sql/functions/host-name-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="39b09-106">Rather than specifying a literal value in the clause (as you do with a static row filter), you specify one or both of the following system functions: [SUSER_SNAME](/sql/t-sql/functions/suser-sname-transact-sql) and [HOST_NAME](/sql/t-sql/functions/host-name-transact-sql).</span></span> <span data-ttu-id="39b09-107">Дополнительные сведения см. в разделе [Параметризованные фильтры строк](../merge/parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="39b09-107">For more information, see [Parameterized Row Filters](../merge/parameterized-filters-parameterized-row-filters.md).</span></span>  
  
 
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="39b09-108">Перед началом</span><span class="sxs-lookup"><span data-stu-id="39b09-108">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="39b09-109">Ограничения</span><span class="sxs-lookup"><span data-stu-id="39b09-109">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="39b09-110">Если добавление, изменение или удаление параметризованного фильтра строк выполняется после инициализации подписок на публикацию, следует создать новый моментальный снимок и повторно инициализировать все подписки после внесения изменений.</span><span class="sxs-lookup"><span data-stu-id="39b09-110">If you add, modify, or delete a parameterized row filter after subscriptions to the publication have been initialized, you must generate a new snapshot and reinitialize all subscriptions after making the change.</span></span> <span data-ttu-id="39b09-111">Дополнительные сведения о требованиях к изменениям свойств см. в статье [Изменение свойств публикации и статьи](change-publication-and-article-properties.md).</span><span class="sxs-lookup"><span data-stu-id="39b09-111">For more information about requirements for property changes, see [Change Publication and Article Properties](change-publication-and-article-properties.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="39b09-112">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="39b09-112">Recommendations</span></span>  
  
-   <span data-ttu-id="39b09-113">Для обеспечения высокой производительности не рекомендуется применять функции к именам столбцов в выражениях параметризованных фильтров строк, таких как `LEFT([MyColumn]) = SUSER_SNAME()`.</span><span class="sxs-lookup"><span data-stu-id="39b09-113">For performance reasons, we recommend that you not apply functions to column names in parameterized row filter clauses, such as `LEFT([MyColumn]) = SUSER_SNAME()`.</span></span> <span data-ttu-id="39b09-114">Если в предложении фильтра используется HOST_NAME и переопределяется значение HOST_NAME, может быть, необходимо выполнить преобразование типов данных при помощи инструкции CONVERT.</span><span class="sxs-lookup"><span data-stu-id="39b09-114">If you use HOST_NAME in a filter clause and override the HOST_NAME value, it might be necessary to convert data types using CONVERT.</span></span> <span data-ttu-id="39b09-115">Дополнительные сведения см. в подразделе «Переопределение значения HOST_NAME()» раздела [Parameterized Row Filters](../merge/parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="39b09-115">For more information about best practices for this case, see the section "Overriding the HOST_NAME() Value" in the topic [Parameterized Row Filters](../merge/parameterized-filters-parameterized-row-filters.md).</span></span>  
  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="39b09-116">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="39b09-116">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="39b09-117">Операции определения, изменения и удаления параметризованных фильтров строк выполняются на странице **Фильтрация строк таблицы** мастера создания публикаций или на странице **Фильтрация строк** диалогового окна **Свойства публикации — \<Publication>** .</span><span class="sxs-lookup"><span data-stu-id="39b09-117">Define, modify, and delete parameterized row filters on the **Filter Table Rows** page of the New Publication Wizard or the **Filter Rows** page of the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="39b09-118">Дополнительные сведения об использовании мастера и доступе к этому диалоговому окну см. в статьях [Создание публикации](create-a-publication.md) и [Просмотр и изменение свойств публикации](view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="39b09-118">For more information about using the wizard and accessing the dialog box, see [Create a Publication](create-a-publication.md) and [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span></span>  
  
#### <a name="to-define-a-parameterized-row-filter"></a><span data-ttu-id="39b09-119">Определение параметризованного фильтра строк</span><span class="sxs-lookup"><span data-stu-id="39b09-119">To define a parameterized row filter</span></span>  
  
1.  <span data-ttu-id="39b09-120">На странице **Фильтрация строк таблицы** мастера создания публикаций или на странице **Фильтрация строк** диалогового окна **Свойства публикации — \<Publication>** нажмите кнопку **Добавить**, а затем — **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="39b09-120">On the **Filter Table Rows** page of the New Publication Wizard or the **Filter Rows** page of the **Publication Properties - \<Publication>**, click **Add**, and then click **Add Filter**.</span></span>  
  
2.  <span data-ttu-id="39b09-121">В окне **Добавление фильтра** выберите в раскрывающемся списке таблицу для фильтрации.</span><span class="sxs-lookup"><span data-stu-id="39b09-121">In the **Add Filter** dialog box, select a table to filter from the drop-down list box.</span></span>  
  
3.  <span data-ttu-id="39b09-122">Создайте инструкцию фильтра в текстовом поле **Инструкция фильтра** .</span><span class="sxs-lookup"><span data-stu-id="39b09-122">Create a filter statement in the **Filter statement** text box.</span></span> <span data-ttu-id="39b09-123">Можно ввести текст в тестовом поле или перетащить столбцы из списка **Столбцы** .</span><span class="sxs-lookup"><span data-stu-id="39b09-123">You can type directly in the text area, and you can also drag and drop columns from the **Columns** list box.</span></span>  
  
    -   <span data-ttu-id="39b09-124">Текстовая область **Инструкция фильтра** содержит текст по умолчанию, в виде:</span><span class="sxs-lookup"><span data-stu-id="39b09-124">The **Filter statement** text area includes the default text, which is in the form of:</span></span>  
  
        ```  
        SELECT <published_columns> FROM [tableowner].[tablename] WHERE  
        ```  
  
    -   <span data-ttu-id="39b09-125">Текст по умолчанию изменять нельзя. Введите предложение фильтра после ключевого слова WHERE, используя стандартный синтаксис SQL.</span><span class="sxs-lookup"><span data-stu-id="39b09-125">The default text cannot be changed; type the filter clause after the WHERE keyword using standard SQL syntax.</span></span> <span data-ttu-id="39b09-126">Параметризованный фильтр включает вызов функции системы `HOST_NAME()` и/или `SUSER_SNAME()` либо пользовательской функции, которая ссылается на одну или обе эти функции.</span><span class="sxs-lookup"><span data-stu-id="39b09-126">A parameterized filter includes a call to the system function `HOST_NAME()` and/or `SUSER_SNAME()`, or a user-defined function that references one or both of these functions.</span></span> <span data-ttu-id="39b09-127">Ниже приведен пример полного выражения для параметризованного фильтра строк:</span><span class="sxs-lookup"><span data-stu-id="39b09-127">The following is an example of a complete filter clause for a parameterized row filter:</span></span>  
  
        ```  
        SELECT <published_columns> FROM [HumanResources].[Employee] WHERE LoginID = SUSER_SNAME()  
        ```  
  
         <span data-ttu-id="39b09-128">В предложении WHERE необходимо использовать имена, состоящие из двух частей; имена, состоящие из трех или четырех частей, не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="39b09-128">The WHERE clause should use two-part naming; three-part naming and four-part naming are not supported.</span></span>  
  
4.  <span data-ttu-id="39b09-129">Выберите параметр, который соответствует способу совместного использования данных подписчиками:</span><span class="sxs-lookup"><span data-stu-id="39b09-129">Select the option that matches how data will be shared among Subscribers:</span></span>  
  
    -   <span data-ttu-id="39b09-130">**Строка из этой таблицы будет отправлена нескольким подпискам**</span><span class="sxs-lookup"><span data-stu-id="39b09-130">**A row from this table will go to multiple subscriptions**</span></span>  
  
    -   <span data-ttu-id="39b09-131">**Строка из этой таблицы будет отправлена только одной подписке**</span><span class="sxs-lookup"><span data-stu-id="39b09-131">**A row from this table will go to only one subscription**</span></span>  
  
     <span data-ttu-id="39b09-132">Если выбрана настройка **Строка из этой таблицы будет отправлена только одной подписке**, производительность репликации слиянием будет оптимизирована путем уменьшения объема хранимых и обрабатываемых метаданных.</span><span class="sxs-lookup"><span data-stu-id="39b09-132">If you select **A row from this table will go to only one subscription**, merge replication can optimize performance by storing and processing less metadata.</span></span> <span data-ttu-id="39b09-133">Однако следует убедиться, что данные секционированы таким образом, что одна строка не может быть реплицирована более чем одному подписчику.</span><span class="sxs-lookup"><span data-stu-id="39b09-133">However, you must ensure that the data is partitioned in such a way that a row cannot be replicated to more than one Subscriber.</span></span> <span data-ttu-id="39b09-134">Дополнительные сведения см. в подразделе «Настройка параметров секционирования» раздела [Параметризованные фильтры строк](../merge/parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="39b09-134">For more information, see the section "Setting 'partition options'" in the topic [Parameterized Row Filters](../merge/parameterized-filters-parameterized-row-filters.md).</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="39b09-135">Если вы находитесь в диалоговом окне **Свойства публикации — \<Publication>** , нажмите кнопку **OK**, чтобы сохранить результаты и закрыть диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="39b09-135">If you are in the **Publication Properties - \<Publication>** dialog box, click **OK** to save and close the dialog box.</span></span>  
  
#### <a name="to-modify-a-parameterized-row-filter"></a><span data-ttu-id="39b09-136">Изменение параметризованного фильтра строк</span><span class="sxs-lookup"><span data-stu-id="39b09-136">To modify a parameterized row filter</span></span>  
  
1.  <span data-ttu-id="39b09-137">На странице **Фильтрация строк таблицы** мастера создания публикаций или странице **Фильтрация строк** диалогового окна **Свойства публикации — \<Publication>** выберите фильтр в области **Отфильтрованные таблицы**, а затем нажмите кнопку **Правка**.</span><span class="sxs-lookup"><span data-stu-id="39b09-137">On the **Filter Table Rows** page of the New Publication Wizard or the **Filter Rows** page of the **Publication Properties - \<Publication>**, select a filter in the **Filtered Tables** pane, and then click **Edit**.</span></span>  
  
2.  <span data-ttu-id="39b09-138">В окне **Изменение фильтра** измените фильтр.</span><span class="sxs-lookup"><span data-stu-id="39b09-138">In the **Edit Filter** dialog box, modify the filter.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
#### <a name="to-delete-a-parameterized-row-filter"></a><span data-ttu-id="39b09-139">Удаление параметризованного фильтра строк</span><span class="sxs-lookup"><span data-stu-id="39b09-139">To delete a parameterized row filter</span></span>  
  
1.  <span data-ttu-id="39b09-140">На странице **Фильтрация строк таблицы** мастера создания публикаций или странице **Фильтрация строк** диалогового окна **Свойства публикации — \<Publication>** выберите фильтр в области **Отфильтрованные таблицы**, а затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="39b09-140">On the **Filter Table Rows** page of the New Publication Wizard or the **Filter Rows** page of the **Publication Properties - \<Publication>**, select a filter in the **Filtered Tables** pane, and then click **Delete**.</span></span>  
  

  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="39b09-141">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="39b09-141">Using Transact-SQL</span></span>  
 <span data-ttu-id="39b09-142">Параметризованные фильтры строк можно создавать и изменять программно с помощью хранимых процедур репликации.</span><span class="sxs-lookup"><span data-stu-id="39b09-142">Parameterized row filters can be created and modified programmatically using replication stored procedures.</span></span>  
  
#### <a name="to-define-a-parameterized-row-filter-for-an-article-in-a-merge-publication"></a><span data-ttu-id="39b09-143">Определение параметризованного фильтра строк для статьи в публикации слиянием</span><span class="sxs-lookup"><span data-stu-id="39b09-143">To define a parameterized row filter for an article in a merge publication</span></span>  
  
1.  <span data-ttu-id="39b09-144">В базе данных публикации на издателе выполните процедуру [sp_addmergearticle (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-addmergearticle-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="39b09-144">At the Publisher on the publication database, execute [sp_addmergearticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergearticle-transact-sql).</span></span> <span data-ttu-id="39b09-145">Укажите **@publication** , имя статьи в параметре **@article** , публикуемую таблицу **@source_object** , предложение WHERE, определяющее параметризованный фильтр для **@subset_filterclause** (не включая `WHERE` ), и одно из следующих значений для **@partition_options** , которое описывает тип секционирования, который будет получен из параметризованного фильтра строк:</span><span class="sxs-lookup"><span data-stu-id="39b09-145">Specify **@publication**, a name for the article for **@article**, the table being published for **@source_object**, the WHERE clause that defines the parameterized filter for **@subset_filterclause** (not including `WHERE`), and one of the following values for **@partition_options**, which describes the type of partitioning that will result from the parameterized row filter:</span></span>  
  
    -   <span data-ttu-id="39b09-146">**0** — фильтрация для данной статьи либо является статической, либо не возвращает уникального подмножества данных для каждой из секций (то есть имеются перекрывающиеся секции).</span><span class="sxs-lookup"><span data-stu-id="39b09-146">**0** - Filtering for the article either is static or does not yield a unique subset of data for each partition (an "overlapping" partition).</span></span>  
  
    -   <span data-ttu-id="39b09-147">**1** — результирующие секции перекрываются, и произведенные на подписчике изменения не могут быть внесены в секцию, которой принадлежит строка.</span><span class="sxs-lookup"><span data-stu-id="39b09-147">**1** - Resulting partitions are overlapping, and updates made at the Subscriber cannot change the partition to which a row belongs.</span></span>  
  
    -   <span data-ttu-id="39b09-148">**2** — фильтрация для статьи дает неперекрывающиеся секции, но несколько подписчиков могут получить одну и ту же секцию.</span><span class="sxs-lookup"><span data-stu-id="39b09-148">**2** - Filtering for the article yields nonoverlapping partitions, but multiple Subscribers can receive the same partition.</span></span>  
  
    -   <span data-ttu-id="39b09-149">**3** — фильтрация для статьи дает неперекрывающиеся секции, уникальные для каждой из подписок.</span><span class="sxs-lookup"><span data-stu-id="39b09-149">**3** - Filtering for the article yields nonoverlapping partitions that are unique for each subscription.</span></span>  
  
#### <a name="to-change-a-parameterized-row-filter-for-an-article-in-a-merge-publication"></a><span data-ttu-id="39b09-150">Изменение параметризованного фильтра строк для статьи в публикации слиянием</span><span class="sxs-lookup"><span data-stu-id="39b09-150">To change a parameterized row filter for an article in a merge publication</span></span>  
  
1.  <span data-ttu-id="39b09-151">В базе данных публикации на издателе выполните процедуру [sp_changemergearticle](/sql/relational-databases/system-stored-procedures/sp-changemergearticle-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="39b09-151">At the Publisher on the publication database, execute [sp_changemergearticle](/sql/relational-databases/system-stored-procedures/sp-changemergearticle-transact-sql).</span></span> <span data-ttu-id="39b09-152">Укажите **@publication** , **@article** , значение `subset_filterclause` для **@property** , выражение, определяющее параметризованный фильтр для **@value** (не включая `WHERE` ), и значение **1** для обоих параметров **@force_invalidate_snapshot** и **@force_reinit_subscription** .</span><span class="sxs-lookup"><span data-stu-id="39b09-152">Specify **@publication**, **@article**, a value of `subset_filterclause` for **@property**, the expression that defines the parameterized filter for **@value** (not including `WHERE`), and a value of **1** for both **@force_invalidate_snapshot** and **@force_reinit_subscription**.</span></span>  
  
2.  <span data-ttu-id="39b09-153">Если это изменение приведет к разному поведению секционирования, еще раз выполните хранимую процедуру [sp_changemergearticle](/sql/relational-databases/system-stored-procedures/sp-changemergearticle-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="39b09-153">If this change results in different partitioning behavior, then execute [sp_changemergearticle](/sql/relational-databases/system-stored-procedures/sp-changemergearticle-transact-sql) again.</span></span> <span data-ttu-id="39b09-154">Укажите **@publication** , **@article** , значение `partition_options` для **@property** и наиболее подходящий параметр секционирования для **@value** , который может принимать одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="39b09-154">Specify **@publication**, **@article**, a value of `partition_options` for **@property**, and the most appropriate partitioning option for **@value**, which can be one of the following:</span></span>  
  
    -   <span data-ttu-id="39b09-155">**0** — фильтрация для данной статьи либо является статической, либо не возвращает уникального подмножества данных для каждой из секций (то есть имеются перекрывающиеся секции).</span><span class="sxs-lookup"><span data-stu-id="39b09-155">**0** - Filtering for the article either is static or does not yield a unique subset of data for each partition (an "overlapping" partition).</span></span>  
  
    -   <span data-ttu-id="39b09-156">**1** — результирующие секции перекрываются, и произведенные на подписчике изменения не могут быть внесены в секцию, которой принадлежит строка.</span><span class="sxs-lookup"><span data-stu-id="39b09-156">**1** - Resulting partitions are overlapping, and updates made at the Subscriber cannot change the partition to which a row belongs.</span></span>  
  
    -   <span data-ttu-id="39b09-157">**2** — фильтрация для статьи дает неперекрывающиеся секции, но несколько подписчиков могут получить одну и ту же секцию.</span><span class="sxs-lookup"><span data-stu-id="39b09-157">**2** - Filtering for the article yields nonoverlapping partitions, but multiple Subscribers can receive the same partition.</span></span>  
  
    -   <span data-ttu-id="39b09-158">**3** — фильтрация для статьи дает неперекрывающиеся секции, уникальные для каждой из подписок.</span><span class="sxs-lookup"><span data-stu-id="39b09-158">**3** - Filtering for the article yields nonoverlapping partitions that are unique for each subscription.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="39b09-159">Примеры (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="39b09-159">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="39b09-160">В этом примере определяется группа статей в публикации слиянием. К статьям применяется последовательность фильтров соединения для таблицы `Employee` , которая в свою очередь фильтруется по столбцу **LoginID** с помощью параметризованного фильтра строк.</span><span class="sxs-lookup"><span data-stu-id="39b09-160">This example defines a group of articles in a merge publication where the articles are filtered with a series of join filters against the `Employee` table that is itself filtered using a parameterized row filter on the **LoginID** column.</span></span> <span data-ttu-id="39b09-161">Во время синхронизации переопределяется значение, возвращаемое функцией [HOST_NAME](/sql/t-sql/functions/host-name-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="39b09-161">During synchronization, the value returned by the [HOST_NAME](/sql/t-sql/functions/host-name-transact-sql) function is overridden.</span></span> <span data-ttu-id="39b09-162">Дополнительные сведения см. в подразделе «Переопределение значения функции HOST_NAME()» раздела [Parameterized Row Filters](../merge/parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="39b09-162">For more information, see Overriding the HOST_NAME() Value in the topic [Parameterized Row Filters](../merge/parameterized-filters-parameterized-row-filters.md).</span></span>  
  
 [!code-sql[HowTo#sp_MergeDynamicPub1](../../../snippets/tsql/SQL15/replication/howto/tsql/createmergepubdynamic1.sql#sp_mergedynamicpub1)]  
  
  
## <a name="see-also"></a><span data-ttu-id="39b09-163">См. также:</span><span class="sxs-lookup"><span data-stu-id="39b09-163">See Also</span></span>  
 <span data-ttu-id="39b09-164">[Определение и изменение фильтра соединения между статьями публикации слиянием](define-and-modify-a-join-filter-between-merge-articles.md) </span><span class="sxs-lookup"><span data-stu-id="39b09-164">[Define and Modify a Join Filter Between Merge Articles](define-and-modify-a-join-filter-between-merge-articles.md) </span></span>  
 <span data-ttu-id="39b09-165">[Изменение свойств публикации и статьи](change-publication-and-article-properties.md) </span><span class="sxs-lookup"><span data-stu-id="39b09-165">[Change Publication and Article Properties](change-publication-and-article-properties.md) </span></span>  
 <span data-ttu-id="39b09-166">[Join Filters](../merge/join-filters.md) </span><span class="sxs-lookup"><span data-stu-id="39b09-166">[Join Filters](../merge/join-filters.md) </span></span>  
 [<span data-ttu-id="39b09-167">Параметризованные фильтры строк</span><span class="sxs-lookup"><span data-stu-id="39b09-167">Parameterized Row Filters</span></span>](../merge/parameterized-filters-parameterized-row-filters.md)  
  
  
