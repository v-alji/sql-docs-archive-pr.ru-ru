---
title: Предоставление пользователям без прав администратора разрешений на использование монитора репликации | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Replication Monitor, non-administrators access
ms.assetid: 1cf21d9e-831d-41a1-a5a0-83ff6d22fa86
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f4a7699c555086d627e4c3a52ea70acf931ea1af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657654"
---
# <a name="allow-non-administrators-to-use-replication-monitor"></a><span data-ttu-id="d778e-102">Предоставление пользователям без прав администратора разрешения на использование монитора репликации</span><span class="sxs-lookup"><span data-stu-id="d778e-102">Allow Non-Administrators to Use Replication Monitor</span></span>
  <span data-ttu-id="d778e-103">В этом разделе показано, как разрешить пользователям без прав администратора использовать монитор репликации в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] при помощи среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d778e-103">This topic describes how to allow non-administrators to use Replication Monitor in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="d778e-104">Монитор репликации может использоваться пользователями, которые являются членами следующих ролей:</span><span class="sxs-lookup"><span data-stu-id="d778e-104">Replication Monitor can be used by users who are members of the following roles:</span></span>  
  
-   <span data-ttu-id="d778e-105">Предопределенная роль сервера **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="d778e-105">The **sysadmin** fixed server role.</span></span>  
  
     <span data-ttu-id="d778e-106">Такие пользователи могут выполнять наблюдение за репликацией и полностью контролировать процессы внесения изменений в свойства репликации, а именно: расписания работы агентов, профили агентов и т. д.</span><span class="sxs-lookup"><span data-stu-id="d778e-106">These users can monitor replication and have full control over changing replication properties such as agent schedules, agent profiles, and so on.</span></span>  
  
-   <span data-ttu-id="d778e-107">`replmonitor`Роль базы данных в базе данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="d778e-107">The `replmonitor` database role in the distribution database.</span></span>  
  
     <span data-ttu-id="d778e-108">Такие пользователи могут выполнять наблюдение за репликацией, но не могут вносить изменения ни в какие свойства репликации.</span><span class="sxs-lookup"><span data-stu-id="d778e-108">These users can monitor replication, but cannot change any replication properties.</span></span>  
  
 <span data-ttu-id="d778e-109">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="d778e-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d778e-110">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="d778e-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d778e-111">Безопасность</span><span class="sxs-lookup"><span data-stu-id="d778e-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d778e-112">**Для предоставления пользователям без прав администратора разрешения на использование монитора репликации используется:**</span><span class="sxs-lookup"><span data-stu-id="d778e-112">**To allow non-administrators to use Replication Monitor, using:**</span></span>  
  
     [<span data-ttu-id="d778e-113">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d778e-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d778e-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d778e-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d778e-115">Перед началом</span><span class="sxs-lookup"><span data-stu-id="d778e-115">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d778e-116">безопасность</span><span class="sxs-lookup"><span data-stu-id="d778e-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d778e-117">Permissions</span><span class="sxs-lookup"><span data-stu-id="d778e-117">Permissions</span></span>  
 <span data-ttu-id="d778e-118">Чтобы разрешить пользователям без прав администратора использовать монитор репликации, член предопределенной роли сервера **sysadmin** должен добавить пользователя в базу данных распространителя и назначить его `replmonitor` роли.</span><span class="sxs-lookup"><span data-stu-id="d778e-118">To allow non-administrators to use Replication Monitor, a member of the **sysadmin** fixed server role must add the user to the distribution database and assign that user to the `replmonitor` role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d778e-119">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d778e-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-allow-non-administrators-to-use-replication-monitor"></a><span data-ttu-id="d778e-120">Предоставление пользователям без прав администратора разрешения на использование монитора репликации</span><span class="sxs-lookup"><span data-stu-id="d778e-120">To allow non-administrators to use Replication Monitor</span></span>  
  
1.  <span data-ttu-id="d778e-121">В среде [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]подключитесь к распространителю, а затем разверните узел сервера.</span><span class="sxs-lookup"><span data-stu-id="d778e-121">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], connect to the Distributor, and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="d778e-122">Последовательно раскройте **Базы данных**, **Системные базы данных**и раскройте базу данных распространителя (по умолчанию называемую **distribution** ).</span><span class="sxs-lookup"><span data-stu-id="d778e-122">Expand **Databases**, expand **System Databases**, and then expand the distribution database (named **distribution** by default).</span></span>  
  
3.  <span data-ttu-id="d778e-123">Раскройте **Безопасность**, щелкните правой кнопкой **Пользователь**, а затем выберите **Создать пользователя...**.</span><span class="sxs-lookup"><span data-stu-id="d778e-123">Expand **Security**, right-click **Users**, and then click **New User**.</span></span>  
  
4.  <span data-ttu-id="d778e-124">Введите имя пользователя и имя входа.</span><span class="sxs-lookup"><span data-stu-id="d778e-124">Enter a user name and login for the user.</span></span>  
  
5.  <span data-ttu-id="d778e-125">Выберите схему по умолчанию `replmonitor` .</span><span class="sxs-lookup"><span data-stu-id="d778e-125">Select a default schema of `replmonitor`.</span></span>  
  
6.  <span data-ttu-id="d778e-126">Установите `replmonitor` флажок в сетке **членство в роли базы данных** .</span><span class="sxs-lookup"><span data-stu-id="d778e-126">Select the `replmonitor` check box in the **Database role membership** grid.</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d778e-127">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d778e-127">Using Transact-SQL</span></span>  
  
#### <a name="to-add-a-user-to-the-replmonitor-fixed-database-role"></a><span data-ttu-id="d778e-128">Добавление пользователя к предопределенной роли «replmonitor» базы данных</span><span class="sxs-lookup"><span data-stu-id="d778e-128">To add a user to the replmonitor fixed database role</span></span>  
  
1.  <span data-ttu-id="d778e-129">В базе данных на распространителе выполните процедуру [sp_helpuser &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpuser-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d778e-129">At the Distributor on the distribution database, execute [sp_helpuser &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpuser-transact-sql).</span></span> <span data-ttu-id="d778e-130">Если пользователь не перечислен в `UserName` результирующем наборе, ему должен быть предоставлен доступ к базе данных распространителя с помощью инструкции [CREATE USER &#40;TRANSACT-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="d778e-130">If the user is not listed in `UserName` in the result set, the user must be granted access to the distribution database using the [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql) statement.</span></span>  
  
2.  <span data-ttu-id="d778e-131">На распространителе в базе данных распространителя выполните [sp_helprolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helprolemember-transact-sql), указав значение `replmonitor` для **@rolename** параметра.</span><span class="sxs-lookup"><span data-stu-id="d778e-131">At the Distributor on the distribution database, execute [sp_helprolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helprolemember-transact-sql), specifying a value of `replmonitor` for the **@rolename** parameter.</span></span> <span data-ttu-id="d778e-132">Если пользователь перечислен в `MemberName` результирующем наборе, он уже принадлежит этой роли.</span><span class="sxs-lookup"><span data-stu-id="d778e-132">If the user is listed in `MemberName` in the result set, the user already belongs to this role.</span></span>  
  
3.  <span data-ttu-id="d778e-133">Если пользователь не принадлежит `replmonitor` роли, выполните [Sp_addrolemember &#40;TRANSACT-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addrolemember-transact-sql) на распространителе в базе данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="d778e-133">If the user does not belong to the `replmonitor` role, execute [sp_addrolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addrolemember-transact-sql) at the Distributor on the distribution database.</span></span> <span data-ttu-id="d778e-134">Укажите значение `replmonitor` для **@rolename** , а также имя пользователя базы данных или [!INCLUDE[msCoName](../../../includes/msconame-md.md)] логин Windows, добавляемый для **@membername** .</span><span class="sxs-lookup"><span data-stu-id="d778e-134">Specify a value of `replmonitor` for **@rolename** and the name of the database user or the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows login being added for **@membername**.</span></span>  
  
#### <a name="to-remove-a-user-from-the-replmonitor-fixed-database-role"></a><span data-ttu-id="d778e-135">Удаление пользователя из предопределенной роли «replmonitor» базы данных</span><span class="sxs-lookup"><span data-stu-id="d778e-135">To remove a user from the replmonitor fixed database role</span></span>  
  
1.  <span data-ttu-id="d778e-136">Чтобы убедиться, что пользователь принадлежит к `replmonitor` роли, выполните [Sp_helprolemember &#40;TRANSACT-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helprolemember-transact-sql) на распространителе в базе данных распространителя и укажите значение `replmonitor` для параметра **@rolename** .</span><span class="sxs-lookup"><span data-stu-id="d778e-136">To verify that the user belongs to the `replmonitor` role, execute [sp_helprolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helprolemember-transact-sql) at the Distributor on the distribution database, and specify a value of `replmonitor` for **@rolename**.</span></span> <span data-ttu-id="d778e-137">Если пользователь не указан в поле `MemberName` результирующего набора, в данный момент он не принадлежит этой роли.</span><span class="sxs-lookup"><span data-stu-id="d778e-137">If the user is not listed in `MemberName` in the result set, the user does not currently belong to this role.</span></span>  
  
2.  <span data-ttu-id="d778e-138">Если пользователь принадлежит к `replmonitor` роли, выполните [Sp_droprolemember &#40;TRANSACT-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-droprolemember-transact-sql) на распространителе в базе данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="d778e-138">If the user does belong to the `replmonitor` role, execute [sp_droprolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-droprolemember-transact-sql) at the Distributor on the distribution database.</span></span> <span data-ttu-id="d778e-139">Укажите значение `replmonitor` для **@rolename** , а также имя пользователя базы данных или имени входа Windows, которое удаляется для **@membername** .</span><span class="sxs-lookup"><span data-stu-id="d778e-139">Specify a value of `replmonitor` for **@rolename** and the name of the database user or the Windows login being removed for **@membername**.</span></span>  
  
  
