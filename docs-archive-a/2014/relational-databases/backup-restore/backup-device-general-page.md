---
title: Устройство резервного копирования (страница "Общие") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.backupdevice.general.f1
ms.assetid: c557e37d-319e-4adb-a0c1-94189b15d2ac
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d73bdf3ce4b88214286b5f232924d811716a247e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655786"
---
# <a name="backup-device-general-page"></a><span data-ttu-id="32a3b-102">Устройство резервного копирования (страница «Общие»)</span><span class="sxs-lookup"><span data-stu-id="32a3b-102">Backup Device (General Page)</span></span>
  <span data-ttu-id="32a3b-103">На странице **Общие** можно указать или просмотреть общие свойства логического устройства резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="32a3b-103">Use the **General** page to specify or view the general properties of a logical backup device.</span></span>  
  
 <span data-ttu-id="32a3b-104">**Использование среды SQL Server Management Studio для просмотра содержимого устройства резервного копирования**</span><span class="sxs-lookup"><span data-stu-id="32a3b-104">**To use SQL Server Management Studio to view the contents of a backup device**</span></span>  
  
-   [<span data-ttu-id="32a3b-105">Просмотр содержимого ленты или файла резервной копии (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="32a3b-105">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="32a3b-106">Просмотр свойств и содержимого логического устройства резервного копирования (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="32a3b-106">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
## <a name="options"></a><span data-ttu-id="32a3b-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="32a3b-107">Options</span></span>  
 <span data-ttu-id="32a3b-108">**Имя устройства**</span><span class="sxs-lookup"><span data-stu-id="32a3b-108">**Device name**</span></span>  
 <span data-ttu-id="32a3b-109">Просмотр имени существующего логического устройства резервного копирования или создание нового имени логического устройства резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="32a3b-109">View the name of an existing logical backup device or specify the name of a new logical backup device.</span></span>  
  
 <span data-ttu-id="32a3b-110">**Лента**</span><span class="sxs-lookup"><span data-stu-id="32a3b-110">**Tape**</span></span>  
 <span data-ttu-id="32a3b-111">Просмотр и выбор целевого ленточного устройства из списка **Лента** .</span><span class="sxs-lookup"><span data-stu-id="32a3b-111">View or select the destination tape device in the **Tape** list.</span></span> <span data-ttu-id="32a3b-112">Этот параметр доступен, только если к компьютеру, на котором выполняется экземпляр компонента [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], подключен ленточный накопитель.</span><span class="sxs-lookup"><span data-stu-id="32a3b-112">This option is available only if a tape drive is attached to the computer that is running the instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="32a3b-113">Устройства резервного копирования на магнитных лентах на удаленных компьютерах не могут указываться в качестве места назначения резервной копии.</span><span class="sxs-lookup"><span data-stu-id="32a3b-113">Tape backup devices on remote computers are not valid backup destinations.</span></span>  
  
 <span data-ttu-id="32a3b-114">**Файл**</span><span class="sxs-lookup"><span data-stu-id="32a3b-114">**File**</span></span>  
 <span data-ttu-id="32a3b-115">Просмотр целевого файла существующего логического устройства резервного копирования или указание целевого файла для нового логического устройства резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="32a3b-115">View the destination file of an existing logical backup device, or specify a destination file for a new logical backup device.</span></span>  
  
-   <span data-ttu-id="32a3b-116">Для существующего логического устройства резервного копирования отображается путь к файлу резервной копии.</span><span class="sxs-lookup"><span data-stu-id="32a3b-116">For an existing logical backup device, the path of the backup file is displayed.</span></span> <span data-ttu-id="32a3b-117">Поле **Файл** недоступно для редактирования, кнопка «Обзор» также недоступна.</span><span class="sxs-lookup"><span data-stu-id="32a3b-117">The **File** field is not editable, and the Browse button is unavailable.</span></span>  
  
-   <span data-ttu-id="32a3b-118">Для нового логического устройства резервного копирования необходимо указать путь файла резервной копии, для которого определяется логическое устройство резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="32a3b-118">For a new logical backup device, you must supply the path of the backup file for which you are defining the logical backup device.</span></span> <span data-ttu-id="32a3b-119">Это должен быть новый файл.</span><span class="sxs-lookup"><span data-stu-id="32a3b-119">This file does not have to exist yet.</span></span>  
  
     <span data-ttu-id="32a3b-120">Для указания локального файла резервной копии нужно нажать кнопку «Обзор» справа от текстового поля **Файл** .</span><span class="sxs-lookup"><span data-stu-id="32a3b-120">To specify a local backup file, you can click the Browse button to the right of the **File** text box.</span></span> <span data-ttu-id="32a3b-121">Затем в диалоговом окне **Расположение файлов базы данных** перейдите к любому местоположению на любом из фиксированных дисков компьютера, на котором выполняется экземпляр сервера.</span><span class="sxs-lookup"><span data-stu-id="32a3b-121">Then, in the **Locate Database Files** dialog box, you can navigate to any location on any of the fixed drives on the computer running the server instance.</span></span> <span data-ttu-id="32a3b-122">Если файл резервной копии еще не существует, нужно ввести имя файла в поле **Имя файла** данного диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="32a3b-122">If the backup file does not exist yet, you must enter the filename you want to use in the **File name** field of that dialog box.</span></span>  
  
     <span data-ttu-id="32a3b-123">Или можно отредактировать поле **Файл** вручную, чтобы изменить путь, имя файла и расширение, указанные по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="32a3b-123">Alternatively, you can edit the **File** field manually to override the default path, file name, and extension.</span></span> <span data-ttu-id="32a3b-124">Для указания удаленного файла в качестве места расположения резервной копии введите полное имя файла в формате UNC.</span><span class="sxs-lookup"><span data-stu-id="32a3b-124">To specify a remote file as your backup destination, enter its fully qualified universal naming convention (UNC) name.</span></span> <span data-ttu-id="32a3b-125">Дополнительные сведения см. в разделе [Устройства резервного копирования (SQL Server)](backup-devices-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="32a3b-125">For more information, see [Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="32a3b-126">Возможны сетевые ошибки в случае резервного копирования данных по сети, поэтому по его окончании рекомендуется сделать проверку.</span><span class="sxs-lookup"><span data-stu-id="32a3b-126">Backing up data over a network can be subject to network errors; therefore, we recommend that you verify the backup operation after it finishes.</span></span> <span data-ttu-id="32a3b-127">Дополнительные сведения см. в разделе [RESTORE VERIFYONLY (Transact-SQL)](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="32a3b-127">For more information, see [RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="32a3b-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="32a3b-128">Remarks</span></span>  
 <span data-ttu-id="32a3b-129">Резервные копии на наборе из одного или нескольких устройств резервного копирования образуют отдельный набор носителей.</span><span class="sxs-lookup"><span data-stu-id="32a3b-129">The backups on a set of one or more backup devices compose a single media set.</span></span> <span data-ttu-id="32a3b-130">*Набор носителей* — это упорядоченная коллекция носителей резервных копий, лент или дисковых файлов, на которые производили запись одна или несколько операций резервного копирования, получая доступ по фиксированному типу и номеру устройства.</span><span class="sxs-lookup"><span data-stu-id="32a3b-130">A *media set* is an ordered collection of backup media, tapes or disk files, to which one or more backup operations have written using a fixed type and number of backup devices.</span></span> <span data-ttu-id="32a3b-131">Сведения о наборах носителей см. в разделе [Наборы носителей, семейства носителей и резервные наборы данных (SQL Server)](media-sets-media-families-and-backup-sets-sql-server.md), подключен ленточный накопитель.</span><span class="sxs-lookup"><span data-stu-id="32a3b-131">For information about media sets, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
 <span data-ttu-id="32a3b-132">Инициализация физического устройства резервного копирования, соответствующего логическому устройству, производится при записи первой резервной копии в наборе носителей на логическое устройство резервной копии.</span><span class="sxs-lookup"><span data-stu-id="32a3b-132">The physical backup device corresponding to a logical backup device is initialized when the first backup in the media set is written to the logical backup device.</span></span> <span data-ttu-id="32a3b-133">Если физическое устройство резервного копирования представляет собой не существующий до этого момента файл, он создается на данном этапе.</span><span class="sxs-lookup"><span data-stu-id="32a3b-133">If the physical backup device is a file that does not exist yet, it is created at that time.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="32a3b-134">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="32a3b-134">Related Tasks</span></span>  
  
-   [<span data-ttu-id="32a3b-135">Определение логического устройства резервного копирования для дискового файла (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="32a3b-135">Define a Logical Backup Device for a Disk File &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-disk-file-sql-server.md)  
  
-   [<span data-ttu-id="32a3b-136">Определение логического устройства резервного копирования для ленточного накопителя (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="32a3b-136">Define a Logical Backup Device for a Tape Drive &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-tape-drive-sql-server.md)  
  
-   [<span data-ttu-id="32a3b-137">Указание в качестве назначения резервного копирования диска или ленты (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="32a3b-137">Specify a Disk or Tape As a Backup Destination &#40;SQL Server&#41;</span></span>](specify-a-disk-or-tape-as-a-backup-destination-sql-server.md)  
  
-   [<span data-ttu-id="32a3b-138">Удаление устройства резервного копирования (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="32a3b-138">Delete a Backup Device &#40;SQL Server&#41;</span></span>](delete-a-backup-device-sql-server.md)  
  
-   [<span data-ttu-id="32a3b-139">Назначение срока хранения резервной копии (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="32a3b-139">Set the Expiration Date on a Backup &#40;SQL Server&#41;</span></span>](set-the-expiration-date-on-a-backup-sql-server.md)  
  
-   [<span data-ttu-id="32a3b-140">Просмотр содержимого ленты или файла резервной копии (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="32a3b-140">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="32a3b-141">Просмотр файлов данных и журналов в резервном наборе данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="32a3b-141">View the Data and Log Files in a Backup Set &#40;SQL Server&#41;</span></span>](view-the-data-and-log-files-in-a-backup-set-sql-server.md)  
  
-   [<span data-ttu-id="32a3b-142">Просмотр свойств и содержимого логического устройства резервного копирования (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="32a3b-142">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
-   [<span data-ttu-id="32a3b-143">Восстановление резервной копии с устройства (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="32a3b-143">Restore a Backup from a Device &#40;SQL Server&#41;</span></span>](restore-a-backup-from-a-device-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="32a3b-144">См. также:</span><span class="sxs-lookup"><span data-stu-id="32a3b-144">See Also</span></span>  
 <span data-ttu-id="32a3b-145">[Устройства резервного копирования (SQL Server)](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="32a3b-145">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 [<span data-ttu-id="32a3b-146">Наборы носителей, семейства носителей и резервные наборы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="32a3b-146">Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
  
  
