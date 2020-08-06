---
title: Освобождение маркера инструкции | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- reusing statement handles
- freeing statement handles
- statements [ODBC], statement handles
- SQLFreeStmt function
- ODBC applications, statements
- statement handles [ODBC]
ms.assetid: 96fdff84-0ca7-460a-a240-94ee826ea41c
author: rothja
ms.author: jroth
ms.openlocfilehash: 8d7a1e93d222e2b87058bc878f7eca85313b4108
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655114"
---
# <a name="freeing-a-statement-handle"></a><span data-ttu-id="8d167-102">Освобождение дескриптора инструкции</span><span class="sxs-lookup"><span data-stu-id="8d167-102">Freeing a Statement Handle</span></span>
  <span data-ttu-id="8d167-103">Многократное использование дескрипторов инструкций значительно эффективнее, чем их удаление и повторное выделение.</span><span class="sxs-lookup"><span data-stu-id="8d167-103">It is more efficient to reuse statement handles than to drop them and allocate new ones.</span></span> <span data-ttu-id="8d167-104">Перед выполнением новой инструкции SQL через дескриптор приложение должно проверить правильность текущих параметров инструкции,</span><span class="sxs-lookup"><span data-stu-id="8d167-104">Before executing a new SQL statement on a statement handle, applications should verify that the current statement settings are appropriate.</span></span> <span data-ttu-id="8d167-105">в частности атрибуты инструкции, привязки параметров и привязки результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="8d167-105">These include statement attributes, parameter bindings, and result set bindings.</span></span> <span data-ttu-id="8d167-106">Как правило, параметры и результирующие наборы для старой инструкции SQL должны быть отменены путем вызова [SQLFreeStmt](../native-client-odbc-api/sqlfreestmt.md) с параметрами SQL_RESET_PARAMS и SQL_UNBIND и повторной привязки для новой инструкции SQL.</span><span class="sxs-lookup"><span data-stu-id="8d167-106">Generally, parameters and result sets for the old SQL statement must be unbound by calling [SQLFreeStmt](../native-client-odbc-api/sqlfreestmt.md) with the SQL_RESET_PARAMS and SQL_UNBIND options and then re-bound for the new SQL statement.</span></span>  
  
 <span data-ttu-id="8d167-107">Когда приложение завершит работу с инструкцией, оно вызывает [SQLFreeHandle](../native-client-odbc-api/sqlfreehandle.md) , чтобы освободить инструкцию.</span><span class="sxs-lookup"><span data-stu-id="8d167-107">When the application has finished using the statement, it calls [SQLFreeHandle](../native-client-odbc-api/sqlfreehandle.md) to free the statement.</span></span> <span data-ttu-id="8d167-108">Обратите внимание, что **SQLDisconnect** автоматически освобождает все инструкции по соединению.</span><span class="sxs-lookup"><span data-stu-id="8d167-108">Note that **SQLDisconnect** automatically frees all statements on a connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d167-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="8d167-109">See Also</span></span>  
 [<span data-ttu-id="8d167-110">Выполняя запросы &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="8d167-110">Executing Queries &#40;ODBC&#41;</span></span>](executing-queries-odbc.md)  
  
  
