---
title: Анализ в Excel (вкладка «браузер», конструктор кубов) (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.browsecube.datapane.f1
- sql12.asvs.ssms.analyzeinexcel.f1
ms.assetid: 890ed457-137e-44ac-9b2c-83344a1b8fc9
author: minewiskan
ms.author: owend
ms.openlocfilehash: b9fa27ae291d40b7f5637e3968438fcaec1de03d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656900"
---
# <a name="analyze-in-excel-browser-tab-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="79f80-102">Анализ в Excel (вкладка «Браузер», конструктор кубов) (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="79f80-102">Analyze in Excel (Browser Tab, Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="79f80-103">Функция**Анализ в Excel** позволяет разработчику куба быстро определить, как проект будут видеть конечные пользователи.</span><span class="sxs-lookup"><span data-stu-id="79f80-103">**Analyze in Excel** provides the cube developer with a way to quickly review how a project would look to the end user.</span></span> <span data-ttu-id="79f80-104">Функция **Анализ в Excel** открывает Microsoft Excel, создает соединение с источником данных, которым выступает база данных рабочей области, и автоматически добавляет сводную таблицу на лист.</span><span class="sxs-lookup"><span data-stu-id="79f80-104">The **Analyze in Excel** feature opens Microsoft Excel, creates a data source connection to the workspace database, and automatically adds a PivotTable to the worksheet.</span></span> <span data-ttu-id="79f80-105">Эта функция заменяет веб-элемент управления Office на вкладке «Браузер», который в предыдущих версиях содержал внедренную сводную таблицу.</span><span class="sxs-lookup"><span data-stu-id="79f80-105">This feature replaces the Office Web Control that provided an embedded PivotTable in the Browser tab in previous releases.</span></span>  
  
 <span data-ttu-id="79f80-106">**Для просмотра данных куба выполните следующие действия.**</span><span class="sxs-lookup"><span data-stu-id="79f80-106">**To view cube data:**</span></span>  
  
1.  <span data-ttu-id="79f80-107">В среде [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]в обозревателе решений дважды щелкните куб, чтобы открыть его в конструкторе кубов.</span><span class="sxs-lookup"><span data-stu-id="79f80-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], in Solution Explorer, double-click a cube to open it in Cube Designer.</span></span>  
  
2.  <span data-ttu-id="79f80-108">Перейдите на вкладку **Браузер** .</span><span class="sxs-lookup"><span data-stu-id="79f80-108">Click the **Browser** tab.</span></span>  
  
3.  <span data-ttu-id="79f80-109">Чтобы проверить соединение, нажмите кнопку **Повторное соединение** .</span><span class="sxs-lookup"><span data-stu-id="79f80-109">Click **Reconnect** to validate the connection.</span></span>  
  
4.  <span data-ttu-id="79f80-110">Щелкните значок Excel в строке меню.</span><span class="sxs-lookup"><span data-stu-id="79f80-110">Click the Excel icon in the menu bar.</span></span>  
  
5.  <span data-ttu-id="79f80-111">Нажмите кнопку **Включить**в окне, предлагающем включить подключения к данным.</span><span class="sxs-lookup"><span data-stu-id="79f80-111">When asked to enable data connections, click **Enable**.</span></span> <span data-ttu-id="79f80-112">Открывается Excel с использованием текущего подключения к данным, на лист добавляется сводная таблица, и можно просматривать данные.</span><span class="sxs-lookup"><span data-stu-id="79f80-112">Excel opens using the current data connection, adding a PivotTable to the worksheet so that you can begin browsing your data.</span></span>  
  
 <span data-ttu-id="79f80-113">Теперь можно построить сводную таблицу в интерактивном режиме, перетаскивая меры из таблицы фактов в область «Значения», а атрибуты измерения — в области «Строки» и «Столбцы».</span><span class="sxs-lookup"><span data-stu-id="79f80-113">You can now build a PivotTable interactively by dragging measures from the fact table to the Values area, and dimension attributes to the Row and Column areas.</span></span> <span data-ttu-id="79f80-114">Имеющиеся иерархии добавляются в область «Строки» или «Столбцы».</span><span class="sxs-lookup"><span data-stu-id="79f80-114">If you have hierarchies, add them to Rows or Column areas.</span></span> <span data-ttu-id="79f80-115">Можно выполнять свертку и детализацию углублением иерархии для просмотра данных фактов на разных уровнях.</span><span class="sxs-lookup"><span data-stu-id="79f80-115">You can roll up or drill down the hierarchy to browse fact data at different levels.</span></span>  
  
 <span data-ttu-id="79f80-116">Объекты и данные просматриваются в контексте действующего пользователя или роли и перспективы.</span><span class="sxs-lookup"><span data-stu-id="79f80-116">Objects and data are viewed within the context of the effective user or role and perspective.</span></span> <span data-ttu-id="79f80-117">В Excel при выполнении запроса для соединения с источником данных используются учетные данные текущего пользователя, а не указанные на странице **Сведения об олицетворении** .</span><span class="sxs-lookup"><span data-stu-id="79f80-117">When using Excel, the credentials of the current user, not the credentials specified in the **Impersonation Information** page, are used to connect to the data source when a query is executed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="79f80-118">Для использования функции «Анализ в Excel» приложение Excel должно быть установлено на одном компьютере со средой [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="79f80-118">To use the Analyze in Excel feature, Excel must be installed on the same computer as [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="79f80-119">Если Excel не установлен на этом компьютере, можно использовать Excel на другом компьютере для подключения к кубу как к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="79f80-119">If Excel is not installed on the same computer, you can use Excel on another computer and connect to the cube as a data source.</span></span> <span data-ttu-id="79f80-120">Затем можно вручную добавить сводную таблицу на лист.</span><span class="sxs-lookup"><span data-stu-id="79f80-120">You can then manually add a PivotTable to the worksheet.</span></span> <span data-ttu-id="79f80-121">Объекты модели (таблицы, столбцы, меры и ключевые показатели эффективности) включаются в качестве полей в список полей сводной таблицы.</span><span class="sxs-lookup"><span data-stu-id="79f80-121">Model objects (tables, columns, measures, and KPIs) are included as fields in the PivotTable field list.</span></span>  
  
 <span data-ttu-id="79f80-122">Дополнительные сведения о функции **Анализ в Excel** см. в следующих ресурсах:</span><span class="sxs-lookup"><span data-stu-id="79f80-122">For more information about the **Analyze in Excel** feature, see these resources:</span></span>  
  
 [<span data-ttu-id="79f80-123">Анализ в Excel (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="79f80-123">Analyze in Excel &#40;SSAS Tabular&#41;</span></span>](tabular-models/analyze-in-excel-ssas-tabular.md)  
  
 [<span data-ttu-id="79f80-124">Анализ табличной модели в Excel (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="79f80-124">Analyze a Tabular Model in Excel &#40;SSAS Tabular&#41;</span></span>](tabular-models/analyze-a-tabular-model-in-excel-ssas-tabular.md)  
  
 [<span data-ttu-id="79f80-125">Просмотр данных и метаданных в кубе</span><span class="sxs-lookup"><span data-stu-id="79f80-125">Browse data and metadata in Cube</span></span>](multidimensional-models/browse-data-and-metadata-in-cube.md)  
  
## <a name="see-also"></a><span data-ttu-id="79f80-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="79f80-126">See Also</span></span>  
 <span data-ttu-id="79f80-127">[Обозреватель &#40;конструктор кубов&#41; &#40;Analysis Services многомерных данных&#41;](browser-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="79f80-127">[Browser &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](browser-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="79f80-128">[Панель инструментов &#40;вкладка «браузер», конструктор кубов&#41; &#40;Analysis Services многомерных данных&#41;](toolbar-browser-tab-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="79f80-128">[Toolbar &#40;Browser Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-browser-tab-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="79f80-129">[Вкладка браузера &#40;метаданных, конструктор кубов&#41; &#40;Analysis Services многомерных данных&#41;](metadata-browser-tab-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="79f80-129">[Metadata &#40;Browser Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](metadata-browser-tab-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="79f80-130">Вкладка «браузер запросов и фильтров &#40;», конструктор кубов&#41; &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="79f80-130">Query and Filter &#40;Browser Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](query-filter-browser-cube-designer-analysis-services-multidimensional-data.md)  
  
  
