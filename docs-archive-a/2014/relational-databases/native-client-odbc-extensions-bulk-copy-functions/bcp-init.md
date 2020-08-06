---
title: bcp_init | Документация Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_init
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_init function
ms.assetid: 6a25862c-7f31-4873-ab65-30f3abde89d2
author: rothja
ms.author: jroth
ms.openlocfilehash: 72d48b2a07e425e0863084c700c4de93d2776739
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657772"
---
# <a name="bcp_init"></a><span data-ttu-id="c89b3-102">bcp_init</span><span class="sxs-lookup"><span data-stu-id="c89b3-102">bcp_init</span></span>
  <span data-ttu-id="c89b3-103">Инициализирует операцию массового копирования.</span><span class="sxs-lookup"><span data-stu-id="c89b3-103">Initializes the bulk copy operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c89b3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c89b3-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_init (  
HDBC   
hdbc  
,  
LPCTSTR   
szTable  
,  
LPCTSTR   
szDataFile  
,  
LPCTSTR   
szErrorFile  
,  
INT   
eDirection  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="c89b3-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="c89b3-105">Arguments</span></span>  
 <span data-ttu-id="c89b3-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="c89b3-106">*hdbc*</span></span>  
 <span data-ttu-id="c89b3-107">Дескриптор соединения ODBC с поддержкой массового копирования.</span><span class="sxs-lookup"><span data-stu-id="c89b3-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="c89b3-108">*szTable*</span><span class="sxs-lookup"><span data-stu-id="c89b3-108">*szTable*</span></span>  
 <span data-ttu-id="c89b3-109">Имя таблицы базы данных, в которую (или из которой) выполняется копирование.</span><span class="sxs-lookup"><span data-stu-id="c89b3-109">Is the name of the database table to be copied into or out of.</span></span> <span data-ttu-id="c89b3-110">Это имя также может включать имя базы данных или владельца.</span><span class="sxs-lookup"><span data-stu-id="c89b3-110">This name can also include the database name or the owner name.</span></span> <span data-ttu-id="c89b3-111">Например, **Pubs. Gracie. titles**, **Pubs.. заголовки**, **Gracie. titles**и **titles** — это имена юридических таблиц.</span><span class="sxs-lookup"><span data-stu-id="c89b3-111">For example, **pubs.gracie.titles**, **pubs..titles**, **gracie.titles**, and **titles** are all legal table names.</span></span>  
  
 <span data-ttu-id="c89b3-112">Если *eDirection* имеет значение DB_OUT, *сзтабле* также может быть именем представления базы данных.</span><span class="sxs-lookup"><span data-stu-id="c89b3-112">If *eDirection* is DB_OUT, *szTable* can also be the name of a database view.</span></span>  
  
 <span data-ttu-id="c89b3-113">Если *eDirection* имеет DB_OUT и инструкция SELECT указывается с помощью [bcp_control](bcp-control.md) перед вызовом [bcp_exec](bcp-exec.md) , **bcp_init**_сзтабле_ должно быть установлено в NULL.</span><span class="sxs-lookup"><span data-stu-id="c89b3-113">If *eDirection* is DB_OUT and a SELECT statement is specified using [bcp_control](bcp-control.md) before [bcp_exec](bcp-exec.md) is called, **bcp_init**_szTable_ must be set to NULL.</span></span>  
  
 <span data-ttu-id="c89b3-114">*szDataFile*</span><span class="sxs-lookup"><span data-stu-id="c89b3-114">*szDataFile*</span></span>  
 <span data-ttu-id="c89b3-115">Имя пользовательского файла, в который или из которого выполняется копирование.</span><span class="sxs-lookup"><span data-stu-id="c89b3-115">Is the name of the user file to be copied into or out of.</span></span> <span data-ttu-id="c89b3-116">Если данные копируются непосредственно из переменных с помощью [bcp_sendrow](bcp-sendrow.md), задайте для *сздатафиле* значение null.</span><span class="sxs-lookup"><span data-stu-id="c89b3-116">If data is being copied directly from variables by using [bcp_sendrow](bcp-sendrow.md), set *szDataFile* to NULL.</span></span>  
  
 <span data-ttu-id="c89b3-117">*szErrorFile*</span><span class="sxs-lookup"><span data-stu-id="c89b3-117">*szErrorFile*</span></span>  
 <span data-ttu-id="c89b3-118">Имя файла ошибок, заполняемого сообщениями о ходе работы, сообщениями об ошибках и копиями строк, которые по каким-либо причинам не могут быть скопированы из пользовательского файла в таблицу.</span><span class="sxs-lookup"><span data-stu-id="c89b3-118">Is the name of the error file to be filled with progress messages, error messages, and copies of any rows that, for any reason, could not be copied from a user file to a table.</span></span> <span data-ttu-id="c89b3-119">Если значение NULL передается как *сзеррорфиле*, файл ошибок не используется.</span><span class="sxs-lookup"><span data-stu-id="c89b3-119">If NULL is passed as *szErrorFile*, no error file is used.</span></span>  
  
 <span data-ttu-id="c89b3-120">*eDirection*</span><span class="sxs-lookup"><span data-stu-id="c89b3-120">*eDirection*</span></span>  
 <span data-ttu-id="c89b3-121">Направление копирования (DB_IN или DB_OUT).</span><span class="sxs-lookup"><span data-stu-id="c89b3-121">Is the direction of the copy, either DB_IN or DB_OUT.</span></span> <span data-ttu-id="c89b3-122">Значение DB_IN указывает на копирование из переменных программы или пользовательского файла в таблицу.</span><span class="sxs-lookup"><span data-stu-id="c89b3-122">DB_IN indicates a copy from program variables or a user file to a table.</span></span> <span data-ttu-id="c89b3-123">Значение DB_OUT указывает на копирование из таблицы базы данных в пользовательский файл.</span><span class="sxs-lookup"><span data-stu-id="c89b3-123">DB_OUT indicates a copy from a database table to a user file.</span></span> <span data-ttu-id="c89b3-124">Если используется значение DB_OUT, необходимо указать имя пользовательского файла.</span><span class="sxs-lookup"><span data-stu-id="c89b3-124">You must specify a user file name with DB_OUT.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="c89b3-125">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c89b3-125">Returns</span></span>  
 <span data-ttu-id="c89b3-126">SUCCEED или FAIL.</span><span class="sxs-lookup"><span data-stu-id="c89b3-126">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c89b3-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="c89b3-127">Remarks</span></span>  
 <span data-ttu-id="c89b3-128">Вызовите **bcp_init** перед вызовом любой другой функции небольшого копирования.</span><span class="sxs-lookup"><span data-stu-id="c89b3-128">Call **bcp_init** before calling any other bulk-copy function.</span></span> <span data-ttu-id="c89b3-129">**bcp_init** выполняет необходимые операции инициализации для выполнения операций с массовым копированием данных между рабочей станцией и [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c89b3-129">**bcp_init** performs the necessary initializations for a bulk copy of data between the workstation and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="c89b3-130">Функция **bcp_init** должна быть предоставлена с помощью обработчика соединений ODBC, включенного для использования с функциями операций с массовым копированием.</span><span class="sxs-lookup"><span data-stu-id="c89b3-130">The **bcp_init** function must be provided with an ODBC connection handle enabled for use with bulk copy functions.</span></span> <span data-ttu-id="c89b3-131">Чтобы включить этот маркер, используйте [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) с параметром SQL_COPT_SS_BCP, чтобы SQL_BCP_ON для выделенного, но не подключенного обработчика соединения.</span><span class="sxs-lookup"><span data-stu-id="c89b3-131">To enable the handle, use [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_BCP set to SQL_BCP_ON on an allocated, but not connected, connection handle.</span></span> <span data-ttu-id="c89b3-132">Попытка назначения атрибута для подключенного дескриптора приведет к ошибке.</span><span class="sxs-lookup"><span data-stu-id="c89b3-132">Attempting to assign the attribute on a connected handle results in an error.</span></span>  
  
 <span data-ttu-id="c89b3-133">Если указан файл данных, **bcp_init** анализирует структуру источника базы данных или целевой таблицы, а не файл данных.</span><span class="sxs-lookup"><span data-stu-id="c89b3-133">When a data file is specified, **bcp_init** examines the structure of the database source or target table, not the data file.</span></span> <span data-ttu-id="c89b3-134">**bcp_init** задает значения формата данных для файла данных на основе каждого столбца в таблице базы данных, представлении или результирующем наборе.</span><span class="sxs-lookup"><span data-stu-id="c89b3-134">**bcp_init** specifies data format values for the data file based on each column in the database table, view, or SELECT result set.</span></span> <span data-ttu-id="c89b3-135">Эта спецификация включает тип данных каждого столбца, присутствие или отсутствие длины и допустимости значений NULL и строки байтов признака конца, а также ширину для типов данных с фиксированной длиной.</span><span class="sxs-lookup"><span data-stu-id="c89b3-135">This specification includes the data type of each column, the presence or absence of a length or null indicator and terminator byte strings in the data, and the width of fixed-length data types.</span></span> <span data-ttu-id="c89b3-136">**bcp_init** задает следующие значения:</span><span class="sxs-lookup"><span data-stu-id="c89b3-136">**bcp_init** sets these values as follows:</span></span>  
  
-   <span data-ttu-id="c89b3-137">Указанный тип данных представляет собой тип данных столбца в таблице базы данных, представлении или результирующем наборе SELECT.</span><span class="sxs-lookup"><span data-stu-id="c89b3-137">The data type specified is the data type of the column in the database table, view, or SELECT result set.</span></span> <span data-ttu-id="c89b3-138">Тип данных ограничивается собственными типами данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], указанными в файле sqlncli.h.</span><span class="sxs-lookup"><span data-stu-id="c89b3-138">The data type is enumerated by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native data types specified in sqlncli.h.</span></span> <span data-ttu-id="c89b3-139">Сами данные представляются в машинной форме.</span><span class="sxs-lookup"><span data-stu-id="c89b3-139">Data itself is represented in its computer form.</span></span> <span data-ttu-id="c89b3-140">Это значит, что данные из столбца **целочисленного** типа представляются в последовательности из четырех байтов с большим или прямым порядком байтов на основе компьютера, создавшего файл данных.</span><span class="sxs-lookup"><span data-stu-id="c89b3-140">That is, data from a column of **integer** data type is represented by a four-byte sequence that is big-or little-endian based on the computer that created the data file.</span></span>  
  
-   <span data-ttu-id="c89b3-141">Если тип данных базы данных имеет фиксированную длину, то для данных файла данных также задается фиксированная длина.</span><span class="sxs-lookup"><span data-stu-id="c89b3-141">If a database data type is fixed in length, the data file data is also fixed in length.</span></span> <span data-ttu-id="c89b3-142">Функции с массовым копированием, обрабатывающие данные (например, [bcp_exec](bcp-exec.md)), анализируют строки данных, ожидающие длины данных в файле данных, так, чтобы они совпадали с длиной данных, указанных в таблице, представлении или списке столбцов базы данных.</span><span class="sxs-lookup"><span data-stu-id="c89b3-142">Bulk-copy functions that process data (for example, [bcp_exec](bcp-exec.md)) parse data rows expecting the length of the data in the data file to be identical to the length of the data specified in the database table, view, or SELECT column list.</span></span> <span data-ttu-id="c89b3-143">Например, данные для столбца базы данных, определенного как **char (13)** , должны быть представлены 13 символами для каждой строки данных в файле.</span><span class="sxs-lookup"><span data-stu-id="c89b3-143">For example, data for a database column defined as **char(13)** must be represented by 13 characters for each row of data in the file.</span></span> <span data-ttu-id="c89b3-144">Данные фиксированной длины могут быть обозначены префиксом с признаком значения NULL, если столбец базы данных допускает значения NULL.</span><span class="sxs-lookup"><span data-stu-id="c89b3-144">Fixed-length data can be prefixed with a null indicator if the database column allows null values.</span></span>  
  
-   <span data-ttu-id="c89b3-145">После определения последовательности байт, служащей признаком конца, ее длина устанавливается в значение 0.</span><span class="sxs-lookup"><span data-stu-id="c89b3-145">When terminator-byte sequence is defined, the length of the terminator-byte sequence is set to 0.</span></span>  
  
-   <span data-ttu-id="c89b3-146">При копировании в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] файл данных должен содержать данные для каждого столбца таблицы базы данных.</span><span class="sxs-lookup"><span data-stu-id="c89b3-146">When copying to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the data file must have data for each column in the database table.</span></span> <span data-ttu-id="c89b3-147">При копировании на [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] данные из всех столбцов в таблице, представлении или результирующем наборе инструкции SELECT базы данных копируются в файл данных.</span><span class="sxs-lookup"><span data-stu-id="c89b3-147">When copying from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], data from all columns in the database table, view, or SELECT result set are copied to the data file.</span></span>  
  
-   <span data-ttu-id="c89b3-148">При копировании в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] порядковый номер столбца в файле данных должен совпадать с порядковым номером столбца таблицы базы данных.</span><span class="sxs-lookup"><span data-stu-id="c89b3-148">When copying to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the ordinal position of a column in the data file must be identical to the ordinal position of the column in the database table.</span></span> <span data-ttu-id="c89b3-149">При копировании [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] из **bcp_exec** помещает данные в зависимости от порядкового номера столбца в таблице базы данных.</span><span class="sxs-lookup"><span data-stu-id="c89b3-149">When copying from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], **bcp_exec** places data based on the ordinal position of the column in the database table.</span></span>  
  
-   <span data-ttu-id="c89b3-150">Если тип данных базы данных имеет переменную длину (например, **varbinary (22)**) или столбец базы данных может содержать значения NULL, то данные в файле данных имеют префикс длины или значения NULL.</span><span class="sxs-lookup"><span data-stu-id="c89b3-150">If a database data type is variable in length (for example, **varbinary(22)**) or if a database column can contain null values, data in the data file is prefixed by a length/null indicator.</span></span> <span data-ttu-id="c89b3-151">Ширина признака изменяется в зависимости от типа данных и версии массового копирования.</span><span class="sxs-lookup"><span data-stu-id="c89b3-151">The width of the indicator varies based on the data type and version of bulk copy.</span></span>  
  
 <span data-ttu-id="c89b3-152">Чтобы изменить значения формата данных, заданные для файла данных, вызовите [bcp_columns](bcp-columns.md) и [bcp_colfmt](bcp-colfmt.md).</span><span class="sxs-lookup"><span data-stu-id="c89b3-152">To change data format values specified for a data file, call [bcp_columns](bcp-columns.md) and [bcp_colfmt](bcp-colfmt.md).</span></span>  
  
 <span data-ttu-id="c89b3-153">Массовое копирование в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] может быть оптимизировано для таблиц, не содержащих индексов, путем установки модели восстановления базы данных в значение SIMPLE или BULK_LOGGED.</span><span class="sxs-lookup"><span data-stu-id="c89b3-153">Bulk copies to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can be optimized for tables that do not contain indexes by setting the database recovery model to SIMPLE or BULK_LOGGED.</span></span> <span data-ttu-id="c89b3-154">Дополнительные сведения см. [в разделе Предварительные требования для минимального ведения журнала при выполнении массового импорта](../import-export/prerequisites-for-minimal-logging-in-bulk-import.md) и [изменения базы данных](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c89b3-154">For more information, see [Prerequisites for Minimal Logging in Bulk Import](../import-export/prerequisites-for-minimal-logging-in-bulk-import.md) and [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
 <span data-ttu-id="c89b3-155">Если файл данных не используется, необходимо вызвать [bcp_bind](../../relational-databases/native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md) , чтобы указать формат и расположение в памяти фсор каждого столбца, а затем скопировать строки данных в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с помощью [bcp_sendrow](bcp-sendrow.md).</span><span class="sxs-lookup"><span data-stu-id="c89b3-155">If no data file is used, you must call [bcp_bind](../../relational-databases/native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md) to specify the format and location in memory of the data fsor each column, then copy data rows to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using [bcp_sendrow](bcp-sendrow.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c89b3-156">Пример</span><span class="sxs-lookup"><span data-stu-id="c89b3-156">Example</span></span>  
 <span data-ttu-id="c89b3-157">В этом образце демонстрируется использование функции ODBC bcp_init с файлом форматирования.</span><span class="sxs-lookup"><span data-stu-id="c89b3-157">This sample shows how to use the ODBC bcp_init function with a format file.</span></span>  
  
 <span data-ttu-id="c89b3-158">Перед компиляцией и выполнением кода на С++ необходимо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="c89b3-158">Before you compile and run the C++ code, you need to do the following:</span></span>  
  
-   <span data-ttu-id="c89b3-159">Создайте источник данных ODBC с именем Test.</span><span class="sxs-lookup"><span data-stu-id="c89b3-159">Create an ODBC data source called Test.</span></span> <span data-ttu-id="c89b3-160">Его можно сопоставить с любой базой данных.</span><span class="sxs-lookup"><span data-stu-id="c89b3-160">You can associate this data source with any database.</span></span>  
  
-   <span data-ttu-id="c89b3-161">Выполните в базе данных следующую инструкцию [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="c89b3-161">Run the following [!INCLUDE[tsql](../../includes/tsql-md.md)] on the database:</span></span>  
  
    ```  
    CREATE TABLE BCPDate (cola int, colb datetime);  
    ```  
  
-   <span data-ttu-id="c89b3-162">В каталог, где будет запускаться приложение, добавьте файл Bcpfmt.fmt и добавьте в этот файл следующик код:</span><span class="sxs-lookup"><span data-stu-id="c89b3-162">In the directory where you will run the application, add a file called Bcpfmt.fmt, and add this to the file:</span></span>  
  
    ```  
    8.0  
    2  
    1SQLCHAR04"\t"1colaSQL_Latin1_General_Cp437_Bin  
    2SQLCHAR08"\r\n"2colbSQL_Latin1_General_Cp437_Bin  
    ```  
  
-   <span data-ttu-id="c89b3-163">В каталог, где будет запускаться приложение, добавьте файл Bcpodbc.bcp и добавьте в этот файл следующик код:</span><span class="sxs-lookup"><span data-stu-id="c89b3-163">In the directory where you will run the application, add a file called Bcpodbc.bcp, and add this to the file:</span></span>  
  
    ```  
    1  
    2  
    ```  
  
 <span data-ttu-id="c89b3-164">Теперь все готово к компиляции и выполнению кода на C++.</span><span class="sxs-lookup"><span data-stu-id="c89b3-164">Now you are ready to compile and run the C++ code.</span></span>  
  
```  
// compile with: odbc32.lib sqlncli11.lib  
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
   retcode = SQLConnect(hdbc1, (UCHAR*)"Test", SQL_NTS, (UCHAR*)"", SQL_NTS, (UCHAR*)"", SQL_NTS);  
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
  
## <a name="see-also"></a><span data-ttu-id="c89b3-165">См. также:</span><span class="sxs-lookup"><span data-stu-id="c89b3-165">See Also</span></span>  
 [<span data-ttu-id="c89b3-166">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="c89b3-166">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
