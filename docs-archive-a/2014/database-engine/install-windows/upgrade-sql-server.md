---
title: Обновление до SQL Server 2014 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- upgrading SQL Server
ms.assetid: 5064e35b-b70d-4a0b-a9e9-fff04162f9d2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 857bbd6d7269b7675653b11a9d7c0acd07927f62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730886"
---
# <a name="upgrade-to-sql-server-2014"></a><span data-ttu-id="4968d-102">Обновление до SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="4968d-102">Upgrade to SQL Server 2014</span></span>
  <span data-ttu-id="4968d-103">Экземпляры [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]или [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] можно обновить до [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4968d-103">You can upgrade instances of, [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], or [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="4968d-104">Перед запуском программы установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для обновления до [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]просмотрите [техническое руководство по обновлению SQL Server 2014](https://download.microsoft.com/download/7/1/5/715BDFA7-51B6-4D7B-AF17-61E78C7E538F/SQL_Server_2014_Upgrade_technical_guide.pdf) (загружается в формате PDF), ознакомьтесь со статьями о процессе обновления в этом разделе и прочитайте [заметки о выпуске SQL Server 2014](https://go.microsoft.com/fwlink/?LinkID=296445).</span><span class="sxs-lookup"><span data-stu-id="4968d-104">Before running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup to upgrade to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], check out the [SQL Server 2014 Upgrade Technical Guide](https://download.microsoft.com/download/7/1/5/715BDFA7-51B6-4D7B-AF17-61E78C7E538F/SQL_Server_2014_Upgrade_technical_guide.pdf) (PDF download), review the topics about the upgrade process in this section, and read the [SQL Server 2014 Release Notes](https://go.microsoft.com/fwlink/?LinkID=296445).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4968d-105">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="4968d-105">In This Section</span></span>  
 <span data-ttu-id="4968d-106">В этом разделе рассматриваются следующие вопросы.</span><span class="sxs-lookup"><span data-stu-id="4968d-106">This section contains the following topics:</span></span>  
  
-   [<span data-ttu-id="4968d-107">Поддерживаемые обновления версий и выпусков</span><span class="sxs-lookup"><span data-stu-id="4968d-107">Supported Version and Edition Upgrades</span></span>](supported-version-and-edition-upgrades.md)  
  
-   [<span data-ttu-id="4968d-108">Использование помощника по обновлению для подготовки к обновлениям</span><span class="sxs-lookup"><span data-stu-id="4968d-108">Use Upgrade Advisor to Prepare for Upgrades</span></span>](../../sql-server/install/use-upgrade-advisor-to-prepare-for-upgrades.md)  
  
-   [<span data-ttu-id="4968d-109">Использование программы распределенного воспроизведения для подготовки обновлений</span><span class="sxs-lookup"><span data-stu-id="4968d-109">Use the Distributed Replay Utility to Prepare for Upgrades</span></span>](../../sql-server/install/use-the-distributed-replay-utility-to-prepare-for-upgrades.md)  
  
-   [<span data-ttu-id="4968d-110">Обновление служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="4968d-110">Upgrade Analysis Services</span></span>](upgrade-analysis-services.md)  
  
-   <span data-ttu-id="4968d-111">[Обновление [компонент ядра СУБД]](upgrade-database-engine.md)</span><span class="sxs-lookup"><span data-stu-id="4968d-111">[Upgrade Database Engine](upgrade-database-engine.md)</span></span>  
  
-   [<span data-ttu-id="4968d-112">Обновление служб Data Quality Services</span><span class="sxs-lookup"><span data-stu-id="4968d-112">Upgrade Data Quality Services</span></span>](upgrade-data-quality-services.md)  
  
-   [<span data-ttu-id="4968d-113">Обновление служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="4968d-113">Upgrade Integration Services</span></span>](../../integration-services/install-windows/upgrade-integration-services.md)  
  
-   [<span data-ttu-id="4968d-114">Обновление служб Master Data Services</span><span class="sxs-lookup"><span data-stu-id="4968d-114">Upgrade Master Data Services</span></span>](upgrade-master-data-services.md)  
  
-   [<span data-ttu-id="4968d-115">Обновление PowerPivot для SharePoint</span><span class="sxs-lookup"><span data-stu-id="4968d-115">Upgrade PowerPivot for SharePoint</span></span>](upgrade-power-pivot-for-sharepoint.md)  
  
-   [<span data-ttu-id="4968d-116">Обновление реплицируемых баз данных</span><span class="sxs-lookup"><span data-stu-id="4968d-116">Upgrade Replicated Databases</span></span>](../../database-engine/install-windows/upgrade-replicated-databases.md)  
  
-   [<span data-ttu-id="4968d-117">Обновление и перенос служб Reporting Services</span><span class="sxs-lookup"><span data-stu-id="4968d-117">Upgrade and Migrate Reporting Services</span></span>](../../reporting-services/install-windows/upgrade-and-migrate-reporting-services.md)  
  
-   [<span data-ttu-id="4968d-118">Обновление средств управления SQL Server</span><span class="sxs-lookup"><span data-stu-id="4968d-118">Upgrade SQL Server Management Tools</span></span>](upgrade-sql-server-management-tools.md)  
  
-   [<span data-ttu-id="4968d-119">Инструкции по обновлению</span><span class="sxs-lookup"><span data-stu-id="4968d-119">Upgrade How-to Topics</span></span>](../../../2014/sql-server/install/upgrade-how-to-topics.md)  
  
## <a name="see-also"></a><span data-ttu-id="4968d-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="4968d-120">See Also</span></span>  
 <span data-ttu-id="4968d-121">[Обновление [компонент ядра СУБД]](upgrade-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="4968d-121">[Upgrade Database Engine](upgrade-database-engine.md) </span></span>  
 <span data-ttu-id="4968d-122">[Обновление служб Analysis Services](upgrade-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="4968d-122">[Upgrade Analysis Services](upgrade-analysis-services.md) </span></span>  
 <span data-ttu-id="4968d-123">[Обновление и перенос служб Reporting Services](../../reporting-services/install-windows/upgrade-and-migrate-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="4968d-123">[Upgrade and Migrate Reporting Services](../../reporting-services/install-windows/upgrade-and-migrate-reporting-services.md) </span></span>  
 <span data-ttu-id="4968d-124">[Обновление служб Integration Services](../../integration-services/install-windows/upgrade-integration-services.md) </span><span class="sxs-lookup"><span data-stu-id="4968d-124">[Upgrade Integration Services](../../integration-services/install-windows/upgrade-integration-services.md) </span></span>  
 <span data-ttu-id="4968d-125">[Обновление реплицируемых баз данных](../../database-engine/install-windows/upgrade-replicated-databases.md) </span><span class="sxs-lookup"><span data-stu-id="4968d-125">[Upgrade Replicated Databases](../../database-engine/install-windows/upgrade-replicated-databases.md) </span></span>  
 <span data-ttu-id="4968d-126">[Обновление служб Master Data Services](upgrade-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="4968d-126">[Upgrade Master Data Services](upgrade-master-data-services.md) </span></span>  
 <span data-ttu-id="4968d-127">[SQL Server 2012 анализатор соответствия рекомендациям](https://www.microsoft.com/download/details.aspx?id=29302) </span><span class="sxs-lookup"><span data-stu-id="4968d-127">[SQL Server 2012 Best Practices Analyzer](https://www.microsoft.com/download/details.aspx?id=29302) </span></span>  
 <span data-ttu-id="4968d-128">[Анализатор соответствия рекомендациям для SQL Server 2008 R2](https://www.microsoft.com/download/details.aspx?id=436) </span><span class="sxs-lookup"><span data-stu-id="4968d-128">[SQL Server 2008 R2 Best Practices Analyzer](https://www.microsoft.com/download/details.aspx?id=436) </span></span>  
 [<span data-ttu-id="4968d-129">Обратная совместимость</span><span class="sxs-lookup"><span data-stu-id="4968d-129">Backward Compatibility</span></span>](../../../2014/getting-started/backward-compatibility.md)  
  
  
