---
title: Выбор типа диаграммы точности и задание параметров диаграммы | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Mining Accuracy Chart [Analysis Services]
- mining models [Analysis Services], validating
- classification accuracy [data mining]
- accuracy testing [data mining]
ms.assetid: bd24dd4a-624f-478a-9c94-b1361e857680
author: minewiskan
ms.author: owend
ms.openlocfilehash: 33c2b5e8a1e228a86328ef6df1b636742d3614ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658566"
---
# <a name="choose-an-accuracy-chart-type-and-set-chart-options"></a><span data-ttu-id="dae06-102">Выбор типа диаграммы точности и задание параметров диаграммы</span><span class="sxs-lookup"><span data-stu-id="dae06-102">Choose an Accuracy Chart Type and Set Chart Options</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="dae06-103">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]предоставляет несколько методов для определения допустимости моделей интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="dae06-103">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] provides multiple methods for determining the validity of your mining models.</span></span> <span data-ttu-id="dae06-104">Тип диаграммы точности, которую можно создать для каждой модели или структуры, зависит от следующих факторов.</span><span class="sxs-lookup"><span data-stu-id="dae06-104">The type of accuracy chart that you can create for each model or structure depends on these factors:</span></span>  
  
-   <span data-ttu-id="dae06-105">Тип алгоритма, который использовался для создания модели.</span><span class="sxs-lookup"><span data-stu-id="dae06-105">The type of algorithm that was used to create the model</span></span>  
  
-   <span data-ttu-id="dae06-106">Тип данных прогнозируемого атрибута.</span><span class="sxs-lookup"><span data-stu-id="dae06-106">The data type of the predictable attribute</span></span>  
  
-   <span data-ttu-id="dae06-107">Количество прогнозируемых атрибутов для измерения.</span><span class="sxs-lookup"><span data-stu-id="dae06-107">The number of predictable attributes to measure</span></span>  
  
 <span data-ttu-id="dae06-108">В этом разделе содержатся общие сведения о различных диаграммах точности.</span><span class="sxs-lookup"><span data-stu-id="dae06-108">This topic provides an overview of the different accuracy charts.</span></span>  
  
 <span data-ttu-id="dae06-109">**Примечание.** Диаграммы и их определения не сохраняются.</span><span class="sxs-lookup"><span data-stu-id="dae06-109">**Note** Charts and their definitions are not saved.</span></span> <span data-ttu-id="dae06-110">Если закрыть окно с диаграммой, то диаграмму придется создать повторно.</span><span class="sxs-lookup"><span data-stu-id="dae06-110">If you close the window that contains a chart, you must create the chart again.</span></span>  
  
## <a name="accuracy-chart-types"></a><span data-ttu-id="dae06-111">Типы диаграмм точности</span><span class="sxs-lookup"><span data-stu-id="dae06-111">Accuracy Chart Types</span></span>  
 <span data-ttu-id="dae06-112">В зависимости от выбранного типа диаграммы может появиться возможность дополнительной настройки параметров, возможность просмотра диаграммы или возможность скопировать диаграмму в буфер обмена и работать с данными в Excel.</span><span class="sxs-lookup"><span data-stu-id="dae06-112">Depending on the chart type that you choose, you have the ability to further configure options, to browse the chart, or copy the chart to the Clipboard and work with the data in Excel.</span></span>  
  
#### <a name="lift-chart"></a><span data-ttu-id="dae06-113">Диаграмма точности прогнозов</span><span class="sxs-lookup"><span data-stu-id="dae06-113">Lift chart</span></span>  
 <span data-ttu-id="dae06-114">Чтобы просмотреть результаты, после настройки параметров для модели и для проверочных данных перейдите на вкладку **Диаграмма точности прогнозов** .</span><span class="sxs-lookup"><span data-stu-id="dae06-114">After you have configured the options for the models and the testing data, click the **Lift Chart** tab to view the results.</span></span> <span data-ttu-id="dae06-115">Также можно скопировать диаграмму в буфер обмена или осуществлять просмотр отдельных линий трендов или точек данных в условных обозначениях интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="dae06-115">You can also copy the chart to the Clipboard, or view details of individual trend lines or data points in the Mining Legend.</span></span>  
  
#### <a name="profit-chart"></a><span data-ttu-id="dae06-116">Диаграмма роста прибыли</span><span class="sxs-lookup"><span data-stu-id="dae06-116">Profit Chart</span></span>  
 <span data-ttu-id="dae06-117">После настройки параметров моделей и проверочных данных перейдите на вкладку **Диаграмма точности прогнозов** , выберите в списке **Тип диаграммы** пункт **Диаграмма роста прибыли** для установки параметров диаграммы роста прибыли и нажмите кнопку **ОК** для просмотра результатов.</span><span class="sxs-lookup"><span data-stu-id="dae06-117">After you have configured the options for the models and the testing data, click the **Lift Chart** tab, select **Profit Chart** from the **Chart Type** list to set profit chart options, and then click **OK** to view the results.</span></span>  
  
 <span data-ttu-id="dae06-118">Диалоговое окно **Настройки диаграммы роста прибыли** можно использовать неограниченное количество раз для проверки влияния различных параметров и повторного отображения диаграммы.</span><span class="sxs-lookup"><span data-stu-id="dae06-118">You can use the **Profit Chart Settings** dialog box as many times as you want to try different cost options and redisplay the chart.</span></span> <span data-ttu-id="dae06-119">В условных обозначениях интеллектуального анализа данных содержатся подробные сведения о предполагаемой прибыли для каждой модели.</span><span class="sxs-lookup"><span data-stu-id="dae06-119">The Mining Legend contains detailed information about the estimated profit for each model.</span></span> <span data-ttu-id="dae06-120">Кроме того, диаграмму и содержимое условных обозначений интеллектуального анализа данных можно скопировать в буфер обмена для последующей работы с ними в Excel.</span><span class="sxs-lookup"><span data-stu-id="dae06-120">You can also copy the chart and the contents of the Mining Legend to the Clipboard to work with it in Excel.</span></span>  
  
#### <a name="scatter-plot"></a><span data-ttu-id="dae06-121">Точечная диаграмма</span><span class="sxs-lookup"><span data-stu-id="dae06-121">Scatter Plot</span></span>  
 <span data-ttu-id="dae06-122">Если был выбран подходящий тип модели, то при переходе на вкладку **Диаграмма точности прогнозов** будет автоматически установлен тип **Точечная диаграмма** и отображена точечная диаграмма.</span><span class="sxs-lookup"><span data-stu-id="dae06-122">If you have selected the appropriate type of model, when you click the **Lift Chart** tab, the chart type is automatically set to **Scatter Plot** and a scatter plot is displayed.</span></span> <span data-ttu-id="dae06-123">Дальнейшая настройка невозможна.</span><span class="sxs-lookup"><span data-stu-id="dae06-123">No further configuration is possible.</span></span> <span data-ttu-id="dae06-124">Кроме того, диаграмму можно скопировать в буфер обмена и вставить ее как графическое изображение в Excel или другое приложение.</span><span class="sxs-lookup"><span data-stu-id="dae06-124">You can also copy the chart to the Clipboard and paste the chart as a graphic into Excel or another application.</span></span>  
  
#### <a name="classification-matrix"></a><span data-ttu-id="dae06-125">Матрица классификации</span><span class="sxs-lookup"><span data-stu-id="dae06-125">Classification Matrix</span></span>  
 <span data-ttu-id="dae06-126">При работе с матрицей классификации следует использовать вкладку **Выбор входа** для выбора моделей и проверочных данных, а затем перейти на вкладку **Матрица классификации** для просмотра результатов.</span><span class="sxs-lookup"><span data-stu-id="dae06-126">For a classification matrix, use the **Input Selection** tab to choose the models and the testing data, and then click the **Classification Matrix** tab to view the results.</span></span>  
  
 <span data-ttu-id="dae06-127">Содержимое матрицы классификации одинаково для всех типов моделей, его настройка не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="dae06-127">The contents of a classification matrix are the same for all model types, and cannot be configured.</span></span> <span data-ttu-id="dae06-128">Данные этой диаграммы можно скопировать в буфер обмена, а затем работать с ними в Excel.</span><span class="sxs-lookup"><span data-stu-id="dae06-128">You can copy the data in the chart to the Clipboard and then work with it in Excel.</span></span>  
  
#### <a name="cross-validation-report"></a><span data-ttu-id="dae06-129">Отчет перекрестной проверки</span><span class="sxs-lookup"><span data-stu-id="dae06-129">Cross-Validation Report</span></span>  
 <span data-ttu-id="dae06-130">При работе с отчетом перекрестной проверки, после выбора в обозревателе решений необходимой структуры или модели интеллектуального анализа данных перейдите на вкладку **Перекрестная проверка** , настройте все нужные параметры, а затем нажмите кнопку **Получить результаты** для создания отчета.</span><span class="sxs-lookup"><span data-stu-id="dae06-130">For a cross-validation report, after you have selected a mining structure or mining model in Solution Explorer, click the **Cross Validation** tab, configure all relevant options, and then click **Get Results** to generate the report.</span></span> <span data-ttu-id="dae06-131">Дальнейшая настройка невозможна.</span><span class="sxs-lookup"><span data-stu-id="dae06-131">No further configuration is possible.</span></span>  
  
 <span data-ttu-id="dae06-132">Отчет перекрестной проверки имеет одинаковый формат для всех типов моделей; настраивать его нельзя.</span><span class="sxs-lookup"><span data-stu-id="dae06-132">The format of the cross-validation report is the same for all model types, and cannot be configured.</span></span> <span data-ttu-id="dae06-133">Однако содержимое отчета отличается в зависимости от типа модели, анализ которой был произведен, и от типа данных прогнозируемого атрибута.</span><span class="sxs-lookup"><span data-stu-id="dae06-133">However, the content of the report differs depending on the type of model that you are analyzing, and the data type of the predictable attribute.</span></span> <span data-ttu-id="dae06-134">Результаты отчета можно скопировать в буфер обмена для последующей работы с ними в Excel.</span><span class="sxs-lookup"><span data-stu-id="dae06-134">You can also copy the results of the report to the Clipboard and work with the data in Excel.</span></span>  
  
  
