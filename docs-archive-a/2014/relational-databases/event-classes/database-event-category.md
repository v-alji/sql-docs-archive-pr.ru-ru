---
title: Категория событий Database | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- event classes [SQL Server], Database event category
- Database event category [SQL Server]
- SQL Server event classes, Database event category
ms.assetid: b61af738-f144-4992-b0b2-d44cb7240991
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2860e1434611393c941a639280343f736073c709
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666056"
---
# <a name="database-event-category"></a><span data-ttu-id="43320-102">Категория событий Database</span><span class="sxs-lookup"><span data-stu-id="43320-102">Database Event Category</span></span>
  <span data-ttu-id="43320-103">В категории событий **База данных** содержатся классы событий для контроля компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="43320-103">The **Database** event category contains event classes to monitor the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="43320-104">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="43320-104">In This Section</span></span>  
  
|<span data-ttu-id="43320-105">Раздел</span><span class="sxs-lookup"><span data-stu-id="43320-105">Topic</span></span>|<span data-ttu-id="43320-106">Description</span><span class="sxs-lookup"><span data-stu-id="43320-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="43320-107">Класс событий Data File Auto Grow</span><span class="sxs-lookup"><span data-stu-id="43320-107">Data File Auto Grow Event Class</span></span>](data-file-auto-grow-event-class.md)|<span data-ttu-id="43320-108">Указывает на то, что размер файла данных увеличивается автоматически.</span><span class="sxs-lookup"><span data-stu-id="43320-108">Indicates that the data file grew automatically.</span></span> <span data-ttu-id="43320-109">Это событие не происходит при явном увеличении файла данных с помощью инструкции ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="43320-109">This event is not triggered if the data file is grown explicitly through ALTER DATABASE.</span></span>|  
|[<span data-ttu-id="43320-110">Класс событий Data File Auto Shrink</span><span class="sxs-lookup"><span data-stu-id="43320-110">Data File Auto Shrink Event Class</span></span>](data-file-auto-shrink-event-class.md)|<span data-ttu-id="43320-111">Указывает на то, что файл данных был сжат.</span><span class="sxs-lookup"><span data-stu-id="43320-111">Indicates that the data file has been shrunk.</span></span>|  
|[<span data-ttu-id="43320-112">Класс событий Database Mirroring Connection</span><span class="sxs-lookup"><span data-stu-id="43320-112">Database Mirroring Connection Event Class</span></span>](database-mirroring-connection-event-class.md)|<span data-ttu-id="43320-113">Событие, формируемое для уведомления о состоянии транспортного соединения для зеркального отображения базы данных.</span><span class="sxs-lookup"><span data-stu-id="43320-113">An event generated to report the status of a transport connection for database mirroring.</span></span>|  
|[<span data-ttu-id="43320-114">Класс событий Database Mirroring State Change</span><span class="sxs-lookup"><span data-stu-id="43320-114">Database Mirroring State Change Event Class</span></span>](database-mirroring-state-change-event-class.md)|<span data-ttu-id="43320-115">Указывает, когда изменяется состояние зеркальной базы данных.</span><span class="sxs-lookup"><span data-stu-id="43320-115">Indicates when the state of a mirrored database changes.</span></span>|  
|[<span data-ttu-id="43320-116">Класс событий Database Suspect Data Page</span><span class="sxs-lookup"><span data-stu-id="43320-116">Database Suspect Data Page Event Class</span></span>](database-suspect-data-page-event-class.md)|<span data-ttu-id="43320-117">Указывает, что страница добавлена в таблицу **suspect_pages** базы данных **msdb** .</span><span class="sxs-lookup"><span data-stu-id="43320-117">Indicates when a page is added to the **suspect_pages** table in the **msdb** database.</span></span>|  
|[<span data-ttu-id="43320-118">Класс событий Log File Auto Grow</span><span class="sxs-lookup"><span data-stu-id="43320-118">Log File Auto Grow Event Class</span></span>](log-file-auto-grow-event-class.md)|<span data-ttu-id="43320-119">Указывает на то, что размер файла журнала был сжат автоматически.</span><span class="sxs-lookup"><span data-stu-id="43320-119">Indicates that the log file grew automatically.</span></span> <span data-ttu-id="43320-120">Это событие не происходит при явном увеличении файла журнала с помощью инструкции ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="43320-120">This event is not triggered if the log file is grown explicitly through ALTER DATABASE.</span></span>|  
|[<span data-ttu-id="43320-121">Класс событий Log File Auto Shrink</span><span class="sxs-lookup"><span data-stu-id="43320-121">Log File Auto Shrink Event Class</span></span>](log-file-auto-shrink-event-class.md)|<span data-ttu-id="43320-122">Указывает на то, что размер файла журнала был сжат автоматически.</span><span class="sxs-lookup"><span data-stu-id="43320-122">Indicates that the log file grew automatically.</span></span> <span data-ttu-id="43320-123">Это событие не происходит при явном сжатии файла журнала с помощью инструкции ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="43320-123">This event is not triggered if the log file shrinks explicitly through ALTER DATABASE.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="43320-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="43320-124">See Also</span></span>  
 [<span data-ttu-id="43320-125">Расширенные события</span><span class="sxs-lookup"><span data-stu-id="43320-125">Extended Events</span></span>](../extended-events/extended-events.md)  
  
  
