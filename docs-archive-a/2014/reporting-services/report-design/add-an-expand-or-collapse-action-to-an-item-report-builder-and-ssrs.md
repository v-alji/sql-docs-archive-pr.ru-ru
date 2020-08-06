---
title: Добавление действия "Развернуть" или "Свернуть" к элементу (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 49f07ad6-242b-4861-8fc1-91ca78c36d6c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 331c6a14a4a898ffcdf86f274c00e7ad3c801ec7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729062"
---
# <a name="add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs"></a><span data-ttu-id="b7fef-102">Добавление действия "Развернуть" или "Свернуть" к элементу (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="b7fef-102">Add an Expand or Collapse Action to an Item (Report Builder and SSRS)</span></span>
  <span data-ttu-id="b7fef-103">Вы можете позволить пользователю в интерактивном режиме раскрывать или свертывать элементы отчета, а также разворачивать и сворачивать строки и столбцы, связанные с группой для таблицы или матрицы.</span><span class="sxs-lookup"><span data-stu-id="b7fef-103">You can enable a user to interactively expand or collapse report items, or expand or collapse rows and columns associated with a group for a table or matrix.</span></span> <span data-ttu-id="b7fef-104">Чтобы разрешить пользователям разворачивать и сворачивать элемент, необходимо задать свойства видимости для этого элемента.</span><span class="sxs-lookup"><span data-stu-id="b7fef-104">To allow users to expand or collapse an item, you set the visibility properties for that item.</span></span> <span data-ttu-id="b7fef-105">Настройка видимости работает в средстве просмотра отчетов HTML и иногда называется *углубленной детализацией* .</span><span class="sxs-lookup"><span data-stu-id="b7fef-105">Setting visibility works in an HTML report viewer, and is sometimes called a *drilldown* action.</span></span>  
  
 <span data-ttu-id="b7fef-106">В представлении конструктора отчетов указывается имя текстового поля, в котором необходимо отобразить значки переключения развертывания и сворачивания.</span><span class="sxs-lookup"><span data-stu-id="b7fef-106">In report design view, you specify the name of the text box where you want to display the expand and collapse toggle icons.</span></span> <span data-ttu-id="b7fef-107">В отчете, готовом для просмотра, помимо самого содержимого, в текстовом поле отображается знак «плюс» (+) или «минус» (-).</span><span class="sxs-lookup"><span data-stu-id="b7fef-107">In the rendered report, the text box displays a plus (+) or minus (-) sign in addition to its contents.</span></span> <span data-ttu-id="b7fef-108">Когда пользователь щелкает переключатель, отображение отчета обновляется, при этом элемент отчета показывается или скрывается в зависимости от текущих параметров видимости для элементов в отчете.</span><span class="sxs-lookup"><span data-stu-id="b7fef-108">When the user clicks the toggle, the report display is refreshed to show or hide the report item, based on the current visibility settings for items in the report.</span></span>  
  
 <span data-ttu-id="b7fef-109">Обычно действия развертывания и свертывания используются для отображения только сводных данных, при этом пользователь, нажав знак «плюс», может открыть и подробные данные.</span><span class="sxs-lookup"><span data-stu-id="b7fef-109">Typically, the expand and collapse action is used to initially display only summary data and to enable the user to click the plus sign to show detail data.</span></span> <span data-ttu-id="b7fef-110">Например, изначально можно скрыть таблицу, отображающую значения диаграммы, или скрыть дочерние группы таблицы с группами вложенных строк или столбцов, как в отчете с углубленной детализацией.</span><span class="sxs-lookup"><span data-stu-id="b7fef-110">For example, you can initially hide a table that displays values for a chart, or hide child groups for a table with nested row or column groups, as in a drilldown report.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-expand-and-collapse-action-to-a-group"></a><span data-ttu-id="b7fef-111">Добавление действия развертывания и свертывания к группе</span><span class="sxs-lookup"><span data-stu-id="b7fef-111">To add expand and collapse action to a group</span></span>  
  
1.  <span data-ttu-id="b7fef-112">В конструкторе отчетов щелкните таблицу или матрицу, чтобы выбрать ее.</span><span class="sxs-lookup"><span data-stu-id="b7fef-112">In report design view, click the table or matrix to select it.</span></span> <span data-ttu-id="b7fef-113">На панели группирования будут отображены группы столбцов и строк.</span><span class="sxs-lookup"><span data-stu-id="b7fef-113">The Grouping pane displays the row and column groups.</span></span>  
  
     <span data-ttu-id="b7fef-114">![Панель группирования](../media/groupingpane.png "Панель группировки")</span><span class="sxs-lookup"><span data-stu-id="b7fef-114">![Grouping Pane](../media/groupingpane.png "Grouping Pane")</span></span>  
  
     <span data-ttu-id="b7fef-115">Если панель группирования не появляется, выберите пункт меню **Вид** и нажмите **Группирование**.</span><span class="sxs-lookup"><span data-stu-id="b7fef-115">If the Grouping pane does not appear, click the **View** menu and then click **Grouping**.</span></span>  
  
2.  <span data-ttu-id="b7fef-116">Щелкните правой кнопкой в любом месте строки заголовка панели "Группирование" и выберите **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="b7fef-116">Right-click anywhere in the title bar of the Grouping pane, and then click **Advanced**.</span></span> <span data-ttu-id="b7fef-117">Режим панели «Группирование» включается для показа базовой структуры отображения строк и столбцов в области конструктора.</span><span class="sxs-lookup"><span data-stu-id="b7fef-117">The Grouping pane mode toggles to show the underlying display structure for rows and columns on the design surface.</span></span>  
  
     <span data-ttu-id="b7fef-118">![Панель группирования с меню "Расширенный режим"](../media/groupingpane-advancedmode.png "Панель группирования с меню "Расширенный режим"")</span><span class="sxs-lookup"><span data-stu-id="b7fef-118">![Grouping Pane with Advanced Mode menu](../media/groupingpane-advancedmode.png "Grouping Pane with Advanced Mode menu")</span></span>  
  
3.  <span data-ttu-id="b7fef-119">В соответствующей панели группы щелкните имя группы строк или группы столбцов, для которой необходимо скрыть связанные строки или столбцы.</span><span class="sxs-lookup"><span data-stu-id="b7fef-119">In the appropriate group pane, click the name of the row group or column group for which you want to hide the associated rows or columns.</span></span> <span data-ttu-id="b7fef-120">Выбирается группа, и на панели «Свойства» отображаются свойства **Элемент табликса** .</span><span class="sxs-lookup"><span data-stu-id="b7fef-120">The group is selected and the Properties pane shows the **Tablix Member** properties.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b7fef-121"> Если вы не видите панель "Свойства", нажмите ленту **Вид** и затем **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="b7fef-121">If you do not see the Properties pane, click **View** on the Ribbon and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="b7fef-122">В выберите `Hidden` один из следующих параметров, чтобы задать видимость этого элемента отчета при первом запуске отчета:</span><span class="sxs-lookup"><span data-stu-id="b7fef-122">In `Hidden`, choose one of the following options to set the visibility of this report item the first time you run a report:</span></span>  
  
    -   <span data-ttu-id="b7fef-123">Выберите `False` , чтобы отобразить элемент отчета.</span><span class="sxs-lookup"><span data-stu-id="b7fef-123">Select `False` to display the report item.</span></span>  
  
    -   <span data-ttu-id="b7fef-124">Выберите `True` , чтобы скрыть элемент отчета.</span><span class="sxs-lookup"><span data-stu-id="b7fef-124">Select `True` to hide the report item.</span></span>  
  
    -   <span data-ttu-id="b7fef-125">Выберите **\<Expression>** , чтобы открыть диалоговое окно **выражение** для создания выражения, вычисляемого во время выполнения для определения видимости.</span><span class="sxs-lookup"><span data-stu-id="b7fef-125">Select **\<Expression>** to open the **Expression** dialog box to create an expression that is evaluated at run time to determine the visibility.</span></span>  
  
5.  <span data-ttu-id="b7fef-126">В раскрывающемся списке **ToggleItem**выберите имя текстового поля, к которому добавляется изображение переключателя.</span><span class="sxs-lookup"><span data-stu-id="b7fef-126">In **ToggleItem**, from the drop-down box, select the name of a text box to which to add the toggle image.</span></span>  
  
     <span data-ttu-id="b7fef-127">На следующем рисунке настройка группы строк "Цвет" позволяет пользователям разворачивать и сворачивать связанные строки.</span><span class="sxs-lookup"><span data-stu-id="b7fef-127">In the following image, the Color row group is configured enable users to expand and collapse associated rows.</span></span>  
  
     <span data-ttu-id="b7fef-128">![Настройка развертываемой группы строк](../media/expandcollapse-confighiddentoggleitemwithnumbers.png "Настройка развертываемой группы строк")</span><span class="sxs-lookup"><span data-stu-id="b7fef-128">![Configuring a row group to be expanded](../media/expandcollapse-confighiddentoggleitemwithnumbers.png "Configuring a row group to be expanded")</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b7fef-129">Текстовое поле с изображением переключателя не может быть группой строк или столбцов, для которой необходимо скрыть связанные строки или столбцы.</span><span class="sxs-lookup"><span data-stu-id="b7fef-129">The text box with the toggle image cannot be the row or column group for which you want to hide the associated rows or columns.</span></span> <span data-ttu-id="b7fef-130">Текстовое поле должно находиться либо в той же группе, что и скрываемый элемент, либо в родительской группе.</span><span class="sxs-lookup"><span data-stu-id="b7fef-130">It must either be in the same group as the item that is being hidden or in an ancestor group.</span></span> <span data-ttu-id="b7fef-131">Например, чтобы включить видимость строк, связанных с дочерней группой, выберите текстовое поле в строке, связанной с родительской группой.</span><span class="sxs-lookup"><span data-stu-id="b7fef-131">For example, to toggle visibility of rows associated with a child group, select a text box in a row associated with the parent group.</span></span>  
  
6.  <span data-ttu-id="b7fef-132">Для проверки переключателя запустите отчет и щелкните текстовое поле с изображением переключателя.</span><span class="sxs-lookup"><span data-stu-id="b7fef-132">To test the toggle, run the report and click the text box with the toggle image.</span></span> <span data-ttu-id="b7fef-133">Экран отчета обновляется для отображения групп строк и столбцов с включенной видимостью.</span><span class="sxs-lookup"><span data-stu-id="b7fef-133">The report display refreshes to show row groups and column groups with their toggled visibility.</span></span>  
  
     <span data-ttu-id="b7fef-134">![Запуск отчета с развертываемой группой строк](../media/expandcollapse-runreport-rowgroup.png "Запуск отчета с развертываемой группой строк")</span><span class="sxs-lookup"><span data-stu-id="b7fef-134">![Running report with expandable row group](../media/expandcollapse-runreport-rowgroup.png "Running report with expandable row group")</span></span>  
  
### <a name="to-add-expand-and-collapse-action-to-a-report-item"></a><span data-ttu-id="b7fef-135">Добавление действия развертывания и свертывания к элементу отчета</span><span class="sxs-lookup"><span data-stu-id="b7fef-135">To add expand and collapse action to a report item</span></span>  
  
1.  <span data-ttu-id="b7fef-136">В режиме конструктора отчетов щелкните правой кнопкой мыши элемент отчета, который нужно показать или скрыть, и выберите пункт *\<report item>* **свойства**.</span><span class="sxs-lookup"><span data-stu-id="b7fef-136">In report design view, right-click the report item to show or hide, and then click *\<report item>* **Properties**.</span></span> <span data-ttu-id="b7fef-137">*\<report item>* Откроется диалоговое окно « **свойства** » для элемента отчета.</span><span class="sxs-lookup"><span data-stu-id="b7fef-137">The *\<report item>* **Properties** dialog box for the report item opens.</span></span>  
  
2.  <span data-ttu-id="b7fef-138">Щелкните **Видимость**.</span><span class="sxs-lookup"><span data-stu-id="b7fef-138">Click **Visibility**.</span></span>  
  
3.  <span data-ttu-id="b7fef-139">В пункте **При первоначальном запуске отчета**выберите один из следующих параметров для установки видимости данного элемента отчета при первом запуске отчета:</span><span class="sxs-lookup"><span data-stu-id="b7fef-139">In **When the report is initially run**, choose one of the following options to set the visibility of this report item the first time you run a report:</span></span>  
  
    -   <span data-ttu-id="b7fef-140">Для отображения элемента отчета выберите **Показать** .</span><span class="sxs-lookup"><span data-stu-id="b7fef-140">Select **Show** to display the report item.</span></span>  
  
    -   <span data-ttu-id="b7fef-141">Для скрытия элемента отчета выберите **Скрыть** .</span><span class="sxs-lookup"><span data-stu-id="b7fef-141">Select **Hide** to hide the report item.</span></span>  
  
    -   <span data-ttu-id="b7fef-142">Для использования выражения, вычисляемого во время выполнения для определения видимости, выберите **Отображать или скрывать в зависимости от выражения** .</span><span class="sxs-lookup"><span data-stu-id="b7fef-142">Select **Show or hide based on an expression** to use an expression evaluated at run time to determine the visibility.</span></span> <span data-ttu-id="b7fef-143">Нажмите кнопку (**FX**), чтобы открыть диалоговое окно **выражение** для создания выражения.</span><span class="sxs-lookup"><span data-stu-id="b7fef-143">Click (**fx**) to open the **Expression** dialog box to create an expression.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="b7fef-144">При задании выражения для видимости настраивается свойство Hidden элемента отчета.</span><span class="sxs-lookup"><span data-stu-id="b7fef-144">When you specify an expression for visibility, you are setting the Hidden property of the report item.</span></span> <span data-ttu-id="b7fef-145">Выражение вычисляет значение `Boolean` (при значении `True` элемент скрыт, а при значении `False` отображается).</span><span class="sxs-lookup"><span data-stu-id="b7fef-145">The expression evaluates to a `Boolean` value of `True` to hide the item and `False` to show the item.</span></span>  
  
4.  <span data-ttu-id="b7fef-146">Из раскрывающегося списка **Отображение может переключаться этим элементом отчета**выберите имя текстового поля в отчете, в котором будет отображаться изображение переключателя, например Textbox1, или введите его вручную.</span><span class="sxs-lookup"><span data-stu-id="b7fef-146">In **Display can be toggled by this report item**, from the drop-down box, type or select the name of a text box in the report in which to display a toggle image; for example, Textbox1.</span></span>  
  
     <span data-ttu-id="b7fef-147">На следующем рисунке таблица настроена таким образом, чтобы пользователи могли разворачивать и сворачивать ее.</span><span class="sxs-lookup"><span data-stu-id="b7fef-147">In the following image, the table is configured to enable users to expand and collapse it.</span></span> <span data-ttu-id="b7fef-148">Отображение таблицы переключается с помощью текстового поля таблицы продуктов.</span><span class="sxs-lookup"><span data-stu-id="b7fef-148">The display of the table is toggled by the Products Table text box.</span></span>  
  
     <span data-ttu-id="b7fef-149">![Настройка развертываемой таблицы отчетов](../media/expandcollapse-reporttable.png "Настройка развертываемой таблицы отчетов")</span><span class="sxs-lookup"><span data-stu-id="b7fef-149">![Configure a report table to be expanded](../media/expandcollapse-reporttable.png "Configure a report table to be expanded")</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b7fef-150">Выбранное текстовое поле должно находиться в текущей области или в области, которая находится в текущей области, для этого элемента отчета (вплоть до самого текста отчета).</span><span class="sxs-lookup"><span data-stu-id="b7fef-150">The text box that you choose must be in the current or containing scope for this report item (up to and including the report body).</span></span> <span data-ttu-id="b7fef-151">Например, чтобы переключить видимость диаграммы, выберите текстовое поле в той же области, где находится эта диаграмма, например в тексте отчета или в прямоугольнике.</span><span class="sxs-lookup"><span data-stu-id="b7fef-151">For example, to toggle visibility of a chart, select a text box that is in the same containing scope as the chart; for example, the report body or a rectangle.</span></span> <span data-ttu-id="b7fef-152">Текстовое поле должно находиться в той же иерархии контейнеров или выше.</span><span class="sxs-lookup"><span data-stu-id="b7fef-152">The text box must be in the same container hierarchy or higher.</span></span>  
  
5.  <span data-ttu-id="b7fef-153">Для проверки переключателя запустите отчет и щелкните текстовое поле с изображением переключателя.</span><span class="sxs-lookup"><span data-stu-id="b7fef-153">To test the toggle, run the report and click the text box with the toggle image.</span></span> <span data-ttu-id="b7fef-154">Экран отчета обновляется для отображения элементов отчета со включенной видимостью.</span><span class="sxs-lookup"><span data-stu-id="b7fef-154">The report display refreshes to show report items with their toggled visibility.</span></span>  
  
     <span data-ttu-id="b7fef-155">![Запуск отчета с развертываемой таблицей](../media/expandcollapse-runreport-reporttable.png "Запуск отчета с развертываемой таблицей")</span><span class="sxs-lookup"><span data-stu-id="b7fef-155">![Running report with an expanding table](../media/expandcollapse-runreport-reporttable.png "Running report with an expanding table")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7fef-156">См. также:</span><span class="sxs-lookup"><span data-stu-id="b7fef-156">See Also</span></span>  
 <span data-ttu-id="b7fef-157">[&#40;действия углубленной детализации построитель отчетов и службы SSRS&#41;](drilldown-action-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b7fef-157">[Drilldown Action &#40;Report Builder and SSRS&#41;](drilldown-action-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="b7fef-158">Скрытие элемента (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="b7fef-158">Hide an Item &#40;Report Builder and SSRS&#41;</span></span>](../report-builder/hide-an-item-report-builder-and-ssrs.md)  
  
  
