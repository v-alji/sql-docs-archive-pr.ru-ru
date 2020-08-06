---
title: Создание структуры модели интеллектуального анализа данных кластеризации последовательностей (учебник по интеллектуальному анализу данных — средний уровень) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: e9339227-6c2e-4c4b-8be2-8c1960bc4a8d
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 37d0a1738a758a9d8c4fd6b80310037937a9803f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658006"
---
# <a name="creating-a-sequence-clustering-mining-model-structure-intermediate-data-mining-tutorial"></a><span data-ttu-id="840ff-102">Создание структуры модели интеллектуального анализа данных кластеризации последовательностей (учебник по интеллектуальному анализу данных — средний уровень)</span><span class="sxs-lookup"><span data-stu-id="840ff-102">Creating a Sequence Clustering Mining Model Structure (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="840ff-103">Первым шагом при создании модели интеллектуального анализа кластеризации последовательностей является использование мастера интеллектуального анализа данных для создания новой структуры интеллектуального анализа и модели интеллектуального анализа данных на основе [!INCLUDE[msCoName](../includes/msconame-md.md)] алгоритма кластеризации последовательностей.</span><span class="sxs-lookup"><span data-stu-id="840ff-103">The first step in creating a sequence clustering mining model is to use the Data Mining Wizard to create a new mining structure and a mining model based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Sequence Clustering algorithm.</span></span>  
  
 <span data-ttu-id="840ff-104">Для этой цели будет использоваться представление источника данных, которое использовалось для анализа покупательского поведения, к которому добавляется столбец, содержащий идентификатор `sequence`.</span><span class="sxs-lookup"><span data-stu-id="840ff-104">You will use the same data source view that you used for the market basket analysis, but you will add a column that contains the `sequence` identifier.</span></span> <span data-ttu-id="840ff-105">В данном сценарии «sequence» означает порядок, в котором покупатели добавляют элементы в свою корзину во время покупок.</span><span class="sxs-lookup"><span data-stu-id="840ff-105">In this scenario, the sequence means the order in which the customer added items to the shopping basket.</span></span>  
  
 <span data-ttu-id="840ff-106">Также будут добавлены несколько столбцов, которые используются в одной из моделей для группировки покупателей по демографическому признаку.</span><span class="sxs-lookup"><span data-stu-id="840ff-106">You will also add some columns that are used in one of the models to group customers by demographics.</span></span>  
  
### <a name="to-create-a-sequence-clustering-structure-and-model"></a><span data-ttu-id="840ff-107">Создание структуры кластеризации последовательностей и модели</span><span class="sxs-lookup"><span data-stu-id="840ff-107">To create a sequence clustering structure and model</span></span>  
  
1.  <span data-ttu-id="840ff-108">В обозреватель решений в щелкните [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] правой кнопкой мыши элемент **структуры интеллектуального анализа данных** и выберите пункт **создать структуру интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="840ff-108">In Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], right-click **Mining Structures** and select **New Mining Structure**.</span></span>  
  
2.  <span data-ttu-id="840ff-109">На странице **Вас приветствует мастер интеллектуального анализа данных** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="840ff-109">On the **Welcome to the Data Mining Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="840ff-110">На странице **Выбор метода определения** убедитесь, что выбран параметр **из существующей реляционной базы данных или хранилища данных** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="840ff-110">On the **Select the Definition Method** page, verify that **From existing relational database or data warehouse** is selected, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="840ff-111">На странице **Создание структуры интеллектуального анализа данных** убедитесь, что выбран параметр **создать структуру интеллектуального анализа с моделью интеллектуального** анализа.</span><span class="sxs-lookup"><span data-stu-id="840ff-111">On the **Create the Data Mining Structure** page, verify that the option **Create mining structure with a mining model** is selected.</span></span> <span data-ttu-id="840ff-112">Затем щелкните раскрывающийся список для параметра, **какой метод интеллектуального анализа данных вы хотите использовать?** и выберите пункт **Кластеризация последовательностей (Майкрософт**).</span><span class="sxs-lookup"><span data-stu-id="840ff-112">Next, click the dropdown list for the option, **Which data mining technique do you want to use?**, and select **Microsoft Sequence Clustering**.</span></span> <span data-ttu-id="840ff-113">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="840ff-113">Click **Next**.</span></span>  
  
     <span data-ttu-id="840ff-114">Откроется страница **Выбор представления источника данных** .</span><span class="sxs-lookup"><span data-stu-id="840ff-114">The **Select Data Source View** page appears.</span></span> <span data-ttu-id="840ff-115">В разделе **Доступные представления источников данных**выберите `Orders` .</span><span class="sxs-lookup"><span data-stu-id="840ff-115">Under **Available data source views**, select `Orders`.</span></span>  
  
     <span data-ttu-id="840ff-116">Заказы — это то представление источника данных, которое использовалось для сценария потребительской корзины.</span><span class="sxs-lookup"><span data-stu-id="840ff-116">Orders is the same data source view that you used for the market basket scenario.</span></span> <span data-ttu-id="840ff-117">Если вы не создали это представление источника данных, см. [руководство по добавлению представления источников данных с вложенными таблицами &#40;учебник по интеллектуальному анализу данных&#41;](../../2014/tutorials/adding-a-data-source-view-with-nested-tables-intermediate-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="840ff-117">If you have not created this data source view, see [Adding a Data Source View with Nested Tables &#40;Intermediate Data Mining Tutorial&#41;](../../2014/tutorials/adding-a-data-source-view-with-nested-tables-intermediate-data-mining-tutorial.md).</span></span>  
  
5.  <span data-ttu-id="840ff-118">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="840ff-118">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="840ff-119">На странице **Выбор типов таблиц** установите флажок Case ( **регистр** ) рядом с таблицей **vAssocSeqOrders** и установите флажок **Nested (вложенный** ) рядом с таблицей **vAssocSeqLineItems** .</span><span class="sxs-lookup"><span data-stu-id="840ff-119">On the **Specify Table Types** page, select the **Case** check box next to the **vAssocSeqOrders** table, and select the **Nested** check box next to the **vAssocSeqLineItems** table.</span></span> <span data-ttu-id="840ff-120">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="840ff-120">Click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="840ff-121">Если при выборе флажка « **case** » или « **Nested** » появляется ошибка, то возможно, что соединение в представлении источника данных неверно.</span><span class="sxs-lookup"><span data-stu-id="840ff-121">If an error occurs when you select the **Case** or **Nested** check boxes, it may be that the join in the data source view is not correct.</span></span> <span data-ttu-id="840ff-122">Вложенная таблица **vAssocSeqLineItems**должна быть подключена к таблице вариантов, **vAssocSeqOrders** с соединением типа «многие к одному».</span><span class="sxs-lookup"><span data-stu-id="840ff-122">The nested table, **vAssocSeqLineItems**, must be connected to the case table, **vAssocSeqOrders,** by a many-to-one join.</span></span> <span data-ttu-id="840ff-123">Можно изменить эту связь, щелкнув правой кнопкой мыши на линии соединения и затем изменив направление соединения на обратное.</span><span class="sxs-lookup"><span data-stu-id="840ff-123">You can edit the relationship by right-clicking on the join line and then reversing the direction of the join.</span></span> <span data-ttu-id="840ff-124">Дополнительные сведения см. в разделе [диалоговое окно "Создание или изменение связи" &#40;Analysis Services многомерных данных&#41;](../../2014/analysis-services/create-or-edit-relationship-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="840ff-124">For more information, see [Create or Edit Relationship Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](../../2014/analysis-services/create-or-edit-relationship-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
7.  <span data-ttu-id="840ff-125">На странице **Определение обучающих данных** выберите столбцы для использования в модели, установив флажок следующим образом:</span><span class="sxs-lookup"><span data-stu-id="840ff-125">On the **Specify the Training Data** page, choose the columns for use in the model by selecting a check box as follows:</span></span>  
  
    -   <span data-ttu-id="840ff-126">**IncomeGroup** Установите флажок **Вход** .</span><span class="sxs-lookup"><span data-stu-id="840ff-126">**IncomeGroup** Select the **Input** check box.</span></span>  
  
         <span data-ttu-id="840ff-127">Данный столбец содержит полезную информацию о покупателях, которую можно использовать для кластеризации.</span><span class="sxs-lookup"><span data-stu-id="840ff-127">This column contains interesting information about the customers that you can use for clustering.</span></span> <span data-ttu-id="840ff-128">Такая информация будет использоваться в первой модели и не будет учитываться во второй.</span><span class="sxs-lookup"><span data-stu-id="840ff-128">You will use it in the first model and then ignore it in the second model.</span></span>  
  
    -   <span data-ttu-id="840ff-129">**OrderNumber** Установите `Key` флажок.</span><span class="sxs-lookup"><span data-stu-id="840ff-129">**OrderNumber** Select the `Key` check box.</span></span>  
  
         <span data-ttu-id="840ff-130">Данное поле будет использоваться в качестве идентификатора таблицы вариантов либо значения `Key`.</span><span class="sxs-lookup"><span data-stu-id="840ff-130">This field will be used as the identifier for the case table, or `Key`.</span></span> <span data-ttu-id="840ff-131">В целом ключевое поле таблицы вариантов никогда не используется в качестве входных данных, поскольку ключ содержит уникальные значения, не представляющие интереса для кластеризации.</span><span class="sxs-lookup"><span data-stu-id="840ff-131">In general, you should never use the key field of the case table as an input, because the key contains unique values that are not useful for clustering.</span></span>  
  
    -   <span data-ttu-id="840ff-132">**Регион** Установите флажок **Вход** .</span><span class="sxs-lookup"><span data-stu-id="840ff-132">**Region** Select the **Input** check box.</span></span>  
  
         <span data-ttu-id="840ff-133">Данный столбец содержит полезную информацию о покупателях, которую можно использовать для кластеризации.</span><span class="sxs-lookup"><span data-stu-id="840ff-133">This column contains interesting information about the customers that you can use for clustering.</span></span> <span data-ttu-id="840ff-134">Такая информация будет использоваться в первой модели и не будет учитываться во второй.</span><span class="sxs-lookup"><span data-stu-id="840ff-134">You will use it in the first model and then ignore it in the second model.</span></span>  
  
    -   <span data-ttu-id="840ff-135">**Номер_строки** Установите флажки `Key` и **ввода** .</span><span class="sxs-lookup"><span data-stu-id="840ff-135">**LineNumber** Select the `Key` and **Input** check boxes.</span></span>  
  
         <span data-ttu-id="840ff-136">Поле **LineNumber** будет использоваться в качестве идентификатора для вложенной таблицы или `Sequence Key` .</span><span class="sxs-lookup"><span data-stu-id="840ff-136">The **LineNumber** field will be used as the identifier for the nested table, or `Sequence Key`.</span></span> <span data-ttu-id="840ff-137">Ключ для вложенной таблицы всегда должен использоваться для ввода.</span><span class="sxs-lookup"><span data-stu-id="840ff-137">The key for a nested table must always be used for input.</span></span>  
  
    -   <span data-ttu-id="840ff-138">**Модель** Установите флажки **Вход** и **прогнозируемые** .</span><span class="sxs-lookup"><span data-stu-id="840ff-138">**Model** Select the **Input** and **Predictable** check boxes.</span></span>  
  
     <span data-ttu-id="840ff-139">Убедитесь, что выбраны правильные параметры, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="840ff-139">Verify that the selections are correct, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="840ff-140">На странице **Определение содержимого и типа данных столбцов** убедитесь, что сетка содержит столбцы, типы содержимого и типы данных, приведенные в следующей таблице, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="840ff-140">On the **Specify Columns' Content and Data Type** page, verify that the grid contains the columns, content types, and data types shown in the following table, and then click **Next**.</span></span>  
  
    |<span data-ttu-id="840ff-141">Таблицы и столбцы</span><span class="sxs-lookup"><span data-stu-id="840ff-141">Tables/Columns</span></span>|<span data-ttu-id="840ff-142">Тип содержимого</span><span class="sxs-lookup"><span data-stu-id="840ff-142">Content Type</span></span>|<span data-ttu-id="840ff-143">Тип данных</span><span class="sxs-lookup"><span data-stu-id="840ff-143">Data Type</span></span>|  
    |---------------------|------------------|---------------|  
    |<span data-ttu-id="840ff-144">IncomeGroup</span><span class="sxs-lookup"><span data-stu-id="840ff-144">IncomeGroup</span></span>|<span data-ttu-id="840ff-145">Discrete</span><span class="sxs-lookup"><span data-stu-id="840ff-145">Discrete</span></span>|<span data-ttu-id="840ff-146">Text</span><span class="sxs-lookup"><span data-stu-id="840ff-146">Text</span></span>|  
    |<span data-ttu-id="840ff-147">OrderNumber</span><span class="sxs-lookup"><span data-stu-id="840ff-147">OrderNumber</span></span>|<span data-ttu-id="840ff-148">Клавиши</span><span class="sxs-lookup"><span data-stu-id="840ff-148">Key</span></span>|<span data-ttu-id="840ff-149">Text</span><span class="sxs-lookup"><span data-stu-id="840ff-149">Text</span></span>|  
    |<span data-ttu-id="840ff-150">Регион</span><span class="sxs-lookup"><span data-stu-id="840ff-150">Region</span></span>|<span data-ttu-id="840ff-151">Discrete</span><span class="sxs-lookup"><span data-stu-id="840ff-151">Discrete</span></span>|<span data-ttu-id="840ff-152">Text</span><span class="sxs-lookup"><span data-stu-id="840ff-152">Text</span></span>|  
    |<span data-ttu-id="840ff-153">vAssocSeqLineItems</span><span class="sxs-lookup"><span data-stu-id="840ff-153">vAssocSeqLineItems</span></span>|||  
    |<span data-ttu-id="840ff-154">Line Number</span><span class="sxs-lookup"><span data-stu-id="840ff-154">Line Number</span></span>|<span data-ttu-id="840ff-155">Ключевая последовательность</span><span class="sxs-lookup"><span data-stu-id="840ff-155">Key Sequence</span></span>|<span data-ttu-id="840ff-156">Long</span><span class="sxs-lookup"><span data-stu-id="840ff-156">Long</span></span>|  
    |<span data-ttu-id="840ff-157">Модель</span><span class="sxs-lookup"><span data-stu-id="840ff-157">Model</span></span>|<span data-ttu-id="840ff-158">Discrete</span><span class="sxs-lookup"><span data-stu-id="840ff-158">Discrete</span></span>|<span data-ttu-id="840ff-159">Text</span><span class="sxs-lookup"><span data-stu-id="840ff-159">Text</span></span>|  
  
9. <span data-ttu-id="840ff-160">На странице **Создание проверочного набора** измените **процент данных для тестирования** на 20, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="840ff-160">On the **Create Testing Set** page, change the **Percentage of data for testing** to 20, and then click **Next**.</span></span>  
  
10. <span data-ttu-id="840ff-161">На странице **Завершение работы мастера** для **имени структуры интеллектуального анализа данных**введите `Sequence Clustering with Region` .</span><span class="sxs-lookup"><span data-stu-id="840ff-161">On the **Completing the Wizard** page, for the **Mining structure name**, type `Sequence Clustering with Region`.</span></span>  
  
11. <span data-ttu-id="840ff-162">В поле **имя модели интеллектуального анализа данных**введите `Sequence Clustering with Region` .</span><span class="sxs-lookup"><span data-stu-id="840ff-162">For the **Mining model name**, type `Sequence Clustering with Region`.</span></span>  
  
12. <span data-ttu-id="840ff-163">Установите флажок **Разрешить детализацию** и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="840ff-163">Check the **Allow drill through** box, and then click **Finish**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="840ff-164">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="840ff-164">Next Task in Lesson</span></span>  
 [<span data-ttu-id="840ff-165">Обработка модели кластеризации последовательностей</span><span class="sxs-lookup"><span data-stu-id="840ff-165">Processing the Sequence Clustering Model</span></span>](../../2014/tutorials/processing-the-sequence-clustering-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="840ff-166">См. также:</span><span class="sxs-lookup"><span data-stu-id="840ff-166">See Also</span></span>  
 <span data-ttu-id="840ff-167">[Конструктор интеллектуального анализа данных](../../2014/analysis-services/data-mining/data-mining-designer.md) </span><span class="sxs-lookup"><span data-stu-id="840ff-167">[Data Mining Designer](../../2014/analysis-services/data-mining/data-mining-designer.md) </span></span>  
 [<span data-ttu-id="840ff-168">Алгоритм кластеризации последовательностей (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="840ff-168">Microsoft Sequence Clustering Algorithm</span></span>](../../2014/analysis-services/data-mining/microsoft-sequence-clustering-algorithm.md)  
  
  
