---
title: Настройка параметров свойства FailureConditionLevel | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
ms.assetid: 513dd179-9a46-46da-9fdd-7632cf6d0816
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8924b864d7cc8be078b370e3182713114f54ff6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659286"
---
# <a name="configure-failureconditionlevel-property-settings"></a><span data-ttu-id="01556-102">Настройка параметров свойства FailureConditionLevel</span><span class="sxs-lookup"><span data-stu-id="01556-102">Configure FailureConditionLevel Property Settings</span></span>
  <span data-ttu-id="01556-103">Свойство FailureConditionLevel служит для задания для экземпляра отказоустойчивого кластера FCI в группе AlwaysOn условий отработки отказа или перезапуска.</span><span class="sxs-lookup"><span data-stu-id="01556-103">Use the FailureConditionLevel property to set the conditions for the AlwaysOn Failover Cluster Instance (FCI) to fail over or restart.</span></span> <span data-ttu-id="01556-104">Изменения значения этого свойства вступают в силу немедленно, без перезапуска службы отказоустойчивого кластера Windows Server или ресурса отказоустойчивого кластера SQL Server.</span><span class="sxs-lookup"><span data-stu-id="01556-104">Changes to this property are applied immediately without requiring a restart of the Windows Server Failover Cluster (WSFC) service or the FCI resource.</span></span>  
  
-   <span data-ttu-id="01556-105">**Перед началом работы**  [Параметры свойства FailureConditionLevel](#Restrictions), [Безопасность](#Security)</span><span class="sxs-lookup"><span data-stu-id="01556-105">**Before you begin:**  [FailureConditionLevel Property Settings](#Restrictions), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="01556-106">**Настройка параметров свойства FailureConditionLevel с помощью** [PowerShell](#PowerShellProcedure), [диспетчера отказоустойчивого кластера](#WSFC), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="01556-106">**To configure the FailureConditionLevel property settings using,** [PowerShell](#PowerShellProcedure), [Failover Cluster Manager](#WSFC), [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="01556-107">Перед началом</span><span class="sxs-lookup"><span data-stu-id="01556-107">Before You Begin</span></span>  
  
###  <a name="failureconditionlevel-property-settings"></a><a name="Restrictions"></a> <span data-ttu-id="01556-108">параметры свойства FailureConditionLevel</span><span class="sxs-lookup"><span data-stu-id="01556-108">FailureConditionLevel Property Settings</span></span>  
 <span data-ttu-id="01556-109">Условия сбоя устанавливаются по прогрессирующей шкале.</span><span class="sxs-lookup"><span data-stu-id="01556-109">The failure conditions are set on an increasing scale.</span></span> <span data-ttu-id="01556-110">Каждый уровень, с 1 по 5, включает все условия предыдущих уровней, а также собственные дополнительные условия.</span><span class="sxs-lookup"><span data-stu-id="01556-110">For levels 1-5, each level includes all the conditions from the previous levels in addition to its own conditions.</span></span> <span data-ttu-id="01556-111">Это означает, что с каждым уровнем вероятность отработки отказа или перезапуска повышается.</span><span class="sxs-lookup"><span data-stu-id="01556-111">This means that with each level, there is an increased probability of a failover or restart.</span></span>  <span data-ttu-id="01556-112">Дополнительные сведения см. в подразделе «Определение сбоев» раздела [Failover Policy for Failover Cluster Instances](failover-policy-for-failover-cluster-instances.md) .</span><span class="sxs-lookup"><span data-stu-id="01556-112">For more information, see the "Determining Failures" section of the [Failover Policy for Failover Cluster Instances](failover-policy-for-failover-cluster-instances.md) topic.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="01556-113">безопасность</span><span class="sxs-lookup"><span data-stu-id="01556-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="01556-114">Permissions</span><span class="sxs-lookup"><span data-stu-id="01556-114">Permissions</span></span>  
 <span data-ttu-id="01556-115">Требует разрешения ALTER SETTINGS и VIEW SERVER STATE.</span><span class="sxs-lookup"><span data-stu-id="01556-115">Requires ALTER SETTINGS and VIEW SERVER STATE permissions.</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="01556-116">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="01556-116">Using PowerShell</span></span>  
  
### <a name="to-configure-failureconditionlevel-settings"></a><span data-ttu-id="01556-117">Настройка параметров свойства FailureConditionLevel</span><span class="sxs-lookup"><span data-stu-id="01556-117">To configure FailureConditionLevel settings</span></span>  
  
1.  <span data-ttu-id="01556-118">Запустите повышенный режим Windows PowerShell с помощью команды **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="01556-118">Start an elevated Windows PowerShell via **Run as Administrator**.</span></span>  
  
2.  <span data-ttu-id="01556-119">Импортируйте модуль `FailoverClusters` для включения командлетов кластера.</span><span class="sxs-lookup"><span data-stu-id="01556-119">Import the `FailoverClusters` module to enable cluster cmdlets.</span></span>  
  
3.  <span data-ttu-id="01556-120">Используйте `Get-ClusterResource` командлет, чтобы найти [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ресурс, а затем используйте `Set-ClusterParameter` командлет, чтобы задать свойство **FailureConditionLevel** для экземпляра отказоустойчивого кластера.</span><span class="sxs-lookup"><span data-stu-id="01556-120">Use the `Get-ClusterResource` cmdlet to find the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] resource, then use `Set-ClusterParameter` cmdlet to set the **FailureConditionLevel** property for a Failover Cluster Instance.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="01556-121">Каждый раз при открытии нового окна Powershell нужно импортировать модуль `FailoverClusters`.</span><span class="sxs-lookup"><span data-stu-id="01556-121">Every time you open a new PowerShell window, you need to import the `FailoverClusters` module.</span></span>  

 <span data-ttu-id="01556-122">В следующем примере параметр FailureConditionLevel экземпляра в ресурсе [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] «`SQL Server (INST1)`» изменяется на обработку отказа или перезапуск при критических ошибках сервера.</span><span class="sxs-lookup"><span data-stu-id="01556-122">The following example changes the FailureConditionLevel setting on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] resource "`SQL Server (INST1)`" to fail over or restart on critical server errors.</span></span>  
  
```powershell  
Import-Module FailoverClusters  
  
$fci = "SQL Server (INST1)"  
Get-ClusterResource $fci | Set-ClusterParameter FailureConditionLevel 3
```  
  
### <a name="related-content-powershell"></a><span data-ttu-id="01556-123">См. также (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="01556-123">Related Content (PowerShell)</span></span>  
  
-   <span data-ttu-id="01556-124">[Кластеризация и высокая доступность](https://techcommunity.microsoft.com/t5/failover-clustering/bg-p/FailoverClustering) (блог группы отказоустойчивой кластеризации и балансировки сетевой нагрузки)</span><span class="sxs-lookup"><span data-stu-id="01556-124">[Clustering and High-Availability](https://techcommunity.microsoft.com/t5/failover-clustering/bg-p/FailoverClustering) (Failover Clustering and Network Load Balancing Team Blog)</span></span>  
  
-   <span data-ttu-id="01556-125">[Приступая к работе с Windows PowerShell в отказоустойчивом кластере](https://technet.microsoft.com/library/ee619762\(WS.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="01556-125">[Getting Started with Windows PowerShell on a Failover Cluster](https://technet.microsoft.com/library/ee619762\(WS.10\).aspx)</span></span>  
  
-   [<span data-ttu-id="01556-126">Команды ресурса кластера и соответствующие командлеты Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="01556-126">Cluster resource commands and equivalent Windows PowerShell cmdlets</span></span>](https://msdn.microsoft.com/library/ee619744.aspx#BKMK_resource)  
  
##  <a name="using-the-failover-cluster-manager-snap-in"></a><a name="WSFC"></a> <span data-ttu-id="01556-127">Использование оснастки «Диспетчер отказоустойчивости кластеров»</span><span class="sxs-lookup"><span data-stu-id="01556-127">Using the Failover Cluster Manager Snap-in</span></span>  

### <a name="to-configure-failureconditionlevel-property-settings"></a><span data-ttu-id="01556-128">Настройка параметров свойства FailureConditionLevel</span><span class="sxs-lookup"><span data-stu-id="01556-128">To configure FailureConditionLevel property settings</span></span>
  
1.  <span data-ttu-id="01556-129">Откройте оснастку «Диспетчер отказоустойчивости кластеров»</span><span class="sxs-lookup"><span data-stu-id="01556-129">Open the Failover Cluster Manager snap-in.</span></span>  
  
2.  <span data-ttu-id="01556-130">Разверните узел **Службы и приложения** и выберите требуемый кластер FCI.</span><span class="sxs-lookup"><span data-stu-id="01556-130">Expand the **Services and Applications** and select the FCI.</span></span>  
  
3.  <span data-ttu-id="01556-131">Щелкните правой кнопкой мыши **Ресурс SQL Server** в разделе **Другие ресурсы**и выберите пункт **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="01556-131">Right-click the **SQL Server resource** under **Other Resources**, and then select **Properties** from the menu.</span></span> <span data-ttu-id="01556-132">Откроется диалоговое окно **Свойства** ресурсов SQL Server.</span><span class="sxs-lookup"><span data-stu-id="01556-132">The SQL Server resource **Properties** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="01556-133">Перейдите на вкладку **Свойства** , введите необходимое значение свойства **FaliureConditionLevel** и нажмите кнопку **ОК** , чтобы применить изменение.</span><span class="sxs-lookup"><span data-stu-id="01556-133">Select the **Properties** tab, enter the desired value for the **FaliureConditionLevel** property, and then click **OK** to apply the change.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="01556-134">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="01556-134">Using Transact-SQL</span></span>  

### <a name="to-configure-failureconditionlevel-property-settings"></a><span data-ttu-id="01556-135">Настройка параметров свойства FailureConditionLevel</span><span class="sxs-lookup"><span data-stu-id="01556-135">To configure FailureConditionLevel property settings</span></span>
  
 <span data-ttu-id="01556-136">С помощью инструкции [ALTER SERVER CONFIGURATION](/sql/t-sql/statements/alter-server-configuration-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] можно задать значение свойства FailureConditionLevel.</span><span class="sxs-lookup"><span data-stu-id="01556-136">Using the [ALTER SERVER CONFIGURATION](/sql/t-sql/statements/alter-server-configuration-transact-sql)[!INCLUDE[tsql](../../../includes/tsql-md.md)] statement, you can specify the FailureConditionLevel property value.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="01556-137">Примеры (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="01556-137">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="01556-138">Следующий пример назначает свойству FailureConditionLevel значение 0, которое указывает, что при любых условиях сбоя отработка отказа или перезапуск не будет выполняться автоматически.</span><span class="sxs-lookup"><span data-stu-id="01556-138">The following example sets the FailureConditionLevel property to 0, indicating that failover or restart will not be triggered automatically on any failure conditions.</span></span>  
  
```sql
ALTER SERVER CONFIGURATION SET FAILOVER CLUSTER PROPERTY FailureConditionLevel = 0;  
```  
  
## <a name="see-also"></a><span data-ttu-id="01556-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="01556-139">See Also</span></span>  
 <span data-ttu-id="01556-140">[sp_server_diagnostics (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="01556-140">[sp_server_diagnostics &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-server-diagnostics-transact-sql) </span></span>  
 [<span data-ttu-id="01556-141">Failover Policy for Failover Cluster Instances</span><span class="sxs-lookup"><span data-stu-id="01556-141">Failover Policy for Failover Cluster Instances</span></span>](failover-policy-for-failover-cluster-instances.md)  
