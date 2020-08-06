---
title: Неявные преобразования курсора (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC cursors, implicit cursor conversions
- implicit cursor conversions
- cursors [ODBC], implicit cursor conversions
ms.assetid: fe29a58d-8448-4512-9ffd-b414784ba338
author: rothja
ms.author: jroth
ms.openlocfilehash: ff8350c71a853e39ff1d35a1f3fba6e8e1944934
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666559"
---
# <a name="implicit-cursor-conversions-odbc"></a><span data-ttu-id="d1701-102">Неявные преобразования курсора (ODBC)</span><span class="sxs-lookup"><span data-stu-id="d1701-102">Implicit Cursor Conversions (ODBC)</span></span>
  <span data-ttu-id="d1701-103">Приложения могут запрашивать тип курсора через [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) , а затем выполнять инструкцию SQL, которая не поддерживается серверными курсорами запрошенного типа.</span><span class="sxs-lookup"><span data-stu-id="d1701-103">Applications can request a cursor type through [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) and then execute an SQL statement that is not supported by server cursors of the type requested.</span></span> <span data-ttu-id="d1701-104">Вызов **SQLExecute** или **SQLExecDirect** возвращает SQL_SUCCESS_WITH_INFO и **SQLGetDiagRec** возвращает:</span><span class="sxs-lookup"><span data-stu-id="d1701-104">A call to **SQLExecute** or **SQLExecDirect** returns SQL_SUCCESS_WITH_INFO and **SQLGetDiagRec** returns:</span></span>  
  
```  
szSqlState = "01S02", *pfNativeError = 0,  
szErrorMsg="[Microsoft][SQL Server Native Client] Cursor type changed"  
```  
  
 <span data-ttu-id="d1701-105">Приложение может определить, какой тип курсора теперь используется, вызвав **SQLGetStmtOption** в значение SQL_CURSOR_TYPE.</span><span class="sxs-lookup"><span data-stu-id="d1701-105">The application can determine what type of cursor is now being used by calling **SQLGetStmtOption** set to SQL_CURSOR_TYPE.</span></span> <span data-ttu-id="d1701-106">Преобразование типа курсора применяется только к одной инструкции.</span><span class="sxs-lookup"><span data-stu-id="d1701-106">The cursor type conversion applies to only one statement.</span></span> <span data-ttu-id="d1701-107">Следующие **SQLExecDirect** или **SQLExecute** будут выполняться с использованием параметров курсора исходной инструкции.</span><span class="sxs-lookup"><span data-stu-id="d1701-107">The next **SQLExecDirect** or **SQLExecute** will be done using the original statement cursor settings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1701-108">См. также:</span><span class="sxs-lookup"><span data-stu-id="d1701-108">See Also</span></span>  
 [<span data-ttu-id="d1701-109">Сведения о программировании курсора &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="d1701-109">Cursor Programming Details &#40;ODBC&#41;</span></span>](cursor-programming-details-odbc.md)  
  
  
