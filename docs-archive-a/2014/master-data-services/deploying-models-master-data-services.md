---
title: Развертывание моделей (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deployment packages [Master Data Services], about deployment packages
- deployment packages [Master Data Services]
ms.assetid: 30085c08-034f-4efe-80fe-408f9091ff5c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: a9cc99112ec874e89ae07faa575235d9a041a972
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669450"
---
# <a name="deploying-models-master-data-services"></a><span data-ttu-id="67980-102">Развертывание моделей (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="67980-102">Deploying Models (Master Data Services)</span></span>
  <span data-ttu-id="67980-103">В службах [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]пакет представляет собой XML-файл, содержащий развертываемую структуру модели и (необязательно) данные этой модели.</span><span class="sxs-lookup"><span data-stu-id="67980-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], a package is an XML file that contains a deployable model structure, and optionally, data from the model.</span></span> <span data-ttu-id="67980-104">Пакеты модели используется для перемещения копий моделей из одной среды служб MDS в другую, либо для создания новых моделей в существующей среде MDS.</span><span class="sxs-lookup"><span data-stu-id="67980-104">Use model packages to move copies of models from one MDS environment to another, or to create new models in your existing MDS environment.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="67980-105">Пакеты могут быть развернуты только в выпуске [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , в котором они были созданы.</span><span class="sxs-lookup"><span data-stu-id="67980-105">Packages can be deployed to the edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] they were created in only.</span></span> <span data-ttu-id="67980-106">Это означает, что пакеты, созданные в среде [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] , не могут быть развернуты в [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] или более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="67980-106">This means that packages created in [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] cannot be deployed to [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] or higher.</span></span>  
  
## <a name="tools-for-deploying-models"></a><span data-ttu-id="67980-107">Инструменты для развертывания моделей</span><span class="sxs-lookup"><span data-stu-id="67980-107">Tools for Deploying Models</span></span>  
 <span data-ttu-id="67980-108">Для работы с пакетами модели можно использовать одно из трех средств, в зависимости от задач, которые требуется выполнить.</span><span class="sxs-lookup"><span data-stu-id="67980-108">To work with model packages, you can use one of three tools, depending on your needs.</span></span>  
  
-   <span data-ttu-id="67980-109">**Средство MDSModelDeploy**. Для создания и развертывания объектов и данных модели используйте средство MDSModelDeploy.exe.</span><span class="sxs-lookup"><span data-stu-id="67980-109">**MDSModelDeploy tool**: To create and deploy model objects and data, use the MDSModelDeploy.exe tool.</span></span> <span data-ttu-id="67980-110">Если при установке MDS был выбран путь по умолчанию, это средство находится в папке *диск*: \PROGRAM Files\Microsoft SQL Server\120\Master Data Services\Configuration.</span><span class="sxs-lookup"><span data-stu-id="67980-110">If you selected the default path when installing MDS, this tool is located on *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\Configuration.</span></span>  
  
-   <span data-ttu-id="67980-111">**Мастер развертывания модели**. Чтобы создать и развернуть только пакеты структуры модели, воспользуйтесь мастером в веб-приложении [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="67980-111">**Model Deployment wizard**: To create and deploy packages of the model structure only, use the wizard in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application.</span></span> <span data-ttu-id="67980-112">Этот мастер нельзя использовать для развертывания данных.</span><span class="sxs-lookup"><span data-stu-id="67980-112">You cannot use this wizard to deploy data.</span></span>  
  
-   <span data-ttu-id="67980-113">**Редактор модели пакета**. Чтобы изменить пакет модели, используйте файл ModelPackageEditor.exe, который запускает редактор пакетов моделей.</span><span class="sxs-lookup"><span data-stu-id="67980-113">**Model Package Editor**: To edit a model package, use the ModelPackageEditor.exe that launches the Model Package Editor wizard.</span></span> <span data-ttu-id="67980-114">С помощью этого мастера выполняется изменения пакета, созданного средством MDSModelDeploy или мастером развертывания модели.</span><span class="sxs-lookup"><span data-stu-id="67980-114">You use this wizard to edit a package that was created by the MDSModelDeploy tool or the Model Deployment wizard.</span></span> <span data-ttu-id="67980-115">Если при установке MDS был выбран путь по умолчанию, это средство находится в папке *диск*: \PROGRAM Files\Microsoft SQL Server\120\Master Data Services\Configuration.</span><span class="sxs-lookup"><span data-stu-id="67980-115">If you selected the default path when installing MDS, this tool is located on *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\Configuration.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="67980-116">MDSDeployModel можно использовать для создания новой модели или клона модели или обновления существующей модели и ее данных.</span><span class="sxs-lookup"><span data-stu-id="67980-116">You can use the MDSDeployModel to create a new model, create a clone of a model, or update an existing model and its data.</span></span> <span data-ttu-id="67980-117">Если средство MDSModelDeploy используется для обновления существующей модели и ее данных и пакет не содержит сущность, атрибут или элемент, имеющиеся в целевой модели, MDSModelDeploy не удаляет из модели эту сущность, атрибут или элемент.</span><span class="sxs-lookup"><span data-stu-id="67980-117">If you use the MDSModelDeploy tool to update an existing model and its data, and the package does not contain an entity, attribute, or member that exists in the destination model, MDSModelDeploy will not delete that entity, attribute, or member from the model.</span></span>  
  
## <a name="what-packages-contain"></a><span data-ttu-id="67980-118">Содержимое пакетов</span><span class="sxs-lookup"><span data-stu-id="67980-118">What Packages Contain</span></span>  
 <span data-ttu-id="67980-119">Пакет модели представляет собой XML-файл, сохраняемый с расширением PKG.</span><span class="sxs-lookup"><span data-stu-id="67980-119">A model package is an XML file that is saved with the .pkg extension.</span></span> <span data-ttu-id="67980-120">При создании развертываемого пакета в него по желанию можно включить данные.</span><span class="sxs-lookup"><span data-stu-id="67980-120">When you create a deployment package, you can decide whether or not to include data.</span></span> <span data-ttu-id="67980-121">Если данные решено включить, то нужно выбрать для них версию.</span><span class="sxs-lookup"><span data-stu-id="67980-121">If you decide to include data, you must select a version of the data to include.</span></span>  
  
 <span data-ttu-id="67980-122">В пакет включаются все объекты модели.</span><span class="sxs-lookup"><span data-stu-id="67980-122">All model objects are included in a package.</span></span> <span data-ttu-id="67980-123">Эти объекты включают в себя:</span><span class="sxs-lookup"><span data-stu-id="67980-123">These objects are:</span></span>  
  
-   <span data-ttu-id="67980-124">Сущности</span><span class="sxs-lookup"><span data-stu-id="67980-124">Entities</span></span>  
  
-   <span data-ttu-id="67980-125">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="67980-125">Attributes</span></span>  
  
-   <span data-ttu-id="67980-126">Группы атрибутов</span><span class="sxs-lookup"><span data-stu-id="67980-126">Attribute groups</span></span>  
  
-   <span data-ttu-id="67980-127">Иерархии</span><span class="sxs-lookup"><span data-stu-id="67980-127">Hierarchies</span></span>  
  
-   <span data-ttu-id="67980-128">Коллекции</span><span class="sxs-lookup"><span data-stu-id="67980-128">Collections</span></span>  
  
-   <span data-ttu-id="67980-129">Бизнес-правила</span><span class="sxs-lookup"><span data-stu-id="67980-129">Business rules</span></span>  
  
-   <span data-ttu-id="67980-130">Флаги версии</span><span class="sxs-lookup"><span data-stu-id="67980-130">Version flags</span></span>  
  
-   <span data-ttu-id="67980-131">Представления подписки</span><span class="sxs-lookup"><span data-stu-id="67980-131">Subscription views</span></span>  
  
 <span data-ttu-id="67980-132">Пользовательские метаданные, атрибуты файлов и разрешения пользователей и групп не включаются.</span><span class="sxs-lookup"><span data-stu-id="67980-132">User-defined metadata, file attributes, and user and group permissions are not included.</span></span> <span data-ttu-id="67980-133">При развертывании модели их нужно обновить вручную.</span><span class="sxs-lookup"><span data-stu-id="67980-133">After you deploy a model, you must update these manually.</span></span>  
  
## <a name="sample-packages"></a><span data-ttu-id="67980-134">Образцы пакетов</span><span class="sxs-lookup"><span data-stu-id="67980-134">Sample Packages</span></span>  
 <span data-ttu-id="67980-135">При установке служб [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]также копируются файлы образцов пакетов.</span><span class="sxs-lookup"><span data-stu-id="67980-135">Sample package files are included when you install [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span></span> <span data-ttu-id="67980-136">Эти файлы пакетов расположены в каталоге Master Data Services\Samples\Packages, где установлена среда [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="67980-136">These package files are in the Master Data Services\Samples\Packages directory where you installed [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span></span> <span data-ttu-id="67980-137">При развертывании этих образцов пакетов с помощью средства MDSModelDeploy создаются и заполняются данными образцы моделей.</span><span class="sxs-lookup"><span data-stu-id="67980-137">When you deploy these sample packages by using the MDSModelDeploy tool, sample models are created and populated with data.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="67980-138">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="67980-138">Related Tasks</span></span>  
  
|<span data-ttu-id="67980-139">Описание задачи</span><span class="sxs-lookup"><span data-stu-id="67980-139">Task Description</span></span>|<span data-ttu-id="67980-140">Раздел</span><span class="sxs-lookup"><span data-stu-id="67980-140">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="67980-141">Средство MDSModelDeploy используется для создания новых пакетов объектов модели и данных.</span><span class="sxs-lookup"><span data-stu-id="67980-141">Create a new deployment package of model objects and/or data by using the MDSModelDeploy tool.</span></span>|[<span data-ttu-id="67980-142">Создание пакета развертывания модели при помощи MDSModelDeploy</span><span class="sxs-lookup"><span data-stu-id="67980-142">Create a Model Deployment Package by Using MDSModelDeploy</span></span>](../../2014/master-data-services/create-a-model-deployment-package-by-using-mdsmodeldeploy.md)|  
|<span data-ttu-id="67980-143">Создать новый пакет развертывания объектов модели можно только с помощью мастера.</span><span class="sxs-lookup"><span data-stu-id="67980-143">Create a new deployment package of model objects only by using the wizard.</span></span>|[<span data-ttu-id="67980-144">Создание пакета развертывания модели с помощью мастера</span><span class="sxs-lookup"><span data-stu-id="67980-144">Create a Model Deployment Package by Using the Wizard</span></span>](../../2014/master-data-services/create-a-model-deployment-package-by-using-the-wizard.md)|  
|<span data-ttu-id="67980-145">Средство MDSModelDeploy используется для развертывания пакета объектов модели и данных.</span><span class="sxs-lookup"><span data-stu-id="67980-145">Deploy a package of model objects and data by using the MDSModelDeploy tool.</span></span>|[<span data-ttu-id="67980-146">Развертывание пакета развертывания модели при помощи MDSModelDeploy</span><span class="sxs-lookup"><span data-stu-id="67980-146">Deploy a Model Deployment Package by Using MDSModelDeploy</span></span>](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-mdsmodeldeploy.md)|  
|<span data-ttu-id="67980-147">Развернуть пакет объектов модели можно только с помощью мастера.</span><span class="sxs-lookup"><span data-stu-id="67980-147">Deploy a package of model objects only by using the wizard.</span></span>|[<span data-ttu-id="67980-148">Развертывание пакета развертывания модели с помощью мастера</span><span class="sxs-lookup"><span data-stu-id="67980-148">Deploy a Model Deployment Package by Using the Wizard</span></span>](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-the-wizard.md)|  
|<span data-ttu-id="67980-149">Изменять пакет развертывания модели необходимо в тех случаях, когда требуется развернуть только определенные части модели, а не всю модель.</span><span class="sxs-lookup"><span data-stu-id="67980-149">Edit a model deployment package to deploy selected parts of a model, rather than the entire model.</span></span>|[<span data-ttu-id="67980-150">Изменение пакета развертывания модели</span><span class="sxs-lookup"><span data-stu-id="67980-150">Edit a Model Deployment Package</span></span>](../../2014/master-data-services/edit-a-model-deployment-package.md)|  
  
## <a name="related-content"></a><span data-ttu-id="67980-151">См. также</span><span class="sxs-lookup"><span data-stu-id="67980-151">Related Content</span></span>  
  
-   [<span data-ttu-id="67980-152">Варианты развертывания модели (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="67980-152">Model Deployment Options &#40;Master Data Services&#41;</span></span>](model-deployment-options-master-data-services.md)  
  
  
