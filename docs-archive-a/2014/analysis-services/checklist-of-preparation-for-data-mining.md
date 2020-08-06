---
title: Контрольный список подготовки к интеллектуальному анализу данных | Документация Майкрософт
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 0e056c95-ba06-413e-8dc1-4d411a447c3b
author: minewiskan
ms.author: owend
ms.openlocfilehash: e37b1adb6aebe5d5f8fd23f5289f52425f752a6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657419"
---
# <a name="checklist-of-preparation-for-data-mining"></a><span data-ttu-id="c668e-102">Контрольный список для подготовки к интеллектуальному анализу данных</span><span class="sxs-lookup"><span data-stu-id="c668e-102">Checklist of Preparation for Data Mining</span></span>
  <span data-ttu-id="c668e-103">Хотя надстройки интеллектуального анализа данных упрощают создание и эксперименты с моделями, когда требуется получить повторяемые результаты, на основании которых можно действовать, необходимо выделить достаточный срок для формулировки базовых требований бизнеса и получения и подготовки данных.</span><span class="sxs-lookup"><span data-stu-id="c668e-103">Although the Data Mining Add-ins make it fairly easy and fun to create and experiment with models, when you need to get repeatable, actionable results, you must allow adequate time for formulating basic business requirements, and for obtaining and preparing data.</span></span> <span data-ttu-id="c668e-104">В этом разделе представлен контрольный список, который поможет вам спланировать исследование, а также приводится описание распространенных проблем.</span><span class="sxs-lookup"><span data-stu-id="c668e-104">This section provides a checklist to help you plan your investigation, and describes common problems.</span></span>  
  
## <a name="checklist-of-data-preparation"></a><span data-ttu-id="c668e-105">Контрольный список подготовки данных</span><span class="sxs-lookup"><span data-stu-id="c668e-105">Checklist of Data Preparation</span></span>  
 <span data-ttu-id="c668e-106">**Я указал точно заданные выходные данные.**</span><span class="sxs-lookup"><span data-stu-id="c668e-106">**I have identified a clearly defined output.**</span></span>  
 <span data-ttu-id="c668e-107">Создать план использования результатов.</span><span class="sxs-lookup"><span data-stu-id="c668e-107">Have a plan for how you will use the results.</span></span> <span data-ttu-id="c668e-108">У различных типов моделей различные выходы.</span><span class="sxs-lookup"><span data-stu-id="c668e-108">Different types of models have different outputs.</span></span> <span data-ttu-id="c668e-109">Модель временных рядов формирует значения для рядов в будущем, которые легко понять и применить.</span><span class="sxs-lookup"><span data-stu-id="c668e-109">A time series model generates values for a series in the future, which are easily understood and acted on.</span></span> <span data-ttu-id="c668e-110">Другие модели создают комплексные наборы, которые для получения наибольшей пользы должны быть проанализированы специалистами в соответствующей предметной области.</span><span class="sxs-lookup"><span data-stu-id="c668e-110">Other models generate complex sets that must be analyzed by subject matter experts to yield the most value.</span></span>  
  
-   <span data-ttu-id="c668e-111">Какие выходные данные нужны?</span><span class="sxs-lookup"><span data-stu-id="c668e-111">What output do you want?</span></span>  
  
-   <span data-ttu-id="c668e-112">Можно ли определить выходные данные как один столбец, одно значение или другой тип результата?</span><span class="sxs-lookup"><span data-stu-id="c668e-112">Can you define the output as a single column or value, or other actionable result?</span></span>  
  
-   <span data-ttu-id="c668e-113">Каковы критерии того, что созданная модель была полезной?</span><span class="sxs-lookup"><span data-stu-id="c668e-113">What are your criteria for knowing that the model was useful?</span></span>  
  
-   <span data-ttu-id="c668e-114">Как эти результаты будут использоваться и интерпретироваться?</span><span class="sxs-lookup"><span data-stu-id="c668e-114">How will you use and interpret those results?</span></span>  
  
-   <span data-ttu-id="c668e-115">Можно ли сопоставить новые входные данные с ожидаемым результатами?</span><span class="sxs-lookup"><span data-stu-id="c668e-115">Can you map new input data to the expected results?</span></span>  
  
 <span data-ttu-id="c668e-116">**Я знаю значение, типы данных и распределение входных данных.**</span><span class="sxs-lookup"><span data-stu-id="c668e-116">**I know the meaning, data types, and distribution of the input data.**</span></span>  
 <span data-ttu-id="c668e-117">Уделите время изучению и анализу исходных данных.</span><span class="sxs-lookup"><span data-stu-id="c668e-117">Take some time to explore and understand your source data.</span></span> <span data-ttu-id="c668e-118">Важно, чтобы пользователи, которые будут просматривать модель, понимали, какие вводные данные использовались и как интерпретировать типы и разброс данных, а также баланс и качество.</span><span class="sxs-lookup"><span data-stu-id="c668e-118">It is important that people who review the model understand what kind of input data was used and know how to interpret the data types and the variability, as well as the balance and the quality.</span></span>  
  
-   <span data-ttu-id="c668e-119">Каков объем имеющихся данных?</span><span class="sxs-lookup"><span data-stu-id="c668e-119">How much data do you have?</span></span> <span data-ttu-id="c668e-120">Достаточно ли данных для моделирования?</span><span class="sxs-lookup"><span data-stu-id="c668e-120">Is there sufficient data for modeling?</span></span>  
  
     <span data-ttu-id="c668e-121">Это не должно быть огромным размером и сбалансированным.</span><span class="sxs-lookup"><span data-stu-id="c668e-121">It need not be a huge amount - smaller and balanced can be better.</span></span>  
  
-   <span data-ttu-id="c668e-122">Данные получены из нескольких источников или одного источника?</span><span class="sxs-lookup"><span data-stu-id="c668e-122">Is the data from multiple sources, or a single source?</span></span>  
  
-   <span data-ttu-id="c668e-123">Данные уже обработаны и очищены?</span><span class="sxs-lookup"><span data-stu-id="c668e-123">Is the data already processed and clean?</span></span> <span data-ttu-id="c668e-124">Доступно ли большее количество входных данных?</span><span class="sxs-lookup"><span data-stu-id="c668e-124">Is more input data available?</span></span>  
  
-   <span data-ttu-id="c668e-125">Вам известно, как он был обработан перед получением, — каким способом данные могут быть усечены, суммироваться или преобразованы?</span><span class="sxs-lookup"><span data-stu-id="c668e-125">Do you know how it was manipulated before you received it - how data might have been truncated, summarized, or converted?</span></span>  
  
-   <span data-ttu-id="c668e-126">Содержат ли входные данные результаты, которые можно использовать для обучения?</span><span class="sxs-lookup"><span data-stu-id="c668e-126">Does the input data have some example results that can be used for training?</span></span>  
  
 <span data-ttu-id="c668e-127">**Я понимаю уровень целостности данных в нашей системе и уровень, которого нам необходимо достигнуть.**</span><span class="sxs-lookup"><span data-stu-id="c668e-127">**I understand the level of data integrity we have and the level we need.**</span></span>  
 <span data-ttu-id="c668e-128">Неверные данные могут повлиять на качество модели или даже не позволить создать модель.</span><span class="sxs-lookup"><span data-stu-id="c668e-128">Bad data can affect the quality of the model, or prevent the model from being built at all.</span></span> <span data-ttu-id="c668e-129">Необходимо хорошо понимать распределение и значение данных, а также как они пришли к этому состоянию.</span><span class="sxs-lookup"><span data-stu-id="c668e-129">You should have a good understanding of both the distribution and meaning of the data, and how it came to this state.</span></span> <span data-ttu-id="c668e-130">Необходимо понимать, можно ли упростить данные путем добавления меток, усечения числовых типов данных или обобщением.</span><span class="sxs-lookup"><span data-stu-id="c668e-130">You'll need to understand if it is possible or appropriate to simplify the data by labeling, truncating numeric data types, or by summarizing.</span></span>  
  
-   <span data-ttu-id="c668e-131">Метки данных: они понятны и исправлены?</span><span class="sxs-lookup"><span data-stu-id="c668e-131">Data labels: are they clear and correct?</span></span>  
  
-   <span data-ttu-id="c668e-132">Типы данных: нужны ли они и были ли они изменены?</span><span class="sxs-lookup"><span data-stu-id="c668e-132">Data types: are they appropriate, and have they been changed?</span></span>  
  
-   <span data-ttu-id="c668e-133">Выполнили ли вы сортировку, очистку или отклонение неверных данных?</span><span class="sxs-lookup"><span data-stu-id="c668e-133">Have you sorted, cleaned up, or discarded wrong data?</span></span>  
  
     <span data-ttu-id="c668e-134">Проверены ли данные на наличие повторов?</span><span class="sxs-lookup"><span data-stu-id="c668e-134">Have you verified there are no duplicates?</span></span>  
  
-   <span data-ttu-id="c668e-135">Как будут обрабатываться отсутствующие значения?</span><span class="sxs-lookup"><span data-stu-id="c668e-135">How will you handle missing values?</span></span> <span data-ttu-id="c668e-136">Есть ли смысл у отсутствующих значений?</span><span class="sxs-lookup"><span data-stu-id="c668e-136">Do missing values have a meaning?</span></span>  
  
-   <span data-ttu-id="c668e-137">Проверены ли источники данных, чтобы убедиться в целостности импортируемых данных?</span><span class="sxs-lookup"><span data-stu-id="c668e-137">Have you verified the sources to see if any errors might have been introduced in the import process?</span></span>  
  
     <span data-ttu-id="c668e-138">Где хранятся входные данные?</span><span class="sxs-lookup"><span data-stu-id="c668e-138">Where is the input stored?</span></span> <span data-ttu-id="c668e-139">Насколько долго данные будут оставаться доступными?</span><span class="sxs-lookup"><span data-stu-id="c668e-139">How long does it stay available?</span></span>  
  
     <span data-ttu-id="c668e-140">Существует ли словарь данных?</span><span class="sxs-lookup"><span data-stu-id="c668e-140">Is there a data dictionary?</span></span> <span data-ttu-id="c668e-141">Можно ли создать словарь?</span><span class="sxs-lookup"><span data-stu-id="c668e-141">Can you create one?</span></span>  
  
-   <span data-ttu-id="c668e-142">Если наборы данных были объединены, проводилась ли проверка столбцов, дублирующих одни и те же данные?</span><span class="sxs-lookup"><span data-stu-id="c668e-142">If you combined data sets, did you check for multiple columns representing the same data?</span></span>  
  
 <span data-ttu-id="c668e-143">**Я могу узнать, где хранятся исходные данные, откуда они поступили и как они обрабатываются. При необходимости процесс можно легко повторить.**</span><span class="sxs-lookup"><span data-stu-id="c668e-143">**I know where source data is stored, where it came from, and how it is processed. The process can be easily repeated if needed.**</span></span>  
 <span data-ttu-id="c668e-144">Односторонние наборы данных прекрасно подойдут для экспериментов, но если вам когда-либо нужно переместить модель в рабочую среду, необходимо заранее подумать о том, как процесс очистки можно применить к рабочим данным.</span><span class="sxs-lookup"><span data-stu-id="c668e-144">One-off data sets are fine for experiments, but if you ever want to move the model into production, you'll want to think in advance about how the cleaning process can be applied to operational data.</span></span> <span data-ttu-id="c668e-145">Кроме того, если у вас есть операционные данные, необходимо знать, как она могла быть изменена до того, как она была получена. вам нужно знать, как она была округлена или обобщена, безусловно.</span><span class="sxs-lookup"><span data-stu-id="c668e-145">Also, if you have operational data, you need to know how it might have been altered before you got it-you'll need to know how it was rounded, or summarized, certainly.</span></span>  
  
-   <span data-ttu-id="c668e-146">Нужна ли возможность повторять эксперимент?</span><span class="sxs-lookup"><span data-stu-id="c668e-146">Do you want to be able to repeat the experiment?</span></span>  
  
-   <span data-ttu-id="c668e-147">Какие инструменты будут использоваться для подготовки данных в формате, который поддерживает анализ данных?</span><span class="sxs-lookup"><span data-stu-id="c668e-147">What tools will you use to prepare data in a format that supports data analysis?</span></span> <span data-ttu-id="c668e-148">Можно ли автоматизировать процесс или необходим кто-то для просмотра и очистки данных в Excel?</span><span class="sxs-lookup"><span data-stu-id="c668e-148">Can it be automated or do you need someone to review and clean up in Excel?</span></span>  
  
-   <span data-ttu-id="c668e-149">Если данные подкачиваются из другой системы, будет ли возможность отслеживать использование фильтров?</span><span class="sxs-lookup"><span data-stu-id="c668e-149">If you are sourcing data from another system, will you be able to capture and track filters that were applied?</span></span>  
  
-   <span data-ttu-id="c668e-150">Может ли ваша среда обработки данных также применить машинные алгоритмы обучения, выполнять тесты и визуализировать ресурсы?</span><span class="sxs-lookup"><span data-stu-id="c668e-150">Can your data processing framework also apply machine learning algorithms, perform tests, and visualize results?</span></span>  
  
 <span data-ttu-id="c668e-151">**Мы достигли соглашения по уровню гранулярности прогнозов, и наши данные были изменены для вывода такими блоками.**</span><span class="sxs-lookup"><span data-stu-id="c668e-151">**We have agreed on the desired granularity of predictions and our data has been modified to output those units.**</span></span>  
 <span data-ttu-id="c668e-152">Примите решение по нужной гранулярности результатов до момента подготовки данных. Например, определите, хотите ли вы получать предсказания по уровням продаж ежедневно или ежеквартально?</span><span class="sxs-lookup"><span data-stu-id="c668e-152">Decide on the granularity of the results you want before preparing data, For example, do you want sales predictions by the day, or for each quarter?</span></span> <span data-ttu-id="c668e-153">Рассмотрите возможность создания различных структур данных для одних и тех же данных, чтобы обрабатывать различные уровни сводки.</span><span class="sxs-lookup"><span data-stu-id="c668e-153">You might consider setting up different data structures for the same data, to handle different levels of summary.</span></span>  
  
-   <span data-ttu-id="c668e-154">Какова текущая единица измерения или единица времени?</span><span class="sxs-lookup"><span data-stu-id="c668e-154">What is the current unit of measure or unit of time?</span></span>  
  
     <span data-ttu-id="c668e-155">Какую единицу измерения нужно использовать в результатах?</span><span class="sxs-lookup"><span data-stu-id="c668e-155">What unit do you want to use in the results?</span></span>  
  
-   <span data-ttu-id="c668e-156">Можно ли определить базовую единицу (например, день, час, минуту или вызов инструкции) для всех входных данных?</span><span class="sxs-lookup"><span data-stu-id="c668e-156">Is it possible to define a basic unit (e.g. day/ hour / min / instruction call) for all input data?</span></span>  
  
     <span data-ttu-id="c668e-157">Требуется ли свертка до больших единиц измерения?</span><span class="sxs-lookup"><span data-stu-id="c668e-157">Do you want to rollup to higher units?</span></span>  
  
-   <span data-ttu-id="c668e-158">Категории обозначены последовательно?</span><span class="sxs-lookup"><span data-stu-id="c668e-158">Are categories labeled consistently?</span></span> <span data-ttu-id="c668e-159">Прост ли процесс добавления или удаления категорий?</span><span class="sxs-lookup"><span data-stu-id="c668e-159">Is it easy to add or remove categories?</span></span>  
  
 <span data-ttu-id="c668e-160">**Наша опытная конструкция воспроизводима во всех отношениях.**</span><span class="sxs-lookup"><span data-stu-id="c668e-160">**Our experimental design is repeatable and reproducible.**</span></span>  
 <span data-ttu-id="c668e-161">Рассмотрите стратегии для анализа и проверки результатов и запланируйте получение моментального снимка данных, чтобы получить возможности связать последствия с данными.</span><span class="sxs-lookup"><span data-stu-id="c668e-161">Consider strategies for analyzing and validating your results and plan to capture a data snapshot, to make sure you can trace back effects to data.</span></span> <span data-ttu-id="c668e-162">При использовании случайного начального значения результаты могут слегка различаться.</span><span class="sxs-lookup"><span data-stu-id="c668e-162">If a random seed is used, the results can differ subtly.</span></span> <span data-ttu-id="c668e-163">Это может затруднить сравнение и проверку моделей.</span><span class="sxs-lookup"><span data-stu-id="c668e-163">This can make it difficult to compare and validate models.</span></span>  
  
-   <span data-ttu-id="c668e-164">При внесении большого количества изменений в данные что происходит при следующем построении модели?</span><span class="sxs-lookup"><span data-stu-id="c668e-164">If you make a lot of custom changes to the data, what happens the next time you want to build the model?</span></span>  
  
-   <span data-ttu-id="c668e-165">Определены ли ручная процедура или процесс, которые необходимо использовать для обработки входных данных и получения нужных выходных данных?</span><span class="sxs-lookup"><span data-stu-id="c668e-165">Has a manual procedure or approved process already been defined that you should use to process input and get the desired outputs?</span></span>  
  
-   <span data-ttu-id="c668e-166">Будет ли использоваться начальное значение в модели?</span><span class="sxs-lookup"><span data-stu-id="c668e-166">Have you decided to use a seed for the model?</span></span>  
  
 <span data-ttu-id="c668e-167">**Мы имеем набор знаний домена для проверки результатов или доступ к специалистам, которые могут дать рекомендации.**</span><span class="sxs-lookup"><span data-stu-id="c668e-167">**We have the domain knowledge to validate the results, or have access to subject matter experts who can advise.**</span></span>  
 <span data-ttu-id="c668e-168">Уделите время, чтобы проверить переменные, модель и результаты.</span><span class="sxs-lookup"><span data-stu-id="c668e-168">Take time to validate the variables, the model, and the results.</span></span> <span data-ttu-id="c668e-169">Попросите помощи у специалистов для оценки взаимодействия и результатов.</span><span class="sxs-lookup"><span data-stu-id="c668e-169">Get the help of experts to assess interactions and results.</span></span> <span data-ttu-id="c668e-170">Тем не менее, не следует предполагать, что свидетельство переносится.</span><span class="sxs-lookup"><span data-stu-id="c668e-170">However, don't let assumptions overrule evidence.</span></span> <span data-ttu-id="c668e-171">Будьте открыты для новых и непредвиденных заключений.</span><span class="sxs-lookup"><span data-stu-id="c668e-171">Be open to new and unexpected findings.</span></span>  
  
-   <span data-ttu-id="c668e-172">Доступны ли знания предметной области для помощи с фильтрацией данных и уменьшением шума входных данных?</span><span class="sxs-lookup"><span data-stu-id="c668e-172">Is domain knowledge available to help in filtering data and reducing input noise?</span></span>  
  
-   <span data-ttu-id="c668e-173">Могут ли эксперты в предметной области понять и интерпретировать результаты, а также предложить улучшения?</span><span class="sxs-lookup"><span data-stu-id="c668e-173">Can domain experts help understand interpret the results and suggest improvements?</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c668e-174">См. также:</span><span class="sxs-lookup"><span data-stu-id="c668e-174">See Also</span></span>  
 [<span data-ttu-id="c668e-175">Выбор данных для интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="c668e-175">Choosing Data for Data Mining</span></span>](choosing-data-for-data-mining.md)  
  
  
