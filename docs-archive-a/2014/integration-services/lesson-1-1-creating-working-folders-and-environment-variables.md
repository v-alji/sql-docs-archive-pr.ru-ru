---
title: Шаг 1. Создание рабочих папок и переменных среды | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 45091ba2-ea3d-4399-9814-489d812b42cc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 63308d406e230538e5ca8b90dbb55bb802759bd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664366"
---
# <a name="step-1-creating-working-folders-and-environment-variables"></a><span data-ttu-id="033f4-102">Шаг 1. Создание рабочих папок и переменных среды</span><span class="sxs-lookup"><span data-stu-id="033f4-102">Step 1: Creating Working Folders and Environment Variables</span></span>
  <span data-ttu-id="033f4-103">В этой задаче предстоит создать рабочую папку (C:\DeploymentTutorial) и новые системные переменные среды (`DataTransfer` и `LoadXMLData`), которые будут использоваться в последующих задачах учебника.</span><span class="sxs-lookup"><span data-stu-id="033f4-103">In this task, you will create the working folder (C:\DeploymentTutorial) and the new system environment variables (`DataTransfer` and `LoadXMLData`) that you will use in later tutorial tasks.</span></span>  
  
 <span data-ttu-id="033f4-104">Рабочая папка является корневой папкой диска C.</span><span class="sxs-lookup"><span data-stu-id="033f4-104">The working folder is at the root of the C drive.</span></span> <span data-ttu-id="033f4-105">Если необходимо, используйте другой диск или расположение.</span><span class="sxs-lookup"><span data-stu-id="033f4-105">If you must use a different drive or location, you can do that.</span></span> <span data-ttu-id="033f4-106">Однако необходимо обратить внимание на это расположение и использовать его в дальнейшем всегда, когда в учебнике встречается ссылка на рабочую папку DeploymentTutorial.</span><span class="sxs-lookup"><span data-stu-id="033f4-106">However, you need to note this location and then use it wherever the tutorial refers to the location of the DeploymentTutorial working folder.</span></span>  
  
 <span data-ttu-id="033f4-107">На следующем занятии пакеты, сохраненные в файловой системе, будут развернуты в таблицу sysssispackages базы данных[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] msdb.</span><span class="sxs-lookup"><span data-stu-id="033f4-107">In a later lesson, you will deploy packages that are saved to the file system to the sysssispackages table in the msdb[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="033f4-108">В идеальном случае предстоит разместить пакеты служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] на другом компьютере.</span><span class="sxs-lookup"><span data-stu-id="033f4-108">Ideally you will deploy the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages to a different computer.</span></span> <span data-ttu-id="033f4-109">Если это невозможно, можно все-таки многое изучить в этом учебнике, развертывая пакеты в экземпляре [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="033f4-109">If that is not possible, you can still learn a lot from doing this tutorial by deploying the packages to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that is on the local computer.</span></span> <span data-ttu-id="033f4-110">Переменные среды, используемые на локальном компьютере и компьютере назначения, имеют одни и те же имена, но в них хранятся разные значения.</span><span class="sxs-lookup"><span data-stu-id="033f4-110">The environment variables that are used on the local and destination computers have the same variable names, but different values are stored in the variables.</span></span> <span data-ttu-id="033f4-111">Например, на локальном компьютере значение переменной среды `DataTransfer` ссылается на папку C:\DeploymentTutorial, в то время как на целевом компьютере переменная среды `DataTransfer` ссылается на папку C:\DeploymentTutorialInstall.</span><span class="sxs-lookup"><span data-stu-id="033f4-111">For example, on the local computer, the value of the environment variable `DataTransfer` references the C:\DeploymentTutorial folder, whereas on the target computer the environment variable `DataTransfer` references the C:\DeploymentTutorialInstall folder.</span></span>  
  
 <span data-ttu-id="033f4-112">Если планируется разместить пакеты на локальном компьютере, то необходимо создать только один набор переменных среды, однако придется назначить переменным окружения соответствующие значения, перед тем как производить локальное размещение.</span><span class="sxs-lookup"><span data-stu-id="033f4-112">If you plan to deploy to the local computer, you need to create only one set of environment variables; however, you will need to update the value of the environment variables to an appropriate value before you do the local deployment.</span></span>  
  
 <span data-ttu-id="033f4-113">Если пакеты планируется разместить на другом компьютере, то необходимо создать два набора переменных сред: один набор для локального компьютера, а другой — для целевого компьютера.</span><span class="sxs-lookup"><span data-stu-id="033f4-113">If you plan to deploy the packages to a different computer, you must create two sets of environment variables: one set for the local computer, and one set for the destination computer.</span></span> <span data-ttu-id="033f4-114">Пока можно создать только переменные для компьютера источника, а переменные для целевого компьютера можно создать потом, но на целевом компьютере, прежде чем пакеты будут установлены на него, должны быть доступны как переменные среды, так и папка.</span><span class="sxs-lookup"><span data-stu-id="033f4-114">You can create only the variables for the source computer now, and create the variables for the destination computer later, but you must have both the folder and environment variables available on the destination computer before you can install the packages on that computer.</span></span>  
  
### <a name="to-create-the-local-working-folder"></a><span data-ttu-id="033f4-115">Создание локальной рабочей папки</span><span class="sxs-lookup"><span data-stu-id="033f4-115">To create the local working folder</span></span>  
  
1.  <span data-ttu-id="033f4-116">Щелкните правой кнопкой мыши меню «Пуск» и выберите «Проводник».</span><span class="sxs-lookup"><span data-stu-id="033f4-116">Right-click the Start menu, and click Explore.</span></span>  
  
2.  <span data-ttu-id="033f4-117">Щелкните **Локальный диск (С:)** .</span><span class="sxs-lookup"><span data-stu-id="033f4-117">Click **Local Disk (C:)**.</span></span>  
  
3.  <span data-ttu-id="033f4-118">В меню **Файл** наведите указатель на пункт **Создать**, а затем выберите пункт **Папка**.</span><span class="sxs-lookup"><span data-stu-id="033f4-118">On the **File** menu, point to **New**, and then click **Folder**.</span></span>  
  
4.  <span data-ttu-id="033f4-119">Переименуйте новую папку в `DeploymentTutorial` .</span><span class="sxs-lookup"><span data-stu-id="033f4-119">Rename New Folder to `DeploymentTutorial`.</span></span>  
  
### <a name="to-create-local-environment-variables"></a><span data-ttu-id="033f4-120">Создание локальных переменных среды</span><span class="sxs-lookup"><span data-stu-id="033f4-120">To create local environment variables</span></span>  
  
1.  <span data-ttu-id="033f4-121">В меню **Пуск** выберите пункт **Панель управления**.</span><span class="sxs-lookup"><span data-stu-id="033f4-121">On the **Start** menu, click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="033f4-122">На панели управления дважды щелкните значок **Система**.</span><span class="sxs-lookup"><span data-stu-id="033f4-122">In Control Panel, double-click **System**.</span></span>  
  
3.  <span data-ttu-id="033f4-123">В диалоговом окне **Свойства системы** выберите вкладку **Дополнительно** , затем нажмите кнопку **Переменные среды**.</span><span class="sxs-lookup"><span data-stu-id="033f4-123">In the **System Properties** dialog box, click the **Advanced** tab, and then click **Environment Variables**.</span></span>  
  
4.  <span data-ttu-id="033f4-124">В диалоговом окне **Переменные среды** в области **Системные переменные** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="033f4-124">In the **Environment Variables** dialog box, in the **System variables** frame, click **New**.</span></span>  
  
5.  <span data-ttu-id="033f4-125">В диалоговом окне **Новая системная переменная** введите `DataTransfer` в поле **имя переменной** и `C:\DeploymentTutorial\datatransferconfig.dtsconfig` в поле **значение переменной** .</span><span class="sxs-lookup"><span data-stu-id="033f4-125">In the **New System Variable** dialog box, type `DataTransfer` in the **Variable name** box, and `C:\DeploymentTutorial\datatransferconfig.dtsconfig` in the **Variable value** box.</span></span>  
  
6.  <span data-ttu-id="033f4-126">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="033f4-126">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="033f4-127">Снова нажмите кнопку **создать** , введите `LoadXMLData` в поле **имя переменной** и `C:\DeploymentTutorial\loadxmldataconfig.dtsconfig` в поле **значение переменной** .</span><span class="sxs-lookup"><span data-stu-id="033f4-127">Click **New** again, and type `LoadXMLData` in the **Variable name** box, and `C:\DeploymentTutorial\loadxmldataconfig.dtsconfig` in the **Variable value** box.</span></span>  
  
8.  <span data-ttu-id="033f4-128">Нажмите кнопку **ОК** для выхода из диалогового окна **Переменные среды** .</span><span class="sxs-lookup"><span data-stu-id="033f4-128">Click **OK** to exit the **Environment Variables** dialog box.</span></span>  
  
9. <span data-ttu-id="033f4-129">Нажмите кнопку **ОК** для выхода из диалогового окна **Свойства системы** .</span><span class="sxs-lookup"><span data-stu-id="033f4-129">Click **OK** to exit the **System Properties** dialog box.\</span></span>  
  
10. <span data-ttu-id="033f4-130">При необходимости перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="033f4-130">Optionally, restart your computer.</span></span> <span data-ttu-id="033f4-131">Если не перезагрузить компьютер, то имя новой переменной не отобразится в мастере настройки пакета, но переменную можно будет использовать.</span><span class="sxs-lookup"><span data-stu-id="033f4-131">If you do not restart the computer, the name of the new variable will not be displayed in the Package Configuration Wizard, but you can still use it.</span></span>  
  
### <a name="to-create-destination-environment-variables"></a><span data-ttu-id="033f4-132">Создание целевых переменных среды</span><span class="sxs-lookup"><span data-stu-id="033f4-132">To create destination environment variables</span></span>  
  
1.  <span data-ttu-id="033f4-133">В меню **Пуск** выберите пункт **Панель управления**.</span><span class="sxs-lookup"><span data-stu-id="033f4-133">On the **Start** menu, click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="033f4-134">На панели управления дважды щелкните значок **Система**.</span><span class="sxs-lookup"><span data-stu-id="033f4-134">In Control Panel, double-click **System**.</span></span>  
  
3.  <span data-ttu-id="033f4-135">В диалоговом окне **Свойства системы** выберите вкладку **Дополнительно** , затем нажмите кнопку **Переменные среды**.</span><span class="sxs-lookup"><span data-stu-id="033f4-135">In the **System Properties** dialog box, click the **Advanced** tab, and then click **Environment Variables**.</span></span>  
  
4.  <span data-ttu-id="033f4-136">В диалоговом окне **Переменные среды** в области **Системные переменные** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="033f4-136">In the **Environment Variables** dialog box, in **System variables** frame, click **New**.</span></span>  
  
5.  <span data-ttu-id="033f4-137">В диалоговом окне **новые системные переменные** введите `DataTransfer` в поле **имя переменной** и `C:\DeploymentTutorialInstall\datatransferconfig.dtsconfig` в поле **значение переменной** .</span><span class="sxs-lookup"><span data-stu-id="033f4-137">In the **New System Variables** dialog box, type `DataTransfer` in the **Variable name** box, and `C:\DeploymentTutorialInstall\datatransferconfig.dtsconfig` in the **Variable value** box.</span></span>  
  
6.  <span data-ttu-id="033f4-138">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="033f4-138">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="033f4-139">Снова нажмите кнопку **создать** , введите `LoadXMLData` в поле **имя переменной** и `C:\DeploymentTutorialInstall\loadxmldataconfig.dtsconfig` в поле **значение переменной** .</span><span class="sxs-lookup"><span data-stu-id="033f4-139">Click **New** again, and type `LoadXMLData` in the **Variable name** box, and `C:\DeploymentTutorialInstall\loadxmldataconfig.dtsconfig` in the **Variable value** box.</span></span>  
  
8.  <span data-ttu-id="033f4-140">Нажмите кнопку **ОК** для выхода из диалогового окна **Переменные среды** .</span><span class="sxs-lookup"><span data-stu-id="033f4-140">Click **OK** to exit the **Environment Variables** dialog box.</span></span>  
  
9. <span data-ttu-id="033f4-141">Нажмите кнопку **ОК** для выхода из диалогового окна **Свойства системы** .</span><span class="sxs-lookup"><span data-stu-id="033f4-141">Click **OK** to exit the **System Properties** dialog box.\</span></span>  
  
10. <span data-ttu-id="033f4-142">При необходимости перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="033f4-142">Optionally, restart your computer.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="033f4-143">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="033f4-143">Next Task in Lesson</span></span>  
 [<span data-ttu-id="033f4-144">Шаг 2. Создание проекта развертывания</span><span class="sxs-lookup"><span data-stu-id="033f4-144">Step 2: Creating the Deployment Project</span></span>](../integration-services/lesson-1-2-creating-the-deployment-project.md)  
  
<span data-ttu-id="033f4-145">![Значок Integration Services (маленький)](media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="033f4-145">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="033f4-146">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="033f4-146">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="033f4-147">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="033f4-147">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="033f4-148">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="033f4-148">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
