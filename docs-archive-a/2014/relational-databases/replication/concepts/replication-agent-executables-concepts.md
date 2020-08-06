---
title: Основные понятия исполняемых файлов агента репликации | Документация Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: reference
helpviewer_keywords:
- programming interfaces [SQL Server replication]
- programming [SQL Server replication], agents
- replication [SQL Server], agents and profiles
- agents [SQL Server replication], executables
- command prompt [SQL Server replication]
ms.assetid: cba476df-d4ea-44c9-bb86-81488971e328
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 73f9fe0d1a98fa1afc813cd113dcced685b4f98a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750752"
---
# <a name="replication-agent-executables-concepts"></a><span data-ttu-id="de9bf-102">Основные понятия исполняемых файлов агента репликации</span><span class="sxs-lookup"><span data-stu-id="de9bf-102">Replication Agent Executables Concepts</span></span>
  <span data-ttu-id="de9bf-103">Управление агентами репликации может осуществляться программным путем следующими способами:</span><span class="sxs-lookup"><span data-stu-id="de9bf-103">Replication agents can be controlled programmatically in the following ways:</span></span>  
  
-   <span data-ttu-id="de9bf-104">использованием управляемых программных интерфейсов агента в пространстве имен <xref:Microsoft.SqlServer.Replication>;</span><span class="sxs-lookup"><span data-stu-id="de9bf-104">Using the managed agent programming interfaces in the <xref:Microsoft.SqlServer.Replication> Namespace.</span></span>  
  
-   <span data-ttu-id="de9bf-105">вызовом исполняемых файлов агента из командной строки с предоставленным набором параметров.</span><span class="sxs-lookup"><span data-stu-id="de9bf-105">Invoking agent executable files from the command prompt with a supplied set of parameters.</span></span>  
  
 <span data-ttu-id="de9bf-106">Непосредственный вызов агентов репликации из командной строки позволяет использовать агенты для доступа к ним программным путем из пакетных файлов сценариев командной строки.</span><span class="sxs-lookup"><span data-stu-id="de9bf-106">Directly invoking replication agents from the command prompt enables agents to be programmatically accessed from command-line scripting in batch files.</span></span> <span data-ttu-id="de9bf-107">Если агент вызван из командной строки, то выполняется в учетной записи системы безопасности [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows того пользователя, который вызвал агента или запустил пакетный файл.</span><span class="sxs-lookup"><span data-stu-id="de9bf-107">When an agent is invoked from the command prompt, it runs under the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows security account of the user that invoked the agent or started the batch file.</span></span>  
  
 <span data-ttu-id="de9bf-108">С применением исполняемых файлов можно запускать экземпляры следующих агентов репликации.</span><span class="sxs-lookup"><span data-stu-id="de9bf-108">Instances of the following replication agents can be run using executable files.</span></span>  
  
-   [<span data-ttu-id="de9bf-109">Replication Distribution Agent</span><span class="sxs-lookup"><span data-stu-id="de9bf-109">Replication Distribution Agent</span></span>](../agents/replication-distribution-agent.md)  
  
-   [<span data-ttu-id="de9bf-110">Агент чтения журнала репликации</span><span class="sxs-lookup"><span data-stu-id="de9bf-110">Replication Log Reader Agent</span></span>](../agents/replication-log-reader-agent.md)  
  
-   [<span data-ttu-id="de9bf-111">Replication Merge Agent</span><span class="sxs-lookup"><span data-stu-id="de9bf-111">Replication Merge Agent</span></span>](../agents/replication-merge-agent.md)  
  
-   [<span data-ttu-id="de9bf-112">Replication Queue Reader Agent</span><span class="sxs-lookup"><span data-stu-id="de9bf-112">Replication Queue Reader Agent</span></span>](../agents/replication-queue-reader-agent.md)  
  
-   [<span data-ttu-id="de9bf-113">Replication Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="de9bf-113">Replication Snapshot Agent</span></span>](../agents/replication-snapshot-agent.md)  
  
 <span data-ttu-id="de9bf-114">При вызове агентов репликации можно использовать профили производительности для автоматической передачи определенного набора параметров для исполняемого файла агента.</span><span class="sxs-lookup"><span data-stu-id="de9bf-114">When invoking replication agents, you can use performance profiles to automatically pass a defined set of parameters to the agent executable.</span></span> <span data-ttu-id="de9bf-115">Дополнительные сведения см. в статье [Replication Agent Profiles](../agents/replication-agent-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="de9bf-115">For more information, see [Replication Agent Profiles](../agents/replication-agent-profiles.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="de9bf-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="de9bf-116">Examples</span></span>  
 <span data-ttu-id="de9bf-117">В следующих примерах показано, как вызывать агенты репликации из командной строки.</span><span class="sxs-lookup"><span data-stu-id="de9bf-117">The following examples show how to invoke replication agents from the command prompt.</span></span> <span data-ttu-id="de9bf-118">Агенты репликации могут быть также вызваны с использованием объектов RMO.</span><span class="sxs-lookup"><span data-stu-id="de9bf-118">Replication agents can also be invoked using Replication Management Objects (RMO).</span></span> <span data-ttu-id="de9bf-119">Дополнительные сведения см. в статье [Синхронизация подписок (репликация)](../synchronize-data.md).</span><span class="sxs-lookup"><span data-stu-id="de9bf-119">For more information, see [Synchronize Subscriptions &#40;Replication&#41;](../synchronize-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="de9bf-120">Символы обозначения конца строки в этих примерах были добавлены для повышения удобства чтения.</span><span class="sxs-lookup"><span data-stu-id="de9bf-120">Line breaks in these examples were added to improve readability.</span></span> <span data-ttu-id="de9bf-121">В пакетном файле команды необходимо вводить в одной строке.</span><span class="sxs-lookup"><span data-stu-id="de9bf-121">In a batch file, commands must be made in a single line.</span></span>  
  
### <a name="running-the-snapshot-agent"></a><span data-ttu-id="de9bf-122">Управление агентом моментальных снимков</span><span class="sxs-lookup"><span data-stu-id="de9bf-122">Running the Snapshot Agent</span></span>  
 <span data-ttu-id="de9bf-123">Этот пример пакетного файла вызывает агент моментальных снимков из командной строки для создания моментального снимка публикации **AdvWorksSalesOrdersMerge**.</span><span class="sxs-lookup"><span data-stu-id="de9bf-123">This example batch file invokes the Snapshot Agent from the command prompt to generate a snapshot for the **AdvWorksSalesOrdersMerge** publication.</span></span>  
  
```  
REM -- Declare variables  
SET Publisher=%InstanceName%;  
SET PublicationDB=AdventureWorks2012;   
SET Publication=AdvWorksSalesOrdersMerge;   
  
REM --Start the Snapshot Agent to generate the snapshot for AdvWorksSalesOrdersMerge.  
"C:\Program Files\Microsoft SQL Server\120\COM\SNAPSHOT.EXE" -Publication %Publication%   
-Publisher %Publisher% -Distributor %Publisher% -PublisherDB %PublicationDB%   
-ReplicationType 2 -OutputVerboseLevel 1 -DistributorSecurityMode 1 ;  
  
```  
  
### <a name="running-the-distribution-agent"></a><span data-ttu-id="de9bf-124">Управление агентом распространителя</span><span class="sxs-lookup"><span data-stu-id="de9bf-124">Running the Distribution Agent</span></span>  
 <span data-ttu-id="de9bf-125">Этот пример пакетного файла вызывает агент распространителя из командной строки для непрерывной репликации изменений из публикации **AdvWorksProductTran** подписчику с принудительной подпиской.</span><span class="sxs-lookup"><span data-stu-id="de9bf-125">This example batch file invokes the Distribution Agent from the command prompt to continuously replicate changes from the **AdvWorksProductTran** publication to a push subscriber.</span></span>  
  
```  
REM -- Declare the variables.  
SET Publisher=%instancename%;  
SET Subscriber=%instancename%;  
SET PublicationDB=AdventureWorks2012;  
SET SubscriptionDB=AdventureWorks2012Replica;   
SET Publication=AdvWorksProductsTran;  
  
REM -- Start the Distribution Agent with four subscription streams.  
REM -- The following command must be supplied without line breaks.  
"C:\Program Files\Microsoft SQL Server\120\COM\DISTRIB.EXE" -Subscriber %Subscriber%   
-SubscriberDB %SubscriptionDB% -SubscriberSecurityMode 1 -Publication %Publication%   
-Publisher %Publisher% -PublisherDB %PublicationDB% -Distributor %Publisher%   
-DistributorSecurityMode 1 -Continuous -SubscriptionType 0 -SubscriptionStreams 4 ;  
  
```  
  
### <a name="running-the-merge-agent"></a><span data-ttu-id="de9bf-126">Управление агентом слияния</span><span class="sxs-lookup"><span data-stu-id="de9bf-126">Running the Merge Agent</span></span>  
 <span data-ttu-id="de9bf-127">Этот пример пакетного файла вызывает агент слияния из командной строки для синхронизации подписки по запросу для публикации **AdvWorksSalesOrdersMerge**.</span><span class="sxs-lookup"><span data-stu-id="de9bf-127">This example batch file invokes the Merge Agent from the command prompt to synchronize a pull subscription to the **AdvWorksSalesOrdersMerge** publication.</span></span>  
  
```  
REM -- Declare the variables.  
SET Publisher=%instancename%;  
SET Subscriber=%instancename%;  
SET PublicationDB=AdventureWorks2012;  
SET SubscriptionDB=AdventureWorks2012Replica;   
SET Publication=AdvWorksSalesOrdersMerge;  
  
REM --Start the Merge Agent with concurrent upload and download processes.  
REM -- The following command must be supplied without line breaks.  
"C:\Program Files\Microsoft SQL Server\120\COM\REPLMERG.EXE" -Publication %Publication%    
-Publisher %Publisher%  -Subscriber  %Subscriber%  -Distributor %Publisher%    
-PublisherDB %PublicationDB%  -SubscriberDB %SubscriptionDB% -PublisherSecurityMode 1    
-OutputVerboseLevel 2  -SubscriberSecurityMode 1  -SubscriptionType 1 -DistributorSecurityMode 1    
-Validate 3  -ParallelUploadDownload 1 ;  
  
```  
  
  
