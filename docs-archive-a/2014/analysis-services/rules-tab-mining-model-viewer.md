---
title: Вкладка "правила" (средство просмотра моделей интеллектуального анализа данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.associationrules.rules.f1
ms.assetid: 705d5492-b58f-45d9-94d7-ed57b7025823
author: minewiskan
ms.author: owend
ms.openlocfilehash: d0d86931865fd9352074669de93b14dacfc84537
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656639"
---
# <a name="rules-tab-mining-model-viewer"></a><span data-ttu-id="66254-102">Вкладка «Правила» (средство просмотра моделей интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="66254-102">Rules Tab (Mining Model Viewer)</span></span>
  <span data-ttu-id="66254-103">Используйте панель **Правила** в модели взаимосвязей для просмотра правил, извлеченных алгоритмом из данных.</span><span class="sxs-lookup"><span data-stu-id="66254-103">Use the **Rules** pane in an association model to view the rules that the algorithm extracted from the data.</span></span> <span data-ttu-id="66254-104">Правила описывают взаимосвязи между элементами и могут использоваться для создания рекомендаций.</span><span class="sxs-lookup"><span data-stu-id="66254-104">Rules describe how items are related to each other, and can be used to create recommendations.</span></span>  
  
 <span data-ttu-id="66254-105">Можно использовать параметры в средстве просмотра, чтобы фильтровать количество правил, отображаемых в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="66254-105">You can use the options in the viewer to filter the number of rules that are displayed in the viewer.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="66254-106">По умолчанию только правила, превышающие порог вероятности, определенный в параметре **Минимальная вероятность** , отображаются в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="66254-106">By default, only the rules that are above the probability threshold defined in **Minimum probability** are displayed in the viewer.</span></span> <span data-ttu-id="66254-107">Это значение нельзя уменьшить с использованием средства просмотра, так как порог вероятности для вывода правил определяется при создании модели.</span><span class="sxs-lookup"><span data-stu-id="66254-107">You cannot make this value any smaller by using the viewer, because the probability threshold for rule output is determined when the model is created.</span></span> <span data-ttu-id="66254-108">Дополнительные сведения см. в разделе [Технический справочник по алгоритму взаимосвязей (Майкрософт)](data-mining/microsoft-association-algorithm-technical-reference.md).</span><span class="sxs-lookup"><span data-stu-id="66254-108">For more information, see [Microsoft Association Algorithm Technical Reference](data-mining/microsoft-association-algorithm-technical-reference.md).</span></span>  
  
 <span data-ttu-id="66254-109">**Дополнительные сведения:** [Алгоритм взаимосвязей (Майкрософт)](data-mining/microsoft-association-algorithm.md), [Просмотр модели с помощью средства просмотра правил взаимосвязи (Майкрософт)](data-mining/browse-a-model-using-the-microsoft-association-rules-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="66254-109">**For More Information:** [Microsoft Association Algorithm](data-mining/microsoft-association-algorithm.md), [Browse a Model Using the Microsoft Association Rules Viewer](data-mining/browse-a-model-using-the-microsoft-association-rules-viewer.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="66254-110">Варианты</span><span class="sxs-lookup"><span data-stu-id="66254-110">Options</span></span>  
 <span data-ttu-id="66254-111">**Обновить содержимое средства просмотра**</span><span class="sxs-lookup"><span data-stu-id="66254-111">**Refresh viewer content**</span></span>  
 <span data-ttu-id="66254-112">Перезагрузить модель интеллектуального анализа данных в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="66254-112">Reload the mining model in the viewer.</span></span>  
  
 <span data-ttu-id="66254-113">**Модель интеллектуального анализа данных**</span><span class="sxs-lookup"><span data-stu-id="66254-113">**Mining Model**</span></span>  
 <span data-ttu-id="66254-114">Выберите для просмотра модель интеллектуального анализа данных, содержащуюся в текущей структуре интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="66254-114">Choose a mining model to view that is contained in the current mining structure.</span></span> <span data-ttu-id="66254-115">Модель интеллектуального анализа данных открывается в связанном средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="66254-115">The mining model will open in its associated viewer.</span></span>  
  
 <span data-ttu-id="66254-116">**Зритель**</span><span class="sxs-lookup"><span data-stu-id="66254-116">**Viewer**</span></span>  
 <span data-ttu-id="66254-117">Выберите средство просмотра, используемое для выбранной модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="66254-117">Choose a viewer to use to view the selected mining model.</span></span> <span data-ttu-id="66254-118">Для каждого типа модели интеллектуального анализа данных можно использовать пользовательское средство просмотра или **средство просмотра деревьев содержимого общего вида (Майкрософт)**.</span><span class="sxs-lookup"><span data-stu-id="66254-118">You can use the custom viewer for each mining model, or the **Microsoft Generic Content Tree Viewer**.</span></span> <span data-ttu-id="66254-119">Также можно использовать подключаемые модули просмотра, если они доступны.</span><span class="sxs-lookup"><span data-stu-id="66254-119">You can also use plug-in viewers if available.</span></span>  
  
 <span data-ttu-id="66254-120">**Минимальная вероятность**</span><span class="sxs-lookup"><span data-stu-id="66254-120">**Minimum probability**</span></span>  
 <span data-ttu-id="66254-121">Измените это значение, чтобы задать минимальную вероятность, необходимую для отображения правила в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="66254-121">Change this value to set the minimum probability required for a rule to be displayed in the viewer.</span></span> <span data-ttu-id="66254-122">Увеличение значения вероятности сократит количество правил, которые будут отображаться.</span><span class="sxs-lookup"><span data-stu-id="66254-122">Increasing the value for probability will reduce the number of rules that are displayed.</span></span>  
  
 <span data-ttu-id="66254-123">**Минимальная важность**</span><span class="sxs-lookup"><span data-stu-id="66254-123">**Minimum importance**</span></span>  
 <span data-ttu-id="66254-124">Измените это значение, чтобы задать минимальную важность, необходимую для отображения правила в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="66254-124">Change this value to set the minimum importance required for a rule to be displayed in the viewer.</span></span> <span data-ttu-id="66254-125">Увеличение значения важности сократит количество правил, которые будут отображаться.</span><span class="sxs-lookup"><span data-stu-id="66254-125">Increasing the value for importance will reduce the number of rules that are displayed.</span></span>  
  
 <span data-ttu-id="66254-126">**Правило фильтра**</span><span class="sxs-lookup"><span data-stu-id="66254-126">**Filter Rule**</span></span>  
 <span data-ttu-id="66254-127">Введите строковое значение для фильтрации количества правил, отображаемых в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="66254-127">Type a string value to filter the number of rules that appear in the viewer.</span></span>  
  
 <span data-ttu-id="66254-128">Можно также ввести регулярные выражения .NET как критерии фильтра.</span><span class="sxs-lookup"><span data-stu-id="66254-128">You can also type .NET regular expressions as filter criteria.</span></span> <span data-ttu-id="66254-129">Например, следующее выражение возвращает все правила, содержащие «Road Bottle Cage» в левой стороне правила:</span><span class="sxs-lookup"><span data-stu-id="66254-129">For example, the following expression returns all rules that contain 'Road Bottle Cage' on the left side of the rule:</span></span>  
  
 `\bRoad\b.\bBottle\b.\bCage\b.*->.*`  
  
 <span data-ttu-id="66254-130">Обратите внимание, что, возможно, потребуется обновить представление, чтобы увидеть применяемые критерии фильтра.</span><span class="sxs-lookup"><span data-stu-id="66254-130">Note that you might need to refresh the view to see the filter criteria apply.</span></span> <span data-ttu-id="66254-131">Чтобы обновить список, можно включать и отключать параметр **Показывать длинное имя** .</span><span class="sxs-lookup"><span data-stu-id="66254-131">You can also toggle the **Show long name** option on and off to refresh the list.</span></span>  
  
 <span data-ttu-id="66254-132">По умолчанию критерии фильтра применяются к полному имени сочетания «атрибут-значение», поэтому при просмотре только имени атрибута не всегда ясно, что критерии фильтра применены верно.</span><span class="sxs-lookup"><span data-stu-id="66254-132">By default the filter criteria applies to the full name of the attribute-value combination; therefore, if you are viewing the attribute name only, it might not be obvious that the filter criteria has applied correctly.</span></span> <span data-ttu-id="66254-133">Используйте раскрывающийся список **Отображать** , чтобы выбрать пункт **Отобразить имя и значение атрибута**и проверить правильность фильтрации списка наборов элементов.</span><span class="sxs-lookup"><span data-stu-id="66254-133">Use the **Show** dropdown list to select **Show attribute name and value**, and verify that the list of itemsets is filtered correctly.</span></span>  
  
 <span data-ttu-id="66254-134">**Показать**</span><span class="sxs-lookup"><span data-stu-id="66254-134">**Show**</span></span>  
 <span data-ttu-id="66254-135">Настройте способ отображения правила в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="66254-135">Adjust the way that the rule is displayed in the viewer.</span></span> <span data-ttu-id="66254-136">Можно выбрать один из трех параметров:</span><span class="sxs-lookup"><span data-stu-id="66254-136">You can select one of the three following options:</span></span>  
  
-   <span data-ttu-id="66254-137">Показывать имя и значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="66254-137">Show the attribute name and value</span></span>  
  
-   <span data-ttu-id="66254-138">Показывать только значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="66254-138">Show the attribute value only</span></span>  
  
-   <span data-ttu-id="66254-139">Показывать только имя атрибута.</span><span class="sxs-lookup"><span data-stu-id="66254-139">Show the attribute name only</span></span>  
  
 <span data-ttu-id="66254-140">**Показывать длинное имя**</span><span class="sxs-lookup"><span data-stu-id="66254-140">**Show long name**</span></span>  
 <span data-ttu-id="66254-141">Показывать полное имя правила в том виде, в каком оно отображается в содержимом модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="66254-141">Show the full name of the rule as it appears in the mining model content.</span></span>  
  
 <span data-ttu-id="66254-142">**Максимальное число строк**</span><span class="sxs-lookup"><span data-stu-id="66254-142">**Maximum rows**</span></span>  
 <span data-ttu-id="66254-143">Ограничьте число правил, отображаемых в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="66254-143">Limit the number of rules that are displayed in the viewer.</span></span>  
  
 <span data-ttu-id="66254-144">**Вероятность**</span><span class="sxs-lookup"><span data-stu-id="66254-144">**Probability**</span></span>  
 <span data-ttu-id="66254-145">Этот столбец в диаграмме показывает вероятность для каждого правила.</span><span class="sxs-lookup"><span data-stu-id="66254-145">This column in the chart displays the probability for each rule.</span></span>  
  
 <span data-ttu-id="66254-146">Чтобы упорядочить по вероятности, щелкните заголовок столбца.</span><span class="sxs-lookup"><span data-stu-id="66254-146">You can click the column heading to sort by probability.</span></span>  
  
 <span data-ttu-id="66254-147">**Важность**</span><span class="sxs-lookup"><span data-stu-id="66254-147">**Importance**</span></span>  
 <span data-ttu-id="66254-148">Этот столбец в таблице показывает важность для каждого правила.</span><span class="sxs-lookup"><span data-stu-id="66254-148">This column in the chart displays the importance for each rule.</span></span>  
  
 <span data-ttu-id="66254-149">Чтобы упорядочить по важности, щелкните заголовок столбца.</span><span class="sxs-lookup"><span data-stu-id="66254-149">You can click the column heading to sort by importance.</span></span>  
  
 <span data-ttu-id="66254-150">**Правило**</span><span class="sxs-lookup"><span data-stu-id="66254-150">**Rule**</span></span>  
 <span data-ttu-id="66254-151">В этом столбце таблицы отображается текстовое описание каждого правила в соответствии с форматом, заданным параметрами **Отображать** и **Показывать длинное имя**.</span><span class="sxs-lookup"><span data-stu-id="66254-151">This column in the chart displays the text description for each rule, according to the format specified by using the options, **Show** and **Show long name**.</span></span>  
  
 <span data-ttu-id="66254-152">Чтобы сортировать по тексту правила, щелкните заголовок столбца.</span><span class="sxs-lookup"><span data-stu-id="66254-152">You can click the column heading to sort by the text of the rule.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66254-153">См. также:</span><span class="sxs-lookup"><span data-stu-id="66254-153">See Also</span></span>  
 <span data-ttu-id="66254-154">[Алгоритмы интеллектуального анализа данных &#40;Analysis Services — интеллектуальный анализ данных&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="66254-154">[Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="66254-155">[Средства просмотра моделей интеллектуального анализа &#40;конструктор моделей интеллектуального анализа данных&#41;](mining-model-viewers-data-mining-model-designer.md) </span><span class="sxs-lookup"><span data-stu-id="66254-155">[Mining Model Viewers &#40;Data Mining Model Designer&#41;](mining-model-viewers-data-mining-model-designer.md) </span></span>  
 [<span data-ttu-id="66254-156">Средства просмотра моделей интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="66254-156">Data Mining Model Viewers</span></span>](data-mining/data-mining-model-viewers.md)  
  
  
