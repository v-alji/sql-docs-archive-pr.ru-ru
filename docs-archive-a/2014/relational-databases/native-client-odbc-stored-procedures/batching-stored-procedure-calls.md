---
title: Пакетирование вызовов хранимых процедур | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- stored procedures [ODBC], batching
- ODBC, stored procedures
- SQL Server Native Client ODBC driver, stored procedures
- batches [ODBC]
- ODBC CALL escape sequence
ms.assetid: b7f53e11-15f0-4602-8134-b166160888f0
author: rothja
ms.author: jroth
ms.openlocfilehash: a0df58ce59853ee15b863cbc7bce34041c37fee4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750863"
---
# <a name="batching-stored-procedure-calls"></a><span data-ttu-id="03a25-102">Создание пакетной обработки вызовов хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="03a25-102">Batching Stored Procedure Calls</span></span>
  <span data-ttu-id="03a25-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Драйвер ODBC для собственного клиента автоматически выполняет пакетные вызовы хранимых процедур на сервере, если это уместно.</span><span class="sxs-lookup"><span data-stu-id="03a25-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver automatically batches stored procedure calls to the server when appropriate.</span></span> <span data-ttu-id="03a25-104">Драйвер производит это действие только при использовании управляющей последовательности ODBC CALL и не производит его для инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="03a25-104">The driver only does this when the ODBC CALL escape sequence is used; it does not do this for the [!INCLUDE[tsql](../../includes/tsql-md.md)] EXECUTE statement.</span></span> <span data-ttu-id="03a25-105">Создание пакетов вызовов хранимых процедур может уменьшить количество обменов данных с сервером и значительно повысить производительность.</span><span class="sxs-lookup"><span data-stu-id="03a25-105">Batching stored procedure calls can reduce the number of round trips to the server and significantly increase performance.</span></span>  
  
 <span data-ttu-id="03a25-106">Драйвер создает пакеты вызовов процедур на сервере при выполнении пакета, который содержит несколько управляющих последовательностей ODBC CALL.</span><span class="sxs-lookup"><span data-stu-id="03a25-106">The driver batches procedure calls to the server when you execute a batch that contains multiple ODBC CALL escape sequences.</span></span> <span data-ttu-id="03a25-107">Он также создает пакеты вызовов процедур, когда массивы связанных параметров используются с управляющей последовательностью ODBC CALL.</span><span class="sxs-lookup"><span data-stu-id="03a25-107">It also batches procedure calls when bound parameter arrays are used with an ODBC CALL escape sequence.</span></span> <span data-ttu-id="03a25-108">Например, если для привязки массива с пятью элементами к параметрам инструкции SQL CALL, то при вызове **SQLExecute** или **SQLExecDirect** драйвер отправляет один пакет с пятью вызовами процедур на сервер, при использовании привязки параметра на уровне строк или на уровне столбца.</span><span class="sxs-lookup"><span data-stu-id="03a25-108">For example, if you use either row-wise or column-wise parameter binding to bind an array with five elements to the parameters of an ODBC CALL SQL statement, when **SQLExecute** or **SQLExecDirect** is called, the driver sends a single batch with five procedure calls to the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03a25-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="03a25-109">See Also</span></span>  
 [<span data-ttu-id="03a25-110">Выполнение хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="03a25-110">Running Stored Procedures</span></span>](running-stored-procedures.md)  
  
  
