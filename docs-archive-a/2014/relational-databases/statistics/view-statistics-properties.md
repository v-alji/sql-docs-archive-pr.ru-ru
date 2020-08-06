---
title: Просмотр свойств статистики | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
f1_keywords:
- sql12.swb.statistics.details.f1
helpviewer_keywords:
- viewing statistics properties
- statistics [SQL Server], viewing properties
ms.assetid: 0eaa2101-006e-4015-9979-3468b50e0aaa
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 63cabc5d8844982604993acac6a791317ee36925
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667623"
---
# <a name="view-statistics-properties"></a><span data-ttu-id="01d98-102">Просмотр свойств статистики</span><span class="sxs-lookup"><span data-stu-id="01d98-102">View Statistics Properties</span></span>
  <span data-ttu-id="01d98-103">Статистику оптимизации текущего запроса для таблицы или индексированного представления можно просмотреть в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="01d98-103">You can display current query optimization statistics for a table or indexed view in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="01d98-104">Объекты статистики включают заголовок, содержащий метаданные о статистике, гистограмму, содержащую распределение значений в первом ключевом столбце объекта статистики, и вектор плотностей для измерения корреляции с охватом нескольких столбцов.</span><span class="sxs-lookup"><span data-stu-id="01d98-104">Statistics objects include a header with metadata about the statistics, a histogram with the distribution of values in the first key column of the statistics object, and a density vector to measure cross-column correlation.</span></span> <span data-ttu-id="01d98-105">Дополнительные сведения о гистограммах и векторах плотностей см. в статье [DBCC SHOW_STATISTICS (Transact-SQL)](/sql/t-sql/database-console-commands/dbcc-show-statistics-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="01d98-105">For more information about histograms and density vectors, see [DBCC SHOW_STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-show-statistics-transact-sql)</span></span>  
  
 <span data-ttu-id="01d98-106">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="01d98-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="01d98-107">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="01d98-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="01d98-108">Безопасность</span><span class="sxs-lookup"><span data-stu-id="01d98-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="01d98-109">**Для просмотра свойств статистики используются:**</span><span class="sxs-lookup"><span data-stu-id="01d98-109">**To view statistics properties, using:**</span></span>  
  
     [<span data-ttu-id="01d98-110">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="01d98-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="01d98-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="01d98-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="01d98-112">Перед началом</span><span class="sxs-lookup"><span data-stu-id="01d98-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="01d98-113">безопасность</span><span class="sxs-lookup"><span data-stu-id="01d98-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="01d98-114">Permissions</span><span class="sxs-lookup"><span data-stu-id="01d98-114">Permissions</span></span>  
 <span data-ttu-id="01d98-115">Чтобы просматривать объект статистики, пользователь должен быть владельцем таблицы или членом предопределенной роли сервера `sysadmin`, предопределенной роли базы данных `db_owner` или предопределенной роли базы данных `db_ddladmin`.</span><span class="sxs-lookup"><span data-stu-id="01d98-115">In order to view the statistics object, the user must own the table or the user must be a member of the `sysadmin` fixed server role, the `db_owner` fixed database role, or the `db_ddladmin` fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="01d98-116">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="01d98-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-statistics-properties"></a><span data-ttu-id="01d98-117">Просмотр свойств статистики</span><span class="sxs-lookup"><span data-stu-id="01d98-117">To view statistics properties</span></span>  
  
1.  <span data-ttu-id="01d98-118">В **обозревателе объектов**щелкните значок «плюс», чтобы развернуть базу данных, в которой нужно создать новую статистику.</span><span class="sxs-lookup"><span data-stu-id="01d98-118">In **Object Explorer**, click the plus sign to expand the database in which you want to create a new statistic.</span></span>  
  
2.  <span data-ttu-id="01d98-119">Чтобы развернуть папку **Таблицы** , щелкните значок «плюс».</span><span class="sxs-lookup"><span data-stu-id="01d98-119">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="01d98-120">Щелкните значок плюса, чтобы развернуть таблицу, в которой нужно просмотреть свойства статистики.</span><span class="sxs-lookup"><span data-stu-id="01d98-120">Click the plus sign to expand the table in which you want to view the statistic's properties.</span></span>  
  
4.  <span data-ttu-id="01d98-121">Щелкните значок «плюс», чтобы развернуть папку **Статистика** .</span><span class="sxs-lookup"><span data-stu-id="01d98-121">Click the plus sign to expand the **Statistics** folder.</span></span>  
  
5.  <span data-ttu-id="01d98-122">Щелкните правой кнопкой мыши объект статистики, для которого нужно просмотреть свойства, и выберите команду **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="01d98-122">Right-click the Statistics object of which you want to view the properties and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="01d98-123">В диалоговом окне **Свойства статистики —**  _имя_статистики_ на панели **Выбор страницы** выберите **Сведения**.</span><span class="sxs-lookup"><span data-stu-id="01d98-123">In the **Statistics Properties -** _statistics_name_ dialog box, in the **Select a page** pane, select **Details**.</span></span>  
  
     <span data-ttu-id="01d98-124">На странице **Сведения** в диалоговом окне **Свойства статистики —** _имя_статистики_ отображаются следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="01d98-124">The following properties show on the **Details** page in the **Statistics Properties -** _statistics_name_ dialog box.</span></span>  
  
     <span data-ttu-id="01d98-125">**Имя таблицы**</span><span class="sxs-lookup"><span data-stu-id="01d98-125">**Table Name**</span></span>  
     <span data-ttu-id="01d98-126">Отображает имя таблицы, которую описывает данная статистика.</span><span class="sxs-lookup"><span data-stu-id="01d98-126">Displays the name of the table described by the statistics.</span></span>  
  
     <span data-ttu-id="01d98-127">**Имя статистики**</span><span class="sxs-lookup"><span data-stu-id="01d98-127">**Statistics Name**</span></span>  
     <span data-ttu-id="01d98-128">Отображает имя объекта базы данных, в котором сохранена статистика.</span><span class="sxs-lookup"><span data-stu-id="01d98-128">Displays the name of the database object where the statistics are stored.</span></span>  
  
     <span data-ttu-id="01d98-129">**Статистика для INDEXимя_статистики**</span><span class="sxs-lookup"><span data-stu-id="01d98-129">**Statistics for INDEXstatistics_name**</span></span>  
     <span data-ttu-id="01d98-130">В этом текстовом поле отображаются свойства, возвращенные из объекта статистики.</span><span class="sxs-lookup"><span data-stu-id="01d98-130">This text box shows the properties returned from the statistics object.</span></span> <span data-ttu-id="01d98-131">Эти свойства делятся на три части: заголовок статистики, вектор плотностей и гистограмма.</span><span class="sxs-lookup"><span data-stu-id="01d98-131">This properties are divided into three sections: Stats Header, Density Vector, and Histogram.</span></span>  
  
     <span data-ttu-id="01d98-132">Следующие данные описывают столбцы, возвращенные в результирующем наборе для заголовка статистики.</span><span class="sxs-lookup"><span data-stu-id="01d98-132">The following information describes the columns returned in the result set for the Stats Header.</span></span>  
  
     <span data-ttu-id="01d98-133">**имя**;</span><span class="sxs-lookup"><span data-stu-id="01d98-133">**Name**</span></span>  
     <span data-ttu-id="01d98-134">Имя объекта статистики.</span><span class="sxs-lookup"><span data-stu-id="01d98-134">Name of the statistics object.</span></span>  
  
     <span data-ttu-id="01d98-135">**Обновленные возможности**</span><span class="sxs-lookup"><span data-stu-id="01d98-135">**Updated**</span></span>  
     <span data-ttu-id="01d98-136">Дата и время последнего обновления статистики.</span><span class="sxs-lookup"><span data-stu-id="01d98-136">Date and time the statistics were last updated.</span></span>  
  
     <span data-ttu-id="01d98-137">**Строки**</span><span class="sxs-lookup"><span data-stu-id="01d98-137">**Rows**</span></span>  
     <span data-ttu-id="01d98-138">Общее число строк в таблице или индексированном представлении при последнем обновлении статистики.</span><span class="sxs-lookup"><span data-stu-id="01d98-138">Total number of rows in the table or indexed view when the statistics were last updated.</span></span> <span data-ttu-id="01d98-139">Если статистика отфильтрована или соответствует отфильтрованному индексу, количество строк может быть меньше, чем количество строк в таблице.</span><span class="sxs-lookup"><span data-stu-id="01d98-139">If the statistics are filtered or correspond to a filtered index, the number of rows might be less than the number of rows in the table.</span></span>  
  
     <span data-ttu-id="01d98-140">**Rows Sampled**</span><span class="sxs-lookup"><span data-stu-id="01d98-140">**Rows Sampled**</span></span>  
     <span data-ttu-id="01d98-141">Общее количество строк, выбранных для статистических вычислений.</span><span class="sxs-lookup"><span data-stu-id="01d98-141">Total number of rows sampled for statistics calculations.</span></span> <span data-ttu-id="01d98-142">Если имеет место условие «количество строк выборки < количество строк таблицы», то отображаемые результаты определения гистограммы и вычисления плотности представляют собой оценки, основанные на строках выборки.</span><span class="sxs-lookup"><span data-stu-id="01d98-142">If Rows Sampled < Rows, the displayed histogram and density results are estimates based on the sampled rows.</span></span>  
  
     <span data-ttu-id="01d98-143">**Шаги**</span><span class="sxs-lookup"><span data-stu-id="01d98-143">**Steps**</span></span>  
     <span data-ttu-id="01d98-144">Число шагов в гистограмме.</span><span class="sxs-lookup"><span data-stu-id="01d98-144">Number of steps in the histogram.</span></span> <span data-ttu-id="01d98-145">Каждый шаг охватывает диапазон значений столбцов, за которым следует значение столбца, представляющее собой верхнюю границу.</span><span class="sxs-lookup"><span data-stu-id="01d98-145">Each step spans a range of column values followed by an upper bound column value.</span></span> <span data-ttu-id="01d98-146">Шаги гистограммы определяются в первом ключевом столбце статистики.</span><span class="sxs-lookup"><span data-stu-id="01d98-146">The histogram steps are defined on the first key column in the statistics.</span></span> <span data-ttu-id="01d98-147">Максимальное число шагов — 200.</span><span class="sxs-lookup"><span data-stu-id="01d98-147">The maximum number of steps is 200.</span></span>  
  
     <span data-ttu-id="01d98-148">**Плотность**</span><span class="sxs-lookup"><span data-stu-id="01d98-148">**Density**</span></span>  
     <span data-ttu-id="01d98-149">Рассчитывается как 1 / *различающиеся значения* для всех значений в первом ключевом столбце объекта статистики, исключая возможные значения гистограммы.</span><span class="sxs-lookup"><span data-stu-id="01d98-149">Calculated as 1 / *distinct values* for all values in the first key column of the statistics object, excluding the histogram boundary values.</span></span> <span data-ttu-id="01d98-150">Это значение плотности не используется оптимизатором запросов и отображается для обратной совместимости с версиями, предшествующими SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="01d98-150">This Density value is not used by the query optimizer and is displayed for backward compatibility with versions before SQL Server 2008.</span></span>  
  
     <span data-ttu-id="01d98-151">**Средняя длина ключа**</span><span class="sxs-lookup"><span data-stu-id="01d98-151">**Average Key Length**</span></span>  
     <span data-ttu-id="01d98-152">Среднее число байтов на значение для всех ключевых столбцов в объекте статистики.</span><span class="sxs-lookup"><span data-stu-id="01d98-152">Average number of bytes per value for all of the key columns in the statistics object.</span></span>  
  
     <span data-ttu-id="01d98-153">**String Index**</span><span class="sxs-lookup"><span data-stu-id="01d98-153">**String Index**</span></span>  
     <span data-ttu-id="01d98-154">Значение «Да» указывает, что объект статистики содержит сводную строковую статистику, позволяющую уточнить оценку количества элементов для предикатов запроса, использующих оператор LIKE, например `WHERE ProductName LIKE '%Bike'`.</span><span class="sxs-lookup"><span data-stu-id="01d98-154">Yes indicates the statistics object contains string summary statistics to improve the cardinality estimates for query predicates that use the LIKE operator; for example, `WHERE ProductName LIKE '%Bike'`.</span></span> <span data-ttu-id="01d98-155">Сводная строковая статистика хранится отдельно от гистограммы и создается в первом ключевом столбце объекта статистики, если он имеет тип **char**, **varchar**, **nchar**, **nvarchar**, **varchar(max)** , **nvarchar(max)** , **text**или **ntext**.</span><span class="sxs-lookup"><span data-stu-id="01d98-155">String summary statistics are stored separately from the histogram and are created on the first key column of the statistics object when it is of type **char**, **varchar**, **nchar**, **nvarchar**, **varchar(max)**, **nvarchar(max)**, **text**, or **ntext**.</span></span>  
  
     <span data-ttu-id="01d98-156">**Критерий фильтра**</span><span class="sxs-lookup"><span data-stu-id="01d98-156">**Filter Expression**</span></span>  
     <span data-ttu-id="01d98-157">Предикат для подмножества строк таблицы, включенных в объект статистики.</span><span class="sxs-lookup"><span data-stu-id="01d98-157">Predicate for the subset of table rows included in the statistics object.</span></span> <span data-ttu-id="01d98-158">NULL — неотфильтрованная статистика.</span><span class="sxs-lookup"><span data-stu-id="01d98-158">NULL = non-filtered statistics.</span></span>  
  
     <span data-ttu-id="01d98-159">**Unfiltered Rows**</span><span class="sxs-lookup"><span data-stu-id="01d98-159">**Unfiltered Rows**</span></span>  
     <span data-ttu-id="01d98-160">Общее количество строк в таблице перед применением критерия фильтра.</span><span class="sxs-lookup"><span data-stu-id="01d98-160">Total number of rows in the table before applying the filter expression.</span></span> <span data-ttu-id="01d98-161">Если Filter Expression имеет значение NULL, то столбец Unfiltered Rows совпадает со столбцом Rows.</span><span class="sxs-lookup"><span data-stu-id="01d98-161">If Filter Expression is NULL, Unfiltered Rows is equal to Rows.</span></span>  
  
     <span data-ttu-id="01d98-162">Следующие данные описывают столбцы, возвращенные в результирующем наборе для вектора плотностей.</span><span class="sxs-lookup"><span data-stu-id="01d98-162">The following information describes the columns returned in the result set for the Density Vector.</span></span>  
  
     <span data-ttu-id="01d98-163">**Общая плотность**</span><span class="sxs-lookup"><span data-stu-id="01d98-163">**All Density**</span></span>  
     <span data-ttu-id="01d98-164">Плотность равна 1 / *различающиеся значения*.</span><span class="sxs-lookup"><span data-stu-id="01d98-164">Density is 1 / *distinct values*.</span></span> <span data-ttu-id="01d98-165">В результатах отображаются плотности для каждого префикса столбцов объекта статистики, по одной строке на плотность.</span><span class="sxs-lookup"><span data-stu-id="01d98-165">Results display density for each prefix of columns in the statistics object, one row per density.</span></span> <span data-ttu-id="01d98-166">Различающееся значение — это отдельный список значений столбцов на строку и на префикс столбцов.</span><span class="sxs-lookup"><span data-stu-id="01d98-166">A distinct value is a distinct list of the column values per row and per columns prefix.</span></span> <span data-ttu-id="01d98-167">Например, если объект статистики содержит ключевые столбцы (A, B, C), то в результатах приводится плотность отдельных списков значений в каждом из следующих префиксов столбцов: (A), (A, B) и (A, B, C).</span><span class="sxs-lookup"><span data-stu-id="01d98-167">For example, if the statistics object contains key columns (A, B, C), the results report the density of the distinct lists of values in each of these column prefixes: (A), (A,B), and (A, B, C).</span></span> <span data-ttu-id="01d98-168">При использовании префикса (A, B, C) каждый из этих списков является отдельным списком значений: (3, 5, 6), (4, 4, 6), (4, 5, 6), (4, 5, 7).</span><span class="sxs-lookup"><span data-stu-id="01d98-168">Using the prefix (A, B, C), each of these lists is a distinct value list: (3, 5, 6), (4, 4, 6), (4, 5, 6), (4, 5, 7).</span></span> <span data-ttu-id="01d98-169">При использовании префикса (A, B) одинаковые значения столбцов имеют следующие отдельные списки значений: (3, 5), (4, 4) и (4, 5).</span><span class="sxs-lookup"><span data-stu-id="01d98-169">Using the prefix (A, B) the same column values have these distinct value lists: (3, 5), (4, 4), and (4, 5).</span></span>  
  
     <span data-ttu-id="01d98-170">**Средняя длина**</span><span class="sxs-lookup"><span data-stu-id="01d98-170">**Average Length**</span></span>  
     <span data-ttu-id="01d98-171">Средняя длина (в байтах) для хранения списка значений столбца для данного префикса столбца.</span><span class="sxs-lookup"><span data-stu-id="01d98-171">Average length, in bytes, to store a list of the column values for the column prefix.</span></span> <span data-ttu-id="01d98-172">Если каждому значению в списке (3, 5, 6), например, требуется по 4 байта, то длина составляет 12 байт.</span><span class="sxs-lookup"><span data-stu-id="01d98-172">For example, if the values in the list (3, 5, 6) each require 4 bytes the length is 12 bytes.</span></span>  
  
     <span data-ttu-id="01d98-173">**Столбцы**</span><span class="sxs-lookup"><span data-stu-id="01d98-173">**Columns**</span></span>  
     <span data-ttu-id="01d98-174">Имена столбцов в префиксе, для которых отображаются значения «Общая плотность» и «Средняя длина».</span><span class="sxs-lookup"><span data-stu-id="01d98-174">Names of columns in the prefix for which All density and Average length are displayed.</span></span>  
  
     <span data-ttu-id="01d98-175">Следующие данные описывают столбцы, возвращенные в результирующем наборе для гистограммы.</span><span class="sxs-lookup"><span data-stu-id="01d98-175">The following information describes the columns returned in the result set for the Histogram.</span></span>  
  
     <span data-ttu-id="01d98-176">**RANGE_HI_KEY**</span><span class="sxs-lookup"><span data-stu-id="01d98-176">**RANGE_HI_KEY**</span></span>  
     <span data-ttu-id="01d98-177">Верхнее граничное значение столбца для шага гистограммы.</span><span class="sxs-lookup"><span data-stu-id="01d98-177">Upper bound column value for a histogram step.</span></span> <span data-ttu-id="01d98-178">Это значение столбца называется также ключевым значением.</span><span class="sxs-lookup"><span data-stu-id="01d98-178">The column value is also called a key value.</span></span>  
  
     <span data-ttu-id="01d98-179">**RANGE_ROWS**</span><span class="sxs-lookup"><span data-stu-id="01d98-179">**RANGE_ROWS**</span></span>  
     <span data-ttu-id="01d98-180">Предполагаемое количество строк, значение столбцов которых находится в пределах шага гистограммы, исключая верхнюю границу.</span><span class="sxs-lookup"><span data-stu-id="01d98-180">Estimated number of rows whose column value falls within a histogram step, excluding the upper bound.</span></span>  
  
     <span data-ttu-id="01d98-181">**EQ_ROWS**</span><span class="sxs-lookup"><span data-stu-id="01d98-181">**EQ_ROWS**</span></span>  
     <span data-ttu-id="01d98-182">Предполагаемое количество строк, значение столбцов которых равно верхней границе шага гистограммы.</span><span class="sxs-lookup"><span data-stu-id="01d98-182">Estimated number of rows whose column value equals the upper bound of the histogram step.</span></span>  
  
     <span data-ttu-id="01d98-183">**DISTINCT_RANGE_ROWS**</span><span class="sxs-lookup"><span data-stu-id="01d98-183">**DISTINCT_RANGE_ROWS**</span></span>  
     <span data-ttu-id="01d98-184">Предполагаемое количество строк с различающимся значением столбца в пределах шага гистограммы, исключая верхнюю границу.</span><span class="sxs-lookup"><span data-stu-id="01d98-184">Estimated number of rows with a distinct column value within a histogram step, excluding the upper bound.</span></span>  
  
     <span data-ttu-id="01d98-185">**AVG_RANGE_ROWS**</span><span class="sxs-lookup"><span data-stu-id="01d98-185">**AVG_RANGE_ROWS**</span></span>  
     <span data-ttu-id="01d98-186">Среднее количество строк с повторяющимися значениями столбцов в пределах шага гистограммы, исключая верхнюю границу (RANGE_ROWS/DISTINCT_RANGE_ROWS для DISTINCT_RANGE_ROWS > 0).</span><span class="sxs-lookup"><span data-stu-id="01d98-186">Average number of rows with duplicate column values within a histogram step, excluding the upper bound (RANGE_ROWS / DISTINCT_RANGE_ROWS for DISTINCT_RANGE_ROWS > 0).</span></span>  
  
7.  <span data-ttu-id="01d98-187">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="01d98-187">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="01d98-188">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="01d98-188">Using Transact-SQL</span></span>  
  
#### <a name="to-view-statistics-properties"></a><span data-ttu-id="01d98-189">Просмотр свойств статистики</span><span class="sxs-lookup"><span data-stu-id="01d98-189">To view statistics properties</span></span>  
  
1.  <span data-ttu-id="01d98-190">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="01d98-190">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="01d98-191">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="01d98-191">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="01d98-192">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="01d98-192">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- The following example displays all statistics information for the AK_Address_rowguid index of the Person.Address table.   
    DBCC SHOW_STATISTICS ("Person.Address", AK_Address_rowguid);   
    GO  
    ```  
  
 <span data-ttu-id="01d98-193">Дополнительные сведения см. в статье [DBCC SHOW_STATISTICS (Transact-SQL)](/sql/t-sql/database-console-commands/dbcc-show-statistics-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="01d98-193">For more information, see [DBCC SHOW_STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-show-statistics-transact-sql).</span></span>  
  
#### <a name="to-find-all-of-the-statistics-on-a-table-or-view"></a><span data-ttu-id="01d98-194">Поиск всех статистических данных по таблице или представлению</span><span class="sxs-lookup"><span data-stu-id="01d98-194">To find all of the statistics on a table or view</span></span>  
  
1.  <span data-ttu-id="01d98-195">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="01d98-195">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="01d98-196">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="01d98-196">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="01d98-197">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="01d98-197">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    /*Gets the following information: name and ID of the statistics, whether the statistics were created automatically or by the user, whether the statistics were created with the NORECOMPUTE option, and whether the statistics have a filter and, if so, what that filter is.  
    */  
    SELECT name AS statistics_name  
        ,stats_id  
        ,auto_created  
        ,user_created  
        ,no_recompute  
        ,has_filter  
        ,filter_definition  
    -- using the sys.stats catalog view  
    FROM sys.stats  
    -- for the Sales.SpecialOffer table  
    WHERE object_id = OBJECT_ID('Sales.SpecialOffer');  
    GO  
    ```  
  
 <span data-ttu-id="01d98-198">Дополнительные сведения см. в статье [sys.stats (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-stats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="01d98-198">For more information, see [sys.stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-stats-transact-sql).</span></span>  
  
  
