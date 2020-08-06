---
title: Печать отчета (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: b96936c9-c387-41a9-8c19-6eb325769ffd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fe029019cdf9739153256db399cfa1426d3ba632
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657544"
---
# <a name="print-a-report-report-builder-and-ssrs"></a><span data-ttu-id="26eb6-102">Печать отчета (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="26eb6-102">Print a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="26eb6-103">После сохранения отчета на сервере отчетов его можно просмотреть и распечатать из браузера, диспетчера отчетов или любого приложения, использующегося для просмотра экспортированных отчетов.</span><span class="sxs-lookup"><span data-stu-id="26eb6-103">After you save a report to a report server, you can view and print the report from a browser, Report Manager, or any application that you use to view an exported report.</span></span> <span data-ttu-id="26eb6-104">Перед сохранением отчета его можно напечатать во время просмотра.</span><span class="sxs-lookup"><span data-stu-id="26eb6-104">Before saving a report, you can print it when you preview it.</span></span>  
  
 <span data-ttu-id="26eb6-105">При печати отчета можно указать используемый размер бумаги.</span><span class="sxs-lookup"><span data-stu-id="26eb6-105">When you print a report, you can specify the size of the paper to use.</span></span> <span data-ttu-id="26eb6-106">От размера бумаги зависит количество страниц в отчете и то, какие данные отчета поместятся на каждой странице.</span><span class="sxs-lookup"><span data-stu-id="26eb6-106">The size of the paper determines the number of pages in a report and which report data fits on each page.</span></span> <span data-ttu-id="26eb6-107">Размер бумаги влияет только на отчеты, которые подготавливаются к просмотру модулями подготовки отчетов к печати: "PDF", "Изображение" и "Печать".</span><span class="sxs-lookup"><span data-stu-id="26eb6-107">Paper size affects only reports that are rendered with hard page-break renders: PDF, Image, and Print.</span></span> <span data-ttu-id="26eb6-108">Параметр размера бумаги не влияет на другие модули подготовки отчетов.</span><span class="sxs-lookup"><span data-stu-id="26eb6-108">Setting the paper size has no effect on other renderers.</span></span> <span data-ttu-id="26eb6-109">Дополнительные сведения см. в разделе [Поведение при подготовке к просмотру (построитель отчетов и службы SSRS)](../report-design/rendering-behaviors-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="26eb6-109">For more information, see [Rendering Behaviors &#40;Report Builder  and SSRS&#41;](../report-design/rendering-behaviors-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="26eb6-110">С помощью панели инструментов средства просмотра отчетов в диспетчере отчетов или в режиме просмотра построителя отчетов можно экспортировать отчет в модуль подготовки с жесткими разрывами страниц или нажать кнопку «Печать», чтобы напечатать копию отчета.</span><span class="sxs-lookup"><span data-stu-id="26eb6-110">From the report viewer toolbar in Report Manager or in preview in Report Builder, you can export a report to a hard page-break renderer or click the Print button to print a copy of the report.</span></span> <span data-ttu-id="26eb6-111">В процессе работы может потребоваться задать размер бумаги или другие свойства параметров страницы.</span><span class="sxs-lookup"><span data-stu-id="26eb6-111">You might need to set the paper size or other page setup properties.</span></span> <span data-ttu-id="26eb6-112">Используйте диалоговое окно **Свойства отчета** , чтобы изменить свойства параметров страницы, включая размер бумаги.</span><span class="sxs-lookup"><span data-stu-id="26eb6-112">Use the **Report Properties** dialog box to change page setup properties, including paper size.</span></span>  
  
 <span data-ttu-id="26eb6-113">Поля страницы для печати можно задать двумя способами: в режиме конструктора и в режиме выполнения.</span><span class="sxs-lookup"><span data-stu-id="26eb6-113">You can specify print page margins in two different locations: in design mode and in run mode.</span></span>  
  
-   <span data-ttu-id="26eb6-114">**Режим конструктора.**</span><span class="sxs-lookup"><span data-stu-id="26eb6-114">**Design mode.**</span></span> <span data-ttu-id="26eb6-115">При установке полей страницы в режиме конструктора эти настройки сохраняются в определении отчета в процессе сохранения отчета.</span><span class="sxs-lookup"><span data-stu-id="26eb6-115">When you set page margins in design mode, these settings are saved in the report definition when you save the report.</span></span>  
  
-   <span data-ttu-id="26eb6-116">**Режим выполнения.**</span><span class="sxs-lookup"><span data-stu-id="26eb6-116">**Run mode.**</span></span> <span data-ttu-id="26eb6-117">При установке полей страницы в режиме выполнения эта информация не сохраняется в определении отчета.</span><span class="sxs-lookup"><span data-stu-id="26eb6-117">When you set page margins in run mode, this information is not saved in the report definition.</span></span> <span data-ttu-id="26eb6-118">В следующий раз при печати отчета будут получены настройки из определения отчета, если снова не указать поля для печати.</span><span class="sxs-lookup"><span data-stu-id="26eb6-118">The next time you print the report, you will get the settings from the report definition, unless you indicate your print margins again.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="26eb6-119">Поля печати не отображаются в режимах конструктора или выполнения.</span><span class="sxs-lookup"><span data-stu-id="26eb6-119">Print margins are not displayed in design or run modes.</span></span> <span data-ttu-id="26eb6-120">Не существует связи между областью конструктора и областью печати отчета.</span><span class="sxs-lookup"><span data-stu-id="26eb6-120">There is no relationship between the design surface area and the print area of your report.</span></span> <span data-ttu-id="26eb6-121">Чтобы просмотреть поля печати в режиме выполнения, нажмите кнопку «Макет страницы» на вкладке **Выполнение** ленты.</span><span class="sxs-lookup"><span data-stu-id="26eb6-121">To see print margins, in run mode, click Print Layout on the **Run** tab on the Ribbon.</span></span>  
  
 <span data-ttu-id="26eb6-122">Дополнительные сведения о разбиении отчета на страницы см. в разделе [Разбиение на страницы в службах Reporting Services (построитель отчетов и службы SSRS)](../report-design/pagination-in-reporting-services-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="26eb6-122">For more information about report paging, see [Pagination in Reporting Services &#40;Report Builder  and SSRS&#41;](../report-design/pagination-in-reporting-services-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-print-a-report-in-report-builder"></a><span data-ttu-id="26eb6-123">Печать отчета в построителе отчетов</span><span class="sxs-lookup"><span data-stu-id="26eb6-123">To print a report in Report Builder</span></span>  
  
1.  <span data-ttu-id="26eb6-124">Откройте отчет.</span><span class="sxs-lookup"><span data-stu-id="26eb6-124">Open a report.</span></span>  
  
2.  <span data-ttu-id="26eb6-125">На вкладке Главная нажмите кнопку **выполнить**.</span><span class="sxs-lookup"><span data-stu-id="26eb6-125">On the Home tab, click **Run**.</span></span>  
  
3.  <span data-ttu-id="26eb6-126">Щелкните **Макет страницы** , чтобы просмотреть, как отчет будет выглядеть после печати (необязательно).</span><span class="sxs-lookup"><span data-stu-id="26eb6-126">(optional) Click **Print Layout** to see how the report will look when it is printed.</span></span>  
  
4.  <span data-ttu-id="26eb6-127">Щелкните **Параметры страницы** , чтобы задать бумагу, ориентацию и поля (необязательно).</span><span class="sxs-lookup"><span data-stu-id="26eb6-127">(optional) Click **Page Setup** to set paper, orientation, and margins.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="26eb6-128">Значения по умолчанию для этих параметров будут взяты из свойств отчета, заданные в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="26eb6-128">The default values for these come from the report properties, which are set in Design view.</span></span> <span data-ttu-id="26eb6-129">Значения, заданные в диалоговом окне **Параметры страницы** , действительны только для текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="26eb6-129">The values you set here in the **Page Setup** dialog box are for this session only.</span></span> <span data-ttu-id="26eb6-130">После закрытия и повторного открытия отчета будут восстановлены значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="26eb6-130">When you close this report and reopen it, it will have the default values again.</span></span>  
  
5.  <span data-ttu-id="26eb6-131">Нажмите кнопку **Печать**.</span><span class="sxs-lookup"><span data-stu-id="26eb6-131">Click **Print**.</span></span>  
  
6.  <span data-ttu-id="26eb6-132">В диалоговом окне **Печать** выберите принтер и укажите другие параметры печати.</span><span class="sxs-lookup"><span data-stu-id="26eb6-132">In the **Print** dialog box, select a printer and specify other printing options.</span></span>  
  
### <a name="to-print-a-report-from-a-web-browser-application"></a><span data-ttu-id="26eb6-133">Печать отчета из приложения веб-браузера</span><span class="sxs-lookup"><span data-stu-id="26eb6-133">To print a report from a Web browser application</span></span>  
  
1.  <span data-ttu-id="26eb6-134">Запустите [Диспетчер отчетов (службы Reporting Services в основном режиме)](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="26eb6-134">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="26eb6-135">В диспетчере отчетов перейдите к отчету, который нужно напечатать.</span><span class="sxs-lookup"><span data-stu-id="26eb6-135">In Report Manager, navigate to the report that you want to print.</span></span> <span data-ttu-id="26eb6-136">Откройте отчет.</span><span class="sxs-lookup"><span data-stu-id="26eb6-136">Open the report.</span></span>  
  
3.  <span data-ttu-id="26eb6-137">На панели инструментов в верхней части отчета нажмите кнопку **Печать**.</span><span class="sxs-lookup"><span data-stu-id="26eb6-137">On the toolbar at the top of the report, click **Print**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="26eb6-138">При первой печати HTML-отчета сервер отчетов предлагает установить элемент управления ActiveX, используемый для печати.</span><span class="sxs-lookup"><span data-stu-id="26eb6-138">The first time you print an HTML report, the report server prompts you to install an ActiveX control used for printing.</span></span> <span data-ttu-id="26eb6-139">Необходимо установить этот элемент управления и настроить его для печати.</span><span class="sxs-lookup"><span data-stu-id="26eb6-139">You must install and configure the control to print.</span></span>  
  
4.  <span data-ttu-id="26eb6-140">В диалоговом окне **Печать** выберите принтер, затем нажмите кнопку **Печать**.</span><span class="sxs-lookup"><span data-stu-id="26eb6-140">In the **Print** dialog box, select a printer, and then click **Prin**t.</span></span>  
  
### <a name="to-print-a-report-from-other-applications"></a><span data-ttu-id="26eb6-141">Печать отчета из других приложений</span><span class="sxs-lookup"><span data-stu-id="26eb6-141">To print a report from other applications</span></span>  
  
1.  <span data-ttu-id="26eb6-142">В диспетчере отчетов перейдите к отчету, который нужно напечатать.</span><span class="sxs-lookup"><span data-stu-id="26eb6-142">In Report Manager, navigate to the report that you want to print.</span></span> <span data-ttu-id="26eb6-143">Откройте отчет.</span><span class="sxs-lookup"><span data-stu-id="26eb6-143">Open the report.</span></span>  
  
2.  <span data-ttu-id="26eb6-144">На панели инструментов в верхней части отчета выберите формат представления и нажмите кнопку **Экспорт**.</span><span class="sxs-lookup"><span data-stu-id="26eb6-144">On the toolbar at the top of the report, select a rendering format, and then click **Export**.</span></span> <span data-ttu-id="26eb6-145">Отчет открывается в приложении просмотра, которое соответствует формату представления.</span><span class="sxs-lookup"><span data-stu-id="26eb6-145">The report opens in a viewer application that corresponds to the rendering format.</span></span>  
  
     <span data-ttu-id="26eb6-146">Например, если будет выбран формат PDF, то отчет откроется в Adobe Acrobat Reader.</span><span class="sxs-lookup"><span data-stu-id="26eb6-146">For example, if you select PDF, the report opens in Adobe Acrobat Reader.</span></span>  
  
3.  <span data-ttu-id="26eb6-147">В меню **Файл** этой программы выберите пункт **Печать**.</span><span class="sxs-lookup"><span data-stu-id="26eb6-147">On the **File** menu in that program, click **Print**.</span></span>  
  
### <a name="to-change-paper-size"></a><span data-ttu-id="26eb6-148">Изменение размера бумаги</span><span class="sxs-lookup"><span data-stu-id="26eb6-148">To change paper size</span></span>  
  
1.  <span data-ttu-id="26eb6-149">Щелкните правой кнопкой мыши за пределами текста отчета и выберите пункт **Свойства отчета**.</span><span class="sxs-lookup"><span data-stu-id="26eb6-149">Right-click outside of the report body and click **Report Properties**.</span></span>  
  
2.  <span data-ttu-id="26eb6-150">В окне **Параметры страницы**выберите значение из списка **Размер бумаги** .</span><span class="sxs-lookup"><span data-stu-id="26eb6-150">In **Page Setup**, select a value from the **Paper Size** list.</span></span> <span data-ttu-id="26eb6-151">При выборе каждого параметра заполняются свойства **Высота** и **Ширина** .</span><span class="sxs-lookup"><span data-stu-id="26eb6-151">Each option populates the **Width** and **Height** properties.</span></span> <span data-ttu-id="26eb6-152">Можно также указать пользовательский размер, введя числовые значения в поля **Ширина** и **Высота** .</span><span class="sxs-lookup"><span data-stu-id="26eb6-152">You can also specify a custom size by typing numeric values in the **Width** and **Height** boxes.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
    > [!NOTE]  
    >  <span data-ttu-id="26eb6-153">Единицы измерения значений размера основаны на настройках локали пользователя.</span><span class="sxs-lookup"><span data-stu-id="26eb6-153">Size values have a default unit based on the user's locale settings.</span></span> <span data-ttu-id="26eb6-154">Чтобы присвоить другую единицу измерения, введите после числового значения обозначение единицы измерения, например см, мм, пт или пк.</span><span class="sxs-lookup"><span data-stu-id="26eb6-154">To designate a different unit, type a physical unit designator such as cm, mm, pt, or pc after the numeric value.</span></span>  
  
### <a name="to-set-page-margins-in-design-mode"></a><span data-ttu-id="26eb6-155">Установка полей страницы в режиме конструктора</span><span class="sxs-lookup"><span data-stu-id="26eb6-155">To set page margins in design mode</span></span>  
  
-   <span data-ttu-id="26eb6-156">Щелкните правой кнопкой мыши синюю область вокруг области конструктора, выберите пункт **Свойства отчета**и откройте **Параметры страницы** .</span><span class="sxs-lookup"><span data-stu-id="26eb6-156">Right-click the blue area around the design surface, click **Report Properties**, and then click the **Page Setup** page.</span></span>  
  
### <a name="to-set-page-margins-in-run-mode"></a><span data-ttu-id="26eb6-157">Установка полей страницы в режиме выполнения</span><span class="sxs-lookup"><span data-stu-id="26eb6-157">To set page margins in run mode</span></span>  
  
-   <span data-ttu-id="26eb6-158">Нажмите кнопку **Параметры страницы** на вкладке **Выполнение** .</span><span class="sxs-lookup"><span data-stu-id="26eb6-158">Click **Page Setup** on the **Run** tab.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26eb6-159">См. также:</span><span class="sxs-lookup"><span data-stu-id="26eb6-159">See Also</span></span>  
 <span data-ttu-id="26eb6-160">[Печать отчетов (построитель отчетов и службы SSRS)](print-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="26eb6-160">[Print Reports &#40;Report Builder and SSRS&#41;](print-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="26eb6-161">[Экспорт отчетов &#40;построитель отчетов и SSRS&#41;](export-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="26eb6-161">[Exporting Reports &#40;Report Builder and SSRS&#41;](export-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="26eb6-162">[Диалоговое окно "Свойства отчета" — "Параметры страницы" (построитель отчетов)](../report-properties-dialog-box-page-setup-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="26eb6-162">[Report Properties Dialog Box, Page Setup &#40;Report Builder&#41;](../report-properties-dialog-box-page-setup-report-builder.md) </span></span>  
 [<span data-ttu-id="26eb6-163">Представление конструктора отчетов (построитель отчетов)</span><span class="sxs-lookup"><span data-stu-id="26eb6-163">Report Design View &#40;Report Builder&#41;</span></span>](report-design-view-report-builder.md)  
  
  
