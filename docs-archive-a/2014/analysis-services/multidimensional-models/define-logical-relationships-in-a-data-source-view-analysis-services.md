---
title: Определение логических связей в представлении источника данных (Analysis Services) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- adding relationships
- relationships [Analysis Services], data source views
- data source views [Analysis Services], relationships
ms.assetid: a20d6dae-e769-4131-8a59-7ef56f174220
author: minewiskan
ms.author: owend
ms.openlocfilehash: c46c2b360a4528aeb0eb88348d0d1242b22d8ef5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664603"
---
# <a name="define-logical-relationships-in-a-data-source-view-analysis-services"></a><span data-ttu-id="686e2-102">Определение логических связей в представлении источника данных (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="686e2-102">Define Logical Relationships in a Data Source View (Analysis Services)</span></span>
  <span data-ttu-id="686e2-103">Мастер представлений источников данных и конструктор представлений источников данных автоматически определяют связи между таблицами, добавленными к представлению источника данных (DSV), основываясь на базовых связях базы данных или на указанном критерии совпадения имен.</span><span class="sxs-lookup"><span data-stu-id="686e2-103">The Data Source View Wizard and Data Source View Designer automatically define relationships between tables added to a data source view (DSV) based on underlying database relationships or name matching criteria you specify.</span></span>  
  
 <span data-ttu-id="686e2-104">При работе с данными из нескольких источников может потребоваться вручную определить логические связи в представлении источника данных (DSV) дополнительно к связям, определенным автоматически.</span><span class="sxs-lookup"><span data-stu-id="686e2-104">In cases where you are working with data from multiple data sources, you may need to manually define logical relationships in the DSV to supplement those relationships that are defined automatically.</span></span> <span data-ttu-id="686e2-105">Связи необходимы службам [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] для идентификации таблиц фактов и измерений, для построения запросов на получение данных и метаданных из базовых источников данных и для использования преимуществ расширенных функций бизнес-аналитики.</span><span class="sxs-lookup"><span data-stu-id="686e2-105">Relationships are required in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to identify fact and dimension tables, to construct queries for retrieving data and metadata from underlying data sources, and to take advantage of advanced business intelligence features.</span></span>  
  
 <span data-ttu-id="686e2-106">В мастере представлений источников данных можно определить следующие типы связей:</span><span class="sxs-lookup"><span data-stu-id="686e2-106">You can define the following types of relationships in Data Source View Designer:</span></span>  
  
-   <span data-ttu-id="686e2-107">Связь одной таблицы с другой таблицей в том же источнике данных.</span><span class="sxs-lookup"><span data-stu-id="686e2-107">A relationship from one table to another table in the same data source.</span></span>  
  
-   <span data-ttu-id="686e2-108">Связь одной таблицы с самой собой, в виде связи «родители-потомки».</span><span class="sxs-lookup"><span data-stu-id="686e2-108">A relationship from one table to itself, as in a parent-child relationship.</span></span>  
  
-   <span data-ttu-id="686e2-109">Связь одной таблицы в источнике данных с другой таблицей в другом источнике данных.</span><span class="sxs-lookup"><span data-stu-id="686e2-109">A relationship from one table in a data source to another table in a different data source.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="686e2-110">Связи, определенные в представлении источника данных (DSV), являются логическими и могут не отображать действительные связи, определенные в базовом источнике данных.</span><span class="sxs-lookup"><span data-stu-id="686e2-110">The relationships defined in a DSV are logical and may not reflect the actual relationships defined in the underlying data source.</span></span> <span data-ttu-id="686e2-111">В конструкторе представлений источников данных можно создавать связи, которые не существуют в базовом источнике данных, и удалять связи, созданные в конструкторе представлений источников данных из существующих связей внешних ключей в базовом источнике данных.</span><span class="sxs-lookup"><span data-stu-id="686e2-111">You can create relationships in Data Source View Designer that do not exist in the underlying data source, and remove relationships created by Data Source View Designer from existing foreign key relationships in the underlying data source.</span></span>  
  
 <span data-ttu-id="686e2-112">Связи являются направленными.</span><span class="sxs-lookup"><span data-stu-id="686e2-112">Relationships are directed.</span></span> <span data-ttu-id="686e2-113">Для каждого значения в исходном столбце имеется соответствующее значение в целевом столбце.</span><span class="sxs-lookup"><span data-stu-id="686e2-113">For every value in the source column, there is a corresponding value in the destination column.</span></span> <span data-ttu-id="686e2-114">На диаграмме представления источников данных, например на диаграммах, отображаемых на панели **Диаграмма** , стрелка на линии между двумя таблицами указывает направление связи.</span><span class="sxs-lookup"><span data-stu-id="686e2-114">In a data source view diagram, such as the diagrams displayed in the **Diagram** pane, an arrow on the line between two tables indicates the direction of the relationship.</span></span>  
  
 <span data-ttu-id="686e2-115">Этот раздел включает следующие подразделы:</span><span class="sxs-lookup"><span data-stu-id="686e2-115">This topic includes the following sections:</span></span>  
  
 [<span data-ttu-id="686e2-116">Добавление связи между таблицами, именованными запросами или представлениями</span><span class="sxs-lookup"><span data-stu-id="686e2-116">To add a relationship between tables, named queries, or views</span></span>](#bkmk_addRel)  
  
 [<span data-ttu-id="686e2-117">Просмотр или изменение связи на панели диаграммы</span><span class="sxs-lookup"><span data-stu-id="686e2-117">To view or modify a relationship in the Diagram pane</span></span>](#bkmk_diagrampane)  
  
 [<span data-ttu-id="686e2-118">Просмотр или изменение связи на панели таблицы</span><span class="sxs-lookup"><span data-stu-id="686e2-118">To view or modify a relationship in the Tables pane</span></span>](#bkmk_tablespane)  
  
##  <a name="to-add-a-relationship-between-tables-named-queries-or-views"></a><a name="bkmk_addRel"></a><span data-ttu-id="686e2-119">Добавление связи между таблицами, именованными запросами или представлениями</span><span class="sxs-lookup"><span data-stu-id="686e2-119">To add a relationship between tables, named queries, or views</span></span>  
  
1.  <span data-ttu-id="686e2-120">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте проект или подключитесь к базе данных, содержащей представление источника данных, в котором необходимо добавить логическую связь.</span><span class="sxs-lookup"><span data-stu-id="686e2-120">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project or connect to the database that contains the data source view in which you wish to add a logical relationship.</span></span>  
  
2.  <span data-ttu-id="686e2-121">Для открытия представления источников данных в **Конструкторе представлений источников данных** в обозревателе решений откройте папку **Представления источников данных**и дважды щелкните нужное представление.</span><span class="sxs-lookup"><span data-stu-id="686e2-121">In Solution Explorer, expand the **Data Source Views** folder, then double-click the data source view to open it in **Data Source View Designer**.</span></span>  
  
3.  <span data-ttu-id="686e2-122">На панели **Таблицы** щелкните правой кнопкой мыши таблицу, именованный запрос или представление, в которые необходимо добавить связь, а затем выберите пункт **Создать связь**.</span><span class="sxs-lookup"><span data-stu-id="686e2-122">Right-click the table, named query or view to which you want to add a relationship in either the **Tables** pane and then click **New Relationship**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="686e2-123">Чтобы найти таблицу, представление или именованный запрос, можно воспользоваться командой **Поиск таблицы** в меню **Представления источников данных** или в контекстном меню, вызываемом щелчком правой кнопкой мыши в свободной области панели **Таблицы** или **Диаграммы** .</span><span class="sxs-lookup"><span data-stu-id="686e2-123">To locate a table, view or named query, you can use the **Find Table** option by either clicking the **Data Source View** menu or right-clicking in an open area of the **Tables** or **Diagram** panes.</span></span>  
  
4.  <span data-ttu-id="686e2-124">В диалоговом окне **Указание связи** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="686e2-124">In the **Specify Relationship** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="686e2-125">Выберите нужную таблицу, именованный запрос или представление в списке **Исходная таблица (внешний ключ)** .</span><span class="sxs-lookup"><span data-stu-id="686e2-125">Select the appropriate table, named query, or view in the **Source (foreign key) table** list.</span></span>  
  
    2.  <span data-ttu-id="686e2-126">Выберите нужную таблицу, именованный запрос или представление в списке **Целевая таблица (первичный ключ)** .</span><span class="sxs-lookup"><span data-stu-id="686e2-126">Select the appropriate table, named query, or view in the **Destination (primary key) table** lists.</span></span>  
  
    3.  <span data-ttu-id="686e2-127">Выберите столбцы из списков **Исходные столбцы** и **Целевые столбцы** , чтобы создать связи между этими двумя таблицами.</span><span class="sxs-lookup"><span data-stu-id="686e2-127">Select columns from the **Source Columns** and **Destination Columns** lists to create a relationship between the two tables.</span></span>  
  
         <span data-ttu-id="686e2-128">Если при выборке данных из базовой таблицы, представления или именованного запроса среда [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] обнаружила, что направление связи определено неверно (от первичного ключа к внешнему ключу, а не наоборот), то будет предложено изменить порядок на обратный.</span><span class="sxs-lookup"><span data-stu-id="686e2-128">If [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] detects, by sampling the data in the underlying table, view, or named query, that you have defined the relationship in the wrong direction (from the primary key to the foreign key rather than from the foreign key to the primary key), you will be prompted to reverse the order.</span></span> <span data-ttu-id="686e2-129">Для быстрого изменения направления связи нажмите кнопку **Обратить**.</span><span class="sxs-lookup"><span data-stu-id="686e2-129">To quickly reverse the order, click **Reverse**.</span></span>  
  
         <span data-ttu-id="686e2-130">Если среда [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] обнаружила, что для выбранных столбцов связь уже существует, будет выведено предложение изменить выбор.</span><span class="sxs-lookup"><span data-stu-id="686e2-130">If [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] detects that a relationship already exists for the columns you have selected, you will be prompted.</span></span> <span data-ttu-id="686e2-131">Повторяющиеся связи определять нельзя.</span><span class="sxs-lookup"><span data-stu-id="686e2-131">You cannot define duplicate relationships.</span></span>  
  
    4.  <span data-ttu-id="686e2-132">Дополнительно в поле **Описание** введите описание связи.</span><span class="sxs-lookup"><span data-stu-id="686e2-132">Optionally, in the **Description** box, type a description for the relationship.</span></span>  
  
##  <a name="to-view-or-modify-a-relationship-in-the-diagram-pane"></a><a name="bkmk_diagrampane"></a><span data-ttu-id="686e2-133">Просмотр или изменение связи на панели «Диаграмма»</span><span class="sxs-lookup"><span data-stu-id="686e2-133">To view or modify a relationship in the Diagram pane</span></span>  
  
-   <span data-ttu-id="686e2-134">На панели **Диаграмма** в **Конструкторе представлений источников данных**щелкните правой кнопкой мыши связь, которую необходимо просмотреть, и выберите пункт **Изменить связь** (или просто дважды щелкните стрелку связи).</span><span class="sxs-lookup"><span data-stu-id="686e2-134">In the **Diagram** pane in **Data Source View Designer**, right-click the relationship that you want to view and click **Edit Relationship** (or simply double-click the relationship arrow).</span></span>  <span data-ttu-id="686e2-135">Для изменения связи используйте диалоговое окно **Изменение связи** .</span><span class="sxs-lookup"><span data-stu-id="686e2-135">Use the **Edit Relationship** dialog box to modify the relationship.</span></span>  
  
##  <a name="to-view-or-modify-a-relationship-in-the-tables-pane"></a><a name="bkmk_tablespane"></a><span data-ttu-id="686e2-136">Просмотр или изменение связи на панели «таблицы»</span><span class="sxs-lookup"><span data-stu-id="686e2-136">To view or modify a relationship in the Tables pane</span></span>  
  
1.  <span data-ttu-id="686e2-137">На панели **Таблицы** в **Конструкторе представлений источников данных**найдите и разверните таблицу, представление или именованный запрос, содержащий связь, которую необходимо просмотреть или изменить.</span><span class="sxs-lookup"><span data-stu-id="686e2-137">In the **Tables** pane in **Data Source View Designer**, locate and then expand the table, view or named query containing the relationship that you wish to view or modify.</span></span>  
  
2.  <span data-ttu-id="686e2-138">Раскройте папку **Связи** .</span><span class="sxs-lookup"><span data-stu-id="686e2-138">Expand the **Relationships** folder.</span></span>  <span data-ttu-id="686e2-139">Связи между выбранной таблицей, представлением или именованным запросом и другими таблицами, представлениями и именованными запросами отображаются вместе со столбцом связей.</span><span class="sxs-lookup"><span data-stu-id="686e2-139">The relationships between the selected table, view or named query and other tables, views and named queries appear with the relationship column listed.</span></span>  
  
3.  <span data-ttu-id="686e2-140">Для изменения связи щелкните ее правой кнопкой мыши и выберите пункт **Изменить связь**.</span><span class="sxs-lookup"><span data-stu-id="686e2-140">Right-click the relationship you want to modify, and then click **Edit Relationship**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="686e2-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="686e2-141">See Also</span></span>  
 [<span data-ttu-id="686e2-142">Представления источников данных в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="686e2-142">Data Source Views in Multidimensional Models</span></span>](data-source-views-in-multidimensional-models.md)  
  
  
