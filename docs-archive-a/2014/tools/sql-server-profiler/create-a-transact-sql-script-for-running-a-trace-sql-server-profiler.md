---
title: Создание сценария Transact-SQL для выполнения трассировки (приложение SQL Server Profiler) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], running
- scripts [SQL Server], traces
ms.assetid: 6b0e2519-998d-40d5-b8ba-5e6a773f91a6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3d4b4bebb2a3e05e3de12e59c53ccca9c980afd5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727577"
---
# <a name="create-a-transact-sql-script-for-running-a-trace-sql-server-profiler"></a><span data-ttu-id="7c4f6-102">создать скрипт Transact-SQL для выполнения трассировки (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="7c4f6-102">Create a Transact-SQL Script for Running a Trace (SQL Server Profiler)</span></span>
  <span data-ttu-id="7c4f6-103">В данном подразделе описан процесс создания скрипта Transact-SQL из существующего файла или таблицы трассировки при помощи приложения [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7c4f6-103">This topic describes how to create a Transact-SQL script from an existing trace file or table by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-create-a-transact-sql-script-to-run-a-trace"></a><span data-ttu-id="7c4f6-104">Создание скрипта Transact-SQL для запуска трассировки</span><span class="sxs-lookup"><span data-stu-id="7c4f6-104">To create a Transact-SQL script to run a trace</span></span>  
  
1.  <span data-ttu-id="7c4f6-105">Откройте таблицу или файл трассировки.</span><span class="sxs-lookup"><span data-stu-id="7c4f6-105">Open a trace file or table.</span></span> <span data-ttu-id="7c4f6-106">Дополнительные сведения см. в статье [Открыть файл трассировки (приложение SQL Server Profiler)](open-a-trace-file-sql-server-profiler.md) или в помощник по настройке ядра СУБД [Открыть таблицу трассировки (приложение SQL Server Profiler)](open-a-trace-table-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="7c4f6-106">For more information, see [Open a Trace File &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) or [Open a Trace Table &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span></span>  
  
2.  <span data-ttu-id="7c4f6-107">В меню**Файл**выберите команду **Экспорт**, затем **Создать определение трассировки**и щелкните версию, соответствующую серверу, который необходимо трассировать.</span><span class="sxs-lookup"><span data-stu-id="7c4f6-107">On the**File**menu, point to **Export**, point to **Script Trace Definition**, and then click the version that corresponds to the server you want to trace.</span></span>  
  
3.  <span data-ttu-id="7c4f6-108">В диалоговом окне **Сохранить как** введите имя файла скрипта и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7c4f6-108">In the **Save As** dialog box, enter a name for the script file, and then click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c4f6-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="7c4f6-109">See Also</span></span>  
 <span data-ttu-id="7c4f6-110">[Шаблоны и разрешения приложения SQL Server Profiler](sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="7c4f6-110">[SQL Server Profiler Templates and Permissions](sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="7c4f6-111">Приложение SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="7c4f6-111">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
