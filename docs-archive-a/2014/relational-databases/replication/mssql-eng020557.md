---
title: MSSQL_ENG020557 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG020557 error
ms.assetid: c43c6952-5b60-4347-b881-11a0004dce24
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 45c24d453eb95abaa967ae65ceb5934b7dee969e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668811"
---
# <a name="mssql_eng020557"></a><span data-ttu-id="a473f-102">MSSQL_ENG020557</span><span class="sxs-lookup"><span data-stu-id="a473f-102">MSSQL_ENG020557</span></span>
    
## <a name="message-details"></a><span data-ttu-id="a473f-103">Сведения о сообщении</span><span class="sxs-lookup"><span data-stu-id="a473f-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a473f-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="a473f-104">Product Name</span></span>|<span data-ttu-id="a473f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a473f-105">SQL Server</span></span>|  
|<span data-ttu-id="a473f-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="a473f-106">Event ID</span></span>|<span data-ttu-id="a473f-107">20557</span><span class="sxs-lookup"><span data-stu-id="a473f-107">20557</span></span>|  
|<span data-ttu-id="a473f-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="a473f-108">Event Source</span></span>|<span data-ttu-id="a473f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a473f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a473f-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="a473f-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="a473f-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="a473f-111">Symbolic Name</span></span>||  
|<span data-ttu-id="a473f-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="a473f-112">Message Text</span></span>|<span data-ttu-id="a473f-113">Завершение работы агента.</span><span class="sxs-lookup"><span data-stu-id="a473f-113">Agent shutdown.</span></span> <span data-ttu-id="a473f-114">Дополнительные сведения см. в журнале заданий агента SQL Server для задания «%s».</span><span class="sxs-lookup"><span data-stu-id="a473f-114">For more information, see the SQL Server Agent job history for job '%s'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a473f-115">Объяснение</span><span class="sxs-lookup"><span data-stu-id="a473f-115">Explanation</span></span>  
 <span data-ttu-id="a473f-116">Агент репликации завершил работу, не записав причину в соответствующую таблицу журнала, либо работа агента была завершена в середине процесса.</span><span class="sxs-lookup"><span data-stu-id="a473f-116">A replication agent has shut down without writing a reason to the appropriate history table, or the agent was shut down while in the middle of a process.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a473f-117">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="a473f-117">User Action</span></span>  
  
-   <span data-ttu-id="a473f-118">Перезапустите агент и посмотрите, будет ли он теперь работать без сбоев.</span><span class="sxs-lookup"><span data-stu-id="a473f-118">Restart the agent to see whether it will now run without failures.</span></span> <span data-ttu-id="a473f-119">Дополнительные сведения см. в статьях и [Запуск и остановка агента репликации (среда SQL Server Management Studio)](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) и [Основные понятия исполняемых файлов агента репликации](concepts/replication-agent-executables-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="a473f-119">For more information, see [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) and [Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span></span>  
  
-   <span data-ttu-id="a473f-120">Проверьте журнал агента и журнал заданий на наличие других ошибок, возникших приблизительно в то же время.</span><span class="sxs-lookup"><span data-stu-id="a473f-120">Check the agent history and job history for other errors that occurred around the same time.</span></span> <span data-ttu-id="a473f-121">Сведения о просмотре состояния агента и сведений об ошибках в мониторе репликации см. в статье [Просмотр сведений и выполнение задач с помощью монитора репликации](monitor/view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="a473f-121">For information about how to view agent status and error details in Replication Monitor, see [View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md).</span></span>
-   <span data-ttu-id="a473f-122">Проверьте функционирование базовых соединений между компьютерами, к которым обращается агент, а затем подключитесь к каждому из этих компьютеров, используя программу, такую как **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="a473f-122">Verify that basic connectivity is working between the computers that are accessed by the agent, and then connect to each computer by using a utility, such as the **sqlcmd** utility.</span></span> <span data-ttu-id="a473f-123">Для соединения используйте ту же учетную запись, под которой агент устанавливает соединения.</span><span class="sxs-lookup"><span data-stu-id="a473f-123">When you connect, use the same account under which the agent makes connections.</span></span> <span data-ttu-id="a473f-124">Дополнительные сведения о правах доступа, необходимых учетной записи каждого агента, см. в разделе [Replication Agent Security Model](security/replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="a473f-124">For more information about the permissions that are required by each agent account, see [Replication Agent Security Model](security/replication-agent-security-model.md).</span></span>  
  
-   <span data-ttu-id="a473f-125">Если ошибка возникает при создании или применении моментального снимка, проверьте файлы в каталоге моментальных снимков на наличие ошибок.</span><span class="sxs-lookup"><span data-stu-id="a473f-125">If the error occurs while you are creating or applying a snapshot, check the files in the snapshot directory for errors.</span></span>  
  
-   <span data-ttu-id="a473f-126">Если ошибка продолжает возникать, увеличьте протоколирование агента и укажите выходной файл для журнала.</span><span class="sxs-lookup"><span data-stu-id="a473f-126">If the error continues to occur, increase the logging of the agent and specify an output file for the log.</span></span> <span data-ttu-id="a473f-127">В зависимости от контекста ошибки эта мера может помочь в определении шагов, которые приведут к ошибке или дополнительным сообщениям об ошибке.</span><span class="sxs-lookup"><span data-stu-id="a473f-127">Depending on the context of the error, this could provide the steps leading up to the error and additional error messages.</span></span> <span data-ttu-id="a473f-128">Дополнительные сведения о настройке ведения журнала репликации см. в статье базы знаний Майкрософт [312292](https://support.microsoft.com/kb/312292).</span><span class="sxs-lookup"><span data-stu-id="a473f-128">For more information about how to configure logging for replication, see the Microsoft Knowledge Base article [312292](https://support.microsoft.com/kb/312292).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a473f-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="a473f-129">See Also</span></span>  
 [<span data-ttu-id="a473f-130">Справочник по ошибкам и событиям (репликация)</span><span class="sxs-lookup"><span data-stu-id="a473f-130">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
