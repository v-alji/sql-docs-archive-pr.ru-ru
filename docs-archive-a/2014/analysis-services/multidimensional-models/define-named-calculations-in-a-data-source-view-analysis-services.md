---
title: Определение именованных вычислений в представлении источника данных (Analysis Services) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- modifying named calculations
- data source views [Analysis Services], named calculations
- named calculations [Analysis Services]
ms.assetid: 729e7b12-6185-4b73-8bcb-cfe459b15355
author: minewiskan
ms.author: owend
ms.openlocfilehash: ae901c340fe29c042430d928a4abaea8e8cfe84b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664598"
---
# <a name="define-named-calculations-in-a-data-source-view-analysis-services"></a><span data-ttu-id="0d6ae-102">Определение именованных вычислений в представлении источника данных (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="0d6ae-102">Define Named Calculations in a Data Source View (Analysis Services)</span></span>
  <span data-ttu-id="0d6ae-103">Именованное вычисление является выражением SQL, представленным в виде вычисляемого столбца.</span><span class="sxs-lookup"><span data-stu-id="0d6ae-103">A named calculation is a SQL expression represented as a calculated column.</span></span> <span data-ttu-id="0d6ae-104">Данное выражение выглядит и работает как столбец таблицы.</span><span class="sxs-lookup"><span data-stu-id="0d6ae-104">This expression appears and behaves as a column in the table.</span></span> <span data-ttu-id="0d6ae-105">Именованное вычисление позволяет расширить реляционную схему таблиц или представлений, существующих в представлении источника данных, не изменяя таблицы или представления в базовом источнике данных.</span><span class="sxs-lookup"><span data-stu-id="0d6ae-105">A named calculation lets you extend the relational schema of existing tables or views in a data source view without modifying the tables or views in the underlying data source.</span></span> <span data-ttu-id="0d6ae-106">Рассмотрим следующие примеры.</span><span class="sxs-lookup"><span data-stu-id="0d6ae-106">Consider the following examples:</span></span>

-   <span data-ttu-id="0d6ae-107">Создайте одно именованное вычисление, получаемое из нескольких столбцов таблицы фактов (например, вычисление суммы налога путем умножения налоговой ставки на стоимость продажи).</span><span class="sxs-lookup"><span data-stu-id="0d6ae-107">Create a single named calculation that is derived from multiple columns in a fact table (for example, creating Tax Amount by multiplying a tax rate by a sales price).</span></span>

-   <span data-ttu-id="0d6ae-108">Составьте для элемента измерения понятное имя.</span><span class="sxs-lookup"><span data-stu-id="0d6ae-108">Construct a user friendly name for a dimension member.</span></span>

-   <span data-ttu-id="0d6ae-109">Для повышения производительности запросов создайте именованное вычисление в представлении источника данных вместо создания вычисляемого элемента в кубе.</span><span class="sxs-lookup"><span data-stu-id="0d6ae-109">As a query performance enhancement, create a named calculation in the DSV instead of creating a calculated member in a cube.</span></span> <span data-ttu-id="0d6ae-110">Именованные вычисления рассчитываются в процессе обработки, тогда как вычисляемые элементы рассчитываются во время запроса.</span><span class="sxs-lookup"><span data-stu-id="0d6ae-110">Named calculations are calculated during processing whereas calculated members are calculated at query time.</span></span>

## <a name="creating-named-calculations"></a><span data-ttu-id="0d6ae-111">Создание именованных вычислений</span><span class="sxs-lookup"><span data-stu-id="0d6ae-111">Creating Named Calculations</span></span>

> [!NOTE]
>  <span data-ttu-id="0d6ae-112">Именованное вычисление нельзя добавить в именованный запрос, а именованный запрос не может быть основан на таблице, которая содержит именованное вычисление.</span><span class="sxs-lookup"><span data-stu-id="0d6ae-112">You cannot add a named calculation to a named query, nor can you base a named query on a table that contains a named calculation.</span></span>

 <span data-ttu-id="0d6ae-113">При создании именованного вычисления указывается имя, выражение SQL и (необязательно) описание вычисления.</span><span class="sxs-lookup"><span data-stu-id="0d6ae-113">When you create a named calculation, you specify a name, the SQL expression, and, optionally, a description of the calculation.</span></span> <span data-ttu-id="0d6ae-114">Выражение SQL может ссылаться на другие таблицы в представлении источника данных.</span><span class="sxs-lookup"><span data-stu-id="0d6ae-114">The SQL expression can refer to other tables in the data source view.</span></span> <span data-ttu-id="0d6ae-115">После определения именованного вычисления выражение в именованном вычислении отправляется поставщику источника данных и проверяется в виде указанной ниже инструкции SQL, в которой `<Expression>` содержит выражение, определяющее именованное вычисление.</span><span class="sxs-lookup"><span data-stu-id="0d6ae-115">After the named calculation is defined, the expression in a named calculation is sent to the provider for the data source and validated as the following SQL statement in which `<Expression>` contains the expression that defines the named calculation.</span></span>

```
SELECT 
   <Table Name in Data Source>.*, 
   <Expression> AS <Column Name> 
FROM 
   <Table Name in Data Source> AS <Table Name in Data Source View>
```

 <span data-ttu-id="0d6ae-116">Тип данных столбца определяется типом данных скалярного значения, возвращенного выражением.</span><span class="sxs-lookup"><span data-stu-id="0d6ae-116">The data type of the column is determined by the data type of the scalar value returned by the expression.</span></span> <span data-ttu-id="0d6ae-117">Если поставщик не обнаружит каких-либо ошибок в выражении, то столбец будет добавлен к таблице.</span><span class="sxs-lookup"><span data-stu-id="0d6ae-117">If the provider does not find any errors in the expression, the column is added to the table.</span></span>

 <span data-ttu-id="0d6ae-118">Столбцы, указанные в выражении, не должны иметь квалификатора вовсе или должны иметь только такой квалификатор, который соответствует имени таблицы.</span><span class="sxs-lookup"><span data-stu-id="0d6ae-118">Columns referenced in the expression should not be qualified or should be qualified by the table name only.</span></span> <span data-ttu-id="0d6ae-119">Например, для ссылки на столбец SaleAmount в таблице можно использовать `SaleAmount` или `Sales.SaleAmount` , но `dbo.Sales.SaleAmount` возвращает ошибку.</span><span class="sxs-lookup"><span data-stu-id="0d6ae-119">For example, to refer to the SaleAmount column in a table, `SaleAmount` or `Sales.SaleAmount` is valid, but `dbo.Sales.SaleAmount` generates an error.</span></span>

 <span data-ttu-id="0d6ae-120">Выражение не заключается автоматически в скобки.</span><span class="sxs-lookup"><span data-stu-id="0d6ae-120">The expression is not automatically enclosed between parentheses.</span></span> <span data-ttu-id="0d6ae-121">Следовательно, если выражение, например инструкцию SELECT, необходимо заключить в скобки, то необходимо ввести скобки в поле **Выражение** .</span><span class="sxs-lookup"><span data-stu-id="0d6ae-121">Therefore, if an expression, such as a SELECT statement, requires parentheses, you must type the parentheses in the **Expression** box.</span></span> <span data-ttu-id="0d6ae-122">Например, следующее выражение допустимо только при наличии скобок.</span><span class="sxs-lookup"><span data-stu-id="0d6ae-122">For example, the following expression is valid only if you type the parentheses.</span></span>

```
(SELECT Description FROM Categories WHERE Categories.CategoryID = CategoryID)
```

## <a name="add-or-edit-a-named-calculation"></a><span data-ttu-id="0d6ae-123">Добавление или изменение именованного вычисления</span><span class="sxs-lookup"><span data-stu-id="0d6ae-123">Add or Edit a Named Calculation</span></span>

1.  <span data-ttu-id="0d6ae-124">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте проект или подключитесь к базе данных, содержащей представление источника данных, в котором необходимо определить именованное вычисление.</span><span class="sxs-lookup"><span data-stu-id="0d6ae-124">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project or connect to the database that contains the data source view in which you wish to define a named calculation.</span></span>

2.  <span data-ttu-id="0d6ae-125">В обозревателе решений откройте папку **Представления источников данных** и дважды щелкните представление источника данных.</span><span class="sxs-lookup"><span data-stu-id="0d6ae-125">In Solution Explorer, expand the **Data Source Views** folder, then double-click the data source view.</span></span>

3.  <span data-ttu-id="0d6ae-126">На панели **Таблицы** или на панели **Диаграмма** щелкните правой кнопкой мыши таблицу, в которой необходимо определить именованное вычисление, и выберите пункт **Создать именованное вычисление**.</span><span class="sxs-lookup"><span data-stu-id="0d6ae-126">Right-click the table in which you wish to define the named calculation in either the **Tables** or the **Diagram** pane, and then click **New Named Calculation**.</span></span> <span data-ttu-id="0d6ae-127">Правой кнопкой мыши щелкните имя таблицы, но не атрибут.</span><span class="sxs-lookup"><span data-stu-id="0d6ae-127">Be sure to right-click on the table name, and not on an attribute.</span></span> <span data-ttu-id="0d6ae-128">Меню должно иметь следующий вид.</span><span class="sxs-lookup"><span data-stu-id="0d6ae-128">The menu should look like the following:</span></span>

     <span data-ttu-id="0d6ae-129">![Снимок экрана: рабочее пространство диаграммы, контекстное меню](../media/ssas-olapdsv-diagram.gif "Снимок экрана: рабочее пространство диаграммы, контекстное меню")</span><span class="sxs-lookup"><span data-stu-id="0d6ae-129">![Screenshot of diagram workspace, right-click menu](../media/ssas-olapdsv-diagram.gif "Screenshot of diagram workspace, right-click menu")</span></span>

    > [!NOTE]
    >  <span data-ttu-id="0d6ae-130">Чтобы найти таблицу или представление, можно использовать команду **Поиск таблицы** , выбрав меню **Представление источника данных** или щелкнув правой кнопкой мыши рабочую область панели **Таблицы** или панели **Диаграмма** .</span><span class="sxs-lookup"><span data-stu-id="0d6ae-130">To locate a table or view, you can use the **Find Table** option by either clicking the **Data Source View** menu or right-clicking in an open area of the **Tables** or **Diagram** panes.</span></span>

4.  <span data-ttu-id="0d6ae-131">В диалоговом окне **Создание именованных вычислений** выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="0d6ae-131">In the **Create Named Calculations** dialog box, do the following:</span></span>

    -   <span data-ttu-id="0d6ae-132">В текстовом поле **Имя столбца** введите имя нового столбца.</span><span class="sxs-lookup"><span data-stu-id="0d6ae-132">In the **Column name** text box, type the name of the new column.</span></span>

    -   <span data-ttu-id="0d6ae-133">В текстовом поле **Описание** введите описание нового столбца.</span><span class="sxs-lookup"><span data-stu-id="0d6ae-133">In the **Description** text box type a description for the new column.</span></span>

    -   <span data-ttu-id="0d6ae-134">В текстовом поле **Выражение** введите выражение, которое возвращает содержимое нового столбца на приемлемой для поставщика данных разновидности языка SQL.</span><span class="sxs-lookup"><span data-stu-id="0d6ae-134">In the **Expression** text box, type the expression that yields the content of the new column in the SQL dialect appropriate for the data provider.</span></span>

5.  <span data-ttu-id="0d6ae-135">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0d6ae-135">Click **OK**.</span></span>

     <span data-ttu-id="0d6ae-136">Столбец именованного вычисления появится как последний столбец в таблице представления источников данных.</span><span class="sxs-lookup"><span data-stu-id="0d6ae-136">The named calculation column appears as the last column in the data source view table.</span></span> <span data-ttu-id="0d6ae-137">Значок калькулятора указывает на то, что столбец содержит именованное вычисление.</span><span class="sxs-lookup"><span data-stu-id="0d6ae-137">A calculator symbol indicates that the column contains a named calculation.</span></span>

## <a name="delete-a-named-calculation"></a><span data-ttu-id="0d6ae-138">Удаление именованного вычисления</span><span class="sxs-lookup"><span data-stu-id="0d6ae-138">Delete a Named Calculation</span></span>
 <span data-ttu-id="0d6ae-139">При попытке удалить именованное вычисление приложение выдаст список объектов, определенных в проекте или базе данных, которые при удалении станут недействительными.</span><span class="sxs-lookup"><span data-stu-id="0d6ae-139">When you attempt to delete a named calculation, you are prompted with a list of the objects defined in the project or database that will be invalidated by the deletion.</span></span> <span data-ttu-id="0d6ae-140">Внимательно просмотрите список перед удалением вычисления.</span><span class="sxs-lookup"><span data-stu-id="0d6ae-140">Review the list carefully before deleting the calculation.</span></span>

## <a name="see-also"></a><span data-ttu-id="0d6ae-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="0d6ae-141">See Also</span></span>
 [<span data-ttu-id="0d6ae-142">Определение именованных запросов в представлении источника данных (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="0d6ae-142">Define Named Queries in a Data Source View &#40;Analysis Services&#41;</span></span>](define-named-queries-in-a-data-source-view-analysis-services.md)


