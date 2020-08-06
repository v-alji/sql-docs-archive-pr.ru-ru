---
title: Создание общего или внедренного набора данных (построитель отчетов и службы SSRS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d1d7bc71-f0e9-4ce5-b3ad-6fee54388a31
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fca74e1ba7965eeef6ce562e79e378af5bb9e145
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729113"
---
# <a name="create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs"></a><span data-ttu-id="6e8b5-102">Создание общего или внедренного набора данных (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="6e8b5-102">Create a Shared Dataset or Embedded Dataset (Report Builder and SSRS)</span></span>
  <span data-ttu-id="6e8b5-103">Можно создавать внедренные наборы данных для использования в отдельных отчетах или общие наборы данных для сохранения на сервере отчетов и использования в нескольких отчетах.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-103">You can create an embedded dataset for use in a single report or a shared dataset to save to a report server, for use by multiple reports.</span></span> <span data-ttu-id="6e8b5-104">Для создания набора данных необходим внедренный или общий источник данных.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-104">To create a dataset, you must have an embedded or shared data source.</span></span>

 <span data-ttu-id="6e8b5-105">Используйте построитель отчетов для выполнения следующих задач:</span><span class="sxs-lookup"><span data-stu-id="6e8b5-105">Use Report Builder to do the following tasks:</span></span>

-   <span data-ttu-id="6e8b5-106">Создание общих наборов данных в режиме конструктора наборов данных.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-106">Create a shared dataset in Dataset Design View.</span></span> <span data-ttu-id="6e8b5-107">Общие наборы данных должны использовать опубликованные общие источники данных.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-107">Shared datasets must use published shared data sources.</span></span>

-   <span data-ttu-id="6e8b5-108">Создание внедренных наборов данных в режиме конструктора отчетов.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-108">Create an embedded dataset in Report Design View.</span></span>

-   <span data-ttu-id="6e8b5-109">Сохранение наборов данных непосредственно на сервере отчетов или сайте SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-109">Save the dataset directly to the report server or SharePoint site.</span></span>

 <span data-ttu-id="6e8b5-110">Используйте конструктор отчетов среды [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] для выполнения следующих задач:</span><span class="sxs-lookup"><span data-stu-id="6e8b5-110">Use Report Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] to do the following tasks:</span></span>

1.  <span data-ttu-id="6e8b5-111">Создание общего набора данных в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-111">Create a shared dataset in Solution Explorer.</span></span> <span data-ttu-id="6e8b5-112">Общие наборы данных должны использовать источники данных из папки «Общие источники данных» в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-112">Shared datasets must use data sources from the Shared Data Sources folder in Solution Explorer.</span></span>

2.  <span data-ttu-id="6e8b5-113">Создание внедренного набора данных в области данных отчета.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-113">Create an embedded dataset in the Report Data pane.</span></span>

3.  <span data-ttu-id="6e8b5-114">При необходимости разверните общие наборы данных и общие источники данных в отчете.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-114">Optionally deploy the shared datasets and shared data source with the report.</span></span> <span data-ttu-id="6e8b5-115">Используйте свойства проекта для указания путей к папкам на сервере отчетов или сайте SharePoint для каждого типа элементов.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-115">For each type of item, use Project Properties to specify paths to folders on the report server or SharePoint site.</span></span>

 <span data-ttu-id="6e8b5-116">Дополнительные сведения см. в разделе [Внедренные и общие наборы данных отчета (построитель отчетов и службы SSRS)](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="6e8b5-116">For more information, see [Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md).</span></span>

> [!NOTE]
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]

### <a name="to-open-report-builder-and-create-a-shared-dataset"></a><span data-ttu-id="6e8b5-117">Открытие построителя отчетов и создание общего набора данных</span><span class="sxs-lookup"><span data-stu-id="6e8b5-117">To open Report Builder and create a shared dataset</span></span>

1.  <span data-ttu-id="6e8b5-118">Откройте построитель отчетов.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-118">Open Report Builder.</span></span> <span data-ttu-id="6e8b5-119">Откроется панель **Создание отчета или набора данных** , как показано на следующих рисунках.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-119">The **New report or dataset pane** opens, as shown in the following figure:</span></span>

     <span data-ttu-id="6e8b5-120">![rs_NewSharedDataset](../media/rs-newshareddataset.gif "rs_NewSharedDataset")</span><span class="sxs-lookup"><span data-stu-id="6e8b5-120">![rs_NewSharedDataset](../media/rs-newshareddataset.gif "rs_NewSharedDataset")</span></span>

    > [!NOTE]
    >  <span data-ttu-id="6e8b5-121"> Если страница **Создание панели отчета или набора данных** не откроется с помощью кнопки построителя отчетов, выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-121">If the **New report or dataset pane** does not appear, from the Report Builder button, click **New**.</span></span>

2.  <span data-ttu-id="6e8b5-122">На левой панели в **Создать набор данных**выберите **Общий набор данных**.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-122">In the left pane, under **Create a dataset**, click **Shared Dataset**.</span></span>

3.  <span data-ttu-id="6e8b5-123">На правой панели выберите **Обзор** , чтобы выбрать общий источник данных на сервере отчетов, а затем выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-123">In the right pane, click **Browse** to select a shared data source from the report server, and then click **Create**.</span></span> <span data-ttu-id="6e8b5-124">Откроется конструктор запросов, связанный с общим источником данных.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-124">The query designer associated with the shared data source opens.</span></span>

4.  <span data-ttu-id="6e8b5-125">В конструкторе запросов укажите поля, которые необходимо включить в набор данных.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-125">In the query designer, specify the fields to include in the dataset.</span></span>

5.  <span data-ttu-id="6e8b5-126">Нажмите кнопку **выполнить** (**!**), чтобы выполнить запрос.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-126">Click **Run** (**!**) to run the query.</span></span>

6.  <span data-ttu-id="6e8b5-127">На кнопке **Построитель отчетов** выберите **Сохранить** или **Сохранить как** , чтобы сохранить общий набор данных на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-127">On the **Report Builder** button, click **Save** or **Save As** to save the shared dataset to the report server.</span></span>

7.  <span data-ttu-id="6e8b5-128">Для выхода из построителя отчетов выберите **Построитель отчетов**, а затем выберите **Выйти из построителя отчетов**.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-128">To exit Report Builder, click **Report Builder**, and then click **Exit Report Builder**.</span></span> <span data-ttu-id="6e8b5-129">Для работы с отчетами выберите **Построитель отчетов**и нажмите кнопку **Создать** или **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-129">To work with reports, click **Report Builder**, and then click **New** or **Open**.</span></span>

### <a name="to-set-query-parameter-options"></a><span data-ttu-id="6e8b5-130">Задание настроек параметров запросов</span><span class="sxs-lookup"><span data-stu-id="6e8b5-130">To set query parameter options</span></span>

1.  <span data-ttu-id="6e8b5-131">Откройте построитель отчетов.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-131">Open Report Builder.</span></span>

2.  <span data-ttu-id="6e8b5-132">Нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-132">Click **Open**.</span></span>

3.  <span data-ttu-id="6e8b5-133">Перейдите к серверу отчетов и выберите папку общего источника данных.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-133">Browse to the report server, and select the folder for the shared data source.</span></span>

4.  <span data-ttu-id="6e8b5-134">В раскрывающемся списке поля **Элементы типа**выберите наборы данных (\*.rsd).</span><span class="sxs-lookup"><span data-stu-id="6e8b5-134">In **Items of type**, click Datasets (\*.rsd) in the drop-down list.</span></span>

5.  <span data-ttu-id="6e8b5-135">Выберите общий набор данных, а затем щелкните **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-135">Select the shared dataset, and then click **Open**.</span></span> <span data-ttu-id="6e8b5-136">Откроется связанный конструктор запросов.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-136">The associated query designer opens.</span></span>

6.  <span data-ttu-id="6e8b5-137">На ленте выберите **Свойства набора данных**.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-137">On the Ribbon, click **Dataset Properties**.</span></span>

7.  <span data-ttu-id="6e8b5-138">Нажмите **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-138">Click **Parameters**.</span></span> <span data-ttu-id="6e8b5-139">На этой странице задайте значение по умолчанию для константы или выражения, пометьте параметр как доступный "только для чтения", допускающий значения NULL или имеющий состояние **Не указывать в запросе**.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-139">On this page, set a default value to a constant or an expression, mark the parameter as read-only, nullable, or **Omit From Query**.</span></span> <span data-ttu-id="6e8b5-140">Дополнительные сведения см. в статье [Диалоговое окно "Свойства набора данных" — "Параметры" (построитель отчетов)](../dataset-properties-dialog-box-parameters-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="6e8b5-140">For more information, see [Dataset Properties Dialog Box, Parameters &#40;Report Builder&#41;](../dataset-properties-dialog-box-parameters-report-builder.md).</span></span>

8.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]


### <a name="to-create-a-dataset-from-a-sql-server-relational-database"></a><span data-ttu-id="6e8b5-141">Создание набора данных в реляционной базе данных SQL Server</span><span class="sxs-lookup"><span data-stu-id="6e8b5-141">To create a dataset from a SQL Server relational database</span></span>

1.  <span data-ttu-id="6e8b5-142">В области данных отчета щелкните правой кнопкой мыши имя источника данных и выберите команду **Добавить набор данных**.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-142">In the Report Data pane, right-click the name of the data source, and then click **Add Dataset**.</span></span> <span data-ttu-id="6e8b5-143">Откроется страница **Запрос** диалогового окна **Свойства набора данных** .</span><span class="sxs-lookup"><span data-stu-id="6e8b5-143">The **Query** page of the **Dataset Properties** dialog box opens.</span></span>

2.  <span data-ttu-id="6e8b5-144">В поле **Имя**введите имя для набора данных или примите имя по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-144">In **Name**, type a name for the dataset or accept the default name.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="6e8b5-145">Имя набора данных используется внутри запроса.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-145">The dataset name is used internally within the report.</span></span> <span data-ttu-id="6e8b5-146">В целях упорядочивания рекомендуется называть набор данных именем, описывающим данные, возвращаемые запросом.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-146">For clarity, we recommend that the name of the dataset describe the data that the query returns.</span></span>

3.  <span data-ttu-id="6e8b5-147">В поле **Источник данных**перейдите и выберите существующий общий источник данных либо нажмите кнопку **Создать** , чтобы создать новый внедренный источник данных.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-147">In **Data source**, browse to and select the name of an existing shared data source, or click **New** to create a new embedded data source.</span></span>

4.  <span data-ttu-id="6e8b5-148">Задайте значение для параметра **Тип запроса** .</span><span class="sxs-lookup"><span data-stu-id="6e8b5-148">Select a **Query type** option.</span></span> <span data-ttu-id="6e8b5-149">Параметры зависят от типа источника данных.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-149">Options depend on the data source type.</span></span>

    -   <span data-ttu-id="6e8b5-150">Выберите **Текст** для записи запроса, использующего язык запросов источника данных.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-150">Select **Text** to write a query using the query language of the data source.</span></span>

    -   <span data-ttu-id="6e8b5-151">Выберите **Таблица** , чтобы возвратить все поля в таблице реляционной базы данных.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-151">Select **Table** to return all the fields in a relational database table.</span></span>

    -   <span data-ttu-id="6e8b5-152">Выберите **StoredProcedure** , чтобы выполнить хранимую процедуру по имени.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-152">Select **StoredProcedure** to run a stored procedure by name.</span></span>

5.  <span data-ttu-id="6e8b5-153">В поле **Запрос**введите имя запроса,z хранимой процедуры или таблицы.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-153">In **Query**, type the query, stored procedure, or table name.</span></span> <span data-ttu-id="6e8b5-154">Также можно нажать кнопку **Конструктор запросов** , чтобы открыть графический или текстовый редактор запросов, либо кнопку **Импорт** , чтобы импортировать запрос из существующего отчета.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-154">Alternatively, click **Query Designer** to open the graphical or text-based query designer tool, or **Import** to import the query from an existing report.</span></span>

     <span data-ttu-id="6e8b5-155">В некоторых случаях указанную в запросе коллекцию полей можно определить, выполнив запрос к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-155">In a few cases, the field collection specified by the query can only be determined by running the query on the data source.</span></span> <span data-ttu-id="6e8b5-156">Например, хранимая процедура может возвратить в результирующем наборе переменный набор полей.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-156">For example, a stored procedure may return a variable set of fields in the result set.</span></span> <span data-ttu-id="6e8b5-157">Нажмите кнопку **Обновить поля** , чтобы выполнить запрос к источнику данных и получить имена полей, необходимые для заполнения коллекции полей набора данных в области данных отчета.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-157">Click **Refresh Fields** to run the query on the data source and retrieve the field names that are needed to populate the dataset field collection in the Report Data pane.</span></span> <span data-ttu-id="6e8b5-158">Коллекция полей появится в узле набора данных после того, как диалоговое окно **Свойства набора данных** будет закрыто.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-158">The field collection appears under the dataset node after you close the **Dataset Properties** dialog box.</span></span>

6.  <span data-ttu-id="6e8b5-159">В поле **Время ожидания**введите, сколько секунд сервер отчетов должен ждать ответа базы данных.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-159">In **Timeout**, type the number of seconds that the report server waits for a response from the database.</span></span> <span data-ttu-id="6e8b5-160">Значение по умолчанию — 0 секунд.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-160">The default value is 0 seconds.</span></span> <span data-ttu-id="6e8b5-161">Если значение времени ожидания равно 0 секунд, то время ожидания запроса не будет ограничено.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-161">When the time out value is 0 seconds, the query does not time out.</span></span>

7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]

     <span data-ttu-id="6e8b5-162">Набор данных и его коллекция полей появляются в области данных отчета под узлом источника данных.</span><span class="sxs-lookup"><span data-stu-id="6e8b5-162">The dataset and its field collection appear in the Report Data pane under the data source node.</span></span>

## <a name="see-also"></a><span data-ttu-id="6e8b5-163">См. также:</span><span class="sxs-lookup"><span data-stu-id="6e8b5-163">See Also</span></span>
 <span data-ttu-id="6e8b5-164">[Внедренные и общие наборы данных отчетов &#40;построитель отчетов и службы ssrs&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) [коллекции полей набора строк &#40;построитель отчетов и SSRS&#41;](dataset-fields-collection-report-builder-and-ssrs.md) [конструкторы запросов &#40;](../query-designers-report-builder.md) построитель отчетов&#41;[Справка по диалоговым окнам, панелям и мастерам](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) [Добавление данных в отчет построитель отчетов &#40;и SSRS построитель отчетов подключения к](report-datasets-ssrs.md) [данным, источники данных и строки подключения в&#41;](../data-connections-data-sources-and-connection-strings-in-report-builder.md) [внедренных и общих наборах данных построитель отчетов &#40;и SSRS](embedded-and-shared-datasets-report-builder-and-ssrs.md) построитель отчетов</span><span class="sxs-lookup"><span data-stu-id="6e8b5-164">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) [Dataset Fields Collection &#40;Report Builder and SSRS&#41;](dataset-fields-collection-report-builder-and-ssrs.md) [Query Designers &#40;Report Builder&#41;](../query-designers-report-builder.md) [Report Builder Help for Dialog Boxes, Panes, and Wizards](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) [Add Data to a Report &#40;Report Builder and SSRS&#41;](report-datasets-ssrs.md) [Data Connections, Data Sources, and Connection Strings in Report Builder](../data-connections-data-sources-and-connection-strings-in-report-builder.md) [Embedded and Shared Datasets &#40;Report Builder and SSRS&#41;](embedded-and-shared-datasets-report-builder-and-ssrs.md)</span></span>


