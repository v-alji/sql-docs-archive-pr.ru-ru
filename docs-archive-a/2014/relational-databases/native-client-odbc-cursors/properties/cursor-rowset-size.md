---
title: Размер набора строк курсора | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- cursors [ODBC], rowset size
- ODBC cursors, rowset size
- rowsets [ODBC]
ms.assetid: 2febe2ae-fdc1-490e-a79f-c516bc8e7c3f
author: rothja
ms.author: jroth
ms.openlocfilehash: 83c4e55025e6e3724f354f022760b7ba1e2f10e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666553"
---
# <a name="cursor-rowset-size"></a><span data-ttu-id="7a5bb-102">Размер набора строк курсора</span><span class="sxs-lookup"><span data-stu-id="7a5bb-102">Cursor Rowset Size</span></span>
  <span data-ttu-id="7a5bb-103">Возможности курсоров ODBC не ограничены выбором только одной строки за один раз.</span><span class="sxs-lookup"><span data-stu-id="7a5bb-103">ODBC cursors are not limited to fetching one row at a time.</span></span> <span data-ttu-id="7a5bb-104">Они могут получать несколько строк в каждом вызове **SQLFetch** или [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md).</span><span class="sxs-lookup"><span data-stu-id="7a5bb-104">They can retrieve multiple rows in each call to **SQLFetch** or [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md).</span></span> <span data-ttu-id="7a5bb-105">При работе с базой данных Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] в режиме клиент-сервер значительно эффективнее извлекать несколько строк за один раз.</span><span class="sxs-lookup"><span data-stu-id="7a5bb-105">When you are working with a client/server database such as Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], it is more efficient to fetch several rows at a time.</span></span> <span data-ttu-id="7a5bb-106">Число строк, возвращаемых при выборке, называется размером набора строк и задается с помощью SQL_ATTR_ROW_ARRAY_SIZE [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="7a5bb-106">The number of rows returned on a fetch is called the rowset size and is specified by using the SQL_ATTR_ROW_ARRAY_SIZE of [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span></span>  
  
```  
SQLUINTEGER uwRowsize;  
SQLSetStmtAttr(m_hstmt, SQL_ATTR_ROW_ARRAY_SIZE, (SQLPOINTER)uwRowsetSize, SQL_IS_UINTEGER);  
```  
  
 <span data-ttu-id="7a5bb-107">Курсоры, имеющие размер набора строк более 1, называются блочными курсорами.</span><span class="sxs-lookup"><span data-stu-id="7a5bb-107">Cursors with a rowset size greater than 1 are called block cursors.</span></span>  
  
 <span data-ttu-id="7a5bb-108">Есть два параметра привязки результирующего набора строк для блочных курсоров.</span><span class="sxs-lookup"><span data-stu-id="7a5bb-108">There are two options for binding result set columns for block cursors:</span></span>  
  
-   <span data-ttu-id="7a5bb-109">Привязка на уровне столбца</span><span class="sxs-lookup"><span data-stu-id="7a5bb-109">Column-wise binding</span></span>  
  
     <span data-ttu-id="7a5bb-110">Каждый столбец привязывается к массиву переменных.</span><span class="sxs-lookup"><span data-stu-id="7a5bb-110">Each column is bound to an array of variables.</span></span> <span data-ttu-id="7a5bb-111">Число элементов в каждом массиве равно размеру набора строк.</span><span class="sxs-lookup"><span data-stu-id="7a5bb-111">Each array has the same number of elements as the rowset size.</span></span>  
  
-   <span data-ttu-id="7a5bb-112">Привязка на уровне строки</span><span class="sxs-lookup"><span data-stu-id="7a5bb-112">Row-wise binding</span></span>  
  
     <span data-ttu-id="7a5bb-113">Массив создается с использованием структур, которые содержат данные и индикаторы для всех столбцов в строке.</span><span class="sxs-lookup"><span data-stu-id="7a5bb-113">An array is built using structures that hold the data and indicators for all the columns in a row.</span></span> <span data-ttu-id="7a5bb-114">Число структур в массиве равно размеру набора строк.</span><span class="sxs-lookup"><span data-stu-id="7a5bb-114">The array has the same number of structures as the rowset size.</span></span>  
  
 <span data-ttu-id="7a5bb-115">При использовании привязки на уровне столбца или на уровне строки каждый вызов **SQLFetch** или **SQLFetchScroll** заполняет привязанные массивы данными из полученного набора строк.</span><span class="sxs-lookup"><span data-stu-id="7a5bb-115">When either column-wise or row-wise binding is used, each call to **SQLFetch** or **SQLFetchScroll** fills the bound arrays with data from the rowset retrieved.</span></span>  
  
 <span data-ttu-id="7a5bb-116">[SQLGetData](../../native-client-odbc-api/sqlgetdata.md) также можно использовать для извлечения данных столбца из блочного курсора.</span><span class="sxs-lookup"><span data-stu-id="7a5bb-116">[SQLGetData](../../native-client-odbc-api/sqlgetdata.md) can also be used to retrieve column data from a block cursor.</span></span> <span data-ttu-id="7a5bb-117">Поскольку **SQLGetData** работает по одной строке за раз, необходимо вызвать функцию **SQLSetPos** , чтобы задать определенную строку в наборе строк в качестве текущей строки перед вызовом **SQLGetData**.</span><span class="sxs-lookup"><span data-stu-id="7a5bb-117">Because **SQLGetData** works one row at a time, **SQLSetPos** must be called to set a specific row in the rowset as the current row before calling **SQLGetData**.</span></span>  
  
 <span data-ttu-id="7a5bb-118">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]Драйвер ODBC для собственного клиента обеспечивает оптимизацию с помощью наборов строк для быстрого получения всего результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="7a5bb-118">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver offers an optimization using rowsets to retrieve a whole result set quickly.</span></span> <span data-ttu-id="7a5bb-119">Чтобы использовать эту оптимизацию, задайте для атрибутов курсора значения по умолчанию ("только вперед", "только для чтения", размер набора строк = 1) во время вызова **SQLExecDirect** или **SQLExecute** .</span><span class="sxs-lookup"><span data-stu-id="7a5bb-119">To use this optimization, set the cursor attributes to their defaults (forward-only, read-only, rowset size = 1) at the time **SQLExecDirect** or **SQLExecute** is called.</span></span> <span data-ttu-id="7a5bb-120">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]Драйвер ODBC для собственного клиента устанавливает результирующий набор по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7a5bb-120">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver sets up a default result set.</span></span> <span data-ttu-id="7a5bb-121">Это более эффективно, чем использование серверных курсоров при передаче результатов клиенту без прокрутки.</span><span class="sxs-lookup"><span data-stu-id="7a5bb-121">This is more efficient than server cursors when transferring results to the client without scrolling.</span></span> <span data-ttu-id="7a5bb-122">После выполнения инструкции увеличьте размер набора строк и примените привязку на уровне столбца или строки.</span><span class="sxs-lookup"><span data-stu-id="7a5bb-122">After the statement has been executed, increase the rowset size and use either column-wise or row-wise binding.</span></span> <span data-ttu-id="7a5bb-123">Это позволяет [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] использовать результирующий набор по умолчанию для эффективного отправки результирующих строк клиенту, в то время как [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] драйвер ODBC для собственного клиента непрерывно извлекает строки из сетевых буферов на клиенте.</span><span class="sxs-lookup"><span data-stu-id="7a5bb-123">This lets [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] use a default result set to send result rows efficiently to the client, while the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver continuously pulls rows from the network buffers on the client.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a5bb-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="7a5bb-124">See Also</span></span>  
 [<span data-ttu-id="7a5bb-125">Свойства курсора</span><span class="sxs-lookup"><span data-stu-id="7a5bb-125">Cursor Properties</span></span>](cursor-properties.md)  
  
  
