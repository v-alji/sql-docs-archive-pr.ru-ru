---
title: Защищаемые объекты | Документация Майкрософт
ms.custom: ''
ms.date: 10/14/2015
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.roleproperties.selectobject.f1
helpviewer_keywords:
- securables [SQL Server]
- schemas [SQL Server], securables
- database securables [SQL Server]
- hierarchies [SQL Server], securables
- server securables [SQL Server]
ms.assetid: bfa748f0-70b0-453c-870a-04b7b205b9ff
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: ff2aaba72e2e5489694d31b35e594622c099acab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730338"
---
# <a name="securables"></a><span data-ttu-id="b9d9a-102">Защищаемые объекты</span><span class="sxs-lookup"><span data-stu-id="b9d9a-102">Securables</span></span>
  <span data-ttu-id="b9d9a-103">К защищаемым объектами относятся ресурсы, доступ к которым регулируется системой авторизации компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b9d9a-103">Securables are the resources to which the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] authorization system regulates access.</span></span> <span data-ttu-id="b9d9a-104">Например, защищаемым объектом является таблица.</span><span class="sxs-lookup"><span data-stu-id="b9d9a-104">For example, a table is a securable.</span></span> <span data-ttu-id="b9d9a-105">Некоторые защищаемые объекты могут храниться внутри других, создавая иерархии «областей», которые сами могут защищаться.</span><span class="sxs-lookup"><span data-stu-id="b9d9a-105">Some securables can be contained within others, creating nested hierarchies called "scopes" that can themselves be secured.</span></span> <span data-ttu-id="b9d9a-106">К областям защищаемых объектов относятся **сервер**, **база данных**и **схема**.</span><span class="sxs-lookup"><span data-stu-id="b9d9a-106">The securable scopes are **server**, **database**, and **schema**.</span></span>  
  
## <a name="securable-scope-server"></a><span data-ttu-id="b9d9a-107">Область защищаемых объектов: Сервер</span><span class="sxs-lookup"><span data-stu-id="b9d9a-107">Securable scope: Server</span></span>  
 <span data-ttu-id="b9d9a-108">Область защищаемых объектов **сервера** содержит следующие защищаемые объекты:</span><span class="sxs-lookup"><span data-stu-id="b9d9a-108">The **server** securable scope contains the following securables:</span></span>  
  
-   <span data-ttu-id="b9d9a-109">группа доступности</span><span class="sxs-lookup"><span data-stu-id="b9d9a-109">Availability group</span></span>  
  
-   <span data-ttu-id="b9d9a-110">Конечная точка</span><span class="sxs-lookup"><span data-stu-id="b9d9a-110">Endpoint</span></span>  
  
-   <span data-ttu-id="b9d9a-111">Имя входа</span><span class="sxs-lookup"><span data-stu-id="b9d9a-111">Login</span></span>  
  
-   <span data-ttu-id="b9d9a-112">Роль сервера</span><span class="sxs-lookup"><span data-stu-id="b9d9a-112">Server role</span></span>  
  
-   <span data-ttu-id="b9d9a-113">База данных</span><span class="sxs-lookup"><span data-stu-id="b9d9a-113">Database</span></span>  
  
## <a name="securable-scope-database"></a><span data-ttu-id="b9d9a-114">Область защищаемых объектов: База данных</span><span class="sxs-lookup"><span data-stu-id="b9d9a-114">Securable scope: Database</span></span>  
 <span data-ttu-id="b9d9a-115">Область защищаемых объектов **базы данных** содержит следующие защищаемые объекты:</span><span class="sxs-lookup"><span data-stu-id="b9d9a-115">The **database** securable scope contains the following securables:</span></span>  
  
-   <span data-ttu-id="b9d9a-116">Роль приложения</span><span class="sxs-lookup"><span data-stu-id="b9d9a-116">Application role</span></span>  
  
-   <span data-ttu-id="b9d9a-117">Сборка</span><span class="sxs-lookup"><span data-stu-id="b9d9a-117">Assembly</span></span>  
  
-   <span data-ttu-id="b9d9a-118">Асимметричный ключ</span><span class="sxs-lookup"><span data-stu-id="b9d9a-118">Asymmetric key</span></span>  
  
-   <span data-ttu-id="b9d9a-119">Сертификат</span><span class="sxs-lookup"><span data-stu-id="b9d9a-119">Certificate</span></span>  
  
-   <span data-ttu-id="b9d9a-120">Контракт</span><span class="sxs-lookup"><span data-stu-id="b9d9a-120">Contract</span></span>  
  
-   <span data-ttu-id="b9d9a-121">Полнотекстовый каталог</span><span class="sxs-lookup"><span data-stu-id="b9d9a-121">Fulltext catalog</span></span>  
  
-   <span data-ttu-id="b9d9a-122">Полнотекстовый список стоп-слов</span><span class="sxs-lookup"><span data-stu-id="b9d9a-122">Fulltext stoplist</span></span>  
  
-   <span data-ttu-id="b9d9a-123">тип сообщений;</span><span class="sxs-lookup"><span data-stu-id="b9d9a-123">Message type</span></span>  
  
-   <span data-ttu-id="b9d9a-124">Привязка удаленной службы</span><span class="sxs-lookup"><span data-stu-id="b9d9a-124">Remote Service Binding</span></span>  
  
-   <span data-ttu-id="b9d9a-125">Роль (база данных)</span><span class="sxs-lookup"><span data-stu-id="b9d9a-125">(Database) Role</span></span>  
  
-   <span data-ttu-id="b9d9a-126">Маршрут</span><span class="sxs-lookup"><span data-stu-id="b9d9a-126">Route</span></span>  
  
-   <span data-ttu-id="b9d9a-127">схема</span><span class="sxs-lookup"><span data-stu-id="b9d9a-127">Schema</span></span>  
  
-   <span data-ttu-id="b9d9a-128">Поиск в списке свойств</span><span class="sxs-lookup"><span data-stu-id="b9d9a-128">Search property list</span></span>  
  
-   <span data-ttu-id="b9d9a-129">Служба</span><span class="sxs-lookup"><span data-stu-id="b9d9a-129">Service</span></span>  
  
-   <span data-ttu-id="b9d9a-130">Симметричный ключ</span><span class="sxs-lookup"><span data-stu-id="b9d9a-130">Symmetric key</span></span>  
  
-   <span data-ttu-id="b9d9a-131">Пользователь</span><span class="sxs-lookup"><span data-stu-id="b9d9a-131">User</span></span>  
  
## <a name="securable-scope-schema"></a><span data-ttu-id="b9d9a-132">Область защищаемых объектов: схема</span><span class="sxs-lookup"><span data-stu-id="b9d9a-132">Securable scope: Schema</span></span>  
 <span data-ttu-id="b9d9a-133">Область защищаемых объектов **схемы** содержит следующие защищаемые объекты:</span><span class="sxs-lookup"><span data-stu-id="b9d9a-133">The **schema** securable scope contains the following securables:</span></span>  
  
-   <span data-ttu-id="b9d9a-134">Тип</span><span class="sxs-lookup"><span data-stu-id="b9d9a-134">Type</span></span>  
  
-   <span data-ttu-id="b9d9a-135">Коллекция схем XML</span><span class="sxs-lookup"><span data-stu-id="b9d9a-135">XML schema collection</span></span>  
  
-   <span data-ttu-id="b9d9a-136">Объект — к классу объекта относятся следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="b9d9a-136">Object - The object class has the following members:</span></span>  
  
    -   <span data-ttu-id="b9d9a-137">Статистическое</span><span class="sxs-lookup"><span data-stu-id="b9d9a-137">Aggregate</span></span>  
  
    -   <span data-ttu-id="b9d9a-138">Компонент</span><span class="sxs-lookup"><span data-stu-id="b9d9a-138">Function</span></span>  
  
    -   <span data-ttu-id="b9d9a-139">Процедура</span><span class="sxs-lookup"><span data-stu-id="b9d9a-139">Procedure</span></span>  
  
    -   <span data-ttu-id="b9d9a-140">Очередь</span><span class="sxs-lookup"><span data-stu-id="b9d9a-140">Queue</span></span>  
  
    -   <span data-ttu-id="b9d9a-141">Синоним</span><span class="sxs-lookup"><span data-stu-id="b9d9a-141">Synonym</span></span>  
  
    -   <span data-ttu-id="b9d9a-142">Таблица</span><span class="sxs-lookup"><span data-stu-id="b9d9a-142">Table</span></span>  
  
    -   <span data-ttu-id="b9d9a-143">Представление</span><span class="sxs-lookup"><span data-stu-id="b9d9a-143">View</span></span>  
  
## <a name="controlling-access-to-a-securable"></a><span data-ttu-id="b9d9a-144">Управление доступом к защищаемому объекту</span><span class="sxs-lookup"><span data-stu-id="b9d9a-144">Controlling Access to a Securable</span></span>  
 <span data-ttu-id="b9d9a-145">Сущность, которая получает разрешение на доступ к защищаемому объекту, именуется участником.</span><span class="sxs-lookup"><span data-stu-id="b9d9a-145">The entity that receives permission to a securable is called a principal.</span></span> <span data-ttu-id="b9d9a-146">Наиболее часто в роли участников выступают имена входа и пользователи базы данных.</span><span class="sxs-lookup"><span data-stu-id="b9d9a-146">The most common principals are logins and database users.</span></span> <span data-ttu-id="b9d9a-147">Управление доступом к защищаемым объектам осуществляется путем предоставления или отзыва разрешений либо путем добавления имен входа и пользователей к ролям, имеющим доступ.</span><span class="sxs-lookup"><span data-stu-id="b9d9a-147">Access to securables is controlled by granting or denying permissions, or by adding logins and user to roles which have access.</span></span> <span data-ttu-id="b9d9a-148">Сведения об управлении разрешениями см. в разделах [GRANT (Transact-SQL)](/sql/t-sql/statements/grant-transact-sql), [REVOKE (Transact-SQL)](/sql/t-sql/statements/revoke-transact-sql), [DENY (Transact-SQL)](/sql/t-sql/statements/deny-transact-sql), [Хранимая процедура sp_addrolemember (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-addrolemember-transact-sql) и [sp_droprolemember (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-droprolemember-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b9d9a-148">For information about controlling permissions, see [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql), [REVOKE &#40;Transact-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql), [DENY &#40;Transact-SQL&#41;](/sql/t-sql/statements/deny-transact-sql), [sp_addrolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addrolemember-transact-sql), and [sp_droprolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-droprolemember-transact-sql).</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="b9d9a-149">Разрешения по умолчанию, которые предоставляются системным объектам во время установки, тщательно оцениваются на предмет возможных угроз, и их не нужно будет изменять для защиты установки [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b9d9a-149">The default permissions that are granted to system objects at the time of setup are carefully evaluated against possible threats and need not be altered as part of hardening the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] installation.</span></span> <span data-ttu-id="b9d9a-150">Любые изменения разрешений в системных объектах могут ограничить или нарушить функциональность, а также перевести установку [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] в неподдерживаемое состояние.</span><span class="sxs-lookup"><span data-stu-id="b9d9a-150">Any changes to the permissions on the system objects could limit or break the functionality and could potentially leave your [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] installation in an unsupported state.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="b9d9a-151">См. также</span><span class="sxs-lookup"><span data-stu-id="b9d9a-151">Related Content</span></span>  
 [<span data-ttu-id="b9d9a-152">Обеспечение безопасности SQL Server</span><span class="sxs-lookup"><span data-stu-id="b9d9a-152">Securing SQL Server</span></span>](securing-sql-server.md)  
  
 [<span data-ttu-id="b9d9a-153">sys.database_principals (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="b9d9a-153">sys.database_principals &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-principals-transact-sql)  
  
 [<span data-ttu-id="b9d9a-154">sys.database_role_members (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="b9d9a-154">sys.database_role_members &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-role-members-transact-sql)  
  
 [<span data-ttu-id="b9d9a-155">sys.server_principals (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="b9d9a-155">sys.server_principals &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-principals-transact-sql)  
  
 [<span data-ttu-id="b9d9a-156">sys.server_role_members (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="b9d9a-156">sys.server_role_members &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-role-members-transact-sql)  
  
 [<span data-ttu-id="b9d9a-157">sys.sql_logins (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="b9d9a-157">sys.sql_logins &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-sql-logins-transact-sql)  
  
  
