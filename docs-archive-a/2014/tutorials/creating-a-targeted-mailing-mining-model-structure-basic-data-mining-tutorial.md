---
title: Создание структуры модели интеллектуального анализа данных с целевой корреспонденцией (учебник по интеллектуальному анализу данных — базовый) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a9c67f29-0c47-4a5a-862b-db0f5213c2c9
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 6a27f818b29120e40248044091c78205dad945bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734726"
---
# <a name="creating-a-targeted-mailing-mining-model-structure-basic-data-mining-tutorial"></a><span data-ttu-id="94d0d-102">Создание структуры модели интеллектуального анализа данных прямой почтовой рассылки (учебник по интеллектуальному анализу данных — начальный уровень)</span><span class="sxs-lookup"><span data-stu-id="94d0d-102">Creating a Targeted Mailing Mining Model Structure (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="94d0d-103">Первым шагом в создании сценария прямой почтовой рассылки является использование мастера интеллектуального анализа данных среды [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] для создания новой структуры интеллектуального анализа данных и модели интеллектуального анализа данных дерева принятия решений.</span><span class="sxs-lookup"><span data-stu-id="94d0d-103">The first step in creating a targeted mailing scenario is to use the Data Mining Wizard in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to create a new mining structure and decision tree mining model.</span></span>  
  
 <span data-ttu-id="94d0d-104">В этой задаче вы настроите новую структуру интеллектуального анализа данных и добавите исходную модель интеллектуального анализа данных на основе [!INCLUDE[msCoName](../includes/msconame-md.md)] алгоритма дерева принятия решений.</span><span class="sxs-lookup"><span data-stu-id="94d0d-104">In this task you will set up a new mining structure, and add an initial mining model based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees algorithm.</span></span> <span data-ttu-id="94d0d-105">Для создания такой структуры сначала необходимо выбрать таблицы и представления, а затем указать столбцы для обучения и столбцы для проверки.</span><span class="sxs-lookup"><span data-stu-id="94d0d-105">To create the structure, you will first select tables and views and then identify which columns will be used for training and which for testing.</span></span>  
  
### <a name="to-create-a-mining-structure-for-the-targeted-mailing-scenario"></a><span data-ttu-id="94d0d-106">Создание структуры интеллектуального анализа данных для сценария прямой почтовой рассылки</span><span class="sxs-lookup"><span data-stu-id="94d0d-106">To create a mining structure for the targeted mailing scenario</span></span>  
  
1.  <span data-ttu-id="94d0d-107">В обозреватель решений щелкните правой кнопкой мыши элемент **структуры интеллектуального анализа** данных и выберите **создать структуру интеллектуального анализа** данных, чтобы запустить мастер интеллектуального анализа.</span><span class="sxs-lookup"><span data-stu-id="94d0d-107">In Solution Explorer, right-click **Mining Structures** and select **New Mining Structure** to start the Data Mining Wizard.</span></span>  
  
2.  <span data-ttu-id="94d0d-108">На странице **Вас приветствует мастер интеллектуального анализа данных** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="94d0d-108">On the **Welcome to the Data Mining Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="94d0d-109">На странице **Выбор метода определения** убедитесь, что выбран параметр **из существующей реляционной базы данных или хранилища данных** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="94d0d-109">On the **Select the Definition Method** page, verify that **From existing relational database or data warehouse** is selected, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="94d0d-110">На странице **Создание структуры интеллектуального анализа данных** , в **которой вы хотите использовать метод интеллектуального анализа данных**, выберите пункт **деревья решений (Майкрософт**).</span><span class="sxs-lookup"><span data-stu-id="94d0d-110">On the **Create the Data Mining Structure** page, under **Which data mining technique do you want to use?**, select **Microsoft Decision Trees**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="94d0d-111">Если появится предупреждение о том, что алгоритмов интеллектуального анализа данных не обнаружено, это может означать, что свойства проекта настроены неправильно.</span><span class="sxs-lookup"><span data-stu-id="94d0d-111">If you get a warning that no data mining algorithms can be found, the project properties might not be configured correctly.</span></span> <span data-ttu-id="94d0d-112">Это предупреждение выдается, только когда проект пытается получить список алгоритмов интеллектуального анализа данных с сервера служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] и не находит сервера.</span><span class="sxs-lookup"><span data-stu-id="94d0d-112">This warning occurs when the project attempts to retrieve a list of data mining algorithms from the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server and cannot find the server.</span></span> <span data-ttu-id="94d0d-113">По умолчанию [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] будет использовать **localhost** в качестве сервера.</span><span class="sxs-lookup"><span data-stu-id="94d0d-113">By default, [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] will use **localhost** as the server.</span></span> <span data-ttu-id="94d0d-114">Если используется другой экземпляр или именованный экземпляр, нужно изменить свойства проекта.</span><span class="sxs-lookup"><span data-stu-id="94d0d-114">If you are using a different instance, or a named instance, you must change the project properties.</span></span> <span data-ttu-id="94d0d-115">Дополнительные сведения см. в разделе [создание Analysis Services проекта &#40;учебник по основам интеллектуального анализа данных&#41;](../../2014/tutorials/creating-an-analysis-services-project-basic-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="94d0d-115">For more information, see [Creating an Analysis Services Project &#40;Basic Data Mining Tutorial&#41;](../../2014/tutorials/creating-an-analysis-services-project-basic-data-mining-tutorial.md).</span></span>  
  
5.  <span data-ttu-id="94d0d-116">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="94d0d-116">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="94d0d-117">На странице **Выбор представления источника данных** на панели **Доступные представления источников данных** выберите **Целевая рассылка**.</span><span class="sxs-lookup"><span data-stu-id="94d0d-117">On the **Select Data Source View** page, in the **Available data source views** pane, select **Targeted Mailing**.</span></span> <span data-ttu-id="94d0d-118">Можно нажать кнопку **Обзор** , чтобы просмотреть таблицы в представлении источника данных, а затем нажать кнопку **Закрыть** , чтобы вернуться к мастеру.</span><span class="sxs-lookup"><span data-stu-id="94d0d-118">You can click **Browse** to view the tables in the data source view and then click **Close** to return to the wizard.</span></span>  
  
7.  <span data-ttu-id="94d0d-119">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="94d0d-119">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="94d0d-120">На странице **Выбор типов таблиц** установите флажок в столбце **вариант** для vTargetMail, чтобы использовать его в качестве таблицы вариантов, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="94d0d-120">On the **Specify Table Types** page, select the check box in the **Case** column for vTargetMail to use it as the case table, and then click **Next**.</span></span> <span data-ttu-id="94d0d-121">Таблица ProspectiveBuyer будет использоваться позже в целях проверки, поэтому на данном этапе ее не нужно учитывать.</span><span class="sxs-lookup"><span data-stu-id="94d0d-121">You will use the ProspectiveBuyer table later for testing; ignore it for now.</span></span>  
  
9. <span data-ttu-id="94d0d-122">На странице **Определение обучающих данных** будет определен как минимум один прогнозируемый столбец, один ключевой столбец и один входной столбец для модели.</span><span class="sxs-lookup"><span data-stu-id="94d0d-122">On the **Specify the Training Data** page, you will identify at least one predictable column, one key column, and one input column for your model.</span></span> <span data-ttu-id="94d0d-123">Установите флажок в столбце **прогнозируемый** в строке **BikeBuyer** .</span><span class="sxs-lookup"><span data-stu-id="94d0d-123">Select the check box in the **Predictable** column in the **BikeBuyer** row.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="94d0d-124">Обратите внимание на предупреждение в нижней части окна.</span><span class="sxs-lookup"><span data-stu-id="94d0d-124">Notice the warning at the bottom of the window.</span></span> <span data-ttu-id="94d0d-125">Вы не сможете переходить к следующей странице, пока не выберете хотя бы один **входной** и один **прогнозируемый** столбец.</span><span class="sxs-lookup"><span data-stu-id="94d0d-125">You will not be able to navigate to the next page until you select at least one **Input** and one **Predictable** column.</span></span>  
  
10. <span data-ttu-id="94d0d-126">Нажмите кнопку **предложить** , чтобы открыть диалоговое окно **предложение связанных столбцов** .</span><span class="sxs-lookup"><span data-stu-id="94d0d-126">Click **Suggest** to open the **Suggest Related Columns** dialog box.</span></span>  
  
     <span data-ttu-id="94d0d-127">Кнопка **предложить** включается, если выбран хотя бы один прогнозируемый атрибут.</span><span class="sxs-lookup"><span data-stu-id="94d0d-127">The **Suggest** button is enabled whenever at least one predictable attribute has been selected.</span></span> <span data-ttu-id="94d0d-128">Диалоговое окно **предложение связанных столбцов** содержит список столбцов, наиболее тесно связанных с прогнозируемым столбцом, и упорядочивает атрибуты по их корреляции с прогнозируемым атрибутом.</span><span class="sxs-lookup"><span data-stu-id="94d0d-128">The **Suggest Related Columns** dialog box lists the columns that are most closely related to the predictable column, and orders the attributes by their correlation with the predictable attribute.</span></span> <span data-ttu-id="94d0d-129">Столбцы со значительной корреляцией (степень достоверности превышает 95 %) автоматически выделены как включаемые в модель.</span><span class="sxs-lookup"><span data-stu-id="94d0d-129">Columns with a significant correlation (confidence greater than 95%) are automatically selected to be included in the model.</span></span>  
  
     <span data-ttu-id="94d0d-130">Просмотрите предложения и нажмите кнопку **Отмена** , чтобы тоигноре предложения.</span><span class="sxs-lookup"><span data-stu-id="94d0d-130">Review the suggestions, and then click **Cancel** toignore the suggestions.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="94d0d-131">Если нажать кнопку **ОК**, все перечисленные предложения будут помечены в мастере как входные столбцы.</span><span class="sxs-lookup"><span data-stu-id="94d0d-131">If you click **OK**, all listed suggestions will be marked as input columns in the wizard.</span></span> <span data-ttu-id="94d0d-132">Если нужны не все предложения, значения придется изменять вручную.</span><span class="sxs-lookup"><span data-stu-id="94d0d-132">If you agree with only some of the suggestions, you must change the values manually.</span></span>  
  
11. <span data-ttu-id="94d0d-133">Убедитесь, что флажок в **ключевом** столбце выбран в строке **CustomerKey** .</span><span class="sxs-lookup"><span data-stu-id="94d0d-133">Verify that the check box in the **Key** column is selected in the **CustomerKey** row.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="94d0d-134">Если для таблицы с входными данными из представления источников данных указан ключ, мастер интеллектуального анализа данных автоматически выберет этот столбец в качестве ключа для модели.</span><span class="sxs-lookup"><span data-stu-id="94d0d-134">If the source table from the data source view indicates a key, the Data Mining Wizard automatically chooses that column as a key for the model.</span></span>  
  
12. <span data-ttu-id="94d0d-135">Установите флажки во **входном** столбце в следующих строках.</span><span class="sxs-lookup"><span data-stu-id="94d0d-135">Select the check boxes in the **Input** column in the following rows.</span></span> <span data-ttu-id="94d0d-136">Чтобы установить флажки в нескольких столбцах, можно выделить диапазон ячеек и удерживать нажатой клавишу CTRL при установке флажка.</span><span class="sxs-lookup"><span data-stu-id="94d0d-136">You can check multiple columns by highlighting a range of cells and pressing CTRL while selecting a check box.</span></span>  
  
    -   <span data-ttu-id="94d0d-137">**Возраст**</span><span class="sxs-lookup"><span data-stu-id="94d0d-137">**Age**</span></span>  
  
    -   <span data-ttu-id="94d0d-138">**CommuteDistance**</span><span class="sxs-lookup"><span data-stu-id="94d0d-138">**CommuteDistance**</span></span>  
  
    -   <span data-ttu-id="94d0d-139">**EnglishEducation**</span><span class="sxs-lookup"><span data-stu-id="94d0d-139">**EnglishEducation**</span></span>  
  
    -   <span data-ttu-id="94d0d-140">**EnglishOccupation**</span><span class="sxs-lookup"><span data-stu-id="94d0d-140">**EnglishOccupation**</span></span>  
  
    -   <span data-ttu-id="94d0d-141">**Gender**</span><span class="sxs-lookup"><span data-stu-id="94d0d-141">**Gender**</span></span>  
  
    -   <span data-ttu-id="94d0d-142">**GeographyKey**</span><span class="sxs-lookup"><span data-stu-id="94d0d-142">**GeographyKey**</span></span>  
  
    -   <span data-ttu-id="94d0d-143">**HouseOwnerFlag**</span><span class="sxs-lookup"><span data-stu-id="94d0d-143">**HouseOwnerFlag**</span></span>  
  
    -   <span data-ttu-id="94d0d-144">**MaritalStatus**</span><span class="sxs-lookup"><span data-stu-id="94d0d-144">**MaritalStatus**</span></span>  
  
    -   <span data-ttu-id="94d0d-145">**NumberCarsOwned**</span><span class="sxs-lookup"><span data-stu-id="94d0d-145">**NumberCarsOwned**</span></span>  
  
    -   <span data-ttu-id="94d0d-146">**NumberChildrenAtHome**</span><span class="sxs-lookup"><span data-stu-id="94d0d-146">**NumberChildrenAtHome**</span></span>  
  
    -   <span data-ttu-id="94d0d-147">**Регион**</span><span class="sxs-lookup"><span data-stu-id="94d0d-147">**Region**</span></span>  
  
    -   <span data-ttu-id="94d0d-148">**TotalChildren**</span><span class="sxs-lookup"><span data-stu-id="94d0d-148">**TotalChildren**</span></span>  
  
    -   <span data-ttu-id="94d0d-149">**YearlyIncome**</span><span class="sxs-lookup"><span data-stu-id="94d0d-149">**YearlyIncome**</span></span>  
  
13. <span data-ttu-id="94d0d-150">В крайнем левом столбце на странице установите флажки в перечисленных ниже строках.</span><span class="sxs-lookup"><span data-stu-id="94d0d-150">On the far left column of the page, select the check boxes in the following rows.</span></span>  
  
    -   <span data-ttu-id="94d0d-151">**AddressLine1**</span><span class="sxs-lookup"><span data-stu-id="94d0d-151">**AddressLine1**</span></span>  
  
    -   <span data-ttu-id="94d0d-152">**AddressLine2**</span><span class="sxs-lookup"><span data-stu-id="94d0d-152">**AddressLine2**</span></span>  
  
    -   <span data-ttu-id="94d0d-153">**DateFirstPurchase**</span><span class="sxs-lookup"><span data-stu-id="94d0d-153">**DateFirstPurchase**</span></span>  
  
    -   <span data-ttu-id="94d0d-154">**EmailAddress**</span><span class="sxs-lookup"><span data-stu-id="94d0d-154">**EmailAddress**</span></span>  
  
    -   <span data-ttu-id="94d0d-155">**FirstName**</span><span class="sxs-lookup"><span data-stu-id="94d0d-155">**FirstName**</span></span>  
  
    -   <span data-ttu-id="94d0d-156">**LastName**</span><span class="sxs-lookup"><span data-stu-id="94d0d-156">**LastName**</span></span>  
  
     <span data-ttu-id="94d0d-157">Убедитесь, что эти строки имеют флажки только в левом столбце.</span><span class="sxs-lookup"><span data-stu-id="94d0d-157">Ensure that these rows have checks only in the left column.</span></span> <span data-ttu-id="94d0d-158">Эти столбцы будут добавлены в структуру, но не будут включены в модель.</span><span class="sxs-lookup"><span data-stu-id="94d0d-158">These columns will be added to your structure but will not be included in the model.</span></span> <span data-ttu-id="94d0d-159">Однако после построения модели их можно будет использовать для детализации и проверки.</span><span class="sxs-lookup"><span data-stu-id="94d0d-159">However, after the model is built, they will be available for drillthrough and testing.</span></span> <span data-ttu-id="94d0d-160">Дополнительные сведения о детализации см. в разделе [запросы детализации &#40;интеллектуальный анализ данных&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md)</span><span class="sxs-lookup"><span data-stu-id="94d0d-160">For more information about drillthrough, see [Drillthrough Queries &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md)</span></span>  
  
14. <span data-ttu-id="94d0d-161">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="94d0d-161">Click **Next**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="94d0d-162">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="94d0d-162">Next Task in Lesson</span></span>  
 [<span data-ttu-id="94d0d-163">Выбор типа данных и типа содержимого &#40;учебник по базовому интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="94d0d-163">Specifying the Data Type and Content Type &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/specifying-the-data-type-and-content-type-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="94d0d-164">См. также:</span><span class="sxs-lookup"><span data-stu-id="94d0d-164">See Also</span></span>  
 <span data-ttu-id="94d0d-165">[Определение типов таблиц &#40;мастера интеллектуального анализа данных&#41;](../../2014/analysis-services/specify-table-types-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="94d0d-165">[Specify Table Types &#40;Data Mining Wizard&#41;](../../2014/analysis-services/specify-table-types-data-mining-wizard.md) </span></span>  
 <span data-ttu-id="94d0d-166">[Конструктор интеллектуального анализа данных](../../2014/analysis-services/data-mining/data-mining-designer.md) </span><span class="sxs-lookup"><span data-stu-id="94d0d-166">[Data Mining Designer](../../2014/analysis-services/data-mining/data-mining-designer.md) </span></span>  
 [<span data-ttu-id="94d0d-167">Алгоритм дерева принятия решений (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="94d0d-167">Microsoft Decision Trees Algorithm</span></span>](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md)  
  
  
