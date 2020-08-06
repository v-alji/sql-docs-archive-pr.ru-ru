---
title: Возвращающие табличные значения параметры (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- table-valued parameters (ODBC)
- ODBC, table-valued parameters
ms.assetid: ef06cd13-18e2-4c65-8ede-c3955d820e54
author: rothja
ms.author: jroth
ms.openlocfilehash: fedfd63f7cbafd68d39aeb62dd29c046df8ab100
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655108"
---
# <a name="table-valued-parameters-odbc"></a><span data-ttu-id="48efd-102">Возвращающие табличное значение параметры (ODBC)</span><span class="sxs-lookup"><span data-stu-id="48efd-102">Table-Valued Parameters (ODBC)</span></span>
  <span data-ttu-id="48efd-103">Поддержка в ODBC возвращающих табличное значение параметров позволяет клиентским приложениям с большей эффективностью передавать параметризованные данные на сервер за счет передачи нескольких строк в ходе одного вызова.</span><span class="sxs-lookup"><span data-stu-id="48efd-103">ODBC support for table-valued parameters lets a client application send parameterized data to the server more efficiently, by sending multiple rows to the server with one call.</span></span>  
  
 <span data-ttu-id="48efd-104">Сведения о возвращающих табличное значение параметрах на сервере см. в разделе [Использование возвращающих табличные значения параметров &#40;ядро СУБД&#41;](../tables/use-table-valued-parameters-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="48efd-104">For information about table-valued parameters on the server, see [Use Table-Valued Parameters &#40;Database Engine&#41;](../tables/use-table-valued-parameters-database-engine.md).</span></span>  
  
 <span data-ttu-id="48efd-105">В ODBC существует два способа передачи на сервер возвращающих табличное значение параметров.</span><span class="sxs-lookup"><span data-stu-id="48efd-105">In ODBC, there are two ways that you can send table-valued parameters to the server:</span></span>  
  
-   <span data-ttu-id="48efd-106">Все данные возвращающего табличное значение параметра могут находиться в памяти во время вызова SQLExecDirect или SQLExecute.</span><span class="sxs-lookup"><span data-stu-id="48efd-106">All the table-valued parameter data can be in memory at the time SQLExecDirect or SQLExecute is called.</span></span> <span data-ttu-id="48efd-107">Эти данные хранятся в массивах, если в табличном значении имеется несколько строк.</span><span class="sxs-lookup"><span data-stu-id="48efd-107">This data is stored in arrays if there are multiple rows in the table-value.</span></span>  
  
-   <span data-ttu-id="48efd-108">Приложение может указать данные при выполнении для возвращающего табличное значение параметра при вызове SQLExecDirect или SQLExecute.</span><span class="sxs-lookup"><span data-stu-id="48efd-108">An application can specify data-at-execution for a table-valued parameter when SQLExecDirect or SQLExecute is called.</span></span> <span data-ttu-id="48efd-109">В этом случае строки данных для табличного значения могут быть представлены в пакетах или по одному, чтобы снизить требования, предъявляемые к памяти.</span><span class="sxs-lookup"><span data-stu-id="48efd-109">In this case, rows of data for the table-value can be provided in batches, or one at a time to reduce memory requirements.</span></span>  
  
 <span data-ttu-id="48efd-110">В первом случае хранимые процедуры могут инкапсулировать дополнительные объемы бизнес-логики.</span><span class="sxs-lookup"><span data-stu-id="48efd-110">The first option enables stored procedures to encapsulate more business logic.</span></span> <span data-ttu-id="48efd-111">К примеру, если элементы заказа передаются в виде возвращающего табличное значение параметра, одна хранимая процедура может инкапсулировать целую транзакцию по приему заказов.</span><span class="sxs-lookup"><span data-stu-id="48efd-111">For example, a single stored procedure could encapsulate a whole order entry transaction when the order items are passed as a table-valued parameter.</span></span> <span data-ttu-id="48efd-112">Этот параметр очень эффективен, поскольку предполагает только одно обращение к серверу.</span><span class="sxs-lookup"><span data-stu-id="48efd-112">This option is very efficient, because only a single round trip to the server is required.</span></span> <span data-ttu-id="48efd-113">Существует и другая возможность: использовать одни процедуры для обработки заголовка заказа, а другие – для элементов заказа, но в этом случае потребуется дополнительный код и более сложный контракт между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="48efd-113">Alternatively, you could use different procedures to handle the order header and order items separately, which would require more code and a more complex contract between the client and server.</span></span>  
  
 <span data-ttu-id="48efd-114">Второй метод представляет собой эффективный механизм для выполнения массовых операций с очень большими объемами данных.</span><span class="sxs-lookup"><span data-stu-id="48efd-114">The second method provides an efficient mechanism for bulk operations with very large amounts of data.</span></span> <span data-ttu-id="48efd-115">Это дает приложению возможность осуществлять потоковую передачу строк данных на сервер без предварительной буферизации их в памяти.</span><span class="sxs-lookup"><span data-stu-id="48efd-115">This enables an application to stream rows of data to the server without having to buffer them all in memory first.</span></span>  
  
 <span data-ttu-id="48efd-116">При создании этой табличной переменной можно формировать ограничения и первичные ключи.</span><span class="sxs-lookup"><span data-stu-id="48efd-116">You can create constraints and primary keys when you create the table variable.</span></span> <span data-ttu-id="48efd-117">Ограничения дают хорошую гарантию того, что данные таблицы соответствуют определенным требованиям.</span><span class="sxs-lookup"><span data-stu-id="48efd-117">Constraints are a good way to ensure that the data in a table meets specific requirements.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="48efd-118">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="48efd-118">In This Section</span></span>  
 [<span data-ttu-id="48efd-119">Сценарии использования возвращающих табличное значение параметров ODBC</span><span class="sxs-lookup"><span data-stu-id="48efd-119">Uses of ODBC Table-Valued Parameters</span></span>](uses-of-odbc-table-valued-parameters.md)  
 <span data-ttu-id="48efd-120">Описывает основные пользовательские сценарии для возвращающих табличное значение параметров и ODBC.</span><span class="sxs-lookup"><span data-stu-id="48efd-120">Describes the primary user scenarios for table-valued parameters and ODBC.</span></span>  
  
 [<span data-ttu-id="48efd-121">Тип ODBC SQL для параметров, возвращающих табличное значение</span><span class="sxs-lookup"><span data-stu-id="48efd-121">ODBC SQL Type for Table-Valued Parameters</span></span>](odbc-sql-type-for-table-valued-parameters.md)  
 <span data-ttu-id="48efd-122">Описывает тип SQL_SS_TABLE.</span><span class="sxs-lookup"><span data-stu-id="48efd-122">Describes the SQL_SS_TABLE type.</span></span> <span data-ttu-id="48efd-123">Это новый тип ODBC SQL, поддерживающий возвращающие табличное значение параметры.</span><span class="sxs-lookup"><span data-stu-id="48efd-123">This is a new ODBC SQL type that supports table-valued parameters.</span></span>  
  
 [<span data-ttu-id="48efd-124">Поля дескрипторов возвращающего табличное значение параметра</span><span class="sxs-lookup"><span data-stu-id="48efd-124">Table-Valued Parameter Descriptor Fields</span></span>](table-valued-parameter-descriptor-fields.md)  
 <span data-ttu-id="48efd-125">Описывает поля дескриптора, которые поддерживают возвращающие табличное значение параметры.</span><span class="sxs-lookup"><span data-stu-id="48efd-125">Describes descriptor fields that support table-valued parameters.</span></span>  
  
 [<span data-ttu-id="48efd-126">Поля дескриптора для столбцов, содержащих параметры, возвращающие табличные значения</span><span class="sxs-lookup"><span data-stu-id="48efd-126">Descriptor Fields for Table-Valued Parameter Constituent Columns</span></span>](descriptor-fields-for-table-valued-parameter-constituent-columns.md)  
 <span data-ttu-id="48efd-127">Описывает поля дескриптора, имеющие смысл для возвращающих табличное значение параметров.</span><span class="sxs-lookup"><span data-stu-id="48efd-127">Describes descriptor fields that have meaning for table-valued parameters.</span></span>  
  
 [<span data-ttu-id="48efd-128">Поля диагностических записей для возвращающих табличные значения параметров</span><span class="sxs-lookup"><span data-stu-id="48efd-128">Table-Valued Parameter Diagnostic Record Fields</span></span>](table-valued-parameter-diagnostic-record-fields.md)  
 <span data-ttu-id="48efd-129">Описывает два диагностических поля, добавленных к диагностическим записям для поддержки параметров, возвращающих табличное значение.</span><span class="sxs-lookup"><span data-stu-id="48efd-129">Describes two diagnostic fields that have been added to diagnostic records to support table-valued parameters.</span></span>  
  
 [<span data-ttu-id="48efd-130">Атрибуты инструкции, влияющие на возвращающие табличное значение параметры</span><span class="sxs-lookup"><span data-stu-id="48efd-130">Statement Attributes that Affect Table-Valued Parameters</span></span>](statement-attributes-that-affect-table-valued-parameters.md)  
 <span data-ttu-id="48efd-131">Описывает новое поле заголовка дескриптора, активирующее столбцы с возвращающими табличное значение параметрами, к которым будет осуществляться обращение.</span><span class="sxs-lookup"><span data-stu-id="48efd-131">Describes a new descriptor header field that enables table-valued parameters columns to be addressed.</span></span>  
  
 [<span data-ttu-id="48efd-132">Привязка и передача данных возвращающих табличное значение параметров и значений столбцов</span><span class="sxs-lookup"><span data-stu-id="48efd-132">Binding and Data Transfer of Table-Valued Parameters and Column Values</span></span>](binding-and-data-transfer-of-table-valued-parameters-and-column-values.md)  
 <span data-ttu-id="48efd-133">Описывает привязку параметров и разъясняет, как передавать серверу возвращающий табличное значение параметр.</span><span class="sxs-lookup"><span data-stu-id="48efd-133">Describes parameter binding and how to pass a table-valued parameter to the server.</span></span>  
  
 [<span data-ttu-id="48efd-134">Метаданные возвращающего табличное значение параметра для подготовленных инструкций</span><span class="sxs-lookup"><span data-stu-id="48efd-134">Table-Valued Parameter Metadata for Prepared Statements</span></span>](table-valued-parameter-metadata-for-prepared-statements.md)  
 <span data-ttu-id="48efd-135">Описывает, как приложение может получить метаданные для заготовленного вызова процедуры.</span><span class="sxs-lookup"><span data-stu-id="48efd-135">Describes how an application can obtain metadata for a prepared procedure call.</span></span>  
  
 [<span data-ttu-id="48efd-136">Дополнительные метаданные возвращающего табличное значение параметра</span><span class="sxs-lookup"><span data-stu-id="48efd-136">Additional Table-Valued Parameter Metadata</span></span>](additional-table-valued-parameter-metadata.md)  
 <span data-ttu-id="48efd-137">Описывает, как использовать SQLProcedureColumns, SQLTables и SQLColumns для получения метаданных для возвращающего табличное значение параметра.</span><span class="sxs-lookup"><span data-stu-id="48efd-137">Describes how to use SQLProcedureColumns, SQLTables, and SQLColumns to retrieve metadata for a table-valued parameter.</span></span>  
  
 [<span data-ttu-id="48efd-138">Ошибки и предупреждения преобразования данных возвращающих табличное значение параметров и другие</span><span class="sxs-lookup"><span data-stu-id="48efd-138">Table-Valued Parameter Data Conversion and Other Errors and Warnings</span></span>](table-valued-parameter-data-conversion-and-other-errors-and-warnings.md)  
 <span data-ttu-id="48efd-139">Описывает, как обрабатывать ошибки в значениях столбцов с возвращающими табличное значение параметрами.</span><span class="sxs-lookup"><span data-stu-id="48efd-139">Describes how to process errors on table-valued parameter column values.</span></span>  
  
 [<span data-ttu-id="48efd-140">Совместимость версий</span><span class="sxs-lookup"><span data-stu-id="48efd-140">Cross-Version Compatibility</span></span>](cross-version-compatibility.md)  
 <span data-ttu-id="48efd-141">Описывает конфликты, которые могут возникать при использовании возвращающих табличное значение параметров клиентом или сервером версии более ранней, чем [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48efd-141">Describes conflicts that can occur when table-valued parameters are used by a client or server of a version earlier than [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
 [<span data-ttu-id="48efd-142">Сводка по API-интерфейсам возвращающих табличное значение параметров ODBC</span><span class="sxs-lookup"><span data-stu-id="48efd-142">ODBC Table-Valued Parameter API Summary</span></span>](odbc-table-valued-parameter-api-summary.md)  
 <span data-ttu-id="48efd-143">Приводит перечень функций ODBC, которые поддерживают возвращающие табличное значение параметры.</span><span class="sxs-lookup"><span data-stu-id="48efd-143">Lists the ODBC functions that support table-valued parameters.</span></span>  
  
 [<span data-ttu-id="48efd-144">Примеры программирования с использованием возвращающих табличное значение параметров ODBC</span><span class="sxs-lookup"><span data-stu-id="48efd-144">ODBC Table-Valued Parameter Programming Examples</span></span>](../../database-engine/dev-guide/odbc-table-valued-parameter-programming-examples.md)  
 <span data-ttu-id="48efd-145">Описывает, как следует выполнять типичные задачи.</span><span class="sxs-lookup"><span data-stu-id="48efd-145">Describes how to perform common tasks.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48efd-146">См. также:</span><span class="sxs-lookup"><span data-stu-id="48efd-146">See Also</span></span>  
 <span data-ttu-id="48efd-147">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="48efd-147">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span></span>  
 [<span data-ttu-id="48efd-148">Возвращающие табличное значение параметры &#40;SQL Server Native Client&#41;</span><span class="sxs-lookup"><span data-stu-id="48efd-148">Table-Valued Parameters &#40;SQL Server Native Client&#41;</span></span>](../native-client/features/table-valued-parameters-sql-server-native-client.md)  
  
  
