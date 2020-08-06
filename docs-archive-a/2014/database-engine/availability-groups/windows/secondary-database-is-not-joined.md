---
title: База данных-получатель не присоединена | Документы Майкрософт
ms.custom: ''
ms.date: 01/09/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.drp2joined.issues.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 10817e5e-75fa-42dd-baa2-359bea3ad051
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 81275e85fd865924778f6d6f985e170a5bda9f9a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740472"
---
# <a name="secondary-database-is-not-joined"></a><span data-ttu-id="eb2f7-102">База данных-получатель не подключена</span><span class="sxs-lookup"><span data-stu-id="eb2f7-102">Secondary database is not joined</span></span>
    
## <a name="introduction"></a><span data-ttu-id="eb2f7-103">Введение</span><span class="sxs-lookup"><span data-stu-id="eb2f7-103">Introduction</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="eb2f7-104">**Имя политики**</span><span class="sxs-lookup"><span data-stu-id="eb2f7-104">**Policy Name**</span></span>|<span data-ttu-id="eb2f7-105">Состояние присоединения базы данных доступности</span><span class="sxs-lookup"><span data-stu-id="eb2f7-105">Availability Database Join State</span></span>|  
|<span data-ttu-id="eb2f7-106">**Проблема**</span><span class="sxs-lookup"><span data-stu-id="eb2f7-106">**Issue**</span></span>|<span data-ttu-id="eb2f7-107">База данных-получатель не присоединена.</span><span class="sxs-lookup"><span data-stu-id="eb2f7-107">Secondary database is not joined.</span></span>|  
|<span data-ttu-id="eb2f7-108">**Категория**</span><span class="sxs-lookup"><span data-stu-id="eb2f7-108">**Category**</span></span>|<span data-ttu-id="eb2f7-109">**Предупреждение**</span><span class="sxs-lookup"><span data-stu-id="eb2f7-109">**Warning**</span></span>|  
|<span data-ttu-id="eb2f7-110">**Аспект**</span><span class="sxs-lookup"><span data-stu-id="eb2f7-110">**Facet**</span></span>|<span data-ttu-id="eb2f7-111">База данных доступности</span><span class="sxs-lookup"><span data-stu-id="eb2f7-111">Availability database</span></span>|  
  
## <a name="description"></a><span data-ttu-id="eb2f7-112">Описание</span><span class="sxs-lookup"><span data-stu-id="eb2f7-112">Description</span></span>  
 <span data-ttu-id="eb2f7-113">Эта политика проверяет состояние соединения данных базы данных-получателя (которая также называется «реплика базы данных-получателя»).</span><span class="sxs-lookup"><span data-stu-id="eb2f7-113">This policy checks the join state of the secondary database (also known as a "secondary database replica").</span></span> <span data-ttu-id="eb2f7-114">Эта политика находится в нерабочем состоянии, если реплика набора данных не присоединена.</span><span class="sxs-lookup"><span data-stu-id="eb2f7-114">The policy is in an unhealthy state when the dataset replica is not joined.</span></span> <span data-ttu-id="eb2f7-115">В остальном политика находится в рабочем состоянии.</span><span class="sxs-lookup"><span data-stu-id="eb2f7-115">The policy is otherwise in a healthy state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="eb2f7-116">Для этого выпуска [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]сведения о возможных причинах проблем и решениях доступны в разделе [База данных-получатель не подключена](https://go.microsoft.com/fwlink/p/?LinkId=220862) в TechNet Wiki.</span><span class="sxs-lookup"><span data-stu-id="eb2f7-116">For this release of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], information about possible causes and solutions is located at [Secondary database is not joined](https://go.microsoft.com/fwlink/p/?LinkId=220862) on the TechNet Wiki.</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="eb2f7-117">Возможные причины</span><span class="sxs-lookup"><span data-stu-id="eb2f7-117">Possible Causes</span></span>  
 <span data-ttu-id="eb2f7-118">Эта база данных-получателя не присоединена к группе доступности.</span><span class="sxs-lookup"><span data-stu-id="eb2f7-118">This secondary database is not joined to the availability group.</span></span> <span data-ttu-id="eb2f7-119">Конфигурация этой базы данных-получателя является неполной.</span><span class="sxs-lookup"><span data-stu-id="eb2f7-119">The configuration of this secondary database is incomplete.</span></span>  
  
## <a name="possible-solution"></a><span data-ttu-id="eb2f7-120">Возможное решение</span><span class="sxs-lookup"><span data-stu-id="eb2f7-120">Possible Solution</span></span>  
 <span data-ttu-id="eb2f7-121">Используйте Transact-SQL, PowerShell или среду SQL Server Management Studio для присоединения вторичной реплики к группе доступности.</span><span class="sxs-lookup"><span data-stu-id="eb2f7-121">Use Transact-SQL, PowerShell, or SQL Server Management Studio to join the secondary replica to the availability group.</span></span> <span data-ttu-id="eb2f7-122">Дополнительные сведения о присоединении вторичных реплик к группам доступности приведены в разделе [Присоединение вторичной реплики к группе доступности (SQL Server)](https://msdn.microsoft.com/library/ff878473\(en-us,SQL.110\).aspx).</span><span class="sxs-lookup"><span data-stu-id="eb2f7-122">For more information about joining secondary replicas to availability groups, see [Joining a Secondary Replica to an Availability Group (SQL Server)](https://msdn.microsoft.com/library/ff878473\(en-us,SQL.110\).aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb2f7-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="eb2f7-123">See Also</span></span>  
 <span data-ttu-id="eb2f7-124">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="eb2f7-124">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="eb2f7-125">Использование панели мониторинга AlwaysOn (среда SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="eb2f7-125">Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;</span></span>](use-the-always-on-dashboard-sql-server-management-studio.md)  
  
  
