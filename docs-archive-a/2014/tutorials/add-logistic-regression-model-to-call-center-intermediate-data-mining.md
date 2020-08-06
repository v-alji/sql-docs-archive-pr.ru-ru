---
title: Добавление модели логистической регрессии в структуру центра обработки вызовов (учебник по интеллектуальному анализу данных — средний уровень) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 97abb77a-346c-44fa-8959-688dee1af6a8
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 7d0100313d1ea5a1af5f729249bc2d743a730222
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735682"
---
# <a name="adding-a-logistic-regression-model-to-the-call-center-structure-intermediate-data-mining-tutorial"></a><span data-ttu-id="060c5-102">Добавление модели логистической регрессии к структуре Call Center (учебник по интеллектуальному анализу данных — средний уровень)</span><span class="sxs-lookup"><span data-stu-id="060c5-102">Adding a Logistic Regression Model to the Call Center Structure (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="060c5-103">Кроме анализа факторов, которые могут повлиять на работу центра обработки вызовов, была поставлена задача выработать конкретные рекомендации для персонала по повышению качества обслуживания.</span><span class="sxs-lookup"><span data-stu-id="060c5-103">In addition to analyzing the factors that might affect call center operations, you were also asked to provide some specific recommendations on how the staff can improve service quality.</span></span> <span data-ttu-id="060c5-104">Для этой задачи будет использоваться та же структура интеллектуального анализа данных, с помощью которой была построена исследовательская модель. Также будет добавлена модель интеллектуального анализа данных, которая будет использоваться для создания прогнозов.</span><span class="sxs-lookup"><span data-stu-id="060c5-104">In this task, you will use the same mining structure that you used to build the exploratory model and add a mining model that will be used for creating predictions.</span></span>  
  
 <span data-ttu-id="060c5-105">В службах [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] модель логистической регрессии основана на алгоритме нейронной сети и поэтому обладает той же гибкостью и мощью, что и модель нейронной сети.</span><span class="sxs-lookup"><span data-stu-id="060c5-105">In [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], a logistic regression model is based on the neural networks algorithm, and therefore provides the same flexibility and power as a neural network model.</span></span> <span data-ttu-id="060c5-106">Однако логистическая регрессия особенно удобна для прогнозирования двоичных результатов.</span><span class="sxs-lookup"><span data-stu-id="060c5-106">However, logistic regression is particularly well-suited for predicting binary outcomes.</span></span>  
  
 <span data-ttu-id="060c5-107">В этом сценарии можно использовать ту же структуру интеллектуального анализа данных, которая использовалась для модели нейронной сети.</span><span class="sxs-lookup"><span data-stu-id="060c5-107">For this scenario, you will use the same mining structure that you used for the neural network model.</span></span> <span data-ttu-id="060c5-108">Однако нужно настроить новую модель, чтобы получить ответы на нужные вопросы.</span><span class="sxs-lookup"><span data-stu-id="060c5-108">However, you will customize the new model to target your business questions.</span></span> <span data-ttu-id="060c5-109">Вас интересует повышение качества обслуживания и необходимое количество опытных операторов, и вы создадите модель для получения прогнозов по этим показателям.</span><span class="sxs-lookup"><span data-stu-id="060c5-109">You are interested in improving service quality and determining how many experienced operators you need, so you will set up your model to predict those values.</span></span>  
  
 <span data-ttu-id="060c5-110">Чтобы все модели, основанные на данных центра обработки вызовов, были как можно более одинаковыми, вы используете то же начальное значение, что и раньше.</span><span class="sxs-lookup"><span data-stu-id="060c5-110">To ensure that all the models based on the call center data are as similar as possible, you will use the same seed value as before.</span></span> <span data-ttu-id="060c5-111">Использование параметра начального значения гарантирует, что модель будет обрабатывать данные с той же начальной точки, и сводит к минимуму количество вариантов, создаваемых артефактами в данных.</span><span class="sxs-lookup"><span data-stu-id="060c5-111">Setting the seed parameter ensures that the model processes the data from the same starting point, and minimizes variations caused by artifacts in the data.</span></span>  
  
### <a name="to-add-a-new-mining-model-to-the-call-center-mining-structure"></a><span data-ttu-id="060c5-112">Добавление новой модели интеллектуального анализа данных к структуре интеллектуального анализа данных центра обработки вызовов</span><span class="sxs-lookup"><span data-stu-id="060c5-112">To add a new mining model to the call center mining structure</span></span>  
  
1.  <span data-ttu-id="060c5-113">В [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] Обозреватель решений щелкните правой кнопкой мыши структуру интеллектуального анализа данных, **вызовите Center Binned**и выберите **открыть конструктор**.</span><span class="sxs-lookup"><span data-stu-id="060c5-113">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in Solution Explorer, right-click the mining structure, **Call Center Binned**, and select **Open Designer**.</span></span>  
  
2.  <span data-ttu-id="060c5-114">В конструкторе интеллектуального анализа данных перейдите на вкладку **модели интеллектуального анализа** .</span><span class="sxs-lookup"><span data-stu-id="060c5-114">In Data Mining Designer, click the **Mining Models** tab.</span></span>  
  
3.  <span data-ttu-id="060c5-115">Щелкните **создать связанную модель интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="060c5-115">Click **Create a related mining model**.</span></span>  
  
4.  <span data-ttu-id="060c5-116">В диалоговом окне **Новая модель интеллектуального анализа данных** в поле **имя модели**введите `Call Center - LR` .</span><span class="sxs-lookup"><span data-stu-id="060c5-116">In the **New Mining Model** dialog box, for **Model name**, type `Call Center - LR`.</span></span>  <span data-ttu-id="060c5-117">В качестве **имени алгоритма**выберите **Microsoft логистическая регрессия**.</span><span class="sxs-lookup"><span data-stu-id="060c5-117">For **Algorithm name**, select **Microsoft Logistic Regression**.</span></span>  
  
5.  <span data-ttu-id="060c5-118">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="060c5-118">Click **OK**.</span></span>  
  
     <span data-ttu-id="060c5-119">Новая модель интеллектуального анализа данных отображается на вкладке **модели интеллектуального анализа данных** .</span><span class="sxs-lookup"><span data-stu-id="060c5-119">The new mining model is displayed in the **Mining Models** tab.</span></span>  
  
### <a name="to-customize-the-logistic-regression-model"></a><span data-ttu-id="060c5-120">Настройка модели логистической регрессии</span><span class="sxs-lookup"><span data-stu-id="060c5-120">To customize the logistic regression model</span></span>  
  
1.  <span data-ttu-id="060c5-121">В столбце для новой модели интеллектуального анализа данных `Call Center - LR` ОСТАВЬТЕ идентификатор фактов CallCenter в качестве ключа.</span><span class="sxs-lookup"><span data-stu-id="060c5-121">In the column for the new mining model, `Call Center - LR`, leave Fact CallCenter ID as the key.</span></span>  
  
2.  <span data-ttu-id="060c5-122">Измените значение ServiceGrade и два оператора уровня на **Predict**.</span><span class="sxs-lookup"><span data-stu-id="060c5-122">Change the value of ServiceGrade and Level Two Operators to **Predict**.</span></span>  
  
     <span data-ttu-id="060c5-123">Эти столбцы будут использоваться и в качестве входных данных, и для прогноза.</span><span class="sxs-lookup"><span data-stu-id="060c5-123">These columns will be used both as input and for prediction.</span></span> <span data-ttu-id="060c5-124">По сути, вы создаете две отдельные модели для одних и тех же данных: одну, которая прогнозирует число операторов и один прогнозирует уровень обслуживания.</span><span class="sxs-lookup"><span data-stu-id="060c5-124">In essence, you are creating two separate models on the same data: one that predicts the number of operators, and one that predicts the service grade.</span></span>  
  
3.  <span data-ttu-id="060c5-125">Измените все остальные столбцы на **входные**.</span><span class="sxs-lookup"><span data-stu-id="060c5-125">Change all other columns to **Input**.</span></span>  
  
### <a name="to-specify-the-seed-and-process-the-models"></a><span data-ttu-id="060c5-126">Указание начального значения и обработка моделей</span><span class="sxs-lookup"><span data-stu-id="060c5-126">To specify the seed and process the models</span></span>  
  
1.  <span data-ttu-id="060c5-127">На вкладке **модель интеллектуального анализа данных** щелкните правой кнопкой мыши столбец для модели с именем Call Center-LR и выберите пункт **задать параметры алгоритма**.</span><span class="sxs-lookup"><span data-stu-id="060c5-127">In the **Mining Model** tab, right-click the column for the model named Call Center - LR, and select **Set Algorithm Parameters**.</span></span>  
  
2.  <span data-ttu-id="060c5-128">В строке для параметра HOLDOUT_SEED щелкните пустую ячейку в поле **значение**и введите `1` .</span><span class="sxs-lookup"><span data-stu-id="060c5-128">In the row for the HOLDOUT_SEED parameter, click the empty cell under **Value**, and type `1`.</span></span> <span data-ttu-id="060c5-129">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="060c5-129">Click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="060c5-130">Значение, выбираемое в качестве начального, не играет роли, но необходимо использовать одно и то же начальное значение для всех связанных моделей.</span><span class="sxs-lookup"><span data-stu-id="060c5-130">The value that you choose as the seed does not matter, as long as you use the same seed for all related models.</span></span>  
  
3.  <span data-ttu-id="060c5-131">В меню **модели интеллектуального анализа данных** выберите пункт **обработать структуру интеллектуального анализа данных и все модели**.</span><span class="sxs-lookup"><span data-stu-id="060c5-131">In the **Mining Models** menu, select **Process Mining Structure and All Models**.</span></span> <span data-ttu-id="060c5-132">Нажмите кнопку **Да** , чтобы развернуть обновленный проект интеллектуального анализа данных на сервере.</span><span class="sxs-lookup"><span data-stu-id="060c5-132">Click **Yes** to deploy the updated data mining project to the server.</span></span>  
  
4.  <span data-ttu-id="060c5-133">В диалоговом окне **Обработка модели интеллектуального анализа данных** нажмите кнопку **выполнить**.</span><span class="sxs-lookup"><span data-stu-id="060c5-133">In the **Process Mining Model** dialog box, click **Run**.</span></span>  
  
5.  <span data-ttu-id="060c5-134">Нажмите кнопку **Закрыть** , чтобы закрыть диалоговое окно **Ход обработки** , а затем еще раз нажмите кнопку **Закрыть** в диалоговом окне **Обработка модели интеллектуального анализа данных** .</span><span class="sxs-lookup"><span data-stu-id="060c5-134">Click **Close** to close the **Process Progress** dialog box, and then click **Close** again in the **Process Mining Model** dialog box.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="060c5-135">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="060c5-135">Next Task in Lesson</span></span>  
 [<span data-ttu-id="060c5-136">Создание прогнозов для моделей центра обработки вызовов &#40;руководстве по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="060c5-136">Creating Predictions for the Call Center Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/create-predictions-call-center-models-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="060c5-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="060c5-137">See Also</span></span>  
 [<span data-ttu-id="060c5-138">Требования к обработке и связанные замечания (интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="060c5-138">Processing Requirements and Considerations &#40;Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md)  
  
  
