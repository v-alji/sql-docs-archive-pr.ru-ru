---
title: Определение готовности информации об изменениях данных | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],determining readiness
ms.assetid: 04935f35-96cc-4d70-a250-0fd326f8daff
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5e672440938e366e53ba150f65d7bcd6aed8a58c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740214"
---
# <a name="determine-whether-the-change-data-is-ready"></a><span data-ttu-id="729d1-102">Определение готовности информации об  изменениях данных</span><span class="sxs-lookup"><span data-stu-id="729d1-102">Determine Whether the Change Data Is Ready</span></span>
  <span data-ttu-id="729d1-103">В потоке управления пакета служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , который выполняет добавочную загрузку измененных данных, вторая задача состоит в том, чтобы убедиться, что изменения данных за выбранный интервал времени подготовлены.</span><span class="sxs-lookup"><span data-stu-id="729d1-103">In the control flow of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that performs an incremental load of change data, the second task is to ensure that the change data for the selected interval is ready.</span></span> <span data-ttu-id="729d1-104">Этот шаг необходим потому, что процесс асинхронной записи, возможно, еще не дошел до выбранной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="729d1-104">This step is necessary because the asynchronous capture process might not yet have processed all the changes up to the selected endpoint.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="729d1-105">Первая задача потока управления — вычислить конечные точки интервала изменений.</span><span class="sxs-lookup"><span data-stu-id="729d1-105">The first task for the control flow is to calculate the endpoints of the change interval.</span></span> <span data-ttu-id="729d1-106">Дополнительные сведения об этой задаче см. в разделе [Задание интервала для информации об изменениях данных](specify-an-interval-of-change-data.md)</span><span class="sxs-lookup"><span data-stu-id="729d1-106">For more information about this task, see [Specify an Interval of Change Data](specify-an-interval-of-change-data.md).</span></span> <span data-ttu-id="729d1-107">Описание общего процесса по проектированию потока управления см. в разделе [Система отслеживания измененных данных (SSIS)](change-data-capture-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="729d1-107">For a description of the overall process of designing the control flow, see [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span></span>  
  
## <a name="understanding-the-components-of-the-solution"></a><span data-ttu-id="729d1-108">Основные сведения о компонентах решения</span><span class="sxs-lookup"><span data-stu-id="729d1-108">Understanding the Components of the Solution</span></span>  
 <span data-ttu-id="729d1-109">В решении, которое описывается в настоящем разделе, используется 4 компонента служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="729d1-109">The solution described in this topic uses 4 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] components:</span></span>  
  
-   <span data-ttu-id="729d1-110">Контейнер «цикл по элементам», который регулярно оценивает выходные данные задачи «Выполнение SQL».</span><span class="sxs-lookup"><span data-stu-id="729d1-110">A For Loop container that repeatedly evaluates the output of an Execute SQL Task.</span></span>  
  
-   <span data-ttu-id="729d1-111">Задача «Выполнение SQL», которая опрашивает обслуживаемые системой отслеживания измененных данных специальные таблицы, а затем использует полученную информацию, чтобы определить, готовы ли данные.</span><span class="sxs-lookup"><span data-stu-id="729d1-111">An Execute SQL task that queries special tables that the change data capture process maintains and then uses this information to determine whether data is ready.</span></span>  
  
-   <span data-ttu-id="729d1-112">Компонент, обеспечивающий задержку в процессе обработки в случаях, когда данные еще не готовы.</span><span class="sxs-lookup"><span data-stu-id="729d1-112">A component that implements a delay in processing when the data is not ready.</span></span> <span data-ttu-id="729d1-113">Это может быть либо задача «Скрипт», либо задача «Выполнение SQL».</span><span class="sxs-lookup"><span data-stu-id="729d1-113">This can be either a Script task or an Execute SQL task.</span></span>  
  
-   <span data-ttu-id="729d1-114">При необходимости используется компонент, извещающий об ошибке или о времени ожидания, если задача «Выполнение SQL» возвращает значение, указывающее на ошибку либо на время ожидания.</span><span class="sxs-lookup"><span data-stu-id="729d1-114">Optionally, a component that reports an error or a timeout when the Execute SQL task returns a value that indicates an error or a timeout condition.</span></span>  
  
 <span data-ttu-id="729d1-115">Эти компоненты задают или считывают значения нескольких переменных пакета, чтобы управлять потоком выполнения внутри цикла и позднее в пакете.</span><span class="sxs-lookup"><span data-stu-id="729d1-115">These components set or read the values of several package variables to control the flow of execution inside the loop and later in the package.</span></span>  
  
#### <a name="to-set-up-package-variables"></a><span data-ttu-id="729d1-116">Настройка переменных пакета</span><span class="sxs-lookup"><span data-stu-id="729d1-116">To set up package variables</span></span>  
  
1.  <span data-ttu-id="729d1-117">В окне [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]Переменные **среды** создайте следующие переменные.</span><span class="sxs-lookup"><span data-stu-id="729d1-117">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in the **Variables** window, create the following variables:</span></span>  
  
    1.  <span data-ttu-id="729d1-118">Создайте переменную с типом данных integer для хранения значения состояния, возвращаемого задачей «Выполнение SQL».</span><span class="sxs-lookup"><span data-stu-id="729d1-118">Create a variable with an integer data type to hold the status value returned by the Execute SQL task.</span></span>  
  
         <span data-ttu-id="729d1-119">В этом примере используется переменная с именем DataReady с исходным значением 0.</span><span class="sxs-lookup"><span data-stu-id="729d1-119">This example uses the variable name, DataReady, with an initial value of 0.</span></span>  
  
    2.  <span data-ttu-id="729d1-120">Создайте переменную для хранения периода времени задержки в случае, если данные не готовы.</span><span class="sxs-lookup"><span data-stu-id="729d1-120">Create a variable to hold the period of time to delay when data is not ready.</span></span> <span data-ttu-id="729d1-121">Если планируется реализовать задержку с помощью задачи «Скрипт», тип данных переменной должен быть integer.</span><span class="sxs-lookup"><span data-stu-id="729d1-121">If you plan to use a Script task to implement the delay, the variable should have an integer data type integer.</span></span> <span data-ttu-id="729d1-122">Если будет использоваться задача «Выполнение SQL» с инструкцией WAITFOR, переменная должна иметь строковый тип данных, чтобы переменная могла принимать значения типа «00:00:10».</span><span class="sxs-lookup"><span data-stu-id="729d1-122">If you plan to use an Execute SQL task with a WAITFOR statement, the variable should have a string data type to accept values such as "00:00:10".</span></span>  
  
         <span data-ttu-id="729d1-123">В этом примере используется переменная с именем DelaySeconds с исходным значением 10.</span><span class="sxs-lookup"><span data-stu-id="729d1-123">This example uses the variable name, DelaySeconds, with an initial value of 10.</span></span>  
  
    3.  <span data-ttu-id="729d1-124">Создайте переменную с типом данных integer для хранения текущей итерации цикла.</span><span class="sxs-lookup"><span data-stu-id="729d1-124">Create a variable with an integer data type to hold the current iteration of the loop.</span></span>  
  
         <span data-ttu-id="729d1-125">В этом примере используется переменная с именем TimeoutCount с исходным значением 0.</span><span class="sxs-lookup"><span data-stu-id="729d1-125">This example uses the variable name, TimeoutCount, with an initial value of 0.</span></span>  
  
    4.  <span data-ttu-id="729d1-126">Создайте переменную типа данных integer, чтобы указать, сколько раз цикл должен проверить данные перед созданием отчета об истечении времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="729d1-126">Create a variable with an integer data type to specify the number of times that the loop should test for data before reporting a timeout condition.</span></span>  
  
         <span data-ttu-id="729d1-127">В этом примере используется переменная с именем TimeoutCeiling с исходным значением 20.</span><span class="sxs-lookup"><span data-stu-id="729d1-127">This example uses the variable name, TimeoutCeiling, with an initial value of 20.</span></span>  
  
    5.  <span data-ttu-id="729d1-128">Создайте переменную с типом данных integer, которую можно использовать для указания первой загрузки измененных данных (необязательно).</span><span class="sxs-lookup"><span data-stu-id="729d1-128">(Optional) Create a variable with an integer data type that you can use to indicate the first load of change data.</span></span>  
  
         <span data-ttu-id="729d1-129">В этом примере используется переменная с именем IntervalID и проверяется только значение 0, указывающее на первоначальную загрузку.</span><span class="sxs-lookup"><span data-stu-id="729d1-129">This example uses the variable name, IntervalID, and checks only for a value of 0 to indicate the initial load.</span></span>  
  
## <a name="configuring-a-for-loop-container"></a><span data-ttu-id="729d1-130">Настройка контейнера «цикл по элементам»</span><span class="sxs-lookup"><span data-stu-id="729d1-130">Configuring a For Loop Container</span></span>  
 <span data-ttu-id="729d1-131">Вместе с набором переменных первым добавляемым компонентом является контейнер «цикл по элементам».</span><span class="sxs-lookup"><span data-stu-id="729d1-131">With the variables set, the For Loop container is the first component to be added.</span></span>  
  
#### <a name="to-configure-a-for-loop-container-to-wait-until-change-data-is-ready"></a><span data-ttu-id="729d1-132">Настройка контейнера «цикл по элементам» для ожидания готовности измененных данных</span><span class="sxs-lookup"><span data-stu-id="729d1-132">To configure a For Loop container to wait until change data is ready</span></span>  
  
1.  <span data-ttu-id="729d1-133">На вкладке **Поток управления** конструктора служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] добавьте к потоку управления контейнер «цикл по элементам».</span><span class="sxs-lookup"><span data-stu-id="729d1-133">On the **Control Flow** tab of the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, add a For Loop container to the control flow.</span></span>  
  
2.  <span data-ttu-id="729d1-134">Соедините задачу «Выполнение SQL», вычисляющую конечные точки интервала, с контейнером «цикл по элементам».</span><span class="sxs-lookup"><span data-stu-id="729d1-134">Connect the Execute SQL Task that calculates the endpoints of the interval to the For Loop container.</span></span>  
  
3.  <span data-ttu-id="729d1-135">В окне **Редактор циклов по элементам**выберите следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="729d1-135">In the **For Loop Editor**, select the following options:</span></span>  
  
    1.  <span data-ttu-id="729d1-136">В поле **InitExpression**введите выражение `@DataReady = 0`.</span><span class="sxs-lookup"><span data-stu-id="729d1-136">For **InitExpression**, enter `@DataReady = 0`.</span></span>  
  
         <span data-ttu-id="729d1-137">Это выражение задает исходное значение для переменной цикла.</span><span class="sxs-lookup"><span data-stu-id="729d1-137">This expression sets the initial value of the loop variable.</span></span>  
  
    2.  <span data-ttu-id="729d1-138">В поле **EvalExpression**введите `@DataReady == 0`.</span><span class="sxs-lookup"><span data-stu-id="729d1-138">For **EvalExpression**m, enter `@DataReady == 0`.</span></span>  
  
         <span data-ttu-id="729d1-139">Когда это выражение принимает значение **False**, выполнение цикла прекращается и начинается добавочная загрузка.</span><span class="sxs-lookup"><span data-stu-id="729d1-139">When this expression evaluates to **False**, execution passes out of the loop and the incremental load starts.</span></span>  
  
## <a name="configuring-the-execute-sql-task-that-queries-for-change-data"></a><span data-ttu-id="729d1-140">Настройка задачи «Выполнение SQL» для запроса об измененных данных</span><span class="sxs-lookup"><span data-stu-id="729d1-140">Configuring the Execute SQL Task That Queries for Change Data</span></span>  
 <span data-ttu-id="729d1-141">Внутри контейнера «цикл по элементам» добавьте задачу «Выполнение SQL».</span><span class="sxs-lookup"><span data-stu-id="729d1-141">Inside the For Loop container, you add an Execute SQL task.</span></span> <span data-ttu-id="729d1-142">Эта задача направляет запросы к таблицам, которые обслуживаются системой отслеживания измененных данных в базах данных.</span><span class="sxs-lookup"><span data-stu-id="729d1-142">This task queries the tables that the change data capture process maintains in the database.</span></span> <span data-ttu-id="729d1-143">Результат этого запроса — значение состояния, указывающее на готовность измененных данных.</span><span class="sxs-lookup"><span data-stu-id="729d1-143">The result of this query is a status value that indicates whether the change data is ready.</span></span>  
  
 <span data-ttu-id="729d1-144">В первом столбце следующей таблицы показаны значения, возвращаемые из задачи «Выполнение SQL» образцом запроса на языке Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="729d1-144">In the following table, the first column shows the values returned from the Execute SQL task by the sample Transact-SQL query.</span></span> <span data-ttu-id="729d1-145">Второй столбец показывает, как реагируют на эти значения остальные компоненты.</span><span class="sxs-lookup"><span data-stu-id="729d1-145">The second column shows how the other components respond to these values.</span></span>  
  
|<span data-ttu-id="729d1-146">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="729d1-146">Return Value</span></span>|<span data-ttu-id="729d1-147">Значение</span><span class="sxs-lookup"><span data-stu-id="729d1-147">Meaning</span></span>|<span data-ttu-id="729d1-148">Ответ</span><span class="sxs-lookup"><span data-stu-id="729d1-148">Response</span></span>|  
|------------------|-------------|--------------|  
|<span data-ttu-id="729d1-149">0</span><span class="sxs-lookup"><span data-stu-id="729d1-149">0</span></span>|<span data-ttu-id="729d1-150">Показывает, что измененные данные не готовы.</span><span class="sxs-lookup"><span data-stu-id="729d1-150">Indicates that the change data is not ready.</span></span><br /><br /> <span data-ttu-id="729d1-151">Отсутствуют записи системы отслеживания измененных данных за период после конечной точки выбранного интервала.</span><span class="sxs-lookup"><span data-stu-id="729d1-151">There are no change data capture records later than the ending point of the selected interval.</span></span>|<span data-ttu-id="729d1-152">Выполнение продолжает компонент, реализующий задержку.</span><span class="sxs-lookup"><span data-stu-id="729d1-152">Execution continues with the component that implements a delay.</span></span> <span data-ttu-id="729d1-153">Затем управление возвращается контейнеру «цикл по элементам», который продолжает проверку задачи «Выполнение SQL» до тех пор, пока возвращается значение 0.</span><span class="sxs-lookup"><span data-stu-id="729d1-153">Then control returns to the For Loop container, which continues to check the Execute SQL task as long as the value returned is 0.</span></span>|  
|<span data-ttu-id="729d1-154">1</span><span class="sxs-lookup"><span data-stu-id="729d1-154">1</span></span>|<span data-ttu-id="729d1-155">Может означать, что измененные данные не были отслежены на протяжении всего интервала, либо они были удалены.</span><span class="sxs-lookup"><span data-stu-id="729d1-155">Might indicate that the change data has not been captured for the complete interval, or that it has been deleted.</span></span> <span data-ttu-id="729d1-156">Это считается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="729d1-156">This is treated as an error condition.</span></span><br /><br /> <span data-ttu-id="729d1-157">Отсутствуют записи системы отслеживания измененных данных за период до начальной точки выбранного интервала.</span><span class="sxs-lookup"><span data-stu-id="729d1-157">There are no change data capture records earlier than the starting point of the selected interval</span></span>|<span data-ttu-id="729d1-158">Выполнение продолжает дополнительный компонент, который регистрирует ошибку.</span><span class="sxs-lookup"><span data-stu-id="729d1-158">Execution continues with the optional component that logs the error.</span></span>|  
|<span data-ttu-id="729d1-159">2</span><span class="sxs-lookup"><span data-stu-id="729d1-159">2</span></span>|<span data-ttu-id="729d1-160">Указывает, что данные готовы.</span><span class="sxs-lookup"><span data-stu-id="729d1-160">Indicates that data is ready.</span></span><br /><br /> <span data-ttu-id="729d1-161">Имеются записи системы отслеживания измененных данных как за период до начальной точки выбранного интервала, так и за период после конечной точки.</span><span class="sxs-lookup"><span data-stu-id="729d1-161">There are change data capture records that are both earlier than the starting point and later than the ending point of the selected interval.</span></span>|<span data-ttu-id="729d1-162">Вычисление выходит за пределы контейнера «цикл по элементам», и начинается добавочная загрузка.</span><span class="sxs-lookup"><span data-stu-id="729d1-162">Execution passes out of the For Loop container and the incremental load starts.</span></span>|  
|<span data-ttu-id="729d1-163">3</span><span class="sxs-lookup"><span data-stu-id="729d1-163">3</span></span>|<span data-ttu-id="729d1-164">Указывает на первоначальную загрузку всех доступных измененных данных.</span><span class="sxs-lookup"><span data-stu-id="729d1-164">Indicates the initial load of all available change data.</span></span><br /><br /> <span data-ttu-id="729d1-165">Условная логика получает это значение от специальной переменной пакета, которая используется только для этой цели.</span><span class="sxs-lookup"><span data-stu-id="729d1-165">The conditional logic obtains this value from a special package variable that is used only for this purpose.</span></span>|<span data-ttu-id="729d1-166">Вычисление выходит за пределы контейнера «цикл по элементам», и начинается добавочная загрузка.</span><span class="sxs-lookup"><span data-stu-id="729d1-166">Execution passes out of the For Loop container and the incremental load starts.</span></span>|  
|<span data-ttu-id="729d1-167">5</span><span class="sxs-lookup"><span data-stu-id="729d1-167">5</span></span>|<span data-ttu-id="729d1-168">Указывает на то, что достигнуто значение TimeoutCeiling.</span><span class="sxs-lookup"><span data-stu-id="729d1-168">Indicates that the TimeoutCeiling has been reached.</span></span><br /><br /> <span data-ttu-id="729d1-169">Цикл произвел проверку на наличие данных указанное число раз, а данные все еще недоступны.</span><span class="sxs-lookup"><span data-stu-id="729d1-169">The loop has tested for data the specified number of times, and data is still not available.</span></span> <span data-ttu-id="729d1-170">Если не выполнять эту или аналогичную ей проверку, пакет может выполняться неограниченно долго.</span><span class="sxs-lookup"><span data-stu-id="729d1-170">Without this test or a similar test, the package might run indefinitely.</span></span>|<span data-ttu-id="729d1-171">Выполнение продолжает дополнительный компонент, который регистрирует истечение времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="729d1-171">Execution continues with the optional component that logs the timeout.</span></span>|  
  
#### <a name="to-configure-an-execute-sql-task-to-query-whether-change-data-is-ready"></a><span data-ttu-id="729d1-172">Настройка задачи «Выполнение SQL» для запроса готовности измененных данных</span><span class="sxs-lookup"><span data-stu-id="729d1-172">To configure an Execute SQL task to query whether change data is ready</span></span>  
  
1.  <span data-ttu-id="729d1-173">В пределах контейнера «цикл по элементам» добавьте задачу «Выполнение SQL».</span><span class="sxs-lookup"><span data-stu-id="729d1-173">Inside the For Loop container, add an Execute SQL task.</span></span>  
  
2.  <span data-ttu-id="729d1-174">В окне **Редактор задачи «Выполнение SQL»** на странице **Общие** выберите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="729d1-174">In the **Execute SQL Task Editor**, on the **General** page, select the following options:</span></span>  
  
    1.  <span data-ttu-id="729d1-175">Для параметра **ResultSet**выберите значение **Одна строка**.</span><span class="sxs-lookup"><span data-stu-id="729d1-175">For **ResultSet**, select **Single row**.</span></span>  
  
    2.  <span data-ttu-id="729d1-176">Настройте допустимое соединение с базой данных-источником.</span><span class="sxs-lookup"><span data-stu-id="729d1-176">Configure a valid connection to the source database.</span></span>  
  
    3.  <span data-ttu-id="729d1-177">Для параметра **SQLSourceType**выберите значение **Прямой ввод**.</span><span class="sxs-lookup"><span data-stu-id="729d1-177">For **SQLSourceType**, select **Direct input**.</span></span>  
  
    4.  <span data-ttu-id="729d1-178">В поле **SQLStatement**введите приведенную ниже инструкцию SQL:</span><span class="sxs-lookup"><span data-stu-id="729d1-178">For **SQLStatement**, enter the following SQL statement:</span></span>  
  
        ```  
        declare @DataReady int, @TimeoutCount int  
  
        if not exists (select tran_end_time from cdc.lsn_time_mapping  
                where tran_end_time > ?  )  
            select @DataReady = 0  
        else  
            if ? = 0  
                select @DataReady = 3   
        else  
            if not exists (select tran_end_time from cdc.lsn_time_mapping  
                    where tran_end_time <= ? )  
                select @DataReady = 1   
        else  
            select @DataReady = 2  
  
        select @TimeoutCount = ?  
        if (@DataReady = 0)  
            select @TimeoutCount = @TimeoutCount + 1  
        else  
            select @TimeoutCount = 0  
  
        if (@TimeoutCount > ?)  
            select @DataReady = 5  
  
        select @DataReady as DataReady, @TimeoutCount as TimeoutCount  
  
        ```  
  
3.  <span data-ttu-id="729d1-179">На странице **Сопоставление параметров** средства **Редактор задачи «Выполнение SQL»** произведите следующие сопоставления.</span><span class="sxs-lookup"><span data-stu-id="729d1-179">On the **Parameter Mapping** page of the **Execute SQL Task Editor**, make the following mappings:</span></span>  
  
    1.  <span data-ttu-id="729d1-180">Сопоставьте переменную ExtractEndTime с параметром 0.</span><span class="sxs-lookup"><span data-stu-id="729d1-180">Map the ExtractEndTime variable to parameter 0.</span></span>  
  
    2.  <span data-ttu-id="729d1-181">Сопоставьте переменную IntervalID с параметром 1.</span><span class="sxs-lookup"><span data-stu-id="729d1-181">Map the IntervalID variable to parameter 1.</span></span>  
  
    3.  <span data-ttu-id="729d1-182">Сопоставьте переменную ExtractStartTime с параметром 2.</span><span class="sxs-lookup"><span data-stu-id="729d1-182">Map the ExtractStartTime variable to parameter 2.</span></span>  
  
    4.  <span data-ttu-id="729d1-183">Сопоставьте переменную TimeoutCount с параметром 3.</span><span class="sxs-lookup"><span data-stu-id="729d1-183">Map the TimeoutCount variable to parameter 3.</span></span>  
  
    5.  <span data-ttu-id="729d1-184">Сопоставьте переменную TimeoutCeiling с параметром 4.</span><span class="sxs-lookup"><span data-stu-id="729d1-184">Map the TimeoutCeiling variable to parameter 4.</span></span>  
  
4.  <span data-ttu-id="729d1-185">На странице **Результирующий набор** средства **Редактор задачи «Выполнение SQL»** сопоставьте результат DataReady с переменной DataReady и результат TimeoutCount с переменной TimeoutCount.</span><span class="sxs-lookup"><span data-stu-id="729d1-185">On the **Result Set** page of the **Execute SQL Task Editor**, map the DataReady result to the DataReady variable, and the TimeoutCount result to the TimeoutCount variable.</span></span>  
  
## <a name="waiting-until-the-change-data-is-ready"></a><span data-ttu-id="729d1-186">Ожидание готовности измененных данных</span><span class="sxs-lookup"><span data-stu-id="729d1-186">Waiting Until the Change Data Is Ready</span></span>  
 <span data-ttu-id="729d1-187">Если измененные данные не готовы, можно использовать один из нескольких методов реализации задержки.</span><span class="sxs-lookup"><span data-stu-id="729d1-187">You can use one of several methods to implement a delay when the change data is not ready.</span></span> <span data-ttu-id="729d1-188">Две следующие процедуры показывают, как реализуется задержка с помощью задачи «Скрипт» или задачи «Выполнение SQL».</span><span class="sxs-lookup"><span data-stu-id="729d1-188">The following two procedures illustrate how to use a Script task or an Execute SQL task to implement the delay.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="729d1-189">Выполнение предварительно скомпилированных скриптов требует меньше ресурсов, чем использование задачи «Выполнение SQL».</span><span class="sxs-lookup"><span data-stu-id="729d1-189">A precompiled script incurs less overhead than an Execute SQL task.</span></span>  
  
#### <a name="to-implement-a-delay-by-using-a-script-task"></a><span data-ttu-id="729d1-190">Реализация задержки с помощью задачи «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="729d1-190">To implement a delay by using a Script task</span></span>  
  
1.  <span data-ttu-id="729d1-191">В пределах контейнера «цикл по элементам» добавьте задачу «Скрипт».</span><span class="sxs-lookup"><span data-stu-id="729d1-191">Inside the For Loop container, add a Script task.</span></span>  
  
2.  <span data-ttu-id="729d1-192">Соедините задачу «Выполнение SQL», которая запрашивает готовность системы отслеживания измененных данных, с новой задачей «Скрипт».</span><span class="sxs-lookup"><span data-stu-id="729d1-192">Connect the Execute SQL task that queries to determine whether the change data is ready to the new Script task.</span></span>  
  
3.  <span data-ttu-id="729d1-193">Для управления очередностью, соединяющего задачу «Выполнение SQL» с задачей «Скрипт», откройте **Редактор управления очередностью** и выберите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="729d1-193">For the precedence constraint that connects the Execute SQL task to the Script task, open the **Precedence Constraint Editor** and select the following options:</span></span>  
  
    1.  <span data-ttu-id="729d1-194">В списке **Вычислительная операция**выберите пункт **Выражение и ограничение**.</span><span class="sxs-lookup"><span data-stu-id="729d1-194">For **Evaluation operation**, select **Expression and Constraint**.</span></span>  
  
    2.  <span data-ttu-id="729d1-195">Для параметра **Значение**выберите значение **Успех**.</span><span class="sxs-lookup"><span data-stu-id="729d1-195">For **Value**, select **Success**.</span></span>  
  
         <span data-ttu-id="729d1-196">Ограничение по значению **Успех** относится к успешности выполнения предыдущей задачи.</span><span class="sxs-lookup"><span data-stu-id="729d1-196">The constraint value of **Success** refers to the success of the previous task.</span></span> <span data-ttu-id="729d1-197">В этом случае это означает успешное выполнение задачи «Выполнение SQL».</span><span class="sxs-lookup"><span data-stu-id="729d1-197">In this case, the success of the Execute SQL task.</span></span>  
  
    3.  <span data-ttu-id="729d1-198">В поле **Выражение**введите `@DataReady == 0 && @TimeoutCount <= @TimeoutCeiling`.</span><span class="sxs-lookup"><span data-stu-id="729d1-198">For **Expression**, enter `@DataReady == 0 && @TimeoutCount <= @TimeoutCeiling`.</span></span>  
  
    4.  <span data-ttu-id="729d1-199">Установите флажок **Логическое И. Все аргументы должны иметь значение True**, если он еще не выбран.</span><span class="sxs-lookup"><span data-stu-id="729d1-199">Select **Logical AND. All constraints must evaluate to True**, if not already selected.</span></span>  
  
4.  <span data-ttu-id="729d1-200">В средстве **Редактор задачи «Скрипт»** на странице **Скрипт** для свойства **ReadOnlyVariables**выберите из списка целочисленную переменную **User::DelaySeconds** .</span><span class="sxs-lookup"><span data-stu-id="729d1-200">In the **Script Task Editor**, on the **Script** page, for **ReadOnlyVariables**, select the **User::DelaySeconds** integer variable from the list.</span></span>  
  
5.  <span data-ttu-id="729d1-201">В окне **Редактор задачи «Скрипт»** на странице **Скрипт** нажмите кнопку **Изменить скрипт** , чтобы открыть среду разработки скриптов.</span><span class="sxs-lookup"><span data-stu-id="729d1-201">In the **Script Task Editor**, on the **Script** page, click **Edit Script** to open the script development environment.</span></span>  
  
6.  <span data-ttu-id="729d1-202">В главной процедуре введите одну из следующих строк кода.</span><span class="sxs-lookup"><span data-stu-id="729d1-202">In the Main procedure, enter one of the following lines of code:</span></span>  
  
    -   <span data-ttu-id="729d1-203">При программировании на языке C# введите следующую строку кода:</span><span class="sxs-lookup"><span data-stu-id="729d1-203">If you are programming in C#, enter the following line of code:</span></span>  
  
        ```  
        System.Threading.Thread.Sleep((int)Dts.Variables["DelaySeconds"].Value * 1000);  
        ```  
  
         <span data-ttu-id="729d1-204">\- или -</span><span class="sxs-lookup"><span data-stu-id="729d1-204">\- or -</span></span>  
  
    -   <span data-ttu-id="729d1-205">При программировании на языке [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)], введите следующую строку кода:</span><span class="sxs-lookup"><span data-stu-id="729d1-205">If you are programming in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)], enter the following line of code:</span></span>  
  
        ```  
        System.Threading.Thread.Sleep(Ctype(Dts.Variables("DelaySeconds").Value, Integer) * 1000)  
  
        ```  
  
        > [!NOTE]  
        >  <span data-ttu-id="729d1-206">Метод `Thread.Sleep` ожидает аргумент, указанный в миллисекундах.</span><span class="sxs-lookup"><span data-stu-id="729d1-206">The `Thread.Sleep` method expects an argument that is specified in milliseconds.</span></span>  
  
7.  <span data-ttu-id="729d1-207">Оставьте без изменений создаваемую по умолчанию строку кода, которая возвращает `DtsExecResult.Success` в результате выполнения скрипта.</span><span class="sxs-lookup"><span data-stu-id="729d1-207">Leave the default line of code which returns `DtsExecResult.Success` from the execution of the script.</span></span>  
  
8.  <span data-ttu-id="729d1-208">Закройте среду разработки скриптов и **Редактор задачи «Скрипт»** .</span><span class="sxs-lookup"><span data-stu-id="729d1-208">Close the script development environment and the **Script Task Editor**.</span></span>  
  
#### <a name="to-implement-a-delay-by-using-an-execute-sql-task"></a><span data-ttu-id="729d1-209">Реализация задержки с помощью задачи «Выполнение SQL»</span><span class="sxs-lookup"><span data-stu-id="729d1-209">To implement a delay by using an Execute SQL task</span></span>  
  
1.  <span data-ttu-id="729d1-210">В пределах контейнера «цикл по элементам» добавьте задачу «Выполнение SQL».</span><span class="sxs-lookup"><span data-stu-id="729d1-210">Inside the For Loop container, add an Execute SQL task.</span></span>  
  
2.  <span data-ttu-id="729d1-211">Соедините задачу «Выполнение SQL», которая направляет запросы для выявления готовности измененных данных, с новой задачей «Выполнение SQL».</span><span class="sxs-lookup"><span data-stu-id="729d1-211">Connect the Execute SQL task that queries to determine whether the change data is ready to the new Execute SQL task.</span></span>  
  
3.  <span data-ttu-id="729d1-212">Для управления очередностью, которое соединяет две задачи «Выполнение SQL», откройте средство **Редактор управления очередностью** и выберите следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="729d1-212">For the precedence constraint that connects the two Execute SQL tasks, open the **Precedence Constraint Editor** and select the following options:</span></span>  
  
    1.  <span data-ttu-id="729d1-213">В списке **Вычислительная операция**выберите пункт **Выражение и ограничение**.</span><span class="sxs-lookup"><span data-stu-id="729d1-213">For **Evaluation operation**, select **Expression and Constraint**.</span></span>  
  
    2.  <span data-ttu-id="729d1-214">Для параметра **Значение**выберите значение **Успех**.</span><span class="sxs-lookup"><span data-stu-id="729d1-214">For **Value**, select **Success**.</span></span>  
  
         <span data-ttu-id="729d1-215">Ограничение по значению **Успешно** указывает на успешное завершение предшествующей задачи «Выполнение SQL».</span><span class="sxs-lookup"><span data-stu-id="729d1-215">The constraint value of **Success** refers to the success of the previous Execute SQL task.</span></span>  
  
    3.  <span data-ttu-id="729d1-216">В поле **Выражение**введите `@DataReady == 0`.</span><span class="sxs-lookup"><span data-stu-id="729d1-216">For **Expression**, enter `@DataReady == 0`.</span></span>  
  
    4.  <span data-ttu-id="729d1-217">Установите флажок **Логическое И. Все аргументы должны иметь значение True**, если он еще не выбран.</span><span class="sxs-lookup"><span data-stu-id="729d1-217">Select **Logical AND. All constraints must evaluate to True**, if not already selected.</span></span>  
  
         <span data-ttu-id="729d1-218">При выборе этого варианта оба условия (ограничение и выражение) должны иметь значение true.</span><span class="sxs-lookup"><span data-stu-id="729d1-218">This selection requires that both conditions, the constraint and the expression, must be true.</span></span>  
  
4.  <span data-ttu-id="729d1-219">В окне **Редактор задачи «Выполнение SQL»** на странице **Общие** выберите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="729d1-219">In the **Execute SQL Task Editor**, on the **General** page, select the following options:</span></span>  
  
    1.  <span data-ttu-id="729d1-220">Для параметра **ResultSet**выберите значение **Одна строка**.</span><span class="sxs-lookup"><span data-stu-id="729d1-220">For **ResultSet**, select **Single row**.</span></span>  
  
    2.  <span data-ttu-id="729d1-221">Настройте допустимое соединение с базой данных-источником.</span><span class="sxs-lookup"><span data-stu-id="729d1-221">Configure a valid connection to the source database.</span></span>  
  
    3.  <span data-ttu-id="729d1-222">Для параметра **SQLSourceType**выберите значение **Прямой ввод**.</span><span class="sxs-lookup"><span data-stu-id="729d1-222">For **SQLSourceType**, select **Direct input**.</span></span>  
  
    4.  <span data-ttu-id="729d1-223">В поле **SQLStatement**введите приведенную ниже инструкцию SQL:</span><span class="sxs-lookup"><span data-stu-id="729d1-223">For **SQLStatement**, enter the following SQL statement:</span></span>  
  
        ```  
        WAITFOR DELAY ?  
  
        ```  
  
5.  <span data-ttu-id="729d1-224">На странице **Сопоставление параметров** редактора сопоставьте строковую переменную DelaySeconds с параметром 0.</span><span class="sxs-lookup"><span data-stu-id="729d1-224">On the **Parameter Mapping** page of the editor, map the DelaySeconds string variable to parameter 0.</span></span>  
  
## <a name="handling-an-error-condition"></a><span data-ttu-id="729d1-225">Обработка ошибки</span><span class="sxs-lookup"><span data-stu-id="729d1-225">Handling an Error Condition</span></span>  
 <span data-ttu-id="729d1-226">При необходимости можно настроить внутри цикла дополнительный компонент для регистрации ошибок или превышении времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="729d1-226">You can optionally configure an additional component inside the loop to log an error or a timeout condition:</span></span>  
  
-   <span data-ttu-id="729d1-227">Этот компонент может регистрировать ошибку, если значение переменной DataReady = 1.</span><span class="sxs-lookup"><span data-stu-id="729d1-227">This component can log an error condition when the value of the DataReady variable = 1.</span></span> <span data-ttu-id="729d1-228">Это значение указывает на то, что измененных данных за период до начала выбранного интервала нет.</span><span class="sxs-lookup"><span data-stu-id="729d1-228">This value indicates that there is no available change data before the start of the selected interval.</span></span>  
  
-   <span data-ttu-id="729d1-229">Данный компонент может также регистрировать превышение времени ожидания по достижении указанного значения переменной TimeoutCeiling.</span><span class="sxs-lookup"><span data-stu-id="729d1-229">This component can also log a timeout condition when the value of the TimeoutCeiling variable is reached.</span></span> <span data-ttu-id="729d1-230">Это значение указывает на то, что цикл выполнил проверку на наличие данных указанное число раз, но данные все еще недоступны.</span><span class="sxs-lookup"><span data-stu-id="729d1-230">This value indicates the loop has tested for data the specified number of times, and data is still not available.</span></span> <span data-ttu-id="729d1-231">Если не выполнять эту или аналогичную ей проверку, пакет может выполняться неограниченно долго.</span><span class="sxs-lookup"><span data-stu-id="729d1-231">Without this test or a similar test, the package might run indefinitely.</span></span>  
  
#### <a name="to-configure-an-optional-script-task-to-log-an-error-condition"></a><span data-ttu-id="729d1-232">Настройка дополнительной задачи «Скрипт» для регистрации ошибки</span><span class="sxs-lookup"><span data-stu-id="729d1-232">To configure an optional Script task to log an error condition</span></span>  
  
1.  <span data-ttu-id="729d1-233">Если необходимо создать отчет об ошибке или превышении времени ожидания, записав сообщение в журнал, настройте ведение журнала для пакета.</span><span class="sxs-lookup"><span data-stu-id="729d1-233">If you want to report the error or timeout by writing a message to the log, configure logging for the package.</span></span> <span data-ttu-id="729d1-234">Дополнительные сведения см. в разделе [Включение средств ведения журналов в SQL Server Data Tools](../enable-package-logging-in-sql-server-data-tools.md).</span><span class="sxs-lookup"><span data-stu-id="729d1-234">For more information, see [Enable Package Logging in SQL Server Data Tools](../enable-package-logging-in-sql-server-data-tools.md).</span></span>  
  
2.  <span data-ttu-id="729d1-235">В пределах контейнера «цикл по элементам» добавьте задачу «Скрипт».</span><span class="sxs-lookup"><span data-stu-id="729d1-235">Inside the For Loop container, add a Script task.</span></span>  
  
3.  <span data-ttu-id="729d1-236">Соедините задачу «Выполнение SQL», которая запрашивает готовность системы отслеживания измененных данных, с новой задачей «Скрипт».</span><span class="sxs-lookup"><span data-stu-id="729d1-236">Connect the Execute SQL task that queries to determine whether the change data is ready to the new Script task.</span></span>  
  
4.  <span data-ttu-id="729d1-237">Для управления очередностью, соединяющего задачу «Выполнение SQL» с задачей «Скрипт», откройте **Редактор управления очередностью** и выберите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="729d1-237">For the precedence constraint that connects the Execute SQL task to the Script task, open the **Precedence Constraint Editor** and select the following options:</span></span>  
  
    1.  <span data-ttu-id="729d1-238">В списке **Вычислительная операция**выберите пункт **Выражение и ограничение**.</span><span class="sxs-lookup"><span data-stu-id="729d1-238">For **Evaluation operation**, select **Expression and Constraint**.</span></span>  
  
    2.  <span data-ttu-id="729d1-239">Для параметра **Значение**выберите значение **Успех**.</span><span class="sxs-lookup"><span data-stu-id="729d1-239">For **Value**, select **Success**.</span></span>  
  
         <span data-ttu-id="729d1-240">Ограничение по значению **Успех** относится к успешности выполнения предыдущей задачи.</span><span class="sxs-lookup"><span data-stu-id="729d1-240">The constraint value of **Success** refers to the success of the previous task.</span></span> <span data-ttu-id="729d1-241">В этом случае это означает успешное выполнение задачи «Выполнение SQL».</span><span class="sxs-lookup"><span data-stu-id="729d1-241">In this case, the success of the Execute SQL task.</span></span>  
  
    3.  <span data-ttu-id="729d1-242">В поле **Выражение**введите `@DataReady == 1 || @DataReady == 5`.</span><span class="sxs-lookup"><span data-stu-id="729d1-242">For **Expression**, enter `@DataReady == 1 || @DataReady == 5`.</span></span>  
  
    4.  <span data-ttu-id="729d1-243">Установите флажок **Логическое И. Все аргументы должны иметь значение True**, если он еще не выбран.</span><span class="sxs-lookup"><span data-stu-id="729d1-243">Select **Logical AND. All constraints must evaluate to True**, if not already selected.</span></span>  
  
         <span data-ttu-id="729d1-244">При выборе этого варианта оба условия (ограничение и выражение) должны иметь значение true.</span><span class="sxs-lookup"><span data-stu-id="729d1-244">This selection requires that both conditions, the constraint and the expression, must be true.</span></span>  
  
5.  <span data-ttu-id="729d1-245">В средстве **Редактор задачи «Скрипт»** на странице **Скрипт** для свойства **ReadOnlyVariables**выберите из списка параметры **User::DataReady** и **User::ExtractStartTime** , чтобы их значения были доступны для скрипта.</span><span class="sxs-lookup"><span data-stu-id="729d1-245">In the **Script Task Editor**, on the **Script** page of the editor, for **ReadOnlyVariables**, select **User::DataReady** and **User::ExtractStartTime** from the list to make their values available to the script.</span></span>  
  
     <span data-ttu-id="729d1-246">Если необходимо включить в записываемые в журнал сведения данные из определенных системных переменных (например, System::PackageName), выберите и эти переменные.</span><span class="sxs-lookup"><span data-stu-id="729d1-246">If you want to include information from certain system variables (for example, System::PackageName) in the information that you write to the log, select those variables also.</span></span>  
  
6.  <span data-ttu-id="729d1-247">В окне **Редактор задачи «Скрипт»** на странице **Скрипт** нажмите кнопку **Изменить скрипт** , чтобы открыть среду разработки скриптов.</span><span class="sxs-lookup"><span data-stu-id="729d1-247">In the **Script Task Editor**, on the **Script** page, click **Edit Script** to open the script development environment.</span></span>  
  
7.  <span data-ttu-id="729d1-248">В главную процедуру добавьте код для регистрации ошибки путем вызова метода `Dts.Log` или создайте событие, путем вызова одного из методов интерфейса `Dts.Events`.</span><span class="sxs-lookup"><span data-stu-id="729d1-248">In the Main procedure, enter code to log an error by calling the `Dts.Log` method, or to raise an event by calling one of the methods of the `Dts.Events` interface.</span></span> <span data-ttu-id="729d1-249">Информируйте пакет об ошибке, вернув `Dts.TaskResult = Dts.Results.Failure`.</span><span class="sxs-lookup"><span data-stu-id="729d1-249">Inform the package of the error by returning `Dts.TaskResult = Dts.Results.Failure`.</span></span>  
  
     <span data-ttu-id="729d1-250">Следующий образец показывает, как записать сообщение в журнал.</span><span class="sxs-lookup"><span data-stu-id="729d1-250">The following sample shows how to write a message to the log.</span></span> <span data-ttu-id="729d1-251">Дополнительные сведения см. в разделах [Logging in the Script Task](../extending-packages-scripting/task/logging-in-the-script-task.md), [Raising Events in the Script Task](../extending-packages-scripting/task/raising-events-in-the-script-task.md)и [Returning Results from the Script Task](../extending-packages-scripting/task/returning-results-from-the-script-task.md).</span><span class="sxs-lookup"><span data-stu-id="729d1-251">For more information, see [Logging in the Script Task](../extending-packages-scripting/task/logging-in-the-script-task.md), [Raising Events in the Script Task](../extending-packages-scripting/task/raising-events-in-the-script-task.md), and [Returning Results from the Script Task](../extending-packages-scripting/task/returning-results-from-the-script-task.md).</span></span>  
  
    ```  
    ' User variables.  
    Dim dataReady As Integer = _  
      CType(Dts.Variables("DataReady").Value, Integer)  
    Dim extractStartTime As Date = _  
      CType(Dts.Variables("ExtractStartTime").Value, DateTime)  
  
    ' System variables.  
    Dim packageName As String = _  
      Dts.Variables("PackageName").Value.ToString()  
    Dim executionStartTime As Date = _  
      CType(Dts.Variables("StartTime").Value, DateTime)  
  
    Dim eventMessage As New System.Text.StringBuilder()  
  
    If dataReady = 1 OrElse dataReady = 5 Then  
  
      If dataReady = 1 Then  
        eventMessage.AppendLine("Start Time Error")  
      Else  
        eventMessage.AppendLine("Timeout Error")  
      End If  
  
      With eventMessage  
        .Append("The package ")  
        .Append(packageName)  
        .Append(" started at ")  
        .Append(executionStartTime.ToString())  
        .Append(" and ended at ")  
        .AppendLine(DateTime.Now().ToString())  
        If dataReady = 1 Then  
          .Append("The specified ExtractStartTime was ")  
          .AppendLine(extractStartTime.ToString())  
        End If  
      End With  
  
      System.Windows.Forms.MessageBox.Show(eventMessage.ToString())  
  
      Dts.Log(eventMessage.ToString(), 0, Nothing)  
  
      Dts.TaskResult = Dts.Results.Failure  
  
    Else  
  
      Dts.TaskResult = Dts.Results.Success  
  
    End If  
  
    ```  
  
8.  <span data-ttu-id="729d1-252">Закройте среду разработки скриптов и **Редактор задачи «Скрипт»** .</span><span class="sxs-lookup"><span data-stu-id="729d1-252">Close the script development environment and the **Script Task Editor**.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="729d1-253">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="729d1-253">Next Step</span></span>  
 <span data-ttu-id="729d1-254">Убедившись, что информация об изменениях готова, выполните следующий шаг — подготовьте запрос для получения измененных данных.</span><span class="sxs-lookup"><span data-stu-id="729d1-254">After you determine that change data is ready, the next step is to prepare to query for the change data.</span></span>  
  
 <span data-ttu-id="729d1-255">**Следующая статья:** [Подготовка к запросу информации об изменениях данных](prepare-to-query-for-the-change-data.md)</span><span class="sxs-lookup"><span data-stu-id="729d1-255">**Next topic:** [Prepare to Query for the Change Data](prepare-to-query-for-the-change-data.md)</span></span>  
  
  
