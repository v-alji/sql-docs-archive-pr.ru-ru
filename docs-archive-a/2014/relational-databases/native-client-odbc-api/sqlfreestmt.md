---
title: SQLFreeStmt | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLFreeStmt function
ms.assetid: d9666d0b-3446-480e-bf1a-10b01213e411
author: rothja
ms.author: jroth
ms.openlocfilehash: d38237b53ed994fd3272f9e129564320f88c6e37
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658228"
---
# <a name="sqlfreestmt"></a><span data-ttu-id="87c9c-102">Функция SQLFreeStmt</span><span class="sxs-lookup"><span data-stu-id="87c9c-102">SQLFreeStmt</span></span>
  <span data-ttu-id="87c9c-103">Не рекомендуется применять функцию**SQLFreeStmt** в ODBC 3.0 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="87c9c-103">**SQLFreeStmt** is not recommended in ODBC 3.0 and later.</span></span> <span data-ttu-id="87c9c-104">Драйвер ODBC собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] поддерживает все определенные значения *Option* для функции **SQLFreeStmt**.</span><span class="sxs-lookup"><span data-stu-id="87c9c-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports all defined *Option* values for **SQLFreeStmt**.</span></span> <span data-ttu-id="87c9c-105">Тем не менее, функции [SQLCloseCursor](sqlclosecursor.md), [SQLBindParameter](sqlbindparameter.md), [SQLBindCol](sqlbindcol.md), **SQLSetDescField**и [SQLFreeHandle](sqlfreehandle.md) заменяют или дублируют функцию **SQLFreeStmt** , и должны использоваться вместо нее.</span><span class="sxs-lookup"><span data-stu-id="87c9c-105">However, [SQLCloseCursor](sqlclosecursor.md), [SQLBindParameter](sqlbindparameter.md), [SQLBindCol](sqlbindcol.md), **SQLSetDescField**, and [SQLFreeHandle](sqlfreehandle.md) replace or duplicate the function of **SQLFreeStmt** and should be used instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87c9c-106">См. также:</span><span class="sxs-lookup"><span data-stu-id="87c9c-106">See Also</span></span>  
 <span data-ttu-id="87c9c-107">[Функция SQLFreeStmt](https://go.microsoft.com/fwlink/?LinkId=59346) </span><span class="sxs-lookup"><span data-stu-id="87c9c-107">[SQLFreeStmt Function](https://go.microsoft.com/fwlink/?LinkId=59346) </span></span>  
 [<span data-ttu-id="87c9c-108">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="87c9c-108">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
