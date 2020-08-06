---
title: SQLProcedures | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLProcedures function
ms.assetid: ec41f017-f5e0-40ef-913a-65d206068631
author: rothja
ms.author: jroth
ms.openlocfilehash: e37f15841a36eb95c1e9263d137ba2734d622367
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668278"
---
# <a name="sqlprocedures"></a><span data-ttu-id="cac63-102">SQLProcedures</span><span class="sxs-lookup"><span data-stu-id="cac63-102">SQLProcedures</span></span>
  <span data-ttu-id="cac63-103">Все хранимые процедуры [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] возвращают какое-либо значение.</span><span class="sxs-lookup"><span data-stu-id="cac63-103">All [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures return a value.</span></span> <span data-ttu-id="cac63-104">**SQLProcedures** reports SQL_PT_FUNCTION для PROCEDURE_TYPE столбца результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="cac63-104">**SQLProcedures** reports SQL_PT_FUNCTION for the result set column PROCEDURE_TYPE.</span></span>  
  
 <span data-ttu-id="cac63-105">**SQLProcedures** возвращает SQL_SUCCESS, существуют ли значения для параметров *CatalogName, SchemaName* или *CNAME* .</span><span class="sxs-lookup"><span data-stu-id="cac63-105">**SQLProcedures** returns SQL_SUCCESS whether or not values exist for *CatalogName, SchemaName,* or *ProcName* parameters.</span></span> <span data-ttu-id="cac63-106">Функция**SQLFetch** возвращает значение SQL_NO_DATA, если в этих параметрах заданы недопустимые значения.</span><span class="sxs-lookup"><span data-stu-id="cac63-106">**SQLFetch** returns SQL_NO_DATA when invalid values are used in these parameters.</span></span>  
  
 <span data-ttu-id="cac63-107">**SQLProcedures** может выполняться на статическом серверном курсоре.</span><span class="sxs-lookup"><span data-stu-id="cac63-107">**SQLProcedures** can be executed on a static server cursor.</span></span> <span data-ttu-id="cac63-108">Попытка выполнить **SQLProcedures** для обновляемого (динамического или ключевого набора ключей) курсора возвратит SQL_SUCCESS_WITH_INFO, указывая, что тип курсора был изменен.</span><span class="sxs-lookup"><span data-stu-id="cac63-108">An attempt to execute **SQLProcedures** on an updatable (dynamic or keyset) cursor will return SQL_SUCCESS_WITH_INFO, indicating that the cursor type has been changed.</span></span>  
  
 <span data-ttu-id="cac63-109">**SQLProcedures** возвращает сведения обо всех процедурах, имена которых совпадают с записями *CNAME* и могут быть выполнены текущим пользователем или для которого текущий пользователь предоставил разрешение View definition.</span><span class="sxs-lookup"><span data-stu-id="cac63-109">**SQLProcedures** returns information about any procedures whose names match *ProcName* and can be executed by the current user, or for which the current user has been granted VIEW DEFINITION permission.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cac63-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="cac63-110">See Also</span></span>  
 <span data-ttu-id="cac63-111">[Функция SQLProcedures](https://go.microsoft.com/fwlink/?LinkId=59364) </span><span class="sxs-lookup"><span data-stu-id="cac63-111">[SQLProcedures Function](https://go.microsoft.com/fwlink/?LinkId=59364) </span></span>  
 [<span data-ttu-id="cac63-112">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="cac63-112">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
