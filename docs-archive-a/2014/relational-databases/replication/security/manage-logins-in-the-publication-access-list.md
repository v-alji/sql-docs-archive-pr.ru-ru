---
title: Управление именами для входа в списке доступа к публикации | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- logins [SQL Server replication], publication access list
- publications [SQL Server replication], publication access lists
- publication access list (PAL)
- PAL (publication access list)
- logins [SQL Server replication], managing
ms.assetid: fceb216b-0b18-4e3b-8ae0-13e35920dcbc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b96e6f46403cf3a482f00a3f5155527177920967
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657635"
---
# <a name="manage-logins-in-the-publication-access-list"></a><span data-ttu-id="1fbd8-102">Управление именами входа в списке доступа к публикации</span><span class="sxs-lookup"><span data-stu-id="1fbd8-102">Manage Logins in the Publication Access List</span></span>
  <span data-ttu-id="1fbd8-103">В этом разделе описывается управление именами входа в списке доступа к публикации в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1fbd8-103">This topic describes how to manage logins in the Publication Access List in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="1fbd8-104">Доступом к публикации управляет список доступа к публикации (PAL).</span><span class="sxs-lookup"><span data-stu-id="1fbd8-104">Access to a publication is controlled by the publication access list (PAL).</span></span> <span data-ttu-id="1fbd8-105">Имена входа и группы можно добавлять в список доступа к публикации и удалять из него.</span><span class="sxs-lookup"><span data-stu-id="1fbd8-105">Logins and groups can be added and removed from the PAL.</span></span>  
  
 <span data-ttu-id="1fbd8-106">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="1fbd8-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1fbd8-107">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="1fbd8-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1fbd8-108">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="1fbd8-108">Prerequisites</span></span>](#Prerequisites)  
  
-   <span data-ttu-id="1fbd8-109">**Для управления именами входа в списке доступа к публикации используется:**</span><span class="sxs-lookup"><span data-stu-id="1fbd8-109">**To manage logins in the Publication Access List, using:**</span></span>  
  
     [<span data-ttu-id="1fbd8-110">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1fbd8-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="1fbd8-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1fbd8-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1fbd8-112">Перед началом</span><span class="sxs-lookup"><span data-stu-id="1fbd8-112">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="1fbd8-113">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="1fbd8-113">Prerequisites</span></span>  
  
-   <span data-ttu-id="1fbd8-114">Перед добавлением имени входа [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] в список доступа к публикации необходимо связать его с пользователем базы данных публикации.</span><span class="sxs-lookup"><span data-stu-id="1fbd8-114">You must associate the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] login with a database user in the publication database before you add the login to the PAL.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1fbd8-115">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1fbd8-115">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="1fbd8-116">Управление именами для входа в списке доступа к публикации (PAL) осуществляется на странице **Список доступа к публикации** диалогового окна **Свойства публикации — \<Publication>** .</span><span class="sxs-lookup"><span data-stu-id="1fbd8-116">You use the publication access list (PAL) on the **Publication Access List** page of the **Publication Properties - \<Publication>** dialog box to manage logins.</span></span> <span data-ttu-id="1fbd8-117">Дополнительные сведения о доступе к этому диалоговому окну см. в статье [Просмотр и изменение свойств публикации](../publish/view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="1fbd8-117">For more information about how to access this dialog box, see [View and Modify Publication Properties](../publish/view-and-modify-publication-properties.md).</span></span>  
  
#### <a name="to-manage-logins-in-the-pal"></a><span data-ttu-id="1fbd8-118">Управление именами входа в списке доступа к публикации (PAL)</span><span class="sxs-lookup"><span data-stu-id="1fbd8-118">To manage logins in the PAL</span></span>  
  
1.  <span data-ttu-id="1fbd8-119">На странице **Список доступа к публикации** диалогового окна **Свойства публикации — \<Publication>** используйте кнопки **Добавить**, **Удалить** и **Удалить все** для добавления или удаления имен для входа и групп в списке доступа к публикации (PAL).</span><span class="sxs-lookup"><span data-stu-id="1fbd8-119">On the **Publication Access List** page of the **Publication Properties - \<Publication>** dialog box, use the **Add**, **Remove**, and **Remove All** buttons to add and remove logins and groups from the PAL.</span></span> <span data-ttu-id="1fbd8-120">Не удаляйте учетную запись **distributor_admin** из списка доступа к публикации.</span><span class="sxs-lookup"><span data-stu-id="1fbd8-120">Do not remove **distributor_admin** from the PAL.</span></span> <span data-ttu-id="1fbd8-121">Эта учетная запись используется при репликации.</span><span class="sxs-lookup"><span data-stu-id="1fbd8-121">This account is used by replication.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1fbd8-122">Если используется удаленный распространитель, то учетные записи в списке доступа к публикации должны быть доступны как на издателе, так и на распространителе.</span><span class="sxs-lookup"><span data-stu-id="1fbd8-122">If a remote Distributor is used, accounts in the PAL must be available at both the Publisher and the Distributor.</span></span> <span data-ttu-id="1fbd8-123">Это должны быть либо учетные записи домена, либо локальные учетные записи, определенные на обоих серверах.</span><span class="sxs-lookup"><span data-stu-id="1fbd8-123">The account must be either a domain account or a local account that is defined at both servers.</span></span> <span data-ttu-id="1fbd8-124">Пароли, связанные с обоими именами входа, должны совпадать.</span><span class="sxs-lookup"><span data-stu-id="1fbd8-124">The passwords that are associated with both logins must be the same.</span></span>  
  
2.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1fbd8-125">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1fbd8-125">Using Transact-SQL</span></span>  
  
#### <a name="to-view-groups-and-logins-that-belong-to-the-pal"></a><span data-ttu-id="1fbd8-126">Просмотр групп и имен входа из списка доступа к публикации</span><span class="sxs-lookup"><span data-stu-id="1fbd8-126">To view groups and logins that belong to the PAL</span></span>  
  
1.  <span data-ttu-id="1fbd8-127">На издателе в базе данных публикации выполните хранимую процедуру [sp_help_publication_access](/sql/relational-databases/system-stored-procedures/sp-help-publication-access-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1fbd8-127">At the Publisher on the publication database, execute [sp_help_publication_access](/sql/relational-databases/system-stored-procedures/sp-help-publication-access-transact-sql).</span></span> <span data-ttu-id="1fbd8-128">В поле \*\* \@ Публикация\*\*укажите имя публикации.</span><span class="sxs-lookup"><span data-stu-id="1fbd8-128">For **\@publication**, specify the publication name.</span></span> <span data-ttu-id="1fbd8-129">Будут отображены сведения о группах и именах входа из списка доступа к публикации.</span><span class="sxs-lookup"><span data-stu-id="1fbd8-129">This displays information about the groups and logins in the PAL.</span></span>  
  
#### <a name="to-add-groups-and-logins-to-the-pal"></a><span data-ttu-id="1fbd8-130">Добавление групп и имен входа в список доступа к публикации</span><span class="sxs-lookup"><span data-stu-id="1fbd8-130">To add groups and logins to the PAL</span></span>  
  
1.  <span data-ttu-id="1fbd8-131">На издателе в базе данных публикации выполните хранимую процедуру [sp_grant_publication_access](/sql/relational-databases/system-stored-procedures/sp-grant-publication-access-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1fbd8-131">At the Publisher on the publication database, execute [sp_grant_publication_access](/sql/relational-databases/system-stored-procedures/sp-grant-publication-access-transact-sql).</span></span> <span data-ttu-id="1fbd8-132">Для параметра \*\* \@ Публикация**укажите имя публикации, а в поле имя \*\* \@ входа**укажите имя входа или добавляемой группы.</span><span class="sxs-lookup"><span data-stu-id="1fbd8-132">For **\@publication**, specify the publication name; and for **\@login**, specify the name of the login or group that is being added.</span></span>  
  
#### <a name="to-remove-groups-and-logins-from-the-pal"></a><span data-ttu-id="1fbd8-133">Удаление групп и имен входа из списка доступа к публикации</span><span class="sxs-lookup"><span data-stu-id="1fbd8-133">To remove groups and logins from the PAL</span></span>  
  
1.  <span data-ttu-id="1fbd8-134">На издателе в базе данных публикации выполните хранимую процедуру [sp_revoke_publication_access](/sql/relational-databases/system-stored-procedures/sp-revoke-publication-access-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1fbd8-134">At the Publisher on the publication database, execute [sp_revoke_publication_access](/sql/relational-databases/system-stored-procedures/sp-revoke-publication-access-transact-sql).</span></span> <span data-ttu-id="1fbd8-135">В поле \*\* \@ Публикация**укажите имя публикации, а для параметра имя \*\* \@ входа**укажите имя входа или удаляемой группы.</span><span class="sxs-lookup"><span data-stu-id="1fbd8-135">For **\@publication**, specify the publication name; and for **\@login**, specify the name of the login or group that is being removed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fbd8-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="1fbd8-136">See Also</span></span>  
 <span data-ttu-id="1fbd8-137">[Replication Agent Security Model](replication-agent-security-model.md)  (Модель безопасности агента репликации)</span><span class="sxs-lookup"><span data-stu-id="1fbd8-137">[Replication Agent Security Model](replication-agent-security-model.md) </span></span>  
 <span data-ttu-id="1fbd8-138">[Защита топологии репликации](view-and-modify-replication-security-settings.md) </span><span class="sxs-lookup"><span data-stu-id="1fbd8-138">[Secure a Replication Topology](view-and-modify-replication-security-settings.md) </span></span>  
 [<span data-ttu-id="1fbd8-139">Защита издателя</span><span class="sxs-lookup"><span data-stu-id="1fbd8-139">Secure the Publisher</span></span>](secure-the-publisher.md)  
  
  
