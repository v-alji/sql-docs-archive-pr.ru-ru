---
title: Развертывание пакета развертывания модели с помощью мастера | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deployment packages [Master Data Services], deploying
- models [Master Data Services], deploying a package
ms.assetid: 4f65dc60-0ff8-46e6-9988-5bc5b9603ad0
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 75af9f7c12d866c6d9707f62c898aa7601f94800
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736455"
---
# <a name="deploy-a-model-deployment-package-by-using-the-wizard"></a><span data-ttu-id="b06a8-102">Развертывание пакета развертывания модели с помощью мастера</span><span class="sxs-lookup"><span data-stu-id="b06a8-102">Deploy a Model Deployment Package by Using the Wizard</span></span>
  <span data-ttu-id="b06a8-103">Мастер развертывания модели [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] служит для развертывания пакетов, содержащих только объекты модели.</span><span class="sxs-lookup"><span data-stu-id="b06a8-103">Use the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] model deployment wizard to deploy packages that contain model objects only.</span></span> <span data-ttu-id="b06a8-104">Если нужно развернуть пакет с данными, см. раздел [Развертывание пакета развертывания модели при помощи MDSModelDeploy](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span><span class="sxs-lookup"><span data-stu-id="b06a8-104">If you need to deploy a package with data, see [Deploy a Model Deployment Package by Using MDSModelDeploy](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b06a8-105">Пакеты могут быть развернуты только в выпуске [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , в котором они были созданы.</span><span class="sxs-lookup"><span data-stu-id="b06a8-105">Packages can be deployed to the edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] they were created in only.</span></span> <span data-ttu-id="b06a8-106">Это означает, что пакеты, созданные в среде [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] , не могут быть развернуты в [!INCLUDE[ssSQL11](../includes/sssql11-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b06a8-106">This means that packages created in [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] cannot be deployed to [!INCLUDE[ssSQL11](../includes/sssql11-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b06a8-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="b06a8-107">Prerequisites</span></span>  
 <span data-ttu-id="b06a8-108">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="b06a8-108">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="b06a8-109">необходимо иметь разрешение на доступ к функциональной области **Администрирование системы** в целевой среде служб [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] ;</span><span class="sxs-lookup"><span data-stu-id="b06a8-109">You must have permission to access the **System Administration** functional area in the target [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] environment.</span></span>  
  
-   <span data-ttu-id="b06a8-110">должен существовать пакет развертывания модели.</span><span class="sxs-lookup"><span data-stu-id="b06a8-110">A model deployment package must exist.</span></span> <span data-ttu-id="b06a8-111">Дополнительные сведения см. в разделе [Создание пакета развертывания модели с помощью мастера](../../2014/master-data-services/create-a-model-deployment-package-by-using-the-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="b06a8-111">For more information, see [Create a Model Deployment Package by Using the Wizard](../../2014/master-data-services/create-a-model-deployment-package-by-using-the-wizard.md).</span></span>  
  
-   <span data-ttu-id="b06a8-112">В среде, в которой выполняется развертывание модели, необходимо обладать правами администратора.</span><span class="sxs-lookup"><span data-stu-id="b06a8-112">You must be an administrator in the environment where you are deploying the model.</span></span> <span data-ttu-id="b06a8-113">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="b06a8-113">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-deploy-a-model-deployment-package-of-model-objects-only"></a><span data-ttu-id="b06a8-114">Развертывание пакета развертывания модели, состоящего только из объектов модели</span><span class="sxs-lookup"><span data-stu-id="b06a8-114">To deploy a model deployment package of model objects only</span></span>  
  
1.  <span data-ttu-id="b06a8-115">В [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните область **Администрирование системы**.</span><span class="sxs-lookup"><span data-stu-id="b06a8-115">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="b06a8-116">На странице **Представление модели** в строке меню наведите курсор на пункт **Система** и выберите **Развертывание**.</span><span class="sxs-lookup"><span data-stu-id="b06a8-116">On the **Model View** page, from the menu bar, point to **System** and click **Deployment**.</span></span>  
  
3.  <span data-ttu-id="b06a8-117">В **Диспетчере развертывания модели**нажмите **Развернуть**.</span><span class="sxs-lookup"><span data-stu-id="b06a8-117">On the **Model Deployment Wizard**, click **Deploy**.</span></span>  
  
4.  <span data-ttu-id="b06a8-118">Нажмите кнопку **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="b06a8-118">Click **Browse**.</span></span>  
  
5.  <span data-ttu-id="b06a8-119">Найдите свой пакет развертывания (файл PKG) и нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="b06a8-119">Find your deployment package (.pkg file) and click **Open**.</span></span>  
  
6.  <span data-ttu-id="b06a8-120">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b06a8-120">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="b06a8-121">После загрузки пакета нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="b06a8-121">After the package is loaded, click **Next**.</span></span>  
  
8.  <span data-ttu-id="b06a8-122">Если модель уже существует, ее можно обновить, выбрав **Обновить существующую модель**.</span><span class="sxs-lookup"><span data-stu-id="b06a8-122">If the model already exists, you can update it by selecting **Update the existing model**.</span></span> <span data-ttu-id="b06a8-123">Чтобы создать новую модель, выберите **Создать новую модель** и после нажатия кнопки **Далее** укажите имя новой модели.</span><span class="sxs-lookup"><span data-stu-id="b06a8-123">To create a new model, select **Create a new model** and after you click **Next** you can type a name for the new model.</span></span>  
  
9. <span data-ttu-id="b06a8-124">Нажмите кнопку **Готово**, чтобы закрыть мастер.</span><span class="sxs-lookup"><span data-stu-id="b06a8-124">Click **Finish** to exit the wizard.</span></span>  
  
 <span data-ttu-id="b06a8-125">**Примечания.**</span><span class="sxs-lookup"><span data-stu-id="b06a8-125">**Notes:**</span></span>  
  
-   <span data-ttu-id="b06a8-126">Если представление подписки в пакете имеет то же имя, что и представление подписки в существующей модели, это представление создается как *modelname. subscriptionviewname*.</span><span class="sxs-lookup"><span data-stu-id="b06a8-126">If a subscription view in the package has the same name as a subscription view in an existing model, the view is created as *modelname.subscriptionviewname*.</span></span> <span data-ttu-id="b06a8-127">Если это имя уже используется, то представление подписки не создается.</span><span class="sxs-lookup"><span data-stu-id="b06a8-127">If this name is already in use, the subscription view is not created.</span></span>  
  
-   <span data-ttu-id="b06a8-128">Процесс развертывания состоит из четырех шагов.</span><span class="sxs-lookup"><span data-stu-id="b06a8-128">The deployment process has four steps:</span></span>  
  
    1.  <span data-ttu-id="b06a8-129">Создаются объекты модели.</span><span class="sxs-lookup"><span data-stu-id="b06a8-129">The model objects are created.</span></span>  
  
    2.  <span data-ttu-id="b06a8-130">Создаются представления подписки.</span><span class="sxs-lookup"><span data-stu-id="b06a8-130">Subscription views are created.</span></span>  
  
    3.  <span data-ttu-id="b06a8-131">Создаются бизнес-правила.</span><span class="sxs-lookup"><span data-stu-id="b06a8-131">Business rules are created.</span></span>  
  
    4.  <span data-ttu-id="b06a8-132">Производится заполнение основных данных.</span><span class="sxs-lookup"><span data-stu-id="b06a8-132">Master data is populated.</span></span>  
  
-   <span data-ttu-id="b06a8-133">Если при создании новой или клонированной модели процесс на любом этапе завершается ошибкой, модель удаляется.</span><span class="sxs-lookup"><span data-stu-id="b06a8-133">When creating a new or cloned model, if the process fails during any step, the model is deleted.</span></span>  
  
     <span data-ttu-id="b06a8-134">При обновлении в случае неудачного завершения любого из первых трех шагов переход к следующему шагу не производится. Однако откат уже внесенных изменений также не выполняется.</span><span class="sxs-lookup"><span data-stu-id="b06a8-134">When updating a model, if the process fails during any of the first three steps, it does not proceed beyond that step; however, changes that are already made are not rolled back.</span></span> <span data-ttu-id="b06a8-135">Если процесс развертывания завершается неудачей в шаге 4, обновляются те элементы, которые могут обновиться.</span><span class="sxs-lookup"><span data-stu-id="b06a8-135">If the process fails in step 4, members that can be updated are updated.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="b06a8-136">Next Steps</span><span class="sxs-lookup"><span data-stu-id="b06a8-136">Next Steps</span></span>  
 <span data-ttu-id="b06a8-137">Определенные пользователем метаданные, атрибуты файлов и разрешения для пользователей и групп не включаются в пакеты развертывания модели.</span><span class="sxs-lookup"><span data-stu-id="b06a8-137">User-defined metadata, file attributes, and user and group permissions are not included in model deployment packages.</span></span> <span data-ttu-id="b06a8-138">При развертывании модели их нужно обновить вручную.</span><span class="sxs-lookup"><span data-stu-id="b06a8-138">After you deploy a model, you must update these manually.</span></span> <span data-ttu-id="b06a8-139">Дополнительные сведения см. в разделе:</span><span class="sxs-lookup"><span data-stu-id="b06a8-139">For more information, see:</span></span>  
  
-   [<span data-ttu-id="b06a8-140">Добавление Master Data Services &#40;метаданных&#41;</span><span class="sxs-lookup"><span data-stu-id="b06a8-140">Add Metadata &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/add-metadata-master-data-services.md)  
  
-   [<span data-ttu-id="b06a8-141">Назначение разрешения для объекта модели (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="b06a8-141">Assign Model Object Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="b06a8-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="b06a8-142">See Also</span></span>  
 [<span data-ttu-id="b06a8-143">Развертывание моделей (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="b06a8-143">Deploying Models &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/deploying-models-master-data-services.md)  
  
  
