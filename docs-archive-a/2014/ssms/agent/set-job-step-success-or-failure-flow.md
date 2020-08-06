---
title: Настройка потока действий системы при успешном или неуспешном выполнении шага задания | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, action flow logic
- successful jobs [SQL Server]
- failed jobs [SQL Server]
- jobs [SQL Server Agent], action flow logic
ms.assetid: 23041ccf-8a07-41d3-85b9-c449a54b7e1e
author: stevestein
ms.author: sstein
ms.openlocfilehash: fddc5820676cb231b6f0cd5f7151e24d8eceaefa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751632"
---
# <a name="set-job-step-success-or-failure-flow"></a><span data-ttu-id="9ca0f-102">Настройка потока действий системы при успешном или неуспешном выполнении шага задания</span><span class="sxs-lookup"><span data-stu-id="9ca0f-102">Set Job Step Success or Failure Flow</span></span>
  <span data-ttu-id="9ca0f-103">При создании [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] заданий агента можно указать, какие действия [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] должны выполняться при возникновении ошибки во время выполнения задания.</span><span class="sxs-lookup"><span data-stu-id="9ca0f-103">When creating [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs, you can specify what action [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should take if a failure occurs during job execution.</span></span> <span data-ttu-id="9ca0f-104">Определите действия, которые должен предпринять [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] при успешном и неуспешном завершении каждого шага задания.</span><span class="sxs-lookup"><span data-stu-id="9ca0f-104">Determine the action that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should take upon the success or failure of each job step.</span></span> <span data-ttu-id="9ca0f-105">Затем с помощью агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] настройте логику потока действий на шаге.</span><span class="sxs-lookup"><span data-stu-id="9ca0f-105">Then use the following procedure to configure the job step action flow logic by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span>  
  
-   <span data-ttu-id="9ca0f-106">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="9ca0f-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="9ca0f-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="9ca0f-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="9ca0f-108">**Для настройки потока действий системы при успешном или неуспешном выполнении шага задания используется:**</span><span class="sxs-lookup"><span data-stu-id="9ca0f-108">**To set job step success or failure flow, using:**</span></span>  
  
     [<span data-ttu-id="9ca0f-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9ca0f-109">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="9ca0f-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9ca0f-110">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="9ca0f-111">Управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="9ca0f-111">SQL Server Management Objects</span></span>](#SMO)  
  
## <a name="before-you-begin"></a><span data-ttu-id="9ca0f-112">Перед началом</span><span class="sxs-lookup"><span data-stu-id="9ca0f-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9ca0f-113">безопасность</span><span class="sxs-lookup"><span data-stu-id="9ca0f-113">Security</span></span>  
 <span data-ttu-id="9ca0f-114">Дополнительные сведения см. в разделе [Обеспечение безопасности агента SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="9ca0f-114">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="9ca0f-115">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9ca0f-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-job-step-success-or-failure-flow"></a><span data-ttu-id="9ca0f-116">Настройка потока действий системы при успешном или неуспешном выполнении шага задания</span><span class="sxs-lookup"><span data-stu-id="9ca0f-116">To set job step success or failure flow</span></span>  
  
1.  <span data-ttu-id="9ca0f-117">В **обозревателе объектов**раскройте узел **Агент SQL Server**, а затем узел **Задания**.</span><span class="sxs-lookup"><span data-stu-id="9ca0f-117">In **Object Explorer**, expand **SQL Server Agent**, and then expand **Jobs**.</span></span>  
  
2.  <span data-ttu-id="9ca0f-118">Щелкните правой кнопкой мыши задание, которое необходимо изменить, и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="9ca0f-118">Right-click the job you want to edit, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="9ca0f-119">Перейдите на страницу **Шаги** , выберите нужный шаг и щелкните **Редактировать**.</span><span class="sxs-lookup"><span data-stu-id="9ca0f-119">Select the **Steps** page, click a step, and then click **Edit**.</span></span>  
  
4.  <span data-ttu-id="9ca0f-120">В диалоговом окне **Свойства шага задания** выберите страницу **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="9ca0f-120">In the **Job Step Properties** dialog box, select the **Advanced** page.</span></span>  
  
5.  <span data-ttu-id="9ca0f-121">В диалоговом окне **Действие при успехе**выберите действие, которое необходимо выполнить при успешном окончании шага задания.</span><span class="sxs-lookup"><span data-stu-id="9ca0f-121">In the **On success action**list, click the action to perform if the job step completes successfully.</span></span>  
  
6.  <span data-ttu-id="9ca0f-122">В поле **Количество повторных попыток** введите количество от 0 до 9999 повторных попыток выполнения шага задания, прежде чем будет принято решение о неуспешном завершении.</span><span class="sxs-lookup"><span data-stu-id="9ca0f-122">In the **Retry attempts** box, enter the number of times from 0 through 9999 that the job step should be repeated before it is considered to have failed.</span></span> <span data-ttu-id="9ca0f-123">При вводе в поле **Повторные попытки** значения, превышающего 0, введите значение в поле **Интервал повтора (в минутах)** . Указанное значение определяет длительность интервала от 1 до 9999 минут между повторными попытками выполнения шага задания.</span><span class="sxs-lookup"><span data-stu-id="9ca0f-123">If you entered a value greater than 0 in the **Retry attempts** box, enter in the **Retry interval (minutes)** box the number of minutes from 1 through 9999 that must pass before the job step is retried.</span></span>  
  
7.  <span data-ttu-id="9ca0f-124">В списке **Действия при неуспешном выполнении** выберите действие, которое необходимо выполнить в случае неуспешного завершения шага задания.</span><span class="sxs-lookup"><span data-stu-id="9ca0f-124">In the **On failure action** list, click the action to perform if the job step fails.</span></span>  
  
8.  <span data-ttu-id="9ca0f-125">Если задание является скриптом [!INCLUDE[tsql](../../includes/tsql-md.md)] , возможен выбор из следующих вариантов.</span><span class="sxs-lookup"><span data-stu-id="9ca0f-125">If the job is a [!INCLUDE[tsql](../../includes/tsql-md.md)] script, you can choose from the following options:</span></span>  
  
    -   <span data-ttu-id="9ca0f-126">В поле **Выходной файл** введите имя выходного файла, в который будет происходить запись выходных данных скрипта.</span><span class="sxs-lookup"><span data-stu-id="9ca0f-126">In the **Output file** box, enter the name of an output file to which the script output will be written.</span></span> <span data-ttu-id="9ca0f-127">По умолчанию файл перезаписывается при каждом выполнении шага задания.</span><span class="sxs-lookup"><span data-stu-id="9ca0f-127">By default the file is overwritten each time the job step executes.</span></span> <span data-ttu-id="9ca0f-128">Если не нужно перезаписывать файл вывода, поставьте флажок **Дописать выходные данные в существующий файл**.</span><span class="sxs-lookup"><span data-stu-id="9ca0f-128">If you do not want the output file overwritten, check **Append output to existing file**.</span></span>  
  
    -   <span data-ttu-id="9ca0f-129">Установите флажок **Сохранять данные журнала в таблице** , если журнал шага задания необходимо вести в таблице базы данных.</span><span class="sxs-lookup"><span data-stu-id="9ca0f-129">Check **Log to table** if you want to log the job step to a database table.</span></span> <span data-ttu-id="9ca0f-130">По умолчанию содержимое таблицы перезаписывается при каждом выполнении шага задания.</span><span class="sxs-lookup"><span data-stu-id="9ca0f-130">By default the table contents are overwritten each time the job step executes.</span></span> <span data-ttu-id="9ca0f-131">Если не нужно, чтобы содержимое таблицы перезаписывалось, поставьте флажок **Дописать выходные данные в существующую запись в таблице**.</span><span class="sxs-lookup"><span data-stu-id="9ca0f-131">If you do not want the table contents overwritten, check **Append output to existing entry in table**.</span></span> <span data-ttu-id="9ca0f-132">После выполнения шага задания можно просмотреть содержимое этой таблицы, нажав **Просмотр**.</span><span class="sxs-lookup"><span data-stu-id="9ca0f-132">After the job step executes, you can view the contents of this table by clicking **View**.</span></span>  
  
    -   <span data-ttu-id="9ca0f-133">Установите флажок **Включить в журнал выходные данные шага** , если результаты шага должны быть включены в его журнал.</span><span class="sxs-lookup"><span data-stu-id="9ca0f-133">Check **Include step output in history** if you want the output included in the step's history.</span></span> <span data-ttu-id="9ca0f-134">Результат будет отображен только в случае отсутствия ошибок.</span><span class="sxs-lookup"><span data-stu-id="9ca0f-134">Output will only be shown if there were no errors.</span></span> <span data-ttu-id="9ca0f-135">Кроме того, отображаемый результат может быть усечен.</span><span class="sxs-lookup"><span data-stu-id="9ca0f-135">Also, output may be truncated.</span></span>  
  
9. <span data-ttu-id="9ca0f-136">В списке **Выполнять от имени пользователя** выберите учетную запись-посредник с учетными данными, которые должно использовать задание.</span><span class="sxs-lookup"><span data-stu-id="9ca0f-136">If the **Run as user** list is available, select the proxy account with the credentials that the job will use.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="9ca0f-137">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9ca0f-137">Using Transact-SQL</span></span>  
  
#### <a name="to-set-job-step-success-or-failure-flow"></a><span data-ttu-id="9ca0f-138">Настройка потока действий системы при успешном или неуспешном выполнении шага задания</span><span class="sxs-lookup"><span data-stu-id="9ca0f-138">To set job step success or failure flow</span></span>  
  
1.  <span data-ttu-id="9ca0f-139">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ca0f-139">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="9ca0f-140">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="9ca0f-140">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="9ca0f-141">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="9ca0f-141">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Set database to read only',  
        @subsystem = N'TSQL',  
        @command = N'ALTER DATABASE SALES SET READ_ONLY',   
        @on_success_action = 1;  
    GO  
    ```  
  
 <span data-ttu-id="9ca0f-142">Дополнительные сведения см. в разделе [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9ca0f-142">For more information, see [sp_add_jobstep &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobstep-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="9ca0f-143">Использование управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="9ca0f-143">Using SQL Server Management Objects</span></span>  

### <a name="to-set-job-step-success-or-failure-flow"></a><span data-ttu-id="9ca0f-144">Настройка потока действий системы при успешном или неуспешном выполнении шага задания</span><span class="sxs-lookup"><span data-stu-id="9ca0f-144">To set job step success or failure flow</span></span>
  
 <span data-ttu-id="9ca0f-145">Воспользуйтесь классом `JobStep` в любом языке программирования (Visual Basic, Visual C# или PowerShell).</span><span class="sxs-lookup"><span data-stu-id="9ca0f-145">Use the `JobStep` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="9ca0f-146">Дополнительные сведения см. в статье [Управляющие объекты SQL Server (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="9ca0f-146">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
