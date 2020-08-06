---
title: Построение запроса в конструкторе реляционных запросов (построитель отчетов и службы SSRS) | Документация Майкрософт
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 28b25861-f3b4-4c3e-a9b0-03d6e4cfea26
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 555d72c4d3bca8677d04fdc4160639f004d6bbe9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739425"
---
# <a name="build-a-query-in-the-relational-query-designer-report-builder-and-ssrs"></a><span data-ttu-id="23993-102">Построение запроса в конструкторе реляционных запросов (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="23993-102">Build a Query in the Relational Query Designer (Report Builder and SSRS)</span></span>
  <span data-ttu-id="23993-103">С помощью конструктора запросов можно указывать, какие данные должны быть получены для набора данных отчета из внешнего источника данных.</span><span class="sxs-lookup"><span data-stu-id="23993-103">A query designer helps you specify which data to retrieve from an external data source for a report dataset.</span></span> <span data-ttu-id="23993-104">Конструктор запросов используется при построении запроса с помощью мастера или создании запроса набора данных.</span><span class="sxs-lookup"><span data-stu-id="23993-104">You use a query designer when you build a query in a wizard or create a dataset query.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
 <span data-ttu-id="23993-105">Набор данных основан на источнике данных.</span><span class="sxs-lookup"><span data-stu-id="23993-105">A dataset is based on a data source.</span></span> <span data-ttu-id="23993-106">От типа источника данных и среды создания отчетов зависит, какой конструктор запросов открывается при определении запроса набора данных.</span><span class="sxs-lookup"><span data-stu-id="23993-106">The type of data source and the authoring environment determines which query designer opens when you define the dataset query.</span></span> <span data-ttu-id="23993-107">Функции конструктора запросов различаются в зависимости от базового источника данных.</span><span class="sxs-lookup"><span data-stu-id="23993-107">Query designer features vary based on the underlying data source.</span></span> <span data-ttu-id="23993-108">Дополнительные сведения о слоях данных см. [в разделе подключения к данным, источники данных и строки подключения в построитель отчетов](../data-connections-data-sources-and-connection-strings-in-report-builder.md) или [подключения к данным, источники данных и строки подключения в Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="23993-108">For more information about data layers, see [Data Connections, Data Sources, and Connection Strings in Report Builder](../data-connections-data-sources-and-connection-strings-in-report-builder.md) or [Data Connections, Data Sources, and Connection Strings in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md).</span></span>  
  
 <span data-ttu-id="23993-109">Конструктор запросов можно использовать для выполнения следующих задач:</span><span class="sxs-lookup"><span data-stu-id="23993-109">You can use a query designer for the following tasks:</span></span>  
  
-   <span data-ttu-id="23993-110">Просмотр метаданных нескольких схем из внешнего источника данных.</span><span class="sxs-lookup"><span data-stu-id="23993-110">Explore the metadata for multiple schemas on the external data source</span></span>  
  
-   <span data-ttu-id="23993-111">Указание полей, получаемых для набора данных.</span><span class="sxs-lookup"><span data-stu-id="23993-111">Specify fields to retrieve for the dataset</span></span>  
  
-   <span data-ttu-id="23993-112">Задание связей между двумя объектами, например таблицами.</span><span class="sxs-lookup"><span data-stu-id="23993-112">Specify relationships between two objects such as tables</span></span>  
  
-   <span data-ttu-id="23993-113">Задание фильтров для ограничения данных до того, как они будут получены в качестве данных отчета.</span><span class="sxs-lookup"><span data-stu-id="23993-113">Specify filters to restrict the data before it is retrieved as report data</span></span>  
  
-   <span data-ttu-id="23993-114">Указание, следует ли создавать параметры.</span><span class="sxs-lookup"><span data-stu-id="23993-114">Indicate whether to create parameters</span></span>  
  
-   <span data-ttu-id="23993-115">Задание агрегатов для выполнения вычислений на внешнем источнике данных</span><span class="sxs-lookup"><span data-stu-id="23993-115">Specify aggregates to perform calculations on the external data source</span></span>  
  
 <span data-ttu-id="23993-116">После открытия конструктора запросов построение запроса выполняется аналогично построению внедренного или общего набора данных.</span><span class="sxs-lookup"><span data-stu-id="23993-116">After you open a query designer, you build a query in the same way for either an embedded dataset or a shared dataset.</span></span> <span data-ttu-id="23993-117">Приведенные ниже процедуры используют запрос к внедренному набору данных.</span><span class="sxs-lookup"><span data-stu-id="23993-117">The following procedures use an embedded dataset query.</span></span>  
  
 <span data-ttu-id="23993-118">Дополнительные сведения см. в разделе [Пользовательский интерфейс конструктора реляционных запросов &#40;построитель отчетов&#41;](relational-query-designer-user-interface-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="23993-118">For more information, see [Relational Query Designer User Interface &#40;Report Builder&#41;](relational-query-designer-user-interface-report-builder.md).</span></span>  
  
### <a name="to-build-a-query-for-an-embedded-dataset-in-report-design-view"></a><span data-ttu-id="23993-119">Построение запроса к внедренному набору данных в представлении конструктора отчетов</span><span class="sxs-lookup"><span data-stu-id="23993-119">To build a query for an embedded dataset in Report Design View</span></span>  
  
1.  <span data-ttu-id="23993-120">Откройте конструктор запросов.</span><span class="sxs-lookup"><span data-stu-id="23993-120">Open the query designer.</span></span> <span data-ttu-id="23993-121">В области данных отчета щелкните правой кнопкой мыши набор данных и выберите пункт **Запрос**.</span><span class="sxs-lookup"><span data-stu-id="23993-121">In the Report Data pane, right-click the dataset, and then click **Query**.</span></span>  
  
     <span data-ttu-id="23993-122">Откроется конструктор запросов, связанный с источником данных.</span><span class="sxs-lookup"><span data-stu-id="23993-122">The query designer that is associated with the data source opens.</span></span>  
  
2.  <span data-ttu-id="23993-123">На панели представления базы данных разверните папки, которые отображают иерархическое представление объектов схемы базы данных, например таблиц, представлений и хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="23993-123">In the Database view pane, expand the folders that display a hierarchical view of database schema objects such as tables, views, and stored procedures.</span></span> <span data-ttu-id="23993-124">Установите флажок выбора, чтобы выбрать все поля для объекта, или разверните узел для выбора отдельных полей.</span><span class="sxs-lookup"><span data-stu-id="23993-124">Click the select box to select all fields for an object or expand the node to select individual fields.</span></span>  
  
     <span data-ttu-id="23993-125">Поля, выбранные на панели представления базы данных, будут отображаться на панели **Выбранные поля** .</span><span class="sxs-lookup"><span data-stu-id="23993-125">As you select fields from the Database view pane, the **Select fields** pane displays your selections.</span></span>  
  
     <span data-ttu-id="23993-126">Если поля выбраны в нескольких связанных таблицах базы данных, воспользуйтесь панелью «Связи», чтобы просмотреть связи таблиц, обнаруженные в схеме базы данных.</span><span class="sxs-lookup"><span data-stu-id="23993-126">If you select fields from more than one related database table, use the Relationships pane to view the table relationships that were detected from the database schema.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="23993-127">Список полей набора данных отображается в области данных отчета.</span><span class="sxs-lookup"><span data-stu-id="23993-127">The list of dataset fields appears in the Report Data pane.</span></span>  
  
### <a name="to-specify-limits-for-a-query"></a><span data-ttu-id="23993-128">Задание пределов для запроса</span><span class="sxs-lookup"><span data-stu-id="23993-128">To specify limits for a query</span></span>  
  
1.  <span data-ttu-id="23993-129">В конструкторе реляционных запросов убедитесь в наличии выбранных полей и проверьте, отображаются ли они на панели **Выбранные поля** .</span><span class="sxs-lookup"><span data-stu-id="23993-129">In the relational query designer, verify that you have fields selected and that the fields appear in the **Selected fields** pane.</span></span>  
  
2.  <span data-ttu-id="23993-130">На панели инструментов панели «Примененные фильтры» выберите **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="23993-130">In the Applied filters pane toolbar, click **Add Filter**.</span></span> <span data-ttu-id="23993-131">Появится строка нового фильтра.</span><span class="sxs-lookup"><span data-stu-id="23993-131">A new filter row appears.</span></span>  
  
3.  <span data-ttu-id="23993-132">Щелкните в поле **Имя поля**, чтобы отобразить раскрывающийся список полей, затем щелкните имя поля, по которому следует выполнять фильтрацию.</span><span class="sxs-lookup"><span data-stu-id="23993-132">In **Field name**, click to display the drop-down list of fields, and then click the name of the field that you want to filter by.</span></span> <span data-ttu-id="23993-133">Например, чтобы отфильтровать по количеству, щелкните поле, содержащее количество элементов.</span><span class="sxs-lookup"><span data-stu-id="23993-133">For example, to filter by quantity, click the field that contains the number of items.</span></span>  
  
4.  <span data-ttu-id="23993-134">Щелкните в поле **Оператор**, чтобы отобразить раскрывающийся список операторов, затем выберите оператор сравнения для использования в фильтре.</span><span class="sxs-lookup"><span data-stu-id="23993-134">In **Operator**, click to display the drop-down list of operators, and then select the comparison operator to use in the filter.</span></span>  
  
5.  <span data-ttu-id="23993-135">В поле **Значение**введите значение, по которому следует отфильтровать данные.</span><span class="sxs-lookup"><span data-stu-id="23993-135">In **Value**, type the value that you want to filter by.</span></span> <span data-ttu-id="23993-136">Например, для фильтрации по количеству более 100 введите «100».</span><span class="sxs-lookup"><span data-stu-id="23993-136">For example, to filter on quantity greater than 100, type 100.</span></span>  
  
6.  <span data-ttu-id="23993-137">Выберите режим параметра в этой строке, чтобы создать параметр набора данных, позволяющий пользователю вводить значение фильтра.</span><span class="sxs-lookup"><span data-stu-id="23993-137">Select the parameter option in this row to create a dataset parameter to enable a user to specify a filter value.</span></span> <span data-ttu-id="23993-138">Автоматически будет создан параметр отчета, соответствующий параметру набора данных.</span><span class="sxs-lookup"><span data-stu-id="23993-138">A report parameter that matches the dataset parameter is automatically created.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="23993-139">Список полей набора данных отображается в области данных отчета.</span><span class="sxs-lookup"><span data-stu-id="23993-139">The list of dataset fields appears in the Report Data pane.</span></span>  
  
### <a name="to-view-a-query-result-set"></a><span data-ttu-id="23993-140">Просмотр результирующего набора запроса</span><span class="sxs-lookup"><span data-stu-id="23993-140">To view a query result set</span></span>  
  
1.  <span data-ttu-id="23993-141">На панели инструментов конструктора запросов нажмите кнопку **Выполнить запрос (!)** .</span><span class="sxs-lookup"><span data-stu-id="23993-141">On the query designer toolbar, click **Run Query (!)**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="23993-142">В конструкторе запросов для выполнения запроса и получения результирующего набора используются учетные данные времени разработки.</span><span class="sxs-lookup"><span data-stu-id="23993-142">The query designer uses design time credentials to run the query and retrieve the result set.</span></span> <span data-ttu-id="23993-143">Дополнительные сведения см. в разделе [Указание учетных данных в построителе отчетов](../specify-credentials-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="23993-143">For more information, see [Specify Credentials in Report Builder](../specify-credentials-in-report-builder.md).</span></span>  
  
 <span data-ttu-id="23993-144">Будет выполнен запрос к источнику данных, и в панели результатов запроса будут возвращены данные примера.</span><span class="sxs-lookup"><span data-stu-id="23993-144">The query runs on the data source and returns example data in the Query results pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23993-145">См. также:</span><span class="sxs-lookup"><span data-stu-id="23993-145">See Also</span></span>  
 <span data-ttu-id="23993-146">[Добавление данных в построитель отчетов &#40;отчетов и SSRS&#41;](report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="23993-146">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-datasets-ssrs.md) </span></span>  
 <span data-ttu-id="23993-147">[Добавление данных из внешних источников данных &#40;SSRS&#41;](add-data-from-external-data-sources-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="23993-147">[Add Data from External Data Sources &#40;SSRS&#41;](add-data-from-external-data-sources-ssrs.md) </span></span>  
 <span data-ttu-id="23993-148">[Конструкторы запросов &#40;построитель отчетов&#41;](../query-designers-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="23993-148">[Query Designers &#40;Report Builder&#41;](../query-designers-report-builder.md) </span></span>  
 <span data-ttu-id="23993-149">[Создание общего или внедренного набора данных (построитель отчетов и службы SSRS)](create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="23993-149">[Create a Shared Dataset or Embedded Dataset &#40;Report Builder and SSRS&#41;](create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="23993-150">[Представление конструктора отчетов (построитель отчетов)](../report-builder/report-design-view-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="23993-150">[Report Design View &#40;Report Builder&#41;](../report-builder/report-design-view-report-builder.md) </span></span>  
 <span data-ttu-id="23993-151">[Представление конструктора общих наборов данных (построитель отчетов)](../report-builder/shared-dataset-design-view-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="23993-151">[Shared Dataset Design View &#40;Report Builder&#41;](../report-builder/shared-dataset-design-view-report-builder.md) </span></span>  
 [<span data-ttu-id="23993-152">Конструкторы запросов служб Reporting Services</span><span class="sxs-lookup"><span data-stu-id="23993-152">Reporting Services Query Designers</span></span>](../reporting-services-query-designers.md)  
  
  
