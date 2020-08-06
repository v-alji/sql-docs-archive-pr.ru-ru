---
title: SQLGetStmtAttr | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLGetStmtAttr function
ms.assetid: e64f4f94-eb73-4477-9745-080b6cbdc751
author: rothja
ms.author: jroth
ms.openlocfilehash: f1f9b6a0c0668540b566c9b3d7ede781c97a1dbf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664894"
---
# <a name="sqlgetstmtattr"></a><span data-ttu-id="764f4-102">SQLGetStmtAttr</span><span class="sxs-lookup"><span data-stu-id="764f4-102">SQLGetStmtAttr</span></span>
  <span data-ttu-id="764f4-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Драйвер ODBC для собственного клиента расширяет SQLGetStmtAttr для предоставления атрибутов инструкций, относящихся к драйверу.</span><span class="sxs-lookup"><span data-stu-id="764f4-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver extends SQLGetStmtAttr to expose driver-specific statement attributes.</span></span>  
  
 <span data-ttu-id="764f4-104">Функция[SQLSetStmtAttr](sqlsetstmtattr.md) перечисляет атрибуты инструкции, которые можно как считывать, так и изменять.</span><span class="sxs-lookup"><span data-stu-id="764f4-104">[SQLSetStmtAttr](sqlsetstmtattr.md) lists statement attributes that are both read and write.</span></span> <span data-ttu-id="764f4-105">В данном разделе приводятся атрибуты инструкции только для чтения.</span><span class="sxs-lookup"><span data-stu-id="764f4-105">This topic lists the read only statement attributes.</span></span>  
  
## <a name="sql_sopt_ss_current_command"></a><span data-ttu-id="764f4-106">SQL_SOPT_SS_CURRENT_COMMAND</span><span class="sxs-lookup"><span data-stu-id="764f4-106">SQL_SOPT_SS_CURRENT_COMMAND</span></span>  
 <span data-ttu-id="764f4-107">Атрибут SQL_SOPT_SS_CURRENT_COMMAND предоставляет текущую команду пакета команд.</span><span class="sxs-lookup"><span data-stu-id="764f4-107">The SQL_SOPT_SS_CURRENT_COMMAND attribute exposes the current command of a command batch.</span></span> <span data-ttu-id="764f4-108">Возвращение является целым числом, указывающим расположение команды в пакете.</span><span class="sxs-lookup"><span data-stu-id="764f4-108">The return is an integer that specifies the location of the command in the batch.</span></span> <span data-ttu-id="764f4-109">Значение аргумента *ValuePtr* имеет тип SQLLEN.</span><span class="sxs-lookup"><span data-stu-id="764f4-109">The *ValuePtr* value is of type SQLLEN.</span></span>  
  
## <a name="sql_sopt_ss_nocount_status"></a><span data-ttu-id="764f4-110">SQL_SOPT_SS_NOCOUNT_STATUS</span><span class="sxs-lookup"><span data-stu-id="764f4-110">SQL_SOPT_SS_NOCOUNT_STATUS</span></span>  
 <span data-ttu-id="764f4-111">Атрибут SQL_SOPT_SS_NOCOUNT_STATUS указывает текущее значение параметра NOCOUNT, управляющего формированием отчета [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] о числе строк, затронутых инструкцией при вызове метода [SQLRowCount](sqlrowcount.md) .</span><span class="sxs-lookup"><span data-stu-id="764f4-111">The SQL_SOPT_SS_NOCOUNT_STATUS attribute indicates the current setting of the NOCOUNT option, which controls whether [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] reports the numbers of rows affected by a statement when [SQLRowCount](sqlrowcount.md) is called.</span></span> <span data-ttu-id="764f4-112">Значение аргумента *ValuePtr* имеет тип SQLLEN.</span><span class="sxs-lookup"><span data-stu-id="764f4-112">The *ValuePtr* value is of type SQLLEN.</span></span>  
  
|<span data-ttu-id="764f4-113">Значение</span><span class="sxs-lookup"><span data-stu-id="764f4-113">Value</span></span>|<span data-ttu-id="764f4-114">Описание</span><span class="sxs-lookup"><span data-stu-id="764f4-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="764f4-115">SQL_NC_OFF</span><span class="sxs-lookup"><span data-stu-id="764f4-115">SQL_NC_OFF</span></span>|<span data-ttu-id="764f4-116">Значение NOCOUNT — OFF.</span><span class="sxs-lookup"><span data-stu-id="764f4-116">NOCOUNT is OFF.</span></span> <span data-ttu-id="764f4-117">SQLRowCount возвращает число затронутых строк.</span><span class="sxs-lookup"><span data-stu-id="764f4-117">SQLRowCount returns number of rows affected.</span></span>|  
|<span data-ttu-id="764f4-118">SQL_NC_ON</span><span class="sxs-lookup"><span data-stu-id="764f4-118">SQL_NC_ON</span></span>|<span data-ttu-id="764f4-119">Значение NOCOUNT — ON.</span><span class="sxs-lookup"><span data-stu-id="764f4-119">NOCOUNT is ON.</span></span> <span data-ttu-id="764f4-120">Число затронутых строк не возвращается функцией SQLRowCount, а возвращаемое значение равно 0.</span><span class="sxs-lookup"><span data-stu-id="764f4-120">The number of rows affected is not returned by SQLRowCount and the returned value is 0.</span></span>|  
  
 <span data-ttu-id="764f4-121">Если SQLRowCount возвращает 0, приложение должно протестировать SQL_SOPT_SS_NOCOUNT_STATUS.</span><span class="sxs-lookup"><span data-stu-id="764f4-121">If SQLRowCount returns 0, the application should test SQL_SOPT_SS_NOCOUNT_STATUS.</span></span> <span data-ttu-id="764f4-122">Если возвращается SQL_NC_ON, значение 0 из SQLRowCount указывает, что [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не вернул число строк.</span><span class="sxs-lookup"><span data-stu-id="764f4-122">If SQL_NC_ON is returned, the value of 0 from SQLRowCount only indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has not returned a row count.</span></span> <span data-ttu-id="764f4-123">Если возвращается SQL_NC_OFF, значит параметр NOCOUNT отключен и значение 0, возвращаемое функцией SQLRowCount, указывает, что инструкция не затронула ни одной строки.</span><span class="sxs-lookup"><span data-stu-id="764f4-123">If SQL_NC_OFF is returned, it means that NOCOUNT is off and the value of 0 from SQLRowCount indicates that the statement did not affect any rows.</span></span>  
  
 <span data-ttu-id="764f4-124">Приложения не должны отображать значение, возвращаемое функцией SQLRowCount, если параметр SQL_SOPT_SS_NOCOUNT_STATUS установлен в значение SQL_NC_OFF.</span><span class="sxs-lookup"><span data-stu-id="764f4-124">Applications should not display the value of SQLRowCount when SQL_SOPT_SS_NOCOUNT_STATUS is SQL_NC_OFF.</span></span> <span data-ttu-id="764f4-125">Большие пакеты или хранимые процедуры могут содержать несколько инструкций SET NOCOUNT, следовательно, нельзя предположить, что SQL_SOPT_SS_NOCOUNT_STATUS остается неизменным.</span><span class="sxs-lookup"><span data-stu-id="764f4-125">Large batches or stored procedures can contain multiple SET NOCOUNT statements, so it cannot be assumed that SQL_SOPT_SS_NOCOUNT_STATUS remains constant.</span></span> <span data-ttu-id="764f4-126">Этот параметр следует проверять каждый раз, когда SQLRowCount возвращает 0.</span><span class="sxs-lookup"><span data-stu-id="764f4-126">This option should be tested each time SQLRowCount returns 0.</span></span>  
  
## <a name="sql_sopt_ss_querynotification_msgtext"></a><span data-ttu-id="764f4-127">Атрибут SQL_SOPT_SS_QUERYNOTIFICATION_MSGTEXT</span><span class="sxs-lookup"><span data-stu-id="764f4-127">SQL_SOPT_SS_QUERYNOTIFICATION_MSGTEXT</span></span>  
 <span data-ttu-id="764f4-128">Атрибут SQL_SOPT_SS_QUERYNOTIFICATION_MSGTEXT возвращает текст сообщения в ответ на запрошенное уведомление о запросе.</span><span class="sxs-lookup"><span data-stu-id="764f4-128">The SQL_SOPT_SS_QUERYNOTIFICATION_MSGTEXT attribute returns the message text for the query notification request.</span></span>  
  
## <a name="sqlgetstmtattr-and-table-valued-parameters"></a><span data-ttu-id="764f4-129">SQLGetStmtAttr и возвращающие табличное значение параметры</span><span class="sxs-lookup"><span data-stu-id="764f4-129">SQLGetStmtAttr and Table-valued Parameters</span></span>  
 <span data-ttu-id="764f4-130">SQLGetStmtAttr можно вызвать, чтобы получить значение SQL_SOPT_SS_PARAM_FOCUS в дескрипторе параметра приложения (APD) при работе с возвращающими табличные значения параметрами.</span><span class="sxs-lookup"><span data-stu-id="764f4-130">SQLGetStmtAttr can be called to get the value of SQL_SOPT_SS_PARAM_FOCUS in the application parameter descriptor (APD) when working with table-valued parameters.</span></span> <span data-ttu-id="764f4-131">Дополнительные сведения о SQL_SOPT_SS_PARAM_FOCUS см. в разделе [SQLSetStmtAttr](sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="764f4-131">For more information on SQL_SOPT_SS_PARAM_FOCUS, see [SQLSetStmtAttr](sqlsetstmtattr.md).</span></span>  
  
 <span data-ttu-id="764f4-132">Дополнительные сведения о возвращающих табличное значение параметрах см. в разделе [возвращающие табличное значение параметры &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="764f4-132">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="764f4-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="764f4-133">See Also</span></span>  
 <span data-ttu-id="764f4-134">[Функция SQLSetStmtAttr](https://go.microsoft.com/fwlink/?LinkId=59370) </span><span class="sxs-lookup"><span data-stu-id="764f4-134">[SQLSetStmtAttr Function](https://go.microsoft.com/fwlink/?LinkId=59370) </span></span>  
 [<span data-ttu-id="764f4-135">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="764f4-135">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
