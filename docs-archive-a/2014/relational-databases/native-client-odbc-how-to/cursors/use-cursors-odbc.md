---
title: Использование курсоров (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- cursors [ODBC], how to topics
ms.assetid: c502736f-bca0-45c3-ae25-d2ad52d296bf
author: rothja
ms.author: jroth
ms.openlocfilehash: e08156b03407c7a05d86278c11482a568d651f5f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654241"
---
# <a name="use-cursors-odbc"></a><span data-ttu-id="85b75-102">Использование курсоров (ODBC)</span><span class="sxs-lookup"><span data-stu-id="85b75-102">Use Cursors (ODBC)</span></span>
    
### <a name="to-use-cursors"></a><span data-ttu-id="85b75-103">Использование курсоров</span><span class="sxs-lookup"><span data-stu-id="85b75-103">To use cursors</span></span>  
  
1.  <span data-ttu-id="85b75-104">Вызовите функцию [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md), чтобы задать нужные атрибуты курсора:</span><span class="sxs-lookup"><span data-stu-id="85b75-104">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the desired cursor attributes:</span></span>  
  
     <span data-ttu-id="85b75-105">Задайте атрибуты SQL_ATTR_CURSOR_TYPE и SQL_ATTR_CONCURRENCY (этот параметр предпочтителен).</span><span class="sxs-lookup"><span data-stu-id="85b75-105">Set the SQL_ATTR_CURSOR_TYPE and SQL_ATTR_CONCURRENCY attributes (this is the preferred option).</span></span>  
  
     <span data-ttu-id="85b75-106">Или</span><span class="sxs-lookup"><span data-stu-id="85b75-106">Or</span></span>  
  
     <span data-ttu-id="85b75-107">Задайте атрибуты SQL_CURSOR_SCROLLABLE и SQL_CURSOR_SENSITIVITY.</span><span class="sxs-lookup"><span data-stu-id="85b75-107">Set the SQL_CURSOR_SCROLLABLE and SQL_CURSOR_SENSITIVITY attributes.</span></span>  
  
2.  <span data-ttu-id="85b75-108">Вызовите метод [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) для установки размера набора строк с помощью атрибута SQL_ATTR_ROW_ARRAY_SIZE.</span><span class="sxs-lookup"><span data-stu-id="85b75-108">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the rowset size by using the SQL_ATTR_ROW_ARRAY_SIZE attribute.</span></span>  
  
3.  <span data-ttu-id="85b75-109">По желанию можно вызвать функцию [SQLSetCursorName](https://go.microsoft.com/fwlink/?LinkId=58406) для задания имени курсора, если позиционированные обновления предполагается проводить с помощью предложения WHERE CURRENT OF.</span><span class="sxs-lookup"><span data-stu-id="85b75-109">Optionally, call [SQLSetCursorName](https://go.microsoft.com/fwlink/?LinkId=58406) to set a cursor name if positioned updates will be done by using the WHERE CURRENT OF clause.</span></span>  
  
4.  <span data-ttu-id="85b75-110">Выполните инструкцию SQL.</span><span class="sxs-lookup"><span data-stu-id="85b75-110">Execute the SQL statement.</span></span>  
  
5.  <span data-ttu-id="85b75-111">По желанию можно вызвать функцию [SQLGetCursorName](../../native-client-odbc-api/sqlgetcursorname.md) для получения имени курсора, если позиционированные обновления предполагается проводить с помощью предложения WHERE CURRENT OF, а имя курсора не было задано с помощью функции [SQLSetCursorName](https://go.microsoft.com/fwlink/?LinkId=58406) на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="85b75-111">Optionally, call [SQLGetCursorName](../../native-client-odbc-api/sqlgetcursorname.md) to get the cursor name if positioned updates will be done by using the WHERE CURRENT OF clause and a cursor name was not supplied with [SQLSetCursorName](https://go.microsoft.com/fwlink/?LinkId=58406) in Step 3.</span></span>  
  
6.  <span data-ttu-id="85b75-112">Вызовите функцию [SQLNumResultCols](../../native-client-odbc-api/sqlnumresultcols.md) для получения числа столбцов (C) в наборе строк.</span><span class="sxs-lookup"><span data-stu-id="85b75-112">Call [SQLNumResultCols](../../native-client-odbc-api/sqlnumresultcols.md) to get the number of columns (C) in the rowset.</span></span>  
  
     <span data-ttu-id="85b75-113">Используйте привязку по столбцам.</span><span class="sxs-lookup"><span data-stu-id="85b75-113">Use column-wise binding.</span></span>  
  
     <span data-ttu-id="85b75-114">\- или -</span><span class="sxs-lookup"><span data-stu-id="85b75-114">\- or -</span></span>  
  
     <span data-ttu-id="85b75-115">Используйте привязку на уровне строки.</span><span class="sxs-lookup"><span data-stu-id="85b75-115">Use row-wise binding.</span></span>  
  
7.  <span data-ttu-id="85b75-116">Получайте наборы строк из курсора по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="85b75-116">Fetch rowsets from the cursor as desired.</span></span>  
  
8.  <span data-ttu-id="85b75-117">Вызовите функцию [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md), чтобы определить, доступен ли другой результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="85b75-117">Call [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) to determine if another result set is available.</span></span>  
  
    -   <span data-ttu-id="85b75-118">Если вернулось значение SQL_SUCCESS, то доступен другой результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="85b75-118">If it returns SQL_SUCCESS, another result set is available.</span></span>  
  
    -   <span data-ttu-id="85b75-119">Если вернулось значение SQL_NO_DATA, то больше нет результирующих наборов.</span><span class="sxs-lookup"><span data-stu-id="85b75-119">If it returns SQL_NO_DATA, no more result sets are available.</span></span>  
  
    -   <span data-ttu-id="85b75-120">Если вернулось значение SQL_SUCCESS_WITH_INFO или SQL_ERROR, вызовом функции [SQLGetDiagRec](https://go.microsoft.com/fwlink/?LinkId=58402) определите, есть ли выходные данные от инструкции PRINT или RAISERROR.</span><span class="sxs-lookup"><span data-stu-id="85b75-120">If it returns SQL_SUCCESS_WITH_INFO or SQL_ERROR, call [SQLGetDiagRec](https://go.microsoft.com/fwlink/?LinkId=58402) to determine if the output from a PRINT or RAISERROR statement is available.</span></span>  
  
     <span data-ttu-id="85b75-121">Если в качестве выходных параметров используются привязанные параметры инструкции или возвращаемое значение хранимой процедуры, используйте данные, имеющиеся в буферах привязанного параметра.</span><span class="sxs-lookup"><span data-stu-id="85b75-121">If bound statement parameters are used for output parameters or the return value of a stored procedure, use the data now available in the bound parameter buffers.</span></span>  
  
     <span data-ttu-id="85b75-122">При использовании привязки параметров каждый вызов метода [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) или [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) выполнит инструкцию SQL S раз, где S — число элементов в массиве привязанных параметров.</span><span class="sxs-lookup"><span data-stu-id="85b75-122">When bound parameters are used, each call to [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) or [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) will have executed the SQL statement S times, where S is the number of elements in the array of bound parameters.</span></span> <span data-ttu-id="85b75-123">Это значит, что придется обработать S наборов результатов, каждый из которых содержит все результирующие наборы, выходные параметры и коды возврата, обычно возвращаемые при исполнении отдельной инструкции SQL.</span><span class="sxs-lookup"><span data-stu-id="85b75-123">This means that there will be S sets of results to process, where each set of results comprises all of the result sets, output parameters, and return codes usually returned by a single execution of the SQL statement.</span></span>  
  
     <span data-ttu-id="85b75-124">Следует заметить, что, когда результирующий набор содержит вычисляемые строки, каждая вычисляемая строка представляется как отдельный результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="85b75-124">Note that when a result set contains compute rows, each compute row is made available as a separate result set.</span></span> <span data-ttu-id="85b75-125">Эти вычисляемые результирующие наборы находятся среди обычных строк, разбивая их на несколько результирующих наборов.</span><span class="sxs-lookup"><span data-stu-id="85b75-125">These compute result sets are interspersed within the normal rows and break normal rows into multiple result sets.</span></span>  
  
9. <span data-ttu-id="85b75-126">Можно также вызвать функцию [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) с SQL_UNBIND, чтобы освободить все буферы связанных столбцов.</span><span class="sxs-lookup"><span data-stu-id="85b75-126">Optionally, call [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) with SQL_UNBIND to release any bound column buffers.</span></span>  
  
10. <span data-ttu-id="85b75-127">Если есть еще один результирующий набор, перейдите к шагу 6.</span><span class="sxs-lookup"><span data-stu-id="85b75-127">If another result set is available, go to Step 6.</span></span>  
  
     <span data-ttu-id="85b75-128">На шаге 9 вызов функции [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) на частично обработанном результирующем наборе очистит оставшиеся результаты из набора.</span><span class="sxs-lookup"><span data-stu-id="85b75-128">In Step 9, calling [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) on a partially processed result set clears the remainder of the result set.</span></span> <span data-ttu-id="85b75-129">Другой способ очистки частично обработанного результирующего набора — вызов функции [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md).</span><span class="sxs-lookup"><span data-stu-id="85b75-129">Another way to clear a partially processed result set is to call [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md).</span></span>  
  
     <span data-ttu-id="85b75-130">Типом курсора можно управлять, задавая параметры SQL_ATTR_CURSOR_TYPE и SQL_ATTR_CONCURRENCY либо SQL_ATTR_CURSOR_SENSITIVITY и SQL_ATTR_CURSOR_SCROLLABLE.</span><span class="sxs-lookup"><span data-stu-id="85b75-130">You can control the type of cursor used by setting either SQL_ATTR_CURSOR_TYPE and SQL_ATTR_CONCURRENCY, or by setting SQL_ATTR_CURSOR_SENSITIVITY and SQL_ATTR_CURSOR_SCROLLABLE.</span></span> <span data-ttu-id="85b75-131">Не следует смешивать два метода задания режима работы курсоров.</span><span class="sxs-lookup"><span data-stu-id="85b75-131">You should not mix the two methods of specifying cursor behavior.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85b75-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="85b75-132">See Also</span></span>  
 [<span data-ttu-id="85b75-133">Инструкции по использованию курсоров &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="85b75-133">Using Cursors How-to Topics &#40;ODBC&#41;</span></span>](using-cursors-how-to-topics-odbc.md)  
  
  
