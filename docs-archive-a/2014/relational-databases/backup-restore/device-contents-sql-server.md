---
title: Содержимое устройства (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.bnrdevicecontents.f1
ms.assetid: 95e1902e-8c7a-4830-bdf9-1a6aca414a24
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c904718eca671b1965a95d0d400f3f6fa075b500
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658848"
---
# <a name="device-contents-sql-server"></a><span data-ttu-id="6805c-102">Содержимое устройства (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="6805c-102">Device Contents (SQL Server)</span></span>
  <span data-ttu-id="6805c-103">При помощи этого диалогового окна можно посмотреть сведения о резервном копировании.</span><span class="sxs-lookup"><span data-stu-id="6805c-103">Use this dialog box to view the backup information.</span></span> <span data-ttu-id="6805c-104">Сюда входят сведения об устройстве, носителе, наборе носителей, а также резервном наборе (наборах) данных.</span><span class="sxs-lookup"><span data-stu-id="6805c-104">This information describes the device, the media, the media set, and the backup set or sets.</span></span>  
  
 <span data-ttu-id="6805c-105">**Использование среды SQL Server Management Studio для просмотра содержимого устройства резервного копирования**</span><span class="sxs-lookup"><span data-stu-id="6805c-105">**To use SQL Server Management Studio to view the contents of a backup device**</span></span>  
  
-   [<span data-ttu-id="6805c-106">Просмотр содержимого ленты или файла резервной копии (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="6805c-106">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="6805c-107">Просмотр свойств и содержимого логического устройства резервного копирования (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="6805c-107">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
## <a name="options"></a><span data-ttu-id="6805c-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="6805c-108">Options</span></span>  
 <span data-ttu-id="6805c-109">**Носитель**</span><span class="sxs-lookup"><span data-stu-id="6805c-109">**Media**</span></span>  
 <span data-ttu-id="6805c-110">Диск или набор носителей на магнитных лентах, где хранятся резервные данные.</span><span class="sxs-lookup"><span data-stu-id="6805c-110">A disk or set of tapes on which backup information is stored.</span></span>  
  
 <span data-ttu-id="6805c-111">**Порядок носителей**</span><span class="sxs-lookup"><span data-stu-id="6805c-111">**Media sequence**</span></span>  
 <span data-ttu-id="6805c-112">Список содержит порядковый номер носителя, порядковый номер семейства и идентификатор зеркального сервера, если такой существует.</span><span class="sxs-lookup"><span data-stu-id="6805c-112">Lists the media sequence number, the family sequence number, and the mirror identifier, if any.</span></span> <span data-ttu-id="6805c-113">Для каждого физического носителя данных резервных копий указан порядковый номер, отражающий поcледовательность, в которой использовались носители.</span><span class="sxs-lookup"><span data-stu-id="6805c-113">The physical backup media are each tagged with a media sequence number that indicates the order in which the media were used.</span></span> <span data-ttu-id="6805c-114">Первый носитель данных резервных копий обозначен цифрой 1, второй (первая дополнительная лента) обозначен цифрой 2 и т. д.</span><span class="sxs-lookup"><span data-stu-id="6805c-114">The initial backup medium is tagged with 1, the second (the first continuation tape) is tagged with 2, and so forth.</span></span> <span data-ttu-id="6805c-115">При восстановлении из резервного набора данных наличие порядковых номеров носителей позволяет гарантировать, что оператор, выполняющий восстановление, подключает носители в правильном порядке.</span><span class="sxs-lookup"><span data-stu-id="6805c-115">When the backup set is restored, the media sequence numbers ensure that the operator that restores the backup mounts the correct media in the correct order.</span></span>  
  
 <span data-ttu-id="6805c-116">**Создан**</span><span class="sxs-lookup"><span data-stu-id="6805c-116">**Created on**</span></span>  
 <span data-ttu-id="6805c-117">Показывает дату записи носителя.</span><span class="sxs-lookup"><span data-stu-id="6805c-117">Displays the media date.</span></span>  
  
 <span data-ttu-id="6805c-118">**Набор носителей**</span><span class="sxs-lookup"><span data-stu-id="6805c-118">**Media Set**</span></span>  
 <span data-ttu-id="6805c-119">Набор носителей представляет собой коллекцию носителей резервной копии, записанной в процессе одной или более операций резервного копирования с использованием постоянного числа устройств резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="6805c-119">A media set is an ordered collection of backup media to which one or more backup operations have written using a constant number of backup devices.</span></span>  
  
 <span data-ttu-id="6805c-120">**имя**;</span><span class="sxs-lookup"><span data-stu-id="6805c-120">**Name**</span></span>  
 <span data-ttu-id="6805c-121">Отображает имя набора носителей.</span><span class="sxs-lookup"><span data-stu-id="6805c-121">Displays the name of the media set.</span></span>  
  
 <span data-ttu-id="6805c-122">**Описание**</span><span class="sxs-lookup"><span data-stu-id="6805c-122">**Description**</span></span>  
 <span data-ttu-id="6805c-123">Отображает набор носителей описания.</span><span class="sxs-lookup"><span data-stu-id="6805c-123">Displays the description media set.</span></span>  
  
 <span data-ttu-id="6805c-124">**Счетчик семейства носителей**</span><span class="sxs-lookup"><span data-stu-id="6805c-124">**Media family count**</span></span>  
 <span data-ttu-id="6805c-125">Отображает счетчик семейства носителей.</span><span class="sxs-lookup"><span data-stu-id="6805c-125">Displays the media family count.</span></span> <span data-ttu-id="6805c-126">Каждый набор носителей представляет собой коллекцию из одного или нескольких семейств носителей.</span><span class="sxs-lookup"><span data-stu-id="6805c-126">Each media set is a collection of one or more media families.</span></span> <span data-ttu-id="6805c-127">Все выходные данные для отдельно взятого устройства резервного копирования (или группы зеркальных устройств резервного копирования) образуют одно семейство носителей.</span><span class="sxs-lookup"><span data-stu-id="6805c-127">All the output to a given single backup device (or group of mirrored backup devices) forms a single media family.</span></span> <span data-ttu-id="6805c-128">Каждый набор носителей содержит одно семейство носителей на каждое отдельное устройство (или группу зеркальных устройств резервного копирования). Например, если набор носителей использует два незеркальных устройства резервного копирования, то в нем содержатся два семейства носителей.</span><span class="sxs-lookup"><span data-stu-id="6805c-128">Each media set contains one media family per separate device (or group of mirrored devices); for example, if a media set uses two nonmirrored backup devices, the media set contains two media families.</span></span>  
  
 <span data-ttu-id="6805c-129">**Резервные наборы данных**</span><span class="sxs-lookup"><span data-stu-id="6805c-129">**Backup sets**</span></span>  
 <span data-ttu-id="6805c-130">Показывает сведения об одном или нескольких резервных наборах данных, содержащихся на носителе.</span><span class="sxs-lookup"><span data-stu-id="6805c-130">Displays information about the backup set or sets contained on the media.</span></span> <span data-ttu-id="6805c-131">Резервный набор данных представляет собой результат успешного завершения операции резервного копирования, чье содержимое распределяется на носителе в наборе устройств резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="6805c-131">A backup set is the result of a successful backup operation whose content is distributed among the media on the set of backup devices.</span></span>  
  
|<span data-ttu-id="6805c-132">Заголовок</span><span class="sxs-lookup"><span data-stu-id="6805c-132">Header</span></span>|<span data-ttu-id="6805c-133">Значения</span><span class="sxs-lookup"><span data-stu-id="6805c-133">Values</span></span>|  
|------------|------------|  
|<span data-ttu-id="6805c-134">**имя**;</span><span class="sxs-lookup"><span data-stu-id="6805c-134">**Name**</span></span>|<span data-ttu-id="6805c-135">Имя резервного набора данных.</span><span class="sxs-lookup"><span data-stu-id="6805c-135">The name of the backup set.</span></span>|  
|<span data-ttu-id="6805c-136">**Тип**</span><span class="sxs-lookup"><span data-stu-id="6805c-136">**Type**</span></span>|<span data-ttu-id="6805c-137">Тип выполняемого резервного копирования: полное, разностное или резервное копирование журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="6805c-137">The type of backup performed: Full, Differential or Transaction Log.</span></span>|  
|<span data-ttu-id="6805c-138">**Компонент**</span><span class="sxs-lookup"><span data-stu-id="6805c-138">**Component**</span></span>|<span data-ttu-id="6805c-139">Компонент, сохраненный в резервной копии: база данных, файл или *\<blank>* (для журналов транзакций).</span><span class="sxs-lookup"><span data-stu-id="6805c-139">The backed-up component: Database, File, or *\<blank>* (for transaction logs).</span></span>|  
|<span data-ttu-id="6805c-140">**Server**</span><span class="sxs-lookup"><span data-stu-id="6805c-140">**Server**</span></span>|<span data-ttu-id="6805c-141">Имя экземпляра компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] , выполнившего операцию резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="6805c-141">The name of the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] that performed the backup operation.</span></span>|  
|<span data-ttu-id="6805c-142">**База данных**</span><span class="sxs-lookup"><span data-stu-id="6805c-142">**Database**</span></span>|<span data-ttu-id="6805c-143">Имя базы данных, резервная копия которой была сделана.</span><span class="sxs-lookup"><span data-stu-id="6805c-143">The name of the database that was backed up.</span></span>|  
|<span data-ttu-id="6805c-144">**Положение**</span><span class="sxs-lookup"><span data-stu-id="6805c-144">**Position**</span></span>|<span data-ttu-id="6805c-145">Расположение резервного набора данных в томе.</span><span class="sxs-lookup"><span data-stu-id="6805c-145">The position of the backup set in the volume.</span></span>|  
|<span data-ttu-id="6805c-146">**Дата**</span><span class="sxs-lookup"><span data-stu-id="6805c-146">**Date**</span></span>|<span data-ttu-id="6805c-147">Дата и время завершения операции резервного копирования, указанные в формате, соответствующем региональным настройкам клиента.</span><span class="sxs-lookup"><span data-stu-id="6805c-147">The date and time when the backup operation finished, presented in the regional setting of the client.</span></span>|  
|<span data-ttu-id="6805c-148">**Размер**</span><span class="sxs-lookup"><span data-stu-id="6805c-148">**Size**</span></span>|<span data-ttu-id="6805c-149">Размер резервного набора данных в байтах.</span><span class="sxs-lookup"><span data-stu-id="6805c-149">The size of the backup set in bytes.</span></span>|  
|<span data-ttu-id="6805c-150">**Имя пользователя**</span><span class="sxs-lookup"><span data-stu-id="6805c-150">**User Name**</span></span>|<span data-ttu-id="6805c-151">Имя пользователя, выполнившего операцию резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="6805c-151">The name of the user who performed the backup operation.</span></span>|  
|<span data-ttu-id="6805c-152">**Истечение срока**</span><span class="sxs-lookup"><span data-stu-id="6805c-152">**Expiration**</span></span>|<span data-ttu-id="6805c-153">Дата и время истечения срока действия резервного набора данных.</span><span class="sxs-lookup"><span data-stu-id="6805c-153">The date and time the backup set expires.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6805c-154">См. также:</span><span class="sxs-lookup"><span data-stu-id="6805c-154">See Also</span></span>  
 [<span data-ttu-id="6805c-155">Наборы носителей, семейства носителей и резервные наборы данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="6805c-155">Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
  
  
