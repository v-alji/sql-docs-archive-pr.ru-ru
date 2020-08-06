---
title: Задача 1. определение политики сопоставления | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 6f89a720-fce5-4f60-bef3-a159bbc9f25c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: bb2556874174939c46d91c6d89e797393d590914
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655477"
---
# <a name="task-1-defining-a-matching-policy"></a><span data-ttu-id="360ba-102">Задача 1. Определение политики сопоставления</span><span class="sxs-lookup"><span data-stu-id="360ba-102">Task 1: Defining a Matching Policy</span></span>
  <span data-ttu-id="360ba-103">В этой задаче будет создана политика проверки соответствия с одним правилом.</span><span class="sxs-lookup"><span data-stu-id="360ba-103">In this task, you create a matching policy with one rule in it.</span></span> <span data-ttu-id="360ba-104">Правило будет иметь один обязательный компонент: **идентификатор поставщика**. Это означает, что идентификаторы поставщиков должны совпадать, прежде чем использовать другие домены в правиле.</span><span class="sxs-lookup"><span data-stu-id="360ba-104">The rule will have one prerequisite: **Supplier ID**, which means that the Supplier IDs must match before using the other domains in the rule.</span></span> <span data-ttu-id="360ba-105">Правило использует два других домена: **имя поставщика** со значением **подобия** , установленным **в 70%** , и **контактный адрес электронной почты** со значением **подобия** , равным **30%**.</span><span class="sxs-lookup"><span data-stu-id="360ba-105">The rule uses two other domains: **Supplier Name** with **Similarity** value set to **70%** and **Contact Email** with **Similarity** value set to **30%**.</span></span>  
  
1.  <span data-ttu-id="360ba-106">На главной странице **клиента DQS**щелкните **стрелку вправо** рядом с базой знаний **поставщики** и выберите **Политика сопоставления**.</span><span class="sxs-lookup"><span data-stu-id="360ba-106">In the main page of **DQS Client**, click **right-arrow** next to **Suppliers** knowledge base, and select **Matching Policy**.</span></span>  
  
     <span data-ttu-id="360ba-107">![Меню «Политика сопоставления» на главной странице](../../2014/tutorials/media/et-definingamatchingpolicy-01.jpg "Меню «Политика сопоставления» на главной странице")</span><span class="sxs-lookup"><span data-stu-id="360ba-107">![Matching Policy Menu on Main Page](../../2014/tutorials/media/et-definingamatchingpolicy-01.jpg "Matching Policy Menu on Main Page")</span></span>  
  
2.  <span data-ttu-id="360ba-108">На странице " **схема** " выберите **файл Excel** для **источника данных**.</span><span class="sxs-lookup"><span data-stu-id="360ba-108">On the **Map** page, select **Excel File** for **Data Source**.</span></span>  
  
3.  <span data-ttu-id="360ba-109">Нажмите кнопку **Обзор**, убедитесь, что для фильтра задано значение **Книга Excel**, и выберите элемент **очищенный поставщик List.xls** файл, экспортированный после выполнения действия Очистка.</span><span class="sxs-lookup"><span data-stu-id="360ba-109">Click **Browse**, ensure that filter is set to **Excel Workbook**, and select **Cleansed Supplier List.xls** file that you exported after you perform the cleansing activity.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="360ba-110">После выполнения этих действий нельзя экспортировать результаты, поскольку действие в основном ориентировано на определение политики проверки соответствия.</span><span class="sxs-lookup"><span data-stu-id="360ba-110">At the end of this activity, you cannot export results because this activity is primarily focused on defining a matching policy.</span></span> <span data-ttu-id="360ba-111">Вы создадите проект качества данных для действия сопоставления и выполните его для удаления повторений из списка поставщиков с помощью политики проверки соответствия на следующем занятии.</span><span class="sxs-lookup"><span data-stu-id="360ba-111">You will create a Data Quality Project for the Matching activity and run it to remove duplicates from the supplier list by using this matching policy in the next lesson.</span></span>  
  
4.  <span data-ttu-id="360ba-112">Сопоставьте столбец « **КодПоставщика** » с **идентификатором поставщика** домен, **имя поставщика** в столбце **имя поставщика** домен, **ContactEmailAddress** столбец, чтобы связаться с доменом **электронной почты** .</span><span class="sxs-lookup"><span data-stu-id="360ba-112">Map **SupplierID** column to **Supplier ID** domain, **Supplier Name** column to **Supplier Name** domain, **ContactEmailAddress** column to **Contact Email** domain.</span></span> <span data-ttu-id="360ba-113">Необходимо сопоставить исходные столбцы лишь с доменами, которые должны использоваться при определении политики проверки соответствия.</span><span class="sxs-lookup"><span data-stu-id="360ba-113">You only need to map source columns to domains that you want to use in defining the matching policy.</span></span> <span data-ttu-id="360ba-114">В этом случае пользователь задает домены идентификатора поставщика, имени поставщика и электронной почты контактного лица как доступные для политики проверки соответствия.</span><span class="sxs-lookup"><span data-stu-id="360ba-114">In this case, you are making the Supplier ID, Supplier Name, and Contact Email domains available for the matching policy activity.</span></span>  
  
     <span data-ttu-id="360ba-115">![Страница сопоставления процесса определения политики сопоставления](../../2014/tutorials/media/et-definingamatchingpolicy-02.jpg "Страница сопоставления процесса определения политики сопоставления")</span><span class="sxs-lookup"><span data-stu-id="360ba-115">![Map Page of Matching Policy Definition Process](../../2014/tutorials/media/et-definingamatchingpolicy-02.jpg "Map Page of Matching Policy Definition Process")</span></span>  
  
5.  <span data-ttu-id="360ba-116">Нажмите кнопку **Далее** , чтобы перейти на страницу **Политика сопоставления** , в которой будет определена политика сопоставления с одним правилом.</span><span class="sxs-lookup"><span data-stu-id="360ba-116">Click **Next** to move to the **Matching Policy** page where you will be defining a matching policy with one rule in it.</span></span>  
  
6.  <span data-ttu-id="360ba-117">Чтобы создать правило в политике, нажмите кнопку **создать правило сопоставления** на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="360ba-117">Click **Create a matching rule** button on the toolbar to create a rule in the policy.</span></span>  
  
     <span data-ttu-id="360ba-118">![Кнопка панели инструментов «Создать правило сопоставления»](../../2014/tutorials/media/et-definingamatchingpolicy-03.jpg "Кнопка панели инструментов «Создать правило сопоставления»")</span><span class="sxs-lookup"><span data-stu-id="360ba-118">![Create a Matching Rule Toolbar Button](../../2014/tutorials/media/et-definingamatchingpolicy-03.jpg "Create a Matching Rule Toolbar Button")</span></span>  
  
7.  <span data-ttu-id="360ba-119">На панели **сведения о правиле** справа введите **Удалить дубликаты поставщиков** в качестве **имени правила**.</span><span class="sxs-lookup"><span data-stu-id="360ba-119">In the **Rule Details** pane on the right, enter **Remove Duplicate Suppliers** for the **Rule name**.</span></span>  
  
8.  <span data-ttu-id="360ba-120">Щелкните **Добавить новый элемент домена** на панели инструментов в правой области.</span><span class="sxs-lookup"><span data-stu-id="360ba-120">Click **Add a new domain element** in the toolbar in the right pane.</span></span>  
  
     <span data-ttu-id="360ba-121">![Подробности правила — кнопка «Добавить новый элемент домена»](../../2014/tutorials/media/et-definingamatchingpolicy-04.jpg "Подробности правила — кнопка «Добавить новый элемент домена»")</span><span class="sxs-lookup"><span data-stu-id="360ba-121">![Rule Details - Add a New Domain Element Button](../../2014/tutorials/media/et-definingamatchingpolicy-04.jpg "Rule Details - Add a New Domain Element Button")</span></span>  
  
9. <span data-ttu-id="360ba-122">Выберите **идентификатор поставщика** для **домена** и установите флажок необходимый **компонент** .</span><span class="sxs-lookup"><span data-stu-id="360ba-122">Select **Supplier ID** for the **domain** and select the **Prerequisite** check box.</span></span> <span data-ttu-id="360ba-123">Обратите внимание, что для параметра **подобие** автоматически устанавливается значение **точное**.</span><span class="sxs-lookup"><span data-stu-id="360ba-123">Notice that **Similarity** is automatically set to **Exact**.</span></span> <span data-ttu-id="360ba-124">Установив **идентификатор поставщика** в качестве **необходимого компонента**, вы указываете, что значения этого поля в двух записях должны возвращать 100% совпадения, иначе записи не считаются совпадением, а другие предложения в правиле не учитываются.</span><span class="sxs-lookup"><span data-stu-id="360ba-124">By setting **Supplier ID** as the **Prerequisite**, you specify that the values for this field in the two records must return a 100% match, else the records are not considered a match and the other clauses in the rule are disregarded.</span></span>  
  
     <span data-ttu-id="360ba-125">![Определение правила удаления дублирующихся поставщиков](../../2014/tutorials/media/et-definingamatchingpolicy-05.jpg "Определение правила удаления дублирующихся поставщиков")</span><span class="sxs-lookup"><span data-stu-id="360ba-125">![Remove Duplicate Suppliers Rule Definition](../../2014/tutorials/media/et-definingamatchingpolicy-05.jpg "Remove Duplicate Suppliers Rule Definition")</span></span>  
  
10. <span data-ttu-id="360ba-126">Снова нажмите кнопку **Добавить новый элемент домена** на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="360ba-126">Click **Add a new domain element** from the toolbar again.</span></span>  
  
11. <span data-ttu-id="360ba-127">Выберите **имя поставщика** домен, выберите **аналогичный** для **подобия**и введите **70** для **веса**.</span><span class="sxs-lookup"><span data-stu-id="360ba-127">Select **Supplier Name** domain, select **Similar** for **Similarity**, and Type **70** for the **Weight**.</span></span>  <span data-ttu-id="360ba-128">Здесь указывается, что имена поставщика не обязательно должны быть одинаковыми, но могут быть похожими, чтобы считать записи соответствующими.</span><span class="sxs-lookup"><span data-stu-id="360ba-128">Here, you are specifying that supplier names do not need to be identical but can be similar for the records to be considered as a match.</span></span> <span data-ttu-id="360ba-129">Вес указывает вклад оценки этого поля в общий показатель сопоставления.</span><span class="sxs-lookup"><span data-stu-id="360ba-129">The weight indicates the contribution of this field's score to the overall matching score.</span></span>  
  
12. <span data-ttu-id="360ba-130">Повторите предыдущие два шага для добавления **контактного домена электронной почты** с **30** для **веса**.</span><span class="sxs-lookup"><span data-stu-id="360ba-130">Repeat previous two steps to add **Contact Email** domain with **30** for the **Weight**.</span></span>  
  
13. <span data-ttu-id="360ba-131">Обратите внимание, что для параметра **минимальный показатель сопоставления** задано значение **80%**, которое отображается на вкладке **Общие** страницы **Конфигурация** в разделе **Администрирование служб DQS**.</span><span class="sxs-lookup"><span data-stu-id="360ba-131">Notice that the **min matching score** is set to **80%**, which is the value you see in the **General** tab of the **Configuration** page of **DQS Administration**.</span></span> <span data-ttu-id="360ba-132">Можно только увеличить эту оценку сверх указанного порогового значения.</span><span class="sxs-lookup"><span data-stu-id="360ba-132">You can only increase this score above this threshold value here.</span></span>  
  
14. <span data-ttu-id="360ba-133">Обратите внимание, что выбран параметр **Перекрывающиеся кластеры** .</span><span class="sxs-lookup"><span data-stu-id="360ba-133">Notice that **Overlapping Clusters** option is selected.</span></span> <span data-ttu-id="360ba-134">Если выбран этот параметр, запись может отображаться в нескольких кластерах.</span><span class="sxs-lookup"><span data-stu-id="360ba-134">With this option, a record can show up in multiple clusters.</span></span> <span data-ttu-id="360ba-135">Если изменить значение параметра на неперекрывающиеся кластеры, то кластеры, которые имеют общие записи, объединяются в один кластер.</span><span class="sxs-lookup"><span data-stu-id="360ba-135">If you change the setting to Non-Overlapping Clusters, the clusters that have common records are combined into one single cluster.</span></span>  
  
15. <span data-ttu-id="360ba-136">Кнопка **запустить** на этой странице позволяет протестировать каждое правило в политике отдельно, тогда как кнопка запустить на следующей странице позволяет протестировать всю политику (все правила в политике).</span><span class="sxs-lookup"><span data-stu-id="360ba-136">The **Start** button on this page allows you to test each rule in the policy separately, whereas, the Start button in the next page allows you to test entire policy (all the rules in the policy).</span></span>  
  
16. <span data-ttu-id="360ba-137">Нажмите кнопку **Далее** , чтобы перейти на страницу **Результаты сопоставления** .</span><span class="sxs-lookup"><span data-stu-id="360ba-137">Click **Next** to switch to the **Matching Results** page.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="360ba-138">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="360ba-138">Next Step</span></span>  
 [<span data-ttu-id="360ba-139">Задача 2. Тестирование и публикация политики проверки сопоставления</span><span class="sxs-lookup"><span data-stu-id="360ba-139">Task 2: Testing and Publishing the Matching Policy</span></span>](../../2014/tutorials/task-2-testing-and-publishing-the-matching-policy.md)  
  
  