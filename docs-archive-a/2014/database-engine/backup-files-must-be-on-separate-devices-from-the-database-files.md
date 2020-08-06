---
title: Файлы резервной копии должны находиться на разных устройствах из файлов базы данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 7039bebb-1f25-4cf3-81f1-393dfb78da12
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: d5eff9cb3139e1e1043f99ba63d11160b1010c27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733141"
---
# <a name="backup-files-must-be-on-separate-devices-from-the-database-files"></a><span data-ttu-id="3142c-102">Файлы резервной копии и файлы базы данных должны находиться на отдельных устройствах</span><span class="sxs-lookup"><span data-stu-id="3142c-102">Backup Files Must Be on Separate Devices from the Database Files</span></span>
  <span data-ttu-id="3142c-103">Это правило проверяет, размещаются ли файлы базы данных на устройствах отдельно от файлов резервных копий.</span><span class="sxs-lookup"><span data-stu-id="3142c-103">This rule checks whether database files are on devices separate from the backup files.</span></span> <span data-ttu-id="3142c-104">Если файлы базы данных и файлов резервных копий расположены на одном устройстве, то в случае его сбоя резервные копии будут недоступны.</span><span class="sxs-lookup"><span data-stu-id="3142c-104">If database files and backup files are on the same device and the device fails, the database and backups will be unavailable.</span></span> <span data-ttu-id="3142c-105">Кроме того, размещение файлов базы данных и файлов резервных копий на отдельных устройствах оптимизирует производительность ввода-вывода как при записи резервных копий, так и в процессе эксплуатации базы данных.</span><span class="sxs-lookup"><span data-stu-id="3142c-105">Also, putting the database and backup files on the separate devices optimizes the I/O performance for both the production use of the database and the writing of backups.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="3142c-106">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="3142c-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="3142c-107">Настоятельно рекомендуется размещать базу данных и резервные копии на отдельных устройствах резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="3142c-107">We strongly recommend that you put the database and backups on separate backup devices.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3142c-108">Эта политика не может обнаружить отдельные физические устройства посредством точек подключения.</span><span class="sxs-lookup"><span data-stu-id="3142c-108">This policy cannot detect separate physical devices through mount points.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="3142c-109">Дополнительные сведения см. в разделе</span><span class="sxs-lookup"><span data-stu-id="3142c-109">For More Information</span></span>  
 [<span data-ttu-id="3142c-110">Устройства резервного копирования (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="3142c-110">Backup Devices &#40;SQL Server&#41;</span></span>](../relational-databases/backup-restore/backup-devices-sql-server.md)  
  
 [<span data-ttu-id="3142c-111">Резервное копирование и восстановление баз данных SQL Server</span><span class="sxs-lookup"><span data-stu-id="3142c-111">Back Up and Restore of SQL Server Databases</span></span>](../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md)  
  
## <a name="see-also"></a><span data-ttu-id="3142c-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="3142c-112">See Also</span></span>  
 [<span data-ttu-id="3142c-113">Наблюдение с помощью управления на основе политик и принудительное применение рекомендаций с помощью управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="3142c-113">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](../relational-databases/policy-based-management/monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
