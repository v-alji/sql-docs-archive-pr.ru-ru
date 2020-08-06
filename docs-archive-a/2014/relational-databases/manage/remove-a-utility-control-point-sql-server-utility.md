---
title: Удаление точки управления служебной программой (служебная программа SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: c048a416-900e-4c77-8243-e0f0d8b94068
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: fe4ebb9de3f7644b4cff5c7dbfb34e50be7e8993
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668850"
---
# <a name="remove-a-utility-control-point-sql-server-utility"></a><span data-ttu-id="c9966-102">удалить точку управления служебной программой (SQL Server Utility)</span><span class="sxs-lookup"><span data-stu-id="c9966-102">Remove a Utility Control Point (SQL Server Utility)</span></span>
  <span data-ttu-id="c9966-103">В этом разделе описывается удаление точки управления служебной программой [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] из экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9966-103">This topic describes how to remove a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utility control point (UCP) from the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="c9966-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="c9966-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c9966-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="c9966-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c9966-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="c9966-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="c9966-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="c9966-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c9966-108">**Для удаления точки управления служебной программы используется:**</span><span class="sxs-lookup"><span data-stu-id="c9966-108">**To remove a Utility Control Point, using:**</span></span>  
  
     [<span data-ttu-id="c9966-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c9966-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c9966-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="c9966-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="c9966-111">Ограничения</span><span class="sxs-lookup"><span data-stu-id="c9966-111">Limitations and Restrictions</span></span>  
 <span data-ttu-id="c9966-112">До использования этой процедуры до удаления пункта управления программой из программы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] следует учесть следующие обстоятельства.</span><span class="sxs-lookup"><span data-stu-id="c9966-112">Before you use this procedure to remove the UCP from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility, note the following requirements.</span></span> <span data-ttu-id="c9966-113">При выполнении операции хранимая процедура выполнит проверку готовности к установке.</span><span class="sxs-lookup"><span data-stu-id="c9966-113">The stored procedure will run prerequisite checks as part of the operation.</span></span>  
  
-   <span data-ttu-id="c9966-114">До выполнения этой процедуры все управляемые экземпляры [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] необходимо удалить из точки управления служебной программой.</span><span class="sxs-lookup"><span data-stu-id="c9966-114">Before you run this procedure, all managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be removed from the UCP.</span></span> <span data-ttu-id="c9966-115">Обратите внимание, что пункт управления программой является управляемым экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9966-115">Note that the UCP is a managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c9966-116">Дополнительные сведения см. в разделе [Удаление экземпляра SQL Server из служебной программы SQL Server](remove-an-instance-of-sql-server-from-the-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="c9966-116">From more information, see [Remove an Instance of SQL Server from the SQL Server Utility](remove-an-instance-of-sql-server-from-the-sql-server-utility.md).</span></span>  
  
-   <span data-ttu-id="c9966-117">Эта процедура должна запускаться на компьютере, являющемся точкой управления служебной программой.</span><span class="sxs-lookup"><span data-stu-id="c9966-117">This procedure must be run on a computer that is a UCP.</span></span>  
  
-   <span data-ttu-id="c9966-118">Если экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , где удален пункт управления служебной программой, содержал набор элементов сбора, не относящийся к служебной программе, эта процедура не удаляет базу данных UMDW (sysutility_mdw).</span><span class="sxs-lookup"><span data-stu-id="c9966-118">If the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] where the UCP was removed has a non-Utility data collection set, the UMDW database (sysutility_mdw) will not be dropped by the procedure.</span></span> <span data-ttu-id="c9966-119">В этом случае перед повторным созданием точки управления служебной программой необходимо вручную удалить базу данных UMDW (sysutility_mdw).</span><span class="sxs-lookup"><span data-stu-id="c9966-119">If this is the case, the UMDW database (sysutility_mdw) must be dropped manually before the UCP can be created again.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c9966-120">безопасность</span><span class="sxs-lookup"><span data-stu-id="c9966-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c9966-121">Permissions</span><span class="sxs-lookup"><span data-stu-id="c9966-121">Permissions</span></span>  
 <span data-ttu-id="c9966-122">Эта процедура должна выполняться пользователем, имеющим разрешения `sysadmin`, необходимые для создания точки управления служебной программой.</span><span class="sxs-lookup"><span data-stu-id="c9966-122">This procedure must be run by a user with `sysadmin` permissions; the same permissions required to create a UCP.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c9966-123">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c9966-123">Using Transact-SQL</span></span>  
  
#### <a name="to-remove-a-utility-control-point"></a><span data-ttu-id="c9966-124">Удаление точки управления служебной программой</span><span class="sxs-lookup"><span data-stu-id="c9966-124">To remove a Utility Control Point</span></span>  
  
1.  <span data-ttu-id="c9966-125">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9966-125">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c9966-126">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="c9966-126">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c9966-127">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="c9966-127">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
```  
EXEC msdb.dbo.sp_sysutility_ucp_remove;  
```  
  
## <a name="see-also"></a><span data-ttu-id="c9966-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="c9966-128">See Also</span></span>  
 <span data-ttu-id="c9966-129">[Функции и задачи служебной программы SQL Server](sql-server-utility-features-and-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="c9966-129">[SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md) </span></span>  
 <span data-ttu-id="c9966-130">[Использование проводника служебных программ для управления служебной программой SQL Server](use-utility-explorer-to-manage-the-sql-server-utility.md) </span><span class="sxs-lookup"><span data-stu-id="c9966-130">[Use Utility Explorer to Manage the SQL Server Utility](use-utility-explorer-to-manage-the-sql-server-utility.md) </span></span>  
 [<span data-ttu-id="c9966-131">Устранение неполадок служебной программы SQL Server</span><span class="sxs-lookup"><span data-stu-id="c9966-131">Troubleshoot the SQL Server Utility</span></span>](../../database-engine/troubleshoot-the-sql-server-utility.md)  
  
  
