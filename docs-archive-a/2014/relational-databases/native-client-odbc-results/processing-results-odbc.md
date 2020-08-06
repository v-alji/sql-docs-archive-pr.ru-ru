---
title: Обработка результатов (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- result sets [ODBC], about result sets
- SQLRowCount function
- SQL Server Native Client ODBC driver, result sets
- ODBC applications, result sets
- COMPUTE clause
- result sets [ODBC]
- COMPUTE BY clause
ms.assetid: 61a8db19-6571-47dd-84e8-fcc97cb60b45
author: rothja
ms.author: jroth
ms.openlocfilehash: 72c0d15231b07a23f10a03b0fca270d1d014891c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750868"
---
# <a name="processing-results-odbc"></a><span data-ttu-id="36295-102">Обработка результатов (ODBC)</span><span class="sxs-lookup"><span data-stu-id="36295-102">Processing Results (ODBC)</span></span>
  <span data-ttu-id="36295-103">После передачи приложением инструкции SQL, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] возвращает все данные результата в виде одного или нескольких результирующих наборов.</span><span class="sxs-lookup"><span data-stu-id="36295-103">After an application submits a SQL statement, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] returns any resulting data as one or more result sets.</span></span> <span data-ttu-id="36295-104">Результирующий набор — это набор строк и столбцов, соответствующих критерию запроса.</span><span class="sxs-lookup"><span data-stu-id="36295-104">A result set is a set of rows and columns that match the criteria of the query.</span></span> <span data-ttu-id="36295-105">Инструкции SELECT, функции работы с каталогами и некоторые хранимые процедуры создают результирующий набор, доступный для приложения в табличной форме.</span><span class="sxs-lookup"><span data-stu-id="36295-105">SELECT statements, catalog functions, and some stored procedures produce a result set made available to an application in tabular form.</span></span> <span data-ttu-id="36295-106">Если выполняемая инструкция SQL является хранимой процедурой, пакетом из нескольких команд либо инструкцией SELECT, содержащей ключевые слова, то необходимо выполнять обработку нескольких результирующих наборов.</span><span class="sxs-lookup"><span data-stu-id="36295-106">If the executed SQL statement is a stored procedure, a batch containing multiple commands, or a SELECT statement containing keywords, there will be multiple result sets to process.</span></span>  
  
 <span data-ttu-id="36295-107">Функции ODBC для работы с каталогами также могут получать данные.</span><span class="sxs-lookup"><span data-stu-id="36295-107">ODBC catalog functions also can retrieve data.</span></span> <span data-ttu-id="36295-108">Например, [SQLColumns](../native-client-odbc-api/sqlcolumns.md) извлекает данные о столбцах в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="36295-108">For example, [SQLColumns](../native-client-odbc-api/sqlcolumns.md) retrieves data about columns in the data source.</span></span> <span data-ttu-id="36295-109">Эти результирующие наборы могут содержать нуль или более строк.</span><span class="sxs-lookup"><span data-stu-id="36295-109">These result sets can contain zero or more rows.</span></span>  
  
 <span data-ttu-id="36295-110">Некоторые инструкции SQL, например GRANT или REVOKE, не возвращают результирующие наборы.</span><span class="sxs-lookup"><span data-stu-id="36295-110">Other SQL statements, such as GRANT or REVOKE, do not return result sets.</span></span> <span data-ttu-id="36295-111">Для этих инструкций код возврата из **SQLExecute** или **SQLExecDirect** обычно указывает на то, что инструкция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="36295-111">For these statements, the return code from **SQLExecute** or **SQLExecDirect** is usually the only indication the statement was successful.</span></span>  
  
 <span data-ttu-id="36295-112">Каждая из инструкций INSERT, UPDATE и DELETE возвращает результирующий набор, содержащий только количество строк, затронутых изменением.</span><span class="sxs-lookup"><span data-stu-id="36295-112">Each INSERT, UPDATE, and DELETE statement returns a result set containing only the number of rows affected by the modification.</span></span> <span data-ttu-id="36295-113">Это число становится доступным, когда приложение вызывает [SQLRowCount](../native-client-odbc-api/sqlrowcount.md).</span><span class="sxs-lookup"><span data-stu-id="36295-113">This count is made available when application calls [SQLRowCount](../native-client-odbc-api/sqlrowcount.md).</span></span> <span data-ttu-id="36295-114">ODBC 3. приложения *x* должны либо вызывать **SQLRowCount** для получения результирующего набора, либо [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) , чтобы отменить его.</span><span class="sxs-lookup"><span data-stu-id="36295-114">ODBC 3.*x* applications must either call **SQLRowCount** to retrieve the result set or [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) to cancel it.</span></span> <span data-ttu-id="36295-115">Когда приложение выполняет пакет или хранимую процедуру, содержащую несколько инструкций INSERT, UPDATE или DELETE, результирующий набор каждой инструкции изменения должен обрабатываться с помощью **SQLRowCount** или отменяться с помощью **SQLMoreResults**.</span><span class="sxs-lookup"><span data-stu-id="36295-115">When an application executes a batch or stored procedure containing multiple INSERT, UPDATE, or DELETE statements, the result set from each modification statement must be processed using **SQLRowCount** or cancelled using **SQLMoreResults**.</span></span> <span data-ttu-id="36295-116">Эти счетчики можно сбросить, включив в пакет или хранимую процедуру инструкцию SET NOCOUNT ON.</span><span class="sxs-lookup"><span data-stu-id="36295-116">These counts can be cancelled by including a SET NOCOUNT ON statement in the batch or stored procedure.</span></span>  
  
 <span data-ttu-id="36295-117">Transact-SQL включает инструкцию SET NOCOUNT.</span><span class="sxs-lookup"><span data-stu-id="36295-117">Transact-SQL includes the SET NOCOUNT statement.</span></span> <span data-ttu-id="36295-118">Если параметр NOCOUNT установлен в значение ON, SQL Server не возвращает количество строк, затронутых инструкцией, а **SQLRowCount** возвращает 0.</span><span class="sxs-lookup"><span data-stu-id="36295-118">When the NOCOUNT option is set on, SQL Server does not return the counts of the rows affected by a statement and **SQLRowCount** returns 0.</span></span> <span data-ttu-id="36295-119">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Версия драйвера ODBC для собственного клиента вводит параметр [SQLGetStmtAttr](../native-client-odbc-api/sqlgetstmtattr.md) , зависящий от драйвера, SQL_SOPT_SS_NOCOUNT_STATUS, чтобы сообщить о том, включен ли параметр NOCOUNT.</span><span class="sxs-lookup"><span data-stu-id="36295-119">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver version introduces a driver-specific [SQLGetStmtAttr](../native-client-odbc-api/sqlgetstmtattr.md) option, SQL_SOPT_SS_NOCOUNT_STATUS, to report on whether the NOCOUNT option is on or off.</span></span> <span data-ttu-id="36295-120">Когда **SQLRowCount** в любое время возвращает 0, приложение должно протестировать SQL_SOPT_SS_NOCOUNT_STATUS.</span><span class="sxs-lookup"><span data-stu-id="36295-120">Anytime **SQLRowCount** returns 0, the application should test SQL_SOPT_SS_NOCOUNT_STATUS.</span></span> <span data-ttu-id="36295-121">Если возвращается SQL_NC_ON, значение 0 из **SQLRowCount** указывает, что SQL Server не вернул число строк.</span><span class="sxs-lookup"><span data-stu-id="36295-121">If SQL_NC_ON is returned, the value of 0 from **SQLRowCount** only indicates that SQL Server has not returned a row count.</span></span> <span data-ttu-id="36295-122">Если возвращается SQL_NC_OFF, это означает, что параметр NOCOUNT отключен и значение 0 из **SQLRowCount** указывает на то, что инструкция не повлияла ни на какие строки.</span><span class="sxs-lookup"><span data-stu-id="36295-122">If SQL_NC_OFF is returned, it means that NOCOUNT is off and the value of 0 from **SQLRowCount** indicates that the statement did not affect any rows.</span></span> <span data-ttu-id="36295-123">Приложения не должны отображать значение **SQLRowCount** , если SQL_SOPT_SS_NOCOUNT_STATUS SQL_NC_OFF.</span><span class="sxs-lookup"><span data-stu-id="36295-123">Applications should not display the value of **SQLRowCount** when SQL_SOPT_SS_NOCOUNT_STATUS is SQL_NC_OFF.</span></span> <span data-ttu-id="36295-124">Большие пакеты или хранимые процедуры могут содержать несколько инструкций SET NOCOUNT, следовательно, программисты не должны предполагать, что параметр SQL_SOPT_SS_NOCOUNT_STATUS останется неизменным.</span><span class="sxs-lookup"><span data-stu-id="36295-124">Large batches or stored procedures may contain multiple SET NOCOUNT statements so programmers cannot assume SQL_SOPT_SS_NOCOUNT_STATUS remains constant.</span></span> <span data-ttu-id="36295-125">Этот параметр следует проверять каждый раз, когда **SQLRowCount** возвращает 0.</span><span class="sxs-lookup"><span data-stu-id="36295-125">The option should be tested each time **SQLRowCount** returns 0.</span></span>  
  
 <span data-ttu-id="36295-126">Несколько других инструкций Transact-SQL возвращают данные в сообщениях, а не в результирующих наборах.</span><span class="sxs-lookup"><span data-stu-id="36295-126">Several other Transact-SQL statements return their data in messages rather than result sets.</span></span> <span data-ttu-id="36295-127">Когда [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] драйвер ODBC для собственного клиента получает эти сообщения, он возвращает SQL_SUCCESS_WITH_INFO, чтобы сообщить приложению о доступности информационных сообщений.</span><span class="sxs-lookup"><span data-stu-id="36295-127">When the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver receives these messages, it returns SQL_SUCCESS_WITH_INFO to let the application know that informational messages are available.</span></span> <span data-ttu-id="36295-128">Затем приложение может вызвать **SQLGetDiagRec** для получения этих сообщений.</span><span class="sxs-lookup"><span data-stu-id="36295-128">The application can then call **SQLGetDiagRec** to retrieve these messages.</span></span> <span data-ttu-id="36295-129">Инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)], работающие таким способом, перечислены ниже.</span><span class="sxs-lookup"><span data-stu-id="36295-129">The [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that work this way are:</span></span>  
  
-   <span data-ttu-id="36295-130">DBCC</span><span class="sxs-lookup"><span data-stu-id="36295-130">DBCC</span></span>  
  
-   <span data-ttu-id="36295-131">SET SHOWPLAN (доступна в ранних версиях SQL Server)</span><span class="sxs-lookup"><span data-stu-id="36295-131">SET SHOWPLAN (available with earlier versions of SQL Server)</span></span>  
  
-   <span data-ttu-id="36295-132">SET STATISTICS</span><span class="sxs-lookup"><span data-stu-id="36295-132">SET STATISTICS</span></span>  
  
-   <span data-ttu-id="36295-133">PRINT</span><span class="sxs-lookup"><span data-stu-id="36295-133">PRINT</span></span>  
  
-   <span data-ttu-id="36295-134">RAISERROR</span><span class="sxs-lookup"><span data-stu-id="36295-134">RAISERROR</span></span>  
  
 <span data-ttu-id="36295-135">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Драйвер ODBC для собственного клиента возвращает SQL_ERROR для RAISERROR с уровнем серьезности 11 или выше.</span><span class="sxs-lookup"><span data-stu-id="36295-135">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver returns SQL_ERROR on a RAISERROR with a severity of 11 or higher.</span></span> <span data-ttu-id="36295-136">При уровне серьезности RAISERROR от 19 и выше соединение отключается.</span><span class="sxs-lookup"><span data-stu-id="36295-136">If the severity of the RAISERROR is 19 or higher, the connection is also dropped.</span></span>  
  
 <span data-ttu-id="36295-137">Чтобы обработать результирующие наборы инструкции SQL, приложение выполняет следующие действия.</span><span class="sxs-lookup"><span data-stu-id="36295-137">To process the result sets from an SQL statement, the application:</span></span>  
  
-   <span data-ttu-id="36295-138">Определяет характеристики результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="36295-138">Determines the characteristics of the result set.</span></span>  
  
-   <span data-ttu-id="36295-139">Привязывает столбцы к переменным программы.</span><span class="sxs-lookup"><span data-stu-id="36295-139">Binds the columns to program variables.</span></span>  
  
-   <span data-ttu-id="36295-140">Получает одно значение, целую строку значений, или несколько строк значений.</span><span class="sxs-lookup"><span data-stu-id="36295-140">Retrieves a single value, an entire row of values, or multiple rows of values.</span></span>  
  
-   <span data-ttu-id="36295-141">Проверяет наличие результирующих наборов, и в случае их существования, начинает цикл снова для определения характеристик нового результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="36295-141">Tests to see if there are more result sets, and if so, loops back to determining the characteristics of the new result set.</span></span>  
  
 <span data-ttu-id="36295-142">Процесс получения строк из источника данных и передачи их в приложение называется выборкой.</span><span class="sxs-lookup"><span data-stu-id="36295-142">The process of retrieving rows from the data source and returning them to the application is called fetching.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="36295-143">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="36295-143">In This Section</span></span>  
  
-   [<span data-ttu-id="36295-144">Определение характеристик результирующего набора &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="36295-144">Determining the Characteristics of a Result Set &#40;ODBC&#41;</span></span>](determining-the-characteristics-of-a-result-set-odbc.md)  
  
-   [<span data-ttu-id="36295-145">Назначение хранилища</span><span class="sxs-lookup"><span data-stu-id="36295-145">Assigning Storage</span></span>](assigning-storage.md)  
  
-   [<span data-ttu-id="36295-146">Выборка итоговых данных</span><span class="sxs-lookup"><span data-stu-id="36295-146">Fetching Result Data</span></span>](fetching-result-data.md)  
  
-   [<span data-ttu-id="36295-147">Сопоставление типов данных &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="36295-147">Mapping Data Types &#40;ODBC&#41;</span></span>](mapping-data-types-odbc.md)  
  
-   [<span data-ttu-id="36295-148">Использование типов данных</span><span class="sxs-lookup"><span data-stu-id="36295-148">Data Type Usage</span></span>](data-type-usage.md)  
  
-   [<span data-ttu-id="36295-149">Автоматическое преобразование символьных данных</span><span class="sxs-lookup"><span data-stu-id="36295-149">Autotranslation of Character Data</span></span>](autotranslation-of-character-data.md)  
  
## <a name="see-also"></a><span data-ttu-id="36295-150">См. также:</span><span class="sxs-lookup"><span data-stu-id="36295-150">See Also</span></span>  
 <span data-ttu-id="36295-151">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="36295-151">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span></span>  
 [<span data-ttu-id="36295-152">Разделы руководства по обработке результатов &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="36295-152">Processing Results How-to Topics &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/processing-results-how-to-topics-odbc.md)  
  
  
