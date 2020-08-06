---
title: 'Свойства шага задания: новый шаг задания (страница "Дополнительно") | Документация Майкрософт'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.job.stepadvanced.f1
ms.assetid: bdecfd4f-bcd8-4ba2-8ada-fbb636314f40
author: stevestein
ms.author: sstein
ms.openlocfilehash: 42820ffbdbb89261e839b5d1011f3a91b5841c86
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737427"
---
# <a name="job-step-properties-new-job-step-advanced-page"></a><span data-ttu-id="833c0-102">Свойства шага задания: создание шага задания (страница "Расширенные")</span><span class="sxs-lookup"><span data-stu-id="833c0-102">Job Step Properties: New Job Step (Advanced Page)</span></span>
  <span data-ttu-id="833c0-103">Эта страница используется для просмотра и изменения свойств [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] шага задания агента.</span><span class="sxs-lookup"><span data-stu-id="833c0-103">Use this page to view and change the properties of a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job step.</span></span>  
  
## <a name="options"></a><span data-ttu-id="833c0-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="833c0-104">Options</span></span>  
 <span data-ttu-id="833c0-105">**Действие при успехе**</span><span class="sxs-lookup"><span data-stu-id="833c0-105">**On success action**</span></span>  
 <span data-ttu-id="833c0-106">Устанавливается действие, выполняемое агентом сервера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] при успешном завершении шага задания.</span><span class="sxs-lookup"><span data-stu-id="833c0-106">Sets the action for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to perform if the job step succeeds.</span></span>  
  
 <span data-ttu-id="833c0-107">**Повторные попытки**</span><span class="sxs-lookup"><span data-stu-id="833c0-107">**Retry attempts**</span></span>  
 <span data-ttu-id="833c0-108">Устанавливается количество повторных попыток агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] выполнить неудачно завершившийся шаг задания.</span><span class="sxs-lookup"><span data-stu-id="833c0-108">Sets the number of times that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent attempts to retry a failed job step.</span></span>  
  
 <span data-ttu-id="833c0-109">**Интервал повтора (в минутах)**</span><span class="sxs-lookup"><span data-stu-id="833c0-109">**Retry interval (minutes)**</span></span>  
 <span data-ttu-id="833c0-110">Устанавливается интервал времени ожидания агентом сервера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] между последовательными повторными попытками.</span><span class="sxs-lookup"><span data-stu-id="833c0-110">Sets the amount of time for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to wait between retry attempts.</span></span>  
  
 <span data-ttu-id="833c0-111">**Действие при ошибке**</span><span class="sxs-lookup"><span data-stu-id="833c0-111">**On failure action**</span></span>  
 <span data-ttu-id="833c0-112">Устанавливается действие, выполняемое агентом сервера [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] при неудачном завершении шага задания.</span><span class="sxs-lookup"><span data-stu-id="833c0-112">Sets the action for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to perform if the job step fails.</span></span>  
  
## <a name="options-for-transact-sql-job-steps"></a><span data-ttu-id="833c0-113">Параметры для шагов задания языка Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="833c0-113">Options for Transact-SQL Job Steps</span></span>  
 <span data-ttu-id="833c0-114">**Выходной файл**</span><span class="sxs-lookup"><span data-stu-id="833c0-114">**Output file**</span></span>  
 <span data-ttu-id="833c0-115">Устанавливается файл, используемый для вывода из шага задания.</span><span class="sxs-lookup"><span data-stu-id="833c0-115">Sets the file to use for output from the job step.</span></span> <span data-ttu-id="833c0-116">Этот параметр доступен только членам предопределенной роли сервера **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="833c0-116">This option is available only to members of the **sysadmin** fixed server role.</span></span>  
  
 <span data-ttu-id="833c0-117">**...**</span><span class="sxs-lookup"><span data-stu-id="833c0-117">**...**</span></span>  
 <span data-ttu-id="833c0-118">Перейдите к файлу, используемому для вывода из шага задания.</span><span class="sxs-lookup"><span data-stu-id="833c0-118">Browse to the file to use for output from the job step.</span></span>  
  
 <span data-ttu-id="833c0-119">**Просмотр**</span><span class="sxs-lookup"><span data-stu-id="833c0-119">**View**</span></span>  
 <span data-ttu-id="833c0-120">В [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Эта кнопка отключена для просмотра выходных файлов.</span><span class="sxs-lookup"><span data-stu-id="833c0-120">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], this button is disabled for viewing output files.</span></span> <span data-ttu-id="833c0-121">Вместо этого для просмотра выходных файлов шага задания используйте приложение «Блокнот».</span><span class="sxs-lookup"><span data-stu-id="833c0-121">Instead, use Notepad to view job step output files.</span></span>  
  
 <span data-ttu-id="833c0-122">**Дописать выходные данные в существующий файл**</span><span class="sxs-lookup"><span data-stu-id="833c0-122">**Append output to existing file**</span></span>  
 <span data-ttu-id="833c0-123">Выходные данные добавляются к существующему содержимому таблицы.</span><span class="sxs-lookup"><span data-stu-id="833c0-123">Append output to the existing contents of the file.</span></span> <span data-ttu-id="833c0-124">В противном случае содержимое файла переписывается каждый раз при выполнении шага задания.</span><span class="sxs-lookup"><span data-stu-id="833c0-124">Otherwise, the previous file contents are overwritten each time the job step runs.</span></span>  
  
 <span data-ttu-id="833c0-125">**Сохранять данные журнала в таблице**</span><span class="sxs-lookup"><span data-stu-id="833c0-125">**Log to table**</span></span>  
 <span data-ttu-id="833c0-126">Записывает выходные данные шага задания в таблицу **sysjobstepslogs** базы данных **msdb** .</span><span class="sxs-lookup"><span data-stu-id="833c0-126">Logs job step output to the **sysjobstepslogs** table in the **msdb** database.</span></span>  
  
 <span data-ttu-id="833c0-127">**Просмотр**</span><span class="sxs-lookup"><span data-stu-id="833c0-127">**View**</span></span>  
 <span data-ttu-id="833c0-128">После того как шаг задания выполнится хотя бы раз, нажмите кнопку **Просмотр** для просмотра его выходных данных в таблице.</span><span class="sxs-lookup"><span data-stu-id="833c0-128">After the job step has run at least once, click **View** to view its output in the table.</span></span>  
  
 <span data-ttu-id="833c0-129">**Дописать выходные данные в существующую запись в таблице**</span><span class="sxs-lookup"><span data-stu-id="833c0-129">**Append output to existing entry in table**</span></span>  
 <span data-ttu-id="833c0-130">Выходные данные добавляются к существующему содержимому таблицы.</span><span class="sxs-lookup"><span data-stu-id="833c0-130">Appends output to the existing contents of the table.</span></span> <span data-ttu-id="833c0-131">В противном случае содержимое таблицы переписывается каждый раз при выполнении шага задания.</span><span class="sxs-lookup"><span data-stu-id="833c0-131">Otherwise, the previous table contents are overwritten each time the job step runs.</span></span>  
  
 <span data-ttu-id="833c0-132">**Включить в журнал выходные данные шага**</span><span class="sxs-lookup"><span data-stu-id="833c0-132">**Include step output in history**</span></span>  
 <span data-ttu-id="833c0-133">Выберите этот параметр для включения вывода из шага задания в журнал заданий.</span><span class="sxs-lookup"><span data-stu-id="833c0-133">Select this option to include output from the job step in the job history.</span></span>  
  
 <span data-ttu-id="833c0-134">**Выполнять от имени**</span><span class="sxs-lookup"><span data-stu-id="833c0-134">**Run as user**</span></span>  
 <span data-ttu-id="833c0-135">Если пользователь является членом предопределенной роли сервера **sysadmin** , он может выбрать другое имя входа SQL для выполнения этого шага задания.</span><span class="sxs-lookup"><span data-stu-id="833c0-135">If you are a member of the **sysadmin** fixed server role, you can select another SQL login to run this job step.</span></span>  
  
## <a name="options-for-operating-system-cmdexec-job-steps"></a><span data-ttu-id="833c0-136">Параметры для шагов задания операционной системы (CmdExec)</span><span class="sxs-lookup"><span data-stu-id="833c0-136">Options for Operating System (CmdExec) Job Steps</span></span>  
 <span data-ttu-id="833c0-137">**Выходной файл**</span><span class="sxs-lookup"><span data-stu-id="833c0-137">**Output file**</span></span>  
 <span data-ttu-id="833c0-138">Устанавливается файл, используемый для вывода из шага задания.</span><span class="sxs-lookup"><span data-stu-id="833c0-138">Sets the file to use for output from the job step.</span></span>  
  
 <span data-ttu-id="833c0-139">**...**</span><span class="sxs-lookup"><span data-stu-id="833c0-139">**...**</span></span>  
 <span data-ttu-id="833c0-140">Перейдите к файлу, используемому для вывода из шага задания.</span><span class="sxs-lookup"><span data-stu-id="833c0-140">Browse to the file to use for output from the job step.</span></span>  
  
 <span data-ttu-id="833c0-141">**Просмотр**</span><span class="sxs-lookup"><span data-stu-id="833c0-141">**View**</span></span>  
 <span data-ttu-id="833c0-142">В [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Эта кнопка отключена для просмотра выходных файлов.</span><span class="sxs-lookup"><span data-stu-id="833c0-142">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], this button is disabled for viewing output files.</span></span> <span data-ttu-id="833c0-143">Вместо этого для просмотра выходных файлов шага задания используйте приложение «Блокнот».</span><span class="sxs-lookup"><span data-stu-id="833c0-143">Instead, use Notepad to view job step output files.</span></span>  
  
 <span data-ttu-id="833c0-144">**Дописать выходные данные в существующий файл**</span><span class="sxs-lookup"><span data-stu-id="833c0-144">**Append output to existing file**</span></span>  
 <span data-ttu-id="833c0-145">При каждом выполнении шага задания его вывод добавляется к имеющемуся содержимому файла.</span><span class="sxs-lookup"><span data-stu-id="833c0-145">Appends the job step output to the previous file contents each time it runs.</span></span>  
  
 <span data-ttu-id="833c0-146">**Сохранять данные журнала в таблице**</span><span class="sxs-lookup"><span data-stu-id="833c0-146">**Log to table**</span></span>  
 <span data-ttu-id="833c0-147">Записывает выходные данные шага задания в таблицу **sysjobstepslogs** базы данных **msdb** .</span><span class="sxs-lookup"><span data-stu-id="833c0-147">Logs job step output to the **sysjobstepslogs** table in the **msdb** database.</span></span>  
  
 <span data-ttu-id="833c0-148">**Просмотр**</span><span class="sxs-lookup"><span data-stu-id="833c0-148">**View**</span></span>  
 <span data-ttu-id="833c0-149">После того как шаг задания выполнится хотя бы раз, нажмите кнопку **Просмотр** для просмотра его выходных данных в таблице.</span><span class="sxs-lookup"><span data-stu-id="833c0-149">After the job step has run at least once, click **View** to view its output in the table.</span></span>  
  
 <span data-ttu-id="833c0-150">**Дописать выходные данные в существующую запись в таблице**</span><span class="sxs-lookup"><span data-stu-id="833c0-150">**Append output to existing entry in table**</span></span>  
 <span data-ttu-id="833c0-151">Выходные данные добавляются к существующему содержимому таблицы.</span><span class="sxs-lookup"><span data-stu-id="833c0-151">Appends output to the existing contents of the table.</span></span> <span data-ttu-id="833c0-152">В противном случае содержимое таблицы переписывается каждый раз при выполнении шага задания.</span><span class="sxs-lookup"><span data-stu-id="833c0-152">Otherwise, the previous table contents are overwritten each time the job step runs.</span></span>  
  
 <span data-ttu-id="833c0-153">**Включить в журнал выходные данные шага**</span><span class="sxs-lookup"><span data-stu-id="833c0-153">**Include step output in history**</span></span>  
 <span data-ttu-id="833c0-154">Выберите этот параметр для включения вывода из шага задания в журнал заданий.</span><span class="sxs-lookup"><span data-stu-id="833c0-154">Select this option to include output from the job step in the job history.</span></span>  
  
## <a name="options-for-powershell-job-steps"></a><span data-ttu-id="833c0-155">Параметры для шагов задания языка PowerShell</span><span class="sxs-lookup"><span data-stu-id="833c0-155">Options for PowerShell Job Steps</span></span>  
 <span data-ttu-id="833c0-156">**Выходной файл**</span><span class="sxs-lookup"><span data-stu-id="833c0-156">**Output file**</span></span>  
 <span data-ttu-id="833c0-157">Устанавливается файл, используемый для вывода из шага задания.</span><span class="sxs-lookup"><span data-stu-id="833c0-157">Sets the file to use for output from the job step.</span></span>  
  
 <span data-ttu-id="833c0-158">**...**</span><span class="sxs-lookup"><span data-stu-id="833c0-158">**...**</span></span>  
 <span data-ttu-id="833c0-159">Перейдите к файлу, используемому для вывода из шага задания.</span><span class="sxs-lookup"><span data-stu-id="833c0-159">Browse to the file to use for output from the job step.</span></span>  
  
 <span data-ttu-id="833c0-160">**Просмотр**</span><span class="sxs-lookup"><span data-stu-id="833c0-160">**View**</span></span>  
 <span data-ttu-id="833c0-161">В [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Эта кнопка отключена для просмотра выходных файлов.</span><span class="sxs-lookup"><span data-stu-id="833c0-161">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], this button is disabled for viewing output files.</span></span> <span data-ttu-id="833c0-162">Вместо этого для просмотра выходных файлов шага задания используйте приложение «Блокнот».</span><span class="sxs-lookup"><span data-stu-id="833c0-162">Instead, use Notepad to view job step output files.</span></span>  
  
 <span data-ttu-id="833c0-163">**Дописать выходные данные в существующий файл**</span><span class="sxs-lookup"><span data-stu-id="833c0-163">**Append output to existing file**</span></span>  
 <span data-ttu-id="833c0-164">При каждом выполнении шага задания его вывод добавляется к имеющемуся содержимому файла.</span><span class="sxs-lookup"><span data-stu-id="833c0-164">Appends the job step output to the previous file contents each time it runs.</span></span>  
  
 <span data-ttu-id="833c0-165">**Сохранять данные журнала в таблице**</span><span class="sxs-lookup"><span data-stu-id="833c0-165">**Log to table**</span></span>  
 <span data-ttu-id="833c0-166">Записывает выходные данные шага задания в таблицу **sysjobstepslogs** базы данных **msdb** .</span><span class="sxs-lookup"><span data-stu-id="833c0-166">Logs job step output to the **sysjobstepslogs** table in the **msdb** database.</span></span>  
  
 <span data-ttu-id="833c0-167">**Просмотр**</span><span class="sxs-lookup"><span data-stu-id="833c0-167">**View**</span></span>  
 <span data-ttu-id="833c0-168">После того как шаг задания выполнится хотя бы раз, нажмите кнопку **Просмотр** для просмотра его выходных данных в таблице.</span><span class="sxs-lookup"><span data-stu-id="833c0-168">After the job step has run at least once, click **View** to view its output in the table.</span></span>  
  
 <span data-ttu-id="833c0-169">**Дописать выходные данные в существующую запись в таблице**</span><span class="sxs-lookup"><span data-stu-id="833c0-169">**Append output to existing entry in table**</span></span>  
 <span data-ttu-id="833c0-170">Выходные данные добавляются к существующему содержимому таблицы.</span><span class="sxs-lookup"><span data-stu-id="833c0-170">Appends output to the existing contents of the table.</span></span> <span data-ttu-id="833c0-171">В противном случае содержимое таблицы переписывается каждый раз при выполнении шага задания.</span><span class="sxs-lookup"><span data-stu-id="833c0-171">Otherwise, the previous table contents are overwritten each time the job step runs.</span></span>  
  
 <span data-ttu-id="833c0-172">**Включить в журнал выходные данные шага**</span><span class="sxs-lookup"><span data-stu-id="833c0-172">**Include step output in history**</span></span>  
 <span data-ttu-id="833c0-173">Выберите этот параметр для включения вывода из шага задания в журнал заданий.</span><span class="sxs-lookup"><span data-stu-id="833c0-173">Select this option to include output from the job step in the job history.</span></span>  
  
## <a name="options-for-replication-queue-reader-job-steps"></a><span data-ttu-id="833c0-174">Параметры шагов заданий для агента чтения очереди репликации</span><span class="sxs-lookup"><span data-stu-id="833c0-174">Options for Replication Queue Reader Job Steps</span></span>  
 <span data-ttu-id="833c0-175">**Server**</span><span class="sxs-lookup"><span data-stu-id="833c0-175">**Server**</span></span>  
 <span data-ttu-id="833c0-176">Устанавливает сервер, чтобы выполнить шаг задания для считывания очереди репликации.</span><span class="sxs-lookup"><span data-stu-id="833c0-176">Sets the server to use for a replication queue reader job step.</span></span>  
  
 <span data-ttu-id="833c0-177">**База данных**</span><span class="sxs-lookup"><span data-stu-id="833c0-177">**Database**</span></span>  
 <span data-ttu-id="833c0-178">Устанавливает базу данных, чтобы выполнить шаг задания для считывания очереди репликации.</span><span class="sxs-lookup"><span data-stu-id="833c0-178">Sets the database to use for a replication queue reader job step.</span></span>  
  
## <a name="options-for-sql-server-analysis-services-job-steps"></a><span data-ttu-id="833c0-179">Параметры для шагов задания служб SQL Server Analysis Services</span><span class="sxs-lookup"><span data-stu-id="833c0-179">Options for SQL Server Analysis Services Job Steps</span></span>  
 <span data-ttu-id="833c0-180">**Выходной файл**</span><span class="sxs-lookup"><span data-stu-id="833c0-180">**Output file**</span></span>  
 <span data-ttu-id="833c0-181">Устанавливается файл, используемый для вывода из шага задания.</span><span class="sxs-lookup"><span data-stu-id="833c0-181">Sets the file to use for output from the job step.</span></span> <span data-ttu-id="833c0-182">Этот параметр доступен только членам предопределенной роли сервера **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="833c0-182">This option is available only to members of the **sysadmin** fixed server role.</span></span>  
  
 <span data-ttu-id="833c0-183">**...**</span><span class="sxs-lookup"><span data-stu-id="833c0-183">**...**</span></span>  
 <span data-ttu-id="833c0-184">Перейдите к файлу, используемому для вывода из шага задания.</span><span class="sxs-lookup"><span data-stu-id="833c0-184">Browse to the file to use for output from the job step.</span></span>  
  
 <span data-ttu-id="833c0-185">**Просмотр**</span><span class="sxs-lookup"><span data-stu-id="833c0-185">**View**</span></span>  
 <span data-ttu-id="833c0-186">В сервере [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]эта кнопка отключена, и просмотр выходных файлов невозможен.</span><span class="sxs-lookup"><span data-stu-id="833c0-186">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], this button is disabled for viewing output files.</span></span> <span data-ttu-id="833c0-187">Вместо этого для просмотра выходных файлов шага задания используйте приложение «Блокнот».</span><span class="sxs-lookup"><span data-stu-id="833c0-187">Instead, use Notepad to view job step output files.</span></span>  
  
 <span data-ttu-id="833c0-188">**Дописать выходные данные в существующий файл**</span><span class="sxs-lookup"><span data-stu-id="833c0-188">**Append output to existing file**</span></span>  
 <span data-ttu-id="833c0-189">Выходные данные добавляются к существующему содержимому таблицы.</span><span class="sxs-lookup"><span data-stu-id="833c0-189">Append output to the existing contents of the file.</span></span> <span data-ttu-id="833c0-190">В противном случае содержимое файла переписывается каждый раз при выполнении шага задания.</span><span class="sxs-lookup"><span data-stu-id="833c0-190">Otherwise, the previous file contents are overwritten each time the job step runs.</span></span>  
  
 <span data-ttu-id="833c0-191">**Сохранять данные журнала в таблице**</span><span class="sxs-lookup"><span data-stu-id="833c0-191">**Log to table**</span></span>  
 <span data-ttu-id="833c0-192">Записывает выходные данные шага задания в таблицу **sysjobstepslogs** базы данных **msdb** .</span><span class="sxs-lookup"><span data-stu-id="833c0-192">Logs job step output to the **sysjobstepslogs** table in the **msdb** database.</span></span>  
  
 <span data-ttu-id="833c0-193">**Просмотр**</span><span class="sxs-lookup"><span data-stu-id="833c0-193">**View**</span></span>  
 <span data-ttu-id="833c0-194">После того как шаг задания выполнится хотя бы раз, нажмите кнопку **Просмотр** для просмотра его выходных данных в таблице.</span><span class="sxs-lookup"><span data-stu-id="833c0-194">After the job step has run at least once, click **View** to view its output in the table.</span></span>  
  
 <span data-ttu-id="833c0-195">**Дописать выходные данные в существующую запись в таблице**</span><span class="sxs-lookup"><span data-stu-id="833c0-195">**Append output to existing entry in table**</span></span>  
 <span data-ttu-id="833c0-196">Выходные данные добавляются к существующему содержимому таблицы.</span><span class="sxs-lookup"><span data-stu-id="833c0-196">Appends output to the existing contents of the table.</span></span> <span data-ttu-id="833c0-197">В противном случае содержимое таблицы переписывается каждый раз при выполнении шага задания.</span><span class="sxs-lookup"><span data-stu-id="833c0-197">Otherwise, the previous table contents are overwritten each time the job step runs.</span></span>  
  
 <span data-ttu-id="833c0-198">**Включить в журнал выходные данные шага**</span><span class="sxs-lookup"><span data-stu-id="833c0-198">**Include step output in history**</span></span>  
 <span data-ttu-id="833c0-199">Выберите этот параметр для включения вывода из шага задания в журнал заданий.</span><span class="sxs-lookup"><span data-stu-id="833c0-199">Select this option to include output from the job step in the job history.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="833c0-200">См. также:</span><span class="sxs-lookup"><span data-stu-id="833c0-200">See Also</span></span>  
 [<span data-ttu-id="833c0-201">Управление шагами задания</span><span class="sxs-lookup"><span data-stu-id="833c0-201">Manage Job Steps</span></span>](manage-job-steps.md)  
  
  
