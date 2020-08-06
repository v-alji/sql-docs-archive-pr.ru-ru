---
title: Отключение публикации и распространения | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- disabling publishing
- publishing [SQL Server replication], disabling
- distribution disabling [SQL Server replication]
- removing replication
- replication [SQL Server], removing
- disabling replication
- disabling distribution
ms.assetid: 6d4a1474-4d13-4826-8be2-80050fafa8a5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8843dac310d1e023fe7ce63eded02c9e1bed3731
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655640"
---
# <a name="disable-publishing-and-distribution"></a><span data-ttu-id="c1a30-102">Отключение публикации и распространения</span><span class="sxs-lookup"><span data-stu-id="c1a30-102">Disable Publishing and Distribution</span></span>
  <span data-ttu-id="c1a30-103">В данном разделе описывается отключение публикации и распространения в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]или объектов RMO.</span><span class="sxs-lookup"><span data-stu-id="c1a30-103">This topic describes how to disable publishing and distribution in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span>  
  
 <span data-ttu-id="c1a30-104">Можно сделать следующее.</span><span class="sxs-lookup"><span data-stu-id="c1a30-104">You can do the following:</span></span>  
  
-   <span data-ttu-id="c1a30-105">Удалите все базы данных распространителя на распространителе.</span><span class="sxs-lookup"><span data-stu-id="c1a30-105">Delete all distribution databases on the Distributor.</span></span>  
  
-   <span data-ttu-id="c1a30-106">Отключите все издатели, использующие данный распространитель, и удалите все публикации на этих издателях.</span><span class="sxs-lookup"><span data-stu-id="c1a30-106">Disable all Publishers that use the Distributor and delete all publications on those Publishers.</span></span>  
  
-   <span data-ttu-id="c1a30-107">Удалите все подписки на публикации.</span><span class="sxs-lookup"><span data-stu-id="c1a30-107">Delete all subscriptions to the publications.</span></span> <span data-ttu-id="c1a30-108">Данные баз данных публикации и подписки удалены не будут; однако они потеряют отношения синхронизации с любыми базами данных публикации.</span><span class="sxs-lookup"><span data-stu-id="c1a30-108">Data in the publication and subscription databases will not be deleted; however, it loses its synchronization relationship to any publication databases.</span></span> <span data-ttu-id="c1a30-109">Если нужно удалить данные на подписчике, то их следует удалять вручную.</span><span class="sxs-lookup"><span data-stu-id="c1a30-109">If you want the data at the Subscriber to be deleted, you must delete it manually.</span></span>  
  
 <span data-ttu-id="c1a30-110">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="c1a30-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c1a30-111">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="c1a30-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c1a30-112">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="c1a30-112">Prerequisites</span></span>](#Prerequisites)  
  
-   <span data-ttu-id="c1a30-113">**Для отключения публикации и распространения используется:**</span><span class="sxs-lookup"><span data-stu-id="c1a30-113">**To disable publishing and distribution, using:**</span></span>  
  
     [<span data-ttu-id="c1a30-114">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c1a30-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c1a30-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c1a30-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="c1a30-116">объекты RMO;</span><span class="sxs-lookup"><span data-stu-id="c1a30-116">Replication Management Objects (RMO)</span></span>](#RMOProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c1a30-117">Перед началом</span><span class="sxs-lookup"><span data-stu-id="c1a30-117">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="c1a30-118">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="c1a30-118">Prerequisites</span></span>  
  
-   <span data-ttu-id="c1a30-119">Для отключения публикации и распространения все базы данных распространителей и публикаций должны находиться в режиме «в сети».</span><span class="sxs-lookup"><span data-stu-id="c1a30-119">To disable publishing and distribution, all distribution and publication databases must be online.</span></span> <span data-ttu-id="c1a30-120">Если для баз данных распространителя или публикации существуют какие-либо *моментальные снимки базы данных* , то их необходимо удалить до отключения публикации и распространения.</span><span class="sxs-lookup"><span data-stu-id="c1a30-120">If any *database snapshots* exist for distribution or publication databases, they must be dropped before disabling publishing and distribution.</span></span> <span data-ttu-id="c1a30-121">Моментальный снимок базы данных — это копия базы данных вне сети, доступная только для чтения и не связанная с моментальным снимком репликации.</span><span class="sxs-lookup"><span data-stu-id="c1a30-121">A database snapshot is a read-only offline copy of a database and is not related to a replication snapshot.</span></span> <span data-ttu-id="c1a30-122">Дополнительные сведения см. в разделе [Моментальные снимки базы данных (SQL Server)](../databases/database-snapshots-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c1a30-122">For more information, see [Database Snapshots &#40;SQL Server&#41;](../databases/database-snapshots-sql-server.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c1a30-123">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c1a30-123">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="c1a30-124">Отключить публикацию и распространение можно с помощью мастера отключения публикации и распространения.</span><span class="sxs-lookup"><span data-stu-id="c1a30-124">Disable publishing and distribution by using the Disable Publishing and Distribution Wizard.</span></span>  
  
#### <a name="to-disable-publishing-and-distribution"></a><span data-ttu-id="c1a30-125">Отключение публикации и распространения</span><span class="sxs-lookup"><span data-stu-id="c1a30-125">To disable publishing and distribution</span></span>  
  
1.  <span data-ttu-id="c1a30-126">Подключитесь к издателю или распространителю, который необходимо отключить, в среде [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], а затем раскройте узел сервера.</span><span class="sxs-lookup"><span data-stu-id="c1a30-126">Connect to the Publisher or Distributor you want to disable in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="c1a30-127">Щелкните правой кнопкой мыши папку **Репликация** и выберите **Отключить публикацию и распространение**.</span><span class="sxs-lookup"><span data-stu-id="c1a30-127">Right-click the **Replication** folder, and then click **Disable Publishing and Distribution**.</span></span>  
  
3.  <span data-ttu-id="c1a30-128">Выполните шаги, предлагаемые мастером отключения публикации и распространителя.</span><span class="sxs-lookup"><span data-stu-id="c1a30-128">Complete the steps in the Disable Publishing and Distribution Wizard.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c1a30-129">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c1a30-129">Using Transact-SQL</span></span>  
 <span data-ttu-id="c1a30-130">Публикацию и распространение можно отключить программно с помощью хранимых процедур репликации.</span><span class="sxs-lookup"><span data-stu-id="c1a30-130">Publishing and distributing can be disabled programmatically using replication stored procedures.</span></span>  
  
#### <a name="to-disable-publishing-and-distribution"></a><span data-ttu-id="c1a30-131">Отключение публикации и распространения</span><span class="sxs-lookup"><span data-stu-id="c1a30-131">To disable publishing and distribution</span></span>  
  
1.  <span data-ttu-id="c1a30-132">Остановите все задания, связанные с репликацией.</span><span class="sxs-lookup"><span data-stu-id="c1a30-132">Stop all replication-related jobs.</span></span> <span data-ttu-id="c1a30-133">Список имен задач см. в подразделе «Безопасность агентов при работе с агентом SQL Server» раздела [Модель безопасности агента репликации](security/replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="c1a30-133">For a list of job names, see the "Agent Security Under SQL Server Agent" section of [Replication Agent Security Model](security/replication-agent-security-model.md).</span></span>  
  
2.  <span data-ttu-id="c1a30-134">На каждом подписчике в базе данных подписки выполните хранимую процедуру [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) , чтобы удалить объекты репликации из базы данных.</span><span class="sxs-lookup"><span data-stu-id="c1a30-134">At each Subscriber on the subscription database, execute [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) to remove replication objects from the database.</span></span> <span data-ttu-id="c1a30-135">Эта хранимая процедура не удаляет задания репликации на распространителе.</span><span class="sxs-lookup"><span data-stu-id="c1a30-135">This stored procedure will not remove replication jobs at the Distributor.</span></span>  
  
3.  <span data-ttu-id="c1a30-136">На издателе в базе данных публикации выполните хранимую процедуру [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) , чтобы удалить объекты репликации из базы данных.</span><span class="sxs-lookup"><span data-stu-id="c1a30-136">At the Publisher on the publication database, execute [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) to remove replication objects from the database.</span></span>  
  
4.  <span data-ttu-id="c1a30-137">Если издатель использует удаленный распространитель, выполните хранимую процедуру [sp_dropdistributor](/sql/relational-databases/system-stored-procedures/sp-dropdistributor-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c1a30-137">If the Publisher uses a remote Distributor, execute [sp_dropdistributor](/sql/relational-databases/system-stored-procedures/sp-dropdistributor-transact-sql).</span></span>  
  
5.  <span data-ttu-id="c1a30-138">На распространителе выполните хранимую процедуру [sp_dropdistpublisher](/sql/relational-databases/system-stored-procedures/sp-dropdistpublisher-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c1a30-138">At the Distributor, execute [sp_dropdistpublisher](/sql/relational-databases/system-stored-procedures/sp-dropdistpublisher-transact-sql).</span></span> <span data-ttu-id="c1a30-139">Эта хранимая процедура должна запускаться по разу для каждого издателя, зарегистрированного на распространителе.</span><span class="sxs-lookup"><span data-stu-id="c1a30-139">This stored procedure should be run once for each Publisher registered at the Distributor.</span></span>  
  
6.  <span data-ttu-id="c1a30-140">На распространителе выполните хранимую процедуру [sp_dropdistributiondb](/sql/relational-databases/system-stored-procedures/sp-dropdistributiondb-transact-sql) , чтобы удалить базу данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="c1a30-140">At the Distributor, execute [sp_dropdistributiondb](/sql/relational-databases/system-stored-procedures/sp-dropdistributiondb-transact-sql) to delete the distribution database.</span></span> <span data-ttu-id="c1a30-141">Эта хранимая процедура должна запускаться на распространителе, по одному разу для каждой базы данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="c1a30-141">This stored procedure should be run once for each distribution database at the Distributor.</span></span> <span data-ttu-id="c1a30-142">При этом также удаляются любые задания агента чтения очереди, связанные с базой данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="c1a30-142">This also removes any Queue Reader Agent jobs associated with the distribution database.</span></span>  
  
7.  <span data-ttu-id="c1a30-143">На распространителе выполните хранимую процедуру [sp_dropdistributor](/sql/relational-databases/system-stored-procedures/sp-dropdistributor-transact-sql) , чтобы удалить с сервера обозначение распространителя.</span><span class="sxs-lookup"><span data-stu-id="c1a30-143">At the Distributor, execute [sp_dropdistributor](/sql/relational-databases/system-stored-procedures/sp-dropdistributor-transact-sql) to remove the Distributor designation from the server.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c1a30-144">Если все объекты публикации репликации и распространения не удалены перед выполнением хранимых процедур [sp_dropdistpublisher](/sql/relational-databases/system-stored-procedures/sp-dropdistpublisher-transact-sql) и [sp_dropdistributor](/sql/relational-databases/system-stored-procedures/sp-dropdistributor-transact-sql), эти процедуры возвратят ошибку.</span><span class="sxs-lookup"><span data-stu-id="c1a30-144">If all replication publishing and distribution objects are not dropped before you execute [sp_dropdistpublisher](/sql/relational-databases/system-stored-procedures/sp-dropdistpublisher-transact-sql) and [sp_dropdistributor](/sql/relational-databases/system-stored-procedures/sp-dropdistributor-transact-sql), these procedures will return an error.</span></span> <span data-ttu-id="c1a30-145">Чтобы удалить все объекты, связанные с репликацией, при удалении издателя или распространителя, параметру \*\* \@ no_checks\*\* должно быть присвоено значение **1**.</span><span class="sxs-lookup"><span data-stu-id="c1a30-145">To drop all replication-related objects when a Publisher or Distributor is dropped, the **\@no_checks** parameter must be set to **1**.</span></span> <span data-ttu-id="c1a30-146">Если издатель или распространитель отключен от сети или недоступен, параметру \*\* \@ ignore_distributor\*\* может быть присвоено значение **1** , чтобы их можно было удалить, однако все публикуемые и распределенные объекты должны быть удалены вручную.</span><span class="sxs-lookup"><span data-stu-id="c1a30-146">If a Publisher or Distributor is offline or unreachable, the **\@ignore_distributor** parameter can be set to **1** so that they can be dropped; however, any publishing and distributing objects left behind must be removed manually.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="c1a30-147">Примеры (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c1a30-147">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="c1a30-148">В этом примере скрипта удаляются объекты репликации из базы данных подписки.</span><span class="sxs-lookup"><span data-stu-id="c1a30-148">This example script removes replication objects from the subscription database.</span></span>  
  
 [!code-sql[HowTo#sp_removedbreplication](../../snippets/tsql/SQL15/replication/howto/tsql/dropdistpub.sql#sp_removedbreplication)]  
  
 <span data-ttu-id="c1a30-149">В этом примере скрипта отключается публикация и распространение на сервере, являющемся издателем и распространителем, и удаляется база данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="c1a30-149">This example script disables publishing and distribution on a server that is a Publisher and Distributor and drops the distribution database.</span></span>  
  
 [!code-sql[HowTo#sp_DropDistPub](../../snippets/tsql/SQL15/replication/howto/tsql/dropdistpub.sql#sp_dropdistpub)]  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="c1a30-150">При помощи объектов RMO</span><span class="sxs-lookup"><span data-stu-id="c1a30-150">Using Replication Management Objects (RMO)</span></span>  
  
#### <a name="to-disable-publishing-and-distribution"></a><span data-ttu-id="c1a30-151">Отключение публикации и распространения</span><span class="sxs-lookup"><span data-stu-id="c1a30-151">To disable publishing and distribution</span></span>  
  
1.  <span data-ttu-id="c1a30-152">Удалите все подписки на публикации, которые используют распространитель.</span><span class="sxs-lookup"><span data-stu-id="c1a30-152">Remove all subscriptions to publications that use the Distributor.</span></span> <span data-ttu-id="c1a30-153">Дополнительные сведения см. в разделах [Delete a Pull Subscription](delete-a-pull-subscription.md) и [Delete a Push Subscription](delete-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="c1a30-153">For more information, see [Delete a Pull Subscription](delete-a-pull-subscription.md) and [Delete a Push Subscription](delete-a-push-subscription.md).</span></span>  
  
2.  <span data-ttu-id="c1a30-154">Удалите все публикации, которые используют распространитель, и отключите публикацию для всех баз данных, если издатель и распространитель находятся на одном сервере.</span><span class="sxs-lookup"><span data-stu-id="c1a30-154">Remove all publications that use the Distributor, and disable publishing for all databases if the Publisher and Distributor are on the same server.</span></span> <span data-ttu-id="c1a30-155">Дополнительные сведения см. в разделе [Delete a Publication](publish/delete-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="c1a30-155">For more information, see [Delete a Publication](publish/delete-a-publication.md).</span></span>  
  
3.  <span data-ttu-id="c1a30-156">Создайте соединение с распространителем с помощью класса <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="c1a30-156">Create a connection to the Distributor by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
4.  <span data-ttu-id="c1a30-157">Создайте экземпляр класса <xref:Microsoft.SqlServer.Replication.DistributionPublisher>.</span><span class="sxs-lookup"><span data-stu-id="c1a30-157">Create an instance of the <xref:Microsoft.SqlServer.Replication.DistributionPublisher> class.</span></span> <span data-ttu-id="c1a30-158">Укажите свойство <xref:Microsoft.SqlServer.Replication.DistributionPublisher.Name%2A> и передайте объект <xref:Microsoft.SqlServer.Management.Common.ServerConnection> из шага 3.</span><span class="sxs-lookup"><span data-stu-id="c1a30-158">Specify the <xref:Microsoft.SqlServer.Replication.DistributionPublisher.Name%2A> property, and pass the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object from step 3.</span></span>  
  
5.  <span data-ttu-id="c1a30-159">(Необязательно) Вызовите метод <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> , чтобы получить свойства объекта и убедиться, что издатель существует.</span><span class="sxs-lookup"><span data-stu-id="c1a30-159">(Optional) Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the properties of the object and verify that the Publisher exists.</span></span> <span data-ttu-id="c1a30-160">Если метод возвращает значение `false`, то имя издателя, установленное на шаге 4, неверно или издатель не используется этим распространителем.</span><span class="sxs-lookup"><span data-stu-id="c1a30-160">If this method returns `false`, the Publisher name set in step 4 was incorrect or the Publisher is not used by this Distributor.</span></span>  
  
6.  <span data-ttu-id="c1a30-161">Вызовите метод <xref:Microsoft.SqlServer.Replication.DistributionPublisher.Remove%2A> .</span><span class="sxs-lookup"><span data-stu-id="c1a30-161">Call the <xref:Microsoft.SqlServer.Replication.DistributionPublisher.Remove%2A> method.</span></span> <span data-ttu-id="c1a30-162">Передайте значение `true` для *Force* , если издатель и распространитель находятся на разных серверах, и когда издатель должен быть удален на распространителе без предварительного подтверждения того, что публикации больше не существуют на издателе.</span><span class="sxs-lookup"><span data-stu-id="c1a30-162">Pass a value of `true` for *force* if the Publisher and Distributor are on different servers, and when the Publisher should be uninstalled at the Distributor without first verifying that publications no longer exist at the Publisher.</span></span>  
  
7.  <span data-ttu-id="c1a30-163">Создайте экземпляр класса <xref:Microsoft.SqlServer.Replication.ReplicationServer>.</span><span class="sxs-lookup"><span data-stu-id="c1a30-163">Create an instance of the <xref:Microsoft.SqlServer.Replication.ReplicationServer> class.</span></span> <span data-ttu-id="c1a30-164">Передайте объект <xref:Microsoft.SqlServer.Management.Common.ServerConnection> , созданный на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="c1a30-164">Pass the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object from step 3.</span></span>  
  
8.  <span data-ttu-id="c1a30-165">Вызовите метод <xref:Microsoft.SqlServer.Replication.ReplicationServer.UninstallDistributor%2A> .</span><span class="sxs-lookup"><span data-stu-id="c1a30-165">Call the <xref:Microsoft.SqlServer.Replication.ReplicationServer.UninstallDistributor%2A> method.</span></span> <span data-ttu-id="c1a30-166">Передайте значение `true` для *Force* , чтобы удалить все объекты репликации на распространителе, не проверяя, отключены ли все локальные базы данных публикации, а также удалены ли базы данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="c1a30-166">Pass a value of `true` for *force* to remove all replication objects at the Distributor without first verifying that all local publication databases have been disabled, and distribution databases have been uninstalled.</span></span>  
  
###  <a name="examples-rmo"></a><a name="PShellExample"></a> <span data-ttu-id="c1a30-167">Примеры (объекты RMO)</span><span class="sxs-lookup"><span data-stu-id="c1a30-167">Examples (RMO)</span></span>  
 <span data-ttu-id="c1a30-168">В этом примере удаляется как регистрация издателя на распространителе, так и база данных распространителя, а также удаляется распространитель.</span><span class="sxs-lookup"><span data-stu-id="c1a30-168">This example removes the Publisher registration at the Distributor, drops the distribution database, and uninstalls the Distributor.</span></span>  
  
 [!code-csharp[HowTo#rmo_DropDistPub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_dropdistpub)]  
  
 [!code-vb[HowTo#rmo_vb_DropDistPub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_dropdistpub)]  
  
 <span data-ttu-id="c1a30-169">В этом примере распространитель удаляется без отключения локальных баз данных публикации или удаления базы данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="c1a30-169">This example uninstalls the Distributor without first disabling local publication databases or dropping the distribution database.</span></span>  
  
 [!code-csharp[HowTo#rmo_DropDistPubForce](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_dropdistpubforce)]  
  
 [!code-vb[HowTo#rmo_vb_DropDistPubForce](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_dropdistpubforce)]  
  
## <a name="see-also"></a><span data-ttu-id="c1a30-170">См. также:</span><span class="sxs-lookup"><span data-stu-id="c1a30-170">See Also</span></span>  
 <span data-ttu-id="c1a30-171">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="c1a30-171">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span></span>  
 [<span data-ttu-id="c1a30-172">Replication System Stored Procedures Concepts</span><span class="sxs-lookup"><span data-stu-id="c1a30-172">Replication System Stored Procedures Concepts</span></span>](concepts/replication-system-stored-procedures-concepts.md)  
  
  
