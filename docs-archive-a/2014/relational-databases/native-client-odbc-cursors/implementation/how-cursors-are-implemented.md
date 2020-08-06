---
title: Как реализуются курсоры | Документация Майкрософт
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
- cursors [ODBC], about ODBC cursors
ms.assetid: 2b1d7dd4-08a4-43fc-b3eb-70c183d0941f
author: rothja
ms.author: jroth
ms.openlocfilehash: 18995355b825d9cb1e62b4794429b5e98ef2b472
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657788"
---
# <a name="how-cursors-are-implemented"></a><span data-ttu-id="66102-102">Способы реализации курсоров</span><span class="sxs-lookup"><span data-stu-id="66102-102">How Cursors Are Implemented</span></span>
  <span data-ttu-id="66102-103">Приложения ODBC управляют поведением курсора путем задания одного или нескольких атрибутов инструкции перед выполнением инструкции SQL.</span><span class="sxs-lookup"><span data-stu-id="66102-103">ODBC applications control the behavior of a cursor by setting one or more statement attributes before executing an SQL statement.</span></span> <span data-ttu-id="66102-104">ODBC может указывать характеристики курсора двумя разными способами.</span><span class="sxs-lookup"><span data-stu-id="66102-104">ODBC has two different ways to specify the characteristics of a cursor:</span></span>  
  
-   <span data-ttu-id="66102-105">Тип курсора</span><span class="sxs-lookup"><span data-stu-id="66102-105">Cursor type</span></span>  
  
     <span data-ttu-id="66102-106">Типы курсоров задаются с помощью атрибута SQL_ATTR_CURSOR_TYPE [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="66102-106">Cursor types are set using the SQL_ATTR_CURSOR_TYPE attribute of [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span></span> <span data-ttu-id="66102-107">Типы курсора ODBC бывают с последовательным доступом, статические, управляемые набором ключей, смешанные и динамические.</span><span class="sxs-lookup"><span data-stu-id="66102-107">The ODBC cursor types are forward-only, static, keyset-driven, mixed, and dynamic.</span></span> <span data-ttu-id="66102-108">Изначально метод указания курсоров в ODBC заключался в задании типа курсора.</span><span class="sxs-lookup"><span data-stu-id="66102-108">Setting the cursor type was the original method of specifying cursors in ODBC.</span></span>  
  
-   <span data-ttu-id="66102-109">Режим работы курсоров</span><span class="sxs-lookup"><span data-stu-id="66102-109">Cursor behavior</span></span>  
  
     <span data-ttu-id="66102-110">Поведение курсора задается с помощью атрибутов SQL_ATTR_CURSOR_SCROLLABLE и SQL_ATTR_CURSOR_SENSITIVITY **SQLSetStmtAttr**.</span><span class="sxs-lookup"><span data-stu-id="66102-110">Cursor behavior is set using the SQL_ATTR_CURSOR_SCROLLABLE and SQL_ATTR_CURSOR_SENSITIVITY attributes of **SQLSetStmtAttr**.</span></span> <span data-ttu-id="66102-111">Эти атрибуты смоделированы на ключевых словах SCROLL и SENSITIVE, которые в стандартах ISO определены для инструкции DECLARE CURSOR.</span><span class="sxs-lookup"><span data-stu-id="66102-111">These attributes are modeled on the SCROLL and SENSITIVE keywords defined for the DECLARE CURSOR statement in ISO standards.</span></span> <span data-ttu-id="66102-112">Два этих параметра ISO появились в ODBC версии 3.0.</span><span class="sxs-lookup"><span data-stu-id="66102-112">These two ISO options were introduced in ODBC version 3.0.</span></span>  
  
 <span data-ttu-id="66102-113">Характеристики курсора ODBC следует указывать с помощью одного из этих методов; при этом предпочтительнее использовать типы курсоров ODBC.</span><span class="sxs-lookup"><span data-stu-id="66102-113">The characteristics of an ODBC cursor should be specified using either one or the other of these two methods, with the preference being to use the ODBC cursor types.</span></span>  
  
 <span data-ttu-id="66102-114">Помимо установки типа курсора приложения ODBC также задают и другие параметры, например число строк, возвращаемое при каждом извлечении, параметры параллелизма, а также уровни изоляции транзакции.</span><span class="sxs-lookup"><span data-stu-id="66102-114">In addition to setting the type of a cursor, ODBC applications also set other options, such as the number of rows returned on each fetch, concurrency options, and transaction isolation levels.</span></span> <span data-ttu-id="66102-115">Эти параметры можно задавать для курсоров в стиле ODBC (с последовательным доступом, статических, управляемых набором ключей, смешанных и динамических) или курсоров в стиле ISO (прокручиваемость и чувствительность).</span><span class="sxs-lookup"><span data-stu-id="66102-115">These options can be set for either ODBC-style cursors (forward-only, static, keyset-driven, mixed, and dynamic) or ISO style cursors (scrollability and sensitivity).</span></span>  
  
 <span data-ttu-id="66102-116">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]Драйвер ODBC для собственного клиента поддерживает несколько способов физической реализации различных типов курсоров.</span><span class="sxs-lookup"><span data-stu-id="66102-116">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver supports several ways to physically implement the various types of cursors.</span></span> <span data-ttu-id="66102-117">Некоторые типы курсоров драйвер реализует с помощью результирующего набора [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] по умолчанию; другие курсоры реализуются им как серверные курсоры либо при помощи библиотеки курсоров ODBC.</span><span class="sxs-lookup"><span data-stu-id="66102-117">The driver implements some types of cursors using a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] default result set; it implements others as server cursors or by using the ODBC Cursor Library.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="66102-118">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="66102-118">In This Section</span></span>  
  
-   [<span data-ttu-id="66102-119">Использование результирующих наборов по умолчанию в SQL Server</span><span class="sxs-lookup"><span data-stu-id="66102-119">Using SQL Server Default Result Sets</span></span>](using-sql-server-default-result-sets.md)  
  
-   [<span data-ttu-id="66102-120">Использование серверных курсоров</span><span class="sxs-lookup"><span data-stu-id="66102-120">Using Server Cursors</span></span>](using-server-cursors.md)  
  
-   [<span data-ttu-id="66102-121">Библиотека курсоров ODBC</span><span class="sxs-lookup"><span data-stu-id="66102-121">ODBC Cursor Library</span></span>](odbc-cursor-library.md)  
  
## <a name="see-also"></a><span data-ttu-id="66102-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="66102-122">See Also</span></span>  
 [<span data-ttu-id="66102-123">Использование курсоров &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="66102-123">Using Cursors &#40;ODBC&#41;</span></span>](../using-cursors-odbc.md)  
  
  
