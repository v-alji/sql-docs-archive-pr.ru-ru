---
title: Использование Windows PowerShell в шагах агента SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: f25f7549-c9b3-4618-85f2-c9a08adbe0e3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8c100e2eaf1f9b706087bd991fbc268540c29a46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658858"
---
# <a name="run-windows-powershell-steps-in-sql-server-agent"></a><span data-ttu-id="45313-102">Использование Windows PowerShell в шагах агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="45313-102">Run Windows PowerShell Steps in SQL Server Agent</span></span>
  <span data-ttu-id="45313-103">Агент SQL Server применяется для запуска скриптов SQL Server PowerShell в запланированное время.</span><span class="sxs-lookup"><span data-stu-id="45313-103">Use SQL Server Agent to run SQL Server PowerShell scripts at schedule times.</span></span>  
  
1.  <span data-ttu-id="45313-104">**Перед началом работы выполните следующие действия.**  [Ограничения](#LimitationsRestrictions)</span><span class="sxs-lookup"><span data-stu-id="45313-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions)</span></span>  
  
2.  <span data-ttu-id="45313-105">**Запуск PowerShell из агента SQL Server с помощью:**  [шагов задания PowerShell](#PShellJob), [шагов задания командной строки](#CmdExecJob).</span><span class="sxs-lookup"><span data-stu-id="45313-105">**To run PowerShell from SQL Server Agent, using:**  [PowerShell Job Step](#PShellJob), [Command Prompt Job Step](#CmdExecJob)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="45313-106">Перед началом</span><span class="sxs-lookup"><span data-stu-id="45313-106">Before You Begin</span></span>  
 <span data-ttu-id="45313-107">Существует несколько типов шагов заданий агента [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="45313-107">There are several types of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent job steps.</span></span> <span data-ttu-id="45313-108">Каждый тип связан с некоторой подсистемой, в которой реализуется определенная среда, например агент репликации или среда командной строки.</span><span class="sxs-lookup"><span data-stu-id="45313-108">Each type is associated with a subsystem that implements a specific environment, such as a replication agent or command prompt environment.</span></span> <span data-ttu-id="45313-109">Можно создавать скрипты Windows PowerShell, а затем использовать агент [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , чтобы включить скрипты в задания, которые выполняются в запланированное время или в ответ на события [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="45313-109">You can code Windows PowerShell scripts, and then use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent to include the scripts in jobs that run at scheduled times or in response to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] events.</span></span> <span data-ttu-id="45313-110">Скрипты Windows PowerShell можно запускать либо с помощью шагов задания командной строки, либо с помощью шагов задания PowerShell.</span><span class="sxs-lookup"><span data-stu-id="45313-110">Windows PowerShell scripts can be run using either a command prompt job step or a PowerShell job step.</span></span>  
  
1.  <span data-ttu-id="45313-111">Используйте шаги задания PowerShell для запуска подсистемой агента [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] программы `sqlps`, запускающей PowerShell 2.0 и импортирующей модуль `sqlps`.</span><span class="sxs-lookup"><span data-stu-id="45313-111">Use a PowerShell job step to have the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent subsystem run the `sqlps` utility, which launches PowerShell 2.0 and imports the `sqlps` module.</span></span>  
  
2.  <span data-ttu-id="45313-112">Используйте шаг задания командной строки для запуска PowerShell.exe и укажите скрипт, импортирующий модуль `sqlps`.</span><span class="sxs-lookup"><span data-stu-id="45313-112">Use a command prompt job step to run PowerShell.exe, and specify a script that imports the `sqlps` module.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="45313-113">Ограничения</span><span class="sxs-lookup"><span data-stu-id="45313-113">Limitations and Restrictions</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="45313-114">Каждый шаг задания агента [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], запускающий PowerShell с модулем `sqlps`, запускает процесс, которому требуется приблизительно 20 МБ памяти.</span><span class="sxs-lookup"><span data-stu-id="45313-114">Each [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent job step that runs PowerShell with the `sqlps` module launches a process which consumes approximately 20 MB of memory.</span></span> <span data-ttu-id="45313-115">Одновременный запуск большого числа шагов задания Windows PowerShell может иметь негативное влияние на производительность.</span><span class="sxs-lookup"><span data-stu-id="45313-115">Running large numbers of concurrent Windows PowerShell job steps can adversely impact performance.</span></span>  
  
##  <a name="create-a-powershell-job-step"></a><a name="PShellJob"></a><span data-ttu-id="45313-116">Создание шага задания PowerShell</span><span class="sxs-lookup"><span data-stu-id="45313-116">Create a PowerShell Job Step</span></span>  
 <span data-ttu-id="45313-117">**Создание шага задания PowerShell**</span><span class="sxs-lookup"><span data-stu-id="45313-117">**To create a PowerShell job step**</span></span>  
  
1.  <span data-ttu-id="45313-118">Разверните **Агент SQL Server**, создайте задание или щелкните правой кнопкой мыши существующее задание и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="45313-118">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span> <span data-ttu-id="45313-119">Дополнительные сведения о создании заданий см. в разделе [Создание заданий](../ssms/agent/create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="45313-119">For more information about creating a job, see [Creating Jobs](../ssms/agent/create-jobs.md).</span></span>  
  
2.  <span data-ttu-id="45313-120">В диалоговом окне **Свойства задания** выберите страницу **Шаги** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="45313-120">In the **Job Properties** dialog, click the **Steps** page, and then click **New**.</span></span>  
  
3.  <span data-ttu-id="45313-121">В диалоговом окне **Новый шаг задания** введите **имя шага**задания.</span><span class="sxs-lookup"><span data-stu-id="45313-121">In the **New Job Step** dialog, type a job **Step name**.</span></span>  
  
4.  <span data-ttu-id="45313-122">В списке **Тип** выберите **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="45313-122">In the **Type** list, click **PowerShell**.</span></span>  
  
5.  <span data-ttu-id="45313-123">В списке **Выполнять как** выберите учетную запись-посредник с учетными данными, используемыми в задании.</span><span class="sxs-lookup"><span data-stu-id="45313-123">In the **Run as** list, select the proxy account with the credentials that the job will use.</span></span>  
  
6.  <span data-ttu-id="45313-124">В поле **Команда** введите синтаксис скрипта PowerShell, который будет выполняться в данном шаге.</span><span class="sxs-lookup"><span data-stu-id="45313-124">In the **Command** box, enter the PowerShell script syntax that will be executed for the job step.</span></span> <span data-ttu-id="45313-125">Или нажмите кнопку **Открыть** и выберите файл, содержащий скрипт.</span><span class="sxs-lookup"><span data-stu-id="45313-125">Alternately, click **Open** and select a file containing the script syntax.</span></span>  
  
7.  <span data-ttu-id="45313-126">Выберите страницу **Дополнительно** , чтобы задать следующие параметры шага задания: какие действия предпринять в случае успешного или неуспешного выполнения шага задания, сколько раз агенту [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] пытаться его выполнить и как часто повторять эти попытки.</span><span class="sxs-lookup"><span data-stu-id="45313-126">Click the **Advanced** page to set the following job step options: what action to take if the job step succeeds or fails, how many times [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent should try to execute the job step, and how often retry attempts should be made.</span></span>  
  
##  <a name="create-a-command-prompt-job-step"></a><a name="CmdExecJob"></a><span data-ttu-id="45313-127">Создание шага задания командной строки</span><span class="sxs-lookup"><span data-stu-id="45313-127">Create a Command Prompt Job Step</span></span>  
 <span data-ttu-id="45313-128">**Создание шага задания CmdExec**</span><span class="sxs-lookup"><span data-stu-id="45313-128">**To create a CmdExec job step**</span></span>  
  
1.  <span data-ttu-id="45313-129">Разверните **Агент SQL Server**, создайте задание или щелкните правой кнопкой мыши существующее задание и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="45313-129">Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**.</span></span> <span data-ttu-id="45313-130">Дополнительные сведения о создании заданий см. в разделе [Создание заданий](../ssms/agent/create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="45313-130">For more information about creating a job, see [Creating Jobs](../ssms/agent/create-jobs.md).</span></span>  
  
2.  <span data-ttu-id="45313-131">В диалоговом окне **Свойства задания** выберите страницу **Шаги** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="45313-131">In the **Job Properties** dialog, click the **Steps** page, and then click **New**.</span></span>  
  
3.  <span data-ttu-id="45313-132">В диалоговом окне **Новый шаг задания** введите **имя шага**задания.</span><span class="sxs-lookup"><span data-stu-id="45313-132">In the **New Job Step** dialog, type a job **Step name**.</span></span>  
  
4.  <span data-ttu-id="45313-133">В списке **Тип** выберите **Операционная система (CmdExec)**.</span><span class="sxs-lookup"><span data-stu-id="45313-133">In the **Type** list, choose **Operating system (CmdExec)**.</span></span>  
  
5.  <span data-ttu-id="45313-134">В списке **Выполнять как** выберите учетную запись-посредник с учетными данными, используемыми в задании.</span><span class="sxs-lookup"><span data-stu-id="45313-134">In **Run as** list, select the proxy account with the credentials that the job will use.</span></span> <span data-ttu-id="45313-135">По умолчанию шаги задания CmdExec выполняются под учетной записью службы агента SQL Server.</span><span class="sxs-lookup"><span data-stu-id="45313-135">By default, CmdExec job steps run under the context of the SQL Server Agent service account.</span></span>  
  
6.  <span data-ttu-id="45313-136">В поле **Код завершения процесса успешной команды** введите значение от 0 до 999999.</span><span class="sxs-lookup"><span data-stu-id="45313-136">In the **Process exit code of a successful command** box, enter a value from 0 to 999999.</span></span>  
  
7.  <span data-ttu-id="45313-137">В поле **Команда** введите powershell.exe с параметрами, указывающими скрипт PowerShell для запуска.</span><span class="sxs-lookup"><span data-stu-id="45313-137">In the **Command** box, enter powershell.exe with parameters specifying the PowerShell script to be run.</span></span>  
  
8.  <span data-ttu-id="45313-138">Выберите вкладку **Дополнительно** , чтобы задать следующие параметры шага задания: действие, которое необходимо выполнить при успешном или неуспешном выполнении шага задания, количество попыток агента [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] выполнить шаг задания и файл, в который агент [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] может записывать результат выполнения шага задания.</span><span class="sxs-lookup"><span data-stu-id="45313-138">Click the **Advanced** page to set job step options, such as: what action to take if the job step succeeds or fails, how many times [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent should try to execute the job step, and the file where [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent can write the job step output.</span></span> <span data-ttu-id="45313-139">Только члены предопределенной роли сервера **sysadmin** могут записывать выходные данные шага задания в файл операционной системы.</span><span class="sxs-lookup"><span data-stu-id="45313-139">Only members of the **sysadmin** fixed server role can write job step output to an operating system file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45313-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="45313-140">See Also</span></span>  
 [<span data-ttu-id="45313-141">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="45313-141">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
  
  
