---
title: Параметры привязки | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, parameters
- parameters [SQL Server Native Client], ODBC
- statements [ODBC], parameters
- binding parameters [SQL Server Native Client]
- parameter markers [ODBC]
- unbound parameter markers
- SQLBindParameter function
- ODBC applications, parameters
- bound parameter markers [SQL Server Native Client]
ms.assetid: d6c69739-8f89-475f-a60a-b2f6c06576e2
author: rothja
ms.author: jroth
ms.openlocfilehash: 3402a7efce43d0ce94a20c93504ac1dcb2c7b48f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655112"
---
# <a name="binding-parameters"></a><span data-ttu-id="ba1ce-102">Привязка параметров</span><span class="sxs-lookup"><span data-stu-id="ba1ce-102">Binding Parameters</span></span>
  <span data-ttu-id="ba1ce-103">Каждый маркер параметра в инструкции SQL должен быть сопоставлен переменной в приложении (привязан к ней), прежде чем можно выполнить инструкцию.</span><span class="sxs-lookup"><span data-stu-id="ba1ce-103">Each parameter marker in an SQL statement must be associated, or bound, to a variable in the application before the statement can be executed.</span></span> <span data-ttu-id="ba1ce-104">Это делается путем вызова функции [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) .</span><span class="sxs-lookup"><span data-stu-id="ba1ce-104">This is done by calling the [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) function.</span></span> <span data-ttu-id="ba1ce-105">**SQLBindParameter** описывает переменную программы (адрес, тип данных C и т. д.) для драйвера.</span><span class="sxs-lookup"><span data-stu-id="ba1ce-105">**SQLBindParameter** describes the program variable (address, C data type, and so on) to the driver.</span></span> <span data-ttu-id="ba1ce-106">Она также определяет маркер параметра, указывая его порядковое значение, а затем описывая характеристики представляемого им объекта SQL (тип данных SQL, точность и т. д.).</span><span class="sxs-lookup"><span data-stu-id="ba1ce-106">It also identifies the parameter marker by indicating its ordinal value and then describes the characteristics of the SQL object it represents (SQL data type, precision, and so on).</span></span>

 <span data-ttu-id="ba1ce-107">Маркеры параметров могут быть привязаны или повторно привязаны в любое время перед выполнением инструкции.</span><span class="sxs-lookup"><span data-stu-id="ba1ce-107">Parameter markers can be bound or rebound at any time before a statement is executed.</span></span> <span data-ttu-id="ba1ce-108">Привязка параметра действует до тех пор, пока не происходит одно из следующих событий.</span><span class="sxs-lookup"><span data-stu-id="ba1ce-108">A parameter binding remains in effect until one of the following occurs:</span></span>

-   <span data-ttu-id="ba1ce-109">Вызов [SQLFreeStmt](../native-client-odbc-api/sqlfreestmt.md) с параметром *Option* , равным SQL_RESET_PARAMS освобождает все параметры, привязанные к маркеру инструкции.</span><span class="sxs-lookup"><span data-stu-id="ba1ce-109">A call to [SQLFreeStmt](../native-client-odbc-api/sqlfreestmt.md) with the *Option* parameter set to SQL_RESET_PARAMS frees all parameters bound to the statement handle.</span></span>

-   <span data-ttu-id="ba1ce-110">Вызов **SQLBindParameter** с *параметернумбер* , равным порядковому номеру привязанного параметра, автоматически освобождает предыдущую привязку.</span><span class="sxs-lookup"><span data-stu-id="ba1ce-110">A call to **SQLBindParameter** with *ParameterNumber* set to the ordinal of a bound parameter marker automatically releases the previous binding.</span></span>

 <span data-ttu-id="ba1ce-111">Приложение также может привязать параметры к массивам переменных программы для пакетной обработки инструкции SQL.</span><span class="sxs-lookup"><span data-stu-id="ba1ce-111">An application can also bind parameters to arrays of program variables to process an SQL statement in batches.</span></span> <span data-ttu-id="ba1ce-112">Существует два типа привязки массивов.</span><span class="sxs-lookup"><span data-stu-id="ba1ce-112">There are two types of array binding:</span></span>

-   <span data-ttu-id="ba1ce-113">Привязка на уровне столбца выполняется, если каждый отдельный параметр привязан к собственному массиву переменных.</span><span class="sxs-lookup"><span data-stu-id="ba1ce-113">Column-wise binding is done when each individual parameter is bound to its own array of variables.</span></span>

     <span data-ttu-id="ba1ce-114">Привязка на уровне столбца задается путем вызова [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) с *атрибутом* , для которого задано значение SQL_ATTR_PARAM_BIND_TYPE, а *ValuePtr* — значение SQL_PARAM_BIND_BY_COLUMN.</span><span class="sxs-lookup"><span data-stu-id="ba1ce-114">Column-wise binding is specified by calling [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) with *Attribute* set to SQL_ATTR_PARAM_BIND_TYPE and *ValuePtr* set to SQL_PARAM_BIND_BY_COLUMN.</span></span>

-   <span data-ttu-id="ba1ce-115">Привязка на уровне строки выполняется, если все параметры в инструкции SQL привязаны в виде блока к массиву структур, которые содержат отдельные переменные для параметров.</span><span class="sxs-lookup"><span data-stu-id="ba1ce-115">Row-wise binding is done when all of the parameters in the SQL statement are bound as a unit to an array of structures that contain the individual variables for the parameters.</span></span>

     <span data-ttu-id="ba1ce-116">Привязка на уровне строки задается путем вызова **SQLSetStmtAttr** с *атрибутом* , для которого задано значение SQL_ATTR_PARAM_BIND_TYPE, а *ValuePtr* задает размер структуры, содержащей переменные программы.</span><span class="sxs-lookup"><span data-stu-id="ba1ce-116">Row-wise binding is specified by calling **SQLSetStmtAttr** with *Attribute* set to SQL_ATTR_PARAM_BIND_TYPE and *ValuePtr* set to the size of the structure holding the program variables.</span></span>

 <span data-ttu-id="ba1ce-117">Когда [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] драйвер ODBC для собственного клиента отправляет на сервер символьные или двоичные строковые параметры, он дополняет значения длиной, указанной в параметре *ColumnSize* **SQLBindParameter** .</span><span class="sxs-lookup"><span data-stu-id="ba1ce-117">When the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver sends character or binary string parameters to the server, it pads the values to the length specified in **SQLBindParameter** *ColumnSize* parameter.</span></span> <span data-ttu-id="ba1ce-118">Если приложение ODBC 2. x указывает 0 для *ColumnSize*, драйвер устанавливает значение параметра в точность типа данных.</span><span class="sxs-lookup"><span data-stu-id="ba1ce-118">If an ODBC 2.x application specifies 0 for *ColumnSize*, the driver pads the parameter value to the precision of the data type.</span></span> <span data-ttu-id="ba1ce-119">Точность равна 8000 при соединении с сервером [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и 255 при соединении с предыдущими версиями [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ba1ce-119">The precision is 8000 when connected to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] servers, 255 when connected to earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ba1ce-120">*ColumnSize* находится в байтах для столбцов типа Variant.</span><span class="sxs-lookup"><span data-stu-id="ba1ce-120">*ColumnSize* is in bytes for variant columns.</span></span>

 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ba1ce-121">поддерживает определение имен для параметров хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="ba1ce-121">supports defining names for stored procedure parameters.</span></span> <span data-ttu-id="ba1ce-122">В ODBC 3.5 также появилась поддержка именованных параметров, используемых при вызове хранимых процедур [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ba1ce-122">ODBC 3.5 also introduced support for named parameters used when calling [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures.</span></span> <span data-ttu-id="ba1ce-123">Эта поддержка может использоваться для следующих действий.</span><span class="sxs-lookup"><span data-stu-id="ba1ce-123">This support can be used to:</span></span>

-   <span data-ttu-id="ba1ce-124">Вызов хранимой процедуры и предоставление значений для подмножества параметров, заданных для хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="ba1ce-124">Call a stored procedure and provide values for a subset of the parameters defined for the stored procedure.</span></span>

-   <span data-ttu-id="ba1ce-125">Указание параметров в приложении не в той последовательности, в какой они были заданы при создании хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="ba1ce-125">Specify the parameters in a different order in the application than the order specified when the stored procedure was created.</span></span>

 <span data-ttu-id="ba1ce-126">Именованные параметры поддерживаются только при использовании [!INCLUDE[tsql](../../includes/tsql-md.md)] `EXECUTE` инструкции или escape-последовательности ODBC CALL для выполнения хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="ba1ce-126">Named parameters are only supported when using the [!INCLUDE[tsql](../../includes/tsql-md.md)] `EXECUTE` statement or the ODBC CALL escape sequence to execute a stored procedure.</span></span>

 <span data-ttu-id="ba1ce-127">Если значение `SQL_DESC_NAME` задано для параметра хранимой процедуры, остальные параметры хранимой процедуры также должны иметь значение `SQL_DESC_NAME`.</span><span class="sxs-lookup"><span data-stu-id="ba1ce-127">If `SQL_DESC_NAME` is set for a stored procedure parameter, all stored procedure parameters in the query should also set `SQL_DESC_NAME`.</span></span>  <span data-ttu-id="ba1ce-128">Если литералы используются в вызовах хранимых процедур, где `SQL_DESC_NAME` заданы параметры, литералы должны использовать формат *"имя* = *значение*", где *Name* — имя параметра хранимой процедуры (например, @p1 ).</span><span class="sxs-lookup"><span data-stu-id="ba1ce-128">If literals are used in stored procedure calls, where parameters have `SQL_DESC_NAME` set, the literals should use the format *'name*=*value*', where *name* is the stored procedure parameter name (for example, @p1).</span></span> <span data-ttu-id="ba1ce-129">Дополнительные сведения см. в разделе [Привязка параметров по имени (именованные параметры)](https://go.microsoft.com/fwlink/?LinkId=167215).</span><span class="sxs-lookup"><span data-stu-id="ba1ce-129">For more information, see [Binding Parameters by Name (Named Parameters)](https://go.microsoft.com/fwlink/?LinkId=167215).</span></span>

## <a name="see-also"></a><span data-ttu-id="ba1ce-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="ba1ce-130">See Also</span></span>
 [<span data-ttu-id="ba1ce-131">Использование параметров инструкции</span><span class="sxs-lookup"><span data-stu-id="ba1ce-131">Using Statement Parameters</span></span>](using-statement-parameters.md)


