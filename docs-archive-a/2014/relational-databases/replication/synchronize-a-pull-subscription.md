---
title: Синхронизация подписки по запросу | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- pull subscriptions [SQL Server replication], synchronizing
- synchronization [SQL Server replication], pull subscriptions
- subscriptions [SQL Server replication], pull
ms.assetid: 3ca24b23-fdc3-408e-8208-a2ace48fc8e3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 826622cd17862c0535e60c01baab756af2b2996b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664865"
---
# <a name="synchronize-a-pull-subscription"></a><span data-ttu-id="40ad3-102">Синхронизация подписки по запросу</span><span class="sxs-lookup"><span data-stu-id="40ad3-102">Synchronize a Pull Subscription</span></span>
  <span data-ttu-id="40ad3-103">В данном разделе описывается синхронизация подписки по запросу в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [агентов репликации](agents/replication-agents-overview.md)или объектов RMO.</span><span class="sxs-lookup"><span data-stu-id="40ad3-103">This topic describes how to synchronize a pull subscription in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [replication agents](agents/replication-agents-overview.md), or Replication Management Objects (RMO).</span></span>  
  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="40ad3-104">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="40ad3-104">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="40ad3-105">Подписки синхронизируются агентом распространителя (для репликации моментальных снимков и репликации транзакций) или агентом слияния (для репликации слиянием).</span><span class="sxs-lookup"><span data-stu-id="40ad3-105">Subscriptions are synchronized by the Distribution Agent (for snapshot and transactional replication) or the Merge Agent (for merge replication).</span></span> <span data-ttu-id="40ad3-106">Агенты могут работать непрерывно, запускаться по запросу или по расписанию.</span><span class="sxs-lookup"><span data-stu-id="40ad3-106">Agents can run continuously, run on demand, or run on a schedule.</span></span> <span data-ttu-id="40ad3-107">Дополнительные сведения о настройке расписаний синхронизации см. в [этой статье](specify-synchronization-schedules.md).</span><span class="sxs-lookup"><span data-stu-id="40ad3-107">For more information about specifying synchronization schedules, see [Specify Synchronization Schedules](specify-synchronization-schedules.md).</span></span>  
  
 <span data-ttu-id="40ad3-108">Синхронизируйте подписку по запросу из папки **Локальные подписки** в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="40ad3-108">Synchronize a subscription on demand from the **Local Subscriptions** folder in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-synchronize-a-pull-subscription-on-demand-in-management-studio"></a><span data-ttu-id="40ad3-109">Синхронизация по запросу подписки по запросу в среде Management Studio</span><span class="sxs-lookup"><span data-stu-id="40ad3-109">To synchronize a pull subscription on demand in Management Studio</span></span>  
  
1.  <span data-ttu-id="40ad3-110">Подключитесь к подписчику в [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]и раскройте узел сервера.</span><span class="sxs-lookup"><span data-stu-id="40ad3-110">Connect to the Subscriber in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="40ad3-111">Раскройте папку **Репликация** , а затем — папку **Локальные подписки** .</span><span class="sxs-lookup"><span data-stu-id="40ad3-111">Expand the **Replication** folder, and then expand the **Local Subscriptions** folder.</span></span>  
  
3.  <span data-ttu-id="40ad3-112">Щелкните подписку правой кнопкой мыши и выберите **Просмотреть состояние синхронизации**.</span><span class="sxs-lookup"><span data-stu-id="40ad3-112">Right-click the subscription you want to synchronize, and then click **View Synchronization Status**.</span></span>  
  
4.  <span data-ttu-id="40ad3-113">В диалоговом окне **Просмотр состояния синхронизации — \<Subscriber>:\<SubscriptionDatabase>** нажмите кнопку **Пуск**.</span><span class="sxs-lookup"><span data-stu-id="40ad3-113">In the **View Synchronization Status - \<Subscriber>:\<SubscriptionDatabase>** dialog box, click **Start**.</span></span> <span data-ttu-id="40ad3-114">Когда синхронизация будет завершена, появится сообщение **Синхронизация завершена** .</span><span class="sxs-lookup"><span data-stu-id="40ad3-114">When synchronization is complete, the message **Synchronization completed** is displayed.</span></span>  
  
5.  <span data-ttu-id="40ad3-115">Щелкните **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="40ad3-115">Click **Close**.</span></span>  
  
##  <a name="replication-agents"></a><a name="ReplProg"></a> <span data-ttu-id="40ad3-116">Replication Agents</span><span class="sxs-lookup"><span data-stu-id="40ad3-116">Replication Agents</span></span>  
 <span data-ttu-id="40ad3-117">Подписки по запросу могут синхронизироваться программно и по требованию, с помощью вызова из командной строки нужного исполняемого файла агента репликации.</span><span class="sxs-lookup"><span data-stu-id="40ad3-117">Pull subscriptions can be synchronized programmatically and on-demand by invoking the appropriate replication agent executable file from the command prompt.</span></span> <span data-ttu-id="40ad3-118">Вызываемый исполняемый файл агента репликации зависит от типа публикации, к которой принадлежит подписка по запросу.</span><span class="sxs-lookup"><span data-stu-id="40ad3-118">The replication agent executable file that is invoked will depend on the type of publication to which the pull subscription belongs.</span></span> <span data-ttu-id="40ad3-119">Дополнительные сведения см. в разделе [Replication Agents](agents/replication-agents-overview.md).</span><span class="sxs-lookup"><span data-stu-id="40ad3-119">For more information, see [Replication Agents](agents/replication-agents-overview.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="40ad3-120">Агенты репликации подключаются к локальному серверу, используя учетные данные проверки подлинности Windows пользователя, запустившего агент из командной строки.</span><span class="sxs-lookup"><span data-stu-id="40ad3-120">Replication agents connect to the local server using the Windows Authentication credentials of the user who started the agent from the command prompt.</span></span> <span data-ttu-id="40ad3-121">Эти учетные данные Windows также применяются при соединении с удаленными серверами с использованием встроенной проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="40ad3-121">These Windows credentials are also used when connecting to remote servers using Windows Integrated Authentication.</span></span>  
  
#### <a name="to-start-the-distribution-agent-from-the-command-prompt-or-from-a-batch-file"></a><span data-ttu-id="40ad3-122">Запуск агента распространителя из командной строки или из пакетного файла</span><span class="sxs-lookup"><span data-stu-id="40ad3-122">To start the distribution agent from the command prompt or from a batch file</span></span>  
  
1.  <span data-ttu-id="40ad3-123">Из командной строки или из пакетного файла запустите [агент распространения репликации](agents/replication-distribution-agent.md) , вызвав программу **distrib.exe**со следующими параметрами командной строки.</span><span class="sxs-lookup"><span data-stu-id="40ad3-123">From the command prompt or in a batch file, start the [Replication Distribution Agent](agents/replication-distribution-agent.md) by running **distrib.exe**, specifying the following command-line arguments:</span></span>  
  
    -   <span data-ttu-id="40ad3-124">**-Publisher**</span><span class="sxs-lookup"><span data-stu-id="40ad3-124">**-Publisher**</span></span>  
  
    -   <span data-ttu-id="40ad3-125">**-PublisherDB**</span><span class="sxs-lookup"><span data-stu-id="40ad3-125">**-PublisherDB**</span></span>  
  
    -   <span data-ttu-id="40ad3-126">**-Distributor**</span><span class="sxs-lookup"><span data-stu-id="40ad3-126">**-Distributor**</span></span>  
  
    -   <span data-ttu-id="40ad3-127">**-DistributorSecurityMode** = **1**</span><span class="sxs-lookup"><span data-stu-id="40ad3-127">**-DistributorSecurityMode** = **1**</span></span>  
  
    -   <span data-ttu-id="40ad3-128">**-Subscriber**</span><span class="sxs-lookup"><span data-stu-id="40ad3-128">**-Subscriber**</span></span>  
  
    -   <span data-ttu-id="40ad3-129">**-SubscriberDB**</span><span class="sxs-lookup"><span data-stu-id="40ad3-129">**-SubscriberDB**</span></span>  
  
    -   <span data-ttu-id="40ad3-130">**-SubscriberSecurityMode** = **1**</span><span class="sxs-lookup"><span data-stu-id="40ad3-130">**-SubscriberSecurityMode** = **1**</span></span>  
  
    -   <span data-ttu-id="40ad3-131">**-SubscriptionType** = **1**</span><span class="sxs-lookup"><span data-stu-id="40ad3-131">**-SubscriptionType** = **1**</span></span>  
  
     <span data-ttu-id="40ad3-132">При использовании проверки подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] необходимо также указать следующие аргументы.</span><span class="sxs-lookup"><span data-stu-id="40ad3-132">If you are using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, you must also specify the following arguments:</span></span>  
  
    -   <span data-ttu-id="40ad3-133">**-DistributorLogin**</span><span class="sxs-lookup"><span data-stu-id="40ad3-133">**-DistributorLogin**</span></span>  
  
    -   <span data-ttu-id="40ad3-134">**-DistributorPassword**</span><span class="sxs-lookup"><span data-stu-id="40ad3-134">**-DistributorPassword**</span></span>  
  
    -   <span data-ttu-id="40ad3-135">**-DistributorSecurityMode** = **0**</span><span class="sxs-lookup"><span data-stu-id="40ad3-135">**-DistributorSecurityMode** = **0**</span></span>  
  
    -   <span data-ttu-id="40ad3-136">**-PublisherLogin**</span><span class="sxs-lookup"><span data-stu-id="40ad3-136">**-PublisherLogin**</span></span>  
  
    -   <span data-ttu-id="40ad3-137">**-PublisherPassword**</span><span class="sxs-lookup"><span data-stu-id="40ad3-137">**-PublisherPassword**</span></span>  
  
    -   <span data-ttu-id="40ad3-138">**-PublisherSecurityMode** = **0**</span><span class="sxs-lookup"><span data-stu-id="40ad3-138">**-PublisherSecurityMode** = **0**</span></span>  
  
    -   <span data-ttu-id="40ad3-139">**-SubscriberLogin**</span><span class="sxs-lookup"><span data-stu-id="40ad3-139">**-SubscriberLogin**</span></span>  
  
    -   <span data-ttu-id="40ad3-140">**-SubscriberPassword**</span><span class="sxs-lookup"><span data-stu-id="40ad3-140">**-SubscriberPassword**</span></span>  
  
    -   <span data-ttu-id="40ad3-141">**-SubscriberSecurityMode** = **0**</span><span class="sxs-lookup"><span data-stu-id="40ad3-141">**-SubscriberSecurityMode** = **0**</span></span>  
  
#### <a name="to-start-the-merge-agent-from-the-command-prompt-or-from-a-batch-file"></a><span data-ttu-id="40ad3-142">Запуск агента слияния из командной строки или из пакетного файла</span><span class="sxs-lookup"><span data-stu-id="40ad3-142">To start the merge agent from the command prompt or from a batch file</span></span>  
  
1.  <span data-ttu-id="40ad3-143">Из командной строки или из пакетного файла запустите [агент слияния репликации](agents/replication-merge-agent.md) , вызвав программу **replmerg.exe**со следующими параметрами командной строки.</span><span class="sxs-lookup"><span data-stu-id="40ad3-143">From the command prompt or in a batch file, start the [Replication Merge Agent](agents/replication-merge-agent.md) by running **replmerg.exe**, specifying the following command-line arguments:</span></span>  
  
    -   <span data-ttu-id="40ad3-144">**-Publisher**</span><span class="sxs-lookup"><span data-stu-id="40ad3-144">**-Publisher**</span></span>  
  
    -   <span data-ttu-id="40ad3-145">**-PublisherDB**</span><span class="sxs-lookup"><span data-stu-id="40ad3-145">**-PublisherDB**</span></span>  
  
    -   <span data-ttu-id="40ad3-146">**-PublisherSecurityMode** = **1**</span><span class="sxs-lookup"><span data-stu-id="40ad3-146">**-PublisherSecurityMode** = **1**</span></span>  
  
    -   <span data-ttu-id="40ad3-147">**-Publication**</span><span class="sxs-lookup"><span data-stu-id="40ad3-147">**-Publication**</span></span>  
  
    -   <span data-ttu-id="40ad3-148">**-Distributor**</span><span class="sxs-lookup"><span data-stu-id="40ad3-148">**-Distributor**</span></span>  
  
    -   <span data-ttu-id="40ad3-149">**-DistributorSecurityMode** = **1**</span><span class="sxs-lookup"><span data-stu-id="40ad3-149">**-DistributorSecurityMode** = **1**</span></span>  
  
    -   <span data-ttu-id="40ad3-150">**-Subscriber**</span><span class="sxs-lookup"><span data-stu-id="40ad3-150">**-Subscriber**</span></span>  
  
    -   <span data-ttu-id="40ad3-151">**-SubscriberSecurityMode** = **1**</span><span class="sxs-lookup"><span data-stu-id="40ad3-151">**-SubscriberSecurityMode** = **1**</span></span>  
  
    -   <span data-ttu-id="40ad3-152">**-SubscriberDB**</span><span class="sxs-lookup"><span data-stu-id="40ad3-152">**-SubscriberDB**</span></span>  
  
    -   <span data-ttu-id="40ad3-153">**-SubscriptionType** = **1**</span><span class="sxs-lookup"><span data-stu-id="40ad3-153">**-SubscriptionType** = **1**</span></span>  
  
     <span data-ttu-id="40ad3-154">При использовании проверки подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] необходимо также указать следующие аргументы.</span><span class="sxs-lookup"><span data-stu-id="40ad3-154">If you are using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, you must also specify the following arguments:</span></span>  
  
    -   <span data-ttu-id="40ad3-155">**-DistributorLogin**</span><span class="sxs-lookup"><span data-stu-id="40ad3-155">**-DistributorLogin**</span></span>  
  
    -   <span data-ttu-id="40ad3-156">**-DistributorPassword**</span><span class="sxs-lookup"><span data-stu-id="40ad3-156">**-DistributorPassword**</span></span>  
  
    -   <span data-ttu-id="40ad3-157">**-DistributorSecurityMode** = **0**</span><span class="sxs-lookup"><span data-stu-id="40ad3-157">**-DistributorSecurityMode** = **0**</span></span>  
  
    -   <span data-ttu-id="40ad3-158">**-PublisherLogin**</span><span class="sxs-lookup"><span data-stu-id="40ad3-158">**-PublisherLogin**</span></span>  
  
    -   <span data-ttu-id="40ad3-159">**-PublisherPassword**</span><span class="sxs-lookup"><span data-stu-id="40ad3-159">**-PublisherPassword**</span></span>  
  
    -   <span data-ttu-id="40ad3-160">**-PublisherSecurityMode** = **0**</span><span class="sxs-lookup"><span data-stu-id="40ad3-160">**-PublisherSecurityMode** = **0**</span></span>  
  
    -   <span data-ttu-id="40ad3-161">**-SubscriberLogin**</span><span class="sxs-lookup"><span data-stu-id="40ad3-161">**-SubscriberLogin**</span></span>  
  
    -   <span data-ttu-id="40ad3-162">**-SubscriberPassword**</span><span class="sxs-lookup"><span data-stu-id="40ad3-162">**-SubscriberPassword**</span></span>  
  
    -   <span data-ttu-id="40ad3-163">**-SubscriberSecurityMode** = **0**</span><span class="sxs-lookup"><span data-stu-id="40ad3-163">**-SubscriberSecurityMode** = **0**</span></span>  
  
###  <a name="examples-replication-agents"></a><a name="TsqlExample"></a> <span data-ttu-id="40ad3-164">Примеры (агенты репликации)</span><span class="sxs-lookup"><span data-stu-id="40ad3-164">Examples (Replication Agents)</span></span>  
 <span data-ttu-id="40ad3-165">В следующем примере запускается агент распространителя для синхронизации подписки по запросу.</span><span class="sxs-lookup"><span data-stu-id="40ad3-165">The following example starts the Distribution Agent to synchronize a pull subscription.</span></span> <span data-ttu-id="40ad3-166">Все соединения устанавливаются с использованием проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="40ad3-166">All connections are made using Windows Authentication.</span></span>  
  
 [!code-sql[HowTo#bat_synctranpullsub_10](../../snippets/tsql/SQL15/replication/howto/tsql/synctranpullsub_10.bat)]  
  
 <span data-ttu-id="40ad3-167">В следующем примере запускается агент слияния для синхронизации подписки по запросу.</span><span class="sxs-lookup"><span data-stu-id="40ad3-167">The following example starts the Merge Agent to synchronize a pull subscription.</span></span> <span data-ttu-id="40ad3-168">Все соединения устанавливаются с использованием проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="40ad3-168">All connections are made using Windows Authentication.</span></span>  
  
 [!code-sql[HowTo#bat_syncmergepullsub_10](../../snippets/tsql/SQL15/replication/howto/tsql/syncmergepullsub_10.bat)]  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="40ad3-169">При помощи объектов RMO</span><span class="sxs-lookup"><span data-stu-id="40ad3-169">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="40ad3-170">Подписки по запросу можно синхронизировать программно с помощью объектов RMO и доступа к функциональности агента репликации из управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="40ad3-170">You can synchronize pull subscriptions programmatically by using Replication Management Objects (RMO) and managed code access to replication agent functionalities.</span></span> <span data-ttu-id="40ad3-171">Конкретные классы, используемые для синхронизации, зависят от типа публикации, к которой принадлежит подписка.</span><span class="sxs-lookup"><span data-stu-id="40ad3-171">The classes you use to synchronize a pull subscription depend on the type of publication to which the subscription belongs.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="40ad3-172">Если нужно выполнить синхронизацию, которая выполняется автономно и не влияет на ваше приложение, запустите агент асинхронно.</span><span class="sxs-lookup"><span data-stu-id="40ad3-172">If you want to start a synchronization that runs autonomously without affecting your application, start the agent asynchronously.</span></span> <span data-ttu-id="40ad3-173">Однако если нужно наблюдать за результатами синхронизации и получать обратные вызовы от агента во время процесса синхронизации (например, если нужно отображать индикатор выполнения), то следует запускать агент синхронно.</span><span class="sxs-lookup"><span data-stu-id="40ad3-173">However, if you want to monitor the outcome of the synchronization and receive callbacks from the agent during the synchronization process (for example, to display a progress bar), you should start the agent synchronously.</span></span> <span data-ttu-id="40ad3-174">Для подписчиков [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)] также необходимо запускать агент синхронно.</span><span class="sxs-lookup"><span data-stu-id="40ad3-174">For [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)] Subscribers, you must start the agent synchronously.</span></span>  
  
#### <a name="to-synchronize-a-pull-subscription-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="40ad3-175">Синхронизация подписки по запросу на публикацию моментальных снимков или транзакций</span><span class="sxs-lookup"><span data-stu-id="40ad3-175">To synchronize a pull subscription to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="40ad3-176">Создайте соединение с подписчиком с помощью класса <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="40ad3-176">Create a connection to the Subscriber by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="40ad3-177">Создайте экземпляр класса <xref:Microsoft.SqlServer.Replication.TransPullSubscription> и укажите следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="40ad3-177">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransPullSubscription> class, and set the following properties:</span></span>  
  
    -   <span data-ttu-id="40ad3-178">имя базы данных подписки в свойстве <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>;</span><span class="sxs-lookup"><span data-stu-id="40ad3-178">The subscription database name for <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>.</span></span>  
  
    -   <span data-ttu-id="40ad3-179">имя публикации, к которой принадлежит подписка, в свойстве <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>;</span><span class="sxs-lookup"><span data-stu-id="40ad3-179">The name of the publication to which the subscription belongs for <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>.</span></span>  
  
    -   <span data-ttu-id="40ad3-180">Имя базы данных публикации в свойстве <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A>.</span><span class="sxs-lookup"><span data-stu-id="40ad3-180">The name of the publication database for <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A>.</span></span>  
  
    -   <span data-ttu-id="40ad3-181">имя издателя в свойстве <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>;</span><span class="sxs-lookup"><span data-stu-id="40ad3-181">The name of the Publisher for <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>.</span></span>  
  
    -   <span data-ttu-id="40ad3-182">соединение, созданное на шаге 1, в свойстве <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="40ad3-182">The connection created in step 1 for <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span></span>  
  
3.  <span data-ttu-id="40ad3-183">Вызовите метод <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> , чтобы получить остальные свойства подписки.</span><span class="sxs-lookup"><span data-stu-id="40ad3-183">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the remaining subscription properties.</span></span> <span data-ttu-id="40ad3-184">Если этот метод возвращает значение `false`, проверьте, существует ли подписка.</span><span class="sxs-lookup"><span data-stu-id="40ad3-184">If this method returns `false`, verify that the subscription exists.</span></span>  
  
4.  <span data-ttu-id="40ad3-185">На распространителе запустите агент распространителя одним из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="40ad3-185">Start the Distribution Agent at the Subscriber in one of the following ways:</span></span>  
  
    -   <span data-ttu-id="40ad3-186">Вызовите метод <xref:Microsoft.SqlServer.Replication.TransPullSubscription.SynchronizeWithJob%2A> экземпляра класса <xref:Microsoft.SqlServer.Replication.TransPullSubscription> , созданного на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="40ad3-186">Call the <xref:Microsoft.SqlServer.Replication.TransPullSubscription.SynchronizeWithJob%2A> method on the instance of <xref:Microsoft.SqlServer.Replication.TransPullSubscription> from step 2.</span></span> <span data-ttu-id="40ad3-187">Этот метод запускает агент распространителя асинхронно, а управление сразу после его вызова передается обратно приложению; задание агента при этом продолжает выполняться.</span><span class="sxs-lookup"><span data-stu-id="40ad3-187">This method starts the Distribution Agent asynchronously, and control immediately returns to your application while the agent job is running.</span></span> <span data-ttu-id="40ad3-188">Этот метод нельзя вызывать для подписчиков [!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)], а так же в том случае, если подписка была создана со значением `false` свойства <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (значение по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="40ad3-188">You cannot call this method for [!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)] Subscribers or if the subscription was created with a value of `false` for <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (the default).</span></span>  
  
    -   <span data-ttu-id="40ad3-189">Получите экземпляр класса <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent> из свойства <xref:Microsoft.SqlServer.Replication.TransPullSubscription.SynchronizationAgent%2A> и вызовите метод <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Synchronize%2A> .</span><span class="sxs-lookup"><span data-stu-id="40ad3-189">Get an instance of the <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent> class from the <xref:Microsoft.SqlServer.Replication.TransPullSubscription.SynchronizationAgent%2A> property, and call the <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Synchronize%2A> method.</span></span> <span data-ttu-id="40ad3-190">Этот метод запускает агент синхронно, и управление не возвращается приложению до тех пор, пока выполнение задания агента не будет завершено.</span><span class="sxs-lookup"><span data-stu-id="40ad3-190">This method starts the agent synchronously, and control remains with the running agent job.</span></span> <span data-ttu-id="40ad3-191">При синхронном выполнении в процессе работы агента можно обрабатывать событие <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Status> .</span><span class="sxs-lookup"><span data-stu-id="40ad3-191">During synchronous execution, you can handle the <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Status> event while the agent is running.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="40ad3-192">Если вы указали значение `false` для <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (по умолчанию) при создании подписки по запросу, необходимо также указать, и, <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Distributor%2A> Если <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.DistributorSecurityMode%2A> <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.DistributorLogin%2A> <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.DistributorPassword%2A> связанные с заданием агента метаданные для подписки недоступны в [MSsubscription_properties](/sql/relational-databases/system-tables/mssubscription-properties-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="40ad3-192">If you specified a value of `false` for <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (the default) when you created the pull subscription, you also need to specify <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.Distributor%2A>, <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.DistributorSecurityMode%2A>, and optionally <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.DistributorLogin%2A> and <xref:Microsoft.SqlServer.Replication.TransSynchronizationAgent.DistributorPassword%2A> because the agent job related metadata for the subscription is not available in [MSsubscription_properties](/sql/relational-databases/system-tables/mssubscription-properties-transact-sql).</span></span>  
  
#### <a name="to-synchronize-a-pull-subscription-to-a-merge-publication"></a><span data-ttu-id="40ad3-193">Синхронизация подписки по запросу на публикацию слиянием</span><span class="sxs-lookup"><span data-stu-id="40ad3-193">To synchronize a pull subscription to a merge publication</span></span>  
  
1.  <span data-ttu-id="40ad3-194">Создайте соединение с подписчиком с помощью класса <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="40ad3-194">Create a connection to the Subscriber by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="40ad3-195">Создайте экземпляр класса <xref:Microsoft.SqlServer.Replication.MergePullSubscription> и укажите следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="40ad3-195">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergePullSubscription> class, and set the following properties:</span></span>  
  
    -   <span data-ttu-id="40ad3-196">имя базы данных подписки в свойстве <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>;</span><span class="sxs-lookup"><span data-stu-id="40ad3-196">The subscription database name for <xref:Microsoft.SqlServer.Replication.PullSubscription.DatabaseName%2A>.</span></span>  
  
    -   <span data-ttu-id="40ad3-197">имя публикации, к которой принадлежит подписка, в свойстве <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>;</span><span class="sxs-lookup"><span data-stu-id="40ad3-197">The name of the publication to which the subscription belongs for <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationName%2A>.</span></span>  
  
    -   <span data-ttu-id="40ad3-198">имя опубликованной базы данных в свойстве <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A>;</span><span class="sxs-lookup"><span data-stu-id="40ad3-198">The name of the published database for <xref:Microsoft.SqlServer.Replication.PullSubscription.PublicationDBName%2A>.</span></span>  
  
    -   <span data-ttu-id="40ad3-199">имя издателя в свойстве <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>;</span><span class="sxs-lookup"><span data-stu-id="40ad3-199">The name of the Publisher for <xref:Microsoft.SqlServer.Replication.PullSubscription.PublisherName%2A>.</span></span>  
  
    -   <span data-ttu-id="40ad3-200">соединение, созданное на шаге 1, в свойстве <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="40ad3-200">The connection created in step 1 for <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span></span>  
  
3.  <span data-ttu-id="40ad3-201">Вызовите метод <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> , чтобы получить остальные свойства подписки.</span><span class="sxs-lookup"><span data-stu-id="40ad3-201">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the remaining subscription properties.</span></span> <span data-ttu-id="40ad3-202">Если этот метод возвращает значение `false`, проверьте, существует ли подписка.</span><span class="sxs-lookup"><span data-stu-id="40ad3-202">If this method returns `false`, verify that the subscription exists.</span></span>  
  
4.  <span data-ttu-id="40ad3-203">На подписчике запустите агент слияния одним из следующих способов:.</span><span class="sxs-lookup"><span data-stu-id="40ad3-203">Start the Merge Agent at the Subscriber in one of the following ways:</span></span>  
  
    -   <span data-ttu-id="40ad3-204">Вызовите метод <xref:Microsoft.SqlServer.Replication.MergePullSubscription.SynchronizeWithJob%2A> экземпляра класса <xref:Microsoft.SqlServer.Replication.MergePullSubscription> , созданного на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="40ad3-204">Call the <xref:Microsoft.SqlServer.Replication.MergePullSubscription.SynchronizeWithJob%2A> method on the instance of <xref:Microsoft.SqlServer.Replication.MergePullSubscription> from step 2.</span></span> <span data-ttu-id="40ad3-205">Этот метод запускает агент слияния асинхронно, а управление сразу после его вызова передается обратно приложению, задание агента при этом продолжает выполняться.</span><span class="sxs-lookup"><span data-stu-id="40ad3-205">This method starts the Merge Agent asynchronously, and control immediately returns to your application while the agent job is running.</span></span> <span data-ttu-id="40ad3-206">Этот метод нельзя вызывать для подписчиков [!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)], а так же в том случае, если подписка была создана со значением `false` свойства <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (значение по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="40ad3-206">You cannot call this method for [!INCLUDE[ssExpressEd2005](../../includes/ssexpressed2005-md.md)] Subscribers or if the subscription was created with a value of `false` for <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (the default).</span></span>  
  
    -   <span data-ttu-id="40ad3-207">Получите экземпляр класса <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent> из свойства <xref:Microsoft.SqlServer.Replication.MergePullSubscription.SynchronizationAgent%2A> и вызовите метод <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Synchronize%2A> .</span><span class="sxs-lookup"><span data-stu-id="40ad3-207">Obtain an instance of the <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent> class from the <xref:Microsoft.SqlServer.Replication.MergePullSubscription.SynchronizationAgent%2A> property, and call the <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Synchronize%2A> method.</span></span> <span data-ttu-id="40ad3-208">Этот метод запускает агент слияния синхронно, и управление не возвращается приложению до тех пор, пока не будет закончено выполнение задания агента.</span><span class="sxs-lookup"><span data-stu-id="40ad3-208">This method starts the Merge Agent synchronously, and control remains with the running agent job.</span></span> <span data-ttu-id="40ad3-209">При синхронном выполнении в процессе работы агента можно обрабатывать событие <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Status> .</span><span class="sxs-lookup"><span data-stu-id="40ad3-209">During synchronous execution, you can handle the <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Status> event while the agent is running.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="40ad3-210">Если при `false` создании подписки по запросу было задано значение для <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (по умолчанию), необходимо также указать,, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Distributor%2A> <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.DistributorSecurityMode%2A> <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.PublisherSecurityMode%2A> , <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.HostName%2A> , <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.SubscriptionType%2A> , и,,, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.ExchangeType%2A> и, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.DistributorLogin%2A> <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.DistributorPassword%2A> <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.PublisherLogin%2A> <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.PublisherPassword%2A> так как метаданные задания агента, связанные с подпиской, недоступны в [MSsubscription_properties](/sql/relational-databases/system-tables/mssubscription-properties-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="40ad3-210">If you specified a value of `false` for <xref:Microsoft.SqlServer.Replication.PullSubscription.CreateSyncAgentByDefault%2A> (the default) when you created the pull subscription, you also need to specify <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.Distributor%2A>, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.DistributorSecurityMode%2A>, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.PublisherSecurityMode%2A>, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.HostName%2A>, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.SubscriptionType%2A>, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.ExchangeType%2A>, and optionally <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.DistributorLogin%2A>, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.DistributorPassword%2A>, <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.PublisherLogin%2A>, and <xref:Microsoft.SqlServer.Replication.MergeSynchronizationAgent.PublisherPassword%2A> because the agent job related metadata for the subscription is not available in [MSsubscription_properties](/sql/relational-databases/system-tables/mssubscription-properties-transact-sql).</span></span>  
  
###  <a name="examples-rmo"></a><a name="PShellExample"></a> <span data-ttu-id="40ad3-211">Примеры (объекты RMO)</span><span class="sxs-lookup"><span data-stu-id="40ad3-211">Examples (RMO)</span></span>  
 <span data-ttu-id="40ad3-212">В следующем примере синхронизируется подписка по запросу на публикацию транзакций, в которой агент запускается асинхронно через задание агента.</span><span class="sxs-lookup"><span data-stu-id="40ad3-212">This example synchronizes a pull subscription to a transactional publication, where the agent is started asynchronously using the agent job.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncTranPullSub_WithJob](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_synctranpullsub_withjob)]  
  
 [!code-vb[HowTo#rmo_vb_SyncTranPullSub_WithJob](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_synctranpullsub_withjob)]  
  
 <span data-ttu-id="40ad3-213">В следующем примере синхронизируется подписка по запросу на публикацию транзакций, в которой агент запускается синхронно.</span><span class="sxs-lookup"><span data-stu-id="40ad3-213">This example synchronizes a pull subscription to a transactional publication, where the agent is started synchronously.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncTranPullSub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_synctranpullsub)]  
  
 [!code-vb[HowTo#rmo_vb_SyncTranPullSub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_synctranpullsub)]  
  
 <span data-ttu-id="40ad3-214">В следующем примере синхронизируется подписка по запросу на публикацию слиянием, в которой агент запускается асинхронно через задание агента.</span><span class="sxs-lookup"><span data-stu-id="40ad3-214">This example synchronizes a pull subscription to a merge publication, where the agent is started asynchronously using the agent job.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncMergePullSub_WithJob](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_syncmergepullsub_withjob)]  
  
 [!code-vb[HowTo#rmo_vb_SyncMergePullSub_WithJob](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_syncmergepullsub_withjob)]  
  
 <span data-ttu-id="40ad3-215">В следующем примере синхронизируется подписка по запросу на публикацию слиянием, в которой агент запускается синхронно.</span><span class="sxs-lookup"><span data-stu-id="40ad3-215">This example synchronizes a pull subscription to a merge publication, where the agent is started synchronously.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncMergePullSub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_syncmergepullsub)]  
  
 [!code-vb[HowTo#rmo_vb_SyncMergePullSub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_syncmergepullsub)]  
  
 <span data-ttu-id="40ad3-216">В следующем примере синхронизируется подписка по запросу на публикацию слиянием с использованием веб-синхронизации.</span><span class="sxs-lookup"><span data-stu-id="40ad3-216">This example synchronizes a pull subscription to a merge publication using Web synchronization.</span></span> <span data-ttu-id="40ad3-217">Данная подписка создается без задания агента и соответствующих метаданных подписки, поэтому агент должен быть запущен синхронно с указанием дополнительных сведений о подписке.</span><span class="sxs-lookup"><span data-stu-id="40ad3-217">The subscription was created without the agent job and related subscription metadata, so the agent must be started synchronously and additional subscription information is supplied.</span></span>  
  
 [!code-csharp[HowTo#rmo_SyncMergePullSub_NoJobWebSync](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_syncmergepullsub_nojobwebsync)]  
  
 [!code-vb[HowTo#rmo_vb_SyncMergePullSub_NoJobWebSync](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_syncmergepullsub_nojobwebsync)]  
  
## <a name="see-also"></a><span data-ttu-id="40ad3-218">См. также:</span><span class="sxs-lookup"><span data-stu-id="40ad3-218">See Also</span></span>  
 <span data-ttu-id="40ad3-219">[Синхронизация данных](synchronize-data.md) </span><span class="sxs-lookup"><span data-stu-id="40ad3-219">[Synchronize Data](synchronize-data.md) </span></span>  
 <span data-ttu-id="40ad3-220">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="40ad3-220">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 [<span data-ttu-id="40ad3-221">Рекомендации по защите репликации</span><span class="sxs-lookup"><span data-stu-id="40ad3-221">Replication Security Best Practices</span></span>](security/replication-security-best-practices.md)  
  
  
