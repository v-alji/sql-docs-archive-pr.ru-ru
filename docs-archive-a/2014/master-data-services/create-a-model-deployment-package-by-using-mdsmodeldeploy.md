---
title: Создание пакета развертывания модели при помощи MDSModelDeploy | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: c2687e39-dc20-494f-a707-2aa29f4c329e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c546d6398234dd43103d0e6c75822377e11de61a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668970"
---
# <a name="create-a-model-deployment-package-by-using-mdsmodeldeploy"></a><span data-ttu-id="2b83d-102">Создание пакета развертывания модели при помощи MDSModelDeploy</span><span class="sxs-lookup"><span data-stu-id="2b83d-102">Create a Model Deployment Package by Using MDSModelDeploy</span></span>
  <span data-ttu-id="2b83d-103">В [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]для создания пакетов используется средство MDSModelDeploy.</span><span class="sxs-lookup"><span data-stu-id="2b83d-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], use the MDSModelDeploy tool to create a package.</span></span> <span data-ttu-id="2b83d-104">В зависимости от указанных команд, пакет может содержать:</span><span class="sxs-lookup"><span data-stu-id="2b83d-104">Depending on the commands you specify, the package can contain either:</span></span>  
  
-   <span data-ttu-id="2b83d-105">только объекты модели;</span><span class="sxs-lookup"><span data-stu-id="2b83d-105">Model objects only.</span></span>  
  
-   <span data-ttu-id="2b83d-106">объекты модели и данные.</span><span class="sxs-lookup"><span data-stu-id="2b83d-106">Model objects and data.</span></span>  
  
 <span data-ttu-id="2b83d-107">Если необходимо развернуть пакет, содержащий только объекты модели, можно воспользоваться мастером развертывания моделей в веб-приложении [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2b83d-107">If you want to deploy a package that contains model objects only, you can use the model deployment wizard in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application instead.</span></span> <span data-ttu-id="2b83d-108">Дополнительные сведения см. в разделе [Создание пакета развертывания модели с помощью мастера](../../2014/master-data-services/create-a-model-deployment-package-by-using-the-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="2b83d-108">For more information, see [Create a Model Deployment Package by Using the Wizard](../../2014/master-data-services/create-a-model-deployment-package-by-using-the-wizard.md).</span></span>  
> [!NOTE]  
> <span data-ttu-id="2b83d-109">Эта версия средства MDSModelDeploy не может использовать больше гигабайт (ГБ) памяти.</span><span class="sxs-lookup"><span data-stu-id="2b83d-109">This version of the MDSModelDeploy tool cannot use more than gigabytes (GB) of memory.</span></span> <span data-ttu-id="2b83d-110">При создании или развертывании больших моделей с помощью **объектов модели и параметров данных** может возникнуть ошибка "недостаточно памяти" или "поток слишком длинный".</span><span class="sxs-lookup"><span data-stu-id="2b83d-110">When you create or deploy large models by using **Model objects and data** option, you may experience "Out of Memory" or "Stream was too long" errors.</span></span> <span data-ttu-id="2b83d-111">Чтобы устранить эту проблему, используйте промежуточное развертывание MDS для развертывания данных. или обновите до версии MDS 2016 или более поздней, которая включает обновленную версию средства MDSModelDeploy.</span><span class="sxs-lookup"><span data-stu-id="2b83d-111">To resolve this issue, use MDS staging to deploy the data; or upgrade to MDS 2016 or a later version, which includes the updated version of the MDSModelDeploy tool.</span></span>
## <a name="prerequisites"></a><span data-ttu-id="2b83d-112">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="2b83d-112">Prerequisites</span></span>  
 <span data-ttu-id="2b83d-113">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="2b83d-113">To perform this procedure:</span></span>  
  
1.  <span data-ttu-id="2b83d-114">Для запуска средства MDSModelDeploy требуются следующие основные разрешения.</span><span class="sxs-lookup"><span data-stu-id="2b83d-114">The basic permissions required to run the MDSModelDeploy tool are the following:</span></span>  
  
    -   <span data-ttu-id="2b83d-115">Такие же разрешения Windows, как у диспетчера конфигурации MDS (администратор Windows)</span><span class="sxs-lookup"><span data-stu-id="2b83d-115">The same Windows permission as the MDS Configuration Manager (administrator of Windows)</span></span>  
  
    -   <span data-ttu-id="2b83d-116">Разрешение DBA на базу данных MDS.</span><span class="sxs-lookup"><span data-stu-id="2b83d-116">DBA permission on the MDS database.</span></span>  
  
2.  <span data-ttu-id="2b83d-117">Для создания пакета с помощью средства MDSModelDeploy требуются следующие основные разрешения.</span><span class="sxs-lookup"><span data-stu-id="2b83d-117">The permissions required to create the package using the MDSModelDeploy tool are the following:</span></span>  
  
    -   <span data-ttu-id="2b83d-118">Разрешение администратора модели MDS на модель данных.</span><span class="sxs-lookup"><span data-stu-id="2b83d-118">MDS model administrator permission on the data model.</span></span>  
  
    -   <span data-ttu-id="2b83d-119">Разрешение на управление интеграцией MDS.</span><span class="sxs-lookup"><span data-stu-id="2b83d-119">MDS Integration Management function permission.</span></span>  
  
3.  <span data-ttu-id="2b83d-120">Для развертывания модели с помощью средства MDSModelDeploy требуются следующие основные разрешения.</span><span class="sxs-lookup"><span data-stu-id="2b83d-120">The permissions required to deploy a model using the MDSModelDeploy tool are the following:</span></span>  
  
    -   <span data-ttu-id="2b83d-121">Разрешение для функции обозревателя MDS</span><span class="sxs-lookup"><span data-stu-id="2b83d-121">MDS Explorer function permission</span></span>  
  
    -   <span data-ttu-id="2b83d-122">Разрешение для функции управления интеграцией MDS</span><span class="sxs-lookup"><span data-stu-id="2b83d-122">MDS Integration Management function permission</span></span>  
  
    -   <span data-ttu-id="2b83d-123">Разрешение для функции администрирования системы MDS.</span><span class="sxs-lookup"><span data-stu-id="2b83d-123">MDS System Administration function permission.</span></span>  
  
4.  <span data-ttu-id="2b83d-124">Для перечисления моделей с помощью средства MDSModelDeploy требуются следующие основные разрешения.</span><span class="sxs-lookup"><span data-stu-id="2b83d-124">The permissions required to list models using the MDSModelDeploy tool are the following:</span></span>  
  
    -   <span data-ttu-id="2b83d-125">Разрешение для функции обозревателя MDS</span><span class="sxs-lookup"><span data-stu-id="2b83d-125">MDS Explorer function permission</span></span>  
  
    -   <span data-ttu-id="2b83d-126">Разрешение администратора модели MDS на модель данных с тем, чтобы видеть модель в списке.</span><span class="sxs-lookup"><span data-stu-id="2b83d-126">MDS model administrator permission on the data model on order to see the model in the list.</span></span>  
  
 <span data-ttu-id="2b83d-127">Для создания пакета модели модель должна существовать.</span><span class="sxs-lookup"><span data-stu-id="2b83d-127">A model must exist for you to create a package of.</span></span> <span data-ttu-id="2b83d-128">Дополнительные сведения см. в разделе [Создание модели (службы Master Data Services)](create-a-model-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="2b83d-128">For more information, see [Create a Model &#40;Master Data Services&#41;](create-a-model-master-data-services.md).</span></span>  
  
 <span data-ttu-id="2b83d-129">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="2b83d-129">For more information, see [Administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span></span>  
  
### <a name="to-create-a-model-deployment-package-by-using-mdsmodeldeploy"></a><span data-ttu-id="2b83d-130">Создание пакета развертывания модели с помощью MDSModelDeploy</span><span class="sxs-lookup"><span data-stu-id="2b83d-130">To create a model deployment package by using MDSModelDeploy</span></span>  
  
1.  <span data-ttu-id="2b83d-131">Откройте командную строку.</span><span class="sxs-lookup"><span data-stu-id="2b83d-131">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="2b83d-132">Перейдите к расположению файла MDSModelDeploy.exe.</span><span class="sxs-lookup"><span data-stu-id="2b83d-132">Navigate to the location of MDSModelDeploy.exe.</span></span>  
  
    -   <span data-ttu-id="2b83d-133">Если службы MDS установлены в расположение по умолчанию, файл находится в папке *диск*: \PROGRAM Files\Microsoft SQL Server\120\Master Data Services\Configuration.</span><span class="sxs-lookup"><span data-stu-id="2b83d-133">If MDS was installed in the default location, the file is in *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\Configuration.</span></span>  
  
    -   <span data-ttu-id="2b83d-134">Если службы MDS установлены не в папку по умолчанию, найдите файл MDSModelDeploy.exe на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="2b83d-134">If MDS was not installed in the default location, search the local computer for MDSModelDeploy.exe.</span></span>  
  
3.  <span data-ttu-id="2b83d-135">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="2b83d-135">Optional.</span></span> <span data-ttu-id="2b83d-136">Просмотрите параметры и справку.</span><span class="sxs-lookup"><span data-stu-id="2b83d-136">View options and help.</span></span>  
  
    -   <span data-ttu-id="2b83d-137">Чтобы показать все доступные параметры, введите `MDSModelDeploy` и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="2b83d-137">To display all available options, type `MDSModelDeploy` and press Enter.</span></span>  
  
    -   <span data-ttu-id="2b83d-138">Чтобы вывести справку для параметра, введите следующую строку, где *OptionName* — имя параметра: `MDSModelDeploy help OptionName`.</span><span class="sxs-lookup"><span data-stu-id="2b83d-138">To display help for an option, type the following, where *OptionName* is the name of the option: `MDSModelDeploy help OptionName`.</span></span>  
  
4.  <span data-ttu-id="2b83d-139">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="2b83d-139">Optional.</span></span> <span data-ttu-id="2b83d-140">При наличии нескольких веб-приложений определите имя развертываемой службы, введя следующую команду, и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="2b83d-140">If you have multiple web applications, determine the name of the service you will deploy to by typing this command and pressing Enter:</span></span>  
  
    ```  
    MDSModelDeploy listservices  
    ```  
  
     <span data-ttu-id="2b83d-141">Возвращается список значений, например `MDS1, Default Web Site, MDS`.</span><span class="sxs-lookup"><span data-stu-id="2b83d-141">A list of values is returned, for example `MDS1, Default Web Site, MDS`.</span></span> <span data-ttu-id="2b83d-142">Первое значение в этом списке (в данном случае `MDS1`) необходимо для развертывания модели.</span><span class="sxs-lookup"><span data-stu-id="2b83d-142">The first value in this list (in this case, `MDS1`) is needed to deploy the model.</span></span>  
  
5.  <span data-ttu-id="2b83d-143">Чтобы создать пакет, содержащий объекты модели и данные, введите следующую строку, в которой *ModelName*, *VersionName*, *ServiceName*и *PackageName* — это имена модели, версии, службы и выходного PKG-файла соответственно:</span><span class="sxs-lookup"><span data-stu-id="2b83d-143">To create a package that contains model objects and data, type the following, where *ModelName*, *VersionName*, *ServiceName*,  and *PackageName* are the names of the model, version, service, and of the .pkg output file respectively:</span></span>  
  
    ```  
    MDSModelDeploy createpackage -model ModelName -version VersionName -service ServiceName -package PackageName -includedata  
    ```  
  
     <span data-ttu-id="2b83d-144">Если включать данные не требуется, не указывайте параметры `-version` и `-includedata` .</span><span class="sxs-lookup"><span data-stu-id="2b83d-144">If you do not want to include data, do not use the `-version` and `-includedata` switches.</span></span>  
  
6.  <span data-ttu-id="2b83d-145">Нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="2b83d-145">Press Enter.</span></span> <span data-ttu-id="2b83d-146">После успешного создания пакета отображается сообщение "Операция MDSModelDeploy успешно завершена".</span><span class="sxs-lookup"><span data-stu-id="2b83d-146">When the package is successfully created, a message stating "MDSModelDeploy operation completed successfully" is displayed.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="2b83d-147">Next Steps</span><span class="sxs-lookup"><span data-stu-id="2b83d-147">Next Steps</span></span>  
  
-   [<span data-ttu-id="2b83d-148">Развертывание пакета развертывания модели при помощи MDSModelDeploy</span><span class="sxs-lookup"><span data-stu-id="2b83d-148">Deploy a Model Deployment Package by Using MDSModelDeploy</span></span>](../../2014/master-data-services/deploy-a-model-deployment-package-by-using-mdsmodeldeploy.md)  
  
## <a name="see-also"></a><span data-ttu-id="2b83d-149">См. также:</span><span class="sxs-lookup"><span data-stu-id="2b83d-149">See Also</span></span>  
 <span data-ttu-id="2b83d-150">[Параметры развертывания модели &#40;Master Data Services&#41;](../../2014/master-data-services/model-deployment-options-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="2b83d-150">[Model Deployment Options &#40;Master Data Services&#41;](../../2014/master-data-services/model-deployment-options-master-data-services.md) </span></span>  
 [<span data-ttu-id="2b83d-151">Развертывание моделей (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="2b83d-151">Deploying Models &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/deploying-models-master-data-services.md)  
  
  
