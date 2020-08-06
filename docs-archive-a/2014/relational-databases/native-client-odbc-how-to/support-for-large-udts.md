---
title: Поддержка больших определяемых пользователем типов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 621b6d13-10f1-47d0-b63c-7adb6ab904e0
author: rothja
ms.author: jroth
ms.openlocfilehash: d5ba9ce9d11afcd1af6789b8ee559aa617d6d635
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664144"
---
# <a name="support-for-large-udts"></a><span data-ttu-id="06173-102">Поддержка больших, определяемых пользователем типов</span><span class="sxs-lookup"><span data-stu-id="06173-102">Support for Large UDTs</span></span>
  <span data-ttu-id="06173-103">В этом образце решения содержатся два проекта.</span><span class="sxs-lookup"><span data-stu-id="06173-103">This sample solution contains two projects.</span></span> <span data-ttu-id="06173-104">Один проект создает сборку (библиотеку DLL) из исходного кода на C#.</span><span class="sxs-lookup"><span data-stu-id="06173-104">One project creates an assembly (DLL) from C# source code.</span></span> <span data-ttu-id="06173-105">Эта сборка содержит тип CLR.</span><span class="sxs-lookup"><span data-stu-id="06173-105">This assembly contains the CLR type.</span></span> <span data-ttu-id="06173-106">В базу данных будет добавлена таблица.</span><span class="sxs-lookup"><span data-stu-id="06173-106">A table will be added to the database.</span></span> <span data-ttu-id="06173-107">Столбец в этой таблице будет иметь тип, определенный в сборке. По умолчанию в этом образце используется база данных master.</span><span class="sxs-lookup"><span data-stu-id="06173-107">A column in the table will be of a type defined in the assembly, By default, this sample will use the master database.</span></span> <span data-ttu-id="06173-108">Второй проект является собственным приложением C, которое считывает данные из таблицы.</span><span class="sxs-lookup"><span data-stu-id="06173-108">The second project is a native C application that reads data from the table.</span></span>  
  
 <span data-ttu-id="06173-109">С версиями [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , вышедшими до [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], образец работать не будет.</span><span class="sxs-lookup"><span data-stu-id="06173-109">This sample will not work with any version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] earlier than [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
 <span data-ttu-id="06173-110">Дополнительные сведения о поддержке больших определяемых пользователем типов см. в разделе [большие определяемые пользователем типы данных CLR &#40;&#41;ODBC ](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="06173-110">For more information about support for large UDTs, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="06173-111">Пример</span><span class="sxs-lookup"><span data-stu-id="06173-111">Example</span></span>  
 <span data-ttu-id="06173-112">Первым листингом кода является исходный код на C#.</span><span class="sxs-lookup"><span data-stu-id="06173-112">The first code listing is C# source code.</span></span> <span data-ttu-id="06173-113">Вставьте его в файл LargeStringUDT.cs и скомпилируйте его в DLL-библиотеку.</span><span class="sxs-lookup"><span data-stu-id="06173-113">Paste it into a file called LargeStringUDT.cs and compile it to a DLL.</span></span> <span data-ttu-id="06173-114">Скопируйте файл LargeStringUDT.dll в корневой каталог диска C.</span><span class="sxs-lookup"><span data-stu-id="06173-114">Copy LargeStringUDT.dll to the root directory of your C drive.</span></span>  
  
 <span data-ttu-id="06173-115">Второй листинг кода ([!INCLUDE[tsql](../../includes/tsql-md.md)]) создает сборку в базе данных master.</span><span class="sxs-lookup"><span data-stu-id="06173-115">The second ([!INCLUDE[tsql](../../includes/tsql-md.md)]) code listing creates the assembly in the master database.</span></span>  
  
 <span data-ttu-id="06173-116">Скомпилируйте второй листинг кода (C++) с библиотеками odbc32.lib и user32.lib.</span><span class="sxs-lookup"><span data-stu-id="06173-116">Compile the second (C++) code listing with odbc32.lib and user32.lib.</span></span> <span data-ttu-id="06173-117">Убедитесь, что переменная среды INCLUDE включает каталог, содержащий файл sqlncli.h.</span><span class="sxs-lookup"><span data-stu-id="06173-117">Make sure your INCLUDE environment variable includes the directory that contains sqlncli.h.</span></span>  
  
 <span data-ttu-id="06173-118">При построении и запуске этого образца как 32-разрядного приложения в 64-разрядной операционной системе необходимо создать источник данных ODBC с помощью программы администрирования ODBC (исполняемый файл %windir%\SysWOW64\odbcad32.exe).</span><span class="sxs-lookup"><span data-stu-id="06173-118">If you will build and run this sample as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
 <span data-ttu-id="06173-119">Этот образец соединяется с установленным на компьютер экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="06173-119">This sample connects to your computer's default [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="06173-120">Чтобы соединиться с именованным экземпляром, измените определение источника данных ODBC, указав экземпляр в следующем формате: Сервер\ИменованныйЭкземпляр.</span><span class="sxs-lookup"><span data-stu-id="06173-120">To connect to a named instance, change the definition of the ODBC data source to specify the instance using the following format: server\namedinstance.</span></span> <span data-ttu-id="06173-121">По умолчанию [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] устанавливается на именованный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="06173-121">By default, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] installs to a named instance.</span></span>  
  
 <span data-ttu-id="06173-122">Четвертый листинг кода ([!INCLUDE[tsql](../../includes/tsql-md.md)]) удаляет сборку из базы данных master.</span><span class="sxs-lookup"><span data-stu-id="06173-122">The fourth ([!INCLUDE[tsql](../../includes/tsql-md.md)]) code listing deletes the assembly from the master database.</span></span>  
  
```  
// LargeStringUDT.cs  
// compile with: /target:library  
using System;  
using System.Data;  
using System.Data.SqlTypes;  
using Microsoft.SqlServer.Server;  
using System.Text;  
  
[assembly: System.CLSCompliantAttribute(true)]  
[Serializable]  
[Microsoft.SqlServer.Server.SqlUserDefinedType(Format.UserDefined, IsFixedLength = false, MaxByteSize = -1, IsByteOrdered = true)]  
public class LargeStringUDT : INullable, IBinarySerialize {  
    private bool _isNull;  
    private string _largeString;  
  
    public bool IsNull {  
        get {  
            return (_isNull);  
        }  
    }  
  
    public static LargeStringUDT Null {  
        get {  
            LargeStringUDT lsUDT = new LargeStringUDT();  
            lsUDT._isNull = true;  
            return lsUDT;  
        }  
    }  
  
    public override string ToString() {  
        if (IsNull)  
            return "NULL";  
        else  
            return _largeString;  
    }  
  
    [SqlMethod(OnNullCall = false)]  
    public static LargeStringUDT Parse(SqlString s) {  
        if (s.IsNull)  
            return Null;  
  
        LargeStringUDT lsUDT = new LargeStringUDT();  
        lsUDT._largeString = s.Value;  
        return lsUDT;  
    }  
  
    public String LargeString {  
        get {  
            return _largeString;  
        }  
  
        set {  
            _largeString = value;  
        }  
    }  
  
    public void Read(System.IO.BinaryReader r) {  
        _isNull = r.ReadBoolean();  
        if (!_isNull)  
            _largeString = new String(r.ReadChars(r.ReadInt32()));  
    }  
  
    public void Write(System.IO.BinaryWriter w) {  
        w.Write(_isNull);  
        if (!_isNull) {  
            w.Write(_largeString.Length);  
            for (int i = 0; i < _largeString.Length; ++i)  
                w.Write(_largeString[i]);  
        }  
    }  
}  
```  
  
```  
USE [MASTER]  
IF EXISTS (SELECT * FROM sys.objects WHERE name = 'LargeStringUDTs')  
   DROP TABLE LargeStringUDTs  
GO  
  
IF EXISTS (SELECT * FROM sys.types WHERE name = 'LargeStringUDT')  
   DROP TYPE dbo.LargeStringUDT  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE name = 'LargeStringUDT')  
   DROP ASSEMBLY LargeStringUDT  
GO  
  
CREATE ASSEMBLY LargeStringUDT  
FROM 'C:\LargeStringUDT.dll'  
WITh PERMISSION_SET=SAFE;  
GO  
  
CREATE TYPE dbo.LargeStringUDT   
EXTERNAL NAME LargeStringUDT.[LargeStringUDT];  
GO  
  
CREATE TABLE dbo.LargeStringUDTs  
(ID int IDENTITY(1,1) PRIMARY KEY, LargeString LargeStringUDT)  
GO  
  
INSERT INTO dbo.LargeStringUDTs (LargeString) VALUES (CONVERT(LargeStringUDT, 'This is the first string'));  
INSERT INTO dbo.LargeStringUDTs (LargeString) VALUES (CONVERT(LargeStringUDT, 'This is the second string'));  
INSERT INTO dbo.LargeStringUDTs (LargeString) VALUES (Convert(LargeStringUDT, 'This is the third string'));  
GO  
```  
  
```  
// compile with: odbc32.lib  
#include <stdio.h>  
#include <tchar.h>  
#include <stddef.h>  
#include <windows.h>  
#define ODBCVER 0x0350  
#include <sql.h>  
#include <sqlext.h>  
#include <sqltypes.h>  
#define _SQLNCLI_ODBC  
#include "sqlncli.h"  
  
int main() {  
   // The command to execute.  
   SQLTCHAR* szCmdString = (SQLTCHAR *)_T("SELECT ID, LargeString FROM dbo.LargeStringUDTs");  
  
   int ret = 0;  
   SQLRETURN rc;  
   SQLHENV hEnv = NULL;  
   SQLHDBC hDbc = NULL;  
   SQLHSTMT hStmt = NULL;  
   SQLTCHAR szConn[256];   
   BYTE DataBuf[15];  
   SQLSMALLINT iLen = 0;  
   SQLLEN iDataLen = 0;  
  
   rc = SQLAllocHandle(SQL_HANDLE_ENV, SQL_NULL_HANDLE, &hEnv);  
   if (rc != SQL_SUCCESS) {  
      printf("Failed to get HENV\n");  
      return -1;  
   }  
  
   rc = SQLSetEnvAttr (hEnv, SQL_ATTR_ODBC_VERSION, (SQLPOINTER)SQL_OV_ODBC3, 0);  
   if (rc != SQL_SUCCESS) {  
      printf("Failed to SetEnvAttr\n");  
      SQLFreeHandle(SQL_HANDLE_ENV, hEnv);  
      return -1;  
   }  
  
   rc = SQLAllocHandle(SQL_HANDLE_DBC, hEnv, &hDbc);  
   if (rc != SQL_SUCCESS) {  
      printf("Failed to get HDBC\n");  
      SQLFreeHandle(SQL_HANDLE_ENV, hEnv);  
      return -1;  
   }  
  
   rc = SQLDriverConnect(hDbc, NULL,   
      (SQLTCHAR *)_T("DRIVER={SQL Server Native Client 10.0};SERVER=(local);Trusted_Connection=Yes;database=master"),   
      SQL_NTS, szConn, 255, &iLen, SQL_DRIVER_NOPROMPT);  
   if (rc != SQL_SUCCESS && rc != SQL_SUCCESS_WITH_INFO) {  
      printf("Failed to connect\n");  
      ret = -1;  
      goto End;  
   }  
  
   rc = SQLAllocHandle(SQL_HANDLE_STMT, hDbc, &hStmt);  
   if (rc != SQL_SUCCESS) {  
      printf("Failed to get hstmt\n");  
      ret = -1;  
      goto End;  
   }  
  
   // Execute the command.  
   rc = SQLExecDirect(hStmt, szCmdString, SQL_NTS);  
   if (rc != SQL_SUCCESS) {  
      printf("Failed to get hstmt\n");  
      ret = -1;  
      goto End;  
   }  
  
   // Process the result set.  
   SQLSMALLINT paramType;  
   SQLTCHAR szData[100], szData2[100];  
   SQLSMALLINT NameLengthPtr = 0, DataTypePtr, DecimalDigitsPtr, NullablePtr;  
   SQLULEN ColumnSizePtr[2];  
   rc = SQLDescribeCol(hStmt, 1, szData, sizeof(szData), &NameLengthPtr, &DataTypePtr, &ColumnSizePtr[0], &DecimalDigitsPtr, &NullablePtr);  
   _tprintf(_T("%s"), szData);  
   rc = SQLDescribeCol(hStmt, 2, szData2, sizeof(szData2), &NameLengthPtr, &DataTypePtr, &ColumnSizePtr[1], &DecimalDigitsPtr, &NullablePtr);  
   _tprintf(_T("          %s\n"), szData2);  
  
   while ( ( rc = SQLFetch(hStmt ) ) == SQL_SUCCESS ) {  
      rc = SQLGetData(hStmt, 1, SQL_C_SHORT, &paramType, sizeof(SQL_C_SHORT), NULL);  
      printf("%d           ", paramType);  
  
      bool ifFirst = true;  
      while ( ( rc = SQLGetData(hStmt, 2 , SQL_C_BINARY, DataBuf, sizeof(DataBuf) ,&iDataLen ) ) != SQL_NO_DATA) {  
         // process number of bytes in the DataBuf;  
         int NumBytes = (iDataLen > sizeof(DataBuf)) || (iDataLen == SQL_NO_TOTAL) ? sizeof(DataBuf): iDataLen;  
         for ( int i = ifFirst?5:0 ; i <NumBytes ; i++ )  
            putchar((char)DataBuf[i]);  
         ifFirst = false;  
      };  
      printf("\n");  
   }  
  
   if ( rc != SQL_NO_DATA ) {  
      printf("Failed to fetch data\n");  
      ret= -1;  
   }  
  
End:  
   if (hStmt) {  
      SQLFreeStmt(hStmt,SQL_CLOSE);  
      SQLFreeStmt(hStmt,SQL_DROP);  
   }  
  
   if (hDbc) {  
      SQLDisconnect(hDbc);  
      SQLFreeConnect(hDbc);  
   }  
  
   if (hEnv)  
      SQLFreeHandle(SQL_HANDLE_ENV, hEnv);  
};  
```  
  
```  
USE [MASTER]  
IF EXISTS (SELECT * FROM sys.objects WHERE name = 'LargeStringUDTs')  
   DROP TABLE LargeStringUDTs  
GO  
  
IF EXISTS (SELECT * FROM sys.types WHERE name = 'LargeStringUDT')  
   DROP TYPE dbo.LargeStringUDT  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE name = 'LargeStringUDT')  
   DROP ASSEMBLY LargeStringUDT  
GO  
```  
  
  
