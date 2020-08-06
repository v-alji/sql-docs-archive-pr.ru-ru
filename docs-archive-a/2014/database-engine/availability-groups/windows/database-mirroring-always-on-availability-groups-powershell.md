---
title: Создание конечной точки зеркального отображения базы данных для группы доступности AlwaysOn (SQL Server PowerShell) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], server instance
- Availability Groups [SQL Server], deploying
- Availability Groups [SQL Server], endpoint
ms.assetid: 6197bbe7-67d4-446d-ba5f-cabfa5df77f1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 56058ff8aa72d2471381dd87fb25a3b68356ed36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752331"
---
# <a name="create-a-database-mirroring-endpoint-for-alwayson-availability-groups-sql-server-powershell"></a><span data-ttu-id="be0e8-102">Создайте конечную точку зеркального отображения базы данных для групп доступности AlwaysOn (SQL Server PowerShell)</span><span class="sxs-lookup"><span data-stu-id="be0e8-102">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups (SQL Server PowerShell)</span></span>
  <span data-ttu-id="be0e8-103">В этом разделе описывается создание конечной точки зеркального отображения базы данных для использования [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] в [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="be0e8-103">This topic describes how to create a database mirroring endpoint for use by [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using PowerShell.</span></span>  
  
 <span data-ttu-id="be0e8-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="be0e8-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="be0e8-105">**Перед началом работы**  [Безопасность](#Security)</span><span class="sxs-lookup"><span data-stu-id="be0e8-105">**Before you begin:**  [Security](#Security)</span></span>  
  
-   <span data-ttu-id="be0e8-106">**Создание конечной точки зеркального отображения базы данных с помощью следующих средств:**  [PowerShell](#PowerShellProcedure)</span><span class="sxs-lookup"><span data-stu-id="be0e8-106">**To create a database mirroring endpoint, using:**  [PowerShell](#PowerShellProcedure)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="be0e8-107">Перед началом</span><span class="sxs-lookup"><span data-stu-id="be0e8-107">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="be0e8-108">безопасность</span><span class="sxs-lookup"><span data-stu-id="be0e8-108">Security</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="be0e8-109">Алгоритм RC4 устарел.</span><span class="sxs-lookup"><span data-stu-id="be0e8-109">The RC4 algorithm is deprecated.</span></span> [!INCLUDE[ssNoteDepFutureDontUse](../../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="be0e8-110">Вместо этого рекомендуется использовать алгоритм AES.</span><span class="sxs-lookup"><span data-stu-id="be0e8-110">We recommend that you use AES.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="be0e8-111">Permissions</span><span class="sxs-lookup"><span data-stu-id="be0e8-111">Permissions</span></span>  
 <span data-ttu-id="be0e8-112">Требуется разрешение CREATE ENDPOINT или членство в предопределенной роли сервера sysadmin.</span><span class="sxs-lookup"><span data-stu-id="be0e8-112">Requires CREATE ENDPOINT permission, or membership in the sysadmin fixed server role.</span></span> <span data-ttu-id="be0e8-113">Дополнительные сведения см. в разделе [GRANT, предоставление разрешений на конечную точку (Transact-SQL)](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="be0e8-113">For more information, see [GRANT Endpoint Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql).</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="be0e8-114">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="be0e8-114">Using PowerShell</span></span>  
 <span data-ttu-id="be0e8-115">**Создание конечной точки зеркального отображения базы данных**</span><span class="sxs-lookup"><span data-stu-id="be0e8-115">**To create a database mirroring endpoint**</span></span>  
  
1.  <span data-ttu-id="be0e8-116">Перейдите в каталог (`cd`) экземпляра сервера, для которого хотите создать конечную точку зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="be0e8-116">Change directory (`cd`) to the server instance for which you want to create the database mirroring endpoint.</span></span>  
  
2.  <span data-ttu-id="be0e8-117">Создайте конечную точку с помощью командлета `New-SqlHadrEndpoint`, а затем с помощью командлета `Set-SqlHadrEndpoint` запустите эту конечную точку.</span><span class="sxs-lookup"><span data-stu-id="be0e8-117">Use the `New-SqlHadrEndpoint` cmdlet to create the endpoint and then use the `Set-SqlHadrEndpoint` to start the endpoint.</span></span>  
  
###  <a name="example-powershell"></a><a name="PShellExample"></a> <span data-ttu-id="be0e8-118">Пример (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="be0e8-118">Example (PowerShell)</span></span>  
 <span data-ttu-id="be0e8-119">Следующие команды PowerShell создают конечную точку зеркального отображения базы данных на экземпляре SQL Server*Machine*( \\ *экземпляре*компьютера).</span><span class="sxs-lookup"><span data-stu-id="be0e8-119">The following PowerShell commands create a database mirroring endpoint on an instance of SQL Server (*Machine*\\*Instance*).</span></span> <span data-ttu-id="be0e8-120">Эта конечная точка использует порт 5022.</span><span class="sxs-lookup"><span data-stu-id="be0e8-120">The endpoint uses port 5022.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="be0e8-121">Этот пример работает только на экземпляре сервера, на котором в данный момент отсутствует конечная точка зеркального отображения базы данных.</span><span class="sxs-lookup"><span data-stu-id="be0e8-121">This example works only on a server instance that currently lack a database mirroring endpoint.</span></span>  
  
```powershell
# Create the endpoint.  
$endpoint = New-SqlHadrEndpoint MyMirroringEndpoint -Port 5022 -Path SQLSERVER:\SQL\Machine\Instance  
  
# Start the endpoint  
Set-SqlHadrEndpoint -InputObject $endpoint -State "Started"
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="be0e8-122">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="be0e8-122">Related Tasks</span></span>  
 <span data-ttu-id="be0e8-123">**Настройка конечной точки зеркального отображения базы данных**</span><span class="sxs-lookup"><span data-stu-id="be0e8-123">**To Configure a Database Mirroring Endpoint**</span></span>  
  
-   [<span data-ttu-id="be0e8-124">Создание конечной точки зеркального отображения базы данных с проверкой подлинности Windows (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="be0e8-124">Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md)  
  
-   [<span data-ttu-id="be0e8-125">Использование сертификатов для конечной точки зеркального отображения базы данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="be0e8-125">Use Certificates for a Database Mirroring Endpoint &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/use-certificates-for-a-database-mirroring-endpoint-transact-sql.md)  
  
    -   [<span data-ttu-id="be0e8-126">Включение использования сертификатов для исходящих соединений в конечной точке зеркального отображения базы данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="be0e8-126">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/database-mirroring-use-certificates-for-outbound-connections.md)  
  
    -   [<span data-ttu-id="be0e8-127">Включение использования сертификатов для входящих соединений в конечной точке зеркального отображения базы данных (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="be0e8-127">Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;</span></span>](../../database-mirroring/database-mirroring-use-certificates-for-inbound-connections.md)  
  
-   [<span data-ttu-id="be0e8-128">Указание сетевого адреса сервера (зеркальное отображение базы данных)</span><span class="sxs-lookup"><span data-stu-id="be0e8-128">Specify a Server Network Address &#40;Database Mirroring&#41;</span></span>](../../database-mirroring/specify-a-server-network-address-database-mirroring.md)  
  
-   [<span data-ttu-id="be0e8-129">Укажите URL-адрес конечной точки при добавлении или изменении реплики доступности (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="be0e8-129">Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;</span></span>](specify-endpoint-url-adding-or-modifying-availability-replica.md)  
  
 <span data-ttu-id="be0e8-130">**Просмотр сведений о конечной точке зеркального отображения базы данных**</span><span class="sxs-lookup"><span data-stu-id="be0e8-130">**To View Information About the Database Mirroring Endpoint**</span></span>  
  
-   [<span data-ttu-id="be0e8-131">sys.database_mirroring_endpoints (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="be0e8-131">sys.database_mirroring_endpoints &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="be0e8-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="be0e8-132">See Also</span></span>  
 <span data-ttu-id="be0e8-133">[Создание группы доступности &#40;&#41;Transact-SQL](create-an-availability-group-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="be0e8-133">[Create an Availability Group &#40;Transact-SQL&#41;](create-an-availability-group-transact-sql.md) </span></span>  
 [<span data-ttu-id="be0e8-134">Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="be0e8-134">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
