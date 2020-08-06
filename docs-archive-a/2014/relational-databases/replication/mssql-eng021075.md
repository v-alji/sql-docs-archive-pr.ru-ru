---
title: MSSQL_ENG021075 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021075 error
ms.assetid: c8c29543-d1f6-49d5-b6c8-e8c3aa373090
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 20f2428038326681f5f8eb877e5c3017ced30f00
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666507"
---
# <a name="mssql_eng021075"></a><span data-ttu-id="60a70-102">MSSQL_ENG021075</span><span class="sxs-lookup"><span data-stu-id="60a70-102">MSSQL_ENG021075</span></span>
    
## <a name="message-details"></a><span data-ttu-id="60a70-103">Сведения о сообщении</span><span class="sxs-lookup"><span data-stu-id="60a70-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="60a70-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="60a70-104">Product Name</span></span>|<span data-ttu-id="60a70-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="60a70-105">SQL Server</span></span>|  
|<span data-ttu-id="60a70-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="60a70-106">Event ID</span></span>|<span data-ttu-id="60a70-107">21075</span><span class="sxs-lookup"><span data-stu-id="60a70-107">21075</span></span>|  
|<span data-ttu-id="60a70-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="60a70-108">Event Source</span></span>|<span data-ttu-id="60a70-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="60a70-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="60a70-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="60a70-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="60a70-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="60a70-111">Symbolic Name</span></span>||  
|<span data-ttu-id="60a70-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="60a70-112">Message Text</span></span>|<span data-ttu-id="60a70-113">Исходный моментальный снимок публикации "%s" еще недоступен.</span><span class="sxs-lookup"><span data-stu-id="60a70-113">The initial snapshot for publication '%s' is not yet available.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="60a70-114">Объяснение</span><span class="sxs-lookup"><span data-stu-id="60a70-114">Explanation</span></span>  
 <span data-ttu-id="60a70-115">Ошибка MSSQL_ENG021075 возникает, если агент распространителя или агент слияния запускается до окончания создания моментального снимка агентом моментальных снимков.</span><span class="sxs-lookup"><span data-stu-id="60a70-115">Error MSSQL_ENG021075 is raised if the Distribution Agent or Merge Agent is started before the Snapshot Agent has finished generating the snapshot.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="60a70-116">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="60a70-116">User Action</span></span>  
 <span data-ttu-id="60a70-117">Если со времени создания подписки агент моментальных снимков для публикации не запускался или если он не запускался со времени последней повторной инициализации подписки, запустите агент моментальных снимков и позвольте ему полностью завершить свою работу до запуска агента распространителя или агента слияния.</span><span class="sxs-lookup"><span data-stu-id="60a70-117">If the Snapshot Agent for the publication has not been started since the subscription was created, or if it has not been started since the last time you chose to reinitialize the subscription, start the Snapshot Agent and let it complete before starting the Distribution Agent or Merge Agent.</span></span> <span data-ttu-id="60a70-118">Дополнительные сведения см. в статье [Создание и применение моментального снимка](create-and-apply-the-snapshot.md).</span><span class="sxs-lookup"><span data-stu-id="60a70-118">For more information, see [Create and Apply the Snapshot](create-and-apply-the-snapshot.md).</span></span>  
  
 <span data-ttu-id="60a70-119">Если агент моментальных снимков не завершил свою работу, проверьте журнал агента моментальных снимков на наличие ошибок и устраните эти ошибки.</span><span class="sxs-lookup"><span data-stu-id="60a70-119">If the Snapshot Agent does not complete, check the Snapshot Agent history for errors and address them.</span></span> <span data-ttu-id="60a70-120">Сведения о просмотре состояния агента и сведений об ошибках в мониторе репликации см. в статье [Просмотр сведений и выполнение задач с помощью монитора репликации](monitor/view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="60a70-120">For information about viewing agent status and error details in Replication Monitor, see [View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="60a70-121">Если ошибка продолжает возникать, увеличьте протоколирование агента и укажите выходной файл для журнала.</span><span class="sxs-lookup"><span data-stu-id="60a70-121">If the error continues to occur, increase the logging of the agent and specify an output file for the log.</span></span> <span data-ttu-id="60a70-122">В зависимости от контекста ошибки эта мера может помочь в определении шагов, которые привели к ошибке или появлению дополнительных сообщений об ошибке.</span><span class="sxs-lookup"><span data-stu-id="60a70-122">Depending on the context of the error, this could provide the steps leading up to the error and/or additional error messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60a70-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="60a70-123">See Also</span></span>  
 [<span data-ttu-id="60a70-124">Справочник по ошибкам и событиям (репликация)</span><span class="sxs-lookup"><span data-stu-id="60a70-124">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
