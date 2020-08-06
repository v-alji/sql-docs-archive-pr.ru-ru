---
title: Свойства запроса (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdtsql.chm:69636
- vdt.ppg.querydesigner.query
ms.assetid: 07495669-6ed5-4004-904e-aae1230be5e4
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6e3c8adfb50e15113228afe8b48218f341f19084
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730001"
---
# <a name="query-properties-visual-database-tools"></a><span data-ttu-id="85d96-102">Свойства запроса (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="85d96-102">Query Properties (Visual Database Tools)</span></span>
  <span data-ttu-id="85d96-103">Эти свойства отображаются в окне «Свойства» при открытии запроса в конструкторе запросов и представлений.</span><span class="sxs-lookup"><span data-stu-id="85d96-103">These properties appear in the Properties window when you have a query open in Query and View Designer.</span></span> <span data-ttu-id="85d96-104">Если не оговорено обратное, эти свойства можно изменять в окне «Свойства».</span><span class="sxs-lookup"><span data-stu-id="85d96-104">Unless otherwise noted, you can edit these properties in the Properties window.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="85d96-105">Свойства в данном разделе группируются по категориям, а не по алфавиту.</span><span class="sxs-lookup"><span data-stu-id="85d96-105">The properties in this topic are ordered by category, rather than alphabetically.</span></span>  
  
## <a name="options"></a><span data-ttu-id="85d96-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="85d96-106">Options</span></span>  
 <span data-ttu-id="85d96-107">**Категория «Идентификатор»**</span><span class="sxs-lookup"><span data-stu-id="85d96-107">**Identity Category**</span></span>  
 <span data-ttu-id="85d96-108">Разверните для отображения свойства **Имя** .</span><span class="sxs-lookup"><span data-stu-id="85d96-108">Expand to show the **Name** property.</span></span>  
  
 <span data-ttu-id="85d96-109">**Название**</span><span class="sxs-lookup"><span data-stu-id="85d96-109">**Name**</span></span>  
 <span data-ttu-id="85d96-110">Показывает имя текущего запроса.</span><span class="sxs-lookup"><span data-stu-id="85d96-110">Shows the name of the current query.</span></span> <span data-ttu-id="85d96-111">Нельзя изменить в среде [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="85d96-111">Cannot be changed in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
 <span data-ttu-id="85d96-112">**Имя базы данных**</span><span class="sxs-lookup"><span data-stu-id="85d96-112">**Database Name**</span></span>  
 <span data-ttu-id="85d96-113">Отображает имя источника данных для выбранной таблицы.</span><span class="sxs-lookup"><span data-stu-id="85d96-113">Shows the name of the data source for the selected table.</span></span>  
  
 <span data-ttu-id="85d96-114">**Имя сервера**</span><span class="sxs-lookup"><span data-stu-id="85d96-114">**Server Name**</span></span>  
 <span data-ttu-id="85d96-115">Показывает имя сервера для источника данных.</span><span class="sxs-lookup"><span data-stu-id="85d96-115">Shows the name of the server for the data source.</span></span>  
  
 <span data-ttu-id="85d96-116">**Категория конструктора запросов**</span><span class="sxs-lookup"><span data-stu-id="85d96-116">**Query Designer Category**</span></span>  
 <span data-ttu-id="85d96-117">Увеличивается для отображения остающихся свойств.</span><span class="sxs-lookup"><span data-stu-id="85d96-117">Expands to show the remaining properties.</span></span>  
  
 <span data-ttu-id="85d96-118">**Целевая таблица**</span><span class="sxs-lookup"><span data-stu-id="85d96-118">**Destination table**</span></span>  
 <span data-ttu-id="85d96-119">Укажите имя таблицы, в которую вставляются данные.</span><span class="sxs-lookup"><span data-stu-id="85d96-119">Specify the name of the table into which you are inserting data.</span></span> <span data-ttu-id="85d96-120">Этот список появляется при создании запроса INSERT или MAKE TABLE.</span><span class="sxs-lookup"><span data-stu-id="85d96-120">This list appears if you are creating an INSERT query or MAKE TABLE query.</span></span> <span data-ttu-id="85d96-121">Для запроса INSERT выберите имя таблицы из данного списка.</span><span class="sxs-lookup"><span data-stu-id="85d96-121">For an INSERT query, select a table name from the list.</span></span>  
  
 <span data-ttu-id="85d96-122">Для запроса MAKE TABLE введите имя новой таблицы.</span><span class="sxs-lookup"><span data-stu-id="85d96-122">For a MAKE TABLE query, type the name of the new table.</span></span> <span data-ttu-id="85d96-123">Для создания целевой таблицы в другом источнике данных укажите полное имя таблицы, включающее имя целевого источника данных, владельца (если требуется) и имя таблицы.</span><span class="sxs-lookup"><span data-stu-id="85d96-123">To create a destination table in another data source, specify a fully qualified table name, including the name of the target data source, the owner (if required), and the name of the table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="85d96-124">Конструктор запросов не проверяет, используется ли уже такое имя и имеются ли разрешения на создание этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="85d96-124">Query Designer does not check whether the name is already in use or whether you have permission to create the table.</span></span>  
  
 <span data-ttu-id="85d96-125">**Различные значения**</span><span class="sxs-lookup"><span data-stu-id="85d96-125">**Distinct values**</span></span>  
 <span data-ttu-id="85d96-126">Указывает, что запрос будет отфильтровывать повторения в результирующем наборе.</span><span class="sxs-lookup"><span data-stu-id="85d96-126">Specify that the query will filter out duplicates in the result set.</span></span> <span data-ttu-id="85d96-127">Этот параметр полезен при использовании только некоторых столбцов из таблицы или нескольких таблиц, а эти столбцы могут содержать повторяющиеся значения или когда обработка соединения двух или более таблиц приводит к повторяющимся строкам в результирующем наборе.</span><span class="sxs-lookup"><span data-stu-id="85d96-127">This option is useful when you are using only some of the columns from the table or tables and those columns might contain duplicate values, or when the process of joining two or more tables produces duplicate rows in the result set.</span></span> <span data-ttu-id="85d96-128">Выбор этого параметра эквивалентен вставке слова DISTINCT в данную инструкцию на панели SQL.</span><span class="sxs-lookup"><span data-stu-id="85d96-128">Choosing this option is equivalent to inserting the word DISTINCT into the statement in the SQL pane.</span></span>  
  
 <span data-ttu-id="85d96-129">**Расширение GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="85d96-129">**GROUP BY Extension**</span></span>  
 <span data-ttu-id="85d96-130">Указывает, что доступны дополнительные параметры запросов, основанные на статистических запросах.</span><span class="sxs-lookup"><span data-stu-id="85d96-130">Specify that additional options for queries based on aggregate queries are available.</span></span> <span data-ttu-id="85d96-131">(Относится только к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].)</span><span class="sxs-lookup"><span data-stu-id="85d96-131">(Applies only to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].)</span></span>  
  
 <span data-ttu-id="85d96-132">**Выводить все столбцы**</span><span class="sxs-lookup"><span data-stu-id="85d96-132">**Output All Columns**</span></span>  
 <span data-ttu-id="85d96-133">Указывает, что все столбцы из всех таблиц в текущем запросе будут включены в результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="85d96-133">Specify that all columns from all tables in the current query will be in the result set.</span></span> <span data-ttu-id="85d96-134">Выбор этого параметра эквивалентен указанию звездочки (\*) вместо имен отдельных столбцов после ключевого слова SELECT в инструкции SQL.</span><span class="sxs-lookup"><span data-stu-id="85d96-134">Choosing this option is equivalent to specifying an asterisk (\*) in place of individual column names after the SELECT keyword in the SQL statement.</span></span>  
  
 <span data-ttu-id="85d96-135">**Список параметров запроса**</span><span class="sxs-lookup"><span data-stu-id="85d96-135">**Query Parameter List**</span></span>  
 <span data-ttu-id="85d96-136">Выводит параметры запроса.</span><span class="sxs-lookup"><span data-stu-id="85d96-136">Shows query parameters.</span></span> <span data-ttu-id="85d96-137">Для изменения этих параметров щелкните это свойство, а затем нажмите кнопку с многоточием **(…)** справа от него.</span><span class="sxs-lookup"><span data-stu-id="85d96-137">To edit the parameters click the property and then click the ellipses **(...)** to the right of the property.</span></span> <span data-ttu-id="85d96-138">(Относится только к общим OLE DB.)</span><span class="sxs-lookup"><span data-stu-id="85d96-138">(Applies only to generic OLE DB.)</span></span>  
  
 <span data-ttu-id="85d96-139">**Комментарий SQL**</span><span class="sxs-lookup"><span data-stu-id="85d96-139">**SQL Comment**</span></span>  
 <span data-ttu-id="85d96-140">Показывает описание инструкций SQL.</span><span class="sxs-lookup"><span data-stu-id="85d96-140">Shows a description of the SQL statements.</span></span> <span data-ttu-id="85d96-141">Чтобы просмотреть или отредактировать описание целиком, щелкните его, а затем нажмите кнопку с многоточием **(...)** справа от свойства.</span><span class="sxs-lookup"><span data-stu-id="85d96-141">To see the entire description or to edit it, click the description and then click the ellipses **(...)** to the right of the property.</span></span> <span data-ttu-id="85d96-142">Комментарии могут содержать, например, сведения о том, кто использует этот запрос и когда он применяется.</span><span class="sxs-lookup"><span data-stu-id="85d96-142">Your comments can include information such as who uses the query and when they use it.</span></span> <span data-ttu-id="85d96-143">(Применимо только для баз данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] версии 7.0 либо более поздней версии.)</span><span class="sxs-lookup"><span data-stu-id="85d96-143">(Applies only to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 7.0 databases or later.)</span></span>  
  
 <span data-ttu-id="85d96-144">**Высшая категория спецификации**</span><span class="sxs-lookup"><span data-stu-id="85d96-144">**Top Specification Category**</span></span>  
 <span data-ttu-id="85d96-145">Разверните для просмотра свойств **Верх**, **Процент**, **Выражение**и **Со связями** .</span><span class="sxs-lookup"><span data-stu-id="85d96-145">Expand to show properties for the **Top**, **Percent**, **Expression**, and **With Ties** properties.</span></span>  
  
 <span data-ttu-id="85d96-146">**(Верх)**</span><span class="sxs-lookup"><span data-stu-id="85d96-146">**(Top)**</span></span>  
 <span data-ttu-id="85d96-147">Указывает, что запрос будет иметь предложение TOP, возвращающее только первые *n* строк или первые *n* процентов строк из результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="85d96-147">Specify hat the query will include a TOP clause, which returns only the first *n* rows or first *n* percentage of rows in the result set.</span></span> <span data-ttu-id="85d96-148">По умолчанию запрос возвращает первые 10 строк из результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="85d96-148">The default is that the query returns the first 10 rows in the result set.</span></span>  
  
 <span data-ttu-id="85d96-149">Это поле позволяет изменить число возвращаемых строк или указать другой процент.</span><span class="sxs-lookup"><span data-stu-id="85d96-149">Use this box to change the number of rows to return or to specify a different percentage.</span></span> <span data-ttu-id="85d96-150">(Относится только к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и более поздним версиям.)</span><span class="sxs-lookup"><span data-stu-id="85d96-150">(Applies only to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or later.)</span></span>  
  
 <span data-ttu-id="85d96-151">**Выражение**</span><span class="sxs-lookup"><span data-stu-id="85d96-151">**Expression**</span></span>  
 <span data-ttu-id="85d96-152">Задает число или процент строк, возвращаемых запросом.</span><span class="sxs-lookup"><span data-stu-id="85d96-152">Specify the number or percentage of rows that the query will return.</span></span> <span data-ttu-id="85d96-153">При задании для параметра **Процент** значения "Да" это число будет процентом строк, возвращаемых запросом; при задании для параметра **Процент** значения "Нет" оно будет числом возвращаемых строк.</span><span class="sxs-lookup"><span data-stu-id="85d96-153">If you set **Percent** to Yes, this number is the percentage of rows the query will return; if you set **Percent** to No, it represents the number of rows to return.</span></span> <span data-ttu-id="85d96-154">(Применимо только для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] версии 7.0 либо более поздней версии.)</span><span class="sxs-lookup"><span data-stu-id="85d96-154">(Applies only to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 7.0 or later.)</span></span>  
  
 <span data-ttu-id="85d96-155">**Процент**</span><span class="sxs-lookup"><span data-stu-id="85d96-155">**Percent**</span></span>  
 <span data-ttu-id="85d96-156">Указывает, что запрос будет возвращать только первые *n* процентов строк из результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="85d96-156">Specify that the query will return only the first *n* percent of rows in the result set.</span></span> <span data-ttu-id="85d96-157">(Применимо только для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] версии 7.0 либо более поздней версии.)</span><span class="sxs-lookup"><span data-stu-id="85d96-157">(Applies only to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 7.0 or later.)</span></span>  
  
 <span data-ttu-id="85d96-158">**Со связями**</span><span class="sxs-lookup"><span data-stu-id="85d96-158">**With Ties**</span></span>  
 <span data-ttu-id="85d96-159">Указывает, что данное представление включает предложение WITH TIES.</span><span class="sxs-lookup"><span data-stu-id="85d96-159">Specify that the view will include a WITH TIES clause.</span></span> <span data-ttu-id="85d96-160">WITH TIES полезно, если представление включает предложения ORDER BY и TOP, основанные на процентах.</span><span class="sxs-lookup"><span data-stu-id="85d96-160">WITH TIES is useful if a view includes an ORDER BY clause and a TOP clause based on percentage.</span></span> <span data-ttu-id="85d96-161">Если этот режим установлен, граница процента приходится на середину набора строк с одинаковыми значениями в предложении ORDER BY, то данное представление будет расширено и включит все такие строки.</span><span class="sxs-lookup"><span data-stu-id="85d96-161">If this option is set, and if the percentage cutoff falls in the middle of a set of rows with identical values in the ORDER BY clause, the view is extended to include all such rows.</span></span> <span data-ttu-id="85d96-162">(Применимо только для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] версии 7.0 либо более поздней версии.)</span><span class="sxs-lookup"><span data-stu-id="85d96-162">(Applies only to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 7.0 or later.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85d96-163">См. также:</span><span class="sxs-lookup"><span data-stu-id="85d96-163">See Also</span></span>  
 <span data-ttu-id="85d96-164">[Запрос с параметрами &#40;визуальных инструментов для баз данных&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="85d96-164">[Query with Parameters &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="85d96-165">Разделы по конструированию запросов и представлений (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="85d96-165">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
