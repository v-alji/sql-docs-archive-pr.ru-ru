---
title: Поведение курсора | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- scrollable cursors [SQL Server]
- SQL Server Native Client ODBC driver, cursors
- version-based optimistic concurrency
- cursors [ODBC], cursor behaviors
- ODBC applications, cursors
- SQL_ATTR_CURSOR_SENSITIVITY option
- SQL_ATTR_CURSOR_SCROLLABLE option
- sensitivity behavior of cursor
- ODBC cursors, cursor behaviors
ms.assetid: 742ddcd2-232b-4aa1-9212-027df120ad35
author: rothja
ms.author: jroth
ms.openlocfilehash: 89c7c4e9a8dcffe03dd12f8013d5ed43810547f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664160"
---
# <a name="cursor-behaviors"></a><span data-ttu-id="fc07d-102">Режимы работы курсоров</span><span class="sxs-lookup"><span data-stu-id="fc07d-102">Cursor Behaviors</span></span>
  <span data-ttu-id="fc07d-103">ODBC поддерживает параметры ISO, предназначенные для указания поведения курсоров, задавая их прокручиваемость и чувствительность.</span><span class="sxs-lookup"><span data-stu-id="fc07d-103">ODBC supports the ISO options for specifying the behavior of cursors by specifying their scrollability and sensitivity.</span></span> <span data-ttu-id="fc07d-104">Эти поведения задаются путем установки параметров SQL_ATTR_CURSOR_SCROLLABLE и SQL_ATTR_CURSOR_SENSITIVITY для вызова [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="fc07d-104">These behaviors are specified by setting the SQL_ATTR_CURSOR_SCROLLABLE and SQL_ATTR_CURSOR_SENSITIVITY options on a call to [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md).</span></span> <span data-ttu-id="fc07d-105">Драйвер ODBC для собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] реализует эти параметры, запрашивая серверные курсоры со следующими характеристиками.</span><span class="sxs-lookup"><span data-stu-id="fc07d-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver implements these options by requesting server cursors with the following characteristics.</span></span>  
  
|<span data-ttu-id="fc07d-106">Параметры режима работы курсоров</span><span class="sxs-lookup"><span data-stu-id="fc07d-106">Cursor behavior settings</span></span>|<span data-ttu-id="fc07d-107">Запрошенные характеристики серверного курсора</span><span class="sxs-lookup"><span data-stu-id="fc07d-107">Server cursor characteristics requested</span></span>|  
|------------------------------|---------------------------------------------|  
|<span data-ttu-id="fc07d-108">SQL_SCROLLABLE и SQL_SENSITIVE</span><span class="sxs-lookup"><span data-stu-id="fc07d-108">SQL_SCROLLABLE and SQL_SENSITIVE</span></span>|<span data-ttu-id="fc07d-109">Курсор, управляемый набором ключей, и основанный на версии оптимистический параллелизм</span><span class="sxs-lookup"><span data-stu-id="fc07d-109">Keyset-driven cursor and version-based optimistic concurrency</span></span>|  
|<span data-ttu-id="fc07d-110">SQL_SCROLLABLE и SQL_INSENSITIVE</span><span class="sxs-lookup"><span data-stu-id="fc07d-110">SQL_SCROLLABLE and SQL_INSENSITIVE</span></span>|<span data-ttu-id="fc07d-111">Статический курсор и параллелизм в режиме «только чтение»</span><span class="sxs-lookup"><span data-stu-id="fc07d-111">Static cursor and read-only concurrency</span></span>|  
|<span data-ttu-id="fc07d-112">SQL_SCROLLABLE и SQL_UNSPECIFIED</span><span class="sxs-lookup"><span data-stu-id="fc07d-112">SQL_SCROLLABLE and SQL_UNSPECIFIED</span></span>|<span data-ttu-id="fc07d-113">Статический курсор и параллелизм в режиме «только чтение»</span><span class="sxs-lookup"><span data-stu-id="fc07d-113">Static cursor and read-only concurrency</span></span>|  
|<span data-ttu-id="fc07d-114">SQL_NONSCROLLABLE и SQL_SENSITIVE</span><span class="sxs-lookup"><span data-stu-id="fc07d-114">SQL_NONSCROLLABLE and SQL_SENSITIVE</span></span>|<span data-ttu-id="fc07d-115">Однопроходный курсор и основанный на версии оптимистический параллелизм</span><span class="sxs-lookup"><span data-stu-id="fc07d-115">Forward-only cursor and version-based optimistic concurrency</span></span>|  
|<span data-ttu-id="fc07d-116">SQL_NONSCROLLABLE и SQL_INSENSITIVE</span><span class="sxs-lookup"><span data-stu-id="fc07d-116">SQL_NONSCROLLABLE and SQL_INSENSITIVE</span></span>|<span data-ttu-id="fc07d-117">Результирующий набор по умолчанию (последовательный доступ, только чтение)</span><span class="sxs-lookup"><span data-stu-id="fc07d-117">Default result set (forward-only, read-only)</span></span>|  
|<span data-ttu-id="fc07d-118">SQL_NONSCROLLABLE и SQL_UNSPECIFIED</span><span class="sxs-lookup"><span data-stu-id="fc07d-118">SQL_NONSCROLLABLE and SQL_UNSPECIFIED</span></span>|<span data-ttu-id="fc07d-119">Результирующий набор по умолчанию (последовательный доступ, только чтение)</span><span class="sxs-lookup"><span data-stu-id="fc07d-119">Default result set (forward-only, read-only)</span></span>|  
  
 <span data-ttu-id="fc07d-120">Для оптимистичного параллелизма на основе версий требуется столбец **отметок времени** в базовой таблице.</span><span class="sxs-lookup"><span data-stu-id="fc07d-120">Version-based optimistic concurrency requires a **timestamp** column in the underlying table.</span></span> <span data-ttu-id="fc07d-121">Если для таблицы, не имеющей столбца **timestamp** , запрашивается управление оптимистичным параллелизмом на основе версий, то сервер использует оптимистичный параллелизм на основе значений.</span><span class="sxs-lookup"><span data-stu-id="fc07d-121">If version-based optimistic concurrency control is requested on a table that does not have a **timestamp** column, the server uses values-based optimistic concurrency.</span></span>  
  
## <a name="scrollability"></a><span data-ttu-id="fc07d-122">Прокручиваемость</span><span class="sxs-lookup"><span data-stu-id="fc07d-122">Scrollability</span></span>  
 <span data-ttu-id="fc07d-123">Если SQL_ATTR_CURSOR_SCROLLABLE имеет значение SQL_SCROLLABLE, курсор поддерживает все различные значения параметра *Фетчориентатион* [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md).</span><span class="sxs-lookup"><span data-stu-id="fc07d-123">When SQL_ATTR_CURSOR_SCROLLABLE is set to SQL_SCROLLABLE, the cursor supports all the different values for the *FetchOrientation* parameter of [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md).</span></span> <span data-ttu-id="fc07d-124">Если SQL_ATTR_CURSOR_SCROLLABLE имеет значение SQL_NONSCROLLABLE, курсор поддерживает только значение *фетчориентатион* , равное SQL_FETCH_NEXT.</span><span class="sxs-lookup"><span data-stu-id="fc07d-124">When SQL_ATTR_CURSOR_SCROLLABLE is set to SQL_NONSCROLLABLE, the cursor only supports a *FetchOrientation* value of SQL_FETCH_NEXT.</span></span>  
  
## <a name="sensitivity"></a><span data-ttu-id="fc07d-125">Чувствительность</span><span class="sxs-lookup"><span data-stu-id="fc07d-125">Sensitivity</span></span>  
 <span data-ttu-id="fc07d-126">Если параметр SQL_ATTR_CURSOR_SENSITIVITY имеет значение SQL_SENSITIVE, курсор отражает изменения данных, произведенные текущим пользователем или зафиксированные другими пользователями.</span><span class="sxs-lookup"><span data-stu-id="fc07d-126">When SQL_ATTR_CURSOR_SENSITIVITY is set to SQL_SENSITIVE, the cursor reflects data modifications made by the current user or committed by other users.</span></span> <span data-ttu-id="fc07d-127">Если параметр SQL_ATTR_CURSOR_SENSITIVITY имеет значение SQL_INSENSITIVE, курсор не отражает изменения данных.</span><span class="sxs-lookup"><span data-stu-id="fc07d-127">When SQL_ATTR_CURSOR_SENSITIVITY is set to SQL_INSENSITIVE, the cursor does not reflect data modifications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc07d-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="fc07d-128">See Also</span></span>  
 [<span data-ttu-id="fc07d-129">Использование курсоров &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="fc07d-129">Using Cursors &#40;ODBC&#41;</span></span>](using-cursors-odbc.md)  
  
  
