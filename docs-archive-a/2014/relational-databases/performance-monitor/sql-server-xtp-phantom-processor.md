---
title: Искусственный процессор XTP | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: 0f691b3d-a8fd-4459-ad21-2cfc8574a8c0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 14158b7097427b6704cf5e747fa998a11217ecd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730569"
---
# <a name="xtp-phantom-processor"></a><span data-ttu-id="b5b03-102">XTP Phantom Processor</span><span class="sxs-lookup"><span data-stu-id="b5b03-102">XTP Phantom Processor</span></span>
  <span data-ttu-id="b5b03-103">Объект производительности XTP Phantom Processor содержит счетчики, относящиеся к подсистеме обработки фантомов механизма XTP.</span><span class="sxs-lookup"><span data-stu-id="b5b03-103">The XTP Phantom Processor performance object contains counters related to the XTP engine's phantom processing subsystem.</span></span> <span data-ttu-id="b5b03-104">Этот компонент отвечает за обнаружение фантомных строк в транзакциях, выполняемых на уровне изоляции SERIALIZABLE.</span><span class="sxs-lookup"><span data-stu-id="b5b03-104">This component is responsible for detecting phantom rows in transactions running at the SERIALIZABLE isolation level.</span></span>  
  
 <span data-ttu-id="b5b03-105">В этой таблице описаны счетчики объекта **XTP Phantom Processor** .</span><span class="sxs-lookup"><span data-stu-id="b5b03-105">This table describes the **XTP Phantom Processor** counters.</span></span>  
  
|<span data-ttu-id="b5b03-106">Счетчик</span><span class="sxs-lookup"><span data-stu-id="b5b03-106">Counter</span></span>|<span data-ttu-id="b5b03-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b5b03-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b5b03-108">**Число попыток сканирования «пыльных углов»/с (от Phantom)**</span><span class="sxs-lookup"><span data-stu-id="b5b03-108">**Dusty corner scan retries/sec (Phantom-issued)**</span></span>|<span data-ttu-id="b5b03-109">Число повторных попыток сканирования из-за конфликтов записи при обработке «пыльных углов», выданное Phantom Processor (в среднем), в секунду</span><span class="sxs-lookup"><span data-stu-id="b5b03-109">The number of scan retries due to write conflicts during dusty corner sweeps issued by the phantom processor (on average), per second.</span></span> <span data-ttu-id="b5b03-110">Это счетчик очень низкого уровня, не предназначенный для пользователей.</span><span class="sxs-lookup"><span data-stu-id="b5b03-110">This is a very low-level counter, not intended for customer use.</span></span>|  
|<span data-ttu-id="b5b03-111">**Удалено истекших фантомных строк/с**</span><span class="sxs-lookup"><span data-stu-id="b5b03-111">**Phantom expired rows removed/sec**</span></span>|<span data-ttu-id="b5b03-112">Число просроченных строк, удаленных фантомными сканированиями (в среднем), в секунду.</span><span class="sxs-lookup"><span data-stu-id="b5b03-112">The number of expired rows removed by phantom scans (on average), per second.</span></span>|  
|<span data-ttu-id="b5b03-113">**Количество затронутых фантомных просроченных строк/с**</span><span class="sxs-lookup"><span data-stu-id="b5b03-113">**Phantom expired rows touched/sec**</span></span>|<span data-ttu-id="b5b03-114">Число просроченных строк, затронутых фантомными сканированиями (в среднем), в секунду.</span><span class="sxs-lookup"><span data-stu-id="b5b03-114">The number of expired rows touched by phantom scans (on average), per second.</span></span>|  
|<span data-ttu-id="b5b03-115">**Количество затронутых фантомных строк с истекающим сроком действия /с**</span><span class="sxs-lookup"><span data-stu-id="b5b03-115">**Phantom expiring rows touched/sec**</span></span>|<span data-ttu-id="b5b03-116">Число строк с истекающим сроком действия, затронутых фантомными сканированиями (в среднем), в секунду.</span><span class="sxs-lookup"><span data-stu-id="b5b03-116">The number of expiring rows touched by phantom scans (on average), per second.</span></span>|  
|<span data-ttu-id="b5b03-117">**Затронутых фантомных строк/с**</span><span class="sxs-lookup"><span data-stu-id="b5b03-117">**Phantom rows touched/sec**</span></span>|<span data-ttu-id="b5b03-118">Число строк, затронутых фантомными сканированиями (в среднем), в секунду.</span><span class="sxs-lookup"><span data-stu-id="b5b03-118">The number of rows touched by phantom scans (on average), per second.</span></span>|  
|<span data-ttu-id="b5b03-119">**Запущено фантомных сканирований/с**</span><span class="sxs-lookup"><span data-stu-id="b5b03-119">**Phantom scans started/sec**</span></span>|<span data-ttu-id="b5b03-120">Число начатых фантомных сканирований (в среднем), в секунду.</span><span class="sxs-lookup"><span data-stu-id="b5b03-120">The number of phantom scans started (on average), per second.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b5b03-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="b5b03-121">See Also</span></span>  
 [<span data-ttu-id="b5b03-122">Счетчики производительности XTP &#40;в памяти OLTP&#41;</span><span class="sxs-lookup"><span data-stu-id="b5b03-122">XTP &#40;In-Memory OLTP&#41; Performance Counters</span></span>](../../integration-services/performance/performance-counters.md)  
  
  
