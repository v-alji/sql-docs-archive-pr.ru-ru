---
title: Диалоговое окно «Свойства действия» (построитель отчетов и службы SSRS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.shared.action.f1
- "10413"
- "10504"
- sql12.rtp.rptdesigner.calculatedseriesproperties.action.f1
- sql12.rtp.rptdesigner.pictureproperties.action.f1
- sql12.rtp.rptdesigner.actionproperties.f1
- sql12.rtp.rptdesigner.charttitleproperties.action.f1
- "10133"
- "10052"
- "10147"
- sql12.rtp.rptdesigner.chartproperties.action.f1
- "10122"
- sql12.rtp.rptdesigner.serieslabelproperties.action.f1
- sql12.rtp.rptdesigner.textboxproperties.action.f1
- "10162"
- "10168"
- sql12.rtp.rptdesigner.textproperties.action.f1
- sql12.rtp.rptdesigner.placeholderproperties.action.f1
- "10250"
- "10129"
- "10244"
- sql12.rtp.rptdesigner.seriesproperties.action.f1
ms.assetid: 2c5d915b-4f97-42cf-b8f1-49ca3ff3d0f9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 77b51af0763010676b95fcedb433ab963fc7fcdf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665880"
---
# <a name="action-properties-dialog-box-report-builder-and-ssrs"></a><span data-ttu-id="510f7-102">Диалоговое окно «Свойства действия» (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="510f7-102">Action Properties Dialog Box (Report Builder and SSRS)</span></span>
  <span data-ttu-id="510f7-103">С помощью диалогового окна **Действие** можно включить параметры гиперссылок для диаграммы, датчика и элементов карты, поддерживающих ссылки.</span><span class="sxs-lookup"><span data-stu-id="510f7-103">The **Action** dialog box can be used to enable hyperlink options for a chart, gauge, and map elements that support links.</span></span> <span data-ttu-id="510f7-104">Определите действие, чтобы дать пользователю возможность щелкнуть отчет и перейти по URL-адресу к другому отчету на том же сервере отчетов или на сайте SharePoint, интегрированном с сервером отчетов, или к другому расположению в текущем отчете.</span><span class="sxs-lookup"><span data-stu-id="510f7-104">Define an action so that a user can click on the report and link to a URL, to a different report on the same report server or on a SharePoint site that is integrated with a report server, or to a different location in the same report.</span></span>  
  
## <a name="options"></a><span data-ttu-id="510f7-105">Варианты</span><span class="sxs-lookup"><span data-stu-id="510f7-105">Options</span></span>  
 <span data-ttu-id="510f7-106">**Включить как действие**</span><span class="sxs-lookup"><span data-stu-id="510f7-106">**Enable as an action**</span></span>  
 <span data-ttu-id="510f7-107">Выберите параметр, указывающий на действие, которое будет выполняться при щелчке изображения мышью.</span><span class="sxs-lookup"><span data-stu-id="510f7-107">Select an option to indicate the action to perform when the user clicks the item.</span></span>  
  
 <span data-ttu-id="510f7-108">**None**</span><span class="sxs-lookup"><span data-stu-id="510f7-108">**None**</span></span>  
 <span data-ttu-id="510f7-109">Выберите этот параметр, чтобы указать на отсутствие у элемента действия.</span><span class="sxs-lookup"><span data-stu-id="510f7-109">Choose this option to indicate that the item has no action.</span></span>  
  
 <span data-ttu-id="510f7-110">**Перейти к отчету**</span><span class="sxs-lookup"><span data-stu-id="510f7-110">**Go to report**</span></span>  
 <span data-ttu-id="510f7-111">Выберите этот параметр, чтобы создать ссылку на детализированный отчет, расположенный на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="510f7-111">Choose this option to create a link to a drillthrough report that is located on a report server.</span></span> <span data-ttu-id="510f7-112">После выбора пункта **Перейти к отчету**появляются следующие дополнительные параметры.</span><span class="sxs-lookup"><span data-stu-id="510f7-112">The following additional options appear when you select **Go to report**.</span></span>  
  
 <span data-ttu-id="510f7-113">**Выберите отчет**</span><span class="sxs-lookup"><span data-stu-id="510f7-113">**Specify a report**</span></span>  
 <span data-ttu-id="510f7-114">Введите или выберите имя отчета, который будет использован в качестве детализированного.</span><span class="sxs-lookup"><span data-stu-id="510f7-114">Type or select the name of the report that you want to use as a drillthrough report.</span></span> <span data-ttu-id="510f7-115">Детализированные отчеты должны располагаться на том же сервере, что и данный отчет.</span><span class="sxs-lookup"><span data-stu-id="510f7-115">Drillthrough reports must be on the same report server as this report.</span></span>  
  
 <span data-ttu-id="510f7-116">Для отчета, который опубликован на сервере отчетов, настроенном для работы в собственном режиме, используется полный или относительный путь без расширения имени файла.</span><span class="sxs-lookup"><span data-stu-id="510f7-116">For a report published to a report server configured for native mode, use a full or relative path without the file name extension.</span></span> <span data-ttu-id="510f7-117">Если отчет находится в той же папке, что и текущий отчет, указывается только имя отчета.</span><span class="sxs-lookup"><span data-stu-id="510f7-117">If the report is in the same folder as the current report, use the name of the report only.</span></span> <span data-ttu-id="510f7-118">Если отчет находится в другой папке на том же сервере отчетов, используйте относительный путь к отчету.</span><span class="sxs-lookup"><span data-stu-id="510f7-118">If the report is in a different folder on the same report server, use a relative path or a full path.</span></span> <span data-ttu-id="510f7-119">Относительный путь к отчету начинается с текущей папки и проходит до иерархии папок, например ../Folder2/Report1.</span><span class="sxs-lookup"><span data-stu-id="510f7-119">A relative path starts from the current folder and moves up the folder hierarchy, for example, ../Folder2/Report1.</span></span> <span data-ttu-id="510f7-120">Полный путь начинается с /, домашней папки.</span><span class="sxs-lookup"><span data-stu-id="510f7-120">A full path starts from /, the Home folder.</span></span> <span data-ttu-id="510f7-121">Например, /Reports/Report1.</span><span class="sxs-lookup"><span data-stu-id="510f7-121">For example, /Reports/Report1.</span></span>  
  
 <span data-ttu-id="510f7-122">Для отчета, который опубликован на сервере отчетов, настроенном для работы в режиме интеграции с SharePoint, используется полный URL-адрес, включая расширение имени файла (RDL).</span><span class="sxs-lookup"><span data-stu-id="510f7-122">For a report published to a report server configured in SharePoint integrated mode, use a fully qualified URL including the file name extension (.rdl).</span></span> <span data-ttu-id="510f7-123">Например, http:// *\<SharePointservername>/\<site>* /Documents/Report1.RDL.</span><span class="sxs-lookup"><span data-stu-id="510f7-123">For example, http://*\<SharePointservername>/\<site>*/Documents/Report1.rdl.</span></span> <span data-ttu-id="510f7-124">Относительные пути не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="510f7-124">Relative paths are not supported.</span></span>  
  
 <span data-ttu-id="510f7-125">Дополнительные сведения см. в разделе [Указание путей к внешним элементам (построитель отчетов и службы SSRS)](report-design/specifying-paths-to-external-items-report-builder-and-ssrs.md) в [документации по построителю отчетов](https://go.microsoft.com/fwlink/?LinkId=154494) на сайте msdn.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="510f7-125">For more information, see [Specifying Paths to External Items &#40;Report Builder and SSRS&#41;](report-design/specifying-paths-to-external-items-report-builder-and-ssrs.md) in the [Report Builder documentation](https://go.microsoft.com/fwlink/?LinkId=154494) on msdn.microsoft.com.</span></span>  
  
 <span data-ttu-id="510f7-126">**Использовать эти параметры при выполнении отчета**</span><span class="sxs-lookup"><span data-stu-id="510f7-126">**Use these parameters to run the report**</span></span>  
 <span data-ttu-id="510f7-127">Добавьте список параметров для передачи детализированному отчету.</span><span class="sxs-lookup"><span data-stu-id="510f7-127">Add a list of parameters to pass to the drillthrough report.</span></span> <span data-ttu-id="510f7-128">Имена параметров должны совпадать с параметрами, определенными для целевого отчета.</span><span class="sxs-lookup"><span data-stu-id="510f7-128">The parameter names must match the parameters defined for the target report.</span></span> <span data-ttu-id="510f7-129">Добавление и удаление параметров производится при помощи кнопок **Добавить** и **Удалить** , а изменение их порядка в списке — стрелками вверх и вниз.</span><span class="sxs-lookup"><span data-stu-id="510f7-129">Use the **Add** and **Delete** buttons to add and remove parameters and use the up and down arrows to order the list of parameters.</span></span>  
  
 <span data-ttu-id="510f7-130">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="510f7-130">**Add**</span></span>  
 <span data-ttu-id="510f7-131">Добавить параметр для передачи детализированному отчету.</span><span class="sxs-lookup"><span data-stu-id="510f7-131">Add a new parameter to pass to the drillthrough report.</span></span>  
  
 <span data-ttu-id="510f7-132">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="510f7-132">**Delete**</span></span>  
 <span data-ttu-id="510f7-133">Удалить параметр детализированного отчета.</span><span class="sxs-lookup"><span data-stu-id="510f7-133">Delete a parameter for the drillthrough report.</span></span>  
  
 <span data-ttu-id="510f7-134">**Стрелка вверх**</span><span class="sxs-lookup"><span data-stu-id="510f7-134">**Up arrow**</span></span>  
 <span data-ttu-id="510f7-135">Переместить параметр в списке вверх.</span><span class="sxs-lookup"><span data-stu-id="510f7-135">Move the parameter up in the list.</span></span>  
  
 <span data-ttu-id="510f7-136">**Стрелка вниз**</span><span class="sxs-lookup"><span data-stu-id="510f7-136">**Down arrow**</span></span>  
 <span data-ttu-id="510f7-137">Переместить параметр в списке вниз.</span><span class="sxs-lookup"><span data-stu-id="510f7-137">Move the parameter down in the list.</span></span>  
  
 <span data-ttu-id="510f7-138">**имя**;</span><span class="sxs-lookup"><span data-stu-id="510f7-138">**Name**</span></span>  
 <span data-ttu-id="510f7-139">Введите текст, представляющий имя параметра, определенного в детализированном отчете.</span><span class="sxs-lookup"><span data-stu-id="510f7-139">Type text that is the name of a parameter defined in the drillthrough report.</span></span>  
  
 <span data-ttu-id="510f7-140">**Значение**</span><span class="sxs-lookup"><span data-stu-id="510f7-140">**Value**</span></span>  
 <span data-ttu-id="510f7-141">Введите или выберите значение именованного параметра для передачи детализированному отчету.</span><span class="sxs-lookup"><span data-stu-id="510f7-141">Type or select a value to pass for the named parameter in the drillthrough report.</span></span> <span data-ttu-id="510f7-142">Нажмите кнопку **выражение** (*FX*), чтобы изменить выражение.</span><span class="sxs-lookup"><span data-stu-id="510f7-142">Click the **Expression** (*fx*) button to edit the expression.</span></span>  
  
 <span data-ttu-id="510f7-143">**Пропустить**</span><span class="sxs-lookup"><span data-stu-id="510f7-143">**Omit**</span></span>  
 <span data-ttu-id="510f7-144">Выберите, чтобы при запуске этот параметр не обрабатывался.</span><span class="sxs-lookup"><span data-stu-id="510f7-144">Select to prevent the parameter from running.</span></span> <span data-ttu-id="510f7-145">По умолчанию этот флажок снят и неактивен.</span><span class="sxs-lookup"><span data-stu-id="510f7-145">By default, this check box is cleared and not active.</span></span> <span data-ttu-id="510f7-146">Чтобы установить этот флажок, нажмите кнопку **Выражение** (*fx*) и введите **True** или создайте выражение.</span><span class="sxs-lookup"><span data-stu-id="510f7-146">To select the check box, click the **Expression** (*fx*) button and either type **True** or create an expression.</span></span> <span data-ttu-id="510f7-147">Флажок устанавливается при нажатии кнопки **ОК** в диалоговом окне **Выражение** .</span><span class="sxs-lookup"><span data-stu-id="510f7-147">The check box is selected when you click **OK** in the **Expression** dialog box.</span></span>  
  
 <span data-ttu-id="510f7-148">**Перейти к закладке**</span><span class="sxs-lookup"><span data-stu-id="510f7-148">**Go to bookmark**</span></span>  
 <span data-ttu-id="510f7-149">Выберите этот параметр, чтобы задать ссылку на закладку в текущем отчете.</span><span class="sxs-lookup"><span data-stu-id="510f7-149">Choose this option to define a link to a bookmark in the current report.</span></span> <span data-ttu-id="510f7-150">После выбора **Перейти к закладке**появляются следующие дополнительные параметры.</span><span class="sxs-lookup"><span data-stu-id="510f7-150">The following additional option appears when you select **Go to bookmark**.</span></span>  
  
 <span data-ttu-id="510f7-151">**Выберите закладку**</span><span class="sxs-lookup"><span data-stu-id="510f7-151">**Select bookmark**</span></span>  
 <span data-ttu-id="510f7-152">Введите или выберите идентификатор закладки в отчете, к которой пользователь переходит по ссылке.</span><span class="sxs-lookup"><span data-stu-id="510f7-152">Type or select the bookmark ID for the report to jump to when the user clicks the link.</span></span> <span data-ttu-id="510f7-153">Чтобы изменить выражение, нажмите кнопку Выражение (**fx**).</span><span class="sxs-lookup"><span data-stu-id="510f7-153">Click the Expression (**fx**) button to change the expression.</span></span> <span data-ttu-id="510f7-154">Идентификатор закладки может быть статическим идентификатором или выражением, результатом которого является идентификатор закладки.</span><span class="sxs-lookup"><span data-stu-id="510f7-154">The bookmark ID can be either a static ID or an expression that evaluates to a bookmark ID.</span></span> <span data-ttu-id="510f7-155">Это выражение может включать в себя поле, содержащее идентификатор закладки.</span><span class="sxs-lookup"><span data-stu-id="510f7-155">The expression can include a field that contains a bookmark ID.</span></span>  
  
 <span data-ttu-id="510f7-156">Чтобы создать ссылку на закладку, необходимо сначала установить свойство «Закладка» элемента отчета.</span><span class="sxs-lookup"><span data-stu-id="510f7-156">To link to a bookmark, you must first set the Bookmark property of a report item.</span></span> <span data-ttu-id="510f7-157">Чтобы установить свойство «Закладка», выберите элемент отчета и в панели «Свойства» введите значение или выражение идентификатора закладки, например, SalesChart или 5TopSales.</span><span class="sxs-lookup"><span data-stu-id="510f7-157">To set the Bookmark property, select a report item, and in the Properties pane, type a value or expression for the bookmark ID; for example, SalesChart or 5TopSales.</span></span>  
  
 <span data-ttu-id="510f7-158">**Перейти по URL-адресу**</span><span class="sxs-lookup"><span data-stu-id="510f7-158">**Go to URL**</span></span>  
 <span data-ttu-id="510f7-159">Выберите этот параметр, чтобы задать ссылку на веб-страницу.</span><span class="sxs-lookup"><span data-stu-id="510f7-159">Choose this option to define a link to a Web page.</span></span> <span data-ttu-id="510f7-160">Введите или выберите URL-адрес веб-страницы или выражение, значением которого является URL-адрес веб-страницы.</span><span class="sxs-lookup"><span data-stu-id="510f7-160">Type or select the URL of a Web page or an expression that evaluates to the URL of a Web page.</span></span> <span data-ttu-id="510f7-161">Чтобы изменить выражение, нажмите кнопку **Выражение** (*fx*).</span><span class="sxs-lookup"><span data-stu-id="510f7-161">Click the **Expression** (*fx*) button to change the expression.</span></span> <span data-ttu-id="510f7-162">Это выражение может включать поле, содержащее URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="510f7-162">This expression can include a field that contains a URL.</span></span> <span data-ttu-id="510f7-163">После выбора **Перейти по URL-адресу**появляются следующие дополнительные параметры.</span><span class="sxs-lookup"><span data-stu-id="510f7-163">The following additional option appears when you select **Go to URL**.</span></span>  
  
 <span data-ttu-id="510f7-164">**Выберите URL-адрес**</span><span class="sxs-lookup"><span data-stu-id="510f7-164">**Select URL**</span></span>  
 <span data-ttu-id="510f7-165">Введите или вставьте URL-адрес элемента.</span><span class="sxs-lookup"><span data-stu-id="510f7-165">Type or enter the URL of the item.</span></span> <span data-ttu-id="510f7-166">Для элемента, опубликованного на сервере отчетов, который настроен для работы в собственном режиме, указывается полный или относительный путь.</span><span class="sxs-lookup"><span data-stu-id="510f7-166">For an item published to a report server configured for native mode, use a full or relative path.</span></span> <span data-ttu-id="510f7-167">Например, http:// *\<servername>* /images/image1.jpg.</span><span class="sxs-lookup"><span data-stu-id="510f7-167">For example, http://*\<servername>*/images/image1.jpg.</span></span> <span data-ttu-id="510f7-168">Для элемента, опубликованного на сервере отчетов, настроенном в режиме интеграции с SharePoint, используйте полный URL-адрес (например, http:// *\<SharePointservername>/\<site>* /документс/имажес/image1.jpg).</span><span class="sxs-lookup"><span data-stu-id="510f7-168">For an item published to a report server configured in SharePoint integrated mode, use a fully qualified URL (for example, http://*\<SharePointservername>/\<site>*/Documents/images/image1.jpg).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="510f7-169">См. также:</span><span class="sxs-lookup"><span data-stu-id="510f7-169">See Also</span></span>  
 <span data-ttu-id="510f7-170">[Диаграммы &#40;построитель отчетов и службы SSRS&#41;](report-design/charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="510f7-170">[Charts &#40;Report Builder and SSRS&#41;](report-design/charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="510f7-171">[Построитель отчетов справки по диалоговым окнам, панелям и мастерам](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="510f7-171">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 <span data-ttu-id="510f7-172">[Параметры отчета &#40;построитель отчетов и конструктор отчетов&#41;](report-design/report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="510f7-172">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-design/report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="510f7-173">[Добавление вложенного отчета и параметров &#40;построитель отчетов и SSRS&#41;](report-design/add-a-subreport-and-parameters-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="510f7-173">[Add a Subreport and Parameters &#40;Report Builder and SSRS&#41;](report-design/add-a-subreport-and-parameters-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="510f7-174">Интерактивная сортировка, схемы документов и ссылки (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="510f7-174">Interactive Sort, Document Maps, and Links &#40;Report Builder and SSRS&#41;</span></span>](report-design/interactive-sort-document-maps-and-links-report-builder-and-ssrs.md)  
  
  
