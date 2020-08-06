---
title: Подготовка и выполнение инструкции (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- statement execution
- statement preparation
ms.assetid: 0adecc63-4da5-486c-bc48-09a004a2fae6
author: rothja
ms.author: jroth
ms.openlocfilehash: 607d8ad1509eca1204f6d029842b04120d3f5d9a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739872"
---
# <a name="prepare-and-execute-a-statement-odbc"></a><span data-ttu-id="d40ad-102">Подготовка и выполнение инструкцию (ODBC)</span><span class="sxs-lookup"><span data-stu-id="d40ad-102">Prepare and Execute a Statement (ODBC)</span></span>
    
### <a name="to-prepare-a-statement-once-and-then-execute-it-multiple-times"></a><span data-ttu-id="d40ad-103">Однократная подготовка инструкции и многократное ее выполнение</span><span class="sxs-lookup"><span data-stu-id="d40ad-103">To prepare a statement once, and then execute it multiple times</span></span>  
  
1.  <span data-ttu-id="d40ad-104">Вызовите функцию [SQLPrepare](https://go.microsoft.com/fwlink/?LinkId=59360) , чтобы подготовить инструкцию.</span><span class="sxs-lookup"><span data-stu-id="d40ad-104">Call [SQLPrepare Function](https://go.microsoft.com/fwlink/?LinkId=59360) to prepare the statement.</span></span>  
  
2.  <span data-ttu-id="d40ad-105">Можно также вызвать метод [SQLNumParams](https://go.microsoft.com/fwlink/?LinkId=58404) , чтобы определить количество параметров в подготовленной инструкции.</span><span class="sxs-lookup"><span data-stu-id="d40ad-105">Optionally, call [SQLNumParams](https://go.microsoft.com/fwlink/?LinkId=58404) to determine the number of parameters in the prepared statement.</span></span>  
  
3.  <span data-ttu-id="d40ad-106">Выполните следующие действия для каждого параметра подготовленной инструкции (не обязательно).</span><span class="sxs-lookup"><span data-stu-id="d40ad-106">Optionally, for each parameter in the prepared statement:</span></span>  
  
    -   <span data-ttu-id="d40ad-107">Вызовите [SQLDescribeParam](../../native-client-odbc-api/sqldescribeparam.md) для получения сведений о параметре.</span><span class="sxs-lookup"><span data-stu-id="d40ad-107">Call [SQLDescribeParam](../../native-client-odbc-api/sqldescribeparam.md) to get parameter information.</span></span>  
  
    -   <span data-ttu-id="d40ad-108">Привяжите каждый параметр к переменной программы с помощью [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md).</span><span class="sxs-lookup"><span data-stu-id="d40ad-108">Bind each parameter to a program variable by using [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md).</span></span> <span data-ttu-id="d40ad-109">Присвойте значения всем параметрам времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="d40ad-109">Set up any data-at-execution parameters.</span></span>  
  
4.  <span data-ttu-id="d40ad-110">Перед каждым выполнением подготовленной инструкции.</span><span class="sxs-lookup"><span data-stu-id="d40ad-110">For each execution of a prepared statement:</span></span>  
  
    -   <span data-ttu-id="d40ad-111">Если в инструкции имеются маркеры параметров, поместите значения данных в буфер связанного параметра.</span><span class="sxs-lookup"><span data-stu-id="d40ad-111">If the statement has parameter markers, put the data values into the bound parameter buffer.</span></span>  
  
    -   <span data-ttu-id="d40ad-112">Вызовите функцию [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) , чтобы выполнить подготовленную инструкцию.</span><span class="sxs-lookup"><span data-stu-id="d40ad-112">Call [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) to execute the prepared statement.</span></span>  
  
    -   <span data-ttu-id="d40ad-113">При использовании входных параметров времени выполнения функция [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) возвращает SQL_NEED_DATA.</span><span class="sxs-lookup"><span data-stu-id="d40ad-113">If data-at-execution input parameters are used, [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) returns SQL_NEED_DATA.</span></span> <span data-ttu-id="d40ad-114">Отправьте данные по фрагментам при помощи функций [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) и [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span><span class="sxs-lookup"><span data-stu-id="d40ad-114">Send the data in chunks by using [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) and [SQLPutData](../../native-client-odbc-api/sqlputdata.md).</span></span>  
  
### <a name="to-prepare-a-statement-with-column-wise-parameter-binding"></a><span data-ttu-id="d40ad-115">Подготовка инструкции с привязкой параметра на уровне столбца</span><span class="sxs-lookup"><span data-stu-id="d40ad-115">To prepare a statement with column-wise parameter binding</span></span>  
  
1.  <span data-ttu-id="d40ad-116">Вызовите функцию [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) , чтобы задать следующие атрибуты.</span><span class="sxs-lookup"><span data-stu-id="d40ad-116">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the following attributes:</span></span>  
  
    -   <span data-ttu-id="d40ad-117">Атрибуту SQL_ATTR_PARAMSET_SIZE задайте число наборов параметров (S).</span><span class="sxs-lookup"><span data-stu-id="d40ad-117">Set SQL_ATTR_PARAMSET_SIZE to the number of sets (S) of parameters.</span></span>  
  
    -   <span data-ttu-id="d40ad-118">Атрибуту SQL_ATTR_PARAM_BIND_TYPE задайте значение SQL_PARAMETER_BIND_BY_COLUMN.</span><span class="sxs-lookup"><span data-stu-id="d40ad-118">Set SQL_ATTR_PARAM_BIND_TYPE to SQL_PARAMETER_BIND_BY_COLUMN.</span></span>  
  
    -   <span data-ttu-id="d40ad-119">Атрибут SQL_ATTR_PARAMS_PROCESSED_PTR должен указывать на переменную SQLUINTEGER, в которую помещается число обработанных параметров.</span><span class="sxs-lookup"><span data-stu-id="d40ad-119">Set the SQL_ATTR_PARAMS_PROCESSED_PTR attribute to point to a SQLUINTEGER variable to hold the number of parameters processed.</span></span>  
  
    -   <span data-ttu-id="d40ad-120">Задайте значение SQL_ATTR_PARAMS_STATUS_PTR, которое указывает на массив [S] переменных SQLUSSMALLINT, предназначенный для сохранения признаков состояния параметра.</span><span class="sxs-lookup"><span data-stu-id="d40ad-120">Set SQL_ATTR_PARAMS_STATUS_PTR to point to an array[S] of SQLUSSMALLINT variables to hold parameter status indicators.</span></span>  
  
2.  <span data-ttu-id="d40ad-121">Вызовите SQLPrepare, чтобы подготовить инструкцию.</span><span class="sxs-lookup"><span data-stu-id="d40ad-121">Call SQLPrepare to prepare the statement.</span></span>  
  
3.  <span data-ttu-id="d40ad-122">Можно также вызвать метод [SQLNumParams](https://go.microsoft.com/fwlink/?LinkId=58404) , чтобы определить количество параметров в подготовленной инструкции.</span><span class="sxs-lookup"><span data-stu-id="d40ad-122">Optionally, call [SQLNumParams](https://go.microsoft.com/fwlink/?LinkId=58404) to determine the number of parameters in the prepared statement.</span></span>  
  
4.  <span data-ttu-id="d40ad-123">При необходимости для каждого параметра в подготовленной инструкции вызовите SQLDescribeParam, чтобы получить сведения о параметрах.</span><span class="sxs-lookup"><span data-stu-id="d40ad-123">Optionally, for each parameter in the prepared statement, call SQLDescribeParam to get parameter information.</span></span>  
  
5.  <span data-ttu-id="d40ad-124">Для каждого маркера параметра выполните следующее.</span><span class="sxs-lookup"><span data-stu-id="d40ad-124">For each parameter marker:</span></span>  
  
    -   <span data-ttu-id="d40ad-125">Выделите массив из S буферов параметра для сохранения значений данных.</span><span class="sxs-lookup"><span data-stu-id="d40ad-125">Allocate an array of S parameter buffers to store data values.</span></span>  
  
    -   <span data-ttu-id="d40ad-126">Выделите массив из S буферов параметра для сохранения длин данных.</span><span class="sxs-lookup"><span data-stu-id="d40ad-126">Allocate an array of S parameter buffers to store data lengths.</span></span>  
  
    -   <span data-ttu-id="d40ad-127">Вызовите функцию SQLBindParameter , чтобы связать массивы значений данных и длин данных с параметром инструкции.</span><span class="sxs-lookup"><span data-stu-id="d40ad-127">Call SQLBindParameter to bind the parameter data value and data length arrays to the statement parameter.</span></span>  
  
    -   <span data-ttu-id="d40ad-128">Если параметр использует данные времени выполнения типов text или image, присвойте ему значение.</span><span class="sxs-lookup"><span data-stu-id="d40ad-128">If the parameter is a data-at-execution text or image parameter, set it up.</span></span>  
  
    -   <span data-ttu-id="d40ad-129">Если используются параметры с данными времени выполнения, присвойте им значения.</span><span class="sxs-lookup"><span data-stu-id="d40ad-129">If any data-at-execution parameters are used, set them up.</span></span>  
  
6.  <span data-ttu-id="d40ad-130">Перед каждым выполнением подготовленной инструкции.</span><span class="sxs-lookup"><span data-stu-id="d40ad-130">For each execution of a prepared statement:</span></span>  
  
    -   <span data-ttu-id="d40ad-131">Поместите значения и длины S-данных в массивы связанных параметров.</span><span class="sxs-lookup"><span data-stu-id="d40ad-131">Put the S data values and S data lengths into the bound parameter arrays.</span></span>  
  
    -   <span data-ttu-id="d40ad-132">Вызовите функцию SQLExecute, чтобы выполнить подготовленную инструкцию.</span><span class="sxs-lookup"><span data-stu-id="d40ad-132">Call SQLExecute to execute the prepared statement.</span></span>  
  
    -   <span data-ttu-id="d40ad-133">При использовании входных параметров времени выполнения функция SQLExecute возвращает SQL_NEED_DATA.</span><span class="sxs-lookup"><span data-stu-id="d40ad-133">If data-at-execution input parameters are used, SQLExecute returns SQL_NEED_DATA.</span></span> <span data-ttu-id="d40ad-134">Отправьте данные по фрагментам при помощи функций SQLParamData и SQLPutData.</span><span class="sxs-lookup"><span data-stu-id="d40ad-134">Send the data in chunks by using SQLParamData and SQLPutData.</span></span>  
  
### <a name="to-prepare-a-statement-with-row-wise-bound-parameters"></a><span data-ttu-id="d40ad-135">Подготовка инструкции с привязкой параметра на уровне строки</span><span class="sxs-lookup"><span data-stu-id="d40ad-135">To prepare a statement with row-wise bound parameters</span></span>  
  
1.  <span data-ttu-id="d40ad-136">Выделите массив структур [S], где S — число наборов параметров.</span><span class="sxs-lookup"><span data-stu-id="d40ad-136">Allocate an array[S] of structures, where S is the number of sets of parameters.</span></span> <span data-ttu-id="d40ad-137">Структура имеет по одному элементу для каждого параметра, а каждый элемент состоит из двух частей.</span><span class="sxs-lookup"><span data-stu-id="d40ad-137">The structure has one element for each parameter, and each element has two parts:</span></span>  
  
    -   <span data-ttu-id="d40ad-138">Первая часть — переменная соответствующего типа данных, в которую помещаются данные параметра.</span><span class="sxs-lookup"><span data-stu-id="d40ad-138">The first part is a variable of the appropriate data type to hold the parameter data.</span></span>  
  
    -   <span data-ttu-id="d40ad-139">Вторая часть — переменная SQLINTEGER, в которую помещается признак состояния.</span><span class="sxs-lookup"><span data-stu-id="d40ad-139">The second part is a SQLINTEGER variable to hold the status indicator.</span></span>  
  
2.  <span data-ttu-id="d40ad-140">Вызовите функцию [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) , чтобы задать следующие атрибуты.</span><span class="sxs-lookup"><span data-stu-id="d40ad-140">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the following attributes:</span></span>  
  
    -   <span data-ttu-id="d40ad-141">Атрибуту SQL_ATTR_PARAMSET_SIZE задайте число наборов параметров (S).</span><span class="sxs-lookup"><span data-stu-id="d40ad-141">Set SQL_ATTR_PARAMSET_SIZE to the number of sets (S) of parameters.</span></span>  
  
    -   <span data-ttu-id="d40ad-142">Атрибуту SQL_ATTR_PARAM_BIND_TYPE задайте размер структуры, выделенной в шаге 1.</span><span class="sxs-lookup"><span data-stu-id="d40ad-142">Set SQL_ATTR_PARAM_BIND_TYPE to the size of the structure allocated in Step 1.</span></span>  
  
    -   <span data-ttu-id="d40ad-143">Атрибут SQL_ATTR_PARAMS_PROCESSED_PTR должен указывать на переменную SQLUINTEGER, в которую помещается число обработанных параметров.</span><span class="sxs-lookup"><span data-stu-id="d40ad-143">Set the SQL_ATTR_PARAMS_PROCESSED_PTR attribute to point to a SQLUINTEGER variable to hold the number of parameters processed.</span></span>  
  
    -   <span data-ttu-id="d40ad-144">Задайте значение SQL_ATTR_PARAMS_STATUS_PTR, которое указывает на массив [S] переменных SQLUSSMALLINT, предназначенный для сохранения признаков состояния параметра.</span><span class="sxs-lookup"><span data-stu-id="d40ad-144">Set SQL_ATTR_PARAMS_STATUS_PTR to point to an array[S] of SQLUSSMALLINT variables to hold parameter status indicators.</span></span>  
  
3.  <span data-ttu-id="d40ad-145">Вызовите SQLPrepare, чтобы подготовить инструкцию.</span><span class="sxs-lookup"><span data-stu-id="d40ad-145">Call SQLPrepare to prepare the statement.</span></span>  
  
4.  <span data-ttu-id="d40ad-146">Для каждого маркера параметра вызовите SQLBindParameter, чтобы указать значения данных параметра и указатель длины данных на их переменные в первом элементе массива структур, выделенных на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="d40ad-146">For each parameter marker, call SQLBindParameter to point the parameter data value and data length pointer to their variables in the first element of the array of structures allocated in Step 1.</span></span> <span data-ttu-id="d40ad-147">Если параметр использует данные времени выполнения, присвойте ему значение.</span><span class="sxs-lookup"><span data-stu-id="d40ad-147">If the parameter is a data-at-execution parameter, set it up.</span></span>  
  
5.  <span data-ttu-id="d40ad-148">Перед каждым выполнением подготовленной инструкции.</span><span class="sxs-lookup"><span data-stu-id="d40ad-148">For each execution of a prepared statement:</span></span>  
  
    -   <span data-ttu-id="d40ad-149">Заполните массив буфера привязанного параметра значениями данных.</span><span class="sxs-lookup"><span data-stu-id="d40ad-149">Fill the bound parameter buffer array with data values.</span></span>  
  
    -   <span data-ttu-id="d40ad-150">Вызовите функцию SQLExecute, чтобы выполнить подготовленную инструкцию.</span><span class="sxs-lookup"><span data-stu-id="d40ad-150">Call SQLExecute to execute the prepared statement.</span></span> <span data-ttu-id="d40ad-151">Драйвер эффективно выполнит инструкцию SQL S раз, по одному разу для каждого набора параметров.</span><span class="sxs-lookup"><span data-stu-id="d40ad-151">The driver efficiently executes the SQL statement S times, once for each set of parameters.</span></span>  
  
    -   <span data-ttu-id="d40ad-152">При использовании входных параметров времени выполнения функция SQLExecute возвращает SQL_NEED_DATA.</span><span class="sxs-lookup"><span data-stu-id="d40ad-152">If data-at-execution input parameters are used, SQLExecute returns SQL_NEED_DATA.</span></span> <span data-ttu-id="d40ad-153">Отправьте данные по фрагментам при помощи функций SQLParamData и SQLPutData.</span><span class="sxs-lookup"><span data-stu-id="d40ad-153">Send the data in chunks by using SQLParamData and SQLPutData.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d40ad-154">См. также:</span><span class="sxs-lookup"><span data-stu-id="d40ad-154">See Also</span></span>  
 [<span data-ttu-id="d40ad-155">Инструкции по выполнению запросов &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="d40ad-155">Executing Queries How-to Topics &#40;ODBC&#41;</span></span>](executing-queries-how-to-topics-odbc.md)  
  
  
