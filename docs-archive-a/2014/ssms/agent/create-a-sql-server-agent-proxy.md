---
title: Создание учетной записи-посредника агента SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- proxies [SQL Server Agent], creating
ms.assetid: 142e0c55-a8b9-4669-be49-b9dc602d5988
author: stevestein
ms.author: sstein
ms.openlocfilehash: a7582aef38d57b15de968d96357e56c1974d733e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666333"
---
# <a name="create-a-sql-server-agent-proxy"></a><span data-ttu-id="f2844-102">Создание учетной записи-посредника агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="f2844-102">Create a SQL Server Agent Proxy</span></span>
  <span data-ttu-id="f2844-103">В этом разделе описано, как создать учетную запись-посредник агента SQL Server в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2844-103">This topic describes how to create a SQL Server Agent proxy in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="f2844-104">Учетная запись-посредник агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] определяет контекст безопасности, в котором может выполняться шаг задания.</span><span class="sxs-lookup"><span data-stu-id="f2844-104">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxy account defines a security context in which a job step can run.</span></span> <span data-ttu-id="f2844-105">Каждой учетной записи-посреднику соответствует учетная запись системы безопасности.</span><span class="sxs-lookup"><span data-stu-id="f2844-105">Each proxy corresponds to a security credential.</span></span> <span data-ttu-id="f2844-106">Чтобы установить разрешения для определенного шага задания, создайте учетную запись-посредник, которая имеет необходимые разрешения для подсистемы агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , и затем назначьте эту учетную запись-посредник шагу задания.</span><span class="sxs-lookup"><span data-stu-id="f2844-106">To set permissions for a particular job step, create a proxy that has the required permissions for a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent subsystem, and then assign that proxy to the job step.</span></span>  
  
 <span data-ttu-id="f2844-107">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="f2844-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f2844-108">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="f2844-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f2844-109">Ограничения</span><span class="sxs-lookup"><span data-stu-id="f2844-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="f2844-110">Безопасность</span><span class="sxs-lookup"><span data-stu-id="f2844-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f2844-111">**Создание учетной записи-посредника агента SQL Server с помощью:**</span><span class="sxs-lookup"><span data-stu-id="f2844-111">**To create a SQL Server Agent proxy, using:**</span></span>  
  
     [<span data-ttu-id="f2844-112">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f2844-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="f2844-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f2844-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f2844-114">Перед началом</span><span class="sxs-lookup"><span data-stu-id="f2844-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f2844-115">Ограничения</span><span class="sxs-lookup"><span data-stu-id="f2844-115">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="f2844-116">Перед созданием учетной записи-посредника необходимо создать учетные данные, если они еще не созданы.</span><span class="sxs-lookup"><span data-stu-id="f2844-116">You must create a credential before you create a proxy if one is not already available.</span></span>  
  
-   <span data-ttu-id="f2844-117">Учетные записи-посредники агента[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] используют учетные данные для хранения сведений об учетных записях пользователей Windows.</span><span class="sxs-lookup"><span data-stu-id="f2844-117">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent proxies use credentials to store information about Windows user accounts.</span></span> <span data-ttu-id="f2844-118">Указанный в учетных данных пользователь должен иметь разрешение «Вход в систему в качестве пакетного задания» на компьютере, где запущен [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f2844-118">The user specified in the credential must have "Log on as a batch job" permission on the computer on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="f2844-119">проверяет действительность доступа к подсистеме учетной записи-посредника и предоставляет ей доступ при каждом выполнении шага задания.</span><span class="sxs-lookup"><span data-stu-id="f2844-119">Agent checks subsystem access for a proxy and gives access to the proxy each time the job step runs.</span></span> <span data-ttu-id="f2844-120">Если учетная запись-посредник больше не имеет доступа к подсистеме, шаг задания завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="f2844-120">If the proxy no longer has access to the subsystem, the job step fails.</span></span> <span data-ttu-id="f2844-121">В противном случае агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] олицетворяет пользователя, указанного в учетной записи-посреднике, и запускает шаг задания.</span><span class="sxs-lookup"><span data-stu-id="f2844-121">Otherwise, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent impersonates the user that is specified in the proxy and runs the job step.</span></span>  
  
-   <span data-ttu-id="f2844-122">Создание учетной записи-посредника не влияет на разрешения пользователя, указанного в учетных данных учетной записи-посредника.</span><span class="sxs-lookup"><span data-stu-id="f2844-122">Creation of a proxy does not change the permissions for the user that is specified in the credential for the proxy.</span></span> <span data-ttu-id="f2844-123">Например, можно создать учетную запись-посредник для пользователя, не имеющего разрешения на подключение к экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2844-123">For example, you can create a proxy for a user that does not have permission to connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f2844-124">В этом случае шаги задания, использующие эту учетную запись-посредник, не смогут соединяться с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2844-124">In this case, job steps that use that proxy are unable to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="f2844-125">Если имени входа пользователя предоставлен доступ к учетной записи-посреднику или пользователь принадлежит к любой роли с доступом к учетной записи-посреднику, то он может использовать учетную запись-посредник в шаге задания.</span><span class="sxs-lookup"><span data-stu-id="f2844-125">If the login for the user has access to the proxy, or the user belongs to any role with access to the proxy, the user can use the proxy in a job step.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f2844-126">безопасность</span><span class="sxs-lookup"><span data-stu-id="f2844-126">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f2844-127">Permissions</span><span class="sxs-lookup"><span data-stu-id="f2844-127">Permissions</span></span>  
  
-   <span data-ttu-id="f2844-128">Только члены предопределенной роли сервера **sysadmin** имеют разрешение на создание, изменение или удаление учетных записей-посредников.</span><span class="sxs-lookup"><span data-stu-id="f2844-128">Only members of the **sysadmin** fixed server role have permission to create, modify, or delete proxy accounts.</span></span> <span data-ttu-id="f2844-129">Пользователи, не являющиеся членами предопределенной роли сервера **sysadmin** , должны быть добавлены к одной из следующих предопределенных ролей базы данных агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в базе данных **msdb** , чтобы использовать записи-посредники: **SQLAgentUserRole**, **SQLAgentReaderRole**или **SQLAgentOperatorRole**.</span><span class="sxs-lookup"><span data-stu-id="f2844-129">Users who are not members of the **sysadmin** fixed server role must be added to one of the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles in the **msdb** database to use proxies: **SQLAgentUserRole**, **SQLAgentReaderRole**, or **SQLAgentOperatorRole**.</span></span>  
  
-   <span data-ttu-id="f2844-130">При создании учетных данных в дополнение к учетной записи-посреднику требуется разрешение `ALTER ANY CREDENTIAL`.</span><span class="sxs-lookup"><span data-stu-id="f2844-130">Requires `ALTER ANY CREDENTIAL` permission if creating a credential in addition to the proxy.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f2844-131">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f2844-131">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-sql-server-agent-proxy"></a><span data-ttu-id="f2844-132">Создание учетной записи-посредника агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="f2844-132">To create a SQL Server Agent proxy</span></span>  
  
1.  <span data-ttu-id="f2844-133">В **обозревателе объектов**щелкните значок «плюс», чтобы развернуть сервер, на котором необходимо создать учетную запись-посредник агента SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f2844-133">In **Object Explorer**, click the plus sign to expand the server where you want to create a proxy on SQL Server Agent.</span></span>  
  
2.  <span data-ttu-id="f2844-134">Щелкните знак "плюс", чтобы развернуть **Агент SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="f2844-134">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="f2844-135">Щелкните правой кнопкой мыши папку **Прокси-серверы** и выберите пункт **Создать прокси-сервер**.</span><span class="sxs-lookup"><span data-stu-id="f2844-135">Right-click the **Proxies** folder and select **New Proxy**.</span></span>  
  
4.  <span data-ttu-id="f2844-136">В диалоговом окне **Создание учетной записи-посредника** на странице **Общие** введите имя учетной записи-посредника в поле **Имя учетной записи-посредника** .</span><span class="sxs-lookup"><span data-stu-id="f2844-136">On the **New Proxy Account** dialog box, on the **General** page, enter the name of the proxy account in the **Proxy name** box.</span></span>  
  
5.  <span data-ttu-id="f2844-137">В поле **Учетные данные** введите учетные данные, которые будут использоваться учетной записью-посредником.</span><span class="sxs-lookup"><span data-stu-id="f2844-137">In the **Credential name** box, enter the name of the security credential that the proxy account will use.</span></span>  
  
6.  <span data-ttu-id="f2844-138">В поле **Описание** введите описание учетной записи-посредника.</span><span class="sxs-lookup"><span data-stu-id="f2844-138">In the **Description** box, enter a description for the proxy account</span></span>  
  
7.  <span data-ttu-id="f2844-139">В поле **Активна для следующих подсистем**выберите соответствующую подсистему или подсистемы для этой учетной записи-посредника.</span><span class="sxs-lookup"><span data-stu-id="f2844-139">Under **Active to the following subsystems**, select the appropriate subsystem or subsystems for this proxy.</span></span>  
  
8.  <span data-ttu-id="f2844-140">На вкладке **Участники** добавьте или удалите имена входа или роли, чтобы предоставить или отменить доступ к учетной записи-посреднику.</span><span class="sxs-lookup"><span data-stu-id="f2844-140">On the **Principals** page, add or remove logins or roles to grant or remove access to the proxy account.</span></span>  
  
9. <span data-ttu-id="f2844-141">После завершения нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f2844-141">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f2844-142">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f2844-142">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-sql-server-agent-proxy"></a><span data-ttu-id="f2844-143">Создание учетной записи-посредника агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="f2844-143">To create a SQL Server Agent proxy</span></span>  
  
1.  <span data-ttu-id="f2844-144">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2844-144">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f2844-145">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="f2844-145">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f2844-146">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="f2844-146">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- creates credential CatalogApplicationCredential  
    USE msdb ;  
    GO  
    CREATE CREDENTIAL CatalogApplicationCredential WITH IDENTITY = 'REDMOND/TestUser',   
        SECRET = 'G3$1o)lkJ8HNd!';  
    GO  
    -- creates proxy "Catalog application proxy" and assigns the credential 'CatalogApplicationCredential' to it.  
    EXEC dbo.sp_add_proxy  
        @proxy_name = 'Catalog application proxy',  
        @enabled = 1,  
        @description = 'Maintenance tasks on catalog application.',  
        @credential_name = 'CatalogApplicationCredential' ;  
    GO  
    -- grants the proxy "Catalog application proxy" access to the ActiveX Scripting subsystem.  
    EXEC dbo.sp_grant_proxy_to_subsystem  
        @proxy_name = N'Catalog application proxy',  
        @subsystem_id = 2 ;  
    GO  
    ```  
  
 <span data-ttu-id="f2844-147">Дополнительные сведения см. в разделе:</span><span class="sxs-lookup"><span data-stu-id="f2844-147">For more information, see:</span></span>  
  
-   [<span data-ttu-id="f2844-148">CREATE CREDENTIAL &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f2844-148">CREATE CREDENTIAL &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-credential-transact-sql)  
  
-   [<span data-ttu-id="f2844-149">sp_add_proxy &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f2844-149">sp_add_proxy &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-proxy-transact-sql)  
  
-   [<span data-ttu-id="f2844-150">sp_grant_proxy_to_subsystem &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f2844-150">sp_grant_proxy_to_subsystem &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-grant-proxy-to-subsystem-transact-sql)  
  
  
