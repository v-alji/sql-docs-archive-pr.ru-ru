---
title: Переименование экземпляра Analysis Services | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- instances of Analysis Services, renaming
- renaming instances of Analysis Services
- names [Analysis Services], renaming instances
- names [Analysis Services]
ms.assetid: 87494741-4a2e-4fed-8061-418fd1e111c3
author: minewiskan
ms.author: owend
ms.openlocfilehash: 763986d82dda7424f2187daf401424fd256ddd64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733250"
---
# <a name="rename-an-analysis-services-instance"></a><span data-ttu-id="9405a-102">Переименование экземпляра служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="9405a-102">Rename an Analysis Services Instance</span></span>
  <span data-ttu-id="9405a-103">Существующий экземпляр можно переименовать с [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] помощью диалогового окна « **Переименование экземпляра** ».</span><span class="sxs-lookup"><span data-stu-id="9405a-103">You can rename an existing instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] by using the **Rename Instance** dialog box.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9405a-104">При переименовании экземпляра средство переименования экземпляра служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] выполняется с расширенными правами доступа, обновляя имя службы Windows, учетные записи безопасности и записи реестра, связанные с этим экземпляром.</span><span class="sxs-lookup"><span data-stu-id="9405a-104">While renaming the instance, the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Instance Rename tool runs under elevated privileges, updating the Windows service name, security accounts, and registry entries associated with that instance.</span></span> <span data-ttu-id="9405a-105">Чтобы обеспечить выполнение этих действий, не забудьте перед запуском средства выполнить вход от имени администратора локальной системы.</span><span class="sxs-lookup"><span data-stu-id="9405a-105">To ensure that these actions are performed, be sure to run this tool as a local system administrator.</span></span>  
  
 <span data-ttu-id="9405a-106">Средство переименования экземпляра служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] не изменяет программную папку, созданную для исходного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="9405a-106">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Instance Rename tool does not modify the program folder that was created for the original instance.</span></span> <span data-ttu-id="9405a-107">Не изменяйте имя программной папки для соответствия переименованному экземпляру.</span><span class="sxs-lookup"><span data-stu-id="9405a-107">Do not modify the program folder name to match the instance you are renaming.</span></span> <span data-ttu-id="9405a-108">В случае изменения имени папки программа установки, возможно, не сможет выполнить исправление установки или ее удаление.</span><span class="sxs-lookup"><span data-stu-id="9405a-108">Changing a program folder name can prevent Setup from repairing or uninstalling the installation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9405a-109">Средство переименования экземпляра служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] не поддерживается в кластерной среде.</span><span class="sxs-lookup"><span data-stu-id="9405a-109">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Instance Rename tool is not supported for use in a cluster environment.</span></span>  
  
### <a name="to-rename-an-instance-of-analysis-services"></a><span data-ttu-id="9405a-110">Подключение к экземпляру служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="9405a-110">To rename an instance of Analysis Services</span></span>  
  
1.  <span data-ttu-id="9405a-111">Запустите средство **переименования экземпляра** **asinstancerename.exe**из папки C:\Program Files\Microsoft SQL Server\110\Tools\Binn\ManagementStudio.</span><span class="sxs-lookup"><span data-stu-id="9405a-111">Launch the **Instance Rename** tool, **asinstancerename.exe**, from C:\Program Files\Microsoft SQL Server\110\Tools\Binn\ManagementStudio.</span></span>  
  
2.  <span data-ttu-id="9405a-112">В диалоговом окне **Переименование экземпляра** в списке **Экземпляр для переименования** выберите экземпляр, который необходимо переименовать.</span><span class="sxs-lookup"><span data-stu-id="9405a-112">In the **Rename Instance** dialog box, in the **Instance to rename** list, select the instance that you want to rename.</span></span>  
  
3.  <span data-ttu-id="9405a-113">В поле **Новое имя экземпляра** введите новое имя для экземпляра.</span><span class="sxs-lookup"><span data-stu-id="9405a-113">In the **New instance name** box, enter the new name for the instance.</span></span>  
  
4.  <span data-ttu-id="9405a-114">Проверьте правильность имени пользователя и пароля и нажмите кнопку **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="9405a-114">Verify that the user name and password are correct, and then click **Rename**.</span></span>  
  
     <span data-ttu-id="9405a-115">Экземпляр служб Analysis Services будет остановлен и перезапущен в процессе изменения имени.</span><span class="sxs-lookup"><span data-stu-id="9405a-115">The Analysis Services instance will be stopped and restarted as part of the name change.</span></span>  
  
### <a name="post-rename-checklist"></a><span data-ttu-id="9405a-116">Контрольный список действий после переименования</span><span class="sxs-lookup"><span data-stu-id="9405a-116">Post-rename checklist</span></span>  
  
1.  <span data-ttu-id="9405a-117">Чтобы возобновить доступ к базам данных, выполняющимся на переименованном экземпляре, потребуется вручную изменить соединения с данными в Excel или в других клиентских приложениях.</span><span class="sxs-lookup"><span data-stu-id="9405a-117">To resume access to databases that are running on the renamed instance, you will need to manually update the data connections in Excel or other client applications.</span></span> <span data-ttu-id="9405a-118">Также следует проверить все стандартные соединения, например общие источники данных служб Reporting Services, файлы ODC Excel и файлы подключения семантических моделей бизнес-аналитики, которые могут ссылаться на переименованный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="9405a-118">Also check any predefined connections, such as Reporting Services shared data sources, Excel ODC files, or BI Semantic Model connection files that might reference the instance you just renamed.</span></span> <span data-ttu-id="9405a-119">Дополнительные сведения см. в разделе [Подключение к службам Analysis Services](connect-to-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="9405a-119">For more information, see [Connect to Analysis Services](connect-to-analysis-services.md).</span></span>  
  
2.  <span data-ttu-id="9405a-120">Обновите скрипты PowerShell или AMO, обычно используемые для резервного копирования, синхронизации и обработки баз данных.</span><span class="sxs-lookup"><span data-stu-id="9405a-120">Update PowerShell scripts or AMO scripts that you routinely use to backup, synchronize, or process databases.</span></span>  
  
3.  <span data-ttu-id="9405a-121">Обновите свойства проекта у проектов служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , с которыми вы работаете в среде [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9405a-121">Update project properties for [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] projects that you work with in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span> <span data-ttu-id="9405a-122">Для экземпляров сервера в табличном режиме необходимо обязательно обновить свойство «Workspace Server» (сервер рабочей области) в файле model.bim, а также свойство «Server» (сервер) проекта.</span><span class="sxs-lookup"><span data-stu-id="9405a-122">For tabular mode server instances, be sure to update the Workspace Server property on the model.bim file, as well as the Server property on the project.</span></span>  
  
4.  <span data-ttu-id="9405a-123">В зависимости от того, каким образом была задана учетная запись службы, может потребоваться обновить имена входа для баз данных или права на доступ к файлам, предоставляющий службе разрешение на доступ к данным (например, если учетная запись службы используется для обработки данных или доступа к связанным объектам на другом сервере).</span><span class="sxs-lookup"><span data-stu-id="9405a-123">Depending on how you specified the service account, you might need to update database logins or file permissions that grant data access rights to the service (for example, if you use the service account to process data or access linked objects on another server).</span></span>  
  
     <span data-ttu-id="9405a-124">Обновление имени входа для базы данных или разрешений на доступ к файлам обязательно, если для подготовки службы к работе использовалась виртуальная учетная запись.</span><span class="sxs-lookup"><span data-stu-id="9405a-124">Updating a database login or file permissions will be necessary if you used a virtual account to provision the service.</span></span> <span data-ttu-id="9405a-125">Виртуальные учетные записи основываются на именах служб, поэтому при переименовании экземпляра одновременно обновляется и имя виртуальной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="9405a-125">Virtual accounts are based on the instance name, so if you rename the instance, the virtual account is also updated at the same time.</span></span> <span data-ttu-id="9405a-126">В результате все ранее созданные для предыдущего экземпляра имена входа и разрешения становятся недействительными.</span><span class="sxs-lookup"><span data-stu-id="9405a-126">This means that any previous logins or permissions that you created for the previous instance are no longer valid.</span></span>  
  
     <span data-ttu-id="9405a-127">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="9405a-127">The following example provides an illustration.</span></span> <span data-ttu-id="9405a-128">Предположим, что вы установили сервер табличного режима как экземпляр с именем "табличный", используя виртуальную учетную запись по умолчанию, что приводит к следующей настройке:</span><span class="sxs-lookup"><span data-stu-id="9405a-128">Suppose you installed a tabular mode server as an instance named "Tabular" using the default virtual account, resulting in the following configuration:</span></span>  
  
    1.  <span data-ttu-id="9405a-129">Имя экземпляра = \<server> \табулар</span><span class="sxs-lookup"><span data-stu-id="9405a-129">Instance name = \<server>\TABULAR</span></span>  
  
    2.  <span data-ttu-id="9405a-130">Имя службы = MSOLAP$TABULAR</span><span class="sxs-lookup"><span data-stu-id="9405a-130">Service name = MSOLAP$TABULAR</span></span>  
  
    3.  <span data-ttu-id="9405a-131">Виртуальная учетная запись = NT Service\ MSOLAP$TABULAR</span><span class="sxs-lookup"><span data-stu-id="9405a-131">Virtual account = NT Service\ MSOLAP$TABULAR</span></span>  
  
     <span data-ttu-id="9405a-132">Теперь предположим, что вы переименуете экземпляр на «TAB2».</span><span class="sxs-lookup"><span data-stu-id="9405a-132">Now suppose you rename the instance to "TAB2".</span></span> <span data-ttu-id="9405a-133">В результате изменения имени конфигурация будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9405a-133">As a result of the name change, your configuration would now look like the following:</span></span>  
  
    1.  <span data-ttu-id="9405a-134">Имя экземпляра = \<server> \TAB2</span><span class="sxs-lookup"><span data-stu-id="9405a-134">Instance name = \<server>\TAB2</span></span>  
  
    2.  <span data-ttu-id="9405a-135">Имя службы = MSOLAP$TAB2</span><span class="sxs-lookup"><span data-stu-id="9405a-135">Service name = MSOLAP$TAB2</span></span>  
  
    3.  <span data-ttu-id="9405a-136">Виртуальная учетная запись = NT Service\ MSOLAP$TAB2</span><span class="sxs-lookup"><span data-stu-id="9405a-136">Virtual account = NT Service\ MSOLAP$TAB2</span></span>  
  
     <span data-ttu-id="9405a-137">Как видите, разрешения на доступ к базам данных и файлам, которые ранее были предоставлены службе NT Service \ MSOLAP $ ТАБЛИЧные, больше не действительны.</span><span class="sxs-lookup"><span data-stu-id="9405a-137">As you can see, database and file permissions that were previously granted to "NT Service\ MSOLAP$TABULAR" are no longer valid.</span></span> <span data-ttu-id="9405a-138">Чтобы обеспечить выполнение задач и операций, выполняемых службой, как и раньше, необходимо предоставить новые разрешения для базы данных и файлов в "NT Service \ MSOLAP $ TAB2".</span><span class="sxs-lookup"><span data-stu-id="9405a-138">To ensure that tasks and operations performed by the service run as before, you would now need to grant new database and file permissions to "NT Service\ MSOLAP$TAB2".</span></span>  
  
  
