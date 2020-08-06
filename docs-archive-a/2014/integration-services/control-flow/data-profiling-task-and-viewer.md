---
title: Задача профилирования данных и средство просмотра профиля данных | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Data Profiling task [Integration Services], about data profiling
- data profiling
- profiling data
ms.assetid: 756840e3-aa09-45cd-9951-1a17af4b5925
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ae15d1cc75f8db04c36a830e44d07800c5aecf75
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658344"
---
# <a name="data-profiling-task-and-viewer"></a><span data-ttu-id="9076a-102">Задачи профилирования и просмотра данных</span><span class="sxs-lookup"><span data-stu-id="9076a-102">Data Profiling Task and Viewer</span></span>
  <span data-ttu-id="9076a-103">Задача «Профилирование данных» обеспечивает профилирование данных внутри процесса извлечения, преобразования и загрузки данных.</span><span class="sxs-lookup"><span data-stu-id="9076a-103">The Data Profiling task provides data profiling functionality inside the process of extracting, transforming, and loading data.</span></span> <span data-ttu-id="9076a-104">Использование задачи «Профилирование данных» может дать следующие преимущества.</span><span class="sxs-lookup"><span data-stu-id="9076a-104">By using the Data Profiling task, you can achieve the following benefits:</span></span>  
  
-   <span data-ttu-id="9076a-105">Более эффективный анализ исходных данных</span><span class="sxs-lookup"><span data-stu-id="9076a-105">Analyze the source data more effectively</span></span>  
  
-   <span data-ttu-id="9076a-106">Более глубокое понимание исходных данных</span><span class="sxs-lookup"><span data-stu-id="9076a-106">Understand the source data better</span></span>  
  
-   <span data-ttu-id="9076a-107">Предотвращение проблем, связанных с качеством данных, еще до того, как последние попадают в хранилище данных</span><span class="sxs-lookup"><span data-stu-id="9076a-107">Prevent data quality problems before they are introduced into the data warehouse.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9076a-108">Задача «Профилирование данных» работает только с данными, хранящимися в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9076a-108">The Data Profiling task works only with data that is stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="9076a-109">Она не работает с источниками данных сторонних разработчиков и с файловыми источниками данных.</span><span class="sxs-lookup"><span data-stu-id="9076a-109">It does not work with third-party or file-based data sources.</span></span>  
  
## <a name="data-profiling-overview"></a><span data-ttu-id="9076a-110">Обзор профилирования данных</span><span class="sxs-lookup"><span data-stu-id="9076a-110">Data Profiling Overview</span></span>  
 <span data-ttu-id="9076a-111">Качество данных имеет важное значение для любого бизнеса.</span><span class="sxs-lookup"><span data-stu-id="9076a-111">Data quality is important to every business.</span></span> <span data-ttu-id="9076a-112">При оснащении транзакционных систем предприятий аналитическими системами и системами бизнес-аналитики надежность ключевых показателей эффективности и прогнозов интеллектуального анализа данных полностью зависит от достоверности данных, на которых они основаны.</span><span class="sxs-lookup"><span data-stu-id="9076a-112">As enterprises build analytical and business intelligence systems on top of their transactional systems, the reliability of key performance indicators and of data mining predictions depends completely on the validity of the data on which they are based.</span></span> <span data-ttu-id="9076a-113">Хотя важность достоверности данных, используемых в процессе принятия бизнес-решений, возрастает, повышается и сложность обеспечения достоверности этих данных.</span><span class="sxs-lookup"><span data-stu-id="9076a-113">But although the importance of valid data for business decision-making is increasing, the challenge of making sure of this data's validity is also increasing.</span></span> <span data-ttu-id="9076a-114">Потоки данных постоянно поступают на предприятия из различных систем и источников, а также от большого числа пользователей.</span><span class="sxs-lookup"><span data-stu-id="9076a-114">Data is streaming into the enterprise constantly from diverse systems and sources, and a large numbers of users.</span></span>  
  
 <span data-ttu-id="9076a-115">Могут возникать сложности с определением метрик качества данных из-за того, что последние связаны с конкретной сферой деятельности или применения.</span><span class="sxs-lookup"><span data-stu-id="9076a-115">Metrics for data quality can be difficult to define because they are specific to the domain or the application.</span></span> <span data-ttu-id="9076a-116">Один из часто применяемых подходов к определению качества данных — это профилирование данных.</span><span class="sxs-lookup"><span data-stu-id="9076a-116">One common approach to defining data quality is data profiling.</span></span>  
  
 <span data-ttu-id="9076a-117">Профиль данных — это коллекция статистических сведений о данных, в которую могут входит следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="9076a-117">A data profile is a collection of aggregate statistics about data that might include the following:</span></span>  
  
-   <span data-ttu-id="9076a-118">Число строк в таблице «Клиенты».</span><span class="sxs-lookup"><span data-stu-id="9076a-118">The number of rows in the Customer table.</span></span>  
  
-   <span data-ttu-id="9076a-119">Число различающихся значений в столбце «Область».</span><span class="sxs-lookup"><span data-stu-id="9076a-119">The number of distinct values in the State column.</span></span>  
  
-   <span data-ttu-id="9076a-120">Число отсутствующих значений или значений NULL в столбце «Почтовый индекс».</span><span class="sxs-lookup"><span data-stu-id="9076a-120">The number of null or missing values in the Zip column.</span></span>  
  
-   <span data-ttu-id="9076a-121">Распределение значений в столбце «Город».</span><span class="sxs-lookup"><span data-stu-id="9076a-121">The distribution of values in the City column.</span></span>  
  
-   <span data-ttu-id="9076a-122">Степень функциональной зависимости столбца "Область" от столбца "Почтовый индекс", иначе говоря, область должна быть всегда одной и той же для данного значения почтового индекса.</span><span class="sxs-lookup"><span data-stu-id="9076a-122">The strength of the functional dependency of the State column on the Zip column-that is, the state should always be the same for a given zip value.</span></span>  
  
 <span data-ttu-id="9076a-123">Статистические сведения, предоставляемые профилем данных, — это информация, необходимая для сведения к минимуму проблем качества, которые могут возникнуть при использовании исходных данных.</span><span class="sxs-lookup"><span data-stu-id="9076a-123">The statistics that a data profile provides gives you the information that you need in order to effectively minimize the quality issues that might occur from using the source data.</span></span>  
  
## <a name="integration-services-and-data-profiling"></a><span data-ttu-id="9076a-124">Службы Integration Services и профилирование данных</span><span class="sxs-lookup"><span data-stu-id="9076a-124">Integration Services and Data Profiling</span></span>  
 <span data-ttu-id="9076a-125">В службах [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]процесс профилирования данных состоит из следующих шагов.</span><span class="sxs-lookup"><span data-stu-id="9076a-125">In [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], the data profiling process consist of the following steps:</span></span>  
  
 <span data-ttu-id="9076a-126">**Шаг 1. Настройка задачи "Профилирование данных"**</span><span class="sxs-lookup"><span data-stu-id="9076a-126">**Step 1: Setting up the Data Profiling Task**</span></span>  
 <span data-ttu-id="9076a-127">Задача «Профилирование данных» используется для настройки профилей, которые необходимо вычислить.</span><span class="sxs-lookup"><span data-stu-id="9076a-127">The Data Profiling task is a task that you use to configure the profiles that you want to compute.</span></span> <span data-ttu-id="9076a-128">Далее запускается пакет, содержащий задачу «Профилирование данных», чтобы вычислить профили.</span><span class="sxs-lookup"><span data-stu-id="9076a-128">You then run the package that contains the Data Profiling task to compute the profiles.</span></span> <span data-ttu-id="9076a-129">Эта задача сохраняет выходные данные профиля в формате XML в файле или в переменной пакета.</span><span class="sxs-lookup"><span data-stu-id="9076a-129">The task saves the profile output in XML format to a file or a package variable.</span></span>  
  
 <span data-ttu-id="9076a-130">**Дополнительные сведения см. в следующих разделах:** [Установка задачи «Профилирование данных»](data-profiling-task.md)</span><span class="sxs-lookup"><span data-stu-id="9076a-130">**For more information:** [Setup of the Data Profiling Task](data-profiling-task.md)</span></span>  
  
 <span data-ttu-id="9076a-131">**Шаг 2. Обзор профилей, вычисляемых задачей "Профилирование данных"**</span><span class="sxs-lookup"><span data-stu-id="9076a-131">**Step 2: Reviewing the Profiles that the Data Profiling Task Computes**</span></span>  
 <span data-ttu-id="9076a-132">Чтобы просмотреть профили данных, вычисляемые задачей «Профилирование данных», нужно направить ее выходные данные в файл и затем использовать средство просмотра профиля данных.</span><span class="sxs-lookup"><span data-stu-id="9076a-132">To view the data profiles that the Data Profiling task computes, you send the output to a file, and then you use the Data Profile Viewer.</span></span> <span data-ttu-id="9076a-133">Это средство представляет собой отдельную программу, которая отображает выходные данные профиля как в формате сводки, так и в подробном формате с дополнительной возможностью углубленной детализации.</span><span class="sxs-lookup"><span data-stu-id="9076a-133">This viewer is a stand-alone utility that displays the profile output in both summary and detail format with optional drilldown capability.</span></span>  
  
 <span data-ttu-id="9076a-134">**Дополнительные сведения см. в следующих разделах:** [Средство просмотра профиля данных](data-profile-viewer.md)</span><span class="sxs-lookup"><span data-stu-id="9076a-134">**For more information:** [Data Profile Viewer](data-profile-viewer.md)</span></span>  
  
### <a name="addition-of-conditional-logic-to-the-data-profiling-workflow"></a><span data-ttu-id="9076a-135">Добавление условной логики в рабочий процесс профилирования данных</span><span class="sxs-lookup"><span data-stu-id="9076a-135">Addition of Conditional Logic to the Data Profiling Workflow</span></span>  
 <span data-ttu-id="9076a-136">Задача «Профилирование данных» не имеет встроенных функций, позволяющих связывать эту задачу с нижестоящими задачами на основе выходных данных профиля с помощью условной логики.</span><span class="sxs-lookup"><span data-stu-id="9076a-136">The Data Profiling task does not have built-in features that allow you to use conditional logic to connect this task to downstream tasks based on the profile output.</span></span> <span data-ttu-id="9076a-137">Однако эту логику можно легко добавить, для чего необходимо включить в задачу «Скрипт» небольшую программу.</span><span class="sxs-lookup"><span data-stu-id="9076a-137">However, you can easily add this logic, with a small amount of programming, in a Script task.</span></span> <span data-ttu-id="9076a-138">Например, задаче «Скрипт» можно поручить выполнение запроса Xpath к выходному файлу задачи «Профилирование данных».</span><span class="sxs-lookup"><span data-stu-id="9076a-138">For example, the Script task could perform an XPath query against the output file of the Data Profiling task.</span></span> <span data-ttu-id="9076a-139">Этот запрос мог бы выявить, превышает ли процентная доля значений NULL в том или ином столбце определенное пороговое значение.</span><span class="sxs-lookup"><span data-stu-id="9076a-139">The query could determine whether the percentage of null values in a particular column exceeds a certain threshold.</span></span> <span data-ttu-id="9076a-140">Если эта процентная доля превышает заданное пороговое значение, можно прервать выполнение пакета и до его возобновления разрешить проблему в исходных данных.</span><span class="sxs-lookup"><span data-stu-id="9076a-140">If the percentage exceeds the threshold, you could interrupt the package and resolve the problem in the source data before continuing.</span></span> <span data-ttu-id="9076a-141">Дополнительные сведения см. в разделе [Включение задачи "Профилирование данных" в рабочий процесс пакета](incorporate-a-data-profiling-task-in-package-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="9076a-141">For more information, see [Incorporate a Data Profiling Task in Package Workflow](incorporate-a-data-profiling-task-in-package-workflow.md).</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="9076a-142">См. также</span><span class="sxs-lookup"><span data-stu-id="9076a-142">Related Content</span></span>  
 [<span data-ttu-id="9076a-143">Схема данных профилировщика</span><span class="sxs-lookup"><span data-stu-id="9076a-143">Data Profiler Schema</span></span>](https://go.microsoft.com/fwlink/?LinkId=251524)  
  
  
