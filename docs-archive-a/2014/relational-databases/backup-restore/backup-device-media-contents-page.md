---
title: Устройство резервного копирования (страница "Содержимое носителя") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.backupdevice.contents.f1
ms.assetid: 5fc7bd22-b6d8-4af1-8a58-2e7d0b994d08
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 07204b5e05ce9fc17e6ea23450066f9f58b7cf87
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664953"
---
# <a name="backup-device-media-contents-page"></a><span data-ttu-id="d3de6-102">Устройство резервного копирования (страница «Содержимое носителя»)</span><span class="sxs-lookup"><span data-stu-id="d3de6-102">Backup Device (Media Contents Page)</span></span>
  <span data-ttu-id="d3de6-103">Используйте диалоговое окно **Устройство резервного копирования** для просмотра сведений о резервной копии.</span><span class="sxs-lookup"><span data-stu-id="d3de6-103">Use the **Backup Device** dialog box to view the backup information.</span></span> <span data-ttu-id="d3de6-104">Сюда входят сведения об устройстве, носителе, наборе носителей, а также резервном наборе (наборах) данных.</span><span class="sxs-lookup"><span data-stu-id="d3de6-104">This information describes the device, the media, the media set, and the backup set or sets.</span></span>  
  
 <span data-ttu-id="d3de6-105">**Использование среды SQL Server Management Studio для просмотра содержимого устройства резервного копирования**</span><span class="sxs-lookup"><span data-stu-id="d3de6-105">**To use SQL Server Management Studio to view the contents of a backup device**</span></span>  
  
-   [<span data-ttu-id="d3de6-106">Просмотр содержимого ленты или файла резервной копии (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d3de6-106">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="d3de6-107">Просмотр свойств и содержимого логического устройства резервного копирования (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d3de6-107">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
## <a name="options"></a><span data-ttu-id="d3de6-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="d3de6-108">Options</span></span>  
 <span data-ttu-id="d3de6-109">Сведения об отдельном носителе, наборе носителей и резервных наборах данных.</span><span class="sxs-lookup"><span data-stu-id="d3de6-109">View information about the individual media, media set, and backup sets.</span></span>  
  
 <span data-ttu-id="d3de6-110">**Носитель**</span><span class="sxs-lookup"><span data-stu-id="d3de6-110">**Media**</span></span>  
 <span data-ttu-id="d3de6-111">Диск или набор носителей на магнитных лентах, где хранятся резервные данные.</span><span class="sxs-lookup"><span data-stu-id="d3de6-111">A disk or set of tapes on which backup information is stored.</span></span>  
  
 <span data-ttu-id="d3de6-112">**Порядок носителей**</span><span class="sxs-lookup"><span data-stu-id="d3de6-112">**Media sequence**</span></span>  
 <span data-ttu-id="d3de6-113">Список содержит порядковый номер носителя, порядковый номер семейства и идентификатор зеркального сервера, если такой существует.</span><span class="sxs-lookup"><span data-stu-id="d3de6-113">Lists the media sequence number, the family sequence number, and the mirror identifier, if any.</span></span> <span data-ttu-id="d3de6-114">Для каждого физического носителя данных резервных копий указан порядковый номер, отражающий поcледовательность, в которой использовались носители.</span><span class="sxs-lookup"><span data-stu-id="d3de6-114">The physical backup media are each tagged with a media sequence number that indicates the order in which the media were used.</span></span> <span data-ttu-id="d3de6-115">Первый носитель резервной копии обозначен цифрой 1, второй (первая дополнительная лента) обозначен цифрой 2 и т. д.</span><span class="sxs-lookup"><span data-stu-id="d3de6-115">The initial backup media is tagged with 1, the second (the first continuation tape) is tagged with 2, and so forth.</span></span> <span data-ttu-id="d3de6-116">При восстановлении из резервного набора данных наличие порядковых номеров носителей позволяет гарантировать, что оператор, выполняющий восстановление, монтирует носители в правильном порядке.</span><span class="sxs-lookup"><span data-stu-id="d3de6-116">When the backup set is restored, the media sequence numbers ensure that the operator restoring the backup mounts the correct media in the correct order.</span></span>  
  
 <span data-ttu-id="d3de6-117">**Создан**</span><span class="sxs-lookup"><span data-stu-id="d3de6-117">**Created on**</span></span>  
 <span data-ttu-id="d3de6-118">Дата и время создания набора носителей.</span><span class="sxs-lookup"><span data-stu-id="d3de6-118">Displays the creation date and time of the media set.</span></span>  
  
 <span data-ttu-id="d3de6-119">**Набор носителей**</span><span class="sxs-lookup"><span data-stu-id="d3de6-119">**Media Set**</span></span>  
 <span data-ttu-id="d3de6-120">Набор носителей — это упорядоченная коллекция носителей резервных копий, куда выполнялась запись одной или нескольких операций резервного копирования с применением постоянного числа устройств резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="d3de6-120">A media set is an ordered collection of backup media to which one or more backup operations have written by using a constant number of backup devices.</span></span>  
  
 <span data-ttu-id="d3de6-121">**имя**;</span><span class="sxs-lookup"><span data-stu-id="d3de6-121">**Name**</span></span>  
 <span data-ttu-id="d3de6-122">Имя набора носителей, если оно есть.</span><span class="sxs-lookup"><span data-stu-id="d3de6-122">Displays the name of the media set, if any.</span></span>  
  
 <span data-ttu-id="d3de6-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="d3de6-123">**Description**</span></span>  
 <span data-ttu-id="d3de6-124">Описание набора носителей, если оно есть.</span><span class="sxs-lookup"><span data-stu-id="d3de6-124">Displays the description of the media set, if any.</span></span>  
  
 <span data-ttu-id="d3de6-125">**Счетчик семейства носителей**</span><span class="sxs-lookup"><span data-stu-id="d3de6-125">**Media family count**</span></span>  
 <span data-ttu-id="d3de6-126">Количество семейств в наборе носителей.</span><span class="sxs-lookup"><span data-stu-id="d3de6-126">Displays the number of families in the media set.</span></span> <span data-ttu-id="d3de6-127">Каждый набор носителей представляет собой коллекцию из одного или нескольких семейств носителей.</span><span class="sxs-lookup"><span data-stu-id="d3de6-127">Each media set is a collection of one or more media families.</span></span> <span data-ttu-id="d3de6-128">Все выходные данные для отдельно взятого устройства резервного копирования (или группы зеркальных устройств резервного копирования) образуют одно семейство носителей.</span><span class="sxs-lookup"><span data-stu-id="d3de6-128">All the output to a given single backup device (or group of mirrored backup devices) forms a single media family.</span></span> <span data-ttu-id="d3de6-129">Каждый набор носителей содержит по одному семейству носителей на каждое отдельное устройство (или группу зеркальных устройств). Например, если набор носителей использует два незеркальных устройства резервного копирования, он содержит два семейства носителей.</span><span class="sxs-lookup"><span data-stu-id="d3de6-129">Each media set contains one media family per separate device (or group of mirrored devices); for instance, if a media set uses two non-mirrored backup devices, the media set contains two media families.</span></span>  
  
 <span data-ttu-id="d3de6-130">**Резервные наборы данных**</span><span class="sxs-lookup"><span data-stu-id="d3de6-130">**Backup sets**</span></span>  
 <span data-ttu-id="d3de6-131">Показывает сведения об одном или нескольких резервных наборах данных, содержащихся на носителе.</span><span class="sxs-lookup"><span data-stu-id="d3de6-131">Displays information about the backup set or sets contained on the media.</span></span> <span data-ttu-id="d3de6-132">Резервный набор данных — результат успешной операции резервного копирования. Содержимое этого набора распределено по носителям набора устройств резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="d3de6-132">A backup set is the result of a successful backup operation, whose content is distributed among the media on the set of backup devices.</span></span>  
  
|<span data-ttu-id="d3de6-133">Заголовок</span><span class="sxs-lookup"><span data-stu-id="d3de6-133">Header</span></span>|<span data-ttu-id="d3de6-134">Значения</span><span class="sxs-lookup"><span data-stu-id="d3de6-134">Values</span></span>|  
|------------|------------|  
|<span data-ttu-id="d3de6-135">**имя**;</span><span class="sxs-lookup"><span data-stu-id="d3de6-135">**Name**</span></span>|<span data-ttu-id="d3de6-136">Имя резервного набора данных.</span><span class="sxs-lookup"><span data-stu-id="d3de6-136">The name of the backup set.</span></span>|  
|<span data-ttu-id="d3de6-137">**Тип**</span><span class="sxs-lookup"><span data-stu-id="d3de6-137">**Type**</span></span>|<span data-ttu-id="d3de6-138">Объект, сохраненный в резервной копии: база данных, файл или *\<blank>* (для журналов транзакций).</span><span class="sxs-lookup"><span data-stu-id="d3de6-138">The backed-up object: Database, File, or *\<blank>* (for transaction logs).</span></span>|  
|<span data-ttu-id="d3de6-139">**Компонент**</span><span class="sxs-lookup"><span data-stu-id="d3de6-139">**Component**</span></span>|<span data-ttu-id="d3de6-140">Тип выполняемого резервного копирования: полное, разностное или резервное копирование журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="d3de6-140">The type of backup performed: Full, Differential or Transaction Log.</span></span>|  
|<span data-ttu-id="d3de6-141">**Server**</span><span class="sxs-lookup"><span data-stu-id="d3de6-141">**Server**</span></span>|<span data-ttu-id="d3de6-142">Имя экземпляра компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] , выполнившего операцию резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="d3de6-142">The name of the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] that performed the backup operation.</span></span>|  
|<span data-ttu-id="d3de6-143">**База данных**</span><span class="sxs-lookup"><span data-stu-id="d3de6-143">**Database**</span></span>|<span data-ttu-id="d3de6-144">Имя базы данных, резервная копия которой была сделана.</span><span class="sxs-lookup"><span data-stu-id="d3de6-144">The name of the database that was backed up.</span></span>|  
|<span data-ttu-id="d3de6-145">**Положение**</span><span class="sxs-lookup"><span data-stu-id="d3de6-145">**Position**</span></span>|<span data-ttu-id="d3de6-146">Расположение резервного набора данных в томе.</span><span class="sxs-lookup"><span data-stu-id="d3de6-146">The position of the backup set in the volume.</span></span>|  
|<span data-ttu-id="d3de6-147">**Дата**</span><span class="sxs-lookup"><span data-stu-id="d3de6-147">**Date**</span></span>|<span data-ttu-id="d3de6-148">Дата и время завершения операции резервного копирования, указанные в формате, соответствующем региональным настройкам клиента.</span><span class="sxs-lookup"><span data-stu-id="d3de6-148">The date and time when the backup operation finished, presented in the regional setting of the client.</span></span>|  
|<span data-ttu-id="d3de6-149">**Размер**</span><span class="sxs-lookup"><span data-stu-id="d3de6-149">**Size**</span></span>|<span data-ttu-id="d3de6-150">Размер резервного набора данных в байтах.</span><span class="sxs-lookup"><span data-stu-id="d3de6-150">The size of the backup set in bytes.</span></span>|  
|<span data-ttu-id="d3de6-151">**Имя пользователя**</span><span class="sxs-lookup"><span data-stu-id="d3de6-151">**User Name**</span></span>|<span data-ttu-id="d3de6-152">Имя пользователя, выполнившего операцию резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="d3de6-152">The name of the user who performed the backup operation.</span></span>|  
|<span data-ttu-id="d3de6-153">**Истечение срока**</span><span class="sxs-lookup"><span data-stu-id="d3de6-153">**Expiration**</span></span>|<span data-ttu-id="d3de6-154">Дата и время истечения срока действия резервного набора данных.</span><span class="sxs-lookup"><span data-stu-id="d3de6-154">The date and time the backup set expires.</span></span>|  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="d3de6-155">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="d3de6-155">Related Tasks</span></span>  
  
-   [<span data-ttu-id="d3de6-156">Определение логического устройства резервного копирования для дискового файла (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d3de6-156">Define a Logical Backup Device for a Disk File &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-disk-file-sql-server.md)  
  
-   [<span data-ttu-id="d3de6-157">Определение логического устройства резервного копирования для ленточного накопителя (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d3de6-157">Define a Logical Backup Device for a Tape Drive &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-tape-drive-sql-server.md)  
  
-   [<span data-ttu-id="d3de6-158">Указание в качестве назначения резервного копирования диска или ленты (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d3de6-158">Specify a Disk or Tape As a Backup Destination &#40;SQL Server&#41;</span></span>](specify-a-disk-or-tape-as-a-backup-destination-sql-server.md)  
  
-   [<span data-ttu-id="d3de6-159">Удаление устройства резервного копирования (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d3de6-159">Delete a Backup Device &#40;SQL Server&#41;</span></span>](delete-a-backup-device-sql-server.md)  
  
-   [<span data-ttu-id="d3de6-160">Назначение срока хранения резервной копии (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d3de6-160">Set the Expiration Date on a Backup &#40;SQL Server&#41;</span></span>](set-the-expiration-date-on-a-backup-sql-server.md)  
  
-   [<span data-ttu-id="d3de6-161">Просмотр содержимого ленты или файла резервной копии (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d3de6-161">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="d3de6-162">Просмотр файлов данных и журналов в резервном наборе данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d3de6-162">View the Data and Log Files in a Backup Set &#40;SQL Server&#41;</span></span>](view-the-data-and-log-files-in-a-backup-set-sql-server.md)  
  
-   [<span data-ttu-id="d3de6-163">Просмотр свойств и содержимого логического устройства резервного копирования (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d3de6-163">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
-   [<span data-ttu-id="d3de6-164">Восстановление резервной копии с устройства (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d3de6-164">Restore a Backup from a Device &#40;SQL Server&#41;</span></span>](restore-a-backup-from-a-device-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="d3de6-165">См. также:</span><span class="sxs-lookup"><span data-stu-id="d3de6-165">See Also</span></span>  
 <span data-ttu-id="d3de6-166">[Устройства резервного копирования (SQL Server)](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d3de6-166">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 [<span data-ttu-id="d3de6-167">Наборы носителей, семейства носителей и резервные наборы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d3de6-167">Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
  
  
