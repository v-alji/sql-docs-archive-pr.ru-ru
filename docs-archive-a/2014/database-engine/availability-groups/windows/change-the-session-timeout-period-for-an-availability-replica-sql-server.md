---
title: Изменение периода ожидания сеанса для реплики доступности (SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], session timeout
- session timeout [SQL Server]
ms.assetid: e23c6e06-1cd1-4d4a-9bc2-e3e06ab2933d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 302ba4a2b0b72a70b05e563eb4085913074469eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750211"
---
# <a name="change-the-session-timeout-period-for-an-availability-replica-sql-server"></a><span data-ttu-id="39b72-102">Изменение периода ожидания сеанса для реплики доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="39b72-102">Change the Session-Timeout Period for an Availability Replica (SQL Server)</span></span>
  <span data-ttu-id="39b72-103">В этом разделе описывается настройка времени ожидания сеанса реплики доступности AlwaysOn при помощи среды [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]или PowerShell в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39b72-103">This topic describes how to configure the session-timeout period of an AlwaysOn availability replica by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="39b72-104">Время ожидания сеанса — это свойство реплики, которое определяет, сколько секунд будет эта реплика доступности ждать отклика на команду ping, отправленную с подключенной реплики перед тем, как признать попытку подключения неудачной.</span><span class="sxs-lookup"><span data-stu-id="39b72-104">The session-timeout period is a replica property that controls how many seconds (in seconds) that an availability replica waits for a ping response from a connected replica before considering the connection to have failed.</span></span> <span data-ttu-id="39b72-105">По умолчанию реплика ожидает ответа на команду ping 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="39b72-105">By default, a replica waits 10 seconds for a ping response.</span></span> <span data-ttu-id="39b72-106">Это свойство реплики применимо только к подключению данной вторичной реплики к первичной реплике группы доступности.</span><span class="sxs-lookup"><span data-stu-id="39b72-106">This replica property applies only the connection between a given secondary replica and the primary replica of the availability group.</span></span> <span data-ttu-id="39b72-107">Дополнительные сведения о периоде времени ожидания сеанса см. в разделе [Обзор групп доступности AlwaysOn (SQL Server)](overview-of-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="39b72-107">For more information about the session-timeout period, see [Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span></span>  
  
-   <span data-ttu-id="39b72-108">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="39b72-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="39b72-109">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="39b72-109">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="39b72-110">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="39b72-110">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="39b72-111">Безопасность</span><span class="sxs-lookup"><span data-stu-id="39b72-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="39b72-112">**Изменение времени ожидания с помощью**</span><span class="sxs-lookup"><span data-stu-id="39b72-112">**To change the session-timeout period, using:**</span></span>  
  
     [<span data-ttu-id="39b72-113">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="39b72-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="39b72-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="39b72-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="39b72-115">PowerShell</span><span class="sxs-lookup"><span data-stu-id="39b72-115">PowerShell</span></span>](#PowerShellProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="39b72-116">Перед началом</span><span class="sxs-lookup"><span data-stu-id="39b72-116">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="39b72-117">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="39b72-117">Prerequisites</span></span>  
  
-   <span data-ttu-id="39b72-118">Необходимо подключиться к экземпляру сервера, на котором размещена первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="39b72-118">You must be connected to the server instance that hosts the primary replica.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="39b72-119">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="39b72-119">Recommendations</span></span>  
 <span data-ttu-id="39b72-120">Рекомендуется установить интервал времени ожидания в 10 секунд или более.</span><span class="sxs-lookup"><span data-stu-id="39b72-120">We recommend that you keep the time-out period at 10 seconds or greater.</span></span> <span data-ttu-id="39b72-121">При установке значения меньше 10 секунд возникает вероятность пропуска команды PING в сильно загруженной системе и вероятность ошибочного сообщения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="39b72-121">Setting the value to less than 10 seconds creates the possibility of a heavily loaded system missing PINGs and declaring a false failure.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="39b72-122">безопасность</span><span class="sxs-lookup"><span data-stu-id="39b72-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="39b72-123">Permissions</span><span class="sxs-lookup"><span data-stu-id="39b72-123">Permissions</span></span>  
 <span data-ttu-id="39b72-124">Необходимо разрешение ALTER AVAILABILITY GROUP для группы доступности, разрешение CONTROL AVAILABILITY GROUP, разрешение ALTER ANY AVAILABILITY GROUP или разрешение CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="39b72-124">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="39b72-125">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="39b72-125">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="39b72-126">**Изменение значения времени ожидания сеанса для реплики доступности**</span><span class="sxs-lookup"><span data-stu-id="39b72-126">**To change the session-timeout period for an availability replica**</span></span>  
  
1.  <span data-ttu-id="39b72-127">В обозревателе объектов подключитесь к экземпляру сервера, на котором размещена первичная реплика, и разверните дерево сервера.</span><span class="sxs-lookup"><span data-stu-id="39b72-127">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="39b72-128">Разверните узел **Высокий уровень доступности AlwaysOn** и узел **Группы доступности** .</span><span class="sxs-lookup"><span data-stu-id="39b72-128">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="39b72-129">Щелкните группу доступности, реплику которой нужно настроить.</span><span class="sxs-lookup"><span data-stu-id="39b72-129">Click the availability group whose availability replica you want to configure.</span></span>  
  
4.  <span data-ttu-id="39b72-130">Щелкните правой кнопкой мыши реплику доступности, которую нужно настроить, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="39b72-130">Right-click the replica to be configured, and click **Properties**.</span></span>  
  
5.  <span data-ttu-id="39b72-131">В диалоговом окне **Свойства реплики доступности** используйте поле **Время ожидания сеанса (в секундах)** , чтобы изменить число секунд, заданное в качестве времени ожидания для этой реплики.</span><span class="sxs-lookup"><span data-stu-id="39b72-131">In the **Availability Replica Properties** dialog box, use the **Session timeout (seconds)** field to change the number of seconds for the session-timeout period on this replica.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="39b72-132">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="39b72-132">Using Transact-SQL</span></span>  
 <span data-ttu-id="39b72-133">**Изменение значения времени ожидания сеанса для реплики доступности**</span><span class="sxs-lookup"><span data-stu-id="39b72-133">**To change the session-timeout period for an availability replica**</span></span>  
  
1.  <span data-ttu-id="39b72-134">Подключитесь к экземпляру сервера, на котором находится первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="39b72-134">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="39b72-135">Инструкция [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) используется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="39b72-135">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="39b72-136">ALTER AVAILABILITY GROUP *имя_группы*</span><span class="sxs-lookup"><span data-stu-id="39b72-136">ALTER AVAILABILITY GROUP *group_name*</span></span>  
  
     <span data-ttu-id="39b72-137">MODIFY REPLICA ON '*имя_экземпляра*' WITH ( SESSION_TIMEOUT =*число_секунд* )</span><span class="sxs-lookup"><span data-stu-id="39b72-137">MODIFY REPLICA ON '*instance_name*' WITH ( SESSION_TIMEOUT =*seconds* )</span></span>  
  
     <span data-ttu-id="39b72-138">где *имя_группы* ― это имя группы доступности, *имя_экземпляра* ― это имя экземпляра сервера, где расположена реплика доступности, свойство которой необходимо изменить, а параметр *число_секунд* указывает количество секунд, которое реплика, будучи вторичной, будет ожидать до момента применения журнала к базам данных.</span><span class="sxs-lookup"><span data-stu-id="39b72-138">where *group_name* is the name of the availability group, *instance_name* is the name of the server instance that hosts the availability replica to be modified, and *seconds* specifies the minimum number of seconds that the replica must wait before applying log to databases when acting as a secondary replica.</span></span> <span data-ttu-id="39b72-139">Значение по умолчанию равно 0 секунд. Это означает, что время задержки равно 0.</span><span class="sxs-lookup"><span data-stu-id="39b72-139">The default is 0 seconds, which indicates that there is no apply delay.</span></span>  
  
     <span data-ttu-id="39b72-140">В следующем примере, введенном на первичной реплике группы доступности `AccountsAG` , выполняется изменение значения времени ожидания сеанса на значение `15` секунд для реплики, размещенной на экземпляре сервера `INSTANCE09` .</span><span class="sxs-lookup"><span data-stu-id="39b72-140">The following example, entered on the primary replica of the `AccountsAG` availability group, changes the session-timeout value to `15` seconds for the replica located on the `INSTANCE09` server instance.</span></span>  
  
    ```  
    ALTER AVAILABILITY GROUP AccountsAG   
       MODIFY REPLICA ON 'INSTANCE09' WITH (SESSION_TIMEOUT = 15);  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="39b72-141">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="39b72-141">Using PowerShell</span></span>  

### <a name="to-change-the-session-timeout-period-for-an-availability-replica"></a><span data-ttu-id="39b72-142">Изменение значения времени ожидания сеанса для реплики доступности</span><span class="sxs-lookup"><span data-stu-id="39b72-142">To change the session-timeout period for an availability replica</span></span>
  
1.  <span data-ttu-id="39b72-143">Перейдите в каталог (`cd`) экземпляра сервера, на котором находится первичная реплика.</span><span class="sxs-lookup"><span data-stu-id="39b72-143">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="39b72-144">Используйте командлет `Set-SqlAvailabilityReplica` с параметром `SessionTimeout`, чтобы изменить число секунд времени ожидания сеанса для указанной реплики доступности.</span><span class="sxs-lookup"><span data-stu-id="39b72-144">Use the `Set-SqlAvailabilityReplica` cmdlet with the `SessionTimeout` parameter to change the number of seconds for the session-timeout period on a specified availability replica.</span></span>  
  
     <span data-ttu-id="39b72-145">Например, следующая команда задает период времени ожидания сеанса 15 секунд.</span><span class="sxs-lookup"><span data-stu-id="39b72-145">For example, the following command sets the session-timeout period to 15 seconds.</span></span>  
  
    ```powershell
    Set-SqlAvailabilityReplica -SessionTimeout 15 -Path SQLSERVER:\Sql\PrimaryServer\InstanceName\AvailabilityGroups\MyAg\AvailabilityReplicas\MyReplica  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="39b72-146">Чтобы просмотреть синтаксис командлета, воспользуйтесь командлетом `Get-Help` в среде [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="39b72-146">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="39b72-147">Дополнительные сведения см. в разделе [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="39b72-147">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
<span data-ttu-id="39b72-148">Сведения о настройке и использовании поставщика SQL Server PowerShell см. в разделе [поставщик SQL Server PowerShell](../../../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="39b72-148">To set up and use the SQL Server PowerShell provider, see [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="39b72-149">См. также:</span><span class="sxs-lookup"><span data-stu-id="39b72-149">See Also</span></span>  
 [<span data-ttu-id="39b72-150">Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="39b72-150">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
