---
title: Удаление экземпляра SQL Server из служебной программы SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.utility.remove.f1
ms.assetid: ae1d126a-46d2-47bf-b339-17c743df6491
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6c09897fcd3ac6d82308288391cf54176eef49d9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668854"
---
# <a name="remove-an-instance-of-sql-server-from-the-sql-server-utility"></a><span data-ttu-id="b4c81-102">Удаление экземпляра SQL Server с помощью служебной программы SQL Server</span><span class="sxs-lookup"><span data-stu-id="b4c81-102">Remove an Instance of SQL Server from the SQL Server Utility</span></span>
  <span data-ttu-id="b4c81-103">Чтобы удалить управляемый экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] из программы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="b4c81-103">Use the following steps to remove a managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span> <span data-ttu-id="b4c81-104">Эта процедура используется для удаления экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] из списка пункта управления программой и остановки сбора данных программой [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b4c81-104">This procedure removes the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the UCP list view and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility data collection stops.</span></span> <span data-ttu-id="b4c81-105">Экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не удален.</span><span class="sxs-lookup"><span data-stu-id="b4c81-105">The instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not uninstalled.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b4c81-106">Перед тем как использовать эту процедуру для удаления экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] из программы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , убедитесь, что на удаляемом экземпляре работают службы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и агента SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b4c81-106">Before you use this procedure to remove an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility, make sure that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and SQL Server Agent services are running on the instance to remove.</span></span>  
  
1.  <span data-ttu-id="b4c81-107">В обозревателе программы в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]щелкните узел **Управляемые экземпляры**.</span><span class="sxs-lookup"><span data-stu-id="b4c81-107">From the Utility Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], click on **Managed Instances**.</span></span> <span data-ttu-id="b4c81-108">На панели содержимого обозревателя программы просмотрите список управляемых экземпляров [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b4c81-108">Observe the list view of managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in the Utility Explorer content pane.</span></span>  
  
2.  <span data-ttu-id="b4c81-109">В столбце **Имя экземпляра SQL Server** списка выберите экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , который требуется удалить из программы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b4c81-109">In the **SQL Server Instance Name** column of the list view, select the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance to remove from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span> <span data-ttu-id="b4c81-110">Щелкните правой кнопкой мыши удаляемый экземпляр и выберите команду **Удалить управляемый экземпляр…** .</span><span class="sxs-lookup"><span data-stu-id="b4c81-110">Right-click on the instance to remove, and select **Remove Managed Instance...**.</span></span>  
  
3.  <span data-ttu-id="b4c81-111">Укажите учетные данные с правами администратора для экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Нажмите кнопку **Подключить…** , проверьте данные в диалоговом окне **Подключение к серверу**, а затем нажмите кнопку **Подключить**.</span><span class="sxs-lookup"><span data-stu-id="b4c81-111">Specify credentials with administrator privileges for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]: Click **Connect...**, verify the information in the **Connect to Server** dialog box, then click **Connect**.</span></span> <span data-ttu-id="b4c81-112">В диалоговом окне **Удаление управляемого экземпляра** появятся данные входа.</span><span class="sxs-lookup"><span data-stu-id="b4c81-112">You will see the login information on the **Remove Managed Instance** dialog.</span></span>  
  
4.  <span data-ttu-id="b4c81-113">Чтобы подтвердить операцию, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b4c81-113">To confirm the operation, click **OK**.</span></span> <span data-ttu-id="b4c81-114">Чтобы прервать операцию, нажмите кнопку **Отмена**.</span><span class="sxs-lookup"><span data-stu-id="b4c81-114">To quit the operation, click **Cancel**.</span></span>  
  
## <a name="manually-remove-a-managed-instance-of-sql-server-from-a-sql-server-utility"></a><span data-ttu-id="b4c81-115">Удаление управляемого экземпляра SQL Server из программы SQL Server Utility вручную</span><span class="sxs-lookup"><span data-stu-id="b4c81-115">Manually Remove a Managed Instance of SQL Server from a SQL Server Utility</span></span>  
 <span data-ttu-id="b4c81-116">Эта процедура используется для удаления экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] из списка пункта управления программой и остановки сбора данных программой [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b4c81-116">This procedure removes the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the UCP list view and stops [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility data collection.</span></span> <span data-ttu-id="b4c81-117">Экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не удален.</span><span class="sxs-lookup"><span data-stu-id="b4c81-117">The instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not uninstalled.</span></span>  
  
 <span data-ttu-id="b4c81-118">Удаление управляемого экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] из программы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b4c81-118">To use PowerShell to remove a managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span> <span data-ttu-id="b4c81-119">Скрипт выполняет следующие операции.</span><span class="sxs-lookup"><span data-stu-id="b4c81-119">This script performs the following operations:</span></span>  
  
-   <span data-ttu-id="b4c81-120">Возвращает пункт управления программой по имени экземпляра сервера.</span><span class="sxs-lookup"><span data-stu-id="b4c81-120">Gets the UCP by server instance name.</span></span>  
  
-   <span data-ttu-id="b4c81-121">Удаляет управляемый экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] из программы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b4c81-121">Removes the managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span>  
  
```powershell
# Get Ucp connection  
$UcpServerInstanceName = "ComputerName\InstanceName";  
$UtilityInstance = new-object -Type Microsoft.SqlServer.Management.Smo.Server $UcpServerInstanceName;  
$UcpConnection = new-object -Type Microsoft.SqlServer.Management.Sdk.Sfc.SqlStoreConnection $UtilityInstance.ConnectionContext.SqlConnectionObject;  
$Utility = [Microsoft.SqlServer.Management.Utility.Utility]::Connect($UcpConnection);  
  
# Now remove the ManagedInstance from the SQL Server Utility  
$ServerInstanceName = "ComputerName\InstanceName";  
$Instance = new-object -Type Microsoft.SqlServer.Management.Smo.Server $ServerInstanceName;  
$InstanceConnection = new-object -Type Microsoft.SqlServer.Management.Sdk.Sfc.SqlStoreConnection $Instance.ConnectionContext.SqlConnectionObject;  
$ManagedInstance = $Utility.ManagedInstances[$ServerInstanceName];  
$ManagedInstance.Remove($InstanceConnection);  
```  
  
<span data-ttu-id="b4c81-122">Важно ссылаться на [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] имя экземпляра точно так же, как оно хранится в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b4c81-122">It's important to refer to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance name exactly as it is stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b4c81-123">Если для экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] учитывается регистр, имя экземпляра следует указывать точно в той форме, которую возвращает команда @@SERVERNAME.</span><span class="sxs-lookup"><span data-stu-id="b4c81-123">On a case-sensitive instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you must specify the instance name using the exact casing as returned by @@SERVERNAME.</span></span> 

<span data-ttu-id="b4c81-124">Чтобы получить имя управляемого экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], выполните этот запрос на управляемом экземпляре:</span><span class="sxs-lookup"><span data-stu-id="b4c81-124">To get the instance name for the managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], run this query on the managed instance:</span></span>  
  
```sql
select @@SERVERNAME AS instance_name  
```  
  
 <span data-ttu-id="b4c81-125">В этот момент управляемый экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] будет полностью удален из пункта управления программой.</span><span class="sxs-lookup"><span data-stu-id="b4c81-125">At this point, the managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is fully removed from the UCP.</span></span> <span data-ttu-id="b4c81-126">При следующем обновлении данных для программы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility он исчезнет из списка.</span><span class="sxs-lookup"><span data-stu-id="b4c81-126">It disappears from the list view the next time you refresh data for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span> <span data-ttu-id="b4c81-127">Это состояние похоже на то, когда пользователь успешно выполнил операцию удаления управляемого экземпляра в пользовательском интерфейсе среды SSMS.</span><span class="sxs-lookup"><span data-stu-id="b4c81-127">This state is identical to a user successfully going through the remove managed instance operation in the SSMS user interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4c81-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="b4c81-128">See Also</span></span>  
 <span data-ttu-id="b4c81-129">[Использование проводника служебных программ для управления служебной программой SQL Server](use-utility-explorer-to-manage-the-sql-server-utility.md) </span><span class="sxs-lookup"><span data-stu-id="b4c81-129">[Use Utility Explorer to Manage the SQL Server Utility](use-utility-explorer-to-manage-the-sql-server-utility.md) </span></span>  
 [<span data-ttu-id="b4c81-130">Устранение неполадок служебной программы SQL Server</span><span class="sxs-lookup"><span data-stu-id="b4c81-130">Troubleshoot the SQL Server Utility</span></span>](../../database-engine/troubleshoot-the-sql-server-utility.md)  
