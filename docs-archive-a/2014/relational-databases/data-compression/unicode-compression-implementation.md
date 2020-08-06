---
title: Реализация сжатия Юникода | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Unicode data compression
- compression [SQL Server], Unicode data
ms.assetid: 44e69e60-9b35-43fe-b9c7-8cf34eaea62a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4c928062169ed7feb03f1031362530474109976a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667210"
---
# <a name="unicode-compression-implementation"></a><span data-ttu-id="dcbb1-102">Реализация сжатия Юникода</span><span class="sxs-lookup"><span data-stu-id="dcbb1-102">Unicode Compression Implementation</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="dcbb1-103">использует алгоритм стандартной схемы сжатия Юникода (SCSU), при этом сохраняются данные в сжатых объектах строк или страниц.</span><span class="sxs-lookup"><span data-stu-id="dcbb1-103">uses an implementation of the Standard Compression Scheme for Unicode (SCSU) algorithm to compress Unicode values that are stored in row or page compressed objects.</span></span> <span data-ttu-id="dcbb1-104">Для этих объектов сжатие Юникода для столбцов типов `nchar(n)` и `nvarchar(n)` выполняется автоматически.</span><span class="sxs-lookup"><span data-stu-id="dcbb1-104">For these compressed objects, Unicode compression is automatic for `nchar(n)` and `nvarchar(n)` columns.</span></span> <span data-ttu-id="dcbb1-105">Компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] хранит данные Юникода как 2 байта, независимо от локали.</span><span class="sxs-lookup"><span data-stu-id="dcbb1-105">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] stores Unicode data as 2 bytes, regardless of locale.</span></span> <span data-ttu-id="dcbb1-106">Такая кодировка называется UCS-2.</span><span class="sxs-lookup"><span data-stu-id="dcbb1-106">This is known as UCS-2 encoding.</span></span> <span data-ttu-id="dcbb1-107">Для некоторых локалей реализация сжатия по алгоритму SCSU в SQL Server может сэкономить до 50 % места в хранилище.</span><span class="sxs-lookup"><span data-stu-id="dcbb1-107">For some locales, the implementation of SCSU compression in SQL Server can save up to 50 percent in storage space.</span></span>  
  
## <a name="supported-data-types"></a><span data-ttu-id="dcbb1-108">Поддерживаемые типы данных</span><span class="sxs-lookup"><span data-stu-id="dcbb1-108">Supported Data Types</span></span>  
 <span data-ttu-id="dcbb1-109">Сжатие Юникода поддерживает типы данных фиксированной длины `nchar(n)` и `nvarchar(n)`.</span><span class="sxs-lookup"><span data-stu-id="dcbb1-109">Unicode compression supports the fixed-length `nchar(n)` and `nvarchar(n)` data types.</span></span> <span data-ttu-id="dcbb1-110">Внестрочные значения данных и значения, хранящиеся в столбцах `nvarchar(max)`, не сжимаются.</span><span class="sxs-lookup"><span data-stu-id="dcbb1-110">Data values that are stored off row or in `nvarchar(max)` columns are not compressed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dcbb1-111">Сжатие Юникода не поддерживается для данных типа `nvarchar(max)`, даже если они хранятся в строке.</span><span class="sxs-lookup"><span data-stu-id="dcbb1-111">Unicode compression is not supported for `nvarchar(max)` data even if it is stored in row.</span></span> <span data-ttu-id="dcbb1-112">Однако сжатие страниц может быть полезно для этого типа данных.</span><span class="sxs-lookup"><span data-stu-id="dcbb1-112">However, this data type can still benefit from page compression.</span></span>  
  
## <a name="upgrading-from-earlier-versions-of-sql-server"></a><span data-ttu-id="dcbb1-113">Обновление с предыдущих версий SQL Server</span><span class="sxs-lookup"><span data-stu-id="dcbb1-113">Upgrading from Earlier Versions of SQL Server</span></span>  
 <span data-ttu-id="dcbb1-114">При обновлении базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] до [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] все изменения, связанные со сжатием Юникода, не оказывают влияния на объекты базы данных, сжатые или распакованные.</span><span class="sxs-lookup"><span data-stu-id="dcbb1-114">When a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database is upgraded to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], Unicode compression-related changes are not made to any database object, compressed or uncompressed.</span></span> <span data-ttu-id="dcbb1-115">После обновления базы данных ситуация с объектами выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="dcbb1-115">After the database is upgraded, objects are affected as follows:</span></span>  
  
-   <span data-ttu-id="dcbb1-116">Если объект не сжат, то никаких изменений не происходит и объект продолжает работать как раньше.</span><span class="sxs-lookup"><span data-stu-id="dcbb1-116">If the object is not compressed, no changes are made and the object continues to function as it did previously.</span></span>  
  
-   <span data-ttu-id="dcbb1-117">Сжатые объекты строк и страниц продолжают работу как раньше.</span><span class="sxs-lookup"><span data-stu-id="dcbb1-117">Row- or page-compressed objects continue to function as they did previously.</span></span> <span data-ttu-id="dcbb1-118">Распакованные данные остаются в распакованной форме до тех пор, пока их значение не будет обновлено.</span><span class="sxs-lookup"><span data-stu-id="dcbb1-118">Uncompressed data remains in uncompressed form until its value is updated.</span></span>  
  
-   <span data-ttu-id="dcbb1-119">Для новых строк, вставляемых в таблицу, сжатую на уровне строк или страниц, производится сжатие Юникода.</span><span class="sxs-lookup"><span data-stu-id="dcbb1-119">New rows that are inserted into a row- or page-compressed table are compressed using Unicode compression.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dcbb1-120">Для использования всех преимуществ сжатия Юникода объект необходимо перестроить с использованием сжатия страниц или строк.</span><span class="sxs-lookup"><span data-stu-id="dcbb1-120">To take full advantage of the benefits of Unicode compression, the object must be rebuilt with page or row compression.</span></span>  
  
## <a name="how-unicode-compression-affects-data-storage"></a><span data-ttu-id="dcbb1-121">Влияние сжатия Юникода на хранилище данных</span><span class="sxs-lookup"><span data-stu-id="dcbb1-121">How Unicode Compression Affects Data Storage</span></span>  
 <span data-ttu-id="dcbb1-122">При создании или перестройке индекса, а также при изменении значения в таблице, сжатой на уровне строк или страниц, соответствующий индекс или значение сохраняется в сжатом виде только в том случае, если его размер в сжатом виде будет меньше текущего.</span><span class="sxs-lookup"><span data-stu-id="dcbb1-122">When an index is created or rebuilt or when a value is changed in a table that was compressed with row or page compression, the affected index or value is stored compressed only if its compressed size is less than its current size.</span></span> <span data-ttu-id="dcbb1-123">Сжатие Юникода позволяет предотвратить разрастание размера строк в таблице или индексе.</span><span class="sxs-lookup"><span data-stu-id="dcbb1-123">This prevents rows in a table or index from increasing in size because of Unicode compression.</span></span>  
  
 <span data-ttu-id="dcbb1-124">Объем места в хранилище, сэкономленного благодаря сжатию, зависит от характеристик сжимаемых данных и локали данных.</span><span class="sxs-lookup"><span data-stu-id="dcbb1-124">The storage space that compression saves depends on the characteristics of the data that is being compressed and the locale of the data.</span></span> <span data-ttu-id="dcbb1-125">Следующая таблица содержит данные по экономии, достижимой для некоторых локалей.</span><span class="sxs-lookup"><span data-stu-id="dcbb1-125">The following table lists the space savings that can be achieved for several locales.</span></span>  
  
|<span data-ttu-id="dcbb1-126">Локаль</span><span class="sxs-lookup"><span data-stu-id="dcbb1-126">Locale</span></span>|<span data-ttu-id="dcbb1-127">Процент сжатия</span><span class="sxs-lookup"><span data-stu-id="dcbb1-127">Compression percent</span></span>|  
|------------|-------------------------|  
|<span data-ttu-id="dcbb1-128">Английский</span><span class="sxs-lookup"><span data-stu-id="dcbb1-128">English</span></span>|<span data-ttu-id="dcbb1-129">50%</span><span class="sxs-lookup"><span data-stu-id="dcbb1-129">50%</span></span>|  
|<span data-ttu-id="dcbb1-130">Немецкий</span><span class="sxs-lookup"><span data-stu-id="dcbb1-130">German</span></span>|<span data-ttu-id="dcbb1-131">50%</span><span class="sxs-lookup"><span data-stu-id="dcbb1-131">50%</span></span>|  
|<span data-ttu-id="dcbb1-132">Hindi</span><span class="sxs-lookup"><span data-stu-id="dcbb1-132">Hindi</span></span>|<span data-ttu-id="dcbb1-133">50%</span><span class="sxs-lookup"><span data-stu-id="dcbb1-133">50%</span></span>|  
|<span data-ttu-id="dcbb1-134">Турецкий</span><span class="sxs-lookup"><span data-stu-id="dcbb1-134">Turkish</span></span>|<span data-ttu-id="dcbb1-135">48 %</span><span class="sxs-lookup"><span data-stu-id="dcbb1-135">48%</span></span>|  
|<span data-ttu-id="dcbb1-136">Вьетнамский</span><span class="sxs-lookup"><span data-stu-id="dcbb1-136">Vietnamese</span></span>|<span data-ttu-id="dcbb1-137">39 %</span><span class="sxs-lookup"><span data-stu-id="dcbb1-137">39%</span></span>|  
|<span data-ttu-id="dcbb1-138">Японский</span><span class="sxs-lookup"><span data-stu-id="dcbb1-138">Japanese</span></span>|<span data-ttu-id="dcbb1-139">15 %</span><span class="sxs-lookup"><span data-stu-id="dcbb1-139">15%</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dcbb1-140">См. также:</span><span class="sxs-lookup"><span data-stu-id="dcbb1-140">See Also</span></span>  
 <span data-ttu-id="dcbb1-141">[Сжатие данных](data-compression.md) </span><span class="sxs-lookup"><span data-stu-id="dcbb1-141">[Data Compression](data-compression.md) </span></span>  
 <span data-ttu-id="dcbb1-142">[sp_estimate_data_compression_savings (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-estimate-data-compression-savings-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dcbb1-142">[sp_estimate_data_compression_savings &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-estimate-data-compression-savings-transact-sql) </span></span>  
 <span data-ttu-id="dcbb1-143">[Реализация сжатия страниц](page-compression-implementation.md) </span><span class="sxs-lookup"><span data-stu-id="dcbb1-143">[Page Compression Implementation](page-compression-implementation.md) </span></span>  
 [<span data-ttu-id="dcbb1-144">sys.dm_db_persisted_sku_features (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="dcbb1-144">sys.dm_db_persisted_sku_features &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-persisted-sku-features-transact-sql)  
  
  
