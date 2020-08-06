---
title: SQLCancel | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLCancel function
ms.assetid: d4c965ae-c1ac-4e9d-b4b9-32b561401106
author: rothja
ms.author: jroth
ms.openlocfilehash: dc3d86229501f80b25fb077788d1835a5f4f5c96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658708"
---
# <a name="sqlcancel"></a><span data-ttu-id="7c65f-102">SQLCancel</span><span class="sxs-lookup"><span data-stu-id="7c65f-102">SQLCancel</span></span>
  <span data-ttu-id="7c65f-103">В разделе [SQLCancel](https://go.microsoft.com/fwlink/?LinkId=203516) говорится о том, что в ODBC 2. x, если приложение вызывает, `SQLCancel` когда в инструкции не выполняется обработка, `SQLCancel` имеет тот же результат, что `SQLFreeStmt` `SQL_CLOSE` и параметр. это поведение определено только для полноты, и приложения должны вызывать `SQLFreeStmt` или `SQLCloseCursor` закрывать курсоры.</span><span class="sxs-lookup"><span data-stu-id="7c65f-103">The [SQLCancel](https://go.microsoft.com/fwlink/?LinkId=203516) topic says that in ODBC 2.x, if an application calls `SQLCancel` when no processing is being done on the statement, `SQLCancel` has the same effect as `SQLFreeStmt` with the `SQL_CLOSE` option; this behavior is defined only for completeness and applications should call `SQLFreeStmt` or `SQLCloseCursor` to close cursors.</span></span> <span data-ttu-id="7c65f-104">Но даже если приложение собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] имеет версию ODBC API 3.5.x или более позднюю, функция `SQLCancel` будет использовать поведение ODBC 2.x.</span><span class="sxs-lookup"><span data-stu-id="7c65f-104">But even if your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client application sets the ODBC API version to be 3.5.x or later, the `SQLCancel` function will use the ODBC 2.x behavior.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c65f-105">См. также:</span><span class="sxs-lookup"><span data-stu-id="7c65f-105">See Also</span></span>  
 <span data-ttu-id="7c65f-106">[SQLCancel](https://go.microsoft.com/fwlink/?LinkId=203516) </span><span class="sxs-lookup"><span data-stu-id="7c65f-106">[SQLCancel](https://go.microsoft.com/fwlink/?LinkId=203516) </span></span>  
 [<span data-ttu-id="7c65f-107">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="7c65f-107">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
