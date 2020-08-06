---
title: Воспроизведение одного события за раз (приложение SQL Server Profiler) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- events [SQL Server], replaying single event at a time
- traces [SQL Server], replaying
- replaying traces
ms.assetid: 220fb192-9636-41a2-b15c-62af6cab8fff
author: stevestein
ms.author: sstein
ms.openlocfilehash: 457bc94d9d8eae470fb60b450d30441c07e676df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737262"
---
# <a name="replay-a-single-event-at-a-time-sql-server-profiler"></a><span data-ttu-id="bd3ab-102">воспроизвести одиночное событие за раз (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="bd3ab-102">Replay a Single Event at a Time (SQL Server Profiler)</span></span>
  <span data-ttu-id="bd3ab-103">В данном разделе описывается, как с помощью приложения [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]воспроизвести одно событие за раз в файл трассировки воспроизведения или таблицу.</span><span class="sxs-lookup"><span data-stu-id="bd3ab-103">This topic describes how to replay one event at a time in a replay trace file or table by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-replay-a-single-event-at-a-time"></a><span data-ttu-id="bd3ab-104">Вспроизведение одиночное события за раз</span><span class="sxs-lookup"><span data-stu-id="bd3ab-104">To replay a single event at a time</span></span>  
  
1.  <span data-ttu-id="bd3ab-105">Откройте файл трассировки или таблицу трассировки, которые необходимо воспроизвести.</span><span class="sxs-lookup"><span data-stu-id="bd3ab-105">Open the trace file or trace table you want to replay.</span></span> <span data-ttu-id="bd3ab-106">Дополнительные сведения см. в статье [Открыть файл трассировки (приложение SQL Server Profiler)](open-a-trace-file-sql-server-profiler.md) или в помощник по настройке ядра СУБД [Открыть таблицу трассировки (приложение SQL Server Profiler)](open-a-trace-table-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="bd3ab-106">For more information, see [Open a Trace File &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) or [Open a Trace Table &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span></span>  
  
     <span data-ttu-id="bd3ab-107">Убедитесь, что открытый файл трассировки или открытая таблица содержат классы событий, которые необходимо воспроизвести.</span><span class="sxs-lookup"><span data-stu-id="bd3ab-107">Make sure that the trace file or table you open contains the event classes necessary for replay.</span></span> <span data-ttu-id="bd3ab-108">Дополнительные сведения см. в разделе [Replay Requirements](replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd3ab-108">For more information, see [Replay Requirements](replay-requirements.md).</span></span>  
  
2.  <span data-ttu-id="bd3ab-109">В меню **Воспроизведение** выберите **Шаг**и подключитесь к экземпляру сервера, на котором предстоит воспроизвести трассировку.</span><span class="sxs-lookup"><span data-stu-id="bd3ab-109">On the **Replay** menu, click **Step**, and connect to the server instance where you want to replay the trace.</span></span>  
  
3.  <span data-ttu-id="bd3ab-110">В диалоговом окне **Конфигурация воспроизведения** проверьте настройки и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="bd3ab-110">In the **Replay Configuration** dialog box, verify the settings, and then click **OK**.</span></span> <span data-ttu-id="bd3ab-111">Дополнительные сведения о задании параметров в диалоговом окне **Конфигурация воспроизведения** см. в разделе [Воспроизведение файла трассировки (SQL Server Profiler)](replay-a-trace-file-sql-server-profiler.md) или [Воспроизведение таблицы трассировки (SQL Server Profiler)](replay-a-trace-table-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="bd3ab-111">For more information about specifying settings on the **Replay Configuration** dialog box, see [Replay a Trace File &#40;SQL Server Profiler&#41;](replay-a-trace-file-sql-server-profiler.md) or [Replay a Trace Table &#40;SQL Server Profiler&#41;](replay-a-trace-table-sql-server-profiler.md).</span></span>  
  
4.  <span data-ttu-id="bd3ab-112">Чтобы воспроизвести первое событие, нажмите кнопку **OK** в диалоговом окне **Конфигурация воспроизведения** .</span><span class="sxs-lookup"><span data-stu-id="bd3ab-112">To replay the first event, click **OK** in the **Replay Configuration** dialog box.</span></span>  
  
5.  <span data-ttu-id="bd3ab-113">Чтобы воспроизвести следующие события, в меню **Воспроизведение** выберите **Шаг**или нажмите клавишу F10.</span><span class="sxs-lookup"><span data-stu-id="bd3ab-113">To replay subsequent events, on the **Replay** menu, click **Step**, or press F10.</span></span> <span data-ttu-id="bd3ab-114">Повторно нажимайте **Шаг** или клавишу F10 для каждого события.</span><span class="sxs-lookup"><span data-stu-id="bd3ab-114">Repeat clicking **Step** or pressing F10 for each event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd3ab-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="bd3ab-115">See Also</span></span>  
 <span data-ttu-id="bd3ab-116">[Воспроизведение трассировок](replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="bd3ab-116">[Replay Traces](replay-traces.md) </span></span>  
 [<span data-ttu-id="bd3ab-117">Приложение SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="bd3ab-117">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
