---
title: SQLGetDescField | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLGetDescField function
ms.assetid: 3e59a37a-28ee-4c91-8968-7fe3b966739d
author: rothja
ms.author: jroth
ms.openlocfilehash: 4538396dbfb5406d0464c4730c1f6f3bd5882799
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665323"
---
# <a name="sqlgetdescfield"></a><span data-ttu-id="42c99-102">SQLGetDescField</span><span class="sxs-lookup"><span data-stu-id="42c99-102">SQLGetDescField</span></span>
  <span data-ttu-id="42c99-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Драйвер ODBC для собственного клиента предоставляет только зависящие от драйвера поля дескриптора для дескриптора строки реализации (IRD).</span><span class="sxs-lookup"><span data-stu-id="42c99-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver exposes driver-specific descriptor fields for the implementation row descriptor (IRD) only.</span></span> <span data-ttu-id="42c99-104">В IRD [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поля дескриптора ссылаются с помощью атрибутов столбцов, специфичных для драйвера.</span><span class="sxs-lookup"><span data-stu-id="42c99-104">Within the IRD, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] descriptor fields are referenced through driver-specific column attributes.</span></span> <span data-ttu-id="42c99-105">Сведения о полном списке доступных полей дескрипторов для конкретных драйверов см. в разделе [SQLColAttribute](sqlcolattribute.md).</span><span class="sxs-lookup"><span data-stu-id="42c99-105">For information about a complete list of available driver-specific descriptor fields, see [SQLColAttribute](sqlcolattribute.md).</span></span>  
  
 <span data-ttu-id="42c99-106">Поля дескриптора, содержащие строки идентификатора столбца, часто являются строками нулевой длины.</span><span class="sxs-lookup"><span data-stu-id="42c99-106">Descriptor fields that contain column identifier strings are often zero-length strings.</span></span> <span data-ttu-id="42c99-107">Все специфические для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] значения поля дескриптора доступны только для чтения.</span><span class="sxs-lookup"><span data-stu-id="42c99-107">All [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-specific descriptor field values are read-only.</span></span>  
  
 <span data-ttu-id="42c99-108">Как и атрибуты, полученные с помощью SQLColAttribute, поля дескриптора, сообщающие атрибуты уровня строки (например, SQL_CA_SS_COMPUTE_ID), выводятся для всех столбцов результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="42c99-108">Like attributes retrieved with SQLColAttribute, descriptor fields that report row-level attributes (such as SQL_CA_SS_COMPUTE_ID) are reported for all columns in the result set.</span></span>  
  
## <a name="sqlgetdescfield-and-table-valued-parameters"></a><span data-ttu-id="42c99-109">Функция SQLGetDescField и возвращающие табличные значения параметры</span><span class="sxs-lookup"><span data-stu-id="42c99-109">SQLGetDescField and Table-Valued Parameters</span></span>  
 <span data-ttu-id="42c99-110">SQLGetDescField можно использовать для получения значений для расширенных атрибутов возвращающих табличное значение параметров и столбцов возвращающих табличное значение параметров.</span><span class="sxs-lookup"><span data-stu-id="42c99-110">SQLGetDescField can be used to get values for extended attributes of table-valued parameters and table-valued parameter columns.</span></span> <span data-ttu-id="42c99-111">Дополнительные сведения о возвращающих табличное значение параметрах см. в разделе [возвращающие табличное значение параметры &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="42c99-111">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="sqlgetdescfield-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="42c99-112">Поддержка функции SQLGetDescField для усовершенствованных функций даты-времени</span><span class="sxs-lookup"><span data-stu-id="42c99-112">SQLGetDescField Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="42c99-113">Сведения о полях дескриптора, доступных в новых типах даты и времени, см. в разделе [метаданные параметров и результатов](../native-client-odbc-date-time/metadata-parameter-and-result.md).</span><span class="sxs-lookup"><span data-stu-id="42c99-113">For information about the descriptor fields available with the new date/time types, see [Parameter and Result Metadata](../native-client-odbc-date-time/metadata-parameter-and-result.md).</span></span>  
  
 <span data-ttu-id="42c99-114">Дополнительные сведения см. в разделе [улучшения даты и времени &#40;&#41;ODBC ](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="42c99-114">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
 <span data-ttu-id="42c99-115">Начиная с [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , SQLGetDescField может возвращать `SQL_C_SS_TIME2` (для `time` типов) или `SQL_C_SS_TIMESTAMPOFFSET` (для `datetimeoffset` ), а не `SQL_C_BINARY` , если приложение использует ODBC 3,8.</span><span class="sxs-lookup"><span data-stu-id="42c99-115">Beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], SQLGetDescField can return `SQL_C_SS_TIME2` (for `time` types) or `SQL_C_SS_TIMESTAMPOFFSET` (for `datetimeoffset`) instead of `SQL_C_BINARY`, if your application uses ODBC 3.8.</span></span>  
  
## <a name="sqlgetdescfield-support-for-large-clr-udts"></a><span data-ttu-id="42c99-116">Поддержка функции SQLGetDescField для больших определяемых пользователем типов данных CLR</span><span class="sxs-lookup"><span data-stu-id="42c99-116">SQLGetDescField Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="42c99-117">Функция `SQLGetDescField` поддерживает определяемые пользователем типы больших данных CLR.</span><span class="sxs-lookup"><span data-stu-id="42c99-117">`SQLGetDescField` supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="42c99-118">Дополнительные сведения см. в разделе [большие определяемые пользователем типы данных CLR &#40;&#41;ODBC ](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="42c99-118">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="sqlgetdescfield-support-for-sparse-columns"></a><span data-ttu-id="42c99-119">Поддержка функции SQLGetDescField Support для разреженных столбцов</span><span class="sxs-lookup"><span data-stu-id="42c99-119">SQLGetDescField Support for Sparse Columns</span></span>  
 <span data-ttu-id="42c99-120">SQLGetDescField можно использовать для запроса нового поля IRD SQL_CA_SS_IS_COLUMN_SET, чтобы определить, является ли столбец `column_set` столбцом.</span><span class="sxs-lookup"><span data-stu-id="42c99-120">SQLGetDescField can be used to query the new IRD field SQL_CA_SS_IS_COLUMN_SET to determine if a column is a `column_set` column.</span></span>  
  
 <span data-ttu-id="42c99-121">Дополнительные сведения см. в разделе [Поддержка разреженных столбцов &#40;&#41;ODBC ](../native-client/odbc/sparse-columns-support-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="42c99-121">For more information, see [Sparse Columns Support &#40;ODBC&#41;](../native-client/odbc/sparse-columns-support-odbc.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="42c99-122">Пример</span><span class="sxs-lookup"><span data-stu-id="42c99-122">Example</span></span>  
  
```  
typedef struct tagCOMPUTEBYLIST  
    {  
    SQLSMALLINT nBys;  
    SQLSMALLINT aByList[1];  
    } COMPUTEBYLIST;  
typedef COMPUTEBYLIST* PCOMPUTEBYLIST;   
  
SQLHDESC    hIRD;   
SQLINTEGER  cbIRD;   
SQLINTEGER  nSet = 0;   
  
// . . .  
// Execute a statement that contains a COMPUTE clause,  
//  then get the descriptor handle of the IRD and  
//  get some IRD values.  
  
SQLGetStmtAttr(g_hStmt, SQL_ATTR_IMP_ROW_DESC,  
    (SQLPOINTER) &hIRD, sizeof(SQLHDESC), &cbIRD);  
  
// For statement-wide column attributes, any  
//  descriptor record will do. You know that 1 exists,  
//  so use it.  
SQLGetDescField(hIRD, 1, SQL_CA_SS_NUM_COMPUTES,  
    (SQLPOINTER) &nComputes, SQL_IS_INTEGER, &cbIRD);  
  
if (nSet == 0)  
    {  
    SQLINTEGER      nOrderID;  
  
    printf_s("Normal result set.\n");  
  
    for (nCol = 0; nCol < nCols; nCol++)  
        {  
        SQLGetDescField(hIRD, nCol+1,  
            SQL_CA_SS_COLUMN_ORDER,  
            (SQLPOINTER) &nOrderID, SQL_IS_INTEGER,  
            &cbIRD);  
  
        if (nOrderID != 0)  
            {  
            printf_s("Col in ORDER BY, pos: %ld",  
                nOrderID);  
            }  
            printf_s("\n");  
        }  
  
    printf_s("\n");  
    }  
else  
    {  
    PCOMPUTEBYLIST  pByList;  
    SQLSMALLINT     nBy;  
    SQLINTEGER      nColID;  
  
    printf_s("Computed result set number: %lu\n",  
        nSet);  
  
    SQLGetDescField(hIRD, 1, SQL_CA_SS_COMPUTE_BYLIST,  
        (SQLPOINTER) &pByList, SQL_IS_INTEGER,  
        &cbIRD);  
  
    if (pByList != NULL)  
        {  
        printf_s("Clause ordered by columns: ");  
        for (nBy = 0; nBy < pByList->nBys; )  
            {  
            printf_s("%u", pByList->aByList[nBy]);  
            nBy++;  
  
            if (nBy == pByList->nBys)  
                {  
                printf_s("\n");  
                }  
            else  
                {  
                printf_s(", ");  
                }  
            }  
        }  
    else  
        {  
        printf_s("Compute clause set not ordered.\n");  
        }  
  
    for (nCol = 0; nCol < nCols; nCol++)  
        {  
        SQLGetDescField(hIRD, nCol+1,  
            SQL_CA_SS_COLUMN_ID, (SQLPOINTER) &nColID,  
            SQL_IS_INTEGER, &cbIRD);  
        printf_s("ColumnID: %lu, nColID);  
        }  
    printf_s("\n");  
    }  
  
if (SQLMoreResults(g_hStmt) == SQL_SUCCESS)  
    {  
    // Determine the result set indicator.  
    SQLGetDescField(hIRD, 1, SQL_CA_SS_COMPUTE_ID,  
        (SQLPOINTER) &nSet, SQL_IS_INTEGER, &cbIRD);  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="42c99-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="42c99-123">See Also</span></span>  
 <span data-ttu-id="42c99-124">[Функция SQLGetDescField](https://go.microsoft.com/fwlink/?LinkId=59351) </span><span class="sxs-lookup"><span data-stu-id="42c99-124">[SQLGetDescField Function](https://go.microsoft.com/fwlink/?LinkId=59351) </span></span>  
 [<span data-ttu-id="42c99-125">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="42c99-125">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
