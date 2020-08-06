---
title: Вкладка «Матрица классификации» (представление диаграммы точности интеллектуального анализа данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.accuracychart.confusionmatrix.f1
ms.assetid: 85d5a047-d656-41e0-8a31-400271c2a620
author: minewiskan
ms.author: owend
ms.openlocfilehash: d202d552b25095d0d0845ff64f9c0e289f7bba0e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656787"
---
# <a name="classification-matrix-tab-mining-accuracy-chart-view"></a><span data-ttu-id="a54c2-102">Вкладка «Матрица классификации» (представление диаграммы точности интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="a54c2-102">Classification Matrix Tab (Mining Accuracy Chart View)</span></span>
  <span data-ttu-id="a54c2-103">На вкладке **Матрица классификации** отображается матрица классификации для каждой модели, выбранной в сетке модели на вкладке **сопоставление столбцов** . Матрица классификации доступна, только если прогнозируемый столбец, выбранный на вкладке **сопоставление столбцов** , не является непрерывным.</span><span class="sxs-lookup"><span data-stu-id="a54c2-103">The **Classification Matrix** tab displays a classification matrix for each model selected in the models grid on the **Column Mapping** tab. The classification matrix is only available if the predictable column that is selected in the **Column Mapping** tab is not continuous.</span></span> <span data-ttu-id="a54c2-104">Подробное описание вкладки **Матрица классификации** см. в разделе [Testing and Validation &#40;Data Mining&#41;](data-mining/testing-and-validation-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="a54c2-104">For a more detailed description of the **Classification Matrix** tab, see [Testing and Validation &#40;Data Mining&#41;](data-mining/testing-and-validation-data-mining.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="a54c2-105">Варианты</span><span class="sxs-lookup"><span data-stu-id="a54c2-105">Options</span></span>  
 <span data-ttu-id="a54c2-106">**Копировать**</span><span class="sxs-lookup"><span data-stu-id="a54c2-106">**Copy**</span></span>  
 <span data-ttu-id="a54c2-107">Позволяет скопировать содержимое каждой матрицы классификации в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="a54c2-107">Copies the content of each classification matrix to the clipboard.</span></span>  
  
 <span data-ttu-id="a54c2-108">**Количество для \<model> включения\< predictable column>**</span><span class="sxs-lookup"><span data-stu-id="a54c2-108">**Counts for \<model> on \< predictable column>**</span></span>  
 <span data-ttu-id="a54c2-109">Отображает матрицу классификации для каждой модели интеллектуального анализа данных в структуре интеллектуального анализа.</span><span class="sxs-lookup"><span data-stu-id="a54c2-109">Displays a classification matrix for each mining model in the mining structure.</span></span> <span data-ttu-id="a54c2-110">Матрица содержит следующие столбцы:</span><span class="sxs-lookup"><span data-stu-id="a54c2-110">The matrix contains the following columns:</span></span>  
  
|<span data-ttu-id="a54c2-111">Значение</span><span class="sxs-lookup"><span data-stu-id="a54c2-111">Value</span></span>|<span data-ttu-id="a54c2-112">Описание</span><span class="sxs-lookup"><span data-stu-id="a54c2-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a54c2-113">**Прогноз**</span><span class="sxs-lookup"><span data-stu-id="a54c2-113">**Predicted**</span></span>|<span data-ttu-id="a54c2-114">Содержит строку для каждого состояния прогнозируемого столбца.</span><span class="sxs-lookup"><span data-stu-id="a54c2-114">Contains a row for each state of the predictable column.</span></span>|  
|<span data-ttu-id="a54c2-115">**\<states>действитель**</span><span class="sxs-lookup"><span data-stu-id="a54c2-115">**\<states> (actual)**</span></span>|<span data-ttu-id="a54c2-116">Столбец для каждого состояния прогнозируемого столбца.</span><span class="sxs-lookup"><span data-stu-id="a54c2-116">A column for each state in the predictable column.</span></span> <span data-ttu-id="a54c2-117">Если состояния строки и столбца совпадают, в ячейке отображается фактическое число вхождений данного состояния в базе данных.</span><span class="sxs-lookup"><span data-stu-id="a54c2-117">If the state of the row and the column correspond, the cell represents the actual number of times the state exists in the database.</span></span> <span data-ttu-id="a54c2-118">Если они не совпадают, в ячейке отображается ошибка прогноза.</span><span class="sxs-lookup"><span data-stu-id="a54c2-118">If they do not correspond, the cell represents the error of the prediction.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a54c2-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="a54c2-119">See Also</span></span>  
 <span data-ttu-id="a54c2-120">[Конструктор диаграмм точности интеллектуального анализа &#40;&#41;интеллектуального анализа данных](mining-accuracy-chart-designer-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="a54c2-120">[Mining Accuracy Chart Designer &#40;Data Mining&#41;](mining-accuracy-chart-designer-data-mining.md) </span></span>  
 <span data-ttu-id="a54c2-121">[Задачи тестирования и проверки и инструкции &#40;&#41;интеллектуального анализа данных](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="a54c2-121">[Testing and Validation Tasks and How-tos &#40;Data Mining&#41;](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span></span>  
 [<span data-ttu-id="a54c2-122">Тестирование и проверка (интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="a54c2-122">Testing and Validation &#40;Data Mining&#41;</span></span>](data-mining/testing-and-validation-data-mining.md)  
  
  
