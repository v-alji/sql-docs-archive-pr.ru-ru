---
title: Задание интервала для информации об изменениях данных | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],specifying interval
ms.assetid: 17899078-8ba3-4f40-8769-e9837dc3ec60
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 70b9c14d609f2db69ee5751eca18acb5262a07a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657840"
---
# <a name="specify-an-interval-of-change-data"></a><span data-ttu-id="ca0db-102">Задание интервала для информации об изменениях данных</span><span class="sxs-lookup"><span data-stu-id="ca0db-102">Specify an Interval of Change Data</span></span>
  <span data-ttu-id="ca0db-103">Первой задачей в потоке управления пакета служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , который выполняет добавочную загрузку информации об измененных данных, является вычисление конечных точек интервала изменений.</span><span class="sxs-lookup"><span data-stu-id="ca0db-103">In the control flow of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that performs an incremental load of change data, the first task is to calculate the endpoints of the change interval.</span></span> <span data-ttu-id="ca0db-104">Эти конечные точки имеют значения `datetime` и сохраняются в переменных пакета для дальнейшего использования в пакете.</span><span class="sxs-lookup"><span data-stu-id="ca0db-104">These endpoints are `datetime` values and will be stored in package variables for use later in the package.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ca0db-105">Описание общего процесса по проектированию потока управления см. в разделе [Система отслеживания измененных данных (SSIS)](change-data-capture-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="ca0db-105">For a description of the overall process of designing the control flow, see [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span></span>  
  
## <a name="set-up-package-variables-for-the-endpoints"></a><span data-ttu-id="ca0db-106">Настройка переменных пакета для конечных точек</span><span class="sxs-lookup"><span data-stu-id="ca0db-106">Set Up Package Variables for the Endpoints</span></span>  
 <span data-ttu-id="ca0db-107">Прежде чем настраивать задачи «Выполнение SQL» для вычисления конечных точек, необходимо определить переменные пакета, в которых будут храниться конечные точки.</span><span class="sxs-lookup"><span data-stu-id="ca0db-107">Before configuring the Execute SQL task to calculate the endpoints, the package variables that will store the endpoints have to be defined.</span></span>  
  
#### <a name="to-set-up-package-variables"></a><span data-ttu-id="ca0db-108">Настройка переменных пакета</span><span class="sxs-lookup"><span data-stu-id="ca0db-108">To set up package variables</span></span>  
  
1.  <span data-ttu-id="ca0db-109">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте новый проект служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ca0db-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open a new [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="ca0db-110">В окне **Переменные** создайте следующие переменные:</span><span class="sxs-lookup"><span data-stu-id="ca0db-110">In the **Variables** window, create the following variables:</span></span>  
  
    1.  <span data-ttu-id="ca0db-111">Создайте переменную с типом данных `datetime` для хранения начальной точки интервала.</span><span class="sxs-lookup"><span data-stu-id="ca0db-111">Create a variable with the `datetime` data type to hold the starting point for the interval.</span></span>  
  
         <span data-ttu-id="ca0db-112">В этом примере используется имя переменной ExtractStartTime.</span><span class="sxs-lookup"><span data-stu-id="ca0db-112">This example uses the variable name, ExtractStartTime.</span></span>  
  
    2.  <span data-ttu-id="ca0db-113">Создайте переменную с типом данных `datetime` для хранения конечной точки интервала.</span><span class="sxs-lookup"><span data-stu-id="ca0db-113">Create another variable with the `datetime` data type to hold the ending point for the interval.</span></span>  
  
         <span data-ttu-id="ca0db-114">В этом примере используется имя переменной ExtractEndTime.</span><span class="sxs-lookup"><span data-stu-id="ca0db-114">This example uses the variable name, ExtractEndTime.</span></span>  
  
 <span data-ttu-id="ca0db-115">Если конечные точки вычисляются в главном пакете, который управляет несколькими дочерними пакетами, можно использовать конфигурации переменных родительского пакета, чтобы передать значения этих переменных каждому дочернему пакету.</span><span class="sxs-lookup"><span data-stu-id="ca0db-115">If you calculate the endpoints in a master package that executes multiple child packages, you can use Parent Package Variable configurations to pass the values of these variables to each child package.</span></span> <span data-ttu-id="ca0db-116">Дополнительные сведения см. в разделах [Задача "Выполнение пакета"](../control-flow/execute-package-task.md) и [Использование значений переменных и параметров в дочернем пакете](../use-the-values-of-variables-and-parameters-in-a-child-package.md).</span><span class="sxs-lookup"><span data-stu-id="ca0db-116">For more information, see [Execute Package Task](../control-flow/execute-package-task.md) and [Use the Values of Variables and Parameters in a Child Package](../use-the-values-of-variables-and-parameters-in-a-child-package.md).</span></span>  
  
## <a name="calculate-a-starting-point-and-an-ending-point-for-change-data"></a><span data-ttu-id="ca0db-117">Вычисление начальной и конечной точек для измененных данных</span><span class="sxs-lookup"><span data-stu-id="ca0db-117">Calculate a Starting Point and an Ending Point for Change Data</span></span>  
 <span data-ttu-id="ca0db-118">Когда переменные пакета для конечных точек интервала настроены, можно вычислить фактические значения конечных точек и сопоставить эти значения с соответствующими переменными пакета.</span><span class="sxs-lookup"><span data-stu-id="ca0db-118">After you set up the package variables for the interval endpoints, you can calculate the actual values for those endpoints and map those values to the corresponding package variables.</span></span> <span data-ttu-id="ca0db-119">Поскольку конечные точки имеют значения `datetime`, необходимо использовать функции, поддерживающие вычисление или обработку значений `datetime`.</span><span class="sxs-lookup"><span data-stu-id="ca0db-119">Because those endpoints are `datetime` values, you will have to use functions that can calculate or work with `datetime` values.</span></span> <span data-ttu-id="ca0db-120">Язык выражений служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] и язык Transact-SQL имеют функции, работающие со значениями `datetime`:</span><span class="sxs-lookup"><span data-stu-id="ca0db-120">Both the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expression language and Transact-SQL have functions that work with `datetime` values:</span></span>  
  
 <span data-ttu-id="ca0db-121">Функции языка выражений служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], работающие со значениями `datetime`</span><span class="sxs-lookup"><span data-stu-id="ca0db-121">Functions in the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expression language that work with `datetime` values</span></span>  
 -   [<span data-ttu-id="ca0db-122">DATEADD (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="ca0db-122">DATEADD &#40;SSIS Expression&#41;</span></span>](../expressions/dateadd-ssis-expression.md)  
  
-   [<span data-ttu-id="ca0db-123">DATEDIFF (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="ca0db-123">DATEDIFF &#40;SSIS Expression&#41;</span></span>](../expressions/datediff-ssis-expression.md)  
  
-   [<span data-ttu-id="ca0db-124">DATEPART (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="ca0db-124">DATEPART &#40;SSIS Expression&#41;</span></span>](../expressions/datepart-ssis-expression.md)  
  
-   [<span data-ttu-id="ca0db-125">DAY (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="ca0db-125">DAY &#40;SSIS Expression&#41;</span></span>](../expressions/day-ssis-expression.md)  
  
-   [<span data-ttu-id="ca0db-126">GETDATE (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="ca0db-126">GETDATE &#40;SSIS Expression&#41;</span></span>](../expressions/getdate-ssis-expression.md)  
  
-   [<span data-ttu-id="ca0db-127">GETUTCDATE (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="ca0db-127">GETUTCDATE &#40;SSIS Expression&#41;</span></span>](../expressions/getutcdate-ssis-expression.md)  
  
-   [<span data-ttu-id="ca0db-128">MONTH (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="ca0db-128">MONTH &#40;SSIS Expression&#41;</span></span>](../expressions/month-ssis-expression.md)  
  
-   [<span data-ttu-id="ca0db-129">YEAR (выражение служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="ca0db-129">YEAR &#40;SSIS Expression&#41;</span></span>](../expressions/year-ssis-expression.md)  
  
 <span data-ttu-id="ca0db-130">Функции языка Transact-SQL, работающие со значениями `datetime`</span><span class="sxs-lookup"><span data-stu-id="ca0db-130">Functions in Transact-SQL that work with `datetime` values</span></span>  
 <span data-ttu-id="ca0db-131">[Типы данных и функции даты и времени (Transact-SQL)](/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ca0db-131">[Date and Time Data Types and Functions &#40;Transact-SQL&#41;](/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql).</span></span>  
  
 <span data-ttu-id="ca0db-132">Прежде чем использовать какую-либо из этих функций `datetime` для вычисления конечных точек, необходимо определить, является ли интервал фиксированным и регулярно повторяющимся.</span><span class="sxs-lookup"><span data-stu-id="ca0db-132">Before you use any one of these `datetime` functions to calculate the endpoints, you have to determine whether the interval is fixed and occurs on a regular schedule.</span></span> <span data-ttu-id="ca0db-133">Обычно требуется регулярное применение изменений, произошедших в исходных таблицах, к целевым таблицам.</span><span class="sxs-lookup"><span data-stu-id="ca0db-133">Typically, you want to apply changes that have occurred in source tables to destination tables on a regular schedule.</span></span> <span data-ttu-id="ca0db-134">Например, эти изменения могут применяться каждый час, ежедневно или еженедельно.</span><span class="sxs-lookup"><span data-stu-id="ca0db-134">For example, you might want to apply those changes on an hourly, daily, or weekly basis.</span></span>  
  
 <span data-ttu-id="ca0db-135">Когда характер интервала изменений установлен (фиксированный или случайный), можно вычислять конечные точки.</span><span class="sxs-lookup"><span data-stu-id="ca0db-135">After you understand whether your change interval is fixed or is more random, you can calculate the endpoints:</span></span>  
  
-   <span data-ttu-id="ca0db-136">**Вычисление начальной даты и времени**.</span><span class="sxs-lookup"><span data-stu-id="ca0db-136">**Calculating the starting date and time**.</span></span> <span data-ttu-id="ca0db-137">В качестве текущей начальной даты и времени используется конечная дата и время предыдущей загрузки.</span><span class="sxs-lookup"><span data-stu-id="ca0db-137">You use the ending date and time from the previous load as the current starting date and time.</span></span> <span data-ttu-id="ca0db-138">Если для добавочных загрузок используется фиксированный интервал, значение можно вычислить с помощью функций `datetime` языка Transact-SQL или языка выражений служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ca0db-138">If you use a fixed interval for incremental loads, you can calculate this value by using the `datetime` functions of Transact-SQL or of the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expression language.</span></span> <span data-ttu-id="ca0db-139">В других случаях иногда приходится сохранять конечные точки между выполнениями и использовать задачи «Выполнение SQL» или «Скрипт» для загрузки предыдущей конечной точки.</span><span class="sxs-lookup"><span data-stu-id="ca0db-139">Otherwise, you might have to persist the endpoints between executions, and use an Execute SQL task or a Script task to load the previous endpoint.</span></span>  
  
-   <span data-ttu-id="ca0db-140">**Вычисление конечной даты и времени**.</span><span class="sxs-lookup"><span data-stu-id="ca0db-140">**Calculating the ending date and time**.</span></span> <span data-ttu-id="ca0db-141">Если для добавочной загрузки используется фиксированный интервал, текущая конечная дата и время вычисляются как смещение относительно начальной даты и времени.</span><span class="sxs-lookup"><span data-stu-id="ca0db-141">If you use a fixed interval for incremental loads, calculate the current ending date and time as an offset from the starting date and time.</span></span> <span data-ttu-id="ca0db-142">Опять же, это значение можно вычислить с помощью `datetime` функций Transact-SQL или [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] языка выражений.</span><span class="sxs-lookup"><span data-stu-id="ca0db-142">Again, you can calculate this value by using the `datetime` functions of Transact-SQL or of the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expression language.</span></span>  
  
 <span data-ttu-id="ca0db-143">В следующей процедуре используется фиксированный интервал изменений и предполагается, что пакет добавочной загрузки выполняется ежедневно без каких-либо исключений.</span><span class="sxs-lookup"><span data-stu-id="ca0db-143">In the following procedure, the change interval uses a fixed interval and assumes that the incremental load package is run daily without exception.</span></span> <span data-ttu-id="ca0db-144">Иначе информация об измененных данных за пропущенные интервалы будет потеряна.</span><span class="sxs-lookup"><span data-stu-id="ca0db-144">Otherwise, change data for missed intervals would be lost.</span></span> <span data-ttu-id="ca0db-145">Начальной точкой интервала является полночь позавчерашнего дня, т. е. от 24 до 48 часов назад.</span><span class="sxs-lookup"><span data-stu-id="ca0db-145">The starting point for the interval is midnight the day before yesterday, that is, between 24 and 48 hours ago.</span></span> <span data-ttu-id="ca0db-146">Конечной точкой интервала является полночь вчерашнего дня, т. е. прошлая ночь, от 0 до 24 часов назад.</span><span class="sxs-lookup"><span data-stu-id="ca0db-146">The ending point for the interval is midnight yesterday, that is, the previous night, between 0 and 24 hours ago.</span></span>  
  
#### <a name="to-calculate-the-starting-point-and-ending-point-for-the-capture-interval"></a><span data-ttu-id="ca0db-147">Вычисление начальной и конечной точек интервала отслеживания</span><span class="sxs-lookup"><span data-stu-id="ca0db-147">To calculate the starting point and ending point for the capture interval</span></span>  
  
1.  <span data-ttu-id="ca0db-148">На вкладке **Поток управления** в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] добавьте в пакет задачу «Выполнение SQL».</span><span class="sxs-lookup"><span data-stu-id="ca0db-148">On the **Control Flow** tab of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, add an Execute SQL Task to the package.</span></span>  
  
2.  <span data-ttu-id="ca0db-149">Откройте **Редактор задачи «Выполнение SQL»** и на странице **Общие** выберите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="ca0db-149">Open the **Execute SQL Task Editor**, and on the **General** page of the editor, select the following options:</span></span>  
  
    1.  <span data-ttu-id="ca0db-150">Для параметра **ResultSet**выберите значение **Одна строка**.</span><span class="sxs-lookup"><span data-stu-id="ca0db-150">For **ResultSet**, select **Single row**.</span></span>  
  
    2.  <span data-ttu-id="ca0db-151">Настройте допустимое соединение с базой данных-источником.</span><span class="sxs-lookup"><span data-stu-id="ca0db-151">Configure a valid connection to the source database.</span></span>  
  
    3.  <span data-ttu-id="ca0db-152">Для параметра **SQLSourceType**выберите значение **Прямой ввод**.</span><span class="sxs-lookup"><span data-stu-id="ca0db-152">For **SQLSourceType**, select **Direct input**.</span></span>  
  
    4.  <span data-ttu-id="ca0db-153">В поле **SQLStatement**введите приведенную ниже инструкцию SQL:</span><span class="sxs-lookup"><span data-stu-id="ca0db-153">For **SQLStatement**, enter the following SQL statement:</span></span>  
  
        ```  
        SELECT DATEADD(dd,0, DATEDIFF(dd,0,GETDATE()-1)) AS ExtractStartTime,  
          DATEADD(dd,0, DATEDIFF(dd,0,GETDATE())) AS ExtractEndTime  
  
        ```  
  
3.  <span data-ttu-id="ca0db-154">На странице **Результирующий набор** **Редактора задачи «Выполнение SQL»** сопоставьте результат ExtractStartTime с переменной ExtractStartTime пакета, а результат ExtractEndTime — с переменной ExtractEndTime пакета.</span><span class="sxs-lookup"><span data-stu-id="ca0db-154">On the **Result Set** page of the **Execute SQL Task Editor**, map the ExtractStartTime result to the ExtractStartTime package variable, and map the ExtractEndTime result to the ExtractEndTime package variable.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ca0db-155">Если для установки значения переменной служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] используется выражение, это выражение вычисляется при каждом обращении к значению переменной.</span><span class="sxs-lookup"><span data-stu-id="ca0db-155">When you use an expression to set the value of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] variable, the expression is evaluated every time that the value of the variable is accessed.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="ca0db-156">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="ca0db-156">Next Step</span></span>  
 <span data-ttu-id="ca0db-157">После вычисления начальной и конечной точек диапазона изменений необходимо определить, готовы ли измененные данные.</span><span class="sxs-lookup"><span data-stu-id="ca0db-157">After you calculate the starting point and ending point for a range of changes, the next step is to determine whether the change data is ready.</span></span>  
  
 <span data-ttu-id="ca0db-158">**Следующая статья:** [Определение готовности информации об изменениях данных](determine-whether-the-change-data-is-ready.md)</span><span class="sxs-lookup"><span data-stu-id="ca0db-158">**Next topic:** [Determine Whether the Change Data Is Ready](determine-whether-the-change-data-is-ready.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca0db-159">См. также:</span><span class="sxs-lookup"><span data-stu-id="ca0db-159">See Also</span></span>  
 <span data-ttu-id="ca0db-160">[Использование переменных в пакетах](../use-variables-in-packages.md) </span><span class="sxs-lookup"><span data-stu-id="ca0db-160">[Use Variables in Packages](../use-variables-in-packages.md) </span></span>  
 <span data-ttu-id="ca0db-161">[Выражения служб Integration Services (SSIS)](../expressions/integration-services-ssis-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="ca0db-161">[Integration Services &#40;SSIS&#41; Expressions](../expressions/integration-services-ssis-expressions.md) </span></span>  
 <span data-ttu-id="ca0db-162">[Задача "Выполнение SQL"](../control-flow/execute-sql-task.md) </span><span class="sxs-lookup"><span data-stu-id="ca0db-162">[Execute SQL Task](../control-flow/execute-sql-task.md) </span></span>  
 [<span data-ttu-id="ca0db-163">Задача «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="ca0db-163">Script Task</span></span>](../control-flow/script-task.md)  
  
  
