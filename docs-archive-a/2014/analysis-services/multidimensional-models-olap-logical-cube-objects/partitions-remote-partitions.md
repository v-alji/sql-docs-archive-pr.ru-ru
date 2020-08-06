---
title: Удаленные секции | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- storage [Analysis Services], partitions
- archiving remote partitions [Analysis Services]
- partitions [Analysis Services], remote
- restoring remote partitions [Analysis Services]
- backing up remote partitions [Analysis Services]
- partitions [Analysis Services], storage
- storing data [Analysis Services], partitions
- remote partitions [Analysis Services]
ms.assetid: 63f5d9f5-c6b6-4ceb-94fe-7b6c396d10bb
author: minewiskan
ms.author: owend
ms.openlocfilehash: 32fdf05d061d4e1c1da6ec0ef9179ecd12bda172
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87733238"
---
# <a name="remote-partitions"></a><span data-ttu-id="a03ea-102">Удаленные секции</span><span class="sxs-lookup"><span data-stu-id="a03ea-102">Remote Partitions</span></span>
  <span data-ttu-id="a03ea-103">Данные удаленной секции хранятся на другом экземпляре Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , отличном от экземпляра, содержащего определения (метаданные) секции и ее родительского куба.</span><span class="sxs-lookup"><span data-stu-id="a03ea-103">The data of a remote partition is stored on a different instance of Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] than the instance that contains the definitions (metadata) of the partition and its parent cube.</span></span> <span data-ttu-id="a03ea-104">Управление удаленной секцией выполняется на том же экземпляре служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], на котором определены секция и ее родительский куб.</span><span class="sxs-lookup"><span data-stu-id="a03ea-104">A remote partition is administered on the same instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] where the partition and its parent cube are defined.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a03ea-105">Чтобы сохранить удаленную секцию, на компьютере должен быть установлен экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] и был запущен тот же уровень пакета обновления, что и у экземпляра, где определена секция.</span><span class="sxs-lookup"><span data-stu-id="a03ea-105">To store a remote partition, the computer must have an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] installed and be running the same service pack level as the instance where the partition was defined.</span></span> <span data-ttu-id="a03ea-106">Удаленные секции экземпляров более ранних версий служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="a03ea-106">Remote partitions on instances of an earlier version of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] are not supported.</span></span>  
  
 <span data-ttu-id="a03ea-107">При включении удаленных секций в группу мер происходит распределение памяти и загрузки ЦП по всем секциям группы мер.</span><span class="sxs-lookup"><span data-stu-id="a03ea-107">When remote partitions are included in a measure group, the memory and CPU utilization of the cube is distributed across all the partitions in the measure group.</span></span> <span data-ttu-id="a03ea-108">Например, во время обработки удаленной секции, отдельно или как часть процесса обработки ее родительского куба, максимальная загрузка памяти ЦП для данной секции приходится на удаленный экземпляр служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a03ea-108">For example, when a remote partition is processed, either alone or as part of parent cube processing, most of the memory and CPU utilization for that partition occurs on the remote instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a03ea-109">Куб, который содержит удаленные секции, может содержать измерения, доступные для записи. Однако это может влиять на производительность этого куба.</span><span class="sxs-lookup"><span data-stu-id="a03ea-109">A cube that contains remote partitions can contain write-enabled dimensions; however, this may affect performance for the cube.</span></span> <span data-ttu-id="a03ea-110">Дополнительные сведения об измерениях, доступных для записи, см. в разделе [измерения, доступные для записи](../multidimensional-models-olap-logical-dimension-objects/write-enabled-dimensions.md).</span><span class="sxs-lookup"><span data-stu-id="a03ea-110">For more information about write-enabled dimensions, see [Write-Enabled Dimensions](../multidimensional-models-olap-logical-dimension-objects/write-enabled-dimensions.md).</span></span>  
  
## <a name="storage-modes-for-remote-partitions"></a><span data-ttu-id="a03ea-111">Режимы хранения для удаленных секций</span><span class="sxs-lookup"><span data-stu-id="a03ea-111">Storage Modes for Remote Partitions</span></span>  
 <span data-ttu-id="a03ea-112">Удаленные секции могут использовать любой из перечисленных ниже типов хранилищ, применяемых локальными секциями: многомерный OLAP (MOLAP), гибридный OLAP (HOLAP) или реляционный OLAP (ROLAP).</span><span class="sxs-lookup"><span data-stu-id="a03ea-112">Remote partitions may use any of the storage types used by local partitions: multidimensional OLAP (MOLAP), hybrid OLAP (HOLAP), or relational OLAP (ROLAP).</span></span> <span data-ttu-id="a03ea-113">Кроме того, удаленные секции могут использовать упреждающее кэширование.</span><span class="sxs-lookup"><span data-stu-id="a03ea-113">Remote partitions may also use proactive caching.</span></span> <span data-ttu-id="a03ea-114">В зависимости от режима хранения удаленной секции на удаленном экземпляре служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] хранятся следующие данные.</span><span class="sxs-lookup"><span data-stu-id="a03ea-114">Depending on the storage mode of a remote partition, the following data is stored on the remote instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a03ea-115">Тип хранения</span><span class="sxs-lookup"><span data-stu-id="a03ea-115">Storage Type</span></span>|<span data-ttu-id="a03ea-116">Данные</span><span class="sxs-lookup"><span data-stu-id="a03ea-116">Data</span></span>|  
|<span data-ttu-id="a03ea-117">MOLAP</span><span class="sxs-lookup"><span data-stu-id="a03ea-117">MOLAP</span></span>|<span data-ttu-id="a03ea-118">Статистические схемы секции и копия исходных данных секции</span><span class="sxs-lookup"><span data-stu-id="a03ea-118">The partition's aggregations and a copy of the partition's source data</span></span>|  
|<span data-ttu-id="a03ea-119">HOLAP</span><span class="sxs-lookup"><span data-stu-id="a03ea-119">HOLAP</span></span>|<span data-ttu-id="a03ea-120">Статистические схемы секций</span><span class="sxs-lookup"><span data-stu-id="a03ea-120">The partitions aggregations</span></span>|  
|<span data-ttu-id="a03ea-121">ROLAP</span><span class="sxs-lookup"><span data-stu-id="a03ea-121">ROLAP</span></span>|<span data-ttu-id="a03ea-122">Данные секции отсутствуют</span><span class="sxs-lookup"><span data-stu-id="a03ea-122">No partition data</span></span>|  
  
 <span data-ttu-id="a03ea-123">Если в группе мер содержится несколько секций MOLAP или HOLAP, хранимых на нескольких экземплярах служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], то куб распределяет данные группы мер между указанными экземплярами служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a03ea-123">If a measure group contains multiple MOLAP or HOLAP partitions stored on multiple instances of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], the cube distributes the data in the measure group data among those instances of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
## <a name="merging-remote-partitions"></a><span data-ttu-id="a03ea-124">Слияние удаленных секций</span><span class="sxs-lookup"><span data-stu-id="a03ea-124">Merging Remote Partitions</span></span>  
 <span data-ttu-id="a03ea-125">Удаленные секции можно объединять только с удаленными секциями, хранимыми на том же удаленном экземпляре служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a03ea-125">Remote partitions can be merged only with other remote partitions that are stored on the same remote instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="a03ea-126">Дополнительные сведения о слиянии секций см. [в разделе Merge partitions in Analysis Services &#40;SSAS-многомерные&#41;](../multidimensional-models/merge-partitions-in-analysis-services-ssas-multidimensional.md).</span><span class="sxs-lookup"><span data-stu-id="a03ea-126">For more information about merging partitions, see [Merge Partitions in Analysis Services &#40;SSAS - Multidimensional&#41;](../multidimensional-models/merge-partitions-in-analysis-services-ssas-multidimensional.md).</span></span>  
  
## <a name="archiving-and-restoring-remote-partitions"></a><span data-ttu-id="a03ea-127">Архивация и восстановление удаленных секций</span><span class="sxs-lookup"><span data-stu-id="a03ea-127">Archiving and Restoring Remote Partitions</span></span>  
 <span data-ttu-id="a03ea-128">Данные удаленных секций можно архивировать или восстанавливать, когда архивируется или восстанавливается хранящая их база данных.</span><span class="sxs-lookup"><span data-stu-id="a03ea-128">Data in remote partitions can be archived or restored when the database that stores the remote partition is archived or restored.</span></span> <span data-ttu-id="a03ea-129">Если восстановление базы данных выполняется без восстановления удаленной секции, то прежде чем использовать данные секции, необходимо обработать удаленную секцию.</span><span class="sxs-lookup"><span data-stu-id="a03ea-129">If you restore a database without restoring a remote partition, you must process the remote partition before you can use the data in the partition.</span></span> <span data-ttu-id="a03ea-130">Дополнительные сведения о архивировании и восстановлении баз данных см. в статье [резервное копирование и восстановление баз данных Analysis Services](../multidimensional-models/backup-and-restore-of-analysis-services-databases.md).</span><span class="sxs-lookup"><span data-stu-id="a03ea-130">For more information about archiving and restoring databases, see [Backup and Restore of Analysis Services Databases](../multidimensional-models/backup-and-restore-of-analysis-services-databases.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a03ea-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="a03ea-131">See Also</span></span>  
 <span data-ttu-id="a03ea-132">[Создание &#40;Analysis Services удаленных секций и управление ими&#41;](../multidimensional-models/create-and-manage-a-remote-partition-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="a03ea-132">[Create and Manage a Remote Partition &#40;Analysis Services&#41;](../multidimensional-models/create-and-manage-a-remote-partition-analysis-services.md) </span></span>  
 [<span data-ttu-id="a03ea-133">Обработка объектов служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="a03ea-133">Processing Analysis Services Objects</span></span>](../multidimensional-models/processing-analysis-services-objects.md)  
  
  
