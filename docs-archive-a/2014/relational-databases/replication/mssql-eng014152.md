---
title: MSSQL_ENG014152 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014152 error
ms.assetid: 4215e2b1-cd30-441f-9671-9afc742adf6e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 615b9cf2996653d86c44d6e43a83e01e8287b110
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658213"
---
# <a name="mssql_eng014152"></a><span data-ttu-id="b92db-102">MSSQL_ENG014152</span><span class="sxs-lookup"><span data-stu-id="b92db-102">MSSQL_ENG014152</span></span>
    
## <a name="message-details"></a><span data-ttu-id="b92db-103">Сведения о сообщении</span><span class="sxs-lookup"><span data-stu-id="b92db-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b92db-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="b92db-104">Product Name</span></span>|<span data-ttu-id="b92db-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b92db-105">SQL Server</span></span>|  
|<span data-ttu-id="b92db-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="b92db-106">Event ID</span></span>|<span data-ttu-id="b92db-107">14152</span><span class="sxs-lookup"><span data-stu-id="b92db-107">14152</span></span>|  
|<span data-ttu-id="b92db-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="b92db-108">Event Source</span></span>|<span data-ttu-id="b92db-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b92db-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b92db-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="b92db-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="b92db-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="b92db-111">Symbolic Name</span></span>||  
|<span data-ttu-id="b92db-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="b92db-112">Message Text</span></span>|<span data-ttu-id="b92db-113">Репликация-%s: назначено повторное выполнение агента %s.</span><span class="sxs-lookup"><span data-stu-id="b92db-113">Replication-%s: agent %s scheduled for retry.</span></span> <span data-ttu-id="b92db-114">%s</span><span class="sxs-lookup"><span data-stu-id="b92db-114">%s</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b92db-115">Объяснение</span><span class="sxs-lookup"><span data-stu-id="b92db-115">Explanation</span></span>  
 <span data-ttu-id="b92db-116">Для указанного агента репликации было запланировано повторное выполнение запрошенной операции.</span><span class="sxs-lookup"><span data-stu-id="b92db-116">The specified replication agent has been scheduled to retry the requested operation.</span></span> <span data-ttu-id="b92db-117">Повторные попытки продолжаются до тех пор, пока не будет достигнуто максимальное число попыток, настроенное для шага задания.</span><span class="sxs-lookup"><span data-stu-id="b92db-117">The process continues to retry until it reaches the configured maximum number of retry attempts for the job step.</span></span>  
  
 <span data-ttu-id="b92db-118">Причиной повторного выполнения обычно становится одно из следующего.</span><span class="sxs-lookup"><span data-stu-id="b92db-118">A retry typically occurs because of one of the following reasons:</span></span>  
  
-   <span data-ttu-id="b92db-119">Превышено значение **QueryTimeout** .</span><span class="sxs-lookup"><span data-stu-id="b92db-119">The **QueryTimeout** value is exceeded.</span></span>  
  
-   <span data-ttu-id="b92db-120">Превышено значение **LoginTimeout** .</span><span class="sxs-lookup"><span data-stu-id="b92db-120">The **LoginTimeout** value is exceeded.</span></span>  
  
-   <span data-ttu-id="b92db-121">Процесс репликации был выбран как жертва взаимоблокировки.</span><span class="sxs-lookup"><span data-stu-id="b92db-121">The replication process was chosen as a deadlock victim.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b92db-122">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="b92db-122">User Action</span></span>  
 <span data-ttu-id="b92db-123">Если сообщение о повторном выполнении появляется нечасто, никакие пользовательские действия не требуются.</span><span class="sxs-lookup"><span data-stu-id="b92db-123">If the retry message is infrequent, no user action is required.</span></span>  
  
 <span data-ttu-id="b92db-124">Используйте процедуру [sp_help_jobstep](/sql/relational-databases/system-stored-procedures/sp-help-jobstep-transact-sql) для проверки текущего значения максимального числа повторений шага **Запустить агент** для указанного агента репликации.</span><span class="sxs-lookup"><span data-stu-id="b92db-124">Use [sp_help_jobstep](/sql/relational-databases/system-stored-procedures/sp-help-jobstep-transact-sql) to view the current setting for the maximum number of times the **Run agent** step for the specified replication agent will retry.</span></span> <span data-ttu-id="b92db-125">**@retry_attempts**Параметр хранимой процедуры [sp_update_jobstep](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql) можно использовать для настройки числа повторных попыток выполнения шага задания.</span><span class="sxs-lookup"><span data-stu-id="b92db-125">You can use the **@retry_attempts** parameter of the [sp_update_jobstep](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql) stored procedure to adjust the number of times a job step retries.</span></span>  
  
 <span data-ttu-id="b92db-126">Если сообщение о повторном выполнении появляется часто, способ устранения неполадок зависит от сообщения, вызывающего повтор.</span><span class="sxs-lookup"><span data-stu-id="b92db-126">If the retry message recurs frequently, troubleshoot the issue based on the message that is causing the retry.</span></span> <span data-ttu-id="b92db-127">Проверьте в журнале агента наличие сообщений, указывающих причину назначения повторного выполнения.</span><span class="sxs-lookup"><span data-stu-id="b92db-127">Check the agent's history for messages that indicate why the retry had to be scheduled.</span></span> <span data-ttu-id="b92db-128">В некоторых случаях может потребоваться включить ведение более подробного журнала для агента репликации.</span><span class="sxs-lookup"><span data-stu-id="b92db-128">In some cases you may have to enable more detailed logging for your replication agent.</span></span> <span data-ttu-id="b92db-129">Дополнительные сведения о настройке ведения журнала репликации см. в статье базы знаний Майкрософт [312292](https://support.microsoft.com/kb/312292).</span><span class="sxs-lookup"><span data-stu-id="b92db-129">For more information about how to configure logging for replication, see the Microsoft Knowledge Base article [312292](https://support.microsoft.com/kb/312292).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b92db-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="b92db-130">See Also</span></span>  
 [<span data-ttu-id="b92db-131">Справочник по ошибкам и событиям (репликация)</span><span class="sxs-lookup"><span data-stu-id="b92db-131">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
