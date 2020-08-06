---
title: Обзор процесса обновления | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- upgrading SQL Server
- Upgrade Advisor [SQL Server], process description
- SQL Server Upgrade Advisor, process description
- upgrade process [Upgrade Advisor]
ms.assetid: f77ffbab-a195-4124-acce-9c538f7ca9ce
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 5da6dc3b3e6d6c7058193801100bf2552bfde7cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751672"
---
# <a name="upgrade-process-overview"></a><span data-ttu-id="a7cdf-102">Общие сведения о процессе обновления</span><span class="sxs-lookup"><span data-stu-id="a7cdf-102">Upgrade Process Overview</span></span>
  <span data-ttu-id="a7cdf-103">В этом разделе содержатся рекомендации для советника по переходу [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] и сводка рекомендованных процедур для обновления до [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7cdf-103">This topic provides best practice information for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Upgrade Advisor and a summary of the recommended process for upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="upgrade-process"></a><span data-ttu-id="a7cdf-104">Процесс обновления</span><span class="sxs-lookup"><span data-stu-id="a7cdf-104">Upgrade Process</span></span>  
 <span data-ttu-id="a7cdf-105">Серверы, работающие с [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] или [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], могут быть обновлены до [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7cdf-105">Servers that are running [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], or [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] can be upgraded to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="a7cdf-106">Некоторые компоненты [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] можно обновить на месте, другие необходимо перенести, а некоторые нужно заменить новым компонентом.</span><span class="sxs-lookup"><span data-stu-id="a7cdf-106">Whereas some [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components can be upgraded in place, others must be migrated, and still others have been superseded by new components.</span></span> <span data-ttu-id="a7cdf-107">Например, начиная с [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], службы [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) заменяют службы DTS, которые больше не поддерживаются в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7cdf-107">For example, starting with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) supersedes Data Transformation Services (DTS), and DTS is no longer supported in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="a7cdf-108">При формировании плана обновления необходимо определить, будут ли текущие пакеты служб DTS обновлены до пакетов служб [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7cdf-108">When you formulate your upgrade plan, you might need to plan for updating your current DTS packages to [!INCLUDE[ssIS](../../includes/ssis-md.md)] packages.</span></span>  
  
 <span data-ttu-id="a7cdf-109">Помощник по обновлению позволяет оценить текущие установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], компоненты и связанные файлы, чтобы выявить известные неполадки, которые вызовут проблемы в процессе и после обновления или перехода на [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7cdf-109">Upgrade Advisor enables you to evaluate current [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installations, components, and related files to identify known issues that will cause problems both during and after you upgrade or migrate to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="a7cdf-110">Некоторые из них могут привести к невозможности обновления до [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7cdf-110">A few of these known issues block the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] upgrade.</span></span> <span data-ttu-id="a7cdf-111">В отчете помощника по обновлению эти проблемы определены как блокировщики обновления.</span><span class="sxs-lookup"><span data-stu-id="a7cdf-111">In the Upgrade Advisor report, these issues are identified as Upgrade Blockers.</span></span> <span data-ttu-id="a7cdf-112">Если препятствия к обновлению не устранены до запуска программы установки, то установка [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] будет прекращена с рекомендацией запустить помощник по обновлению, чтобы выявить конкретные проблемы, которые не позволяют его выполнить.</span><span class="sxs-lookup"><span data-stu-id="a7cdf-112">If you have not addressed the Upgrade Blockers before you run Setup, [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Setup exits and recommends that you run Upgrade Advisor to identify the specific issues that are blocking the upgrade.</span></span>  
  
 <span data-ttu-id="a7cdf-113">Перед началом обновления до [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] рекомендуется создать резервную копию данных и системных настроек и выполнить стратегические шаги, перечисленные в рабочих правилах, принятых в компании.</span><span class="sxs-lookup"><span data-stu-id="a7cdf-113">As a best practice before upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], we recommend that you back up your data and system settings, and take strategic steps as outlined in the operational guidelines defined for your organization.</span></span> <span data-ttu-id="a7cdf-114">Для завершения обновления выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="a7cdf-114">Use the following steps to complete the upgrade:</span></span>  
  
1.  <span data-ttu-id="a7cdf-115">Обратитесь к разделу [Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="a7cdf-115">Review [Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="a7cdf-116">Создайте резервную копию данных и системных настроек.</span><span class="sxs-lookup"><span data-stu-id="a7cdf-116">Back up data and system settings.</span></span>  
  
3.  <span data-ttu-id="a7cdf-117">Запустите помощник по обновлению.</span><span class="sxs-lookup"><span data-stu-id="a7cdf-117">Run Upgrade Advisor.</span></span>  
  
     <span data-ttu-id="a7cdf-118">Помощник по обновлению не изменяет данные или параметры компьютера.</span><span class="sxs-lookup"><span data-stu-id="a7cdf-118">Upgrade Advisor does not modify your data or change settings on your computer.</span></span>  
  
4.  <span data-ttu-id="a7cdf-119">Просмотрите проблемы, выявленные в отчете помощника по обновлению.</span><span class="sxs-lookup"><span data-stu-id="a7cdf-119">Review the issues identified in the Upgrade Advisor report.</span></span>  
  
5.  <span data-ttu-id="a7cdf-120">Устраните любые критические препятствия, которые не позволяют выполнить обновление до [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7cdf-120">Resolve any blocking issues that would prevent you from upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
6.  <span data-ttu-id="a7cdf-121">Устраните любые проблемы, связанные с подготовкой к обновлению.</span><span class="sxs-lookup"><span data-stu-id="a7cdf-121">Resolve any other pre-upgrade issues.</span></span>  
  
7.  <span data-ttu-id="a7cdf-122">Запустите помощник по обновлению, чтобы убедиться, что все известные проблемы устранены.</span><span class="sxs-lookup"><span data-stu-id="a7cdf-122">Run Upgrade Advisor to verify that all known issues have been addressed.</span></span>  
  
8.  <span data-ttu-id="a7cdf-123">Запустите программу установки [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a7cdf-123">Run [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Setup.</span></span>  
  
9. <span data-ttu-id="a7cdf-124">Устраните любые проблемы, возникающие после обновления и миграции.</span><span class="sxs-lookup"><span data-stu-id="a7cdf-124">Resolve any post-upgrade and migration issues.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7cdf-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="a7cdf-125">See Also</span></span>  
 <span data-ttu-id="a7cdf-126">[Запуск помощника по обновлению &#40;пользовательского интерфейса&#41;](../../../2014/sql-server/install/running-upgrade-advisor-user-interface.md) </span><span class="sxs-lookup"><span data-stu-id="a7cdf-126">[Running Upgrade Advisor &#40;User Interface&#41;](../../../2014/sql-server/install/running-upgrade-advisor-user-interface.md) </span></span>  
 <span data-ttu-id="a7cdf-127">[Использование отчетов](../../../2014/sql-server/install/using-reports.md) </span><span class="sxs-lookup"><span data-stu-id="a7cdf-127">[Using Reports](../../../2014/sql-server/install/using-reports.md) </span></span>  
 [<span data-ttu-id="a7cdf-128">Работа с помощником по обновлению</span><span class="sxs-lookup"><span data-stu-id="a7cdf-128">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
