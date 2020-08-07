---
title: Развертывание пакетов с помощью программы развертывания | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- packages [Integration Services], installing
- installing packages
- dependencies [Integration Services]
- deploying packages [Integration Services], installing
ms.assetid: eaf4b56e-2023-4d17-971c-703031da758c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a09ad307dc0215fca679cfb1ef5a37031f951caf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734390"
---
# <a name="deploy-packages-by-using-the-deployment-utility"></a><span data-ttu-id="aff52-102">Развертывание пакетов с помощью программы развертывания</span><span class="sxs-lookup"><span data-stu-id="aff52-102">Deploy Packages by Using the Deployment Utility</span></span>
  <span data-ttu-id="aff52-103">Если сборка программы развертывания, предназначенной для установки пакетов из проекта служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , выполнена на компьютере, отличном от того, на котором находится сам проект, прежде всего необходимо скопировать папку развертывания на целевой компьютер.</span><span class="sxs-lookup"><span data-stu-id="aff52-103">When you have built a deployment utility to install packages from an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project on a different computer than the one on which the deployment utility was built, you must first copy the deployment folder to the destination computer.</span></span>  
  
 <span data-ttu-id="aff52-104">Путь к папке развертывания указывается в свойстве DeploymentOutputPath того проекта служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , для которого была собрана данная программа развертывания.</span><span class="sxs-lookup"><span data-stu-id="aff52-104">The path of the deployment folder is specified in the DeploymentOutputPath property of the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project for which you created the deployment utility.</span></span> <span data-ttu-id="aff52-105">По умолчанию папкой развертывания является папка bin\Deployment относительно проекта служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="aff52-105">The default path is bin\Deployment, relative to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span> <span data-ttu-id="aff52-106">Дополнительные сведения см. в статье [Create a Deployment Utility](../../2014/integration-services/create-a-deployment-utility.md).</span><span class="sxs-lookup"><span data-stu-id="aff52-106">For more information, see [Create a Deployment Utility](../../2014/integration-services/create-a-deployment-utility.md).</span></span>  
  
 <span data-ttu-id="aff52-107">Для установки пакетов используется мастер установки пакетов.</span><span class="sxs-lookup"><span data-stu-id="aff52-107">You use the Package Installation Wizard to install the packages.</span></span> <span data-ttu-id="aff52-108">Чтобы запустить мастер, дважды щелкните файл программы развертывания после копирования папки развертывания на сервер.</span><span class="sxs-lookup"><span data-stu-id="aff52-108">To launch the wizard, double-click the deployment utility file after you have copied the deployment folder to the server.</span></span> <span data-ttu-id="aff52-109">Этот файл называется \<project name>.SSISDeploymentManifest и находится в папке развертывания на конечном компьютере.</span><span class="sxs-lookup"><span data-stu-id="aff52-109">This file is named \<project name>.SSISDeploymentManifest, and can be found in the deployment folder on the destination computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aff52-110">В зависимости от версии развертываемого пакета, параллельная установка разных версий [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] может вызвать ошибку.</span><span class="sxs-lookup"><span data-stu-id="aff52-110">Depending on the version of the package that you are deploying, you might encounter an error if you have different versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] installed side-by-side.</span></span> <span data-ttu-id="aff52-111">Эта ошибка может возникнуть из-за того, что расширение имени файла SSISDeploymentManifest одинаково для всех версий [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aff52-111">This error can occur because the .SSISDeploymentManifest file name extension is the same for all versions of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="aff52-112">Если дважды щелкнуть имя файла, вызывается установщик (dtsinstall.exe) последней установленной версии служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], которая может отличаться от версии файла программы развертывания.</span><span class="sxs-lookup"><span data-stu-id="aff52-112">Double-clicking the file calls the installer (dtsinstall.exe) for the most recently installed version of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], which might not be the same version as the deployment utility file.</span></span> <span data-ttu-id="aff52-113">Чтобы решить эту проблему, запустите нужную версию dtsinstall.exe из командной строки и укажите путь к файлу программы развертывания.</span><span class="sxs-lookup"><span data-stu-id="aff52-113">To work around this problem, run the correct version of dtsinstall.exe from the command line, and provide the path of the deployment utility file.</span></span>  
  
 <span data-ttu-id="aff52-114">Мастер установки пакета проведет по всем шагам установки пакетов в файловую систему или в [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aff52-114">The Package Installation Wizard guides you through the steps to install packages to the file system or to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="aff52-115">Установку можно настроить следующим образом:</span><span class="sxs-lookup"><span data-stu-id="aff52-115">You can configure the installation in the following ways:</span></span>  
  
-   <span data-ttu-id="aff52-116">выбрать тип расположения и само расположение для установки пакетов;</span><span class="sxs-lookup"><span data-stu-id="aff52-116">Choosing the location type and location to install the packages.</span></span>  
  
-   <span data-ttu-id="aff52-117">выбрать расположение для установки зависимостей пакетов;</span><span class="sxs-lookup"><span data-stu-id="aff52-117">Choosing location to install package dependencies.</span></span>  
  
-   <span data-ttu-id="aff52-118">проверить пакеты после их установки на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="aff52-118">Validating the packages after they are installed on the target server.</span></span>  
  
 <span data-ttu-id="aff52-119">Файловые зависимости для пакетов всегда устанавливаются в файловую систему.</span><span class="sxs-lookup"><span data-stu-id="aff52-119">The file-based dependencies for packages are always installed to the file system.</span></span> <span data-ttu-id="aff52-120">При установке пакета в файловую систему эти зависимости устанавливаются в ту же папку, которая была указана для данного пакета.</span><span class="sxs-lookup"><span data-stu-id="aff52-120">If you install a package to the file system, the dependencies are installed in the same folder as the one that you specify for the package.</span></span> <span data-ttu-id="aff52-121">При установке пакета в [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]можно указать папку для хранения файловых зависимостей.</span><span class="sxs-lookup"><span data-stu-id="aff52-121">If you install a package to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], you can specify the folder in which to store the file-based dependencies.</span></span>  
  
 <span data-ttu-id="aff52-122">Если данный пакет содержит конфигурации, которые нужно будет изменить на целевом компьютере, значения соответствующих свойств можно изменить в этом мастере.</span><span class="sxs-lookup"><span data-stu-id="aff52-122">If the package includes configurations that you want to modify for use on the destination computer, you can update the values of the properties by using the wizard.</span></span>  
  
 <span data-ttu-id="aff52-123">Помимо установки пакетов с помощью мастера установки пакета их можно копировать и перемещать с помощью программы командной строки **dtutil** .</span><span class="sxs-lookup"><span data-stu-id="aff52-123">In addition to installing packages by using the Package Installation Wizard, you can copy and move packages by using the **dtutil** command prompt utility.</span></span> <span data-ttu-id="aff52-124">Дополнительные сведения см. в статье [dtutil Utility](dtutil-utility.md).</span><span class="sxs-lookup"><span data-stu-id="aff52-124">For more information, see [dtutil Utility](dtutil-utility.md).</span></span>  
  
### <a name="to-deploy-packages-to-an-instance-of-sql-server"></a><span data-ttu-id="aff52-125">Развертывание пакетов в экземпляре SQL Server</span><span class="sxs-lookup"><span data-stu-id="aff52-125">To deploy packages to an instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="aff52-126">Откройте папку развертывания на целевом компьютере.</span><span class="sxs-lookup"><span data-stu-id="aff52-126">Open the deployment folder on the target computer.</span></span>  
  
2.  <span data-ttu-id="aff52-127">Дважды щелкните файл манифеста, \<project name>.SSISDeploymentManifest, чтобы запустить мастер установки пакета.</span><span class="sxs-lookup"><span data-stu-id="aff52-127">Double-click the manifest file, \<project name>.SSISDeploymentManifest, to start the Package Installation Wizard.</span></span>  
  
3.  <span data-ttu-id="aff52-128">На странице **Установка пакетов служб SSIS** выберите параметр **Установить на SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="aff52-128">On the **Deploy SSIS Packages** page, select the **SQL Server deployment** option.</span></span>  
  
4.  <span data-ttu-id="aff52-129">Можно также установить флажок **Проверить пакеты после установки** , чтобы проверить правильность пакетов после их установки на целевой сервер.</span><span class="sxs-lookup"><span data-stu-id="aff52-129">Optionally, select **Validate packages after installation** to validate packages after they are installed on the target server.</span></span>  
  
5.  <span data-ttu-id="aff52-130">На странице **Выбор целевого сервера SQL Server** укажите экземпляр [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , куда будут установлены пакеты, и выберите режим проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="aff52-130">On the **Specify Target SQL Server** page, specify the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to install the packages to and select an authentication mode.</span></span> <span data-ttu-id="aff52-131">Если выбрать проверку подлинности [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , необходимо будет ввести имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="aff52-131">If you select [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, you must provide a user name and a password.</span></span>  
  
6.  <span data-ttu-id="aff52-132">На странице **Выбор папки для установки** укажите папку в файловой системе, куда будут установлены зависимости пакета.</span><span class="sxs-lookup"><span data-stu-id="aff52-132">On the **Select Installation Folder** page, specify the folder in the file system for the package dependencies that will be installed.</span></span>  
  
7.  <span data-ttu-id="aff52-133">Если пакет содержит конфигурации, можно изменить его, обновляя значения в списке **Значение** на странице настройки пакетов.</span><span class="sxs-lookup"><span data-stu-id="aff52-133">If the package includes configurations, you can edit configurations by updating values in the **Value** list on the Configure Packages page.</span></span>  
  
8.  <span data-ttu-id="aff52-134">Если выбрана функция проверки пакетов после установки, посмотрите результаты проверки развернутых пакетов.</span><span class="sxs-lookup"><span data-stu-id="aff52-134">If you elected to validate packages after installation, view the validation results of the deployed packages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aff52-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="aff52-135">See Also</span></span>  
 [<span data-ttu-id="aff52-136">Развертывание пакетов &#40;&#41;SSIS</span><span class="sxs-lookup"><span data-stu-id="aff52-136">Package Deployment &#40;SSIS&#41;</span></span>](packages/legacy-package-deployment-ssis.md)  
  
  
