---
title: Создание целевого сервера | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.tsxwiz.msx.f1
- sql12.ag.tsxwiz.cover.f1
- sql12.ag.tsxwiz.credentials.f1
- sql12.ag.tsxwiz.complete.f1
helpviewer_keywords:
- Target Server Wizard
- SQL Server Agent jobs, target servers
- target servers [SQL Server], creating
ms.assetid: 13aabe2d-67fe-4c67-8d49-2928dd705b7a
author: stevestein
ms.author: sstein
ms.openlocfilehash: bd60a19234d186bb0912978589fa60fd8e8a8c22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727901"
---
# <a name="make-a-target-server"></a><span data-ttu-id="efcaa-102">Создание целевого сервера</span><span class="sxs-lookup"><span data-stu-id="efcaa-102">Make a Target Server</span></span>
  <span data-ttu-id="efcaa-103">В этом разделе описывается создание целевого сервера в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)]или управляющих объектов SQL Server (SMO).</span><span class="sxs-lookup"><span data-stu-id="efcaa-103">This topic describes how to make a target server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects (SMO).</span></span>  
  
 <span data-ttu-id="efcaa-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="efcaa-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="efcaa-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="efcaa-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="efcaa-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="efcaa-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="efcaa-107">**Для создания целевого сервера используется:**</span><span class="sxs-lookup"><span data-stu-id="efcaa-107">**To make a target server, using:**</span></span>  
  
     [<span data-ttu-id="efcaa-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="efcaa-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="efcaa-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="efcaa-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="efcaa-110">ОБЪЕКТАХ</span><span class="sxs-lookup"><span data-stu-id="efcaa-110">SMO</span></span>](#PowerShellProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="efcaa-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="efcaa-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="efcaa-112">безопасность</span><span class="sxs-lookup"><span data-stu-id="efcaa-112">Security</span></span>  
 <span data-ttu-id="efcaa-113">Распределенные задания, имеющие связанные с учетной записью-посредником шаги, выполняются в контексте учетной записи-посредника на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="efcaa-113">Distributed jobs that have steps which are associated with a proxy run under the context of the proxy account on the target server.</span></span> <span data-ttu-id="efcaa-114">Убедитесь в том, что выполняются нижеприведенные условия, либо в том, что шаги заданий, связанные с учетной записью-посредником, не будут загружаться с главного сервера на целевой:</span><span class="sxs-lookup"><span data-stu-id="efcaa-114">Make sure that the following conditions are met or job steps that are associated with a proxy will not be downloaded from the master server to the target:</span></span>  
  
-   <span data-ttu-id="efcaa-115">В подразделе реестра главного сервера **\ HKEY_LOCAL_MACHINE \софтваре\микрософт\микрософт SQL Server \\ < *instance_name*> \SQL Server Agent\AllowDownloadedJobsToMatchProxyName** (REG_DWORD) установлено значение 1 (true).</span><span class="sxs-lookup"><span data-stu-id="efcaa-115">The master server registry subkey **\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<*instance_name*>\SQL Server Agent\AllowDownloadedJobsToMatchProxyName** (REG_DWORD) is set to 1 (true).</span></span> <span data-ttu-id="efcaa-116">По умолчанию для него задается значение 0 (false).</span><span class="sxs-lookup"><span data-stu-id="efcaa-116">By default, this subkey is set to 0 (false).</span></span>  
  
-   <span data-ttu-id="efcaa-117">На целевом сервере есть учетная запись-посредник. Ее имя совпадает с именем учетной записи-посредника на главном сервере, под которой выполняется шаг задания.</span><span class="sxs-lookup"><span data-stu-id="efcaa-117">A proxy account exists on the target server that has the same name as the master server proxy account under which the job step runs.</span></span>  
  
 <span data-ttu-id="efcaa-118">Если шаги задания, использующие учетную запись-посредник, завершаются с ошибками при скачивании с главного сервера на целевой, то в столбце **error_message** в таблице **sysdownloadlist** базы данных **msdb** появятся следующие сообщения об ошибках:</span><span class="sxs-lookup"><span data-stu-id="efcaa-118">If job steps that use proxy accounts fail when downloading them from the master server to the target server, you can check the **error_message** column in the **sysdownloadlist** table in the **msdb** database for the following error messages:</span></span>  
  
-   <span data-ttu-id="efcaa-119">«Для этого шага задания необходима учетная запись-посредник, однако проверка совпадения учетной записи-посредника на целевом сервере отключена.»</span><span class="sxs-lookup"><span data-stu-id="efcaa-119">"The job step requires a proxy account, however proxy matching is disabled on the target server."</span></span>  
  
     <span data-ttu-id="efcaa-120">Чтобы устранить эту ошибку, задайте для раздела реестра **AllowDownloadedJobsToMatchProxyName** значение 1.</span><span class="sxs-lookup"><span data-stu-id="efcaa-120">To resolve this error, set the **AllowDownloadedJobsToMatchProxyName** registry subkey to 1.</span></span>  
  
-   <span data-ttu-id="efcaa-121">«Учетная запись-посредник не найдена.»</span><span class="sxs-lookup"><span data-stu-id="efcaa-121">"Proxy not found."</span></span>  
  
     <span data-ttu-id="efcaa-122">Чтобы устранить эту ошибку, убедитесь, что на целевом сервере есть учетная запись-посредник, имя которой совпадает с именем посреднической учетной записи на главном сервере, под которой выполняется шаг задания.</span><span class="sxs-lookup"><span data-stu-id="efcaa-122">To resolve this error, make sure a proxy account exists on the target server that has the same name as the master server proxy account under which the job step runs.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="efcaa-123">Permissions</span><span class="sxs-lookup"><span data-stu-id="efcaa-123">Permissions</span></span>  
 <span data-ttu-id="efcaa-124">По умолчанию разрешения на выполнение этой процедуры предоставляются членам предопределенной роли сервера `sysadmin`.</span><span class="sxs-lookup"><span data-stu-id="efcaa-124">Permissions to execute this procedure default to members of the `sysadmin` fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="efcaa-125">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="efcaa-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-make-a-target-server"></a><span data-ttu-id="efcaa-126">Создание целевого сервера</span><span class="sxs-lookup"><span data-stu-id="efcaa-126">To make a target server</span></span>  
  
1.  <span data-ttu-id="efcaa-127">В **обозревателе объектов** подключитесь к экземпляру [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , а затем разверните этот экземпляр.</span><span class="sxs-lookup"><span data-stu-id="efcaa-127">In **Object Explorer,** connect to an instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="efcaa-128">Щелкните правой кнопкой мыши элемент **Агент SQL Server**, укажите **Администрирование нескольких серверов**и выберите пункт **Сделать целевым**.</span><span class="sxs-lookup"><span data-stu-id="efcaa-128">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Make this a Target**.</span></span> <span data-ttu-id="efcaa-129">**Мастер целевого сервера** проведет через процесс создания целевого сервера.</span><span class="sxs-lookup"><span data-stu-id="efcaa-129">The **Target Server Wizard** guides you through the process of making a target server.</span></span>  
  
3.  <span data-ttu-id="efcaa-130">На странице **Выбор главного сервера** выберите главный сервер, от которого данный целевой сервер будет получать задания.</span><span class="sxs-lookup"><span data-stu-id="efcaa-130">From the **Select a Master Server** page, select the master server that this target server will receive jobs from.</span></span>  
  
     <span data-ttu-id="efcaa-131">**Выбрать сервер**</span><span class="sxs-lookup"><span data-stu-id="efcaa-131">**Pick Server**</span></span>  
     <span data-ttu-id="efcaa-132">Подключиться к главному серверу.</span><span class="sxs-lookup"><span data-stu-id="efcaa-132">Connect to the master server.</span></span>  
  
     <span data-ttu-id="efcaa-133">**Описание этого сервера**</span><span class="sxs-lookup"><span data-stu-id="efcaa-133">**Description of this server**</span></span>  
     <span data-ttu-id="efcaa-134">Введите описание для данного целевого сервера.</span><span class="sxs-lookup"><span data-stu-id="efcaa-134">Type a description for this target server.</span></span> <span data-ttu-id="efcaa-135">Целевой сервер выгрузит это описание на главный сервер.</span><span class="sxs-lookup"><span data-stu-id="efcaa-135">The target server uploads this description to the master server.</span></span>  
  
4.  <span data-ttu-id="efcaa-136">На странице **Учетные данные для входа на главный сервер** создайте новое имя входа на целевой сервер, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="efcaa-136">From the **Master Server Login Credentials** page, create a new login on the target server, if necessary.</span></span>  
  
     <span data-ttu-id="efcaa-137">**Создать новое имя входа (если необходимо) и присвоить ему права на главный сервер**</span><span class="sxs-lookup"><span data-stu-id="efcaa-137">**Create a new login if necessary and assign it rights to the MSX**</span></span>  
     <span data-ttu-id="efcaa-138">Если указанное имя входа еще не существует, создайте на целевом сервере новое имя входа.</span><span class="sxs-lookup"><span data-stu-id="efcaa-138">Create a new login on the target server if the login specified does not already exist.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="efcaa-139">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="efcaa-139">Using Transact-SQL</span></span>  
  
#### <a name="to-make-a-target-server"></a><span data-ttu-id="efcaa-140">Создание целевого сервера</span><span class="sxs-lookup"><span data-stu-id="efcaa-140">To make a target server</span></span>  
  
1.  <span data-ttu-id="efcaa-141">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="efcaa-141">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="efcaa-142">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="efcaa-142">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="efcaa-143">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="efcaa-143">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="efcaa-144">В этом примере текущий сервер прикрепляется к главному серверу AdventureWorks1.</span><span class="sxs-lookup"><span data-stu-id="efcaa-144">This example enlists the current server into the AdventureWorks1 master server.</span></span> <span data-ttu-id="efcaa-145">Расположение текущего сервера: строение 21, комната 309, стойка 5.</span><span class="sxs-lookup"><span data-stu-id="efcaa-145">The location for the current server is Building 21, Room 309, Rack 5.</span></span>  
  
    ```sql
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_msx_enlist N'AdventureWorks1',   
        N'Building 21, Room 309, Rack 5' ;   
    GO;  
    ```  
  
     <span data-ttu-id="efcaa-146">Дополнительные сведения см. в разделе [sp_msx_enlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="efcaa-146">For more information, see [sp_msx_enlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects-smo"></a><a name="PowerShellProcedure"></a><span data-ttu-id="efcaa-147">Использование управляющие объекты SQL Server (SMO)</span><span class="sxs-lookup"><span data-stu-id="efcaa-147">Using SQL Server Management Objects (SMO)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efcaa-148">См. также:</span><span class="sxs-lookup"><span data-stu-id="efcaa-148">See Also</span></span>  
 [<span data-ttu-id="efcaa-149">Автоматизация администрирования в масштабах предприятия</span><span class="sxs-lookup"><span data-stu-id="efcaa-149">Automated Administration Across an Enterprise</span></span>](automated-administration-across-an-enterprise.md)  
