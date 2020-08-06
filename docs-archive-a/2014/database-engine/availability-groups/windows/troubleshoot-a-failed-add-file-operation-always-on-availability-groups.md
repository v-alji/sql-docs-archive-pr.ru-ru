---
title: Устранение неполадок при выполнении операции добавления файла (группы доступности AlwaysOn) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- secondary databases [SQL Server], Availability Groups
- Availability Groups [SQL Server], troubleshooting
ms.assetid: 31ceaebf-864b-4dd0-9112-0d047b0316ad
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2551080c214f18473caa71a3e17797c34fcc943a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750168"
---
# <a name="troubleshoot-a-failed-add-file-operation-alwayson-availability-groups"></a><span data-ttu-id="dd9b7-102">Устранение неполадок с операцией добавления файла, давшей сбой (группы доступности AlwaysOn)</span><span class="sxs-lookup"><span data-stu-id="dd9b7-102">Troubleshoot a Failed Add-File Operation (AlwaysOn Availability Groups)</span></span>
  <span data-ttu-id="dd9b7-103">В некоторых развертываниях групп доступности AlwaysOn различаются пути в системах, где размещена первичная реплика и где размещена вторичная реплика.</span><span class="sxs-lookup"><span data-stu-id="dd9b7-103">In some AlwaysOn availability group deployments, file paths differ between the system that hosts the primary replica and systems that host a secondary replica.</span></span> <span data-ttu-id="dd9b7-104">Если путь к файлу операции добавления файла во вторичной реплике не существует, то будет выполнена успешно операция добавления файлов в базе данных-источнике.</span><span class="sxs-lookup"><span data-stu-id="dd9b7-104">If the file path of an add-file operation does not exist on a secondary replica, the add-file operation will succeed on the primary database.</span></span> <span data-ttu-id="dd9b7-105">Однако операция добавления файла приводит к приостановке базы данных-получателя.</span><span class="sxs-lookup"><span data-stu-id="dd9b7-105">But the add-file operation will cause the secondary database to be suspended.</span></span> <span data-ttu-id="dd9b7-106">Это, в свою очередь, вызовет переход дополнительной реплики в состояние NOT SYNCHRONIZING.</span><span class="sxs-lookup"><span data-stu-id="dd9b7-106">This, in turn, causes the secondary replica to enter the NOT SYNCHRONIZING state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dd9b7-107">Рекомендуется, чтобы при возможности путь к файлам (в том числе буква диска) базы данных-получателя совпадала с путем соответствующей базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="dd9b7-107">We recommend that, if possible, the file path (including the drive letter) of a given secondary database be identical to the path of the corresponding primary database.</span></span>  
  
## <a name="problem-resolution"></a><span data-ttu-id="dd9b7-108">Решение проблем</span><span class="sxs-lookup"><span data-stu-id="dd9b7-108">Problem Resolution</span></span>  
 <span data-ttu-id="dd9b7-109">Чтобы разрешить эту проблему, владелец базы данных должен выполнить следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="dd9b7-109">To resolve this problem the database owner must complete the following steps:</span></span>  
  
1.  <span data-ttu-id="dd9b7-110">Удалите базу данных-получатель из группы доступности.</span><span class="sxs-lookup"><span data-stu-id="dd9b7-110">Remove the secondary database from the availability group.</span></span> <span data-ttu-id="dd9b7-111">Дополнительные сведения см. в разделе [Удаление базы данных-получателя из группы доступности (SQL Server)](remove-a-secondary-database-from-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="dd9b7-111">For more information, see [Remove a Secondary Database from an Availability Group &#40;SQL Server&#41;](remove-a-secondary-database-from-an-availability-group-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="dd9b7-112">В существующей базе данных-получателе выполните восстановление полной резервной копии файловой группы, содержащей файл, добавленный в базу данных-получатель, применив параметры WITH NORECOVERY и WITH MOVE (задав путь файла на экземпляре сервера, на котором размещена дополнительная реплика).</span><span class="sxs-lookup"><span data-stu-id="dd9b7-112">On the existing secondary database, restore a full backup of the filegroup that contains the added file to the secondary database, using WITH NORECOVERY and WITH MOVE (specifying the file path on the server instance that hosts the secondary replica).</span></span> <span data-ttu-id="dd9b7-113">Дополнительные сведения см. в разделе [Восстановление базы данных в новое расположение (SQL Server)](../../../relational-databases/backup-restore/restore-a-database-to-a-new-location-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="dd9b7-113">For more information, see [Restore a Database to a New Location &#40;SQL Server&#41;](../../../relational-databases/backup-restore/restore-a-database-to-a-new-location-sql-server.md).</span></span>  
  
3.  <span data-ttu-id="dd9b7-114">Создайте резервную копию журнала транзакций, содержащего операцию добавления файла, в базе данных-источнике и вручную восстановите эту резервную копию журналов в базе данных-получателе с помощью параметров WITH NORECOVERY и WITH MOVE.</span><span class="sxs-lookup"><span data-stu-id="dd9b7-114">Back up the transaction log that contains the add-file operation on the primary database, and manually restore the log backup on the secondary database using WITH NORECOVERY and WITH MOVE.</span></span>  
  
4.  <span data-ttu-id="dd9b7-115">Подготовьте базу данных-получатель к повторному присоединению к группе доступности, выполнив восстановление с параметром NO RECOVERY остальных ожидающих резервных копий журналов из базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="dd9b7-115">Prepare the secondary database for re-joining the availability group, by restoring, WITH NO RECOVERY, any other outstanding log backups from the primary database.</span></span>  
  
5.  <span data-ttu-id="dd9b7-116">Повторно присоедините базу данных-получатель к группе доступности.</span><span class="sxs-lookup"><span data-stu-id="dd9b7-116">Rejoin the secondary database to the availability group.</span></span> <span data-ttu-id="dd9b7-117">Дополнительные сведения см. в статье [Присоединение базы данных-получателя к группе доступности (SQL Server)](join-a-secondary-database-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="dd9b7-117">For more information, see [Join a Secondary Database to an Availability Group &#40;SQL Server&#41;](join-a-secondary-database-to-an-availability-group-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd9b7-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="dd9b7-118">See Also</span></span>  
 <span data-ttu-id="dd9b7-119">[Общие сведения о группы доступности AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="dd9b7-119">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="dd9b7-120">[Подготовка базы данных-получателя для присоединения к группе доступности вручную (SQL Server)](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="dd9b7-120">[Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md) </span></span>  
 <span data-ttu-id="dd9b7-121">[Диагностика пользователей, утративших связь с учетной записью (SQL Server)](../../../sql-server/failover-clusters/troubleshoot-orphaned-users-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="dd9b7-121">[Troubleshoot Orphaned Users &#40;SQL Server&#41;](../../../sql-server/failover-clusters/troubleshoot-orphaned-users-sql-server.md) </span></span>  
 [<span data-ttu-id="dd9b7-122">Устранение неполадок &#40;конфигурации группы доступности AlwaysOn SQL Server&#41;Deleted</span><span class="sxs-lookup"><span data-stu-id="dd9b7-122">Troubleshoot AlwaysOn Availability Groups Configuration &#40;SQL Server&#41;deleted</span></span>](troubleshoot-always-on-availability-groups-configuration-sql-server.md)  
  
  
