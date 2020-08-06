---
title: Создание одноэлементного запроса в конструкторе интеллектуального анализа данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- singleton queries [Analysis Services]
- Mining Model Prediction [Analysis Services], singleton queries
ms.assetid: 6cdca8a0-cf16-46eb-a652-0bff820625ab
author: minewiskan
ms.author: owend
ms.openlocfilehash: 07491924dbcf0bd35d049e6a7c290d49becfb45d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656046"
---
# <a name="create-a-singleton-query-in-the-data-mining-designer"></a><span data-ttu-id="10dd4-102">Создание одноэлементного запроса в конструкторе интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="10dd4-102">Create a Singleton Query in the Data Mining Designer</span></span>
  <span data-ttu-id="10dd4-103">Одноэлементный запрос используется при необходимости создать прогноз для одного объекта.</span><span class="sxs-lookup"><span data-stu-id="10dd4-103">A singleton query is useful if you want to create a prediction for a single case.</span></span> <span data-ttu-id="10dd4-104">Дополнительные сведения об одноэлементных запросах см. в разделе [Запросы интеллектуального анализа данных](data-mining-queries.md).</span><span class="sxs-lookup"><span data-stu-id="10dd4-104">For more information about singleton queries, see [Data Mining Queries](data-mining-queries.md).</span></span>  
  
 <span data-ttu-id="10dd4-105">На вкладке **Прогноз модели интеллектуального анализа данных** конструктора интеллектуального анализа данных можно создавать много различных типов запросов.</span><span class="sxs-lookup"><span data-stu-id="10dd4-105">In the **Mining Model Prediction** tab of Data Mining Designer, you can create many different types of queries.</span></span> <span data-ttu-id="10dd4-106">Запросы можно создавать с помощью конструктора, либо путем ввода инструкций расширения интеллектуального анализа данных (DMX-инструкций).</span><span class="sxs-lookup"><span data-stu-id="10dd4-106">You can create a query by using the designer, or by typing Data Mining Extensions (DMX) statements.</span></span> <span data-ttu-id="10dd4-107">Кроме того, можно начать работу с конструктором, а затем изменить созданный в нем запрос путем изменения DMX-инструкций или путем добавления предложений WHERE или ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="10dd4-107">You can also start with the designer and modify the query that it creates by changing the DMX statements, or by adding a WHERE or ORDER BY clause.</span></span>  
  
 <span data-ttu-id="10dd4-108">Чтобы переключиться между представлением конструктора запросов и представлением текста запросов, нажмите первую кнопку на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="10dd4-108">To switch between the query design view and the query text view, click the first button on the toolbar.</span></span> <span data-ttu-id="10dd4-109">В режиме представления текста запроса можно посмотреть код расширений интеллектуального анализа данных, созданный построителем прогнозирующих запросов.</span><span class="sxs-lookup"><span data-stu-id="10dd4-109">When you are in the query text view, you can view the DMX code that Prediction Query Builder creates.</span></span> <span data-ttu-id="10dd4-110">Кроме того, здесь можно выполнить запрос, изменить его и выполнить измененный запрос.</span><span class="sxs-lookup"><span data-stu-id="10dd4-110">You can also run the query, modify the query, and run the modified query.</span></span> <span data-ttu-id="10dd4-111">Однако измененный запрос не сохранится при переключении обратно в представление проектирования запроса.</span><span class="sxs-lookup"><span data-stu-id="10dd4-111">However, the modified query is not persisted if you switch back to the query design view.</span></span>  
  
 <span data-ttu-id="10dd4-112">В приведенном ниже коде показан пример одноэлементного запроса к модели целевой рассылки TM_Decision_Tree.</span><span class="sxs-lookup"><span data-stu-id="10dd4-112">The following code shows an example of a singleton query against the targeted mailing model, TM_Decision_Tree.</span></span>  
  
```  
SELECT [Bike Buyer], PredictProbability([Bike Buyer]) as ProbableBuyer  
FROM [TM_Decision_Tree]  
NATURAL PREDICTION JOIN  
(SELECT '2' AS [Number Children At Home], '45' as [Age])  
AS [t]  
```  
  
 <span data-ttu-id="10dd4-113">Следующие шаги объясняют процедуру создания прогнозирующего запроса.</span><span class="sxs-lookup"><span data-stu-id="10dd4-113">The following steps explain how to create this prediction query.</span></span>  
  
### <a name="to-create-a-singleton-query-by-using-the-data-mining-designer"></a><span data-ttu-id="10dd4-114">Создание одноэлементного запроса с помощью конструктора интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="10dd4-114">To create a singleton query by using the Data Mining Designer</span></span>  
  
1.  <span data-ttu-id="10dd4-115">Перейдите на вкладку **Прогноз моделей интеллектуального анализа данных** в конструкторе интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="10dd4-115">Click the **Mining Model Prediction** tab in Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="10dd4-116">Нажмите кнопку **Выбрать модель** в таблице **Модель интеллектуального анализа данных** .</span><span class="sxs-lookup"><span data-stu-id="10dd4-116">Click **Select Model** on the **Mining Model** table.</span></span>  
  
     <span data-ttu-id="10dd4-117">Откроется диалоговое окно **Выбор модели интеллектуального анализа данных** со списком всех структур интеллектуального анализа данных, существующих в текущем проекте.</span><span class="sxs-lookup"><span data-stu-id="10dd4-117">The **Select Mining Model** dialog box opens to show all the mining structures that exist in the current project.</span></span>  
  
     <span data-ttu-id="10dd4-118">Выберите модель, которую необходимо использовать в прогнозе.</span><span class="sxs-lookup"><span data-stu-id="10dd4-118">Select the model that you want to use for creating a prediction.</span></span>  
  
     <span data-ttu-id="10dd4-119">Например, для создания образца кода, показанного в начале этого раздела, выберите TM_Decision_Tree, затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="10dd4-119">For example, to create the sample code shown at the start of this topic, select TM_Decision_Tree, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="10dd4-120">Нажмите на панели инструментов вкладки **Прогноз модели интеллектуального анализа данных** кнопку **Одноэлементный запрос** .</span><span class="sxs-lookup"><span data-stu-id="10dd4-120">Click **Singleton query** on the toolbar of the **Mining Model Prediction** tab.</span></span>  
  
     <span data-ttu-id="10dd4-121">На вкладке появится таблица **Ввод одноэлементного запроса** , столбцы в которой автоматически сопоставляются со столбцами в таблице **Модель интеллектуального анализа данных** .</span><span class="sxs-lookup"><span data-stu-id="10dd4-121">The **Singleton Query Input** table appears on the tab, with the columns automatically mapped to the columns in the **Mining Model** table.</span></span>  
  
4.  <span data-ttu-id="10dd4-122">В таблице **Ввод одноэлементного запроса** выберите в столбце **Значение** значения, описывающие объект, для которого необходимо создать прогноз.</span><span class="sxs-lookup"><span data-stu-id="10dd4-122">On the **Singleton Query Input** table, select values in the **Value** column to describe the case for which you want to create a prediction.</span></span>  
  
     <span data-ttu-id="10dd4-123">Например, выберите **2** для **числа детей дома**, а затем введите `45` в качестве значения **Age**.</span><span class="sxs-lookup"><span data-stu-id="10dd4-123">For example, select **2** for **Number Children At Home**, and then type `45` for **Age**.</span></span>  
  
5.  <span data-ttu-id="10dd4-124">Перетащите прогнозируемый столбец из таблицы **модель интеллектуального анализа данных** в **Исходный** столбец в нижней части вкладки. при необходимости можно ввести псевдоним для столбца.</span><span class="sxs-lookup"><span data-stu-id="10dd4-124">Drag a predictable column from the **Mining Model** table to the **Source** column at the bottom of the tab. Optionally, you can type an alias for the column.</span></span>  
  
     <span data-ttu-id="10dd4-125">Например, перетащите **Bike Buyer** в столбец **Источник** .</span><span class="sxs-lookup"><span data-stu-id="10dd4-125">For example, drag **Bike Buyer** to the **Source** column.</span></span>  
  
6.  <span data-ttu-id="10dd4-126">Выберите из раскрывающегося списка в столбце **Источник** пункт **Прогнозирующая функция** или **Пользовательское выражение** и добавьте дополнительные функции к запросу.</span><span class="sxs-lookup"><span data-stu-id="10dd4-126">Add any additional functions to the query by selecting **Prediction Function** or **Custom Expression** from the drop-down list in the **Source** column.</span></span>  
  
     <span data-ttu-id="10dd4-127">Например, выберите **Прогнозирующая функция**, затем выберите функцию **PredictProbability**.</span><span class="sxs-lookup"><span data-stu-id="10dd4-127">For example, click **Prediction Function**, and select **PredictProbability**.</span></span>  
  
7.  <span data-ttu-id="10dd4-128">Щелкните **Критерий или аргумент** в строке **PredictProbability** , затем введите имя столбца для прогнозирования и, при необходимости, укажите конкретное значение для прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="10dd4-128">Click **Criteria/Argument** in the **PredictProbability** row, and type the name of the column to predict, and optionally a specific value to predict.</span></span>  
  
     <span data-ttu-id="10dd4-129">Например, введите `[Bike Buyer], 1`.</span><span class="sxs-lookup"><span data-stu-id="10dd4-129">For example, type `[Bike Buyer], 1`.</span></span>  
  
8.  <span data-ttu-id="10dd4-130">Щелкните поле **Псевдоним** в строке **PredictProbability** , затем введите имя для ссылки на новый столбец.</span><span class="sxs-lookup"><span data-stu-id="10dd4-130">Click the **Alias** box in the **PredictProbability** row, and type a name to refer to the new column.</span></span>  
  
     <span data-ttu-id="10dd4-131">Например, введите `ProbableBuyer`.</span><span class="sxs-lookup"><span data-stu-id="10dd4-131">For example, type `ProbableBuyer`.</span></span>  
  
9. <span data-ttu-id="10dd4-132">Нажмите на панели инструментов вкладки **Прогноз модели интеллектуального анализа данных** кнопку **Переключение в режим просмотра результата запроса** .</span><span class="sxs-lookup"><span data-stu-id="10dd4-132">Click **Switch to query result view** on the toolbar of the **Mining Model Prediction** tab.</span></span>  
  
     <span data-ttu-id="10dd4-133">Откроется новый экран, в котором отобразится результат запроса.</span><span class="sxs-lookup"><span data-stu-id="10dd4-133">A new screen opens to show the result of the query.</span></span> <span data-ttu-id="10dd4-134">Чтобы просмотреть созданную DMX-инструкцию, щелкните **SQL**.</span><span class="sxs-lookup"><span data-stu-id="10dd4-134">To view the DMX statement that you just created, click **SQL**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10dd4-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="10dd4-135">See Also</span></span>  
 [<span data-ttu-id="10dd4-136">Прогнозирующие запросы (интеллектуальный анализ данных)</span><span class="sxs-lookup"><span data-stu-id="10dd4-136">Prediction Queries &#40;Data Mining&#41;</span></span>](prediction-queries-data-mining.md)  
  
  
