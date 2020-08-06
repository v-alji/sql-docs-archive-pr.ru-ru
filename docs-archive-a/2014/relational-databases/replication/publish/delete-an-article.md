---
title: Удаление статьи | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- articles [SQL Server replication], dropping
- sp_droparticle
- sp_dropmergearticle
- deleting articles
- removing articles
- dropping articles
ms.assetid: 185b58fc-38c0-4abe-822e-6ec20066c863
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 082f90d33c2b8dedfae34dcada9b3935bed134ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656328"
---
# <a name="delete-an-article"></a><span data-ttu-id="b5f9a-102">Удаление статьи</span><span class="sxs-lookup"><span data-stu-id="b5f9a-102">Delete an Article</span></span>
  <span data-ttu-id="b5f9a-103">В данном разделе описывается удаление статьи в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] с помощью [!INCLUDE[tsql](../../../includes/tsql-md.md)] или объектов RMO.</span><span class="sxs-lookup"><span data-stu-id="b5f9a-103">This topic describes how to delete an article in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)] or Replication Management Objects (RMO).</span></span> <span data-ttu-id="b5f9a-104">Сведения об условиях, при которых статьи могут быть удалены, и о том, требуется ли при удалении статьи создание нового моментального снимка или повторная инициализация подписок, см. в [этой статье](add-articles-to-and-drop-articles-from-existing-publications.md).</span><span class="sxs-lookup"><span data-stu-id="b5f9a-104">For information about the conditions under which articles can be dropped and whether dropping an article requires a new snapshot or the reinitialization of subscriptions, see [Add Articles to and Drop Articles from Existing Publications](add-articles-to-and-drop-articles-from-existing-publications.md).</span></span>  
  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b5f9a-105">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b5f9a-105">Using Transact-SQL</span></span>  
 <span data-ttu-id="b5f9a-106">Статьи можно удалять программно, с помощью хранимых процедур репликации.</span><span class="sxs-lookup"><span data-stu-id="b5f9a-106">Articles can be deleted programmatically using replication stored procedures.</span></span> <span data-ttu-id="b5f9a-107">Хранимые процедуры, используемые для этого, зависят от типа публикации, к которой принадлежит статья.</span><span class="sxs-lookup"><span data-stu-id="b5f9a-107">The stored procedures that you use depend on the type of publication to which the article belongs.</span></span>  
  
#### <a name="to-delete-an-article-from-a-snapshot-or-transactional-publication"></a><span data-ttu-id="b5f9a-108">Удаление статьи из публикации моментальных снимков или публикации транзакций</span><span class="sxs-lookup"><span data-stu-id="b5f9a-108">To delete an article from a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="b5f9a-109">Чтобы удалить статью, указанную в параметре **\@article**, из публикации, указанной в параметре **\@publication**, выполните процедуру [sp_droparticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-droparticle-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b5f9a-109">Execute [sp_droparticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-droparticle-transact-sql) to delete an article, specified by **\@article**, from a publication, specified by **\@publication**.</span></span> <span data-ttu-id="b5f9a-110">Укажите значение **1** для \*\* \@ force_invalidate_snapshot\*\*.</span><span class="sxs-lookup"><span data-stu-id="b5f9a-110">Specify a value of **1** for **\@force_invalidate_snapshot**.</span></span>  
  
2.  <span data-ttu-id="b5f9a-111">(Необязательно) Чтобы полностью удалить опубликованный объект из базы данных, выполните команду `DROP <objectname>` на издателе для базы данных публикации.</span><span class="sxs-lookup"><span data-stu-id="b5f9a-111">(Optional) To remove the published object from the database entirely, execute the `DROP <objectname>` command at the Publisher on the publication database.</span></span>  
  
#### <a name="to-delete-an-article-from-a-merge-publication"></a><span data-ttu-id="b5f9a-112">Удаление статьи из публикации слиянием</span><span class="sxs-lookup"><span data-stu-id="b5f9a-112">To delete an article from a merge publication</span></span>  
  
1.  <span data-ttu-id="b5f9a-113">Чтобы удалить статью, указанную в параметре **\@article**, из публикации, указанной в параметре **\@publication**, выполните процедуру [sp_dropmergearticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropmergearticle-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b5f9a-113">Execute [sp_dropmergearticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropmergearticle-transact-sql) to delete an article, specified by **\@article**, from a publication, specified by **\@publication**.</span></span> <span data-ttu-id="b5f9a-114">При необходимости укажите значение **1** для \*\* \@ force_invalidate_snapshot\*\* и значение **1** для \*\* \@ force_reinit_subscription\*\*.</span><span class="sxs-lookup"><span data-stu-id="b5f9a-114">If necessary, specify a value of **1** for **\@force_invalidate_snapshot** and a value of **1** for **\@force_reinit_subscription**.</span></span>  
  
2.  <span data-ttu-id="b5f9a-115">(Необязательно) Чтобы полностью удалить опубликованный объект из базы данных, выполните команду `DROP <objectname>` на издателе для базы данных публикации.</span><span class="sxs-lookup"><span data-stu-id="b5f9a-115">(Optional) To remove the published object from the database entirely, execute the `DROP <objectname>` command at the Publisher on the publication database.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="b5f9a-116">Примеры (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="b5f9a-116">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="b5f9a-117">В следующем примере удаляется статья из публикации транзакций.</span><span class="sxs-lookup"><span data-stu-id="b5f9a-117">The following example deletes an article from a transactional publication.</span></span> <span data-ttu-id="b5f9a-118">Так как это изменение делает недействительным существующий моментальный снимок, для параметра \*\* \@ force_invalidate_snapshot\*\* указывается значение **1** .</span><span class="sxs-lookup"><span data-stu-id="b5f9a-118">Because this change invalidates the existing snapshot, a value of **1** is specified for the **\@force_invalidate_snapshot** parameter.</span></span>  
  
 [!code-sql[HowTo#sp_droparticle](../../../snippets/tsql/SQL15/replication/howto/tsql/droptranpub.sql#sp_droparticle)]  
  
 <span data-ttu-id="b5f9a-119">В следующем примере две статьи удаляются из публикации слиянием.</span><span class="sxs-lookup"><span data-stu-id="b5f9a-119">The following example deletes two articles from a merge publication.</span></span> <span data-ttu-id="b5f9a-120">Так как эти изменения делают недействительным существующий моментальный снимок, для параметра \*\* \@ force_invalidate_snapshot\*\* указывается значение **1** .</span><span class="sxs-lookup"><span data-stu-id="b5f9a-120">Because these changes invalidate the existing snapshot, a value of **1** is specified for the **\@force_invalidate_snapshot** parameter.</span></span>  
  
 [!code-sql[HowTo#sp_dropmergearticle](../../../snippets/tsql/SQL15/replication/howto/tsql/dropmergepub.sql#sp_dropmergearticle)]
 [!code-sql[HowTo#sp_dropmergearticle](../../../snippets/tsql/SQL15/replication/howto/tsql/dropmergearticles.sql#sp_dropmergearticle)]  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="b5f9a-121">При помощи объектов RMO</span><span class="sxs-lookup"><span data-stu-id="b5f9a-121">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="b5f9a-122">Удаление статьи можно произвести программным путем с помощью объектов RMO.</span><span class="sxs-lookup"><span data-stu-id="b5f9a-122">You can delete articles programmatically by using Replication Management Objects (RMO).</span></span> <span data-ttu-id="b5f9a-123">Какие именно классы RMO будут для этого применяться, зависит от типа публикации, которой принадлежит подписка.</span><span class="sxs-lookup"><span data-stu-id="b5f9a-123">The RMO classes you use to delete an article depend on the type of publication to which the article belongs.</span></span>  
  
#### <a name="to-delete-an-article-that-belongs-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="b5f9a-124">Удаление статьи, принадлежащей публикации моментальных снимков или транзакций</span><span class="sxs-lookup"><span data-stu-id="b5f9a-124">To delete an article that belongs to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="b5f9a-125">Создайте соединение с издателем с помощью класса <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="b5f9a-125">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="b5f9a-126">Создайте экземпляр класса <xref:Microsoft.SqlServer.Replication.TransArticle>.</span><span class="sxs-lookup"><span data-stu-id="b5f9a-126">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransArticle> class.</span></span>  
  
3.  <span data-ttu-id="b5f9a-127">Установите свойства <xref:Microsoft.SqlServer.Replication.Article.Name%2A>, <xref:Microsoft.SqlServer.Replication.Article.PublicationName%2A>и <xref:Microsoft.SqlServer.Replication.Article.DatabaseName%2A> .</span><span class="sxs-lookup"><span data-stu-id="b5f9a-127">Set the <xref:Microsoft.SqlServer.Replication.Article.Name%2A>, <xref:Microsoft.SqlServer.Replication.Article.PublicationName%2A>, and <xref:Microsoft.SqlServer.Replication.Article.DatabaseName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="b5f9a-128">Установите полученное на шаге 1 соединение в качестве значения свойства <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> .</span><span class="sxs-lookup"><span data-stu-id="b5f9a-128">Set the connection from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property.</span></span>  
  
5.  <span data-ttu-id="b5f9a-129">Проверьте свойство <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> , чтобы убедиться, что статья существует.</span><span class="sxs-lookup"><span data-stu-id="b5f9a-129">Check the <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> property to verify that the article exists.</span></span> <span data-ttu-id="b5f9a-130">Если это свойство имеет значение `false`, значит, на шаге 3 были неправильно заданы свойства статьи либо статья не существует.</span><span class="sxs-lookup"><span data-stu-id="b5f9a-130">If the value of this property is `false`, either the article properties in step 3 were defined incorrectly or the article does not exist.</span></span>  
  
6.  <span data-ttu-id="b5f9a-131">Вызовите метод <xref:Microsoft.SqlServer.Replication.Article.Remove%2A> .</span><span class="sxs-lookup"><span data-stu-id="b5f9a-131">Call the <xref:Microsoft.SqlServer.Replication.Article.Remove%2A> method.</span></span>  
  
7.  <span data-ttu-id="b5f9a-132">Закройте все соединения.</span><span class="sxs-lookup"><span data-stu-id="b5f9a-132">Close all connections.</span></span>  
  
#### <a name="to-delete-an-article-that-belongs-to-a-merge-publication"></a><span data-ttu-id="b5f9a-133">Удаление статьи, принадлежащей публикации слиянием</span><span class="sxs-lookup"><span data-stu-id="b5f9a-133">To delete an article that belongs to a merge publication</span></span>  
  
1.  <span data-ttu-id="b5f9a-134">Создайте соединение с издателем с помощью класса <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="b5f9a-134">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="b5f9a-135">Создайте экземпляр класса <xref:Microsoft.SqlServer.Replication.MergeArticle>.</span><span class="sxs-lookup"><span data-stu-id="b5f9a-135">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergeArticle> class.</span></span>  
  
3.  <span data-ttu-id="b5f9a-136">Установите свойства <xref:Microsoft.SqlServer.Replication.Article.Name%2A>, <xref:Microsoft.SqlServer.Replication.Article.PublicationName%2A>и <xref:Microsoft.SqlServer.Replication.Article.DatabaseName%2A> .</span><span class="sxs-lookup"><span data-stu-id="b5f9a-136">Set the <xref:Microsoft.SqlServer.Replication.Article.Name%2A>, <xref:Microsoft.SqlServer.Replication.Article.PublicationName%2A>, and <xref:Microsoft.SqlServer.Replication.Article.DatabaseName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="b5f9a-137">Установите полученное на шаге 1 соединение в качестве значения свойства <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> .</span><span class="sxs-lookup"><span data-stu-id="b5f9a-137">Set the connection from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property.</span></span>  
  
5.  <span data-ttu-id="b5f9a-138">Проверьте свойство <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> , чтобы убедиться, что статья существует.</span><span class="sxs-lookup"><span data-stu-id="b5f9a-138">Check the <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> property to verify that the article exists.</span></span> <span data-ttu-id="b5f9a-139">Если это свойство имеет значение `false`, значит, на шаге 3 были неправильно заданы свойства статьи либо статья не существует.</span><span class="sxs-lookup"><span data-stu-id="b5f9a-139">If the value of this property is `false`, either the article properties in step 3 were defined incorrectly or the article does not exist.</span></span>  
  
6.  <span data-ttu-id="b5f9a-140">Вызовите метод <xref:Microsoft.SqlServer.Replication.Article.Remove%2A> .</span><span class="sxs-lookup"><span data-stu-id="b5f9a-140">Call the <xref:Microsoft.SqlServer.Replication.Article.Remove%2A> method.</span></span>  
  
7.  <span data-ttu-id="b5f9a-141">Закройте все соединения.</span><span class="sxs-lookup"><span data-stu-id="b5f9a-141">Close all connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5f9a-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="b5f9a-142">See Also</span></span>  
 <span data-ttu-id="b5f9a-143">[Добавление и удаление статей в существующих публикациях](add-articles-to-and-drop-articles-from-existing-publications.md) </span><span class="sxs-lookup"><span data-stu-id="b5f9a-143">[Add Articles to and Drop Articles from Existing Publications](add-articles-to-and-drop-articles-from-existing-publications.md) </span></span>  
 [<span data-ttu-id="b5f9a-144">Replication System Stored Procedures Concepts</span><span class="sxs-lookup"><span data-stu-id="b5f9a-144">Replication System Stored Procedures Concepts</span></span>](../concepts/replication-system-stored-procedures-concepts.md)  
  
  
