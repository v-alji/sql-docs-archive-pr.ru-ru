---
title: Вызов хранимых процедур (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- stored procedures [ODBC], calling
ms.assetid: 31176be8-d40e-4f93-8d44-a46e804a3e2d
author: rothja
ms.author: jroth
ms.openlocfilehash: d98d623dbbb4701bb59c95df502d0063d528d0d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664155"
---
# <a name="call-stored-procedures-odbc"></a><span data-ttu-id="c3d41-102">Вызов хранимых процедур (ODBC)</span><span class="sxs-lookup"><span data-stu-id="c3d41-102">Call Stored Procedures (ODBC)</span></span>
  <span data-ttu-id="c3d41-103">Когда инструкция SQL вызывает хранимую процедуру с помощью предложения escape-вызова ODBC, драйвер Microsoft SQL Server отправляет процедуру SQL Server с помощью механизма удаленного вызова хранимой процедуры (RPC).</span><span class="sxs-lookup"><span data-stu-id="c3d41-103">When a SQL statement calls a stored procedure using the ODBC CALL escape clause, the Microsoft SQL Server driver sends the procedure to SQL Server using the remote stored procedure call (RPC) mechanism.</span></span> <span data-ttu-id="c3d41-104">Запросы RPC пропускают большую часть синтаксической проверки и обработки параметров инструкции в SQL Server; они быстрее, чем инструкция Transact-SQL EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="c3d41-104">RPC requests bypass much of the statement parsing and parameter processing in SQL Server and are faster than using the Transact-SQL EXECUTE statement.</span></span>  
  
 <span data-ttu-id="c3d41-105">Пример приложения, демонстрирующий эту функцию, см. в разделе [обработка кодов возврата и выходных параметров &#40;&#41;ODBC ](running-stored-procedures-process-return-codes-and-output-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="c3d41-105">For a sample application that demonstrates this feature, see [Process Return Codes and Output Parameters &#40;ODBC&#41;](running-stored-procedures-process-return-codes-and-output-parameters.md).</span></span>  
  
### <a name="to-run-a-procedure-as-an-rpc"></a><span data-ttu-id="c3d41-106">Выполнение процедуры с помощью RPC</span><span class="sxs-lookup"><span data-stu-id="c3d41-106">To run a procedure as an RPC</span></span>  
  
1.  <span data-ttu-id="c3d41-107">Сконструируйте инструкцию SQL, использующую escape-последовательность ODBC CALL.</span><span class="sxs-lookup"><span data-stu-id="c3d41-107">Construct a SQL statement that uses the ODBC CALL escape sequence.</span></span> <span data-ttu-id="c3d41-108">В этой инструкции для каждого входного, входного-выходного и выходного параметров, а также для возвращаемого процедурой значения (при его наличии) используются маркеры параметров.</span><span class="sxs-lookup"><span data-stu-id="c3d41-108">The statement uses parameter markers for each input, input/output, and output parameter, and for the procedure return value (if any):</span></span>  
  
    ```  
    {? = CALL procname (?,?)}  
    ```  
  
2.  <span data-ttu-id="c3d41-109">Вызовите [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) для каждого параметра входа, входа-выхода и выхода, а также для значения, возвращаемого процедурой (если оно имеется).</span><span class="sxs-lookup"><span data-stu-id="c3d41-109">Call [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) for each input, input/output, and output parameter, and for the procedure return value (if any).</span></span>  
  
3.  <span data-ttu-id="c3d41-110">Выполните инструкцию с помощью [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399).</span><span class="sxs-lookup"><span data-stu-id="c3d41-110">Execute the statement with [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c3d41-111">Если приложение отправляет процедуру при помощи синтаксиса Transact-SQL EXECUTE (в отличие от escape-последовательности ODBC CALL), драйвер SQL Server ODBC передает этот вызов процедуры SQL Server в виде инструкции SQL, а не RPC.</span><span class="sxs-lookup"><span data-stu-id="c3d41-111">If an application submits a procedure using the Transact-SQL EXECUTE syntax (as opposed to the ODBC CALL escape sequence), the SQL Server ODBC driver passes the procedure call to SQL Server as a SQL statement rather than as an RPC.</span></span> <span data-ttu-id="c3d41-112">Кроме того, при использовании инструкции Transact-SQL EXECUTE выходные параметры не возвращаются.</span><span class="sxs-lookup"><span data-stu-id="c3d41-112">Also, output parameters are not returned if the Transact-SQL EXECUTE statement is used.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3d41-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="c3d41-113">See Also</span></span>  
 <span data-ttu-id="c3d41-114">[Разделы руководства по выполнению хранимых процедур &#40;ODBC&#41;](../../database-engine/dev-guide/running-stored-procedures-how-to-topics-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="c3d41-114">[Running Stored Procedures How-to Topics &#40;ODBC&#41;](../../database-engine/dev-guide/running-stored-procedures-how-to-topics-odbc.md) </span></span>  
 <span data-ttu-id="c3d41-115">[Пакетирование вызовов хранимых процедур](../native-client-odbc-stored-procedures/batching-stored-procedure-calls.md) </span><span class="sxs-lookup"><span data-stu-id="c3d41-115">[Batching Stored Procedure Calls](../native-client-odbc-stored-procedures/batching-stored-procedure-calls.md) </span></span>  
 <span data-ttu-id="c3d41-116">[Выполнение хранимых процедур](../native-client-odbc-stored-procedures/running-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="c3d41-116">[Running Stored Procedures](../native-client-odbc-stored-procedures/running-stored-procedures.md) </span></span>  
 <span data-ttu-id="c3d41-117">[Вызов хранимой процедуры](../native-client-odbc-stored-procedures/calling-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="c3d41-117">[Calling a Stored Procedure](../native-client-odbc-stored-procedures/calling-a-stored-procedure.md) </span></span>  
 [<span data-ttu-id="c3d41-118">Процедуры</span><span class="sxs-lookup"><span data-stu-id="c3d41-118">Procedures</span></span>](../native-client-odbc-queries/executing-statements/procedures.md)  
  
  
