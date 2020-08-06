---
title: Требования к распределенное воспроизведение | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 6fffee7d-891f-4d9d-b2c3-dd19855a1c2c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 66be93534756360e722fcccaf405815e14ffa7ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659038"
---
# <a name="distributed-replay-requirements"></a><span data-ttu-id="49cae-102">Distributed Replay Requirements</span><span class="sxs-lookup"><span data-stu-id="49cae-102">Distributed Replay Requirements</span></span>
  <span data-ttu-id="49cae-103">Для использования компонента распределенного воспроизведения [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] необходимо обеспечить выполнение требований, указанных в этой статье.</span><span class="sxs-lookup"><span data-stu-id="49cae-103">Before using the [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay feature, consider the product requirements that are outlined in this topic.</span></span>  
  
## <a name="input-trace-requirements"></a><span data-ttu-id="49cae-104">Требования к входным данным трассировки</span><span class="sxs-lookup"><span data-stu-id="49cae-104">Input Trace Requirements</span></span>  
 <span data-ttu-id="49cae-105">Для успешного воспроизведения данных трассировки они должны соответствовать требованиям к версии и формату и содержать необходимые события и столбцы.</span><span class="sxs-lookup"><span data-stu-id="49cae-105">To successfully replay trace data, it must meet the requirements for version and format, and contain the required events and columns.</span></span>  
  
### <a name="input-trace-versions"></a><span data-ttu-id="49cae-106">Версии входных данных трассировки</span><span class="sxs-lookup"><span data-stu-id="49cae-106">Input Trace Versions</span></span>  
 <span data-ttu-id="49cae-107">Распределенное воспроизведение поддерживает входные данные трассировки, собранные в следующих версиях [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="49cae-107">Distributed Replay supports input trace data that is collected on the following versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]  
  
-   [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]  
  
-   [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]  
  
-   [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]  
  
-   [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]  
  
### <a name="input-trace-formats"></a><span data-ttu-id="49cae-108">Форматы входных данных трассировки</span><span class="sxs-lookup"><span data-stu-id="49cae-108">Input Trace Formats</span></span>  
 <span data-ttu-id="49cae-109">Входные данные трассировки могут предоставляться в любом из следующих форматов:</span><span class="sxs-lookup"><span data-stu-id="49cae-109">The input trace data can be in any of the following formats:</span></span>  
  
-   <span data-ttu-id="49cae-110">Отдельный файл трассировки с расширением `.trc` .</span><span class="sxs-lookup"><span data-stu-id="49cae-110">A single trace file that has the `.trc` extension.</span></span>  
  
-   <span data-ttu-id="49cae-111">Набор файлов продолжения трассировки, соответствующих соглашению об именовании для переключения на файл продолжения, например: `<TraceFile>.trc`, `<TraceFile>_1.trc`, `<TraceFile>_2.trc`, `<TraceFile>_3.trc`, … `<TraceFile>_n.trc`.</span><span class="sxs-lookup"><span data-stu-id="49cae-111">A set of rollover trace files that follow the file rollover naming convention, for example: `<TraceFile>.trc`, `<TraceFile>_1.trc`, `<TraceFile>_2.trc`, `<TraceFile>_3.trc`, ... `<TraceFile>_n.trc`.</span></span>  
  
### <a name="input-trace-events-and-columns"></a><span data-ttu-id="49cae-112">События и столбцы входных данных трассировки</span><span class="sxs-lookup"><span data-stu-id="49cae-112">Input Trace Events and Columns</span></span>  
 <span data-ttu-id="49cae-113">Входные данные трассировки должны содержать определенные события и столбцы, которые воспроизводятся компонентами распределенного воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="49cae-113">The input trace data must contain specific events and columns to be replayed by Distributed Replay.</span></span> <span data-ttu-id="49cae-114">Шаблон **TSQL_Replay** в приложении [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] содержит все необходимые события и столбцы, помимо дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="49cae-114">The **TSQL_Replay** template in [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] contains all of the required events and columns, in addition to extra information.</span></span> <span data-ttu-id="49cae-115">Дополнительные сведения об этом шаблоне см. в разделе [Replay Requirements](../sql-server-profiler/replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49cae-115">For more information about that template, see [Replay Requirements](../sql-server-profiler/replay-requirements.md).</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="49cae-116">Если для записи входных данных трассировки шаблон **TSQL_Replay** не используется или если требования к входным данным трассировки не соблюдены, при воспроизведении могут возникнуть непредвиденные результаты.</span><span class="sxs-lookup"><span data-stu-id="49cae-116">If you do not use the **TSQL_Replay** template to capture the input trace data, or if the input trace requirements are not satisfied, you may receive unexpected replay results.</span></span>  
  
 <span data-ttu-id="49cae-117">Также можно создать пользовательский шаблон трассировки и использовать его для воспроизведения событий в программе распределенного воспроизведения, если он содержит следующие события:</span><span class="sxs-lookup"><span data-stu-id="49cae-117">You can also create a custom trace template and use it to replay events with Distributed Replay, as long as it contains the following events:</span></span>  
  
-   <span data-ttu-id="49cae-118">Аудит входа в систему</span><span class="sxs-lookup"><span data-stu-id="49cae-118">Audit Login</span></span>  
  
-   <span data-ttu-id="49cae-119">Audit Logout</span><span class="sxs-lookup"><span data-stu-id="49cae-119">Audit Logout</span></span>  
  
-   <span data-ttu-id="49cae-120">ExistingConnection</span><span class="sxs-lookup"><span data-stu-id="49cae-120">ExistingConnection</span></span>  
  
-   <span data-ttu-id="49cae-121">RPC Output Parameter</span><span class="sxs-lookup"><span data-stu-id="49cae-121">RPC Output Parameter</span></span>  
  
-   <span data-ttu-id="49cae-122">RPC:Completed</span><span class="sxs-lookup"><span data-stu-id="49cae-122">RPC:Completed</span></span>  
  
-   <span data-ttu-id="49cae-123">RPC:Starting</span><span class="sxs-lookup"><span data-stu-id="49cae-123">RPC:Starting</span></span>  
  
-   <span data-ttu-id="49cae-124">SQL:BatchCompleted</span><span class="sxs-lookup"><span data-stu-id="49cae-124">SQL:BatchCompleted</span></span>  
  
-   <span data-ttu-id="49cae-125">SQL:BatchStarting</span><span class="sxs-lookup"><span data-stu-id="49cae-125">SQL:BatchStarting</span></span>  
  
 <span data-ttu-id="49cae-126">При воспроизведении серверных курсоров также необходимы следующие события:</span><span class="sxs-lookup"><span data-stu-id="49cae-126">If you are replaying server-side cursors, the following events are also required:</span></span>  
  
-   <span data-ttu-id="49cae-127">CursorClose</span><span class="sxs-lookup"><span data-stu-id="49cae-127">CursorClose</span></span>  
  
-   <span data-ttu-id="49cae-128">CursorExecute</span><span class="sxs-lookup"><span data-stu-id="49cae-128">CursorExecute</span></span>  
  
-   <span data-ttu-id="49cae-129">CursorOpen</span><span class="sxs-lookup"><span data-stu-id="49cae-129">CursorOpen</span></span>  
  
-   <span data-ttu-id="49cae-130">CursorPrepare</span><span class="sxs-lookup"><span data-stu-id="49cae-130">CursorPrepare</span></span>  
  
-   <span data-ttu-id="49cae-131">CursorUnprepare</span><span class="sxs-lookup"><span data-stu-id="49cae-131">CursorUnprepare</span></span>  
  
 <span data-ttu-id="49cae-132">При воспроизведении инструкций SQL, подготовленных на сервере, дополнительно необходимы следующие события:</span><span class="sxs-lookup"><span data-stu-id="49cae-132">If you are replaying server-side prepared SQL statements, the following events are also required:</span></span>  
  
-   <span data-ttu-id="49cae-133">Exec Prepared SQL</span><span class="sxs-lookup"><span data-stu-id="49cae-133">Exec Prepared SQL</span></span>  
  
-   <span data-ttu-id="49cae-134">Prepare SQL</span><span class="sxs-lookup"><span data-stu-id="49cae-134">Prepare SQL</span></span>  
  
 <span data-ttu-id="49cae-135">Все входные данные трассировки должны содержать следующие столбцы:</span><span class="sxs-lookup"><span data-stu-id="49cae-135">All input trace data must contain the following columns:</span></span>  
  
-   <span data-ttu-id="49cae-136">Класс событий</span><span class="sxs-lookup"><span data-stu-id="49cae-136">Event Class</span></span>  
  
-   <span data-ttu-id="49cae-137">EventSequence</span><span class="sxs-lookup"><span data-stu-id="49cae-137">EventSequence</span></span>  
  
-   <span data-ttu-id="49cae-138">TextData</span><span class="sxs-lookup"><span data-stu-id="49cae-138">TextData</span></span>  
  
-   <span data-ttu-id="49cae-139">Имя приложения</span><span class="sxs-lookup"><span data-stu-id="49cae-139">Application Name</span></span>  
  
-   <span data-ttu-id="49cae-140">LoginName</span><span class="sxs-lookup"><span data-stu-id="49cae-140">LoginName</span></span>  
  
-   <span data-ttu-id="49cae-141">имя_базы_данных</span><span class="sxs-lookup"><span data-stu-id="49cae-141">DatabaseName</span></span>  
  
-   <span data-ttu-id="49cae-142">Идентификатор базы данных</span><span class="sxs-lookup"><span data-stu-id="49cae-142">Database ID</span></span>  
  
-   <span data-ttu-id="49cae-143">HostName</span><span class="sxs-lookup"><span data-stu-id="49cae-143">HostName</span></span>  
  
-   <span data-ttu-id="49cae-144">Binary Data</span><span class="sxs-lookup"><span data-stu-id="49cae-144">Binary Data</span></span>  
  
-   <span data-ttu-id="49cae-145">SPID</span><span class="sxs-lookup"><span data-stu-id="49cae-145">SPID</span></span>  
  
-   <span data-ttu-id="49cae-146">Время начала</span><span class="sxs-lookup"><span data-stu-id="49cae-146">Start Time</span></span>  
  
-   <span data-ttu-id="49cae-147">EndTime</span><span class="sxs-lookup"><span data-stu-id="49cae-147">EndTime</span></span>  
  
-   <span data-ttu-id="49cae-148">IsSystem</span><span class="sxs-lookup"><span data-stu-id="49cae-148">IsSystem</span></span>  
  
## <a name="supported-input-trace-and-target-server-combinations"></a><span data-ttu-id="49cae-149">Поддерживаемые сочетания входных данных трассировки и целевых серверов</span><span class="sxs-lookup"><span data-stu-id="49cae-149">Supported Input Trace and Target Server Combinations</span></span>  
 <span data-ttu-id="49cae-150">В следующей таблице перечислены поддерживаемые версии данных трассировки и для каждой версии указываются поддерживаемые версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , для которых могут воспроизводиться данные.</span><span class="sxs-lookup"><span data-stu-id="49cae-150">The following table lists the supported versions of trace data, and for each, the supported versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that data can be replayed against.</span></span>  
  
|<span data-ttu-id="49cae-151">Версия входных данных трассировки</span><span class="sxs-lookup"><span data-stu-id="49cae-151">Version of Input Trace Data</span></span>|<span data-ttu-id="49cae-152">Поддерживаемые версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для экземпляра целевого сервера</span><span class="sxs-lookup"><span data-stu-id="49cae-152">Supported Versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for the Target Server Instance</span></span>|  
|---------------------------------|------------------------------------------------------------------------------------|  
|[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]|[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]<span data-ttu-id="49cae-153">, [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49cae-153">, [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]|[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]<span data-ttu-id="49cae-154">, [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49cae-154">, [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="49cae-155">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49cae-155">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|[!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]|[!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]<span data-ttu-id="49cae-156">, [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49cae-156">, [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|[!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]|[!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]|  
  
## <a name="operating-system-requirements"></a><span data-ttu-id="49cae-157">Требования к операционной системе</span><span class="sxs-lookup"><span data-stu-id="49cae-157">Operating System Requirements</span></span>  
 <span data-ttu-id="49cae-158">Для запуска средства администрирования, контроллера и клиентских служб поддерживаются те же операционные системы, что и для экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="49cae-158">Supported operating systems for running the administration tool and the controller and client services is the same as your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="49cae-159">Дополнительные сведения о том, какие операционные системы поддерживаются для вашего [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] экземпляра, см. в разделе [требования к оборудованию и программному обеспечению для установки SQL Server 2014](../../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="49cae-159">For more information about which operating systems are supported for your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance, see [Hardware and Software Requirements for Installing SQL Server 2014](../../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md).</span></span>  
  
 <span data-ttu-id="49cae-160">Компоненты распределенного воспроизведения поддерживаются в операционных системах как для платформы x86, так и для платформы x64.</span><span class="sxs-lookup"><span data-stu-id="49cae-160">Distributed Replay features are supported on both x86-based and x64-based operating systems.</span></span> <span data-ttu-id="49cae-161">Для операционных систем платформы x64 поддерживается только режим Windows on Windows (WOW).</span><span class="sxs-lookup"><span data-stu-id="49cae-161">For x64-based operating systems, only Windows on Windows (WOW) mode is supported.</span></span>  
  
## <a name="installation-limitations"></a><span data-ttu-id="49cae-162">Ограничения на установку</span><span class="sxs-lookup"><span data-stu-id="49cae-162">Installation Limitations</span></span>  
 <span data-ttu-id="49cae-163">На одном компьютере можно устанавливать только один экземпляр компонента распределенного воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="49cae-163">Any one computer can only have a single instance of each Distributed Replay feature installed.</span></span> <span data-ttu-id="49cae-164">В следующей таблице указано, сколько установленных экземпляров каждого компонента допускается в одной среде распределенного воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="49cae-164">The following table lists how many installations of each feature are allowed in a single Distributed Replay environment.</span></span>  
  
|<span data-ttu-id="49cae-165">Компонент распределенного воспроизведения</span><span class="sxs-lookup"><span data-stu-id="49cae-165">Distributed Replay Feature</span></span>|<span data-ttu-id="49cae-166">Максимальное число установленных экземпляров для среды воспроизведения</span><span class="sxs-lookup"><span data-stu-id="49cae-166">Maximum Installations Per Replay Environment</span></span>|  
|--------------------------------|--------------------------------------------------|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="49cae-167">Служба контроллера распределенного воспроизведения</span><span class="sxs-lookup"><span data-stu-id="49cae-167">Distributed Replay controller service</span></span>|<span data-ttu-id="49cae-168">1</span><span class="sxs-lookup"><span data-stu-id="49cae-168">1</span></span>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="49cae-169">Служба клиента распределенного воспроизведения</span><span class="sxs-lookup"><span data-stu-id="49cae-169">Distributed Replay client service</span></span>|<span data-ttu-id="49cae-170">16 (физических или виртуальных компьютеров)</span><span class="sxs-lookup"><span data-stu-id="49cae-170">16 (physical or virtual computers)</span></span>|  
|<span data-ttu-id="49cae-171">Средство администрирования</span><span class="sxs-lookup"><span data-stu-id="49cae-171">Administration tool</span></span>|<span data-ttu-id="49cae-172">Неограниченно</span><span class="sxs-lookup"><span data-stu-id="49cae-172">Unlimited</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="49cae-173">Хотя на одном компьютере можно устанавливать только один экземпляр программы администрирования, допускается одновременный запуск нескольких экземпляров программы администрирования.</span><span class="sxs-lookup"><span data-stu-id="49cae-173">Although only one instance of the administration tool can be installed on a single computer, you can start multiple instances of the administration tool.</span></span> <span data-ttu-id="49cae-174">Команды, поступающие от нескольких экземпляров программы администрирования, разрешаются в порядке поступления.</span><span class="sxs-lookup"><span data-stu-id="49cae-174">Commands issued from multiple administration tools are resolved in the order in which they are received.</span></span>  
  
## <a name="data-access-provider"></a><span data-ttu-id="49cae-175">Поставщик данных</span><span class="sxs-lookup"><span data-stu-id="49cae-175">Data Access Provider</span></span>  
 <span data-ttu-id="49cae-176">Распределенное воспроизведение поддерживает только поставщик ODBC доступа к данным собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="49cae-176">Distributed Replay only supports the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC data access provider.</span></span>  
  
## <a name="target-server-preparation-requirements"></a><span data-ttu-id="49cae-177">Требования к подготовке целевого сервера</span><span class="sxs-lookup"><span data-stu-id="49cae-177">Target Server Preparation Requirements</span></span>  
 <span data-ttu-id="49cae-178">Рекомендуется размещать целевой сервер в среде тестирования.</span><span class="sxs-lookup"><span data-stu-id="49cae-178">We recommend that the target server be located in a test environment.</span></span> <span data-ttu-id="49cae-179">Чтобы воспроизвести данные трассировки на экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , отличном от экземпляра, в котором они были изначально записаны, убедитесь, что для целевого сервера выполняются следующие требования.</span><span class="sxs-lookup"><span data-stu-id="49cae-179">To replay trace data against a different instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] than it was originally recorded, make sure that the following has been done to the target server:</span></span>  
  
-   <span data-ttu-id="49cae-180">Все имена входа и пользователи, содержащиеся в данных трассировки, должны присутствовать на целевом сервере в той же базе данных.</span><span class="sxs-lookup"><span data-stu-id="49cae-180">All logins and users that are contained in the trace data must be present in the same database on the target server.</span></span>  
  
-   <span data-ttu-id="49cae-181">Все имена входа и пользователи на целевом сервере должны обладать теми же разрешениями, которые были у них на исходном сервере.</span><span class="sxs-lookup"><span data-stu-id="49cae-181">All logins and users on the target server must have the same permissions they had on the original server.</span></span>  
  
-   <span data-ttu-id="49cae-182">Желательно, чтобы идентификаторы баз данных на целевом и на исходном серверах совпадали.</span><span class="sxs-lookup"><span data-stu-id="49cae-182">The database IDs on the target ideally should be the same as those on the source.</span></span> <span data-ttu-id="49cae-183">Впрочем, если они не совпадают, соответствие можно установить по параметру **DatabaseName** , если он есть в трассировке.</span><span class="sxs-lookup"><span data-stu-id="49cae-183">However, if they are not the same, matching can be performed based on **DatabaseName** if it is present in the trace.</span></span>  
  
-   <span data-ttu-id="49cae-184">Для каждого имени входа в трассировке должна быть задана база данных по умолчанию, соответствующая целевой базе данных имени входа.</span><span class="sxs-lookup"><span data-stu-id="49cae-184">The default database for each login that is contained in the trace data must be set (on the target server) to the respective target database of the login.</span></span> <span data-ttu-id="49cae-185">Например, на исходном экземпляре **в базе данных**Fred_Db **данные трассировки для воспроизведения содержат операцию для имени входа** Fred [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="49cae-185">For example, the trace data to be replayed contains activity for the login, **Fred**, in the database **Fred_Db** on the original instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="49cae-186">Поэтому на целевом сервере необходимо задать базу данных по умолчанию для имени входа **Fred**, соответствующую базе данных **Fred_Db** (даже если имена баз данных различаются).</span><span class="sxs-lookup"><span data-stu-id="49cae-186">Therefore, on the target server, the default database for the login, **Fred**, must be set to the database that matches **Fred_Db** (even if the database name is different).</span></span> <span data-ttu-id="49cae-187">Базу данных по умолчанию для имени входа можно задать с помощью хранимой процедуры `sp_defaultdb` .</span><span class="sxs-lookup"><span data-stu-id="49cae-187">To set the default database of the login, use the `sp_defaultdb` system stored procedure.</span></span>  
  
 <span data-ttu-id="49cae-188">В результате воспроизведения событий, связанных с отсутствующими или неверными именами входа, будут возникать ошибки воспроизведения, но сама операция воспроизведения будет продолжена.</span><span class="sxs-lookup"><span data-stu-id="49cae-188">Replaying events associated with missing or incorrect logins results in replay errors, but the replay operation continues.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49cae-189">См. также:</span><span class="sxs-lookup"><span data-stu-id="49cae-189">See Also</span></span>  
 <span data-ttu-id="49cae-190">[Распределенное воспроизведение SQL Server](sql-server-distributed-replay.md) </span><span class="sxs-lookup"><span data-stu-id="49cae-190">[SQL Server Distributed Replay](sql-server-distributed-replay.md) </span></span>  
 <span data-ttu-id="49cae-191">[Безопасность распределенное воспроизведение](distributed-replay-security.md) </span><span class="sxs-lookup"><span data-stu-id="49cae-191">[Distributed Replay Security](distributed-replay-security.md) </span></span>  
 [<span data-ttu-id="49cae-192">Установка распределенного воспроизведения</span><span class="sxs-lookup"><span data-stu-id="49cae-192">Install Distributed Replay</span></span>](install-distributed-replay-overview.md)  
  
  
