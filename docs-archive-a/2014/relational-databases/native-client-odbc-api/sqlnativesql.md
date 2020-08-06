---
title: SQLNativeSql | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLNativeSql function
ms.assetid: 2d999fec-9e22-4514-ad5f-22a64b82f95b
author: rothja
ms.author: jroth
ms.openlocfilehash: 433b086dc36a79cb82868edebac9f0a4814c21fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668283"
---
# <a name="sqlnativesql"></a><span data-ttu-id="3297f-102">SQLNativeSql</span><span class="sxs-lookup"><span data-stu-id="3297f-102">SQLNativeSql</span></span>
  <span data-ttu-id="3297f-103">Драйвер ODBC собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] удовлетворяет запросы **SQLNativeSql** , не заходя на сервер.</span><span class="sxs-lookup"><span data-stu-id="3297f-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver satisfies **SQLNativeSql** requests without visiting the server.</span></span> <span data-ttu-id="3297f-104">Эта функция выполняет эффективную проверку синтаксиса инструкций SQL.</span><span class="sxs-lookup"><span data-stu-id="3297f-104">The function efficiently tests the syntax of SQL statements.</span></span> <span data-ttu-id="3297f-105">При проверке синтаксиса не устанавливается допустимость идентификаторов или результатов выражений в инструкциях SQL, а выполнение собственного SQL [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , возвращенного функцией **SQLNativeSql** , может завершиться неудачей.</span><span class="sxs-lookup"><span data-stu-id="3297f-105">Syntax checking does not determine if identifiers or the results of expressions in the SQL statements are valid, and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native SQL returned by **SQLNativeSql** can fail to run.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3297f-106">См. также:</span><span class="sxs-lookup"><span data-stu-id="3297f-106">See Also</span></span>  
 <span data-ttu-id="3297f-107">[Функция SQLNativeSql](https://go.microsoft.com/fwlink/?LinkID=59358) </span><span class="sxs-lookup"><span data-stu-id="3297f-107">[SQLNativeSql Function](https://go.microsoft.com/fwlink/?LinkID=59358) </span></span>  
 [<span data-ttu-id="3297f-108">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="3297f-108">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
