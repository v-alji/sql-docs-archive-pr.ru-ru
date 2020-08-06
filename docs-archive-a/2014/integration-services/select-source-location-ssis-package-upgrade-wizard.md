---
title: Выбор исходного расположения (мастер обновления пакетов служб SSIS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.is.upgradewizard.selectsourcelocation.f1
ms.assetid: 429f146e-edb4-4401-a225-f2c8468971c5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e24eec77dc87a6215f9d686cf5af964cc244d68d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728457"
---
# <a name="select-source-location-ssis-package-upgrade-wizard"></a><span data-ttu-id="083ef-102">Выбор расположения источника (мастер обновления пакетов служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="083ef-102">Select Source Location (SSIS Package Upgrade Wizard)</span></span>
  <span data-ttu-id="083ef-103">Используйте страницу **Выбор исходного расположения** для задания местонахождения источника обновляемых пакетов.</span><span class="sxs-lookup"><span data-stu-id="083ef-103">Use the **Select Source Location** page to specify the source from which to upgrade packages.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="083ef-104">Эта страница доступна только при запуске мастера обновления пакетов служб [!INCLUDE[ssIS](../includes/ssis-md.md)] в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] или из командной строки.</span><span class="sxs-lookup"><span data-stu-id="083ef-104">This page is only available when you run the [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Upgrade Wizard from [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] or at the command prompt.</span></span>  
  
 <span data-ttu-id="083ef-105">**Запуск мастера обновления пакетов служб SSIS**</span><span class="sxs-lookup"><span data-stu-id="083ef-105">**To run the SSIS Package Upgrade Wizard**</span></span>  
  
-   [<span data-ttu-id="083ef-106">обновить пакеты служб Integration Services с помощью мастера обновления пакетов служб SSIS</span><span class="sxs-lookup"><span data-stu-id="083ef-106">Upgrade Integration Services Packages Using the SSIS Package Upgrade Wizard</span></span>](install-windows/upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard.md)  
  
## <a name="static-options"></a><span data-ttu-id="083ef-107">Статические параметры</span><span class="sxs-lookup"><span data-stu-id="083ef-107">Static Options</span></span>  
 <span data-ttu-id="083ef-108">**Источник пакета**</span><span class="sxs-lookup"><span data-stu-id="083ef-108">**Package source**</span></span>  
 <span data-ttu-id="083ef-109">Укажите место хранения, содержащее обновляемые пакеты.</span><span class="sxs-lookup"><span data-stu-id="083ef-109">Select the storage location that contains the packages to be upgraded.</span></span> <span data-ttu-id="083ef-110">Все возможные значения этого параметра приведены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="083ef-110">This option has the values listed in the following table.</span></span>  
  
|<span data-ttu-id="083ef-111">Значение</span><span class="sxs-lookup"><span data-stu-id="083ef-111">Value</span></span>|<span data-ttu-id="083ef-112">Описание</span><span class="sxs-lookup"><span data-stu-id="083ef-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="083ef-113">**Файловая система**</span><span class="sxs-lookup"><span data-stu-id="083ef-113">**File System**</span></span>|<span data-ttu-id="083ef-114">Указывает, что пакеты, подлежащие обновлению, находятся в папке на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="083ef-114">Indicates that the packages to be upgraded are in a folder on the local computer.</span></span><br /><br /> <span data-ttu-id="083ef-115">Чтобы мастер создавал резервные копии исходных пакетов перед их обновлением, исходные пакеты должны храниться в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="083ef-115">To have the wizard back up the original packages before upgrading those packages, the original packages must be stored in the file system.</span></span> <span data-ttu-id="083ef-116">Дополнительные сведения см. в разделе «Как».</span><span class="sxs-lookup"><span data-stu-id="083ef-116">For more information, see How To Topic.</span></span>|  
|<span data-ttu-id="083ef-117">**Хранилище пакетов служб SSIS**</span><span class="sxs-lookup"><span data-stu-id="083ef-117">**SSIS Package Store**</span></span>|<span data-ttu-id="083ef-118">Указывает, что обновляемые пакеты находятся в хранилище пакетов.</span><span class="sxs-lookup"><span data-stu-id="083ef-118">Indicates that the packages to be upgraded are in the package store.</span></span> <span data-ttu-id="083ef-119">Хранилище пакетов представляет собой набор папок в файловой системе, управляемый службой Windows служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="083ef-119">The package store consists of the set of file system folders that the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service manages.</span></span> <span data-ttu-id="083ef-120">Дополнительные сведения см. в разделе [Управление пакетами (службы SSIS)](service/package-management-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="083ef-120">For more information, see [Package Management &#40;SSIS Service&#41;](service/package-management-ssis-service.md).</span></span><br /><br /> <span data-ttu-id="083ef-121">При выборе этого значения отображается соответствующий динамический параметр **Источник пакета** .</span><span class="sxs-lookup"><span data-stu-id="083ef-121">Selecting this value displays the corresponding **Package source** dynamic options.</span></span>|  
|<span data-ttu-id="083ef-122">**Microsoft SQL Server**</span><span class="sxs-lookup"><span data-stu-id="083ef-122">**Microsoft SQL Server**</span></span>|<span data-ttu-id="083ef-123">Указывает, что подлежащие обновлению пакеты находятся в существующем экземпляре служб [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="083ef-123">Indicates the packages to be upgraded are from an existing instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="083ef-124">При выборе этого значения отображается соответствующий динамический параметр **Источник пакета** .</span><span class="sxs-lookup"><span data-stu-id="083ef-124">Selecting this value displays the corresponding **Package source** dynamic options.</span></span>|  
  
 <span data-ttu-id="083ef-125">**Папка**</span><span class="sxs-lookup"><span data-stu-id="083ef-125">**Folder**</span></span>  
 <span data-ttu-id="083ef-126">Введите имя папки, содержащей пакеты, которые необходимо обновить, или нажмите кнопку **Обзор** и укажите папку.</span><span class="sxs-lookup"><span data-stu-id="083ef-126">Type the name of a folder that contains the packages you want to upgrade or click **Browse** and locate the folder.</span></span>  
  
 <span data-ttu-id="083ef-127">**Обзор**</span><span class="sxs-lookup"><span data-stu-id="083ef-127">**Browse**</span></span>  
 <span data-ttu-id="083ef-128">Перейдите к папке, содержащей пакеты, которые необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="083ef-128">Browse to locate the folder that contains the packages you want to upgrade.</span></span>  
  
## <a name="package-source-dynamic-options"></a><span data-ttu-id="083ef-129">Динамические параметры источника пакетов</span><span class="sxs-lookup"><span data-stu-id="083ef-129">Package Source Dynamic Options</span></span>  
  
### <a name="package-source--ssis-package-store"></a><span data-ttu-id="083ef-130">Источник пакета = хранилище пакетов служб SSIS</span><span class="sxs-lookup"><span data-stu-id="083ef-130">Package source = SSIS Package Store</span></span>  
 <span data-ttu-id="083ef-131">**Server**</span><span class="sxs-lookup"><span data-stu-id="083ef-131">**Server**</span></span>  
 <span data-ttu-id="083ef-132">Введите имя сервера, на котором хранятся обновляемые пакеты, или выберите сервер из списка.</span><span class="sxs-lookup"><span data-stu-id="083ef-132">Type the name of the server that has the packages to be upgraded, or select this server in the list.</span></span>  
  
### <a name="package-source--microsoft-sql-server"></a><span data-ttu-id="083ef-133">Источник пакета = Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="083ef-133">Package source = Microsoft SQL Server</span></span>  
 <span data-ttu-id="083ef-134">**Server**</span><span class="sxs-lookup"><span data-stu-id="083ef-134">**Server**</span></span>  
 <span data-ttu-id="083ef-135">Введите имя сервера, на котором хранятся обновляемые пакеты, или выберите сервер из списка.</span><span class="sxs-lookup"><span data-stu-id="083ef-135">Type the name of the server that has the packages to be upgraded, or select this server from the list.</span></span>  
  
 <span data-ttu-id="083ef-136">**Использовать проверку подлинности Windows**</span><span class="sxs-lookup"><span data-stu-id="083ef-136">**Use Windows authentication**</span></span>  
 <span data-ttu-id="083ef-137">Выберите использование проверки подлинности Windows для подключения к серверу.</span><span class="sxs-lookup"><span data-stu-id="083ef-137">Select to use Windows Authentication to connect to the server.</span></span>  
  
 <span data-ttu-id="083ef-138">**Использовать проверку подлинности SQL Server**</span><span class="sxs-lookup"><span data-stu-id="083ef-138">**Use SQL Server authentication**</span></span>  
 <span data-ttu-id="083ef-139">Выберите использование проверки подлинности [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] для подключения к серверу.</span><span class="sxs-lookup"><span data-stu-id="083ef-139">Select to use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication to connect to the server.</span></span> <span data-ttu-id="083ef-140">Если используется проверка подлинности [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , необходимо ввести имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="083ef-140">If you use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, you must provide a user name and password.</span></span>  
  
 <span data-ttu-id="083ef-141">**User name**</span><span class="sxs-lookup"><span data-stu-id="083ef-141">**User name**</span></span>  
 <span data-ttu-id="083ef-142">Введите имя пользователя, которое будет использовано для проверки подлинности [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] при подключении к серверу.</span><span class="sxs-lookup"><span data-stu-id="083ef-142">Type the user name that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication will use to connect to the server.</span></span>  
  
 <span data-ttu-id="083ef-143">**Пароль**</span><span class="sxs-lookup"><span data-stu-id="083ef-143">**Password**</span></span>  
 <span data-ttu-id="083ef-144">Введите пароль, который будет использован для проверки подлинности [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] при подключении к серверу.</span><span class="sxs-lookup"><span data-stu-id="083ef-144">Type the password that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication will use to connect to the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="083ef-145">См. также:</span><span class="sxs-lookup"><span data-stu-id="083ef-145">See Also</span></span>  
 [<span data-ttu-id="083ef-146">Обновление пакетов служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="083ef-146">Upgrade Integration Services Packages</span></span>](install-windows/upgrade-integration-services-packages.md)  
  
  
