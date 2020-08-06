---
title: Проектирование агрегатов (Analysis Services-многомерные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- aggregations [Analysis Services], partitions
- partitions [Analysis Services], aggregations
ms.assetid: 3072b7e0-6961-42ad-a287-16f391f2cec4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 18d8ea1adb645868a11b70966ba3be2ed1764fbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668468"
---
# <a name="designing-aggregations-analysis-services---multidimensional"></a><span data-ttu-id="21c2a-102">Проектирование агрегатов (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="21c2a-102">Designing Aggregations (Analysis Services - Multidimensional)</span></span>
  <span data-ttu-id="21c2a-103">Агрегатами называются предварительно вычисленные сводки по данным куба, помогающие службам [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ускорить выполнение запросов.</span><span class="sxs-lookup"><span data-stu-id="21c2a-103">Aggregations are precalculated summaries of cube data that help enable [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to provide rapid query responses.</span></span>  
  
 <span data-ttu-id="21c2a-104">Для настройки параметров хранения и проектирования статистических схем для секции применяется мастер статистических схем.</span><span class="sxs-lookup"><span data-stu-id="21c2a-104">To set storage options and design aggregations for a partition, use the Aggregation Design Wizard.</span></span> <span data-ttu-id="21c2a-105">Мастер работает с одной секцией группы мер, поэтому каждую секцию можно настроить по-своему.</span><span class="sxs-lookup"><span data-stu-id="21c2a-105">The wizard operates on a single partition of a measure group at a time so that you can select different options and designs for each partition.</span></span> <span data-ttu-id="21c2a-106">Мастер руководит настройкой хранилища и проектированием статистических схем для секции.</span><span class="sxs-lookup"><span data-stu-id="21c2a-106">The wizard takes you through steps to configure storage and design aggregation for a partition.</span></span> <span data-ttu-id="21c2a-107">Для получения дополнительных сведений о настройке хранилища см.</span><span class="sxs-lookup"><span data-stu-id="21c2a-107">For more information about configuring storage, see.</span></span>  
  
 <span data-ttu-id="21c2a-108">Выберите метод управления количеством статистических схем, которые будет строить мастер, и запустите проектирование.</span><span class="sxs-lookup"><span data-stu-id="21c2a-108">Select a method for controlling the number of aggregations the wizard will design, and then let the wizard design the aggregations.</span></span>  
  
 <span data-ttu-id="21c2a-109">Задача — спроектировать оптимальное количество статистических схем.</span><span class="sxs-lookup"><span data-stu-id="21c2a-109">The goal is to design the optimal number of aggregations.</span></span> <span data-ttu-id="21c2a-110">Это количество должно не только обеспечивать приемлемое время ответа, но предотвращать лишний рост размеров сегмента.</span><span class="sxs-lookup"><span data-stu-id="21c2a-110">This number should not only provide satisfactory response time, but also prevent excessive partition size.</span></span> <span data-ttu-id="21c2a-111">С увеличением количества статистических схем уменьшается время ответа, но увеличивается пространство, которое требуется для их хранения, и время вычисления.</span><span class="sxs-lookup"><span data-stu-id="21c2a-111">A greater number of aggregations produces faster response times but it also requires more storage space and may take longer to compute.</span></span> <span data-ttu-id="21c2a-112">Кроме того, первые агрегаты, намного сильнее увеличивают производительность, чем последующие.</span><span class="sxs-lookup"><span data-stu-id="21c2a-112">Moreover, as the wizard designs more and more aggregations, earlier aggregations produce considerably larger performance gains than later aggregations.</span></span> <span data-ttu-id="21c2a-113">Уменьшение количества менее полезных агрегатов так же может увеличить производительность.</span><span class="sxs-lookup"><span data-stu-id="21c2a-113">Reduction in less useful aggregations increases performance as well.</span></span> <span data-ttu-id="21c2a-114">Для управления количеством агрегатов, которые проектирует мастер, можно использовать один из следующих методов.</span><span class="sxs-lookup"><span data-stu-id="21c2a-114">You can control the number of aggregations the wizard designs by one of the following methods available in the wizard:</span></span>  
  
-   <span data-ttu-id="21c2a-115">Укажите ограничение на размер пространства для хранения агрегатов.</span><span class="sxs-lookup"><span data-stu-id="21c2a-115">Specify a storage space limit for the aggregations.</span></span>  
  
-   <span data-ttu-id="21c2a-116">Укажите ограничение на увеличение производительности.</span><span class="sxs-lookup"><span data-stu-id="21c2a-116">Specify a performance gain limit.</span></span>  
  
-   <span data-ttu-id="21c2a-117">Вручную остановите работу мастера, когда кривая производительности начнет снижаться до приемлемого уровня увеличения производительности.</span><span class="sxs-lookup"><span data-stu-id="21c2a-117">Stop the wizard manually when the displayed performance versus size curve starts to level off at an acceptable performance gain.</span></span>  
  
-   <span data-ttu-id="21c2a-118">Отмените проектирование агрегатов.</span><span class="sxs-lookup"><span data-stu-id="21c2a-118">Choose not to design aggregations.</span></span>  
  
 <span data-ttu-id="21c2a-119">Чтобы построить хранилище, мастер должен иметь возможность соединяться со службами [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="21c2a-119">To design storage, the wizard must be able to connect to [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] on the target server.</span></span> <span data-ttu-id="21c2a-120">Если службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] не запущены на целевом сервере или процесс проектирования не может к нему подключиться, появится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="21c2a-120">The wizard will display an error message if [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] is not running on the target server or if the storage design process is otherwise unable to connect to the target server.</span></span>  
  
 <span data-ttu-id="21c2a-121">Последний шаг мастера позволяет продолжить или отложить обработку.</span><span class="sxs-lookup"><span data-stu-id="21c2a-121">The final step of the wizard allows you to process or defer processing.</span></span> <span data-ttu-id="21c2a-122">В первом случае будут созданы спроектированные агрегаты, а во втором они будут сохранены для будущей обработки.</span><span class="sxs-lookup"><span data-stu-id="21c2a-122">Processing creates the aggregations you design with the wizard, while deferring processing saves the designed aggregations for future processing, thus allowing design activities to continue without processing.</span></span> <span data-ttu-id="21c2a-123">В зависимости от размеров секции, обработка может занять значительное время.</span><span class="sxs-lookup"><span data-stu-id="21c2a-123">Depending on the size of the partition, processing may take considerable time.</span></span> <span data-ttu-id="21c2a-124">При необходимости можно прервать обработку секции.</span><span class="sxs-lookup"><span data-stu-id="21c2a-124">If you choose, you can interrupt processing a partition.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21c2a-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="21c2a-125">See Also</span></span>  
 [<span data-ttu-id="21c2a-126">Aggregations and Aggregation Designs</span><span class="sxs-lookup"><span data-stu-id="21c2a-126">Aggregations and Aggregation Designs</span></span>](../multidimensional-models-olap-logical-cube-objects/aggregations-and-aggregation-designs.md)  
  
  
