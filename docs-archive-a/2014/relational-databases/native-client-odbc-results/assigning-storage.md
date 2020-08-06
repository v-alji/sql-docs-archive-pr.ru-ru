---
title: Назначение хранилища | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- column-wise binding [ODBC]
- SQL Server Native Client ODBC driver, result sets
- ODBC applications, result sets
- SQLBindCol function
- storing data [ODBC]
- result sets [ODBC], storage
- SQL Server Native Client ODBC driver, data storage
- row-wise binding
- binding result sets [SQL Server Native Client]
- array binding
ms.assetid: 11c81955-5300-495f-925f-9256f2587b58
author: rothja
ms.author: jroth
ms.openlocfilehash: ada18c91493d91b36ced51bf84c32513a0c5f5df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666536"
---
# <a name="assigning-storage"></a><span data-ttu-id="517be-102">Назначение хранилища</span><span class="sxs-lookup"><span data-stu-id="517be-102">Assigning Storage</span></span>
  <span data-ttu-id="517be-103">Приложение может назначить хранилище для результатов перед выполнением инструкции SQL или после него.</span><span class="sxs-lookup"><span data-stu-id="517be-103">An application can assign storage for results before or after it executes a SQL statement.</span></span> <span data-ttu-id="517be-104">Если приложение сначала подготавливает или выполняет инструкцию SQL, оно может запросить о результирующем наборе перед назначением хранилища для результатов.</span><span class="sxs-lookup"><span data-stu-id="517be-104">If an application prepares or executes the SQL statement first, it can inquire about the result set before it assigns storage for results.</span></span> <span data-ttu-id="517be-105">Например, если результирующий набор неизвестен, приложение должно получить количество столбцов, прежде чем им можно будет назначить хранилище.</span><span class="sxs-lookup"><span data-stu-id="517be-105">For example, if the result set is unknown, the application must retrieve the number of columns before it can assign storage for them.</span></span>  
  
 <span data-ttu-id="517be-106">Чтобы связать хранилище для столбца данных, приложение вызывает [SQLBindCol](../native-client-odbc-api/sqlbindcol.md)и передает его:</span><span class="sxs-lookup"><span data-stu-id="517be-106">To associate storage for a column of data, an application calls [SQLBindCol](../native-client-odbc-api/sqlbindcol.md)and passes it:</span></span>  
  
-   <span data-ttu-id="517be-107">Тип данных, в который будут преобразованы данные.</span><span class="sxs-lookup"><span data-stu-id="517be-107">The data type to which the data is to be converted.</span></span>  
  
-   <span data-ttu-id="517be-108">Адрес выходного буфера для данных.</span><span class="sxs-lookup"><span data-stu-id="517be-108">The address of an output buffer for the data.</span></span>  
  
     <span data-ttu-id="517be-109">Приложение должно выделить этот буфер, причем буфер должен иметь достаточный размер для данных в той форме, в которую они будут преобразованы.</span><span class="sxs-lookup"><span data-stu-id="517be-109">The application must allocate this buffer, and it must be large enough to hold the data in the form to which it is converted.</span></span>  
  
-   <span data-ttu-id="517be-110">Длину выходного буфера.</span><span class="sxs-lookup"><span data-stu-id="517be-110">The length of the output buffer.</span></span>  
  
     <span data-ttu-id="517be-111">Это значение пропускается, если возвращаемые данные имеют фиксированную длину в C, например целое число, вещественное число или структура данных.</span><span class="sxs-lookup"><span data-stu-id="517be-111">This value is ignored if the returned data has a fixed width in C, such as an integer, real number, or date structure.</span></span>  
  
-   <span data-ttu-id="517be-112">Адрес буфера хранения, в который возвращается определенное число байтов доступных данных.</span><span class="sxs-lookup"><span data-stu-id="517be-112">The address of a storage buffer in which to return the number of bytes of available data.</span></span>  
  
 <span data-ttu-id="517be-113">Приложение также может привязать столбцы результирующего набора к массивам переменных программы, обеспечивая поддержку получения строк результирующего набора поблочно.</span><span class="sxs-lookup"><span data-stu-id="517be-113">An application can also bind result set columns to arrays of program variables to support fetching result set rows in blocks.</span></span> <span data-ttu-id="517be-114">Существуют два различных типа привязки массивов.</span><span class="sxs-lookup"><span data-stu-id="517be-114">There are two different types of array binding:</span></span>  
  
-   <span data-ttu-id="517be-115">Привязка на уровне столбца завершается, когда каждый столбец привязан к собственному массиву переменных.</span><span class="sxs-lookup"><span data-stu-id="517be-115">Column-wise binding is finished when each column is bound to its own array of variables.</span></span>  
  
     <span data-ttu-id="517be-116">Привязка на уровне столбца задается путем вызова [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) с *атрибутом* , для которого задано значение SQL_ATTR_ROW_BIND_TYPE, а *ValuePtr* — значение SQL_BIND_BY_COLUMN.</span><span class="sxs-lookup"><span data-stu-id="517be-116">Column-wise binding is specified by calling [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) with *Attribute* set to SQL_ATTR_ROW_BIND_TYPE and *ValuePtr* set to SQL_BIND_BY_COLUMN.</span></span> <span data-ttu-id="517be-117">Все массивы должны содержать одинаковое количество элементов.</span><span class="sxs-lookup"><span data-stu-id="517be-117">All the arrays must have the same number of elements.</span></span>  
  
-   <span data-ttu-id="517be-118">Привязка на уровне строки завершается, когда все параметры в инструкции SQL привязаны как единое целое к массиву структур, которые содержат отдельные переменные для параметров.</span><span class="sxs-lookup"><span data-stu-id="517be-118">Row-wise binding is finished when all the parameters in the SQL statement are bound as a unit to an array of structures that contain the individual variables for the parameters.</span></span>  
  
     <span data-ttu-id="517be-119">Привязка на уровне строки задается путем вызова **SQLSetStmtAttr** с *атрибутом* , имеющим значение SQL_ATTR_ROW_BIND_TYPE, а *ValuePtr* задает размер структуры, содержащей переменные, которые будут принимать столбцы результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="517be-119">Row-wise binding is specified by calling **SQLSetStmtAttr** with *Attribute* set to SQL_ATTR_ROW_BIND_TYPE and *ValuePtr* set to the size of the structure holding the variables that will receive the result set columns.</span></span>  
  
 <span data-ttu-id="517be-120">Приложение также указывает для атрибута SQL_ATTR_ROW_ARRAY_SIZE значение, равное количеству элементов в массивах столбцов или строк, и устанавливает значения SQL_ATTR_ROW_STATUS_PTR и SQL_ATTR_ROWS_FETCHED_PTR.</span><span class="sxs-lookup"><span data-stu-id="517be-120">The application also sets SQL_ATTR_ROW_ARRAY_SIZE to the number of elements in the column or row arrays and sets SQL_ATTR_ROW_STATUS_PTR and SQL_ATTR_ROWS_FETCHED_PTR.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="517be-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="517be-121">See Also</span></span>  
 [<span data-ttu-id="517be-122">Обработка результатов &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="517be-122">Processing Results &#40;ODBC&#41;</span></span>](processing-results-odbc.md)  
  
  
