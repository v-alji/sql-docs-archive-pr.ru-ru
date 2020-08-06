---
title: Задание уровня совместимости для публикаций слиянием | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- compatibility [SQL Server], replication
- backward compatibility [SQL Server], replication
- publications [SQL Server replication], backward compatibility
ms.assetid: db47ac73-948b-4d77-b272-bb3565135ea5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 04ad80b0c99e7282ff2acfa459a08665efbdee1c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668769"
---
# <a name="set-the-compatibility-level-for-merge-publications"></a><span data-ttu-id="fb686-102">Задание уровня совместимости для публикаций слиянием</span><span class="sxs-lookup"><span data-stu-id="fb686-102">Set the Compatibility Level for Merge Publications</span></span>
  <span data-ttu-id="fb686-103">В этом разделе описывается установка уровня совместимости для публикации слиянием в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb686-103">This topic describes how to set the compatibility level for merge publications in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="fb686-104">В репликации слиянием с помощью уровня совместимости публикации определяется, какие функции могут использоваться публикациями в указанной базе данных.</span><span class="sxs-lookup"><span data-stu-id="fb686-104">Merge replication uses the publication compatibility level to determine which features can be used by publications in a given database.</span></span>  
  
 <span data-ttu-id="fb686-105">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="fb686-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="fb686-106">**Для установки уровня совместимости для публикаций слиянием используется:**</span><span class="sxs-lookup"><span data-stu-id="fb686-106">**To set the compatibility level for merge publications, using:**</span></span>  
  
     [<span data-ttu-id="fb686-107">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fb686-107">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="fb686-108">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fb686-108">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="fb686-109">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fb686-109">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="fb686-110">Установите уровень совместимости на странице **Типы подписчиков** мастера создания публикации.</span><span class="sxs-lookup"><span data-stu-id="fb686-110">Set the compatibility level on the **Subscriber Types** page of the New Publication Wizard.</span></span> <span data-ttu-id="fb686-111">Дополнительные сведения о доступе к этому мастеру см. в разделе [Create a Publication](create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="fb686-111">For more information on accessing this wizard, see [Create a Publication](create-a-publication.md).</span></span> <span data-ttu-id="fb686-112">После создания моментального снимка публикации уровень совместимости можно увеличить, но нельзя снизить.</span><span class="sxs-lookup"><span data-stu-id="fb686-112">After a publication snapshot is created, the compatibility level can be increased but cannot be decreased.</span></span> <span data-ttu-id="fb686-113">Увеличьте уровень совместимости на странице **Общие** диалогового окна **Свойства публикации — \<Publication>** .</span><span class="sxs-lookup"><span data-stu-id="fb686-113">Increase the compatibility level on the **General** page of the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="fb686-114">Дополнительные сведения о доступе к этому диалоговому окну см. в разделе [Просмотр и изменение свойств публикации](view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="fb686-114">For more information about accessing this dialog box, see [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span></span> <span data-ttu-id="fb686-115">При повышении уровня совместимости публикации все существующие подписки на серверах, использующих версии с меньшими уровнями совместимости, более не смогут синхронизироваться.</span><span class="sxs-lookup"><span data-stu-id="fb686-115">If you increase the publication compatibility level, any existing subscriptions at servers running versions prior to the compatibility level will no longer be able to synchronize.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fb686-116">Так как уровень совместимости влияет на другие свойства публикации, для которых свойства статьи являются допустимыми, не изменяйте одновременно уровень совместимости и другие свойства в одном сеансе работы с диалоговым окном.</span><span class="sxs-lookup"><span data-stu-id="fb686-116">Because the compatibility level has implications for other publication properties and for which article properties are valid, do not change the compatibility level and other properties in the same use of the dialog box.</span></span> <span data-ttu-id="fb686-117">После изменения свойства необходимо повторно сформировать моментальный снимок публикации.</span><span class="sxs-lookup"><span data-stu-id="fb686-117">The snapshot for the publication should be regenerated after the property is changed.</span></span>  
  
#### <a name="to-set-the-publication-compatibility-level"></a><span data-ttu-id="fb686-118">Установка уровня совместимости публикации</span><span class="sxs-lookup"><span data-stu-id="fb686-118">To set the publication compatibility level</span></span>  
  
-   <span data-ttu-id="fb686-119">На странице **Типы подписчиков** мастера создания публикации выберите типы подписчиков, которые должны поддерживаться публикацией.</span><span class="sxs-lookup"><span data-stu-id="fb686-119">On the **Subscriber Types** page of the New Publication Wizard, select the types of Subscribers that the publication should support.</span></span>  
  
#### <a name="to-increase-the-publication-compatibility-level"></a><span data-ttu-id="fb686-120">Повышение уровня совместимости публикации</span><span class="sxs-lookup"><span data-stu-id="fb686-120">To increase the publication compatibility level</span></span>  
  
-   <span data-ttu-id="fb686-121">На странице **Общие** диалогового окна **Свойства публикации — \<Publication>** выберите **Уровень совместимости**.</span><span class="sxs-lookup"><span data-stu-id="fb686-121">On the **General** page of the **Publication Properties - \<Publication>** dialog box, select for **Compatibility level**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="fb686-122">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fb686-122">Using Transact-SQL</span></span>  
 <span data-ttu-id="fb686-123">Уровень совместимости для публикации слиянием можно программно установить при создании публикации или программно изменить позже.</span><span class="sxs-lookup"><span data-stu-id="fb686-123">The compatibility level for a merge publication can either be set programmatically when a publication is created or modified programmatically at a later time.</span></span> <span data-ttu-id="fb686-124">Установить или изменить свойства публикации можно с помощью хранимых процедур репликации.</span><span class="sxs-lookup"><span data-stu-id="fb686-124">You can use replication stored procedures to set or change this publication property.</span></span>  
  
#### <a name="to-set-the-publication-compatibility-level-for-a-merge-publication"></a><span data-ttu-id="fb686-125">Установка уровня совместимости для публикации слиянием</span><span class="sxs-lookup"><span data-stu-id="fb686-125">To set the publication compatibility level for a merge publication</span></span>  
  
1.  <span data-ttu-id="fb686-126">На издателе выполните [sp_addmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql), указав значение, **@publication_compatibility_level** чтобы сделать публикацию совместимой с более старыми версиями [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fb686-126">At the Publisher, execute [sp_addmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql), specifying a value for **@publication_compatibility_level** to make the publication compatible with older versions of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="fb686-127">Дополнительные сведения см. в разделе [Create a Publication](create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="fb686-127">For more information, see [Create a Publication](create-a-publication.md).</span></span>  
  
#### <a name="to-change-the-publication-compatibility-level-of-a-merge-publication"></a><span data-ttu-id="fb686-128">Изменение уровня совместимости для публикации слиянием</span><span class="sxs-lookup"><span data-stu-id="fb686-128">To change the publication compatibility level of a merge publication</span></span>  
  
1.  <span data-ttu-id="fb686-129">Выполните [sp_changemergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql), указав **publication_compatibility_level** для **@property** и соответствующий уровень совместимости публикации для **@value** .</span><span class="sxs-lookup"><span data-stu-id="fb686-129">Execute [sp_changemergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql), specifying **publication_compatibility_level** for **@property** and the appropriate publication compatibility level for **@value**.</span></span>  
  
#### <a name="to-determine-the-publication-compatibility-level-of-a-merge-publication"></a><span data-ttu-id="fb686-130">Определение уровня совместимости для публикации слиянием</span><span class="sxs-lookup"><span data-stu-id="fb686-130">To determine the publication compatibility level of a merge publication</span></span>  
  
1.  <span data-ttu-id="fb686-131">Выполните процедуру [sp_helpmergepublication (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-helpmergepublication-transact-sql), указав нужную публикацию.</span><span class="sxs-lookup"><span data-stu-id="fb686-131">Execute [sp_helpmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpmergepublication-transact-sql), specifying the desired publication.</span></span>  
  
2.  <span data-ttu-id="fb686-132">Найдите уровень совместимости публикации в столбце **backward_comp_level** результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="fb686-132">Locate the publication compatibility level in the **backward_comp_level** column in the result set.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="fb686-133">Примеры (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="fb686-133">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="fb686-134">В примере создается публикация слиянием и устанавливается уровень совместимости публикации.</span><span class="sxs-lookup"><span data-stu-id="fb686-134">This example creates a merge publication and sets the publication compatibility level.</span></span>  
  
```  
-- To avoid storing the login and password in the script file, the values   
-- are passed into SQLCMD as scripting variables. For information about   
-- how to use scripting variables on the command line and in SQL Server  
-- Management Studio, see the "Executing Replication Scripts" section in  
-- the topic "Programming Replication Using System Stored Procedures".  
  
--Add a new merge publication.  
DECLARE @publicationDB AS sysname;  
DECLARE @publication AS sysname;  
DECLARE @login AS sysname;  
DECLARE @password AS sysname;  
SET @publicationDB = N'AdventureWorks2012';   
SET @publication = N'AdvWorksSalesOrdersMerge'   
SET @login = $(Login);  
SET @password = $(Password);  
  
-- Create a new merge publication.   
USE [AdventureWorks2012]  
EXEC sp_addmergepublication   
@publication = @publication,   
-- Set the compatibility level to SQL Server 2014.  
@publication_compatibility_level = '120RTM';   
  
-- Create the snapshot job for the publication.  
EXEC sp_addpublication_snapshot   
@publication = @publication,  
@job_login = @login,  
@job_password = @password;  
GO  
```  
  
 <span data-ttu-id="fb686-135">В примере изменяется уровень совместимости публикации для публикации слиянием.</span><span class="sxs-lookup"><span data-stu-id="fb686-135">This example changes the publication compatibility level for the merge publication.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fb686-136">Изменение уровня совместимости публикации может быть запрещено, если публикация использует функции, для которых необходим конкретный уровень совместимости.</span><span class="sxs-lookup"><span data-stu-id="fb686-136">Changing the publication compatibility level might not be allowed if the publication uses any features that require a particular compatibility level.</span></span> <span data-ttu-id="fb686-137">Дополнительные сведения см. в статье [Обратная совместимость репликации](../replication-backward-compatibility.md).</span><span class="sxs-lookup"><span data-stu-id="fb686-137">For more information, see [Replication Backward Compatibility](../replication-backward-compatibility.md).</span></span>  
  
```  
DECLARE @publication AS sysname;  
SET @publication = N'AdvWorksSalesOrdersMerge' ;  
  
-- Change the publication compatibility level to   
-- SQL Server 2012.  
EXEC sp_changemergepublication   
@publication = @publication,   
@property = N'publication_compatibility_level',   
@value = N'110RTM';  
GO  
  
```  
  
 <span data-ttu-id="fb686-138">В примере возвращается текущий уровень совместимости публикации для публикации слиянием.</span><span class="sxs-lookup"><span data-stu-id="fb686-138">This example returns the current publication compatibility level for the merge publication.</span></span>  
  
```  
DECLARE @publication AS sysname;  
SET @publication = N'AdvWorksSalesOrdersMerge' ;  
EXEC sp_helpmergepublication   
@publication = @publication;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="fb686-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="fb686-139">See Also</span></span>  
 [<span data-ttu-id="fb686-140">Create a Publication</span><span class="sxs-lookup"><span data-stu-id="fb686-140">Create a Publication</span></span>](create-a-publication.md)  
  
  
