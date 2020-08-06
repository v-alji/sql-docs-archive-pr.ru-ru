---
title: Занятие 11. Создание секций | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 92eb21a8-5fc4-4999-ad37-1332ce26431d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4db5edd5d47fe424ef6e6ad2a822106110209059
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654562"
---
# <a name="lesson-11-create-partitions"></a><span data-ttu-id="25c87-102">Урок 11. Создание секций</span><span class="sxs-lookup"><span data-stu-id="25c87-102">Lesson 11: Create Partitions</span></span>
  <span data-ttu-id="25c87-103">На этом занятии мы создадим секции для разделения таблицы интернет-продаж на более мелкие логические части, которые могут быть обработаны (обновлены) независимо от других секций.</span><span class="sxs-lookup"><span data-stu-id="25c87-103">In this lesson, you will create partitions to divide the Internet Sales table into smaller logical parts that can be processed (Refreshed) independent of other partitions.</span></span> <span data-ttu-id="25c87-104">По умолчанию каждая таблица, включенная в модель, содержит одну секцию, включающую все столбцы и строки таблицы.</span><span class="sxs-lookup"><span data-stu-id="25c87-104">By default, every table you include in your model has one partition which includes all of the table's columns and rows.</span></span> <span data-ttu-id="25c87-105">Для таблицы Sales Интернет необходимо разделить данные по годам; один раздел для каждой из пяти лет таблицы.</span><span class="sxs-lookup"><span data-stu-id="25c87-105">For the Internet Sales table, we want to divide the data by year; one partition for each of the table's five years.</span></span>  <span data-ttu-id="25c87-106">После этого каждую секцию можно обработать независимо.</span><span class="sxs-lookup"><span data-stu-id="25c87-106">Each partition can then be processed independently.</span></span> <span data-ttu-id="25c87-107">Дополнительные сведения см. в разделе [Секции (табличные службы SSAS)](tabular-models/partitions-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="25c87-107">To learn more, see [Partitions &#40;SSAS Tabular&#41;](tabular-models/partitions-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="25c87-108">Предполагаемое время выполнения этого занятия: **15 минут**</span><span class="sxs-lookup"><span data-stu-id="25c87-108">Estimated time to complete this lesson: **15 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="25c87-109">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="25c87-109">Prerequisites</span></span>  
 <span data-ttu-id="25c87-110">Этот раздел входит в учебник по табличному моделированию, который следует изучать в предложенном порядке.</span><span class="sxs-lookup"><span data-stu-id="25c87-110">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="25c87-111">Прежде чем выполнять задания в этом занятии, необходимо завершить предыдущее занятие: [Занятие 10. Создание иерархий](lesson-9-create-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="25c87-111">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 10: Create Hierarchies](lesson-9-create-hierarchies.md).</span></span>  
  
## <a name="create-partitions"></a><span data-ttu-id="25c87-112">Создание секций</span><span class="sxs-lookup"><span data-stu-id="25c87-112">Create Partitions</span></span>  
  
#### <a name="to-create-partitions-in-the-internet-sales-table"></a><span data-ttu-id="25c87-113">Создание секций в таблице интернет-продаж</span><span class="sxs-lookup"><span data-stu-id="25c87-113">To create partitions in the Internet Sales table</span></span>  
  
1.  <span data-ttu-id="25c87-114">В конструкторе моделей щелкните таблицу **Интернет-продажи** , а затем откройте меню **Таблица** и выберите пункт **Секции**.</span><span class="sxs-lookup"><span data-stu-id="25c87-114">In the model designer, click on the **Internet Sales** table, then click on the **Table** menu, and then click **Partitions**.</span></span>  
  
     <span data-ttu-id="25c87-115">Откроется диалоговое окно **Диспетчер секций** .</span><span class="sxs-lookup"><span data-stu-id="25c87-115">The **Partition Manager** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="25c87-116">В диалоговом окне **Диспетчер секций** в разделе **Секции**щелкните раздел **продажи через Интернет** .</span><span class="sxs-lookup"><span data-stu-id="25c87-116">In the **Partition Manager** dialog box, in **Partitions**, click the **Internet Sales** partition.</span></span>  
  
3.  <span data-ttu-id="25c87-117">В поле **имя секции**измените имя на `Internet Sales 2005` .</span><span class="sxs-lookup"><span data-stu-id="25c87-117">In **Partition Name**, change the name to `Internet Sales 2005`.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="25c87-118">Прежде чем переходить к следующему шагу, обратите внимание, что имена столбцов в окне «Предварительный просмотр таблицы» отображают столбцы, включенные в таблицу модели (которая отмечена флажком) с именами столбцов из источника.</span><span class="sxs-lookup"><span data-stu-id="25c87-118">Before continuing to the next step, notice the column names in the Table Preview window display those columns included in the model table (checked) with the column names from the source.</span></span> <span data-ttu-id="25c87-119">Это происходит, потому что окно «Предварительный просмотр таблицы» отображает столбцы из исходной таблицы, а не из таблицы модели.</span><span class="sxs-lookup"><span data-stu-id="25c87-119">This is because the Table Preview window displays columns from the source table, not from the model table.</span></span>  
  
4.  <span data-ttu-id="25c87-120">Нажмите кнопку **Редактор запросов** чуть выше в правой части окна предварительного просмотра.</span><span class="sxs-lookup"><span data-stu-id="25c87-120">Select the **Query Editor** button just above the right side of the preview window.</span></span>  
  
     <span data-ttu-id="25c87-121">Поскольку необходимо, чтобы секция включала только строки из определенного периода, используйте предложение WHERE.</span><span class="sxs-lookup"><span data-stu-id="25c87-121">Because you want the partition to include only those rows within a certain period, you must include a WHERE clause.</span></span> <span data-ttu-id="25c87-122">Предложение WHERE можно создать только с помощью инструкции SQL.</span><span class="sxs-lookup"><span data-stu-id="25c87-122">You can only create a WHERE clause by using a SQL Statement.</span></span>  
  
5.  <span data-ttu-id="25c87-123">В поле **Инструкция SQL** замените существующую инструкцию, вставив следующее:</span><span class="sxs-lookup"><span data-stu-id="25c87-123">In the **SQL Statement** field, replace the existing statement by pasting in the following statement:</span></span>  
  
    ```  
    SELECT   
    [dbo].[FactInternetSales].[ProductKey],  
    [dbo].[FactInternetSales].[CustomerKey],  
    [dbo].[FactInternetSales].[PromotionKey],  
    [dbo].[FactInternetSales].[CurrencyKey],  
    [dbo].[FactInternetSales].[SalesTerritoryKey],  
    [dbo].[FactInternetSales].[SalesOrderNumber],  
    [dbo].[FactInternetSales].[SalesOrderLineNumber],  
    [dbo].[FactInternetSales].[RevisionNumber],  
    [dbo].[FactInternetSales].[OrderQuantity],  
    [dbo].[FactInternetSales].[UnitPrice],  
    [dbo].[FactInternetSales].[ExtendedAmount],  
    [dbo].[FactInternetSales].[UnitPriceDiscountPct],  
    [dbo].[FactInternetSales].[DiscountAmount],  
    [dbo].[FactInternetSales].[ProductStandardCost],  
    [dbo].[FactInternetSales].[TotalProductCost],  
    [dbo].[FactInternetSales].[SalesAmount],  
    [dbo].[FactInternetSales].[TaxAmt],  
    [dbo].[FactInternetSales].[Freight],  
    [dbo].[FactInternetSales].[CarrierTrackingNumber],  
    [dbo].[FactInternetSales].[CustomerPONumber],  
    [dbo].[FactInternetSales].[OrderDate],  
    [dbo].[FactInternetSales].[DueDate],  
    [dbo].[FactInternetSales].[ShipDate]   
    FROM [dbo].[FactInternetSales]  
    WHERE (([OrderDate] >= N'2005-01-01 00:00:00') AND ([OrderDate] < N'2006-01-01 00:00:00'))  
    ```  
  
     <span data-ttu-id="25c87-124">Эта инструкция указывает, что секция должна включать все данные из строк, в которых OrderDate относится к календарному 2005 году, согласно предложению WHERE.</span><span class="sxs-lookup"><span data-stu-id="25c87-124">This statement specifies the partition should include all of the data in those rows where the OrderDate is for the 2005 calendar year as specified in the WHERE clause.</span></span>  
  
6.  <span data-ttu-id="25c87-125">Нажмите кнопку **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="25c87-125">Click **Validate**.</span></span>  
  
     <span data-ttu-id="25c87-126">Обратите внимание на предупреждение о том, что некоторые столбцы не присутствуют в источнике.</span><span class="sxs-lookup"><span data-stu-id="25c87-126">Notice a warning is displayed stating that certain columns are not present in source.</span></span> <span data-ttu-id="25c87-127">Это связано с тем, что в [занятии 3](rename-columns.md)столбцы переименованы в таблице Интернет-продажи в модели, чтобы они отличались от тех же столбцов в источнике.</span><span class="sxs-lookup"><span data-stu-id="25c87-127">This is because in [Lesson 3: Rename Columns](rename-columns.md), you renamed those columns in the Internet Sales table in the model to be different from those same columns at the source.</span></span>  
  
#### <a name="to-create-a-partition-for-the-2006-year-in-the-internet-sales-table"></a><span data-ttu-id="25c87-128">Создание секции для 2006 года в таблице Интернет-продаж</span><span class="sxs-lookup"><span data-stu-id="25c87-128">To create a partition for the 2006 year in the Internet Sales table</span></span>  
  
1.  <span data-ttu-id="25c87-129">В диалоговом окне **Диспетчер секций** в разделе **Секции**щелкните `Internet Sales 2005` только что созданную секцию, а затем **скопируйте**.</span><span class="sxs-lookup"><span data-stu-id="25c87-129">In the **Partition Manager** dialog box, in **Partitions**, click the `Internet Sales 2005` partition you just created, and then **Copy**.</span></span>  
  
2.  <span data-ttu-id="25c87-130">В **разделе Имя секции**введите `Internet Sales 2006` .</span><span class="sxs-lookup"><span data-stu-id="25c87-130">In **Partition Name**, type `Internet Sales 2006`.</span></span>  
  
3.  <span data-ttu-id="25c87-131">В инструкции SQL, чтобы секция включала только строки 2006 года, замените предложение WHERE следующим:</span><span class="sxs-lookup"><span data-stu-id="25c87-131">In the SQL Statement, in-order for the partition to include only those rows for the 2006 year, replace the WHERE clause with the following:</span></span>  
  
    ```  
    WHERE (([OrderDate] >= N'2006-01-01 00:00:00') AND ([OrderDate] < N'2007-01-01 00:00:00'))  
    ```  
  
#### <a name="to-create-a-partition-for-the-2007-year-in-the-internet-sales-table"></a><span data-ttu-id="25c87-132">Создание секции для 2007 года в таблице Интернет-продаж</span><span class="sxs-lookup"><span data-stu-id="25c87-132">To create a partition for the 2007 year in the Internet Sales table</span></span>  
  
1.  <span data-ttu-id="25c87-133">В диалоговом окне **Диспетчер секций** выберите команду **Копировать**.</span><span class="sxs-lookup"><span data-stu-id="25c87-133">In the **Partition Manager** dialog box, click **Copy**.</span></span>  
  
2.  <span data-ttu-id="25c87-134">В **разделе Имя секции**введите `Internet Sales 2007` .</span><span class="sxs-lookup"><span data-stu-id="25c87-134">In **Partition Name**, type `Internet Sales 2007`.</span></span>  
  
3.  <span data-ttu-id="25c87-135">В списке **переключиться на**выберите **Редактор запросов**.</span><span class="sxs-lookup"><span data-stu-id="25c87-135">In **Switch To**, select **Query Editor**.</span></span>  
  
4.  <span data-ttu-id="25c87-136">В инструкции SQL, чтобы секция включала только строки 2007 года, замените предложение WHERE следующим:</span><span class="sxs-lookup"><span data-stu-id="25c87-136">In the SQL Statement, in-order for the partition to include only those rows for the 2007 year, replace the WHERE clause with the following:</span></span>  
  
    ```  
    WHERE (([OrderDate] >= N'2007-01-01 00:00:00') AND ([OrderDate] < N'2008-01-01 00:00:00'))  
    ```  
  
#### <a name="to-create-a-partition-for-the-2008-year-in-the-internet-sales-table"></a><span data-ttu-id="25c87-137">Создание секции для 2008 года в таблице Интернет-продаж</span><span class="sxs-lookup"><span data-stu-id="25c87-137">To create a partition for the 2008 year in the Internet Sales table</span></span>  
  
1.  <span data-ttu-id="25c87-138">В диалоговом окне **Диспетчер секций** выберите команду **Создать**.</span><span class="sxs-lookup"><span data-stu-id="25c87-138">In the **Partition Manager** dialog box, click **New**.</span></span>  
  
2.  <span data-ttu-id="25c87-139">В **разделе Имя секции**введите `Internet Sales 2008` .</span><span class="sxs-lookup"><span data-stu-id="25c87-139">In **Partition Name**, type `Internet Sales 2008`.</span></span>  
  
3.  <span data-ttu-id="25c87-140">В списке **переключиться на**выберите **Редактор запросов**.</span><span class="sxs-lookup"><span data-stu-id="25c87-140">In **Switch To**, select **Query Editor**.</span></span>  
  
4.  <span data-ttu-id="25c87-141">В инструкции SQL, чтобы секция включала только строки 2008 года, замените предложение WHERE следующим:</span><span class="sxs-lookup"><span data-stu-id="25c87-141">In the SQL Statement, in-order for the partition to include only those rows for the 2008 year, replace the WHERE clause with the following:</span></span>  
  
    ```  
    WHERE (([OrderDate] >= N'2008-01-01 00:00:00') AND ([OrderDate] < N'2009-01-01 00:00:00'))  
    ```  
  
#### <a name="to-create-a-partition-for-the-2009-year-in-the-internet-sales-table"></a><span data-ttu-id="25c87-142">Создание секции для 2009 года в таблице «Интернет-продажи»</span><span class="sxs-lookup"><span data-stu-id="25c87-142">To create a partition for the 2009 year in the Internet Sales table</span></span>  
  
1.  <span data-ttu-id="25c87-143">В диалоговом окне **Диспетчер секций** выберите команду **Создать**.</span><span class="sxs-lookup"><span data-stu-id="25c87-143">In the **Partition Manager** dialog box, click **New**.</span></span>  
  
2.  <span data-ttu-id="25c87-144">В **разделе Имя секции**введите `Internet Sales 2009` .</span><span class="sxs-lookup"><span data-stu-id="25c87-144">In **Partition Name**, type `Internet Sales 2009`.</span></span>  
  
3.  <span data-ttu-id="25c87-145">В списке **переключиться на**выберите **Редактор запросов**.</span><span class="sxs-lookup"><span data-stu-id="25c87-145">In **Switch To**, select **Query Editor**.</span></span>  
  
4.  <span data-ttu-id="25c87-146">Для того чтобы секция включала только строки для 2009 года, замените предложение WHERE в инструкции SQL на следующее:</span><span class="sxs-lookup"><span data-stu-id="25c87-146">In the SQL Statement, in-order for the partition to include only those rows for the 2009 year, replace the WHERE clause with the following:</span></span>  
  
    ```  
    WHERE (([OrderDate] >= N'2009-01-01 00:00:00') AND ([OrderDate] < N'2010-01-01 00:00:00'))  
    ```  
  
## <a name="process-partitions"></a><span data-ttu-id="25c87-147">Обработка секций</span><span class="sxs-lookup"><span data-stu-id="25c87-147">Process Partitions</span></span>  
 <span data-ttu-id="25c87-148">В диалоговом окне **Диспетчер секций** обратите внимание на звездочку (**\***) рядом с именем каждой из только что созданных секций.</span><span class="sxs-lookup"><span data-stu-id="25c87-148">In the **Partition Manager** dialog box, notice the asterisk (**\***) next to the partition names for each of the new partitions you just created.</span></span> <span data-ttu-id="25c87-149">Это означает, что секция не была обработана (обновлена).</span><span class="sxs-lookup"><span data-stu-id="25c87-149">This indicates that the partition has not been processed (refreshed).</span></span> <span data-ttu-id="25c87-150">Во время создания новых секций нужно запустить операцию обработки секций или обработки таблиц для обновления данных в этих секциях.</span><span class="sxs-lookup"><span data-stu-id="25c87-150">When you create new partitions, you should run a Process Partitions or Process Table operation to refresh the data in those partitions.</span></span>  
  
#### <a name="to-process-internet-sales-partitions"></a><span data-ttu-id="25c87-151">Обработка секций интернет-продаж</span><span class="sxs-lookup"><span data-stu-id="25c87-151">To process Internet Sales partitions</span></span>  
  
1.  <span data-ttu-id="25c87-152">Нажмите кнопку **OK** , чтобы закрыть диалоговое окно **Диспетчер секций** .</span><span class="sxs-lookup"><span data-stu-id="25c87-152">Click **OK** to close the **Partition Manager** dialog box.</span></span>  
  
2.  <span data-ttu-id="25c87-153">В конструкторе моделей щелкните таблицу **Интернет-продажи** , откройте меню **Модель** , наведите указатель на пункт **Обработка** (обновление) и выберите команду **Обработать секции**.</span><span class="sxs-lookup"><span data-stu-id="25c87-153">In the model designer, click the **Internet Sales** table, then click the **Model** menu, then point to **Process** (Refresh), and then click **Process Partitions**.</span></span>  
  
3.  <span data-ttu-id="25c87-154">Убедитесь в том, что в диалоговом окне **Обработать секции** свойство **Режим** имеет значение **Обработка по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="25c87-154">In the **Process Partitions** dialog box, verify the **Mode** is set to **Process Default**.</span></span>  
  
4.  <span data-ttu-id="25c87-155">Установите флажок в столбце **Обработка** для каждой из пяти созданных секций, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="25c87-155">Select the checkbox in the **Process** column for each of the five partitions you created, and then click **OK**.</span></span>  
  
     <span data-ttu-id="25c87-156">Если появится окно для ввода учетных данных олицетворения, введите имя пользователя и пароль в системе Windows, которые были указаны в занятии 2, шаге 6.</span><span class="sxs-lookup"><span data-stu-id="25c87-156">If you are prompted for Impersonation credentials, enter the Windows user name and password you specified in Lesson 2, step 6.</span></span>  
  
     <span data-ttu-id="25c87-157">Затем отображается диалоговое окно **обработка данных** , в котором отображаются сведения о процессе для каждой секции.</span><span class="sxs-lookup"><span data-stu-id="25c87-157">The **Data Process** dialog box then appears and displays process details for each partition.</span></span> <span data-ttu-id="25c87-158">Обратите внимание, что для каждой секции передается различное количество строк.</span><span class="sxs-lookup"><span data-stu-id="25c87-158">Notice that a different number of rows for each partition are transferred.</span></span> <span data-ttu-id="25c87-159">Это происходит, потому что каждая секция включает только строки для года, указанного с помощью предложения WHERE в инструкции SQL.</span><span class="sxs-lookup"><span data-stu-id="25c87-159">This is because each partition includes only those rows for the year specified in the WHERE clause in the SQL Statement.</span></span> <span data-ttu-id="25c87-160">Нет данных за 2010 год.</span><span class="sxs-lookup"><span data-stu-id="25c87-160">There is no data for the 2010 year.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="25c87-161">Next Steps</span><span class="sxs-lookup"><span data-stu-id="25c87-161">Next Steps</span></span>  
 <span data-ttu-id="25c87-162">Чтобы продолжить изучение этого учебника, перейдите к следующему занятию: [Занятие 12. Создание ролей](lesson-11-create-roles.md).</span><span class="sxs-lookup"><span data-stu-id="25c87-162">To continue this tutorial, go to the next lesson: Lesson: [Lesson 12: Create Roles](lesson-11-create-roles.md).</span></span>  
  
  
