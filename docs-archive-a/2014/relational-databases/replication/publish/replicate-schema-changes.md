---
title: Репликация изменений схемы | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], schema changes
- schemas [SQL Server replication], replicating changes
ms.assetid: c09007f0-9374-4f60-956b-8a87670cd043
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bec2f363cd8c4f7dea45935568a88722b19323fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664870"
---
# <a name="replicate-schema-changes"></a><span data-ttu-id="1a0b7-102">Репликация изменений схемы</span><span class="sxs-lookup"><span data-stu-id="1a0b7-102">Replicate Schema Changes</span></span>
  <span data-ttu-id="1a0b7-103">В этом разделе описывается процесс репликации изменений схемы в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1a0b7-103">This topic describes how to replicate schema changes in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="1a0b7-104">Если в опубликованную статью внести следующие изменения схемы, они по умолчанию распространяются на подписчики [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1a0b7-104">If you make the following schema changes to a published article, they are propagated, by default, to [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Subscribers:</span></span>  
  
-   <span data-ttu-id="1a0b7-105">ALTER TABLE</span><span class="sxs-lookup"><span data-stu-id="1a0b7-105">ALTER TABLE</span></span>  
  
-   <span data-ttu-id="1a0b7-106">ALTER VIEW</span><span class="sxs-lookup"><span data-stu-id="1a0b7-106">ALTER VIEW</span></span>  
  
-   <span data-ttu-id="1a0b7-107">ALTER PROCEDURE</span><span class="sxs-lookup"><span data-stu-id="1a0b7-107">ALTER PROCEDURE</span></span>  
  
-   <span data-ttu-id="1a0b7-108">ALTER FUNCTION</span><span class="sxs-lookup"><span data-stu-id="1a0b7-108">ALTER FUNCTION</span></span>  
  
-   <span data-ttu-id="1a0b7-109">ALTER TRIGGER</span><span class="sxs-lookup"><span data-stu-id="1a0b7-109">ALTER TRIGGER</span></span>  
  
 <span data-ttu-id="1a0b7-110">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="1a0b7-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1a0b7-111">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="1a0b7-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1a0b7-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="1a0b7-112">Limitations and Restrictions</span></span>](#Restrictions)  
  
-   <span data-ttu-id="1a0b7-113">**Для репликации изменений схемы используется:**</span><span class="sxs-lookup"><span data-stu-id="1a0b7-113">**To replicate schema changes, using:**</span></span>  
  
     [<span data-ttu-id="1a0b7-114">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1a0b7-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="1a0b7-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1a0b7-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1a0b7-116">Перед началом</span><span class="sxs-lookup"><span data-stu-id="1a0b7-116">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="1a0b7-117">Ограничения</span><span class="sxs-lookup"><span data-stu-id="1a0b7-117">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="1a0b7-118">Инструкция ALTER TABLE ... DROP COLUMN всегда реплицируется для всех подписчиков, чьи подписки содержат удаляемые столбцы, даже при отключенной репликации изменений схемы.</span><span class="sxs-lookup"><span data-stu-id="1a0b7-118">The ALTER TABLE ... DROP COLUMN statement is always replicated to all Subscribers whose subscription contains the columns being dropped, even if you disable the replication of schema changes.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1a0b7-119">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1a0b7-119">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="1a0b7-120">Если реплицировать изменения схемы для публикации не требуется, отключите репликацию изменений схемы в диалоговом окне **Свойства публикации — \<Publication>** .</span><span class="sxs-lookup"><span data-stu-id="1a0b7-120">If you do not want to replicate schema changes for a publication, disable the replication of schema changes in the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="1a0b7-121">Дополнительные сведения о доступе к этому диалоговому окну см. в разделе [Просмотр и изменение свойств публикации](view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="1a0b7-121">For more information about accessing this dialog box, see [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span></span>  
  
#### <a name="to-disable-replication-of-schema-changes"></a><span data-ttu-id="1a0b7-122">Отключение репликации изменений схемы</span><span class="sxs-lookup"><span data-stu-id="1a0b7-122">To disable replication of schema changes</span></span>  
  
1.  <span data-ttu-id="1a0b7-123">На странице **Параметры подписки** диалогового окна **Свойства публикации — \<Publication>** установите для свойства **Реплицировать изменения схемы** значение **False**.</span><span class="sxs-lookup"><span data-stu-id="1a0b7-123">On the **Subscription Options** page of the **Publication Properties - \<Publication>** dialog box, set the value of the **Replicate schema changes** property to **False**.</span></span>  
  
2.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
     <span data-ttu-id="1a0b7-124">Для распространения только определенных изменений схемы перед изменением схемы установите свойство в **True** , а после выполнения изменений установите его в **False** .</span><span class="sxs-lookup"><span data-stu-id="1a0b7-124">To propagate only specific schema changes, set the property to **True** before a schema change, and then set it to **False** after the change is made.</span></span> <span data-ttu-id="1a0b7-125">И наоборот, для распространения всех изменений схемы, за исключением данного изменения, перед изменением схемы установите свойство в **False** , а после выполнения изменений установите его в **True** .</span><span class="sxs-lookup"><span data-stu-id="1a0b7-125">Conversely, to propagate most schema changes, but not a given change, set the property to **False** before the schema change, and then set it to **True** after the change is made.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1a0b7-126">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1a0b7-126">Using Transact-SQL</span></span>  
 <span data-ttu-id="1a0b7-127">Можно использовать хранимые процедуры репликации для указания, следует ли реплицировать эти изменения схемы.</span><span class="sxs-lookup"><span data-stu-id="1a0b7-127">You can use replication stored procedures to specify whether these schema changes are replicated.</span></span> <span data-ttu-id="1a0b7-128">Используемая хранимая процедура зависит от типа публикации.</span><span class="sxs-lookup"><span data-stu-id="1a0b7-128">The stored procedure that you use depends on the type of publication.</span></span>  
  
#### <a name="to-create-a-snapshot-or-transactional-publication-that-does-not-replicate-schema-changes"></a><span data-ttu-id="1a0b7-129">Создание публикации моментальных снимков или публикации транзакций без репликации изменений схемы</span><span class="sxs-lookup"><span data-stu-id="1a0b7-129">To create a snapshot or transactional publication that does not replicate schema changes</span></span>  
  
1.  <span data-ttu-id="1a0b7-130">На издателе в базе данных публикации выполните [sp_addpublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql), указав значение **0** для \*\* \@ replicate_ddl\*\*.</span><span class="sxs-lookup"><span data-stu-id="1a0b7-130">At the Publisher on the publication database, execute [sp_addpublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql), specifying a value of **0** for **\@replicate_ddl**.</span></span> <span data-ttu-id="1a0b7-131">Дополнительные сведения см. в разделе [Create a Publication](create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="1a0b7-131">For more information, see [Create a Publication](create-a-publication.md).</span></span>  
  
#### <a name="to-create-a-merge-publication-that-does-not-replicate-schema-changes"></a><span data-ttu-id="1a0b7-132">Создание публикации слиянием без репликации изменений схемы</span><span class="sxs-lookup"><span data-stu-id="1a0b7-132">To create a merge publication that does not replicate schema changes</span></span>  
  
1.  <span data-ttu-id="1a0b7-133">На издателе в базе данных публикации выполните [sp_addmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql), указав значение **0** для \*\* \@ replicate_ddl\*\*.</span><span class="sxs-lookup"><span data-stu-id="1a0b7-133">At the Publisher on the publication database, execute [sp_addmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql), specifying a value of **0** for **\@replicate_ddl**.</span></span> <span data-ttu-id="1a0b7-134">Дополнительные сведения см. в разделе [Create a Publication](create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="1a0b7-134">For more information, see [Create a Publication](create-a-publication.md).</span></span>  
  
#### <a name="to-temporarily-disable-replicating-schema-changes-for-a-snapshot-or-transactional-publication"></a><span data-ttu-id="1a0b7-135">Временное отключение репликации изменений схемы для публикации моментальных снимков или публикации транзакций</span><span class="sxs-lookup"><span data-stu-id="1a0b7-135">To temporarily disable replicating schema changes for a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="1a0b7-136">Для публикации с репликацией изменений схемы выполните [sp_changepublication &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql), указав значение **replicate_ddl** для \*\* \@ Свойства\*\* и значение **0** в качестве \*\* \@ значения\*\*.</span><span class="sxs-lookup"><span data-stu-id="1a0b7-136">For a publication with replication of schema changes, execute [sp_changepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql), specifying a value of **replicate_ddl** for **\@property** and a value of **0** for **\@value**.</span></span>  
  
2.  <span data-ttu-id="1a0b7-137">Выполните команду DDL на опубликованном объекте.</span><span class="sxs-lookup"><span data-stu-id="1a0b7-137">Execute the DDL command on the published object.</span></span>  
  
3.  <span data-ttu-id="1a0b7-138">Используемых Повторно включите репликацию изменений схемы, выполнив [sp_changepublication &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql), указав значение **replicate_ddl** для \*\* \@ Свойства\*\* и значение **1** в качестве \*\* \@ значения\*\*.</span><span class="sxs-lookup"><span data-stu-id="1a0b7-138">(Optional) Re-enable replicating schema changes by executing [sp_changepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql), specifying a value of **replicate_ddl** for **\@property** and a value of **1** for **\@value**.</span></span>  
  
#### <a name="to-temporarily-disable-replicating-schema-changes-for-a-merge-publication"></a><span data-ttu-id="1a0b7-139">Временное отключение репликации изменений схемы для публикации слиянием</span><span class="sxs-lookup"><span data-stu-id="1a0b7-139">To temporarily disable replicating schema changes for a merge publication</span></span>  
  
1.  <span data-ttu-id="1a0b7-140">Для публикации с репликацией изменений схемы выполните [sp_changemergepublication &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql), указав значение **replicate_ddl** для \*\* \@ Свойства\*\* и значение **0** в качестве \*\* \@ значения\*\*.</span><span class="sxs-lookup"><span data-stu-id="1a0b7-140">For a publication with replication of schema changes, execute [sp_changemergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql), specifying a value of **replicate_ddl** for **\@property** and a value of **0** for **\@value**.</span></span>  
  
2.  <span data-ttu-id="1a0b7-141">Выполните команду DDL на опубликованном объекте.</span><span class="sxs-lookup"><span data-stu-id="1a0b7-141">Execute the DDL command on the published object.</span></span>  
  
3.  <span data-ttu-id="1a0b7-142">Используемых Повторно включите репликацию изменений схемы, выполнив [sp_changemergepublication &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql), указав значение **replicate_ddl** для \*\* \@ Свойства\*\* и значение **1** в качестве \*\* \@ значения\*\*.</span><span class="sxs-lookup"><span data-stu-id="1a0b7-142">(Optional) Re-enable replicating schema changes by executing [sp_changemergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql), specifying a value of **replicate_ddl** for **\@property** and a value of **1** for **\@value**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a0b7-143">См. также:</span><span class="sxs-lookup"><span data-stu-id="1a0b7-143">See Also</span></span>  
 <span data-ttu-id="1a0b7-144">[Внесение изменений в схемы баз данных публикации](make-schema-changes-on-publication-databases.md) </span><span class="sxs-lookup"><span data-stu-id="1a0b7-144">[Make Schema Changes on Publication Databases](make-schema-changes-on-publication-databases.md) </span></span>  
 [<span data-ttu-id="1a0b7-145">Внесение изменений в схемы баз данных публикации</span><span class="sxs-lookup"><span data-stu-id="1a0b7-145">Make Schema Changes on Publication Databases</span></span>](make-schema-changes-on-publication-databases.md)  
  
  
