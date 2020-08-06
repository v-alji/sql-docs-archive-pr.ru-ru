---
title: Поддержка FILESTREAM (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- FILESTREAM [SQL Server], ODBC
- ODBC, FILESTREAM support
ms.assetid: 87982955-1542-4551-9c06-447ffe8193b9
author: rothja
ms.author: jroth
ms.openlocfilehash: e9b77a6a893c1c7c12e5fc14f23bf9fd719c689f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657073"
---
# <a name="filestream-support-odbc"></a><span data-ttu-id="09298-102">Поддержка FILESTREAM (ODBC)</span><span class="sxs-lookup"><span data-stu-id="09298-102">FILESTREAM Support (ODBC)</span></span>
  <span data-ttu-id="09298-103">Драйвер ODBC собственного клиента [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] поддерживает улучшенную функциональность FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="09298-103">ODBC in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client supports the enhanced FILESTREAM feature.</span></span> <span data-ttu-id="09298-104">Дополнительные сведения об этой функции см. в разделе [Поддержка FILESTREAM](../features/filestream-support.md).</span><span class="sxs-lookup"><span data-stu-id="09298-104">For more information about this feature, see [FILESTREAM Support](../features/filestream-support.md).</span></span> <span data-ttu-id="09298-105">Пример, демонстрирующий поддержку ODB для FILESTREAM, см. в разделе [пошаговая отправка и получение данных с помощью FILESTREAM &#40;&#41;ODBC ](../../native-client-odbc-how-to/send-and-receive-data-incrementally-with-filestream-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="09298-105">For a sample demonstrating ODB support for FILESTREAM, see [Send and Receive Data Incrementally with FILESTREAM &#40;ODBC&#41;](../../native-client-odbc-how-to/send-and-receive-data-incrementally-with-filestream-odbc.md).</span></span>  
  
 <span data-ttu-id="09298-106">Чтобы отправлять и получать `varbinary(max)` значения, превышающие 2 ГБ, приложение должно выполнить привязку параметров с помощью SQLBindParameter с параметром *ColumnSize* , для которого задано значение `SQL_SS_LENGTH_UNLIMITED` , и задать содержимое *StrLen_or_IndPtr* до `SQL_DATA_AT_EXEC` SQLExecDirect или SQLExecute.</span><span class="sxs-lookup"><span data-stu-id="09298-106">To send and receive `varbinary(max)` values greater than 2 GB, an application must bind parameters by using SQLBindParameter with *ColumnSize* set to `SQL_SS_LENGTH_UNLIMITED`, and set the contents of *StrLen_or_IndPtr* to `SQL_DATA_AT_EXEC` before SQLExecDirect or SQLExecute.</span></span>  
  
 <span data-ttu-id="09298-107">Как и в случае с любыми параметрами выполнения, данные будут предоставляться с помощью метод SQLParamData и SQLPutData.</span><span class="sxs-lookup"><span data-stu-id="09298-107">As with any data-at-execution parameter, the data will be supplied with SQLParamData and SQLPutData.</span></span>  
  
 <span data-ttu-id="09298-108">Можно вызвать SQLGetData для выборки данных в блоках для столбца FILESTREAM, если столбец не привязан к SQLBindCol.</span><span class="sxs-lookup"><span data-stu-id="09298-108">You can call SQLGetData to fetch data in chunks for a FILESTREAM column if the column is not bound with SQLBindCol.</span></span>  
  
 <span data-ttu-id="09298-109">Вы можете обновить данные FILESTREAM, если они привязаны к SQLBindCol.</span><span class="sxs-lookup"><span data-stu-id="09298-109">You can update FILESTREAM data if it is bound with SQLBindCol.</span></span>  
  
 <span data-ttu-id="09298-110">При вызове SQLFetch для привязанного столбца вы получите предупреждение "данные усекаются", если буфер недостаточно велик для хранения всего значения.</span><span class="sxs-lookup"><span data-stu-id="09298-110">If you call SQLFetch on a bound column, you will receive a "data truncated" warning if the buffer is not large enough to hold the entire value.</span></span> <span data-ttu-id="09298-111">Пропустите это предупреждение и обновите данные в этом связанном столбце с помощью вызовов метод SQLParamData и SQLPutData.</span><span class="sxs-lookup"><span data-stu-id="09298-111">Ignore this warning and update the data in this bound column with SQLParamData and SQLPutData calls.</span></span> <span data-ttu-id="09298-112">Данные FILESTREAM можно обновить с помощью функции SQLSetPos, если они привязаны к SQLBindCol.</span><span class="sxs-lookup"><span data-stu-id="09298-112">You can update FILESTREAM data by using SQLSetPos if it is bound with SQLBindCol.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09298-113">Пример</span><span class="sxs-lookup"><span data-stu-id="09298-113">Example</span></span>  
 <span data-ttu-id="09298-114">Столбцы FILESTREAM ведут себя точно так же, как столбцы `varbinary(max)`, однако, они не имеют ограничений по размерам.</span><span class="sxs-lookup"><span data-stu-id="09298-114">FILESTREAM columns behave exactly like `varbinary(max)` columns, but without a size limit.</span></span> <span data-ttu-id="09298-115">Они связываются как SQL_VARBINARY.</span><span class="sxs-lookup"><span data-stu-id="09298-115">They are bound as SQL_VARBINARY.</span></span> <span data-ttu-id="09298-116">(SQL_LONGVARBINARY используется со столбцами типа image, и на этот тип накладываются определенные ограничения.</span><span class="sxs-lookup"><span data-stu-id="09298-116">(SQL_LONGVARBINARY is used with image columns, and there are restrictions on this type.</span></span> <span data-ttu-id="09298-117">Например, SQL_LONGVARBINARY Коннот использоваться в качестве выходного параметра.) В следующих примерах показан прямой доступ NTFS к столбцам FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="09298-117">For example, SQL_LONGVARBINARY connot be used as an output parameter.) The following examples show direct NTFS access for FILESTREAM columns.</span></span> <span data-ttu-id="09298-118">Эти примеры основываются на той посылке, что следующий код [!INCLUDE[tsql](../../../includes/tsql-md.md)] был выполнен в базе данных:</span><span class="sxs-lookup"><span data-stu-id="09298-118">These examples assume that the following [!INCLUDE[tsql](../../../includes/tsql-md.md)] code has been executed in the database:</span></span>  
  
```  
CREATE TABLE fileStreamDocs(  
id uniqueidentifier ROWGUIDCOL NOT NULL UNIQUE,  
author varchar(64),  
document VARBINARY(MAX) FILESTREAM NULL)  
```  
  
### <a name="read"></a><span data-ttu-id="09298-119">Чтение</span><span class="sxs-lookup"><span data-stu-id="09298-119">Read</span></span>  
  
```  
void selectFilestream (LPCWSTR dstFilePath) {  
SQLRETURN r;  
SQLCHAR transactionToken[1024];  
SQLWCHAR srcFilePath[1024];  
SQLINTEGER cbTransactionToken, cbsrcFilePath;  
  
// The GUID columns must be visible to the query,   
// even if it is not used  
r = SQLExecDirect(hstmt, (SQLTCHAR *)   
_T("select GET_FILESTREAM_TRANSACTION_CONTEXT(); \  
select TOP(1) id, document.PathName() \  
from fileStreamDocs WHERE author = 'Chris Lee'"),   
SQL_NTS);  
if (r != SQL_SUCCESS && r!=SQL_SUCCESS_WITH_INFO) {  
ODBCError(henv, hdbc, hstmt, NULL, true); exit(-1);  
}  
  
r = SQLFetch(hstmt);  
if (r != SQL_SUCCESS && r!=SQL_SUCCESS_WITH_INFO) {  
ODBCError(henv, hdbc, hstmt, NULL, true); exit(-1);  
}  
  
r = SQLGetData(hstmt, 1, SQL_C_BINARY,   
transactionToken, sizeof(transactionToken), &cbTransactionToken);  
if (r != SQL_SUCCESS && r!=SQL_SUCCESS_WITH_INFO) {  
ODBCError(henv, hdbc, hstmt, NULL, true); exit(-1);  
}  
  
r = SQLMoreResults(hstmt);  
if (r != SQL_SUCCESS && r!=SQL_SUCCESS_WITH_INFO) {  
ODBCError(henv, hdbc, hstmt, NULL, true); exit(-1);  
}  
if (r != SQL_SUCCESS && r!=SQL_SUCCESS_WITH_INFO) {  
ODBCError(henv, hdbc, hstmt, NULL, true); exit(-1);  
}  
  
r = SQLFetch(hstmt);  
r = SQLGetData(hstmt, 2, SQL_C_TCHAR,   
srcFilePath, sizeof(srcFilePath), &cbsrcFilePath);  
if (r != SQL_SUCCESS && r!=SQL_SUCCESS_WITH_INFO) {  
ODBCError(henv, hdbc, hstmt, NULL, true); exit(-1);  
}  
  
if (!copyFileFromSql(srcFilePath, dstFilePath, transactionToken, cbTransactionToken)) {  
DeleteFile(dstFilePath);  
}  
r = SQLTransact(henv, hdbc, SQL_ROLLBACK);  
if (r != SQL_SUCCESS && r!=SQL_SUCCESS_WITH_INFO) {  
ODBCError(henv, hdbc, hstmt, NULL, true); exit(-1);  
}  
}  
```  
  
### <a name="insert"></a><span data-ttu-id="09298-120">Вставить</span><span class="sxs-lookup"><span data-stu-id="09298-120">Insert</span></span>  
  
```  
void insertFilestream(LPCWSTR srcFilePath) {  
SQLRETURN r;  
SQLCHAR transactionToken[64];  
SQLWCHAR dstFilePath[1024];  
SQLINTEGER cbTransactionToken, cbDstFilePath;  
SQLUSMALLINT mode;  
  
r = SQLExecDirect(hstmt, (SQLTCHAR *)   
_T("insert into fileStreamDocs (id, author, document)\  
    output Get_Filestream_Transaction_Context(), inserted.document.PathName() \  
        values (newid(), 'Chris Lee', convert(varbinary, '**Temp**')) "), SQL_NTS);  
if (r != SQL_SUCCESS && r!=SQL_SUCCESS_WITH_INFO) {  
ODBCError(henv, hdbc, hstmt, NULL, true); exit(-1);  
}  
  
r = SQLFetch(hstmt);  
if (r != SQL_SUCCESS && r!=SQL_SUCCESS_WITH_INFO) {  
ODBCError(henv, hdbc, hstmt, NULL, true); exit(-1);  
}  
  
r = SQLGetData(hstmt, 1, SQL_C_BINARY,  
transactionToken, sizeof(transactionToken), &cbTransactionToken);  
if (r != SQL_SUCCESS && r!=SQL_SUCCESS_WITH_INFO) {  
ODBCError(henv, hdbc, hstmt, NULL, true); exit(-1);  
}  
  
r = SQLGetData(hstmt, 2, SQL_C_TCHAR,  
dstFilePath, sizeof(dstFilePath), &cbDstFilePath);  
if (r != SQL_SUCCESS && r!=SQL_SUCCESS_WITH_INFO) {  
ODBCError(henv, hdbc, hstmt, NULL, true); exit(-1);  
}  
  
r = SQLCloseCursor(hstmt);  
if (r != SQL_SUCCESS && r!=SQL_SUCCESS_WITH_INFO) {  
ODBCError(henv, hdbc, hstmt, NULL, true); exit(-1);  
}  
  
if (copyFileToSql(  
srcFilePath, dstFilePath,   
transactionToken, cbTransactionToken)) {  
mode = SQL_COMMIT;  
}  
else {  
mode = SQL_ROLLBACK;  
}  
  
r = SQLTransact(henv, hdbc, mode);  
if (r != SQL_SUCCESS && r!=SQL_SUCCESS_WITH_INFO) {  
ODBCError(henv, hdbc, hstmt, NULL, true); exit(-1);  
}  
}  
```  
  
### <a name="helper-routines"></a><span data-ttu-id="09298-121">Вспомогательные подпрограммы</span><span class="sxs-lookup"><span data-stu-id="09298-121">Helper Routines</span></span>  
  
```  
#define COPYBUFFERSIZE 4096  
BOOL copyFileContents (HANDLE srcHandle, HANDLE dstHandle) {  
  
BYTE buffer[COPYBUFFERSIZE];  
DWORD bytesRead, bytesWritten;  
BOOL r;  
  
do {  
r = ReadFile(srcHandle, buffer, COPYBUFFERSIZE, &bytesRead,NULL);  
if (bytesRead == 0) {  
return r;  
}  
r = WriteFile(dstHandle, buffer, bytesRead, &bytesWritten, NULL);  
if (bytesWritten == 0) {  
return r;  
}  
} while (TRUE);  
}  
  
BOOL copyFileToSql(LPCWSTR srcFilePath, LPCWSTR dstFilePath, LPBYTE transactionToken, SQLINTEGER cbTransactionToken) {  
  
BOOL r;  
  
HANDLE srcHandle, dstHandle;  
unsigned int NtStatus;  
  
srcHandle =  CreateFile(  
                         srcFilePath,  
                         GENERIC_READ,  
                         FILE_SHARE_READ,  
                         NULL,  
                         OPEN_EXISTING,  
                         FILE_FLAG_SEQUENTIAL_SCAN,  
 NULL);  
  
if (srcHandle == INVALID_HANDLE_VALUE) {  
return FALSE;  
}  
  
dstHandle =  OpenSqlFilestream(  
                         dstFilePath,  
                         Write,  
                         0,  
                         transactionToken,  
                         cbTransactionToken,  
                         0);  
  
if (dstHandle == INVALID_HANDLE_VALUE) {  
NtStatus = GetLastError();  
r = CloseHandle(srcHandle);  
return FALSE;  
}  
  
//copy file  
r = copyFileContents(srcHandle, dstHandle);  
  
CloseHandle(srcHandle);  
  
CloseHandle(dstHandle);  
  
return r;  
}  
  
BOOL copyFileFromSql(LPCWSTR srcFilePath, LPCWSTR dstFilePath, LPBYTE transactionToken, SQLINTEGER cbTransactionToken) {  
  
BOOL r;  
  
HANDLE srcHandle, dstHandle;  
unsigned int NtStatus;  
  
srcHandle =  OpenSqlFilestream(  
                         srcFilePath,  
                         Read,  
                         0,  
                         transactionToken,  
                         cbTransactionToken,  
                         0);  
  
if (srcHandle == INVALID_HANDLE_VALUE) {  
return FALSE;  
}  
  
dstHandle =  CreateFile(  
                         dstFilePath,  
                         GENERIC_WRITE,  
                         0,  
                         NULL,  
                         OPEN_ALWAYS,  
                         FILE_ATTRIBUTE_NORMAL,  
 NULL);  
  
if (dstHandle == INVALID_HANDLE_VALUE) {  
CloseHandle(srcHandle);  
return FALSE;  
}  
  
r = copyFileContents(srcHandle, dstHandle);  
  
CloseHandle(srcHandle);  
  
CloseHandle(dstHandle);  
  
return r;  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="09298-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="09298-122">See Also</span></span>  
 [<span data-ttu-id="09298-123">Программирование собственного клиента SQL Server</span><span class="sxs-lookup"><span data-stu-id="09298-123">SQL Server Native Client Programming</span></span>](../sql-server-native-client-programming.md)  
  
  
