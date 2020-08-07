---
title: Обработка инструкций, создающих сообщения | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- PRINT statement
- messages [ODBC], statements generating messages
- statements [ODBC], message generation
- errors [ODBC], statements generating messages
- SQL Server Native Client ODBC driver, errors
- STATISTICS IO option
- STATISTICS TIME option
- DBCC statements
- SQLExecute function
- RAISERROR statement
- SQLGetDiagRec function
- ODBC error handling, statements generating messages
- SQLExecDirect function
ms.assetid: 672ebdc5-7fa1-4ceb-8d52-fd25ef646654
author: rothja
ms.author: jroth
ms.openlocfilehash: c26376eabb756d356dd71fb3bd8284a6b11dced7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730658"
---
# <a name="processing-statements-that-generate-messages"></a><span data-ttu-id="c519f-102">Обработка инструкций, выдающих сообщения</span><span class="sxs-lookup"><span data-stu-id="c519f-102">Processing Statements That Generate Messages</span></span>
  <span data-ttu-id="c519f-103">Параметры STATISTICS TIME и STATISTICS IO инструкции SET языка [!INCLUDE[tsql](../../includes/tsql-md.md)] используются для получения сведений, помогающих при диагностике долго выполняющихся запросов.</span><span class="sxs-lookup"><span data-stu-id="c519f-103">The [!INCLUDE[tsql](../../includes/tsql-md.md)] SET statement options STATISTICS TIME and STATISTICS IO are used to get information that aids in diagnosing long-running queries.</span></span> <span data-ttu-id="c519f-104">Предыдущие версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] также поддерживают параметр SHOWPLAN для анализа планов запросов.</span><span class="sxs-lookup"><span data-stu-id="c519f-104">Earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] also support the SHOWPLAN option for analyzing query plans.</span></span> <span data-ttu-id="c519f-105">Приложение ODBC может установить эти параметры с помощью следующих инструкций:</span><span class="sxs-lookup"><span data-stu-id="c519f-105">An ODBC application can set these options by executing the following statements:</span></span>  
  
```  
SQLExecDirect(hstmt, "SET SHOWPLAN ON", SQL_NTS);  
SQLExecDirect(hstmt, "SET STATISTICS TIME ON", SQL_NTS90  
);  
SQLExecDirect(hstmt, "SET STATISTICS IO ON", SQL_NTS);  
```  
  
 <span data-ttu-id="c519f-106">Если параметр SET STATISTICS TIME или SET SHOWPLAN имеет значение ON, то **SQLExecute** и **SQLExecDirect** возвращают SQL_SUCCESS_WITH_INFO, и на этом этапе приложение может получить выходные данные инструкции Showplan или Statistics, вызвав **SQLGetDiagRec** , пока не вернет SQL_NO_DATA.</span><span class="sxs-lookup"><span data-stu-id="c519f-106">When SET STATISTICS TIME or SET SHOWPLAN are ON, **SQLExecute** and **SQLExecDirect** return SQL_SUCCESS_WITH_INFO, and, at that point, the application can retrieve the SHOWPLAN or STATISTICS TIME output by calling **SQLGetDiagRec** until it returns SQL_NO_DATA.</span></span> <span data-ttu-id="c519f-107">Каждая строка данных SHOWPLAN возвращается в следующем формате.</span><span class="sxs-lookup"><span data-stu-id="c519f-107">Each line of SHOWPLAN data comes back in the format:</span></span>  
  
```  
szSqlState="01000", *pfNativeError=6223,  
szErrorMsg="[Microsoft][SQL Server Native Client][SQL Server]   
              Table Scan"  
```  
  
 <span data-ttu-id="c519f-108">В [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] версии 7.0 параметр SHOWPLAN заменен на SHOWPLAN_ALL и SHOWPLAN_TEXT, которые возвращают выходные данные в виде результирующего набора, а не набора сообщений.</span><span class="sxs-lookup"><span data-stu-id="c519f-108">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 7.0 replaced the SHOWPLAN option with SHOWPLAN_ALL and SHOWPLAN_TEXT, both of which return output as a result set, not a set of messages.</span></span>  
  
 <span data-ttu-id="c519f-109">Каждая строка STATISTICS TIME возвращается в следующем формате.</span><span class="sxs-lookup"><span data-stu-id="c519f-109">Each line of STATISTICS TIME comes back in the format:</span></span>  
  
```  
szSqlState="01000", *pfNativeError= 3613,  
szErrorMsg="[Microsoft][SQL Server Native Client][SQL Server]  
   SQL Server Parse and Compile Time: cpu time = 0 ms."  
```  
  
 <span data-ttu-id="c519f-110">Выходные данные SET STATISTICS IO недоступны до завершения результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="c519f-110">The output of SET STATISTICS IO is not available until the end of a result set.</span></span> <span data-ttu-id="c519f-111">Чтобы получить СТАТИСТИКУ ввода-вывода статистики, приложение вызывает **SQLGetDiagRec** во время **SQLFetch** или [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md) возвращает SQL_NO_DATA.</span><span class="sxs-lookup"><span data-stu-id="c519f-111">To get STATISTICS IO output, the application calls **SQLGetDiagRec** at the time **SQLFetch** or [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md) returns SQL_NO_DATA.</span></span> <span data-ttu-id="c519f-112">Выходные данные STATISTICS IO возвращаются в следующем формате.</span><span class="sxs-lookup"><span data-stu-id="c519f-112">The output of STATISTICS IO comes back in the format:</span></span>  
  
```  
szSqlState="01000", *pfNativeError= 3615,  
szErrorMsg="[Microsoft][ SQL Server Native Client][SQL Server]  
   Table: testshow  scan count 1,  logical reads: 1,  
   physical reads: 0."  
```  
  
## <a name="using-dbcc-statements"></a><span data-ttu-id="c519f-113">Использование инструкций DBCC</span><span class="sxs-lookup"><span data-stu-id="c519f-113">Using DBCC Statements</span></span>  
 <span data-ttu-id="c519f-114">Инструкции DBCC возвращают данные в виде сообщений, а не результирующих наборов.</span><span class="sxs-lookup"><span data-stu-id="c519f-114">DBCC statements return their data as messages, not result sets.</span></span> <span data-ttu-id="c519f-115">**SQLExecDirect** или **SQLExecute** возвращают SQL_SUCCESS_WITH_INFO, и приложение получает выходные данные, вызывая **SQLGetDiagRec** , пока не вернет SQL_NO_DATA.</span><span class="sxs-lookup"><span data-stu-id="c519f-115">**SQLExecDirect** or **SQLExecute** return SQL_SUCCESS_WITH_INFO, and the application retrieves the output by calling **SQLGetDiagRec** until it returns SQL_NO_DATA.</span></span>  
  
 <span data-ttu-id="c519f-116">Например, следующая инструкция возвращает значение SQL_SUCCESS_WITH_INFO.</span><span class="sxs-lookup"><span data-stu-id="c519f-116">For example, the following statement returns SQL_SUCCESS_WITH_INFO:</span></span>  
  
```  
SQLExecDirect(hstmt, "DBCC CHECKTABLE(Authors)", SQL_NTS);  
```  
  
 <span data-ttu-id="c519f-117">Вызовы **SQLGetDiagRec** возвращают:</span><span class="sxs-lookup"><span data-stu-id="c519f-117">Calls to **SQLGetDiagRec** return:</span></span>  
  
```  
szSqlState = "01000", *pfNativeError = 2536,  
szErrorMsg="[Microsoft][ SQL Server Native Client][SQL Server]  
   Checking authors"  
szSqlState = "01000", *pfNativeError = 2579,  
szErrorMsg="[Microsoft][ SQL Server Native Client][SQL Server]  
   The total number of data pages in this table is 1."  
szSqlState = "01000", *pfNativeError = 7929,  
szErrorMsg="[Microsoft][ SQL Server Native Client][SQL Server]  
   Table has 23 data rows."  
szSqlState = "01000", *pfNativeError = 2528  
szErrorMsg="[Microsoft][ SQL Server Native Client][SQL Server]  
   DBCC execution completed. If DBCC printed error messages,  
   see your System Administrator."  
```  
  
## <a name="using-print-and-raiserror-statements"></a><span data-ttu-id="c519f-118">Использование инструкций PRINT и RAISERROR</span><span class="sxs-lookup"><span data-stu-id="c519f-118">Using PRINT and RAISERROR Statements</span></span>  
 [!INCLUDE[tsql](../../includes/tsql-md.md)]<span data-ttu-id="c519f-119">Инструкции PRINT и RAISERROR также возвращают данные путем вызова **SQLGetDiagRec**.</span><span class="sxs-lookup"><span data-stu-id="c519f-119">PRINT and RAISERROR statements also return data by calling **SQLGetDiagRec**.</span></span> <span data-ttu-id="c519f-120">Инструкции PRINT приводят к тому, что выполнение инструкции SQL возвращает SQL_SUCCESS_WITH_INFO, а последующий вызов **SQLGetDiagRec** возвращает значение *SQLSTATE* 01000.</span><span class="sxs-lookup"><span data-stu-id="c519f-120">PRINT statements cause the SQL statement execution to return SQL_SUCCESS_WITH_INFO, and a subsequent call to **SQLGetDiagRec** returns a *SQLState* of 01000.</span></span> <span data-ttu-id="c519f-121">Инструкция RAISERROR со степенью серьезности 10 или ниже работает так же, как PRINT.</span><span class="sxs-lookup"><span data-stu-id="c519f-121">A RAISERROR with a severity of ten or lower behaves the same as PRINT.</span></span> <span data-ttu-id="c519f-122">Инструкция RAISERROR с уровнем серьезности 11 или выше приводит к тому, что оператор Execute возвращает SQL_ERROR, а последующий вызов **SQLGetDiagRec** возвращает *SQLSTATE* 42000.</span><span class="sxs-lookup"><span data-stu-id="c519f-122">A RAISERROR with a severity of 11 or higher causes the execute to return SQL_ERROR, and a subsequent call to **SQLGetDiagRec** returns *SQLState* 42000.</span></span> <span data-ttu-id="c519f-123">Например, следующая инструкция возвращает значение SQL_SUCCESS_WITH_INFO.</span><span class="sxs-lookup"><span data-stu-id="c519f-123">For example, the following statement returns SQL_SUCCESS_WITH_INFO:</span></span>  
  
```  
SQLExecDirect (hstmt, "PRINT  'Some message' ", SQL_NTS);  
```  
  
 <span data-ttu-id="c519f-124">Вызов **SQLGetDiagRec** возвращает:</span><span class="sxs-lookup"><span data-stu-id="c519f-124">Calling **SQLGetDiagRec** returns:</span></span>  
  
```  
szSQLState = "01000", *pfNative Error = 0,  
szErrorMsg= "[Microsoft] [SQL Server Native Client][SQL Server]  
   Some message"  
```  
  
 <span data-ttu-id="c519f-125">Следующая инструкция возвращает значение SQL_SUCCESS_WITH_INFO.</span><span class="sxs-lookup"><span data-stu-id="c519f-125">The following statement returns SQL_SUCCESS_WITH_INFO:</span></span>  
  
```  
SQLExecDirect (hstmt, "RAISERROR ('Sample error 1.', 10, -1)",  
   SQL_NTS)  
```  
  
 <span data-ttu-id="c519f-126">Вызов **SQLGetDiagRec** возвращает:</span><span class="sxs-lookup"><span data-stu-id="c519f-126">Calling **SQLGetDiagRec** returns:</span></span>  
  
```  
szSQLState = "01000", *pfNative Error = 50000,  
szErrorMsg= "[Microsoft] [SQL Server Native Client][SQL Server]  
   Sample error 1."  
```  
  
 <span data-ttu-id="c519f-127">Следующая инструкция возвращает значение SQL_ERROR.</span><span class="sxs-lookup"><span data-stu-id="c519f-127">The following statement returns SQL_ERROR:</span></span>  
  
```  
SQLExecDirect (hstmt, "RAISERROR ('Sample error 2.', 11, -1)", SQL_NTS)  
```  
  
 <span data-ttu-id="c519f-128">Вызов **SQLGetDiagRec** возвращает:</span><span class="sxs-lookup"><span data-stu-id="c519f-128">Calling **SQLGetDiagRec** returns:</span></span>  
  
```  
szSQLState = "42000", *pfNative Error = 50000,  
szErrorMsg= "[Microsoft] [SQL Server Native Client][SQL Server]  
   Sample error 2."  
```  
  
 <span data-ttu-id="c519f-129">Время вызова **SQLGetDiagRec** является критическим, если выходные данные инструкций Print или RAISERROR включаются в результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="c519f-129">The timing of calling **SQLGetDiagRec** is critical when output from PRINT or RAISERROR statements is included in a result set.</span></span> <span data-ttu-id="c519f-130">Вызов **SQLGetDiagRec** для получения выходных данных печати или RAISERROR должен выполняться сразу после инструкции, принимающей SQL_ERROR или SQL_SUCCESS_WITH_INFO.</span><span class="sxs-lookup"><span data-stu-id="c519f-130">The call to **SQLGetDiagRec** to retrieve the PRINT or RAISERROR output must be made immediately after the statement that receives SQL_ERROR or SQL_SUCCESS_WITH_INFO.</span></span> <span data-ttu-id="c519f-131">Это просто в случае выполнения отдельной инструкции SQL, как показано в примере выше.</span><span class="sxs-lookup"><span data-stu-id="c519f-131">This is straightforward when only a single SQL statement is executed, as in the examples above.</span></span> <span data-ttu-id="c519f-132">В этих случаях вызов **SQLExecDirect** или **SQLExecute** возвращает SQL_ERROR или SQL_SUCCESS_WITH_INFO и **SQLGetDiagRec** может быть вызван.</span><span class="sxs-lookup"><span data-stu-id="c519f-132">In these cases, the call to **SQLExecDirect** or **SQLExecute** returns SQL_ERROR or SQL_SUCCESS_WITH_INFO and **SQLGetDiagRec** can then be called.</span></span> <span data-ttu-id="c519f-133">При программировании циклов для обработки выходных данных пакета инструкций SQL или выполнении хранимых процедур [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] возникают осложнения.</span><span class="sxs-lookup"><span data-stu-id="c519f-133">It is less straightforward when coding loops to handle the output of a batch of SQL statements or when executing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures.</span></span>  
  
 <span data-ttu-id="c519f-134">В этом случае [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] возвращает результирующий набор для каждой инструкции SELECT, выполненной в пакете или хранимой процедуре.</span><span class="sxs-lookup"><span data-stu-id="c519f-134">In this case, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] returns a result set for every SELECT statement executed in a batch or stored procedure.</span></span> <span data-ttu-id="c519f-135">Если пакет или процедура содержит инструкции PRINT или RAISERROR, то их выходные данные чередуются с результирующими наборами инструкций.</span><span class="sxs-lookup"><span data-stu-id="c519f-135">If the batch or procedure contains PRINT or RAISERROR statements, the output for these is interleaved with the SELECT statement result sets.</span></span> <span data-ttu-id="c519f-136">Если первый оператор в пакете или процедуре является ПЕЧАТЬю или ИНСТРУКЦИей RAISERROR, то **SQLExecute** или **SQLExecDirect** возвращает SQL_SUCCESS_WITH_INFO или SQL_ERROR, и приложению необходимо вызвать **SQLGetDiagRec** до тех пор, пока не вернет SQL_NO_DATA для получения сведений о печати или инструкции RAISERROR.</span><span class="sxs-lookup"><span data-stu-id="c519f-136">If the first statement in the batch or procedure is a PRINT or RAISERROR, the **SQLExecute** or **SQLExecDirect** returns SQL_SUCCESS_WITH_INFO or SQL_ERROR, and the application needs to call **SQLGetDiagRec** until it returns SQL_NO_DATA to retrieve the PRINT or RAISERROR information.</span></span>  
  
 <span data-ttu-id="c519f-137">Если инструкция PRINT или RAISERROR находится после инструкции SQL (например, инструкции SELECT), то сведения о печати или RAISERROR возвращаются, когда [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md)позиции в результирующем наборе, содержащем ошибку.</span><span class="sxs-lookup"><span data-stu-id="c519f-137">If the PRINT or RAISERROR statement comes after an SQL statement (such as a SELECT statement), then the PRINT or RAISERROR information is returned when [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md)positions on the result set containing the error.</span></span> <span data-ttu-id="c519f-138">**SQLMoreResults** возвращает SQL_SUCCESS_WITH_INFO или SQL_ERROR в зависимости от серьезности сообщения.</span><span class="sxs-lookup"><span data-stu-id="c519f-138">**SQLMoreResults** returns SQL_SUCCESS_WITH_INFO or SQL_ERROR depending on the severity of the message.</span></span> <span data-ttu-id="c519f-139">Сообщения извлекаются путем вызова **SQLGetDiagRec** до тех пор, пока не будут возвращены SQL_NO_DATA.</span><span class="sxs-lookup"><span data-stu-id="c519f-139">Messages are retrieved by calling **SQLGetDiagRec** until it returns SQL_NO_DATA.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c519f-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="c519f-140">See Also</span></span>  
 [<span data-ttu-id="c519f-141">Обработка ошибок и сообщений</span><span class="sxs-lookup"><span data-stu-id="c519f-141">Handling Errors and Messages</span></span>](handling-errors-and-messages.md)  
  
  
