---
title: Параллелизм курсоров (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- concurrency [ODBC]
- cursors [ODBC], concurrency
- ODBC cursors, concurrency
ms.assetid: 68228ece-cbf1-4f19-bfdc-053884c1af48
author: rothja
ms.author: jroth
ms.openlocfilehash: c47f24152978fedf8f2c3d49ec3b721969712814
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666561"
---
# <a name="cursor-concurrency-odbc"></a><span data-ttu-id="1f9c8-102">Параллелизм курсоров (ODBC)</span><span class="sxs-lookup"><span data-stu-id="1f9c8-102">Cursor Concurrency (ODBC)</span></span>
  <span data-ttu-id="1f9c8-103">Операции курсора, как и типы курсора, зависят от параметров параллелизма, устанавливаемых приложением.</span><span class="sxs-lookup"><span data-stu-id="1f9c8-103">Cursor operations, like cursor types, are affected by the concurrency options set by the application.</span></span> <span data-ttu-id="1f9c8-104">Параметры параллелизма задаются с помощью параметра SQL_ATTR_CONCURRENCY [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="1f9c8-104">Concurrency options are set using the SQL_ATTR_CONCURRENCY option of [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span></span> <span data-ttu-id="1f9c8-105">Существуют следующие типы параллелизма.</span><span class="sxs-lookup"><span data-stu-id="1f9c8-105">The concurrency types are:</span></span>  
  
-   <span data-ttu-id="1f9c8-106">Только для чтения (SQL_CONCUR_READONLY).</span><span class="sxs-lookup"><span data-stu-id="1f9c8-106">Read-only (SQL_CONCUR_READONLY)</span></span>  
  
-   <span data-ttu-id="1f9c8-107">Значения (SQL_CONCUR_VALUES).</span><span class="sxs-lookup"><span data-stu-id="1f9c8-107">Values (SQL_CONCUR_VALUES)</span></span>  
  
-   <span data-ttu-id="1f9c8-108">Версия строки (SQL_CONCUR_ROWVER).</span><span class="sxs-lookup"><span data-stu-id="1f9c8-108">Row version (SQL_CONCUR_ROWVER)</span></span>  
  
-   <span data-ttu-id="1f9c8-109">Блокировка (SQL_CONCUR_LOCK).</span><span class="sxs-lookup"><span data-stu-id="1f9c8-109">Lock (SQL_CONCUR_LOCK)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f9c8-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="1f9c8-110">See Also</span></span>  
 [<span data-ttu-id="1f9c8-111">Свойства курсора</span><span class="sxs-lookup"><span data-stu-id="1f9c8-111">Cursor Properties</span></span>](cursor-properties.md)  
  
  
