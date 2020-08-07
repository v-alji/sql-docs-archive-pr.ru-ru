---
title: Данные производительности драйвера профиля (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- driver performance data [ODBC]
ms.assetid: b997790a-8cc6-4800-8867-74c1bef07be3
author: rothja
ms.author: jroth
ms.openlocfilehash: 3575cfd304d526bdb25eee6a2578d67c6bb67bc9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730649"
---
# <a name="profile-driver-performance-data-odbc"></a><span data-ttu-id="b2331-102">Сбор сведений о производительности драйвера (ODBC)</span><span class="sxs-lookup"><span data-stu-id="b2331-102">Profile Driver Performance Data (ODBC)</span></span>
  <span data-ttu-id="b2331-103">В этом образце показаны параметры [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для драйвера ODBC, относящиеся к сбору статистики производительности.</span><span class="sxs-lookup"><span data-stu-id="b2331-103">This sample shows the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ODBC driver-specific options to record performance statistics.</span></span> <span data-ttu-id="b2331-104">Образец создает один файл: odbcperf.log. Этот образец показывает и создание файла журнала со сведениями о производительности, и отображение сведений о производительности непосредственно из структуры данных SQLPERF (структура SQLPERF определена в файле Odbcss.h.).</span><span class="sxs-lookup"><span data-stu-id="b2331-104">The sample creates one file: odbcperf.log.This sample shows both the creation of a performance data log file and displaying performance data directly from the SQLPERF data structure (The SQLPERF structure is defined in Odbcss.h.).</span></span> <span data-ttu-id="b2331-105">Этот образец разработан для ODBC версии 3.0 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="b2331-105">This sample was developed for ODBC version 3.0 or later.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b2331-106">По возможности используйте аутентификацию Windows.</span><span class="sxs-lookup"><span data-stu-id="b2331-106">When possible, use Windows Authentication.</span></span> <span data-ttu-id="b2331-107">Если проверка подлинности Windows недоступна, запросите у пользователя ввод учетных данных во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="b2331-107">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="b2331-108">Избегайте хранения учетных данных в файле.</span><span class="sxs-lookup"><span data-stu-id="b2331-108">Avoid storing credentials in a file.</span></span> <span data-ttu-id="b2331-109">Если необходимо сохранить учетные данные, зашифруйте их с помощью [API-интерфейса шифрования Win32](https://go.microsoft.com/fwlink/?LinkId=64532).</span><span class="sxs-lookup"><span data-stu-id="b2331-109">If you must persist credentials, you should encrypt them with the [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532).</span></span>  
  
### <a name="to-log-driver-performance-data-using-odbc-administrator"></a><span data-ttu-id="b2331-110">Запись сведений о производительности драйвера при помощи администратора ODBC</span><span class="sxs-lookup"><span data-stu-id="b2331-110">To log driver performance data using ODBC Administrator</span></span>  
  
1.  <span data-ttu-id="b2331-111">На **панели управления**дважды щелкните **Администрирование** , а затем дважды щелкните **Источники данных (ODBC)**.</span><span class="sxs-lookup"><span data-stu-id="b2331-111">In **Control Panel**, double-click **Administrative Tools** and then double-click **Data Sources (ODBC)**.</span></span> <span data-ttu-id="b2331-112">Можно также вызвать программу odbcad32.exe.</span><span class="sxs-lookup"><span data-stu-id="b2331-112">Alternatively, you can invoke odbcad32.exe.</span></span>  
  
2.  <span data-ttu-id="b2331-113">Щелкните вкладку **DSN пользователя**, **системное имя DSN**или **Файловый DSN** .</span><span class="sxs-lookup"><span data-stu-id="b2331-113">Click the **User DSN**, **System DSN**, or **File DSN** tab.</span></span>  
  
3.  <span data-ttu-id="b2331-114">Щелкните источник данных, для которого необходимо заносить в журнал производительность.</span><span class="sxs-lookup"><span data-stu-id="b2331-114">Click the data source for which to log performance.</span></span>  
  
4.  <span data-ttu-id="b2331-115">Щелкните **Настройка**.</span><span class="sxs-lookup"><span data-stu-id="b2331-115">Click **Configure**.</span></span>  
  
5.  <span data-ttu-id="b2331-116">В мастере настройки имени DSN Microsoft SQL Server перейдите к странице с **записью статистики драйвера ODBC log в файл журнала**.</span><span class="sxs-lookup"><span data-stu-id="b2331-116">In the Microsoft SQL Server Configure DSN Wizard, navigate to the page with **Log ODBC driver statistics to the log file**.</span></span>  
  
6.  <span data-ttu-id="b2331-117">Выберите **Журнал статистика драйвера ODBC в файле журнала**.</span><span class="sxs-lookup"><span data-stu-id="b2331-117">Select **Log ODBC driver statistics to the log file**.</span></span> <span data-ttu-id="b2331-118">В поле укажите имя файла, куда будет записана статистика.</span><span class="sxs-lookup"><span data-stu-id="b2331-118">In the box, place the name of the file where the statistics should be logged.</span></span> <span data-ttu-id="b2331-119">При необходимости нажмите кнопку **Обзор** , чтобы просмотреть файловую систему для журнала статистики.</span><span class="sxs-lookup"><span data-stu-id="b2331-119">Optionally, click **Browse** to browse the file system for the statistics log.</span></span>  
  
### <a name="to-log-driver-performance-data-programmatically"></a><span data-ttu-id="b2331-120">Программная запись сведений о производительности драйвера</span><span class="sxs-lookup"><span data-stu-id="b2331-120">To log driver performance data programmatically</span></span>  
  
1.  <span data-ttu-id="b2331-121">Вызовите [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) с SQL_COPT_SS_PERF_DATA_LOG, а также полный путь и имя файла журнала данных производительности.</span><span class="sxs-lookup"><span data-stu-id="b2331-121">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_PERF_DATA_LOG and the full path and file name of the performance data log file.</span></span> <span data-ttu-id="b2331-122">Пример:</span><span class="sxs-lookup"><span data-stu-id="b2331-122">For example:</span></span>  
  
    ```  
    "C:\\Odbcperf.log"  
    ```  
  
2.  <span data-ttu-id="b2331-123">Вызовите [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) с SQL_COPT_SS_PERF_DATA и SQL_PERF_START, чтобы начать запись данных о производительности.</span><span class="sxs-lookup"><span data-stu-id="b2331-123">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_PERF_DATA and SQL_PERF_START to start logging performance data.</span></span>  
  
3.  <span data-ttu-id="b2331-124">При необходимости вызовите [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) с SQL_COPT_SS_LOG_NOW и NULL, чтобы записать в файл журнала данных производительности записи с разделителями-символами табуляции.</span><span class="sxs-lookup"><span data-stu-id="b2331-124">Optionally, call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_LOG_NOW and NULL to write a tab-delimited record of performance data to the performance data log file.</span></span> <span data-ttu-id="b2331-125">Это можно делать каждый раз при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="b2331-125">This can be done multiple times as the application runs.</span></span>  
  
4.  <span data-ttu-id="b2331-126">Вызовите [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) с SQL_COPT_SS_PERF_DATA и SQL_PERF_STOP, чтобы отключить ведение журнала данных о производительности.</span><span class="sxs-lookup"><span data-stu-id="b2331-126">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_PERF_DATA and SQL_PERF_STOP to stop logging performance data.</span></span>  
  
### <a name="to-pull-driver-performance-data-into-an-application"></a><span data-ttu-id="b2331-127">Получение в приложение данных о производительности</span><span class="sxs-lookup"><span data-stu-id="b2331-127">To pull driver performance data into an application</span></span>  
  
1.  <span data-ttu-id="b2331-128">Вызовите [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) с SQL_COPT_SS_PERF_DATA и SQL_PERF_START, чтобы начать профилирование данных производительности.</span><span class="sxs-lookup"><span data-stu-id="b2331-128">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_PERF_DATA and SQL_PERF_START to start profiling performance data.</span></span>  
  
2.  <span data-ttu-id="b2331-129">Вызовите [SQLGetConnectAttr](../native-client-odbc-api/sqlgetconnectattr.md) с SQL_COPT_SS_PERF_DATA и адресом указателя на структуру SQLPERF.</span><span class="sxs-lookup"><span data-stu-id="b2331-129">Call [SQLGetConnectAttr](../native-client-odbc-api/sqlgetconnectattr.md) with SQL_COPT_SS_PERF_DATA and the address of a pointer to a SQLPERF structure.</span></span> <span data-ttu-id="b2331-130">Первый такой вызов установит указатель на адрес допустимой структуры SQLPERF, содержащей текущие сведения о производительности.</span><span class="sxs-lookup"><span data-stu-id="b2331-130">The first such call sets the pointer to the address of a valid SQLPERF structure that contains current performance data.</span></span> <span data-ttu-id="b2331-131">Драйвер не обновляет непрерывно данные в структуре производительности.</span><span class="sxs-lookup"><span data-stu-id="b2331-131">The driver does not continually refresh the data in the performance structure.</span></span> <span data-ttu-id="b2331-132">Приложение должно повторить вызов [SQLGetConnectAttr](../native-client-odbc-api/sqlgetconnectattr.md) каждый раз, когда ему потребуется обновить структуру с более актуальными данными о производительности.</span><span class="sxs-lookup"><span data-stu-id="b2331-132">The application must repeat the call to [SQLGetConnectAttr](../native-client-odbc-api/sqlgetconnectattr.md) any time it needs to refresh the structure with more current performance data.</span></span>  
  
3.  <span data-ttu-id="b2331-133">Вызовите [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) с SQL_COPT_SS_PERF_DATA и SQL_PERF_STOP, чтобы отключить ведение журнала данных о производительности.</span><span class="sxs-lookup"><span data-stu-id="b2331-133">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_PERF_DATA and SQL_PERF_STOP to stop logging performance data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2331-134">Пример</span><span class="sxs-lookup"><span data-stu-id="b2331-134">Example</span></span>  
 <span data-ttu-id="b2331-135">Также необходим источник данных ODBC с именем AdventureWorks, для которого базой данных по умолчанию является образец базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="b2331-135">You will need an ODBC data source called AdventureWorks, whose default database is the AdventureWorks sample database.</span></span> <span data-ttu-id="b2331-136">(Образец базы данных AdventureWorks можно скачать на домашней странице [Microsoft SQL Server примеры и проекты сообщества](https://go.microsoft.com/fwlink/?LinkID=85384) .) Этот источник данных должен быть основан на драйвере ODBC, предоставленном операционной системой (имя драйвера — "SQL Server").</span><span class="sxs-lookup"><span data-stu-id="b2331-136">(You can download the AdventureWorks sample database from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.) This data source must be based on the ODBC driver that is supplied by the operating system (the driver name is "SQL Server").</span></span> <span data-ttu-id="b2331-137">При построении и запуске этого образца как 32-разрядного приложения в 64-разрядной операционной системе необходимо создать источник данных ODBC с помощью программы администрирования ODBC (исполняемый файл %windir%\SysWOW64\odbcad32.exe).</span><span class="sxs-lookup"><span data-stu-id="b2331-137">If you will build and run this sample as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
 <span data-ttu-id="b2331-138">Этот образец соединяется с установленным на компьютер экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b2331-138">This sample connects to your computer's default [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="b2331-139">Чтобы соединиться с именованным экземпляром, измените определение источника данных ODBC, указав экземпляр в следующем формате: Сервер\ИменованныйЭкземпляр.</span><span class="sxs-lookup"><span data-stu-id="b2331-139">To connect to a named instance, change the definition of the ODBC data source to specify the instance using the following format: server\namedinstance.</span></span> <span data-ttu-id="b2331-140">По умолчанию [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] устанавливается на именованный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="b2331-140">By default, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] installs to a named instance.</span></span>  
  
 <span data-ttu-id="b2331-141">Скомпилируйте с библиотекой odbc32.lib.</span><span class="sxs-lookup"><span data-stu-id="b2331-141">Compile with odbc32.lib.</span></span>  
  
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
  
   // Pointer to the ODBC driver performance structure.  
   SQLPERF *PerfPtr;  
   SQLINTEGER cbPerfPtr;  
  
   // Allocate the ODBC environment and save handle.  
   retcode = SQLAllocHandle (SQL_HANDLE_ENV, NULL, &henv);  
   if( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(Env) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Notify ODBC that this is an ODBC 3.0 app.  
   retcode = SQLSetEnvAttr(henv, SQL_ATTR_ODBC_VERSION, (SQLPOINTER) SQL_OV_ODBC3, SQL_IS_INTEGER);  
   if( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLSetEnvAttr(ODBC version) Failed\n\n");  
      Cleanup();  
      return(9);      
   }  
  
   // Allocate ODBC connection handle and connect.  
   retcode = SQLAllocHandle(SQL_HANDLE_DBC, henv, &hdbc1);  
   if( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // This sample use Integrated Security. Please create the SQL Server   
   // DSN by using the Windows NT authentication.   
   retcode = SQLConnect(hdbc1, (UCHAR*)"AdventureWorks", SQL_NTS, (UCHAR*)"", SQL_NTS, (UCHAR*)"", SQL_NTS);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLConnect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Set options to log performance statistics.  Specify file to use for the log.  
   retcode = SQLSetConnectAttr( hdbc1, SQL_COPT_SS_PERF_DATA_LOG, &"odbcperf.log", SQL_NTS);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLSetConnectAttr() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Start the performance statistics log.  
   retcode =   
      SQLSetConnectAttr( hdbc1, SQL_COPT_SS_PERF_DATA, (SQLPOINTER)SQL_PERF_START, SQL_IS_UINTEGER);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLSetConnectAttr() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Allocate statement handle, then execute command.  
   retcode = SQLAllocHandle(SQL_HANDLE_STMT, hdbc1, &hstmt1);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLAllocHandle() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   retcode = SQLExecDirect(hstmt1, (UCHAR*)"SELECT * FROM Purchasing.Vendor", SQL_NTS);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLExecDirect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Clear any result sets generated.  
   while ( ( retcode = SQLMoreResults(hstmt1) ) != SQL_NO_DATA ) {  
      if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
         printf("SQLMoreResults() Failed\n\n");  
         Cleanup();  
         return(9);  
      }  
   }  
  
   retcode = SQLExecDirect(hstmt1, (UCHAR*)"SELECT * FROM Sales.Store", SQL_NTS);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLExecDirect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Clear any result sets generated.  
   while ( ( retcode = SQLMoreResults(hstmt1) ) != SQL_NO_DATA ) {  
      if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
         printf("SQLMoreResults() Failed\n\n");  
         Cleanup();  
         return(9);  
      }  
   }  
  
   // Generate a long-running query.  
   retcode = SQLExecDirect(hstmt1, (UCHAR*)"waitfor delay '00:00:04' ", SQL_NTS);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLExecDirect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Clear any result sets generated.  
   while ( ( retcode = SQLMoreResults(hstmt1) ) != SQL_NO_DATA ) {  
      if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
         printf("SQLMoreResults() Failed\n\n");  
         Cleanup();  
         return(9);  
      }  
   }  
  
   // Write current statistics to the performance log.  
   retcode =   
      SQLSetConnectAttr( hdbc1, SQL_COPT_SS_PERF_DATA_LOG_NOW, (SQLPOINTER)NULL, SQL_IS_UINTEGER);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLSetConnectAttr() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Get pointer to current SQLPerf structure.  
   // Print a couple of statistics.  
   retcode =   
      SQLGetConnectAttr( hdbc1, SQL_COPT_SS_PERF_DATA, (SQLPOINTER)&PerfPtr, SQL_IS_POINTER, &cbPerfPtr);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLGetConnectAttr() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   printf("SQLSelects = %d, SQLSelectRows = %d\n", PerfPtr->SQLSelects, PerfPtr->SQLSelectRows);  
  
   // Cleanup  
   SQLFreeHandle(SQL_HANDLE_STMT, hstmt1);  
   SQLDisconnect(hdbc1);  
   SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="b2331-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="b2331-142">See Also</span></span>  
 <span data-ttu-id="b2331-143">[Инструкции по профилированию производительности драйвера ODBC &#40;ODBC&#41;](profiling-odbc-driver-performance-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="b2331-143">[Profiling ODBC Driver Performance How-to Topics &#40;ODBC&#41;](profiling-odbc-driver-performance-odbc.md) </span></span>  
 [<span data-ttu-id="b2331-144">Создание профилей производительности драйвера ODBC</span><span class="sxs-lookup"><span data-stu-id="b2331-144">Profiling ODBC Driver Performance</span></span>](../native-client/odbc/profiling-odbc-driver-performance.md)  
  
  
