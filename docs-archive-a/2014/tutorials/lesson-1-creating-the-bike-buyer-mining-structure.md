---
title: Занятие 1. Создание структуры интеллектуального анализа данных покупателя велосипеда | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a73ac60b-660f-458a-bd2f-993fbeba7226
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: d6384910858d87a80aa3c8f897bc88e45f4504fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734706"
---
# <a name="lesson-1-creating-the-bike-buyer-mining-structure"></a><span data-ttu-id="3f9b1-102">Урок 1. Создание структуры интеллектуального анализа данных "Покупатель велосипеда"</span><span class="sxs-lookup"><span data-stu-id="3f9b1-102">Lesson 1: Creating the Bike Buyer Mining Structure</span></span>
  <span data-ttu-id="3f9b1-103">На этом занятии вы создадите структуры интеллектуального анализа данных, которая позволяет предсказать, купит ли потенциальный клиент [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] велосипед.</span><span class="sxs-lookup"><span data-stu-id="3f9b1-103">In this lesson, you will create a mining structure that allows you to predict whether a potential customer of [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] will purchase a bicycle.</span></span> <span data-ttu-id="3f9b1-104">Дополнительные сведения о структурах интеллектуального анализа данных и их ролях в интеллектуальном анализе см. в разделе [структуры интеллектуального анализа данных &#40;Analysis Services-&#41;интеллектуального анализа ](../../2014/analysis-services/data-mining/mining-structures-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="3f9b1-104">If you are unfamiliar with mining structures and their role in data mining, see [Mining Structures &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/mining-structures-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="3f9b1-105">Структура интеллектуального анализа данных покупателя велосипеда, которая будет создана на этом занятии, поддерживает добавление моделей интеллектуального анализа данных на основе алгоритма [кластеризации Майкрософт](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md)[Microsoft для дерева принятия решений](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="3f9b1-105">The Bike Buyer mining structure that you will create in this lesson supports adding mining models based on the [Microsoft Clustering Algorithm](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md)[Microsoft Decision Trees Algorithm](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md).</span></span> <span data-ttu-id="3f9b1-106">На следующих занятиях вы будете использовать кластерные модели интеллектуального анализа данных для исследования других способов группирования клиентов и будете использовать модели интеллектуального анализа данных дерева решений для предсказания, купит ли потенциальный клиент велосипед.</span><span class="sxs-lookup"><span data-stu-id="3f9b1-106">In later lessons, you will use the clustering mining models to explore the different ways in which customers can be grouped, and will use decision tree mining models to predict whether or not a potential customer will purchase a bicycle.</span></span>  
  
## <a name="create-mining-structure-statement"></a><span data-ttu-id="3f9b1-107">Инструкция CREATE MINING STRUCTURE</span><span class="sxs-lookup"><span data-stu-id="3f9b1-107">CREATE MINING STRUCTURE Statement</span></span>  
 <span data-ttu-id="3f9b1-108">Чтобы создать структуру интеллектуального анализа данных, используйте инструкцию [создания структуры интеллектуального анализа данных &#40;DMX&#41;](/sql/dmx/create-mining-structure-dmx) .</span><span class="sxs-lookup"><span data-stu-id="3f9b1-108">To create a mining structure, you use the [CREATE MINING STRUCTURE &#40;DMX&#41;](/sql/dmx/create-mining-structure-dmx) statement.</span></span> <span data-ttu-id="3f9b1-109">Код инструкции можно разбить на следующие части:</span><span class="sxs-lookup"><span data-stu-id="3f9b1-109">The code in the statement can be broken into the following parts:</span></span>  
  
-   <span data-ttu-id="3f9b1-110">Присвоение структуре имени.</span><span class="sxs-lookup"><span data-stu-id="3f9b1-110">Naming the structure.</span></span>  
  
-   <span data-ttu-id="3f9b1-111">Определение ключевого столбца.</span><span class="sxs-lookup"><span data-stu-id="3f9b1-111">Defining the key column.</span></span>  
  
-   <span data-ttu-id="3f9b1-112">Определение столбцов интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="3f9b1-112">Defining the mining columns.</span></span>  
  
-   <span data-ttu-id="3f9b1-113">Определение необязательного набора проверочных данных.</span><span class="sxs-lookup"><span data-stu-id="3f9b1-113">Defining an optional testing data set.</span></span>  
  
 <span data-ttu-id="3f9b1-114">В следующем фрагменте показан общий пример инструкции CREATE MINING STRUCTURE:</span><span class="sxs-lookup"><span data-stu-id="3f9b1-114">The following is a generic example of the CREATE MINING STRUCTURE statement:</span></span>  
  
```  
CREATE MINING STRUCTURE [<mining structure name>]  
(  
    <key column>,  
    <mining structure columns>  
)   
WITH HOLDOUT (<holdout specifier>)  
```  
  
 <span data-ttu-id="3f9b1-115">Первая строчка кода определяет имя структуры:</span><span class="sxs-lookup"><span data-stu-id="3f9b1-115">The first line of the code defines the name of the structure:</span></span>  
  
```  
CREATE MINING STRUCTURE [<mining structure name>]  
```  
  
 <span data-ttu-id="3f9b1-116">Сведения об именовании объекта в расширениях интеллектуального анализа данных см. в разделе [идентификаторы &#40;dmx&#41;](/sql/dmx/identifiers-dmx).</span><span class="sxs-lookup"><span data-stu-id="3f9b1-116">For information about naming an object in Data Mining Extensions (DMX), see [Identifiers &#40;DMX&#41;](/sql/dmx/identifiers-dmx).</span></span>  
  
 <span data-ttu-id="3f9b1-117">Следующая строка кода определяет ключевой столбец структуры интеллектуального анализа данных, уникально определяющий сущность в исходных данных:</span><span class="sxs-lookup"><span data-stu-id="3f9b1-117">The next line of the code defines the key column for the mining structure, which uniquely identifies an entity in the source data:</span></span>  
  
```  
<key column>,  
```  
  
 <span data-ttu-id="3f9b1-118">В созданной структуре интеллектуального анализа данных идентификатор клиента, `CustomerKey`, определяет некоторую сущность в исходных данных.</span><span class="sxs-lookup"><span data-stu-id="3f9b1-118">In the mining structure you will create, the customer identifier, `CustomerKey`, defines an entity in the source data.</span></span>  
  
 <span data-ttu-id="3f9b1-119">В следующей строке кода определяются столбцы интеллектуального анализа, используемые моделями интеллектуального анализа, связанными со структурой интеллектуального анализа:</span><span class="sxs-lookup"><span data-stu-id="3f9b1-119">The next line of the code is used to define the mining columns that will be used by the mining models associated with the mining structure:</span></span>  
  
```  
<mining structure columns>  
```  
  
 <span data-ttu-id="3f9b1-120">Функцию ДИСКРЕТИЗАЦИИ можно использовать в \<mining structure columns> для дискретизации непрерывных столбцов с помощью следующего синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="3f9b1-120">You can use the DISCRETIZE function within \<mining structure columns> to discretize continuous columns by using the following syntax:</span></span>  
  
 `DISCRETIZE(<method>,<number of buckets>)`  
  
 <span data-ttu-id="3f9b1-121">Дополнительные сведения о дискретизации столбцов см. в разделе [методы дискретизации &#40;&#41;интеллектуального анализа данных ](../../2014/analysis-services/data-mining/discretization-methods-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="3f9b1-121">For more information about discretizing columns, see [Discretization Methods &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/discretization-methods-data-mining.md).</span></span> <span data-ttu-id="3f9b1-122">Дополнительные сведения о типах столбцов структуры интеллектуального анализа данных, которые можно определить, см. в разделе [столбцы структуры интеллектуального анализа данных](../../2014/analysis-services/data-mining/mining-structure-columns.md).</span><span class="sxs-lookup"><span data-stu-id="3f9b1-122">For more information about the types of mining structure columns that you can define, see [Mining Structure Columns](../../2014/analysis-services/data-mining/mining-structure-columns.md).</span></span>  
  
 <span data-ttu-id="3f9b1-123">В последней строке кода определяется необязательная секция в структуре интеллектуального анализа данных:</span><span class="sxs-lookup"><span data-stu-id="3f9b1-123">The final line of the code defines an optional partition in the mining structure:</span></span>  
  
```  
WITH HOLDOUT (<holdout specifier>)  
```  
  
 <span data-ttu-id="3f9b1-124">Можно определить некоторую часть данных как предназначенную для проверки моделей интеллектуального анализа данных, относящихся к этой структуре, после чего оставшиеся данные применяются для обучения моделей.</span><span class="sxs-lookup"><span data-stu-id="3f9b1-124">You specify some portion of the data to use for testing mining models that are related to the structure, and the remaining data is used for training the models.</span></span> <span data-ttu-id="3f9b1-125">По умолчанию службы [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] создают набор проверочных данных, который содержит 30 процентов всех данных варианта.</span><span class="sxs-lookup"><span data-stu-id="3f9b1-125">By default, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] creates a test data set that contains 30 percent of all case data.</span></span> <span data-ttu-id="3f9b1-126">Будет добавлена спецификация, согласно которой набор проверочных данных должен содержать 30 процентов вариантов, вплоть до максимального количества, равного 1000 вариант.</span><span class="sxs-lookup"><span data-stu-id="3f9b1-126">You will add the specification that the test data set should contain 30 percent of the cases up to a maximum of 1000 cases.</span></span> <span data-ttu-id="3f9b1-127">Если 30 процентов вариантов меньше 1000, набор проверочных данных будет содержать это меньшее количество.</span><span class="sxs-lookup"><span data-stu-id="3f9b1-127">If 30 percent of the cases is less than 1000, the test data set will contain the smaller amount.</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="3f9b1-128">Задачи занятия</span><span class="sxs-lookup"><span data-stu-id="3f9b1-128">Lesson Tasks</span></span>  
 <span data-ttu-id="3f9b1-129">На этом занятии будут выполнены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="3f9b1-129">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="3f9b1-130">Создание нового пустого запроса.</span><span class="sxs-lookup"><span data-stu-id="3f9b1-130">Create a new blank query.</span></span>  
  
-   <span data-ttu-id="3f9b1-131">Изменение запроса, чтобы создать структуру интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="3f9b1-131">Alter the query to create the mining structure.</span></span>  
  
-   <span data-ttu-id="3f9b1-132">выполнение запроса.</span><span class="sxs-lookup"><span data-stu-id="3f9b1-132">Execute the query.</span></span>  
  
## <a name="creating-the-query"></a><span data-ttu-id="3f9b1-133">Создание запроса</span><span class="sxs-lookup"><span data-stu-id="3f9b1-133">Creating the Query</span></span>  
 <span data-ttu-id="3f9b1-134">На первом этапе необходимо подключиться к экземпляру служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] и создать новый DMX-запрос в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3f9b1-134">The first step is to connect to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] and create a new DMX query in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-create-a-new-dmx-query-in-sql-server-management-studio"></a><span data-ttu-id="3f9b1-135">Создание нового DMX-запроса в среде SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3f9b1-135">To create a new DMX query in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="3f9b1-136">Откройте среду [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3f9b1-136">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="3f9b1-137">В диалоговом окне **соединение с сервером** в поле **тип сервера**выберите **Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="3f9b1-137">In the **Connect to Server** dialog box, for **Server type**, select **Analysis Services**.</span></span> <span data-ttu-id="3f9b1-138">В поле **имя сервера**введите `LocalHost` или введите имя экземпляра [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , к которому необходимо подключиться для этого занятия.</span><span class="sxs-lookup"><span data-stu-id="3f9b1-138">In **Server name**, type `LocalHost`, or type the name of the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that you want to connect to for this lesson.</span></span> <span data-ttu-id="3f9b1-139">Нажмите кнопку **Подключиться**.</span><span class="sxs-lookup"><span data-stu-id="3f9b1-139">Click **Connect**.</span></span>  
  
3.  <span data-ttu-id="3f9b1-140">В **обозревателе объектов**щелкните правой кнопкой мыши экземпляр [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , наведите указатель на пункт **создать запрос**и выберите **расширения интеллектуального анализа данных** , чтобы открыть **Редактор запросов** и новый пустой запрос.</span><span class="sxs-lookup"><span data-stu-id="3f9b1-140">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX** to open the **Query Editor** and a new, blank query.</span></span>  
  
## <a name="altering-the-query"></a><span data-ttu-id="3f9b1-141">Изменение запроса</span><span class="sxs-lookup"><span data-stu-id="3f9b1-141">Altering the Query</span></span>  
 <span data-ttu-id="3f9b1-142">Следующим шагом будет изменение инструкции CREATE MINING STRUCTURE, описанной выше, чтобы создать структуру интеллектуального анализа данных для покупателя велосипеда.</span><span class="sxs-lookup"><span data-stu-id="3f9b1-142">The next step is to modify the CREATE MINING STRUCTURE statement described above to create the Bike Buyer mining structure.</span></span>  
  
#### <a name="to-customize-the-create-mining-structure-statement"></a><span data-ttu-id="3f9b1-143">Настройка инструкции CREATE MINING STRUCTURE</span><span class="sxs-lookup"><span data-stu-id="3f9b1-143">To customize the CREATE MINING STRUCTURE statement</span></span>  
  
1.  <span data-ttu-id="3f9b1-144">В редакторе запросов скопируйте общий пример инструкции CREATE MINING STRUCTURE в пустое окно запроса.</span><span class="sxs-lookup"><span data-stu-id="3f9b1-144">In the Query Editor, copy the generic example of the CREATE MINING STRUCTURE statement into the blank query.</span></span>  
  
2.  <span data-ttu-id="3f9b1-145">Вместо</span><span class="sxs-lookup"><span data-stu-id="3f9b1-145">Replace the following:</span></span>  
  
    ```  
    [<mining structure>]   
    ```  
  
     <span data-ttu-id="3f9b1-146">на:</span><span class="sxs-lookup"><span data-stu-id="3f9b1-146">with:</span></span>  
  
    ```  
    [Bike Buyer]  
    ```  
  
3.  <span data-ttu-id="3f9b1-147">Вместо</span><span class="sxs-lookup"><span data-stu-id="3f9b1-147">Replace the following:</span></span>  
  
    ```  
    <key column>   
    ```  
  
     <span data-ttu-id="3f9b1-148">на:</span><span class="sxs-lookup"><span data-stu-id="3f9b1-148">with:</span></span>  
  
    ```  
    CustomerKey LONG KEY  
    ```  
  
4.  <span data-ttu-id="3f9b1-149">Вместо</span><span class="sxs-lookup"><span data-stu-id="3f9b1-149">Replace the following:</span></span>  
  
    ```  
    <mining structure columns>   
    ```  
  
     <span data-ttu-id="3f9b1-150">на:</span><span class="sxs-lookup"><span data-stu-id="3f9b1-150">with:</span></span>  
  
    ```  
    [Age] LONG DISCRETIZED(Automatic,10),  
    [Bike Buyer] LONG DISCRETE,  
    [Commute Distance] TEXT DISCRETE,  
    [Education] TEXT DISCRETE,  
    [Gender] TEXT DISCRETE,  
    [House Owner Flag] TEXT DISCRETE,  
    [Marital Status] TEXT DISCRETE,  
    [Number Cars Owned] LONG DISCRETE,  
    [Number Children At Home] LONG DISCRETE,  
    [Occupation] TEXT DISCRETE,  
    [Region] TEXT DISCRETE,  
    [Total Children]LONG DISCRETE,  
    [Yearly Income] DOUBLE CONTINUOUS  
    ```  
  
5.  <span data-ttu-id="3f9b1-151">Вместо</span><span class="sxs-lookup"><span data-stu-id="3f9b1-151">Replace the following:</span></span>  
  
    ```  
    WITH HOLDOUT (holdout specifier>)  
    ```  
  
     <span data-ttu-id="3f9b1-152">на:</span><span class="sxs-lookup"><span data-stu-id="3f9b1-152">with:</span></span>  
  
    ```  
    WITH HOLDOUT (30 PERCENT or 1000 CASES)  
    ```  
  
     <span data-ttu-id="3f9b1-153">Полная инструкция создания структуры интеллектуального анализа данных должна выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="3f9b1-153">The complete mining structure statement should now be as follows:</span></span>  
  
    ```  
    CREATE MINING STRUCTURE [Bike Buyer]  
    (  
       [Customer Key] LONG KEY,  
       [Age]LONG DISCRETIZED(Automatic,10),  
       [Bike Buyer] LONG DISCRETE,  
       [Commute Distance] TEXT DISCRETE,  
       [Education] TEXT DISCRETE,  
       [Gender] TEXT DISCRETE,  
       [House Owner Flag] TEXT DISCRETE,  
       [Marital Status] TEXT DISCRETE,  
       [Number Cars Owned]LONG DISCRETE,  
       [Number Children At Home]LONG DISCRETE,  
       [Occupation] TEXT DISCRETE,  
       [Region] TEXT DISCRETE,  
       [Total Children]LONG DISCRETE,  
       [Yearly Income] DOUBLE CONTINUOUS  
    )  
    WITH HOLDOUT (30 PERCENT or 1000 CASES)  
  
    ```  
  
6.  <span data-ttu-id="3f9b1-154">В меню **Файл** щелкните **Сохранить DMXQuery1.dmx как**.</span><span class="sxs-lookup"><span data-stu-id="3f9b1-154">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="3f9b1-155">В диалоговом окне **Сохранить как** перейдите в соответствующую папку и присвойте файлу имя `Bike Buyer Structure.dmx` .</span><span class="sxs-lookup"><span data-stu-id="3f9b1-155">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Bike Buyer Structure.dmx`.</span></span>  
  
## <a name="executing-the-query"></a><span data-ttu-id="3f9b1-156">Выполнение запроса</span><span class="sxs-lookup"><span data-stu-id="3f9b1-156">Executing the Query</span></span>  
 <span data-ttu-id="3f9b1-157">На последнем шаге нужно выполнить запрос.</span><span class="sxs-lookup"><span data-stu-id="3f9b1-157">The final step is to execute the query.</span></span> <span data-ttu-id="3f9b1-158">После создания и сохранения запроса его необходимо выполнить.</span><span class="sxs-lookup"><span data-stu-id="3f9b1-158">After a query is created and saved, it needs to be executed.</span></span> <span data-ttu-id="3f9b1-159">Это означает, что должна быть запущена инструкция для создания на сервере структуры интеллектуального анализа.</span><span class="sxs-lookup"><span data-stu-id="3f9b1-159">That is, the statement needs to be run in order to create the mining structure on the server.</span></span> <span data-ttu-id="3f9b1-160">Дополнительные сведения о выполнении запросов в редакторе запросов см. в разделе [ядро СУБД редактор запросов &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/database-engine-query-editor-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="3f9b1-160">For more information about executing queries in Query Editor, see [Database Engine Query Editor &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/database-engine-query-editor-sql-server-management-studio.md).</span></span>  
  
#### <a name="to-execute-the-query"></a><span data-ttu-id="3f9b1-161">Выполнение запроса</span><span class="sxs-lookup"><span data-stu-id="3f9b1-161">To execute the query</span></span>  
  
1.  <span data-ttu-id="3f9b1-162">На панели инструментов редактора запросов нажмите кнопку **выполнить**.</span><span class="sxs-lookup"><span data-stu-id="3f9b1-162">In Query Editor, on the toolbar, click **Execute**.</span></span>  
  
     <span data-ttu-id="3f9b1-163">Состояние запроса отображается на вкладке **сообщения** в нижней части редактора запросов после завершения выполнения инструкции.</span><span class="sxs-lookup"><span data-stu-id="3f9b1-163">The status of the query is displayed in the **Messages** tab at the bottom of Query Editor after the statement finishes executing.</span></span> <span data-ttu-id="3f9b1-164">Сообщение должно выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3f9b1-164">Messages should display:</span></span>  
  
    ```  
    Executing the query   
    Execution complete  
    ```  
  
     <span data-ttu-id="3f9b1-165">На сервере теперь существует новая структура с именем **Bike Buyer** .</span><span class="sxs-lookup"><span data-stu-id="3f9b1-165">A new structure named **Bike Buyer** now exists on the server.</span></span>  
  
 <span data-ttu-id="3f9b1-166">На следующем занятии вы добавите модели интеллектуального анализа данных в только что созданную структуру.</span><span class="sxs-lookup"><span data-stu-id="3f9b1-166">In the next lesson, you will add mining models to the structure you just created.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="3f9b1-167">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="3f9b1-167">Next Lesson</span></span>  
 [<span data-ttu-id="3f9b1-168">Урок 2. Добавление моделей к структуре интеллектуального анализа данных "Покупатель велосипеда"</span><span class="sxs-lookup"><span data-stu-id="3f9b1-168">Lesson 2: Adding Mining Models to the Bike Buyer Mining Structure</span></span>](../../2014/tutorials/lesson-2-adding-mining-models-to-the-bike-buyer-mining-structure.md)  
  
  
