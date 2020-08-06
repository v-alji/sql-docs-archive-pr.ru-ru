---
title: SQLExecute | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLExecute function
ms.assetid: 4d7db8b6-611f-4fe4-be85-2a407059de45
author: rothja
ms.author: jroth
ms.openlocfilehash: 514436c65ef103cafae2189a03b560255b447eda
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658697"
---
# <a name="sqlexecute"></a><span data-ttu-id="b2daf-102">SQLExecute</span><span class="sxs-lookup"><span data-stu-id="b2daf-102">SQLExecute</span></span>
  <span data-ttu-id="b2daf-103">Если атрибуту инструкции SQL_SOPT_SS_PARAM_FOCUS не присвоено значение 0, SQLExecute будет возвращать SQL_ERROR и формировать диагностическую запись с SQLSTATE = HY024 и сообщением "Недопустимое значение атрибута, SQL_SOPT_SS_PARAM_FOCUS (во время выполнения должно быть равно нулю)".</span><span class="sxs-lookup"><span data-stu-id="b2daf-103">If the statement attribute SQL_SOPT_SS_PARAM_FOCUS is not set to 0, SQLExecute will return SQL_ERROR and generate a diagnostic record with SQLSTATE=HY024 and the message "Invalid attribute value, SQL_SOPT_SS_PARAM_FOCUS (must be zero at execution time)".</span></span> <span data-ttu-id="b2daf-104">Дополнительные сведения об атрибуте SQL_SOPT_SS_PARAM_FOCUS см. в разделе [SQLSetStmtAttr](sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="b2daf-104">For more information about SQL_SOPT_SS_PARAM_FOCUS, see [SQLSetStmtAttr](sqlsetstmtattr.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2daf-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="b2daf-105">Remarks</span></span>  
 <span data-ttu-id="b2daf-106">Дополнительные сведения о возвращающих табличное значение параметрах см. в разделе [возвращающие табличное значение параметры &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="b2daf-106">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2daf-107">См. также:</span><span class="sxs-lookup"><span data-stu-id="b2daf-107">See Also</span></span>  
 <span data-ttu-id="b2daf-108">[SQLExecute](https://go.microsoft.com/fwlink/?LinkId=80708) </span><span class="sxs-lookup"><span data-stu-id="b2daf-108">[SQLExecute](https://go.microsoft.com/fwlink/?LinkId=80708) </span></span>  
 [<span data-ttu-id="b2daf-109">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="b2daf-109">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
