---
title: Другие проблемы при обновлении ядро СУБД | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Database Engine [SQL Server], upgrading
ms.assetid: 78a1d8e8-fa97-476f-8777-84617d145340
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: db496112fc975304bb2d7da9d9ea1c52e6dd8bec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657481"
---
# <a name="other-database-engine-upgrade-issues"></a><span data-ttu-id="c35a3-102">Другие проблемы обновления компонента Database Engine</span><span class="sxs-lookup"><span data-stu-id="c35a3-102">Other Database Engine Upgrade Issues</span></span>
  <span data-ttu-id="c35a3-103">Текущая версия помощника по обновлению не может обнаружить следующие проблемы, возникающие при обновлении.</span><span class="sxs-lookup"><span data-stu-id="c35a3-103">The following upgrade issues cannot be detected by the current version of Upgrade Advisor.</span></span> <span data-ttu-id="c35a3-104">Ознакомьтесь с нижеприведенным списком проблем, чтобы оценить потенциальные последствия для систем.</span><span class="sxs-lookup"><span data-stu-id="c35a3-104">Review the issues listed below to evaluate their potential impact to your systems.</span></span>  
  
## <a name="multiple-database-engine-deprecated-features"></a><span data-ttu-id="c35a3-105">Некоторые устаревшие функции компонента Database Engine</span><span class="sxs-lookup"><span data-stu-id="c35a3-105">Multiple Database Engine Deprecated Features</span></span>  
 <span data-ttu-id="c35a3-106">Следующие инструкции или параметры [!INCLUDE[tsql](../../includes/tsql-md.md)] устарели.</span><span class="sxs-lookup"><span data-stu-id="c35a3-106">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements or options are deprecated:</span></span>  
  
-   <span data-ttu-id="c35a3-107">параметры NO_LOG и TRUNCATE_ONLY инструкции BACKUP LOG;</span><span class="sxs-lookup"><span data-stu-id="c35a3-107">NO_LOG and TRUNCATE_ONLY options of BACKUP LOG</span></span>  
  
-   <span data-ttu-id="c35a3-108">BACKUP TRANSACTION;</span><span class="sxs-lookup"><span data-stu-id="c35a3-108">BACKUP TRANSACTION</span></span>  
  
-   <span data-ttu-id="c35a3-109">RESTORE TRANSACTION;</span><span class="sxs-lookup"><span data-stu-id="c35a3-109">RESTORE TRANSACTION</span></span>  
  
-   <span data-ttu-id="c35a3-110">DUMP;</span><span class="sxs-lookup"><span data-stu-id="c35a3-110">DUMP</span></span>  
  
-   <span data-ttu-id="c35a3-111">LOAD</span><span class="sxs-lookup"><span data-stu-id="c35a3-111">LOAD</span></span>  
  
-   <span data-ttu-id="c35a3-112">DBCC CONCURRENCYVIOLATION</span><span class="sxs-lookup"><span data-stu-id="c35a3-112">DBCC CONCURRENCYVIOLATION</span></span>  
  
-   <span data-ttu-id="c35a3-113">sp_addalias</span><span class="sxs-lookup"><span data-stu-id="c35a3-113">sp_addalias</span></span>  
  
-   <span data-ttu-id="c35a3-114">sp_addgroup</span><span class="sxs-lookup"><span data-stu-id="c35a3-114">sp_addgroup</span></span>  
  
-   <span data-ttu-id="c35a3-115">sp_changegroup</span><span class="sxs-lookup"><span data-stu-id="c35a3-115">sp_changegroup</span></span>  
  
-   <span data-ttu-id="c35a3-116">sp_dropgroup</span><span class="sxs-lookup"><span data-stu-id="c35a3-116">sp_dropgroup</span></span>  
  
-   <span data-ttu-id="c35a3-117">sp_helpgroup</span><span class="sxs-lookup"><span data-stu-id="c35a3-117">sp_helpgroup</span></span>  
  
-   <span data-ttu-id="c35a3-118">syssegments</span><span class="sxs-lookup"><span data-stu-id="c35a3-118">syssegments</span></span>  
  
 <span data-ttu-id="c35a3-119">Использование протокола VIA для подключения к компоненту [!INCLUDE[ssDE](../../includes/ssde-md.md)] устарело.</span><span class="sxs-lookup"><span data-stu-id="c35a3-119">Use of the VIA protocol to connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is deprecated.</span></span>  
  
## <a name="new-data-types"></a><span data-ttu-id="c35a3-120">Новые типы данных</span><span class="sxs-lookup"><span data-stu-id="c35a3-120">New Data Types</span></span>  
 <span data-ttu-id="c35a3-121">Следующие типы данных будут зарезервированными системными типами.</span><span class="sxs-lookup"><span data-stu-id="c35a3-121">The following will be reserved system types.</span></span> <span data-ttu-id="c35a3-122">Перед обновлением или сразу после обновления необходимо переименовать существующие конфликтующие типы, определяемые пользователем.</span><span class="sxs-lookup"><span data-stu-id="c35a3-122">Rename the existing conflicting user defined types either before or after upgrade.</span></span>  
  
-   <span data-ttu-id="c35a3-123">Geography</span><span class="sxs-lookup"><span data-stu-id="c35a3-123">Geography</span></span>  
  
-   <span data-ttu-id="c35a3-124">Геометрия</span><span class="sxs-lookup"><span data-stu-id="c35a3-124">Geometry</span></span>  
  
-   <span data-ttu-id="c35a3-125">Datetime2</span><span class="sxs-lookup"><span data-stu-id="c35a3-125">Datetime2</span></span>  
  
-   <span data-ttu-id="c35a3-126">HierarchyID</span><span class="sxs-lookup"><span data-stu-id="c35a3-126">HierarchyID</span></span>  
  
## <a name="target-table-of-the-output-into-clause-cannot-have-any-defined-triggers"></a><span data-ttu-id="c35a3-127">Целевая таблица для предложения OUTPUT INTO не может содержать определяемых триггеров.</span><span class="sxs-lookup"><span data-stu-id="c35a3-127">Target Table of the OUTPUT INTO Clause Cannot Have Any Defined Triggers</span></span>  
 <span data-ttu-id="c35a3-128">Выходные данные в целевую таблицу, если в таблице есть включенные триггеры, не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="c35a3-128">OUTPUT INTO a target table when the table has any enabled triggers is not supported.</span></span>  
  
## <a name="compile-time-error-for-udfs-when-the-target-of-an-output-into-clause-is-a-table"></a><span data-ttu-id="c35a3-129">Ошибки времени компиляции для определяемых пользователем функций в случаях, если целевой объект предложения OUTPUT INTO — таблица</span><span class="sxs-lookup"><span data-stu-id="c35a3-129">Compile Time Error for UDFs When the Target of an OUTPUT INTO Clause is a Table</span></span>  
 <span data-ttu-id="c35a3-130">Нельзя использовать определяемую пользователем функцию, чтобы выполнить действия, изменяющие состояние базы данных.</span><span class="sxs-lookup"><span data-stu-id="c35a3-130">User-defined functions (UDF) cannot be used to perform actions that modify the database state.</span></span> <span data-ttu-id="c35a3-131">Например, такая функция не может выполнять инструкции DDL (CREATE/ALTER/DROP) и DML (INSERT/UPDATE/DELETE) ни на каких объектах, кроме табличных переменных.</span><span class="sxs-lookup"><span data-stu-id="c35a3-131">For example, a UDF cannot perform any DDL (CREATE/ALTER/DROP) or DML (INSERT/UPDATE/DELETE) actions on any objects, except for table variables.</span></span>  
  
## <a name="merge-is-a-reserved-keyword"></a><span data-ttu-id="c35a3-132">MERGE является зарезервированным ключевым словом.</span><span class="sxs-lookup"><span data-stu-id="c35a3-132">MERGE is a Reserved Keyword</span></span>  
 <span data-ttu-id="c35a3-133">MERGE теперь является полностью зарезервированным ключевым словом.</span><span class="sxs-lookup"><span data-stu-id="c35a3-133">MERGE is now a fully-reserved keyword.</span></span> <span data-ttu-id="c35a3-134">Поэтому в приложениях не должно быть объектов (таблиц, столбцов и пр.) с именем MERGE.</span><span class="sxs-lookup"><span data-stu-id="c35a3-134">Applications can no longer have objects (table, column, etc.) called MERGE.</span></span>  
  
## <a name="rename-cdc-schema"></a><span data-ttu-id="c35a3-135">Переименование схемы CDC</span><span class="sxs-lookup"><span data-stu-id="c35a3-135">Rename CDC Schema</span></span>  
 <span data-ttu-id="c35a3-136">Существует имя схемы CDC.</span><span class="sxs-lookup"><span data-stu-id="c35a3-136">There is a schema name called CDC.</span></span> <span data-ttu-id="c35a3-137">Это имя схемы не может использоваться, если для базы данных включена система **отслеживания измененных данных** .</span><span class="sxs-lookup"><span data-stu-id="c35a3-137">This schema name cannot be in used if **Change Data Capture** is enabled for the database.</span></span>  
  
 <span data-ttu-id="c35a3-138">Перед включением системы **отслеживания измененных данных** для базы данных необходимо удалить схему cdc.</span><span class="sxs-lookup"><span data-stu-id="c35a3-138">You must drop the CDC schema before you enable **Change Data Capture** for the database.</span></span> <span data-ttu-id="c35a3-139">Это можно сделать до обновления или после.</span><span class="sxs-lookup"><span data-stu-id="c35a3-139">This step can be done before or after the upgrade.</span></span> <span data-ttu-id="c35a3-140">Удаление схемы производится следующим образом.</span><span class="sxs-lookup"><span data-stu-id="c35a3-140">To drop the schema, use the following steps:</span></span>  
  
1.  <span data-ttu-id="c35a3-141">Передайте объекты из схемы CDC в новую схему с помощью инструкции ALTER SCHEMA.</span><span class="sxs-lookup"><span data-stu-id="c35a3-141">Transfer the objects from CDC schema to a new schema name using ALTER SCHEMA.</span></span>  
  
2.  <span data-ttu-id="c35a3-142">Проверьте разрешения на доступ к объектам в новой схеме.</span><span class="sxs-lookup"><span data-stu-id="c35a3-142">Verify permissions for the objects in the new schema.</span></span>  
  
3.  <span data-ttu-id="c35a3-143">Внесите необходимые изменения в приложение.</span><span class="sxs-lookup"><span data-stu-id="c35a3-143">Make necessary modifications to the application.</span></span>  
  
4.  <span data-ttu-id="c35a3-144">Удалите схему CDC с помощью инструкции DROP SCHEMA.</span><span class="sxs-lookup"><span data-stu-id="c35a3-144">Drop the CDC schema using DROP SCHEMA.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c35a3-145">См. также:</span><span class="sxs-lookup"><span data-stu-id="c35a3-145">See Also</span></span>  
 [<span data-ttu-id="c35a3-146">Проблемы обновления ядра СУБД</span><span class="sxs-lookup"><span data-stu-id="c35a3-146">Database Engine Upgrade Issues</span></span>](../../../2014/sql-server/install/database-engine-upgrade-issues.md)  
  
  
