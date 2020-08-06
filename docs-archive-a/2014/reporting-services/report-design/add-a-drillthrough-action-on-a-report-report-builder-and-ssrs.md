---
title: Добавление действия детализации в отчет (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 153729c4-d01e-4629-b78f-0cfd5a7f83da
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a429380f677a309e4e1437a2e3c5036bb4e8a455
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657519"
---
# <a name="add-a-drillthrough-action-on-a-report-report-builder-and-ssrs"></a><span data-ttu-id="e841c-102">Добавление действия детализации в отчет (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="e841c-102">Add a Drillthrough Action on a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="e841c-103">Отчеты, открывающиеся при щелчке ссылки в основном отчете, называются *детализированными отчетами*.</span><span class="sxs-lookup"><span data-stu-id="e841c-103">The report that opens when you click the link in the main report is known as a *drillthrough report*.</span></span> <span data-ttu-id="e841c-104">Данная ссылка детализации активирует действие детализации.</span><span class="sxs-lookup"><span data-stu-id="e841c-104">This drillthrough link enables a drillthrough action.</span></span>  
  
 <span data-ttu-id="e841c-105">Детализированные отчеты должны публиковаться на том же сервере отчетов, что и основной отчет, однако они могут находиться в разных папках.</span><span class="sxs-lookup"><span data-stu-id="e841c-105">Drillthrough reports must be published to the same report server as the main report, but they can be in different folders.</span></span> <span data-ttu-id="e841c-106">Предусмотрена возможность добавить ссылку детализации к любому элементу, имеющему свойство **Action** , например к текстовому полю, изображению или точкам данных на диаграмме.</span><span class="sxs-lookup"><span data-stu-id="e841c-106">You can add a drillthrough link to any item that has an **Action** property, such as a text box, an image, or data points on a chart.</span></span>  
  
 <span data-ttu-id="e841c-107">Чтобы добавить ссылку детализации в отчет, необходимо сначала создать детализированный отчет, на который будет ссылаться основной отчет.</span><span class="sxs-lookup"><span data-stu-id="e841c-107">To add a drillthrough link to a report, you must first create the drillthrough report that the main report will link to.</span></span> <span data-ttu-id="e841c-108">Детализированный отчет обычно содержит подробные сведения об элементе, содержащемся в исходном сводном отчете, и часто содержит параметры, фильтрующие детализированный отчет на основе параметров, переданных из основного отчета.</span><span class="sxs-lookup"><span data-stu-id="e841c-108">A drillthrough report commonly contains details about an item that is contained in the original summary report, and often contains parameters that filter the drillthrough report based on parameters passed to it from the main report.</span></span> <span data-ttu-id="e841c-109">Дополнительные сведения о создании детализированного отчета см. в разделе [Детализированные отчеты (построитель отчетов и службы SSRS)](drillthrough-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e841c-109">For more information on creating the drillthrough report, see [Drillthrough Reports &#40;Report Builder and SSRS&#41;](drillthrough-reports-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-drillthrough-action"></a><span data-ttu-id="e841c-110">Добавление действия детализации</span><span class="sxs-lookup"><span data-stu-id="e841c-110">To add a drillthrough action</span></span>  
  
1.  <span data-ttu-id="e841c-111">В режиме конструктора щелкните правой кнопкой мыши текстовое поле, рисунок или диаграмму, к которым нужно добавить ссылку, и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="e841c-111">In Design view, right-click the text box, image, or chart to which you want to add a link and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="e841c-112">В диалоговом окне **Свойства** для элемента нажмите кнопку **Действие**.</span><span class="sxs-lookup"><span data-stu-id="e841c-112">In the item's **Properties** dialog box, click **Action**.</span></span>  
  
3.  <span data-ttu-id="e841c-113">Выберите **Перейти к отчету**.</span><span class="sxs-lookup"><span data-stu-id="e841c-113">Select **Go to report**.</span></span> <span data-ttu-id="e841c-114">В диалоговом окне появятся дополнительные области, соответствующие данному параметру.</span><span class="sxs-lookup"><span data-stu-id="e841c-114">Additional sections appear in the dialog box for this option.</span></span>  
  
4.  <span data-ttu-id="e841c-115">В поле **Выбор отчета**нажмите кнопку **Обзор** , чтобы найти местоположение отчета, к которому необходимо перейти, или введите имя отчета.</span><span class="sxs-lookup"><span data-stu-id="e841c-115">In **Specify a report**, click **Browse** to locate the report that you want to jump to, or type the name of the report.</span></span> <span data-ttu-id="e841c-116">Также можно нажать кнопку выражения (**fx**), чтобы создать выражение для имени отчета.</span><span class="sxs-lookup"><span data-stu-id="e841c-116">Alternatively, click the expression (**fx**) button to create an expression for the report name.</span></span>  
  
     <span data-ttu-id="e841c-117">В собственном режиме и режиме интеграции с SharePoint используется различный формат пути к детализированному отчету.</span><span class="sxs-lookup"><span data-stu-id="e841c-117">The format of the path to the drillthrough report differs for native and SharePoint integrated mode.</span></span> <span data-ttu-id="e841c-118">Если перейти к отчету, будет создан путь правильного формата.</span><span class="sxs-lookup"><span data-stu-id="e841c-118">If you browse to the report, a path of the correct format is provided.</span></span> <span data-ttu-id="e841c-119">Дополнительные сведения см. в разделе [Указание путей к внешним элементам (построитель отчетов и службы SSRS)](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e841c-119">For more information, see [Specifying Paths to External Items &#40;Report Builder and SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span></span>  
  
     <span data-ttu-id="e841c-120">Чтобы указать параметры для детализированного отчета, выполните следующий шаг.</span><span class="sxs-lookup"><span data-stu-id="e841c-120">If you have to specify parameters for the drillthrough report, follow the next step.</span></span>  
  
5.  <span data-ttu-id="e841c-121">В области **Использовать эти параметры при выполнении отчета**нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e841c-121">In **Use these parameters to run the report**, click **Add**.</span></span> <span data-ttu-id="e841c-122">В сетку параметров добавится новая строка.</span><span class="sxs-lookup"><span data-stu-id="e841c-122">A new row is added to the parameter grid.</span></span>  
  
    -   <span data-ttu-id="e841c-123">В текстовом поле **Имя** щелкните раскрывающийся список или введите имя параметра отчета для детализированного отчета.</span><span class="sxs-lookup"><span data-stu-id="e841c-123">In the **Name** text box, click the drop-down list or type the name of the report parameter in the drillthrough report.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="e841c-124">Имена в списке параметров должны точно совпадать с параметрами, ожидаемыми целевым отчетом.</span><span class="sxs-lookup"><span data-stu-id="e841c-124">The names in the parameter list must match the expected parameters in the target report exactly.</span></span> <span data-ttu-id="e841c-125">Например, должен совпадать регистр в именах параметров.</span><span class="sxs-lookup"><span data-stu-id="e841c-125">For example, parameter names must match by case.</span></span> <span data-ttu-id="e841c-126">Если имена не совпадают или если ожидаемый параметр не указан, в детализированном отчете возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="e841c-126">If the names do not match, or if an expected parameter is not listed, the drillthrough report fails.</span></span>  
  
    -   <span data-ttu-id="e841c-127">В поле **Значение**введите или выберите значение, передаваемое параметру детализированного отчета.</span><span class="sxs-lookup"><span data-stu-id="e841c-127">In **Value**, type or select the value to pass to the parameter in the drillthrough report.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="e841c-128">Значения могут содержать выражение, которое вычисляет значение, передаваемое как параметр отчета.</span><span class="sxs-lookup"><span data-stu-id="e841c-128">Values can contain an expression that evaluates to a value to pass to the report parameter.</span></span> <span data-ttu-id="e841c-129">Выражения в списке значений включают список полей текущего отчета.</span><span class="sxs-lookup"><span data-stu-id="e841c-129">The expressions in the value list include the field list for the current report.</span></span>  
  
     <span data-ttu-id="e841c-130">Сведения о том, как скрыть параметры в отчетах, см. в разделе [Добавление, изменение или удаление параметра отчета (построитель отчетов и службы SSRS)](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e841c-130">For information on how to hide parameters in reports, see [Add, Change, or Delete a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md).</span></span>  
  
6.  <span data-ttu-id="e841c-131">В случае с текстовыми полями желательно указать пользователю на то, что текст является ссылкой, изменив цвет и стиль текста на вкладке **Главная** на ленте (необязательно).</span><span class="sxs-lookup"><span data-stu-id="e841c-131">(Optional) For text boxes, it is helpful to indicate to the user that the text is a link by changing the color and effect of the text on the **Home** tab of the Ribbon.</span></span>  
  
7.  <span data-ttu-id="e841c-132">Для проверки ссылки надо запустить отчет и щелкнуть элемент отчета, для которого была задана ссылка.</span><span class="sxs-lookup"><span data-stu-id="e841c-132">To test the link, run the report and click the report item that you set this link on.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e841c-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="e841c-133">See Also</span></span>  
 <span data-ttu-id="e841c-134">[Диалоговое окно "Свойства действия" (построитель отчетов и службы SSRS)](../action-properties-dialog-box-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e841c-134">[Action Properties Dialog Box &#40;Report Builder and SSRS&#41;](../action-properties-dialog-box-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e841c-135">[Форматирование точек данных на диаграмме (построитель отчетов и службы SSRS)](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e841c-135">[Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="e841c-136">Отображение всплывающих подсказок для ряда (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="e841c-136">Show ToolTips on a Series &#40;Report Builder and SSRS&#41;</span></span>](show-tooltips-on-a-series-report-builder-and-ssrs.md)  
  
  
