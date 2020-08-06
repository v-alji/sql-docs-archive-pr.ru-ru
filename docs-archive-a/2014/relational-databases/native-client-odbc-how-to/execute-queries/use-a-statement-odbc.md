---
title: Использование оператора (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- statements [ODBC]
ms.assetid: f7573f8f-6f21-4e03-8dd5-a5f2ea4878cc
author: rothja
ms.author: jroth
ms.openlocfilehash: 8ff3bc8c545cc9b55f0da3bb31d68d1ecbb5b547
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739875"
---
# <a name="use-a-statement-odbc"></a><span data-ttu-id="1c43d-102">Использование инструкции (ODBC)</span><span class="sxs-lookup"><span data-stu-id="1c43d-102">Use a Statement (ODBC)</span></span>
    
### <a name="to-use-a-statement"></a><span data-ttu-id="1c43d-103">Использование инструкции</span><span class="sxs-lookup"><span data-stu-id="1c43d-103">To use a statement</span></span>  
  
1.  <span data-ttu-id="1c43d-104">Для выделения дескриптора инструкции вызовите функцию [SQLAllocHandle](https://go.microsoft.com/fwlink/?LinkId=58396) с параметром *HandleType*, имеющим значение SQL_HANDLE_STMT.</span><span class="sxs-lookup"><span data-stu-id="1c43d-104">Call [SQLAllocHandle](https://go.microsoft.com/fwlink/?LinkId=58396) with a *HandleType* of SQL_HANDLE_STMT to allocate a statement handle.</span></span>  
  
2.  <span data-ttu-id="1c43d-105">Также можно вызвать [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) для настройки параметров инструкции или [SQLGetStmtAttr](../../native-client-odbc-api/sqlgetstmtattr.md) для получения атрибутов инструкции.</span><span class="sxs-lookup"><span data-stu-id="1c43d-105">Optionally, call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set statement options or [SQLGetStmtAttr](../../native-client-odbc-api/sqlgetstmtattr.md) to get statement attributes.</span></span>  
  
     <span data-ttu-id="1c43d-106">Чтобы использовать серверные курсоры, необходимо установить атрибуты курсоров в значения, отличные от значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1c43d-106">To use server cursors, you must set cursor attributes to values other than their defaults.</span></span>  
  
3.  <span data-ttu-id="1c43d-107">Если инструкция будет выполняться несколько раз, то ее можно подготовить к выполнению с помощью функции [SQLPrepare](https://go.microsoft.com/fwlink/?LinkId=59360).</span><span class="sxs-lookup"><span data-stu-id="1c43d-107">Optionally, if the statement will be executed several times, prepare the statement for execution with [SQLPrepare Function](https://go.microsoft.com/fwlink/?LinkId=59360).</span></span>  
  
4.  <span data-ttu-id="1c43d-108">Если инструкция имеет связанные маркеры параметров, можно привязать их к переменным программы с помощью функции [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md).</span><span class="sxs-lookup"><span data-stu-id="1c43d-108">Optionally, if the statement has bound parameter markers, bind the parameter markers to program variables by using [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md).</span></span> <span data-ttu-id="1c43d-109">Для подготовленной инструкции можно вызвать функции [SQLNumParams](https://go.microsoft.com/fwlink/?LinkId=58404) и [SQLDescribeParam](../../native-client-odbc-api/sqldescribeparam.md) to find the number и characteristics of the parameters.</span><span class="sxs-lookup"><span data-stu-id="1c43d-109">If the statement was prepared, you can call [SQLNumParams](https://go.microsoft.com/fwlink/?LinkId=58404) and [SQLDescribeParam](../../native-client-odbc-api/sqldescribeparam.md) to find the number and characteristics of the parameters.</span></span>  
  
5.  <span data-ttu-id="1c43d-110">Произведите прямое выполнение инструкции с помощью функции SQLExecDirect.</span><span class="sxs-lookup"><span data-stu-id="1c43d-110">Execute a statement directly by using SQLExecDirect.</span></span>  
  
     <span data-ttu-id="1c43d-111">\- или -</span><span class="sxs-lookup"><span data-stu-id="1c43d-111">\- or -</span></span>  
  
     <span data-ttu-id="1c43d-112">Если инструкция была подготовлена, выполните ее несколько раз с помощью функции [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400).</span><span class="sxs-lookup"><span data-stu-id="1c43d-112">If the statement was prepared, execute it multiple times by using [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400).</span></span>  
  
     <span data-ttu-id="1c43d-113">\- или -</span><span class="sxs-lookup"><span data-stu-id="1c43d-113">\- or -</span></span>  
  
     <span data-ttu-id="1c43d-114">Вызовите функцию каталога, возвращающую результаты.</span><span class="sxs-lookup"><span data-stu-id="1c43d-114">Call a catalog function, which returns results.</span></span>  
  
6.  <span data-ttu-id="1c43d-115">Обработайте результаты, связав столбцы результирующего набора с переменными программы, переместив данные из столбцов результирующего набора в переменные программы с помощью функции [SQLGetData](../../native-client-odbc-api/sqlgetdata.md)или используя сочетание этих двух методов.</span><span class="sxs-lookup"><span data-stu-id="1c43d-115">Process the results by binding the result set columns to program variables, by moving data from the result set columns to program variables by using [SQLGetData](../../native-client-odbc-api/sqlgetdata.md), or a combination of the two methods.</span></span>  
  
     <span data-ttu-id="1c43d-116">Произведите выборку из результирующего набора инструкции одной строки.</span><span class="sxs-lookup"><span data-stu-id="1c43d-116">Fetch through the result set of a statement one row at a time.</span></span>  
  
     <span data-ttu-id="1c43d-117">\- или -</span><span class="sxs-lookup"><span data-stu-id="1c43d-117">\- or -</span></span>  
  
     <span data-ttu-id="1c43d-118">Произведите выборку из результирующего набора нескольких строк с помощью блочного курсора.</span><span class="sxs-lookup"><span data-stu-id="1c43d-118">Fetch through the result set several rows at a time by using a block cursor.</span></span>  
  
     <span data-ttu-id="1c43d-119">\- или -</span><span class="sxs-lookup"><span data-stu-id="1c43d-119">\- or -</span></span>  
  
     <span data-ttu-id="1c43d-120">Вызовите функцию [SQLRowCount](../../native-client-odbc-api/sqlrowcount.md) , чтобы определить число строк, затронутых инструкцией INSERT, UPDATE или DELETE.</span><span class="sxs-lookup"><span data-stu-id="1c43d-120">Call [SQLRowCount](../../native-client-odbc-api/sqlrowcount.md) to determine the number of rows affected by an INSERT, UPDATE, or DELETE statement.</span></span>  
  
     <span data-ttu-id="1c43d-121">Если инструкция SQL имеет несколько результирующих наборов, то после получения каждого результирующего набора вызовите функцию [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) , чтобы просмотреть, есть ли дополнительные результирующие наборы для обработки.</span><span class="sxs-lookup"><span data-stu-id="1c43d-121">If the SQL statement can have multiple result sets, call [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) at the end of each result set to see if there are additional result sets to process.</span></span>  
  
7.  <span data-ttu-id="1c43d-122">После обработки результатов, чтобы сделать для дескриптора инструкции доступной возможность выполнения новой инструкции, могут потребоваться следующие действия.</span><span class="sxs-lookup"><span data-stu-id="1c43d-122">After results are processed, the following actions may be necessary to make the statement handle available to execute a new statement:</span></span>  
  
    -   <span data-ttu-id="1c43d-123">Если функция [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) не вызывалась до возвращения значения SQL_NO_DATA, вызовите функцию [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) для закрытия курсора.</span><span class="sxs-lookup"><span data-stu-id="1c43d-123">If you did not call [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) until it returned SQL_NO_DATA, call [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) to close the cursor.</span></span>  
  
    -   <span data-ttu-id="1c43d-124">Если маркеры параметров привязаны к переменным программы, то для их освобождения вызовите функцию [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) с параметром *Option* , установленным в значение SQL_RESET_PARAMS.</span><span class="sxs-lookup"><span data-stu-id="1c43d-124">If you bound parameter markers to program variables, call [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) with *Option* set to SQL_RESET_PARAMS to free the bound parameters.</span></span>  
  
    -   <span data-ttu-id="1c43d-125">Если столбцы результирующего набора привязаны к переменным программы, для их освобождения вызовите функцию [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) с параметром *Option* , установленным в значение SQL_UNBIND.</span><span class="sxs-lookup"><span data-stu-id="1c43d-125">If you bound result set columns to program variables, call [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) with *Option* set to SQL_UNBIND to free the bound columns.</span></span>  
  
    -   <span data-ttu-id="1c43d-126">Для повторного использования дескриптора инструкции перейдите к шагу 2.</span><span class="sxs-lookup"><span data-stu-id="1c43d-126">To reuse the statement handle, go to Step 2.</span></span>  
  
8.  <span data-ttu-id="1c43d-127">Для освобождения дескриптора инструкции вызовите функцию [SQLFreeHandle](../../native-client-odbc-api/sqlfreehandle.md) с параметром *HandleType*, установленным в значение SQL_HANDLE_STMT.</span><span class="sxs-lookup"><span data-stu-id="1c43d-127">Call [SQLFreeHandle](../../native-client-odbc-api/sqlfreehandle.md) with a *HandleType* of SQL_HANDLE_STMT to free the statement handle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c43d-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="1c43d-128">See Also</span></span>  
 [<span data-ttu-id="1c43d-129">Инструкции по выполнению запросов &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="1c43d-129">Executing Queries How-to Topics &#40;ODBC&#41;</span></span>](executing-queries-how-to-topics-odbc.md)  
  
  
