---
title: Занятие 3. Обработка структуры интеллектуального анализа данных для потребительской корзины | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 095a043f-cf6f-45bb-a021-ae4e1b535c65
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: ce2c2e6944d524a38edc331d2cd128ca7cf7d419
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727518"
---
# <a name="lesson-3-processing-the-market-basket-mining-structure"></a><span data-ttu-id="45263-102">Урок 3. Обработка структуры интеллектуального анализа данных «Потребительская корзина»</span><span class="sxs-lookup"><span data-stu-id="45263-102">Lesson 3: Processing the Market Basket Mining Structure</span></span>
  <span data-ttu-id="45263-103">На этом занятии для обработки структур и моделей интеллектуального анализа данных, созданных на занятии 1, вы будете использовать инструкцию [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) , а также VAssocSeqLineItems и vAssocSeqOrders в образце базы. для этого нужно создать структуру интеллектуального анализа данных [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] для [рынка](../../2014/tutorials/lesson-1-creating-the-market-basket-mining-structure.md) и [занятие 2: Добавление моделей интеллектуального анализа данных в структуру интеллектуального анализа данных для рынка](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="45263-103">In this lesson, you will use the [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) statement and the vAssocSeqLineItems and vAssocSeqOrders from the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] sample database to process the mining structures and mining models that you created in [Lesson 1: Creating the Market Basket Mining Structure](../../2014/tutorials/lesson-1-creating-the-market-basket-mining-structure.md) and [Lesson 2: Adding Mining Models to the Market Basket Mining Structure](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md).</span></span>  
  
 <span data-ttu-id="45263-104">При обработке структуры интеллектуального анализа данных службы [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] считывают исходные данные и создают структуры, поддерживающие модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="45263-104">When you process a mining structure, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] reads the source data and builds the structures that support mining models.</span></span> <span data-ttu-id="45263-105">При обработке модели интеллектуального анализа данных, данные, определенные структурой интеллектуального анализа данных, обрабатываются выбранным алгоритмом интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="45263-105">When you process a mining model, the data defined by the mining structure is passed through the data mining algorithm that you chose.</span></span> <span data-ttu-id="45263-106">Алгоритм находит тренды и шаблоны и сохраняет эти данные в модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="45263-106">The algorithm searches for trends and patterns, and then stores this information in the mining model.</span></span> <span data-ttu-id="45263-107">Поэтому в модели интеллектуального анализа данных содержатся не фактические исходные данные, а данные, выявленные алгоритмом.</span><span class="sxs-lookup"><span data-stu-id="45263-107">The mining model, therefore, does not contain the actual source data, but instead contains the information that was discovered by the algorithm.</span></span> <span data-ttu-id="45263-108">Дополнительные сведения об обработке моделей интеллектуального анализа данных см. в разделе [требования к обработке и рекомендации &#40;&#41;интеллектуального анализа ](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="45263-108">For more information about processing mining models, see [Processing Requirements and Considerations &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md).</span></span>  
  
 <span data-ttu-id="45263-109">Повторная обработка структуры интеллектуального анализа данных нужна только в случае, когда изменяются столбцы структуры или исходные данные.</span><span class="sxs-lookup"><span data-stu-id="45263-109">You only have to reprocess a mining structure if you change a structure column or change the source data.</span></span> <span data-ttu-id="45263-110">При добавлении модели интеллектуального анализа данных к уже обработанной структуре интеллектуального анализа данных, можно использовать инструкцию `INSERT INTO MINING MODEL` для обучения новой модели интеллектуального анализа данных с помощью существующих данных.</span><span class="sxs-lookup"><span data-stu-id="45263-110">If you add a mining model to a mining structure that has already been processed, you can use the `INSERT INTO MINING MODEL` statement to train the new mining model on the existing data.</span></span>  
  
 <span data-ttu-id="45263-111">Так как структура интеллектуального анализа данных «Потребительская корзина» содержит вложенную таблицу, потребуется определить столбцы интеллектуального анализа данных, которые нужно обучить с помощью структуры этой таблицы, и использовать команду `SHAPE`, чтобы определить запросы, которые получат обучающие данные из исходных таблиц.</span><span class="sxs-lookup"><span data-stu-id="45263-111">Because the Market Basket mining structure contains a nested table, you will have to define the mining columns to be trained using the nested table structure, and use the `SHAPE` command to define the queries that pull the training data from the source tables.</span></span>  
  
## <a name="insert-into-statement"></a><span data-ttu-id="45263-112">Инструкция INSERT INTO</span><span class="sxs-lookup"><span data-stu-id="45263-112">INSERT INTO Statement</span></span>  
 <span data-ttu-id="45263-113">Чтобы обучить структуру интеллектуального анализа данных «Потребительская корзина» и связанные с ней модели интеллектуального анализа данных, используйте инструкцию [INSERT в &#40;DMX&#41;](/sql/dmx/insert-into-dmx) .</span><span class="sxs-lookup"><span data-stu-id="45263-113">In order to train the Market Basket mining structure and its associated mining models, use the [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) statement.</span></span> <span data-ttu-id="45263-114">Код инструкции можно разбить на следующие части.</span><span class="sxs-lookup"><span data-stu-id="45263-114">The code in the statement can be broken into the following parts.</span></span>  
  
-   <span data-ttu-id="45263-115">Определение структуры интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="45263-115">Identifying the mining structure</span></span>  
  
-   <span data-ttu-id="45263-116">Список столбцов структуры интеллектуального анализа</span><span class="sxs-lookup"><span data-stu-id="45263-116">Listing the columns in the mining structure</span></span>  
  
-   <span data-ttu-id="45263-117">Определение обучающих данных с помощью инструкции `SHAPE`</span><span class="sxs-lookup"><span data-stu-id="45263-117">Defining the training data using `SHAPE`</span></span>  
  
 <span data-ttu-id="45263-118">Далее приведен общий пример инструкции `INSERT INTO`:</span><span class="sxs-lookup"><span data-stu-id="45263-118">The following is a generic example of the `INSERT INTO` statement:</span></span>  
  
```  
INSERT INTO MINING STRUCTURE [<mining structure name>]  
(  
   <mining structure columns>  
   [<nested table>]  
   ( SKIP, <skipped column> )  
)  
SHAPE {  
  OPENQUERY([<datasource>],'<SELECT statement>') }  
APPEND  
(   
  {OPENQUERY([<datasource>],'<nested SELECT statement>')  
}  
RELATE [<case key>] TO [<foreign key>]  
) AS [<nested table>]  
```  
  
 <span data-ttu-id="45263-119">В первой строчке кода задается структура интеллектуального анализа данных, которую необходимо обучить:</span><span class="sxs-lookup"><span data-stu-id="45263-119">The first line of the code identifies the mining structure that you will train:</span></span>  
  
```  
INSERT INTO MINING STRUCTURE [<mining structure name>]  
```  
  
 <span data-ttu-id="45263-120">Следующие строки кода указывают столбцы, определенные структурой интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="45263-120">The next lines of the code specify the columns that are defined by the mining structure.</span></span> <span data-ttu-id="45263-121">Необходимо перечислить все столбцы структуры интеллектуального анализа данных, и каждый столбец должен сопоставляться с каким-либо столбцом из данных исходного запроса.</span><span class="sxs-lookup"><span data-stu-id="45263-121">You must list each column in the mining structure, and each column must map to a column contained within the source query data.</span></span> <span data-ttu-id="45263-122">Можно использовать инструкцию `SKIP`, чтобы не обрабатывать столбцы, существующие в исходных данных, но не в структуре интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="45263-122">You can use `SKIP` to ignore columns that exist in the source data but do not exist in the mining structure.</span></span> <span data-ttu-id="45263-123">Дополнительные сведения об использовании `SKIP` см. [в разделе вставка в &#40;DMX&#41;](/sql/dmx/insert-into-dmx).</span><span class="sxs-lookup"><span data-stu-id="45263-123">For more information about how to use `SKIP`, see [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx).</span></span>  
  
```  
(  
   <mining structure columns>  
   [<nested table>]  
   ( SKIP, <skipped column> )  
)  
```  
  
 <span data-ttu-id="45263-124">Последние строки кода определяют данные, которые будут использованы для обучения структуры интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="45263-124">The final lines of the code define the data that will be used to train the mining structure.</span></span> <span data-ttu-id="45263-125">Так как исходные данные содержатся в двух таблицах, для их связывания будет использована инструкция `SHAPE`.</span><span class="sxs-lookup"><span data-stu-id="45263-125">Because the source data is contained within two tables, you will use `SHAPE` to relate the tables.</span></span>  
  
```  
SHAPE {  
  OPENQUERY([<datasource>],'<SELECT statement>') }  
APPEND  
(   
  {OPENQUERY([<datasource>],''<nested SELECT statement>'')  
}  
RELATE [<case key>] TO [<foreign key>]  
) AS [<nested table>]  
```  
  
 <span data-ttu-id="45263-126">На этом занятии требуется определить исходные данные с помощью инструкции `OPENQUERY`.</span><span class="sxs-lookup"><span data-stu-id="45263-126">In this lesson, you use `OPENQUERY` to define the source data.</span></span> <span data-ttu-id="45263-127">Дополнительные сведения о других методах определения запроса к исходным данным см. в разделе [&#60;Source Data query&#62;](/sql/dmx/source-data-query).</span><span class="sxs-lookup"><span data-stu-id="45263-127">For information about other methods of defining a query on the source data, see [&#60;source data query&#62;](/sql/dmx/source-data-query).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="45263-128">Задачи занятия</span><span class="sxs-lookup"><span data-stu-id="45263-128">Lesson Tasks</span></span>  
 <span data-ttu-id="45263-129">На этом занятии требуется выполнить следующую задачу:</span><span class="sxs-lookup"><span data-stu-id="45263-129">You will perform the following task in this lesson:</span></span>  
  
-   <span data-ttu-id="45263-130">Обработка структуры интеллектуального анализа данных «Потребительская корзина»</span><span class="sxs-lookup"><span data-stu-id="45263-130">Process the Market Basket mining structure</span></span>  
  
## <a name="processing-the-market-basket-mining-structure"></a><span data-ttu-id="45263-131">Обработка структуры интеллектуального анализа данных «Потребительская корзина»</span><span class="sxs-lookup"><span data-stu-id="45263-131">Processing the Market Basket Mining Structure</span></span>  
  
#### <a name="to-process-the-mining-structure-by-using-insert-into"></a><span data-ttu-id="45263-132">Обработка структуры интеллектуального анализа данных с помощью инструкции INSERT INTO</span><span class="sxs-lookup"><span data-stu-id="45263-132">To process the mining structure by using INSERT INTO</span></span>  
  
1.  <span data-ttu-id="45263-133">В окне **Обозреватель объектов**щелкните правой кнопкой мыши экземпляр служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], укажите **Создать запрос**, а затем выберите пункт **Расширения интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="45263-133">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="45263-134">Откроется редактор запросов, содержащий новый, пустой запрос.</span><span class="sxs-lookup"><span data-stu-id="45263-134">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="45263-135">Скопируйте стандартный пример использования инструкции INSERT INTO в пустое окно запроса.</span><span class="sxs-lookup"><span data-stu-id="45263-135">Copy the generic example of the INSERT INTO statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="45263-136">Вместо</span><span class="sxs-lookup"><span data-stu-id="45263-136">Replace the following:</span></span>  
  
    ```  
    [<mining structure>]  
    ```  
  
     <span data-ttu-id="45263-137">на:</span><span class="sxs-lookup"><span data-stu-id="45263-137">with:</span></span>  
  
    ```  
    Market Basket  
    ```  
  
4.  <span data-ttu-id="45263-138">Вместо</span><span class="sxs-lookup"><span data-stu-id="45263-138">Replace the following:</span></span>  
  
    ```  
    <mining structure columns>  
    [<nested table>]  
    ( SKIP, <skipped column> )  
    ```  
  
     <span data-ttu-id="45263-139">на:</span><span class="sxs-lookup"><span data-stu-id="45263-139">with:</span></span>  
  
    ```  
    [OrderNumber],  
    [Products]   
    (SKIP, [Model])  
    ```  
  
     <span data-ttu-id="45263-140">В инструкции параметр `Products` относится к таблице продуктов, определенной инструкцией SHAPE.</span><span class="sxs-lookup"><span data-stu-id="45263-140">In the statement, `Products` refers to the Products table defined by the SHAPE statement.</span></span> <span data-ttu-id="45263-141">Столбец `SKIP` используется для пропуска столбца «Model», который существует в исходных данных в качестве ключа, но не используется структурой интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="45263-141">`SKIP` is used to ignore the Model column, which exists in the source data as a key, but is not used by the mining structure.</span></span>  
  
5.  <span data-ttu-id="45263-142">Вместо</span><span class="sxs-lookup"><span data-stu-id="45263-142">Replace the following:</span></span>  
  
    ```  
    SHAPE {  
      OPENQUERY([<datasource>],'<SELECT statement>') }  
    APPEND  
    (   
      {OPENQUERY([<datasource>],'<nested SELECT statement>')  
    }  
    RELATE [<case key>] TO [<foreign key>]  
    ) AS [<nested table>]  
    ```  
  
     <span data-ttu-id="45263-143">на:</span><span class="sxs-lookup"><span data-stu-id="45263-143">with:</span></span>  
  
    ```  
    SHAPE {  
      OPENQUERY([Adventure Works DW],'SELECT OrderNumber  
                FROM vAssocSeqOrders ORDER BY OrderNumber')}  
    APPEND  
    (   
      {OPENQUERY([Adventure Works DW],'SELECT OrderNumber, Model FROM   
        dbo.vAssocSeqLineItems ORDER BY OrderNumber, Model')  
    }  
    RELATE OrderNumber to OrderNumber   
    ) AS [Products]  
    ```  
  
     <span data-ttu-id="45263-144">Исходный запрос ссылается на [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] источник данных, определенный в [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] образце проекта.</span><span class="sxs-lookup"><span data-stu-id="45263-144">The source query references the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] data source defined in the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] sample project.</span></span> <span data-ttu-id="45263-145">Он использует этот источник данных для доступа к представлениям vAssocSeqLineItems и vAssocSeqOrders.</span><span class="sxs-lookup"><span data-stu-id="45263-145">It uses this data source to access the vAssocSeqLineItems and vAssocSeqOrders views.</span></span> <span data-ttu-id="45263-146">Эти представления содержат исходные данные, которые будут использованы для обучения модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="45263-146">These views contain the source data that will be used to train the mining model.</span></span> <span data-ttu-id="45263-147">Если вы не создали этот проект или эти представления, см. [учебник по основам интеллектуального анализа данных](../../2014/tutorials/basic-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="45263-147">If you have not created this project or these views, see [Basic Data Mining Tutorial](../../2014/tutorials/basic-data-mining-tutorial.md).</span></span>  
  
     <span data-ttu-id="45263-148">Внутри команды `SHAPE` будет использоваться предложение `OPENQUERY` для определения двух запросов.</span><span class="sxs-lookup"><span data-stu-id="45263-148">Within the `SHAPE` command, you will use `OPENQUERY` to define two queries.</span></span> <span data-ttu-id="45263-149">Первый запрос определяет родительскую таблицу, второй — вложенную.</span><span class="sxs-lookup"><span data-stu-id="45263-149">The first query defines the parent table, and the second query defines the nested table.</span></span> <span data-ttu-id="45263-150">Две таблицы связаны с помощью столбца OrderNumber, который присутствует в обеих таблицах.</span><span class="sxs-lookup"><span data-stu-id="45263-150">The two tables are related using the OrderNumber column, which exists in both tables.</span></span>  
  
     <span data-ttu-id="45263-151">Полная инструкция теперь должна выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="45263-151">The complete statement should now be as follows:</span></span>  
  
    ```  
    INSERT INTO MINING STRUCTURE [Market Basket]  
    (  
       [OrderNumber],[Products] (SKIP, [Model])  
    )  
    SHAPE {  
      OPENQUERY([Adventure Works DW],'SELECT OrderNumber  
                FROM vAssocSeqOrders ORDER BY OrderNumber')}  
    APPEND  
    (   
      {OPENQUERY([Adventure Works DW],'SELECT OrderNumber, Model FROM   
        dbo.vAssocSeqLineItems ORDER BY OrderNumber, Model')  
    }  
    RELATE OrderNumber to OrderNumber   
    ) AS [Products]  
    ```  
  
6.  <span data-ttu-id="45263-152">В меню **Файл** щелкните **Сохранить DMXQuery1.dmx как**.</span><span class="sxs-lookup"><span data-stu-id="45263-152">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="45263-153">В диалоговом окне **Сохранить как** перейдите в соответствующую папку и присвойте файлу имя `Process Market Basket.dmx` .</span><span class="sxs-lookup"><span data-stu-id="45263-153">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Process Market Basket.dmx`.</span></span>  
  
8.  <span data-ttu-id="45263-154">На панели инструментов нажмите кнопку **Выполнить** .</span><span class="sxs-lookup"><span data-stu-id="45263-154">On the toolbar, click the **Execute** button.</span></span>  
  
 <span data-ttu-id="45263-155">После завершения выполнения запроса можно просмотреть найденные закономерности и наборы элементов, просмотреть взаимосвязи или фильтровать результаты в зависимости от набора элементов, вероятности или важности.</span><span class="sxs-lookup"><span data-stu-id="45263-155">After the query has finished running, you can view the patterns and itemsets that were found, view associations, or filter by itemset, probability, or importance.</span></span> <span data-ttu-id="45263-156">Чтобы просмотреть эти сведения, в щелкните [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] правой кнопкой мыши имя модели данных, а затем нажмите кнопку **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="45263-156">To view this information, in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], right-click the name of the data model, and then click **Browse**.</span></span>  
  
 <span data-ttu-id="45263-157">В следующем занятии будут созданы несколько прогнозов, основанных на моделях интеллектуального анализа данных, которые были добавлены в структуру «Потребительская корзина».</span><span class="sxs-lookup"><span data-stu-id="45263-157">In the next lesson, you will create several predictions based on the mining models that you added to the Market Basket structure.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="45263-158">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="45263-158">Next Lesson</span></span>  
 [<span data-ttu-id="45263-159">Занятие 4: Прогнозирование покупательского поведения</span><span class="sxs-lookup"><span data-stu-id="45263-159">Lesson 4: Executing Market Basket Predictions</span></span>](../../2014/tutorials/lesson-4-executing-market-basket-predictions.md)  
  
  
