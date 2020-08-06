---
title: Свойства агента SQL Server (страница "Журнал") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.agent.history.f1
ms.assetid: dc73734c-b3c3-407f-bbd1-8714b4fa47b0
author: stevestein
ms.author: sstein
ms.openlocfilehash: d67ff3da97e11292abcac03958fe1e423b35d7d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667525"
---
# <a name="sql-server-agent-properties-history-page"></a><span data-ttu-id="bee0f-102">Свойства агента SQL Server (страница «Журнал»)</span><span class="sxs-lookup"><span data-stu-id="bee0f-102">SQL Server Agent Properties (History Page)</span></span>
  <span data-ttu-id="bee0f-103">Эта страница используется для просмотра и изменения параметров [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] журнала службы агента.</span><span class="sxs-lookup"><span data-stu-id="bee0f-103">Use this page to view and modify settings for managing the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service history log.</span></span>  
  
## <a name="options"></a><span data-ttu-id="bee0f-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="bee0f-104">Options</span></span>  
 <span data-ttu-id="bee0f-105">**Ограничить размер журнала заданий**</span><span class="sxs-lookup"><span data-stu-id="bee0f-105">**Limit size of job history log**</span></span>  
 <span data-ttu-id="bee0f-106">Ограничивает объем данных, которые агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] сохраняет в журнале заданий.</span><span class="sxs-lookup"><span data-stu-id="bee0f-106">Sets limits for the amount of job history information that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent retains in the log.</span></span>  
  
 <span data-ttu-id="bee0f-107">**Максимальный размер журнала заданий (в строках)**</span><span class="sxs-lookup"><span data-stu-id="bee0f-107">**Maximum job history log size (in rows)**</span></span>  
 <span data-ttu-id="bee0f-108">Максимальное число строк, записываемых агентом [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bee0f-108">Sets the maximum number of rows that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent retains.</span></span> <span data-ttu-id="bee0f-109">При увеличении объема журнала до указанной границы для записи новых строк агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] удаляет наиболее старые строки в журнале.</span><span class="sxs-lookup"><span data-stu-id="bee0f-109">When the log grows to contain this number of rows, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent removes the oldest rows in the log as new rows are entered.</span></span>  
  
 <span data-ttu-id="bee0f-110">**Максимальное число строк в журнале заданий для одного задания**</span><span class="sxs-lookup"><span data-stu-id="bee0f-110">**Maximum job history rows per job**</span></span>  
 <span data-ttu-id="bee0f-111">Максимальное количество строк, записываемых агентом [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для одного задания.</span><span class="sxs-lookup"><span data-stu-id="bee0f-111">Sets the maximum number of rows that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent retains per job.</span></span> <span data-ttu-id="bee0f-112">При увеличении объема журнала для указанного задания до указанной границы для записи новых строк агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] удаляет наиболее старые строки в журнале.</span><span class="sxs-lookup"><span data-stu-id="bee0f-112">When the history for a particular job grows to contain this number of rows, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent removes the oldest rows in the log as new rows are entered.</span></span>  
  
 <span data-ttu-id="bee0f-113">**Удаление журнала агента**</span><span class="sxs-lookup"><span data-stu-id="bee0f-113">**Remove agent history**</span></span>  
 <span data-ttu-id="bee0f-114">Вызывает удаление агентом [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] записей со сроком давности больше заданного.</span><span class="sxs-lookup"><span data-stu-id="bee0f-114">Specifies that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent will remove entries that have been in the log longer than a specified length of time.</span></span> <span data-ttu-id="bee0f-115">Это однократное выполнение для удаления журнала.</span><span class="sxs-lookup"><span data-stu-id="bee0f-115">This is a one-time execution to remove the history.</span></span> <span data-ttu-id="bee0f-116">Для выполнения повторяющегося задания создайте план обслуживания с заданием очистки и расписание для него.</span><span class="sxs-lookup"><span data-stu-id="bee0f-116">If a reoccurring job is needed, create and schedule a maintenance plan with a cleanup job.</span></span>  
  
 <span data-ttu-id="bee0f-117">**Срок давности**</span><span class="sxs-lookup"><span data-stu-id="bee0f-117">**Older than**</span></span>  
 <span data-ttu-id="bee0f-118">Срок, в течение которого агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] хранит записи.</span><span class="sxs-lookup"><span data-stu-id="bee0f-118">Sets the amount of time that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent will retain entries.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bee0f-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="bee0f-119">See Also</span></span>  
 [<span data-ttu-id="bee0f-120">Журнал ошибок агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="bee0f-120">SQL Server Agent Error Log</span></span>](sql-server-agent-error-log.md)  
  
  
