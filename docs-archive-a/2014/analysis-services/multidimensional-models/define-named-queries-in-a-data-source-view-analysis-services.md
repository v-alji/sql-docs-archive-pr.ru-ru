---
title: Определение именованных запросов в представлении источника данных (Analysis Services) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- named queries [Analysis Services], creating
- modifying named queries
- data source views [Analysis Services], named queries
ms.assetid: f09ba8aa-950e-4c0d-961e-970de13200be
author: minewiskan
ms.author: owend
ms.openlocfilehash: dfe2dbc6081e0c33f681ba894b16057c8890e0b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657370"
---
# <a name="define-named-queries-in-a-data-source-view-analysis-services"></a><span data-ttu-id="02c2e-102">Определение именованных запросов в представлении источника данных (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="02c2e-102">Define Named Queries in a Data Source View (Analysis Services)</span></span>
  <span data-ttu-id="02c2e-103">Именованный запрос является выражением SQL, представленным в виде таблицы.</span><span class="sxs-lookup"><span data-stu-id="02c2e-103">A named query is a SQL expression represented as a table.</span></span> <span data-ttu-id="02c2e-104">В именованном запросе можно указать выражение SQL для выбора строк и столбцов, возвращаемых из одной или нескольких таблиц в одном или нескольких источниках данных.</span><span class="sxs-lookup"><span data-stu-id="02c2e-104">In a named query, you can specify an SQL expression to select rows and columns returned from one or more tables in one or more data sources.</span></span> <span data-ttu-id="02c2e-105">Именованный запрос подобен другим таблицам со строками и связями в представлении источника данных, за исключением того, что он основан на выражении.</span><span class="sxs-lookup"><span data-stu-id="02c2e-105">A named query is like any other table in a data source view (DSV) with rows and relationships, except that the named query is based on an expression.</span></span>  
  
 <span data-ttu-id="02c2e-106">Именованный запрос позволяет расширять реляционную схему таблиц, существующих в представлении источника данных, не изменяя базового источника данных.</span><span class="sxs-lookup"><span data-stu-id="02c2e-106">A named query lets you extend the relational schema of existing tables in DSV without modifying the underlying data source.</span></span> <span data-ttu-id="02c2e-107">Например, ряд именованных запросов можно использовать для разбиения сложной таблицы измерения на меньшие, более простые таблицы измерений для использований в измерениях баз данных.</span><span class="sxs-lookup"><span data-stu-id="02c2e-107">For example, a series of named queries can be used to split up a complex dimension table into smaller, simpler dimension tables for use in database dimensions.</span></span> <span data-ttu-id="02c2e-108">Именованный запрос может быть использован для соединения нескольких таблиц баз данных из одного или более источников данных в одну таблицу представления источников данных.</span><span class="sxs-lookup"><span data-stu-id="02c2e-108">A named query can also be used to join multiple database tables from one or more data sources into a single data source view table.</span></span>  
  
## <a name="creating-a-named-query"></a><span data-ttu-id="02c2e-109">Создание именованного запроса</span><span class="sxs-lookup"><span data-stu-id="02c2e-109">Creating a Named Query</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="02c2e-110">Именованное вычисление нельзя добавить в именованный запрос, а именованный запрос не может быть основан на таблице, которая содержит именованное вычисление.</span><span class="sxs-lookup"><span data-stu-id="02c2e-110">You cannot add a named calculation to a named query, nor can you base a named query on a table that contains a named calculation.</span></span>  
  
 <span data-ttu-id="02c2e-111">При создании именованного запроса укажите имя, SQL-запрос, возвращающий столбцы и данные для таблицы, и, дополнительно, описание именованного запроса.</span><span class="sxs-lookup"><span data-stu-id="02c2e-111">When you create a named query, you specify a name, the SQL query returning the columns and data for the table, and optionally, a description of the named query.</span></span> <span data-ttu-id="02c2e-112">Выражение SQL может ссылаться на другие таблицы в представлении источника данных.</span><span class="sxs-lookup"><span data-stu-id="02c2e-112">The SQL expression can refer to other tables in the data source view.</span></span> <span data-ttu-id="02c2e-113">После определения именованного запроса SQL-запрос в именованном запросе пересылается к поставщику для выбора источника данных и проверки всего запроса.</span><span class="sxs-lookup"><span data-stu-id="02c2e-113">After the named query is defined, the SQL query in a named query is sent to the provider for the data source and validated as a whole.</span></span> <span data-ttu-id="02c2e-114">Если поставщик не обнаруживает каких-либо ошибок в SQL-запросе, то столбец добавляется к таблице.</span><span class="sxs-lookup"><span data-stu-id="02c2e-114">If the provider does not find any errors in the SQL query, the column is added to the table.</span></span>  
  
 <span data-ttu-id="02c2e-115">Таблицы и столбцы, указанные в SQL-запросе, не должны квалифицироваться или должны квалифицироваться только именем таблицы.</span><span class="sxs-lookup"><span data-stu-id="02c2e-115">Tables and columns referenced in the SQL query should not be qualified or should be qualified by the table name only.</span></span> <span data-ttu-id="02c2e-116">Например, для ссылки на столбец SaleAmount в таблице можно использовать `SaleAmount` или `Sales.SaleAmount` , но `dbo.Sales.SaleAmount` возвращает ошибку.</span><span class="sxs-lookup"><span data-stu-id="02c2e-116">For example, to refer to the SaleAmount column in a table, `SaleAmount` or `Sales.SaleAmount` is valid, but `dbo.Sales.SaleAmount` generates an error.</span></span>  
  
 <span data-ttu-id="02c2e-117">**Примечание** При определении именованного запроса, обращающегося к источнику данных [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] или [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 7.0, именованный запрос, который содержит связанный вложенный запрос и предложение GROUP BY, завершится неудачно.</span><span class="sxs-lookup"><span data-stu-id="02c2e-117">**Note** When defining a named query that queries a [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 7.0 data source, a named query that contains a correlated subquery and a GROUP BY clause will fail.</span></span> <span data-ttu-id="02c2e-118">Дополнительные сведения см. в статье [Internal Error with SELECT Statement Containing Correlated Subquery and GROUP BY](https://support.microsoft.com/kb/274729) (Внутренняя ошибка инструкции SELECT, содержащей связанный вложенный запрос и предложение GROUP BY) в базе знаний [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="02c2e-118">For more information, see [Internal Error with SELECT Statement Containing Correlated Subquery and GROUP BY](https://support.microsoft.com/kb/274729) in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base.</span></span>  
  
## <a name="add-or-edit-a-named-query"></a><span data-ttu-id="02c2e-119">Добавление или изменение именованного запроса</span><span class="sxs-lookup"><span data-stu-id="02c2e-119">Add or Edit a Named Query</span></span>  
  
1.  <span data-ttu-id="02c2e-120">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте проект или подключитесь к базе данных, которая содержит представление источника данных, в который необходимо добавить именованный запрос.</span><span class="sxs-lookup"><span data-stu-id="02c2e-120">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project or connect to the database that contains the data source view in which you want to add a named query.</span></span>  
  
2.  <span data-ttu-id="02c2e-121">В обозревателе решений откройте папку **Представления источников данных** и дважды щелкните представление источника данных.</span><span class="sxs-lookup"><span data-stu-id="02c2e-121">In Solution Explorer, expand the **Data Source Views** folder, then double-click the data source view.</span></span>  
  
3.  <span data-ttu-id="02c2e-122">На панели **Таблицы** или **Диаграмма** щелкните правой кнопкой мыши и выберите команду **Создать именованный запрос**.</span><span class="sxs-lookup"><span data-stu-id="02c2e-122">In the **Tables** or **Diagram** pane, right-click an open area and then click **New Named Query**.</span></span>  
  
4.  <span data-ttu-id="02c2e-123">В диалоговом окне **Создание именованного запроса** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="02c2e-123">In the **Create Named Query** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="02c2e-124">В текстовом поле **Имя** введите имя запроса.</span><span class="sxs-lookup"><span data-stu-id="02c2e-124">In the **Name** text box, type a query name.</span></span>  
  
    2.  <span data-ttu-id="02c2e-125">При необходимости в текстовом поле **Описание** введите описание запроса.</span><span class="sxs-lookup"><span data-stu-id="02c2e-125">Optionally, in the **Description** text box, type a description for the query.</span></span>  
  
    3.  <span data-ttu-id="02c2e-126">В списке **Источник данных** выберите источник данных для именованного запроса.</span><span class="sxs-lookup"><span data-stu-id="02c2e-126">In the **Data Source** list box, select the data source against which the named query will execute.</span></span>  
  
    4.  <span data-ttu-id="02c2e-127">Введите запрос на нижней панели или воспользуйтесь средствами графического построителя запросов для его создания.</span><span class="sxs-lookup"><span data-stu-id="02c2e-127">Type the query in the bottom pane, or use the graphical query building tools to create a query.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="02c2e-128">Помните, что пользовательский интерфейс построителя запросов зависит от источника данных.</span><span class="sxs-lookup"><span data-stu-id="02c2e-128">The query-building user interface (UI) depends on the data source.</span></span> <span data-ttu-id="02c2e-129">Вместо графического интерфейса можно воспользоваться универсальным текстовым.</span><span class="sxs-lookup"><span data-stu-id="02c2e-129">Instead of getting a graphical UI, you can get a generic UI, which is text-based.</span></span> <span data-ttu-id="02c2e-130">Для выполнения одних и тех же задач доступны оба пользовательских интерфейса, но выполняемые при этом действия будут отличаться.</span><span class="sxs-lookup"><span data-stu-id="02c2e-130">You can accomplish the same things with these different UIs, but you must do so in different ways.</span></span> <span data-ttu-id="02c2e-131">Дополнительные сведения см. в разделе [Диалоговое окно "Создание именованного запроса" или "Изменение именованного запроса" (службы Analysis Services — многомерные данные)](../create-or-edit-named-query-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="02c2e-131">For more information, see [Create or Edit Named Query Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](../create-or-edit-named-query-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
5.  <span data-ttu-id="02c2e-132">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="02c2e-132">Click **OK**.</span></span> <span data-ttu-id="02c2e-133">В заголовке таблицы появится значок с двумя пересекающимися таблицами, указывающий на то, что таблица была заменена именованным запросом.</span><span class="sxs-lookup"><span data-stu-id="02c2e-133">An icon showing two overlapping tables appears in the table header to indicate that the table has been replaced by a named query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02c2e-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="02c2e-134">See Also</span></span>  
 <span data-ttu-id="02c2e-135">[Представления источников данных в многомерных моделях](data-source-views-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="02c2e-135">[Data Source Views in Multidimensional Models](data-source-views-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="02c2e-136">Определение именованных вычислений в представлении источника данных (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="02c2e-136">Define Named Calculations in a Data Source View &#40;Analysis Services&#41;</span></span>](define-named-calculations-in-a-data-source-view-analysis-services.md)  
  
  
