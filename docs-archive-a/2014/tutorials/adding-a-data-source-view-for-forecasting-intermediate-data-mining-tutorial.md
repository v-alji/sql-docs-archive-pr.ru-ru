---
title: Добавление представления источников данных для прогнозирования (учебник по интеллектуальному анализу данных — средний уровень) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2665040a-1291-4064-ba01-f458637dda57
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 9424988efa6a9856f4ef0d558992fc90ac303861
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735673"
---
# <a name="adding-a-data-source-view-for-forecasting-intermediate-data-mining-tutorial"></a><span data-ttu-id="265a5-102">Добавление представления источников данных для прогнозирования (учебник по интеллектуальному анализу данных — средний уровень)</span><span class="sxs-lookup"><span data-stu-id="265a5-102">Adding a Data Source View for Forecasting (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="265a5-103">В этой задаче добавляется новое представление источника данных, которое будет использоваться в сценарии прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="265a5-103">In this task, you add a data source view that will be used for the forecasting scenario.</span></span> <span data-ttu-id="265a5-104">Модель прогнозирования требует, чтобы данные содержали столбец, который может быть использован для идентификации шагов временных рядов.</span><span class="sxs-lookup"><span data-stu-id="265a5-104">A forecasting model requires that the data contains a column that can be used to identify steps in a time series.</span></span> <span data-ttu-id="265a5-105">Если планируется анализировать несколько рядов данных, то все ряды должны заканчиваться на одном и том же шаге даты или времени.</span><span class="sxs-lookup"><span data-stu-id="265a5-105">If you plan to analyze multiple series of data, all series must end on the same date or time step.</span></span>  
  
### <a name="to-add-a-data-source-view"></a><span data-ttu-id="265a5-106">Добавление представления источников данных</span><span class="sxs-lookup"><span data-stu-id="265a5-106">To add a data source view</span></span>  
  
1.  <span data-ttu-id="265a5-107">В обозреватель решений щелкните правой кнопкой мыши элемент **представления источников данных**и выберите пункт **создать представление источника данных**.</span><span class="sxs-lookup"><span data-stu-id="265a5-107">In Solution Explorer, right-click **Data Source Views**, and then select **New Data Source View**.</span></span>  
  
2.  <span data-ttu-id="265a5-108">На странице **Мастер представления источника данных** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="265a5-108">On the **Welcome to the Data Source View Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="265a5-109">На странице **Выбор источника данных** в разделе **реляционные источники данных**выберите [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] источник данных.</span><span class="sxs-lookup"><span data-stu-id="265a5-109">On the **Select a Data Source** page, under **Relational data sources**, select the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] data source.</span></span> <span data-ttu-id="265a5-110">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="265a5-110">Click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="265a5-111">Если этот источник данных отсутствует, шаги по созданию источника данных можно найти в [учебнике по основам интеллектуального анализа данных](../../2014/tutorials/basic-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="265a5-111">If you do not have this data source, you can find the steps to create the data source in the [Basic Data Mining Tutorial](../../2014/tutorials/basic-data-mining-tutorial.md).</span></span>  
  
4.  <span data-ttu-id="265a5-112">На странице **Выбор таблиц и представлений** выберите таблицу vTimeSeries (dbo), а затем щелкните стрелку вправо, чтобы добавить ее в представление источника данных.</span><span class="sxs-lookup"><span data-stu-id="265a5-112">On the **Select Tables and Views** page, select the table, vTimeSeries (dbo), and then click the right arrow to add it to the data source view.</span></span>  
  
5.  <span data-ttu-id="265a5-113">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="265a5-113">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="265a5-114">На странице **Завершение работы мастера** по умолчанию представление источника данных имеет имя [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="265a5-114">On the **Completing the Wizard** page, by default the data source view is named [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)].</span></span> <span data-ttu-id="265a5-115">Измените имя на **SalesByRegion**и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="265a5-115">Change the name to **SalesByRegion**, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="265a5-116">Откроется конструктор представлений источников данных, и появится представление источника данных **SalesByRegion** .</span><span class="sxs-lookup"><span data-stu-id="265a5-116">Data Source View Designer opens and the **SalesByRegion** data source view appears.</span></span>  
  
## <a name="working-with-the-data-source-view"></a><span data-ttu-id="265a5-117">Работа с представлением источника данных</span><span class="sxs-lookup"><span data-stu-id="265a5-117">Working with the Data Source View</span></span>  
 <span data-ttu-id="265a5-118">После создания представления источников данных можно исследовать данные приведенными ниже способами.</span><span class="sxs-lookup"><span data-stu-id="265a5-118">After you have created the data source view, you can explore the data in the following ways:</span></span>  
  
-   <span data-ttu-id="265a5-119">Щелкните правой кнопкой мыши таблицу vTimeSeries в конструкторе и выберите **Просмотр данных** , чтобы открыть выбранную таблицу в сетке.</span><span class="sxs-lookup"><span data-stu-id="265a5-119">Right-click the table vTimeSeries in the designer, and select **Explore Data** to open the selected table in a grid.</span></span>  
  
-   <span data-ttu-id="265a5-120">Щелкните **Параметры выборки** , а затем используйте диалоговое окно **Параметры просмотра данных** , чтобы изменить метод выборки.</span><span class="sxs-lookup"><span data-stu-id="265a5-120">Click **Sampling options** and then use the **Data Exploration Options** dialog box to change the sampling method.</span></span> <span data-ttu-id="265a5-121">Нажмите кнопку **Обновить** , чтобы загрузить данные в таблицу с помощью параметров новый параметр.</span><span class="sxs-lookup"><span data-stu-id="265a5-121">Click **Refresh** to load data in the table using the new option settings.</span></span> <span data-ttu-id="265a5-122">Например, можно указать количество строк для вывода в выборке или выбрать n верхних строк.</span><span class="sxs-lookup"><span data-stu-id="265a5-122">For example, you could specify the number of rows to output in the sample, or choose the top n rows.</span></span>  
  
-   <span data-ttu-id="265a5-123">Щелкните правой кнопкой мыши таблицу vTimeSeries и выберите **Свойства** , чтобы назначить таблице новое имя.</span><span class="sxs-lookup"><span data-stu-id="265a5-123">Right-click the table vTimeSeries and select **Properties** to assign a new name to the table.</span></span> <span data-ttu-id="265a5-124">Также можно выбрать отдельные столбцы в представлении источников данных и изменить свойства столбца.</span><span class="sxs-lookup"><span data-stu-id="265a5-124">You can also select individual columns from the data source view, and the modify the column properties.</span></span>  
  
-   <span data-ttu-id="265a5-125">Щелкните любой участок области конструктора представления источников данных, создайте новый запрос и задайте имя для него, чтобы создать связи между таблицами, либо измените макет в области конструктора.</span><span class="sxs-lookup"><span data-stu-id="265a5-125">Click anywhere in the data source view design area to create a new query and assign a name to it, to create relationships between tables, or to change the layout of the design area.</span></span>  
  
-   <span data-ttu-id="265a5-126">Щелкните правой кнопкой мыши таблицу и выберите **Создать именованное вычисление** , чтобы создать производные столбцы, включая агрегаты.</span><span class="sxs-lookup"><span data-stu-id="265a5-126">Right-click a table and select **New Named Calculation** to create derived columns, including aggregations.</span></span> <span data-ttu-id="265a5-127">Можно также добавить в это представление новые таблицы и представления из источника данных.</span><span class="sxs-lookup"><span data-stu-id="265a5-127">You can also add new tables and views from the data source in this view.</span></span>  
  
 <span data-ttu-id="265a5-128">В следующей задаче рассмотрим некоторые временные ряды данных и определим, какой столбец лучше всего использовать в качестве идентификатора временных рядов.</span><span class="sxs-lookup"><span data-stu-id="265a5-128">In the next task, you will explore the time series data and determine the best column to use as the time series identifier.</span></span> <span data-ttu-id="265a5-129">Вы также узнаете, как обрабатывать промежутки данных во временных рядах.</span><span class="sxs-lookup"><span data-stu-id="265a5-129">You will also learn how to handle gaps in time series data.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="265a5-130">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="265a5-130">Next Task in Lesson</span></span>  
 [<span data-ttu-id="265a5-131">Основные сведения о требованиях к модели временных рядов &#40;руководстве по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="265a5-131">Understanding the Requirements for a Time Series Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/time-series-model-requirements-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="265a5-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="265a5-132">See Also</span></span>  
 [<span data-ttu-id="265a5-133">Алгоритм временных рядов (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="265a5-133">Microsoft Time Series Algorithm</span></span>](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md)  
  
  
