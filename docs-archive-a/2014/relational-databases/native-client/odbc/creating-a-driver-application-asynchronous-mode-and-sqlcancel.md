---
title: Асинхронный режим и SQLCancel | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- asynchronous operations [SQL Server Native Client]
- SQLCancel function
- SQLSetConnectAttr function
- SQL Server Native Client, asynchronous operations
- ODBC functions
- ODBC applications, asynchronous operations
- SQL Server Native Client ODBC driver, asynchronous mode
ms.assetid: f31702a2-df76-4589-ac3b-da5412c03dc2
author: rothja
ms.author: jroth
ms.openlocfilehash: 9071c6821e6edeb577b639223e42899d2927bced
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666519"
---
# <a name="asynchronous-mode-and-sqlcancel"></a><span data-ttu-id="08a17-102">Асинхронный режим и команда SQLCancel</span><span class="sxs-lookup"><span data-stu-id="08a17-102">Asynchronous Mode and SQLCancel</span></span>
  <span data-ttu-id="08a17-103">Некоторые функции ODBC могут работать как синхронно, так и асинхронно.</span><span class="sxs-lookup"><span data-stu-id="08a17-103">Some ODBC functions can operate either synchronously or asynchronously.</span></span> <span data-ttu-id="08a17-104">В приложении могут быть разрешены асинхронные операции как для дескриптора инструкции, так и для дескриптора соединения.</span><span class="sxs-lookup"><span data-stu-id="08a17-104">The application can enable asynchronous operations for either a statement handle or a connection handle.</span></span> <span data-ttu-id="08a17-105">Если параметр установлен для дескриптора соединения, он затрагивает все дескрипторы инструкции в этом дескрипторе соединения.</span><span class="sxs-lookup"><span data-stu-id="08a17-105">If the option is set for a connection handle, it affects all statement handles on the connection handle.</span></span> <span data-ttu-id="08a17-106">Приложение использует следующие инструкции, чтобы включить или отключить асинхронный режим:</span><span class="sxs-lookup"><span data-stu-id="08a17-106">The application uses the following statements to enable or disable asynchronous operations:</span></span>  
  
```  
SQLSetConnectAttr(hdbc, SQL_ATTR_ASYNC_ENABLE,  
                        SQL_ASYNC_ENABLE_ON, SQL_IS_INTEGER);  
SQLSetConnectAttr(hdbc, SQL_ATTR_ASYNC_ENABLE,  
                        SQL_ASYNC_ENABLE_OFF, SQL_IS_INTEGER);  
SQLSetStmtAttr(hstmt, SQL_ATTR_ASYNC_ENABLE,  
                        SQL_ASYNC_ENABLE_ON, SQL_IS_INTEGER);  
SQLSetStmtAttr(hstmt, SQL_ATTR_ASYNC_ENABLE,  
                        SQL_ASYNC_ENABLE_OFF, SQL_IS_INTEGER);  
```  
  
 <span data-ttu-id="08a17-107">Когда приложение вызывает функцию ODBC в синхронном режиме, драйвер не возвращает управление приложению, пока не получит уведомление о том, что сервер завершил выполнение команды.</span><span class="sxs-lookup"><span data-stu-id="08a17-107">When an application calls an ODBC function in synchronous mode, the driver does not return control to the application until it is notified that the server has completed the command.</span></span>  
  
 <span data-ttu-id="08a17-108">В асинхронном режиме драйвер возвращает управление приложению немедленно, даже перед отправкой команды серверу.</span><span class="sxs-lookup"><span data-stu-id="08a17-108">When operating asynchronously, the driver immediately returns control to the application, even before sending the command to the server.</span></span> <span data-ttu-id="08a17-109">Драйвер выставляет код возврата в значение SQL_STILL_EXECUTING.</span><span class="sxs-lookup"><span data-stu-id="08a17-109">The driver sets the return code to SQL_STILL_EXECUTING.</span></span> <span data-ttu-id="08a17-110">Приложение может выполнять другую работу.</span><span class="sxs-lookup"><span data-stu-id="08a17-110">The application can then perform other work.</span></span>  
  
 <span data-ttu-id="08a17-111">Когда приложение проверяет завершение выполнения команды, делается тот же вызов функции с теми же параметрами для драйвера.</span><span class="sxs-lookup"><span data-stu-id="08a17-111">When the application tests for completion of the command, it makes the same function call with the same parameters to the driver.</span></span> <span data-ttu-id="08a17-112">Если драйвер еще не получил ответ от сервера, он опять вернет значение SQL_STILL_EXECUTING.</span><span class="sxs-lookup"><span data-stu-id="08a17-112">If the driver has not yet received an answer from the server, it will again return SQL_STILL_EXECUTING.</span></span> <span data-ttu-id="08a17-113">Приложение должно проверять команду периодически до тех пор, пока код возврата не станет отличен от SQL_STILL_EXECUTING.</span><span class="sxs-lookup"><span data-stu-id="08a17-113">The application must test the command periodically until the return code is something other than SQL_STILL_EXECUTING.</span></span> <span data-ttu-id="08a17-114">Когда приложение получает любой другой код возврата, даже SQL_ERROR, оно может определить, что выполнение команды завершено.</span><span class="sxs-lookup"><span data-stu-id="08a17-114">When the application gets some other return code, even SQL_ERROR, it can determine that the command has completed.</span></span>  
  
 <span data-ttu-id="08a17-115">Иногда команда остается необработанной долгое время.</span><span class="sxs-lookup"><span data-stu-id="08a17-115">Sometimes a command is outstanding for a long time.</span></span> <span data-ttu-id="08a17-116">Если приложению нужно отменить команду, не дожидаясь ответа, это можно сделать, вызвав **SQLCancel** с тем же маркером инструкции, что и у необработанной команды.</span><span class="sxs-lookup"><span data-stu-id="08a17-116">If the application needs to cancel the command without waiting for a reply, it can do so by calling **SQLCancel** with the same statement handle as the outstanding command.</span></span> <span data-ttu-id="08a17-117">Это единственный момент, когда следует использовать **SQLCancel** .</span><span class="sxs-lookup"><span data-stu-id="08a17-117">This is the only time **SQLCancel** should be used.</span></span> <span data-ttu-id="08a17-118">Некоторые программисты используют **SQLCancel** , когда они обрабатывали фрагменты в результирующем наборе и хотят отменить оставшуюся часть результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="08a17-118">Some programmers use **SQLCancel** when they have processed part way through a result set and want to cancel the rest of the result set.</span></span> <span data-ttu-id="08a17-119">[SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) или [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) следует использовать для отмены оставшейся части необработанного результирующего набора, а не **SQLCancel**.</span><span class="sxs-lookup"><span data-stu-id="08a17-119">[SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) or [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) should be used to cancel the remainder of an outstanding result set, not **SQLCancel**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08a17-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="08a17-120">See Also</span></span>  
 [<span data-ttu-id="08a17-121">Создание драйвера ODBC для собственного клиента SQL Server</span><span class="sxs-lookup"><span data-stu-id="08a17-121">Creating a SQL Server Native Client ODBC Driver Application</span></span>](creating-a-driver-application.md)  
  
  
