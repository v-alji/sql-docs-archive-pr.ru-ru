---
title: Создание схемы документа (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c200a97b-67f2-499f-8374-3ed1ebe3f33c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a9dad0f8e6ee1d9b9ada44fda0eec5908f27cfcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658154"
---
# <a name="create-a-document-map-report-builder-and-ssrs"></a><span data-ttu-id="45ce5-102">Создание схемы документа (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="45ce5-102">Create a Document Map (Report Builder and SSRS)</span></span>
  <span data-ttu-id="45ce5-103">В схеме документа предоставляется набор ссылок на элементы отчета, готового к просмотру.</span><span class="sxs-lookup"><span data-stu-id="45ce5-103">A document map provides a set of navigational links to report items in a rendered report.</span></span> <span data-ttu-id="45ce5-104">Когда осуществляется просмотр отчета, содержащего схему документа, рядом с отчетом появляется отдельная боковая панель.</span><span class="sxs-lookup"><span data-stu-id="45ce5-104">When you view a report that includes a document map, a separate side pane appears next to the report.</span></span> <span data-ttu-id="45ce5-105">Пользователи могут использовать ссылки в схеме документа для перехода к странице отчета, на которой отображен данный элемент.</span><span class="sxs-lookup"><span data-stu-id="45ce5-105">A user can click links in the document map to jump to the report page that displays that item.</span></span> <span data-ttu-id="45ce5-106">Разделы и группы отчета выстроены в соответствии с иерархией ссылок.</span><span class="sxs-lookup"><span data-stu-id="45ce5-106">Report sections and groups are arranged in a hierarchy of links.</span></span> <span data-ttu-id="45ce5-107">При выборе элементов схемы документа отчет обновляется и отображается та его область, которая соответствует выбранному элементу.</span><span class="sxs-lookup"><span data-stu-id="45ce5-107">Clicking items in the document map refreshes the report and displays the area of the report that corresponds to the item in the document map.</span></span>  
  
 <span data-ttu-id="45ce5-108">Чтобы добавить ссылки в схему документа, установите в качестве значения свойства `DocumentMapLabel` элемента отчета созданный текст или выражение, результатом которого является текст, который должен быть отображен в схеме документа.</span><span class="sxs-lookup"><span data-stu-id="45ce5-108">To add links to the document map, you set the `DocumentMapLabel` property of the report item to text that you create or to an expression that evaluates to the text that you want display in the document map.</span></span> <span data-ttu-id="45ce5-109">Также в схему документа можно добавить уникальные значения для группы таблиц или матриц.</span><span class="sxs-lookup"><span data-stu-id="45ce5-109">You can also add the unique values for a table or matrix group to the document map.</span></span> <span data-ttu-id="45ce5-110">Например, для групп, основанных на цветах, каждый уникальный цвет будет ссылкой на страницу отчета, отображающую экземпляр группы данного цвета.</span><span class="sxs-lookup"><span data-stu-id="45ce5-110">For example, for a group based on color, each unique color is a link to the report page that displays the group instance for that color.</span></span>  
  
 <span data-ttu-id="45ce5-111">Также можно создать URL-адрес отчета, переопределяющий отображение схемы документа, чтобы можно было запускать отчет без отображения схемы документа, а затем использовать кнопку **Показать/скрыть схему документа** на панели инструментов средства просмотра отчетов для переключения отображения.</span><span class="sxs-lookup"><span data-stu-id="45ce5-111">You can also create a URL to a report that overrides the display of the document map, so that you can run the report without displaying the document map, and then click the **Show/Hide Document Map** button on the report viewer toolbar to toggle the display.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="document-maps-and-rendering-extensions"></a><a name="DocMapRenderExtensions"></a> <span data-ttu-id="45ce5-112">Схемы документа и модули подготовки отчетов</span><span class="sxs-lookup"><span data-stu-id="45ce5-112">Document Maps and Rendering Extensions</span></span>  
 <span data-ttu-id="45ce5-113">Схема документа предназначена для использования в модуле подготовки отчетов в формате HTML, например при предварительном просмотре и в средстве просмотра отчетов.</span><span class="sxs-lookup"><span data-stu-id="45ce5-113">The document map is intended for use in the HTML rendering extension-for example, in Preview and the Report Viewer.</span></span> <span data-ttu-id="45ce5-114">Другие модули подготовки отчетов определяют схему документа другим образом.</span><span class="sxs-lookup"><span data-stu-id="45ce5-114">Other rendering extensions have different ways of articulating a document map:</span></span>  
  
-   <span data-ttu-id="45ce5-115">Модули подготовки отчетов в формате PDF обращаются со схемой документа как с панелью закладок.</span><span class="sxs-lookup"><span data-stu-id="45ce5-115">PDF renders a document map as the Bookmarks pane.</span></span>  
  
-   <span data-ttu-id="45ce5-116">Модули подготовки отчетов в формате Excel превращают схему документа в виде именованной таблицы, содержащей иерархию ссылок.</span><span class="sxs-lookup"><span data-stu-id="45ce5-116">Excel renders a document map as a named worksheet that includes a hierarchy of links.</span></span> <span data-ttu-id="45ce5-117">Разделы отчета помещаются на отдельные листы, которые затем включаются в ту же книгу, что и схема документа.</span><span class="sxs-lookup"><span data-stu-id="45ce5-117">Report sections are rendered in separate worksheets that are included with the document map in the same workbook.</span></span>  
  
-   <span data-ttu-id="45ce5-118">Текстовый редактор Word содержит схему документа в виде оглавления.</span><span class="sxs-lookup"><span data-stu-id="45ce5-118">Word includes a document map as the table of contents.</span></span>  
  
-   <span data-ttu-id="45ce5-119">Модули подготовки отчетов в формате Atom, TIFF, XML и CSV не используют схемы документа.</span><span class="sxs-lookup"><span data-stu-id="45ce5-119">Atom, TIFF, XML, and CSV ignore document maps.</span></span>  
  
 <span data-ttu-id="45ce5-120">Дополнительные сведения см. в разделе [Интерактивные возможности различных модулей подготовки отчетов к просмотру (построитель отчетов и службы SSRS)](../report-builder/interactive-functionality-different-report-rendering-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="45ce5-120">For more information, see [Interactive Functionality for Different Report Rendering Extensions &#40;Report Builder and SSRS&#41;](../report-builder/interactive-functionality-different-report-rendering-extensions.md).</span></span>  
  
##  <a name="AddRptItemToMap"></a>   
#### <a name="to-add-a-report-item-to-a-document-map"></a><span data-ttu-id="45ce5-121">Добавление элемента отчета к схеме документа</span><span class="sxs-lookup"><span data-stu-id="45ce5-121">To add a report item to a document map</span></span>  
  
1.  <span data-ttu-id="45ce5-122">Выберите элемент отчета в режиме конструктора, например таблицу, матрицу или датчик, который следует добавить в схему документа.</span><span class="sxs-lookup"><span data-stu-id="45ce5-122">In Design view, select the report item such as a table, matrix, or gauge that you want to add to the document map.</span></span> <span data-ttu-id="45ce5-123">Свойства этого элемента отчета появятся на панели свойств.</span><span class="sxs-lookup"><span data-stu-id="45ce5-123">The report item properties appear in the Properties pane.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="45ce5-124">Чтобы выбрать область данных табликса, щелкните любую ячейку, чтобы вывести дескрипторы строк и столбцов, а затем щелкните угловой маркер.</span><span class="sxs-lookup"><span data-stu-id="45ce5-124">To select a tablix data region, click in any cell to display the row and column handles, and then click the corner handle.</span></span>  
  
2.  <span data-ttu-id="45ce5-125">В области Свойства введите текст, который должен отображаться в схеме документа в `DocumentMapLabel` свойстве, или введите выражение, результатом которого является метка.</span><span class="sxs-lookup"><span data-stu-id="45ce5-125">In the Properties pane, type the text that you want to appear in the document map in the `DocumentMapLabel` property, or enter an expression that evaluates to a label.</span></span> <span data-ttu-id="45ce5-126">Например, введите **Диаграмма продаж**.</span><span class="sxs-lookup"><span data-stu-id="45ce5-126">For example, type **Sales Chart**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="45ce5-127">Если панель свойств не видна, выберите пункт **Свойства** в группе **Показать/скрыть** на вкладке **Вид**.</span><span class="sxs-lookup"><span data-stu-id="45ce5-127">If you do not see the Properties pane, on the **View** tab, in the **Show/Hide** group, select **Properties**.</span></span>  
  
3.  <span data-ttu-id="45ce5-128">Повторите шаги 1 и 2 для всех элементов отчета, которые должны появиться в схеме документа.</span><span class="sxs-lookup"><span data-stu-id="45ce5-128">Repeat steps 1 and 2 for every report item that you want to appear in the document map.</span></span>  
  
4.  <span data-ttu-id="45ce5-129">Нажмите кнопку **Запустить**.</span><span class="sxs-lookup"><span data-stu-id="45ce5-129">Click **Run**.</span></span> <span data-ttu-id="45ce5-130">Отчет будет запущен, а в его схеме документа будут отображены созданные метки.</span><span class="sxs-lookup"><span data-stu-id="45ce5-130">The report runs and the document map displays the labels you created.</span></span> <span data-ttu-id="45ce5-131">Щелкните любую из ссылок, чтобы перейти к странице отчета с данным элементом.</span><span class="sxs-lookup"><span data-stu-id="45ce5-131">Click any link to jump to the report page with that item.</span></span>  
  
 
  
##  <a name="AddUniqueValuesToMap"></a>   
#### <a name="to-add-unique-group-values-to-a-document-map"></a><span data-ttu-id="45ce5-132">Добавление в схему документа уникальных значений групп</span><span class="sxs-lookup"><span data-stu-id="45ce5-132">To add unique group values to a document map</span></span>  
  
1.  <span data-ttu-id="45ce5-133">В режиме конструктора выберите таблицу, матрицу или список, содержащий группу, которая должна быть отображена в схеме документа.</span><span class="sxs-lookup"><span data-stu-id="45ce5-133">In Design view, select the table, matrix, or list that contains the group that you want to display in the document map.</span></span> <span data-ttu-id="45ce5-134">На панели группирования будут отображены группы столбцов и строк.</span><span class="sxs-lookup"><span data-stu-id="45ce5-134">The Grouping pane displays the row and column groups.</span></span>  
  
2.  <span data-ttu-id="45ce5-135">На панели "Группы строк" щелкните правой кнопкой мыши группу и выберите пункт **Изменить группу**.</span><span class="sxs-lookup"><span data-stu-id="45ce5-135">In the Row Groups pane, right-click the group, and then click **Edit Group**.</span></span> <span data-ttu-id="45ce5-136">Откроется страница **Общие** диалогового окна **Свойства группы табликсов** .</span><span class="sxs-lookup"><span data-stu-id="45ce5-136">The **General** page of the **Tablix Group Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="45ce5-137">Щелкните **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="45ce5-137">Click **Advanced**.</span></span>  
  
4.  <span data-ttu-id="45ce5-138">В списке **Схема документа** введите или выберите выражение, совпадающее с выражением группы.</span><span class="sxs-lookup"><span data-stu-id="45ce5-138">In the **Document map** list box, type or select an expression that matches the group expression.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="45ce5-139">Повторите шаги 1 — 4 для всех групп, которые должны появиться в схеме документа.</span><span class="sxs-lookup"><span data-stu-id="45ce5-139">Repeat steps 1-4 for every group that you want to appear in the document map.</span></span>  
  
7.  <span data-ttu-id="45ce5-140">Нажмите кнопку **Запустить**.</span><span class="sxs-lookup"><span data-stu-id="45ce5-140">Click **Run**.</span></span> <span data-ttu-id="45ce5-141">Отчет будет запущен, а в его схеме документа будут отображены значения групп.</span><span class="sxs-lookup"><span data-stu-id="45ce5-141">The report runs and the document map displays the group values.</span></span> <span data-ttu-id="45ce5-142">Щелкните любую из ссылок, чтобы перейти к странице отчета с данным элементом.</span><span class="sxs-lookup"><span data-stu-id="45ce5-142">Click any link to jump to the report page with that item.</span></span>  
  
 
  
##  <a name="HideMapWhenViewRpt"></a>   
#### <a name="to-hide-the-document-map-when-you-view-a-report"></a><span data-ttu-id="45ce5-143">Скрытие схемы документа при просмотре отчета</span><span class="sxs-lookup"><span data-stu-id="45ce5-143">To hide the document map when you view a report</span></span>  
  
1.  <span data-ttu-id="45ce5-144">В диспетчере отчетов перейдите к отчету, имеющему схему документа.</span><span class="sxs-lookup"><span data-stu-id="45ce5-144">In Report Manager, browse to the report that has the document map.</span></span>  
  
     <span data-ttu-id="45ce5-145">Например, в образцах отчетов [!INCLUDE[ssSampleDBUserInputNonLocal](../../includes/sssampledbuserinputnonlocal-md.md)] следующий URL-адрес указывает отчет с именем «Каталог продуктов».</span><span class="sxs-lookup"><span data-stu-id="45ce5-145">For example, for the [!INCLUDE[ssSampleDBUserInputNonLocal](../../includes/sssampledbuserinputnonlocal-md.md)] sample reports, the following URL specifies the report named Product Catalog.</span></span>  
  
    ```  
    http://localhost/Reports/Pages/Report.aspx?ItemPath=%2fAdventureWorks2012+Sample+Reports%2fProduct+Catalog  
    ```  
  
2.  <span data-ttu-id="45ce5-146">Скопируйте путь к отчету на сервере.</span><span class="sxs-lookup"><span data-stu-id="45ce5-146">Copy the report path on the server.</span></span> <span data-ttu-id="45ce5-147">В приведенном примере путем к отчету является `%2fAdventureWorks2012+Sample+Reports%2fProduct+Catalog`.</span><span class="sxs-lookup"><span data-stu-id="45ce5-147">In the example, the report path is `%2fAdventureWorks2012+Sample+Reports%2fProduct+Catalog`.</span></span>  
  
3.  <span data-ttu-id="45ce5-148">Создайте новый URL-адрес со следующими тремя компонентами:</span><span class="sxs-lookup"><span data-stu-id="45ce5-148">Create a new URL with the following three components:</span></span>  
  
    -   <span data-ttu-id="45ce5-149">Средство просмотра отчетов на сервере отчетов: `http://localhost/ReportServer/Pages/ReportViewer.aspx?`</span><span class="sxs-lookup"><span data-stu-id="45ce5-149">The report viewer on the report server: `http://localhost/ReportServer/Pages/ReportViewer.aspx?`</span></span>  
  
    -   <span data-ttu-id="45ce5-150">Имя отчета, скопированного на шаге 1, например `%2fAdventureWorks2012+Sample+Reports%2fProduct+Catalog`</span><span class="sxs-lookup"><span data-stu-id="45ce5-150">The name of the report you copied in step 1, for example: `%2fAdventureWorks2012+Sample+Reports%2fProduct+Catalog`</span></span>  
  
    -   <span data-ttu-id="45ce5-151">Параметры сведений об устройстве, в которых указывается необходимость скрыть схему документа: `&rs%3aCommand=Render&rc%3aFormat=HTML4.0&rc%3aDocMap=False`</span><span class="sxs-lookup"><span data-stu-id="45ce5-151">The device information parameters that specify hiding the document map: `&rs%3aCommand=Render&rc%3aFormat=HTML4.0&rc%3aDocMap=False`</span></span>  
  
     <span data-ttu-id="45ce5-152">Следующий URL-адрес состоит из данных трех компонентов, соединенных в порядке их перечисления.</span><span class="sxs-lookup"><span data-stu-id="45ce5-152">The following URL consists of these three components appended in the order they are listed.</span></span>  
  
    ```  
    http://localhost/ReportServer/Pages/ReportViewer.aspx?  
    %2fAdventureWorks2012+Sample+Reports%2fProduct+Catalog  
    &rs%3aCommand=Render&rc%3aFormat=HTML4.0&rc%3aDocMap=False  
    ```  
  
     <span data-ttu-id="45ce5-153">Чтобы использовать данный URL-адрес, скопируйте его и удалите все разрывы строк.</span><span class="sxs-lookup"><span data-stu-id="45ce5-153">To use this URL, copy it and remove all line breaks.</span></span>  
  
4.  <span data-ttu-id="45ce5-154">Вставьте URL-адрес в диспетчер отчетов и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="45ce5-154">Paste the URL in Report Manager, and then press ENTER.</span></span> <span data-ttu-id="45ce5-155">Отчет будет запущен со скрытой схемой документа.</span><span class="sxs-lookup"><span data-stu-id="45ce5-155">The report runs, and the document map is hidden.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="45ce5-156">Дополнительные сведения о скачивании образцов отчетов см. в разделе [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [образцы отчетов построитель отчетов и конструктор отчетов](https://go.microsoft.com/fwlink/?LinkId=198283).</span><span class="sxs-lookup"><span data-stu-id="45ce5-156">For more information about downloading sample reports, see [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Report Builder and Report Designer sample reports](https://go.microsoft.com/fwlink/?LinkId=198283).</span></span>  
>   
>  <span data-ttu-id="45ce5-157">Дополнительные сведения см. в разделе «Доступ по URL-адресу» [документации по службам Reporting Services](https://go.microsoft.com/fwlink/?linkid=121312) , входящей в состав электронной документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="45ce5-157">For more information, see "URL Access" in the [Reporting Services documentation](https://go.microsoft.com/fwlink/?linkid=121312) in SQL Server Books Online.</span></span>  
  
 
  
## <a name="see-also"></a><span data-ttu-id="45ce5-158">См. также:</span><span class="sxs-lookup"><span data-stu-id="45ce5-158">See Also</span></span>  
 [<span data-ttu-id="45ce5-159">Поиск и просмотр отчетов в диспетчере отчетов (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="45ce5-159">Finding and Viewing Reports in Report Manager &#40;Report Builder and SSRS&#41;</span></span>](../report-builder/finding-and-viewing-reports-in-the-web-portal-report-builder-and-ssrs.md)  
  
  
