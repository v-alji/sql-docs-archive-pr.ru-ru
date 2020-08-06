---
title: Обновление служб Analysis Services | Документы Майкрософт
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- upgrading databases
- databases [Analysis Services], upgrading
- installing Analysis Services, side-by-side installations
- Analysis Services upgrades
- Analysis Services upgrades, about upgrading Analysis Services
- SSAS, database migration
- upgrading Analysis Services
- installing Analysis Services, upgrading
- SSAS, upgrading
ms.assetid: a131d329-386e-4470-aaa9-ffcde4e5ec0c
author: Minewiskan
ms.author: owend
ms.openlocfilehash: 78bf7f27233bcfd46bc1f189324eddc72adcc961
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657878"
---
# <a name="upgrade-analysis-services"></a><span data-ttu-id="abace-102">Обновление служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="abace-102">Upgrade Analysis Services</span></span>
  <span data-ttu-id="abace-103">Используйте пакет установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для обновления [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="abace-103">Use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup to upgrade [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="abace-104">Дополнительные сведения об обновлении [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в режиме интеграции с SharePoint см. в разделе [Upgrade PowerPivot для SharePoint](upgrade-power-pivot-for-sharepoint.md).</span><span class="sxs-lookup"><span data-stu-id="abace-104">For detailed information on upgrading [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in SharePoint mode, see [Upgrade PowerPivot for SharePoint](upgrade-power-pivot-for-sharepoint.md).</span></span> <span data-ttu-id="abace-105">Дополнительные сведения об обновлении существующего экземпляра SQL Server см. в статье [обновление до SQL Server 2014 с помощью мастера установки &#40;&#41;установки ](upgrade-sql-server-using-the-installation-wizard-setup.md).</span><span class="sxs-lookup"><span data-stu-id="abace-105">For more information about upgrading an existing SQL Server instance, see [Upgrade to SQL Server 2014 Using the Installation Wizard &#40;Setup&#41;](upgrade-sql-server-using-the-installation-wizard-setup.md).</span></span>  
  
## <a name="known-upgrade-issues"></a><span data-ttu-id="abace-106">Известные проблемы при обновлении</span><span class="sxs-lookup"><span data-stu-id="abace-106">Known Upgrade Issues</span></span>  
 <span data-ttu-id="abace-107">Перед обновлением до [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]просмотрите следующие источники:</span><span class="sxs-lookup"><span data-stu-id="abace-107">Before upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], review the following:</span></span>  
  
-   <span data-ttu-id="abace-108">[Заметки о Выпуске SQL Server 2014](https://go.microsoft.com/fwlink/?LinkID=296445).</span><span class="sxs-lookup"><span data-stu-id="abace-108">[SQL Server 2014 Release Notes](https://go.microsoft.com/fwlink/?LinkID=296445).</span></span>  
  
-   <span data-ttu-id="abace-109">Чтобы узнать [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , какие функции и функции были прекращены, устарели или изменены, см. [Analysis Services обратная совместимость](https://docs.microsoft.com/analysis-services/analysis-services-backward-compatibility).</span><span class="sxs-lookup"><span data-stu-id="abace-109">To learn which [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] features and functionality have been discontinued, deprecated, or changed see [Analysis Services Backward Compatibility](https://docs.microsoft.com/analysis-services/analysis-services-backward-compatibility).</span></span>  
  
## <a name="pre-upgrade-checklist"></a><span data-ttu-id="abace-110">Контрольный список действий перед обновлением</span><span class="sxs-lookup"><span data-stu-id="abace-110">Pre-Upgrade Checklist</span></span>  
 <span data-ttu-id="abace-111">Перед обновлением просмотрите следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="abace-111">Before upgrading, review the following information:</span></span>  
  
-   [<span data-ttu-id="abace-112">Поддерживаемые обновления версий и выпусков</span><span class="sxs-lookup"><span data-stu-id="abace-112">Supported Version and Edition Upgrades</span></span>](supported-version-and-edition-upgrades.md)  
  
-   [<span data-ttu-id="abace-113">Требования к аппаратному и программному обеспечению для установки SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="abace-113">Hardware and Software Requirements for Installing SQL Server 2014</span></span>](../../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md)  
  
-   [<span data-ttu-id="abace-114">Параметры для средства проверки конфигурации системы</span><span class="sxs-lookup"><span data-stu-id="abace-114">Check Parameters for the System Configuration Checker</span></span>](check-parameters-for-the-system-configuration-checker.md)  
  
-   [<span data-ttu-id="abace-115">Вопросы безопасности при установке SQL Server</span><span class="sxs-lookup"><span data-stu-id="abace-115">Security Considerations for a SQL Server Installation</span></span>](../../sql-server/install/security-considerations-for-a-sql-server-installation.md)  
  
-   [<span data-ttu-id="abace-116">Создание и восстановление резервных копий баз данных служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="abace-116">Backup and Restore of Analysis Services Databases</span></span>](https://docs.microsoft.com/analysis-services/multidimensional-models/backup-and-restore-of-analysis-services-databases)  
  
-   [<span data-ttu-id="abace-117">Использование помощника по обновлению для подготовки к обновлениям</span><span class="sxs-lookup"><span data-stu-id="abace-117">Use Upgrade Advisor to Prepare for Upgrades</span></span>](../../sql-server/install/use-upgrade-advisor-to-prepare-for-upgrades.md)  
  
## <a name="upgrading-analysis-services"></a><span data-ttu-id="abace-118">Обновление служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="abace-118">Upgrading Analysis Services</span></span>  
 <span data-ttu-id="abace-119">Можно выбрать один из нескольких способов обновления сервера и данных.</span><span class="sxs-lookup"><span data-stu-id="abace-119">You can choose from several approaches to upgrade server and data:</span></span>  
  
-   <span data-ttu-id="abace-120">**При обновлении на месте** существующие программные файлы заменяются [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] программами.</span><span class="sxs-lookup"><span data-stu-id="abace-120">An **in-place upgrade** replaces the existing program files with [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] program files.</span></span> <span data-ttu-id="abace-121">Базы данных остаются в том же расположении.</span><span class="sxs-lookup"><span data-stu-id="abace-121">Databases remain in the same location.</span></span> <span data-ttu-id="abace-122">Программные папки обновляются с целью отражения нового имени.</span><span class="sxs-lookup"><span data-stu-id="abace-122">Program folders are updated to reflect the new name.</span></span>  
  
-   <span data-ttu-id="abace-123">**Параллельное обновление** — это новая установка [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] на том же компьютере, на котором имеется экземпляр Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="abace-123">A **side-by-side upgrade** is a new installation of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] on the same computer that has an existing Analysis Services instance.</span></span> <span data-ttu-id="abace-124">Можно перенести базы данных на новый экземпляр на этом же компьютере и затем удалить старую версию, если она больше не используется.</span><span class="sxs-lookup"><span data-stu-id="abace-124">You can move databases over to the new instance on the same computer, and then uninstall the old version if you no longer use it.</span></span>  
  
-   <span data-ttu-id="abace-125">Можно также установить службы Analysis Services на новом оборудовании, а затем осуществить миграцию существующих баз данных на этот сервер.</span><span class="sxs-lookup"><span data-stu-id="abace-125">You can also install Analysis Services on new hardware and then migrate existing databases to that server.</span></span>  
  
## <a name="in-place-upgrade"></a><span data-ttu-id="abace-126">Обновление на месте</span><span class="sxs-lookup"><span data-stu-id="abace-126">In-place Upgrade</span></span>  
 <span data-ttu-id="abace-127">Можно обновить существующий экземпляр [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] до [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] и, как часть процесса обновления, автоматически перенести существующие базы данных из старого экземпляра в новый экземпляр.</span><span class="sxs-lookup"><span data-stu-id="abace-127">You can upgrade an existing instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] and, as part of the upgrade process, automatically migrate existing databases from the old instance to the new instance.</span></span> <span data-ttu-id="abace-128">Поскольку метаданные и двоичные данные между двумя версиями совместимы, после обновления данные сохраняются и их не нужно переносить вручную.</span><span class="sxs-lookup"><span data-stu-id="abace-128">Because the metadata and binary data is compatible between the two versions, you will retain the data after you upgrade and you do not have to manually migrate the data.</span></span>  
  
 <span data-ttu-id="abace-129">Чтобы обновить существующий экземпляр, запустите программу установки и укажите имя существующего экземпляра в качестве имени нового экземпляра.</span><span class="sxs-lookup"><span data-stu-id="abace-129">To upgrade an existing instance, run Setup and specify the name of the existing instance as the name of the new instance.</span></span>  
  
## <a name="upgrading-databases"></a><span data-ttu-id="abace-130">Обновление баз данных</span><span class="sxs-lookup"><span data-stu-id="abace-130">Upgrading Databases</span></span>  
 <span data-ttu-id="abace-131">Базы данных, созданные в предыдущих версиях служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , на обновленном сервере работают со старым значением уровня совместимости.</span><span class="sxs-lookup"><span data-stu-id="abace-131">Databases that were created in previous versions of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] run on the upgraded server under an older database compatibility level setting.</span></span> <span data-ttu-id="abace-132">Базы данных, созданные в следующих версиях, имеют уровень совместимости баз данных 105.</span><span class="sxs-lookup"><span data-stu-id="abace-132">Databases created in the following versions, have a database compatibility level of 105.</span></span> <span data-ttu-id="abace-133">Если необходимо использовать функции, требующие нового уровня совместимости базы данных, уровень совместимости можно изменить.</span><span class="sxs-lookup"><span data-stu-id="abace-133">You can change the compatibility level if you want to use features that require a newer database compatibility level.</span></span> <span data-ttu-id="abace-134">В противном случае базы данных можно запустить на обновленном сервере, используя исходные параметры.</span><span class="sxs-lookup"><span data-stu-id="abace-134">Otherwise, you can run the databases on the upgraded server using the original settings.</span></span> <span data-ttu-id="abace-135">Дополнительные сведения см. [в разделе Установка уровня совместимости многомерной базы данных &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/compatibility-level-of-a-multidimensional-database-analysis-services).</span><span class="sxs-lookup"><span data-stu-id="abace-135">For more information, see [Set the Compatibility Level of a Multidimensional Database &#40;Analysis Services&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/compatibility-level-of-a-multidimensional-database-analysis-services).</span></span>  
  
-   [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]  
  
-   [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]  
  
-   [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]  
  
-   [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="abace-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="abace-136">See Also</span></span>  
 <span data-ttu-id="abace-137">[Функции, поддерживаемые различными выпусками SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md) </span><span class="sxs-lookup"><span data-stu-id="abace-137">[Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md) </span></span>  
 <span data-ttu-id="abace-138">[Планирование установки SQL Server](../../sql-server/install/planning-a-sql-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="abace-138">[Planning a SQL Server Installation](../../sql-server/install/planning-a-sql-server-installation.md) </span></span>  
 <span data-ttu-id="abace-139">[Основные сведения об архитектуре Microsoft OLAP](https://docs.microsoft.com/analysis-services/multidimensional-models/olap-physical/understanding-microsoft-olap-architecture) </span><span class="sxs-lookup"><span data-stu-id="abace-139">[Understanding Microsoft OLAP Architecture](https://docs.microsoft.com/analysis-services/multidimensional-models/olap-physical/understanding-microsoft-olap-architecture) </span></span>  
 <span data-ttu-id="abace-140">[PowerPivot для SharePoint обновления](upgrade-power-pivot-for-sharepoint.md) </span><span class="sxs-lookup"><span data-stu-id="abace-140">[Upgrade PowerPivot for SharePoint](upgrade-power-pivot-for-sharepoint.md) </span></span>  
 <span data-ttu-id="abace-141">[Установка Analysis Services в многомерном режиме и модели интеллектуального анализа данных](../../sql-server/install/install-analysis-services-in-multidimensional-and-data-mining-mode.md) </span><span class="sxs-lookup"><span data-stu-id="abace-141">[Install Analysis Services in Multidimensional and Data Mining Mode](../../sql-server/install/install-analysis-services-in-multidimensional-and-data-mining-mode.md) </span></span>  
 [<span data-ttu-id="abace-142">Установка PowerPivot для SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="abace-142">PowerPivot for SharePoint 2010 Installation</span></span>](../../sql-server/install/powerpivot-for-sharepoint-2010-installation.md)  
  
  
