---
title: Получение сведений о сборках | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- assemblies [CLR integration], metadata
- status information [SQL Server], assemblies
- metadata [SQL Server], assemblies
ms.assetid: 6aa7f18e-baad-4481-9777-8c3b230b392f
author: rothja
ms.author: jroth
ms.openlocfilehash: ec559ba5ccbb53dd92f3a5e1175a10a59fbaf43c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735357"
---
# <a name="getting-information-about-assemblies"></a><span data-ttu-id="aaaa0-102">Получение сведений о сборках</span><span class="sxs-lookup"><span data-stu-id="aaaa0-102">Getting Information About Assemblies</span></span>
  <span data-ttu-id="aaaa0-103">Чтобы получить метаданные о сборках можно использовать следующие представления каталога и функции.</span><span class="sxs-lookup"><span data-stu-id="aaaa0-103">The following catalog views and functions can be queried for metadata about assemblies.</span></span>  
  
 <span data-ttu-id="aaaa0-104">**Получение сведений об отдельных сборках**</span><span class="sxs-lookup"><span data-stu-id="aaaa0-104">**To get information about individual assemblies**</span></span>  
  
-   [<span data-ttu-id="aaaa0-105">ASSEMBLYPROPERTY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="aaaa0-105">ASSEMBLYPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/assemblyproperty-transact-sql)  
  
 <span data-ttu-id="aaaa0-106">**Получение сведений обо всех сборках в базе данных**</span><span class="sxs-lookup"><span data-stu-id="aaaa0-106">**To get information about all assemblies in the database**</span></span>  
  
-   [<span data-ttu-id="aaaa0-107">sys. assemblies &#40;&#41;Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="aaaa0-107">sys.assemblies &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-assemblies-transact-sql)  
  
 <span data-ttu-id="aaaa0-108">**Получение сведений о файлах сборки, включая исполняемые файлы, исходные тексты и отладочные файлы**</span><span class="sxs-lookup"><span data-stu-id="aaaa0-108">**To get information about assembly files, including assembly binaries, source files, and debug files**</span></span>  
  
-   [<span data-ttu-id="aaaa0-109">sys. assembly_files &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="aaaa0-109">sys.assembly_files &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-assembly-files-transact-sql)  
  
 <span data-ttu-id="aaaa0-110">**Получение сведений о перекрестных ссылках между сборками**</span><span class="sxs-lookup"><span data-stu-id="aaaa0-110">**To get information about cross-assembly references**</span></span>  
  
-   [<span data-ttu-id="aaaa0-111">sys. assembly_references &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="aaaa0-111">sys.assembly_references &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-assembly-references-transact-sql)  
  
 <span data-ttu-id="aaaa0-112">**Получение сведений об определяемых пользователем типах в сборках**</span><span class="sxs-lookup"><span data-stu-id="aaaa0-112">**To get assembly information about user-defined types**</span></span>  
  
-   [<span data-ttu-id="aaaa0-113">sys. assembly_types &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="aaaa0-113">sys.assembly_types &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-assembly-types-transact-sql)  
  
-   [<span data-ttu-id="aaaa0-114">sys.types (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="aaaa0-114">sys.types &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-types-transact-sql)  
  
 <span data-ttu-id="aaaa0-115">**Получение сведений о хранимых процедурах, триггерах и функциях среды CLR**</span><span class="sxs-lookup"><span data-stu-id="aaaa0-115">**To get assembly information about common language runtime (CLR) stored procedures, triggers, and functions**</span></span>  
  
-   [<span data-ttu-id="aaaa0-116">sys.assembly_modules (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="aaaa0-116">sys.assembly_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql)  
  
 <span data-ttu-id="aaaa0-117">**Получение сведений о объектах, не являющихся объектами CLR**</span><span class="sxs-lookup"><span data-stu-id="aaaa0-117">**To get information about non-CLR objects**</span></span>  
  
-   [<span data-ttu-id="aaaa0-118">sys.sql_modules (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="aaaa0-118">sys.sql_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="aaaa0-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="aaaa0-119">See Also</span></span>  
 <span data-ttu-id="aaaa0-120">[Сборки &#40;ядро СУБД&#41;](../../relational-databases/clr-integration/assemblies-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="aaaa0-120">[Assemblies &#40;Database Engine&#41;](../../relational-databases/clr-integration/assemblies-database-engine.md) </span></span>  
 <span data-ttu-id="aaaa0-121">[Проектирование сборок](../../relational-databases/clr-integration/assemblies-designing.md) </span><span class="sxs-lookup"><span data-stu-id="aaaa0-121">[Designing Assemblies](../../relational-databases/clr-integration/assemblies-designing.md) </span></span>  
 [<span data-ttu-id="aaaa0-122">Реализация сборок</span><span class="sxs-lookup"><span data-stu-id="aaaa0-122">Implementing Assemblies</span></span>](assemblies-implementing.md)  
  
  
