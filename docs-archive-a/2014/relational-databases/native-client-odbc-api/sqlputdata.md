---
title: SQLPutData | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLPutData function
ms.assetid: d39aaa5b-7fbc-4315-a7f2-5a7787e04f25
author: rothja
ms.author: jroth
ms.openlocfilehash: 31da9c21f9e4323a492a25629a979c66a4f7d365
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668277"
---
# <a name="sqlputdata"></a><span data-ttu-id="c3d6c-102">SQLPutData</span><span class="sxs-lookup"><span data-stu-id="c3d6c-102">SQLPutData</span></span>
  <span data-ttu-id="c3d6c-103">Следующие ограничения применяются при использовании SQLPutData для отправки более чем 65 535 байт данных (для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] версии 4.21 a) или 400 КБ данных (для SQL Server версии 6,0 и более поздних) для столбца SQL_LONGVARCHAR ( `text` ), SQL_WLONGVARCHAR ( `ntext` ) или SQL_LONGVARBINARY ( `image` ):</span><span class="sxs-lookup"><span data-stu-id="c3d6c-103">The following restrictions apply when using SQLPutData to send more than 65,535 bytes of data (for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 4.21a) or 400 KB of data (for SQL Server version 6.0 and later) for a SQL_LONGVARCHAR (`text`), SQL_WLONGVARCHAR (`ntext`) or SQL_LONGVARBINARY (`image`) column:</span></span>  
  
-   <span data-ttu-id="c3d6c-104">Параметр, на который указывает ссылка, может быть *insert_value* в инструкции INSERT.</span><span class="sxs-lookup"><span data-stu-id="c3d6c-104">The referenced parameter can be the *insert_value* in an INSERT statement.</span></span>  
  
-   <span data-ttu-id="c3d6c-105">Параметр, на который указывает ссылка, может быть *выражением* в предложении SET инструкции UPDATE.</span><span class="sxs-lookup"><span data-stu-id="c3d6c-105">The referenced parameter can be an *expression* in the SET clause of an UPDATE statement.</span></span>  
  
 <span data-ttu-id="c3d6c-106">Отмена последовательности вызовов SQLPutData, предоставляющих данные в блоках на сервере, на котором выполняется, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] приводит к частичному обновлению значения столбца при использовании версии 6,5 или более ранней.</span><span class="sxs-lookup"><span data-stu-id="c3d6c-106">Canceling a sequence of SQLPutData calls that provide data in blocks to a server running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] causes a partial update of the column's value when using version 6.5 or earlier.</span></span> <span data-ttu-id="c3d6c-107">`text`Столбец, `ntext` или `image` , на который было дана ссылка при вызове SQLCancel, имеет значение промежуточного значения заполнителя.</span><span class="sxs-lookup"><span data-stu-id="c3d6c-107">The `text`, `ntext`, or `image` column that was referenced when SQLCancel was called is set to an intermediate placeholder value.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c3d6c-108">Драйвер ODBC собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не поддерживает соединение с версией [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 6.5 и более ранней.</span><span class="sxs-lookup"><span data-stu-id="c3d6c-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver does not support connecting to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 6.5 and earlier.</span></span>  
  
## <a name="diagnostics"></a><span data-ttu-id="c3d6c-109">Диагностика</span><span class="sxs-lookup"><span data-stu-id="c3d6c-109">Diagnostics</span></span>  
 <span data-ttu-id="c3d6c-110">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Для SQLPutData существует один собственный клиент с конкретным кодом SQLSTATE:</span><span class="sxs-lookup"><span data-stu-id="c3d6c-110">There is one [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client specific SQLSTATE for SQLPutData:</span></span>  
  
|<span data-ttu-id="c3d6c-111">SQLSTATE</span><span class="sxs-lookup"><span data-stu-id="c3d6c-111">SQLSTATE</span></span>|<span data-ttu-id="c3d6c-112">Ошибка</span><span class="sxs-lookup"><span data-stu-id="c3d6c-112">Error</span></span>|<span data-ttu-id="c3d6c-113">Описание</span><span class="sxs-lookup"><span data-stu-id="c3d6c-113">Description</span></span>|  
|--------------|-----------|-----------------|  
|<span data-ttu-id="c3d6c-114">22026</span><span class="sxs-lookup"><span data-stu-id="c3d6c-114">22026</span></span>|<span data-ttu-id="c3d6c-115">Строковые данные, несовпадение длины</span><span class="sxs-lookup"><span data-stu-id="c3d6c-115">String data, length mismatch</span></span>|<span data-ttu-id="c3d6c-116">Если длина данных в байтах для отправки была задана приложением, например с SQL_LEN_DATA_AT_EXEC (*n*), где *n* больше 0, общее число байтов, заданное приложением через SQLPutData, должно соответствовать указанной длине.</span><span class="sxs-lookup"><span data-stu-id="c3d6c-116">If the length of data in bytes to be sent has been specified by an application, for example, with SQL_LEN_DATA_AT_EXEC(*n*) where *n* is greater than 0, the total number of bytes given by the application via SQLPutData must match the specified length.</span></span>|  
  
## <a name="sqlputdata-and-table-valued-parameters"></a><span data-ttu-id="c3d6c-117">Функция SQLPutData и параметры, возвращающие табличные значения</span><span class="sxs-lookup"><span data-stu-id="c3d6c-117">SQLPutData and Table-Valued Parameters</span></span>  
 <span data-ttu-id="c3d6c-118">SQLPutData используется приложением при использовании привязки строк переменных с возвращающими табличные значения параметрами.</span><span class="sxs-lookup"><span data-stu-id="c3d6c-118">SQLPutData is used by an application when using variable row binding with table-valued parameters.</span></span> <span data-ttu-id="c3d6c-119">Параметр *StrLen_Or_Ind* указывает, что драйвер готов к приему данных для следующей строки или строк данных возвращающего табличное значение параметра или что больше нет доступных строк:</span><span class="sxs-lookup"><span data-stu-id="c3d6c-119">The *StrLen_Or_Ind* parameter indicates that it is ready for the driver to collect data for the next row or rows of table-valued parameter data, or that no more rows are available:</span></span>  
  
-   <span data-ttu-id="c3d6c-120">Значение, большее 0, указывает на доступность следующего набора значений строки.</span><span class="sxs-lookup"><span data-stu-id="c3d6c-120">A value greater than 0 indicates that the next set of row values is available.</span></span>  
  
-   <span data-ttu-id="c3d6c-121">Значение 0 указывает, что строк для отправки больше нет.</span><span class="sxs-lookup"><span data-stu-id="c3d6c-121">A value of 0 indicates that there are no more rows to be sent.</span></span>  
  
-   <span data-ttu-id="c3d6c-122">Значение меньше 0 является ошибочным и приводит к внесению в журнал диагностической записи со значением SQLState, равным HY090, и сообщением «Недопустимая длина строки или буфера».</span><span class="sxs-lookup"><span data-stu-id="c3d6c-122">Any value less than 0 is an error and results in a diagnostic record being logged with SQLState HY090 and the messaage "Invalid string or buffer length".</span></span>  
  
 <span data-ttu-id="c3d6c-123">Параметр *датаптр* игнорируется, но ему должно быть присвоено значение, отличное от NULL.</span><span class="sxs-lookup"><span data-stu-id="c3d6c-123">The *DataPtr* parameter is ignored, but must be set to a non-NULL value.</span></span> <span data-ttu-id="c3d6c-124">Дополнительные сведения см. в разделе, посвященном TVP строке привязки в [Binding и передача данных значений параметров и столбцов, возвращающих](../native-client-odbc-table-valued-parameters/binding-and-data-transfer-of-table-valued-parameters-and-column-values.md)табличное значение.</span><span class="sxs-lookup"><span data-stu-id="c3d6c-124">For more information, see the section on Variable TVP row binding in [Binding and Data Transfer of Table-Valued Parameters and Column Values](../native-client-odbc-table-valued-parameters/binding-and-data-transfer-of-table-valued-parameters-and-column-values.md).</span></span>  
  
 <span data-ttu-id="c3d6c-125">Если *StrLen_Or_Ind* имеет любое значение, отличное от SQL_DEFAULT_PARAM или число от 0 до SQL_PARAMSET_SIZE (то есть параметр *ColumnSize* SQLBindParameter), это является ошибкой.</span><span class="sxs-lookup"><span data-stu-id="c3d6c-125">If *StrLen_Or_Ind* has any value other than SQL_DEFAULT_PARAM or a number between 0 and the SQL_PARAMSET_SIZE (that is, the *ColumnSize* parameter of SQLBindParameter), it is an error.</span></span> <span data-ttu-id="c3d6c-126">Эта ошибка приводит к тому, что SQLPutData возвращает SQL_ERROR: SQLSTATE = HY090, "Недопустимая строка или длина буфера".</span><span class="sxs-lookup"><span data-stu-id="c3d6c-126">This error causes SQLPutData to return SQL_ERROR: SQLSTATE=HY090, "Invalid string or buffer length".</span></span>  
  
 <span data-ttu-id="c3d6c-127">Дополнительные сведения о возвращающих табличное значение параметрах см. в разделе [возвращающие табличное значение параметры &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="c3d6c-127">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="sqlputdata-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="c3d6c-128">Поддержка функции SQLPutData для улучшенных функций даты-времени</span><span class="sxs-lookup"><span data-stu-id="c3d6c-128">SQLPutData Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="c3d6c-129">Значения параметров типов даты-времени преобразуются, как описано в статье [преобразования из C в SQL](../native-client-odbc-date-time/datetime-data-type-conversions-from-c-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="c3d6c-129">Parameter values of date/time types are converted as described in [Conversions from C to SQL](../native-client-odbc-date-time/datetime-data-type-conversions-from-c-to-sql.md).</span></span>  
  
 <span data-ttu-id="c3d6c-130">Дополнительные сведения см. в разделе [улучшения даты и времени &#40;&#41;ODBC ](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="c3d6c-130">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="sqlputdata-support-for-large-clr-udts"></a><span data-ttu-id="c3d6c-131">Поддержка функции SQLPutData для больших определяемых пользователем типов данных CLR</span><span class="sxs-lookup"><span data-stu-id="c3d6c-131">SQLPutData Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="c3d6c-132">Функция `SQLPutData` поддерживает определяемые пользователем типы больших данных CLR.</span><span class="sxs-lookup"><span data-stu-id="c3d6c-132">`SQLPutData` supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="c3d6c-133">Дополнительные сведения см. в разделе [большие определяемые пользователем типы данных CLR &#40;&#41;ODBC ](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="c3d6c-133">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3d6c-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="c3d6c-134">See Also</span></span>  
 <span data-ttu-id="c3d6c-135">[Функция SQLPutData](https://go.microsoft.com/fwlink/?LinkId=59365) </span><span class="sxs-lookup"><span data-stu-id="c3d6c-135">[SQLPutData Function](https://go.microsoft.com/fwlink/?LinkId=59365) </span></span>  
 [<span data-ttu-id="c3d6c-136">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="c3d6c-136">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
