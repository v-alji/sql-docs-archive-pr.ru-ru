---
title: Занятие 8. Создание фильтра данных | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 19ccbdba-e3da-40a4-b652-32c628cf32e5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9c11d4cf83619e53cd7e8f00091c66cc8e50ad76
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656218"
---
# <a name="lesson-8-create-a-data-filter"></a><span data-ttu-id="b0060-102">Занятие 8. Создание фильтра данных</span><span class="sxs-lookup"><span data-stu-id="b0060-102">Lesson 8: Create a Data Filter</span></span>
  <span data-ttu-id="b0060-103">После добавления к родительскому отчету операции детализации следующий шаг состоит в создании фильтра данных для таблицы данных, которая определена в дочернем отчете.</span><span class="sxs-lookup"><span data-stu-id="b0060-103">After you add a drillthrough action on the parent report, your next step is to create a data filter for the data table that you defined for the child report.</span></span>  
  
 <span data-ttu-id="b0060-104">Для детализированного отчета можно создать фильтр на основе таблицы **или** фильтр запроса.</span><span class="sxs-lookup"><span data-stu-id="b0060-104">You can create a table-based filter **or** a query filter for the drillthrough report.</span></span> <span data-ttu-id="b0060-105">На этом занятии приведены указания по обоим вариантам.</span><span class="sxs-lookup"><span data-stu-id="b0060-105">This lesson provides instructions for both options.</span></span>  
  
## <a name="table-based-filter"></a><span data-ttu-id="b0060-106">Фильтр на основе таблицы</span><span class="sxs-lookup"><span data-stu-id="b0060-106">Table-Based Filter</span></span>  
 <span data-ttu-id="b0060-107">Для реализации фильтра на основе таблицы необходимо выполнить следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="b0060-107">You need to complete the following tasks to implement a table-based filter.</span></span>  
  
-   <span data-ttu-id="b0060-108">Добавить критерий фильтра к табликсу в дочернем отчете.</span><span class="sxs-lookup"><span data-stu-id="b0060-108">Add a filter expression to the tablix in the child report.</span></span>  
  
-   <span data-ttu-id="b0060-109">Создать функцию, которая выбирает нефильтрованные данные из таблицы `PurchaseOrderDetail`.</span><span class="sxs-lookup"><span data-stu-id="b0060-109">Create a function that selects unfiltered data from the `PurchaseOrderDetail` table.</span></span>  
  
-   <span data-ttu-id="b0060-110">Добавить обработчик событий, который связывает таблицу данных `PurchaseOrderDetail` с дочерним отчетом.</span><span class="sxs-lookup"><span data-stu-id="b0060-110">Add an event handler that binds the `PurchaseOrderDetail` DataTable to the child report.</span></span>  
  
#### <a name="to-add-a-filter-expression-to-the-tablix-in-the-child-report"></a><span data-ttu-id="b0060-111">Добавление критерия фильтра к табликсу в дочернем отчете</span><span class="sxs-lookup"><span data-stu-id="b0060-111">To add a filter expression to the tablix in the child report</span></span>  
  
1.  <span data-ttu-id="b0060-112">Откройте дочерний отчет.</span><span class="sxs-lookup"><span data-stu-id="b0060-112">Open the child report.</span></span>  
  
2.  <span data-ttu-id="b0060-113">Выберите заголовок столбца в табликса, щелкните правой кнопкой мыши серую ячейку, которая появляется над заголовком столбца, и выберите пункт **Свойства табликса**.</span><span class="sxs-lookup"><span data-stu-id="b0060-113">Select a column heading in the tablix, right-click the gray cell that appears above the column heading, and then click **Tablix Properties**.</span></span>  
  
3.  <span data-ttu-id="b0060-114">Щелкните страницу **фильтры** , а затем нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="b0060-114">Click on the **Filters** page, and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="b0060-115">В заархивированном **выражении** щелкните `ProductID` из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="b0060-115">In the **Expression** filed, click `ProductID` from the drop-down list.</span></span> <span data-ttu-id="b0060-116">Это столбец, к которому применяется фильтр.</span><span class="sxs-lookup"><span data-stu-id="b0060-116">This is the column to which you apply the filter.</span></span>  
  
5.  <span data-ttu-id="b0060-117">В раскрывающемся **=** списке **оператор** щелкните оператор EQUAL ().</span><span class="sxs-lookup"><span data-stu-id="b0060-117">Click the equal (**=**) operator in the **Operator** drop-down list.</span></span>  
  
6.  <span data-ttu-id="b0060-118">Нажмите кнопку выражения рядом с полем **значение** , выберите **Параметры** в области **Категория** , а затем дважды щелкните `productid` в области **значения** .</span><span class="sxs-lookup"><span data-stu-id="b0060-118">Click the expression button next to the **Value** field, click **Parameters** in the **Category** area, and then double-click `productid` in the **Values** area.</span></span> <span data-ttu-id="b0060-119">Поле **Задать выражение для: Значение** теперь должно содержать выражение, аналогичное **=Parameters!productid.Value**.</span><span class="sxs-lookup"><span data-stu-id="b0060-119">The **Set expression for: Value** field should now contain expression similar to **=Parameters!productid.Value**.</span></span>  
  
7.  <span data-ttu-id="b0060-120">Снова нажмите кнопку **ОК** и **ОК** в диалоговом окне **Свойства табликса** .</span><span class="sxs-lookup"><span data-stu-id="b0060-120">Click **OK,** and **OK** again in the **Tablix Properties** dialog box.</span></span>  
  
8.  <span data-ttu-id="b0060-121">Сохраните RDLC-файл.</span><span class="sxs-lookup"><span data-stu-id="b0060-121">Save the .rdlc file.</span></span>  
  
#### <a name="to-create-a-function-that-selects-unfiltered-data-from-the-purchaseordedetail-table"></a><span data-ttu-id="b0060-122">Создание функции, которая выбирает нефильтрованные данные из таблицы PurchaseOrdeDetail</span><span class="sxs-lookup"><span data-stu-id="b0060-122">To create a function that selects unfiltered data from the PurchaseOrdeDetail table</span></span>  
  
1.  <span data-ttu-id="b0060-123">В обозревателе решений разверните Default.aspx, затем дважды щелкните Default.aspx.cs.</span><span class="sxs-lookup"><span data-stu-id="b0060-123">In Solution Explorer, expand Default.aspx, and then double click Default.aspx.cs.</span></span>  
  
2.  <span data-ttu-id="b0060-124">Создайте новую функцию, которая принимает параметр `productid` типа Integer, возвращает объект `datatable` и выполняет следующие действия.</span><span class="sxs-lookup"><span data-stu-id="b0060-124">Create a new function that accepts a parameter, `productid`, of type Integer and returns a `datatable` object, and does the following.</span></span>  
  
    1.  <span data-ttu-id="b0060-125">Создает экземпляр набора данных, `DataSet2` который был создан на шаге 2 [занятия 4: определение подключения к данным и таблицы данных для дочернего отчета](lesson-4-define-a-data-connection-and-data-table-for-child-report.md).</span><span class="sxs-lookup"><span data-stu-id="b0060-125">Creates an instance of the dataset, `DataSet2`, which was created in Step 2 of [Lesson 4: Define a Data Connection and Data Table for Child Report](lesson-4-define-a-data-connection-and-data-table-for-child-report.md).</span></span>  
  
    2.  <span data-ttu-id="b0060-126">Создает подключение к базе данных SqlServer для выполнения запроса, который был определен на **занятии 4. "Определение подключения к данным и таблицы данных для дочернего отчета"** .</span><span class="sxs-lookup"><span data-stu-id="b0060-126">Create a connection to the SqlServer database to execute the query defined in **Lesson 4: Define a Data Connection and DataTable for Child Report**.</span></span>  
  
    3.  <span data-ttu-id="b0060-127">Запрос возвратит нефильтрованные данные.</span><span class="sxs-lookup"><span data-stu-id="b0060-127">The query will return unfiltered data.</span></span>  
  
    4.  <span data-ttu-id="b0060-128">Заполнение экземпляра набора данных нефильтрованными данными путем выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="b0060-128">Fill the DataSet instance with the unfiltered data by executing the query.</span></span>  
  
    5.  <span data-ttu-id="b0060-129">Возврат таблицы данных `PurchaseOrderDetail`.</span><span class="sxs-lookup"><span data-stu-id="b0060-129">Return the `PurchaseOrderDetail` DataTable.</span></span>  
  
         <span data-ttu-id="b0060-130">Функция будет иметь примерно такой вид, как показано ниже. (Этот пример приведен только для справки.</span><span class="sxs-lookup"><span data-stu-id="b0060-130">The function will look similar to the one below, (This is just for your reference.</span></span> <span data-ttu-id="b0060-131">Для выборки необходимых данных для дочернего отчета можно применять любой подход.)</span><span class="sxs-lookup"><span data-stu-id="b0060-131">You can follow any pattern that you want, to fetch the necessary data for child report).</span></span>  
  
        ```  
        /// <summary>  
            /// Function to query PurchaseOrderDetail table, fetch the  
            /// unfiltered data and bind it with the Child report  
            /// </summary>  
            /// <returns>A dataTable of type PurchaseOrderDetail</returns>  
            private DataTable GetPurchaseOrderDetail()  
            {  
                try  
                {  
                    //Create the instance for the typed dataset, DataSet2 which will   
                    //hold the [PurchaseOrderDetail] table details.  
                    //The dataset was created as part of the tutorial in Step 4.  
                    DataSet2 ds = new DataSet2();  
  
                    //Create a SQL Connection to the AdventureWorks2008 database using Windows Authentication.  
                    using (SqlConnection sqlconn = new SqlConnection("Data Source=.;Initial Catalog=Adventureworks;Integrated Security=SSPI"))  
                    {  
                        //Building the dynamic query with the parameter ProductID.  
                        SqlDataAdapter adap = new SqlDataAdapter("SELECT PurchaseOrderID, PurchaseOrderDetailID, OrderQty, ProductID, ReceivedQty, RejectedQty, StockedQty FROM Purchasing.PurchaseOrderDetail ", sqlconn);  
                        //Executing the QUERY and fill the dataset with the PurchaseOrderDetail table data.  
                        adap.Fill(ds, "PurchaseOrderDetail");  
                    }  
  
                    //Return the PurchaseOrderDetail table for the Report Data Source.  
                    return ds.PurchaseOrderDetail;  
                }  
                catch  
                {  
                    throw;  
                }  
            }  
        ```  
  
#### <a name="to-add-an-event-handler-that-binds-the-purchaseorderdetail-datatable-to-the-child-report"></a><span data-ttu-id="b0060-132">Добавление обработчика событий, который связывает таблицу данных PurchaseOrderDetail с дочерним отчетом</span><span class="sxs-lookup"><span data-stu-id="b0060-132">To add an event handler that binds the PurchaseOrderDetail DataTable to the child report</span></span>  
  
1.  <span data-ttu-id="b0060-133">Откройте страницу Default.aspx.</span><span class="sxs-lookup"><span data-stu-id="b0060-133">Open Default.aspx.</span></span>  
  
2.  <span data-ttu-id="b0060-134">Щелкните правой кнопкой мыши элемент управления ReportViewer и выберите пункт **Свойства.**</span><span class="sxs-lookup"><span data-stu-id="b0060-134">Right click the ReportViewer control, and then click **Properties.**</span></span>  
  
3.  <span data-ttu-id="b0060-135">На странице **Свойства** щелкните значок **события** .</span><span class="sxs-lookup"><span data-stu-id="b0060-135">On the **Properties** page, click the **Events** icon.</span></span>  
  
4.  <span data-ttu-id="b0060-136">Дважды щелкните событие **детализации** .</span><span class="sxs-lookup"><span data-stu-id="b0060-136">Double click the **Drillthrough** event.</span></span>  
  
     <span data-ttu-id="b0060-137">Это приведет к добавлению раздела обработчика событий в код, который выглядит так, как в приведенном ниже блоке.</span><span class="sxs-lookup"><span data-stu-id="b0060-137">This will add an event handler section in the code, which will look similar to the below block.</span></span>  
  
    ```  
    protected void ReportViewer1_Drillthrough(object sender, Microsoft.Reporting.WebForms.DrillthroughEventArgs e)  
    {  
    }  
    ```  
  
5.  <span data-ttu-id="b0060-138">Завершите подготовку обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="b0060-138">Complete the event handler.</span></span> <span data-ttu-id="b0060-139">Он должен включать следующие функции.</span><span class="sxs-lookup"><span data-stu-id="b0060-139">It should include the following functionalty.</span></span>  
  
    1.  <span data-ttu-id="b0060-140">Выборка ссылки на объект дочернего отчета из параметра *DrillthroughEventArgs* .</span><span class="sxs-lookup"><span data-stu-id="b0060-140">Fetch the child report object reference from the *DrillthroughEventArgs* parameter.</span></span>  
  
    2.  <span data-ttu-id="b0060-141">Вызовите функцию,`GetPurchaseOrderDetail`</span><span class="sxs-lookup"><span data-stu-id="b0060-141">Call the function, `GetPurchaseOrderDetail`</span></span>  
  
    3.  <span data-ttu-id="b0060-142">Привязка таблицы данных `PurchaseOrderDetail` к соответствующему источнику данных отчета.</span><span class="sxs-lookup"><span data-stu-id="b0060-142">Bind the `PurchaseOrderDetail` DataTable with the report's corresponding data source.</span></span>  
  
         <span data-ttu-id="b0060-143">Код обработчика событий в законченном виде будет выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="b0060-143">The completed event handler code will look similar to the following.</span></span>  
  
        ```  
        protected void ReportViewer1_Drillthrough(object sender, Microsoft.Reporting.WebForms.DrillthroughEventArgs e)  
            {  
                try  
                {  
                     //Get the instance of the Target report, in our case the JumpReport.rdlc.  
                    LocalReport report = (LocalReport)e.Report;  
  
                     //Binding the DataTable to the Child report dataset.  
                    //The name DataSet1 which can be located from,   
                    //Go to Design view of Child.rdlc, Click View menu -> Report Data  
                    //You'll see this name under DataSet2.  
                    report.DataSources.Add(new ReportDataSource("DataSet1", GetPurchaseOrderDetail()));  
                }  
                catch (Exception ex)  
                {  
                    Response.Write(ex.Message);  
                }  
            }  
        ```  
  
6.  <span data-ttu-id="b0060-144">Сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="b0060-144">Save the file.</span></span>  
  
## <a name="query-filter"></a><span data-ttu-id="b0060-145">Фильтр с запросом</span><span class="sxs-lookup"><span data-stu-id="b0060-145">Query Filter</span></span>  
 <span data-ttu-id="b0060-146">Для реализации фильтра с запросом необходимо выполнить следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="b0060-146">You need to complete the following tasks to implement a query filter.</span></span>  
  
-   <span data-ttu-id="b0060-147">Создание функции, которая выбирает фильтрованные данные из таблицы `PurchaseOrderDetail`.</span><span class="sxs-lookup"><span data-stu-id="b0060-147">Create a function that selected filtered data from the `PurchaseOrderDetail` table.</span></span>  
  
-   <span data-ttu-id="b0060-148">Добавление обработчика событий, который получает значения параметров и привязывает таблицу данных `PurchaseOrdeDetail` к дочернему отчету.</span><span class="sxs-lookup"><span data-stu-id="b0060-148">Add an event handler that retrieves parameter values and binds the `PurchaseOrdeDetail` DataTable to the child report.</span></span>  
  
#### <a name="to-create-a-function-that-selects-filtered-data-from-the-purchaseorderdetail-table"></a><span data-ttu-id="b0060-149">Создание функции, которая выбирает фильтрованные данные из таблицы PurchaseOrderDetail</span><span class="sxs-lookup"><span data-stu-id="b0060-149">To create a function that selects filtered data from the PurchaseOrderDetail table</span></span>  
  
1.  <span data-ttu-id="b0060-150">В обозревателе решений разверните Default.aspx, затем дважды щелкните Default.aspx.cs.</span><span class="sxs-lookup"><span data-stu-id="b0060-150">In Solution Explorer, expand Default.aspx, and then double click Default.aspx.cs.</span></span>  
  
2.  <span data-ttu-id="b0060-151">Создайте новую функцию, которая принимает параметр `productid` типа Integer, возвращает объект `datatable` и выполняет следующие действия.</span><span class="sxs-lookup"><span data-stu-id="b0060-151">Create a new function that accepts a parameter, `productid`, of type Integer and returns a `datatable` object and does the following.</span></span>  
  
    1.  <span data-ttu-id="b0060-152">Создает экземпляр набора данных, `DataSet2` который был создан на шаге 2 [занятия 4: определение подключения к данным и таблицы данных для дочернего отчета](lesson-4-define-a-data-connection-and-data-table-for-child-report.md).</span><span class="sxs-lookup"><span data-stu-id="b0060-152">Creates an instance of the dataset, `DataSet2`, which was created in Step 2 of [Lesson 4: Define a Data Connection and Data Table for Child Report](lesson-4-define-a-data-connection-and-data-table-for-child-report.md).</span></span>  
  
    2.  <span data-ttu-id="b0060-153">Создает подключение к базе данных SqlServer для выполнения запроса, который был определен на **занятии 4. "Определение подключения к данным и таблицы данных для дочернего отчета"** .</span><span class="sxs-lookup"><span data-stu-id="b0060-153">Create a connection to the SqlServer database to execute the query defined **Lesson 4: Define a Data Connection and DataTable for Child Report**.</span></span>  
  
    3.  <span data-ttu-id="b0060-154">Запрос должен включать параметр `productid` для обеспечения фильтрации возвращаемых данных с учетом значения `ProductID`, выбранного в родительском отчете.</span><span class="sxs-lookup"><span data-stu-id="b0060-154">The query will include a parameter, `productid`, to make sure the data returned is filtered based on the `ProductID` selected in the parent report.</span></span>  
  
    4.  <span data-ttu-id="b0060-155">Заполнение экземпляра набора данных фильтрованными данными путем выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="b0060-155">Fill the DataSet instance with the filtered data by executing the query.</span></span>  
  
    5.  <span data-ttu-id="b0060-156">Возврат таблицы данных `PurchaseOrderDetail`.</span><span class="sxs-lookup"><span data-stu-id="b0060-156">Return the `PurchaseOrderDetail` DataTable.</span></span>  
  
         <span data-ttu-id="b0060-157">Функция будет иметь примерно такой вид, как показано ниже. (Этот пример приведен только для справки.</span><span class="sxs-lookup"><span data-stu-id="b0060-157">The function will look similar to the one below, (This is just for your reference.</span></span> <span data-ttu-id="b0060-158">Для выборки необходимых данных для дочернего отчета можно применять любой подход.)</span><span class="sxs-lookup"><span data-stu-id="b0060-158">You can follow any pattern that you want, to fetch the necessary data for child report).</span></span>  
  
        ```  
        /// <summary>  
            /// Function to query PurchaseOrderDetail table and filter the  
            /// data for a specific ProductID selected in the Parent report.  
            /// </summary>  
            /// <param name="productid">Parameter passed from the Parent report to filter data.</param>  
            /// <returns>A dataTable of type PurchaseOrderDetail</returns>  
            private DataTable GetPurchaseOrderDetail(int productid)  
            {  
                try  
                {  
                    //Create the instance for the typed dataset, DataSet2 which will   
                    //hold the [PurchaseOrderDetail] table details.  
                    //The dataset was created as part of the tutorial in Step 4.  
                    DataSet2 ds = new DataSet2();  
  
                    //Create a SQL Connection to the AdventureWorks2008 database using Windows Authentication.  
                    using (SqlConnection sqlconn = new SqlConnection("Data Source=.;Initial Catalog=Adventureworks;Integrated Security=SSPI"))  
                    {  
                        //Building the dynamic query with the parameter ProductID.  
                        SqlDataAdapter adap = new SqlDataAdapter("SELECT PurchaseOrderID, PurchaseOrderDetailID, OrderQty, ProductID, ReceivedQty, RejectedQty, StockedQty FROM Purchasing.PurchaseOrderDetail where ProductID = " + productid, sqlconn);  
                        //Executing the QUERY and fill the dataset with the PurchaseOrderDetail table data.  
                        adap.Fill(ds, "PurchaseOrderDetail");  
                    }  
  
                    //Return the PurchaseOrderDetail table for the Report Data Source.  
                    return ds.PurchaseOrderDetail;  
                }  
                catch  
                {  
                    throw;  
                }  
            }  
        ```  
  
#### <a name="to-add-an-event-handler-that-retrieves-parameter-values-and-binds-the-purchaseordedetail-datatable-to-the-child-report"></a><span data-ttu-id="b0060-159">Добавление обработчика событий, который получает значения параметров и связывает таблицу данных PurchaseOrdeDetail с дочерним отчетом</span><span class="sxs-lookup"><span data-stu-id="b0060-159">To add an event handler that retrieves parameter values and binds the PurchaseOrdeDetail DataTable to the child report</span></span>  
  
1.  <span data-ttu-id="b0060-160">Откройте страницу Default.aspx.</span><span class="sxs-lookup"><span data-stu-id="b0060-160">Open Default.aspx.</span></span>  
  
2.  <span data-ttu-id="b0060-161">Щелкните правой кнопкой мыши элемент управления ReportViewer и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="b0060-161">Right-click the ReportViewer control, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="b0060-162">На панели **Свойства** щелкните значок **события** .</span><span class="sxs-lookup"><span data-stu-id="b0060-162">On the **Properties** pane, click the **Events** icon.</span></span>  
  
4.  <span data-ttu-id="b0060-163">Дважды щелкните событие **детализации** .</span><span class="sxs-lookup"><span data-stu-id="b0060-163">Double click the **Drillthrough** event.</span></span>  
  
     <span data-ttu-id="b0060-164">Это приведет к добавлению раздела с обработчиком событий в код, который будет выглядеть примерно так.</span><span class="sxs-lookup"><span data-stu-id="b0060-164">This will add an event handler section in the code that will look similar to the following.</span></span>  
  
    ```  
    protected void ReportViewer1_Drillthrough(object sender, Microsoft.Reporting.WebForms.DrillthroughEventArgs e)  
    {  
    }  
    ```  
  
5.  <span data-ttu-id="b0060-165">Завершите подготовку обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="b0060-165">Complete the event handler.</span></span> <span data-ttu-id="b0060-166">Он должен выполнять следующие функции.</span><span class="sxs-lookup"><span data-stu-id="b0060-166">It should include the following functionality.</span></span>  
  
    1.  <span data-ttu-id="b0060-167">Выборка ссылки на объект дочернего отчета из параметра *DrillthroughEventArgs* .</span><span class="sxs-lookup"><span data-stu-id="b0060-167">Fetch the Child report object reference from the *DrillthroughEventArgs* parameter.</span></span>  
  
    2.  <span data-ttu-id="b0060-168">Получение списка параметров дочернего отчета из имеющегося объекта дочернего отчета.</span><span class="sxs-lookup"><span data-stu-id="b0060-168">Get the child report parameter list from the child report object fetched.</span></span>  
  
    3.  <span data-ttu-id="b0060-169">Итерация в коллекции параметров и выборка значения для параметра `ProductID`, переданного из родительского отчета.</span><span class="sxs-lookup"><span data-stu-id="b0060-169">Iterate through the parameter's collection and retrieve the value for the parameter, `ProductID`, passed from the parent report.</span></span>  
  
    4.  <span data-ttu-id="b0060-170">Вызов функции `GetPurchaseOrderDetail` и передача значения для параметра `ProductID`.</span><span class="sxs-lookup"><span data-stu-id="b0060-170">Call the function, `GetPurchaseOrderDetail`, and pass the value for parameter `ProductID`.</span></span>  
  
    5.  <span data-ttu-id="b0060-171">Привязка таблицы данных `PurchaseOrderDetail` к соответствующему источнику данных отчета.</span><span class="sxs-lookup"><span data-stu-id="b0060-171">Bind the `PurchaseOrderDetail` DataTable with the Report's corresponding data source.</span></span>  
  
         <span data-ttu-id="b0060-172">Код обработчика событий в законченном виде будет выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="b0060-172">The completed event handler code will look similar to the following.</span></span>  
  
        ```  
        protected void ReportViewer1_Drillthrough(object sender, Microsoft.Reporting.WebForms.DrillthroughEventArgs e)  
            {  
                try  
                {  
                    //Variable to store the parameter value passed from the MainReport.  
                    int productid = 0;  
  
                    //Get the instance of the Target report, in our case the JumpReport.rdlc.  
                    LocalReport report = (LocalReport)e.Report;  
  
                    //Get all the parameters passed from the main report to the target report.  
                    //OriginalParametersToDrillthrough actually returns a Generic list of   
                    //type ReportParameter.  
                    IList<ReportParameter> list = report.OriginalParametersToDrillthrough;  
  
                    //Parse through each parameters to fetch the values passed along with them.  
                    foreach (ReportParameter param in list)  
                    {  
                        //Since we know the report has only one parameter and it is not a multivalued,   
                        //we can directly fetch the first value from the Values array.  
                        productid = Convert.ToInt32(param.Values[0].ToString());  
                    }  
  
                    //Binding the DataTable to the Child report dataset.  
                    //The name DataSet1 which can be located from,   
                    //Go to Design view of Child.rdlc, Click View menu -> Report Data  
                    //You'll see this name under DataSet2.  
                    report.DataSources.Add(new ReportDataSource("DataSet1", GetPurchaseOrderDetail(productid)));  
                }  
                catch (Exception ex)  
                {  
                    Response.Write(ex.Message);  
                }  
            }  
        ```  
  
6.  <span data-ttu-id="b0060-173">Сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="b0060-173">Save the file.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="b0060-174">Следующая задача</span><span class="sxs-lookup"><span data-stu-id="b0060-174">Next Task</span></span>  
 <span data-ttu-id="b0060-175">Тем самым был успешно создан фильтр данных для таблицы данных, которая определена в дочернем отчете.</span><span class="sxs-lookup"><span data-stu-id="b0060-175">You have successfully created a data filter for the data table that you defined for the child report.</span></span> <span data-ttu-id="b0060-176">Затем необходимо построить и запустить приложение веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="b0060-176">Next, you will build and run the website application.</span></span>  
  
  
