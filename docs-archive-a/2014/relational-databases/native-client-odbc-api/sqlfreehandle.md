---
title: SQLFreeHandle | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLFreeHandle function
ms.assetid: d374e5c8-ed35-43bf-8dd6-c37e38d9b5f1
author: rothja
ms.author: jroth
ms.openlocfilehash: f51f031bec05715e0345507278113f4f16179a77
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658229"
---
# <a name="sqlfreehandle"></a><span data-ttu-id="93538-102">SQLFreeHandle</span><span class="sxs-lookup"><span data-stu-id="93538-102">SQLFreeHandle</span></span>
  <span data-ttu-id="93538-103">В режиме с фиксацией вручную вызов функции **SQLFreeHandle** при помощи дескриптора инструкции с открытой транзакцией приводит к откату ожидающих обработки изменений в базе данных.</span><span class="sxs-lookup"><span data-stu-id="93538-103">In manual-commit mode, calling **SQLFreeHandle** on a statement handle with an open transaction causes a rollback of pending changes to the database.</span></span> <span data-ttu-id="93538-104">Вызов функции **SQLFreeHandle** применительно к дескриптору инструкции всегда обусловливает закрытие всех открытых курсоров и удаление результатов, ожидающих обработки, что приводит к освобождению всех ресурсов, связанных с дескриптором инструкции.</span><span class="sxs-lookup"><span data-stu-id="93538-104">Calling **SQLFreeHandle** on a statement handle always closes any open cursors and discards pending results, freeing all resources associated with the statement handle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93538-105">См. также:</span><span class="sxs-lookup"><span data-stu-id="93538-105">See Also</span></span>  
 <span data-ttu-id="93538-106">[Функция SQLFreeHandle](https://go.microsoft.com/fwlink/?LinkId=59345) </span><span class="sxs-lookup"><span data-stu-id="93538-106">[SQLFreeHandle Function](https://go.microsoft.com/fwlink/?LinkId=59345) </span></span>  
 [<span data-ttu-id="93538-107">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="93538-107">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
