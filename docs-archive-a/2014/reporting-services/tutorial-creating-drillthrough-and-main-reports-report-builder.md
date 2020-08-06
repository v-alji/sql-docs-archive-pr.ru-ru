---
title: Учебник. Создание детализированных и главных отчетов (построитель отчетов) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 7168c8d3-cef5-4c4a-a0bf-fff1ac5b8b71
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d7d30b59a0c5523ed50df06f8587bbd701ae4c79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737808"
---
# <a name="tutorial-creating-drillthrough-and-main-reports-report-builder"></a><span data-ttu-id="95c3a-102">Учебник. Создание детализированных и главных отчетов (построитель отчетов)</span><span class="sxs-lookup"><span data-stu-id="95c3a-102">Tutorial: Creating Drillthrough and Main Reports (Report Builder)</span></span>
  <span data-ttu-id="95c3a-103">Это учебник описывает создание отчетов двух типов: детализированного отчета и основного отчета.</span><span class="sxs-lookup"><span data-stu-id="95c3a-103">This tutorial teaches you how to create two kinds of reports: a drillthrough report and a main report.</span></span> <span data-ttu-id="95c3a-104">Образцы данных по продажам, использованные в этих отчетах, извлекаются из куба служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="95c3a-104">The sample sales data used in these reports is retrieved from an Analysis Services cube.</span></span> <span data-ttu-id="95c3a-105">На приведенной ниже иллюстрации показаны отчеты, которые предстоит создать.</span><span class="sxs-lookup"><span data-stu-id="95c3a-105">The following illustration shows the reports you will create.</span></span>  
  
 <span data-ttu-id="95c3a-106">![rs_DrillthroughCubeTutorial](../../2014/tutorials/media/rs-drillthroughcubetutorial.gif "rs_DrillthroughCubeTutorial")</span><span class="sxs-lookup"><span data-stu-id="95c3a-106">![rs_DrillthroughCubeTutorial](../../2014/tutorials/media/rs-drillthroughcubetutorial.gif "rs_DrillthroughCubeTutorial")</span></span>  
  
 <span data-ttu-id="95c3a-107">На следующем рисунке показано, как значения поля, игры и Toys в основном отчете отображаются в заголовке детализированного отчета.</span><span class="sxs-lookup"><span data-stu-id="95c3a-107">The following illustration shows how the field value, Games and Toys, in the main report displays in the drillthrough report's title.</span></span> <span data-ttu-id="95c3a-108">Данные в детализированном отчете относятся к категории продуктов «Игры и игрушки».</span><span class="sxs-lookup"><span data-stu-id="95c3a-108">The data in the drillthrough pertains to the Games and Toys product category.</span></span>  
  
 <span data-ttu-id="95c3a-109">![rs_DrillthroughCubeTutorialParmExpr](../../2014/tutorials/media/rs-drillthroughcubetutorialparmexpr.gif "rs_DrillthroughCubeTutorialParmExpr")</span><span class="sxs-lookup"><span data-stu-id="95c3a-109">![rs_DrillthroughCubeTutorialParmExpr](../../2014/tutorials/media/rs-drillthroughcubetutorialparmexpr.gif "rs_DrillthroughCubeTutorialParmExpr")</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="95c3a-110">Обзор учебника</span><span class="sxs-lookup"><span data-stu-id="95c3a-110">What You Will Learn</span></span>  
 <span data-ttu-id="95c3a-111">**В разделах, посвященных детализированному отчету, рассматриваются следующие темы.**</span><span class="sxs-lookup"><span data-stu-id="95c3a-111">**In the drillthrough report you will learn how to:**</span></span>  
  
1.  [<span data-ttu-id="95c3a-112">Создание детализированного матричного отчета и набора данных с помощью мастера таблицы или матрицы</span><span class="sxs-lookup"><span data-stu-id="95c3a-112">Create a Drillthrough Matrix Report and Dataset from the Table or Matrix Wizard</span></span>](#DMatrixAndDataset)  
  
    1.  [<span data-ttu-id="95c3a-113">Задание подключения к данным</span><span class="sxs-lookup"><span data-stu-id="95c3a-113">Specify a Data Connection</span></span>](#DConnection)  
  
    2.  [<span data-ttu-id="95c3a-114">Создание запроса многомерных выражений</span><span class="sxs-lookup"><span data-stu-id="95c3a-114">Create an MDX Query</span></span>](#DMDXQuery)  
  
    3.  [<span data-ttu-id="95c3a-115">Стиль упорядочения данных по группам</span><span class="sxs-lookup"><span data-stu-id="95c3a-115">Organize Data into Groups Style</span></span>](#DLayout)  
  
    4.  [<span data-ttu-id="95c3a-116">Добавление подытогов и итогов</span><span class="sxs-lookup"><span data-stu-id="95c3a-116">Add Subtotals and Totals</span></span>](#DTotals)  
  
    5.  [<span data-ttu-id="95c3a-117">Выбор стиля</span><span class="sxs-lookup"><span data-stu-id="95c3a-117">Choose a Style</span></span>](#DStyle)  
  
2.  [<span data-ttu-id="95c3a-118">Форматирование данных в денежном формате</span><span class="sxs-lookup"><span data-stu-id="95c3a-118">Format Data as Currency</span></span>](#DFormat)  
  
3.  [<span data-ttu-id="95c3a-119">Добавление столбцов для отображения значений продаж в спарклайна</span><span class="sxs-lookup"><span data-stu-id="95c3a-119">Add columns to Show Sales Values in Sparklines</span></span>](#DSparkline)  
  
4.  [<span data-ttu-id="95c3a-120">Добавление в заголовок отчета названия категории продуктов</span><span class="sxs-lookup"><span data-stu-id="95c3a-120">Add Report Title with Product Category Name</span></span>](#DReportTitle)  
  
5.  [<span data-ttu-id="95c3a-121">Обновление свойств параметров</span><span class="sxs-lookup"><span data-stu-id="95c3a-121">Update Parameter Properties</span></span>](#DParameter)  
  
6.  [<span data-ttu-id="95c3a-122">Сохранение отчета в библиотеке SharePoint</span><span class="sxs-lookup"><span data-stu-id="95c3a-122">Save the Report to a SharePoint Library</span></span>](#DSave)  
  
 <span data-ttu-id="95c3a-123">**В разделах, посвященных основному отчету, рассматриваются следующие темы.**</span><span class="sxs-lookup"><span data-stu-id="95c3a-123">**In the main report you will learn how to:**</span></span>  
  
1.  [<span data-ttu-id="95c3a-124">Создание основного матричного отчета и набора данных с помощью мастера таблицы или матрицы</span><span class="sxs-lookup"><span data-stu-id="95c3a-124">Create the Main Matrix Report and Dataset from the Table or Matrix Wizard</span></span>](#MMatrixAndDataset)  
  
    1.  [<span data-ttu-id="95c3a-125">Задание подключения к данным</span><span class="sxs-lookup"><span data-stu-id="95c3a-125">Specify a Data Connection</span></span>](#MConnection)  
  
    2.  [<span data-ttu-id="95c3a-126">Создание запроса многомерных выражений</span><span class="sxs-lookup"><span data-stu-id="95c3a-126">Create an MDX Query</span></span>](#MMDXQuery)  
  
    3.  [<span data-ttu-id="95c3a-127">Упорядочение данных по группам</span><span class="sxs-lookup"><span data-stu-id="95c3a-127">Organize Data into Groups</span></span>](#MLayout)  
  
    4.  [<span data-ttu-id="95c3a-128">Добавление подытогов и итогов</span><span class="sxs-lookup"><span data-stu-id="95c3a-128">Add Subtotals and Totals</span></span>](#MTotals)  
  
    5.  [<span data-ttu-id="95c3a-129">Выбор стиля</span><span class="sxs-lookup"><span data-stu-id="95c3a-129">Choose a Style</span></span>](#MStyle)  
  
2.  [<span data-ttu-id="95c3a-130">Удаление строки «Общий итог»</span><span class="sxs-lookup"><span data-stu-id="95c3a-130">Remove the Grand Total Row</span></span>](#MGrandTotal)  
  
3.  [<span data-ttu-id="95c3a-131">Действие «Настройка текстового поля» для детализированного отчета</span><span class="sxs-lookup"><span data-stu-id="95c3a-131">Configure Text Box Action for Drillthrough</span></span>](#MDrillthrough)  
  
4.  [<span data-ttu-id="95c3a-132">Замена числовых значений индикаторами</span><span class="sxs-lookup"><span data-stu-id="95c3a-132">Replace Numeric Values with Indicators</span></span>](#MIndicators)  
  
5.  [<span data-ttu-id="95c3a-133">Обновление свойств параметров</span><span class="sxs-lookup"><span data-stu-id="95c3a-133">Update Parameter Properties</span></span>](#MParameter)  
  
6.  [<span data-ttu-id="95c3a-134">Добавление заголовка отчета</span><span class="sxs-lookup"><span data-stu-id="95c3a-134">Add a Report Title</span></span>](#MTitle)  
  
7.  [<span data-ttu-id="95c3a-135">Сохранение отчета в библиотеке SharePoint</span><span class="sxs-lookup"><span data-stu-id="95c3a-135">Save the Report to a SharePoint Library</span></span>](#MSave)  
  
8.  [<span data-ttu-id="95c3a-136">Запуск основного и детализированного отчетов</span><span class="sxs-lookup"><span data-stu-id="95c3a-136">Run the Main and Drillthrough Reports</span></span>](#MRunReports)  
  
 <span data-ttu-id="95c3a-137">Предполагаемое время для выполнения заданий данного учебника: 30 минут.</span><span class="sxs-lookup"><span data-stu-id="95c3a-137">Estimated time to complete this tutorial: 30 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95c3a-138">Требования</span><span class="sxs-lookup"><span data-stu-id="95c3a-138">Requirements</span></span>  
 <span data-ttu-id="95c3a-139">Для выполнения упражнений этого учебника требуется доступ к кубу Contoso Sales.</span><span class="sxs-lookup"><span data-stu-id="95c3a-139">This tutorial requires access to the Contoso Sales cube.</span></span> <span data-ttu-id="95c3a-140">Это требование относится как к детализированному, так и к основному отчету.</span><span class="sxs-lookup"><span data-stu-id="95c3a-140">This requirement applies to both the drillthrough and the main reports.</span></span> <span data-ttu-id="95c3a-141">Дополнительные сведения о требованиях см. в разделе [Предварительные условия для использования учебников (построитель отчетов)](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="95c3a-141">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-drillthrough-report-from-the-table-or-matrix-wizard"></a><a name="DMatrixAndDataset"></a><span data-ttu-id="95c3a-142">1. Создание детализированного отчета с помощью мастера таблицы или матрицы</span><span class="sxs-lookup"><span data-stu-id="95c3a-142">1. Create a Drillthrough Report from the Table or Matrix Wizard</span></span>  
 <span data-ttu-id="95c3a-143">Создайте в диалоговом окне Приступая к работе матричный отчет с помощью **мастера таблицы или матрицы**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-143">From the Getting Started dialog box, create a matrix report by using the **Table or Matrix Wizard**.</span></span> <span data-ttu-id="95c3a-144">Мастер поддерживает два режима работы: режим конструктора отчета и режим конструктора общего набора данных.</span><span class="sxs-lookup"><span data-stu-id="95c3a-144">There are two modes available in the wizard: report design and shared dataset design.</span></span> <span data-ttu-id="95c3a-145">В этом учебнике будет использоваться режим конструктора отчетов.</span><span class="sxs-lookup"><span data-stu-id="95c3a-145">In this tutorial, you will use the report design mode.</span></span>  
  
#### <a name="to-create-a-new-report"></a><span data-ttu-id="95c3a-146">Создание нового отчета</span><span class="sxs-lookup"><span data-stu-id="95c3a-146">To create a new report</span></span>  
  
1.  <span data-ttu-id="95c3a-147">Нажмите кнопку **Пуск**, укажите пункт **программы**, выберите пункт [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Построитель отчетов**, а затем щелкните **Построитель отчетов**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-147">Click **Start**, point to **Programs**, point to [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="95c3a-148">Откроется диалоговое окно **Приступая к работе** .</span><span class="sxs-lookup"><span data-stu-id="95c3a-148">The **Getting Started** dialog box opens.</span></span> <span data-ttu-id="95c3a-149">Если кнопка не отображается, нажмите кнопку **создать**в **Построитель отчетов** .</span><span class="sxs-lookup"><span data-stu-id="95c3a-149">If it does not appear, from the **Report Builder** button, click **New**.</span></span>  
  
2.  <span data-ttu-id="95c3a-150">Убедитесь, что на левой панели выбран **Новый отчет** .</span><span class="sxs-lookup"><span data-stu-id="95c3a-150">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="95c3a-151">Убедитесь в том, что на панели справа выбран **Мастер таблицы или матрицы** .</span><span class="sxs-lookup"><span data-stu-id="95c3a-151">In the right pane, verify that **Table or Matrix Wizard** is selected.</span></span>  
  
##  <a name="1a-specify-a-data-connection"></a><a name="DConnection"></a><span data-ttu-id="95c3a-152">SR1a.</span><span class="sxs-lookup"><span data-stu-id="95c3a-152">1a.</span></span> <span data-ttu-id="95c3a-153">Задание подключения к данным</span><span class="sxs-lookup"><span data-stu-id="95c3a-153">Specify a Data Connection</span></span>  
 <span data-ttu-id="95c3a-154">Подключение к данным содержит сведения, необходимые для подключения к внешнему источнику данных, например к кубу служб Analysis Services или базе данных [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="95c3a-154">A data connection contains the information necessary to connect to an external data source such as an Analysis Services cube or a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="95c3a-155">Чтобы указать подключение к данным, можно воспользоваться общим источником данных с сервера отчетов или создать внедренный источник данных, используемый только в этом отчете.</span><span class="sxs-lookup"><span data-stu-id="95c3a-155">To specify a data connection, you can use a shared data source from the report server or create an embedded data source that is used only in this report.</span></span> <span data-ttu-id="95c3a-156">В этом учебнике используется внедренный источник данных.</span><span class="sxs-lookup"><span data-stu-id="95c3a-156">In this tutorial, you will use an embedded data source.</span></span> <span data-ttu-id="95c3a-157">Дополнительные сведения об использовании общих источников данных см. в разделе [Альтернативные способы создания подключения к данным (построитель отчетов)](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="95c3a-157">To learn more about using a shared data source, see [Alternative Ways to Get a Data Connection &#40;Report Builder&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span></span>  
  
#### <a name="to-create-an-embedded-data-source"></a><span data-ttu-id="95c3a-158">Создание внедренного источника данных</span><span class="sxs-lookup"><span data-stu-id="95c3a-158">To create an embedded data source</span></span>  
  
1.  <span data-ttu-id="95c3a-159">На странице **Выбор набора данных** выберите команду **Создать набор данных**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-159">On the **Choose a dataset** page, select **Create a dataset**, and then click **Next**.</span></span> <span data-ttu-id="95c3a-160">Откроется страница **Выберите соединение с источником данных** .</span><span class="sxs-lookup"><span data-stu-id="95c3a-160">The **Choose a connection to a data source** page opens.</span></span>  
  
2.  <span data-ttu-id="95c3a-161">Нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-161">Click **New**.</span></span> <span data-ttu-id="95c3a-162">Откроется диалоговое окно **Свойства источника данных** .</span><span class="sxs-lookup"><span data-stu-id="95c3a-162">The **Data Source Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="95c3a-163">В текстовом поле **Имя**введите имя источника данных: **Online and Reseller Sales Detail** .</span><span class="sxs-lookup"><span data-stu-id="95c3a-163">In **Name**, type **Online and Reseller Sales Detail** as the name for the data source.</span></span>  
  
4.  <span data-ttu-id="95c3a-164">Выберите в списке **Выберите тип соединения**пункт **Microsoft SQL Server Analysis Services**и нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-164">In **Select a connection type**, select **Microsoft SQL Server Analysis Services**, and then click **Build**.</span></span>  
  
5.  <span data-ttu-id="95c3a-165">Убедитесь в том, что в поле **Источник данных**указано значение **Microsoft SQL Server Analysis Services (AdomdClient)**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-165">In **Data source**, verify that the data source is **Microsoft SQL Server Analysis Services (AdomdClient)**.</span></span>  
  
6.  <span data-ttu-id="95c3a-166">Введите в поле **Имя сервера**имя сервера, на котором установлен экземпляр служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="95c3a-166">In **Server name**, type the name of a server where an instance of Analysis Services is installed.</span></span>  
  
7.  <span data-ttu-id="95c3a-167">Выберите в поле **Выберите или введите имя базы данных**куб Contoso.</span><span class="sxs-lookup"><span data-stu-id="95c3a-167">In **Select or enter a database name**, select the Contoso cube.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
9. <span data-ttu-id="95c3a-168">Убедитесь в том, что поле **Строка подключения** содержит строку в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="95c3a-168">Verify that **Connection string** contains the following syntax:</span></span>  
  
    ```  
    Data Source=<servername>; Initial Catalog = Contoso  
    ```  
  
     <span data-ttu-id="95c3a-169">Элемент `<servername>` представляет имя экземпляра сервера [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] с установленными службами Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="95c3a-169">The `<servername>` is the name of an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] with Analysis Services installed.</span></span>  
  
10. <span data-ttu-id="95c3a-170">Выберите **Тип учетных данных**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-170">Click **Credentials type**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="95c3a-171">В зависимости от настройки разрешений для источника данных может потребоваться изменить параметры проверки подлинности по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="95c3a-171">Depending on how permissions are configured on the data source, you might need to change the default authentication options.</span></span> <span data-ttu-id="95c3a-172">Дополнительные сведения см. в разделах [Безопасность (построитель отчетов)](report-builder/security-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="95c3a-172">For more information, see [Security &#40;Report Builder&#41;](report-builder/security-report-builder.md).</span></span>  
  
11. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="95c3a-173">Откроется страница **Выбор соединения с источником данных** .</span><span class="sxs-lookup"><span data-stu-id="95c3a-173">The **Choose a connection to a data source** page appears.</span></span>  
  
12. <span data-ttu-id="95c3a-174">Нажмите кнопку **Проверить соединение**, чтобы проверить соединение с источником данных.</span><span class="sxs-lookup"><span data-stu-id="95c3a-174">To verify that you can connect to the data source, click **Test Connection**.</span></span>  
  
     <span data-ttu-id="95c3a-175">Подключение сообщения **успешно создано** .</span><span class="sxs-lookup"><span data-stu-id="95c3a-175">The message **Connection created successfully** appears.</span></span>  
  
13. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
14. <span data-ttu-id="95c3a-176">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-176">Click **Next**.</span></span>  
  
##  <a name="1b-create-an-mdx-query"></a><a name="DMDXQuery"></a><span data-ttu-id="95c3a-177">1b.</span><span class="sxs-lookup"><span data-stu-id="95c3a-177">1b.</span></span> <span data-ttu-id="95c3a-178">Создание запроса многомерных выражений</span><span class="sxs-lookup"><span data-stu-id="95c3a-178">Create an MDX Query</span></span>  
 <span data-ttu-id="95c3a-179">В отчете можно использовать общий набор данных со стандартным запросом или создать внедренный набор данных только для этого отчета.</span><span class="sxs-lookup"><span data-stu-id="95c3a-179">In a report, you can use a shared dataset that has a predefined query, or you can create an embedded dataset for use only in your report.</span></span> <span data-ttu-id="95c3a-180">В этом учебнике рассматривается создание внедренного набора данных.</span><span class="sxs-lookup"><span data-stu-id="95c3a-180">In this tutorial, you will create an embedded dataset.</span></span>  
  
#### <a name="to-create-query-filters"></a><span data-ttu-id="95c3a-181">Создание фильтров запроса</span><span class="sxs-lookup"><span data-stu-id="95c3a-181">To create query filters</span></span>  
  
1.  <span data-ttu-id="95c3a-182">На странице **Конструирование запроса** на панели Метаданные нажмите кнопку **(...)**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-182">On the **Design a query** page, in the Metadata pane, click the button **(...)**.</span></span>  
  
2.  <span data-ttu-id="95c3a-183">В диалоговом окне **Выбор куба** выберите Sales и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-183">In the **Cube Selection** dialog box, click Sales, and then click **OK**.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="95c3a-184">Если вы не хотите создавать запрос многомерных выражений вручную, щелкните значок ![Перейти в режим конструктора](media/rsqdicon-designmode.gif "Перейти в режим конструктора"), переключите конструктор запросов в режим "Запрос", вставьте в конструктор законченное многомерное выражение и перейдите к шагу 6 раздела [Создание набора данных](#DSkip).</span><span class="sxs-lookup"><span data-stu-id="95c3a-184">If you do not want to build the MDX query manually, click the ![Switch to Design mode](media/rsqdicon-designmode.gif "Switch to Design mode") icon, toggle the query designer to Query mode, paste the completed MDX to the query designer, and then proceed to step 6 in [To create the dataset](#DSkip).</span></span>  
  
    ```  
    SELECT NON EMPTY { [Measures].[Sales Amount], [Measures].[Sales Return Amount] } ON COLUMNS, NON EMPTY { ([Channel].[Channel Name].[Channel Name].ALLMEMBERS * [Product].[Product Category Name].[Product Category Name].ALLMEMBERS * [Product].[Product Subcategory Name].[Product Subcategory Name].ALLMEMBERS ) } DIMENSION PROPERTIES MEMBER_CAPTION, MEMBER_UNIQUE_NAME ON ROWS FROM ( SELECT ( { [Date].[Calendar Year].&[2009] } ) ON COLUMNS FROM ( SELECT ( { [Sales Territory].[Sales Territory Group].&[North America] } ) ON COLUMNS FROM ( SELECT ( STRTOSET(@ProductProductCategoryName, CONSTRAINED) ) ON COLUMNS FROM ( SELECT ( { [Channel].[Channel Name].&[2], [Channel].[Channel Name].&[4] } ) ON COLUMNS FROM [Sales])))) WHERE ( [Sales Territory].[Sales Territory Group].&[North America], [Date].[Calendar Year].&[2009] ) CELL PROPERTIES VALUE, BACK_COLOR, FORE_COLOR, FORMATTED_VALUE, FORMAT_STRING, FONT_NAME, FONT_SIZE, FONT_FLAGS  
    ```  
  
3.  <span data-ttu-id="95c3a-185">Разверните на панели "Группа мер" узел "Канал" и перетащите "Имя канала" в столбец **Иерархия** на панели фильтра.</span><span class="sxs-lookup"><span data-stu-id="95c3a-185">In the Measure Group pane, expand Channel, and then drag Channel Name to the **Hierarchy** column in the filter pane.</span></span>  
  
     <span data-ttu-id="95c3a-186">Имя размерности "Канал" автоматически добавляется в столбец **Размерность** .</span><span class="sxs-lookup"><span data-stu-id="95c3a-186">The dimension name, Channel, is automatically added to the **Dimension** column.</span></span> <span data-ttu-id="95c3a-187">Не меняйте значения в столбцах **Размерность** и **Оператор** .</span><span class="sxs-lookup"><span data-stu-id="95c3a-187">Do not change the **Dimension** or **Operator** columns.</span></span>  
  
4.  <span data-ttu-id="95c3a-188">Чтобы открыть список **Критерий фильтра** , щелкните стрелку вниз в столбце **Критерий фильтра** .</span><span class="sxs-lookup"><span data-stu-id="95c3a-188">To open the **Filter Expression** list, click the down arrow in the **Filter Expression** column.</span></span>  
  
5.  <span data-ttu-id="95c3a-189">В списке критериев фильтра разверните узел **Весь канал**, выберите **Online**, затем **Reseller**, после чего нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-189">In the filter expression list, expand **All Channel**, click **Online**, click **Reseller**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="95c3a-190">Теперь запрос содержит фильтр, включающий только эти каналы: Online и Reseller.</span><span class="sxs-lookup"><span data-stu-id="95c3a-190">The query now includes a filter to include only these channels: Online and Reseller.</span></span>  
  
6.  <span data-ttu-id="95c3a-191">Разверните размерность "Территория продаж", затем перетащите элемент "Группа территорий продаж" в столбец **Иерархия** ниже элемента **Имя канала**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-191">Expand the Sales Territory dimension, and then drag Sales Territory Group to the **Hierarchy** column (below **Channel Name**).</span></span>  
  
7.  <span data-ttu-id="95c3a-192">Откройте список **Критерий фильтра** , разверните узел **Территория продаж: все**, выберите элемент **Северная Америка**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-192">Open the **Filter Expression** list, expand **All Sales Territory**, click **North America**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="95c3a-193">Теперь запрос содержит фильтр, включающий только продажи в Северной Америке.</span><span class="sxs-lookup"><span data-stu-id="95c3a-193">The query now has a filter to include only sales in North America.</span></span>  
  
8.  <span data-ttu-id="95c3a-194">Разверните на панели "Группа мер" узел "Дата", затем перетащите "Календарный год" в столбец **Иерархия** на панели фильтра.</span><span class="sxs-lookup"><span data-stu-id="95c3a-194">In the Measure Group pane, expand Date, and then drag Calendar Year to the **Hierarchy** column in the filter pane.</span></span>  
  
     <span data-ttu-id="95c3a-195">Имя размерности "Дата" автоматически добавляется в столбец **Размерность** .</span><span class="sxs-lookup"><span data-stu-id="95c3a-195">The dimension name, Date, is automatically added to the **Dimension** column.</span></span> <span data-ttu-id="95c3a-196">Не меняйте значения в столбцах **Размерность** и **Оператор** .</span><span class="sxs-lookup"><span data-stu-id="95c3a-196">Do not change the **Dimension** or **Operator** columns.</span></span>  
  
9. <span data-ttu-id="95c3a-197">Чтобы открыть список **Критерий фильтра** , щелкните стрелку вниз в столбце **Критерий фильтра** .</span><span class="sxs-lookup"><span data-stu-id="95c3a-197">To open the **Filter Expression** list, click the down arrow in the **Filter Expression** column.</span></span>  
  
10. <span data-ttu-id="95c3a-198">В списке критериев фильтра разверните узел **Дата: все**, выберите элемент **Год 2009**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-198">In the filter expression list, expand **All Date**, click **Year 2009**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="95c3a-199">Теперь запрос содержит фильтр, включающий только 2009 календарный год.</span><span class="sxs-lookup"><span data-stu-id="95c3a-199">The query now includes a filter to include only the calendar year 2009.</span></span>  
  
#### <a name="to-create-the-parameter"></a><span data-ttu-id="95c3a-200">Создание параметра</span><span class="sxs-lookup"><span data-stu-id="95c3a-200">To create the parameter</span></span>  
  
1.  <span data-ttu-id="95c3a-201">Разверните размерность "Продукт", а затем перетащите элемент "Имя категории продуктов" в столбец **Иерархия** ниже элемента **Календарный год**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-201">Expand the Product dimension, and then drag the Product Category Name member to the **Hierarchy** column below **Calendar Year**.</span></span>  
  
2.  <span data-ttu-id="95c3a-202">Откройте список **Критерий фильтра** , выберите элемент **Все продукты**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-202">Open the **Filter Expression** list, click **All Products**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="95c3a-203">Установите флажок **Параметр** .</span><span class="sxs-lookup"><span data-stu-id="95c3a-203">Click the **Parameter** checkbox.</span></span> <span data-ttu-id="95c3a-204">Теперь запрос содержит параметр ProductProductCategoryName.</span><span class="sxs-lookup"><span data-stu-id="95c3a-204">The query now includes the parameter ProductProductCategoryName.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="95c3a-205">Параметр содержит имена категорий продуктов.</span><span class="sxs-lookup"><span data-stu-id="95c3a-205">The parameter contains the names of product categories.</span></span> <span data-ttu-id="95c3a-206">Если щелкнуть имя категории продуктов в основном отчете, его имя передается в детализированный отчет с использованием данного параметра.</span><span class="sxs-lookup"><span data-stu-id="95c3a-206">When you click a product category name in the main report, its name is passed to the drillthrough report by using this parameter.</span></span>  
  
###  <a name="to-create-the-dataset"></a><a name="DSkip"></a><span data-ttu-id="95c3a-207">Создание набора данных</span><span class="sxs-lookup"><span data-stu-id="95c3a-207">To create the dataset</span></span>  
  
1.  <span data-ttu-id="95c3a-208">Из размерности "Канал" перетащите элемент "Имя канала" на панель данных.</span><span class="sxs-lookup"><span data-stu-id="95c3a-208">From the Channel dimension, drag Channel Name to the data pane.</span></span>  
  
2.  <span data-ttu-id="95c3a-209">Из размерности "Продукт" перетащите элемент "Имя категории продуктов" на панель данных, разместив его справа от элемента "Имя канала".</span><span class="sxs-lookup"><span data-stu-id="95c3a-209">From the Product dimension, drag Product Category Name to the data pane, and then place it to the right of Channel Name.</span></span>  
  
3.  <span data-ttu-id="95c3a-210">Из размерности "Продукт" перетащите элемент "Имя подкатегории продуктов" на панель данных, разместив его справа от элемента "Имя категории продуктов".</span><span class="sxs-lookup"><span data-stu-id="95c3a-210">From the Product dimension, drag Product Subcategory Name to the data pane, and then place it to the right of Product Category Name.</span></span>  
  
4.  <span data-ttu-id="95c3a-211">На панели "Метаданные" разверните узел **Мера**, а затем разверните узел "Продажи".</span><span class="sxs-lookup"><span data-stu-id="95c3a-211">In the Metadata pane, expand **Measure**, and then expand Sales.</span></span>  
  
5.  <span data-ttu-id="95c3a-212">Перетащите меру "Объем продаж" на панель данных, разместив ее справа от элемента "Имя подкатегории продуктов".</span><span class="sxs-lookup"><span data-stu-id="95c3a-212">Drag the Sales Amount measure to the data pane, and then place it to the right of Product Subcategory Name.</span></span>  
  
6.  <span data-ttu-id="95c3a-213">На панели инструментов конструктора запросов нажмите кнопку **выполнить (!)**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-213">On the query designer toolbar, click **Run (!)**.</span></span>  
  
7.  <span data-ttu-id="95c3a-214">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-214">Click **Next**.</span></span>  
  
##  <a name="1c-organize-data-into-groups"></a><a name="DLayout"></a><span data-ttu-id="95c3a-215">1C.</span><span class="sxs-lookup"><span data-stu-id="95c3a-215">1c.</span></span> <span data-ttu-id="95c3a-216">Упорядочение данных по группам</span><span class="sxs-lookup"><span data-stu-id="95c3a-216">Organize Data into Groups</span></span>  
 <span data-ttu-id="95c3a-217">При выборе полей для группирования данных создается матрица со строками и столбцами, отображающими подробные и агрегированные данные.</span><span class="sxs-lookup"><span data-stu-id="95c3a-217">When you select the fields on which to group the data, you design a matrix with rows and columns that displays detail and aggregated data.</span></span>  
  
#### <a name="to-organize-data-into-groups"></a><span data-ttu-id="95c3a-218">Организация данных в группы</span><span class="sxs-lookup"><span data-stu-id="95c3a-218">To organize data into groups</span></span>  
  
1.  <span data-ttu-id="95c3a-219">Щелкните **Конструктор**для переключения в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="95c3a-219">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="95c3a-220">На странице **Размещение полей** перетащите элемент Имя_подкатегории_продуктов в область **Группы строк**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-220">On the **Arrange fields** page, drag Product_Subcategory_Name to **Row groups**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="95c3a-221">Пробелы в именах заменяются на символы подчеркивания (_).</span><span class="sxs-lookup"><span data-stu-id="95c3a-221">The spaces in the names are replaced with underscores (_).</span></span> <span data-ttu-id="95c3a-222">Например, "Имя категории продуктов" превращается в Имя_категории_продуктов.</span><span class="sxs-lookup"><span data-stu-id="95c3a-222">For example Product Category Name is Product_Category_Name.</span></span>  
  
3.  <span data-ttu-id="95c3a-223">Перетащите элемент Имя_канала в область **Группы столбцов**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-223">Drag Channel_Name to **Column groups**.</span></span>  
  
4.  <span data-ttu-id="95c3a-224">Перетащите элемент Объем_продаж в область **Значения**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-224">Drag Sales_Amount to **Values**.</span></span>  
  
     <span data-ttu-id="95c3a-225">Объем_продаж автоматически вычисляется с помощью функции Sum, используемой по умолчанию для статистических вычислений.</span><span class="sxs-lookup"><span data-stu-id="95c3a-225">Sales_Amount is automatically aggregated by the Sum function, the default aggregate for numeric fields.</span></span> <span data-ttu-id="95c3a-226">Значение — `[Sum(Sales_Amount)]`.</span><span class="sxs-lookup"><span data-stu-id="95c3a-226">The value is `[Sum(Sales_Amount)]`.</span></span>  
  
     <span data-ttu-id="95c3a-227">Для просмотра других доступных агрегатных функций откройте раскрывающийся список (не меняйте агрегатную функцию).</span><span class="sxs-lookup"><span data-stu-id="95c3a-227">To view the other aggregate functions available, open the drop-down list (do not change the aggregate function).</span></span>  
  
5.  <span data-ttu-id="95c3a-228">Перетащите элемент Выручка_от_продаж в область **Значения**, разместив его под элементом `[Sum(Sales_Amount)]`.</span><span class="sxs-lookup"><span data-stu-id="95c3a-228">Drag Sales_Return_Amount to **Values**, and then place it below `[Sum(Sales_Amount)]`.</span></span>  
  
     <span data-ttu-id="95c3a-229">Шаги 4 и 5 задают данные, отображаемые в матрице.</span><span class="sxs-lookup"><span data-stu-id="95c3a-229">Steps 4 and 5 specify the data to display in the matrix.</span></span>  
  
6.  <span data-ttu-id="95c3a-230">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-230">Click **Next**.</span></span>  
  
##  <a name="1d-add-subtotals-and-totals"></a><a name="DTotals"></a><span data-ttu-id="95c3a-231">1д.</span><span class="sxs-lookup"><span data-stu-id="95c3a-231">1d.</span></span> <span data-ttu-id="95c3a-232">Добавление подытогов и итогов</span><span class="sxs-lookup"><span data-stu-id="95c3a-232">Add Subtotals and Totals</span></span>  
 <span data-ttu-id="95c3a-233">После создания групп можно добавить и отформатировать строки, в которых будут отображаться значения агрегатной обработки полей.</span><span class="sxs-lookup"><span data-stu-id="95c3a-233">After you create groups, you can add and format rows where the aggregate values for the fields will display.</span></span> <span data-ttu-id="95c3a-234">Можно также выбрать режим отображения данных: показывать все или позволить пользователю сворачивать и разворачивать сгруппированные данные интерактивно.</span><span class="sxs-lookup"><span data-stu-id="95c3a-234">You can also choose whether to show all the data or to let a user expand and collapse grouped data interactively.</span></span>  
  
#### <a name="to-add-subtotals-and-totals"></a><span data-ttu-id="95c3a-235">Добавление подытогов и итогов</span><span class="sxs-lookup"><span data-stu-id="95c3a-235">To add subtotals and totals</span></span>  
  
1.  <span data-ttu-id="95c3a-236">На странице **Выбор макета** в разделе **Параметры**убедитесь, что выбран параметр **Показывать подытоги и общие итоги** .</span><span class="sxs-lookup"><span data-stu-id="95c3a-236">On the **Choose the layout** page, under **Options**, verify that **Show subtotals and grand totals** is selected.</span></span>  
  
     <span data-ttu-id="95c3a-237">На панели просмотра в мастере отображается матрица с четырьмя строками.</span><span class="sxs-lookup"><span data-stu-id="95c3a-237">The wizard Preview pane displays a matrix with four rows.</span></span>  
  
2.  <span data-ttu-id="95c3a-238">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-238">Click **Next**.</span></span>  
  
##  <a name="1e-choose-a-style"></a><a name="DStyle"></a><span data-ttu-id="95c3a-239">1E.</span><span class="sxs-lookup"><span data-stu-id="95c3a-239">1e.</span></span> <span data-ttu-id="95c3a-240">Выбор стиля</span><span class="sxs-lookup"><span data-stu-id="95c3a-240">Choose a Style</span></span>  
 <span data-ttu-id="95c3a-241">Стиль задает стиль шрифта, набор цветов и стиль границы.</span><span class="sxs-lookup"><span data-stu-id="95c3a-241">A style specifies a font style, a set of colors, and a border style.</span></span>  
  
#### <a name="to-specify-a-style"></a><span data-ttu-id="95c3a-242">Задание стиля</span><span class="sxs-lookup"><span data-stu-id="95c3a-242">To specify a style</span></span>  
  
1.  <span data-ttu-id="95c3a-243">На странице **Выбор стиля** на панели Стили выберите элемент содержание.</span><span class="sxs-lookup"><span data-stu-id="95c3a-243">On the **Choose a Style** page, in the Styles pane, select Slate.</span></span>  
  
2.  <span data-ttu-id="95c3a-244">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-244">Click **Finish**.</span></span>  
  
     <span data-ttu-id="95c3a-245">Таблица добавляется в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="95c3a-245">The table is added to the design surface.</span></span>  
  
3.  <span data-ttu-id="95c3a-246">Нажмите кнопку **Выполнить (!)**, чтобы выполнить предварительный просмотр отчета.</span><span class="sxs-lookup"><span data-stu-id="95c3a-246">To preview the report, click **Run (!)**.</span></span>  
  
##  <a name="2-format-data-as-currency"></a><a name="DFormat"></a><span data-ttu-id="95c3a-247">2. Форматирование данных в денежном формате</span><span class="sxs-lookup"><span data-stu-id="95c3a-247">2. Format Data as Currency</span></span>  
 <span data-ttu-id="95c3a-248">Добавьте форматирование в денежном формате для полей объема продаж в детализированном отчете.</span><span class="sxs-lookup"><span data-stu-id="95c3a-248">Apply currency formatting to the sales amount fields in the drillthrough report.</span></span>  
  
#### <a name="to-format-data-as-currency"></a><span data-ttu-id="95c3a-249">Форматирование данных в денежном формате</span><span class="sxs-lookup"><span data-stu-id="95c3a-249">To format data as currency</span></span>  
  
1.  <span data-ttu-id="95c3a-250">Щелкните **Конструктор**для переключения в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="95c3a-250">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="95c3a-251">Чтобы выбрать и отформатировать несколько ячеек одновременно, выберите ячейки, содержащие числовые данные о продажах, удерживая клавишу Ctrl.</span><span class="sxs-lookup"><span data-stu-id="95c3a-251">To select and format multiple cells at one time, press the Ctrl key, and then select the cells that contain the numeric sales data.</span></span>  
  
3.  <span data-ttu-id="95c3a-252">На вкладке **Главная** в группе **Число** нажмите кнопку **Валюта**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-252">On the **Home** tab, in the **Number** group, click **Currency**.</span></span>  
  
##  <a name="3-add-columns-to-show-sales-values-in-sparklines"></a><a name="DSparkline"></a><span data-ttu-id="95c3a-253">3. Добавление столбцов для отображения значений продаж в спарклайнах</span><span class="sxs-lookup"><span data-stu-id="95c3a-253">3. Add Columns to Show Sales Values in Sparklines</span></span>  
 <span data-ttu-id="95c3a-254">Вместо того чтобы отображать данные по продажам и выручке от продаж в виде денежных сумм, отчет показывает их в виде спарклайна.</span><span class="sxs-lookup"><span data-stu-id="95c3a-254">Instead of showing sales and sales returns as currency values, the report shows the values in a sparkline.</span></span>  
  
#### <a name="to-add-sparklines-to-columns"></a><span data-ttu-id="95c3a-255">Добавление спарклайн-графиков в столбцы</span><span class="sxs-lookup"><span data-stu-id="95c3a-255">To add sparklines to columns</span></span>  
  
1.  <span data-ttu-id="95c3a-256">Щелкните **Конструктор**для переключения в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="95c3a-256">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="95c3a-257">В группе "Итого" матрицы щелкните правой кнопкой мыши столбец **Объем продаж** , выберите пункт **Вставить столбец**, после чего выберите **Справа**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-257">In the Total group of the matrix, right-click the **Sales Amount** column, click **Insert Column**, and then click **Right**.</span></span>  
  
     <span data-ttu-id="95c3a-258">Справа от столбца **Объем продаж**добавляется пустой столбец.</span><span class="sxs-lookup"><span data-stu-id="95c3a-258">An empty column is added to the right of **Sales Amount**.</span></span>  
  
3.  <span data-ttu-id="95c3a-259">Выберите на ленте **Прямоугольник**, а затем щелкните пустую ячейку справа от ячейки `[Sum(Sales_Amount)]` в группе строк [Подкатегория_продуктов].</span><span class="sxs-lookup"><span data-stu-id="95c3a-259">On the ribbon, click **Rectangle**, and then click the empty cell to the right of the `[Sum(Sales_Amount)]` cell in the [Product_Subcategory] row group.</span></span>  
  
4.  <span data-ttu-id="95c3a-260">Выберите на ленте значок **Спарклайн** , а затем щелкните ячейку, куда был добавлен прямоугольник.</span><span class="sxs-lookup"><span data-stu-id="95c3a-260">On the ribbon, click the **Sparkline** icon, and then click the cell where the rectangle was added.</span></span>  
  
5.  <span data-ttu-id="95c3a-261">Убедитесь в том, что в диалоговом окне **Выбор типа спарклайн-графика** выбран тип **Столбец** .</span><span class="sxs-lookup"><span data-stu-id="95c3a-261">In the **Select Sparkline Type** dialog box, verify that **Column** type is selected.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="95c3a-262">Щелкните правой кнопкой мыши спарклайн.</span><span class="sxs-lookup"><span data-stu-id="95c3a-262">Right-click the sparkline.</span></span>  
  
8.  <span data-ttu-id="95c3a-263">Щелкните на панели "Данные диаграммы" значок **Добавить поле** , а затем выберите Объем_продаж.</span><span class="sxs-lookup"><span data-stu-id="95c3a-263">In the Chart Data pane, click the **Add field** icon, and then click Sales_Amount.</span></span>  
  
9. <span data-ttu-id="95c3a-264">Щелкните правой кнопкой мыши столбец `Sales_Return_Amount` , затем добавьте справа от него новый столбец.</span><span class="sxs-lookup"><span data-stu-id="95c3a-264">Right-click the `Sales_Return_Amount` column, and then add a column to the right of it.</span></span>  
  
10. <span data-ttu-id="95c3a-265">Повторите шаги с 2 по 6.</span><span class="sxs-lookup"><span data-stu-id="95c3a-265">Repeat steps 2 through 6.</span></span>  
  
11. <span data-ttu-id="95c3a-266">Щелкните правой кнопкой мыши спарклайн.</span><span class="sxs-lookup"><span data-stu-id="95c3a-266">Right-click the sparkline.</span></span>  
  
12. <span data-ttu-id="95c3a-267">Щелкните на панели "Данные диаграммы" значок **Добавить поле** , а затем выберите Выручка_от_продаж.</span><span class="sxs-lookup"><span data-stu-id="95c3a-267">In the Chart Data pane, click the **Add field** icon, and then click Sales_Return_Amount.</span></span>  
  
13. <span data-ttu-id="95c3a-268">Нажмите кнопку **Выполнить**, чтобы выполнить предварительный просмотр отчета.</span><span class="sxs-lookup"><span data-stu-id="95c3a-268">To preview the report, click **Run**.</span></span>  
  
##  <a name="4-add-report-title-with-product-category-name"></a><a name="DReportTitle"></a><span data-ttu-id="95c3a-269">4. Добавление заголовка отчета с названием категории продукта</span><span class="sxs-lookup"><span data-stu-id="95c3a-269">4. Add Report Title with Product Category Name</span></span>  
 <span data-ttu-id="95c3a-270">Заголовок отчета отображается в верхней части отчета.</span><span class="sxs-lookup"><span data-stu-id="95c3a-270">A report title appears at the top of the report.</span></span> <span data-ttu-id="95c3a-271">Можно поместить заголовок отчета в верхнем колонтитуле или, если в отчете колонтитулы не используются, в текстовом поле в верхней части текста отчета.</span><span class="sxs-lookup"><span data-stu-id="95c3a-271">You can place the report title in a report header or, if the report does not use one, in a text box at the top of the report body.</span></span> <span data-ttu-id="95c3a-272">В данном учебнике это текстовое поле автоматически размещается в верхней части текста отчета.</span><span class="sxs-lookup"><span data-stu-id="95c3a-272">In this tutorial, you will use the text box that is automatically placed at the top of the report body.</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="95c3a-273">Добавление заголовка отчета</span><span class="sxs-lookup"><span data-stu-id="95c3a-273">To add a report title</span></span>  
  
1.  <span data-ttu-id="95c3a-274">Щелкните **Конструктор**для переключения в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="95c3a-274">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="95c3a-275">В области конструктора щелкните ссылку **Щелкните, чтобы добавить заголовок**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-275">On the design surface, click **Click to add title**.</span></span>  
  
3.  <span data-ttu-id="95c3a-276">Введите текст **Объемы продаж и выручка от продаж для категории:**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-276">Type **Sales and Returns for Category:**.</span></span>  
  
4.  <span data-ttu-id="95c3a-277">Щелкните это поле правой кнопкой мыши и выберите пункт **Создать заполнитель**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-277">Right-click, and then click **Create Placeholder**.</span></span>  
  
5.  <span data-ttu-id="95c3a-278">Нажмите кнопку **(fx)** справа от списка **Значение** .</span><span class="sxs-lookup"><span data-stu-id="95c3a-278">Click the **(fx)** button to the right of the **Value** list.</span></span>  
  
6.  <span data-ttu-id="95c3a-279">На панели "Категория" диалогового окна **Выражение** выберите пункт **Набор данных**, а затем в списке **Значения** дважды щелкните элемент `First(Product_Category_Name)`.</span><span class="sxs-lookup"><span data-stu-id="95c3a-279">In the **Expression** dialog box, in the Category pane, click **Dataset**, and then in the **Values** list double-click `First(Product_Category_Name)`.</span></span>  
  
     <span data-ttu-id="95c3a-280">Поле **Выражение** содержит следующее выражение:</span><span class="sxs-lookup"><span data-stu-id="95c3a-280">The **Expression** box contains the following expression:</span></span>  
  
    ```  
    =First(Fields!Product_Category_Name.Value, "DataSet1")  
    ```  
  
7.  <span data-ttu-id="95c3a-281">Нажмите кнопку **Выполнить**, чтобы выполнить предварительный просмотр отчета.</span><span class="sxs-lookup"><span data-stu-id="95c3a-281">To preview the report, click **Run**.</span></span>  
  
 <span data-ttu-id="95c3a-282">Заголовок отчета содержит имя первой категории продуктов.</span><span class="sxs-lookup"><span data-stu-id="95c3a-282">The report title includes the name of the first product category.</span></span> <span data-ttu-id="95c3a-283">В дальнейшем, когда отчет запускается в виде детализированного отчета, имя категории продуктов будет динамически меняться, отражая имя категории продуктов, которая была нажата в основном отчете.</span><span class="sxs-lookup"><span data-stu-id="95c3a-283">Later, after you run this report as a drillthrough report, the product category name will dynamically change to reflect the name of the product category that was clicked in the main report.</span></span>  
  
##  <a name="5-update-parameter-properties"></a><a name="DParameter"></a><span data-ttu-id="95c3a-284">5. свойства параметров обновления</span><span class="sxs-lookup"><span data-stu-id="95c3a-284">5. Update Parameter Properties</span></span>  
 <span data-ttu-id="95c3a-285">По умолчанию параметры видимы, но для данного отчета это неприемлемо.</span><span class="sxs-lookup"><span data-stu-id="95c3a-285">By default parameters are visible, which is not appropriate for this report.</span></span> <span data-ttu-id="95c3a-286">Поэтому мы обновим свойства параметров детализированного отчета.</span><span class="sxs-lookup"><span data-stu-id="95c3a-286">You will update the parameter properties for the drillthrough report.</span></span>  
  
#### <a name="to-hide-a-parameter"></a><span data-ttu-id="95c3a-287">Скрытие параметра</span><span class="sxs-lookup"><span data-stu-id="95c3a-287">To hide a parameter</span></span>  
  
1.  <span data-ttu-id="95c3a-288">В области данных отчета разверните узел **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-288">In the Report Data pane, expand **Parameters**.</span></span>  
  
2.  <span data-ttu-id="95c3a-289">Щелкните правой кнопкой мыши \@ ProductProductCategoryName и выберите пункт **Свойства параметра**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-289">Right-click \@ProductProductCategoryName, and then click **Parameter Properties**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="95c3a-290">Символ \@ рядом с именем указывает на то, что это параметр.</span><span class="sxs-lookup"><span data-stu-id="95c3a-290">The \@ character next to the name indicates that this is a parameter.</span></span>  
  
3.  <span data-ttu-id="95c3a-291">На вкладке **Общие** установите флажок **Скрытый**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-291">On the **General** tab, click **Hidden**.</span></span>  
  
4.  <span data-ttu-id="95c3a-292">В поле **Запрос** введите **Категория продуктов**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-292">In the **Prompt** box, type **Product Category**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="95c3a-293">Поскольку параметр является скрытым, эта подсказка никогда не используется.</span><span class="sxs-lookup"><span data-stu-id="95c3a-293">Because the parameter is hidden, this prompt is never used.</span></span>  
  
5.  <span data-ttu-id="95c3a-294">По желанию можно открыть вкладки **Доступные значения** и **Значения по умолчанию** и просмотреть параметры, доступные на них.</span><span class="sxs-lookup"><span data-stu-id="95c3a-294">Optionally, click **Available Values** and **Default Values** and review their options.</span></span> <span data-ttu-id="95c3a-295">Не изменяйте параметры на этих вкладках.</span><span class="sxs-lookup"><span data-stu-id="95c3a-295">Do not change any options on these tabs.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="6-save-the-report-to-a-sharepoint-library"></a><a name="DSave"></a><span data-ttu-id="95c3a-296">6. Сохранение отчета в библиотеке SharePoint</span><span class="sxs-lookup"><span data-stu-id="95c3a-296">6. Save the Report to a SharePoint Library</span></span>  
 <span data-ttu-id="95c3a-297">Отчет можно сохранить в библиотеке SharePoint, на сервере отчетов или на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="95c3a-297">You can save the report to a SharePoint library, report server, or your computer.</span></span> <span data-ttu-id="95c3a-298">При сохранении отчета на локальном компьютере некоторые возможности служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , например работа с элементами отчетов и вложенными отчетами, будут недоступны.</span><span class="sxs-lookup"><span data-stu-id="95c3a-298">If you save the report to your computer, a number of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features such as report parts and subreports are not available.</span></span> <span data-ttu-id="95c3a-299">В этом занятии отчет будет сохранен в библиотеке SharePoint.</span><span class="sxs-lookup"><span data-stu-id="95c3a-299">In this tutorial, you will save the report to a SharePoint library.</span></span>  
  
#### <a name="to-save-the-report"></a><span data-ttu-id="95c3a-300">Сохранение отчета</span><span class="sxs-lookup"><span data-stu-id="95c3a-300">To save the report</span></span>  
  
1.  <span data-ttu-id="95c3a-301">В построителе отчетов нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-301">From the Report Builder button, click **Save**.</span></span> <span data-ttu-id="95c3a-302">Откроется диалоговое окно **Сохранение отчета** .</span><span class="sxs-lookup"><span data-stu-id="95c3a-302">The **Save As Report** dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="95c3a-303">Во время повторного сохранения отчет автоматически сохраняется в предыдущем расположении.</span><span class="sxs-lookup"><span data-stu-id="95c3a-303">If you are resaving a report, it is automatically resaved to its previous location.</span></span> <span data-ttu-id="95c3a-304">Чтобы изменить расположение, используйте вариант **Сохранить как** .</span><span class="sxs-lookup"><span data-stu-id="95c3a-304">To change the location, use the **Save As** option.</span></span>  
  
2.  <span data-ttu-id="95c3a-305">Также можно перейти по ссылке **Последние сайты и серверы**, чтобы вывести список недавно использовавшихся серверов отчетов и сайтов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="95c3a-305">To show a list of recently used report servers and SharePoint sites, click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="95c3a-306">Выберите или введите имя сайта SharePoint, на котором у вас имеется разрешение на сохранение отчетов.</span><span class="sxs-lookup"><span data-stu-id="95c3a-306">Select or type the name of the SharePoint site where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="95c3a-307">URL-адрес библиотеки SharePoint имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="95c3a-307">The URL of the SharePoint library has the following syntax:</span></span>  
  
    ```  
    Http://<ServerName>/<Sites>/  
    ```  
  
4.  <span data-ttu-id="95c3a-308">Выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-308">Click **Save**.</span></span>  
  
     <span data-ttu-id="95c3a-309">Список**Последние сайты и серверы** включает библиотеки на сайте SharePoint.</span><span class="sxs-lookup"><span data-stu-id="95c3a-309">**Recent Sites and Servers** lists the libraries on the SharePoint site.</span></span>  
  
5.  <span data-ttu-id="95c3a-310">Перейдите к библиотеке, в которой необходимо сохранить отчет.</span><span class="sxs-lookup"><span data-stu-id="95c3a-310">Navigate to the library where you will save the report.</span></span>  
  
6.  <span data-ttu-id="95c3a-311">В поле **Имя** замените имя по умолчанию на строку **ResellerVSOnlineDrillthrough**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-311">In the **Name** box, replace the default name with **ResellerVSOnlineDrillthrough**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="95c3a-312">В следующем занятии мы сохраним в том же расположении основной отчет.</span><span class="sxs-lookup"><span data-stu-id="95c3a-312">You will save the main report to the same location.</span></span> <span data-ttu-id="95c3a-313">Если нужно сохранить основной и детализированный отчет на разных сайтах или в разных библиотеках, необходимо обновить путь в действии **Переход к отчету** основного отчета.</span><span class="sxs-lookup"><span data-stu-id="95c3a-313">If you want to save the main and drillthrough reports to different sites or libraries, you must update the path of the **Go to report** action in the main report.</span></span>  
  
7.  <span data-ttu-id="95c3a-314">Выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-314">Click **Save**.</span></span>  
  
##  <a name="1-create-a-new-report-from-the-table-or-matrix-wizard"></a><a name="MMatrixAndDataset"></a><span data-ttu-id="95c3a-315">1. Создание нового отчета с помощью мастера таблицы или матрицы</span><span class="sxs-lookup"><span data-stu-id="95c3a-315">1. Create a New Report from the Table or Matrix Wizard</span></span>  
 <span data-ttu-id="95c3a-316">Создайте в диалоговом окне **Приступая к работе** матричный отчет с помощью **мастера таблицы или матрицы**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-316">From the **Getting Started** dialog box, create a matrix report by using the **Table or Matrix Wizard**.</span></span>  
  
#### <a name="to-create-a-new-report"></a><span data-ttu-id="95c3a-317">Создание нового отчета</span><span class="sxs-lookup"><span data-stu-id="95c3a-317">To create a new report</span></span>  
  
1.  <span data-ttu-id="95c3a-318">Нажмите кнопку **Пуск**, укажите пункт **программы**, выберите пункт [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Построитель отчетов**, а затем щелкните **Построитель отчетов**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-318">Click **Start**, point to **Programs**, point to [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Report Builder**, and then click **Report Builder**.</span></span>  
  
2.  <span data-ttu-id="95c3a-319">Убедитесь в том, что в диалоговом окне **Приступая к работе** выбран пункт **Новый отчет** , после чего щелкните **Мастер таблиц или матриц**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-319">In the **Getting Started** dialog box, verify that **New Report** is selected, and then click **Table or Matrix Wizard**.</span></span>  
  
##  <a name="1a-specify-a-data-connection"></a><a name="MConnection"></a><span data-ttu-id="95c3a-320">SR1a.</span><span class="sxs-lookup"><span data-stu-id="95c3a-320">1a.</span></span> <span data-ttu-id="95c3a-321">Задание подключения к данным</span><span class="sxs-lookup"><span data-stu-id="95c3a-321">Specify a Data Connection</span></span>  
 <span data-ttu-id="95c3a-322">Добавим в основной отчет внедренный источник данных.</span><span class="sxs-lookup"><span data-stu-id="95c3a-322">You will add an embedded data source to the main report.</span></span>  
  
#### <a name="to-create-an-embedded-data-source"></a><span data-ttu-id="95c3a-323">Создание внедренного источника данных</span><span class="sxs-lookup"><span data-stu-id="95c3a-323">To create an embedded data source</span></span>  
  
1.  <span data-ttu-id="95c3a-324">На странице **Выбор набора данных** выберите команду **Создать набор данных**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-324">On the **Choose a dataset** page, select **Create a dataset**, and then click **Next**.</span></span>  
  
2.  <span data-ttu-id="95c3a-325">Нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-325">Click **New**.</span></span>  
  
3.  <span data-ttu-id="95c3a-326">В поле **Имя**введите имя источника данных: **Online and Reseller Sales Main** .</span><span class="sxs-lookup"><span data-stu-id="95c3a-326">In **Name**, type **Online and Reseller Sales Main** as the name for the data source.</span></span>  
  
4.  <span data-ttu-id="95c3a-327">Выберите в списке **Выберите тип соединения**пункт **Microsoft SQL Server Analysis Services**и нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-327">In **Select a connection type**, select **Microsoft SQL Server Analysis Services**, and then click **Build**.</span></span>  
  
5.  <span data-ttu-id="95c3a-328">Убедитесь в том, что в поле **Источник данных**указано значение **Microsoft SQL Server Analysis Services (AdomdClient)**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-328">In **Data source**, verify that the data source is **Microsoft SQL Server Analysis Services (AdomdClient)**.</span></span>  
  
6.  <span data-ttu-id="95c3a-329">В поле **имя сервера**введите имя сервера, на котором [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] установлен экземпляр.</span><span class="sxs-lookup"><span data-stu-id="95c3a-329">In **Server name**, type the name of a server where an instance of [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] is installed.</span></span>  
  
7.  <span data-ttu-id="95c3a-330">Выберите в поле **Выберите или введите имя базы данных**куб Contoso.</span><span class="sxs-lookup"><span data-stu-id="95c3a-330">In **Select or enter a database name**, select the Contoso cube.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
9. <span data-ttu-id="95c3a-331">Убедитесь в том, что поле **Строка подключения** содержит строку в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="95c3a-331">Verify that the **Connection string** contains the following syntax:</span></span>  
  
    ```  
    Data Source=<servername>; Initial Catalog = Contoso  
    ```  
  
10. <span data-ttu-id="95c3a-332">Выберите **Тип учетных данных**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-332">Click **Credentials type**.</span></span>  
  
     <span data-ttu-id="95c3a-333">В зависимости от настройки разрешений для источника данных может потребоваться изменить параметры проверки подлинности по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="95c3a-333">Depending on how permissions are configured on the data source, you might need to change the default authentication.</span></span>  
  
11. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
12. <span data-ttu-id="95c3a-334">Нажмите кнопку **Проверить соединение**, чтобы проверить соединение с источником данных.</span><span class="sxs-lookup"><span data-stu-id="95c3a-334">To verify that you can connect to the data source, click **Test Connection**.</span></span>  
  
13. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
14. <span data-ttu-id="95c3a-335">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-335">Click **Next**.</span></span>  
  
##  <a name="1b-create-an-mdx-query"></a><a name="MMDXQuery"></a><span data-ttu-id="95c3a-336">1b.</span><span class="sxs-lookup"><span data-stu-id="95c3a-336">1b.</span></span> <span data-ttu-id="95c3a-337">Создание запроса многомерных выражений</span><span class="sxs-lookup"><span data-stu-id="95c3a-337">Create an MDX Query</span></span>  
 <span data-ttu-id="95c3a-338">Далее создайте внедренный набор данных.</span><span class="sxs-lookup"><span data-stu-id="95c3a-338">Next, create an embedded dataset.</span></span> <span data-ttu-id="95c3a-339">Для этого используется конструктор запросов, позволяющий создать фильтры, параметры и вычисляемые элементы, а также сам набор данных.</span><span class="sxs-lookup"><span data-stu-id="95c3a-339">To do so, you will use the query designer to create filters, parameters, and calculated members as well as the dataset itself.</span></span>  
  
#### <a name="to-create-query-filters"></a><span data-ttu-id="95c3a-340">Создание фильтров запроса</span><span class="sxs-lookup"><span data-stu-id="95c3a-340">To create query filters</span></span>  
  
1.  <span data-ttu-id="95c3a-341">На странице **Проектирование запроса** на панели Метаданные в разделе Куб нажмите кнопку с многоточием **(...)**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-341">On the **Design a query** page, in the Metadata pane, in the cube section, click the ellipsis **(...)**.</span></span>  
  
2.  <span data-ttu-id="95c3a-342">В диалоговом окне **Выбор куба** выберите Sales и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-342">In the **Cube Selection** dialog box, click Sales, and then click **OK**.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="95c3a-343">Если вы не хотите создавать запрос многомерных выражений вручную, щелкните значок ![Перейти в режим конструктора](media/rsqdicon-designmode.gif "Перейти в режим конструктора"), переключите конструктор запросов в режим "Запрос", вставьте в конструктор законченное многомерное выражение и перейдите к шагу 5 раздела [Создание набора данных](#MSkip).</span><span class="sxs-lookup"><span data-stu-id="95c3a-343">If you do not want to build the MDX query manually, click the ![Switch to Design mode](media/rsqdicon-designmode.gif "Switch to Design mode") icon, toggle the query designer to Query mode, paste the completed MDX to the query designer, and then proceed to step 5 in [To create the dataset](#MSkip).</span></span>  
  
    ```  
    WITH MEMBER [Measures].[Net QTY] AS [Measures].[Sales Quantity] -[Measures].[Sales Return Quantity] MEMBER [Measures].[Net Sales] AS [Measures].[Sales Amount] - [Measures].[Sales Return Amount] SELECT NON EMPTY { [Measures].[Net QTY], [Measures].[Net Sales] } ON COLUMNS, NON EMPTY { ([Channel].[Channel Name].[Channel Name].ALLMEMBERS * [Product].[Product Category Name].[Product Category Name].ALLMEMBERS ) } DIMENSION PROPERTIES MEMBER_CAPTION, MEMBER_UNIQUE_NAME ON ROWS FROM ( SELECT ( { [Date].[Calendar Year].&[2009] } ) ON COLUMNS FROM ( SELECT ( STRTOSET(@ProductProductCategoryName, CONSTRAINED) ) ON COLUMNS FROM ( SELECT ( { [Sales Territory].[Sales Territory Group].&[North America] } ) ON COLUMNS FROM ( SELECT ( { [Channel].[Channel Name].&[2], [Channel].[Channel Name].&[4] } ) ON COLUMNS FROM [Sales])))) WHERE ( [Sales Territory].[Sales Territory Group].&[North America], [Date].[Calendar Year].&[2009] ) CELL PROPERTIES VALUE, BACK_COLOR, FORE_COLOR, FORMATTED_VALUE, FORMAT_STRING, FONT_NAME, FONT_SIZE, FONT_FLAGSQuery text: Code.  
    ```  
  
3.  <span data-ttu-id="95c3a-344">Разверните на панели "Группа мер" узел "Канал" и перетащите "Имя канала" в столбец **Иерархия** на панели фильтра.</span><span class="sxs-lookup"><span data-stu-id="95c3a-344">In the Measure Group pane, expand Channel, and then drag Channel Name to the **Hierarchy** column in the filter pane.</span></span>  
  
     <span data-ttu-id="95c3a-345">Имя размерности "Канал" автоматически добавляется в столбец **Размерность** .</span><span class="sxs-lookup"><span data-stu-id="95c3a-345">The dimension name, Channel, is automatically added to the **Dimension** column.</span></span> <span data-ttu-id="95c3a-346">Не меняйте значения в столбцах **Размерность** и **Оператор** .</span><span class="sxs-lookup"><span data-stu-id="95c3a-346">Do not change the **Dimension** or **Operator** columns.</span></span>  
  
4.  <span data-ttu-id="95c3a-347">Чтобы открыть список **Критерий фильтра** , щелкните стрелку вниз в столбце **Критерий фильтра** .</span><span class="sxs-lookup"><span data-stu-id="95c3a-347">To open the **Filter Expression** list, click the down arrow in the **Filter Expression** column.</span></span>  
  
5.  <span data-ttu-id="95c3a-348">В списке критериев фильтра разверните узел **Весь канал**, выберите **Online** и **Reseller**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-348">In the filter expression list, expand **All Channel**, click **Online** and **Reseller**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="95c3a-349">Теперь запрос содержит фильтр, включающий только эти каналы: Online и Reseller.</span><span class="sxs-lookup"><span data-stu-id="95c3a-349">The query now includes a filter to include only these channels: Online and Reseller.</span></span>  
  
6.  <span data-ttu-id="95c3a-350">Разверните измерение территория продаж, а затем перетащите группу территории продаж в столбец **Иерархия** под **именем канала**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-350">Expand the Sales Territory dimension, and then drag Sales Territory Group to the **Hierarchy** column, below **Channel Name**.</span></span>  
  
7.  <span data-ttu-id="95c3a-351">Откройте список **Критерий фильтра** , разверните узел **Территория продаж: все**, выберите элемент **Северная Америка**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-351">Open the **Filter Expression** list, expand **All Sales Territory**, click **North America**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="95c3a-352">Теперь запрос содержит фильтр, включающий только продажи в Северной Америке.</span><span class="sxs-lookup"><span data-stu-id="95c3a-352">The query now has a filter to include only sales in North America.</span></span>  
  
8.  <span data-ttu-id="95c3a-353">Разверните на панели "Группа мер" узел "Дата", а затем перетащите "Календарный год" в столбец **Иерархия** на панели фильтра.</span><span class="sxs-lookup"><span data-stu-id="95c3a-353">In the Measure Group pane, expand Date, and drag Calendar Year to the **Hierarchy** column in the filter pane.</span></span>  
  
     <span data-ttu-id="95c3a-354">Имя размерности "Дата" автоматически добавляется в столбец **Размерность** .</span><span class="sxs-lookup"><span data-stu-id="95c3a-354">The dimension name, Date, is automatically added to the **Dimension** column.</span></span> <span data-ttu-id="95c3a-355">Не меняйте значения в столбцах **Размерность** и **Оператор** .</span><span class="sxs-lookup"><span data-stu-id="95c3a-355">Do not change the **Dimension** or **Operator** columns.</span></span>  
  
9. <span data-ttu-id="95c3a-356">Чтобы открыть список **Критерий фильтра** , щелкните стрелку вниз в столбце **Критерий фильтра** .</span><span class="sxs-lookup"><span data-stu-id="95c3a-356">To open the **Filter Expression** list, click the down arrow in the **Filter Expression** column.</span></span>  
  
10. <span data-ttu-id="95c3a-357">В списке критериев фильтра разверните узел **Дата: все**, выберите элемент **Год 2009**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-357">In the filter expression list, expand **All Date**, click **Year 2009**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="95c3a-358">Теперь запрос содержит фильтр, включающий только 2009 календарный год.</span><span class="sxs-lookup"><span data-stu-id="95c3a-358">The query now includes a filter to include only the calendar year 2009.</span></span>  
  
#### <a name="to-create-the-parameter"></a><span data-ttu-id="95c3a-359">Создание параметра</span><span class="sxs-lookup"><span data-stu-id="95c3a-359">To create the parameter</span></span>  
  
1.  <span data-ttu-id="95c3a-360">Разверните размерность "Продукт", а затем перетащите элемент "Имя категории продуктов" в столбец **Иерархия** ниже элемента **Группа территорий продаж**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-360">Expand the Product dimension, and then drag the Product Category Name member to the **Hierarchy** column below **Sales Territory Group**.</span></span>  
  
2.  <span data-ttu-id="95c3a-361">Откройте список **Критерий фильтра** , выберите элемент **Все продукты**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-361">Open the **Filter Expression** list, click **All Products**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="95c3a-362">Установите флажок **Параметр** .</span><span class="sxs-lookup"><span data-stu-id="95c3a-362">Click the **Parameter** checkbox.</span></span> <span data-ttu-id="95c3a-363">Теперь запрос содержит параметр ProductProductCategoryName.</span><span class="sxs-lookup"><span data-stu-id="95c3a-363">The query now includes the parameter ProductProductCategoryName.</span></span>  
  
#### <a name="to-create-calculated-members"></a><span data-ttu-id="95c3a-364">Создание вычисляемых элементов</span><span class="sxs-lookup"><span data-stu-id="95c3a-364">To create calculated members</span></span>  
  
1.  <span data-ttu-id="95c3a-365">Переместите курсор на панель "Вычисляемые элементы", щелкните правой кнопкой мыши и выберите пункт **Создать вычисляемый элемент**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-365">Place the cursor inside the Calculated Members pane, right-click, and then click **New Calculated Member**.</span></span>  
  
2.  <span data-ttu-id="95c3a-366">На панели Метаданные разверните узел **меры** , а затем узел продажи.</span><span class="sxs-lookup"><span data-stu-id="95c3a-366">In the Metadata pane, expand **Measures** and then expand Sales.</span></span>  
  
3.  <span data-ttu-id="95c3a-367">Перетащите меру "Количество продаж" в поле **Выражение** , введите символ вычитания (-) и перетащите меру "Объем выручки от продаж" в поле **Выражение** , разместив его после символа вычитания.</span><span class="sxs-lookup"><span data-stu-id="95c3a-367">Drag the Sales Quantity measure to the **Expression** box, type the subtraction character (-), and then drag the Sales Return Quantity measure to the **Expression** box; place it after the subtraction character.</span></span>  
  
     <span data-ttu-id="95c3a-368">Следующий образец кода содержит выражение:</span><span class="sxs-lookup"><span data-stu-id="95c3a-368">The following code shows the expression:</span></span>  
  
    ```  
    [Measures].[Sales Quantity] - [Measures].[Sales Return Quantity]  
    ```  
  
4.  <span data-ttu-id="95c3a-369">В поле "Имя" введите **Чистый объем**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-369">In the Name box, type **Net QTY**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="95c3a-370">На панели "Вычисляемые элементы" отображается вычисляемый элемент **Чистый объем** .</span><span class="sxs-lookup"><span data-stu-id="95c3a-370">The Calculated Members pane lists the **Net QTY** calculated member.</span></span>  
  
5.  <span data-ttu-id="95c3a-371">Щелкните правой кнопкой мыши область **Вычисляемые элементы**и выберите пункт **Создать вычисляемый элемент**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-371">Right-click **Calculated Members**, and then click **New Calculated Member**.</span></span>  
  
6.  <span data-ttu-id="95c3a-372">На панели "Метаданные" разверните узел **Меры**, а затем узел "Продажи".</span><span class="sxs-lookup"><span data-stu-id="95c3a-372">In the Metadata pane, expand **Measures**, and then expand Sales.</span></span>  
  
7.  <span data-ttu-id="95c3a-373">Перетащите меру "Объем продаж" в поле **Выражение** , введите символ вычитания (-) и перетащите меру "Объем выручки от продаж" в поле **Выражение** , разместив ее после символа вычитания.</span><span class="sxs-lookup"><span data-stu-id="95c3a-373">Drag the Sales Amount measure to the **Expression** box, type the subtraction character (-), and then drag the Sales Return Amount measure to the **Expression** box; place it after the subtraction character.</span></span>  
  
     <span data-ttu-id="95c3a-374">Следующий образец кода содержит выражение:</span><span class="sxs-lookup"><span data-stu-id="95c3a-374">The following code shows the expression:</span></span>  
  
    ```  
    [Measures].[Sales Amount] - [Measures].[Sales Return Amount]  
    ```  
  
8.  <span data-ttu-id="95c3a-375">Введите в поле **Имя** строку  **Чистая сумма продаж**и нажмите кнопку **ОК**. На панели "Вычисляемые элементы" отображается вычисляемый элемент **Чистая сумма продаж** .</span><span class="sxs-lookup"><span data-stu-id="95c3a-375">In the **Name** box, type  **Net Sales**, and then click **OK**.The Calculated Members pane lists the **Net Sales** calculated member.</span></span>  
  
###  <a name="to-create-the-dataset"></a><a name="MSkip"></a><span data-ttu-id="95c3a-376">Создание набора данных</span><span class="sxs-lookup"><span data-stu-id="95c3a-376">To create the dataset</span></span>  
  
1.  <span data-ttu-id="95c3a-377">Из размерности "Канал" перетащите элемент "Имя канала" на панель данных.</span><span class="sxs-lookup"><span data-stu-id="95c3a-377">From the Channel dimension, drag Channel Name to the data pane.</span></span>  
  
2.  <span data-ttu-id="95c3a-378">Из размерности "Продукт" перетащите элемент "Имя категории продуктов" на панель данных, разместив его справа от элемента "Имя канала".</span><span class="sxs-lookup"><span data-stu-id="95c3a-378">From the Product dimension, drag Product Category Name to the data pane, and then place it to the right of Channel Name.</span></span>  
  
3.  <span data-ttu-id="95c3a-379">На панели **Вычисляемые элементы**перетащите элемент `Net QTY` в область данных и разместите его справа от элемента"Имя категории продуктов".</span><span class="sxs-lookup"><span data-stu-id="95c3a-379">From **Calculated Members**, drag `Net QTY` to the data pane, and then place it to the right of Product Category Name.</span></span>  
  
4.  <span data-ttu-id="95c3a-380">На панели "Вычисляемые элементы" перетащите элемент "Чистая выручка от продаж" в область данных и разместите его справа от элемента `Net QTY`.</span><span class="sxs-lookup"><span data-stu-id="95c3a-380">From Calculated Members, drag Net Sales to the data pane, and then place it to the right of `Net QTY`.</span></span>  
  
5.  <span data-ttu-id="95c3a-381">На панели инструментов конструктора запросов нажмите кнопку **выполнить (!)**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-381">On the query designer toolbar, click **Run (!)**.</span></span>  
  
     <span data-ttu-id="95c3a-382">Просмотрите результирующий набор запроса.</span><span class="sxs-lookup"><span data-stu-id="95c3a-382">Review the query result set.</span></span>  
  
6.  <span data-ttu-id="95c3a-383">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-383">Click **Next**.</span></span>  
  
##  <a name="1c-organize-data-into-groups"></a><a name="MLayout"></a><span data-ttu-id="95c3a-384">1C.</span><span class="sxs-lookup"><span data-stu-id="95c3a-384">1c.</span></span> <span data-ttu-id="95c3a-385">Упорядочение данных по группам</span><span class="sxs-lookup"><span data-stu-id="95c3a-385">Organize Data into Groups</span></span>  
 <span data-ttu-id="95c3a-386">При выборе полей для группирования данных создается матрица со строками и столбцами, отображающими подробные и агрегированные данные.</span><span class="sxs-lookup"><span data-stu-id="95c3a-386">When you select the fields on which to group data, you design a matrix with rows and columns that displays detail and aggregated data.</span></span>  
  
#### <a name="to-organize-data-into-groups"></a><span data-ttu-id="95c3a-387">Организация данных в группы</span><span class="sxs-lookup"><span data-stu-id="95c3a-387">To organize data into groups</span></span>  
  
1.  <span data-ttu-id="95c3a-388">На странице **Размещение полей** перетащите элемент Имя_категории_продуктов в область **Группы строк**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-388">On the **Arrange fields** page, drag Product_Category_Name to **Row groups**.</span></span>  
  
2.  <span data-ttu-id="95c3a-389">Перетащите элемент Имя_канала в область **Группы столбцов**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-389">Drag Channel_Name to **Column groups**.</span></span>  
  
3.  <span data-ttu-id="95c3a-390">Перетащите поле `Net_QTY` в область **Значения**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-390">Drag `Net_QTY` to **Values**.</span></span>  
  
     <span data-ttu-id="95c3a-391">`Net_QTY` автоматически вычисляется с помощью функции Sum, используемой по умолчанию для агрегирования числовых полей.</span><span class="sxs-lookup"><span data-stu-id="95c3a-391">`Net_QTY` is automatically aggregated by the Sum function, the default aggregate for numeric fields.</span></span> <span data-ttu-id="95c3a-392">Значение — `[Sum(Net_QTY)]`.</span><span class="sxs-lookup"><span data-stu-id="95c3a-392">The value is `[Sum(Net_QTY)]`.</span></span>  
  
     <span data-ttu-id="95c3a-393">Другие доступные агрегатные функции можно просмотреть в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="95c3a-393">To view the other aggregate functions available, open the drop-down list.</span></span> <span data-ttu-id="95c3a-394">Не изменяйте агрегатную функцию.</span><span class="sxs-lookup"><span data-stu-id="95c3a-394">Do not change the aggregate function.</span></span>  
  
4.  <span data-ttu-id="95c3a-395">Перетащите элемент `Net_Sales_Return` в область **Значения** и разместите его под элементом `[Sum(Net_QTY)]`.</span><span class="sxs-lookup"><span data-stu-id="95c3a-395">Drag `Net_Sales_Return` to **Values** and then place it below `[Sum(Net_QTY)]`.</span></span>  
  
     <span data-ttu-id="95c3a-396">Шаги 3 и 4 задают данные, отображаемые в матрице.</span><span class="sxs-lookup"><span data-stu-id="95c3a-396">Steps 3 and 4 specify the data to display in the matrix.</span></span>  
  
##  <a name="1d-add-subtotals-and-totals"></a><a name="MTotals"></a><span data-ttu-id="95c3a-397">1д.</span><span class="sxs-lookup"><span data-stu-id="95c3a-397">1d.</span></span> <span data-ttu-id="95c3a-398">Добавление подытогов и итогов</span><span class="sxs-lookup"><span data-stu-id="95c3a-398">Add Subtotals and Totals</span></span>  
 <span data-ttu-id="95c3a-399">В отчетах можно показывать подытоги и общие итоги.</span><span class="sxs-lookup"><span data-stu-id="95c3a-399">You can show subtotals and grand totals in reports.</span></span> <span data-ttu-id="95c3a-400">Данные в основном отчете отображаются в виде индикатора. По завершении мастера общий итог можно удалить.</span><span class="sxs-lookup"><span data-stu-id="95c3a-400">The data in the main report displays as an indicator; you will remove the grand total after you complete the wizard.</span></span>  
  
#### <a name="to-add-subtotals-and-grand-totals"></a><span data-ttu-id="95c3a-401">Добавление подытогов и общих итогов</span><span class="sxs-lookup"><span data-stu-id="95c3a-401">To add subtotals and grand totals</span></span>  
  
1.  <span data-ttu-id="95c3a-402">На странице **Выбор макета** в разделе **Параметры**убедитесь, что выбран параметр **Показывать подытоги и общие итоги** .</span><span class="sxs-lookup"><span data-stu-id="95c3a-402">On the **Choose the layout** page, under **Options**, verify that **Show subtotals and grand totals** is selected.</span></span>  
  
     <span data-ttu-id="95c3a-403">На панели просмотра в мастере отображается матрица с четырьмя строками.</span><span class="sxs-lookup"><span data-stu-id="95c3a-403">The wizard Preview pane displays a matrix with four rows.</span></span>  <span data-ttu-id="95c3a-404">При запуске отчета каждая строка отобразится следующим образом: первая строка представляет группу столбцов, вторая строка содержит заголовки столбцов, третья строка содержит данные категории продуктов (`[Sum(Net_ QTY)]` и `[Sum(Net_Sales)]`), а четвертая строка содержит итоговые значения.</span><span class="sxs-lookup"><span data-stu-id="95c3a-404">When you run the report, each row will display in the following way: The first row is the column group, the second row contains the column headings, the third row contains the product category data (`[Sum(Net_ QTY)]` and `[Sum(Net_Sales)]`, and the fourth row contains the totals.</span></span>  
  
2.  <span data-ttu-id="95c3a-405">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-405">Click **Next**.</span></span>  
  
##  <a name="1e-choose-a-style"></a><a name="MStyle"></a><span data-ttu-id="95c3a-406">1E.</span><span class="sxs-lookup"><span data-stu-id="95c3a-406">1e.</span></span> <span data-ttu-id="95c3a-407">Выбор стиля</span><span class="sxs-lookup"><span data-stu-id="95c3a-407">Choose a Style</span></span>  
 <span data-ttu-id="95c3a-408">Примените к отчету стиль «Сланец».</span><span class="sxs-lookup"><span data-stu-id="95c3a-408">Apply the Slate style to the report.</span></span> <span data-ttu-id="95c3a-409">Это тот же стиль, который используется в детализированном отчете.</span><span class="sxs-lookup"><span data-stu-id="95c3a-409">This is the same style that the drillthrough report uses.</span></span>  
  
#### <a name="to-specify-a-style"></a><span data-ttu-id="95c3a-410">Задание стиля</span><span class="sxs-lookup"><span data-stu-id="95c3a-410">To specify a style</span></span>  
  
1.  <span data-ttu-id="95c3a-411">На странице **Выбор стиля** на панели Стили выберите элемент содержание.</span><span class="sxs-lookup"><span data-stu-id="95c3a-411">On the **Choose a Style** page, in the Styles pane, select Slate.</span></span>  
  
2.  <span data-ttu-id="95c3a-412">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-412">Click **Finish**.</span></span>  
  
3.  <span data-ttu-id="95c3a-413">Нажмите кнопку **Выполнить**, чтобы выполнить предварительный просмотр отчета.</span><span class="sxs-lookup"><span data-stu-id="95c3a-413">To preview the report, click **Run**.</span></span>  
  
##  <a name="2-remove-the-grand-total-row"></a><a name="MGrandTotal"></a><span data-ttu-id="95c3a-414">2. Удаление строки общего итога</span><span class="sxs-lookup"><span data-stu-id="95c3a-414">2. Remove the Grand Total Row</span></span>  
 <span data-ttu-id="95c3a-415">Значения данных показаны в виде состояний индикатора, включая итоговые значения по группам столбцов.</span><span class="sxs-lookup"><span data-stu-id="95c3a-415">The data values are shown as indictor states, including the column group totals.</span></span> <span data-ttu-id="95c3a-416">Удалите строку, отображающую общий итог.</span><span class="sxs-lookup"><span data-stu-id="95c3a-416">Remove the row that displays the grand total.</span></span>  
  
#### <a name="to-remove-the-grand-total-row"></a><span data-ttu-id="95c3a-417">Удаление строки «Общий итог»</span><span class="sxs-lookup"><span data-stu-id="95c3a-417">To remove the grand total row</span></span>  
  
1.  <span data-ttu-id="95c3a-418">Щелкните **Конструктор**для переключения в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="95c3a-418">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="95c3a-419">Щелкните строку "Итого" (последнюю строку матрицы), щелкните ее еще раз правой кнопкой мыши, а затем выберите команду **Удалить строки**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-419">Click the Total row (the last row in the matrix), right-click, and then click **Delete Rows**.</span></span>  
  
3.  <span data-ttu-id="95c3a-420">Нажмите кнопку **Выполнить**, чтобы выполнить предварительный просмотр отчета.</span><span class="sxs-lookup"><span data-stu-id="95c3a-420">To preview the report, click **Run**.</span></span>  
  
##  <a name="3-configure-text-box-action-for-drillthrough"></a><a name="MDrillthrough"></a><span data-ttu-id="95c3a-421">3. действие "настроить текстовое поле" для детализации</span><span class="sxs-lookup"><span data-stu-id="95c3a-421">3. Configure Text Box Action for Drillthrough</span></span>  
 <span data-ttu-id="95c3a-422">Чтобы включить детализированный отчет, укажите действие для текстового поля основного отчета.</span><span class="sxs-lookup"><span data-stu-id="95c3a-422">To enable the drillthrough, specify an action on a text box in the main report.</span></span>  
  
#### <a name="to-enable-an-action"></a><span data-ttu-id="95c3a-423">Включение действия</span><span class="sxs-lookup"><span data-stu-id="95c3a-423">To enable an action</span></span>  
  
1.  <span data-ttu-id="95c3a-424">Щелкните **Конструктор**для переключения в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="95c3a-424">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="95c3a-425">Щелкните правой кнопкой мыши ячейку, содержащую Имя_категории_продуктов, а затем выберите пункт **Свойства текстового поля**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-425">Right-click the cell that contains Product_Category_Name, and then click **Text Box Properties**.</span></span>  
  
3.  <span data-ttu-id="95c3a-426">Перейдите на вкладку **Действие**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-426">Click the **Action** tab.</span></span>  
  
4.  <span data-ttu-id="95c3a-427">Выберите **Переход к отчету.**</span><span class="sxs-lookup"><span data-stu-id="95c3a-427">Select **Go to report.**</span></span>  
  
5.  <span data-ttu-id="95c3a-428">В поле **Выберите отчет**нажмите кнопку **Обзор**, чтобы найти местоположение детализированного отчета с именем ResellerVSOnlineDrillthrough.</span><span class="sxs-lookup"><span data-stu-id="95c3a-428">In **Specify a report**, click **Browse**, and then locate the drillthrough report named ResellerVSOnlineDrillthrough.</span></span>  
  
6.  <span data-ttu-id="95c3a-429">Чтобы добавить параметр для передачи детализированному отчету, нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-429">To add a parameter to run the drillthrough report, click **Add**.</span></span>  
  
7.  <span data-ttu-id="95c3a-430">В списке **Имя** выберите ProductProductCategoryName.</span><span class="sxs-lookup"><span data-stu-id="95c3a-430">In the **Name** list, select ProductProductCategoryName.</span></span>  
  
8.  <span data-ttu-id="95c3a-431">В разделе **Значение** введите `[Product_Category_Name.UniqueName]`.</span><span class="sxs-lookup"><span data-stu-id="95c3a-431">In **Value**, type `[Product_Category_Name.UniqueName]`.</span></span>  
  
     <span data-ttu-id="95c3a-432">Имя_категории_продуктов — это поле из набора данных.</span><span class="sxs-lookup"><span data-stu-id="95c3a-432">Product_Category_Name is a field in the dataset.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="95c3a-433">Необходимо включить свойство `UniqueName`, потому что действие детализации требует, чтобы значение было уникальным.</span><span class="sxs-lookup"><span data-stu-id="95c3a-433">You must include the `UniqueName` property because the drillthrough action requires a unique value.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-format-the-drillthrough-field"></a><span data-ttu-id="95c3a-434">Форматирование поля детализации</span><span class="sxs-lookup"><span data-stu-id="95c3a-434">To format the drillthrough field</span></span>  
  
1.  <span data-ttu-id="95c3a-435">Щелкните правой кнопкой мыши ячейку, содержащую `Product_Category_Name`, и выберите пункт **Свойства текстового поля**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-435">Right-click the cell that contains the `Product_Category_Name`, and then click **Text Box Properties**.</span></span>  
  
2.  <span data-ttu-id="95c3a-436">Перейдите на вкладку **Шрифт** .</span><span class="sxs-lookup"><span data-stu-id="95c3a-436">Click the **Font** tab.</span></span>  
  
3.  <span data-ttu-id="95c3a-437">В списке **Эффекты** выберите **Подчеркивание**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-437">In the **Effects** list, select **Underline**.</span></span>  
  
4.  <span data-ttu-id="95c3a-438">В списке **Цвет** выберите **Синий**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-438">In the **Color** list, select **Blue**.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="95c3a-439">Нажмите кнопку **Выполнить**для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="95c3a-439">To preview your report, click **Run**.</span></span>  
  
 <span data-ttu-id="95c3a-440">Имена категорий продуктов представлены в формате обычных ссылок (синие и подчеркнутые).</span><span class="sxs-lookup"><span data-stu-id="95c3a-440">The product category names are in the common link format (blue and underlined).</span></span>  
  
##  <a name="4-replace-numeric-values-with-indicators"></a><a name="MIndicators"></a><span data-ttu-id="95c3a-441">4. Замена числовых значений индикаторами</span><span class="sxs-lookup"><span data-stu-id="95c3a-441">4. Replace Numeric Values with Indicators</span></span>  
 <span data-ttu-id="95c3a-442">Используйте индикаторы для отображения состояния количеств и объемов продаж по каналам Online и Reseller.</span><span class="sxs-lookup"><span data-stu-id="95c3a-442">Use indicators to show the state of quantities and sales for Online and Reseller channels.</span></span>  
  
#### <a name="to-add-an-indicator-for-net-qty-values"></a><span data-ttu-id="95c3a-443">Добавление индикатора для значений «Чистый объем»</span><span class="sxs-lookup"><span data-stu-id="95c3a-443">To add an indicator for Net QTY values</span></span>  
  
1.  <span data-ttu-id="95c3a-444">Щелкните **Конструктор**для переключения в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="95c3a-444">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="95c3a-445">Щелкните на ленте значок **Прямоугольник** , а затем щелкните ячейку `[Sum(Net QTY)]` в группе строк `[Product_Category_Name]` в группе столбцов `Channel_Name` .</span><span class="sxs-lookup"><span data-stu-id="95c3a-445">On the ribbon, click the **Rectangle** icon, and then click in the `[Sum(Net QTY)]` cell in the `[Product_Category_Name]` row group in the `Channel_Name` column group.</span></span>  
  
3.  <span data-ttu-id="95c3a-446">Щелкните на ленте значок **Индикатор** , а затем щелкните внутри прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="95c3a-446">On the ribbon, click the **Indicator** icon, and then click inside the rectangle.</span></span> <span data-ttu-id="95c3a-447">Откроется диалоговое окно **Выбор стиля индикатора** с выбранным индикатором **Направленные** .</span><span class="sxs-lookup"><span data-stu-id="95c3a-447">The **Select Indicator Type** dialog box opens with the **Directional** indicator selected.</span></span>  
  
4.  <span data-ttu-id="95c3a-448">Выберите тип **3 знака** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-448">Click the **3 Signs** type, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="95c3a-449">Щелкните правой кнопкой мыши индикатор, а затем щелкните на панели "Данные датчика" стрелку вниз рядом с полем **(Не задано)**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-449">Right-click the indicator and in the Gauge Data pane, click the down arrow next to **(Unspecified)**.</span></span> <span data-ttu-id="95c3a-450">Выберите `Net_QTY`.</span><span class="sxs-lookup"><span data-stu-id="95c3a-450">Select `Net_QTY`.</span></span>  
  
6.  <span data-ttu-id="95c3a-451">Повторите шаги 2–5 для ячейки `[Sum(Net QTY)]` в группе строк `[Product_Category_Name]` области **Итого**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-451">Repeat steps 2 through 5 for the `[Sum(Net QTY)]` cell in the `[Product_Category_Name]` row group within **Total**.</span></span>  
  
#### <a name="to-add-an-indicator-for-net-sales-values"></a><span data-ttu-id="95c3a-452">Добавление индикатора для значений «Чистая выручка от продаж»</span><span class="sxs-lookup"><span data-stu-id="95c3a-452">To add an indicator for Net Sales values</span></span>  
  
1.  <span data-ttu-id="95c3a-453">Щелкните на ленте значок **Прямоугольник** , а затем щелкните ячейку `[Sum(Net_Sales)]` в группе строк `[Product_Category_Name]` в группе столбцов `Channel_Name` .</span><span class="sxs-lookup"><span data-stu-id="95c3a-453">On the ribbon, click the **Rectangle** icon, and then click inside the `[Sum(Net_Sales)]` cell in the `[Product_Category_Name]` row group in the `Channel_Name` column group.</span></span>  
  
2.  <span data-ttu-id="95c3a-454">Щелкните на ленте значок **Индикатор** , а затем щелкните внутри прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="95c3a-454">On the ribbon, click the **Indicator** icon, and then click inside the rectangle.</span></span>  
  
3.  <span data-ttu-id="95c3a-455">Выберите тип **3 знака** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-455">Click the **3 Signs** type, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="95c3a-456">Щелкните правой кнопкой мыши индикатор, а затем щелкните на панели "Данные датчика" стрелку вниз рядом с полем **(Не задано)**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-456">Right-click the indicator and in the Gauge Data pane, click the down arrow next to **(Unspecified)**.</span></span> <span data-ttu-id="95c3a-457">Выберите `Net_Sales`.</span><span class="sxs-lookup"><span data-stu-id="95c3a-457">Select `Net_Sales`.</span></span>  
  
5.  <span data-ttu-id="95c3a-458">Повторите шаги 1–4 для ячейки `[Sum(Net_Sales)]` в группе строк `[Product_Category_Name]` области **Итого**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-458">Repeat steps 1 through 4 for the `[Sum(Net_Sales)]` cell in the `[Product_Category_Name]` row group within **Total**.</span></span>  
  
6.  <span data-ttu-id="95c3a-459">Нажмите кнопку **Выполнить**для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="95c3a-459">To preview your report, click **Run**.</span></span>  
  
##  <a name="5-update-parameter-properties"></a><a name="MParameter"></a><span data-ttu-id="95c3a-460">5. свойства параметров обновления</span><span class="sxs-lookup"><span data-stu-id="95c3a-460">5. Update Parameter Properties</span></span>  
 <span data-ttu-id="95c3a-461">По умолчанию параметры видимы, но для данного отчета это неприемлемо.</span><span class="sxs-lookup"><span data-stu-id="95c3a-461">By default, parameters are visible, which is not appropriate for this report.</span></span> <span data-ttu-id="95c3a-462">Мы обновим свойства параметра, сделав его внутренним.</span><span class="sxs-lookup"><span data-stu-id="95c3a-462">You will update the parameter properties to make the parameter internal.</span></span>  
  
#### <a name="to-make-the-parameter-internal"></a><span data-ttu-id="95c3a-463">Превращение параметра во внутренний</span><span class="sxs-lookup"><span data-stu-id="95c3a-463">To make the parameter internal</span></span>  
  
1.  <span data-ttu-id="95c3a-464">В области данных отчета разверните узел **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-464">In the Report Data pane, expand **Parameters**.</span></span>  
  
2.  <span data-ttu-id="95c3a-465">Щелкните правой кнопкой мыши элемент `@ProductProductCategoryName,` и выберите пункт **Свойства параметра**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-465">Right-click `@ProductProductCategoryName,` and then click **Parameter Properties**.</span></span>  
  
3.  <span data-ttu-id="95c3a-466">На вкладке **Общие** установите флажок **Внутренний**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-466">On the **General** tab, click **Internal**.</span></span>  
  
4.  <span data-ttu-id="95c3a-467">По желанию можно открыть вкладки **Доступные значения** и **Значения по умолчанию** и просмотреть параметры, доступные на них.</span><span class="sxs-lookup"><span data-stu-id="95c3a-467">Optionally, click the **Available Values** and **Default Values** tabs and review their options.</span></span> <span data-ttu-id="95c3a-468">Не изменяйте параметры на этих вкладках.</span><span class="sxs-lookup"><span data-stu-id="95c3a-468">Do not change any options on these tabs.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="6-add-a-report-title"></a><a name="MTitle"></a><span data-ttu-id="95c3a-469">6. Добавление заголовка отчета</span><span class="sxs-lookup"><span data-stu-id="95c3a-469">6. Add a Report Title</span></span>  
 <span data-ttu-id="95c3a-470">Добавьте заголовок в основной отчет.</span><span class="sxs-lookup"><span data-stu-id="95c3a-470">Add a title to the main report.</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="95c3a-471">Добавление заголовка отчета</span><span class="sxs-lookup"><span data-stu-id="95c3a-471">To add a report title</span></span>  
  
1.  <span data-ttu-id="95c3a-472">В области конструктора щелкните ссылку **Щелкните, чтобы добавить заголовок**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-472">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="95c3a-473">Введите **Продажи по категориям продуктов за 2009 г.: категории Online и Reseller:**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-473">Type **2009 Product Category Sales: Online and Reseller Category:**.</span></span>  
  
3.  <span data-ttu-id="95c3a-474">Выберите набранный текст.</span><span class="sxs-lookup"><span data-stu-id="95c3a-474">Select the text you typed.</span></span>  
  
4.  <span data-ttu-id="95c3a-475">На вкладке **Главная** ленты в группе "Шрифт" выберите **Times New Roman** , размер **16 пунктов** , стили **Полужирный** и **Курсив** .</span><span class="sxs-lookup"><span data-stu-id="95c3a-475">On the **Home** tab of the ribbon, in the Font group, select the **Times New Roman** font, **16pt** size, and the **Bold** and **Italic** styles.</span></span>  
  
5.  <span data-ttu-id="95c3a-476">Нажмите кнопку **Выполнить**для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="95c3a-476">To preview your report, click **Run**.</span></span>  
  
##  <a name="7-save-the-main-report-to-a-sharepoint-library"></a><a name="MSave"></a><span data-ttu-id="95c3a-477">7. Сохранение основного отчета в библиотеке SharePoint</span><span class="sxs-lookup"><span data-stu-id="95c3a-477">7. Save the Main Report to a SharePoint Library</span></span>  
 <span data-ttu-id="95c3a-478">Сохраните основной отчет в библиотеке SharePoint.</span><span class="sxs-lookup"><span data-stu-id="95c3a-478">Save the main report to a SharePoint library.</span></span>  
  
#### <a name="to-save-the-report"></a><span data-ttu-id="95c3a-479">Сохранение отчета</span><span class="sxs-lookup"><span data-stu-id="95c3a-479">To save the report</span></span>  
  
1.  <span data-ttu-id="95c3a-480">Щелкните **Конструктор**для переключения в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="95c3a-480">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="95c3a-481">В построителе отчетов нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-481">From the Report Builder button, click **Save**.</span></span>  
  
3.  <span data-ttu-id="95c3a-482">Также можно щелкнуть ссылку **Последние сайты и серверы**, чтобы вывести список недавно использовавшихся серверов отчета и сайтов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="95c3a-482">Optionally, to show a list of recently used report servers and SharePoint sites, click **Recent Sites and Servers**.</span></span>  
  
4.  <span data-ttu-id="95c3a-483">Выберите или введите имя сайта SharePoint, на котором у вас имеется разрешение на сохранение отчетов.</span><span class="sxs-lookup"><span data-stu-id="95c3a-483">Select or type the name of the SharePoint site where you have permission to save reports.</span></span> <span data-ttu-id="95c3a-484">URL-адрес библиотеки SharePoint имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="95c3a-484">The URL of the SharePoint library has the following syntax:</span></span>  
  
    ```  
    Http://<ServerName>/<Sites>/  
    ```  
  
5.  <span data-ttu-id="95c3a-485">Перейдите к библиотеке, в которой необходимо сохранить отчет.</span><span class="sxs-lookup"><span data-stu-id="95c3a-485">Navigate to the library where you want to save the report.</span></span>  
  
6.  <span data-ttu-id="95c3a-486">В поле **Имя**замените имя по умолчанию на **ResellerVSOnlineMain**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-486">In **Name**, replace the default name with **ResellerVSOnlineMain**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="95c3a-487">Сохраните основной отчет в то же расположение, куда был сохранен детализированный отчет.</span><span class="sxs-lookup"><span data-stu-id="95c3a-487">Save the main report to the same location where you saved the drillthrough report.</span></span> <span data-ttu-id="95c3a-488">Чтобы сохранить основной и детализированный отчет на разных сайтах или в разных библиотеках, убедитесь в том, что в действии **Переход к отчету** основного отчета указано правильное расположение детализированного отчета.</span><span class="sxs-lookup"><span data-stu-id="95c3a-488">To save the main and drillthrough reports to different sites or libraries, confirm that the **Go to report** action in the main report, points to the correct location of the drillthrough report.</span></span>  
  
7.  <span data-ttu-id="95c3a-489">Выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="95c3a-489">Click **Save**.</span></span>  
  
##  <a name="8-run-the-main-and-drillthrough-reports"></a><a name="MRunReports"></a><span data-ttu-id="95c3a-490">8. Запуск основного и детализированного отчетов</span><span class="sxs-lookup"><span data-stu-id="95c3a-490">8. Run the Main and Drillthrough Reports</span></span>  
 <span data-ttu-id="95c3a-491">Запустите основной отчет и попробуйте щелкнуть значения в столбце категорий продуктов для запуска детализированного отчета.</span><span class="sxs-lookup"><span data-stu-id="95c3a-491">Run the main report, and then click values in the product category column to run the drillthrough report.</span></span>  
  
#### <a name="to-run-the-reports"></a><span data-ttu-id="95c3a-492">Запуск отчетов</span><span class="sxs-lookup"><span data-stu-id="95c3a-492">To run the reports</span></span>  
  
1.  <span data-ttu-id="95c3a-493">Откройте библиотеку SharePoint, в которой сохранены отчеты.</span><span class="sxs-lookup"><span data-stu-id="95c3a-493">Open the SharePoint library where the reports are saved.</span></span>  
  
2.  <span data-ttu-id="95c3a-494">Дважды щелкните ResellerVSOnlineMain.</span><span class="sxs-lookup"><span data-stu-id="95c3a-494">Double-click ResellerVSOnlineMain.</span></span>  
  
     <span data-ttu-id="95c3a-495">Отчет запускается и отображает сведения о продажах по категориям продуктов.</span><span class="sxs-lookup"><span data-stu-id="95c3a-495">The report runs and displays product category sales information.</span></span>  
  
3.  <span data-ttu-id="95c3a-496">Щелкните ссылку **Игры и игрушки** в столбце, который содержит имена категорий продуктов.</span><span class="sxs-lookup"><span data-stu-id="95c3a-496">Click the **Games and Toys** link in the column that contains product category names.</span></span>  
  
     <span data-ttu-id="95c3a-497">При этом запускается детализированный отчет, отображающий только значения категории продуктов «Игры и игрушки».</span><span class="sxs-lookup"><span data-stu-id="95c3a-497">The drillthrough report runs, displaying only the values for the Games and Toys product category.</span></span>  
  
4.  <span data-ttu-id="95c3a-498">Чтобы вернуться в основной отчет, нажмите кнопку «Назад» Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="95c3a-498">To return to the main report, click the Internet Explorer back button.</span></span>  
  
5.  <span data-ttu-id="95c3a-499">При необходимости просмотрите другие категории продуктов, щелкая их имена.</span><span class="sxs-lookup"><span data-stu-id="95c3a-499">Optionally, explore other product categories by clicking their names.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95c3a-500">См. также:</span><span class="sxs-lookup"><span data-stu-id="95c3a-500">See Also</span></span>  
 [<span data-ttu-id="95c3a-501">Учебники &#40;построитель отчетов&#41;</span><span class="sxs-lookup"><span data-stu-id="95c3a-501">Tutorials &#40;Report Builder&#41;</span></span>](report-builder-tutorials.md)  
  
  
