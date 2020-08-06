---
title: Фильтрация правила в модели правил взаимосвязей | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- filtering rules [Analysis Services]
- Mining Model Viewer [Analysis Services], rules
- Rules Viewer
ms.assetid: 26cdba5b-5bf1-439e-80a3-8759774e918b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3c904713acc6eaf132e7cb1195186165f21d971a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665670"
---
# <a name="filter-a-rule-in-an-association-rules-model"></a><span data-ttu-id="eccee-102">Фильтрация правила в модели ассоциативных правил</span><span class="sxs-lookup"><span data-stu-id="eccee-102">Filter a Rule in an Association Rules Model</span></span>
  <span data-ttu-id="eccee-103">Чтобы ограничить итоговый список, показав только нужные взаимосвязи, с моделями взаимосвязей можно использовать фильтрацию.</span><span class="sxs-lookup"><span data-stu-id="eccee-103">You can use filtering with association models to restrict the results to just the associations that interest you.</span></span> <span data-ttu-id="eccee-104">Например, можно отфильтровать правила, чтобы показать только правила, содержащие определенный товар.</span><span class="sxs-lookup"><span data-stu-id="eccee-104">For example, you might filter the rules to show only those that include a specific product.</span></span>  
  
 <span data-ttu-id="eccee-105">В конструкторе интеллектуального анализа данных вы используете элементы управления на вкладке **Правила** средства просмотра правил взаимосвязи [!INCLUDE[msCoName](../../includes/msconame-md.md)] , чтобы отфильтровать отображаемые правила.</span><span class="sxs-lookup"><span data-stu-id="eccee-105">In Data Mining Designer, you use the controls on the **Rules** tab of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Association Rules Viewer to filter the rules that are displayed.</span></span>  <span data-ttu-id="eccee-106">Можно также создать запрос для модели, чтобы просмотреть только набор элементов, содержащий определенное значение.</span><span class="sxs-lookup"><span data-stu-id="eccee-106">You can also create a query on the model to see only itemset that contains a particular value.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="eccee-107">Этот параметр доступен только для моделей интеллектуального анализа данных, созданных по алгоритму взаимосвязей (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="eccee-107">This option is available only for mining models that have been created by using the Microsoft Association Algorithm.</span></span>  
  
### <a name="filter-a-rule-in-an-association-model"></a><span data-ttu-id="eccee-108">Фильтрация правил для модели взаимосвязей</span><span class="sxs-lookup"><span data-stu-id="eccee-108">Filter a rule in an association model</span></span>  
  
1.  <span data-ttu-id="eccee-109">Откройте модель интеллектуального анализа данных в **средстве просмотра правил взаимосвязи**.</span><span class="sxs-lookup"><span data-stu-id="eccee-109">Open the mining model by using the **Association Rules Viewer**.</span></span> <span data-ttu-id="eccee-110">Для этого в среде SQL Server Management Studio щелкните правой кнопкой мыши имя модели и выберите команду **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="eccee-110">To do this in SQL Server Management Studio, right click the model name and select **Browse**.</span></span> <span data-ttu-id="eccee-111">Чтобы сделать это в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], дважды щелкните структуру интеллектуального анализа данных, которая содержит модель, а затем перейдите на вкладку **Средство просмотра моделей интеллектуального анализа данных** окна **Конструктор интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="eccee-111">To do this in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], double-click the mining structure that contains the model, and then click the **Mining Model Viewer** tab of **Data Mining Designer**.</span></span>  
  
2.  <span data-ttu-id="eccee-112">Перейдите на вкладку **Правила** окна **Средство просмотра правил взаимосвязи**.</span><span class="sxs-lookup"><span data-stu-id="eccee-112">Click the **Rules** tab of the **Association Rules Viewer**.</span></span>  
  
3.  <span data-ttu-id="eccee-113">В поле **Правило фильтра** введите условие для правила.</span><span class="sxs-lookup"><span data-stu-id="eccee-113">Type a rule condition into the **Filter Rule** box.</span></span> <span data-ttu-id="eccee-114">Например, условием для правила может быть строка «Bike Stand». В этом случае правилу будет удовлетворять и строка «Bike Stands».</span><span class="sxs-lookup"><span data-stu-id="eccee-114">For example, a rule condition might be "Bike Stand", which also returns "Bike Stands".</span></span>  
  
     <span data-ttu-id="eccee-115">В текстовом поле **Правило фильтра** поддерживаются регулярные выражения, определенные языком .NET.</span><span class="sxs-lookup"><span data-stu-id="eccee-115">The **Filter Rule** text box supports regular expressions as defined by the .NET language.</span></span> <span data-ttu-id="eccee-116">Поэтому можно использовать выражения, подобные следующему: `((.Helmets.*Fenders.*)|(.*Fenders.*Helmets.*))`.</span><span class="sxs-lookup"><span data-stu-id="eccee-116">Therefore, you can use expressions such as the following: `((.Helmets.*Fenders.*)|(.*Fenders.*Helmets.*))`.</span></span> <span data-ttu-id="eccee-117">Это выражение возвращает все наборы элементов, содержащие атрибуты со словами Helmets и Fenders в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="eccee-117">This expression would return any itemsets that include attributes with the words Helmets and Fenders, in any order.</span></span>  
  
4.  <span data-ttu-id="eccee-118">В поле **Минимальная вероятность**повысьте значение вероятности, чтобы отобразить меньше правил, или понизьте значение, чтобы показать больше правил.</span><span class="sxs-lookup"><span data-stu-id="eccee-118">For **Minimum probability**, increase the value of probability to see fewer rules, or decrease the value to see more rules.</span></span>  
  
5.  <span data-ttu-id="eccee-119">В поле **Минимальная важность**повысьте значение важности, чтобы отобразить меньше правил, или понизьте значение, чтобы показать больше правил.</span><span class="sxs-lookup"><span data-stu-id="eccee-119">For **Minimum importance**, increase the value of importance to see fewer rules, or decrease the value to see more rules.</span></span>  
  
6.  <span data-ttu-id="eccee-120">Для функции **Показать**выберите один из следующих параметров: **Отобразить имя и значение атрибута**, **Отобразить только имя атрибута**или **Отобразить только значение атрибута**.</span><span class="sxs-lookup"><span data-stu-id="eccee-120">For **Show**, select one of the following options: **Show attribute name and value**, **Show attribute name only**, or **Show attribute value only**.</span></span>  
  
7.  <span data-ttu-id="eccee-121">В поле **Максимальное число строк**повысьте значение, чтобы увеличить общее количество правил, удовлетворяющих указанным условиям, или понизьте значение, чтобы ограничить число возвращаемых правил.</span><span class="sxs-lookup"><span data-stu-id="eccee-121">For **Maximum rows**, increase the value to increase the total number of rules that meet the specified conditions, or decrease the value to limit the number of rules returned.</span></span> <span data-ttu-id="eccee-122">Правила упорядочиваются по вероятности, поэтому можно исключить дополнительные правила, удовлетворяющие условиям для вероятности или важности.</span><span class="sxs-lookup"><span data-stu-id="eccee-122">Rules are ordered by probability, so you might eliminate additional rules that meet the specified conditions for probability or importance.</span></span>  
  
8.  <span data-ttu-id="eccee-123">Установите или снимите флажок **Показывать длинное имя** , чтобы изменить способ отображения имен правил.</span><span class="sxs-lookup"><span data-stu-id="eccee-123">Select or deselect the **Show long name** check box to toggle the way that the rules names are displayed.</span></span>  
  
     <span data-ttu-id="eccee-124">Теперь правила отфильтрованы так, что отображаются только правила, содержащие указанный элемент.</span><span class="sxs-lookup"><span data-stu-id="eccee-124">The rules are now filtered to only display rules that contain the indicated item.</span></span> <span data-ttu-id="eccee-125">Условие фильтра применяется к значениям атрибутов до или после разделителя правила «->».</span><span class="sxs-lookup"><span data-stu-id="eccee-125">The filter condition applies to attribute values either before or after the rule delimiter, "->".</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="eccee-126">Средство просмотра помещает в кэш первоначальный список правил на основании запроса к модели интеллектуального анализа данных и не обновляет список правил, если не изменить условия запроса путем указания параметров максимального числа строк, вероятности, важности или отображения длинных имен.</span><span class="sxs-lookup"><span data-stu-id="eccee-126">The viewer caches the initial list of rules, based on a query to the mining model, and does not refresh the list of rules unless you change the conditions of the query by setting the maximum rows, the probability, importance, or the display of long names.</span></span> <span data-ttu-id="eccee-127">Поэтому, если после ввода условия отображаемые элементы не обновляются немедленно, можно вызвать принудительное обновление данных в средстве просмотра, установив и сняв флажок **Показывать длинное имя** .</span><span class="sxs-lookup"><span data-stu-id="eccee-127">Therefore, if you type a condition and the display does not immediately refresh, you can force the viewer to refresh the data by selecting and then deselecting the **Show long names** check box.</span></span>  
  
### <a name="create-a-query-on-the-itemsets-in-an-association-model"></a><span data-ttu-id="eccee-128">Создание запроса к наборам элементов в модели взаимосвязей</span><span class="sxs-lookup"><span data-stu-id="eccee-128">Create a query on the itemsets in an association model</span></span>  
  
-   [<span data-ttu-id="eccee-129">Примеры запросов моделей взаимосвязей</span><span class="sxs-lookup"><span data-stu-id="eccee-129">Association Model Query Examples</span></span>](association-model-query-examples.md)  
  
## <a name="see-also"></a><span data-ttu-id="eccee-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="eccee-130">See Also</span></span>  
 <span data-ttu-id="eccee-131">[Задачи и инструкции средства просмотра моделей интеллектуального анализа данных](mining-model-viewer-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="eccee-131">[Mining Model Viewer Tasks and How-tos](mining-model-viewer-tasks-and-how-tos.md) </span></span>  
 <span data-ttu-id="eccee-132">[Просмотр модели с помощью средства просмотра правил взаимосвязей (Майкрософт)](browse-a-model-using-the-microsoft-association-rules-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="eccee-132">[Browse a Model Using the Microsoft Association Rules Viewer](browse-a-model-using-the-microsoft-association-rules-viewer.md) </span></span>  
 [<span data-ttu-id="eccee-133">Урок 3. Построение сценария покупательского поведения (учебник по интеллектуальному анализу данных — средний уровень)</span><span class="sxs-lookup"><span data-stu-id="eccee-133">Lesson 3: Building a Market Basket Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../tutorials/lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial.md)  
  
  
