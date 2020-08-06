---
title: Тип ODBC SQL для возвращающих табличное значение параметров | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL_SS_TABLE
ms.assetid: 6725bfb9-5f10-4115-be09-fd9c9f5779ea
author: rothja
ms.author: jroth
ms.openlocfilehash: c8ed46bf117c9158ae5b60c10ebd89e3d348f77c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667075"
---
# <a name="odbc-sql-type-for-table-valued-parameters"></a><span data-ttu-id="5f67d-102">Тип ODBC SQL для параметров, возвращающих табличное значение</span><span class="sxs-lookup"><span data-stu-id="5f67d-102">ODBC SQL Type for Table-Valued Parameters</span></span>
  <span data-ttu-id="5f67d-103">Поддержка возвращающих табличное значение параметров обеспечивается новым типом ODBC SQL — SQL_SS_TABLE.</span><span class="sxs-lookup"><span data-stu-id="5f67d-103">Support for table-valued parameters is provided by a new ODBC SQL type, SQL_SS_TABLE.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f67d-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="5f67d-104">Remarks</span></span>  
 <span data-ttu-id="5f67d-105">Тип SQL_SS_TABLE нельзя преобразовать в любой другой тип данных ODBC или [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5f67d-105">SQL_SS_TABLE cannot be converted to any other ODBC or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type.</span></span>  
  
 <span data-ttu-id="5f67d-106">Если SQL_SS_TABLE используется в качестве типа данных C в параметре *ValueType* SQLBindParameter или предпринимается попытка установить SQL_DESC_TYPE в записи дескриптора параметра приложения (APD) в SQL_SS_TABLE, возвращается SQL_ERROR и создается диагностическая запись с параметром SQLSTATE = HY003, "Недопустимый тип буфера приложения".</span><span class="sxs-lookup"><span data-stu-id="5f67d-106">If SQL_SS_TABLE is used as a C data type in the *ValueType* parameter of SQLBindParameter, or an attempt is made to set SQL_DESC_TYPE in an application parameter descriptor (APD) record to SQL_SS_TABLE, SQL_ERROR is returned and a diagnostic record is generated with SQLSTATE=HY003, "Invalid application buffer type".</span></span>  
  
 <span data-ttu-id="5f67d-107">Если SQL_DESC_TYPE устанавливается в IPD-записи в значение SQL_SS_TABLE, а соответствующая запись дескриптора параметра приложения не SQL_C_DEFAULT, то возвращается значение SQL_ERROR и создается диагностическая запись с кодом SQLSTATE=HY003 и сообщением «Недопустимый тип буфера приложения».</span><span class="sxs-lookup"><span data-stu-id="5f67d-107">If SQL_DESC_TYPE is set to SQL_SS_TABLE in an IPD record and the corresponding application parameter descriptor record is not SQL_C_DEFAULT, SQL_ERROR is returned and a diagnostic record is generated with SQLSTATE=HY003, "Invalid application buffer type".</span></span> <span data-ttu-id="5f67d-108">Это может произойти с *ParameterType* SQLSetDescField, SQLSetDescRec или SQLBindParameter.</span><span class="sxs-lookup"><span data-stu-id="5f67d-108">This can occur with the *ParameterType* of a SQLSetDescField, SQLSetDescRec or SQLBindParameter.</span></span>  
  
 <span data-ttu-id="5f67d-109">Если параметр *TargetType* SQL_SS_TABLE при вызове SQLGetData, возвращается SQL_ERROR и создается диагностическая запись с параметром SQLSTATE = HY003, "Недопустимый тип буфера приложения".</span><span class="sxs-lookup"><span data-stu-id="5f67d-109">If the *TargetType* parameter is SQL_SS_TABLE when calling SQLGetData, SQL_ERROR is returned and a diagnostic record is generated with SQLSTATE=HY003, "Invalid application buffer type".</span></span>  
  
 <span data-ttu-id="5f67d-110">Столбец возвращающего табличное значение параметра не может привязываться в виде типа SQL_SS_TABLE.</span><span class="sxs-lookup"><span data-stu-id="5f67d-110">A table-valued parameter column cannot be bound as type SQL_SS_TABLE.</span></span> <span data-ttu-id="5f67d-111">Если `SQLBindParameter` метод вызывается с параметром *ParameterType* , для которого задано значение SQL_SS_TABLE, возвращается SQL_ERROR и создается диагностическая запись с параметром SQLSTATE = HY004, "Недопустимый тип данных SQL".</span><span class="sxs-lookup"><span data-stu-id="5f67d-111">If `SQLBindParameter` is called with *ParameterType* set to SQL_SS_TABLE, SQL_ERROR is returned and a diagnostic record is generated with SQLSTATE=HY004, "Invalid SQL data type".</span></span> <span data-ttu-id="5f67d-112">Это также может произойти с SQLSetDescField и SQLSetDescRec.</span><span class="sxs-lookup"><span data-stu-id="5f67d-112">This can also occur with SQLSetDescField and SQLSetDescRec.</span></span>  
  
 <span data-ttu-id="5f67d-113">Значения столбца возвращающего табличные значения параметра имеют те же возможности преобразования данных, как параметры и результирующие столбцы.</span><span class="sxs-lookup"><span data-stu-id="5f67d-113">Table-valued parameter column values have the same data conversion options as parameters and result columns.</span></span>  
  
 <span data-ttu-id="5f67d-114">В [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] и более поздних версиях возвращающий табличное значение параметр может быть только входным параметром.</span><span class="sxs-lookup"><span data-stu-id="5f67d-114">A table-valued parameter can only be an input parameter in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] or later.</span></span> <span data-ttu-id="5f67d-115">Если предпринимается попытка задать для SQL_DESC_PARAMETER_TYPE значение, отличное от SQL_PARAM_INPUT через SQLBindParameter или SQLSetDescField, возвращается SQL_ERROR, а в инструкцию с SQLSTATE = HY105 и сообщением «Недопустимый тип параметра» добавляется запись диагностики.</span><span class="sxs-lookup"><span data-stu-id="5f67d-115">If an attempt is made to set SQL_DESC_PARAMETER_TYPE to a value other than SQL_PARAM_INPUT via SQLBindParameter or SQLSetDescField, SQL_ERROR is returned and a diagnostic record is added to the statement with SQLSTATE=HY105 and the message "Invalid parameter type".</span></span>  
  
 <span data-ttu-id="5f67d-116">Столбцы возвращающего табличное значение параметра не могут использовать в качестве параметра *StrLen_or_IndPtr*значение SQL_DEFAULT_PARAM, так как значения по умолчанию не поддерживаются возвращающими табличное значение параметрами.</span><span class="sxs-lookup"><span data-stu-id="5f67d-116">Table-valued parameter columns cannot use SQL_DEFAULT_PARAM in *StrLen_or_IndPtr*, because per-row default values are not supported with table-valued parameters.</span></span> <span data-ttu-id="5f67d-117">Вместо этого приложение может установить атрибут столбца SQL_CA_SS_COL_HAS_DEFAULT_VALUE в значение 1.</span><span class="sxs-lookup"><span data-stu-id="5f67d-117">Instead, an application can set the column attribute SQL_CA_SS_COL_HAS_DEFAULT_VALUE to 1.</span></span> <span data-ttu-id="5f67d-118">Это значит, что во всех строках столбца будут значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5f67d-118">This means that the column will have default values for all rows.</span></span> <span data-ttu-id="5f67d-119">Если *StrLen_or_IndPtr* имеет значение SQL_DEFAULT_PARAM, то SQLExecute или SQLExecDirect возвращает SQL_ERROR, а запись диагностики будет добавлена в инструкцию с параметром SQLSTATE = HY090 и сообщением "Недопустимая строка или длина буфера".</span><span class="sxs-lookup"><span data-stu-id="5f67d-119">If *StrLen_or_IndPtr* is set to SQL_DEFAULT_PARAM, SQLExecute or SQLExecDirect will return SQL_ERROR, and a diagnostic record will be added to the statement with SQLSTATE=HY090 and the message "Invalid string or buffer length".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f67d-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="5f67d-120">See Also</span></span>  
 [<span data-ttu-id="5f67d-121">Возвращающие табличное значение параметры &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="5f67d-121">Table-Valued Parameters &#40;ODBC&#41;</span></span>](table-valued-parameters-odbc.md)  
  
  
