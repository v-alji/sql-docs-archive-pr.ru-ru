---
title: Продолжить восстановление | Документация Майкрософт
description: В SQL Server используйте диалоговое окно продолжение восстановления, чтобы указать, нужно ли восстанавливать следующий резервный набор данных.
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.continuerestore.f1
ms.assetid: 987ac05f-57c0-49a9-9903-9889717aae4f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: c7a438ac7b8696d2f57bdf93ff86030cf607e682
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740313"
---
# <a name="continue-with-restore"></a><span data-ttu-id="564bc-103">Продолжить восстановление</span><span class="sxs-lookup"><span data-stu-id="564bc-103">Continue with Restore</span></span>
  <span data-ttu-id="564bc-104">Диалоговое окно **Продолжение восстановления** используется для указания, нужно ли восстанавливать следующий резервный набор данных в последовательности восстановления.</span><span class="sxs-lookup"><span data-stu-id="564bc-104">Use the **Continue with Restore** dialog box to indicate whether you want to restore the next backup set.</span></span> <span data-ttu-id="564bc-105">Чтобы приостановить операцию восстановления, например при смене ленты, завершите подготовительные операции и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="564bc-105">To delay the restore operation, for example, to swap tapes, wait until you are ready to proceed before you click **OK**.</span></span>  
  
 <span data-ttu-id="564bc-106">Нажатие на кнопку **Нет** останавливает последовательность восстановления, оставляя базу данных в состоянии восстановления из копии.</span><span class="sxs-lookup"><span data-stu-id="564bc-106">Clicking **No** terminates the restore sequence, leaving the database in the restoring state.</span></span> <span data-ttu-id="564bc-107">Чтобы продолжить восстановление позже, используйте задачи **Восстановить базу данных** или **Восстановить журнал транзакций** в зависимости от ситуации.</span><span class="sxs-lookup"><span data-stu-id="564bc-107">To continue with the restore later, use either the **Restore Database** or **Restore Transaction Log** task, as appropriate.</span></span>  
  
## <a name="options"></a><span data-ttu-id="564bc-108">Варианты</span><span class="sxs-lookup"><span data-stu-id="564bc-108">Options</span></span>  
 <span data-ttu-id="564bc-109">**Набор носителей**</span><span class="sxs-lookup"><span data-stu-id="564bc-109">**Media set**</span></span>  
 <span data-ttu-id="564bc-110">Отображает имя следующего набора носителей (если доступно).</span><span class="sxs-lookup"><span data-stu-id="564bc-110">Displays the next media set name (if available).</span></span>  
  
 <span data-ttu-id="564bc-111">**Резервный набор данных**</span><span class="sxs-lookup"><span data-stu-id="564bc-111">**Backup set**</span></span>  
 <span data-ttu-id="564bc-112">Отображает имя резервного набора данных.</span><span class="sxs-lookup"><span data-stu-id="564bc-112">Displays the backup set name.</span></span>  
  
 <span data-ttu-id="564bc-113">**Описание резервного набора данных**</span><span class="sxs-lookup"><span data-stu-id="564bc-113">**Backup set description**</span></span>  
 <span data-ttu-id="564bc-114">Отображает описание резервного набора данных.</span><span class="sxs-lookup"><span data-stu-id="564bc-114">Displays the backup set description.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="564bc-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="564bc-115">See Also</span></span>  
 <span data-ttu-id="564bc-116">[Просмотр содержимого ленты или файла резервной копии (SQL Server)](../relational-databases/backup-restore/view-the-contents-of-a-backup-tape-or-file-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="564bc-116">[View the Contents of a Backup Tape or File &#40;SQL Server&#41;](../relational-databases/backup-restore/view-the-contents-of-a-backup-tape-or-file-sql-server.md) </span></span>  
 <span data-ttu-id="564bc-117">[Просмотр свойств и содержимого логического устройства резервного копирования (SQL Server)](../relational-databases/backup-restore/view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="564bc-117">[View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;](../relational-databases/backup-restore/view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md) </span></span>  
 <span data-ttu-id="564bc-118">[Восстановление резервной копии базы данных &#40;SQL Server Management Studio&#41;](../relational-databases/backup-restore/restore-a-database-backup-using-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="564bc-118">[Restore a Database Backup &#40;SQL Server Management Studio&#41;](../relational-databases/backup-restore/restore-a-database-backup-using-ssms.md) </span></span>  
 [<span data-ttu-id="564bc-119">Восстановление резервной копии журнала транзакций (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="564bc-119">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](../relational-databases/backup-restore/restore-a-transaction-log-backup-sql-server.md)  
  
  
