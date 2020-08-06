---
title: Средства вычисления (вкладка «вычисления», конструктор кубов) (Analysis Services многомерных данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.calculationsview.calculationtoolspane.f1
ms.assetid: b1aa8a1a-6532-45d2-8f53-d3e211d7197a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6701a15a7d773a90e48ec39dc976b9ef579c9ec8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656795"
---
# <a name="calculation-tools-calculations-tab-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="5c23d-102">Средства вычисления (вкладка «Вычисления», конструктор кубов) (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="5c23d-102">Calculation Tools (Calculations Tab, Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="5c23d-103">С помощью панели **Средства вычисления** на вкладке **Вычисления** конструктора кубов можно исследовать метаданные, функции и шаблоны, доступные для использования в расчетах.</span><span class="sxs-lookup"><span data-stu-id="5c23d-103">Use the **Calculation Tools** pane on the **Calculations** tab in Cube Designer to explore metadata, functions, and templates available for use in calculations.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5c23d-104">Варианты</span><span class="sxs-lookup"><span data-stu-id="5c23d-104">Options</span></span>  
 <span data-ttu-id="5c23d-105">**Метаданные**</span><span class="sxs-lookup"><span data-stu-id="5c23d-105">**Metadata**</span></span>  
 <span data-ttu-id="5c23d-106">Отображает метаданные для выделенного куба.</span><span class="sxs-lookup"><span data-stu-id="5c23d-106">Displays the metadata for the selected cube.</span></span>  
  
 <span data-ttu-id="5c23d-107">Перетащите выделенный элемент на панель «Редактор скриптов», «Редактор форм вычисляемых элементов» или «Редактор форм именованных наборов» для добавления синтаксиса многомерных выражений для этого элемента в выбранном месте панели.</span><span class="sxs-lookup"><span data-stu-id="5c23d-107">Drag a selected element to the Script Editor, Calculated Member Form Editor, or Named Set Form Editor pane to include the Multidimensional Expressions (MDX) syntax for that element at the selected location in the pane.</span></span>  
  
 <span data-ttu-id="5c23d-108">**Функции**</span><span class="sxs-lookup"><span data-stu-id="5c23d-108">**Functions**</span></span>  
 <span data-ttu-id="5c23d-109">Выводит доступные функции для выражений и условий.</span><span class="sxs-lookup"><span data-stu-id="5c23d-109">Displays the functions available for expressions and conditions.</span></span>  
  
 <span data-ttu-id="5c23d-110">Перетащите выделенный элемент на панель **Редактор скриптов**, **Редактор форм вычисляемых элементов**или **Редактор форм именованных наборов** для добавления синтаксиса на языке многомерных выражений для этого элемента в выбранном месте панели.</span><span class="sxs-lookup"><span data-stu-id="5c23d-110">Drag a selected element to the **Script Editor**, **Calculated Member Form Editor**, or **Named Set Form Editor** pane to include the MDX syntax for that element at the selected location in the pane.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5c23d-111">В режиме проекта диалоговое окно **Средства вычисления** считывает сведения для этого параметра из XML-файла с именем MDXFunctions.xml, который имеется в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c23d-111">In project mode, the **Calculation Tools** dialog box reads information for this option from an XML file named MDXFunctions.xml, included with [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="5c23d-112">В режиме «в сети» сведения для этого параметра извлекаются из набора строк схемы MDSCHEMA_FUNCTIONS для этого экземпляра.</span><span class="sxs-lookup"><span data-stu-id="5c23d-112">In online mode, information for this option is retrieved from the MDSCHEMA_FUNCTIONS schema rowset for the instance.</span></span>  
  
 <span data-ttu-id="5c23d-113">**Шаблоны**</span><span class="sxs-lookup"><span data-stu-id="5c23d-113">**Templates**</span></span>  
 <span data-ttu-id="5c23d-114">Отображаются определенные заранее шаблоны, доступные вычисляемым элементам, именованным наборам и командам скрипта.</span><span class="sxs-lookup"><span data-stu-id="5c23d-114">Displays the predefined templates available for calculated members, named sets, and script commands.</span></span>  
  
 <span data-ttu-id="5c23d-115">Перетащите выделенный элемент на панель **Редактор скриптов**, **Редактор форм вычисляемых элементов**или **Редактор форм именованных наборов** для добавления синтаксиса на языке многомерных выражений для этого элемента в выбранном месте панели.</span><span class="sxs-lookup"><span data-stu-id="5c23d-115">Drag a selected element to the **Script Editor**, **Calculated Member Form Editor**, or **Named Set Form Editor** pane to include the MDX syntax for that element at the selected location in the pane.</span></span>  
  
## <a name="context-menu"></a><span data-ttu-id="5c23d-116">Контекстное меню</span><span class="sxs-lookup"><span data-stu-id="5c23d-116">Context Menu</span></span>  
 <span data-ttu-id="5c23d-117">Следующие параметры доступны в контекстном меню, которое выводится при щелчке элемента на панели **Средства вычисления** правой кнопкой мыши:</span><span class="sxs-lookup"><span data-stu-id="5c23d-117">The following options are available in the context menu displayed by right-clicking an element in the **Calculation Tools** pane:</span></span>  
  
 <span data-ttu-id="5c23d-118">**Копировать**</span><span class="sxs-lookup"><span data-stu-id="5c23d-118">**Copy**</span></span>  
 <span data-ttu-id="5c23d-119">Копирование в буфер обмена элемента, выбранного в параметре **Метаданные** или **Функции** .</span><span class="sxs-lookup"><span data-stu-id="5c23d-119">Select to copy the selected element in **Metadata** or **Functions** to the Clipboard.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5c23d-120">Этот параметр не отображается, если выбраны **Шаблоны** .</span><span class="sxs-lookup"><span data-stu-id="5c23d-120">This option is not displayed if **Templates** is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5c23d-121">Этот параметр недоступен, если выделены элементы, которые нельзя копировать, например папка **Наборы** измерения, отображаемого в параметре **Метаданные** , или функция группы папок для функции, отображаемой в параметре **Функции**.</span><span class="sxs-lookup"><span data-stu-id="5c23d-121">This option is disabled if the selected member cannot be copied, such as the **Sets** folder of a dimension displayed in **Metadata** or the function group folder for a function displayed in **Functions**.</span></span>  
  
 <span data-ttu-id="5c23d-122">**Фильтрация элементов**</span><span class="sxs-lookup"><span data-stu-id="5c23d-122">**Filter Members**</span></span>  
 <span data-ttu-id="5c23d-123">Вызов диалогового окна **Фильтрация элементов** и фильтрация элементов, отображаемых для элемента, выделенного в параметре **Метаданные**.</span><span class="sxs-lookup"><span data-stu-id="5c23d-123">Select to display the **Filter Members** dialog box and filter members displayed for the selected element in **Metadata**.</span></span> <span data-ttu-id="5c23d-124">Дополнительные сведения о диалоговом окне **Фильтрация элементов** см. в разделе [Диалоговое окно "Фильтрация элементов" (службы Analysis Services — многомерные данные)](filter-members-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="5c23d-124">For more information about the **Filter Members** dialog box, see [Filter Members Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](filter-members-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5c23d-125">Этот параметр доступен только в том случае, если выбран параметр **Метаданные** .</span><span class="sxs-lookup"><span data-stu-id="5c23d-125">This option is displayed only if **Metadata** is selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5c23d-126"> Этот параметр доступен только в том случае, если на панели **Метаданные**выбран уровень для атрибута.</span><span class="sxs-lookup"><span data-stu-id="5c23d-126">This option is enabled only if a level for an attribute is selected in **Metadata**.</span></span>  
  
 <span data-ttu-id="5c23d-127">**Добавление шаблона**</span><span class="sxs-lookup"><span data-stu-id="5c23d-127">**Add Template**</span></span>  
 <span data-ttu-id="5c23d-128">Выберите для добавления нового вычисляемого элемента, именованного набора или команды скрипта, основанной на выбранном шаблоне, в скрипт куба и открытия одного из редакторов **Редактор скриптов**, **Редактор форм вычисляемого элемента**или **Редактор форм именованных наборов** , наиболее подходящего для этой команды (в представлении формы) или для перехода к этой команде в скрипте куба на панели **Редактор скриптов** (в представлении скрипта).</span><span class="sxs-lookup"><span data-stu-id="5c23d-128">Select to add a new calculated member, named set, or script command based on the selected template to the cube script and display the **Script Editor**, **Calculated Member Form Editor**, or **Named Set Form Editor** as appropriate for that command (in form view) or to scroll the contents of the **Script Editor** pane to the location of the command in the cube script (in script view).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5c23d-129">Этот параметр доступен только в том случае, если выбран параметр **Метаданные** .</span><span class="sxs-lookup"><span data-stu-id="5c23d-129">This option is displayed only if **Metadata** is selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c23d-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="5c23d-130">See Also</span></span>  
 <span data-ttu-id="5c23d-131">[Конструктор кубов &#40;Analysis Services многомерных данных&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="5c23d-131">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="5c23d-132">[Панель инструментов &#40;вкладка «вычисления», конструктор кубов&#41; &#40;Analysis Services многомерных данных&#41;](toolbar-calculations-tab-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="5c23d-132">[Toolbar &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-calculations-tab-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="5c23d-133">[Коллекция скриптов &#40;вкладка «вычисления», конструктор кубов&#41; &#40;Analysis Services многомерных данных&#41;](script-organizer-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="5c23d-133">[Script Organizer &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](script-organizer-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="5c23d-134">[Редактор форм вычисляемых элементов вкладка «вычисления» &#40;, конструктор кубов&#41; &#40;Analysis Services многомерных данных&#41;](calculated-member-form-editor-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="5c23d-134">[Calculated Member Form Editor &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](calculated-member-form-editor-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="5c23d-135">[Редактор формы именованных наборов &#40;вкладка «вычисления», конструктор кубов&#41; &#40;Analysis Services многомерных данных&#41;](named-set-form-editor-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="5c23d-135">[Named Set Form Editor &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](named-set-form-editor-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="5c23d-136">[Редактор скриптов &#40;вкладка «вычисления», конструктор кубов&#41; &#40;Analysis Services многомерных данных&#41;](script-editor-calculations-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="5c23d-136">[Script Editor &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](script-editor-calculations-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="5c23d-137">Вычисления &#40;конструкторе кубов&#41; &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="5c23d-137">Calculations &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](calculations-cube-designer-analysis-services-multidimensional-data.md)  
  
  
