---
title: MSSQL_ENG014151 | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014151 error
ms.assetid: 54b45e70-46b3-4c7a-a5bf-06f6dd028ceb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d2796451f6f681cfb0ce529ed44a946c34135649
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655070"
---
# <a name="mssql_eng014151"></a><span data-ttu-id="eea25-102">MSSQL_ENG014151</span><span class="sxs-lookup"><span data-stu-id="eea25-102">MSSQL_ENG014151</span></span>
    
## <a name="message-details"></a><span data-ttu-id="eea25-103">Сведения о сообщении</span><span class="sxs-lookup"><span data-stu-id="eea25-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="eea25-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="eea25-104">Product Name</span></span>|<span data-ttu-id="eea25-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="eea25-105">SQL Server</span></span>|  
|<span data-ttu-id="eea25-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="eea25-106">Event ID</span></span>|<span data-ttu-id="eea25-107">14151</span><span class="sxs-lookup"><span data-stu-id="eea25-107">14151</span></span>|  
|<span data-ttu-id="eea25-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="eea25-108">Event Source</span></span>|<span data-ttu-id="eea25-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="eea25-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="eea25-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="eea25-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="eea25-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="eea25-111">Symbolic Name</span></span>||  
|<span data-ttu-id="eea25-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="eea25-112">Message Text</span></span>|<span data-ttu-id="eea25-113">Репликация-%s: ошибка агента %s.</span><span class="sxs-lookup"><span data-stu-id="eea25-113">Replication-%s: agent %s failed.</span></span> <span data-ttu-id="eea25-114">%s</span><span class="sxs-lookup"><span data-stu-id="eea25-114">%s</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="eea25-115">Объяснение</span><span class="sxs-lookup"><span data-stu-id="eea25-115">Explanation</span></span>  
 <span data-ttu-id="eea25-116">Эта ошибка возникает в случае сбоя любого агента репликации.</span><span class="sxs-lookup"><span data-stu-id="eea25-116">This error is raised for any replication agent failure.</span></span> <span data-ttu-id="eea25-117">Текст в конце сообщения зависит от контекста сбоя.</span><span class="sxs-lookup"><span data-stu-id="eea25-117">The text at the end of the message depends on the context of the failure.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="eea25-118">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="eea25-118">User Action</span></span>  
 <span data-ttu-id="eea25-119">Эта ошибка может возникать в нескольких ситуациях; в зависимости от сложившихся обстоятельств используйте следующие подходы:</span><span class="sxs-lookup"><span data-stu-id="eea25-119">This error can occur in a number of situations; use the following approaches as necessary:</span></span>  
  
-   <span data-ttu-id="eea25-120">Перезапустите агент, сбой которого произошел, и посмотрите, будет ли он теперь работать без сбоев.</span><span class="sxs-lookup"><span data-stu-id="eea25-120">Restart the failed agent to see if it will now run without failures.</span></span> <span data-ttu-id="eea25-121">Дополнительные сведения см. в статьях и [Запуск и остановка агента репликации (среда SQL Server Management Studio)](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) и [Основные понятия исполняемых файлов агента репликации](concepts/replication-agent-executables-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="eea25-121">For more information, see [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) and [Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span></span>  
  
-   <span data-ttu-id="eea25-122">Проверьте журнал агента и журнал заданий на наличие других ошибок, возникших приблизительно в то же время.</span><span class="sxs-lookup"><span data-stu-id="eea25-122">Check the agent history and job history for other errors that occurred around the same time.</span></span> <span data-ttu-id="eea25-123">Сведения о просмотре состояния агента и сведений об ошибках в мониторе репликации см. в статье [Просмотр сведений и выполнение задач с помощью монитора репликации](monitor/view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="eea25-123">For information about viewing agent status and error details in Replication Monitor, see [View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
-   <span data-ttu-id="eea25-124">Проверьте функционирование базовых соединений между компьютерами, к которым обращается агент, а затем подключитесь к каждому из этих компьютеров, используя программу, такую как [sqlcmd Utility](../../tools/sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="eea25-124">Verify that basic connectivity is working between the computers accessed by the agent, and then connect to each computer with a utility like the [sqlcmd Utility](../../tools/sqlcmd-utility.md).</span></span> <span data-ttu-id="eea25-125">При подключении используйте ту же учетную запись, под которой агент устанавливает соединения.</span><span class="sxs-lookup"><span data-stu-id="eea25-125">When connecting, use the same account under which the agent makes connections.</span></span> <span data-ttu-id="eea25-126">Дополнительные сведения о правах доступа, необходимых учетной записи каждого агента, см. в разделе [Replication Agent Security Model](security/replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="eea25-126">For more information about the permissions required by each agent account, see [Replication Agent Security Model](security/replication-agent-security-model.md).</span></span>  
  
-   <span data-ttu-id="eea25-127">Если ошибка возникает при создании или применении моментального снимка, проверьте файлы в каталоге моментальных снимков на наличие ошибок.</span><span class="sxs-lookup"><span data-stu-id="eea25-127">If the error occurs while creating or applying a snapshot, check the files in the snapshot directory for errors.</span></span>  
  
-   <span data-ttu-id="eea25-128">Если ошибка продолжает возникать, увеличьте протоколирование агента и укажите выходной файл для журнала.</span><span class="sxs-lookup"><span data-stu-id="eea25-128">If the error continues to occur, increase the logging of the agent and specify an output file for the log.</span></span> <span data-ttu-id="eea25-129">В зависимости от контекста ошибки эта мера может помочь в определении шагов, которые привели к ошибке или появлению дополнительных сообщений об ошибке.</span><span class="sxs-lookup"><span data-stu-id="eea25-129">Depending on the context of the error, this could provide the steps leading up to the error and/or additional error messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eea25-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="eea25-130">See Also</span></span>  
 <span data-ttu-id="eea25-131">[Администрирование агента репликации](agents/replication-agent-administration.md) </span><span class="sxs-lookup"><span data-stu-id="eea25-131">[Replication Agent Administration](agents/replication-agent-administration.md) </span></span>  
 <span data-ttu-id="eea25-132">[Справочник по ошибкам и событиям (репликация)](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="eea25-132">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 <span data-ttu-id="eea25-133">[Replication Distribution Agent](agents/replication-distribution-agent.md) </span><span class="sxs-lookup"><span data-stu-id="eea25-133">[Replication Distribution Agent](agents/replication-distribution-agent.md) </span></span>  
 <span data-ttu-id="eea25-134">[Replication Log Reader Agent](agents/replication-log-reader-agent.md) </span><span class="sxs-lookup"><span data-stu-id="eea25-134">[Replication Log Reader Agent](agents/replication-log-reader-agent.md) </span></span>  
 <span data-ttu-id="eea25-135">[Replication Merge Agent](agents/replication-merge-agent.md) </span><span class="sxs-lookup"><span data-stu-id="eea25-135">[Replication Merge Agent](agents/replication-merge-agent.md) </span></span>  
 <span data-ttu-id="eea25-136">[Агент чтения очереди репликации](agents/replication-queue-reader-agent.md) </span><span class="sxs-lookup"><span data-stu-id="eea25-136">[Replication Queue Reader Agent](agents/replication-queue-reader-agent.md) </span></span>  
 [<span data-ttu-id="eea25-137">Replication Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="eea25-137">Replication Snapshot Agent</span></span>](agents/replication-snapshot-agent.md)  
  
  
