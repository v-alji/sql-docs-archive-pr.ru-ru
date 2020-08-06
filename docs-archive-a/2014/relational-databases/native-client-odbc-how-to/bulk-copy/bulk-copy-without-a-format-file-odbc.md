---
title: Групповое копирование без файла форматирования (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- bulk copy [ODBC], file formats
- bulk copy [ODBC]
- bulk copy [ODBC], data files
- bulk copy [ODBC], about bulk copy
ms.assetid: 4ee969a7-44ba-40d0-b9ab-8306f1a2b19d
author: rothja
ms.author: jroth
ms.openlocfilehash: a65f013d92f5a5d39a580cfb3a9bd77bc6f84e9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750887"
---
# <a name="bulk-copy-without-a-format-file-odbc"></a><span data-ttu-id="8a5d3-102">Выполнение массового копирования без файла форматирования (ODBC)</span><span class="sxs-lookup"><span data-stu-id="8a5d3-102">Bulk Copy Without a Format File (ODBC)</span></span>
  <span data-ttu-id="8a5d3-103">В этом образце показывается, как использовать функции массового копирования без файла форматирования для создания файла данных в собственном режиме.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-103">This sample shows how to use bulk copy functions to create a native mode data file, without a format file.</span></span> <span data-ttu-id="8a5d3-104">Этот образец разработан для ODBC версии 3.0 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-104">This sample was developed for ODBC version 3.0 or later.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8a5d3-105">По возможности используйте аутентификацию Windows.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-105">When possible, use Windows Authentication.</span></span> <span data-ttu-id="8a5d3-106">Если проверка подлинности Windows недоступна, запросите у пользователя ввод учетных данных во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-106">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="8a5d3-107">Избегайте хранения учетных данных в файле.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-107">Avoid storing credentials in a file.</span></span> <span data-ttu-id="8a5d3-108">Если необходимо сохранить учетные данные, зашифруйте их с помощью [API-интерфейса шифрования Win32](https://go.microsoft.com/fwlink/?LinkId=64532).</span><span class="sxs-lookup"><span data-stu-id="8a5d3-108">If you must persist credentials, you should encrypt them with the [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532).</span></span>  
  
### <a name="to-bulk-copy-without-a-format-file"></a><span data-ttu-id="8a5d3-109">Массовое копирование без файла форматирования</span><span class="sxs-lookup"><span data-stu-id="8a5d3-109">To bulk copy without a format file</span></span>  
  
1.  <span data-ttu-id="8a5d3-110">Выделите дескриптор среды и дескриптор соединения.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-110">Allocate an environment handle and a connection handle.</span></span>  
  
2.  <span data-ttu-id="8a5d3-111">Включите операцию массового копирования, укажите параметры SQL_COPT_SS_BCP и SQL_BCP_ON.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-111">Set SQL_COPT_SS_BCP and SQL_BCP_ON to enable bulk copy operations.</span></span>  
  
3.  <span data-ttu-id="8a5d3-112">Соединитесь с SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-112">Connect to SQL Server.</span></span>  
  
4.  <span data-ttu-id="8a5d3-113">Вызовите [bcp_init](../../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) , чтобы задать следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="8a5d3-113">Call [bcp_init](../../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) to set the following information:</span></span>  
  
    -   <span data-ttu-id="8a5d3-114">Имя таблицы или представления, из которого или в которое будет производиться массовое копирование.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-114">The name of the table or view to bulk copy from or to.</span></span>  
  
    -   <span data-ttu-id="8a5d3-115">Имя файла данных, в котором содержатся данные для копирования в базу данных или который получает данные при копировании из базы данных.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-115">The name of the data file that contains the data to copy into the database or that receives data when copying from the database.</span></span>  
  
    -   <span data-ttu-id="8a5d3-116">Имя файла данных, в который сохраняются все сообщения об ошибках массового копирования (укажите значение NULL, если файл для сообщений не требуется).</span><span class="sxs-lookup"><span data-stu-id="8a5d3-116">The name of a data file to receive any bulk copy error messages (specify NULL if you do not want a message file).</span></span>  
  
    -   <span data-ttu-id="8a5d3-117">Направление копирования: DB_IN из файла в представление или таблицу или DB_OUT в файл из таблицы или представления.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-117">The direction of the copy: DB_IN from the file to the view or table, or DB_OUT to the file from the table or view.</span></span>  
  
5.  <span data-ttu-id="8a5d3-118">Вызовите [bcp_exec](../../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) , чтобы выполнить операцию с массовым копированием.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-118">Call [bcp_exec](../../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) to execute the bulk copy operation.</span></span>  
  
 <span data-ttu-id="8a5d3-119">Если при выполнении этих шагов установлено значение DB_OUT, файл создается в собственном формате.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-119">When DB_OUT is set with these steps, the file is created in native format.</span></span> <span data-ttu-id="8a5d3-120">Затем файл можно с помощью операции массового копирования скопировать на сервер, выполнив те же шаги, за исключением того, что необходимо установить значение DB_OUT вместо DB_IN.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-120">The file can then be bulk copied into a server by following these same steps, except that DB_OUT is set instead of DB_IN.</span></span> <span data-ttu-id="8a5d3-121">Это возможно только в случае, когда структура исходной и целевой таблиц идентична.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-121">This works only if both the source and target tables have exactly the same structure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a5d3-122">Пример</span><span class="sxs-lookup"><span data-stu-id="8a5d3-122">Example</span></span>  
 <span data-ttu-id="8a5d3-123">Этот образец не поддерживается на архитектуре IA64.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-123">This sample is not supported on IA64.</span></span>  
  
 <span data-ttu-id="8a5d3-124">Также необходим источник данных ODBC с именем AdventureWorks, для которого базой данных по умолчанию является образец базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-124">You will need an ODBC data source called AdventureWorks, whose default database is the AdventureWorks sample database.</span></span> <span data-ttu-id="8a5d3-125">(Образец базы данных AdventureWorks можно скачать на домашней странице [Microsoft SQL Server примеры и проекты сообщества](https://go.microsoft.com/fwlink/?LinkID=85384) .) Этот источник данных должен быть основан на драйвере ODBC, предоставленном операционной системой (имя драйвера — "SQL Server").</span><span class="sxs-lookup"><span data-stu-id="8a5d3-125">(You can download the AdventureWorks sample database from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.) This data source must be based on the ODBC driver that is supplied by the operating system (the driver name is "SQL Server").</span></span> <span data-ttu-id="8a5d3-126">При построении и запуске этого образца как 32-разрядного приложения в 64-разрядной операционной системе необходимо создать источник данных ODBC с помощью программы администрирования ODBC (исполняемый файл %windir%\SysWOW64\odbcad32.exe).</span><span class="sxs-lookup"><span data-stu-id="8a5d3-126">If you will build and run this sample as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
 <span data-ttu-id="8a5d3-127">Этот образец соединяется с установленным на компьютер экземпляром [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-127">This sample connects to your computer's default [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="8a5d3-128">Чтобы соединиться с именованным экземпляром, измените определение источника данных ODBC, указав экземпляр в следующем формате: Сервер\ИменованныйЭкземпляр.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-128">To connect to a named instance, change the definition of the ODBC data source to specify the instance using the following format: server\namedinstance.</span></span> <span data-ttu-id="8a5d3-129">По умолчанию [!INCLUDE[ssExpress](../../../includes/ssexpress-md.md)] устанавливается на именованный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-129">By default, [!INCLUDE[ssExpress](../../../includes/ssexpress-md.md)] installs to a named instance.</span></span>  
  
 <span data-ttu-id="8a5d3-130">Скомпилируйте с библиотеками odbc32.lib и odbcbcp.lib.</span><span class="sxs-lookup"><span data-stu-id="8a5d3-130">Compile with odbc32.lib and odbcbcp.lib.</span></span>  
  
```  
// compile with: odbc32.lib odbcbcp.lib  
#include <stdio.h>  
#include <string.h>  
#include <windows.h>  
#include <sql.h>  
#include <sqlext.h>  
#include <odbcss.h>  
  
#define MAXBUFLEN 256  
  
SQLHENV henv = SQL_NULL_HENV;  
HDBC hdbc1 = SQL_NULL_HDBC;  
  
void Cleanup() {  
   if (hdbc1 != SQL_NULL_HDBC) {  
      SQLDisconnect(hdbc1);  
      SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   }  
  
   if (henv != SQL_NULL_HENV)  
      SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
  
int main() {  
   RETCODE retcode;  
  
   // Bulk copy variables.  
   SDWORD cRows;  
  
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
  
   // Allocate ODBC connection handle, set bulk copy mode, and then connect.  
   retcode = SQLAllocHandle(SQL_HANDLE_DBC, henv, &hdbc1);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   retcode = SQLSetConnectAttr(hdbc1, SQL_COPT_SS_BCP, (void *)SQL_BCP_ON, SQL_IS_INTEGER);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLSetConnectAttr(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Sample uses Integrated Security, create the SQL Server DSN using Windows NT authentication.   
   retcode = SQLConnect(hdbc1, (UCHAR*)"AdventureWorks", SQL_NTS, (UCHAR*)"", SQL_NTS, (UCHAR*)"", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLConnect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Initialize the bulk copy.  
   retcode = bcp_init(hdbc1, "Purchasing.Vendor", "BCPODBC.bcp", "BCPERROR.out", DB_OUT);  
   // Test is for the bulk copy return of SUCCEED, not the ODBC return of SQL_SUCCESS.  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_init(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Execute the bulk copy.  
   retcode = bcp_exec(hdbc1, &cRows);  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_exec(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   printf("Number of rows bulk copied out = %d.\n", cRows);  
  
   // Cleanup  
   SQLDisconnect(hdbc1);  
   SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="8a5d3-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="8a5d3-131">See Also</span></span>  
 [<span data-ttu-id="8a5d3-132">Инструкции по групповому копированию с помощью драйвера ODBC SQL Server &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="8a5d3-132">Bulk Copying with the SQL Server ODBC Driver How-to Topics &#40;ODBC&#41;</span></span>](bulk-copying-with-the-sql-server-odbc-driver-how-to-topics-odbc.md)  
  
  
