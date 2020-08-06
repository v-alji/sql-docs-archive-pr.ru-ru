---
title: Критические изменения в функциях средств управления в SQL Server 2014 | Документация Майкрософт
ms.custom: ''
ms.date: 11/27/2018
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 3ff3fad8-b569-4516-bd58-5a3efeb537e2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0487b6ab0958e0b83d4e8e34be507b5b3211ac87
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665598"
---
# <a name="breaking-changes-to-management-tools-features-in-sql-server-2014"></a><span data-ttu-id="bafc9-102">Критические изменения в функциях средств управления в SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="bafc9-102">Breaking Changes to Management Tools Features in SQL Server 2014</span></span>
  <span data-ttu-id="bafc9-103">В этом разделе описаны критические изменения в функциях средств управления.</span><span class="sxs-lookup"><span data-stu-id="bafc9-103">This topic describes breaking changes to management tools features.</span></span> <span data-ttu-id="bafc9-104">Эти изменения могут нарушать работу приложений, скриптов или механизмов, основанных на более ранних версиях [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bafc9-104">These changes might break applications, scripts, or functionalities that are based on earlier versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="bafc9-105">При обновлении могут возникнуть следующие проблемы.</span><span class="sxs-lookup"><span data-stu-id="bafc9-105">You might encounter these issues when you upgrade.</span></span> <span data-ttu-id="bafc9-106">Дополнительные сведения см. в разделе [Use Upgrade Advisor to Prepare for Upgrades](../../2014/sql-server/install/use-upgrade-advisor-to-prepare-for-upgrades.md).</span><span class="sxs-lookup"><span data-stu-id="bafc9-106">For more information, see [Use Upgrade Advisor to Prepare for Upgrades](../../2014/sql-server/install/use-upgrade-advisor-to-prepare-for-upgrades.md).</span></span>  
  
## <a name="breaking-changes-in-sssql14"></a><span data-ttu-id="bafc9-107">Критические изменения в [!INCLUDE[ssSQL14](../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bafc9-107">Breaking Changes in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)]</span></span>  
 <span data-ttu-id="bafc9-108">Сведения будут доступны позже.</span><span class="sxs-lookup"><span data-stu-id="bafc9-108">Information to come later.</span></span>  
  
## <a name="breaking-changes-in-sssql11"></a><span data-ttu-id="bafc9-109">Критические изменения в [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bafc9-109">Breaking Changes in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]</span></span>  
  
### <a name="you-cannot-use-sssql11-management-tools-to-create-a-utility-control-point-on-a-sskilimanjaro-instance-of-sql-server"></a><span data-ttu-id="bafc9-110">Средства управления [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] нельзя использовать для создания точки управления служебной программой в экземпляре SQL Server [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bafc9-110">You cannot use [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] Management Tools to create a utility control point on a [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] instance of SQL Server</span></span>  
 <span data-ttu-id="bafc9-111">Для создания точки управления служебной программой в экземпляре [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)]используйте средства управления [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bafc9-111">To create a utility control point on an instance of [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)], use [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] Management Tools.</span></span>  
  
### <a name="smo-has-been-reversioned-in-sssql11"></a><span data-ttu-id="bafc9-112">В [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] изменилась версия объектов SMO.</span><span class="sxs-lookup"><span data-stu-id="bafc9-112">SMO has been reversioned in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]</span></span>  
 <span data-ttu-id="bafc9-113">Код, использующий объекты SMO из [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] или более ранних версий, может оказаться неработоспособным в [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] без внесения небольших изменений.</span><span class="sxs-lookup"><span data-stu-id="bafc9-113">Code developed with SMO from [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] or earlier versions might not build against [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] without minor modifications.</span></span> <span data-ttu-id="bafc9-114">Дополнительные сведения см. в разделе [Backward Compatibility in SMO](../relational-databases/server-management-objects-smo/backward-compatibility-in-smo.md).</span><span class="sxs-lookup"><span data-stu-id="bafc9-114">For more information, see [Backward Compatibility in SMO](../relational-databases/server-management-objects-smo/backward-compatibility-in-smo.md).</span></span>  

## <a name="breaking-changes-in-sql-server-2005"></a><a name="previous-versions"></a><span data-ttu-id="bafc9-115">Критические изменения в SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="bafc9-115">Breaking Changes in SQL Server 2005</span></span>  

[!INCLUDE[Archived documentation for very old versions of SQL Server](../includes/paragraph-content/previous-versions-archive-documentation-sql-server.md)]

## <a name="see-also"></a><span data-ttu-id="bafc9-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="bafc9-116">See Also</span></span>  
 [<span data-ttu-id="bafc9-117">Обратная совместимость</span><span class="sxs-lookup"><span data-stu-id="bafc9-117">Backward Compatibility</span></span>](../../2014/getting-started/backward-compatibility.md)  
 [<span data-ttu-id="bafc9-118">Дополнительные сведения о критических изменениях в функциях средств управления в SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="bafc9-118">More about Breaking Changes to Management Tools Features in SQL Server 2014</span></span>](breaking-changes-to-database-engine-features-in-sql-server-2016.md?view=sql-server-2014)  
  
  
