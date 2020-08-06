---
title: Занятие 2. Добавление моделей интеллектуального анализа данных в структуру интеллектуального анализа данных "потребительская корзина" | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d96a7a7d-35d7-4b34-abb5-f0822c256253
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: b9573d9359983e33cf23533787c26039572710ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733374"
---
# <a name="lesson-2-adding-mining-models-to-the-market-basket-mining-structure"></a><span data-ttu-id="5403d-102">Урок 2. Добавление моделей к структуре интеллектуального анализа данных покупательского поведения</span><span class="sxs-lookup"><span data-stu-id="5403d-102">Lesson 2: Adding Mining Models to the Market Basket Mining Structure</span></span>
  <span data-ttu-id="5403d-103">На этом занятии вы добавите две модели интеллектуального анализа данных в структуру интеллектуального анализа данных "потребительская корзина", созданную на [занятии 1: создание структуры интеллектуального анализа данных для потребительской корзины](../../2014/tutorials/lesson-1-creating-the-market-basket-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="5403d-103">In this lesson, you will add two mining models to the Market Basket mining structure that you created in [Lesson 1: Creating the Market Basket Mining Structure](../../2014/tutorials/lesson-1-creating-the-market-basket-mining-structure.md).</span></span> <span data-ttu-id="5403d-104">С помощью этих моделей интеллектуального анализа данных можно будет создавать прогнозы.</span><span class="sxs-lookup"><span data-stu-id="5403d-104">These mining models will allow you to create predictions.</span></span>  
  
 <span data-ttu-id="5403d-105">Для прогнозирования типов продуктов, которые клиенты могут приобретать одновременно, необходимо создать две модели интеллектуального анализа данных с помощью [алгоритма взаимосвязей (Майкрософт](../../2014/analysis-services/data-mining/microsoft-association-algorithm.md) ) и два разных значения для параметра *MINIMUM_PROBABILTY* .</span><span class="sxs-lookup"><span data-stu-id="5403d-105">To predict the types of products that customers tend to purchase at the same time, you will create two mining models using the [Microsoft Association Algorithm](../../2014/analysis-services/data-mining/microsoft-association-algorithm.md) and two different values for the *MINIMUM_PROBABILTY* parameter.</span></span>  
  
 <span data-ttu-id="5403d-106">*MINIMUM_PROBABILTY* — это [!INCLUDE[msCoName](../includes/msconame-md.md)] параметр алгоритма взаимосвязей, который помогает определить количество правил, которые будет содержать модель интеллектуального анализа данных, указав минимальную вероятность, которую должно иметь правило.</span><span class="sxs-lookup"><span data-stu-id="5403d-106">*MINIMUM_PROBABILTY* is a [!INCLUDE[msCoName](../includes/msconame-md.md)] Association algorithm parameter that helps to determine the number of rules that a mining model will contain by specifying the minimum probability that a rule must have.</span></span> <span data-ttu-id="5403d-107">Например, установка этого параметра в значение 0,4 означает, что правило может быть сформировано только в том случае, если вероятность появления сочетания продуктов, описанного в нем, равняется, по крайней мере, сорока процентам.</span><span class="sxs-lookup"><span data-stu-id="5403d-107">For example, setting this value to 0.4 specifies that a rule can be generated only if the combination of products that the rule describes has at least a forty percent probability of occurring.</span></span>  
  
 <span data-ttu-id="5403d-108">Результат изменения параметра *MINIMUM_PROBABILTY* будет представлен на следующем занятии.</span><span class="sxs-lookup"><span data-stu-id="5403d-108">You will view the effect of changing the *MINIMUM_PROBABILTY* parameter in a later lesson.</span></span>  
  
## <a name="alter-mining-structure-statement"></a><span data-ttu-id="5403d-109">Инструкция ALTER MINING STRUCTURE</span><span class="sxs-lookup"><span data-stu-id="5403d-109">ALTER MINING STRUCTURE Statement</span></span>  
 <span data-ttu-id="5403d-110">Для добавления модели интеллектуального анализа данных, содержащей вложенную таблицу, в структуру интеллектуального анализа данных используется инструкция [ALTER MINING structure &#40;DMX&#41;](/sql/dmx/alter-mining-structure-dmx?view=sql-server-2016) .</span><span class="sxs-lookup"><span data-stu-id="5403d-110">To add a mining model that contains a nested table to a mining structure, you use the [ALTER MINING STRUCTURE &#40;DMX&#41;](/sql/dmx/alter-mining-structure-dmx?view=sql-server-2016) statement.</span></span> <span data-ttu-id="5403d-111">Код инструкции можно разбить на следующие части:</span><span class="sxs-lookup"><span data-stu-id="5403d-111">The code in the statement can be broken into the following parts:</span></span>  
  
-   <span data-ttu-id="5403d-112">Определение структуры интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="5403d-112">Identifying the mining structure</span></span>  
  
-   <span data-ttu-id="5403d-113">Указание имени модели интеллектуального анализа</span><span class="sxs-lookup"><span data-stu-id="5403d-113">Naming the mining model</span></span>  
  
-   <span data-ttu-id="5403d-114">Определение ключевого столбца</span><span class="sxs-lookup"><span data-stu-id="5403d-114">Defining the key column</span></span>  
  
-   <span data-ttu-id="5403d-115">Определение столбцов исходных данных и прогнозируемых столбцов</span><span class="sxs-lookup"><span data-stu-id="5403d-115">Defining the input and predictable columns</span></span>  
  
-   <span data-ttu-id="5403d-116">Определение столбцов вложенных таблиц</span><span class="sxs-lookup"><span data-stu-id="5403d-116">Defining the nested table columns</span></span>  
  
-   <span data-ttu-id="5403d-117">Идентификация алгоритма и изменений параметра</span><span class="sxs-lookup"><span data-stu-id="5403d-117">Identifying the algorithm and parameter changes</span></span>  
  
 <span data-ttu-id="5403d-118">Далее приведен общий пример инструкции `ALTER MINING STRUCTURE`, добавляющей в структуру модель интеллектуального анализа данных, содержащую столбцы вложенной таблицы:</span><span class="sxs-lookup"><span data-stu-id="5403d-118">The following is a generic example of the `ALTER MINING STRUCTURE` statement that adds a mining model to a structure that includes nested table columns:</span></span>  
  
```  
ALTER MINING STRUCTURE [<Mining Structure Name>]  
ADD MINING MODEL [<Mining Model Name>]  
(  
    [<key column>],  
    <mining model column> <usage>,  
    <table columns>  
    (  [<nested key column>],  
       <nested mining model columns> )  
) USING <algorithm>( <algorithm parameters> )  
```  
  
 <span data-ttu-id="5403d-119">В первой строке кода идентифицируется существующая структура интеллектуального анализа данных, в которую будет добавлена модель интеллектуального анализа данных:</span><span class="sxs-lookup"><span data-stu-id="5403d-119">The first line of the code identifies the existing mining structure to which the mining model will be added:</span></span>  
  
```  
ALTER MINING STRUCTURE [<mining structure name>]  
```  
  
 <span data-ttu-id="5403d-120">В следующей строчке кода модели интеллектуального анализа данных, добавляемой к структуре интеллектуального анализа, присваивается имя:</span><span class="sxs-lookup"><span data-stu-id="5403d-120">The next line of the code names the mining model that will be added to the mining structure:</span></span>  
  
```  
ADD MINING MODEL [<mining model name>]  
```  
  
 <span data-ttu-id="5403d-121">Сведения об именовании объекта в расширениях интеллектуального анализа данных см. в разделе [идентификаторы &#40;dmx&#41;](/sql/dmx/identifiers-dmx).</span><span class="sxs-lookup"><span data-stu-id="5403d-121">For information about naming an object in Data Mining Extensions (DMX), see [Identifiers &#40;DMX&#41;](/sql/dmx/identifiers-dmx).</span></span>  
  
 <span data-ttu-id="5403d-122">Следующие строки кода задают столбцы из структуры интеллектуального анализа данных, которые будут использоваться моделью интеллектуального анализа данных:</span><span class="sxs-lookup"><span data-stu-id="5403d-122">The next lines of the code define the columns in the mining structure that will be used by the mining model:</span></span>  
  
```  
[<key column>],  
<mining model columns> <usage>,  
```  
  
 <span data-ttu-id="5403d-123">Можно использовать только столбцы, которые уже существуют в структуре интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="5403d-123">You can only use columns that already exist in the mining structure.</span></span>  
  
 <span data-ttu-id="5403d-124">Первым столбцом в списке столбцов модели интеллектуального анализа данных должен быть ключевой столбец структуры интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="5403d-124">The first column in the list of mining model columns must be the key column in the mining structure.</span></span> <span data-ttu-id="5403d-125">Однако для указания использования не нужно вводить данные `KEY` после ключевого столбца.</span><span class="sxs-lookup"><span data-stu-id="5403d-125">However, you do not have to type `KEY` after the key column to specify usage.</span></span> <span data-ttu-id="5403d-126">При создании структуры интеллектуального анализа данных этот столбец уже был определен как ключевой.</span><span class="sxs-lookup"><span data-stu-id="5403d-126">That is because you have already defined the column as a key when you created the mining structure.</span></span>  
  
 <span data-ttu-id="5403d-127">В остальных строках задается использование столбцов новой модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="5403d-127">The remaining lines specify the usage of the columns in the new mining model.</span></span> <span data-ttu-id="5403d-128">С помощью следующего синтаксиса можно указать столбец модели интеллектуального анализа, который следует использовать для прогнозирования:</span><span class="sxs-lookup"><span data-stu-id="5403d-128">You can specify that a column in the mining model will be used for prediction by using the following syntax:</span></span>  
  
```  
<column name> PREDICT,  
```  
  
 <span data-ttu-id="5403d-129">Если для столбца не было указано использование, то этот столбец можно не включать в структуру интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="5403d-129">If you do not specify usage, you do not have to include a data mining structure column in the list.</span></span> <span data-ttu-id="5403d-130">Все столбцы, которые используются в упоминаемой структуре интеллектуального анализа данных, автоматически доступны для использования в моделях интеллектуального анализа данных, основанных на этой структуре.</span><span class="sxs-lookup"><span data-stu-id="5403d-130">All columns that are used by the referenced data mining structure are automatically available for use by the mining models that are based on that structure.</span></span> <span data-ttu-id="5403d-131">Однако модель не будет использовать столбцы для обучения, если не было указано их использование.</span><span class="sxs-lookup"><span data-stu-id="5403d-131">However, the model will not use the columns for training unless you specify the usage.</span></span>  
  
 <span data-ttu-id="5403d-132">В последней строке фрагмента кода задается алгоритм и параметры алгоритма, используемые для формирования модели интеллектуального анализа.</span><span class="sxs-lookup"><span data-stu-id="5403d-132">The last line in the code defines the algorithm and algorithm parameters that will be used to generate the mining model.</span></span>  
  
```  
) USING <algorithm>( <algorithm parameters> )  
```  
  
## <a name="lesson-tasks"></a><span data-ttu-id="5403d-133">Задачи занятия</span><span class="sxs-lookup"><span data-stu-id="5403d-133">Lesson Tasks</span></span>  
 <span data-ttu-id="5403d-134">На этом занятии будут выполнены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="5403d-134">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="5403d-135">Добавление в структуру ассоциативной модели интеллектуального анализа данных, используя вероятность по умолчанию</span><span class="sxs-lookup"><span data-stu-id="5403d-135">Add an association mining model to the structure using the default probability</span></span>  
  
-   <span data-ttu-id="5403d-136">Добавление в структуру ассоциативной модели интеллектуального анализа данных, используя измененную вероятность</span><span class="sxs-lookup"><span data-stu-id="5403d-136">Add an association mining model to the structure using a modified probability</span></span>  
  
## <a name="adding-an-association-mining-model-to-the-structure-using-the-default-minimum_probability"></a><span data-ttu-id="5403d-137">Добавление модели интеллектуального анализа взаимосвязей к структуре с помощью параметра по умолчанию MINIMUM_PROBABILTY</span><span class="sxs-lookup"><span data-stu-id="5403d-137">Adding an Association Mining Model to the Structure Using the Default MINIMUM_PROBABILITY</span></span>  
 <span data-ttu-id="5403d-138">Первая задача — добавить новую модель интеллектуального анализа данных в структуру интеллектуального анализа данных «Потребительская корзина» на основе [!INCLUDE[msCoName](../includes/msconame-md.md)] алгоритма взаимосвязей, используя значение по умолчанию для *MINIMUM_PROBABILITY*.</span><span class="sxs-lookup"><span data-stu-id="5403d-138">The first task is to add a new mining model to the Market Basket mining structure based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Association algorithm using the default value for *MINIMUM_PROBABILITY*.</span></span>  
  
#### <a name="to-add-an-association-mining-model"></a><span data-ttu-id="5403d-139">Добавление ассоциативной модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="5403d-139">To add an Association mining model</span></span>  
  
1.  <span data-ttu-id="5403d-140">В окне **Обозреватель объектов**щелкните правой кнопкой мыши экземпляр служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], укажите **Создать запрос**, а затем выберите пункт **Расширения интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="5403d-140">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="5403d-141">Откроется редактор запросов, содержащий новый, пустой запрос.</span><span class="sxs-lookup"><span data-stu-id="5403d-141">Query Editor opens and contains a new, blank query.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5403d-142">Чтобы создать запрос расширений интеллектуального анализа данных к определенной базе данных служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], щелкните правой кнопкой мыши базу данных, а не экземпляр.</span><span class="sxs-lookup"><span data-stu-id="5403d-142">To create a DMX query against a specific [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database, right-click the database instead of the instance.</span></span>  
  
2.  <span data-ttu-id="5403d-143">Скопируйте общий пример инструкции `ALTER MINING STRUCTURE` в пустой запрос.</span><span class="sxs-lookup"><span data-stu-id="5403d-143">Copy the generic example of the `ALTER MINING STRUCTURE` statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="5403d-144">Вместо</span><span class="sxs-lookup"><span data-stu-id="5403d-144">Replace the following:</span></span>  
  
    ```  
    <mining structure name>   
    ```  
  
     <span data-ttu-id="5403d-145">на:</span><span class="sxs-lookup"><span data-stu-id="5403d-145">with:</span></span>  
  
    ```  
    [Market Basket]  
    ```  
  
4.  <span data-ttu-id="5403d-146">Вместо</span><span class="sxs-lookup"><span data-stu-id="5403d-146">Replace the following:</span></span>  
  
    ```  
    <mining model name>   
    ```  
  
     <span data-ttu-id="5403d-147">на:</span><span class="sxs-lookup"><span data-stu-id="5403d-147">with:</span></span>  
  
    ```  
    [Default Association]  
    ```  
  
5.  <span data-ttu-id="5403d-148">Вместо</span><span class="sxs-lookup"><span data-stu-id="5403d-148">Replace the following:</span></span>  
  
    ```  
    [<key column>],  
    <mining model columns>,  
    <table columns>  
    (  [<nested key column>],  
       <nested mining model columns> )  
    ```  
  
     <span data-ttu-id="5403d-149">на:</span><span class="sxs-lookup"><span data-stu-id="5403d-149">with:</span></span>  
  
    ```  
    OrderNumber,  
        [Products] PREDICT (  
            [Model]  
        )  
    ```  
  
     <span data-ttu-id="5403d-150">В этом случае в качестве прогнозируемого столбца была назначен столбец таблицы `[Products]``.` Кроме того, в список столбцов вложенной таблицы был добавлен столбец `[Model]`, поскольку он является ключевым столбцом вложенной таблицы.</span><span class="sxs-lookup"><span data-stu-id="5403d-150">In this case, the `[Products]` table has been designated as the predictable column`.` Also, the `[Model]` column is included in the list of nested table columns because it is the key column of the nested table.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5403d-151">Помните, что ключ вложенной таблицы отличается от ключа варианта.</span><span class="sxs-lookup"><span data-stu-id="5403d-151">Remember that a nested key is different from a case key.</span></span> <span data-ttu-id="5403d-152">Ключ варианта — это уникальный идентификатор варианта, а ключ вложенной таблицы — атрибут, подлежащий моделированию.</span><span class="sxs-lookup"><span data-stu-id="5403d-152">A case key is a unique identifier of the case, whereas the nested key is an attribute that you want to model.</span></span>  
  
6.  <span data-ttu-id="5403d-153">Вместо</span><span class="sxs-lookup"><span data-stu-id="5403d-153">Replace the following:</span></span>  
  
    ```  
    USING <algorithm>( <algorithm parameters> )  
    ```  
  
     <span data-ttu-id="5403d-154">на:</span><span class="sxs-lookup"><span data-stu-id="5403d-154">with:</span></span>  
  
    ```  
    Using Microsoft_Association_Rules  
    ```  
  
     <span data-ttu-id="5403d-155">В результате инструкция должна выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="5403d-155">The resulting statement should now be as follows:</span></span>  
  
    ```  
    ALTER MINING STRUCTURE [Market Basket]  
    ADD MINING MODEL [Default Association]  
    (  
        OrderNumber,  
        [Products] PREDICT (  
            [Model]  
        )  
    )  
    Using Microsoft_Association_Rules  
    ```  
  
7.  <span data-ttu-id="5403d-156">В меню **Файл** щелкните **Сохранить DMXQuery1.dmx как**.</span><span class="sxs-lookup"><span data-stu-id="5403d-156">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
8.  <span data-ttu-id="5403d-157">В диалоговом окне **Сохранить как** перейдите в соответствующую папку и присвойте файлу имя `Default_Association_Model.dmx` .</span><span class="sxs-lookup"><span data-stu-id="5403d-157">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Default_Association_Model.dmx`.</span></span>  
  
9. <span data-ttu-id="5403d-158">На панели инструментов нажмите кнопку **Выполнить** .</span><span class="sxs-lookup"><span data-stu-id="5403d-158">On the toolbar, click the **Execute** button.</span></span>  
  
## <a name="adding-an-association-mining-model-to-the-structure-changing-the-default-minimum_probability"></a><span data-ttu-id="5403d-159">Добавление модели интеллектуального анализа взаимосвязей к структуре путем изменения параметра MINIMUM_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="5403d-159">Adding an Association Mining Model to the Structure Changing the Default MINIMUM_PROBABILITY</span></span>  
 <span data-ttu-id="5403d-160">Следующей задачей является добавление новой модели интеллектуального анализа данных в структуру интеллектуального анализа данных «Потребительская корзина» на основе [!INCLUDE[msCoName](../includes/msconame-md.md)] алгоритма взаимосвязей и изменение значения по умолчанию для MINIMUM_PROBABILITY на 0,01.</span><span class="sxs-lookup"><span data-stu-id="5403d-160">The next task is to add a new mining model to the Market Basket mining structure based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Association algorithm, and change the default value for MINIMUM_PROBABILITY to 0.01.</span></span> <span data-ttu-id="5403d-161">Изменение параметра приведет к тому, что [!INCLUDE[msCoName](../includes/msconame-md.md)] алгоритм взаимосвязей создаст больше правил.</span><span class="sxs-lookup"><span data-stu-id="5403d-161">Changing the parameter will cause the [!INCLUDE[msCoName](../includes/msconame-md.md)] Association algorithm to create more rules.</span></span>  
  
#### <a name="to-add-an-association-mining-model"></a><span data-ttu-id="5403d-162">Добавление ассоциативной модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="5403d-162">To add an Association mining model</span></span>  
  
1.  <span data-ttu-id="5403d-163">В окне **Обозреватель объектов**щелкните правой кнопкой мыши экземпляр служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], укажите **Создать запрос**, а затем выберите пункт **Расширения интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="5403d-163">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="5403d-164">Откроется редактор запросов, содержащий новый, пустой запрос.</span><span class="sxs-lookup"><span data-stu-id="5403d-164">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="5403d-165">Скопируйте общий пример инструкции `ALTER MINING STRUCTURE` в пустой запрос.</span><span class="sxs-lookup"><span data-stu-id="5403d-165">Copy the generic example of the `ALTER MINING STRUCTURE` statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="5403d-166">Вместо</span><span class="sxs-lookup"><span data-stu-id="5403d-166">Replace the following:</span></span>  
  
    ```  
    <mining structure name>   
    ```  
  
     <span data-ttu-id="5403d-167">на:</span><span class="sxs-lookup"><span data-stu-id="5403d-167">with:</span></span>  
  
    ```  
    Market Basket  
    ```  
  
4.  <span data-ttu-id="5403d-168">Вместо</span><span class="sxs-lookup"><span data-stu-id="5403d-168">Replace the following:</span></span>  
  
    ```  
    <mining model name>   
    ```  
  
     <span data-ttu-id="5403d-169">на:</span><span class="sxs-lookup"><span data-stu-id="5403d-169">with:</span></span>  
  
    ```  
    [Modified Association]  
    ```  
  
5.  <span data-ttu-id="5403d-170">Вместо</span><span class="sxs-lookup"><span data-stu-id="5403d-170">Replace the following:</span></span>  
  
    ```  
    <mining model columns>,  
    <table columns>  
    (  [<nested key column>],  
       <nested mining model columns> )  
    ```  
  
     <span data-ttu-id="5403d-171">на:</span><span class="sxs-lookup"><span data-stu-id="5403d-171">with:</span></span>  
  
    ```  
    OrderNumber,  
    [Products] PREDICT (  
            [Model]  
        )  
    ```  
  
     <span data-ttu-id="5403d-172">В этом случае таблица `[Products]` обозначается как прогнозируемый столбец.</span><span class="sxs-lookup"><span data-stu-id="5403d-172">In this case, the `[Products]` table has been designated as the predictable column.</span></span> <span data-ttu-id="5403d-173">Столбец `[MODEL]` также включается в список, поскольку он является ключевым столбцом во вложенной таблице.</span><span class="sxs-lookup"><span data-stu-id="5403d-173">Also, the `[MODEL]` column is included in the list because it is the key column in the nested table.</span></span>  
  
6.  <span data-ttu-id="5403d-174">Вместо</span><span class="sxs-lookup"><span data-stu-id="5403d-174">Replace the following:</span></span>  
  
    ```  
    USING <algorithm>( <algorithm parameters> )  
    ```  
  
     <span data-ttu-id="5403d-175">на:</span><span class="sxs-lookup"><span data-stu-id="5403d-175">with:</span></span>  
  
    ```  
    USING Microsoft_Association_Rules (Minimum_Probability = 0.1)  
    ```  
  
     <span data-ttu-id="5403d-176">В результате инструкция должна выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="5403d-176">The resulting statement should now be as follows:</span></span>  
  
    ```  
    ALTER MINING STRUCTURE [Market Basket]  
    ADD MINING MODEL [Modified Assocation]  
    (  
        OrderNumber,  
        [Products] PREDICT (  
            [Model]  
        )  
    )  
    USING Microsoft_Association_Rules (Minimum_Probability = 0.1)  
    ```  
  
7.  <span data-ttu-id="5403d-177">В меню **Файл** щелкните **Сохранить DMXQuery1.dmx как**.</span><span class="sxs-lookup"><span data-stu-id="5403d-177">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
8.  <span data-ttu-id="5403d-178">В диалоговом окне **Сохранить как** перейдите в соответствующую папку и присвойте файлу имя `Modified Association_Model.dmx` .</span><span class="sxs-lookup"><span data-stu-id="5403d-178">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Modified Association_Model.dmx`.</span></span>  
  
9. <span data-ttu-id="5403d-179">На панели инструментов нажмите кнопку **Выполнить** .</span><span class="sxs-lookup"><span data-stu-id="5403d-179">On the toolbar, click the **Execute** button.</span></span>  
  
 <span data-ttu-id="5403d-180">На следующем занятии требуется обработать структуру интеллектуального анализа данных «Потребительская корзина» и связанные с ней модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="5403d-180">In this next lesson you will process the Market Basket mining structure together with its associated mining models.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="5403d-181">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="5403d-181">Next Lesson</span></span>  
 [<span data-ttu-id="5403d-182">Урок 3. Обработка структуры интеллектуального анализа данных «Потребительская корзина»</span><span class="sxs-lookup"><span data-stu-id="5403d-182">Lesson 3: Processing the Market Basket Mining Structure</span></span>](../../2014/tutorials/lesson-3-processing-the-market-basket-mining-structure.md)  
  
  
