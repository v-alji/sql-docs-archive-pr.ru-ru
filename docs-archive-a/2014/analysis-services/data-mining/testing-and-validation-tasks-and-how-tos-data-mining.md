---
title: Задачи тестирования и проверки и инструкции (интеллектуальный анализ данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Mining Accuracy Chart [Analysis Services]
- predictive modeling [Analysis Services]
- mining structures [Analysis Services], predictive modeling
- Mining Accuracy Chart [Analysis Services], how-to topics
- mining models [Analysis Services], predictive modeling
- predictive accuracy [data mining]
ms.assetid: 3a0b4dc9-5b64-4be1-aa5f-6ff26f43dbf8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 10844a7d39e49ab595eb25bb56ed3f4f5d415565
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667955"
---
# <a name="testing-and-validation-tasks-and-how-tos-data-mining"></a><span data-ttu-id="765c3-102">Задачи и решения по тестированию и проверке (интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="765c3-102">Testing and Validation Tasks and How-tos (Data Mining)</span></span>
  <span data-ttu-id="765c3-103">Вкладку **Диаграмма точности интеллектуального анализа** конструктора интеллектуального анализа данных в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] можно использовать для сравнения точности прогнозов моделей интеллектуального анализа данных в структуре интеллектуального анализа.</span><span class="sxs-lookup"><span data-stu-id="765c3-103">You can use the **Mining Accuracy Chart** tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] to compare the predictive accuracy of the mining models in your mining structure.</span></span>  
  
 <span data-ttu-id="765c3-104">Можно создавать диаграммы четырех типов:</span><span class="sxs-lookup"><span data-stu-id="765c3-104">You can create four kinds of charts:</span></span>  
  
-   <span data-ttu-id="765c3-105">Диаграмма точности прогнозов</span><span class="sxs-lookup"><span data-stu-id="765c3-105">Lift chart</span></span>  
  
-   <span data-ttu-id="765c3-106">диаграмма роста прибыли;</span><span class="sxs-lookup"><span data-stu-id="765c3-106">Profit chart</span></span>  
  
-   <span data-ttu-id="765c3-107">матрица классификации;</span><span class="sxs-lookup"><span data-stu-id="765c3-107">Classification matrix</span></span>  
  
-   <span data-ttu-id="765c3-108">отчет перекрестной проверки.</span><span class="sxs-lookup"><span data-stu-id="765c3-108">Cross-validation report</span></span>  
  
 <span data-ttu-id="765c3-109">Диаграммы первых трех типов используют вкладку **Выбор входа** для определения данных, которые используются для создания диаграммы.</span><span class="sxs-lookup"><span data-stu-id="765c3-109">The first three charts use the **Input Selection** tab to define the data that is used for generating the chart.</span></span>  
  
 <span data-ttu-id="765c3-110">Диаграмма перекрестной проверки создается с помощью дополнительных входных данных, доступных на вкладке **Перекрестная проверка** . Дополнительные сведения см. в разделе [Перекрестная проверка &#40;Analysis Services-&#41;интеллектуального анализа данных ](cross-validation-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="765c3-110">The Cross-validation chart is created by using additional inputs, available on the **Cross-Validation** tab. For more information, see [Cross-Validation &#40;Analysis Services - Data Mining&#41;](cross-validation-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="765c3-111">Дополнительные сведения об использовании диаграммы точности интеллектуального анализа см. в разделе [Тестирование и проверка (интеллектуальный анализ данных)](testing-and-validation-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="765c3-111">For more information about how to use the mining accuracy chart, see [Testing and Validation &#40;Data Mining&#41;](testing-and-validation-data-mining.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="765c3-112">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="765c3-112">In This Section</span></span>  
  
-   [<span data-ttu-id="765c3-113">Создать диаграмму точности прогнозов, диаграмму роста прибыли или матрицу классификации</span><span class="sxs-lookup"><span data-stu-id="765c3-113">Create a Lift Chart, Profit Chart, or Classification Matrix</span></span>](create-a-lift-chart-profit-chart-or-classification-matrix.md)  
  
-   [<span data-ttu-id="765c3-114">создать отчет перекрестной проверки</span><span class="sxs-lookup"><span data-stu-id="765c3-114">Create a Cross-Validation Report</span></span>](create-a-cross-validation-report.md)  
  
-   [<span data-ttu-id="765c3-115">Выбрать и сопоставить данные проверки модели</span><span class="sxs-lookup"><span data-stu-id="765c3-115">Choose and Map Model Testing Data</span></span>](choose-and-map-model-testing-data.md)  
  
-   [<span data-ttu-id="765c3-116">Применение фильтров к данным проверки модели</span><span class="sxs-lookup"><span data-stu-id="765c3-116">Apply Filters to Model Testing Data</span></span>](apply-filters-to-model-testing-data.md)  
  
-   [<span data-ttu-id="765c3-117">Выбор столбца, используемого для тестирования модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="765c3-117">Choose the Column to Use for Testing a Mining Model</span></span>](choose-the-column-to-use-for-testing-a-mining-model.md)  
  
-   [<span data-ttu-id="765c3-118">Использование данных вложенной таблицы в качестве входных для диаграммы точности</span><span class="sxs-lookup"><span data-stu-id="765c3-118">Using Nested Table Data as an Input for an Accuracy Chart</span></span>](using-nested-table-data-as-an-input-for-an-accuracy-chart.md)  
  
  
