---
title: Укажите столбец для использования в качестве регрессии в модели | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d8e0cb8e-302a-4166-9ed0-e2d9e2919b0a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 86899d3793985b5e3c07618360d7b6a540935a54
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654598"
---
# <a name="specify-a-column-to-use-as-regressor-in-a-model"></a><span data-ttu-id="e0699-102">Указание столбца, который будет использоваться в модели в качестве регрессора</span><span class="sxs-lookup"><span data-stu-id="e0699-102">Specify a Column to Use as Regressor in a Model</span></span>
  <span data-ttu-id="e0699-103">Модель линейной регрессии представляет значение прогнозируемого атрибута как результат формулы, в которой входные данные комбинируются таким образом, чтобы они как можно ближе соответствовали предполагаемой линии регрессии.</span><span class="sxs-lookup"><span data-stu-id="e0699-103">A linear regression model represents the value of the predictable attribute as the result of a formula that combines the inputs in such a way that the data is fitted as a closely as possible to an estimated regression line.</span></span> <span data-ttu-id="e0699-104">Этот алгоритм принимает только числовые значения и автоматически обнаруживает входные данные, которые обеспечивают наиболее близкое соответствие.</span><span class="sxs-lookup"><span data-stu-id="e0699-104">The algorithm accepts only numeric values as inputs, and automatically detects the inputs that provide the best fit.</span></span>  
  
 <span data-ttu-id="e0699-105">Однако можно указать, что столбец включается в качестве регрессора добавлением в модель параметра FORCE_REGRESSOR и указанием использования регрессоров.</span><span class="sxs-lookup"><span data-stu-id="e0699-105">However, you can specify that a column be included as a regressor by adding the FORCE_REGRESSOR parameter to the model and specifying the regressors to use.</span></span> <span data-ttu-id="e0699-106">Это может понадобиться, когда атрибут имеет значение даже в том случае, если эффект слишком мал и не может быть обнаружен моделью либо когда необходимо обеспечить включение атрибута в формулу.</span><span class="sxs-lookup"><span data-stu-id="e0699-106">You might want to do this in cases where the attribute has meaning even if the effect is too small to be detected by the model, or when you want to ensure that the attribute is included in the formula.</span></span>  
  
 <span data-ttu-id="e0699-107">В следующей процедуре показано, как создать простую модель линейной регрессии с помощью образцов данных, использованных в [учебнике по нейронным сетям](../../tutorials/lesson-5-build-models-intermediate-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="e0699-107">The following procedure describes how to create a simple linear regression model, using the same sample data that is used for the [neural networks tutorial](../../tutorials/lesson-5-build-models-intermediate-data-mining-tutorial.md).</span></span> <span data-ttu-id="e0699-108">Модель не обязательно будет надежной, однако она демонстрирует, как использовать конструктор интеллектуального анализа данных для настройки модели линейной регрессии.</span><span class="sxs-lookup"><span data-stu-id="e0699-108">The model is not necessarily robust, but demonstrates how to use the Data Mining Designer to customize a linear regression model.</span></span>  
  
### <a name="how-to-create-a-simple-linear-regression-model"></a><span data-ttu-id="e0699-109">Как создать простую модель линейной регрессии</span><span class="sxs-lookup"><span data-stu-id="e0699-109">How to create a simple linear regression model</span></span>  
  
1.  <span data-ttu-id="e0699-110">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], в **обозревателе решений**разверните узел **Структуры интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="e0699-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in **Solution Explorer**, expand **Mining Structures**.</span></span>  
  
2.  <span data-ttu-id="e0699-111">Дважды щелкните Call Center.dmm, чтобы открыть его в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="e0699-111">Double-click Call Center.dmm to open it in the designer.</span></span>  
  
3.  <span data-ttu-id="e0699-112">В меню **Модель интеллектуального анализа данных** выберите пункт **Создать модель интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="e0699-112">From the **Mining Model** menu, select **New Mining Model**.</span></span>  
  
4.  <span data-ttu-id="e0699-113">В качестве алгоритма выберите **Алгоритм линейной регрессии (Майкрософт)**.</span><span class="sxs-lookup"><span data-stu-id="e0699-113">For the algorithm, select **Microsoft Linear Regression**.</span></span> <span data-ttu-id="e0699-114">В качестве имени введите **Call Center Regression**.</span><span class="sxs-lookup"><span data-stu-id="e0699-114">For the name, type **Call Center Regression**.</span></span>  
  
5.  <span data-ttu-id="e0699-115">На вкладке **Модели интеллектуального анализа данных** измените использование столбца следующим образом.</span><span class="sxs-lookup"><span data-stu-id="e0699-115">In the **Mining Models** tab, change the column usage as follows.</span></span> <span data-ttu-id="e0699-116">Все столбцы, отсутствующие в следующем списке, должны быть установлены в значение **Пропустить**.</span><span class="sxs-lookup"><span data-stu-id="e0699-116">All columns not in the following list should be set to **Ignore**, if they are not already.</span></span>  
  
     <span data-ttu-id="e0699-117">FactCallCenterID**Key**</span><span class="sxs-lookup"><span data-stu-id="e0699-117">FactCallCenterID**Key**</span></span>  
  
     <span data-ttu-id="e0699-118">ServiceGrade**PredictOnly**</span><span class="sxs-lookup"><span data-stu-id="e0699-118">ServiceGrade**PredictOnly**</span></span>  
  
     <span data-ttu-id="e0699-119">Total Operators**Input**</span><span class="sxs-lookup"><span data-stu-id="e0699-119">Total Operators**Input**</span></span>  
  
     <span data-ttu-id="e0699-120">AverageTimePerIssue**Input**</span><span class="sxs-lookup"><span data-stu-id="e0699-120">AverageTimePerIssue**Input**</span></span>  
  
6.  <span data-ttu-id="e0699-121">В меню **Модель интеллектуального анализа данных** выберите команду **Задать параметры модели**.</span><span class="sxs-lookup"><span data-stu-id="e0699-121">From the **Mining Model** menu, select **Set Model Parameters**.</span></span>  
  
7.  <span data-ttu-id="e0699-122">Для параметра FORCE_REGRESSOR в столбце **Значение** перечислите через запятую имена столбцов, заключенные в квадратные скобки, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e0699-122">For the parameter, FORCE_REGRESSOR, in the **Value** column, type the column names enclosed in brackets and separated by a comma, as follows:</span></span>  
  
    ```  
    [Average Time Per Issue],[Total Operators]  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="e0699-123">Алгоритм автоматически обнаруживает столбцы, являющиеся лучшими регрессорами.</span><span class="sxs-lookup"><span data-stu-id="e0699-123">The algorithm will automatically detect which columns are the best regressors.</span></span> <span data-ttu-id="e0699-124">Нужно только при необходимости принудительно использовать регрессоры, чтобы обеспечить включение столбца в конечную формулу.</span><span class="sxs-lookup"><span data-stu-id="e0699-124">You only need to force regressors when you want to ensure that a column is included in the final formula.</span></span>  
  
8.  <span data-ttu-id="e0699-125">В меню **Модель интеллектуального анализа данных** выберите пункт **Обработать модель**.</span><span class="sxs-lookup"><span data-stu-id="e0699-125">From the **Mining Model** menu, select **Process Model**.</span></span>  
  
     <span data-ttu-id="e0699-126">В средстве просмотра модель представляется единственным узлом, содержащим формулу регрессии.</span><span class="sxs-lookup"><span data-stu-id="e0699-126">In the viewer, the model is represented a single node containing the regression formula.</span></span> <span data-ttu-id="e0699-127">Можно просмотреть формулу в окне **Обозначения интеллектуального анализа данных**или получить коэффициенты для формулы с помощью запросов.</span><span class="sxs-lookup"><span data-stu-id="e0699-127">You can view the formula in the **Mining Legend**, or you can extract the coefficients for the formula by using queries.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0699-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="e0699-128">See Also</span></span>  
 <span data-ttu-id="e0699-129">[Алгоритм линейной регрессии (Майкрософт)](microsoft-linear-regression-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="e0699-129">[Microsoft Linear Regression Algorithm](microsoft-linear-regression-algorithm.md) </span></span>  
 <span data-ttu-id="e0699-130">[Запросы интеллектуального анализа данных](data-mining-queries.md) </span><span class="sxs-lookup"><span data-stu-id="e0699-130">[Data Mining Queries](data-mining-queries.md) </span></span>  
 <span data-ttu-id="e0699-131">[Технический справочник по алгоритму линейной регрессии (Майкрософт)](microsoft-linear-regression-algorithm-technical-reference.md) </span><span class="sxs-lookup"><span data-stu-id="e0699-131">[Microsoft Linear Regression Algorithm Technical Reference](microsoft-linear-regression-algorithm-technical-reference.md) </span></span>  
 [<span data-ttu-id="e0699-132">Содержимое моделей интеллектуального анализа данных для моделей линейной регрессии (службы Analysis Services — интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="e0699-132">Mining Model Content for Linear Regression Models &#40;Analysis Services - Data Mining&#41;</span></span>](mining-model-content-for-linear-regression-models-analysis-services-data-mining.md)  
  
  
