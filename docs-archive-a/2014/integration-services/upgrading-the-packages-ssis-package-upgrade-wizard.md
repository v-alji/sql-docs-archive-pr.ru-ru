---
title: Обновление пакетов (мастер обновления пакетов служб SSIS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.is.upgradewizard.upgradingpackage.f1
ms.assetid: cdb842e3-2e59-4ede-b127-be4fde46875c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d13228dabc1566b592733da4afd8ebde3671ee0d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656453"
---
# <a name="upgrading-the-packages-ssis-package-upgrade-wizard"></a><span data-ttu-id="07a94-102">Обновление пакетов (мастер обновления пакетов служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="07a94-102">Upgrading the Packages (SSIS Package Upgrade Wizard)</span></span>
  <span data-ttu-id="07a94-103">Страница **Обновление пакетов** используется для слежения за ходом обновления пакетов и прерывания процесса обновления.</span><span class="sxs-lookup"><span data-stu-id="07a94-103">Use the **Upgrading the Packages** page to view the progress of package upgrade and to interrupt the upgrade process.</span></span> <span data-ttu-id="07a94-104">Мастер обновления пакетов служб [!INCLUDE[ssIS](../includes/ssis-md.md)] обновляет выбранные пакеты один за другим.</span><span class="sxs-lookup"><span data-stu-id="07a94-104">The [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Upgrade Wizard upgrades the selected packages one by one.</span></span>  
  
 <span data-ttu-id="07a94-105">**Просмотр обновленных пакетов, сохраненных в базе данных SQL Server или в хранилище пакетов**</span><span class="sxs-lookup"><span data-stu-id="07a94-105">**To view upgraded packages that were saved to a SQL Server database or to the package store**</span></span>  
  
-   <span data-ttu-id="07a94-106">В обозревателе объектов среды [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]установите соединение с локальным экземпляром служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], а затем разверните узел **Сохраненные пакеты** , чтобы увидеть обновленные пакеты.</span><span class="sxs-lookup"><span data-stu-id="07a94-106">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], in Object Explorer, connect to the local instance of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], and then expand the **Stored Packages** node to see the packages that were upgraded.</span></span>  
  
 <span data-ttu-id="07a94-107">**Просмотр обновленных пакетов из SQL Server Data Tools**</span><span class="sxs-lookup"><span data-stu-id="07a94-107">**To view upgraded packages that were upgraded from SQL Server Data Tools**</span></span>  
  
-   <span data-ttu-id="07a94-108">В обозревателе решений среды [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , а затем разверните узел **Пакеты служб SSIS** , чтобы увидеть обновленные пакеты.</span><span class="sxs-lookup"><span data-stu-id="07a94-108">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in Solution Explorer, open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project, and then expand the **SSIS Packages** node to see the upgraded packages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="07a94-109">Варианты</span><span class="sxs-lookup"><span data-stu-id="07a94-109">Options</span></span>  
 <span data-ttu-id="07a94-110">**Панель сообщений**</span><span class="sxs-lookup"><span data-stu-id="07a94-110">**Message pane**</span></span>  
 <span data-ttu-id="07a94-111">Отображает сообщения о ходе обновления и сводку в течение процесса обновления.</span><span class="sxs-lookup"><span data-stu-id="07a94-111">Displays progress messages and summary information during the upgrade process.</span></span>  
  
 <span data-ttu-id="07a94-112">**Действие**</span><span class="sxs-lookup"><span data-stu-id="07a94-112">**Action**</span></span>  
 <span data-ttu-id="07a94-113">Просмотр действий по обновлению.</span><span class="sxs-lookup"><span data-stu-id="07a94-113">View the actions in the upgrade.</span></span>  
  
 <span data-ttu-id="07a94-114">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="07a94-114">**Status**</span></span>  
 <span data-ttu-id="07a94-115">Просмотр результатов каждого действия.</span><span class="sxs-lookup"><span data-stu-id="07a94-115">View the result of each action.</span></span>  
  
 <span data-ttu-id="07a94-116">**Message**</span><span class="sxs-lookup"><span data-stu-id="07a94-116">**Message**</span></span>  
 <span data-ttu-id="07a94-117">Просмотр сообщений об ошибках, которые формируются каждым действием.</span><span class="sxs-lookup"><span data-stu-id="07a94-117">View the error messages that each action generates.</span></span>  
  
 <span data-ttu-id="07a94-118">**Остановить**</span><span class="sxs-lookup"><span data-stu-id="07a94-118">**Stop**</span></span>  
 <span data-ttu-id="07a94-119">Остановка обновления пакетов.</span><span class="sxs-lookup"><span data-stu-id="07a94-119">Stop the package upgrade.</span></span>  
  
 <span data-ttu-id="07a94-120">**Отчет**</span><span class="sxs-lookup"><span data-stu-id="07a94-120">**Report**</span></span>  
 <span data-ttu-id="07a94-121">Выбор действий с отчетом, содержащим результаты обновления пакетов:</span><span class="sxs-lookup"><span data-stu-id="07a94-121">Select what you want to do with the report that contains the results of the package upgrade:</span></span>  
  
-   <span data-ttu-id="07a94-122">просмотр отчета в режиме в сети;</span><span class="sxs-lookup"><span data-stu-id="07a94-122">View the report online.</span></span>  
  
-   <span data-ttu-id="07a94-123">сохранение отчета в файл;</span><span class="sxs-lookup"><span data-stu-id="07a94-123">Save the report to a file.</span></span>  
  
-   <span data-ttu-id="07a94-124">копирование отчета в буфер обмена;</span><span class="sxs-lookup"><span data-stu-id="07a94-124">Copy the report to the Clipboard</span></span>  
  
-   <span data-ttu-id="07a94-125">отправка отчета по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="07a94-125">Send the report as an e-mail message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07a94-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="07a94-126">See Also</span></span>  
 [<span data-ttu-id="07a94-127">Обновление пакетов служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="07a94-127">Upgrade Integration Services Packages</span></span>](install-windows/upgrade-integration-services-packages.md)  
  
  
