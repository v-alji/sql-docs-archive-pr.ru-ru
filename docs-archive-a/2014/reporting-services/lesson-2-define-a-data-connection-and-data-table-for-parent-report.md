---
title: Занятие 2. Определение подключения к данным и таблицы данных для родительского отчета | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f02dee0c-85ad-45d4-b707-10e9e8541db9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 045ff576061bf12d163668cb9a57651e591768a4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655547"
---
# <a name="lesson-2-define-a-data-connection-and-data-table-for-parent-report"></a><span data-ttu-id="78952-102">Занятие 2. Определение подключения к данным и таблицы данных для родительского отчета</span><span class="sxs-lookup"><span data-stu-id="78952-102">Lesson 2: Define a Data Connection and Data Table for Parent Report</span></span>
  <span data-ttu-id="78952-103">После создания нового проекта веб-сайта с использованием шаблона веб-сайта ASP.NET для Visual C# далее необходимо создать подключение к данным и таблицу данных для родительского отчета.</span><span class="sxs-lookup"><span data-stu-id="78952-103">After you create a new website project using the ASP.NET website template for Visual C#, your next step is to create a data connection and a data table for the parent report.</span></span> <span data-ttu-id="78952-104">В этом учебнике в качестве источника подключения к данным используется база данных AdventureWorks2008.</span><span class="sxs-lookup"><span data-stu-id="78952-104">In this tutorial the data connection is to the AdventureWorks2008 database.</span></span> <span data-ttu-id="78952-105">Предусмотрена также возможность установить подключение к базе данных AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="78952-105">You also have the option of connecting to the AdventureWorks2012 database.</span></span>  
  
### <a name="to-define-a-data-connection-and-data-table-by-adding-a-dataset-for-parent-report"></a><span data-ttu-id="78952-106">Определение подключения к данным и таблицы данных путем добавления набора данных (для родительского отчета)</span><span class="sxs-lookup"><span data-stu-id="78952-106">To define a data connection and Data Table by adding a DataSet (for parent report)</span></span>  
  
1.  <span data-ttu-id="78952-107">В меню **Веб-сайт** выберите команду **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="78952-107">On the **Website** menu, select **Add New Item**.</span></span>  
  
2.  <span data-ttu-id="78952-108">В диалоговом окне **Добавление нового элемента** выберите **набор данных** и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="78952-108">In the **Add New Item** dialog box, select **DataSet** and click **Add**.</span></span> <span data-ttu-id="78952-109">При появлении запроса необходимо добавить элемент в папку **App_Code** , нажав кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="78952-109">When prompted you should add the item to the **App_Code** folder by clicking **Yes**.</span></span>  
  
     <span data-ttu-id="78952-110">В результате к проекту добавляется новый XSD-файл **DataSet1.xsd** и открывается конструктор набора данных.</span><span class="sxs-lookup"><span data-stu-id="78952-110">This adds a new XSD file **DataSet1.xsd** to the project and opens the DataSet Designer.</span></span>  
  
3.  <span data-ttu-id="78952-111">Из окна Панель элементов перетащите элемент управления **[TableAdapter](https://msdn.microsoft.com/library/bz9tthwx\(v=vs.100\).aspx)** в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="78952-111">From the Toolbox window, drag a **[TableAdapter](https://msdn.microsoft.com/library/bz9tthwx\(v=vs.100\).aspx)** control to the design surface.</span></span> <span data-ttu-id="78952-112">Запустится мастер настройки **TableAdapter** .</span><span class="sxs-lookup"><span data-stu-id="78952-112">This launches the **TableAdapter** Configuration Wizard.</span></span>  
  
4.  <span data-ttu-id="78952-113">На странице **Выбор подключения к данным** нажмите кнопку **создать подключение**.</span><span class="sxs-lookup"><span data-stu-id="78952-113">On the **Choose Your Data Connection** page, click **New Connection**.</span></span>  
  
5.  <span data-ttu-id="78952-114">Если вы впервые создали источник данных в Visual Studio, отобразится страница **Выбор источника данных** .</span><span class="sxs-lookup"><span data-stu-id="78952-114">If this is the first time you've created a data source in Visual Studio, you will see the **Choose Data Source** page.</span></span> <span data-ttu-id="78952-115">В поле **Источник данных** выберите **Microsoft SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="78952-115">In the **Data Source** box, select **Microsoft SQL Server**.</span></span>  
  
6.  <span data-ttu-id="78952-116">В диалоговом окне **Добавление подключения** выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="78952-116">In the **Add Connection** dialog box, perform the following steps:</span></span>  
  
    1.  <span data-ttu-id="78952-117">В поле **имя сервера** введите сервер, на котором расположена база данных **AdventureWorks2008** .</span><span class="sxs-lookup"><span data-stu-id="78952-117">In the **Server name** box, enter the server where the **AdventureWorks2008** database is located.</span></span>  
  
         <span data-ttu-id="78952-118">Экземпляром SQL Server Express по умолчанию является **(local)\sqlexpress**.</span><span class="sxs-lookup"><span data-stu-id="78952-118">The default SQL Server Express instance is **(local)\sqlexpress**.</span></span>  
  
    2.  <span data-ttu-id="78952-119">В разделе **Вход на сервер** выберите параметр, который предоставляет доступ к данным.</span><span class="sxs-lookup"><span data-stu-id="78952-119">In the **Log on to the server** section, select the option that provides you access to the data.</span></span> <span data-ttu-id="78952-120">По умолчанию установлен параметр**Использовать проверку подлинности Windows** .</span><span class="sxs-lookup"><span data-stu-id="78952-120">**Use Windows Authentication** is the default.</span></span>  
  
    3.  <span data-ttu-id="78952-121">В раскрывающемся списке **выберите или введите имя базы данных** щелкните **AdventureWorks2008**.</span><span class="sxs-lookup"><span data-stu-id="78952-121">From the **Select or enter a database name** drop-down list, click **AdventureWorks2008**.</span></span>  
  
    4.  <span data-ttu-id="78952-122">Нажмите кнопку **ОК** и затем кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="78952-122">Click **OK**, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="78952-123">Если в шаге 6 (b) был выбран вариант **Использовать проверку подлинности SQL Server** , выберите включение конфиденциальных данных в строку или задание этих сведений в коде приложения.</span><span class="sxs-lookup"><span data-stu-id="78952-123">If you selected **Use SQL Server Authentication** in the Step 6 (b), select the option whether to include the sensitive data in the string or set the information in your application code.</span></span>  
  
8.  <span data-ttu-id="78952-124">На странице **Сохранение строки подключения в файле конфигурации приложения** введите имя строки подключения или примите **AdventureWorks2008ConnectionString**по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="78952-124">On the **Save the Connection String to the Application Configuration File** page, type in the name for the connection string or accept the default **AdventureWorks2008ConnectionString**.</span></span> <span data-ttu-id="78952-125">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="78952-125">Click **Next**.</span></span>  
  
9. <span data-ttu-id="78952-126">На странице **Выбор типа команды** выберите команду **использовать инструкции SQL**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="78952-126">On the **Choose a Command Type** page, select **Use SQL Statements**, and then click **Next**.</span></span>  
  
10. <span data-ttu-id="78952-127">На странице **Ввод инструкции SQL** введите следующий запрос TRANSACT-SQL для получения данных из базы данных **AdventureWorks2008** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="78952-127">On the **Enter a SQL Statement** page, enter the following Transact-SQL query to retrieve data from the **AdventureWorks2008** database, and then click **Next**.</span></span>  
  
    ```  
    SELECT ProductID, Name, ProductNumber, SafetyStockLevel, ReorderPoint FROM  Production.Product Order By ProductID  
    ```  
  
     <span data-ttu-id="78952-128">Можно также создать запрос, нажав кнопку **конструктор запросов**, а затем проверить запрос, нажав кнопку **выполнить запрос**.</span><span class="sxs-lookup"><span data-stu-id="78952-128">You can also create the query by clicking **Query Builder**, and then verify the query by clicking **Execute Query**.</span></span> <span data-ttu-id="78952-129">Если запрос не возвращает ожидаемые данные, возможно, используется более ранняя версия AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="78952-129">If the query does not return the expected data, you might be using an earlier version of AdventureWorks.</span></span> <span data-ttu-id="78952-130">Дополнительные сведения об установке версии **AdventureWorks2008** AdventureWorks см. [в разделе Пошаговое руководство. Установка базы данных AdventureWorks](https://msdn.microsoft.com/library/aa992075\(v=vs.100\).aspx).</span><span class="sxs-lookup"><span data-stu-id="78952-130">For more information about installing the **AdventureWorks2008** version of AdventureWorks, see [Walkthrough: Installing the AdventureWorks Database](https://msdn.microsoft.com/library/aa992075\(v=vs.100\).aspx).</span></span>  
  
11. <span data-ttu-id="78952-131">На странице **Выбор методов для создания** установите флажок **создать методы для отправки обновлений непосредственно в базу данных (GenerateDBDirectMethods)**, а затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="78952-131">On the **Choose Methods to Generate** page, be sure to uncheck **Create methods to send updates directly to the database (GenerateDBDirectMethods)**, and then click **Finish**.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="78952-132">Обязательно снимите флажок «Создать»</span><span class="sxs-lookup"><span data-stu-id="78952-132">Be sure to uncheck Create</span></span>  
  
     <span data-ttu-id="78952-133">На этом настройка объекта DataTable ADO.NET в качестве источника данных для отчета завершена.</span><span class="sxs-lookup"><span data-stu-id="78952-133">You have now completed configuring the ADO.NET DataTable object as the data source for your report.</span></span> <span data-ttu-id="78952-134">На странице конструктора набора данных в Visual Studio появится добавленный объект DataTable со списком столбцов, указанных в запросе.</span><span class="sxs-lookup"><span data-stu-id="78952-134">On the DataSet Designer page in Visual Studio, you should see the DataTable object you added, listing the columns specified in the query.</span></span> <span data-ttu-id="78952-135">Набор данных DataSet1 содержит данные таблицы Product, полученные с помощью запроса.</span><span class="sxs-lookup"><span data-stu-id="78952-135">DataSet1 contains the data from the Product table, based on the query.</span></span>  
  
12. <span data-ttu-id="78952-136">Сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="78952-136">Save the file.</span></span>  
  
13. <span data-ttu-id="78952-137">Для предварительного просмотра данных выберите пункт **Предварительный просмотр данных** в меню **данные** , а затем щелкните **Предварительный просмотр**.</span><span class="sxs-lookup"><span data-stu-id="78952-137">To preview the data, click **Preview Data** on the **Data** menu, and then click **Preview**.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="78952-138">Следующая задача</span><span class="sxs-lookup"><span data-stu-id="78952-138">Next Task</span></span>  
 <span data-ttu-id="78952-139">Тем самым были успешно созданы подключение к данным и таблица данных для родительского отчета.</span><span class="sxs-lookup"><span data-stu-id="78952-139">You have successfully created a data connection and a data table for the parent report.</span></span> <span data-ttu-id="78952-140">Затем необходимо спроектировать родительский отчет с использованием мастера отчетов.</span><span class="sxs-lookup"><span data-stu-id="78952-140">Next, you will design the parent report using the Report Wizard.</span></span>  
  
  
