---
title: Указание параметров развертывания секций и ролей | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- input files [Analysis Services]
- partitions [Analysis Services], deployment options
- Analysis Services deployments, roles
- Analysis Services deployments, partitions
- Analysis Services Deployment Wizard, roles
- Analysis Services Deployment Wizard, partitions
- deploying [Analysis Services], roles
- roles [Analysis Services], deployment options
- deploying [Analysis Services], partitions
- modifying role deployments
- modifying partition deployments
ms.assetid: e9b9ca57-a5cc-4fc0-87b5-305257038d56
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8c8dd7bcb482c2d28a18e3039f5acb777b121202
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667914"
---
# <a name="specifying-partition-and-role-deployment-options"></a><span data-ttu-id="f8cce-102">Указание параметров развертывания секций и ролей</span><span class="sxs-lookup"><span data-stu-id="f8cce-102">Specifying Partition and Role Deployment Options</span></span>
  <span data-ttu-id="f8cce-103">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]Мастер развертывания считывает параметры развертывания секций и ролей из \<*project name*> файла deploymentoptions.</span><span class="sxs-lookup"><span data-stu-id="f8cce-103">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard reads the partition and role deployment options from the \<*project name*>.deploymentoptions file.</span></span> [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]<span data-ttu-id="f8cce-104">создает этот файл при сборке [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] проекта.</span><span class="sxs-lookup"><span data-stu-id="f8cce-104">creates this file when you build the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]<span data-ttu-id="f8cce-105">использует параметры развертывания секций и ролей текущего проекта при \<*project name*> создании файла. deploymentoptions.</span><span class="sxs-lookup"><span data-stu-id="f8cce-105">uses the partition and role deployment options of the current project when the \<*project name*>.deploymentoptions file is created.</span></span> <span data-ttu-id="f8cce-106">Дополнительные сведения о настройках конфигурации см. в разделе [Understanding the Input Files Used to Create the Deployment Script](deployment-script-files-input-used-to-create-deployment-script.md).</span><span class="sxs-lookup"><span data-stu-id="f8cce-106">For more information about configuration settings, see [Understanding the Input Files Used to Create the Deployment Script](deployment-script-files-input-used-to-create-deployment-script.md).</span></span>  
  
## <a name="reviewing-the-partition-and-role-deployment-options"></a><span data-ttu-id="f8cce-107">Просмотр параметров развертывания секций и ролей</span><span class="sxs-lookup"><span data-stu-id="f8cce-107">Reviewing the Partition and Role Deployment Options</span></span>  
 <span data-ttu-id="f8cce-108">Параметры развертывания в \<*project name*> файле. deploymentoptions включают следующее:</span><span class="sxs-lookup"><span data-stu-id="f8cce-108">The deployment options in the \<*project name*>.deploymentoptions file include the following:</span></span>  
  
 <span data-ttu-id="f8cce-109">**Параметры развертывания секций**</span><span class="sxs-lookup"><span data-stu-id="f8cce-109">**Partition deployment options**</span></span>  
 <span data-ttu-id="f8cce-110">\<*project name*>Файл. deploymentoptions указывает, сохраняются ли существующие секции в целевой базе данных (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="f8cce-110">The \<*project name*>.deploymentoptions file specifies whether existing partitions in the destination database are retained or overwritten (default).</span></span> <span data-ttu-id="f8cce-111">Если существующие секции сохраняются, то будут развернуты только новые секции, а секции и статистические схемы во всех существующих группах мер останутся неизменными.</span><span class="sxs-lookup"><span data-stu-id="f8cce-111">If existing partitions are retained, only new partitions will be deployed, and the partitions and aggregation designs on all existing measure groups are left unchanged.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f8cce-112">Если группа мер, на которой основана секция, удаляется, то секция также автоматически удаляется.</span><span class="sxs-lookup"><span data-stu-id="f8cce-112">If the measure group in which the partition exists is deleted, the partition is automatically deleted.</span></span>  
  
 <span data-ttu-id="f8cce-113">**Параметры развертывания ролей**</span><span class="sxs-lookup"><span data-stu-id="f8cce-113">**Role deployment options**</span></span>  
 <span data-ttu-id="f8cce-114">\<*project name*>Файл. deploymentoptions указывает один из следующих вариантов развертывания роли:</span><span class="sxs-lookup"><span data-stu-id="f8cce-114">The \<*project name*>.deploymentoptions file specifies one of the following role deployment options:</span></span>  
  
-   <span data-ttu-id="f8cce-115">Существующие роли и члены ролей в целевой базе данных сохраняются, и развертываются только новые роли и члены ролей.</span><span class="sxs-lookup"><span data-stu-id="f8cce-115">Existing roles and role members in the destination database are retained, and only new roles and role members are deployed.</span></span>  
  
-   <span data-ttu-id="f8cce-116">Все существующие роли и члены ролей в целевой базе данных заменяются развертываемыми ролями и членами.</span><span class="sxs-lookup"><span data-stu-id="f8cce-116">All existing roles and members in the destination database are replaced by the roles and members being deployed.</span></span>  
  
-   <span data-ttu-id="f8cce-117">Существующие роли и члены ролей в целевой базе данных сохраняются, и новые роли не развертываются.</span><span class="sxs-lookup"><span data-stu-id="f8cce-117">Existing roles and role members in the destination database are retained, and no new roles are deployed.</span></span>  
  
-   <span data-ttu-id="f8cce-118">**Примечание** При сохранении существующих ролей или членов ролей связанные с ними разрешения теряются.</span><span class="sxs-lookup"><span data-stu-id="f8cce-118">**Note** When existing roles and members are retained, the permissions associated with those roles are reset to none.</span></span> <span data-ttu-id="f8cce-119">Разрешения содержатся в защищаемых объектах, а не в ролях безопасности, с которыми они связаны.</span><span class="sxs-lookup"><span data-stu-id="f8cce-119">Security permissions are contained by the objects they secure, not by the security roles with which they are associated.</span></span> <span data-ttu-id="f8cce-120">Дополнительные сведения о работе с этим поведением с помощью мастера развертывания служб Analysis Services см. в разделе "сохраните роли и члены" в базе знаний Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f8cce-120">For more information about how to work with this behavior by using the Analysis Service Deployment Wizard, see 'Retain Roles and Members' in the Microsoft Knowledge Base.</span></span>  
  
## <a name="modifying-the-partition-and-role-deployment-options"></a><span data-ttu-id="f8cce-121">Изменение параметров развертывания секций и ролей</span><span class="sxs-lookup"><span data-stu-id="f8cce-121">Modifying the Partition and Role Deployment Options</span></span>  
 <span data-ttu-id="f8cce-122">Может потребоваться развернуть [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] проект, используя параметры раздела и роли, отличные от тех, которые хранятся в \<*project name*> файле deploymentoptions.</span><span class="sxs-lookup"><span data-stu-id="f8cce-122">You may have to deploy the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project using different partition and role options than those stored in the \<*project name*>.deploymentoptions file.</span></span> <span data-ttu-id="f8cce-123">Например, можно хранить существующие секции, роли и члены ролей вместо того, чтобы заменять все существующие секции, роли и члены, как указано в \<*project name*> файле deploymentoptions.</span><span class="sxs-lookup"><span data-stu-id="f8cce-123">For example, you may want to retain existing partitions, roles, and role members, instead of replacing all existing partitions, roles, and members as indicated in the \<*project name*>.deploymentoptions file.</span></span>  
  
 <span data-ttu-id="f8cce-124">Чтобы изменить развертывание секций и ролей в [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] проекте, нельзя изменить параметры секций и ролей в проекте, так как *\<project name>* диалоговое окно **страницы свойств** в [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] не отображает эти параметры.</span><span class="sxs-lookup"><span data-stu-id="f8cce-124">To modify the deployment of partitions and roles in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, you cannot change the partition and roles settings within the project because the *\<project name>* **Properties Pages** dialog box in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] does not display these options.</span></span> <span data-ttu-id="f8cce-125">Если вы хотите изменить параметры развертывания для ролей и секций, необходимо изменить эти сведения в \<*project name*> самом файле. deploymentoptions.</span><span class="sxs-lookup"><span data-stu-id="f8cce-125">If you want to change the deployment options for roles and partitions, you must change this information within the \<*project name*>.deploymentoptions file itself.</span></span> <span data-ttu-id="f8cce-126">В следующей процедуре описывается изменение параметров развертывания секций и ролей в \<*project name*> deploymentoptions файле.</span><span class="sxs-lookup"><span data-stu-id="f8cce-126">The following procedure describes how to change the partition and role deployment options within the \<*project name*>.deploymentoptions file.</span></span>  
  
#### <a name="to-change-the-deployment-of-partitions-or-roles-after-the-input-files-have-been-generated"></a><span data-ttu-id="f8cce-127">Изменение развертывания секций и ролей после формирования входных файлов</span><span class="sxs-lookup"><span data-stu-id="f8cce-127">To change the deployment of partitions or roles after the input files have been generated</span></span>  
  
-   <span data-ttu-id="f8cce-128">Запустите мастер развертывания служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] в интерактивном режиме и на странице **Параметры развертывания секций и ролей** укажите новые параметры развертывания для секций и ролей.</span><span class="sxs-lookup"><span data-stu-id="f8cce-128">Run the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard interactively, and on the **Partition and Role Deployment Options** page, specify new deployment options for the partitions and roles.</span></span>  
  
     <span data-ttu-id="f8cce-129">-или-</span><span class="sxs-lookup"><span data-stu-id="f8cce-129">-or-</span></span>  
  
-   <span data-ttu-id="f8cce-130">Запустите мастер развертывания служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] из командной строки и настройте его на работу в режиме файла ответов.</span><span class="sxs-lookup"><span data-stu-id="f8cce-130">Run the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard at the command prompt, and set the wizard to run in answer file mode.</span></span> <span data-ttu-id="f8cce-131">(Дополнительные сведения о режиме файла ответов см. [в разделе Запуск мастера развертывания Analysis Services](running-the-analysis-services-deployment-wizard.md).)</span><span class="sxs-lookup"><span data-stu-id="f8cce-131">(For more information about answer file mode, see [Running the Analysis Services Deployment Wizard](running-the-analysis-services-deployment-wizard.md).)</span></span>  
  
     <span data-ttu-id="f8cce-132">-или-</span><span class="sxs-lookup"><span data-stu-id="f8cce-132">-or-</span></span>  
  
-   <span data-ttu-id="f8cce-133">Откройте \<*project name*> . deploymentoptions в любом текстовом редакторе и вручную измените параметры.</span><span class="sxs-lookup"><span data-stu-id="f8cce-133">Open the \<*project name*>.deploymentoptions in any text editor and manually change the options.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8cce-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="f8cce-134">See Also</span></span>  
 <span data-ttu-id="f8cce-135">[Указание целевого объекта установки](deployment-script-files-specifying-the-installation-target.md) </span><span class="sxs-lookup"><span data-stu-id="f8cce-135">[Specifying the Installation Target](deployment-script-files-specifying-the-installation-target.md) </span></span>  
 <span data-ttu-id="f8cce-136">[Указание параметров конфигурации для развертывания решения](deployment-script-files-solution-deployment-config-settings.md) </span><span class="sxs-lookup"><span data-stu-id="f8cce-136">[Specifying Configuration Settings for Solution Deployment](deployment-script-files-solution-deployment-config-settings.md) </span></span>  
 [<span data-ttu-id="f8cce-137">Указание параметров обработки</span><span class="sxs-lookup"><span data-stu-id="f8cce-137">Specifying Processing Options</span></span>](deployment-script-files-specifying-processing-options.md)  
  
  
