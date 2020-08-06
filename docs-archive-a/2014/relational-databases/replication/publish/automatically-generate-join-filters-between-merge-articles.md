---
title: Автоматически формировать набор фильтров соединений между статьями публикации слиянием (SQL Server Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- automatic join filter generation
- join filters
ms.assetid: 7ef419f4-c17f-42a5-9068-174a3ec08941
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4bfdbf93aad134e4da873a6aade307754a2637e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654156"
---
# <a name="automatically-generate-a-set-of-join-filters-between-merge-articles-sql-server-management-studio"></a><span data-ttu-id="7d811-102">Автоматическое формирование набора фильтров соединения между статьями публикации слиянием (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="7d811-102">Automatically Generate a Set of Join Filters Between Merge Articles (SQL Server Management Studio)</span></span>
  <span data-ttu-id="7d811-103">Набор фильтров соединения можно автоматически сформировать на странице **Фильтрация строк таблицы** мастера создания публикаций или на странице **Фильтрация строк** диалогового окна **Свойства публикации — \<Publication>** .</span><span class="sxs-lookup"><span data-stu-id="7d811-103">Automatically generate a set of join filters on the **Filter Table Rows** page of the New Publication Wizard or the **Filter Rows** page of the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="7d811-104">Дополнительные сведения об использовании мастера и доступе к этому диалоговому окну см. в статьях [Создание публикации](create-a-publication.md) и [Просмотр и изменение свойств публикации](view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="7d811-104">For more information about using the wizard and accessing the dialog box, see [Create a Publication](create-a-publication.md) and [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7d811-105">В случае автоматического создания набора фильтров соединения в диалоговом окне **Свойства публикации — \<Publication>** после того, как были инициализированы подписки на публикацию, нужно создать новый моментальный снимок и повторно инициализировать все подписки после внесения изменений.</span><span class="sxs-lookup"><span data-stu-id="7d811-105">If you automatically generate a set of join filters in the **Publication Properties - \<Publication>** dialog box after subscriptions to the publication have been initialized, you must generate a new snapshot and reinitialize all subscriptions after making the change.</span></span> <span data-ttu-id="7d811-106">Дополнительные сведения о требованиях к изменениям свойств см. в статье [Изменение свойств публикации и статьи](change-publication-and-article-properties.md).</span><span class="sxs-lookup"><span data-stu-id="7d811-106">For more information about requirements for property changes, see [Change Publication and Article Properties](change-publication-and-article-properties.md).</span></span>  
  
 <span data-ttu-id="7d811-107">Фильтры соединения могут быть созданы вручную для набора таблиц или автоматически системой репликации на основе определенных в таблицах отношений внешних ключей к первичным ключам.</span><span class="sxs-lookup"><span data-stu-id="7d811-107">Join filters can be created manually for a set of tables, or replication can generate the filters automatically based on the foreign key to primary key relationships defined on the tables.</span></span> <span data-ttu-id="7d811-108">Дополнительные сведения о создании фильтров соединения вручную см. в статье[Определение и изменение фильтра соединения между статьями публикации слиянием](define-and-modify-a-join-filter-between-merge-articles.md).</span><span class="sxs-lookup"><span data-stu-id="7d811-108">For more information about creating join filters manually, see [Define and Modify a Join Filter Between Merge Articles](define-and-modify-a-join-filter-between-merge-articles.md).</span></span>  
  
### <a name="to-automatically-generate-a-set-of-join-filters-between-merge-articles"></a><span data-ttu-id="7d811-109">Автоматическое создание набора фильтров соединения между статьями публикаций слиянием</span><span class="sxs-lookup"><span data-stu-id="7d811-109">To automatically generate a set of join filters between merge articles</span></span>  
  
1.  <span data-ttu-id="7d811-110">На странице **Фильтрация строк таблицы** мастера создания публикаций или на странице **Фильтрация строк** диалогового окна **Свойства публикации — \<Publication>** щелкните **Добавить**, а затем — **Автоматически создать фильтры**.</span><span class="sxs-lookup"><span data-stu-id="7d811-110">On the **Filter Table Rows** page of the New Publication Wizard or the **Filter Rows** page of the **Publication Properties - \<Publication>**, click **Add**, and then click **Automatically Generate Filters**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7d811-111">При автоматическом создании фильтров из публикации удаляются любые существующие фильтры строк и фильтры соединения.</span><span class="sxs-lookup"><span data-stu-id="7d811-111">Automatically generating filters deletes any existing row filters or join filters in the publication.</span></span> <span data-ttu-id="7d811-112">Фильтры можно добавить вручную после автоматического создания набора фильтров.</span><span class="sxs-lookup"><span data-stu-id="7d811-112">You can add filters after automatically generating a set of filters.</span></span>  
  
2.  <span data-ttu-id="7d811-113">Следуйте указаниям в диалоговом окне **Создать фильтры** для создания фильтра строк.</span><span class="sxs-lookup"><span data-stu-id="7d811-113">Follow the process in the **Generate Filters** dialog box to create a row filter.</span></span> <span data-ttu-id="7d811-114">Затем фильтр строк расширяется на таблицы, связанные с фильтруемой таблицей связью по первичным и внешним ключам.</span><span class="sxs-lookup"><span data-stu-id="7d811-114">The row filter is then extended to the tables related to the filtered table through primary key and foreign key relationships.</span></span>  
  
    1.  <span data-ttu-id="7d811-115">Выберите таблицу для фильтрации в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="7d811-115">Select a table to filter from the drop-down list box.</span></span>  
  
    2.  <span data-ttu-id="7d811-116">Создайте инструкцию фильтра в текстовом поле **Инструкция фильтра** .</span><span class="sxs-lookup"><span data-stu-id="7d811-116">Create a filter statement in the **Filter statement** text box.</span></span> <span data-ttu-id="7d811-117">Можно ввести текст в тестовом поле или перетащить столбцы из списка **Столбцы** .</span><span class="sxs-lookup"><span data-stu-id="7d811-117">You can type directly in the text area, and you can also drag and drop columns from the **Columns** list box.</span></span>  
  
         <span data-ttu-id="7d811-118">Текстовая область **Инструкция фильтра** содержит текст по умолчанию, в виде:</span><span class="sxs-lookup"><span data-stu-id="7d811-118">The **Filter statement** text area includes the default text, which is in the form of:</span></span>  
  
        ```  
        SELECT <published_columns> FROM [tableowner].[tablename] WHERE  
        ```  
  
         <span data-ttu-id="7d811-119">Текст по умолчанию изменять нельзя. Введите предложение фильтра для статического или параметризованного фильтра строк после ключевого слова WHERE, используя стандартный синтаксис SQL.</span><span class="sxs-lookup"><span data-stu-id="7d811-119">The default text cannot be changed; type the filter clause for a static row filter or a parameterized row filter after the WHERE keyword using standard SQL syntax.</span></span> <span data-ttu-id="7d811-120">Полное предложение фильтра для параметризованного фильтра строк должно иметь вид:</span><span class="sxs-lookup"><span data-stu-id="7d811-120">The complete filter clause for a parameterized row filter would look like:</span></span>  
  
        ```  
        SELECT <published_columns> FROM [HumanResources].[Employee] WHERE LoginID = SUSER_SNAME()  
        ```  
  
         <span data-ttu-id="7d811-121">В предложении WHERE необходимо использовать имена, состоящие из двух частей; имена, состоящие из трех или четырех частей, не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="7d811-121">The WHERE clause should use two-part naming; three-part naming and four-part naming are not supported.</span></span>  
  
    3.  <span data-ttu-id="7d811-122">Укажите параметры фильтра.</span><span class="sxs-lookup"><span data-stu-id="7d811-122">Specify filter options.</span></span>  
  
         <span data-ttu-id="7d811-123">Выберите параметр, который соответствует способу совместного использования данных подписчиками: **Строка из этой таблицы отправляется нескольким подпискам** или **Строка из этой таблицы отправляется только одной подписке**.</span><span class="sxs-lookup"><span data-stu-id="7d811-123">Select the option that matches how data will be shared among Subscribers: **A row from this table will go to multiple subscriptions** or **A row from this table will go to only one subscription**.</span></span> <span data-ttu-id="7d811-124">Если выбрана настройка **Строка из этой таблицы будет отправлена только одной подписке**, производительность репликации слиянием будет оптимизирована путем уменьшения объема хранимых и обрабатываемых метаданных.</span><span class="sxs-lookup"><span data-stu-id="7d811-124">If you select **A row from this table will go to only one subscription**, merge replication can optimize performance by storing and processing less metadata.</span></span> <span data-ttu-id="7d811-125">Однако следует убедиться, что данные секционированы таким образом, что одна строка не может быть реплицирована более чем одному подписчику.</span><span class="sxs-lookup"><span data-stu-id="7d811-125">However, you must ensure that the data is partitioned in such a way that a row cannot be replicated to more than one Subscriber.</span></span> <span data-ttu-id="7d811-126">Дополнительные сведения см. в подразделе «Настройка параметров секционирования» раздела [Параметризованные фильтры строк](../merge/parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="7d811-126">For more information, see the section "Setting 'partition options'" in the topic [Parameterized Row Filters](../merge/parameterized-filters-parameterized-row-filters.md).</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
     <span data-ttu-id="7d811-127">Проводится синтаксический анализ указанного фильтра, после чего фильтр применяется к таблице в предложении SELECT.</span><span class="sxs-lookup"><span data-stu-id="7d811-127">The filter you specified is parsed and run against the table in the SELECT clause.</span></span> <span data-ttu-id="7d811-128">Если оператор фильтра содержит синтаксические ошибки или встречаются другие проблемы, пользователь уведомляется, после чего может отредактировать эту инструкцию фильтра.</span><span class="sxs-lookup"><span data-stu-id="7d811-128">If the filter statement contains syntax errors or other problems, you will be notified and will be able to edit the filter statement.</span></span>  
  
     <span data-ttu-id="7d811-129">После синтаксического анализа инструкции система репликации создает необходимые фильтры соединения и показывает их на панели **Отфильтрованные таблицы: таблицы** на страницах **Фильтрация строк таблицы** или **Фильтрация строк** .</span><span class="sxs-lookup"><span data-stu-id="7d811-129">After the statement is parsed, replication creates the necessary join filters and displays them in the **Filtered Tables** pane on the **Filter Table Rows** or **Filter Rows** page.</span></span> <span data-ttu-id="7d811-130">Если фильтры формируются в мастере создания публикаций, а распространитель для издателя, для которого выполняется мастер, еще не настроен, появляется подсказка о необходимости настроить распространитель.</span><span class="sxs-lookup"><span data-stu-id="7d811-130">If you are generating filters from the New Publication Wizard and have not yet configured the Distributor for the Publisher against which this wizard is running, you are prompted to configure it.</span></span>  
  
4.  <span data-ttu-id="7d811-131">Если вы находитесь в диалоговом окне **Свойства публикации — \<Publication>** , нажмите кнопку **ОК**, чтобы сохранить результаты и закрыть диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="7d811-131">If you are in the **Publication Properties - \<Publication>** dialog box, click **OK** to save and close the dialog box.</span></span>  
  
### <a name="to-modify-a-filter-that-was-automatically-generated"></a><span data-ttu-id="7d811-132">Изменение автоматически созданного фильтра</span><span class="sxs-lookup"><span data-stu-id="7d811-132">To modify a filter that was automatically generated</span></span>  
  
1.  <span data-ttu-id="7d811-133">На странице **Фильтрация строк таблицы** мастера создания публикаций или странице **Фильтрация строк** диалогового окна **Свойства публикации — \<Publication>** выберите фильтр в области **Отфильтрованные таблицы**, а затем нажмите кнопку **Правка**.</span><span class="sxs-lookup"><span data-stu-id="7d811-133">On the **Filter Table Rows** page of the New Publication Wizard or the **Filter Rows** page of the **Publication Properties - \<Publication>**, select a filter in the **Filtered Tables** pane, and then click **Edit**.</span></span>  
  
2.  <span data-ttu-id="7d811-134">В диалоговом окне **Изменение фильтра** или **Изменение соединения** измените фильтр.</span><span class="sxs-lookup"><span data-stu-id="7d811-134">In the **Edit Filter** or **Edit Join** dialog box, modify the filter.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-delete-a-filter-that-was-automatically-generated"></a><span data-ttu-id="7d811-135">Удаление автоматически созданного фильтра</span><span class="sxs-lookup"><span data-stu-id="7d811-135">To delete a filter that was automatically generated</span></span>  
  
1.  <span data-ttu-id="7d811-136">На странице **Фильтрация строк таблицы** мастера создания публикаций или странице **Фильтрация строк** диалогового окна **Свойства публикации — \<Publication>** выберите фильтр в области **Отфильтрованные таблицы**, а затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="7d811-136">On the **Filter Table Rows** page of the New Publication Wizard or the **Filter Rows** page of the **Publication Properties - \<Publication>**, select a filter in the **Filtered Tables** pane, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d811-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="7d811-137">See Also</span></span>  
 <span data-ttu-id="7d811-138">[Join Filters](../merge/join-filters.md) </span><span class="sxs-lookup"><span data-stu-id="7d811-138">[Join Filters](../merge/join-filters.md) </span></span>  
 [<span data-ttu-id="7d811-139">Параметризованные фильтры строк</span><span class="sxs-lookup"><span data-stu-id="7d811-139">Parameterized Row Filters</span></span>](../merge/parameterized-filters-parameterized-row-filters.md)  
  
  
