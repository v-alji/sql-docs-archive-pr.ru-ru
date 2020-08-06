---
title: Обновление пакетов служб Integration Services с помощью мастера обновления пакетов служб SSIS | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services packages, upgrading
- upgrading Integration Services packages
ms.assetid: 9359275a-48f5-4d1e-8ae7-e797759e3ccf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bcafd1c9750d8333639ca2d315512a2c2b8759c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664406"
---
# <a name="upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard"></a><span data-ttu-id="4874b-102">обновить пакеты служб Integration Services с помощью мастера обновления пакетов служб SSIS</span><span class="sxs-lookup"><span data-stu-id="4874b-102">Upgrade Integration Services Packages Using the SSIS Package Upgrade Wizard</span></span>
  <span data-ttu-id="4874b-103">Пакеты, созданные в более ранних версиях служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , можно обновить до формата служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , используемых [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4874b-103">You can upgrade packages that were created in earlier versions of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] format that [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] uses.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="4874b-104">предоставляет мастер обновления пакетов служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4874b-104">provides the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard to help in this process.</span></span> <span data-ttu-id="4874b-105">Мастер можно настроить так, что исходные пакеты останутся без изменений. Поэтому в случае каких-либо трудностей обновления можно продолжать использовать исходные пакеты.</span><span class="sxs-lookup"><span data-stu-id="4874b-105">Because you can configure the wizard to backup up your original packages, you can continue to use the original packages if you experience upgrade difficulties.</span></span>  
  
 <span data-ttu-id="4874b-106">Мастер миграции пакетов служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] устанавливается при установке служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4874b-106">The [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard is installed when [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] is installed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4874b-107">Мастер миграции пакетов служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] доступен в следующих выпусках [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]: Standard, Enterprise, Developer.</span><span class="sxs-lookup"><span data-stu-id="4874b-107">The [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard is available in the Standard, Enterprise, and Developer Editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="4874b-108">Дополнительные сведения об обновлении пакетов служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] см. в разделе [Обновление пакетов служб Integration Services](upgrade-integration-services-packages.md).</span><span class="sxs-lookup"><span data-stu-id="4874b-108">For more information about how to upgrade [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, see [Upgrade Integration Services Packages](upgrade-integration-services-packages.md).</span></span>  
  
 <span data-ttu-id="4874b-109">В оставшейся части раздела описывается работа с мастером и создание резервных копий исходных пакетов.</span><span class="sxs-lookup"><span data-stu-id="4874b-109">The remainder of this topic describes how to run the wizard and back up the original packages.</span></span>  
  
## <a name="running-the-ssis-package-upgrade-wizard"></a><span data-ttu-id="4874b-110">Работа с мастером обновления пакетов служб SSIS</span><span class="sxs-lookup"><span data-stu-id="4874b-110">Running the SSIS Package Upgrade Wizard</span></span>  
 <span data-ttu-id="4874b-111">Мастер обновления пакетов служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] можно запустить из среды [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], из среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]или из командной строки.</span><span class="sxs-lookup"><span data-stu-id="4874b-111">You can run the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard from [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], or at the command prompt.</span></span>  
  
#### <a name="to-run-the-wizard-from-sql-server-data-tools"></a><span data-ttu-id="4874b-112">Запуск мастера из SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="4874b-112">To run the wizard from SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="4874b-113">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]создайте или откройте проект служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4874b-113">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], create or open an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="4874b-114">Находясь в обозревателе решений, правой кнопкой мыши щелкните узел **Пакеты служб SSIS** и выберите команду **Обновить все пакеты** , чтобы обновить все пакеты, принадлежащие этому узлу.</span><span class="sxs-lookup"><span data-stu-id="4874b-114">In Solution Explorer, right-click the **SSIS Packages** node, and then click **Upgrade All Packages** to upgrade all the packages under this node.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4874b-115">При открытии проекта служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], содержащего пакеты служб [!INCLUDE[ssISversion2005](../../includes/ssisversion2005-md.md)] или [!INCLUDE[ssISversion10](../../includes/ssisversion10-md.md)], службы [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] автоматически открывают мастер обновления пакетов служб [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4874b-115">When you open an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains [!INCLUDE[ssISversion2005](../../includes/ssisversion2005-md.md)] or [!INCLUDE[ssISversion10](../../includes/ssisversion10-md.md)] packages, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] automatically opens the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard.</span></span>  
  
#### <a name="to-run-the-wizard-from-sql-server-management-studio"></a><span data-ttu-id="4874b-116">Запуск мастера в среде SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4874b-116">To run the wizard from SQL Server Management Studio</span></span>  
  
-   <span data-ttu-id="4874b-117">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]подключитесь к службам [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], разверните узел **Сохраненные пакеты** , щелкните правой кнопкой мыши узел **Файловая система** или узел **MSDB** и выберите пункт **Обновить пакеты**.</span><span class="sxs-lookup"><span data-stu-id="4874b-117">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], expand the **Stored Packages** node, and right-click the **File System** or **MSDB** node, and then click **Upgrade Packages**.</span></span>  
  
#### <a name="to-run-the-wizard-at-the-command-prompt"></a><span data-ttu-id="4874b-118">Запуск мастера из командной строки</span><span class="sxs-lookup"><span data-stu-id="4874b-118">To run the wizard at the command prompt</span></span>  
  
-   <span data-ttu-id="4874b-119">В командной строке запустите файл SSISUpgrade.exe из папки **C:\Program FILES\MICROSOFT SQL server\120\dts\binn»** .</span><span class="sxs-lookup"><span data-stu-id="4874b-119">At the command prompt, run the SSISUpgrade.exe file from the **C:\Program Files\Microsoft SQL Server\120\DTS\Binn** folder.</span></span>  
  
## <a name="backing-up-the-original-packages"></a><span data-ttu-id="4874b-120">Резервное копирование исходных пакетов</span><span class="sxs-lookup"><span data-stu-id="4874b-120">Backing Up the Original Packages</span></span>  
 <span data-ttu-id="4874b-121">Чтобы создать резервные копии исходных пакетов перед их обновлением, исходные пакеты и обновленные пакеты должны храниться в той же папке файловой системы.</span><span class="sxs-lookup"><span data-stu-id="4874b-121">To back up the original packages, both the original packages and the upgraded packages must be stored in the same folder in the file system.</span></span> <span data-ttu-id="4874b-122">В зависимости от способа запуска мастера, это место хранения может определяться автоматически.</span><span class="sxs-lookup"><span data-stu-id="4874b-122">Depending on how you run the wizard, this storage location might be automatically selected.</span></span>  
  
-   <span data-ttu-id="4874b-123">При запуске мастера обновления пакетов служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] из среды [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]мастер автоматически сохраняет исходные и обновленные пакеты в одной папке файловой системы.</span><span class="sxs-lookup"><span data-stu-id="4874b-123">When you run the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard from [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], the wizard automatically stores both the original packages and upgraded packages in the same folder in the file system.</span></span>  
  
-   <span data-ttu-id="4874b-124">При запуске мастера обновления пакетов служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] из среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или из командной строки можно указать различное место хранения для первоначальных и обновленных пакетов.</span><span class="sxs-lookup"><span data-stu-id="4874b-124">When you run the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or at the command prompt, you can specify different storage locations for the original and upgraded packages.</span></span> <span data-ttu-id="4874b-125">Чтобы мастер создавал резервные копии исходных пакетов, убедитесь, что исходные и обновленные пакеты хранятся в одной и той же папке файловой системы.</span><span class="sxs-lookup"><span data-stu-id="4874b-125">To back up the original packages, make sure to specify that both the original and upgraded packages are stored in the same folder in the file system.</span></span> <span data-ttu-id="4874b-126">Если задать другие параметры хранения, мастер не сможет создать резервные копии исходных пакетов.</span><span class="sxs-lookup"><span data-stu-id="4874b-126">If you specify any other storage options, the wizard will not be able to back up the original packages.</span></span>  
  
 <span data-ttu-id="4874b-127">Мастер будет создавать резервные копии исходных пакетов в папке **SSISBackupFolder** .</span><span class="sxs-lookup"><span data-stu-id="4874b-127">When the wizard backs up the original packages, the wizard stores a copy of the original packages in an **SSISBackupFolder** folder.</span></span> <span data-ttu-id="4874b-128">Мастер создает папку **SSISBackupFolder** в папке, которая содержит исходные и обновленные пакеты.</span><span class="sxs-lookup"><span data-stu-id="4874b-128">The wizard creates this **SSISBackupFolder** folder as a subfolder to the folder that contains the original packages and the upgraded packages.</span></span>  
  
#### <a name="to-back-up-the-original-packages-in-sql-server-management-studio-or-at-the-command-prompt"></a><span data-ttu-id="4874b-129">Создание резервных копий исходных пакетов в среде SQL Server Management Studio или из командной строки</span><span class="sxs-lookup"><span data-stu-id="4874b-129">To back up the original packages in SQL Server Management Studio or at the command prompt</span></span>  
  
1.  <span data-ttu-id="4874b-130">Сохраните исходные пакеты в папке файловой системы.</span><span class="sxs-lookup"><span data-stu-id="4874b-130">Save the original packages to a location on the file system.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4874b-131">Мастер может создавать резервные копии только для пакетов, хранящихся в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="4874b-131">The backup option in the wizard only works with packages that have been stored to the file system.</span></span>  
  
2.  <span data-ttu-id="4874b-132">Запустите мастер обновления пакетов служб [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] из среды [!INCLUDE[ssIS](../../includes/ssis-md.md)] или из командной строки.</span><span class="sxs-lookup"><span data-stu-id="4874b-132">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or at the command prompt, run the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard.</span></span>  
  
3.  <span data-ttu-id="4874b-133">На странице **Выбор исходного расположения** мастера выберите для свойства **Источник пакета** значение **Файловая система**.</span><span class="sxs-lookup"><span data-stu-id="4874b-133">On the **Select Source Location** page of the wizard, set the **Package source** property to **File System**.</span></span>  
  
4.  <span data-ttu-id="4874b-134">На странице **Выбор целевого расположения** мастера выберите **Сохранить в исходное расположение** , чтобы сохранить обновленные пакеты в ту же папку, где находятся исходные пакеты.</span><span class="sxs-lookup"><span data-stu-id="4874b-134">On the **Select Destination Location** page of the wizard, select **Save to source location** tosave the upgraded packages to the same location as the original packages.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4874b-135">Этот параметр становится доступен только в случае, когда исходные и обновленные пакеты хранятся в одной и той же папке.</span><span class="sxs-lookup"><span data-stu-id="4874b-135">The backup option in the wizard is available only when the upgraded packages are stored in the same folder as the original packages.</span></span>  
  
5.  <span data-ttu-id="4874b-136">На странице мастера **Выбор параметров управления пакетами** выберите параметр **Создать резервную копию исходных пакетов** .</span><span class="sxs-lookup"><span data-stu-id="4874b-136">On the **Select Package Management Options** page of the wizard, select the **Backup original packages** option.</span></span>  
  
#### <a name="to-back-up-the-original-packages-in-sql-server-data-tools"></a><span data-ttu-id="4874b-137">Резервное копирование исходных пакетов в SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="4874b-137">To back up the original packages in SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="4874b-138">Сохраните исходные пакеты в папке файловой системы.</span><span class="sxs-lookup"><span data-stu-id="4874b-138">Save the original packages to a location on the file system.</span></span>  
  
2.  <span data-ttu-id="4874b-139">На странице мастера **Выбор параметров управления пакетами** выберите параметр **Создать резервную копию исходных пакетов** .</span><span class="sxs-lookup"><span data-stu-id="4874b-139">On the **Select Package Management Options** page of the wizard, select the **Backup original packages** option.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="4874b-140">Параметр **создать резервную копию исходных пакетов** не отображается при открытии [!INCLUDE[ssISversion2005](../../includes/ssisversion2005-md.md)] проекта или [!INCLUDE[ssISversion10](../../includes/ssisversion10-md.md)] в [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] , который автоматически запускает мастер.</span><span class="sxs-lookup"><span data-stu-id="4874b-140">The **Backup original packages** option is not displayed when you open a [!INCLUDE[ssISversion2005](../../includes/ssisversion2005-md.md)] or [!INCLUDE[ssISversion10](../../includes/ssisversion10-md.md)] project in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], which automatically launches the wizard.</span></span>  
  
3.  <span data-ttu-id="4874b-141">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]запустите мастер обновления пакетов служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4874b-141">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], run the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard.</span></span>  
  
  
