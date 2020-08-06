---
title: Инструкции DDL, функции, хранимые процедуры и представления для полнотекстового поиска | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
ms.assetid: 98c36715-4195-482e-a4a3-d93ff65b75f1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 29b026ac60fd3f7d00ca519c4ced84533ce9740f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667665"
---
# <a name="full-text-search-ddl-functions-stored-procedures-and-views"></a><span data-ttu-id="036f7-102">Инструкции полнотекстового поиска DDL, функции, хранимые процедуры и представления</span><span class="sxs-lookup"><span data-stu-id="036f7-102">Full-Text Search DDL, Functions, Stored Procedures, and Views</span></span>
  <span data-ttu-id="036f7-103">Содержит список инструкций Transact-SQL и объектов базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , поддерживающих полнотекстовый поиск, включая функцию поиска свойств.</span><span class="sxs-lookup"><span data-stu-id="036f7-103">Lists the Transact-SQL statements and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database objects that support full-text search, including the property search feature.</span></span>  
  
 <span data-ttu-id="036f7-104">Этот список не содержит устаревшие объекты.</span><span class="sxs-lookup"><span data-stu-id="036f7-104">This list does not include deprecated objects.</span></span>  
  
 <span data-ttu-id="036f7-105">Список объектов базы данных, которые поддерживают семантический поиск, см. в разделе [Semantic Search DDL, Functions, Stored Procedures, and Views](../views/views.md).</span><span class="sxs-lookup"><span data-stu-id="036f7-105">For the list of database objects that support semantic search, see [Semantic Search DDL, Functions, Stored Procedures, and Views](../views/views.md).</span></span>  
  
##  <a name="transact-sql-data-definition-language-ddl-statements"></a><a name="ddl"></a> <span data-ttu-id="036f7-106">Инструкции языка описания данных (DDL) Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="036f7-106">Transact-SQL Data Definition Language (DDL) Statements</span></span>  
  
-   [<span data-ttu-id="036f7-107">CREATE FULLTEXT CATALOG (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-107">CREATE FULLTEXT CATALOG &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-fulltext-catalog-transact-sql)  
  
-   [<span data-ttu-id="036f7-108">CREATE FULLTEXT INDEX (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-108">CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-fulltext-index-transact-sql)  
  
-   [<span data-ttu-id="036f7-109">CREATE FULLTEXT STOPLIST (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-109">CREATE FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-fulltext-stoplist-transact-sql)  
  
-   [<span data-ttu-id="036f7-110">CREATE SEARCH PROPERTY LIST (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-110">CREATE SEARCH PROPERTY LIST &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-search-property-list-transact-sql)  
  
-   [<span data-ttu-id="036f7-111">ALTER FULLTEXT CATALOG (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-111">ALTER FULLTEXT CATALOG &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-fulltext-catalog-transact-sql)  
  
-   [<span data-ttu-id="036f7-112">ALTER FULLTEXT INDEX (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-112">ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-fulltext-index-transact-sql)  
  
-   [<span data-ttu-id="036f7-113">ALTER FULLTEXT STOPLIST (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-113">ALTER FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-fulltext-stoplist-transact-sql)  
  
-   [<span data-ttu-id="036f7-114">ALTER SEARCH PROPERTY LIST (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-114">ALTER SEARCH PROPERTY LIST &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-search-property-list-transact-sql)  
  
-   [<span data-ttu-id="036f7-115">DROP FULLTEXT CATALOG (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-115">DROP FULLTEXT CATALOG &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-fulltext-catalog-transact-sql)  
  
-   [<span data-ttu-id="036f7-116">DROP FULLTEXT INDEX (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-116">DROP FULLTEXT INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-fulltext-index-transact-sql)  
  
-   [<span data-ttu-id="036f7-117">DROP FULLTEXT STOPLIST (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-117">DROP FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-fulltext-stoplist-transact-sql)  
  
-   [<span data-ttu-id="036f7-118">DROP SEARCH PROPERTY LIST (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-118">DROP SEARCH PROPERTY LIST &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-search-property-list-transact-sql)  
  
##  <a name="system-predicates-and-functions"></a><a name="func"></a> <span data-ttu-id="036f7-119">Системные предикаты и функции</span><span class="sxs-lookup"><span data-stu-id="036f7-119">System Predicates and Functions</span></span>  
  
-   [<span data-ttu-id="036f7-120">CONTAINS (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-120">CONTAINS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/contains-transact-sql)  
  
-   [<span data-ttu-id="036f7-121">CONTAINSTABLE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-121">CONTAINSTABLE &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/containstable-transact-sql)  
  
-   [<span data-ttu-id="036f7-122">FREETEXT (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-122">FREETEXT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/freetext-transact-sql)  
  
-   [<span data-ttu-id="036f7-123">FREETEXTTABLE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-123">FREETEXTTABLE &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/freetexttable-transact-sql)  
  
##  <a name="system-metadata-functions"></a><a name="meta"></a> <span data-ttu-id="036f7-124">Системные функции метаданных</span><span class="sxs-lookup"><span data-stu-id="036f7-124">System Metadata Functions</span></span>  
  
-   [<span data-ttu-id="036f7-125">COLUMNPROPERTY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-125">COLUMNPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/columnproperty-transact-sql)  
  
-   [<span data-ttu-id="036f7-126">FULLTEXTCATALOGPROPERTY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-126">FULLTEXTCATALOGPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/fulltextcatalogproperty-transact-sql)  
  
-   [<span data-ttu-id="036f7-127">FULLTEXTSERVICEPROPERTY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-127">FULLTEXTSERVICEPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/fulltextserviceproperty-transact-sql)  
  
-   [<span data-ttu-id="036f7-128">INDEXPROPERTY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-128">INDEXPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/indexproperty-transact-sql)  
  
-   [<span data-ttu-id="036f7-129">OBJECTPROPERTY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-129">OBJECTPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/objectpropertyex-transact-sql)  
  
-   [<span data-ttu-id="036f7-130">OBJECTPROPERTYEX (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-130">OBJECTPROPERTYEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/objectproperty-transact-sql)  
  
-   [<span data-ttu-id="036f7-131">SERVERPROPERTY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-131">SERVERPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/serverproperty-transact-sql)  
  
##  <a name="system-stored-procedures"></a><a name="proc"></a> <span data-ttu-id="036f7-132">Системные хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="036f7-132">System Stored Procedures</span></span>  
  
-   [<span data-ttu-id="036f7-133">sp_fulltext_keymappings (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-133">sp_fulltext_keymappings &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-fulltext-keymappings-transact-sql)  
  
-   [<span data-ttu-id="036f7-134">sp_fulltext_load_thesaurus_file (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-134">sp_fulltext_load_thesaurus_file &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-fulltext-load-thesaurus-file-transact-sql)  
  
-   [<span data-ttu-id="036f7-135">sp_fulltext_pendingchanges (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-135">sp_fulltext_pendingchanges &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-fulltext-pendingchanges-transact-sql)  
  
-   [<span data-ttu-id="036f7-136">sp_fulltext_service (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-136">sp_fulltext_service &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-fulltext-service-transact-sql)  
  
-   [<span data-ttu-id="036f7-137">sp_help_fulltext_system_components (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-137">sp_help_fulltext_system_components &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-help-fulltext-system-components-transact-sql)  
  
##  <a name="system-views---catalog-views"></a><a name="cat"></a> <span data-ttu-id="036f7-138">Системные представления — представления каталога</span><span class="sxs-lookup"><span data-stu-id="036f7-138">System Views - Catalog Views</span></span>  
  
-   [<span data-ttu-id="036f7-139">sys.fulltext_catalogs (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-139">sys.fulltext_catalogs &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-catalogs-transact-sql)  
  
-   [<span data-ttu-id="036f7-140">sys.fulltext_document_types (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-140">sys.fulltext_document_types &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-document-types-transact-sql)  
  
-   [<span data-ttu-id="036f7-141">sys.fulltext_index_catalog_usages (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-141">sys.fulltext_index_catalog_usages &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-index-catalog-usages-transact-sql)  
  
-   [<span data-ttu-id="036f7-142">sys.fulltext_index_columns (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-142">sys.fulltext_index_columns &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-index-columns-transact-sql)  
  
-   [<span data-ttu-id="036f7-143">sys.fulltext_index_fragments (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-143">sys.fulltext_index_fragments &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-index-fragments-transact-sql)  
  
-   [<span data-ttu-id="036f7-144">sys.fulltext_indexes (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-144">sys.fulltext_indexes &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-indexes-transact-sql)  
  
-   [<span data-ttu-id="036f7-145">sys.fulltext_languages (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-145">sys.fulltext_languages &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql)  
  
-   [<span data-ttu-id="036f7-146">sys.fulltext_stoplists (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-146">sys.fulltext_stoplists &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-stoplists-transact-sql)  
  
-   [<span data-ttu-id="036f7-147">sys.fulltext_stopwords (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-147">sys.fulltext_stopwords &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-stopwords-transact-sql)  
  
-   [<span data-ttu-id="036f7-148">sys.fulltext_system_stopwords (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-148">sys.fulltext_system_stopwords &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-system-stopwords-transact-sql)  
  
-   [<span data-ttu-id="036f7-149">sys.registered_search_properties (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-149">sys.registered_search_properties &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-registered-search-properties-transact-sql)  
  
-   [<span data-ttu-id="036f7-150">sys.registered_search_property_lists (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-150">sys.registered_search_property_lists &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-registered-search-property-lists-transact-sql)  
  
##  <a name="system-views---dynamic-management-views"></a><a name="dmv"></a> <span data-ttu-id="036f7-151">Системные представления — динамические административные представления</span><span class="sxs-lookup"><span data-stu-id="036f7-151">System Views - Dynamic Management Views</span></span>  
  
-   [<span data-ttu-id="036f7-152">sys.dm_fts_active_catalogs (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-152">sys.dm_fts_active_catalogs &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-active-catalogs-transact-sql)  
  
-   [<span data-ttu-id="036f7-153">sys.dm_fts_fdhosts (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-153">sys.dm_fts_fdhosts &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-fdhosts-transact-sql)  
  
-   [<span data-ttu-id="036f7-154">sys.dm_fts_index_keywords (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-154">sys.dm_fts_index_keywords &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-index-keywords-transact-sql)  
  
-   [<span data-ttu-id="036f7-155">sys.dm_fts_index_keywords_by_document (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-155">sys.dm_fts_index_keywords_by_document &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-index-keywords-by-document-transact-sql)  
  
-   [<span data-ttu-id="036f7-156">sys.dm_fts_index_keywords_by_property (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-156">sys.dm_fts_index_keywords_by_property &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-index-keywords-by-property-transact-sql)  
  
-   [<span data-ttu-id="036f7-157">sys.dm_fts_index_population (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-157">sys.dm_fts_index_population &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-index-population-transact-sql)  
  
-   [<span data-ttu-id="036f7-158">sys.dm_fts_memory_buffers (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-158">sys.dm_fts_memory_buffers &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-memory-buffers-transact-sql)  
  
-   [<span data-ttu-id="036f7-159">sys.dm_fts_memory_pools (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-159">sys.dm_fts_memory_pools &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-memory-pools-transact-sql)  
  
-   [<span data-ttu-id="036f7-160">sys.dm_fts_outstanding_batches (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-160">sys.dm_fts_outstanding_batches &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-outstanding-batches-transact-sql)  
  
-   [<span data-ttu-id="036f7-161">sys.dm_fts_parser (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-161">sys.dm_fts_parser &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-parser-transact-sql)  
  
-   [<span data-ttu-id="036f7-162">sys.dm_fts_population_ranges (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="036f7-162">sys.dm_fts_population_ranges &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-population-ranges-transact-sql)  
  
  
