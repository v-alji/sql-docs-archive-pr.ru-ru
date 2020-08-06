---
title: Защита сборщика данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- data collection [SQL Server]
- security [data collector]
- data collector [SQL Server], security
ms.assetid: e75d6975-641e-440a-a642-cb39a583359a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c89f1658f6ae1b5bd79de96f20222b0b19529df2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656422"
---
# <a name="data-collector-security"></a><span data-ttu-id="ac7ca-102">Безопасность сборщика данных</span><span class="sxs-lookup"><span data-stu-id="ac7ca-102">Data Collector Security</span></span>
  <span data-ttu-id="ac7ca-103">Сборщик данных использует безопасность на основе ролей, реализованную агентом [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ac7ca-103">The data collector uses the role-based security model implemented by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="ac7ca-104">Эта модель позволяет администратору базы данных запускать различные задачи сборщика данных в контексте безопасности, имеющем только те разрешения, которые необходимы для выполнения задачи.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-104">This model lets the database administrator run the various data collector tasks in a security context that has only the permissions required to perform that task.</span></span> <span data-ttu-id="ac7ca-105">Этот подход также используется для операций, затрагивающих внутренние таблицы, доступ к которым можно осуществить только с помощью хранимой процедуры или представления.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-105">This approach is also used for operations involving internal tables, which can only be accessed by using a stored procedure or view.</span></span> <span data-ttu-id="ac7ca-106">Внутренним таблицам разрешения не предоставляются.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-106">No permissions are granted to internal tables.</span></span> <span data-ttu-id="ac7ca-107">Вместо этого разрешения проверяются у пользователя хранимой процедуры или представления, используемых для доступа к таблице.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-107">Instead, permissions are checked on the user of the stored procedure or view that is used to access a table.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ac7ca-108">Еще одним ключевым аспектом данной модели безопасности являются вложенные разрешения.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-108">Another key aspect of this security model is concentric permissions.</span></span> <span data-ttu-id="ac7ca-109">При использовании вложенных разрешений роли с более широкими правами наследуют разрешения ролей с менее широкими правами на объекты (включая предупреждения, операторы, задания, расписания и учетные записи-посредники).</span><span class="sxs-lookup"><span data-stu-id="ac7ca-109">Under concentric permissions, more privileged roles inherit the permissions of less privileged roles on objects (including alerts, operators, jobs, schedules, and proxies).</span></span> <span data-ttu-id="ac7ca-110">Дополнительные сведения см. в статье [SQL Server Agent Fixed Database Roles](../../ssms/agent/sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="ac7ca-110">For more information, see [SQL Server Agent Fixed Database Roles](../../ssms/agent/sql-server-agent-fixed-database-roles.md).</span></span>  
  
 <span data-ttu-id="ac7ca-111">В следующих разделах в общих чертах описывается безопасность сбора данных, а также те роли, которые необходимо предоставлять пользователям, чтобы они могли настроить и использовать сборщик данных и осуществлять выполнение задач, связанных с хранилищем управляющих данных.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-111">The following sections describe data collection security in general, as well as the roles you must grant to users so they can configure and use the data collector, and carry out tasks associated with the management data warehouse.</span></span>  
  
## <a name="general-security"></a><span data-ttu-id="ac7ca-112">Общая безопасность</span><span class="sxs-lookup"><span data-stu-id="ac7ca-112">General Security</span></span>  
 <span data-ttu-id="ac7ca-113">Сборщик данных устанавливается в соответствии с документированными стандартами для [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac7ca-113">The data collector is installed according to the documented standards specified for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
### <a name="network-security"></a><span data-ttu-id="ac7ca-114">Безопасность сети</span><span class="sxs-lookup"><span data-stu-id="ac7ca-114">Network Security</span></span>  
 <span data-ttu-id="ac7ca-115">Конфиденциальные данные могут передаваться между целевыми экземплярами, реляционным экземпляром, связанным с сервером конфигурации, на котором работают наборы сбора, и сервером, на котором расположено хранилище управляющих данных.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-115">Sensitive information can be passed between target instances, the relational instance associated with the configuration server, the collection sets that are running, and the server that hosts the management data warehouse.</span></span>  
  
 <span data-ttu-id="ac7ca-116">Для защиты любых данных, передаваемых по сети, были введены стандартные механизмы безопасности, такие как шифрование протокола для [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac7ca-116">To protect any data that is transferred over a network, the standard security mechanisms are implemented, such as protocol encryption for [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
## <a name="permissions-for-configuring-and-using-the-data-collector"></a><span data-ttu-id="ac7ca-117">Разрешения для настройки и использования сборщика данных</span><span class="sxs-lookup"><span data-stu-id="ac7ca-117">Permissions for Configuring and Using the Data Collector</span></span>  
 <span data-ttu-id="ac7ca-118">В зависимости от задачи пользователи должны быть участниками одной или нескольких предопределенных ролей базы данных, предоставленных для сборщика данных.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-118">Depending on the task, users must be members of one or more of the fixed database roles provided for the data collector.</span></span> <span data-ttu-id="ac7ca-119">В порядке от наиболее привилегированных до наименее привилегированных список ролей выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-119">In order of most-privileged to least-privileged access, the roles are as follows:</span></span>  
  
-   `dc_admin`  
  
-   <span data-ttu-id="ac7ca-120">**dc_operator**</span><span class="sxs-lookup"><span data-stu-id="ac7ca-120">**dc_operator**</span></span>  
  
-   <span data-ttu-id="ac7ca-121">**dc_proxy**</span><span class="sxs-lookup"><span data-stu-id="ac7ca-121">**dc_proxy**</span></span>  
  
 <span data-ttu-id="ac7ca-122">Эти роли хранятся в базе данных msdb.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-122">These roles are stored in the msdb database.</span></span> <span data-ttu-id="ac7ca-123">По умолчанию ни один из пользователей ни в одну из этих ролей не входит.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-123">By default, no user is a member of these database roles.</span></span> <span data-ttu-id="ac7ca-124">Членство в этих ролях необходимо предоставлять явным образом.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-124">User membership in these roles must be granted explicitly.</span></span>  
  
 <span data-ttu-id="ac7ca-125">Пользователи, являющиеся членами `sysadmin` предопределенной роли сервера, имеют полный доступ к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] объектам агента и представлениям сборщика данных.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-125">Users who are members of the `sysadmin` fixed server role have full access to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent objects and data collector views.</span></span> <span data-ttu-id="ac7ca-126">Однако для этого их нужно явно добавить в роли сборщика данных.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-126">However, they need to be explicitly added to data collector roles.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ac7ca-127">Члены роли db_ssisadmin и роли dc_admin могут повышать свои права доступа до sysadmin.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-127">Members of the db_ssisadmin role and the dc_admin role may be able to elevate their privileges to sysadmin.</span></span> <span data-ttu-id="ac7ca-128">Такое повышение права доступа может произойти, так как эти роли могут изменять пакеты служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , а пакеты [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] могут выполняться [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] при помощи контекста безопасности sysadmin агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ac7ca-128">This elevation of privilege can occur because these roles can modify [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages and [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages can be executed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using the sysadmin security context of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="ac7ca-129">Чтобы предотвратить такое повышение прав при выполнении планов обслуживания, наборов сбора данных и других пакетов служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , настройте задания агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , запускающие пакеты, на использование учетной записи-посредника с ограниченными правами или добавьте членов sysadmin в роли db_ssisadmin и dc_admin.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-129">To guard against this elevation of privilege when running maintenance plans, data collection sets, and other [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs that run packages to use a proxy account with limited privileges or only add sysadmin members to the db_ssisadmin and dc_admin roles.</span></span>  
  
### <a name="dc_admin-role"></a><span data-ttu-id="ac7ca-130">Роль dc_admin</span><span class="sxs-lookup"><span data-stu-id="ac7ca-130">dc_admin Role</span></span>  
 <span data-ttu-id="ac7ca-131">Пользователи, которым назначена `dc_admin` роль, имеют полный доступ администратора (создание, чтение, обновление и удаление) к конфигурации сборщика данных на экземпляре сервера.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-131">Users assigned to the `dc_admin` role have full administrator access (Create, Read, Update, and Delete) to the data collector configuration on a server instance.</span></span> <span data-ttu-id="ac7ca-132">Члены этой роли могут выполнять следующие операции:</span><span class="sxs-lookup"><span data-stu-id="ac7ca-132">Members of this role can perform the following operations:</span></span>  
  
-   <span data-ttu-id="ac7ca-133">задавать свойства уровня сборщика;</span><span class="sxs-lookup"><span data-stu-id="ac7ca-133">Set collector-level properties.</span></span>  
  
-   <span data-ttu-id="ac7ca-134">добавлять новые наборы сбора;</span><span class="sxs-lookup"><span data-stu-id="ac7ca-134">Add new collection sets.</span></span>  
  
-   <span data-ttu-id="ac7ca-135">устанавливать новые типы сбора;</span><span class="sxs-lookup"><span data-stu-id="ac7ca-135">Install new collection types.</span></span>  
  
-   <span data-ttu-id="ac7ca-136">выполнять все действия, разрешенные роли **dc_operator** .</span><span class="sxs-lookup"><span data-stu-id="ac7ca-136">Perform all the operations permitted to the **dc_operator** role.</span></span>  
  
 <span data-ttu-id="ac7ca-137">`dc_admin`Роль является членом следующих ролей:</span><span class="sxs-lookup"><span data-stu-id="ac7ca-137">The `dc_admin` role is a member of the following roles:</span></span>  
  
-   <span data-ttu-id="ac7ca-138">**SQLAgentUserRole**.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-138">**SQLAgentUserRole**.</span></span> <span data-ttu-id="ac7ca-139">Эта роль необходима для создания расписаний и запуска заданий.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-139">This role is required to create schedules and run jobs.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ac7ca-140">Прокси-серверы, созданные для сборщика данных, должны предоставлять доступ к `dc_admin` для их создания и использовать в любых шагах задания, требующих прокси.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-140">Proxies created for the data collector must grant access to `dc_admin` to create them and use them in any job steps that require a proxy.</span></span>  
  
-   <span data-ttu-id="ac7ca-141">**dc_operator**.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-141">**dc_operator**.</span></span> <span data-ttu-id="ac7ca-142">Члены класса `dc_admin` наследуют разрешения, предоставленные **dc_operator**.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-142">Members of `dc_admin` inherit the permissions given to **dc_operator**.</span></span>  
  
### <a name="dc_operator-role"></a><span data-ttu-id="ac7ca-143">Роль dc_operator</span><span class="sxs-lookup"><span data-stu-id="ac7ca-143">dc_operator Role</span></span>  
 <span data-ttu-id="ac7ca-144">Члены роли **dc_operator** имеют доступ на чтение и обновление.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-144">Members of the **dc_operator** role have Read and Update access.</span></span> <span data-ttu-id="ac7ca-145">Эта роль поддерживает задачи, связанные с выполнением и настройкой наборов сбора.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-145">This role supports operations tasks related to running and configuring collection sets.</span></span> <span data-ttu-id="ac7ca-146">Члены этой роли могут выполнять следующие операции:</span><span class="sxs-lookup"><span data-stu-id="ac7ca-146">Members of this role can perform the following operations:</span></span>  
  
-   <span data-ttu-id="ac7ca-147">запускать или останавливать набор сбора;</span><span class="sxs-lookup"><span data-stu-id="ac7ca-147">Start or stop a collection set.</span></span>  
  
-   <span data-ttu-id="ac7ca-148">перечислять существующие наборы сбора;</span><span class="sxs-lookup"><span data-stu-id="ac7ca-148">Enumerate existing collection sets.</span></span>  
  
-   <span data-ttu-id="ac7ca-149">просматривать подробные сведения (например, элементы сбора и частоту сбора), связанные с набором сбора;</span><span class="sxs-lookup"><span data-stu-id="ac7ca-149">View the detailed information (for example, collection items, and collection frequency) associated with a collection set.</span></span>  
  
-   <span data-ttu-id="ac7ca-150">изменять частоту загрузки для существующих наборов сбора;</span><span class="sxs-lookup"><span data-stu-id="ac7ca-150">Change the upload frequency for existing collection sets.</span></span>  
  
-   <span data-ttu-id="ac7ca-151">изменять частоту сбора для элементов сбора, являющихся частью существующего набора сбора.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-151">Change the collection frequency for collection items that are part of an existing collection set.</span></span>  
  
 <span data-ttu-id="ac7ca-152">Роль **dc_operator** является членом следующих ролей, необходимых для перечисления и просмотра пакетов сборщика данных:</span><span class="sxs-lookup"><span data-stu-id="ac7ca-152">The **dc_operator** role is a member of the following roles that are required for enumerating and viewing data collector packages:</span></span>  
  
-   <span data-ttu-id="ac7ca-153">**db_ssisltduser**</span><span class="sxs-lookup"><span data-stu-id="ac7ca-153">**db_ssisltduser**</span></span>  
  
-   <span data-ttu-id="ac7ca-154">**db_ssisoperator**</span><span class="sxs-lookup"><span data-stu-id="ac7ca-154">**db_ssisoperator**</span></span>  
  
 <span data-ttu-id="ac7ca-155">Дополнительные сведения см. в разделе [Роли служб Integration Services (службы SSIS)](../../integration-services/security/integration-services-roles-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="ac7ca-155">For more information, see [Integration Services Roles &#40;SSIS Service&#41;](../../integration-services/security/integration-services-roles-ssis-service.md).</span></span>  
  
### <a name="dc_proxy-role"></a><span data-ttu-id="ac7ca-156">Роль dc_proxy</span><span class="sxs-lookup"><span data-stu-id="ac7ca-156">dc_proxy Role</span></span>  
 <span data-ttu-id="ac7ca-157">Члены роли **dc_proxy** имеют доступ на чтение всех наборов элементов сбора сборщика данных и свойств уровня сборщика.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-157">Members of the **dc_proxy** role have Read access to data collector collection sets and collector-level properties.</span></span> <span data-ttu-id="ac7ca-158">Члены этой роли могут также выполнять задания, владельцами которых они являются, и создавать шаги задания, которые выполняются от имени существующей учетной записи-посредника.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-158">Members of this role can also execute jobs that they own and create job steps that run as an existing proxy account.</span></span>  
  
 <span data-ttu-id="ac7ca-159">Члены этой роли могут выполнять следующие операции:</span><span class="sxs-lookup"><span data-stu-id="ac7ca-159">Members of this role can perform the following operations:</span></span>  
  
-   <span data-ttu-id="ac7ca-160">просматривать сведения о конфигурации набора сбора (например, входные параметры для элементов сбора и их частоту);</span><span class="sxs-lookup"><span data-stu-id="ac7ca-160">View collection set configuration information (for example, input parameters for collection items, and the collection frequency for these items).</span></span>  
  
-   <span data-ttu-id="ac7ca-161">получать внутренние зашифрованные данные, доступ к которым можно получить только с помощью подписанной хранимой процедуры (например, сведения о соединении с хранилищем данных, используемым для передачи данных);</span><span class="sxs-lookup"><span data-stu-id="ac7ca-161">Obtain internal encrypted information that can only be accessed by a signed stored procedure (for example, data warehouse connection information used for data uploads).</span></span>  
  
-   <span data-ttu-id="ac7ca-162">вести журнал событий времени исполнения наборов сбора.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-162">Log collection-set run-time events.</span></span>  
  
 <span data-ttu-id="ac7ca-163">Роль **dc_proxy** является членом следующих ролей, необходимых для перечисления и просмотра пакетов сборщика данных.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-163">The **dc_proxy** role is a member of the following roles that are required for enumerating and viewing data collector packages:</span></span>  
  
-   <span data-ttu-id="ac7ca-164">**db_ssisltduser**.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-164">**db_ssisltduser**.</span></span>  
  
-   <span data-ttu-id="ac7ca-165">**db_ssisoperator**</span><span class="sxs-lookup"><span data-stu-id="ac7ca-165">**db_ssisoperator**</span></span>  
  
 <span data-ttu-id="ac7ca-166">Дополнительные сведения см. в разделе [Роли служб Integration Services (службы SSIS)](../../integration-services/security/integration-services-roles-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="ac7ca-166">For more information, see [Integration Services Roles &#40;SSIS Service&#41;](../../integration-services/security/integration-services-roles-ssis-service.md).</span></span>  
  
## <a name="permissions-for-configuring-and-using-the-management-data-warehouse"></a><span data-ttu-id="ac7ca-167">Разрешения для настройки и использования хранилища управляющих данных</span><span class="sxs-lookup"><span data-stu-id="ac7ca-167">Permissions for Configuring and Using the Management Data Warehouse</span></span>  
 <span data-ttu-id="ac7ca-168">В зависимости от задачи пользователи должны быть членами одной или нескольких предопределенных ролей базы данных, предоставленных для доступа к хранилищу данных управления.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-168">Depending on the task, users must be members of one or more of the fixed database roles provided for accessing the management data warehouse.</span></span> <span data-ttu-id="ac7ca-169">В порядке от наиболее привилегированных до наименее привилегированных список ролей выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-169">In order of most-privileged to least-privileged access, the roles are as follows:</span></span>  
  
-   <span data-ttu-id="ac7ca-170">**mdw_admin**</span><span class="sxs-lookup"><span data-stu-id="ac7ca-170">**mdw_admin**</span></span>  
  
-   <span data-ttu-id="ac7ca-171">**mdw_writer**</span><span class="sxs-lookup"><span data-stu-id="ac7ca-171">**mdw_writer**</span></span>  
  
-   <span data-ttu-id="ac7ca-172">**mdw_reader**</span><span class="sxs-lookup"><span data-stu-id="ac7ca-172">**mdw_reader**</span></span>  
  
 <span data-ttu-id="ac7ca-173">Эти роли хранятся в базе данных msdb.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-173">These roles are stored in the msdb database.</span></span> <span data-ttu-id="ac7ca-174">По умолчанию ни один из пользователей ни в одну из этих ролей не входит.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-174">By default, no user is a member of these database roles.</span></span> <span data-ttu-id="ac7ca-175">Членство в этих ролях необходимо предоставлять явным образом.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-175">User membership in these roles must be granted explicitly.</span></span>  
  
 <span data-ttu-id="ac7ca-176">Пользователи, являющиеся членами `sysadmin` предопределенной роли сервера, имеют полный доступ к представлениям сборщика данных.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-176">Users who are members of the `sysadmin` fixed server role have full access to data collector views.</span></span> <span data-ttu-id="ac7ca-177">Однако для этого их нужно явно добавить в роли базы данных для выполнения других операций.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-177">However, they need to be explicitly added to database roles to perform other operations.</span></span>  
  
### <a name="mdw_admin-role"></a><span data-ttu-id="ac7ca-178">Роль mdw_admin</span><span class="sxs-lookup"><span data-stu-id="ac7ca-178">mdw_admin Role</span></span>  
 <span data-ttu-id="ac7ca-179">Члены роли **mdw_admin** имеют доступ на чтение, запись, обновление и удаление данных в хранилище данных управления.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-179">Members of the **mdw_admin** role have Read, Write, Update, and Delete access to the management data warehouse.</span></span>  
  
 <span data-ttu-id="ac7ca-180">Члены этой роли могут выполнять следующие операции:</span><span class="sxs-lookup"><span data-stu-id="ac7ca-180">Members of this role can perform the following operations:</span></span>  
  
-   <span data-ttu-id="ac7ca-181">изменять при необходимости схему хранилища данных управления (например, добавлять новую таблицу при установке нового типа сбора);</span><span class="sxs-lookup"><span data-stu-id="ac7ca-181">Change the management data warehouse schema when required (for example, adding a new table when a new collection type is installed).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ac7ca-182">При изменении схемы пользователь также должен быть членом `dc_admin` роли для установки нового типа сборщика, так как для этого действия требуется разрешение на обновление конфигурации сборщика данных в msdb.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-182">Where there is a schema change, the user must also be a member of the `dc_admin` role to install a new collector type, since this action requires permission to update the data collector configuration in msdb.</span></span>  
  
-   <span data-ttu-id="ac7ca-183">запускать обслуживающие задания для хранилища данных управления, например архивацию или очистку.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-183">Run maintenance jobs on the management data warehouse, such as archive or cleanup.</span></span>  
  
### <a name="mdw_writer-role"></a><span data-ttu-id="ac7ca-184">Роль mdw_writer</span><span class="sxs-lookup"><span data-stu-id="ac7ca-184">mdw_writer Role</span></span>  
 <span data-ttu-id="ac7ca-185">Члены роли **mdw_writer** могут передавать и записывать данные в хранилище данных управления.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-185">Members of the **mdw_writer** role can upload and write data to the management data warehouse.</span></span> <span data-ttu-id="ac7ca-186">Любой сборщик данных, хранящий данные в хранилище данных управления, должен быть членом данной роли.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-186">Any data collector that stores data in the management data warehouse has to be a member of this role.</span></span>  
  
### <a name="mdw_reader-role"></a><span data-ttu-id="ac7ca-187">Роль mdw_reader</span><span class="sxs-lookup"><span data-stu-id="ac7ca-187">mdw_reader Role</span></span>  
 <span data-ttu-id="ac7ca-188">Члены роли **mdw_reader** имеют доступ на чтение к хранилищу данных управления.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-188">Members of the **mdw_reader** role have Read access to the management data warehouse.</span></span> <span data-ttu-id="ac7ca-189">Эта роль предназначена для помощи при устранении неполадок путем предоставления доступа к данным с предысторией. Ее члены не могут просматривать другие элементы схемы хранилища данных управления.</span><span class="sxs-lookup"><span data-stu-id="ac7ca-189">Because the purpose of this role is to support troubleshooting by providing access to historical data, members of this role cannot view other elements of the management data warehouse schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac7ca-190">См. также:</span><span class="sxs-lookup"><span data-stu-id="ac7ca-190">See Also</span></span>  
 [<span data-ttu-id="ac7ca-191">Обеспечение безопасности агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="ac7ca-191">Implement SQL Server Agent Security</span></span>](../../ssms/agent/implement-sql-server-agent-security.md)  
  
  
