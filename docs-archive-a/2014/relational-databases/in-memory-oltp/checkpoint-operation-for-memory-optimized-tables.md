---
title: Использование контрольной точки для таблиц, оптимизированных для памяти | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 47975bd5-373f-43cd-946a-da8e8088b610
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 07560ea0bf147198fb759f6769ae1c6d5c68a71e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749912"
---
# <a name="checkpoint-operation-for-memory-optimized-tables"></a><span data-ttu-id="4b8f2-102">Работа контрольной точки для оптимизированных для памяти таблиц</span><span class="sxs-lookup"><span data-stu-id="4b8f2-102">Checkpoint Operation for Memory-Optimized Tables</span></span>
  <span data-ttu-id="4b8f2-103">Контрольную точку нужно периодически обрабатывать для данных, оптимизированных для памяти, в файлах данных и разностных файлах, чтобы дополнять активную часть журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="4b8f2-103">A checkpoint needs to occur periodically for memory-optimized data in data and delta files to advance the active part of transaction log.</span></span> <span data-ttu-id="4b8f2-104">Контрольная точка позволяет восстанавливать таблицы, оптимизированные для памяти, до последней успешной контрольной точки, после чего применяется активная часть журнала транзакций для обновления таблиц, оптимизированных для памяти, и завершения восстановления.</span><span class="sxs-lookup"><span data-stu-id="4b8f2-104">The checkpoint allows memory-optimized tables to restore or recover to the last successful checkpoint and then the active portion of transaction log is applied to update the memory-optimized tables to complete the recovery.</span></span> <span data-ttu-id="4b8f2-105">Процессы работы контрольной точки для таблиц на диске и оптимизированных для памяти таблиц отличаются.</span><span class="sxs-lookup"><span data-stu-id="4b8f2-105">The checkpoint operation for disk-based tables and memory-optimized tables are distinct operations.</span></span> <span data-ttu-id="4b8f2-106">Ниже описываются различные сценарии и режим работы контрольной точки для таблиц на диске и таблиц, оптимизированных для памяти.</span><span class="sxs-lookup"><span data-stu-id="4b8f2-106">The following describes different scenarios and the checkpoint behavior for disk-based and memory-optimized tables:</span></span>  
  
## <a name="manual-checkpoint"></a><span data-ttu-id="4b8f2-107">Контрольная точка, установленная вручную</span><span class="sxs-lookup"><span data-stu-id="4b8f2-107">Manual Checkpoint</span></span>  
 <span data-ttu-id="4b8f2-108">При создании контрольной точки вручную закрывается контрольная точка для таблиц на диске и таблиц, оптимизированных для памяти.</span><span class="sxs-lookup"><span data-stu-id="4b8f2-108">When you issue a manual checkpoint, it closes the checkpoint for both disk-based and memory-optimized tables.</span></span> <span data-ttu-id="4b8f2-109">Активный файл данных закрывается, хотя он может быть заполнен только частично.</span><span class="sxs-lookup"><span data-stu-id="4b8f2-109">The active data file is closed even though it may be partially filled.</span></span>  
  
## <a name="automatic-checkpoint"></a><span data-ttu-id="4b8f2-110">Автоматически создаваемые контрольные точки</span><span class="sxs-lookup"><span data-stu-id="4b8f2-110">Automatic Checkpoint</span></span>  
 <span data-ttu-id="4b8f2-111">Автоматически создаваемая контрольная точка реализуется по разному для таблиц на диске и таблиц, оптимизированных для памяти, из-за различных способов сохранения данных.</span><span class="sxs-lookup"><span data-stu-id="4b8f2-111">Automatic checkpoint is implemented differently for disk-based and memory-optimized tables because of the different ways the data is persisted.</span></span>  
  
 <span data-ttu-id="4b8f2-112">Для таблиц на диске устанавливается автоматическая контрольная точка на основе параметра конфигурации, определяющего интервал восстановления (дополнительные сведения см. в разделе [Изменение целевого времени восстановления базы данных (SQL Server)](../logs/change-the-target-recovery-time-of-a-database-sql-server.md)).</span><span class="sxs-lookup"><span data-stu-id="4b8f2-112">For disk-based tables, an automatic checkpoint is taken based on the recovery interval configuration option (for more information, see [Change the Target Recovery Time of a Database &#40;SQL Server&#41;](../logs/change-the-target-recovery-time-of-a-database-sql-server.md)).</span></span>  
  
 <span data-ttu-id="4b8f2-113">Для оптимизированных для памяти таблиц автоматическая контрольная точка устанавливается, когда размер файла журнала транзакций становится больше 512 МБ с момента создания последней контрольной точки.</span><span class="sxs-lookup"><span data-stu-id="4b8f2-113">For memory-optimized tables, an automatic checkpoint is taken when transaction log file becomes bigger than 512 MB since the last checkpoint.</span></span> <span data-ttu-id="4b8f2-114">В эти 512 МБ входят записи журналов транзакций как для таблиц на диске, так и для оптимизированных для памяти таблиц.</span><span class="sxs-lookup"><span data-stu-id="4b8f2-114">512 MB includes transaction log records for both disk-based and memory-optimized tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b8f2-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="4b8f2-115">See Also</span></span>  
 [<span data-ttu-id="4b8f2-116">Создание и управление хранилищем для оптимизированных для памяти объектов</span><span class="sxs-lookup"><span data-stu-id="4b8f2-116">Creating and Managing Storage for Memory-Optimized Objects</span></span>](creating-and-managing-storage-for-memory-optimized-objects.md)  
  
  
