---
title: Задача 2. Тестирование и публикация политики сопоставления | Документация Майкрософт
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: e1ffb6d7-fbc5-4695-b538-cc2302d1a17d
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 88bed2e91ca1fee3eab6136fb94df0d13328dc80
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666916"
---
# <a name="task-2-testing-and-publishing-the-matching-policy"></a><span data-ttu-id="20815-102">Задача 2. Тестирование и публикация политики проверки сопоставления</span><span class="sxs-lookup"><span data-stu-id="20815-102">Task 2: Testing and Publishing the Matching Policy</span></span>
  <span data-ttu-id="20815-103">В этой задаче выполняется проверка и публикация политики сопоставления **Удаление повторяющихся поставщиков** .</span><span class="sxs-lookup"><span data-stu-id="20815-103">In this task, you test and publish the **Remove Duplicate Suppliers** matching policy.</span></span>  
  
1.  <span data-ttu-id="20815-104">На странице **Результаты сопоставления** нажмите кнопку **запустить** , чтобы протестировать всю политику.</span><span class="sxs-lookup"><span data-stu-id="20815-104">In the **Matching Results** page, click **Start** to test the entire policy.</span></span> <span data-ttu-id="20815-105">В вашем случае в политике всего одно правило, поэтому результаты проверки правила и политики должны совпадать.</span><span class="sxs-lookup"><span data-stu-id="20815-105">In your case, you have only rule in the policy, so the results from testing the rule and the policy should be the same.</span></span>  
  
2.  <span data-ttu-id="20815-106">Просмотрите все сопоставленные записи и соответствующие оценки в списке.</span><span class="sxs-lookup"><span data-stu-id="20815-106">Review all the matched records and their matching score in the list box.</span></span> <span data-ttu-id="20815-107">Запись с **зеленым** значком, связанная с ним, является дубликатом сводной записи, предшествующей ей.</span><span class="sxs-lookup"><span data-stu-id="20815-107">A record that has a **Green** icon associated with it is a duplicate of the pivot record that precedes it.</span></span> <span data-ttu-id="20815-108">Вот несколько примеров.</span><span class="sxs-lookup"><span data-stu-id="20815-108">Here are couple of examples:</span></span>  
  
    1.  <span data-ttu-id="20815-109">Запись с **идентификатором записи: 1000005** является совпадением записи с **идентификатором записи: 1000004** с **Score: 100%** , так как обе записи имеют одинаковые значения для **КодПоставщика (необходимое условие)**, **имя поставщика**и **ContactEmailAddress столбцы**.</span><span class="sxs-lookup"><span data-stu-id="20815-109">The record with **Record ID: 1000005** is a match of the record with **Record Id: 1000004** with **Score: 100%** because both the records have the same values for **SupplierID (prerequisite)**, **Supplier Name**, and **ContactEmailAddress columns**.</span></span> <span data-ttu-id="20815-110">DQS произвольно выбирает запись в качестве сводной записи для кластера.</span><span class="sxs-lookup"><span data-stu-id="20815-110">DQS randomly picks a record as the pivot record for a cluster.</span></span>  
  
    2.  <span data-ttu-id="20815-111">Запись **1000023** является совпадением записи **1000022** с показателем сопоставления: 93%, так как две записи имеют одинаковые значения для столбцов « **КодПоставщика» (необходимое условие)** и « **имя поставщика** », но разные значения для столбца **ContactEmailAddress** .</span><span class="sxs-lookup"><span data-stu-id="20815-111">The record **1000023** is a match of the record **1000022** with the matching score: 93% because the two records have the same values for **SupplierID (prerequisite)** and **Supplier Name** columns, but different values for the **ContactEmailAddress** column.</span></span>  
  
    3.  <span data-ttu-id="20815-112">Прокрутите список до нижней части, чтобы увидеть две записи с идентификаторами: **1000051** и **1000052**.</span><span class="sxs-lookup"><span data-stu-id="20815-112">Scroll to the bottom of the list to see two records with records IDs: **1000051** and **1000052**.</span></span> <span data-ttu-id="20815-113">Запись **1000052** считается совпадением с рейтингом **91%** , поскольку две записи имеют одинаковые значения для столбцов « **КодПоставщика** » и « **ContactEmailAddress** », но разные значения для столбца « **имя поставщика** ».</span><span class="sxs-lookup"><span data-stu-id="20815-113">Record **1000052** is considered a match with matching score **91%** because the two records have the same values for the **SupplierID** and **ContactEmailAddress** columns, but different values for the **Supplier Name** column.</span></span>  
  
     <span data-ttu-id="20815-114">![Определение политики — результаты политики](../../2014/tutorials/media/et-testingandpublishingthematchingpolicy-01.jpg "Определение политики — результаты политики")</span><span class="sxs-lookup"><span data-stu-id="20815-114">![Policy Definition - Policy Results](../../2014/tutorials/media/et-testingandpublishingthematchingpolicy-01.jpg "Policy Definition - Policy Results")</span></span>  
  
3.  <span data-ttu-id="20815-115">Щелкните правой кнопкой мыши любую совпадающую запись (с зеленым значком) и выберите **Просмотреть сведения** , чтобы просмотреть дополнительные сведения о сопоставлении, например вклад каждой оценки поля в общий показатель сопоставления.</span><span class="sxs-lookup"><span data-stu-id="20815-115">Right-click on any matched record (with green icon) and click **View Details** to see more details about the matching such as contribution of each field score to the overall matching score.</span></span>  
  
     <span data-ttu-id="20815-116">![Диалоговое окно «Подробные сведения о показателе сопоставления»](../../2014/tutorials/media/et-testingandpublishingthematchingpolicy-02.jpg "Диалоговое окно «Подробные сведения о показателе сопоставления»")</span><span class="sxs-lookup"><span data-stu-id="20815-116">![Matching Score Details Dialog Box](../../2014/tutorials/media/et-testingandpublishingthematchingpolicy-02.jpg "Matching Score Details Dialog Box")</span></span>  
  
4.  <span data-ttu-id="20815-117">Нажмите кнопку **Закрыть** , чтобы закрыть диалоговое окно **сведения о показателе сопоставления** .</span><span class="sxs-lookup"><span data-stu-id="20815-117">Click **Close** to close the **Matching Score Details** dialog box.</span></span>  
  
5.  <span data-ttu-id="20815-118">Щелкните вкладку **Результаты сопоставления** в нижней части страницы.</span><span class="sxs-lookup"><span data-stu-id="20815-118">Click **Matching Results** tab at the bottom of the page.</span></span> <span data-ttu-id="20815-119">На этой вкладке представлены различные сведения, например число сопоставленных записей, число несопоставленных записей, число кластеров с сопоставленными записями, средний, минимальный и максимальный размер кластера.</span><span class="sxs-lookup"><span data-stu-id="20815-119">This tab gives you detail such as number of matched records, number of unmatched records, number of clusters with matched records, the average cluster size, minimum cluster size, and maximum cluster size.</span></span> <span data-ttu-id="20815-120">Дополнительные сведения см. [в разделе Создание политики сопоставления](https://msdn.microsoft.com/library/hh270290.aspx) .</span><span class="sxs-lookup"><span data-stu-id="20815-120">See [Create a Matching Policy](https://msdn.microsoft.com/library/hh270290.aspx) for more details.</span></span> <span data-ttu-id="20815-121">Результаты этой операции нельзя экспортировать.</span><span class="sxs-lookup"><span data-stu-id="20815-121">You cannot export results from this activity.</span></span> <span data-ttu-id="20815-122">Вы просто задаете политику проверки соответствия с помощью образца данных для проверки правил и политики на основе образца данных.</span><span class="sxs-lookup"><span data-stu-id="20815-122">You are just defining a matching policy by using the sample data to test rules and the policy against the sample data.</span></span>  
  
     <span data-ttu-id="20815-123">![Вкладка «результаты сопоставления»](../../2014/tutorials/media/et-testingandpublishingthematchingpolicy-03.jpg "Вкладка «Результаты сопоставления»")</span><span class="sxs-lookup"><span data-stu-id="20815-123">![Matching Results Tab](../../2014/tutorials/media/et-testingandpublishingthematchingpolicy-03.jpg "Matching Results Tab")</span></span>  
  
6.  <span data-ttu-id="20815-124">Нажмите кнопку **Готово** , чтобы завершить создание политики сопоставления.</span><span class="sxs-lookup"><span data-stu-id="20815-124">Click **Finish** to finish creating the matching policy.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="20815-125">В этой задаче вы определили политику проверки соответствия здесь, поэтому не можете экспортировать результаты в выходной файл.</span><span class="sxs-lookup"><span data-stu-id="20815-125">You have defined the matching policy here; therefore you cannot export results to an output file.</span></span> <span data-ttu-id="20815-126">По существу вы использовали пример входного файла, создали правила, проверили правила и политику на основе образцов данных, чтобы определить политику.</span><span class="sxs-lookup"><span data-stu-id="20815-126">You basically used a sample input file, created rules, and tested the rules and policy against the sample data with the goal of defining the policy.</span></span>  
  
7.  <span data-ttu-id="20815-127">В диалоговом окне SQL Server Data Quality Services нажмите кнопку **опубликовать** и нажмите кнопку **ОК** в окне сообщения.</span><span class="sxs-lookup"><span data-stu-id="20815-127">In the SQL Server Data Quality Services dialog box, click **Publish** and click **OK** on the message box.</span></span> <span data-ttu-id="20815-128">Теперь определенная политика сопоставления публикуется в базе знаний **поставщики** .</span><span class="sxs-lookup"><span data-stu-id="20815-128">Now, the matching policy you defined is published into the **Suppliers** Knowledge Base.</span></span> <span data-ttu-id="20815-129">Вы можете использовать ее для сопоставления входного файла в целях обнаружения и удаления повторений.</span><span class="sxs-lookup"><span data-stu-id="20815-129">You can use the knowledge base to run the matching process against an input file to identify and remove duplicates.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="20815-130">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="20815-130">Next Step</span></span>  
 [<span data-ttu-id="20815-131">Задача 3. Создание и запуск проекта качества данных для сопоставления</span><span class="sxs-lookup"><span data-stu-id="20815-131">Task 3: Creating and Running a Data Quality Project for Matching</span></span>](../../2014/tutorials/task-3-creating-and-running-a-data-quality-project-for-matching.md)  
  
  