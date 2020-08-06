---
title: SQLExecDirect | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLExecDirect function
ms.assetid: e7c2a5b5-83f4-4c72-9aca-7b9fb4748b11
author: rothja
ms.author: jroth
ms.openlocfilehash: 68188506546e7b4a5dd4c05bc9a94cbf34300001
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658706"
---
# <a name="sqlexecdirect"></a><span data-ttu-id="dba34-102">SQLExecDirect</span><span class="sxs-lookup"><span data-stu-id="dba34-102">SQLExecDirect</span></span>
  <span data-ttu-id="dba34-103">Если атрибут инструкции SQL_SOPT_SS_PARAM_FOCUS не равен 0, SQLExecDirect будет возвращать SQL_ERROR и создавать диагностическую запись с SQLSTATE = HY024 и сообщением "Недопустимое значение атрибута, SQL_SOPT_SS_PARAM_FOCUS (во время выполнения должно быть равно нулю)".</span><span class="sxs-lookup"><span data-stu-id="dba34-103">If the statement attribute SQL_SOPT_SS_PARAM_FOCUS is not 0, SQLExecDirect will return SQL_ERROR and generate a diagnostic record with SQLSTATE=HY024 and the message "Invalid attribute value, SQL_SOPT_SS_PARAM_FOCUS (must be zero at execution time)".</span></span> <span data-ttu-id="dba34-104">Дополнительные сведения об атрибуте SQL_SOPT_SS_PARAM_FOCUS см. в разделе [SQLSetStmtAttr](sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="dba34-104">For more information about SQL_SOPT_SS_PARAM_FOCUS, see [SQLSetStmtAttr](sqlsetstmtattr.md).</span></span>  
  
 <span data-ttu-id="dba34-105">Дополнительные сведения о возвращающих табличное значение параметрах см. в разделе [возвращающие табличное значение параметры &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="dba34-105">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dba34-106">См. также:</span><span class="sxs-lookup"><span data-stu-id="dba34-106">See Also</span></span>  
 <span data-ttu-id="dba34-107">[SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=80709) </span><span class="sxs-lookup"><span data-stu-id="dba34-107">[SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=80709) </span></span>  
 [<span data-ttu-id="dba34-108">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="dba34-108">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
