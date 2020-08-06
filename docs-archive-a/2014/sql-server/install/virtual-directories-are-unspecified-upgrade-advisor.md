---
title: Виртуальные каталоги не указаны (советник по переходу) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- virtual directories [Reporting Services]
ms.assetid: 7d32b560-49d6-4558-b5d6-9127067f82d6
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: e20c48d0bf58d28cb2894baa26c2e11db26fab96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659122"
---
# <a name="virtual-directories-are-unspecified-upgrade-advisor"></a><span data-ttu-id="11343-102">Виртуальные каталоги не указаны (советник по переходу)</span><span class="sxs-lookup"><span data-stu-id="11343-102">Virtual directories are unspecified (Upgrade Advisor)</span></span>
  <span data-ttu-id="11343-103">Помощник по обновлению не обнаружил настроек виртуального каталога для веб-службы сервера отчетов или диспетчера отчетов.</span><span class="sxs-lookup"><span data-stu-id="11343-103">Upgrade Advisor did not detect virtual directory settings for the Report Server Web service or Report Manager.</span></span> <span data-ttu-id="11343-104">После завершения обновления необходимо настроить резервирования URL-адресов для сервера отчетов с помощью диспетчера конфигурации служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="11343-104">After upgrade completes, you must configure URL reservations for the report server by using the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration Manager.</span></span>  
  
||  
|-|  
|<span data-ttu-id="11343-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Собственный режим.</span><span class="sxs-lookup"><span data-stu-id="11343-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="11343-106">Компонент</span><span class="sxs-lookup"><span data-stu-id="11343-106">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="11343-107">Описание</span><span class="sxs-lookup"><span data-stu-id="11343-107">Description</span></span>  
 <span data-ttu-id="11343-108">При обновлении установки служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] резервируются новые URL-адреса для веб-службы сервера отчетов и диспетчера отчетов.</span><span class="sxs-lookup"><span data-stu-id="11343-108">Upgrading a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation includes reserving new URLs for the Report Server Web service and Report Manager.</span></span> <span data-ttu-id="11343-109">Помощник по обновлению не нашел в настройках обновляемого экземпляра виртуальные каталоги для веб-службы сервера отчетов или диспетчера отчетов. У помощника по обновлению недостаточно информации, чтобы зарезервировать URL-адреса для обновленного сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="11343-109">Upgrade Advisor did not detect virtual directories for the report server or Report Manager for the instance to be upgraded, and therefore the upgrade process has insufficient information to create URL reservations for the upgraded report server.</span></span> <span data-ttu-id="11343-110">Процесс обновления может быть продолжен, но виртуальные каталоги для сервера отчетов и диспетчера отчетов после новой установки не будут определены.</span><span class="sxs-lookup"><span data-stu-id="11343-110">Upgrade can continue, but the report server or Report Manager virtual directory will be undefined after the upgraded installation.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="11343-111">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="11343-111">Corrective Action</span></span>  
 <span data-ttu-id="11343-112">После окончания обновления задайте URL-адреса сервера отчетов и диспетчера отчетов при помощи диспетчера конфигурации служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="11343-112">After upgrade finishes, use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration Manager to set the URLs for report server and Report Manager.</span></span> <span data-ttu-id="11343-113">В диспетчере служб IIS удалите все виртуальные каталоги, в которых больше нет необходимости.</span><span class="sxs-lookup"><span data-stu-id="11343-113">Use IIS Manager to remove any virtual directories you no longer need.</span></span>  
  
 <span data-ttu-id="11343-114">Дополнительные сведения см. в разделе [Настройка URL-адреса &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/configure-a-url-ssrs-configuration-manager.md) [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] электронной документации по.</span><span class="sxs-lookup"><span data-stu-id="11343-114">For more information, see [Configure a URL  &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/configure-a-url-ssrs-configuration-manager.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11343-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="11343-115">See Also</span></span>  
 [<span data-ttu-id="11343-116">Reporting Services проблем обновления &#40;советник по переходу&#41;</span><span class="sxs-lookup"><span data-stu-id="11343-116">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
