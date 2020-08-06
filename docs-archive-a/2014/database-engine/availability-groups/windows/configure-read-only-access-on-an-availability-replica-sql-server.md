---
title: Настройка доступа только для чтения в реплике доступности (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 10/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- connection access to availability replicas
- Availability Groups [SQL Server], readable secondary replicas
- active secondary replicas [SQL Server], read-only access to
- Availability Groups [SQL Server], read-only routing
- Availability Groups [SQL Server], client connectivity
ms.assetid: 22387419-22c4-43fa-851c-5fecec4b049b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ab13081396aff46d193c1b0449d6b93042ee60d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729833"
---
# <a name="configure-read-only-access-on-an-availability-replica-sql-server"></a><span data-ttu-id="adc94-102">Настройка доступа только для чтения в реплике доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="adc94-102">Configure Read-Only Access on an Availability Replica (SQL Server)</span></span>
  <span data-ttu-id="adc94-103">По умолчанию и доступ для чтения и записи, и доступ только для чтения разрешены в первичной реплике, а подключения к вторичным репликам группы доступности AlwaysOn запрещены.</span><span class="sxs-lookup"><span data-stu-id="adc94-103">By default both read-write and read-intent access are allowed to the primary replica and no connections are allowed to secondary replicas of an AlwaysOn availability group.</span></span> <span data-ttu-id="adc94-104">В этом разделе описывается настройка доступа к соединениям реплики доступности в группе доступности AlwaysOn в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="adc94-104">This topic describes how to configure connection access on an availability replica of an AlwaysOn availability group in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell.</span></span>  
  
 <span data-ttu-id="adc94-105">Сведения о последствиях включения доступа только для чтения во вторичной реплике и обзор доступа к соединениям см. в статьях [Сведения о доступе клиентского подключения к репликам доступности (SQL Server)](about-client-connection-access-to-availability-replicas-sql-server.md) и [Активные вторичные реплики: вторичные реплики для чтения (группы доступности AlwaysOn)](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="adc94-105">For information about the implications of enabling read-only access for a secondary replica and for an introduction to connection access, see [About Client Connection Access to Availability Replicas &#40;SQL Server&#41;](about-client-connection-access-to-availability-replicas-sql-server.md) and [Active Secondaries: Readable Secondary Replicas &#40;AlwaysOn Availability Groups&#41;](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md).</span></span>  
  
  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="adc94-106">Перед началом</span><span class="sxs-lookup"><span data-stu-id="adc94-106">Before You Begin</span></span>  
  
###  <a name="prerequisites-and-restrictions"></a><a name="Prerequisites"></a> <span data-ttu-id="adc94-107">Требования и ограничения</span><span class="sxs-lookup"><span data-stu-id="adc94-107">Prerequisites and Restrictions</span></span>  
  
-   <span data-ttu-id="adc94-108">Если нужно настроить разный доступ к подключениям, необходимо подключиться к экземпляру сервера, на котором размещается первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="adc94-108">To configure different connection access, you must be connected to the server instance that hosts the primary replica.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="adc94-109">безопасность</span><span class="sxs-lookup"><span data-stu-id="adc94-109">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="adc94-110">Permissions</span><span class="sxs-lookup"><span data-stu-id="adc94-110">Permissions</span></span>  
  
|<span data-ttu-id="adc94-111">Задача</span><span class="sxs-lookup"><span data-stu-id="adc94-111">Task</span></span>|<span data-ttu-id="adc94-112">Разрешения</span><span class="sxs-lookup"><span data-stu-id="adc94-112">Permissions</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="adc94-113">Настройка реплик при создании группы доступности</span><span class="sxs-lookup"><span data-stu-id="adc94-113">To configure replicas when creating an availability group</span></span>|<span data-ttu-id="adc94-114">Требуется членство в фиксированной роли сервера **sysadmin** и одно из разрешений: CREATE AVAILABILITY GROUP, ALTER ANY AVAILABILITY GROUP или CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="adc94-114">Requires membership in the **sysadmin** fixed server role and either CREATE AVAILABILITY GROUP server permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>|  
|<span data-ttu-id="adc94-115">Изменение реплики доступности</span><span class="sxs-lookup"><span data-stu-id="adc94-115">To modify an availability replica</span></span>|<span data-ttu-id="adc94-116">Необходимо разрешение ALTER AVAILABILITY GROUP для группы доступности, разрешение CONTROL AVAILABILITY GROUP, разрешение ALTER ANY AVAILABILITY GROUP или разрешение CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="adc94-116">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>|  
  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="adc94-117">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="adc94-117">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="adc94-118">**Настройка доступа к реплике доступности**</span><span class="sxs-lookup"><span data-stu-id="adc94-118">**To configure access on an availability replica**</span></span>  
  
1.  <span data-ttu-id="adc94-119">В обозревателе объектов подключитесь к экземпляру сервера, на котором размещена первичная реплика, и разверните дерево сервера.</span><span class="sxs-lookup"><span data-stu-id="adc94-119">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="adc94-120">Разверните узел **Высокий уровень доступности AlwaysOn** и узел **Группы доступности** .</span><span class="sxs-lookup"><span data-stu-id="adc94-120">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="adc94-121">Щелкните группу доступности, реплику которой нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="adc94-121">Click the availability group whose replica you want to change.</span></span>  
  
4.  <span data-ttu-id="adc94-122">Щелкните правой кнопкой мыши реплику доступности и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="adc94-122">Right-click the availability replica, and click **Properties**.</span></span>  
  
5.  <span data-ttu-id="adc94-123">В диалоговом окне **Свойства реплики доступности** можно изменить доступ к соединению для первичной и вторичной роли следующим образом:</span><span class="sxs-lookup"><span data-stu-id="adc94-123">In the **Availability Replica Properties** dialog box, you can change the connection access for the primary role and for the secondary role, as follows:</span></span>  
  
    -   <span data-ttu-id="adc94-124">Для вторичной роли выберите новое значение в раскрывающемся списке **Доступная для чтения вторичная** следующим образом.</span><span class="sxs-lookup"><span data-stu-id="adc94-124">For the secondary role, select a new value from the **Readable secondary** drop list, as follows:</span></span>  
  
         <span data-ttu-id="adc94-125">**Нет**</span><span class="sxs-lookup"><span data-stu-id="adc94-125">**No**</span></span>  
         <span data-ttu-id="adc94-126">Для баз данных-получателей этой реплики соединения пользователя не разрешаются.</span><span class="sxs-lookup"><span data-stu-id="adc94-126">No user connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="adc94-127">Для них не разрешен доступ для чтения.</span><span class="sxs-lookup"><span data-stu-id="adc94-127">They are not available for read access.</span></span> <span data-ttu-id="adc94-128">Это параметр по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="adc94-128">This is the default setting.</span></span>  
  
         <span data-ttu-id="adc94-129">**Назначение — только чтение**</span><span class="sxs-lookup"><span data-stu-id="adc94-129">**Read-intent only**</span></span>  
         <span data-ttu-id="adc94-130">Для баз данных-получателей этой реплики разрешены лишь подключения только для чтения.</span><span class="sxs-lookup"><span data-stu-id="adc94-130">Only read-only connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="adc94-131">Для всех баз данных-получателей разрешен доступ для чтения.</span><span class="sxs-lookup"><span data-stu-id="adc94-131">The secondary database(s) are all available for read access.</span></span>  
  
         <span data-ttu-id="adc94-132">**Да**</span><span class="sxs-lookup"><span data-stu-id="adc94-132">**Yes**</span></span>  
         <span data-ttu-id="adc94-133">Для баз данных-получателей этой реплики разрешены все соединения, но только с доступом для чтения.</span><span class="sxs-lookup"><span data-stu-id="adc94-133">All connections are allowed to secondary databases of this replica, but only for read access.</span></span> <span data-ttu-id="adc94-134">Для всех баз данных-получателей разрешен доступ для чтения.</span><span class="sxs-lookup"><span data-stu-id="adc94-134">The secondary database(s) are all available for read access.</span></span>  
  
    -   <span data-ttu-id="adc94-135">Для первичной роли выберите новое значение в раскрывающемся списке **Соединения в первичной роли** следующим образом:</span><span class="sxs-lookup"><span data-stu-id="adc94-135">For the primary role, select a new value from the **Connections in primary role** drop list, as follows:</span></span>  
  
         <span data-ttu-id="adc94-136">**разрешить все соединения.**</span><span class="sxs-lookup"><span data-stu-id="adc94-136">**Allow all connections**</span></span>  
         <span data-ttu-id="adc94-137">Разрешаются все соединения с базами данных в первичной реплике.</span><span class="sxs-lookup"><span data-stu-id="adc94-137">All connections are allowed to the databases in the primary replica.</span></span> <span data-ttu-id="adc94-138">Это параметр по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="adc94-138">This is the default setting.</span></span>  
  
         <span data-ttu-id="adc94-139">**разрешить соединения с доступом на чтение и запись;**</span><span class="sxs-lookup"><span data-stu-id="adc94-139">**Allow read/write connections**</span></span>  
         <span data-ttu-id="adc94-140">Если свойство «Назначение приложения» имеет значение **ReadWrite** или не задано, то соединение разрешено.</span><span class="sxs-lookup"><span data-stu-id="adc94-140">When the Application Intent property is set to **ReadWrite** or the Application Intent connection property is not set, the connection is allowed.</span></span> <span data-ttu-id="adc94-141">Соединения, у которых свойство соединения «Назначение приложения» равно **ReadOnly** , не разрешены.</span><span class="sxs-lookup"><span data-stu-id="adc94-141">Connections where the Application Intent connection property is set to **ReadOnly** are not allowed.</span></span> <span data-ttu-id="adc94-142">Таким образом, клиент не сможет по ошибке подключить рабочую нагрузку с намерением чтения к первичной реплике.</span><span class="sxs-lookup"><span data-stu-id="adc94-142">This can help prevent customers from connecting a read-intent work load to the primary replica by mistake.</span></span> <span data-ttu-id="adc94-143">Дополнительные сведения о свойстве соединения «Назначение приложения» см. в разделе [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="adc94-143">For more information about Application Intent connection property, see [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="adc94-144">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="adc94-144">Using Transact-SQL</span></span>  
 <span data-ttu-id="adc94-145">**Настройка доступа к реплике доступности**</span><span class="sxs-lookup"><span data-stu-id="adc94-145">**To configure access on an availability replica**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="adc94-146">Пример этой процедуры см. в подразделе [Примеры (Transact-SQL)](#TsqlExample)далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="adc94-146">For an example of this procedure, see [Example (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="adc94-147">Подключитесь к экземпляру сервера, на котором находится первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="adc94-147">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="adc94-148">Если вы указываете реплику для новой группы доступности, воспользуйтесь инструкцией [CREATE AVAILABILITY GROUP](/sql/t-sql/statements/create-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="adc94-148">If you are specifying a replica for a new availability group, use the [CREATE AVAILABILITY GROUP](/sql/t-sql/statements/create-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="adc94-149">Если вы добавляете или изменяете реплику существующей группы доступности, воспользуйтесь инструкцией [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="adc94-149">If you are adding or modifying a replica of an existing availability group, use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] statement.</span></span>  
  
    -   <span data-ttu-id="adc94-150">Чтобы настроить доступ к соединению для вторичной роли, укажите в предложении ADD REPLICA или MODIFY REPLICA WITH параметр SECONDARY_ROLE следующим образом:</span><span class="sxs-lookup"><span data-stu-id="adc94-150">To configure connection access for the secondary role, in the ADD REPLICA or MODIFY REPLICA WITH clause, specify the SECONDARY_ROLE option, as follows:</span></span>  
  
         <span data-ttu-id="adc94-151">SECONDARY_ROLE **(** ALLOW_CONNECTIONS **=** { NO | READ_ONLY | ALL } **)**</span><span class="sxs-lookup"><span data-stu-id="adc94-151">SECONDARY_ROLE **(** ALLOW_CONNECTIONS **=** { NO | READ_ONLY | ALL } **)**</span></span>  
  
         <span data-ttu-id="adc94-152">где</span><span class="sxs-lookup"><span data-stu-id="adc94-152">where,</span></span>  
  
         <span data-ttu-id="adc94-153">NO</span><span class="sxs-lookup"><span data-stu-id="adc94-153">NO</span></span>  
         <span data-ttu-id="adc94-154">Прямые подключения для баз данных-получателей этой реплики не разрешаются.</span><span class="sxs-lookup"><span data-stu-id="adc94-154">No direct connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="adc94-155">Для них не разрешен доступ для чтения.</span><span class="sxs-lookup"><span data-stu-id="adc94-155">They are not available for read access.</span></span> <span data-ttu-id="adc94-156">Это параметр по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="adc94-156">This is the default setting.</span></span>  
  
         <span data-ttu-id="adc94-157">READ_ONLY</span><span class="sxs-lookup"><span data-stu-id="adc94-157">READ_ONLY</span></span>  
         <span data-ttu-id="adc94-158">Для баз данных-получателей этой реплики разрешены лишь подключения только для чтения.</span><span class="sxs-lookup"><span data-stu-id="adc94-158">Only read-only connections are allowed to secondary databases of this replica.</span></span> <span data-ttu-id="adc94-159">Для всех баз данных-получателей разрешен доступ для чтения.</span><span class="sxs-lookup"><span data-stu-id="adc94-159">The secondary database(s) are all available for read access.</span></span>  
  
         <span data-ttu-id="adc94-160">ALL</span><span class="sxs-lookup"><span data-stu-id="adc94-160">ALL</span></span>  
         <span data-ttu-id="adc94-161">Для баз данных-получателей этой реплики разрешены все соединения, но только с доступом для чтения.</span><span class="sxs-lookup"><span data-stu-id="adc94-161">All connections are allowed to secondary databases of this replica, but only for read access.</span></span> <span data-ttu-id="adc94-162">Для всех баз данных-получателей разрешен доступ для чтения.</span><span class="sxs-lookup"><span data-stu-id="adc94-162">The secondary database(s) are all available for read access.</span></span>  
  
3.  <span data-ttu-id="adc94-163">Чтобы настроить доступ к соединению для первичной роли, укажите в предложении ADD REPLICA или MODIFY REPLICA WITH параметр PRIMARY_ROLE следующим образом:</span><span class="sxs-lookup"><span data-stu-id="adc94-163">To configure connection access for the primary role, in the ADD REPLICA or MODIFY REPLICA WITH clause, specify the PRIMARY_ROLE option, as follows:</span></span>  
  
     <span data-ttu-id="adc94-164">PRIMARY_ROLE **(** ALLOW_CONNECTIONS **=** { READ_WRITE | ALL } **)**</span><span class="sxs-lookup"><span data-stu-id="adc94-164">PRIMARY_ROLE **(** ALLOW_CONNECTIONS **=** { READ_WRITE | ALL } **)**</span></span>  
  
     <span data-ttu-id="adc94-165">где</span><span class="sxs-lookup"><span data-stu-id="adc94-165">where,</span></span>  
  
     <span data-ttu-id="adc94-166">READ_WRITE</span><span class="sxs-lookup"><span data-stu-id="adc94-166">READ_WRITE</span></span>  
     <span data-ttu-id="adc94-167">Соединения, у которых свойство "Назначение приложения" равно **ReadOnly** , не разрешены.</span><span class="sxs-lookup"><span data-stu-id="adc94-167">Connections where the Application Intent connection property is set to **ReadOnly** are disallowed.</span></span>  <span data-ttu-id="adc94-168">Если свойство «Назначение приложения» имеет значение **ReadWrite** или не задано, то соединение разрешено.</span><span class="sxs-lookup"><span data-stu-id="adc94-168">When the Application Intent property is set to **ReadWrite** or the Application Intent connection property is not set, the connection is allowed.</span></span> <span data-ttu-id="adc94-169">Дополнительные сведения о свойстве соединения «Назначение приложения» см. в разделе [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="adc94-169">For more information about Application Intent connection property, see [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
     <span data-ttu-id="adc94-170">ALL</span><span class="sxs-lookup"><span data-stu-id="adc94-170">ALL</span></span>  
     <span data-ttu-id="adc94-171">Разрешаются все соединения с базами данных в первичной реплике.</span><span class="sxs-lookup"><span data-stu-id="adc94-171">All connections are allowed to the databases in the primary replica.</span></span> <span data-ttu-id="adc94-172">Это параметр по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="adc94-172">This is the default setting.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="adc94-173">Примеры (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="adc94-173">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="adc94-174">В следующем примере вторичная реплика добавляется в группу доступности с именем *AG2*.</span><span class="sxs-lookup"><span data-stu-id="adc94-174">The following example adds a secondary replica to an availability group named *AG2*.</span></span> <span data-ttu-id="adc94-175">Для размещения новой реплики доступности указывается отдельный экземпляр сервера *COMPUTER03\HADR_INSTANCE*.</span><span class="sxs-lookup"><span data-stu-id="adc94-175">A stand-alone server instance, *COMPUTER03\HADR_INSTANCE*, is specified to host the new availability replica.</span></span> <span data-ttu-id="adc94-176">В этой реплике разрешены только соединения для чтения и записи для первичной роли, а для вторичной роли разрешены соединения с намерением чтения.</span><span class="sxs-lookup"><span data-stu-id="adc94-176">This replica configured to allow only read-write connections for the primary role and to allow only read-intent connections for secondary role.</span></span>  
  
```sql
ALTER AVAILABILITY GROUP AG2   
   ADD REPLICA ON   
      'COMPUTER03\HADR_INSTANCE' WITH   
         (  
         ENDPOINT_URL = 'TCP://COMPUTER03:7022',  
         PRIMARY_ROLE ( ALLOW_CONNECTIONS = READ_WRITE ),  
         SECONDARY_ROLE (ALLOW_CONNECTIONS = READ_ONLY )  
         );   
GO  
```  
  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="adc94-177">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="adc94-177">Using PowerShell</span></span>  

### <a name="to-configure-access-on-an-availability-replica"></a><span data-ttu-id="adc94-178">Настройка доступа к реплике доступности</span><span class="sxs-lookup"><span data-stu-id="adc94-178">To configure access on an availability replica</span></span>
  
> [!NOTE]  
>  <span data-ttu-id="adc94-179">Пример кода см. в разделе примеры PowerShell ниже.</span><span class="sxs-lookup"><span data-stu-id="adc94-179">For a code example, see the PowerShell examples later in this section.</span></span>  
  
1.  <span data-ttu-id="adc94-180">Перейдите в каталог (`cd`) экземпляра сервера, на котором находится первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="adc94-180">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="adc94-181">При добавлении реплики доступности в группу доступности воспользуйтесь командлетом `New-SqlAvailabilityReplica`.</span><span class="sxs-lookup"><span data-stu-id="adc94-181">When adding an availability replica to an availability group, use the `New-SqlAvailabilityReplica` cmdlet.</span></span> <span data-ttu-id="adc94-182">При изменении существующей реплики доступности воспользуйтесь командлетом `Set-SqlAvailabilityReplica`.</span><span class="sxs-lookup"><span data-stu-id="adc94-182">When modifying an existing availability replica, use the `Set-SqlAvailabilityReplica` cmdlet.</span></span> <span data-ttu-id="adc94-183">Соответствующие параметры:</span><span class="sxs-lookup"><span data-stu-id="adc94-183">The relevant parameters are as follows:</span></span>  
  
    -   <span data-ttu-id="adc94-184">Чтобы настроить доступ к соединению для вторичной роли, укажите `ConnectionModeInSecondaryRole` параметр *secondary_role_keyword* , где *secondary_role_keyword* равно одному из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="adc94-184">To configure connection access for the secondary role, specify the `ConnectionModeInSecondaryRole`*secondary_role_keyword* parameter, where *secondary_role_keyword* equals one of the following values:</span></span>  
  
         `AllowNoConnections`  
         <span data-ttu-id="adc94-185">Не допускаются прямые соединения с базами данных во вторичной реплике, кроме того, к базам данных также нельзя получить доступ только для чтения.</span><span class="sxs-lookup"><span data-stu-id="adc94-185">No direct connections are allowed to the databases in the secondary replica and the databases are not available for read access.</span></span> <span data-ttu-id="adc94-186">Это параметр по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="adc94-186">This is the default setting.</span></span>  
  
         `AllowReadIntentConnectionsOnly`  
         <span data-ttu-id="adc94-187">Разрешаются только соединения с базами данных во вторичной реплике, у которых свойство "Назначение приложения" равно **ReadOnly**.</span><span class="sxs-lookup"><span data-stu-id="adc94-187">Connections are allowed only to the databases in the secondary replica where the Application Intent property is set to **ReadOnly**.</span></span> <span data-ttu-id="adc94-188">Дополнительные сведения об этом свойстве см. в разделе [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="adc94-188">For more information about this property, see [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
         `AllowAllConnections`  
         <span data-ttu-id="adc94-189">К базам данных во вторичной реплике разрешаются все соединения на доступ только для чтения.</span><span class="sxs-lookup"><span data-stu-id="adc94-189">All connections are allowed to the databases in the secondary replica for read-only access.</span></span>  
  
    -   <span data-ttu-id="adc94-190">Чтобы настроить доступ к соединению для первичной роли, укажите `ConnectionModeInPrimaryRole` *primary_role_keyword*, где *primary_role_keyword* равно одному из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="adc94-190">To configure connection access for the primary role, specify `ConnectionModeInPrimaryRole`*primary_role_keyword*, where *primary_role_keyword* equals one of the following values:</span></span>  
  
         `AllowReadWriteConnections`  
         <span data-ttu-id="adc94-191">Соединения, у которых свойство «Назначение приложения» равно ReadOnly, разрешены.</span><span class="sxs-lookup"><span data-stu-id="adc94-191">Connections where the Application Intent connection property is set to ReadOnly are disallowed.</span></span> <span data-ttu-id="adc94-192">Если свойство «Назначение приложения» имеет значение ReadWrite либо оно не задано, то соединение разрешено.</span><span class="sxs-lookup"><span data-stu-id="adc94-192">When the Application Intent property is set to ReadWrite or the Application Intent connection property is not set, the connection is allowed.</span></span> <span data-ttu-id="adc94-193">Дополнительные сведения о свойстве соединения «Назначение приложения» см. в разделе [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="adc94-193">For more information about Application Intent connection property, see [Using Connection String Keywords with SQL Server Native Client](../../../relational-databases/native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
         `AllowAllConnections`  
         <span data-ttu-id="adc94-194">Разрешаются все соединения с базами данных в первичной реплике.</span><span class="sxs-lookup"><span data-stu-id="adc94-194">All connections are allowed to the databases in the primary replica.</span></span> <span data-ttu-id="adc94-195">Это параметр по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="adc94-195">This is the default setting.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="adc94-196">Чтобы просмотреть синтаксис командлета, воспользуйтесь командлетом `Get-Help` в среде [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="adc94-196">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] PowerShell environment.</span></span> <span data-ttu-id="adc94-197">Дополнительные сведения см. в разделе [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="adc94-197">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
<span data-ttu-id="adc94-198">Сведения о настройке и использовании поставщика SQL Server PowerShell см. в разделе [поставщик SQL Server PowerShell](../../../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="adc94-198">To set up and use the SQL Server PowerShell provider, see [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md).</span></span>
  
<span data-ttu-id="adc94-199">В следующем примере параметры `ConnectionModeInSecondaryRole` и `ConnectionModeInPrimaryRole` устанавливаются в значение `AllowAllConnections`.</span><span class="sxs-lookup"><span data-stu-id="adc94-199">The following example, sets the both the `ConnectionModeInSecondaryRole` and `ConnectionModeInPrimaryRole` parameters to `AllowAllConnections`.</span></span>  
  
```powershell
Set-Location SQLSERVER:\SQL\PrimaryServer\default\AvailabilityGroups\MyAg  
$primaryReplica = Get-Item "AvailabilityReplicas\PrimaryServer"  

Set-SqlAvailabilityReplica -ConnectionModeInSecondaryRole "AllowAllConnections" `
 -InputObject $primaryReplica  
Set-SqlAvailabilityReplica -ConnectionModeInPrimaryRole "AllowAllConnections" `
-InputObject $primaryReplica
```  

##  <a name="follow-up-after-configuring-read-only-access-for-an-availability-replica"></a><a name="FollowUp"></a> <span data-ttu-id="adc94-200">Дальнейшие действия. После настройки доступа только для чтения для реплики доступности</span><span class="sxs-lookup"><span data-stu-id="adc94-200">Follow Up: After Configuring Read-Only Access for an Availability Replica</span></span>  
 <span data-ttu-id="adc94-201">**Доступ только для чтения к к доступным для чтения вторичным репликам.**</span><span class="sxs-lookup"><span data-stu-id="adc94-201">**Read-only access to a readable secondary replica**</span></span>  
  
-   <span data-ttu-id="adc94-202">При использовании [программы bcp](../../../tools/bcp-utility.md) или [программы sqlcmd](../../../tools/sqlcmd-utility.md)можно указать доступ только для чтения ко всем вторичным репликам, для которых разрешен доступ только для чтения, указав `-K ReadOnly` параметр.</span><span class="sxs-lookup"><span data-stu-id="adc94-202">When using the [bcp Utility](../../../tools/bcp-utility.md) or [sqlcmd Utility](../../../tools/sqlcmd-utility.md), you can specify read-only access to any secondary replica that is enabled for read-only access by specifying the `-K ReadOnly` switch.</span></span>  
  
-   <span data-ttu-id="adc94-203">Обеспечение возможности подключения клиентских приложений к доступным для чтения вторичным репликам.</span><span class="sxs-lookup"><span data-stu-id="adc94-203">To enable client applications to connect to readable secondary replicas:</span></span>  
  
    ||<span data-ttu-id="adc94-204">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="adc94-204">Prerequisite</span></span>|<span data-ttu-id="adc94-205">Ссылка</span><span class="sxs-lookup"><span data-stu-id="adc94-205">Link</span></span>|  
    |-|------------------|----------|  
    |<span data-ttu-id="adc94-206">![Флажок](../../media/checkboxemptycenterxtraspacetopandright.gif "Флажок")</span><span class="sxs-lookup"><span data-stu-id="adc94-206">![Checkbox](../../media/checkboxemptycenterxtraspacetopandright.gif "Checkbox")</span></span>|<span data-ttu-id="adc94-207">Убедитесь, что группа доступности имеет прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="adc94-207">Ensure that the availability group has a listener.</span></span>|[<span data-ttu-id="adc94-208">Создание или настройка прослушивателя группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="adc94-208">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)|  
    |<span data-ttu-id="adc94-209">![Флажок](../../media/checkboxemptycenterxtraspacetopandright.gif "Флажок")</span><span class="sxs-lookup"><span data-stu-id="adc94-209">![Checkbox](../../media/checkboxemptycenterxtraspacetopandright.gif "Checkbox")</span></span>|<span data-ttu-id="adc94-210">Настройте маршрутизацию только для чтения в группе доступности.</span><span class="sxs-lookup"><span data-stu-id="adc94-210">Configure read-only routing for the availability group.</span></span>|[<span data-ttu-id="adc94-211">Настройка маршрутизации только для чтения в группе доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="adc94-211">Configure Read-Only Routing for an Availability Group &#40;SQL Server&#41;</span></span>](configure-read-only-routing-for-an-availability-group-sql-server.md)|  
  
 <span data-ttu-id="adc94-212">**Факторы, которые могут повлиять на триггеры и задания после отработки отказа.**</span><span class="sxs-lookup"><span data-stu-id="adc94-212">**Factors that might affect triggers and jobs after a failover**</span></span>  
  
 <span data-ttu-id="adc94-213">Если имеются триггеры и задания, которые не могут выполняться в недоступной или доступной для чтения базы данных-получателе, то в скриптах триггеров и заданий следует проверять, какой базой данных является искомая реплика, базой данных-источником или базой данных-получателем, доступной для чтения.</span><span class="sxs-lookup"><span data-stu-id="adc94-213">If you have triggers and jobs that will fail when running on a non-readable secondary database or on a readable secondary database, you need to script the triggers and jobs to check on a given replica to determine whether the database is a primary database or is a readable secondary database.</span></span> <span data-ttu-id="adc94-214">Для получения этих сведений следует использовать функцию [DATABASEPROPERTYEX](/sql/t-sql/functions/databasepropertyex-transact-sql) , возвращающую свойство **Updatability** базы данных.</span><span class="sxs-lookup"><span data-stu-id="adc94-214">To obtain this information, use the [DATABASEPROPERTYEX](/sql/t-sql/functions/databasepropertyex-transact-sql) function to return the **Updatability** property of the database.</span></span> <span data-ttu-id="adc94-215">Чтобы определить базу данных, доступную только для чтения, задайте в качестве значения READ_ONLY, как в примере ниже:</span><span class="sxs-lookup"><span data-stu-id="adc94-215">To identify a read-only database, specify READ_ONLY as the value, as follows:</span></span>  
  
```  
DATABASEPROPERTYEX([db name],'Updatability') = N'READ_ONLY'  
```  
  
 <span data-ttu-id="adc94-216">Чтобы определить базу данных для чтения и записи, укажите в качестве значения READ_WRITE.</span><span class="sxs-lookup"><span data-stu-id="adc94-216">To identify a read-write database, specify READ_WRITE as the value.</span></span>  
  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="adc94-217">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="adc94-217">Related Tasks</span></span>  
  
-   [<span data-ttu-id="adc94-218">Настройка маршрутизации только для чтения в группе доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="adc94-218">Configure Read-Only Routing for an Availability Group &#40;SQL Server&#41;</span></span>](configure-read-only-routing-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="adc94-219">Создание или настройка прослушивателя группы доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="adc94-219">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="adc94-220">См. также</span><span class="sxs-lookup"><span data-stu-id="adc94-220">Related Content</span></span>  
  
-   [<span data-ttu-id="adc94-221">Always On: ценностное предложение читаемой вторичной реплики</span><span class="sxs-lookup"><span data-stu-id="adc94-221">Always On: Value Proposition of Readable Secondary</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-value-proposition-of-readable-secondary)  
  
-   [<span data-ttu-id="adc94-222">Always On: почему есть два варианта включения вторичной реплики для читаемой рабочей нагрузки?</span><span class="sxs-lookup"><span data-stu-id="adc94-222">Always On: Why there are two options to enable a secondary replica for read workload?</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-why-there-are-two-options-to-enable-a-secondary-replica-for-read-workload)  
  
-   [<span data-ttu-id="adc94-223">Always On: Настройка доступной для чтения вторичной реплики</span><span class="sxs-lookup"><span data-stu-id="adc94-223">Always On: Setting up Readable Secondary Replica</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-setting-up-readable-seconary-replica)  
  
-   [<span data-ttu-id="adc94-224">Always On: я только что включил читаемую вторичную реплику, но мой запрос был заблокирован. В чем дело?</span><span class="sxs-lookup"><span data-stu-id="adc94-224">Always On: I just enabled Readable Secondary but my query is blocked?</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-i-just-enabled-readable-secondary-but-my-query-is-blocked)  
  
-   [<span data-ttu-id="adc94-225">Always On: обеспечение доступности последних статистических данных о читаемой вторичной реплике, базе данных только для чтения и моментальном снимке базы данных</span><span class="sxs-lookup"><span data-stu-id="adc94-225">Always On: Making latest statistics available on Readable Secondary, Read-Only database and Database Snapshot</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-making-latest-statistics-available-on-readable-secondary-read-only-database-and-database-snapshot)  
  
-   [<span data-ttu-id="adc94-226">Always On: проблемы со статистическими данными о базе данных только для чтения, моментальном снимке базы данных и вторичной реплике</span><span class="sxs-lookup"><span data-stu-id="adc94-226">Always On: Challenges with statistics on ReadOnly database, Database Snapshot and Secondary Replica</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-challenges-with-statistics-on-readonly-database-database-snapshot-and-secondary-replica)  
  
-   [<span data-ttu-id="adc94-227">Always On: влияние на основную рабочую нагрузку при запуске рабочей нагрузки составления отчетов на вторичной реплике</span><span class="sxs-lookup"><span data-stu-id="adc94-227">Always On: Impact on the primary workload when you run reporting workload on the secondary replica</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-impact-on-the-primary-workload-when-you-run-reporting-workload-on-the-secondary-replica)  
  
-   [<span data-ttu-id="adc94-228">Always On: влияние сопоставления рабочей нагрузки составления отчетов на вторичной реплике на изоляцию моментальных снимков</span><span class="sxs-lookup"><span data-stu-id="adc94-228">Always On: Impact of mapping reporting workload on Readable Secondary to Snapshot Isolation</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-impact-of-mapping-reporting-workload-on-readable-secondary-to-snapshot-isolation)  
  
-   [<span data-ttu-id="adc94-229">Always On: минимизация блокировок потока REDO при запуске рабочей нагрузки составления отчетов на вторичной реплике</span><span class="sxs-lookup"><span data-stu-id="adc94-229">Always On: Minimizing blocking of REDO thread when running reporting workload on Secondary Replica</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-minimizing-blocking-of-redo-thread-when-running-reporting-workload-on-secondary-replica)  
  
-   [<span data-ttu-id="adc94-230">Always On: читаемая вторичная реплика и задержка данных</span><span class="sxs-lookup"><span data-stu-id="adc94-230">Always On: Readable Secondary and data latency</span></span>](https://docs.microsoft.com/archive/blogs/sqlserverstorageengine/alwayson-readable-secondary-and-data-latency)  
  
## <a name="see-also"></a><span data-ttu-id="adc94-231">См. также:</span><span class="sxs-lookup"><span data-stu-id="adc94-231">See Also</span></span>  
 <span data-ttu-id="adc94-232">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="adc94-232">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="adc94-233">Активные вторичные реплики: &#40;группы доступности AlwaysOn для чтения&#41;</span><span class="sxs-lookup"><span data-stu-id="adc94-233">Active Secondaries: Readable Secondary Replicas &#40;AlwaysOn Availability Groups&#41;</span></span>](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md)  
 [<span data-ttu-id="adc94-234">Сведения о доступе клиентского подключения к репликам доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="adc94-234">About Client Connection Access to Availability Replicas &#40;SQL Server&#41;</span></span>](about-client-connection-access-to-availability-replicas-sql-server.md)  
