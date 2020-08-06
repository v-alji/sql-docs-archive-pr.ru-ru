---
title: Просмотр сохраненной трассировки (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], viewing
- displaying traces
- viewing traces
ms.assetid: 3a95a816-aa89-4d5f-858c-968a9cb3ee87
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f8b67760d575b651b089a6936adc945d74a1c62b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752040"
---
# <a name="view-a-saved-trace-transact-sql"></a><span data-ttu-id="af997-102">просмотреть сохраненную трассировку (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="af997-102">View a Saved Trace (Transact-SQL)</span></span>
  <span data-ttu-id="af997-103">В этом разделе разъясняется, как использовать встроенные функции для просмотра сохраненных трассировок.</span><span class="sxs-lookup"><span data-stu-id="af997-103">This topic describes how to use built-in functions to view a saved trace.</span></span>  
  
### <a name="to-view-a-specific-trace"></a><span data-ttu-id="af997-104">Просмотр конкретной трассировки</span><span class="sxs-lookup"><span data-stu-id="af997-104">To view a specific trace</span></span>  
  
1.  <span data-ttu-id="af997-105">Выполните функцию **fn_trace_getinfo** , указав идентификатор трассировки, сведения о котором необходимо получить.</span><span class="sxs-lookup"><span data-stu-id="af997-105">Execute **fn_trace_getinfo** by specifying the ID of the trace about which information is needed.</span></span> <span data-ttu-id="af997-106">Данная функция возвращает таблицу, в которой перечислены трассировка, свойство трассировки и сведения об этом свойстве.</span><span class="sxs-lookup"><span data-stu-id="af997-106">This function returns a table that lists the trace, trace property, and information about the property.</span></span>  
  
     <span data-ttu-id="af997-107">Запустите функцию следующим способом:</span><span class="sxs-lookup"><span data-stu-id="af997-107">Invoke the function this way:</span></span>  
  
    ```  
    SELECT *  
    FROM ::fn_trace_getinfo(trace_id)  
    ```  
  
### <a name="to-view-all-existing-traces"></a><span data-ttu-id="af997-108">Просмотр всех существующих трассировок</span><span class="sxs-lookup"><span data-stu-id="af997-108">To view all existing traces</span></span>  
  
1.  <span data-ttu-id="af997-109">Выполните функцию **fn_trace_getinfo** , указав значения `0` или `default`.</span><span class="sxs-lookup"><span data-stu-id="af997-109">Execute **fn_trace_getinfo** by specifying `0` or `default`.</span></span> <span data-ttu-id="af997-110">Данная функция возвращает таблицу, в которой перечислены все трассировки, свойства трассировок и сведения об этих свойствах.</span><span class="sxs-lookup"><span data-stu-id="af997-110">This function returns a table that lists all the traces, their properties, and information about these properties.</span></span>  
  
     <span data-ttu-id="af997-111">Функция вызывается следующим образом:</span><span class="sxs-lookup"><span data-stu-id="af997-111">Invoke the function as follows:</span></span>  
  
    ```  
    SELECT *  
    FROM ::fn_trace_getinfo(default)  
    ```  
  
## <a name="net-framework-security"></a><span data-ttu-id="af997-112">Безопасность .NET Framework</span><span class="sxs-lookup"><span data-stu-id="af997-112">.NET Framework Security</span></span>  
 <span data-ttu-id="af997-113">Для выполнения встроенной функции **fn_trace_getinfo**пользователю требуются следующие разрешения:</span><span class="sxs-lookup"><span data-stu-id="af997-113">To run the built-in function **fn_trace_getinfo**, the user needs the following permission:</span></span>  
  
 <span data-ttu-id="af997-114">ALTER TRACE на сервере.</span><span class="sxs-lookup"><span data-stu-id="af997-114">ALTER TRACE on the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af997-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="af997-115">See Also</span></span>  
 <span data-ttu-id="af997-116">[sys.fn_trace_getinfo (Transact-SQL)](/sql/relational-databases/system-functions/sys-fn-trace-getinfo-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="af997-116">[sys.fn_trace_getinfo &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-trace-getinfo-transact-sql) </span></span>  
 [<span data-ttu-id="af997-117">Просмотр и анализ трассировок с помощью приложения SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="af997-117">View and Analyze Traces with SQL Server Profiler</span></span>](../../tools/sql-server-profiler/view-and-analyze-traces-with-sql-server-profiler.md)  
  
  
