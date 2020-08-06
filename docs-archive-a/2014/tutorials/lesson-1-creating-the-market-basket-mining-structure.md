---
title: Занятие 1. Создание структуры интеллектуального анализа данных для потребительской корзины | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a817c8d1-aff4-42b4-b194-ad9cc1c60f35
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a6a6e123e525512a72d70bcc8ca2eba549d1347e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734709"
---
# <a name="lesson-1-creating-the-market-basket-mining-structure"></a><span data-ttu-id="6afd8-102">Урок 1. Создание структуры интеллектуального анализа данных покупательского поведения</span><span class="sxs-lookup"><span data-stu-id="6afd8-102">Lesson 1: Creating the Market Basket Mining Structure</span></span>
  <span data-ttu-id="6afd8-103">На этом занятии требуется создать структуру интеллектуального анализа, позволяющуюй делать прогнозы относительно товаров [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)], которые клиент обычно покупает одновременно.</span><span class="sxs-lookup"><span data-stu-id="6afd8-103">In this lesson, you will create a mining structure that allows you to predict what [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] products a customer tends to purchase at the same time.</span></span> <span data-ttu-id="6afd8-104">Дополнительные сведения о структурах интеллектуального анализа данных и их ролях в интеллектуальном анализе см. в разделе [структуры интеллектуального анализа данных &#40;Analysis Services-&#41;интеллектуального анализа ](../../2014/analysis-services/data-mining/mining-structures-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="6afd8-104">If you are unfamiliar with mining structures and their role in data mining, see [Mining Structures &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/mining-structures-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="6afd8-105">Структура интеллектуального анализа данных взаимосвязей, которая будет создана на этом занятии, поддерживает добавление моделей интеллектуального анализа данных на основе [алгоритма взаимосвязей (Майкрософт](../../2014/analysis-services/data-mining/microsoft-association-algorithm.md)).</span><span class="sxs-lookup"><span data-stu-id="6afd8-105">The association mining structure that you will create in this lesson supports adding mining models based on the [Microsoft Association Algorithm](../../2014/analysis-services/data-mining/microsoft-association-algorithm.md).</span></span> <span data-ttu-id="6afd8-106">На следующих занятиях с помощью этих моделей интеллектуального анализа будет сформирован прогноз относительно типов товара, покупаемых клиентом одновременно, называемый анализом потребительской корзины. </span><span class="sxs-lookup"><span data-stu-id="6afd8-106">In later lessons, you will use the mining models to predict the type of products a customer tends to purchase at the same time, which is called a market basket analysis.</span></span> <span data-ttu-id="6afd8-107">Например, можно обнаружить, что обычно клиенты покупают одновременно горные велосипеды, шины для велосипедов и шлемы.</span><span class="sxs-lookup"><span data-stu-id="6afd8-107">For example, you may find that customers tend to buy mountain bikes, bike tires, and helmets at the same time.</span></span>  
  
 <span data-ttu-id="6afd8-108">На данном занятии структура интеллектуального анализа определяется с помощью вложенных таблиц.</span><span class="sxs-lookup"><span data-stu-id="6afd8-108">In this lesson, the mining structure is defined by using nested tables.</span></span> <span data-ttu-id="6afd8-109">Использование вложенных таблиц необходимо, потому что определяемый структурой домен данных содержится в двух различных исходных таблицах.</span><span class="sxs-lookup"><span data-stu-id="6afd8-109">Nested tables are used because the data domain that will be defined by the structure is contained within two different source tables.</span></span> <span data-ttu-id="6afd8-110">Дополнительные сведения о вложенных таблицах см. в разделе [вложенные таблицы &#40;Analysis Services-&#41;интеллектуального анализа данных ](../../2014/analysis-services/data-mining/nested-tables-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="6afd8-110">For more information on nested tables, see [Nested Tables &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/nested-tables-analysis-services-data-mining.md).</span></span>  
  
## <a name="create-mining-structure-statement"></a><span data-ttu-id="6afd8-111">Инструкция CREATE MINING STRUCTURE</span><span class="sxs-lookup"><span data-stu-id="6afd8-111">CREATE MINING STRUCTURE Statement</span></span>  
 <span data-ttu-id="6afd8-112">Чтобы создать структуру интеллектуального анализа данных, содержащую вложенную таблицу, используется инструкция [CREATE интеллектуального анализа данных &#40;DMX&#41;](/sql/dmx/create-mining-structure-dmx) .</span><span class="sxs-lookup"><span data-stu-id="6afd8-112">In order to create a mining structure containing a nested table, you use the [CREATE MINING STRUCTURE &#40;DMX&#41;](/sql/dmx/create-mining-structure-dmx) statement.</span></span> <span data-ttu-id="6afd8-113">Код инструкции можно разбить на следующие части:</span><span class="sxs-lookup"><span data-stu-id="6afd8-113">The code in the statement can be broken into the following parts:</span></span>  
  
-   <span data-ttu-id="6afd8-114">Присвоение структуре имени</span><span class="sxs-lookup"><span data-stu-id="6afd8-114">Naming the structure</span></span>  
  
-   <span data-ttu-id="6afd8-115">Определение ключевого столбца</span><span class="sxs-lookup"><span data-stu-id="6afd8-115">Defining the key column</span></span>  
  
-   <span data-ttu-id="6afd8-116">Определение столбцов интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="6afd8-116">Defining the mining columns</span></span>  
  
-   <span data-ttu-id="6afd8-117">Определение столбцов вложенных таблиц</span><span class="sxs-lookup"><span data-stu-id="6afd8-117">Defining the nested table columns</span></span>  
  
 <span data-ttu-id="6afd8-118">В следующем фрагменте показан общий пример инструкции CREATE MINING STRUCTURE:</span><span class="sxs-lookup"><span data-stu-id="6afd8-118">The following is a generic example of the CREATE MINING STRUCTURE statement:</span></span>  
  
```  
CREATE MINING STRUCTURE [<Mining Structure Name>]  
(  
   <key column>,  
   <mining structure columns>,  
   <table columns>  
   (  <nested key column>,  
      <nested mining structure columns> )  
)  
  
```  
  
 <span data-ttu-id="6afd8-119">Первая строчка кода определяет имя структуры:</span><span class="sxs-lookup"><span data-stu-id="6afd8-119">The first line of the code defines the name of the structure:</span></span>  
  
```  
CREATE MINING STRUCTURE [Mining Structure Name]  
```  
  
 <span data-ttu-id="6afd8-120">Сведения об именовании объекта в расширениях интеллектуального анализа данных см. в разделе [идентификаторы &#40;&#41;расширений интеллектуального анализа данных ](/sql/dmx/identifiers-dmx).</span><span class="sxs-lookup"><span data-stu-id="6afd8-120">For information about naming an object in DMX, see [Identifiers &#40;DMX&#41;](/sql/dmx/identifiers-dmx).</span></span>  
  
 <span data-ttu-id="6afd8-121">Следующая строка кода определяет ключевой столбец структуры интеллектуального анализа данных, уникально определяющий сущность в исходных данных:</span><span class="sxs-lookup"><span data-stu-id="6afd8-121">The next line of the code defines the key column for the mining structure, which uniquely identifies an entity in the source data:</span></span>  
  
```  
<key column>  
```  
  
 <span data-ttu-id="6afd8-122">В следующей строке кода определяются столбцы интеллектуального анализа, используемые моделями интеллектуального анализа, связанными со структурой интеллектуального анализа:</span><span class="sxs-lookup"><span data-stu-id="6afd8-122">The next line of the code is used to define the mining columns that will be used by the mining models associated with the mining structure:</span></span>  
  
```  
<mining structure columns>  
```  
  
 <span data-ttu-id="6afd8-123">В следующих строках кода определяются столбцы вложенных таблиц:</span><span class="sxs-lookup"><span data-stu-id="6afd8-123">The next lines of the code define the nested table columns:</span></span>  
  
```  
<table columns>  
(  <nested key column>,  
   <nested mining structure columns> )  
```  
  
 <span data-ttu-id="6afd8-124">Дополнительные сведения о типах столбцов структуры интеллектуального анализа данных, которые можно определить, см. в разделе [столбцы структуры интеллектуального анализа данных](../../2014/analysis-services/data-mining/mining-structure-columns.md).</span><span class="sxs-lookup"><span data-stu-id="6afd8-124">For information about the types of mining structure columns that you can define, see [Mining Structure Columns](../../2014/analysis-services/data-mining/mining-structure-columns.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6afd8-125">По умолчанию среда [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] создает 30-процентный набор контрольных данных для каждой структуры интеллектуального анализа данных. Однако, если для создания структуры используются расширения интеллектуального анализа данных, набор контрольных данных необходимо добавить вручную, если он нужен.</span><span class="sxs-lookup"><span data-stu-id="6afd8-125">By default, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] creates a 30 percent holdout data set for each mining structure; however, when you use DMX to create a mining structure, you must manually add the holdout data set, if desired.</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="6afd8-126">Задачи занятия</span><span class="sxs-lookup"><span data-stu-id="6afd8-126">Lesson Tasks</span></span>  
 <span data-ttu-id="6afd8-127">На этом занятии будут выполнены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="6afd8-127">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="6afd8-128">Создание нового пустого запроса</span><span class="sxs-lookup"><span data-stu-id="6afd8-128">Create a new blank query</span></span>  
  
-   <span data-ttu-id="6afd8-129">Изменение запроса, чтобы создать структуру интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="6afd8-129">Alter the query to create the mining structure</span></span>  
  
-   <span data-ttu-id="6afd8-130">Выполнение запроса</span><span class="sxs-lookup"><span data-stu-id="6afd8-130">Execute the query</span></span>  
  
## <a name="creating-the-query"></a><span data-ttu-id="6afd8-131">Создание запроса</span><span class="sxs-lookup"><span data-stu-id="6afd8-131">Creating the Query</span></span>  
 <span data-ttu-id="6afd8-132">На первом этапе необходимо подключиться к экземпляру служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] и создать новый DMX-запрос в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6afd8-132">The first step is to connect to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] and create a new DMX query in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-create-a-new-dmx-query-in-sql-server-management-studio"></a><span data-ttu-id="6afd8-133">Создание нового DMX-запроса в среде SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6afd8-133">To create a new DMX query in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="6afd8-134">Откройте среду [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6afd8-134">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="6afd8-135">В диалоговом окне **соединение с сервером** в поле **тип сервера**выберите **Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="6afd8-135">In the **Connect to Server** dialog box, for **Server type**, select **Analysis Services**.</span></span> <span data-ttu-id="6afd8-136">В поле **имя сервера**введите `LocalHost` или имя экземпляра [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , к которому необходимо подключиться для этого занятия.</span><span class="sxs-lookup"><span data-stu-id="6afd8-136">In **Server name**, type `LocalHost`, or the name of the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that you want to connect to for this lesson.</span></span> <span data-ttu-id="6afd8-137">Нажмите кнопку **Подключиться**.</span><span class="sxs-lookup"><span data-stu-id="6afd8-137">Click **Connect**.</span></span>  
  
3.  <span data-ttu-id="6afd8-138">В окне **Обозреватель объектов**щелкните правой кнопкой мыши экземпляр служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], укажите **Создать запрос**, а затем выберите пункт **Расширения интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="6afd8-138">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="6afd8-139">Откроется редактор запросов, содержащий новый, пустой запрос.</span><span class="sxs-lookup"><span data-stu-id="6afd8-139">Query Editor opens and contains a new, blank query.</span></span>  
  
## <a name="altering-the-query"></a><span data-ttu-id="6afd8-140">Изменение запроса</span><span class="sxs-lookup"><span data-stu-id="6afd8-140">Altering the Query</span></span>  
 <span data-ttu-id="6afd8-141">На следующем этапе необходимо изменить описанную выше инструкцию CREATE MINING STRUCTURE, чтобы создать структуру интеллектуального анализа «Потребительская корзина».</span><span class="sxs-lookup"><span data-stu-id="6afd8-141">The next step is to modify the CREATE MINING STRUCTURE statement described above to create the Market Basket mining structure.</span></span>  
  
#### <a name="to-customize-the-create-mining-structure-statement"></a><span data-ttu-id="6afd8-142">Настройка инструкции CREATE MINING STRUCTURE</span><span class="sxs-lookup"><span data-stu-id="6afd8-142">To customize the CREATE MINING STRUCTURE statement</span></span>  
  
1.  <span data-ttu-id="6afd8-143">В редакторе запросов скопируйте общий пример инструкции CREATE MINING STRUCTURE в пустое окно запроса.</span><span class="sxs-lookup"><span data-stu-id="6afd8-143">In Query Editor, copy the generic example of the CREATE MINING STRUCTURE statement into the blank query.</span></span>  
  
2.  <span data-ttu-id="6afd8-144">Вместо</span><span class="sxs-lookup"><span data-stu-id="6afd8-144">Replace the following:</span></span>  
  
    ```  
    [mining structure name]   
    ```  
  
     <span data-ttu-id="6afd8-145">на:</span><span class="sxs-lookup"><span data-stu-id="6afd8-145">with:</span></span>  
  
    ```  
    [Market Basket]  
    ```  
  
3.  <span data-ttu-id="6afd8-146">Вместо</span><span class="sxs-lookup"><span data-stu-id="6afd8-146">Replace the following:</span></span>  
  
    ```  
    <key column>  
    ```  
  
     <span data-ttu-id="6afd8-147">на:</span><span class="sxs-lookup"><span data-stu-id="6afd8-147">with:</span></span>  
  
    ```  
    OrderNumber TEXT KEY  
    ```  
  
4.  <span data-ttu-id="6afd8-148">Вместо</span><span class="sxs-lookup"><span data-stu-id="6afd8-148">Replace the following:</span></span>  
  
    ```  
    <table columns>  
    (  <nested key column>,  
       <nested mining structure columns> )  
    ```  
  
     <span data-ttu-id="6afd8-149">на:</span><span class="sxs-lookup"><span data-stu-id="6afd8-149">with:</span></span>  
  
    ```  
    [Products] TABLE (  
        [Model] TEXT KEY  
    )  
    ```  
  
     <span data-ttu-id="6afd8-150">Язык TEXT KEY указывает, что столбец модели является ключевым столбцом для вложенной таблицы.</span><span class="sxs-lookup"><span data-stu-id="6afd8-150">The TEXT KEY language specifies that the Model column is the key column for the nested table.</span></span>  
  
     <span data-ttu-id="6afd8-151">Полная инструкция создания структуры интеллектуального анализа данных должна выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="6afd8-151">The complete mining structure statement should now be as follows:</span></span>  
  
    ```  
    CREATE MINING STRUCTURE [Market Basket] (  
        OrderNumber TEXT KEY,  
        [Products] TABLE (  
            [Model] TEXT KEY  
        )  
    )  
    ```  
  
5.  <span data-ttu-id="6afd8-152">В меню **Файл** щелкните **Сохранить DMXQuery1.dmx как**.</span><span class="sxs-lookup"><span data-stu-id="6afd8-152">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
6.  <span data-ttu-id="6afd8-153">В диалоговом окне **Сохранить как** перейдите в соответствующую папку и присвойте файлу имя `Market Basket Structure.dmx` .</span><span class="sxs-lookup"><span data-stu-id="6afd8-153">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Market Basket Structure.dmx`.</span></span>  
  
## <a name="executing-the-query"></a><span data-ttu-id="6afd8-154">Выполнение запроса</span><span class="sxs-lookup"><span data-stu-id="6afd8-154">Executing the Query</span></span>  
 <span data-ttu-id="6afd8-155">На последнем шаге нужно выполнить запрос.</span><span class="sxs-lookup"><span data-stu-id="6afd8-155">The final step is to execute the query.</span></span> <span data-ttu-id="6afd8-156">После создания и сохранения запроса его нужно выполнить (то есть нужно выполнить инструкцию), чтобы создать на сервере структуру интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="6afd8-156">After a query is created and saved, it needs to be executed (that is, the statement needs to be run) in order to create the mining structure on the server.</span></span> <span data-ttu-id="6afd8-157">Дополнительные сведения о выполнении запросов в редакторе запросов см. в разделе [ядро СУБД редактор запросов &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/database-engine-query-editor-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="6afd8-157">For more information about executing queries in Query Editor, see [Database Engine Query Editor &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/database-engine-query-editor-sql-server-management-studio.md).</span></span>  
  
#### <a name="to-execute-the-query"></a><span data-ttu-id="6afd8-158">Выполнение запроса</span><span class="sxs-lookup"><span data-stu-id="6afd8-158">To execute the query</span></span>  
  
-   <span data-ttu-id="6afd8-159">На панели инструментов редактора запросов нажмите кнопку **выполнить**.</span><span class="sxs-lookup"><span data-stu-id="6afd8-159">In Query Editor, on the toolbar, click **Execute**.</span></span>  
  
     <span data-ttu-id="6afd8-160">Состояние запроса отображается на вкладке **сообщения** в нижней части редактора запросов после завершения выполнения инструкции.</span><span class="sxs-lookup"><span data-stu-id="6afd8-160">The status of the query is displayed in the **Messages** tab at the bottom of Query Editor after the statement finishes executing.</span></span> <span data-ttu-id="6afd8-161">Сообщение должно выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="6afd8-161">Messages should display:</span></span>  
  
    ```  
    Executing the query   
    Execution complete  
    ```  
  
     <span data-ttu-id="6afd8-162">На сервере теперь существует новая структура с именем " **Потребительская корзина** ".</span><span class="sxs-lookup"><span data-stu-id="6afd8-162">A new structure named **Market Basket** now exists on the server.</span></span>  
  
 <span data-ttu-id="6afd8-163">На следующем занятии к созданной структуре интеллектуального анализа «Потребительская корзина» будет добавлена модель интеллектуального анализа.</span><span class="sxs-lookup"><span data-stu-id="6afd8-163">In the next lesson, you will add mining models to the Market Basket mining structure you just created.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="6afd8-164">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="6afd8-164">Next Lesson</span></span>  
 [<span data-ttu-id="6afd8-165">Урок 2. Добавление моделей к структуре интеллектуального анализа данных покупательского поведения</span><span class="sxs-lookup"><span data-stu-id="6afd8-165">Lesson 2: Adding Mining Models to the Market Basket Mining Structure</span></span>](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md)  
  
  
