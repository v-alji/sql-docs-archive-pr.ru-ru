---
title: Установка параметров курсора (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- cursors [ODBC], options
ms.assetid: 0e72b48a-fc5a-4656-8cf5-39f57d8c1565
author: rothja
ms.author: jroth
ms.openlocfilehash: 877c2596c87ce50295a15912493661c6dd4e0305
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739866"
---
# <a name="set-cursor-options-odbc"></a><span data-ttu-id="cb989-102">Указание параметров курсора (ODBC)</span><span class="sxs-lookup"><span data-stu-id="cb989-102">Set Cursor Options (ODBC)</span></span>
  <span data-ttu-id="cb989-103">Чтобы задать параметры курсора, вызовите [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) , чтобы задать или [SQLGetStmtAttr](../../native-client-odbc-api/sqlgetstmtattr.md) , чтобы получить параметры инструкции, управляющие поведением курсора.</span><span class="sxs-lookup"><span data-stu-id="cb989-103">To set cursor options, Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set or [SQLGetStmtAttr](../../native-client-odbc-api/sqlgetstmtattr.md) to get the statement options that control cursor behavior.</span></span>  
  
|<span data-ttu-id="cb989-104">*Attribute (XElement Dynamic Property)* (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="cb989-104">*Attribute*</span></span>|<span data-ttu-id="cb989-105">Что определяет</span><span class="sxs-lookup"><span data-stu-id="cb989-105">Specifies</span></span>|  
|-----------------|---------------|  
|<span data-ttu-id="cb989-106">SQL_ATTR_CURSOR_TYPE</span><span class="sxs-lookup"><span data-stu-id="cb989-106">SQL_ATTR_CURSOR_TYPE</span></span>|<span data-ttu-id="cb989-107">Однопроходный, статический, динамический или управляемый набором ключей тип курсора</span><span class="sxs-lookup"><span data-stu-id="cb989-107">Cursor type of forward-only, static, dynamic, or keyset-driven</span></span>|  
|<span data-ttu-id="cb989-108">SQL_ATTR_CONCURRENCY</span><span class="sxs-lookup"><span data-stu-id="cb989-108">SQL_ATTR_CONCURRENCY</span></span>|<span data-ttu-id="cb989-109">Параметр управления параллелизмом – только для чтения, блокирующий, оптимистичный с использованием отметок времени или оптимистичный с использованием значений</span><span class="sxs-lookup"><span data-stu-id="cb989-109">Concurrency control option of read-only, locking, optimistic using timestamps, or optimistic using values</span></span>|  
|<span data-ttu-id="cb989-110">SQL_ATTR_ROW_ARRAY_SIZE</span><span class="sxs-lookup"><span data-stu-id="cb989-110">SQL_ATTR_ROW_ARRAY_SIZE</span></span>|<span data-ttu-id="cb989-111">Количество строк, получаемых в каждой выборке</span><span class="sxs-lookup"><span data-stu-id="cb989-111">Number of rows retrieved in each fetch</span></span>|  
|<span data-ttu-id="cb989-112">SQL_ATTR_CURSOR_SENSITIVITY</span><span class="sxs-lookup"><span data-stu-id="cb989-112">SQL_ATTR_CURSOR_SENSITIVITY</span></span>|<span data-ttu-id="cb989-113">Курсор, который отображает или не отображает обновления строк курсора, выполняемые в других соединениях</span><span class="sxs-lookup"><span data-stu-id="cb989-113">Cursor that does or does not show updates to cursor rows made by other connections</span></span>|  
|<span data-ttu-id="cb989-114">SQL_ATTR_CURSOR_SCROLLABLE</span><span class="sxs-lookup"><span data-stu-id="cb989-114">SQL_ATTR_CURSOR_SCROLLABLE</span></span>|<span data-ttu-id="cb989-115">Курсор, который может прокручиваться вперед и назад</span><span class="sxs-lookup"><span data-stu-id="cb989-115">Cursor that can be scrolled forward and backward</span></span>|  
  
 <span data-ttu-id="cb989-116">Значения по умолчанию для этих атрибутов (однопроходный, только для чтения, размер набора строк, равный 1) не используют серверные курсоры.</span><span class="sxs-lookup"><span data-stu-id="cb989-116">The default values for these attributes (forward-only, read-only, rowset size of 1) do not use server cursors.</span></span> <span data-ttu-id="cb989-117">Для использования серверных курсоров по крайней мере одному из этих атрибутов должно быть задано значение, отличное от значения по умолчанию, а выполняемая инструкция должна быть единственной инструкцией SELECT или хранимой процедурой, содержащей единственную инструкцию SELECT.</span><span class="sxs-lookup"><span data-stu-id="cb989-117">To use server cursors, at least one of these attributes must be set to a value other than the default, and the statement being executed must be a single SELECT statement or a stored procedure that contains a single SELECT statement.</span></span> <span data-ttu-id="cb989-118">При использовании серверных курсоров инструкции SELECT не могут использовать предложения, не поддерживаемые серверными курсорами: ВЫЧИСЛЕНие, ВЫЧИСЛЕНие по, для просмотра и в.</span><span class="sxs-lookup"><span data-stu-id="cb989-118">When using server cursors, SELECT statements cannot use clauses not supported by server cursors: COMPUTE, COMPUTE BY, FOR BROWSE, and INTO.</span></span>  
  
 <span data-ttu-id="cb989-119">Используемым типом курсора можно управлять, установив SQL_ATTR_CURSOR_TYPE и SQL_ATTR_CONCURRENCY или установив SQL_ATTR_CURSOR_SENSITIVITY и SQL_ATTR_CURSOR_SCROLLABLE.</span><span class="sxs-lookup"><span data-stu-id="cb989-119">You can control the type of cursor used either by setting SQL_ATTR_CURSOR_TYPE and SQL_ATTR_CONCURRENCY, or by setting SQL_ATTR_CURSOR_SENSITIVITY and SQL_ATTR_CURSOR_SCROLLABLE.</span></span> <span data-ttu-id="cb989-120">Не следует смешивать два метода задания режима работы курсоров.</span><span class="sxs-lookup"><span data-stu-id="cb989-120">You should not mix the two methods of specifying cursor behavior.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb989-121">Пример</span><span class="sxs-lookup"><span data-stu-id="cb989-121">Example</span></span>  
 <span data-ttu-id="cb989-122">В следующем образце выделяется дескриптор инструкции, устанавливается динамический тип курсора и оптимистический параллелизм с управлением версиями строк, а затем выполняется инструкция SELECT.</span><span class="sxs-lookup"><span data-stu-id="cb989-122">The following sample allocates a statement handle, sets a dynamic cursor type with row versioning optimistic concurrency, and then executes a SELECT.</span></span>  
  
```  
retcode = SQLAllocHandle(SQL_HANDLE_STMT, hdbc1, &hstmt1);  
retcode = SQLSetStmtAttr(hstmt1, SQL_ATTR_CURSOR_TYPE, (SQLPOINTER)SQL_CURSOR_DYNAMIC, SQL_IS_INTEGER);  
retcode = SQLSetStmtAttr(hstmt1, SQL_ATTR_CONCURRENCY, SQLPOINTER)SQL_CONCUR_ROWVER, SQL_IS_INTEGER);  
retcode = SQLExecDirect(hstmt1, SELECT au_lname FROM authors", SQL_NTS);  
```  
  
## <a name="example"></a><span data-ttu-id="cb989-123">Пример</span><span class="sxs-lookup"><span data-stu-id="cb989-123">Example</span></span>  
 <span data-ttu-id="cb989-124">В следующем образце выделяется дескриптор инструкции, устанавливается прокручиваемый, чувствительный курсор, а затем выполняется инструкция SELECT.</span><span class="sxs-lookup"><span data-stu-id="cb989-124">The following sample allocates a statement handle, sets a scrollable, sensitive cursor, and then executes a SELECT</span></span>  
  
```  
retcode = SQLAllocHandle(SQL_HANDLE_STMT, hdbc1, &hstmt1);  
  
// Set the cursor options and execute the statement.  
retcode = SQLSetStmtAttr(hstmt1, SQL_ATTR_CURSOR_SCROLLABLE, SQLPOINTER)SQL_SCROLLABLE, SQL_IS_INTEGER);  
retcode = SQLSetStmtAttr(hstmt1, SQL_ATTR_CURSOR_SENSITIVITY, SQLPOINTER)SQL_INSENSITIVE, SQL_IS_INTEGER);  
retcode = SQLExecDirect(hstmt1, select au_lname from authors", SQL_NTS);  
```  
  
## <a name="see-also"></a><span data-ttu-id="cb989-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="cb989-125">See Also</span></span>  
 [<span data-ttu-id="cb989-126">Инструкции по выполнению запросов &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="cb989-126">Executing Queries How-to Topics &#40;ODBC&#41;</span></span>](executing-queries-how-to-topics-odbc.md)  
  
  
