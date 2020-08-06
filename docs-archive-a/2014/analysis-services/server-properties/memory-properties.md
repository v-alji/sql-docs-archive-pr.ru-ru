---
title: Свойства памяти | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- LowMemoryLimit property
- MinimumAllocatedMemory property
- MidMemoryPrice property
- MemoryHeapType property
- memory [Analysis Services]
- DefaultPagesCountToReuse property
- TotalMemoryLimit property
- SessionMemoryLimit property
- VirtualMemoryLimit property
- WaitCountIfHighMemory property
- HighMemoryPrice property
- HeapTypeForObjects property
ms.assetid: 085f5195-7b2c-411a-9813-0ff5c6066d13
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6f2d2e56c9a951cee27752bd57d55d185a9b6618
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752380"
---
# <a name="memory-properties"></a><span data-ttu-id="c6edb-102">Свойства памяти</span><span class="sxs-lookup"><span data-stu-id="c6edb-102">Memory Properties</span></span>
  <span data-ttu-id="c6edb-103">Службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] поддерживают свойства памяти сервера, перечисленные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="c6edb-103">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] supports the server memory properties listed in the following table.</span></span> <span data-ttu-id="c6edb-104">Инструкции по установке этих свойств см. в [Руководстве по работе со службами SQL Server 2008 R2 Analysis Services](https://go.microsoft.com/fwlink/?LinkID=225539).</span><span class="sxs-lookup"><span data-stu-id="c6edb-104">For guidance in setting these properties, see [SQL Server 2008 R2 Analysis Services Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539).</span></span>  
  
 <span data-ttu-id="c6edb-105">Значения в диапазоне от 1 до 100 представляют процент **общего объема физической памяти** или **виртуального адресного пространства**в зависимости от того, какое значение меньше.</span><span class="sxs-lookup"><span data-stu-id="c6edb-105">Values between 1 and 100 represent percentages of **Total Physical Memory** or **Virtual Address Space**, whichever is less.</span></span> <span data-ttu-id="c6edb-106">Значения, превышающие 100, представляют собой ограничения памяти в байтах.</span><span class="sxs-lookup"><span data-stu-id="c6edb-106">Values over 100 represent memory limits in bytes.</span></span>  
  
 <span data-ttu-id="c6edb-107">**Применимо к:** Многомерный и табличный режим сервера, если не указано иное.</span><span class="sxs-lookup"><span data-stu-id="c6edb-107">**Applies to:** Multidimensional and Tabular server mode, unless noted otherwise.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c6edb-108">Свойства</span><span class="sxs-lookup"><span data-stu-id="c6edb-108">Properties</span></span>  
 `LowMemoryLimit`  
 <span data-ttu-id="c6edb-109">Подписанное 64-разрядное свойство числа с плавающей запятой двойной точности, определяющее точку, в которой серверу не хватает памяти, в процентах от общего объема физической памяти.</span><span class="sxs-lookup"><span data-stu-id="c6edb-109">A signed 64-bit double-precision floating-point number property that defines the point at which the server is low on memory, expressed as percentage of total physical memory.</span></span> <span data-ttu-id="c6edb-110">При достижении этого ограничения экземпляр начнет постепенно очищать память из кэшей, закрывая истекшие сеансы и выгружая неиспользуемые вычисления.</span><span class="sxs-lookup"><span data-stu-id="c6edb-110">When this limit is reached, the instance will start to slowly clear memory out of caches by closing expired sessions and unloading unused calculations.</span></span> <span data-ttu-id="c6edb-111">Сервер не будет освобождать память ниже этого предела.</span><span class="sxs-lookup"><span data-stu-id="c6edb-111">The server will not release memory below this limit.</span></span> <span data-ttu-id="c6edb-112">Значение по умолчанию равно 65, то есть предел недостатка памяти составляет 65 % от объема физической памяти или виртуального адресного пространства (в зависимости от того, какое значение меньше).</span><span class="sxs-lookup"><span data-stu-id="c6edb-112">The default value is 65; which indicates the low memory limit is 65% of physical memory or the virtual address space, whichever is less.</span></span>  
  
 `TotalMemoryLimit`  
 <span data-ttu-id="c6edb-113">Определяет порог, при достижении которого сервер начинает освобождать память более агрессивно.</span><span class="sxs-lookup"><span data-stu-id="c6edb-113">Defines a threshold that when reached, causes the server to deallocate memory more aggressively.</span></span> <span data-ttu-id="c6edb-114">Значение по умолчанию равно 80 % от объема физической памяти или виртуального адресного пространства (в зависимости от того, какое значение меньше).</span><span class="sxs-lookup"><span data-stu-id="c6edb-114">The default value 80% of physical memory or the virtual address space, whichever is less.</span></span>  
  
 <span data-ttu-id="c6edb-115">Обратите внимание, что значение `TotalMemoryLimit` всегда должно быть меньше, чем `HardMemoryLimit`</span><span class="sxs-lookup"><span data-stu-id="c6edb-115">Note that `TotalMemoryLimit` must always be less than `HardMemoryLimit`</span></span>  
  
 `HardMemoryLimit`  
 <span data-ttu-id="c6edb-116">Задает порог памяти, после достижения которого экземпляр агрессивно прерывает активные сеансы пользователей, чтобы уменьшить использование памяти.</span><span class="sxs-lookup"><span data-stu-id="c6edb-116">Specifies a memory threshold after which the instance aggressively terminates active user sessions to reduce memory usage.</span></span> <span data-ttu-id="c6edb-117">Во всех прерванных сеансах отображается сообщение об ошибке (про отмену в связи с нехваткой памяти).</span><span class="sxs-lookup"><span data-stu-id="c6edb-117">All terminated sessions will receive an error about being cancelled by memory pressure.</span></span> <span data-ttu-id="c6edb-118">Значение по умолчанию 0 означает, что для параметра `HardMemoryLimit` будет задано среднее значение между `TotalMemoryLimit` и общим объемом физической памяти системы. Если объем физической памяти системы превышает объем виртуального адресного пространства процесса, то при вычислении `HardMemoryLimit` вместо физической памяти используется виртуальное адресное пространство.</span><span class="sxs-lookup"><span data-stu-id="c6edb-118">The default value, zero (0), means the `HardMemoryLimit` will be set to a midway value between `TotalMemoryLimit` and the total physical memory of the system; if the physical memory of the system is larger than the virtual address space of the process, then virtual address space will be used instead to calculate `HardMemoryLimit`.</span></span>  
  
 `VirtualMemoryLimit`  
 <span data-ttu-id="c6edb-119">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c6edb-119">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `VertiPaqPagingPolicy`  
 <span data-ttu-id="c6edb-120">Определяет использование подкачки в случае, если серверу не хватает памяти.</span><span class="sxs-lookup"><span data-stu-id="c6edb-120">Specifies the paging behavior in the event the server runs low on memory.</span></span> <span data-ttu-id="c6edb-121">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="c6edb-121">Valid values are as follows:</span></span>  
  
 <span data-ttu-id="c6edb-122">Нуль (**0**) отключает механизм подкачки страниц.</span><span class="sxs-lookup"><span data-stu-id="c6edb-122">Zero (**0**) disables paging.</span></span> <span data-ttu-id="c6edb-123">При недостатке памяти обработка прерывается с ошибкой нехватки памяти.</span><span class="sxs-lookup"><span data-stu-id="c6edb-123">If memory is insufficient, processing fails with an out-of-memory error.</span></span> <span data-ttu-id="c6edb-124">Если подкачка запрещена, вы должны предоставить права доступа Windows учетной записи службы.</span><span class="sxs-lookup"><span data-stu-id="c6edb-124">If you disable paging, you must grant Windows privileges to the service account.</span></span> <span data-ttu-id="c6edb-125">Инструкции см. в разделе [Настройка учетных записей служб (службы Analysis Services)](../instances/configure-service-accounts-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="c6edb-125">See [Configure Service Accounts &#40;Analysis Services&#41;](../instances/configure-service-accounts-analysis-services.md) for instructions.</span></span>  
  
 <span data-ttu-id="c6edb-126">По умолчанию —**1** .</span><span class="sxs-lookup"><span data-stu-id="c6edb-126">**1** is the default.</span></span> <span data-ttu-id="c6edb-127">Данное свойство разрешает подкачку на диск с использованием файла подкачки операционной системы (pagefile.sys).</span><span class="sxs-lookup"><span data-stu-id="c6edb-127">This property enables paging to disk using the operating system page file (pagefile.sys).</span></span>  
  
 <span data-ttu-id="c6edb-128">Если свойство `VertiPaqPagingPolicy` имеет значение 1, то ошибки обработки вследствие ограничений памяти менее вероятны, поскольку сервер использует подкачку на диск по указанному методу.</span><span class="sxs-lookup"><span data-stu-id="c6edb-128">When `VertiPaqPagingPolicy` is set to 1, processing is less likely to fail due to memory constraints because the server will try to page to disk using the method that you specified.</span></span> <span data-ttu-id="c6edb-129">Установка свойства `VertiPaqPagingPolicy` не гарантирует полное отсутствие ошибок памяти.</span><span class="sxs-lookup"><span data-stu-id="c6edb-129">Setting the `VertiPaqPagingPolicy` property does not guarantee that memory errors will never happen.</span></span> <span data-ttu-id="c6edb-130">Ошибки нехватки памяти по-прежнему могут возникать при следующих условиях.</span><span class="sxs-lookup"><span data-stu-id="c6edb-130">Out of memory errors can still occur under the following conditions:</span></span>  
  
-   <span data-ttu-id="c6edb-131">Недостаточно памяти для всех словарей.</span><span class="sxs-lookup"><span data-stu-id="c6edb-131">There is not enough memory for all dictionaries.</span></span> <span data-ttu-id="c6edb-132">В ходе обработки службы Analysis Services блокируют словари для каждого столбца в памяти, и общий объем всех словарей не может превышать значения, заданного в свойстве `VertiPaqMemoryLimit`.</span><span class="sxs-lookup"><span data-stu-id="c6edb-132">During processing, Analysis Services locks the dictionaries for each column in memory, and all of these together cannot be more than the value specified for `VertiPaqMemoryLimit`.</span></span>  
  
-   <span data-ttu-id="c6edb-133">Недостаточно виртуального адресного пространства для процесса.</span><span class="sxs-lookup"><span data-stu-id="c6edb-133">There is insufficient virtual address space to accommodate the process.</span></span>  
  
 <span data-ttu-id="c6edb-134">Чтобы устранить постоянные ошибки памяти, можно изменить структуру модели, чтобы сократить объем данных, нуждающихся в обработке, или увеличить объем физической памяти на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c6edb-134">To resolve persistent out of memory errors, you can either try to redesign the model to reduce the amount of data that needs processing, or you can add more physical memory to the computer.</span></span>  
  
 <span data-ttu-id="c6edb-135">Применяется только в табличном режиме сервера.</span><span class="sxs-lookup"><span data-stu-id="c6edb-135">Applies to tabular server mode only.</span></span>  
  
 `VertiPaqMemoryLimit`  
 <span data-ttu-id="c6edb-136">Если подкачка на диск разрешена, это свойство задает уровень использования памяти (в процентах от общего объема памяти), при котором начинается подкачка.</span><span class="sxs-lookup"><span data-stu-id="c6edb-136">If paging to disk is allowed, this property specifies the level of memory consumption (as a percentage of total memory) at which paging starts.</span></span> <span data-ttu-id="c6edb-137">Значение по умолчанию равно 60.</span><span class="sxs-lookup"><span data-stu-id="c6edb-137">The default is 60.</span></span> <span data-ttu-id="c6edb-138">Если память используется менее чем на 60 процентов, сервер не осуществляет подкачку на диск.</span><span class="sxs-lookup"><span data-stu-id="c6edb-138">If memory consumption is less than 60 percent, the server will not page to disk.</span></span>  
  
 <span data-ttu-id="c6edb-139">Это свойство зависит от свойства `VertiPaqPagingPolicyProperty`, которое должно быть равно 1, чтобы подкачка происходила.</span><span class="sxs-lookup"><span data-stu-id="c6edb-139">This property depends on the `VertiPaqPagingPolicyProperty`, which must be set to 1 in order for paging to occur.</span></span>  
  
 <span data-ttu-id="c6edb-140">Применяется только в табличном режиме сервера.</span><span class="sxs-lookup"><span data-stu-id="c6edb-140">Applies to tabular server mode only.</span></span>  
  
 `HighMemoryPrice`  
 <span data-ttu-id="c6edb-141">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c6edb-141">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MemoryHeapType`  
 <span data-ttu-id="c6edb-142">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c6edb-142">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="c6edb-143">Применяется только в многомерном режиме сервера.</span><span class="sxs-lookup"><span data-stu-id="c6edb-143">Applies to multidimensional server mode only.</span></span>  
  
 `HeapTypeForObjects`  
 <span data-ttu-id="c6edb-144">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c6edb-144">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="c6edb-145">Применяется только в многомерном режиме сервера.</span><span class="sxs-lookup"><span data-stu-id="c6edb-145">Applies to multidimensional server mode only.</span></span>  
  
 `DefaultPagesCountToReuse`  
 <span data-ttu-id="c6edb-146">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c6edb-146">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `HandleIA64AlignmentFaults`  
 <span data-ttu-id="c6edb-147">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c6edb-147">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MidMemoryPrice`  
 <span data-ttu-id="c6edb-148">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c6edb-148">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MinimumAllocatedMemory`  
 <span data-ttu-id="c6edb-149">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c6edb-149">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `PreAllocate`  
 <span data-ttu-id="c6edb-150">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c6edb-150">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `SessionMemoryLimit`  
 <span data-ttu-id="c6edb-151">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c6edb-151">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `WaitCountIfHighMemory`  
 <span data-ttu-id="c6edb-152">Дополнительное свойство, которое следует изменять только под руководством службы поддержки [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c6edb-152">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6edb-153">См. также:</span><span class="sxs-lookup"><span data-stu-id="c6edb-153">See Also</span></span>  
 <span data-ttu-id="c6edb-154">[Настройка свойств сервера в Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="c6edb-154">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="c6edb-155">Определение режима работы сервера экземпляра служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="c6edb-155">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
