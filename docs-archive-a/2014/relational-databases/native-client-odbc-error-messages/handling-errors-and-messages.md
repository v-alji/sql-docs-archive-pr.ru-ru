---
title: Обработка ошибок и сообщений | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC error handling, about error handling
- errors [ODBC]
- SQL Server Native Client ODBC driver, errors
- messages [ODBC], about messages
- ODBC error handling
- SQL_INVALID_HANDLE return code
- errors [ODBC], about error handling
- messages [ODBC]
ms.assetid: 74ea9630-e482-4a46-bb45-f5234f079b48
author: rothja
ms.author: jroth
ms.openlocfilehash: 4701b3224b87e7d19f1121f193d4be20f9d4c441
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730665"
---
# <a name="handling-errors-and-messages"></a><span data-ttu-id="04860-102">Обработка ошибок и сообщений</span><span class="sxs-lookup"><span data-stu-id="04860-102">Handling Errors and Messages</span></span>
  <span data-ttu-id="04860-103">Когда приложение вызывает функцию ODBC, драйвер выполняет функцию и возвращает диагностическую информацию двумя способами: код возврата указывает на общий успех или сбой функции ODBC, а диагностические записи предоставляют подробные сведения о функции.</span><span class="sxs-lookup"><span data-stu-id="04860-103">When an application calls an ODBC function, the driver executes the function and returns diagnostic information in two ways: A return code indicates the overall success or failure of an ODBC function, and diagnostic records provide detailed information about the function.</span></span> <span data-ttu-id="04860-104">Диагностическая запись состоит из записи заголовка и записи состояния.</span><span class="sxs-lookup"><span data-stu-id="04860-104">Diagnostic records include a header record and status records.</span></span> <span data-ttu-id="04860-105">При успешном выполнении функции возвращается как минимум одна диагностическая запись, запись заголовка.</span><span class="sxs-lookup"><span data-stu-id="04860-105">At least one diagnostic record, the header record, is returned even if the function succeeds.</span></span>  
  
 <span data-ttu-id="04860-106">Диагностические сведения используются во время разработки для перехвата программных ошибок, например недопустимых дескрипторов и синтаксических ошибок в жестко запрограммированных инструкциях SQL.</span><span class="sxs-lookup"><span data-stu-id="04860-106">Diagnostic information is used at development time to catch programming errors, such as invalid handles and syntax errors in hard-coded SQL statements.</span></span> <span data-ttu-id="04860-107">Она также используется во время выполнения для захвата ошибок и предупреждений времени выполнения, например усечения данных, нарушения правил и синтаксических ошибок в инструкциях SQL, введенных пользователем.</span><span class="sxs-lookup"><span data-stu-id="04860-107">It is also used at run time to catch run-time errors and warnings, such as data truncation, rule violations, and syntax errors in SQL statements entered by the user.</span></span> <span data-ttu-id="04860-108">Программная логика обычно основана на кодах возврата.</span><span class="sxs-lookup"><span data-stu-id="04860-108">Program logic is generally based on return codes.</span></span>  
  
 <span data-ttu-id="04860-109">Например, после того, как приложение вызывает **SQLFetch** для получения строк в результирующем наборе, код возврата указывает, был ли достигнут конец результирующего набора (SQL_NO_DATA), если были возвращены какие-либо информационные сообщения (SQL_SUCCESS_WITH_INFO) или произошла ошибка (SQL_ERROR).</span><span class="sxs-lookup"><span data-stu-id="04860-109">For example, after an application calls **SQLFetch** to retrieve the rows in a result set, the return code indicates whether the end of the result set was reached (SQL_NO_DATA), if any informational messages were returned (SQL_SUCCESS_WITH_INFO), or if an error occurred (SQL_ERROR).</span></span>  
  
 <span data-ttu-id="04860-110">Если [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] драйвер ODBC для собственного клиента возвращает что-либо, кроме SQL_SUCCESS, приложение может вызвать **SQLGetDiagRec** для получения любых информационных или сообщений об ошибках.</span><span class="sxs-lookup"><span data-stu-id="04860-110">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver returns anything other than SQL_SUCCESS, the application can call **SQLGetDiagRec** to retrieve any informational or error messages.</span></span> <span data-ttu-id="04860-111">Используйте **SQLGetDiagRec** для прокрутки набора сообщений вверх и вниз, если имеется более одного сообщения.</span><span class="sxs-lookup"><span data-stu-id="04860-111">Use **SQLGetDiagRec** to scroll up and down the message set if there is more than one message.</span></span>  
  
 <span data-ttu-id="04860-112">Код возврата SQL_INVALID_HANDLE всегда указывает на программную ошибку, поэтому не должен встречаться во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="04860-112">The return code SQL_INVALID_HANDLE always indicates a programming error and should never be encountered at run time.</span></span> <span data-ttu-id="04860-113">Все другие коды возврата предоставляют сведения времени выполнения, хотя SQL_ERROR может означать программную ошибку.</span><span class="sxs-lookup"><span data-stu-id="04860-113">All other return codes provide run-time information, although SQL_ERROR may indicate a programming error.</span></span>  
  
 <span data-ttu-id="04860-114">Исходный [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] собственный API DB-Library для C позволяет приложению устанавливать функции обработки ошибок и обработки сообщений обратного вызова, возвращающие ошибки или сообщения.</span><span class="sxs-lookup"><span data-stu-id="04860-114">The original [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native API, DB-Library for C, allows an application to install callback error-handling and message-handling functions that return errors or messages.</span></span> <span data-ttu-id="04860-115">Некоторые инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)], например PRINT, RAISERROR, DBCC и SET, возвращают свои результаты функции обработки сообщений DB-Library, а не результирующему набору.</span><span class="sxs-lookup"><span data-stu-id="04860-115">Some [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, such as PRINT, RAISERROR, DBCC, and SET, return their results to the DB-Library message handler function instead of to a result set.</span></span> <span data-ttu-id="04860-116">Однако API-интерфейс ODBC не имеет такой возможности обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="04860-116">However, the ODBC API has no such callback capability.</span></span> <span data-ttu-id="04860-117">Когда [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] драйвер ODBC для собственного клиента обнаруживает сообщения, возвращенные из [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , он устанавливает код возврата ODBC в SQL_SUCCESS_WITH_INFO или SQL_ERROR и возвращает сообщение в виде одной или нескольких диагностических записей.</span><span class="sxs-lookup"><span data-stu-id="04860-117">When the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver detects messages coming back from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], it sets the ODBC return code to SQL_SUCCESS_WITH_INFO or SQL_ERROR and returns the message as one or more diagnostic records.</span></span> <span data-ttu-id="04860-118">Поэтому приложение ODBC должно тщательно протестировать эти коды возврата и вызвать **SQLGetDiagRec** для получения данных сообщения.</span><span class="sxs-lookup"><span data-stu-id="04860-118">Therefore, an ODBC application must carefully test for these return codes and call **SQLGetDiagRec** to retrieve message data.</span></span>  
  
 <span data-ttu-id="04860-119">Сведения об ошибках трассировки см. в статье [Отслеживание доступа к данным](https://go.microsoft.com/fwlink/?LinkId=125805).</span><span class="sxs-lookup"><span data-stu-id="04860-119">For information about tracing errors, see [Data Access Tracing](https://go.microsoft.com/fwlink/?LinkId=125805).</span></span> <span data-ttu-id="04860-120">См. сведения об улучшениях трассировки ошибок, добавленных в [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], в руководстве по [получению доступа к диагностическим сведениям в расширенном журнале событий](../native-client/features/accessing-diagnostic-information-in-the-extended-events-log.md).</span><span class="sxs-lookup"><span data-stu-id="04860-120">For information about enhancements to error tracing added in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], see [Accessing Diagnostic Information in the Extended Events Log](../native-client/features/accessing-diagnostic-information-in-the-extended-events-log.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="04860-121">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="04860-121">In This Section</span></span>  
  
-   [<span data-ttu-id="04860-122">Обработка инструкций, выдающих сообщения</span><span class="sxs-lookup"><span data-stu-id="04860-122">Processing Statements That Generate Messages</span></span>](processing-statements-that-generate-messages.md)  
  
-   [<span data-ttu-id="04860-123">Диагностические записи и поля</span><span class="sxs-lookup"><span data-stu-id="04860-123">Diagnostic Records and Fields</span></span>](diagnostic-records-and-fields.md)  
  
-   [<span data-ttu-id="04860-124">Собственные коды ошибок</span><span class="sxs-lookup"><span data-stu-id="04860-124">Native Error Numbers</span></span>](native-error-numbers.md)  
  
-   [<span data-ttu-id="04860-125">SQLSTATE &#40;коды ошибок ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="04860-125">SQLSTATE &#40;ODBC Error Codes&#41;</span></span>](sqlstate-odbc-error-codes.md)  
  
-   [<span data-ttu-id="04860-126">сообщения об ошибках</span><span class="sxs-lookup"><span data-stu-id="04860-126">Error Messages</span></span>](error-messages.md)  
  
## <a name="see-also"></a><span data-ttu-id="04860-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="04860-127">See Also</span></span>  
 [<span data-ttu-id="04860-128">SQL Server Native Client (ODBC)</span><span class="sxs-lookup"><span data-stu-id="04860-128">SQL Server Native Client &#40;ODBC&#41;</span></span>](../native-client/odbc/sql-server-native-client-odbc.md)  
  
  
