---
title: Выбор целевого расположения (мастер обновления пакетов служб SSIS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.is.upgradewizard.selectdestinationlocation.f1
ms.assetid: 89274a71-0ffe-4889-84df-f5a7d78459ef
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9411157434c3dbb9fb033f7b63b5e6041fd8f75d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668990"
---
# <a name="select-destination-location-ssis-package-upgrade-wizard"></a><span data-ttu-id="a3d12-102">Выбор целевого расположения (мастер обновления пакетов служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="a3d12-102">Select Destination Location (SSIS Package Upgrade Wizard)</span></span>
  <span data-ttu-id="a3d12-103">Страница **Выбор целевого расположения** используется для указания назначения, в которое сохраняются обновленные пакеты.</span><span class="sxs-lookup"><span data-stu-id="a3d12-103">Use the **Select Destination Location** page to specify the destination to which to save the upgraded packages.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a3d12-104">Эта страница доступна только при запуске мастера обновления пакетов служб [!INCLUDE[ssIS](../includes/ssis-md.md)] в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] или из командной строки.</span><span class="sxs-lookup"><span data-stu-id="a3d12-104">This page is only available when you run the [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Upgrade Wizard from [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] or at the command prompt.</span></span>  
  
 <span data-ttu-id="a3d12-105">**Запуск мастера обновления пакетов служб SSIS**</span><span class="sxs-lookup"><span data-stu-id="a3d12-105">**To run the SSIS Package Upgrade Wizard**</span></span>  
  
-   [<span data-ttu-id="a3d12-106">обновить пакеты служб Integration Services с помощью мастера обновления пакетов служб SSIS</span><span class="sxs-lookup"><span data-stu-id="a3d12-106">Upgrade Integration Services Packages Using the SSIS Package Upgrade Wizard</span></span>](install-windows/upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard.md)  
  
## <a name="static-options"></a><span data-ttu-id="a3d12-107">Статические параметры</span><span class="sxs-lookup"><span data-stu-id="a3d12-107">Static Options</span></span>  
 <span data-ttu-id="a3d12-108">**Сохранить в исходное расположение**</span><span class="sxs-lookup"><span data-stu-id="a3d12-108">**Save to source location**</span></span>  
 <span data-ttu-id="a3d12-109">Сохраните обновленные пакеты в то же расположение, которое было указано на странице мастера **Выбор исходного расположения** .</span><span class="sxs-lookup"><span data-stu-id="a3d12-109">Save the upgraded packages to the same location as specified on the **Select Source Location** page of the wizard.</span></span>  
  
 <span data-ttu-id="a3d12-110">Если исходные пакеты хранились в файловой системе и нужно, чтобы мастер создал их резервные копии, выберите параметр **Сохранить в исходное расположение** .</span><span class="sxs-lookup"><span data-stu-id="a3d12-110">If the original packages are stored in the file system and you want the wizard to back up those packages, select the **Save to source location** option.</span></span> <span data-ttu-id="a3d12-111">Дополнительные сведения см. в разделе [Обновление пакетов служб Integration Services с помощью мастера обновления пакетов служб SSIS](install-windows/upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="a3d12-111">For more information, see [Upgrade Integration Services Packages Using the SSIS Package Upgrade Wizard](install-windows/upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard.md).</span></span>  
  
 <span data-ttu-id="a3d12-112">**Выбрать новое целевое расположение**</span><span class="sxs-lookup"><span data-stu-id="a3d12-112">**Select new destination location**</span></span>  
 <span data-ttu-id="a3d12-113">Сохраните обновленные пакеты в расположение, указанное на этой странице.</span><span class="sxs-lookup"><span data-stu-id="a3d12-113">Save the upgraded packages to the destination location that is specified on this page.</span></span>  
  
 <span data-ttu-id="a3d12-114">**Источник пакета**</span><span class="sxs-lookup"><span data-stu-id="a3d12-114">**Package source**</span></span>  
 <span data-ttu-id="a3d12-115">Позволяет указать, где будут храниться обновленные пакеты.</span><span class="sxs-lookup"><span data-stu-id="a3d12-115">Specify where the upgrade packages are to be stored.</span></span> <span data-ttu-id="a3d12-116">Все возможные значения этого параметра приведены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="a3d12-116">This option has the values listed in the following table.</span></span>  
  
|<span data-ttu-id="a3d12-117">Значение</span><span class="sxs-lookup"><span data-stu-id="a3d12-117">Value</span></span>|<span data-ttu-id="a3d12-118">Описание</span><span class="sxs-lookup"><span data-stu-id="a3d12-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a3d12-119">**Файловая система**</span><span class="sxs-lookup"><span data-stu-id="a3d12-119">**File System**</span></span>|<span data-ttu-id="a3d12-120">Указывает, что обновленные пакеты должны быть сохранены в папку на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a3d12-120">Indicates that the upgraded packages are to be saved to a folder on the local computer.</span></span>|  
|<span data-ttu-id="a3d12-121">**Хранилище пакетов служб SSIS**</span><span class="sxs-lookup"><span data-stu-id="a3d12-121">**SSIS Package Store**</span></span>|<span data-ttu-id="a3d12-122">Указывает, что обновленные пакеты должны быть сохранены в хранилище пакетов служб Integration Services.</span><span class="sxs-lookup"><span data-stu-id="a3d12-122">Indicates that the upgraded packages are to be saved to the Integration Services package store.</span></span> <span data-ttu-id="a3d12-123">Хранилище пакетов представляет собой набор папок в файловой системе, управляемый службами Integration Services.</span><span class="sxs-lookup"><span data-stu-id="a3d12-123">The package store consists of the set of file system folders that the Integration Services service manages.</span></span> <span data-ttu-id="a3d12-124">Дополнительные сведения см. в разделе [Управление пакетами (службы SSIS)](service/package-management-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="a3d12-124">For more information, see [Package Management &#40;SSIS Service&#41;](service/package-management-ssis-service.md).</span></span><br /><br /> <span data-ttu-id="a3d12-125">При выборе этого значения отображаются соответствующие динамические параметры **Источник пакета** .</span><span class="sxs-lookup"><span data-stu-id="a3d12-125">Selecting this value displays the corresponding **Package source** dynamics options.</span></span>|  
|<span data-ttu-id="a3d12-126">**Microsoft SQL Server**</span><span class="sxs-lookup"><span data-stu-id="a3d12-126">**Microsoft SQL Server**</span></span>|<span data-ttu-id="a3d12-127">Указывает, что обновленные пакеты должны быть сохранены в существующем экземпляре [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a3d12-127">Indicates that the upgraded packages are to be saved to an existing instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="a3d12-128">При выборе этого значения отображаются соответствующие динамические параметры **Источник пакета** .</span><span class="sxs-lookup"><span data-stu-id="a3d12-128">Selecting this value displays the corresponding dynamic **Package source** dynamic options.</span></span>|  
  
 <span data-ttu-id="a3d12-129">**Папка**</span><span class="sxs-lookup"><span data-stu-id="a3d12-129">**Folder**</span></span>  
 <span data-ttu-id="a3d12-130">Введите имя папки, чтобы сохранить обновленные пакеты, или нажмите кнопку **Обзор** и укажите папку.</span><span class="sxs-lookup"><span data-stu-id="a3d12-130">Type the name of a folder to which the upgraded packages will be saved, or click **Browse** and locate the folder.</span></span>  
  
 <span data-ttu-id="a3d12-131">**Обзор**</span><span class="sxs-lookup"><span data-stu-id="a3d12-131">**Browse**</span></span>  
 <span data-ttu-id="a3d12-132">Укажите папку, в которую будут сохранены обновленные пакеты.</span><span class="sxs-lookup"><span data-stu-id="a3d12-132">Browse to locate the folder to which the upgraded packages will be saved.</span></span>  
  
## <a name="package-source-dynamic-options"></a><span data-ttu-id="a3d12-133">Динамические параметры источника пакетов</span><span class="sxs-lookup"><span data-stu-id="a3d12-133">Package Source Dynamic Options</span></span>  
  
### <a name="package-source--ssis-package-store"></a><span data-ttu-id="a3d12-134">Источник пакета = хранилище пакетов служб SSIS</span><span class="sxs-lookup"><span data-stu-id="a3d12-134">Package source = SSIS Package Store</span></span>  
 <span data-ttu-id="a3d12-135">**Server**</span><span class="sxs-lookup"><span data-stu-id="a3d12-135">**Server**</span></span>  
 <span data-ttu-id="a3d12-136">Введите имя сервера, на котором будет сохранен обновленный пакет, или выберите сервер из списка.</span><span class="sxs-lookup"><span data-stu-id="a3d12-136">Type the name of the server to which the upgrade packages will be saved, or select a server in the list.</span></span>  
  
### <a name="package-source--microsoft-sql-server"></a><span data-ttu-id="a3d12-137">Источник пакета = Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="a3d12-137">Package source = Microsoft SQL Server</span></span>  
 <span data-ttu-id="a3d12-138">**Server**</span><span class="sxs-lookup"><span data-stu-id="a3d12-138">**Server**</span></span>  
 <span data-ttu-id="a3d12-139">Введите имя сервера, на котором будет сохранен обновленный пакет, или выберите сервер из списка.</span><span class="sxs-lookup"><span data-stu-id="a3d12-139">Type the name of the server to which the upgrade packages will be saved, or select this server in the list.</span></span>  
  
 <span data-ttu-id="a3d12-140">**Использовать проверку подлинности Windows**</span><span class="sxs-lookup"><span data-stu-id="a3d12-140">**Use Windows authentication**</span></span>  
 <span data-ttu-id="a3d12-141">Выберите использование проверки подлинности Windows для подключения к серверу.</span><span class="sxs-lookup"><span data-stu-id="a3d12-141">Select to use Windows Authentication to connect to the server.</span></span>  
  
 <span data-ttu-id="a3d12-142">**Использовать проверку подлинности SQL Server**</span><span class="sxs-lookup"><span data-stu-id="a3d12-142">**Use SQL Server authentication**</span></span>  
 <span data-ttu-id="a3d12-143">Выберите использование проверки подлинности [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] для подключения к серверу.</span><span class="sxs-lookup"><span data-stu-id="a3d12-143">Select to use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication to connect to the server.</span></span> <span data-ttu-id="a3d12-144">Если используется проверка подлинности [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , необходимо ввести имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="a3d12-144">If you use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, you must provide a user name and password.</span></span>  
  
 <span data-ttu-id="a3d12-145">**User name**</span><span class="sxs-lookup"><span data-stu-id="a3d12-145">**User name**</span></span>  
 <span data-ttu-id="a3d12-146">Введите имя пользователя, которое будет использовано, если при подключении к серверу применяется проверка подлинности [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a3d12-146">Type the user name to be used when using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication to connect to the server.</span></span>  
  
 <span data-ttu-id="a3d12-147">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="a3d12-147">**Password**</span></span>  
 <span data-ttu-id="a3d12-148">Введите пароль, который будет использован, если при подключении к серверу применяется проверка подлинности [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a3d12-148">Type the password to be used when using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication to connect to the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3d12-149">См. также:</span><span class="sxs-lookup"><span data-stu-id="a3d12-149">See Also</span></span>  
 [<span data-ttu-id="a3d12-150">Обновление пакетов служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="a3d12-150">Upgrade Integration Services Packages</span></span>](install-windows/upgrade-integration-services-packages.md)  
  
  
