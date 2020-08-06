---
title: Просмотр развернутого куба | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 849c6109-1453-4fe4-a892-c49a982cfadb
author: minewiskan
ms.author: owend
ms.openlocfilehash: b876c8b2876aaf4ad28b0f4ea3fb8bab32cd787b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665649"
---
# <a name="browsing-the-deployed-cube"></a><span data-ttu-id="edc14-102">Просмотр развернутого куба</span><span class="sxs-lookup"><span data-stu-id="edc14-102">Browsing the Deployed Cube</span></span>
  <span data-ttu-id="edc14-103">В этой задаче будет проводиться просмотр куба [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial.</span><span class="sxs-lookup"><span data-stu-id="edc14-103">In the following task, you browse the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span> <span data-ttu-id="edc14-104">Так как при проведении анализа сравниваются несколько измерений, для просмотра данных воспользуемся сводной таблицей Excel.</span><span class="sxs-lookup"><span data-stu-id="edc14-104">Because our analysis compares measure across multiple dimensions, you will use an Excel PivotTable to browse your data.</span></span> <span data-ttu-id="edc14-105">Разместим в сводной таблице информацию о клиенте, дате и продукте на разных осях, чтобы было видно, как изменяются продажи через Интернет в различные периоды времени, для различных групп клиентов и продуктовых линий.</span><span class="sxs-lookup"><span data-stu-id="edc14-105">Using a PivotTable lets you place customer, date, and product information on different axes so that you can see how Internet Sales change when viewed across specific time periods, customer demographics, and product lines.</span></span>  
  
### <a name="to-browse-the-deployed-cube"></a><span data-ttu-id="edc14-106">Просмотр развернутого куба</span><span class="sxs-lookup"><span data-stu-id="edc14-106">To browse the deployed cube</span></span>  
  
1.  <span data-ttu-id="edc14-107">Чтобы переключиться в конструктор кубов в [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] , дважды щелкните куб \*\* [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial\*\* в папке **Кубы** Обозреватель решений.</span><span class="sxs-lookup"><span data-stu-id="edc14-107">To switch to Cube Designer in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], double-click the **[!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial** cube in the **Cubes** folder of the Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="edc14-108">Перейдите на вкладку **Браузер** и на панели инструментов конструктора нажмите кнопку **Повторное соединение** .</span><span class="sxs-lookup"><span data-stu-id="edc14-108">Open the **Browser** tab, and then click the **Reconnect** button on the toolbar of the designer.</span></span>  
  
3.  <span data-ttu-id="edc14-109">Щелкните значок Excel, чтобы запустить программу Excel, используя в качестве источника базу данных рабочей области.</span><span class="sxs-lookup"><span data-stu-id="edc14-109">Click the Excel icon to launch Excel using the workspace database as the data source.</span></span> <span data-ttu-id="edc14-110">Нажмите кнопку **Включить**при появлении запроса на подключение к данным.</span><span class="sxs-lookup"><span data-stu-id="edc14-110">When prompted to enable connections, click **Enable**.</span></span>  
  
4.  <span data-ttu-id="edc14-111">В списке полей сводной таблицы разверните группу **Продажи через Интернет**, а затем перетащите показатель **Объем продаж** в область **Значения** .</span><span class="sxs-lookup"><span data-stu-id="edc14-111">In the PivotTable Field List, expand **Internet Sales**, and then drag the **Sales Amount** measure to the **Values** area.</span></span>  
  
5.  <span data-ttu-id="edc14-112">В списке полей сводной таблицы разверните узел **Продукт**.</span><span class="sxs-lookup"><span data-stu-id="edc14-112">In the PivotTable Field List, expand **Product**.</span></span>  
  
6.  <span data-ttu-id="edc14-113">Перетащите пользовательскую иерархию **Product Model Lines** в область **Столбцы** .</span><span class="sxs-lookup"><span data-stu-id="edc14-113">Drag the **Product Model Lines** user hierarchy to the **Columns** area.</span></span>  
  
7.  <span data-ttu-id="edc14-114">В списке полей сводной таблицы разверните узел **Клиент**, затем узел **Местоположение**и перетащите иерархию **Customer Geography** из папки отображения расположения в область **Строки** .</span><span class="sxs-lookup"><span data-stu-id="edc14-114">In the PivotTable Field List, expand **Customer**, expand **Location**, and then drag the **Customer Geography** hierarchy from the Location display folder in the Customer dimension to the **Rows** area.</span></span>  
  
8.  <span data-ttu-id="edc14-115">В списке полей сводной таблицы разверните узел **Дата заказа**и перетащите иерархию **Order Date.Calendar Date** в область **Фильтр отчета** .</span><span class="sxs-lookup"><span data-stu-id="edc14-115">In the PivotTable Field List, expand **Order Date**, and then drag the **Order Date.Calendar Date** hierarchy to the **Report Filter** area.</span></span>  
  
9. <span data-ttu-id="edc14-116">Нажмите стрелку справа от фильтра **Order Date.Calendar Date** на панели данных, снимите флажок для уровня **(Все)** , последовательно разверните узлы **2006**, **H1 CY 2006**и **Q1 CY 2006**, установите флажок **Февраль 2006**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="edc14-116">Click the arrow to the right of the **Order Date.Calendar Date** filter in the data pane, clear the check box for the **(All)** level, expand **2006**, expand **H1 CY 2006**, expand **Q1 CY 2006**, select the check box for **February 2006**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="edc14-117">На экран будут выведены продажи через Интернет по регионам и линейкам продуктов в феврале 2006 г., как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="edc14-117">Internet sales by region and product line for the month of February, 2006 appear as shown in the following image.</span></span>  
  
     <span data-ttu-id="edc14-118">![«Продажи через Интернет» по регионам и сериям продуктов](../../2014/tutorials/media/l3-cube-browser-finish.gif "«Продажи через Интернет» по регионам и сериям продуктов")</span><span class="sxs-lookup"><span data-stu-id="edc14-118">![Internet sales by region and product line](../../2014/tutorials/media/l3-cube-browser-finish.gif "Internet sales by region and product line")</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="edc14-119">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="edc14-119">Next Lesson</span></span>  
 [<span data-ttu-id="edc14-120">Занятие 4: Определение расширенных свойств атрибутов и измерений</span><span class="sxs-lookup"><span data-stu-id="edc14-120">Lesson 4: Defining Advanced Attribute and Dimension Properties</span></span>](lesson-4-defining-advanced-attribute-and-dimension-properties.md)  
  
  
