---
title: Учебник. Общие сведения о выражениях | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2d05ef4c-5f91-48b2-8795-f0a201a0b3cc
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 62a815800dba0730052eb812124d4561d031d0e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737796"
---
# <a name="tutorial-introducing-expressions"></a><span data-ttu-id="e8dae-102">Учебник. Общие сведения о выражениях</span><span class="sxs-lookup"><span data-stu-id="e8dae-102">Tutorial: Introducing Expressions</span></span>
  <span data-ttu-id="e8dae-103">Выражения позволяют создавать мощные и гибкие отчеты.</span><span class="sxs-lookup"><span data-stu-id="e8dae-103">Expressions help you create powerful and flexible reports.</span></span> <span data-ttu-id="e8dae-104">С помощью этого учебника вы научитесь создавать и реализовывать выражения с часто используемыми функциями и операторами.</span><span class="sxs-lookup"><span data-stu-id="e8dae-104">This tutorial teaches you to create and implement expressions that use common functions and operators.</span></span> <span data-ttu-id="e8dae-105">Диалоговое окно **выражение** используется для написания выражений, объединяющих значения имени, поиска значений в отдельном наборе данных, отображения различных изображений на основе значений полей и т. д.</span><span class="sxs-lookup"><span data-stu-id="e8dae-105">You will use the **Expression** dialog box to write expressions that concatenate name values, look up values in a separate dataset, display different pictures based on field values, and so on.</span></span>  
  
 <span data-ttu-id="e8dae-106">Это отчет, в котором чередуются строки белого и другого цвета.</span><span class="sxs-lookup"><span data-stu-id="e8dae-106">The report is a barred report with alternating row colors in white and a color.</span></span> <span data-ttu-id="e8dae-107">В отчет включен параметр для выбора цвета строк, отличных от белых.</span><span class="sxs-lookup"><span data-stu-id="e8dae-107">The report includes a parameter for selecting the color of the non-white rows.</span></span>  
  
 <span data-ttu-id="e8dae-108">На приведенном далее рисунке показан отчет, похожий на тот, который будет в итоге создан.</span><span class="sxs-lookup"><span data-stu-id="e8dae-108">The following illustration shows a report similar to the one you will create.</span></span>  
  
 <span data-ttu-id="e8dae-109">![rs_ExpressionsTutorial](../../2014/tutorials/media/rs-expressionstutorial.gif "rs_ExpressionsTutorial")</span><span class="sxs-lookup"><span data-stu-id="e8dae-109">![rs_ExpressionsTutorial](../../2014/tutorials/media/rs-expressionstutorial.gif "rs_ExpressionsTutorial")</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="e8dae-110">Что вы узнаете</span><span class="sxs-lookup"><span data-stu-id="e8dae-110">What You Will Learn</span></span>  
 <span data-ttu-id="e8dae-111">В этом учебнике рассматриваются следующие темы:</span><span class="sxs-lookup"><span data-stu-id="e8dae-111">In this tutorial you will learn how to do the following:</span></span>  
  
1.  [<span data-ttu-id="e8dae-112">Создание табличного отчета и набора данных с помощью мастера таблицы или матрицы</span><span class="sxs-lookup"><span data-stu-id="e8dae-112">Create a Table Report and Dataset from the Table or Matrix Wizard</span></span>](#Setup)  
  
2.  [<span data-ttu-id="e8dae-113">Обновление имен по умолчанию для источника и набора данных</span><span class="sxs-lookup"><span data-stu-id="e8dae-113">Update Default Names of the Data Source and Dataset</span></span>](#UpdateNames)  
  
3.  [<span data-ttu-id="e8dae-114">Отображение фамилии, имени и инициала отчества</span><span class="sxs-lookup"><span data-stu-id="e8dae-114">Display First Name, Initial, and Last Name</span></span>](#Concatenate)  
  
4.  [<span data-ttu-id="e8dae-115">Отображение пола с помощью изображений</span><span class="sxs-lookup"><span data-stu-id="e8dae-115">Use Images to Display Gender</span></span>](#Gender)  
  
5.  [<span data-ttu-id="e8dae-116">Поиск имени в таблице CountryRegion</span><span class="sxs-lookup"><span data-stu-id="e8dae-116">Look Up CountryRegion Name</span></span>](#Lookup)  
  
6.  [<span data-ttu-id="e8dae-117">Подсчет дней с последней покупки</span><span class="sxs-lookup"><span data-stu-id="e8dae-117">Count Days Since Last Purchase</span></span>](#Count)  
  
7.  [<span data-ttu-id="e8dae-118">Отображение сравнения цен с помощью индикатора</span><span class="sxs-lookup"><span data-stu-id="e8dae-118">Use an Indicator to Show Sales Comparison</span></span>](#Indicator)  
  
8.  [<span data-ttu-id="e8dae-119">Создание отчета с «зеленым» отчетом</span><span class="sxs-lookup"><span data-stu-id="e8dae-119">Make the Report a "Green Bar" Report</span></span>](#GreenBar)  
  
### <a name="other-optional-steps"></a><span data-ttu-id="e8dae-120">Другие дополнительные шаги</span><span class="sxs-lookup"><span data-stu-id="e8dae-120">Other Optional Steps</span></span>  
  
-   [<span data-ttu-id="e8dae-121">Форматирование столбца даты</span><span class="sxs-lookup"><span data-stu-id="e8dae-121">Format Date Column</span></span>](#DateFormat)  
  
-   [<span data-ttu-id="e8dae-122">Добавление заголовка отчета</span><span class="sxs-lookup"><span data-stu-id="e8dae-122">Add a Report Title</span></span>](#Title)  
  
-   [<span data-ttu-id="e8dae-123">Сохранение отчета</span><span class="sxs-lookup"><span data-stu-id="e8dae-123">Save the Report</span></span>](#Save)  
  
 <span data-ttu-id="e8dae-124">Предполагаемое время для выполнения заданий данного учебника: 30 минут.</span><span class="sxs-lookup"><span data-stu-id="e8dae-124">Estimated time to complete this tutorial: 30 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8dae-125">Требования</span><span class="sxs-lookup"><span data-stu-id="e8dae-125">Requirements</span></span>  
 <span data-ttu-id="e8dae-126">Дополнительные сведения о требованиях см. в разделе [Предварительные условия для использования учебников (построитель отчетов)](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="e8dae-126">For information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-table-report-and-dataset-from-the-table-or-matrix-wizard"></a><a name="Setup"></a><span data-ttu-id="e8dae-127">1. Создание табличного отчета и набора данных с помощью мастера таблицы или матрицы</span><span class="sxs-lookup"><span data-stu-id="e8dae-127">1. Create a Table Report and Dataset from the Table or Matrix Wizard</span></span>  
 <span data-ttu-id="e8dae-128">Создайте табличный отчет, источник данных и набор данных.</span><span class="sxs-lookup"><span data-stu-id="e8dae-128">Create a table report, a data source, and a dataset.</span></span> <span data-ttu-id="e8dae-129">При создании макета таблицы будут включены лишь несколько полей.</span><span class="sxs-lookup"><span data-stu-id="e8dae-129">When you lay out the table, you will include only a few fields.</span></span> <span data-ttu-id="e8dae-130">После завершения работы мастера добавьте столбцы вручную.</span><span class="sxs-lookup"><span data-stu-id="e8dae-130">After you complete the wizard you will manually add columns.</span></span> <span data-ttu-id="e8dae-131">Мастер дает возможность легко разместить в отчете таблицу и применить стиль.</span><span class="sxs-lookup"><span data-stu-id="e8dae-131">The wizard makes it easy for you to lay out the table and apply a style.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e8dae-132">В этом учебнике запрос уже содержит значения данных, поэтому внешний источник данных не требуется.</span><span class="sxs-lookup"><span data-stu-id="e8dae-132">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="e8dae-133">В связи с этим запрос получается весьма длинным.</span><span class="sxs-lookup"><span data-stu-id="e8dae-133">This makes the query quite long.</span></span> <span data-ttu-id="e8dae-134">В рабочей среде запрос не будет содержать данные.</span><span class="sxs-lookup"><span data-stu-id="e8dae-134">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="e8dae-135">Этот запрос содержит данные только в учебных целях.</span><span class="sxs-lookup"><span data-stu-id="e8dae-135">This is for learning purposes only.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e8dae-136">В этом учебнике шаги работы с мастером объединены в одну процедуру.</span><span class="sxs-lookup"><span data-stu-id="e8dae-136">In this tutorial, the steps for the wizard are consolidated into one procedure.</span></span> <span data-ttu-id="e8dae-137">Пошаговые инструкции по переходу к серверу отчетов, выбору источника данных и созданию набора данных см. в первом учебнике этой серии: [Учебник. Создание простого табличного отчета &#40;построитель отчетов&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="e8dae-137">For step-by-step instructions about how to browse to a report server, choose a data source, and create a dataset, see the first tutorial in this series: [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
#### <a name="to-create-a-new-table-report"></a><span data-ttu-id="e8dae-138">Создание нового табличного отчета</span><span class="sxs-lookup"><span data-stu-id="e8dae-138">To create a new table report</span></span>  
  
1.  <span data-ttu-id="e8dae-139">Нажмите кнопку **Пуск**, укажите пункт **программы**, выберите пункт [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Построитель отчетов**и щелкните **Построитель отчетов**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-139">Click **Start**, point to **Programs**, click [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)]**Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="e8dae-140">Откроется диалоговое окно **Начало работы** .</span><span class="sxs-lookup"><span data-stu-id="e8dae-140">The **Getting Started** dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e8dae-141">Если диалоговое окно **Начало работы** не отображается, на кнопке **Построитель отчетов** нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-141">If the **Getting Started** dialog box does not appear, from the **Report Builder** button, click **New**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e8dae-142">Если вы предпочитаете использовать версию ClickOnce построитель отчетов, откройте диспетчер отчетов и нажмите кнопку " **Построитель отчетов**" или перейдите на сайт SharePoint, на котором Reporting Services типы содержимого, такие как отчеты, и щелкните **Построитель отчетов отчет** в меню " **создать документ** " на вкладке " **документы** " библиотеки общих документов.</span><span class="sxs-lookup"><span data-stu-id="e8dae-142">If you prefer using the ClickOnce version of Report Builder, open Report Manager and click **Report Builder**, or go to a SharePoint site on which Reporting Services content types such as reports are enabled and click **Report Builder Report** on the **New Document** menu on the **Documents** tab of a shared documents library.</span></span>  
  
2.  <span data-ttu-id="e8dae-143">Убедитесь, что на левой панели выбран **Новый отчет** .</span><span class="sxs-lookup"><span data-stu-id="e8dae-143">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="e8dae-144">На панели справа выберите **Мастер таблицы или матрицы**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-144">In the right pane, click **Table or Matrix Wizard**.</span></span>  
  
4.  <span data-ttu-id="e8dae-145">На странице **Выбор набора данных** выберите **Создать набор данных**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-145">On the **Choose a dataset** page, click **Create a dataset**.</span></span>  
  
5.  <span data-ttu-id="e8dae-146">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-146">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="e8dae-147">На странице **Выбор соединения с источником данных** выберите источник данных, имеющий тип **SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-147">On the **Choose a connection to a data source** page, select a data source that is type **SQL Server**.</span></span> <span data-ttu-id="e8dae-148">Выберите источник данных из списка или перейдите на сервер отчетов, чтобы выбрать его там.</span><span class="sxs-lookup"><span data-stu-id="e8dae-148">Select a data source from the list or browse to the report server to select one.</span></span>  
  
7.  <span data-ttu-id="e8dae-149">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-149">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="e8dae-150">На странице **Проектирование запроса** нажмите кнопку **Изменить как текст**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-150">On the **Design a query** page, click **Edit as Text**.</span></span>  
  
9. <span data-ttu-id="e8dae-151">На панель запроса вставьте следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="e8dae-151">Paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT 'Lauren' AS FirstName,'Johnson' AS LastName, 'American Samoa' AS StateProvince, 1 AS CountryRegionID,'Unknown' AS Gender, CAST(9996.60 AS money) AS YTDPurchase, CAST('2010-6-10' AS date) AS LastPurchase  
    UNION SELECT'Warren' AS FirstName, 'Pal' AS LastName, 'New South Wales' AS StateProvince, 2 AS CountryRegionID, 'Male' AS Gender, CAST(5747.25 AS money) AS YTDPurchase, CAST('2010-7-3' AS date) AS LastPurchase  
    UNION SELECT 'Fernando' AS FirstName, 'Ross' AS LastName, 'Alberta' AS StateProvince, 3 AS CountryRegionID, 'Male' AS Gender, CAST(9248.15 AS money) AS YTDPurchase, CAST('2010-10-17' AS date) AS LastPurchase  
    UNION SELECT 'Rob' AS FirstName, 'Caron' AS LastName, 'Northwest Territories' AS StateProvince, 3 AS CountryRegionID, 'Male' AS Gender, CAST(742.50 AS money) AS YTDPurchase, CAST('2010-4-29' AS date) AS LastPurchase  
    UNION SELECT 'James' AS FirstName, 'Bailey' AS LastName, 'British Columbia' AS StateProvince, 3 AS CountryRegionID, 'Male' AS Gender, CAST(1147.50 AS money) AS YTDPurchase, CAST('2010-6-15' AS date) AS LastPurchase  
    UNION SELECT  'Bridget' AS FirstName, 'She' AS LastName, 'Hamburg' AS StateProvince, 4 AS CountryRegionID, 'Female' AS Gender, CAST(7497.30 AS money) AS YTDPurchase, CAST('2010-5-10' AS date) AS LastPurchase  
    UNION SELECT 'Alexander' AS FirstName, 'Martin' AS LastName, 'Saxony' AS StateProvince, 4 AS CountryRegionID, 'Male' AS Gender, CAST(2997.60 AS money) AS YTDPurchase, CAST('2010-11-19' AS date) AS LastPurchase  
    UNION SELECT 'Yolanda' AS FirstName, 'Sharma' AS LastName ,'Micronesia' AS StateProvince, 5 AS CountryRegionID, 'Female' AS Gender, CAST(3247.95 AS money) AS YTDPurchase, CAST('2010-8-23' AS date) AS LastPurchase  
    UNION SELECT 'Marc' AS FirstName, 'Zimmerman' AS LastName, 'Moselle' AS StateProvince, 6 AS CountryRegionID, 'Male' AS Gender, CAST(1200.00 AS money) AS YTDPurchase, CAST('2010-11-16' AS date) AS LastPurchase  
    UNION SELECT 'Katherine' AS FirstName, 'Abel' AS LastName, 'Moselle' AS StateProvince, 6 AS CountryRegionID, 'Female' AS Gender, CAST(2025.00 AS money) AS YTDPurchase, CAST('2010-12-1' AS date) AS LastPurchase  
    UNION SELECT 'Nicolas' as FirstName, 'Anand' AS LastName, 'Seine (Paris)' AS StateProvince, 6 AS CountryRegionID, 'Male' AS Gender, CAST(1425.00 AS money) AS YTDPurchase, CAST('2010-12-11' AS date) AS LastPurchase  
    UNION SELECT 'James' AS FirstName, 'Peters' AS LastName, 'England' AS StateProvince, 12 AS CountryRegionID, 'Male' AS Gender, CAST(887.50 AS money) AS YTDPurchase, CAST('2010-8-15' AS date) AS LastPurchase  
    UNION SELECT 'Alison' AS FirstName, 'Nath' AS LastName, 'Alaska' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(607.50 AS money) AS YTDPurchase, CAST('2010-10-13' AS date) AS LastPurchase  
    UNION SELECT 'Grace' AS FirstName, 'Patterson' AS LastName, 'Kansas' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(1215.00 AS money) AS YTDPurchase, CAST('2010-10-18' AS date) AS LastPurchase  
    UNION SELECT 'Bobby' AS FirstName, 'Sanchez' AS LastName, 'North Dakota' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(6191.00 AS money) AS YTDPurchase, CAST('2010-9-17' AS date) AS LastPurchase  
    UNION SELECT 'Charles' AS FirstName, 'Reed' AS LastName, 'Nebraska' AS StateProvince, 7 AS CountryRegionID, 'Male' AS Gender, CAST(8772.00 AS money) AS YTDPurchase, CAST('2010-8-27' AS date) AS LastPurchase  
    UNION SELECT 'Orlando' AS FirstName, 'Romeo' AS LastName, 'Texas' AS StateProvince, 7 AS CountryRegionID, 'Male' AS Gender, CAST(8578.00 AS money) AS YTDPurchase, CAST('2010-7-29' AS date) AS LastPurchase  
    UNION SELECT 'Cynthia' AS FirstName, 'Randall' AS LastName, 'Utah' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(7218.10 AS money) AS YTDPurchase, CAST('2010-1-11' AS date) AS LastPurchase  
    UNION SELECT 'Rebecca' AS FirstName, 'Roberts' AS LastName, 'Washington' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(8357.80 AS money) AS YTDPurchase, CAST('2010-10-28' AS date) AS LastPurchase  
    UNION SELECT 'Cristian' AS FirstName, 'Petulescu' AS LastName, 'Wisconsin' AS StateProvince, 7 AS CountryRegionID, 'Male' AS Gender, CAST(3470.00 AS money) AS YTDPurchase, CAST('2010-11-30' AS date) AS LastPurchase  
    UNION SELECT 'Cynthia' AS FirstName, 'Randall' AS LastName, 'Utah' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(7218.10 AS money) AS YTDPurchase, CAST('2010-1-11' AS date) AS LastPurchase  
    UNION SELECT 'Rebecca' AS FirstName, 'Roberts' AS LastName, 'Washington' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(8357.80 AS money) AS YTDPurchase, CAST('2010-10-28' AS date) AS LastPurchase  
    UNION SELECT 'Cristian' AS FirstName, 'Petulescu' AS LastName, 'Wisconsin' AS StateProvince, 7 AS CountryRegionID, 'Male' AS Gender, CAST(3470.00 AS money) AS YTDPurchase, CAST('2010-11-30' AS date) AS LastPurchase  
    ```  
  
     <span data-ttu-id="e8dae-152">В запросе указываются имена таких столбцов, как дата рождения, фамилия, имя, область или республика, идентификатор страны или региона, пол и число покупок за последний год.</span><span class="sxs-lookup"><span data-stu-id="e8dae-152">The query specifies column names that include a birth date, first name, last name, state or province, country/region identifier, gender, and year-to-date purchases.</span></span>  
  
10. <span data-ttu-id="e8dae-153">На панели инструментов конструктора запросов нажмите кнопку **выполнить** (**!**).</span><span class="sxs-lookup"><span data-stu-id="e8dae-153">On the query designer toolbar, click **Run** (**!**).</span></span> <span data-ttu-id="e8dae-154">В результирующем наборе будет 20 строк данных, включающих следующие столбцы: FirstName, LastName, StateProvince, CountryRegionID, Gender, YTDPurchase и LastPurchase.</span><span class="sxs-lookup"><span data-stu-id="e8dae-154">The result set displays 20 rows of data and includes the following columns: FirstName, LastName, StateProvince, CountryRegionID, Gender, YTDPurchase, and LastPurchase.</span></span>  
  
11. <span data-ttu-id="e8dae-155">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-155">Click **Next**.</span></span>  
  
12. <span data-ttu-id="e8dae-156">На странице **Размещение полей** перетащите следующие поля в указанном порядке из списка **Доступные поля** в список **Значения** .</span><span class="sxs-lookup"><span data-stu-id="e8dae-156">On the **Arrange fields** page, drag the following fields, in the specified order, from the **Available Fields** list to the **Values** list.</span></span>  
  
    -   <span data-ttu-id="e8dae-157">StateProvince</span><span class="sxs-lookup"><span data-stu-id="e8dae-157">StateProvince</span></span>  
  
    -   <span data-ttu-id="e8dae-158">CountryRegionID</span><span class="sxs-lookup"><span data-stu-id="e8dae-158">CountryRegionID</span></span>  
  
    -   <span data-ttu-id="e8dae-159">LastPurchase</span><span class="sxs-lookup"><span data-stu-id="e8dae-159">LastPurchase</span></span>  
  
    -   <span data-ttu-id="e8dae-160">YTDPurchase</span><span class="sxs-lookup"><span data-stu-id="e8dae-160">YTDPurchase</span></span>  
  
     <span data-ttu-id="e8dae-161">Поскольку столбцы CountryRegionID и YTDPurchase содержат числовые данные, по умолчанию к ним применяется статистическое выражение SUM.</span><span class="sxs-lookup"><span data-stu-id="e8dae-161">Because the CountryRegionID and YTDPurchase contain numeric data, the SUM aggregate is applied to them by default.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e8dae-162">Поля FirstName и LastName не включаются.</span><span class="sxs-lookup"><span data-stu-id="e8dae-162">The FirstName and LastName fields are not included.</span></span> <span data-ttu-id="e8dae-163">Их нужно будет добавить позже.</span><span class="sxs-lookup"><span data-stu-id="e8dae-163">You will add them in a later step.</span></span>  
  
13. <span data-ttu-id="e8dae-164">В списке **значения** щелкните правой кнопкой мыши `CountryRegionID` и выберите параметр **Sum** .</span><span class="sxs-lookup"><span data-stu-id="e8dae-164">In the **Values** list, right-click `CountryRegionID` and click the **Sum** option.</span></span>  
  
     <span data-ttu-id="e8dae-165">Суммирование больше не применяется к полю CountryRegionID.</span><span class="sxs-lookup"><span data-stu-id="e8dae-165">Sum is no longer applied to CountryRegionID.</span></span>  
  
14. <span data-ttu-id="e8dae-166">В списке **Значения** щелкните правой кнопкой мыши **YTDPurchase** и выберите пункт **Сумма** .</span><span class="sxs-lookup"><span data-stu-id="e8dae-166">In the **Values** list, right-click **YTDPurchase** and click the **Sum** option.</span></span>  
  
     <span data-ttu-id="e8dae-167">Суммирование больше не применяется к полю YTDPurchase.</span><span class="sxs-lookup"><span data-stu-id="e8dae-167">Sum is no longer applied to YTDPurchase.</span></span>  
  
15. <span data-ttu-id="e8dae-168">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-168">Click **Next**.</span></span>  
  
16. <span data-ttu-id="e8dae-169">На странице **Выбор макета** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-169">On the **Choose the layout** page, click **Next**.</span></span>  
  
17. <span data-ttu-id="e8dae-170">На странице **Выбор стиля** щелкните элемент **содержание**и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-170">On the **Choose a style** page, click **Slate**, and then click **Finish**.</span></span>  
  
##  <a name="2-update-default-names-of-the-data-source-and-dataset"></a><a name="UpdateNames"></a><span data-ttu-id="e8dae-171">2. обновление имен по умолчанию для источника данных и набора данных</span><span class="sxs-lookup"><span data-stu-id="e8dae-171">2. Update Default Names of the Data Source and Dataset</span></span>  
  
#### <a name="to-update-the-default-name-of-the-data-source"></a><span data-ttu-id="e8dae-172">Изменение имени источника данных по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e8dae-172">To update the default name of the data source</span></span>  
  
1.  <span data-ttu-id="e8dae-173">В области данных отчета разверните узел **Источники данных**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-173">In the Report Data pane, expand **Data Sources**.</span></span>  
  
2.  <span data-ttu-id="e8dae-174">Щелкните правой кнопкой мыши пункт **DataSource1** и выберите пункт **Свойства источника данных**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-174">Right-click **DataSource1** and click **Data Source Properties.**</span></span>  
  
3.  <span data-ttu-id="e8dae-175">В поле **Имя** введите **ExpressionsDataSource**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-175">In the **Name** box, type **ExpressionsDataSource**</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-update-the-default-name-of-the-dataset"></a><span data-ttu-id="e8dae-176">Изменение имени набора данных по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e8dae-176">To update the default name of the dataset</span></span>  
  
1.  <span data-ttu-id="e8dae-177">В области данных отчета разверните узел **Наборы данных**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-177">In the Report Data pane, expand **Datasets**.</span></span>  
  
2.  <span data-ttu-id="e8dae-178">Щелкните правой кнопкой мыши пункт **DataSet1** и выберите пункт **Свойства набора данных**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-178">Right-click **DataSet1** and click **Dataset Properties.**</span></span>  
  
3.  <span data-ttu-id="e8dae-179">В поле **Имя** введите **Expressions**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-179">In the **Name** box, type **Expressions**</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="3-display-first-name-initial-and-last-name"></a><a name="Concatenate"></a><span data-ttu-id="e8dae-180">3. Отображение имени, начального и последнего имени</span><span class="sxs-lookup"><span data-stu-id="e8dae-180">3. Display First Name, Initial, and Last Name</span></span>  
 <span data-ttu-id="e8dae-181">Укажите в выражении функцию **Left** и оператор **Concatenate** (**&**) для вычисления имени, состоящего из фамилии и инициала отчества.</span><span class="sxs-lookup"><span data-stu-id="e8dae-181">Use the **Left** function and the **Concatenate** (**&**) operator in an expression that evaluates to a name that includes an initial and a last name.</span></span> <span data-ttu-id="e8dae-182">Можно построить выражение в пошаговом режиме либо пропустить процедуру, а затем скопировать и вставить выражение из учебника в диалоговом окне **Выражение** .</span><span class="sxs-lookup"><span data-stu-id="e8dae-182">You can build the expression step by step or skip ahead in the procedure and copy/paste the expression from the tutorial into the **Expression** dialog box.</span></span>  
  
#### <a name="to-add-the-name-column"></a><span data-ttu-id="e8dae-183">Добавление столбца Name</span><span class="sxs-lookup"><span data-stu-id="e8dae-183">To add the Name column</span></span>  
  
1.  <span data-ttu-id="e8dae-184">Щелкните правой кнопкой мыши столбец **StateProvince** , наведите указатель на пункт **Вставить столбец**, а затем выберите пункт **Слева**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-184">Right-click the **StateProvince** column, point to **Insert Column**, and then click **Left**.</span></span>  
  
     <span data-ttu-id="e8dae-185">Новый столбец будет добавлен слева от столбца **StateProvince** .</span><span class="sxs-lookup"><span data-stu-id="e8dae-185">A new column is added to the left of the **StateProvince** column.</span></span>  
  
2.  <span data-ttu-id="e8dae-186">Щелкните заголовок нового столбца и введите **Name**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-186">Click the title of the new column and type **Name**</span></span>  
  
3.  <span data-ttu-id="e8dae-187">Щелкните правой кнопкой мыши ячейку данных для столбца **Name** и выберите пункт **Выражение**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-187">Right-click the data cell for the **Name** column and click **Expression**.</span></span>  
  
4.  <span data-ttu-id="e8dae-188">В диалоговом окне **Выражение** разверните узел **Общие функции**и выберите **Текст**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-188">In the **Expression** dialog box, expand **Common Functions**, and then click **Text**.</span></span>  
  
5.  <span data-ttu-id="e8dae-189">В списке **Элемент** дважды щелкните **Left**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-189">In the **Item** list, double-click **Left**.</span></span>  
  
     <span data-ttu-id="e8dae-190">В выражение будет добавлена функция **Left** .</span><span class="sxs-lookup"><span data-stu-id="e8dae-190">The **Left** function is added to the expression.</span></span>  
  
6.  <span data-ttu-id="e8dae-191">В списке **Категория** щелкните **Поля (выражения)**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-191">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
7.  <span data-ttu-id="e8dae-192">В списке **Значения** дважды щелкните **FirstName**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-192">In the **Values** list, double-click **FirstName**.</span></span>  
  
8.  <span data-ttu-id="e8dae-193">Введите **, 1)**</span><span class="sxs-lookup"><span data-stu-id="e8dae-193">Type **, 1)**</span></span>  
  
     <span data-ttu-id="e8dae-194">Это выражение извлекает один символ из значения **FirstName** , считая слева.</span><span class="sxs-lookup"><span data-stu-id="e8dae-194">This expression extracts one character from the **FirstName** value, counting from the left.</span></span>  
  
9. <span data-ttu-id="e8dae-195">Введите **&" "&**</span><span class="sxs-lookup"><span data-stu-id="e8dae-195">Type **&" "&**</span></span>  
  
10. <span data-ttu-id="e8dae-196">В списке **Значения** дважды щелкните **LastName**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-196">In the **Values** list, double-click **LastName**.</span></span>  
  
     <span data-ttu-id="e8dae-197">Готовое выражение: `=Left(Fields!FirstName.Value, 1) &" "& Fields!LastName.Value`</span><span class="sxs-lookup"><span data-stu-id="e8dae-197">The completed expression: `=Left(Fields!FirstName.Value, 1) &" "& Fields!LastName.Value`</span></span>  
  
11. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
12. <span data-ttu-id="e8dae-198">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="e8dae-198">Click **Run** to preview the report.</span></span>  
  
##  <a name="4-use-images-to-display-gender"></a><a name="Gender"></a><span data-ttu-id="e8dae-199">4. Использование изображений для вывода пола</span><span class="sxs-lookup"><span data-stu-id="e8dae-199">4. Use Images to Display Gender</span></span>  
 <span data-ttu-id="e8dae-200">Пол можно показать с помощью изображений, обозначив неизвестный пол третьим изображением.</span><span class="sxs-lookup"><span data-stu-id="e8dae-200">Use images to show the gender of a person, and identify unknown gender values by using a third image.</span></span> <span data-ttu-id="e8dae-201">Добавим в отчет три скрытых изображения в новом столбце, а затем определим изображение, которое будет отображаться в столбце исходя из значения поля Gender.</span><span class="sxs-lookup"><span data-stu-id="e8dae-201">You will add to the report three hidden images and a new column to display the images, and then determine the image that appears in the column based on the value of the Gender field.</span></span>  
  
 <span data-ttu-id="e8dae-202">Чтобы применить цвет к ячейке таблицы, содержащей изображение, когда создается отчет с чередованием цвета строк, нужно добавить прямоугольник и добавить изображение в него.</span><span class="sxs-lookup"><span data-stu-id="e8dae-202">To apply a color to the table cell that contains the image when you make the report a barred report, you will add a rectangle and then add the image to the rectangle.</span></span> <span data-ttu-id="e8dae-203">Использование прямоугольника обусловлено тем, что фоновый цвет можно применить к прямоугольнику, а не к изображению.</span><span class="sxs-lookup"><span data-stu-id="e8dae-203">You need to use a rectangle because you can apply a background color to a rectangle, but not to an image.</span></span>  
  
 <span data-ttu-id="e8dae-204">В учебнике используются изображения, устанавливаемые в составе Windows, однако можно использовать и любые другие доступные изображения.</span><span class="sxs-lookup"><span data-stu-id="e8dae-204">The tutorial uses images that are installed with Windows, but you can use any images available to you.</span></span> <span data-ttu-id="e8dae-205">Внедренные изображения, которые мы будем использовать, не нужно устанавливать на локальном компьютере или сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="e8dae-205">You will use embedded images, and they do not need to be installed on your local computer or the report server.</span></span>  
  
#### <a name="to-add-images-to-the-report-body"></a><span data-ttu-id="e8dae-206">Добавление изображений в текст отчета</span><span class="sxs-lookup"><span data-stu-id="e8dae-206">To add images to the report body</span></span>  
  
1.  <span data-ttu-id="e8dae-207">Щелкните **Конструктор** для возврата в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="e8dae-207">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="e8dae-208">На вкладке ленты **Вставка** щелкните **Изображение**, а затем текст отчета ниже таблицы.</span><span class="sxs-lookup"><span data-stu-id="e8dae-208">On the **Insert** tab of the ribbon, click **Image** and then click in the report body, below the table.</span></span>  
  
     <span data-ttu-id="e8dae-209">Откроется диалоговое окно **Свойства изображения**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-209">The **Image Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="e8dae-210">Щелкните **Импорт** и перейдите в папку C:\Пользователи\Общие\Общие изображения\Образцы изображений.</span><span class="sxs-lookup"><span data-stu-id="e8dae-210">Click **Import** and navigate to C:\Users\Public\Public Pictures\Sample Pictures.</span></span>  
  
4.  <span data-ttu-id="e8dae-211">Щелкните файл Penguins.JPG, а затем нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-211">Click Penguins.JPG and click **Open**.</span></span>  
  
     <span data-ttu-id="e8dae-212">В диалоговом окне **Свойства изображения** щелкните **Видимость**, а затем выберите параметр **Скрыть**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-212">In the **Image Properties** dialog box, click **Visibility** and then click the **Hide** option.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="e8dae-213">Повторите шаги с 2 по 5, выбрав файл Koala.JPG.</span><span class="sxs-lookup"><span data-stu-id="e8dae-213">Repeat steps 2 through 5, but choose Koala.JPG.</span></span>  
  
7.  <span data-ttu-id="e8dae-214">Повторите шаги с 2 по 5, выбрав Tulips.JPG.</span><span class="sxs-lookup"><span data-stu-id="e8dae-214">Repeat steps 2 through 5, but choose Tulips.JPG.</span></span>  
  
#### <a name="to-add-the-gender-column"></a><span data-ttu-id="e8dae-215">Добавление столбца Gender</span><span class="sxs-lookup"><span data-stu-id="e8dae-215">To add the Gender column</span></span>  
  
1.  <span data-ttu-id="e8dae-216">Щелкните правой кнопкой мыши столбец **Name**, наведите указатель на пункт **Вставить столбец**, а затем выберите пункт **Справа**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-216">Right-click the **Name** column, point to **Insert Column**, and then click **Right**.</span></span>  
  
     <span data-ttu-id="e8dae-217">Новый столбец будет добавлен справа от столбца **Name**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-217">A new column is added to the right of the **Name** column.</span></span>  
  
2.  <span data-ttu-id="e8dae-218">Щелкните название нового столбца и введите **Gender**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-218">Click the title of the new column and type **Gender**</span></span>  
  
#### <a name="to-add-a-rectangle"></a><span data-ttu-id="e8dae-219">Добавление прямоугольника</span><span class="sxs-lookup"><span data-stu-id="e8dae-219">To add a rectangle</span></span>  
  
-   <span data-ttu-id="e8dae-220">На вкладке ленты **Вставка** щелкните **Прямоугольник**, а затем щелкните ячейку данных в столбце **Gender**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-220">On the **Insert** tab of the ribbon, click **Rectangle** and then click in the data cell of the **Gender** column.</span></span>  
  
     <span data-ttu-id="e8dae-221">В ячейку будет добавлен прямоугольник.</span><span class="sxs-lookup"><span data-stu-id="e8dae-221">A rectangle is added to the cell.</span></span>  
  
#### <a name="to-add-an-image-to-the-rectangle"></a><span data-ttu-id="e8dae-222">Добавление изображения в прямоугольник</span><span class="sxs-lookup"><span data-stu-id="e8dae-222">To add an image to the rectangle</span></span>  
  
1.  <span data-ttu-id="e8dae-223">Щелкните прямоугольник правой кнопкой мыши, наведите указатель на пункт **Вставить** и выберите пункт **Изображение**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-223">Right-click in the rectangle, point to **Insert**, and then click **Image**.</span></span>  
  
2.  <span data-ttu-id="e8dae-224">В диалоговом окне **Свойства изображения** щелкните стрелку вниз рядом с параметром **Использовать это изображение**, а затем выберите одно из добавленных изображений, например Penguins.JPG.</span><span class="sxs-lookup"><span data-stu-id="e8dae-224">In the **Image Properties** dialog box, click the down arrow beside **Use this image**, and select one of the images you added, for example, Penguins.JPG.</span></span>  
  
3.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-use-images-to-show-gender"></a><span data-ttu-id="e8dae-225">Отображение пола с помощью изображений</span><span class="sxs-lookup"><span data-stu-id="e8dae-225">To use images to show gender</span></span>  
  
1.  <span data-ttu-id="e8dae-226">Щелкните правой кнопкой мыши изображение в ячейке данных в столбце **Gender** и выберите пункт **Свойства изображения**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-226">Right-click the image in the data cell in the **Gender** column and click **Image Properties**.</span></span>  
  
2.  <span data-ttu-id="e8dae-227">В диалоговом окне **Свойства изображения** нажмите кнопку выражения **fx** рядом с текстовым полем **Использовать это изображение**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-227">In the **Image Properties** dialog box, click the expression **fx** button next to the **Use this image** text box.</span></span>  
  
3.  <span data-ttu-id="e8dae-228">В диалоговом окне **Выражение** разверните узел **Общие функции** и выберите **Программный поток**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-228">In the **Expression** dialog box, expand **Common Functions** and click **Program Flow**.</span></span>  
  
4.  <span data-ttu-id="e8dae-229">В списке **Элемент** дважды щелкните **Switch**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-229">In the **Item** list, double-click **Switch**.</span></span>  
  
5.  <span data-ttu-id="e8dae-230">В списке **Категория** щелкните **Поля (выражения)**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-230">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
6.  <span data-ttu-id="e8dae-231">В списке **Значения** дважды щелкните **Gender**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-231">In the **Values** list, double-click **Gender**.</span></span>  
  
7.  <span data-ttu-id="e8dae-232">Введите **="Мужской", "Коала",**</span><span class="sxs-lookup"><span data-stu-id="e8dae-232">Type **="Male", "Koala",**</span></span>  
  
8.  <span data-ttu-id="e8dae-233">В списке **Значения** дважды щелкните **Gender**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-233">In the **Values** list, double-click **Gender**.</span></span>  
  
9. <span data-ttu-id="e8dae-234">Введите **="Женский", "Пингвины",**</span><span class="sxs-lookup"><span data-stu-id="e8dae-234">Type **="Female", "Penguins",**</span></span>  
  
10. <span data-ttu-id="e8dae-235">В списке **Значения** дважды щелкните **Gender**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-235">In the **Values** list, double-click **Gender**.</span></span>  
  
11. <span data-ttu-id="e8dae-236">Введите **="Неизвестно", "Тюльпаны")**</span><span class="sxs-lookup"><span data-stu-id="e8dae-236">Type **="Unknown", "Tulips")**</span></span>  
  
     <span data-ttu-id="e8dae-237">Готовое выражение: `=Switch(Fields!Gender.Value ="Male", "Koala",Fields!Gender.Value ="Female","Penguins",Fields!Gender.Value ="Unknown","Tulips")`</span><span class="sxs-lookup"><span data-stu-id="e8dae-237">The completed expression: `=Switch(Fields!Gender.Value ="Male", "Koala",Fields!Gender.Value ="Female","Penguins",Fields!Gender.Value ="Unknown","Tulips")`</span></span>  
  
12. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
13. <span data-ttu-id="e8dae-238">Снова нажмите кнопку **ОК**, чтобы выйти из диалогового окна **Свойства изображения**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-238">Click **OK** again to close the **Image Properties** dialog box.</span></span>  
  
14. <span data-ttu-id="e8dae-239">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="e8dae-239">Click **Run** to preview the report.</span></span>  
  
##  <a name="5-look-up-countryregion-name"></a><a name="Lookup"></a><span data-ttu-id="e8dae-240">5. Поиск имени в названии "страна"</span><span class="sxs-lookup"><span data-stu-id="e8dae-240">5. Look Up CountryRegion Name</span></span>  
 <span data-ttu-id="e8dae-241">Создадим набор данных CountryRegion и покажем название страны или региона вместо идентификатора с помощью функции **Lookup**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-241">Create the CountryRegion dataset and use the **Lookup** function to display the name of a country/region instead of the identifier of the country/region.</span></span>  
  
#### <a name="to-create-the-countryregion-dataset"></a><span data-ttu-id="e8dae-242">Создание набора данных CountryRegion</span><span class="sxs-lookup"><span data-stu-id="e8dae-242">To create the CountryRegion dataset</span></span>  
  
1.  <span data-ttu-id="e8dae-243">Щелкните **Конструктор** для возврата в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="e8dae-243">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="e8dae-244">В области данных отчета нажмите кнопку **Создать** и выберите **Набор данных**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-244">In the Report Data pane, click **New** and then click **Dataset**.</span></span>  
  
3.  <span data-ttu-id="e8dae-245">Выберите **Использовать набор данных, внедренный в отчет**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-245">Click **Use a dataset embedded in my report**.</span></span>  
  
4.  <span data-ttu-id="e8dae-246">В списке **Источник данных** выберите ExpressionsDataSource.</span><span class="sxs-lookup"><span data-stu-id="e8dae-246">In the **Data source** list, select ExpressionsDataSource.</span></span>  
  
5.  <span data-ttu-id="e8dae-247">В поле **Имя** введите **CountryRegion**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-247">In the **Name** box, type **CountryRegion**</span></span>  
  
6.  <span data-ttu-id="e8dae-248">Убедитесь в том, что выбран тип запроса **Текст** , и нажмите кнопку **Конструктор запросов**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-248">Verify that the **Text** query type is selected and click **Query Designer**.</span></span>  
  
7.  <span data-ttu-id="e8dae-249">Нажмите кнопку **Изменить как текст**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-249">Click **Edit as Text**.</span></span>  
  
8.  <span data-ttu-id="e8dae-250">Скопируйте и вставьте на панели запросов следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="e8dae-250">Copy and paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT 1 AS ID, 'American Samoa' AS CountryRegion  
    UNION SELECT 2 AS CountryRegionID, 'Australia' AS CountryRegion  
    UNION SELECT 3 AS ID, 'Canada' AS CountryRegion  
    UNION SELECT 4 AS ID, 'Germany' AS CountryRegion  
    UNION SELECT 5 AS ID, 'Micronesia' AS CountryRegion  
    UNION SELECT 6 AS ID, 'France' AS CountryRegion  
    UNION SELECT 7 AS ID, 'United States' AS CountryRegion  
    UNION SELECT 8 AS ID, 'Brazil' AS CountryRegion  
    UNION SELECT 9 AS ID, 'Mexico' AS CountryRegion  
    UNION SELECT 10 AS ID, 'Japan' AS CountryRegion  
    UNION SELECT 10 AS ID, 'Australia' AS CountryRegion  
    UNION SELECT 12 AS ID, 'United Kingdom' AS CountryRegion  
    ```  
  
9. <span data-ttu-id="e8dae-251">Нажмите кнопку **выполнить** (**!**), чтобы выполнить запрос.</span><span class="sxs-lookup"><span data-stu-id="e8dae-251">Click **Run** (**!**) to run the query.</span></span>  
  
     <span data-ttu-id="e8dae-252">Результатом запроса будут идентификаторы и названия стран и регионов.</span><span class="sxs-lookup"><span data-stu-id="e8dae-252">The query results are the country/region identifiers and names.</span></span>  
  
10. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
11. <span data-ttu-id="e8dae-253">Снова нажмите кнопку **ОК** , чтобы выйти из диалогового окна **Свойства набора данных** .</span><span class="sxs-lookup"><span data-stu-id="e8dae-253">Click **OK** again to close the **Dataset Properties** dialog box.</span></span>  
  
#### <a name="to-look-up-values-in-the-countryregion-dataset"></a><span data-ttu-id="e8dae-254">Поиск значений в наборе данных CountryRegion</span><span class="sxs-lookup"><span data-stu-id="e8dae-254">To look up values in the CountryRegion dataset</span></span>  
  
1.  <span data-ttu-id="e8dae-255">Щелкните заголовок столбца **Country Region ID** и удалите текст: ID.</span><span class="sxs-lookup"><span data-stu-id="e8dae-255">Click the **Country Region ID** column title and delete the text: ID.</span></span>  
  
2.  <span data-ttu-id="e8dae-256">Щелкните правой кнопкой мыши ячейку для столбца **Country Region** и выберите пункт **Выражение**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-256">Right-click the data cell for the **Country Region** column and click **Expression**.</span></span>  
  
3.  <span data-ttu-id="e8dae-257">Удалите выражение, оставив знак равенства «=».</span><span class="sxs-lookup"><span data-stu-id="e8dae-257">Delete the expression except the initial equal (=) sign.</span></span>  
  
     <span data-ttu-id="e8dae-258">Оставшееся выражение: `=`</span><span class="sxs-lookup"><span data-stu-id="e8dae-258">The remaining expression is: `=`</span></span>  
  
4.  <span data-ttu-id="e8dae-259">В диалоговом окне **Выражение** разверните узел **Общие функции** и выберите **Прочее**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-259">In the **Expression** dialog box, expand **Common Functions** and click **Miscellaneous**.</span></span>  
  
5.  <span data-ttu-id="e8dae-260">В списке **Элемент** дважды щелкните **Lookup**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-260">In the **Item** list, double-click **Lookup**.</span></span>  
  
6.  <span data-ttu-id="e8dae-261">В списке **Категория** щелкните **Поля (выражения)**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-261">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
7.  <span data-ttu-id="e8dae-262">В списке **значения** дважды щелкните `CountryRegionID` .</span><span class="sxs-lookup"><span data-stu-id="e8dae-262">In the **Values** list, double-click `CountryRegionID`.</span></span>  
  
8.  <span data-ttu-id="e8dae-263">Если курсор не расположен сразу после `CountryRegionID.Value`, установите его в это положение.</span><span class="sxs-lookup"><span data-stu-id="e8dae-263">If the cursor is not already immediately after `CountryRegionID.Value`, place it there.</span></span>  
  
9. <span data-ttu-id="e8dae-264">Удалите правую скобку и введите **,Fields!ID.value, Fields!CountryRegion.value, "CountryRegion")**</span><span class="sxs-lookup"><span data-stu-id="e8dae-264">Delete the right parenthesis and then type **,Fields!ID.value, Fields!CountryRegion.value, "CountryRegion")**</span></span>  
  
     <span data-ttu-id="e8dae-265">Готовое выражение: `=Lookup(Fields!CountryRegionID.Value,Fields!ID.value, Fields!CountryRegion.value, "CountryRegion")`</span><span class="sxs-lookup"><span data-stu-id="e8dae-265">The completed expression: `=Lookup(Fields!CountryRegionID.Value,Fields!ID.value, Fields!CountryRegion.value, "CountryRegion")`</span></span>  
  
     <span data-ttu-id="e8dae-266">Синтаксис функции **Lookup** задает поиск соответствия между CountryRegionID и ID в наборе данных CountryRegion, возвращающий значение CountryRegion, которое также имеется в наборе данных CountryRegion.</span><span class="sxs-lookup"><span data-stu-id="e8dae-266">The syntax of the **Lookup** function specifies a lookup between CountryRegionID and ID in the CountryRegion dataset that returns the CountryRegion value, which is also in the CountryRegion dataset.</span></span>  
  
10. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
11. <span data-ttu-id="e8dae-267">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="e8dae-267">Click **Run** to preview the report.</span></span>  
  
##  <a name="6-count-days-since-last-purchase"></a><a name="Count"></a><span data-ttu-id="e8dae-268">6. Подсчет дней с момента последней покупки</span><span class="sxs-lookup"><span data-stu-id="e8dae-268">6. Count Days Since Last Purchase</span></span>  
 <span data-ttu-id="e8dae-269">Добавьте столбец, а затем используйте функцию **Now** или `ExecutionTime` встроенную глобальную переменную, чтобы рассчитать количество дней с сегодняшнего дня с момента последнего приобретения сотрудника.</span><span class="sxs-lookup"><span data-stu-id="e8dae-269">Add a column and then use the **Now** function or the `ExecutionTime` built-in global variable to calculate the number of days from today since a person's last purchases.</span></span>  
  
#### <a name="to-add-the-days-ago-column"></a><span data-ttu-id="e8dae-270">Добавление столбца Days Ago</span><span class="sxs-lookup"><span data-stu-id="e8dae-270">To add the Days Ago column</span></span>  
  
1.  <span data-ttu-id="e8dae-271">Щелкните **Конструктор** для возврата в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="e8dae-271">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="e8dae-272">Щелкните правой кнопкой мыши столбец **Last Purchase** , наведите указатель на пункт **Вставить столбец**, а затем выберите пункт **Справа**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-272">Right-click the **Last Purchase** column, point to **Insert Column**, and then click **Right**.</span></span>  
  
     <span data-ttu-id="e8dae-273">Новый столбец будет добавлен справа от столбца **Last Purchase** .</span><span class="sxs-lookup"><span data-stu-id="e8dae-273">A new column is added to the right of the **Last Purchase** column.</span></span>  
  
3.  <span data-ttu-id="e8dae-274">В заголовке столбца введите **Days Ago**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-274">In the column header, type **Days Ago**</span></span>  
  
4.  <span data-ttu-id="e8dae-275">Щелкните правой кнопкой мыши ячейку столбца **Days Ago** и выберите пункт **Выражение**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-275">Right-click the data cell for the **Days Ago** column and click **Expression**.</span></span>  
  
5.  <span data-ttu-id="e8dae-276">В диалоговом окне **Выражение** разверните узел **Общие функции** и выберите пункт **Дата и время**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-276">In the **Expression** dialog box, expand **Common Functions**, and then click **Date & Time**.</span></span>  
  
6.  <span data-ttu-id="e8dae-277">В списке **Элемент** дважды щелкните **DateDiff**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-277">In the **Item** list, double-click **DateDiff**.</span></span>  
  
7.  <span data-ttu-id="e8dae-278">Если курсор не расположен сразу после `DateDiff(`, установите его в это положение.</span><span class="sxs-lookup"><span data-stu-id="e8dae-278">If the cursor is not already immediately after `DateDiff(`, place it there.</span></span>  
  
8.  <span data-ttu-id="e8dae-279">Введите **"d",**</span><span class="sxs-lookup"><span data-stu-id="e8dae-279">Type **"d",**</span></span>  
  
9. <span data-ttu-id="e8dae-280">В списке **Категория** щелкните **Поля (выражения)**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-280">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
10. <span data-ttu-id="e8dae-281">В списке **Значения** дважды щелкните **LastPurchase**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-281">In the **Values** list, double-click **LastPurchase**.</span></span>  
  
11. <span data-ttu-id="e8dae-282">Если курсор не расположен сразу после `Fields!LastPurchase.Value`, установите его в это положение.</span><span class="sxs-lookup"><span data-stu-id="e8dae-282">If the cursor is not already immediately after `Fields!LastPurchase.Value`, place it there.</span></span>  
  
12. <span data-ttu-id="e8dae-283">Тип **,**</span><span class="sxs-lookup"><span data-stu-id="e8dae-283">Type **,**</span></span>  
  
13. <span data-ttu-id="e8dae-284">В списке **Категория** еще раз щелкните **Дата и время**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-284">In the **Category** list, click **Date & Time** again.</span></span>  
  
14. <span data-ttu-id="e8dae-285">В списке **Элемент** дважды щелкните **Now**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-285">In the **Item** list, double-click **Now**.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="e8dae-286">В рабочих отчетах функцию **Now** нельзя использовать в выражениях, которые вычисляются многократно при подготовке отчета (например, в строках детализации отчета).</span><span class="sxs-lookup"><span data-stu-id="e8dae-286">In production reports you should not use the **Now** function in expressions that are evaluated multiple times as the report renders (for example, in the detail rows of a report).</span></span> <span data-ttu-id="e8dae-287">Значение **Now** будет разным в разных строках, и эти различия повлияют на результаты вычислений, что может привести к некоторой несогласованности результатов.</span><span class="sxs-lookup"><span data-stu-id="e8dae-287">The value of **Now** changes from row to row and the different values affect the evaluation results of expressions, which leads to results that are subtly inconsistent.</span></span> <span data-ttu-id="e8dae-288">Вместо этого необходимо пользоваться глобальной переменной `ExecutionTime`, имеющейся в службах [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e8dae-288">Instead, you should use the `ExecutionTime` global variable that [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] provides.</span></span>  
  
15. <span data-ttu-id="e8dae-289">Если курсор не расположен сразу после `Now(`, установите его в это положение.</span><span class="sxs-lookup"><span data-stu-id="e8dae-289">If the cursor is not already immediately after `Now(`, place it there.</span></span>  
  
16. <span data-ttu-id="e8dae-290">Удалите левую скобку и введите **)**</span><span class="sxs-lookup"><span data-stu-id="e8dae-290">Delete the left parenthesis and then type **)**</span></span>  
  
     <span data-ttu-id="e8dae-291">Готовое выражение: `=DateDiff("d", Fields!LastPurchase.Value, Now)`</span><span class="sxs-lookup"><span data-stu-id="e8dae-291">The completed expression: `=DateDiff("d", Fields!LastPurchase.Value, Now)`</span></span>  
  
17. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="7-use-an-indicator-to-show-sales-comparison"></a><a name="Indicator"></a><span data-ttu-id="e8dae-292">7. Использование индикатора для отображения сравнения продаж</span><span class="sxs-lookup"><span data-stu-id="e8dae-292">7. Use an Indicator to Show Sales Comparison</span></span>  
 <span data-ttu-id="e8dae-293">Добавьте новый столбец и используйте индикатор, чтобы узнать, будут ли покупки пользователя с начала года (YTD) выше или ниже среднего закупок с начала года.</span><span class="sxs-lookup"><span data-stu-id="e8dae-293">Add a new column and use an indicator to show whether a person's year-to-date (YTD) purchases are above or below the average YTD purchases.</span></span> <span data-ttu-id="e8dae-294">Функция **Round** округляет значения до целого числа.</span><span class="sxs-lookup"><span data-stu-id="e8dae-294">The **Round** function removes decimals from values.</span></span>  
  
 <span data-ttu-id="e8dae-295">Настройка индикатора и его состояний производится в несколько шагов.</span><span class="sxs-lookup"><span data-stu-id="e8dae-295">The configuration of the indicator and its states requires many steps.</span></span> <span data-ttu-id="e8dae-296">При необходимости в процедуре "Настройка индикатора" можно пропустить и скопировать и вставить заполненные выражения из этого учебника в диалоговое окно **выражение** .</span><span class="sxs-lookup"><span data-stu-id="e8dae-296">If you want to, in the "To configure the indicator" procedure, you can skip ahead and copy/paste the completed expressions from this tutorial into the **Expression** dialog box.</span></span>  
  
#### <a name="to-add-the--or---avg-sales-column"></a><span data-ttu-id="e8dae-297">Добавление столбца «+ or - AVG Sales»</span><span class="sxs-lookup"><span data-stu-id="e8dae-297">To add the + or - AVG Sales column</span></span>  
  
1.  <span data-ttu-id="e8dae-298">Щелкните правой кнопкой мыши столбец **YTD Purchase** , наведите указатель на пункт **Вставить столбец**, а затем выберите пункт **Справа**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-298">Right-click the **YTD Purchase** column, point to **Insert Column**, and then click **Right**.</span></span>  
  
     <span data-ttu-id="e8dae-299">Новый столбец будет добавлен справа от столбца **YTD Purchase** .</span><span class="sxs-lookup"><span data-stu-id="e8dae-299">A new column is added to the right of the **YTD Purchase** column.</span></span>  
  
2.  <span data-ttu-id="e8dae-300">Щелкните заголовок нового столбца и введите **+ or - AVG Sales**</span><span class="sxs-lookup"><span data-stu-id="e8dae-300">Click the title of the column and type **+ or - AVG Sales**</span></span>  
  
#### <a name="to-add-an-indicator"></a><span data-ttu-id="e8dae-301">Добавление индикатора</span><span class="sxs-lookup"><span data-stu-id="e8dae-301">To add an indicator</span></span>  
  
1.  <span data-ttu-id="e8dae-302">На вкладке ленты **Вставка** щелкните **Индикатор**, а затем ячейку данных для столбца **+ or - AVG Sales**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-302">On the **Insert** tab of the ribbon, click **Indicator**, and then click the data cell for the **+ or - AVG Sales** column.</span></span>  
  
     <span data-ttu-id="e8dae-303">Откроется диалоговое окно **Выбор стиля индикатора** .</span><span class="sxs-lookup"><span data-stu-id="e8dae-303">The **Select Indicator Type** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="e8dae-304">В группе наборов значков **Направляющие** щелкните набор из трех серых стрелок.</span><span class="sxs-lookup"><span data-stu-id="e8dae-304">In the **Directional** group of icon sets, click the set of three gray arrows.</span></span>  
  
3.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-configure-the-indicator"></a><span data-ttu-id="e8dae-305">Настройка индикатора</span><span class="sxs-lookup"><span data-stu-id="e8dae-305">To configure the indicator</span></span>  
  
1.  <span data-ttu-id="e8dae-306">Щелкните индикатор правой кнопкой мыши, выберите пункт **Свойства индикатора**, а затем щелкните **Значение и состояния**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-306">Right-click the indicator, click **Indicator Properties**, and then click **Value and States**.</span></span>  
  
2.  <span data-ttu-id="e8dae-307">Нажмите кнопку выражения **fx** рядом с текстовым полем **Значение** .</span><span class="sxs-lookup"><span data-stu-id="e8dae-307">Click the expression **fx** button next to the **Value** text box.</span></span>  
  
3.  <span data-ttu-id="e8dae-308">В диалоговом окне **Выражение** разверните узел **Общие функции**и выберите **Математические**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-308">In the **Expression** dialog box, expand **Common Functions**, and then click **Math**.</span></span>  
  
4.  <span data-ttu-id="e8dae-309">В списке **Элемент** дважды щелкните **Round**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-309">In the **Item** list, double-click **Round**.</span></span>  
  
5.  <span data-ttu-id="e8dae-310">В списке **Категория** щелкните **Поля (выражения)**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-310">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
6.  <span data-ttu-id="e8dae-311">В списке **Значения** дважды щелкните **YTDPurchase**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-311">In the **Values** list, double-click **YTDPurchase**.</span></span>  
  
7.  <span data-ttu-id="e8dae-312">Если курсор не расположен сразу после `Fields!YTDPurchase.Value`, установите его в это положение.</span><span class="sxs-lookup"><span data-stu-id="e8dae-312">If the cursor is not already immediately after `Fields!YTDPurchase.Value`, place it there.</span></span>  
  
8.  <span data-ttu-id="e8dae-313">Тип**-**</span><span class="sxs-lookup"><span data-stu-id="e8dae-313">Type  **-**</span></span>  
  
9. <span data-ttu-id="e8dae-314">Разверните узел **Общие функции** снова и выберите **Статистические**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-314">Expand **Common Functions** again and click **Aggregate**.</span></span>  
  
10. <span data-ttu-id="e8dae-315">В списке **Элемент** дважды щелкните **Avg**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-315">In the **Item** list, double-click **Avg**.</span></span>  
  
11. <span data-ttu-id="e8dae-316">В списке **Категория** щелкните **Поля (выражения)**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-316">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
12. <span data-ttu-id="e8dae-317">В списке **Значения** дважды щелкните **YTDPurchase**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-317">In the **Values** list, double-click **YTDPurchase**.</span></span>  
  
13. <span data-ttu-id="e8dae-318">Если курсор не расположен сразу после `Fields!YTDPurchase.Value`, установите его в это положение.</span><span class="sxs-lookup"><span data-stu-id="e8dae-318">If the cursor is not already immediately after `Fields!YTDPurchase.Value`, place it there.</span></span>  
  
14. <span data-ttu-id="e8dae-319">Введите **, "Expressions"))**</span><span class="sxs-lookup"><span data-stu-id="e8dae-319">Type **, "Expressions"))**</span></span>  
  
     <span data-ttu-id="e8dae-320">Готовое выражение: `=Round(Fields!YTDPurchase.Value - Avg(Fields!YTDPurchase.Value, "Expressions"))`</span><span class="sxs-lookup"><span data-stu-id="e8dae-320">The completed expression: `=Round(Fields!YTDPurchase.Value - Avg(Fields!YTDPurchase.Value, "Expressions"))`</span></span>  
  
15. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
16. <span data-ttu-id="e8dae-321">В поле **Единица измерения состояний** выберите **Число**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-321">In the **States Measurement Unit** box, select **Numeric**.</span></span>  
  
17. <span data-ttu-id="e8dae-322">В строке со стрелкой вниз нажмите кнопку **fx** справа от текстового поля для значения **Начало** .</span><span class="sxs-lookup"><span data-stu-id="e8dae-322">In the row with the down-pointing arrow, click the **fx** button to the right of the text box for the **Start** value.</span></span>  
  
18. <span data-ttu-id="e8dae-323">В диалоговом окне **Выражение** разверните узел **Общие функции**и выберите **Математические**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-323">In the **Expression** dialog box, expand **Common Functions**, and then click **Math**.</span></span>  
  
19. <span data-ttu-id="e8dae-324">В списке **Элемент** дважды щелкните **Round**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-324">In the **Item** list, double-click **Round**.</span></span>  
  
20. <span data-ttu-id="e8dae-325">В списке **Категория** щелкните **Поля (выражения)**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-325">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
21. <span data-ttu-id="e8dae-326">В списке **Значения** дважды щелкните **YTDPurchase**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-326">In the **Values** list, double-click **YTDPurchase**.</span></span>  
  
22. <span data-ttu-id="e8dae-327">Если курсор не расположен сразу после `Fields!YTDPurchase.Value`, установите его в это положение.</span><span class="sxs-lookup"><span data-stu-id="e8dae-327">If the cursor is not already immediately after `Fields!YTDPurchase.Value`, place it there.</span></span>  
  
23. <span data-ttu-id="e8dae-328">Тип**-**</span><span class="sxs-lookup"><span data-stu-id="e8dae-328">Type  **-**</span></span>  
  
24. <span data-ttu-id="e8dae-329">Разверните узел **Общие функции** снова и выберите **Статистические**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-329">Expand **Common Functions** again and click **Aggregate**.</span></span>  
  
25. <span data-ttu-id="e8dae-330">В списке **Элемент** дважды щелкните **Avg**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-330">In the **Item** list, double-click **Avg**.</span></span>  
  
26. <span data-ttu-id="e8dae-331">В списке **Категория** щелкните **Поля (выражения)**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-331">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
27. <span data-ttu-id="e8dae-332">В списке **Значения** дважды щелкните **YTDPurchase**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-332">In the **Values** list, double-click **YTDPurchase**.</span></span>  
  
28. <span data-ttu-id="e8dae-333">Если курсор не расположен сразу после `Fields!YTDPurchase.Value`, установите его в это положение.</span><span class="sxs-lookup"><span data-stu-id="e8dae-333">If the cursor is not already immediately after `Fields!YTDPurchase.Value`, place it there.</span></span>  
  
29. <span data-ttu-id="e8dae-334">Введите **, "Expressions")) < 0**</span><span class="sxs-lookup"><span data-stu-id="e8dae-334">Type **, "Expressions")) < 0**</span></span>  
  
     <span data-ttu-id="e8dae-335">Готовое выражение: `=Round(Fields!YTDPurchase.Value - Avg(Fields!YTDPurchase.Value, "Expressions")) < 0`</span><span class="sxs-lookup"><span data-stu-id="e8dae-335">The completed expression: `=Round(Fields!YTDPurchase.Value - Avg(Fields!YTDPurchase.Value, "Expressions")) < 0`</span></span>  
  
30. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
31. <span data-ttu-id="e8dae-336">В текстовом поле для значения **Конец** введите **0**</span><span class="sxs-lookup"><span data-stu-id="e8dae-336">In the text box for the **End** value, type **0**</span></span>  
  
32. <span data-ttu-id="e8dae-337">Щелкните строку, где находится горизонтальная стрелка, а затем щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-337">Click the row with the horizontal-pointing arrow and click **Delete**.</span></span>  
  
33. <span data-ttu-id="e8dae-338">В строке со стрелкой вверх в поле **Начало** введите **0**</span><span class="sxs-lookup"><span data-stu-id="e8dae-338">In the row with the up-pointing arrow, in the **Start** box, type **0**</span></span>  
  
34. <span data-ttu-id="e8dae-339">Нажмите кнопку **fx** справа от текстового поля для значения **Конец** .</span><span class="sxs-lookup"><span data-stu-id="e8dae-339">Click the **fx** button to the right of the text box for the **End** value.</span></span>  
  
35. <span data-ttu-id="e8dae-340">В диалоговом окне **выражение** создайте выражение:`=Round(Fields!YTDPurchase.Value - Avg(Fields!YTDPurchase.Value, "Expressions")) >0`</span><span class="sxs-lookup"><span data-stu-id="e8dae-340">In the **Expression** dialog box, create the expression: `=Round(Fields!YTDPurchase.Value - Avg(Fields!YTDPurchase.Value, "Expressions")) >0`</span></span>  
  
36. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
37. <span data-ttu-id="e8dae-341">Снова нажмите кнопку **ОК** , чтобы закрыть диалоговое окно **Свойства индикатора** .</span><span class="sxs-lookup"><span data-stu-id="e8dae-341">Click **OK** again to close the **Indicator properties** dialog box.</span></span>  
  
38. <span data-ttu-id="e8dae-342">Нажмите кнопку **Выполнить** для предварительного просмотра отчета.</span><span class="sxs-lookup"><span data-stu-id="e8dae-342">Click **Run** to preview the report.</span></span>  
  
##  <a name="8-make-the-report-a-green-bar-report"></a><a name="GreenBar"></a><span data-ttu-id="e8dae-343">8. Сделайте отчет отчетом «зеленая полоса»</span><span class="sxs-lookup"><span data-stu-id="e8dae-343">8. Make the Report a "Green Bar" Report</span></span>  
 <span data-ttu-id="e8dae-344">Задайте в параметре цвет, который будет применен для чередования строк в отчете.</span><span class="sxs-lookup"><span data-stu-id="e8dae-344">Use a parameter to specify the color to apply to alternating rows in the report, making it a barred report.</span></span>  
  
#### <a name="to-add-a-parameter"></a><span data-ttu-id="e8dae-345">Добавление параметра</span><span class="sxs-lookup"><span data-stu-id="e8dae-345">To add a parameter</span></span>  
  
1.  <span data-ttu-id="e8dae-346">Щелкните **Конструктор** для возврата в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="e8dae-346">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="e8dae-347">На панели **Данные отчета** щелкните правой кнопкой мыши узел **Параметры** и выберите команду **Добавить параметр**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-347">In the **Report Data** pane, right-click **Parameters** and click **Add Parameter**.</span></span>  
  
     <span data-ttu-id="e8dae-348">Откроется диалоговое окно **Свойства параметра отчета** .</span><span class="sxs-lookup"><span data-stu-id="e8dae-348">The **Report Parameter Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="e8dae-349">В поле **Подсказка**введите **Выберите цвет**</span><span class="sxs-lookup"><span data-stu-id="e8dae-349">In **Prompt**, type **Choose color**</span></span>  
  
4.  <span data-ttu-id="e8dae-350">В поле **Имя**введите **RowColor**</span><span class="sxs-lookup"><span data-stu-id="e8dae-350">In **Name**, type **RowColor**</span></span>  
  
5.  <span data-ttu-id="e8dae-351">На левой панели щелкните **Допустимые значения**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-351">In the left pane, click **Available Values**.</span></span>  
  
6.  <span data-ttu-id="e8dae-352">Нажмите кнопку **Указать значения**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-352">Click **Specify values**.</span></span>  
  
7.  <span data-ttu-id="e8dae-353">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-353">Click **Add**.</span></span>  
  
8.  <span data-ttu-id="e8dae-354">В поле **Метка** введите: **желтый** .</span><span class="sxs-lookup"><span data-stu-id="e8dae-354">In the **Label** box, type: **Yellow**</span></span>  
  
9. <span data-ttu-id="e8dae-355">В поле **Значение** введите **Yellow**</span><span class="sxs-lookup"><span data-stu-id="e8dae-355">In the **Value** box, type **Yellow**</span></span>  
  
10. <span data-ttu-id="e8dae-356">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-356">Click **Add**.</span></span>  
  
11. <span data-ttu-id="e8dae-357">В поле **Метка** введите **Green**</span><span class="sxs-lookup"><span data-stu-id="e8dae-357">In the **Label** box, type **Green**</span></span>  
  
12. <span data-ttu-id="e8dae-358">В поле **Значение** введите **PaleGreen**</span><span class="sxs-lookup"><span data-stu-id="e8dae-358">In the **Value** box, type **PaleGreen**</span></span>  
  
13. <span data-ttu-id="e8dae-359">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-359">Click **Add**.</span></span>  
  
14. <span data-ttu-id="e8dae-360">В поле **Метка** введите **Blue**</span><span class="sxs-lookup"><span data-stu-id="e8dae-360">In the **Label** box, type **Blue**</span></span>  
  
15. <span data-ttu-id="e8dae-361">В поле **Значение** введите **LightBlue**</span><span class="sxs-lookup"><span data-stu-id="e8dae-361">In the **Value** box, type **LightBlue**</span></span>  
  
16. <span data-ttu-id="e8dae-362">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-362">Click **Add**.</span></span>  
  
17. <span data-ttu-id="e8dae-363">В поле **Метка** введите **Pink**</span><span class="sxs-lookup"><span data-stu-id="e8dae-363">In the **Label** box, type **Pink**</span></span>  
  
18. <span data-ttu-id="e8dae-364">В поле **Значение** введите **Pink**</span><span class="sxs-lookup"><span data-stu-id="e8dae-364">In the **Value** box, type **Pink**</span></span>  
  
19. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-apply-alternating-colors-to-detail-rows"></a><span data-ttu-id="e8dae-365">Применение цветов чередования строк детализации</span><span class="sxs-lookup"><span data-stu-id="e8dae-365">To apply alternating colors to detail rows</span></span>  
  
1.  <span data-ttu-id="e8dae-366">Откройте на ленте вкладку **Вид** и убедитесь в том, что выбрано **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-366">Click the **View** tab on the ribbon and verify that **Properties** is selected.</span></span>  
  
2.  <span data-ttu-id="e8dae-367">Щелкните ячейку данных для столбца **Name** и нажмите клавишу SHIFT.</span><span class="sxs-lookup"><span data-stu-id="e8dae-367">Click the data cell for the **Name** column and press the Shift key.</span></span>  
  
3.  <span data-ttu-id="e8dae-368">Одну за другой щелкните все остальные ячейки в строке.</span><span class="sxs-lookup"><span data-stu-id="e8dae-368">One by one, click the other cells in the row.</span></span>  
  
4.  <span data-ttu-id="e8dae-369">На панели свойств щелкните **BackgroundColor**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-369">In the Properties pane, click **BackgroundColor**.</span></span>  
  
     <span data-ttu-id="e8dae-370">Если на панели свойств свойства разбиты по категориям, свойство **BackgroundColor** находится в категории **Заливка**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-370">If your Properties pane lists properties by category, you will find the **BackgroundColor** under the **Fill** category.</span></span>  
  
5.  <span data-ttu-id="e8dae-371">Нажмите стрелку вниз и выберите **Выражение**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-371">Click the down arrow and then click **Expression**.</span></span>  
  
6.  <span data-ttu-id="e8dae-372">В диалоговом окне **Выражение** разверните узел **Общие функции** и выберите **Программный поток**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-372">In the **Expression** dialog box, expand **Common Functions**, and then click **Program Flow**.</span></span>  
  
7.  <span data-ttu-id="e8dae-373">В списке **Элемент** дважды щелкните **IIf**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-373">In the **Item** list, double-click **IIf**.</span></span>  
  
8.  <span data-ttu-id="e8dae-374">Разверните узел **Общие функции** и выберите **Статистические**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-374">Expand **Common Functions** and click **Aggregate**.</span></span>  
  
9. <span data-ttu-id="e8dae-375">В списке **Элемент** дважды щелкните **RunningValue**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-375">In the **Item** list, double-click **RunningValue**.</span></span>  
  
10. <span data-ttu-id="e8dae-376">В списке **Категория** щелкните **Поля (выражения)**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-376">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
11. <span data-ttu-id="e8dae-377">В списке **Значения** дважды щелкните **FirstName**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-377">In the **Values** list, double-click **FirstName**.</span></span>  
  
12. <span data-ttu-id="e8dae-378">Если курсор не расположен сразу после `Fields!FirstName.Value`, установите его в это положение, а затем введите **,**</span><span class="sxs-lookup"><span data-stu-id="e8dae-378">If the cursor is not already immediately after `Fields!FirstName.Value`, place it there and type **,**</span></span>  
  
13. <span data-ttu-id="e8dae-379">Разверните узел **Общие функции** и выберите **Статистические**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-379">Expand **Common Functions** and click **Aggregate**.</span></span>  
  
14. <span data-ttu-id="e8dae-380">В списке **Элемент** дважды щелкните **Count**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-380">In the **Item** list, double-click **Count**.</span></span>  
  
15. <span data-ttu-id="e8dae-381">Если курсор не расположен сразу после `Count(`, установите его в это положение.</span><span class="sxs-lookup"><span data-stu-id="e8dae-381">If the cursor is not already immediately after `Count(`, place it there.</span></span>  
  
16. <span data-ttu-id="e8dae-382">Удалите левую круглую скобку и введите **"Expressions")**</span><span class="sxs-lookup"><span data-stu-id="e8dae-382">Delete the left parenthesis and then type **,"Expressions")**</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e8dae-383">Expressions — это имя набора данных, в котором нужно подсчитать строки данных.</span><span class="sxs-lookup"><span data-stu-id="e8dae-383">Expressions is the name of the dataset in which to count data rows.</span></span>  
  
17. <span data-ttu-id="e8dae-384">Разверните узел **Операторы** и выберите **Арифметические**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-384">Expand **Operators** and click **Arithmetic**.</span></span>  
  
18. <span data-ttu-id="e8dae-385">В списке **Элемент** дважды щелкните **Mod**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-385">In the **Item** list, double-click **Mod**.</span></span>  
  
19. <span data-ttu-id="e8dae-386">Если курсор не расположен сразу после `Mod`, установите его в это положение.</span><span class="sxs-lookup"><span data-stu-id="e8dae-386">If the cursor is not already immediately after `Mod`, place it there.</span></span>  
  
20. <span data-ttu-id="e8dae-387">Введите **2 =0,**</span><span class="sxs-lookup"><span data-stu-id="e8dae-387">Type  **2 =0,**</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="e8dae-388">Перед числом 2 должен стоять пробел.</span><span class="sxs-lookup"><span data-stu-id="e8dae-388">Be sure you include a space before you type the number 2.</span></span>  
  
21. <span data-ttu-id="e8dae-389">Щелкните **Параметры** и в списке **Значения** дважды щелкните **RowColor**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-389">Click **Parameters** and in the **Values** list, double-click **RowColor**.</span></span>  
  
22. <span data-ttu-id="e8dae-390">Если курсор не расположен сразу после `Parameters!RowColor.Value`, установите его в это положение.</span><span class="sxs-lookup"><span data-stu-id="e8dae-390">If the cursor is not already immediately after `Parameters!RowColor.Value`, place it there.</span></span>  
  
23. <span data-ttu-id="e8dae-391">Введите **, "белый")**</span><span class="sxs-lookup"><span data-stu-id="e8dae-391">Type **, "White")**</span></span>  
  
     <span data-ttu-id="e8dae-392">Готовое выражение: `=IIf(RunningValue(Fields!FirstName.Value,Count, "Expressions") Mod 2 =0, Parameters!RowColor.Value, "White")`</span><span class="sxs-lookup"><span data-stu-id="e8dae-392">The completed expression: `=IIf(RunningValue(Fields!FirstName.Value,Count, "Expressions") Mod 2 =0, Parameters!RowColor.Value, "White")`</span></span>  
  
24. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="run-the-report"></a><span data-ttu-id="e8dae-393">Запустите отчет.</span><span class="sxs-lookup"><span data-stu-id="e8dae-393">Run the Report</span></span>  
  
1.  <span data-ttu-id="e8dae-394">Если не открыта вкладка **Главная**, перейдите на вкладку **Главная**, чтобы вернуться в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="e8dae-394">If not on the **Home** tab, click **Home** to return to design view.</span></span>  
  
2.  <span data-ttu-id="e8dae-395">Нажмите кнопку **Запустить**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-395">Click **Run**.</span></span>  
  
3.  <span data-ttu-id="e8dae-396">В раскрывающемся списке **Выбор цвета** выберите цвет для строк отчета, отличных от белых.</span><span class="sxs-lookup"><span data-stu-id="e8dae-396">In the **Choose color** drop-down list, select the color of the non-white bars on the report.</span></span>  
  
4.  <span data-ttu-id="e8dae-397">Нажмите кнопку **Просмотреть отчет**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-397">Click **View Report**.</span></span>  
  
     <span data-ttu-id="e8dae-398">Отчет будет подготовлен к просмотру с выбранным цветом фона чередующихся строк.</span><span class="sxs-lookup"><span data-stu-id="e8dae-398">The report renders and alternating rows have the background that you chose.</span></span>  
  
##  <a name="optional-format-date-column"></a><a name="DateFormat"></a><span data-ttu-id="e8dae-399">используемых Форматировать столбец даты</span><span class="sxs-lookup"><span data-stu-id="e8dae-399">(optional) Format Date Column</span></span>  
 <span data-ttu-id="e8dae-400">Отформатируйте столбец **Last Purchase**, который содержит даты.</span><span class="sxs-lookup"><span data-stu-id="e8dae-400">Format the **Last Purchase** column, which contains dates.</span></span>  
  
#### <a name="to-format-date-column"></a><span data-ttu-id="e8dae-401">Форматирование столбца даты</span><span class="sxs-lookup"><span data-stu-id="e8dae-401">To format date column</span></span>  
  
1.  <span data-ttu-id="e8dae-402">Щелкните **Конструктор** для возврата в режим конструктора.</span><span class="sxs-lookup"><span data-stu-id="e8dae-402">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="e8dae-403">Щелкните правой кнопкой мыши ячейку данных для столбца **Last Purchase** и выберите пункт **Свойства текстового поля**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-403">Right-click the data cell for the **Last Purchase** column and click **Text Box Properties**.</span></span>  
  
3.  <span data-ttu-id="e8dae-404">В диалоговом окне **Свойства текстового поля** щелкните **Число**, затем **Дата**, а затем выберите тип **\*1/31/2000**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-404">In the **Text Box Properties** dialog box, click **Number**, click **Date**, and then click the type **\*1/31/2000**.</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="optional-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="e8dae-405">используемых Добавление заголовка отчета</span><span class="sxs-lookup"><span data-stu-id="e8dae-405">(optional) Add a Report Title</span></span>  
 <span data-ttu-id="e8dae-406">Добавим заголовок отчета.</span><span class="sxs-lookup"><span data-stu-id="e8dae-406">Add a title to the report.</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="e8dae-407">Добавление заголовка отчета</span><span class="sxs-lookup"><span data-stu-id="e8dae-407">To add a report title</span></span>  
  
1.  <span data-ttu-id="e8dae-408">В области конструктора щелкните ссылку **Щелкните, чтобы добавить заголовок**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-408">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="e8dae-409">Введите фразу **Сводка сравнения продаж** и щелкните за пределами текстового поля.</span><span class="sxs-lookup"><span data-stu-id="e8dae-409">Type **Sales Comparison Summary**, and then click outside the text box.</span></span>  
  
3.  <span data-ttu-id="e8dae-410">Щелкните правой кнопкой мыши текстовое поле **Сводка сравнения продаж** и выберите пункт **Свойства текстового поля**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-410">Right-click the text box that contains **Sales Comparison Summary** and click **Text Box Properties**.</span></span>  
  
4.  <span data-ttu-id="e8dae-411">В диалоговом окне **Свойства текстового поля** нажмите кнопку **Шрифт**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-411">In the **Text Box Properties** dialog box, click **Font**.</span></span>  
  
5.  <span data-ttu-id="e8dae-412">В списке **Размер** выберите **18пт**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-412">In the **Size** list, select **18pt**.</span></span>  
  
6.  <span data-ttu-id="e8dae-413">В списке **Цвет** выберите **Серый**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-413">In the **Color** list, select **Gray**.</span></span>  
  
7.  <span data-ttu-id="e8dae-414">Выберите **Полужирный** и **Курсив**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-414">Select  **Bold** and  **Italic**.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="optional-save-the-report"></a><a name="Save"></a><span data-ttu-id="e8dae-415">используемых Сохранение отчета</span><span class="sxs-lookup"><span data-stu-id="e8dae-415">(optional) Save the Report</span></span>  
 <span data-ttu-id="e8dae-416">Отчеты можно сохранять на сервере отчетов, в библиотеке SharePoint или на компьютере.</span><span class="sxs-lookup"><span data-stu-id="e8dae-416">You can save reports to a report server, SharePoint library, or your computer.</span></span> <span data-ttu-id="e8dae-417">Дополнительные сведения см. в разделе [Сохранение отчетов (построитель отчетов)](report-builder/saving-reports-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="e8dae-417">For more information, see [Saving Reports &#40;Report Builder&#41;](report-builder/saving-reports-report-builder.md).</span></span>  
  
 <span data-ttu-id="e8dae-418">В данном учебнике предусмотрено сохранение отчета на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="e8dae-418">In this tutorial, save the report to a report server.</span></span> <span data-ttu-id="e8dae-419">Если нет доступа к серверу отчетов, сохраните отчет на компьютере.</span><span class="sxs-lookup"><span data-stu-id="e8dae-419">If you do not have access to a report server, save the report to your computer.</span></span>  
  
#### <a name="to-save-the-report-to-a-report-server"></a><span data-ttu-id="e8dae-420">Сохранение отчета на сервере отчетов</span><span class="sxs-lookup"><span data-stu-id="e8dae-420">To save the report to a report server</span></span>  
  
1.  <span data-ttu-id="e8dae-421">На кнопке **Построитель отчетов** нажмите кнопку **Сохранить как**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-421">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="e8dae-422">Нажмите кнопку **Последние сайты и серверы**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-422">Click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="e8dae-423">Выберите или введите имя сервера отчетов, для которого существует разрешение на сохранение отчетов.</span><span class="sxs-lookup"><span data-stu-id="e8dae-423">Select or type the name of the report server where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="e8dae-424">Появится сообщение «Соединение с сервером отчетов».</span><span class="sxs-lookup"><span data-stu-id="e8dae-424">The message "Connecting to report server" appears.</span></span> <span data-ttu-id="e8dae-425">После того как соединение установлено, пользователю представляется содержимое папки, заданной администратором сервера отчетов в качестве места хранения отчетов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e8dae-425">When the connection is complete, you will see the contents of the report folder that the report server administrator specified as the default report location.</span></span>  
  
4.  <span data-ttu-id="e8dae-426">В поле **Имя** замените имя по умолчанию на **Сводка сравнения продаж**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-426">In **Name**, replace the default name with **Sales Comparison Summary**.</span></span>  
  
5.  <span data-ttu-id="e8dae-427">Выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-427">Click **Save**.</span></span>  
  
 <span data-ttu-id="e8dae-428">Отчет будет сохранен на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="e8dae-428">The report is saved to the report server.</span></span> <span data-ttu-id="e8dae-429">Имя сервера отчетов, с которым установлено соединение, будет отображено в строке состояния в нижней части окна.</span><span class="sxs-lookup"><span data-stu-id="e8dae-429">The name of report server that you are connected to appears in the status bar at the bottom of the window.</span></span>  
  
#### <a name="to-save-the-report-to-your-computer"></a><span data-ttu-id="e8dae-430">Сохранение отчета на компьютере</span><span class="sxs-lookup"><span data-stu-id="e8dae-430">To save the report to your computer</span></span>  
  
1.  <span data-ttu-id="e8dae-431">На кнопке **Построитель отчетов** нажмите кнопку **Сохранить как**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-431">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="e8dae-432">Перейдите на **Рабочий стол**, откройте папку **Мои документы**или **Мой компьютер**и перейдите в папку, в которую нужно сохранить отчет.</span><span class="sxs-lookup"><span data-stu-id="e8dae-432">Click **Desktop**, **My Documents**, or **My computer**, and then browse to the folder where you want to save the report.</span></span>  
  
3.  <span data-ttu-id="e8dae-433">В поле **Имя** замените имя по умолчанию на **Сводка сравнения продаж**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-433">In **Name**, replace the default name with **Sales Comparison Summary**.</span></span>  
  
4.  <span data-ttu-id="e8dae-434">Выберите команду **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e8dae-434">Click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8dae-435">См. также:</span><span class="sxs-lookup"><span data-stu-id="e8dae-435">See Also</span></span>  
 <span data-ttu-id="e8dae-436">[Выражения (построитель отчетов и службы SSRS)](report-design/expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e8dae-436">[Expressions &#40;Report Builder and SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e8dae-437">[Примеры выражений (построитель отчетов и службы SSRS)](report-design/expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e8dae-437">[Expression Examples &#40;Report Builder and SSRS&#41;](report-design/expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e8dae-438">[Индикаторы &#40;построитель отчетов и службы SSRS&#41;](report-design/indicators-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e8dae-438">[Indicators &#40;Report Builder and SSRS&#41;](report-design/indicators-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e8dae-439">[Изображения, текстовые поля, прямоугольники и линии &#40;построитель отчетов и SSRS&#41;](report-design/rectangles-and-lines-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e8dae-439">[Images, Text Boxes, Rectangles, and Lines &#40;Report Builder and SSRS&#41;](report-design/rectangles-and-lines-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e8dae-440">[Таблицы &#40;построитель отчетов и службы SSRS&#41;](report-design/tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e8dae-440">[Tables &#40;Report Builder  and SSRS&#41;](report-design/tables-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="e8dae-441">Добавление данных в построитель отчетов &#40;отчетов и SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e8dae-441">Add Data to a Report &#40;Report Builder and SSRS&#41;</span></span>](report-data/report-datasets-ssrs.md)  
  
  
