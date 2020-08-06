---
title: Настройка параметров свойства HealthCheckTimeout | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
ms.assetid: 3bbeb979-e6fc-4184-ad6e-cca62108de74
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a38cd6e9e4718a2f1c136e5412cde340e92f14c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659284"
---
# <a name="configure-healthchecktimeout-property-settings"></a><span data-ttu-id="9982a-102">Настройка параметров свойства HealthCheckTimeout</span><span class="sxs-lookup"><span data-stu-id="9982a-102">Configure HealthCheckTimeout Property Settings</span></span>
  <span data-ttu-id="9982a-103">Параметр HealthCheckTimeout используется для задания временного интервала (в миллисекундах) ожидания библиотекой ресурсов SQL Server данных, возвращаемых хранимой процедурой [sp_server_diagnostics](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) , до появления сообщения о том, что экземпляр отказоустойчивого кластера AlwaysOn SQL Server (FCI) не отвечает.</span><span class="sxs-lookup"><span data-stu-id="9982a-103">The HealthCheckTimeout setting is used to specify the length of time, in milliseconds, that the SQL Server resource DLL should wait for information returned by the [sp_server_diagnostics](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) stored procedure before reporting the AlwaysOn Failover Cluster Instance (FCI) as unresponsive.</span></span> <span data-ttu-id="9982a-104">Изменения, внесенные в параметры времени ожидания, вступают в силу немедленно и не требуют перезапуска ресурса SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9982a-104">Changes that are made to the timeout settings are effective immediately and do not require a restart of the SQL Server resource.</span></span>  
  
-   <span data-ttu-id="9982a-105">**Перед началом работы**  [Ограничения](#Limits), [Безопасность](#Security)</span><span class="sxs-lookup"><span data-stu-id="9982a-105">**Before you begin:**  [Limitations and Restrictions](#Limits), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="9982a-106">**Настройка параметра HealthCheckTimeout с помощью следующих средств:**  [PowerShell](#PowerShellProcedure), [диспетчер отказоустойчивого кластера](#WSFC), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="9982a-106">**To Configure the HeathCheckTimeout setting, using:**  [PowerShell](#PowerShellProcedure), [Failover Cluster Manager](#WSFC), [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9982a-107">Перед началом</span><span class="sxs-lookup"><span data-stu-id="9982a-107">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Limits"></a> <span data-ttu-id="9982a-108">Ограничения</span><span class="sxs-lookup"><span data-stu-id="9982a-108">Limitations and Restrictions</span></span>  
 <span data-ttu-id="9982a-109">Значение по умолчанию для этого свойства составляет 60 000 миллисекунд (60 секунд).</span><span class="sxs-lookup"><span data-stu-id="9982a-109">The default value for this property is 60,000 milliseconds (60 seconds).</span></span> <span data-ttu-id="9982a-110">Минимальное значение равно 15 000 миллисекундам (15 секундам).</span><span class="sxs-lookup"><span data-stu-id="9982a-110">The minimum value is 15,000 milliseconds (15 seconds).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9982a-111">безопасность</span><span class="sxs-lookup"><span data-stu-id="9982a-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9982a-112">Permissions</span><span class="sxs-lookup"><span data-stu-id="9982a-112">Permissions</span></span>  
 <span data-ttu-id="9982a-113">Требует разрешения ALTER SETTINGS и VIEW SERVER STATE.</span><span class="sxs-lookup"><span data-stu-id="9982a-113">Requires ALTER SETTINGS and VIEW SERVER STATE permissions.</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="9982a-114">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="9982a-114">Using PowerShell</span></span>  
  
### <a name="to-configure-healthchecktimeout-settings"></a><span data-ttu-id="9982a-115">Настройка параметров HealthCheckTimeout</span><span class="sxs-lookup"><span data-stu-id="9982a-115">To configure HealthCheckTimeout settings</span></span>  
  
1.  <span data-ttu-id="9982a-116">Запустите повышенный режим Windows PowerShell с помощью команды **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="9982a-116">Start an elevated Windows PowerShell via **Run as Administrator**.</span></span>  
  
2.  <span data-ttu-id="9982a-117">Импортируйте модуль `FailoverClusters` для включения командлетов кластера.</span><span class="sxs-lookup"><span data-stu-id="9982a-117">Import the `FailoverClusters` module to enable cluster cmdlets.</span></span>  
  
3.  <span data-ttu-id="9982a-118">Используйте `Get-ClusterResource` командлет, чтобы найти [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ресурс, а затем используйте `Set-ClusterParameter` командлет, чтобы задать свойство **HealthCheckTimeout** для экземпляра отказоустойчивого кластера.</span><span class="sxs-lookup"><span data-stu-id="9982a-118">Use the `Get-ClusterResource` cmdlet to find the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] resource, then use `Set-ClusterParameter` cmdlet to set the **HealthCheckTimeout** property for the failover cluster instance.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="9982a-119">Каждый раз при открытии нового окна Powershell нужно импортировать модуль `FailoverClusters`.</span><span class="sxs-lookup"><span data-stu-id="9982a-119">Every time you open a new PowerShell window, you need to import the `FailoverClusters` module.</span></span>  

 <span data-ttu-id="9982a-120">В следующем примере демонстрируется изменение параметра HealthCheckTimeout ресурса [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] «`SQL Server (INST1)`» на 60 000 миллисекунд.</span><span class="sxs-lookup"><span data-stu-id="9982a-120">The following example changes the HealthCheckTimeout setting on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] resource "`SQL Server (INST1)`" to 60000 milliseconds.</span></span>  
  
```powershell  
Import-Module FailoverClusters  
  
$fci = "SQL Server (INST1)"  
Get-ClusterResource $fci | Set-ClusterParameter HealthCheckTimeout 60000  
```  
  
### <a name="related-content-powershell"></a><span data-ttu-id="9982a-121">См. также (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="9982a-121">Related Content (PowerShell)</span></span>  
  
-   <span data-ttu-id="9982a-122">[Кластеризация и высокая доступность](https://techcommunity.microsoft.com/t5/failover-clustering/bg-p/FailoverClustering) (блог группы отказоустойчивой кластеризации и балансировки сетевой нагрузки)</span><span class="sxs-lookup"><span data-stu-id="9982a-122">[Clustering and High-Availability](https://techcommunity.microsoft.com/t5/failover-clustering/bg-p/FailoverClustering) (Failover Clustering and Network Load Balancing Team Blog)</span></span>  
  
-   <span data-ttu-id="9982a-123">[Приступая к работе с Windows PowerShell в отказоустойчивом кластере](https://technet.microsoft.com/library/ee619762\(WS.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="9982a-123">[Getting Started with Windows PowerShell on a Failover Cluster](https://technet.microsoft.com/library/ee619762\(WS.10\).aspx)</span></span>  
  
-   [<span data-ttu-id="9982a-124">Команды ресурса кластера и соответствующие командлеты Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9982a-124">Cluster resource commands and equivalent Windows PowerShell cmdlets</span></span>](https://msdn.microsoft.com/library/ee619744.aspx#BKMK_resource)  
  
##  <a name="using-the-failover-cluster-manager-snap-in"></a><a name="WSFC"></a> <span data-ttu-id="9982a-125">Использование оснастки «Диспетчер отказоустойчивости кластеров»</span><span class="sxs-lookup"><span data-stu-id="9982a-125">Using the Failover Cluster Manager Snap-in</span></span>  
 <span data-ttu-id="9982a-126">**Для настройки параметров HealthCheckTimeout**</span><span class="sxs-lookup"><span data-stu-id="9982a-126">**To configure HealthCheckTimeout setting**</span></span>  
  
1.  <span data-ttu-id="9982a-127">Откройте оснастку «Диспетчер отказоустойчивости кластеров»</span><span class="sxs-lookup"><span data-stu-id="9982a-127">Open the Failover Cluster Manager snap-in.</span></span>  
  
2.  <span data-ttu-id="9982a-128">Раскройте узел **Службы и приложения** и выберите требуемый кластер FCI.</span><span class="sxs-lookup"><span data-stu-id="9982a-128">Expand **Services and Applications** and select the FCI.</span></span>  
  
3.  <span data-ttu-id="9982a-129">Щелкните правой кнопкой мыши **Ресурс SQL Server** в разделе **Другие ресурсы** и выберите из контекстного меню пункт **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="9982a-129">Right-click the **SQL Server resource** under **Other Resources** and select **Properties** from the right-click menu.</span></span> <span data-ttu-id="9982a-130">Откроется диалоговое окно **Свойства** ресурсов SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9982a-130">The SQL Server resource **Properties** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="9982a-131">Перейдите на вкладку **Свойства** , введите желаемое значение свойства **HealthCheckTimeout** и нажмите кнопку **ОК** , чтобы применить изменение.</span><span class="sxs-lookup"><span data-stu-id="9982a-131">Select the **Properties** tab, enter the desired value for the **HealthCheckTimeout** property, and then click **OK** to apply the change.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9982a-132">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9982a-132">Using Transact-SQL</span></span>  
 <span data-ttu-id="9982a-133">С помощью инструкции [ALTER Server Configuration](/sql/t-sql/statements/alter-server-configuration-transact-sql) [!INCLUDE[tsql](../../../includes/tsql-md.md)] можно указать значение свойства HealthCheckTimeOut.</span><span class="sxs-lookup"><span data-stu-id="9982a-133">Using the [ALTER SERVER CONFIGURATION](/sql/t-sql/statements/alter-server-configuration-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] statement, you can specify the HealthCheckTimeOut property value.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="9982a-134">Примеры (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="9982a-134">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="9982a-135">В следующем примере для параметра HealthCheckTimeout устанавливается значение, равное 15 000 миллисекунд (15 секунд).</span><span class="sxs-lookup"><span data-stu-id="9982a-135">The following example sets the HealthCheckTimeout option to 15,000 milliseconds (15 seconds).</span></span>  
  
```sql
ALTER SERVER CONFIGURATION   
SET FAILOVER CLUSTER PROPERTY HealthCheckTimeout = 15000;  
```  
  
## <a name="see-also"></a><span data-ttu-id="9982a-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="9982a-136">See Also</span></span>  
 [<span data-ttu-id="9982a-137">Failover Policy for Failover Cluster Instances</span><span class="sxs-lookup"><span data-stu-id="9982a-137">Failover Policy for Failover Cluster Instances</span></span>](failover-policy-for-failover-cluster-instances.md)  
