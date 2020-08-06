---
title: Создание резервной копии на зеркальном наборе носителей (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: 5fc43a5d-dfd6-4c53-a4ef-3c8da23ccc81
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 255a3c190139c029f5211dcab9780b6d07d975a4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664955"
---
# <a name="back-up-to-a-mirrored-media-set-transact-sql"></a><span data-ttu-id="8ee5c-102">Создание резервной копии на зеркальном наборе носителей (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="8ee5c-102">Back Up to a Mirrored Media Set (Transact-SQL)</span></span>
  <span data-ttu-id="8ee5c-103">В этом разделе описывается использование [!INCLUDE[tsql](../../includes/tsql-md.md)] инструкции [BACKUP](/sql/t-sql/statements/backup-transact-sql) для указания зеркального набора носителей при резервном копировании [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] базы данных.</span><span class="sxs-lookup"><span data-stu-id="8ee5c-103">This topic describes how to use the [!INCLUDE[tsql](../../includes/tsql-md.md)][BACKUP](/sql/t-sql/statements/backup-transact-sql) statement to specify a mirrored media set when backing up a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="8ee5c-104">Для определения зеркального набора носителей в инструкции BACKUP укажите первое зеркало в предложении TO.</span><span class="sxs-lookup"><span data-stu-id="8ee5c-104">In your BACKUP statement, specify the first mirror in the TO clause.</span></span> <span data-ttu-id="8ee5c-105">Затем определите каждое зеркало в своем собственном предложении TO.</span><span class="sxs-lookup"><span data-stu-id="8ee5c-105">Then, specify each mirror in its own MIRROR TO clause.</span></span> <span data-ttu-id="8ee5c-106">Предложения TO и MIRROR TO должны определять одинаковое количество и одинаковый тип устройств резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="8ee5c-106">The TO and MIRROR TO clauses must specify the same number and type of backup devices.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ee5c-107">Пример</span><span class="sxs-lookup"><span data-stu-id="8ee5c-107">Example</span></span>  
 <span data-ttu-id="8ee5c-108">В следующем примере создается зеркальный набор носителей, показанный на предыдущем рисунке, и производится резервное копирование базы данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] на оба зеркала.</span><span class="sxs-lookup"><span data-stu-id="8ee5c-108">The following example creates the mirrored media set illustrated in the previous illustration and backs up the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database to both mirrors.</span></span>  
  
```  
BACKUP DATABASE AdventureWorks2012  
TO TAPE = '\\.\tape0', TAPE = '\\.\tape1'  
MIRROR TO TAPE = '\\.\tape2', TAPE = '\\.\tape3'  
WITH  
    FORMAT,  
    MEDIANAME = 'AdventureWorks2012Set1';  
GO  
```  
  
## <a name="related-tasks"></a><span data-ttu-id="8ee5c-109">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="8ee5c-109">Related Tasks</span></span>  
 <span data-ttu-id="8ee5c-110">**Восстановление из зеркально отображенной резервной копии**</span><span class="sxs-lookup"><span data-stu-id="8ee5c-110">**To restore from a mirrored backup**</span></span>  
  
-   [<span data-ttu-id="8ee5c-111">RESTORE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="8ee5c-111">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="8ee5c-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="8ee5c-112">See Also</span></span>  
 <span data-ttu-id="8ee5c-113">[BACKUP (Transact-SQL)](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8ee5c-113">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 [<span data-ttu-id="8ee5c-114">Зеркальные наборы носителей резервных копий (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="8ee5c-114">Mirrored Backup Media Sets &#40;SQL Server&#41;</span></span>](mirrored-backup-media-sets-sql-server.md)  
  
  
