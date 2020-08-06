---
title: Удаление трассировки (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], deleting
- removing traces
- deleting traces
ms.assetid: a5502814-b281-42dd-b885-5c9368025ae6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b3551cff36ef6e2c2e9cc6a4d9b7056ae44cb950
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664824"
---
# <a name="delete-a-trace-transact-sql"></a><span data-ttu-id="5ee44-102">удалить трассировку (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="5ee44-102">Delete a Trace (Transact-SQL)</span></span>
  <span data-ttu-id="5ee44-103">В этом подразделе описано использование хранимых процедур для удаления трассировок.</span><span class="sxs-lookup"><span data-stu-id="5ee44-103">This topic describes how to use stored procedures to delete a trace.</span></span>  
  
 <span data-ttu-id="5ee44-104">Пример использования хранимых процедур трассировки см. в разделе [Создание трассировки (Transact-SQL)](create-a-trace-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="5ee44-104">For an example of using trace stored procedures, see [Create a Trace &#40;Transact-SQL&#41;](create-a-trace-transact-sql.md).</span></span>  
  
### <a name="to-delete-a-trace"></a><span data-ttu-id="5ee44-105">Удаление трассировки</span><span class="sxs-lookup"><span data-stu-id="5ee44-105">To delete a trace</span></span>  
  
1.  <span data-ttu-id="5ee44-106">Чтобы остановить трассировку, выполните процедуру **sp_trace_setstatus** , указав параметр **@status =0**.</span><span class="sxs-lookup"><span data-stu-id="5ee44-106">Execute **sp_trace_setstatus** by specifying **@status = 0** to stop the trace.</span></span>  
  
2.  <span data-ttu-id="5ee44-107">Чтобы закрыть трассировку и удалить сведения о ней с сервера, выполните процедуру **sp_trace_setstatus** , указав параметр **@status =2**.</span><span class="sxs-lookup"><span data-stu-id="5ee44-107">Execute **sp_trace_setstatus** by specifying **@status = 2** to close the trace and delete its information from the server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5ee44-108">Перед закрытием трассировка должна быть остановлена.</span><span class="sxs-lookup"><span data-stu-id="5ee44-108">A trace must be stopped first before it can be closed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ee44-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="5ee44-109">See Also</span></span>  
 <span data-ttu-id="5ee44-110">[Хранимая процедура sp_trace_setstatus (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5ee44-110">[sp_trace_setstatus &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql) </span></span>  
 <span data-ttu-id="5ee44-111">[Системные хранимые процедуры (Transact-SQL)](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5ee44-111">[System Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql) </span></span>  
 [<span data-ttu-id="5ee44-112">Хранимые процедуры приложения SQL Server Profiler (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="5ee44-112">SQL Server Profiler Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql)  
  
  
