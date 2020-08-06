---
title: Включение и отключение группы доступности AlwaysOn (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], server instance
- Availability Groups [SQL Server], deploying
- Availability Groups [SQL Server], disabling
- Availability Groups [SQL Server], enabling
ms.assetid: 7c326958-5ae9-4761-9c57-905972276a8f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 585f1d86d328b7c5027241310108d102b56ca327
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655966"
---
# <a name="enable-and-disable-alwayson-availability-groups-sql-server"></a><span data-ttu-id="f36d3-102">Включение и отключение групп доступности AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f36d3-102">Enable and Disable AlwaysOn Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="f36d3-103">Включение [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] является предварительным условием для того, чтобы экземпляр сервера мог использовать группы доступности.</span><span class="sxs-lookup"><span data-stu-id="f36d3-103">Enabling [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] is a prerequisite for a server instance to use availability groups.</span></span> <span data-ttu-id="f36d3-104">Перед тем как создавать и настраивать любую группу доступности, следует включить компонент [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] на каждом экземпляре [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , где будет размещаться реплика доступности для одной или нескольких групп доступности.</span><span class="sxs-lookup"><span data-stu-id="f36d3-104">Before you can create and configure any availability group, the [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] feature must have been enabled on the each instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that will host an availability replica for one or more availability groups.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f36d3-105">При удалении и повторном создании кластера WSFC необходимо отключить и повторно включить функцию [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] в каждом экземпляре [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , который обеспечил размещение реплики доступности в исходном кластере WSFC.</span><span class="sxs-lookup"><span data-stu-id="f36d3-105">If you delete and re-create a WSFC cluster, you must disable and re-enable the [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] feature on each instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosted an availability replica on the original WSFC cluster.</span></span>  
  
-   <span data-ttu-id="f36d3-106">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="f36d3-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f36d3-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="f36d3-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="f36d3-108">Безопасность</span><span class="sxs-lookup"><span data-stu-id="f36d3-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f36d3-109">**Инструкции:**</span><span class="sxs-lookup"><span data-stu-id="f36d3-109">**How To:**</span></span>  
  
    -   [<span data-ttu-id="f36d3-110">Определите, включены ли группы доступности AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="f36d3-110">Determine Whether AlwaysOn Availability Groups is Enabled</span></span>](#IsEnabled)  
  
    -   [<span data-ttu-id="f36d3-111">Включить группы доступности AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="f36d3-111">Enable AlwaysOn Availability Groups</span></span>](#EnableAOAG)  
  
    -   [<span data-ttu-id="f36d3-112">Отключите группы доступности AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="f36d3-112">Disable AlwaysOn Availability Groups</span></span>](#DisableAOAG)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f36d3-113">Перед началом</span><span class="sxs-lookup"><span data-stu-id="f36d3-113">Before You Begin</span></span>  
  
###  <a name="prerequisites-for-enabling-alwayson-availability-groups"></a><a name="Prerequisites"></a><span data-ttu-id="f36d3-114">Необходимые условия для включения группы доступности AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="f36d3-114">Prerequisites for Enabling AlwaysOn Availability Groups</span></span>  
  
-   <span data-ttu-id="f36d3-115">Экземпляр сервера должен находиться на узле отказоустойчивой кластеризации Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="f36d3-115">The server instance must reside on a Windows Server Failover Clustering (WSFC) node.</span></span>  
  
-   <span data-ttu-id="f36d3-116">Экземпляр сервера должен работать на выпуске SQL Server, который поддерживает [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f36d3-116">The server instance must be running an edition of SQL Server that supports [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span></span> <span data-ttu-id="f36d3-117">Дополнительные сведения см. [в разделе функции, поддерживаемые различными Выпусками SQL Server 2014](../../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="f36d3-117">For more information, see [Features Supported by the Editions of SQL Server 2014](../../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
-   <span data-ttu-id="f36d3-118">Включайте группы доступности AlwaysOn только на одном экземпляре сервера единовременно.</span><span class="sxs-lookup"><span data-stu-id="f36d3-118">Enable AlwaysOn Availability Groups on only one server instance at a time.</span></span> <span data-ttu-id="f36d3-119">После включения групп доступности AlwaysOn подождите, пока служба [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] не перезапустится, и только после этого включайте следующий экземпляр.</span><span class="sxs-lookup"><span data-stu-id="f36d3-119">After enabling AlwaysOn Availability Groups, wait until the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service has restarted before you proceed to another server instance.</span></span>  
  
 <span data-ttu-id="f36d3-120">Дополнительные сведения о дополнительных предварительных требованиях для создания и настройки групп доступности см. в разделе [Предварительные требования, ограничения и рекомендации для группы доступности AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="f36d3-120">For information about additional prerequisites for creating and configuring availability groups, see [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f36d3-121">безопасность</span><span class="sxs-lookup"><span data-stu-id="f36d3-121">Security</span></span>  
 <span data-ttu-id="f36d3-122">Когда группы доступности AlwaysOn включены на экземпляре [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], экземпляр сервера получает полный контроль над кластером WSFC.</span><span class="sxs-lookup"><span data-stu-id="f36d3-122">While AlwaysOn Availability Groups is enabled on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the server instance has full control on the WSFC cluster.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f36d3-123">Permissions</span><span class="sxs-lookup"><span data-stu-id="f36d3-123">Permissions</span></span>  
 <span data-ttu-id="f36d3-124">Требуется членство в группе **Администратор** на локальном компьютере и полный контроль над кластером WSFC.</span><span class="sxs-lookup"><span data-stu-id="f36d3-124">Requires membership in the **Administrator** group on the local computer and full control on the WSFC cluster.</span></span> <span data-ttu-id="f36d3-125">При включении функции AlwaysOn при помощи консоли PowerShell, откройте окно командной строки, используя команду **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="f36d3-125">When enabling AlwaysOn by using PowerShell, open the Command Prompt window using the **Run as administrator** option.</span></span>  
  
 <span data-ttu-id="f36d3-126">Требуются разрешения Active Directory на создание объектов и управление объектами.</span><span class="sxs-lookup"><span data-stu-id="f36d3-126">Requires Active Directory Create Objects and Manage Objects permissions.</span></span>  
  
##  <a name="determine-whether-alwayson-availability-groups-is-enabled"></a><a name="IsEnabled"></a><span data-ttu-id="f36d3-127">Определение того, включена ли группы доступности AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="f36d3-127">Determine Whether AlwaysOn Availability Groups is Enabled</span></span>  
  
-   [<span data-ttu-id="f36d3-128">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f36d3-128">SQL Server Management Studio</span></span>](#SSMS1Procedure)  
  
-   [<span data-ttu-id="f36d3-129">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f36d3-129">Transact-SQL</span></span>](#Tsql1Procedure)  
  
-   [<span data-ttu-id="f36d3-130">PowerShell</span><span class="sxs-lookup"><span data-stu-id="f36d3-130">PowerShell</span></span>](#PowerShell1Procedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMS1Procedure"></a> <span data-ttu-id="f36d3-131">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f36d3-131">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="f36d3-132">**Определение того, включены ли группы доступности AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="f36d3-132">**To determine whether AlwaysOn Availability Groups is enabled**</span></span>  
  
1.  <span data-ttu-id="f36d3-133">В обозревателе объектов щелкните правой кнопкой мыши экземпляр сервера и выберите команду **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="f36d3-133">In Object Explorer, right-click the server instance, and  click **Properties**.</span></span>  
  
2.  <span data-ttu-id="f36d3-134">В диалоговом окне **Свойства сервера** перейдите на страницу **Общие** .</span><span class="sxs-lookup"><span data-stu-id="f36d3-134">In the **Server Properties** dialog box, click the **General** page.</span></span> <span data-ttu-id="f36d3-135">Свойство **HADR включен** имеет одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="f36d3-135">The **Is HADR Enabled** property displays one of the following values:</span></span>  
  
    -   <span data-ttu-id="f36d3-136">**True**, если группы доступности AlwaysOn включены</span><span class="sxs-lookup"><span data-stu-id="f36d3-136">**True**, if AlwaysOn Availability Groups is enabled</span></span>  
  
    -   <span data-ttu-id="f36d3-137">**False**, если группы доступности AlwaysOn отключены</span><span class="sxs-lookup"><span data-stu-id="f36d3-137">**False**, if AlwaysOn Availability Groups is disabled.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="Tsql1Procedure"></a> <span data-ttu-id="f36d3-138">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f36d3-138">Using Transact-SQL</span></span>  
 <span data-ttu-id="f36d3-139">**Определение того, включены ли группы доступности AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="f36d3-139">**To determine whether AlwaysOn Availability Groups is enabled**</span></span>  
  
1.  <span data-ttu-id="f36d3-140">Используйте следующую инструкцию [SERVERPROPERTY](/sql/t-sql/functions/serverproperty-transact-sql) :</span><span class="sxs-lookup"><span data-stu-id="f36d3-140">Use the following [SERVERPROPERTY](/sql/t-sql/functions/serverproperty-transact-sql) statement:</span></span>  
  
    ```sql
    SELECT SERVERPROPERTY ('IsHadrEnabled');  
    ```  
  
     <span data-ttu-id="f36d3-141">Значение свойства сервера `IsHadrEnabled` указывает, может ли экземпляр [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] входить в группы доступности AlwaysOn следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f36d3-141">The setting of the `IsHadrEnabled` server property indicates whether an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is enabled for AlwaysOn Availability Groups, as follows:</span></span>  
  
    -   <span data-ttu-id="f36d3-142">Если значение свойства `IsHadrEnabled` = 1, это означает группы доступности AlwaysOn включены.</span><span class="sxs-lookup"><span data-stu-id="f36d3-142">If `IsHadrEnabled` = 1, AlwaysOn Availability Groups is enabled.</span></span>  
  
    -   <span data-ttu-id="f36d3-143">Если значение свойства `IsHadrEnabled` = 0, это означает, что группы доступности AlwaysOn отключены.</span><span class="sxs-lookup"><span data-stu-id="f36d3-143">If `IsHadrEnabled` = 0, AlwaysOn Availability Groups is disabled.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f36d3-144">Дополнительные сведения о `IsHadrEnabled` свойстве сервера см. в разделе [SERVERPROPERTY &#40;TRANSACT-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f36d3-144">For more information about the `IsHadrEnabled` server property, see [SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql).</span></span>  
  
###  <a name="using-powershell"></a><a name="PowerShell1Procedure"></a> <span data-ttu-id="f36d3-145">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="f36d3-145">Using PowerShell</span></span>  
 <span data-ttu-id="f36d3-146">**Определение того, включены ли группы доступности AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="f36d3-146">**To determine whether AlwaysOn Availability Groups is enabled**</span></span>  
  
1.  <span data-ttu-id="f36d3-147">Задайте для параметра Default ( `cd` ) экземпляр сервера (например, `\SQL\NODE1\DEFAULT` ), для которого необходимо определить [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] , включен ли параметр.</span><span class="sxs-lookup"><span data-stu-id="f36d3-147">Set default (`cd`) to the server instance (e.g. `\SQL\NODE1\DEFAULT`) on which you want to determine whether [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] is enabled.</span></span>  
  
2.  <span data-ttu-id="f36d3-148">Введите следующую команду PowerShell `Get-Item`:</span><span class="sxs-lookup"><span data-stu-id="f36d3-148">Enter the following PowerShell `Get-Item` command:</span></span>  
  
    ```powershell
    Get-Item . | Select IsHadrEnabled  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="f36d3-149">Чтобы просмотреть синтаксис командлета, воспользуйтесь командлетом `Get-Help` в среде [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f36d3-149">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="f36d3-150">Дополнительные сведения см. в разделе [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="f36d3-150">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="f36d3-151">**Настройка и использование поставщика SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="f36d3-151">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="f36d3-152">Поставщик SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="f36d3-152">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="enable-alwayson-availability-groups"></a><a name="EnableAOAG"></a> <span data-ttu-id="f36d3-153">Включение групп доступности AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="f36d3-153">Enable AlwaysOn Availability Groups</span></span>  
 <span data-ttu-id="f36d3-154">**Включение функции AlwaysOn с помощью**</span><span class="sxs-lookup"><span data-stu-id="f36d3-154">**To enable AlwaysOn, using:**</span></span>  
  
-   [<span data-ttu-id="f36d3-155">Диспетчер конфигурации SQL Server</span><span class="sxs-lookup"><span data-stu-id="f36d3-155">SQL Server Configuration Manager</span></span>](#SQLCM2Procedure)  
  
-   [<span data-ttu-id="f36d3-156">PowerShell</span><span class="sxs-lookup"><span data-stu-id="f36d3-156">PowerShell</span></span>](#PScmd2Procedure)  
  
###  <a name="using-sql-server-configuration-manager"></a><a name="SQLCM2Procedure"></a> <span data-ttu-id="f36d3-157">Использование диспетчера конфигурации SQL Server</span><span class="sxs-lookup"><span data-stu-id="f36d3-157">Using SQL Server Configuration Manager</span></span>  
 <span data-ttu-id="f36d3-158">**Включение функции «Группы доступности AlwaysOn»**</span><span class="sxs-lookup"><span data-stu-id="f36d3-158">**To enable AlwaysOn Availability Groups**</span></span>  
  
1.  <span data-ttu-id="f36d3-159">Выполните подключение к узлу отказоустойчивой кластеризации Windows Server (WSFC), на котором размещен экземпляр [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], на котором требуется включить группы доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="f36d3-159">Connect to the Windows Server Failover Clustering (WSFC) node that hosts the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance where you want to enable AlwaysOn Availability Groups.</span></span>  
  
2.  <span data-ttu-id="f36d3-160">В меню **Пуск** последовательно выберите пункты **Все программы**, [!INCLUDE[ssCurrentUI](../../../includes/sscurrentui-md.md)], **Средства настройки**и **Диспетчер конфигурации SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="f36d3-160">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and  click **SQL Server Configuration Manager**.</span></span>  
  
3.  <span data-ttu-id="f36d3-161">В **Диспетчер конфигурации SQL Server**щелкните **SQL Server службы**, щелкните правой кнопкой мыши SQL Server (\*\* < *`instance name`*>)\*\*, где **<*`instance name`*>** — имя локального экземпляра сервера, для которого требуется включить группы доступности AlwaysOn, и нажмите кнопку **Свойства.**</span><span class="sxs-lookup"><span data-stu-id="f36d3-161">In **SQL Server Configuration Manager**, click **SQL Server Services**, right-click SQL Server (**<*`instance name`*>)**, where **<*`instance name`*>** is the name of a local server instance for which you want to enable AlwaysOn Availability Groups, and click **Properties.**</span></span>  
  
4.  <span data-ttu-id="f36d3-162">Перейдите на вкладку **Высокий уровень доступности AlwaysOn** .</span><span class="sxs-lookup"><span data-stu-id="f36d3-162">Select the **AlwaysOn High Availability** tab.</span></span>  
  
5.  <span data-ttu-id="f36d3-163">Убедитесь, что поле **Имя отказоустойчивого кластера Windows** содержит имя локального отказоустойчивого кластера.</span><span class="sxs-lookup"><span data-stu-id="f36d3-163">Verify that **Windows failover cluster name** field contains the name of the local failover cluster.</span></span> <span data-ttu-id="f36d3-164">Если это поле не заполнено, в настоящее время этот экземпляр сервера не поддерживает [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f36d3-164">If this field is blank, this server instance currently does not support [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span></span> <span data-ttu-id="f36d3-165">Либо локальный компьютер не является узлом кластера, кластер WSFC завершил работу, либо этот выпуск [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] не поддерживает [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f36d3-165">Either the local computer is not a cluster node, the WSFC cluster has been shut down, or this edition of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] that does not support [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span></span>  
  
6.  <span data-ttu-id="f36d3-166">Установите флажок **включить группы доступности AlwaysOn** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f36d3-166">Select the **Enable AlwaysOn Availability Groups** check box, and click **OK**.</span></span>  
  
     [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="f36d3-167">сохранит внесенные изменения.</span><span class="sxs-lookup"><span data-stu-id="f36d3-167">Configuration Manager saves your change.</span></span> <span data-ttu-id="f36d3-168">После этого необходимо вручную перезапустить службу [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f36d3-168">Then, you must manually restart the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service.</span></span> <span data-ttu-id="f36d3-169">Это позволит выбрать время перезапуска, которое лучше всего подходит под требования вашего предприятия.</span><span class="sxs-lookup"><span data-stu-id="f36d3-169">This enables you to choose a restart time that is best for your business requirements.</span></span> <span data-ttu-id="f36d3-170">После перезапуска службы [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] функция AlwaysOn будет включена, а свойство `IsHadrEnabled` будет установлено в значение 1.</span><span class="sxs-lookup"><span data-stu-id="f36d3-170">When the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service restarts, AlwaysOn will be enabled, and the `IsHadrEnabled` server property will be set to 1.</span></span>  
  
###  <a name="using-sql-server-powershell"></a><a name="PScmd2Procedure"></a> <span data-ttu-id="f36d3-171">Использование SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="f36d3-171">Using SQL Server PowerShell</span></span>  
 <span data-ttu-id="f36d3-172">**Включение функции AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="f36d3-172">**To enable AlwaysOn**</span></span>  
  
1.  <span data-ttu-id="f36d3-173">Измените каталог (`cd`) на каталог экземпляра сервера, для которого необходимо включить группы доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="f36d3-173">Change directory (`cd`) to a server instance that you want to enable for AlwaysOn Availability Groups.</span></span>  
  
2.  <span data-ttu-id="f36d3-174">С помощью командлета `Enable-SqlAlwaysOn` включите группы доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="f36d3-174">Use the `Enable-SqlAlwaysOn` cmdlet to enable AlwaysOn Availability Groups.</span></span>  
  
     <span data-ttu-id="f36d3-175">Чтобы просмотреть синтаксис командлета, воспользуйтесь командлетом `Get-Help` в среде [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f36d3-175">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="f36d3-176">Дополнительные сведения см. в разделе [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="f36d3-176">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f36d3-177">Сведения о том, как управлять тем `Enable-SqlAlwaysOn` , перезапускается ли командлет [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , см. в разделе Когда командлет перезапускает [службу SQL Server?](#WhenCmdletRestartsSQL)далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="f36d3-177">For information about how to control whether the `Enable-SqlAlwaysOn` cmdlet restarts the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service, see [When Does a Cmdlet Restart the SQL Server Service?](#WhenCmdletRestartsSQL), later in this topic.</span></span>  
  
 <span data-ttu-id="f36d3-178">**Настройка и использование поставщика SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="f36d3-178">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="f36d3-179">Поставщик SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="f36d3-179">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
####  <a name="example-enable-sqlalwayson"></a><a name="ExmplEnable-SqlHadrServic"></a> <span data-ttu-id="f36d3-180">Пример. Enable-SqlAlwaysOn</span><span class="sxs-lookup"><span data-stu-id="f36d3-180">Example: Enable-SqlAlwaysOn</span></span>  
 <span data-ttu-id="f36d3-181">Следующая команда PowerShell включает [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] на экземпляре SQL Server (*Computer*\\*Instance*).</span><span class="sxs-lookup"><span data-stu-id="f36d3-181">The following PowerShell command enables [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] on an instance of SQL Server (*Computer*\\*Instance*).</span></span>  
  
```powershell
Enable-SqlAlwaysOn -Path SQLSERVER:\SQL\Computer\Instance  
```  
  
##  <a name="disable-alwayson-availability-groups"></a><a name="DisableAOAG"></a><span data-ttu-id="f36d3-182">Отключить группы доступности AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="f36d3-182">Disable AlwaysOn Availability Groups</span></span>  
  
-   <span data-ttu-id="f36d3-183">**Перед отключением AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="f36d3-183">**Before you disable AlwaysOn:**</span></span>  
  
     [<span data-ttu-id="f36d3-184">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="f36d3-184">Recommendations</span></span>](#Recommendations)  
  
-   <span data-ttu-id="f36d3-185">**Отключение AlwaysOn с помощью**</span><span class="sxs-lookup"><span data-stu-id="f36d3-185">**To disable AlwaysOn, using:**</span></span>  
  
    -   [<span data-ttu-id="f36d3-186">Диспетчер конфигурации SQL Server</span><span class="sxs-lookup"><span data-stu-id="f36d3-186">SQL Server Configuration Manager</span></span>](#SQLCM3Procedure)  
  
    -   [<span data-ttu-id="f36d3-187">PowerShell</span><span class="sxs-lookup"><span data-stu-id="f36d3-187">PowerShell</span></span>](#PScmd3Procedure)  
  
-   <span data-ttu-id="f36d3-188">**Дальнейшие действия.**  [после отключения AlwaysOn](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="f36d3-188">**Follow Up:**  [After Disabling AlwaysOn](#FollowUp)</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f36d3-189">Функцию AlwaysOn следует одновременно отключать только для одного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="f36d3-189">Disable AlwaysOn on only one server instance at a time.</span></span> <span data-ttu-id="f36d3-190">После отключения групп доступности AlwaysOn подождите, пока служба [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] не перезапустится, и только после этого переходите к другому экземпляру.</span><span class="sxs-lookup"><span data-stu-id="f36d3-190">After disabling AlwaysOn Availability Groups, wait until the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service has restarted before you proceed to another server instance.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="f36d3-191">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="f36d3-191">Recommendations</span></span>  
 <span data-ttu-id="f36d3-192">Перед отключением AlwaysOn на экземпляре сервера рекомендуется выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="f36d3-192">Before you disable AlwaysOn on a server instance, we recommend that you do the following:</span></span>  
  
1.  <span data-ttu-id="f36d3-193">Если на экземпляре сервера в настоящее время размещается первичная реплика группы доступности, которую нужно сохранить, то рекомендуется вручную переключить группу доступности на синхронизированную вторичную реплику, если это возможно.</span><span class="sxs-lookup"><span data-stu-id="f36d3-193">If the server instance is currently hosting the primary replica of an availability group that you want to keep, we recommend that you manually fail over the availability group to a synchronized secondary replica, if possible.</span></span> <span data-ttu-id="f36d3-194">Дополнительные сведения см. в разделе [Выполнение запланированного перехода на другой ресурс вручную для группы доступности (SQL Server)](perform-a-planned-manual-failover-of-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f36d3-194">For more information, see [Perform a Planned Manual Failover of an Availability Group &#40;SQL Server&#41;](perform-a-planned-manual-failover-of-an-availability-group-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="f36d3-195">Удалите все локальные вторичные реплики.</span><span class="sxs-lookup"><span data-stu-id="f36d3-195">Remove all local secondary replicas.</span></span> <span data-ttu-id="f36d3-196">Дополнительные сведения см. в разделе [Удаление вторичной реплики из группы доступности (SQL Server)](remove-a-secondary-replica-from-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f36d3-196">For more information, see [Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;](remove-a-secondary-replica-from-an-availability-group-sql-server.md).</span></span>  
  
###  <a name="using-sql-server-configuration-manager"></a><a name="SQLCM3Procedure"></a> <span data-ttu-id="f36d3-197">Использование диспетчера конфигурации SQL Server</span><span class="sxs-lookup"><span data-stu-id="f36d3-197">Using SQL Server Configuration Manager</span></span>  
 <span data-ttu-id="f36d3-198">**Отключение функции AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="f36d3-198">**To disable AlwaysOn**</span></span>  
  
1.  <span data-ttu-id="f36d3-199">Выполните подключение к узлу отказоустойчивой кластеризации Windows Server (WSFC), где размещен экземпляр [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], в котором требуется отключить группы доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="f36d3-199">Connect to the Windows Server Failover Clustering (WSFC) node that hosts the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance where you want to disable AlwaysOn Availability Groups.</span></span>  
  
2.  <span data-ttu-id="f36d3-200">В меню **Пуск** последовательно укажите пункты **Все программы**, [!INCLUDE[ssCurrentUI](../../../includes/sscurrentui-md.md)], **Средства настройки**и выберите пункт **Диспетчер конфигурации SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="f36d3-200">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and click **SQL Server Configuration Manager**.</span></span>  
  
3.  <span data-ttu-id="f36d3-201">В **Диспетчер конфигурации SQL Server**щелкните **SQL Server службы**, щелкните правой кнопкой мыши SQL Server (\*\* < *`instance name`*>)\*\*, где **<*`instance name`*>** — имя локального экземпляра сервера, для которого требуется отключить группы доступности AlwaysOn, и нажмите кнопку **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="f36d3-201">In **SQL Server Configuration Manager**, click **SQL Server Services**, right-click SQL Server (**<*`instance name`*>)**, where **<*`instance name`*>** is the name of a local server instance for which you want to disable AlwaysOn Availability Groups, and click **Properties**.</span></span>  
  
4.  <span data-ttu-id="f36d3-202">На вкладке**Высокий уровень доступности AlwaysOn**снимите флажок **Включить группы доступности AlwaysOn** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f36d3-202">On the**AlwaysOn High Availability**tab, deselect the **Enable AlwaysOn Availability Groups** check box, and click **OK**.</span></span>  
  
     [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="f36d3-203">сохранит изменения и перезапустит службу [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f36d3-203">Configuration Manager saves your change and restarts the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service.</span></span> <span data-ttu-id="f36d3-204">После перезапуска службы [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] функция AlwaysOn будет отключена, а свойство `IsHadrEnabled` будет установлено в значение 0, указывающее на то, группы доступности AlwaysOn отключены.</span><span class="sxs-lookup"><span data-stu-id="f36d3-204">When the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service restarts, AlwaysOn will be disabled, and the `IsHadrEnabled` server property will be set to 0, to indicate that AlwaysOn Availability Groups is disabled.</span></span>  
  
5.  <span data-ttu-id="f36d3-205">Рекомендуется ознакомиться с разделом [Дальнейшие действия. После отключения AlwaysOn](#FollowUp)ниже в этой статье.</span><span class="sxs-lookup"><span data-stu-id="f36d3-205">We recommend that you read the information in [Follow Up: After Disabling AlwaysOn](#FollowUp), later in this topic.</span></span>  
  
###  <a name="using-sql-server-powershell"></a><a name="PScmd3Procedure"></a> <span data-ttu-id="f36d3-206">Использование SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="f36d3-206">Using SQL Server PowerShell</span></span>  
 <span data-ttu-id="f36d3-207">**Отключение функции AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="f36d3-207">**To disable AlwaysOn**</span></span>  
  
1.  <span data-ttu-id="f36d3-208">Перейдите в каталог ( `cd` ) на экземпляр сервера, включенный в данный момент, который вы хотите включить для группы доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="f36d3-208">Change directory (`cd`) to a currently-enabled server instance that you want to disenable for AlwaysOn Availability Groups.</span></span>  
  
2.  <span data-ttu-id="f36d3-209">С помощью командлета `Disable-SqlAlwaysOn` включите группы доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="f36d3-209">Use the `Disable-SqlAlwaysOn` cmdlet to enable AlwaysOn Availability Groups.</span></span>  
  
     <span data-ttu-id="f36d3-210">Например, следующая команда отключает группы доступности AlwaysOn на экземпляре SQL Server (*Computer* \\ *экземпляре*компьютера).</span><span class="sxs-lookup"><span data-stu-id="f36d3-210">For example, the following command disables AlwaysOn Availability Groups on an instance of SQL Server (*Computer*\\*Instance*).</span></span>  <span data-ttu-id="f36d3-211">Эта команда требует перезапуска экземпляра, который будет предложено подтвердить.</span><span class="sxs-lookup"><span data-stu-id="f36d3-211">This command requires restarting the instance, and you will be prompted to confirm this restart.</span></span>  
  
    ```powershell
    Disable-SqlAlwaysOn -Path SQLSERVER:\SQL\Computer\Instance  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="f36d3-212">Сведения о том, как управлять тем `Disable-SqlAlwaysOn` , перезапускается ли командлет [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , см. в разделе Когда командлет перезапускает [службу SQL Server?](#WhenCmdletRestartsSQL)далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="f36d3-212">For information about how to control whether the `Disable-SqlAlwaysOn` cmdlet restarts the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service, see [When Does a Cmdlet Restart the SQL Server Service?](#WhenCmdletRestartsSQL), later in this topic.</span></span>  
  
     <span data-ttu-id="f36d3-213">Чтобы просмотреть синтаксис командлета, воспользуйтесь командлетом `Get-Help` в среде [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f36d3-213">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="f36d3-214">Дополнительные сведения см. в разделе [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="f36d3-214">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="f36d3-215">**Настройка и использование поставщика SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="f36d3-215">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="f36d3-216">Поставщик SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="f36d3-216">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
###  <a name="follow-up-after-disabling-alwayson"></a><a name="FollowUp"></a><span data-ttu-id="f36d3-217">Дальнейшие действия. После отключения AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="f36d3-217">Follow Up: After Disabling AlwaysOn</span></span>  
 <span data-ttu-id="f36d3-218">После отключения групп доступности AlwaysOn экземпляр [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] необходимо перезапустить.</span><span class="sxs-lookup"><span data-stu-id="f36d3-218">After you disable AlwaysOn Availability Groups, the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] must be restarted.</span></span> <span data-ttu-id="f36d3-219">Диспетчер конфигурации SQL Server автоматически перезапускает экземпляр сервера.</span><span class="sxs-lookup"><span data-stu-id="f36d3-219">SQL Configuration Manager restarts the server instance automatically.</span></span> <span data-ttu-id="f36d3-220">Но если использовался командлет `Disable-SqlAlwaysOn`, то потребуется перезапустить экземпляр сервера вручную.</span><span class="sxs-lookup"><span data-stu-id="f36d3-220">However, if you used the `Disable-SqlAlwaysOn` cmdlet, you will need to restart the server instance manually.</span></span> <span data-ttu-id="f36d3-221">Дополнительные сведения см. в статье [sqlservr Application](../../../tools/sqlservr-application.md).</span><span class="sxs-lookup"><span data-stu-id="f36d3-221">For more information, see [sqlservr Application](../../../tools/sqlservr-application.md).</span></span>  
  
 <span data-ttu-id="f36d3-222">На перезапущенном экземпляре сервера происходит следующее:</span><span class="sxs-lookup"><span data-stu-id="f36d3-222">On the restarted server instance:</span></span>  
  
-   <span data-ttu-id="f36d3-223">базы данных обеспечения доступности не запускаются при запуске сервер SQL Server, из-за чего они становятся недоступными.</span><span class="sxs-lookup"><span data-stu-id="f36d3-223">Availability databases do not start up at SQL Server startup, making them inaccessible.</span></span>  
  
-   <span data-ttu-id="f36d3-224">Единственная поддерживаемая инструкция AlwaysOn [!INCLUDE[tsql](../../../includes/tsql-md.md)] — [DROP AVAILABILITY GROUP](/sql/t-sql/statements/drop-availability-group-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f36d3-224">The only supported AlwaysOn [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement is [DROP AVAILABILITY GROUP](/sql/t-sql/statements/drop-availability-group-transact-sql).</span></span> <span data-ttu-id="f36d3-225">Инструкции CREATE AVAILABILITY GROUP, ALTER AVAILABILITY GROUP и параметры SET HADR инструкции ALTER DATABASE не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="f36d3-225">CREATE AVAILABILITY GROUP, ALTER AVAILABILITY GROUP, and the SET HADR options of ALTER DATABASE are not supported.</span></span>  
  
-   <span data-ttu-id="f36d3-226">При отключении групп доступности AlwaysOn метаданные службы [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] и данные конфигурации [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] в WSFC не затрагиваются.</span><span class="sxs-lookup"><span data-stu-id="f36d3-226">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] metadata and [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] configuration data in WSFC are unaffected by disabling AlwaysOn Availability Groups.</span></span>  
  
 <span data-ttu-id="f36d3-227">Если нужно полностью отключить группы доступности AlwaysOn в каждом экземпляре сервера, где размещается реплика доступности для одной или нескольких групп доступности, то рекомендуется выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="f36d3-227">If you permanently disable AlwaysOn Availability Groups on every server instance that hosts an availability replica for one or more availability groups, we recommend that you complete the following steps:</span></span>  
  
1.  <span data-ttu-id="f36d3-228">Если перед отключением AlwaysOn локальные реплики доступности не удалялись, удалите все группы доступности, для которых на экземпляре сервера размещается реплика доступности.</span><span class="sxs-lookup"><span data-stu-id="f36d3-228">If you did not remove the local availability replicas before disabling AlwaysOn, delete (drop) each availability group for which the server instance is hosting an availability replica.</span></span> <span data-ttu-id="f36d3-229">Сведения об удалении группы доступности см. в разделе [Удаление группы доступности (SQL Server)](remove-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f36d3-229">For information about deleting an availability group, see [Remove an Availability Group &#40;SQL Server&#41;](remove-an-availability-group-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="f36d3-230">Чтобы удалить оставшиеся метаданные, удалите все затронутые группы доступности на экземпляре сервера, который входит в состав исходного кластера WSFC.</span><span class="sxs-lookup"><span data-stu-id="f36d3-230">To remove the metadata left behind, delete (drop) each affected availability group on a server instance that is part of the original WSFC cluster.</span></span>  
  
3.  <span data-ttu-id="f36d3-231">Все базы данных-источники остаются доступными для всех подключений, однако синхронизация данных между главной и базами данных-получателями останавливается.</span><span class="sxs-lookup"><span data-stu-id="f36d3-231">Any primary databases continue to be accessible to all connections but the data synchronization between the primary and secondary databases stops.</span></span>  
  
4.  <span data-ttu-id="f36d3-232">Базы данных-получатели переводятся в состояние RESTORING.</span><span class="sxs-lookup"><span data-stu-id="f36d3-232">The secondary databases enter the RESTORING state.</span></span> <span data-ttu-id="f36d3-233">Вы можете либо удалить эти базы данных, либо восстановить их при помощи функции RESTORE WITH RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="f36d3-233">You can delete them, or you can restore them by using RESTORE WITH RECOVERY.</span></span> <span data-ttu-id="f36d3-234">Однако восстановленные базы данных больше не будут участвовать в синхронизации данных группы доступности.</span><span class="sxs-lookup"><span data-stu-id="f36d3-234">However, restored databases are no longer participating in availability-group data synchronization.</span></span>  
  
##  <a name="when-does-a-cmdlet-restart-the-sql-server-service"></a><a name="WhenCmdletRestartsSQL"></a> <span data-ttu-id="f36d3-235">Когда командлет перезапускает службу SQL Server?</span><span class="sxs-lookup"><span data-stu-id="f36d3-235">When Does a Cmdlet Restart the SQL Server Service?</span></span>  
 <span data-ttu-id="f36d3-236">В экземпляре сервера, запущенном в настоящее время, использование командлетов `Enable-SqlAlwaysOn` или `Disable-SqlAlwaysOn` для смены текущей настройки функции AlwaysOn может стать причиной перезапуска службы SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f36d3-236">On a server instance that is currently running, using `Enable-SqlAlwaysOn` or `Disable-SqlAlwaysOn` to change the current AlwaysOn setting could cause the SQL Server service to restart.</span></span> <span data-ttu-id="f36d3-237">Алгоритм перезапуска зависит от следующих условий:</span><span class="sxs-lookup"><span data-stu-id="f36d3-237">The restart behavior on depends on the following conditions:</span></span>  
  
|<span data-ttu-id="f36d3-238">указан параметр -NoServiceRestart;</span><span class="sxs-lookup"><span data-stu-id="f36d3-238">-NoServiceRestart parameter specified</span></span>|<span data-ttu-id="f36d3-239">указан параметр -Force.</span><span class="sxs-lookup"><span data-stu-id="f36d3-239">-Force parameter specified</span></span>|<span data-ttu-id="f36d3-240">Перезапущена ли служба [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ?</span><span class="sxs-lookup"><span data-stu-id="f36d3-240">Is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service restarted?</span></span>|  
|--------------------------------------------|---------------------------------|---------------------------------------------------------|  
|<span data-ttu-id="f36d3-241">Нет</span><span class="sxs-lookup"><span data-stu-id="f36d3-241">No</span></span>|<span data-ttu-id="f36d3-242">Нет</span><span class="sxs-lookup"><span data-stu-id="f36d3-242">No</span></span>|<span data-ttu-id="f36d3-243">По умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f36d3-243">By default.</span></span> <span data-ttu-id="f36d3-244">Однако командлет выводит следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="f36d3-244">But the cmdlet prompts you as follows:</span></span><br /><br /> <span data-ttu-id="f36d3-245">**Чтобы выполнить это действие, необходимо перезапустить службу SQL Server для экземпляра сервера "<имя_экземпляра>". Продолжить?**</span><span class="sxs-lookup"><span data-stu-id="f36d3-245">**To complete this action, we must restart the SQL Server service for server instance '<instance_name>'. Do you want to continue?**</span></span><br /><br /> <span data-ttu-id="f36d3-246">**[Y] Yes  [N] No  [S] Suspend  [?] Help (значение по умолчанию — "Y"):**</span><span class="sxs-lookup"><span data-stu-id="f36d3-246">**[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):**</span></span><br /><br /> <span data-ttu-id="f36d3-247">Если указать **N** или **S**, служба не будет перезапущена.</span><span class="sxs-lookup"><span data-stu-id="f36d3-247">If you specify **N** or **S**, the service is not restarted.</span></span>|  
|<span data-ttu-id="f36d3-248">Нет</span><span class="sxs-lookup"><span data-stu-id="f36d3-248">No</span></span>|<span data-ttu-id="f36d3-249">Да</span><span class="sxs-lookup"><span data-stu-id="f36d3-249">Yes</span></span>|<span data-ttu-id="f36d3-250">Служба перезапускается.</span><span class="sxs-lookup"><span data-stu-id="f36d3-250">Service is restarted.</span></span>|  
|<span data-ttu-id="f36d3-251">Да</span><span class="sxs-lookup"><span data-stu-id="f36d3-251">Yes</span></span>|<span data-ttu-id="f36d3-252">Нет</span><span class="sxs-lookup"><span data-stu-id="f36d3-252">No</span></span>|<span data-ttu-id="f36d3-253">Служба не перезапускается.</span><span class="sxs-lookup"><span data-stu-id="f36d3-253">Service is not restarted.</span></span>|  
|<span data-ttu-id="f36d3-254">Да</span><span class="sxs-lookup"><span data-stu-id="f36d3-254">Yes</span></span>|<span data-ttu-id="f36d3-255">Да</span><span class="sxs-lookup"><span data-stu-id="f36d3-255">Yes</span></span>|<span data-ttu-id="f36d3-256">Служба не перезапускается.</span><span class="sxs-lookup"><span data-stu-id="f36d3-256">Service is not restarted.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f36d3-257">См. также:</span><span class="sxs-lookup"><span data-stu-id="f36d3-257">See Also</span></span>  
 <span data-ttu-id="f36d3-258">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f36d3-258">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="f36d3-259">SERVERPROPERTY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f36d3-259">SERVERPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/serverproperty-transact-sql)  
