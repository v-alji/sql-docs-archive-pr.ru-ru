---
title: Приостановка трассировки (SQL Server Profiler) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- pausing traces
- temporarily stopping traces
- traces [SQL Server], pausing
- stopping traces
ms.assetid: 432b9b0c-b5e7-47f3-a71b-310fb3bf2445
author: stevestein
ms.author: sstein
ms.openlocfilehash: cdc9dbbd01099b1d33787a72b0bd59b65cea722e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727569"
---
# <a name="pause-a-trace-sql-server-profiler"></a><span data-ttu-id="7f26d-102">приостановить трассировки (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="7f26d-102">Pause a Trace (SQL Server Profiler)</span></span>
  <span data-ttu-id="7f26d-103">При приостановке трассировки дальнейший захват событий прекращается до ее возобновления.</span><span class="sxs-lookup"><span data-stu-id="7f26d-103">Pausing a trace prevents further event data from being captured until the trace is restarted.</span></span>  
  
 <span data-ttu-id="7f26d-104">Приостановка трассировки приводит к тому, что сбор данных о событиях прекращается до ее перезапуска.</span><span class="sxs-lookup"><span data-stu-id="7f26d-104">When you pause a trace, you prevent event data from being captured until the trace is restarted.</span></span> <span data-ttu-id="7f26d-105">Перезапуск трассировки позволяет возобновить сбор данных.</span><span class="sxs-lookup"><span data-stu-id="7f26d-105">Restarting a trace lets trace operations resume.</span></span> <span data-ttu-id="7f26d-106">При перезапуске трассировки уже зарегистрированные данные не утрачиваются.</span><span class="sxs-lookup"><span data-stu-id="7f26d-106">No previously captured data is lost after a restart.</span></span> <span data-ttu-id="7f26d-107">После перезапуска трассировки сбор данных возобновляется, начиная с текущей точки.</span><span class="sxs-lookup"><span data-stu-id="7f26d-107">When the trace is restarted, data capturing resumes from that point onward.</span></span> <span data-ttu-id="7f26d-108">Приостановив трассировку, можно изменить ее имя, события, столбцы и фильтры.</span><span class="sxs-lookup"><span data-stu-id="7f26d-108">While a trace is paused, you can change the name, events, columns, and filters.</span></span> <span data-ttu-id="7f26d-109">Однако изменить места назначения, в которые отправляются данные трассировки, и соединение с сервером нельзя.</span><span class="sxs-lookup"><span data-stu-id="7f26d-109">However, you cannot change the destinations to which you are sending the trace data, nor change the server connection.</span></span>  
  
### <a name="to-pause-a-trace"></a><span data-ttu-id="7f26d-110">Приостановка трассировки</span><span class="sxs-lookup"><span data-stu-id="7f26d-110">To pause a trace</span></span>  
  
1.  <span data-ttu-id="7f26d-111">Выберите окно, содержащее выполняющуюся трассировку.</span><span class="sxs-lookup"><span data-stu-id="7f26d-111">Select a window that contains a running trace.</span></span>  
  
2.  <span data-ttu-id="7f26d-112">В меню **Файл** выберите пункт **Приостановить трассировку**.</span><span class="sxs-lookup"><span data-stu-id="7f26d-112">On the **File** menu, click **Pause Trace**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f26d-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="7f26d-113">See Also</span></span>  
 [<span data-ttu-id="7f26d-114">Приложение SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="7f26d-114">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
