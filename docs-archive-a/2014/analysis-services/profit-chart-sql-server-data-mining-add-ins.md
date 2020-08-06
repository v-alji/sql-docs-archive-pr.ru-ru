---
title: Диаграмма роста прибыли (SQL Server надстроек интеллектуального анализа данных) | Документация Майкрософт
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- accuracy chart
- profit chart
- mining models, charting
- mining models, testing
ms.assetid: 5c902543-4da9-4db3-99d5-4ce04c43d7ef
author: minewiskan
ms.author: owend
ms.openlocfilehash: 030e511047b816543c12c81bdab307e599bbc5d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664516"
---
# <a name="profit-chart-sql-server-data-mining-add-ins"></a><span data-ttu-id="72873-102">Диаграмма роста прибыли (надстройки интеллектуального анализа данных SQL Server)</span><span class="sxs-lookup"><span data-stu-id="72873-102">Profit Chart (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="72873-103">![Кнопка «Диаграмма роста прибыли» на ленте «Интеллектуальный анализ данных»](media/dmc-profitchart.gif "Кнопка «Диаграмма роста прибыли» на ленте «Интеллектуальный анализ данных»")</span><span class="sxs-lookup"><span data-stu-id="72873-103">![Profit Chart button in Data Mining ribbon](media/dmc-profitchart.gif "Profit Chart button in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="72873-104">На диаграмме роста прибыли отображается оцененное увеличение прибыли, связанное с использованием модели интеллектуального анализа данных для определения, с какими заказчиками должна связаться компания в соответствии со сценарием.</span><span class="sxs-lookup"><span data-stu-id="72873-104">A profit chart displays the estimated profit increase that is associated with using a mining model to determine which customers a company should contact in a business scenario.</span></span> <span data-ttu-id="72873-105">Ось Y на диаграмме представляет прибыль, в то время как ось X — процент совокупности, с которым связалась компания.</span><span class="sxs-lookup"><span data-stu-id="72873-105">The Y-axis of the chart represents the profit, while the X-axis represents the percentage of the population that the company contacted.</span></span> <span data-ttu-id="72873-106">На типичной диаграмме роста прибыли отображается увеличение прибыли до определенной точки, после которой прибыль уменьшается при связи с еще большей совокупностью.</span><span class="sxs-lookup"><span data-stu-id="72873-106">A typical profit chart shows an increase in profits up to a point, after which profits decrease as more of the population is contacted.</span></span>  
  
## <a name="configuring-the-profit-chart"></a><span data-ttu-id="72873-107">Настройка диаграммы роста прибыли</span><span class="sxs-lookup"><span data-stu-id="72873-107">Configuring the Profit Chart</span></span>  
 <span data-ttu-id="72873-108">Диаграмма точности оценивает только вероятность точности или неточности прогнозов, а диаграмма роста прибыли содержит в своем прогнозе реальные знания о последствиях предпринимаемых действий.</span><span class="sxs-lookup"><span data-stu-id="72873-108">Whereas the accuracy chart assesses only the probability that predictions are right or wrong, the profit chart incorporates real-world knowledge about the consequences of taking action on a prediction.</span></span> <span data-ttu-id="72873-109">Это достигается с помощью принятия в расчет следующих факторов, указываемых при работе с мастером.</span><span class="sxs-lookup"><span data-stu-id="72873-109">This is achieved by taking into account the following factors, which you specify when you run the wizard:</span></span>  
  
-   <span data-ttu-id="72873-110">**Повтор**</span><span class="sxs-lookup"><span data-stu-id="72873-110">**Population**</span></span>  
  
     <span data-ttu-id="72873-111">Количество вариантов в наборе данных, используемое для создания диаграммы точности прогнозов.</span><span class="sxs-lookup"><span data-stu-id="72873-111">The number of cases in the dataset that is being used to create the lift chart.</span></span> <span data-ttu-id="72873-112">Например, количество потенциальных покупателей.</span><span class="sxs-lookup"><span data-stu-id="72873-112">For example, the number of potential customers.</span></span>  
  
-   <span data-ttu-id="72873-113">**Фиксированные затраты**</span><span class="sxs-lookup"><span data-stu-id="72873-113">**Fixed Cost**</span></span>  
  
     <span data-ttu-id="72873-114">Фиксированные издержки, связанные с бизнес-задачами.</span><span class="sxs-lookup"><span data-stu-id="72873-114">The fixed cost that is associated with the business problem.</span></span> <span data-ttu-id="72873-115">При оценке решения целевой рассылки эти издержки не будут зависеть от таких переменных, как количество телефонных звонков или количество рекламных писем.</span><span class="sxs-lookup"><span data-stu-id="72873-115">If this were for a targeted mailing solution, the cost would not depend on variables such as the number of telephone calls made or the number of promotional mailings sent.</span></span>  
  
-   <span data-ttu-id="72873-116">**Индивидуальная стоимость**</span><span class="sxs-lookup"><span data-stu-id="72873-116">**Individual Cost**</span></span>  
  
     <span data-ttu-id="72873-117">Расходы, добавляющиеся к фиксированным издержкам, которые могут быть связаны с обращением к каждому заказчику.</span><span class="sxs-lookup"><span data-stu-id="72873-117">Costs that are in addition to the fixed cost, that can be associated with each customer contact.</span></span> <span data-ttu-id="72873-118">Например, рекламные письма или телефонные звонки.</span><span class="sxs-lookup"><span data-stu-id="72873-118">For example, promotional mailings or telephone calls.</span></span>  
  
-   <span data-ttu-id="72873-119">**Доход на единицу**</span><span class="sxs-lookup"><span data-stu-id="72873-119">**Revenue Per Individual**</span></span>  
  
     <span data-ttu-id="72873-120">Сумма прибыли, связанная с каждой успешной продажей.</span><span class="sxs-lookup"><span data-stu-id="72873-120">The amount of revenue that is associated with each successful sale.</span></span>  
  
## <a name="using-the-profit-chart-wizard"></a><span data-ttu-id="72873-121">Использование мастера диаграмм роста прибыли</span><span class="sxs-lookup"><span data-stu-id="72873-121">Using the Profit Chart Wizard</span></span>  
 <span data-ttu-id="72873-122">При создании диаграммы роста прибыли необходимо ссылаться на существующую модель интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="72873-122">To create a profit chart, you must reference an existing data mining model.</span></span> <span data-ttu-id="72873-123">Можно просмотреть модели, чтобы найти модель, которая соответствует данным, щелкнув **Управление моделями** или **Обзор** , чтобы просмотреть сведения об используемом алгоритме и столбцах в модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="72873-123">You can browse models to find a model that matches your data by clicking **Manage Models** or **Browse** to see details about the algorithm that was used and the columns in the mining model.</span></span>  
  
 <span data-ttu-id="72873-124">Дополнительные сведения см. в статьях [Просмотр моделей в Excel &#40;SQL Server надстройки интеллектуального анализа данных&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md) и [управление моделями &#40;SQL Server надстройки интеллектуального анализа данных&#41;](manage-models-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="72873-124">For more information, see [Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md) and [Manage Models &#40;SQL Server Data Mining Add-ins&#41;](manage-models-sql-server-data-mining-add-ins.md).</span></span>  
  
#### <a name="to-create-a-profit-chart"></a><span data-ttu-id="72873-125">Создание диаграммы роста прибыли</span><span class="sxs-lookup"><span data-stu-id="72873-125">To create a profit chart</span></span>  
  
1.  <span data-ttu-id="72873-126">Выберите существующую модель.</span><span class="sxs-lookup"><span data-stu-id="72873-126">Select an existing model.</span></span>  
  
2.  <span data-ttu-id="72873-127">Укажите столбец для выполнения прогноза и целевое значение, если необходимо.</span><span class="sxs-lookup"><span data-stu-id="72873-127">Specify the column that you want to predict, and a target value, if appropriate.</span></span>  
  
3.  <span data-ttu-id="72873-128">Выберите источник данных, данные из которого будут использоваться моделью для создания прогноза.</span><span class="sxs-lookup"><span data-stu-id="72873-128">Select the source data, which means the data you will pass through the model in order to create a prediction.</span></span> <span data-ttu-id="72873-129">Эти данные не должны совпадать с данными, которые использовались при создании модели.</span><span class="sxs-lookup"><span data-stu-id="72873-129">This should not be the same data that you used to create the model.</span></span>  
  
4.  <span data-ttu-id="72873-130">Сопоставьте столбцы с новыми (исходными) данными со столбцами, используемыми в модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="72873-130">Map the columns in the new (source) date to the columns used in the data mining model.</span></span> <span data-ttu-id="72873-131">Если имена столбцов аналогичны, мастер сопоставит их автоматически.</span><span class="sxs-lookup"><span data-stu-id="72873-131">If the column names are similar, the wizard will automatically map them.</span></span>  
  
5.  <span data-ttu-id="72873-132">Введите сведения о затратах, необходимые мастеру: фиксированные затраты, Индивидуальная стоимость, совокупность и ожидаемый доход.</span><span class="sxs-lookup"><span data-stu-id="72873-132">Enter the cost information required by the wizard: the fixed cost, individual cost, the population, and the revenue expected.</span></span>  
  
6.  <span data-ttu-id="72873-133">При необходимости можно ввести градиентный ряд затрат (нажмите кнопку обзора **(...)** ).</span><span class="sxs-lookup"><span data-stu-id="72873-133">Optionally, you can enter a graduated series of costs (click the browse **(...)** button).</span></span> <span data-ttu-id="72873-134">Например, отправку можно удешевить, увеличив количество отправляемых элементов, так что можно ввести различную стоимость в зависимости от количества элементов, а мастер автоматически установит затраты для каждого типового размера.</span><span class="sxs-lookup"><span data-stu-id="72873-134">For example, a mailing might become cheaper as you increase the number of items that are sent, so you can enter a different cost depending on the number of items, and the wizard will automatically adjust the costs for each sample size.</span></span>  
  
7.  <span data-ttu-id="72873-135">Мастер создает диаграмму, которая включает анализ затрат для модели.</span><span class="sxs-lookup"><span data-stu-id="72873-135">The wizard creates a chart that includes the cost-benefit analysis for the model.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="72873-136">Требования</span><span class="sxs-lookup"><span data-stu-id="72873-136">Requirements</span></span>  
 <span data-ttu-id="72873-137">Если прогнозируется дискретное числовое значение, необходимо выбрать для прогноза точное целевое значение.</span><span class="sxs-lookup"><span data-stu-id="72873-137">If you are predicting a discrete numeric value, you must select the exact target value to predict.</span></span>  
  
## <a name="understanding-the-profit-chart"></a><span data-ttu-id="72873-138">Основные сведения о диаграмме роста прибыли</span><span class="sxs-lookup"><span data-stu-id="72873-138">Understanding the Profit Chart</span></span>  
 <span data-ttu-id="72873-139">Диаграмма роста прибыли содержит серую вертикальную линию, которую можно перемещать, щелкая в разных местах диаграммы.</span><span class="sxs-lookup"><span data-stu-id="72873-139">The profit chart contains a gray vertical line, which you can move by clicking a location in the chart.</span></span> <span data-ttu-id="72873-140">**Условные обозначения интеллектуального анализа данных** отображают оценку, заполнение и вероятность прогноза, связанные с расположением серой линии на диаграмме.</span><span class="sxs-lookup"><span data-stu-id="72873-140">The **Mining Legend** displays a score, the population correct, and the predict probability that are associated with the location of the gray line on the chart.</span></span> <span data-ttu-id="72873-141">Если при применении этой серой линии выбрать точку максимальной прибыли, то можно использовать значение вероятности прогнозирования, чтобы определить порог вероятности для связи с заказчиком.</span><span class="sxs-lookup"><span data-stu-id="72873-141">If you select the maximum point of profits in the chart by using the gray line, you can use the predict probability value to determine a probability threshold for contacting a customer.</span></span>  
  
 <span data-ttu-id="72873-142">Например, пик кривой прибыли лежит на 55 % совокупности, а соответствующая вероятность прогнозирования равна 20 %, это указывает на то, что для достижения максимальной прибыли необходимо связаться только с заказчиками, чья вероятность ответа равна 20 % или выше.</span><span class="sxs-lookup"><span data-stu-id="72873-142">For example, if the peak of the profit curve is at 55 percent of the population and the associated predict probability is 20 percent, this indicates that to achieve maximum profits you should only contact those customers whose response is predicted with a 20 percent or greater probability.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72873-143">См. также:</span><span class="sxs-lookup"><span data-stu-id="72873-143">See Also</span></span>  
 [<span data-ttu-id="72873-144">Проверка моделей и использование моделей для прогнозирования &#40;надстройки интеллектуального анализа данных для Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="72873-144">Validating Models and Using Models for Prediction &#40;Data Mining Add-ins for Excel&#41;</span></span>](validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel.md)  
  
  
