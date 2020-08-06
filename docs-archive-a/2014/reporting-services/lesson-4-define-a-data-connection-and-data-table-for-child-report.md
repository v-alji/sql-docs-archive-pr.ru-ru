---
title: Занятие 4. Определение подключения к данным и таблицы данных для дочернего отчета | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a6aa2c56-227c-43c5-a28e-c7104131ac5e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6d9144d960ad933afa65f9d4483e96b5f732d944
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656226"
---
# <a name="lesson-4-define-a-data-connection-and-data-table-for-child-report"></a><span data-ttu-id="bdd76-102">Занятие 4. Определение подключения к данным и таблицы данных для родительского отчета</span><span class="sxs-lookup"><span data-stu-id="bdd76-102">Lesson 4: Define a Data Connection and Data Table for Child Report</span></span>
  <span data-ttu-id="bdd76-103">После проектирования родительского отчета далее необходимо создать подключение к данным и таблицу данных для дочернего отчета.</span><span class="sxs-lookup"><span data-stu-id="bdd76-103">After you design the parent report, you next step is to create a data connection and a data table for the child report.</span></span> <span data-ttu-id="bdd76-104">В этом учебнике в качестве источника подключения к данным используется база данных AdventureWorks2008.</span><span class="sxs-lookup"><span data-stu-id="bdd76-104">In this tutorial the data connection is to the AdventureWorks2008 database.</span></span> <span data-ttu-id="bdd76-105">Предусмотрена также возможность установить подключение к базе данных AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="bdd76-105">You also have the option of connecting to the AdventureWorks2012 database.</span></span>  
  
### <a name="to-define-a-data-connection-and-datatable-by-adding-a-dataset-for-child-report"></a><span data-ttu-id="bdd76-106">Определение подключения к данным и таблицы данных путем добавления набора данных (для дочернего отчета)</span><span class="sxs-lookup"><span data-stu-id="bdd76-106">To define a data connection and DataTable by adding a DataSet (for child report)</span></span>  
  
1.  <span data-ttu-id="bdd76-107">В меню **веб-сайт** выберите команду **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="bdd76-107">On the **Website** menu, click **Add New Item**.</span></span>  
  
2.  <span data-ttu-id="bdd76-108">В диалоговом окне **Добавление нового элемента** выберите **набор данных** и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="bdd76-108">In the **Add New Item** dialog box, click **DataSet** and then click **Add**.</span></span> <span data-ttu-id="bdd76-109">При появлении запроса необходимо добавить элемент в папку **App_Code** , нажав кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="bdd76-109">When prompted, you should add the item to the **App_Code** folder by clicking **Yes**.</span></span>  
  
     <span data-ttu-id="bdd76-110">В результате произойдет добавление нового XSD-файла **DataSet2.xsd** к проекту и откроется конструктор набора данных.</span><span class="sxs-lookup"><span data-stu-id="bdd76-110">This adds a new XSD file **DataSet2.xsd** to the project and opens the DataSet Designer.</span></span>  
  
3.  <span data-ttu-id="bdd76-111">Из окна "Панель элементов" перетащите элемент управления **TableAdapter** в рабочую область конструирования.</span><span class="sxs-lookup"><span data-stu-id="bdd76-111">From the Toolbox window, drag a **TableAdapter** control to the design surface.</span></span> <span data-ttu-id="bdd76-112">Запустится мастер настройки **TableAdapter** .</span><span class="sxs-lookup"><span data-stu-id="bdd76-112">This launches the **TableAdapter** Configuration Wizard.</span></span>  
  
4.  <span data-ttu-id="bdd76-113">На странице **Выбор подключения к данным** нажмите кнопку **создать подключение**.</span><span class="sxs-lookup"><span data-stu-id="bdd76-113">On the **Choose Your Data Connection** page, click **New Connection**.</span></span>  
  
5.  <span data-ttu-id="bdd76-114">В диалоговом окне **Добавление подключения** выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="bdd76-114">In the **Add Connection** dialog box, perform the following steps:</span></span>  
  
    1.  <span data-ttu-id="bdd76-115">В поле **имя сервера** введите сервер, на котором расположена база данных **AdventureWorks2008** .</span><span class="sxs-lookup"><span data-stu-id="bdd76-115">In the **Server name** box, enter the server where the **AdventureWorks2008** database is located.</span></span>  
  
         <span data-ttu-id="bdd76-116">Экземпляром SQL Server Express по умолчанию является **(local)\sqlexpress**.</span><span class="sxs-lookup"><span data-stu-id="bdd76-116">The default SQL Server Express instance is **(local)\sqlexpress**.</span></span>  
  
    2.  <span data-ttu-id="bdd76-117">В разделе **Вход на сервер** выберите параметр, который предоставляет доступ к данным.</span><span class="sxs-lookup"><span data-stu-id="bdd76-117">In the **Log on to the server** section, select the option that provides you access to the data.</span></span> <span data-ttu-id="bdd76-118">По умолчанию установлен параметр**Использовать проверку подлинности Windows** .</span><span class="sxs-lookup"><span data-stu-id="bdd76-118">**Use Windows Authentication** is the default.</span></span>  
  
    3.  <span data-ttu-id="bdd76-119">В раскрывающемся списке **выберите или введите имя базы данных** щелкните **AdventureWorks2008**.</span><span class="sxs-lookup"><span data-stu-id="bdd76-119">From the **Select or enter a database name** drop-down list, click **AdventureWorks2008**.</span></span>  
  
    4.  <span data-ttu-id="bdd76-120">Нажмите кнопку **ОК** и затем кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="bdd76-120">Click **OK**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="bdd76-121">Если в шаге 5 (b) был выбран вариант **Использовать проверку подлинности SQL Server** , выберите включение конфиденциальных данных в строку или задание этих сведений в коде приложения.</span><span class="sxs-lookup"><span data-stu-id="bdd76-121">If you selected **Use SQL Server Authentication** in Step 5 (b), select the option whether to include the sensitive data in the string or set the information in your application code.</span></span>  
  
7.  <span data-ttu-id="bdd76-122">На странице **Сохранение строки подключения в файле конфигурации приложения** введите имя строки подключения или примите **AdventureWorks2008ConnectionString**по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bdd76-122">On the **Save the Connection String to the Application Configuration File** page, type in the name for the connection string or accept the default **AdventureWorks2008ConnectionString**.</span></span> <span data-ttu-id="bdd76-123">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="bdd76-123">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="bdd76-124">На странице **Выбор типа команды** выберите команду **использовать инструкции SQL**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="bdd76-124">On the **Choose a Command Type** page, select **Use SQL Statements**, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="bdd76-125">На странице **Ввод инструкции SQL** введите следующий запрос TRANSACT-SQL для получения данных из базы данных **AdventureWorks2008** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="bdd76-125">On the **Enter a SQL Statement** page, enter the following Transact-SQL query to retrieve data from the **AdventureWorks2008** database, and then click **Next**.</span></span>  
  
    ```  
    SELECT PurchaseOrderID, PurchaseOrderDetailID, OrderQty, ProductID, ReceivedQty, RejectedQty, StockedQty FROM Purchasing.PurchaseOrderDetail  
    ```  
  
     <span data-ttu-id="bdd76-126">Можно также создать запрос, нажав кнопку **конструктор запросов**, а затем проверить запрос, нажав кнопку **выполнить запрос** .</span><span class="sxs-lookup"><span data-stu-id="bdd76-126">You can also create the query by clicking **Query Builder**, and then verify the query by clicking **Execute Query** button.</span></span> <span data-ttu-id="bdd76-127">Если запрос не возвращает ожидаемые данные, возможно, используется более ранняя версия AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="bdd76-127">If the query does not return the expected data, you might be using an earlier version of AdventureWorks.</span></span> <span data-ttu-id="bdd76-128">Дополнительные сведения об установке версии **AdventureWorks2008** AdventureWorks см. [в разделе Пошаговое руководство. Установка базы данных AdventureWorks](https://msdn.microsoft.com/library/aa992075\(v=vs.100\).aspx).</span><span class="sxs-lookup"><span data-stu-id="bdd76-128">For more information about installing the **AdventureWorks2008** version of AdventureWorks, see [Walkthrough: Installing the AdventureWorks Database](https://msdn.microsoft.com/library/aa992075\(v=vs.100\).aspx).</span></span>  
  
10. <span data-ttu-id="bdd76-129">На странице **Выбор методов для создания** снимите флажок **создать методы для отправки обновлений непосредственно в базу данных (GenerateDBDirectMethods)**, а затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="bdd76-129">On the **Choose Methods to Generate** page, uncheck **Create methods to send updates directly to the database (GenerateDBDirectMethods)**, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="bdd76-130">Теперь вы завершили настройку [datatable](https://msdn.microsoft.com/library/system.data.datatable\(v=vs.100\).aspx) ADO.NET в качестве источника данных для отчета.</span><span class="sxs-lookup"><span data-stu-id="bdd76-130">You have now completed configuring the ADO.NET [DataTable](https://msdn.microsoft.com/library/system.data.datatable\(v=vs.100\).aspx) as data source for your report.</span></span> <span data-ttu-id="bdd76-131">На странице конструктора набора данных в Visual Studio появится добавленный объект **DataTable** со списком столбцов, указанных в запросе.</span><span class="sxs-lookup"><span data-stu-id="bdd76-131">On the DataSet Designer page in Visual Studio, you should see the **DataTable** you added, listing the columns specified in the query.</span></span> <span data-ttu-id="bdd76-132">Набор данных DataSet2 содержит данные таблицы PurhcaseOrderDetail, указанные в запросе.</span><span class="sxs-lookup"><span data-stu-id="bdd76-132">DataSet2 contains the data from the PurhcaseOrderDetail table, based on the query.</span></span>  
  
11. <span data-ttu-id="bdd76-133">Сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="bdd76-133">Save the file.</span></span>  
  
12. <span data-ttu-id="bdd76-134">Для предварительного просмотра данных выберите пункт **Предварительный просмотр данных** в меню **данные** , а затем щелкните **Предварительный просмотр**.</span><span class="sxs-lookup"><span data-stu-id="bdd76-134">To preview the data, click **Preview Data** on the **Data** menu, and then click **Preview**.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="bdd76-135">Следующая задача</span><span class="sxs-lookup"><span data-stu-id="bdd76-135">Next Task</span></span>  
 <span data-ttu-id="bdd76-136">Тем самым были успешно созданы подключение к данным и таблица данных для дочернего отчета.</span><span class="sxs-lookup"><span data-stu-id="bdd76-136">You have successfully created a data connection and data table for the child report.</span></span> <span data-ttu-id="bdd76-137">Затем необходимо спроектировать дочерний отчет с использованием мастера отчетов.</span><span class="sxs-lookup"><span data-stu-id="bdd76-137">Next, you will design the child report using the Report Wizard.</span></span>  
  
  
