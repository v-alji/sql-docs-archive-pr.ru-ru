---
title: Удалите ссылки на устаревшие системные хранимые процедуры | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- undocumented system stored procedures [SQL Server]
- system stored procedures [SQL Server]
ms.assetid: 487d24fc-41d5-495e-843c-0ac974ec472f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 65e7da666beaf84050dd8d60caf4cac5bfc013c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735873"
---
# <a name="remove-references-to-deprecated-system-stored-procedures"></a><span data-ttu-id="e9ec0-102">Удаление ссылок на устаревшие системные хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="e9ec0-102">Remove references to deprecated system stored procedures</span></span>
  <span data-ttu-id="e9ec0-103">Советник по переходу обнаружил инструкции, которые ссылаются на недокументированные системные хранимые процедуры и расширенные хранимые процедуры, более не доступные в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9ec0-103">Upgrade Advisor detected statements that reference undocumented system stored procedures and extended stored procedures that are no longer available in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e9ec0-104">Выполнение инструкций, ссылающихся на эти объекты, приведет к ошибке.</span><span class="sxs-lookup"><span data-stu-id="e9ec0-104">Statements that reference these objects will fail.</span></span> <span data-ttu-id="e9ec0-105">Не пользуйтесь недокументированными системными объектами и API-интерфейсами, поскольку их функциональные возможности могут быть изменены или удалены в следующей версии без уведомления.</span><span class="sxs-lookup"><span data-stu-id="e9ec0-105">Do not use undocumented system objects or APIs as the functionality might change or be removed without notification in a future release.</span></span>  
  
## <a name="component"></a><span data-ttu-id="e9ec0-106">Компонент</span><span class="sxs-lookup"><span data-stu-id="e9ec0-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="e9ec0-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e9ec0-107">Description</span></span>  
  
### <a name="documented-system-stored-procedures"></a><span data-ttu-id="e9ec0-108">Документированные системные хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="e9ec0-108">Documented System Stored Procedures</span></span>  
 <span data-ttu-id="e9ec0-109">Были удалены следующие системные хранимые процедуры.</span><span class="sxs-lookup"><span data-stu-id="e9ec0-109">The following documented system stored procedures have been removed:</span></span>  
  
-   <span data-ttu-id="e9ec0-110">sp_addalias</span><span class="sxs-lookup"><span data-stu-id="e9ec0-110">sp_addalias</span></span>  
  
-   <span data-ttu-id="e9ec0-111">sp_addgroup</span><span class="sxs-lookup"><span data-stu-id="e9ec0-111">sp_addgroup</span></span>  
  
-   <span data-ttu-id="e9ec0-112">sp_changegroup</span><span class="sxs-lookup"><span data-stu-id="e9ec0-112">sp_changegroup</span></span>  
  
-   <span data-ttu-id="e9ec0-113">sp_dropgroup</span><span class="sxs-lookup"><span data-stu-id="e9ec0-113">sp_dropgroup</span></span>  
  
-   <span data-ttu-id="e9ec0-114">sp_helpgroup</span><span class="sxs-lookup"><span data-stu-id="e9ec0-114">sp_helpgroup</span></span>  
  
### <a name="undocumented-system-stored-procedures"></a><span data-ttu-id="e9ec0-115">Недокументированные системные хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="e9ec0-115">Undocumented System Stored Procedures</span></span>  
 <span data-ttu-id="e9ec0-116">Следующие недокументированные системные хранимые процедуры и расширенные хранимые процедуры были удалены.</span><span class="sxs-lookup"><span data-stu-id="e9ec0-116">The following undocumented system stored procedures and extended stored procedures have been removed:</span></span>  
  
-   <span data-ttu-id="e9ec0-117">sp_articlesynctranprocs</span><span class="sxs-lookup"><span data-stu-id="e9ec0-117">sp_articlesynctranprocs</span></span>  
  
-   <span data-ttu-id="e9ec0-118">sp_diskdefault</span><span class="sxs-lookup"><span data-stu-id="e9ec0-118">sp_diskdefault</span></span>  
  
-   <span data-ttu-id="e9ec0-119">sp_EventLog</span><span class="sxs-lookup"><span data-stu-id="e9ec0-119">sp_EventLog</span></span>  
  
-   <span data-ttu-id="e9ec0-120">sp_GetMBCSCharLen</span><span class="sxs-lookup"><span data-stu-id="e9ec0-120">sp_GetMBCSCharLen</span></span>  
  
-   <span data-ttu-id="e9ec0-121">sp_helplog</span><span class="sxs-lookup"><span data-stu-id="e9ec0-121">sp_helplog</span></span>  
  
-   <span data-ttu-id="e9ec0-122">sp_helpsql</span><span class="sxs-lookup"><span data-stu-id="e9ec0-122">sp_helpsql</span></span>  
  
-   <span data-ttu-id="e9ec0-123">sp_IsMBCSLeadByte</span><span class="sxs-lookup"><span data-stu-id="e9ec0-123">sp_IsMBCSLeadByte</span></span>  
  
-   <span data-ttu-id="e9ec0-124">sp_lock2</span><span class="sxs-lookup"><span data-stu-id="e9ec0-124">sp_lock2</span></span>  
  
-   <span data-ttu-id="e9ec0-125">sp_MSget_current_activity</span><span class="sxs-lookup"><span data-stu-id="e9ec0-125">sp_MSget_current_activity</span></span>  
  
-   <span data-ttu-id="e9ec0-126">sp_MSset_current_activity</span><span class="sxs-lookup"><span data-stu-id="e9ec0-126">sp_MSset_current_activity</span></span>  
  
-   <span data-ttu-id="e9ec0-127">sp_MSobjessearch</span><span class="sxs-lookup"><span data-stu-id="e9ec0-127">sp_MSobjessearch</span></span>  
  
-   <span data-ttu-id="e9ec0-128">xp_enum_ActiveScriptEngines</span><span class="sxs-lookup"><span data-stu-id="e9ec0-128">xp_enum_ActiveScriptEngines</span></span>  
  
-   <span data-ttu-id="e9ec0-129">xp_eventlog</span><span class="sxs-lookup"><span data-stu-id="e9ec0-129">xp_eventlog</span></span>  
  
-   <span data-ttu-id="e9ec0-130">xp_GetAdminGroupName</span><span class="sxs-lookup"><span data-stu-id="e9ec0-130">xp_GetAdminGroupName</span></span>  
  
-   <span data-ttu-id="e9ec0-131">xp_GetFileDetails</span><span class="sxs-lookup"><span data-stu-id="e9ec0-131">xp_GetFileDetails</span></span>  
  
-   <span data-ttu-id="e9ec0-132">xp_GetLocalSystemAccountName</span><span class="sxs-lookup"><span data-stu-id="e9ec0-132">xp_GetLocalSystemAccountName</span></span>  
  
-   <span data-ttu-id="e9ec0-133">xp_IsNTAdmin</span><span class="sxs-lookup"><span data-stu-id="e9ec0-133">xp_IsNTAdmin</span></span>  
  
-   <span data-ttu-id="e9ec0-134">xp_MSLocalSystem</span><span class="sxs-lookup"><span data-stu-id="e9ec0-134">xp_MSLocalSystem</span></span>  
  
-   <span data-ttu-id="e9ec0-135">xp_MSnt2000</span><span class="sxs-lookup"><span data-stu-id="e9ec0-135">xp_MSnt2000</span></span>  
  
-   <span data-ttu-id="e9ec0-136">xp_MSplatform</span><span class="sxs-lookup"><span data-stu-id="e9ec0-136">xp_MSplatform</span></span>  
  
-   <span data-ttu-id="e9ec0-137">xp_SetSecurity</span><span class="sxs-lookup"><span data-stu-id="e9ec0-137">xp_SetSecurity</span></span>  
  
-   <span data-ttu-id="e9ec0-138">xp_varbintohexstr</span><span class="sxs-lookup"><span data-stu-id="e9ec0-138">xp_varbintohexstr</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="e9ec0-139">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="e9ec0-139">Corrective Action</span></span>  
  
### <a name="documented-system-stored-procedures"></a><span data-ttu-id="e9ec0-140">Документированные системные хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="e9ec0-140">Documented System Stored Procedures</span></span>  
 <span data-ttu-id="e9ec0-141">Измените приложения в соответствии со следующей таблицей.</span><span class="sxs-lookup"><span data-stu-id="e9ec0-141">Modify your applications according to the following table.</span></span>  
  
|<span data-ttu-id="e9ec0-142">Вместо</span><span class="sxs-lookup"><span data-stu-id="e9ec0-142">Instead of</span></span>|<span data-ttu-id="e9ec0-143">выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="e9ec0-143">Do this</span></span>|  
|----------------|-------------|  
|<span data-ttu-id="e9ec0-144">sp_addalias</span><span class="sxs-lookup"><span data-stu-id="e9ec0-144">sp_addalias</span></span>|<span data-ttu-id="e9ec0-145">Псевдонимы заменены сочетанием учетных записей пользователей и ролями базы данных.</span><span class="sxs-lookup"><span data-stu-id="e9ec0-145">Replace aliases with a combination of user accounts and database roles.</span></span> <span data-ttu-id="e9ec0-146">Дополнительные сведения см. в разделах «CREATE USER (Transact-SQL)» и «CREATE ROLE (Transact-SQL)» электронной документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e9ec0-146">For more information, see "CREATE USER (Transact-SQL)" and "CREATE ROLE (Transact-SQL)" in SQL Server Books Online.</span></span> <span data-ttu-id="e9ec0-147">В обновленных базах данных псевдонимы необходимо удалить с помощью процедуры sp_dropalias.</span><span class="sxs-lookup"><span data-stu-id="e9ec0-147">Remove aliases in upgraded databases by using sp_dropalias.</span></span>|  
|<span data-ttu-id="e9ec0-148">sp_addgroupsp_changegroup</span><span class="sxs-lookup"><span data-stu-id="e9ec0-148">sp_addgroupsp_changegroup</span></span><br /><br /> <span data-ttu-id="e9ec0-149">sp_dropgroup</span><span class="sxs-lookup"><span data-stu-id="e9ec0-149">sp_dropgroup</span></span><br /><br /> <span data-ttu-id="e9ec0-150">sp_helpgroup</span><span class="sxs-lookup"><span data-stu-id="e9ec0-150">sp_helpgroup</span></span>|<span data-ttu-id="e9ec0-151">Используйте роли.</span><span class="sxs-lookup"><span data-stu-id="e9ec0-151">Use roles.</span></span> <span data-ttu-id="e9ec0-152">Дополнительные сведения см. в разделах «Роли уровня сервера» и «Роли уровня базы данных» в электронной документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e9ec0-152">For more information, see "Server-Level Roles" and "Database-Level Roles" in SQL Server Books Online.</span></span>|  
  
### <a name="undocmented-system-stored-procedures"></a><span data-ttu-id="e9ec0-153">Недокументированные системные хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="e9ec0-153">Undocmented System Stored Procedures</span></span>  
 <span data-ttu-id="e9ec0-154">Чтобы заменить недокументированные системные хранимые процедуры, можно создать хранимые процедуры CLR с равнозначной функциональностью.</span><span class="sxs-lookup"><span data-stu-id="e9ec0-154">You can create CLR stored procedures with equivalent functionality to replace the undocumented system stored procedures.</span></span> <span data-ttu-id="e9ec0-155">Дополнительные сведения см. в разделе «Хранимые процедуры CLR» электронной документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e9ec0-155">For more information, see the topic "CLR Stored Procedures" in SQL Server Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9ec0-156">См. также:</span><span class="sxs-lookup"><span data-stu-id="e9ec0-156">See Also</span></span>  
 <span data-ttu-id="e9ec0-157">[Проблемы обновления ядро СУБД](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="e9ec0-157">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="e9ec0-158">Советник по переходу SQL Server 2014 &#91;New&#93;</span><span class="sxs-lookup"><span data-stu-id="e9ec0-158">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
