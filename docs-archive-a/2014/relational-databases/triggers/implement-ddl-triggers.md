---
title: Реализация триггеров DDL | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- DDL triggers, implementing
ms.assetid: f44e5340-1d18-40e9-828e-0ffcca091ae3
author: rothja
ms.author: jroth
ms.openlocfilehash: 110e69aca31df75d4b4d7a732de5c58556bd3e24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668140"
---
# <a name="implement-ddl-triggers"></a><span data-ttu-id="bc53b-102">Реализация триггеров DDL</span><span class="sxs-lookup"><span data-stu-id="bc53b-102">Implement DDL Triggers</span></span>
  <span data-ttu-id="bc53b-103">В этом разделе приведены сведения, необходимые для создания, изменения, выключения и удаления триггеров DDL.</span><span class="sxs-lookup"><span data-stu-id="bc53b-103">This topic provides information to help you create DDL triggers, modify DDL triggers, and disable or drop DDL triggers.</span></span>  
  
## <a name="creating-ddl-triggers"></a><span data-ttu-id="bc53b-104">Создание триггеров DDL</span><span class="sxs-lookup"><span data-stu-id="bc53b-104">Creating DDL Triggers</span></span>  
 <span data-ttu-id="bc53b-105">Триггеры DDL создаются при помощи инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE TRIGGER для триггеров DDL.</span><span class="sxs-lookup"><span data-stu-id="bc53b-105">DDL triggers are created by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE TRIGGER statement for DDL triggers.</span></span>  
  
 <span data-ttu-id="bc53b-106">**Создание триггера DDL**</span><span class="sxs-lookup"><span data-stu-id="bc53b-106">**To create a DDL trigger**</span></span>  
  
-   [<span data-ttu-id="bc53b-107">CREATE TRIGGER (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="bc53b-107">CREATE TRIGGER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-trigger-transact-sql)  
  
> [!IMPORTANT]  
>  <span data-ttu-id="bc53b-108">Возможность возвращать результирующие наборы из триггеров будет удалена в следующей версии [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc53b-108">The ability to return result sets from triggers will be removed in a future version of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="bc53b-109">Триггеры, возвращающие результирующие наборы, могут привести к непредвиденному поведению приложений, не предназначенных для работы с ними.</span><span class="sxs-lookup"><span data-stu-id="bc53b-109">Triggers that return result sets may cause unexpected behavior in applications that are not designed to work with them.</span></span> <span data-ttu-id="bc53b-110">Не используйте в разрабатываемых приложениях триггеры, возвращающие результирующие наборы, и запланируйте изменение приложений, которые используют их в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="bc53b-110">Avoid returning result sets from triggers in new development work, and plan to modify applications that currently do this.</span></span> <span data-ttu-id="bc53b-111">Чтобы триггеры не возвращали результирующие наборы в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], задайте значение параметра [disallow results from triggers](../../database-engine/configure-windows/disallow-results-from-triggers-server-configuration-option.md) , равное 1.</span><span class="sxs-lookup"><span data-stu-id="bc53b-111">To prevent triggers from returning result sets in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], set the [disallow results from triggers Option](../../database-engine/configure-windows/disallow-results-from-triggers-server-configuration-option.md) to 1.</span></span> <span data-ttu-id="bc53b-112">В будущих версиях [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]для этого параметра по умолчанию будет задаваться значение 1.</span><span class="sxs-lookup"><span data-stu-id="bc53b-112">The default setting of this option will be 1 in a future version of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="modifying-ddl-triggers"></a><span data-ttu-id="bc53b-113">Изменение триггеров DDL</span><span class="sxs-lookup"><span data-stu-id="bc53b-113">Modifying DDL Triggers</span></span>  
 <span data-ttu-id="bc53b-114">Если необходимо изменить определение триггера DDL, можно удалить и вновь создать триггер или переопределить существующий триггер одной инструкцией.</span><span class="sxs-lookup"><span data-stu-id="bc53b-114">If you have to modify the definition of a DDL trigger, you can either drop and re-create the trigger or redefine the existing trigger in a single step.</span></span>  
  
 <span data-ttu-id="bc53b-115">Если изменилось имя объекта, на который ссылается триггер DDL, текст триггера необходимо соответствующим образом изменить.</span><span class="sxs-lookup"><span data-stu-id="bc53b-115">If you change the name of an object that is referenced by a DDL trigger, you must modify the trigger so that its text reflects the new name.</span></span> <span data-ttu-id="bc53b-116">Поэтому перед переименованием объекта вначале выведите зависимости объекта, чтобы определить, не повлияет ли предлагаемое изменение на работу каких-либо триггеров.</span><span class="sxs-lookup"><span data-stu-id="bc53b-116">Therefore, before renaming an object, display the dependencies of the object first to determine whether any triggers are affected by the proposed change.</span></span>  
  
 <span data-ttu-id="bc53b-117">Может быть также зашифровано определение триггера.</span><span class="sxs-lookup"><span data-stu-id="bc53b-117">A trigger can also be modified to encrypt its definition.</span></span>  
  
 <span data-ttu-id="bc53b-118">**Изменение триггера**</span><span class="sxs-lookup"><span data-stu-id="bc53b-118">**To modify a trigger**</span></span>  
  
-   [<span data-ttu-id="bc53b-119">ALTER TRIGGER (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="bc53b-119">ALTER TRIGGER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-trigger-transact-sql)  
  
 <span data-ttu-id="bc53b-120">**Просмотр зависимостей триггера**</span><span class="sxs-lookup"><span data-stu-id="bc53b-120">**To view the dependencies of a trigger**</span></span>  
  
-   [<span data-ttu-id="bc53b-121">sys.sql_expression_dependencies (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="bc53b-121">sys.sql_expression_dependencies &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql)  
  
-   [<span data-ttu-id="bc53b-122">Функция динамического управления sys.dm_sql_referenced_entities (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="bc53b-122">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referenced-entities-transact-sql)  
  
-   [<span data-ttu-id="bc53b-123">sys.dm_sql_referencing_entities (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="bc53b-123">sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referencing-entities-transact-sql)  
  
## <a name="disabling-and-dropping-ddl-triggers"></a><span data-ttu-id="bc53b-124">Отключение и удаление триггеров DDL</span><span class="sxs-lookup"><span data-stu-id="bc53b-124">Disabling and Dropping DDL Triggers</span></span>  
 <span data-ttu-id="bc53b-125">Если триггер DDL больше не нужен, он может быть отключен или удален.</span><span class="sxs-lookup"><span data-stu-id="bc53b-125">When a DDL trigger is no longer needed, you can disable it or delete it.</span></span>  
  
 <span data-ttu-id="bc53b-126">Отключение триггера DDL не приводит к его удалению,</span><span class="sxs-lookup"><span data-stu-id="bc53b-126">Disabling a DDL trigger does not drop it.</span></span> <span data-ttu-id="bc53b-127">Триггер все еще существует как объект в текущей базе данных.</span><span class="sxs-lookup"><span data-stu-id="bc53b-127">The trigger still exists as an object in the current database.</span></span> <span data-ttu-id="bc53b-128">Однако этот триггер не будет срабатывать при выполнении инструкций [!INCLUDE[tsql](../../includes/tsql-md.md)] , на которые он был запрограммирован.</span><span class="sxs-lookup"><span data-stu-id="bc53b-128">However, the trigger will not fire when any [!INCLUDE[tsql](../../includes/tsql-md.md)] statements on which it was programmed are run.</span></span> <span data-ttu-id="bc53b-129">Отключенные триггеры DDL можно повторно включать.</span><span class="sxs-lookup"><span data-stu-id="bc53b-129">DDL triggers that are disabled can be reenabled.</span></span> <span data-ttu-id="bc53b-130">После включения триггер DDL вновь начинает срабатывать так, как это было указано при его создании.</span><span class="sxs-lookup"><span data-stu-id="bc53b-130">Enabling a DDL trigger causes it to fire in the same way the trigger did when it was originally created.</span></span> <span data-ttu-id="bc53b-131">При создании триггеров DDL они включаются по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bc53b-131">When DDL triggers are created, they are enabled by default.</span></span>  
  
 <span data-ttu-id="bc53b-132">При удалении триггера DDL он удаляется из текущей базы данных.</span><span class="sxs-lookup"><span data-stu-id="bc53b-132">When a DDL trigger is deleted, it is dropped from the current database.</span></span> <span data-ttu-id="bc53b-133">Удаление триггера DDL никоим образом не влияет на объекты или данные, на которые распространялась область действия триггера.</span><span class="sxs-lookup"><span data-stu-id="bc53b-133">Any objects or data upon which the DDL trigger is scoped are not affected.</span></span>  
  
 <span data-ttu-id="bc53b-134">**Отключение триггера DDL**</span><span class="sxs-lookup"><span data-stu-id="bc53b-134">**To disable a DDL trigger**</span></span>  
  
-   [<span data-ttu-id="bc53b-135">DISABLE TRIGGER (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="bc53b-135">DISABLE TRIGGER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/disable-trigger-transact-sql)  
  
-   [<span data-ttu-id="bc53b-136">ALTER TABLE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="bc53b-136">ALTER TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-table-transact-sql)  
  
 <span data-ttu-id="bc53b-137">**Включение триггера DDL**</span><span class="sxs-lookup"><span data-stu-id="bc53b-137">**To enable a DDL trigger**</span></span>  
  
-   [<span data-ttu-id="bc53b-138">ENABLE TRIGGER (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="bc53b-138">ENABLE TRIGGER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/enable-trigger-transact-sql)  
  
-   [<span data-ttu-id="bc53b-139">ALTER TABLE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="bc53b-139">ALTER TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-table-transact-sql)  
  
 <span data-ttu-id="bc53b-140">**Удаление триггера DDL**</span><span class="sxs-lookup"><span data-stu-id="bc53b-140">**To delete a DDL trigger**</span></span>  
  
-   [<span data-ttu-id="bc53b-141">DROP TRIGGER (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="bc53b-141">DROP TRIGGER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-trigger-transact-sql)  
  
  
