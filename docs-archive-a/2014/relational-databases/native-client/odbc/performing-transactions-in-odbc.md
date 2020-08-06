---
title: Транзакции в ODBC | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, transactions
- transactions [ODBC]
- ODBC, transactions
ms.assetid: c5a87fa5-827a-4e6f-a0d9-924bac881eb0
author: rothja
ms.author: jroth
ms.openlocfilehash: 386b248edfdb6e0ac5eb97b3aeb6c0bbc505a5a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657066"
---
# <a name="transactions-in-odbc"></a><span data-ttu-id="286a7-102">Транзакции в ODBC</span><span class="sxs-lookup"><span data-stu-id="286a7-102">Transactions in ODBC</span></span>
  <span data-ttu-id="286a7-103">Управление транзакциями в ODBC выполняется на уровне соединения.</span><span class="sxs-lookup"><span data-stu-id="286a7-103">Transactions in ODBC are managed at the connection level.</span></span> <span data-ttu-id="286a7-104">Когда приложение завершает транзакцию, оно фиксирует или откатывает назад все операции со всеми инструкциями, хранящими дескриптор данного соединения.</span><span class="sxs-lookup"><span data-stu-id="286a7-104">When an application completes a transaction, it commits or rolls back all work completed through all statement handles on that connection.</span></span> <span data-ttu-id="286a7-105">Для фиксации или отката транзакции приложения должны вызывать метод [SQLEndTran](../../native-client-odbc-api/sqlendtran.md) вместо непосредственного выполнения инструкции COMMIT или ROLLBACK.</span><span class="sxs-lookup"><span data-stu-id="286a7-105">To commit or roll back a transaction, applications should call [SQLEndTran](../../native-client-odbc-api/sqlendtran.md) instead of submitting a COMMIT or ROLLBACK statement.</span></span>  
  
 <span data-ttu-id="286a7-106">Для переключения между двумя режимами управления транзакциями, которые применяются в ODBC, используется метод [SQLSetConnectAttr](../../native-client-odbc-api/sqlsetconnectattr.md) .</span><span class="sxs-lookup"><span data-stu-id="286a7-106">An application calls [SQLSetConnectAttr](../../native-client-odbc-api/sqlsetconnectattr.md) to switch between the two ODBC modes of managing transactions:</span></span>  
  
-   <span data-ttu-id="286a7-107">Режим автоматической фиксации</span><span class="sxs-lookup"><span data-stu-id="286a7-107">Autocommit mode</span></span>  
  
     <span data-ttu-id="286a7-108">Каждая отдельная инструкция языка автоматически фиксируется после успешного завершения.</span><span class="sxs-lookup"><span data-stu-id="286a7-108">Each statement is automatically committed when it is completed successfully.</span></span> <span data-ttu-id="286a7-109">При работе в режиме автоматической фиксации других средств управления транзакциями не требуется.</span><span class="sxs-lookup"><span data-stu-id="286a7-109">When you run in autocommit mode, no other transaction management functions are required.</span></span>  
  
-   <span data-ttu-id="286a7-110">Режим ручной фиксации</span><span class="sxs-lookup"><span data-stu-id="286a7-110">Manual-commit mode</span></span>  
  
     <span data-ttu-id="286a7-111">Все выполненные инструкции будут включены в одну и ту же транзакцию, если ее не прекратить явным образом, вызвав **SQLEndTran**.</span><span class="sxs-lookup"><span data-stu-id="286a7-111">All executed statements are included in the same transaction until it is specifically stopped by calling **SQLEndTran**.</span></span>  
  
 <span data-ttu-id="286a7-112">Режим автоматической фиксации применяется в ODBC по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="286a7-112">Autocommit mode is the default transaction mode for ODBC.</span></span> <span data-ttu-id="286a7-113">Любое новое соединение находится в режиме автоматической фиксации, пока не будет вызван метод **SQLSetConnectAttr** для перехода в режим ручной фиксации.</span><span class="sxs-lookup"><span data-stu-id="286a7-113">When a connection is made, it is in autocommit mode until **SQLSetConnectAttr** is called to switch to manual-commit mode by setting autocommit mode off.</span></span> <span data-ttu-id="286a7-114">Когда приложение отключает режим автоматической фиксации, следующая инструкция, введенная в базу данных, начнет транзакцию.</span><span class="sxs-lookup"><span data-stu-id="286a7-114">When an application turns autocommit off, the next statement sent to the database starts a transaction.</span></span> <span data-ttu-id="286a7-115">Эта транзакция остается в силе, пока приложение не вызовет функцию **SQLEndTran** с параметром SQL_COMMIT либо SQL_ROLLBACK.</span><span class="sxs-lookup"><span data-stu-id="286a7-115">The transaction then remains in effect until the application calls **SQLEndTran** with either the SQL_COMMIT or SQL_ROLLBACK options.</span></span> <span data-ttu-id="286a7-116">Команда, посланная в базу данных после вызова функции **SQLEndTran** , начинает новую транзакцию.</span><span class="sxs-lookup"><span data-stu-id="286a7-116">The command sent to the database after **SQLEndTran** starts the next transaction.</span></span>  
  
 <span data-ttu-id="286a7-117">Если приложение переключается с режима ручной фиксации на автоматическую, драйвер фиксирует все транзакции, открытые в этот момент для данного соединения.</span><span class="sxs-lookup"><span data-stu-id="286a7-117">If an application switches from manual-commit to autocommit mode, the driver commits any transactions currently open on the connection.</span></span>  
  
 <span data-ttu-id="286a7-118">Приложения ODBC не должны использовать инструкции языка Transact-SQL, такие как BEGIN TRANSACTION, COMMIT TRANSACTION и ROLLBACK TRANSACTION, потому что это может привести к ситуации, когда поведение драйвера не определено.</span><span class="sxs-lookup"><span data-stu-id="286a7-118">ODBC applications should not use Transact-SQL transaction statements such as BEGIN TRANSACTION, COMMIT TRANSACTION, or ROLLBACK TRANSACTION because this can cause indeterminate behavior in the driver.</span></span> <span data-ttu-id="286a7-119">Приложение ODBC должно выполняться в режиме автоматической фиксации и не использовать никаких функций или инструкций для управления транзакциями или работать в режиме ручной фиксации и использовать функцию ODBC **SQLEndTran** для фиксации и отката транзакций.</span><span class="sxs-lookup"><span data-stu-id="286a7-119">An ODBC application should run in autocommit mode and not use any transaction management functions or statements, or run in manual-commit mode and use the ODBC **SQLEndTran** function to either commit or roll back transactions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="286a7-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="286a7-120">See Also</span></span>  
 [<span data-ttu-id="286a7-121">Выполнение транзакций &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="286a7-121">Performing Transactions &#40;ODBC&#41;</span></span>](../../../database-engine/dev-guide/performing-transactions-odbc.md)  
  
  
