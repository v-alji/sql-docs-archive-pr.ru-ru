---
title: Занятие 2. Добавление данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 13c3a8cc-b1db-4aba-ad9b-038b7971be8d
author: minewiskan
ms.author: owend
ms.openlocfilehash: c844ea6558949407ca9b8206601ff7fe802ec399
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657378"
---
# <a name="lesson-2-add-data"></a><span data-ttu-id="79209-102">Урок 2. Добавление данных</span><span class="sxs-lookup"><span data-stu-id="79209-102">Lesson 2: Add Data</span></span>
  <span data-ttu-id="79209-103">На этом занятии будет использован мастер импорта таблиц в среде [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] для подключения к базе данных SQL AdventureWorksDW, выбора данных, предварительного просмотра и фильтрации данных и последующего импорта данных в рабочую область модели.</span><span class="sxs-lookup"><span data-stu-id="79209-103">In this lesson, you will use the Table Import Wizard in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] to connect to the AdventureWorksDW SQL database, select data, preview, and filter the data, and then import the data into your model workspace.</span></span>  
  
 <span data-ttu-id="79209-104">С помощью мастера импорта таблиц можно импортировать данные из разных реляционных источников: Access, SQL, Oracle, Sybase, Informix, DB2, Teradata и других.</span><span class="sxs-lookup"><span data-stu-id="79209-104">By using the Table Import Wizard, you can import data from a variety of relational sources: Access, SQL, Oracle, Sybase, Informix, DB2, Teradata, and more.</span></span> <span data-ttu-id="79209-105">Шаги по импорту данных из каждого из этих реляционных источников очень похожи на те, которые будут описаны ниже.</span><span class="sxs-lookup"><span data-stu-id="79209-105">The steps for importing data from each of these relational sources are very similar to what is described below.</span></span> <span data-ttu-id="79209-106">Кроме того, данные можно выбирать с помощью хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="79209-106">Additionally, data can be selected using a stored procedure.</span></span>  
  
 <span data-ttu-id="79209-107">Дополнительные сведения об импорте данных и различных типах источников данных, из которых можно выполнить импорт, см. в разделе [Источники данных (табличные службы SSAS)](data-sources-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="79209-107">To learn more about importing data and the different types of data sources you can import from, see [Data Sources &#40;SSAS Tabular&#41;](data-sources-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="79209-108">Предполагаемое время выполнения этого занятия: **20 минут**</span><span class="sxs-lookup"><span data-stu-id="79209-108">Estimated time to complete this lesson: **20 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="79209-109">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="79209-109">Prerequisites</span></span>  
 <span data-ttu-id="79209-110">Этот раздел входит в учебник по табличному моделированию, который следует изучать в предложенном порядке.</span><span class="sxs-lookup"><span data-stu-id="79209-110">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="79209-111">Перед выполнением задач на этом занятии необходимо завершить предыдущее занятие: [занятие 1. Создание нового проекта табличной модели](lesson-1-create-a-new-tabular-model-project.md).</span><span class="sxs-lookup"><span data-stu-id="79209-111">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 1: Create a New Tabular Model Project](lesson-1-create-a-new-tabular-model-project.md).</span></span>  
  
## <a name="create-a-connection"></a><span data-ttu-id="79209-112">Создание подключения</span><span class="sxs-lookup"><span data-stu-id="79209-112">Create a Connection</span></span>  
  
#### <a name="to-create-a-connection-to-a-the-adventureworksdw2012-database"></a><span data-ttu-id="79209-113">Создание соединения с базой данных AdventureWorksDW2012</span><span class="sxs-lookup"><span data-stu-id="79209-113">To create a connection to a the AdventureWorksDW2012 database</span></span>  
  
1.  <span data-ttu-id="79209-114">В среде [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]в меню **Модель** выберите пункт **Импорт из источника данных**.</span><span class="sxs-lookup"><span data-stu-id="79209-114">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click on the **Model** menu, and then click **Import from Data Source**.</span></span>  
  
     <span data-ttu-id="79209-115">Запустится мастер импорта таблиц, который поможет установить соединение с источником данных.</span><span class="sxs-lookup"><span data-stu-id="79209-115">This launches the Table Import Wizard which guides you through setting up a connection to a data source.</span></span> <span data-ttu-id="79209-116">Если пункт **Импортировать из источника данных** неактивен, щелкните дважды по файлу **Model.bim** в **Обозревателе решений** , чтобы открыть модель в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="79209-116">If **Import from Data Source** is greyed out, double click **Model.bim** in **Solution Explorer** to open the model in the designer.</span></span>  
  
2.  <span data-ttu-id="79209-117">В **Мастере импорта таблиц**под вкладкой **Реляционные базы данных**щелкните **Microsoft SQL Server**и затем щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="79209-117">In the **Table Import Wizard**, under **Relational Databases**, click **Microsoft SQL Server**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="79209-118">На странице **Подключение к Microsoft SQL Serverной базе данных** в поле **понятное имя соединения**введите `Adventure Works DB from SQL` .</span><span class="sxs-lookup"><span data-stu-id="79209-118">In the **Connect to a Microsoft SQL Server Database** page, in **Friendly Connection Name**, type `Adventure Works DB from SQL`.</span></span>  
  
4.  <span data-ttu-id="79209-119">В поле **Имя сервера**введите имя сервера, на котором установлена база данных AdventureWorksDW.</span><span class="sxs-lookup"><span data-stu-id="79209-119">In **Server name**, type the name of the server you installed the AdventureWorksDW database.</span></span>  
  
5.  <span data-ttu-id="79209-120">В поле **Имя базы данных** щелкните стрелку вниз, выберите базу данных **AdventureWorksDW**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="79209-120">In the **Database name** field, click the down arrow and select **AdventureWorksDW**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="79209-121">На странице **Сведения об олицетворении** нужно указать учетные данные, которые службы Analysis Services будут использовать для подключения к источнику данных во время импорта и обработки данных.</span><span class="sxs-lookup"><span data-stu-id="79209-121">In the **Impersonation Information** page, you need to specify the credentials Analysis Services will use to connect to the data source when importing and processing data.</span></span> <span data-ttu-id="79209-122">Убедитесь, что пункт **Имя и пароль определенного пользователя Windows** выбран, после чего в поле **Имя пользователя** и **Пароль**введите учетные данные для входа в систему Windows и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="79209-122">Verify **Specific Windows user name and password** is selected, and then in **User Name** and **Password**, enter your Windows logon credentials, and then click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="79209-123">Использование другой пользовательской учетной записи и пароля Windows обеспечивает наиболее безопасный метод подключения к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="79209-123">Using a Windows user account and password provides the most secure method of connecting to a data source.</span></span> <span data-ttu-id="79209-124">Дополнительные сведения см. в разделе [Олицетворение (табличные службы SSAS)](tabular-models/impersonation-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="79209-124">For more information, see [Impersonation &#40;SSAS Tabular&#41;](tabular-models/impersonation-ssas-tabular.md).</span></span>  
  
7.  <span data-ttu-id="79209-125">На странице **Выбор способа импорта данных** убедитесь, что пункт **Выбрать из списка таблиц и представлений данные для импорта** выбран.</span><span class="sxs-lookup"><span data-stu-id="79209-125">In the **Choose How to Import the Data** page, verify **Select from a list of tables and views to choose the data to import** is selected.</span></span> <span data-ttu-id="79209-126">Поскольку необходимо выбрать из списка таблиц и представлений, нажмите **Далее** , чтобы отобразить список всех исходных таблиц в базе данных-источнике.</span><span class="sxs-lookup"><span data-stu-id="79209-126">You want to select from a list of tables and views, so click **Next** to display a list of all the source tables in the source database.</span></span>  
  
8.  <span data-ttu-id="79209-127">На странице **Выбор таблиц и представлений** установите флажки напротив следующих таблиц: **DimCustomer**, **DimDate**, **DimGeography**, **DimProduct**, **DimProductCategory**, **DimProductSubcategory**и **FactInternetSales**.</span><span class="sxs-lookup"><span data-stu-id="79209-127">In the **Select Tables and Views** page, select the check box for the following tables: **DimCustomer**, **DimDate**, **DimGeography**, **DimProduct**, **DimProductCategory**, **DimProductSubcategory**, and **FactInternetSales**.</span></span>  
  
9. <span data-ttu-id="79209-128">Необходимо задать таблицам в модели более понятные имена.</span><span class="sxs-lookup"><span data-stu-id="79209-128">We want to give the tables in the model more easily understood names.</span></span> <span data-ttu-id="79209-129">Щелкните по ячейке в столбце **Понятное имя** для **DimCustomer**.</span><span class="sxs-lookup"><span data-stu-id="79209-129">Click on the cell in the **Friendly Name** column for **DimCustomer**.</span></span> <span data-ttu-id="79209-130">Переименуйте таблицу, удалив "Dim" из DimCustomer.</span><span class="sxs-lookup"><span data-stu-id="79209-130">Rename the table by removing "Dim" from DimCustomer.</span></span>  
  
10. <span data-ttu-id="79209-131">Переименуйте другие таблицы:</span><span class="sxs-lookup"><span data-stu-id="79209-131">Rename the other tables:</span></span>  
  
    |<span data-ttu-id="79209-132">Имя источника</span><span class="sxs-lookup"><span data-stu-id="79209-132">Source name</span></span>|<span data-ttu-id="79209-133">Понятное имя</span><span class="sxs-lookup"><span data-stu-id="79209-133">Friendly Name</span></span>|  
    |-----------------|-------------------|  
    |<span data-ttu-id="79209-134">DimDate</span><span class="sxs-lookup"><span data-stu-id="79209-134">DimDate</span></span>|<span data-ttu-id="79209-135">Дата</span><span class="sxs-lookup"><span data-stu-id="79209-135">Date</span></span>|  
    |<span data-ttu-id="79209-136">DimGeography</span><span class="sxs-lookup"><span data-stu-id="79209-136">DimGeography</span></span>|<span data-ttu-id="79209-137">Geography</span><span class="sxs-lookup"><span data-stu-id="79209-137">Geography</span></span>|  
    |<span data-ttu-id="79209-138">DimProduct</span><span class="sxs-lookup"><span data-stu-id="79209-138">DimProduct</span></span>|<span data-ttu-id="79209-139">Продукт</span><span class="sxs-lookup"><span data-stu-id="79209-139">Product</span></span>|  
    |<span data-ttu-id="79209-140">DimProductCategory</span><span class="sxs-lookup"><span data-stu-id="79209-140">DimProductCategory</span></span>|<span data-ttu-id="79209-141">Категория продуктов</span><span class="sxs-lookup"><span data-stu-id="79209-141">Product Category</span></span>|  
    |<span data-ttu-id="79209-142">DimProductSubcategory</span><span class="sxs-lookup"><span data-stu-id="79209-142">DimProductSubcategory</span></span>|<span data-ttu-id="79209-143">Подкатегория продукта</span><span class="sxs-lookup"><span data-stu-id="79209-143">Product Subcategory</span></span>|  
    |<span data-ttu-id="79209-144">FactInternetSales</span><span class="sxs-lookup"><span data-stu-id="79209-144">FactInternetSales</span></span>|<span data-ttu-id="79209-145">Internet Sales</span><span class="sxs-lookup"><span data-stu-id="79209-145">Internet Sales</span></span>|  
  
     <span data-ttu-id="79209-146">**НЕ** нажимайте кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="79209-146">**DO NOT** click **Finish**.</span></span>  
  
 <span data-ttu-id="79209-147">После того как соединение с базой данных установлено, выбраны таблицы для импорта и таблицам заданы понятные имена, перейдите к разделу занятия [Фильтрация данных таблицы перед импортом](#FilterData).</span><span class="sxs-lookup"><span data-stu-id="79209-147">Now that you have connected to the database, selected the tables to import, and given the tables friendly names, go to the next section, [Filter the Table Data prior to Importing](#FilterData).</span></span>  
  
##  <a name="filter-the-table-data"></a><a name="FilterData"></a><span data-ttu-id="79209-148">Фильтрация данных таблицы</span><span class="sxs-lookup"><span data-stu-id="79209-148">Filter the Table Data</span></span>  
 <span data-ttu-id="79209-149">Таблица DimCustomer, импортируемая из базы данных, содержит подмножество данных из исходной базы данных SQL Server Adventure Works.</span><span class="sxs-lookup"><span data-stu-id="79209-149">The DimCustomer table that you are importing from the database contains a subset of the data from the original SQL Server Adventure Works database.</span></span> <span data-ttu-id="79209-150">Некоторые из ненужных столбцов таблицы DimCustomer будут отфильтровываться.</span><span class="sxs-lookup"><span data-stu-id="79209-150">You will filter out some of the columns from the DimCustomer table that aren't necessary.</span></span> <span data-ttu-id="79209-151">По возможности нужно отфильтровать данные, которые не будут использоваться, чтобы сэкономить пространство памяти для модели.</span><span class="sxs-lookup"><span data-stu-id="79209-151">When possible, you will want to filter out data that will not be used in order to save in-memory space used by the model.</span></span>  
  
#### <a name="to-filter-the-table-data-prior-to-importing"></a><span data-ttu-id="79209-152">Фильтрация данных таблицы перед импортом</span><span class="sxs-lookup"><span data-stu-id="79209-152">To filter the table data prior to importing</span></span>  
  
1.  <span data-ttu-id="79209-153">Выберите строку для таблицы **Заказчик**, а затем нажмите кнопку **Просмотр и фильтрация**.</span><span class="sxs-lookup"><span data-stu-id="79209-153">Select the row for the **Customer** table, and then click **Preview & Filter**.</span></span> <span data-ttu-id="79209-154">Откроется окно **Предварительный просмотр выбранной таблицы** , в котором будут показаны все столбцы в таблице DimCustomer.</span><span class="sxs-lookup"><span data-stu-id="79209-154">The **Preview Selected Table** window opens with all the columns in the DimCustomer source table displayed.</span></span>  
  
2.  <span data-ttu-id="79209-155">Снимите флажки над следующими столбцами.</span><span class="sxs-lookup"><span data-stu-id="79209-155">Clear the checkbox at the top of the following columns:</span></span>  
  
    |<span data-ttu-id="79209-156">Customer</span><span class="sxs-lookup"><span data-stu-id="79209-156">Customer</span></span>|  
    |--------------|  
    |<span data-ttu-id="79209-157">**SpanishEducation**</span><span class="sxs-lookup"><span data-stu-id="79209-157">**SpanishEducation**</span></span>|  
    |<span data-ttu-id="79209-158">**FrenchEducation**</span><span class="sxs-lookup"><span data-stu-id="79209-158">**FrenchEducation**</span></span>|  
    |<span data-ttu-id="79209-159">**SpanishOccupation**</span><span class="sxs-lookup"><span data-stu-id="79209-159">**SpanishOccupation**</span></span>|  
    |<span data-ttu-id="79209-160">**FrenchOccupation**</span><span class="sxs-lookup"><span data-stu-id="79209-160">**FrenchOccupation**</span></span>|  
  
     <span data-ttu-id="79209-161">Поскольку значения для этих столбцов не являются актуальными для анализа интернет-продаж, нет необходимости их импортировать.</span><span class="sxs-lookup"><span data-stu-id="79209-161">Since the values for these columns are not relevant to Internet sales analysis, there is no need to import these columns.</span></span> <span data-ttu-id="79209-162">Если удалить ненужные столбцы, модель будет меньше.</span><span class="sxs-lookup"><span data-stu-id="79209-162">Eliminating unnecessary columns will make your model smaller.</span></span>  
  
3.  <span data-ttu-id="79209-163">Убедитесь, что флажки для всех остальных столбцов установлены, и нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="79209-163">Verify that all other columns are checked, and then click **OK**.</span></span>  
  
     <span data-ttu-id="79209-164">Обратите внимание, что слова **Примененные фильтры** теперь отображаются в столбце **сведения о фильтре** в строке **клиента** . Если щелкнуть эту ссылку, отобразится текстовое описание фильтров, которые вы только что применили.</span><span class="sxs-lookup"><span data-stu-id="79209-164">Notice the words **Applied filters** are now displayed in the **Filter Details** column in the **Customer** row; if you click on that link you'll see a text description of the filters you just applied.</span></span>  
  
4.  <span data-ttu-id="79209-165">Отфильтруйте оставшиеся таблицы, сняв флажки для следующих столбцов в каждой таблице:</span><span class="sxs-lookup"><span data-stu-id="79209-165">Filter the remaining tables by clearing the checkboxes for the following columns in each table:</span></span>  
  
    |<span data-ttu-id="79209-166">Дата</span><span class="sxs-lookup"><span data-stu-id="79209-166">Date</span></span>|  
    |----------|  
    |<span data-ttu-id="79209-167">**DateKey**</span><span class="sxs-lookup"><span data-stu-id="79209-167">**DateKey**</span></span>|  
    |<span data-ttu-id="79209-168">**SpanishDayNameOfWeek**</span><span class="sxs-lookup"><span data-stu-id="79209-168">**SpanishDayNameOfWeek**</span></span>|  
    |<span data-ttu-id="79209-169">**FrenchDayNameOfWeek**</span><span class="sxs-lookup"><span data-stu-id="79209-169">**FrenchDayNameOfWeek**</span></span>|  
    |<span data-ttu-id="79209-170">**SpanishMonthName**</span><span class="sxs-lookup"><span data-stu-id="79209-170">**SpanishMonthName**</span></span>|  
    |<span data-ttu-id="79209-171">**FrenchMonthName**</span><span class="sxs-lookup"><span data-stu-id="79209-171">**FrenchMonthName**</span></span>|  
  
    |<span data-ttu-id="79209-172">Geography</span><span class="sxs-lookup"><span data-stu-id="79209-172">Geography</span></span>|  
    |---------------|  
    |<span data-ttu-id="79209-173">**SpanishCountryRegionName**</span><span class="sxs-lookup"><span data-stu-id="79209-173">**SpanishCountryRegionName**</span></span>|  
    |<span data-ttu-id="79209-174">**FrenchCountryRegionName**</span><span class="sxs-lookup"><span data-stu-id="79209-174">**FrenchCountryRegionName**</span></span>|  
    |<span data-ttu-id="79209-175">**IpAddressLocator**</span><span class="sxs-lookup"><span data-stu-id="79209-175">**IpAddressLocator**</span></span>|  
  
    |<span data-ttu-id="79209-176">Продукт</span><span class="sxs-lookup"><span data-stu-id="79209-176">Product</span></span>|  
    |-------------|  
    |<span data-ttu-id="79209-177">**SpanishProductName**</span><span class="sxs-lookup"><span data-stu-id="79209-177">**SpanishProductName**</span></span>|  
    |<span data-ttu-id="79209-178">**FrenchProductName**</span><span class="sxs-lookup"><span data-stu-id="79209-178">**FrenchProductName**</span></span>|  
    |<span data-ttu-id="79209-179">**FrenchDescription**</span><span class="sxs-lookup"><span data-stu-id="79209-179">**FrenchDescription**</span></span>|  
    |<span data-ttu-id="79209-180">**ChineseDescription**</span><span class="sxs-lookup"><span data-stu-id="79209-180">**ChineseDescription**</span></span>|  
    |<span data-ttu-id="79209-181">**ArabicDescription**</span><span class="sxs-lookup"><span data-stu-id="79209-181">**ArabicDescription**</span></span>|  
    |<span data-ttu-id="79209-182">**HebrewDescription**</span><span class="sxs-lookup"><span data-stu-id="79209-182">**HebrewDescription**</span></span>|  
    |<span data-ttu-id="79209-183">**ThaiDescription**</span><span class="sxs-lookup"><span data-stu-id="79209-183">**ThaiDescription**</span></span>|  
    |<span data-ttu-id="79209-184">**GermanDescription**</span><span class="sxs-lookup"><span data-stu-id="79209-184">**GermanDescription**</span></span>|  
    |<span data-ttu-id="79209-185">**JapaneseDescription**</span><span class="sxs-lookup"><span data-stu-id="79209-185">**JapaneseDescription**</span></span>|  
    |<span data-ttu-id="79209-186">**TurkishDescription**</span><span class="sxs-lookup"><span data-stu-id="79209-186">**TurkishDescription**</span></span>|  
  
    |<span data-ttu-id="79209-187">Категория продуктов</span><span class="sxs-lookup"><span data-stu-id="79209-187">Product Category</span></span>|  
    |----------------------|  
    |<span data-ttu-id="79209-188">**SpanishProductCategoryName**</span><span class="sxs-lookup"><span data-stu-id="79209-188">**SpanishProductCategoryName**</span></span>|  
    |<span data-ttu-id="79209-189">**FrenchProductCategoryName**</span><span class="sxs-lookup"><span data-stu-id="79209-189">**FrenchProductCategoryName**</span></span>|  
  
    |<span data-ttu-id="79209-190">Подкатегория продукта</span><span class="sxs-lookup"><span data-stu-id="79209-190">Product Subcategory</span></span>|  
    |-------------------------|  
    |<span data-ttu-id="79209-191">**SpanishProductSubcategoryName**</span><span class="sxs-lookup"><span data-stu-id="79209-191">**SpanishProductSubcategoryName**</span></span>|  
    |<span data-ttu-id="79209-192">**FrenchProductSubcategoryName**</span><span class="sxs-lookup"><span data-stu-id="79209-192">**FrenchProductSubcategoryName**</span></span>|  
  
    |<span data-ttu-id="79209-193">Internet Sales</span><span class="sxs-lookup"><span data-stu-id="79209-193">Internet Sales</span></span>|  
    |--------------------|  
    |<span data-ttu-id="79209-194">**OrderDateKey**</span><span class="sxs-lookup"><span data-stu-id="79209-194">**OrderDateKey**</span></span>|  
    |<span data-ttu-id="79209-195">**DueDateKey**</span><span class="sxs-lookup"><span data-stu-id="79209-195">**DueDateKey**</span></span>|  
    |<span data-ttu-id="79209-196">**ShipDateKey**</span><span class="sxs-lookup"><span data-stu-id="79209-196">**ShipDateKey**</span></span>|  
  
 <span data-ttu-id="79209-197">После предварительного просмотра и фильтрации ненужных данных можно выполнить импорт данных.</span><span class="sxs-lookup"><span data-stu-id="79209-197">Now that you have previewed and filtered out unnecessary data, you can import the data.</span></span> <span data-ttu-id="79209-198">Перейдите к следующему разделу **Импорт данных выбранных таблиц и столбцов**.</span><span class="sxs-lookup"><span data-stu-id="79209-198">Go to the next section **Import the Selected Tables and Column Data**.</span></span>  
  
##  <a name="import-the-selected-tables-and-column-data"></a><a name="Import"></a><span data-ttu-id="79209-199">Импорт выбранных таблиц и данных столбцов</span><span class="sxs-lookup"><span data-stu-id="79209-199">Import the Selected Tables and Column Data</span></span>  
 <span data-ttu-id="79209-200">Теперь можно импортировать выбранные данные.</span><span class="sxs-lookup"><span data-stu-id="79209-200">You can now import the selected data.</span></span> <span data-ttu-id="79209-201">Мастер импортирует данные таблицы вместе со всеми связями между таблицами.</span><span class="sxs-lookup"><span data-stu-id="79209-201">The wizard imports the table data along with any relationships between tables.</span></span> <span data-ttu-id="79209-202">Новые таблицы и столбцы создаются в модели с использованием указанных понятных имен; отфильтрованные ранее данные не будут импортированы.</span><span class="sxs-lookup"><span data-stu-id="79209-202">New tables and columns are created in the model using the friendly names you specified, and data that you filtered out will not be imported.</span></span>  
  
#### <a name="to-import-the-selected-tables-and-column-data"></a><span data-ttu-id="79209-203">Чтобы импортировать данные из выбранных таблиц и столбцов, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="79209-203">To import the selected tables and column data</span></span>  
  
1.  <span data-ttu-id="79209-204">Просмотрите выбранные параметры.</span><span class="sxs-lookup"><span data-stu-id="79209-204">Review your selections.</span></span> <span data-ttu-id="79209-205">Если все верно, нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="79209-205">If everything looks OK, click **Finish**.</span></span>  
  
     <span data-ttu-id="79209-206">При импорте данных мастер отображает количество выбранных строк.</span><span class="sxs-lookup"><span data-stu-id="79209-206">While importing the data, the wizard displays how many rows have been fetched.</span></span> <span data-ttu-id="79209-207">После импорта всех данных отображается сообщение, указывающее на успешное завершение процесса.</span><span class="sxs-lookup"><span data-stu-id="79209-207">When all the data has been imported, a message indicating success is displayed.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="79209-208"> Для просмотра связей, которые были автоматически созданы между импортированными таблицами, в строке **Подготовка данных** щелкните **Подробные сведения**.</span><span class="sxs-lookup"><span data-stu-id="79209-208">To see the relationships that were automatically created between the imported tables, on the **Data preparation** row, click **Details**.</span></span>  
  
2.  <span data-ttu-id="79209-209">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="79209-209">Click **Close**.</span></span>  
  
     <span data-ttu-id="79209-210">Мастер закроется, и появится конструктор моделей.</span><span class="sxs-lookup"><span data-stu-id="79209-210">The wizard closes and the model designer is visible.</span></span> <span data-ttu-id="79209-211">Каждая таблица была добавлена в конструктор моделей как новая вкладка.</span><span class="sxs-lookup"><span data-stu-id="79209-211">Each table has been added as a new tab in the model designer.</span></span>  
  
## <a name="save-the-model-project"></a><span data-ttu-id="79209-212">Сохранение проекта модели</span><span class="sxs-lookup"><span data-stu-id="79209-212">Save the Model Project</span></span>  
 <span data-ttu-id="79209-213">Важно часто сохранять проект модели.</span><span class="sxs-lookup"><span data-stu-id="79209-213">It is important to frequently save your model project.</span></span>  
  
#### <a name="to-save-the-model-project"></a><span data-ttu-id="79209-214">Чтобы сохранить проект модели, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="79209-214">To save the model project</span></span>  
  
-   <span data-ttu-id="79209-215">В среде [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]щелкните меню **Файл** и выберите команду **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="79209-215">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click on the **File** menu, and then click **Save All**.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="79209-216">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="79209-216">Next Step</span></span>  
 <span data-ttu-id="79209-217">Чтобы продолжить изучение этого учебника, перейдите к следующему занятию: [Занятие 3. Переименование столбцов](rename-columns.md).</span><span class="sxs-lookup"><span data-stu-id="79209-217">To continue this tutorial, go to the next lesson: [Lesson 3: Rename Columns](rename-columns.md).</span></span>  
  
  
