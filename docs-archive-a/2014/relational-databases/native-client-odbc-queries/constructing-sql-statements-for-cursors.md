---
title: Построение инструкций SQL для курсоров | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- cursors [ODBC], statement construction
- ODBC applications, cursors
- SQL Server Native Client ODBC driver, statements
- statements [ODBC], constructing
- ODBC applications, statements
- statements [ODBC], cursors
ms.assetid: 134003fd-9c93-4f5c-a988-045990933b80
author: rothja
ms.author: jroth
ms.openlocfilehash: b0fe0831b97c13c5d20067386f4e9d8c97ee19ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655131"
---
# <a name="constructing-sql-statements-for-cursors"></a><span data-ttu-id="e8d2c-102">Конструирование инструкций SQL для курсоров</span><span class="sxs-lookup"><span data-stu-id="e8d2c-102">Constructing SQL Statements for Cursors</span></span>
  <span data-ttu-id="e8d2c-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Драйвер ODBC для собственного клиента использует серверные курсоры для реализации функции курсора, определенной в спецификации ODBC.</span><span class="sxs-lookup"><span data-stu-id="e8d2c-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver uses server cursors to implement the cursor functionality defined in the ODBC specification.</span></span> <span data-ttu-id="e8d2c-104">Приложение ODBC управляет поведением курсора с помощью [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) для установки различных атрибутов операторов.</span><span class="sxs-lookup"><span data-stu-id="e8d2c-104">An ODBC application controls the cursor behavior by using [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) to set different statement attributes.</span></span> <span data-ttu-id="e8d2c-105">К ним относятся атрибуты и их значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e8d2c-105">These are the attributes and their defaults.</span></span>  
  
|<span data-ttu-id="e8d2c-106">attribute</span><span class="sxs-lookup"><span data-stu-id="e8d2c-106">Attribute</span></span>|<span data-ttu-id="e8d2c-107">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="e8d2c-107">Default</span></span>|  
|---------------|-------------|  
|<span data-ttu-id="e8d2c-108">SQL_ATTR_CONCURRENCY</span><span class="sxs-lookup"><span data-stu-id="e8d2c-108">SQL_ATTR_CONCURRENCY</span></span>|<span data-ttu-id="e8d2c-109">SQL_CONCUR_READ_ONLY</span><span class="sxs-lookup"><span data-stu-id="e8d2c-109">SQL_CONCUR_READ_ONLY</span></span>|  
|<span data-ttu-id="e8d2c-110">SQL_ATTR_CURSOR_TYPE</span><span class="sxs-lookup"><span data-stu-id="e8d2c-110">SQL_ATTR_CURSOR_TYPE</span></span>|<span data-ttu-id="e8d2c-111">SQL_CURSOR_FORWARD_ONLY</span><span class="sxs-lookup"><span data-stu-id="e8d2c-111">SQL_CURSOR_FORWARD_ONLY</span></span>|  
|<span data-ttu-id="e8d2c-112">SQL_ATTR_CURSOR_SCROLLABLE</span><span class="sxs-lookup"><span data-stu-id="e8d2c-112">SQL_ATTR_CURSOR_SCROLLABLE</span></span>|<span data-ttu-id="e8d2c-113">SQL_NONSCROLLABLE</span><span class="sxs-lookup"><span data-stu-id="e8d2c-113">SQL_NONSCROLLABLE</span></span>|  
|<span data-ttu-id="e8d2c-114">SQL_ATTR_CURSOR_SENSITIVITY</span><span class="sxs-lookup"><span data-stu-id="e8d2c-114">SQL_ATTR_CURSOR_SENSITIVITY</span></span>|<span data-ttu-id="e8d2c-115">SQL_UNSPECIFIED</span><span class="sxs-lookup"><span data-stu-id="e8d2c-115">SQL_UNSPECIFIED</span></span>|  
|<span data-ttu-id="e8d2c-116">SQL_ATTR_ROW_ARRAY_SIZE</span><span class="sxs-lookup"><span data-stu-id="e8d2c-116">SQL_ATTR_ROW_ARRAY_SIZE</span></span>|<span data-ttu-id="e8d2c-117">1</span><span class="sxs-lookup"><span data-stu-id="e8d2c-117">1</span></span>|  
  
 <span data-ttu-id="e8d2c-118">Если для этих параметров заданы значения по умолчанию во время выполнения инструкции SQL, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] драйвер ODBC для собственного клиента не использует серверный курсор для реализации результирующего набора; вместо этого он использует результирующий набор по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e8d2c-118">When these options are set to their defaults at the time an SQL statement is executed, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver does not use a server cursor to implement the result set; instead, it uses a default result set.</span></span> <span data-ttu-id="e8d2c-119">Если какой-либо из этих параметров изменяется со значений по умолчанию во время выполнения инструкции SQL, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] драйвер ODBC для собственного клиента пытается использовать серверный курсор для реализации результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="e8d2c-119">If any of these options are changed from their defaults at the time an SQL statement is executed, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver attempts to use a server cursor to implement the result set.</span></span>  
  
 <span data-ttu-id="e8d2c-120">Результирующие наборы по умолчанию поддерживают все инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e8d2c-120">Default result sets support all of the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="e8d2c-121">Ограничения на типы инструкций SQL, которые можно выполнять при использовании результирующего набора по умолчанию, отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="e8d2c-121">There are no restrictions on the types of SQL statements that can be executed when using a default result set.</span></span>  
  
 <span data-ttu-id="e8d2c-122">Серверные курсоры поддерживают не все инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e8d2c-122">Server cursors do not support all [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="e8d2c-123">Серверные курсоры не поддерживают любые инструкции SQL, формирующие множественные результирующие наборы.</span><span class="sxs-lookup"><span data-stu-id="e8d2c-123">Server cursors do not support any SQL statement that generates multiple result sets.</span></span>  
  
 <span data-ttu-id="e8d2c-124">Следующие типы инструкций не поддерживаются серверными курсорами.</span><span class="sxs-lookup"><span data-stu-id="e8d2c-124">The following types of statements are not supported by server cursors:</span></span>  
  
-   <span data-ttu-id="e8d2c-125">Пакеты</span><span class="sxs-lookup"><span data-stu-id="e8d2c-125">Batches</span></span>  
  
     <span data-ttu-id="e8d2c-126">Инструкции SQL, состоящие из двух и более отдельных инструкций SQL SELECT, например:</span><span class="sxs-lookup"><span data-stu-id="e8d2c-126">SQL statements built from two or more individual SQL SELECT statements, for example:</span></span>  
  
    ```  
    SELECT * FROM Authors; SELECT * FROM Titles  
    ```  
  
-   <span data-ttu-id="e8d2c-127">Хранимые процедуры с несколькими инструкциями SELECT</span><span class="sxs-lookup"><span data-stu-id="e8d2c-127">Stored procedures with multiple SELECT statements</span></span>  
  
     <span data-ttu-id="e8d2c-128">Инструкции SQL, которые выполняют хранимую процедуру, содержащую более одной инструкции SELECT.</span><span class="sxs-lookup"><span data-stu-id="e8d2c-128">SQL statements that execute a stored procedure containing more than one SELECT statement.</span></span> <span data-ttu-id="e8d2c-129">К ним относятся инструкции SELECT, которые заполняют параметры или переменные.</span><span class="sxs-lookup"><span data-stu-id="e8d2c-129">This includes SELECT statements that fill parameters or variables.</span></span>  
  
-   <span data-ttu-id="e8d2c-130">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e8d2c-130">Keywords</span></span>  
  
     <span data-ttu-id="e8d2c-131">Инструкции SQL, которые содержат ключевые слова FOR BROWSE или INTO.</span><span class="sxs-lookup"><span data-stu-id="e8d2c-131">SQL statements containing the keywords FOR BROWSE, or INTO.</span></span>  
  
 <span data-ttu-id="e8d2c-132">В [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]: если инструкция SQL, соответствующая любому из этих условий, выполняется с серверным курсором, то серверный курсор неявно преобразуется в результирующий набор по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e8d2c-132">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], if an SQL statement that matches any of these conditions is executed with a server cursor, the server cursor is implicitly converted to a default result set.</span></span> <span data-ttu-id="e8d2c-133">После того как **SQLExecDirect** или **SQLExecute** возвращает SQL_SUCCESS_WITH_INFO, для атрибутов курсора будут заданы значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e8d2c-133">After **SQLExecDirect** or **SQLExecute** returns SQL_SUCCESS_WITH_INFO, the cursor attributes will be set back to their default settings.</span></span>  
  
 <span data-ttu-id="e8d2c-134">Инструкции SQL, не относящиеся к перечисленным выше категориям, могут выполняться с любыми настройками атрибутов инструкций; они работают одинаково успешно с результирующим набором по умолчанию и с серверным курсором.</span><span class="sxs-lookup"><span data-stu-id="e8d2c-134">SQL statements that do not fit the categories above can be executed with any statement attribute settings; they work equally well with either a default result set or a server cursor.</span></span>  
  
## <a name="errors"></a><span data-ttu-id="e8d2c-135">ошибки</span><span class="sxs-lookup"><span data-stu-id="e8d2c-135">Errors</span></span>  
 <span data-ttu-id="e8d2c-136">В [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 7.0 и более поздних версиях попытка выполнить инструкцию, возвращающую несколько результирующих наборов, формирует SQL_SUCCESS_WITH_INFO и следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="e8d2c-136">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 7.0 and later, an attempt to execute a statement that produces multiple result sets generates SQL_SUCCESS_WITH INFO and the following message:</span></span>  
  
```  
SqlState: 01S02"  
pfNative: 0  
szErrorMsgString: "[Microsoft][SQL Server Native Client][SQL Server]  
               Cursor type changed."  
```  
  
 <span data-ttu-id="e8d2c-137">Приложения ODBC, получающие это сообщение, могут вызывать [SQLGetStmtAttr](../native-client-odbc-api/sqlgetstmtattr.md) для определения текущих параметров курсора.</span><span class="sxs-lookup"><span data-stu-id="e8d2c-137">ODBC applications receiving this message can call [SQLGetStmtAttr](../native-client-odbc-api/sqlgetstmtattr.md) to determine the current cursor settings.</span></span>  
  
 <span data-ttu-id="e8d2c-138">При попытке выполнить процедуру с несколькими инструкциями SELECT с использованием серверных курсоров формируется следующая ошибка:</span><span class="sxs-lookup"><span data-stu-id="e8d2c-138">An attempt to execute a procedure with multiple SELECT statements when using server cursors generates the following error:</span></span>  
  
```  
SqlState: 42000  
pfNative: 16937  
szErrorMsgString: [Microsoft][SQL Server Native Client][SQL Server]  
               A server cursor is not allowed on a stored procedure  
               with more than one SELECT statement in it. Use a  
               default result set or client cursor.  
```  
  
 <span data-ttu-id="e8d2c-139">При попытке выполнить пакет с несколькими инструкциями SELECT с использованием серверных курсоров формируется следующая ошибка:</span><span class="sxs-lookup"><span data-stu-id="e8d2c-139">An attempt to execute a batch with multiple SELECT statements when using server cursors generates the following error:</span></span>  
  
```  
SqlState: 42000  
pfNative: 16938  
szErrorMsgString: [Microsoft][SQL Server Native Client][SQL Server]  
               sp_cursoropen. The statement parameter can only  
               be a single SELECT statement or a single stored   
               procedure.  
```  
  
 <span data-ttu-id="e8d2c-140">Приложения ODBC, получающие эти ошибки, должны сбросить все атрибуты инструкции курсора в их значения по умолчанию перед попыткой выполнить инструкцию.</span><span class="sxs-lookup"><span data-stu-id="e8d2c-140">ODBC applications receiving these errors must reset all the cursor statement attributes to their defaults before attempting to execute the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8d2c-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="e8d2c-141">See Also</span></span>  
 [<span data-ttu-id="e8d2c-142">Выполняя запросы &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="e8d2c-142">Executing Queries &#40;ODBC&#41;</span></span>](executing-queries-odbc.md)  
  
  
