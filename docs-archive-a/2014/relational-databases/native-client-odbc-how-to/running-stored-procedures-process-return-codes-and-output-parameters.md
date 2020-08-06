---
title: Обработка кодов возврата и выходных параметров (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- return codes [ODBC]
- output parameters [ODBC]
ms.assetid: 102ae1d0-973d-4e12-992c-d844bf05160d
author: rothja
ms.author: jroth
ms.openlocfilehash: b119d43806dafa68fe049595d94e909a5a1bb896
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664147"
---
# <a name="process-return-codes-and-output-parameters-odbc"></a><span data-ttu-id="f27cc-102">Обработка кодов возврата и выходных параметров (ODBC)</span><span class="sxs-lookup"><span data-stu-id="f27cc-102">Process Return Codes and Output Parameters (ODBC)</span></span>
  <span data-ttu-id="f27cc-103">Хранимые процедуры [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] могут иметь целочисленные коды возврата и выходные параметры.</span><span class="sxs-lookup"><span data-stu-id="f27cc-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures can have integer return codes and output parameters.</span></span> <span data-ttu-id="f27cc-104">Коды возврата и выходные параметры пересылаются в последнем пакете от сервера, они не доступны приложению, пока [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) не возвратит SQL_NO_DATA.</span><span class="sxs-lookup"><span data-stu-id="f27cc-104">The return codes and output parameters are sent in the last packet from the server and are not available to the application until [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) returns SQL_NO_DATA.</span></span> <span data-ttu-id="f27cc-105">Если ошибка возвращается хранимой процедурой, вызовите SQLMoreResults, чтобы перейти к следующему результату, пока не будет возвращено SQL_NO_DATA.</span><span class="sxs-lookup"><span data-stu-id="f27cc-105">If an error is returned from a stored procedure, call SQLMoreResults to advance to the next result until SQL_NO_DATA is returned.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f27cc-106">По возможности используйте аутентификацию Windows.</span><span class="sxs-lookup"><span data-stu-id="f27cc-106">When possible, use Windows Authentication.</span></span> <span data-ttu-id="f27cc-107">Если проверка подлинности Windows недоступна, запросите у пользователя ввод учетных данных во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="f27cc-107">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="f27cc-108">Избегайте хранения учетных данных в файле.</span><span class="sxs-lookup"><span data-stu-id="f27cc-108">Avoid storing credentials in a file.</span></span> <span data-ttu-id="f27cc-109">Если необходимо сохранить учетные данные, зашифруйте их с помощью [API-интерфейса шифрования Win32](https://go.microsoft.com/fwlink/?LinkId=64532).</span><span class="sxs-lookup"><span data-stu-id="f27cc-109">If you must persist credentials, you should encrypt them with the [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532).</span></span>  
  
### <a name="to-process-return-codes-and-output-parameters"></a><span data-ttu-id="f27cc-110">Обработка кодов возврата и выходных параметров</span><span class="sxs-lookup"><span data-stu-id="f27cc-110">To process return codes and output parameters</span></span>  
  
1.  <span data-ttu-id="f27cc-111">Сконструируйте инструкцию SQL, использующую escape-последовательность ODBC CALL.</span><span class="sxs-lookup"><span data-stu-id="f27cc-111">Construct an SQL statement that uses the ODBC CALL escape sequence.</span></span> <span data-ttu-id="f27cc-112">Инструкция должна использовать маркеры параметров для каждого параметра входа, входа-выхода и выхода, а также для возвращаемого процедурой значения (если оно имеется).</span><span class="sxs-lookup"><span data-stu-id="f27cc-112">The statement should use parameter markers for each input, input/output, and output parameter, and for the procedure return value (if any).</span></span>  
  
2.  <span data-ttu-id="f27cc-113">Вызовите [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) для каждого параметра входа, входа-выхода и выхода, а также для значения, возвращаемого процедурой (если оно имеется).</span><span class="sxs-lookup"><span data-stu-id="f27cc-113">Call [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) for each input, input/output, and output parameter, and for the procedure return value (if any).</span></span>  
  
3.  <span data-ttu-id="f27cc-114">Выполните инструкцию с помощью `SQLExecDirect`.</span><span class="sxs-lookup"><span data-stu-id="f27cc-114">Execute the statement with `SQLExecDirect`.</span></span>  
  
4.  <span data-ttu-id="f27cc-115">Обрабатывайте результирующие наборы до тех пор, пока `SQLFetch` или `SQLFetchScroll` не возвратит SQL_NO_DATA при обработке последнего результирующего набора или до тех пор, пока `SQLMoreResults` не возвратит SQL_NO_DATA.</span><span class="sxs-lookup"><span data-stu-id="f27cc-115">Process result sets until `SQLFetch` or `SQLFetchScroll` returns SQL_NO_DATA while processing the last result set or until `SQLMoreResults` returns SQL_NO_DATA.</span></span> <span data-ttu-id="f27cc-116">На этот момент переменные, привязанные к коду возврата, а также выходные параметры заполнены возвращенными значениями данных.</span><span class="sxs-lookup"><span data-stu-id="f27cc-116">At this point, the variables bound to the return code and output parameters are filled with returned data values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f27cc-117">Пример</span><span class="sxs-lookup"><span data-stu-id="f27cc-117">Example</span></span>  
 <span data-ttu-id="f27cc-118">В данном образце демонстрируется обработка кода возврата и выходного параметра.</span><span class="sxs-lookup"><span data-stu-id="f27cc-118">This sample shows processing a return code and output parameter.</span></span> <span data-ttu-id="f27cc-119">Этот образец не поддерживается на архитектуре IA64.</span><span class="sxs-lookup"><span data-stu-id="f27cc-119">This sample is not supported on IA64.</span></span> <span data-ttu-id="f27cc-120">Этот образец разработан для ODBC версии 3.0 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="f27cc-120">This sample was developed for ODBC version 3.0 or later.</span></span>  
  
 <span data-ttu-id="f27cc-121">Также необходим источник данных ODBC с именем AdventureWorks, для которого базой данных по умолчанию является образец базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="f27cc-121">You will need an ODBC data source called AdventureWorks, whose default database is the AdventureWorks sample database.</span></span> <span data-ttu-id="f27cc-122">(Образец базы данных AdventureWorks можно скачать на домашней странице [Microsoft SQL Server примеры и проекты сообщества](https://go.microsoft.com/fwlink/?LinkID=85384) .) Этот источник данных должен быть основан на драйвере ODBC, предоставленном операционной системой (имя драйвера — "SQL Server").</span><span class="sxs-lookup"><span data-stu-id="f27cc-122">(You can download the AdventureWorks sample database from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.) This data source must be based on the ODBC driver that is supplied by the operating system (the driver name is "SQL Server").</span></span> <span data-ttu-id="f27cc-123">При построении и запуске этого образца как 32-разрядного приложения в 64-разрядной операционной системе необходимо создать источник данных ODBC с помощью программы администрирования ODBC (исполняемый файл %windir%\SysWOW64\odbcad32.exe).</span><span class="sxs-lookup"><span data-stu-id="f27cc-123">If you will build and run this sample as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
 <span data-ttu-id="f27cc-124">Этот образец соединяется с установленным на компьютер экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f27cc-124">This sample connects to your computer's default [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="f27cc-125">Чтобы соединиться с именованным экземпляром, измените определение источника данных ODBC, указав экземпляр в следующем формате: Сервер\ИменованныйЭкземпляр.</span><span class="sxs-lookup"><span data-stu-id="f27cc-125">To connect to a named instance, change the definition of the ODBC data source to specify the instance using the following format: server\namedinstance.</span></span> <span data-ttu-id="f27cc-126">По умолчанию [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] устанавливается на именованный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="f27cc-126">By default, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] installs to a named instance.</span></span>  
  
 <span data-ttu-id="f27cc-127">Первый листинг кода ([!INCLUDE[tsql](../../includes/tsql-md.md)]) создает хранимую процедуру, которая используется данным образцом.</span><span class="sxs-lookup"><span data-stu-id="f27cc-127">The first ([!INCLUDE[tsql](../../includes/tsql-md.md)]) code listing creates a stored procedure used by this sample.</span></span>  
  
 <span data-ttu-id="f27cc-128">Скомпилируйте второй листинг кода (C++) с библиотекой odbc32.lib.</span><span class="sxs-lookup"><span data-stu-id="f27cc-128">Compile the second (C++) code listing with odbc32.lib.</span></span> <span data-ttu-id="f27cc-129">Затем запустите программу.</span><span class="sxs-lookup"><span data-stu-id="f27cc-129">Then, execute the program.</span></span>  
  
 <span data-ttu-id="f27cc-130">Третий листинг кода ([!INCLUDE[tsql](../../includes/tsql-md.md)]) удаляет хранимую процедуру, используемую данным образцом.</span><span class="sxs-lookup"><span data-stu-id="f27cc-130">The third ([!INCLUDE[tsql](../../includes/tsql-md.md)]) code listing deletes the stored procedure used by this sample.</span></span>  
  
```  
use AdventureWorks  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'TestParm')  
   DROP PROCEDURE TestParm  
GO  
  
CREATE PROCEDURE TestParm   
@OutParm int OUTPUT   
AS  
SELECT Name FROM Purchasing.Vendor  
SELECT @OutParm = 88  
RETURN 99  
go  
```  
  
```  
// compile with: odbc32.lib  
#include <stdio.h>  
#include <string.h>  
#include <windows.h>  
#include <sql.h>  
#include <sqlext.h>  
#include <odbcss.h>  
  
#define MAXBUFLEN 255  
  
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
   // SQLBindParameter variables.  
   SWORD sParm1 = 0, sParm2 = 1;  
   SQLLEN cbParm1 = SQL_NTS;  
   SQLLEN cbParm2 = SQL_NTS;  
  
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
  
   // This sample use Integrated Security. Create the SQL Server DSN by using the Windows NT authentication.   
   retcode = SQLConnect(hdbc1, (UCHAR*)"AdventureWorks", SQL_NTS, (UCHAR*)"",SQL_NTS, (UCHAR*)"", SQL_NTS);  
  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLConnect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Allocate statement handle.  
   retcode = SQLAllocHandle(SQL_HANDLE_STMT, hdbc1, &hstmt1);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLAllocHandle(hstmt1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Bind the return code to variable sParm1.  
   retcode = SQLBindParameter(hstmt1, 1, SQL_PARAM_OUTPUT, SQL_C_SSHORT, SQL_INTEGER, 0, 0, &sParm1, 0, &cbParm1);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLBindParameter(sParm1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Bind the output parameter to variable sParm2.  
   retcode = SQLBindParameter(hstmt1, 2, SQL_PARAM_OUTPUT, SQL_C_SSHORT, SQL_INTEGER, 0, 0, &sParm2, 0, &cbParm2);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLBindParameter(sParm2) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Execute the command.   
   retcode = SQLExecDirect(hstmt1, (UCHAR*)"{? = call TestParm(?)}", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLExecDirect Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Show parameters are not filled.  
   printf("Before result sets cleared: RetCode = %d, OutParm = %d.\n", sParm1, sParm2);  
  
   // Clear any result sets generated.  
   while ( ( retcode = SQLMoreResults(hstmt1) ) != SQL_NO_DATA )  
      ;  
  
   // Show parameters are now filled.  
   printf("After result sets drained: RetCode = %d, OutParm = %d.\n", sParm1, sParm2);  
  
   // Clean up.   
   SQLFreeHandle(SQL_HANDLE_STMT, hstmt1);  
   SQLDisconnect(hdbc1);  
   SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
```  
  
```  
use AdventureWorks  
DROP PROCEDURE TestParm  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="f27cc-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="f27cc-131">See Also</span></span>  
 [<span data-ttu-id="f27cc-132">Разделы руководства по выполнению хранимых процедур &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="f27cc-132">Running Stored Procedures How-to Topics &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/running-stored-procedures-how-to-topics-odbc.md)  
  
  
