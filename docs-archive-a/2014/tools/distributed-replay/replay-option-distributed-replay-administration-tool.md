---
title: Параметр воспроизведения (средство администрирования распределенного воспроизведения) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
ms.assetid: d7bce6a5-d414-488d-a3cd-50c1c62019c4
author: stevestein
ms.author: sstein
ms.openlocfilehash: a3114d7c2a2a7908e4e010fbf5d80c7d332d264c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740619"
---
# <a name="replay-option-distributed-replay-administration-tool"></a><span data-ttu-id="e7f5a-102">Параметр воспроизведения (средство администрирования распределенного воспроизведения)</span><span class="sxs-lookup"><span data-stu-id="e7f5a-102">Replay Option (Distributed Replay Administration Tool)</span></span>
  <span data-ttu-id="e7f5a-103">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Средство администрирования распределенное воспроизведение `DReplay.exe` — это средство командной строки, которое можно использовать для взаимодействия с контроллером распределенного воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="e7f5a-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Distributed Replay administration tool, `DReplay.exe`, is a command-line tool that you can use to communicate with the distributed replay controller.</span></span> <span data-ttu-id="e7f5a-104">В этом разделе описываются параметр командной строки **replay** и соответствующий синтаксис.</span><span class="sxs-lookup"><span data-stu-id="e7f5a-104">This topic describes the **replay** command-line option and corresponding syntax.</span></span>

 <span data-ttu-id="e7f5a-105">Параметр **replay** инициирует стадию воспроизведения события, на которой контроллер отправляет данные воспроизведения указанным клиентам, запускает распределенное воспроизведение и синхронизирует клиенты.</span><span class="sxs-lookup"><span data-stu-id="e7f5a-105">The **replay** option initiates the event replay stage, in which the controller dispatches replay data to the specified clients, launches the distributed replay and synchronizes the clients.</span></span> <span data-ttu-id="e7f5a-106">При необходимости каждый клиент, участвующий в воспроизведении, может записывать последовательность воспроизведения и сохранять получившиеся файлы трассировки в локальном кэше.</span><span class="sxs-lookup"><span data-stu-id="e7f5a-106">Optionally, each client participating in the replay can record the replay activity and save a result trace file locally.</span></span>

 <span data-ttu-id="e7f5a-107">![Значок ссылки на раздел](../../database-engine/media/topic-link.gif "Значок ссылки на раздел") См. сведения о [синтаксических обозначениях в Transact-SQL (Transact-SQL)](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql), используемых в синтаксисе средства администрирования.</span><span class="sxs-lookup"><span data-stu-id="e7f5a-107">![Topic link icon](../../database-engine/media/topic-link.gif "Topic link icon") For more information about the syntax conventions that are used with the administration tool syntax, see [Transact-SQL Syntax Conventions &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span></span>

## <a name="syntax"></a><span data-ttu-id="e7f5a-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e7f5a-108">Syntax</span></span>

```

      dreplay replay [-mcontroller] -dcontroller_working_dir [-o]
    [-starget_server] -wclients [-cconfig_file]
    [-fstatus_interval]
```

#### <a name="parameters"></a><span data-ttu-id="e7f5a-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="e7f5a-109">Parameters</span></span>
 <span data-ttu-id="e7f5a-110">*контроллер* **-m** указывает имя компьютера контроллера.</span><span class="sxs-lookup"><span data-stu-id="e7f5a-110">**-m** *controller* Specifies the computer name of the controller.</span></span> <span data-ttu-id="e7f5a-111">Локальный компьютер можно указать как «`localhost`» или «`.`».</span><span class="sxs-lookup"><span data-stu-id="e7f5a-111">You can use "`localhost`" or "`.`" to refer to the local computer.</span></span>

 <span data-ttu-id="e7f5a-112">Если параметр **-m** не задан, то используется локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="e7f5a-112">If the **-m** parameter is not specified, the local computer is used.</span></span>

 <span data-ttu-id="e7f5a-113">**-d** *controller_working_dir* указывает каталог на контроллере, где будет храниться промежуточный файл.</span><span class="sxs-lookup"><span data-stu-id="e7f5a-113">**-d** *controller_working_dir* Specifies the directory on the controller where the intermediate file will be stored.</span></span> <span data-ttu-id="e7f5a-114">Параметр **-d** является обязательным.</span><span class="sxs-lookup"><span data-stu-id="e7f5a-114">The **-d** parameter is required.</span></span>

 <span data-ttu-id="e7f5a-115">К нему предъявляются следующие требования.</span><span class="sxs-lookup"><span data-stu-id="e7f5a-115">The following requirements apply:</span></span>

-   <span data-ttu-id="e7f5a-116">Каталог должен находиться на контроллере.</span><span class="sxs-lookup"><span data-stu-id="e7f5a-116">The directory must reside on the controller.</span></span>

-   <span data-ttu-id="e7f5a-117">Необходимо указать полный путь, начиная с буквы диска (например, `c:\WorkingDir`).</span><span class="sxs-lookup"><span data-stu-id="e7f5a-117">You must specify the full path, starting with a drive letter (for example, `c:\WorkingDir`).</span></span>

-   <span data-ttu-id="e7f5a-118">Путь не должен завершаться обратной косой чертой «`\`».</span><span class="sxs-lookup"><span data-stu-id="e7f5a-118">The path must not end with a backslash "`\`".</span></span>

-   <span data-ttu-id="e7f5a-119">Пути в формате UNC не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="e7f5a-119">UNC paths are not supported.</span></span>

 <span data-ttu-id="e7f5a-120">**-o** Захватывает действие воспроизведения клиентов и сохраняет его в результирующий файл трассировки по пути, указанному `<ResultDirectory>` в элементе в файле конфигурации клиента `DReplayClient.xml` .</span><span class="sxs-lookup"><span data-stu-id="e7f5a-120">**-o** Captures the clients' replay activity and saves it to a result trace file in the path specified by the `<ResultDirectory>` element in the client configuration file, `DReplayClient.xml`.</span></span>

 <span data-ttu-id="e7f5a-121">Если параметр **-o** не задан, результирующий файл трассировки не создается.</span><span class="sxs-lookup"><span data-stu-id="e7f5a-121">When the **-o** parameter is not specified, the result trace file is not generated.</span></span> <span data-ttu-id="e7f5a-122">В конце воспроизведения консоль возвращает сводные данные, но остальная статистика воспроизведения недоступна.</span><span class="sxs-lookup"><span data-stu-id="e7f5a-122">The console output returns summary information at the end of replay, but no other replay statistics are available.</span></span>

 <span data-ttu-id="e7f5a-123">**-s** *target_server* указывает целевой экземпляр [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , с которым должна воспроизводиться Распределенная рабочая нагрузка.</span><span class="sxs-lookup"><span data-stu-id="e7f5a-123">**-s** *target_server* Specifies the target instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that the distributed workload should be replayed against.</span></span> <span data-ttu-id="e7f5a-124">Этот параметр необходимо задать в формате **имя_сервера[\имя_экземпляра]** .</span><span class="sxs-lookup"><span data-stu-id="e7f5a-124">You must specify this parameter in the format **server_name[\instance name]**.</span></span>

 <span data-ttu-id="e7f5a-125">Недопустимо использовать в качестве целевого сервера «`localhost`» или «`.`».</span><span class="sxs-lookup"><span data-stu-id="e7f5a-125">You cannot use "`localhost`" or "`.`" as the target server.</span></span>

 <span data-ttu-id="e7f5a-126">Параметр **-s** не является обязательным, если элемент `<Server>` задан в секции `<ReplayOptions>` файла конфигурации воспроизведения `DReplay.exe.replay.config`.</span><span class="sxs-lookup"><span data-stu-id="e7f5a-126">The **-s** parameter is not required if the `<Server>` element is specified in the `<ReplayOptions>` section of the replay configuration file, `DReplay.exe.replay.config`.</span></span>

 <span data-ttu-id="e7f5a-127">Если используется параметр **-s** , элемент `<Server>` в секции `<ReplayOptions>` файла конфигурации воспроизведения будет игнорироваться.</span><span class="sxs-lookup"><span data-stu-id="e7f5a-127">If the **-s** parameter is used, the `<Server>` element in the `<ReplayOptions>` section of the replay configuration file will be ignored.</span></span>

 <span data-ttu-id="e7f5a-128">**-w** *Клиенты* . Этот обязательный параметр является разделенным запятыми (без пробелов), указывающими имена компьютеров клиентов, которые должны участвовать в распределенном воспроизведении.</span><span class="sxs-lookup"><span data-stu-id="e7f5a-128">**-w** *clients* This required parameter is a comma-separated list (without spaces) that specifies the computer names of clients that should participate in the distributed replay.</span></span> <span data-ttu-id="e7f5a-129">IP-адреса недопустимы.</span><span class="sxs-lookup"><span data-stu-id="e7f5a-129">IP addresses are not allowed.</span></span> <span data-ttu-id="e7f5a-130">Помните, что клиенты должны быть уже зарегистрированы на контроллере.</span><span class="sxs-lookup"><span data-stu-id="e7f5a-130">Be aware that the clients must already be registered with the controller.</span></span>

> [!NOTE]
>  <span data-ttu-id="e7f5a-131">Каждый клиент регистрируется на контроллере, который указывается в файле конфигурации клиента при запуске службы клиента.</span><span class="sxs-lookup"><span data-stu-id="e7f5a-131">Each client registers with the controller that is specified in the client configuration file when the client service starts.</span></span>

 <span data-ttu-id="e7f5a-132">**-c** *config_file* — это полный путь к файлу конфигурации воспроизведения; используется для указания расположения, когда оно хранится в другом расположении.</span><span class="sxs-lookup"><span data-stu-id="e7f5a-132">**-c** *config_file* Is the full path of the replay configuration file; used to specify the location when it is stored in a different location.</span></span>

 <span data-ttu-id="e7f5a-133">Параметр **-c** не является обязательным, если будут использоваться значения по умолчанию файла конфигурации воспроизведения `DReplay.exe.replay.config`.</span><span class="sxs-lookup"><span data-stu-id="e7f5a-133">The **-c** parameter is not required if you want to use the default values of the replay configuration file, `DReplay.exe.replay.config`.</span></span>

 <span data-ttu-id="e7f5a-134">**-f** *status_interval* указывает частоту (в секундах) вывода состояния.</span><span class="sxs-lookup"><span data-stu-id="e7f5a-134">**-f** *status_interval* Specifies the frequency (in seconds) at which to display the status.</span></span>

 <span data-ttu-id="e7f5a-135">Если параметр **-f** не задан, интервал по умолчанию составляет 30 секунд.</span><span class="sxs-lookup"><span data-stu-id="e7f5a-135">If **-f** is not specified, the default interval is 30 seconds.</span></span>

## <a name="examples"></a><span data-ttu-id="e7f5a-136">Примеры</span><span class="sxs-lookup"><span data-stu-id="e7f5a-136">Examples</span></span>
 <span data-ttu-id="e7f5a-137">В данном примере распределенное воспроизведение наследует большую часть своего поведения из измененного файла конфигурации воспроизведения `DReplay.exe.replay.config`.</span><span class="sxs-lookup"><span data-stu-id="e7f5a-137">In this example, the distributed replay derives much of its behavior from a modified replay configuration file, `DReplay.exe.replay.config`.</span></span>

-   <span data-ttu-id="e7f5a-138">Параметр **-m** указывает, что в качестве контроллера выступает компьютер `controller1` .</span><span class="sxs-lookup"><span data-stu-id="e7f5a-138">The **-m** parameter specifies that a computer named `controller1` acts as the controller.</span></span> <span data-ttu-id="e7f5a-139">Имя компьютера нужно указывать, если служба контроллера работает на другом компьютере.</span><span class="sxs-lookup"><span data-stu-id="e7f5a-139">The computer name must be specified when the controller service is running on a different computer.</span></span>

-   <span data-ttu-id="e7f5a-140">Параметр **-d** указывает расположение промежуточного файла `c:\WorkingDir`на контроллере.</span><span class="sxs-lookup"><span data-stu-id="e7f5a-140">The **-d** parameter specifies the location of the intermediate file on the controller, `c:\WorkingDir`.</span></span>

-   <span data-ttu-id="e7f5a-141">Параметр **-o** указывает, что каждый заданный клиент регистрирует действие воспроизведения и сохраняет его в результирующем файле трассировки.</span><span class="sxs-lookup"><span data-stu-id="e7f5a-141">The **-o** parameter specifies that each specified client capture the replay activity and save it to a result trace file.</span></span> <span data-ttu-id="e7f5a-142">Примечание. С помощью элемента `<ResultTrace>` файла конфигурации можно указать, следует ли записывать количество строк и результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="e7f5a-142">Note: The `<ResultTrace>` element in the configuration file can be used to specify if row count and result set be recorded.</span></span>

-   <span data-ttu-id="e7f5a-143">Параметр **-w** указывает, что компьютеры `client1` – `client4` являются клиентами распределенного воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="e7f5a-143">The **-w** parameter specifies that computers `client1` through `client4` participate as clients in the distributed replay.</span></span>

-   <span data-ttu-id="e7f5a-144">Параметр **-c** указывает на измененный файл конфигурации `DReplay.exe.replay.config`.</span><span class="sxs-lookup"><span data-stu-id="e7f5a-144">The **-c** parameter is used to point to the modified configuration file, `DReplay.exe.replay.config`.</span></span>

-   <span data-ttu-id="e7f5a-145">Параметр **-s** не является обязательным, потому что элемент `<Server>` задан в элементе `<ReplayOptions>` файла конфигурации воспроизведения `DReplay.exe.replay.config`.</span><span class="sxs-lookup"><span data-stu-id="e7f5a-145">The **-s** parameter is not required because the `<Server>` element is specified in the `<ReplayOptions>` element of the replay configuration file, `DReplay.exe.replay.config`.</span></span>

 <span data-ttu-id="e7f5a-146">Этап воспроизведения событий инициируется следующим синтаксисом, когда средство администрирования запускается не на контроллере:</span><span class="sxs-lookup"><span data-stu-id="e7f5a-146">The event replay stage is initiated with the following syntax, when the administration tool is run from a different computer than the controller:</span></span>

```
dreplay replay -m controller1 -d c:\WorkingDir -o -w client1,client2,client3,client4 -c c:\DReplay.exe.replay.config
```

 <span data-ttu-id="e7f5a-147">Чтобы установить синхронный режим последовательного выполнения, элементу `<SequencingMode>` в файле `DReplay.exe.replay.config` нужно присвоить значение `synchronization`.</span><span class="sxs-lookup"><span data-stu-id="e7f5a-147">To specify a synchronous sequencing mode, the `<SequencingMode>` element of the `DReplay.exe.replay.config` file is set equal to the value `synchronization`.</span></span> <span data-ttu-id="e7f5a-148">Раздел `<ResultTrace>` файла конфигурации воспроизведения изменен для указания записи количества строк.</span><span class="sxs-lookup"><span data-stu-id="e7f5a-148">The `<ResultTrace>` section of the replay configuration file is modified to specify that row count be recorded.</span></span> <span data-ttu-id="e7f5a-149">Эти изменения показаны в следующем примере XML-кода:</span><span class="sxs-lookup"><span data-stu-id="e7f5a-149">These changes are shown in the following XML example:</span></span>

```
<?xml version='1.0'?>
<Options>
    <ReplayOptions>
        <Server>server_name\replay_target_instance</Server>
        <SequencingMode>synchronization</SequencingMode>
        <ConnectTimeScale></ConnectTimeScale>
        <ThinkTimeScale></ThinkTimeScale>
        <HealthmonInterval>60</HealthmonInterval>
        <QueryTimeout>3600</QueryTimeout>
        <ThreadsPerClient></ThreadsPerClient>
    </ReplayOptions>
    <OutputOptions>
        <ResultTrace>
            <RecordRowCount>Yes</RecordRowCount>
            <RecordResultSet>No</RecordResultSet>
        </ResultTrace>
    </OutputOptions>
</Options>
```

 <span data-ttu-id="e7f5a-150">Чтобы установить режим нагрузки последовательного выполнения, элементу `<SequencingMode>` в файле `DReplay.exe.replay.config` нужно присвоить значение `stress`.</span><span class="sxs-lookup"><span data-stu-id="e7f5a-150">To specify a stress sequencing mode, the `<SequencingMode>` element of the `DReplay.exe.replay.config` file is set equal to the value `stress`.</span></span> <span data-ttu-id="e7f5a-151">Элементам `<ConnectTimeScale>` и `<ThinkTimeScale>` присваивается значение `50` (что означает 50 процентов).</span><span class="sxs-lookup"><span data-stu-id="e7f5a-151">The `<ConnectTimeScale>` and `<ThinkTimeScale>` elements are set to the value `50` (to specify 50 percent).</span></span> <span data-ttu-id="e7f5a-152">Дополнительные сведения о времени соединения и времени обработки см. в разделе [Настройка распределенного воспроизведения](configure-distributed-replay.md).</span><span class="sxs-lookup"><span data-stu-id="e7f5a-152">For more information about connect time and think time, see [Configure Distributed Replay](configure-distributed-replay.md).</span></span> <span data-ttu-id="e7f5a-153">Эти изменения показаны в следующем примере XML-кода:</span><span class="sxs-lookup"><span data-stu-id="e7f5a-153">These changes are shown in the following XML example:</span></span>

```
<?xml version='1.0'?>
<Options>
    <ReplayOptions>
        <Server>server_name\replay_target_instance_name</Server>
        <SequencingMode>stress</SequencingMode>
        <ConnectTimeScale>50</ConnectTimeScale>
        <ThinkTimeScale>50</ThinkTimeScale>
        <HealthmonInterval>60</HealthmonInterval>
        <QueryTimeout>3600</QueryTimeout>
        <ThreadsPerClient></ThreadsPerClient>
    </ReplayOptions>
    <OutputOptions>
        <ResultTrace>
            <RecordRowCount>Yes</RecordRowCount>
            <RecordResultSet>No</RecordResultSet>
        </ResultTrace>
    </OutputOptions>
</Options>
```

## <a name="permissions"></a><span data-ttu-id="e7f5a-154">Разрешения</span><span class="sxs-lookup"><span data-stu-id="e7f5a-154">Permissions</span></span>
 <span data-ttu-id="e7f5a-155">Средство администрирования должно запускаться как интерактивный пользователь, с учетной записью локального пользователя или пользователя домена.</span><span class="sxs-lookup"><span data-stu-id="e7f5a-155">You must run the administration tool as an interactive user, as either a local user or a domain user account.</span></span> <span data-ttu-id="e7f5a-156">Для использования учетной записи локального пользователя средство администрирования и контроллер должны быть запущены на одном компьютере.</span><span class="sxs-lookup"><span data-stu-id="e7f5a-156">To use a local user account, the administration tool and controller must be running on the same computer.</span></span>

 <span data-ttu-id="e7f5a-157">Дополнительные сведения см. в статье [Distributed Replay Security](distributed-replay-security.md).</span><span class="sxs-lookup"><span data-stu-id="e7f5a-157">For more information, see [Distributed Replay Security](distributed-replay-security.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e7f5a-158">См. также:</span><span class="sxs-lookup"><span data-stu-id="e7f5a-158">See Also</span></span>
 <span data-ttu-id="e7f5a-159">[Воспроизведение данных трассировки](replay-trace-data.md) [проверьте результаты воспроизведения](review-the-replay-results.md) [SQL Server распределенное воспроизведение](sql-server-distributed-replay.md) [настроить](configure-distributed-replay.md) [форум распределенное воспроизведение SQL Server распределенное воспроизведение](https://social.technet.microsoft.com/Forums/sl/sqldru/) [, используя распределенное воспроизведение для нагрузочного тестирования SQL Server. часть 2](https://docs.microsoft.com/archive/blogs/msdn/mspfe/using-distributed-replay-to-load-test-your-sql-serverpart-2) [с помощью распределенное воспроизведение для нагрузочного тестирования SQL Server. часть 1](https://docs.microsoft.com/archive/blogs/batuhanyildiz/using-distributed-replay-to-load-test-your-sql-serverpart-1)</span><span class="sxs-lookup"><span data-stu-id="e7f5a-159">[Replay Trace Data](replay-trace-data.md) [Review the Replay Results](review-the-replay-results.md) [SQL Server Distributed Replay](sql-server-distributed-replay.md) [Configure Distributed Replay](configure-distributed-replay.md) [SQL Server Distributed Replay Forum](https://social.technet.microsoft.com/Forums/sl/sqldru/) [Using Distributed Replay to Load Test Your SQL Server - Part 2](https://docs.microsoft.com/archive/blogs/msdn/mspfe/using-distributed-replay-to-load-test-your-sql-serverpart-2) [Using Distributed Replay to Load Test Your SQL Server - Part 1](https://docs.microsoft.com/archive/blogs/batuhanyildiz/using-distributed-replay-to-load-test-your-sql-serverpart-1)</span></span>


