---
title: Запись состояния задания в журнал приложений Windows | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- status information [SQL Server], jobs
- SQL Server Agent jobs, status
- writing job status to log
- jobs [SQL Server Agent], status
- logs [SQL Server], jobs
ms.assetid: 3b813702-8f61-40ec-bf3b-ce9deb7e68be
author: stevestein
ms.author: sstein
ms.openlocfilehash: 67bdd7948d1722e49976d5e48b571c684431cd1c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734882"
---
# <a name="write-the-job-status-to-the-windows-application-log"></a><span data-ttu-id="f9076-102">Write the Job Status to the Windows Application Log</span><span class="sxs-lookup"><span data-stu-id="f9076-102">Write the Job Status to the Windows Application Log</span></span>
  <span data-ttu-id="f9076-103">В этом разделе описывается настройка [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] агента в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] для записи состояния задания в журнал событий приложений Windows с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] или управляющие объекты SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f9076-103">This topic describes how to configure [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] to write job status to the Windows application event log by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="f9076-104">Ответы заданий дают гарантию того, что администраторы базы данных будут знать о завершении выполнения заданий и частоте их выполнения.</span><span class="sxs-lookup"><span data-stu-id="f9076-104">Job responses ensure that database administrators know when jobs complete and how frequently they run.</span></span> <span data-ttu-id="f9076-105">Обычными ответами заданий являются следующие.</span><span class="sxs-lookup"><span data-stu-id="f9076-105">Typical job responses include:</span></span>  
  
-   <span data-ttu-id="f9076-106">Уведомление оператора с помощью электронной почты, системы пейджинга или сообщения **net send** .</span><span class="sxs-lookup"><span data-stu-id="f9076-106">Notifying the operator by using e-mail, electronic paging, or a **net send** message.</span></span> <span data-ttu-id="f9076-107">Используйте один из этих ответов на задание, если оператор должен выполнить последующие действия.</span><span class="sxs-lookup"><span data-stu-id="f9076-107">Use one of these job responses if the operator must perform a follow-up action.</span></span> <span data-ttu-id="f9076-108">Например, после успешного выполнения задания резервного копирования оператор должен получить напоминание об удалении магнитной ленты с резервной копией и сохранении ее в безопасном месте.</span><span class="sxs-lookup"><span data-stu-id="f9076-108">For example, if a backup job completes successfully, the operator must be notified to remove the backup tape and store it in a safe location.</span></span>  
  
-   <span data-ttu-id="f9076-109">Запись сообщений о событиях в журнал приложений Windows.</span><span class="sxs-lookup"><span data-stu-id="f9076-109">Writing an event message to the Windows application log.</span></span> <span data-ttu-id="f9076-110">Этот ответ можно использовать только для неудачно завершившихся заданий.</span><span class="sxs-lookup"><span data-stu-id="f9076-110">You can use this response only for failed jobs.</span></span>  
  
-   <span data-ttu-id="f9076-111">Автоматическое удаление задания.</span><span class="sxs-lookup"><span data-stu-id="f9076-111">Automatically deleting the job.</span></span> <span data-ttu-id="f9076-112">Используйте этот ответ только тогда, когда есть уверенность в том, что не понадобится выполнять это задание повторно.</span><span class="sxs-lookup"><span data-stu-id="f9076-112">Use this job response if you are certain that you do not need to rerun this job.</span></span>  
  
 <span data-ttu-id="f9076-113">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="f9076-113">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f9076-114">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="f9076-114">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f9076-115">Безопасность</span><span class="sxs-lookup"><span data-stu-id="f9076-115">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f9076-116">**Для записи состояния задания в журнал приложений Windows используется:**</span><span class="sxs-lookup"><span data-stu-id="f9076-116">**To write the job status to the Windows application log, using:**</span></span>  
  
     [<span data-ttu-id="f9076-117">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f9076-117">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="f9076-118">Управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="f9076-118">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f9076-119">Перед началом</span><span class="sxs-lookup"><span data-stu-id="f9076-119">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f9076-120">безопасность</span><span class="sxs-lookup"><span data-stu-id="f9076-120">Security</span></span>  
 <span data-ttu-id="f9076-121">Дополнительные сведения см. в разделе [Обеспечение безопасности агента SQL Server](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="f9076-121">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="f9076-122">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f9076-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-write-job-status-to-the-windows-application-log"></a><span data-ttu-id="f9076-123">Запись данных о состоянии задания в журнал приложений Windows</span><span class="sxs-lookup"><span data-stu-id="f9076-123">To write job status to the Windows application log</span></span>  
  
1.  <span data-ttu-id="f9076-124">В **обозревателе объектов** подключитесь к экземпляру [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , а затем разверните этот экземпляр.</span><span class="sxs-lookup"><span data-stu-id="f9076-124">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="f9076-125">Разверните узел **Агент SQL Server**, выберите раздел **Задания**, щелкните правой кнопкой мыши задание, которое нужно изменить, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="f9076-125">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to edit, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="f9076-126">Выберите страницу **Уведомления** .</span><span class="sxs-lookup"><span data-stu-id="f9076-126">Select the **Notifications** page.</span></span>  
  
4.  <span data-ttu-id="f9076-127">Установите флажок **Запись в журнал событий приложений Windows**, а затем выберите:</span><span class="sxs-lookup"><span data-stu-id="f9076-127">Check **Write to Windows application event log**, and choose one of the following:</span></span>  
  
    -   <span data-ttu-id="f9076-128">**При успешном завершении задания**для регистрации успешных завершений задания.</span><span class="sxs-lookup"><span data-stu-id="f9076-128">Click**When the job succeeds**to log the job status when the job completes successfully.</span></span>  
  
    -   <span data-ttu-id="f9076-129">**При ошибке задания**для регистрации завершений задания с ошибками.</span><span class="sxs-lookup"><span data-stu-id="f9076-129">Click**When the job fails**to log the job status when the job completes unsuccessfully.</span></span>  
  
    -   <span data-ttu-id="f9076-130">**При завершении задания** для регистрации любых состояний завершения задания.</span><span class="sxs-lookup"><span data-stu-id="f9076-130">Click**When the job completes** to log the job status regardless of completion status.</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="f9076-131">Использование управляющие объекты SQL Server</span><span class="sxs-lookup"><span data-stu-id="f9076-131">Using SQL Server Management Objects</span></span>  

### <a name="to-write-job-status-to-the-windows-application-log"></a><span data-ttu-id="f9076-132">Запись данных о состоянии задания в журнал приложений Windows</span><span class="sxs-lookup"><span data-stu-id="f9076-132">To write job status to the Windows application log</span></span>
  
 <span data-ttu-id="f9076-133">Вызовите свойство `EventLogLevel` класса `Job`, используя выбранный язык программирования, например Visual Basic, Visual C# или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f9076-133">Call the `EventLogLevel` property of the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
  
 <span data-ttu-id="f9076-134">В следующем примере кода для задания задается создание записи в журнале событий операционной системы после завершения выполнения задания.</span><span class="sxs-lookup"><span data-stu-id="f9076-134">The following code example sets the job to generate an operating system event log entry when the job execution finishes.</span></span>  
  
```powershell
$srv = new-object Microsoft.SqlServer.Management.Smo.Server("(local)")  
$jb = new-object Microsoft.SqlServer.Management.Smo.Agent.Job($srv.JobServer, "Test Job")  
$jb.EventLogLevel = [Microsoft.SqlServer.Management.Smo.Agent.CompletionAction]::Always  
```  
