---
title: Обработка результатов (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- processing results [ODBC]
ms.assetid: 4810fe3f-78ee-4f0d-8bcc-a4659fbcf46f
author: rothja
ms.author: jroth
ms.openlocfilehash: 8a22e9d7280f88de7799c31d2d0611e5299043d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738294"
---
# <a name="process-results-odbc"></a><span data-ttu-id="77ec8-102">Обработка результатов (ODBC)</span><span class="sxs-lookup"><span data-stu-id="77ec8-102">Process Results (ODBC)</span></span>
    
### <a name="to-process-results"></a><span data-ttu-id="77ec8-103">Обработка результатов</span><span class="sxs-lookup"><span data-stu-id="77ec8-103">To process results</span></span>  
  
1.  <span data-ttu-id="77ec8-104">Получите сведения о результирующем наборе.</span><span class="sxs-lookup"><span data-stu-id="77ec8-104">Retrieve result set information.</span></span>  
  
2.  <span data-ttu-id="77ec8-105">Если используются привязанные столбцы, вызовите функцию [SQLBindCol](../native-client-odbc-api/sqlbindcol.md) для каждого столбца, чтобы привязать буфер программы к столбцу.</span><span class="sxs-lookup"><span data-stu-id="77ec8-105">If bound columns are used, for each column you want to bind to, call [SQLBindCol](../native-client-odbc-api/sqlbindcol.md) to bind a program buffer to the column.</span></span>  
  
3.  <span data-ttu-id="77ec8-106">Для каждой строки в результирующем наборе сделайте следующее.</span><span class="sxs-lookup"><span data-stu-id="77ec8-106">For each row in the result set:</span></span>  
  
    -   <span data-ttu-id="77ec8-107">Вызовите функцию [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401), чтобы получить следующую строку.</span><span class="sxs-lookup"><span data-stu-id="77ec8-107">Call [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) to get the next row.</span></span>  
  
    -   <span data-ttu-id="77ec8-108">Если используются привязанные столбцы, используйте данные, теперь доступные в привязанных буферах столбцов.</span><span class="sxs-lookup"><span data-stu-id="77ec8-108">If bound columns are used, use the data now available in the bound column buffers.</span></span>  
  
    -   <span data-ttu-id="77ec8-109">Если используются непривязанные столбцы, вызовите функцию [SQLGetData](../native-client-odbc-api/sqlgetdata.md) один или несколько раз, чтобы получить данные для непривязанных столбцов после последнего привязанного столбца.</span><span class="sxs-lookup"><span data-stu-id="77ec8-109">If unbound columns are used, call [SQLGetData](../native-client-odbc-api/sqlgetdata.md) one or more times to get the data for unbound columns after the last bound column.</span></span> <span data-ttu-id="77ec8-110">Вызовы функции `SQLGetData` должны следовать по возрастанию номера столбца.</span><span class="sxs-lookup"><span data-stu-id="77ec8-110">Calls to `SQLGetData` should be in increasing order of column number.</span></span>  
  
    -   <span data-ttu-id="77ec8-111">Получение данных из столбца типа text или image производится многократным вызовом функции `SQLGetData`.</span><span class="sxs-lookup"><span data-stu-id="77ec8-111">Call `SQLGetData` multiple times to get data from a text or image column.</span></span>  
  
4.  <span data-ttu-id="77ec8-112">Когда функция [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) указывает конец результирующего набора, возвращая SQL_NO_DATA, вызовите функцию [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md), чтобы определить, доступен ли другой результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="77ec8-112">When [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) signals the end of the result set by returning SQL_NO_DATA, call [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) to determine if another result set is available.</span></span>  
  
    -   <span data-ttu-id="77ec8-113">Если вернулось значение SQL_SUCCESS, то доступен другой результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="77ec8-113">If it returns SQL_SUCCESS, another result set is available.</span></span>  
  
    -   <span data-ttu-id="77ec8-114">Если вернулось значение SQL_NO_DATA, то больше нет результирующих наборов.</span><span class="sxs-lookup"><span data-stu-id="77ec8-114">If it returns SQL_NO_DATA, no more result sets are available.</span></span>  
  
    -   <span data-ttu-id="77ec8-115">Если вернулось значение SQL_SUCCESS_WITH_INFO или SQL_ERROR, вызовом функции [SQLGetDiagRec](https://go.microsoft.com/fwlink/?LinkId=58402) определите, есть ли выходные данные от инструкции PRINT или RAISERROR.</span><span class="sxs-lookup"><span data-stu-id="77ec8-115">If it returns SQL_SUCCESS_WITH_INFO or SQL_ERROR, call [SQLGetDiagRec](https://go.microsoft.com/fwlink/?LinkId=58402) to determine if the output from a PRINT or RAISERROR statement is available.</span></span>  
  
         <span data-ttu-id="77ec8-116">Если в качестве выходных параметров используются привязанные параметры инструкции или возвращаемое значение хранимой процедуры, используйте данные, имеющиеся в буферах привязанного параметра.</span><span class="sxs-lookup"><span data-stu-id="77ec8-116">If bound statement parameters are used for output parameters or the return value of a stored procedure, use the data now available in the bound parameter buffers.</span></span> <span data-ttu-id="77ec8-117">Кроме того, если используются привязанные параметры, при каждом вызове функции [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) или [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) инструкция SQL будет выполняться *S* раз, где *S* — количество элементов в массиве привязанных параметров.</span><span class="sxs-lookup"><span data-stu-id="77ec8-117">Also, when bound parameters are used, each call to [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) or [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) will have executed the SQL statement *S* times, where *S* is the number of elements in the array of bound parameters.</span></span> <span data-ttu-id="77ec8-118">Это значит, что придется обработать *S* наборов результатов, каждый из которых содержит все результирующие наборы, выходные параметры и коды возврата, обычно возвращаемые при исполнении отдельной инструкции SQL.</span><span class="sxs-lookup"><span data-stu-id="77ec8-118">This means that there will be *S* sets of results to process, where each set of results comprises all of the result sets, output parameters, and return codes usually returned by a single execution of the SQL statement.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="77ec8-119">Если результирующий набор содержит вычисляемые строки, каждая вычисляемая строка доступна как отдельный результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="77ec8-119">When a result set contains compute rows, each compute row is made available as a separate result set.</span></span> <span data-ttu-id="77ec8-120">Эти вычисляемые результирующие наборы находятся среди обычных строк, разбивая их на несколько результирующих наборов.</span><span class="sxs-lookup"><span data-stu-id="77ec8-120">These compute result sets are interspersed within the normal rows and break normal rows into multiple result sets.</span></span>  
  
5.  <span data-ttu-id="77ec8-121">Можно также вызвать функцию [SQLFreeStmt](../native-client-odbc-api/sqlfreestmt.md) с SQL_UNBIND, чтобы освободить все буферы связанных столбцов.</span><span class="sxs-lookup"><span data-stu-id="77ec8-121">Optionally, call [SQLFreeStmt](../native-client-odbc-api/sqlfreestmt.md) with SQL_UNBIND to release any bound column buffers.</span></span>  
  
6.  <span data-ttu-id="77ec8-122">Если есть еще один результирующий набор, перейдите к шагу 1.</span><span class="sxs-lookup"><span data-stu-id="77ec8-122">If another result set is available, go to Step 1.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="77ec8-123">Чтобы отменить обработку результирующего набора прежде, чем функция [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) вернет значение SQL_NO_DATA, вызовите функцию [SQLCloseCursor](../native-client-odbc-api/sqlclosecursor.md).</span><span class="sxs-lookup"><span data-stu-id="77ec8-123">To cancel processing a result set before [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) returns SQL_NO_DATA, call [SQLCloseCursor](../native-client-odbc-api/sqlclosecursor.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77ec8-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="77ec8-124">See Also</span></span>  
 [<span data-ttu-id="77ec8-125">Разделы руководства по обработке результатов &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="77ec8-125">Processing Results How-to Topics &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/processing-results-how-to-topics-odbc.md)  
  
  
