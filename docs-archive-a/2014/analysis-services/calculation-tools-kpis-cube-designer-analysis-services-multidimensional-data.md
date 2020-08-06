---
title: Средства вычисления (вкладка «Ключевые показатели эффективности», конструктор кубов) (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.kpisview.calculationtoolspane.f1
ms.assetid: c030c725-7763-4c23-9988-4b274a88fc31
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7bb8470173b0a413795fb7b5e3213bb50aa8ee43
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656793"
---
# <a name="calculation-tools-kpis-tab-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="e365f-102">Средства вычисления (вкладка «Ключевые показатели эффективности», конструктор кубов) (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="e365f-102">Calculation Tools (KPIs Tab, Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="e365f-103">С помощью панели **Средства вычисления** на вкладке **Ключевые показатели эффективности** конструктора кубов можно исследовать метаданные, функции и шаблоны, доступные для использования в ключевых показателях эффективности.</span><span class="sxs-lookup"><span data-stu-id="e365f-103">Use the **Calculation Tools** pane on the **KPIs** tab in Cube Designer to explore metadata, functions, and templates available for use in Key Performance Indicators (KPIs).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e365f-104">Данная панель отображается только в представлении формы.</span><span class="sxs-lookup"><span data-stu-id="e365f-104">This pane is displayed only in form view.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e365f-105">Варианты</span><span class="sxs-lookup"><span data-stu-id="e365f-105">Options</span></span>  
 <span data-ttu-id="e365f-106">**Метаданные**</span><span class="sxs-lookup"><span data-stu-id="e365f-106">**Metadata**</span></span>  
 <span data-ttu-id="e365f-107">Отображает метаданные для выделенного куба.</span><span class="sxs-lookup"><span data-stu-id="e365f-107">Displays the metadata for the selected cube.</span></span>  
  
 <span data-ttu-id="e365f-108">Перетащите выбранный элемент на панели **Редактор форм ключевого показателя эффективности** , чтобы включить синтаксис многомерных выражений для этого элемента в выбранном размещении на панели.</span><span class="sxs-lookup"><span data-stu-id="e365f-108">Drag a selected element to the **KPI Form Editor** pane to include the Multidimensional Expressions (MDX) syntax for that element at the selected location in the pane.</span></span>  
  
 <span data-ttu-id="e365f-109">**Функции**</span><span class="sxs-lookup"><span data-stu-id="e365f-109">**Functions**</span></span>  
 <span data-ttu-id="e365f-110">Выводит доступные функции для выражений и условий.</span><span class="sxs-lookup"><span data-stu-id="e365f-110">Displays the functions available for expressions and conditions.</span></span>  
  
 <span data-ttu-id="e365f-111">Перетащите выбранный элемент на панели **Редактор форм ключевого показателя эффективности** , чтобы включить синтаксис многомерных выражений для этого элемента в выбранном размещении на панели.</span><span class="sxs-lookup"><span data-stu-id="e365f-111">Drag a selected element to the **KPI Form Editor** pane to include the MDX syntax for that element at the selected location in the pane.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e365f-112">В режиме проекта диалоговое окно **Средства вычисления** считывает сведения для этого параметра из XML-файла с именем MDXFunctions.xml, который имеется в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e365f-112">In project mode, the **Calculation Tools** dialog box reads information for this option from an XML file named MDXFunctions.xml, included with [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="e365f-113">В режиме «в сети» сведения для этого параметра извлекаются из набора строк схемы MDSCHEMA_FUNCTIONS для этого экземпляра.</span><span class="sxs-lookup"><span data-stu-id="e365f-113">In online mode, information for this option is retrieved from the MDSCHEMA_FUNCTIONS schema rowset for the instance.</span></span>  
  
 <span data-ttu-id="e365f-114">**Шаблоны**</span><span class="sxs-lookup"><span data-stu-id="e365f-114">**Templates**</span></span>  
 <span data-ttu-id="e365f-115">Отображает предопределенные шаблоны, доступные для ключевых показателей эффективности.</span><span class="sxs-lookup"><span data-stu-id="e365f-115">Displays the predefined templates available for KPIs.</span></span>  
  
 <span data-ttu-id="e365f-116">Перетащите выбранный элемент на панели **Редактор форм ключевого показателя эффективности** , чтобы включить синтаксис многомерных выражений для этого элемента в выбранном размещении на панели.</span><span class="sxs-lookup"><span data-stu-id="e365f-116">Drag a selected element to the **KPI Form Editor** pane to include the MDX syntax for that element at the selected location in the pane.</span></span>  
  
## <a name="context-menu"></a><span data-ttu-id="e365f-117">Контекстное меню</span><span class="sxs-lookup"><span data-stu-id="e365f-117">Context Menu</span></span>  
 <span data-ttu-id="e365f-118">Следующие параметры доступны в контекстном меню, которое выводится при щелчке элемента на панели **Средства вычисления** правой кнопкой мыши:</span><span class="sxs-lookup"><span data-stu-id="e365f-118">The following options are available in the context menu displayed by right-clicking an element in the **Calculation Tools** pane:</span></span>  
  
 <span data-ttu-id="e365f-119">**Копировать**</span><span class="sxs-lookup"><span data-stu-id="e365f-119">**Copy**</span></span>  
 <span data-ttu-id="e365f-120">Копирование в буфер обмена элемента, выбранного в параметре **Метаданные** или **Функции** .</span><span class="sxs-lookup"><span data-stu-id="e365f-120">Select to copy the selected element in **Metadata** or **Functions** to the Clipboard.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e365f-121">Этот параметр не отображается, если выбраны **Шаблоны** .</span><span class="sxs-lookup"><span data-stu-id="e365f-121">This option is not displayed if **Templates** is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e365f-122">Этот параметр недоступен, если выделены элементы, которые нельзя копировать, например папка **Наборы** измерения, отображаемого в параметре **Метаданные** , или функция группы папок для функции, отображаемой в параметре **Функции**.</span><span class="sxs-lookup"><span data-stu-id="e365f-122">This option is disabled if the selected member cannot be copied, such as the **Sets** folder of a dimension displayed in **Metadata** or the function group folder for a function displayed in **Functions**.</span></span>  
  
 <span data-ttu-id="e365f-123">**Фильтрация элементов**</span><span class="sxs-lookup"><span data-stu-id="e365f-123">**Filter Members**</span></span>  
 <span data-ttu-id="e365f-124">Вызов диалогового окна **Фильтрация элементов** и фильтрация элементов, отображаемых для элемента, выделенного в параметре **Метаданные**.</span><span class="sxs-lookup"><span data-stu-id="e365f-124">Select to display the **Filter Members** dialog box and filter members displayed for the selected element in **Metadata**.</span></span> <span data-ttu-id="e365f-125">Дополнительные сведения о диалоговом окне **Фильтрация элементов** см. в разделе [Диалоговое окно "Фильтрация элементов" (службы Analysis Services — многомерные данные)](filter-members-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="e365f-125">For more information about the **Filter Members** dialog box, see [Filter Members Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](filter-members-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e365f-126">Этот параметр доступен только в том случае, если выбран параметр **Метаданные** .</span><span class="sxs-lookup"><span data-stu-id="e365f-126">This option is displayed only if **Metadata** is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e365f-127"> Этот параметр доступен только в том случае, если на панели **Метаданные**выбран уровень для атрибута.</span><span class="sxs-lookup"><span data-stu-id="e365f-127">This option is enabled only if a level for an attribute is selected in **Metadata**.</span></span>  
  
 <span data-ttu-id="e365f-128">**Добавление шаблона**</span><span class="sxs-lookup"><span data-stu-id="e365f-128">**Add Template**</span></span>  
 <span data-ttu-id="e365f-129">Добавление нового вычисляемого элемента, именованного набора или команды скрипта на основе выделенного шаблона к скрипту куба и отображение **Редактор формы ключевого показателя эффективности** в представлении формы.</span><span class="sxs-lookup"><span data-stu-id="e365f-129">Select to add a new calculated member, named set, or script command based on the selected template to the cube script and display the **KPI Form Editor** in form view.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e365f-130">Этот параметр доступен только в том случае, если выбран параметр **Метаданные** .</span><span class="sxs-lookup"><span data-stu-id="e365f-130">This option is displayed only if **Metadata** is selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e365f-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="e365f-131">See Also</span></span>  
 <span data-ttu-id="e365f-132">[Конструктор кубов &#40;Analysis Services многомерных данных&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="e365f-132">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="e365f-133">[Ключевые показатели эффективности &#40;конструктора кубов&#41; &#40;Analysis Services многомерных данных&#41;](kpis-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="e365f-133">[KPIs &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](kpis-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="e365f-134">[Панель инструментов &#40;вкладка «Ключевые показатели эффективности», конструктор кубов&#41; &#40;Analysis Services многомерных данных&#41;](toolbar-kpis-tab-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="e365f-134">[Toolbar &#40;KPIs Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-kpis-tab-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="e365f-135">[Организатор ключевых показателей эффективности &#40;вкладка "ключевые показатели эффективности", конструктор кубов&#41; &#40;Analysis Services многомерных данных&#41;](kpi-organizer-kpis-tab-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="e365f-135">[KPI Organizer &#40;KPIs Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](kpi-organizer-kpis-tab-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="e365f-136">[Редактор форм ключевых показателей эффективности &#40;вкладка "ключевые показатели эффективности", конструктор кубов&#41; &#40;Analysis Services многомерных данных&#41;](kpi-form-editor-kpis-tab-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="e365f-136">[KPI Form Editor &#40;KPIs Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](kpi-form-editor-kpis-tab-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="e365f-137">Обозреватель ключевых показателей эффективности &#40;вкладка "ключевые показатели эффективности", конструктор кубов&#41; &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="e365f-137">KPI Browser &#40;KPIs Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](kpi-browser-kpis-tab-cube-designer-analysis-services-multidimensional-data.md)  
  
  
