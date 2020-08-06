---
title: Выбор параметров Управление пакетами (мастер обновления пакетов служб SSIS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.is.upgradewizard.selectpackagemgtoptions.f1
ms.assetid: 810fc020-51cd-43ed-9f35-af99b4f35947
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b5113ad5a1f6758a75742ca58aef04ce92168649
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668988"
---
# <a name="select-package-management-options-ssis-package-upgrade-wizard"></a><span data-ttu-id="d551b-102">Выбор параметров управления пакетами (мастер обновления пакетов служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="d551b-102">Select Package Management Options (SSIS Package Upgrade Wizard)</span></span>
  <span data-ttu-id="d551b-103">Страница **Выбор параметров управления пакетами** используется для выбора параметров обновления пакетов.</span><span class="sxs-lookup"><span data-stu-id="d551b-103">Use the **Select Package Management Options** page to specify options for upgrading packages.</span></span>  
  
 <span data-ttu-id="d551b-104">**Запуск мастера обновления пакетов служб SSIS**</span><span class="sxs-lookup"><span data-stu-id="d551b-104">**To run the SSIS Package Upgrade Wizard**</span></span>  
  
-   [<span data-ttu-id="d551b-105">обновить пакеты служб Integration Services с помощью мастера обновления пакетов служб SSIS</span><span class="sxs-lookup"><span data-stu-id="d551b-105">Upgrade Integration Services Packages Using the SSIS Package Upgrade Wizard</span></span>](install-windows/upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard.md)  
  
## <a name="options"></a><span data-ttu-id="d551b-106">Варианты</span><span class="sxs-lookup"><span data-stu-id="d551b-106">Options</span></span>  
 <span data-ttu-id="d551b-107">**Обновить строки соединения для использования новых имен поставщиков**</span><span class="sxs-lookup"><span data-stu-id="d551b-107">**Update connection strings to use new provider names**</span></span>  
 <span data-ttu-id="d551b-108">Обновите строки соединения, чтобы в них использовались имена для следующих поставщиков текущего выпуска служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d551b-108">Update the connection strings to use the names for the following providers for the current release of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="d551b-109">Поставщик OLE DB для служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d551b-109">OLE DB Provider for [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="d551b-110">Собственный клиент [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d551b-110">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Native Client</span></span>  
  
 <span data-ttu-id="d551b-111">Мастер обновления пакетов [!INCLUDE[ssIS](../includes/ssis-md.md)] обновляет только те строки подключения, которые хранятся в диспетчерах соединений.</span><span class="sxs-lookup"><span data-stu-id="d551b-111">The [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Upgrade Wizard updates only connection strings that are stored in connection managers.</span></span> <span data-ttu-id="d551b-112">Мастер не обновляет строки соединения, которые формируются динамически с помощью языка выражений служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] или программно в задаче «Скрипт».</span><span class="sxs-lookup"><span data-stu-id="d551b-112">The wizard does not update connection strings that are constructed dynamically by using the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] expression language, or by using code in a Script task.</span></span>  
  
 <span data-ttu-id="d551b-113">**Проверить обновленные пакеты**</span><span class="sxs-lookup"><span data-stu-id="d551b-113">**Validate upgrade packages**</span></span>  
 <span data-ttu-id="d551b-114">Проверьте обновленные пакеты и сохраните только пакеты, прошедшие проверку.</span><span class="sxs-lookup"><span data-stu-id="d551b-114">Validate the upgrade packages and save only those upgrade packages that pass validation.</span></span>  
  
 <span data-ttu-id="d551b-115">Если не указать этот параметр, мастер не будет проверять обновленные пакеты.</span><span class="sxs-lookup"><span data-stu-id="d551b-115">If you do not select this option, the wizard will not validate upgrade packages.</span></span> <span data-ttu-id="d551b-116">Он будет сохранять все обновленные пакеты, независимо от их правильности.</span><span class="sxs-lookup"><span data-stu-id="d551b-116">Therefore, the wizard will save all upgrade packages, regardless of whether the packages are valid or not.</span></span> <span data-ttu-id="d551b-117">Мастер сохраняет пакеты обновления в то же расположение, которое было указано на странице мастера **Выбор целевого расположения** .</span><span class="sxs-lookup"><span data-stu-id="d551b-117">The wizard saves upgrade packages to the destination that is specified on the **SelectDestination Location** page of the wizard.</span></span>  
  
 <span data-ttu-id="d551b-118">Проверка увеличивает время процесса обновления.</span><span class="sxs-lookup"><span data-stu-id="d551b-118">Validation adds time to the upgrade process.</span></span> <span data-ttu-id="d551b-119">Рекомендуется не выбирать этот параметр для больших пакетов, которые, по всей вероятности, обновятся успешно.</span><span class="sxs-lookup"><span data-stu-id="d551b-119">We recommend that you do not select this option for large packages that are likely to be upgraded successfully.</span></span>  
  
 <span data-ttu-id="d551b-120">**Создать новые идентификаторы пакетов**</span><span class="sxs-lookup"><span data-stu-id="d551b-120">**Create new package IDs**</span></span>  
 <span data-ttu-id="d551b-121">Создайте новые идентификаторы для обновленных пакетов.</span><span class="sxs-lookup"><span data-stu-id="d551b-121">Create new package IDs for the upgrade packages.</span></span>  
  
 <span data-ttu-id="d551b-122">**Продолжать процесс обновления в случае ошибки обновления пакетов**</span><span class="sxs-lookup"><span data-stu-id="d551b-122">**Continue upgrade process when a package upgrade fails**</span></span>  
 <span data-ttu-id="d551b-123">Укажите, что в случае невозможности обновления того или иного пакета мастер обновления пакетов [!INCLUDE[ssIS](../includes/ssis-md.md)] продолжит обновление оставшихся пакетов.</span><span class="sxs-lookup"><span data-stu-id="d551b-123">Specify that when a package cannot be upgraded, the [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Upgrade Wizard continues to upgrade the remaining packages.</span></span>  
  
 <span data-ttu-id="d551b-124">**Конфликты имен пакетов**</span><span class="sxs-lookup"><span data-stu-id="d551b-124">**Package name conflicts**</span></span>  
 <span data-ttu-id="d551b-125">Укажите, что мастер должен сделать с пакетами, имена которых совпадают.</span><span class="sxs-lookup"><span data-stu-id="d551b-125">Specify how the wizard should handle packages that have the same name.</span></span> <span data-ttu-id="d551b-126">Все возможные значения этого параметра приведены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="d551b-126">This option has the values listed in the following table.</span></span>  
  
 <span data-ttu-id="d551b-127">**Перезаписать существующие файлы пакетов**</span><span class="sxs-lookup"><span data-stu-id="d551b-127">**Overwrite existing package files**</span></span>  
 <span data-ttu-id="d551b-128">Заменяет существующий пакет обновленным пакетом с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="d551b-128">Replaces the existing package with the upgrade package of the same name.</span></span>  
  
 <span data-ttu-id="d551b-129">**Добавлять к именам обновленных пакетов числовые суффиксы**</span><span class="sxs-lookup"><span data-stu-id="d551b-129">**Add numeric suffixes to upgrade package names**</span></span>  
 <span data-ttu-id="d551b-130">Добавляет к именам обновленных пакетов числовые суффиксы.</span><span class="sxs-lookup"><span data-stu-id="d551b-130">Adds a numeric suffix to the name of the upgrade package.</span></span>  
  
 <span data-ttu-id="d551b-131">**Не обновлять пакеты**</span><span class="sxs-lookup"><span data-stu-id="d551b-131">**Do not upgrade packages**</span></span>  
 <span data-ttu-id="d551b-132">Прекращает обновление пакетов и выдает сообщение об ошибке при завершении работы мастера.</span><span class="sxs-lookup"><span data-stu-id="d551b-132">Stops the packages from being upgraded and displays an error when you complete the wizard.</span></span>  
  
 <span data-ttu-id="d551b-133">Эти параметры недоступны, если выбран параметр **Сохранить в исходное расположение** страницы мастера **Выбор целевого расположения** .</span><span class="sxs-lookup"><span data-stu-id="d551b-133">These options are not available when you select the **Save to source location** option on the **Select Destination Location** page of the wizard.</span></span>  
  
 <span data-ttu-id="d551b-134">**Игнорировать конфигурации**</span><span class="sxs-lookup"><span data-stu-id="d551b-134">**Ignore Configurations**</span></span>  
 <span data-ttu-id="d551b-135">Конфигурации пакетов не загружаются во время обновления пакетов.</span><span class="sxs-lookup"><span data-stu-id="d551b-135">Does not load package configurations during the package upgrade.</span></span> <span data-ttu-id="d551b-136">Выбор этого параметра позволяет сократить время, требуемое на обновление пакета.</span><span class="sxs-lookup"><span data-stu-id="d551b-136">Selecting this option reduces the time required to upgrade the package.</span></span>  
  
 <span data-ttu-id="d551b-137">**Создать резервную копию исходных пакетов**</span><span class="sxs-lookup"><span data-stu-id="d551b-137">**Backup original packages**</span></span>  
 <span data-ttu-id="d551b-138">Мастер будет создавать резервные копии исходных пакетов в папке **SSISBackupFolder** .</span><span class="sxs-lookup"><span data-stu-id="d551b-138">Have the wizard back up the original packages to an **SSISBackupFolder** folder.</span></span> <span data-ttu-id="d551b-139">Мастер создает папку **SSISBackupFolder** в папке, которая содержит исходные и обновленные пакеты.</span><span class="sxs-lookup"><span data-stu-id="d551b-139">The wizard creates the **SSISBackupFolder** folder as a subfolder to the folder that contains the original packages and the upgraded packages.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d551b-140">Этот параметр становится доступен только после указания, что исходные и обновленные пакеты должны храниться в файловой системе и в одной и той же папке.</span><span class="sxs-lookup"><span data-stu-id="d551b-140">This option is available only when you specify that the original packages and the upgraded packages are stored in the file system and in the same folder.</span></span>  
  
 <span data-ttu-id="d551b-141">Дополнительные сведения см. в разделе [Обновление пакетов служб Integration Services с помощью мастера обновления пакетов служб SSIS](install-windows/upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="d551b-141">For more information, see [Upgrade Integration Services Packages Using the SSIS Package Upgrade Wizard](install-windows/upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d551b-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="d551b-142">See Also</span></span>  
 [<span data-ttu-id="d551b-143">Обновление пакетов служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="d551b-143">Upgrade Integration Services Packages</span></span>](install-windows/upgrade-integration-services-packages.md)  
  
  
