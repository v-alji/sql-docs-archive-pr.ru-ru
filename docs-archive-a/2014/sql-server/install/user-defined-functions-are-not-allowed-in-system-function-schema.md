---
title: В system_function_schema не допускаются определяемые пользователем функции | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- system functions [SQL Server]
- user-defined functions [SQL Server], system
ms.assetid: 3cb54053-ef65-4558-ae96-8686b6b22f4f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 7242f9fda74288a2b7354ac0550ff4966e05c555
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751659"
---
# <a name="user-defined-functions-are-not-allowed-in-system_function_schema"></a><span data-ttu-id="fbc3d-102">В схеме system_function_schema запрещены определяемые пользователем функции</span><span class="sxs-lookup"><span data-stu-id="fbc3d-102">User-defined functions are not allowed in system_function_schema</span></span>
  <span data-ttu-id="fbc3d-103">Советник по переходу обнаружил определяемые пользователем функции, принадлежащие недокументированному пользователю **system_function_schema**.</span><span class="sxs-lookup"><span data-stu-id="fbc3d-103">The Upgrade Advisor detected user-defined functions that are owned by the undocumented user **system_function_schema**.</span></span> <span data-ttu-id="fbc3d-104">Нельзя создать определяемую пользователем системную функцию с указанием пользователя.</span><span class="sxs-lookup"><span data-stu-id="fbc3d-104">You cannot create a user-defined system function by specifying this user.</span></span> <span data-ttu-id="fbc3d-105">Имя пользователя **system_function_schema** не существует, а идентификатор пользователя, связанный с этим именем (UID = 4), зарезервирован для схемы **sys** и ограничен только внутренним использованием.</span><span class="sxs-lookup"><span data-stu-id="fbc3d-105">The **system_function_schema** user name does not exist, and the user ID that is associated with this name (UID = 4) is reserved for the **sys** schema and is restricted to internal use only.</span></span>  
  
## <a name="component"></a><span data-ttu-id="fbc3d-106">Компонент</span><span class="sxs-lookup"><span data-stu-id="fbc3d-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="fbc3d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="fbc3d-107">Description</span></span>  
 <span data-ttu-id="fbc3d-108">Хранение системных объектов и доступ к ним изменились следующим образом.</span><span class="sxs-lookup"><span data-stu-id="fbc3d-108">System object storage and access has changed in the following ways:</span></span>  
  
-   <span data-ttu-id="fbc3d-109">Системные объекты хранятся в базе данных **ресурсов** только для чтения, а прямые обновления системных объектов не допускаются.</span><span class="sxs-lookup"><span data-stu-id="fbc3d-109">System objects are stored in the read-only **Resource** database, and direct system object updates are not permitted.</span></span>  
  
     <span data-ttu-id="fbc3d-110">Системные объекты логически отображаются в схеме **sys** каждой базы данных.</span><span class="sxs-lookup"><span data-stu-id="fbc3d-110">System objects logically appear in the **sys** schema of every database.</span></span> <span data-ttu-id="fbc3d-111">Таким образом обеспечивается возможность вызова системных функций из любой базы данных по однокомпонентному имени функции.</span><span class="sxs-lookup"><span data-stu-id="fbc3d-111">This maintains the ability to invoke system functions from any database by specifying a one-part function name.</span></span> <span data-ttu-id="fbc3d-112">Например, из любой базы данных можно запустить инструкцию `SELECT * FROM fn_helpcollations()`.</span><span class="sxs-lookup"><span data-stu-id="fbc3d-112">For example, the statement `SELECT * FROM fn_helpcollations()` can be run from any database.</span></span>  
  
-   <span data-ttu-id="fbc3d-113">Недокументированный пользователь **system_function_schema** был удален.</span><span class="sxs-lookup"><span data-stu-id="fbc3d-113">The undocumented user **system_function_schema** has been removed.</span></span>  
  
-   <span data-ttu-id="fbc3d-114">Идентификатор пользователя, связанный с **system_function_schema** (UID = 4), зарезервирован для схемы **sys** и ограничен только внутренним использованием.</span><span class="sxs-lookup"><span data-stu-id="fbc3d-114">The user ID associated with **system_function_schema** (UID = 4) is reserved for the **sys** schema and is restricted to internal use only.</span></span>  
  
 <span data-ttu-id="fbc3d-115">Эти изменения влияют на определяемые пользователем системные функции следующим образом.</span><span class="sxs-lookup"><span data-stu-id="fbc3d-115">These changes have the following effect on user-defined system functions:</span></span>  
  
-   <span data-ttu-id="fbc3d-116">Инструкции языка описания данных DDL, которые ссылаются на **system_function_schema** , завершатся ошибкой.</span><span class="sxs-lookup"><span data-stu-id="fbc3d-116">Data Definition Language (DDL) statements that reference **system_function_schema** will fail.</span></span> <span data-ttu-id="fbc3d-117">Например, оператор `CREATE FUNCTION system` _ `function` \_ `schema.fn` \_ `MySystemFunction` ... не будет выполнена.</span><span class="sxs-lookup"><span data-stu-id="fbc3d-117">For example, the statement `CREATE FUNCTION system`_`function`\_`schema.fn`\_`MySystemFunction` ... will not succeed.</span></span>  
  
-   <span data-ttu-id="fbc3d-118">После обновления до [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] существующие объекты, принадлежащие **system_function_schema** , содержатся только в схеме **sys** базы данных **master** .</span><span class="sxs-lookup"><span data-stu-id="fbc3d-118">After you upgrade to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], existing objects that are owned by **system_function_schema** are contained only in the **sys** schema of the **master** database.</span></span> <span data-ttu-id="fbc3d-119">Поскольку системные объекты не могут быть изменены, эти функции не могут быть изменены или удалены из базы данных **master** .</span><span class="sxs-lookup"><span data-stu-id="fbc3d-119">Because system objects cannot be modified, these functions can never be changed or dropped from the **master** database.</span></span> <span data-ttu-id="fbc3d-120">Кроме того, эти функции не могут быть вызваны из других баз данных с помощью только однокомпонентного имени функции.</span><span class="sxs-lookup"><span data-stu-id="fbc3d-120">Additionally, these functions cannot be invoked from other databases by specifying only a one-part function name.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="fbc3d-121">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="fbc3d-121">Corrective Action</span></span>  
 <span data-ttu-id="fbc3d-122">Перед началом обновления выполните следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="fbc3d-122">Before you upgrade , complete the following tasks:</span></span>  
  
1.  <span data-ttu-id="fbc3d-123">Измените принадлежность существующих определяемых пользователем функций на **dbo** с помощью системной хранимой процедуры **sp_changeobjectowner** .</span><span class="sxs-lookup"><span data-stu-id="fbc3d-123">Change the ownership of existing user-defined functions to **dbo** by using the **sp_changeobjectowner** system stored procedure.</span></span>  
  
2.  <span data-ttu-id="fbc3d-124">Рассмотрите возможность переименования функции, чтобы в имени не использовался префикс «fn_».</span><span class="sxs-lookup"><span data-stu-id="fbc3d-124">Consider renaming the function so that is does not use the prefix 'fn_'.</span></span> <span data-ttu-id="fbc3d-125">Это поможет избежать потенциальных конфликтов имен с существующими и будущими системными функциями.</span><span class="sxs-lookup"><span data-stu-id="fbc3d-125">This will avoid potential name conflicts with current or future system functions.</span></span>  
  
3.  <span data-ttu-id="fbc3d-126">Добавьте копии измененных функций во все базы данных, которые их используют.</span><span class="sxs-lookup"><span data-stu-id="fbc3d-126">Add a copy of the modified functions in every database that uses them.</span></span>  
  
4.  <span data-ttu-id="fbc3d-127">Замените ссылки на **system_function_schema** с **dbo** во всех скриптах, содержащих инструкции DDL определяемой пользователем функции.</span><span class="sxs-lookup"><span data-stu-id="fbc3d-127">Replace references to **system_function_schema** with **dbo** in all scripts that contain user-defined function DDL statements.</span></span>  
  
5.  <span data-ttu-id="fbc3d-128">Измените скрипты, которые вызывают эти функции, чтобы использовать имя dbo из двух частей **.** _function_name_или имя из трех частей _database_name_**.** dbo. *function_name*.</span><span class="sxs-lookup"><span data-stu-id="fbc3d-128">Modify scripts that invoke these functions to use either the two-part name dbo **.**_function_name_, or the three-part name _database_name_**.** dbo.*function_name*.</span></span>  
  
 <span data-ttu-id="fbc3d-129">Дополнительные сведения см. в следующих разделах электронной документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fbc3d-129">For more information, see the following topics in SQL Server Books Online:</span></span>  
  
-   <span data-ttu-id="fbc3d-130">sp_changeobjectowner</span><span class="sxs-lookup"><span data-stu-id="fbc3d-130">"sp_changeobjectowner"</span></span>  
  
-   <span data-ttu-id="fbc3d-131">Отделение пользователей от схем</span><span class="sxs-lookup"><span data-stu-id="fbc3d-131">"User-schema Separation"</span></span>  
  
-   <span data-ttu-id="fbc3d-132">База данных Resource</span><span class="sxs-lookup"><span data-stu-id="fbc3d-132">"Resource Database"</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbc3d-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="fbc3d-133">See Also</span></span>  
 <span data-ttu-id="fbc3d-134">[Советник по переходу SQL Server 2014 &#91;New&#93;](sql-server-2014-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="fbc3d-134">[SQL Server 2014 Upgrade Advisor &#91;new&#93;](sql-server-2014-upgrade-advisor.md) </span></span>  
 <span data-ttu-id="fbc3d-135">[Проблемы обновления ядро СУБД](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="fbc3d-135">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 <span data-ttu-id="fbc3d-136">[Удалите инструкции, изменяющие системные объекты](../../../2014/sql-server/install/remove-statements-that-modify-system-objects.md) </span><span class="sxs-lookup"><span data-stu-id="fbc3d-136">[Remove statements that modify system objects](../../../2014/sql-server/install/remove-statements-that-modify-system-objects.md) </span></span>  
 [<span data-ttu-id="fbc3d-137">Удалите инструкции, которые удаляют системные объекты</span><span class="sxs-lookup"><span data-stu-id="fbc3d-137">Remove statements that drop system objects</span></span>](../../../2014/sql-server/install/remove-statements-that-drop-system-objects.md)  
  
  
