---
title: Быстрые однопроходные курсоры (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- fast forward-only cursors
- forward-only cursors
- cursors [ODBC], fast forward-only
- ODBC cursors, fast forward-only
ms.assetid: 0707d07e-fc95-42ed-9280-b7e508ac8c62
author: rothja
ms.author: jroth
ms.openlocfilehash: de8d82a0c72ad51741a3785fba2910f691028cba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666566"
---
# <a name="fast-forward-only-cursors-odbc"></a><span data-ttu-id="ce583-102">Быстрые курсоры последовательного доступа (ODBC)</span><span class="sxs-lookup"><span data-stu-id="ce583-102">Fast Forward-Only Cursors (ODBC)</span></span>
  <span data-ttu-id="ce583-103">При подключении к экземпляру [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] драйвер ODBC собственного клиента поддерживает оптимизацию производительности для однопроходных курсоров только для чтения.</span><span class="sxs-lookup"><span data-stu-id="ce583-103">When connected to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver supports performance optimizations for forward-only, read-only cursors.</span></span> <span data-ttu-id="ce583-104">Быстрые однопроходные курсоры реализуются драйвером и сервером внутренне, при этом способ реализации очень похож на результирующие наборы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ce583-104">Fast forward-only cursors are implemented internally by the driver and server in a manner very similar to default result sets.</span></span> <span data-ttu-id="ce583-105">Кроме того, имея высокую производительность, быстрые однопроходные курсоры обладают следующими характеристиками.</span><span class="sxs-lookup"><span data-stu-id="ce583-105">Besides having high performance, fast forward-only cursors also have these characteristics:</span></span>  
  
-   <span data-ttu-id="ce583-106">[SQLGetData](../../native-client-odbc-api/sqlgetdata.md) не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="ce583-106">[SQLGetData](../../native-client-odbc-api/sqlgetdata.md) is not supported.</span></span> <span data-ttu-id="ce583-107">Столбцы результирующего набора должны быть привязаны к переменным программы.</span><span class="sxs-lookup"><span data-stu-id="ce583-107">The result set columns must be bound to program variables.</span></span>  
  
-   <span data-ttu-id="ce583-108">Когда сервер достигает конца курсора, он автоматически закрывает курсор.</span><span class="sxs-lookup"><span data-stu-id="ce583-108">The server automatically closes the cursor when the end of the cursor is detected.</span></span> <span data-ttu-id="ce583-109">Приложение по-прежнему должно вызывать [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) или [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md)(SQL_CLOSE), но драйверу не нужно отсылать запрос на закрытие на сервер.</span><span class="sxs-lookup"><span data-stu-id="ce583-109">The application must still call [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) or [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md)(SQL_CLOSE), but the driver does not have to send the close request to the server.</span></span> <span data-ttu-id="ce583-110">Это экономит обращение через сеть к серверу.</span><span class="sxs-lookup"><span data-stu-id="ce583-110">This saves a roundtrip across the network to the server.</span></span>  
  
 <span data-ttu-id="ce583-111">Приложение запрашивает быстрые однопроходные курсоры при помощи атрибута инструкции SQL_SOPT_SS_CURSOR_OPTIONS, зависящего от драйвера.</span><span class="sxs-lookup"><span data-stu-id="ce583-111">The application requests fast forward-only cursors using the driver-specific statement attribute SQL_SOPT_SS_CURSOR_OPTIONS.</span></span> <span data-ttu-id="ce583-112">При установке значения SQL_CO_FFO быстрые однопроходные курсоры разрешаются без автоматической выборки.</span><span class="sxs-lookup"><span data-stu-id="ce583-112">When set to SQL_CO_FFO, fast forward-only cursors are enabled without autofetch.</span></span> <span data-ttu-id="ce583-113">При установке значения SQL_CO_FFO_AF включен параметр автоматической выборки.</span><span class="sxs-lookup"><span data-stu-id="ce583-113">When set to SQL_CO_FFO_AF, the autofetch option is also enabled.</span></span> <span data-ttu-id="ce583-114">Дополнительные сведения о автоматической выборке см. в разделе [Использование автоматической выборки с курсорами ODBC](using-autofetch-with-odbc-cursors.md).</span><span class="sxs-lookup"><span data-stu-id="ce583-114">For more information about autofetch, see [Using Autofetch with ODBC Cursors](using-autofetch-with-odbc-cursors.md).</span></span>  
  
 <span data-ttu-id="ce583-115">Быстрые однопроходные курсоры с автоматической выборкой можно использовать для получения небольшого результирующего набора с однократным обращением к серверу.</span><span class="sxs-lookup"><span data-stu-id="ce583-115">Fast forward-only cursors with autofetch can be used to retrieve a small result set with only one roundtrip to the server.</span></span> <span data-ttu-id="ce583-116">В этих шагах *n* — число возвращаемых строк:</span><span class="sxs-lookup"><span data-stu-id="ce583-116">In these steps, *n* is the number of rows to be returned:</span></span>  
  
1.  <span data-ttu-id="ce583-117">Установите для атрибута SQL_SOPT_SS_CURSOR_OPTIONS значение SQL_CO_FFO_AF.</span><span class="sxs-lookup"><span data-stu-id="ce583-117">Set SQL_SOPT_SS_CURSOR_OPTIONS to SQL_CO_FFO_AF.</span></span>  
  
2.  <span data-ttu-id="ce583-118">Задайте для параметра SQL_ATTR_ROW_ARRAY_SIZE значение *n* + 1.</span><span class="sxs-lookup"><span data-stu-id="ce583-118">Set SQL_ATTR_ROW_ARRAY_SIZE to *n* + 1.</span></span>  
  
3.  <span data-ttu-id="ce583-119">Привязка результирующих столбцов к массивам элементов *n* + 1 (для защиты, если фактически выбирается *n* + 1 строк).</span><span class="sxs-lookup"><span data-stu-id="ce583-119">Bind the result columns to arrays of *n* + 1 elements (to be safe if *n* + 1 rows are actually fetched).</span></span>  
  
4.  <span data-ttu-id="ce583-120">Откройте курсор с помощью **SQLExecDirect** или **SQLExecute**.</span><span class="sxs-lookup"><span data-stu-id="ce583-120">Open the cursor with either **SQLExecDirect** or **SQLExecute**.</span></span>  
  
5.  <span data-ttu-id="ce583-121">Если возвращаемое состояние — SQL_SUCCESS, вызовите **SQLFreeStmt** или **SQLCloseCursor** , чтобы закрыть курсор.</span><span class="sxs-lookup"><span data-stu-id="ce583-121">If the return status is SQL_SUCCESS, then call **SQLFreeStmt** or **SQLCloseCursor** to close the cursor.</span></span> <span data-ttu-id="ce583-122">Все данные для строк будут находиться в связанных программных переменных.</span><span class="sxs-lookup"><span data-stu-id="ce583-122">All data for the rows will be in the bound program variables.</span></span>  
  
 <span data-ttu-id="ce583-123">С помощью этих шагов **SQLExecDirect** или **SQLExecute** отправляет запрос на открытие курсора с включенным параметром автоматической выборки.</span><span class="sxs-lookup"><span data-stu-id="ce583-123">With these steps, the **SQLExecDirect** or **SQLExecute** sends a cursor open request with the autofetch option enabled.</span></span> <span data-ttu-id="ce583-124">В ответ на этот отдельный запрос от клиента сервер:</span><span class="sxs-lookup"><span data-stu-id="ce583-124">On that single request from the client, the server:</span></span>  
  
-   <span data-ttu-id="ce583-125">Открывает курсор.</span><span class="sxs-lookup"><span data-stu-id="ce583-125">Opens the cursor.</span></span>  
  
-   <span data-ttu-id="ce583-126">Строит результирующий набор и отправляет строки клиенту.</span><span class="sxs-lookup"><span data-stu-id="ce583-126">Builds the result set and sends the rows to the client.</span></span>  
  
-   <span data-ttu-id="ce583-127">Так как размер набора строк был установлен в значение на 1 большее, чем число строк результирующего набора, сервер определяет конец курсора и закрывает его.</span><span class="sxs-lookup"><span data-stu-id="ce583-127">Because the rowset size was set to 1 more than the number of rows in the result set, the server detects the end of the cursor and closes the cursor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce583-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="ce583-128">See Also</span></span>  
 [<span data-ttu-id="ce583-129">Сведения о программировании курсора &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="ce583-129">Cursor Programming Details &#40;ODBC&#41;</span></span>](cursor-programming-details-odbc.md)  
  
  
