---
title: Просмотр определяемых пользователем функций | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.udfproperties.general.f1
- sql12.swb.functionproperties.general.f1
helpviewer_keywords:
- displaying user-defined functions
- viewing user-defined functions
- user-defined functions [SQL Server], viewing
- status information [SQL Server], user-defined functions
ms.assetid: a45dfab5-6384-4311-b935-2e23a70c5c10
author: rothja
ms.author: jroth
ms.openlocfilehash: 5248f75540b72b489a7605b2cca34144dfcfedbf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654103"
---
# <a name="view-user-defined-functions"></a><span data-ttu-id="44999-102">Просмотр определяемых пользователем функций</span><span class="sxs-lookup"><span data-stu-id="44999-102">View User-defined Functions</span></span>
  <span data-ttu-id="44999-103">Получить сведения об определении или свойствах определяемой пользователем функции в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] можно с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44999-103">You can gain information about the definition or properties of a user-defined function in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="44999-104">Возможность просмотреть определение функции может понадобиться, чтобы понять, как его данные извлекаются из исходных таблиц, или чтобы увидеть данные, определенные функцией.</span><span class="sxs-lookup"><span data-stu-id="44999-104">You may need to see the definition of the function to understand how its data is derived from the source tables or to see the data defined by the function.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="44999-105">Если имя объекта, на который ссылается функция, было изменено, необходимо изменить функцию так, чтобы в ее тексте использовалось новое имя.</span><span class="sxs-lookup"><span data-stu-id="44999-105">If you change the name of an object referenced by a function, you must modify that function so that its text reflects the new name.</span></span> <span data-ttu-id="44999-106">Поэтому, прежде чем переименовать объект, отобразите список его зависимостей, чтобы определить, отразится ли планируемое изменение на каких-либо функциях.</span><span class="sxs-lookup"><span data-stu-id="44999-106">Therefore, before renaming an object, display the dependencies of the object first to determine if any functions are affected by the proposed change.</span></span>  
  
 <span data-ttu-id="44999-107">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="44999-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="44999-108">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="44999-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="44999-109">Безопасность</span><span class="sxs-lookup"><span data-stu-id="44999-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="44999-110">**Для получения сведений о функции используется:**</span><span class="sxs-lookup"><span data-stu-id="44999-110">**To get information about a function, using:**</span></span>  
  
     [<span data-ttu-id="44999-111">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="44999-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="44999-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="44999-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="44999-113">Перед началом</span><span class="sxs-lookup"><span data-stu-id="44999-113">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="44999-114">безопасность</span><span class="sxs-lookup"><span data-stu-id="44999-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="44999-115">Permissions</span><span class="sxs-lookup"><span data-stu-id="44999-115">Permissions</span></span>  
 <span data-ttu-id="44999-116">Для использования **sys.sql_expression_dependencies** в поиске всех зависимостей функции необходимо разрешение VIEW DEFINITION на базу данных и разрешение SELECT на представление **sys.sql_expression_dependencies** для базы данных.</span><span class="sxs-lookup"><span data-stu-id="44999-116">Using **sys.sql_expression_dependencies** to find all the dependencies on a function requires VIEW DEFINITION permission on the database and SELECT permission on **sys.sql_expression_dependencies** for the database.</span></span> <span data-ttu-id="44999-117">Определения системных объектов, например полученные в OBJECT_DEFINITION, видимы для всех.</span><span class="sxs-lookup"><span data-stu-id="44999-117">System object definitions, like the ones returned in OBJECT_DEFINITION, are publicly visible.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="44999-118">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="44999-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-show-a-user-defined-functions-properties"></a><span data-ttu-id="44999-119">Отображение свойств определяемой пользователем функции</span><span class="sxs-lookup"><span data-stu-id="44999-119">To show a user-defined function's properties</span></span>  
  
1.  <span data-ttu-id="44999-120">В **обозревателе объектов**щелкните знак «плюс» рядом с базой данных, содержащей функцию, свойства которой необходимо просмотреть, а затем щелкните знак «плюс», чтобы развернуть папку **Программирование** .</span><span class="sxs-lookup"><span data-stu-id="44999-120">In **Object Explorer**, click the plus sign next to the database that contains the function to which you want to view the properties, and then click the plus sign to expand the **Programmability** folder.</span></span>  
  
2.  <span data-ttu-id="44999-121">Чтобы развернуть папку **Функции** , щелкните знак «плюс» (+).</span><span class="sxs-lookup"><span data-stu-id="44999-121">Click the plus sign to expand the **Functions** folder.</span></span>  
  
3.  <span data-ttu-id="44999-122">Щелкните знак «плюс», чтобы развернуть папку, содержащую функцию, для которой нужно просмотреть свойства.</span><span class="sxs-lookup"><span data-stu-id="44999-122">Click the plus sign to expand the folder that contains the function to which you want to view the properties:</span></span>  
  
    -   <span data-ttu-id="44999-123">Table-valued Function</span><span class="sxs-lookup"><span data-stu-id="44999-123">Table-valued Function</span></span>  
  
    -   <span data-ttu-id="44999-124">Скалярная функция</span><span class="sxs-lookup"><span data-stu-id="44999-124">Scalar-valued Function</span></span>  
  
    -   <span data-ttu-id="44999-125">Агрегатная функция</span><span class="sxs-lookup"><span data-stu-id="44999-125">Aggregate Function</span></span>  
  
4.  <span data-ttu-id="44999-126">Щелкните правой кнопкой мыши функцию, свойства которой необходимо просмотреть, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="44999-126">Right-click the function of which you want to view the properties and select **Properties**.</span></span>  
  
     <span data-ttu-id="44999-127">Следующие свойства отображаются в диалоговом окне **Свойства функции —** _имя_функции_.</span><span class="sxs-lookup"><span data-stu-id="44999-127">The following properties appear in the **Function Properties -** _function_name_ dialog box.</span></span>  
  
     <span data-ttu-id="44999-128">**База данных**</span><span class="sxs-lookup"><span data-stu-id="44999-128">**Database**</span></span>  
     <span data-ttu-id="44999-129">Имя базы данных, содержащей эту функцию.</span><span class="sxs-lookup"><span data-stu-id="44999-129">The name of the database containing this function.</span></span>  
  
     <span data-ttu-id="44999-130">**Server**</span><span class="sxs-lookup"><span data-stu-id="44999-130">**Server**</span></span>  
     <span data-ttu-id="44999-131">Имя текущего экземпляра сервера.</span><span class="sxs-lookup"><span data-stu-id="44999-131">The name of the current server instance.</span></span>  
  
     <span data-ttu-id="44999-132">**Пользователь**</span><span class="sxs-lookup"><span data-stu-id="44999-132">**User**</span></span>  
     <span data-ttu-id="44999-133">Имя пользователя этого соединения.</span><span class="sxs-lookup"><span data-stu-id="44999-133">The name of the user of this connection.</span></span>  
  
     <span data-ttu-id="44999-134">**Дата создания**</span><span class="sxs-lookup"><span data-stu-id="44999-134">**Created date**</span></span>  
     <span data-ttu-id="44999-135">Дата создания функции.</span><span class="sxs-lookup"><span data-stu-id="44999-135">Displays the date the function was created.</span></span>  
  
     <span data-ttu-id="44999-136">**Выполнить от имени**</span><span class="sxs-lookup"><span data-stu-id="44999-136">**Execute As**</span></span>  
     <span data-ttu-id="44999-137">Контекст выполнения для функции.</span><span class="sxs-lookup"><span data-stu-id="44999-137">Execution context for the function.</span></span>  
  
     <span data-ttu-id="44999-138">**Название**</span><span class="sxs-lookup"><span data-stu-id="44999-138">**Name**</span></span>  
     <span data-ttu-id="44999-139">Имя текущей функции.</span><span class="sxs-lookup"><span data-stu-id="44999-139">The name of the current function.</span></span>  
  
     <span data-ttu-id="44999-140">**Схема**</span><span class="sxs-lookup"><span data-stu-id="44999-140">**Schema**</span></span>  
     <span data-ttu-id="44999-141">Схема, которой принадлежит функция.</span><span class="sxs-lookup"><span data-stu-id="44999-141">Displays the schema that owns the function.</span></span>  
  
     <span data-ttu-id="44999-142">**Системный объект**</span><span class="sxs-lookup"><span data-stu-id="44999-142">**System object**</span></span>  
     <span data-ttu-id="44999-143">Указывает принадлежность функции к системным объектам.</span><span class="sxs-lookup"><span data-stu-id="44999-143">Indicates whether the function is a system object.</span></span> <span data-ttu-id="44999-144">Возможные значения: True и False.</span><span class="sxs-lookup"><span data-stu-id="44999-144">Values are True and False.</span></span>  
  
     <span data-ttu-id="44999-145">**Значения NULL по стандарту ANSI**</span><span class="sxs-lookup"><span data-stu-id="44999-145">**ANSI NULLs**</span></span>  
     <span data-ttu-id="44999-146">Указывает, был ли объект создан с параметром ANSI NULL.</span><span class="sxs-lookup"><span data-stu-id="44999-146">Indicates if the object was created with the ANSI NULLs option.</span></span>  
  
     <span data-ttu-id="44999-147">**Зашифрована**</span><span class="sxs-lookup"><span data-stu-id="44999-147">**Encrypted**</span></span>  
     <span data-ttu-id="44999-148">Указывает, зашифрована ли функция.</span><span class="sxs-lookup"><span data-stu-id="44999-148">Indicates whether the function is encrypted.</span></span> <span data-ttu-id="44999-149">Возможные значения: True и False.</span><span class="sxs-lookup"><span data-stu-id="44999-149">Values are True and False.</span></span>  
  
     <span data-ttu-id="44999-150">**Тип функции**</span><span class="sxs-lookup"><span data-stu-id="44999-150">**Function Type**</span></span>  
     <span data-ttu-id="44999-151">Тип определяемой пользователем функции.</span><span class="sxs-lookup"><span data-stu-id="44999-151">The type of user defined function.</span></span>  
  
     <span data-ttu-id="44999-152">**Заключенный в кавычки идентификатор**</span><span class="sxs-lookup"><span data-stu-id="44999-152">**Quoted identifier**</span></span>  
     <span data-ttu-id="44999-153">Показывает, был ли объект создан с параметром «заключенный в кавычки идентификатор».</span><span class="sxs-lookup"><span data-stu-id="44999-153">Indicates if the object was created with the quoted identifier option.</span></span>  
  
     <span data-ttu-id="44999-154">**Привязка к схеме**</span><span class="sxs-lookup"><span data-stu-id="44999-154">**Schema bound**</span></span>  
     <span data-ttu-id="44999-155">Указывает, привязана ли функция к схеме.</span><span class="sxs-lookup"><span data-stu-id="44999-155">Indicates whether the function is schema-bound.</span></span> <span data-ttu-id="44999-156">Возможные значения: True и False.</span><span class="sxs-lookup"><span data-stu-id="44999-156">Values are True and False.</span></span> <span data-ttu-id="44999-157">Дополнительные сведения о функциях, привязанных к схеме, см. в подразделе SCHEMABINDING раздела [CREATE FUNCTION (Transact-SQL)](/sql/t-sql/statements/create-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="44999-157">For information about schema-bound functions, see the SCHEMABINDING section of [CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="44999-158">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="44999-158">Using Transact-SQL</span></span>  
  
#### <a name="to-get-the-definition-and-properties-of-a-function"></a><span data-ttu-id="44999-159">Получение определения и свойств функции</span><span class="sxs-lookup"><span data-stu-id="44999-159">To get the definition and properties of a function</span></span>  
  
1.  <span data-ttu-id="44999-160">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44999-160">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="44999-161">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="44999-161">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="44999-162">Скопируйте и вставьте один из следующих примеров в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="44999-162">Copy and paste one of the following examples into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Get the function name, definition, and relevant properties  
    SELECT sm.object_id,   
       OBJECT_NAME(sm.object_id) AS object_name,   
       o.type,   
       o.type_desc,   
       sm.definition,  
       sm.uses_ansi_nulls,  
       sm.uses_quoted_identifier,  
       sm.is_schema_bound,  
       sm.execute_as_principal_id  
    -- using the two system tables sys.sql_modules and sys.objects  
    FROM sys.sql_modules AS sm  
    JOIN sys.objects AS o ON sm.object_id = o.object_id  
    -- from the function 'dbo.ufnGetProductDealerPrice'  
    WHERE sm.object_id = OBJECT_ID('dbo.ufnGetProductDealerPrice')  
    ORDER BY o.type;  
    GO  
  
    ```  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Get the definition of the function dbo.ufnGetProductDealerPrice  
    SELECT OBJECT_DEFINITION (OBJECT_ID('dbo.ufnGetProductDealerPrice')) AS ObjectDefinition;  
    GO  
    ```  
  
 <span data-ttu-id="44999-163">Дополнительные сведения см. в разделах [sys.sql_modules (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) и [OBJECT_DEFINITION (Transact-SQL)](/sql/t-sql/functions/object-definition-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="44999-163">For more information, see [sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) and [OBJECT_DEFINITION &#40;Transact-SQL&#41;](/sql/t-sql/functions/object-definition-transact-sql).</span></span>  
  
#### <a name="to-get-the-dependencies-of-a-function"></a><span data-ttu-id="44999-164">Получение зависимостей функции</span><span class="sxs-lookup"><span data-stu-id="44999-164">To get the dependencies of a function</span></span>  
  
1.  <span data-ttu-id="44999-165">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44999-165">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="44999-166">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="44999-166">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="44999-167">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="44999-167">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Get all of the dependency information  
    SELECT OBJECT_NAME(sed.referencing_id) AS referencing_entity_name,   
        o.type_desc AS referencing_desciption,   
        COALESCE(COL_NAME(sed.referencing_id, sed.referencing_minor_id), '(n/a)') AS referencing_minor_id,   
        sed.referencing_class_desc, sed.referenced_class_desc,  
        sed.referenced_server_name, sed.referenced_database_name, sed.referenced_schema_name,  
        sed.referenced_entity_name,   
        COALESCE(COL_NAME(sed.referenced_id, sed.referenced_minor_id), '(n/a)') AS referenced_column_name,  
        sed.is_caller_dependent, sed.is_ambiguous  
    -- from the two system tables sys.sql_expression_dependencies and sys.object  
    FROM sys.sql_expression_dependencies AS sed  
    INNER JOIN sys.objects AS o ON sed.referencing_id = o.object_id  
    -- on the function dbo.ufnGetProductDealerPrice  
    WHERE sed.referencing_id = OBJECT_ID('dbo.ufnGetProductDealerPrice');  
    GO  
    ```  
  
 <span data-ttu-id="44999-168">Дополнительные сведения см. в разделах [sys.sql_expression_dependencies (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) и [sys.objects (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="44999-168">For more information, see [sys.sql_expression_dependencies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql) and [sys.objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql).</span></span>  
  
  
