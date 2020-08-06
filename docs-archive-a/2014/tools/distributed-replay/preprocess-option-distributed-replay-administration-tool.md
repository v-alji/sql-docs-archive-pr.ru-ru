---
title: Параметр предварительной обработки (средство администрирования распределенного воспроизведения) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
ms.assetid: 9b5012fd-233e-4a25-a2e1-585c63b70502
author: stevestein
ms.author: sstein
ms.openlocfilehash: e7f168d45b03473d958e202bd75116f4519d2fc4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657444"
---
# <a name="preprocess-option-distributed-replay-administration-tool"></a><span data-ttu-id="5d94d-102">Параметр предварительной обработки (средство администрирования распределенного воспроизведения)</span><span class="sxs-lookup"><span data-stu-id="5d94d-102">Preprocess Option (Distributed Replay Administration Tool)</span></span>
  <span data-ttu-id="5d94d-103">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Средство администрирования распределенное воспроизведение `DReplay.exe` — это средство командной строки, которое можно использовать для взаимодействия с контроллером распределенного воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="5d94d-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay administration tool, `DReplay.exe`, is a command-line tool that you can use to communicate with the distributed replay controller.</span></span> <span data-ttu-id="5d94d-104">В этом разделе описан параметр командной строки **preprocess** и соответствующий синтаксис.</span><span class="sxs-lookup"><span data-stu-id="5d94d-104">This topic describes the **preprocess** command-line option and corresponding syntax.</span></span>

 <span data-ttu-id="5d94d-105">Параметр **preprocess** запускает предварительную обработку.</span><span class="sxs-lookup"><span data-stu-id="5d94d-105">The **preprocess** option initiates the preprocess stage.</span></span> <span data-ttu-id="5d94d-106">На этом этапе контроллер подготавливает для воспроизведения на целевом сервере входные данные трассировки.</span><span class="sxs-lookup"><span data-stu-id="5d94d-106">During this stage, the controller prepares the input trace data for replay against the target server.</span></span>

 <span data-ttu-id="5d94d-107">![Значок ссылки на раздел](../../database-engine/media/topic-link.gif "Значок ссылки на раздел") Дополнительные сведения о синтаксических обозначениях, используемых в синтаксисе средства администрирования, см. в статье [Синтаксические обозначения в Transact-SQL (Transact-SQL)](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5d94d-107">![Topic link icon](../../database-engine/media/topic-link.gif "Topic link icon") For more information about the syntax conventions that are used with the administration tool syntax, see [Transact-SQL Syntax Conventions &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span></span>

## <a name="syntax"></a><span data-ttu-id="5d94d-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5d94d-108">Syntax</span></span>

```

      dreplay preprocess [-mcontroller] -iinput_trace_file
    -dcontroller_working_dir [-cconfig_file] [-fstatus_interval]
```

#### <a name="parameters"></a><span data-ttu-id="5d94d-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="5d94d-109">Parameters</span></span>
 <span data-ttu-id="5d94d-110">*контроллер* **-m** указывает имя компьютера контроллера.</span><span class="sxs-lookup"><span data-stu-id="5d94d-110">**-m** *controller* Specifies the computer name of the controller.</span></span> <span data-ttu-id="5d94d-111">Локальный компьютер можно указать как «`localhost`» или «`.`».</span><span class="sxs-lookup"><span data-stu-id="5d94d-111">You can use "`localhost`" or "`.`" to refer to the local computer.</span></span>

 <span data-ttu-id="5d94d-112">Если параметр **-m** не задан, то используется локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="5d94d-112">If the **-m** parameter is not specified, the local computer is used.</span></span>

 <span data-ttu-id="5d94d-113">**-i** *input_trace_file* указывает полный путь к входному файлу трассировки на контроллере, например `D:\Mytrace.trc` .</span><span class="sxs-lookup"><span data-stu-id="5d94d-113">**-i** *input_trace_file* Specifies the full path of the input trace file on the controller, such as `D:\Mytrace.trc`.</span></span> <span data-ttu-id="5d94d-114">Параметр **-i** является обязательным.</span><span class="sxs-lookup"><span data-stu-id="5d94d-114">The **-i** parameter is required.</span></span>

 <span data-ttu-id="5d94d-115">При наличии в том же каталоге файлов продолжения они загружаются и используются автоматически.</span><span class="sxs-lookup"><span data-stu-id="5d94d-115">If there are rollover files in the same directory, they will be loaded and used automatically.</span></span> <span data-ttu-id="5d94d-116">Файлы должны соответствовать соглашению об именовании переключения на файл продолжения, например: `Mytrace.trc`, `Mytrace_1.trc`, `Mytrace_2.trc`, `Mytrace_3.trc`, … `Mytrace_n.trc`.</span><span class="sxs-lookup"><span data-stu-id="5d94d-116">The files must follow the file rollover naming convention, for example: `Mytrace.trc`, `Mytrace_1.trc`, `Mytrace_2.trc`, `Mytrace_3.trc`, ... `Mytrace_n.trc`.</span></span>

> [!NOTE]
>  <span data-ttu-id="5d94d-117">При использовании средства администрирования на компьютере, отличном от контроллера, необходимо скопировать файлы входных данных трассировки на контроллер, чтобы в этом параметре можно было использовать локальный путь.</span><span class="sxs-lookup"><span data-stu-id="5d94d-117">If you are using the administration tool on a different computer than the controller, you will need to copy the input trace files to the controller so that a local path can be used for this parameter.</span></span>

 <span data-ttu-id="5d94d-118">**-d** *controller_working_dir* указывает каталог на контроллере, где будет храниться промежуточный файл.</span><span class="sxs-lookup"><span data-stu-id="5d94d-118">**-d** *controller_working_dir* Specifies the directory on the controller where the intermediate file will be stored.</span></span> <span data-ttu-id="5d94d-119">Параметр **-d** является обязательным.</span><span class="sxs-lookup"><span data-stu-id="5d94d-119">The **-d** parameter is required.</span></span>

 <span data-ttu-id="5d94d-120">К нему предъявляются следующие требования.</span><span class="sxs-lookup"><span data-stu-id="5d94d-120">The following requirements apply:</span></span>

-   <span data-ttu-id="5d94d-121">Каталог должен находиться на контроллере.</span><span class="sxs-lookup"><span data-stu-id="5d94d-121">The directory must reside on the controller.</span></span>

-   <span data-ttu-id="5d94d-122">Необходимо указать полный путь, начиная с буквы диска (например, `c:\WorkingDir`).</span><span class="sxs-lookup"><span data-stu-id="5d94d-122">You must specify the full path, starting with a drive letter (for example, `c:\WorkingDir`).</span></span>

-   <span data-ttu-id="5d94d-123">Путь не должен завершаться обратной косой чертой «`\`».</span><span class="sxs-lookup"><span data-stu-id="5d94d-123">The path must not end with a backslash "`\`".</span></span>

-   <span data-ttu-id="5d94d-124">Пути в формате UNC не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="5d94d-124">UNC paths are not supported.</span></span>

 <span data-ttu-id="5d94d-125">**-c** *config_file* — это полный путь к файлу конфигурации предварительной обработки; используется для указания расположения файла конфигурации предварительной обработки при хранении в другом расположении.</span><span class="sxs-lookup"><span data-stu-id="5d94d-125">**-c** *config_file* Is the full path of the preprocess configuration file; used to specify the location of the preprocess configuration file when stored in a different location.</span></span> <span data-ttu-id="5d94d-126">Этот параметр может быть путем в формате UNC или задавать локальный путь на компьютере, на котором выполняется средство администрирования.</span><span class="sxs-lookup"><span data-stu-id="5d94d-126">This parameter can be a UNC path, or can reside locally on the computer where you run the administration tool.</span></span>

 <span data-ttu-id="5d94d-127">Если фильтрация не требуется или не нужно изменять максимальное время простоя, то указывать параметр **-c** не обязательно.</span><span class="sxs-lookup"><span data-stu-id="5d94d-127">The **-c** parameter is not required if no filtering is needed, or if you do not want to modify the maximum idle time.</span></span>

 <span data-ttu-id="5d94d-128">Без параметра **-c** используется файл конфигурации предварительной обработки по умолчанию — `DReplay.exe.preprocess.config`.</span><span class="sxs-lookup"><span data-stu-id="5d94d-128">Without the **-c** parameter, the default preprocess configuration file, `DReplay.exe.preprocess.config`, is used.</span></span>

 <span data-ttu-id="5d94d-129">**-f** *status_interval* указывает частоту (в секундах) вывода сообщений о состоянии.</span><span class="sxs-lookup"><span data-stu-id="5d94d-129">**-f** *status_interval* Specifies the frequency (in seconds) at which to display status messages.</span></span>

 <span data-ttu-id="5d94d-130">Если параметр **-f** не задан, интервал по умолчанию составляет 30 секунд.</span><span class="sxs-lookup"><span data-stu-id="5d94d-130">If **-f** is not specified, the default interval is 30 seconds.</span></span>

## <a name="examples"></a><span data-ttu-id="5d94d-131">Примеры</span><span class="sxs-lookup"><span data-stu-id="5d94d-131">Examples</span></span>
 <span data-ttu-id="5d94d-132">В этом примере предварительная подготовка запускается со всеми параметрами по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5d94d-132">In this example, the preprocess stage is initiated with all of the default settings.</span></span> <span data-ttu-id="5d94d-133">Значение `localhost` указывает, что служба контроллера запущена на том же компьютере, что и средство администрирования.</span><span class="sxs-lookup"><span data-stu-id="5d94d-133">The value `localhost` indicates that the controller service is running on the same computer as the administration tool.</span></span> <span data-ttu-id="5d94d-134">Параметр *input_trace_file* задает расположение входных данных трассировки — `c:\mytrace.trc`.</span><span class="sxs-lookup"><span data-stu-id="5d94d-134">The *input_trace_file* parameter specifies the location of the input trace data, `c:\mytrace.trc`.</span></span> <span data-ttu-id="5d94d-135">Так как фильтрация файлов трассировки не используется, указывать параметр **-c** не обязательно.</span><span class="sxs-lookup"><span data-stu-id="5d94d-135">Because there is no trace file filtering involved, the **-c** parameter does have to be specified.</span></span>

```
dreplay preprocess -m localhost -i c:\mytrace.trc -d c:\WorkingDir
```

 <span data-ttu-id="5d94d-136">В этом примере запускается этап предварительной подготовки и указывается измененный файл конфигурации предварительной обработки.</span><span class="sxs-lookup"><span data-stu-id="5d94d-136">In this example, the preprocess stage is initiated and a modified preprocess configuration file is specified.</span></span> <span data-ttu-id="5d94d-137">В отличие от предыдущего примера параметр **-c** используется для указания измененного файла конфигурации, сохраненного в другом расположении.</span><span class="sxs-lookup"><span data-stu-id="5d94d-137">Unlike the previous example, the **-c** parameter is used to point to the modified configuration file, if you have stored it in a different location.</span></span> <span data-ttu-id="5d94d-138">Пример:</span><span class="sxs-lookup"><span data-stu-id="5d94d-138">For example:</span></span>

```
dreplay preprocess -m localhost -i c:\mytrace.trc -d c:\WorkingDir -c c:\DReplay.exe.preprocess.config
```

 <span data-ttu-id="5d94d-139">В измененном файле конфигурации предварительной обработки добавлено условие фильтра, которое позволяет отфильтровать системные сеансы во время распределенного воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="5d94d-139">In the modified preprocess configuration file, a filter condition is added that filters out system sessions during distributed replay.</span></span> <span data-ttu-id="5d94d-140">Фильтр добавляется путем изменения элемента `<PreprocessModifiers>` в файле конфигурации предварительной обработки `DReplay.exe.preprocess.config`.</span><span class="sxs-lookup"><span data-stu-id="5d94d-140">The filter is added by modifying the `<PreprocessModifiers>` element in the preprocess configuration file, `DReplay.exe.preprocess.config`.</span></span>

 <span data-ttu-id="5d94d-141">В следующем примере показан измененный файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5d94d-141">The following shows an example of the modified configuration file:</span></span>

```
<?xml version='1.0'?>
<Options>
    <PreprocessModifiers>
        <IncSystemSession>No</IncSystemSession>
        <MaxIdleTime>-1</MaxIdleTime>
    </PreprocessModifiers>
</Options>
```

## <a name="permissions"></a><span data-ttu-id="5d94d-142">Разрешения</span><span class="sxs-lookup"><span data-stu-id="5d94d-142">Permissions</span></span>
 <span data-ttu-id="5d94d-143">Средство администрирования должно запускаться как интерактивный пользователь, с учетной записью локального пользователя или пользователя домена.</span><span class="sxs-lookup"><span data-stu-id="5d94d-143">You must run the administration tool as an interactive user, as either a local user or a domain user account.</span></span> <span data-ttu-id="5d94d-144">Для использования учетной записи локального пользователя средство администрирования и контроллер должны быть запущены на одном компьютере.</span><span class="sxs-lookup"><span data-stu-id="5d94d-144">To use a local user account, the administration tool and controller must be running on the same computer.</span></span>

 <span data-ttu-id="5d94d-145">Дополнительные сведения см. в статье [Distributed Replay Security](distributed-replay-security.md).</span><span class="sxs-lookup"><span data-stu-id="5d94d-145">For more information, see [Distributed Replay Security](distributed-replay-security.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5d94d-146">См. также:</span><span class="sxs-lookup"><span data-stu-id="5d94d-146">See Also</span></span>
 <span data-ttu-id="5d94d-147">[Подготовьте входные данные трассировки](prepare-the-input-trace-data.md) [SQL Server распределенное воспроизведение](sql-server-distributed-replay.md) [настроить распределенное воспроизведение](configure-distributed-replay.md)</span><span class="sxs-lookup"><span data-stu-id="5d94d-147">[Prepare the Input Trace Data](prepare-the-input-trace-data.md) [SQL Server Distributed Replay](sql-server-distributed-replay.md) [Configure Distributed Replay](configure-distributed-replay.md)</span></span>


