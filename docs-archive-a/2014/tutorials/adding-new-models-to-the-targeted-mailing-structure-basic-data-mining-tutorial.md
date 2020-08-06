---
title: Добавление новых моделей в структуру целевой рассылки (учебник по интеллектуальному анализу данных — базовый) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 512c6888-60f1-46e4-9639-bc448395b8d7
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: b83dfc6c9e218eecf3f2abe636b8c24d69d1b507
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735670"
---
# <a name="adding-new-models-to-the-targeted-mailing-structure-basic-data-mining-tutorial"></a><span data-ttu-id="9d89a-102">Добавление новых моделей в структуру целевой рассылки (учебник по интеллектуальному анализу данных — начальный уровень)</span><span class="sxs-lookup"><span data-stu-id="9d89a-102">Adding New Models to the Targeted Mailing Structure (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="9d89a-103">В этой задаче предстоит определить две дополнительные модели с помощью вкладки **модели интеллектуального анализа** данных конструктора интеллектуального анализа.</span><span class="sxs-lookup"><span data-stu-id="9d89a-103">In this task, you will define two additional models by using the **Mining Models** tab of Data Mining Designer.</span></span> <span data-ttu-id="9d89a-104">Для создания моделей будут использоваться упрощенный алгоритм Байеса и алгоритм кластеризации (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="9d89a-104">You will use the Microsoft Clustering and Microsoft Naive Bayes algorithms to create the models.</span></span> <span data-ttu-id="9d89a-105">Эти два алгоритма выбраны благодаря их способности прогнозировать дискретную величину (на примере приобретения велосипеда).</span><span class="sxs-lookup"><span data-stu-id="9d89a-105">These two algorithms are selected because of their ability to predict a discrete value (i.e., bike purchase).</span></span> <span data-ttu-id="9d89a-106">Дополнительные сведения об этих алгоритмах см. в разделе [алгоритм кластеризации (Майкрософт](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md) ) и [упрощенный алгоритм Байеса (Майкрософт](../../2014/analysis-services/data-mining/microsoft-naive-bayes-algorithm.md) ).</span><span class="sxs-lookup"><span data-stu-id="9d89a-106">For more information about these algorithms, see [Microsoft Clustering Algorithm](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md) and [Microsoft Naive Bayes Algorithm](../../2014/analysis-services/data-mining/microsoft-naive-bayes-algorithm.md)</span></span>  
  
### <a name="to-create-a-clustering-mining-model"></a><span data-ttu-id="9d89a-107">Создание модели кластеризации для интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="9d89a-107">To create a clustering mining model</span></span>  
  
1.  <span data-ttu-id="9d89a-108">Перейдите на вкладку **модели интеллектуального анализа** данных конструктора интеллектуального анализа в [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9d89a-108">Switch to the **Mining Models** tab in Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
     <span data-ttu-id="9d89a-109">Обратите внимание, что в конструкторе отображаются два столбца: один для структуры интеллектуального анализа данных, а другой для `TM_Decision_Tree` модели интеллектуального анализа данных, созданной на предыдущем занятии.</span><span class="sxs-lookup"><span data-stu-id="9d89a-109">Notice that the designer displays two columns, one for the mining structure and one for the `TM_Decision_Tree` mining model, which you created in the previous lesson.</span></span>  
  
2.  <span data-ttu-id="9d89a-110">Щелкните правой кнопкой мыши столбец **Структура** и выберите **создать модель интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="9d89a-110">Right-click the **Structure** column and select **New Mining Model**.</span></span>  
  
3.  <span data-ttu-id="9d89a-111">В диалоговом окне **Новая модель интеллектуального анализа данных** в поле **имя модели**введите `TM_Clustering` .</span><span class="sxs-lookup"><span data-stu-id="9d89a-111">In the **New Mining Model** dialog box, in **Model name**, type `TM_Clustering`.</span></span>  
  
4.  <span data-ttu-id="9d89a-112">В списке **имя алгоритма**выберите **кластеризация Майкрософт**.</span><span class="sxs-lookup"><span data-stu-id="9d89a-112">In **Algorithm name**, select **Microsoft Clustering**.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
 <span data-ttu-id="9d89a-113">Теперь новая модель отображается на вкладке **модели интеллектуального анализа** данных конструктора интеллектуального анализа.</span><span class="sxs-lookup"><span data-stu-id="9d89a-113">The new model now appears in the **Mining Models** tab of Data Mining Designer.</span></span> <span data-ttu-id="9d89a-114">Эта модель, построенная с помощью [!INCLUDE[msCoName](../includes/msconame-md.md)] алгоритма кластеризации, группирует клиентов со сходными характеристиками в кластеры и прогнозирует приобретение велосипедов для каждого кластера.</span><span class="sxs-lookup"><span data-stu-id="9d89a-114">This model, built with the [!INCLUDE[msCoName](../includes/msconame-md.md)] Clustering algorithm, groups customers with similar characteristics into clusters and predicts bike buying for each cluster.</span></span> <span data-ttu-id="9d89a-115">Хотя можно изменить использование столбцов и свойств для новой модели, `TM_Clustering` для этого руководства не требуется вносить изменения в модель.</span><span class="sxs-lookup"><span data-stu-id="9d89a-115">Although you can modify the column usage and properties for the new model, no changes to the `TM_Clustering` model are necessary for this tutorial.</span></span>  
  
### <a name="to-create-a-naive-bayes-mining-model"></a><span data-ttu-id="9d89a-116">Создание модели интеллектуального анализа данных с упрощенным алгоритмом Байеса</span><span class="sxs-lookup"><span data-stu-id="9d89a-116">To create a Naive Bayes mining model</span></span>  
  
1.  <span data-ttu-id="9d89a-117">На вкладке **модели интеллектуального анализа** данных конструктора интеллектуального анализа, щелкните правой кнопкой мыши столбец **Структура** и выберите пункт **Новая модель интеллектуального анализа**данных.</span><span class="sxs-lookup"><span data-stu-id="9d89a-117">In the **Mining Models** tab of Data Mining Designer, right-clickthe **Structure** column, and select **New Mining Model**.</span></span>  
  
2.  <span data-ttu-id="9d89a-118">В диалоговом окне **Новая модель интеллектуального анализа данных** в поле **имя модели**введите `TM_NaiveBayes` .</span><span class="sxs-lookup"><span data-stu-id="9d89a-118">In the **New Mining Model** dialog box, under **Model name**, type `TM_NaiveBayes`.</span></span>  
  
3.  <span data-ttu-id="9d89a-119">В списке **имя алгоритма**выберите **упрощенный алгоритм Байеса (Майкрософт**) и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9d89a-119">In **Algorithm name**, select **Microsoft Naive Bayes**, then click **OK**.</span></span>  
  
     <span data-ttu-id="9d89a-120">Появится сообщение о том, что [!INCLUDE[msCoName](../includes/msconame-md.md)] упрощенный алгоритм Байеса не поддерживает столбцы **Age** и **годовой доход** , которые являются непрерывными.</span><span class="sxs-lookup"><span data-stu-id="9d89a-120">A message appears stating that the [!INCLUDE[msCoName](../includes/msconame-md.md)] Naive Bayes algorithm does not support the **Age** and **Yearly Income** columns, which are continuous.</span></span>  
  
4.  <span data-ttu-id="9d89a-121">Нажмите кнопку **Да** , чтобы подтвердить сообщение и продолжить.</span><span class="sxs-lookup"><span data-stu-id="9d89a-121">Click **Yes** to acknowledge the message and continue.</span></span>  
  
 <span data-ttu-id="9d89a-122">Новая модель отображается на вкладке **модели интеллектуального анализа** данных конструктора интеллектуального анализа.</span><span class="sxs-lookup"><span data-stu-id="9d89a-122">A new model appears in the **Mining Models** tab of Data Mining Designer.</span></span> <span data-ttu-id="9d89a-123">Хотя можно изменить использование столбцов и свойств для всех моделей на этой вкладке, `TM_NaiveBayes` для этого руководства не требуется вносить изменения в модель.</span><span class="sxs-lookup"><span data-stu-id="9d89a-123">Although you can modify the column usage and properties for all the models in this tab, no changes to the `TM_NaiveBayes` model are necessary for this tutorial.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="9d89a-124">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="9d89a-124">Next Task in Lesson</span></span>  
 [<span data-ttu-id="9d89a-125">Руководство по обработке моделей в структуре целевой рассылки &#40;базовом руководстве по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="9d89a-125">Processing Models in the Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/processing-models-in-the-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="9d89a-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="9d89a-126">See Also</span></span>  
 <span data-ttu-id="9d89a-127">[Добавление моделей интеллектуального анализа данных в структуру &#40;Analysis Services интеллектуального анализа&#41;](../../2014/analysis-services/data-mining/add-mining-models-to-a-structure-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="9d89a-127">[Add Mining Models to a Structure &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/add-mining-models-to-a-structure-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="9d89a-128">[Конструктор интеллектуального анализа данных](../../2014/analysis-services/data-mining/data-mining-designer.md) </span><span class="sxs-lookup"><span data-stu-id="9d89a-128">[Data Mining Designer](../../2014/analysis-services/data-mining/data-mining-designer.md) </span></span>  
 [<span data-ttu-id="9d89a-129">Перемещение объектов интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="9d89a-129">Moving Data Mining Objects</span></span>](../../2014/analysis-services/data-mining/moving-data-mining-objects.md)  
  
  
