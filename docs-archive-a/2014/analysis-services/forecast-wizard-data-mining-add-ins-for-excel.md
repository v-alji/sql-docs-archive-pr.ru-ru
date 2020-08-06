---
title: Мастер прогнозов (надстройки интеллектуального анализа данных для Excel) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- forecasting [data mining]
- time series [data mining]
ms.assetid: c5b33f75-42d4-4598-89e7-94815c142ce6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8c3fae97bf1c36154d8ae378840014f2fb997afd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656686"
---
# <a name="forecast-wizard-data-mining-add-ins-for-excel"></a><span data-ttu-id="694fb-102">Мастер прогнозов (надстройки интеллектуального анализа данных для Excel)</span><span class="sxs-lookup"><span data-stu-id="694fb-102">Forecast Wizard (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="694fb-103">![Мастер взаимосвязей на ленте «Интеллектуальный анализ данных»](media/dmc-forecast.gif "Мастер взаимосвязей на ленте «Интеллектуальный анализ данных»")</span><span class="sxs-lookup"><span data-stu-id="694fb-103">![Associate wizard in Data Mining ribbon](media/dmc-forecast.gif "Associate wizard in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="694fb-104">С помощью мастера прогнозов можно прогнозировать значения во временных рядах.</span><span class="sxs-lookup"><span data-stu-id="694fb-104">The Forecast wizard helps you predict values in a time series.</span></span> <span data-ttu-id="694fb-105">Мастер прогнозов использует [!INCLUDE[msCoName](../includes/msconame-md.md)] алгоритм временных рядов (), который является алгоритмом регрессии, предназначенным для прогнозирования непрерывных столбцов, таких как продажи продукта.</span><span class="sxs-lookup"><span data-stu-id="694fb-105">The Forecast wizard uses the [!INCLUDE[msCoName](../includes/msconame-md.md)] Time Series algorithm, which is a regression algorithm for use in predicting continuous columns, such as product sales.</span></span>  
  
 <span data-ttu-id="694fb-106">В каждой модели прогнозирования должен содержаться ряд вариантов, то есть столбец, различающий точки в последовательности.</span><span class="sxs-lookup"><span data-stu-id="694fb-106">Each forecasting model must contain a case series, which is the column that distinguishes between points in a sequence.</span></span> <span data-ttu-id="694fb-107">Например, если используются исторические данные для прогнозирования продаж на период нескольких месяцев, в качестве ряда вариантов будет использоваться столбец с сериями дат.</span><span class="sxs-lookup"><span data-stu-id="694fb-107">For example, if you are using historical data to forecast sales over a period of several months, you would use a column containing a series of dates as the case series.</span></span>  
  
 <span data-ttu-id="694fb-108">Можно создавать прогнозы из моделей прогнозирования, не добавляя новые входные данные.</span><span class="sxs-lookup"><span data-stu-id="694fb-108">You can create predictions from a forecasting model without providing new input data.</span></span>  
  
 <span data-ttu-id="694fb-109">Средство « [прогноз &#40;средств анализа таблиц для Excel&#41;](forecast-table-analysis-tools-for-excel.md) » на ленте « **анализ** » также позволяет создавать модели прогнозирования, но является менее настраиваемым и может использовать только данные в таблицах Excel.</span><span class="sxs-lookup"><span data-stu-id="694fb-109">The [Forecast &#40;Table Analysis Tools for Excel&#41;](forecast-table-analysis-tools-for-excel.md) tool, in the **Analyze** ribbon, also lets you create forecasting models, but it is less customizable and can only use data in Excel tables.</span></span>  
  
## <a name="using-the-forecast-wizard"></a><span data-ttu-id="694fb-110">Использование мастера прогнозов</span><span class="sxs-lookup"><span data-stu-id="694fb-110">Using the Forecast Wizard</span></span>  
  
1.  <span data-ttu-id="694fb-111">На ленте **интеллектуальный анализ данных** щелкните **Прогноз**.</span><span class="sxs-lookup"><span data-stu-id="694fb-111">In the **Data Mining** ribbon, click **Forecast**.</span></span>  
  
2.  <span data-ttu-id="694fb-112">В поле **Выбор источника данных**выберите таблицу Excel, диапазон или внешний источник данных, которые следует использовать в качестве входных.</span><span class="sxs-lookup"><span data-stu-id="694fb-112">In the **Select Source Data**, choose the Excel table, range, or external data source to use as inputs.</span></span>  
  
     <span data-ttu-id="694fb-113">Если используется внешний источник данных, можно определить пользовательское представление или запросы и сохранить их как источник данных [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="694fb-113">If you use an external data source, you can define custom view or queries and save it as an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] data source.</span></span>  
  
3.  <span data-ttu-id="694fb-114">На странице **Прогнозирование** в поле **Метка времени**выберите столбец, содержащий уникальное числовое значение (в том числе значения даты и времени), которое можно использовать в качестве ряда вариантов.</span><span class="sxs-lookup"><span data-stu-id="694fb-114">On the **Forecasting** page, for **Time stamp**, select a column that contains unique numeric value (this includes date and time values) that can be used as the case series.</span></span> <span data-ttu-id="694fb-115">Источник данных должен быть отсортирован по этому столбцу в порядке возрастания.</span><span class="sxs-lookup"><span data-stu-id="694fb-115">The data source must be sorted in ascending order by this column.</span></span>  
  
     <span data-ttu-id="694fb-116">Если в данных нет такого столбца, можно использовать параметр \<no time stamp> .</span><span class="sxs-lookup"><span data-stu-id="694fb-116">If your data does not have such a column, you can use the option \<no time stamp>.</span></span> <span data-ttu-id="694fb-117">Мастер добавит уникальный столбец сортировки для входных данных, поэтому необходимо убедиться, что данные отсортированы должным способом, прежде чем запускать мастер и выбирать этот параметр.</span><span class="sxs-lookup"><span data-stu-id="694fb-117">The wizard will add a unique order column for the input data; therefore, you must make sure that the data is sorted the way you want before running the wizard and choosing this option.</span></span>  
  
4.  <span data-ttu-id="694fb-118">При необходимости можно нажать кнопку **Параметры** и настроить поведение модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="694fb-118">Optionally, you can click **Parameters** and customize the behavior of the mining model.</span></span>  
  
     <span data-ttu-id="694fb-119">Модели прогнозирования поддерживают несколько различных алгоритмов:</span><span class="sxs-lookup"><span data-stu-id="694fb-119">Forecasting models support several different algorithms:</span></span>  
  
    -   <span data-ttu-id="694fb-120">ARIMA</span><span class="sxs-lookup"><span data-stu-id="694fb-120">ARIMA</span></span>  
  
    -   <span data-ttu-id="694fb-121">ARTXP (вид регрессионной модели)</span><span class="sxs-lookup"><span data-stu-id="694fb-121">ARTXP (a type of regression model)</span></span>  
  
    -   <span data-ttu-id="694fb-122">Объединенные ARTXP и ARIMA</span><span class="sxs-lookup"><span data-stu-id="694fb-122">ARTXP and ARIMA combined</span></span>  
  
     <span data-ttu-id="694fb-123">Сведения о различиях см. в [статье Технический справочник по алгоритму временных рядов (Майкрософт](data-mining/microsoft-time-series-algorithm-technical-reference.md)).</span><span class="sxs-lookup"><span data-stu-id="694fb-123">For information about the differences, see [Microsoft Time Series Algorithm Technical Reference](data-mining/microsoft-time-series-algorithm-technical-reference.md).</span></span>  
  
     <span data-ttu-id="694fb-124">Также можно добавить указания периодичности, указать параметры сглаживания и настроить параметры регрессии для модели.</span><span class="sxs-lookup"><span data-stu-id="694fb-124">You can also add periodicity hints, specify smoothing options, and customize regression options for the model.</span></span>  
  
5.  <span data-ttu-id="694fb-125">На странице **Готово** укажите описательное имя для набора данных и модели и задайте следующие параметры, определяющие способ работы с готовой моделью.</span><span class="sxs-lookup"><span data-stu-id="694fb-125">On the **Finish** page, provide a descriptive name for your data set and model, and set the following options that control how you work with the finished model:</span></span>  
  
    -   <span data-ttu-id="694fb-126">**Обзор модели**.</span><span class="sxs-lookup"><span data-stu-id="694fb-126">**Browse model**.</span></span> <span data-ttu-id="694fb-127">Если выбран этот параметр, то после того, как мастер закончит обработку модели, откроется окно **обзора** , в котором можно просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="694fb-127">When this option is selected, as soon as the wizard finishes processing the model, it opens a **Browse** window to help you explore the results.</span></span> <span data-ttu-id="694fb-128">Содержимое средства просмотра зависит от типа создаваемой модели.</span><span class="sxs-lookup"><span data-stu-id="694fb-128">The contents of the viewer depend on the type of model you built.</span></span> <span data-ttu-id="694fb-129">Дополнительные сведения см. [в разделе Просмотр модели прогнозирования](browsing-a-forecasting-model.md).</span><span class="sxs-lookup"><span data-stu-id="694fb-129">For more information, see [Browsing a Forecasting Model](browsing-a-forecasting-model.md).</span></span>  
  
    -   <span data-ttu-id="694fb-130">**Включить детализацию**.</span><span class="sxs-lookup"><span data-stu-id="694fb-130">**Enable drillthrough**.</span></span> <span data-ttu-id="694fb-131">Выберите этот параметр, чтобы просмотреть базовые данные из созданной модели.</span><span class="sxs-lookup"><span data-stu-id="694fb-131">Select this option to view the underlying data from the finished model.</span></span> <span data-ttu-id="694fb-132">Этот параметр доступен только для модели «дерево принятия решений».</span><span class="sxs-lookup"><span data-stu-id="694fb-132">This option is only available if you build a Decision Tree model.</span></span>  
  
    -   <span data-ttu-id="694fb-133">**Использовать временную модель**.</span><span class="sxs-lookup"><span data-stu-id="694fb-133">**Use temporary model**.</span></span> <span data-ttu-id="694fb-134">Если выбрать этот параметр, модель не будет сохранена на сервере.</span><span class="sxs-lookup"><span data-stu-id="694fb-134">If you select this option, the model will not be saved to the server.</span></span> <span data-ttu-id="694fb-135">Временные модели удаляются при закрытии Excel.</span><span class="sxs-lookup"><span data-stu-id="694fb-135">Temporary models are deleted when you close Excel.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="694fb-136">Требования</span><span class="sxs-lookup"><span data-stu-id="694fb-136">Requirements</span></span>  
 <span data-ttu-id="694fb-137">Данные должны также включать по меньшей мере один столбец, который можно использовать как временной ряд.</span><span class="sxs-lookup"><span data-stu-id="694fb-137">Your data should include at least one column that can be used as the time series.</span></span> <span data-ttu-id="694fb-138">Значения в этом столбце должны быть уникальными и непрерывными, т. е. не должно быть пробелов.</span><span class="sxs-lookup"><span data-stu-id="694fb-138">The values in this column should be unique and continuous - that is, there should be no gaps.</span></span> <span data-ttu-id="694fb-139">Прежде чем запускать мастер, отсортируйте данные по столбцу временного ряда в порядке возрастания.</span><span class="sxs-lookup"><span data-stu-id="694fb-139">Before running the wizard, sort the data by the time series column in ascending order.</span></span>  
  
 <span data-ttu-id="694fb-140">Если данные не имеют столбца времени или даты, можно назначить произвольный числовой ряд или разрешить мастеру создать его.</span><span class="sxs-lookup"><span data-stu-id="694fb-140">If your data does not include a time or date column, you can assign an arbitrary numeric series, or let the wizard create one.</span></span> <span data-ttu-id="694fb-141">Если вы разрешили мастеру создать столбец для сортировки, убедитесь, что остальные столбцы отсортированы в нужном порядке, прежде чем запускать мастер.</span><span class="sxs-lookup"><span data-stu-id="694fb-141">F you let the wizard create the series order column, make sure the other columns are sorted in the worder you want them before starting the wizard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="694fb-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="694fb-142">See Also</span></span>  
 <span data-ttu-id="694fb-143">[Создание модели интеллектуального анализа данных](creating-a-data-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="694fb-143">[Creating a Data Mining Model](creating-a-data-mining-model.md) </span></span>  
 <span data-ttu-id="694fb-144">[Прогнозирование &#40;средств анализа таблиц для Excel&#41;](forecast-table-analysis-tools-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="694fb-144">[Forecast &#40;Table Analysis Tools for Excel&#41;](forecast-table-analysis-tools-for-excel.md) </span></span>  
 [<span data-ttu-id="694fb-145">Просмотр модели прогнозов</span><span class="sxs-lookup"><span data-stu-id="694fb-145">Browsing a Forecasting Model</span></span>](browsing-a-forecasting-model.md)  
  
  
