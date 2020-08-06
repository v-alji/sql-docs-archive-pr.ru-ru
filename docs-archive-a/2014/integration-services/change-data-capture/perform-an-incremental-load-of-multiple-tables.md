---
title: Выполнение добавочной загрузки нескольких таблиц | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],multiple tables
ms.assetid: 39252dd5-09c3-46f9-a17b-15208cfd336d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e4bf81d1d529e8102271c66839440ef712219600
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656529"
---
# <a name="perform-an-incremental-load-of-multiple-tables"></a><span data-ttu-id="859ca-102">Выполнение добавочной загрузки нескольких таблиц</span><span class="sxs-lookup"><span data-stu-id="859ca-102">Perform an Incremental Load of Multiple Tables</span></span>
  <span data-ttu-id="859ca-103">На диаграмме в разделе [Улучшение добавочных загрузок с помощью системы отслеживания измененных данных](change-data-capture-ssis.md)показан базовый пакет, выполняющий добавочную загрузку только для одной таблицы.</span><span class="sxs-lookup"><span data-stu-id="859ca-103">In the topic, [Improving Incremental Loads with Change Data Capture](change-data-capture-ssis.md), the diagram illustrates a basic package that performs an incremental load on just one table.</span></span> <span data-ttu-id="859ca-104">Однако чаще требуется добавочная загрузка не одной, а нескольких таблиц</span><span class="sxs-lookup"><span data-stu-id="859ca-104">However, loading one table is not as common as having to perform an incremental load of multiple tables.</span></span>  
  
 <span data-ttu-id="859ca-105">Если выполняется добавочная загрузка нескольких таблиц, некоторые шаги достаточно выполнить один раз для всех таблиц, а другие приходится повторять для каждой исходной таблицы.</span><span class="sxs-lookup"><span data-stu-id="859ca-105">When you perform an incremental load of multiple tables, some steps have to be performed once for all the tables, and other steps have to be repeated for each source table.</span></span> <span data-ttu-id="859ca-106">Существуют следующие режимы выполнения этих шагов в службах [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="859ca-106">You have more than one option for implementing these steps in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="859ca-107">Использование родительского пакета и дочерних пакетов.</span><span class="sxs-lookup"><span data-stu-id="859ca-107">Use a parent package and child packages.</span></span>  
  
-   <span data-ttu-id="859ca-108">Использование нескольких задач потока данных в одном пакете.</span><span class="sxs-lookup"><span data-stu-id="859ca-108">Use multiple Data Flow tasks in a single package.</span></span>  
  
## <a name="loading-multiple-tables-by-using-a-parent-package-and-multiple-child-packages"></a><span data-ttu-id="859ca-109">Загрузка нескольких таблиц с помощью родительского пакета и нескольких дочерних пакетов</span><span class="sxs-lookup"><span data-stu-id="859ca-109">Loading Multiple Tables by Using a Parent Package and Multiple Child Packages</span></span>  
 <span data-ttu-id="859ca-110">Для шагов, которые достаточно выполнить один раз, можно использовать родительский пакет.</span><span class="sxs-lookup"><span data-stu-id="859ca-110">You can use a parent package to perform those steps that only have to be done once.</span></span> <span data-ttu-id="859ca-111">Дочерние пакеты выполнят шаги, которые необходимо повторить для каждой исходной таблицы.</span><span class="sxs-lookup"><span data-stu-id="859ca-111">The child packages will perform those steps that have to be done for each source table.</span></span>  
  
#### <a name="to-create-a-parent-package-that-performs-those-steps-that-only-have-to-be-done-once"></a><span data-ttu-id="859ca-112">Создание родительского пакета для шагов, которые достаточно выполнить один раз.</span><span class="sxs-lookup"><span data-stu-id="859ca-112">To create a parent package that performs those steps that only have to be done once</span></span>  
  
1.  <span data-ttu-id="859ca-113">Создайте родительский пакет.</span><span class="sxs-lookup"><span data-stu-id="859ca-113">Create a parent package.</span></span>  
  
2.  <span data-ttu-id="859ca-114">В потоке управления используйте задачу «Выполнение SQL» или выражения служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , чтобы вычислить конечные точки.</span><span class="sxs-lookup"><span data-stu-id="859ca-114">In the control flow, use an Execute SQL task or [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expressions to calculate the endpoints.</span></span>  
  
     <span data-ttu-id="859ca-115">Пример вычисления конечных точек см. в разделе [Задание интервала для информации об изменениях данных](specify-an-interval-of-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="859ca-115">For an example of how to calculate endpoints, see [Specify an Interval of Change Data](specify-an-interval-of-change-data.md).</span></span>  
  
3.  <span data-ttu-id="859ca-116">Если требуется, используйте контейнер «цикл по элементам», чтобы задержать выполнение, пока не будут готовы измененные данные для выбранного периода.</span><span class="sxs-lookup"><span data-stu-id="859ca-116">If needed, use a For Loop container to delay execution until change data for the selected period is ready.</span></span>  
  
     <span data-ttu-id="859ca-117">Пример подобного контейнера "цикл по элементам" см. в разделе [Определение готовности информации об изменениях данных](determine-whether-the-change-data-is-ready.md).</span><span class="sxs-lookup"><span data-stu-id="859ca-117">For an example of such a For Loop container, see [Determine Whether the Change Data Is Ready](determine-whether-the-change-data-is-ready.md).</span></span>  
  
4.  <span data-ttu-id="859ca-118">Используйте несколько задач «Выполнение пакета», чтобы выполнить дочерние пакеты для каждой загружаемой таблицы.</span><span class="sxs-lookup"><span data-stu-id="859ca-118">Use multiple Execute Package tasks to execute child packages for each table to be loaded.</span></span> <span data-ttu-id="859ca-119">Передайте конечные точки, вычисленные в родительском пакете, в каждый дочерний пакет с помощью конфигураций переменной родительского пакета.</span><span class="sxs-lookup"><span data-stu-id="859ca-119">Pass the endpoints calculated in the parent package to each child package by using Parent Package Variable configurations.</span></span>  
  
     <span data-ttu-id="859ca-120">Дополнительные сведения см. в разделах [Задача "Выполнение пакета"](../control-flow/execute-package-task.md) и [Использование значений переменных и параметров в дочернем пакете](../use-the-values-of-variables-and-parameters-in-a-child-package.md).</span><span class="sxs-lookup"><span data-stu-id="859ca-120">For more information, see [Execute Package Task](../control-flow/execute-package-task.md) and [Use the Values of Variables and Parameters in a Child Package](../use-the-values-of-variables-and-parameters-in-a-child-package.md).</span></span>  
  
#### <a name="to-create-child-packages-to-perform-those-steps-that-have-to-be-done-for-each-source-table"></a><span data-ttu-id="859ca-121">Создание дочерних пакетов для шагов, которые нужно выполнить для каждой исходной таблицы</span><span class="sxs-lookup"><span data-stu-id="859ca-121">To create child packages to perform those steps that have to be done for each source table</span></span>  
  
1.  <span data-ttu-id="859ca-122">Создайте дочерний пакет для каждой исходной таблицы.</span><span class="sxs-lookup"><span data-stu-id="859ca-122">For each source table, create a child package.</span></span>  
  
2.  <span data-ttu-id="859ca-123">В потоке управления используйте задачу «Скрипт» или «Выполнение SQL», чтобы составить инструкцию SQL, которая будет использоваться для запроса изменений.</span><span class="sxs-lookup"><span data-stu-id="859ca-123">In the control flow, use a Script task or an Execute SQL task to assemble the SQL statement that will be used to query for changes.</span></span>  
  
     <span data-ttu-id="859ca-124">Пример по сборке запроса см. в разделе [Подготовка к запросу информации об изменениях](prepare-to-query-for-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="859ca-124">For an example of how to assemble the query, see [Prepare to Query for the Change Data](prepare-to-query-for-the-change-data.md).</span></span>  
  
3.  <span data-ttu-id="859ca-125">Используйте одну задачу потока данных в каждом дочернем пакете, чтобы загрузить измененные данные и применить их к назначению.</span><span class="sxs-lookup"><span data-stu-id="859ca-125">Use a single Data Flow task in each child package to load the change data and apply it to the destination.</span></span> <span data-ttu-id="859ca-126">Настройте поток данных, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="859ca-126">Configure the Data Flow as described in the following steps:</span></span>  
  
    1.  <span data-ttu-id="859ca-127">В потоке данных используйте исходный компонент, чтобы запросить изменения из таблиц изменений, входящие в диапазон выбранных конечных точек.</span><span class="sxs-lookup"><span data-stu-id="859ca-127">In the data flow, use a source component to query the change tables for the changes that fall within the selected endpoints.</span></span>  
  
         <span data-ttu-id="859ca-128">Пример запроса таблиц изменений см. в разделе [Получение и интерпретация измененных данных](retrieve-and-understand-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="859ca-128">For an example of how to query the change tables, see [Retrieve and Understand the Change Data](retrieve-and-understand-the-change-data.md).</span></span>  
  
    2.  <span data-ttu-id="859ca-129">Преобразование «Условное разбиение» предназначено для направления операций вставки, обновления и удаления на различные выходы для необходимой обработки.</span><span class="sxs-lookup"><span data-stu-id="859ca-129">Use a Conditional Split transformation to direct inserts, updates, and deletes to different outputs for appropriate processing.</span></span>  
  
         <span data-ttu-id="859ca-130">Пример, демонстрирующий настройку этого преобразования на непосредственный вывод, см. в разделе [Обработка операций вставки, обновления и удаления](process-inserts-updates-and-deletes.md).</span><span class="sxs-lookup"><span data-stu-id="859ca-130">For an example of how to configure this transformation to direct output, see [Process Inserts, Updates, and Deletes](process-inserts-updates-and-deletes.md).</span></span>  
  
    3.  <span data-ttu-id="859ca-131">Используйте компонент назначения, чтобы применить операции вставки в целевой базе данных.</span><span class="sxs-lookup"><span data-stu-id="859ca-131">Use a destination component to apply the inserts to the destination.</span></span> <span data-ttu-id="859ca-132">Преобразования «Команда OLE DB» с параметризованными инструкциями UPDATE и DELETE предназначены для применения операций обновления и удаления в целевой базе данных.</span><span class="sxs-lookup"><span data-stu-id="859ca-132">Use OLE DB Command transformations with parameterized UPDATE and DELETE statements to apply updates and deletes to the destination.</span></span>  
  
         <span data-ttu-id="859ca-133">Пример, демонстрирующий использование этого преобразования для применения операций обновления и удаления, см. в разделе [Применение изменений в назначении](apply-the-changes-to-the-destination.md).</span><span class="sxs-lookup"><span data-stu-id="859ca-133">For an example of how to use this transformation to apply updates and deletes, see [Apply the Changes to the Destination](apply-the-changes-to-the-destination.md).</span></span>  
  
## <a name="loading-multiple-tables-by-using-multiple-data-flow-tasks-in-a-single-package"></a><span data-ttu-id="859ca-134">Загрузка нескольких таблиц с помощью нескольких задач потока данных в одном пакете</span><span class="sxs-lookup"><span data-stu-id="859ca-134">Loading Multiple Tables by Using Multiple Data Flow Tasks in a Single Package</span></span>  
 <span data-ttu-id="859ca-135">Можно также использовать один пакет, содержащий отдельную задачу потока данных для каждой загружаемой исходной таблицы.</span><span class="sxs-lookup"><span data-stu-id="859ca-135">Alternatively, you can use a single package that contains a separate Data Flow task for each source table to be loaded.</span></span>  
  
#### <a name="to-load-multiple-tables-by-using-multiple-data-flow-tasks-in-a-single-package"></a><span data-ttu-id="859ca-136">Загрузка нескольких таблиц с помощью нескольких задач потока данных в одном пакете</span><span class="sxs-lookup"><span data-stu-id="859ca-136">To load multiple tables by using multiple Data Flow tasks in a single package</span></span>  
  
1.  <span data-ttu-id="859ca-137">Создайте один пакет.</span><span class="sxs-lookup"><span data-stu-id="859ca-137">Create a single package.</span></span>  
  
2.  <span data-ttu-id="859ca-138">В потоке управления используйте задачу «Выполнение SQL» или выражения служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , чтобы вычислить конечные точки.</span><span class="sxs-lookup"><span data-stu-id="859ca-138">In the control flow, use an Execute SQL Task or [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expressions to calculate the endpoints.</span></span>  
  
     <span data-ttu-id="859ca-139">Пример вычисления конечных точек см. в разделе [Задание интервала для информации об изменениях данных](specify-an-interval-of-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="859ca-139">For an example of how to calculate endpoints, see [Specify an Interval of Change Data](specify-an-interval-of-change-data.md).</span></span>  
  
3.  <span data-ttu-id="859ca-140">Если требуется, используйте контейнер «цикл по элементам», чтобы задержать выполнение, пока не будут готовы измененные данные для выбранного интервала.</span><span class="sxs-lookup"><span data-stu-id="859ca-140">If needed, use a For Loop container to delay execution until the change data for the selected interval is ready.</span></span>  
  
     <span data-ttu-id="859ca-141">Пример подобного контейнера "цикл по элементам" см. в разделе [Определение готовности информации об изменениях данных](determine-whether-the-change-data-is-ready.md).</span><span class="sxs-lookup"><span data-stu-id="859ca-141">For an example of such a For Loop container, see [Determine Whether the Change Data Is Ready](determine-whether-the-change-data-is-ready.md).</span></span>  
  
4.  <span data-ttu-id="859ca-142">Используйте задачу «Скрипт» или задачу «Выполнение SQL», чтобы собрать инструкцию SQL, которая будет использоваться для запроса изменений.</span><span class="sxs-lookup"><span data-stu-id="859ca-142">Use a Script task or an Execute SQL task to assemble the SQL statement that will be used to query for changes.</span></span>  
  
     <span data-ttu-id="859ca-143">Пример по сборке запроса см. в разделе [Подготовка к запросу информации об изменениях](prepare-to-query-for-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="859ca-143">For an example of how to assemble the query, see [Prepare to Query for the Change Data](prepare-to-query-for-the-change-data.md).</span></span>  
  
5.  <span data-ttu-id="859ca-144">Используйте несколько задач потока данных, чтобы загрузить измененные данные из каждой исходной таблицы и применить их к назначению.</span><span class="sxs-lookup"><span data-stu-id="859ca-144">Use multiple Data Flow tasks to load the change data from each source table and apply it to the destination.</span></span> <span data-ttu-id="859ca-145">Настройте каждую задачу потока данных, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="859ca-145">Configure each Data Flow task as described in the following steps.</span></span>  
  
    1.  <span data-ttu-id="859ca-146">В каждом потоке данных используйте исходный компонент для запроса изменений, находящихся в диапазоне выбранных конечных точек, из таблиц изменений.</span><span class="sxs-lookup"><span data-stu-id="859ca-146">In each data flow, use a source component to query the change tables for the changes that fall within the selected endpoints.</span></span>  
  
         <span data-ttu-id="859ca-147">Пример запроса таблиц изменений см. в разделе [Получение и интерпретация измененных данных](retrieve-and-understand-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="859ca-147">For an example of how to query the change tables, see [Retrieve and Understand the Change Data](retrieve-and-understand-the-change-data.md).</span></span>  
  
    2.  <span data-ttu-id="859ca-148">Преобразование «Условное разбиение» предназначено для направления операций вставки, обновления и удаления на различные выходы для необходимой обработки.</span><span class="sxs-lookup"><span data-stu-id="859ca-148">Use a Conditional Split transformation to direct inserts, updates, and deletes to different outputs for appropriate processing.</span></span>  
  
         <span data-ttu-id="859ca-149">Пример, демонстрирующий настройку этого преобразования на непосредственный вывод, см. в разделе [Обработка операций вставки, обновления и удаления](process-inserts-updates-and-deletes.md).</span><span class="sxs-lookup"><span data-stu-id="859ca-149">For an example of how to configure this transformation to direct output, see [Process Inserts, Updates, and Deletes](process-inserts-updates-and-deletes.md).</span></span>  
  
    3.  <span data-ttu-id="859ca-150">Используйте компонент назначения, чтобы применить операции вставки в целевой базе данных.</span><span class="sxs-lookup"><span data-stu-id="859ca-150">Use a destination component to apply the inserts to the destination.</span></span> <span data-ttu-id="859ca-151">Преобразования «Команда OLE DB» с параметризованными инструкциями UPDATE и DELETE предназначены для применения операций обновления и удаления в целевой базе данных.</span><span class="sxs-lookup"><span data-stu-id="859ca-151">Use OLE DB Command transformations with parameterized UPDATE and DELETE statements to apply updates and deletes to the destination.</span></span>  
  
         <span data-ttu-id="859ca-152">Пример, демонстрирующий использование этого преобразования для применения операций обновления и удаления, см. в разделе [Применение изменений в назначении](apply-the-changes-to-the-destination.md).</span><span class="sxs-lookup"><span data-stu-id="859ca-152">For an example of how to use this transformation to apply updates and deletes, see [Apply the Changes to the Destination](apply-the-changes-to-the-destination.md).</span></span>  
  
  
