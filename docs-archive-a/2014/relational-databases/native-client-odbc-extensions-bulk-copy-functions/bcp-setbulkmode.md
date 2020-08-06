---
title: bcp_setbulkmode | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- bcp_setbulkmode function
ms.assetid: de56f206-1f7e-4c03-bf22-da9c7f9f4433
author: rothja
ms.author: jroth
ms.openlocfilehash: 1b7a68dfb3c868422b2e01cccf511a623d3afe52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665319"
---
# <a name="bcp_setbulkmode"></a><span data-ttu-id="0e1ca-102">bcp_setbulkmode</span><span class="sxs-lookup"><span data-stu-id="0e1ca-102">bcp_setbulkmode</span></span>
  <span data-ttu-id="0e1ca-103">bcp_setbulkmode позволяет указать формат столбца в операции массового копирования, устанавливая все атрибуты столбца в одном вызове функции.</span><span class="sxs-lookup"><span data-stu-id="0e1ca-103">bcp_setbulkmode lets you specify the column format in a bulk copy operation, setting all the column attributes in a single function call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e1ca-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0e1ca-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_setbulkmode (  
   HDBC   
hdbc  
,  
   INT   
property  
,  
   void *   
pField  
,  
   INT   
cbField  
,  
   void *   
pRow  
,  
   INT   
cbRow  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="0e1ca-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="0e1ca-105">Arguments</span></span>  
 <span data-ttu-id="0e1ca-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="0e1ca-106">*hdbc*</span></span>  
 <span data-ttu-id="0e1ca-107">Дескриптор соединения ODBC с поддержкой массового копирования.</span><span class="sxs-lookup"><span data-stu-id="0e1ca-107">The bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="0e1ca-108">*property*</span><span class="sxs-lookup"><span data-stu-id="0e1ca-108">*property*</span></span>  
 <span data-ttu-id="0e1ca-109">Константа типа BYTE.</span><span class="sxs-lookup"><span data-stu-id="0e1ca-109">A constant of type BYTE.</span></span> <span data-ttu-id="0e1ca-110">Список констант см. в таблице в подразделе «Примечания».</span><span class="sxs-lookup"><span data-stu-id="0e1ca-110">See the table in the Remarks section for a list of the constants.</span></span>  
  
 <span data-ttu-id="0e1ca-111">*pField*</span><span class="sxs-lookup"><span data-stu-id="0e1ca-111">*pField*</span></span>  
 <span data-ttu-id="0e1ca-112">Указатель на значение признака конца поля.</span><span class="sxs-lookup"><span data-stu-id="0e1ca-112">The pointer to the field terminator value.</span></span>  
  
 <span data-ttu-id="0e1ca-113">*cbField*</span><span class="sxs-lookup"><span data-stu-id="0e1ca-113">*cbField*</span></span>  
 <span data-ttu-id="0e1ca-114">Длина в байтах значения признака конца поля.</span><span class="sxs-lookup"><span data-stu-id="0e1ca-114">The length (in bytes) of the field terminator value.</span></span>  
  
 <span data-ttu-id="0e1ca-115">*pRow*</span><span class="sxs-lookup"><span data-stu-id="0e1ca-115">*pRow*</span></span>  
 <span data-ttu-id="0e1ca-116">Указатель на значение признака конца строки.</span><span class="sxs-lookup"><span data-stu-id="0e1ca-116">The pointer to the row terminator value.</span></span>  
  
 <span data-ttu-id="0e1ca-117">*cbRow*</span><span class="sxs-lookup"><span data-stu-id="0e1ca-117">*cbRow*</span></span>  
 <span data-ttu-id="0e1ca-118">Длина в байтах значения признака конца строки.</span><span class="sxs-lookup"><span data-stu-id="0e1ca-118">The length in bytes of the row terminator value.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="0e1ca-119">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0e1ca-119">Returns</span></span>  
 <span data-ttu-id="0e1ca-120">SUCCEED или FAIL</span><span class="sxs-lookup"><span data-stu-id="0e1ca-120">SUCCEED or FAIL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e1ca-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="0e1ca-121">Remarks</span></span>  
 <span data-ttu-id="0e1ca-122">bcp_setbulkmode можно использовать для выполнения полного копирования из запроса или таблицы.</span><span class="sxs-lookup"><span data-stu-id="0e1ca-122">bcp_setbulkmode can be used to bulk copy out of either a query or a table.</span></span> <span data-ttu-id="0e1ca-123">Если bcp_setbulkmode используется для выполнения операций с массовым копированием инструкции запроса, он должен быть вызван перед вызовом bcp_control с BCP_HINT.</span><span class="sxs-lookup"><span data-stu-id="0e1ca-123">When bcp_setbulkmode is used to bulk copy out a query statement, it must be called before calling bcp_control with BCP_HINT.</span></span>  
  
 <span data-ttu-id="0e1ca-124">bcp_setbulkmode является альтернативой использованию [bcp_setcolfmt](bcp-setcolfmt.md) и [bcp_columns](bcp-columns.md), который позволяет задавать только формат одного столбца для каждого вызова функции.</span><span class="sxs-lookup"><span data-stu-id="0e1ca-124">bcp_setbulkmode is an alternative to using [bcp_setcolfmt](bcp-setcolfmt.md) and [bcp_columns](bcp-columns.md), which only let you specify the format of one column per function call.</span></span>  
  
 <span data-ttu-id="0e1ca-125">В следующей таблице перечислены константы для параметра *property* .</span><span class="sxs-lookup"><span data-stu-id="0e1ca-125">The following table lists the constants for the *property* parameter.</span></span>  
  
|<span data-ttu-id="0e1ca-126">Свойство</span><span class="sxs-lookup"><span data-stu-id="0e1ca-126">Property</span></span>|<span data-ttu-id="0e1ca-127">Описание</span><span class="sxs-lookup"><span data-stu-id="0e1ca-127">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="0e1ca-128">BCP_OUT_CHARACTER_MODE</span><span class="sxs-lookup"><span data-stu-id="0e1ca-128">BCP_OUT_CHARACTER_MODE</span></span>|<span data-ttu-id="0e1ca-129">Указывает символьный режим вывода.</span><span class="sxs-lookup"><span data-stu-id="0e1ca-129">Specifies character output mode.</span></span><br /><br /> <span data-ttu-id="0e1ca-130">Соответствует параметру-c в BCP.EXE и для bcp_setcolfmt со `BCP_FMT_TYPE` свойством, для которого задано значение `SQLCHARACTER` .</span><span class="sxs-lookup"><span data-stu-id="0e1ca-130">Corresponds to the -c option in BCP.EXE, and to bcp_setcolfmt with `BCP_FMT_TYPE` property set to `SQLCHARACTER`.</span></span>|  
|<span data-ttu-id="0e1ca-131">BCP_OUT_WIDE_CHARACTER_MODE</span><span class="sxs-lookup"><span data-stu-id="0e1ca-131">BCP_OUT_WIDE_CHARACTER_MODE</span></span>|<span data-ttu-id="0e1ca-132">Указывает режим вывода в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="0e1ca-132">Specifies Unicode output mode.</span></span><br /><br /> <span data-ttu-id="0e1ca-133">Соответствует параметру-w в BCP.EXE и bcp_setcolfmt со `BCP_FMT_TYPE` свойством, для которого задано значение `SQLNCHAR` .</span><span class="sxs-lookup"><span data-stu-id="0e1ca-133">Corresponds to the -w option in BCP.EXE and bcp_setcolfmt with `BCP_FMT_TYPE` property set to `SQLNCHAR`.</span></span>|  
|<span data-ttu-id="0e1ca-134">BCP_OUT_NATIVE_TEXT_MODE</span><span class="sxs-lookup"><span data-stu-id="0e1ca-134">BCP_OUT_NATIVE_TEXT_MODE</span></span>|<span data-ttu-id="0e1ca-135">Указывает собственные типы для несимвольных типов и Юникод для символьных типов.</span><span class="sxs-lookup"><span data-stu-id="0e1ca-135">Specifies native types for non-character types and Unicode for character types.</span></span><br /><br /> <span data-ttu-id="0e1ca-136">Соответствует параметру-N в BCP.EXE и bcp_setcolfmt свойство со `BCP_FMT_TYPE` значением, `SQLNCHAR` Если тип столбца является строкой (по умолчанию, если строка не является строкой).</span><span class="sxs-lookup"><span data-stu-id="0e1ca-136">Corresponds to the -N option in BCP.EXE and bcp_setcolfmt with `BCP_FMT_TYPE` property set to `SQLNCHAR` if the column type is a string (default if not a string).</span></span>|  
|<span data-ttu-id="0e1ca-137">BCP_OUT_NATIVE_MODE</span><span class="sxs-lookup"><span data-stu-id="0e1ca-137">BCP_OUT_NATIVE_MODE</span></span>|<span data-ttu-id="0e1ca-138">Указывает типы данных базы данных.</span><span class="sxs-lookup"><span data-stu-id="0e1ca-138">Specifies native database types.</span></span><br /><br /> <span data-ttu-id="0e1ca-139">Соответствует параметру-n в BCP.EXE и bcp_setcolfmt `BCP_FMT_TYPE` свойству задано значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0e1ca-139">Corresponds to the -n option in BCP.EXE and bcp_setcolfmt with `BCP_FMT_TYPE` property set to the default.</span></span>|  
  
 <span data-ttu-id="0e1ca-140">Не следует использовать bcp_setbulkmode с последовательностью вызовов функций, включающих bcp_setcolfmt, bcp_control и bcp_readfmt.</span><span class="sxs-lookup"><span data-stu-id="0e1ca-140">You should not use bcp_setbulkmode with a sequence of function calls that includes bcp_setcolfmt, bcp_control, and bcp_readfmt.</span></span> <span data-ttu-id="0e1ca-141">Например, не следует вызывать bcp_control (БКПТЕКСТФИЛЕ) и bcp_setbulkmode.</span><span class="sxs-lookup"><span data-stu-id="0e1ca-141">For example, you should not call bcp_control(BCPTEXTFILE) and bcp_setbulkmode.</span></span>  
  
 <span data-ttu-id="0e1ca-142">Можно вызвать bcp_control и bcp_setbulkmode для параметров bcp_control, которые не конфликтуют с bcp_setbulkmode.</span><span class="sxs-lookup"><span data-stu-id="0e1ca-142">You can call bcp_control and bcp_setbulkmode for bcp_control options that do not conflict with bcp_setbulkmode.</span></span> <span data-ttu-id="0e1ca-143">Например, можно вызвать bcp_control (БКПФИРСТ) и bcp_setbulkmode.</span><span class="sxs-lookup"><span data-stu-id="0e1ca-143">For example, you can call bcp_control(BCPFIRST) and bcp_setbulkmode.</span></span>  
  
 <span data-ttu-id="0e1ca-144">При попытке вызвать bcp_setbulkmode с последовательностью вызовов функций, включающих bcp_setcolfmt, bcp_control и bcp_readfmt, один из вызовов функций возвратит ошибку последовательности.</span><span class="sxs-lookup"><span data-stu-id="0e1ca-144">If you attempt to call bcp_setbulkmode with a sequence of function calls that includes bcp_setcolfmt, bcp_control, and bcp_readfmt, one of the function calls will return a sequence error failure.</span></span> <span data-ttu-id="0e1ca-145">Если вы решите устранить ошибку, вызовите bcp_init, чтобы сбросить все параметры и начать заново.</span><span class="sxs-lookup"><span data-stu-id="0e1ca-145">If you choose to correct the failure, call bcp_init to reset all the settings and start over.</span></span>  
  
 <span data-ttu-id="0e1ca-146">В следующей таблице приведено несколько примеров вызовов функций, которые вызовут ошибку последовательности.</span><span class="sxs-lookup"><span data-stu-id="0e1ca-146">The following table presents some examples of function calls that result in a function sequence error:</span></span>  
  
 <span data-ttu-id="0e1ca-147">Последовательность вызовов</span><span class="sxs-lookup"><span data-stu-id="0e1ca-147">Call sequence</span></span>  
  
```  
bcp_init("table", DB_IN);  
bcp_setbulkmode();  
```  
  
```  
bcp_init("table", DB_OUT);  
bcp_setbulkmode();  
bcp_readfmt();  
```  
  
```  
bcp_init(NULL, DB_OUT);  
bcp_control(BCPHINTS, "select ...");  
bcp_setbulkmode();  
```  
  
```  
bcp_init("table", DB_OUT);  
bcp_setbulkmode();  
bcp_setcolfmt();  
```  
  
```  
bcp_init("table", DB_OUT);  
bcp_control(BCPDELAYREADFMT, true);  
bcp_readfmt();  
bcp_setcolfmt();  
```  
  
```  
bcp_init(NULL, DB_OUT);  
bcp_control(BCPDELAYREADFMT, true);  
bcp_setbulkmode();  
bcp_control(BCPHINTS, "select ...");  
bcp_readfmt();  
```  
  
```  
bcp_init("table", DB_OUT);  
bcp_control(BCPDELAYREADFMT, true);  
bcp_columns();  
```  
  
```  
bcp_init("table", DB_OUT);  
bcp_control(BCPDELAYREADFMT, true);  
bcp_setcolfmt();  
```  
  
## <a name="example"></a><span data-ttu-id="0e1ca-148">Пример</span><span class="sxs-lookup"><span data-stu-id="0e1ca-148">Example</span></span>  
 <span data-ttu-id="0e1ca-149">В следующем образце создается четыре файла с использованием разных параметров функции bcp_setbulkmode.</span><span class="sxs-lookup"><span data-stu-id="0e1ca-149">The following sample creates four files using different settings of bcp_setbulkmode.</span></span>  
  
```  
// compile with: sqlncli11.lib odbc32.lib  
  
#include <windows.h>  
#include <stdio.h>  
#include <tchar.h>  
#include <sqlext.h>  
#include "sqlncli.h"  
  
// Global variables  
SQLHENV g_hEnv = NULL;  
SQLHDBC g_hDbc = NULL;  
  
void ODBCCleanUp() {  
   if (g_hDbc) {  
      SQLDisconnect(g_hDbc);  
      SQLFreeHandle(SQL_HANDLE_DBC, g_hDbc);  
      g_hDbc = NULL;  
   }  
   if (g_hEnv) {  
      SQLFreeHandle(SQL_HANDLE_ENV, g_hEnv);  
      g_hEnv = NULL;  
   }  
}  
  
BOOL MakeODBCConnection(TCHAR * pszServer) {  
   TCHAR szConnectionString[500];  
   TCHAR szOutConnectionString[500];  
   SQLSMALLINT iLen;  
   SQLRETURN rc;  
  
   _sntprintf_s(szConnectionString, 500, TEXT("DRIVER={SQL Server Native Client 11.0};Server=%s;Trusted_connection=yes;"), pszServer);  
   rc = SQLAllocHandle(SQL_HANDLE_ENV, SQL_NULL_HANDLE,&g_hEnv);  
   if (SQL_SUCCESS != rc && SQL_SUCCESS_WITH_INFO != rc) {  
      printf("SQLAllocHandle(SQL_HANDLE_ENV...) failed\n");  
      return false;  
   }  
   rc = SQLSetEnvAttr(g_hEnv,SQL_ATTR_ODBC_VERSION, (SQLPOINTER)SQL_OV_ODBC3, SQL_IS_UINTEGER);  
   if (SQL_SUCCESS != rc && SQL_SUCCESS_WITH_INFO != rc) {  
      printf("SQLSetEnvAttr failed\n");  
      SQLFreeHandle(SQL_HANDLE_ENV, g_hEnv);  
      return false;  
   }  
   rc = SQLAllocHandle( SQL_HANDLE_DBC, g_hEnv , &g_hDbc);  
   if (SQL_SUCCESS != rc && SQL_SUCCESS_WITH_INFO != rc) {  
      printf("SQLAllocHandle(SQL_HANDLE_DBC...) failed\n");  
      SQLFreeHandle(SQL_HANDLE_ENV, g_hEnv);  
      return false;  
   }  
   // Enable BCP  
   rc = SQLSetConnectAttr(g_hDbc, SQL_COPT_SS_BCP, (SQLPOINTER)SQL_BCP_ON, SQL_IS_INTEGER);  
   if (SQL_SUCCESS != rc && SQL_SUCCESS_WITH_INFO != rc) {  
      printf("SQLSetConnectAttr(.. SQL_COPT_SS_BCP, (SQLPOINTER)SQL_BCP_ON ...) failed\n");  
      ODBCCleanUp();  
      return false;  
   }  
   // connecting ...  
   rc = SQLDriverConnect(g_hDbc,NULL, (SQLTCHAR*)szConnectionString, SQL_NTS, (SQLTCHAR*)szOutConnectionString, 500, &iLen, SQL_DRIVER_NOPROMPT);  
   if (SQL_SUCCESS != rc && SQL_SUCCESS_WITH_INFO != rc) {  
      printf("SQLDriverConnect(SQL_HANDLE_DBC...) failed\n");  
      ODBCCleanUp();  
      return false;  
   }  
   return true;  
}  
  
BOOL BCPSetBulkMode(TCHAR * pszServer, TCHAR * pszQureryOut, char BCPType, TCHAR * pszDataFile) {  
   SQLRETURN rc;  
  
   if (!MakeODBCConnection(pszServer))  
      return false;  
   rc = bcp_init(g_hDbc, NULL, pszDataFile, NULL, DB_OUT);   // bcp init for queryout  
   if (SUCCEED != rc) {  
      printf("bcp_init failed\n");  
      ODBCCleanUp();  
      return false;  
   }  
   // setbulkmode  
   char ColTerm[] = "\t";  
   char RowTerm[] = "\r\n";  
   wchar_t wColTerm[] = L"\t";  
   wchar_t wRowTerm[] = L"\r\n";  
   BYTE * pColTerm = NULL;  
   int cbColTerm = NULL;  
   BYTE * pRowTerm = 0;  
   int cbRowTerm = 0;  
   int bulkmode = -1;  
  
   if (BCPType == 'c') {   // bcp -c  
      pColTerm = (BYTE*)ColTerm;  
      pRowTerm = (BYTE*)RowTerm;  
      cbColTerm = 1;  
      cbRowTerm = 2;  
      bulkmode = BCP_OUT_CHARACTER_MODE;  
   }  
   else  
      if (BCPType == 'w') {   // bcp -w   
         pColTerm = (BYTE*)wColTerm;  
         pRowTerm = (BYTE*)wRowTerm;  
         cbColTerm = 2;  
         cbRowTerm = 4;  
         bulkmode = BCP_OUT_WIDE_CHARACTER_MODE;  
      }  
      else  
         if (BCPType == 'n')   // bcp -n  
            bulkmode = BCP_OUT_NATIVE_MODE;  
         else  
            if (BCPType == 'N')   // bcp -n  
               bulkmode = BCP_OUT_NATIVE_TEXT_MODE;  
            else {  
               printf("unknown bcp mode\n");  
               ODBCCleanUp();  
               return false;  
            }  
            rc = bcp_setbulkmode(g_hDbc, bulkmode, pColTerm, cbColTerm, pRowTerm, cbRowTerm);  
            if (SUCCEED != rc) {  
               printf("bcp_setbulkmode failed\n");  
               ODBCCleanUp();  
               return false;  
            }  
            // set queryout TSQL statement  
            rc = bcp_control(g_hDbc, BCPHINTS , pszQureryOut);  
            if (SUCCEED != rc) {  
               printf("bcp_control(..BCP_OPTION_HINTS..) failed\n");  
               ODBCCleanUp();  
               return false;  
            }  
            // bcp copy  
            DBINT nRowsInserted = 0;  
            rc = bcp_exec(g_hDbc, &nRowsInserted);  
            if (SUCCEED != rc) {  
               printf("bcp_exec failed\n");  
               ODBCCleanUp();  
               return false;  
            }  
            printf("bcp done\n");  
            ODBCCleanUp();  
            return true;  
}  
  
int main() {  
   BCPSetBulkMode(TEXT("localhost"), TEXT("SELECT 'this is a bcp -c test', 1,2") , 'c', TEXT("bcpc.dat"));  
   BCPSetBulkMode(TEXT("localhost"), TEXT("SELECT 'this is a bcp -w test', 1,2") , 'w', TEXT("bcpw.dat"));  
   BCPSetBulkMode(TEXT("localhost"), TEXT("SELECT 'this is a bcp -c test', 1,2") , 'n', TEXT("bcpn.dat"));  
   BCPSetBulkMode(TEXT("localhost"), TEXT("SELECT 'this is a bcp -w test', 1,2") , 'N', TEXT("bcp_N.dat"));  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="0e1ca-150">См. также:</span><span class="sxs-lookup"><span data-stu-id="0e1ca-150">See Also</span></span>  
 [<span data-ttu-id="0e1ca-151">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="0e1ca-151">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
