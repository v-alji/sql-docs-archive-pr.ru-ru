---
title: Поддерживаемые типы данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: a7380ef0-c9d7-49e4-b6de-fad34752b9f3
author: rothja
ms.author: jroth
ms.openlocfilehash: a7dda500486c39a66f871d5934f957028fc51e9d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749883"
---
# <a name="supported-data-types"></a><span data-ttu-id="0974b-102">Поддерживаемые типы данных</span><span class="sxs-lookup"><span data-stu-id="0974b-102">Supported Data Types</span></span>
  <span data-ttu-id="0974b-103">Следующие типы данных **поддерживаются** для оптимизированных для памяти таблиц и хранимых процедур, скомпилированных в собственном коде.</span><span class="sxs-lookup"><span data-stu-id="0974b-103">The following data types are **supported** in memory-optimized tables and natively compiled stored procedures:</span></span>  
  
 <span data-ttu-id="0974b-104">**Числовые типы данных**</span><span class="sxs-lookup"><span data-stu-id="0974b-104">**Numeric Data Types**</span></span>  
  
|<span data-ttu-id="0974b-105">Тип данных</span><span class="sxs-lookup"><span data-stu-id="0974b-105">Data type</span></span>|<span data-ttu-id="0974b-106">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="0974b-106">For more information</span></span>|  
|---------------|--------------------------|  
|<span data-ttu-id="0974b-107">int</span><span class="sxs-lookup"><span data-stu-id="0974b-107">int</span></span>|[<span data-ttu-id="0974b-108">int, bigint, smallint и tinyint (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0974b-108">int, bigint, smallint, and tinyint &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/int-bigint-smallint-and-tinyint-transact-sql)|  
|<span data-ttu-id="0974b-109">BIGINT</span><span class="sxs-lookup"><span data-stu-id="0974b-109">bigint</span></span>|[<span data-ttu-id="0974b-110">int, bigint, smallint и tinyint (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0974b-110">int, bigint, smallint, and tinyint &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/int-bigint-smallint-and-tinyint-transact-sql)|  
|<span data-ttu-id="0974b-111">smallint</span><span class="sxs-lookup"><span data-stu-id="0974b-111">smallint</span></span>|[<span data-ttu-id="0974b-112">int, bigint, smallint и tinyint (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0974b-112">int, bigint, smallint, and tinyint &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/int-bigint-smallint-and-tinyint-transact-sql)|  
|<span data-ttu-id="0974b-113">tinyint</span><span class="sxs-lookup"><span data-stu-id="0974b-113">tinyint</span></span>|[<span data-ttu-id="0974b-114">int, bigint, smallint и tinyint (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0974b-114">int, bigint, smallint, and tinyint &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/int-bigint-smallint-and-tinyint-transact-sql)|  
|<span data-ttu-id="0974b-115">Decimal</span><span class="sxs-lookup"><span data-stu-id="0974b-115">decimal</span></span>|[<span data-ttu-id="0974b-116">decimal и numeric (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0974b-116">decimal and numeric &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/decimal-and-numeric-transact-sql)|  
|<span data-ttu-id="0974b-117">NUMERIC</span><span class="sxs-lookup"><span data-stu-id="0974b-117">numeric</span></span>|[<span data-ttu-id="0974b-118">decimal и numeric (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0974b-118">decimal and numeric &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/decimal-and-numeric-transact-sql)|  
|<span data-ttu-id="0974b-119">FLOAT</span><span class="sxs-lookup"><span data-stu-id="0974b-119">float</span></span>|[<span data-ttu-id="0974b-120">Типы данных float и real (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0974b-120">float and real &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/float-and-real-transact-sql)|  
|<span data-ttu-id="0974b-121">real</span><span class="sxs-lookup"><span data-stu-id="0974b-121">real</span></span>|[<span data-ttu-id="0974b-122">Типы данных float и real (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0974b-122">float and real &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/float-and-real-transact-sql)|  
|<span data-ttu-id="0974b-123">money</span><span class="sxs-lookup"><span data-stu-id="0974b-123">money</span></span>|[<span data-ttu-id="0974b-124">Типы money и smallmoney (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0974b-124">money and smallmoney &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/money-and-smallmoney-transact-sql)|  
|<span data-ttu-id="0974b-125">smallmoney</span><span class="sxs-lookup"><span data-stu-id="0974b-125">smallmoney</span></span>|[<span data-ttu-id="0974b-126">Типы money и smallmoney (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0974b-126">money and smallmoney &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/money-and-smallmoney-transact-sql)|  
  
 <span data-ttu-id="0974b-127">**Строковые типы данных**</span><span class="sxs-lookup"><span data-stu-id="0974b-127">**String Data Types**</span></span>  
  
|<span data-ttu-id="0974b-128">Тип данных</span><span class="sxs-lookup"><span data-stu-id="0974b-128">Data type</span></span>|<span data-ttu-id="0974b-129">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="0974b-129">For more information</span></span>|  
|---------------|--------------------------|  
|<span data-ttu-id="0974b-130">char(n)</span><span class="sxs-lookup"><span data-stu-id="0974b-130">char(n)</span></span>|[<span data-ttu-id="0974b-131">char и varchar (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0974b-131">char and varchar &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/char-and-varchar-transact-sql)|  
|<span data-ttu-id="0974b-132">varchar (n) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0974b-132">varchar(n) <sup>1</sup></span></span>|[<span data-ttu-id="0974b-133">char и varchar (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0974b-133">char and varchar &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/char-and-varchar-transact-sql)|  
|<span data-ttu-id="0974b-134">nchar(n)</span><span class="sxs-lookup"><span data-stu-id="0974b-134">nchar(n)</span></span>|[<span data-ttu-id="0974b-135">nchar и nvarchar (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0974b-135">nchar and nvarchar &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/nchar-and-nvarchar-transact-sql)|  
|<span data-ttu-id="0974b-136">nvarchar (n) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0974b-136">nvarchar(n) <sup>1</sup></span></span>|[<span data-ttu-id="0974b-137">nchar и nvarchar (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0974b-137">nchar and nvarchar &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/nchar-and-nvarchar-transact-sql)|  
|<span data-ttu-id="0974b-138">sysname</span><span class="sxs-lookup"><span data-stu-id="0974b-138">sysname</span></span>|[<span data-ttu-id="0974b-139">nchar и nvarchar (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0974b-139">nchar and nvarchar &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/nchar-and-nvarchar-transact-sql)|  
  
 <span data-ttu-id="0974b-140"><sup>1</sup> ограничение составляет 8060 байт на строку, считая (n) в типах переменной длины.</span><span class="sxs-lookup"><span data-stu-id="0974b-140"><sup>1</sup> Limitation is 8060 bytes per row total, counting (n) in variable-length types.</span></span>  
  
 <span data-ttu-id="0974b-141">Дополнительные сведения о поддерживаемых параметрах сортировки см. в разделе [Collations and Code Pages](../../database-engine/collations-and-code-pages.md).</span><span class="sxs-lookup"><span data-stu-id="0974b-141">For information about supported collations, see [Collations and Code Pages](../../database-engine/collations-and-code-pages.md).</span></span>  
  
 <span data-ttu-id="0974b-142">**Типы данных даты и времени**</span><span class="sxs-lookup"><span data-stu-id="0974b-142">**Date and Time Data Types**</span></span>  
  
|<span data-ttu-id="0974b-143">Тип данных</span><span class="sxs-lookup"><span data-stu-id="0974b-143">Data type</span></span>|<span data-ttu-id="0974b-144">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="0974b-144">For more information</span></span>|  
|---------------|--------------------------|  
|<span data-ttu-id="0974b-145">Дата</span><span class="sxs-lookup"><span data-stu-id="0974b-145">date</span></span>|[<span data-ttu-id="0974b-146">date &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0974b-146">date &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/date-transact-sql)|  
|<span data-ttu-id="0974b-147">time</span><span class="sxs-lookup"><span data-stu-id="0974b-147">time</span></span>|[<span data-ttu-id="0974b-148">time (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0974b-148">time &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/time-transact-sql)|  
|<span data-ttu-id="0974b-149">DATETIME</span><span class="sxs-lookup"><span data-stu-id="0974b-149">datetime</span></span>|[<span data-ttu-id="0974b-150">datetime (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0974b-150">datetime &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/datetime-transact-sql)|  
|<span data-ttu-id="0974b-151">datetime2</span><span class="sxs-lookup"><span data-stu-id="0974b-151">datetime2</span></span>|[<span data-ttu-id="0974b-152">datetime2 &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0974b-152">datetime2 &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/datetime2-transact-sql)|  
|<span data-ttu-id="0974b-153">smalldatetime</span><span class="sxs-lookup"><span data-stu-id="0974b-153">smalldatetime</span></span>|[<span data-ttu-id="0974b-154">smalldatetime (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0974b-154">smalldatetime &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/smalldatetime-transact-sql)|  
  
 <span data-ttu-id="0974b-155">**Двоичные типы данных**</span><span class="sxs-lookup"><span data-stu-id="0974b-155">**Binary Data Types**</span></span>  
  
|<span data-ttu-id="0974b-156">Тип данных</span><span class="sxs-lookup"><span data-stu-id="0974b-156">Data type</span></span>|<span data-ttu-id="0974b-157">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="0974b-157">For more information</span></span>|  
|---------------|--------------------------|  
|<span data-ttu-id="0974b-158">bit</span><span class="sxs-lookup"><span data-stu-id="0974b-158">bit</span></span>|[<span data-ttu-id="0974b-159">bit (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0974b-159">bit &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/bit-transact-sql)|  
|<span data-ttu-id="0974b-160">binary(n)</span><span class="sxs-lookup"><span data-stu-id="0974b-160">binary(n)</span></span>|[<span data-ttu-id="0974b-161">binary и varbinary (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0974b-161">binary and varbinary &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/binary-and-varbinary-transact-sql)|  
|<span data-ttu-id="0974b-162">varbinary (n) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0974b-162">varbinary(n) <sup>1</sup></span></span>|[<span data-ttu-id="0974b-163">binary и varbinary (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0974b-163">binary and varbinary &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/binary-and-varbinary-transact-sql)|  
  
 <span data-ttu-id="0974b-164"><sup>1</sup> ограничение составляет 8060 байт на строку, считая (n) в типах переменной длины.</span><span class="sxs-lookup"><span data-stu-id="0974b-164"><sup>1</sup> Limitation is 8060 bytes per row total, counting (n) in variable-length types.</span></span>  
  
 <span data-ttu-id="0974b-165">**Другие типы данных**</span><span class="sxs-lookup"><span data-stu-id="0974b-165">**Other data types**</span></span>  
  
|<span data-ttu-id="0974b-166">Тип данных</span><span class="sxs-lookup"><span data-stu-id="0974b-166">Data type</span></span>|<span data-ttu-id="0974b-167">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="0974b-167">For more information</span></span>|  
|---------------|--------------------------|  
|<span data-ttu-id="0974b-168">UNIQUEIDENTIFIER</span><span class="sxs-lookup"><span data-stu-id="0974b-168">uniqueidentifier</span></span>|[<span data-ttu-id="0974b-169">uniqueidentifier (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0974b-169">uniqueidentifier &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/uniqueidentifier-transact-sql)|  
  
 <span data-ttu-id="0974b-170">**Неподдерживаемые типы данных**</span><span class="sxs-lookup"><span data-stu-id="0974b-170">**Unsupported Data Types**</span></span>  
  
 <span data-ttu-id="0974b-171">Следующие типы данных не поддерживаются:</span><span class="sxs-lookup"><span data-stu-id="0974b-171">The following data types are not supported:</span></span>  
  
||||  
|-|-|-|  
|<span data-ttu-id="0974b-172">DATETIMEOFFSET</span><span class="sxs-lookup"><span data-stu-id="0974b-172">DATETIMEOFFSET</span></span>|<span data-ttu-id="0974b-173">GEOGRAPHY</span><span class="sxs-lookup"><span data-stu-id="0974b-173">GEOGRAPHY</span></span>|<span data-ttu-id="0974b-174">GEOMETRY</span><span class="sxs-lookup"><span data-stu-id="0974b-174">GEOMETRY</span></span>|  
|<span data-ttu-id="0974b-175">HIERARCHYID</span><span class="sxs-lookup"><span data-stu-id="0974b-175">HIERARCHYID</span></span>|<span data-ttu-id="0974b-176">Большие объекты (LOB).</span><span class="sxs-lookup"><span data-stu-id="0974b-176">Large Objects (LOBs).</span></span> <span data-ttu-id="0974b-177">Например, varchar(max), nvarchar(max), varbinary(max), image, xml, text и ntext.</span><span class="sxs-lookup"><span data-stu-id="0974b-177">For example, varchar(max), nvarchar(max), varbinary(max), image, xml, text, and ntext.</span></span>|<span data-ttu-id="0974b-178">ROWVERSION</span><span class="sxs-lookup"><span data-stu-id="0974b-178">ROWVERSION</span></span>|  
|<span data-ttu-id="0974b-179">sql_variant</span><span class="sxs-lookup"><span data-stu-id="0974b-179">sql_variant</span></span>|<span data-ttu-id="0974b-180">Функции среды CLR</span><span class="sxs-lookup"><span data-stu-id="0974b-180">CLR functions</span></span>|<span data-ttu-id="0974b-181">Определяемые пользователем типы</span><span class="sxs-lookup"><span data-stu-id="0974b-181">User-defined types (UDTs)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0974b-182">См. также:</span><span class="sxs-lookup"><span data-stu-id="0974b-182">See Also</span></span>  
 <span data-ttu-id="0974b-183">[Поддержка Transact-SQL для In-Memory OLTP](transact-sql-support-for-in-memory-oltp.md) </span><span class="sxs-lookup"><span data-stu-id="0974b-183">[Transact-SQL Support for In-Memory OLTP](transact-sql-support-for-in-memory-oltp.md) </span></span>  
 <span data-ttu-id="0974b-184">[Реализация столбцов LOB в таблице, оптимизированной для памяти](../../database-engine/implementing-lob-columns-in-a-memory-optimized-table.md) </span><span class="sxs-lookup"><span data-stu-id="0974b-184">[Implementing LOB Columns in a Memory-Optimized Table](../../database-engine/implementing-lob-columns-in-a-memory-optimized-table.md) </span></span>  
 [<span data-ttu-id="0974b-185">Реализация SQL_VARIANT в таблице, оптимизированной для памяти</span><span class="sxs-lookup"><span data-stu-id="0974b-185">Implementing SQL_VARIANT in a Memory-Optimized Table</span></span>](implementing-sql-variant-in-a-memory-optimized-table.md)  
  
  
