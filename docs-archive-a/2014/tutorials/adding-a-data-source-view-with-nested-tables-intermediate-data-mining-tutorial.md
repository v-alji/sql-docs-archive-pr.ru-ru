---
title: Добавление представления источников данных с вложенными таблицами (учебник по интеллектуальному анализу данных — средний уровень) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a14cd7f1-7a10-4ec6-af6a-f5f0676a0308
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: da1a9bff093e0b59e9d1166554d95bcf61aded08
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735674"
---
# <a name="adding-a-data-source-view-with-nested-tables-intermediate-data-mining-tutorial"></a><span data-ttu-id="ddd70-102">Добавление представления источников данных с вложенными таблицами (учебник по интеллектуальному анализу данных — средний уровень)</span><span class="sxs-lookup"><span data-stu-id="ddd70-102">Adding a Data Source View with Nested Tables (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="ddd70-103">Для создания модели потребительской корзины необходимо использовать представление источника данных, поддерживающее ассоциативных данные.</span><span class="sxs-lookup"><span data-stu-id="ddd70-103">To create a market basket model, you must use a data source view that supports associative data.</span></span> <span data-ttu-id="ddd70-104">Это представление также будет использоваться в сценарии кластеризации последовательностей.</span><span class="sxs-lookup"><span data-stu-id="ddd70-104">This data source view will also be used for the sequence clustering scenario.</span></span>  
  
 <span data-ttu-id="ddd70-105">Это представление источника данных отличается от других, с которыми вы могли работать, так как содержит *вложенную таблицу*.</span><span class="sxs-lookup"><span data-stu-id="ddd70-105">This data source view is different from others that you may have worked with because it contains a *nested table*.</span></span> <span data-ttu-id="ddd70-106">*Вложенная таблица* содержит несколько строк сведений о одной строке в таблице вариантов.</span><span class="sxs-lookup"><span data-stu-id="ddd70-106">A *nested table* is a table that contains multiple rows of information about a single row in the case table.</span></span> <span data-ttu-id="ddd70-107">Например, если модель анализирует поведение клиентов в процессе покупки, обычно в качестве таблицы вариантов используется таблица, содержащая уникальную строку для каждого клиента.</span><span class="sxs-lookup"><span data-stu-id="ddd70-107">For example, if your model analyzes the purchasing behavior of customers, you would typically use a table that has a unique row for each customer as the case table.</span></span> <span data-ttu-id="ddd70-108">Однако каждый клиент может выполнить несколько покупок, и может понадобиться проанализировать последовательность покупок или продукты, часто приобретаемые совместно.</span><span class="sxs-lookup"><span data-stu-id="ddd70-108">However, each customer might make multiple purchases, and you might want to analyze the sequence of purchases, or products that are frequently purchased together.</span></span> <span data-ttu-id="ddd70-109">Для логического представления данных покупок в модели необходимо добавить в представление источника данных еще одну таблицу, в которой будут перечисляться покупки каждого клиента.</span><span class="sxs-lookup"><span data-stu-id="ddd70-109">To logically represent these purchases in your model, you add another table to the data source view that lists the purchases for each customer.</span></span>  
  
 <span data-ttu-id="ddd70-110">Вложенная таблица покупок связана с таблицей клиентов связью «многие к одному».</span><span class="sxs-lookup"><span data-stu-id="ddd70-110">This nested purchases table is related to the customer table by a many-to-one relationship.</span></span> <span data-ttu-id="ddd70-111">Вложенная таблица может содержать множество строк для каждого клиента, а каждая строка содержит один купленный продукт, иногда с дополнительными сведениями о заказах, на основании которых были сделаны покупки, о цене на момент заказа или любых действовавших акциях.</span><span class="sxs-lookup"><span data-stu-id="ddd70-111">The nested table might contain many rows for each customer, each row containing a single product that was purchased, perhaps with additional information about the order that the purchases were made, the price at the time of the order, or any promotions that applied.</span></span> <span data-ttu-id="ddd70-112">Сведения вложенной таблицы можно использовать в качестве входных данных для модели или прогнозируемого атрибута.</span><span class="sxs-lookup"><span data-stu-id="ddd70-112">You can use the information in the nested table as inputs to the model, or as the predictable attribute.</span></span>  
  
 <span data-ttu-id="ddd70-113">На этом занятии будут выполнены следующие действия.</span><span class="sxs-lookup"><span data-stu-id="ddd70-113">In this lesson, you do the following tasks:</span></span>  
  
-   <span data-ttu-id="ddd70-114">В источник данных добавляется представление источника данных [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ddd70-114">You add a data source view to the [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] data source.</span></span>  
  
-   <span data-ttu-id="ddd70-115">В данное представление будут добавлены таблица вариантов и вложенные таблицы.</span><span class="sxs-lookup"><span data-stu-id="ddd70-115">You add the case and nested tables to this view.</span></span>  
  
-   <span data-ttu-id="ddd70-116">Будет задана связь «многие к одному» между таблицей вариантов и вложенной таблицей.</span><span class="sxs-lookup"><span data-stu-id="ddd70-116">You specify the many-to-one relationship between the case and nested table.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ddd70-117">.</span><span class="sxs-lookup"><span data-stu-id="ddd70-117">.</span></span> <span data-ttu-id="ddd70-118">Очень важно точно следовать описанной процедуре и правильно задать связь между таблицей вариантов и вложенной таблицей, иначе при попытке обработки модели могут появиться ошибки.</span><span class="sxs-lookup"><span data-stu-id="ddd70-118">It is important that you follow the described procedure exactly, to correctly specify the relationship between the case table and the nested table and to avoid errors when you process the model.</span></span>  
  
-   <span data-ttu-id="ddd70-119">Затем задается способ использования столбцов данных в модели.</span><span class="sxs-lookup"><span data-stu-id="ddd70-119">You define how the columns of data are used in the model.</span></span>  
  
 <span data-ttu-id="ddd70-120">Дополнительные сведения о работе с вариантами и вложенными таблицами, а также о выборе ключа вложенной таблицы см. в разделе [вложенные таблицы &#40;Analysis Services-&#41;интеллектуального анализа данных ](../../2014/analysis-services/data-mining/nested-tables-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="ddd70-120">For more information about working with case and nested tables, and how to choose a nested table key, see [Nested Tables &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/nested-tables-analysis-services-data-mining.md).</span></span>  
  
### <a name="to-add-a-data-source-view"></a><span data-ttu-id="ddd70-121">Добавление представления источников данных</span><span class="sxs-lookup"><span data-stu-id="ddd70-121">To add a data source view</span></span>  
  
1.  <span data-ttu-id="ddd70-122">В обозреватель решений щелкните правой кнопкой мыши элемент **представления источников данных**и выберите пункт **создать представление источника данных**.</span><span class="sxs-lookup"><span data-stu-id="ddd70-122">In Solution Explorer, right-click **Data Source Views**, and then select **New Data Source View**.</span></span>  
  
     <span data-ttu-id="ddd70-123">Будет открыт мастер представлений источников данных.</span><span class="sxs-lookup"><span data-stu-id="ddd70-123">The Data Source View Wizard opens.</span></span>  
  
2.  <span data-ttu-id="ddd70-124">На странице **Мастер представления источника данных** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ddd70-124">On the **Welcome to the Data Source View Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="ddd70-125">На странице **Выбор источника данных** в разделе **реляционные источники данных**выберите [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] источник данных, созданный в учебнике по основам интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="ddd70-125">On the **Select a Data Source** page, under **Relational data sources**, select the [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] data source that you created in the Basic Data Mining Tutorial.</span></span> <span data-ttu-id="ddd70-126">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ddd70-126">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="ddd70-127">На странице **Выбор таблиц и представлений** выберите следующие таблицы, а затем щелкните стрелку вправо, чтобы включить их в новое представление источника данных:</span><span class="sxs-lookup"><span data-stu-id="ddd70-127">On the **Select Tables and Views** page, select the following tables, and then click the right arrow to include them in the new data source view:</span></span>  
  
    -   `vAssocSeqOrders`  
  
    -   `vAssocSeqLineItems`  
  
5.  <span data-ttu-id="ddd70-128">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ddd70-128">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="ddd70-129">На странице **Завершение работы мастера** по умолчанию представление источника данных имеет имя [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ddd70-129">On the **Completing the Wizard** page, by default the data source view is named [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)].</span></span> <span data-ttu-id="ddd70-130">Измените имя на `Orders` , а затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="ddd70-130">Change the name to `Orders`, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="ddd70-131">Откроется конструктор представлений источников данных, и `Orders` появится представление источника данных.</span><span class="sxs-lookup"><span data-stu-id="ddd70-131">Data Source View Designer opens and the `Orders` data source view appears.</span></span>  
  
### <a name="to-create-a-relationship-between-tables"></a><span data-ttu-id="ddd70-132">Создание связи между таблицами</span><span class="sxs-lookup"><span data-stu-id="ddd70-132">To create a relationship between tables</span></span>  
  
1.  <span data-ttu-id="ddd70-133">В конструкторе представлений источников данных расположите две таблицы горизонтально друг напротив друга, поместив таблицу vAssocSeqLineItems слева, а vAssocSeqOrders — справа.</span><span class="sxs-lookup"><span data-stu-id="ddd70-133">In Data Source View Designer, position the two tables so that the tables are aligned horizontally, with the vAssocSeqLineItems table on the left side and the vAssocSeqOrders table on the right side.</span></span>  
  
2.  <span data-ttu-id="ddd70-134">Выберите столбец **OrderNumber** в таблице vAssocSeqLineItems.</span><span class="sxs-lookup"><span data-stu-id="ddd70-134">Select the **OrderNumber** column in the vAssocSeqLineItems table.</span></span>  
  
3.  <span data-ttu-id="ddd70-135">Перетащите столбец в таблицу vAssocSeqOrders и вставьте его в столбец **OrderNumber** .</span><span class="sxs-lookup"><span data-stu-id="ddd70-135">Drag the column to the vAssocSeqOrders table, and put it on the **OrderNumber** column.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="ddd70-136">Не забудьте перетащить столбец **OrderNumber** из вложенной таблицы vAssocSeqLineItems, которая представляет собой множество сторон объединения, в таблицу вариантов vAssocSeqOrders, которая представляет одну сторону объединения.</span><span class="sxs-lookup"><span data-stu-id="ddd70-136">Make sure to drag the **OrderNumber** column from the vAssocSeqLineItems nested table, which represents the many side of the join, to the vAssocSeqOrders case table, which represents the one side of the join.</span></span>  
  
     <span data-ttu-id="ddd70-137">Теперь между таблицами vAssocSeqLineItems и vAssocSeqOrders существует новая *связь "многие к одному* ".</span><span class="sxs-lookup"><span data-stu-id="ddd70-137">A new *many-to-one relationship* now exists between the vAssocSeqLineItems and vAssocSeqOrders tables.</span></span> <span data-ttu-id="ddd70-138">Если соединение таблиц выполнено правильно, должно появиться следующее представление источника данных:</span><span class="sxs-lookup"><span data-stu-id="ddd70-138">If you have joined the tables correctly, the data source view should appear as follows:</span></span>  
  
     <span data-ttu-id="ddd70-139">![ожидаемое соединение «многие к одному» вложенной таблицы и таблицы вариантов](../../2014/tutorials/media/dsv-nestedjoin-illustration.gif "ожидаемое соединение «многие к одному» вложенной таблицы и таблицы вариантов")</span><span class="sxs-lookup"><span data-stu-id="ddd70-139">![expected many-to-one join on nested and case table](../../2014/tutorials/media/dsv-nestedjoin-illustration.gif "expected many-to-one join on nested and case table")</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="ddd70-140">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="ddd70-140">Next Task in Lesson</span></span>  
 [<span data-ttu-id="ddd70-141">Руководство по созданию структуры потребительской корзины и модели &#40;промежуточного интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="ddd70-141">Creating a Market Basket Structure and Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-market-basket-structure-and-model-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="ddd70-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="ddd70-142">See Also</span></span>  
 <span data-ttu-id="ddd70-143">[Учебник по интеллектуальному анализу данных &#40;Analysis Services — интеллектуальный анализ данных&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="ddd70-143">[Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="ddd70-144">[Структуры интеллектуального анализа данных &#40;Analysis Services — интеллектуальный анализ&#41;](../../2014/analysis-services/data-mining/mining-structures-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="ddd70-144">[Mining Structures &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/mining-structures-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="ddd70-145">Модели интеллектуального анализа данных (службы Analysis Services — интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="ddd70-145">Mining Models &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/mining-models-analysis-services-data-mining.md)  
  
  
