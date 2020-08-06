---
title: Занятие 2. Изменение свойств источника данных отчета | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c962b0ff-ce8a-4742-8262-dc730901afcf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 05e56a58ce28ee1e1e450d3af012cbd1ffe668ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656239"
---
# <a name="lesson-2-modifying-the-report-data-source-properties"></a><span data-ttu-id="fc6b6-102">Lesson 2: Modifying the Report Data Source Properties</span><span class="sxs-lookup"><span data-stu-id="fc6b6-102">Lesson 2: Modifying the Report Data Source Properties</span></span>
  <span data-ttu-id="fc6b6-103">На этом занятии с помощью диспетчера отчетов будет выбираться отчет, который необходимо доставить получателям.</span><span class="sxs-lookup"><span data-stu-id="fc6b6-103">In this lesson, you will use Report Manager to select a report that will be delivered to recipients.</span></span> <span data-ttu-id="fc6b6-104">Управляемая данными подписка, которую вы создадите, будет распространять отчет **Заказ на продажу** , созданный при работе с учебником [Создание простого табличного отчета (учебник по службам SSRS)](../reporting-services/create-a-basic-table-report-ssrs-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="fc6b6-104">The data-driven subscription that you will define will distribute the **Sales Order** report created in the tutorial [Create a Basic Table Report &#40;SSRS Tutorial&#41;](../reporting-services/create-a-basic-table-report-ssrs-tutorial.md).</span></span> <span data-ttu-id="fc6b6-105">В последующих шагах будут изменены сведения о соединении с источником данных, используемые в отчете для получения данных.</span><span class="sxs-lookup"><span data-stu-id="fc6b6-105">In the steps that follow, you will modify the data source connection information used by the report to get data.</span></span> <span data-ttu-id="fc6b6-106">Только отчеты, использующие **сохраненные учетные данные** для доступа к источнику данных для отчета, могут распространяться с помощью управляемой данными подписки.</span><span class="sxs-lookup"><span data-stu-id="fc6b6-106">Only reports that use **stored credentials** to access a report data source can be distributed through a data-driven subscription.</span></span> <span data-ttu-id="fc6b6-107">Сохраненные учетные данные нужны для автоматической обработки отчета.</span><span class="sxs-lookup"><span data-stu-id="fc6b6-107">Stored credentials are necessary for unattended report processing.</span></span>

 <span data-ttu-id="fc6b6-108">Вы также измените набор данных и отчет, включив в них параметр для фильтрации отчета по `[Order]` , с тем чтобы подписка могла выдавать разные экземпляры отчета для определенных заказов и форматов подготовки к просмотру.</span><span class="sxs-lookup"><span data-stu-id="fc6b6-108">You will also modify the dataset and report to use a parameter to filter the report on the `[Order]` so the subscription can output different instances of the report for specific orders and rendering formats.</span></span>

 <span data-ttu-id="fc6b6-109">**В этом разделе:**</span><span class="sxs-lookup"><span data-stu-id="fc6b6-109">**In this topic:**</span></span>

-   [<span data-ttu-id="fc6b6-110">Изменение свойств источника данных</span><span class="sxs-lookup"><span data-stu-id="fc6b6-110">To Modify the Data Source Properties</span></span>](#bkmk_modify_datasource)

-   [<span data-ttu-id="fc6b6-111">Изменение набора данных AdventureWorksDataset</span><span class="sxs-lookup"><span data-stu-id="fc6b6-111">To Modify the AdventureWorksDataset</span></span>](#bkmk_modify_dataset)

-   [<span data-ttu-id="fc6b6-112">Добавление параметра отчета и повторная публикация отчета</span><span class="sxs-lookup"><span data-stu-id="fc6b6-112">To Add a Report Parameter and Republish the Report</span></span>](#bkmk_add_reportparameter)

-   [<span data-ttu-id="fc6b6-113">Повторное развертывание отчета</span><span class="sxs-lookup"><span data-stu-id="fc6b6-113">To Re-deploy the Report</span></span>](#bkmk_redeploy)

##  <a name="to-modify-the-data-source-properties"></a><a name="bkmk_modify_datasource"></a><span data-ttu-id="fc6b6-114">Изменение свойств источника данных</span><span class="sxs-lookup"><span data-stu-id="fc6b6-114">To Modify the Data Source Properties</span></span>

1.  <span data-ttu-id="fc6b6-115">Запустите [диспетчер отчетов &#40;служб SSRS в собственном режиме&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) с правами администратора, например щелкните правой кнопкой мыши значок Internet Explorer и выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="fc6b6-115">Start [Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) with administrator privileges, for example, right-click the icon for Internet Explorer and click **Run as administrator**.</span></span>

2.  <span data-ttu-id="fc6b6-116">Перейдите в папку с отчетом **Sales Orders** и в контекстном меню отчета щелкните пункт **Управление**.</span><span class="sxs-lookup"><span data-stu-id="fc6b6-116">Browse to the folder containing the **Sales Orders** report and in the context menu of the report, click **Manage**.</span></span>

     <span data-ttu-id="fc6b6-117">![Откройте контекстное меню отчета и выберите «Управление»](../../2014/tutorials/media/ssrs-tutorial-datadriven-manage-report.gif "Откройте контекстное меню отчета и выберите «Управление»")</span><span class="sxs-lookup"><span data-stu-id="fc6b6-117">![Open the report context menu and select manage](../../2014/tutorials/media/ssrs-tutorial-datadriven-manage-report.gif "Open the report context menu and select manage")</span></span>

3.  <span data-ttu-id="fc6b6-118">Перейдите на вкладку **Источники данных** .</span><span class="sxs-lookup"><span data-stu-id="fc6b6-118">Click the **Data Sources** tab.</span></span>

4.  <span data-ttu-id="fc6b6-119">В поле **Тип соединения**укажите **Microsoft SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="fc6b6-119">For **Connection Type**, select **Microsoft SQL Server**.</span></span>

5.  <span data-ttu-id="fc6b6-120">Будет использоваться следующая строка подключения к пользовательскому источнику данных (предполагается, что образец базы данных находится на локальном сервере баз данных):</span><span class="sxs-lookup"><span data-stu-id="fc6b6-120">The custom data source connection string will be the following and it assumes that the sample database is on a local database server:</span></span>

    ```
    Data source=localhost; initial catalog=AdventureWorks2012
    ```

6.  <span data-ttu-id="fc6b6-121">Щелкните **Учетные данные, которые безопасно хранятся на сервере отчетов**.</span><span class="sxs-lookup"><span data-stu-id="fc6b6-121">Click **Credentials stored securely in the report server**.</span></span>

7.  <span data-ttu-id="fc6b6-122">Введите имя пользователя (в формате *домен\имя*) и пароль.</span><span class="sxs-lookup"><span data-stu-id="fc6b6-122">Type your user name (use the format *domain\user*) and password.</span></span> <span data-ttu-id="fc6b6-123">Воспользуйтесь именем входа, у которого есть разрешение на доступ к базе данных [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fc6b6-123">If you do not have permission to access the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database, specify a login that does.</span></span>

8.  <span data-ttu-id="fc6b6-124">Установите флажок **Использовать учетные данные Windows при соединение с источником данных**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fc6b6-124">Click **Use as windows credentials when connecting to the data source**, and then click **OK**.</span></span> <span data-ttu-id="fc6b6-125">Если учетная запись домена не используется (например, используется учетная запись [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ), не устанавливайте этот флажок.</span><span class="sxs-lookup"><span data-stu-id="fc6b6-125">If you are not using a domain account (for example, if you are using a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login), do not click this checkbox.</span></span>

9. <span data-ttu-id="fc6b6-126">Нажмите кнопку **Проверить соединение** , чтобы проверить соединение с источником данных.</span><span class="sxs-lookup"><span data-stu-id="fc6b6-126">Click **Test Connection** to verify you can connect to the data source.</span></span>

10. <span data-ttu-id="fc6b6-127">Щелкните **Применить**.</span><span class="sxs-lookup"><span data-stu-id="fc6b6-127">Click **Apply**.</span></span>

11. <span data-ttu-id="fc6b6-128">Просмотрите отчет, чтобы убедиться, что он выполняется с указанными учетными данными.</span><span class="sxs-lookup"><span data-stu-id="fc6b6-128">View the report to verify that the report runs with the credentials you specified.</span></span> <span data-ttu-id="fc6b6-129">Чтобы просмотреть отчет, перейдите на вкладку **вид** . Обратите внимание, что после открытия отчета необходимо выбрать имя сотрудника, а затем нажать кнопку **Просмотреть отчет** , чтобы просмотреть отчет.</span><span class="sxs-lookup"><span data-stu-id="fc6b6-129">To view the report, click the **View** tab. Note that once the report is open, you must select an Employee name and then click the **View Report** button to view the report.</span></span>

##  <a name="to-modify-the-adventureworksdataset"></a><a name="bkmk_modify_dataset"></a><span data-ttu-id="fc6b6-130">Изменение AdventureWorksDataset</span><span class="sxs-lookup"><span data-stu-id="fc6b6-130">To Modify the AdventureWorksDataset</span></span>

1.  <span data-ttu-id="fc6b6-131">Откройте отчет Sales Orders в среде [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc6b6-131">Open the Sales Orders report in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]</span></span>

2.  <span data-ttu-id="fc6b6-132">Щелкните правой кнопкой мыши набор данных `AdventureWorksDataset` и выберите пункт **Свойства набора данных**.</span><span class="sxs-lookup"><span data-stu-id="fc6b6-132">Right-click the dataset `AdventureWorksDataset` and click **Dataset Properties**.</span></span>

3.  <span data-ttu-id="fc6b6-133">Добавьте инструкцию `WHERE (UPPER(SalesOrderNumber) =UPPER(@OrderNumber) or  @OrderNumber IS NULL)` перед инструкцией `Group By` .</span><span class="sxs-lookup"><span data-stu-id="fc6b6-133">Add the statement `WHERE (UPPER(SalesOrderNumber) =UPPER(@OrderNumber) or  @OrderNumber IS NULL)` before the `Group By` statement.</span></span> <span data-ttu-id="fc6b6-134">Полный синтаксис запроса:</span><span class="sxs-lookup"><span data-stu-id="fc6b6-134">The full query syntax is the following:</span></span>

    ```
    SELECT soh.OrderDate AS Date, soh.SalesOrderNumber AS [Order], pps.Name AS Subcat, pp.Name AS Product, SUM(sd.OrderQty) AS Qty, SUM(sd.LineTotal)  AS LineTotal
    FROM Sales.SalesPerson AS sp INNER JOIN
      Sales.SalesOrderHeader AS soh ON sp.BusinessEntityID = soh.SalesPersonID INNER JOIN
       Sales.SalesOrderDetail AS sd ON sd.SalesOrderID = soh.SalesOrderID INNER JOIN
       Production.Product AS pp ON sd.ProductID = pp.ProductID
    INNER JOIN
       Production.ProductSubcategory AS pps ON pp.ProductSubcategoryID = pps.ProductSubcategoryID 
    INNER JOIN
        Production.ProductCategory AS ppc ON ppc.ProductCategoryID = pps.ProductCategoryID

    WHERE (UPPER(SalesOrderNumber) =UPPER(@OrderNumber) or  @OrderNumber IS NULL)

    GROUP BY ppc.Name, soh.OrderDate, soh.SalesOrderNumber, pps.Name, pp.Name, soh.SalesPersonID
    HAVING (ppc.Name = 'Clothing')
    ```

4.  <span data-ttu-id="fc6b6-135">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fc6b6-135">Click **OK**</span></span>

##  <a name="to-add-a-report-parameter-and-republish-the-report"></a><a name="bkmk_add_reportparameter"></a><span data-ttu-id="fc6b6-136">Добавление параметра отчета и повторная публикация отчета</span><span class="sxs-lookup"><span data-stu-id="fc6b6-136">To Add a Report Parameter and Republish the Report</span></span>

1.  <span data-ttu-id="fc6b6-137">В области **Данные отчета** нажмите кнопку **Создать** и выберите **Параметр...**.</span><span class="sxs-lookup"><span data-stu-id="fc6b6-137">In the **Report Data** pane click **New** and then click **Parameter...**</span></span>

2.  <span data-ttu-id="fc6b6-138">В поле **Имя**введите `OrderNumber`.</span><span class="sxs-lookup"><span data-stu-id="fc6b6-138">In **Name**, type `OrderNumber`.</span></span>

3.  <span data-ttu-id="fc6b6-139">В поле **Подсказка**введите `OrderNumber`.</span><span class="sxs-lookup"><span data-stu-id="fc6b6-139">In **Prompt**, type `OrderNumber`.</span></span>

4.  <span data-ttu-id="fc6b6-140">Выберите **Разрешить пустое значение ("")**.</span><span class="sxs-lookup"><span data-stu-id="fc6b6-140">Select **Allow blank value ("")**.</span></span>

5.  <span data-ttu-id="fc6b6-141">Выберите **Разрешить значение NULL**.</span><span class="sxs-lookup"><span data-stu-id="fc6b6-141">Select **Allow null value**.</span></span>

6.  <span data-ttu-id="fc6b6-142">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fc6b6-142">Click **OK**.</span></span> <span data-ttu-id="fc6b6-143">Параметр будет добавлен в область **Данные отчета** и будет выглядеть, как на следующем изображении:</span><span class="sxs-lookup"><span data-stu-id="fc6b6-143">The parameter will be added to the **Report Data pane** and it will look like the following image:</span></span>

     <span data-ttu-id="fc6b6-144">![Новый параметр добавляется на панель «Данные отчета»](../../2014/tutorials/media/ssrs-tutorial-datadriven-parameter.gif "Новый параметр добавляется на панель «Данные отчета»")</span><span class="sxs-lookup"><span data-stu-id="fc6b6-144">![The new parameter is added to the Report Data pane](../../2014/tutorials/media/ssrs-tutorial-datadriven-parameter.gif "The new parameter is added to the Report Data pane")</span></span>

7.  <span data-ttu-id="fc6b6-145">Перейдите на вкладку **Просмотр** , чтобы запустить отчет. Обратите внимание на поле ввода параметра вверху отчета.</span><span class="sxs-lookup"><span data-stu-id="fc6b6-145">Click the **Preview** tab to run the report.Note the parameter input box at the top of the report.</span></span> <span data-ttu-id="fc6b6-146">Вы можете сделать одно из двух:</span><span class="sxs-lookup"><span data-stu-id="fc6b6-146">You can either:</span></span>

    -   <span data-ttu-id="fc6b6-147">щелкнуть «Просмотр отчета», чтобы отобразить весь отчет без использования параметра;</span><span class="sxs-lookup"><span data-stu-id="fc6b6-147">Click View Report to see the full report without using a parameter.</span></span>

    -   <span data-ttu-id="fc6b6-148">снять выбор параметра NULL и ввести номер заказа, например so71949, чтобы просмотреть в отчете только один заказ.</span><span class="sxs-lookup"><span data-stu-id="fc6b6-148">Unselect the Null option and type an order number, for example so71949 to view only the one order in the report.</span></span>

         <span data-ttu-id="fc6b6-149">![Средство просмотра отчетов с отображаемой областью параметров](../../2014/tutorials/media/ssrs-tutorial-datadriven-reportviewer-parameter.gif "Средство просмотра отчетов с отображаемой областью параметров")</span><span class="sxs-lookup"><span data-stu-id="fc6b6-149">![Report viewer with parameter area visible](../../2014/tutorials/media/ssrs-tutorial-datadriven-reportviewer-parameter.gif "Report viewer with parameter area visible")</span></span>

8.  <span data-ttu-id="fc6b6-150">Повторно разверните отчет, с тем чтобы конфигурация подписки, которая будет создана на следующем занятии, могла использовать изменения, внесенные на этом занятии.</span><span class="sxs-lookup"><span data-stu-id="fc6b6-150">Re-deploy the report so the subscription configuration in the next lesson can utilize the changes you made in this lesson.</span></span> <span data-ttu-id="fc6b6-151">Дополнительные сведения о свойствах проекта, используемых в учебнике по таблицам, см. в разделе "Публикация отчета на сервере отчетов (необязательно)" [занятия 6. Добавление группирования и итогов &#40;Reporting Services&#41;](../reporting-services/lesson-6-adding-grouping-and-totals-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="fc6b6-151">For more information on the project properties used in the table tutorial, see section 'To Publish the Report to the Report Server (Optional)' of [Lesson 6: Adding Grouping and Totals &#40;Reporting Services&#41;](../reporting-services/lesson-6-adding-grouping-and-totals-reporting-services.md).</span></span>

##  <a name="to-re-deploy-the-report"></a><a name="bkmk_redeploy"></a><span data-ttu-id="fc6b6-152">Повторное развертывание отчета</span><span class="sxs-lookup"><span data-stu-id="fc6b6-152">To Re-deploy the Report</span></span>

1.  <span data-ttu-id="fc6b6-153">Повторно разверните отчет, с тем чтобы конфигурация подписки, которая будет создана на следующем занятии, могла использовать изменения, внесенные на этом занятии.</span><span class="sxs-lookup"><span data-stu-id="fc6b6-153">Re-deploy the report so the subscription configuration in the next lesson can utilize the changes you made in this lesson.</span></span> <span data-ttu-id="fc6b6-154">Дополнительные сведения о свойствах проекта, используемых в учебнике по таблицам, см. в разделе "Публикация отчета на сервере отчетов (необязательно)" [занятия 6. Добавление группирования и итогов &#40;Reporting Services&#41;](../reporting-services/lesson-6-adding-grouping-and-totals-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="fc6b6-154">For more information on the project properties used in the table tutorial, see section 'To Publish the Report to the Report Server (Optional)' of [Lesson 6: Adding Grouping and Totals &#40;Reporting Services&#41;](../reporting-services/lesson-6-adding-grouping-and-totals-reporting-services.md).</span></span>

2.  <span data-ttu-id="fc6b6-155">На панели инструментов щелкните **Построить** , а затем ― **Развернуть учебник**.</span><span class="sxs-lookup"><span data-stu-id="fc6b6-155">On the toolbar click **Build** and then click **Deploy tutorial**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fc6b6-156">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="fc6b6-156">Next Steps</span></span>
 <span data-ttu-id="fc6b6-157">Отчет настроен для получения данных с применением сохраненных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="fc6b6-157">You successfully configured the report to get data using stored credentials.</span></span> <span data-ttu-id="fc6b6-158">Далее предстоит определить подписку с помощью страниц управляемых данными подписок в диспетчере отчетов.</span><span class="sxs-lookup"><span data-stu-id="fc6b6-158">Next, you specify the subscription using the Data-Driven Subscription pages in Report Manager.</span></span> <span data-ttu-id="fc6b6-159">См. [Занятие 3. Определение управляемой данными подписки](../reporting-services/lesson-3-defining-a-data-driven-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="fc6b6-159">See [Lesson 3: Defining a Data-Driven Subscription](../reporting-services/lesson-3-defining-a-data-driven-subscription.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fc6b6-160">См. также</span><span class="sxs-lookup"><span data-stu-id="fc6b6-160">See Also</span></span>
 <span data-ttu-id="fc6b6-161">[Управление источниками данных отчета](report-data/manage-report-data-sources.md) [Указание учетных данных и сведений о соединении для источников данных отчета](report-data/specify-credential-and-connection-information-for-report-data-sources.md) [создание управляемой данными подписки &#40;SSRS руководство&#41;](../reporting-services/create-a-data-driven-subscription-ssrs-tutorial.md) [Создание простого табличного отчета &#40;руководстве по службам SSRS&#41;](../reporting-services/create-a-basic-table-report-ssrs-tutorial.md)</span><span class="sxs-lookup"><span data-stu-id="fc6b6-161">[Manage Report Data Sources](report-data/manage-report-data-sources.md) [Specify Credential and Connection Information for Report Data Sources](report-data/specify-credential-and-connection-information-for-report-data-sources.md) [Create a Data-Driven Subscription &#40;SSRS Tutorial&#41;](../reporting-services/create-a-data-driven-subscription-ssrs-tutorial.md) [Create a Basic Table Report &#40;SSRS Tutorial&#41;](../reporting-services/create-a-basic-table-report-ssrs-tutorial.md)</span></span>


