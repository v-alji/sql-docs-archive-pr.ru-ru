---
title: Указание набора проверочных данных для структуры (учебник по интеллектуальному анализу данных — базовый) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 75cd508f-b126-418b-848d-3c4c3e6c303f
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: c1430706a0ec2cd3ddc0eaee18d7001d05fefae1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654668"
---
# <a name="specifying-a-testing-data-set-for-the-structure-basic-data-mining-tutorial"></a><span data-ttu-id="a92e6-102">Задание набора проверочных данных для структуры (учебник по интеллектуальному анализу данных — начальный уровень)</span><span class="sxs-lookup"><span data-stu-id="a92e6-102">Specifying a Testing Data Set for the Structure (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="a92e6-103">На нескольких последних экранах мастера интеллектуального анализа данных данные разбиваются на обучающий и проверочный наборы.</span><span class="sxs-lookup"><span data-stu-id="a92e6-103">In the final few screens of the Data Mining Wizard you will split your data into a testing set and a training set.</span></span> <span data-ttu-id="a92e6-104">Затем структура именуется и включается детализация на модели.</span><span class="sxs-lookup"><span data-stu-id="a92e6-104">You will then name your structure and enable drillthrough on the model.</span></span>  
  
## <a name="specifying-a-testing-set"></a><span data-ttu-id="a92e6-105">Задание проверочного набора</span><span class="sxs-lookup"><span data-stu-id="a92e6-105">Specifying a Testing Set</span></span>  
 <span data-ttu-id="a92e6-106">Благодаря разделению данных на обучающий и проверочный наборы при создании структуры интеллектуального анализа стало значительно проще оценить точность моделей интеллектуального анализа данных, создаваемых в дальнейшем.</span><span class="sxs-lookup"><span data-stu-id="a92e6-106">Separating data into training and testing sets when you create a mining structure makes it possible to easily assess the accuracy of the mining models that you create later.</span></span> <span data-ttu-id="a92e6-107">Дополнительные сведения о проверочных наборах см. в разделе [обучающие и проверочные наборы данных](../../2014/analysis-services/data-mining/training-and-testing-data-sets.md).</span><span class="sxs-lookup"><span data-stu-id="a92e6-107">For more information on testing sets, see [Training and Testing Data Sets](../../2014/analysis-services/data-mining/training-and-testing-data-sets.md).</span></span>  
  
#### <a name="to-specify-the-testing-set"></a><span data-ttu-id="a92e6-108">Задание проверочного набора</span><span class="sxs-lookup"><span data-stu-id="a92e6-108">To specify the testing set</span></span>  
  
1.  <span data-ttu-id="a92e6-109">На странице **Создание проверочного набора** в поле **процент данных для тестирования**оставьте значение по умолчанию `30` .</span><span class="sxs-lookup"><span data-stu-id="a92e6-109">On the **Create Testing Set** page, for **Percentage of data for testing**, leave the default value of `30`.</span></span>  
  
2.  <span data-ttu-id="a92e6-110">Для параметра **Максимальное число вариантов в наборе проверочных данных**введите `1000` .</span><span class="sxs-lookup"><span data-stu-id="a92e6-110">For **Maximum number of cases in testing data set**, type `1000`.</span></span>  
  
3.  <span data-ttu-id="a92e6-111">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="a92e6-111">Click **Next**.</span></span>  
  
## <a name="specifying-drillthrough"></a><span data-ttu-id="a92e6-112">Задание детализации</span><span class="sxs-lookup"><span data-stu-id="a92e6-112">Specifying Drillthrough</span></span>  
 <span data-ttu-id="a92e6-113">Детализация может быть включена для моделей и структур.</span><span class="sxs-lookup"><span data-stu-id="a92e6-113">Drillthrough can be enabled on models and on structures.</span></span> <span data-ttu-id="a92e6-114">Флажок в этом диалоговом окне включает детализацию для именованной модели.</span><span class="sxs-lookup"><span data-stu-id="a92e6-114">The checkbox in this dialog box enables drillthrough on the named model.</span></span> <span data-ttu-id="a92e6-115">После обработки модели можно извлекать подробные сведения из обучающих данных, которые использовались при создании модели.</span><span class="sxs-lookup"><span data-stu-id="a92e6-115">After the model has been processed,  you will be able to retrieve detailed information from the training data that were used to create the model.</span></span>  
  
 <span data-ttu-id="a92e6-116">Если детализация также разрешена для базовой структуры интеллектуального анализа данных, то можно получать сведения из вариантов модели и структуры интеллектуального анализа данных, включая столбцы, отсутствующие в модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="a92e6-116">If the underlying mining structure has also been configured to allow drillthrough, you can retrieve detailed information from both the model cases and the mining structure, including columns that were not included in the mining model.</span></span> <span data-ttu-id="a92e6-117">Дополнительные сведения см. в разделе [Запросы детализации (интеллектуальный анализ данных)](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="a92e6-117">For more information, see [Drillthrough Queries &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md).</span></span>  
  
#### <a name="to-name-the-model-and-structure-and-specify-drillthrough"></a><span data-ttu-id="a92e6-118">Именование модели и структуры и задание детализации</span><span class="sxs-lookup"><span data-stu-id="a92e6-118">To name the model and structure and specify drillthrough</span></span>  
  
1.  <span data-ttu-id="a92e6-119">На странице **Завершение работы мастера** в поле **имя структуры интеллектуального анализа данных**введите `Targeted Mailing` .</span><span class="sxs-lookup"><span data-stu-id="a92e6-119">On the **Completing the Wizard** page, in **Mining structure name**, type `Targeted Mailing`.</span></span>  
  
2.  <span data-ttu-id="a92e6-120">В списке **имя модели интеллектуального анализа данных**введите `TM_Decision_Tree` .</span><span class="sxs-lookup"><span data-stu-id="a92e6-120">In **Mining model name**, type `TM_Decision_Tree`.</span></span>  
  
3.  <span data-ttu-id="a92e6-121">Установите флажок **Разрешить детализацию** .</span><span class="sxs-lookup"><span data-stu-id="a92e6-121">Select the **Allow drill through** check box.</span></span>  
  
4.  <span data-ttu-id="a92e6-122">Просмотрите панель **предварительного просмотра** .</span><span class="sxs-lookup"><span data-stu-id="a92e6-122">Review the **Preview** pane.</span></span> <span data-ttu-id="a92e6-123">Обратите внимание, что отображаются только столбцы, выбранные как **Key**, **input** или **Predict** .</span><span class="sxs-lookup"><span data-stu-id="a92e6-123">Notice that only those columns selected as **Key**, **Input** or **Predictable** are shown.</span></span> <span data-ttu-id="a92e6-124">Остальные выбранные столбцы (например, AddressLine1) не используются для построения модели, но будут доступны в базовой структуре, и к ним можно выполнять запросы после обработки и развертывания модели.</span><span class="sxs-lookup"><span data-stu-id="a92e6-124">The other columns you selected (e.g., AddressLine1) are not used for building the model but will be available in the underlying structure, and can be queried after the model is processed and deployed.</span></span>  
  
5.  <span data-ttu-id="a92e6-125">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="a92e6-125">Click **Finish**.</span></span>  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="a92e6-126">Предыдущая задача занятия</span><span class="sxs-lookup"><span data-stu-id="a92e6-126">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="a92e6-127">Выбор типа данных и типа содержимого &#40;учебник по базовому интеллектуальному анализу данных&#41;</span><span class="sxs-lookup"><span data-stu-id="a92e6-127">Specifying the Data Type and Content Type &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/specifying-the-data-type-and-content-type-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="a92e6-128">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="a92e6-128">Next Lesson</span></span>  
 [<span data-ttu-id="a92e6-129">Урок 3. Добавление и обработка моделей</span><span class="sxs-lookup"><span data-stu-id="a92e6-129">Lesson 3: Adding and Processing Models</span></span>](../../2014/tutorials/lesson-3-adding-and-processing-models.md)  
  
## <a name="see-also"></a><span data-ttu-id="a92e6-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="a92e6-130">See Also</span></span>  
 <span data-ttu-id="a92e6-131">[Включение детализации для модели интеллектуального анализа данных](../../2014/analysis-services/data-mining/enable-drillthrough-for-a-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="a92e6-131">[Enable Drillthrough for a Mining Model](../../2014/analysis-services/data-mining/enable-drillthrough-for-a-mining-model.md) </span></span>  
 <span data-ttu-id="a92e6-132">[Запросы детализации &#40;&#41;интеллектуального анализа данных](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="a92e6-132">[Drillthrough Queries &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md) </span></span>  
 [<span data-ttu-id="a92e6-133">Укажите обучающие данные &#40;мастер интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="a92e6-133">Specify the Training Data &#40;Data Mining Wizard&#41;</span></span>](../../2014/analysis-services/specify-the-training-data-data-mining-wizard.md)  
  
  
