---
title: Индексы по вычисляемым столбцам | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- computed columns, index creation
- index creation [SQL Server], computed columns
- imprecise columns
- persisted computed columns
- precise [SQL Server]
ms.assetid: 8d17ac9c-f3af-4bbb-9cc1-5cf647e994c4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2ecbca9e7838c4c9395a8bcb6e11351c40f7037f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750959"
---
# <a name="indexes-on-computed-columns"></a><span data-ttu-id="70bc4-102">Индексы вычисляемых столбцов</span><span class="sxs-lookup"><span data-stu-id="70bc4-102">Indexes on Computed Columns</span></span>
  <span data-ttu-id="70bc4-103">Индексы вычисляемых столбцов можно определить, если удовлетворяются следующие требования:</span><span class="sxs-lookup"><span data-stu-id="70bc4-103">You can define indexes on computed columns as long as the following requirements are met:</span></span>  
  
-   <span data-ttu-id="70bc4-104">требования к владению;</span><span class="sxs-lookup"><span data-stu-id="70bc4-104">Ownership requirements</span></span>  
  
-   <span data-ttu-id="70bc4-105">требования к детерминированности;</span><span class="sxs-lookup"><span data-stu-id="70bc4-105">Determinism requirements</span></span>  
  
-   <span data-ttu-id="70bc4-106">требования к точности;</span><span class="sxs-lookup"><span data-stu-id="70bc4-106">Precision requirements</span></span>  
  
-   <span data-ttu-id="70bc4-107">требования к типам данных;</span><span class="sxs-lookup"><span data-stu-id="70bc4-107">Data type requirements</span></span>  
  
-   <span data-ttu-id="70bc4-108">требования к параметру SET.</span><span class="sxs-lookup"><span data-stu-id="70bc4-108">SET option requirements</span></span>  
  
 <span data-ttu-id="70bc4-109">**Ownership Requirements**</span><span class="sxs-lookup"><span data-stu-id="70bc4-109">**Ownership Requirements**</span></span>  
  
 <span data-ttu-id="70bc4-110">Все ссылки на функции в вычисляемом столбце должны иметь того же владельца, что и таблица.</span><span class="sxs-lookup"><span data-stu-id="70bc4-110">All function references in the computed column must have the same owner as the table.</span></span>  
  
 <span data-ttu-id="70bc4-111">**Determinism Requirements**</span><span class="sxs-lookup"><span data-stu-id="70bc4-111">**Determinism Requirements**</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="70bc4-112">Выражения являются детерминированными, если они всегда возвращают один и тот же результат для определенного набора входных данных.</span><span class="sxs-lookup"><span data-stu-id="70bc4-112">Expressions are deterministic if they always return the same result for a specified set of inputs.</span></span> <span data-ttu-id="70bc4-113">Свойство **IsDeterministic** функции [COLUMNPROPERTY](/sql/t-sql/functions/columnproperty-transact-sql) определяет, детерминировано ли выражение *computed_column_expression* .</span><span class="sxs-lookup"><span data-stu-id="70bc4-113">The **IsDeterministic** property of the [COLUMNPROPERTY](/sql/t-sql/functions/columnproperty-transact-sql) function reports whether a *computed_column_expression* is deterministic.</span></span>  
  
 <span data-ttu-id="70bc4-114">Выражение *computed_column_expression* должно быть детерминированным.</span><span class="sxs-lookup"><span data-stu-id="70bc4-114">The *computed_column_expression* must be deterministic.</span></span> <span data-ttu-id="70bc4-115">Выражение *computed_column_expression* является детерминированным, если соблюдается одно или несколько следующих условий:</span><span class="sxs-lookup"><span data-stu-id="70bc4-115">A *computed_column_expression* is deterministic when one or more of the following is true:</span></span>  
  
-   <span data-ttu-id="70bc4-116">Все функции, на которые ссылается выражение, являются детерминированными и точными.</span><span class="sxs-lookup"><span data-stu-id="70bc4-116">All functions that are referenced by the expression are deterministic and precise.</span></span> <span data-ttu-id="70bc4-117">Это относится как к пользовательским, так и к встроенным функциям.</span><span class="sxs-lookup"><span data-stu-id="70bc4-117">These functions include both user-defined and built-in functions.</span></span> <span data-ttu-id="70bc4-118">Дополнительные сведения см. в разделе [Deterministic and Nondeterministic Functions](../user-defined-functions/deterministic-and-nondeterministic-functions.md).</span><span class="sxs-lookup"><span data-stu-id="70bc4-118">For more information, see [Deterministic and Nondeterministic Functions](../user-defined-functions/deterministic-and-nondeterministic-functions.md).</span></span> <span data-ttu-id="70bc4-119">Функции могут быть неточными, если вычисляемый столбец помечен как PERSISTED.</span><span class="sxs-lookup"><span data-stu-id="70bc4-119">Functions might be imprecise if the computed column is PERSISTED.</span></span> <span data-ttu-id="70bc4-120">Дополнительные сведения см. ниже в разделе [Создание индексов материализованных вычисляемых столбцов](#BKMK_persisted) .</span><span class="sxs-lookup"><span data-stu-id="70bc4-120">For more information, see [Creating Indexes on Persisted Computed Columns](#BKMK_persisted) later in this topic.</span></span>  
  
-   <span data-ttu-id="70bc4-121">Все столбцы, на которые ссылается выражение, берутся из таблицы, содержащей вычисляемый столбец.</span><span class="sxs-lookup"><span data-stu-id="70bc4-121">All columns that are referenced in the expression come from the table that contains the computed column.</span></span>  
  
-   <span data-ttu-id="70bc4-122">Ни одна ссылка на столбец не запрашивает данные из нескольких строк.</span><span class="sxs-lookup"><span data-stu-id="70bc4-122">No column reference pulls data from multiple rows.</span></span> <span data-ttu-id="70bc4-123">Например, агрегатные функции, такие как SUM или AVG, используют данные из нескольких строк и делают выражение *computed_column_expression* недетерминированным.</span><span class="sxs-lookup"><span data-stu-id="70bc4-123">For example, aggregate functions such as SUM or AVG depend on data from multiple rows and would make a *computed_column_expression* nondeterministic.</span></span>  
  
-   <span data-ttu-id="70bc4-124">У выражения *computed_column_expression* нет доступа к системным данным или данным пользователя.</span><span class="sxs-lookup"><span data-stu-id="70bc4-124">The *computed_column_expression* has no system data access or user data access.</span></span>  
  
 <span data-ttu-id="70bc4-125">Для индексирования требуется, чтобы любой вычисляемый столбец, содержащий выражение CLR, перед индексированием был детерминированным и помеченным как PERSISTED.</span><span class="sxs-lookup"><span data-stu-id="70bc4-125">Any computed column that contains a common language runtime (CLR) expression must be deterministic and marked PERSISTED before the column can be indexed.</span></span> <span data-ttu-id="70bc4-126">Выражения определяемого пользователем типа данных CLR допускаются в определениях вычисляемых столбцов.</span><span class="sxs-lookup"><span data-stu-id="70bc4-126">CLR user-defined type expressions are allowed in computed column definitions.</span></span> <span data-ttu-id="70bc4-127">Вычисляемые столбцы, которые имеют определяемый пользователем тип данных CLR, могут быть индексированы, если этот тип сопоставим.</span><span class="sxs-lookup"><span data-stu-id="70bc4-127">Computed columns whose type is a CLR user-defined type can be indexed as long as the type is comparable.</span></span> <span data-ttu-id="70bc4-128">Дополнительные сведения об определяемых пользователем типах данных CLR см. в разделе [Определяемые пользователем типы данных CLR](../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md).</span><span class="sxs-lookup"><span data-stu-id="70bc4-128">For more information, see [CLR User-Defined Types](../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="70bc4-129">При указании в индексируемых вычисляемых столбцах [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]строковых литералов типа данных «дата», рекомендуется явно преобразовывать их в тип данных «дата» при помощи детерминированного стиля форматирования даты.</span><span class="sxs-lookup"><span data-stu-id="70bc4-129">When you refer to string literals of the date data type in indexed computed columns in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], we recommend that you explicitly convert the literal to the date type that you want by using a deterministic date format style.</span></span> <span data-ttu-id="70bc4-130">Список детерминированных стилей форматирования даты см. в разделе [CAST и CONVERT](/sql/t-sql/functions/cast-and-convert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="70bc4-130">For a list of the date format styles that are deterministic, see [CAST and CONVERT](/sql/t-sql/functions/cast-and-convert-transact-sql).</span></span> <span data-ttu-id="70bc4-131">Выражения, включающие неявные преобразования символьных строк в типы данных, считаются недетерминированными, если только не установлен уровень совместимости базы данных, равный 80 или менее.</span><span class="sxs-lookup"><span data-stu-id="70bc4-131">Expressions that involve implicit conversion of character strings to date data types are considered nondeterministic, unless the database compatibility level is set to 80 or earlier.</span></span> <span data-ttu-id="70bc4-132">Это связано с тем, что результаты зависят от значений параметров [LANGUAGE](/sql/t-sql/statements/set-language-transact-sql) и [DATEFORMAT](/sql/t-sql/statements/set-dateformat-transact-sql) , определенных для сеанса сервера.</span><span class="sxs-lookup"><span data-stu-id="70bc4-132">This is because the results depend on the [LANGUAGE](/sql/t-sql/statements/set-language-transact-sql) and [DATEFORMAT](/sql/t-sql/statements/set-dateformat-transact-sql) settings of the server session.</span></span> <span data-ttu-id="70bc4-133">Например, результат выражения `CONVERT (datetime, '30 listopad 1996', 113)` зависит от значения параметра LANGUAGE, поскольку строка`30 listopad 1996`в различных языках обозначает разные месяцы.</span><span class="sxs-lookup"><span data-stu-id="70bc4-133">For example, the results of the expression `CONVERT (datetime, '30 listopad 1996', 113)` depend on the LANGUAGE setting because the string '`30 listopad 1996`' means different months in different languages.</span></span> <span data-ttu-id="70bc4-134">Аналогично, в выражении `DATEADD(mm,3,'2000-12-01')`компонент [!INCLUDE[ssDE](../../../includes/ssde-md.md)] интерпретирует строку `'2000-12-01'` в соответствии со значением параметра DATEFORMAT.</span><span class="sxs-lookup"><span data-stu-id="70bc4-134">Similarly, in the expression `DATEADD(mm,3,'2000-12-01')`, the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] interprets the string `'2000-12-01'` based on the DATEFORMAT setting.</span></span>  
>   
>  <span data-ttu-id="70bc4-135">Неявное преобразование символьных данных не в Юникоде между различными параметрами сортировки также считается недетерминированным, если уровень совместимости не установлен равным или меньшим 80.</span><span class="sxs-lookup"><span data-stu-id="70bc4-135">Implicit conversion of non-Unicode character data between collations is also considered nondeterministic, unless the compatibility level is set to 80 or earlier.</span></span>  
>   
>  <span data-ttu-id="70bc4-136">Если параметр уровня совместимости равен 90, создавать индексы на вычисляемых столбцах, содержащих эти выражения, нельзя.</span><span class="sxs-lookup"><span data-stu-id="70bc4-136">When the database compatibility level setting is 90, you cannot create indexes on computed columns that contain these expressions.</span></span> <span data-ttu-id="70bc4-137">Это, однако, не относится к существующим вычисляемым столбцам, содержащим такие выражения из обновленной базы данных.</span><span class="sxs-lookup"><span data-stu-id="70bc4-137">However, existing computed columns that contain these expressions from an upgraded database are maintainable.</span></span> <span data-ttu-id="70bc4-138">Если используются индексированные вычисляемые столбцы, которые содержат неявные преобразования из строк в даты, то для предотвращения возможного повреждения индекса убедитесь, что параметры LANGUAGE и DATEFORMAT согласованы с базами данных и приложениями.</span><span class="sxs-lookup"><span data-stu-id="70bc4-138">If you use indexed computed columns that contain implicit string to date conversions, to avoid possible index corruption, make sure that the LANGUAGE and DATEFORMAT settings are consistent in your databases and applications.</span></span>  
  
 <span data-ttu-id="70bc4-139">**Precision Requirements**</span><span class="sxs-lookup"><span data-stu-id="70bc4-139">**Precision Requirements**</span></span>  
  
 <span data-ttu-id="70bc4-140">Выражение *computed_column_expression* должно быть точным.</span><span class="sxs-lookup"><span data-stu-id="70bc4-140">The *computed_column_expression* must be precise.</span></span> <span data-ttu-id="70bc4-141">Выражение *computed_column_expression* является точным, если соблюдается одно или несколько следующих условий:</span><span class="sxs-lookup"><span data-stu-id="70bc4-141">A *computed_column_expression* is precise when one or more of the following is true:</span></span>  
  
-   <span data-ttu-id="70bc4-142">Выражение не относится к типу данных `float` или `real`.</span><span class="sxs-lookup"><span data-stu-id="70bc4-142">It is not an expression of the `float` or `real` data types.</span></span>  
  
-   <span data-ttu-id="70bc4-143">В его определении не используется тип данных `float` или `real`.</span><span class="sxs-lookup"><span data-stu-id="70bc4-143">It does not use a `float` or `real` data type in its definition.</span></span> <span data-ttu-id="70bc4-144">Например, в следующей инструкции столбец `y` имеет тип `int` и является детерминированным, но неточным.</span><span class="sxs-lookup"><span data-stu-id="70bc4-144">For example, in the following statement, column `y` is `int` and deterministic but not precise.</span></span>  
  
    ```  
    CREATE TABLE t2 (a int, b int, c int, x float,   
       y AS CASE x   
             WHEN 0 THEN a   
             WHEN 1 THEN b   
             ELSE c   
          END);  
    ```  
  
> [!NOTE]  
>  <span data-ttu-id="70bc4-145">Любое выражение, которое имеет тип данных `float` или `real`, считается неточным и не может быть ключом индекса; выражения, которые имеют тип `float` или `real`, могут использоваться в индексированном представлении, но не в качестве ключа.</span><span class="sxs-lookup"><span data-stu-id="70bc4-145">Any `float` or `real` expression is considered imprecise and cannot be a key of an index; a `float` or `real` expression can be used in an indexed view but not as a key.</span></span> <span data-ttu-id="70bc4-146">Это верно и для вычисляемых столбцов.</span><span class="sxs-lookup"><span data-stu-id="70bc4-146">This is true also for computed columns.</span></span> <span data-ttu-id="70bc4-147">Любая функция, выражение или определяемая пользователем функция считается неточной, если содержит выражение типа `float` или `real`,</span><span class="sxs-lookup"><span data-stu-id="70bc4-147">Any function, expression, or user-defined function is considered imprecise if it contains any `float` or `real` expressions.</span></span> <span data-ttu-id="70bc4-148">включая логические выражения (сравнения).</span><span class="sxs-lookup"><span data-stu-id="70bc4-148">This includes logical ones (comparisons).</span></span>  
  
 <span data-ttu-id="70bc4-149">Свойство **IsPrecise** функции COLUMNPROPERTY определяет, является ли выражение *computed_column_expression* точным.</span><span class="sxs-lookup"><span data-stu-id="70bc4-149">The **IsPrecise** property of the COLUMNPROPERTY function reports whether a *computed_column_expression* is precise.</span></span>  
  
 <span data-ttu-id="70bc4-150">**Data Type Requirements**</span><span class="sxs-lookup"><span data-stu-id="70bc4-150">**Data Type Requirements**</span></span>  
  
-   <span data-ttu-id="70bc4-151">*Computed_column_expression* , определенные для вычисляемого столбца, не могут оцениваться `text` до `ntext` `image` типов данных, или.</span><span class="sxs-lookup"><span data-stu-id="70bc4-151">The *computed_column_expression* defined for the computed column cannot evaluate to the `text`, `ntext`, or `image` data types.</span></span>  
  
-   <span data-ttu-id="70bc4-152">Вычисляемые столбцы, производные от типов данных `image`, `ntext`, `text`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)` и `xml`, могут индексироваться, если тип данных вычисляемого столбца допускается в качестве ключевого столбца индекса.</span><span class="sxs-lookup"><span data-stu-id="70bc4-152">Computed columns derived from `image`, `ntext`, `text`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)`, and `xml` data types can be indexed as long as the computed column data type is allowable as an index key column.</span></span>  
  
-   <span data-ttu-id="70bc4-153">Вычисляемые столбцы, производные от типов данных `image`, `ntext` и `text`, могут быть неключевыми (включенными) столбцами некластеризованного индекса, если тип данных вычисляемого столбца является допустимым в качестве неключевого индексного столбца.</span><span class="sxs-lookup"><span data-stu-id="70bc4-153">Computed columns derived from `image`, `ntext`, and `text` data types can be nonkey (included) columns in a nonclustered index as long as the computed column data type is allowable as a nonkey index column.</span></span>  
  
 <span data-ttu-id="70bc4-154">**требования к параметру SET.**</span><span class="sxs-lookup"><span data-stu-id="70bc4-154">**SET Option Requirements**</span></span>  
  
-   <span data-ttu-id="70bc4-155">Параметру уровня соединения ANSI_NULLS необходимо присвоить значение ON, если выполняется инструкция CREATE TABLE или ALTER TABLE, определяющая вычисляемый столбец.</span><span class="sxs-lookup"><span data-stu-id="70bc4-155">The ANSI_NULLS connection-level option must be set to ON when the CREATE TABLE or ALTER TABLE statement that defines the computed column is executed.</span></span> <span data-ttu-id="70bc4-156">Функция [OBJECTPROPERTY](/sql/t-sql/functions/objectpropertyex-transact-sql) через свойство **IsAnsiNullsOn** сообщает, включен ли этот параметр.</span><span class="sxs-lookup"><span data-stu-id="70bc4-156">The [OBJECTPROPERTY](/sql/t-sql/functions/objectpropertyex-transact-sql) function reports whether the option is on through the **IsAnsiNullsOn** property.</span></span>  
  
-   <span data-ttu-id="70bc4-157">Соединение, для которого создается индекс, и все соединения, выполняющие инструкции INSERT, UPDATE или DELETE, которые изменяют значения в индексе, должны иметь шесть параметров инструкции SET в значении ON и один параметр в значении OFF.</span><span class="sxs-lookup"><span data-stu-id="70bc4-157">The connection on which the index is created, and all connections trying INSERT, UPDATE, or DELETE statements that will change values in the index, must have six SET options set to ON and one option set to OFF.</span></span> <span data-ttu-id="70bc4-158">Оптимизатор пропускает индекс вычисляемого столбца для любой инструкции SELECT, выполняемой соединением, в котором эти параметры не имеют таких же значений.</span><span class="sxs-lookup"><span data-stu-id="70bc4-158">The optimizer ignores an index on a computed column for any SELECT statement executed by a connection that does not have these same option settings.</span></span>  
  
    -   <span data-ttu-id="70bc4-159">Параметр NUMERIC_ROUNDABORT должен быть установлен в OFF, а следующие параметры должны быть установлены в ON:</span><span class="sxs-lookup"><span data-stu-id="70bc4-159">The NUMERIC_ROUNDABORT option must be set to OFF, and the following options must be set to ON:</span></span>  
  
    -   <span data-ttu-id="70bc4-160">ANSI_NULLS</span><span class="sxs-lookup"><span data-stu-id="70bc4-160">ANSI_NULLS</span></span>  
  
    -   <span data-ttu-id="70bc4-161">ANSI_PADDING</span><span class="sxs-lookup"><span data-stu-id="70bc4-161">ANSI_PADDING</span></span>  
  
    -   <span data-ttu-id="70bc4-162">ANSI_WARNINGS</span><span class="sxs-lookup"><span data-stu-id="70bc4-162">ANSI_WARNINGS</span></span>  
  
    -   <span data-ttu-id="70bc4-163">ARITHABORT</span><span class="sxs-lookup"><span data-stu-id="70bc4-163">ARITHABORT</span></span>  
  
    -   <span data-ttu-id="70bc4-164">CONCAT_NULL_YIELDS_NULL</span><span class="sxs-lookup"><span data-stu-id="70bc4-164">CONCAT_NULL_YIELDS_NULL</span></span>  
  
    -   <span data-ttu-id="70bc4-165">QUOTED_IDENTIFIER</span><span class="sxs-lookup"><span data-stu-id="70bc4-165">QUOTED_IDENTIFIER</span></span>  
  
     <span data-ttu-id="70bc4-166">Если уровень совместимости базы данных равен 90 или более, при установке параметра ANSI_WARNINGS в состояние ON параметр ARITHABORT также устанавливается в состояние ON.</span><span class="sxs-lookup"><span data-stu-id="70bc4-166">Setting ANSI_WARNINGS to ON implicitly sets ARITHABORT to ON when the database compatibility level is set to 90 or higher.</span></span>  
  
##  <a name="creating-indexes-on-persisted-computed-columns"></a><a name="BKMK_persisted"></a> <span data-ttu-id="70bc4-167">Создание индексов материализованных вычисляемых столбцов</span><span class="sxs-lookup"><span data-stu-id="70bc4-167">Creating Indexes on Persisted Computed Columns</span></span>  
 <span data-ttu-id="70bc4-168">Индекс вычисляемого столбца, который определен с помощью детерминированного, но неточного выражения, можно создать, если в инструкции CREATE TABLE или ALTER TABLE этот столбец помечен как PERSISTED.</span><span class="sxs-lookup"><span data-stu-id="70bc4-168">You can create an index on a computed column that is defined with a deterministic, but imprecise, expression if the column is marked PERSISTED in the CREATE TABLE or ALTER TABLE statement.</span></span> <span data-ttu-id="70bc4-169">Это означает, что [!INCLUDE[ssDE](../../../includes/ssde-md.md)] компонент использует эти сохраненные значения при создании индекса для столбца, а также при обращении к индексу в запросе.</span><span class="sxs-lookup"><span data-stu-id="70bc4-169">This means that the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] uses these persisted values when it creates an index on the column, and when the index is referenced in a query.</span></span> <span data-ttu-id="70bc4-170">Этот параметр позволяет создать индекс для вычисляемого столбца [!INCLUDE[ssDE](../../../includes/dnprdnshort-md.md)] , если, является как детерминированным, так и точным.</span><span class="sxs-lookup"><span data-stu-id="70bc4-170">This option enables you to create an index on a computed column when [!INCLUDE[ssDE](../../../includes/dnprdnshort-md.md)], is both deterministic and precise.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="70bc4-171">См. также</span><span class="sxs-lookup"><span data-stu-id="70bc4-171">Related Content</span></span>  
 [<span data-ttu-id="70bc4-172">COLUMNPROPERTY (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="70bc4-172">COLUMNPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/columnproperty-transact-sql)  
  
  
