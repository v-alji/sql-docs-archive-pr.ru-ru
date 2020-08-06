---
title: Обнаружено ограничение IP-адресов (советник по переходу) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- report servers [Reporting Services], upgrade issues
ms.assetid: 9a154455-c68f-4403-a3a7-b90f4d35eecb
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 2028e59e91d42bfdced2d18fa6ce129dfb108302
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732294"
---
# <a name="ip-address-restriction-detected-upgrade-advisor"></a><span data-ttu-id="4addc-102">Обнаружено ограничение по IP-адресу (советник по переходу)</span><span class="sxs-lookup"><span data-stu-id="4addc-102">IP address restriction detected (Upgrade Advisor)</span></span>
  <span data-ttu-id="4addc-103">Помощник по обновлению обнаружил одно ограничение IP-адреса или более на веб-сайте IIS, на котором размещается сервер отчетов или виртуальные каталоги диспетчера отчетов.</span><span class="sxs-lookup"><span data-stu-id="4addc-103">Upgrade Advisor detected one or more IP address restrictions on the IIS Web site that hosts the report server or Report Manager virtual directories.</span></span> <span data-ttu-id="4addc-104">Службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] не поддерживают собственную реализацию ограничений IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="4addc-104">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] does not provide native support for IP address restrictions.</span></span>  
  
||  
|-|  
|<span data-ttu-id="4addc-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Собственной.</span><span class="sxs-lookup"><span data-stu-id="4addc-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="4addc-106">Компонент</span><span class="sxs-lookup"><span data-stu-id="4addc-106">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="4addc-107">Описание</span><span class="sxs-lookup"><span data-stu-id="4addc-107">Description</span></span>  
 <span data-ttu-id="4addc-108">Программа установки не может определить ограничений IP-адреса на URL-адреса, созданные для обновленного сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="4addc-108">Setup cannot define IP address restrictions on URLs created for an upgraded report server.</span></span> <span data-ttu-id="4addc-109">Обновление может быть продолжено, но ограничения IP-адреса не будут наложены на URL-адреса служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4addc-109">Upgrade can continue, but IP address restrictions will not be defined on the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] URLs.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="4addc-110">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="4addc-110">Corrective Action</span></span>  
 <span data-ttu-id="4addc-111">После обновления для разрешения или запрещения запросов к серверу отчетов с конкретных IP-адресов используйте сервер ISA, брандмауэр или другое решение.</span><span class="sxs-lookup"><span data-stu-id="4addc-111">After upgrade, use ISA Server, your firewall software, or another solution to allow or exclude requests from specific IP addresses to the report server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4addc-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="4addc-112">See Also</span></span>  
 [<span data-ttu-id="4addc-113">Reporting Services проблем обновления &#40;советник по переходу&#41;</span><span class="sxs-lookup"><span data-stu-id="4addc-113">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
