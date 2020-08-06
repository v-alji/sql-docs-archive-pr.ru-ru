---
title: Завершение трассировки (SQL Server Profiler) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], stopping
- stopping traces
ms.assetid: 47c4f33d-63e0-4444-bec8-4c1c91f8e25c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 501ea4a4838f8e2ea42fc475c486466d48020a4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734741"
---
# <a name="stop-a-trace-sql-server-profiler"></a><span data-ttu-id="ba90b-102">остановить трассировку (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="ba90b-102">Stop a Trace (SQL Server Profiler)</span></span>
  <span data-ttu-id="ba90b-103">В этом разделе описано, как остановить выполняющуюся трассировку в приложении [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ba90b-103">This topic describes how to stop a trace that is running by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
 <span data-ttu-id="ba90b-104">Остановка трассировки приводит к прекращению сбора данных.</span><span class="sxs-lookup"><span data-stu-id="ba90b-104">Stopping a trace stops data from being captured.</span></span> <span data-ttu-id="ba90b-105">После остановки трассировки ее нельзя перезапустить без утраты уже собранных данных, если эти данные не были сохранены в файле или таблице трассировки.</span><span class="sxs-lookup"><span data-stu-id="ba90b-105">After a trace is stopped, it cannot be restarted without losing previously captured data, unless the data has been captured to a trace file or trace table.</span></span> <span data-ttu-id="ba90b-106">Также можно сохранить собранные данные в таблице или файле после остановки трассировки.</span><span class="sxs-lookup"><span data-stu-id="ba90b-106">You can also save the collected data to a table or file after stopping a trace.</span></span> <span data-ttu-id="ba90b-107">При остановке трассировки все ранее выбранные значения ее свойств остаются неизменными.</span><span class="sxs-lookup"><span data-stu-id="ba90b-107">All trace properties that were previously selected are preserved when a trace is stopped.</span></span> <span data-ttu-id="ba90b-108">Остановив трассировку, можно изменить ее имя, события, столбцы и фильтры.</span><span class="sxs-lookup"><span data-stu-id="ba90b-108">When a trace is stopped, you can change the name, events, columns, and filters.</span></span>  
  
### <a name="to-stop-a-trace"></a><span data-ttu-id="ba90b-109">Прекращение трассировки</span><span class="sxs-lookup"><span data-stu-id="ba90b-109">To stop a trace</span></span>  
  
1.  <span data-ttu-id="ba90b-110">Выберите выполняющуюся трассировку</span><span class="sxs-lookup"><span data-stu-id="ba90b-110">Select a trace that is running.</span></span>  
  
2.  <span data-ttu-id="ba90b-111">В меню **Файл** выберите пункт **Остановить трассировку**.</span><span class="sxs-lookup"><span data-stu-id="ba90b-111">On the **File** menu, click **Stop Trace**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba90b-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="ba90b-112">See Also</span></span>  
 [<span data-ttu-id="ba90b-113">Приложение SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="ba90b-113">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
