---
title: Выполненные инструкции (ODBC) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, statements
- statements [ODBC]
- ODBC applications, statements
- statements [ODBC], executing
ms.assetid: 063fc40d-ff81-490d-9c9b-2faefb729f37
author: rothja
ms.author: jroth
ms.openlocfilehash: 3066a09cb1f5e63105ca3ffe2441f19e4bbe0101
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655123"
---
# <a name="executing-statements-odbc"></a><span data-ttu-id="33d12-102">Выполнение инструкций (ODBC)</span><span class="sxs-lookup"><span data-stu-id="33d12-102">Executing Statements (ODBC)</span></span>
  <span data-ttu-id="33d12-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]Драйвер ODBC для собственного клиента предоставляет различные способы выполнения инструкций SQL в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] базе данных:</span><span class="sxs-lookup"><span data-stu-id="33d12-103">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver offers a variety ways to execute SQL statements in a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database:</span></span>  
  
-   <span data-ttu-id="33d12-104">прямое выполнение;</span><span class="sxs-lookup"><span data-stu-id="33d12-104">Direct execution</span></span>  
  
-   <span data-ttu-id="33d12-105">подготовленное выполнение.</span><span class="sxs-lookup"><span data-stu-id="33d12-105">Prepared execution</span></span>  
  
 <span data-ttu-id="33d12-106">Прямое выполнение включает в себя создание символьной строки [!INCLUDE[tsql](../../../includes/tsql-md.md)] , содержащей инструкцию, и ее отправка для выполнения с помощью функции **SQLExecDirect** .</span><span class="sxs-lookup"><span data-stu-id="33d12-106">Direct execution involves building a character string containing a [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement and submitting it for execution using the **SQLExecDirect** function.</span></span> <span data-ttu-id="33d12-107">Подготовленное выполнение включает в себя построение строки символов, содержащей инструкцию [!INCLUDE[tsql](../../../includes/tsql-md.md)], и последующее выполнение этой инструкции в два шага.</span><span class="sxs-lookup"><span data-stu-id="33d12-107">Prepared execution involves building a character string containing a [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement and then executing it in two stages.</span></span> <span data-ttu-id="33d12-108">На первом этапе функция [SQLPrepare](https://go.microsoft.com/fwlink/?LinkId=59360) используется для синтаксического анализа и компиляции плана выполнения инструкции в [!INCLUDE[ssDE](../../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="33d12-108">The first stage uses the [SQLPrepare Function](https://go.microsoft.com/fwlink/?LinkId=59360) function to parse and compile the execution plan for the statement in the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span> <span data-ttu-id="33d12-109">На втором этапе используется функция **SQLExecute** для выполнения ранее подготовленного плана выполнения.</span><span class="sxs-lookup"><span data-stu-id="33d12-109">The second stage uses the **SQLExecute** function to execute the previously prepared execution plan.</span></span> <span data-ttu-id="33d12-110">Это снижает расход ресурсов на синтаксический анализ и компиляцию при каждом выполнении.</span><span class="sxs-lookup"><span data-stu-id="33d12-110">This saves the parsing and compiling overhead on each execution.</span></span> <span data-ttu-id="33d12-111">Подготовленное выполнение часто используется приложениями для многократного выполнения параметризованных инструкций SQL.</span><span class="sxs-lookup"><span data-stu-id="33d12-111">Prepared execution is commonly used by applications to repeatedly execute the same, parameterized SQL statement.</span></span>  
  
 <span data-ttu-id="33d12-112">Как при непосредственном, так и при подготовленном выполнении может выполняться одиночная инструкция [!INCLUDE[tsql](../../../includes/tsql-md.md)] или пакет инструкций SQL, может также вызываться хранимая процедура.</span><span class="sxs-lookup"><span data-stu-id="33d12-112">Both direct and prepared execution can execute a single [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement or a batch of SQL statements, or they can call a stored procedure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="33d12-113">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="33d12-113">In This Section</span></span>  
  
-   [<span data-ttu-id="33d12-114">Прямое выполнение</span><span class="sxs-lookup"><span data-stu-id="33d12-114">Direct Execution</span></span>](direct-execution.md)  
  
-   [<span data-ttu-id="33d12-115">Подготовленное выполнение</span><span class="sxs-lookup"><span data-stu-id="33d12-115">Prepared Execution</span></span>](prepared-execution.md)  
  
-   [<span data-ttu-id="33d12-116">Процедуры</span><span class="sxs-lookup"><span data-stu-id="33d12-116">Procedures</span></span>](procedures.md)  
  
-   [<span data-ttu-id="33d12-117">Пакеты инструкций</span><span class="sxs-lookup"><span data-stu-id="33d12-117">Batches of Statements</span></span>](batches-of-statements.md)  
  
-   [<span data-ttu-id="33d12-118">Действие параметров ISO</span><span class="sxs-lookup"><span data-stu-id="33d12-118">Effects of ISO Options</span></span>](effects-of-iso-options.md)  
  
## <a name="see-also"></a><span data-ttu-id="33d12-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="33d12-119">See Also</span></span>  
 [<span data-ttu-id="33d12-120">Выполняя запросы &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="33d12-120">Executing Queries &#40;ODBC&#41;</span></span>](../executing-queries-odbc.md)  
  
  
