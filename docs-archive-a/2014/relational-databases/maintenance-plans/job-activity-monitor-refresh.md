---
title: Обновление монитора активности заданий | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.jobactivitymon.refresh.f1
ms.assetid: 413a368e-fd2b-4e1f-b370-002cdbc85bab
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5f290825f8a776c954ef802b184f7600aea5dc9d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664195"
---
# <a name="job-activity-monitor-refresh"></a><span data-ttu-id="9ff62-102">Обновление монитора активности заданий</span><span class="sxs-lookup"><span data-stu-id="9ff62-102">Job Activity Monitor Refresh</span></span>
  <span data-ttu-id="9ff62-103">Диалоговое окно **Настройки обновления** используется для настройки частоты получения монитором активности заданий новых данных об активности сервера.</span><span class="sxs-lookup"><span data-stu-id="9ff62-103">Use the **Refresh Settings** dialog box to configure how often Job Activity Monitor obtains new information about server activity.</span></span> <span data-ttu-id="9ff62-104">Монитор активности заданий должен выполнять запросы на контролируемом сервере для получения данных для сетки монитора активности заданий.</span><span class="sxs-lookup"><span data-stu-id="9ff62-104">Job Activity Monitor must run queries on the monitored server to obtain information for the Job Activity Monitor grid.</span></span> <span data-ttu-id="9ff62-105">Если интервал автообновления составляет менее 30 секунд, время выполнения этих запросов может влиять на производительность сервера.</span><span class="sxs-lookup"><span data-stu-id="9ff62-105">When the auto-refresh interval is set to less than 30 seconds, the time used to run these queries can affect server performance.</span></span>  
  
 <span data-ttu-id="9ff62-106">Для открытия данного диалогового окна выберите пункт **Просмотреть настройки обновления**в разделе **Состояние** монитора активности заданий.</span><span class="sxs-lookup"><span data-stu-id="9ff62-106">To open this dialog, click **View refresh settings**, in the **Status** section of Job Activity Monitor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9ff62-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="9ff62-107">Options</span></span>  
 <span data-ttu-id="9ff62-108">**Автоматическое обновление каждые**</span><span class="sxs-lookup"><span data-stu-id="9ff62-108">**Auto-refresh every**</span></span>  
 <span data-ttu-id="9ff62-109">Выберите, чтобы включить автоматическое обновление сведений монитора активности.</span><span class="sxs-lookup"><span data-stu-id="9ff62-109">Check to initiate automatic refreshing of Activity Monitor information.</span></span> <span data-ttu-id="9ff62-110">По умолчанию эта настройка отключена.</span><span class="sxs-lookup"><span data-stu-id="9ff62-110">This is off by default.</span></span>  
  
 <span data-ttu-id="9ff62-111">**секунд**</span><span class="sxs-lookup"><span data-stu-id="9ff62-111">**seconds**</span></span>  
 <span data-ttu-id="9ff62-112">Количество секунд между попытками автообновления.</span><span class="sxs-lookup"><span data-stu-id="9ff62-112">The number of seconds between auto-refresh attempts.</span></span> <span data-ttu-id="9ff62-113">Значение по умолчанию — 60 секунд.</span><span class="sxs-lookup"><span data-stu-id="9ff62-113">Defaults to 60 seconds.</span></span> <span data-ttu-id="9ff62-114">При установке значения 5 или менее обновление будет производиться каждые 5 секунд.</span><span class="sxs-lookup"><span data-stu-id="9ff62-114">Refreshes every 5 seconds when set to 5 or less.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ff62-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="9ff62-115">See Also</span></span>  
 [<span data-ttu-id="9ff62-116">Наблюдение за активностью заданий</span><span class="sxs-lookup"><span data-stu-id="9ff62-116">Monitor Job Activity</span></span>](../../ssms/agent/monitor-job-activity.md)  
  
  
