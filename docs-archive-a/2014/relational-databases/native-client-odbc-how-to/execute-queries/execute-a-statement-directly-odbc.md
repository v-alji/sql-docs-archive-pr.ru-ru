---
title: Непосредственное выполнение инструкции (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- statement execution
ms.assetid: b690f9de-66e1-4ee5-ab6a-121346fb5f85
author: rothja
ms.author: jroth
ms.openlocfilehash: 2aeada906a925cff93455ffd92e7c17822a80124
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654234"
---
# <a name="execute-a-statement-directly-odbc"></a><span data-ttu-id="0cf66-102">Непосредственное выполнение инструкции (ODBC)</span><span class="sxs-lookup"><span data-stu-id="0cf66-102">Execute a Statement Directly (ODBC)</span></span>
    
### <a name="to-execute-a-statement-directly-and-one-time-only"></a><span data-ttu-id="0cf66-103">Однократное непосредственное выполнение инструкции</span><span class="sxs-lookup"><span data-stu-id="0cf66-103">To execute a statement directly and one time only</span></span>  
  
1.  <span data-ttu-id="0cf66-104">Если инструкция содержит маркеры параметров, воспользуйтесь [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md) для привязки каждого параметра к программной переменной.</span><span class="sxs-lookup"><span data-stu-id="0cf66-104">If the statement has parameter markers, use [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md) to bind each parameter to a program variable.</span></span> <span data-ttu-id="0cf66-105">Необходимо заполнить программные переменные значениями данных, а затем установить все параметры с данными времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="0cf66-105">Fill the program variables with data values, and then set up any data-at-execution parameters.</span></span>  
  
2.  <span data-ttu-id="0cf66-106">Чтобы выполнить инструкцию, вызовите метод [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) .</span><span class="sxs-lookup"><span data-stu-id="0cf66-106">Call [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) to execute the statement.</span></span>  
  
3.  <span data-ttu-id="0cf66-107">При использовании входных параметров с данными времени выполнения вызов [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) возвращает SQL_NEED_DATA.</span><span class="sxs-lookup"><span data-stu-id="0cf66-107">If data-at-execution input parameters are used, [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) returns SQL_NEED_DATA.</span></span> <span data-ttu-id="0cf66-108">Отправьте данные по фрагментам при помощи функций [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) и [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span><span class="sxs-lookup"><span data-stu-id="0cf66-108">Send the data in chunks by using [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) and [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span></span>  
  
### <a name="to-execute-a-statement-multiple-times-by-using-column-wise-parameter-binding"></a><span data-ttu-id="0cf66-109">Выполнение инструкции несколько раз при помощи привязки параметра на уровне столбца</span><span class="sxs-lookup"><span data-stu-id="0cf66-109">To execute a statement multiple times by using column-wise parameter binding</span></span>  
  
1.  <span data-ttu-id="0cf66-110">Вызовите функцию [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) , чтобы задать следующие атрибуты.</span><span class="sxs-lookup"><span data-stu-id="0cf66-110">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the following attributes:</span></span>  
  
     <span data-ttu-id="0cf66-111">Атрибуту SQL_ATTR_PARAMSET_SIZE задайте число наборов параметров (S).</span><span class="sxs-lookup"><span data-stu-id="0cf66-111">Set SQL_ATTR_PARAMSET_SIZE to the number of sets (S) of parameters.</span></span>  
  
     <span data-ttu-id="0cf66-112">Атрибуту SQL_ATTR_PARAM_BIND_TYPE задайте значение SQL_PARAMETER_BIND_BY_COLUMN.</span><span class="sxs-lookup"><span data-stu-id="0cf66-112">Set SQL_ATTR_PARAM_BIND_TYPE to SQL_PARAMETER_BIND_BY_COLUMN.</span></span>  
  
     <span data-ttu-id="0cf66-113">Атрибут SQL_ATTR_PARAMS_PROCESSED_PTR должен указывать на переменную SQLUINTEGER, в которую помещается число обработанных параметров.</span><span class="sxs-lookup"><span data-stu-id="0cf66-113">Set the SQL_ATTR_PARAMS_PROCESSED_PTR attribute to point to a SQLUINTEGER variable to hold the number of parameters processed.</span></span>  
  
     <span data-ttu-id="0cf66-114">Атрибут SQL_ATTR_PARAMS_STATUS_PTR должен указывать на массив [S] переменных SQLUSSMALLINT, в которые помещаются признаки состояния параметров.</span><span class="sxs-lookup"><span data-stu-id="0cf66-114">Set SQL_ATTR_PARAMS_STATUS_PTR to point to an array[S] of SQLUSSMALLINT variables to hold the parameter status indicators.</span></span>  
  
2.  <span data-ttu-id="0cf66-115">Для каждого маркера параметра выполните следующее.</span><span class="sxs-lookup"><span data-stu-id="0cf66-115">For each parameter marker:</span></span>  
  
     <span data-ttu-id="0cf66-116">Выделите массив из S буферов параметра для сохранения значений данных.</span><span class="sxs-lookup"><span data-stu-id="0cf66-116">Allocate an array of S parameter buffers to store data values.</span></span>  
  
     <span data-ttu-id="0cf66-117">Выделите массив из S буферов параметра для сохранения длин данных.</span><span class="sxs-lookup"><span data-stu-id="0cf66-117">Allocate an array of S parameter buffers to store data lengths.</span></span>  
  
     <span data-ttu-id="0cf66-118">Вызовите функцию [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md) , чтобы связать массивы значений данных и длин данных с параметром инструкции.</span><span class="sxs-lookup"><span data-stu-id="0cf66-118">Call [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md) to bind the parameter data value and data length arrays to the statement parameter.</span></span>  
  
     <span data-ttu-id="0cf66-119">Настройте текстовые столбцы или столбцы изображений, получающие данные во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="0cf66-119">Set up any data-at-execution text or image parameters.</span></span>  
  
     <span data-ttu-id="0cf66-120">Поместите S значений данных и S длин данных в привязанные массивы параметров.</span><span class="sxs-lookup"><span data-stu-id="0cf66-120">Put S data values and S data lengths into the bound parameter arrays.</span></span>  
  
3.  <span data-ttu-id="0cf66-121">Чтобы выполнить инструкцию, вызовите метод [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) .</span><span class="sxs-lookup"><span data-stu-id="0cf66-121">Call [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) to execute the statement.</span></span> <span data-ttu-id="0cf66-122">Драйвер эффективно выполнит инструкцию S раз, по одному разу для каждого набора параметров.</span><span class="sxs-lookup"><span data-stu-id="0cf66-122">The driver efficiently executes the statement S times, once for each set of parameters.</span></span>  
  
4.  <span data-ttu-id="0cf66-123">При использовании входных параметров с данными времени выполнения вызов [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) возвращает SQL_NEED_DATA.</span><span class="sxs-lookup"><span data-stu-id="0cf66-123">If data-at-execution input parameters are used, [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) returns SQL_NEED_DATA.</span></span> <span data-ttu-id="0cf66-124">Отправьте данные по фрагментам при помощи функций [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) и [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span><span class="sxs-lookup"><span data-stu-id="0cf66-124">Send the data in chunks by using [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) and [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span></span>  
  
### <a name="to-execute-a-statement-multiple-times-by-using-row-wise-parameter-binding"></a><span data-ttu-id="0cf66-125">Выполнение инструкции несколько раз при помощи привязки параметра на уровне строки</span><span class="sxs-lookup"><span data-stu-id="0cf66-125">To execute a statement multiple times by using row-wise parameter binding</span></span>  
  
1.  <span data-ttu-id="0cf66-126">Выделите массив структур [S], где S — число наборов параметров.</span><span class="sxs-lookup"><span data-stu-id="0cf66-126">Allocate an array[S] of structures, where S is the number of sets of parameters.</span></span> <span data-ttu-id="0cf66-127">Структура имеет по одному элементу для каждого параметра, а каждый элемент состоит из двух частей.</span><span class="sxs-lookup"><span data-stu-id="0cf66-127">The structure has one element for each parameter, and each element has two parts:</span></span>  
  
     <span data-ttu-id="0cf66-128">Первая часть — переменная соответствующего типа данных, в которую помещаются данные параметра.</span><span class="sxs-lookup"><span data-stu-id="0cf66-128">The first part is a variable of the appropriate data type to hold the parameter data.</span></span>  
  
     <span data-ttu-id="0cf66-129">Вторая часть — переменная SQLINTEGER, в которую помещается признак состояния.</span><span class="sxs-lookup"><span data-stu-id="0cf66-129">The second part is a SQLINTEGER variable to hold the status indicator.</span></span>  
  
2.  <span data-ttu-id="0cf66-130">Вызовите функцию [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) , чтобы задать следующие атрибуты.</span><span class="sxs-lookup"><span data-stu-id="0cf66-130">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the following attributes:</span></span>  
  
     <span data-ttu-id="0cf66-131">Атрибуту SQL_ATTR_PARAMSET_SIZE задайте число наборов параметров (S).</span><span class="sxs-lookup"><span data-stu-id="0cf66-131">Set SQL_ATTR_PARAMSET_SIZE to the number of sets (S) of parameters.</span></span>  
  
     <span data-ttu-id="0cf66-132">Атрибуту SQL_ATTR_PARAM_BIND_TYPE задайте размер структуры, выделенной в шаге 1.</span><span class="sxs-lookup"><span data-stu-id="0cf66-132">Set SQL_ATTR_PARAM_BIND_TYPE to the size of the structure allocated in Step 1.</span></span>  
  
     <span data-ttu-id="0cf66-133">Атрибут SQL_ATTR_PARAMS_PROCESSED_PTR должен указывать на переменную SQLUINTEGER, в которую помещается число обработанных параметров.</span><span class="sxs-lookup"><span data-stu-id="0cf66-133">Set the SQL_ATTR_PARAMS_PROCESSED_PTR attribute to point to a SQLUINTEGER variable to hold the number of parameters processed.</span></span>  
  
     <span data-ttu-id="0cf66-134">Атрибут SQL_ATTR_PARAMS_STATUS_PTR должен указывать на массив [S] переменных SQLUSSMALLINT, в которые помещаются признаки состояния параметров.</span><span class="sxs-lookup"><span data-stu-id="0cf66-134">Set SQL_ATTR_PARAMS_STATUS_PTR to point to an array[S] of SQLUSSMALLINT variables to hold the parameter status indicators.</span></span>  
  
3.  <span data-ttu-id="0cf66-135">Для каждого маркера параметра вызовите функцию [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md) , чтобы связать значение данных параметра и указатель на длину его данных с соответствующими переменными в первом элементе массива структур, выделенных на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="0cf66-135">For each parameter marker, call [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md) to point the parameter's data value and data length pointer to their variables in the first element of the array of structures allocated in Step 1.</span></span> <span data-ttu-id="0cf66-136">Если параметр использует данные времени выполнения, присвойте ему значение.</span><span class="sxs-lookup"><span data-stu-id="0cf66-136">If the parameter is a data-at-execution parameter, set it up.</span></span>  
  
4.  <span data-ttu-id="0cf66-137">Заполните массив буфера привязанного параметра значениями данных.</span><span class="sxs-lookup"><span data-stu-id="0cf66-137">Fill the bound parameter buffer array with data values.</span></span>  
  
5.  <span data-ttu-id="0cf66-138">Чтобы выполнить инструкцию, вызовите метод [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) .</span><span class="sxs-lookup"><span data-stu-id="0cf66-138">Call [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) to execute the statement.</span></span> <span data-ttu-id="0cf66-139">Драйвер эффективно выполнит инструкцию S раз, по одному разу для каждого набора параметров.</span><span class="sxs-lookup"><span data-stu-id="0cf66-139">The driver efficiently executes the statement S times, once for each set of parameters.</span></span>  
  
6.  <span data-ttu-id="0cf66-140">При использовании входных параметров с данными времени выполнения вызов [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) возвращает SQL_NEED_DATA.</span><span class="sxs-lookup"><span data-stu-id="0cf66-140">If data-at-execution input parameters are used, [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) returns SQL_NEED_DATA.</span></span> <span data-ttu-id="0cf66-141">Отправьте данные по фрагментам при помощи функций [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) и [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span><span class="sxs-lookup"><span data-stu-id="0cf66-141">Send the data in chunks by using [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) and [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span></span>  
  
 <span data-ttu-id="0cf66-142">**Примечание.** Привязка на уровне столбцов и строк используется чаще совместно с функциями [SQLPrepare](https://go.microsoft.com/fwlink/?LinkId=59360) и [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) , чем с функцией [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399).</span><span class="sxs-lookup"><span data-stu-id="0cf66-142">**Note** Column-wise and row-wise binding are more typically used in conjunction with [SQLPrepare Function](https://go.microsoft.com/fwlink/?LinkId=59360) and [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) than with [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cf66-143">См. также:</span><span class="sxs-lookup"><span data-stu-id="0cf66-143">See Also</span></span>  
 [<span data-ttu-id="0cf66-144">Инструкции по выполнению запросов &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="0cf66-144">Executing Queries How-to Topics &#40;ODBC&#41;</span></span>](executing-queries-how-to-topics-odbc.md)  
  
  
