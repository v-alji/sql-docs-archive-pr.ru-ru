---
title: Службы Integration Services (службы SSIS) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services service, about Integration Services service
- SQL Server Integration Services service
- service [Integration Services],about Integration Services service
- service [Integration Services]
- SQL Server Integration Services, service
ms.assetid: 2c785b3b-4a0c-4df7-b5cd-23756dc87842
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 04b24f0f0d54009c50654904d606a208504f229c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751288"
---
# <a name="integration-services-service-ssis-service"></a><span data-ttu-id="270bb-102">Службы Integration Services (службы SSIS)</span><span class="sxs-lookup"><span data-stu-id="270bb-102">Integration Services Service (SSIS Service)</span></span>
  <span data-ttu-id="270bb-103">В подразделах этого раздела описывается служба [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] — служба Windows для управления пакетами служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="270bb-103">The topics in this section discuss the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service, a Windows service for managing [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span> <span data-ttu-id="270bb-104">Эта служба не требуется для создания, сохранения и выполнения пакетов служб Integration Services.</span><span class="sxs-lookup"><span data-stu-id="270bb-104">This service is not required to create, save, and run Integration Services packages.</span></span> [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] <span data-ttu-id="270bb-105">поддерживает службу [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] для обеспечения обратной совместимости с более ранними версиями служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="270bb-105">supports the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service for backward compatibility with earlier releases of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="270bb-106">Начиная с [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] сохраняет объекты, параметры и рабочие данные в `SSISDB` базе данных для проектов, развернутых на [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] сервере с помощью модели развертывания проекта.</span><span class="sxs-lookup"><span data-stu-id="270bb-106">Starting in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] stores objects, settings, and operational data in the `SSISDB` database for projects that you've deployed to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server using the project deployment model.</span></span> <span data-ttu-id="270bb-107">На сервере служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , который является экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ядра СУБД, размещается база данных.</span><span class="sxs-lookup"><span data-stu-id="270bb-107">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server, which is an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Database Engine, hosts the database.</span></span> <span data-ttu-id="270bb-108">Дополнительные сведения о базе данных см. в разделе [Каталог служб SSIS](../catalog/ssis-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="270bb-108">For more information about the database, see [SSIS Catalog](../catalog/ssis-catalog.md).</span></span> <span data-ttu-id="270bb-109">Дополнительные сведения о развертывании проектов на сервере служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] см. в разделе [Развертывание проектов на сервере служб Integration Services](../deploy-projects-to-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="270bb-109">For more information about deploying projects to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server, see [Deploy Projects to Integration Services Server](../deploy-projects-to-integration-services-server.md).</span></span>  
  
## <a name="management-capabilities"></a><span data-ttu-id="270bb-110">Функции управления</span><span class="sxs-lookup"><span data-stu-id="270bb-110">Management Capabilities</span></span>  
 <span data-ttu-id="270bb-111">Служба [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] является службой Windows для управления пакетами служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="270bb-111">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service is a Windows service for managing [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span> <span data-ttu-id="270bb-112">Служба [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] доступна только в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="270bb-112">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service is available only in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="270bb-113">Использование службы Windows служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] дает следующие возможности управления:</span><span class="sxs-lookup"><span data-stu-id="270bb-113">Running the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service provides the following management capabilities:</span></span>  
  
-   <span data-ttu-id="270bb-114">запуск удаленных и локально хранимых пакетов;</span><span class="sxs-lookup"><span data-stu-id="270bb-114">Starting remote and locally stored packages</span></span>  
  
-   <span data-ttu-id="270bb-115">остановка удаленных и локально запущенных пакетов;</span><span class="sxs-lookup"><span data-stu-id="270bb-115">Stopping remote and locally running packages</span></span>  
  
-   <span data-ttu-id="270bb-116">наблюдение за работой удаленных и локальных пакетов;</span><span class="sxs-lookup"><span data-stu-id="270bb-116">Monitoring remote and locally running packages</span></span>  
  
-   <span data-ttu-id="270bb-117">импорт и экспорт пакетов;</span><span class="sxs-lookup"><span data-stu-id="270bb-117">Importing and exporting packages</span></span>  
  
-   <span data-ttu-id="270bb-118">управление хранилищем пакетов;</span><span class="sxs-lookup"><span data-stu-id="270bb-118">Managing package storage</span></span>  
  
-   <span data-ttu-id="270bb-119">настройка папок хранения;</span><span class="sxs-lookup"><span data-stu-id="270bb-119">Customizing storage folders</span></span>  
  
-   <span data-ttu-id="270bb-120">остановка запущенных пакетов при остановке службы;</span><span class="sxs-lookup"><span data-stu-id="270bb-120">Stopping running packages when the service is stopped</span></span>  
  
-   <span data-ttu-id="270bb-121">просмотр журнала событий Windows;</span><span class="sxs-lookup"><span data-stu-id="270bb-121">Viewing the Windows Event log</span></span>  
  
-   <span data-ttu-id="270bb-122">соединение с несколькими серверами служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="270bb-122">Connecting to multiple [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] servers</span></span>  
  
## <a name="startup-type-for-integration-services-service"></a><span data-ttu-id="270bb-123">Тип запуска службы Integration Services</span><span class="sxs-lookup"><span data-stu-id="270bb-123">Startup Type for Integration Services Service</span></span>  
 <span data-ttu-id="270bb-124">Служба [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] устанавливается при установке компонента [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="270bb-124">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service is installed when you install the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] component of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="270bb-125">По умолчанию запускается служба [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] и устанавливается ее автоматический запуск.</span><span class="sxs-lookup"><span data-stu-id="270bb-125">By default, the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service is started and the startup type of the service is set to automatic.</span></span> <span data-ttu-id="270bb-126">Для наблюдения за пакетами, хранящимися в хранилище пакетов служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] , эта служба должна быть запущена.</span><span class="sxs-lookup"><span data-stu-id="270bb-126">The service must be running to monitor the packages that are stored in the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Store.</span></span> <span data-ttu-id="270bb-127">Хранилищем пакетов служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] может быть как база данных msdb в экземпляре служб [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , так и назначенные папки файловой системы.</span><span class="sxs-lookup"><span data-stu-id="270bb-127">The [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Store can be either the msdb database in an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or the designated folders in the file system.</span></span>  
  
 <span data-ttu-id="270bb-128">Запуск службы Windows служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] не требуется, если необходимо только создавать и выполнять пакеты служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="270bb-128">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service is not required if you only want to design and execute [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span> <span data-ttu-id="270bb-129">Однако эта служба необходима для перечисления и монитора пакетов, использующих среду [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="270bb-129">However, the service is required to list and monitor packages using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="270bb-130">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="270bb-130">Related Tasks</span></span>  
  
-   [<span data-ttu-id="270bb-131">задать свойства службы Integration Services</span><span class="sxs-lookup"><span data-stu-id="270bb-131">Set the Properties of the Integration Services Service</span></span>](../set-the-properties-of-the-integration-services-service.md)  
  
-   [<span data-ttu-id="270bb-132">просмотреть события службы Integration Services</span><span class="sxs-lookup"><span data-stu-id="270bb-132">View Events for the Integration Services Service</span></span>](../view-events-for-the-integration-services-service.md)  
  
  
