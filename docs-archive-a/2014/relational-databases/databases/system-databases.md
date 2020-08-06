---
title: Системные базы данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- system databases [SQL Server]
- displaying system database data
- modifying system data
- viewing system database data
ms.assetid: 30468a7c-4225-4d35-aa4a-ffa7da4f1282
author: stevestein
ms.author: sstein
ms.openlocfilehash: 65deee685c2205a7c6e41ed86f71c69639555d7c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728310"
---
# <a name="system-databases"></a><span data-ttu-id="81f29-102">Системные базы данных</span><span class="sxs-lookup"><span data-stu-id="81f29-102">System Databases</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="81f29-103">входят следующие системные базы данных.</span><span class="sxs-lookup"><span data-stu-id="81f29-103">includes the following system databases.</span></span>  
  
|<span data-ttu-id="81f29-104">Системная база данных</span><span class="sxs-lookup"><span data-stu-id="81f29-104">System database</span></span>|<span data-ttu-id="81f29-105">Description</span><span class="sxs-lookup"><span data-stu-id="81f29-105">Description</span></span>|  
|---------------------|-----------------|  
|[<span data-ttu-id="81f29-106">База данных master</span><span class="sxs-lookup"><span data-stu-id="81f29-106">master Database</span></span>](master-database.md)|<span data-ttu-id="81f29-107">В этой базе данных хранятся все данные системного уровня для экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="81f29-107">Records all the system-level information for an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="81f29-108">База данных msdb</span><span class="sxs-lookup"><span data-stu-id="81f29-108">msdb Database</span></span>](msdb-database.md)|<span data-ttu-id="81f29-109">Используется агентом SQL Server для планирования предупреждений и задач.</span><span class="sxs-lookup"><span data-stu-id="81f29-109">Is used by SQL Server Agent for scheduling alerts and jobs.</span></span>|  
|[<span data-ttu-id="81f29-110">Шаблон базы данных</span><span class="sxs-lookup"><span data-stu-id="81f29-110">model Database</span></span>](model-database.md)|<span data-ttu-id="81f29-111">Используется в качестве шаблона для всех баз данных, создаваемых в экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="81f29-111">Is used as the template for all databases created on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="81f29-112">Изменение размера, параметров сортировки, модели восстановления и других параметров базы данных **model** приводит к изменению соответствующих параметров всех баз данных, создаваемых после изменения.</span><span class="sxs-lookup"><span data-stu-id="81f29-112">Modifications made to the **model** database, such as database size, collation, recovery model, and other database options, are applied to any databases created afterward.</span></span>|  
|[<span data-ttu-id="81f29-113">База данных ресурсов</span><span class="sxs-lookup"><span data-stu-id="81f29-113">Resource Database</span></span>](resource-database.md)|<span data-ttu-id="81f29-114">База данных только для чтения. Содержит системные объекты, которые входят в состав [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="81f29-114">Is a read-only database that contains system objects that are included with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="81f29-115">Системные объекты физически хранятся в базе данных **Resource** , но логически отображаются в схеме **sys** любой базы данных.</span><span class="sxs-lookup"><span data-stu-id="81f29-115">System objects are physically persisted in the **Resource** database, but they logically appear in the **sys** schema of every database.</span></span>|  
|[<span data-ttu-id="81f29-116">База данных tempdb</span><span class="sxs-lookup"><span data-stu-id="81f29-116">tempdb Database</span></span>](tempdb-database.md)|<span data-ttu-id="81f29-117">Рабочее пространство для временных объектов или взаимодействия результирующих наборов.</span><span class="sxs-lookup"><span data-stu-id="81f29-117">Is a workspace for holding temporary objects or intermediate result sets.</span></span>|  
  
## <a name="modifying-system-data"></a><span data-ttu-id="81f29-118">изменение системных данных</span><span class="sxs-lookup"><span data-stu-id="81f29-118">Modifying System Data</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="81f29-119">не поддерживает прямое обновление пользователями данных в таких системных объектах, как таблицы, системные хранимые процедуры и представления каталогов.</span><span class="sxs-lookup"><span data-stu-id="81f29-119">does not support users directly updating the information in system objects such as system tables, system stored procedures, and catalog views.</span></span> <span data-ttu-id="81f29-120">Вместо этого [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] предоставляет полный набор административных средств, позволяющих пользователям управлять всей системой, пользователями и объектами базы данных.</span><span class="sxs-lookup"><span data-stu-id="81f29-120">Instead, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides a complete set of administrative tools that let users fully administer their system and manage all users and objects in a database.</span></span> <span data-ttu-id="81f29-121">следующие основные параметры.</span><span class="sxs-lookup"><span data-stu-id="81f29-121">These include the following:</span></span>  
  
-   <span data-ttu-id="81f29-122">Административные программы, например [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="81f29-122">Administration utilities, such as [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="81f29-123">SQL-SMO API.</span><span class="sxs-lookup"><span data-stu-id="81f29-123">SQL-SMO API.</span></span> <span data-ttu-id="81f29-124">Этот программный интерфейс позволяет программистам включать любые административные возможности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в разрабатываемые приложения.</span><span class="sxs-lookup"><span data-stu-id="81f29-124">This lets programmers include complete functionality for administering [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in their applications.</span></span>  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="81f29-125">.</span><span class="sxs-lookup"><span data-stu-id="81f29-125">scripts and stored procedures.</span></span> <span data-ttu-id="81f29-126">Можно использовать системные хранимые процедуры и DDL-инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="81f29-126">These can use system stored procedures and [!INCLUDE[tsql](../../includes/tsql-md.md)] DDL statements.</span></span>  
  
 <span data-ttu-id="81f29-127">Эти средства защищают приложения от изменений системных объектов.</span><span class="sxs-lookup"><span data-stu-id="81f29-127">These tools shield applications from changes in the system objects.</span></span> <span data-ttu-id="81f29-128">Например, иногда в целях поддержки новых возможностей, добавленных в новые версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , приходится изменять системные таблицы этих версий [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="81f29-128">For example, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sometimes has to change the system tables in new versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to support new functionality that is being added in that version.</span></span> <span data-ttu-id="81f29-129">Приложения, выполняющие инструкции SELECT, которые ссылаются непосредственно на системные таблицы, часто зависят от старого формата этих таблиц.</span><span class="sxs-lookup"><span data-stu-id="81f29-129">Applications issuing SELECT statements that directly reference system tables are frequently dependent on the old format of the system tables.</span></span> <span data-ttu-id="81f29-130">Обновление сайтов до новой версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] невозможно, пока для них не будут переписаны приложения, выполняющие выборку из системных таблиц.</span><span class="sxs-lookup"><span data-stu-id="81f29-130">Sites may not be able to upgrade to a new version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] until they have rewritten applications that are selecting from system tables.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="81f29-131">учитывает существующие системные хранимые процедуры, DDL и опубликованные интерфейсы SQL-SMO и работает, поддерживая обратную совместимость этих интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="81f29-131">considers the system stored procedures, DDL, and SQL-SMO published interfaces, and works to maintain the backward compatibility of these interfaces.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="81f29-132">не поддерживаются триггеры, заданные для системных таблиц, поскольку они могут влиять на работу системы.</span><span class="sxs-lookup"><span data-stu-id="81f29-132">does not support triggers defined on the system tables, because they might modify the operation of the system.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="81f29-133">Системные базы данных не могут размещаться в общих каталогах UNC.</span><span class="sxs-lookup"><span data-stu-id="81f29-133">System databases cannot reside on UNC share directories.</span></span>  
  
## <a name="viewing-system-database-data"></a><span data-ttu-id="81f29-134">просмотр данных системной базы данных</span><span class="sxs-lookup"><span data-stu-id="81f29-134">Viewing System Database Data</span></span>  
 <span data-ttu-id="81f29-135">Не следует создавать инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] , которые выполняют запросы непосредственно к системным таблицам, если только это не единственный способ получить данные, необходимые для приложения.</span><span class="sxs-lookup"><span data-stu-id="81f29-135">You should not code [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that directly query the system tables, unless that is the only way to obtain the information that is required by the application.</span></span> <span data-ttu-id="81f29-136">Приложения должны получать данные каталога и системные данные с помощью следующих средств:</span><span class="sxs-lookup"><span data-stu-id="81f29-136">Instead, applications should obtain catalog and system information by using the following:</span></span>  
  
-   <span data-ttu-id="81f29-137">Представления системного каталога</span><span class="sxs-lookup"><span data-stu-id="81f29-137">System catalog views</span></span>  
  
-   <span data-ttu-id="81f29-138">SQL-SMO;</span><span class="sxs-lookup"><span data-stu-id="81f29-138">SQL-SMO</span></span>  
  
-   <span data-ttu-id="81f29-139">интерфейса инструментария управления Windows (WMI);</span><span class="sxs-lookup"><span data-stu-id="81f29-139">Windows Management Instrumentation (WMI) interface</span></span>  
  
-   <span data-ttu-id="81f29-140">функций каталога, методов, атрибутов или свойств данных API, использующихся в приложении, например ADO, OLE DB или ODBC;</span><span class="sxs-lookup"><span data-stu-id="81f29-140">Catalog functions, methods, attributes, or properties of the data API used in the application, such as ADO, OLE DB, or ODBC.</span></span>  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="81f29-141">встроенных функций и системных хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="81f29-141">system stored procedures and built-in functions.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="81f29-142">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="81f29-142">Related Tasks</span></span>  
 [<span data-ttu-id="81f29-143">Резервное копирование и восстановление системных баз данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="81f29-143">Back Up and Restore of System Databases &#40;SQL Server&#41;</span></span>](../backup-restore/back-up-and-restore-of-system-databases-sql-server.md)  
  
 [<span data-ttu-id="81f29-144">Скрыть системные объекты в обозревателе объектов</span><span class="sxs-lookup"><span data-stu-id="81f29-144">Hide System Objects in Object Explorer</span></span>](../../ssms/object/object-explorer.md)  
  
## <a name="related-content"></a><span data-ttu-id="81f29-145">См. также</span><span class="sxs-lookup"><span data-stu-id="81f29-145">Related Content</span></span>  
 [<span data-ttu-id="81f29-146">Представления каталога (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="81f29-146">Catalog Views &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/catalog-views-transact-sql)  
  
 [<span data-ttu-id="81f29-147">Базы данных</span><span class="sxs-lookup"><span data-stu-id="81f29-147">Databases</span></span>](databases.md)  
  
  
