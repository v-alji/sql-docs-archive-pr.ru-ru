---
title: Развертывание пакета развертывания модели при помощи MDSModelDeploy | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: fb2a4df4-5e0d-4b34-818f-383dbde1b15c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c23dcc592c2de34fa87703c8ba58d949dfec455c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666100"
---
# <a name="deploy-a-model-deployment-package-by-using-mdsmodeldeploy"></a><span data-ttu-id="469b1-102">Развертывание пакета развертывания модели при помощи MDSModelDeploy</span><span class="sxs-lookup"><span data-stu-id="469b1-102">Deploy a Model Deployment Package by Using MDSModelDeploy</span></span>
  <span data-ttu-id="469b1-103">В [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]средство MDSModelDeploy используется для развертывания пакетов, содержащих:</span><span class="sxs-lookup"><span data-stu-id="469b1-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], use the MDSModelDeploy tool to deploy a package that contains either:</span></span>  
  
-   <span data-ttu-id="469b1-104">только объекты модели;</span><span class="sxs-lookup"><span data-stu-id="469b1-104">Model objects only.</span></span>  
  
-   <span data-ttu-id="469b1-105">объекты модели и данные.</span><span class="sxs-lookup"><span data-stu-id="469b1-105">Model objects and data.</span></span>  
  
 <span data-ttu-id="469b1-106">Если необходимо развернуть пакет, содержащий только объекты модели, можно воспользоваться мастером развертывания моделей в веб-приложении [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="469b1-106">If you want to deploy a package that contains model objects only, you can use the model deployment wizard in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application instead.</span></span> <span data-ttu-id="469b1-107">Дополнительные сведения см. в статье [Создание пакета развертывания модели с помощью мастера](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-the-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="469b1-107">For more information, see [Deploy a Model Deployment Package by Using the Wizard](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-the-wizard.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="469b1-108">Пакеты могут быть развернуты только в выпуске [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , в котором они были созданы.</span><span class="sxs-lookup"><span data-stu-id="469b1-108">Packages can be deployed to the edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] they were created in only.</span></span> <span data-ttu-id="469b1-109">Это означает, что пакеты, созданные в среде [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] , не могут быть развернуты в [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] или более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="469b1-109">This means that packages created in [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] cannot be deployed to [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] or higher.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="469b1-110">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="469b1-110">Prerequisites</span></span>  
 <span data-ttu-id="469b1-111">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="469b1-111">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="469b1-112">необходимо иметь разрешение на доступ к функциональной области **Администрирование системы** в целевой среде служб [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] ;</span><span class="sxs-lookup"><span data-stu-id="469b1-112">You must have permission to access the **System Administration** functional area in the target [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] environment.</span></span>  
  
-   <span data-ttu-id="469b1-113">должен существовать пакет развертывания модели.</span><span class="sxs-lookup"><span data-stu-id="469b1-113">A model deployment package must exist.</span></span> <span data-ttu-id="469b1-114">Дополнительные сведения см. в статье  [Создание пакета развертывания модели при помощи MDSModelDeploy](../../2014/master-data-services/create-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span><span class="sxs-lookup"><span data-stu-id="469b1-114">For more information, see  [Create a Model Deployment Package by Using MDSModelDeploy](../../2014/master-data-services/create-a-model-deployment-package-by-using-mdsmodeldeploy.md).</span></span>  
  
-   <span data-ttu-id="469b1-115">В среде, в которой выполняется развертывание модели, необходимо обладать правами администратора.</span><span class="sxs-lookup"><span data-stu-id="469b1-115">You must be an administrator in the environment where you are deploying the model.</span></span> <span data-ttu-id="469b1-116">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="469b1-116">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="469b1-117">При обновлении модели данных развертываемая версия не может быть **Заблокирована** или **Зафиксирована**.</span><span class="sxs-lookup"><span data-stu-id="469b1-117">If you are updating a model with data, the version you're deploying to cannot be **Locked** or **Committed**.</span></span>  
  
### <a name="to-deploy-a-model-deployment-package"></a><span data-ttu-id="469b1-118">Развертывание пакетов развертывания модели</span><span class="sxs-lookup"><span data-stu-id="469b1-118">To deploy a model deployment package</span></span>  
  
1.  <span data-ttu-id="469b1-119">Определите, производится развертывание новой модели, копии модели или обновление скопированной ранее модели.</span><span class="sxs-lookup"><span data-stu-id="469b1-119">Determine whether you are deploying a new model, a clone of a model, or updating a previously-cloned model.</span></span> <span data-ttu-id="469b1-120">Дополнительные сведения см. в разделе [Варианты развертывания модели (службы Master Data Services)](../../2014/master-data-services/model-deployment-options-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="469b1-120">For more information, see [Model Deployment Options &#40;Master Data Services&#41;](../../2014/master-data-services/model-deployment-options-master-data-services.md).</span></span>  
  
2.  <span data-ttu-id="469b1-121">Откройте командную строку и перейдите к MDSModelDeploy.exe.</span><span class="sxs-lookup"><span data-stu-id="469b1-121">Open a command prompt and navigate to MDSModelDeploy.exe.</span></span>  
  
    -   <span data-ttu-id="469b1-122">Если службы MDS установлены в расположении по умолчанию, это средство доступно на *диске*: \PROGRAM Files\Microsoft SQL Server\120\Master Data Services\Configuration\MDSModelDeploy.exe</span><span class="sxs-lookup"><span data-stu-id="469b1-122">If MDS is installed at the default location, the tool is available at *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\Configuration\MDSModelDeploy.exe</span></span>  
  
    -   <span data-ttu-id="469b1-123">Если службы MDS не установлены в местоположение по умолчанию, то найдите файл MDSModelDeploy.exe на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="469b1-123">If MDS is not installed at the default location, search the local computer for MDSModelDeploy.exe.</span></span>  
  
3.  <span data-ttu-id="469b1-124">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="469b1-124">Optional.</span></span> <span data-ttu-id="469b1-125">Просмотрите параметры и справку.</span><span class="sxs-lookup"><span data-stu-id="469b1-125">View options and help.</span></span>  
  
    -   <span data-ttu-id="469b1-126">Чтобы показать все доступные параметры, введите `MDSModelDeploy` и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="469b1-126">To display all available options, type `MDSModelDeploy` and press Enter.</span></span>  
  
    -   <span data-ttu-id="469b1-127">Чтобы вывести справку для параметра, введите следующую строку, где *OptionName* — имя параметра: `MDSModelDeploy help OptionName`.</span><span class="sxs-lookup"><span data-stu-id="469b1-127">To display help for an option, type the following, where *OptionName* is the name of the option: `MDSModelDeploy help OptionName`.</span></span>  
  
4.  <span data-ttu-id="469b1-128">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="469b1-128">Optional.</span></span> <span data-ttu-id="469b1-129">При наличии нескольких веб-приложений определите имя развертываемой службы, введя следующую команду, и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="469b1-129">If you have multiple web applications, determine the name of the service you will deploy to by typing this command and pressing Enter:</span></span>  
  
    ```  
    MDSModelDeploy listservices  
    ```  
  
     <span data-ttu-id="469b1-130">Возвращается список значений, например `MDS1, Default Web Site, MDS`.</span><span class="sxs-lookup"><span data-stu-id="469b1-130">A list of values is returned, for example `MDS1, Default Web Site, MDS`.</span></span> <span data-ttu-id="469b1-131">Первое значение в этом списке (в данном случае `MDS1`) необходимо для развертывания модели.</span><span class="sxs-lookup"><span data-stu-id="469b1-131">The first value in this list (in this case, `MDS1`) is needed to deploy the model.</span></span>  
  
5.  <span data-ttu-id="469b1-132">В зависимости от выполняемой задачи (создание модели, копирование модели или обновление модели) наберите в командной строке следующий текст и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="469b1-132">Depending on whether you are creating a model, cloning a model, or updating a model, at the command prompt, type the following and press Enter.</span></span>  
  
    -   <span data-ttu-id="469b1-133">Создание новой модели:</span><span class="sxs-lookup"><span data-stu-id="469b1-133">To create a new model:</span></span>  
  
        ```  
        MDSModelDeploy deploynew -package PackageName -model ModelName -service ServiceName  
        ```  
  
    -   <span data-ttu-id="469b1-134">Создание копии модели:</span><span class="sxs-lookup"><span data-stu-id="469b1-134">To create a clone of a model:</span></span>  
  
        ```  
        MDSModelDeploy deployclone -package PackageName  
        ```  
  
    -   <span data-ttu-id="469b1-135">Обновление существующей модели и ее данных:</span><span class="sxs-lookup"><span data-stu-id="469b1-135">To update an existing model and its data:</span></span>  
  
        ```  
        MDSModelDeploy deployupdate -package PackageName -version VersionName  
        ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="469b1-136">Если средство MDSModelDeploy используется для обновления существующей модели и ее данных и пакет не содержит сущность, атрибут или элемент, имеющиеся в целевой модели, MDSModelDeploy не удаляет из модели эту сущность, атрибут или элемент.</span><span class="sxs-lookup"><span data-stu-id="469b1-136">If you use the MDSModelDeploy tool to update an existing model and its data, and the package does not contain an entity, attribute, or member that exists in the destination model, MDSModelDeploy will not delete that entity, attribute, or member from the model.</span></span>  
  
     <span data-ttu-id="469b1-137">Здесь *PackageName* — имя файла пакета (PKG), *ModelName* — имя новой модели, *VersionName* — имя версии, а *ServiceName* — полученное на предыдущем шаге имя службы.</span><span class="sxs-lookup"><span data-stu-id="469b1-137">Where *PackageName* is the name of the package (.pkg) file, *ModelName* is the name of the new model, *VersionName* is the name of the version, and *ServiceName* is the name of the service that you returned in the previous step.</span></span> <span data-ttu-id="469b1-138">Убедитесь, что имена модели и версии в точности соответствуют заданным названиям с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="469b1-138">Ensure that the model and version names match the exact case-sensitive names.</span></span>  
  
6.  <span data-ttu-id="469b1-139">После успешного развертывания пакета отображается сообщение "Операция MDSModelDeploy успешно завершена".</span><span class="sxs-lookup"><span data-stu-id="469b1-139">When the package is successfully deployed, a message stating "MDSModelDeploy operation completed successfully" is displayed.</span></span>  
  
 <span data-ttu-id="469b1-140">**Примечания.**</span><span class="sxs-lookup"><span data-stu-id="469b1-140">**Notes:**</span></span>  
  
-   <span data-ttu-id="469b1-141">Если представление подписки в пакете имеет то же имя, что и представление подписки в существующей модели, это представление создается как *modelname. subscriptionviewname*.</span><span class="sxs-lookup"><span data-stu-id="469b1-141">If a subscription view in the package has the same name as a subscription view in an existing model, the view is created as *modelname.subscriptionviewname*.</span></span> <span data-ttu-id="469b1-142">Если это имя уже используется, то представление подписки не создается.</span><span class="sxs-lookup"><span data-stu-id="469b1-142">If this name is already in use, the subscription view is not created.</span></span>  
  
-   <span data-ttu-id="469b1-143">Процесс развертывания состоит из четырех шагов.</span><span class="sxs-lookup"><span data-stu-id="469b1-143">The deployment process has four steps:</span></span>  
  
    1.  <span data-ttu-id="469b1-144">Создаются объекты модели.</span><span class="sxs-lookup"><span data-stu-id="469b1-144">The model objects are created.</span></span>  
  
    2.  <span data-ttu-id="469b1-145">Создаются бизнес-правила.</span><span class="sxs-lookup"><span data-stu-id="469b1-145">Business rules are created.</span></span>  
  
    3.  <span data-ttu-id="469b1-146">Создаются представления подписки.</span><span class="sxs-lookup"><span data-stu-id="469b1-146">Subscription views are created.</span></span>  
  
    4.  <span data-ttu-id="469b1-147">Производится заполнение основных данных.</span><span class="sxs-lookup"><span data-stu-id="469b1-147">Master data is populated.</span></span>  
  
-   <span data-ttu-id="469b1-148">Если при создании новой или клонированной модели процесс на любом этапе завершается ошибкой, модель удаляется.</span><span class="sxs-lookup"><span data-stu-id="469b1-148">When creating a new or cloned model, if the process fails during any step, the model is deleted.</span></span>  
  
     <span data-ttu-id="469b1-149">При обновлении в случае неудачного завершения любого из первых трех шагов переход к следующему шагу не производится. Однако откат уже внесенных изменений также не выполняется.</span><span class="sxs-lookup"><span data-stu-id="469b1-149">When updating a model, if the process fails during the first three steps, it does not proceed; however, changes that are already made are not rolled back.</span></span> <span data-ttu-id="469b1-150">Если процесс развертывания завершается неудачей в шаге 4, обновляются те элементы, которые могут обновиться.</span><span class="sxs-lookup"><span data-stu-id="469b1-150">If the process fails in step 4, members that can be updated are updated.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="469b1-151">Next Steps</span><span class="sxs-lookup"><span data-stu-id="469b1-151">Next Steps</span></span>  
 <span data-ttu-id="469b1-152">Определенные пользователем метаданные, атрибуты файлов и разрешения для пользователей и групп не включаются в пакеты развертывания модели.</span><span class="sxs-lookup"><span data-stu-id="469b1-152">User-defined metadata, file attributes, and user and group permissions are not included in model deployment packages.</span></span> <span data-ttu-id="469b1-153">При развертывании модели их нужно обновить вручную.</span><span class="sxs-lookup"><span data-stu-id="469b1-153">After you deploy a model, you must update these manually.</span></span> <span data-ttu-id="469b1-154">Дополнительные сведения см. в разделе:</span><span class="sxs-lookup"><span data-stu-id="469b1-154">For more information, see:</span></span>  
  
-   [<span data-ttu-id="469b1-155">Добавление Master Data Services &#40;метаданных&#41;</span><span class="sxs-lookup"><span data-stu-id="469b1-155">Add Metadata &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/add-metadata-master-data-services.md)  
  
-   [<span data-ttu-id="469b1-156">Назначение разрешения для объекта модели (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="469b1-156">Assign Model Object Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/assign-model-object-permissions-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="469b1-157">См. также:</span><span class="sxs-lookup"><span data-stu-id="469b1-157">See Also</span></span>  
 [<span data-ttu-id="469b1-158">Развертывание моделей (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="469b1-158">Deploying Models &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/deploying-models-master-data-services.md)  
  
  
