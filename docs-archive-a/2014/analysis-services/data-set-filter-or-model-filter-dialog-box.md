---
title: Диалоговое окно «Фильтр набора данных» или «фильтр модели» | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a9602174-b7e2-4e16-8ded-dfd8eb9264d7
author: minewiskan
ms.author: owend
ms.openlocfilehash: afa796cd8cb23894c059deba411b3e1d6676e3b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733318"
---
# <a name="data-set-filter-or-model-filter-dialog-box"></a><span data-ttu-id="7b623-102">Диалоговое окно "Фильтр набора данных" или "Фильтр модели"</span><span class="sxs-lookup"><span data-stu-id="7b623-102">Data Set Filter or Model Filter Dialog Box</span></span>
  <span data-ttu-id="7b623-103">Это диалоговое окно позволяет создавать фильтры, которые можно применить к набору данных.</span><span class="sxs-lookup"><span data-stu-id="7b623-103">This dialog box helps you build the filters that you can apply to a data set.</span></span>  <span data-ttu-id="7b623-104">Набор данных может быть внешним набором данных, используемых для проверки, или данными варианта для модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="7b623-104">The data set can be an external data set used for testing, or the case data for a mining model.</span></span> <span data-ttu-id="7b623-105">Имя диалогового окна изменяется в зависимости от того, предназначен ли фильтр для внешнего набора данных или для модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="7b623-105">The name of the dialog box changes depending on whether the filter is for an external data set or for a mining model.</span></span>  
  
 <span data-ttu-id="7b623-106">Если к новому набору данных применяется фильтр, модель интеллектуального анализа данных оценивается с помощью только тех вариантов набора данных, которые удовлетворяют заданным критериям.</span><span class="sxs-lookup"><span data-stu-id="7b623-106">If you apply the filter to a new data set, the data mining model is evaluated by using only those cases in the data set that meet the conditions.</span></span> <span data-ttu-id="7b623-107">Если фильтр применяется к самой модели интеллектуального анализа данных, обучение и проверка модели осуществляется с помощью только тех вариантов существующего набора проверочных данных, которые удовлетворяют критериям фильтрации.</span><span class="sxs-lookup"><span data-stu-id="7b623-107">If you apply the filter to the mining model itself, the model will be trained and tested by using only the cases in the existing test data set that meet the filter criteria.</span></span>  
  
-   <span data-ttu-id="7b623-108">Вызвать диалоговое окно **Фильтр набора данных** можно с вкладки **Выбор входа** конструктора **Диаграмма точности интеллектуального анализа данных** .</span><span class="sxs-lookup"><span data-stu-id="7b623-108">The **Data Set Filter** dialog box is available from the **Input Selection** tab of the **Mining Accuracy Chart** designer.</span></span>  
  
-   <span data-ttu-id="7b623-109">Диалоговое окно **Фильтр модели** можно вызвать с вкладки **Модели интеллектуального анализа данных** конструктора интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="7b623-109">The **Model Filter** dialog box is available from the **Mining Models** tab of the Data Miningdesigner.</span></span>  
  
-   <span data-ttu-id="7b623-110">Сетка **Условия** содержит столбцы, в которых можно указать имя таблицы или столбца, оператор и целевые значения.</span><span class="sxs-lookup"><span data-stu-id="7b623-110">The **Conditions** grid contains columns where you can specify a table or column name, an operator, and target values.</span></span> <span data-ttu-id="7b623-111">Использование этой сетки является, по сути, созданием предложения WHERE.</span><span class="sxs-lookup"><span data-stu-id="7b623-111">By using this grid you are essentially creating a WHERE clause.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="7b623-112"> Чтобы проверить точность на подмножестве исходных обучающих данных, можно добавить представление источников данных, используемое для определения обучающего набора, в виде внешних проверочных данных, после чего добавить условия в сетке **Фильтр набора данных** .</span><span class="sxs-lookup"><span data-stu-id="7b623-112">To test accuracy on a subset of the original training data, you can add the data source view that was used to define the training set as the external testing data, and then add conditions in the **Data Set Filter** grid.</span></span>  
  
 <span data-ttu-id="7b623-113">**Дополнительные сведения:** [Тестирование и проверка (интеллектуальный анализ данных)](data-mining/testing-and-validation-data-mining.md)</span><span class="sxs-lookup"><span data-stu-id="7b623-113">**For more information:** [Testing and Validation &#40;Data Mining&#41;](data-mining/testing-and-validation-data-mining.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="7b623-114">Варианты</span><span class="sxs-lookup"><span data-stu-id="7b623-114">Options</span></span>  
 <span data-ttu-id="7b623-115">**Условия**</span><span class="sxs-lookup"><span data-stu-id="7b623-115">**Conditions**</span></span>  
 <span data-ttu-id="7b623-116">Отображает имена таблиц, за которыми следуют имена столбцов с условиями.</span><span class="sxs-lookup"><span data-stu-id="7b623-116">Displays table names, followed by column names with conditions.</span></span>  
  
|<span data-ttu-id="7b623-117">Значение</span><span class="sxs-lookup"><span data-stu-id="7b623-117">Value</span></span>|<span data-ttu-id="7b623-118">Описание</span><span class="sxs-lookup"><span data-stu-id="7b623-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7b623-119">**И (или)**</span><span class="sxs-lookup"><span data-stu-id="7b623-119">**And/Or**</span></span>|<span data-ttu-id="7b623-120">Выберите оператор для соединения нескольких условий.</span><span class="sxs-lookup"><span data-stu-id="7b623-120">Choose an operator to join multiple conditions.</span></span>|  
|<span data-ttu-id="7b623-121">**Столбец структуры интеллектуального анализа данных**</span><span class="sxs-lookup"><span data-stu-id="7b623-121">**Mining Structure Column**</span></span>|<span data-ttu-id="7b623-122">Нажмите, чтобы выбрать источник данных, затем щелкните последующие строки сетки, чтобы добавить столбцы из источника данных.</span><span class="sxs-lookup"><span data-stu-id="7b623-122">Click to select a data source, and then click successive lines in the grid to add columns from the data source.</span></span><br /><br /> <span data-ttu-id="7b623-123">В первой строке сетки указано представление источника данных.</span><span class="sxs-lookup"><span data-stu-id="7b623-123">The first line in the grid specifies the data source view.</span></span> <span data-ttu-id="7b623-124">После того как выбрано представление источника данных, в поле **Столбец структуры интеллектуального анализа данных** отображается значок таблицы, а в поле **Значение** отображается сочетание всех критериев, определенных для этого источника данных.</span><span class="sxs-lookup"><span data-stu-id="7b623-124">After you select a data source view, **Mining Structure Column** displays a table icon, and the **Value** field displays the combination of all criteria that you have defined for this data source.</span></span><br /><br /> <span data-ttu-id="7b623-125">После выбора источника данных поле **Столбец структуры интеллектуального анализа данных** содержит раскрывающийся список отдельных столбцов этого источника данных.</span><span class="sxs-lookup"><span data-stu-id="7b623-125">After you have selected a data source, the **Mining Structure Column** box provides a dropdown list of individual columns in the data source.</span></span>|  
|<span data-ttu-id="7b623-126">**Оператор**</span><span class="sxs-lookup"><span data-stu-id="7b623-126">**Operator**</span></span>|<span data-ttu-id="7b623-127">Выберите оператор из списка.</span><span class="sxs-lookup"><span data-stu-id="7b623-127">Select an operator from the list.</span></span>|  
|<span data-ttu-id="7b623-128">**Значение**</span><span class="sxs-lookup"><span data-stu-id="7b623-128">**Value**</span></span>|<span data-ttu-id="7b623-129">Для таблиц в поле **Значение** отображается сочетание всех фильтров, применяемых к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="7b623-129">For tables, the **Value** field shows the combination of all filters applied to the data source.</span></span> <span data-ttu-id="7b623-130">Можно также нажать кнопку Построить **(...)** справа от текстового поля, чтобы открыть диалоговое окно **Фильтр** и построить условие.</span><span class="sxs-lookup"><span data-stu-id="7b623-130">You can also click the build **(...)** button at the right of the text box to open the **Filter** dialog box and build a condition.</span></span>|  
  
 <span data-ttu-id="7b623-131">**Выражение**</span><span class="sxs-lookup"><span data-stu-id="7b623-131">**Expression**</span></span>  
 <span data-ttu-id="7b623-132">Отображает набор критериев, построенных с помощью сетки.</span><span class="sxs-lookup"><span data-stu-id="7b623-132">Displays the set of criteria that you built by using the grid.</span></span>  
  
 <span data-ttu-id="7b623-133">**Изменить запрос**</span><span class="sxs-lookup"><span data-stu-id="7b623-133">**Edit Query**</span></span>  
 <span data-ttu-id="7b623-134">Меняет режим изменения фильтра, позволяя вводить критерий фильтра непосредственно в текстовое поле **Выражение** .</span><span class="sxs-lookup"><span data-stu-id="7b623-134">Changes the filter editing mode so that you can type a filter expression directly in the **Expression** text box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7b623-135">После внесения изменений в критерий фильтра вручную вы не сможете вернуться в режим правки сетки даже после сохранения выражения в поле **критерий фильтра** на вкладке **Выбор входа** . Если требуется построить выражение с помощью сетки, необходимо удалить существующее выражение фильтра и начать заново.</span><span class="sxs-lookup"><span data-stu-id="7b623-135">After you have made manual changes to the filter expression, you cannot return to grid edit mode, even after you have saved the expression in the **Filter Expression** box on the **Input Selection** tab. If you want to build an expression by using the grid, you must delete the existing filter expression and start over.</span></span>  
  
 <span data-ttu-id="7b623-136">**Сбросить изменения запроса**</span><span class="sxs-lookup"><span data-stu-id="7b623-136">**Revert Query Edits**</span></span>  
 <span data-ttu-id="7b623-137">Восстанавливает прежнее состояние сетки и отменяет все изменения, внесенные в критерий фильтра.</span><span class="sxs-lookup"><span data-stu-id="7b623-137">Restores the grid to its previous state and cancels any changes that you made to the filter expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b623-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="7b623-138">See Also</span></span>  
 <span data-ttu-id="7b623-139">[Задачи тестирования и проверки и инструкции &#40;&#41;интеллектуального анализа данных](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="7b623-139">[Testing and Validation Tasks and How-tos &#40;Data Mining&#41;](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span></span>  
 [<span data-ttu-id="7b623-140">Конструктор диаграмм точности интеллектуального анализа &#40;&#41;интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="7b623-140">Mining Accuracy Chart Designer &#40;Data Mining&#41;</span></span>](mining-accuracy-chart-designer-data-mining.md)  
  
  
