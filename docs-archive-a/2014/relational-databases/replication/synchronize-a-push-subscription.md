---
title: Синхронизация принудительной подписки | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- synchronization [SQL Server replication], push subscriptions
- subscriptions [SQL Server replication], push
- push subscriptions [SQL Server replication], synchronizing
ms.assetid: 0cfa7ae5-91d3-4a4f-9edf-a852d45783b5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5fb2f7bd961748272d6cd67e3412b09d9370a6f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732558"
---
# <a name="synchronize-a-push-subscription"></a><span data-ttu-id="f931d-102">Синхронизация принудительной подписки</span><span class="sxs-lookup"><span data-stu-id="f931d-102">Synchronize a Push Subscription</span></span>
  <span data-ttu-id="f931d-103">В данном разделе описывается синхронизация принудительной подписки в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [агентов репликации](agents/replication-agents-overview.md)или объектов RMO.</span><span class="sxs-lookup"><span data-stu-id="f931d-103">This topic describes how to synchronize a push subscription in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [replication agents](agents/replication-agents-overview.md), or Replication Management Objects (RMO).</span></span>  
  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f931d-104">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f931d-104">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="f931d-105">Подписки синхронизируются агентом распространителя (для репликации моментальных снимков и репликации транзакций) или агентом слияния (для репликации слиянием).</span><span class="sxs-lookup"><span data-stu-id="f931d-105">Subscriptions are synchronized by the Distribution Agent (for snapshot and transactional replication) or the Merge Agent (for merge replication).</span></span> <span data-ttu-id="f931d-106">Агенты могут работать непрерывно, запускаться по запросу или по расписанию.</span><span class="sxs-lookup"><span data-stu-id="f931d-106">Agents can run continuously, run on demand, or run on a schedule.</span></span> <span data-ttu-id="f931d-107">Дополнительные сведения о настройке расписаний синхронизации см. в [этой статье](specify-synchronization-schedules.md).</span><span class="sxs-lookup"><span data-stu-id="f931d-107">For more information about specifying synchronization schedules, see [Specify Synchronization Schedules](specify-synchronization-schedules.md).</span></span>  
  
 <span data-ttu-id="f931d-108">Синхронизируйте подписки по запросу из папок **Локальные публикации** и **Локальные подписки** в среде [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] и **Все подписки** в мониторе репликации.</span><span class="sxs-lookup"><span data-stu-id="f931d-108">Synchronize a subscription on demand from the **Local Publications** and **Local Subscriptions** folders in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and the **All Subscriptions** tab in Replication Monitor.</span></span> <span data-ttu-id="f931d-109">Подписки на публикации Oracle не синхронизируются по запросу подписчика.</span><span class="sxs-lookup"><span data-stu-id="f931d-109">Subscriptions to Oracle publications cannot be synchronized on demand from the Subscriber.</span></span> <span data-ttu-id="f931d-110">Сведения о запуске монитора репликации см. в [этой статье](monitor/start-the-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="f931d-110">For information about starting Replication Monitor, see [Start the Replication Monitor](monitor/start-the-replication-monitor.md).</span></span>  
  
#### <a name="to-synchronize-a-push-subscription-on-demand-in-management-studio-at-the-publisher"></a><span data-ttu-id="f931d-111">Синхронизация принудительной подписки по запросу в среде Management Studio (на издателе)</span><span class="sxs-lookup"><span data-stu-id="f931d-111">To synchronize a push subscription on demand in Management Studio (at the Publisher)</span></span>  
  
1.  <span data-ttu-id="f931d-112">Подключитесь к издателю в среде [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], а затем раскройте узел сервера.</span><span class="sxs-lookup"><span data-stu-id="f931d-112">Connect to the Publisher in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="f931d-113">Раскройте папку **Репликация** , а затем папку **Локальные публикации** .</span><span class="sxs-lookup"><span data-stu-id="f931d-113">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="f931d-114">Разверните публикацию, для которой хотите выполнить синхронизацию подписок.</span><span class="sxs-lookup"><span data-stu-id="f931d-114">Expand the publication for which you want to synchronize subscriptions.</span></span>  
  
4.  <span data-ttu-id="f931d-115">Щелкните подписку правой кнопкой мыши и выберите **Просмотреть состояние синхронизации**.</span><span class="sxs-lookup"><span data-stu-id="f931d-115">Right-click the subscription you want to synchronize, and then click **View Synchronization Status**.</span></span>  
  
5.  <span data-ttu-id="f931d-116">В диалоговом окне **Просмотр состояния синхронизации — \<Subscriber>:\<SubscriptionDatabase>** нажмите кнопку **Пуск**.</span><span class="sxs-lookup"><span data-stu-id="f931d-116">In the **View Synchronization Status - \<Subscriber>:\<SubscriptionDatabase>** dialog box, click **Start**.</span></span> <span data-ttu-id="f931d-117">Когда синхронизация будет завершена, появится сообщение **Синхронизация завершена** .</span><span class="sxs-lookup"><span data-stu-id="f931d-117">When synchronization is complete, the message **Synchronization completed** is displayed.</span></span>  
  
6.  <span data-ttu-id="f931d-118">Щелкните **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="f931d-118">Click **Close**.</span></span>  
  
#### <a name="to-synchronize-a-push-subscription-on-demand-in-management-studio-at-the-subscriber"></a><span data-ttu-id="f931d-119">Синхронизация принудительной подписки по запросу в среде Management Studio (на подписчике)</span><span class="sxs-lookup"><span data-stu-id="f931d-119">To synchronize a push subscription on demand in Management Studio (at the Subscriber)</span></span>  
  
1.  <span data-ttu-id="f931d-120">Подключитесь к подписчику в [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]и раскройте узел сервера.</span><span class="sxs-lookup"><span data-stu-id="f931d-120">Connect to the Subscriber in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="f931d-121">Раскройте папку **Репликация** , а затем — папку **Локальные подписки** .</span><span class="sxs-lookup"><span data-stu-id="f931d-121">Expand the **Replication** folder, and then expand the **Local Subscriptions** folder.</span></span>  
  
3.  <span data-ttu-id="f931d-122">Щелкните подписку правой кнопкой мыши и выберите **Просмотреть состояние синхронизации**.</span><span class="sxs-lookup"><span data-stu-id="f931d-122">Right-click the subscription you want to synchronize, and then click **View Synchronization Status**.</span></span>  
  
4.  <span data-ttu-id="f931d-123">Появится сообщение об установке соединения с распространителем.</span><span class="sxs-lookup"><span data-stu-id="f931d-123">A message is displayed about establishing a connection to the Distributor.</span></span> <span data-ttu-id="f931d-124">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f931d-124">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="f931d-125">В диалоговом окне **Просмотр состояния синхронизации — \<Subscriber>:\<SubscriptionDatabase>** нажмите кнопку **Пуск**.</span><span class="sxs-lookup"><span data-stu-id="f931d-125">In the **View Synchronization Status - \<Subscriber>:\<SubscriptionDatabase>** dialog box, click **Start**.</span></span> <span data-ttu-id="f931d-126">Когда синхронизация будет завершена, появится сообщение **Синхронизация завершена** .</span><span class="sxs-lookup"><span data-stu-id="f931d-126">When synchronization is complete, the message **Synchronization completed** is displayed.</span></span>  
  
6.  <span data-ttu-id="f931d-127">Щелкните **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="f931d-127">Click **Close**.</span></span>  
  
#### <a name="to-synchronize-a-push-subscription-on-demand-in-replication-monitor"></a><span data-ttu-id="f931d-128">Синхронизация принудительной подписки по запросу в мониторе репликации</span><span class="sxs-lookup"><span data-stu-id="f931d-128">To synchronize a push subscription on demand in Replication Monitor</span></span>  
  
1.  <span data-ttu-id="f931d-129">В мониторе репликации раскройте группу издателей на левой панели, раскройте нужного издателя, а затем выберите публикацию.</span><span class="sxs-lookup"><span data-stu-id="f931d-129">In Replication Monitor, expand a Publisher group in the left pane, expand a Publisher, and then click a publication.</span></span>  
  
2.  <span data-ttu-id="f931d-130">Перейдите на вкладку **Все подписки** .</span><span class="sxs-lookup"><span data-stu-id="f931d-130">Click the **All Subscriptions** tab.</span></span>  
  
3.  <span data-ttu-id="f931d-131">Щелкните правой кнопкой мыши подписку, которую хотите синхронизировать, а затем щелкните **Запустить синхронизацию**.</span><span class="sxs-lookup"><span data-stu-id="f931d-131">Right-click the subscription you want to synchronize, and then click **Start Synchronizing**.</span></span>  
  
4.  <span data-ttu-id="f931d-132">Чтобы просмотреть ход выполнения синхронизации, щелкните правой кнопкой мыши подписку, а затем щелкните **Просмотреть подробности**.</span><span class="sxs-lookup"><span data-stu-id="f931d-132">To view synchronization progress, right-click the subscription, and then click **View Details**.</span></span>  
  
##  <a name="using-replication-agents"></a><a name="ReplProg"></a> <span data-ttu-id="f931d-133">При помощи агентов репликации</span><span class="sxs-lookup"><span data-stu-id="f931d-133">Using Replication Agents</span></span>  
 <span data-ttu-id="f931d-134">Принудительные подписки можно синхронизировать программно и по требованию, с помощью вызова из командной строки нужного исполняемого файла агента репликации.</span><span class="sxs-lookup"><span data-stu-id="f931d-134">Push subscriptions can be synchronized programmatically and on-demand by invoking the appropriate replication agent executable file from the command prompt.</span></span> <span data-ttu-id="f931d-135">Вызываемый исполняемый файл агента репликации зависит от типа публикации, к которой принадлежит принудительная подписка.</span><span class="sxs-lookup"><span data-stu-id="f931d-135">The replication agent executable file that is invoked will depend on the type of publication to which the push subscription belongs.</span></span>  
  
#### <a name="to-start-the-distribution-agent-to-synchronize-a-push-subscription-to-a-transactional-publication"></a><span data-ttu-id="f931d-136">Запуск агента распространителя для синхронизации принудительной подписки на публикацию транзакций</span><span class="sxs-lookup"><span data-stu-id="f931d-136">To start the Distribution Agent to synchronize a push subscription to a transactional publication</span></span>  
  
1.  <span data-ttu-id="f931d-137">Выполните программу **distrib.exe**из командной строки или из пакетного файла на распространителе.</span><span class="sxs-lookup"><span data-stu-id="f931d-137">From the command prompt or in a batch file at the Distributor, execute **distrib.exe**.</span></span> <span data-ttu-id="f931d-138">Укажите следующие аргументы командной строки.</span><span class="sxs-lookup"><span data-stu-id="f931d-138">Specify the following command-line arguments:</span></span>  
  
    -   <span data-ttu-id="f931d-139">**-Publisher**</span><span class="sxs-lookup"><span data-stu-id="f931d-139">**-Publisher**</span></span>  
  
    -   <span data-ttu-id="f931d-140">**-PublisherDB**</span><span class="sxs-lookup"><span data-stu-id="f931d-140">**-PublisherDB**</span></span>  
  
    -   <span data-ttu-id="f931d-141">**-Distributor**</span><span class="sxs-lookup"><span data-stu-id="f931d-141">**-Distributor**</span></span>  
  
    -   <span data-ttu-id="f931d-142">**-Subscriber**</span><span class="sxs-lookup"><span data-stu-id="f931d-142">**-Subscriber**</span></span>  
  
    -   <span data-ttu-id="f931d-143">**-SubscriberDB**</span><span class="sxs-lookup"><span data-stu-id="f931d-143">**-SubscriberDB**</span></span>  
  
    -   <span data-ttu-id="f931d-144">**-SubscriptionType = 0**</span><span class="sxs-lookup"><span data-stu-id="f931d-144">**-SubscriptionType = 0**</span></span>  
  
     <span data-ttu-id="f931d-145">При использовании проверки подлинности SQL Server необходимо также указать следующие аргументы.</span><span class="sxs-lookup"><span data-stu-id="f931d-145">If you are using SQL Server Authentication, you must also specify the following arguments:</span></span>  
  
    -   <span data-ttu-id="f931d-146">**-DistributorLogin**</span><span class="sxs-lookup"><span data-stu-id="f931d-146">**-DistributorLogin**</span></span>  
  
    -   <span data-ttu-id="f931d-147">**-DistributorPassword**</span><span class="sxs-lookup"><span data-stu-id="f931d-147">**-DistributorPassword**</span></span>  
  
    -   <span data-ttu-id="f931d-148">**-DistributorSecurityMode = 0**</span><span class="sxs-lookup"><span data-stu-id="f931d-148">**-DistributorSecurityMode = 0**</span></span>  
  
    -   <span data-ttu-id="f931d-149">**-PublisherLogin**</span><span class="sxs-lookup"><span data-stu-id="f931d-149">**-PublisherLogin**</span></span>  
  
    -   <span data-ttu-id="f931d-150">**-PublisherPassword**</span><span class="sxs-lookup"><span data-stu-id="f931d-150">**-PublisherPassword**</span></span>  
  
    -   <span data-ttu-id="f931d-151">**-PublisherSecurityMode = 0**</span><span class="sxs-lookup"><span data-stu-id="f931d-151">**-PublisherSecurityMode = 0**</span></span>  
  
    -   <span data-ttu-id="f931d-152">**-SubscriberLogin**</span><span class="sxs-lookup"><span data-stu-id="f931d-152">**-SubscriberLogin**</span></span>  
  
    -   <span data-ttu-id="f931d-153">**-SubscriberPassword**</span><span class="sxs-lookup"><span data-stu-id="f931d-153">**-SubscriberPassword**</span></span>  
  
    -   <span data-ttu-id="f931d-154">**-SubscriberSecurityMode = 0**</span><span class="sxs-lookup"><span data-stu-id="f931d-154">**-SubscriberSecurityMode = 0**</span></span>  
  
        > [!IMPORTANT]  
        >  [!INCLUDE[ssNoteWinAuthentication](../../includes/ssnotewinauthentication-md.md)]  
  
#### <a name="to-start-the-merge-agent-to-synchronize-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="f931d-155">Запуск агента слияния для синхронизации принудительной подписки на публикацию слиянием</span><span class="sxs-lookup"><span data-stu-id="f931d-155">To start the Merge Agent to synchronize a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="f931d-156">Выполните программу **replmerg.exe**из командной строки или из пакетного файла на распространителе.</span><span class="sxs-lookup"><span data-stu-id="f931d-156">From the command prompt or in a batch file at the Distributor, execute **replmerg.exe**.</span></span> <span data-ttu-id="f931d-157">Укажите следующие аргументы командной строки.</span><span class="sxs-lookup"><span data-stu-id="f931d-157">Specify the following command-line arguments:</span></span>  
  
    -   <span data-ttu-id="f931d-158">**-Publisher**</span><span class="sxs-lookup"><span data-stu-id="f931d-158">**-Publisher**</span></span>  
  
    -   <span data-ttu-id="f931d-159">**-PublisherDB**</span><span class="sxs-lookup"><span data-stu-id="f931d-159">**-PublisherDB**</span></span>  
  
    -   <span data-ttu-id="f931d-160">**-Publication**</span><span class="sxs-lookup"><span data-stu-id="f931d-160">**-Publication**</span></span>  
  
    -   <span data-ttu-id="f931d-161">**-Distributor**</span><span class="sxs-lookup"><span data-stu-id="f931d-161">**-Distributor**</span></span>  
  
    -   <span data-ttu-id="f931d-162">**-Subscriber**</span><span class="sxs-lookup"><span data-stu-id="f931d-162">**-Subscriber**</span></span>  
  
    -   <span data-ttu-id="f931d-163">**-SubscriberDB**</span><span class="sxs-lookup"><span data-stu-id="f931d-163">**-SubscriberDB**</span></span>  
  
    -   <span data-ttu-id="f931d-164">**-SubscriptionType = 0**</span><span class="sxs-lookup"><span data-stu-id="f931d-164">**-SubscriptionType = 0**</span></span>  
  
     <span data-ttu-id="f931d-165">При использовании проверки подлинности SQL Server необходимо также указать следующие аргументы.</span><span class="sxs-lookup"><span data-stu-id="f931d-165">If you are using SQL Server Authentication, you must also specify the following arguments:</span></span>  
  
    -   <span data-ttu-id="f931d-166">**-DistributorLogin**</span><span class="sxs-lookup"><span data-stu-id="f931d-166">**-DistributorLogin**</span></span>  
  
    -   <span data-ttu-id="f931d-167">**-DistributorPassword**</span><span class="sxs-lookup"><span data-stu-id="f931d-167">**-DistributorPassword**</span></span>  
  
    -   <span data-ttu-id="f931d-168">**-DistributorSecurityMode = 0**</span><span class="sxs-lookup"><span data-stu-id="f931d-168">**-DistributorSecurityMode = 0**</span></span>  
  
    -   <span data-ttu-id="f931d-169">**-PublisherLogin**</span><span class="sxs-lookup"><span data-stu-id="f931d-169">**-PublisherLogin**</span></span>  
  
    -   <span data-ttu-id="f931d-170">**-PublisherPassword**</span><span class="sxs-lookup"><span data-stu-id="f931d-170">**-PublisherPassword**</span></span>  
  
    -   <span data-ttu-id="f931d-171">**-PublisherSecurityMode = 0**</span><span class="sxs-lookup"><span data-stu-id="f931d-171">**-PublisherSecurityMode = 0**</span></span>  
  
    -   <span data-ttu-id="f931d-172">**-SubscriberLogin**</span><span class="sxs-lookup"><span data-stu-id="f931d-172">**-SubscriberLogin**</span></span>  
  
    -   <span data-ttu-id="f931d-173">**-SubscriberPassword**</span><span class="sxs-lookup"><span data-stu-id="f931d-173">**-SubscriberPassword**</span></span>  
  
    -   <span data-ttu-id="f931d-174">**-SubscriberSecurityMode = 0**</span><span class="sxs-lookup"><span data-stu-id="f931d-174">**-SubscriberSecurityMode = 0**</span></span>  
  
        > [!IMPORTANT]  
        >  [!INCLUDE[ssNoteWinAuthentication](../../includes/ssnotewinauthentication-md.md)]  
  
###  <a name="examples-replication-agents"></a><a name="TsqlExample"></a> <span data-ttu-id="f931d-175">Примеры (агенты репликации)</span><span class="sxs-lookup"><span data-stu-id="f931d-175">Examples (Replication Agents)</span></span>  
 <span data-ttu-id="f931d-176">В следующем примере агент распространителя запускается для синхронизации принудительной подписки.</span><span class="sxs-lookup"><span data-stu-id="f931d-176">The following example starts the Distribution Agent to synchronize a push subscription.</span></span>  
  
 
```
REM -- Declare the variables.  
SET Publisher=%instancename%  
SET Subscriber=%instancename%  
SET PublicationDB=AdventureWorks2012  
SET SubscriptionDB=AdventureWorks2012Replica   
SET Publication=AdvWorksProductsTran  
  
REM -- Start the Distribution Agent with four subscription streams.  
REM -- The following command must be supplied without line breaks.  
"C:\Program Files\Microsoft SQL Server\120\COM\DISTRIB.EXE" -Subscriber %Subscriber%   
-SubscriberDB %SubscriptionDB% -SubscriberSecurityMode 1 -Publication %Publication%   
-Publisher %Publisher% -PublisherDB %PublicationDB% -Distributor %Publisher%   
-DistributorSecurityMode 1 -Continuous -SubscriptionType 0 -SubscriptionStreams 4
```
  
 <span data-ttu-id="f931d-177">В следующем примере агент слияния запускается для синхронизации принудительной подписки.</span><span class="sxs-lookup"><span data-stu-id="f931d-177">The following example starts the Merge Agent to synchronize a push subscription.</span></span>  

```
REM -- Declare the variables.  
SET Publisher=%instancename%  
SET Subscriber=%instancename%  
SET PublicationDB=AdventureWorks2012  
SET SubscriptionDB=AdventureWorks2012Replica   
SET Publication=AdvWorksSalesOrdersMerge  
  
REM -- Start the Merge Agent.  
REM -- The following command must be supplied without line breaks.  
"C:\Program Files\Microsoft SQL Server\120\COM\REPLMERG.EXE"  -Publisher %Publisher%   
-Subscriber  %Subscriber%  -Distributor %Publisher% -PublisherDB  %PublicationDB%   
-SubscriberDB %SubscriptionDB% -Publication %Publication% -PublisherSecurityMode 1   
-OutputVerboseLevel 3  -Output -SubscriberSecurityMode 1  -SubscriptionType 0   
-DistributorSecurityMode 1
```
  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="f931d-178">При помощи объектов RMO</span><span class="sxs-lookup"><span data-stu-id="f931d-178">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="f931d-179">Принудительные подписки можно синхронизировать программно с помощью объектов RMO и доступа к функциональности агента репликации из управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="f931d-179">You can synchronize push subscriptions programmatically by using Replication Management Objects (RMO) and managed code access to replication agent functionalities.</span></span> <span data-ttu-id="f931d-180">Конкретные классы, используемые для синхронизации, зависят от типа публикации, к которой принадлежит подписка.</span><span class="sxs-lookup"><span data-stu-id="f931d-180">The classes that you use to synchronize a push subscription depend on the type of publication to which the subscription belongs.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f931d-181">Если нужно выполнить синхронизацию, которая выполняется автономно и не влияет на ваше приложение, запустите агент асинхронно.</span><span class="sxs-lookup"><span data-stu-id="f931d-181">If you want to start a synchronization that runs autonomously without affecting your application, start the agent asynchronously.</span></span> <span data-ttu-id="f931d-182">Однако если нужно наблюдать за результатами синхронизации и получать обратные вызовы от агента во время процесса синхронизации (например, если нужно отображать индикатор выполнения), то следует запускать агент синхронно.</span><span class="sxs-lookup"><span data-stu-id="f931d-182">However, if you want to monitor the outcome of the synchronization and receive callbacks from the agent during the synchronization process (for example, if you want to display a progress bar), you should start the agent synchronously.</span></span> <span data-ttu-id="f931d-183">Для подписчиков [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)] также необходимо запускать агент синхронно.</span><span class="sxs-lookup"><span data-stu-id="f931d-183">For [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)] Subscribers, you must start the agent synchronously.</span></span>  
  
#### <a name="to-synchronize-a-push-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="f931d-184">Синхронизация принудительной подписки на публикацию моментальных снимков или транзакций</span><span class="sxs-lookup"><span data-stu-id="f931d-184">To synchronize a push subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="f931d-185">Создайте соединение с распространителем с помощью класса <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="f931d-185">Create a connection to the Distributor by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="f931d-186">Создайте экземпляр класса <xref:Microsoft.SqlServer.Replication.TransSubscription> и укажите следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="f931d-186">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransSubscription> class and set the following properties:</span></span>  
  
    -   <span data-ttu-id="f931d-187">имя базы данных публикации в свойстве <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>;</span><span class="sxs-lookup"><span data-stu-id="f931d-187">The publication database name for <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>.</span></span>  
  
    -   <span data-ttu-id="f931d-188">имя публикации, к которой принадлежит подписка, в свойстве <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>;</span><span class="sxs-lookup"><span data-stu-id="f931d-188">The name of the publication to which the subscription belongs for <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>.</span></span>  
  
    -   <span data-ttu-id="f931d-189">имя базы данных подписки в свойстве <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>;</span><span class="sxs-lookup"><span data-stu-id="f931d-189">The name of the subscription database for <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>.</span></span>  
  
    -   <span data-ttu-id="f931d-190">имя подписчика в свойстве <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>;</span><span class="sxs-lookup"><span data-stu-id="f931d-190">The name of the Subscriber for <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>.</span></span>  
  
    -   <span data-ttu-id="f931d-191">соединение, созданное на шаге 1, в свойстве <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="f931d-191">The connection created in step 1 for <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span></span>  
  
3.  <span data-ttu-id="f931d-192">Вызовите метод <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> , чтобы получить остальные свойства подписки.</span><span class="sxs-lookup"><span data-stu-id="f931d-192">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the remaining subscription properties.</span></span> <span data-ttu-id="f931d-193">Если этот метод возвращает значение `false`, проверьте, существует ли подписка.</span><span class="sxs-lookup"><span data-stu-id="f931d-193">If this method returns `false`, verify that the subscription exists.</span></span>  
  
4.  <span data-ttu-id="f931d-194">На распространителе запустите агент распространителя одним из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="f931d-194">Start the Distribution Agent at the Distributor in one of the following ways:</span></span>  
  
    -   <span data-ttu-id="f931d-195">Вызовите метод <xref:Microsoft.SqlServer.Replication.TransSubscription.SynchronizeWithJob%2A> экземпляра класса <xref:Microsoft.SqlServer.Replication.TransSubscription> , созданного на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="f931d-195">Call the <xref:Microsoft.SqlServer.Replication.TransSubscription.SynchronizeWithJob%2A> method on the instance of <xref:Microsoft.SqlServer.Replication.TransSubscription> from step 2.</span></span> <span data-ttu-id="f931d-196">Этот метод запускает агент распространителя асинхронно, а управление сразу после его вызова передается обратно приложению; задание агента при этом продолжает выполняться.</span><span class="sxs-lookup"><span data-stu-id="f931d-196">This method starts the Distribution Agent asynchronously, and control immediately returns to your application while the agent job is running.</span></span> <span data-ttu-id="f931d-197">Этот метод нельзя вызвать, если при создании подписки свойству <xref:Microsoft.SqlServer.Replication.Subscription.CreateSyncAgentByDefault%2A> было присвоено значение `false`.</span><span class="sxs-lookup"><span data-stu-id="f931d-197">You cannot call this method if the subscription was created with a value of `false` for <xref:Microsoft.SqlServer.Replication.Subscription.CreateSyncAgentByDefault%2A>.</span></span>  
  
    -   <span data-ttu-id="f931d-198">Получите экземпляр класса <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent> из свойства <xref:Microsoft.SqlServer.Replication.TransSubscription.SynchronizationAgent%2A> и вызовите метод <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Synchronize%2A> .</span><span class="sxs-lookup"><span data-stu-id="f931d-198">Obtain an instance of the <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent> class from the <xref:Microsoft.SqlServer.Replication.TransSubscription.SynchronizationAgent%2A> property, and call the <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Synchronize%2A> method.</span></span> <span data-ttu-id="f931d-199">Этот метод запускает агент синхронно, и управление не возвращается приложению до тех пор, пока выполнение задания агента не будет завершено.</span><span class="sxs-lookup"><span data-stu-id="f931d-199">This method starts the agent synchronously, and control remains with the running agent job.</span></span> <span data-ttu-id="f931d-200">При синхронном выполнении во время работы агента можно обрабатывать события <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Status> .</span><span class="sxs-lookup"><span data-stu-id="f931d-200">During synchronous execution you can handle the <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Status> event while the agent is running.</span></span>  
  
#### <a name="to-synchronize-a-push-subscription-to-a-merge-publication"></a><span data-ttu-id="f931d-201">Синхронизация принудительной подписки на публикацию слиянием</span><span class="sxs-lookup"><span data-stu-id="f931d-201">To synchronize a push subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="f931d-202">Создайте соединение с распространителем с помощью класса <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="f931d-202">Create a connection to the Distributor by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="f931d-203">Создайте экземпляр класса <xref:Microsoft.SqlServer.Replication.MergeSubscription> и укажите следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="f931d-203">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergeSubscription> class, and set the following properties:</span></span>  
  
    -   <span data-ttu-id="f931d-204">имя базы данных публикации в свойстве <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>;</span><span class="sxs-lookup"><span data-stu-id="f931d-204">The publication database name for <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>.</span></span>  
  
    -   <span data-ttu-id="f931d-205">имя публикации, к которой принадлежит подписка, в свойстве <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>;</span><span class="sxs-lookup"><span data-stu-id="f931d-205">The name of the publication to which the subscription belongs for <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>.</span></span>  
  
    -   <span data-ttu-id="f931d-206">имя базы данных подписки в свойстве <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>;</span><span class="sxs-lookup"><span data-stu-id="f931d-206">The name of the subscription database for <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>.</span></span>  
  
    -   <span data-ttu-id="f931d-207">имя подписчика в свойстве <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>;</span><span class="sxs-lookup"><span data-stu-id="f931d-207">The name of the Subscriber for <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A>.</span></span>  
  
    -   <span data-ttu-id="f931d-208">соединение, созданное на шаге 1, в свойстве <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="f931d-208">The connection created in step 1 for <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span></span>  
  
3.  <span data-ttu-id="f931d-209">Вызовите метод <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> , чтобы получить остальные свойства подписки.</span><span class="sxs-lookup"><span data-stu-id="f931d-209">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the remaining subscription properties.</span></span> <span data-ttu-id="f931d-210">Если этот метод возвращает значение `false`, проверьте, существует ли подписка.</span><span class="sxs-lookup"><span data-stu-id="f931d-210">If this method returns `false`, verify that the subscription exists.</span></span>  
  
4.  <span data-ttu-id="f931d-211">На распространителе запустите агент слияния одним из следующих способов:.</span><span class="sxs-lookup"><span data-stu-id="f931d-211">Start the Merge Agent at the Distributor in one of the following ways:</span></span>  
  
    -   <span data-ttu-id="f931d-212">Вызовите метод <xref:Microsoft.SqlServer.Replication.MergeSubscription.SynchronizeWithJob%2A> экземпляра класса <xref:Microsoft.SqlServer.Replication.MergeSubscription> , созданного на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="f931d-212">Call the <xref:Microsoft.SqlServer.Replication.MergeSubscription.SynchronizeWithJob%2A> method on the instance of <xref:Microsoft.SqlServer.Replication.MergeSubscription> from step 2.</span></span> <span data-ttu-id="f931d-213">Этот метод запускает агент слияния асинхронно, а управление сразу после его вызова передается обратно приложению, задание агента при этом продолжает выполняться.</span><span class="sxs-lookup"><span data-stu-id="f931d-213">This method starts the Merge Agent asynchronously, and control immediately returns to your application while the agent job is running.</span></span> <span data-ttu-id="f931d-214">Этот метод нельзя вызвать, если при создании подписки свойству <xref:Microsoft.SqlServer.Replication.Subscription.CreateSyncAgentByDefault%2A> было присвоено значение `false`.</span><span class="sxs-lookup"><span data-stu-id="f931d-214">You cannot call this method if the subscription was created with a value of `false` for <xref:Microsoft.SqlServer.Replication.Subscription.CreateSyncAgentByDefault%2A>.</span></span>  
  
    -   <span data-ttu-id="f931d-215">Получите экземпляр класса <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent> из свойства <xref:Microsoft.SqlServer.Replication.MergeSubscription.SynchronizationAgent%2A> и вызовите метод <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Synchronize%2A> .</span><span class="sxs-lookup"><span data-stu-id="f931d-215">Obtain an instance of the <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent> class from the <xref:Microsoft.SqlServer.Replication.MergeSubscription.SynchronizationAgent%2A> property, and call the <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Synchronize%2A> method.</span></span> <span data-ttu-id="f931d-216">Этот метод запускает агент слияния синхронно, и управление не возвращается приложению до тех пор, пока не будет закончено выполнение задания агента.</span><span class="sxs-lookup"><span data-stu-id="f931d-216">This method starts the Merge Agent synchronously, and control remains with the running agent job.</span></span> <span data-ttu-id="f931d-217">При синхронном выполнении в процессе работы агента можно обрабатывать событие <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Status> .</span><span class="sxs-lookup"><span data-stu-id="f931d-217">During synchronous execution, you can handle the <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Status> event while the agent is running.</span></span>  
  
###  <a name="examples-rmo"></a><a name="PShellExample"></a> <span data-ttu-id="f931d-218">Примеры (объекты RMO)</span><span class="sxs-lookup"><span data-stu-id="f931d-218">Examples (RMO)</span></span>  
 <span data-ttu-id="f931d-219">В следующем примере синхронизируется принудительная подписка на публикацию транзакций, в которой агент запускается асинхронно через задание агента.</span><span class="sxs-lookup"><span data-stu-id="f931d-219">This example synchronizes a push subscription to a transactional publication, where the agent is started asynchronously using the agent job.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncTranPushSub_WithJob](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_synctranpushsub_withjob)]  
  
 [!code-vb[HowTo#rmo_vb_SyncTranPushSub_WithJob](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_synctranpushsub_withjob)]  
  
 <span data-ttu-id="f931d-220">В следующем примере синхронизируется принудительная подписка на публикацию транзакций, в которой агент запускается синхронно.</span><span class="sxs-lookup"><span data-stu-id="f931d-220">This example synchronizes a push subscription to a transactional publication, where the agent is started synchronously.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncTranPushSub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_synctranpushsub)]  
  
 [!code-vb[HowTo#rmo_vb_SyncTranPushSub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_synctranpushsub)]  
  
 <span data-ttu-id="f931d-221">В следующем примере синхронизируется принудительная подписка на публикацию слиянием, в которой агент запускается асинхронно через задание агента.</span><span class="sxs-lookup"><span data-stu-id="f931d-221">This example synchronizes a push subscription to a merge publication, where the agent is started asynchronously using the agent job.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncMergePushSub_WithJob](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_syncmergepushsub_withjob)]  
  
 [!code-vb[HowTo#rmo_vb_SyncMergePushSub_WithJob](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_syncmergepushsub_withjob)]  
  
 <span data-ttu-id="f931d-222">В следующем примере синхронизируется принудительная подписка на публикацию слиянием, в которой агент запускается синхронно.</span><span class="sxs-lookup"><span data-stu-id="f931d-222">This example synchronizes a push subscription to a merge publication, where the agent is started synchronously.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncMergePushSub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_syncmergepushsub)]  
  
 [!code-vb[HowTo#rmo_vb_SyncMergePushSub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_syncmergepushsub)]  
  
## <a name="see-also"></a><span data-ttu-id="f931d-223">См. также:</span><span class="sxs-lookup"><span data-stu-id="f931d-223">See Also</span></span>  
 <span data-ttu-id="f931d-224">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="f931d-224">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span></span>  
 <span data-ttu-id="f931d-225">[Синхронизация данных](synchronize-data.md) </span><span class="sxs-lookup"><span data-stu-id="f931d-225">[Synchronize Data](synchronize-data.md) </span></span>  
 [<span data-ttu-id="f931d-226">Рекомендации по защите репликации</span><span class="sxs-lookup"><span data-stu-id="f931d-226">Replication Security Best Practices</span></span>](security/replication-security-best-practices.md)  
  
  
