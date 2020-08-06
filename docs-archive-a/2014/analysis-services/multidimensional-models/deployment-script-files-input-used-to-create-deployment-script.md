---
title: Основные сведения о входных файлах, используемых для создания скрипта развертывания | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- input files [Analysis Services]
- Analysis Services Deployment Wizard, scripts
- deploying [Analysis Services], input files
- Analysis Services Deployment Wizard, input files
- scripts [Analysis Services], deployment
- Analysis Services deployments, input files
- modifying input files
ms.assetid: 20e080cd-6a0e-4591-b022-ea4cd3638e36
author: minewiskan
ms.author: owend
ms.openlocfilehash: 34695993d4f153c6c0b97fef744d92c682517c99
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664597"
---
# <a name="understanding-the-input-files-used-to-create-the-deployment-script"></a><span data-ttu-id="dd41d-102">Основные сведения о входных файлах, применяемых для создания скрипта развертывания</span><span class="sxs-lookup"><span data-stu-id="dd41d-102">Understanding the Input Files Used to Create the Deployment Script</span></span>
  <span data-ttu-id="dd41d-103">При построении [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] проекта [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] создает XML-файлы для проекта.</span><span class="sxs-lookup"><span data-stu-id="dd41d-103">When you build a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] generates XML files for the project.</span></span> <span data-ttu-id="dd41d-104">Среда [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] помещает эти XML-файлы в выходную папку проекта служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd41d-104">[!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] puts these XML files in the Output folder of the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="dd41d-105">По умолчанию в качестве папки проекта используется \Bin.</span><span class="sxs-lookup"><span data-stu-id="dd41d-105">By default output is out in the \Bin folder.</span></span> <span data-ttu-id="dd41d-106">В следующей таблице перечислены XML-файлы, которые создает среда [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dd41d-106">The following table lists the XML files that [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] creates.</span></span>  
  
|<span data-ttu-id="dd41d-107">XMLA-файл</span><span class="sxs-lookup"><span data-stu-id="dd41d-107">XMLA file</span></span>|<span data-ttu-id="dd41d-108">Описание</span><span class="sxs-lookup"><span data-stu-id="dd41d-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dd41d-109">\<*project name*>. asdatabase</span><span class="sxs-lookup"><span data-stu-id="dd41d-109">\<*project name*>.asdatabase</span></span>|<span data-ttu-id="dd41d-110">Содержит декларативные определения всех объектов служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] проекта.</span><span class="sxs-lookup"><span data-stu-id="dd41d-110">Contains the declarative definitions for all the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects in the project.</span></span>|  
|<span data-ttu-id="dd41d-111">\<*project name*>. deploymenttargets</span><span class="sxs-lookup"><span data-stu-id="dd41d-111">\<*project name*>.deploymenttargets</span></span>|<span data-ttu-id="dd41d-112">Содержит имя экземпляра [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] и базы данных, в которой будут созданы объекты служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dd41d-112">Contains the name of the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance and database in which the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects will be created.</span></span>|  
|<span data-ttu-id="dd41d-113">\<*project name*>. configsettings</span><span class="sxs-lookup"><span data-stu-id="dd41d-113">\<*project name*>.configsettings</span></span>|<span data-ttu-id="dd41d-114">Содержит параметры, которые относятся к окружению, например сведения о соединении с источником данных и о месте хранения объектов.</span><span class="sxs-lookup"><span data-stu-id="dd41d-114">Contains environment specific settings, such as data source connection information and object storage locations.</span></span> <span data-ttu-id="dd41d-115">Параметры в этом файле переопределяют параметры в \<*project name*> asdatabase файле.</span><span class="sxs-lookup"><span data-stu-id="dd41d-115">Settings in this file override settings in the \<*project name*>.asdatabase file.</span></span>|  
|<span data-ttu-id="dd41d-116">\<*project name*>. deploymentoptions</span><span class="sxs-lookup"><span data-stu-id="dd41d-116">\<*project name*>.deploymentoptions</span></span>|<span data-ttu-id="dd41d-117">Содержит параметры развертывания, которые указывают, является ли развертывание транзакционным и нужно ли обрабатывать объекты после развертывания.</span><span class="sxs-lookup"><span data-stu-id="dd41d-117">Contains deployment options, such as whether deployment is transactional and whether deployed objects should be processed after deployment.</span></span>|  
  
> [!NOTE]  
>  [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] <span data-ttu-id="dd41d-118">не хранит пароли в файлах проектов.</span><span class="sxs-lookup"><span data-stu-id="dd41d-118">never stores passwords in its project files.</span></span>  
  
## <a name="modifying-the-input-files"></a><span data-ttu-id="dd41d-119">Изменение входных файлов</span><span class="sxs-lookup"><span data-stu-id="dd41d-119">Modifying the Input Files</span></span>  
 <span data-ttu-id="dd41d-120">Изменение значений во входных файлах или значений, полученных из входных файлов, позволяет изменить назначение развертывания, параметры конфигурации и параметры развертывания без изменения всего \<*project name*> файла. asdatabase (или всего файла скрипта XMLA при создании скрипта из существующей [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] базы данных).</span><span class="sxs-lookup"><span data-stu-id="dd41d-120">Modifying the values in the input files, or the values retrieved from the input files, makes it possible to change the deployment destination, the configuration settings, and deployment options without editing the whole \<*project name*>.asdatabase file (or a whole XMLA script file if you generate a script from an existing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database).</span></span> <span data-ttu-id="dd41d-121">Благодаря возможности редактирования отдельных файлов можно легко создавать различные скрипты развертывания для разных целей.</span><span class="sxs-lookup"><span data-stu-id="dd41d-121">Being able to modify individual files lets you easily create different deployment scripts for different purposes.</span></span>  
  
 <span data-ttu-id="dd41d-122">Следующие разделы содержат сведения об изменении значений в различных входных файлах:</span><span class="sxs-lookup"><span data-stu-id="dd41d-122">The following topics explain how to modify values in the various input files:</span></span>  
  
-   [<span data-ttu-id="dd41d-123">Указание целевого объекта установки</span><span class="sxs-lookup"><span data-stu-id="dd41d-123">Specifying the Installation Target</span></span>](deployment-script-files-specifying-the-installation-target.md)  
  
-   [<span data-ttu-id="dd41d-124">Указание параметров развертывания секций и ролей</span><span class="sxs-lookup"><span data-stu-id="dd41d-124">Specifying Partition and Role Deployment Options</span></span>](deployment-script-files-partition-and-role-deployment-options.md)  
  
-   [<span data-ttu-id="dd41d-125">Указание настроек конфигурации для развертывания решения</span><span class="sxs-lookup"><span data-stu-id="dd41d-125">Specifying Configuration Settings for Solution Deployment</span></span>](deployment-script-files-solution-deployment-config-settings.md)  
  
-   [<span data-ttu-id="dd41d-126">Указание параметров обработки</span><span class="sxs-lookup"><span data-stu-id="dd41d-126">Specifying Processing Options</span></span>](deployment-script-files-specifying-processing-options.md)  
  
## <a name="see-also"></a><span data-ttu-id="dd41d-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="dd41d-127">See Also</span></span>  
 <span data-ttu-id="dd41d-128">[Запуск мастера развертывания Analysis Services](running-the-analysis-services-deployment-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="dd41d-128">[Running the Analysis Services Deployment Wizard](running-the-analysis-services-deployment-wizard.md) </span></span>  
 [<span data-ttu-id="dd41d-129">Основные сведения о скрипте развертывания служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="dd41d-129">Understanding the Analysis Services Deployment Script</span></span>](understanding-the-analysis-services-deployment-script.md)  
  
  
