---
title: Операторы внешнего объединения *= и =* не поддерживаются в режимах совместимости 90 и более поздних версий | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- outer joins
- =* join
- '*= join'
- joins [SQL Server]
ms.assetid: ca4aa11f-1048-411f-9c6c-3d0a8e319f2f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 357c729e6d53cc17f2e4c169dd66613b6cfd2f5d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735886"
---
# <a name="outer-join-operators--and--are-not-supported-in-90-or-later-compatibility-modes"></a><span data-ttu-id="da150-102">Операторы внешнего соединения \*= и =\* не поддерживаются в режиме совместимости 90 и выше</span><span class="sxs-lookup"><span data-stu-id="da150-102">Outer join operators \*= and =\* are not supported in 90 or later compatibility modes</span></span>
  <span data-ttu-id="da150-103">Советник по переходу обнаружил использование операторов внешнего объединения \* = и = \* .</span><span class="sxs-lookup"><span data-stu-id="da150-103">Upgrade Advisor detected the use of outer join operators \*= and =\*.</span></span> <span data-ttu-id="da150-104">Эти операторы не поддерживаются в режиме совместимости 90 и выше.</span><span class="sxs-lookup"><span data-stu-id="da150-104">These operators are not supported in 90 or later compatibility modes.</span></span> <span data-ttu-id="da150-105">При обновлении пользовательские базы данных сохраняют свой режим совместимости.</span><span class="sxs-lookup"><span data-stu-id="da150-105">When you upgrade, user databases maintain their compatibility mode.</span></span> <span data-ttu-id="da150-106">Инструкции, использующие эти операторы, завершатся ошибкой.</span><span class="sxs-lookup"><span data-stu-id="da150-106">Statements that use these operators will fail.</span></span>  
  
## <a name="component"></a><span data-ttu-id="da150-107">Компонент</span><span class="sxs-lookup"><span data-stu-id="da150-107">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="da150-108">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="da150-108">Corrective Action</span></span>  
 <span data-ttu-id="da150-109">Прежде чем изменить режим совместимости базы данных на 90 или более поздней версии, измените инструкции, использующие операторы внешнего объединения \* = и =, \* для использования эквивалентных ключевых слов внешнего объединения.</span><span class="sxs-lookup"><span data-stu-id="da150-109">Before you change the database compatibility mode to 90 or later, modify statements that use the outer join operators \*= and =\* to use equivalent OUTER JOIN keywords.</span></span> <span data-ttu-id="da150-110">В следующем примере показан запрос, использующий оператор `\*=`, и эквивалентный ему запрос, использующий ключевые слова `LEFT OUTER JOIN`.</span><span class="sxs-lookup"><span data-stu-id="da150-110">The following example shows a query that uses the `\*=` operator and an equivalent query that uses the `LEFT OUTER JOIN` keywords.</span></span>  
  
```  
-- This query uses an old-style outer join operator.  
USE pubs  
SELECT employee.job_id, employee.emp_id,  
   employee.fname, employee.minit, jobs.job_desc  
FROM employee, jobs   
WHERE employee.job_id *= jobs.job_id  
ORDER BY employee.job_id  
  
-- This query uses the ANSI standard keywords LEFT OUTER JOIN.  
USE pubs;  
SELECT employee.job_id, employee.emp_id,  
   employee.fname, employee.minit, jobs.job_desc  
FROM employee LEFT OUTER JOIN jobs ON   
    employee.job_id = jobs.job_id  
ORDER BY employee.job_id  
```  
  
 <span data-ttu-id="da150-111">Дополнительные сведения о внешних соединениях см. в разделе «Использование внешних соединений» электронной документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="da150-111">For more information about outer joins, see "Using Outer Joins" in SQL Server Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da150-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="da150-112">See Also</span></span>  
 <span data-ttu-id="da150-113">[Проблемы обновления ядро СУБД](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="da150-113">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="da150-114">Советник по переходу SQL Server 2014 &#91;New&#93;</span><span class="sxs-lookup"><span data-stu-id="da150-114">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
