---
title: Добавление каскадных параметров в отчет (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 3a22eec3-57a7-478e-b6fc-102a9dbe0591
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5419d448b2fa9526224e1bccd80d5c195e2763d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729049"
---
# <a name="add-cascading-parameters-to-a-report-report-builder-and-ssrs"></a><span data-ttu-id="104d6-102">Добавление каскадных параметров в отчет (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="104d6-102">Add Cascading Parameters to a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="104d6-103">Каскадирование параметров предоставляет способ управления большими объемами данных отчета.</span><span class="sxs-lookup"><span data-stu-id="104d6-103">Cascading parameters provide a way of managing large amounts of report data.</span></span> <span data-ttu-id="104d6-104">Можно определить набор связанных параметров таким образом, чтобы список значений для одного параметра зависел от значения, выбранного в другом параметре.</span><span class="sxs-lookup"><span data-stu-id="104d6-104">You can define a set of related parameters so that the list of values for one parameter depends on the value chosen in another parameter.</span></span> <span data-ttu-id="104d6-105">Например, первый параметр является независимым и может представлять список категорий продуктов.</span><span class="sxs-lookup"><span data-stu-id="104d6-105">For example, the first parameter is independent and might present a list of product categories.</span></span> <span data-ttu-id="104d6-106">При выборе пользователем категории второй параметр зависит от значения первого параметра.</span><span class="sxs-lookup"><span data-stu-id="104d6-106">When the user selects a category, the second parameter is dependent on the value of the first parameter.</span></span> <span data-ttu-id="104d6-107">Эти значения обновляются списком подкатегорий выбранной категории.</span><span class="sxs-lookup"><span data-stu-id="104d6-107">Its values are updated with a list of subcategories within the chosen category.</span></span> <span data-ttu-id="104d6-108">При просмотре пользователем отчета значения параметров категорий и подкатегорий используются для фильтрации данных отчета.</span><span class="sxs-lookup"><span data-stu-id="104d6-108">When the user views the report, the values for both the category and subcategory parameters are used to filter report data.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
 <span data-ttu-id="104d6-109">При создании каскадирования параметров сначала определяется запрос набора данных и для каждого необходимого каскадного параметра включается параметр запроса.</span><span class="sxs-lookup"><span data-stu-id="104d6-109">To create cascading parameters, you define the dataset query first and include a query parameter for each cascading parameter that you need.</span></span> <span data-ttu-id="104d6-110">Для обеспечения доступных значений также необходимо создать отдельный набор данных для каждого каскадного параметра.</span><span class="sxs-lookup"><span data-stu-id="104d6-110">You must also create a separate dataset for each cascading parameter to provide available values.</span></span> <span data-ttu-id="104d6-111">Дополнительные сведения см. в разделе [Добавление, изменение и удаление допустимых значений параметра отчета (построитель отчетов и службы SSRS)](add-change-or-delete-available-values-for-a-report-parameter.md).</span><span class="sxs-lookup"><span data-stu-id="104d6-111">For more information, see [Add, Change, or Delete Available Values for a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-available-values-for-a-report-parameter.md).</span></span>  
  
 <span data-ttu-id="104d6-112">Для каскадирования параметров важен порядок следования, поскольку запрос набора данных для параметра, расположенного дальше в списке, включает ссылки на каждый параметр, находящийся в списке раньше его.</span><span class="sxs-lookup"><span data-stu-id="104d6-112">Order is important for cascading parameters because the dataset query for a parameter later in the list includes a reference to each parameter that is earlier in the list.</span></span> <span data-ttu-id="104d6-113">Во время выполнения порядок параметров в области данных отчета определяет порядок появления запросов параметров в отчете и, таким образом, порядок выбора пользователем каждого последующего значения параметра.</span><span class="sxs-lookup"><span data-stu-id="104d6-113">At run time, the order of the parameters in the Report Data pane determines the order in which the parameter queries appear in the report, and therefore, the order in which a user chooses each successive parameter value.</span></span>  
  
 <span data-ttu-id="104d6-114">Сведения о создании каскадных параметров с несколькими значениями и о включении функции «Выделить все» см. на странице [How to have a Select All Multivalue Cascading Parameter](https://go.microsoft.com/fwlink/?LinkId=184757).</span><span class="sxs-lookup"><span data-stu-id="104d6-114">For information about creating cascading parameters with multiple values and including the Select All feature, see [How to have a Select All Multivalue Cascading Parameter](https://go.microsoft.com/fwlink/?LinkId=184757).</span></span>  
  
### <a name="to-create-the-main-dataset-with-a-query-that-includes-multiple-related-parameters"></a><span data-ttu-id="104d6-115">Создание основного набора данных с запросом, включающим несколько связанных параметров</span><span class="sxs-lookup"><span data-stu-id="104d6-115">To create the main dataset with a query that includes multiple related parameters</span></span>  
  
1.  <span data-ttu-id="104d6-116">В области данных отчета щелкните правой кнопкой мыши источник данных и выберите команду **Добавить набор данных**.</span><span class="sxs-lookup"><span data-stu-id="104d6-116">In the Report Data pane, right-click a data source, and then click **Add Dataset**.</span></span>  
  
2.  <span data-ttu-id="104d6-117">В поле **Имя**введите имя набора данных.</span><span class="sxs-lookup"><span data-stu-id="104d6-117">In **Name**, type the name of the dataset.</span></span>  
  
3.  <span data-ttu-id="104d6-118">В поле **Источник данных**выберите имя источника данных или нажмите кнопку **Создать** для создания нового источника данных.</span><span class="sxs-lookup"><span data-stu-id="104d6-118">In **Data source**, choose the name of the data source or click **New** to create one.</span></span>  
  
4.  <span data-ttu-id="104d6-119">В поле **Тип запроса**выберите тип запроса для выбранного источника данных.</span><span class="sxs-lookup"><span data-stu-id="104d6-119">In **Query type**, choose the type of query for the selected data source.</span></span> <span data-ttu-id="104d6-120">В этом разделе предполагается использование запроса типа **Текст** .</span><span class="sxs-lookup"><span data-stu-id="104d6-120">In this topic, query type **Text** is assumed.</span></span>  
  
5.  <span data-ttu-id="104d6-121">В поле **Запрос**введите запрос, используемый для получения данных для этого отчета.</span><span class="sxs-lookup"><span data-stu-id="104d6-121">In **Query**, type the query to use to retrieve data for this report.</span></span> <span data-ttu-id="104d6-122">Запрос должен включать следующие части:</span><span class="sxs-lookup"><span data-stu-id="104d6-122">The query must include the following parts:</span></span>  
  
    1.  <span data-ttu-id="104d6-123">Список полей источника данных.</span><span class="sxs-lookup"><span data-stu-id="104d6-123">A list of data source fields.</span></span> <span data-ttu-id="104d6-124">Например, в инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] инструкция SELECT указывает список имен столбцов базы данных из заданной таблицы или представления.</span><span class="sxs-lookup"><span data-stu-id="104d6-124">For example, in a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement, the SELECT statement specifies a list of database column names from a given table or view.</span></span>  
  
    2.  <span data-ttu-id="104d6-125">По одному параметру запроса для каждого каскадного параметра.</span><span class="sxs-lookup"><span data-stu-id="104d6-125">One query parameter for each cascading parameter.</span></span> <span data-ttu-id="104d6-126">Параметр запроса ограничивает данные, полученные из источника данных, путем указания определенных значений для включения или исключения из запроса.</span><span class="sxs-lookup"><span data-stu-id="104d6-126">A query parameter limits the data retrieved from the data source by specifying certain values to include or exclude from the query.</span></span> <span data-ttu-id="104d6-127">Как правило, параметры запроса появляются в предложении ограничения запроса.</span><span class="sxs-lookup"><span data-stu-id="104d6-127">Typically, query parameters occur in a restriction clause in the query.</span></span> <span data-ttu-id="104d6-128">Например, в инструкции SELECT языка [!INCLUDE[tsql](../../includes/tsql-md.md)] параметры запроса обнаруживаются в предложении WHERE.</span><span class="sxs-lookup"><span data-stu-id="104d6-128">For example, in a [!INCLUDE[tsql](../../includes/tsql-md.md)] SELECT statement, query parameters occur in the WHERE clause.</span></span> <span data-ttu-id="104d6-129">Дополнительные сведения см. в разделе «Фильтрация строк с помощью предложений WHERE и HAVING» в документации по службам [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] в [электронной документации по SQL Server](https://go.microsoft.com/fwlink/?linkid=120955).</span><span class="sxs-lookup"><span data-stu-id="104d6-129">For more information, see "Filtering Rows by Using WHERE and HAVING" in the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] documentation in [SQL Server Books Online](https://go.microsoft.com/fwlink/?linkid=120955).</span></span>  
  
6.  <span data-ttu-id="104d6-130">Нажмите кнопку **Запустить** (**!**).</span><span class="sxs-lookup"><span data-stu-id="104d6-130">Click **Run** (**!**).</span></span> <span data-ttu-id="104d6-131">После включения параметров запроса и запуска запроса параметры отчета, соответствующие параметрам запроса, создаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="104d6-131">After you include query parameters and then run the query, report parameters that correspond to the query parameters are automatically created.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="104d6-132">Порядок параметров запроса при первом запуске запроса определяет порядок их создания в отчете.</span><span class="sxs-lookup"><span data-stu-id="104d6-132">The order of query parameters the first time you run a query determines the order that they are created in the report.</span></span> <span data-ttu-id="104d6-133">Способ изменения порядка см. в разделе [Изменение порядка параметров отчета (построитель отчетов и службы SSRS)](change-the-order-of-a-report-parameter-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="104d6-133">To change the order, see [Change the Order of a Report Parameter &#40;Report Builder and SSRS&#41;](change-the-order-of-a-report-parameter-report-builder-and-ssrs.md)</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="104d6-134">Далее создается набор данных, предоставляющий значения для независимого параметра.</span><span class="sxs-lookup"><span data-stu-id="104d6-134">Next, you will create a dataset that provides the values for the independent parameter.</span></span>  
  
### <a name="to-create-a-dataset-to-provide-values-for-an-independent-parameter"></a><span data-ttu-id="104d6-135">Создание набора данных, предоставляющего значения для независимого параметра</span><span class="sxs-lookup"><span data-stu-id="104d6-135">To create a dataset to provide values for an independent parameter</span></span>  
  
1.  <span data-ttu-id="104d6-136">В области данных отчета щелкните правой кнопкой мыши источник данных и выберите команду **Добавить набор данных**.</span><span class="sxs-lookup"><span data-stu-id="104d6-136">In the Report Data pane, right-click a data source, and then click **Add Dataset**.</span></span>  
  
2.  <span data-ttu-id="104d6-137">В поле **Имя**введите имя набора данных.</span><span class="sxs-lookup"><span data-stu-id="104d6-137">In **Name**, type the name of the dataset.</span></span>  
  
3.  <span data-ttu-id="104d6-138">В поле **Источник данных**удостоверьтесь, что имя совпадает с именем источника данных, выбранного в шаге 1.</span><span class="sxs-lookup"><span data-stu-id="104d6-138">In **Data source**, verify the name is the name of the data source you chose in step 1.</span></span>  
  
4.  <span data-ttu-id="104d6-139">В поле **Тип запроса**выберите тип запроса для выбранного источника данных.</span><span class="sxs-lookup"><span data-stu-id="104d6-139">In **Query type**, choose the type of query for the selected data source.</span></span> <span data-ttu-id="104d6-140">В этом разделе предполагается использование запроса типа **Текст** .</span><span class="sxs-lookup"><span data-stu-id="104d6-140">In this topic, query type **Text** is assumed.</span></span>  
  
5.  <span data-ttu-id="104d6-141">В поле **Запрос**введите запрос, используемый для получения значений для этого параметра.</span><span class="sxs-lookup"><span data-stu-id="104d6-141">In **Query**, type the query to use to retrieve values for this parameter.</span></span> <span data-ttu-id="104d6-142">Запросы для независимых параметров обычно не содержат параметры запроса.</span><span class="sxs-lookup"><span data-stu-id="104d6-142">Queries for independent parameters typically do not contain query parameters.</span></span> <span data-ttu-id="104d6-143">Например, чтобы создать запрос для параметра, обеспечивающего все значения категории, можно использовать следующую инструкцию [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="104d6-143">For example, to create a query for a parameter that provides all category values, you might use a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement similar to the following:</span></span>  
  
    ```  
    SELECT DISTINCT <column name> FROM <table>  
    ```  
  
     <span data-ttu-id="104d6-144">Команда SELECT DISTINCT удаляет повторяющиеся значения из результирующего набора, что позволяет получить каждое уникальное значение из указанного столбца указанной таблицы.</span><span class="sxs-lookup"><span data-stu-id="104d6-144">The SELECT DISTINCT command removes duplicate values from the result set so that you get each unique value from the specified column in the specified table.</span></span>  
  
     <span data-ttu-id="104d6-145">Нажмите кнопку **Запустить** (**!**).</span><span class="sxs-lookup"><span data-stu-id="104d6-145">Click **Run** (**!**).</span></span> <span data-ttu-id="104d6-146">Результирующий набор показывает доступные значения для первого параметра.</span><span class="sxs-lookup"><span data-stu-id="104d6-146">The result set shows the values that are available for this first parameter.</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="104d6-147">Далее задаются свойства первого параметра для использования данного набора данных в целях заполнения его доступных значений во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="104d6-147">Next, you will set the properties of the first parameter to use this dataset to populate its available values at run-time.</span></span>  
  
### <a name="to-set-available-values-for-a-report-parameter"></a><span data-ttu-id="104d6-148">Задание допустимых значений параметра отчета</span><span class="sxs-lookup"><span data-stu-id="104d6-148">To set available values for a report parameter</span></span>  
  
1.  <span data-ttu-id="104d6-149">В области данных отчета в папке "Параметры" щелкните первый параметр правой кнопкой мыши и выберите **Свойства параметра**.</span><span class="sxs-lookup"><span data-stu-id="104d6-149">In the Report Data pane, in the Parameters folder, right-click the first parameter, and then click **Parameter Properties**.</span></span>  
  
2.  <span data-ttu-id="104d6-150">В поле **Имя**проверьте правильность имени параметра.</span><span class="sxs-lookup"><span data-stu-id="104d6-150">In **Name**, verify that the name of the parameter is correct.</span></span>  
  
3.  <span data-ttu-id="104d6-151">Нажмите кнопку **Допустимые значения**.</span><span class="sxs-lookup"><span data-stu-id="104d6-151">Click **Available Values**.</span></span>  
  
4.  <span data-ttu-id="104d6-152">Щелкните **Получать значения из запроса**.</span><span class="sxs-lookup"><span data-stu-id="104d6-152">Click **Get values from a query**.</span></span> <span data-ttu-id="104d6-153">Появится три поля.</span><span class="sxs-lookup"><span data-stu-id="104d6-153">Three fields appear.</span></span>  
  
5.  <span data-ttu-id="104d6-154">В раскрывающемся списке поля **Набор данных**выберите имя набора данных, созданного в предыдущей процедуре.</span><span class="sxs-lookup"><span data-stu-id="104d6-154">In **Dataset**, from the drop-down list, click the name of the dataset you created in the previous procedure.</span></span>  
  
6.  <span data-ttu-id="104d6-155">В поле **Значение** щелкните имя поля, предоставляющего значение параметра.</span><span class="sxs-lookup"><span data-stu-id="104d6-155">In **Value** field, click the name of the field that provides the parameter value.</span></span>  
  
7.  <span data-ttu-id="104d6-156">В поле **Метка** щелкните имя поля, предоставляющего метку параметра.</span><span class="sxs-lookup"><span data-stu-id="104d6-156">In **Label** field, click the name of the field that provides the parameter label.</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="104d6-157">Далее создается набор данных, предоставляющий значения для зависимого параметра.</span><span class="sxs-lookup"><span data-stu-id="104d6-157">Next, you will create a dataset that provides the values for a dependent parameter.</span></span>  
  
### <a name="to-create-a-dataset-to-provide-values-for-a-dependent-parameter"></a><span data-ttu-id="104d6-158">Создание набора данных, предоставляющего значения для зависимого параметра</span><span class="sxs-lookup"><span data-stu-id="104d6-158">To create a dataset to provide values for a dependent parameter</span></span>  
  
1.  <span data-ttu-id="104d6-159">В области данных отчета щелкните правой кнопкой мыши источник данных и выберите команду **Добавить набор данных**.</span><span class="sxs-lookup"><span data-stu-id="104d6-159">In the Report Data pane, right-click a data source, and then click **Add Dataset**.</span></span>  
  
2.  <span data-ttu-id="104d6-160">В поле **Имя**введите имя набора данных.</span><span class="sxs-lookup"><span data-stu-id="104d6-160">In **Name**, type the name of the dataset.</span></span>  
  
3.  <span data-ttu-id="104d6-161">В поле **Источник данных**удостоверьтесь, что имя совпадает с именем источника данных, выбранного в шаге 1.</span><span class="sxs-lookup"><span data-stu-id="104d6-161">In **Data source**, verify the name is the name of the data source you chose in step 1.</span></span>  
  
4.  <span data-ttu-id="104d6-162">В поле **Тип запроса**выберите тип запроса для выбранного источника данных.</span><span class="sxs-lookup"><span data-stu-id="104d6-162">In **Query type**, choose the type of query for the selected data source.</span></span> <span data-ttu-id="104d6-163">В этом разделе предполагается использование запроса типа **Текст** .</span><span class="sxs-lookup"><span data-stu-id="104d6-163">In this topic, query type **Text** is assumed.</span></span>  
  
5.  <span data-ttu-id="104d6-164">В поле **Запрос**введите запрос, используемый для получения значений для этого параметра.</span><span class="sxs-lookup"><span data-stu-id="104d6-164">In **Query**, type the query to use to retrieve values for this parameter.</span></span> <span data-ttu-id="104d6-165">Запросы для зависимых параметров обычно включают параметры запроса для каждого параметра, от которого зависит данный параметр.</span><span class="sxs-lookup"><span data-stu-id="104d6-165">Queries for dependent parameters typically include query parameters for each parameter that this parameter is dependent on.</span></span> <span data-ttu-id="104d6-166">Например, чтобы создать запрос для параметра, обеспечивающего все значения подкатегории (зависимый параметр) для категории (независимый параметр), можно использовать следующую инструкцию [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="104d6-166">For example, to create a query for a parameter that provides all subcategory (dependent parameter) values for a category (independent parameter), you might use a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement similar to the following:</span></span>  
  
    ```  
    SELECT DISTINCT Subcategory FROM <table>   
    WHERE (Category = @Category)  
    ```  
  
     <span data-ttu-id="104d6-167">В предложении WHERE Категория — это имя поля из \<table> и @Category является параметром запроса.</span><span class="sxs-lookup"><span data-stu-id="104d6-167">In the WHERE clause, Category is the name of a field from \<table> and @Category is a query parameter.</span></span> <span data-ttu-id="104d6-168">Эта инструкция возвращает список подкатегорий для категории, указанной в параметре @Category.</span><span class="sxs-lookup"><span data-stu-id="104d6-168">This statement produces a list of subcategories for the category specified in @Category.</span></span> <span data-ttu-id="104d6-169">Во время выполнения данное значение будет заполнено значением, которое выбирает пользователь для параметра отчета с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="104d6-169">At run time, this value will be filled in with the value that the user chooses for the report parameter that has the same name.</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="104d6-170">Далее устанавливаются свойства второго параметра в целях использования этого набора данных для наполнения его доступных значений во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="104d6-170">Next, you will set the properties of the second parameter to use this dataset to populate its available values at run time.</span></span>  
  
### <a name="to-set-available-values-for-a-report-parameter"></a><span data-ttu-id="104d6-171">Задание допустимых значений параметра отчета</span><span class="sxs-lookup"><span data-stu-id="104d6-171">To set available values for a report parameter</span></span>  
  
1.  <span data-ttu-id="104d6-172">В области данных отчета в папке "Параметры" щелкните первый параметр правой кнопкой мыши и выберите **Свойства параметра**.</span><span class="sxs-lookup"><span data-stu-id="104d6-172">In the Report Data pane, in the Parameters folder, right-click the first parameter, and then click **Parameter Properties**.</span></span>  
  
2.  <span data-ttu-id="104d6-173">В поле **Имя**проверьте правильность имени параметра.</span><span class="sxs-lookup"><span data-stu-id="104d6-173">In **Name**, verify that the name of the parameter is correct.</span></span>  
  
3.  <span data-ttu-id="104d6-174">Нажмите кнопку **Допустимые значения**.</span><span class="sxs-lookup"><span data-stu-id="104d6-174">Click **Available Values**.</span></span>  
  
4.  <span data-ttu-id="104d6-175">Щелкните **Получать значения из запроса**.</span><span class="sxs-lookup"><span data-stu-id="104d6-175">Click **Get values from a query**.</span></span>  
  
5.  <span data-ttu-id="104d6-176">В раскрывающемся списке поля **Набор данных**выберите имя набора данных, созданного в предыдущей процедуре.</span><span class="sxs-lookup"><span data-stu-id="104d6-176">In **Dataset**, from the drop-down list, click the name of the dataset you created in the previous procedure.</span></span>  
  
6.  <span data-ttu-id="104d6-177">В поле **Значение** щелкните имя поля, предоставляющего значение параметра.</span><span class="sxs-lookup"><span data-stu-id="104d6-177">In **Value** field, click the name of the field that provides the parameter value.</span></span>  
  
7.  <span data-ttu-id="104d6-178">В поле **Метка** щелкните имя поля, предоставляющего метку параметра.</span><span class="sxs-lookup"><span data-stu-id="104d6-178">In **Label** field, click the name of the field that provides the parameter label.</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-test-the-cascading-parameters"></a><span data-ttu-id="104d6-179">Проверка каскадирования параметров</span><span class="sxs-lookup"><span data-stu-id="104d6-179">To test the cascading parameters</span></span>  
  
1.  <span data-ttu-id="104d6-180">Нажмите кнопку **Запустить**.</span><span class="sxs-lookup"><span data-stu-id="104d6-180">Click **Run**.</span></span>  
  
2.  <span data-ttu-id="104d6-181">В раскрывающемся списке выберите значение для первого, независимого параметра.</span><span class="sxs-lookup"><span data-stu-id="104d6-181">From the drop-down list for the first, independent parameter, choose a value.</span></span>  
  
     <span data-ttu-id="104d6-182">Обработчик отчетов запускает запрос набора данных для следующего параметра и передает ему значение, выбранное для первого параметра.</span><span class="sxs-lookup"><span data-stu-id="104d6-182">The report processor runs the dataset query for the next parameter and passes it the value you chose for the first parameter.</span></span> <span data-ttu-id="104d6-183">Раскрывающийся список для второго параметра заполняется доступными значениями с учетом значения первого параметра.</span><span class="sxs-lookup"><span data-stu-id="104d6-183">The drop-down list for the second parameter is populated with the available values based on the first parameter value.</span></span>  
  
3.  <span data-ttu-id="104d6-184">Выберите значение в раскрывающемся списке для второго, зависимого параметра.</span><span class="sxs-lookup"><span data-stu-id="104d6-184">From the drop-down list for the second, dependent parameter, choose a value.</span></span>  
  
     <span data-ttu-id="104d6-185">После выбора последнего параметра отчет не запускается автоматически, что позволяет переопределить выбор.</span><span class="sxs-lookup"><span data-stu-id="104d6-185">The report does not run automatically after you choose the last parameter so that you can change your choice.</span></span>  
  
4.  <span data-ttu-id="104d6-186">Нажмите кнопку **Просмотреть отчет**.</span><span class="sxs-lookup"><span data-stu-id="104d6-186">Click **View Report**.</span></span> <span data-ttu-id="104d6-187">Экран отчета обновляется на основании выбранных параметров.</span><span class="sxs-lookup"><span data-stu-id="104d6-187">The report updates the display based on the parameters you have chosen.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="104d6-188">См. также:</span><span class="sxs-lookup"><span data-stu-id="104d6-188">See Also</span></span>  
 <span data-ttu-id="104d6-189">[Добавить, изменить или удалить параметр отчета &#40;построитель отчетов и SSRS&#41;](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="104d6-189">[Add, Change, or Delete a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="104d6-190">[Параметры отчета &#40;построитель отчетов и конструктор отчетов&#41;](report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="104d6-190">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="104d6-191">[Учебник. Добавление параметра в отчет &#40;построитель отчетов&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="104d6-191">[Tutorial: Add a Parameter to Your Report &#40;Report Builder&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span></span>  
 <span data-ttu-id="104d6-192">[Учебники &#40;построитель отчетов&#41;](../report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="104d6-192">[Tutorials &#40;Report Builder&#41;](../report-builder-tutorials.md) </span></span>  
 <span data-ttu-id="104d6-193">[Добавление фильтров набора данных, фильтров области данных и групповых фильтров &#40;построитель отчетов и SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="104d6-193">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 [<span data-ttu-id="104d6-194">Внедренные и общие наборы данных отчета (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="104d6-194">Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;</span></span>](../report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md)  
  
  
