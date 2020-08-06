---
title: Просмотр и чтение файлов журналов программы установки SQL Server | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- viewing logs
- displaying log files
- Setup [SQL Server], logs
- installation log files [SQL Server]
- installing SQL Server, logs
- errors [SQL Server], Setup
- logs [SQL Server], Setup
ms.assetid: 9d77af64-9084-4375-908a-d90f99535062
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 70f9bbb9a8ed72503dc6fe90077232748b2c4ac2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730885"
---
# <a name="view-and-read-sql-server-setup-log-files"></a><span data-ttu-id="f46c5-102">Просмотр и чтение файлов журналов программы установки SQL Server</span><span class="sxs-lookup"><span data-stu-id="f46c5-102">View and Read SQL Server Setup Log Files</span></span>
  <span data-ttu-id="f46c5-103">При каждом выполнении программы установки создаются файлы журнала с новой папкой журнала с меткой времени в папке% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\ .</span><span class="sxs-lookup"><span data-stu-id="f46c5-103">Each execution of Setup creates log files are created with a new timestamped log folder at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\.</span></span> <span data-ttu-id="f46c5-104">Формат папки журналов с меткой времени — ГГГГММДД_ччммсс.</span><span class="sxs-lookup"><span data-stu-id="f46c5-104">The time-stamped log folder name format is YYYYMMDD_hhmmss.</span></span> <span data-ttu-id="f46c5-105">При запуске программы установке в автоматическом режиме журналы создаются в % temp%\sqlsetup\*.log.</span><span class="sxs-lookup"><span data-stu-id="f46c5-105">When Setup is run in an unattended mode, the logs are created at % temp%\sqlsetup\*.log.</span></span> <span data-ttu-id="f46c5-106">Все файлы в папке журналов архивируются в файле Log\*.cab в соответствующей папке журналов.</span><span class="sxs-lookup"><span data-stu-id="f46c5-106">All files in the logs folder are archived into the Log\*.cab file in their respective log folder.</span></span>  
  
 <span data-ttu-id="f46c5-107">В процессе выполнения запрос программы установки проходит через три фазы:</span><span class="sxs-lookup"><span data-stu-id="f46c5-107">A typical Setup request goes through three execution phases:</span></span>  
  
1.  <span data-ttu-id="f46c5-108">Текстовое содержание глобальных правил</span><span class="sxs-lookup"><span data-stu-id="f46c5-108">Global rules text</span></span>  
  
2.  <span data-ttu-id="f46c5-109">Обновление компонента</span><span class="sxs-lookup"><span data-stu-id="f46c5-109">Component update</span></span>  
  
3.  <span data-ttu-id="f46c5-110">Действие, указанное пользователем</span><span class="sxs-lookup"><span data-stu-id="f46c5-110">User-requested action</span></span>  
  
 <span data-ttu-id="f46c5-111">На каждом этапе программа становки создает подробный и сводный журналы; при этом, если необходимо, создаются дополнительные журналы.</span><span class="sxs-lookup"><span data-stu-id="f46c5-111">In each phase, Setup generates detail and summary logs with additional logs created as appropriate.</span></span> <span data-ttu-id="f46c5-112">Программа установки вызывается по меньшей мере трижды при выполнении каждого указанного пользователем действия по установке.</span><span class="sxs-lookup"><span data-stu-id="f46c5-112">Setup is called at least three times per user-requested Setup action.</span></span>  
  
 <span data-ttu-id="f46c5-113">В файлах хранилища данных содержится моментальный снимок состояния всех объектов конфигурации, отслеживаемых процессом установки; эти файлы могут пригодиться при диагностике ошибок конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f46c5-113">Datastore files contain a snapshot of the state of all configuration objects being tracked by the Setup process, and are useful for troubleshooting configuration errors.</span></span> <span data-ttu-id="f46c5-114">Дампы XML-файлов создаются для объектов хранилища данных в каждой фазе выполнения.</span><span class="sxs-lookup"><span data-stu-id="f46c5-114">XML file dumps are created for datastore objects for each execution phase.</span></span> <span data-ttu-id="f46c5-115">Они сохраняются в собственной подпапке журналов в папке журналов с меткой времени следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f46c5-115">They are saved in their own log subfolder under the time-stamped log folder, as follows:</span></span>  
  
-   <span data-ttu-id="f46c5-116">Datastore_GlobalRules</span><span class="sxs-lookup"><span data-stu-id="f46c5-116">Datastore_GlobalRules</span></span>  
  
-   <span data-ttu-id="f46c5-117">Datastore_ComponentUpdated</span><span class="sxs-lookup"><span data-stu-id="f46c5-117">Datastore_ComponentUpdated</span></span>  
  
-   <span data-ttu-id="f46c5-118">Хранилище данных</span><span class="sxs-lookup"><span data-stu-id="f46c5-118">Datastore</span></span>  
  
 <span data-ttu-id="f46c5-119">В следующих разделах описываются файлы журналов установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f46c5-119">The following sections describe [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup log files.</span></span>  
  
## <a name="summary-text"></a><span data-ttu-id="f46c5-120">Текстовое содержание сводки</span><span class="sxs-lookup"><span data-stu-id="f46c5-120">Summary Text</span></span>  
  
### <a name="overview"></a><span data-ttu-id="f46c5-121">Обзор</span><span class="sxs-lookup"><span data-stu-id="f46c5-121">Overview</span></span>  
 <span data-ttu-id="f46c5-122">В этом файле отображаются компоненты [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , обнаруженные на этапе установки, среда операционной системы, значения параметров командной строки (если указаны) и общее состояние всех выполненных MSI/MSP.</span><span class="sxs-lookup"><span data-stu-id="f46c5-122">This file shows the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components that were detected during Setup, the operating system environment, command-line parameter values if they are specified, and the overall status of each MSI/MSP that was executed.</span></span>  
  
 <span data-ttu-id="f46c5-123">Журнал структурирован с использованием следующих разделов:</span><span class="sxs-lookup"><span data-stu-id="f46c5-123">The log is organized into the following sections:</span></span>  
  
-   <span data-ttu-id="f46c5-124">Общая сводка выполнения</span><span class="sxs-lookup"><span data-stu-id="f46c5-124">An overall summary of the execution</span></span>  
  
-   <span data-ttu-id="f46c5-125">Свойства и конфигурация компьютера, на котором была запущена программа установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f46c5-125">Properties and the configuration of the computer where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup was run</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="f46c5-126">, ранее установленного на компьютере</span><span class="sxs-lookup"><span data-stu-id="f46c5-126">product features previously installed on the computer</span></span>  
  
-   <span data-ttu-id="f46c5-127">Описание версии установки и свойства пакета установки</span><span class="sxs-lookup"><span data-stu-id="f46c5-127">Description of the installation version and installation package properties</span></span>  
  
-   <span data-ttu-id="f46c5-128">Входные параметры среды выполнения, указанные при установке</span><span class="sxs-lookup"><span data-stu-id="f46c5-128">Runtime input settings that are provided during install</span></span>  
  
-   <span data-ttu-id="f46c5-129">Местоположение файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="f46c5-129">Location of the configuration file</span></span>  
  
-   <span data-ttu-id="f46c5-130">Данные о результатах выполнения</span><span class="sxs-lookup"><span data-stu-id="f46c5-130">Details of the execution results</span></span>  
  
-   <span data-ttu-id="f46c5-131">Глобальные правила</span><span class="sxs-lookup"><span data-stu-id="f46c5-131">Global rules</span></span>  
  
-   <span data-ttu-id="f46c5-132">Правила, связанные с определенным сценарием установки</span><span class="sxs-lookup"><span data-stu-id="f46c5-132">Rules specific to the installation scenario</span></span>  
  
-   <span data-ttu-id="f46c5-133">Правила, при выполнении которых произошла ошибка</span><span class="sxs-lookup"><span data-stu-id="f46c5-133">Failed rules</span></span>  
  
-   <span data-ttu-id="f46c5-134">Местоположение файла отчета о выполнении правил</span><span class="sxs-lookup"><span data-stu-id="f46c5-134">Location of the rules report file</span></span>  
  
### <a name="location"></a><span data-ttu-id="f46c5-135">Расположение</span><span class="sxs-lookup"><span data-stu-id="f46c5-135">Location</span></span>  
 <span data-ttu-id="f46c5-136">Он находится в папке% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\ .</span><span class="sxs-lookup"><span data-stu-id="f46c5-136">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\.</span></span>  
  
 <span data-ttu-id="f46c5-137">Чтобы найти ошибки в текстовом файле сводки, воспользуйтесь поиском с ключевыми словами «error» или «failed».</span><span class="sxs-lookup"><span data-stu-id="f46c5-137">To find errors in the summary text file, search the file by using the "error" or "failed" keywords.</span></span>  
  
## <a name="summary_engine-base_yyyymmdd_hhmmsstxt"></a><span data-ttu-id="f46c5-138">Summary_engine-base_YYYYMMDD_HHMMss.txt</span><span class="sxs-lookup"><span data-stu-id="f46c5-138">Summary_engine-base_YYYYMMDD_HHMMss.txt</span></span>  
  
### <a name="overview"></a><span data-ttu-id="f46c5-139">Обзор</span><span class="sxs-lookup"><span data-stu-id="f46c5-139">Overview</span></span>  
 <span data-ttu-id="f46c5-140">Базовый файл summary_engine схож с файлом справки и создается при выполнении основного рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="f46c5-140">The summary_engine base file is similar to the summary file and is generated during the main workflow.</span></span>  
  
### <a name="location"></a><span data-ttu-id="f46c5-141">Расположение</span><span class="sxs-lookup"><span data-stu-id="f46c5-141">Location</span></span>  
 <span data-ttu-id="f46c5-142">Он находится в папке% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="f46c5-142">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="summary_engine-base_yyyymmdd_hhmmss_componentupdatetxt"></a><span data-ttu-id="f46c5-143">Summary_engine-base_YYYYMMDD_HHMMss_ComponentUpdate.txt</span><span class="sxs-lookup"><span data-stu-id="f46c5-143">Summary_engine-base_YYYYMMDD_HHMMss_ComponentUpdate.txt</span></span>  
  
### <a name="overview"></a><span data-ttu-id="f46c5-144">Обзор</span><span class="sxs-lookup"><span data-stu-id="f46c5-144">Overview</span></span>  
 <span data-ttu-id="f46c5-145">Базовый файл summary_engine схож с файлом справки и создается при выполнении основного рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="f46c5-145">The component update summary log file is similar to the summary file and is generated during the component update workflow.</span></span>  
  
### <a name="location"></a><span data-ttu-id="f46c5-146">Расположение</span><span class="sxs-lookup"><span data-stu-id="f46c5-146">Location</span></span>  
 <span data-ttu-id="f46c5-147">Он находится в папке% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="f46c5-147">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="summary_engine-base_versionnumbermmdd_hhmmss_globalrulestxt"></a><span data-ttu-id="f46c5-148">Base_ Summary_engine \<VersionNumber>MMDD_HHMMss_GlobalRules.txt</span><span class="sxs-lookup"><span data-stu-id="f46c5-148">Summary_engine-base_\<VersionNumber>MMDD_HHMMss_GlobalRules.txt</span></span>  
  
### <a name="overview"></a><span data-ttu-id="f46c5-149">Обзор</span><span class="sxs-lookup"><span data-stu-id="f46c5-149">Overview</span></span>  
 <span data-ttu-id="f46c5-150">Файл сводного журнала глобальных правил схож с файлом справки и создается при выполнении рабочего процесса глобальных правил.</span><span class="sxs-lookup"><span data-stu-id="f46c5-150">The global rules summary log file is similar to the summary file generated during the global rules workflow.</span></span>  
  
### <a name="location"></a><span data-ttu-id="f46c5-151">Расположение</span><span class="sxs-lookup"><span data-stu-id="f46c5-151">Location</span></span>  
 <span data-ttu-id="f46c5-152">Он находится в папке% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="f46c5-152">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="detailtxt"></a><span data-ttu-id="f46c5-153">Detail.txt</span><span class="sxs-lookup"><span data-stu-id="f46c5-153">Detail.txt</span></span>  
  
### <a name="overview"></a><span data-ttu-id="f46c5-154">Обзор</span><span class="sxs-lookup"><span data-stu-id="f46c5-154">Overview</span></span>  
 <span data-ttu-id="f46c5-155">Detail.txt создается при выполнении рабочего процесса основных процедур, таких как установка или обновление, и обеспечивает сведения о выполнении.</span><span class="sxs-lookup"><span data-stu-id="f46c5-155">Detail.txt is generated for the main workflow such as install or upgrade, and provides the details of the execution.</span></span> <span data-ttu-id="f46c5-156">Журналы в файле создаются с учетом времени инициации всех действий, связанных с установкой, и указывают на порядок выполнения действий и их зависимости.</span><span class="sxs-lookup"><span data-stu-id="f46c5-156">The logs in the file are generated based on the time when each action for the installation was invoked, and show the order in which the actions were executed, and their dependencies.</span></span>  
  
### <a name="location"></a><span data-ttu-id="f46c5-157">Расположение</span><span class="sxs-lookup"><span data-stu-id="f46c5-157">Location</span></span>  
 <span data-ttu-id="f46c5-158">Он находится в папке% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup</span><span class="sxs-lookup"><span data-stu-id="f46c5-158">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup</span></span>  
  
 <span data-ttu-id="f46c5-159">Bootstrap\Log\\<ГГГГММДД_ЧЧММ>\Detail.txt.</span><span class="sxs-lookup"><span data-stu-id="f46c5-159">Bootstrap\Log\\<YYYYMMDD_HHMM>\Detail.txt.</span></span>  
  
 <span data-ttu-id="f46c5-160">При возникновении ошибки во время процесса установки исключение или ошибка регистрируются в конце этого файла.</span><span class="sxs-lookup"><span data-stu-id="f46c5-160">If an error occurs during the Setup process, the exception or error are logged at the end of this file.</span></span> <span data-ttu-id="f46c5-161">Чтобы найти ошибки в этом файле, сначала проверьте конец файла, а затем воспользуйтесь поиском по файлу с ключевыми словами «ошибка» и «исключение».</span><span class="sxs-lookup"><span data-stu-id="f46c5-161">To find the errors in this file, first examine the end of the file followed by a search of the file for the "error" or "exception" keywords.</span></span>  
  
## <a name="detail_componentupdatetxt"></a><span data-ttu-id="f46c5-162">Detail_ComponentUpdate.txt</span><span class="sxs-lookup"><span data-stu-id="f46c5-162">Detail_ComponentUpdate.txt</span></span>  
  
### <a name="overview"></a><span data-ttu-id="f46c5-163">Обзор</span><span class="sxs-lookup"><span data-stu-id="f46c5-163">Overview</span></span>  
 <span data-ttu-id="f46c5-164">Файл Detail_ComponentUpdate.txt создается для рабочего процесса обновлений компонентов и похож на файл Detail.txt.</span><span class="sxs-lookup"><span data-stu-id="f46c5-164">The Detail_ComponentUpdate.txt file is generated for the component update workflow and is similar to Detail.txt.</span></span>  
  
### <a name="location"></a><span data-ttu-id="f46c5-165">Расположение</span><span class="sxs-lookup"><span data-stu-id="f46c5-165">Location</span></span>  
 <span data-ttu-id="f46c5-166">Он находится в папке% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="f46c5-166">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="detail_globalrulestxt"></a><span data-ttu-id="f46c5-167">Detail_GlobalRules.txt</span><span class="sxs-lookup"><span data-stu-id="f46c5-167">Detail_GlobalRules.txt</span></span>  
  
### <a name="overview"></a><span data-ttu-id="f46c5-168">Обзор</span><span class="sxs-lookup"><span data-stu-id="f46c5-168">Overview</span></span>  
 <span data-ttu-id="f46c5-169">Файл Detail_GlobalRules.txt создается при выполнении глобальных правил и похож на файл Detail.txt.</span><span class="sxs-lookup"><span data-stu-id="f46c5-169">Detail_GlobalRules.txt is generated for the global rules execution and is similar to Detail.txt.</span></span>  
  
### <a name="location"></a><span data-ttu-id="f46c5-170">Расположение</span><span class="sxs-lookup"><span data-stu-id="f46c5-170">Location</span></span>  
 <span data-ttu-id="f46c5-171">Он находится в папке% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="f46c5-171">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="msi-log-files"></a><span data-ttu-id="f46c5-172">Файлы журнала MSI.</span><span class="sxs-lookup"><span data-stu-id="f46c5-172">MSI log files</span></span>  
  
### <a name="overview"></a><span data-ttu-id="f46c5-173">Обзор</span><span class="sxs-lookup"><span data-stu-id="f46c5-173">Overview</span></span>  
 <span data-ttu-id="f46c5-174">В файлах журнала MSI указаны сведения о установке пакетов.</span><span class="sxs-lookup"><span data-stu-id="f46c5-174">The MSI log files provide details of the installation package process.</span></span> <span data-ttu-id="f46c5-175">Они создаются MSIEXEC при установке определенных пакетов.</span><span class="sxs-lookup"><span data-stu-id="f46c5-175">They are generated by the MSIEXEC during the installation of the specified package.</span></span>  
  
 <span data-ttu-id="f46c5-176">Типы файлов журналов MSI:</span><span class="sxs-lookup"><span data-stu-id="f46c5-176">Types of MSI log files:</span></span>  
  
-   <span data-ttu-id="f46c5-177">\<Feature>_\<Architecture>\_\<Interaction>.log</span><span class="sxs-lookup"><span data-stu-id="f46c5-177">\<Feature>_\<Architecture>\_\<Interaction>.log</span></span>  
  
-   <span data-ttu-id="f46c5-178">\<Feature>_\<Architecture>\_\<Language>\_\<Interaction>.log</span><span class="sxs-lookup"><span data-stu-id="f46c5-178">\<Feature>_\<Architecture>\_\<Language>\_\<Interaction>.log</span></span>  
  
-   <span data-ttu-id="f46c5-179">\<Feature>_\<Architecture>\_\<Interaction>\_\<workflow>.log</span><span class="sxs-lookup"><span data-stu-id="f46c5-179">\<Feature>_\<Architecture>\_\<Interaction>\_\<workflow>.log</span></span>  
  
### <a name="location"></a><span data-ttu-id="f46c5-180">Расположение</span><span class="sxs-lookup"><span data-stu-id="f46c5-180">Location</span></span>  
 <span data-ttu-id="f46c5-181">Файлы журнала MSI находятся в папке% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\<Name \> . log.</span><span class="sxs-lookup"><span data-stu-id="f46c5-181">The MSI log files are located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\<Name\>.log.</span></span>  
  
 <span data-ttu-id="f46c5-182">В конце файла приведена сводка выполнения, в которой указываются общее состояние (успешное или ошибка) и свойства.</span><span class="sxs-lookup"><span data-stu-id="f46c5-182">At the end of the file is a summary of the execution which includes the success or failure status and properties.</span></span> <span data-ttu-id="f46c5-183">Для поиска ошибок в файле MSI воспользуйтесь поиском по ключевому выражению «value 3». Обычно ошибки можно найти рядом со строкой.</span><span class="sxs-lookup"><span data-stu-id="f46c5-183">To find the error in the MSI file, search for "value 3" and usually the errors can be found close to the string.</span></span>  
  
## <a name="configurationfileini"></a><span data-ttu-id="f46c5-184">ConfigurationFile.ini</span><span class="sxs-lookup"><span data-stu-id="f46c5-184">ConfigurationFile.ini</span></span>  
  
### <a name="overview"></a><span data-ttu-id="f46c5-185">Обзор</span><span class="sxs-lookup"><span data-stu-id="f46c5-185">Overview</span></span>  
 <span data-ttu-id="f46c5-186">В файле конфигурации содержатся входные параметры, указанные при установке.</span><span class="sxs-lookup"><span data-stu-id="f46c5-186">The configuration file contains the input settings that are provided during installation.</span></span> <span data-ttu-id="f46c5-187">Их можно использовать для повторной установки, что избавит от необходимости их ввода вручную.</span><span class="sxs-lookup"><span data-stu-id="f46c5-187">It can be used to restart the installation without having to enter the settings manually.</span></span> <span data-ttu-id="f46c5-188">Однако пароли учетных записей, PID и некоторые параметры не сохраняются в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f46c5-188">However, passwords for the accounts, PID, and some parameters are not saved in the configuration file.</span></span> <span data-ttu-id="f46c5-189">Параметры могут либо быть добавлены к файлу или указаны с помощью командной строки или пользовательского интерфейса программы установки.</span><span class="sxs-lookup"><span data-stu-id="f46c5-189">The settings can be either added to the file or provided by using the command line or the Setup user interface.</span></span> <span data-ttu-id="f46c5-190">Дополнительные сведения см. [в разделе Install SQL Server 2014 с помощью файла конфигурации](install-sql-server-using-a-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="f46c5-190">For more information, see [Install SQL Server 2014 Using a Configuration File](install-sql-server-using-a-configuration-file.md).</span></span>  
  
### <a name="location"></a><span data-ttu-id="f46c5-191">Расположение</span><span class="sxs-lookup"><span data-stu-id="f46c5-191">Location</span></span>  
 <span data-ttu-id="f46c5-192">Он находится в папке% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="f46c5-192">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="systemconfigurationcheck_reporthtm"></a><span data-ttu-id="f46c5-193">SystemConfigurationCheck_Report.htm</span><span class="sxs-lookup"><span data-stu-id="f46c5-193">SystemConfigurationCheck_Report.htm</span></span>  
  
### <a name="overview"></a><span data-ttu-id="f46c5-194">Обзор</span><span class="sxs-lookup"><span data-stu-id="f46c5-194">Overview</span></span>  
 <span data-ttu-id="f46c5-195">В отчете о проверке конфигурации системы содержится краткое описание всех выполняемых правил и состояния выполнения.</span><span class="sxs-lookup"><span data-stu-id="f46c5-195">The system configuration check report contains a short description for each executed rule, and the execution status.</span></span>  
  
### <a name="location"></a><span data-ttu-id="f46c5-196">Расположение</span><span class="sxs-lookup"><span data-stu-id="f46c5-196">Location</span></span>  
 <span data-ttu-id="f46c5-197">Он находится в папке% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="f46c5-197">It is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f46c5-198">См. также:</span><span class="sxs-lookup"><span data-stu-id="f46c5-198">See Also</span></span>  
 <span data-ttu-id="f46c5-199">[Практические руководства по установке](../../sql-server/install/installation-how-to-topics.md) </span><span class="sxs-lookup"><span data-stu-id="f46c5-199">[Installation How-to Topics](../../sql-server/install/installation-how-to-topics.md) </span></span>  
 [<span data-ttu-id="f46c5-200">Установка SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="f46c5-200">Install SQL Server 2014</span></span>](install-sql-server.md)  
  
  
