---
title: Использование курсоров (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, cursors
- ODBC cursors, about ODBC cursors
- ODBC applications, cursors
- cursors [ODBC]
- ODBC cursors
ms.assetid: 51322f92-0d76-44c9-9c33-9223676cf1d3
author: rothja
ms.author: jroth
ms.openlocfilehash: 61afedab4f4a1e309a08d9c2421ca7889811da8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739887"
---
# <a name="using-cursors-odbc"></a><span data-ttu-id="30fa0-102">Использование курсоров (ODBC)</span><span class="sxs-lookup"><span data-stu-id="30fa0-102">Using Cursors (ODBC)</span></span>
  <span data-ttu-id="30fa0-103">ODBC поддерживает модель курсора, которая позволяет следующее.</span><span class="sxs-lookup"><span data-stu-id="30fa0-103">ODBC supports a cursor model that allows:</span></span>  
  
-   <span data-ttu-id="30fa0-104">Несколько типов курсоров.</span><span class="sxs-lookup"><span data-stu-id="30fa0-104">Several types of cursors.</span></span>  
  
-   <span data-ttu-id="30fa0-105">Прокрутку и позиционирование в курсоре.</span><span class="sxs-lookup"><span data-stu-id="30fa0-105">Scrolling and positioning within a cursor.</span></span>  
  
-   <span data-ttu-id="30fa0-106">Несколько параметров параллелизма.</span><span class="sxs-lookup"><span data-stu-id="30fa0-106">Several concurrency options.</span></span>  
  
-   <span data-ttu-id="30fa0-107">Позиционированные обновления.</span><span class="sxs-lookup"><span data-stu-id="30fa0-107">Positioned updates.</span></span>  
  
 <span data-ttu-id="30fa0-108">Приложения ODBC редко декларируют и открывают курсоры или используют любые связанные с курсорами инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="30fa0-108">ODBC applications rarely declare and open cursors or use any cursor-related [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="30fa0-109">ODBC автоматически открывает курсор для каждого возвращенного результирующего набора из инструкции SQL.</span><span class="sxs-lookup"><span data-stu-id="30fa0-109">ODBC automatically opens a cursor for every result set returned from an SQL statement.</span></span> <span data-ttu-id="30fa0-110">Характеристики курсоров контролируются атрибутами инструкции, заданными с помощью [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) , перед выполнением инструкции SQL.</span><span class="sxs-lookup"><span data-stu-id="30fa0-110">The characteristics of the cursors are controlled by statement attributes set with [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) before the SQL statement is executed.</span></span> <span data-ttu-id="30fa0-111">Функции API ODBC для обработки результирующих наборов поддерживают полный набор функций работы с курсором, включая выборку, прокрутку и позиционированные обновления.</span><span class="sxs-lookup"><span data-stu-id="30fa0-111">The ODBC API functions for processing result sets support the full range of cursor functionality, including fetching, scrolling, and positioned updates.</span></span>  
  
 <span data-ttu-id="30fa0-112">Далее приведено сравнение работы с курсорами в скриптах [!INCLUDE[tsql](../../includes/tsql-md.md)] и приложениях ODBC.</span><span class="sxs-lookup"><span data-stu-id="30fa0-112">This is a comparison of how [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts and ODBC applications work with cursors.</span></span>  
  
|<span data-ttu-id="30fa0-113">Действие</span><span class="sxs-lookup"><span data-stu-id="30fa0-113">Action</span></span>|[!INCLUDE[tsql](../../includes/tsql-md.md)]|<span data-ttu-id="30fa0-114">ODBC</span><span class="sxs-lookup"><span data-stu-id="30fa0-114">ODBC</span></span>|  
|------------|------------------------|----------|  
|<span data-ttu-id="30fa0-115">Определение режима работы курсоров</span><span class="sxs-lookup"><span data-stu-id="30fa0-115">Define cursor behavior</span></span>|<span data-ttu-id="30fa0-116">Указание через параметры DECLARE CURSOR</span><span class="sxs-lookup"><span data-stu-id="30fa0-116">Specify through DECLARE CURSOR parameters</span></span>|<span data-ttu-id="30fa0-117">Установка атрибутов курсора с помощью [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md)</span><span class="sxs-lookup"><span data-stu-id="30fa0-117">Set cursor attributes by using [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md)</span></span>|  
|<span data-ttu-id="30fa0-118">Открытие курсора</span><span class="sxs-lookup"><span data-stu-id="30fa0-118">Open a cursor</span></span>|<span data-ttu-id="30fa0-119">ОБЪЯВЛЕНИЕ открытого КУРСОРа *cursor_name*</span><span class="sxs-lookup"><span data-stu-id="30fa0-119">DECLARE CURSOR OPEN *cursor_name*</span></span>|<span data-ttu-id="30fa0-120">**SQLExecDirect** или **SQLExecute**</span><span class="sxs-lookup"><span data-stu-id="30fa0-120">**SQLExecDirect** or **SQLExecute**</span></span>|  
|<span data-ttu-id="30fa0-121">Выборка строк</span><span class="sxs-lookup"><span data-stu-id="30fa0-121">Fetch rows</span></span>|<span data-ttu-id="30fa0-122">FETCH</span><span class="sxs-lookup"><span data-stu-id="30fa0-122">FETCH</span></span>|<span data-ttu-id="30fa0-123">**SQLFetch** или [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md)</span><span class="sxs-lookup"><span data-stu-id="30fa0-123">**SQLFetch** or [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md)</span></span>|  
|<span data-ttu-id="30fa0-124">Позиционированное обновление</span><span class="sxs-lookup"><span data-stu-id="30fa0-124">Positioned update</span></span>|<span data-ttu-id="30fa0-125">Предложение WHERE CURRENT OF для инструкции UPDATE или DELETE.</span><span class="sxs-lookup"><span data-stu-id="30fa0-125">WHERE CURRENT OF clause on UPDATE or DELETE</span></span>|<span data-ttu-id="30fa0-126">**функция SQLSetPos;**</span><span class="sxs-lookup"><span data-stu-id="30fa0-126">**SQLSetPos**</span></span>|  
|<span data-ttu-id="30fa0-127">Закрытие курсора</span><span class="sxs-lookup"><span data-stu-id="30fa0-127">Close a cursor</span></span>|<span data-ttu-id="30fa0-128">ЗАКРЫТЬ *CURSOR_NAME* освободить</span><span class="sxs-lookup"><span data-stu-id="30fa0-128">CLOSE *cursor_name* DEALLOCATE</span></span>|[<span data-ttu-id="30fa0-129">SQLCloseCursor</span><span class="sxs-lookup"><span data-stu-id="30fa0-129">SQLCloseCursor</span></span>](../native-client-odbc-api/sqlclosecursor.md)|  
  
 <span data-ttu-id="30fa0-130">Серверные курсоры, реализованные в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], поддерживают функции модели курсора ODBC.</span><span class="sxs-lookup"><span data-stu-id="30fa0-130">The server cursors implemented in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] support the functionality of the ODBC cursor model.</span></span> <span data-ttu-id="30fa0-131">Драйвер для собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] использует серверные курсоры для поддержки функций работы с курсорами API ODBC.</span><span class="sxs-lookup"><span data-stu-id="30fa0-131">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client driver uses server cursors to support the cursor functionality of the ODBC API.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="30fa0-132">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="30fa0-132">In This Section</span></span>  
  
-   [<span data-ttu-id="30fa0-133">Способы реализации курсоров</span><span class="sxs-lookup"><span data-stu-id="30fa0-133">How Cursors Are Implemented</span></span>](implementation/how-cursors-are-implemented.md)  
  
-   [<span data-ttu-id="30fa0-134">Типы курсоров</span><span class="sxs-lookup"><span data-stu-id="30fa0-134">Cursor Types</span></span>](cursor-types.md)  
  
-   [<span data-ttu-id="30fa0-135">Режимы работы курсоров</span><span class="sxs-lookup"><span data-stu-id="30fa0-135">Cursor Behaviors</span></span>](cursor-behaviors.md)  
  
-   [<span data-ttu-id="30fa0-136">Свойства курсора</span><span class="sxs-lookup"><span data-stu-id="30fa0-136">Cursor Properties</span></span>](properties/cursor-properties.md)  
  
-   [<span data-ttu-id="30fa0-137">Сведения о программировании курсора &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="30fa0-137">Cursor Programming Details &#40;ODBC&#41;</span></span>](programming/cursor-programming-details-odbc.md)  
  
-   [<span data-ttu-id="30fa0-138">Прокрутка и выборка строк</span><span class="sxs-lookup"><span data-stu-id="30fa0-138">Scrolling and Fetching Rows</span></span>](../native-client-ole-db-rowsets/fetching-rows.md)  
  
-   [<span data-ttu-id="30fa0-139">Позиционированные обновления &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="30fa0-139">Positioned Updates &#40;ODBC&#41;</span></span>](positioned-updates-odbc.md)  
  
## <a name="see-also"></a><span data-ttu-id="30fa0-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="30fa0-140">See Also</span></span>  
 <span data-ttu-id="30fa0-141">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="30fa0-141">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span></span>  
 <span data-ttu-id="30fa0-142">[ЗАКРЫТЬ &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/close-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="30fa0-142">[CLOSE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/close-transact-sql) </span></span>  
 <span data-ttu-id="30fa0-143">[Курсоры](../../relational-databases/cursors.md) </span><span class="sxs-lookup"><span data-stu-id="30fa0-143">[Cursors](../../relational-databases/cursors.md) </span></span>  
 <span data-ttu-id="30fa0-144">[ОСВОБОЖДЕНИЕ &#40;&#41;Transact-SQL](/sql/t-sql/language-elements/deallocate-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="30fa0-144">[DEALLOCATE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/deallocate-transact-sql) </span></span>  
 <span data-ttu-id="30fa0-145">[ОБЪЯВИТь курсор &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-cursor-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="30fa0-145">[DECLARE CURSOR &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-cursor-transact-sql) </span></span>  
 <span data-ttu-id="30fa0-146">[FETCH (Transact-SQL)](/sql/t-sql/language-elements/fetch-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="30fa0-146">[FETCH &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/fetch-transact-sql) </span></span>  
 [<span data-ttu-id="30fa0-147">OPEN (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="30fa0-147">OPEN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/open-transact-sql)  
  
  
