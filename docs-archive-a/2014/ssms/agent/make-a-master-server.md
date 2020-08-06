---
title: Создание главного сервера | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.msxwiz.complete.f1
- sql12.ag.msxwiz.target.f1
- sql12.ag.msxwiz.login.f1
- sql12.ag.msxwiz.cover.f1
- sql12.ag.msxwiz.operator.f1
helpviewer_keywords:
- master servers [SQL Server], creating
- wizards [SQL Server Management Studio], Master Server Wizard
- SQL Server Agent jobs, master servers
- Master Server Wizard
ms.assetid: 05739a73-1fdf-4d9d-92a6-70f328380322
author: stevestein
ms.author: sstein
ms.openlocfilehash: ce8e7428aaf8ba459bcf6831988c61da3f192bac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659070"
---
# <a name="make-a-master-server"></a><span data-ttu-id="6e402-102">Make a Master Server</span><span class="sxs-lookup"><span data-stu-id="6e402-102">Make a Master Server</span></span>
  <span data-ttu-id="6e402-103">В этом разделе описывается, как создать главный сервер [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6e402-103">This topic describes how to make a master server [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="6e402-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="6e402-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6e402-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="6e402-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6e402-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="6e402-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="6e402-107">**Для создания главного сервера используется:**</span><span class="sxs-lookup"><span data-stu-id="6e402-107">**To make a master server, using:**</span></span>  
  
     [<span data-ttu-id="6e402-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6e402-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="6e402-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6e402-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6e402-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="6e402-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6e402-111">безопасность</span><span class="sxs-lookup"><span data-stu-id="6e402-111">Security</span></span>  
 <span data-ttu-id="6e402-112">Распределенные задания, имеющие связанные с учетной записью-посредником шаги, выполняются в контексте учетной записи-посредника на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="6e402-112">Distributed jobs that have steps which are associated with a proxy run under the context of the proxy account on the target server.</span></span> <span data-ttu-id="6e402-113">Убедитесь в том, что выполняются нижеприведенные условия, либо в том, что шаги заданий, связанные с учетной записью-посредником, не будут загружаться с главного сервера на целевой:</span><span class="sxs-lookup"><span data-stu-id="6e402-113">Make sure that the following conditions are met or job steps that are associated with a proxy will not be downloaded from the master server to the target:</span></span>  
  
-   <span data-ttu-id="6e402-114">В подразделе реестра главного сервера **\ HKEY_LOCAL_MACHINE \софтваре\микрософт\микрософт SQL Server \\ < *instance_name*> \SQL Server Agent\AllowDownloadedJobsToMatchProxyName** (REG_DWORD) установлено значение 1 (true).</span><span class="sxs-lookup"><span data-stu-id="6e402-114">The master server registry subkey **\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<*instance_name*>\SQL Server Agent\AllowDownloadedJobsToMatchProxyName** (REG_DWORD) is set to 1 (true).</span></span> <span data-ttu-id="6e402-115">По умолчанию для него задается значение 0 (false).</span><span class="sxs-lookup"><span data-stu-id="6e402-115">By default, this subkey is set to 0 (false).</span></span>  
  
-   <span data-ttu-id="6e402-116">На целевом сервере есть учетная запись-посредник. Ее имя совпадает с именем учетной записи-посредника на главном сервере, под которой выполняется шаг задания.</span><span class="sxs-lookup"><span data-stu-id="6e402-116">A proxy account exists on the target server that has the same name as the master server proxy account under which the job step runs.</span></span>  
  
 <span data-ttu-id="6e402-117">Если шаги задания, использующие учетную запись-посредник, завершаются с ошибками при скачивании с главного сервера на целевой, то в столбце **error_message** в таблице **sysdownloadlist** базы данных **msdb** появятся следующие сообщения об ошибках:</span><span class="sxs-lookup"><span data-stu-id="6e402-117">If job steps that use proxy accounts fail when downloading them from the master server to the target server, you can check the **error_message** column in the **sysdownloadlist** table in the **msdb** database for the following error messages:</span></span>  
  
-   <span data-ttu-id="6e402-118">«Для этого шага задания необходима учетная запись-посредник, однако проверка совпадения учетной записи-посредника на целевом сервере отключена.»</span><span class="sxs-lookup"><span data-stu-id="6e402-118">"The job step requires a proxy account, however proxy matching is disabled on the target server."</span></span>  
  
     <span data-ttu-id="6e402-119">Чтобы устранить эту ошибку, задайте для раздела реестра **AllowDownloadedJobsToMatchProxyName** значение 1.</span><span class="sxs-lookup"><span data-stu-id="6e402-119">To resolve this error, set the **AllowDownloadedJobsToMatchProxyName** registry subkey to 1.</span></span>  
  
-   <span data-ttu-id="6e402-120">«Учетная запись-посредник не найдена.»</span><span class="sxs-lookup"><span data-stu-id="6e402-120">"Proxy not found."</span></span>  
  
     <span data-ttu-id="6e402-121">Чтобы устранить эту ошибку, убедитесь, что на целевом сервере есть учетная запись-посредник, имя которой совпадает с именем посреднической учетной записи на главном сервере, под которой выполняется шаг задания.</span><span class="sxs-lookup"><span data-stu-id="6e402-121">To resolve this error, make sure a proxy account exists on the target server that has the same name as the master server proxy account under which the job step runs.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6e402-122">Permissions</span><span class="sxs-lookup"><span data-stu-id="6e402-122">Permissions</span></span>  
 <span data-ttu-id="6e402-123">По умолчанию разрешения на выполнение этой процедуры предоставляются членам предопределенной роли сервера `sysadmin`.</span><span class="sxs-lookup"><span data-stu-id="6e402-123">Permissions to execute this procedure default to members of the `sysadmin` fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6e402-124">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6e402-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-make-a-master-server"></a><span data-ttu-id="6e402-125">Создание главного сервера</span><span class="sxs-lookup"><span data-stu-id="6e402-125">To make a master server</span></span>  
  
1.  <span data-ttu-id="6e402-126">В **обозревателе объектов** подключитесь к экземпляру [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , а затем разверните этот экземпляр.</span><span class="sxs-lookup"><span data-stu-id="6e402-126">In **Object Explorer,** connect to an instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="6e402-127">Щелкните правой кнопкой мыши элемент **Агент SQL Server**, укажите **Администрирование нескольких серверов**и выберите пункт **Сделать главным**.</span><span class="sxs-lookup"><span data-stu-id="6e402-127">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Make this a Master**.</span></span> <span data-ttu-id="6e402-128">**Мастер настройки главного сервера** служит проводником по созданию главного сервера и добавлению целевых серверов.</span><span class="sxs-lookup"><span data-stu-id="6e402-128">The **Master Server Wizard** guides you through the process of making a master server and adding target servers.</span></span>  
  
3.  <span data-ttu-id="6e402-129">На странице **Оператор главного сервера** настройте оператора для главного сервера. Чтобы отправлять уведомления операторам по электронной почте или на пейджеры, необходимо настроить агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для отправки электронной почты.</span><span class="sxs-lookup"><span data-stu-id="6e402-129">From the **Master Server Operator** page, configure an operator for the master server To send notifications to operators by using e-mail or pagers, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be configured to send e-mail.</span></span> <span data-ttu-id="6e402-130">Для отправки уведомлений операторам с использованием команды **net send**на сервере, где установлен агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , должна быть запущена служба сообщений.</span><span class="sxs-lookup"><span data-stu-id="6e402-130">To send notifications to operators by using **net send**, the Messenger service must be running on the server where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent resides.</span></span>  
  
     <span data-ttu-id="6e402-131">**Адрес электронной почты**</span><span class="sxs-lookup"><span data-stu-id="6e402-131">**E-mail address**</span></span>  
     <span data-ttu-id="6e402-132">Адрес электронной почты оператора.</span><span class="sxs-lookup"><span data-stu-id="6e402-132">Sets the e-mail address for the operator.</span></span>  
  
     <span data-ttu-id="6e402-133">**Адрес пейджера**</span><span class="sxs-lookup"><span data-stu-id="6e402-133">**Pager address**</span></span>  
     <span data-ttu-id="6e402-134">Адрес электронной почты пейджера оператора.</span><span class="sxs-lookup"><span data-stu-id="6e402-134">Sets the pager e-mail address for the operator.</span></span>  
  
     <span data-ttu-id="6e402-135">**Адрес для команды net send**</span><span class="sxs-lookup"><span data-stu-id="6e402-135">**Net send address**</span></span>  
     <span data-ttu-id="6e402-136">Задает адрес **net send** для оператора.</span><span class="sxs-lookup"><span data-stu-id="6e402-136">Sets the **net send** address for the operator.</span></span>  
  
4.  <span data-ttu-id="6e402-137">На странице **Целевой сервер** выберите целевые серверы для главного сервера.</span><span class="sxs-lookup"><span data-stu-id="6e402-137">From the **Target Server** page, select target servers for the master server.</span></span>  
  
     <span data-ttu-id="6e402-138">**зарегистрированные серверы**</span><span class="sxs-lookup"><span data-stu-id="6e402-138">**Registered Servers**</span></span>  
     <span data-ttu-id="6e402-139">Выводит серверы, зарегистрированные в среде Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , которые еще не являются целевыми.</span><span class="sxs-lookup"><span data-stu-id="6e402-139">Lists the servers registered in Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] that are not already target servers.</span></span>  
  
     <span data-ttu-id="6e402-140">**Целевые серверы**</span><span class="sxs-lookup"><span data-stu-id="6e402-140">**Target Servers**</span></span>  
     <span data-ttu-id="6e402-141">Выводит серверы, являющиеся целевыми серверами.</span><span class="sxs-lookup"><span data-stu-id="6e402-141">Lists the servers that are target servers.</span></span>  
  
     **>**  
     <span data-ttu-id="6e402-142">Перемещает выбранный сервер в список целевых серверов.</span><span class="sxs-lookup"><span data-stu-id="6e402-142">Move the selected server to the target server list.</span></span>  
  
     **>>**  
     <span data-ttu-id="6e402-143">Перемещает все серверы в список целевых серверов.</span><span class="sxs-lookup"><span data-stu-id="6e402-143">Move all servers to the target server list.</span></span>  
  
     **<**  
     <span data-ttu-id="6e402-144">Удаляет выбранный сервер из списка целевых серверов.</span><span class="sxs-lookup"><span data-stu-id="6e402-144">Remove the selected server from the target server list.</span></span>  
  
     **<<**  
     <span data-ttu-id="6e402-145">Удаляет все серверы из списка целевых серверов.</span><span class="sxs-lookup"><span data-stu-id="6e402-145">Remove all servers from the target server list.</span></span>  
  
     <span data-ttu-id="6e402-146">**Добавить соединение**</span><span class="sxs-lookup"><span data-stu-id="6e402-146">**Add connection**</span></span>  
     <span data-ttu-id="6e402-147">Добавляет сервер в список целевых серверов без регистрации.</span><span class="sxs-lookup"><span data-stu-id="6e402-147">Add a server to the target server list without registering the server.</span></span>  
  
     <span data-ttu-id="6e402-148">**Соединение**</span><span class="sxs-lookup"><span data-stu-id="6e402-148">**Connection**</span></span>  
     <span data-ttu-id="6e402-149">Измените свойства соединения выбранного сервера.</span><span class="sxs-lookup"><span data-stu-id="6e402-149">Change the connection properties for the selected server.</span></span>  
  
5.  <span data-ttu-id="6e402-150">Страница **Учетные данные для входа на главный сервер** используется для создания в случае необходимости нового имени входа для целевого сервера и для назначения этому имени прав на главном сервере.</span><span class="sxs-lookup"><span data-stu-id="6e402-150">From the **Master Server Login Credentials** page to specify if you want to create a new login for the target server, if necessary, and assign it rights to the master server.</span></span>  
  
     <span data-ttu-id="6e402-151">**Создать новое имя входа (если необходимо) и присвоить ему права на главный сервер**</span><span class="sxs-lookup"><span data-stu-id="6e402-151">**Create a new login if necessary and assign it rights to the MSX**</span></span>  
     <span data-ttu-id="6e402-152">Если указанное имя входа еще не существует, создайте на целевом сервере новое имя входа.</span><span class="sxs-lookup"><span data-stu-id="6e402-152">Create a new login on the target server if the login specified does not already exist.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="6e402-153">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6e402-153">Using Transact-SQL</span></span>  
  
#### <a name="to-make-a-master-server"></a><span data-ttu-id="6e402-154">Создание главного сервера</span><span class="sxs-lookup"><span data-stu-id="6e402-154">To make a master server</span></span>  
  
1.  <span data-ttu-id="6e402-155">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6e402-155">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6e402-156">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="6e402-156">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6e402-157">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="6e402-157">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="6e402-158">В этом примере текущий сервер прикрепляется к главному серверу AdventureWorks1.</span><span class="sxs-lookup"><span data-stu-id="6e402-158">This example enlists the current server into the AdventureWorks1 master server.</span></span> <span data-ttu-id="6e402-159">Расположение текущего сервера: строение 21, комната 309, стойка 5.</span><span class="sxs-lookup"><span data-stu-id="6e402-159">The location for the current server is Building 21, Room 309, Rack 5.</span></span>  
  
```  
USE msdb ;  
GO  
  
EXEC dbo.sp_msx_enlist N'AdventureWorks1',   
    N'Building 21, Room 309, Rack 5' ;   
GO;  
```  
  
 <span data-ttu-id="6e402-160">Дополнительные сведения см. в разделе [sp_msx_enlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6e402-160">For more information, see [sp_msx_enlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e402-161">См. также:</span><span class="sxs-lookup"><span data-stu-id="6e402-161">See Also</span></span>  
 <span data-ttu-id="6e402-162">[Создание многосерверной среды](create-a-multiserver-environment.md) </span><span class="sxs-lookup"><span data-stu-id="6e402-162">[Create a Multiserver Environment](create-a-multiserver-environment.md) </span></span>  
 [<span data-ttu-id="6e402-163">Автоматизация администрирования в масштабах предприятия</span><span class="sxs-lookup"><span data-stu-id="6e402-163">Automated Administration Across an Enterprise</span></span>](automated-administration-across-an-enterprise.md)  
  
  
