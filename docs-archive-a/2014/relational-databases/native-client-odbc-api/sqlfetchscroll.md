---
title: SQLFetchScroll | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLFetchScroll function
ms.assetid: 524a3985-a08d-4445-99e0-bb551a666615
author: rothja
ms.author: jroth
ms.openlocfilehash: eecf9714a97577ff490b642cee5b9c380333e40b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657791"
---
# <a name="sqlfetchscroll"></a><span data-ttu-id="c787f-102">SQLFetchScroll</span><span class="sxs-lookup"><span data-stu-id="c787f-102">SQLFetchScroll</span></span>
  <span data-ttu-id="c787f-103">Функция**SQLFetchScroll** возвращает приложению один набор строк данных.</span><span class="sxs-lookup"><span data-stu-id="c787f-103">**SQLFetchScroll** returns one row set of data to the application.</span></span> <span data-ttu-id="c787f-104">Размер набора строк задается с помощью функции [SQLSetStmtAttr](sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="c787f-104">The size of the row set is set using [SQLSetStmtAttr](sqlsetstmtattr.md).</span></span> <span data-ttu-id="c787f-105">Драйвер ODBC собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поддерживает все определенные инструкции выборки (например, SQL_FETCH_RELATIVE) со следующими ограничениями.</span><span class="sxs-lookup"><span data-stu-id="c787f-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports all defined fetch instructions (for example, SQL_FETCH_RELATIVE) with the following limitations:</span></span>  
  
-   <span data-ttu-id="c787f-106">Если для инструкции определен однопроходный курсор, необходимо использовать инструкцию SQL_FETCH_NEXT, а попытки произвести выборку любым другим способом приведут к ошибке.</span><span class="sxs-lookup"><span data-stu-id="c787f-106">If a forward-only cursor is defined for the statement, SQL_FETCH_NEXT is required and attempts to fetch in any other fashion will result in an error return.</span></span>  
  
-   <span data-ttu-id="c787f-107">Инструкция SQL_FETCH_BOOKMARK поддерживается только для статических курсоров и курсоров, управляемых набором ключей.</span><span class="sxs-lookup"><span data-stu-id="c787f-107">SQL_FETCH_BOOKMARK is supported for static and keyset-driven cursors only.</span></span>  
  
## <a name="sqlfetchscroll-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="c787f-108">Поддержка функцией SQLFetchScroll улучшенных функций даты и времени</span><span class="sxs-lookup"><span data-stu-id="c787f-108">SQLFetchScroll Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="c787f-109">Значения результирующих столбцов типов даты-времени преобразуются, как описано в статье [преобразования из SQL в C](../native-client-odbc-date-time/datetime-data-type-conversions-from-sql-to-c.md).</span><span class="sxs-lookup"><span data-stu-id="c787f-109">Result column values of date/time types are converted as described in [Conversions from SQL to C](../native-client-odbc-date-time/datetime-data-type-conversions-from-sql-to-c.md).</span></span>  
  
 <span data-ttu-id="c787f-110">Дополнительные сведения см. в разделе [улучшения даты и времени &#40;&#41;ODBC ](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="c787f-110">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="sqlfetchscroll-support-for-large-clr-udts"></a><span data-ttu-id="c787f-111">Поддержка функцией SQLFetchScroll больших определяемых пользователем типов CLR</span><span class="sxs-lookup"><span data-stu-id="c787f-111">SQLFetchScroll Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="c787f-112">Функция**SQLFetchScroll** поддерживает большие определяемые пользователем типы данных CLR.</span><span class="sxs-lookup"><span data-stu-id="c787f-112">**SQLFetchScroll** supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="c787f-113">Дополнительные сведения см. в разделе [большие определяемые пользователем типы данных CLR &#40;&#41;ODBC ](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="c787f-113">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c787f-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="c787f-114">See Also</span></span>  
 <span data-ttu-id="c787f-115">[Функция SQLFetchScroll](https://go.microsoft.com/fwlink/?LinkId=59343) </span><span class="sxs-lookup"><span data-stu-id="c787f-115">[SQLFetchScroll Function](https://go.microsoft.com/fwlink/?LinkId=59343) </span></span>  
 [<span data-ttu-id="c787f-116">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="c787f-116">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
