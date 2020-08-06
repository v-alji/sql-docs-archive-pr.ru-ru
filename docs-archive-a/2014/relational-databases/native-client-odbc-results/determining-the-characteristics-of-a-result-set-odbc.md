---
title: Определение характеристик результирующего набора (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- result sets [ODBC], characteristics
- SQL Server Native Client ODBC driver, result sets
- ODBC applications, result sets
- SQLDescribeCol function
- metadata [ODBC]
- SQLColAttribute function
- SQLNumResultCols function
ms.assetid: 90be414c-04b3-46c0-906b-ae7537989b7d
author: rothja
ms.author: jroth
ms.openlocfilehash: 5957092cdddfbcbce904d9a6483914672565d337
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657755"
---
# <a name="determining-the-characteristics-of-a-result-set-odbc"></a><span data-ttu-id="6a0eb-102">Определение характеристик результирующего набора (ODBC)</span><span class="sxs-lookup"><span data-stu-id="6a0eb-102">Determining the Characteristics of a Result Set (ODBC)</span></span>
  <span data-ttu-id="6a0eb-103">Метаданные — это данные, описывающие другие данные.</span><span class="sxs-lookup"><span data-stu-id="6a0eb-103">Metadata is data that describes other data.</span></span> <span data-ttu-id="6a0eb-104">Например, метаданные результирующего набора описывают такие характеристики результирующего набора, как количество столбцов, типы данных в этих столбцах, их имена, точность и допустимость значений NULL.</span><span class="sxs-lookup"><span data-stu-id="6a0eb-104">For example, result set metadata describes the characteristics of a result set, such as the number of columns in the result set, the data types of those columns, their names, precision, and nullability.</span></span>  
  
 <span data-ttu-id="6a0eb-105">ODBC сообщает метаданные приложениям с помощью функций каталога API-интерфейса.</span><span class="sxs-lookup"><span data-stu-id="6a0eb-105">ODBC supplies metadata to applications through its catalog API functions.</span></span> <span data-ttu-id="6a0eb-106">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Драйвер ODBC для собственного клиента реализует многие функции каталога API ODBC в качестве вызовов к соответствующей [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] процедуре каталога.</span><span class="sxs-lookup"><span data-stu-id="6a0eb-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver implements many of the ODBC API catalog functions as calls to a corresponding [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] catalog procedure.</span></span>  
  
 <span data-ttu-id="6a0eb-107">Метаданные требуются приложениям для большинства операций с результирующими наборами.</span><span class="sxs-lookup"><span data-stu-id="6a0eb-107">Applications require metadata for most result set operations.</span></span> <span data-ttu-id="6a0eb-108">Например, приложение использует тип данных столбца, чтобы определить, какую переменную привязывать к этому столбцу.</span><span class="sxs-lookup"><span data-stu-id="6a0eb-108">For example, the application uses the data type of a column to determine what kind of variable to bind to that column.</span></span> <span data-ttu-id="6a0eb-109">Оно использует длину в байтах столбцов с символьными значениями, чтоб определить, сколько места потребуется для отображения данных из этого столбца.</span><span class="sxs-lookup"><span data-stu-id="6a0eb-109">It uses the byte length of a character column to determine how much space it must have to display data from that column.</span></span> <span data-ttu-id="6a0eb-110">Способ определения метаданных для столбца зависит от типа приложения.</span><span class="sxs-lookup"><span data-stu-id="6a0eb-110">How an application determines the metadata for a column depends on the type of the application.</span></span>  
  
 <span data-ttu-id="6a0eb-111">Вертикальные приложения обычно работают со стандартными таблицами и выполняют стандартные операции с этими таблицами.</span><span class="sxs-lookup"><span data-stu-id="6a0eb-111">Vertical applications typically work with predefined tables and perform predefined operations on those tables.</span></span> <span data-ttu-id="6a0eb-112">Поскольку метаданные результирующих наборов для таких приложений определяются даже до того, как приложение написано, и управляются разработчиком, они могут быть жестко запрограммированы в приложении.</span><span class="sxs-lookup"><span data-stu-id="6a0eb-112">Because the result set metadata for such applications is defined before the application is even written and is controlled by the developer, it can be hard-coded into the application.</span></span> <span data-ttu-id="6a0eb-113">Например, если столбец идентификатора заказа определен в источник данных как 4-байтовое целое число, приложение может всегда привязывать 4-байтовые целые числа к этому столбцу.</span><span class="sxs-lookup"><span data-stu-id="6a0eb-113">For example, if an order ID column is defined as a 4-byte integer in the data source, the application can always bind a 4-byte integer to that column.</span></span> <span data-ttu-id="6a0eb-114">Если метаданные жестко запрограммированы в приложении, изменения в используемых приложением таблицах обычно подразумевают изменения в коде приложения.</span><span class="sxs-lookup"><span data-stu-id="6a0eb-114">When metadata is hard-coded in the application, a change to the tables used by the application generally implies a change to the application code.</span></span>  
  
 <span data-ttu-id="6a0eb-115">В обычных приложениях, особенно приложениях, поддерживающих нерегламентируемые запросы, метаданные результирующих наборов обычно неизвестны до времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="6a0eb-115">In generic applications, especially applications that support ad hoc queries, the metadata of the result sets they create is typically unknown until run time.</span></span>  
  
 <span data-ttu-id="6a0eb-116">Чтобы определить характеристики результирующего набора, приложение может вызвать следующие функции.</span><span class="sxs-lookup"><span data-stu-id="6a0eb-116">To determine the characteristics of a result set, an application can call:</span></span>  
  
-   <span data-ttu-id="6a0eb-117">[SQLNumResultCols](../native-client-odbc-api/sqlnumresultcols.md) , чтобы определить, сколько столбцов возвращает запрос.</span><span class="sxs-lookup"><span data-stu-id="6a0eb-117">[SQLNumResultCols](../native-client-odbc-api/sqlnumresultcols.md) to determine how many columns a request returned.</span></span>  
  
-   <span data-ttu-id="6a0eb-118">[SQLColAttribute](../native-client-odbc-api/sqlcolattribute.md) или [SQLDescribeCol](../native-client-odbc-api/sqldescribecol.md) для описания столбца в результирующем наборе.</span><span class="sxs-lookup"><span data-stu-id="6a0eb-118">[SQLColAttribute](../native-client-odbc-api/sqlcolattribute.md) or [SQLDescribeCol](../native-client-odbc-api/sqldescribecol.md) to describe a column in the result set.</span></span>  
  
 <span data-ttu-id="6a0eb-119">Хорошо спроектированные приложения пишутся с предположением, что результирующий набор неизвестен, и используют для привязки столбцов в результирующем наборе данные, возвращаемые этими функциями.</span><span class="sxs-lookup"><span data-stu-id="6a0eb-119">A well-designed application is written with the assumption that the result set is unknown and uses the information returned by these functions to bind the columns in the result set.</span></span> <span data-ttu-id="6a0eb-120">Приложение может вызвать эти функции в любое время после подготовки или выполнения инструкции.</span><span class="sxs-lookup"><span data-stu-id="6a0eb-120">An application can call these functions at any time after a statement is prepared or executed.</span></span> <span data-ttu-id="6a0eb-121">Однако для оптимальной производительности приложение должно вызывать **SQLColAttribute**, **SQLDescribeCol**и **SQLNumResultCols** после выполнения инструкции.</span><span class="sxs-lookup"><span data-stu-id="6a0eb-121">However, for optimal performance, an application should call **SQLColAttribute**, **SQLDescribeCol**, and **SQLNumResultCols** after a statement is executed.</span></span>  
  
 <span data-ttu-id="6a0eb-122">Можно выполнять несколько одновременных вызовов метаданных.</span><span class="sxs-lookup"><span data-stu-id="6a0eb-122">You can have multiple concurrent calls for metadata.</span></span> <span data-ttu-id="6a0eb-123">Эти процедуры системного каталога, лежащие в основе реализаций API-интерфейса каталога ODBC, могут вызываться драйвером ODBC во время использования им статических серверных курсоров.</span><span class="sxs-lookup"><span data-stu-id="6a0eb-123">The system catalog procedures underlying the ODBC catalog API implementations can be called by the ODBC driver while it is using static server cursors.</span></span> <span data-ttu-id="6a0eb-124">Это позволяет приложениям одновременно обрабатывать несколько вызовов функций каталога ODBC.</span><span class="sxs-lookup"><span data-stu-id="6a0eb-124">This lets applications concurrently process multiple calls to ODBC catalog functions.</span></span>  
  
 <span data-ttu-id="6a0eb-125">Если приложение использует определенный набор метаданных более одного раза, может быть полезно кэшировать данные в закрытых переменных после их первого получения.</span><span class="sxs-lookup"><span data-stu-id="6a0eb-125">If an application uses a particular set of metadata more than one time, it will probably benefit from caching the information in private variables when it is first obtained.</span></span> <span data-ttu-id="6a0eb-126">Этот предотвращает последующие вызовы функций каталога ODBC для получения тех же данных, ради которых драйверу приходится многократно обращаться к серверу.</span><span class="sxs-lookup"><span data-stu-id="6a0eb-126">This prevents later calls to the ODBC catalog functions for the same information, which force the driver to make round trips to the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a0eb-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="6a0eb-127">See Also</span></span>  
 [<span data-ttu-id="6a0eb-128">Обработка результатов &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="6a0eb-128">Processing Results &#40;ODBC&#41;</span></span>](processing-results-odbc.md)  
  
  
