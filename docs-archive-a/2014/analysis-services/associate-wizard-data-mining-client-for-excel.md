---
title: Мастер связывания (клиент интеллектуального анализа данных для Excel) | Документация Майкрософт
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- nested tables, in association models
- association [data mining]
ms.assetid: 4db6462f-93c7-443f-8ff7-39474dc7029e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 73ce4bbedb710de1ded149a12f6f9b83f0b92a11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656891"
---
# <a name="associate-wizard-data-mining-client-for-excel"></a><span data-ttu-id="6a909-102">Мастер взаимосвязей (клиент интеллектуального анализа данных для Excel)</span><span class="sxs-lookup"><span data-stu-id="6a909-102">Associate Wizard (Data Mining Client for Excel)</span></span>
  <span data-ttu-id="6a909-103">![Мастер взаимосвязей на ленте «Интеллектуальный анализ данных»](media/dmc-associate.gif "Мастер взаимосвязей на ленте «Интеллектуальный анализ данных»")</span><span class="sxs-lookup"><span data-stu-id="6a909-103">![Associate wizard in Data Mining ribbon](media/dmc-associate.gif "Associate wizard in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="6a909-104">Мастер взаимосвязей помогает создать модель интеллектуального анализа данных с помощью [!INCLUDE[msCoName](../includes/msconame-md.md)] алгоритма правил взаимосвязей.</span><span class="sxs-lookup"><span data-stu-id="6a909-104">The Associate wizard helps you create a data mining model using the [!INCLUDE[msCoName](../includes/msconame-md.md)] Association Rules algorithm.</span></span> <span data-ttu-id="6a909-105">Такие модели интеллектуального анализа данных особенно полезны для создания *систем рекомендаций*.</span><span class="sxs-lookup"><span data-stu-id="6a909-105">Such mining models are particularly useful for creating *recommendation systems*.</span></span>  
  
 <span data-ttu-id="6a909-106">Алгоритм взаимосвязей [!INCLUDE[msCoName](../includes/msconame-md.md)] сканирует набор данных, состоящий из транзакций или событий, и находит частые сочетания.</span><span class="sxs-lookup"><span data-stu-id="6a909-106">How it works is that the [!INCLUDE[msCoName](../includes/msconame-md.md)] Association Rules algorithm scans a dataset comprised of transactions or events, and finds the combinations that frequently appear together.</span></span> <span data-ttu-id="6a909-107">Возможны тысячи сочетаний, но алгоритм можно настроить для поиска большего или меньшего числа сочетаний и сохранения наиболее вероятных из них.</span><span class="sxs-lookup"><span data-stu-id="6a909-107">There can be many thousand combinations, but the algorithm can be customized to find more or fewer, and to retain only the most probable combinations.</span></span>  
  
 <span data-ttu-id="6a909-108">Анализ взаимосвязей можно применить для решения многих задач.</span><span class="sxs-lookup"><span data-stu-id="6a909-108">You can apply association analysis to many problems.</span></span> <span data-ttu-id="6a909-109">Самое популярное применение этого метода — анализ покупательского поведения, находящий отдельные продукты, которые часто приобретаются вместе.</span><span class="sxs-lookup"><span data-stu-id="6a909-109">The most popular application of this method is market basket analysis, which finds individual products that are often purchased together.</span></span> <span data-ttu-id="6a909-110">Эту информацию можно использовать для рекомендации товаров клиентам на основе товаров, которые они уже купили.</span><span class="sxs-lookup"><span data-stu-id="6a909-110">You can then use that information to recommend products to customers based on items they have already bought.</span></span>  
  
## <a name="using-the-associate-wizard"></a><span data-ttu-id="6a909-111">Использование мастера взаимосвязей</span><span class="sxs-lookup"><span data-stu-id="6a909-111">Using the Associate Wizard</span></span>  
  
1.  <span data-ttu-id="6a909-112">На ленте **интеллектуальный анализ данных** нажмите кнопку **связать**.</span><span class="sxs-lookup"><span data-stu-id="6a909-112">In the **Data Mining** ribbon, click **Associate**.</span></span>  
  
2.  <span data-ttu-id="6a909-113">На странице **Выбор источника данных** выберите таблицу или диапазон данных Excel и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="6a909-113">On the **Select Source Data** page, choose an Excel table or data range, and click **Next**.</span></span>  
  
     <span data-ttu-id="6a909-114">Книга с образцами данных на вкладке «Взаимосвязи» содержит пример того, как данные транзакций обычно упорядочиваются, если, например, имеется несколько товаров в каждой транзакции или несколько записей о покупках в расчете на клиента, которые вы хотите проанализировать.</span><span class="sxs-lookup"><span data-stu-id="6a909-114">The sample data workbook contains an example, in the Associate tab, of how transaction data is typically arranged if, for example, you have multiple products in each transaction or multiple purchasing records per customer that you want to analyze.</span></span>  
  
     <span data-ttu-id="6a909-115">Если вы хотите использовать внешние данные для создания модели взаимосвязей с помощью мастера связывания, необходимо сначала добавить данные в Excel и выполнить *сведение* данных.</span><span class="sxs-lookup"><span data-stu-id="6a909-115">If you want to use external data to build an association model using the Associate wizard, you must add the data to Excel first, and *flatten* the data.</span></span> <span data-ttu-id="6a909-116">Дополнительные сведения о подготовке данных для моделирования взаимосвязей см. в разделе [вложенные таблицы &#40;Analysis Services-&#41;интеллектуального анализа данных ](data-mining/nested-tables-analysis-services-data-mining.md)в Электронная документация на SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6a909-116">For more information about preparing data for association modeling, see [Nested Tables &#40;Analysis Services - Data Mining&#41;](data-mining/nested-tables-analysis-services-data-mining.md), in SQL Server Books Online.</span></span>  
  
3.  <span data-ttu-id="6a909-117">На странице **Ассоциация** выберите столбец, определяющий транзакцию.</span><span class="sxs-lookup"><span data-stu-id="6a909-117">On the **Association** page, choose the column that identifies the transaction.</span></span>  
  
     <span data-ttu-id="6a909-118">Для моделей покупательского поведения этот идентификатор представляет собой моделируемый элемент.</span><span class="sxs-lookup"><span data-stu-id="6a909-118">For market basket models, this identifier represents the unit you want to model.</span></span> <span data-ttu-id="6a909-119">Требуется ли анализировать позиции, которые каждый отдельный клиент приобретает в разное время, или множество транзакций разных пользователей?</span><span class="sxs-lookup"><span data-stu-id="6a909-119">Do you want to analyze items that individual customers have purchased over time, or do you want to analyze many transactions involving multiple customers?</span></span> <span data-ttu-id="6a909-120">В первом случае следует выбрать идентификатор клиента, во втором — идентификатор покупки или другой транзакции.</span><span class="sxs-lookup"><span data-stu-id="6a909-120">In the first case, you would choose the customer ID; in the latter you would choose the purchase order or other transaction ID.</span></span>  
  
4.  <span data-ttu-id="6a909-121">В поле **элемент**выберите столбец, содержащий элементы, между которыми необходимо найти связи.</span><span class="sxs-lookup"><span data-stu-id="6a909-121">For **Item**, select the column that contains the things among which you need to find associations.</span></span>  
  
     <span data-ttu-id="6a909-122">Например, в модели покупательского поведения можно выбрать поле товара, чтобы проанализировать, какие товары часто приобретаются вместе.</span><span class="sxs-lookup"><span data-stu-id="6a909-122">For example, in a market basket model, you would choose a products field, to analyze which products are often purchased together.</span></span> <span data-ttu-id="6a909-123">Если отдельных товаров слишком много для эффективного поиска корреляции, можно выбрать категорию или подкатегорию товаров.</span><span class="sxs-lookup"><span data-stu-id="6a909-123">If there are too many individual products to correlate them effectively, you might choose a product category or subcategory field.</span></span>  
  
5.  <span data-ttu-id="6a909-124">В поле **пороговые**значения можно задать значение, определяющее или влияющее на выходные данные модели.</span><span class="sxs-lookup"><span data-stu-id="6a909-124">In **Thresholds**, you can set values that control or affect the output of the model:</span></span>  
  
    -   <span data-ttu-id="6a909-125">**Минимальная поддержка.**</span><span class="sxs-lookup"><span data-stu-id="6a909-125">**Minimum support.**</span></span> <span data-ttu-id="6a909-126">Указывает, сколько раз группа элементов должна появляться, чтобы считаться важной.</span><span class="sxs-lookup"><span data-stu-id="6a909-126">Specifies how many times a group of items must appear to be considered important.</span></span> <span data-ttu-id="6a909-127">Алгоритм будет пропускать все сочетания элементов, не отвечающие этому критерию.</span><span class="sxs-lookup"><span data-stu-id="6a909-127">The algorithm will ignore any item combinations that do not meet this criterion.</span></span> <span data-ttu-id="6a909-128">Например, вас могут интересовать только те наборы элементов, где элементы появляются вместе не менее 10 раз.</span><span class="sxs-lookup"><span data-stu-id="6a909-128">For example, you might want to see only itemsets where the items appeared together at least 10 times overall.</span></span>  
  
    -   <span data-ttu-id="6a909-129">**Минимальная вероятность правила**.</span><span class="sxs-lookup"><span data-stu-id="6a909-129">**Minimum rule probability**.</span></span> <span data-ttu-id="6a909-130">Задает значение минимальной вероятности, необходимой для сохранения правила.</span><span class="sxs-lookup"><span data-stu-id="6a909-130">Specifies the minimum probability value required for a rule to be saved.</span></span> <span data-ttu-id="6a909-131">Анализируется весь набор данных для нахождения всех сочетаний, после чего подсчитывается вероятность.</span><span class="sxs-lookup"><span data-stu-id="6a909-131">The entire data set is analyzed to find all combinations, and then probability is calculated.</span></span> <span data-ttu-id="6a909-132">Если порог низкий, мастер может ассоциировать элементы со слабой корреляцией.</span><span class="sxs-lookup"><span data-stu-id="6a909-132">If the threshold is low, the wizard may associate items that are only loosely correlated.</span></span> <span data-ttu-id="6a909-133">Если порог слишком высокий, некоторые взаимосвязи могут быть пропущены, поскольку их не поддерживает достаточный объем данных.</span><span class="sxs-lookup"><span data-stu-id="6a909-133">If the threshold is too high, some associations may be omitted because they do not have enough supporting data.</span></span>  
  
     <span data-ttu-id="6a909-134">В целом при изменении этих значений возникнут следующие результаты.</span><span class="sxs-lookup"><span data-stu-id="6a909-134">In general, changing these values has the following effects:</span></span>  
  
    -   <span data-ttu-id="6a909-135">По мере уменьшения значения несущего множества увеличивается число найденных сочетаний.</span><span class="sxs-lookup"><span data-stu-id="6a909-135">As you lower the value for support, you increase the number of combinations that are found.</span></span>  
  
    -   <span data-ttu-id="6a909-136">При уменьшении максимального значения несущего множества отфильтровываются элементы, встречающиеся настолько часто, что их присутствие не имеет смысла.</span><span class="sxs-lookup"><span data-stu-id="6a909-136">As you decrease the maximum support, you filter out items that occur so often that they have little meaning.</span></span>  
  
    -   <span data-ttu-id="6a909-137">По мере понижения вероятности правила понижаются требования, которым должно удовлетворять сочетание, чтобы считаться важным в контексте полного набора данных.</span><span class="sxs-lookup"><span data-stu-id="6a909-137">As you lower the probability of a rule, you lower the requirements that a combination must meet to be considered important in the context of the total data set.</span></span>  
  
     <span data-ttu-id="6a909-138">**Совет.** Рекомендуется создать несколько моделей интеллектуального анализа данных, используя разные сочетания поддержки и вероятности.</span><span class="sxs-lookup"><span data-stu-id="6a909-138">**Tip:** It is a good idea to create multiple mining models using different combinations of support and probability.</span></span> <span data-ttu-id="6a909-139">Чтобы определить, какие параметры используются для каждой модели, можно воспользоваться мастером **модели документов** , доступным в клиенте интеллектуального анализа данных для Excel, и использовать параметр **подробный** отчет.</span><span class="sxs-lookup"><span data-stu-id="6a909-139">To track which settings you used for each model, you can use the **Document Model** wizard, available in the Data Mining Client for Excel, and use the **Detailed** report option.</span></span> <span data-ttu-id="6a909-140">Дополнительные сведения см. в разделе [документирование моделей интеллектуального анализа данных &#40;надстройки интеллектуального анализа для Excel&#41;](documenting-mining-models-data-mining-add-ins-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="6a909-140">For more information, see [Documenting Mining Models &#40;Data Mining Add-ins for Excel&#41;](documenting-mining-models-data-mining-add-ins-for-excel.md).</span></span>  
  
6.  <span data-ttu-id="6a909-141">При необходимости нажмите кнопку **Параметры** , чтобы изменить параметры алгоритма и настроить поведение модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="6a909-141">Optionally, click **Parameters** to change the algorithm parameters and customize the behavior of the mining model.</span></span>  
  
     <span data-ttu-id="6a909-142">В диалоговом окне «Параметры алгоритма» содержатся все параметры, задаваемые в мастере, а также еще несколько используемых реже обычного, таких как MAXIMUM_SUPPORT.</span><span class="sxs-lookup"><span data-stu-id="6a909-142">The Algorithm Parameters dialog box includes all of the parameters you set in the wizard, plus a few that are less commonly used, such as MAXIMUM_SUPPORT.</span></span> <span data-ttu-id="6a909-143">Дополнительные сведения об использовании этих параметров см. в [статье Технический справочник по алгоритму взаимосвязей (Майкрософт](data-mining/microsoft-association-algorithm-technical-reference.md)).</span><span class="sxs-lookup"><span data-stu-id="6a909-143">For information about how to use these parameters, see [Microsoft Association Algorithm Technical Reference](data-mining/microsoft-association-algorithm-technical-reference.md).</span></span>  
  
7.  <span data-ttu-id="6a909-144">На странице **Готово** введите уникальное имя для набора данных и модели.</span><span class="sxs-lookup"><span data-stu-id="6a909-144">On the **Finish** page, type a unique name for the data set and the model.</span></span>  
  
8.  <span data-ttu-id="6a909-145">В **параметрах параметры**вы определяете, как вы хотите работать с моделью после ее завершения:</span><span class="sxs-lookup"><span data-stu-id="6a909-145">In **Options**, you define how you want to work with the model after it is completed:</span></span>  
  
    -   <span data-ttu-id="6a909-146">**Обзор**.</span><span class="sxs-lookup"><span data-stu-id="6a909-146">**Browse**.</span></span>  <span data-ttu-id="6a909-147">Когда модель готова, мастер открывает окно, в котором выводит правила, наборы элементов и диаграмму сети зависимостей с отображением взаимосвязей.</span><span class="sxs-lookup"><span data-stu-id="6a909-147">When the model is ready, the wizard opens a window that displays the rules, the itemsets, and a dependency network graph that depicts associations.</span></span>  
  
         <span data-ttu-id="6a909-148">Дополнительные сведения о том, как интерпретировать данные в средстве просмотра моделей взаимосвязей, см. в разделе [Просмотр модели правил взаимосвязей](browsing-an-association-rules-model.md).</span><span class="sxs-lookup"><span data-stu-id="6a909-148">For more information about how to interpret the data in the association model viewer, see [Browsing an Association Rules Model](browsing-an-association-rules-model.md).</span></span>  
  
    -   <span data-ttu-id="6a909-149">**Включить детализацию**.</span><span class="sxs-lookup"><span data-stu-id="6a909-149">**Enable drillthrough**.</span></span> <span data-ttu-id="6a909-150">Выберите этот параметр, чтобы получить доступ к базовым данным из модели.</span><span class="sxs-lookup"><span data-stu-id="6a909-150">Select this option to gain access to the underlying data, via the model.</span></span>  
  
         <span data-ttu-id="6a909-151">Детализация полезна, например, если требуется возможность просмотра исходных данных при щелчке на том или ином наборе элементов.</span><span class="sxs-lookup"><span data-stu-id="6a909-151">Drillthrough is useful, for example, if you want to click on a particular itemset and see the source data.</span></span>  
  
    -   <span data-ttu-id="6a909-152">**Использовать временную модель**.</span><span class="sxs-lookup"><span data-stu-id="6a909-152">**Use temporary model**.</span></span> <span data-ttu-id="6a909-153">Выберите этот параметр, если не нужно, чтобы модель сохранялась на сервере.</span><span class="sxs-lookup"><span data-stu-id="6a909-153">Select this option if you don't want the model saved on the server.</span></span> <span data-ttu-id="6a909-154">Временные модели удаляются при закрытии Excel.</span><span class="sxs-lookup"><span data-stu-id="6a909-154">Temporary models are deleted when you close Excel.</span></span>  
  
9. <span data-ttu-id="6a909-155">Мастер анализирует все возможные сочетания и создает отчет, содержащий наборы элементов и правил.</span><span class="sxs-lookup"><span data-stu-id="6a909-155">The wizard analyzes all possible combinations and creates a report that contains the itemsets and rules.</span></span>  
  
## <a name="more-about-association-models"></a><span data-ttu-id="6a909-156">Дополнительные сведения о моделях взаимосвязей</span><span class="sxs-lookup"><span data-stu-id="6a909-156">More About Association Models</span></span>  
 <span data-ttu-id="6a909-157">[!INCLUDE[msCoName](../includes/msconame-md.md)]Алгоритм правил взаимосвязей проверяет обучающие данные для поиска элементов, которые отображаются вместе в транзакции.</span><span class="sxs-lookup"><span data-stu-id="6a909-157">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Association Rules algorithm examines the training data to find items that appear together in a transaction.</span></span> <span data-ttu-id="6a909-158">Каждая группа элементов образует *набор элементов*.</span><span class="sxs-lookup"><span data-stu-id="6a909-158">Each group of items constitutes an *itemset*.</span></span> <span data-ttu-id="6a909-159">Затем алгоритм подсчитывает число раз, когда появляется каждый набор элементов, и подсчитывает относительную важность каждого набора элементов во всех транзакциях.</span><span class="sxs-lookup"><span data-stu-id="6a909-159">The algorithm then counts the number of times each itemset appears and calculates the relative importance of each itemset across all transactions.</span></span>  
  
 <span data-ttu-id="6a909-160">Алгоритм использует эти сведения о наборах элементов для формирования правил, которые могут быть использованы для прогноза взаимосвязей или формирования рекомендаций.</span><span class="sxs-lookup"><span data-stu-id="6a909-160">The algorithm uses this information about itemsets to generate rules that can be used to predict associations or make recommendations.</span></span> <span data-ttu-id="6a909-161">Например, правило может гласить: «если пользователь приобрел книгу автора 1 и книгу автора 2, то он, вероятнее всего, также приобретет книгу автора 3».</span><span class="sxs-lookup"><span data-stu-id="6a909-161">For example, a rule could be "if the user purchased a book by Author 1 and a book by Author 2, then it is likely that the user will also purchase a book by Author 3".</span></span> <span data-ttu-id="6a909-162">Каждой рекомендации присваивается вероятность на основе прочности взаимосвязей.</span><span class="sxs-lookup"><span data-stu-id="6a909-162">Each recommendation is assigned a probability, based on the strength of the associations.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="6a909-163">Требования</span><span class="sxs-lookup"><span data-stu-id="6a909-163">Requirements</span></span>  
 <span data-ttu-id="6a909-164">Чтобы использовать мастер взаимосвязей, необходимо соединение с базой данных [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6a909-164">To use the Associate wizard, you must be connected to a [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="6a909-165">Исходные данные могут быть организованы в виде таблицы транзакций.</span><span class="sxs-lookup"><span data-stu-id="6a909-165">Your source data must be organized as a transaction table.</span></span> <span data-ttu-id="6a909-166">Исходные данные должны содержать один столбец с идентификаторами транзакций.</span><span class="sxs-lookup"><span data-stu-id="6a909-166">The source data must contain one column that contains the transaction identifier.</span></span> <span data-ttu-id="6a909-167">Этот столбец определяет каждую группу элементов.</span><span class="sxs-lookup"><span data-stu-id="6a909-167">This column identifies each group of items.</span></span> <span data-ttu-id="6a909-168">Столбец транзакций должен иметь связь типа «один ко многим» со вторым столбцом, идентификатором элементов, в котором хранятся имена или идентификаторы отдельных элементов в группе.</span><span class="sxs-lookup"><span data-stu-id="6a909-168">That transaction column must be in a one-to-many relationship with a second column, the item ID, which stores names or ID numbers for the individual items in the group.</span></span>  
  
 <span data-ttu-id="6a909-169">Возможно, понимание этого облегчит сравнение с покупательской корзиной.</span><span class="sxs-lookup"><span data-stu-id="6a909-169">Conceptually, this might be easiest to understand by recalling the shopping cart example.</span></span> <span data-ttu-id="6a909-170">Покупательской корзине присваивается идентификатор, который служит идентификатором транзакции.</span><span class="sxs-lookup"><span data-stu-id="6a909-170">If the shopping cart is assigned an ID, the shopping cart ID serves as the identifier for the transaction.</span></span> <span data-ttu-id="6a909-171">Каждый элемент в покупательской корзине, например пакет картошки или молока, является членом этой транзакции.</span><span class="sxs-lookup"><span data-stu-id="6a909-171">Each item in the shopping cart, such as potatoes or milk, is a member of that transaction.</span></span> <span data-ttu-id="6a909-172">Алгоритм связывания может отслеживанию элементов в транзакциях. Например, чтобы определить, сколько раз Potatoes и молоко отображаются в рамках одной транзакции.</span><span class="sxs-lookup"><span data-stu-id="6a909-172">The Associate algorithm can track items across transactions: for example, to determine how many times potatoes and milk appear within any single transaction.</span></span>  
  
 <span data-ttu-id="6a909-173">Источник данных должен быть отсортирован по столбцу идентификатора транзакций.</span><span class="sxs-lookup"><span data-stu-id="6a909-173">Your source data must be sorted by the transaction identifier column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a909-174">См. также:</span><span class="sxs-lookup"><span data-stu-id="6a909-174">See Also</span></span>  
 <span data-ttu-id="6a909-175">[Создание модели интеллектуального анализа данных](creating-a-data-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="6a909-175">[Creating a Data Mining Model](creating-a-data-mining-model.md) </span></span>  
 <span data-ttu-id="6a909-176">[Просмотр модели правил взаимосвязей](browsing-an-association-rules-model.md) </span><span class="sxs-lookup"><span data-stu-id="6a909-176">[Browsing an Association Rules Model](browsing-an-association-rules-model.md) </span></span>  
 <span data-ttu-id="6a909-177">[Анализ покупательской корзины &#40;таблицу Аналисистулс для Excel&#41;](shopping-basket-analysis-table-analysistools-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="6a909-177">[Shopping Basket Analysis &#40;Table AnalysisTools for Excel&#41;](shopping-basket-analysis-table-analysistools-for-excel.md) </span></span>  
 [<span data-ttu-id="6a909-178">Пошаговое руководство по диаграмме сети зависимостей &#40;надстроек интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="6a909-178">Dependency Network Diagram Walkthrough &#40;Data Mining Add-ins&#41;</span></span>](dependency-network-diagram-walkthrough-data-mining-add-ins.md)  
  
  