---
title: Ведение журнала длительных запросов (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- queries [ODBC]
ms.assetid: b9c1ddce-1dd9-409d-a414-8b544d616273
author: rothja
ms.author: jroth
ms.openlocfilehash: f73dbf6fe8fc4b3dfbbbc0012d14a58614b218dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749816"
---
# <a name="log-long-running-queries-odbc"></a><span data-ttu-id="e59cc-102">Ведение журналов длительных запросов (ODBC)</span><span class="sxs-lookup"><span data-stu-id="e59cc-102">Log Long-Running Queries (ODBC)</span></span>
  <span data-ttu-id="e59cc-103">В этом образце демонстрируются параметры ODBC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], относящиеся к драйверу, для долго выполняемых запросов.</span><span class="sxs-lookup"><span data-stu-id="e59cc-103">This sample shows the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ODBC driver-specific options to log long-running queries.</span></span> <span data-ttu-id="e59cc-104">При запуске этот образец создает файл журнала Odbcqry.log, содержащий список запросов, время выполнения которых превысило интервал, установленный приложением.</span><span class="sxs-lookup"><span data-stu-id="e59cc-104">When run, this sample creates Odbcqry.log, which contains a list of queries whose execution exceeds an interval set by the application.</span></span> <span data-ttu-id="e59cc-105">Этот образец не поддерживается на архитектуре IA64.</span><span class="sxs-lookup"><span data-stu-id="e59cc-105">This sample is not supported on IA64.</span></span> <span data-ttu-id="e59cc-106">Этот образец разработан для ODBC версии 3.0 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="e59cc-106">This sample was developed for ODBC version 3.0 or later.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e59cc-107">По возможности используйте аутентификацию Windows.</span><span class="sxs-lookup"><span data-stu-id="e59cc-107">When possible, use Windows Authentication.</span></span> <span data-ttu-id="e59cc-108">Если проверка подлинности Windows недоступна, запросите у пользователя ввод учетных данных во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="e59cc-108">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="e59cc-109">Избегайте хранения учетных данных в файле.</span><span class="sxs-lookup"><span data-stu-id="e59cc-109">Avoid storing credentials in a file.</span></span> <span data-ttu-id="e59cc-110">Если необходимо сохранить учетные данные, зашифруйте их с помощью [API-интерфейса шифрования Win32](https://go.microsoft.com/fwlink/?LinkId=64532).</span><span class="sxs-lookup"><span data-stu-id="e59cc-110">If you must persist credentials, you should encrypt them with the [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532).</span></span>  
  
### <a name="to-log-long-running-queries-using-odbc-administrator"></a><span data-ttu-id="e59cc-111">Ведение журнала длительно выполняющихся запросов с помощью администратора ODBC</span><span class="sxs-lookup"><span data-stu-id="e59cc-111">To log long-running queries using ODBC Administrator</span></span>  
  
1.  <span data-ttu-id="e59cc-112">На **панели управления**дважды щелкните **Администрирование** , а затем дважды щелкните **Источники данных (ODBC)**.</span><span class="sxs-lookup"><span data-stu-id="e59cc-112">In **Control Panel**, double-click **Administrative Tools** and then double-click **Data Sources (ODBC)**.</span></span> <span data-ttu-id="e59cc-113">(Можно также запустить файл odbcad32.exe из командной строки.)</span><span class="sxs-lookup"><span data-stu-id="e59cc-113">(Alternatively, you can run odbcad32.exe from the command prompt.)</span></span>  
  
2.  <span data-ttu-id="e59cc-114">Щелкните вкладку **DSN пользователя**, **системное имя DSN**или **Файловый DSN** .</span><span class="sxs-lookup"><span data-stu-id="e59cc-114">Click the **User DSN**, **System DSN**, or **File DSN** tab.</span></span>  
  
3.  <span data-ttu-id="e59cc-115">Щелкните источник данных, для которого создается журнал длительно выполняющихся запросов.</span><span class="sxs-lookup"><span data-stu-id="e59cc-115">Click the data source for which to log long-running queries.</span></span>  
  
4.  <span data-ttu-id="e59cc-116">Щелкните **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="e59cc-116">Click **Configure**.</span></span>  
  
5.  <span data-ttu-id="e59cc-117">В мастере настройки имени DSN Microsoft SQL Server перейдите к странице с **сохраненными запросами длительного выполнения в файле журнала**.</span><span class="sxs-lookup"><span data-stu-id="e59cc-117">In the Microsoft SQL Server Configure DSN Wizard, navigate to the page with **Save long-running queries to the log file**.</span></span>  
  
6.  <span data-ttu-id="e59cc-118">Выберите **сохранить длительные запросы в файл журнала**.</span><span class="sxs-lookup"><span data-stu-id="e59cc-118">Select **Save long-running queries to the log file**.</span></span> <span data-ttu-id="e59cc-119">В текстовое поле введите имя файла журнала для запросов длительного выполнения.</span><span class="sxs-lookup"><span data-stu-id="e59cc-119">In the box, place the name of the file where the long-running queries should be logged.</span></span> <span data-ttu-id="e59cc-120">При необходимости нажмите кнопку **Обзор** , чтобы просмотреть файловую систему для журнала запросов.</span><span class="sxs-lookup"><span data-stu-id="e59cc-120">Optionally, click **Browse** to browse the file system for the query log.</span></span>  
  
7.  <span data-ttu-id="e59cc-121">Задайте интервал времени ожидания запроса (в миллисекундах) в поле **длительное время запроса (миллисекунды)** .</span><span class="sxs-lookup"><span data-stu-id="e59cc-121">Set a query time-out interval, in milliseconds, in the **Long query time (milliseconds)** box.</span></span>  
  
### <a name="to-log-long-running-queries-data-programmatically"></a><span data-ttu-id="e59cc-122">Ведение журнала длительно выполняющихся запросов программным образом</span><span class="sxs-lookup"><span data-stu-id="e59cc-122">To log long-running queries data programmatically</span></span>  
  
1.  <span data-ttu-id="e59cc-123">Вызовите [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) с SQL_COPT_SS_PERF_QUERY_LOG, а также полный путь и имя файла журнала долго выполняющегося запроса.</span><span class="sxs-lookup"><span data-stu-id="e59cc-123">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_PERF_QUERY_LOG and the full path and file name of the long-running query log file.</span></span> <span data-ttu-id="e59cc-124">Пример:</span><span class="sxs-lookup"><span data-stu-id="e59cc-124">For example:</span></span>  
  
    ```  
    C:\\Odbcqry.log  
    ```  
  
2.  <span data-ttu-id="e59cc-125">Вызовите [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) с SQL_COPT_SS_PERF_QUERY_INTERVAL и задайте интервал времени ожидания (в миллисекундах).</span><span class="sxs-lookup"><span data-stu-id="e59cc-125">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_PERF_QUERY_INTERVAL and set to the time-out interval, in milliseconds.</span></span>  
  
3.  <span data-ttu-id="e59cc-126">Вызовите [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) с SQL_COPT_SS_PERF_QUERY и SQL_PERF_START, чтобы начать запись долго выполняющихся запросов.</span><span class="sxs-lookup"><span data-stu-id="e59cc-126">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_PERF_QUERY and SQL_PERF_START to start logging long-running queries.</span></span>  
  
4.  <span data-ttu-id="e59cc-127">Вызовите [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) с помощью SQL_COPT_SS_PERF_QUERY и SQL_PERF_STOP, чтобы прерывать ведение журнала долго выполняющихся запросов.</span><span class="sxs-lookup"><span data-stu-id="e59cc-127">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_PERF_QUERY and SQL_PERF_STOP to stop logging long-running queries.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e59cc-128">Пример</span><span class="sxs-lookup"><span data-stu-id="e59cc-128">Example</span></span>  
 <span data-ttu-id="e59cc-129">Также необходим источник данных ODBC с именем AdventureWorks, для которого базой данных по умолчанию является образец базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="e59cc-129">You will need an ODBC data source called AdventureWorks, whose default database is the AdventureWorks sample database.</span></span> <span data-ttu-id="e59cc-130">(Образец базы данных AdventureWorks можно скачать на домашней странице [Microsoft SQL Server примеры и проекты сообщества](https://go.microsoft.com/fwlink/?LinkID=85384) .) Этот источник данных должен быть основан на драйвере ODBC, предоставленном операционной системой (имя драйвера — "SQL Server").</span><span class="sxs-lookup"><span data-stu-id="e59cc-130">(You can download the AdventureWorks sample database from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.) This data source must be based on the ODBC driver that is supplied by the operating system (the driver name is "SQL Server").</span></span> <span data-ttu-id="e59cc-131">При построении и запуске этого образца как 32-разрядного приложения в 64-разрядной операционной системе необходимо создать источник данных ODBC с помощью программы администрирования ODBC (исполняемый файл %windir%\SysWOW64\odbcad32.exe).</span><span class="sxs-lookup"><span data-stu-id="e59cc-131">If you will build and run this sample as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
 <span data-ttu-id="e59cc-132">Этот образец соединяется с установленным на компьютер экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e59cc-132">This sample connects to your computer's default [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="e59cc-133">Чтобы соединиться с именованным экземпляром, измените определение источника данных ODBC, указав экземпляр в следующем формате: Сервер\ИменованныйЭкземпляр.</span><span class="sxs-lookup"><span data-stu-id="e59cc-133">To connect to a named instance, change the definition of the ODBC data source to specify the instance using the following format: server\namedinstance.</span></span> <span data-ttu-id="e59cc-134">По умолчанию [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] устанавливается на именованный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="e59cc-134">By default, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] installs to a named instance.</span></span>  
  
 <span data-ttu-id="e59cc-135">Скомпилируйте с библиотекой odbc32.lib.</span><span class="sxs-lookup"><span data-stu-id="e59cc-135">Compile with odbc32.lib.</span></span>  
  
```  
// compile with: odbc32.lib  
#include <stdio.h>  
#include <string.h>  
#include <windows.h>  
#include <sql.h>  
#include <sqlext.h>  
#include <odbcss.h>  
  
SQLHENV henv = SQL_NULL_HENV;  
SQLHDBC hdbc1 = SQL_NULL_HDBC;       
SQLHSTMT hstmt1 = SQL_NULL_HSTMT;  
  
void Cleanup() {  
   if (hstmt1 != SQL_NULL_HSTMT)  
      SQLFreeHandle(SQL_HANDLE_STMT, hstmt1);  
  
   if (hdbc1 != SQL_NULL_HDBC) {  
      SQLDisconnect(hdbc1);  
      SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   }  
  
   if (henv != SQL_NULL_HENV)  
      SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
  
int main() {  
   RETCODE retcode;  
  
   // Allocate the ODBC environment and save handle.  
   retcode = SQLAllocHandle (SQL_HANDLE_ENV, NULL, &henv);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(Env) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Notify ODBC that this is an ODBC 3.0 app.  
   retcode = SQLSetEnvAttr(henv, SQL_ATTR_ODBC_VERSION, (SQLPOINTER) SQL_OV_ODBC3, SQL_IS_INTEGER);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLSetEnvAttr(ODBC version) Failed\n\n");  
      Cleanup();  
      return(9);      
   }  
  
   // Allocate ODBC connection handle and connect.  
   retcode = SQLAllocHandle(SQL_HANDLE_DBC, henv, &hdbc1);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // sample uses Integrated Security, create SQL Server DSN using the Windows NT authentication.   
   retcode = SQLConnect(hdbc1, (UCHAR*)"AdventureWorks", SQL_NTS, (UCHAR*)"",SQL_NTS, (UCHAR*)"", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLConnect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Set options to log long-running queries, including the file to use for the log.  
   retcode = SQLSetConnectAttr( hdbc1, SQL_COPT_SS_PERF_QUERY_LOG, &"odbcqry.log", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLSetConnectAttr Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Set the long-running query interval (in milliseconds).  Note that for version 2.50 and 2.65  
   // drivers, this value is specified in seconds, not milliseconds.  
   retcode =   
      SQLSetConnectAttr( hdbc1, SQL_COPT_SS_PERF_QUERY_INTERVAL, (SQLPOINTER)3000, SQL_IS_UINTEGER);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLSetConnectAttr Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Start the long-running query log.  
   retcode =   
      SQLSetConnectAttr( hdbc1, SQL_COPT_SS_PERF_QUERY, (SQLPOINTER)SQL_PERF_START, SQL_IS_UINTEGER);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLSetConnectAttr Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Allocate statement handle then execute commands.  
   retcode = SQLAllocHandle(SQL_HANDLE_STMT, hdbc1, &hstmt1);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLAllocHandle(hstmt1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   retcode = SQLExecDirect(hstmt1, (UCHAR*)"SELECT * FROM Purchasing.Vendor", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLExecDirect Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Clear any result sets generated.  
   while ( ( retcode = SQLMoreResults(hstmt1) ) != SQL_NO_DATA ) {  
      if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
         printf("SQLMoreResults Failed\n\n");  
         Cleanup();  
           return(9);  
      }  
   }  
  
   retcode = SQLExecDirect(hstmt1, (UCHAR*)"SELECT * FROM Sales.Store", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLExecDirect Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Clear any result sets generated.  
   while ( ( retcode = SQLMoreResults(hstmt1) ) != SQL_NO_DATA ) {  
      if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
         printf("SQLMoreResults Failed\n\n");  
         Cleanup();  
         return(9);  
      }  
   }  
  
   // Generate a long-running query.  
   retcode = SQLExecDirect(hstmt1, (UCHAR*)"waitfor delay '00:00:04' ", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLExecDirect Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Clear any result sets generated.  
   while ( ( retcode = SQLMoreResults(hstmt1) ) != SQL_NO_DATA ) {  
      if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
         printf("SQLMoreResults Failed\n\n");  
         Cleanup();  
         return(9);  
      }  
   }  
  
   // Cleanup  
   SQLFreeHandle(SQL_HANDLE_STMT, hstmt1);  
   SQLDisconnect(hdbc1);  
   SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="e59cc-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="e59cc-136">See Also</span></span>  
 [<span data-ttu-id="e59cc-137">Инструкции по профилированию производительности драйвера ODBC &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="e59cc-137">Profiling ODBC Driver Performance How-to Topics &#40;ODBC&#41;</span></span>](profiling-odbc-driver-performance-odbc.md)  
  
  
