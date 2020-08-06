---
title: Определение параметров в конструкторе запросов многомерных выражений для Analysis Services (построитель отчетов и SSRS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- parameters [Reporting Services], MDX
- Multidimensional Expressions [Reporting Services]
- Data Mining Prediction [Reporting Services]
- MDX [Reporting Services], defining parameters
- DMX [Reporting Services]
ms.assetid: 4ad1e5bc-f510-4752-b4f6-589e55317a90
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6b2b05fc0122eb25a7a0799f7b47b1b99486a28c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751787"
---
# <a name="define-parameters-in-the-mdx-query-designer-for-analysis-services-report-builder-and-ssrs"></a><span data-ttu-id="bbadf-102">Определение параметров в конструкторе запросов многомерных выражений для служб Analysis Services (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="bbadf-102">Define Parameters in the MDX Query Designer for Analysis Services (Report Builder and SSRS)</span></span>
  <span data-ttu-id="bbadf-103">Чтобы параметризовать запрос многомерных выражений для источника данных служб [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] , необходимо добавить параметр запроса к этому запросу.</span><span class="sxs-lookup"><span data-stu-id="bbadf-103">To parameterize an MDX query for an [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data source, you must add a query parameter to the query.</span></span> <span data-ttu-id="bbadf-104">В конструкторе запросов многомерных выражений параметр запроса можно добавить как в режиме конструктора, так и в режиме запроса, настроив фильтр.</span><span class="sxs-lookup"><span data-stu-id="bbadf-104">In the MDX query designer, you can add a query parameter in both Design mode and Query mode by specifying a filter.</span></span> <span data-ttu-id="bbadf-105">После определения запроса с параметром запроса, службы Reporting Services автоматически создают параметр отчета и набор данных, чтобы предоставить список допустимых значений.</span><span class="sxs-lookup"><span data-stu-id="bbadf-105">After you define the query with a query parameter, Reporting Services automatically creates a report parameter and a dataset to provide the list of valid values.</span></span> <span data-ttu-id="bbadf-106">Это позволяет пользователю указать значение, которое передается непосредственно запросу.</span><span class="sxs-lookup"><span data-stu-id="bbadf-106">This enables a user to specify a value that is passed directly to the query.</span></span>

> [!NOTE]
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]

### <a name="to-define-a-query-parameter-in-mdx-in-design-mode"></a><span data-ttu-id="bbadf-107">Определение параметра запроса в многомерном выражении в режиме конструктора</span><span class="sxs-lookup"><span data-stu-id="bbadf-107">To define a query parameter in MDX in Design mode</span></span>

1.  <span data-ttu-id="bbadf-108">В области данных отчета щелкните правой кнопкой мыши набор данных, созданный на основе типа источника данных служб [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], и выберите пункт **Запрос**.</span><span class="sxs-lookup"><span data-stu-id="bbadf-108">In the Report Data pane, right-click on a dataset created from a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data source type, and then click **Query**.</span></span> <span data-ttu-id="bbadf-109">Конструктор запросов многомерных выражений открывается в режиме конструктора.</span><span class="sxs-lookup"><span data-stu-id="bbadf-109">The MDX query designer opens in Design mode.</span></span>

2.  <span data-ttu-id="bbadf-110">Перетащите измерение в область фильтра в первую ячейку в столбце **Измерение** .</span><span class="sxs-lookup"><span data-stu-id="bbadf-110">Drag a dimension to the filter area and drop it on the first cell in the **Dimension** column.</span></span>

3.  <span data-ttu-id="bbadf-111">В столбце **Иерархия** выберите значение в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="bbadf-111">In the **Hierarchy** column, choose a value from the drop-down list.</span></span>

4.  <span data-ttu-id="bbadf-112">В столбце **Оператор** выберите оператор в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="bbadf-112">In the **Operator** column, choose an operator for the drop-down list.</span></span>

5.  <span data-ttu-id="bbadf-113">В столбце **Критерий фильтра** выберите отдельные значения из раскрывающегося списка или щелкните **Все** , чтобы выбрать все значения.</span><span class="sxs-lookup"><span data-stu-id="bbadf-113">In the **Filter Expression** column, select individual values from the drop-down list, or click the **All** member to choose all values.</span></span>

6.  <span data-ttu-id="bbadf-114">В столбце **Параметры** установите флажок, чтобы создать параметр отчета.</span><span class="sxs-lookup"><span data-stu-id="bbadf-114">In the **Parameters** column, select the check box to create a report parameter.</span></span>

7.  <span data-ttu-id="bbadf-115">Нажмите кнопку **Запустить**.</span><span class="sxs-lookup"><span data-stu-id="bbadf-115">Click **Run**.</span></span>

     <span data-ttu-id="bbadf-116">После запуска запроса нажмите кнопку **Конструктор** на панели инструментов, чтобы переключиться в режим запроса для просмотра созданного запроса многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="bbadf-116">After you run the query, click **Design** on the toolbar to toggle to Query mode to view the MDX query that was created.</span></span> <span data-ttu-id="bbadf-117">Чтобы продолжить работу в режиме конструктора для создания запроса, не изменяйте текст запроса в режиме запроса.</span><span class="sxs-lookup"><span data-stu-id="bbadf-117">Do not change the query text in Query mode if you want to continue to use Design mode to develop the query.</span></span> <span data-ttu-id="bbadf-118">Нажмите кнопку **Конструктор** , чтобы снова переключиться в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="bbadf-118">Click **Design** to toggle back to Design mode.</span></span>

8.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]

     <span data-ttu-id="bbadf-119">В области данных отчета разверните узел «Параметры», чтобы отобразить параметр отчета, который был автоматически создан для фильтра.</span><span class="sxs-lookup"><span data-stu-id="bbadf-119">In the Report Data pane, expand the Parameters node to display the report parameter that was automatically created for the filter.</span></span>

     <span data-ttu-id="bbadf-120">Чтобы просмотреть набор данных, который включает доступные значения для параметра отчета, щелкните правой кнопкой мыши в любом пустом месте на панели данных отчета и выберите пункт **Показывать скрытые наборы данных**.</span><span class="sxs-lookup"><span data-stu-id="bbadf-120">To view the dataset that provides available values for the report parameter, right-click any blank area in the Report Data pane, and then click **Show Hidden Datasets**.</span></span> <span data-ttu-id="bbadf-121">В области данных отчета отображаются все наборы данных отчета.</span><span class="sxs-lookup"><span data-stu-id="bbadf-121">The Report Data pane displays all datasets in the report.</span></span>

### <a name="to-define-a-query-parameter-in-mdx-in-query-mode"></a><span data-ttu-id="bbadf-122">Определение параметра запроса в многомерном выражении в режиме запроса</span><span class="sxs-lookup"><span data-stu-id="bbadf-122">To define a query parameter in MDX in Query mode</span></span>

1.  <span data-ttu-id="bbadf-123">В области данных отчета щелкните правой кнопкой мыши набор данных, созданный на основе типа источника данных служб [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], и выберите пункт **Запрос**.</span><span class="sxs-lookup"><span data-stu-id="bbadf-123">In the Report Data pane, right-click on a dataset created from a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data source type, and then click **Query**.</span></span> <span data-ttu-id="bbadf-124">Конструктор запросов многомерных выражений открывается в режиме конструктора.</span><span class="sxs-lookup"><span data-stu-id="bbadf-124">The MDX query designer opens in Design mode.</span></span>

2.  <span data-ttu-id="bbadf-125">На панели инструментов нажмите кнопку **Конструктор** , чтобы переключиться в режим запроса.</span><span class="sxs-lookup"><span data-stu-id="bbadf-125">On the toolbar, click **Design** to toggle to Query mode.</span></span>

3.  <span data-ttu-id="bbadf-126">На панели инструментов в конструкторе запросов многомерных выражений щелкните **Параметры запроса** (![Значок диалогового окна "Параметры запроса"](../../analysis-services/media/iconqueryparameter.gif "Значок диалогового окна "Параметры запроса"")).</span><span class="sxs-lookup"><span data-stu-id="bbadf-126">On the MDX query designer toolbar, click **Query Parameters** (![Icon for the Query Parameters dialog box](../../analysis-services/media/iconqueryparameter.gif "Icon for the Query Parameters dialog box")).</span></span> <span data-ttu-id="bbadf-127">Откроется диалоговое окно «Параметры запроса».</span><span class="sxs-lookup"><span data-stu-id="bbadf-127">The Query Parameters dialog box opens.</span></span>

4.  <span data-ttu-id="bbadf-128">В столбце **параметр** щелкните **\<Enter Parameter>** , а затем введите имя параметра.</span><span class="sxs-lookup"><span data-stu-id="bbadf-128">In the **Parameter** column, click **\<Enter Parameter>**, and then type the name of a parameter.</span></span>

5.  <span data-ttu-id="bbadf-129">В столбце **Измерение** выберите значение в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="bbadf-129">In the **Dimension** column, choose a value from the drop-down list.</span></span>

6.  <span data-ttu-id="bbadf-130">В столбце **Иерархия** выберите значение в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="bbadf-130">In the **Hierarchy** column, choose a value from the drop-down list.</span></span>

7.  <span data-ttu-id="bbadf-131">В столбце **Несколько значений** установите флажок, чтобы создать многозначный параметр.</span><span class="sxs-lookup"><span data-stu-id="bbadf-131">In the **Multiple values** column, select the check box to create a multivalue parameter.</span></span>

8.  <span data-ttu-id="bbadf-132">В столбце **По умолчанию** выберите в раскрывающемся списке одно или несколько значений (в зависимости от выбора, сделанного на шаге 5).</span><span class="sxs-lookup"><span data-stu-id="bbadf-132">In the **Default** column, from the drop-down list, select a single value or multiple values depending on your choice in step 5.</span></span>

9. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]

10. <span data-ttu-id="bbadf-133">На панели инструментов конструктора запросов нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="bbadf-133">On the query designer toolbar, click **Run**.</span></span>

11. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]

     <span data-ttu-id="bbadf-134">В области данных отчета разверните узел «Параметры», чтобы отобразить параметр отчета, который был автоматически создан для фильтра.</span><span class="sxs-lookup"><span data-stu-id="bbadf-134">In the Report Data pane, expand the Parameters node to display the report parameter that was automatically created for the filter.</span></span>

     <span data-ttu-id="bbadf-135">Чтобы просмотреть набор данных, который включает доступные значения для параметра отчета, щелкните правой кнопкой мыши в любом пустом месте на панели данных отчета и выберите пункт **Показывать скрытые наборы данных**.</span><span class="sxs-lookup"><span data-stu-id="bbadf-135">To view the dataset that provides available values for the report parameter, right-click any blank area in the Report Data pane, and then click **Show Hidden Datasets**.</span></span> <span data-ttu-id="bbadf-136">В области данных отчета отображаются все наборы данных отчета.</span><span class="sxs-lookup"><span data-stu-id="bbadf-136">The Report Data pane displays all datasets in the report.</span></span>

## <a name="see-also"></a><span data-ttu-id="bbadf-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="bbadf-137">See Also</span></span>
 <span data-ttu-id="bbadf-138">[Analysis Services тип соединения для многомерных служб sql &#40;SSRS&#41;](analysis-services-connection-type-for-mdx-ssrs.md) [Analysis Services пользовательского интерфейса конструктора запросов многомерных выражений](analysis-services-mdx-query-designer-user-interface.md)</span><span class="sxs-lookup"><span data-stu-id="bbadf-138">[Analysis Services Connection Type for MDX &#40;SSRS&#41;](analysis-services-connection-type-for-mdx-ssrs.md) [Analysis Services MDX Query Designer User Interface](analysis-services-mdx-query-designer-user-interface.md)</span></span>


