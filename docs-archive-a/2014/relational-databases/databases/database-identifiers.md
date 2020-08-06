---
title: Идентификаторы баз данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- regular identifiers [SQL Server]
- identifiers [SQL Server]
- names [SQL Server], identifiers
- identifiers [SQL Server], about identifiers
- SQL Server identifiers
- Transact-SQL identifiers
- database objects [SQL Server], names
ms.assetid: 171291bb-f57f-4ad1-8cea-0b092d5d150c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 347b20c12a0ac5edd82172741377617aa0fe12c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658827"
---
# <a name="database-identifiers"></a><span data-ttu-id="210d0-102">Идентификаторы баз данных</span><span class="sxs-lookup"><span data-stu-id="210d0-102">Database Identifiers</span></span>
  <span data-ttu-id="210d0-103">Имя объекта базы данных называется его идентификатором.</span><span class="sxs-lookup"><span data-stu-id="210d0-103">The database object name is referred to as its identifier.</span></span> <span data-ttu-id="210d0-104">Идентификаторы в [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] могут присваиваться любым сущностям:</span><span class="sxs-lookup"><span data-stu-id="210d0-104">Everything in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can have an identifier.</span></span> <span data-ttu-id="210d0-105">серверам, базам данных и их объектам, например таблицам, представлениям, столбцам, индексам, триггерам, процедурам, ограничениям и правилам.</span><span class="sxs-lookup"><span data-stu-id="210d0-105">Servers, databases, and database objects, such as tables, views, columns, indexes, triggers, procedures, constraints, and rules, can have identifiers.</span></span> <span data-ttu-id="210d0-106">Для большинства объектов идентификаторы необходимы, а для некоторых, например ограничений, необязательны.</span><span class="sxs-lookup"><span data-stu-id="210d0-106">Identifiers are required for most objects, but are optional for some objects such as constraints.</span></span>  
  
 <span data-ttu-id="210d0-107">Идентификатор объекта создается при определении объекта.</span><span class="sxs-lookup"><span data-stu-id="210d0-107">An object identifier is created when the object is defined.</span></span> <span data-ttu-id="210d0-108">Затем идентификатор используется для обращения к объекту.</span><span class="sxs-lookup"><span data-stu-id="210d0-108">The identifier is then used to reference the object.</span></span> <span data-ttu-id="210d0-109">Например, следующая инструкция создает таблицу с идентификатором `TableX`и двумя столбцами с идентификаторами `KeyCol` и `Description`:</span><span class="sxs-lookup"><span data-stu-id="210d0-109">For example, the following statement creates a table with the identifier `TableX`, and two columns with the identifiers `KeyCol` and `Description`:</span></span>  
  
```  
CREATE TABLE TableX  
(KeyCol INT PRIMARY KEY, Description nvarchar(80))  
```  
  
 <span data-ttu-id="210d0-110">Эта таблица также содержит безымянное ограничение.</span><span class="sxs-lookup"><span data-stu-id="210d0-110">This table also has an unnamed constraint.</span></span> <span data-ttu-id="210d0-111">Ограничение `PRIMARY KEY` не имеет идентификатора.</span><span class="sxs-lookup"><span data-stu-id="210d0-111">The `PRIMARY KEY` constraint has no identifier.</span></span>  
  
 <span data-ttu-id="210d0-112">Параметры сортировки идентификатора зависят от уровня, для которого определен этот идентификатор.</span><span class="sxs-lookup"><span data-stu-id="210d0-112">The collation of an identifier depends on the level at which it is defined.</span></span> <span data-ttu-id="210d0-113">К идентификаторам объектов на уровне экземпляров, таких как имена входа и имена базы данных, применяются параметры сортировки по умолчанию для экземпляра.</span><span class="sxs-lookup"><span data-stu-id="210d0-113">Identifiers of instance-level objects, such as logins and database names, are assigned the default collation of the instance.</span></span> <span data-ttu-id="210d0-114">Идентификаторам объектов в пределах базы данных, например таблиц, представлений или имен столбцов, назначаются параметры сортировки, установленные по умолчанию для базы данных.</span><span class="sxs-lookup"><span data-stu-id="210d0-114">Identifiers of objects in a database, such as tables, views, and column names, are assigned the default collation of the database.</span></span> <span data-ttu-id="210d0-115">Например, две таблицы с именами, отличающимися только регистром, могут быть созданы в базе данных с параметрами сортировки c учетом регистра, но не могут быть созданы в базе данных с параметрами сортировки без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="210d0-115">For example, two tables with names that differ only in case can be created in a database that has case-sensitive collation, but cannot be created in a database that has case-insensitive collation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="210d0-116">Имена переменных или параметров функций и хранимых процедур должны соответствовать правилам для идентификаторов [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="210d0-116">The names of variables, or the parameters of functions and stored procedures must comply with the rules for [!INCLUDE[tsql](../../includes/tsql-md.md)] identifiers.</span></span>  
  
## <a name="classes-of-identifiers"></a><span data-ttu-id="210d0-117">Классы идентификаторов</span><span class="sxs-lookup"><span data-stu-id="210d0-117">Classes of Identifiers</span></span>  
 <span data-ttu-id="210d0-118">Существует два класса идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="210d0-118">There are two classes of identifiers:</span></span>  
  
 <span data-ttu-id="210d0-119">Обычные идентификаторы</span><span class="sxs-lookup"><span data-stu-id="210d0-119">Regular identifiers</span></span>  
 <span data-ttu-id="210d0-120">Соответствуют правилам форматирования идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="210d0-120">Comply with the rules for the format of identifiers.</span></span> <span data-ttu-id="210d0-121">Обычные идентификаторы не разделяются при использовании в инструкциях языка [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="210d0-121">Regular identifiers are not delimited when they are used in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span>  
  
```  
SELECT *  
FROM TableX  
WHERE KeyCol = 124  
```  
  
 <span data-ttu-id="210d0-122">Идентификаторы с разделителем</span><span class="sxs-lookup"><span data-stu-id="210d0-122">Delimited identifiers</span></span>  
 <span data-ttu-id="210d0-123">Заключаются в двойные кавычки (") или квадратные скобки ([ ]).</span><span class="sxs-lookup"><span data-stu-id="210d0-123">Are enclosed in double quotation marks (") or brackets ([ ]).</span></span> <span data-ttu-id="210d0-124">Идентификаторы, которые соответствуют правилам форматирования идентификаторов, могут быть не разделяемыми.</span><span class="sxs-lookup"><span data-stu-id="210d0-124">Identifiers that comply with the rules for the format of identifiers might not be delimited.</span></span> <span data-ttu-id="210d0-125">Пример:</span><span class="sxs-lookup"><span data-stu-id="210d0-125">For example:</span></span>  
  
```  
SELECT *  
FROM [TableX]         --Delimiter is optional.  
WHERE [KeyCol] = 124  --Delimiter is optional.  
```  
  
 <span data-ttu-id="210d0-126">Идентификаторы, которые не соответствуют всем правилам для идентификаторов, в инструкции языка [!INCLUDE[tsql](../../includes/tsql-md.md)] должны быть разделены.</span><span class="sxs-lookup"><span data-stu-id="210d0-126">Identifiers that do not comply with all the rules for identifiers must be delimited in a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="210d0-127">Пример:</span><span class="sxs-lookup"><span data-stu-id="210d0-127">For example:</span></span>  
  
```  
SELECT *  
FROM [My Table]      --Identifier contains a space and uses a reserved keyword.  
WHERE [order] = 10   --Identifier is a reserved keyword.  
```  
  
 <span data-ttu-id="210d0-128">И обычные идентификаторы, и идентификаторы с разделителями должны содержать от 1 до 128 символов.</span><span class="sxs-lookup"><span data-stu-id="210d0-128">Both regular and delimited identifiers must contain from 1 through 128 characters.</span></span> <span data-ttu-id="210d0-129">Для локальных временных таблиц идентификатор может содержать не более 116 символов.</span><span class="sxs-lookup"><span data-stu-id="210d0-129">For local temporary tables, the identifier can have a maximum of 116 characters.</span></span>  
  
## <a name="rules-for-regular-identifiers"></a><span data-ttu-id="210d0-130">Правила для обычных идентификаторов</span><span class="sxs-lookup"><span data-stu-id="210d0-130">Rules for Regular Identifiers</span></span>  
 <span data-ttu-id="210d0-131">Имена переменных, функций и хранимых процедур должны соответствовать этим правилам для идентификаторов [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="210d0-131">The names of variables, functions, and stored procedures must comply with the following rules for [!INCLUDE[tsql](../../includes/tsql-md.md)] identifiers.</span></span>  
  
1.  <span data-ttu-id="210d0-132">Первым символом должен быть один из следующих.</span><span class="sxs-lookup"><span data-stu-id="210d0-132">The first character must be one of the following:</span></span>  
  
    -   <span data-ttu-id="210d0-133">Буква в соответствии со стандартом Unicode Standard 3,2.</span><span class="sxs-lookup"><span data-stu-id="210d0-133">A letter as defined by the Unicode Standard 3.2.</span></span> <span data-ttu-id="210d0-134">Определения букв в стандарте Юникод включают латинские символы от «a» до «z», от «A» до «Z», а также буквенные символы других языков;</span><span class="sxs-lookup"><span data-stu-id="210d0-134">The Unicode definition of letters includes Latin characters from a through z, from A through Z, and also letter characters from other languages.</span></span>  
  
    -   <span data-ttu-id="210d0-135">подчеркивание (_), символ @ или решетка (#).</span><span class="sxs-lookup"><span data-stu-id="210d0-135">The underscore (_), at sign (@), or number sign (#).</span></span>  
  
         <span data-ttu-id="210d0-136">Определенные символы в начале идентификатора в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]имеют особое значение.</span><span class="sxs-lookup"><span data-stu-id="210d0-136">Certain symbols at the beginning of an identifier have special meaning in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="210d0-137">Обычный идентификатор, начинающийся символом @, означает локальную переменную или параметр и не может использоваться в качестве имени объекта какого-либо иного типа.</span><span class="sxs-lookup"><span data-stu-id="210d0-137">A regular identifier that starts with the at sign always denotes a local variable or parameter and cannot be used as the name of any other type of object.</span></span> <span data-ttu-id="210d0-138">Идентификатор, начинающийся символом решетки (#), означает временную таблицу или процедуру.</span><span class="sxs-lookup"><span data-stu-id="210d0-138">An identifier that starts with a number sign denotes a temporary table or procedure.</span></span> <span data-ttu-id="210d0-139">Идентификатор, начинающийся двойным символом решетки (##), означает глобальный временный объект.</span><span class="sxs-lookup"><span data-stu-id="210d0-139">An identifier that starts with double number signs (##) denotes a global temporary object.</span></span> <span data-ttu-id="210d0-140">Хотя символы решетки и двойной решетки могут использоваться в начале имен объектов других типов, мы не рекомендуем такой способ именования.</span><span class="sxs-lookup"><span data-stu-id="210d0-140">Although the number sign or double number sign characters can be used to begin the names of other types of objects, we do not recommend this practice.</span></span>  
  
         <span data-ttu-id="210d0-141">Некоторые функции языка [!INCLUDE[tsql](../../includes/tsql-md.md)] имеют имена, начинающиеся с двойного символа «@» (@@).</span><span class="sxs-lookup"><span data-stu-id="210d0-141">Some [!INCLUDE[tsql](../../includes/tsql-md.md)] functions have names that start with double at signs (@@).</span></span> <span data-ttu-id="210d0-142">Во избежание путаницы с этими функциями не следует использовать имена, начинающиеся символами @@.</span><span class="sxs-lookup"><span data-stu-id="210d0-142">To avoid confusion with these functions, you should not use names that start with @@.</span></span>  
  
2.  <span data-ttu-id="210d0-143">Последующие символы могут включать:</span><span class="sxs-lookup"><span data-stu-id="210d0-143">Subsequent characters can include the following:</span></span>  
  
    -   <span data-ttu-id="210d0-144">Буквы в соответствии со стандартом Unicode Standard 3,2.</span><span class="sxs-lookup"><span data-stu-id="210d0-144">Letters as defined in the Unicode Standard 3.2.</span></span>  
  
    -   <span data-ttu-id="210d0-145">Десятичные цифры из набора символов Basic Latin или другого набора символов национального языка.</span><span class="sxs-lookup"><span data-stu-id="210d0-145">Decimal numbers from either Basic Latin or other national scripts.</span></span>  
  
    -   <span data-ttu-id="210d0-146">символ @, знак доллара ($), решетка или подчеркивание.</span><span class="sxs-lookup"><span data-stu-id="210d0-146">The at sign, dollar sign ($), number sign, or underscore.</span></span>  
  
3.  <span data-ttu-id="210d0-147">Идентификатор не должен быть зарезервированным словом [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="210d0-147">The identifier must not be a [!INCLUDE[tsql](../../includes/tsql-md.md)] reserved word.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="210d0-148">резервирует версии зарезервированных слов как в верхнем, так и в нижнем регистре.</span><span class="sxs-lookup"><span data-stu-id="210d0-148">reserves both the uppercase and lowercase versions of reserved words.</span></span> <span data-ttu-id="210d0-149">Если идентификаторы используются в инструкциях языка [!INCLUDE[tsql](../../includes/tsql-md.md)] , идентификаторы, которые не соответствуют этим правилам, должны быть заключены в двойные кавычки или квадратные скобки.</span><span class="sxs-lookup"><span data-stu-id="210d0-149">When identifiers are used in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, the identifiers that do not comply with these rules must be delimited by double quotation marks or brackets.</span></span> <span data-ttu-id="210d0-150">Состав зарезервированных слов зависит от уровня совместимости базы данных.</span><span class="sxs-lookup"><span data-stu-id="210d0-150">The words that are reserved depend on the database compatibility level.</span></span> <span data-ttu-id="210d0-151">Этот уровень можно установить с помощью инструкции [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level) .</span><span class="sxs-lookup"><span data-stu-id="210d0-151">This level can be set by using the [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level) statement.</span></span>  
  
4.  <span data-ttu-id="210d0-152">Внутри идентификаторов запрещается использовать символы пробела или специальные символы.</span><span class="sxs-lookup"><span data-stu-id="210d0-152">Embedded spaces or special characters are not allowed.</span></span>  
  
5.  <span data-ttu-id="210d0-153">Дополнительные символы недопустимы.</span><span class="sxs-lookup"><span data-stu-id="210d0-153">Supplementary characters are not allowed.</span></span>  
  
 <span data-ttu-id="210d0-154">Если идентификаторы используются в инструкциях языка [!INCLUDE[tsql](../../includes/tsql-md.md)] , идентификаторы, которые не соответствуют этим правилам, должны быть заключены в двойные кавычки или квадратные скобки.</span><span class="sxs-lookup"><span data-stu-id="210d0-154">When identifiers are used in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, the identifiers that do not comply with these rules must be delimited by double quotation marks or brackets.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="210d0-155">Некоторые правила форматирования обычных идентификаторов зависят от уровня совместимости базы данных.</span><span class="sxs-lookup"><span data-stu-id="210d0-155">Some rules for the format of regular identifiers depend on the database compatibility level.</span></span> <span data-ttu-id="210d0-156">Этот уровень можно установить с помощью процедуры [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level).</span><span class="sxs-lookup"><span data-stu-id="210d0-156">This level can be set by using [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="210d0-157">См. также:</span><span class="sxs-lookup"><span data-stu-id="210d0-157">See Also</span></span>  
 <span data-ttu-id="210d0-158">[ALTER TABLE (Transact-SQL)](/sql/t-sql/statements/alter-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="210d0-158">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span></span>  
 <span data-ttu-id="210d0-159">[CREATE DATABASE (SQL Server Transact-SQL)](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="210d0-159">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 <span data-ttu-id="210d0-160">[CREATE DEFAULT (Transact-SQL)](/sql/t-sql/statements/create-default-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="210d0-160">[CREATE DEFAULT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-default-transact-sql) </span></span>  
 <span data-ttu-id="210d0-161">[CREATE PROCEDURE (Transact-SQL)](/sql/t-sql/statements/create-procedure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="210d0-161">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span></span>  
 <span data-ttu-id="210d0-162">[CREATE RULE (Transact-SQL)](/sql/t-sql/statements/create-rule-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="210d0-162">[CREATE RULE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-rule-transact-sql) </span></span>  
 <span data-ttu-id="210d0-163">[CREATE TABLE (Transact-SQL)](/sql/t-sql/statements/create-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="210d0-163">[CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) </span></span>  
 <span data-ttu-id="210d0-164">[CREATE TRIGGER (Transact-SQL)](/sql/t-sql/statements/create-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="210d0-164">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span></span>  
 <span data-ttu-id="210d0-165">[CREATE VIEW (Transact-SQL)](/sql/t-sql/statements/create-view-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="210d0-165">[CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql) </span></span>  
 <span data-ttu-id="210d0-166">[DECLARE @local_variable (Transact-SQL)](/sql/t-sql/language-elements/declare-local-variable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="210d0-166">[DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql) </span></span>  
 <span data-ttu-id="210d0-167">[DELETE (Transact-SQL)](/sql/t-sql/statements/delete-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="210d0-167">[DELETE &#40;Transact-SQL&#41;](/sql/t-sql/statements/delete-transact-sql) </span></span>  
 <span data-ttu-id="210d0-168">[INSERT (Transact-SQL)](/sql/t-sql/statements/insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="210d0-168">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span></span>  
 <span data-ttu-id="210d0-169">[Зарезервированные ключевые слова (Transact-SQL)](/sql/t-sql/language-elements/reserved-keywords-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="210d0-169">[Reserved Keywords &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reserved-keywords-transact-sql) </span></span>  
 <span data-ttu-id="210d0-170">[SELECT (Transact-SQL)](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="210d0-170">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 [<span data-ttu-id="210d0-171">UPDATE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="210d0-171">UPDATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/update-transact-sql)  
  
  
