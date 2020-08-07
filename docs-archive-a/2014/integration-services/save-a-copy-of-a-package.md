---
title: Сохранение копии пакета | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services packages, saving
- packages [Integration Services], saving
- saving packages
- SSIS packages, saving
- SQL Server Integration Services packages, saving
ms.assetid: 21482a20-e420-4452-b7eb-8f9fa1929f31
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 02ee2374fddb7dbb6b17adc2a4a10707179c882d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730833"
---
# <a name="save-a-copy-of-a-package"></a><span data-ttu-id="a6ddc-102">Сохранение одной копии пакета</span><span class="sxs-lookup"><span data-stu-id="a6ddc-102">Save a Copy of a Package</span></span>
  <span data-ttu-id="a6ddc-103">Эта процедура описывает, как сохранить копию пакета в файле, хранилище пакетов или базе данных **msdb** в [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a6ddc-103">This procedure describes how to save a copy of a package to the file system, to the package store, or to the **msdb** database in [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a6ddc-104">При указании места сохранения копии пакета можно также обновить имя пакета.</span><span class="sxs-lookup"><span data-stu-id="a6ddc-104">When you specify a location to save the package copy, you can also update the name of the package.</span></span>  
  
 <span data-ttu-id="a6ddc-105">Хранилищем пакетов может быть одновременно база данных **msdb** и папки файловой системы, только база данных **msdb**или только папки файловой системы.</span><span class="sxs-lookup"><span data-stu-id="a6ddc-105">The package store can include both the **msdb** database and the folders in the file system, only **msdb**, or only folders in the file system.</span></span> <span data-ttu-id="a6ddc-106">В базе данных **msdb**пакеты хранятся в таблице **sysdtspackages90** .</span><span class="sxs-lookup"><span data-stu-id="a6ddc-106">In **msdb**, packages are saved to the **sysssispackages** table.</span></span> <span data-ttu-id="a6ddc-107">Эта таблица содержит столбец **folderid** , который идентифицирует логический каталог, которому принадлежит пакет.</span><span class="sxs-lookup"><span data-stu-id="a6ddc-107">This table includes a **folderid** column that identifies the logical folder to which the package belongs.</span></span> <span data-ttu-id="a6ddc-108">Логические каталоги предоставляют полезный способ группировки пакетов, сохраненных в базе данных **msdb** так же как файловая система предоставляет способ группировки пакетов, сохраненных в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="a6ddc-108">The logical folders provide a useful way to group packages saved to **msdb** in the same way that folders in the file system provide a way to group packages saved to the file system.</span></span> <span data-ttu-id="a6ddc-109">Строки в таблице **sysdtspackagefolders90** в базе данных **msdb** определяют папки.</span><span class="sxs-lookup"><span data-stu-id="a6ddc-109">Rows in the **sysssispackagefolders** table in **msdb** define the folders.</span></span>  
  
 <span data-ttu-id="a6ddc-110">Если база данных **msdb** не определена как часть хранилища пакетов, то при выборе SQL Server в параметре **Путь к пакету** можно продолжить связывание пакетов с существующими логическими папками.</span><span class="sxs-lookup"><span data-stu-id="a6ddc-110">If **msdb** is not defined as part of the package store, you can continue to associate packages with existing logical folders when you select SQL Server in the **Package Path** option.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a6ddc-111">Чтобы сохранить копию пакета, необходимо открыть пакет в конструкторе служб [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a6ddc-111">The package must be opened in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer before you can save a copy of the package.</span></span>  
  
### <a name="to-save-a-copy-of-a-package"></a><span data-ttu-id="a6ddc-112">Сохранение копии пакета</span><span class="sxs-lookup"><span data-stu-id="a6ddc-112">To save a copy of a package</span></span>  
  
1.  <span data-ttu-id="a6ddc-113">В обозревателе решений дважды щелкните пакет, копию которого необходимо сохранить.</span><span class="sxs-lookup"><span data-stu-id="a6ddc-113">In Solution Explorer, double-click the package of which you want to save a copy.</span></span>  
  
2.  <span data-ttu-id="a6ddc-114">В меню **Файл** выберите команду **Сохранить копию \<package file> как**.</span><span class="sxs-lookup"><span data-stu-id="a6ddc-114">On the **File** menu, click **Save Copy of \<package file> As**.</span></span>  
  
3.  <span data-ttu-id="a6ddc-115">В диалоговом окне **Сохранение копии пакета** выберите размещение пакета в списке **Размещение пакета** .</span><span class="sxs-lookup"><span data-stu-id="a6ddc-115">In the **Save Copy of Package** dialog box, select a package location in the **Package location** list.</span></span>  
  
4.  <span data-ttu-id="a6ddc-116">Если для размещения пакета выбран **SQL Server** или **Хранилище пакетов служб SSIS**, то введите имя сервера.</span><span class="sxs-lookup"><span data-stu-id="a6ddc-116">If the location is **SQL Server** or **SSIS Package Store**, provide a server name.</span></span>  
  
5.  <span data-ttu-id="a6ddc-117">Если сохранение производится в [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], укажите тип проверки подлинности а если используется проверка подлинности [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , введите имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="a6ddc-117">If saving to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], specify the authentication type and, if using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a user name and password.</span></span>  
  
6.  <span data-ttu-id="a6ddc-118">Чтобы указать путь к пакету, введите путь к пакету или нажмите кнопку обзора **(…)** и укажите расположение пакета.</span><span class="sxs-lookup"><span data-stu-id="a6ddc-118">To specify the package path, either type the path or click the browse button **(...)** to specify the location of the package.</span></span> <span data-ttu-id="a6ddc-119">Стандартное имя пакета — Пакет.</span><span class="sxs-lookup"><span data-stu-id="a6ddc-119">The default name of the package is Package.</span></span> <span data-ttu-id="a6ddc-120">При необходимости замените имя пакета на нужное.</span><span class="sxs-lookup"><span data-stu-id="a6ddc-120">Optionally, update the package name to one that suits your needs.</span></span>  
  
     <span data-ttu-id="a6ddc-121">При выборе **SQL Server** в качестве значения параметра **Путь к пакету** путь к пакету состоит из логических папок в базе данных **msdb** и имени пакета.</span><span class="sxs-lookup"><span data-stu-id="a6ddc-121">If you select **SQL Server** as the **Package Path** option, the package path consists of logical folders in **msdb** and the package name.</span></span> <span data-ttu-id="a6ddc-122">Например, если пакет DownloadMonthlyData связан с каталогом Finance в каталоге MSDB (имя по умолчанию корневого логического каталога в базе данных **msdb**), то путь к пакету DownloadMonthlyData выглядит как MSDB/Finance/DownloadMonthlyData</span><span class="sxs-lookup"><span data-stu-id="a6ddc-122">For example, if the package DownloadMonthlyData is associated with the Finance folder within the MSDB folder (the default name of the root logical folder in **msdb**), the package path for the package named DownloadMonthlyData is MSDB/Finance/DownloadMonthlyData</span></span>  
  
     <span data-ttu-id="a6ddc-123">Если в качестве значения параметра **Путь к пакету** выбирается **Хранилище пакетов служб SSIS** , путь к пакету состоит из каталога, которым управляют службы Integration Services.</span><span class="sxs-lookup"><span data-stu-id="a6ddc-123">If you select **SSIS Package Store** as the **Package Path** option, the package path consists of the folder that the Integration Services service manages.</span></span> <span data-ttu-id="a6ddc-124">Например, если пакет UpdateDeductions находится в папке HumanResources — в папке файловой системы, которой управляет служба, то путь к пакету выглядит как /File System/HumanResources/UpdateDeductions; аналогично: если пакет PostResumes связан с папкой HumanResources в папке MSDB, то путь к пакету выглядит как MSDB/HumanResources/PostResumes.</span><span class="sxs-lookup"><span data-stu-id="a6ddc-124">For example, if the package UpdateDeductions is located in the HumanResources folder within the file system folder that the service manages, the package path is /File System/HumanResources/UpdateDeductions; likewise, if the package PostResumes is associated with the HumanResources folder within the MSDB folder, the package path is MSDB/HumanResources/PostResumes.</span></span>  
  
     <span data-ttu-id="a6ddc-125">При выборе **Файловой системы** в качестве значения параметра **Путь к пакету** , путь к пакету представляет собой имя в файловой системе и имя файла.</span><span class="sxs-lookup"><span data-stu-id="a6ddc-125">If you select **File System** as the **Package Path** option, the package path is the location in the file system and the file name.</span></span> <span data-ttu-id="a6ddc-126">Например, если имя пакета UpdateDemographics, то путь к пакету выглядит как C:\HumanResources\Quarterly\UpdateDemographics.dtsx.</span><span class="sxs-lookup"><span data-stu-id="a6ddc-126">For example, if the package name is UpdateDemographics the package path is C:\HumanResources\Quarterly\UpdateDemographics.dtsx.</span></span>  
  
7.  <span data-ttu-id="a6ddc-127">Просмотрите уровень защиты пакета.</span><span class="sxs-lookup"><span data-stu-id="a6ddc-127">Review the package protection level.</span></span>  
  
8.  <span data-ttu-id="a6ddc-128">Для изменения уровня защиты нажмите кнопку обзора **(…)** возле поля **Уровень защиты**.</span><span class="sxs-lookup"><span data-stu-id="a6ddc-128">Optionally, click the browse button **(...)** by the **Protection level** box to change the protection level.</span></span>  
  
    -   <span data-ttu-id="a6ddc-129">В диалоговом окне **Уровень защиты пакета** выберите иной уровень защиты.</span><span class="sxs-lookup"><span data-stu-id="a6ddc-129">In the **Package Protection Level** dialog box, select a different protection level.</span></span>  
  
    -   <span data-ttu-id="a6ddc-130">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a6ddc-130">Click **OK**.</span></span>  
  
9. <span data-ttu-id="a6ddc-131">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a6ddc-131">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6ddc-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="a6ddc-132">See Also</span></span>  
 <span data-ttu-id="a6ddc-133">[Integration Services &#40;пакетов&#41; SSIS](../../2014/integration-services/integration-services-ssis-packages.md) </span><span class="sxs-lookup"><span data-stu-id="a6ddc-133">[Integration Services &#40;SSIS&#41; Packages](../../2014/integration-services/integration-services-ssis-packages.md) </span></span>  
 [<span data-ttu-id="a6ddc-134">Настройка служб Integration Services (службы SSIS)</span><span class="sxs-lookup"><span data-stu-id="a6ddc-134">Configuring the Integration Services Service &#40;SSIS Service&#41;</span></span>](service/integration-services-service-ssis-service.md)  
  
  
