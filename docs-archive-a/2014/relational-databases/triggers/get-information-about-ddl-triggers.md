---
title: Получение сведений о триггерах DDL | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- metadata [SQL Server], triggers
- status information [SQL Server], DDL triggers
- DDL triggers, metadata
ms.assetid: 462becea-292a-4b9e-bb98-533e89733911
author: rothja
ms.author: jroth
ms.openlocfilehash: 9cd71d188c2f53bd9872359199c07d700688552d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668149"
---
# <a name="get-information-about-ddl-triggers"></a><span data-ttu-id="7afb8-102">Получение сведений о триггерах DDL</span><span class="sxs-lookup"><span data-stu-id="7afb8-102">Get Information About DDL Triggers</span></span>
  <span data-ttu-id="7afb8-103">Представления каталога, приведенные в этом разделе, можно использовать для получения сведений о триггерах DDL.</span><span class="sxs-lookup"><span data-stu-id="7afb8-103">The catalog views listed in this section can be used to get information about DDL Triggers.</span></span>  
  
 <span data-ttu-id="7afb8-104">**Получение сведений о событиях или группах событий, при возникновении которых может сработать триггер DDL.**</span><span class="sxs-lookup"><span data-stu-id="7afb8-104">**To get information about the events or event groups on which a DDL trigger can fire.**</span></span>  
  
-   [<span data-ttu-id="7afb8-105">sys.trigger_event_types (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="7afb8-105">sys.trigger_event_types &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-trigger-event-types-transact-sql)  
  
 <span data-ttu-id="7afb8-106">**Просмотр зависимостей триггера**</span><span class="sxs-lookup"><span data-stu-id="7afb8-106">**To view the dependencies of a trigger**</span></span>  
  
-   [<span data-ttu-id="7afb8-107">sys.sql_expression_dependencies (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="7afb8-107">sys.sql_expression_dependencies &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql)  
  
-   [<span data-ttu-id="7afb8-108">Функция динамического управления sys.dm_sql_referenced_entities (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="7afb8-108">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referenced-entities-transact-sql)  
  
-   [<span data-ttu-id="7afb8-109">sys.dm_sql_referencing_entities (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="7afb8-109">sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referencing-entities-transact-sql)  
  
## <a name="database-scoped-ddl-triggers"></a><span data-ttu-id="7afb8-110">Триггеры DDL уровня базы данных</span><span class="sxs-lookup"><span data-stu-id="7afb8-110">Database-Scoped DDL Triggers</span></span>  
 <span data-ttu-id="7afb8-111">**Сведения о триггерах с областью действия на уровне базы данных**</span><span class="sxs-lookup"><span data-stu-id="7afb8-111">**To get information about database-scoped triggers**</span></span>  
  
-   [<span data-ttu-id="7afb8-112">sys.triggers (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="7afb8-112">sys.triggers &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql)  
  
 <span data-ttu-id="7afb8-113">**Сведения о событиях базы данных, вызывающих срабатывание триггеров**</span><span class="sxs-lookup"><span data-stu-id="7afb8-113">**To get information about database events that fire triggers**</span></span>  
  
-   [<span data-ttu-id="7afb8-114">sys.trigger_events (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="7afb8-114">sys.trigger_events &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-trigger-events-transact-sql)  
  
 <span data-ttu-id="7afb8-115">**Определения триггеров уровня базы данных**</span><span class="sxs-lookup"><span data-stu-id="7afb8-115">**To view the definition of a database-scoped trigger**</span></span>  
  
-   [<span data-ttu-id="7afb8-116">sys.sql_modules (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="7afb8-116">sys.sql_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql)  
  
 <span data-ttu-id="7afb8-117">**Сведения о триггерах среды CLR уровня базы данных**</span><span class="sxs-lookup"><span data-stu-id="7afb8-117">**To get information about CLR database-scoped triggers**</span></span>  
  
-   [<span data-ttu-id="7afb8-118">sys.assembly_modules (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="7afb8-118">sys.assembly_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql)  
  
## <a name="server-scoped-ddl-triggers"></a><span data-ttu-id="7afb8-119">Триггеры DDL уровня сервера</span><span class="sxs-lookup"><span data-stu-id="7afb8-119">Server-Scoped DDL Triggers</span></span>  
 <span data-ttu-id="7afb8-120">**Сведения о триггерах с областью действия на уровне сервера**</span><span class="sxs-lookup"><span data-stu-id="7afb8-120">**To get information about server-scoped triggers**</span></span>  
  
-   [<span data-ttu-id="7afb8-121">sys.server_triggers (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="7afb8-121">sys.server_triggers &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql)  
  
 <span data-ttu-id="7afb8-122">**Сведения о событиях сервера, вызывающих срабатывание триггеров**</span><span class="sxs-lookup"><span data-stu-id="7afb8-122">**To get information about server events that fire triggers**</span></span>  
  
-   [<span data-ttu-id="7afb8-123">sys.server_trigger_events (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="7afb8-123">sys.server_trigger_events &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql)  
  
 <span data-ttu-id="7afb8-124">**Определения триггеров с областью действия на уровне сервера**</span><span class="sxs-lookup"><span data-stu-id="7afb8-124">**To view the definition of a server-scoped trigger**</span></span>  
  
-   [<span data-ttu-id="7afb8-125">sys.server_sql_modules (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="7afb8-125">sys.server_sql_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql)  
  
 <span data-ttu-id="7afb8-126">**Сведения о триггерах CLR с областью действия на уровне сервера**</span><span class="sxs-lookup"><span data-stu-id="7afb8-126">**To get information about CLR server-scoped triggers**</span></span>  
  
-   [<span data-ttu-id="7afb8-127">sys.server_assembly_modules (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="7afb8-127">sys.server_assembly_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-assembly-modules-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="7afb8-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="7afb8-128">See Also</span></span>  
 [<span data-ttu-id="7afb8-129">Триггеры DDL</span><span class="sxs-lookup"><span data-stu-id="7afb8-129">DDL Triggers</span></span>](../triggers/ddl-triggers.md)  
  
  
