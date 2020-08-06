---
title: Планирование административных задач SSAS с помощью агент SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2d1484b3-51d9-48a0-93d2-0c3e4ed22b87
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2c78fa5fcebc0589ba863163b93ad2d10731b75a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733249"
---
# <a name="schedule-ssas-administrative-tasks-with-sql-server-agent"></a><span data-ttu-id="e3c16-102">Планирование задач администрирования служб SSAS с помощью агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="e3c16-102">Schedule SSAS Administrative Tasks with SQL Server Agent</span></span>
  <span data-ttu-id="e3c16-103">Используя службу агента SQL Server, вы можете запланировать административные задачи [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] в нужном порядке и в нужное время.</span><span class="sxs-lookup"><span data-stu-id="e3c16-103">Using the SQL Server Agent service, you can schedule [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] administrative tasks to run in the order and times that you need.</span></span> <span data-ttu-id="e3c16-104">Планирование задач позволяет автоматизировать процессы, выполняющиеся регулярно или с предсказуемой цикличностью.</span><span class="sxs-lookup"><span data-stu-id="e3c16-104">Scheduled tasks help you automate processes that run on regular or predictable cycles.</span></span> <span data-ttu-id="e3c16-105">Задачи типа обработки кубов могут быть запланированы на периоды низкой деловой активности.</span><span class="sxs-lookup"><span data-stu-id="e3c16-105">You can schedule administrative tasks, such as cube processing, to run during times of slow business activity.</span></span> <span data-ttu-id="e3c16-106">Кроме того, при создании шагов задания агента SQL Server пользователь имеет возможность определить порядок, в котором будут выполняться задачи.</span><span class="sxs-lookup"><span data-stu-id="e3c16-106">You can also determine the order in which tasks run by creating job steps within a SQL Server Agent job.</span></span> <span data-ttu-id="e3c16-107">Например, можно выполнить обработку куба, а затем создать его резервную копию.</span><span class="sxs-lookup"><span data-stu-id="e3c16-107">For example, you can process a cube and then perform a backup of the cube.</span></span>  
  
 <span data-ttu-id="e3c16-108">Шаги задания позволяют управлять потоком выполнения.</span><span class="sxs-lookup"><span data-stu-id="e3c16-108">Job steps give you control over flow of execution.</span></span> <span data-ttu-id="e3c16-109">Агент SQL Server может быть настроен таким образом, чтобы в случае сбоя одного из заданий выполнение оставшихся задач было продолжено или прекращено.</span><span class="sxs-lookup"><span data-stu-id="e3c16-109">If one job fails, you can configure SQL Server Agent to continue to run the remaining tasks or to stop execution.</span></span> <span data-ttu-id="e3c16-110">Вы можете также настроить агент SQL Server на отправку уведомлений о выполнении или сбое выполнения задания.</span><span class="sxs-lookup"><span data-stu-id="e3c16-110">You can also configure SQL Server Agent to send notifications about the success or failure of job execution.</span></span>  
  
 <span data-ttu-id="e3c16-111">Данный раздел является пошаговым руководством, демонстрирующим два способа использования агента SQL Server для запуска скрипта XML для аналитики.</span><span class="sxs-lookup"><span data-stu-id="e3c16-111">This topic is a walkthrough that shows two ways of using SQL Server Agent to run XMLA script.</span></span> <span data-ttu-id="e3c16-112">В первом примере показано, как запланировать обработку одного измерения.</span><span class="sxs-lookup"><span data-stu-id="e3c16-112">The first example demonstrates how to schedule processing of a single dimension.</span></span> <span data-ttu-id="e3c16-113">Второй пример показывает, как объединить задачи обработки в единый скрипт, выполняемый по расписанию.</span><span class="sxs-lookup"><span data-stu-id="e3c16-113">Example two shows how to combine processing tasks into a single script that runs on a schedule.</span></span> <span data-ttu-id="e3c16-114">Для прохождения этого пошагового руководства необходимо выполнить следующие предварительные требования.</span><span class="sxs-lookup"><span data-stu-id="e3c16-114">To complete this walkthrough, you will need to meet the following prerequisites.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e3c16-115">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="e3c16-115">Prerequisites</span></span>  
 <span data-ttu-id="e3c16-116">Должна быть установлена служба агента SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e3c16-116">SQL Server Agent service must be installed.</span></span>  
  
 <span data-ttu-id="e3c16-117">По умолчанию задания запускаются под учетной записью службы.</span><span class="sxs-lookup"><span data-stu-id="e3c16-117">By default, jobs run under the service account.</span></span> <span data-ttu-id="e3c16-118">В [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] учетной записи по умолчанию для агент SQL Server является NT Service\SQLAgent $ \<instancename> .</span><span class="sxs-lookup"><span data-stu-id="e3c16-118">In [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], the default account for SQL Server Agent is NT Service\SQLAgent$\<instancename>.</span></span> <span data-ttu-id="e3c16-119">Для выполнения задачи резервного копирования или обработки эта учетная запись должна принадлежать системному администратору в экземпляре служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="e3c16-119">To perform a backup or processing task, this account must be a system administrator on the Analysis Services instance.</span></span> <span data-ttu-id="e3c16-120">Дополнительные сведения см. в статьях [предоставление разрешений администратора сервера &#40;Analysis Services&#41;](grant-server-admin-rights-to-an-analysis-services-instance.md).</span><span class="sxs-lookup"><span data-stu-id="e3c16-120">For more information, see [Grant Server Administrator Permissions &#40;Analysis Services&#41;](grant-server-admin-rights-to-an-analysis-services-instance.md).</span></span>  
  
 <span data-ttu-id="e3c16-121">Также необходимо наличие тестовой базы данных, с которой будет производиться работа.</span><span class="sxs-lookup"><span data-stu-id="e3c16-121">You should also have a test database to work with.</span></span> <span data-ttu-id="e3c16-122">Для использования в данном пошаговом руководстве вы можете развернуть образец многомерной базы данных AdventureWorks или проект из учебника по многомерному моделированию в службах Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="e3c16-122">You can deploy the AdventureWorks multidimensional sample database or a project from the Analysis Services multidimensional tutorial to use in this walkthrough.</span></span> <span data-ttu-id="e3c16-123">Дополнительные сведения см. [в разделе Установка образцов данных и проектов для учебника по многомерному моделированию Analysis Services](../install-sample-data-and-projects.md).</span><span class="sxs-lookup"><span data-stu-id="e3c16-123">For more information, see [Install Sample Data and Projects for the Analysis Services Multidimensional Modeling Tutorial](../install-sample-data-and-projects.md).</span></span>  
  
## <a name="example-1-processing-a-dimension-in-a-scheduled-task"></a><span data-ttu-id="e3c16-124">Пример 1. Обработка измерения в запланированной задаче</span><span class="sxs-lookup"><span data-stu-id="e3c16-124">Example 1: Processing a dimension in a scheduled task</span></span>  
 <span data-ttu-id="e3c16-125">В этом примере показано, как создать и запланировать задание по обработке измерения.</span><span class="sxs-lookup"><span data-stu-id="e3c16-125">This example demonstrates how to create and schedule a job that processes a dimension.</span></span>  
  
 <span data-ttu-id="e3c16-126">Запланированная задача служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] представляет собой скрипт XML для аналитики, внедренный в задание агента SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e3c16-126">An [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] scheduled task is an XMLA script that is embedded into a SQL Server Agent job.</span></span> <span data-ttu-id="e3c16-127">Это задание имеет расписание для запуска в нужное время и с нужной частотой.</span><span class="sxs-lookup"><span data-stu-id="e3c16-127">This job is scheduled to run at desired times and frequency.</span></span> <span data-ttu-id="e3c16-128">Поскольку агент SQL Server является частью [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], при создании задачи администрирования придется работать и с ядром СУБД, и со службами [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e3c16-128">Because the SQL Server Agent is part of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you work with both the Database Engine and [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to create and schedule an administrative task.</span></span>  
  
###  <a name="create-a-script-for-processing-a-dimension-in-a-sql-server-agent-job"></a><a name="bkmk_CreateScript"></a><span data-ttu-id="e3c16-129">Создание скрипта для обработки измерения в агент SQL Serverном задании</span><span class="sxs-lookup"><span data-stu-id="e3c16-129">Create a script for processing a dimension in a SQL Server Agent job</span></span>  
  
1.  <span data-ttu-id="e3c16-130">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]подключитесь к службам [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e3c16-130">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="e3c16-131">Откройте папку базы данных и найдите измерение.</span><span class="sxs-lookup"><span data-stu-id="e3c16-131">Open a database folder and find a dimension.</span></span> <span data-ttu-id="e3c16-132">Щелкните измерение правой кнопкой мыши и выберите команду **Обработать**.</span><span class="sxs-lookup"><span data-stu-id="e3c16-132">Right-click the dimension and select **Process**.</span></span>  
  
2.  <span data-ttu-id="e3c16-133">Убедитесь в том, что в диалоговом окне **Обработка измерения** в разделе **Список объектов** для столбца **Параметры обработки**выбран параметр **Обработка. Полная**.</span><span class="sxs-lookup"><span data-stu-id="e3c16-133">In the **Process Dimension** dialog box, in the **Process Options** column under **Object list**, verify that the option for this column is **Process Full**.</span></span> <span data-ttu-id="e3c16-134">Если этот параметр не выбран, выделите столбец **Параметры обработки**, а затем в раскрывающемся списке выберите **Обработка. Полная** .</span><span class="sxs-lookup"><span data-stu-id="e3c16-134">If it is not, under **Process Options**, click the option, and then select **Process Full** from the drop-down list.</span></span>  
  
3.  <span data-ttu-id="e3c16-135">Нажмите кнопку **Скрипт**.</span><span class="sxs-lookup"><span data-stu-id="e3c16-135">Click **Script**.</span></span>  
  
     <span data-ttu-id="e3c16-136">На этом шаге открывается окно **XML-запрос** , содержащее скрипт XML для аналитики, который обрабатывает измерение.</span><span class="sxs-lookup"><span data-stu-id="e3c16-136">This step opens an **XML Query** window that contains the XMLA script that processes the dimension.</span></span>  
  
4.  <span data-ttu-id="e3c16-137">В диалоговом окне **Обработка измерения** нажмите кнопку **Отмена** , чтобы закрыть его.</span><span class="sxs-lookup"><span data-stu-id="e3c16-137">In the **Process Dimension** dialog box, click **Cancel** to close the dialog box.</span></span>  
  
5.  <span data-ttu-id="e3c16-138">В окне **Запрос XML для аналитики** выделите скрипт XML для аналитики, щелкните его правой кнопкой мыши и выберите команду **Копировать**.</span><span class="sxs-lookup"><span data-stu-id="e3c16-138">In the **XMLA Query** window, highlight the XMLA script, right-click the highlighted script, and select **Copy**.</span></span>  
  
     <span data-ttu-id="e3c16-139">Этот шаг копирует скрипт XML для аналитики в буфер обмена Windows.</span><span class="sxs-lookup"><span data-stu-id="e3c16-139">This step copies the XMLA script to the Windows Clipboard.</span></span> <span data-ttu-id="e3c16-140">Скрипт XML для аналитики вы можете оставить в буфере обмена или вставить его в «Блокнот» или другой текстовый редактор.</span><span class="sxs-lookup"><span data-stu-id="e3c16-140">You can leave the XMLA script in the Clipboard or paste it into Notepad or another text editor.</span></span> <span data-ttu-id="e3c16-141">Далее приведен пример скрипта XML для аналитики.</span><span class="sxs-lookup"><span data-stu-id="e3c16-141">The following is an example of the XMLA script.</span></span>  
  
    ```  
    <Batch xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
     <Parallel>  
      <Process xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
        <Object>  
          <DatabaseID>Adventure Works DW Multidimensional</DatabaseID>  
          <DimensionID>Dim Account</DimensionID>  
        </Object>  
        <Type>ProcessFull</Type>  
        <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
      </Process>  
     </Parallel>  
    </Batch>  
    ```  
  
###  <a name="create-and-schedule-the-dimension-processing-job"></a><a name="bkmk_ProcessJob"></a><span data-ttu-id="e3c16-142">Создание и планирование задания по обработке измерений</span><span class="sxs-lookup"><span data-stu-id="e3c16-142">Create and schedule the dimension processing job</span></span>  
  
1.  <span data-ttu-id="e3c16-143">Подключитесь к экземпляру ядра СУБД, а затем откройте обозреватель объектов.</span><span class="sxs-lookup"><span data-stu-id="e3c16-143">Connect to an instance of the Database Engine and then open Object Explorer.</span></span>  
  
2.  <span data-ttu-id="e3c16-144">Разверните узел **Агент SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="e3c16-144">Expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="e3c16-145">Щелкните правой кнопкой мыши **Задания** и выберите пункт **Создать задание**.</span><span class="sxs-lookup"><span data-stu-id="e3c16-145">Right-click **Jobs** and select **New Job**.</span></span>  
  
4.  <span data-ttu-id="e3c16-146">В диалоговом окне **Создание задания** введите имя задания в поле **Имя**.</span><span class="sxs-lookup"><span data-stu-id="e3c16-146">In the **New Job** dialog box, enter a job name in **Name**.</span></span>  
  
5.  <span data-ttu-id="e3c16-147">В разделе **Выбор страницы**выберите **Шаги**, а затем нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="e3c16-147">Under **Select a page**, select **Steps**, and then click **New**.</span></span>  
  
6.  <span data-ttu-id="e3c16-148">В диалоговом окне **Новый шаг задания** введите имя шага в поле **Имя шага**.</span><span class="sxs-lookup"><span data-stu-id="e3c16-148">In the **New Job Step** dialog box, enter a step name in **Step Name**.</span></span>  
  
7.  <span data-ttu-id="e3c16-149">В окне **сервер**введите **localhost** для экземпляра по умолчанию [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] и \*\*localhost \\ \*\* \<*instance name*> для именованного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="e3c16-149">In **Server**, type **localhost** for a default instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] and **localhost\\**\<*instance name*> for a named instance.</span></span>  
  
     <span data-ttu-id="e3c16-150">Если задание будет выполняться с удаленного компьютера, используйте имя сервера и имя экземпляра, в котором будет выполняться задание.</span><span class="sxs-lookup"><span data-stu-id="e3c16-150">If you will be running the job from a remote computer, use the server name and instance name where the job will run.</span></span> <span data-ttu-id="e3c16-151">Используйте формат \<*server name*> для экземпляра по умолчанию и \<*server name*> \\ < *имя экземпляра*> для именованного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="e3c16-151">Use the format \<*server name*> for a default instance, and \<*server name*>\\<*instance name*> for a named instance.</span></span>  
  
8.  <span data-ttu-id="e3c16-152">В поле **Тип**выберите **Команда служб SQL Server Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="e3c16-152">In **Type**, select **SQL Server Analysis Services Command**.</span></span>  
  
9. <span data-ttu-id="e3c16-153">В поле **Команда**щелкните правой кнопкой мыши и выберите **Вставить**.</span><span class="sxs-lookup"><span data-stu-id="e3c16-153">In **Command**, right-click and select **Paste**.</span></span> <span data-ttu-id="e3c16-154">Скрипт XML для аналитики, созданный на предыдущем шаге, должен отобразиться в командном окне.</span><span class="sxs-lookup"><span data-stu-id="e3c16-154">The XMLA script that you generated in the previous step should appear in the command window.</span></span>  
  
10. <span data-ttu-id="e3c16-155">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e3c16-155">Click **OK**.</span></span>  
  
11. <span data-ttu-id="e3c16-156">В разделе **Выбор страницы**выберите **Расписания**, а затем нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="e3c16-156">Under **Select a page**, click **Schedules**, and then click **New**.</span></span>  
  
12. <span data-ttu-id="e3c16-157">В диалоговом окне **Создание расписания задания** введите имя расписания в поле **Имя**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e3c16-157">In the **New Job Schedule** dialog box, enter a schedule name in **Name**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="e3c16-158">Этот шаг создает расписание на воскресенье в 00:00.</span><span class="sxs-lookup"><span data-stu-id="e3c16-158">This step creates a schedule for Sunday at 12:00 AM.</span></span> <span data-ttu-id="e3c16-159">Следующий шаг показывает, как вручную выполнить задание.</span><span class="sxs-lookup"><span data-stu-id="e3c16-159">The next step shows you how to manually execute the job.</span></span> <span data-ttu-id="e3c16-160">Вы можете также указать расписание, которое выполнит задание во время его мониторинга.</span><span class="sxs-lookup"><span data-stu-id="e3c16-160">You can also specify a schedule that executes the job when you are monitoring it.</span></span>  
  
13. <span data-ttu-id="e3c16-161">В диалоговом окне **Создание задания** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e3c16-161">In the **New Job** dialog box, click **OK**.</span></span>  
  
14. <span data-ttu-id="e3c16-162">В **обозревателе объектов**разверните узел **Задания**, щелкните правой кнопкой мыши созданное задание и выберите команду **Запустить задание на шаге**.</span><span class="sxs-lookup"><span data-stu-id="e3c16-162">In **Object Explorer**, expand **Jobs**, right-click the job you created, and then select **Start Job at Step**.</span></span>  
  
     <span data-ttu-id="e3c16-163">Поскольку задание состоит только из одного шага, оно будет выполнено немедленно.</span><span class="sxs-lookup"><span data-stu-id="e3c16-163">Because the job has only one step, the job executes immediately.</span></span> <span data-ttu-id="e3c16-164">Если в задании содержится более одного шага, вы можете выбрать шаг, с которого будет запущено задание.</span><span class="sxs-lookup"><span data-stu-id="e3c16-164">If the job contains more than one step, you can select the step at which the job should start.</span></span>  
  
15. <span data-ttu-id="e3c16-165">По завершении задания нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="e3c16-165">When the job finishes, click **Close**.</span></span>  
  
## <a name="example-2-batch-processing-a-dimension-and-a-partition-in-a-scheduled-task"></a><span data-ttu-id="e3c16-166">Пример 2. Пакетная обработка измерения и секции в запланированной задаче</span><span class="sxs-lookup"><span data-stu-id="e3c16-166">Example 2: Batch processing a dimension and a partition in a scheduled task</span></span>  
 <span data-ttu-id="e3c16-167">Процедуры в данном примере демонстрируют, как создать и запланировать задание по пакетной обработке измерения базы данных служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] и одновременно обработать секцию куба, которая зависит от измерения для агрегата.</span><span class="sxs-lookup"><span data-stu-id="e3c16-167">The procedures in this example demonstrate how to create and schedule a job that batch processes an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database dimension, and at the same time to process a  cube partition that depends on the dimension for aggregation.</span></span> <span data-ttu-id="e3c16-168">Дополнительные сведения о пакетной обработке объектов [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] см. в разделе [Пакетная обработка (службы Analysis Services)](../multidimensional-models/batch-processing-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="e3c16-168">For more information about batch processing of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects, see [Batch Processing &#40;Analysis Services&#41;](../multidimensional-models/batch-processing-analysis-services.md).</span></span>  
  
###  <a name="create-a-script-for-batch-processing-a-dimension-and-partition-in-a-sql-server-agent-job"></a><a name="bkmk_BatchProcess"></a><span data-ttu-id="e3c16-169">Создание скрипта для пакетной обработки измерения и секции в задании агент SQL Server</span><span class="sxs-lookup"><span data-stu-id="e3c16-169">Create a script for batch processing a dimension and partition in a SQL Server Agent job</span></span>  
  
1.  <span data-ttu-id="e3c16-170">Используя ту же базу данных, разверните узел **Измерения**, щелкните правой кнопкой мыши измерение **Клиент** и выберите **Обработать**.</span><span class="sxs-lookup"><span data-stu-id="e3c16-170">Using the same database, expand **Dimensions**, right-click the **Customer** dimension, and select **Process**.</span></span>  
  
2.  <span data-ttu-id="e3c16-171">Убедитесь в том, что в диалоговом окне **Обработка измерения** для столбца **Параметры обработки** в разделе **Список объектов**выбран параметр **Обработка. Полная**.</span><span class="sxs-lookup"><span data-stu-id="e3c16-171">In the **Process Dimension** dialog box, in **Process Options** column under **Object list**, verify that the option for this column is **Process Full**.</span></span>  
  
3.  <span data-ttu-id="e3c16-172">Нажмите кнопку **Скрипт**.</span><span class="sxs-lookup"><span data-stu-id="e3c16-172">Click **Script**.</span></span>  
  
     <span data-ttu-id="e3c16-173">На этом шаге открывается окно **XML-запрос** , содержащее скрипт XML для аналитики, который обрабатывает измерение.</span><span class="sxs-lookup"><span data-stu-id="e3c16-173">This step opens an **XML Query** window that contains the XMLA script that processes the dimension.</span></span>  
  
4.  <span data-ttu-id="e3c16-174">В диалоговом окне **Обработка измерения** нажмите кнопку **Отмена** , чтобы закрыть его.</span><span class="sxs-lookup"><span data-stu-id="e3c16-174">In the **Process Dimension** dialog box, click **Cancel** to close the dialog box.</span></span>  
  
5.  <span data-ttu-id="e3c16-175">Разверните последовательно узлы **Кубы**, **Adventure Works**, **Группы мер**, **Интернет-продажи**, **Секции**, щелкните правой кнопкой мыши последнюю секцию в списке и выберите команду **Обработать**.</span><span class="sxs-lookup"><span data-stu-id="e3c16-175">Expand **Cubes**, expand **Adventure Works**, expand **Measure Groups**, expand **Internet Sales**, expand **Partitions**, right-click the last partition in the list, and then select **Process**.</span></span>  
  
6.  <span data-ttu-id="e3c16-176">Убедитесь в том, что в диалоговом окне **Обработка секции** для столбца **Параметры обработки** в разделе **Список объектов**выбран параметр **Обработка. Полная**.</span><span class="sxs-lookup"><span data-stu-id="e3c16-176">In the **Process Partition** dialog box, in the **Process Options** column under **Object list**, verify that the option for this column is **Process Full**.</span></span>  
  
7.  <span data-ttu-id="e3c16-177">Нажмите кнопку **Скрипт**.</span><span class="sxs-lookup"><span data-stu-id="e3c16-177">Click **Script**.</span></span>  
  
     <span data-ttu-id="e3c16-178">На этом шаге откроется второе окно **XML-запрос** , содержащее скрипт XML для аналитики, который обрабатывает секцию.</span><span class="sxs-lookup"><span data-stu-id="e3c16-178">This step opens a second **XML Query** window that contains the XMLA script that processes the partition.</span></span>  
  
8.  <span data-ttu-id="e3c16-179">В диалоговом окне **Обработка секции** нажмите кнопку **Отмена** , чтобы закрыть редактор.</span><span class="sxs-lookup"><span data-stu-id="e3c16-179">In the **Process Partition** dialog box, click **Cancel** to close the editor.</span></span>  
  
     <span data-ttu-id="e3c16-180">На этом этапе необходимо объединить два скрипта и обеспечить обработку измерения в первую очередь.</span><span class="sxs-lookup"><span data-stu-id="e3c16-180">At this point you must merge the two scripts, and ensure that the dimension is processed first.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="e3c16-181">Если сначала обрабатывается секция, последующая обработка измерения приводит к тому, что секция становится необработанной.</span><span class="sxs-lookup"><span data-stu-id="e3c16-181">If the partition is processed first, the subsequent dimension processing causes the partition to become unprocessed.</span></span> <span data-ttu-id="e3c16-182">После этого для достижения обработанного состояния требуется повторная обработка секции.</span><span class="sxs-lookup"><span data-stu-id="e3c16-182">The partition would then require a second processing to reach a processed state.</span></span>  
  
9. <span data-ttu-id="e3c16-183">В окне **Запрос XML для аналитики** , содержащем скрипт XML для аналитики, который обрабатывает раздел, выделите код внутри тегов `Batch` и `Parallel` , щелкните правой кнопкой мыши выделенный скрипт и выберите команду **Копировать**.</span><span class="sxs-lookup"><span data-stu-id="e3c16-183">In the **XMLA Query** window that contains the XMLA script that processes the partition, highlight the code inside the `Batch` and `Parallel` tags, right-click the highlighted script, and select **Copy**.</span></span>  
  
    ```  
    <Process xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
        <Object>  
          <DatabaseID> Adventure Works DW Multidimensional</DatabaseID>  
          <CubeID>Adventure Works</CubeID>  
          <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
          <PartitionID> Internet_Sales_2004</PartitionID>  
        </Object>  
        <Type>ProcessFull</Type>  
        <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
      </Process>  
    ```  
  
10. <span data-ttu-id="e3c16-184">Откройте окно **Запрос XML для аналитики** , содержащее скрипт XML для аналитики, который обрабатывает измерение.</span><span class="sxs-lookup"><span data-stu-id="e3c16-184">Open the **XMLA Query** window that contains the XMLA script that processes the dimension.</span></span> <span data-ttu-id="e3c16-185">Щелкните правой кнопкой мыши внутри скрипта слева от тега `</Process>` и выберите команду **Вставить**.</span><span class="sxs-lookup"><span data-stu-id="e3c16-185">Right-click within the script to the left of the `</Process>` tag and select **Paste**.</span></span>  
  
     <span data-ttu-id="e3c16-186">В следующем примере показан измененный скрипт XML для аналитики.</span><span class="sxs-lookup"><span data-stu-id="e3c16-186">The following example shows the revised XMLA script.</span></span>  
  
    ```  
    <Batch xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
     <Parallel>  
      <Process xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
        <Object>  
          <DatabaseID>Adventure Works DW Multidimensional</DatabaseID>  
          <DimensionID>Dim Customer</DimensionID>  
        </Object>  
        <Type>ProcessFull</Type>  
        <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
      </Process>  
      <Process xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
        <Object>  
          <DatabaseID>Adventure Works DW Multidimensional</DatabaseID>  
          <CubeID>Adventure Works</CubeID>  
          <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
          <PartitionID>Internet_Sales_2004</PartitionID>  
        </Object>  
        <Type>ProcessFull</Type>  
        <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
      </Process>  
     </Parallel>  
    </Batch>  
    ```  
  
11. <span data-ttu-id="e3c16-187">Выделите измененный скрипт XML для аналитики, щелкните его правой кнопкой мыши и выберите команду **Копировать**.</span><span class="sxs-lookup"><span data-stu-id="e3c16-187">Highlight the revised XMLA script, right-click the highlighted script, and select **Copy.**</span></span>  
  
12. <span data-ttu-id="e3c16-188">Этот шаг копирует скрипт XML для аналитики в буфер обмена Windows.</span><span class="sxs-lookup"><span data-stu-id="e3c16-188">This step copies the XMLA script to the Windows Clipboard.</span></span> <span data-ttu-id="e3c16-189">Скрипт XML для аналитики вы можете оставить в буфере обмена, сохранить в файл или вставить его в «Блокнот» или другой текстовый редактор.</span><span class="sxs-lookup"><span data-stu-id="e3c16-189">You can leave the XMLA script in the Clipboard, save it to a file, or paste it into Notepad or another text editor.</span></span>  
  
###  <a name="create-and-schedule-the-batch-processing-job"></a><a name="bkmk_Scheduling"></a><span data-ttu-id="e3c16-190">Создание и планирование задания пакетной обработки</span><span class="sxs-lookup"><span data-stu-id="e3c16-190">Create and schedule the batch processing job</span></span>  
  
1.  <span data-ttu-id="e3c16-191">Подключитесь к экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], после чего откройте обозреватель объектов.</span><span class="sxs-lookup"><span data-stu-id="e3c16-191">Connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and then open Object Explorer.</span></span>  
  
2.  <span data-ttu-id="e3c16-192">Разверните узел **Агент SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="e3c16-192">Expand **SQL Server Agent**.</span></span> <span data-ttu-id="e3c16-193">Если служба не запущена, запустите ее.</span><span class="sxs-lookup"><span data-stu-id="e3c16-193">Start the service if is not running.</span></span>  
  
3.  <span data-ttu-id="e3c16-194">Щелкните правой кнопкой мыши **Задания** и выберите пункт **Создать задание**.</span><span class="sxs-lookup"><span data-stu-id="e3c16-194">Right-click **Jobs** and select **New Job**.</span></span>  
  
4.  <span data-ttu-id="e3c16-195">В диалоговом окне **Создание задания** введите имя задания в поле **Имя**.</span><span class="sxs-lookup"><span data-stu-id="e3c16-195">In the **New Job** dialog box, enter a job name in **Name**.</span></span>  
  
5.  <span data-ttu-id="e3c16-196">В разделе **Шаги**нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="e3c16-196">In **Steps**, click **New**.</span></span>  
  
6.  <span data-ttu-id="e3c16-197">В диалоговом окне **Новый шаг задания** введите имя шага в поле **Имя шага**.</span><span class="sxs-lookup"><span data-stu-id="e3c16-197">In the **New Job Step** dialog box, enter a step name in **Step Name**.</span></span>  
  
7.  <span data-ttu-id="e3c16-198">В поле **Тип**выберите **Команда служб SQL Server Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="e3c16-198">In **Type**, select **SQL Server Analysis Services Command**.</span></span>  
  
8.  <span data-ttu-id="e3c16-199">В разделе **Выполнять как**выберите пункт **Учетная запись службы агента SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="e3c16-199">In **Run as**, select the **SQL Server Agent Service Account**.</span></span> <span data-ttu-id="e3c16-200">Как было указано в разделе «Предварительные требования», эта учетная запись должна иметь разрешения администратора для служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="e3c16-200">Recall from the Prerequisites section that this account must have administrative permissions on Analysis Services.</span></span>  
  
9. <span data-ttu-id="e3c16-201">В поле **Сервер**укажите имя сервера экземпляра служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="e3c16-201">In **Server**, specify the server name of the Analysis Services instance.</span></span>  
  
10. <span data-ttu-id="e3c16-202">В поле **Команда**щелкните правой кнопкой мыши и выберите **Вставить**.</span><span class="sxs-lookup"><span data-stu-id="e3c16-202">In **Command**, right-click and select **Paste**.</span></span>  
  
11. <span data-ttu-id="e3c16-203">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e3c16-203">Click **OK**.</span></span>  
  
12. <span data-ttu-id="e3c16-204">На странице **Расписания** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="e3c16-204">In the **Schedules** page, click **New**.</span></span>  
  
13. <span data-ttu-id="e3c16-205">В диалоговом окне **Создание расписания задания** введите имя расписания в поле **Имя**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e3c16-205">In the **New Job Schedule** dialog box, enter a schedule name in **Name**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="e3c16-206">Этот шаг создает расписание на воскресенье в 00:00.</span><span class="sxs-lookup"><span data-stu-id="e3c16-206">This step creates a schedule for Sunday at 12:00 AM.</span></span> <span data-ttu-id="e3c16-207">Следующий шаг показывает, как вручную выполнить задание.</span><span class="sxs-lookup"><span data-stu-id="e3c16-207">The next step shows you how to manually execute the job.</span></span> <span data-ttu-id="e3c16-208">Вы можете также выбрать расписание, которое выполнит задание во время его мониторинга.</span><span class="sxs-lookup"><span data-stu-id="e3c16-208">You can also select a schedule which will execute the job when you are monitoring it.</span></span>  
  
14. <span data-ttu-id="e3c16-209">Чтобы закрыть диалоговое окно, нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="e3c16-209">Click **OK** to close the dialog box.</span></span>  
  
15. <span data-ttu-id="e3c16-210">В **обозревателе объектов**разверните узел **Задания**, щелкните правой кнопкой мыши созданное задание и выберите команду **Запустить задание на шаге**.</span><span class="sxs-lookup"><span data-stu-id="e3c16-210">In **Object Explorer**, expand **Jobs**, right-click the job you created, and select **Start Job at Step**.</span></span>  
  
     <span data-ttu-id="e3c16-211">Поскольку задание состоит только из одного шага, оно будет выполнено немедленно.</span><span class="sxs-lookup"><span data-stu-id="e3c16-211">Because the job has only one step, the job executes immediately.</span></span> <span data-ttu-id="e3c16-212">Если в задании содержится более одного шага, вы можете выбрать шаг, с которого будет запущено задание.</span><span class="sxs-lookup"><span data-stu-id="e3c16-212">If the job contains more than one step, you can select the step at which the job should start.</span></span>  
  
16. <span data-ttu-id="e3c16-213">По завершении задания нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="e3c16-213">When the job finishes, click **Close**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3c16-214">См. также:</span><span class="sxs-lookup"><span data-stu-id="e3c16-214">See Also</span></span>  
 <span data-ttu-id="e3c16-215">[Параметры обработки и настройки &#40;Analysis Services&#41;](../multidimensional-models/processing-options-and-settings-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="e3c16-215">[Processing Options and Settings &#40;Analysis Services&#41;](../multidimensional-models/processing-options-and-settings-analysis-services.md) </span></span>  
 [<span data-ttu-id="e3c16-216">Создание скриптов для административных задач в службах Analysis Services</span><span class="sxs-lookup"><span data-stu-id="e3c16-216">Script Administrative Tasks in Analysis Services</span></span>](../script-administrative-tasks-in-analysis-services.md)  
  
  
