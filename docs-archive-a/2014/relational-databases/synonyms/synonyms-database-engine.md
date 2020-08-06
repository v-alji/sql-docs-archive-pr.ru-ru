---
title: Синонимы (ядро СУБД) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: t-sql
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- synonyms [SQL Server], about synonyms
ms.assetid: 6210e1d5-075f-47e4-ac8d-f84bcf26fbc0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3494f4f5b13c422efb8e2a39597e131c10d81ed1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664096"
---
# <a name="synonyms-database-engine"></a><span data-ttu-id="10908-102">Синонимы (компонент Database Engine)</span><span class="sxs-lookup"><span data-stu-id="10908-102">Synonyms (Database Engine)</span></span>
  <span data-ttu-id="10908-103">Синонимом является объект базы данных, который выполняет следующие функции:</span><span class="sxs-lookup"><span data-stu-id="10908-103">A synonym is a database object that serves the following purposes:</span></span>  
  
-   <span data-ttu-id="10908-104">предоставляет альтернативное имя для другого объекта базы данных, существующего на локальном или удаленном сервере, на которое затем ссылаются как на базовый объект;</span><span class="sxs-lookup"><span data-stu-id="10908-104">Provides an alternative name for another database object, referred to as the base object, that can exist on a local or remote server.</span></span>  
  
-   <span data-ttu-id="10908-105">обеспечивает уровень абстракции, защищающий клиентские приложения от изменений, производимых в имени или местоположении базовых объектов.</span><span class="sxs-lookup"><span data-stu-id="10908-105">Provides a layer of abstraction that protects a client application from changes made to the name or location of the base object.</span></span>  
  
 <span data-ttu-id="10908-106">Например, рассмотрим таблицу **Employee** образца базы данных [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)], расположенную на сервере **Server1**.</span><span class="sxs-lookup"><span data-stu-id="10908-106">For example, consider the **Employee** table of [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)], located on a server named **Server1**.</span></span> <span data-ttu-id="10908-107">Для доступа к этой таблице сервера **Server2**клиентское приложение должно указать имя из четырех компонентов: **Server1.AdventureWorks.Person.Employee**.</span><span class="sxs-lookup"><span data-stu-id="10908-107">To reference this table from another server, **Server2**, a client application would have to use the four-part name **Server1.AdventureWorks.Person.Employee**.</span></span> <span data-ttu-id="10908-108">Если бы таблицу нужно было переместить, например, на другой сервер, клиентское приложение также надо было бы модифицировать, чтобы отобразить ее новое местоположение.</span><span class="sxs-lookup"><span data-stu-id="10908-108">Also, if the location of the table were to change, for example, to another server, the client application would have to be modified to reflect that change.</span></span>  
  
 <span data-ttu-id="10908-109">Для решения обеих этих проблем на сервере **Server2**можно создать синоним — **EmpTable** —для таблицы **Employee** , расположенной на **Server1**.</span><span class="sxs-lookup"><span data-stu-id="10908-109">To address both these issues, you can create a synonym, **EmpTable**, on **Server2** for the **Employee** table on **Server1**.</span></span> <span data-ttu-id="10908-110">Теперь клиентскому приложению необходимо указывать имя таблицы, состоящее всего из одного элемента **EmpTable**, для обращения к таблице **Employee** .</span><span class="sxs-lookup"><span data-stu-id="10908-110">Now, the client application only has to use the single-part name, **EmpTable**, to reference the **Employee** table.</span></span> <span data-ttu-id="10908-111">Кроме того, если местоположение таблицы **Employee** будет изменено, нужно будет только изменить синоним **EmpTable**, чтобы он указывал на новое местоположение таблицы **Employee** .</span><span class="sxs-lookup"><span data-stu-id="10908-111">Also, if the location of the **Employee** table changes, you will have to modify the synonym, **EmpTable**, to point to the new location of the **Employee** table.</span></span> <span data-ttu-id="10908-112">Так как инструкции ALTER SYNONYM не существует, для этого сначала удаляют синоним **EmpTable**, а затем повторно создают его с тем же именем, указывая новое местоположение таблицы **Employee**.</span><span class="sxs-lookup"><span data-stu-id="10908-112">Because there is no ALTER SYNONYM statement, you first have to drop the synonym, **EmpTable**, and then re-create the synonym with the same name, but point the synonym to the new location of **Employee**.</span></span>  
  
 <span data-ttu-id="10908-113">Синоним принадлежит схеме, и, как и для всех остальных объектов схемы, имя синонима должно быть уникальным в ее пределах.</span><span class="sxs-lookup"><span data-stu-id="10908-113">A synonym belongs to a schema, and like other objects in a schema, the name of a synonym must be unique.</span></span> <span data-ttu-id="10908-114">Синонимы могут быть созданы для следующих объектов базы данных.</span><span class="sxs-lookup"><span data-stu-id="10908-114">You can create synonyms for the following database objects:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="10908-115">Хранимая процедура сборки (среда CLR)</span><span class="sxs-lookup"><span data-stu-id="10908-115">Assembly (CLR) stored procedure</span></span>|<span data-ttu-id="10908-116">Возвращающая табличное значение функция сборки (среда CLR)</span><span class="sxs-lookup"><span data-stu-id="10908-116">Assembly (CLR) table-valued function</span></span>|  
|<span data-ttu-id="10908-117">Скалярная функция сборки (среда CLR)</span><span class="sxs-lookup"><span data-stu-id="10908-117">Assembly (CLR) scalar function</span></span>|<span data-ttu-id="10908-118">Агрегатная функция сборки (среда CLR)</span><span class="sxs-lookup"><span data-stu-id="10908-118">Assembly (CLR) aggregate functions</span></span>|  
|<span data-ttu-id="10908-119">Процедура фильтра репликации</span><span class="sxs-lookup"><span data-stu-id="10908-119">Replication-filter-procedure</span></span>|<span data-ttu-id="10908-120">Расширенная хранимая процедура</span><span class="sxs-lookup"><span data-stu-id="10908-120">Extended stored procedure</span></span>|  
|<span data-ttu-id="10908-121">Скалярная функция SQL</span><span class="sxs-lookup"><span data-stu-id="10908-121">SQL scalar function</span></span>|<span data-ttu-id="10908-122">Возвращающая табличное значение функция SQL</span><span class="sxs-lookup"><span data-stu-id="10908-122">SQL table-valued function</span></span>|  
|<span data-ttu-id="10908-123">Возвращающая табличное значение встроенная функция SQL</span><span class="sxs-lookup"><span data-stu-id="10908-123">SQL inline-tabled-valued function</span></span>|<span data-ttu-id="10908-124">Хранимая процедура SQL</span><span class="sxs-lookup"><span data-stu-id="10908-124">SQL stored procedure</span></span>|  
|<span data-ttu-id="10908-125">Просмотр</span><span class="sxs-lookup"><span data-stu-id="10908-125">View</span></span>|<span data-ttu-id="10908-126">Таблица<sup>1</sup> (пользовательская)</span><span class="sxs-lookup"><span data-stu-id="10908-126">Table<sup>1</sup> (User-defined)</span></span>|  
  
 <span data-ttu-id="10908-127"><sup>1</sup> включает локальные и глобальные временные таблицы;</span><span class="sxs-lookup"><span data-stu-id="10908-127"><sup>1</sup> Includes local and global temporary tables</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="10908-128">Имена, состоящие из четырех элементов, для базовых объектов-функций не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="10908-128">Four-part names for function base objects are not supported.</span></span>  
  
 <span data-ttu-id="10908-129">Синоним не может быть базовым объектом для другого синонима, а также не может ссылаться на определяемую пользователем агрегатную функцию.</span><span class="sxs-lookup"><span data-stu-id="10908-129">A synonym cannot be the base object for another synonym, and a synonym cannot reference a user-defined aggregate function.</span></span>  
  
 <span data-ttu-id="10908-130">Синоним связан с его базовым объектом только по имени.</span><span class="sxs-lookup"><span data-stu-id="10908-130">The binding between a synonym and its base object is by name only.</span></span> <span data-ttu-id="10908-131">Любые проверки на существование, тип и разрешения для базового объекта откладываются до стадии выполнения.</span><span class="sxs-lookup"><span data-stu-id="10908-131">All existence, type, and permissions checking on the base object is deferred until run time.</span></span> <span data-ttu-id="10908-132">Таким образом, базовый объект может быть изменен, удален или заменен другим объектом, имеющим то же имя, что и исходный.</span><span class="sxs-lookup"><span data-stu-id="10908-132">Therefore, the base object can be modified, dropped, or dropped and replaced by another object that has the same name as the original base object.</span></span> <span data-ttu-id="10908-133">Например, предположим, что синоним **MyContacts**ссылается на таблицу **Person.Contact** в базе данных [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="10908-133">For example, consider a synonym, **MyContacts**, that references the **Person.Contact** table in [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)].</span></span> <span data-ttu-id="10908-134">Если таблица **Contact** удаляется и заменяется представлением с именем **Person.Contact**, синоним **MyContacts** будет указывать на представление **Person.Contact** .</span><span class="sxs-lookup"><span data-stu-id="10908-134">If the **Contact** table is dropped and replaced by a view named **Person.Contact**, **MyContacts** now references the **Person.Contact** view.</span></span>  
  
 <span data-ttu-id="10908-135">Ссылки на синонимы не привязаны к схеме.</span><span class="sxs-lookup"><span data-stu-id="10908-135">References to synonyms are not schema-bound.</span></span> <span data-ttu-id="10908-136">Таким образом, синоним может быть удален в любой момент.</span><span class="sxs-lookup"><span data-stu-id="10908-136">Therefore, a synonym can be dropped at any time.</span></span> <span data-ttu-id="10908-137">Однако удаление синонима может оказаться чревато тем, что останутся несвязанные ссылки на него,</span><span class="sxs-lookup"><span data-stu-id="10908-137">However, by dropping a synonym, you run the risk of leaving dangling references to the synonym that was dropped.</span></span> <span data-ttu-id="10908-138">что проявится только на стадии выполнения.</span><span class="sxs-lookup"><span data-stu-id="10908-138">These references will only be found at run time.</span></span>  
  
## <a name="synonyms-and-schemas"></a><span data-ttu-id="10908-139">Синонимы и схемы</span><span class="sxs-lookup"><span data-stu-id="10908-139">Synonyms and Schemas</span></span>  
 <span data-ttu-id="10908-140">Если пользователь создает синоним в схеме, владельцем которой он не является, имя синонима необходимо предварять именем схемы, владельцем которой является пользователь.</span><span class="sxs-lookup"><span data-stu-id="10908-140">If you have a default schema that you do not own and want to create a synonym, you must qualify the synonym name with the name of a schema that you do own.</span></span> <span data-ttu-id="10908-141">Например, если пользователь владеет схемой **x**, но текущей схемой является **y** , то при выполнении инструкции CREATE SYNONYM имя синонима необходимо предварять схемой **x**, а не указывать его по имени, состоящему из одного элемента.</span><span class="sxs-lookup"><span data-stu-id="10908-141">For example, if you own a schema **x**, but **y** is your default schema and you use the CREATE SYNONYM statement, you must prefix the name of the synonym with the schema **x**, instead of naming the synonym by using a single-part name.</span></span> <span data-ttu-id="10908-142">Дополнительные сведения о том, как создавать синонимы, см. в разделе [CREATE SYNONYM (Transact-SQL)](/sql/t-sql/statements/create-synonym-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="10908-142">For more information about how to create synonyms, see [CREATE SYNONYM &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-synonym-transact-sql).</span></span>  
  
## <a name="granting-permissions-on-a-synonym"></a><span data-ttu-id="10908-143">Предоставление разрешений на синоним</span><span class="sxs-lookup"><span data-stu-id="10908-143">Granting Permissions on a Synonym</span></span>  
 <span data-ttu-id="10908-144">Только владельцы синонима или члены ролей **db_owner**и **db_ddladmin** могут предоставлять разрешения на синоним.</span><span class="sxs-lookup"><span data-stu-id="10908-144">Only synonym owners, members of **db_owner**, or members of **db_ddladmin** can grant permission on a synonym.</span></span>  
  
 <span data-ttu-id="10908-145">Для синонима можно предоставить, запретить или отменить все или любые разрешения из нижеперечисленных:</span><span class="sxs-lookup"><span data-stu-id="10908-145">You can GRANT, DENY, REVOKE all or any of the following permissions on a synonym:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="10908-146">CONTROL</span><span class="sxs-lookup"><span data-stu-id="10908-146">CONTROL</span></span>|<span data-ttu-id="10908-147">DELETE</span><span class="sxs-lookup"><span data-stu-id="10908-147">DELETE</span></span>|  
|<span data-ttu-id="10908-148">EXECUTE</span><span class="sxs-lookup"><span data-stu-id="10908-148">EXECUTE</span></span>|<span data-ttu-id="10908-149">INSERT</span><span class="sxs-lookup"><span data-stu-id="10908-149">INSERT</span></span>|  
|<span data-ttu-id="10908-150">SELECT</span><span class="sxs-lookup"><span data-stu-id="10908-150">SELECT</span></span>|<span data-ttu-id="10908-151">TAKE OWNERSHIP</span><span class="sxs-lookup"><span data-stu-id="10908-151">TAKE OWNERSHIP</span></span>|  
|<span data-ttu-id="10908-152">UPDATE</span><span class="sxs-lookup"><span data-stu-id="10908-152">UPDATE</span></span>|<span data-ttu-id="10908-153">VIEW DEFINITION</span><span class="sxs-lookup"><span data-stu-id="10908-153">VIEW DEFINITION</span></span>|  
  
## <a name="using-synonyms"></a><span data-ttu-id="10908-154">Использование синонимов</span><span class="sxs-lookup"><span data-stu-id="10908-154">Using Synonyms</span></span>  
 <span data-ttu-id="10908-155">Можно использовать синонимы вместо их базового объекта, на который они ссылаются, в нескольких инструкциях SQL и контекстах выражения.</span><span class="sxs-lookup"><span data-stu-id="10908-155">You can use synonyms in place of their referenced base object in several SQL statements and expression contexts.</span></span> <span data-ttu-id="10908-156">Следующая таблица содержит список этих инструкций и контекстов выражения.</span><span class="sxs-lookup"><span data-stu-id="10908-156">The following table contains a list of these statements and expression contexts:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="10908-157">SELECT</span><span class="sxs-lookup"><span data-stu-id="10908-157">SELECT</span></span>|<span data-ttu-id="10908-158">INSERT</span><span class="sxs-lookup"><span data-stu-id="10908-158">INSERT</span></span>|  
|<span data-ttu-id="10908-159">UPDATE</span><span class="sxs-lookup"><span data-stu-id="10908-159">UPDATE</span></span>|<span data-ttu-id="10908-160">DELETE</span><span class="sxs-lookup"><span data-stu-id="10908-160">DELETE</span></span>|  
|<span data-ttu-id="10908-161">EXECUTE</span><span class="sxs-lookup"><span data-stu-id="10908-161">EXECUTE</span></span>|<span data-ttu-id="10908-162">Подзапросы выборки</span><span class="sxs-lookup"><span data-stu-id="10908-162">Sub-selects</span></span>|  
  
 <span data-ttu-id="10908-163">При работе с синонимами в сформулированных ранее контекстах будет затронут базовый объект.</span><span class="sxs-lookup"><span data-stu-id="10908-163">When you are working with synonyms in the contexts previously stated, the base object is affected.</span></span> <span data-ttu-id="10908-164">Например, если синоним ссылается на базовый объект, который является таблицей, и строка вставляется в синоним, то фактически строка вставляется в таблицу, на которую ссылается синоним.</span><span class="sxs-lookup"><span data-stu-id="10908-164">For example, if a synonym references a base object that is a table and you insert a row into the synonym, you are actually inserting a row into the referenced table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="10908-165">Нельзя сослаться на синоним, который расположен на связанном сервере.</span><span class="sxs-lookup"><span data-stu-id="10908-165">You cannot reference a synonym that is located on a linked server.</span></span>  
  
 <span data-ttu-id="10908-166">Синоним можно использовать в качестве параметра функции OBJECT_ID; однако эта функция вернет идентификатор объекта для синонима, а не для базового объекта.</span><span class="sxs-lookup"><span data-stu-id="10908-166">You can use a synonym as the parameter for the OBJECT_ID function; however, the function returns the object ID of the synonym, not the base object.</span></span>  
  
 <span data-ttu-id="10908-167">Нельзя ссылаться на синоним в инструкции DDL.</span><span class="sxs-lookup"><span data-stu-id="10908-167">You cannot reference a synonym in a DDL statement.</span></span> <span data-ttu-id="10908-168">Например, следующие инструкции, ссылающиеся на синоним `dbo.MyProduct`, приведут к ошибке.</span><span class="sxs-lookup"><span data-stu-id="10908-168">For example, the following statements, which reference a synonym named `dbo.MyProduct`, generate errors:</span></span>  
  
```  
ALTER TABLE dbo.MyProduct  
   ADD NewFlag int null;  
EXEC ('ALTER TABLE dbo.MyProduct  
   ADD NewFlag int null');  
```  
  
 <span data-ttu-id="10908-169">Следующие инструкции разрешений связаны только с синонимом, а не с базовым объектом.</span><span class="sxs-lookup"><span data-stu-id="10908-169">The following permission statements are associated only with the synonym and not the base object:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="10908-170">GRANT</span><span class="sxs-lookup"><span data-stu-id="10908-170">GRANT</span></span>|<span data-ttu-id="10908-171">DENY</span><span class="sxs-lookup"><span data-stu-id="10908-171">DENY</span></span>|  
|<span data-ttu-id="10908-172">REVOKE</span><span class="sxs-lookup"><span data-stu-id="10908-172">REVOKE</span></span>||  
  
 <span data-ttu-id="10908-173">Синонимы не привязаны к схеме, и поэтому на них нельзя сослаться следующими привязанными к схеме контекстами выражения.</span><span class="sxs-lookup"><span data-stu-id="10908-173">Synonyms are not schema-bound and, therefore, cannot be referenced by the following schema-bound expression contexts:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="10908-174">CHECK, ограничение</span><span class="sxs-lookup"><span data-stu-id="10908-174">CHECK constraints</span></span>|<span data-ttu-id="10908-175">Вычисляемые столбцы</span><span class="sxs-lookup"><span data-stu-id="10908-175">Computed columns</span></span>|  
|<span data-ttu-id="10908-176">Выражения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="10908-176">Default expressions</span></span>|<span data-ttu-id="10908-177">Выражения правил</span><span class="sxs-lookup"><span data-stu-id="10908-177">Rule expressions</span></span>|  
|<span data-ttu-id="10908-178">Привязанные к схеме представления</span><span class="sxs-lookup"><span data-stu-id="10908-178">Schema-bound views</span></span>|<span data-ttu-id="10908-179">Привязанные к схеме функции</span><span class="sxs-lookup"><span data-stu-id="10908-179">Schema-bound functions</span></span>|  
  
 <span data-ttu-id="10908-180">Дополнительные сведения о привязанных к схеме функциях см. в разделе [Создание определяемых пользователем функций (компонент Database Engine)](../user-defined-functions/create-user-defined-functions-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="10908-180">For more information about schema-bound functions, see [Create User-defined Functions &#40;Database Engine&#41;](../user-defined-functions/create-user-defined-functions-database-engine.md).</span></span>  
  
## <a name="getting-information-about-synonyms"></a><span data-ttu-id="10908-181">Получение данных о синонимах</span><span class="sxs-lookup"><span data-stu-id="10908-181">Getting Information About Synonyms</span></span>  
 <span data-ttu-id="10908-182">Представление каталога sys.synonyms содержит запись для каждого синонима в данной базе данных.</span><span class="sxs-lookup"><span data-stu-id="10908-182">The sys.synonyms catalog view contains an entry for each synonym in a given database.</span></span> <span data-ttu-id="10908-183">Это представление каталога обеспечивает доступ к таким метаданным, как имя синонима и имя базового объекта.</span><span class="sxs-lookup"><span data-stu-id="10908-183">This catalog view exposes synonym metadata such as the name of the synonym and the name of the base object.</span></span> <span data-ttu-id="10908-184">Дополнительные сведения о `sys.synonyms` представлении каталога см. в разделе [sys. synonyms &#40;TRANSACT-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-synonyms-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="10908-184">For more information about the `sys.synonyms` catalog view, see [sys.synonyms &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-synonyms-transact-sql).</span></span>  
  
 <span data-ttu-id="10908-185">С помощью расширенных свойств можно добавлять описательный или управляющий текст, маски ввода и правила форматирования в виде свойств синонима.</span><span class="sxs-lookup"><span data-stu-id="10908-185">By using extended properties, you can add descriptive or instructional text, input masks, and formatting rules as properties of a synonym.</span></span> <span data-ttu-id="10908-186">Так как свойства хранятся в базе данных, все приложения, считывающие их, могут таким же образом вычислять объект.</span><span class="sxs-lookup"><span data-stu-id="10908-186">Because the property is stored in the database, all applications that read the property can evaluate the object in the same way.</span></span> <span data-ttu-id="10908-187">Дополнительные сведения см. в разделе [sp_addextendedproperty (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-addextendedproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="10908-187">For more information, see [sp_addextendedproperty &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addextendedproperty-transact-sql).</span></span>  
  
 <span data-ttu-id="10908-188">Чтобы найти базовый тип базового объекта синонима, используйте функцию OBJECTPROPERTYEX.</span><span class="sxs-lookup"><span data-stu-id="10908-188">To find the base type of the base object of a synonym, use the OBJECTPROPERTYEX function.</span></span> <span data-ttu-id="10908-189">Дополнительные сведения см. в разделе [OBJECTPROPERTYEX (Transact-SQL)](/sql/t-sql/functions/objectproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="10908-189">For more information, see [OBJECTPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectproperty-transact-sql).</span></span>  
  
### <a name="examples"></a><span data-ttu-id="10908-190">Примеры</span><span class="sxs-lookup"><span data-stu-id="10908-190">Examples</span></span>  
 <span data-ttu-id="10908-191">В следующем примере будет возвращен базовый тип локального базового объекта синонима.</span><span class="sxs-lookup"><span data-stu-id="10908-191">The following example returns the base type of a synonym's base object that is a local object.</span></span>  
  
```  
USE tempdb;  
GO  
CREATE SYNONYM MyEmployee   
FOR AdventureWorks2012.HumanResources.Employee;  
GO  
SELECT OBJECTPROPERTYEX(OBJECT_ID('MyEmployee'), 'BaseType') AS BaseType;  
```  
  
 <span data-ttu-id="10908-192">В следующем примере будет возвращен базовый тип удаленного базового объекта синонима, где базовый объект находится на сервере `Server1`.</span><span class="sxs-lookup"><span data-stu-id="10908-192">The following example returns the base type of a synonym's base object that is a remote object located on a server named `Server1`.</span></span>  
  
```  
EXECUTE sp_addlinkedserver Server1;  
GO  
CREATE SYNONYM MyRemoteEmployee  
FOR Server1.AdventureWorks2012.HumanResources.Employee;  
GO  
SELECT OBJECTPROPERTYEX(OBJECT_ID('MyRemoteEmployee'), 'BaseType') AS BaseType;  
GO  
```  
  
## <a name="related-content"></a><span data-ttu-id="10908-193">См. также</span><span class="sxs-lookup"><span data-stu-id="10908-193">Related Content</span></span>  
 [<span data-ttu-id="10908-194">Создание синонимов</span><span class="sxs-lookup"><span data-stu-id="10908-194">Create Synonyms</span></span>](create-synonyms.md)  
  
 [<span data-ttu-id="10908-195">CREATE SYNONYM (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="10908-195">CREATE SYNONYM &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-synonym-transact-sql)  
  
 [<span data-ttu-id="10908-196">DROP SYNONYM (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="10908-196">DROP SYNONYM &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-synonym-transact-sql)  
  
  
