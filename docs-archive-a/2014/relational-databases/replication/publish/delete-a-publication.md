---
title: Удаление публикации| Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- removing publications
- publications [SQL Server replication], deleting
- articles [SQL Server replication], deleting
- deleting publications
ms.assetid: 408a1360-12ee-4896-ac94-482ae839593b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5d2b39a326d59333868b4f8015eb9a2e59d59e44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750679"
---
# <a name="delete-a-publication"></a><span data-ttu-id="d78ed-102">Удаление публикации</span><span class="sxs-lookup"><span data-stu-id="d78ed-102">Delete a Publication</span></span>
  <span data-ttu-id="d78ed-103">В данном разделе описывается удаление публикации в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]или объектов RMO.</span><span class="sxs-lookup"><span data-stu-id="d78ed-103">This topic describes how to delete a publication in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span>  
  
 <span data-ttu-id="d78ed-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="d78ed-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d78ed-105">**Для удаления публикации используется:**</span><span class="sxs-lookup"><span data-stu-id="d78ed-105">**To delete a publication, using:**</span></span>  
  
     [<span data-ttu-id="d78ed-106">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d78ed-106">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d78ed-107">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d78ed-107">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="d78ed-108">объекты RMO;</span><span class="sxs-lookup"><span data-stu-id="d78ed-108">Replication Management Objects (RMO)</span></span>](#RMOProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d78ed-109">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d78ed-109">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="d78ed-110">Удалите публикации из папки **Локальные публикации** в среде [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d78ed-110">Delete publications from the **Local Publications** folder in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-delete-a-publication"></a><span data-ttu-id="d78ed-111">Удаление публикации</span><span class="sxs-lookup"><span data-stu-id="d78ed-111">To delete a publication</span></span>  
  
1.  <span data-ttu-id="d78ed-112">Подключитесь к издателю в среде [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], а затем раскройте узел сервера.</span><span class="sxs-lookup"><span data-stu-id="d78ed-112">Connect to the Publisher in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="d78ed-113">Раскройте папку **Репликация** , а затем папку **Локальные публикации** .</span><span class="sxs-lookup"><span data-stu-id="d78ed-113">Expand the **Replication** folder, and then expand the **Local Publications** folder.</span></span>  
  
3.  <span data-ttu-id="d78ed-114">Щелкните правой кнопкой мыши публикацию, которую требуется удалить, и выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="d78ed-114">Right-click the publication you want to delete, and then click **Delete**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d78ed-115">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d78ed-115">Using Transact-SQL</span></span>  
 <span data-ttu-id="d78ed-116">Публикации могут быть удалены программно, с помощью хранимых процедур репликации.</span><span class="sxs-lookup"><span data-stu-id="d78ed-116">Publications can be deleted programmatically using replication stored procedures.</span></span> <span data-ttu-id="d78ed-117">Какие именно хранимые процедуры для этого применяются, зависит от типа удаляемой публикации.</span><span class="sxs-lookup"><span data-stu-id="d78ed-117">The stored procedures that you use depend on the type of publication being deleted.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d78ed-118">При удалении публикации опубликованные объекты базы данных публикации и связанные с ними объекты базы данных подписки не удаляются.</span><span class="sxs-lookup"><span data-stu-id="d78ed-118">Deleting a publication does not remove published objects from the publication database or the corresponding objects from the subscription database.</span></span> <span data-ttu-id="d78ed-119">При необходимости их необходимо удалить вручную, при помощи инструкции `DROP <object>` .</span><span class="sxs-lookup"><span data-stu-id="d78ed-119">Use the `DROP <object>` command to manually remove these objects if necessary.</span></span>  
  
#### <a name="to-delete-a-snapshot-or-transactional-publication"></a><span data-ttu-id="d78ed-120">Удаление публикации моментальных снимков или транзакций</span><span class="sxs-lookup"><span data-stu-id="d78ed-120">To delete a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="d78ed-121">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="d78ed-121">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="d78ed-122">Для удаления отдельной публикации в базе данных публикации на издателе выполните инструкцию [sp_droppublication](/sql/relational-databases/system-stored-procedures/sp-droppublication-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="d78ed-122">To delete a single publication, execute [sp_droppublication](/sql/relational-databases/system-stored-procedures/sp-droppublication-transact-sql) at the Publisher on the publication database.</span></span>  
  
    -   <span data-ttu-id="d78ed-123">Чтобы удалить все публикации и удалить все объекты репликации из опубликованной базы данных, выполните процедуру [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) на издателе.</span><span class="sxs-lookup"><span data-stu-id="d78ed-123">To delete all publications in and remove all replication objects from a published database, execute [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) at the Publisher.</span></span> <span data-ttu-id="d78ed-124">Укажите значение `tran` для \*\* \@ типа\*\*.</span><span class="sxs-lookup"><span data-stu-id="d78ed-124">Specify a value of `tran` for **\@type**.</span></span> <span data-ttu-id="d78ed-125">Если распространитель недоступен или база данных находится в подозрительном состоянии или в режиме "вне сети", укажите значение **1** в параметре **\@force** (необязательно).</span><span class="sxs-lookup"><span data-stu-id="d78ed-125">(Optional) If the Distributor cannot be accessed or if the status of the database is suspect or offline, specify a value of **1** for **\@force**.</span></span> <span data-ttu-id="d78ed-126">Укажите имя базы данных в параметре **\@dbname**, если процедура [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) не выполнялась в базе данных публикации (необязательно).</span><span class="sxs-lookup"><span data-stu-id="d78ed-126">(Optional) Specify the name of the database for **\@dbname** if [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) is not executed on the publication database.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="d78ed-127">Если задать значение **1** в параметре **\@force**, в базе данных могут остаться объекты публикации, связанные с репликацией.</span><span class="sxs-lookup"><span data-stu-id="d78ed-127">Specifying a value of **1** for **\@force** may leave replication-related publishing objects in the database.</span></span>  
  
2.  <span data-ttu-id="d78ed-128">Если база данных содержит только одну публикацию, то для того, чтобы отключить публикацию текущей базы данных с помощью репликации моментальных снимков или транзакций, выполните хранимую процедуру [sp_replicationdboption (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) (необязательно).</span><span class="sxs-lookup"><span data-stu-id="d78ed-128">(Optional) If this database has no other publications, execute [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) to disable publication of the current database using snapshot or transactional replication.</span></span>  
  
3.  <span data-ttu-id="d78ed-129">(Необязательно) Чтобы удалить все метаданные репликации, оставшиеся в базе данных подписки, на подписчике в базе данных публикации выполните хранимую процедуру [sp_subscription_cleanup](/sql/relational-databases/system-stored-procedures/sp-subscription-cleanup-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="d78ed-129">(Optional) At the Subscriber on the subscription database, execute [sp_subscription_cleanup](/sql/relational-databases/system-stored-procedures/sp-subscription-cleanup-transact-sql) to remove any remaining replication metadata in the subscription database.</span></span>  
  
#### <a name="to-delete-a-merge-publication"></a><span data-ttu-id="d78ed-130">Удаление публикации слиянием</span><span class="sxs-lookup"><span data-stu-id="d78ed-130">To delete a merge publication</span></span>  
  
1.  <span data-ttu-id="d78ed-131">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="d78ed-131">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="d78ed-132">Чтобы удалить отдельную публикацию, выполните инструкцию [sp_dropmergepublication (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-dropmergepublication-transact-sql) в базе данных публикации на издателе.</span><span class="sxs-lookup"><span data-stu-id="d78ed-132">To delete a single publication, execute [sp_dropmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropmergepublication-transact-sql) at the Publisher on the publication database.</span></span>  
  
    -   <span data-ttu-id="d78ed-133">Чтобы удалить все публикации и удалить все объекты репликации из опубликованной базы данных, выполните процедуру [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) на издателе.</span><span class="sxs-lookup"><span data-stu-id="d78ed-133">To delete all publications in and remove all replication objects from a published database, execute [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) at the Publisher.</span></span> <span data-ttu-id="d78ed-134">Укажите значение `merge` для \*\* \@ типа\*\*.</span><span class="sxs-lookup"><span data-stu-id="d78ed-134">Specify a value of `merge` for **\@type**.</span></span> <span data-ttu-id="d78ed-135">Если распространитель недоступен или база данных находится в подозрительном состоянии или в режиме "вне сети", укажите значение **1** в параметре **\@force** (необязательно).</span><span class="sxs-lookup"><span data-stu-id="d78ed-135">(Optional) If the Distributor cannot be accessed or if the status of the database is suspect or offline, specify a value of **1** for **\@force**.</span></span> <span data-ttu-id="d78ed-136">Укажите имя базы данных в параметре **\@dbname**, если процедура [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) не выполнялась в базе данных публикации (необязательно).</span><span class="sxs-lookup"><span data-stu-id="d78ed-136">(Optional) Specify the name of the database for **\@dbname** if [sp_removedbreplication](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) is not executed on the publication database.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="d78ed-137">Если задать значение **1** в параметре **\@force**, в базе данных могут остаться объекты публикации, связанные с репликацией.</span><span class="sxs-lookup"><span data-stu-id="d78ed-137">Specifying a value of **1** for **\@force** may leave replication-related publishing objects in the database.</span></span>  
  
2.  <span data-ttu-id="d78ed-138">Если база данных содержит только одну публикацию, то для того, чтобы отключить публикацию текущей базы данных с помощью репликации слияния, выполните хранимую процедуру [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) (необязательно).</span><span class="sxs-lookup"><span data-stu-id="d78ed-138">(Optional) If this database has no other publications, execute [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) to disable publication of the current database using merge replication.</span></span>  
  
3.  <span data-ttu-id="d78ed-139">Чтобы удалить все метаданные репликации, оставшиеся в базе данных подписки, на подписчике в базе данных публикации выполните хранимую процедуру [sp_mergesubscription_cleanup (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-mergesubscription-cleanup-transact-sql) (необязательно).</span><span class="sxs-lookup"><span data-stu-id="d78ed-139">(Optional) At the Subscriber on the subscription database, execute [sp_mergesubscription_cleanup &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-mergesubscription-cleanup-transact-sql) to remove any remaining replication metadata in the subscription database.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="d78ed-140">Примеры (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="d78ed-140">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="d78ed-141">В следующем примере показано удаление публикации транзакций и отключение функции публикации транзакций для базы данных.</span><span class="sxs-lookup"><span data-stu-id="d78ed-141">This example shows how to remove a transactional publication and disable transactional publishing for a database.</span></span> <span data-ttu-id="d78ed-142">В этом примере предполагается, что все подписки были удалены ранее.</span><span class="sxs-lookup"><span data-stu-id="d78ed-142">This example assumes that all subscriptions were previously removed.</span></span> <span data-ttu-id="d78ed-143">Дополнительные сведения см. в разделе [Delete a Pull Subscription](../delete-a-pull-subscription.md) или [Delete a Push Subscription](../delete-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="d78ed-143">For more information, see [Delete a Pull Subscription](../delete-a-pull-subscription.md) or [Delete a Push Subscription](../delete-a-push-subscription.md).</span></span>  
  
 [!code-sql[HowTo#sp_droppublication](../../../snippets/tsql/SQL15/replication/howto/tsql/droptranpub.sql#sp_droppublication)]  
  
 <span data-ttu-id="d78ed-144">В следующем примере показано удаление публикации слиянием и отключение функции публикации слиянием для базы данных.</span><span class="sxs-lookup"><span data-stu-id="d78ed-144">This example shows how to remove a merge publication and disable merge publishing for a database.</span></span> <span data-ttu-id="d78ed-145">В этом примере предполагается, что все подписки были удалены ранее.</span><span class="sxs-lookup"><span data-stu-id="d78ed-145">This example assumes that all subscriptions were previously removed.</span></span> <span data-ttu-id="d78ed-146">Дополнительные сведения см. в разделе [Delete a Pull Subscription](../delete-a-pull-subscription.md) или [Delete a Push Subscription](../delete-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="d78ed-146">For more information, see [Delete a Pull Subscription](../delete-a-pull-subscription.md) or [Delete a Push Subscription](../delete-a-push-subscription.md).</span></span>  
  
 [!code-sql[HowTo#sp_dropmergepublication](../../../snippets/tsql/SQL15/replication/howto/tsql/dropmergepub.sql#sp_dropmergepublication)]  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="d78ed-147">При помощи объектов RMO</span><span class="sxs-lookup"><span data-stu-id="d78ed-147">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="d78ed-148">Публикации можно удалять программно с помощью объектов RMO.</span><span class="sxs-lookup"><span data-stu-id="d78ed-148">You can delete publications programmatically by using Replication Management Objects (RMO).</span></span> <span data-ttu-id="d78ed-149">Классы RMO, используемые, чтобы удалить публикацию, зависят от типа удаляемой публикации.</span><span class="sxs-lookup"><span data-stu-id="d78ed-149">The RMO classes that you use to remove a publication depend on the type of publication you remove.</span></span>  
  
#### <a name="to-remove-a-snapshot-or-transactional-publication"></a><span data-ttu-id="d78ed-150">Удаление публикации моментальных снимков или публикации транзакций</span><span class="sxs-lookup"><span data-stu-id="d78ed-150">To remove a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="d78ed-151">Создайте соединение с издателем с помощью класса <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="d78ed-151">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="d78ed-152">Создайте экземпляр класса <xref:Microsoft.SqlServer.Replication.TransPublication>.</span><span class="sxs-lookup"><span data-stu-id="d78ed-152">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransPublication> class.</span></span>  
  
3.  <span data-ttu-id="d78ed-153">Задайте для публикации свойства <xref:Microsoft.SqlServer.Replication.Publication.Name%2A> и <xref:Microsoft.SqlServer.Replication.Publication.DatabaseName%2A> , а также установите созданное на шаге 1 соединение <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> в качестве значения для свойства.</span><span class="sxs-lookup"><span data-stu-id="d78ed-153">Set the <xref:Microsoft.SqlServer.Replication.Publication.Name%2A> and <xref:Microsoft.SqlServer.Replication.Publication.DatabaseName%2A> properties for the publication, and set the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property to the connection created in step 1.</span></span>  
  
4.  <span data-ttu-id="d78ed-154">Чтобы убедиться в существовании публикации, проверьте свойство <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> .</span><span class="sxs-lookup"><span data-stu-id="d78ed-154">Check the <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> property to verify that the publication exists.</span></span> <span data-ttu-id="d78ed-155">Если значение этого свойства равно `false`, то либо на шаге 3 были неверно определены свойства публикации, либо публикация не существует.</span><span class="sxs-lookup"><span data-stu-id="d78ed-155">If the value of this property is `false`, either the publication properties in step 3 were defined incorrectly or the publication does not exist.</span></span>  
  
5.  <span data-ttu-id="d78ed-156">Вызовите метод <xref:Microsoft.SqlServer.Replication.Publication.Remove%2A> .</span><span class="sxs-lookup"><span data-stu-id="d78ed-156">Call the <xref:Microsoft.SqlServer.Replication.Publication.Remove%2A> method.</span></span>  
  
6.  <span data-ttu-id="d78ed-157">(Необязательно) Если в базе данных не существует других публикаций транзакций, базу данных можно отключить от публикации транзакций следующим образом.</span><span class="sxs-lookup"><span data-stu-id="d78ed-157">(Optional) If no other transactional publications exist for this database, the database can be disabled for transactional publishing as follows:</span></span>  
  
    1.  <span data-ttu-id="d78ed-158">Создайте экземпляр класса <xref:Microsoft.SqlServer.Replication.ReplicationDatabase>.</span><span class="sxs-lookup"><span data-stu-id="d78ed-158">Create an instance of the <xref:Microsoft.SqlServer.Replication.ReplicationDatabase> class.</span></span> <span data-ttu-id="d78ed-159">В качестве значения для свойства <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> укажите экземпляр соединения <xref:Microsoft.SqlServer.Management.Common.ServerConnection> , созданный на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="d78ed-159">Set the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property to the instance of <xref:Microsoft.SqlServer.Management.Common.ServerConnection> from step 1.</span></span>  
  
    2.  <span data-ttu-id="d78ed-160">Вызовите метод <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> .</span><span class="sxs-lookup"><span data-stu-id="d78ed-160">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method.</span></span> <span data-ttu-id="d78ed-161">Если этот метод возвращает значение `false`, убедитесь, что база данных существует.</span><span class="sxs-lookup"><span data-stu-id="d78ed-161">If this method returns `false`, confirm that the database exists.</span></span>  
  
    3.  <span data-ttu-id="d78ed-162">Задайте для свойства <xref:Microsoft.SqlServer.Replication.ReplicationDatabase.EnabledTransPublishing%2A> значение `false`.</span><span class="sxs-lookup"><span data-stu-id="d78ed-162">Set the <xref:Microsoft.SqlServer.Replication.ReplicationDatabase.EnabledTransPublishing%2A> property to `false`.</span></span>  
  
    4.  <span data-ttu-id="d78ed-163">Вызовите метод <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> .</span><span class="sxs-lookup"><span data-stu-id="d78ed-163">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method.</span></span>  
  
7.  <span data-ttu-id="d78ed-164">Закройте соединения.</span><span class="sxs-lookup"><span data-stu-id="d78ed-164">Close the connections.</span></span>  
  
#### <a name="to-remove-a-merge-publication"></a><span data-ttu-id="d78ed-165">Удаление публикации слиянием</span><span class="sxs-lookup"><span data-stu-id="d78ed-165">To remove a merge publication</span></span>  
  
1.  <span data-ttu-id="d78ed-166">Создайте соединение с издателем с помощью класса <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="d78ed-166">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="d78ed-167">Создайте экземпляр класса <xref:Microsoft.SqlServer.Replication.MergePublication>.</span><span class="sxs-lookup"><span data-stu-id="d78ed-167">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergePublication> class.</span></span>  
  
3.  <span data-ttu-id="d78ed-168">Задайте для публикации свойства <xref:Microsoft.SqlServer.Replication.Publication.Name%2A> и <xref:Microsoft.SqlServer.Replication.Publication.DatabaseName%2A> , а также установите созданное на шаге 1 соединение <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> в качестве значения для свойства.</span><span class="sxs-lookup"><span data-stu-id="d78ed-168">Set the <xref:Microsoft.SqlServer.Replication.Publication.Name%2A> and <xref:Microsoft.SqlServer.Replication.Publication.DatabaseName%2A> properties for the publication, and set the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property to the connection created in step 1.</span></span>  
  
4.  <span data-ttu-id="d78ed-169">Чтобы убедиться в существовании публикации, проверьте свойство <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> .</span><span class="sxs-lookup"><span data-stu-id="d78ed-169">Check the <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> property to verify that the publication exists.</span></span> <span data-ttu-id="d78ed-170">Если значение этого свойства равно `false`, то либо на шаге 3 были неверно определены свойства публикации, либо публикация не существует.</span><span class="sxs-lookup"><span data-stu-id="d78ed-170">If the value of this property is `false`, either the publication properties in step 3 were defined incorrectly or the publication does not exist.</span></span>  
  
5.  <span data-ttu-id="d78ed-171">Вызовите метод <xref:Microsoft.SqlServer.Replication.Publication.Remove%2A> .</span><span class="sxs-lookup"><span data-stu-id="d78ed-171">Call the <xref:Microsoft.SqlServer.Replication.Publication.Remove%2A> method.</span></span>  
  
6.  <span data-ttu-id="d78ed-172">(Необязательно) Если в базе данных не существует других публикаций слиянием, базу данных можно отключить от публикации слиянием следующим образом.</span><span class="sxs-lookup"><span data-stu-id="d78ed-172">(Optional) If no other merge publications exist for this database, the database can be disabled for merge publishing as follows:</span></span>  
  
    1.  <span data-ttu-id="d78ed-173">Создайте экземпляр класса <xref:Microsoft.SqlServer.Replication.ReplicationDatabase>.</span><span class="sxs-lookup"><span data-stu-id="d78ed-173">Create an instance of the <xref:Microsoft.SqlServer.Replication.ReplicationDatabase> class.</span></span> <span data-ttu-id="d78ed-174">Присвойте свойству <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> значение экземпляра <xref:Microsoft.SqlServer.Management.Common.ServerConnection> из шага 1.</span><span class="sxs-lookup"><span data-stu-id="d78ed-174">Set the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property to the instance of <xref:Microsoft.SqlServer.Management.Common.ServerConnection> from Step 1.</span></span>  
  
    2.  <span data-ttu-id="d78ed-175">Вызовите метод <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> .</span><span class="sxs-lookup"><span data-stu-id="d78ed-175">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method.</span></span> <span data-ttu-id="d78ed-176">Если этот метод возвращает значение `false`, проверьте, существует ли база данных.</span><span class="sxs-lookup"><span data-stu-id="d78ed-176">If this method returns `false`, verify that the database exists.</span></span>  
  
    3.  <span data-ttu-id="d78ed-177">Задайте для свойства <xref:Microsoft.SqlServer.Replication.ReplicationDatabase.EnabledMergePublishing%2A> значение `false`.</span><span class="sxs-lookup"><span data-stu-id="d78ed-177">Set the <xref:Microsoft.SqlServer.Replication.ReplicationDatabase.EnabledMergePublishing%2A> property to `false`.</span></span>  
  
    4.  <span data-ttu-id="d78ed-178">Вызовите метод <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> .</span><span class="sxs-lookup"><span data-stu-id="d78ed-178">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method.</span></span>  
  
7.  <span data-ttu-id="d78ed-179">Закройте соединения.</span><span class="sxs-lookup"><span data-stu-id="d78ed-179">Close the connections.</span></span>  
  
###  <a name="examples-rmo"></a><a name="PShellExample"></a> <span data-ttu-id="d78ed-180">Примеры (объекты RMO)</span><span class="sxs-lookup"><span data-stu-id="d78ed-180">Examples (RMO)</span></span>  
 <span data-ttu-id="d78ed-181">В следующем примере удаляется публикация транзакций.</span><span class="sxs-lookup"><span data-stu-id="d78ed-181">The following example deletes a transactional publication.</span></span> <span data-ttu-id="d78ed-182">Если в этой базе данных не существует других публикаций транзакций, публикация транзакций также отключается.</span><span class="sxs-lookup"><span data-stu-id="d78ed-182">If no other transactional publications exist for this database, transactional publishing is also disabled.</span></span>  
  
 [!code-csharp[HowTo#rmo_DropTranPub](../../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_droptranpub)]  
  
 [!code-vb[HowTo#rmo_vb_DropTranPub](../../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_droptranpub)]  
  
 <span data-ttu-id="d78ed-183">В следующем примере удаляется публикация слиянием.</span><span class="sxs-lookup"><span data-stu-id="d78ed-183">The following example deletes a merge publication.</span></span> <span data-ttu-id="d78ed-184">Если в этой базе данных не существует других публикаций слиянием, публикация слиянием также отключается.</span><span class="sxs-lookup"><span data-stu-id="d78ed-184">If no other merge publications exist for this database, merge publishing is also disabled.</span></span>  
  
 [!code-csharp[HowTo#rmo_DropMergePub](../../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_dropmergepub)]  
  
 [!code-vb[HowTo#rmo_vb_DropMergePub](../../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_dropmergepub)]  
  
## <a name="see-also"></a><span data-ttu-id="d78ed-185">См. также:</span><span class="sxs-lookup"><span data-stu-id="d78ed-185">See Also</span></span>  
 <span data-ttu-id="d78ed-186">[Replication System Stored Procedures Concepts](../concepts/replication-system-stored-procedures-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="d78ed-186">[Replication System Stored Procedures Concepts](../concepts/replication-system-stored-procedures-concepts.md) </span></span>  
 [<span data-ttu-id="d78ed-187">Публикация данных и объектов базы данных</span><span class="sxs-lookup"><span data-stu-id="d78ed-187">Publish Data and Database Objects</span></span>](publish-data-and-database-objects.md)  
  
  
