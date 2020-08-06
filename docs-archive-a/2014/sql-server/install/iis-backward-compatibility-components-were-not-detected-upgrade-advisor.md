---
title: Не обнаружены компоненты обратной совместимости IIS (советник по переходу) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- IIS [Reporting Services]
ms.assetid: e794185a-0a77-480a-9aea-d09f8760a6b8
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: a5aad54a01b3840e121c6a63de0ea26f35921fa7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668045"
---
# <a name="iis-backward-compatibility-components-were-not-detected-upgrade-advisor"></a><span data-ttu-id="d3c63-102">Не найдены компоненты обратной совместимости служб IIS (советник по переходу)</span><span class="sxs-lookup"><span data-stu-id="d3c63-102">IIS backward compatibility components were not detected (Upgrade Advisor)</span></span>
  <span data-ttu-id="d3c63-103">Помощник по обновлению не обнаружил компонентов и настроек служб IIS, которые содержат информацию, используемую программой настройки для создания новых URL-адресов служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d3c63-103">Upgrade Advisor did not detect IIS components and settings that provide information used by Setup to create new [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] URLS.</span></span>  
  
||  
|-|  
|<span data-ttu-id="d3c63-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Собственный режим.</span><span class="sxs-lookup"><span data-stu-id="d3c63-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="d3c63-105">Компонент</span><span class="sxs-lookup"><span data-stu-id="d3c63-105">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="d3c63-106">Описание</span><span class="sxs-lookup"><span data-stu-id="d3c63-106">Description</span></span>  
 <span data-ttu-id="d3c63-107">Службы IIS включают компоненты, которые предоставляют информацию о виртуальных каталогах сервера отчетов и диспетчера отчетов. Эти компоненты не установлены на компьютере, на котором размещен сервер отчетов.</span><span class="sxs-lookup"><span data-stu-id="d3c63-107">IIS includes components that provide information about the report server and Report Manager virtual directories, and those components are not installed on the report server computer.</span></span> <span data-ttu-id="d3c63-108">Обновление может быть продолжено, но URL-адреса сервера отчетов и диспетчера отчетов повторно созданы не будут.</span><span class="sxs-lookup"><span data-stu-id="d3c63-108">Upgrade can continue, but URLs for the report server or Report Manager will not be recreated by upgrade.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="d3c63-109">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="d3c63-109">Corrective Action</span></span>  
 <span data-ttu-id="d3c63-110">После окончания обновления задайте URL-адреса сервера отчетов и диспетчера отчетов при помощи программы настройки служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d3c63-110">After upgrade finishes, use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool to set the URLs for report server or Report Manager.</span></span> <span data-ttu-id="d3c63-111">В диспетчере служб IIS удалите виртуальные каталоги, в которых больше нет необходимости.</span><span class="sxs-lookup"><span data-stu-id="d3c63-111">Use IIS Manager to remove the virtual directories you no longer need.</span></span>  
  
 <span data-ttu-id="d3c63-112">Дополнительные сведения см. в разделе [Настройка URL-адреса &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/configure-a-url-ssrs-configuration-manager.md) [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] электронной документации по.</span><span class="sxs-lookup"><span data-stu-id="d3c63-112">For more information, see [Configure a URL  &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/configure-a-url-ssrs-configuration-manager.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3c63-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="d3c63-113">See Also</span></span>  
 [<span data-ttu-id="d3c63-114">Reporting Services проблем обновления &#40;советник по переходу&#41;</span><span class="sxs-lookup"><span data-stu-id="d3c63-114">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
