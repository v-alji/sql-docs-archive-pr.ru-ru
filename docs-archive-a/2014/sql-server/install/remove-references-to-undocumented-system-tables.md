---
title: Удалить ссылки на недокументированные системные таблицы | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- undocumented system tables [SQL Server]
- system tables [SQL Server]
ms.assetid: 010b1236-2219-4bf4-a6db-e3fc3abfa37a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 45c38038ee3d3214e4303c0ddbe0110be926c37e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735874"
---
# <a name="remove-references-to-undocumented-system-tables"></a><span data-ttu-id="f080c-102">Удаление ссылки на недокументированные системные таблицы</span><span class="sxs-lookup"><span data-stu-id="f080c-102">Remove references to undocumented system tables</span></span>
  <span data-ttu-id="f080c-103">Многие системные таблицы, которые были недокументированными в предыдущих версиях, изменились или больше не существуют, поэтому использование таких таблиц может вызывать ошибки после обновления.</span><span class="sxs-lookup"><span data-stu-id="f080c-103">Many system tables that were undocumented in prior releases have changed or no longer exist; therefore, using these tables may cause errors after upgrading.</span></span> <span data-ttu-id="f080c-104">Поскольку помощник по обновлению ищет ссылки на системные таблицы, он сообщит о ссылках на любые пользовательские таблицы, имена которых совпадают с именами системных таблиц.</span><span class="sxs-lookup"><span data-stu-id="f080c-104">Because Upgrade Advisor looks for references to system table names, it will report references to any user tables that have the same names as system tables.</span></span>  
  
## <a name="component"></a><span data-ttu-id="f080c-105">Компонент</span><span class="sxs-lookup"><span data-stu-id="f080c-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="f080c-106">Описание</span><span class="sxs-lookup"><span data-stu-id="f080c-106">Description</span></span>  
 <span data-ttu-id="f080c-107">Удалены следующие недокументированные системные таблицы.</span><span class="sxs-lookup"><span data-stu-id="f080c-107">The following undocumented system tables are removed:</span></span>  
  
-   <span data-ttu-id="f080c-108">**spt_datatype_info**</span><span class="sxs-lookup"><span data-stu-id="f080c-108">**spt_datatype_info**</span></span>  
  
-   <span data-ttu-id="f080c-109">**spt_datatype_info_ext**</span><span class="sxs-lookup"><span data-stu-id="f080c-109">**spt_datatype_info_ext**</span></span>  
  
-   <span data-ttu-id="f080c-110">**spt_provider_types**</span><span class="sxs-lookup"><span data-stu-id="f080c-110">**spt_provider_types**</span></span>  
  
-   <span data-ttu-id="f080c-111">**spt_server_info**</span><span class="sxs-lookup"><span data-stu-id="f080c-111">**spt_server_info**</span></span>  
  
-   <span data-ttu-id="f080c-112">**spt_values**</span><span class="sxs-lookup"><span data-stu-id="f080c-112">**spt_values**</span></span>  
  
-   <span data-ttu-id="f080c-113">**sysfulltextnotify**</span><span class="sxs-lookup"><span data-stu-id="f080c-113">**sysfulltextnotify**</span></span>  
  
-   <span data-ttu-id="f080c-114">**syslocks**</span><span class="sxs-lookup"><span data-stu-id="f080c-114">**syslocks**</span></span>  
  
-   <span data-ttu-id="f080c-115">**sysproperties**</span><span class="sxs-lookup"><span data-stu-id="f080c-115">**sysproperties**</span></span>  
  
-   <span data-ttu-id="f080c-116">**sysprotects_aux**</span><span class="sxs-lookup"><span data-stu-id="f080c-116">**sysprotects_aux**</span></span>  
  
-   <span data-ttu-id="f080c-117">**sysprotects_view**</span><span class="sxs-lookup"><span data-stu-id="f080c-117">**sysprotects_view**</span></span>  
  
-   <span data-ttu-id="f080c-118">**SYSREMOTE_CATALOGS**</span><span class="sxs-lookup"><span data-stu-id="f080c-118">**SYSREMOTE_CATALOGS**</span></span>  
  
-   <span data-ttu-id="f080c-119">**SYSREMOTE_COLUMN_PRIVILEGES**</span><span class="sxs-lookup"><span data-stu-id="f080c-119">**SYSREMOTE_COLUMN_PRIVILEGES**</span></span>  
  
-   <span data-ttu-id="f080c-120">**SYSREMOTE_COLUMNS**</span><span class="sxs-lookup"><span data-stu-id="f080c-120">**SYSREMOTE_COLUMNS**</span></span>  
  
-   <span data-ttu-id="f080c-121">**SYSREMOTE_FOREIGN_KEYS**</span><span class="sxs-lookup"><span data-stu-id="f080c-121">**SYSREMOTE_FOREIGN_KEYS**</span></span>  
  
-   <span data-ttu-id="f080c-122">**SYSREMOTE_INDEXES**</span><span class="sxs-lookup"><span data-stu-id="f080c-122">**SYSREMOTE_INDEXES**</span></span>  
  
-   <span data-ttu-id="f080c-123">**SYSREMOTE_PRIMARY_KEYS**</span><span class="sxs-lookup"><span data-stu-id="f080c-123">**SYSREMOTE_PRIMARY_KEYS**</span></span>  
  
-   <span data-ttu-id="f080c-124">**SYSREMOTE_PROVIDER_TYPES**</span><span class="sxs-lookup"><span data-stu-id="f080c-124">**SYSREMOTE_PROVIDER_TYPES**</span></span>  
  
-   <span data-ttu-id="f080c-125">**SYSREMOTE_SCHEMATA**</span><span class="sxs-lookup"><span data-stu-id="f080c-125">**SYSREMOTE_SCHEMATA**</span></span>  
  
-   <span data-ttu-id="f080c-126">**SYSREMOTE_STATISTICS**</span><span class="sxs-lookup"><span data-stu-id="f080c-126">**SYSREMOTE_STATISTICS**</span></span>  
  
-   <span data-ttu-id="f080c-127">**SYSREMOTE_TABLE_PRIVILEGES**</span><span class="sxs-lookup"><span data-stu-id="f080c-127">**SYSREMOTE_TABLE_PRIVILEGES**</span></span>  
  
-   <span data-ttu-id="f080c-128">**SYSREMOTE_TABLES**</span><span class="sxs-lookup"><span data-stu-id="f080c-128">**SYSREMOTE_TABLES**</span></span>  
  
-   <span data-ttu-id="f080c-129">**SYSREMOTE_VIEWS**</span><span class="sxs-lookup"><span data-stu-id="f080c-129">**SYSREMOTE_VIEWS**</span></span>  
  
-   <span data-ttu-id="f080c-130">**syssegments**</span><span class="sxs-lookup"><span data-stu-id="f080c-130">**syssegments**</span></span>  
  
-   <span data-ttu-id="f080c-131">**sysxlogins**</span><span class="sxs-lookup"><span data-stu-id="f080c-131">**sysxlogins**</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="f080c-132">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="f080c-132">Corrective Action</span></span>  
 <span data-ttu-id="f080c-133">Измените приложения в соответствии со следующей таблицей.</span><span class="sxs-lookup"><span data-stu-id="f080c-133">Modify your applications according to the following table.</span></span>  
  
|<span data-ttu-id="f080c-134">Вместо</span><span class="sxs-lookup"><span data-stu-id="f080c-134">Instead of</span></span>|<span data-ttu-id="f080c-135">Использование</span><span class="sxs-lookup"><span data-stu-id="f080c-135">Use</span></span>|  
|----------------|---------|  
|<span data-ttu-id="f080c-136">**sysfulltextnotify**</span><span class="sxs-lookup"><span data-stu-id="f080c-136">**sysfulltextnotify**</span></span>|<span data-ttu-id="f080c-137">Свойство**TableFulltextPendingChanges** функции OBJECTPROPERTYEX.</span><span class="sxs-lookup"><span data-stu-id="f080c-137">**TableFulltextPendingChanges** property of the OBJECTPROPERTYEX function.</span></span>|  
|<span data-ttu-id="f080c-138">**syslocks**</span><span class="sxs-lookup"><span data-stu-id="f080c-138">**syslocks**</span></span>|<span data-ttu-id="f080c-139">Динамическое административное представление**sys.dm_tran_locks** , хранимая процедура sp_lock или представление совместимости **sys.syslockinfo** .</span><span class="sxs-lookup"><span data-stu-id="f080c-139">**sys.dm_tran_locks** dynamic management view, or sp_lock, or the **sys.syslockinfo** compatibility view.</span></span>|  
|<span data-ttu-id="f080c-140">**sysproperties**</span><span class="sxs-lookup"><span data-stu-id="f080c-140">**sysproperties**</span></span>|<span data-ttu-id="f080c-141">Представление каталога**sys.extended_properties** или функция **fn_listextendedproperty** .</span><span class="sxs-lookup"><span data-stu-id="f080c-141">**sys.extended_properties** catalog view or the **fn_listextendedproperty** function</span></span>|  
|<span data-ttu-id="f080c-142">**sysxlogins**</span><span class="sxs-lookup"><span data-stu-id="f080c-142">**sysxlogins**</span></span>|<span data-ttu-id="f080c-143">Представление каталога**sys.server_principals** или представление совместимости **syslogins** .</span><span class="sxs-lookup"><span data-stu-id="f080c-143">**sys.server_principals** catalog view or **syslogins** compatibility view.</span></span>|  
|<span data-ttu-id="f080c-144">Все таблицы **spt_**</span><span class="sxs-lookup"><span data-stu-id="f080c-144">all **spt_** tables</span></span>|<span data-ttu-id="f080c-145">Замена отсутствует</span><span class="sxs-lookup"><span data-stu-id="f080c-145">No replacement available</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f080c-146">См. также:</span><span class="sxs-lookup"><span data-stu-id="f080c-146">See Also</span></span>  
 <span data-ttu-id="f080c-147">[Проблемы обновления ядро СУБД](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="f080c-147">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="f080c-148">Советник по переходу SQL Server 2014 &#91;New&#93;</span><span class="sxs-lookup"><span data-stu-id="f080c-148">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
