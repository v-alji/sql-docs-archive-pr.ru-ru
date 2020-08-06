---
title: Пакеты инструкций | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- statements [ODBC], batches
- batches [ODBC]
- ODBC applications, statements
- multiple statements, batches
- SQLMoreResults function
- SQLExecDirect function
ms.assetid: 057d7c1c-1428-4780-9447-a002ea741188
author: rothja
ms.author: jroth
ms.openlocfilehash: 4818b67766dafe851035041c8fd5137a0dfade73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655128"
---
# <a name="batches-of-statements"></a><span data-ttu-id="f84c6-102">Пакеты инструкций</span><span class="sxs-lookup"><span data-stu-id="f84c6-102">Batches of Statements</span></span>
  <span data-ttu-id="f84c6-103">Пакет [!INCLUDE[tsql](../../../includes/tsql-md.md)] инструкций содержит две или более инструкции, разделенные точкой с запятой (;), встроенными в одну строку, переданную в функцию **SQLExecDirect** или [SQLPrepare](https://go.microsoft.com/fwlink/?LinkId=59360).</span><span class="sxs-lookup"><span data-stu-id="f84c6-103">A batch of [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements contains two or more statements, separated by a semicolon (;), built into a single string passed to **SQLExecDirect** or [SQLPrepare Function](https://go.microsoft.com/fwlink/?LinkId=59360).</span></span> <span data-ttu-id="f84c6-104">Пример:</span><span class="sxs-lookup"><span data-stu-id="f84c6-104">For example:</span></span>  
  
```  
SQLExecDirect(hstmt,   
    "SELECT * FROM Authors; SELECT * FROM Titles",  
    SQL_NTS);  
```  
  
 <span data-ttu-id="f84c6-105">Пакеты могут быть более эффективными, чем отправка инструкций по одной, так как они часто уменьшают требуемый сетевой трафик.</span><span class="sxs-lookup"><span data-stu-id="f84c6-105">Batches can be more efficient than submitting statements separately because network traffic is often reduced.</span></span> <span data-ttu-id="f84c6-106">Используйте [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) , чтобы перейти к следующему результирующему набору по завершении текущего результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="f84c6-106">Use [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) to get positioned on the next result set when finished with the current result set.</span></span>  
  
 <span data-ttu-id="f84c6-107">Пакеты инструкций всегда можно использовать, если атрибуты курсора ODBC установлены по умолчанию (однопроходный курсор только для чтения), а размер набора строк равен 1.</span><span class="sxs-lookup"><span data-stu-id="f84c6-107">Batches can always be used when the ODBC cursor attributes are set to the defaults of a forward-only, read-only cursor with a rowset size of 1.</span></span>  
  
 <span data-ttu-id="f84c6-108">Если инструкция выполняется в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], с помощью серверных курсоров, то серверный курсор неявно преобразуется в результирующий набор по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f84c6-108">If a batch is executed when using server cursors against [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the server cursor is implicitly converted to a default result set.</span></span> <span data-ttu-id="f84c6-109">**SQLExecDirect** или **SQLExecute** возвращают SQL_SUCCESS_WITH_INFO, а вызов **SQLGetDiagRec** возвращает:</span><span class="sxs-lookup"><span data-stu-id="f84c6-109">**SQLExecDirect** or **SQLExecute** return SQL_SUCCESS_WITH_INFO, and a call to **SQLGetDiagRec** returns:</span></span>  
  
```  
szSqlState = "01S02", pfNativeError = 0  
szErrorMsg = "[Microsoft][SQL Server Native Server Native Client]Cursor type changed."  
```  
  
## <a name="see-also"></a><span data-ttu-id="f84c6-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="f84c6-110">See Also</span></span>  
 [<span data-ttu-id="f84c6-111">Исполнение инструкций &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="f84c6-111">Executing Statements &#40;ODBC&#41;</span></span>](executing-statements-odbc.md)  
  
  
