---
title: 'Свойства шага задания: Создание шага задания (страница "Общие") | Документация Майкрософт'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.job.stepgeneral.f1
ms.assetid: 8d1885ba-4386-4528-8f2b-68c16852720c
author: stevestein
ms.author: sstein
ms.openlocfilehash: c76e1ecb69a1475ec102f143a6a1ca34fbf91e3f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666328"
---
# <a name="job-step-properties-new-job-step-general-page"></a><span data-ttu-id="a6dad-102">Свойства шага задания: создание шага задания (страница "Общие")</span><span class="sxs-lookup"><span data-stu-id="a6dad-102">Job Step Properties: New Job Step (General Page)</span></span>
  <span data-ttu-id="a6dad-103">Эта страница используется для просмотра и изменения свойств [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] шага задания агента, а также для определения нового шага задания.</span><span class="sxs-lookup"><span data-stu-id="a6dad-103">Use this page to view and change the properties of a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step, or to define a new job step.</span></span>  
  
 <span data-ttu-id="a6dad-104">Для перехода к данной странице в обозревателе объектов среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] разверните агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , щелкните правой кнопкой мыши **Задания**, выберите пункт **Создать задание**, страницу **Шаги** и нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="a6dad-104">To navigate to this page, in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Object Explorer, expand [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, right-click **Jobs**, click **New Jobs**, select the **Steps** page, and click **New**.</span></span> <span data-ttu-id="a6dad-105">Перейти к этой странице можно также, щелкнув правой кнопкой мыши задание в обозревателе объектов, наведя курсор мыши на пункт **Свойства**, затем выбрав страницу **Шаги** и нажав кнопку **Создать**, **Вставить**или **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="a6dad-105">You can also navigate to this page by right-clicking a job in Object Explorer, clicking **Properties**, selecting the **Steps** page, and clicking **New**, **Insert**, or **Edit**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a6dad-106">Варианты</span><span class="sxs-lookup"><span data-stu-id="a6dad-106">Options</span></span>  
 <span data-ttu-id="a6dad-107">**Имя шага**</span><span class="sxs-lookup"><span data-stu-id="a6dad-107">**Step name**</span></span>  
 <span data-ttu-id="a6dad-108">Задайте имя для шага задания.</span><span class="sxs-lookup"><span data-stu-id="a6dad-108">Set the name of the job step.</span></span>  
  
 <span data-ttu-id="a6dad-109">**Тип**</span><span class="sxs-lookup"><span data-stu-id="a6dad-109">**Type**</span></span>  
 <span data-ttu-id="a6dad-110">Укажите подсистему, используемую на шаге задания.</span><span class="sxs-lookup"><span data-stu-id="a6dad-110">Set the subsystem that the job step uses.</span></span> <span data-ttu-id="a6dad-111">Исходя из выбранной подсистемы, параметры отображаются для определения изменения шагов задания.</span><span class="sxs-lookup"><span data-stu-id="a6dad-111">Based on the subsystem you choose, the options displayed for defining the job step change.</span></span>  
  
 <span data-ttu-id="a6dad-112">**Выполнять как**</span><span class="sxs-lookup"><span data-stu-id="a6dad-112">**Run as**</span></span>  
 <span data-ttu-id="a6dad-113">Укажите учетную запись-посредник для этого шага задания.</span><span class="sxs-lookup"><span data-stu-id="a6dad-113">Set the proxy account for the job step.</span></span> <span data-ttu-id="a6dad-114">Члены предопределенной роли сервера sysadmin также могут указать **Учетную запись службы агента SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="a6dad-114">Members of the sysadmin fixed server role may also specify the **SQL Agent Service Account**.</span></span>  
  
 <span data-ttu-id="a6dad-115">**База данных**</span><span class="sxs-lookup"><span data-stu-id="a6dad-115">**Database**</span></span>  
 <span data-ttu-id="a6dad-116">Задайте базу данных, в которой запускается шаг задания.</span><span class="sxs-lookup"><span data-stu-id="a6dad-116">Set the database that the job step runs in.</span></span> <span data-ttu-id="a6dad-117">Этот параметр доступен не для всех типов шагов задания.</span><span class="sxs-lookup"><span data-stu-id="a6dad-117">This option is not available for all job step types.</span></span>  
  
 <span data-ttu-id="a6dad-118">**Command**</span><span class="sxs-lookup"><span data-stu-id="a6dad-118">**Command**</span></span>  
 <span data-ttu-id="a6dad-119">Задайте команду, запускаемую шагом задания.</span><span class="sxs-lookup"><span data-stu-id="a6dad-119">Set the command that the job step runs.</span></span>  
  
## <a name="options-for-transact-sql-job-steps"></a><span data-ttu-id="a6dad-120">Параметры для шагов задания языка Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a6dad-120">Options for Transact-SQL Job Steps</span></span>  
 <span data-ttu-id="a6dad-121">**Открыть**</span><span class="sxs-lookup"><span data-stu-id="a6dad-121">**Open**</span></span>  
 <span data-ttu-id="a6dad-122">Загрузить команду из файла.</span><span class="sxs-lookup"><span data-stu-id="a6dad-122">Load the command from a file.</span></span>  
  
 <span data-ttu-id="a6dad-123">**Выделить все**</span><span class="sxs-lookup"><span data-stu-id="a6dad-123">**Select All**</span></span>  
 <span data-ttu-id="a6dad-124">Выбрать текст команды.</span><span class="sxs-lookup"><span data-stu-id="a6dad-124">Select the text of the command.</span></span>  
  
 <span data-ttu-id="a6dad-125">**Копировать**</span><span class="sxs-lookup"><span data-stu-id="a6dad-125">**Copy**</span></span>  
 <span data-ttu-id="a6dad-126">Копировать выделенный текст в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="a6dad-126">Copy the selected text to the Clipboard.</span></span>  
  
 <span data-ttu-id="a6dad-127">**Вставить**</span><span class="sxs-lookup"><span data-stu-id="a6dad-127">**Paste**</span></span>  
 <span data-ttu-id="a6dad-128">Вставить содержимое буфера обмена.</span><span class="sxs-lookup"><span data-stu-id="a6dad-128">Paste the contents of the Clipboard.</span></span>  
  
 <span data-ttu-id="a6dad-129">**Анализ**</span><span class="sxs-lookup"><span data-stu-id="a6dad-129">**Parse**</span></span>  
 <span data-ttu-id="a6dad-130">Проверить синтаксис команды.</span><span class="sxs-lookup"><span data-stu-id="a6dad-130">Check the syntax of the command.</span></span>  
  
## <a name="options-for-activex-script-job-steps"></a><span data-ttu-id="a6dad-131">Параметры шагов задания скриптов ActiveX</span><span class="sxs-lookup"><span data-stu-id="a6dad-131">Options for ActiveX Script Job Steps</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a6dad-132">Подсистема сценариев ActiveX будет удалена из агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в последующей версии [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a6dad-132">The ActiveX Scripting subsystem will be removed from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in a future version of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a6dad-133">Избегайте использования этого компонента в новых разработках и запланируйте изменение существующих приложений, в которых он применяется.</span><span class="sxs-lookup"><span data-stu-id="a6dad-133">Avoid using this feature in new development work, and plan to modify applications that currently use this feature.</span></span>  
  
 <span data-ttu-id="a6dad-134">**VBScript**</span><span class="sxs-lookup"><span data-stu-id="a6dad-134">**VBScript**</span></span>  
 <span data-ttu-id="a6dad-135">Указывает [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic Scripting Edition в качестве языка, используемого шагами задания.</span><span class="sxs-lookup"><span data-stu-id="a6dad-135">Specify [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic Scripting Edition as the language for the job steps.</span></span>  
  
 <span data-ttu-id="a6dad-136">**Язык JScript**</span><span class="sxs-lookup"><span data-stu-id="a6dad-136">**JScript**</span></span>  
 <span data-ttu-id="a6dad-137">Указывает JScript в качестве языка, используемого шагами задания.</span><span class="sxs-lookup"><span data-stu-id="a6dad-137">Specify JScript as the language for the job steps.</span></span>  
  
 <span data-ttu-id="a6dad-138">**Другое**</span><span class="sxs-lookup"><span data-stu-id="a6dad-138">**Other**</span></span>  
 <span data-ttu-id="a6dad-139">Введите имя языка для шагов задания, написанных на другом языке сценариев.</span><span class="sxs-lookup"><span data-stu-id="a6dad-139">Type the name of the language for job steps written in another scripting language.</span></span>  
  
 <span data-ttu-id="a6dad-140">**Открыть**</span><span class="sxs-lookup"><span data-stu-id="a6dad-140">**Open**</span></span>  
 <span data-ttu-id="a6dad-141">Загрузить команду из файла.</span><span class="sxs-lookup"><span data-stu-id="a6dad-141">Load the command from a file.</span></span>  
  
 <span data-ttu-id="a6dad-142">**Выделить все**</span><span class="sxs-lookup"><span data-stu-id="a6dad-142">**Select All**</span></span>  
 <span data-ttu-id="a6dad-143">Выбрать текст команды.</span><span class="sxs-lookup"><span data-stu-id="a6dad-143">Select the text of the command.</span></span>  
  
 <span data-ttu-id="a6dad-144">**Копировать**</span><span class="sxs-lookup"><span data-stu-id="a6dad-144">**Copy**</span></span>  
 <span data-ttu-id="a6dad-145">Копировать выделенный текст.</span><span class="sxs-lookup"><span data-stu-id="a6dad-145">Copy the selected text.</span></span>  
  
 <span data-ttu-id="a6dad-146">**Вставить**</span><span class="sxs-lookup"><span data-stu-id="a6dad-146">**Paste**</span></span>  
 <span data-ttu-id="a6dad-147">Вставить содержимое буфера обмена.</span><span class="sxs-lookup"><span data-stu-id="a6dad-147">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-operating-system-cmdexec-job-steps"></a><span data-ttu-id="a6dad-148">Параметры для шагов задания операционной системы (CmdExec)</span><span class="sxs-lookup"><span data-stu-id="a6dad-148">Options for Operating System (CmdExec) Job Steps</span></span>  
 <span data-ttu-id="a6dad-149">**Код завершения процесса успешной команды**</span><span class="sxs-lookup"><span data-stu-id="a6dad-149">**Process exit code of a successful command**</span></span>  
 <span data-ttu-id="a6dad-150">Введите код завершения, возвращаемый командой после успешного выполнения.</span><span class="sxs-lookup"><span data-stu-id="a6dad-150">Type the exit code that the command returns to indicate success.</span></span>  
  
 <span data-ttu-id="a6dad-151">**Открыть**</span><span class="sxs-lookup"><span data-stu-id="a6dad-151">**Open**</span></span>  
 <span data-ttu-id="a6dad-152">Загрузить команду из файла.</span><span class="sxs-lookup"><span data-stu-id="a6dad-152">Load the command from a file.</span></span>  
  
 <span data-ttu-id="a6dad-153">**Выделить все**</span><span class="sxs-lookup"><span data-stu-id="a6dad-153">**Select All**</span></span>  
 <span data-ttu-id="a6dad-154">Выбрать текст команды.</span><span class="sxs-lookup"><span data-stu-id="a6dad-154">Select the text of the command.</span></span>  
  
 <span data-ttu-id="a6dad-155">**Копировать**</span><span class="sxs-lookup"><span data-stu-id="a6dad-155">**Copy**</span></span>  
 <span data-ttu-id="a6dad-156">Копировать выделенный текст.</span><span class="sxs-lookup"><span data-stu-id="a6dad-156">Copy the selected text.</span></span>  
  
 <span data-ttu-id="a6dad-157">**Вставить**</span><span class="sxs-lookup"><span data-stu-id="a6dad-157">**Paste**</span></span>  
 <span data-ttu-id="a6dad-158">Вставить содержимое буфера обмена.</span><span class="sxs-lookup"><span data-stu-id="a6dad-158">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-powershell-job-steps"></a><span data-ttu-id="a6dad-159">Параметры для шагов задания языка PowerShell</span><span class="sxs-lookup"><span data-stu-id="a6dad-159">Options for PowerShell Job Steps</span></span>  
 <span data-ttu-id="a6dad-160">**Открыть**</span><span class="sxs-lookup"><span data-stu-id="a6dad-160">**Open**</span></span>  
 <span data-ttu-id="a6dad-161">Загрузить скрипт из файла.</span><span class="sxs-lookup"><span data-stu-id="a6dad-161">Load the script from a file.</span></span>  
  
 <span data-ttu-id="a6dad-162">**Выделить все**</span><span class="sxs-lookup"><span data-stu-id="a6dad-162">**Select All**</span></span>  
 <span data-ttu-id="a6dad-163">Выбрать текст скрипта.</span><span class="sxs-lookup"><span data-stu-id="a6dad-163">Select the text of the script.</span></span>  
  
 <span data-ttu-id="a6dad-164">**Копировать**</span><span class="sxs-lookup"><span data-stu-id="a6dad-164">**Copy**</span></span>  
 <span data-ttu-id="a6dad-165">Копировать выделенный текст.</span><span class="sxs-lookup"><span data-stu-id="a6dad-165">Copy the selected text.</span></span>  
  
 <span data-ttu-id="a6dad-166">**Вставить**</span><span class="sxs-lookup"><span data-stu-id="a6dad-166">**Paste**</span></span>  
 <span data-ttu-id="a6dad-167">Вставить содержимое буфера обмена.</span><span class="sxs-lookup"><span data-stu-id="a6dad-167">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-replication-distributor-job-steps"></a><span data-ttu-id="a6dad-168">Параметры шагов задания распространителя репликации</span><span class="sxs-lookup"><span data-stu-id="a6dad-168">Options for Replication Distributor Job Steps</span></span>  
 <span data-ttu-id="a6dad-169">**Выделить все**</span><span class="sxs-lookup"><span data-stu-id="a6dad-169">**Select All**</span></span>  
 <span data-ttu-id="a6dad-170">Выбрать текст команды.</span><span class="sxs-lookup"><span data-stu-id="a6dad-170">Select the text of the command.</span></span>  
  
 <span data-ttu-id="a6dad-171">**Копировать**</span><span class="sxs-lookup"><span data-stu-id="a6dad-171">**Copy**</span></span>  
 <span data-ttu-id="a6dad-172">Копировать выделенный текст.</span><span class="sxs-lookup"><span data-stu-id="a6dad-172">Copy the selected text.</span></span>  
  
 <span data-ttu-id="a6dad-173">**Вставить**</span><span class="sxs-lookup"><span data-stu-id="a6dad-173">**Paste**</span></span>  
 <span data-ttu-id="a6dad-174">Вставить содержимое буфера обмена.</span><span class="sxs-lookup"><span data-stu-id="a6dad-174">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-replication-merge-job-steps"></a><span data-ttu-id="a6dad-175">Параметры шагов задания по слиянию репликации</span><span class="sxs-lookup"><span data-stu-id="a6dad-175">Options for Replication Merge Job Steps</span></span>  
 <span data-ttu-id="a6dad-176">**Выделить все**</span><span class="sxs-lookup"><span data-stu-id="a6dad-176">**Select All**</span></span>  
 <span data-ttu-id="a6dad-177">Выбрать текст команды.</span><span class="sxs-lookup"><span data-stu-id="a6dad-177">Select the text of the command.</span></span>  
  
 <span data-ttu-id="a6dad-178">**Копировать**</span><span class="sxs-lookup"><span data-stu-id="a6dad-178">**Copy**</span></span>  
 <span data-ttu-id="a6dad-179">Копировать выделенный текст.</span><span class="sxs-lookup"><span data-stu-id="a6dad-179">Copy the selected text.</span></span>  
  
 <span data-ttu-id="a6dad-180">**Вставить**</span><span class="sxs-lookup"><span data-stu-id="a6dad-180">**Paste**</span></span>  
 <span data-ttu-id="a6dad-181">Вставить содержимое буфера обмена.</span><span class="sxs-lookup"><span data-stu-id="a6dad-181">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-replication-queue-reader-job-steps"></a><span data-ttu-id="a6dad-182">Параметры шагов заданий для агента чтения очереди репликации</span><span class="sxs-lookup"><span data-stu-id="a6dad-182">Options for Replication Queue Reader Job Steps</span></span>  
 <span data-ttu-id="a6dad-183">**База данных**</span><span class="sxs-lookup"><span data-stu-id="a6dad-183">**Database**</span></span>  
 <span data-ttu-id="a6dad-184">База данных, которая будет использоваться на шаге задания.</span><span class="sxs-lookup"><span data-stu-id="a6dad-184">The database to use for the job step.</span></span>  
  
 <span data-ttu-id="a6dad-185">**Выделить все**</span><span class="sxs-lookup"><span data-stu-id="a6dad-185">**Select All**</span></span>  
 <span data-ttu-id="a6dad-186">Выбрать текст команды.</span><span class="sxs-lookup"><span data-stu-id="a6dad-186">Select the text of the command.</span></span>  
  
 <span data-ttu-id="a6dad-187">**Копировать**</span><span class="sxs-lookup"><span data-stu-id="a6dad-187">**Copy**</span></span>  
 <span data-ttu-id="a6dad-188">Копировать выделенный текст.</span><span class="sxs-lookup"><span data-stu-id="a6dad-188">Copy the selected text.</span></span>  
  
 <span data-ttu-id="a6dad-189">**Вставить**</span><span class="sxs-lookup"><span data-stu-id="a6dad-189">**Paste**</span></span>  
 <span data-ttu-id="a6dad-190">Вставить содержимое буфера обмена.</span><span class="sxs-lookup"><span data-stu-id="a6dad-190">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-replication-snapshot-job-steps"></a><span data-ttu-id="a6dad-191">Параметры шагов задания моментальных снимков репликации</span><span class="sxs-lookup"><span data-stu-id="a6dad-191">Options for Replication Snapshot Job Steps</span></span>  
 <span data-ttu-id="a6dad-192">**Выделить все**</span><span class="sxs-lookup"><span data-stu-id="a6dad-192">**Select All**</span></span>  
 <span data-ttu-id="a6dad-193">Выбрать текст команды.</span><span class="sxs-lookup"><span data-stu-id="a6dad-193">Select the text of the command.</span></span>  
  
 <span data-ttu-id="a6dad-194">**Копировать**</span><span class="sxs-lookup"><span data-stu-id="a6dad-194">**Copy**</span></span>  
 <span data-ttu-id="a6dad-195">Копировать выделенный текст.</span><span class="sxs-lookup"><span data-stu-id="a6dad-195">Copy the selected text.</span></span>  
  
 <span data-ttu-id="a6dad-196">**Вставить**</span><span class="sxs-lookup"><span data-stu-id="a6dad-196">**Paste**</span></span>  
 <span data-ttu-id="a6dad-197">Вставить содержимое буфера обмена.</span><span class="sxs-lookup"><span data-stu-id="a6dad-197">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-replication-transaction-log-reader-job-steps"></a><span data-ttu-id="a6dad-198">Параметры шагов задания агента чтения журнала транзакций репликации</span><span class="sxs-lookup"><span data-stu-id="a6dad-198">Options for Replication Transaction-Log Reader Job Steps</span></span>  
 <span data-ttu-id="a6dad-199">**Выделить все**</span><span class="sxs-lookup"><span data-stu-id="a6dad-199">**Select All**</span></span>  
 <span data-ttu-id="a6dad-200">Выбрать текст команды.</span><span class="sxs-lookup"><span data-stu-id="a6dad-200">Select the text of the command.</span></span>  
  
 <span data-ttu-id="a6dad-201">**Копировать**</span><span class="sxs-lookup"><span data-stu-id="a6dad-201">**Copy**</span></span>  
 <span data-ttu-id="a6dad-202">Копировать выделенный текст.</span><span class="sxs-lookup"><span data-stu-id="a6dad-202">Copy the selected text.</span></span>  
  
 <span data-ttu-id="a6dad-203">**Вставить**</span><span class="sxs-lookup"><span data-stu-id="a6dad-203">**Paste**</span></span>  
 <span data-ttu-id="a6dad-204">Вставить содержимое буфера обмена.</span><span class="sxs-lookup"><span data-stu-id="a6dad-204">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-sql-server-analysis-services-command-job-steps"></a><span data-ttu-id="a6dad-205">Параметры шагов задания команды служб SQL Server Analysis Services</span><span class="sxs-lookup"><span data-stu-id="a6dad-205">Options for SQL Server Analysis Services Command Job Steps</span></span>  
 <span data-ttu-id="a6dad-206">**Server**</span><span class="sxs-lookup"><span data-stu-id="a6dad-206">**Server**</span></span>  
 <span data-ttu-id="a6dad-207">Выбрать сервер, на котором будет выполняться шаг задания.</span><span class="sxs-lookup"><span data-stu-id="a6dad-207">Select the server where the job step runs.</span></span>  
  
 <span data-ttu-id="a6dad-208">**Открыть**</span><span class="sxs-lookup"><span data-stu-id="a6dad-208">**Open**</span></span>  
 <span data-ttu-id="a6dad-209">Загрузить команду из файла.</span><span class="sxs-lookup"><span data-stu-id="a6dad-209">Load the command from a file.</span></span>  
  
 <span data-ttu-id="a6dad-210">**Выделить все**</span><span class="sxs-lookup"><span data-stu-id="a6dad-210">**Select All**</span></span>  
 <span data-ttu-id="a6dad-211">Выбрать текст команды.</span><span class="sxs-lookup"><span data-stu-id="a6dad-211">Select the text of the command.</span></span>  
  
 <span data-ttu-id="a6dad-212">**Копировать**</span><span class="sxs-lookup"><span data-stu-id="a6dad-212">**Copy**</span></span>  
 <span data-ttu-id="a6dad-213">Копировать выделенный текст.</span><span class="sxs-lookup"><span data-stu-id="a6dad-213">Copy the selected text.</span></span>  
  
 <span data-ttu-id="a6dad-214">**Вставить**</span><span class="sxs-lookup"><span data-stu-id="a6dad-214">**Paste**</span></span>  
 <span data-ttu-id="a6dad-215">Вставить содержимое буфера обмена.</span><span class="sxs-lookup"><span data-stu-id="a6dad-215">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-sql-server-analysis-services-query-job-steps"></a><span data-ttu-id="a6dad-216">Параметры шагов задания очереди служб SQL Server Analysis Services</span><span class="sxs-lookup"><span data-stu-id="a6dad-216">Options for SQL Server Analysis Services Query Job Steps</span></span>  
 <span data-ttu-id="a6dad-217">**Server**</span><span class="sxs-lookup"><span data-stu-id="a6dad-217">**Server**</span></span>  
 <span data-ttu-id="a6dad-218">Выбрать сервер, на котором будет выполняться шаг задания.</span><span class="sxs-lookup"><span data-stu-id="a6dad-218">Select the server where the job step runs.</span></span>  
  
 <span data-ttu-id="a6dad-219">**База данных**</span><span class="sxs-lookup"><span data-stu-id="a6dad-219">**Database**</span></span>  
 <span data-ttu-id="a6dad-220">База данных, которая будет использоваться на шаге задания.</span><span class="sxs-lookup"><span data-stu-id="a6dad-220">The database to use for the job step.</span></span>  
  
 <span data-ttu-id="a6dad-221">**Открыть**</span><span class="sxs-lookup"><span data-stu-id="a6dad-221">**Open**</span></span>  
 <span data-ttu-id="a6dad-222">Загрузить команду из файла.</span><span class="sxs-lookup"><span data-stu-id="a6dad-222">Load the command from a file.</span></span>  
  
 <span data-ttu-id="a6dad-223">**Выделить все**</span><span class="sxs-lookup"><span data-stu-id="a6dad-223">**Select All**</span></span>  
 <span data-ttu-id="a6dad-224">Выбрать текст команды.</span><span class="sxs-lookup"><span data-stu-id="a6dad-224">Select the text of the command.</span></span>  
  
 <span data-ttu-id="a6dad-225">**Копировать**</span><span class="sxs-lookup"><span data-stu-id="a6dad-225">**Copy**</span></span>  
 <span data-ttu-id="a6dad-226">Копировать выделенный текст.</span><span class="sxs-lookup"><span data-stu-id="a6dad-226">Copy the selected text.</span></span>  
  
 <span data-ttu-id="a6dad-227">**Вставить**</span><span class="sxs-lookup"><span data-stu-id="a6dad-227">**Paste**</span></span>  
 <span data-ttu-id="a6dad-228">Вставить содержимое буфера обмена.</span><span class="sxs-lookup"><span data-stu-id="a6dad-228">Paste the contents of the Clipboard.</span></span>  
  
## <a name="options-for-integration-services-package-execution-job-steps"></a><span data-ttu-id="a6dad-229">Параметры шагов задания выполнения пакетов служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="a6dad-229">Options for Integration Services Package Execution Job Steps</span></span>  
  
### <a name="general-tab"></a><span data-ttu-id="a6dad-230">Вкладка «Общие»</span><span class="sxs-lookup"><span data-stu-id="a6dad-230">General Tab</span></span>  
 <span data-ttu-id="a6dad-231">Позволяет указать размещение пакета [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] (службы[!INCLUDE[ssIS](../../includes/ssis-md.md)]) и используемый метод проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="a6dad-231">Specify where the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) package is located and what authentication method to use.</span></span> <span data-ttu-id="a6dad-232">При выборе этой вкладки доступны следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="a6dad-232">The following options are available when you select this tab.</span></span>  
  
 <span data-ttu-id="a6dad-233">**Источник пакета**</span><span class="sxs-lookup"><span data-stu-id="a6dad-233">**Package source**</span></span>  
 <span data-ttu-id="a6dad-234">Позволяет указать, где хранится пакет служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a6dad-234">Specify where the [!INCLUDE[ssIS](../../includes/ssis-md.md)] package is stored.</span></span> <span data-ttu-id="a6dad-235">Выберите один из следующих вариантов.</span><span class="sxs-lookup"><span data-stu-id="a6dad-235">Choose one of the following:</span></span>  
  
-   <span data-ttu-id="a6dad-236">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="a6dad-236">**SQL Server**</span></span>  
  
-   <span data-ttu-id="a6dad-237">**Файловая система**</span><span class="sxs-lookup"><span data-stu-id="a6dad-237">**File system**</span></span>  
  
-   <span data-ttu-id="a6dad-238">**Хранилище пакетов служб SSIS**</span><span class="sxs-lookup"><span data-stu-id="a6dad-238">**SSIS Package Store**</span></span>  
  
 <span data-ttu-id="a6dad-239">**Server**</span><span class="sxs-lookup"><span data-stu-id="a6dad-239">**Server**</span></span>  
 <span data-ttu-id="a6dad-240">Введите имя сервера, на котором хранится пакет служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a6dad-240">Type the server name where the [!INCLUDE[ssIS](../../includes/ssis-md.md)] package is stored.</span></span> <span data-ttu-id="a6dad-241">Этот параметр доступен только в случае, если в поле **Источник пакета** указано значение **SQL Server** или **Хранилище пакетов служб SSIS**.</span><span class="sxs-lookup"><span data-stu-id="a6dad-241">This option is only available when **SQL Server** or **SSIS Package Store** is specified for **Package Source**.</span></span>  
  
 <span data-ttu-id="a6dad-242">**Использовать проверку подлинности Windows**</span><span class="sxs-lookup"><span data-stu-id="a6dad-242">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="a6dad-243">Имена входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] используют проверку подлинности [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="a6dad-243">Logins to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] use [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="a6dad-244">**Использовать проверку подлинности SQL Server**</span><span class="sxs-lookup"><span data-stu-id="a6dad-244">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="a6dad-245">Имена входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] используют проверку подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a6dad-245">Logins to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="a6dad-246">При выборе этого метода проверки подлинности введите соответствующие **Имя пользователя** и **Пароль**.</span><span class="sxs-lookup"><span data-stu-id="a6dad-246">If this method of authentication is selected, enter the appropriate **User name** and **Password**.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a6dad-247">поддерживается для обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="a6dad-247">Authentication is provided for backward compatibility.</span></span> <span data-ttu-id="a6dad-248">Для повышения безопасности, по возможности, используйте проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="a6dad-248">For improved security, use Windows Authentication if possible.</span></span>  
  
 <span data-ttu-id="a6dad-249">**Пакет**</span><span class="sxs-lookup"><span data-stu-id="a6dad-249">**Package**</span></span>  
 <span data-ttu-id="a6dad-250">Введите местонахождение пакета.</span><span class="sxs-lookup"><span data-stu-id="a6dad-250">Type the location of the package.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a6dad-251">Для защищенных паролем пакетов [!INCLUDE[ssIS](../../includes/ssis-md.md)] перейдите на вкладку **Конфигурации** и введите пароль в диалоговом окне **Пароль пакета** .</span><span class="sxs-lookup"><span data-stu-id="a6dad-251">For password-protected [!INCLUDE[ssIS](../../includes/ssis-md.md)] packages, click the **Configurations** tab to enter the password in the **Package Password** dialog box.</span></span> <span data-ttu-id="a6dad-252">В противном случае задание агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , выполняющее защищенный паролем пакет, завершится с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="a6dad-252">Otherwise, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job that executes the password-protected package will fail.</span></span>  
  
### <a name="configurations-tab"></a><span data-ttu-id="a6dad-253">Вкладка «Конфигурации»</span><span class="sxs-lookup"><span data-stu-id="a6dad-253">Configurations Tab</span></span>  
 <span data-ttu-id="a6dad-254">Позволяет задать параметры конфигурации пакета служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a6dad-254">Specify configuration options for the [!INCLUDE[ssIS](../../includes/ssis-md.md)] package.</span></span> <span data-ttu-id="a6dad-255">При выборе этой вкладки доступны следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="a6dad-255">The following options are available when this tab is selected.</span></span>  
  
 <span data-ttu-id="a6dad-256">**Файлы конфигурации**</span><span class="sxs-lookup"><span data-stu-id="a6dad-256">**Configuration files**</span></span>  
 <span data-ttu-id="a6dad-257">Содержит список файлов конфигурации пакета.</span><span class="sxs-lookup"><span data-stu-id="a6dad-257">Lists the configuration files for the package.</span></span>  
  
 <span data-ttu-id="a6dad-258">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="a6dad-258">**Add**</span></span>  
 <span data-ttu-id="a6dad-259">Добавить файл конфигурации пакета.</span><span class="sxs-lookup"><span data-stu-id="a6dad-259">Add a configuration file for the package.</span></span>  
  
 <span data-ttu-id="a6dad-260">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="a6dad-260">**Remove**</span></span>  
 <span data-ttu-id="a6dad-261">Удалить файл конфигурации пакета.</span><span class="sxs-lookup"><span data-stu-id="a6dad-261">Remove a configuration file for the package.</span></span>  
  
 <span data-ttu-id="a6dad-262">**Вверх**</span><span class="sxs-lookup"><span data-stu-id="a6dad-262">**Move Up**</span></span>  
 <span data-ttu-id="a6dad-263">Переместить выбранный файл конфигурации вверх.</span><span class="sxs-lookup"><span data-stu-id="a6dad-263">Move the selected configuration file up.</span></span>  
  
 <span data-ttu-id="a6dad-264">**Вниз**</span><span class="sxs-lookup"><span data-stu-id="a6dad-264">**Move Down**</span></span>  
 <span data-ttu-id="a6dad-265">Переместить выбранный файл конфигурации вниз.</span><span class="sxs-lookup"><span data-stu-id="a6dad-265">Move the selected configuration file down.</span></span>  
  
### <a name="command-files-tab"></a><span data-ttu-id="a6dad-266">Вкладка «Командные файлы»</span><span class="sxs-lookup"><span data-stu-id="a6dad-266">Command Files Tab</span></span>  
 <span data-ttu-id="a6dad-267">Позволяет выбрать командные файлы для пакета.</span><span class="sxs-lookup"><span data-stu-id="a6dad-267">Select command files for the package.</span></span> <span data-ttu-id="a6dad-268">Командные файлы обрабатываются в порядке отображения их в списке.</span><span class="sxs-lookup"><span data-stu-id="a6dad-268">Command files are processed in the order in which they appear in the list.</span></span> <span data-ttu-id="a6dad-269">При выборе этой вкладки доступны следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="a6dad-269">The following options are available when you select this tab.</span></span>  
  
 <span data-ttu-id="a6dad-270">**Командные файлы**</span><span class="sxs-lookup"><span data-stu-id="a6dad-270">**Command files**</span></span>  
 <span data-ttu-id="a6dad-271">Содержит список командных файлов пакета.</span><span class="sxs-lookup"><span data-stu-id="a6dad-271">Lists the command files for the package.</span></span>  
  
 <span data-ttu-id="a6dad-272">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="a6dad-272">**Add**</span></span>  
 <span data-ttu-id="a6dad-273">Добавить командный файл.</span><span class="sxs-lookup"><span data-stu-id="a6dad-273">Add a command file.</span></span>  
  
 <span data-ttu-id="a6dad-274">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="a6dad-274">**Remove**</span></span>  
 <span data-ttu-id="a6dad-275">Удалить выбранный командный файл.</span><span class="sxs-lookup"><span data-stu-id="a6dad-275">Remove the selected command file.</span></span>  
  
 <span data-ttu-id="a6dad-276">**Вверх**</span><span class="sxs-lookup"><span data-stu-id="a6dad-276">**Move Up**</span></span>  
 <span data-ttu-id="a6dad-277">Переместить выбранный командный файл вверх.</span><span class="sxs-lookup"><span data-stu-id="a6dad-277">Move the selected command file up.</span></span>  
  
 <span data-ttu-id="a6dad-278">**Вниз**</span><span class="sxs-lookup"><span data-stu-id="a6dad-278">**Move Down**</span></span>  
 <span data-ttu-id="a6dad-279">Переместить выбранный командный файл вниз.</span><span class="sxs-lookup"><span data-stu-id="a6dad-279">Move the selected command file down.</span></span>  
  
### <a name="data-sources-tab"></a><span data-ttu-id="a6dad-280">Вкладка «Источники данных»</span><span class="sxs-lookup"><span data-stu-id="a6dad-280">Data Sources Tab</span></span>  
 <span data-ttu-id="a6dad-281">На этой вкладке можно просмотреть источники данных, заданные для пакета.</span><span class="sxs-lookup"><span data-stu-id="a6dad-281">View the data sources specified in the package on this tab.</span></span>  
  
 <span data-ttu-id="a6dad-282">**Диспетчер соединений**</span><span class="sxs-lookup"><span data-stu-id="a6dad-282">**Connection Manager**</span></span>  
 <span data-ttu-id="a6dad-283">Просмотр имени источника данных.</span><span class="sxs-lookup"><span data-stu-id="a6dad-283">View the name of the data source.</span></span>  
  
 <span data-ttu-id="a6dad-284">**Описание**</span><span class="sxs-lookup"><span data-stu-id="a6dad-284">**Description**</span></span>  
 <span data-ttu-id="a6dad-285">Позволяет просмотреть описание источника данных.</span><span class="sxs-lookup"><span data-stu-id="a6dad-285">View the description of the data source.</span></span>  
  
 <span data-ttu-id="a6dad-286">**Строка подключения**</span><span class="sxs-lookup"><span data-stu-id="a6dad-286">**Connection String**</span></span>  
 <span data-ttu-id="a6dad-287">Позволяет просмотреть строку соединения к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="a6dad-287">View the connection string for the data source.</span></span>  
  
### <a name="execution-options-tab"></a><span data-ttu-id="a6dad-288">Вкладка «Параметры выполнения»</span><span class="sxs-lookup"><span data-stu-id="a6dad-288">Execution Options Tab</span></span>  
 <span data-ttu-id="a6dad-289">На этой вкладке можно просмотреть или изменить параметры выполнения пакета.</span><span class="sxs-lookup"><span data-stu-id="a6dad-289">View or change the execution options for the package on this tab.</span></span>  
  
 <span data-ttu-id="a6dad-290">**Завершить работу с ошибкой при предупреждениях проверки**</span><span class="sxs-lookup"><span data-stu-id="a6dad-290">**Fail package on validation warnings**</span></span>  
 <span data-ttu-id="a6dad-291">Выберите этот параметр для остановки выполнения пакета в случае появления предупреждений проверки.</span><span class="sxs-lookup"><span data-stu-id="a6dad-291">Select this option for package execution to fail if validation warnings occur.</span></span>  
  
 <span data-ttu-id="a6dad-292">**Проверить пакет без выполнения**</span><span class="sxs-lookup"><span data-stu-id="a6dad-292">**Validate package without executing**</span></span>  
 <span data-ttu-id="a6dad-293">Выберите этот параметр для проверки на данном шаге задания без выполнения этого пакета.</span><span class="sxs-lookup"><span data-stu-id="a6dad-293">Select this option for the job step to validate, but not execute, the package.</span></span>  
  
 <span data-ttu-id="a6dad-294">**Максимальное число одновременно исполняемых объектов**</span><span class="sxs-lookup"><span data-stu-id="a6dad-294">**Maximum concurrent executables**</span></span>  
 <span data-ttu-id="a6dad-295">Максимальное число исполняемых файлов, которые могут быть запущены одновременно.</span><span class="sxs-lookup"><span data-stu-id="a6dad-295">Maximum number of executable files that can run at one time.</span></span>  
  
 <span data-ttu-id="a6dad-296">**Включить контрольные точки пакета**</span><span class="sxs-lookup"><span data-stu-id="a6dad-296">**Enable package checkpoints**</span></span>  
 <span data-ttu-id="a6dad-297">Выберите этот параметр, чтобы использовать контрольные точки пакета на данном шаге задания.</span><span class="sxs-lookup"><span data-stu-id="a6dad-297">Select this option for the job step to use package checkpoints.</span></span>  
  
 <span data-ttu-id="a6dad-298">**Файл контрольных точек**</span><span class="sxs-lookup"><span data-stu-id="a6dad-298">**Checkpoint file**</span></span>  
 <span data-ttu-id="a6dad-299">Введите имя файла контрольных точек пакета.</span><span class="sxs-lookup"><span data-stu-id="a6dad-299">Type the name of the package checkpoint file.</span></span>  
  
 <span data-ttu-id="a6dad-300">**...**</span><span class="sxs-lookup"><span data-stu-id="a6dad-300">**...**</span></span>  
 <span data-ttu-id="a6dad-301">Позволяет выполнить обзор для поиска файла контрольных точек пакета.</span><span class="sxs-lookup"><span data-stu-id="a6dad-301">Browse to find the package checkpoint file.</span></span>  
  
 <span data-ttu-id="a6dad-302">**Переопределить режим перезапуска**</span><span class="sxs-lookup"><span data-stu-id="a6dad-302">**Override restart options**</span></span>  
 <span data-ttu-id="a6dad-303">Выберите этот параметр, чтобы указать параметры перезапуска данного шага задания, отличные от параметров перезапуска, указанных для пакета.</span><span class="sxs-lookup"><span data-stu-id="a6dad-303">Select this option to specify restart options for this job step that are different from the restart options specified in the package.</span></span>  
  
 <span data-ttu-id="a6dad-304">**Параметр перезапуска**</span><span class="sxs-lookup"><span data-stu-id="a6dad-304">**Restart option**</span></span>  
 <span data-ttu-id="a6dad-305">Выберите действие, выполняемое при перезапуске пакета.</span><span class="sxs-lookup"><span data-stu-id="a6dad-305">Select the action to take when the package restarts.</span></span>  
  
### <a name="logging-tab"></a><span data-ttu-id="a6dad-306">Вкладка «Регистрация»</span><span class="sxs-lookup"><span data-stu-id="a6dad-306">Logging Tab</span></span>  
 <span data-ttu-id="a6dad-307">На этой вкладке можно просмотреть или изменить регистраторы для пакета.</span><span class="sxs-lookup"><span data-stu-id="a6dad-307">View or change the log providers for the package on this tab.</span></span>  
  
 <span data-ttu-id="a6dad-308">**Регистратор**</span><span class="sxs-lookup"><span data-stu-id="a6dad-308">**Log Provider**</span></span>  
 <span data-ttu-id="a6dad-309">Выберите идентификатор ClassID регистратора.</span><span class="sxs-lookup"><span data-stu-id="a6dad-309">Select the ClassID for the log provider.</span></span>  
  
 <span data-ttu-id="a6dad-310">**Строка конфигурации**</span><span class="sxs-lookup"><span data-stu-id="a6dad-310">**Configuration String**</span></span>  
 <span data-ttu-id="a6dad-311">Введите строку конфигурации для регистратора.</span><span class="sxs-lookup"><span data-stu-id="a6dad-311">Type the configuration string for the log provider.</span></span>  
  
 <span data-ttu-id="a6dad-312">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="a6dad-312">**Remove**</span></span>  
 <span data-ttu-id="a6dad-313">Удаляет регистратор.</span><span class="sxs-lookup"><span data-stu-id="a6dad-313">Removes the log provider.</span></span>  
  
### <a name="set-values-tab"></a><span data-ttu-id="a6dad-314">Вкладка «Установка значений»</span><span class="sxs-lookup"><span data-stu-id="a6dad-314">Set Values Tab</span></span>  
 <span data-ttu-id="a6dad-315">На этой вкладке можно просмотреть или изменить значения свойств пакета.</span><span class="sxs-lookup"><span data-stu-id="a6dad-315">View or change property values for the package on this tab.</span></span>  
  
 <span data-ttu-id="a6dad-316">**Путь к свойству**</span><span class="sxs-lookup"><span data-stu-id="a6dad-316">**Property path**</span></span>  
 <span data-ttu-id="a6dad-317">Позволяет просмотреть или изменить путь к свойству.</span><span class="sxs-lookup"><span data-stu-id="a6dad-317">View or change the path for the property.</span></span>  
  
 <span data-ttu-id="a6dad-318">**Значение**</span><span class="sxs-lookup"><span data-stu-id="a6dad-318">**Value**</span></span>  
 <span data-ttu-id="a6dad-319">Позволяет просмотреть или изменить значение свойства.</span><span class="sxs-lookup"><span data-stu-id="a6dad-319">View or change the value for the property.</span></span>  
  
 <span data-ttu-id="a6dad-320">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="a6dad-320">**Remove**</span></span>  
 <span data-ttu-id="a6dad-321">Позволяет удалить свойство.</span><span class="sxs-lookup"><span data-stu-id="a6dad-321">Removes the property.</span></span>  
  
### <a name="verification-tab"></a><span data-ttu-id="a6dad-322">Вкладка «Проверка»</span><span class="sxs-lookup"><span data-stu-id="a6dad-322">Verification Tab</span></span>  
 <span data-ttu-id="a6dad-323">На этой вкладке можно выбрать параметры проверки для данного шага задания.</span><span class="sxs-lookup"><span data-stu-id="a6dad-323">Select the verification options for the job step on this tab.</span></span>  
  
 <span data-ttu-id="a6dad-324">**Выполнять только подписанные пакеты**</span><span class="sxs-lookup"><span data-stu-id="a6dad-324">**Execute only signed packages**</span></span>  
 <span data-ttu-id="a6dad-325">Позволяет запускать только подписанные пакеты.</span><span class="sxs-lookup"><span data-stu-id="a6dad-325">Run only packages that have been signed.</span></span> <span data-ttu-id="a6dad-326">При выборе этого параметра шаг задания выдаст сбой в случае неподписанного пакета.</span><span class="sxs-lookup"><span data-stu-id="a6dad-326">When this option is selected, the job step fails if the package is unsigned.</span></span>  
  
 <span data-ttu-id="a6dad-327">**Проверка сборки пакета**</span><span class="sxs-lookup"><span data-stu-id="a6dad-327">**Verify package build**</span></span>  
 <span data-ttu-id="a6dad-328">Позволяет запускать только пакеты с определенным номером сборки.</span><span class="sxs-lookup"><span data-stu-id="a6dad-328">Run only packages with a specific build number.</span></span> <span data-ttu-id="a6dad-329">При выборе этого параметра шаг задания выдаст сбой в случае несоответствия номера сборки пакета указанному.</span><span class="sxs-lookup"><span data-stu-id="a6dad-329">When this option is selected, the job step fails if the package does not have the specified build number.</span></span>  
  
 <span data-ttu-id="a6dad-330">**Сборка**</span><span class="sxs-lookup"><span data-stu-id="a6dad-330">**Build**</span></span>  
 <span data-ttu-id="a6dad-331">Введите номер сборки пакета.</span><span class="sxs-lookup"><span data-stu-id="a6dad-331">Type the build number of the package.</span></span>  
  
 <span data-ttu-id="a6dad-332">**Проверить идентификатор пакета**</span><span class="sxs-lookup"><span data-stu-id="a6dad-332">**Verify package ID**</span></span>  
 <span data-ttu-id="a6dad-333">Позволяет запускать только пакеты с определенным идентификатором.</span><span class="sxs-lookup"><span data-stu-id="a6dad-333">Run only packages with a specific ID.</span></span> <span data-ttu-id="a6dad-334">При выборе этого параметра шаг задания сформирует ошибку в случае отсутствия у пакета указанного идентификатора.</span><span class="sxs-lookup"><span data-stu-id="a6dad-334">When this option is selected, the job step fails if the package does not have the specified ID.</span></span>  
  
 <span data-ttu-id="a6dad-335">**Идентификатор пакета**</span><span class="sxs-lookup"><span data-stu-id="a6dad-335">**Package ID**</span></span>  
 <span data-ttu-id="a6dad-336">Введите идентификатор пакета.</span><span class="sxs-lookup"><span data-stu-id="a6dad-336">Type the package ID.</span></span>  
  
 <span data-ttu-id="a6dad-337">**Проверить идентификатор версии**</span><span class="sxs-lookup"><span data-stu-id="a6dad-337">**Verify version ID**</span></span>  
 <span data-ttu-id="a6dad-338">Позволяет запускать только пакеты с определенным идентификатором версии.</span><span class="sxs-lookup"><span data-stu-id="a6dad-338">Run only packages with a specific version ID.</span></span> <span data-ttu-id="a6dad-339">При выборе этого параметра шаг задания сформирует ошибку в случае отсутствия у пакета указанного идентификатора версии.</span><span class="sxs-lookup"><span data-stu-id="a6dad-339">When this option is selected, the job step fails if the package does not have the specified version ID.</span></span>  
  
 <span data-ttu-id="a6dad-340">**Идентификатор версии**</span><span class="sxs-lookup"><span data-stu-id="a6dad-340">**Version ID**</span></span>  
 <span data-ttu-id="a6dad-341">Введите идентификатор версии.</span><span class="sxs-lookup"><span data-stu-id="a6dad-341">Type the version ID.</span></span>  
  
### <a name="command-line-tab"></a><span data-ttu-id="a6dad-342">Вкладка «Командная строка»</span><span class="sxs-lookup"><span data-stu-id="a6dad-342">Command Line Tab</span></span>  
 <span data-ttu-id="a6dad-343">Позволяет задать параметры командной строки для пакета.</span><span class="sxs-lookup"><span data-stu-id="a6dad-343">Specify command-line options for the package.</span></span> <span data-ttu-id="a6dad-344">При выборе этой вкладки доступны следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="a6dad-344">The following options are available when this tab is selected.</span></span>  
  
 <span data-ttu-id="a6dad-345">**Восстановить первоначальные значения параметров**</span><span class="sxs-lookup"><span data-stu-id="a6dad-345">**Restore the original options**</span></span>  
 <span data-ttu-id="a6dad-346">Позволяет использовать параметры командной строки, установленные в этом диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="a6dad-346">Use the command-line options set in this dialog.</span></span>  
  
 <span data-ttu-id="a6dad-347">**Изменить командную строку вручную**</span><span class="sxs-lookup"><span data-stu-id="a6dad-347">**Edit the command line manually**</span></span>  
 <span data-ttu-id="a6dad-348">Позволяет задать параметры в окне командной строки.</span><span class="sxs-lookup"><span data-stu-id="a6dad-348">Specify options in the command-line window.</span></span>  
  
 <span data-ttu-id="a6dad-349">**Командная строка**</span><span class="sxs-lookup"><span data-stu-id="a6dad-349">**Command line**</span></span>  
 <span data-ttu-id="a6dad-350">Введите параметры командной строки для использования в данном пакете.</span><span class="sxs-lookup"><span data-stu-id="a6dad-350">Type the command line options to use for this package.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6dad-351">См. также:</span><span class="sxs-lookup"><span data-stu-id="a6dad-351">See Also</span></span>  
 <span data-ttu-id="a6dad-352">[Управление шагами задания](manage-job-steps.md) </span><span class="sxs-lookup"><span data-stu-id="a6dad-352">[Manage Job Steps](manage-job-steps.md) </span></span>  
 <span data-ttu-id="a6dad-353">[Задания агент SQL Server для пакетов](../../integration-services/packages/sql-server-agent-jobs-for-packages.md) </span><span class="sxs-lookup"><span data-stu-id="a6dad-353">[SQL Server Agent Jobs for Packages](../../integration-services/packages/sql-server-agent-jobs-for-packages.md) </span></span>  
 [<span data-ttu-id="a6dad-354">Администрирование агента репликации</span><span class="sxs-lookup"><span data-stu-id="a6dad-354">Replication Agent Administration</span></span>](../../relational-databases/replication/agents/replication-agent-administration.md)  
  
  
