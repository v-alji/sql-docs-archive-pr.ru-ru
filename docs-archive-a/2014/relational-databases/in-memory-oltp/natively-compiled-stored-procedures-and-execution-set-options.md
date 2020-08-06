---
title: Скомпилированные в собственном коде хранимые процедуры и параметры набора выполнения | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: c1869cf7-9030-4d18-85d6-0e419a4e9af7
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 264a2b3ab1e6f3f0bda97bfe89a4438aa641577d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750968"
---
# <a name="natively-compiled-stored-procedures-and-execution-set-options"></a><span data-ttu-id="1b51e-102">Скомпилированные в собственном коде хранимые процедуры и параметры SET выполнения</span><span class="sxs-lookup"><span data-stu-id="1b51e-102">Natively Compiled Stored Procedures and Execution Set Options</span></span>
  <span data-ttu-id="1b51e-103">Параметры сеанса фиксированы в блоках ATOMIC.</span><span class="sxs-lookup"><span data-stu-id="1b51e-103">Session options are fixed in atomic blocks.</span></span> <span data-ttu-id="1b51e-104">Выполнение хранимой процедуры не зависит от значения параметров SET сеанса.</span><span class="sxs-lookup"><span data-stu-id="1b51e-104">A stored procedure's execution is not affected by a session's SET options.</span></span> <span data-ttu-id="1b51e-105">Однако некоторые параметры SET, например SET NOEXEC и SET SHOWPLAN_XML, препятствуют выполнению хранимых процедур (в том числе хранимых процедур, скомпилированных в собственном коде).</span><span class="sxs-lookup"><span data-stu-id="1b51e-105">However, certain SET options, such as SET NOEXEC and SET SHOWPLAN_XML, cause stored procedures (including natively compiled stored procedures) to not execute.</span></span>  
  
 <span data-ttu-id="1b51e-106">Если хранимая процедура, скомпилированная в собственном коде, выполняется с любым включенным параметром STATISTICS, то статистика собирается для процедуры в целом, а не одной инструкции.</span><span class="sxs-lookup"><span data-stu-id="1b51e-106">When a natively compiled stored procedure is executed with any STATISTICS option turned on, statistics are gathered for the procedure as a whole and not per statement.</span></span> <span data-ttu-id="1b51e-107">Дополнительные сведения см. в статьях [SET STATISTICS IO (Transact-SQL)](/sql/t-sql/statements/set-statistics-io-transact-sql), [SET STATISTICS PROFILE (Transact-SQL)](/sql/t-sql/statements/set-statistics-profile-transact-sql), [SET STATISTICS TIME (Transact-SQL)](/sql/t-sql/statements/set-statistics-time-transact-sql) и [SET STATISTICS XML (Transact-SQL)](/sql/t-sql/statements/set-statistics-xml-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1b51e-107">For more information, see [SET STATISTICS IO &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-io-transact-sql), [SET STATISTICS PROFILE &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-profile-transact-sql), [SET STATISTICS TIME &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-time-transact-sql), and [SET STATISTICS XML &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statistics-xml-transact-sql).</span></span> <span data-ttu-id="1b51e-108">Чтобы получить статистику выполнения на уровне инструкций в изначально скомпилированных хранимых процедурах, используйте сеанс расширенных событий в событии sp_statement_completed, которое запускается, когда завершаются все отдельные запросы в выполнении хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="1b51e-108">To obtain execution statistics on a per-statement level in natively compiled stored procedures, use an Extended Event session on the sp_statement_completed event, which starts when each individual query in a stored procedures execution completes.</span></span> <span data-ttu-id="1b51e-109">Дополнительные сведения о создании сеансов расширенных событий см. в разделе [CREATE EVENT SESSION (Transact-SQL)](/sql/t-sql/statements/create-event-session-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1b51e-109">For more information on creating Extended Event sessions, see [CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql).</span></span>  
  
 <span data-ttu-id="1b51e-110">`SHOWPLAN_XML` поддерживается для хранимых процедурах, скомпилированных в собственном коде.</span><span class="sxs-lookup"><span data-stu-id="1b51e-110">`SHOWPLAN_XML` is supported for natively compiled stored procedures.</span></span> <span data-ttu-id="1b51e-111">`SHOWPLAN_ALL` и `SHOWPLAN_TEXT` не поддерживаются для хранимых процедур, скомпилированных в собственном коде.</span><span class="sxs-lookup"><span data-stu-id="1b51e-111">`SHOWPLAN_ALL` and `SHOWPLAN_TEXT` are not supported with natively compiled stored procedures.</span></span>  
  
 <span data-ttu-id="1b51e-112">`SET FMTONLY` не поддерживается для хранимых процедур, скомпилированных в собственном коде.</span><span class="sxs-lookup"><span data-stu-id="1b51e-112">`SET FMTONLY` in not supported with natively compiled stored procedures.</span></span> <span data-ttu-id="1b51e-113">Используйте вместо этой инструкции [sp_describe_first_result_set (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-describe-first-result-set-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1b51e-113">Use [sp_describe_first_result_set &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-describe-first-result-set-transact-sql) instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b51e-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="1b51e-114">See Also</span></span>  
 [<span data-ttu-id="1b51e-115">Скомпилированные в собственном коде хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="1b51e-115">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
