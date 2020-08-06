---
title: Выбор устройства резервного копирования | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.selectbackupdevice.f1
ms.assetid: 7887c9fd-15ce-4cc8-b069-845c1d09088c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8a848f9188eec0ebb09931bca460b0389b9570ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736419"
---
# <a name="select-backup-device"></a><span data-ttu-id="51aef-102">Выбор устройства резервного копирования</span><span class="sxs-lookup"><span data-stu-id="51aef-102">Select Backup Device</span></span>
  <span data-ttu-id="51aef-103">Используйте диалоговое окно **Выбор устройства резервного копирования** , чтобы выбрать логическое устройство резервного копирования для операции восстановления.</span><span class="sxs-lookup"><span data-stu-id="51aef-103">Use the **Select Backup Device** dialog box to select a logical backup device for the restore operation.</span></span>  
  
 <span data-ttu-id="51aef-104">Логическим устройством резервного копирования является определяемое пользователем логическое устройство, которое относится к физическим устройствам, или ленточный накопитель, или дисковый накопитель, предоставляемый операционной системой.</span><span class="sxs-lookup"><span data-stu-id="51aef-104">A logical backup device is a user-defined logical device that corresponds to a physical device, either a tape drive or a disk drive, that is provided by the operating system.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="51aef-105">Если несколько устройств резервного копирования используется для выполнения операции резервного копирования, все они должны соответствовать одному типу устройства.</span><span class="sxs-lookup"><span data-stu-id="51aef-105">If a backup uses multiple backup devices, they all must correspond to a single type of device.</span></span>  
  
 <span data-ttu-id="51aef-106">**Использование среды SQL Server Management Studio для просмотра содержимого устройства резервного копирования**</span><span class="sxs-lookup"><span data-stu-id="51aef-106">**To use SQL Server Management Studio to view the contents of a backup device**</span></span>  
  
-   [<span data-ttu-id="51aef-107">Просмотр содержимого ленты или файла резервной копии (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="51aef-107">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="51aef-108">Просмотр свойств и содержимого логического устройства резервного копирования (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="51aef-108">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
## <a name="options"></a><span data-ttu-id="51aef-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="51aef-109">Options</span></span>  
 <span data-ttu-id="51aef-110">**устройство резервного копирования;**</span><span class="sxs-lookup"><span data-stu-id="51aef-110">**Backup device**</span></span>  
 <span data-ttu-id="51aef-111">В окне списка выберите имя устройства резервного копирования, с которого необходимо произвести восстановление.</span><span class="sxs-lookup"><span data-stu-id="51aef-111">In the list box, select the name of a logical backup device from which you want to restore.</span></span>  
  
 <span data-ttu-id="51aef-112">Сведения о просмотре содержимого устройства резервного копирования см. в разделе [Просмотр свойств и содержимого логического устройства резервного копирования (SQL Server)](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="51aef-112">For information about how to view the contents of a backup device, see [View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51aef-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="51aef-113">Remarks</span></span>  
 <span data-ttu-id="51aef-114">Если не отображается логическое устройство резервного копирования, содержащее необходимую резервную копию, резервная копия может быть записана прямо на один или более дисковых накопителей или ленточных накопителей.</span><span class="sxs-lookup"><span data-stu-id="51aef-114">If you do not see a logical backup device that contains the backup you are seeking on the list, the backup might have been written directly to one or more files or tape drives.</span></span> <span data-ttu-id="51aef-115">В таком случае закройте диалоговое окно **Выбор устройства резервного копирования** и в диалоговом окне **Указание резервной копии** выберите **Файл** или **Лента** в окне списка **Носитель резервной копии** .</span><span class="sxs-lookup"><span data-stu-id="51aef-115">If this is the case, cancel the **Select Backup Device** dialog box; and in the **Specify Backup** dialog box, select **File** or **Tape** in the **Backup media** list box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51aef-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="51aef-116">See Also</span></span>  
 [<span data-ttu-id="51aef-117">Устройства резервного копирования (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="51aef-117">Backup Devices &#40;SQL Server&#41;</span></span>](backup-devices-sql-server.md)  
  
  
