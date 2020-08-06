---
title: SQLSetDescField | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLSetDescField function
ms.assetid: de4bed15-15be-4825-994c-1046255e725a
author: rothja
ms.author: jroth
ms.openlocfilehash: 1b8290fd90c0c9bb91f08d94e119689d38fbc04e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668264"
---
# <a name="sqlsetdescfield"></a><span data-ttu-id="b4df6-102">SQLSetDescField</span><span class="sxs-lookup"><span data-stu-id="b4df6-102">SQLSetDescField</span></span>
  <span data-ttu-id="b4df6-103">SQLSetDescField можно использовать для задания полей дескриптора для возвращающих табличное значение параметров и столбцов возвращающих табличное значение параметров.</span><span class="sxs-lookup"><span data-stu-id="b4df6-103">SQLSetDescField can be used to set descriptor fields for table-valued parameters and table-valued parameter columns.</span></span> <span data-ttu-id="b4df6-104">Сведения о доступных полях см. в разделе [поля дескриптора возвращающего](../native-client-odbc-table-valued-parameters/table-valued-parameter-descriptor-fields.md) табличное значение параметра и [поля дескриптора для составных столбцов возвращающего](../native-client-odbc-table-valued-parameters/descriptor-fields-for-table-valued-parameter-constituent-columns.md)табличное значение параметра.</span><span class="sxs-lookup"><span data-stu-id="b4df6-104">For information about the available fields, see [Table-Valued Parameter Descriptor Fields](../native-client-odbc-table-valued-parameters/table-valued-parameter-descriptor-fields.md) and [Descriptor Fields for Table-Valued Parameter Constituent Columns](../native-client-odbc-table-valued-parameters/descriptor-fields-for-table-valued-parameter-constituent-columns.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4df6-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="b4df6-105">Remarks</span></span>  
 <span data-ttu-id="b4df6-106">Столбцы возвращающих табличное значение параметров доступны только в том случае, когда в поле заголовка дескриптора SQL_SOPT_SS_PARAM_FOCUS задан порядковый номер записи, имеющей тип SQL_DESC_TYPE со значением SQL_SS_TABLE.</span><span class="sxs-lookup"><span data-stu-id="b4df6-106">Table-valued parameter columns are only available when the descriptor header field SQL_SOPT_SS_PARAM_FOCUS is set to the ordinal of a record that has SQL_DESC_TYPE set to SQL_SS_TABLE.</span></span> <span data-ttu-id="b4df6-107">Дополнительные сведения об атрибуте SQL_SOPT_SS_PARAM_FOCUS см. в разделе [SQLSetStmtAttr](sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="b4df6-107">For more information about SQL_SOPT_SS_PARAM_FOCUS, see [SQLSetStmtAttr](sqlsetstmtattr.md).</span></span>  
  
 <span data-ttu-id="b4df6-108">Если предпринимается попытка задать SQL_SOPT_SS_PARAM_FOCUS порядковому номеру параметра, который не является возвращающим табличное значение параметром, SQLSetStmtAttr возвращает SQL_ERROR, а запись диагностики создается с параметром SQLSTATE = HY024 и сообщением "Недопустимый атрибут value".</span><span class="sxs-lookup"><span data-stu-id="b4df6-108">If an attempt is made to set SQL_SOPT_SS_PARAM_FOCUS to the ordinal of a parameter that is not a table-valued parameter, SQLSetStmtAttr returns SQL_ERROR, and a diagnostic record is created with SQLSTATE = HY024 and the message "Invalid attribute value".</span></span> <span data-ttu-id="b4df6-109">Если возвращается значение SQL_ERROR, то атрибут SQL_SOPT_SS_PARAM_FOCUS не меняется.</span><span class="sxs-lookup"><span data-stu-id="b4df6-109">SQL_SOPT_SS_PARAM_FOCUS is not changed when SQL_ERROR is returned.</span></span>  
  
 <span data-ttu-id="b4df6-110">Установка атрибута SQL_SOPT_SS_PARAM_FOCUS в значение 0 восстанавливает доступ к записям дескриптора для параметров.</span><span class="sxs-lookup"><span data-stu-id="b4df6-110">Setting SQL_SOPT_SS_PARAM_FOCUS to 0 restores access to descriptor records for parameters.</span></span>  
  
 <span data-ttu-id="b4df6-111">Дополнительные сведения о возвращающих табличное значение параметрах см. в разделе [возвращающие табличное значение параметры &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="b4df6-111">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="sqlsetdescfield-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="b4df6-112">Поддержка функцией SQLSetDescField улучшенных функций работы с данными в формате даты-времени</span><span class="sxs-lookup"><span data-stu-id="b4df6-112">SQLSetDescField Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="b4df6-113">Функции работы с данными в формате даты-времени были расширены в ODBC.</span><span class="sxs-lookup"><span data-stu-id="b4df6-113">Date/time features have been enhanced in ODBC.</span></span> <span data-ttu-id="b4df6-114">Сведения о поле дескриптора, предоставленном для новых типов даты и времени, см. в разделе [метаданные параметров и результатов](../native-client-odbc-date-time/metadata-parameter-and-result.md).</span><span class="sxs-lookup"><span data-stu-id="b4df6-114">For information about the descriptor field provided for the new date/time types, see [Parameter and Result Metadata](../native-client-odbc-date-time/metadata-parameter-and-result.md).</span></span>  
  
 <span data-ttu-id="b4df6-115">Дополнительные сведения см. в разделе [улучшения даты и времени &#40;&#41;ODBC ](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="b4df6-115">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="sqlsetdescfield-support-for-large-clr-udts"></a><span data-ttu-id="b4df6-116">Поддержка функцией SQLSetDescField определяемых пользователем типов больших данных CLR</span><span class="sxs-lookup"><span data-stu-id="b4df6-116">SQLSetDescField Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="b4df6-117">SQLSetDescField поддерживает большие определяемые пользователем типы данных CLR (UDT).</span><span class="sxs-lookup"><span data-stu-id="b4df6-117">SQLSetDescField supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="b4df6-118">Дополнительные сведения см. в разделе [большие определяемые пользователем типы данных CLR &#40;&#41;ODBC ](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="b4df6-118">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="sqlsetdescfield-support-for-sparse-columns"></a><span data-ttu-id="b4df6-119">Поддержка функцией SQLSetDescField разреженных столбцов</span><span class="sxs-lookup"><span data-stu-id="b4df6-119">SQLSetDescField Support for Sparse Columns</span></span>  
 <span data-ttu-id="b4df6-120">Склсетдекфиелд можно использовать для установки SQL_SOPT_SS_NAME_SCOPE в дескрипторе параметра приложения (APD) на значения SQL_SS_NAME_SCOPE_EXTENDED и SQL_SS_NAME_SCOPE_SPARSE_COLUMN_SET.</span><span class="sxs-lookup"><span data-stu-id="b4df6-120">SQLSetDecField can be used to set SQL_SOPT_SS_NAME_SCOPE in the application parameter descriptor (APD) to the values SQL_SS_NAME_SCOPE_EXTENDED and SQL_SS_NAME_SCOPE_SPARSE_COLUMN_SET.</span></span>  
  
 <span data-ttu-id="b4df6-121">Дополнительные сведения см. в разделе [Поддержка разреженных столбцов &#40;&#41;ODBC ](../native-client/odbc/sparse-columns-support-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="b4df6-121">For more information, see [Sparse Columns Support &#40;ODBC&#41;](../native-client/odbc/sparse-columns-support-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4df6-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="b4df6-122">See Also</span></span>  
 <span data-ttu-id="b4df6-123">[SQLSetDescField](https://go.microsoft.com/fwlink/?LinkId=80705) </span><span class="sxs-lookup"><span data-stu-id="b4df6-123">[SQLSetDescField](https://go.microsoft.com/fwlink/?LinkId=80705) </span></span>  
 [<span data-ttu-id="b4df6-124">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="b4df6-124">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
