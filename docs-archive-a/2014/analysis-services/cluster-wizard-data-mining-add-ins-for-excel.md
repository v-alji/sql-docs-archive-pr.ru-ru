---
title: Мастер кластеров (надстройки интеллектуального анализа данных для Excel) | Документация Майкрософт
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- clustering [data mining]
ms.assetid: 85b25625-a7ab-4960-9f9c-df22e8ecae37
author: minewiskan
ms.author: owend
ms.openlocfilehash: 90500ae627bcafd1ca5ce17114dac9df9939691d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657400"
---
# <a name="cluster-wizard-data-mining-add-ins-for-excel"></a><span data-ttu-id="57644-102">Мастер кластеризации (надстройки интеллектуального анализа данных для Excel)</span><span class="sxs-lookup"><span data-stu-id="57644-102">Cluster Wizard (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="57644-103">![Мастер кластеризации на ленте «Интеллектуальный анализ данных»](media/dmc-cluster.gif "Мастер кластеризации на ленте «Интеллектуальный анализ данных»")</span><span class="sxs-lookup"><span data-stu-id="57644-103">![Cluster wizard in Data Mining ribbon](media/dmc-cluster.gif "Cluster wizard in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="57644-104">Мастер кластеризации помогает построить модель, определяющую строки со сходными характеристиками и группирующую их для максимизации расстояния между группами.</span><span class="sxs-lookup"><span data-stu-id="57644-104">The Cluster wizard helps you build a model that detects rows that share similar characteristics and groups them to maximize the distance between groups.</span></span> <span data-ttu-id="57644-105">Этот мастер полезен для нахождения закономерностей во всех видах данных.</span><span class="sxs-lookup"><span data-stu-id="57644-105">This wizard is useful for finding patterns in all kinds of data.</span></span>  
  
 <span data-ttu-id="57644-106">Мастер кластеризации применяет алгоритм кластеризации Майкрософт и может быть в значительной степени настроен.</span><span class="sxs-lookup"><span data-stu-id="57644-106">The Cluster wizard uses the Microsoft Clustering algorithm and can be extensively customized.</span></span> <span data-ttu-id="57644-107">Он работает на существующих данных из таблицы Excel, из диапазона Excel или из запроса [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57644-107">It works on existing data from an Excel table, an Excel range, or an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] query.</span></span> <span data-ttu-id="57644-108">Аналогичные функциональные возможности обеспечиваются средством « [Поиск категорий](detect-categories-table-analysis-tools-for-excel.md) », представленным в средствах анализа таблиц для Excel.</span><span class="sxs-lookup"><span data-stu-id="57644-108">Similar functionality is provided by the [Detect Categories](detect-categories-table-analysis-tools-for-excel.md) tool, provided in the Table Analysis Tools for Excel.</span></span> <span data-ttu-id="57644-109">Однако средство «Определение категории» нельзя настроить, и оно может использовать данные только из таблиц Excel.</span><span class="sxs-lookup"><span data-stu-id="57644-109">However, the Detect Categories tool cannot be customized and must use data in Excel tables.</span></span>  
  
## <a name="using-the-cluster-wizard"></a><span data-ttu-id="57644-110">Использование мастера кластеризации</span><span class="sxs-lookup"><span data-stu-id="57644-110">Using the Cluster Wizard</span></span>  
  
1.  <span data-ttu-id="57644-111">На ленте Интеллектуальный анализ данных щелкните **кластер**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="57644-111">In the Data Mining ribbon, click **Cluster**, and then click **Next**.</span></span>  
  
2.  <span data-ttu-id="57644-112">На странице **Выбор источника данных** выберите таблицу или диапазон Excel.</span><span class="sxs-lookup"><span data-stu-id="57644-112">In the **Select Source Data** page, select an Excel table or range.</span></span> <span data-ttu-id="57644-113">Вместо этого можно указать внешний источник данных.</span><span class="sxs-lookup"><span data-stu-id="57644-113">Or specify and external data source.</span></span>  
  
     <span data-ttu-id="57644-114">Если используется внешний источник данных, можно создать пользовательские представления или вставить пользовательский текст запроса и сохранить набор данных как источник данных [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57644-114">If you use an external data source, you can create custom views or paste in custom query text, and save the data set as an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] data source.</span></span>  
  
3.  <span data-ttu-id="57644-115">На странице **кластеризация** можно настроить способ построения модели.</span><span class="sxs-lookup"><span data-stu-id="57644-115">On the **Clustering** page, you can customize the way the model is built.</span></span>  
  
    -   <span data-ttu-id="57644-116">Для **количества сегментов**можно указать мастеру создать фиксированное число категорий или позволить автоматически определить оптимальное количество группирований.</span><span class="sxs-lookup"><span data-stu-id="57644-116">For **Number of segments**, you can tell the wizard to create a fixed number of categories, or let it automatically detect the optimum number of groupings.</span></span>  
  
    -   <span data-ttu-id="57644-117">Проверьте список столбцов в списке **входные столбцы** и отмените выбор всех столбцов, которые не используются при создании шаблонов.</span><span class="sxs-lookup"><span data-stu-id="57644-117">Review the list of columns in the **Input columns** list, and deselect any columns that are not useful in creating patterns.</span></span> <span data-ttu-id="57644-118">В столбцы, которые следует исключить, входят идентификационные номера, имена клиентов и так далее.</span><span class="sxs-lookup"><span data-stu-id="57644-118">Columns you should exclude include ID numbers, customer names, and so on.</span></span>  
  
4.  <span data-ttu-id="57644-119">При необходимости нажмите кнопку **Параметры** , чтобы изменить параметры алгоритма и настроить поведение модели кластеризации.</span><span class="sxs-lookup"><span data-stu-id="57644-119">Optionally, click **Parameters** to change the algorithm parameters and customize the behavior of the clustering model.</span></span>  
  
5.  <span data-ttu-id="57644-120">На странице **разделение данных на обучающий и проверочный наборы** укажите объем данных для тестирования.</span><span class="sxs-lookup"><span data-stu-id="57644-120">In the **Split data into training and testing sets** page, specify how much data to hold out for testing.</span></span> <span data-ttu-id="57644-121">Остаток всегда используется для обучения модели.</span><span class="sxs-lookup"><span data-stu-id="57644-121">The remainder is always used for training the model.</span></span>  
  
     <span data-ttu-id="57644-122">Значение по умолчанию — 30 % для проверочных данных и 70 % для обучения.</span><span class="sxs-lookup"><span data-stu-id="57644-122">The default setting is 30% testing data and 70% training data.</span></span>  
  
6.  <span data-ttu-id="57644-123">На странице **Готово** укажите описательное имя для набора данных и модели и задайте следующие параметры, определяющие способ работы с готовой моделью.</span><span class="sxs-lookup"><span data-stu-id="57644-123">On the **Finish** page, provide a descriptive name for your data set and model, and set the following options that control how you work with the finished model:</span></span>  
  
    -   <span data-ttu-id="57644-124">**Обзор модели**.</span><span class="sxs-lookup"><span data-stu-id="57644-124">**Browse model**.</span></span> <span data-ttu-id="57644-125">Если выбран этот параметр, то после того, как мастер закончит обработку модели, откроется окно **обзора** , в котором можно просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="57644-125">When this option is selected, as soon as the wizard finishes processing the model, it opens a **Browse** window to help you explore the results.</span></span> <span data-ttu-id="57644-126">Содержимое средства просмотра зависит от типа создаваемой модели.</span><span class="sxs-lookup"><span data-stu-id="57644-126">The contents of the viewer depend on the type of model you built.</span></span> <span data-ttu-id="57644-127">Дополнительные сведения см. [в разделе Обзор модели кластеризации](browsing-a-clustering-model.md).</span><span class="sxs-lookup"><span data-stu-id="57644-127">For more information, see [Browsing a Clustering Model](browsing-a-clustering-model.md).</span></span>  
  
    -   <span data-ttu-id="57644-128">**Включить детализацию**.</span><span class="sxs-lookup"><span data-stu-id="57644-128">**Enable drillthrough**.</span></span> <span data-ttu-id="57644-129">Выберите этот параметр, чтобы просмотреть базовые данные из созданной модели.</span><span class="sxs-lookup"><span data-stu-id="57644-129">Select this option to view the underlying data from the finished model.</span></span> <span data-ttu-id="57644-130">Этот параметр доступен только для модели «дерево принятия решений».</span><span class="sxs-lookup"><span data-stu-id="57644-130">This option is only available if you build a Decision Tree model.</span></span>  
  
    -   <span data-ttu-id="57644-131">**Использовать временную модель**.</span><span class="sxs-lookup"><span data-stu-id="57644-131">**Use temporary model**.</span></span> <span data-ttu-id="57644-132">Если выбрать этот параметр, модель не будет сохранена на сервере.</span><span class="sxs-lookup"><span data-stu-id="57644-132">If you select this option, the model will not be saved to the server.</span></span> <span data-ttu-id="57644-133">Временные модели удаляются при закрытии Excel.</span><span class="sxs-lookup"><span data-stu-id="57644-133">Temporary models are deleted when you close Excel.</span></span>  
  
## <a name="more-about-clustering-models"></a><span data-ttu-id="57644-134">Дополнительные сведения о моделях кластеризации</span><span class="sxs-lookup"><span data-stu-id="57644-134">More about Clustering Models</span></span>  
 <span data-ttu-id="57644-135">Чтобы изменить алгоритм кластеризации, используемый этим мастером, нажмите кнопку **Дополнительно** и в диалоговом окне **Параметры алгоритма** .</span><span class="sxs-lookup"><span data-stu-id="57644-135">You can change the clustering algorithm used by this wizard by clicking **Advanced** and using the **Algorithm Parameters** dialog box.</span></span>  
  
 <span data-ttu-id="57644-136">Алгоритм кластеризации Майкрософт предоставляет следующие методы кластеризации:</span><span class="sxs-lookup"><span data-stu-id="57644-136">The Microsoft Clustering algorithm provides these clustering methods:</span></span>  
  
-   <span data-ttu-id="57644-137">К-средние, масштабируемые и не масштабируемые.</span><span class="sxs-lookup"><span data-stu-id="57644-137">K-means -  scalable or non-scaling.</span></span>  
  
-   <span data-ttu-id="57644-138">Максимизация ожиданий (EM), масштабируемая и не масштабируемая.</span><span class="sxs-lookup"><span data-stu-id="57644-138">Expectation Maximization (EM) - scalable or non-scaling.</span></span>  
  
 <span data-ttu-id="57644-139">Также можно использовать параметр CLUSTER_SEED для контроля начального значения и обеспечения того, что повторяющиеся модели, использующие один и тот же набор данных, будут давать одинаковые результаты.</span><span class="sxs-lookup"><span data-stu-id="57644-139">You can also use the CLUSTER_SEED parameter to control the starting value and ensure that repeated models using the same data set have the same results.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="57644-140">Требования</span><span class="sxs-lookup"><span data-stu-id="57644-140">Requirements</span></span>  
 <span data-ttu-id="57644-141">Чтобы использовать мастер кластеризации, необходимо установить соединение с базой данных служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57644-141">To use the Cluster wizard, you must be connected to a [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="57644-142">Дополнительные сведения см. [в разделе Подключение к источнику данных &#40;клиент интеллектуального анализа данных для Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="57644-142">For more information, see [Connect to Source Data &#40;Data Mining Client for Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57644-143">См. также:</span><span class="sxs-lookup"><span data-stu-id="57644-143">See Also</span></span>  
 <span data-ttu-id="57644-144">[Создание модели интеллектуального анализа данных](creating-a-data-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="57644-144">[Creating a Data Mining Model](creating-a-data-mining-model.md) </span></span>  
 [<span data-ttu-id="57644-145">Определение категорий &#40;средств анализа таблиц для Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="57644-145">Detect Categories &#40;Table Analysis Tools for Excel&#41;</span></span>](detect-categories-table-analysis-tools-for-excel.md)  
  
  
