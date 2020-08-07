---
title: Обработка моделей в структуре целевой рассылки (учебник по интеллектуальному анализу данных — базовый) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 9d8233bb-117e-4563-9302-8a5a8ad1fae2
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: b8fb7b9f601f351520c3f611cc3c520614ed8ccc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731245"
---
# <a name="processing-models-in-the-targeted-mailing-structure-basic-data-mining-tutorial"></a><span data-ttu-id="7033c-102">Обработка моделей в структуре интеллектуального анализа данных прямой почтовой рассылки (учебник по интеллектуальному анализу данных — начальный уровень)</span><span class="sxs-lookup"><span data-stu-id="7033c-102">Processing Models in the Targeted Mailing Structure (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="7033c-103">Прежде чем выполнить обзор моделей интеллектуального анализа данных или приступить к работе с ними, необходимо развернуть проект служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], а также обработать структуру и модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="7033c-103">Before you can browse or work with the mining models that you have created, you must deploy the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project and process the mining structure and mining models.</span></span>  
  
-   <span data-ttu-id="7033c-104">*Развертывание* отправляет проект на сервер и создает на сервере любые объекты в этом проекте.</span><span class="sxs-lookup"><span data-stu-id="7033c-104">*Deploying* sends the project to a server and creates any objects in that project on the server.</span></span>  
  
-   <span data-ttu-id="7033c-105">*Обработка* заполняет [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] объекты данными из реляционных источников данных.</span><span class="sxs-lookup"><span data-stu-id="7033c-105">*Processing* populates [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] objects with data from relational data sources.</span></span>  
  
 <span data-ttu-id="7033c-106">Модели можно использовать только после их развертывания и обработки.</span><span class="sxs-lookup"><span data-stu-id="7033c-106">Models cannot be used until they have been deployed and processed.</span></span> <span data-ttu-id="7033c-107">Кроме того, при внесении любых изменений в модель, например при добавлении новых данных, необходимо повторно развернуть и повторно обработать модели.</span><span class="sxs-lookup"><span data-stu-id="7033c-107">Also, when you make any changes to the model, such as adding new data, you must redeploy and reprocess the models.</span></span>  
  
## <a name="ensuring-consistency-with-holdoutseed"></a><span data-ttu-id="7033c-108">Обеспечение согласованности с помощью элемента HoldoutSeed</span><span class="sxs-lookup"><span data-stu-id="7033c-108">Ensuring Consistency with HoldoutSeed</span></span>  
 <span data-ttu-id="7033c-109">При развертывании проекта и обработке структуры и моделей отдельные строки в структуре данных назначаются либо в обучающий набор, либо на проверочный набор, основанный на числовом начальном значении.</span><span class="sxs-lookup"><span data-stu-id="7033c-109">When you deploy a project and process the structure and models, individual rows in your data structure are assigned to either the training set or testing set based on a numerical seed value.</span></span> <span data-ttu-id="7033c-110">По умолчанию числовое значение начального значения вычисляются на основе атрибутов структуры данных.</span><span class="sxs-lookup"><span data-stu-id="7033c-110">By default, the numerical seed value is computed based on attributes of the data structure.</span></span> <span data-ttu-id="7033c-111">Однако если вы изменяете некоторые аспекты модели, начальное значение изменится, что приведет к слегка разным результатам.</span><span class="sxs-lookup"><span data-stu-id="7033c-111">However, if you ever change some aspects of your model, the seed value would change, leading to subtly different results.</span></span> <span data-ttu-id="7033c-112">Поэтому, чтобы гарантировать, что результаты будут такими же, как описано здесь, мы будем произвольно назначать фиксированное *Контрольное значение* `12` .</span><span class="sxs-lookup"><span data-stu-id="7033c-112">Therefore, in order to ensure that your results are the same as described here, we will arbitrarily assign a fixed *holdout seed* of `12`.</span></span> <span data-ttu-id="7033c-113">Начальное контрольное значение используется для инициализации алгоритма выборки и обеспечивает секционирование данных примерно так же, как для всех структур интеллектуального анализа данных и их моделей.</span><span class="sxs-lookup"><span data-stu-id="7033c-113">The holdout seed is used to initialize the sampling algorithm, and ensures that the data is partitioned in roughly the same way for all mining structures and their models.</span></span>  
  
 <span data-ttu-id="7033c-114">Это значение не влияет на количество вариантов в обучающем наборе; Он просто гарантирует, что один и тот же метод секционирования будет использоваться при каждой сборке модели.</span><span class="sxs-lookup"><span data-stu-id="7033c-114">This value does not affect the number of cases in the training set; it simply ensures that the same partitioning method will be used each time you build the model.</span></span>  
  
 <span data-ttu-id="7033c-115">Дополнительные сведения о начальных контрольных значениях см. в разделе [обучающие и проверочные наборы данных](../../2014/analysis-services/data-mining/training-and-testing-data-sets.md).</span><span class="sxs-lookup"><span data-stu-id="7033c-115">For more information on holdout seed, see [Training and Testing Data Sets](../../2014/analysis-services/data-mining/training-and-testing-data-sets.md).</span></span>  
  
#### <a name="to-set-the-holdout-seed"></a><span data-ttu-id="7033c-116">Настройка начального контрольного значения</span><span class="sxs-lookup"><span data-stu-id="7033c-116">To set the Holdout Seed</span></span>  
  
1.  <span data-ttu-id="7033c-117">Перейдите на вкладку **Структура интеллектуального анализа** данных или вкладку **модели интеллектуального** анализа в конструкторе интеллектуального анализа в [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7033c-117">Click on the **Mining Structure** tab or the **Mining Models** tab in Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
     <span data-ttu-id="7033c-118">**Целевая рассылка MiningStructure** отображается на панели « **свойства** ».</span><span class="sxs-lookup"><span data-stu-id="7033c-118">**Targeted Mailing MiningStructure** displays in the **Properties** pane.</span></span>  
  
2.  <span data-ttu-id="7033c-119">Убедитесь, что панель **свойств** открыта, нажав клавишу **F4**.</span><span class="sxs-lookup"><span data-stu-id="7033c-119">Ensure that the **Properties** pane is open by pressing **F4**.</span></span>  
  
3.  <span data-ttu-id="7033c-120">Убедитесь, что для **CacheMode** задано значение **KeepTrainingCases**.</span><span class="sxs-lookup"><span data-stu-id="7033c-120">Ensure that **CacheMode** is set to **KeepTrainingCases**.</span></span>  
  
4.  <span data-ttu-id="7033c-121">Введите `12` для **HoldoutSeed**.</span><span class="sxs-lookup"><span data-stu-id="7033c-121">Enter `12` for **HoldoutSeed**.</span></span>  
  
## <a name="deploying-and-processing-the-models"></a><span data-ttu-id="7033c-122">Развертывание и обработка моделей</span><span class="sxs-lookup"><span data-stu-id="7033c-122">Deploying and Processing the Models</span></span>  
 <span data-ttu-id="7033c-123">В конструкторе интеллектуального анализа данных можно выбрать объекты для обработки в зависимости от области изменений, внесенных в модель или базовые данные.</span><span class="sxs-lookup"><span data-stu-id="7033c-123">In Data Mining Designer, you can decide which objects to process, depending on the scope of changes you've made to your model or the underlying data:</span></span>  
  
 <span data-ttu-id="7033c-124">Для этой задачи, поскольку данные и модели являются новыми, вы будете обрабатывать структуру и все модели одновременно.</span><span class="sxs-lookup"><span data-stu-id="7033c-124">For this task, because the data and the models are new, you will process the structure and all the models at the same time.</span></span>  
  
#### <a name="to-deploy-the-project-and-process-all-the-mining-models"></a><span data-ttu-id="7033c-125">Развертывание и обработка всех моделей интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="7033c-125">To deploy the project and process all the mining models</span></span>  
  
1.  <span data-ttu-id="7033c-126">В меню **модель интеллектуального анализа данных** выберите пункт **обработать структуру интеллектуального анализа данных и все модели**.</span><span class="sxs-lookup"><span data-stu-id="7033c-126">In the **Mining Model** menu, select **Process Mining Structure and All Models**.</span></span>  
  
     <span data-ttu-id="7033c-127">При внесении изменений в структуру будет выдано приглашение к повторному построению и развертыванию проекта перед обработкой моделей.</span><span class="sxs-lookup"><span data-stu-id="7033c-127">If you made changes to the structure, you will be prompted to build and deploy the project before processing the models.</span></span> <span data-ttu-id="7033c-128">Нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="7033c-128">Click **Yes**.</span></span>  
  
2.  <span data-ttu-id="7033c-129">В диалоговом окне **Обработка структуры интеллектуального анализа данных — Целевая отправка** нажмите кнопку **выполнить** .</span><span class="sxs-lookup"><span data-stu-id="7033c-129">Click **Run** in the **Processing Mining Structure - Targeted Mailing** dialog box.</span></span>  
  
     <span data-ttu-id="7033c-130">Откроется диалоговое окно **Ход обработки** , отображающее подробные сведения об обработке модели.</span><span class="sxs-lookup"><span data-stu-id="7033c-130">The **Process Progress** dialog box opens to display the details of model processing.</span></span> <span data-ttu-id="7033c-131">Обработка модели может занять некоторое время, которое зависит от мощности компьютера.</span><span class="sxs-lookup"><span data-stu-id="7033c-131">Model processing might take some time, depending on your computer.</span></span>  
  
3.  <span data-ttu-id="7033c-132">Нажмите кнопку **Закрыть** в диалоговом окне **Ход обработки** после завершения обработки моделей.</span><span class="sxs-lookup"><span data-stu-id="7033c-132">Click **Close** in the **Process Progress** dialog box after the models have completed processing.</span></span>  
  
4.  <span data-ttu-id="7033c-133">В диалоговом окне **Обработка \<structure> структуры интеллектуального анализа данных** нажмите кнопку **Закрыть** .</span><span class="sxs-lookup"><span data-stu-id="7033c-133">Click **Close** in the **Processing Mining Structure - \<structure>** dialog box.</span></span>  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="7033c-134">Предыдущая задача занятия</span><span class="sxs-lookup"><span data-stu-id="7033c-134">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="7033c-135">Добавление новых моделей в структуру целевой рассылки &#40;базовое руководство по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="7033c-135">Adding New Models to the Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/adding-new-models-to-the-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="7033c-136">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="7033c-136">Next Lesson</span></span>  
 [<span data-ttu-id="7033c-137">Занятие 4. изучение моделей целевой рассылки &#40;учебник по основам интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="7033c-137">Lesson 4: Exploring the Targeted Mailing Models &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-exploring-the-targeted-mailing-models-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="7033c-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="7033c-138">See Also</span></span>  
 [<span data-ttu-id="7033c-139">Требования к обработке и связанные замечания (интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="7033c-139">Processing Requirements and Considerations &#40;Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md)  
  
  
