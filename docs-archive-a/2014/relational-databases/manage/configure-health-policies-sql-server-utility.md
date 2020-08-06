---
title: Настройка политик исправности (служебная программа SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 030aac3b-8901-4c41-91ed-aba96420276c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c5ee466dd2d5bac2ea64364bfc78de8f2f5bea10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656406"
---
# <a name="configure-health-policies-sql-server-utility"></a><span data-ttu-id="ad77e-102">Настройка политик исправности (служебная программа SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ad77e-102">Configure Health Policies (SQL Server Utility)</span></span>
  <span data-ttu-id="ad77e-103">Панель мониторинга программы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] позволяет просмотреть параметры программы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для управляемых экземпляров [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и приложений уровня данных.</span><span class="sxs-lookup"><span data-stu-id="ad77e-103">Use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility dashboard in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to view [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility resource parameters for managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and data-tier applications.</span></span> <span data-ttu-id="ad77e-104">Дополнительные сведения см. в разделе [Функции и задачи служебной программы SQL Server](sql-server-utility-features-and-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="ad77e-104">For more information, see [SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md).</span></span>  
  
 <span data-ttu-id="ad77e-105">Чтобы просмотреть результаты политики исправности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , подключитесь к точке управления служебной программой из среды [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ad77e-105">To view [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility health policy results, connect to a utility control point from [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="ad77e-106">Дополнительные сведения см. в статье [Использование проводника служебных программ для управления служебной программой SQL Server](use-utility-explorer-to-manage-the-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="ad77e-106">For more information, see [Use Utility Explorer to Manage the SQL Server Utility](use-utility-explorer-to-manage-the-sql-server-utility.md).</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ad77e-107">Политики исправности программы можно настроить для приложений уровня данных и экземпляров [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ad77e-107">Utility health policies can be configured for data-tier applications and managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ad77e-108">В программе [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] политика исправности может быть задана глобально для всех приложений уровня данных и управляемых экземпляров [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , либо ее можно задать индивидуально для отдельных приложений уровня данных и управляемых экземпляров [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в программе [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ad77e-108">Health policies can be defined globally for all data-tier applications and managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility, or they can be defined individually for each data-tier application and for each managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span>  
  
## <a name="monitoring-policies-for-data-tier-applications"></a><span data-ttu-id="ad77e-109">Политики наблюдения для приложений уровня данных</span><span class="sxs-lookup"><span data-stu-id="ad77e-109">Monitoring Policies for Data-tier Applications</span></span>  
 <span data-ttu-id="ad77e-110">Политики чрезмерного и недостаточного использования для приложений уровня данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="ad77e-110">Overutilization and underutilization policies for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data-tier applications are as follows:</span></span>  
  
-   <span data-ttu-id="ad77e-111">Загрузка процессора приложением уровня данных.</span><span class="sxs-lookup"><span data-stu-id="ad77e-111">Data-tier application processor utilization.</span></span>  
  
-   <span data-ttu-id="ad77e-112">Файловое пространство приложения уровня данных для файлов баз данных.</span><span class="sxs-lookup"><span data-stu-id="ad77e-112">Data-tier application file space for database files.</span></span>  
  
-   <span data-ttu-id="ad77e-113">Файловое пространство приложения уровня данных для томов хранилища.</span><span class="sxs-lookup"><span data-stu-id="ad77e-113">Data-tier application file space for storage volumes.</span></span>  
  
-   <span data-ttu-id="ad77e-114">Использование процессора компьютера.</span><span class="sxs-lookup"><span data-stu-id="ad77e-114">Computer processor utilization.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ad77e-115">Для приложений уровня данных использование томов хранилища и процессора является политиками только для чтения.</span><span class="sxs-lookup"><span data-stu-id="ad77e-115">Storage volume and processor utilization are read-only policies for data-tier applications.</span></span>  
  
 <span data-ttu-id="ad77e-116">Дополнительные сведения о просмотре или изменении глобальных политик наблюдения для приложений уровня данных см. в статье [Администрирование программ (служебная программа SQL Server)](../../database-engine/utility-administration-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="ad77e-116">For more information about viewing or changing global monitoring policies for data-tier applications, see [Utility Administration &#40;SQL Server Utility&#41;](../../database-engine/utility-administration-sql-server-utility.md).</span></span>  
  
 <span data-ttu-id="ad77e-117">Дополнительные сведения о просмотре и изменении политик наблюдения для отдельных приложений уровня данных см. в статье [Подробные сведения о развернутом приложении уровня данных (служебная программа SQL Server)](../../database-engine/deployed-data-tier-application-details-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="ad77e-117">For more information about viewing or changing monitoring policies for individual data-tier applications, see [Deployed Data-tier Application Details &#40;SQL Server Utility&#41;](../../database-engine/deployed-data-tier-application-details-sql-server-utility.md).</span></span>  
  
## <a name="monitoring-policies-for-managed-instances-of-sql-server"></a><span data-ttu-id="ad77e-118">Политики наблюдения для управляемых экземпляров SQL Server</span><span class="sxs-lookup"><span data-stu-id="ad77e-118">Monitoring Policies for Managed Instances of SQL Server</span></span>  
 <span data-ttu-id="ad77e-119">Политики чрезмерного и недостаточного использования для управляемых экземпляров [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="ad77e-119">Overutilization and underutilization policies for managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are as follows:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ad77e-120">.</span><span class="sxs-lookup"><span data-stu-id="ad77e-120">instance processor utilization.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ad77e-121">для файлов баз данных.</span><span class="sxs-lookup"><span data-stu-id="ad77e-121">instance file space for database files.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ad77e-122">для томов хранилища.</span><span class="sxs-lookup"><span data-stu-id="ad77e-122">instance file space for storage volumes.</span></span>  
  
-   <span data-ttu-id="ad77e-123">Использование процессора компьютера.</span><span class="sxs-lookup"><span data-stu-id="ad77e-123">Computer processor utilization.</span></span>  
  
 <span data-ttu-id="ad77e-124">Дополнительные сведения о просмотре или изменении глобальных политик наблюдения для управляемых экземпляров [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] см. в статье [Администрирование программ (служебная программа SQL Server)](../../database-engine/utility-administration-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="ad77e-124">For more information about viewing or changing global monitoring policies for managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Utility Administration &#40;SQL Server Utility&#41;](../../database-engine/utility-administration-sql-server-utility.md).</span></span>  
  
 <span data-ttu-id="ad77e-125">Дополнительные сведения о просмотре и изменении политик наблюдения для отдельных управляемых экземпляров [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] см. в статье [Подробные сведения о развернутом приложении уровня данных (служебная программа SQL Server)](../../database-engine/managed-instance-details-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="ad77e-125">For more information about viewing or changing monitoring policies for individual managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Managed Instance Details &#40;SQL Server Utility&#41;](../../database-engine/managed-instance-details-sql-server-utility.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad77e-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="ad77e-126">See Also</span></span>  
 <span data-ttu-id="ad77e-127">[Функции и задачи служебной программы SQL Server](sql-server-utility-features-and-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="ad77e-127">[SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md) </span></span>  
 [<span data-ttu-id="ad77e-128">Уменьшение уровня шума в политиках загрузки ЦП (служебная программа SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ad77e-128">Reduce Noise in CPU Utilization Policies &#40;SQL Server Utility&#41;</span></span>](reduce-noise-in-cpu-utilization-policies-sql-server-utility.md)  
  
  
