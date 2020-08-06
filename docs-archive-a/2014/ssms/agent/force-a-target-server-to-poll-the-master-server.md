---
title: Принудительный опрос главного сервера целевым сервером | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- forcing master server polling
- polling master servers [SQL Server]
- master servers [SQL Server], polling
- target servers [SQL Server], polling the master server
ms.assetid: f1189a47-5ac3-45e2-9c5f-847810672279
author: stevestein
ms.author: sstein
ms.openlocfilehash: b37bf19bfe8e8fb55c29c8d94c28a341d06df5da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654730"
---
# <a name="force-a-target-server-to-poll-the-master-server"></a><span data-ttu-id="6aca3-102">Force a Target Server to Poll the Master Server</span><span class="sxs-lookup"><span data-stu-id="6aca3-102">Force a Target Server to Poll the Master Server</span></span>
  <span data-ttu-id="6aca3-103">В этом подразделе описана реализация принудительного опроса главного сервера целевым сервером.</span><span class="sxs-lookup"><span data-stu-id="6aca3-103">This topic describes how to force a target server to poll the master server.</span></span> <span data-ttu-id="6aca3-104">Целевой сервер должен быть зарегистрирован на главном.</span><span class="sxs-lookup"><span data-stu-id="6aca3-104">The target server must be a registered server on the master server.</span></span>  
  
 <span data-ttu-id="6aca3-105">Задание — это указанная последовательность действий, выполняемых агентом [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6aca3-105">A job is a specified series of actions that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent performs.</span></span> <span data-ttu-id="6aca3-106">Многосерверное задание — это задание, которое главный сервер выполняет на одном или нескольких целевых серверах.</span><span class="sxs-lookup"><span data-stu-id="6aca3-106">A multiserver job is a job that a master server runs on one or more target servers.</span></span> <span data-ttu-id="6aca3-107">На каждом целевом сервере может одновременно выполняться только один экземпляр одного и того же задания.</span><span class="sxs-lookup"><span data-stu-id="6aca3-107">Each target server can run one instance of the same job at the same time.</span></span> <span data-ttu-id="6aca3-108">Каждый целевой сервер периодически опрашивает главный сервер, загружает копию новых назначенных ему заданий и отключается.</span><span class="sxs-lookup"><span data-stu-id="6aca3-108">Each target server periodically polls the master server, downloads a copy of any new jobs assigned to the target server, and then disconnects.</span></span> <span data-ttu-id="6aca3-109">Целевой сервер выполняет задание локально, а затем снова подключается к главному серверу, чтобы передать результирующее состояние задания.</span><span class="sxs-lookup"><span data-stu-id="6aca3-109">The target server runs the job locally and then reconnects to the master server to upload the job outcome status.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6aca3-110">Если главный сервер недоступен в момент, когда целевой сервер пытается передать состояние задания, то сведения о состоянии задания помещаются в очередь, пока главный сервер не станет доступен.</span><span class="sxs-lookup"><span data-stu-id="6aca3-110">If the master server is inaccessible when the target server tries to upload job status, the job status is spooled until the master server can be accessed.</span></span>  
  
-   <span data-ttu-id="6aca3-111">**Перед началом работы**  [Ограничения](#Restrictions), [Безопасность](#Security)</span><span class="sxs-lookup"><span data-stu-id="6aca3-111">**Before you begin:**  [Limitations and Restrictions](#Restrictions), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="6aca3-112">**Для принудительного опроса главного сервера целевым сервером используется:**  [Среда SQL Server Management Studio](#SSMS)</span><span class="sxs-lookup"><span data-stu-id="6aca3-112">**To force a target server to poll the master server, using:**  [SQL Server Management Studio](#SSMS)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6aca3-113">Перед началом</span><span class="sxs-lookup"><span data-stu-id="6aca3-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="6aca3-114">Ограничения</span><span class="sxs-lookup"><span data-stu-id="6aca3-114">Limitations and Restrictions</span></span>  
 <span data-ttu-id="6aca3-115">Целевой сервер должен быть зарегистрирован на главном.</span><span class="sxs-lookup"><span data-stu-id="6aca3-115">The target server must be a registered server on the master server.</span></span> <span data-ttu-id="6aca3-116">Инструкции, приведенные в этом разделе, необходимо запускать с главного сервера.</span><span class="sxs-lookup"><span data-stu-id="6aca3-116">You must run the instructions given in this topic from the master server.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6aca3-117">безопасность</span><span class="sxs-lookup"><span data-stu-id="6aca3-117">Security</span></span>  
 <span data-ttu-id="6aca3-118">Дополнительные сведения см. в разделах [Implement SQL Server Agent Security](implement-sql-server-agent-security.md) и [Choose the Right SQL Server Agent Service Account for Multiserver Environments](choose-the-right-sql-server-agent-service-account-for-multiserver-environments.md).</span><span class="sxs-lookup"><span data-stu-id="6aca3-118">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md) and [Choose the Right SQL Server Agent Service Account for Multiserver Environments](choose-the-right-sql-server-agent-service-account-for-multiserver-environments.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="6aca3-119">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6aca3-119">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="6aca3-120">**Принудительный опрос главного сервера целевым сервером**</span><span class="sxs-lookup"><span data-stu-id="6aca3-120">**To force a target server to poll the master server**</span></span>  
  
1.  <span data-ttu-id="6aca3-121">В **Обозревателе объектов**разверните главный сервер.</span><span class="sxs-lookup"><span data-stu-id="6aca3-121">In **Object Explorer**, expand the master server.</span></span>  
  
2.  <span data-ttu-id="6aca3-122">Щелкните правой кнопкой мыши элемент **Агент SQL Server**, укажите пункт **Администрирование нескольких серверов**, а затем выберите пункт **Управление целевыми серверами**.</span><span class="sxs-lookup"><span data-stu-id="6aca3-122">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Manage Target Servers**.</span></span>  
  
3.  <span data-ttu-id="6aca3-123">Щелкните целевой сервер, а затем нажмите кнопку **Опрос**.</span><span class="sxs-lookup"><span data-stu-id="6aca3-123">Click a target server, and then click **Force Poll**.</span></span>  
  
  
