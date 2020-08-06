---
title: Использование SQL Server результирующих наборов по умолчанию | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLSetStmtAttr function
- ODBC cursors, default result sets
- cursors [ODBC], default result sets
- default result sets
- result sets [ODBC], default
- ODBC applications, cursors
ms.assetid: ee1db3e5-60eb-4425-8a6b-977eeced3f98
author: rothja
ms.author: jroth
ms.openlocfilehash: 18cd10dd95329f68a42497d2bea5ce63f345ceff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657777"
---
# <a name="using-sql-server-default-result-sets"></a><span data-ttu-id="7dddc-102">Использование результирующих наборов по умолчанию в SQL Server</span><span class="sxs-lookup"><span data-stu-id="7dddc-102">Using SQL Server Default Result Sets</span></span>
  <span data-ttu-id="7dddc-103">Атрибутами курсора ODBC по умолчанию являются:</span><span class="sxs-lookup"><span data-stu-id="7dddc-103">The default ODBC cursor attributes are:</span></span>  
  
```  
SQLSetStmtAttr(hstmt, SQL_ATTR_CURSOR_TYPE, SQL_CURSOR_FORWARD_ONLY, SQL_IS_INTEGER);  
SQLSetStmtAttr(hstmt, SQL_ATTR_CONCURRENCY, SQL_CONCUR_READ_ONLY, SQL_IS_INTEGER);  
SQLSetStmtAttr(hstmt, SQL_ATTR_ROW_ARRAY_SIZE, 1, SQL_IS_INTEGER);  
```  
  
 <span data-ttu-id="7dddc-104">Если для этих атрибутов заданы значения по умолчанию, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] драйвер ODBC для собственного клиента использует [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] результирующий набор по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7dddc-104">Whenever these attributes are set to their defaults, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver uses a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] default result set.</span></span> <span data-ttu-id="7dddc-105">Результирующие наборы по умолчанию могут использоваться для любой инструкции SQL, поддерживаемой [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], и являются самым эффективным методом передачи всего результирующего набора клиенту.</span><span class="sxs-lookup"><span data-stu-id="7dddc-105">Default result sets can be used for any SQL statement supported by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], and are the most efficient method of transferring an entire result set to the client.</span></span>  
  
 [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]<span data-ttu-id="7dddc-106">Добавлена поддержка множественных активных результирующих наборов (MARS). у приложений теперь может быть несколько активных результирующих наборов по умолчанию для каждого подключения.</span><span class="sxs-lookup"><span data-stu-id="7dddc-106">introduced support for multiple active result sets (MARS); applications can now have more than one active default result set per connection.</span></span> <span data-ttu-id="7dddc-107">По умолчанию режим MARS не включен.</span><span class="sxs-lookup"><span data-stu-id="7dddc-107">MARS is not enabled by default.</span></span>  
  
 <span data-ttu-id="7dddc-108">До версии [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] принимаемые по умолчанию результирующие наборы не поддерживали несколько активных инструкций для одного соединения.</span><span class="sxs-lookup"><span data-stu-id="7dddc-108">Before [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], default result sets did not support multiple active statements on the same connection.</span></span> <span data-ttu-id="7dddc-109">После выполнения инструкции SQL для соединения сервер не принимает команд от клиента в этом соединении до тех пор, пока не будут обработаны все строки результирующего набора. Исключение составляют запросы на отмену оставшейся части результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="7dddc-109">After an SQL statement is executed on a connection, the server does not accept commands (except a request to cancel the rest of the result set) from the client on that connection until all the rows in the result set have been processed.</span></span> <span data-ttu-id="7dddc-110">Чтобы отменить оставшуюся часть частично обработанного результирующего набора, вызовите [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) или [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) , указав для параметра *параметром fOption* значение SQL_CLOSE.</span><span class="sxs-lookup"><span data-stu-id="7dddc-110">To cancel the remainder of a partially processed result set, call [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) or [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) with the *fOption* parameter set to SQL_CLOSE.</span></span> <span data-ttu-id="7dddc-111">Чтобы завершить частично обработанный результирующий набор и проверить наличие другого результирующего набора, вызовите [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md).</span><span class="sxs-lookup"><span data-stu-id="7dddc-111">To finish a partially processed result set and test for the presence of another result set, call [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md).</span></span> <span data-ttu-id="7dddc-112">Если приложение ODBC пытается выполнить команду в обработчике соединения до того, как результирующий набор по умолчанию будет полностью обработан, вызов создает SQL_ERROR и вызов **SQLGetDiagRec** возвращает:</span><span class="sxs-lookup"><span data-stu-id="7dddc-112">If an ODBC application attempts a command on a connection handle before a default result set has been completely processed, the call generates SQL_ERROR and a call to **SQLGetDiagRec** returns:</span></span>  
  
```  
szSqlState: "HY000", pfNativeError: 0  
szErrorMsg: "[Microsoft][SQL Server Native Client]  
                Connection is busy with results for another hstmt."  
```  
  
## <a name="see-also"></a><span data-ttu-id="7dddc-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="7dddc-113">See Also</span></span>  
 [<span data-ttu-id="7dddc-114">Способы реализации курсоров</span><span class="sxs-lookup"><span data-stu-id="7dddc-114">How Cursors Are Implemented</span></span>](how-cursors-are-implemented.md)  
  
  
