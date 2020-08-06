---
title: Запросы детализации (интеллектуальный анализ данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- AllowDrillThrough property
- drillthrough [Analysis Services]
- drillthrough [DMX]
ms.assetid: 246c784b-1b0c-4f0b-96f7-3af265e67051
author: minewiskan
ms.author: owend
ms.openlocfilehash: 21e8c6f7cb6938e629be9d252c208c61c04d17d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666890"
---
# <a name="drillthrough-queries-data-mining"></a><span data-ttu-id="f9e91-102">Запросы детализации (интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="f9e91-102">Drillthrough Queries (Data Mining)</span></span>
  <span data-ttu-id="f9e91-103">*Запрос детализации* позволяет извлекать сведения из базовых вариантов или данных структуры, отсылая запрос в модель интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="f9e91-103">A *drillthrough query* lets you retrieve details from the underlying cases or structure data, by sending a query to the mining model.</span></span> <span data-ttu-id="f9e91-104">Детализация применяется в том случае, если нужно просмотреть варианты, использованные для обучения модели, в отличие от вариантов, которые используются для ее проверки, либо чтобы просмотреть дополнительных сведения из данных варианта.</span><span class="sxs-lookup"><span data-stu-id="f9e91-104">Drillthrough is useful if you want to view the cases that were used to train the model, versus the cases that are used to test the model, or if you want to see additional details from the case data.</span></span>  
  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="f9e91-105">предусматривает два различных варианта детализации.</span><span class="sxs-lookup"><span data-stu-id="f9e91-105">Data Mining provides two different options for drillthrough:</span></span>  
  
-   <span data-ttu-id="f9e91-106">Детализация до **вариантов модели**</span><span class="sxs-lookup"><span data-stu-id="f9e91-106">Drilling through to the **model cases**</span></span>  
  
     <span data-ttu-id="f9e91-107">Детализация до вариантов модели используется, если нужно перейти от определенного шаблона в модели, такого как кластер или ветвь дерева принятия решений, и просмотреть сведения об отдельных вариантах.</span><span class="sxs-lookup"><span data-stu-id="f9e91-107">Drillthrough to model cases is used when you want to go from a specific pattern in the model-such as a cluster or branch of a decision tree-and view details about the individual cases.</span></span>  
  
-   <span data-ttu-id="f9e91-108">Детализация до **вариантов структуры**</span><span class="sxs-lookup"><span data-stu-id="f9e91-108">Drilling through to the **structure cases**</span></span>  
  
     <span data-ttu-id="f9e91-109">Детализация до вариантов структуры используется в том случае, когда структура содержит сведения, которые могут не быть доступными в модели.</span><span class="sxs-lookup"><span data-stu-id="f9e91-109">Drillthrough to structure cases is used when the structure contains information that might not be available in the model.</span></span> <span data-ttu-id="f9e91-110">Например, не используются контактные сведения покупателей в модели кластеризации, даже если эти данные включены в структуру.</span><span class="sxs-lookup"><span data-stu-id="f9e91-110">For example, you would not use customer contact information in a clustering model, even if the data was included in the structure.</span></span> <span data-ttu-id="f9e91-111">Однако после создания модели может потребоваться получить контактные сведения покупателей, сгруппированных в определенный кластер.</span><span class="sxs-lookup"><span data-stu-id="f9e91-111">However, after you create the model, you might want to retrieve contact information for customers who are grouped into a particular cluster.</span></span>  
  
 <span data-ttu-id="f9e91-112">В данном разделе будут приведены примеры создания таких запросов.</span><span class="sxs-lookup"><span data-stu-id="f9e91-112">This section provides examples of how you can create these queries.</span></span>  
  
 [<span data-ttu-id="f9e91-113">Использование детализации в конструкторе интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="f9e91-113">Using Drillthrough in Data Mining Designer</span></span>](#bkmk_Designer)  
  
 [<span data-ttu-id="f9e91-114">Создание запросов детализации с помощью расширений интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="f9e91-114">Creating Drillthrough Queries using DMX</span></span>](#bkmk_DMX)  
  
 [<span data-ttu-id="f9e91-115">Вопросы, связанные с использованием детализации</span><span class="sxs-lookup"><span data-stu-id="f9e91-115">Considerations When Using Drillthrough</span></span>](#bkmk_Considerations)  
  
-   [<span data-ttu-id="f9e91-116">Проблемы с безопасностью</span><span class="sxs-lookup"><span data-stu-id="f9e91-116">Security Issues</span></span>](#bkmk_Security)  
  
-   [<span data-ttu-id="f9e91-117">Ограничения</span><span class="sxs-lookup"><span data-stu-id="f9e91-117">Limitations</span></span>](#bkmk_Limits)  
  
##  <a name="using-drillthrough-in-data-mining-designer"></a><a name="bkmk_Designer"></a><span data-ttu-id="f9e91-118">Использование детализации в конструкторе интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="f9e91-118">Using Drillthrough in Data Mining Designer</span></span>  
 <span data-ttu-id="f9e91-119">Возможность детализации предусмотрена в модели интеллектуального анализа данных, и при наличии соответствующих разрешений во время просмотра модели можно щелкнуть узел в соответствующем средстве просмотра и получить подробные сведения о вариантах в данном узле.</span><span class="sxs-lookup"><span data-stu-id="f9e91-119">If a mining model has been configured to allow drillthrough, and if you have the appropriate permissions, when you browse the model, you can click on a node in the appropriate viewer and retrieve detailed information about the cases in that particular node.</span></span>  
  
 <span data-ttu-id="f9e91-120">[Детализация до данных вариантов из модели интеллектуального анализа](drill-through-to-case-data-from-a-mining-model.md)данных.</span><span class="sxs-lookup"><span data-stu-id="f9e91-120">[Drill Through to Case Data from a Mining Model](drill-through-to-case-data-from-a-mining-model.md).</span></span>  
  
 <span data-ttu-id="f9e91-121">Если при обработке структуры интеллектуального анализа данных обучающие варианты кэшировались и у пользователя есть необходимые разрешения, то можно получать сведения из вариантов модели и структуры интеллектуального анализа данных, включая столбцы, не включенные в модель интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="f9e91-121">If the training cases were cached when you processed the mining structure, and you have the necessary permissions, you can return information from the model cases and from the mining structure, including columns that were not included in the mining model.</span></span>  
  
##  <a name="creating-drillthrough-queries-using-dmx"></a><a name="bkmk_DMX"></a><span data-ttu-id="f9e91-122">Создание запросов детализации с помощью расширений интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="f9e91-122">Creating Drillthrough Queries using DMX</span></span>  
 <span data-ttu-id="f9e91-123">Можно выполнять детализацию данных варианта путем создания запроса расширений интеллектуального анализа данных в том случае, если у вас имеются разрешения для модели или для структуры.</span><span class="sxs-lookup"><span data-stu-id="f9e91-123">You can drill through to case data by creating a DMX query, if you have permissions on the model or on the structure.</span></span> <span data-ttu-id="f9e91-124">Примеры синтаксиса для создания запросов детализации в расширении интеллектуального анализа данных содержатся в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="f9e91-124">For examples of the syntax for creating drillthrough queries in DMX, see the following topic:</span></span>  
  
 [<span data-ttu-id="f9e91-125">Создание запросов детализации с помощью расширений интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="f9e91-125">Create Drillthrough Queries using DMX</span></span>](create-drillthrough-queries-using-dmx.md)  
  
##  <a name="considerations-when-using-drillthrough"></a><a name="bkmk_Considerations"></a><span data-ttu-id="f9e91-126">Рекомендации по использованию детализации</span><span class="sxs-lookup"><span data-stu-id="f9e91-126">Considerations When Using Drillthrough</span></span>  
  
-   <span data-ttu-id="f9e91-127">Если используется мастер интеллектуального анализа данных, то включить детализацию можно на его последней странице.</span><span class="sxs-lookup"><span data-stu-id="f9e91-127">If you use the Data Mining Wizard, the option to enable drillthrough to the model cases is on the final page of the wizard.</span></span> <span data-ttu-id="f9e91-128">По умолчанию детализация отключена.</span><span class="sxs-lookup"><span data-stu-id="f9e91-128">Drillthrough is disabled by default.</span></span> <span data-ttu-id="f9e91-129">Дополнительные сведения см. в разделе [Завершение работы мастера (мастер интеллектуального анализа данных)](../completing-the-wizard-data-mining-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="f9e91-129">For more information, see [Completing the Wizard &#40;Data Mining Wizard&#41;](../completing-the-wizard-data-mining-wizard.md).</span></span>  
  
-   <span data-ttu-id="f9e91-130">Возможность детализации можно добавить в существующую модель интеллектуального анализа данных, но в этом случае модель необходимо обработать повторно, чтобы изменения вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="f9e91-130">You can add the ability to drill through on an existing mining model, but if you do, the model must be reprocessed before you can drill through to the data.</span></span>  
  
-   <span data-ttu-id="f9e91-131">Детализация работает посредством получения информации об обучающих вариантах структуры интеллектуального анализа данных. Эта информация была кэширована при обработке структуры.</span><span class="sxs-lookup"><span data-stu-id="f9e91-131">Drillthrough works by retrieving information about the training cases that was cached when you processed the mining structure.</span></span> <span data-ttu-id="f9e91-132">Поэтому, если произвести удаление всех кэшированных данных изменением свойства <xref:Microsoft.AnalysisServices.MiningStructureCacheMode> на `ClearAfterProcessing`, детализация работать не будет.</span><span class="sxs-lookup"><span data-stu-id="f9e91-132">Therefore, if you cleared the cached data after processing the structure by changing the <xref:Microsoft.AnalysisServices.MiningStructureCacheMode> property to `ClearAfterProcessing`, drillthrough will not work.</span></span> <span data-ttu-id="f9e91-133">Чтобы разрешить детализацию до столбцов структуры, нужно изменить значение свойства <xref:Microsoft.AnalysisServices.MiningStructureCacheMode> на `KeepTrainingCases` а затем выполнить повторную обработку структуры.</span><span class="sxs-lookup"><span data-stu-id="f9e91-133">To enable drillthrough to structure columns, you must change the <xref:Microsoft.AnalysisServices.MiningStructureCacheMode> property to `KeepTrainingCases` and then reprocess the structure.</span></span>  
  
-   <span data-ttu-id="f9e91-134">Если детализация разрешена в модели интеллектуального анализа данных, но не разрешена в структуре, то сведения можно просматривать только из вариантов модели, но не из структуры интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="f9e91-134">If the mining structure does not allow drillthrough but the mining model does, you can view information only from the model cases, and not from the mining structure.</span></span>  
  
###  <a name="security-issues-for-drillthrough"></a><a name="bkmk_Security"></a><span data-ttu-id="f9e91-135">Проблемы безопасности для детализации</span><span class="sxs-lookup"><span data-stu-id="f9e91-135">Security Issues for Drillthrough</span></span>  
 <span data-ttu-id="f9e91-136">Если необходимо выполнить детализацию до вариантов структуры из модели, необходимо убедиться, что свойство [AllowDrillthrough](https://docs.microsoft.com/bi-reference/assl/properties/allowdrillthrough-element-assl) в структуре интеллектуального анализа данных и модели интеллектуального анализа данных имеет значение `True` .</span><span class="sxs-lookup"><span data-stu-id="f9e91-136">If you want to drill through to structure cases from the model, you must verify that both the mining structure and the mining model have the [AllowDrillThrough](https://docs.microsoft.com/bi-reference/assl/properties/allowdrillthrough-element-assl) property set to `True`.</span></span> <span data-ttu-id="f9e91-137">Более того, необходимо быть членом роли, обладающей разрешением на детализацию как в структуре, так и в модели.</span><span class="sxs-lookup"><span data-stu-id="f9e91-137">Moreover, you must be a member of a role that has drillthrough permissions on both the structure and the model.</span></span> <span data-ttu-id="f9e91-138">Дополнительные сведения о создании ролей см. в разделе [Конструктор ролей (службы Analysis Services — многомерные данные)](https://msdn.microsoft.com/library/ms189696(v=sql.120).aspx).</span><span class="sxs-lookup"><span data-stu-id="f9e91-138">For information about how to create roles, see [Role Designer &#40;Analysis Services - Multidimensional Data&#41;](https://msdn.microsoft.com/library/ms189696(v=sql.120).aspx).</span></span> <span data-ttu-id="f9e91-139">см.</span><span class="sxs-lookup"><span data-stu-id="f9e91-139">see.</span></span>  
  
 <span data-ttu-id="f9e91-140">Разрешения на детализацию устанавливаются отдельно для структуры и для модели.</span><span class="sxs-lookup"><span data-stu-id="f9e91-140">Drillthrough permissions are set separately on the structure and model.</span></span> <span data-ttu-id="f9e91-141">Разрешение на детализацию модели позволяет проводить детализацию на основе модели, даже если у пользователя нет разрешения на детализацию структуры.</span><span class="sxs-lookup"><span data-stu-id="f9e91-141">The model permission lets you drill through from the model, even if you do not have permissions on the structure.</span></span> <span data-ttu-id="f9e91-142">Разрешения на детализацию структуры предоставляют дополнительную возможность включать столбцы структуры в запросы детализации с помощью функции [StructureColumn (DMX)](/sql/dmx/structurecolumn-dmx).</span><span class="sxs-lookup"><span data-stu-id="f9e91-142">Drillthrough permissions on the structure provide the additional ability to include structure columns in drillthrough queries from the model, by using the [StructureColumn &#40;DMX&#41;](/sql/dmx/structurecolumn-dmx) function.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f9e91-143">Если включить детализацию как структуры, так и модели интеллектуального анализа данных, то любой пользователь, являющийся членом роли с разрешениями детализации в модели, также видит столбцы в структуре, даже если эти столбцы не входят в модель интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="f9e91-143">If you enable drillthrough on both the mining structure and the mining model, any user who is a member of a role that has drillthrough permissions on the mining model can also view columns in the mining structure, even if those columns are not included in the mining model.</span></span> <span data-ttu-id="f9e91-144">Поэтому, чтобы защитить конфиденциальные данные, необходимо настроить в представлении источника данных маскирование персональных данных и разрешать доступ к детализации структуры интеллектуального анализа данных только при необходимости.</span><span class="sxs-lookup"><span data-stu-id="f9e91-144">Therefore, to protect sensitive data, you should set up the data source view to mask personal information, and allow drillthrough access on the mining structure only when necessary.</span></span>  
  
###  <a name="limitations-on-drillthrough"></a><a name="bkmk_Limits"></a><span data-ttu-id="f9e91-145">Ограничения детализации</span><span class="sxs-lookup"><span data-stu-id="f9e91-145">Limitations on Drillthrough</span></span>  
  
-   <span data-ttu-id="f9e91-146">Приведенные ниже ограничения относятся к операциям по детализации с моделью и зависят от алгоритма, с помощью которого была создана модель.</span><span class="sxs-lookup"><span data-stu-id="f9e91-146">The following limitations apply to drillthrough operations on a model, depending on the algorithm that was used to create the model:</span></span>  
  
|<span data-ttu-id="f9e91-147">Имя алгоритма</span><span class="sxs-lookup"><span data-stu-id="f9e91-147">Algorithm name</span></span>|<span data-ttu-id="f9e91-148">Проблема</span><span class="sxs-lookup"><span data-stu-id="f9e91-148">Issue</span></span>|  
|--------------------|-----------|  
|<span data-ttu-id="f9e91-149">Упрощенный алгоритм Байеса (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="f9e91-149">Microsoft Naïve Bayes algorithm</span></span>|<span data-ttu-id="f9e91-150">Не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="f9e91-150">Not supported.</span></span> <span data-ttu-id="f9e91-151">В этих алгоритмах не назначаются варианты для отдельных узлов содержимого.</span><span class="sxs-lookup"><span data-stu-id="f9e91-151">These algorithms do not assign cases to specific nodes in the content.</span></span>|  
|<span data-ttu-id="f9e91-152">Алгоритм нейронной сети (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="f9e91-152">Microsoft Neural Network algorithm</span></span>|<span data-ttu-id="f9e91-153">Не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="f9e91-153">Not supported.</span></span> <span data-ttu-id="f9e91-154">В этих алгоритмах не назначаются варианты для отдельных узлов содержимого.</span><span class="sxs-lookup"><span data-stu-id="f9e91-154">These algorithms do not assign cases to specific nodes in the content.</span></span>|  
|<span data-ttu-id="f9e91-155">Алгоритм логистической регрессии (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="f9e91-155">Microsoft Logistic Regression algorithm</span></span>|<span data-ttu-id="f9e91-156">Не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="f9e91-156">Not supported.</span></span> <span data-ttu-id="f9e91-157">В этих алгоритмах не назначаются варианты для отдельных узлов содержимого.</span><span class="sxs-lookup"><span data-stu-id="f9e91-157">These algorithms do not assign cases to specific nodes in the content.</span></span>|  
|<span data-ttu-id="f9e91-158">Алгоритм линейной регрессии (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="f9e91-158">Microsoft Linear Regression algorithm</span></span>|<span data-ttu-id="f9e91-159">Поддерживается.</span><span class="sxs-lookup"><span data-stu-id="f9e91-159">Supported.</span></span> <span data-ttu-id="f9e91-160">Однако, поскольку модель содержит только один узел, `All`, при детализации возвращаются все обучающие варианты модели.</span><span class="sxs-lookup"><span data-stu-id="f9e91-160">However, because the model creates a single node, `All`, drilling through returns all the training cases for the model.</span></span> <span data-ttu-id="f9e91-161">Если задан большой обучающий набор, то загрузка результатов может занять много времени.</span><span class="sxs-lookup"><span data-stu-id="f9e91-161">If the training set is large, loading the results may take a very long time.</span></span>|  
|<span data-ttu-id="f9e91-162">Алгоритм временных рядов (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="f9e91-162">Microsoft Time Series algorithm</span></span>|<span data-ttu-id="f9e91-163">Поддерживается.</span><span class="sxs-lookup"><span data-stu-id="f9e91-163">Supported.</span></span> <span data-ttu-id="f9e91-164">Однако нельзя выполнять детализацию структуры или данных вариантов с помощью **Средства просмотра моделей интеллектуального анализа данных** в конструкторе интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="f9e91-164">However, you cannot drill through to structure or case data by using the **Mining Model Viewer** in Data Mining Designer.</span></span> <span data-ttu-id="f9e91-165">Вместо этого необходимо создать DMX-запрос.</span><span class="sxs-lookup"><span data-stu-id="f9e91-165">You must create a DMX query instead.</span></span><br /><br /> <span data-ttu-id="f9e91-166">Кроме того, нельзя выполнять детализацию по конкретным узлам или писать DMX-запросы для получения вариантов из конкретных узлов модели временных рядов.</span><span class="sxs-lookup"><span data-stu-id="f9e91-166">Also, you cannot drill through to specific nodes, or write a DMX query to retrieve cases in specific nodes of a time series model.</span></span> <span data-ttu-id="f9e91-167">Данные вариантов можно извлечь либо из модели, либо из структуры по другим критериям, например по значениям атрибутов.</span><span class="sxs-lookup"><span data-stu-id="f9e91-167">You can retrieve case data from either the model or the structure by using other criteria, such as date or attribute values.</span></span><br /><br /> <span data-ttu-id="f9e91-168">Можно также получить даты вариантов в модели с помощью функции [Журнал (DMX)](/sql/dmx/lag-dmx).</span><span class="sxs-lookup"><span data-stu-id="f9e91-168">You can also return the dates from the cases in the model, by using the [Lag &#40;DMX&#41;](/sql/dmx/lag-dmx) function.</span></span><br /><br /> <span data-ttu-id="f9e91-169">Просмотреть узлы ARTXP и ARIMA, созданные алгоритмом временных рядов (Майкрософт), может быть проще с помощью [средства просмотра деревьев содержимого общего вида (Майкрософт) (интеллектуальный анализ данных)](../microsoft-generic-content-tree-viewer-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="f9e91-169">If you wish to view details of the ARTXP and ARIMA nodes created by the Microsoft Time Series algorithm, you can use the [Microsoft Generic Content Tree Viewer &#40;Data Mining&#41;](../microsoft-generic-content-tree-viewer-data-mining.md).</span></span>|  
  
##  <a name="related-tasks"></a><a name="bkmk_Tasks"></a> <span data-ttu-id="f9e91-170">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="f9e91-170">Related Tasks</span></span>  
 <span data-ttu-id="f9e91-171">Используйте следующие ссылки для работы с детализацией в конкретных сценариях.</span><span class="sxs-lookup"><span data-stu-id="f9e91-171">Use the following links to work with drillthrough in specific scenarios.</span></span>  
  
|<span data-ttu-id="f9e91-172">Задача</span><span class="sxs-lookup"><span data-stu-id="f9e91-172">Task</span></span>|<span data-ttu-id="f9e91-173">Ссылка</span><span class="sxs-lookup"><span data-stu-id="f9e91-173">Link</span></span>|  
|----------|----------|  
|<span data-ttu-id="f9e91-174">Процедуры, описывающие использование детализации в конструкторе интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="f9e91-174">Procedure describing use of drillthrough in the Data Mining Designer</span></span>|[<span data-ttu-id="f9e91-175">выполнить детализацию до данных вариантов из модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="f9e91-175">Drill Through to Case Data from a Mining Model</span></span>](drill-through-to-case-data-from-a-mining-model.md)|  
|<span data-ttu-id="f9e91-176">Изменение существующей модели интеллектуального анализа данных для разрешения детализации</span><span class="sxs-lookup"><span data-stu-id="f9e91-176">To alter an existing mining model to allow drillthrough</span></span>|[<span data-ttu-id="f9e91-177">включить детализацию для модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="f9e91-177">Enable Drillthrough for a Mining Model</span></span>](enable-drillthrough-for-a-mining-model.md)|  
|<span data-ttu-id="f9e91-178">Включение детализации для структуры интеллектуального анализа данных с помощью предложения DMX WITH DRILLTHROUGH</span><span class="sxs-lookup"><span data-stu-id="f9e91-178">Enabling drillthrough on a mining structure by using the DMX WITH DRILLTHROUGH clause</span></span>|[<span data-ttu-id="f9e91-179">СОЗДАНИЕ СТРУКТУРЫ ИНТЕЛЛЕКТУАЛЬНОГО АНАЛИЗА ДАННЫХ (DMX)</span><span class="sxs-lookup"><span data-stu-id="f9e91-179">CREATE MINING STRUCTURE &#40;DMX&#41;</span></span>](/sql/dmx/create-mining-structure-dmx)|  
|<span data-ttu-id="f9e91-180">Сведения о присвоении разрешений, относящихся к детализации структур и моделей интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="f9e91-180">For information about assigning permissions that apply to drillthrough on mining structures and mining models</span></span>|[<span data-ttu-id="f9e91-181">Предоставление разрешений структурам интеллектуального анализа данных и моделям интеллектуального анализа данных (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="f9e91-181">Grant permissions on data mining structures and models &#40;Analysis Services&#41;</span></span>](../multidimensional-models/grant-permissions-on-data-mining-structures-and-models-analysis-services.md)|  
  
## <a name="see-also"></a><span data-ttu-id="f9e91-182">См. также:</span><span class="sxs-lookup"><span data-stu-id="f9e91-182">See Also</span></span>  
 <span data-ttu-id="f9e91-183">[Средства просмотра моделей интеллектуального анализа данных](data-mining-model-viewers.md) </span><span class="sxs-lookup"><span data-stu-id="f9e91-183">[Data Mining Model Viewers](data-mining-model-viewers.md) </span></span>  
 [<span data-ttu-id="f9e91-184">Запросы интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="f9e91-184">Data Mining Queries</span></span>](data-mining-queries.md)  
  
  