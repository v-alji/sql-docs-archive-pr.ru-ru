---
title: Использование детализации данных структуры (учебник по интеллектуальному анализу данных — базовый) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a693979c-0564-4d6d-b35d-cbbc8f350469
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 49a1ced27150676def541548f47a90a3f847c8ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654634"
---
# <a name="using-drillthrough-on-structure-data-basic-data-mining-tutorial"></a><span data-ttu-id="e9035-102">Использование детализации для данных структуры (учебник по интеллектуальному анализу данных — начальный уровень)</span><span class="sxs-lookup"><span data-stu-id="e9035-102">Using Drillthrough on Structure Data (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="e9035-103">В рамках своей рекламной кампании [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] отправляется сообщение электронной почты потенциальным клиентам в 34-40 возрасте.</span><span class="sxs-lookup"><span data-stu-id="e9035-103">As part of their advertising campaign, [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] is sending a mailer to potential customers in the 34-40 age demographic.</span></span> <span data-ttu-id="e9035-104">В отделе маркетинга принимается решение также отправить рассылку заказчикам, купившим велосипеды в [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] более пяти лет назад.</span><span class="sxs-lookup"><span data-stu-id="e9035-104">The marketing department has decided that they would also like to send the mailer to the customers who purchased bikes from [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] more than five years ago.</span></span> <span data-ttu-id="e9035-105">На этом занятии будут определены заказчики, имеющие старые велосипеды, и получена их контактная информация.</span><span class="sxs-lookup"><span data-stu-id="e9035-105">In this lesson you will identify customers with older bikes and retrieve their contact information.</span></span> <span data-ttu-id="e9035-106">Такая информация не включена в модель, но включена в структуру.</span><span class="sxs-lookup"><span data-stu-id="e9035-106">This information is not included in the model, but is included in the structure.</span></span> <span data-ttu-id="e9035-107">Чтобы получить контактные данные, прежде всего необходимо включить для структуры функцию детализации, а затем с помощью этой функции найти имена и адреса целевых заказчиков.</span><span class="sxs-lookup"><span data-stu-id="e9035-107">To retrieve the contact information you will first ensure that drillthrough is enabled for the structure and then you will use drillthrough to reveal the names and addresses of the targeted customers.</span></span>  
  
### <a name="to-enable-drillthrough-on-a-mining-model"></a><span data-ttu-id="e9035-108">Включение детализации в модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="e9035-108">To enable drillthrough on a mining model</span></span>  
  
1.  <span data-ttu-id="e9035-109">В службах [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] на вкладке **модели интеллектуального анализа** данных конструктора интеллектуального анализа щелкните правой кнопкой мыши модель **TM_Decision_Tree** и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="e9035-109">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], on the **Mining Models** tab of Data Mining Designer, right-click the **TM_Decision_Tree** model, and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="e9035-110">В окне свойств щелкните свойство **AllowDrillthrough**и выберите значение **True**.</span><span class="sxs-lookup"><span data-stu-id="e9035-110">In the Properties windows, click **AllowDrillthrough**, and select **True**.</span></span>  
  
3.  <span data-ttu-id="e9035-111">На вкладке Модели интеллектуального анализа данных щелкните правой кнопкой мыши нужную модель и выберите команду **Обработать модель**.</span><span class="sxs-lookup"><span data-stu-id="e9035-111">In the Mining Models tab, right-click the model, and select **Process Model**.</span></span>  
  
 <span data-ttu-id="e9035-112">Дополнительные сведения см. в разделе [запросы детализации &#40;интеллектуальный анализ данных&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md)</span><span class="sxs-lookup"><span data-stu-id="e9035-112">For more information, see [Drillthrough Queries &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md)</span></span>  
  
### <a name="to-view-drillthrough-data-from-a-mining-model"></a><span data-ttu-id="e9035-113">Просмотр данных детализации в модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="e9035-113">To view drillthrough data from a mining model</span></span>  
  
1.  <span data-ttu-id="e9035-114">В конструкторе интеллектуального анализа данных перейдите на вкладку **Средство просмотра моделей интеллектуального анализа данных** .</span><span class="sxs-lookup"><span data-stu-id="e9035-114">In Data Mining Designer, click the **Mining Model Viewer** tab.</span></span>  
  
2.  <span data-ttu-id="e9035-115">Выберите модель **TM_Decision_Tree** из списка **модель интеллектуального анализа данных** .</span><span class="sxs-lookup"><span data-stu-id="e9035-115">Select the **TM_Decision_Tree** model from the **Mining Model** list.</span></span>  
  
3.  <span data-ttu-id="e9035-116">Измените значение параметра **фон** на `1` .</span><span class="sxs-lookup"><span data-stu-id="e9035-116">Change the **Background** value to `1`.</span></span> <span data-ttu-id="e9035-117">В результате этого будет отображена только та часть модели, которая связана с заказчиком, купившим велосипеды.</span><span class="sxs-lookup"><span data-stu-id="e9035-117">By doing this, you show only the part of the model that is related to customer who bought bikes.</span></span>  
  
4.  <span data-ttu-id="e9035-118">Выберите средство просмотра деревьев (Майкрософт) в списке **Средство просмотра** .</span><span class="sxs-lookup"><span data-stu-id="e9035-118">Select the Microsoft Tree viewer from the **Viewer** list.</span></span> <span data-ttu-id="e9035-119">Средство просмотра будет принудительно обновлено с учетом новых условий фильтрации.</span><span class="sxs-lookup"><span data-stu-id="e9035-119">This will force the viewer to refresh with the new filter conditions.</span></span> <span data-ttu-id="e9035-120">Затем найдите узел **Age >= 34 и <41** и щелкните узел правой кнопкой мыши.</span><span class="sxs-lookup"><span data-stu-id="e9035-120">Then, locate the **Age >=34 and <41** node and right-click the node.</span></span>  
  
5.  <span data-ttu-id="e9035-121">Чтобы открыть окно **Детализация**, выберите пункт **Детализация** , а затем **Столбцы модели и структуры** .</span><span class="sxs-lookup"><span data-stu-id="e9035-121">Select **Drill Through**, and then select **Model and Structure Columns** to open the **Drill Through** window.</span></span>  
  
6.  <span data-ttu-id="e9035-122">Перейдите к столбцу **Структура.Дата первого приобретения** для просмотра дат покупки старых велосипедов.</span><span class="sxs-lookup"><span data-stu-id="e9035-122">Scroll to the **Structure.Date First Purchase** column to view the purchase dates for the older bikes.</span></span>  
  
7.  <span data-ttu-id="e9035-123">Чтобы скопировать данные в буфер обмена, щелкните правой кнопкой мыши строку таблицы и выберите команду **Копировать все**.</span><span class="sxs-lookup"><span data-stu-id="e9035-123">To copy the data to the Clipboard, right-click any row in the table, and select **Copy All**.</span></span>  
  
 <span data-ttu-id="e9035-124">Поздравляем! Начальный уровень учебника по основам интеллектуального анализа данных пройден.</span><span class="sxs-lookup"><span data-stu-id="e9035-124">Congratulations, you have completed the basic data mining tutorial.</span></span> <span data-ttu-id="e9035-125">Вы научились использовать средства интеллектуального анализа данных. Теперь рекомендуется пройти средний уровень учебника по интеллектуальному анализу данных, в котором описывается процесс создания моделей для прогнозирования, анализа покупательского поведения и кластеризации последовательностей.</span><span class="sxs-lookup"><span data-stu-id="e9035-125">Now that you are comfortable using the data mining tools, we recommend that you also complete the intermediate data mining tutorial, which demonstrates how to create models for forecasting, market basket analysis, and sequence clustering.</span></span>  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="e9035-126">Предыдущая задача занятия</span><span class="sxs-lookup"><span data-stu-id="e9035-126">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="e9035-127">Создание прогнозов (учебник по интеллектуальному анализу данных — начальный уровень)</span><span class="sxs-lookup"><span data-stu-id="e9035-127">Creating Predictions &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-predictions-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="e9035-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="e9035-128">See Also</span></span>  
 [<span data-ttu-id="e9035-129">Создание прогнозирующего запроса с помощью построителя прогнозирующих запросов</span><span class="sxs-lookup"><span data-stu-id="e9035-129">Create a Prediction Query Using the Prediction Query Builder</span></span>](../../2014/analysis-services/data-mining/create-a-prediction-query-using-the-prediction-query-builder.md)  
  
  
