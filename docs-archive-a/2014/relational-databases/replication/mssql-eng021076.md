---
title: MSSQL_ENG021076 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021076 error
ms.assetid: 612e5c59-ba3e-49c3-a3df-56bac3d850a2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4161428767ce78726436c0cf794f5250140d35b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730505"
---
# <a name="mssql_eng021076"></a><span data-ttu-id="b5335-102">MSSQL_ENG021076</span><span class="sxs-lookup"><span data-stu-id="b5335-102">MSSQL_ENG021076</span></span>
    
## <a name="message-details"></a><span data-ttu-id="b5335-103">Сведения о сообщении</span><span class="sxs-lookup"><span data-stu-id="b5335-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b5335-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="b5335-104">Product Name</span></span>|<span data-ttu-id="b5335-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b5335-105">SQL Server</span></span>|  
|<span data-ttu-id="b5335-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="b5335-106">Event ID</span></span>|<span data-ttu-id="b5335-107">21076</span><span class="sxs-lookup"><span data-stu-id="b5335-107">21076</span></span>|  
|<span data-ttu-id="b5335-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="b5335-108">Event Source</span></span>|<span data-ttu-id="b5335-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b5335-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b5335-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="b5335-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="b5335-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="b5335-111">Symbolic Name</span></span>||  
|<span data-ttu-id="b5335-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="b5335-112">Message Text</span></span>|<span data-ttu-id="b5335-113">Исходный моментальный снимок для статьи "%s" еще не доступен.</span><span class="sxs-lookup"><span data-stu-id="b5335-113">The initial snapshot for article '%s' is not yet available.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b5335-114">Объяснение</span><span class="sxs-lookup"><span data-stu-id="b5335-114">Explanation</span></span>  
 <span data-ttu-id="b5335-115">Ошибка MSSQL_ENG021076 может возникнуть, если агент распространителя запускается до того, как агент моментальных снимков закончил создание моментального снимка.</span><span class="sxs-lookup"><span data-stu-id="b5335-115">Error MSSQL_ENG021076 can be raised if the Distribution Agent is started before the Snapshot Agent has finished generating the snapshot.</span></span> <span data-ttu-id="b5335-116">Эта ошибка возникает, только если публикация содержит единственную статью.</span><span class="sxs-lookup"><span data-stu-id="b5335-116">This error is raised only if the publication contains a single article.</span></span> <span data-ttu-id="b5335-117">Если публикация содержит несколько статей, то вместо описываемой ошибки возникает ошибка MSSQL_ENG021075.</span><span class="sxs-lookup"><span data-stu-id="b5335-117">If the publication contains more than one article, MSSQL_ENG021075 is raised instead.</span></span> <span data-ttu-id="b5335-118">Дополнительные сведения см. в разделе [MSSQL_ENG021075](mssql-eng021075.md).</span><span class="sxs-lookup"><span data-stu-id="b5335-118">For more information, see [MSSQL_ENG021075](mssql-eng021075.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b5335-119">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="b5335-119">User Action</span></span>  
 <span data-ttu-id="b5335-120">Если агент моментальных снимков для публикации не запускался после создания подписки или если он не запускался с момента повторной инициализации подписки, запустите агент моментальных снимков и дайте ему возможность завершить работу, прежде чем запустить агент распространителя.</span><span class="sxs-lookup"><span data-stu-id="b5335-120">If the Snapshot Agent for the publication has not been started since the subscription was created, or if it has not been started since the last time you chose to reinitialize the subscription, start the Snapshot Agent and let it complete before starting the Distribution Agent.</span></span> <span data-ttu-id="b5335-121">Дополнительные сведения см. в статье [Создание и применение моментального снимка](create-and-apply-the-snapshot.md).</span><span class="sxs-lookup"><span data-stu-id="b5335-121">For more information, see [Create and Apply the Snapshot](create-and-apply-the-snapshot.md).</span></span>  
  
 <span data-ttu-id="b5335-122">Если агент моментальных снимков не завершил свою работу, проверьте журнал агента моментальных снимков на наличие ошибок и устраните эти ошибки.</span><span class="sxs-lookup"><span data-stu-id="b5335-122">If the Snapshot Agent does not complete, check the Snapshot Agent history for errors and address them.</span></span> <span data-ttu-id="b5335-123">Сведения о просмотре состояния агента и сведений об ошибках в мониторе репликации см. в статье [Просмотр сведений и выполнение задач с помощью монитора репликации](monitor/view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="b5335-123">For information about viewing agent status and error details in Replication Monitor, see [View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="b5335-124">Если ошибка продолжает возникать, увеличьте протоколирование агента и укажите выходной файл для журнала.</span><span class="sxs-lookup"><span data-stu-id="b5335-124">If the error continues to occur, increase the logging of the agent and specify an output file for the log.</span></span> <span data-ttu-id="b5335-125">В зависимости от контекста ошибки эта мера может помочь в определении шагов, которые привели к ошибке или появлению дополнительных сообщений об ошибке.</span><span class="sxs-lookup"><span data-stu-id="b5335-125">Depending on the context of the error, this could provide the steps leading up to the error and/or additional error messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5335-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="b5335-126">See Also</span></span>  
 [<span data-ttu-id="b5335-127">Справочник по ошибкам и событиям (репликация)</span><span class="sxs-lookup"><span data-stu-id="b5335-127">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
