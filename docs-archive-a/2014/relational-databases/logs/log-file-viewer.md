---
title: Средство просмотра журналов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- Log File Viewer
ms.assetid: a4ea7fc8-1cb2-4c98-bc86-8991c5e748b2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5139a32838070b817fce3bccf22b9fe08b5012e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658251"
---
# <a name="log-file-viewer"></a><span data-ttu-id="f9714-102">Средство просмотра файлов журнала</span><span class="sxs-lookup"><span data-stu-id="f9714-102">Log File Viewer</span></span>
  <span data-ttu-id="f9714-103">Средство просмотра журнала в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] служит для доступа к сведениям об ошибках и событиях, регистрируемых в файлах журналов.</span><span class="sxs-lookup"><span data-stu-id="f9714-103">Log File Viewer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] is used to access information about errors and events that are captured in log files.</span></span>  
  
## <a name="benefits-of-using-log-file-viewer"></a><span data-ttu-id="f9714-104">Преимущества использования средства просмотра журналов</span><span class="sxs-lookup"><span data-stu-id="f9714-104">Benefits of using Log File Viewer</span></span>  
 <span data-ttu-id="f9714-105">Можно просматривать файлы журнала [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на локальных и удаленных экземплярах [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , которые находятся вне сети или не могут запуститься.</span><span class="sxs-lookup"><span data-stu-id="f9714-105">You can view [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log files from a local or remote instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] when the target instance is offline or cannot start.</span></span> <span data-ttu-id="f9714-106">Получить доступ к файлам журналов вне сети можно в списке «Зарегистрированные серверы» или программным способом с помощью запросов WMI и WQL.</span><span class="sxs-lookup"><span data-stu-id="f9714-106">You can access the offline log files from Registered Servers, or programmatically through WMI and WQL (WMI Query Language) queries.</span></span> <span data-ttu-id="f9714-107">Дополнительные сведения см. в разделе [Просмотр автономных файлов журнала](view-offline-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="f9714-107">For more information, see [View Offline Log Files](view-offline-log-files.md).</span></span> <span data-ttu-id="f9714-108">Ниже приведены типы файлов журналов, которые можно открыть с помощью средства просмотра журналов.</span><span class="sxs-lookup"><span data-stu-id="f9714-108">Following are the types of log files you can access using Log File Viewer:</span></span>  
  
-   <span data-ttu-id="f9714-109">Коллекция аудита</span><span class="sxs-lookup"><span data-stu-id="f9714-109">Audit Collection</span></span>  
  
-   <span data-ttu-id="f9714-110">Сбор данных</span><span class="sxs-lookup"><span data-stu-id="f9714-110">Data Collection</span></span>  
  
-   <span data-ttu-id="f9714-111">Database Mail</span><span class="sxs-lookup"><span data-stu-id="f9714-111">Database Mail</span></span>  
  
-   <span data-ttu-id="f9714-112">Журнал заданий</span><span class="sxs-lookup"><span data-stu-id="f9714-112">Job History</span></span>  
  
-   <span data-ttu-id="f9714-113">Планы обслуживания</span><span class="sxs-lookup"><span data-stu-id="f9714-113">Maintenance Plans</span></span>  
  
-   <span data-ttu-id="f9714-114">Удаленные планы обслуживания</span><span class="sxs-lookup"><span data-stu-id="f9714-114">Remote Maintenance Plans</span></span>  
  
-   <span data-ttu-id="f9714-115">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f9714-115">SQL Server</span></span>  
  
-   <span data-ttu-id="f9714-116">Агент SQL Server</span><span class="sxs-lookup"><span data-stu-id="f9714-116">SQL Server Agent</span></span>  
  
-   <span data-ttu-id="f9714-117">Windows NT (это события Windows, также доступные из программы просмотра событий Windows)</span><span class="sxs-lookup"><span data-stu-id="f9714-117">Windows NT (These are Windows events that can also be accessed from Event Viewer.)</span></span>  
  
## <a name="log-file-viewer-tasks"></a><span data-ttu-id="f9714-118">Задачи средства просмотра журналов</span><span class="sxs-lookup"><span data-stu-id="f9714-118">Log File Viewer Tasks</span></span>  
  
|<span data-ttu-id="f9714-119">Описание задачи</span><span class="sxs-lookup"><span data-stu-id="f9714-119">Task Description</span></span>|<span data-ttu-id="f9714-120">Раздел</span><span class="sxs-lookup"><span data-stu-id="f9714-120">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="f9714-121">Описывает процедуру открытия средства просмотра журналов в зависимости от того, какие сведения нужно просмотреть.</span><span class="sxs-lookup"><span data-stu-id="f9714-121">Describes how to open Log File Viewer depending on the information that you want to view.</span></span>|[<span data-ttu-id="f9714-122">открыть средство просмотра журнала</span><span class="sxs-lookup"><span data-stu-id="f9714-122">Open Log File Viewer</span></span>](open-log-file-viewer.md)|  
|<span data-ttu-id="f9714-123">Описывает процедуру просмотра файлов журналов, находящихся в режиме вне сети, с помощью зарегистрированных серверов, а также процедуру проверки разрешений WMI.</span><span class="sxs-lookup"><span data-stu-id="f9714-123">Describes how to view offline log files through registered servers and how to verify WMI permissions.</span></span>|[<span data-ttu-id="f9714-124">Просмотр автономных файлов журнала</span><span class="sxs-lookup"><span data-stu-id="f9714-124">View Offline Log Files</span></span>](view-offline-log-files.md)|  
|<span data-ttu-id="f9714-125">Предоставляет справку F1 для средства просмотра журналов.</span><span class="sxs-lookup"><span data-stu-id="f9714-125">Provides Log File Viewer F1 Help.</span></span>|[<span data-ttu-id="f9714-126">Справка средства просмотра журнала F1</span><span class="sxs-lookup"><span data-stu-id="f9714-126">Log File Viewer F1 Help</span></span>](log-file-viewer-f1-help.md)|  
  
## <a name="see-also"></a><span data-ttu-id="f9714-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="f9714-127">See Also</span></span>  
 <span data-ttu-id="f9714-128">[Подсистема аудита SQL Server (компонент Database Engine)](../security/auditing/sql-server-audit-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="f9714-128">[SQL Server Audit &#40;Database Engine&#41;](../security/auditing/sql-server-audit-database-engine.md) </span></span>  
 [<span data-ttu-id="f9714-129">Журнал ошибок агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="f9714-129">SQL Server Agent Error Log</span></span>](../../ssms/agent/sql-server-agent-error-log.md)  
  
  
