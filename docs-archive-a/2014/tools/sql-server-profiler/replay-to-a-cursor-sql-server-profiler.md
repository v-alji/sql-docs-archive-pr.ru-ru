---
title: Воспроизвести до курсора (SQL Server Profiler) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- replaying cursors
- traces [SQL Server], replaying
- replaying traces
ms.assetid: 89eadc41-4424-4a1c-ba61-0b52c851cdb1
author: stevestein
ms.author: sstein
ms.openlocfilehash: bfc5ba06b60100bf8ecc8d04909371021a5b00e5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737232"
---
# <a name="replay-to-a-cursor-sql-server-profiler"></a><span data-ttu-id="40a0f-102">воспроизвести до курсора (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="40a0f-102">Replay to a Cursor (SQL Server Profiler)</span></span>
  <span data-ttu-id="40a0f-103">В этом подразделе описывается воспроизведение файлов или таблиц трассировки, которые были приостановлены по достижении курсора при помощи приложения [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="40a0f-103">This topic describes how to replay trace files or tables that pause when a cursor is reached by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="40a0f-104">Приостановка трассировок курсоров поддерживает отладку, так как существует возможность разбиения воспроизведения длинных скриптов трассировки на короткие сегменты, которые могут анализироваться по шагам.</span><span class="sxs-lookup"><span data-stu-id="40a0f-104">Pausing traces at cursors supports debugging because you can break the replay of long trace scripts into short segments that can be analyzed incrementally.</span></span>  
  
### <a name="to-replay-to-the-cursor"></a><span data-ttu-id="40a0f-105">Воспроизведение до курсора</span><span class="sxs-lookup"><span data-stu-id="40a0f-105">To replay to the cursor</span></span>  
  
1.  <span data-ttu-id="40a0f-106">Откройте файл трассировки или таблицу трассировки, которые необходимо воспроизвести.</span><span class="sxs-lookup"><span data-stu-id="40a0f-106">Open the trace file or trace table you want to replay.</span></span> <span data-ttu-id="40a0f-107">Дополнительные сведения см. в статье [Открыть файл трассировки (приложение SQL Server Profiler)](open-a-trace-file-sql-server-profiler.md) или в помощник по настройке ядра СУБД [Открыть таблицу трассировки (приложение SQL Server Profiler)](open-a-trace-table-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="40a0f-107">For more information, see [Open a Trace File &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) or [Open a Trace Table &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span></span>  
  
     <span data-ttu-id="40a0f-108">Убедитесь, что открытый файл трассировки или открытая таблица содержат классы событий, которые необходимо воспроизвести.</span><span class="sxs-lookup"><span data-stu-id="40a0f-108">Make sure that the trace file or table you open contains the event classes necessary for replay.</span></span> <span data-ttu-id="40a0f-109">Дополнительные сведения см. в разделе [Replay Requirements](replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40a0f-109">For more information, see [Replay Requirements](replay-requirements.md).</span></span>  
  
2.  <span data-ttu-id="40a0f-110">В окне трассировки выберите событие.</span><span class="sxs-lookup"><span data-stu-id="40a0f-110">In the trace window, click an event.</span></span>  
  
3.  <span data-ttu-id="40a0f-111">В меню **Воспроизведение** выберите пункт **Выполнить до курсора**и подключитесь к серверу, на котором хотите воспроизвести трассировку.</span><span class="sxs-lookup"><span data-stu-id="40a0f-111">On the **Replay** menu, click **Run to Cursor**, and then connect to the server where you want to replay the trace.</span></span>  
  
4.  <span data-ttu-id="40a0f-112">В диалоговом окне **Конфигурация воспроизведения** проверьте настройки и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="40a0f-112">In the **Replay Configuration** dialog box, verify the settings, and then click **OK**.</span></span>  
  
     <span data-ttu-id="40a0f-113">Воспроизведение начинается, останавливаясь по достижении первого курсора.</span><span class="sxs-lookup"><span data-stu-id="40a0f-113">The replay starts, pausing when the first cursor is reached.</span></span>  
  
5.  <span data-ttu-id="40a0f-114">Для продолжения трассировки нажмите клавишу F5.</span><span class="sxs-lookup"><span data-stu-id="40a0f-114">Press F5 to resume the trace.</span></span>  
  
6.  <span data-ttu-id="40a0f-115">Повторяйте шаг 5 до завершения трассировки.</span><span class="sxs-lookup"><span data-stu-id="40a0f-115">Repeat Step 5 through the end of the trace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40a0f-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="40a0f-116">See Also</span></span>  
 <span data-ttu-id="40a0f-117">[Воспроизведение нагрузки до точки останова (приложение SQL Server Profiler)](replay-to-a-breakpoint-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="40a0f-117">[Replay to a Breakpoint &#40;SQL Server Profiler&#41;](replay-to-a-breakpoint-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="40a0f-118">[Воспроизведение трассировок](replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="40a0f-118">[Replay Traces](replay-traces.md) </span></span>  
 [<span data-ttu-id="40a0f-119">Приложение SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="40a0f-119">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
