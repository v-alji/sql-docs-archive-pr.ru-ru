---
title: Выполнение хранимых процедур | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC, stored procedures
- stored procedures [ODBC], running
- SQL Server Native Client ODBC driver, stored procedures
- stored procedures [ODBC], executing
ms.assetid: 866b6dd3-2acd-4dfb-aeca-a0352b2d4c6a
author: rothja
ms.author: jroth
ms.openlocfilehash: 8e5de6a9a13c95b417657a1d108403fa27abe34b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750844"
---
# <a name="running-stored-procedures"></a><span data-ttu-id="2ecb8-102">Выполнение хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="2ecb8-102">Running Stored Procedures</span></span>
  <span data-ttu-id="2ecb8-103">Хранимая процедура представляет собой исполняемый объект, хранящийся в базе данных.</span><span class="sxs-lookup"><span data-stu-id="2ecb8-103">A stored procedure is an executable object stored in a database.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2ecb8-104">поддерживает:</span><span class="sxs-lookup"><span data-stu-id="2ecb8-104">supports:</span></span>  
  
-   <span data-ttu-id="2ecb8-105">Хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="2ecb8-105">Stored procedures:</span></span>  
  
     <span data-ttu-id="2ecb8-106">Одна или несколько инструкций SQL предварительно откомпилированы в одну исполняемую процедуру.</span><span class="sxs-lookup"><span data-stu-id="2ecb8-106">One or more SQL statements precompiled into a single executable procedure.</span></span>  
  
-   <span data-ttu-id="2ecb8-107">Расширенные хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="2ecb8-107">Extended stored procedures:</span></span>  
  
     <span data-ttu-id="2ecb8-108">Библиотеки динамических ссылок (DLL) C или C++, написанные с использованием API-интерфейса служб SQL Server Open Data Services для расширенных хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="2ecb8-108">C or C++ dynamic-link libraries (DLL) written to the SQL Server Open Data Services API for extended stored procedures.</span></span> <span data-ttu-id="2ecb8-109">API-интерфейс служб Open Data Services расширяет возможности хранимых процедур, позволяя им использовать код на C или C++.</span><span class="sxs-lookup"><span data-stu-id="2ecb8-109">The Open Data Services API extends the capabilities of stored procedures to include C or C++ code.</span></span>  
  
 <span data-ttu-id="2ecb8-110">При выполнении инструкций путем вызова хранимой процедуры для источника данных (в противоположность непосредственному выполнению или подготовке инструкций в клиентском приложении) можно получить следующие преимущества.</span><span class="sxs-lookup"><span data-stu-id="2ecb8-110">When executing statements, calling a stored procedure on the data source (instead of directly executing or preparing a statement in the client application) can provide:</span></span>  
  
-   <span data-ttu-id="2ecb8-111">Более высокая производительность</span><span class="sxs-lookup"><span data-stu-id="2ecb8-111">Higher performance</span></span>  
  
     <span data-ttu-id="2ecb8-112">Инструкции SQL анализируются и компилируются во время формирования процедур.</span><span class="sxs-lookup"><span data-stu-id="2ecb8-112">SQL statements are parsed and compiled when procedures are created.</span></span> <span data-ttu-id="2ecb8-113">Затем эта дополнительная нагрузка компенсируется при выполнении процедур.</span><span class="sxs-lookup"><span data-stu-id="2ecb8-113">This overhead is then saved when the procedures are executed.</span></span>  
  
-   <span data-ttu-id="2ecb8-114">Снижение сетевых издержек</span><span class="sxs-lookup"><span data-stu-id="2ecb8-114">Reduced network overhead</span></span>  
  
     <span data-ttu-id="2ecb8-115">Когда вместо отправки по сети сложных запросов выполняется процедура, это способствует сокращению объема сетевого трафика.</span><span class="sxs-lookup"><span data-stu-id="2ecb8-115">Executing a procedure instead of sending complex queries across the network can reduce network traffic.</span></span> <span data-ttu-id="2ecb8-116">Если при выполнении хранимой процедуры приложение ODBC использует синтаксическую конструкцию ODBC {CALL}, драйвер ODBC принимает дополнительные меры по оптимизации, которые снимают необходимость преобразования данных параметров.</span><span class="sxs-lookup"><span data-stu-id="2ecb8-116">If an ODBC application uses the ODBC { CALL } syntax to execute a stored procedure, the ODBC driver makes additional optimizations that eliminate the need to convert parameter data.</span></span>  
  
-   <span data-ttu-id="2ecb8-117">Повышение уровня согласованности</span><span class="sxs-lookup"><span data-stu-id="2ecb8-117">Greater consistency</span></span>  
  
     <span data-ttu-id="2ecb8-118">Если правила организации реализованы в центральном ресурсе, таком, как хранимая процедура, их можно кодировать, тестировать и отлаживать в один прием.</span><span class="sxs-lookup"><span data-stu-id="2ecb8-118">If an organization's rules are implemented in a central resource, such as a stored procedure, they can be coded, tested, and debugged once.</span></span> <span data-ttu-id="2ecb8-119">Затем индивидуальные программисты могут использовать эти протестированные хранимые процедуры, не разрабатывая собственных реализаций.</span><span class="sxs-lookup"><span data-stu-id="2ecb8-119">Individual programmers can then use the tested stored procedures instead of developing their own implementations.</span></span>  
  
-   <span data-ttu-id="2ecb8-120">Более высокая точность</span><span class="sxs-lookup"><span data-stu-id="2ecb8-120">Greater accuracy</span></span>  
  
     <span data-ttu-id="2ecb8-121">Поскольку хранимые процедуры, как правило, создаются опытными программистами, они обычно бывают более эффективными и содержат меньше ошибок, нежели код, создаваемый многократно программистами различных уровней компетентности.</span><span class="sxs-lookup"><span data-stu-id="2ecb8-121">Because stored procedures are usually developed by experienced programmers, they tend to be more efficient and have fewer errors than code developed multiple times by programmers of varying skill levels.</span></span>  
  
-   <span data-ttu-id="2ecb8-122">Дополнительные функциональные возможности</span><span class="sxs-lookup"><span data-stu-id="2ecb8-122">Added functionality</span></span>  
  
     <span data-ttu-id="2ecb8-123">В расширенных хранимых процедурах можно использовать средства на языках C и C++, недоступные в инструкциях [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ecb8-123">Extended stored procedures can use C and C++ features not available in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span>  
  
     <span data-ttu-id="2ecb8-124">Пример вызова хранимой процедуры см. в разделе [обработка кодов возврата и выходных параметров &#40;&#41;ODBC ](../native-client-odbc-how-to/running-stored-procedures-process-return-codes-and-output-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="2ecb8-124">For an example of how to call a stored procedure, see [Process Return Codes and Output Parameters &#40;ODBC&#41;](../native-client-odbc-how-to/running-stored-procedures-process-return-codes-and-output-parameters.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2ecb8-125">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="2ecb8-125">In This Section</span></span>  
  
-   [<span data-ttu-id="2ecb8-126">Вызов хранимой процедуры</span><span class="sxs-lookup"><span data-stu-id="2ecb8-126">Calling a Stored Procedure</span></span>](calling-a-stored-procedure.md)  
  
-   [<span data-ttu-id="2ecb8-127">Создание пакетной обработки вызовов хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="2ecb8-127">Batching Stored Procedure Calls</span></span>](batching-stored-procedure-calls.md)  
  
-   [<span data-ttu-id="2ecb8-128">Обработка результатов хранимой процедуры</span><span class="sxs-lookup"><span data-stu-id="2ecb8-128">Processing Stored Procedure Results</span></span>](processing-stored-procedure-results.md)  
  
## <a name="see-also"></a><span data-ttu-id="2ecb8-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="2ecb8-129">See Also</span></span>  
 <span data-ttu-id="2ecb8-130">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="2ecb8-130">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span></span>  
 [<span data-ttu-id="2ecb8-131">Разделы руководства по выполнению хранимых процедур &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="2ecb8-131">Running Stored Procedures How-to Topics &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/running-stored-procedures-how-to-topics-odbc.md)  
  
  
