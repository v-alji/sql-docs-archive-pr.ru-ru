---
title: Воспроизведение сценария Transact-SQL (приложение SQL Server Profiler) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], replaying
- scripts [SQL Server], traces
- replaying traces
ms.assetid: 9c0eb222-e6e3-4bc1-a25f-a41e962d361b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5abf22a1201ac927f12ef9e4cfdd1f6d3026d00a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737247"
---
# <a name="replay-a-transact-sql-script-sql-server-profiler"></a><span data-ttu-id="2d438-102">воспроизвести скрипт на языке Transact-SQL (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="2d438-102">Replay a Transact-SQL Script (SQL Server Profiler)</span></span>
  <span data-ttu-id="2d438-103">При тестировании возможных решений для устранения ошибки производительности используйте приложение [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] для воспроизведения скриптов на языке [!INCLUDE[tsql](../../includes/tsql-md.md)] и сравните производительность до внесения изменений и после внесенных изменений.</span><span class="sxs-lookup"><span data-stu-id="2d438-103">When you test possible solutions to a performance problem, use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to replay [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts, and compare performance before and after your changes.</span></span>  
  
### <a name="to-replay-a-transact-sql-script"></a><span data-ttu-id="2d438-104">Воспроизведение скрипта на языке Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2d438-104">To replay a Transact-SQL script</span></span>  
  
1.  <span data-ttu-id="2d438-105">В меню **Файл** выберите **Открыть**и щелкните **Файл скрипта**.</span><span class="sxs-lookup"><span data-stu-id="2d438-105">On the **File** menu, point to **Open**, and then click **Script File**.</span></span>  
  
2.  <span data-ttu-id="2d438-106">Выберите файл скрипта на языке [!INCLUDE[tsql](../../includes/tsql-md.md)] , который нужно открыть.</span><span class="sxs-lookup"><span data-stu-id="2d438-106">Select the [!INCLUDE[tsql](../../includes/tsql-md.md)] script file you want to open.</span></span> <span data-ttu-id="2d438-107">Убедитесь, что скрипт на языке [!INCLUDE[tsql](../../includes/tsql-md.md)] содержит события, необходимые для воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="2d438-107">Make sure that the [!INCLUDE[tsql](../../includes/tsql-md.md)] script contains events necessary for replay.</span></span> <span data-ttu-id="2d438-108">Дополнительные сведения см. в разделе [Replay Requirements](replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d438-108">For more information, see [Replay Requirements](replay-requirements.md).</span></span>  
  
3.  <span data-ttu-id="2d438-109">В меню **Воспроизведение** выберите **Пуск**и подключитесь к серверу, на котором нужно воспроизвести скрипт.</span><span class="sxs-lookup"><span data-stu-id="2d438-109">On the **Replay** menu, click **Start**, and connect to the server where you want to replay the script.</span></span>  
  
4.  <span data-ttu-id="2d438-110">В диалоговом окне **Конфигурация воспроизведения** проверьте настройки и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2d438-110">In the **Replay Configuration** dialog box, verify the settings, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d438-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="2d438-111">See Also</span></span>  
 <span data-ttu-id="2d438-112">[Воспроизведение трассировок](replay-traces.md) </span><span class="sxs-lookup"><span data-stu-id="2d438-112">[Replay Traces](replay-traces.md) </span></span>  
 [<span data-ttu-id="2d438-113">Приложение SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="2d438-113">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
