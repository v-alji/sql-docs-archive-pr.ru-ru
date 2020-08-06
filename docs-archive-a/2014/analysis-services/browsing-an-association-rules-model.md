---
title: Просмотр модели правил взаимосвязей | Документация Майкрософт
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, browsing
- mining model, association
- mining models, viewing
- association [data mining]
ms.assetid: faffe208-7a64-4ec6-825f-ecbaa79caff7
author: minewiskan
ms.author: owend
ms.openlocfilehash: de5adbca264fff81b44424d865a2c8201a6fdfc3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656811"
---
# <a name="browsing-an-association-rules-model"></a><span data-ttu-id="c2f9e-102">Просмотр модели правил взаимосвязей</span><span class="sxs-lookup"><span data-stu-id="c2f9e-102">Browsing an Association Rules Model</span></span>
  <span data-ttu-id="c2f9e-103">При открытии модели взаимосвязей с помощью **кнопки Обзор**модель отображается в интерактивном средстве просмотра, подобно средству просмотра правил взаимосвязи в среде [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c2f9e-103">When you open an association model using **Browse**, the model is displayed in an interactive viewer, similar to the Association Rules Viewer in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  <span data-ttu-id="c2f9e-104">Средство просмотра позволяет быстро узнать, какие элементы коррелировали друг с другом, и отображает правила, применимые для прогнозов и рекомендаций.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-104">The viewer lets you see at a glance which items were correlated with each other, and displays rules that you can use for prediction or making recommendations.</span></span>  
  
##  <a name="explore-the-model"></a><a name="BKMK_ViewerTabs"></a><span data-ttu-id="c2f9e-105">Изучение модели</span><span class="sxs-lookup"><span data-stu-id="c2f9e-105">Explore the Model</span></span>  
 <span data-ttu-id="c2f9e-106">При открытии модели интеллектуального анализа данных, созданной с помощью [!INCLUDE[msCoName](../includes/msconame-md.md)] алгоритма правил взаимосвязей, окно **Обзор** содержит следующие представления, разработанные для просмотра различных аспектов модели.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-106">When you open a mining model that was created using the [!INCLUDE[msCoName](../includes/msconame-md.md)] Association Rules algorithm, the **Browse** window includes the following views, each designed to let you explore a different aspect of the model:</span></span>  
  
-   [<span data-ttu-id="c2f9e-107">Наборы элементов</span><span class="sxs-lookup"><span data-stu-id="c2f9e-107">Itemsets</span></span>](#BKMK_Itemsets)  
  
-   [<span data-ttu-id="c2f9e-108">Правила</span><span class="sxs-lookup"><span data-stu-id="c2f9e-108">Rules</span></span>](#BKMK_Rules)  
  
-   [<span data-ttu-id="c2f9e-109">Сеть зависимостей</span><span class="sxs-lookup"><span data-stu-id="c2f9e-109">Dependency Net</span></span>](#BKMK_Dependency)  
  
 <span data-ttu-id="c2f9e-110">Запишите параметр на каждой вкладке, чтобы **отображалось длинное имя** .</span><span class="sxs-lookup"><span data-stu-id="c2f9e-110">Take note of the option on each tab, **Show long name** .</span></span> <span data-ttu-id="c2f9e-111">С его помощью можно отобразить или скрыть таблицу, из которой образовывается набор элементов, и сократить или удлинить имя правила или набора элементов.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-111">By selecting this option, you can show or hide the table from which the itemset originates, and shorten or lengthen the name of the rule or itemset.</span></span> <span data-ttu-id="c2f9e-112">Эта возможность особенно полезна в тех случаях, когда данные вариантов и данные атрибутов берутся из разных источников.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-112">This option is particularly useful when your case data and attribute data are from different data sources.</span></span>  
  
 <span data-ttu-id="c2f9e-113">Для экспериментов с моделью взаимосвязей можно использовать образцы данных на вкладке «Взаимосвязи» книги с образцами данных и построить модель взаимосвязей, не меняя значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-113">To experiment with an association model, you can use the sample data on the Associate tab of the sample data workbook, and build an association model using all the defaults.</span></span> <span data-ttu-id="c2f9e-114">Вы также можете создать модель анализа покупательской корзины и открыть ее с помощью **кнопки Обзор**.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-114">You can also build a Shopping Basket Analysis model and open that using **Browse**.</span></span>  
  
###  <a name="itemsets"></a><a name="BKMK_Itemsets"></a><span data-ttu-id="c2f9e-115">Создаваем</span><span class="sxs-lookup"><span data-stu-id="c2f9e-115">Itemsets</span></span>  
 <span data-ttu-id="c2f9e-116">Вкладка **наборы элементов** — хорошее место для начала изучения модели взаимосвязей.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-116">The **Itemsets** tab is a good place to begin exploring an association model.</span></span> <span data-ttu-id="c2f9e-117">На этой вкладке отображается список элементов, которые модель часто обнаруживает совместно.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-117">This tab shows a list of the items that the model frequently found together.</span></span>  
  
 <span data-ttu-id="c2f9e-118">![Список элементов в модели взаимосвязей](media/dm13-association-itemsets.gif "Список элементов в модели взаимосвязей")</span><span class="sxs-lookup"><span data-stu-id="c2f9e-118">![List of items in an association model](media/dm13-association-itemsets.gif "List of items in an association model")</span></span>  
  
 <span data-ttu-id="c2f9e-119">Самый типичный пример наборов элементов — это модель покупательского поведения, где набор элементов представляет пары или наборы товаров, которые клиенты покупают одновременно.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-119">The most common example of itemsets is in a shopping basket model, where an itemset represents pairs or sets of products that lots of customers purchase at the same time.</span></span> <span data-ttu-id="c2f9e-120">Тем не менее в зависимости от того, как сгруппированы и упорядочены элементы, набор элементов может содержать, допустим, последовательность кинофильмов, которые пользователи заказывают за определенный период времени, или событий, происходящих в конкретном месте.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-120">However, depending on how you group and order your items, the itemset might contain a sequence of movies that customers order over a period of time, or events that tend to occur in  a particular location.</span></span>  
  
 <span data-ttu-id="c2f9e-121">Набор *элементов* может содержать как минимум один элемент с двумя, три или, однако, многие задаются в качестве максимального размера набора элементов для модели.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-121">An *itemset* can contain as few as one item to two, three, or however, many is set as the maximum itemset size for the model.</span></span> <span data-ttu-id="c2f9e-122">Для каждого набора элементов средство просмотра отображает *поддержку*, *вероятность*и *Размер*набора элементов.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-122">For each itemset, the viewer displays the itemset  *support*,  *probability*, and *size*.</span></span> <span data-ttu-id="c2f9e-123">Несущее множество и вероятность — это основные показатели статистики, используемые для ранжирования наборов элементов и правил, сформированных моделью взаимосвязей.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-123">Support and probability are the principal statistics used to rank the itemsets and rules generated by an association model.</span></span> <span data-ttu-id="c2f9e-124">Эти значения также используются для подсчета и описания их важности.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-124">These values are also used to calculate and describe their importance.</span></span>  
  
 <span data-ttu-id="c2f9e-125">**Поддержка**.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-125">**Support**.</span></span> <span data-ttu-id="c2f9e-126">Несущее множество означает максимальное количество вариантов или строк входных данных, в которых присутствует элемент.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-126">Support means the number of cases or rows of input data that have this item.</span></span> <span data-ttu-id="c2f9e-127">Например, если набор элементов содержит два элемента, которые находятся в корзине для покупок, число в столбце **support** показывает, сколько раз в источнике данных произошло сочетание элементов.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-127">For example, if an itemset contains two items that are found in a shopping cart, the number in the **Support** column indicates how many times that combination of items occurred in the source data.</span></span>  
  
 <span data-ttu-id="c2f9e-128">**Размер**.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-128">**Size**.</span></span> <span data-ttu-id="c2f9e-129">Изменяя размер набора элементов, можно контролировать длину списков наборов элементов.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-129">By changing itemset size, you can control the length of the lists of itemsets.</span></span> <span data-ttu-id="c2f9e-130">Если вы не хотите видеть отдельные продукты в списке, измените параметр, **Минимальный размер набора элементов**, на 2 или более.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-130">If you don't want to see single products in the list, change the option, **Minimum itemset size**, to 2 or more.</span></span>  <span data-ttu-id="c2f9e-131">Ограничение списка путем увеличения минимального размера наборов элементов позволяет выявлять весьма специализированные шаблоны.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-131">Restricting the list by increasing the minimum size of itemsets lets you look for very specific patterns.</span></span> <span data-ttu-id="c2f9e-132">Необходимость в этом может возникнуть при работе с очень крупным набором данных.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-132">This might be useful if you are working with a very large set of data.</span></span>  
  
 <span data-ttu-id="c2f9e-133">Количество наборов элементов, отображаемых на вкладке, можно отфильтровать, изменив **минимальное значение поддержки** и **Максимальное число строк** .</span><span class="sxs-lookup"><span data-stu-id="c2f9e-133">You can filter the number of itemsets that are displayed in the tab by changing the **Minimum support** and **Maximum rows** values.</span></span> <span data-ttu-id="c2f9e-134">Если увеличить минимальное значение **поддержки** , в списке будет показано меньше наборов элементов, но наборы элементов будут более распространенными в входных данных.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-134">If you increase the **Minimum Support** value, the list will show fewer itemsets, but the itemsets will be the more common ones in the input data.</span></span> <span data-ttu-id="c2f9e-135">Независимо от того, является ли общий вопрос важным, вы можете ознакомиться с помощью вкладки **правила** .</span><span class="sxs-lookup"><span data-stu-id="c2f9e-135">Whether common is the same as important is another question, which you can explore using the **Rules** tab.</span></span>  
  
 <span data-ttu-id="c2f9e-136">Обратите внимание, что изменение значения поддержки или других элементов управления на вкладке **наборы элементов** изменяет только отображаемые элементы и не влияет на базовую модель.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-136">Note that changing the support value or other controls on the **Itemsets** tab only changes the items that are displayed, and does not affect the underlying model.</span></span> <span data-ttu-id="c2f9e-137">Если необходимо создать меньше наборов элементов или ограничить их размер, следует использовать параметры `MINIMUM_SUPPORT` и `MAXIMUM_SUPPORT` , доступные в диалоговом окне **Параметры алгоритма** .</span><span class="sxs-lookup"><span data-stu-id="c2f9e-137">If you want to generate fewer or more itemsets, or limit their size, you should use the parameters, `MINIMUM_SUPPORT` and `MAXIMUM_SUPPORT`, available in the **Algorithm Parameters** dialog box.</span></span>  
  
##### <a name="explore-the-itemsets-list"></a><span data-ttu-id="c2f9e-138">Просмотр списка наборов элементов</span><span class="sxs-lookup"><span data-stu-id="c2f9e-138">Explore the itemsets list</span></span>  
  
1.  <span data-ttu-id="c2f9e-139">Щелкните столбец **Поддержка** , чтобы отсортировать по убыванию поддержки.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-139">Click the **Support** column to sort by highest to lowest support.</span></span> <span data-ttu-id="c2f9e-140">Это даст вам представление о том, что покупатели покупают чаще всего.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-140">This will give you an idea of what customers are buying most often.</span></span>  
  
2.  <span data-ttu-id="c2f9e-141">Чтобы сосредоточиться на определенном наборе элементов, из множества тысяч возможных комбинаций введите некоторый текст в поле **Фильтровать набор элементов** .</span><span class="sxs-lookup"><span data-stu-id="c2f9e-141">To focus on a particular itemset of interest, out of the many thousand combinations possible, type some text in the **Filter Itemset** box.</span></span>  
  
     <span data-ttu-id="c2f9e-142">Мы ввели `Gloves` .</span><span class="sxs-lookup"><span data-stu-id="c2f9e-142">Here we typed `Gloves`.</span></span> <span data-ttu-id="c2f9e-143">После применения фильтра в списке наборов элементов (после его обновления) будут отображаться только те наборы, которые содержат строку «gloves».</span><span class="sxs-lookup"><span data-stu-id="c2f9e-143">When you apply the filter, the list is refreshed to show only itemsets containing gloves.</span></span> <span data-ttu-id="c2f9e-144">Это поможет сосредоточиться на тех транзакциях, где клиенты покупали перчатки и некоторые другие предметы.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-144">This lets you focus on the transactions where customers purchased gloves and some other item.</span></span>  
  
     <span data-ttu-id="c2f9e-145">Параметр **Фильтровать набор элементов** также отображает список ранее использованных фильтров.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-145">The **Filter Itemset** option also displays a list of the filters that you have used previously.</span></span>  
  
3.  <span data-ttu-id="c2f9e-146">Измените значение параметра **Минимальный размер набора элементов** , чтобы отфильтровать клиентов, которые приобрели только перчатки и не имеют других элементов.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-146">Change the value of **Minimum itemset size** to filter out the customers who bought only gloves and no other items.</span></span>  
  
4.  <span data-ttu-id="c2f9e-147">Щелкните раскрывающийся список для параметра **Показать**, чтобы управлять отображением атрибутов.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-147">Click the dropdown list for the option **Show**, to control how the attributes are displayed:</span></span>  
  
    -   <span data-ttu-id="c2f9e-148">**Отобразить имя и значение атрибута**</span><span class="sxs-lookup"><span data-stu-id="c2f9e-148">**Show attribute name and value**</span></span>  
  
    -   <span data-ttu-id="c2f9e-149">**Отобразить только значение атрибута**</span><span class="sxs-lookup"><span data-stu-id="c2f9e-149">**Show attribute value only**</span></span>  
  
    -   <span data-ttu-id="c2f9e-150">**Отобразить только имя атрибута**</span><span class="sxs-lookup"><span data-stu-id="c2f9e-150">**Show attribute name only**</span></span>  
  
     <span data-ttu-id="c2f9e-151">Обратите внимание на то, как будет изменяться имя.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-151">Notice how the name changes.</span></span> <span data-ttu-id="c2f9e-152">В случае модели анализа покупательского поведения, построенной на основе вложенных таблиц товаров, приобретенных многими клиентами, имя атрибута обычно является названием продукта, а присутствие товара в списке отмечается как `Existing`, указывая, что покупатель купил товар.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-152">In the case of a market basket model, which is built on nested tables of products that were purchased by multiple customers, the attribute name is typically the product name, and the presence of the product in the list is marked as `Existing`, meaning that the customer did buy the item.</span></span>  
  
     <span data-ttu-id="c2f9e-153">Противоположностью `Existing` является `Missing`, что может быть полезным атрибутом для интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-153">The opposite of `Existing` is `Missing`, which can be a very useful attribute to investigate in data mining.</span></span> <span data-ttu-id="c2f9e-154">Например, предположим, что набор элементов A + B настолько популярен, что вы хотели бы найти клиентов, которые приобрели товар A, но не элемент B. Это можно сделать с помощью прогнозирующего запроса и получения транзакций с помощью одного, но не другого, а также выполнить некоторые дальнейшие анализа.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-154">For example, suppose the itemset A +B is so very popular that you wanted to find customers who purchased Item A but not item B. You could do this by using a prediction query and retrieving the transactions with one but not the other, and do some further analysis on those.</span></span> <span data-ttu-id="c2f9e-155">Сведения о создании прогнозирующих запросов к моделям взаимосвязей см. в разделе [примеры запросов модели взаимосвязей](data-mining/association-model-query-examples.md) в Электронная документация на SQL Server</span><span class="sxs-lookup"><span data-stu-id="c2f9e-155">For information about how to create prediction queries on association models, see [Association Model Query Examples](data-mining/association-model-query-examples.md) in SQL Server Books Online</span></span>  
  
5.  <span data-ttu-id="c2f9e-156">Чтобы принудительно отобразить список наборов элементов, используя новые условия фильтра, можно установить или снять флажок **Показывать длинное имя** .</span><span class="sxs-lookup"><span data-stu-id="c2f9e-156">To force the list of itemsets to redisplay using your new filter criteria, you can select or clear the **Show long name** check box.</span></span>  
  
 [<span data-ttu-id="c2f9e-157">К началу</span><span class="sxs-lookup"><span data-stu-id="c2f9e-157">Back to Top</span></span>](#BKMK_ViewerTabs)  
  
###  <a name="rules"></a><a name="BKMK_Rules"></a><span data-ttu-id="c2f9e-158">Правил</span><span class="sxs-lookup"><span data-stu-id="c2f9e-158">Rules</span></span>  
 <span data-ttu-id="c2f9e-159">На вкладке **правила** объединены сведения о наборах элементов и их относительном значении.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-159">The **Rules** tab combines information about the itemsets and their relative value.</span></span>  
  
 <span data-ttu-id="c2f9e-160">![Список правил, созданных моделью взаимосвязей](media/dm13-association-rules.gif "Список правил, созданных моделью взаимосвязей")</span><span class="sxs-lookup"><span data-stu-id="c2f9e-160">![List of rules created by an association model](media/dm13-association-rules.gif "List of rules created by an association model")</span></span>  
  
 <span data-ttu-id="c2f9e-161">*Вероятность* представляет часть вариантов в наборе данных, содержащих целевое сочетание элементов.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-161">*Probability* represents the fraction of cases in the dataset that contain the targeted combination of items.</span></span> <span data-ttu-id="c2f9e-162">Вероятность аналогична статистической концепции *достоверности*и дает указание о том, насколько вероятна вероятность результата правила.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-162">Probability is similar to the statistical concept of *confidence*, and gives you an indication of how likely the result of a rule is to occur.</span></span> <span data-ttu-id="c2f9e-163">Вы можете изменить значение **минимальной вероятности** на этой панели, чтобы отфильтровать отображаемые правила.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-163">You can change the value of **Minimum probability** in this pane to filter the rules that are displayed.</span></span>  
  
 <span data-ttu-id="c2f9e-164">Значение **минимальной вероятности** , которое вы первоначально видите, — это пороговое значение, которое использовалось алгоритмом при построении модели.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-164">The value for **Minimum probability** that you initially see is the threshold value that was used by the algorithm when building the model.</span></span> <span data-ttu-id="c2f9e-165">После завершения модели это значение нельзя уменьшить, но можно увеличить его, чтобы отобразить только более высокие элементы вероятности.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-165">After the model is complete, you can't decrease this value, but you can increase it to show only the higher probability items.</span></span>  
  
 <span data-ttu-id="c2f9e-166">*Важность* предназначена для измерения полезности правила.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-166">*Importance* is designed to measure the usefulness of a rule.</span></span> <span data-ttu-id="c2f9e-167">Слишком типичное правило может быть столь универсальным, что будет иметь низкую информационную ценность.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-167">A rule that is very common might be so ubiquitous that is has little information value.</span></span> <span data-ttu-id="c2f9e-168">Чем больше значение в столбце «Важность», тем большую ценность имеет правило для прогнозирования результата.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-168">The greater the importance, the more valuable the rule is for predicting the outcome.</span></span> <span data-ttu-id="c2f9e-169">В средстве анализ покупательской [корзины &#40;таблице аналисистулс for Excel&#41;](shopping-basket-analysis-table-analysistools-for-excel.md) Tool важность можно сочетать с ценой товаров для определения пакетов, которые потенциально наиболее ценны в плане продаж.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-169">In the [Shopping Basket Analysis &#40;Table AnalysisTools for Excel&#41;](shopping-basket-analysis-table-analysistools-for-excel.md) tool, importance can be combined with the price of items to determine the bundles that are potentially most valuable in terms of sales.</span></span>  
  
##### <a name="explore-the-rules-list"></a><span data-ttu-id="c2f9e-170">Просмотр списка правил</span><span class="sxs-lookup"><span data-stu-id="c2f9e-170">Explore the rules list</span></span>  
  
1.  <span data-ttu-id="c2f9e-171">Попробуйте щелкнуть заголовки столбцов — **вероятность**, **важность**и **правило** , чтобы увидеть, как изменяются данные.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-171">Try clicking the column headings - **Probability**, **Importance**, and **Rule** - to see how the data changes.</span></span>  
  
2.  <span data-ttu-id="c2f9e-172">Используйте параметр **правило фильтра** , чтобы ввести значения и сосредоточиться на целевых правилах.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-172">Use the **Filter Rule** option to type in values and focus on targeted rules.</span></span>  
  
     <span data-ttu-id="c2f9e-173">Например, если вы хотите просмотреть все правила, которые прогнозируют, что клиенты с большой вероятностью приобретаются вместе с перчатки, введите "перчатки" в текстовом поле и обновите панель.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-173">For example, if you want to see all the rules that predict what customers are likely to purchase along with gloves, type "gloves" in the text box and refresh the pane.</span></span>  
  
     <span data-ttu-id="c2f9e-174">Параметр **Фильтровать набор элементов** также отображает список ранее использованных фильтров.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-174">The **Filter Itemset** option also displays a list of the filters that you have used previously.</span></span>  
  
3.  <span data-ttu-id="c2f9e-175">Чтобы принудительно отобразить список правил с помощью условий фильтра, можно установить или снять флажок **Показывать длинное имя** .</span><span class="sxs-lookup"><span data-stu-id="c2f9e-175">To force the list of rules to redisplay using filter criteria, you can select or clear the **Show long name** check box.</span></span>  
  
4.  <span data-ttu-id="c2f9e-176">Используйте параметр **Показать** , чтобы управлять способом отображения имен правил.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-176">Use the option, **Show** to control the way that rule names are displayed.</span></span>  
  
5.  <span data-ttu-id="c2f9e-177">Задайте для параметра **Максимальное число строк** значение 100, а затем нажмите кнопку **Копировать в Excel**.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-177">Set the value for the **Maximum rows** option to 100, and then click **Copy to Excel**.</span></span>  
  
     <span data-ttu-id="c2f9e-178">Обратите внимание, что изменение этого значения не влияет на объем данных в модели. Он просто управляет количеством строк в списке Отображение.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-178">Note that changing this value doesn't have any effect on the amount of data in the model; it simply controls the number of rows in the display list.</span></span> <span data-ttu-id="c2f9e-179">Этот параметр может быть полезен при работе с очень большими моделями.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-179">This option can be useful when working with very large models.</span></span>  
  
 [<span data-ttu-id="c2f9e-180">К началу</span><span class="sxs-lookup"><span data-stu-id="c2f9e-180">Back to Top</span></span>](#BKMK_ViewerTabs)  
  
###  <a name="dependency-network"></a><a name="BKMK_Dependency"></a><span data-ttu-id="c2f9e-181">Сеть зависимостей</span><span class="sxs-lookup"><span data-stu-id="c2f9e-181">Dependency Network</span></span>  
 <span data-ttu-id="c2f9e-182">Вкладка **Сеть зависимостей** — это визуальная схема корреляций между элементами.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-182">The **Dependency Network** tab is a visual map of the correlations among items.</span></span> <span data-ttu-id="c2f9e-183">Каждый овал в графе (называемый *узлом*) представляет пару "атрибут-значение", например "Прокрутка = существующий" или "Age = 1-30".</span><span class="sxs-lookup"><span data-stu-id="c2f9e-183">Each oval in the graph (referred to as a *node*) represents an attribute-value pair, such as "Vest = Existing" or "Age = 1-30".</span></span>  <span data-ttu-id="c2f9e-184">Каждая строка, соединяющая овалы (называемые *ребром*), представляет тип корреляции.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-184">Each line connecting the ovals (referred to as an *edge*) represents a type of correlation.</span></span>  
  
 <span data-ttu-id="c2f9e-185">![Диаграмма сети зависимостей для модели взаимосвязей](media/dm13-association-dependencynetwork.gif "Диаграмма сети зависимостей для модели взаимосвязей")</span><span class="sxs-lookup"><span data-stu-id="c2f9e-185">![Dependency network graph for an association model](media/dm13-association-dependencynetwork.gif "Dependency network graph for an association model")</span></span>  
  
##### <a name="explore-the-dependency-network"></a><span data-ttu-id="c2f9e-186">Просмотр сети зависимостей</span><span class="sxs-lookup"><span data-stu-id="c2f9e-186">Explore the dependency network</span></span>  
  
1.  <span data-ttu-id="c2f9e-187">Нажмите кнопку **найти** и используйте диалоговое окно **Поиск узла** для ввода интересующего элемента.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-187">Click the **Find** button and use the **Find Node** dialog box to type an item of interest.</span></span>  
  
     <span data-ttu-id="c2f9e-188">Например, введите «перчатки», а затем разверните диаграмму в окне, чтобы можно было легко просмотреть результаты.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-188">For example, type "gloves" and then maximize the graph in the window so that you can easily see the results.</span></span>  
  
     <span data-ttu-id="c2f9e-189">Узел, содержащий элемент, выделен; стрелки, указывающие на узел, представляют правило, соединяющее элементы.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-189">The node that contains the item is highlighted, while the arrows pointing to the node represent a rule that connects the items.</span></span>  
  
     <span data-ttu-id="c2f9e-190">Направление стрелки сообщает о направленности правила.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-190">The direction of the arrow tells you the direction of the rule.</span></span> <span data-ttu-id="c2f9e-191">Например, если кто-то покупает Перчатки и, скорее всего, купит свой тариф, то стрелка начнется с узла "специализированный" и прекратит работу на узле "направка".</span><span class="sxs-lookup"><span data-stu-id="c2f9e-191">For example, if someone who buys gloves is also likely to buy a vest, the arrow will start from the "glove" node and terminate on the "vest" node.</span></span>  
  
     <span data-ttu-id="c2f9e-192">Чтобы получить дополнительную статистику об этом правиле, перейдите на вкладку **правила** и найдите правило с описанием «специализированный-existing»-> «по праву на текущий».)</span><span class="sxs-lookup"><span data-stu-id="c2f9e-192">To get additional statistics about this rule, you can click the **Rules** tab and look for a rule with the description, "Glove - Existing" -> "Vest - Existing.")</span></span>  
  
2.  <span data-ttu-id="c2f9e-193">Перетащите ползунок в левой части средства просмотра.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-193">Click and drag the slider at the left of the viewer.</span></span>  
  
     <span data-ttu-id="c2f9e-194">Ползунок выступает в качестве фильтра, привязанного к вероятности правил.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-194">The slider acts as a filter on the probability of the rules.</span></span> <span data-ttu-id="c2f9e-195">При движении ползунка вниз отображаются только самые сильные правила.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-195">Lowering the slider shows only the strongest rules.</span></span>  
  
3.  <span data-ttu-id="c2f9e-196">Нажмите кнопку **Копировать в Excel** , чтобы скопировать моментальный снимок текущего окна в Excel.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-196">Click **Copy to Excel** to copy a snapshot of the current window to Excel.</span></span>  
  
     <span data-ttu-id="c2f9e-197">Вы не сможете работать с графом, скопированным в Excel; Если вам нужен интерактивный граф сети, используйте оснастку [Просмотр моделей интеллектуального анализа данных в Visio &#40;надстройки интеллектуального анализа данных&#41;](viewing-data-mining-models-in-visio-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="c2f9e-197">You won't be able to work with the graph that you copy into Excel; if you need an interactive network graph, use the [Viewing Data Mining Models in Visio &#40;Data Mining Add-ins&#41;](viewing-data-mining-models-in-visio-data-mining-add-ins.md).</span></span>  
  
 [<span data-ttu-id="c2f9e-198">К началу</span><span class="sxs-lookup"><span data-stu-id="c2f9e-198">Back to Top</span></span>](#BKMK_ViewerTabs)  
  
## <a name="more-about-association-models"></a><span data-ttu-id="c2f9e-199">Дополнительные сведения о моделях взаимосвязей</span><span class="sxs-lookup"><span data-stu-id="c2f9e-199">More about Association Models</span></span>  
 <span data-ttu-id="c2f9e-200">Функцию **Обзор** можно использовать для открытия и изучения любой модели, созданной с помощью алгоритма правил взаимосвязей (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="c2f9e-200">You can use the **Browse** feature to open and explore any model that was created using the Microsoft Association Rules algorithm.</span></span> <span data-ttu-id="c2f9e-201">К ним относятся модели, созданные с помощью средства [анализ покупательской корзины &#40;таблице аналисистулс для Excel&#41;](shopping-basket-analysis-table-analysistools-for-excel.md) , на ленте **средства анализа таблиц** или в [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c2f9e-201">This includes models built using the [Shopping Basket Analysis &#40;Table AnalysisTools for Excel&#41;](shopping-basket-analysis-table-analysistools-for-excel.md) tool, in the **Table Analysis Tools** ribbon, or in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="c2f9e-202">Если модель правил взаимосвязей создается с помощью средства «Средство анализа покупательского поведения», настройка многих дополнительных параметров осуществляется автоматически.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-202">If you create an association rules model using the Shopping Basket Analysis tool, many of the advanced options are configured automatically for you.</span></span>  
  
 <span data-ttu-id="c2f9e-203">Если вы хотите задать дополнительные параметры или изменить минимальную вероятность и поддержку, воспользуйтесь [мастером связи &#40;мастере создания клиента интеллектуального анализа данных для excel&#41;](associate-wizard-data-mining-client-for-excel.md) или создайте собственную модель с помощью функции [Добавить модель для структурирования &#40;надстройки интеллектуального анализа данных для Excel&#41;](add-model-to-structure-data-mining-add-ins-for-excel.md) моделирования.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-203">If you want to set advanced parameters or alter minimum probability and support, use the [Associate Wizard &#40;Data Mining Client for Excel&#41;](associate-wizard-data-mining-client-for-excel.md) wizard, or build your own model using the [Add Model to Structure &#40;Data Mining Add-ins for Excel&#41;](add-model-to-structure-data-mining-add-ins-for-excel.md) modeling option.</span></span>  
  
-   <span data-ttu-id="c2f9e-204">**Наборы элементов:** При создании модели можно также управлять количеством наборов элементов, создаваемых путем присвоения значения параметру MINIMUM_PROBABILITY.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-204">**Itemsets:** When you create the model, you can also control the number of itemsets that are generated by assigning a value to the MINIMUM_PROBABILITY parameter.</span></span> <span data-ttu-id="c2f9e-205">Этот параметр доступен в диалоговом окне Параметры алгоритма.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-205">This parameter is available in the Algorithm Parameters dialog box.</span></span>  
  
-   <span data-ttu-id="c2f9e-206">**Правила:** [!INCLUDE[msCoName](../includes/msconame-md.md)]Алгоритм правил взаимосвязей использует значения вероятности для ограничения числа создаваемых правил.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-206">**Rules:** The [!INCLUDE[msCoName](../includes/msconame-md.md)] Association Rules algorithm uses probability values to restrict the number of rules that are generated.</span></span> <span data-ttu-id="c2f9e-207">Количество правил можно регулировать с помощью параметров `MINIMUM_PROBABILITY` и `MINIMUM _IMPORTANCE`.</span><span class="sxs-lookup"><span data-stu-id="c2f9e-207">You can control the number of rules by setting the parameters, `MINIMUM_PROBABILITY` or `MINIMUM _IMPORTANCE`.</span></span>  
  
 <span data-ttu-id="c2f9e-208">Дополнительные сведения о настройке дополнительных параметров см. в разделе [алгоритмы интеллектуального анализа данных &#40;SQL Server надстроек интеллектуального анализа данных&#41;](data-mining-algorithms-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="c2f9e-208">For more information about configuring advanced parameters, see [Data Mining Algorithms &#40;SQL Server Data Mining Add-ins&#41;](data-mining-algorithms-sql-server-data-mining-add-ins.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2f9e-209">См. также:</span><span class="sxs-lookup"><span data-stu-id="c2f9e-209">See Also</span></span>  
 [<span data-ttu-id="c2f9e-210">Просмотр моделей в Excel &#40;SQL Server надстройки интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="c2f9e-210">Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](browsing-models-in-excel-sql-server-data-mining-add-ins.md)  
  
  