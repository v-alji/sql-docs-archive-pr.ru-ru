---
title: MSSQL_REPL027056 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_REPL027056 error
ms.assetid: 92d62f3c-b8ae-482e-a348-2e9a8ee9786e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 44fb130321ec54c39559d52e493cc8f3424172fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736206"
---
# <a name="mssql_repl027056"></a><span data-ttu-id="05c72-102">MSSQL_REPL027056</span><span class="sxs-lookup"><span data-stu-id="05c72-102">MSSQL_REPL027056</span></span>
    
## <a name="message-details"></a><span data-ttu-id="05c72-103">Сведения о сообщении</span><span class="sxs-lookup"><span data-stu-id="05c72-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="05c72-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="05c72-104">Product Name</span></span>|<span data-ttu-id="05c72-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="05c72-105">SQL Server</span></span>|  
|<span data-ttu-id="05c72-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="05c72-106">Event ID</span></span>|<span data-ttu-id="05c72-107">27056</span><span class="sxs-lookup"><span data-stu-id="05c72-107">27056</span></span>|  
|<span data-ttu-id="05c72-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="05c72-108">Event Source</span></span>|<span data-ttu-id="05c72-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="05c72-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="05c72-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="05c72-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="05c72-111">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="05c72-111">Symbolic Name</span></span>||  
|<span data-ttu-id="05c72-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="05c72-112">Message Text</span></span>|<span data-ttu-id="05c72-113">Процессу слияния не удалось изменить журнал поколений в '%1'.</span><span class="sxs-lookup"><span data-stu-id="05c72-113">The merge process was unable to change generation history at the '%1'.</span></span> <span data-ttu-id="05c72-114">В целях диагностики запустите синхронизацию повторно, включив подробное протоколирование и укажите выходной файл для записи.</span><span class="sxs-lookup"><span data-stu-id="05c72-114">When troubleshooting, restart the synchronization with verbose history logging and specify an output file to which to write.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="05c72-115">Объяснение</span><span class="sxs-lookup"><span data-stu-id="05c72-115">Explanation</span></span>  
 <span data-ttu-id="05c72-116">Эта ошибка обычно возникает в результате состязания между чрезмерно увеличившимися системными таблицами репликации слиянием.</span><span class="sxs-lookup"><span data-stu-id="05c72-116">This error is typically raised as a result of contention in merge replication system tables that have grown excessively large.</span></span> <span data-ttu-id="05c72-117">Большой размер системных таблицы обычно обусловлен длительным сроком хранения публикации, поскольку метаданные должны сохраняться в этих таблицах до тех пор, пока не закончится срок хранения.</span><span class="sxs-lookup"><span data-stu-id="05c72-117">Large system tables are typically caused by a long publication retention period, because metadata must be stored in these tables until the retention period is reached.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="05c72-118">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="05c72-118">User Action</span></span>  
 <span data-ttu-id="05c72-119">**Способы устранения проблемы.**</span><span class="sxs-lookup"><span data-stu-id="05c72-119">**To resolve the issue:**</span></span>  
  
1.  <span data-ttu-id="05c72-120">Уменьшите значение параметров**DownloadGenerationsPerBatch** и **-UploadGenerationsPerBatch** агента слияния, чтобы разрешить продолжение обработки, пока устраняются причины ошибки.</span><span class="sxs-lookup"><span data-stu-id="05c72-120">Decrease the value of the -**DownloadGenerationsPerBatch** and **-UploadGenerationsPerBatch** parameters for the Merge Agent to allow processing to continue while you address the underlying issue causing the error.</span></span> <span data-ttu-id="05c72-121">Параметры агента могут задаваться в профилях агента или в командной строке.</span><span class="sxs-lookup"><span data-stu-id="05c72-121">Agent parameters can be specified in agent profiles and on the command line.</span></span> <span data-ttu-id="05c72-122">Дополнительные сведения см. в разделе:</span><span class="sxs-lookup"><span data-stu-id="05c72-122">For more information, see:</span></span>  
  
    -   [<span data-ttu-id="05c72-123">Работа с профилями агента репликации</span><span class="sxs-lookup"><span data-stu-id="05c72-123">Work with Replication Agent Profiles</span></span>](agents/replication-agent-profiles.md)  
  
    -   [<span data-ttu-id="05c72-124">Просмотр и изменение параметров командной строки агента репликации (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="05c72-124">View and Modify Replication Agent Command Prompt Parameters &#40;SQL Server Management Studio&#41;</span></span>](agents/view-and-modify-replication-agent-command-prompt-parameters.md)  
  
    -   <span data-ttu-id="05c72-125">[Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="05c72-125">[Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span></span>  
  
2.  <span data-ttu-id="05c72-126">Укажите наименьшее возможное значение срока хранения публикации.</span><span class="sxs-lookup"><span data-stu-id="05c72-126">Specify the lowest setting possible for the publication retention period.</span></span> <span data-ttu-id="05c72-127">Дополнительные сведения см. в разделе [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="05c72-127">For more information, see [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span></span>  
  
3.  <span data-ttu-id="05c72-128">Обслуживая репликацию слиянием, иногда проверяйте увеличение размера системных таблиц, связанных с репликацией слиянием: **MSmerge_contents**, **MSmerge_genhistory**, **MSmerge_tombstone**, **MSmerge_current_partition_mappings**и **MSmerge_past_partition_mappings**.</span><span class="sxs-lookup"><span data-stu-id="05c72-128">As part of maintenance for merge replication, occasionally check the growth of the system tables associated with merge replication: **MSmerge_contents**, **MSmerge_genhistory**, and **MSmerge_tombstone**, **MSmerge_current_partition_mappings**, and **MSmerge_past_partition_mappings**.</span></span> <span data-ttu-id="05c72-129">Время от времени проводите повторную индексацию этих таблиц.</span><span class="sxs-lookup"><span data-stu-id="05c72-129">Periodically re-index these tables.</span></span> <span data-ttu-id="05c72-130">Дополнительные сведения см. в статье [Реорганизация и перестроение индексов](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="05c72-130">For more information, see [Reorganize and Rebuild Indexes](../indexes/indexes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05c72-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="05c72-131">See Also</span></span>  
 [<span data-ttu-id="05c72-132">Справочник по ошибкам и событиям (репликация)</span><span class="sxs-lookup"><span data-stu-id="05c72-132">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
