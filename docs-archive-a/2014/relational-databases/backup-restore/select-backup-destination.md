---
title: Выбор места расположения резервной копии | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.selectbackupdest.f1
ms.assetid: f79e824b-1525-45de-8ede-513563af41b6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5ffd1d2529dd13e42689bcf168c972d757fb5499
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666669"
---
# <a name="select-backup-destination"></a><span data-ttu-id="a7c76-102">Выбор места расположения резервной копии</span><span class="sxs-lookup"><span data-stu-id="a7c76-102">Select Backup Destination</span></span>
  <span data-ttu-id="a7c76-103">Используйте диалоговое окно **Выбор места расположения резервной копии** для выбора устройства, где будет находиться резервная копия.</span><span class="sxs-lookup"><span data-stu-id="a7c76-103">Use the **Select Backup Destination** dialog box to select a device as your backup destination.</span></span> <span data-ttu-id="a7c76-104">Расположением резервной копии может быть диск или логическое устройство резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="a7c76-104">A backup destination can be either a disk or a logical backup device.</span></span>  
  
 <span data-ttu-id="a7c76-105">**Резервное копирование базы данных с помощью среды SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="a7c76-105">**To use SQL Server Management Studio to back up a database**</span></span>  
  
-   [<span data-ttu-id="a7c76-106">Создание полной резервной копии базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a7c76-106">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="a7c76-107">Создание разностной резервной копии базы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a7c76-107">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="a7c76-108">Резервное копирование файлов и файловых групп (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a7c76-108">Back Up Files and Filegroups &#40;SQL Server&#41;</span></span>](back-up-files-and-filegroups-sql-server.md)  
  
-   [<span data-ttu-id="a7c76-109">Создание резервной копии журнала транзакций (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a7c76-109">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](back-up-a-transaction-log-sql-server.md)  
  
## <a name="options"></a><span data-ttu-id="a7c76-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="a7c76-110">Options</span></span>  
 <span data-ttu-id="a7c76-111">Параметры диалогового окна зависят от выбранного места назначения: диск или магнитная лента.</span><span class="sxs-lookup"><span data-stu-id="a7c76-111">The options of this dialog box depend on whether you are selecting a destination on disk or on tape.</span></span>  
  
 <span data-ttu-id="a7c76-112">**Место назначения на диске**</span><span class="sxs-lookup"><span data-stu-id="a7c76-112">**Destination on disk**</span></span>  
 <span data-ttu-id="a7c76-113">Для указания места назначения резервной копии выберите один из следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="a7c76-113">To specify a backup destination, choose one of the following options.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a7c76-114">**Имя файла**</span><span class="sxs-lookup"><span data-stu-id="a7c76-114">**File name**</span></span>|<span data-ttu-id="a7c76-115">Выберите этот параметр и введите в текстовом поле локальный или удаленный файл как место расположения резервной копии.</span><span class="sxs-lookup"><span data-stu-id="a7c76-115">Choose this option to enter a local or remote file as the backup destination in the text box.</span></span><br /><br /> <span data-ttu-id="a7c76-116">Чтобы указать локальный файл, нажмите кнопку обзора справа от текстового поля и перейдите к файлу на фиксированных дисках компьютера, на котором выполняется сервер, или введите полный путь и имя файла напрямую. Например, `C:\Program Files\Microsoft SQL Server\MSSQL\Backup\AdventureWorksBackup.bak` .</span><span class="sxs-lookup"><span data-stu-id="a7c76-116">To specify a local file, click the browse button to the right of the text box and navigate to a file on the fixed drives of the computer running the server, or enter the full path and file name directly; for example, `C:\Program Files\Microsoft SQL Server\MSSQL\Backup\AdventureWorksBackup.bak`.</span></span><br /><br /> <span data-ttu-id="a7c76-117">Для указания удаленного файла в качестве места расположения резервной копии введите полное имя файла в формате UNC.</span><span class="sxs-lookup"><span data-stu-id="a7c76-117">To specify a remote file as your backup destination, enter its fully qualified universal naming convention (UNC) name.</span></span> <span data-ttu-id="a7c76-118">Дополнительные сведения см. в разделе [Устройства резервного копирования (SQL Server)](backup-devices-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="a7c76-118">For more information, see [Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md).</span></span><br /><br /> <span data-ttu-id="a7c76-119">**\*\* Важная информация. \*\*** В случае резервного копирования данных по сети могут произойти сетевые ошибки. Поэтому по его завершении рекомендуется сделать проверку.</span><span class="sxs-lookup"><span data-stu-id="a7c76-119">**\*\* Important \*\*** Backing up data over a network can be subject to network errors; therefore, we recommend that you verify the backup operation after it finishes.</span></span> <span data-ttu-id="a7c76-120">Дополнительные сведения см. в разделе [RESTORE VERIFYONLY (Transact-SQL)](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a7c76-120">For more information, see [RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql).</span></span>|  
|<span data-ttu-id="a7c76-121">**устройство резервного копирования;**</span><span class="sxs-lookup"><span data-stu-id="a7c76-121">**Backup device**</span></span>|<span data-ttu-id="a7c76-122">Выберите этот параметр для выбора логического устройства резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="a7c76-122">Choose this option to select a logical backup device.</span></span><br /><br /> <span data-ttu-id="a7c76-123">Примечание. Дополнительные сведения о создании дискового устройства резервного копирования см. в разделе [Определение логического устройства резервного копирования для дискового файла (SQL Server)](define-a-logical-backup-device-for-a-disk-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="a7c76-123">Note: For information about how to create a disk backup device, see [Define a Logical Backup Device for a Disk File &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-disk-file-sql-server.md).</span></span>|  
  
 <span data-ttu-id="a7c76-124">**Место назначения на ленте**</span><span class="sxs-lookup"><span data-stu-id="a7c76-124">**Destination on tape**</span></span>  
 <span data-ttu-id="a7c76-125">В качестве места расположения резервной копии выберите ленточный накопитель, физически подключенный к компьютеру, на котором находится сервер (экземпляр компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="a7c76-125">Specify a backup destination on a tape drive physically connected to the computer running the server (that is, the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)]).</span></span> <span data-ttu-id="a7c76-126">Выберите один из следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="a7c76-126">Choose one of the following options.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a7c76-127">**Ленточный накопитель**</span><span class="sxs-lookup"><span data-stu-id="a7c76-127">**Tape drive**</span></span>|<span data-ttu-id="a7c76-128">Выберите этот параметр, чтобы в качестве места расположения резервной копии выбрать накопитель на магнитной ленте из списка ленточных накопителей, физически подключенных к компьютеру, на котором находится экземпляр сервера.</span><span class="sxs-lookup"><span data-stu-id="a7c76-128">Choose this option to select a tape drive as the backup destination from the list of tape drives that are physically connected to the computer that is running the server instance.</span></span><br /><br /> <span data-ttu-id="a7c76-129">Примечание. Устройства резервного копирования на магнитных лентах на удаленных компьютерах не могут указываться в качестве места назначения резервной копии.</span><span class="sxs-lookup"><span data-stu-id="a7c76-129">Note: Tape backup devices on remote computers are not valid backup destinations.</span></span>|  
|<span data-ttu-id="a7c76-130">**устройство резервного копирования;**</span><span class="sxs-lookup"><span data-stu-id="a7c76-130">**Backup device**</span></span>|<span data-ttu-id="a7c76-131">Выберите этот параметр для выбора существующего логического устройства резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="a7c76-131">Choose this option to select an existing logical backup device.</span></span> <span data-ttu-id="a7c76-132">Эти логические устройства соответствуют ленточным накопителям, физически подключенным к компьютеру, на котором находится экземпляр сервера.</span><span class="sxs-lookup"><span data-stu-id="a7c76-132">These logical backup devices correspond to tape drives that are physically connected to the computer that is running the server instance.</span></span><br /><br /> <span data-ttu-id="a7c76-133">Примечание. Дополнительные сведения о создании ленточного устройства резервного копирования см. в разделе [Определение логического устройства резервного копирования для ленточного накопителя (SQL Server)](define-a-logical-backup-device-for-a-tape-drive-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="a7c76-133">Note: For information about how to create a tape backup device, see [Define a Logical Backup Device for a Tape Drive &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-tape-drive-sql-server.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a7c76-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="a7c76-134">See Also</span></span>  
 <span data-ttu-id="a7c76-135">[Устройства резервного копирования (SQL Server)](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a7c76-135">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 [<span data-ttu-id="a7c76-136">Наборы носителей, семейства носителей и резервные наборы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a7c76-136">Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
  
  
