---
title: Основные сведения о схемах баз данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Schema Generation Wizard, database schema
- database schema [Analysis Services]
- relational schema [Analysis Services], database schema
- subject area schema options [Analysis Services]
- staging area schema options [Analysis Services]
- denormalized schemas
ms.assetid: 51e411f9-ee3f-4b92-9833-c2bce8c6b752
author: minewiskan
ms.author: owend
ms.openlocfilehash: 84f44db1b7abca1b8cad45cf5f46fcc0006bd92a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732093"
---
# <a name="understanding-the-database-schemas"></a><span data-ttu-id="b5fd6-102">Основные сведения о схемах баз данных</span><span class="sxs-lookup"><span data-stu-id="b5fd6-102">Understanding the Database Schemas</span></span>
  <span data-ttu-id="b5fd6-103">Мастер формирования схем создает ненормализованную реляционную схему для предметной области базы данных на основе измерений и групп мер служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b5fd6-103">The Schema Generation Wizard generates a denormalized relational schema for the subject area database based on the dimensions and measure groups in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="b5fd6-104">Мастер создает реляционную таблицу для каждого измерения (таблица измерения), в которой хранятся данные измерений, которую называют таблицей измерения, и реляционную таблицу для каждой группы мер (таблица фактов), в которой хранятся данные фактов.</span><span class="sxs-lookup"><span data-stu-id="b5fd6-104">The wizard generates a relational table for each dimension to store dimension data, which is called a dimension table, and a relational table for each measure group to store fact data, which is called a fact table.</span></span> <span data-ttu-id="b5fd6-105">При создании реляционных таблиц мастер игнорирует связанные измерения, связанные группы мер и серверные измерения времени.</span><span class="sxs-lookup"><span data-stu-id="b5fd6-105">The wizard ignores linked dimensions, linked measure groups, and server time dimensions when it generates these relational tables.</span></span>  
  
## <a name="validation"></a><span data-ttu-id="b5fd6-106">Проверка</span><span class="sxs-lookup"><span data-stu-id="b5fd6-106">Validation</span></span>  
 <span data-ttu-id="b5fd6-107">Перед созданием базовой реляционной схемы мастер формирования схем проверяет кубы служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] и измерения.</span><span class="sxs-lookup"><span data-stu-id="b5fd6-107">Before it begins to generate the underlying relational schema, the Schema Generation Wizard validates the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] cubes and dimensions.</span></span> <span data-ttu-id="b5fd6-108">При обнаружении ошибок выполнение мастера останавливается, и выводится отчет об ошибках в окне «Список задач» в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b5fd6-108">If the wizard detects errors, it stops and reports the errors to the Task List window in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="b5fd6-109">Примеры ошибок, приводящих к остановке формирования:</span><span class="sxs-lookup"><span data-stu-id="b5fd6-109">Examples of errors that prevent generation include the following:</span></span>  
  
-   <span data-ttu-id="b5fd6-110">измерения, имеющие более одного ключевого атрибута;</span><span class="sxs-lookup"><span data-stu-id="b5fd6-110">Dimensions that have more than one key attribute.</span></span>  
  
-   <span data-ttu-id="b5fd6-111">родительские атрибуты, типы данных которых отличаются от ключевых атрибутов;</span><span class="sxs-lookup"><span data-stu-id="b5fd6-111">Parent attributes that have different data types than the key attributes.</span></span>  
  
-   <span data-ttu-id="b5fd6-112">группы мер, которые не содержат мер;</span><span class="sxs-lookup"><span data-stu-id="b5fd6-112">Measure groups that do not have measures.</span></span>  
  
-   <span data-ttu-id="b5fd6-113">неправильно сконфигурированные вырожденные измерения или меры;</span><span class="sxs-lookup"><span data-stu-id="b5fd6-113">Degenerate dimensions or measures that are improperly configured.</span></span>  
  
-   <span data-ttu-id="b5fd6-114">неправильно сконфигурированные суррогатные ключи, например: несколько атрибутов используют тип атрибута `ScdOriginalID` или атрибут использует тип `ScdOriginalID`, не связанный со столбцом с целочисленным типом данных.</span><span class="sxs-lookup"><span data-stu-id="b5fd6-114">Surrogate keys that are improperly configured, such as multiple attributes using the `ScdOriginalID` attribute type or an attribute using the `ScdOriginalID` that is not bound to a column using the integer data type.</span></span>  
  
## <a name="dimension-tables"></a><span data-ttu-id="b5fd6-115">Таблицы измерений</span><span class="sxs-lookup"><span data-stu-id="b5fd6-115">Dimension Tables</span></span>  
 <span data-ttu-id="b5fd6-116">Мастер формирования схем создает для каждого измерения таблицу, которая включается в предметную область базы данных.</span><span class="sxs-lookup"><span data-stu-id="b5fd6-116">For each dimension, the Schema Generation Wizard generates a dimension table to be included in the subject area database.</span></span> <span data-ttu-id="b5fd6-117">Структура таблицы измерения зависит от выборов, сделанных во время проектирования измерения, на котором основана таблица.</span><span class="sxs-lookup"><span data-stu-id="b5fd6-117">The structure of the dimension table depends on the choices made while designing the dimension on which it is based.</span></span>  
  
 <span data-ttu-id="b5fd6-118">Столбцы</span><span class="sxs-lookup"><span data-stu-id="b5fd6-118">Columns</span></span>  
 <span data-ttu-id="b5fd6-119">Мастер формирует один столбец для привязок, связанных с каждым атрибутом в измерении, на котором основана таблица, например привязок для свойств `KeyColumns`, `NameColumn`, `ValueColumn`, `CustomRollupColumn`, `CustomRollupPropertiesColumn` и `UnaryOperatorColumn` каждого атрибута.</span><span class="sxs-lookup"><span data-stu-id="b5fd6-119">The wizard generates one column for the bindings associated to each attribute in the dimension on which the dimension table is based, such as the bindings for the `KeyColumns`, `NameColumn`, `ValueColumn`, `CustomRollupColumn`, `CustomRollupPropertiesColumn`, and `UnaryOperatorColumn` properties of each attribute.</span></span>  
  
 <span data-ttu-id="b5fd6-120">Отношения</span><span class="sxs-lookup"><span data-stu-id="b5fd6-120">Relationships</span></span>  
 <span data-ttu-id="b5fd6-121">Мастер формирует связи между столбцом для каждого родительского атрибута и первичным ключом таблицы измерения.</span><span class="sxs-lookup"><span data-stu-id="b5fd6-121">The wizard generates a relationship between the column for each parent attribute and the primary key of the dimension table.</span></span>  
  
 <span data-ttu-id="b5fd6-122">Мастер также формирует связь с первичным ключом во всех имеющихся дополнительных таблицах измерений, определенных как ссылочное измерение в кубе.</span><span class="sxs-lookup"><span data-stu-id="b5fd6-122">The wizard also generates a relationship to the primary key in each additional dimension table defined as a referenced dimension in the cube, if applicable.</span></span>  
  
 <span data-ttu-id="b5fd6-123">Ограничения</span><span class="sxs-lookup"><span data-stu-id="b5fd6-123">Constraints</span></span>  
 <span data-ttu-id="b5fd6-124">По умолчанию мастер формирует ограничение первичного ключа для каждой таблицы измерения, основанное на ключевом атрибуте измерения.</span><span class="sxs-lookup"><span data-stu-id="b5fd6-124">The wizard generates a primary key constraint, by default, for each dimension table based on the key attribute of the dimension.</span></span> <span data-ttu-id="b5fd6-125">При создании ограничения первичного ключа по умолчанию формируется отдельный столбец имен.</span><span class="sxs-lookup"><span data-stu-id="b5fd6-125">If the primary key constraint is generated, a separate name column is generated by default.</span></span> <span data-ttu-id="b5fd6-126">Если первичный ключ в базе данных решено не создавать, то в представлении источника данных создается логический первичный ключ.</span><span class="sxs-lookup"><span data-stu-id="b5fd6-126">A logical primary key is created in the data source view even if you decide not to create the primary key in the database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b5fd6-127">Если в измерении, на котором основана таблица измерения, имеется несколько ключевых атрибутов, то возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="b5fd6-127">An error occurs if more than one key attribute is specified in the dimension on which the dimension table is based.</span></span>  
  
 <span data-ttu-id="b5fd6-128">Translations</span><span class="sxs-lookup"><span data-stu-id="b5fd6-128">Translations</span></span>  
 <span data-ttu-id="b5fd6-129">Мастер формирует отдельную таблицу для переведенных значений любого атрибута, для которого требуется столбец перевода.</span><span class="sxs-lookup"><span data-stu-id="b5fd6-129">The wizard generates a separate table to hold the translated values for any attribute that requires a translation column.</span></span> <span data-ttu-id="b5fd6-130">Мастер также создает отдельный столбец для каждого из требуемых языков.</span><span class="sxs-lookup"><span data-stu-id="b5fd6-130">The wizard also creates a separate column for each of the required languages.</span></span>  
  
## <a name="fact-tables"></a><span data-ttu-id="b5fd6-131">Таблицы фактов</span><span class="sxs-lookup"><span data-stu-id="b5fd6-131">Fact Tables</span></span>  
 <span data-ttu-id="b5fd6-132">Для каждой группы мер в кубе мастер формирования схем формирует таблицу фактов, которая включается в предметную область базы данных.</span><span class="sxs-lookup"><span data-stu-id="b5fd6-132">For each measure group in a cube, the Schema Generation Wizard generates a fact table to be included in the subject area database.</span></span> <span data-ttu-id="b5fd6-133">Структура таблицы фактов зависит от параметров, заданных при разработке группы мер, на которых основана таблица, и связей, определенных между группой мер и любыми включенными измерениями.</span><span class="sxs-lookup"><span data-stu-id="b5fd6-133">The structure of the fact table depends on the choices made while designing the measure group on which it is based, and the relationships established between the measure group and any included dimensions.</span></span>  
  
 <span data-ttu-id="b5fd6-134">Столбцы</span><span class="sxs-lookup"><span data-stu-id="b5fd6-134">Columns</span></span>  
 <span data-ttu-id="b5fd6-135">Мастер формирует по одному столбцу для всех мер, за исключением мер, использующих статистическую функцию `Count`.</span><span class="sxs-lookup"><span data-stu-id="b5fd6-135">The wizard generates one column for each measure, except for measures that use the `Count` aggregation function.</span></span> <span data-ttu-id="b5fd6-136">Для таких мер соответствующий столбец в таблице фактов не требуется.</span><span class="sxs-lookup"><span data-stu-id="b5fd6-136">Such measures do not require a corresponding column in the fact table.</span></span>  
  
 <span data-ttu-id="b5fd6-137">Мастер также формирует по одному столбцу для всех столбцов атрибута гранулярности каждой обычной связи измерений в группе мер, а также по одному или несколько столбцов для привязок, связанных с каждым атрибутом измерения, имеющим фактическую связь измерений с группой мер, на которой основана таблица.</span><span class="sxs-lookup"><span data-stu-id="b5fd6-137">The wizard also generates one column for each granularity attribute column of each regular dimension relationship on the measure group, and one or more columns for the bindings associated to each attribute of a dimension that has a fact dimension relationship to the measure group on which this table is based, if applicable.</span></span>  
  
 <span data-ttu-id="b5fd6-138">Отношения</span><span class="sxs-lookup"><span data-stu-id="b5fd6-138">Relationships</span></span>  
 <span data-ttu-id="b5fd6-139">Мастер формирует по одной связи для всех обычных связей измерений из таблицы фактов с атрибутом гранулярности таблицы измерения.</span><span class="sxs-lookup"><span data-stu-id="b5fd6-139">The wizard generates one relationship for each regular dimension relationship from the fact table to the dimension table's granularity attribute.</span></span> <span data-ttu-id="b5fd6-140">Если гранулярность основана на ключевом атрибуте таблицы измерения, то связь создается в базе данных и в представлении источника данных.</span><span class="sxs-lookup"><span data-stu-id="b5fd6-140">If the granularity is based on the key attribute of the dimension table, the relationship is created in the database and in the data source view.</span></span> <span data-ttu-id="b5fd6-141">Если гранулярность основана на другом атрибуте, то связь создается только в представлении источника данных.</span><span class="sxs-lookup"><span data-stu-id="b5fd6-141">If the granularity is based on another attribute, the relationship is created only in the data source view.</span></span>  
  
 <span data-ttu-id="b5fd6-142">Если в мастере выбрано создание индексов, то для каждого из этих столбцов связи создается некластеризованный индекс.</span><span class="sxs-lookup"><span data-stu-id="b5fd6-142">If you chose to generate indexes in the wizard, a nonclustered index is generated for each of these relationship columns.</span></span>  
  
 <span data-ttu-id="b5fd6-143">Ограничения</span><span class="sxs-lookup"><span data-stu-id="b5fd6-143">Constraints</span></span>  
 <span data-ttu-id="b5fd6-144">Первичные ключи в таблицах фактов не формируются.</span><span class="sxs-lookup"><span data-stu-id="b5fd6-144">Primary keys are not generated on fact tables.</span></span>  
  
 <span data-ttu-id="b5fd6-145">Если выбрано задание ссылочной целостности, то между таблицами измерений и таблицами фактов создаются ограничения ссылочной целостности.</span><span class="sxs-lookup"><span data-stu-id="b5fd6-145">If you chose to enforce referential integrity, referential integrity constraints are generated between dimension tables and fact tables where applicable.</span></span>  
  
 <span data-ttu-id="b5fd6-146">Translations</span><span class="sxs-lookup"><span data-stu-id="b5fd6-146">Translations</span></span>  
 <span data-ttu-id="b5fd6-147">Мастер формирует отдельную таблицу для переведенных значений любого свойства в группе мер, для которого требуется столбец перевода.</span><span class="sxs-lookup"><span data-stu-id="b5fd6-147">The wizard generates a separate table to hold the translated values for any property in the measure group that requires a translation column.</span></span> <span data-ttu-id="b5fd6-148">Мастер также создает отдельный столбец для каждого из требуемых языков.</span><span class="sxs-lookup"><span data-stu-id="b5fd6-148">The wizard also creates a separate column for each of the required languages.</span></span>  
  
## <a name="data-type-conversion-and-default-lengths"></a><span data-ttu-id="b5fd6-149">Конвертация типов данных и длины по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b5fd6-149">Data Type Conversion and Default Lengths</span></span>  
 <span data-ttu-id="b5fd6-150">Мастер формирования схем игнорирует типы данных во всех случаях, за исключением столбцов, использующих [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `wchar` тип данных.</span><span class="sxs-lookup"><span data-stu-id="b5fd6-150">Schema Generation Wizard ignores data types in all cases except for columns that use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `wchar` data type.</span></span> <span data-ttu-id="b5fd6-151">Размер данных `wchar` преобразуется непосредственно в тип данных `nvarchar`.</span><span class="sxs-lookup"><span data-stu-id="b5fd6-151">The `wchar` data size translates directly to the `nvarchar` data type.</span></span> <span data-ttu-id="b5fd6-152">Если заданная длина столбца, использующего размер `wchar`, превышает 4 000 байт, то мастер формирования схем формирует ошибку.</span><span class="sxs-lookup"><span data-stu-id="b5fd6-152">However, if the specified length of a column using the `wchar` size is larger than 4000 bytes, the Schema Generation Wizard generates an error.</span></span>  
  
 <span data-ttu-id="b5fd6-153">Если элемент данных, например привязка атрибута, не имеет заданной длины, то в столбце используется одно из значений длины по умолчанию, перечисленных в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="b5fd6-153">If a data item, such as the binding for an attribute, has no specified length, the default length listed in the following table is used for the column.</span></span>  
  
|<span data-ttu-id="b5fd6-154">Элемент данных</span><span class="sxs-lookup"><span data-stu-id="b5fd6-154">Data item</span></span>|<span data-ttu-id="b5fd6-155">Длина по умолчанию (в байтах)</span><span class="sxs-lookup"><span data-stu-id="b5fd6-155">Default length (bytes)</span></span>|  
|---------------|------------------------------|  
|<span data-ttu-id="b5fd6-156">KeyColumn</span><span class="sxs-lookup"><span data-stu-id="b5fd6-156">KeyColumn</span></span>|<span data-ttu-id="b5fd6-157">50</span><span class="sxs-lookup"><span data-stu-id="b5fd6-157">50</span></span>|  
|<span data-ttu-id="b5fd6-158">NameColumn</span><span class="sxs-lookup"><span data-stu-id="b5fd6-158">NameColumn</span></span>|<span data-ttu-id="b5fd6-159">50</span><span class="sxs-lookup"><span data-stu-id="b5fd6-159">50</span></span>|  
|<span data-ttu-id="b5fd6-160">CustomRollupColumn</span><span class="sxs-lookup"><span data-stu-id="b5fd6-160">CustomRollupColumn</span></span>|<span data-ttu-id="b5fd6-161">3000</span><span class="sxs-lookup"><span data-stu-id="b5fd6-161">3000</span></span>|  
|<span data-ttu-id="b5fd6-162">CustomRollupPropertiesColumn</span><span class="sxs-lookup"><span data-stu-id="b5fd6-162">CustomRollupPropertiesColumn</span></span>|<span data-ttu-id="b5fd6-163">500</span><span class="sxs-lookup"><span data-stu-id="b5fd6-163">500</span></span>|  
|<span data-ttu-id="b5fd6-164">UnaryOperatorColumn</span><span class="sxs-lookup"><span data-stu-id="b5fd6-164">UnaryOperatorColumn</span></span>|<span data-ttu-id="b5fd6-165">1</span><span class="sxs-lookup"><span data-stu-id="b5fd6-165">1</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b5fd6-166">См. также:</span><span class="sxs-lookup"><span data-stu-id="b5fd6-166">See Also</span></span>  
 <span data-ttu-id="b5fd6-167">[Основные сведения о добавочном создании](understanding-incremental-generation.md) </span><span class="sxs-lookup"><span data-stu-id="b5fd6-167">[Understanding Incremental Generation](understanding-incremental-generation.md) </span></span>  
 [<span data-ttu-id="b5fd6-168">Управление изменениями в источниках данных и представлениях источников данных</span><span class="sxs-lookup"><span data-stu-id="b5fd6-168">Manage Changes to Data Source Views and Data Sources</span></span>](manage-changes-to-data-source-views-and-data-sources.md)  
  
  
