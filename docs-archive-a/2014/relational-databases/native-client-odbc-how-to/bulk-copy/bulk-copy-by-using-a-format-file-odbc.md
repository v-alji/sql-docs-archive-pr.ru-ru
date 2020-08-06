---
title: Групповое копирование с помощью файла форматирования (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- bulk copy using format file [ODBC]
- ODBC, bulk copy operations
ms.assetid: 970fd3af-f918-4fc3-a5b1-92596515d4de
author: rothja
ms.author: jroth
ms.openlocfilehash: 19959d5f1da7243275c60560963d577446f809b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750896"
---
# <a name="bulk-copy-by-using-a-format-file-odbc"></a><span data-ttu-id="e9628-102">Выполнение массового копирования при использовании файла форматирования (ODBC)</span><span class="sxs-lookup"><span data-stu-id="e9628-102">Bulk Copy by Using a Format File (ODBC)</span></span>
  <span data-ttu-id="e9628-103">В этом образце демонстрируется использование функции ODBC bcp_init с файлом форматирования.</span><span class="sxs-lookup"><span data-stu-id="e9628-103">This sample shows how to use the ODBC bcp_init function with a format file.</span></span>  
  
### <a name="to-bulk-copy-by-using-a-format-file"></a><span data-ttu-id="e9628-104">Массовое копирование с использованием файла форматирования</span><span class="sxs-lookup"><span data-stu-id="e9628-104">To bulk copy by using a format file</span></span>  
  
1.  <span data-ttu-id="e9628-105">Выделите дескриптор среды и дескриптор соединения.</span><span class="sxs-lookup"><span data-stu-id="e9628-105">Allocate an environment handle and a connection handle.</span></span>  
  
2.  <span data-ttu-id="e9628-106">Включите операцию массового копирования, укажите параметры SQL_COPT_SS_BCP и SQL_BCP_ON.</span><span class="sxs-lookup"><span data-stu-id="e9628-106">Set SQL_COPT_SS_BCP and SQL_BCP_ON to enable bulk copy operations.</span></span>  
  
3.  <span data-ttu-id="e9628-107">Подключитесь к Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e9628-107">Connect to Microsoft SQL Server.</span></span>  
  
4.  <span data-ttu-id="e9628-108">Вызовите [bcp_init](../../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) , чтобы задать следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="e9628-108">Call [bcp_init](../../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) to set the following information:</span></span>  
  
    -   <span data-ttu-id="e9628-109">Имя таблицы или представления, из которого или в которое будет производиться массовое копирование.</span><span class="sxs-lookup"><span data-stu-id="e9628-109">The name of the table or view to bulk copy from or to.</span></span>  
  
    -   <span data-ttu-id="e9628-110">Имя файла данных, в котором содержатся данные для копирования в базу данных или который получает данные при копировании из базы данных.</span><span class="sxs-lookup"><span data-stu-id="e9628-110">The name of the data file that contains the data to copy into the database or that receives data when copying from the database.</span></span>  
  
    -   <span data-ttu-id="e9628-111">Имя файла данных, в который сохраняются все сообщения об ошибках массового копирования (укажите значение NULL, если файл для сообщений не требуется).</span><span class="sxs-lookup"><span data-stu-id="e9628-111">The name of a data file to receive any bulk copy error messages (specify NULL if you do not want a message file).</span></span>  
  
    -   <span data-ttu-id="e9628-112">Направление копирования: DB_IN из файла в таблицу или представление.</span><span class="sxs-lookup"><span data-stu-id="e9628-112">The direction of the copy: DB_IN from the file to the table or view.</span></span>  
  
5.  <span data-ttu-id="e9628-113">Вызовите [bcp_readfmt](../../native-client-odbc-extensions-bulk-copy-functions/bcp-readfmt.md) , чтобы прочитать файл форматирования, описывающий файл данных, который будет использоваться операцией с массовым копированием.</span><span class="sxs-lookup"><span data-stu-id="e9628-113">Call [bcp_readfmt](../../native-client-odbc-extensions-bulk-copy-functions/bcp-readfmt.md) to read the format file describing the data file to be used by the bulk copy operation.</span></span>  
  
6.  <span data-ttu-id="e9628-114">Вызовите [bcp_exec](../../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) , чтобы выполнить операцию с массовым копированием.</span><span class="sxs-lookup"><span data-stu-id="e9628-114">Call [bcp_exec](../../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) to execute the bulk copy operation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9628-115">Пример</span><span class="sxs-lookup"><span data-stu-id="e9628-115">Example</span></span>  
 <span data-ttu-id="e9628-116">Этот образец не поддерживается на архитектуре IA64.</span><span class="sxs-lookup"><span data-stu-id="e9628-116">This sample is not supported on IA64.</span></span>  
  
 <span data-ttu-id="e9628-117">Также необходим источник данных ODBC с именем AdventureWorks, для которого базой данных по умолчанию является образец базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="e9628-117">You will need an ODBC data source called AdventureWorks, whose default database is the AdventureWorks sample database.</span></span> <span data-ttu-id="e9628-118">(Образец базы данных AdventureWorks можно скачать на домашней странице [Microsoft SQL Server примеры и проекты сообщества](https://go.microsoft.com/fwlink/?LinkID=85384) .) Этот источник данных должен быть основан на драйвере ODBC, предоставленном операционной системой (имя драйвера — "SQL Server").</span><span class="sxs-lookup"><span data-stu-id="e9628-118">(You can download the AdventureWorks sample database from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.) This data source must be based on the ODBC driver that is supplied by the operating system (the driver name is "SQL Server").</span></span> <span data-ttu-id="e9628-119">При построении и запуске этого образца как 32-разрядного приложения в 64-разрядной операционной системе необходимо создать источник данных ODBC с помощью программы администрирования ODBC (исполняемый файл %windir%\SysWOW64\odbcad32.exe).</span><span class="sxs-lookup"><span data-stu-id="e9628-119">If you will build and run this sample as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
 <span data-ttu-id="e9628-120">Этот образец соединяется с установленным на компьютер экземпляром [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e9628-120">This sample connects to your computer's default [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="e9628-121">Чтобы соединиться с именованным экземпляром, измените определение источника данных ODBC, указав экземпляр в следующем формате: Сервер\ИменованныйЭкземпляр.</span><span class="sxs-lookup"><span data-stu-id="e9628-121">To connect to a named instance, change the definition of the ODBC data source to specify the instance using the following format: server\namedinstance.</span></span> <span data-ttu-id="e9628-122">По умолчанию [!INCLUDE[ssExpress](../../../includes/ssexpress-md.md)] устанавливается на именованный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="e9628-122">By default, [!INCLUDE[ssExpress](../../../includes/ssexpress-md.md)] installs to a named instance.</span></span>  
  
 <span data-ttu-id="e9628-123">Выполните первый листинг кода ([!INCLUDE[tsql](../../../includes/tsql-md.md)]), чтобы создать таблицу, которой пользуется образец.</span><span class="sxs-lookup"><span data-stu-id="e9628-123">Execute the first ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) code listing to create the table that the sample will use.</span></span>  
  
 <span data-ttu-id="e9628-124">Скопируйте второй листинг кода и вставьте его в файл Bcpfmt.fmt.</span><span class="sxs-lookup"><span data-stu-id="e9628-124">Copy the second code listing and paste it into a file called Bcpfmt.fmt.</span></span> <span data-ttu-id="e9628-125">Каждый столбец в таблице отделен символом табуляции.</span><span class="sxs-lookup"><span data-stu-id="e9628-125">Each column in the table is separated by a tab character.</span></span>  
  
 <span data-ttu-id="e9628-126">Скопируйте третий листинг кода и вставьте его в файл Bcpodbc.bcp.</span><span class="sxs-lookup"><span data-stu-id="e9628-126">Copy the third code listing and paste it into a file called Bcpodbc.bcp.</span></span> <span data-ttu-id="e9628-127">Каждому возврату каретки в файле предшествует символ табуляции.</span><span class="sxs-lookup"><span data-stu-id="e9628-127">A tab character precedes each carriage return in the file.</span></span>  
  
 <span data-ttu-id="e9628-128">Скомпилируйте четвертый листинг кода (C++) с библиотеками odbc32.lib и odbcbcp.lib.</span><span class="sxs-lookup"><span data-stu-id="e9628-128">Compile the fourth (C++) code listing with odbc32.lib and odbcbcp.lib.</span></span> <span data-ttu-id="e9628-129">При работе с программой MSBuild.exe сначала скопируйте файлы Bcpfmt.fmt и Bcpodbc.bcp из каталога проекта в тот каталог, где находится исполняемый файл, а затем вызовите этот исполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="e9628-129">If you built with MSBuild.exe, copy Bcpfmt.fmt and Bcpodbc.bcp from the project directory into the directory with the .exe and then invoke the .exe.</span></span>  
  
 <span data-ttu-id="e9628-130">Выполните пятый листинг кода ([!INCLUDE[tsql](../../../includes/tsql-md.md)]), чтобы удалить таблицу, которую использовал образец.</span><span class="sxs-lookup"><span data-stu-id="e9628-130">Execute the fifth ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) code listing to delete the table that the sample used.</span></span>  
  
```sql
use AdventureWorks  
CREATE TABLE BCPDate (cola int, colb datetime)  
```  
  
```  
8.0  
2  
1SQLCHAR04"\t"1colaSQL_Latin1_General_Cp437_Bin  
2SQLCHAR08"\r\n"2colbSQL_Latin1_General_Cp437_Bin  
```  
  
```  
1  
2  
```  
  
```cpp
// compile with: odbc32.lib odbcbcp.lib  
#include <stdio.h>  
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
  
   // Allocate ODBC connection handle, set BCP mode, and connect.  
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
  
   // Sample uses Integrated Security. Create SQL Server DSN using Windows NT authentication.  
   retcode = SQLConnect(hdbc1, (UCHAR*)"AdventureWorks", SQL_NTS, (UCHAR*)"", SQL_NTS, (UCHAR*)"", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLConnect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Initialize the bulk copy.  
   retcode = bcp_init(hdbc1, "BCPDate", "BCPODBC.bcp", NULL, DB_IN);  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_init(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Read the format file.  
   retcode = bcp_readfmt(hdbc1, "BCPFMT.fmt");  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_readfmt(hdbc1) Failed\n\n");  
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
  
   printf("Number of rows bulk copied in = %d.\n", cRows);  
  
   // Cleanup  
   SQLDisconnect(hdbc1);  
   SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
```  
  
```sql
use AdventureWorks  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'BCPDate')  
     DROP TABLE BCPDate  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="e9628-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="e9628-131">See Also</span></span>  
 <span data-ttu-id="e9628-132">[Инструкции по групповому копированию с помощью драйвера ODBC SQL Server &#40;ODBC&#41;](bulk-copying-with-the-sql-server-odbc-driver-how-to-topics-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="e9628-132">[Bulk Copying with the SQL Server ODBC Driver How-to Topics &#40;ODBC&#41;](bulk-copying-with-the-sql-server-odbc-driver-how-to-topics-odbc.md) </span></span>  
 [<span data-ttu-id="e9628-133">Использование файлов данных и файлов форматирования</span><span class="sxs-lookup"><span data-stu-id="e9628-133">Using Data Files and Format Files</span></span>](../../native-client-odbc-bulk-copy-operations/using-data-files-and-format-files.md)  
  
  
