---
title: Сервер Integration Services (SSIS) | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- packages [Integration Services], managing
- managing packages [Integration Services]
ms.assetid: 6d667bba-7c25-492a-8f4d-70ebaca28f40
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a0da83cdac269499dfbde7a6387a4af4690c83ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665503"
---
# <a name="integration-services-ssis-server"></a><span data-ttu-id="f2c9b-102">Службы Integration Services (SSIS Server)</span><span class="sxs-lookup"><span data-stu-id="f2c9b-102">Integration Services (SSIS) Server</span></span>
  <span data-ttu-id="f2c9b-103">После разработки и тестирования пакетов в [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]вы можете выполнить развертывание проектов, содержащих пакеты, на сервере [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f2c9b-103">After you design and test packages in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], you can deploy the projects that contain the packages to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
 <span data-ttu-id="f2c9b-104">Сервер служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] представляет собой экземпляр [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], на котором размещена база данных `SSISDB`.</span><span class="sxs-lookup"><span data-stu-id="f2c9b-104">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server is an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the `SSISDB` database.</span></span> <span data-ttu-id="f2c9b-105">В базе данных хранятся следующие объекты: пакеты, проекты, параметры, разрешения, свойства сервера и журнал операций.</span><span class="sxs-lookup"><span data-stu-id="f2c9b-105">The database stores the following objects: packages, projects, parameters, permissions, server properties, and operational history.</span></span>  
  
 <span data-ttu-id="f2c9b-106">База данных `SSISDB` предоставляет сведения об объектах в общих представлениях, к которым вы можете выполнить запрос.</span><span class="sxs-lookup"><span data-stu-id="f2c9b-106">The `SSISDB` database exposes the object information in public views that you can query.</span></span> <span data-ttu-id="f2c9b-107">База данных также содержит хранимые процедуры, которые вы можете вызвать для управления объектами.</span><span class="sxs-lookup"><span data-stu-id="f2c9b-107">The database also provides stored procedures that you can call to manage the objects.</span></span>  
  
 <span data-ttu-id="f2c9b-108">Прежде чем развертывать проекты на сервере [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], необходимо создать каталог `SSISDB`.</span><span class="sxs-lookup"><span data-stu-id="f2c9b-108">Before you can deploy the projects to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server, you need to create the `SSISDB` catalog.</span></span>  
  
 <span data-ttu-id="f2c9b-109">Общие сведения о функциональных возможностях каталога SSISDB см. в разделе [Каталог служб SSIS](ssis-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="f2c9b-109">For an overview of the SSISDB catalog functionality, see [SSIS Catalog](ssis-catalog.md).</span></span>  
  
## <a name="high-availability"></a><span data-ttu-id="f2c9b-110">Высокий уровень доступности</span><span class="sxs-lookup"><span data-stu-id="f2c9b-110">High Availability</span></span>  
 <span data-ttu-id="f2c9b-111">Как и другие пользовательские базы данных, база данных `SSISDB` поддерживает зеркальное отображение базы данных и репликацию.</span><span class="sxs-lookup"><span data-stu-id="f2c9b-111">Like other user databases, the `SSISDB` database does support database mirroring and replication.</span></span> <span data-ttu-id="f2c9b-112">Дополнительные сведения о зеркальном отображении и репликации см. в разделе [Зеркальное отображение базы данных (SQL Server)](../../database-engine/database-mirroring/database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f2c9b-112">For more information about mirroring and replication, see [Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md).</span></span>  
  
 <span data-ttu-id="f2c9b-113">Также вы можете обеспечить высокий уровень доступности SSISDB и содержимого с помощью служб SSIS и групп доступности AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="f2c9b-113">You can also provide high-availability of SSISDB and its contents by making use of SSIS and AlwaysOn Availability Groups.</span></span> <span data-ttu-id="f2c9b-114">Дополнительные сведения см. в записи блога Метта Мэйсона (Matt Masson) [Службы SSIS с AlwaysOn](https://go.microsoft.com/fwlink/?LinkId=255873)на сайте blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="f2c9b-114">For more information, see this blog post by Matt Masson, [SSIS with AlwaysOn](https://go.microsoft.com/fwlink/?LinkId=255873), at blogs.msdn.com.</span></span>  
  
##  <a name="integration-services-server-in-sql-server-management-studio"></a><a name="ssms"></a><span data-ttu-id="f2c9b-115">Integration Services Server в SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f2c9b-115">Integration Services Server in SQL Server Management Studio</span></span>  
 <span data-ttu-id="f2c9b-116">При подключении к экземпляру [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], на котором размещена база данных `SSISDB`, в обозревателе объектов отображаются следующие объекты:</span><span class="sxs-lookup"><span data-stu-id="f2c9b-116">When you connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the `SSISDB` database, you see the following objects in Object Explorer:</span></span>  
  
-   <span data-ttu-id="f2c9b-117">**База данных SSISDB**</span><span class="sxs-lookup"><span data-stu-id="f2c9b-117">**SSISDB Database**</span></span>  
  
     <span data-ttu-id="f2c9b-118">`SSISDB`База данных отображается в узле " **базы данных** " в разделе "Просмотр объектов".</span><span class="sxs-lookup"><span data-stu-id="f2c9b-118">The `SSISDB` database appears under the **Databases** node in Object Explore.</span></span> <span data-ttu-id="f2c9b-119">Вы можете создавать запросы к представлениям и вызывать хранимые процедуры для управления сервером служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] и объектами, которые хранятся на нем.</span><span class="sxs-lookup"><span data-stu-id="f2c9b-119">You can query the views and call the stored procedures that manage the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server and the objects that are stored on the server.</span></span>  
  
-   <span data-ttu-id="f2c9b-120">**Каталоги служб Integration Services**</span><span class="sxs-lookup"><span data-stu-id="f2c9b-120">**Integration Services Catalogs**</span></span>  
  
     <span data-ttu-id="f2c9b-121">В узле **Каталоги служб Integration Services** есть папки для проектов и сред [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f2c9b-121">Under the **Integration Services Catalogs** node there are folders for [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] projects and environments.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="f2c9b-122">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="f2c9b-122">Related Tasks</span></span>  
  
-   [<span data-ttu-id="f2c9b-123">Создание каталога служб SSIS</span><span class="sxs-lookup"><span data-stu-id="f2c9b-123">Create the SSIS Catalog</span></span>](../create-the-ssis-catalog.md)  
  
-   [<span data-ttu-id="f2c9b-124">Просмотр списка пакетов на сервере служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="f2c9b-124">View the List of Packages on the Integration Services Server</span></span>](view-the-list-of-packages-on-the-integration-services-server.md)  
  
-   [<span data-ttu-id="f2c9b-125">Развертывание проектов на сервере служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="f2c9b-125">Deploy Projects to Integration Services Server</span></span>](../deploy-projects-to-integration-services-server.md)  
  
-   [<span data-ttu-id="f2c9b-126">Выполнение пакета на сервере служб SSIS с использованием среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f2c9b-126">Run a Package on the SSIS Server Using SQL Server Management Studio</span></span>](../run-a-package-on-the-ssis-server-using-sql-server-management-studio.md)  
  
## <a name="related-content"></a><span data-ttu-id="f2c9b-127">См. также</span><span class="sxs-lookup"><span data-stu-id="f2c9b-127">Related Content</span></span>  
 <span data-ttu-id="f2c9b-128">Запись в блоге [Службы SSIS с AlwaysOn](https://go.microsoft.com/fwlink/?LinkId=255873)на blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="f2c9b-128">Blog entry, [SSIS with AlwaysOn](https://go.microsoft.com/fwlink/?LinkId=255873), at blogs.msdn.com.</span></span>  
  
  
