---
title: Использование регулятора ресурсов для ограничения загрузки ЦП при сжатии резервной копии (компонент Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backup compression [SQL Server], Resource Governor
- backup compression [SQL Server], CPU usage
- compression [SQL Server], backup compression
- backups [SQL Server], compression
- Resource Governor, backup compression
ms.assetid: 01796551-578d-4425-9b9e-d87210f7ba72
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 19a95cfa5c6780fbdf71ae58bd141aa9aa351efa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751211"
---
# <a name="use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql"></a><span data-ttu-id="4fc49-102">Использование регулятора ресурсов для ограничения загрузки ЦП при сжатии резервной копии (компонент Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4fc49-102">Use Resource Governor to Limit CPU Usage by Backup Compression (Transact-SQL)</span></span>
  <span data-ttu-id="4fc49-103">По умолчанию резервное копирование с использованием сжатия существенно увеличивает загрузку ЦП, а дополнительная загрузка ЦП процессом сжатия может неблагоприятно повлиять на параллельные операции.</span><span class="sxs-lookup"><span data-stu-id="4fc49-103">By default, backing up using compression significantly increases CPU usage, and the additional CPU consumed by the compression process can adversely impact concurrent operations.</span></span> <span data-ttu-id="4fc49-104">Поэтому может понадобиться создать низкоприоритетную сжатую резервную копию в сеансе, загрузка ЦП в котором ограничивается[Resource Governor](../resource-governor/resource-governor.md) в случае конфликта ЦП.</span><span class="sxs-lookup"><span data-stu-id="4fc49-104">Therefore, you might want to create a low-priority compressed backup in a session whose CPU usage is limited by[Resource Governor](../resource-governor/resource-governor.md) when CPU contention occurs.</span></span> <span data-ttu-id="4fc49-105">В этом разделе представлен сценарий, классифицирующий сеансы отдельного пользователя [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] путем сопоставления их с той или иной группой рабочей нагрузки регулятора ресурсов, которая в таких случаях ограничивает загрузку ЦП.</span><span class="sxs-lookup"><span data-stu-id="4fc49-105">This topic presents a scenario that classifies the sessions of a particular [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user by mapping them to a Resource Governor workload group that limits CPU usage in such cases.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4fc49-106">В данном сценарии регулятора ресурсов классификация сеансов может основываться на имени пользователя, названии приложения или каком-либо другом критерии различения соединения.</span><span class="sxs-lookup"><span data-stu-id="4fc49-106">In a given Resource Governor scenario, session classification might be based on a user name, an application name, or anything else that can differentiate a connection.</span></span> <span data-ttu-id="4fc49-107">Дополнительные сведения см. в разделах [Resource Governor Classifier Function](../resource-governor/resource-governor-classifier-function.md) и [Resource Governor Workload Group](../resource-governor/resource-governor-workload-group.md).</span><span class="sxs-lookup"><span data-stu-id="4fc49-107">For more information, see [Resource Governor Classifier Function](../resource-governor/resource-governor-classifier-function.md) and [Resource Governor Workload Group](../resource-governor/resource-governor-workload-group.md).</span></span>  
  
##  <a name="this-topic-contains-the-following-set-of-scenarios-which-are-presented-in-sequence"></a><a name="Top"></a> <span data-ttu-id="4fc49-108">Этот раздел содержит следующий набор сценариев, представленных в следующей последовательности.</span><span class="sxs-lookup"><span data-stu-id="4fc49-108">This topic contains the following set of scenarios, which are presented in sequence:</span></span>  
  
1.  [<span data-ttu-id="4fc49-109">Создание учетной записи и пользователя для операций с низким приоритетом</span><span class="sxs-lookup"><span data-stu-id="4fc49-109">Setting Up a Login and User for Low-Priority Operations</span></span>](#setup_login_and_user)  
  
2.  [<span data-ttu-id="4fc49-110">Настройка регулятора ресурсов для ограничения загрузки ЦП</span><span class="sxs-lookup"><span data-stu-id="4fc49-110">Configuring Resource Governor to Limit CPU Usage</span></span>](#configure_RG)  
  
3.  [<span data-ttu-id="4fc49-111">Проверка классификации текущего сеанса (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4fc49-111">Verifying the Classification of the Current Session (Transact-SQL)</span></span>](#verifying)  
  
4.  [<span data-ttu-id="4fc49-112">Сжатие резервных копий в сеансе с ограничением доступа к ЦП</span><span class="sxs-lookup"><span data-stu-id="4fc49-112">Compressing Backups Using a Session with Limited CPU</span></span>](#creating_compressed_backup)  
  
##  <a name="setting-up-a-login-and-user-for-low-priority-operations"></a><a name="setup_login_and_user"></a> <span data-ttu-id="4fc49-113">Создание учетной записи и пользователя для операций с низким приоритетом</span><span class="sxs-lookup"><span data-stu-id="4fc49-113">Setting Up a Login and User for Low-Priority Operations</span></span>  
 <span data-ttu-id="4fc49-114">Для сценария в этом разделе требуется низкоприоритетное имя входа в систему [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и пользователь.</span><span class="sxs-lookup"><span data-stu-id="4fc49-114">The scenario in this topic requires a low-priority [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and user.</span></span> <span data-ttu-id="4fc49-115">Имя пользователя будет использоваться для классификации сеансов, запущенных в процессе входа, и для направления их в группу рабочей нагрузки регулятора ресурсов, которая ограничивает загрузку ЦП.</span><span class="sxs-lookup"><span data-stu-id="4fc49-115">The user name will be used to classify sessions running in the login and route them to a Resource Governor workload group that limits CPU usage.</span></span>  
  
 <span data-ttu-id="4fc49-116">Ниже описываются этапы настройки имени входа и пользователя для этой цели, за которыми следует пример на языке [!INCLUDE[tsql](../../includes/tsql-md.md)]: "Пример А. Настройка имени входа и пользователя (Transact-SQL)".</span><span class="sxs-lookup"><span data-stu-id="4fc49-116">The following procedure describes the steps for setting up a login and user for this purpose, followed by a [!INCLUDE[tsql](../../includes/tsql-md.md)] example, "Example A: Setting Up a Login and User (Transact-SQL)."</span></span>  
  
### <a name="to-set-up-a-login-and-database-user-for-classifying-sessions"></a><span data-ttu-id="4fc49-117">Настройка имени входа и пользователя базы данных для классификации сеансов</span><span class="sxs-lookup"><span data-stu-id="4fc49-117">To set up a login and database user for classifying sessions</span></span>  
  
1.  <span data-ttu-id="4fc49-118">Создайте имя входа на [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для создания низкоприоритетных сжатых резервных копий.</span><span class="sxs-lookup"><span data-stu-id="4fc49-118">Create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login for creating low-priority compressed backups.</span></span>  
  
     <span data-ttu-id="4fc49-119">**Создание имени входа**</span><span class="sxs-lookup"><span data-stu-id="4fc49-119">**To create a login**</span></span>  
  
    -   [<span data-ttu-id="4fc49-120">Создание имени входа</span><span class="sxs-lookup"><span data-stu-id="4fc49-120">Create a Login</span></span>](../security/authentication-access/create-a-login.md)  
  
    -   [<span data-ttu-id="4fc49-121">CREATE LOGIN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4fc49-121">CREATE LOGIN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-login-transact-sql)  
  
2.  <span data-ttu-id="4fc49-122">При необходимости можно также предоставить этому имени входа разрешение VIEW SERVER STATE.</span><span class="sxs-lookup"><span data-stu-id="4fc49-122">Optionally, grant VIEW SERVER STATE to this login.</span></span>  
  
    -   [<span data-ttu-id="4fc49-123">GRANT, предоставление разрешения на системный объект (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4fc49-123">GRANT System Object Permissions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/grant-system-object-permissions-transact-sql)  
  
     <span data-ttu-id="4fc49-124">Дополнительные сведения см. в разделе [GRANT, предоставление разрешений на участника базы данных (Transact-SQL)](/sql/t-sql/statements/grant-database-principal-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4fc49-124">For more information, see [GRANT Database Principal Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-principal-permissions-transact-sql).</span></span>  
  
3.  <span data-ttu-id="4fc49-125">Создайте пользователя [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для данного имени входа.</span><span class="sxs-lookup"><span data-stu-id="4fc49-125">Create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user for this login.</span></span>  
  
     <span data-ttu-id="4fc49-126">**Создание пользователя**</span><span class="sxs-lookup"><span data-stu-id="4fc49-126">**To create a user**</span></span>  
  
    -   [<span data-ttu-id="4fc49-127">Создание пользователя базы данных</span><span class="sxs-lookup"><span data-stu-id="4fc49-127">Create a Database User</span></span>](../security/authentication-access/create-a-database-user.md)  
  
    -   [<span data-ttu-id="4fc49-128">CREATE USER (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4fc49-128">CREATE USER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-user-transact-sql)  
  
4.  <span data-ttu-id="4fc49-129">Чтобы разрешить для сеансов данного имени входа и пользователя резервное копирование заданной базы данных, добавьте пользователя к роли db_backupoperator для этой базы данных.</span><span class="sxs-lookup"><span data-stu-id="4fc49-129">To enable sessions of this login and user to back up a given database, add the user to the db_backupoperator database role of that database.</span></span> <span data-ttu-id="4fc49-130">Выполните это для каждой из баз данных, резервные копии которых должен создать данный пользователь.</span><span class="sxs-lookup"><span data-stu-id="4fc49-130">Do this for each database that this user will back up.</span></span> <span data-ttu-id="4fc49-131">При необходимости добавьте пользователя к другим предопределенным ролям баз данных.</span><span class="sxs-lookup"><span data-stu-id="4fc49-131">Optionally, add the user to other fixed database roles.</span></span>  
  
     <span data-ttu-id="4fc49-132">**Добавление пользователя к предопределенной роли базы данных**</span><span class="sxs-lookup"><span data-stu-id="4fc49-132">**To add a user to a fixed database role**</span></span>  
  
    -   [<span data-ttu-id="4fc49-133">sp_addrolemember &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4fc49-133">sp_addrolemember &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addrolemember-transact-sql)  
  
     <span data-ttu-id="4fc49-134">Дополнительные сведения см. в разделе [GRANT, предоставление разрешений на участника базы данных (Transact-SQL)](/sql/t-sql/statements/grant-database-principal-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4fc49-134">For more information, see [GRANT Database Principal Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-principal-permissions-transact-sql).</span></span>  
  
### <a name="example-a-setting-up-a-login-and-user-transact-sql"></a><span data-ttu-id="4fc49-135">Пример А. Настройка имени входа и пользователя (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4fc49-135">Example A: Setting Up a Login and User (Transact-SQL)</span></span>  
 <span data-ttu-id="4fc49-136">Следующий пример касается только случая, когда выбрано создание нового имени входа и пользователя [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для низкоприоритетных резервных копий.</span><span class="sxs-lookup"><span data-stu-id="4fc49-136">The following example is relevant only if you choose to create a new [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and user for low-priority backups.</span></span> <span data-ttu-id="4fc49-137">В качестве альтернативы можно использовать существующие имя входа и пользователя, если таковой существует.</span><span class="sxs-lookup"><span data-stu-id="4fc49-137">Alternatively, you can use an existing login and user, if an appropriate one exists.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4fc49-138">В приведенном ниже примере используется образец имени для входа и пользователя — *имя_домена*`\MAX_CPU`.</span><span class="sxs-lookup"><span data-stu-id="4fc49-138">The following example uses a sample login and user name, *domain_name*`\MAX_CPU`.</span></span> <span data-ttu-id="4fc49-139">Замените их именами входа и пользователя [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , которые планируется использовать при создании низкоприоритетных сжатых резервных копий.</span><span class="sxs-lookup"><span data-stu-id="4fc49-139">Replace these with the names of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and user that you plan to use when creating your low-priority compressed backups.</span></span>  
  
 <span data-ttu-id="4fc49-140">В этом примере создается имя для входа для учетной записи Windows *имя_домена*`\MAX_CPU` , а затем этому имени для входа предоставляется разрешение VIEW SERVER STATE.</span><span class="sxs-lookup"><span data-stu-id="4fc49-140">This example creates a login for the *domain_name*`\MAX_CPU` Windows account and then grants VIEW SERVER STATE permission to the login.</span></span> <span data-ttu-id="4fc49-141">Это разрешение позволяет проверить классификацию сеансов имени входа в регуляторе ресурсов.</span><span class="sxs-lookup"><span data-stu-id="4fc49-141">This permission enables you to verify the Resource Governor classification of sessions of the login.</span></span> <span data-ttu-id="4fc49-142">Затем для имени *имя_домена*`\MAX_CPU` создается пользователь и добавляется к предопределенной роли db_backupoperator для образца базы данных [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4fc49-142">The example then creates a user for *domain_name*`\MAX_CPU` and adds it to the db_backupoperator fixed database role for the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] sample database.</span></span> <span data-ttu-id="4fc49-143">Это имя пользователя будет использоваться функцией-классификатором в регуляторе ресурсов.</span><span class="sxs-lookup"><span data-stu-id="4fc49-143">This user name will be used by the Resource Governor classifier function.</span></span>  
  
```sql  
-- Create a SQL Server login for low-priority operations  
USE master;  
CREATE LOGIN [domain_name\MAX_CPU] FROM WINDOWS;  
GRANT VIEW SERVER STATE TO [domain_name\MAX_CPU];  
GO  
-- Create a SQL Server user in AdventureWorks2012 for this login  
USE AdventureWorks2012;  
CREATE USER [domain_name\MAX_CPU] FOR LOGIN [domain_name\MAX_CPU];  
EXEC sp_addrolemember 'db_backupoperator', 'domain_name\MAX_CPU';  
GO  
  
```  
  
 [<span data-ttu-id="4fc49-144">&#91;В начало&#93;</span><span class="sxs-lookup"><span data-stu-id="4fc49-144">&#91;Top&#93;</span></span>](#Top)  
  
##  <a name="configuring-resource-governor-to-limit-cpu-usage"></a><a name="configure_RG"></a> <span data-ttu-id="4fc49-145">Настройка регулятора ресурсов для ограничения загрузки ЦП</span><span class="sxs-lookup"><span data-stu-id="4fc49-145">Configuring Resource Governor to Limit CPU Usage</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4fc49-146">Убедитесь, что регулятор ресурсов включен.</span><span class="sxs-lookup"><span data-stu-id="4fc49-146">Ensure that Resource Governor is enabled.</span></span> <span data-ttu-id="4fc49-147">Дополнительные сведения см. в разделе [Активация регулятора ресурсов](../resource-governor/enable-resource-governor.md).</span><span class="sxs-lookup"><span data-stu-id="4fc49-147">For more information, see [Enable Resource Governor](../resource-governor/enable-resource-governor.md).</span></span>  
  
 <span data-ttu-id="4fc49-148">В этом сценарии регулятора ресурсов процесс настройки состоит из следующих основных этапов.</span><span class="sxs-lookup"><span data-stu-id="4fc49-148">In this Resource Governor scenario, configuration comprises the following basic steps:</span></span>  
  
1.  <span data-ttu-id="4fc49-149">Создайте и настройте для регулятора ресурсов пул ресурсов, который ограничивает максимальную среднюю пропускную способность ЦП, предоставляемую запросам из пула ресурсов в случае состязания из-за ЦП.</span><span class="sxs-lookup"><span data-stu-id="4fc49-149">Create and configure a Resource Governor resource pool that limits the maximum average CPU bandwidth that will be given to requests in the resource pool when CPU contention occurs.</span></span>  
  
2.  <span data-ttu-id="4fc49-150">Создайте и настройте группу рабочей нагрузки регулятора ресурсов, которая будет использовать этот пул.</span><span class="sxs-lookup"><span data-stu-id="4fc49-150">Create and configure a Resource Governor workload group that uses this pool.</span></span>  
  
3.  <span data-ttu-id="4fc49-151">Создайте *функцию-классификатор*— определяемую пользователем функцию, возвращаемые значения которой используются регулятором Resource Governor для классификации сеансов с целью направления в соответствующую группу рабочей нагрузки.</span><span class="sxs-lookup"><span data-stu-id="4fc49-151">Create a *classifier function*, which is a user-defined function (UDF) whose return values are used by Resource Governor for classifying sessions so that they are routed to the appropriate workload group.</span></span>  
  
4.  <span data-ttu-id="4fc49-152">Зарегистрируйте эту функцию-классификатор в регуляторе ресурсов.</span><span class="sxs-lookup"><span data-stu-id="4fc49-152">Register the classifier function with Resource Governor.</span></span>  
  
5.  <span data-ttu-id="4fc49-153">Примените изменения в хранящейся в памяти конфигурации регулятора ресурсов.</span><span class="sxs-lookup"><span data-stu-id="4fc49-153">Apply the changes to the Resource Governor in-memory configuration.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4fc49-154">Сведения о пулах ресурсов Resource Governor, группах рабочей нагрузки и классификации см. в разделе [Resource Governor](../resource-governor/resource-governor.md).</span><span class="sxs-lookup"><span data-stu-id="4fc49-154">For information about Resource Governor resource pools, workload groups, and classification, see [Resource Governor](../resource-governor/resource-governor.md).</span></span>  
  
 <span data-ttu-id="4fc49-155">Инструкции языка [!INCLUDE[tsql](../../includes/tsql-md.md)] для указанных этапов описаны в процедуре «Настройка регулятора ресурсов для ограничения загрузки ЦП», за которой следует пример процедуры на языке [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4fc49-155">The [!INCLUDE[tsql](../../includes/tsql-md.md)] statements for these steps are described in the procedure, "To configure Resource Governor for limiting CPU usage," which is followed by a [!INCLUDE[tsql](../../includes/tsql-md.md)] example of the procedure.</span></span>  
  
 <span data-ttu-id="4fc49-156">**Настройка регулятора ресурсов (среда SQL Server Management Studio)**</span><span class="sxs-lookup"><span data-stu-id="4fc49-156">**To configure Resource Governor (SQL Server Management Studio)**</span></span>  
  
-   [<span data-ttu-id="4fc49-157">Настройка регулятора ресурсов с помощью шаблона</span><span class="sxs-lookup"><span data-stu-id="4fc49-157">Configure Resource Governor Using a Template</span></span>](../resource-governor/configure-resource-governor-using-a-template.md)  
  
-   [<span data-ttu-id="4fc49-158">Создание пула ресурсов</span><span class="sxs-lookup"><span data-stu-id="4fc49-158">Create a Resource Pool</span></span>](../resource-governor/create-a-resource-pool.md)  
  
-   [<span data-ttu-id="4fc49-159">Создание группы рабочей нагрузки</span><span class="sxs-lookup"><span data-stu-id="4fc49-159">Create a Workload Group</span></span>](../resource-governor/create-a-workload-group.md)  
  
### <a name="to-configure-resource-governor-for-limiting-cpu-usage-transact-sql"></a><span data-ttu-id="4fc49-160">Настройка регулятора ресурсов для ограничения загрузки ЦП (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4fc49-160">To configure Resource Governor for limiting CPU usage (Transact-SQL)</span></span>  
  
1.  <span data-ttu-id="4fc49-161">Выполните инструкцию [CREATE RESOURCE POOL](/sql/t-sql/statements/create-resource-pool-transact-sql) , чтобы создать пул ресурсов.</span><span class="sxs-lookup"><span data-stu-id="4fc49-161">Issue a [CREATE RESOURCE POOL](/sql/t-sql/statements/create-resource-pool-transact-sql) statement to create a resource pool.</span></span> <span data-ttu-id="4fc49-162">В примере этой процедуры используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="4fc49-162">The example for this procedure uses the following syntax:</span></span>  
  
     <span data-ttu-id="4fc49-163">*CREATE RESOURCE POOL имя_пула* WITH ( MAX_CPU_PERCENT = *значение* );</span><span class="sxs-lookup"><span data-stu-id="4fc49-163">*CREATE RESOURCE POOL pool_name* WITH ( MAX_CPU_PERCENT = *value* );</span></span>  
  
     <span data-ttu-id="4fc49-164">*Value* — целое число от 1 до 100, которое указывает максимальную среднюю пропускную способность ЦП в процентах.</span><span class="sxs-lookup"><span data-stu-id="4fc49-164">*Value* is an integer from 1 to 100 that indicates the percentage of maximum average CPU bandwidth.</span></span> <span data-ttu-id="4fc49-165">Рекомендуемое значение зависит от конкретной среды.</span><span class="sxs-lookup"><span data-stu-id="4fc49-165">The appropriate value depends on your environment.</span></span> <span data-ttu-id="4fc49-166">Для иллюстрации в примере из этого разделе используется значение 20% (MAX_CPU_PERCENT = 20).</span><span class="sxs-lookup"><span data-stu-id="4fc49-166">For the purpose of illustration, the example in this topic uses 20%  percent (MAX_CPU_PERCENT = 20.)</span></span>  
  
2.  <span data-ttu-id="4fc49-167">Выполните инструкцию [CREATE WORKLOAD GROUP](/sql/t-sql/statements/create-workload-group-transact-sql) , чтобы создать группу рабочей нагрузки для низкоприоритетных операций, загрузку ЦП которыми следует регулировать.</span><span class="sxs-lookup"><span data-stu-id="4fc49-167">Issue a [CREATE WORKLOAD GROUP](/sql/t-sql/statements/create-workload-group-transact-sql) statement to create a workload group for low-priority operations whose CPU usage you want to govern.</span></span> <span data-ttu-id="4fc49-168">В примере этой процедуры используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="4fc49-168">The example for this procedure uses the following syntax:</span></span>  
  
     <span data-ttu-id="4fc49-169">CREATE WORKLOAD GROUP *имя_группы* USING *имя_пула*;</span><span class="sxs-lookup"><span data-stu-id="4fc49-169">CREATE WORKLOAD GROUP *group_name* USING *pool_name*;</span></span>  
  
3.  <span data-ttu-id="4fc49-170">Выполните инструкцию [CREATE FUNCTION](/sql/t-sql/statements/create-function-transact-sql) , чтобы создать функцию-классификатор, сопоставляющую созданную на предыдущем этапе группу рабочей нагрузки с пользователем с низкоприоритетным именем входа.</span><span class="sxs-lookup"><span data-stu-id="4fc49-170">Issue a [CREATE FUNCTION](/sql/t-sql/statements/create-function-transact-sql) statement to create a classifier function that maps the workload group created in the preceding step to the user of the low-priority login.</span></span> <span data-ttu-id="4fc49-171">В примере этой процедуры используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="4fc49-171">The example for this procedure uses the following syntax:</span></span>  
  
     <span data-ttu-id="4fc49-172">CREATE FUNCTION [*имя_схемы*.]*имя_функции*() RETURNS sysname</span><span class="sxs-lookup"><span data-stu-id="4fc49-172">CREATE FUNCTION [*schema_name*.]*function_name*() RETURNS sysname</span></span>  
  
     <span data-ttu-id="4fc49-173">WITH SCHEMABINDING</span><span class="sxs-lookup"><span data-stu-id="4fc49-173">WITH SCHEMABINDING</span></span>  
  
     <span data-ttu-id="4fc49-174">AS</span><span class="sxs-lookup"><span data-stu-id="4fc49-174">AS</span></span>  
  
     <span data-ttu-id="4fc49-175">BEGIN</span><span class="sxs-lookup"><span data-stu-id="4fc49-175">BEGIN</span></span>  
  
     <span data-ttu-id="4fc49-176">DECLARE @workload_group_name AS *sysname*</span><span class="sxs-lookup"><span data-stu-id="4fc49-176">DECLARE @workload_group_name AS *sysname*</span></span>  
  
     <span data-ttu-id="4fc49-177">IF (SUSER_NAME() = '*пользователь_с_низкоприоритетным_именем_входа*')</span><span class="sxs-lookup"><span data-stu-id="4fc49-177">IF (SUSER_NAME() = '*user_of_low_priority_login*')</span></span>  
  
     <span data-ttu-id="4fc49-178">SET @workload_group_name = '*workload_group_name*'</span><span class="sxs-lookup"><span data-stu-id="4fc49-178">SET @workload_group_name = '*workload_group_name*'</span></span>  
  
     <span data-ttu-id="4fc49-179">RETURN @workload_group_name</span><span class="sxs-lookup"><span data-stu-id="4fc49-179">RETURN @workload_group_name</span></span>  
  
     <span data-ttu-id="4fc49-180">END</span><span class="sxs-lookup"><span data-stu-id="4fc49-180">END</span></span>  
  
     <span data-ttu-id="4fc49-181">Дополнительные сведения о компонентах этой инструкции CREATE FUNCTION см. в разделах:</span><span class="sxs-lookup"><span data-stu-id="4fc49-181">For information about the components of this CREATE FUNCTION statement, see:</span></span>  
  
    -   [<span data-ttu-id="4fc49-182">DECLARE @local_variable &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4fc49-182">DECLARE @local_variable &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/declare-local-variable-transact-sql)  
  
    -   [<span data-ttu-id="4fc49-183">SUSER_SNAME (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4fc49-183">SUSER_SNAME &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/suser-sname-transact-sql)  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="4fc49-184">SUSER_NAME — лишь одна из нескольких системных функций, которые можно использовать в функции-классификаторе.</span><span class="sxs-lookup"><span data-stu-id="4fc49-184">SUSER_NAME is just one of several system functions that can be used in a classifier function.</span></span> <span data-ttu-id="4fc49-185">Дополнительные сведения см. в разделе [Создание и проверка определяемой пользователем функции-классификатора](../resource-governor/create-and-test-a-classifier-user-defined-function.md).</span><span class="sxs-lookup"><span data-stu-id="4fc49-185">For more information, see [Create and Test a Classifier User-Defined Function](../resource-governor/create-and-test-a-classifier-user-defined-function.md).</span></span>  
  
    -   <span data-ttu-id="4fc49-186">[SET @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/set-local-variable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4fc49-186">[SET @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/set-local-variable-transact-sql).</span></span>  
  
4.  <span data-ttu-id="4fc49-187">Выполните инструкцию [ALTER RESOURCE GOVERNOR](/sql/t-sql/statements/alter-resource-governor-transact-sql) , чтобы зарегистрировать функцию-классификатор в регуляторе ресурсов.</span><span class="sxs-lookup"><span data-stu-id="4fc49-187">Issue an [ALTER RESOURCE GOVERNOR](/sql/t-sql/statements/alter-resource-governor-transact-sql) statement to register the classifier function with Resource Governor.</span></span> <span data-ttu-id="4fc49-188">В примере этой процедуры используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="4fc49-188">The example for this procedure uses the following syntax:</span></span>  
  
     <span data-ttu-id="4fc49-189">ALTER RESOURCE GOVERNOR WITH (CLASSIFIER_FUNCTION = *имя_схемы*.*имя_функции*);</span><span class="sxs-lookup"><span data-stu-id="4fc49-189">ALTER RESOURCE GOVERNOR WITH (CLASSIFIER_FUNCTION = *schema_name*.*function_name*);</span></span>  
  
5.  <span data-ttu-id="4fc49-190">Выполните еще одну инструкцию ALTER RESOURCE GOVERNOR, чтобы применить изменения в хранящейся в памяти конфигурации регулятора ресурсов, как указано ниже:</span><span class="sxs-lookup"><span data-stu-id="4fc49-190">Issue a second ALTER RESOURCE GOVERNOR statement to apply the changes to the Resource Governor in-memory configuration, as follows:</span></span>  
  
    ```  
    ALTER RESOURCE GOVERNOR RECONFIGURE;  
    ```  
  
### <a name="example-b-configuring-resource-governor-transact-sql"></a><span data-ttu-id="4fc49-191">Пример Б. Настройка Resource Governor (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4fc49-191">Example B: Configuring Resource Governor (Transact-SQL)</span></span>  
 <span data-ttu-id="4fc49-192">В нижеприведенном примере в одной транзакции выполняются следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="4fc49-192">The following example performs the following steps within a single transaction:</span></span>  
  
1.  <span data-ttu-id="4fc49-193">Создание пула ресурсов `pMAX_CPU_PERCENT_20` .</span><span class="sxs-lookup"><span data-stu-id="4fc49-193">Creates the `pMAX_CPU_PERCENT_20` resource pool.</span></span>  
  
2.  <span data-ttu-id="4fc49-194">Создание группы рабочей нагрузки `gMAX_CPU_PERCENT_20` .</span><span class="sxs-lookup"><span data-stu-id="4fc49-194">Creates the `gMAX_CPU_PERCENT_20` workload group.</span></span>  
  
3.  <span data-ttu-id="4fc49-195">Создание функции-классификатора `rgclassifier_MAX_CPU()` , в которой используется имя пользователя, созданное в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="4fc49-195">Creates the `rgclassifier_MAX_CPU()` classifier function, which uses the user name created in the preceding example.</span></span>  
  
4.  <span data-ttu-id="4fc49-196">Регистрация функции-классификатора в регуляторе ресурсов.</span><span class="sxs-lookup"><span data-stu-id="4fc49-196">Registers the classifier function with Resource Governor.</span></span>  
  
 <span data-ttu-id="4fc49-197">После того как транзакция зафиксирована, применяются изменения в конфигурации, запрошенные в инструкциях ALTER WORKLOAD GROUP или ALTER RESOURCE POOL.</span><span class="sxs-lookup"><span data-stu-id="4fc49-197">After committing the transaction, the example applies the configuration changes requested in the ALTER WORKLOAD GROUP or ALTER RESOURCE POOL statements.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4fc49-198">В следующем примере используется образец имени пользователя [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], созданный в разделе "Пример А. Настройка имени входа и пользователя (Transact-SQL)", — *domain_name*`\MAX_CPU`.</span><span class="sxs-lookup"><span data-stu-id="4fc49-198">The following example uses the user name of the sample [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user created in "Example A: Setting Up a Login and User (Transact-SQL)," *domain_name*`\MAX_CPU`.</span></span> <span data-ttu-id="4fc49-199">Замените его именем пользователя, соответствующего имени входа, которое планируется использовать для создания низкоприоритетных сжатых резервных копий.</span><span class="sxs-lookup"><span data-stu-id="4fc49-199">Replace this with the name of the user of the login that you plan to use for creating low-priority compressed backups.</span></span>  
  
```sql  
-- Configure Resource Governor.  
BEGIN TRAN  
USE master;  
-- Create a resource pool that sets the MAX_CPU_PERCENT to 20%.   
CREATE RESOURCE POOL pMAX_CPU_PERCENT_20  
   WITH  
      (MAX_CPU_PERCENT = 20);  
GO  
-- Create a workload group to use this pool.   
CREATE WORKLOAD GROUP gMAX_CPU_PERCENT_20  
USING pMAX_CPU_PERCENT_20;  
GO  
-- Create a classification function.  
-- Note that any request that does not get classified goes into   
-- the 'Default' group.  
CREATE FUNCTION dbo.rgclassifier_MAX_CPU() RETURNS sysname   
WITH SCHEMABINDING  
AS  
BEGIN  
    DECLARE @workload_group_name AS sysname  
      IF (SUSER_NAME() = 'domain_name\MAX_CPU')  
          SET @workload_group_name = 'gMAX_CPU_PERCENT_20'  
    RETURN @workload_group_name  
END;  
GO  
  
-- Register the classifier function with Resource Governor.  
ALTER RESOURCE GOVERNOR WITH (CLASSIFIER_FUNCTION= dbo.rgclassifier_MAX_CPU);  
COMMIT TRAN;  
GO  
-- Start Resource Governor  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
  
```  
  
 [<span data-ttu-id="4fc49-200">&#91;В начало&#93;</span><span class="sxs-lookup"><span data-stu-id="4fc49-200">&#91;Top&#93;</span></span>](#Top)  
  
##  <a name="verifying-the-classification-of-the-current-session-transact-sql"></a><a name="verifying"></a> <span data-ttu-id="4fc49-201">Проверка классификации текущего сеанса (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4fc49-201">Verifying the Classification of the Current Session (Transact-SQL)</span></span>  
 <span data-ttu-id="4fc49-202">При необходимости войдите в систему как пользователь, указанный в функции-классификаторе, и проверьте классификацию сеанса, выполнив следующую инструкцию [SELECT](/sql/t-sql/queries/select-transact-sql) в обозревателе объектов:</span><span class="sxs-lookup"><span data-stu-id="4fc49-202">Optionally, log in as the user that you specified in your classifier function, and verify the session classification by issuing the following [SELECT](/sql/t-sql/queries/select-transact-sql) statement in Object Explorer:</span></span>  
  
```sql  
USE master;  
SELECT sess.session_id, sess.login_name, sess.group_id, grps.name   
FROM sys.dm_exec_sessions AS sess   
JOIN sys.dm_resource_governor_workload_groups AS grps   
    ON sess.group_id = grps.group_id  
WHERE session_id > 50;  
GO  
```  
  
 <span data-ttu-id="4fc49-203">В области результатов столбец **name** должен содержать один или несколько сеансов для имени группы рабочей нагрузки, указанного в функции-классификаторе.</span><span class="sxs-lookup"><span data-stu-id="4fc49-203">In the results pane, the **name** column should list one or more sessions for the workload-group name that you specified in your classifier function.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4fc49-204">Дополнительные сведения о динамических административных представлениях, вызываемых этой инструкцией SELECT, см. в разделах [sys.dm_exec_sessions (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) и [sys.dm_resource_governor_workload_groups (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-workload-groups-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4fc49-204">For information about the dynamic management views called by this SELECT statement, see [sys.dm_exec_sessions &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) and [sys.dm_resource_governor_workload_groups &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-workload-groups-transact-sql).</span></span>  
  
 [<span data-ttu-id="4fc49-205">&#91;В начало&#93;</span><span class="sxs-lookup"><span data-stu-id="4fc49-205">&#91;Top&#93;</span></span>](#Top)  
  
##  <a name="compressing-backups-using-a-session-with-limited-cpu"></a><a name="creating_compressed_backup"></a> <span data-ttu-id="4fc49-206">Сжатие резервных копий в сеансе с ограничением доступа к ЦП</span><span class="sxs-lookup"><span data-stu-id="4fc49-206">Compressing Backups Using a Session with Limited CPU</span></span>  
 <span data-ttu-id="4fc49-207">Чтобы создать сжатую резервную копию в сеансе с ограниченной максимальной загрузкой ЦП, войдите в систему как пользователь, указанный в функции-классификаторе.</span><span class="sxs-lookup"><span data-stu-id="4fc49-207">To create a compressed backup in a session with a limited maximum CPU, log in as the user specified in your classifier function.</span></span> <span data-ttu-id="4fc49-208">В команде Backup укажите с помощью СЖАТИЯ ( [!INCLUDE[tsql](../../includes/tsql-md.md)] ) или выберите **Сжимать резервные копии** ( [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="4fc49-208">In your backup command, either specify WITH COMPRESSION ([!INCLUDE[tsql](../../includes/tsql-md.md)]) or select **Compress backup** ([!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]).</span></span> <span data-ttu-id="4fc49-209">Сведения о создании сжатой резервной копии базы данных см. в разделе [Создание полной резервной копии базы данных (SQL Server)](create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4fc49-209">To create a compressed database backup, see [Create a Full Database Backup &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span></span>  
  
### <a name="example-c-creating-a-compressed-backup-transact-sql"></a><span data-ttu-id="4fc49-210">Пример В. Создание сжатой резервной копии (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4fc49-210">Example C: Creating a Compressed Backup (Transact-SQL)</span></span>  
 <span data-ttu-id="4fc49-211">В следующем примере [BACKUP](/sql/t-sql/statements/backup-transact-sql) создается сжатая полная резервная копия базы данных [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] в чистом форматированном файле резервной копии `Z:\SQLServerBackups\AdvWorksData.bak`.</span><span class="sxs-lookup"><span data-stu-id="4fc49-211">The following [BACKUP](/sql/t-sql/statements/backup-transact-sql) example creates a compressed full backup of the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database in a newly formatted backup file, `Z:\SQLServerBackups\AdvWorksData.bak`.</span></span>  
  
```sql  
--Run backup statement in the gBackup session.  
BACKUP DATABASE AdventureWorks2012 TO DISK='Z:\SQLServerBackups\AdvWorksData.bak'   
WITH   
   FORMAT,   
   MEDIADESCRIPTION='AdventureWorks2012 Compressed Data Backups'  
   DESCRIPTION='First database backup on AdventureWorks2012 Compressed Data Backups media set'  
   COMPRESSION;  
GO  
```  
  
 [<span data-ttu-id="4fc49-212">&#91;В начало&#93;</span><span class="sxs-lookup"><span data-stu-id="4fc49-212">&#91;Top&#93;</span></span>](#Top)  
  
## <a name="see-also"></a><span data-ttu-id="4fc49-213">См. также:</span><span class="sxs-lookup"><span data-stu-id="4fc49-213">See Also</span></span>  
 <span data-ttu-id="4fc49-214">[Создание и проверка определяемой пользователем функции-классификатора](../resource-governor/create-and-test-a-classifier-user-defined-function.md) </span><span class="sxs-lookup"><span data-stu-id="4fc49-214">[Create and Test a Classifier User-Defined Function](../resource-governor/create-and-test-a-classifier-user-defined-function.md) </span></span>  
 [<span data-ttu-id="4fc49-215">Регулятор ресурсов</span><span class="sxs-lookup"><span data-stu-id="4fc49-215">Resource Governor</span></span>](../resource-governor/resource-governor.md)  
  
  
