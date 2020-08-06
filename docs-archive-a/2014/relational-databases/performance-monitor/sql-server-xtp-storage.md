---
title: Хранилище XTP | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: 4070580b-880d-4f4c-abcc-626a4fe0c9a2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: efd4a9eba36060d3d4bab9b371678ab2b2c409ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664891"
---
# <a name="xtp-storage"></a><span data-ttu-id="a3c29-102">Хранилище XTP</span><span class="sxs-lookup"><span data-stu-id="a3c29-102">XTP Storage</span></span>
  <span data-ttu-id="a3c29-103">Объект производительности XTP Storage содержит счетчики, относящиеся к хранилищу XTP в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a3c29-103">The XTP Storage performance object contains counters related to XTP storage in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="a3c29-104">В данной таблице описаны счетчики **Хранилище XTP** .</span><span class="sxs-lookup"><span data-stu-id="a3c29-104">This table describes the **XTP Storage** counters.</span></span>  
  
|<span data-ttu-id="a3c29-105">Счетчик</span><span class="sxs-lookup"><span data-stu-id="a3c29-105">Counter</span></span>|<span data-ttu-id="a3c29-106">Описание</span><span class="sxs-lookup"><span data-stu-id="a3c29-106">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a3c29-107">**Закрытые контрольные точки**</span><span class="sxs-lookup"><span data-stu-id="a3c29-107">**Checkpoints Closed**</span></span>|<span data-ttu-id="a3c29-108">Количество закрытых контрольных точек, подсчитанное агентом в сети</span><span class="sxs-lookup"><span data-stu-id="a3c29-108">Count of checkpoints closed done by online agent.</span></span>|  
|<span data-ttu-id="a3c29-109">**Выполненные контрольные точки**</span><span class="sxs-lookup"><span data-stu-id="a3c29-109">**Checkpoints Completed**</span></span>|<span data-ttu-id="a3c29-110">Количество контрольных точек, обработанных потоком контрольных точек в режиме «вне сети».</span><span class="sxs-lookup"><span data-stu-id="a3c29-110">Count of checkpoints processed by offline checkpoint thread.</span></span>|  
|<span data-ttu-id="a3c29-111">**Выполненные основные слияния**</span><span class="sxs-lookup"><span data-stu-id="a3c29-111">**Core Merges Completed**</span></span>|<span data-ttu-id="a3c29-112">Число основных слияний, выполненных рабочим потоком слияния.</span><span class="sxs-lookup"><span data-stu-id="a3c29-112">The number of core merges completed by the merge worker thread.</span></span> <span data-ttu-id="a3c29-113">Эти слияния по-прежнему требуют установки.</span><span class="sxs-lookup"><span data-stu-id="a3c29-113">These merges still need to be installed.</span></span>|  
|<span data-ttu-id="a3c29-114">**Оценка политики слияния**</span><span class="sxs-lookup"><span data-stu-id="a3c29-114">**Merge Policy Evaluations**</span></span>|<span data-ttu-id="a3c29-115">Число оценок политики слияния с момента запуска сервера.</span><span class="sxs-lookup"><span data-stu-id="a3c29-115">The number of merge policy evaluations since the server started.</span></span>|  
|<span data-ttu-id="a3c29-116">**Незавершенные запросы о слиянии**</span><span class="sxs-lookup"><span data-stu-id="a3c29-116">**Merge Requests Outstanding**</span></span>|<span data-ttu-id="a3c29-117">Число запросов о слиянии, которые не были выполнены с момента запуска сервера.</span><span class="sxs-lookup"><span data-stu-id="a3c29-117">The number of merge requests outstanding since the server started.</span></span>|  
|<span data-ttu-id="a3c29-118">**Оставленные слияния**</span><span class="sxs-lookup"><span data-stu-id="a3c29-118">**Merges Abandoned**</span></span>|<span data-ttu-id="a3c29-119">Количество слияний, оставленных из-за сбоя.</span><span class="sxs-lookup"><span data-stu-id="a3c29-119">The number of merges abandoned due to failure.</span></span>|  
|<span data-ttu-id="a3c29-120">**Установленные слияния**</span><span class="sxs-lookup"><span data-stu-id="a3c29-120">**Merges Installed**</span></span>|<span data-ttu-id="a3c29-121">Число успешно установленных слияний.</span><span class="sxs-lookup"><span data-stu-id="a3c29-121">The number of merges successfully installed.</span></span>|  
|<span data-ttu-id="a3c29-122">**Общее число объединенных файлов**</span><span class="sxs-lookup"><span data-stu-id="a3c29-122">**Total Files Merged**</span></span>|<span data-ttu-id="a3c29-123">Общее количество объединенных исходных файлов.</span><span class="sxs-lookup"><span data-stu-id="a3c29-123">The total number of source files merged.</span></span> <span data-ttu-id="a3c29-124">С помощью этого количества можно определить среднее число исходных файлов в слиянии.</span><span class="sxs-lookup"><span data-stu-id="a3c29-124">This count can be used to find the average number of source files in the merge.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a3c29-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="a3c29-125">See Also</span></span>  
 [<span data-ttu-id="a3c29-126">Счетчики производительности XTP &#40;в памяти OLTP&#41;</span><span class="sxs-lookup"><span data-stu-id="a3c29-126">XTP &#40;In-Memory OLTP&#41; Performance Counters</span></span>](../../integration-services/performance/performance-counters.md)  
  
  
