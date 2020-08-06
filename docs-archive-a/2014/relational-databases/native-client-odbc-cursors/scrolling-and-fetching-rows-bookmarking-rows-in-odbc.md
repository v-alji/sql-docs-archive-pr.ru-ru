---
title: Создание закладок для строк в ODBC | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- cursors [ODBC], fetching rows
- ODBC cursors, fetching rows
- cursors [ODBC], scrolling rows
- ODBC cursors, scrolling rows
- bookmarks [ODBC]
ms.assetid: 9cfcd243-c9d4-4c2a-abc4-399dbabe5f6b
author: rothja
ms.author: jroth
ms.openlocfilehash: def05f478c16dcbcdc91771925a11b0b91da2e9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739923"
---
# <a name="bookmarking-rows-in-odbc"></a><span data-ttu-id="a020d-102">Создание закладок строк в ODBC</span><span class="sxs-lookup"><span data-stu-id="a020d-102">Bookmarking Rows in ODBC</span></span>
  <span data-ttu-id="a020d-103">Закладка представляет собой значение, используемое для идентификации строки данных.</span><span class="sxs-lookup"><span data-stu-id="a020d-103">A bookmark is a value used to identify a row of data.</span></span> <span data-ttu-id="a020d-104">Содержание значения закладки понятно только драйверу или источнику данных.</span><span class="sxs-lookup"><span data-stu-id="a020d-104">The meaning of the bookmark value is known only to the driver or data source.</span></span> <span data-ttu-id="a020d-105">Например, оно может быть простым (номером строки) или сложным (адрес на диске).</span><span class="sxs-lookup"><span data-stu-id="a020d-105">For example, it might be as simple as a row number or as complex as a disk address.</span></span> <span data-ttu-id="a020d-106">В ODBC приложение запрашивает закладку для конкретной строки, сохраняет ее и передает обратно курсору для возврата к строке.</span><span class="sxs-lookup"><span data-stu-id="a020d-106">In ODBC, the application requests a bookmark for a particular row, stores it, and passes it back to the cursor to return to the row.</span></span>  
  
 <span data-ttu-id="a020d-107">При выборке строк с помощью [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md)приложение может использовать закладку в качестве основы для выбора начальной строки.</span><span class="sxs-lookup"><span data-stu-id="a020d-107">When fetching rows with [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md), an application can use a bookmark as a basis for selecting the starting row.</span></span> <span data-ttu-id="a020d-108">Такой способ представляет собой форму абсолютной адресации, поскольку не зависит от текущей позиции курсора.</span><span class="sxs-lookup"><span data-stu-id="a020d-108">This is a form of absolute addressing because it does not depend on the current cursor position.</span></span> <span data-ttu-id="a020d-109">Для прокрутки к строке с закладкой приложение вызывает **SQLFetchScroll** с *фетчориентатион* SQL_FETCH_BOOKMARK.</span><span class="sxs-lookup"><span data-stu-id="a020d-109">To scroll to a bookmarked row, the application calls **SQLFetchScroll** with a *FetchOrientation* of SQL_FETCH_BOOKMARK.</span></span> <span data-ttu-id="a020d-110">Эта операция использует закладку, на которую указывает атрибут параметра SQL_ATTR_FETCH_BOOKMARK_PTR.</span><span class="sxs-lookup"><span data-stu-id="a020d-110">This operation uses the bookmark pointed to by the SQL_ATTR_FETCH_BOOKMARK_PTR option attribute.</span></span> <span data-ttu-id="a020d-111">Она возвращает набор строк, начинающийся со строки, определяемой закладкой.</span><span class="sxs-lookup"><span data-stu-id="a020d-111">It returns the rowset starting with the row identified by that bookmark.</span></span> <span data-ttu-id="a020d-112">Приложение может указать смещение для этой операции в аргументе *фетчоффсет* вызова **SQLFetchScroll**.</span><span class="sxs-lookup"><span data-stu-id="a020d-112">An application can specify an offset for this operation in the *FetchOffset* argument of the call to **SQLFetchScroll**.</span></span> <span data-ttu-id="a020d-113">При указании смещения первая строка возвращаемого набора строк определяется сложением числа в аргументе FetchOffset с номером строки, определяемой закладкой.</span><span class="sxs-lookup"><span data-stu-id="a020d-113">When an offset is specified, the first row of the returned rowset is determined by adding the number in the FetchOffset argument to the number of the row identified by the bookmark.</span></span> <span data-ttu-id="a020d-114">Поставщик OLE DB для собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поддерживает только закладки в статических курсорах и курсорах, управляемых набором ключей.</span><span class="sxs-lookup"><span data-stu-id="a020d-114">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver only supports bookmarks on static and keyset cursors.</span></span> <span data-ttu-id="a020d-115">Если при включенных закладках запрошен динамический курсор, то вместо него открывается курсор, управляемый набором ключей.</span><span class="sxs-lookup"><span data-stu-id="a020d-115">If a dynamic cursor is requested when bookmarks are set on, a keyset cursor is opened instead.</span></span>  
  
 <span data-ttu-id="a020d-116">Закладки также можно использовать с функцией **SQLBulkOperations** для выполнения операций с набором строк, начиная с закладки.</span><span class="sxs-lookup"><span data-stu-id="a020d-116">Bookmarks can also be used with the **SQLBulkOperations** function to perform operations on a set of rows starting at the bookmark.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a020d-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="a020d-117">See Also</span></span>  
 [<span data-ttu-id="a020d-118">Прокрутка и выборка строк</span><span class="sxs-lookup"><span data-stu-id="a020d-118">Scrolling and Fetching Rows</span></span>](../native-client-ole-db-rowsets/fetching-rows.md)  
  
  
