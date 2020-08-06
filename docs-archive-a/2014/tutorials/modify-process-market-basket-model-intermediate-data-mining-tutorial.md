---
title: Изменение и обработка модели потребительской корзины (учебник по интеллектуальному анализу данных — средний уровень) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b6019413-aebd-4ff7-831a-644572ad88b1
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 369de98e944c5ccf5d06ef61eaa16c06bb864e7b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654677"
---
# <a name="modifying-and-processing-the-market-basket-model-intermediate-data-mining-tutorial"></a><span data-ttu-id="7b5e9-102">Изменение и обработка модели потребительской корзины (учебник по интеллектуальному анализу данных — средний уровень)</span><span class="sxs-lookup"><span data-stu-id="7b5e9-102">Modifying and Processing the Market Basket Model (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="7b5e9-103">Прежде чем обрабатывать созданную модель интеллектуального анализа данных взаимосвязей, необходимо изменить значения по умолчанию двух параметров: *Поддержка* и *вероятность*.</span><span class="sxs-lookup"><span data-stu-id="7b5e9-103">Before you process the association mining model that you created, you must change the default values of two of the parameters: *Support* and *Probability*.</span></span>  
  
-   <span data-ttu-id="7b5e9-104">*Поддержка* определяет процент вариантов, в которых должно существовать правило, прежде чем оно считается допустимым.</span><span class="sxs-lookup"><span data-stu-id="7b5e9-104">*Support* defines the percentage of cases in which a rule must exist before it is considered valid.</span></span> <span data-ttu-id="7b5e9-105">Необходимо указать, что правило должно содержаться по крайней мере в 1 проценте случаев.</span><span class="sxs-lookup"><span data-stu-id="7b5e9-105">You will specify that a rule must be found in at least 1 percent of cases.</span></span>  
  
-   <span data-ttu-id="7b5e9-106">*Вероятность* определяет, насколько вероятно, что связь должна быть, прежде чем она будет считаться допустимой.</span><span class="sxs-lookup"><span data-stu-id="7b5e9-106">*Probability* defines how likely an association must be before it is considered valid.</span></span> <span data-ttu-id="7b5e9-107">Будут учитываться все взаимосвязи с вероятностью не менее 10 процентов.</span><span class="sxs-lookup"><span data-stu-id="7b5e9-107">You will consider any association with a probability of at least 10 percent.</span></span>  
  
 <span data-ttu-id="7b5e9-108">Дополнительные сведения о последствиях увеличения или уменьшения поддержки и вероятности см. в [статье Технический справочник по алгоритму взаимосвязей (Майкрософт](../../2014/analysis-services/data-mining/microsoft-association-algorithm-technical-reference.md)).</span><span class="sxs-lookup"><span data-stu-id="7b5e9-108">For more information about the effects of increasing or decreasing support and probability, see [Microsoft Association Algorithm Technical Reference](../../2014/analysis-services/data-mining/microsoft-association-algorithm-technical-reference.md).</span></span>  
  
 <span data-ttu-id="7b5e9-109">Определив структуру и параметры модели интеллектуального анализа данных **взаимосвязей** , вы обработаете модель.</span><span class="sxs-lookup"><span data-stu-id="7b5e9-109">After you have defined the structure and parameters for the **Association** mining model, you will process the model.</span></span>  
  
### <a name="to-adjust-the-parameters-of-the-association-model"></a><span data-ttu-id="7b5e9-110">Настройка параметров модели «Взаимосвязь»</span><span class="sxs-lookup"><span data-stu-id="7b5e9-110">To adjust the parameters of the Association model</span></span>  
  
1.  <span data-ttu-id="7b5e9-111">Откройте вкладку **модели интеллектуального анализа** данных конструктора интеллектуального анализа.</span><span class="sxs-lookup"><span data-stu-id="7b5e9-111">Open the **Mining Models** tab of Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="7b5e9-112">Щелкните правой кнопкой мыши столбец **Ассоциация** в сетке в конструкторе и выберите команду **задать параметры алгоритма, чтобы открыть диалоговое окно Параметры алгоритма** .</span><span class="sxs-lookup"><span data-stu-id="7b5e9-112">Right-click the **Association** column in the grid in the designer and select **Set Algorithm Parameters to open the Algorithm Parameters** dialog box.</span></span>  
  
3.  <span data-ttu-id="7b5e9-113">В столбце **значение** диалогового окна **Параметры алгоритма** задайте следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="7b5e9-113">In the **Value** column of the **Algorithm Parameters** dialog box, set the following parameters:</span></span>  
  
     <span data-ttu-id="7b5e9-114">MINIMUM_PROBABILITY = 0.1</span><span class="sxs-lookup"><span data-stu-id="7b5e9-114">MINIMUM_PROBABILITY = 0.1</span></span>  
  
     <span data-ttu-id="7b5e9-115">MINIMUM_SUPPORT = 0.01</span><span class="sxs-lookup"><span data-stu-id="7b5e9-115">MINIMUM_SUPPORT = 0.01</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
### <a name="to-process-the-mining-model"></a><span data-ttu-id="7b5e9-116">Обработка модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="7b5e9-116">To process the mining model</span></span>  
  
1.  <span data-ttu-id="7b5e9-117">В меню **модель интеллектуального анализа** данных служб [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] выберите пункт **обработать структуру интеллектуального анализа данных и все модели.**</span><span class="sxs-lookup"><span data-stu-id="7b5e9-117">On the **Mining Model** menu of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], select **Process Mining Structure and All Models.**</span></span>  
  
2.  <span data-ttu-id="7b5e9-118">В окне предупреждения с вопросом о том, нужно ли выполнить построение и развертывание проекта, нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="7b5e9-118">At the warning asking whether you want to build and deploy the project, click **Yes**.</span></span>  
  
     <span data-ttu-id="7b5e9-119">Откроется диалоговое окно **Обработка структуры интеллектуального анализа данных — Ассоциация** .</span><span class="sxs-lookup"><span data-stu-id="7b5e9-119">The **Process Mining Structure - Association** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="7b5e9-120">Нажмите кнопку **Запустить**.</span><span class="sxs-lookup"><span data-stu-id="7b5e9-120">Click **Run**.</span></span>  
  
     <span data-ttu-id="7b5e9-121">Будет открыто диалоговое окно **Ход обработки** , в котором отображаются сведения о ходе обработки модели.</span><span class="sxs-lookup"><span data-stu-id="7b5e9-121">The **Process Progress** dialog box opens to display information about model processing.</span></span> <span data-ttu-id="7b5e9-122">Обработка новой структуры и модели может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="7b5e9-122">Processing of the new structure and model might take some time.</span></span>  
  
4.  <span data-ttu-id="7b5e9-123">После успешного завершения обработки нажмите кнопку **Закрыть** , чтобы закрыть диалоговое окно **Ход обработки** .</span><span class="sxs-lookup"><span data-stu-id="7b5e9-123">After processing is complete, click **Close** to exit the **Process Progress** dialog box.</span></span>  
  
5.  <span data-ttu-id="7b5e9-124">Нажмите кнопку **Закрыть** еще раз, чтобы закрыть диалоговое окно **Обработка структуры интеллектуального анализа данных — Ассоциация** .</span><span class="sxs-lookup"><span data-stu-id="7b5e9-124">Click **Close** again to exit the **Process Mining Structure - Association** dialog box.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="7b5e9-125">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="7b5e9-125">Next Task in Lesson</span></span>  
 [<span data-ttu-id="7b5e9-126">Изучение моделей потребительской корзины &#40;руководстве по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="7b5e9-126">Exploring the Market Basket Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-market-basket-models-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="7b5e9-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="7b5e9-127">See Also</span></span>  
 [<span data-ttu-id="7b5e9-128">Требования к обработке и связанные замечания (интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="7b5e9-128">Processing Requirements and Considerations &#40;Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md)  
  
  
