---
title: Вкладка «Диаграмма точности прогнозов» (представление диаграммы точности интеллектуального анализа данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.accuracychart.liftchart.f1
ms.assetid: f1674e2e-d38e-40c7-b8d1-5585ce9a0168
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7cdad01ff3549140bf4fed606b1e8f9eaed10dac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752475"
---
# <a name="lift-chart-tab-mining-accuracy-chart-view"></a><span data-ttu-id="698d7-102">Вкладка «Диаграмма точности прогнозов» (представление диаграммы точности интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="698d7-102">Lift Chart Tab (Mining Accuracy Chart View)</span></span>
  <span data-ttu-id="698d7-103">Панель **Диаграмма точности прогнозов** позволяет просмотреть диаграмму, в которой сравниваются все выбранные модели интеллектуального анализа данных, имеющиеся в выбранной структуре интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="698d7-103">Use the **Lift Chart** pane to view a chart that compares all the selected mining models in the selected mining structure.</span></span>  
  
 <span data-ttu-id="698d7-104">Если модель используется для прогнозирования дискретного атрибута, на этой панели можно отобразить либо диаграмму точности прогнозов, либо диаграмму роста прибыли.</span><span class="sxs-lookup"><span data-stu-id="698d7-104">If the model predicts a discrete attribute, the pane can display either a lift chart or a profit chart.</span></span> <span data-ttu-id="698d7-105">Сведения о диаграммах точности прогнозов см. в разделе [Диаграмма точности прогнозов (службы Analysis Services — интеллектуальный анализ данных)](data-mining/lift-chart-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="698d7-105">For information about lift charts, see [Lift Chart &#40;Analysis Services - Data Mining&#41;](data-mining/lift-chart-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="698d7-106">Чтобы создать диаграмму роста прибыли, необходимо предоставить дополнительные сведения о затратах на реализацию рекомендаций модели интеллектуального анализа данных, а также сведения об ожидаемой окупаемости.</span><span class="sxs-lookup"><span data-stu-id="698d7-106">To create a profit chart, you must provide additional information about the cost of implementing the recommendations of the mining model, as well as the expected return.</span></span> <span data-ttu-id="698d7-107">Дополнительные сведения см. в разделе [Диаграмма роста прибыли (службы Analysis Services — интеллектуальный анализ данных)](data-mining/profit-chart-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="698d7-107">For more information, see [Profit Chart &#40;Analysis Services - Data Mining&#41;](data-mining/profit-chart-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="698d7-108">Если модель используется для прогнозирования непрерывного атрибута, на этой панели будет отображена точечная диаграмма.</span><span class="sxs-lookup"><span data-stu-id="698d7-108">If the model predicts a continuous attribute, the pane will display a scatter plot graph.</span></span>  
  
 <span data-ttu-id="698d7-109">Общие сведения о методах измерения точности моделей интеллектуального анализа данных см. в разделе [Диаграмма точности прогнозов (службы Analysis Services — интеллектуальный анализ данных)](data-mining/lift-chart-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="698d7-109">For general information about methods of measuring the accuracy of a mining model, see [Lift Chart &#40;Analysis Services - Data Mining&#41;](data-mining/lift-chart-analysis-services-data-mining.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="698d7-110">Варианты</span><span class="sxs-lookup"><span data-stu-id="698d7-110">Options</span></span>  
 <span data-ttu-id="698d7-111">**Тип диаграммы**</span><span class="sxs-lookup"><span data-stu-id="698d7-111">**Chart Type**</span></span>  
 <span data-ttu-id="698d7-112">Устанавливает тип отображаемой в окне просмотра диаграммы.</span><span class="sxs-lookup"><span data-stu-id="698d7-112">Sets the type of chart to display in the viewer.</span></span> <span data-ttu-id="698d7-113">Можно выбрать либо **Диаграмма точности прогнозов** , либо **Диаграмма роста прибыли**.</span><span class="sxs-lookup"><span data-stu-id="698d7-113">You can select either **Lift Chart** or **Profit Chart**.</span></span>  
  
 <span data-ttu-id="698d7-114">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="698d7-114">**Settings**</span></span>  
 <span data-ttu-id="698d7-115">Открывает диалоговое окно **Настройки диаграммы роста прибыли** , которое можно использовать для настройки диаграммы роста прибыли.</span><span class="sxs-lookup"><span data-stu-id="698d7-115">Opens the **Profit Chart Settings** dialog box, which you can use to configure a profit chart.</span></span>  
  
 <span data-ttu-id="698d7-116">Диаграмма роста прибыли недоступна, если был выбран непрерывный прогнозируемый столбец во вкладке **Сопоставление столбцов** .</span><span class="sxs-lookup"><span data-stu-id="698d7-116">The profit chart is not available if a continuous predictable column was selected in the **Column Mapping** tab.</span></span>  
  
 <span data-ttu-id="698d7-117">**Копировать**</span><span class="sxs-lookup"><span data-stu-id="698d7-117">**Copy**</span></span>  
 <span data-ttu-id="698d7-118">Копирует диаграмму в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="698d7-118">Copies the chart to the Clipboard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="698d7-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="698d7-119">See Also</span></span>  
 <span data-ttu-id="698d7-120">[Конструктор диаграмм точности интеллектуального анализа &#40;&#41;интеллектуального анализа данных](mining-accuracy-chart-designer-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="698d7-120">[Mining Accuracy Chart Designer &#40;Data Mining&#41;](mining-accuracy-chart-designer-data-mining.md) </span></span>  
 <span data-ttu-id="698d7-121">[Задачи тестирования и проверки и инструкции &#40;&#41;интеллектуального анализа данных](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="698d7-121">[Testing and Validation Tasks and How-tos &#40;Data Mining&#41;](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span></span>  
 [<span data-ttu-id="698d7-122">Тестирование и проверка (интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="698d7-122">Testing and Validation &#40;Data Mining&#41;</span></span>](data-mining/testing-and-validation-data-mining.md)  
  
  
