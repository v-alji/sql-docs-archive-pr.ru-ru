---
title: SQLGetTypeInfo | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLGetTypeInfo function
ms.assetid: 13b982c3-ae03-4155-bc0d-e225050703ce
author: rothja
ms.author: jroth
ms.openlocfilehash: 3b2bca833eeed5e51237347a5ea118d839dd36de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668297"
---
# <a name="sqlgettypeinfo"></a><span data-ttu-id="22365-102">SQLGetTypeInfo</span><span class="sxs-lookup"><span data-stu-id="22365-102">SQLGetTypeInfo</span></span>
  <span data-ttu-id="22365-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Драйвер ODBC для собственного клиента сообщает дополнительный столбец USERTYPE в результирующем наборе `SQLGetTypeInfo` .</span><span class="sxs-lookup"><span data-stu-id="22365-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver reports the additional column USERTYPE in the result set of `SQLGetTypeInfo`.</span></span> <span data-ttu-id="22365-104">USERTYPE возвращает определение типа данных DB-Library. Этот столбец полезен разработчикам, которые переносят существующие приложения DB-Library в ODBC.</span><span class="sxs-lookup"><span data-stu-id="22365-104">USERTYPE reports the DB-Library data type definition and is useful to developers porting existing DB-Library applications to ODBC.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="22365-105">рассматривает идентификатор как атрибут, а в ODBC он считается типом данных.</span><span class="sxs-lookup"><span data-stu-id="22365-105">treats identity as an attribute, whereas ODBC treats it as a data type.</span></span> <span data-ttu-id="22365-106">Чтобы устранить это несоответствие, `SQLGetTypeInfo` возвращает типы данных: **интидентити**, **смаллинтидентити**, **тининтидентити**, **деЦималидентити**и **нумериЦидентити**.</span><span class="sxs-lookup"><span data-stu-id="22365-106">To resolve this mismatch, `SQLGetTypeInfo` returns the data types: **intidentity**, **smallintidentity**, **tinyintidentity**, **decimalidentity**, and **numericidentity**.</span></span> <span data-ttu-id="22365-107">`SQLGetTypeInfo`Столбец результирующего набора AUTO_UNIQUE_VALUE сообщает значение true для этих типов данных.</span><span class="sxs-lookup"><span data-stu-id="22365-107">The `SQLGetTypeInfo` result set column AUTO_UNIQUE_VALUE reports the value TRUE for these data types.</span></span>  
  
 <span data-ttu-id="22365-108">Для типа **varchar**, **nvarchar** и **varbinary**драйвер ODBC для собственного клиента по-своемуу [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] отчету 8000, 4000 и 8000 соответственно для COLUMN_SIZE значения, хотя на самом деле он не ограничен.</span><span class="sxs-lookup"><span data-stu-id="22365-108">For **varchar**, **nvarchar** and **varbinary**, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver continues to report 8000, 4000 and 8000 respectively for the COLUMN_SIZE value, even though it is actually unlimited.</span></span> <span data-ttu-id="22365-109">Это делается в целях обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="22365-109">This is to ensure backward compatibility.</span></span>  
  
 <span data-ttu-id="22365-110">Для типа данных **XML** [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] драйвер ODBC для собственного клиента сообщает SQL_SS_LENGTH_UNLIMITED для COLUMN_SIZE, чтобы обозначить неограниченный размер.</span><span class="sxs-lookup"><span data-stu-id="22365-110">For the **xml** data type, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver reports SQL_SS_LENGTH_UNLIMITED for COLUMN_SIZE to denote unlimited size.</span></span>  
  
## <a name="sqlgettypeinfo-and-table-valued-parameters"></a><span data-ttu-id="22365-111">SQLGetTypeInfo и параметры, возвращающие табличные значения</span><span class="sxs-lookup"><span data-stu-id="22365-111">SQLGetTypeInfo and Table-Valued Parameters</span></span>  
 <span data-ttu-id="22365-112">Тип таблицы для возвращающих табличное значение параметров фактически является мета-типом, т. е. типом, используемым для определения других типов.</span><span class="sxs-lookup"><span data-stu-id="22365-112">The table type for table-valued parameters is effectively a meta-type-that is, a type used to define other types.</span></span> <span data-ttu-id="22365-113">Поэтому он не должен предоставляться через SQLGetTypeInfo.</span><span class="sxs-lookup"><span data-stu-id="22365-113">Therefore, it does not have to be exposed through SQLGetTypeInfo.</span></span> <span data-ttu-id="22365-114">Для получения метаданных для табличных типов, используемых с возвращающими табличное значение параметрами, приложения должны использовать SQLTables, а не SQLGetTypeInfo.</span><span class="sxs-lookup"><span data-stu-id="22365-114">Applications must use SQLTables, rather than SQLGetTypeInfo, to retrieve metadata for table types used with table-valued parameters.</span></span>  
  
 <span data-ttu-id="22365-115">Дополнительные сведения о получении метдата для возвращающих табличное значение параметров см. в разделе [атрибуты инструкций, влияющие на возвращающие](../native-client-odbc-table-valued-parameters/statement-attributes-that-affect-table-valued-parameters.md)табличное значение параметры.</span><span class="sxs-lookup"><span data-stu-id="22365-115">For more information, about retrieving metdata for table-valued parameters, see [Statement Attributes that Affect Table-Valued Parameters](../native-client-odbc-table-valued-parameters/statement-attributes-that-affect-table-valued-parameters.md).</span></span>  
  
 <span data-ttu-id="22365-116">Дополнительные сведения о возвращающих табличное значение параметрах см. в разделе [возвращающие табличное значение параметры &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="22365-116">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="sqlgettypeinfo-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="22365-117">Поддержка SQLGetTypeInfo для улучшенных функций даты-времени</span><span class="sxs-lookup"><span data-stu-id="22365-117">SQLGetTypeInfo Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="22365-118">Сведения о значениях, возвращаемых для типов даты-времени, см. в разделе [Catalog Metadata](../native-client-odbc-date-time/metadata-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="22365-118">For the values returned for date/time types, see [Catalog Metadata](../native-client-odbc-date-time/metadata-catalog.md).</span></span>  
  
 <span data-ttu-id="22365-119">Дополнительные общие сведения см. в разделе [улучшения даты и времени &#40;&#41;ODBC ](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="22365-119">For more general information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="sqlgettypeinfo-support-for-large-clr-udts"></a><span data-ttu-id="22365-120">Поддержка SQLGetTypeInfo для больших определяемых пользователем типов данных среды CLR</span><span class="sxs-lookup"><span data-stu-id="22365-120">SQLGetTypeInfo Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="22365-121">Функция `SQLGetTypeInfo` поддерживает определяемые пользователем типы больших данных CLR.</span><span class="sxs-lookup"><span data-stu-id="22365-121">`SQLGetTypeInfo` supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="22365-122">Дополнительные сведения см. в разделе [большие определяемые пользователем типы данных CLR &#40;&#41;ODBC ](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="22365-122">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22365-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="22365-123">See Also</span></span>  
 <span data-ttu-id="22365-124">[Функция SQLGetTypeInfo](https://go.microsoft.com/fwlink/?LinkId=59356) </span><span class="sxs-lookup"><span data-stu-id="22365-124">[SQLGetTypeInfo Function](https://go.microsoft.com/fwlink/?LinkId=59356) </span></span>  
 [<span data-ttu-id="22365-125">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="22365-125">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
