---
title: Прокрутка и выборка строк | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- scrollable cursors [SQL Server]
- SQL Server Native Client ODBC driver, cursors
- SQLFetchScroll function
- ODBC applications, cursors
- cursors [ODBC], fetching rows
- ODBC cursors, fetching rows
- cursors [ODBC], scrolling rows
- fetching [ODBC]
- ODBC cursors, scrolling rows
ms.assetid: 9109f10d-326b-4a6d-8c97-831f60da8c4c
author: rothja
ms.author: jroth
ms.openlocfilehash: 97586f82ddddb79581b0f9c027aa60d7822b472c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739899"
---
# <a name="scrolling-and-fetching-rows"></a><span data-ttu-id="1ed3c-102">Прокрутка и выборка строк</span><span class="sxs-lookup"><span data-stu-id="1ed3c-102">Scrolling and Fetching Rows</span></span>
  <span data-ttu-id="1ed3c-103">Чтобы можно было использовать прокручиваемый курсор в приложение ODBC, необходимо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="1ed3c-103">To use a scrollable cursor, an ODBC application must:</span></span>  
  
-   <span data-ttu-id="1ed3c-104">Установите возможности курсора с помощью [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="1ed3c-104">Set the cursor capabilities using [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md).</span></span>  
  
-   <span data-ttu-id="1ed3c-105">Откройте курсор с помощью **SQLExecute** или **SQLExecDirect**.</span><span class="sxs-lookup"><span data-stu-id="1ed3c-105">Open the cursor using **SQLExecute** or **SQLExecDirect**.</span></span>  
  
-   <span data-ttu-id="1ed3c-106">Прокрутите и извлеките строки с помощью **SQLFetch** или [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md).</span><span class="sxs-lookup"><span data-stu-id="1ed3c-106">Scroll and fetch rows using **SQLFetch** or [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md).</span></span>  
  
 <span data-ttu-id="1ed3c-107">Одновременно **SQLFetch** и **склфетчсролл** могут получать блоки строк за раз.</span><span class="sxs-lookup"><span data-stu-id="1ed3c-107">Both **SQLFetch** and **SQLFetchSroll** can fetch blocks of rows at a time.</span></span> <span data-ttu-id="1ed3c-108">Число возвращаемых строк задается с помощью **SQLSetStmtAttr** для установки параметра SQL_ATTR_ROW_ARRAY_SIZE.</span><span class="sxs-lookup"><span data-stu-id="1ed3c-108">The number of rows returned is specified by using **SQLSetStmtAttr** to set the SQL_ATTR_ROW_ARRAY_SIZE parameter.</span></span>  
  
 <span data-ttu-id="1ed3c-109">Приложения ODBC могут использовать **SQLFetch** для выборки однопроходного курсора.</span><span class="sxs-lookup"><span data-stu-id="1ed3c-109">ODBC applications can use **SQLFetch** to fetch through a forward-only cursor.</span></span>  
  
 <span data-ttu-id="1ed3c-110">**SQLFetchScroll** используется для прокрутки курсора.</span><span class="sxs-lookup"><span data-stu-id="1ed3c-110">**SQLFetchScroll** is used to scroll around a cursor.</span></span> <span data-ttu-id="1ed3c-111">**SQLFetchScroll** поддерживает выборку следующих, предыдущих, первых и последних наборов строк в дополнение к относительным выборам (получение строк набора строк *n* из начала текущего набора строк) и абсолютная выборка (выборка набора строк, начиная со строки *n*).</span><span class="sxs-lookup"><span data-stu-id="1ed3c-111">**SQLFetchScroll** supports fetching the next, prior, first, and last rowsets in addition to relative fetching (fetch the rowset *n* rows from the start of the current rowset) and absolute fetching (fetch the rowset starting at row *n*).</span></span> <span data-ttu-id="1ed3c-112">Если *n* является отрицательным в абсолютной выборки, строки учитываются с конца результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="1ed3c-112">If *n* is negative in an absolute fetch, rows are counted from the end of the result set.</span></span> <span data-ttu-id="1ed3c-113">Абсолютная выборка строки -1 означает, что будет возвращен набор строк, начинающийся с последней строки результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="1ed3c-113">An absolute fetch of row -1 means to fetch the rowset that starts with the last row in the result set.</span></span>  
  
 <span data-ttu-id="1ed3c-114">Приложения, использующие **SQLFetchScroll** только для возможностей блочных курсоров, таких как отчеты, скорее всего, будут проходить через результирующий набор один раз, используя только параметр для выборки следующего набора строк.</span><span class="sxs-lookup"><span data-stu-id="1ed3c-114">Applications that use **SQLFetchScroll** only for its block cursor capabilities, such as reports, are likely to pass through the result set a single time, using only the option to fetch the next rowset.</span></span> <span data-ttu-id="1ed3c-115">С другой стороны, приложения на основе экрана могут воспользоваться всеми возможностями **SQLFetchScroll**.</span><span class="sxs-lookup"><span data-stu-id="1ed3c-115">Screen-based applications, on the other hand, can take advantage of all the capabilities of **SQLFetchScroll**.</span></span> <span data-ttu-id="1ed3c-116">Если приложение устанавливает размер набора строк равным количеству строк, отображаемым на экране, и привязывает буферы экрана к результирующему набору, он может перевести операции полосы прокрутки непосредственно в вызовы **SQLFetchScroll**.</span><span class="sxs-lookup"><span data-stu-id="1ed3c-116">If the application sets the rowset size to the number of rows displayed on the screen and binds the screen buffers to the result set, it can translate scroll bar operations directly to calls to **SQLFetchScroll**.</span></span>  
  
|<span data-ttu-id="1ed3c-117">Операция полосы прокрутки</span><span class="sxs-lookup"><span data-stu-id="1ed3c-117">Scroll bar operation</span></span>|<span data-ttu-id="1ed3c-118">Параметр прокрутки SQLFetchScroll</span><span class="sxs-lookup"><span data-stu-id="1ed3c-118">SQLFetchScroll scrolling option</span></span>|  
|--------------------------|-------------------------------------|  
|<span data-ttu-id="1ed3c-119">На страницу вверх</span><span class="sxs-lookup"><span data-stu-id="1ed3c-119">Page up</span></span>|<span data-ttu-id="1ed3c-120">SQL_FETCH_PRIOR</span><span class="sxs-lookup"><span data-stu-id="1ed3c-120">SQL_FETCH_PRIOR</span></span>|  
|<span data-ttu-id="1ed3c-121">На страницу вниз</span><span class="sxs-lookup"><span data-stu-id="1ed3c-121">Page down</span></span>|<span data-ttu-id="1ed3c-122">SQL_FETCH_NEXT</span><span class="sxs-lookup"><span data-stu-id="1ed3c-122">SQL_FETCH_NEXT</span></span>|  
|<span data-ttu-id="1ed3c-123">На строку вверх</span><span class="sxs-lookup"><span data-stu-id="1ed3c-123">Line up</span></span>|<span data-ttu-id="1ed3c-124">SQL_FETCH_RELATIVE с Фетчоффсет, равным-1</span><span class="sxs-lookup"><span data-stu-id="1ed3c-124">SQL_FETCH_RELATIVE with FetchOffset equal to -1</span></span>|  
|<span data-ttu-id="1ed3c-125">На строку вниз</span><span class="sxs-lookup"><span data-stu-id="1ed3c-125">Line down</span></span>|<span data-ttu-id="1ed3c-126">SQL_FETCH_RELATIVE с FetchOffset, равным 1</span><span class="sxs-lookup"><span data-stu-id="1ed3c-126">SQL_FETCH_RELATIVE with FetchOffset equal to 1</span></span>|  
|<span data-ttu-id="1ed3c-127">Ползунок вверх</span><span class="sxs-lookup"><span data-stu-id="1ed3c-127">Scroll box to top</span></span>|<span data-ttu-id="1ed3c-128">SQL_FETCH_FIRST</span><span class="sxs-lookup"><span data-stu-id="1ed3c-128">SQL_FETCH_FIRST</span></span>|  
|<span data-ttu-id="1ed3c-129">Ползунок вниз</span><span class="sxs-lookup"><span data-stu-id="1ed3c-129">Scroll box to bottom</span></span>|<span data-ttu-id="1ed3c-130">SQL_FETCH_LAST</span><span class="sxs-lookup"><span data-stu-id="1ed3c-130">SQL_FETCH_LAST</span></span>|  
|<span data-ttu-id="1ed3c-131">Случайное положение ползунка</span><span class="sxs-lookup"><span data-stu-id="1ed3c-131">Random scroll box position</span></span>|<span data-ttu-id="1ed3c-132">SQL_FETCH_ABSOLUTE</span><span class="sxs-lookup"><span data-stu-id="1ed3c-132">SQL_FETCH_ABSOLUTE</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="1ed3c-133">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="1ed3c-133">In This Section</span></span>  
  
-   [<span data-ttu-id="1ed3c-134">Создание закладок строк в ODBC</span><span class="sxs-lookup"><span data-stu-id="1ed3c-134">Bookmarking Rows in ODBC</span></span>](scrolling-and-fetching-rows-bookmarking-rows-in-odbc.md)  
  
## <a name="see-also"></a><span data-ttu-id="1ed3c-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="1ed3c-135">See Also</span></span>  
 [<span data-ttu-id="1ed3c-136">Использование курсоров &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="1ed3c-136">Using Cursors &#40;ODBC&#41;</span></span>](using-cursors-odbc.md)  
  
  
