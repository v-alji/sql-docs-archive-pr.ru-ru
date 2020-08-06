---
title: Использовать привязку наборов строк (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- rowset binding [ODBC]
ms.assetid: a7be05f0-6b11-4b53-9fbc-501e591eef09
author: rothja
ms.author: jroth
ms.openlocfilehash: e2e0671fd1140e72005cd1a7532ea581f077382f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654238"
---
# <a name="use-rowset-binding-odbc"></a><span data-ttu-id="80f0c-102">Использование привязки наборов строк (ODBC)</span><span class="sxs-lookup"><span data-stu-id="80f0c-102">Use Rowset Binding (ODBC)</span></span>
    
### <a name="to-use-column-wise-binding"></a><span data-ttu-id="80f0c-103">Использование привязки на уровне столбца</span><span class="sxs-lookup"><span data-stu-id="80f0c-103">To use column-wise binding</span></span>  
  
1.  <span data-ttu-id="80f0c-104">Для каждого привязанного столбца выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="80f0c-104">For each bound column, do the following:</span></span>  
  
    -   <span data-ttu-id="80f0c-105">Выделите массив из R (или больше) буферов столбцов для хранения значений данных, где R — это число строк в наборе строк.</span><span class="sxs-lookup"><span data-stu-id="80f0c-105">Allocate an array of R (or more) column buffers to store data values, where R is number of rows in the rowset.</span></span>  
  
    -   <span data-ttu-id="80f0c-106">При необходимости выделите массив из R (или больше) буферов столбцов для хранения длин данных.</span><span class="sxs-lookup"><span data-stu-id="80f0c-106">Optionally, allocate an array of R (or more) column buffers to store data lengths.</span></span>  
  
    -   <span data-ttu-id="80f0c-107">Вызовите [SQLBindCol](../../native-client-odbc-api/sqlbindcol.md) , чтобы связать значение данных столбца и массивы длин данных со столбцом набора строк.</span><span class="sxs-lookup"><span data-stu-id="80f0c-107">Call [SQLBindCol](../../native-client-odbc-api/sqlbindcol.md) to bind the column's data value and data length arrays to the column of the rowset.</span></span>  
  
2.  <span data-ttu-id="80f0c-108">Вызовите функцию [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) , чтобы задать следующие атрибуты.</span><span class="sxs-lookup"><span data-stu-id="80f0c-108">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the following attributes:</span></span>  
  
    -   <span data-ttu-id="80f0c-109">Задайте число строк в наборе строк (R) в атрибуте SQL_ATTR_ROW_ARRAY_SIZE.</span><span class="sxs-lookup"><span data-stu-id="80f0c-109">Set SQL_ATTR_ROW_ARRAY_SIZE to the number of rows in the rowset (R).</span></span>  
  
    -   <span data-ttu-id="80f0c-110">Задайте значение SQL_ATTR_ROW_BIND_TYPE, равное SQL_BIND_BY_COLUMN.</span><span class="sxs-lookup"><span data-stu-id="80f0c-110">Set SQL_ATTR_ROW_BIND_TYPE to SQL_BIND_BY_COLUMN.</span></span>  
  
    -   <span data-ttu-id="80f0c-111">Задайте значение атрибута SQL_ATTR_ROWS_FETCHED_PTR, которое указывает на переменную SQLUINTEGER, предназначенную для хранения количества извлеченных строк.</span><span class="sxs-lookup"><span data-stu-id="80f0c-111">Set the SQL_ATTR_ROWS FETCHED_PTR attribute to point to a SQLUINTEGER variable to hold the number of rows fetched.</span></span>  
  
    -   <span data-ttu-id="80f0c-112">Задайте значение SQL_ATTR_ROW_STATUS_PTR, которое указывает на массив array[R] переменных SQLUSSMALLINT, в котором будут храниться признаки состояния строк.</span><span class="sxs-lookup"><span data-stu-id="80f0c-112">Set SQL_ATTR_ROW_STATUS_PTR to point to an array[R] of SQLUSSMALLINT variables to hold the row-status indicators.</span></span>  
  
3.  <span data-ttu-id="80f0c-113">Выполните инструкцию.</span><span class="sxs-lookup"><span data-stu-id="80f0c-113">Execute the statement.</span></span>  
  
4.  <span data-ttu-id="80f0c-114">При каждом вызове функции [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) или [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md) происходит получение числа строк, равного R, и передача данных в привязанные столбцы.</span><span class="sxs-lookup"><span data-stu-id="80f0c-114">Each call to [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) or [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md) retrieves R rows and transfers the data into the bound columns.</span></span>  
  
### <a name="to-use-row-wise-binding"></a><span data-ttu-id="80f0c-115">Использование привязки на уровне строки</span><span class="sxs-lookup"><span data-stu-id="80f0c-115">To use row-wise binding</span></span>  
  
1.  <span data-ttu-id="80f0c-116">Выделите массив array[R] структур, где R — это число строк в наборе строк.</span><span class="sxs-lookup"><span data-stu-id="80f0c-116">Allocate an array[R] of structures, where R is the number of rows in the rowset.</span></span> <span data-ttu-id="80f0c-117">Структура должна иметь по одному элементу для каждого столбца, а каждый элемент должен состоять из двух частей:</span><span class="sxs-lookup"><span data-stu-id="80f0c-117">The structure has one element for each column, and each element has two parts:</span></span>  
  
    -   <span data-ttu-id="80f0c-118">первая часть — это переменная подходящего типа данных, в которой будут храниться данные столбца;</span><span class="sxs-lookup"><span data-stu-id="80f0c-118">The first part is a variable of the appropriate data type to hold the column data.</span></span>  
  
    -   <span data-ttu-id="80f0c-119">вторая часть — это переменная SQLINTEGER, в которой будет храниться признак состояния столбца.</span><span class="sxs-lookup"><span data-stu-id="80f0c-119">The second part is a SQLINTEGER variable to hold the column status indicator.</span></span>  
  
2.  <span data-ttu-id="80f0c-120">Вызовите функцию [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) , чтобы задать следующие атрибуты.</span><span class="sxs-lookup"><span data-stu-id="80f0c-120">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the following attributes:</span></span>  
  
    -   <span data-ttu-id="80f0c-121">Задайте число строк в наборе строк (R) в атрибуте SQL_ATTR_ROW_ARRAY_SIZE.</span><span class="sxs-lookup"><span data-stu-id="80f0c-121">Set SQL_ATTR_ROW_ARRAY_SIZE to the number of rows in the rowset (R).</span></span>  
  
    -   <span data-ttu-id="80f0c-122">В атрибуте SQL_ATTR_ROW_BIND_TYPE задайте размер структуры, выделенной в шаге 1.</span><span class="sxs-lookup"><span data-stu-id="80f0c-122">Set SQL_ATTR_ROW_BIND_TYPE to the size of the structure allocated in Step 1.</span></span>  
  
    -   <span data-ttu-id="80f0c-123">Задайте значение атрибута SQL_ATTR_ROWS_FETCHED_PTR, которое указывает на переменную SQLUINTEGER, предназначенную для хранения количества извлеченных строк.</span><span class="sxs-lookup"><span data-stu-id="80f0c-123">Set the SQL_ATTR_ROWS_FETCHED_PTR attribute to point to a SQLUINTEGER variable to hold the number of rows fetched.</span></span>  
  
    -   <span data-ttu-id="80f0c-124">В атрибуте SQL_ATTR_PARAMS_STATUS_PTR задайте указатель на массив array[R] из переменных SQLUSSMALLINT, в котором будут храниться признаки состояния строк.</span><span class="sxs-lookup"><span data-stu-id="80f0c-124">Set SQL_ATTR_PARAMS_STATUS_PTR to point to an array[R] of SQLUSSMALLINT variables to hold the row-status indicators.</span></span>  
  
3.  <span data-ttu-id="80f0c-125">Для каждого столбца из результирующего набора вызовите функцию [SQLBindCol](../../native-client-odbc-api/sqlbindcol.md) , чтобы связать значение данных и указатель на длину данных столбца с соответствующими им переменными в первом элементе массива структур, выделенных в шаге 1.</span><span class="sxs-lookup"><span data-stu-id="80f0c-125">For each column in the result set, call [SQLBindCol](../../native-client-odbc-api/sqlbindcol.md) to point the data value and data length pointer of the column to their variables in the first element of the array of structures allocated in Step 1.</span></span>  
  
4.  <span data-ttu-id="80f0c-126">Выполните инструкцию.</span><span class="sxs-lookup"><span data-stu-id="80f0c-126">Execute the statement.</span></span>  
  
5.  <span data-ttu-id="80f0c-127">При каждом вызове функции [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) или [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md) происходит получение числа строк, равного R, и передача данных в привязанные столбцы.</span><span class="sxs-lookup"><span data-stu-id="80f0c-127">Each call to [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) or [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md) retrieves R rows and transfers the data into the bound columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80f0c-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="80f0c-128">See Also</span></span>  
 <span data-ttu-id="80f0c-129">[Инструкции по использованию курсоров &#40;ODBC&#41;](using-cursors-how-to-topics-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="80f0c-129">[Using Cursors How-to Topics &#40;ODBC&#41;](using-cursors-how-to-topics-odbc.md) </span></span>  
 <span data-ttu-id="80f0c-130">[Как реализуются курсоры](../../native-client-odbc-cursors/implementation/how-cursors-are-implemented.md) </span><span class="sxs-lookup"><span data-stu-id="80f0c-130">[How Cursors Are Implemented](../../native-client-odbc-cursors/implementation/how-cursors-are-implemented.md) </span></span>  
 [<span data-ttu-id="80f0c-131">Использование курсоров &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="80f0c-131">Use Cursors &#40;ODBC&#41;</span></span>](use-cursors-odbc.md)  
  
  
