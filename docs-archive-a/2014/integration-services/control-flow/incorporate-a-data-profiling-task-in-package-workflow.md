---
title: Включение задачи "Профилирование данных" в рабочий процесс пакета | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Data Profiling task [Integration Services], using output in workflow
ms.assetid: 39a51586-6977-4c45-b80b-0157a54ad510
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cd3544586ac99f66b961f7961e4f4af4d9e4a4c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658343"
---
# <a name="incorporate-a-data-profiling-task-in-package-workflow"></a><span data-ttu-id="254a4-102">Включение задачи «Профилирование данных» в рабочий процесс пакета</span><span class="sxs-lookup"><span data-stu-id="254a4-102">Incorporate a Data Profiling Task in Package Workflow</span></span>
  <span data-ttu-id="254a4-103">Профилирование и очистка данных на ранних стадиях не подходят для автоматизации.</span><span class="sxs-lookup"><span data-stu-id="254a4-103">Data profiling and cleanup are not candidates for an automated process in their early stages.</span></span> <span data-ttu-id="254a4-104">В службах [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] выходные данные задачи профилирования данных обычно требуют визуального анализа и вмешательства человека, чтобы определить, являются ли зафиксированные нарушения реальными.</span><span class="sxs-lookup"><span data-stu-id="254a4-104">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], the output of the Data Profiling task usually requires visual analysis and human judgment to determine whether reported violations are meaningful or excessive.</span></span> <span data-ttu-id="254a4-105">Для очистки данных, даже после обнаружения проблем с их качеством, нужен хорошо продуманный план.</span><span class="sxs-lookup"><span data-stu-id="254a4-105">Even after recognizing data quality problems, there still has to be a carefully thought-out plan that addresses the best approach for cleanup.</span></span>  
  
 <span data-ttu-id="254a4-106">Однако после выработки критериев качества данных можно автоматизировать регулярный анализ и очистку источника данных.</span><span class="sxs-lookup"><span data-stu-id="254a4-106">However, after criteria for data quality have been established, you might want to automate a periodic analysis and cleanup of the data source.</span></span> <span data-ttu-id="254a4-107">Рассмотрим следующие ситуации.</span><span class="sxs-lookup"><span data-stu-id="254a4-107">Consider these scenarios:</span></span>  
  
-   <span data-ttu-id="254a4-108">**Проверка качества данных перед добавочной загрузкой**.</span><span class="sxs-lookup"><span data-stu-id="254a4-108">**Checking data quality before an incremental load**.</span></span> <span data-ttu-id="254a4-109">Используйте задачу «Профилирование данных» для вычисления профиля соотношения значений NULL в столбцах новых данных, предназначенных для столбца CustomerName в таблице Customers.</span><span class="sxs-lookup"><span data-stu-id="254a4-109">Use the Data Profiling task to compute the Column Null Ratio Profile of new data intended for the CustomerName column in a Customers table.</span></span> <span data-ttu-id="254a4-110">Если процент значений NULL превышает 20%, необходимо отправить оператору сообщение электронной почты с профилем выходных данных и завершить работу пакета.</span><span class="sxs-lookup"><span data-stu-id="254a4-110">If the percentage of null values is greater than 20%, send an e-mail message that contains the profile output to the operator and end the package.</span></span> <span data-ttu-id="254a4-111">В противном случае можно продолжить добавочную загрузку.</span><span class="sxs-lookup"><span data-stu-id="254a4-111">Otherwise, continue the incremental load.</span></span>  
  
-   <span data-ttu-id="254a4-112">**Автоматизация очистки данных при выполнении определенных условий**.</span><span class="sxs-lookup"><span data-stu-id="254a4-112">**Automating cleanup when the specified conditions are met**.</span></span> <span data-ttu-id="254a4-113">Используйте задачу «Профилирование данных» для вычисления профиля включения значений столбца «Штат» из уточняющей таблицы штатов и почтового индекса из уточняющей таблицы почтовых индексов.</span><span class="sxs-lookup"><span data-stu-id="254a4-113">Use the Data Profiling task to compute the Value Inclusion Profile of the State column against a lookup table of states, and of the ZIP Code/Postal Code column against a lookup table of zip codes.</span></span> <span data-ttu-id="254a4-114">Если интенсивность включения значений штата менее 80%, но интенсивность включения значений почтового индекса превышает 99%, это означает две вещи.</span><span class="sxs-lookup"><span data-stu-id="254a4-114">If the inclusion strength of the state values is less than 80%, but the inclusion strength of the ZIP Code/Postal Code values is greater than 99%, this indicates two things.</span></span> <span data-ttu-id="254a4-115">Во-первых, качество данных со штатами плохое.</span><span class="sxs-lookup"><span data-stu-id="254a4-115">First, the state data is bad.</span></span> <span data-ttu-id="254a4-116">Во-вторых, качество данных с почтовыми индексами хорошее.</span><span class="sxs-lookup"><span data-stu-id="254a4-116">Second, the ZIP Code/Postal Code data is good.</span></span> <span data-ttu-id="254a4-117">Запустите задачу потока данных для очистки данных со штатами, которая выполнит уточняющий запрос, определяющий правильное значение штата по почтовому индексу.</span><span class="sxs-lookup"><span data-stu-id="254a4-117">Launch a Data Flow task that cleans up the state data by performing a lookup of the correct state value from the current Zip Code/Postal Code value.</span></span>  
  
 <span data-ttu-id="254a4-118">После создания рабочего процесса, в который можно интегрировать задачу потока данных, станут понятны шаги, которые необходимо для этого выполнить.</span><span class="sxs-lookup"><span data-stu-id="254a4-118">After you have a workflow into which you can incorporate the Data Flow task, you have to understand the steps that are required to add this task.</span></span> <span data-ttu-id="254a4-119">В следующем разделе описывается общий процесс интеграции задачи потока данных.</span><span class="sxs-lookup"><span data-stu-id="254a4-119">The next section describes the general process of incorporating the Data Flow task.</span></span> <span data-ttu-id="254a4-120">В двух последних разделах описывается подключение задачи потока данных непосредственно к источнику данных или к преобразованным данным из потока данных.</span><span class="sxs-lookup"><span data-stu-id="254a4-120">The final two sections describe how to connect the Data Flow task either directly to a data source or to transformed data from the Data Flow.</span></span>  
  
## <a name="defining-a-general-workflow-for-the-data-flow-task"></a><span data-ttu-id="254a4-121">Определение основного рабочего процесса для задачи потока данных</span><span class="sxs-lookup"><span data-stu-id="254a4-121">Defining a General Workflow for the Data Flow Task</span></span>  
 <span data-ttu-id="254a4-122">Далее описывается общий случай использования выхода задачи профилирования данных в рабочем процессе пакета.</span><span class="sxs-lookup"><span data-stu-id="254a4-122">The following procedure outlines the general approach for using the output of the Data Profiling task in the workflow of a package.</span></span>  
  
#### <a name="to-use-the-output-of-the-data-profiling-task-programmatically-in-a-package"></a><span data-ttu-id="254a4-123">Программное использование выхода задачи профилирования данных в пакете</span><span class="sxs-lookup"><span data-stu-id="254a4-123">To use the output of the Data Profiling task programmatically in a package</span></span>  
  
1.  <span data-ttu-id="254a4-124">Добавьте в пакет и настройте задачу «Профилирование данных».</span><span class="sxs-lookup"><span data-stu-id="254a4-124">Add and configure the Data Profiling task in a package.</span></span>  
  
2.  <span data-ttu-id="254a4-125">Настройте переменные пакета, указав в них значения, которые нужно получить из результатов профиля.</span><span class="sxs-lookup"><span data-stu-id="254a4-125">Configure package variables to hold the values that you want to retrieve from the profile results.</span></span>  
  
3.  <span data-ttu-id="254a4-126">Добавьте и настройте задачу «Скрипт».</span><span class="sxs-lookup"><span data-stu-id="254a4-126">Add and configure a Script task.</span></span> <span data-ttu-id="254a4-127">Соедините задачу «Скрипт» с задачей «Профилирование данных».</span><span class="sxs-lookup"><span data-stu-id="254a4-127">Connect the Script task to the Data Profiling task.</span></span> <span data-ttu-id="254a4-128">В задаче «Скрипт» напишите программный код, считывающий нужные значения из выходного файла задачи «Профилирование данных» и присваивающий значения переменным пакета.</span><span class="sxs-lookup"><span data-stu-id="254a4-128">In the Script task, write code that reads the desired values from the output file of the Data Profiling task and populates the package variables.</span></span>  
  
4.  <span data-ttu-id="254a4-129">В объектах управления очередностью, соединяющих задачу «Скрипт» с нисходящими компонентами в рабочем процессе, напишите выражения направления рабочего процесса, использующие значения переменных.</span><span class="sxs-lookup"><span data-stu-id="254a4-129">In the precedence constraints that connect the Script task to downstream branches in the workflow, write expressions that use the values of the variables to direct the workflow.</span></span>  
  
 <span data-ttu-id="254a4-130">При интеграции задачи «Профилирование данных» в рабочем процессе пакета нужно помнить о следующих двух характеристиках задачи.</span><span class="sxs-lookup"><span data-stu-id="254a4-130">When incorporating the Data Profiling task into the workflow of a package, keep these two features of the task in mind:</span></span>  
  
-   <span data-ttu-id="254a4-131">**Выходные данные задачи**.</span><span class="sxs-lookup"><span data-stu-id="254a4-131">**Task output**.</span></span> <span data-ttu-id="254a4-132">Задача «Профилирование данных» выводит информацию в файл или переменную пакета в формате XML в соответствии со схемой DataProfile.xsd.</span><span class="sxs-lookup"><span data-stu-id="254a4-132">The Data Profiling task writes its output to a file or a package variable in XML format according to the DataProfile.xsd schema.</span></span> <span data-ttu-id="254a4-133">Поэтому, если результаты профиля нужно использовать в логике рабочего процесса пакета, необходимо создать запросы к выходным данным в формате XML.</span><span class="sxs-lookup"><span data-stu-id="254a4-133">Therefore, you have to query the XML output if you want to use the profile results in the conditional workflow of a package.</span></span> <span data-ttu-id="254a4-134">Для этого удобно воспользоваться языком запросов Xpath.</span><span class="sxs-lookup"><span data-stu-id="254a4-134">You can easily use the Xpath query language to query this XML output.</span></span> <span data-ttu-id="254a4-135">Для изучения структуры выхода в формате XML можно открыть образец выходного файла или саму схему.</span><span class="sxs-lookup"><span data-stu-id="254a4-135">To study the structure of this XML output, you can open a sample output file or the schema itself.</span></span> <span data-ttu-id="254a4-136">Открыть выходной файл или схему можно в среде [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], другом редакторе XML или в текстовом редакторе (например, в Блокноте).</span><span class="sxs-lookup"><span data-stu-id="254a4-136">To open the output file or schema, you can use [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], another XML editor, or a text editor, such as Notepad.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="254a4-137">Некоторые результаты профиля, отображаемые в средстве просмотра профиля данных, являются вычисляемыми значениями, которые нельзя найти в выходных данных.</span><span class="sxs-lookup"><span data-stu-id="254a4-137">Some of the profile results that are displayed in the Data Profile Viewer are calculated values that are not directly found in the output.</span></span> <span data-ttu-id="254a4-138">Например, выход профиля соотношения значений NULL в столбцах содержит общее количество строк и количество строк, содержащих значения NULL.</span><span class="sxs-lookup"><span data-stu-id="254a4-138">For example, the output of the Column Null Ratio Profile contains the total number of rows and the number of rows that contain null values.</span></span> <span data-ttu-id="254a4-139">Чтобы получить соотношение значений NULL в столбцах, нужно запросить эти два значения, а затем вычислить процент строк, содержащих значения NULL.</span><span class="sxs-lookup"><span data-stu-id="254a4-139">You have to query these two values, and then calculate the percentage of rows that contain null values, to obtain the column null ratio.</span></span>  
  
-   <span data-ttu-id="254a4-140">**Входные данные задачи**.</span><span class="sxs-lookup"><span data-stu-id="254a4-140">**Task input**.</span></span> <span data-ttu-id="254a4-141">Задача «Профилирование данных» считывает свои входные данные из таблиц [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="254a4-141">The Data Profiling task reads its input from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables.</span></span> <span data-ttu-id="254a4-142">Поэтому, если нужно профилировать данные, уже загруженные и преобразованные в поток данных, то данные, хранящиеся в памяти, нужно сохранить в промежуточных таблицах.</span><span class="sxs-lookup"><span data-stu-id="254a4-142">Therefore, you have to save data that is in memory to staging tables if you want to profile data that has already been loaded and transformed in the data flow.</span></span>  
  
 <span data-ttu-id="254a4-143">В следующих разделах описывается применение этого обобщенного рабочего процесса к профильным данным, поступающим непосредственно из внешнего источника данных или в преобразованном виде от задачи потока данных.</span><span class="sxs-lookup"><span data-stu-id="254a4-143">The following sections apply this general workflow to profiling data that comes directly from an external data source or that comes transformed from the Data Flow task.</span></span> <span data-ttu-id="254a4-144">В этих разделах также демонстрируются требования к обработке входных и выходных данных задачи потока данных.</span><span class="sxs-lookup"><span data-stu-id="254a4-144">These sections also show how to handle the input and output requirements of the Data Flow task.</span></span>  
  
## <a name="connecting-the-data-profiling-task-directly-to-an-external-data-source"></a><span data-ttu-id="254a4-145">Соединение задачи «Профилирование данных» непосредственно с внешним источником данных</span><span class="sxs-lookup"><span data-stu-id="254a4-145">Connecting the Data Profiling Task Directly to an External Data Source</span></span>  
 <span data-ttu-id="254a4-146">Задача «Профилирование данных» может профилировать данные, поступающие непосредственно из внешнего источника данных.</span><span class="sxs-lookup"><span data-stu-id="254a4-146">The Data Profiling task can profile data that comes directly from a data source.</span></span>  <span data-ttu-id="254a4-147">Следующий пример иллюстрирует эту возможность. Задача «Профилирование данных»  применяется для вычисления профиля соотношения значений NULL в столбцах таблицы Person.Address базы данных [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="254a4-147">To illustrate this capability, the following example uses the Data Profiling task to compute a Column Null Ratio Profile on the columns of the Person.Address table in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="254a4-148">Затем в примере используется задача «Скрипт» для получения результатов из выходного файла и присвоения значений переменным пакета, которые можно использовать для управления рабочим процессом.</span><span class="sxs-lookup"><span data-stu-id="254a4-148">Then, this example uses a Script task to retrieve the results from the output file and populate package variables that can be used to direct workflow.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="254a4-149">Для этого простого примера был выбран столбец AddressLine2, поскольку он содержит высокий процент значений NULL.</span><span class="sxs-lookup"><span data-stu-id="254a4-149">The AddressLine2 column was selected for this simple example because this column contains a high percentage of null values.</span></span>  
  
 <span data-ttu-id="254a4-150">Пример состоит из следующих шагов:</span><span class="sxs-lookup"><span data-stu-id="254a4-150">This example consists of the following steps:</span></span>  
  
-   <span data-ttu-id="254a4-151">настройка диспетчеров соединений для подключения к внешнему источнику данных и выходному файлу, в который будут помещены результаты профилирования;</span><span class="sxs-lookup"><span data-stu-id="254a4-151">Configuring the connection managers that connect to the external data source and to the output file that will contain the profile results.</span></span>  
  
-   <span data-ttu-id="254a4-152">настройка переменных пакета, в которых будут храниться значения, необходимые задаче профилирования данных;</span><span class="sxs-lookup"><span data-stu-id="254a4-152">Configuring the package variables that will hold the values needed by the Data Profiling task.</span></span>  
  
-   <span data-ttu-id="254a4-153">настройка задачи «Профилирование данных» для вычисления профиля соотношения значений NULL в столбце;</span><span class="sxs-lookup"><span data-stu-id="254a4-153">Configuring the Data Profiling task to compute the Column Null Ratio Profile.</span></span>  
  
-   <span data-ttu-id="254a4-154">настройка задачи «Скрипт» для работы с выходными данными задачи «Профилирование данных» в формате XML;</span><span class="sxs-lookup"><span data-stu-id="254a4-154">Configuring the Script task to work the XML output from the Data Profiling task.</span></span>  
  
-   <span data-ttu-id="254a4-155">настройка элементов управления очередностью, определяющих выбор компонентов нисходящего рабочего процесса на основании результатов задачи «Профилирование данных».</span><span class="sxs-lookup"><span data-stu-id="254a4-155">Configuring the precedence constraints that will control which downstream branches in the workflow are run based on the results of the Data Profiling task.</span></span>  
  
### <a name="configure-the-connection-managers"></a><span data-ttu-id="254a4-156">Настройка диспетчеров соединений</span><span class="sxs-lookup"><span data-stu-id="254a4-156">Configure the Connection Managers</span></span>  
 <span data-ttu-id="254a4-157">В этом примере используется два диспетчера соединений:</span><span class="sxs-lookup"><span data-stu-id="254a4-157">For this example, there are two connection managers:</span></span>  
  
-   <span data-ttu-id="254a4-158">диспетчер соединений [!INCLUDE[vstecado](../../includes/vstecado-md.md)] , который подключается к исходной базе данных [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] ;</span><span class="sxs-lookup"><span data-stu-id="254a4-158">An [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager that connects to the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] database.</span></span>  
  
-   <span data-ttu-id="254a4-159">диспетчер соединения файлов, создающий выходной файл для хранения результатов задачи «Профилирование данных».</span><span class="sxs-lookup"><span data-stu-id="254a4-159">A File connection manager that creates the output file that will hold the results of the Data Profiling task.</span></span>  
  
##### <a name="to-configure-the-connection-managers"></a><span data-ttu-id="254a4-160">Настройка диспетчеров соединений</span><span class="sxs-lookup"><span data-stu-id="254a4-160">To configure the connection managers</span></span>  
  
1.  <span data-ttu-id="254a4-161">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]создайте новый пакет служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="254a4-161">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], create a new [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package.</span></span>  
  
2.  <span data-ttu-id="254a4-162">Добавьте к пакету диспетчер соединений [!INCLUDE[vstecado](../../includes/vstecado-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="254a4-162">Add an [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager to the package.</span></span> <span data-ttu-id="254a4-163">Настройте этот диспетчер подключений для использования поставщика данных .NET для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) и для соединения с доступным экземпляром базы данных [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="254a4-163">Configure this connection manager to use the NET Data Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) and to connect to an available instance of the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] database.</span></span>  
  
     <span data-ttu-id="254a4-164">По умолчанию диспетчеру подключений присваивается следующее имя: \<server name>.AdventureWorks1.</span><span class="sxs-lookup"><span data-stu-id="254a4-164">By default, the connection manager has the following name: \<server name>.AdventureWorks1.</span></span>  
  
3.  <span data-ttu-id="254a4-165">Добавьте к пакету диспетчер соединения файлов.</span><span class="sxs-lookup"><span data-stu-id="254a4-165">Add a File connection manager to the package.</span></span> <span data-ttu-id="254a4-166">Настройте этот диспетчер соединений, чтобы он создавал выходной файл для задачи «Профилирование данных».</span><span class="sxs-lookup"><span data-stu-id="254a4-166">Configure this connection manager to create the output file for the Data Profiling task.</span></span>  
  
     <span data-ttu-id="254a4-167">В этом примере используется файл с именем DataProfile1.xml.</span><span class="sxs-lookup"><span data-stu-id="254a4-167">This example uses the file name, DataProfile1.xml.</span></span> <span data-ttu-id="254a4-168">По умолчанию имя диспетчера соединений совпадает с именем файла.</span><span class="sxs-lookup"><span data-stu-id="254a4-168">By default, the connection manager has the same name as the file.</span></span>  
  
### <a name="configure-the-package-variables"></a><span data-ttu-id="254a4-169">Настройка переменных пакета</span><span class="sxs-lookup"><span data-stu-id="254a4-169">Configure the Package Variables</span></span>  
 <span data-ttu-id="254a4-170">В этом примере используются две переменные пакета:</span><span class="sxs-lookup"><span data-stu-id="254a4-170">This example uses two package variables:</span></span>  
  
-   <span data-ttu-id="254a4-171">переменная ProfileConnectionName передает имя диспетчера соединения файлов задаче «Скрипт»;</span><span class="sxs-lookup"><span data-stu-id="254a4-171">The ProfileConnectionName variable passes the name of the File connection manager to the Script task.</span></span>  
  
-   <span data-ttu-id="254a4-172">переменная AddressLine2NullRatio передает вычисленное соотношение значений NULL в столбце из задачи «Скрипт» в пакет.</span><span class="sxs-lookup"><span data-stu-id="254a4-172">The AddressLine2NullRatio variable passes the calculated null ratio for this column out of the Script task to the package.</span></span>  
  
##### <a name="to-configure-the-package-variables-that-will-hold-profile-results"></a><span data-ttu-id="254a4-173">Настройка переменных пакета, в которых будут содержаться результаты профилирования</span><span class="sxs-lookup"><span data-stu-id="254a4-173">To configure the package variables that will hold profile results</span></span>  
  
-   <span data-ttu-id="254a4-174">В окне **Переменные** создайте и настройте следующие две переменные пакета.</span><span class="sxs-lookup"><span data-stu-id="254a4-174">In the **Variables** window, add and configure the following two package variables:</span></span>  
  
    -   <span data-ttu-id="254a4-175">Введите имя `ProfileConnectionName` для одной из переменных и задайте для этой переменной тип **String**.</span><span class="sxs-lookup"><span data-stu-id="254a4-175">Enter the name, `ProfileConnectionName`, for one of the variables and set the type of this variable to **String**.</span></span>  
  
    -   <span data-ttu-id="254a4-176">Введите имя `AddressLine2NullRatio` для другой переменной и задайте для этой переменной тип **Double**.</span><span class="sxs-lookup"><span data-stu-id="254a4-176">Enter the name, `AddressLine2NullRatio`, for the other variable and set the type of this variable to **Double**.</span></span>  
  
### <a name="configure-the-data-profiling-task"></a><span data-ttu-id="254a4-177">Настройка задачи «Профилирование данных»</span><span class="sxs-lookup"><span data-stu-id="254a4-177">Configure the Data Profiling Task</span></span>  
 <span data-ttu-id="254a4-178">Задачу «Профилирование данных» нужно настроить следующим образом:</span><span class="sxs-lookup"><span data-stu-id="254a4-178">The Data Profiling task has to be configured in the following way:</span></span>  
  
-   <span data-ttu-id="254a4-179">для использования данных, которые диспетчер соединений [!INCLUDE[vstecado](../../includes/vstecado-md.md)] поставляет в качестве входных;</span><span class="sxs-lookup"><span data-stu-id="254a4-179">To use the data that the [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager supplies as input.</span></span>  
  
-   <span data-ttu-id="254a4-180">для вычисления профиля соотношения значений NULL на входных данных;</span><span class="sxs-lookup"><span data-stu-id="254a4-180">To perform a Column Null Ratio profile on the input data.</span></span>  
  
-   <span data-ttu-id="254a4-181">для сохранения результатов профилирования в файле, связанном с диспетчером соединения файла.</span><span class="sxs-lookup"><span data-stu-id="254a4-181">To save the profile results to the file that is associated with the File connection manager.</span></span>  
  
##### <a name="to-configure-the-data-profiling-task"></a><span data-ttu-id="254a4-182">Настройка задачи «Профилирование данных»</span><span class="sxs-lookup"><span data-stu-id="254a4-182">To configure the Data Profiling task</span></span>  
  
1.  <span data-ttu-id="254a4-183">На вкладке «Поток управления» добавьте задачу «Профилирование данных».</span><span class="sxs-lookup"><span data-stu-id="254a4-183">To the Control Flow, add a Data Profiling task.</span></span>  
  
2.  <span data-ttu-id="254a4-184">Для настройки задачи откройте **Редактор задачи «Профилирование данных»** .</span><span class="sxs-lookup"><span data-stu-id="254a4-184">Open the **Data Profiling Task Editor** to configure the task.</span></span>  
  
3.  <span data-ttu-id="254a4-185">На странице **Общие** редактора в поле **Назначение**выберите имя предварительно настроенного диспетчера соединения файлов.</span><span class="sxs-lookup"><span data-stu-id="254a4-185">On the **General** page of the editor, for **Destination**, select the name of the File connection manager that you have previously configured.</span></span>  
  
4.  <span data-ttu-id="254a4-186">На странице редактора **Запросы профиля** создайте новый профиль «Соотношение значений NULL в столбце».</span><span class="sxs-lookup"><span data-stu-id="254a4-186">On the **Profile Requests** page of the editor, create a new Column Null Ratio Profile.</span></span>  
  
5.  <span data-ttu-id="254a4-187">На панели **Свойства запроса** выберите в качестве значения параметра **ConnectionManager**предварительно настроенный диспетчер соединений [!INCLUDE[vstecado](../../includes/vstecado-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="254a4-187">In the **Request properties** pane, for **ConnectionManager**, select the [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager that you have previously configured.</span></span> <span data-ttu-id="254a4-188">Затем в поле **TableOrView**выберите Person.Address.</span><span class="sxs-lookup"><span data-stu-id="254a4-188">Then, for **TableOrView**, select Person.Address.</span></span>  
  
6.  <span data-ttu-id="254a4-189">Закройте редактор задачи «Профилирование данных».</span><span class="sxs-lookup"><span data-stu-id="254a4-189">Close the Data Profiling Task Editor.</span></span>  
  
### <a name="configure-the-script-task"></a><span data-ttu-id="254a4-190">Настройка задачи «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="254a4-190">Configure the Script Task</span></span>  
 <span data-ttu-id="254a4-191">Задачу «Скрипт» нужно настроить таким образом, чтобы она получала результаты из выходного файла и присваивала их значения предварительно созданным переменным пакета.</span><span class="sxs-lookup"><span data-stu-id="254a4-191">The Script task has to be configured to retrieve the results from the output file and populate the package variables that were previously configured.</span></span>  
  
##### <a name="to-configure-the-script-task"></a><span data-ttu-id="254a4-192">Настройка задачи «Скрипт»</span><span class="sxs-lookup"><span data-stu-id="254a4-192">To configure the Script task</span></span>  
  
1.  <span data-ttu-id="254a4-193">На вкладке «Поток управления» добавьте задачу «Скрипт».</span><span class="sxs-lookup"><span data-stu-id="254a4-193">To the Control Flow, add a Script task.</span></span>  
  
2.  <span data-ttu-id="254a4-194">Соедините задачу «Скрипт» с задачей «Профилирование данных».</span><span class="sxs-lookup"><span data-stu-id="254a4-194">Connect the Script task to the Data Profiling task.</span></span>  
  
3.  <span data-ttu-id="254a4-195">Для настройки задачи откройте **Редактор задачи «Скрипт»** .</span><span class="sxs-lookup"><span data-stu-id="254a4-195">Open the **Script Task Editor** to configure the task.</span></span>  
  
4.  <span data-ttu-id="254a4-196">На странице **Скрипт** выберите нужный язык программирования.</span><span class="sxs-lookup"><span data-stu-id="254a4-196">On the **Script** page, select your preferred programming language.</span></span> <span data-ttu-id="254a4-197">Затем сделайте две переменных пакета доступными для скрипта.</span><span class="sxs-lookup"><span data-stu-id="254a4-197">Then, make the two package variables available to the script:</span></span>  
  
    1.  <span data-ttu-id="254a4-198">Для `ReadOnlyVariables` выберите `ProfileConnectionName` .</span><span class="sxs-lookup"><span data-stu-id="254a4-198">For `ReadOnlyVariables`, select `ProfileConnectionName`.</span></span>  
  
    2.  <span data-ttu-id="254a4-199">Для **ReadWriteVariables**выберите `AddressLine2NullRatio` .</span><span class="sxs-lookup"><span data-stu-id="254a4-199">For **ReadWriteVariables**, select `AddressLine2NullRatio`.</span></span>  
  
5.  <span data-ttu-id="254a4-200">Выберите **Изменить скрипт** , чтобы открыть среду разработки скрипта.</span><span class="sxs-lookup"><span data-stu-id="254a4-200">Select **Edit Script** to open the script development environment.</span></span>  
  
6.  <span data-ttu-id="254a4-201">Добавьте ссылку на пространство имен System.Xml.</span><span class="sxs-lookup"><span data-stu-id="254a4-201">Add a reference to the System.Xml namespace.</span></span>  
  
7.  <span data-ttu-id="254a4-202">Введите образец кода, соответствующий выбранному языку программирования.</span><span class="sxs-lookup"><span data-stu-id="254a4-202">Enter the sample code that corresponds to your programming language:</span></span>  
  
    ```vb  
    Imports System  
    Imports Microsoft.SqlServer.Dts.Runtime  
    Imports System.Xml  
  
    Public Class ScriptMain  
  
      Private FILENAME As String = "C:\ TEMP\DataProfile1.xml"  
      Private PROFILE_NAMESPACE_URI As String = "https://schemas.microsoft.com/DataDebugger/"  
      Private NULLCOUNT_XPATH As String = _  
        "/default:DataProfile/default:DataProfileOutput/default:Profiles" & _  
        "/default:ColumnNullRatioProfile[default:Column[@Name='AddressLine2']]/default:NullCount/text()"  
      Private TABLE_XPATH As String = _  
        "/default:DataProfile/default:DataProfileOutput/default:Profiles" & _  
        "/default:ColumnNullRatioProfile[default:Column[@Name='AddressLine2']]/default:Table"  
  
      Public Sub Main()  
  
        Dim profileConnectionName As String  
        Dim profilePath As String  
        Dim profileOutput As New XmlDocument  
        Dim profileNSM As XmlNamespaceManager  
        Dim nullCountNode As XmlNode  
        Dim nullCount As Integer  
        Dim tableNode As XmlNode  
        Dim rowCount As Integer  
        Dim nullRatio As Double  
  
        ' Open output file.  
        profileConnectionName = Dts.Variables("ProfileConnectionName").Value.ToString()  
        profilePath = Dts.Connections(profileConnectionName).ConnectionString  
        profileOutput.Load(profilePath)  
        profileNSM = New XmlNamespaceManager(profileOutput.NameTable)  
        profileNSM.AddNamespace("default", PROFILE_NAMESPACE_URI)  
  
        ' Get null count for column.  
        nullCountNode = profileOutput.SelectSingleNode(NULLCOUNT_XPATH, profileNSM)  
        nullCount = CType(nullCountNode.Value, Integer)  
  
        ' Get row count for table.  
        tableNode = profileOutput.SelectSingleNode(TABLE_XPATH, profileNSM)  
        rowCount = CType(tableNode.Attributes("RowCount").Value, Integer)  
  
        ' Compute and return null ratio.  
        nullRatio = nullCount / rowCount  
        Dts.Variables("AddressLine2NullRatio").Value = nullRatio  
  
        Dts.TaskResult = Dts.Results.Success  
  
      End Sub  
  
    End Class  
    ```  
  
    ```csharp  
    using System;  
    using Microsoft.SqlServer.Dts.Runtime;  
    using System.Xml;  
  
    public class ScriptMain  
    {  
  
      private string FILENAME = "C:\\ TEMP\\DataProfile1.xml";  
      private string PROFILE_NAMESPACE_URI = "https://schemas.microsoft.com/DataDebugger/";  
      private string NULLCOUNT_XPATH = "/default:DataProfile/default:DataProfileOutput/default:Profiles" + "/default:ColumnNullRatioProfile[default:Column[@Name='AddressLine2']]/default:NullCount/text()";  
      private string TABLE_XPATH = "/default:DataProfile/default:DataProfileOutput/default:Profiles" + "/default:ColumnNullRatioProfile[default:Column[@Name='AddressLine2']]/default:Table";  
  
      public void Main()  
      {  
  
        string profileConnectionName;  
        string profilePath;  
        XmlDocument profileOutput = new XmlDocument();  
        XmlNamespaceManager profileNSM;  
        XmlNode nullCountNode;  
        int nullCount;  
        XmlNode tableNode;  
        int rowCount;  
        double nullRatio;  
  
        // Open output file.  
        profileConnectionName = Dts.Variables["ProfileConnectionName"].Value.ToString();  
        profilePath = Dts.Connections[profileConnectionName].ConnectionString;  
        profileOutput.Load(profilePath);  
        profileNSM = new XmlNamespaceManager(profileOutput.NameTable);  
        profileNSM.AddNamespace("default", PROFILE_NAMESPACE_URI);  
  
        // Get null count for column.  
        nullCountNode = profileOutput.SelectSingleNode(NULLCOUNT_XPATH, profileNSM);  
        nullCount = (int)nullCountNode.Value;  
  
        // Get row count for table.  
        tableNode = profileOutput.SelectSingleNode(TABLE_XPATH, profileNSM);  
        rowCount = (int)tableNode.Attributes["RowCount"].Value;  
  
        // Compute and return null ratio.  
        nullRatio = nullCount / rowCount;  
        Dts.Variables["AddressLine2NullRatio"].Value = nullRatio;  
  
        Dts.TaskResult = Dts.Results.Success;  
  
      }  
  
    }  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="254a4-203">Образец кода, использованный в данной процедуре, демонстрирует загрузку выхода задачи «Профилирование данных» из файла.</span><span class="sxs-lookup"><span data-stu-id="254a4-203">The sample code shown in this procedure demonstrates how to load the output of the Data Profiling task from a file.</span></span> <span data-ttu-id="254a4-204">Чтобы вместо этого загрузить выход задачи «Профилирование данных» из пакетной переменной, ознакомьтесь с альтернативным образцом программного кода, расположенным после этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="254a4-204">To load the output of the Data Profiling task from a package variable instead, see the alternative sample code that follows this procedure.</span></span>  
  
8.  <span data-ttu-id="254a4-205">Закройте среду разработки скриптов и редактор задачи «Скрипт».</span><span class="sxs-lookup"><span data-stu-id="254a4-205">Close the script development environment, and then close the Script Task Editor.</span></span>  
  
#### <a name="alternative-code-reading-the-profile-output-from-a-variable"></a><span data-ttu-id="254a4-206">Альтернативный образец программного кода — чтение выхода задачи профилирования из переменной</span><span class="sxs-lookup"><span data-stu-id="254a4-206">Alternative Code-Reading the Profile Output from a Variable</span></span>  
 <span data-ttu-id="254a4-207">В предыдущей процедуре описана загрузка выходных данных задачи "Профилирование данных" из файла.</span><span class="sxs-lookup"><span data-stu-id="254a4-207">The previous procedure shows how to load the output of the Data Profiling task from a file.</span></span> <span data-ttu-id="254a4-208">Другой вариант — загрузить эти выходные данные из переменной пакета.</span><span class="sxs-lookup"><span data-stu-id="254a4-208">However, an alternative method would be to load this output from a package variable.</span></span> <span data-ttu-id="254a4-209">Чтобы загрузить эти выходные данные из переменной пакета, нужно внести в образец кода следующие изменения.</span><span class="sxs-lookup"><span data-stu-id="254a4-209">To load the output from a variable, you have to make the following changes to the sample code:</span></span>  
  
-   <span data-ttu-id="254a4-210">Вызовите метод `LoadXml` класса `XmlDocument` вместо метода `Load`.</span><span class="sxs-lookup"><span data-stu-id="254a4-210">Call the `LoadXml` method of the `XmlDocument` class instead of the `Load` method.</span></span>  
  
-   <span data-ttu-id="254a4-211">В редакторе задачи «Скрипт» добавьте имя переменной пакета, содержащей выход профиля, в список `ReadOnlyVariables` задачи.</span><span class="sxs-lookup"><span data-stu-id="254a4-211">In the Script Task Editor, add the name of the package variable that contains the profile output to the task's `ReadOnlyVariables` list.</span></span>  
  
-   <span data-ttu-id="254a4-212">Передайте строковое значение переменной методу `LoadXML`, как показано в следующем образце программного кода.</span><span class="sxs-lookup"><span data-stu-id="254a4-212">Pass the string value of the variable to the `LoadXML` method, as shown in the following code example.</span></span> <span data-ttu-id="254a4-213">(В данном примере в качестве имени переменной пакета, содержащей выход задачи профилирования, используется «ProfileOutput».)</span><span class="sxs-lookup"><span data-stu-id="254a4-213">(This example uses "ProfileOutput" as the name of the package variable that contains the profile output.)</span></span>  
  
    ```vb  
    Dim outputString As String  
    outputString = Dts.Variables("ProfileOutput").Value.ToString()  
    ...  
    profileOutput.LoadXml(outputString)  
    ```  
  
    ```csharp  
    string outputString;  
    outputString = Dts.Variables["ProfileOutput"].Value.ToString();  
    ...  
    profileOutput.LoadXml(outputString);  
    ```  
  
### <a name="configure-the-precedence-constraints"></a><span data-ttu-id="254a4-214">Настройка элементов управления очередностью</span><span class="sxs-lookup"><span data-stu-id="254a4-214">Configure the Precedence Constraints</span></span>  
 <span data-ttu-id="254a4-215">Необходимо настроить элементы управления очередностью, которые определяют выбор компонентов нисходящего рабочего процесса на основании результатов задачи «Профилирование данных».</span><span class="sxs-lookup"><span data-stu-id="254a4-215">The precedence constraints have to be configured to control which downstream branches in the workflow are run based on the results of the Data Profiling task.</span></span>  
  
##### <a name="to-configure-the-precedence-constraints"></a><span data-ttu-id="254a4-216">Настройка элементов управления очередностью</span><span class="sxs-lookup"><span data-stu-id="254a4-216">To configure the precedence constraints</span></span>  
  
-   <span data-ttu-id="254a4-217">В объектах управления очередностью, соединяющих задачу «Скрипт» с нисходящими компонентами в рабочем процессе, напишите выражения направления рабочего процесса, использующие значения переменных.</span><span class="sxs-lookup"><span data-stu-id="254a4-217">In the precedence constraints that connect the Script task to downstream branches in the workflow, write expressions that use the values of the variables to direct the workflow.</span></span>  
  
     <span data-ttu-id="254a4-218">Например, можно задать для параметра **Вычислительная операция** управления очередностью значение **Выражение и ограничение**.</span><span class="sxs-lookup"><span data-stu-id="254a4-218">For example, you might set the **Evaluation operation** of the precedence constraint to **Expression and Constraint**.</span></span> <span data-ttu-id="254a4-219">Затем можно использовать `@AddressLine2NullRatio < .90` в качестве значения этого выражения.</span><span class="sxs-lookup"><span data-stu-id="254a4-219">Then, you might use `@AddressLine2NullRatio < .90` as the value of the expression.</span></span> <span data-ttu-id="254a4-220">Тогда рабочий процесс выберет этот путь, если предыдущие задачи завершатся успешно, а также в случае если процент значений NULL в выбранном столбце меньше 90%.</span><span class="sxs-lookup"><span data-stu-id="254a4-220">This causes the workflow to follow the selected path when the previous tasks succeed, and when the percentage of null values in the selected column is less than 90%.</span></span>  
  
## <a name="connecting-the-data-profiling-task-to-transformed-data-from-the-data-flow"></a><span data-ttu-id="254a4-221">Соединение задачи «Профилирование данных» с преобразованными данными из потока данных</span><span class="sxs-lookup"><span data-stu-id="254a4-221">Connecting the Data Profiling Task to Transformed Data from the Data Flow</span></span>  
 <span data-ttu-id="254a4-222">Можно профилировать данные, поступающие не непосредственно из источника данных, а уже загруженные и преобразованные в потоке данных.</span><span class="sxs-lookup"><span data-stu-id="254a4-222">Instead of profiling data directly from a data source, you can profile data that has already been loaded and transformed in the data flow.</span></span> <span data-ttu-id="254a4-223">Однако задача «Профилирование данных» работает только с материализованными данными и не работает с данными, находящимися в памяти.</span><span class="sxs-lookup"><span data-stu-id="254a4-223">However, the Data Profiling task works only against persisted data, not against in-memory data.</span></span> <span data-ttu-id="254a4-224">Поэтому вначале нужно использовать целевой компонент, сохраняющий преобразованные данные в промежуточную таблицу.</span><span class="sxs-lookup"><span data-stu-id="254a4-224">Therefore, you must first use a destination component to save the transformed data to a staging table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="254a4-225">При настройке задачи «Профилирование данных» необходимо выбрать существующие таблицы и столбцы.</span><span class="sxs-lookup"><span data-stu-id="254a4-225">When you configure the Data Profiling task, you have to select existing tables and columns.</span></span> <span data-ttu-id="254a4-226">Поэтому промежуточные таблицы нужно создавать на стадии разработки, перед настройкой задачи.</span><span class="sxs-lookup"><span data-stu-id="254a4-226">Therefore, you must create the staging table at design time before you can configure the task.</span></span> <span data-ttu-id="254a4-227">Иными словами, невозможно использовать временную таблицу, создаваемую во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="254a4-227">In other words, this scenario does not allow you to use a temporary table that is created at run time.</span></span>  
  
 <span data-ttu-id="254a4-228">Сохранив данные в промежуточной таблице, можно:</span><span class="sxs-lookup"><span data-stu-id="254a4-228">After saving the data to a staging table, you can do the following actions:</span></span>  
  
-   <span data-ttu-id="254a4-229">использовать задачу «Профилирование данных» для профилирования данных;</span><span class="sxs-lookup"><span data-stu-id="254a4-229">Use the Data Profiling task to profile the data.</span></span>  
  
-   <span data-ttu-id="254a4-230">использовать задачу «Скрипт» для чтения результатов, как описано выше в данном разделе;</span><span class="sxs-lookup"><span data-stu-id="254a4-230">Use a Script task to read the results as described earlier in this topic.</span></span>  
  
-   <span data-ttu-id="254a4-231">использовать полученные результаты для управления последующим рабочим процессом пакета.</span><span class="sxs-lookup"><span data-stu-id="254a4-231">Use those results to direct the subsequent workflow of the package.</span></span>  
  
 <span data-ttu-id="254a4-232">Далее описывается общий случай использования задачи профилирования данных для данных, преобразованных потоком данных.</span><span class="sxs-lookup"><span data-stu-id="254a4-232">The following procedure provides the general approach for using the Data Profiling task to profile data that has been transformed by the data flow.</span></span> <span data-ttu-id="254a4-233">Многие из описываемых здесь шагов похожи на шаги, которые описывались ранее для профилирования данных непосредственно из внешнего источника данных.</span><span class="sxs-lookup"><span data-stu-id="254a4-233">Many of these steps are similar to the ones described earlier for profiling data that comes directly from an external data source.</span></span> <span data-ttu-id="254a4-234">Можно перечитать описание предыдущих шагов для получения дополнительных сведений о настройке различных компонентов.</span><span class="sxs-lookup"><span data-stu-id="254a4-234">You might want to review those earlier steps for more information about how to configure the various components.</span></span>  
  
#### <a name="to-use-the-data-profiling-task-in-the-data-flow"></a><span data-ttu-id="254a4-235">Использование задачи «Профилирование данных» в потоке данных</span><span class="sxs-lookup"><span data-stu-id="254a4-235">To use the Data Profiling task in the data flow</span></span>  
  
1.  <span data-ttu-id="254a4-236">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]создайте новый пакет.</span><span class="sxs-lookup"><span data-stu-id="254a4-236">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], create a package.</span></span>  
  
2.  <span data-ttu-id="254a4-237">На вкладке «Поток данных» добавьте, настройте и подключите соответствующие источники данных и преобразования.</span><span class="sxs-lookup"><span data-stu-id="254a4-237">In the Data Flow, add, configure, and connect the appropriate sources and transformations.</span></span>  
  
3.  <span data-ttu-id="254a4-238">На вкладке «Поток данных» добавьте, настройте и подключите целевой компонент, сохраняющий преобразованные данные в промежуточную таблицу.</span><span class="sxs-lookup"><span data-stu-id="254a4-238">In the Data Flow, add, configure, and connect a destination component that saves the transformed data to a staging table.</span></span>  
  
4.  <span data-ttu-id="254a4-239">На вкладке «Поток управления» добавьте и настройте задачу «Профилирование данных», которая вычисляет нужные профили для преобразованных данных из промежуточной таблицы.</span><span class="sxs-lookup"><span data-stu-id="254a4-239">In the Control Flow, add and configure a Data Profiling task that computes the desired profiles against the transformed data in the staging table.</span></span> <span data-ttu-id="254a4-240">Подключите задачу «Профилирование данных» к задаче потока данных.</span><span class="sxs-lookup"><span data-stu-id="254a4-240">Connect the Data Profiling task to the Data Flow task.</span></span>  
  
5.  <span data-ttu-id="254a4-241">Настройте переменные пакета, указав в них значения, которые нужно получить из результатов профиля.</span><span class="sxs-lookup"><span data-stu-id="254a4-241">Configure package variables to hold the values that you want to retrieve from the profile results.</span></span>  
  
6.  <span data-ttu-id="254a4-242">Добавьте и настройте задачу «Скрипт».</span><span class="sxs-lookup"><span data-stu-id="254a4-242">Add and configure a Script task.</span></span> <span data-ttu-id="254a4-243">Соедините задачу «Скрипт» с задачей «Профилирование данных».</span><span class="sxs-lookup"><span data-stu-id="254a4-243">Connect the Script task to the Data Profiling task.</span></span> <span data-ttu-id="254a4-244">В задаче «Скрипт» напишите программный код, считывающий нужные значения из выходных данных задачи «Профилирование данных» и присваивающий значения переменным пакета.</span><span class="sxs-lookup"><span data-stu-id="254a4-244">In the Script task, write code that reads the desired values from the output of the Data Profiling task and populates the package variables.</span></span>  
  
7.  <span data-ttu-id="254a4-245">В объектах управления очередностью, соединяющих задачу «Скрипт» с нисходящими компонентами в рабочем процессе, напишите выражения направления рабочего процесса, использующие значения переменных.</span><span class="sxs-lookup"><span data-stu-id="254a4-245">In the precedence constraints that connect the Script task to downstream branches in the workflow, write expressions that use the values of the variables to direct the workflow.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="254a4-246">См. также:</span><span class="sxs-lookup"><span data-stu-id="254a4-246">See Also</span></span>  
 <span data-ttu-id="254a4-247">[Установка задачи «Профилирование данных»](data-profiling-task.md) </span><span class="sxs-lookup"><span data-stu-id="254a4-247">[Setup of the Data Profiling Task](data-profiling-task.md) </span></span>  
 [<span data-ttu-id="254a4-248">Средство просмотра профиля данных</span><span class="sxs-lookup"><span data-stu-id="254a4-248">Data Profile Viewer</span></span>](data-profile-viewer.md)  
  
  
