---
title: Просмотр и изменение свойств издателя и распространителя | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- viewing replication properties
- Distributors [SQL Server replication], modifying
- modifying replication properties, Distributors
- Distributors [SQL Server replication], properties
ms.assetid: 5dae1d59-c377-4c6e-adc9-b68c5b328f79
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 571f6f3a0d44f0fc87c67885249fca441776946d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657633"
---
# <a name="view-and-modify-distributor-and-publisher-properties"></a><span data-ttu-id="41346-102">Просмотр и изменение свойств издателя и распространителя</span><span class="sxs-lookup"><span data-stu-id="41346-102">View and Modify Distributor and Publisher Properties</span></span>
  <span data-ttu-id="41346-103">В данном разделе описывается просмотр и изменение свойств распространителя и издателя в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] при помощи среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]или объектов RMO.</span><span class="sxs-lookup"><span data-stu-id="41346-103">This topic describes how to view and modify Distributor and Publisher properties in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span>  
  
 <span data-ttu-id="41346-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="41346-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="41346-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="41346-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="41346-106">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="41346-106">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="41346-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="41346-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="41346-108">**Для просмотра и изменения свойств распространителя и издателя используется:**</span><span class="sxs-lookup"><span data-stu-id="41346-108">**To view and modify Distributor and Publisher properties, using:**</span></span>  
  
     [<span data-ttu-id="41346-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="41346-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="41346-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="41346-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="41346-111">объекты RMO;</span><span class="sxs-lookup"><span data-stu-id="41346-111">Replication Management Objects (RMO)</span></span>](#RMOProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="41346-112">Перед началом</span><span class="sxs-lookup"><span data-stu-id="41346-112">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="41346-113">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="41346-113">Recommendations</span></span>  
  
-   <span data-ttu-id="41346-114">Для издателей, которые используют версии, предшествующие [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], пользователь, являющийся членом предопределенной роли сервера **sysadmin**, может зарегистрировать подписчиков на странице **Подписчики**.</span><span class="sxs-lookup"><span data-stu-id="41346-114">For Publishers running versions prior to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], a user in the **sysadmin** fixed server role can register Subscribers on the **Subscribers** page.</span></span> <span data-ttu-id="41346-115">Начиная с [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]больше нет необходимости в явной регистрации подписчиков для репликации.</span><span class="sxs-lookup"><span data-stu-id="41346-115">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], it is no longer necessary to explicitly register Subscribers for replication.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="41346-116">безопасность</span><span class="sxs-lookup"><span data-stu-id="41346-116">Security</span></span>  
 <span data-ttu-id="41346-117">По возможности предлагайте пользователям вводить учетные данные системы безопасности во время выполнения приложения.</span><span class="sxs-lookup"><span data-stu-id="41346-117">When possible, prompt users to enter security credentials at runtime.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="41346-118">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="41346-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-and-modify-distributor-properties"></a><span data-ttu-id="41346-119">Просмотр и изменение свойств распространителя</span><span class="sxs-lookup"><span data-stu-id="41346-119">To view and modify Distributor properties</span></span>  
  
1.  <span data-ttu-id="41346-120">Подключитесь к распространителю в [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]и разверните узел сервера.</span><span class="sxs-lookup"><span data-stu-id="41346-120">Connect to the Distributor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="41346-121">Щелкните правой кнопкой папку **Репликация** , затем щелкните **Свойства распространителя**.</span><span class="sxs-lookup"><span data-stu-id="41346-121">Right-click the **Replication** folder, and then click **Distributor Properties**.</span></span>  
  
3.  <span data-ttu-id="41346-122">Просмотрите и измените свойства в диалоговом окне **Свойства распространителя — \<Distributor>** .</span><span class="sxs-lookup"><span data-stu-id="41346-122">View and modify properties in the **Distributor Properties - \<Distributor>** dialog box.</span></span>  
  
    -   <span data-ttu-id="41346-123">Для просмотра и изменения свойств базы данных распространителя нажмите кнопку с многоточием ( **...** ) базы данных на вкладке **Общие** диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="41346-123">To view and modify properties for a distribution database, click the properties button (**...**) for the database on the **General** page of thedialog box.</span></span>  
  
    -   <span data-ttu-id="41346-124">Для просмотра и изменения свойств издателя, связанного с распространителем, нажмите кнопку с многоточием ( **...** ) издателя на вкладке **Издатели** диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="41346-124">To view and modify Publisher properties associated with the Distributor, click the properties button (**...**) for the Publisher on the **Publishers** page of the dialog box.</span></span>  
  
    -   <span data-ttu-id="41346-125">Для доступа к профилям агентов репликации нажмите кнопку **Значения по умолчанию для профилей** на странице **Общие** диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="41346-125">To access profiles for replication agents, click the **Profile Defaults** button on the **General** page of the dialog box.</span></span> <span data-ttu-id="41346-126">Дополнительные сведения см. в статье [Replication Agent Profiles](agents/replication-agent-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="41346-126">For more information, see [Replication Agent Profiles](agents/replication-agent-profiles.md).</span></span>  
  
    -   <span data-ttu-id="41346-127">Для изменения пароля учетной записи, используемой при выполнении административных хранимых процедур на издателе и обновлении данных на распространителе, введите новый пароль в поля **Пароль** и **Подтверждение пароля** на странице **Издатели** диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="41346-127">To change the password for the account used when administrative stored procedures execute at the Publisher and update information at the Distributor, enter a new password in the **Password** and **Confirm password** boxes on the **Publishers** page of the dialog box.</span></span> <span data-ttu-id="41346-128">Дополнительные сведения см. в разделе [Организация безопасности распространителя](security/secure-the-distributor.md).</span><span class="sxs-lookup"><span data-stu-id="41346-128">For more information, see [Secure the Distributor](security/secure-the-distributor.md).</span></span>  
  
4.  <span data-ttu-id="41346-129">Измените свойства, если необходимо, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="41346-129">Modify any properties if necessary, and then click **OK**.</span></span>  
  
#### <a name="to-view-and-modify-publisher-properties"></a><span data-ttu-id="41346-130">Просмотр и изменение свойств издателя</span><span class="sxs-lookup"><span data-stu-id="41346-130">To view and modify Publisher properties</span></span>  
  
1.  <span data-ttu-id="41346-131">Подключитесь к издателю в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], а затем раскройте узел сервера.</span><span class="sxs-lookup"><span data-stu-id="41346-131">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="41346-132">Правой кнопкой мыши щелкните папку **Репликация** , а затем выберите пункт **Свойства издателя**.</span><span class="sxs-lookup"><span data-stu-id="41346-132">Right-click the **Replication** folder, and then click **Publisher Properties**.</span></span>  
  
3.  <span data-ttu-id="41346-133">Просмотр и изменение свойств в диалоговом окне **свойства \< Publisher > издателя —** .</span><span class="sxs-lookup"><span data-stu-id="41346-133">View and modify properties in the **Publisher Properties - \< Publisher >** dialog box.</span></span>  
  
    -   <span data-ttu-id="41346-134">Пользователь, являющийся членом предопределенной роли сервера **sysadmin** , может разрешить применение репликации для баз данных, выполнив настройки на странице **Базы данных публикации** .</span><span class="sxs-lookup"><span data-stu-id="41346-134">A user in the **sysadmin** fixed server role can enable databases for replication on the **Publication Databases** page.</span></span> <span data-ttu-id="41346-135">Разрешение репликации для базы данных не вызывает ее публикации. Вместо этого оно позволяет любому пользователю, принадлежащему к предопределенной роли базы данных **db_owner** для этой базы данных, создавать в ней одну или несколько публикаций.</span><span class="sxs-lookup"><span data-stu-id="41346-135">Enabling a database does not publish that database; rather, it allows any user in the **db_owner** fixed database role for that database to create one or more publications in the database.</span></span>  
  
4.  <span data-ttu-id="41346-136">Измените свойства, если необходимо, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="41346-136">Modify any properties if necessary, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="41346-137">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="41346-137">Using Transact-SQL</span></span>  
 <span data-ttu-id="41346-138">Свойства издателя и распространителя можно просмотреть программно с помощью хранимых процедур репликации.</span><span class="sxs-lookup"><span data-stu-id="41346-138">Publisher and Distributor properties can be viewed programmatically using replication stored procedures.</span></span>  
  
#### <a name="to-view-distributor-and-distribution-database-properties"></a><span data-ttu-id="41346-139">Просмотр свойств распространителя и базы данных распространителя</span><span class="sxs-lookup"><span data-stu-id="41346-139">To view Distributor and distribution database properties</span></span>  
  
1.  <span data-ttu-id="41346-140">Выполните хранимую процедуру [sp_helpdistributor](/sql/relational-databases/system-stored-procedures/sp-helpdistributor-transact-sql) , которая возвращает сведения о распространителе, базе данных распространителя и рабочем каталоге.</span><span class="sxs-lookup"><span data-stu-id="41346-140">Execute [sp_helpdistributor](/sql/relational-databases/system-stored-procedures/sp-helpdistributor-transact-sql) to return information about the Distributor, distribution database, and working directory.</span></span>  
  
2.  <span data-ttu-id="41346-141">Выполните хранимую процедуру [sp_helpdistributiondb](/sql/relational-databases/system-stored-procedures/sp-helpdistributiondb-transact-sql) , которая возвращает свойства заданной базы данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="41346-141">Execute [sp_helpdistributiondb](/sql/relational-databases/system-stored-procedures/sp-helpdistributiondb-transact-sql) to return properties of a specified distribution database.</span></span>  
  
#### <a name="to-change-distributor-and-distribution-database-properties"></a><span data-ttu-id="41346-142">Изменение свойств распространителя и базы данных распространителя</span><span class="sxs-lookup"><span data-stu-id="41346-142">To change Distributor and distribution database properties</span></span>  
  
1.  <span data-ttu-id="41346-143">Чтобы изменить свойства распространителя, выполните на распространителе хранимую процедуру [sp_changedistributor_property](/sql/relational-databases/system-stored-procedures/sp-changedistributor-property-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="41346-143">At the Distributor, execute [sp_changedistributor_property](/sql/relational-databases/system-stored-procedures/sp-changedistributor-property-transact-sql) to modify Distributor properties.</span></span>  
  
2.  <span data-ttu-id="41346-144">Чтобы изменить свойства базы данных распространителя, выполните на распространителе хранимую процедуру [sp_changedistributiondb](/sql/relational-databases/system-stored-procedures/sp-changedistributiondb-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="41346-144">At the Distributor, execute [sp_changedistributiondb](/sql/relational-databases/system-stored-procedures/sp-changedistributiondb-transact-sql) to modify distribution database properties.</span></span>  
  
3.  <span data-ttu-id="41346-145">Чтобы изменить пароль распространителя, выполните на распространителе хранимую процедуру [sp_changedistributor_password](/sql/relational-databases/system-stored-procedures/sp-changedistributor-password-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="41346-145">At the Distributor, execute [sp_changedistributor_password](/sql/relational-databases/system-stored-procedures/sp-changedistributor-password-transact-sql) to change the Distributor password.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="41346-146">По возможности предлагайте пользователям вводить учетные данные системы безопасности во время выполнения приложения.</span><span class="sxs-lookup"><span data-stu-id="41346-146">When possible, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="41346-147">Если нужно хранить учетные данные в файле скрипта, для этого файла необходимо обеспечить защиту, чтобы исключить несанкционированный доступ.</span><span class="sxs-lookup"><span data-stu-id="41346-147">If you must store credentials in a script file, secure the file to prevent unauthorized access.</span></span>  
  
4.  <span data-ttu-id="41346-148">Чтобы изменить свойства издателя с помощью распространителя, выполните на распространителе хранимую процедуру [sp_changedistpublisher](/sql/relational-databases/system-stored-procedures/sp-changedistpublisher-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="41346-148">At the Distributor, execute [sp_changedistpublisher](/sql/relational-databases/system-stored-procedures/sp-changedistpublisher-transact-sql) to change the properties of a Publisher using the Distributor.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="41346-149">Примеры (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="41346-149">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="41346-150">В следующем примере скрипт [!INCLUDE[tsql](../../includes/tsql-md.md)] возвращает сведения о распространителе и базе данных распространителя.</span><span class="sxs-lookup"><span data-stu-id="41346-150">The following example [!INCLUDE[tsql](../../includes/tsql-md.md)] script returns information about the Distributor and distribution database.</span></span>  
  
 [!code-sql[HowTo#sp_helpdistributor](../../snippets/tsql/SQL15/replication/howto/tsql/changedistpub.sql#sp_helpdistributor)]  
  
 [!code-sql[HowTo#sp_helpdistributiondb](../../snippets/tsql/SQL15/replication/howto/tsql/changedistpub.sql#sp_helpdistributiondb)]  
  
 <span data-ttu-id="41346-151">В этом примере изменяются сроки хранения для распространителя, пароль соединения с распространителем и интервал, с которым распространитель проверяет состояние различных агентов репликации (интервал тактового импульса).</span><span class="sxs-lookup"><span data-stu-id="41346-151">This example changes retention periods for the Distributor, the password used when connecting to the Distributor, and the interval at which the Distributor checks the status of various replication agents (also known as the heartbeat interval).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="41346-152">По возможности предлагайте пользователям вводить учетные данные системы безопасности во время выполнения приложения.</span><span class="sxs-lookup"><span data-stu-id="41346-152">When possible, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="41346-153">Если нужно хранить учетные данные в файле скрипта, для этого файла необходимо обеспечить защиту, чтобы исключить несанкционированный доступ.</span><span class="sxs-lookup"><span data-stu-id="41346-153">If you must store credentials in a script file, secure the file to prevent unauthorized access.</span></span>  
  
 [!code-sql[HowTo#sp_changedistributor_property](../../snippets/tsql/SQL15/replication/howto/tsql/changedistpub.sql#sp_changedistributor_property)]  
  
 [!code-sql[HowTo#sp_changedistributiondb](../../snippets/tsql/SQL15/replication/howto/tsql/changedistpub.sql#sp_changedistributiondb)]  
  
 [!code-sql[HowTo#sp_changedistributor_password](../../snippets/tsql/SQL15/replication/howto/tsql/changedistpub.sql#sp_changedistributor_password)]  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="41346-154">При помощи объектов RMO</span><span class="sxs-lookup"><span data-stu-id="41346-154">Using Replication Management Objects (RMO)</span></span>  
  
#### <a name="to-view-and-modify-distributor-properties"></a><span data-ttu-id="41346-155">Просмотр и изменение свойств распространителя</span><span class="sxs-lookup"><span data-stu-id="41346-155">To view and modify Distributor properties</span></span>  
  
1.  <span data-ttu-id="41346-156">Создайте соединение с распространителем с помощью класса <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="41346-156">Create a connection to the Distributor by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="41346-157">Создайте экземпляр класса <xref:Microsoft.SqlServer.Replication.ReplicationServer>.</span><span class="sxs-lookup"><span data-stu-id="41346-157">Create an instance of the <xref:Microsoft.SqlServer.Replication.ReplicationServer> class.</span></span> <span data-ttu-id="41346-158">Передайте объект <xref:Microsoft.SqlServer.Management.Common.ServerConnection> , созданный на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="41346-158">Pass the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object from step 1.</span></span>  
  
3.  <span data-ttu-id="41346-159">(Необязательно) Проверьте свойство <xref:Microsoft.SqlServer.Replication.ReplicationServer.IsDistributor%2A> , чтобы убедиться, что подключенный в настоящее время сервер является распространителем.</span><span class="sxs-lookup"><span data-stu-id="41346-159">(Optional) Check the <xref:Microsoft.SqlServer.Replication.ReplicationServer.IsDistributor%2A> property to verify that the currently connected server is a Distributor.</span></span>  
  
4.  <span data-ttu-id="41346-160">Чтобы получить свойства с сервера, необходимо вызвать метод <xref:Microsoft.SqlServer.Replication.ReplicationObject.Load%2A> .</span><span class="sxs-lookup"><span data-stu-id="41346-160">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.Load%2A> method to get the properties from the server.</span></span>  
  
5.  <span data-ttu-id="41346-161">(Необязательно) Чтобы изменить свойства, укажите новое значение для одного или нескольких свойств распространителя, которые могут принимать значение <xref:Microsoft.SqlServer.Replication.ReplicationServer> .</span><span class="sxs-lookup"><span data-stu-id="41346-161">(Optional) To change properties, set a new value for one or more of the Distributor properties that can be set on the <xref:Microsoft.SqlServer.Replication.ReplicationServer> object.</span></span>  
  
6.  <span data-ttu-id="41346-162">Если свойство <xref:Microsoft.SqlServer.Replication.ReplicationObject.CachePropertyChanges%2A> объекта <xref:Microsoft.SqlServer.Replication.ReplicationServer> имеет значение `true`, для фиксирования изменений на сервере необходимо вызвать метод <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> (необязательно).</span><span class="sxs-lookup"><span data-stu-id="41346-162">(Optional) If the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CachePropertyChanges%2A> property on the <xref:Microsoft.SqlServer.Replication.ReplicationServer> object is set to `true`, call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method to commit the changes to the server.</span></span>  
  
#### <a name="to-view-and-modify-distribution-database-properties"></a><span data-ttu-id="41346-163">Просмотр и изменение свойств базы данных-распространителя</span><span class="sxs-lookup"><span data-stu-id="41346-163">To view and modify distribution database properties</span></span>  
  
1.  <span data-ttu-id="41346-164">Создайте соединение с распространителем с помощью класса <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="41346-164">Create a connection to the Distributor by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="41346-165">Создайте экземпляр класса <xref:Microsoft.SqlServer.Replication.DistributionDatabase>.</span><span class="sxs-lookup"><span data-stu-id="41346-165">Create an instance of the <xref:Microsoft.SqlServer.Replication.DistributionDatabase> class.</span></span> <span data-ttu-id="41346-166">Укажите свойство Name и передайте объект <xref:Microsoft.SqlServer.Management.Common.ServerConnection> из шага 1.</span><span class="sxs-lookup"><span data-stu-id="41346-166">Specify the name property and pass the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object from step 1.</span></span>  
  
3.  <span data-ttu-id="41346-167">Чтобы получить свойства с сервера, необходимо вызвать метод <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> .</span><span class="sxs-lookup"><span data-stu-id="41346-167">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the properties from the server.</span></span> <span data-ttu-id="41346-168">Если этот метод вернет значение `false`, значит, на сервере не существует базы данных с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="41346-168">If this method returns `false`, the database with the specified name does not exist on the server.</span></span>  
  
4.  <span data-ttu-id="41346-169">Чтобы изменить свойства, установите новое значение для одного из свойств <xref:Microsoft.SqlServer.Replication.DistributionDatabase> , которое можно установить (необязательно).</span><span class="sxs-lookup"><span data-stu-id="41346-169">(Optional) To change properties, set a new value for one of the <xref:Microsoft.SqlServer.Replication.DistributionDatabase> properties that can be set.</span></span>  
  
5.  <span data-ttu-id="41346-170">Если свойство <xref:Microsoft.SqlServer.Replication.ReplicationObject.CachePropertyChanges%2A> объекта <xref:Microsoft.SqlServer.Replication.DistributionDatabase> имеет значение `true`, для фиксирования изменений на сервере необходимо вызвать метод <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> (необязательно).</span><span class="sxs-lookup"><span data-stu-id="41346-170">(Optional) If the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CachePropertyChanges%2A> property on the <xref:Microsoft.SqlServer.Replication.DistributionDatabase> object is set to `true`, call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method to commit the changes to the server.</span></span>  
  
#### <a name="to-view-and-modify-publisher-properties"></a><span data-ttu-id="41346-171">Просмотр и изменение свойств издателя</span><span class="sxs-lookup"><span data-stu-id="41346-171">To view and modify Publisher properties</span></span>  
  
1.  <span data-ttu-id="41346-172">Создайте соединение с издателем с помощью класса <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="41346-172">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="41346-173">Создайте экземпляр класса <xref:Microsoft.SqlServer.Replication.DistributionPublisher>.</span><span class="sxs-lookup"><span data-stu-id="41346-173">Create an instance of the <xref:Microsoft.SqlServer.Replication.DistributionPublisher> class.</span></span> <span data-ttu-id="41346-174">Укажите свойство <xref:Microsoft.SqlServer.Replication.DistributionPublisher.Name%2A> и передайте объект <xref:Microsoft.SqlServer.Management.Common.ServerConnection> из шага 1.</span><span class="sxs-lookup"><span data-stu-id="41346-174">Specify the <xref:Microsoft.SqlServer.Replication.DistributionPublisher.Name%2A> property and pass the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object from step 1.</span></span>  
  
3.  <span data-ttu-id="41346-175">Чтобы изменить свойства, установите новое значение для одного из свойств <xref:Microsoft.SqlServer.Replication.DistributionPublisher> , которое можно установить (необязательно).</span><span class="sxs-lookup"><span data-stu-id="41346-175">(Optional) To change properties, set a new value for one of the <xref:Microsoft.SqlServer.Replication.DistributionPublisher> properties that can be set.</span></span>  
  
4.  <span data-ttu-id="41346-176">Если свойство <xref:Microsoft.SqlServer.Replication.ReplicationObject.CachePropertyChanges%2A> объекта <xref:Microsoft.SqlServer.Replication.DistributionPublisher> имеет значение `true`, для фиксирования изменений на сервере необходимо вызвать метод <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> (необязательно).</span><span class="sxs-lookup"><span data-stu-id="41346-176">(Optional) If the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CachePropertyChanges%2A> property on the <xref:Microsoft.SqlServer.Replication.DistributionPublisher> object is set to `true`, call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method to commit the changes to the server.</span></span>  
  
#### <a name="to-change-the-password-for-the-administrative-connection-from-the-publisher-to-the-distributor"></a><span data-ttu-id="41346-177">Изменение пароля для административного соединения между издателем и распространителем</span><span class="sxs-lookup"><span data-stu-id="41346-177">To change the password for the administrative connection from the Publisher to the Distributor</span></span>  
  
1.  <span data-ttu-id="41346-178">Создайте соединение с распространителем с помощью класса <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="41346-178">Create a connection to the Distributor by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="41346-179">Создайте экземпляр класса <xref:Microsoft.SqlServer.Replication.ReplicationServer>.</span><span class="sxs-lookup"><span data-stu-id="41346-179">Create an instance of the <xref:Microsoft.SqlServer.Replication.ReplicationServer> class.</span></span>  
  
3.  <span data-ttu-id="41346-180">В свойстве <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> укажите созданное на шаге 1 соединение.</span><span class="sxs-lookup"><span data-stu-id="41346-180">Set the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property to the connection created in step 1.</span></span>  
  
4.  <span data-ttu-id="41346-181">Чтобы получить свойства объекта, вызовите метод <xref:Microsoft.SqlServer.Replication.ReplicationObject.Load%2A> .</span><span class="sxs-lookup"><span data-stu-id="41346-181">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.Load%2A> method to get the properties of the object.</span></span>  
  
5.  <span data-ttu-id="41346-182">Вызовите метод <xref:Microsoft.SqlServer.Replication.ReplicationServer.ChangeDistributorPassword%2A> .</span><span class="sxs-lookup"><span data-stu-id="41346-182">Call the <xref:Microsoft.SqlServer.Replication.ReplicationServer.ChangeDistributorPassword%2A> method.</span></span> <span data-ttu-id="41346-183">Передайте новое значение пароля в параметре *password* .</span><span class="sxs-lookup"><span data-stu-id="41346-183">Pass the new password value for the *password* parameter.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="41346-184">По возможности предлагайте пользователям вводить учетные данные системы безопасности во время выполнения приложения.</span><span class="sxs-lookup"><span data-stu-id="41346-184">When possible, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="41346-185">Если необходимо хранить учетные данные, используйте [службы шифрования](https://go.microsoft.com/fwlink/?LinkId=34733) , предоставляемые платформой [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="41346-185">If you must store credentials, use the [cryptographic services](https://go.microsoft.com/fwlink/?LinkId=34733) provided by the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows .NET Framework.</span></span>  
  
6.  <span data-ttu-id="41346-186">(Необязательно) Выполните следующие шаги, чтобы изменить пароль на каждом удаленном издателе, использующем данный распространитель.</span><span class="sxs-lookup"><span data-stu-id="41346-186">(Optional) Perform the following steps to change the password at each remote Publisher that uses this Distributor:</span></span>  
  
    1.  <span data-ttu-id="41346-187">Создайте соединение с издателем с помощью класса <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="41346-187">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
    2.  <span data-ttu-id="41346-188">Создайте экземпляр класса <xref:Microsoft.SqlServer.Replication.ReplicationServer>.</span><span class="sxs-lookup"><span data-stu-id="41346-188">Create an instance of the <xref:Microsoft.SqlServer.Replication.ReplicationServer> class.</span></span>  
  
    3.  <span data-ttu-id="41346-189">Укажите в качестве свойства <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> соединение, созданное в шаге 6a.</span><span class="sxs-lookup"><span data-stu-id="41346-189">Set the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property to the connection created in step 6a.</span></span>  
  
    4.  <span data-ttu-id="41346-190">Чтобы получить свойства объекта, вызовите метод <xref:Microsoft.SqlServer.Replication.ReplicationObject.Load%2A> .</span><span class="sxs-lookup"><span data-stu-id="41346-190">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.Load%2A> method to get the properties of the object.</span></span>  
  
    5.  <span data-ttu-id="41346-191">Вызовите метод <xref:Microsoft.SqlServer.Replication.ReplicationServer.ChangeDistributorPassword%2A> .</span><span class="sxs-lookup"><span data-stu-id="41346-191">Call the <xref:Microsoft.SqlServer.Replication.ReplicationServer.ChangeDistributorPassword%2A> method.</span></span> <span data-ttu-id="41346-192">Передайте новое значение пароля из шага 5 в параметре *password* .</span><span class="sxs-lookup"><span data-stu-id="41346-192">Pass the new password value from Step 5 for the *password* parameter.</span></span>  
  
###  <a name="example-rmo"></a><a name="PShellExample"></a> <span data-ttu-id="41346-193">Пример (объекты RMO)</span><span class="sxs-lookup"><span data-stu-id="41346-193">Example (RMO)</span></span>  
 <span data-ttu-id="41346-194">В этом примере показано, как изменить свойства распространителя и базы данных-распространителя.</span><span class="sxs-lookup"><span data-stu-id="41346-194">This example shows how to change Distribution and distribution database properties.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="41346-195">Чтобы учетные данные не хранились в коде, новый пароль для распространителя указывается во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="41346-195">To avoid storing credentials in the code, the new Distributor password is supplied at runtime.</span></span>  
  
 [!code-csharp[HowTo#rmo_ChangeDistPub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_changedistpub)]  
  
 [!code-vb[HowTo#rmo_vb_ChangeDistPub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_changedistpub)]  
  
## <a name="see-also"></a><span data-ttu-id="41346-196">См. также:</span><span class="sxs-lookup"><span data-stu-id="41346-196">See Also</span></span>  
 <span data-ttu-id="41346-197">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="41346-197">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span></span>  
 <span data-ttu-id="41346-198">[Disable Publishing and Distribution](disable-publishing-and-distribution.md)  (Отключение публикации и распространения)</span><span class="sxs-lookup"><span data-stu-id="41346-198">[Disable Publishing and Distribution](disable-publishing-and-distribution.md) </span></span>  
 <span data-ttu-id="41346-199">[Настройка распространения](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="41346-199">[Configure Distribution](configure-distribution.md) </span></span>  
 <span data-ttu-id="41346-200">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="41346-200">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span></span>  
 <span data-ttu-id="41346-201">[Distributor and Publisher Information Script](administration/distributor-and-publisher-information-script.md)  (Скрипт вывода сведений о распространителе и издателе)</span><span class="sxs-lookup"><span data-stu-id="41346-201">[Distributor and Publisher Information Script](administration/distributor-and-publisher-information-script.md) </span></span>  
 <span data-ttu-id="41346-202">[Replication System Stored Procedures Concepts](concepts/replication-system-stored-procedures-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="41346-202">[Replication System Stored Procedures Concepts](concepts/replication-system-stored-procedures-concepts.md) </span></span>  
 [<span data-ttu-id="41346-203">Просмотр сведений и выполнение задач с помощью монитора репликации</span><span class="sxs-lookup"><span data-stu-id="41346-203">View Information and Perform Tasks using Replication Monitor</span></span>](monitor/view-information-and-perform-tasks-replication-monitor.md)  
  
  
