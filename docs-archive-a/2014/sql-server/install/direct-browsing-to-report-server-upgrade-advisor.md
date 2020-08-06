---
title: Прямой просмотр сервера отчетов (советник по переходу) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 3d2814a4-318a-45ed-b093-1e852fab561f
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: ab4d146bba4bd87de56b30ad100b57f79eb68de3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668625"
---
# <a name="direct-browsing-to-report-server-upgrade-advisor"></a><span data-ttu-id="3c233-102">Прямой переход на сервер отчетов (советник по переходу)</span><span class="sxs-lookup"><span data-stu-id="3c233-102">Direct Browsing to Report Server (Upgrade Advisor)</span></span>
  <span data-ttu-id="3c233-103">Советник по переходу обнаружил, что текущая установка [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] — Просмотр непосредственно в виртуальном каталоге сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="3c233-103">Upgrade Advisor detected your current installation of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is browsing directly to the report server virtual directory.</span></span>  
  
||  
|-|  
|<span data-ttu-id="3c233-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Режим интеграции с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3c233-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="3c233-105">Компонент</span><span class="sxs-lookup"><span data-stu-id="3c233-105">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="3c233-106">Описание</span><span class="sxs-lookup"><span data-stu-id="3c233-106">Description</span></span>  
 <span data-ttu-id="3c233-107">Советник по переходу обнаружил, что текущая установка [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] находится непосредственно в виртуальном каталоге сервера отчетов, например **http:// \<server name> /ReportServer**.</span><span class="sxs-lookup"><span data-stu-id="3c233-107">Upgrade Advisor detected your current installation of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is browsing directly to the report server virtual directory, for example **http://\<server name>/ReportServer**.</span></span> <span data-ttu-id="3c233-108">Не поддерживается в текущих версиях служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3c233-108">This is not supported in current versions of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3c233-109">Это правило является предупреждением, обновление не заблокировано.</span><span class="sxs-lookup"><span data-stu-id="3c233-109">This rule is a warning and upgrade is not blocked.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="3c233-110">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="3c233-110">Corrective Action</span></span>  
 <span data-ttu-id="3c233-111">Просмотр с помощью пользовательского интерфейса SharePoint для библиотек документов или использование **http:// \<server name> /шарепоинт site>/_vti_bin/ReportServer**.</span><span class="sxs-lookup"><span data-stu-id="3c233-111">Browse using the SharePoint user interface for document libraries or use **http://\<server name>/sharepoint site>/_vti_bin/reportserver**.</span></span>  
  
  
