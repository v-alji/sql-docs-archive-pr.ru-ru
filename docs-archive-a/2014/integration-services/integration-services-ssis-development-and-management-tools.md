---
title: Integration Services (SSIS) и среды Studio | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- studio environments [Integration Services]
- tools [Integration Services], Business Intelligence Development Studio
- Business Intelligence Development Studio, Integration Services in
- SQL Server Management Studio [Integration Services]
- SSIS, studio environments
- SQL Server Integration Services, studio environments
- tools [Integration Services], SQL Server Management Studio
ms.assetid: 4eb73e65-d9f3-4ac6-a408-abfa85afc537
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bfe0cf7ef482dce3870db8c730c597daf1d539e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664390"
---
# <a name="integration-services-ssis-and-studio-environments"></a><span data-ttu-id="d9efe-102">Службы Integration Services (SSIS) и среды Studio</span><span class="sxs-lookup"><span data-stu-id="d9efe-102">Integration Services (SSIS) and Studio Environments</span></span>
  <span data-ttu-id="d9efe-103">Службы[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] содержат две интегрированные среды для работы со службами [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="d9efe-103">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] includes two studios for working with [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="d9efe-104">Среда[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] предназначена для разработки пакетов [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , необходимых для бизнес-решения.</span><span class="sxs-lookup"><span data-stu-id="d9efe-104">[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] for developing the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages that a business solution requires.</span></span> <span data-ttu-id="d9efe-105">Среда[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] предоставляет проект [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , в котором можно создавать пакеты.</span><span class="sxs-lookup"><span data-stu-id="d9efe-105">[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] provides the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project in which you create packages.</span></span>  
  
-   <span data-ttu-id="d9efe-106">Среда[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] предназначена для управления пакетами в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="d9efe-106">[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] for managing packages in a production environment.</span></span>  
  
## <a name="sql-server-data-tools"></a><span data-ttu-id="d9efe-107">SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="d9efe-107">SQL Server Data Tools</span></span>  
 <span data-ttu-id="d9efe-108">Работая в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], можно выполнять следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="d9efe-108">Working in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], you can perform the following tasks:</span></span>  
  
-   <span data-ttu-id="d9efe-109">Запускать мастер импорта и экспорта [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] для создания основных пакетов, которые осуществляют копирование данных из источника в место назначения.</span><span class="sxs-lookup"><span data-stu-id="d9efe-109">Run the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Import and Export Wizard to create basic packages that copy data from a source to a destination.</span></span>  
  
-   <span data-ttu-id="d9efe-110">Создавать пакеты, содержащие сложные потоки управления, потоки данных, событийно-управляемую логику и ведение журнала.</span><span class="sxs-lookup"><span data-stu-id="d9efe-110">Create packages that include complex control flow, data flow, event-driven logic, and logging.</span></span>  
  
-   <span data-ttu-id="d9efe-111">Проверять и запускать отладку для пакетов при помощи функций диагностики и наблюдения в конструкторе служб [!INCLUDE[ssIS](../includes/ssis-md.md)] и функций отладки в [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d9efe-111">Test and debug packages by using the troubleshooting and monitoring features in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, and the debugging features in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="d9efe-112">Создавать настройки для обновления свойств пакетов и объектов пакетов в процессе выполнения.</span><span class="sxs-lookup"><span data-stu-id="d9efe-112">Create configurations that update the properties of packages and package objects at run time.</span></span>  
  
-   <span data-ttu-id="d9efe-113">Создавать программу развертывания, при помощи которой можно устанавливать пакеты и их зависимости на другие компьютеры.</span><span class="sxs-lookup"><span data-stu-id="d9efe-113">Create a deployment utility that can install packages and their dependencies on other computers.</span></span>  
  
-   <span data-ttu-id="d9efe-114">Сохранять копии пакетов в базе данных [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] msdb, в хранилище пакетов служб [!INCLUDE[ssIS](../includes/ssis-md.md)] и в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="d9efe-114">Save copies of packages to the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] msdb database, the [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Store, and the file system.</span></span>  
  
 <span data-ttu-id="d9efe-115">Дополнительные сведения о [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]см. в разделе [SQL Server Data Tools (SSDT)](https://msdn.microsoft.com/library/hh272686.aspx).</span><span class="sxs-lookup"><span data-stu-id="d9efe-115">For more information about [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], see [SQL Server Data Tools](https://msdn.microsoft.com/library/hh272686.aspx).</span></span>  
  
## <a name="sql-server-management-studio"></a><span data-ttu-id="d9efe-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d9efe-116">SQL Server Management Studio</span></span>  
 <span data-ttu-id="d9efe-117">Среда[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] предоставляет службу [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , применяемую для управления пакетами и контроля за выполнением пакетов, а также для определения влияния и преобразования данных для объектов [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] и [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d9efe-117">[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] provides the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service that you use to manage packages, monitor running packages, and determine impact and data lineage for [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] and [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects.</span></span>  
  
 <span data-ttu-id="d9efe-118">Работая в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], можно выполнять следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="d9efe-118">Working in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], you can perform the following tasks:</span></span>  
  
-   <span data-ttu-id="d9efe-119">Создавать папки для систематизации пакетов нужным для организации образом.</span><span class="sxs-lookup"><span data-stu-id="d9efe-119">Create folders to organize packages in a way that is meaningful to your organization.</span></span>  
  
-   <span data-ttu-id="d9efe-120">Запускать пакеты, хранимые на локальном компьютере, при помощи программы выполнения пакетов.</span><span class="sxs-lookup"><span data-stu-id="d9efe-120">Run packages that are stored on the local computer by using the Execute Package utility.</span></span>  
  
-   <span data-ttu-id="d9efe-121">Запустите программу выполнения пакетов для создания командной строки, которую можно использовать в программе командной строки **dtexec** (dtexec.exe).</span><span class="sxs-lookup"><span data-stu-id="d9efe-121">Run the Execute Package utility to generate a command line to use when you run the **dtexec** command prompt utility (dtexec.exe).</span></span>  
  
-   <span data-ttu-id="d9efe-122">Проводить операции импорта и экспорта пакетов с базой данных [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] msdb, хранилищами пакетов [!INCLUDE[ssIS](../includes/ssis-md.md)] и с файловой системой.</span><span class="sxs-lookup"><span data-stu-id="d9efe-122">Import and export packages to and from the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] msdb database, the [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Store, and the file system.</span></span>  
  
