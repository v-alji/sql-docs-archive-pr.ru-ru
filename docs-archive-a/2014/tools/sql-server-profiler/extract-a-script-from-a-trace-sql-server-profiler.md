---
title: Извлечение сценария из трассировки (приложение SQL Server Profiler) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- scripts [SQL Server], traces
- extracting script from trace [SQL Server]
ms.assetid: 431126a6-ff91-4818-8763-4442152bd571
author: stevestein
ms.author: sstein
ms.openlocfilehash: f6633fafb8a39b189093044ef39694afa601af7c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727566"
---
# <a name="extract-a-script-from-a-trace-sql-server-profiler"></a><span data-ttu-id="fa12f-102">извлечь скрипт из трассировки (приложение SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="fa12f-102">Extract a Script from a Trace (SQL Server Profiler)</span></span>
  <span data-ttu-id="fa12f-103">В этом подразделе описано, как извлечь события [!INCLUDE[tsql](../../includes/tsql-md.md)] из файла или таблицы трассировки и сохранить их в виде скрипта [!INCLUDE[tsql](../../includes/tsql-md.md)] при помощи приложения [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fa12f-103">This topic describes how to extract [!INCLUDE[tsql](../../includes/tsql-md.md)] events from a trace file or table and save them as a [!INCLUDE[tsql](../../includes/tsql-md.md)] script file by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-extract-a-transact-sql-script-from-a-trace-file-or-table"></a><span data-ttu-id="fa12f-104">Извлечение скрипта Transact-SQL из файла или таблицы трассировки:</span><span class="sxs-lookup"><span data-stu-id="fa12f-104">To extract a Transact-SQL script from a trace file or table</span></span>  
  
1.  <span data-ttu-id="fa12f-105">Откройте файл трассировки или таблицы, содержащий события [!INCLUDE[tsql](../../includes/tsql-md.md)] , которые необходимо сохранить в файле скрипта [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fa12f-105">Open a trace file or table that contains [!INCLUDE[tsql](../../includes/tsql-md.md)] events that you want to save to a [!INCLUDE[tsql](../../includes/tsql-md.md)] script file.</span></span> <span data-ttu-id="fa12f-106">Дополнительные сведения см. в статье [Открыть файл трассировки (приложение SQL Server Profiler)](open-a-trace-file-sql-server-profiler.md) или в помощник по настройке ядра СУБД [Открыть таблицу трассировки (приложение SQL Server Profiler)](open-a-trace-table-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="fa12f-106">For more information, see [Open a Trace File &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) or [Open a Trace Table &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span></span>  
  
2.  <span data-ttu-id="fa12f-107">В меню **Файл** выберите пункт **Экспорт**, затем **Извлечь события SQL Server**и щелкните **Извлечь события Transact-SQL**.</span><span class="sxs-lookup"><span data-stu-id="fa12f-107">On the **File** menu, point to **Export**, point to **Extract SQL Server Events**, and then click **Extract Transact-SQL Events**.</span></span>  
  
3.  <span data-ttu-id="fa12f-108">В диалоговом окне **Сохранить как** введите имя файла [!INCLUDE[tsql](../../includes/tsql-md.md)] и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="fa12f-108">In the **Save As** dialog box, type a name for the [!INCLUDE[tsql](../../includes/tsql-md.md)] file, and click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa12f-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="fa12f-109">See Also</span></span>  
 [<span data-ttu-id="fa12f-110">Приложение SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="fa12f-110">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
