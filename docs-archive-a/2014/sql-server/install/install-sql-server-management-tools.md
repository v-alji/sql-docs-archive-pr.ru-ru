---
title: Установка средства управления SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Management Tools
ms.assetid: af68d59a-a04d-4f23-9967-ad4ee2e63381
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 39a7ed6d859c6bbbb63e938cc7127958082737dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666384"
---
# <a name="install-sql-server-management-tools"></a><span data-ttu-id="2e236-102">Установка базовой версии средств управления SQL Server</span><span class="sxs-lookup"><span data-stu-id="2e236-102">Install SQL Server Management Tools</span></span>
  <span data-ttu-id="2e236-103">Средства управления [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] включают следующие компоненты.</span><span class="sxs-lookup"><span data-stu-id="2e236-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management tools include the following components:</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]  
  
-   [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]  
  
-   <span data-ttu-id="2e236-104">Помощник по настройке базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e236-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Database Tuning Advisor</span></span>  
  
-   <span data-ttu-id="2e236-105">Средства командной строки, такие, как программы sqlcmd.exe и osql.exe.</span><span class="sxs-lookup"><span data-stu-id="2e236-105">Command prompt tools, such as sqlcmd.exe and osql.exe.</span></span>  
  
-   [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]<span data-ttu-id="2e236-106">надстройки для [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e236-106">add-ins to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]</span></span>  
  
 <span data-ttu-id="2e236-107">Обратите внимание, что среда [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] является отдельным параметром при установке [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2e236-107">Note that [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] is a separate option during [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation.</span></span>  
  
 <span data-ttu-id="2e236-108">Независимо от количества устанавливаемых экземпляров [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]или [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] устанавливается только одна копия средств управления [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2e236-108">Regardless of how many instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], or [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] are installed on a computer, only one copy of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Management Tools will be installed.</span></span>  
  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]<span data-ttu-id="2e236-109">Средства управления могут работать параллельно на одном компьютере с более ранними версиями [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] средств управления.</span><span class="sxs-lookup"><span data-stu-id="2e236-109">Management Tools can run side-by-side on the same computer with earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Tools.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e236-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="2e236-110">See Also</span></span>  
 <span data-ttu-id="2e236-111">[Функции, поддерживаемые различными выпусками SQL Server 2014](../../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md) </span><span class="sxs-lookup"><span data-stu-id="2e236-111">[Features Supported by the Editions of SQL Server 2014](../../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md) </span></span>  
 <span data-ttu-id="2e236-112">[Выпуски и компоненты SQL Server 2014](../editions-and-components-of-sql-server-2016.md) </span><span class="sxs-lookup"><span data-stu-id="2e236-112">[Editions and Components of SQL Server 2014](../editions-and-components-of-sql-server-2016.md) </span></span>  
 <span data-ttu-id="2e236-113">[Установка SQL Server 2014 с помощью мастера установки &#40;установки&#41;](../../database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup.md) </span><span class="sxs-lookup"><span data-stu-id="2e236-113">[Install SQL Server 2014 from the Installation Wizard &#40;Setup&#41;](../../database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup.md) </span></span>  
 [<span data-ttu-id="2e236-114">Обновление до SQL Server 2014 с помощью мастера установки &#40;установки&#41;</span><span class="sxs-lookup"><span data-stu-id="2e236-114">Upgrade to SQL Server 2014 Using the Installation Wizard &#40;Setup&#41;</span></span>](../../database-engine/install-windows/upgrade-sql-server-using-the-installation-wizard-setup.md)  
  
  
