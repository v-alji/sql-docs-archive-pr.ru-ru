---
title: Подготовка к запросу информации об изменениях данных | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],preparing query
ms.assetid: 9ea2db7a-3dca-4bbf-9903-cccd2d494b5f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5ab732389d5a747c596472f14f5229361dd46275
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655299"
---
# <a name="prepare-to-query-for-the-change-data"></a><span data-ttu-id="63e60-102">Подготовка к запросу информации об изменениях</span><span class="sxs-lookup"><span data-stu-id="63e60-102">Prepare to Query for the Change Data</span></span>
  <span data-ttu-id="63e60-103">В потоке управления пакета служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , который выполняет добавочную загрузку измененных данных, третья и последняя задача состоит в том, чтобы подготовить запрос для измененных данных и добавить задачу потока данных.</span><span class="sxs-lookup"><span data-stu-id="63e60-103">In the control flow of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that performs an incremental load of change data, the third and final task is to prepare to query for the change data and add a Data Flow task.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="63e60-104">Вторая задача для потока управления — убедиться, что измененные данные для выбранного интервала готовы.</span><span class="sxs-lookup"><span data-stu-id="63e60-104">The second task for the control flow is to ensure that the change data for the selected interval is ready.</span></span> <span data-ttu-id="63e60-105">Дополнительные сведения об этой задаче см. в разделе [Определение готовности информации об изменениях данных](determine-whether-the-change-data-is-ready.md).</span><span class="sxs-lookup"><span data-stu-id="63e60-105">For more information about this task, see [Determine Whether the Change Data Is Ready](determine-whether-the-change-data-is-ready.md).</span></span> <span data-ttu-id="63e60-106">Описание общего процесса по проектированию потока управления см. в разделе [Система отслеживания измененных данных (SSIS)](change-data-capture-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="63e60-106">For a description of the overall process of designing the control flow, see [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span></span>  
  
## <a name="design-considerations"></a><span data-ttu-id="63e60-107">Вопросы проектирования</span><span class="sxs-lookup"><span data-stu-id="63e60-107">Design Considerations</span></span>  
 <span data-ttu-id="63e60-108">Чтобы получить измененные данные, нужно вызвать возвращающую табличное значение функцию Transact-SQL, которая принимает конечные точки интервала в качестве входных параметров и возвращает измененные данные за указанный период.</span><span class="sxs-lookup"><span data-stu-id="63e60-108">To retrieve the change data, you will call a Transact-SQL table-valued function that accepts the endpoints of the interval as input parameters and returns change data for the specified interval.</span></span> <span data-ttu-id="63e60-109">Эту функцию вызывает исходный компонент в потоке данных.</span><span class="sxs-lookup"><span data-stu-id="63e60-109">A source component in the data flow calls this function.</span></span> <span data-ttu-id="63e60-110">Сведения об этом исходном компоненте см. в разделе [Получение и интерпретация измененных данных](retrieve-and-understand-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="63e60-110">For information about this source component, see [Retrieve and Understand the Change Data](retrieve-and-understand-the-change-data.md).</span></span>  
  
 <span data-ttu-id="63e60-111">Чаще всего используемые исходные компоненты служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , включая источник OLE DB, источник ADO и источник ADO NET, не могут получить сведения о параметрах для функции с табличным значением.</span><span class="sxs-lookup"><span data-stu-id="63e60-111">The most frequently used [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] source components, including the OLE DB source, the ADO source, and the ADO NET source, cannot derive parameter information for a table-valued function.</span></span> <span data-ttu-id="63e60-112">Следовательно, в большинстве своем источники не могут вызывать параметризованные функции напрямую.</span><span class="sxs-lookup"><span data-stu-id="63e60-112">Therefore, most sources cannot call a parameterized function directly.</span></span>  
  
 <span data-ttu-id="63e60-113">Существует два конструкторских решения проблемы передачи входных параметров для такой функции.</span><span class="sxs-lookup"><span data-stu-id="63e60-113">You have two design options for passing the input parameters to the function:</span></span>  
  
-   <span data-ttu-id="63e60-114">**Сборка параметризированного запроса в виде строки**.</span><span class="sxs-lookup"><span data-stu-id="63e60-114">**Assemble the parameterized query as a string**.</span></span> <span data-ttu-id="63e60-115">Чтобы собрать динамическую строку SQL со значениями параметров, жестко запрограммированными в эту строку, можно использовать задачу «Скрипт» или «Выполнение SQL».</span><span class="sxs-lookup"><span data-stu-id="63e60-115">You can use a Script task or an Execute SQL task to assemble a dynamic SQL string with parameter values hard-coded into the string.</span></span> <span data-ttu-id="63e60-116">Затем эту строку можно сохранить в переменной пакета и использовать для задания исходному компоненту свойства SqlCommand.</span><span class="sxs-lookup"><span data-stu-id="63e60-116">Then, you can store this string in a package variable and use it to set the SqlCommand property of a source component.</span></span> <span data-ttu-id="63e60-117">Этот подход приводит к успеху, так как исходный компонент более не требует сведений о параметрах.</span><span class="sxs-lookup"><span data-stu-id="63e60-117">This approach succeeds because the source component no longer requires parameter information.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="63e60-118">Выполнение предварительно скомпилированных скриптов требует меньше ресурсов, чем использование задачи «Выполнение SQL».</span><span class="sxs-lookup"><span data-stu-id="63e60-118">A precompiled script incurs less overhead than an Execute SQL task.</span></span>  
  
-   <span data-ttu-id="63e60-119">**Использование параметризованной оболочки**.</span><span class="sxs-lookup"><span data-stu-id="63e60-119">**Use a parameterized wrapper**.</span></span> <span data-ttu-id="63e60-120">В качестве альтернативы можно создать параметризованную хранимую процедуру как оболочку, которая вызывает параметризованную функцию с табличным значением.</span><span class="sxs-lookup"><span data-stu-id="63e60-120">Alternatively, you can create a parameterized stored procedure as a wrapper that calls the parameterized table-valued function.</span></span> <span data-ttu-id="63e60-121">Этот подход приводит к успеху, так как исходный компонент может успешно получать сведения о параметрах для хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="63e60-121">This approach succeeds because a source component can successfully derive parameter information for a stored procedure.</span></span>  
  
 <span data-ttu-id="63e60-122">В данном разделе используется первое конструкторское решение и создается параметризированный запрос в виде строки.</span><span class="sxs-lookup"><span data-stu-id="63e60-122">This topic uses the first design option and assembles a parameterized query as a string.</span></span>  
  
## <a name="preparing-the-query"></a><span data-ttu-id="63e60-123">Подготовка запроса</span><span class="sxs-lookup"><span data-stu-id="63e60-123">Preparing the Query</span></span>  
 <span data-ttu-id="63e60-124">Чтобы получить возможность объединения входных параметров в единую строку запроса, пользователь должен настроить переменные пакета, необходимые для этого запроса.</span><span class="sxs-lookup"><span data-stu-id="63e60-124">Before you can concatenate the values of the input parameters into a single query string, you have to set up the package variables that the query needs.</span></span>  
  
#### <a name="to-set-up-package-variables"></a><span data-ttu-id="63e60-125">Настройка переменных пакета</span><span class="sxs-lookup"><span data-stu-id="63e60-125">To set up package variables</span></span>  
  
-   <span data-ttu-id="63e60-126">В окне [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]Переменные **среды** создайте переменную со строковым типом данных для хранения строки запроса, возвращенной задачей «Выполнение SQL».</span><span class="sxs-lookup"><span data-stu-id="63e60-126">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in the **Variables** window, create a variable with a string data type to hold the query string returned by the Execute SQL Task.</span></span>  
  
     <span data-ttu-id="63e60-127">В этом примере используется имя переменной SqlDataQuery.</span><span class="sxs-lookup"><span data-stu-id="63e60-127">This example uses the variable name, SqlDataQuery.</span></span>  
  
 <span data-ttu-id="63e60-128">После создания переменной пакета можно объединять значения входных параметров с помощью задачи «Скрипт» или «Выполнение SQL».</span><span class="sxs-lookup"><span data-stu-id="63e60-128">With the package variable created, you can use either a Script task or Execute SQL task to concatenate the values of the input parameters.</span></span> <span data-ttu-id="63e60-129">В следующих двух процедурах описывается настройка этих компонентов.</span><span class="sxs-lookup"><span data-stu-id="63e60-129">The following two procedures describe how to configure these components.</span></span>  
  
#### <a name="to-use-a-script-task-to-concatenate-the-query-string"></a><span data-ttu-id="63e60-130">Использование задачи «Скрипт» для объединения строки запроса</span><span class="sxs-lookup"><span data-stu-id="63e60-130">To use a Script task to concatenate the query string</span></span>  
  
1.  <span data-ttu-id="63e60-131">На вкладке **Поток управления** добавьте к пакету задачу «Скрипт» после контейнера «цикл по элементам» и соедините контейнер с этой задачей.</span><span class="sxs-lookup"><span data-stu-id="63e60-131">On the **Control Flow** tab, add a Script task to the package after the For Loop container and connect the For Loop container to the task.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="63e60-132">Здесь предполагается, что пакет выполняет добавочную загрузку из одной таблицы.</span><span class="sxs-lookup"><span data-stu-id="63e60-132">This procedure assumes that the package performs an incremental load from a single table.</span></span> <span data-ttu-id="63e60-133">Если пакет загружает данные из нескольких таблиц и содержит родительский пакет с несколькими дочерними, то эту задачу следует добавить в качестве первого компонента каждого из дочерних пакетов.</span><span class="sxs-lookup"><span data-stu-id="63e60-133">If the package loads from multiple tables and has a parent package with multiple child packages, this task would be added as the first component to each child package.</span></span> <span data-ttu-id="63e60-134">Дополнительные сведения см. в разделе [Выполнение добавочной загрузки нескольких таблиц](perform-an-incremental-load-of-multiple-tables.md).</span><span class="sxs-lookup"><span data-stu-id="63e60-134">For more information, see [Perform an Incremental Load of Multiple Tables](perform-an-incremental-load-of-multiple-tables.md).</span></span>  
  
2.  <span data-ttu-id="63e60-135">В окне **Редактор задачи «Скрипт»** на странице **Скрипт** выберите следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="63e60-135">In the **Script Task Editor**, on the **Script** page, select the following options:</span></span>  
  
    1.  <span data-ttu-id="63e60-136">Для свойства **ReadOnlyVariables**выберите из списка значения **User::DataReady**, **User::ExtractStartTime**и **User::ExtractEndTime** .</span><span class="sxs-lookup"><span data-stu-id="63e60-136">For **ReadOnlyVariables**, select **User::DataReady**, **User::ExtractStartTime**, and **User::ExtractEndTime** from the.</span></span>  
  
    2.  <span data-ttu-id="63e60-137">Для свойства **ReadWriteVariables**выберите из списка значение User::SqlDataQuery.</span><span class="sxs-lookup"><span data-stu-id="63e60-137">For **ReadWriteVariables**, select User::SqlDataQuery from the list.</span></span>  
  
3.  <span data-ttu-id="63e60-138">В окне **Редактор задачи «Скрипт»** на странице **Скрипт** нажмите кнопку **Изменить скрипт** , чтобы открыть среду разработки скриптов.</span><span class="sxs-lookup"><span data-stu-id="63e60-138">In the **Script Task Editor**, on the **Script** page, click **Edit Script** to open the script development environment.</span></span>  
  
4.  <span data-ttu-id="63e60-139">В главной процедуре введите один из следующих сегментов кода.</span><span class="sxs-lookup"><span data-stu-id="63e60-139">In the Main procedure, enter one of the following code segments:</span></span>  
  
    -   <span data-ttu-id="63e60-140">При программировании на языке C# введите следующие строки кода:</span><span class="sxs-lookup"><span data-stu-id="63e60-140">If you are programming in C#, enter the following lines of code:</span></span>  
  
        ```  
        int dataReady;  
        System.DateTime extractStartTime;  
        System.DateTime extractEndTime;  
        string sqlDataQuery;  
  
        dataReady = (int)Dts.Variables["DataReady"].Value;  
        extractStartTime = (System.DateTime)Dts.Variables["ExtractStartTime"].Value;  
        extractEndTime = (System.DateTime)Dts.Variables["ExtractEndTime"].Value;  
  
        if (dataReady == 2)  
          {  
          sqlDataQuery = "SELECT * FROM CDCSample.uf_Customer('" + string.Format("{0:yyyy-MM-dd hh:mm:ss}", extractStartTime) + "', '" + string.Format("{0:yyyy-MM-dd hh:mm:ss}", extractEndTime) + "')";  
          }  
        else  
          {  
          sqlDataQuery = "SELECT * FROM CDCSample.uf_Customer(null" + ", '" + string.Format("{0:yyyy-MM-dd hh:mm:ss}", extractEndTime) + "')";  
          }  
  
        Dts.Variables["SqlDataQuery"].Value = sqlDataQuery;  
        ```  
  
         <span data-ttu-id="63e60-141">\- или -</span><span class="sxs-lookup"><span data-stu-id="63e60-141">\- or -</span></span>  
  
    -   <span data-ttu-id="63e60-142">При программировании на языке [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)], введите следующие строки кода:</span><span class="sxs-lookup"><span data-stu-id="63e60-142">If you are programming in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)], enter the following lines of code:</span></span>  
  
        ```  
        Dim dataReady As Integer  
        Dim extractStartTime As Date  
        Dim extractEndTime As Date  
        Dim sqlDataQuery As String  
  
        dataReady = CType(Dts.Variables("DataReady").Value, Integer)  
        extractStartTime = CType(Dts.Variables("ExtractStartTime").Value, Date)  
        extractEndTime = CType(Dts.Variables("ExtractEndTime").Value, Date)  
  
        If dataReady = 2 Then  
          sqlDataQuery = "SELECT * FROM CDCSample.uf_Customer('" & _  
              String.Format("{0:yyyy-MM-dd hh:mm:ss}", extractStartTime) & _  
              "', '" & _  
              String.Format("{0:yyyy-MM-dd hh:mm:ss}", extractEndTime) & _  
              "')"  
        Else  
          sqlDataQuery = "SELECT * FROM CDCSample.uf_Customer(null" & _  
              ", '" & _  
              String.Format("{0:yyyy-MM-dd hh:mm:ss}", extractEndTime) & _  
              "')"  
        End If  
  
        Dts.Variables("SqlDataQuery").Value = sqlDataQuery  
  
        ```  
  
5.  <span data-ttu-id="63e60-143">Оставьте без изменений создаваемую по умолчанию строку кода, которая возвращает `DtsExecResult.Success` в результате выполнения скрипта.</span><span class="sxs-lookup"><span data-stu-id="63e60-143">Leave the default line of code which returns `DtsExecResult.Success` from the execution of the script.</span></span>  
  
6.  <span data-ttu-id="63e60-144">Закройте среду разработки скриптов и **Редактор задачи «Скрипт»** .</span><span class="sxs-lookup"><span data-stu-id="63e60-144">Close the script development environment and the **Script Task Editor**.</span></span>  
  
#### <a name="to-use-an-execute-sql-task-to-concatenate-the-query-string"></a><span data-ttu-id="63e60-145">Использование задачи «Выполнение SQL» для объединения строки запроса</span><span class="sxs-lookup"><span data-stu-id="63e60-145">To use an Execute SQL task to concatenate the query string</span></span>  
  
1.  <span data-ttu-id="63e60-146">На вкладке **Поток управления** добавьте к пакету задачу «Выполнение SQL» после контейнера «цикл по элементам» и соедините контейнер с этой задачей.</span><span class="sxs-lookup"><span data-stu-id="63e60-146">On the **Control Flow** tab, add an Execute SQL task to the package after the For Loop container and connect the For Loop container to this task.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="63e60-147">Здесь предполагается, что пакет выполняет добавочную загрузку из одной таблицы.</span><span class="sxs-lookup"><span data-stu-id="63e60-147">This procedure assumes that the package performs an incremental load from a single table.</span></span> <span data-ttu-id="63e60-148">Если пакет загружает данные из нескольких таблиц и содержит родительский пакет с несколькими дочерними, то эту задачу следует добавить в качестве первого компонента каждого из дочерних пакетов.</span><span class="sxs-lookup"><span data-stu-id="63e60-148">If the package loads from multiple tables and has a parent package with multiple child packages, this task would be added as the first component to each child package.</span></span> <span data-ttu-id="63e60-149">Дополнительные сведения см. в разделе [Выполнение добавочной загрузки нескольких таблиц](perform-an-incremental-load-of-multiple-tables.md).</span><span class="sxs-lookup"><span data-stu-id="63e60-149">For more information, see [Perform an Incremental Load of Multiple Tables](perform-an-incremental-load-of-multiple-tables.md).</span></span>  
  
2.  <span data-ttu-id="63e60-150">В окне **Редактор задачи «Выполнение SQL»** на странице **Общие** выберите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="63e60-150">In the **Execute SQL Task Editor**, on the **General** page, select the following options:</span></span>  
  
    1.  <span data-ttu-id="63e60-151">Для параметра **ResultSet**выберите значение **Одна строка**.</span><span class="sxs-lookup"><span data-stu-id="63e60-151">For **ResultSet**, select **Single row**.</span></span>  
  
    2.  <span data-ttu-id="63e60-152">Настройте допустимое соединение с базой данных-источником.</span><span class="sxs-lookup"><span data-stu-id="63e60-152">Configure a valid connection to the source database.</span></span>  
  
    3.  <span data-ttu-id="63e60-153">Для параметра **SQLSourceType**выберите значение **Прямой ввод**.</span><span class="sxs-lookup"><span data-stu-id="63e60-153">For **SQLSourceType**, select **Direct input**.</span></span>  
  
    4.  <span data-ttu-id="63e60-154">В поле **SQLStatement**введите приведенную ниже инструкцию SQL:</span><span class="sxs-lookup"><span data-stu-id="63e60-154">For **SQLStatement**, enter the following SQL statement:</span></span>  
  
        ```  
        declare @ExtractStartTime datetime,  
        @ExtractEndTime datetime,   
        @DataReady int  
  
        select @DataReady = ?,   
        @ExtractStartTime = ?,   
        @ExtractEndTime = ?  
  
        if @DataReady = 2  
        select N'select * from CDCSample.uf_Customer'  
        + N'('''+ convert(nvarchar(30),@ExtractStartTime,120)  
        + ''', '''  
        + convert(nvarchar(30),@ExtractEndTime,120) + ''') '   
        as SqlDataQuery  
        else  
        select N'select * from CDCSample.uf_Customer'  
        + N'(null, '''  
        + convert(nvarchar(30),@ExtractEndTime,120)  
        + ''') '  
        as SqlDataQuery  
  
        ```  
  
        > [!NOTE]  
        >  <span data-ttu-id="63e60-155">Предложение `else` в этом образце формирует запрос на первоначальную загрузку информации об изменениях, передавая значение NULL для даты и времени начала.</span><span class="sxs-lookup"><span data-stu-id="63e60-155">The `else` clause in this sample generates a query for the initial load of change data by passing a null value for the starting date and time.</span></span> <span data-ttu-id="63e60-156">Этот образец не учитывает случай, когда изменения, сделанные до включения системы отслеживания измененных данных, тоже необходимо загрузить в хранилище данных.</span><span class="sxs-lookup"><span data-stu-id="63e60-156">This sample does not address the scenario in which changes that were made before change data capture was enabled also have to be uploaded to the data warehouse.</span></span>  
  
3.  <span data-ttu-id="63e60-157">На странице **Сопоставление параметров** средства **Редактор задачи «Выполнение SQL»** выполните следующее сопоставление.</span><span class="sxs-lookup"><span data-stu-id="63e60-157">On the **Parameter Mapping** page of the **Execute SQL Task Editor**, do the following mapping:</span></span>  
  
    1.  <span data-ttu-id="63e60-158">Сопоставьте переменную DataReady с параметром 0.</span><span class="sxs-lookup"><span data-stu-id="63e60-158">Map the DataReady variable to parameter 0.</span></span>  
  
    2.  <span data-ttu-id="63e60-159">Сопоставьте переменную ExtractStartTime с параметром 1.</span><span class="sxs-lookup"><span data-stu-id="63e60-159">Map the ExtractStartTime variable to parameter 1.</span></span>  
  
    3.  <span data-ttu-id="63e60-160">Сопоставьте переменную ExtractEndTime с параметром 2.</span><span class="sxs-lookup"><span data-stu-id="63e60-160">Map the ExtractEndTime variable to parameter 2.</span></span>  
  
4.  <span data-ttu-id="63e60-161">На странице **Результирующий набор** средства **Редактор задачи «Выполнение SQL»** сопоставьте столбец «Имя результата» с переменной SqlDataQuery.</span><span class="sxs-lookup"><span data-stu-id="63e60-161">On the **Result Set** page of the **Execute SQL Task Editor**, map the Result Name to the SqlDataQuery variable.</span></span>  
  
     <span data-ttu-id="63e60-162">Имя результата — это имя единственного возвращаемого столбца SqlDataQuery.</span><span class="sxs-lookup"><span data-stu-id="63e60-162">The Result Name is the name of the single column that is returned, SqlDataQuery.</span></span>  
  
 <span data-ttu-id="63e60-163">Предшествующие процедуры настраивают задачу, которая готовит строку запроса с жестко запрограммированными строковыми значениями для входных параметров.</span><span class="sxs-lookup"><span data-stu-id="63e60-163">The previous procedures configure a task that prepares a query string with hard-coded string values for the input parameters.</span></span> <span data-ttu-id="63e60-164">Следующий код представляет собой пример такой строки запроса:</span><span class="sxs-lookup"><span data-stu-id="63e60-164">The following code is an example of such a query string:</span></span>  
  
 `select * from CDCSample. uf_Customer('2007-06-11 14:21:58', '2007-06-12 14:21:58')`  
  
## <a name="adding-a-data-flow-task"></a><span data-ttu-id="63e60-165">Добавление задачи потока данных</span><span class="sxs-lookup"><span data-stu-id="63e60-165">Adding a Data Flow Task</span></span>  
 <span data-ttu-id="63e60-166">Последний этап процесса разработки потока управления для пакета — добавление задачи потока данных.</span><span class="sxs-lookup"><span data-stu-id="63e60-166">The last step in designing the control flow for the package is to add a Data Flow task.</span></span>  
  
#### <a name="to-add-a-data-flow-task-and-complete-the-control-flow"></a><span data-ttu-id="63e60-167">Добавление задачи потока данных и завершение формирования потока управления</span><span class="sxs-lookup"><span data-stu-id="63e60-167">To add a Data Flow task and complete the control flow</span></span>  
  
-   <span data-ttu-id="63e60-168">На вкладке **Поток управления** добавьте задачу потока данных и соедините с задачей, которая объединяла строку запроса.</span><span class="sxs-lookup"><span data-stu-id="63e60-168">On the **Control Flow** tab, add a Data Flow task and connect the task that concatenated the query string.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="63e60-169">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="63e60-169">Next Step</span></span>  
 <span data-ttu-id="63e60-170">Завершив подготовку строки запроса и настройку задачи потока данных, приступайте к следующему шагу — созданию функции с табличным значением для получения измененных данных из базы данных.</span><span class="sxs-lookup"><span data-stu-id="63e60-170">After you prepare the query string and configure the Data Flow task, the next step is create the table-valued function that will retrieve the change data from the database.</span></span>  
  
 <span data-ttu-id="63e60-171">**Следующая статья:** [Создание функции для получения информации об изменениях данных](create-the-function-to-retrieve-the-change-data.md)</span><span class="sxs-lookup"><span data-stu-id="63e60-171">**Next topic:** [Create the Function to Retrieve the Change Data](create-the-function-to-retrieve-the-change-data.md)</span></span>  
  
  
