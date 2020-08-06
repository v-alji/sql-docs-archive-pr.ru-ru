---
title: Выберите столбец, который будет использоваться для тестирования модели интеллектуального анализа данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- columns [data mining], predictable mining columns
- Mining Accuracy Chart [Analysis Services], columns
- predictable mining columns [Analysis Services]
ms.assetid: c6a8f23a-da21-4f31-9521-99460d624649
author: minewiskan
ms.author: owend
ms.openlocfilehash: 326a7084600695d95d3a132f633041e9abad045b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665677"
---
# <a name="choose-the-column-to-use-for-testing-a-mining-model"></a><span data-ttu-id="ff64d-102">Выбор столбца, используемого для тестирования модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="ff64d-102">Choose the Column to Use for Testing a Mining Model</span></span>
  <span data-ttu-id="ff64d-103">Прежде чем измерять точность модели интеллектуального анализа данных, необходимо решить, какие результаты вы хотите оценить.</span><span class="sxs-lookup"><span data-stu-id="ff64d-103">Before you can measure the accuracy of a mining model, you must decide which outcome it is that you want to assess.</span></span> <span data-ttu-id="ff64d-104">Для большинства моделей интеллектуального анализа данных необходимо выбрать хотя бы один столбец, который будет использоваться в качестве прогнозируемого атрибута при создании модели.</span><span class="sxs-lookup"><span data-stu-id="ff64d-104">Most data mining models require that you choose at least one column to use as the predictable attribute when you create the model.</span></span> <span data-ttu-id="ff64d-105">Поэтому при проверке точности модели обычно необходимо выбрать для проверки этот атрибут.</span><span class="sxs-lookup"><span data-stu-id="ff64d-105">Therefore, when you test the accuracy of the model, you generally must select that attribute to test.</span></span>  
  
 <span data-ttu-id="ff64d-106">В следующем списке указаны некоторые дополнительные соображения, связанные с выбором прогнозируемого атрибута для использования при проверке.</span><span class="sxs-lookup"><span data-stu-id="ff64d-106">The following list describes some additional considerations for choosing the predictable attribute to use in testing:</span></span>  
  
-   <span data-ttu-id="ff64d-107">Некоторые типы моделей интеллектуального анализа данных могут прогнозировать несколько атрибутов, таких как нейронные сети, которые могут исследовать связи между множеством атрибутов.</span><span class="sxs-lookup"><span data-stu-id="ff64d-107">Some types of data mining models can predict multiple attributes-such as neural networks, which can explore the relationships between many attributes.</span></span>  
  
-   <span data-ttu-id="ff64d-108">Другие типы моделей интеллектуального анализа данных, такие как модели кластеризации, не обязательно имеют прогнозируемый атрибут.</span><span class="sxs-lookup"><span data-stu-id="ff64d-108">Other types of mining models-such as clustering models-do not necessarily have a predictable attribute.</span></span> <span data-ttu-id="ff64d-109">Модели кластеризации невозможно проверить, если они не имеют прогнозируемого атрибута.</span><span class="sxs-lookup"><span data-stu-id="ff64d-109">Clustering models cannot be tested unless they have a predictable attribute.</span></span>  
  
-   <span data-ttu-id="ff64d-110">Чтобы создать точечную диаграмму или измерить точность модели логистической регрессии, необходимо выбрать в качестве результата непрерывный прогнозируемый атрибут.</span><span class="sxs-lookup"><span data-stu-id="ff64d-110">To create a scatter plot or measure the accuracy of a regression model requires that you choose a continuous predictable attribute as the outcome.</span></span> <span data-ttu-id="ff64d-111">В этом случае невозможно указать целевое значение.</span><span class="sxs-lookup"><span data-stu-id="ff64d-111">In that case, you cannot specify a target value.</span></span> <span data-ttu-id="ff64d-112">Если создается не точечная диаграмма, базовый столбец структуры интеллектуального анализа данных должен также иметь тип содержимого **Дискретный** или **Дискретизированный**.</span><span class="sxs-lookup"><span data-stu-id="ff64d-112">If you are creating anything other than a scatter plot, the underlying mining structure column must also have a content type of **Discrete** or **Discretized**.</span></span>  
  
-   <span data-ttu-id="ff64d-113">Если выбрать в качестве результата дискретный атрибут, можно также указать целевое значение для прогнозируемого столбца или оставить поле **Прогнозируемое значение** пустым.</span><span class="sxs-lookup"><span data-stu-id="ff64d-113">If you choose a discrete attribute as the predictable outcome, you can also specify a target value, or you can leave the **Predict Value** field blank.</span></span> <span data-ttu-id="ff64d-114">Если включить **значение прогноза**, диаграмма будет измерять только эффективность модели при прогнозировании целевого значения.</span><span class="sxs-lookup"><span data-stu-id="ff64d-114">If you include a **Predict Value**, the chart will measure only the model's effectiveness at predicting the target value.</span></span> <span data-ttu-id="ff64d-115">Если не указать целевой результат, измеряется точность модели в прогнозировании всех результатов.</span><span class="sxs-lookup"><span data-stu-id="ff64d-115">If you do not specify a target outcome, the model is measured for its accuracy in predicting all outcomes.</span></span>  
  
-   <span data-ttu-id="ff64d-116">Если нужно включить несколько моделей и сравнить их на одной диаграмме точности, все модели должны использовать один и тот же прогнозируемый столбец.</span><span class="sxs-lookup"><span data-stu-id="ff64d-116">If you want to include multiple models and compare them in a single accuracy chart, all models must use the same predictable column.</span></span>  
  
-   <span data-ttu-id="ff64d-117">Если создается отчет перекрестной проверки, службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] автоматически проанализируют все модели с одним и тем же прогнозируемым атрибутом.</span><span class="sxs-lookup"><span data-stu-id="ff64d-117">When you create a cross-validation report, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will automatically analyze all models that have the same predictable attribute.</span></span>  
  
-   <span data-ttu-id="ff64d-118">Если флажок **Синхронизировать столбцы и значения прогноза**установлен, службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] автоматически выбирают прогнозируемые столбцы с одинаковыми именами и соответствующими типами данных.</span><span class="sxs-lookup"><span data-stu-id="ff64d-118">When the option, **Synchronize Prediction columns and Values**, is selected, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] automatically chooses predictable columns that have the same names and matching data types.</span></span> <span data-ttu-id="ff64d-119">Если столбцы не удовлетворяют этим критериям, можно снять этот флажок и выбрать прогнозируемый столбец вручную.</span><span class="sxs-lookup"><span data-stu-id="ff64d-119">If your columns do not meet these criteria, you can turn off this option and manually choose a predictable column.</span></span> <span data-ttu-id="ff64d-120">Это может потребоваться для проверки модели с внешним набором данных, столбцы которого отличаются от столбцов модели.</span><span class="sxs-lookup"><span data-stu-id="ff64d-120">You might need to do this if you are testing the model with an external data set that has different columns than the model.</span></span> <span data-ttu-id="ff64d-121">Однако, если выбрать столбец с неправильным типом данных, это приведет к ошибке или плохим результатам.</span><span class="sxs-lookup"><span data-stu-id="ff64d-121">However, if you choose a column with the wrong the type of data you will either get an error or bad results.</span></span>  
  
### <a name="specify-the-outcome-to-predict"></a><span data-ttu-id="ff64d-122">Укажите прогнозируемый столбец.</span><span class="sxs-lookup"><span data-stu-id="ff64d-122">Specify the outcome to predict</span></span>  
  
1.  <span data-ttu-id="ff64d-123">Дважды щелкните структуру интеллектуального анализа данных, чтобы открыть ее в конструкторе интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="ff64d-123">Double-click the mining structure to open it in Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="ff64d-124">Перейдите на вкладку **Диаграмма точности интеллектуального анализа данных** .</span><span class="sxs-lookup"><span data-stu-id="ff64d-124">Select the **Mining Accuracy Chart** tab.</span></span>  
  
3.  <span data-ttu-id="ff64d-125">Перейдите на вкладку **Выбор входа** .</span><span class="sxs-lookup"><span data-stu-id="ff64d-125">Select the **Input Selection** tab.</span></span>  
  
4.  <span data-ttu-id="ff64d-126">На вкладке **Выбор входа** , в списке **Имя прогнозируемого столбца**выберите прогнозируемый столбец для каждой модели, которую хотите включить в диаграмму.</span><span class="sxs-lookup"><span data-stu-id="ff64d-126">On the **Input Selection** tab, under **Predictable Column Name**, select a predictable column for each model that you include in the chart.</span></span>  
  
     <span data-ttu-id="ff64d-127">В окне **Имя прогнозируемого столбца** доступны только те столбцы модели интеллектуального анализа данных, которые имеют тип **Прогноз** или **Только прогноз**.</span><span class="sxs-lookup"><span data-stu-id="ff64d-127">The mining model columns that are available in the **Predictable Column Name** box are only those with the usage type set to **Predict** or **Predict Only**.</span></span>  
  
5.  <span data-ttu-id="ff64d-128">Чтобы определить точность модели, необходимо указать конкретное значение результата, выбрав его в списке **Значение прогнозирования** .</span><span class="sxs-lookup"><span data-stu-id="ff64d-128">If you want to determine the lift for a model, you must select a specific outcome value to measure, for by choosing from the **Predict Value** list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff64d-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="ff64d-129">See Also</span></span>  
 <span data-ttu-id="ff64d-130">[Выбор и сопоставьте данные тестирования модели](choose-and-map-model-testing-data.md) </span><span class="sxs-lookup"><span data-stu-id="ff64d-130">[Choose and Map Model Testing Data](choose-and-map-model-testing-data.md) </span></span>  
 [<span data-ttu-id="ff64d-131">Выбор типа диаграммы точности и задание параметров диаграммы</span><span class="sxs-lookup"><span data-stu-id="ff64d-131">Choose an Accuracy Chart Type and Set Chart Options</span></span>](choose-an-accuracy-chart-type-and-set-chart-options.md)  
  
  
