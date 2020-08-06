---
title: Создание файла форматирования для копирования (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- bulk copy [ODBC], file formats
- bulk copy [ODBC], data files
ms.assetid: 0572fef3-daf5-409e-b557-c2a632f9a06d
author: rothja
ms.author: jroth
ms.openlocfilehash: 9d35342b2f6b25a129df968383d204931d64bfa5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655140"
---
# <a name="create-a-bulk-copy-format-file-odbc"></a><span data-ttu-id="56a31-102">Создание файла форматирования массового копирования (ODBC)</span><span class="sxs-lookup"><span data-stu-id="56a31-102">Create a Bulk Copy Format File (ODBC)</span></span>
  <span data-ttu-id="56a31-103">В этом образце показано использование функций массового копирования для создания как файла данных, так и файла форматирования.</span><span class="sxs-lookup"><span data-stu-id="56a31-103">This sample shows how to use bulk copy functions to create both a data file and a format file.</span></span> <span data-ttu-id="56a31-104">Этот образец разработан для ODBC версии 3.0 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="56a31-104">This sample was developed for ODBC version 3.0 or later.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="56a31-105">По возможности используйте аутентификацию Windows.</span><span class="sxs-lookup"><span data-stu-id="56a31-105">When possible, use Windows Authentication.</span></span> <span data-ttu-id="56a31-106">Если проверка подлинности Windows недоступна, запросите у пользователя ввод учетных данных во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="56a31-106">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="56a31-107">Избегайте хранения учетных данных в файле.</span><span class="sxs-lookup"><span data-stu-id="56a31-107">Avoid storing credentials in a file.</span></span> <span data-ttu-id="56a31-108">Если необходимо сохранить учетные данные, зашифруйте их с помощью [API-интерфейса шифрования Win32](https://go.microsoft.com/fwlink/?LinkId=64532).</span><span class="sxs-lookup"><span data-stu-id="56a31-108">If you must persist credentials, you should encrypt them with the [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532).</span></span>  
  
### <a name="to-create-a-bulk-copy-format-file"></a><span data-ttu-id="56a31-109">Создание файла формата массового копирования</span><span class="sxs-lookup"><span data-stu-id="56a31-109">To create a bulk copy format file</span></span>  
  
1.  <span data-ttu-id="56a31-110">Выделите дескриптор среды и дескриптор соединения.</span><span class="sxs-lookup"><span data-stu-id="56a31-110">Allocate an environment handle and a connection handle.</span></span>  
  
2.  <span data-ttu-id="56a31-111">Включите операцию массового копирования, укажите параметры SQL_COPT_SS_BCP и SQL_BCP_ON.</span><span class="sxs-lookup"><span data-stu-id="56a31-111">Set SQL_COPT_SS_BCP and SQL_BCP_ON to enable bulk copy operations.</span></span>  
  
3.  <span data-ttu-id="56a31-112">Соединитесь с SQL Server.</span><span class="sxs-lookup"><span data-stu-id="56a31-112">Connect to SQL Server.</span></span>  
  
4.  <span data-ttu-id="56a31-113">Вызовите [bcp_init](../../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) , чтобы задать следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="56a31-113">Call [bcp_init](../../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) to set the following information:</span></span>  
  
    -   <span data-ttu-id="56a31-114">Имя таблицы или представления, из которого или в которое будет производиться массовое копирование.</span><span class="sxs-lookup"><span data-stu-id="56a31-114">The name of the table or view to bulk copy from or to.</span></span>  
  
    -   <span data-ttu-id="56a31-115">Имя файла данных, в котором содержатся данные для копирования в базу данных или который получает данные при копировании из базы данных.</span><span class="sxs-lookup"><span data-stu-id="56a31-115">The name of the data file that contains the data to copy into the database or that receives data when copying from the database.</span></span>  
  
    -   <span data-ttu-id="56a31-116">Имя файла данных, в который сохраняются все сообщения об ошибках массового копирования (укажите значение NULL, если файл для сообщений не требуется).</span><span class="sxs-lookup"><span data-stu-id="56a31-116">The name of a data file to receive any bulk copy error messages (specify NULL if you do not want a message file).</span></span>  
  
    -   <span data-ttu-id="56a31-117">Направление копирования: DB_OUT в файл из таблицы или представления.</span><span class="sxs-lookup"><span data-stu-id="56a31-117">The direction of the copy: DB_OUT to the file from the table or view.</span></span>  
  
5.  <span data-ttu-id="56a31-118">Вызовите [bcp_columns](../../native-client-odbc-extensions-bulk-copy-functions/bcp-columns.md) , чтобы задать число столбцов.</span><span class="sxs-lookup"><span data-stu-id="56a31-118">Call [bcp_columns](../../native-client-odbc-extensions-bulk-copy-functions/bcp-columns.md) to set the number of columns.</span></span>  
  
6.  <span data-ttu-id="56a31-119">Вызовите [bcp_colfmt](../../native-client-odbc-extensions-bulk-copy-functions/bcp-colfmt.md) для каждого столбца, чтобы определить его характеристики в файле данных.</span><span class="sxs-lookup"><span data-stu-id="56a31-119">Call [bcp_colfmt](../../native-client-odbc-extensions-bulk-copy-functions/bcp-colfmt.md) for each column to define its characteristics in the data file.</span></span>  
  
7.  <span data-ttu-id="56a31-120">Вызовите [bcp_writefmt](../../native-client-odbc-extensions-bulk-copy-functions/bcp-writefmt.md) , чтобы создать файл форматирования, описывающий файл данных, который будет создан операцией при выполнении операции с массовым копированием.</span><span class="sxs-lookup"><span data-stu-id="56a31-120">Call [bcp_writefmt](../../native-client-odbc-extensions-bulk-copy-functions/bcp-writefmt.md) to create a format file describing the data file to be created by the bulk copy operation.</span></span>  
  
8.  <span data-ttu-id="56a31-121">Вызовите [bcp_exec](../../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) , чтобы выполнить операцию с массовым копированием.</span><span class="sxs-lookup"><span data-stu-id="56a31-121">Call [bcp_exec](../../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) to execute the bulk copy operation.</span></span>  
  
 <span data-ttu-id="56a31-122">Операция копирования, которая выполняется этим способом, создает как файл данных, содержащий данные массового копирования, так и файл форматирования, описывающий макет файла данных.</span><span class="sxs-lookup"><span data-stu-id="56a31-122">A bulk copy operation run in this way creates both a data file containing the bulk copied data and a format file describing the layout of the data file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="56a31-123">Пример</span><span class="sxs-lookup"><span data-stu-id="56a31-123">Example</span></span>  
 <span data-ttu-id="56a31-124">Также необходим источник данных ODBC с именем AdventureWorks, для которого базой данных по умолчанию является образец базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="56a31-124">You will need an ODBC data source called AdventureWorks, whose default database is the AdventureWorks sample database.</span></span> <span data-ttu-id="56a31-125">(Образец базы данных AdventureWorks можно скачать на домашней странице [Microsoft SQL Server примеры и проекты сообщества](https://go.microsoft.com/fwlink/?LinkID=85384) .) Этот источник данных должен быть основан на драйвере ODBC, предоставленном операционной системой (имя драйвера — "SQL Server").</span><span class="sxs-lookup"><span data-stu-id="56a31-125">(You can download the AdventureWorks sample database from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.) This data source must be based on the ODBC driver that is supplied by the operating system (the driver name is "SQL Server").</span></span> <span data-ttu-id="56a31-126">При построении и запуске этого образца как 32-разрядного приложения в 64-разрядной операционной системе необходимо создать источник данных ODBC с помощью программы администрирования ODBC (исполняемый файл %windir%\SysWOW64\odbcad32.exe).</span><span class="sxs-lookup"><span data-stu-id="56a31-126">If you will build and run this sample as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
 <span data-ttu-id="56a31-127">Этот образец соединяется с установленным на компьютер экземпляром [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="56a31-127">This sample connects to your computer's default [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="56a31-128">Чтобы соединиться с именованным экземпляром, измените определение источника данных ODBC, указав экземпляр в следующем формате: Сервер\ИменованныйЭкземпляр.</span><span class="sxs-lookup"><span data-stu-id="56a31-128">To connect to a named instance, change the definition of the ODBC data source to specify the instance using the following format: server\namedinstance.</span></span> <span data-ttu-id="56a31-129">По умолчанию [!INCLUDE[ssExpress](../../../includes/ssexpress-md.md)] устанавливается на именованный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="56a31-129">By default, [!INCLUDE[ssExpress](../../../includes/ssexpress-md.md)] installs to a named instance.</span></span>  
  
 <span data-ttu-id="56a31-130">Выполните первый листинг кода ([!INCLUDE[tsql](../../../includes/tsql-md.md)]), чтобы создать таблицу, которой пользуется образец.</span><span class="sxs-lookup"><span data-stu-id="56a31-130">Execute the first ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) code listing to create the table that the sample will use.</span></span>  
  
 <span data-ttu-id="56a31-131">Скомпилируйте второй листинг кода (C++) с библиотеками odbc32.lib и odbcbcp.lib.</span><span class="sxs-lookup"><span data-stu-id="56a31-131">Compile the second (C++) code listing with odbc32.lib and odbcbcp.lib.</span></span>  
  
 <span data-ttu-id="56a31-132">Выполните третий листинг кода ([!INCLUDE[tsql](../../../includes/tsql-md.md)]), чтобы удалить таблицу, которую использовал образец.</span><span class="sxs-lookup"><span data-stu-id="56a31-132">Execute the third ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) code listing to delete the table that the sample used.</span></span>  
  
```  
use AdventureWorks  
  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'BCPDate')  
     DROP TABLE BCPDate  
GO  
  
CREATE TABLE BCPDate (cola int, colb datetime)  
insert BCPDate(cola) values(1)   
insert BCPDate(cola) values(2)   
insert BCPDate(cola) values(3)   
insert BCPDate(cola) values(4)  
```  
  
```  
// compile with: odbc32.lib odbcbcp.lib  
#include <stdio.h>  
#include <string.h>  
#include <windows.h>  
#include <sql.h>  
#include <sqlext.h>  
#include <odbcss.h>  
  
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
  
   // BCP variables.  
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
  
   // Allocate ODBC connection handle, set bulk copy mode, and connect.  
   retcode = SQLAllocHandle(SQL_HANDLE_DBC, henv, &hdbc1);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   retcode = SQLSetConnectAttr(hdbc1, SQL_COPT_SS_BCP, (void *)SQL_BCP_ON, SQL_IS_INTEGER);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLSetEnvAttr(ODBC version) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Sample uses Integrated Security, create SQL Server DSN using Windows NT authentication.   
   retcode = SQLConnect(hdbc1, (UCHAR*)"AdventureWorks", SQL_NTS, (UCHAR*)"",SQL_NTS, (UCHAR*)"", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLConnect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Initialize the bulk copy.  
   retcode = bcp_init(hdbc1, "BCPDate", "BCPODBC.bcp", NULL, DB_OUT);  
   if (retcode != SUCCEED) {  
      printf("bcp_init() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Set the number of output columns.  
   retcode = bcp_columns(hdbc1, 2);  
   if (retcode != SUCCEED) {  
      printf("bcp_init() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Describe the format of column 1 in the data file.  
   retcode = bcp_colfmt(hdbc1, 1, SQLCHARACTER, -1, 5, NULL, 0, 1);  
   if (retcode != SUCCEED) {  
      printf("bcp_init() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Describe the format of column 2 in the data file.  
   retcode = bcp_colfmt(hdbc1, 2, SQLCHARACTER, -1, 20, NULL, 0, 2);  
   if (retcode != SUCCEED) {  
      printf("bcp_init() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Create the format file.  
   retcode = bcp_writefmt(hdbc1, "c:\\BCPFMT.fmt");  
   if (retcode != SUCCEED) {  
      printf("bcp_init() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Execute the bulk copy.  
   retcode = bcp_exec(hdbc1, &cRows);  
   if (retcode != SUCCEED) {  
      printf("bcp_init() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   printf("Number of rows bulk copied out = %d.\n", cRows);  
  
   // Cleanup  
   SQLDisconnect(hdbc1);  
   SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   SQLFreeHandle(SQL_HANDLE_ENV, henv);  
   return(0);  
}  
```  
  
```  
use AdventureWorks  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'BCPDate')  
     DROP TABLE BCPDate  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="56a31-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="56a31-133">See Also</span></span>  
 <span data-ttu-id="56a31-134">[Инструкции по групповому копированию с помощью драйвера ODBC SQL Server &#40;ODBC&#41;](bulk-copying-with-the-sql-server-odbc-driver-how-to-topics-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="56a31-134">[Bulk Copying with the SQL Server ODBC Driver How-to Topics &#40;ODBC&#41;](bulk-copying-with-the-sql-server-odbc-driver-how-to-topics-odbc.md) </span></span>  
 [<span data-ttu-id="56a31-135">Использование файлов данных и файлов форматирования</span><span class="sxs-lookup"><span data-stu-id="56a31-135">Using Data Files and Format Files</span></span>](../../native-client-odbc-bulk-copy-operations/using-data-files-and-format-files.md)  
  
  
