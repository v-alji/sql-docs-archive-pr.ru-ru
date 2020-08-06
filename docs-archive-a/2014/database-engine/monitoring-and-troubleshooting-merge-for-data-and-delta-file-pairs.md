---
title: Мониторинг и устранение неполадок слияния для пар данных и разностных файлов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: a8b0bacc-4d2c-42e4-84bf-1a97e0bd385b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5dc57d08f3db1792a9359b3aa79aaceecd03a025
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667887"
---
# <a name="monitoring-and-troubleshooting-merge-for-data-and-delta-file-pairs"></a><span data-ttu-id="5816e-102">Мониторинг и устранение неполадок со слиянием для пар файлов данных и разностных файлов</span><span class="sxs-lookup"><span data-stu-id="5816e-102">Monitoring and Troubleshooting Merge for Data and Delta File Pairs</span></span>
  <span data-ttu-id="5816e-103">In-Memory OLTP использует политику слияния для автоматического объединения пар смежных файлов данных и разностных файлов.</span><span class="sxs-lookup"><span data-stu-id="5816e-103">In-Memory OLTP uses a merge policy to merge adjacent data and delta file pairs automatically.</span></span> <span data-ttu-id="5816e-104">Действия слияния отключить нельзя.</span><span class="sxs-lookup"><span data-stu-id="5816e-104">You cannot disable merge activity.</span></span>  
  
 <span data-ttu-id="5816e-105">Мониторинг пар файлов данных и разностных файлов может осуществляться следующим образом.</span><span class="sxs-lookup"><span data-stu-id="5816e-105">You can monitor data and delta file pairs, as follows:</span></span>  
  
-   <span data-ttu-id="5816e-106">Сравните размер хранилища в памяти и общего размера хранилища.</span><span class="sxs-lookup"><span data-stu-id="5816e-106">Compare the size of in-memory storage to overall size of storage.</span></span> <span data-ttu-id="5816e-107">Если хранилище несоразмерно велико, то, скорее всего, слияние не активируется.</span><span class="sxs-lookup"><span data-stu-id="5816e-107">If the storage is dis-proportionately large, then it is likely that merge is not getting triggered.</span></span> <span data-ttu-id="5816e-108">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="5816e-108">For information</span></span>  
  
-   <span data-ttu-id="5816e-109">Взгляните на используемое пространство в файлах данных и разностном файле с помощью [sys. dm_db_xtp_checkpoint_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-xtp-checkpoint-files-transact-sql) , чтобы узнать, не активируется ли слияние.</span><span class="sxs-lookup"><span data-stu-id="5816e-109">Look at the used space in data and delta files using [sys.dm_db_xtp_checkpoint_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-xtp-checkpoint-files-transact-sql) to see if merge is not getting triggered when it should.</span></span>  
  
## <a name="performing-a-manual-merge"></a><span data-ttu-id="5816e-110">Выполнение слияния вручную</span><span class="sxs-lookup"><span data-stu-id="5816e-110">Performing a Manual Merge</span></span>  
 <span data-ttu-id="5816e-111">Для выполнения ручного слияния можно использовать [sys. sp_xtp_merge_checkpoint_files &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-merge-checkpoint-files-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="5816e-111">You can use [sys.sp_xtp_merge_checkpoint_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-merge-checkpoint-files-transact-sql) to perform a manual merge.</span></span>  
  
 <span data-ttu-id="5816e-112">Используйте следующий запрос для получения сведений о файлах данных и разностных файлах.</span><span class="sxs-lookup"><span data-stu-id="5816e-112">Use the following query to retrieve information about the data and delta files,</span></span>  
  
```sql  
select checkpoint_file_id, file_type_desc, internal_storage_slot, file_size_in_bytes, file_size_used_in_bytes,   
inserted_row_count, deleted_row_count, lower_bound_tsn, upper_bound_tsn   
from sys.dm_db_xtp_checkpoint_files  
where state = 1  
order by file_type_desc, upper_bound_tsn  
```  
  
 <span data-ttu-id="5816e-113">Предположим, что обнаружено три файла данных, которые не были объединены.</span><span class="sxs-lookup"><span data-stu-id="5816e-113">Assume that you found three data files that have not been merged.</span></span> <span data-ttu-id="5816e-114">Используя значение `lower_bound_tsn` первого файла данных и значение `upper_bound_tsn` последнего файла данных, можно выполнить следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5816e-114">Using the `lower_bound_tsn` value of the first data file and the `upper_bound_tsn` of the last data file, you can issue the following command:</span></span>  
  
```sql  
exec sys.sp_xtp_merge_checkpoint_files 'H_DB',  12345, 67890  
```  
  
 <span data-ttu-id="5816e-115">Предположим, что три пары файлов данных и разностных файлов имеют каждая по 15 836 строк и 5279 удаленных строк.</span><span class="sxs-lookup"><span data-stu-id="5816e-115">Assume that the three data and delta file pairs each had 15,836 rows and 5,279 deleted rows.</span></span> <span data-ttu-id="5816e-116">После слияния новый файл данных содержит 31 872 строки и 0 удаленных строк.</span><span class="sxs-lookup"><span data-stu-id="5816e-116">After the merge, the new data file has 31,872 rows and 0 deleted rows.</span></span> <span data-ttu-id="5816e-117">Размер нового файла данных может быть значительно больше, чем выбранный исходный размер 128 МБ.</span><span class="sxs-lookup"><span data-stu-id="5816e-117">The size of the new data file can be much larger than the initially allocated size of 128MB.</span></span> <span data-ttu-id="5816e-118">Это происходит потому, что слияние вручную переопределяет политику слияния и принудительно выполняет слияние запрошенных файлов.</span><span class="sxs-lookup"><span data-stu-id="5816e-118">This is because manual merge overrides the merge policy and forces the merge of the requested files.</span></span>  
  
 <span data-ttu-id="5816e-119">[Переход состояния блога файлов контрольных точек в базах данных с таблицами, оптимизированными для памяти](https://cloudblogs.microsoft.com/sqlserver/2014/01/23/state-transition-of-checkpoint-files-in-databases-with-memory-optimized-tables/) , описывает смену состояния пар данных и разностных файлов с момента создания на сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="5816e-119">The blog [State Transition of Checkpoint Files in Databases with Memory-Optimized Tables](https://cloudblogs.microsoft.com/sqlserver/2014/01/23/state-transition-of-checkpoint-files-in-databases-with-memory-optimized-tables/) describes state transition of data and delta file pairs from inception to garbage collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5816e-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="5816e-120">See Also</span></span>  
 [<span data-ttu-id="5816e-121">Создание и управление хранилищем для оптимизированных для памяти объектов</span><span class="sxs-lookup"><span data-stu-id="5816e-121">Creating and Managing Storage for Memory-Optimized Objects</span></span>](../relational-databases/in-memory-oltp/creating-and-managing-storage-for-memory-optimized-objects.md)  
  
