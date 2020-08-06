---
title: Импорт и экспорт пакетов (службы SSIS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- packages [Integration Services], importing
- packages [Integration Services], exporting
- importing packages
- exporting packages
ms.assetid: ef18ec11-b536-47d9-abd1-794099f43486
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b69f9d23431ed86f6b84be6857b7104cd8ba3dcc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666172"
---
# <a name="import-and-export-packages-ssis-service"></a><span data-ttu-id="76e97-102">Импорт и экспорт пакетов (службы SSIS)</span><span class="sxs-lookup"><span data-stu-id="76e97-102">Import and Export Packages (SSIS Service)</span></span>
    
> [!IMPORTANT]  
>  <span data-ttu-id="76e97-103">В данном разделе описывается компонент [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] — служба Windows для управления пакетами служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="76e97-103">This topic discusses the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service, a Windows service for managing [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages.</span></span> [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] <span data-ttu-id="76e97-104">поддерживает эту службу для обеспечения обратной совместимости с более ранними версиями служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76e97-104">supports the service for backward compatibility with earlier releases of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="76e97-105">Начиная с [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], на сервере служб Integration Services можно управлять пакетами.</span><span class="sxs-lookup"><span data-stu-id="76e97-105">Starting in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], you can manage objects such as packages on the Integration Services server.</span></span>  
  
 <span data-ttu-id="76e97-106">Пакеты можно сохранять либо в таблице sysssispackages базы данных msdb [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , либо в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="76e97-106">Packages can be saved either in the sysssispackages table in the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] msdb database or in the file system.</span></span>  
  
 <span data-ttu-id="76e97-107">Хранилище пакетов, являющееся логическим хранилищем, которое контролируется службой [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , может включать и базу данных msdb, и папки файловой системы, указанные в файле конфигурации для службы [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="76e97-107">The package store, which is the logical storage that [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service monitors and manages, can include both the msdb database and the file system folders specified in the configuration file for the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span>  
  
 <span data-ttu-id="76e97-108">Можно выполнять импорт и экспорт пакетов между следующими типами хранилищ:</span><span class="sxs-lookup"><span data-stu-id="76e97-108">You can import and export packages between the following storage types:</span></span>  
  
-   <span data-ttu-id="76e97-109">Папки файловой системы в любом месте этой файловой системы.</span><span class="sxs-lookup"><span data-stu-id="76e97-109">File system folders anywhere in the file system.</span></span>  
  
-   <span data-ttu-id="76e97-110">Папки в хранилище пакетов служб SSIS.</span><span class="sxs-lookup"><span data-stu-id="76e97-110">Folders in the SSIS Package Store.</span></span> <span data-ttu-id="76e97-111">Две папки по умолчанию с именами File System и MSDB.</span><span class="sxs-lookup"><span data-stu-id="76e97-111">The two default folders are named File System and MSDB.</span></span>  
  
-   <span data-ttu-id="76e97-112">База данных msdb [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="76e97-112">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] msdb database.</span></span>  
  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="76e97-113">предоставляют возможность для импорта и экспорта пакетов и посредством этого изменения формата и места хранения пакетов.</span><span class="sxs-lookup"><span data-stu-id="76e97-113">gives you the ability to import and export packages, and by doing this change the storage format and location of packages.</span></span> <span data-ttu-id="76e97-114">С помощью функций импорта и экспорта можно добавлять пакеты в файловую систему, хранилище пакетов или базу данных msdb, а также копировать пакеты из одного формата хранения в другой.</span><span class="sxs-lookup"><span data-stu-id="76e97-114">Using the import and export features, you can add packages to the file system, package store, or msdb database, and copy packages from one storage format to another.</span></span> <span data-ttu-id="76e97-115">Например, пакеты, сохраненные в msdb, можно скопировать в файловую систему и наоборот.</span><span class="sxs-lookup"><span data-stu-id="76e97-115">For example, packages saved in msdb can be copied to the file system and vice versa.</span></span>  
  
 <span data-ttu-id="76e97-116">Можно также скопировать пакет в другой формат с помощью программы командной строки **dtutil** (dtutil.exe).</span><span class="sxs-lookup"><span data-stu-id="76e97-116">You can also copy a package to a different format using the **dtutil** command prompt utility (dtutil.exe).</span></span> <span data-ttu-id="76e97-117">Дополнительные сведения см. в статье [dtutil Utility](dtutil-utility.md).</span><span class="sxs-lookup"><span data-stu-id="76e97-117">For more information, see [dtutil Utility](dtutil-utility.md).</span></span>  
  
## <a name="to-import-or-export-a-package"></a><span data-ttu-id="76e97-118">Импорт и экспорт пакетов</span><span class="sxs-lookup"><span data-stu-id="76e97-118">To import or export a package</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="76e97-119">В этом разделе обсуждается служба [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , входящая в состав [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76e97-119">This topic discusses the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service that is part of [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span></span> [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] <span data-ttu-id="76e97-120">поддерживает службы [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] для обеспечения обратной совместимости с [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76e97-120">supports the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service for backward compatibility with [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span></span> <span data-ttu-id="76e97-121">Сведения об управлении пакетами в [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] см. в разделе [Сервер служб Integration Services (SSIS)](catalog/integration-services-ssis-server-and-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="76e97-121">For information about managing packages in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], see [Integration Services &#40;SSIS&#41; Server](catalog/integration-services-ssis-server-and-catalog.md).</span></span>  
  
 <span data-ttu-id="76e97-122">Можно выполнять импорт и экспорт пакетов служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] между следующими типами хранилищ.</span><span class="sxs-lookup"><span data-stu-id="76e97-122">You can import or export an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package from or to the following locations:</span></span>  
  
-   <span data-ttu-id="76e97-123">Можно выполнить импорт пакетов, которые хранятся в экземпляре [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], в файловой системе или хранилище пакетов служб [!INCLUDE[ssIS](../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76e97-123">You can import a package that is stored in an instance of [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], in the file system, or in the [!INCLUDE[ssIS](../includes/ssis-md.md)] package store.</span></span> <span data-ttu-id="76e97-124">Импортированные пакеты сохраняются в [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] или в папке хранилища пакетов служб [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="76e97-124">The imported package is saved to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] or to a folder in the [!INCLUDE[ssIS](../includes/ssis-md.md)] package store.</span></span>  
  
-   <span data-ttu-id="76e97-125">Можно экспортировать пакеты, хранящиеся в экземпляре [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], в файловой системе или хранилище пакетов служб [!INCLUDE[ssIS](../includes/ssis-md.md)] , в другой формат хранения и в другое расположение.</span><span class="sxs-lookup"><span data-stu-id="76e97-125">You can export a package that is stored in an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], the file system, or the [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Store to a different storage format and location.</span></span>  
  
 <span data-ttu-id="76e97-126">Однако существует ряд ограничений на импорт и экспорт пакетов между разными версиями [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="76e97-126">However, there are some restrictions on importing and exporting a package between different versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="76e97-127">С экземпляра [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)]можно импортировать пакеты из экземпляра [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)], но нельзя экспортировать их в экземпляр [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76e97-127">On an instance of [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)], you can import packages from an instance of [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)], but you cannot export packages to an instance of [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)].</span></span>  
  
-   <span data-ttu-id="76e97-128">С экземпляра [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)]нельзя импортировать пакеты из экземпляра [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)]или экспортировать их туда.</span><span class="sxs-lookup"><span data-stu-id="76e97-128">On an instance of [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)], you cannot import packages from, or export packages to, an instance of [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span></span>  
  
 <span data-ttu-id="76e97-129">В следующих разделах описывается импорт и экспорт пакетов с помощью среды [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="76e97-129">The following procedures describe how to use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to import or export a package.</span></span>  
  
#### <a name="to-import-a-package-by-using-sql-server-management-studio"></a><span data-ttu-id="76e97-130">Импорт пакета с помощью среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="76e97-130">To import a package by Using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="76e97-131">Нажмите кнопку **Пуск**, укажите пункт **Microsoft** [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] и выберите пункт **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="76e97-131">Click **Start**, point to **Microsoft** [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="76e97-132">В диалоговом окне **Соединение с сервером** установите следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="76e97-132">In the **Connect to Server** dialog box set the following options:</span></span>  
  
    -   <span data-ttu-id="76e97-133">В поле **Тип сервера** выберите **Службы Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="76e97-133">In the **Server type** box, select **Integration Services**.</span></span>  
  
    -   <span data-ttu-id="76e97-134">В поле **Имя сервера** введите имя сервера или щелкните **\<Browse for more...>** и найдите нужный сервер.</span><span class="sxs-lookup"><span data-stu-id="76e97-134">In the **Server name** box, provide a server name or click **\<Browse for more...>** and locate the server to use.</span></span>  
  
3.  <span data-ttu-id="76e97-135">Если обозреватель объектов не открыт, в меню **Вид** выберите пункт **Обозреватель объектов**.</span><span class="sxs-lookup"><span data-stu-id="76e97-135">If Object Explorer is not open, on the **View** menu, click **Object Explorer**.</span></span>  
  
4.  <span data-ttu-id="76e97-136">В обозревателе объектов разверните папку **Сохраненные пакеты** .</span><span class="sxs-lookup"><span data-stu-id="76e97-136">In Object Explorer, expand the **Stored Packages** folder.</span></span>  
  
5.  <span data-ttu-id="76e97-137">Разверните вложенные папки и найдите папку, в которую нужно выполнить импорт пакета.</span><span class="sxs-lookup"><span data-stu-id="76e97-137">Expand the subfolders to locate the folder into which you want to import a package.</span></span>  
  
6.  <span data-ttu-id="76e97-138">Щелкните папку правой кнопкой мыши и выберите пункт **Импорт пакета**.</span><span class="sxs-lookup"><span data-stu-id="76e97-138">Right-click the folder, click **Import Package**.</span></span> <span data-ttu-id="76e97-139">А затем выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="76e97-139">and then do one of the following:</span></span>  
  
    -   <span data-ttu-id="76e97-140">Чтобы выполнить импорт из экземпляра [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], выберите параметр **SQL Server** и укажите сервер и метод проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="76e97-140">To import from an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], select the **SQL Server** option, and then specify the server and select the authentication mode.</span></span> <span data-ttu-id="76e97-141">При выборе проверки подлинности [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] укажите имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="76e97-141">If you select [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a user name and a password.</span></span>  
  
         <span data-ttu-id="76e97-142">Нажмите кнопку обзора **(…)** , выберите импортируемый пакет и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="76e97-142">Click the browse button **(...)**, select the package to import, and then click **OK.**</span></span>  
  
    -   <span data-ttu-id="76e97-143">Чтобы выполнить импорт из файловой системы, выберите параметр **Файловая система** .</span><span class="sxs-lookup"><span data-stu-id="76e97-143">To import from the file system, select the **File system** option.</span></span>  
  
         <span data-ttu-id="76e97-144">Нажмите кнопку обзора **(…)** , выберите импортируемый пакет и нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="76e97-144">Click the browse button **(...)**, select the package to import, and then click **Open.**</span></span>  
  
    -   <span data-ttu-id="76e97-145">Чтобы выполнить импорт из хранилища пакетов служб [!INCLUDE[ssIS](../includes/ssis-md.md)] , укажите сервер в поле **Хранилище пакетов служб SSIS** .</span><span class="sxs-lookup"><span data-stu-id="76e97-145">To import from the [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Store, select the **SSIS Package Store** option and specify the server.</span></span>  
  
         <span data-ttu-id="76e97-146">Нажмите кнопку обзора **(…)** , выберите импортируемый пакет и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="76e97-146">Click the browse button **(...)**, select the package to import, and then click **OK.**</span></span>  
  
7.  <span data-ttu-id="76e97-147">При необходимости обновите название пакета.</span><span class="sxs-lookup"><span data-stu-id="76e97-147">Optionally, update the package name.</span></span>  
  
8.  <span data-ttu-id="76e97-148">Чтобы обновить уровень защиты пакета, нажмите кнопку обзора **(…)** и выберите иной уровень защиты с помощью диалогового окна **Уровень защиты пакета**.</span><span class="sxs-lookup"><span data-stu-id="76e97-148">To update the protection level of the package, click the browse button **(...)** and choose a different protection level by using the **Package Protection Level** dialog box.</span></span> <span data-ttu-id="76e97-149">При выборе параметра **Шифровать конфиденциальные данные паролем** или **Шифровать все данные паролем** введите и подтвердите пароль.</span><span class="sxs-lookup"><span data-stu-id="76e97-149">If the **Encrypt sensitive data with password** or the **Encrypt all data with password** option is selected, type and confirm a password.</span></span>  
  
9. <span data-ttu-id="76e97-150">Чтобы завершить импорт, нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="76e97-150">Click **OK** to complete the import.</span></span>  
  
#### <a name="to-export-a-package-by-using-sql-server-management-studio"></a><span data-ttu-id="76e97-151">Экспорт пакета с помощью среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="76e97-151">To export a package by Using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="76e97-152">Нажмите кнопку **Пуск**, укажите пункт **Microsoft** [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] и выберите пункт **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="76e97-152">Click **Start**, point to **Microsoft** [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="76e97-153">В диалоговом окне **Соединение с сервером** установите следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="76e97-153">In the **Connect to Server** dialog box, set the following options:</span></span>  
  
    -   <span data-ttu-id="76e97-154">В поле **Тип сервера** выберите **Службы Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="76e97-154">In the **Server type** box, select **Integration Services**.</span></span>  
  
    -   <span data-ttu-id="76e97-155">В поле **Имя сервера** введите имя сервера или щелкните **\<Browse for more...>** и найдите нужный сервер.</span><span class="sxs-lookup"><span data-stu-id="76e97-155">In the **Server name** box, provide a server name or click **\<Browse for more...>** and locate the server to use.</span></span>  
  
3.  <span data-ttu-id="76e97-156">Если обозреватель объектов не открыт, в меню **Вид** выберите пункт **Обозреватель объектов**.</span><span class="sxs-lookup"><span data-stu-id="76e97-156">If Object Explorer is not open, on the **View** menu, click **Object Explorer**.</span></span>  
  
4.  <span data-ttu-id="76e97-157">В обозревателе объектов разверните папку **Сохраненные пакеты** .</span><span class="sxs-lookup"><span data-stu-id="76e97-157">In Object Explorer, expand the **Stored Packages** folder.</span></span>  
  
5.  <span data-ttu-id="76e97-158">Разверните вложенные папки и выберите пакет для экспорта.</span><span class="sxs-lookup"><span data-stu-id="76e97-158">Expand the subfolders to locate the package you want to export.</span></span>  
  
6.  <span data-ttu-id="76e97-159">Щелкните правой кнопкой мыши пакет, выберите пункт **Экспорт**и выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="76e97-159">Right-click the package, click **Export**, and then do one of the following:</span></span>  
  
    -   <span data-ttu-id="76e97-160">Чтобы выполнить экспорт в экземпляр [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], выберите **SQL Server** , затем определите сервер и выберите режим проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="76e97-160">To export to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], select the **SQL Server** option, and then specify the server and select the authentication mode.</span></span> <span data-ttu-id="76e97-161">При выборе проверки подлинности [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] укажите имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="76e97-161">If you select [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a user name and a password.</span></span>  
  
         <span data-ttu-id="76e97-162">Нажмите кнопку обзора **(…)** и разверните папку **Пакеты служб SSIS**, чтобы выбрать папку, в которую нужно сохранить пакет.</span><span class="sxs-lookup"><span data-stu-id="76e97-162">Click the browse button **(...)**, and expand the **SSIS Packages** folder to locate the folder to which you want to save the package.</span></span> <span data-ttu-id="76e97-163">При необходимости измените имя пакета по умолчанию и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="76e97-163">Optionally, update the default name of the package, and then click **OK**.</span></span>  
  
    -   <span data-ttu-id="76e97-164">Чтобы выполнить экспорт в файловую систему, выберите параметр **Файловая система** .</span><span class="sxs-lookup"><span data-stu-id="76e97-164">To export to the file system, select the **File System** option.</span></span>  
  
         <span data-ttu-id="76e97-165">Нажмите кнопку обзора **(…)** , чтобы выбрать папку, в которую нужно экспортировать пакет, введите имя файла пакета и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="76e97-165">Click the browse button **(...)** to locate the folder to which you want to export the package, type the name of the package file, and then click **Save.**</span></span>  
  
    -   <span data-ttu-id="76e97-166">Чтобы выполнить экспорт в хранилище пакетов служб [!INCLUDE[ssIS](../includes/ssis-md.md)] , выберите **Хранилище пакетов служб SSIS** и укажите сервер.</span><span class="sxs-lookup"><span data-stu-id="76e97-166">To export to the [!INCLUDE[ssIS](../includes/ssis-md.md)] package store, select the **SSIS Package Store** option, and specify the server.</span></span>  
  
         <span data-ttu-id="76e97-167">Нажмите кнопку обзора **(…)** , разверните папку **Пакеты служб SSIS** и выберите папку, в которую нужно сохранить пакет.</span><span class="sxs-lookup"><span data-stu-id="76e97-167">Click the browse button **(...)**, expand the **SSIS Packages** folder, and select the folder to which you want to save the package.</span></span> <span data-ttu-id="76e97-168">Если нужно изменить имя пакета, введите новое имя в текстовое поле **Имя пакета** .</span><span class="sxs-lookup"><span data-stu-id="76e97-168">Optionally, enter a new name for the package in the **Package Name** text box.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="76e97-169">Чтобы обновить уровень защиты пакета, нажмите кнопку обзора **(…)** и выберите иной уровень защиты с помощью диалогового окна **Уровень защиты пакета**.</span><span class="sxs-lookup"><span data-stu-id="76e97-169">To update the protection level of the package, click the browse button **(...)** and choose a different protection level by using the **Package Protection Level** dialog box.</span></span> <span data-ttu-id="76e97-170">При выборе параметра **Шифровать конфиденциальные данные паролем** или **Шифровать все данные паролем** введите и подтвердите пароль.</span><span class="sxs-lookup"><span data-stu-id="76e97-170">If the **Encrypt sensitive data with password** or the **Encrypt all data with password** option is selected, type and confirm a password.</span></span>  
  
8.  <span data-ttu-id="76e97-171">Чтобы завершить экспорт, нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="76e97-171">Click **OK** to complete the export.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76e97-172">См. также:</span><span class="sxs-lookup"><span data-stu-id="76e97-172">See Also</span></span>  
 [<span data-ttu-id="76e97-173">Управление пакетами (службы SSIS)</span><span class="sxs-lookup"><span data-stu-id="76e97-173">Package Management &#40;SSIS Service&#41;</span></span>](service/package-management-ssis-service.md)  
  
  
