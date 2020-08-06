---
title: MSSQLSERVER_ 2020 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2020 (Database Engine error)
ms.assetid: 4a8bf90f-a083-4c53-84f0-d23c711c8081
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5939267c37e90e7b8456dc01a4af79545e775656
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667142"
---
# <a name="mssqlserver_2020"></a><span data-ttu-id="d6696-102">MSSQLSERVER_2020</span><span class="sxs-lookup"><span data-stu-id="d6696-102">MSSQLSERVER_2020</span></span>
    
## <a name="details"></a><span data-ttu-id="d6696-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="d6696-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d6696-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="d6696-104">Product Name</span></span>|<span data-ttu-id="d6696-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d6696-105">SQL Server</span></span>|  
|<span data-ttu-id="d6696-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="d6696-106">Event ID</span></span>|<span data-ttu-id="d6696-107">2020</span><span class="sxs-lookup"><span data-stu-id="d6696-107">2020</span></span>|  
|<span data-ttu-id="d6696-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="d6696-108">Event Source</span></span>|<span data-ttu-id="d6696-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d6696-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d6696-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="d6696-110">Component</span></span>|<span data-ttu-id="d6696-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d6696-111">SQLEngine</span></span>|  
|<span data-ttu-id="d6696-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="d6696-112">Symbolic Name</span></span>||  
|<span data-ttu-id="d6696-113">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="d6696-113">Message Text</span></span>|<span data-ttu-id="d6696-114">Зависимости для сущности "%.\*ls" не содержат ссылок на столбцы.</span><span class="sxs-lookup"><span data-stu-id="d6696-114">The dependencies reported for entity "%.\*ls" do not include references to columns.</span></span> <span data-ttu-id="d6696-115">Это происходит либо оттого, что сущности ссылаются на несуществующий объект, либо из-за ошибки в одной или нескольких инструкциях сущности.</span><span class="sxs-lookup"><span data-stu-id="d6696-115">This is either because the entity references an object that does not exist or because of an error in one or more statements in the entity.</span></span>  <span data-ttu-id="d6696-116">Перед повторным выполнением запроса убедитесь, что отсутствуют ошибки в сущности и существуют все объекты, упоминаемые в сущности.</span><span class="sxs-lookup"><span data-stu-id="d6696-116">Before rerunning the query, ensure that there are no errors in the entity and that all objects referenced by the entity exist.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d6696-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="d6696-117">Explanation</span></span>  
 <span data-ttu-id="d6696-118">Системная функция **sys.dm_sql_referenced_entities** отобразит любую зависимость на уровне столбцов для ссылок, привязанных к схемам.</span><span class="sxs-lookup"><span data-stu-id="d6696-118">The **sys.dm_sql_referenced_entities** system function will report any column-level dependency for schema-bound references.</span></span> <span data-ttu-id="d6696-119">Например, функция отобразит все зависимости на уровне столбцов для индексированного представления, поскольку для индексированного представления необходима привязка к схеме.</span><span class="sxs-lookup"><span data-stu-id="d6696-119">For example, the function will report all column-level dependencies for an indexed view because an indexed view requires schema binding.</span></span> <span data-ttu-id="d6696-120">Однако если упоминаемая сущность, на которую дается ссылка, не привязана к схеме, зависимости столбцов отображаются только в том случае, если можно привязать все инструкции, в которых имеются ссылки на столбцы.</span><span class="sxs-lookup"><span data-stu-id="d6696-120">However, when the referenced entity is not schema-bound, column dependencies are reported only when all statements in which the columns are referenced can be bound.</span></span> <span data-ttu-id="d6696-121">Инструкции можно успешно привязать только при наличии всех объектов в момент синтаксического анализа инструкций.</span><span class="sxs-lookup"><span data-stu-id="d6696-121">Statements can be successfully bound only if all objects exist at the time the statements are parsed.</span></span> <span data-ttu-id="d6696-122">Если инструкцию, определенную в сущности, привязать не удается, зависимости столбцов не будут отображаться и столбец **referenced_minor_id** возвратит значение 0.</span><span class="sxs-lookup"><span data-stu-id="d6696-122">If any statement defined in the entity fails to bind, column dependencies will not be reported and the **referenced_minor_id** column will return 0.</span></span> <span data-ttu-id="d6696-123">Если не удается разрешить зависимости столбцов, возникает ошибка 2020.</span><span class="sxs-lookup"><span data-stu-id="d6696-123">When column dependencies cannot be resolved, error 2020 is raised.</span></span> <span data-ttu-id="d6696-124">Эта ошибка не препятствует возврату запросом зависимостей на уровне объектов.</span><span class="sxs-lookup"><span data-stu-id="d6696-124">This error does not prevent the query from returning object-level dependencies.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d6696-125">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="d6696-125">User Action</span></span>  
 <span data-ttu-id="d6696-126">Устраните ошибки, определенные в сообщении до возникновения ошибки 2020.</span><span class="sxs-lookup"><span data-stu-id="d6696-126">Correct any errors identified in the message before error 2020.</span></span> <span data-ttu-id="d6696-127">Например, в следующем примере кода представление `Production.ApprovedDocuments` определяется в столбцах `Title`, `ChangeNumber` и `Status` в таблице `Production.Document`.</span><span class="sxs-lookup"><span data-stu-id="d6696-127">For example, in the following code example the view `Production.ApprovedDocuments` is defined on the columns `Title`, `ChangeNumber`, and `Status` in the `Production.Document` table.</span></span> <span data-ttu-id="d6696-128">Объекты и столбцы, от которых зависит представление `ApprovedDocuments`, запрашиваются через системную функцию **sys.dm_sql_referenced_entities**.</span><span class="sxs-lookup"><span data-stu-id="d6696-128">The **sys.dm_sql_referenced_entities** system function is queried for the objects and columns on which the `ApprovedDocuments` view depends.</span></span> <span data-ttu-id="d6696-129">Поскольку представление не создается при помощи предложения WITH SCHEMA_BINDING, столбцы, на которые имеются ссылки в представлении, можно изменять в ссылочной таблице.</span><span class="sxs-lookup"><span data-stu-id="d6696-129">Because the view is not created using the WITH SCHEMA_BINDING clause, the columns referenced in the view can be modified in the referenced table.</span></span> <span data-ttu-id="d6696-130">В примере изменяется столбец `ChangeNumber` в таблице `Production.Document` путем переименования его в `TrackingNumber`.</span><span class="sxs-lookup"><span data-stu-id="d6696-130">The example alters the column `ChangeNumber` in the `Production.Document` table by renaming it to `TrackingNumber`.</span></span> <span data-ttu-id="d6696-131">Представление каталога вновь запрашивается для получения представления `ApprovedDocuments`; однако его нельзя привязать ко всем столбцам, определенным в представлении.</span><span class="sxs-lookup"><span data-stu-id="d6696-131">The catalog view is queried again for the `ApprovedDocuments` view; however it cannot bind to all the columns defined in the view.</span></span> <span data-ttu-id="d6696-132">Ошибки 207 и 2020 возвращаются с указанием проблемы.</span><span class="sxs-lookup"><span data-stu-id="d6696-132">Errors 207 and 2020 are returned identifying the problem.</span></span> <span data-ttu-id="d6696-133">Для решения проблемы необходимо изменить представление так, чтобы отразить новое имя столбца.</span><span class="sxs-lookup"><span data-stu-id="d6696-133">To resolve the problem, the view must be altered to reflect the new name of the column.</span></span>  
  
 `USE AdventureWorks2012;`  
  
 `GO`  
  
 `CREATE VIEW Production.ApprovedDocuments`  
  
 `AS`  
  
 `SELECT Title, ChangeNumber, Status`  
  
 `FROM Production.Document`  
  
 `WHERE Status = 2;`  
  
 `GO`  
  
 `SELECT referenced_schema_name AS schema_name`  
  
 `,referenced_entity_name AS table_name`  
  
 `,referenced_minor_name AS referenced_column`  
  
 `FROM sys.dm_sql_referenced_entities ('Production.ApprovedDocuments', 'OBJECT');`  
  
 `GO`  
  
 `EXEC sp_rename 'Production.Document.ChangeNumber', 'TrackingNumber', 'COLUMN';`  
  
 `GO`  
  
 `SELECT referenced_schema_name AS schema_name`  
  
 `,referenced_entity_name AS table_name`  
  
 `,referenced_minor_name AS referenced_column`  
  
 `FROM sys.dm_sql_referenced_entities ('Production.ApprovedDocuments', 'OBJECT');`  
  
 `GO`  
  
 <span data-ttu-id="d6696-134">Результатом запроса будут следующие сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="d6696-134">The query returns the following error messages.</span></span>  
  
 `Msg 207, Level 16, State 1, Procedure ApprovedDocuments, Line 3`  
  
 `Invalid column name 'ChangeNumber'.`  
  
 `Msg 2020, Level 16, State 1, Line 1`  
  
 `The dependencies reported for entity`  
  
 `"Production.ApprovedDocuments" do not include references to`  
  
 `columns. This is either because the entity references an`  
  
 `object that does not exist or because of an error in one or`  
  
 `more statements in the entity. Before rerunning the query,`  
  
 `ensure that there are no errors in the entity and that all`  
  
 `objects referenced by the entity exist.`  
  
 <span data-ttu-id="d6696-135">В следующем примере исправляется имя столбца в представлении.</span><span class="sxs-lookup"><span data-stu-id="d6696-135">The following example corrects the column name in the view.</span></span>  
  
 `USE AdventureWorks2012;`  
  
 `GO`  
  
 `ALTER VIEW Production.ApprovedDocuments`  
  
 `AS`  
  
 `SELECT Title,TrackingNumber, Status`  
  
 `FROM Production.Document`  
  
 `WHERE Status = 2;`  
  
 `GO`  
  
## <a name="see-also"></a><span data-ttu-id="d6696-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="d6696-136">See Also</span></span>  
 [<span data-ttu-id="d6696-137">Функция динамического управления sys.dm_sql_referenced_entities (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="d6696-137">sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referenced-entities-transact-sql)  
  
  
