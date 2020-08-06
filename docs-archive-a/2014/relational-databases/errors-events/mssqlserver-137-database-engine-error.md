---
title: MSSQLSERVER_137 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 137 (Database Engine error)
ms.assetid: 47fb4212-2165-4fec-bc41-6d548465d7be
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e0142cd53006609e9274972e4f5964132f5982c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667184"
---
# <a name="mssqlserver_137"></a><span data-ttu-id="1b82d-102">MSSQLSERVER_137</span><span class="sxs-lookup"><span data-stu-id="1b82d-102">MSSQLSERVER_137</span></span>
    
## <a name="details"></a><span data-ttu-id="1b82d-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="1b82d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1b82d-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="1b82d-104">Product Name</span></span>|<span data-ttu-id="1b82d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="1b82d-105">SQL Server</span></span>|  
|<span data-ttu-id="1b82d-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="1b82d-106">Event ID</span></span>|<span data-ttu-id="1b82d-107">137</span><span class="sxs-lookup"><span data-stu-id="1b82d-107">137</span></span>|  
|<span data-ttu-id="1b82d-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="1b82d-108">Event Source</span></span>|<span data-ttu-id="1b82d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="1b82d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="1b82d-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="1b82d-110">Component</span></span>|<span data-ttu-id="1b82d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="1b82d-111">SQLEngine</span></span>|  
|<span data-ttu-id="1b82d-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="1b82d-112">Symbolic Name</span></span>|<span data-ttu-id="1b82d-113">P_SCALAR_VAR_NOTFOUND</span><span class="sxs-lookup"><span data-stu-id="1b82d-113">P_SCALAR_VAR_NOTFOUND</span></span>|  
|<span data-ttu-id="1b82d-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="1b82d-114">Message Text</span></span>|<span data-ttu-id="1b82d-115">Должна быть объявлена скалярная переменная «%.\*ls».</span><span class="sxs-lookup"><span data-stu-id="1b82d-115">Must declare the scalar variable "%.\*ls".</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1b82d-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="1b82d-116">Explanation</span></span>  
 <span data-ttu-id="1b82d-117">Эта ошибка происходит, если переменная используется в скрипте SQL без предварительного объявления этой переменной.</span><span class="sxs-lookup"><span data-stu-id="1b82d-117">This error occurs when a variable is used in a SQL script without first declaring the variable.</span></span> <span data-ttu-id="1b82d-118">В следующем примере возвращается ошибка 137 для инструкций SET и SELECT, поскольку **@mycol** не объявлено.</span><span class="sxs-lookup"><span data-stu-id="1b82d-118">The following example returns error 137 for both the SET and SELECT statements because **@mycol** is not declared.</span></span>  
  
 <span data-ttu-id="1b82d-119">SET @mycol = 'ContactName';</span><span class="sxs-lookup"><span data-stu-id="1b82d-119">SET @mycol = 'ContactName';</span></span>  
  
 <span data-ttu-id="1b82d-120">SELECT @mycol;</span><span class="sxs-lookup"><span data-stu-id="1b82d-120">SELECT @mycol;</span></span>  
  
 <span data-ttu-id="1b82d-121">Одной из трудноуловимых причин этой ошибки является использование переменной, которая объявлена вне инструкции EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="1b82d-121">One of the more complicated causes of this error includes the use of a variable that is declared outside the EXECUTE statement.</span></span> <span data-ttu-id="1b82d-122">Например, переменная, **@mycol** указанная в инструкции SELECT, является локальной по отношению к инструкции SELECT, поэтому она находится за пределами инструкции EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="1b82d-122">For example, the variable **@mycol** specified in the SELECT statement is local to the SELECT statement; thus it is outside the EXECUTE statement.</span></span>  
  
 <span data-ttu-id="1b82d-123">USE AdventureWorks2012;</span><span class="sxs-lookup"><span data-stu-id="1b82d-123">USE AdventureWorks2012;</span></span>  
  
 <span data-ttu-id="1b82d-124">GO</span><span class="sxs-lookup"><span data-stu-id="1b82d-124">GO</span></span>  
  
 <span data-ttu-id="1b82d-125">DECLARE @mycol nvarchar(20);</span><span class="sxs-lookup"><span data-stu-id="1b82d-125">DECLARE @mycol nvarchar(20);</span></span>  
  
 <span data-ttu-id="1b82d-126">SET @mycol = 'Name';</span><span class="sxs-lookup"><span data-stu-id="1b82d-126">SET @mycol = 'Name';</span></span>  
  
 <span data-ttu-id="1b82d-127">EXECUTE ('SELECT @mycol FROM Production.Product;');</span><span class="sxs-lookup"><span data-stu-id="1b82d-127">EXECUTE ('SELECT @mycol FROM Production.Product;');</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1b82d-128">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="1b82d-128">User Action</span></span>  
 <span data-ttu-id="1b82d-129">Убедитесь в том, что все переменные, используемые в скрипте SQL, объявляются перед их применением в любом месте скрипта.</span><span class="sxs-lookup"><span data-stu-id="1b82d-129">Verify that any variables used in a SQL script are declared before being used elsewhere in the script.</span></span>  
  
 <span data-ttu-id="1b82d-130">Перепишите скрипт так, чтобы в инструкции EXECUTE не применялись ссылки на переменные, которые объявлены вне этой инструкции.</span><span class="sxs-lookup"><span data-stu-id="1b82d-130">Rewrite the script so that it does not reference variables in the EXECUTE statement that are declared outside of it.</span></span> <span data-ttu-id="1b82d-131">Пример:</span><span class="sxs-lookup"><span data-stu-id="1b82d-131">For example:</span></span>  
  
 <span data-ttu-id="1b82d-132">USE AdventureWorks2012;</span><span class="sxs-lookup"><span data-stu-id="1b82d-132">USE AdventureWorks2012;</span></span>  
  
 <span data-ttu-id="1b82d-133">GO</span><span class="sxs-lookup"><span data-stu-id="1b82d-133">GO</span></span>  
  
 <span data-ttu-id="1b82d-134">DECLARE @mycol nvarchar(20) ;</span><span class="sxs-lookup"><span data-stu-id="1b82d-134">DECLARE @mycol nvarchar(20) ;</span></span>  
  
 <span data-ttu-id="1b82d-135">SET @mycol = 'Name';</span><span class="sxs-lookup"><span data-stu-id="1b82d-135">SET @mycol = 'Name';</span></span>  
  
 <span data-ttu-id="1b82d-136">EXECUTE ('SELECT ' + @mycol + ' FROM Production.Product';) ;</span><span class="sxs-lookup"><span data-stu-id="1b82d-136">EXECUTE ('SELECT ' + @mycol + ' FROM Production.Product';) ;</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b82d-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="1b82d-137">See Also</span></span>  
 <span data-ttu-id="1b82d-138">[EXECUTE (Transact-SQL)](/sql/t-sql/language-elements/execute-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1b82d-138">[EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql) </span></span>  
 <span data-ttu-id="1b82d-139">[Инструкции SET (Transact-SQL)](/sql/t-sql/statements/set-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1b82d-139">[SET Statements &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-statements-transact-sql) </span></span>  
 [<span data-ttu-id="1b82d-140">DECLARE @local_variable &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1b82d-140">DECLARE @local_variable &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/declare-local-variable-transact-sql)  
  
  
