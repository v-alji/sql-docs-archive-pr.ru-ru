---
title: Определение ответов заданий | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], responses
- SQL Server Agent jobs, responses
- actions [SQL Server Agent jobs]
- responding to jobs
ms.assetid: 050242e1-9b79-4ade-91a9-580707b9d2d9
author: stevestein
ms.author: sstein
ms.openlocfilehash: d41c5e1552a1ff16343bdb2c4e9feaafb51c5783
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727894"
---
# <a name="specify-job-responses"></a><span data-ttu-id="d52d7-102">Определение ответов заданий</span><span class="sxs-lookup"><span data-stu-id="d52d7-102">Specify Job Responses</span></span>
  <span data-ttu-id="d52d7-103">Ответы заданий определяют действия, выполняемые службой агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] после выполнения задания.</span><span class="sxs-lookup"><span data-stu-id="d52d7-103">Job responses specify actions that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service will take after a job completes.</span></span> <span data-ttu-id="d52d7-104">Ответы заданий дают гарантию того, что администраторы базы данных будут знать о завершении выполнения заданий и частоте их выполнения.</span><span class="sxs-lookup"><span data-stu-id="d52d7-104">Job responses ensure that database administrators know when jobs complete and how frequently they run.</span></span> <span data-ttu-id="d52d7-105">Обычными ответами заданий являются следующие.</span><span class="sxs-lookup"><span data-stu-id="d52d7-105">Typical job responses include:</span></span>  
  
-   <span data-ttu-id="d52d7-106">Уведомление оператора с помощью электронной почты, системы пейджинга или сообщения **net send** .</span><span class="sxs-lookup"><span data-stu-id="d52d7-106">Notifying the operator by using e-mail, electronic paging, or a **net send** message.</span></span>  
  
     <span data-ttu-id="d52d7-107">Используйте один из этих ответов на задание, если оператор должен выполнить последующие действия.</span><span class="sxs-lookup"><span data-stu-id="d52d7-107">Use one of these job responses if the operator must perform a follow-up action.</span></span> <span data-ttu-id="d52d7-108">Например, после успешного выполнения задания резервного копирования оператор должен получить напоминание об удалении магнитной ленты с резервной копией и сохранении ее в безопасном месте.</span><span class="sxs-lookup"><span data-stu-id="d52d7-108">For example, if a backup job completes successfully, the operator must be notified to remove the backup tape and store it in a safe location.</span></span>  
  
-   <span data-ttu-id="d52d7-109">Запись сообщений о событиях в журнал приложений Windows.</span><span class="sxs-lookup"><span data-stu-id="d52d7-109">Writing an event message to the Windows application log.</span></span>  
  
     <span data-ttu-id="d52d7-110">Этот ответ можно использовать только для неудачно завершившихся заданий.</span><span class="sxs-lookup"><span data-stu-id="d52d7-110">You can use this response only for failed jobs.</span></span>  
  
-   <span data-ttu-id="d52d7-111">Автоматическое удаление задания.</span><span class="sxs-lookup"><span data-stu-id="d52d7-111">Automatically deleting the job.</span></span>  
  
     <span data-ttu-id="d52d7-112">Используйте этот ответ только тогда, когда есть уверенность в том, что не понадобится выполнять это задание повторно.</span><span class="sxs-lookup"><span data-stu-id="d52d7-112">Use this job response if you are certain that you do not need to rerun this job.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="d52d7-113">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="d52d7-113">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d52d7-114">**Описание**</span><span class="sxs-lookup"><span data-stu-id="d52d7-114">**Description**</span></span>|<span data-ttu-id="d52d7-115">**Раздел**</span><span class="sxs-lookup"><span data-stu-id="d52d7-115">**Topic**</span></span>|  
|<span data-ttu-id="d52d7-116">Описывает, как уведомить оператора о состоянии задания.</span><span class="sxs-lookup"><span data-stu-id="d52d7-116">Describes how to notify an operator of job status.</span></span>|[<span data-ttu-id="d52d7-117">Notify an Operator of Job Status</span><span class="sxs-lookup"><span data-stu-id="d52d7-117">Notify an Operator of Job Status</span></span>](notify-an-operator-of-job-status.md)|  
|<span data-ttu-id="d52d7-118">Описывает, как записать состояние задания в журнал приложений Windows.</span><span class="sxs-lookup"><span data-stu-id="d52d7-118">Describes how to write job status to the Windows application log.</span></span>|[<span data-ttu-id="d52d7-119">Write the Job Status to the Windows Application Log</span><span class="sxs-lookup"><span data-stu-id="d52d7-119">Write the Job Status to the Windows Application Log</span></span>](../../reporting-services/report-server/windows-application-log.md)|  
  
## <a name="see-also"></a><span data-ttu-id="d52d7-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="d52d7-120">See Also</span></span>  
 [<span data-ttu-id="d52d7-121">Наблюдение и обработка событий</span><span class="sxs-lookup"><span data-stu-id="d52d7-121">Monitor and Respond to Events</span></span>](monitor-and-respond-to-events.md)  
  
  
