---
title: Создание профиля компонента Database Mail | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Database Mail [SQL Server], public profiles
- profiles [SQL Server], Database Mail
- public profiles [Database Mail]
ms.assetid: 58ae749d-6ada-4f9c-bf00-de7c7a992a2d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0453d495c90c1e599bfc7777b4899f30e6659c52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657814"
---
# <a name="create-a-database-mail-profile"></a><span data-ttu-id="8560e-102">Создание профиля компонента Database Mail</span><span class="sxs-lookup"><span data-stu-id="8560e-102">Create a Database Mail Profile</span></span>
  <span data-ttu-id="8560e-103">Открытые и закрытые профили компонента Database Mail можно создать с помощью **мастера настройки компонента Database Mail** или [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8560e-103">Use either the **Database Mail Configuration Wizard** or [!INCLUDE[tsql](../../includes/tsql-md.md)] to create Database Mail public and private profiles.</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8560e-104">Перед началом</span><span class="sxs-lookup"><span data-stu-id="8560e-104">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="8560e-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="8560e-105">Prerequisites</span></span>  
 <span data-ttu-id="8560e-106">Создайте одну или несколько учетных записей компонента Database Mail для профиля.</span><span class="sxs-lookup"><span data-stu-id="8560e-106">Create one or more Database Mail accounts for the profile.</span></span> <span data-ttu-id="8560e-107">Дополнительные сведения о создании компонента Database Mail см. в разделе [Создание учетной записи компонента Database Mail](create-a-database-mail-account.md).</span><span class="sxs-lookup"><span data-stu-id="8560e-107">For more information about creating Database Mail accounts, see [Create a Database Mail Account](create-a-database-mail-account.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8560e-108">безопасность</span><span class="sxs-lookup"><span data-stu-id="8560e-108">Security</span></span>  
 <span data-ttu-id="8560e-109">Открытый профиль дает возможность всем пользователям получать доступ к базе данных **msdb** , отправив туда почтовое сообщение из этого профиля.</span><span class="sxs-lookup"><span data-stu-id="8560e-109">A public profile allows any user with access to the **msdb** database to send e-mail using that profile.</span></span> <span data-ttu-id="8560e-110">Персональный профиль может использоваться как пользователем, так и ролью.</span><span class="sxs-lookup"><span data-stu-id="8560e-110">A private profile can be used by a user or by a role.</span></span> <span data-ttu-id="8560e-111">Предоставление роли доступа к профилю создает более простую обслуживаемую архитектуру.</span><span class="sxs-lookup"><span data-stu-id="8560e-111">Granting roles access to profiles creates a more easily maintained architecture.</span></span> <span data-ttu-id="8560e-112">Для отправки почты пользователь должен быть членом роли **DatabaseMailUserRole** в базе данных **msdb** , а также иметь доступ как минимум к одному профилю Database Mail.</span><span class="sxs-lookup"><span data-stu-id="8560e-112">To send mail you must be a member of the **DatabaseMailUserRole** in the **msdb** database, and have access to at least one Database Mail profile.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8560e-113">Permissions</span><span class="sxs-lookup"><span data-stu-id="8560e-113">Permissions</span></span>  
 <span data-ttu-id="8560e-114">Пользователь, создающий учетные записи профилей и выполняющий хранимые процедуры, должен быть членом предопределенной роли сервера sysadmin.</span><span class="sxs-lookup"><span data-stu-id="8560e-114">The user creating the profiles accounts and executing stored procedures should be a member of the sysadmin fixed server role.</span></span>  
  

  
##  <a name="using-database-mail-configuration-wizard"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8560e-115">Использование мастера настройки компонента Database Mail</span><span class="sxs-lookup"><span data-stu-id="8560e-115">Using Database Mail Configuration Wizard</span></span>  
 <span data-ttu-id="8560e-116">**Создание профиля компонента Database Mail**</span><span class="sxs-lookup"><span data-stu-id="8560e-116">**To Create a Database Mail profile**</span></span>  
  
-   <span data-ttu-id="8560e-117">В обозревателе объектов подключитесь к экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , для которого необходимо настроить компонент Database Mail, и разверните дерево сервера.</span><span class="sxs-lookup"><span data-stu-id="8560e-117">In Object Explorer, connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you want to configure Database Mail on, and expand the server tree.</span></span>  
  
-   <span data-ttu-id="8560e-118">Разверните узел **Управление**</span><span class="sxs-lookup"><span data-stu-id="8560e-118">Expand the **Management** node</span></span>  
  
-   <span data-ttu-id="8560e-119">Дважды щелкните компонент Database Mail, чтобы открыть мастер настройки компонента Database Mail.</span><span class="sxs-lookup"><span data-stu-id="8560e-119">Double click Database Mail to open the Database Mail Configuration Wizard.</span></span>  
  
-   <span data-ttu-id="8560e-120">На странице **Выбор задачи настройки** установите флажок **Управление учетными записями и профилями Database Mail** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8560e-120">On the **Select Configuration Task** page, select **Manage Database Mail accounts and profiles** option and click **Next**.</span></span>  
  
-   <span data-ttu-id="8560e-121">На странице **Управление профилями и учетными записями** выберите команду **Создать новый профиль** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8560e-121">On the **Manage Profiles and Accounts** page, select **Create a new profile** option, and click **Next**.</span></span>  
  
-   <span data-ttu-id="8560e-122">На странице **Создать профиль** задайте имя профиля и описание, а также добавьте учетные записи, которые будут включены в профиль, после чего нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8560e-122">On the **New Profile** page, specify the Profile name, Description and add accounts to be included in the profile, and click **Next**.</span></span>  
  
-   <span data-ttu-id="8560e-123">На странице **Завершение работы мастера** просмотрите действия, которые будут выполнены, и нажмите кнопку **Готово** , чтобы завершить создание нового профиля.</span><span class="sxs-lookup"><span data-stu-id="8560e-123">On the **Complete the Wizard** page, review the actions to be performed and click **Finish** to complete creating the new profile.</span></span>  
  
-   <span data-ttu-id="8560e-124">**Настройка закрытого профиля компонента Database Mail.**</span><span class="sxs-lookup"><span data-stu-id="8560e-124">**To configure a Database Mail private profile:**</span></span>  
  
    -   <span data-ttu-id="8560e-125">Откройте мастер настройки компонента Database Mail.</span><span class="sxs-lookup"><span data-stu-id="8560e-125">Open the Database Mail Configuration Wizard.</span></span>  
  
    -   <span data-ttu-id="8560e-126">На странице **Выбор задачи настройки** выберите **Управление учетными записями и профилями компонента Database Mail** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8560e-126">On the **Select Configuration Task** page, select **Manage Database Mail accounts and profiles** option, and click **Next**.</span></span>  
  
    -   <span data-ttu-id="8560e-127">На странице **Управление учетными записями и профилями** выберите **Управление безопасностью профилей** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8560e-127">On the **Manage Profiles and Accounts** page, select **Manage profile security** option and click **Next**.</span></span>  
  
    -   <span data-ttu-id="8560e-128">На вкладке **Закрытые профили** установите флажок для профиля, который необходимо настроить, и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8560e-128">In the **Private Profiles** tab, select the check box for the profile you would like to configure and click **Next**.</span></span>  
  
    -   <span data-ttu-id="8560e-129">На странице **Завершение работы мастера** просмотрите действия, которые необходимо выполнить, и нажмите кнопку **Готово** , чтобы завершить настройку профиля.</span><span class="sxs-lookup"><span data-stu-id="8560e-129">On the **Complete the Wizard** page, review the actions to be performed and click **Finish** to complete configuring the profile.</span></span>  
  
-   <span data-ttu-id="8560e-130">**Настройка открытого профиля компонента Database Mail.**</span><span class="sxs-lookup"><span data-stu-id="8560e-130">**To configure a Database Mail public profile:**</span></span>  
  
    -   <span data-ttu-id="8560e-131">Откройте мастер настройки компонента Database Mail.</span><span class="sxs-lookup"><span data-stu-id="8560e-131">Open the Database Mail Configuration Wizard.</span></span>  
  
    -   <span data-ttu-id="8560e-132">На странице **Выбор задачи настройки** выберите **Управление учетными записями и профилями компонента Database Mail** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8560e-132">On the **Select Configuration Task** page, select **Manage Database Mail accounts and profiles** option, and click **Next**.</span></span>  
  
    -   <span data-ttu-id="8560e-133">На странице **Управление учетными записями и профилями** выберите **Управление безопасностью профилей** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8560e-133">On the **Manage Profiles and Accounts** page, select **Manage profile security** option and click **Next**.</span></span>  
  
    -   <span data-ttu-id="8560e-134">На вкладке **Открытые профили** установите флажок для профиля, который необходимо настроить, и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8560e-134">In the **Public Profiles** tab, select the check box for the profile you would like to configure and click **Next**.</span></span>  
  
    -   <span data-ttu-id="8560e-135">На странице **Завершение работы мастера** просмотрите действия, которые необходимо выполнить, и нажмите кнопку **Готово** , чтобы завершить настройку профиля.</span><span class="sxs-lookup"><span data-stu-id="8560e-135">On the **Complete the Wizard** page, review the actions to be performed and click **Finish** to complete configuring the profile.</span></span>  
  

  
## <a name="using-transact-sql"></a><span data-ttu-id="8560e-136">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8560e-136">Using Transact-SQL</span></span>  
  
###  <a name="to-create-a-database-mail-private-profile"></a><a name="PrivateProfile"></a><span data-ttu-id="8560e-137">Создание Database Mail личного профиля</span><span class="sxs-lookup"><span data-stu-id="8560e-137">To Create a Database Mail private profile</span></span>  
  
-   <span data-ttu-id="8560e-138">Подключитесь к экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8560e-138">Connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
-   <span data-ttu-id="8560e-139">Чтобы создать новый профиль, выполните системную хранимую процедуру [sysmail_add_profile_sp (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sysmail-add-profile-sp-transact-sql) следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8560e-139">To create a new profile, run the system stored procedure [sysmail_add_profile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profile-sp-transact-sql) as follows:</span></span>  
  
     <span data-ttu-id="8560e-140">**EXECUTEmsdb.dbo.sysmail_add_profile_sp**</span><span class="sxs-lookup"><span data-stu-id="8560e-140">**EXECUTEmsdb.dbo.sysmail_add_profile_sp**</span></span>  
  
     <span data-ttu-id="8560e-141">*@profile_name*= '*Имя профиля*'</span><span class="sxs-lookup"><span data-stu-id="8560e-141">*@profile_name* = '*Profile Name*'</span></span>  
  
     <span data-ttu-id="8560e-142">*@description*= '*Описание*'</span><span class="sxs-lookup"><span data-stu-id="8560e-142">*@description* = '*Desciption*'</span></span>  
  
     <span data-ttu-id="8560e-143">где *@profile_name* — имя профиля, а *@description* — Описание профиля.</span><span class="sxs-lookup"><span data-stu-id="8560e-143">where *@profile_name* is the name of the profile, and *@description* is the description of the profile.</span></span> <span data-ttu-id="8560e-144">Это необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="8560e-144">This parameter is optional.</span></span>  
  
-   <span data-ttu-id="8560e-145">Для каждой учетной записи выполните хранимую процедуру [sysmail_add_profileaccount_sp (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sysmail-add-profileaccount-sp-transact-sql), как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="8560e-145">For each account, run the stored procedure [sysmail_add_profileaccount_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profileaccount-sp-transact-sql) as follows:</span></span>  
  
     <span data-ttu-id="8560e-146">**EXECUTEmsdb.dbo.sysmail_add_profileaccount_sp**</span><span class="sxs-lookup"><span data-stu-id="8560e-146">**EXECUTEmsdb.dbo.sysmail_add_profileaccount_sp**</span></span>  
  
     <span data-ttu-id="8560e-147">*@profile_name*= '*Имя профиля*'</span><span class="sxs-lookup"><span data-stu-id="8560e-147">*@profile_name* = '*Name of the profile*'</span></span>  
  
     <span data-ttu-id="8560e-148">*@account_name*= '*Имя учетной записи*'</span><span class="sxs-lookup"><span data-stu-id="8560e-148">*@account_name* = '*Name of the account*'</span></span>  
  
     <span data-ttu-id="8560e-149">*@sequence_number*= '*порядковый номер учетной записи в профиле.*</span><span class="sxs-lookup"><span data-stu-id="8560e-149">*@sequence_number* = '*sequence number of the account within the profile.*</span></span> <span data-ttu-id="8560e-150">'</span><span class="sxs-lookup"><span data-stu-id="8560e-150">'</span></span>  
  
     <span data-ttu-id="8560e-151">где *@profile_name* — имя профиля, а *@account_name* — имя учетной записи, добавляемой в профиль, *@sequence_number* определяет порядок, в котором учетные записи используются в профиле.</span><span class="sxs-lookup"><span data-stu-id="8560e-151">where *@profile_name* is the name of the profile, and *@account_name* is the name of the account to add to the profile, *@sequence_number* determines the order in which the accounts are used in the profile.</span></span>  
  
-   <span data-ttu-id="8560e-152">Всем ролям или пользователям баз данных, отправляющим письма с использованием этого профиля, следует предоставить доступ к профилю.</span><span class="sxs-lookup"><span data-stu-id="8560e-152">For each database role or user that will send mail using this profile, grant access to the profile.</span></span> <span data-ttu-id="8560e-153">Для этого выполните хранимую процедуру [sysmail_add_principalprofile_sp (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sysmail-add-principalprofile-sp-transact-sql), как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="8560e-153">To do this, run the stored procedure [sysmail_add_principalprofile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-principalprofile-sp-transact-sql) as follows:</span></span>  
  
     <span data-ttu-id="8560e-154">**EXECUTEmsdb.sysmail_add_principalprofile_sp**</span><span class="sxs-lookup"><span data-stu-id="8560e-154">**EXECUTEmsdb.sysmail_add_principalprofile_sp**</span></span>  
  
     <span data-ttu-id="8560e-155">*@profile_name*= '*Имя профиля*'</span><span class="sxs-lookup"><span data-stu-id="8560e-155">*@profile_name* = '*Name of the profile*'</span></span>  
  
     <span data-ttu-id="8560e-156">*@ principal_name* = '*Имя пользователя или роли базы данных*'</span><span class="sxs-lookup"><span data-stu-id="8560e-156">*@ principal_name* = '*Name of the database user or role*'</span></span>  
  
     <span data-ttu-id="8560e-157">*@is_default*= '*Состояние профиля по умолчанию* '</span><span class="sxs-lookup"><span data-stu-id="8560e-157">*@is_default* = '*Default Profile status* '</span></span>  
  
     <span data-ttu-id="8560e-158">где *@profile_name* — имя профиля, а *@principal_name* — имя пользователя или роли базы данных, *@is_default* определяет, является ли этот профиль значением по умолчанию для пользователя или роли базы данных.</span><span class="sxs-lookup"><span data-stu-id="8560e-158">where *@profile_name* is the name of the profile, and *@principal_name* is the name of the database user or role, *@is_default* determines the whether this profile is the default for the database user or role.</span></span>  
  
 <span data-ttu-id="8560e-159">В следующем примере создается учетная запись компонента Database Mail, создается закрытый профиль компонента Database Mail, затем учетная запись добавляется к профилю и предоставляется доступ к профилю для роли базы данных **DBMailUsers** в базе данных **msdb** .</span><span class="sxs-lookup"><span data-stu-id="8560e-159">The following example creates a Database Mail account, creates a Database Mail private profile, then adds the account to the profile and grants access to the profile to the **DBMailUsers** database role in the **msdb** database.</span></span>  
  
```  
-- Create a Database Mail account  
EXECUTE msdb.dbo.sysmail_add_account_sp  
    @account_name = 'AdventureWorks Administrator',  
    @description = 'Mail account for administrative e-mail.',  
    @email_address = 'dba@Adventure-Works.com',  
    @replyto_address = 'danw@Adventure-Works.com',  
    @display_name = 'AdventureWorks Automated Mailer',  
    @mailserver_name = 'smtp.Adventure-Works.com' ;  
  
-- Create a Database Mail profile  
EXECUTE msdb.dbo.sysmail_add_profile_sp  
    @profile_name = 'AdventureWorks Administrator Profile',  
    @description = 'Profile used for administrative mail.' ;  
  
-- Add the account to the profile  
EXECUTE msdb.dbo.sysmail_add_profileaccount_sp  
    @profile_name = 'AdventureWorks Administrator Profile',  
    @account_name = 'AdventureWorks Administrator',  
    @sequence_number =1 ;  
  
-- Grant access to the profile to the DBMailUsers role  
EXECUTE msdb.dbo.sysmail_add_principalprofile_sp  
    @profile_name = 'AdventureWorks Administrator Profile',  
    @principal_name = 'ApplicationUser',  
    @is_default = 1 ;  
```  
  
 
  
###  <a name="to-create-a-database-mail-public-profile"></a><a name="PublicProfile"></a><span data-ttu-id="8560e-160">Создание Database Mail общего профиля</span><span class="sxs-lookup"><span data-stu-id="8560e-160">To Create a Database Mail public profile</span></span>  
  
-   <span data-ttu-id="8560e-161">Подключитесь к экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8560e-161">Connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
-   <span data-ttu-id="8560e-162">Чтобы создать новый профиль, выполните системную хранимую процедуру [sysmail_add_profile_sp (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sysmail-add-profile-sp-transact-sql) следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8560e-162">To create a new profile, run the system stored procedure [sysmail_add_profile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profile-sp-transact-sql) as follows:</span></span>  
  
     <span data-ttu-id="8560e-163">**EXECUTEmsdb.dbo.sysmail_add_profile_sp**</span><span class="sxs-lookup"><span data-stu-id="8560e-163">**EXECUTEmsdb.dbo.sysmail_add_profile_sp**</span></span>  
  
     <span data-ttu-id="8560e-164">*@profile_name*= '*Имя профиля*'</span><span class="sxs-lookup"><span data-stu-id="8560e-164">*@profile_name* = '*Profile Name*'</span></span>  
  
     <span data-ttu-id="8560e-165">*@description*= '*Описание*'</span><span class="sxs-lookup"><span data-stu-id="8560e-165">*@description* = '*Desciption*'</span></span>  
  
     <span data-ttu-id="8560e-166">где *@profile_name* — имя профиля, а *@description* — Описание профиля.</span><span class="sxs-lookup"><span data-stu-id="8560e-166">where *@profile_name* is the name of the profile, and *@description* is the description of the profile.</span></span> <span data-ttu-id="8560e-167">Это необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="8560e-167">This parameter is optional.</span></span>  
  
-   <span data-ttu-id="8560e-168">Для каждой учетной записи выполните хранимую процедуру [sysmail_add_profileaccount_sp (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sysmail-add-profileaccount-sp-transact-sql), как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="8560e-168">For each account, run the stored procedure [sysmail_add_profileaccount_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profileaccount-sp-transact-sql) as follows:</span></span>  
  
     <span data-ttu-id="8560e-169">**EXECUTEmsdb.dbo.sysmail_add_profileaccount_sp**</span><span class="sxs-lookup"><span data-stu-id="8560e-169">**EXECUTEmsdb.dbo.sysmail_add_profileaccount_sp**</span></span>  
  
     <span data-ttu-id="8560e-170">*@profile_name*= '*Имя профиля*'</span><span class="sxs-lookup"><span data-stu-id="8560e-170">*@profile_name* = '*Name of the profile*'</span></span>  
  
     <span data-ttu-id="8560e-171">*@account_name*= '*Имя учетной записи*'</span><span class="sxs-lookup"><span data-stu-id="8560e-171">*@account_name* = '*Name of the account*'</span></span>  
  
     <span data-ttu-id="8560e-172">*@sequence_number*= '*порядковый номер учетной записи в профиле.*</span><span class="sxs-lookup"><span data-stu-id="8560e-172">*@sequence_number* = '*sequence number of the account within the profile.*</span></span> <span data-ttu-id="8560e-173">'</span><span class="sxs-lookup"><span data-stu-id="8560e-173">'</span></span>  
  
     <span data-ttu-id="8560e-174">где *@profile_name* — имя профиля, а *@account_name* — имя учетной записи, добавляемой в профиль, *@sequence_number* определяет порядок, в котором учетные записи используются в профиле.</span><span class="sxs-lookup"><span data-stu-id="8560e-174">where *@profile_name* is the name of the profile, and *@account_name* is the name of the account to add to the profile, *@sequence_number* determines the order in which the accounts are used in the profile.</span></span>  
  
-   <span data-ttu-id="8560e-175">Чтобы предоставить открытый доступ, выполните хранимую процедуру [sysmail_add_principalprofile_sp (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sysmail-add-principalprofile-sp-transact-sql), как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="8560e-175">To grant public access, run the stored procedure [sysmail_add_principalprofile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-principalprofile-sp-transact-sql) as follows:</span></span>  
  
     <span data-ttu-id="8560e-176">**EXECUTEmsdb.sysmail_add_principalprofile_sp**</span><span class="sxs-lookup"><span data-stu-id="8560e-176">**EXECUTEmsdb.sysmail_add_principalprofile_sp**</span></span>  
  
     <span data-ttu-id="8560e-177">*@profile_name*= '*Имя профиля*'</span><span class="sxs-lookup"><span data-stu-id="8560e-177">*@profile_name* = '*Name of the profile*'</span></span>  
  
     <span data-ttu-id="8560e-178">*@ principal_name* = '**открытый** или **0**'</span><span class="sxs-lookup"><span data-stu-id="8560e-178">*@ principal_name* = '**public** or **0**'</span></span>  
  
     <span data-ttu-id="8560e-179">*@is_default*= '*Состояние профиля по умолчанию* '</span><span class="sxs-lookup"><span data-stu-id="8560e-179">*@is_default* = '*Default Profile status* '</span></span>  
  
     <span data-ttu-id="8560e-180">где *@profile_name* — имя профиля, а чтобы указать, что это *@principal_name* открытый профиль, *@is_default* определяет, является ли этот профиль значением по умолчанию для пользователя или роли базы данных.</span><span class="sxs-lookup"><span data-stu-id="8560e-180">where *@profile_name* is the name of the profile, and *@principal_name* to indicate this is a public profile, *@is_default* determines the whether this profile is the default for the database user or role.</span></span>  
  
 <span data-ttu-id="8560e-181">В следующем примере создается учетная запись компонента Database Mail, создается закрытый профиль компонента Database Mail, затем учетная запись добавляется к профилю и предоставляется общий доступ к профилю.</span><span class="sxs-lookup"><span data-stu-id="8560e-181">The following example creates a Database Mail account, creates a Database Mail private profile, then adds the account to the profile and grants public access to the profile.</span></span>  
  
```  
-- Create a Database Mail account  
  
EXECUTE msdb.dbo.sysmail_add_account_sp  
    @account_name = 'AdventureWorks Public Account',  
    @description = 'Mail account for use by all database users.',  
    @email_address = 'db_users@Adventure-Works.com',  
    @replyto_address = 'danw@Adventure-Works.com',  
    @display_name = 'AdventureWorks Automated Mailer',  
    @mailserver_name = 'smtp.Adventure-Works.com' ;  
  
-- Create a Database Mail profile  
  
EXECUTE msdb.dbo.sysmail_add_profile_sp  
    @profile_name = 'AdventureWorks Public Profile',  
    @description = 'Profile used for administrative mail.' ;  
  
-- Add the account to the profile  
  
EXECUTE msdb.dbo.sysmail_add_profileaccount_sp  
    @profile_name = 'AdventureWorks Public Profile',  
    @account_name = 'AdventureWorks Public Account',  
    @sequence_number =1 ;  
  
-- Grant access to the profile to all users in the msdb database  
  
EXECUTE msdb.dbo.sysmail_add_principalprofile_sp  
    @profile_name = 'AdventureWorks Public Profile',  
    @principal_name = 'public',  
    @is_default = 1 ;  
```  
  

  
  
