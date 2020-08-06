---
title: Microsoft SQL Server Reporting Services общая служба SharePoint установлена параллельно (советник по переходу) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 6ae1017e-129b-4702-9ea7-00ac9b024062
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: b8a26fedd892dfb26dea4616efd46d3b3748b508
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666336"
---
# <a name="microsoft-sql-server-reporting-services-sharepoint-shared-service-is-installed-side-by-side-upgrade-advisor"></a><span data-ttu-id="1e0f5-102">Общая служба Microsoft SQL Server Reporting Services SharePoint установлена параллельно (советник по переходу)</span><span class="sxs-lookup"><span data-stu-id="1e0f5-102">Microsoft SQL Server Reporting Services SharePoint Shared Service is Installed Side by Side (Upgrade Advisor)</span></span>
  <span data-ttu-id="1e0f5-103">Советник по переходу обнаружил, [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] что общая служба SharePoint установлена параллельно с предыдущей версией [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1e0f5-103">Upgrade Advisor detected [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint Shared service is installed side by side with a previous version of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
||  
|-|  
|<span data-ttu-id="1e0f5-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Режим интеграции с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1e0f5-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="1e0f5-105">Компонент</span><span class="sxs-lookup"><span data-stu-id="1e0f5-105">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="1e0f5-106">Описание</span><span class="sxs-lookup"><span data-stu-id="1e0f5-106">Description</span></span>  
 <span data-ttu-id="1e0f5-107">Советник по переходу обнаружил, [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] что общая служба SharePoint установлена параллельно с предыдущей версией [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , которая не основана на архитектуре общей службы SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1e0f5-107">Upgrade Advisor detected [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint Shared service is installed side by side with a previous version of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] that is not based on the SharePoint shared service architecture.</span></span> <span data-ttu-id="1e0f5-108">Поскольку на компьютере параллельно установлены старая и новая версии служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], связанных с технологиями SharePoint, обновление заблокировано.</span><span class="sxs-lookup"><span data-stu-id="1e0f5-108">Because the computer has both older and newer [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint related technologies installed side by side, upgrade is blocked.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="1e0f5-109">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="1e0f5-109">Corrective Action</span></span>  
 <span data-ttu-id="1e0f5-110">Чтобы продолжить обновление, необходимо удалить одну из существующих установок служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1e0f5-110">To continue with upgrade, you must uninstall one of the existing [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installations.</span></span> <span data-ttu-id="1e0f5-111">После удаления одной из установок служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] повторно запустите помощник по обновлению, чтобы убедиться в отсутствии других проблем обновления.</span><span class="sxs-lookup"><span data-stu-id="1e0f5-111">After removing one of the installations of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], re-run Upgrade Advisor to confirm that there are no other upgrade issues.</span></span>  
  
  
