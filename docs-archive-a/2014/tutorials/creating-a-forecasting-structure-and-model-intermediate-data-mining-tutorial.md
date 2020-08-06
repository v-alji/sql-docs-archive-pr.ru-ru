---
title: Создание структуры и модели прогнозирования (учебник по интеллектуальному анализу данных — средний уровень) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 5f55cbf6-0db4-4cb4-a0f5-e27441873d4f
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: d77b15a9a8efe9a9c6faec49a2274ee182706992
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727529"
---
# <a name="creating-a-forecasting-structure-and-model-intermediate-data-mining-tutorial"></a><span data-ttu-id="dc5c9-102">Создание структуры и модели прогнозирования (учебник по интеллектуальному анализу данных — средний уровень)</span><span class="sxs-lookup"><span data-stu-id="dc5c9-102">Creating a Forecasting Structure and Model (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="dc5c9-103">Далее будет использоваться мастер интеллектуального анализа данных для создания новой структуры интеллектуального анализа данных и модели интеллектуального анализа данных на основе только что созданного представления источников данных.</span><span class="sxs-lookup"><span data-stu-id="dc5c9-103">Next, you will use the Data Mining Wizard to create a new mining structure and mining model based on the data source view that you just created.</span></span> <span data-ttu-id="dc5c9-104">В этой задаче будет указано, что модель интеллектуального анализа данных должна использовать [!INCLUDE[msCoName](../includes/msconame-md.md)] алгоритм временных рядов.</span><span class="sxs-lookup"><span data-stu-id="dc5c9-104">In this task you will specify that the mining model should use the [!INCLUDE[msCoName](../includes/msconame-md.md)] Time Series algorithm.</span></span>  
  
### <a name="to-create-a-forecasting-mining-structure"></a><span data-ttu-id="dc5c9-105">Создание структуры интеллектуального анализа данных для прогнозирования</span><span class="sxs-lookup"><span data-stu-id="dc5c9-105">To create a forecasting mining structure</span></span>  
  
1.  <span data-ttu-id="dc5c9-106">В обозреватель решений в щелкните [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] правой кнопкой мыши элемент **структуры интеллектуального анализа данных** и выберите пункт **создать структуру интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="dc5c9-106">In Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], right-click **Mining Structures** and select **New Mining Structure**.</span></span>  
  
2.  <span data-ttu-id="dc5c9-107">На странице **Вас приветствует мастер интеллектуального анализа данных** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dc5c9-107">On the **Welcome to the Data Mining Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="dc5c9-108">На странице **Выбор метода определения** убедитесь, что выбран параметр **из существующей реляционной базы данных или хранилища данных** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dc5c9-108">On the **Select the Definition Method** page, verify that **From existing relational database or data warehouse** is selected, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="dc5c9-109">На странице **Создание структуры интеллектуального анализа данных** , в **которой вы хотите использовать метод интеллектуального анализа данных**, выберите **временные ряды Microsoft**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dc5c9-109">On the **Create the Data Mining Structure** page, under **Which data mining technique do you want to use?**, select **Microsoft Time Series**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="dc5c9-110">На странице **Выбор представления источника данных** в разделе **Доступные представления источников данных**выберите **SalesByRegion**.</span><span class="sxs-lookup"><span data-stu-id="dc5c9-110">On the **Select Data Source View** page, under **Available data source views**, select **SalesByRegion**.</span></span>  
  
6.  <span data-ttu-id="dc5c9-111">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dc5c9-111">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="dc5c9-112">На странице **Выбор типов таблиц** убедитесь, что установлен флажок в столбце **вариант** для таблицы vTimeSeries, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dc5c9-112">On the **Specify Table Types** page, ensure that the check box in the **Case** column for the vTimeSeries table is selected, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="dc5c9-113">На странице **Определение обучающих данных** установите флажки в столбце **ключевое** значение для столбцов ModelRegion и ReportingDate.</span><span class="sxs-lookup"><span data-stu-id="dc5c9-113">On the **Specify the Training Data** page, select the check boxes in the **Key** column for the ModelRegion and ReportingDate columns.</span></span>  
  
     <span data-ttu-id="dc5c9-114">По умолчанию должен быть выбран столбец ReportingDate, поскольку при создании представления источника данных был указан этот столбец как логический первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="dc5c9-114">ReportingDate should be selected by default, because you specified this column as the logical primary key when you created the data source view.</span></span> <span data-ttu-id="dc5c9-115">Если столбец ModelRegion добавлен в качестве второго ключа, то алгоритм будет создавать отдельный временной ряд для каждого сочетания модели и области, указанной в списке этого поля.</span><span class="sxs-lookup"><span data-stu-id="dc5c9-115">By adding ModelRegion as a second key, you are telling the algorithm to create a separate time series for each combination of model and region listed in this field.</span></span>  
  
9. <span data-ttu-id="dc5c9-116">Установите флажки в полях **входные** и **прогнозируемые** столбцы количество, столбец и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dc5c9-116">Select the check boxes in the **Input** and **Predictable** columns for the Quantity, column, and then click **Next**.</span></span>  
  
     <span data-ttu-id="dc5c9-117">Выбрав **прогнозируемый**, вы указываете, что вы хотите создать прогнозы для данных в этом столбце.</span><span class="sxs-lookup"><span data-stu-id="dc5c9-117">By selecting **Predictable**, you indicate that you want to create forecasts on the data in this column.</span></span> <span data-ttu-id="dc5c9-118">Однако поскольку прогнозы должны быть основаны на прошлых данных, необходимо также добавить столбец как входной.</span><span class="sxs-lookup"><span data-stu-id="dc5c9-118">However, because you want to base the forecasts on past data, you must also add the column as an input.</span></span>  
  
10. <span data-ttu-id="dc5c9-119">На странице **Указание содержимого и типа данных столбцов**проверьте выбор.</span><span class="sxs-lookup"><span data-stu-id="dc5c9-119">On the page **Specify Columns' Content and Data Type**, review the selections.</span></span>  
  
     <span data-ttu-id="dc5c9-120">Столбец ModelRegion назначается в качестве **ключевого** столбца, а столбец ReportingDate автоматически назначается в качестве **ключевого столбца времени** .</span><span class="sxs-lookup"><span data-stu-id="dc5c9-120">The ModelRegion column is designated as a **Key** column and the ReportingDate column is automatically designated as a **Key Time** column.</span></span> <span data-ttu-id="dc5c9-121">Допускается только один ключ каждого типа.</span><span class="sxs-lookup"><span data-stu-id="dc5c9-121">You can have only one of each type of key.</span></span>  
  
11. <span data-ttu-id="dc5c9-122">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="dc5c9-122">Click **Next**.</span></span>  
  
12. <span data-ttu-id="dc5c9-123">На странице **Завершение работы мастера** в поле **имя структуры интеллектуального анализа данных**введите `Forecasting` .</span><span class="sxs-lookup"><span data-stu-id="dc5c9-123">On the **Completing the Wizard** page, for **Mining structure name**, type `Forecasting`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dc5c9-124">Для моделей временных рядов возможность включения детализации недоступна.</span><span class="sxs-lookup"><span data-stu-id="dc5c9-124">The option to enable drillthrough is not available for time series models.</span></span>  
  
13. <span data-ttu-id="dc5c9-125">В списке **имя модели интеллектуального анализа данных**введите `Forecasting` , а затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="dc5c9-125">In **Mining model name**, type `Forecasting`, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="dc5c9-126">Откроется конструктор интеллектуального анализа данных, чтобы отобразить `Forecasting` только что созданную структуру интеллектуального анализа.</span><span class="sxs-lookup"><span data-stu-id="dc5c9-126">Data Mining Designer opens to display the `Forecasting` mining structure that you just created.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="dc5c9-127">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="dc5c9-127">Next Task in Lesson</span></span>  
 [<span data-ttu-id="dc5c9-128">Изменение структуры прогнозирования &#40;промежуточное руководство по интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="dc5c9-128">Modifying the Forecasting Structure &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/modifying-the-forecasting-structure-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="dc5c9-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="dc5c9-129">See Also</span></span>  
 <span data-ttu-id="dc5c9-130">[Конструктор интеллектуального анализа данных](../../2014/analysis-services/data-mining/data-mining-designer.md) </span><span class="sxs-lookup"><span data-stu-id="dc5c9-130">[Data Mining Designer](../../2014/analysis-services/data-mining/data-mining-designer.md) </span></span>  
 [<span data-ttu-id="dc5c9-131">Алгоритм временных рядов (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="dc5c9-131">Microsoft Time Series Algorithm</span></span>](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md)  
  
  
