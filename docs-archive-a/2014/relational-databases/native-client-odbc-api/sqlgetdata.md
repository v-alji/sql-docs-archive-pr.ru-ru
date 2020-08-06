---
title: SQLGetData | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLGetData function
ms.assetid: 204848be-8787-45b4-816f-a60ac9d56fcf
author: rothja
ms.author: jroth
ms.openlocfilehash: c351cf7340bc7b0afeb76b139bd75aa429f56e10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654257"
---
# <a name="sqlgetdata"></a><span data-ttu-id="f2bde-102">SQLGetData</span><span class="sxs-lookup"><span data-stu-id="f2bde-102">SQLGetData</span></span>
  <span data-ttu-id="f2bde-103">**SQLGetData** используется для получения результирующих наборов данных без значений столбцов привязки.</span><span class="sxs-lookup"><span data-stu-id="f2bde-103">**SQLGetData** is used to retrieve result set data without binding column values.</span></span> <span data-ttu-id="f2bde-104">**SQLGetData** можно последовательно вызывать для одного и того же столбца, чтобы получить большие объемы данных из столбца с типом данных **Text**, **ntext**или **Image** .</span><span class="sxs-lookup"><span data-stu-id="f2bde-104">**SQLGetData** can be called successively on the same column to retrieve large amounts of data from a column with a **text**, **ntext**, or **image** data type.</span></span>  
  
 <span data-ttu-id="f2bde-105">В приложении не обязательно выполнять привязку данных для получения данных результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="f2bde-105">There is no requirement that an application bind variables to fetch result set data.</span></span> <span data-ttu-id="f2bde-106">Данные любого столбца можно получить из [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] драйвера ODBC собственного клиента с помощью **SQLGetData**.</span><span class="sxs-lookup"><span data-stu-id="f2bde-106">The data of any column can be retrieved from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver by using **SQLGetData**.</span></span>  
  
 <span data-ttu-id="f2bde-107">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Драйвер ODBC для собственного клиента не поддерживает использование **SQLGetData** для получения данных в случайном порядке столбцов.</span><span class="sxs-lookup"><span data-stu-id="f2bde-107">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver does not support using **SQLGetData** to retrieve data in random column order.</span></span> <span data-ttu-id="f2bde-108">Все несвязанные столбцы, обрабатываемые с помощью **SQLGetData** , должны иметь более высокие порядковые номера столбцов, чем связанные столбцы в результирующем наборе.</span><span class="sxs-lookup"><span data-stu-id="f2bde-108">All unbound columns processed with **SQLGetData** must have higher column ordinals than the bound columns in the result set.</span></span> <span data-ttu-id="f2bde-109">Приложение обрабатывает данные непривязанных столбцов (начиная со столбца с наименьшим порядковым номером и заканчивая столбцом с наибольшим порядковым номером).</span><span class="sxs-lookup"><span data-stu-id="f2bde-109">The application must process data from the lowest unbound ordinal column value to the highest.</span></span> <span data-ttu-id="f2bde-110">Попытка получить данные из столбца с более низким порядковым номером приведет к ошибке.</span><span class="sxs-lookup"><span data-stu-id="f2bde-110">Attempting to retrieve data from a lower ordinally numbered column results in an error.</span></span> <span data-ttu-id="f2bde-111">Если в приложении используются серверные курсоры для формирования сообщений о строках результирующего набора, то приложение может повторно получить текущую строку, а затем получить значение столбца.</span><span class="sxs-lookup"><span data-stu-id="f2bde-111">If the application is using server cursors to report result set rows, the application can refetch the current row and then fetch the value of a column.</span></span> <span data-ttu-id="f2bde-112">Если инструкция выполняется для однопроходного курсора только для чтения по умолчанию, необходимо повторно выполнить инструкцию для резервного копирования **SQLGetData**.</span><span class="sxs-lookup"><span data-stu-id="f2bde-112">If a statement is executed on the default read-only, forward-only cursor, you must re-execute the statement to back up **SQLGetData**.</span></span>  
  
 <span data-ttu-id="f2bde-113">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Драйвер ODBC для собственного клиента точно сообщает длину данных типа **Text**, **ntext**и **Image** , полученных с помощью **SQLGetData**.</span><span class="sxs-lookup"><span data-stu-id="f2bde-113">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver accurately reports the length of **text**, **ntext**, and **image** data retrieved using **SQLGetData**.</span></span> <span data-ttu-id="f2bde-114">Приложение может правильно использовать параметр *StrLen_or_IndPtr* возвращаться для быстрого получения длинных данных.</span><span class="sxs-lookup"><span data-stu-id="f2bde-114">The application can make good use of the *StrLen_or_IndPtr* parameter return to retrieve long data rapidly.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f2bde-115">Для типов больших значений *StrLen_or_IndPtr* будет возвращать SQL_NO_TOTAL в случае усечения данных.</span><span class="sxs-lookup"><span data-stu-id="f2bde-115">For large value types, *StrLen_or_IndPtr* will return SQL_NO_TOTAL in cases of data truncation.</span></span>  
  
## <a name="sqlgetdata-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="f2bde-116">Поддержка методом SQLGetData улучшенных функций даты и времени</span><span class="sxs-lookup"><span data-stu-id="f2bde-116">SQLGetData Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="f2bde-117">Значения результирующих столбцов типов даты-времени преобразуются, как описано в статье [преобразования из SQL в C](../native-client-odbc-date-time/datetime-data-type-conversions-from-sql-to-c.md).</span><span class="sxs-lookup"><span data-stu-id="f2bde-117">Result column values of date/time types are converted as described in [Conversions from SQL to C](../native-client-odbc-date-time/datetime-data-type-conversions-from-sql-to-c.md).</span></span>  
  
 <span data-ttu-id="f2bde-118">Дополнительные сведения см. в разделе [улучшения даты и времени &#40;&#41;ODBC ](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="f2bde-118">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="sqlgetdata-support-for-large-clr-udts"></a><span data-ttu-id="f2bde-119">Поддержка методом SQLGetData больших определяемых пользователем типов (UDT) в среде CLR</span><span class="sxs-lookup"><span data-stu-id="f2bde-119">SQLGetData Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="f2bde-120">**SQLGetData** поддерживает большие определяемые пользователем типы данных CLR (UDT).</span><span class="sxs-lookup"><span data-stu-id="f2bde-120">**SQLGetData** supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="f2bde-121">Дополнительные сведения см. в разделе [большие определяемые пользователем типы данных CLR &#40;&#41;ODBC ](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="f2bde-121">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2bde-122">Пример</span><span class="sxs-lookup"><span data-stu-id="f2bde-122">Example</span></span>  
  
```  
SQLHDBC     hDbc = NULL;  
SQLHSTMT    hStmt = NULL;  
long        lEmpID;  
PBYTE       pPicture;  
SQLINTEGER  pIndicators[2];  
  
// Get an environment, connection, and so on.  
...  
  
// Get a statement handle and execute a command.  
SQLAllocHandle(SQL_HANDLE_STMT, hDbc, &hStmt);  
  
if (SQLExecDirect(hStmt,  
    (SQLCHAR*) "SELECT EmployeeID, Photo FROM Employees",  
    SQL_NTS) == SQL_ERROR)  
    {  
    // Handle error and return.  
    }  
  
// Retrieve data from row set.  
SQLBindCol(hStmt, 1, SQL_C_LONG, (SQLPOINTER) &lEmpID, sizeof(long),  
    &pIndicators[0]);  
  
while (SQLFetch(hStmt) == SQL_SUCCESS)  
    {  
    cout << "EmployeeID: " << lEmpID << "\n";  
  
    // Call SQLGetData to determine the amount of data that's waiting.  
    if (SQLGetData(hStmt, 2, SQL_C_BINARY, pPicture, 0, &pIndicators[1])  
        == SQL_SUCCESS_WITH_INFO)  
        {  
        cout << "Photo size: " pIndicators[1] << "\n\n";  
  
        // Get all the data at once.  
        pPicture = new BYTE[pIndicators[1]];  
        if (SQLGetData(hStmt, 2, SQL_C_DEFAULT, pPicture,  
            pIndicators[1], &pIndicators[1]) != SQL_SUCCESS)  
            {  
            // Handle error and continue.  
            }  
  
        delete [] pPicture;  
        }  
    else  
        {  
        // Handle error on attempt to get data length.  
        }  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="f2bde-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="f2bde-123">See Also</span></span>  
 <span data-ttu-id="f2bde-124">[Функция SQLGetData](https://go.microsoft.com/fwlink/?LinkId=59350) </span><span class="sxs-lookup"><span data-stu-id="f2bde-124">[SQLGetData Function](https://go.microsoft.com/fwlink/?LinkId=59350) </span></span>  
 [<span data-ttu-id="f2bde-125">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="f2bde-125">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
