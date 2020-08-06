---
title: Параметры командной строки средства администрирования (программа распределенного воспроизведения) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
ms.assetid: c01b0ed3-67e4-4561-92d2-a8fbb086aca8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 506be071f44937d82902585e5a0621212083dfa5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665177"
---
# <a name="administration-tool-command-line-options-distributed-replay-utility"></a><span data-ttu-id="55886-102">Параметры командной строки средства администрирования (программа распределенного воспроизведения)</span><span class="sxs-lookup"><span data-stu-id="55886-102">Administration Tool Command-line Options (Distributed Replay Utility)</span></span>
  <span data-ttu-id="55886-103">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Средство администрирования распределенное воспроизведение `DReplay.exe` — это средство командной строки, которое можно использовать для взаимодействия с контроллером распределенного воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="55886-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay administration tool, `DReplay.exe`, is a command-line tool that you can use to communicate with the distributed replay controller.</span></span> <span data-ttu-id="55886-104">При помощи средства администрирования можно инициировать операции на контроллере, наблюдать за ними и отменять.</span><span class="sxs-lookup"><span data-stu-id="55886-104">Use the administration tool to initiate, monitor, and cancel operations on the controller.</span></span>  
  
 <span data-ttu-id="55886-105">![Значок ссылки на раздел](../../database-engine/media/topic-link.gif "Значок ссылки на раздел") Дополнительные сведения о синтаксических обозначениях, используемых в синтаксисе средства администрирования, см. в разделе [Синтаксические обозначения в Transact-SQL (Transact-SQL)](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="55886-105">![Topic link icon](../../database-engine/media/topic-link.gif "Topic link icon") For more information about the syntax conventions that are used with the administration tool syntax, see [Transact-SQL Syntax Conventions &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55886-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="55886-106">Syntax</span></span>  
  
```  
  
      dreplay {preprocess|replay|status|cancel} [options] [-?]}  
  
Usage:  
  
  dreplay preprocess [-mcontroller] -iinput_trace_file  
    -dcontroller_working_dir [-cconfig_file] [-fstatus_interval]  
  
  dreplay replay [-mcontroller] -dcontroller_working_dir [-o]  
    [-starget_server] -wclients [-cconfig_file]  
    [-fstatus_interval]  
  
  dreplay status [-mcontroller] [-fstatus_interval]  
  
  dreplay cancel [-mcontroller] [-q]   
```  
  
## <a name="remarks"></a><span data-ttu-id="55886-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="55886-107">Remarks</span></span>  
 <span data-ttu-id="55886-108">В программе `DReplay.exe` можно применять следующие параметры командной строки:</span><span class="sxs-lookup"><span data-stu-id="55886-108">You can issue the following command-line options with `DReplay.exe`:</span></span>  
  
 <span data-ttu-id="55886-109">**preprocess**</span><span class="sxs-lookup"><span data-stu-id="55886-109">**preprocess**</span></span>  
 <span data-ttu-id="55886-110">Инициирует стадию предварительной обработки.</span><span class="sxs-lookup"><span data-stu-id="55886-110">Initiates the preprocess stage.</span></span> <span data-ttu-id="55886-111">Подготавливаются для воспроизведения на целевом сервере входные данные трассировки, отслеженные в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="55886-111">The controller prepares the input trace data, which you captured from the production environment, for replay against the target server.</span></span>  
  
 <span data-ttu-id="55886-112">**replay**</span><span class="sxs-lookup"><span data-stu-id="55886-112">**replay**</span></span>  
 <span data-ttu-id="55886-113">Инициирует стадию воспроизведения события.</span><span class="sxs-lookup"><span data-stu-id="55886-113">Initiates the event replay stage.</span></span> <span data-ttu-id="55886-114">Данные воспроизведения отправляются указанным клиентам, запускается распределенное воспроизведение, синхронизируются клиенты.</span><span class="sxs-lookup"><span data-stu-id="55886-114">The controller dispatches replay data to the specified clients, launches the distributed replay, and synchronizes the clients.</span></span> <span data-ttu-id="55886-115">При необходимости каждый выбранный клиент может записывать последовательность воспроизведения и сохранять получившиеся файлы трассировки в локальном кэше.</span><span class="sxs-lookup"><span data-stu-id="55886-115">Optionally, each client that was selected records the replay activity and saves result trace files locally.</span></span>  
  
 <span data-ttu-id="55886-116">**status**</span><span class="sxs-lookup"><span data-stu-id="55886-116">**status**</span></span>  
 <span data-ttu-id="55886-117">Опрашивает контроллер и отображает его текущее состояние.</span><span class="sxs-lookup"><span data-stu-id="55886-117">Queries the controller and displays the current status.</span></span>  
  
 <span data-ttu-id="55886-118">**cancel**</span><span class="sxs-lookup"><span data-stu-id="55886-118">**cancel**</span></span>  
 <span data-ttu-id="55886-119">Отменяет текущую операцию, выполняемую на контроллере.</span><span class="sxs-lookup"><span data-stu-id="55886-119">Cancels the current operation that is running on the controller.</span></span>  
  
 <span data-ttu-id="55886-120">Подробные сведения о синтаксисе, включая командные аргументы и примеры, см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="55886-120">For detailed syntax information that includes the command arguments and examples, see the following topics:</span></span>  
  
-   [<span data-ttu-id="55886-121">Параметр предварительной обработки (средство администрирования распределенного воспроизведения)</span><span class="sxs-lookup"><span data-stu-id="55886-121">Preprocess Option &#40;Distributed Replay Administration Tool&#41;</span></span>](preprocess-option-distributed-replay-administration-tool.md)  
  
-   [<span data-ttu-id="55886-122">Параметр воспроизведения (средство администрирования распределенного воспроизведения)</span><span class="sxs-lookup"><span data-stu-id="55886-122">Replay Option &#40;Distributed Replay Administration Tool&#41;</span></span>](replay-option-distributed-replay-administration-tool.md)  
  
-   [<span data-ttu-id="55886-123">Параметр состояния (средство администрирования распределенного воспроизведения)</span><span class="sxs-lookup"><span data-stu-id="55886-123">Status Option &#40;Distributed Replay Administration Tool&#41;</span></span>](status-option-distributed-replay-administration-tool.md)  
  
-   [<span data-ttu-id="55886-124">Параметр отмены (средство администрирования распределенного воспроизведения)</span><span class="sxs-lookup"><span data-stu-id="55886-124">Cancel Option &#40;Distributed Replay Administration Tool&#41;</span></span>](cancel-option-distributed-replay-administration-tool.md)  
  
 <span data-ttu-id="55886-125">Удаленные вызовы процедур (RPC) воспроизводятся как RPC, а не события языка.</span><span class="sxs-lookup"><span data-stu-id="55886-125">RPCs are replayed as RPCs and not as language events.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="55886-126">Разрешения</span><span class="sxs-lookup"><span data-stu-id="55886-126">Permissions</span></span>  
 <span data-ttu-id="55886-127">Средство администрирования должно запускаться как интерактивный пользователь, с учетной записью локального пользователя или пользователя домена.</span><span class="sxs-lookup"><span data-stu-id="55886-127">You must run the administration tool as an interactive user, as either a local user or a domain user account.</span></span> <span data-ttu-id="55886-128">Для использования учетной записи локального пользователя средство администрирования и контроллер должны быть запущены на одном компьютере.</span><span class="sxs-lookup"><span data-stu-id="55886-128">To use a local user account, the administration tool and controller must be running on the same computer.</span></span>  
  
 <span data-ttu-id="55886-129">Дополнительные сведения см. в статье [Distributed Replay Security](distributed-replay-security.md).</span><span class="sxs-lookup"><span data-stu-id="55886-129">For more information, see [Distributed Replay Security](distributed-replay-security.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55886-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="55886-130">See Also</span></span>  
 [<span data-ttu-id="55886-131">Распределенное воспроизведение SQL Server</span><span class="sxs-lookup"><span data-stu-id="55886-131">SQL Server Distributed Replay</span></span>](sql-server-distributed-replay.md)  
  
  
