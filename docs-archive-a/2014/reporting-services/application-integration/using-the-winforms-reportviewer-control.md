---
title: Использование элемента управления WinForms ReportViewer | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- ReportViewer controls
ms.assetid: 29fb9f7d-ba65-49fd-9cbc-4c380869de96
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3e4eda5218a91b3c8286177607034da230ff7cc2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664042"
---
# <a name="using-the-winforms-reportviewer-control"></a><span data-ttu-id="eb245-102">Использование элемента управления WinForms ReportViewer</span><span class="sxs-lookup"><span data-stu-id="eb245-102">Using the WinForms ReportViewer Control</span></span>
  <span data-ttu-id="eb245-103">Для просмотра отчетов, развернутых на сервере отчетов, и отчетов, существующих в локальной файловой системе, можно использовать элемент управления WinForms ReportViewer для подготовки отчетов к просмотру в приложении Windows.</span><span class="sxs-lookup"><span data-stu-id="eb245-103">To view reports that have been deployed to a report server or reports that exist on the local file system, you can use the WinForms ReportViewer control to render them in a Windows application.</span></span>  
  
###### <a name="to-add-the-reportviewer-control-to-a-windows-application"></a><span data-ttu-id="eb245-104">Добавление элемента управления ReportViewer в приложение Windows</span><span class="sxs-lookup"><span data-stu-id="eb245-104">To add the ReportViewer Control to a Windows application</span></span>  
  
1.  <span data-ttu-id="eb245-105">Создайте новое приложение Windows, используя либо [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csprcs](../../includes/csprcs-md.md)] [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="eb245-105">Create a new Windows application using either [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csprcs](../../includes/csprcs-md.md)] or [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)].</span></span>  
  
     <span data-ttu-id="eb245-106">\- - или -</span><span class="sxs-lookup"><span data-stu-id="eb245-106">\- Or -</span></span>  
  
     <span data-ttu-id="eb245-107">Открыть существующий проект приложения Windows и добавить новую форму.</span><span class="sxs-lookup"><span data-stu-id="eb245-107">Open an exiting Windows application project and add a new form.</span></span>  
  
2.  <span data-ttu-id="eb245-108">Укажите элемент управления ReportViewer в окне **Панель элементов**.</span><span class="sxs-lookup"><span data-stu-id="eb245-108">Locate the ReportViewer control in the **Toolbox**.</span></span> <span data-ttu-id="eb245-109">Если окно **Панель элементов** не отображается, к нему можно получить доступ из меню **Вид**, выбрав пункт **Панель элементов**.</span><span class="sxs-lookup"><span data-stu-id="eb245-109">If the **Toolbox** is not visible, you can access it from the **View** menu by selecting **Toolbox**.</span></span>  
  
     <span data-ttu-id="eb245-110">![Выбор элемента управления ReportViewer](../../../2014/reporting-services/media/windowsapp-toolboxreportviewer.png "Выбор элемента управления ReportViewer")</span><span class="sxs-lookup"><span data-stu-id="eb245-110">![Selecting ReportViewer control](../../../2014/reporting-services/media/windowsapp-toolboxreportviewer.png "Selecting ReportViewer control")</span></span>  
  
3.  <span data-ttu-id="eb245-111">Перетащите элемент управления ReportViewer в область конструктора Windows Form.</span><span class="sxs-lookup"><span data-stu-id="eb245-111">Drag the ReportViewer control onto the design surface of the Windows Form.</span></span>  
  
     <span data-ttu-id="eb245-112">В форму будет добавлен элемент управления ReportViewer с именем reportViewer1.</span><span class="sxs-lookup"><span data-stu-id="eb245-112">A ReportViewer control named reportViewer1 is added to the form.</span></span>  
  
 <span data-ttu-id="eb245-113">После добавления элемента управления в форму появляется смарт-тег **Задачи ReportViewer** и выводится приглашение выбрать отчет.</span><span class="sxs-lookup"><span data-stu-id="eb245-113">After the control is added to the form, the **ReportViewer Tasks** smart tag appears and prompts you to select a report.</span></span>  
  
 <span data-ttu-id="eb245-114">Если отчет, который требуется просмотреть, был развернут на сервере отчетов, выберите **\<Server Report>** параметр из раскрывающегося списка **Выбор отчета** .</span><span class="sxs-lookup"><span data-stu-id="eb245-114">If the report you wish to view has been deployed to a report server, select the **\<Server Report>** option from the **Choose Report** drop-down list.</span></span> <span data-ttu-id="eb245-115">После **\<Server Report>** выбора параметра появляются два дополнительных свойства: **URL-адрес сервера отчетов** и **путь к отчету**.</span><span class="sxs-lookup"><span data-stu-id="eb245-115">After the **\<Server Report>** option is selected, two additional properties appear: **Report Server Url** and **Report Path**.</span></span> <span data-ttu-id="eb245-116">Свойство **URL-адрес сервера отчетов** задает адрес сервера отчетов, а свойство **Путь к отчету** задает полный путь к подготавливаемому к просмотру отчету.</span><span class="sxs-lookup"><span data-stu-id="eb245-116">The **Report Server Url** is the address to the report server and the **Report Path** is the full path to the report to render.</span></span>  
  
 <span data-ttu-id="eb245-117">![Выбор серверного отчета](../../../2014/reporting-services/media/windowsapp-serverreportsettings.png "Выбор серверного отчета")</span><span class="sxs-lookup"><span data-stu-id="eb245-117">![Select server report](../../../2014/reporting-services/media/windowsapp-serverreportsettings.png "Select server report")</span></span>  
  
 <span data-ttu-id="eb245-118">Если просматриваемый отчет является отчетом в локальном режиме, выберите параметр **Создать новый отчет** для запуска конструктора отчетов или отчет, который уже является частью существующего проекта.</span><span class="sxs-lookup"><span data-stu-id="eb245-118">If the report you wish to view a report in local mode, select either the **Design a new report** option to launch the report designer or select a report that is already part of the existing project.</span></span>  
  
 <span data-ttu-id="eb245-119">![Выбор локального отчета](../../../2014/reporting-services/media/windowsapp-localreportsettings.png "Выбор локального отчета")</span><span class="sxs-lookup"><span data-stu-id="eb245-119">![Select local report](../../../2014/reporting-services/media/windowsapp-localreportsettings.png "Select local report")</span></span>  
  
## <a name="viewing-reports-in-remote-processing-mode"></a><span data-ttu-id="eb245-120">Просмотр отчетов в режиме удаленной обработки</span><span class="sxs-lookup"><span data-stu-id="eb245-120">Viewing Reports in Remote Processing Mode</span></span>  
 <span data-ttu-id="eb245-121">В следующем примере показана подготовка к просмотру отчета, развернутого на сервере отчетов при помощи элемента управления WinForms ReportViewer.</span><span class="sxs-lookup"><span data-stu-id="eb245-121">The following example demonstrates how to render a report that has been deployed to a report server using the WinForms ReportViewer control.</span></span> <span data-ttu-id="eb245-122">В этом примере используется отчет Sales Order Detail, который включен в проект с образцами отчетов [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eb245-122">This example uses the Sales Order Detail report that is included with the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample reports project.</span></span>  
  
```csharp  
public partial class Form1 : Form  
{  
    private void Form1_Load(object sender, EventArgs e)  
    {  
        // Set the processing mode for the ReportViewer to Remote  
        reportViewer1.ProcessingMode = ProcessingMode.Remote;  
  
        ServerReport serverReport = reportViewer1.ServerReport;  
  
        // Get a reference to the default credentials  
        System.Net.ICredentials credentials =  
            System.Net.CredentialCache.DefaultCredentials;  
  
        // Get a reference to the report server credentials  
        ReportServerCredentials rsCredentials =  
            serverReport.ReportServerCredentials;  
  
        // Set the credentials for the server report  
        rsCredentials.NetworkCredentials = credentials;  
  
        // Set the report server URL and report path  
        serverReport.ReportServerUrl =   
            new Uri("http:// <Server Name>/reportserver");  
        serverReport.ReportPath =   
            "/AdventureWorks Sample Reports/Sales Order Detail";  
  
        // Create the sales order number report parameter  
        ReportParameter salesOrderNumber = new ReportParameter();  
        salesOrderNumber.Name = "SalesOrderNumber";  
        salesOrderNumber.Values.Add("SO43661");  
  
        // Set the report parameters for the report  
        reportViewer1.ServerReport.SetParameters(  
            new ReportParameter[] { salesOrderNumber });  
  
        // Refresh the report  
        reportViewer1.RefreshReport();  
    }  
}  
```  
  
```vb  
Imports Microsoft.Reporting.WinForms  
  
Public Class Form1  
  
    Private Sub Form1_Load(ByVal sender As System.Object, _  
                           ByVal e As System.EventArgs) _  
                           Handles MyBase.Load  
  
        'Set the processing mode for the ReportViewer to Remote  
        reportViewer1.ProcessingMode = ProcessingMode.Remote  
  
        Dim serverReport As ServerReport  
        serverReport = reportViewer1.ServerReport  
  
        'Get a reference to the default credentials  
        Dim credentials As System.Net.ICredentials  
        credentials = System.Net.CredentialCache.DefaultCredentials  
  
        'Get a reference to the report server credentials  
        Dim rsCredentials As ReportServerCredentials  
        rsCredentials = serverReport.ReportServerCredentials  
  
        'Set the credentials for the server report  
        rsCredentials.NetworkCredentials = credentials  
  
        'Set the report server URL and report path  
        serverReport.ReportServerUrl = _  
           New Uri("http://<Server Name>/reportserver")  
        serverReport.ReportPath = _  
           "/AdventureWorks Sample Reports/Sales Order Detail"  
  
        'Create the sales order number report parameter  
        Dim salesOrderNumber As New ReportParameter()  
        salesOrderNumber.Name = "SalesOrderNumber"  
        salesOrderNumber.Values.Add("SO43661")  
  
        'Set the report parameters for the report  
        Dim parameters() As ReportParameter = {salesOrderNumber}  
        serverReport.SetParameters(parameters)  
  
        'Refresh the report  
        reportViewer1.RefreshReport()  
    End Sub  
  
End Class  
```  
  
## <a name="viewing-reports-in-local-processing-mode"></a><span data-ttu-id="eb245-123">Просмотр отчетов в режиме локальной обработки</span><span class="sxs-lookup"><span data-stu-id="eb245-123">Viewing Reports in Local Processing Mode</span></span>  
 <span data-ttu-id="eb245-124">В следующем примере показана подготовка к просмотру отчета, который является частью приложения Windows и не был помещен на сервер отчетов.</span><span class="sxs-lookup"><span data-stu-id="eb245-124">The following example demonstrates how to render a report that is part of the Windows application and has not been deployed to a report server.</span></span>  
  
###### <a name="to-add-the-sales-order-detail-report-to-a-windows-application"></a><span data-ttu-id="eb245-125">Добавление отчета «Сведения о заказе на продажу» в приложение Windows</span><span class="sxs-lookup"><span data-stu-id="eb245-125">To add the Sales Order Detail report to a Windows application</span></span>  
  
1.  <span data-ttu-id="eb245-126">Открыть проект Windows, в который будет добавлен отчет.</span><span class="sxs-lookup"><span data-stu-id="eb245-126">Open the Windows project to which the report will be added.</span></span>  
  
2.  <span data-ttu-id="eb245-127">В меню **Проект** выберите пункт **Добавить существующий элемент**.</span><span class="sxs-lookup"><span data-stu-id="eb245-127">From the **Project** menu, select **Add Existing Item**.</span></span>  
  
3.  <span data-ttu-id="eb245-128">Перейти в папку, в которой были установлены проекты образцов отчетов [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eb245-128">Browse to the location where you installed the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] Report Samples project.</span></span>  
  
     <span data-ttu-id="eb245-129">Чтобы скачать примеры отчетов, перейдите в раздел [Примеры отчетов AdventureWorks 2012](https://go.microsoft.com/fwlink/?LinkId=404153).</span><span class="sxs-lookup"><span data-stu-id="eb245-129">The download the report samples, go to [AdventureWorks 2012 Report Samples](https://go.microsoft.com/fwlink/?LinkId=404153)</span></span>  
  
4.  <span data-ttu-id="eb245-130">Выберите файл Sales Order Detail.rdl и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="eb245-130">Select the Sales Order Detail.rdl file and click the **Add** button.</span></span>  
  
     <span data-ttu-id="eb245-131">Файл «Сведения о заказе на продажу.rdl» теперь станет частью проекта.</span><span class="sxs-lookup"><span data-stu-id="eb245-131">The Sales Order Detail.rdl file should now be part of the project.</span></span>  
  
     <span data-ttu-id="eb245-132">![Отчет со сведениями о заказе](../../../2014/reporting-services/media/windowsapp-salesorderdetailreport.png "Отчет со сведениями о заказе")</span><span class="sxs-lookup"><span data-stu-id="eb245-132">![Sales Order Detail Report](../../../2014/reporting-services/media/windowsapp-salesorderdetailreport.png "Sales Order Detail Report")</span></span>  
  
5.  <span data-ttu-id="eb245-133">Щелкните правой кнопкой мыши файл Sales Order Detail.rdl в обозревателе решений и выберите команду **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="eb245-133">Right-click the Sales Order Detail.rdl file in Solution Explorer and select **Rename**.</span></span> <span data-ttu-id="eb245-134">Переименуйте отчет в **Сведения о заказах на продажу.rdlc** и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="eb245-134">Rename the report to **Sales Order Detail.rdlc** and press ENTER.</span></span>  
  
     <span data-ttu-id="eb245-135">Если обозреватель решений не отображается, его можно открыть из меню **Вид**, выбрав пункт **Обозреватель решений**.</span><span class="sxs-lookup"><span data-stu-id="eb245-135">If Solution Explorer is not visible, you can open it from the **View** menu by selecting **Solution Explorer**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="eb245-136">Переименование расширения из rdl в rdlc позволит редактировать отчет при помощи конструктора отчетов для [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[vsprvslong](../../includes/vsprvslong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eb245-136">Renaming the file extension from rdl to rdlc will allow you to edit the report using report designer for [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[vsprvslong](../../includes/vsprvslong-md.md)].</span></span>  
  
6.  <span data-ttu-id="eb245-137">После переименования отчета выберите файл и перейдите в окно «Свойства».</span><span class="sxs-lookup"><span data-stu-id="eb245-137">After the report has been renamed, select the file and locate the Properties window.</span></span> <span data-ttu-id="eb245-138">Для свойства **Копировать в выходной каталог** задайте значение **Копировать более новые**.</span><span class="sxs-lookup"><span data-stu-id="eb245-138">Change the **Copy to Output Directory** property to **Copy if Newer**.</span></span>  
  
     <span data-ttu-id="eb245-139">![Настройка копирования в выходной параметр](../../../2014/reporting-services/media/windowsapp-copytooutputsetting.png "Настройка копирования в выходной параметр")</span><span class="sxs-lookup"><span data-stu-id="eb245-139">![Configuring Copy To Output setting](../../../2014/reporting-services/media/windowsapp-copytooutputsetting.png "Configuring Copy To Output setting")</span></span>  
  
     <span data-ttu-id="eb245-140">Если окно **Свойства** не отображается, можно открыть его из меню **Вид**, выбрав **Окно "Свойства"**.</span><span class="sxs-lookup"><span data-stu-id="eb245-140">If the **Properties** window is not visible, you can open it from the **View** menu by selecting **Properties Window**.</span></span>  
  
 <span data-ttu-id="eb245-141">В следующем примере кода создается набор данных для данных о заказе на продажу, а затем подготавливается к просмотру отчет «Сведения о заказе на продажу» в локальном режиме.</span><span class="sxs-lookup"><span data-stu-id="eb245-141">The following code example will create a dataset for the sales order data and then render the Sales Order Detail report in local mode.</span></span>  
  
```csharp  
public partial class Form1 : Form  
{  
    private void Form1_Load(object sender, EventArgs e)  
    {  
        // Set the processing mode for the ReportViewer to Local  
        reportViewer1.ProcessingMode = ProcessingMode.Local;  
  
        LocalReport localReport = reportViewer1.LocalReport;  
  
        localReport.ReportPath = "Sales Order Detail.rdlc";  
  
        DataSet dataset = new DataSet("Sales Order Detail");  
  
        string salesOrderNumber = "SO43661";  
  
        // Get the sales order data  
        GetSalesOrderData(salesOrderNumber, ref dataset);  
  
        // Create a report data source for the sales order data  
        ReportDataSource dsSalesOrder = new ReportDataSource();  
        dsSalesOrder.Name = "SalesOrder";  
        dsSalesOrder.Value = dataset.Tables["SalesOrder"];  
  
        localReport.DataSources.Add(dsSalesOrder);  
  
        // Get the sales order detail data  
        GetSalesOrderDetailData(salesOrderNumber, ref dataset);  
  
        // Create a report data source for the sales order detail   
        // data  
        ReportDataSource dsSalesOrderDetail =  
            new ReportDataSource();  
        dsSalesOrderDetail.Name = "SalesOrderDetail";  
        dsSalesOrderDetail.Value =  
            dataset.Tables["SalesOrderDetail"];  
  
        localReport.DataSources.Add(dsSalesOrderDetail);  
  
        // Create a report parameter for the sales order number   
        ReportParameter rpSalesOrderNumber = new ReportParameter();  
        rpSalesOrderNumber.Name = "SalesOrderNumber";  
        rpSalesOrderNumber.Values.Add("SO43661");  
  
        // Set the report parameters for the report  
        localReport.SetParameters(  
            new ReportParameter[] { rpSalesOrderNumber });  
  
        // Refresh the report  
        reportViewer1.RefreshReport();  
    }  
  
    private void GetSalesOrderData(string salesOrderNumber,  
                                   ref DataSet dsSalesOrder)  
    {  
        string sqlSalesOrder =  
            "SELECT SOH.SalesOrderNumber, S.Name AS Store, " +  
            "       SOH.OrderDate, C.FirstName AS SalesFirstName, " +  
            "       C.LastName AS SalesLastName, E.Title AS " +  
            "       SalesTitle, SOH.PurchaseOrderNumber, " +  
            "       SM.Name AS ShipMethod, BA.AddressLine1 " +  
            "       AS BillAddress1, BA.AddressLine2 AS " +  
            "       BillAddress2, BA.City AS BillCity, " +  
            "       BA.PostalCode AS BillPostalCode, BSP.Name " +  
            "       AS BillStateProvince, BCR.Name AS " +  
            "       BillCountryRegion, SA.AddressLine1 AS " +  
            "       ShipAddress1, SA.AddressLine2 AS " +  
            "       ShipAddress2, SA.City AS ShipCity, " +  
            "       SA.PostalCode AS ShipPostalCode, SSP.Name " +  
            "       AS ShipStateProvince, SCR.Name AS " +  
            "       ShipCountryRegion, CC.Phone AS CustPhone, " +  
            "       CC.FirstName AS CustFirstName, CC.LastName " +  
            "       AS CustLastName " +  
            "FROM   Person.Address SA INNER JOIN " +  
            "       Person.StateProvince SSP ON " +  
            "       SA.StateProvinceID = SSP.StateProvinceID " +  
            "       INNER JOIN Person.CountryRegion SCR ON " +  
            "       SSP.CountryRegionCode = SCR.CountryRegionCode " +  
            "       RIGHT OUTER JOIN Sales.SalesOrderHeader SOH " +  
            "       LEFT OUTER JOIN  Person.Contact CC ON " +  
            "       SOH.ContactID = CC.ContactID LEFT OUTER JOIN" +  
            "       Person.Address BA INNER JOIN " +  
            "       Person.StateProvince BSP ON " +  
            "       BA.StateProvinceID = BSP.StateProvinceID " +  
            "       INNER JOIN Person.CountryRegion BCR ON " +  
            "       BSP.CountryRegionCode = " +  
            "       BCR.CountryRegionCode ON SOH.BillToAddressID " +  
            "       = BA.AddressID ON  SA.AddressID = " +  
            "       SOH.ShipToAddressID LEFT OUTER JOIN " +  
            "       Person.Contact C RIGHT OUTER JOIN " +  
            "       HumanResources.Employee E ON C.ContactID = " +  
            "       E.ContactID ON SOH.SalesPersonID = " +  
            "       E.EmployeeID LEFT OUTER JOIN " +  
            "       Purchasing.ShipMethod SM ON SOH.ShipMethodID " +  
            "       = SM.ShipMethodID LEFT OUTER JOIN Sales.Store" +  
            "        S ON SOH.CustomerID = S.CustomerID " +  
            "WHERE  (SOH.SalesOrderNumber = @SalesOrderNumber)";  
  
        SqlConnection connection = new  
            SqlConnection("Data Source=(local); " +  
                          "Initial Catalog=AdventureWorks; " +  
                          "Integrated Security=SSPI");  
  
        SqlCommand command =  
            new SqlCommand(sqlSalesOrder, connection);  
  
        command.Parameters.Add(  
            new SqlParameter("SalesOrderNumber",  
            salesOrderNumber));  
  
        SqlDataAdapter salesOrderAdapter = new  
            SqlDataAdapter(command);  
  
        salesOrderAdapter.Fill(dsSalesOrder, "SalesOrder");  
    }  
  
    private void GetSalesOrderDetailData(string salesOrderNumber,  
                           ref DataSet dsSalesOrder)  
    {  
        string sqlSalesOrderDetail =  
            "SELECT  SOD.SalesOrderDetailID, SOD.OrderQty, " +  
            "        SOD.UnitPrice, CASE WHEN " +  
            "        SOD.UnitPriceDiscount IS NULL THEN 0 " +  
            "        ELSE SOD.UnitPriceDiscount END AS " +  
            "        UnitPriceDiscount, SOD.LineTotal, " +  
            "        SOD.CarrierTrackingNumber, " +  
            "        SOD.SalesOrderID, P.Name, P.ProductNumber " +  
            "FROM    Sales.SalesOrderDetail SOD INNER JOIN " +  
            "        Production.Product P ON SOD.ProductID = " +  
            "        P.ProductID INNER JOIN " +  
            "        Sales.SalesOrderHeader SOH ON " +  
            "        SOD.SalesOrderID = SOH.SalesOrderID " +  
            "WHERE   (SOH.SalesOrderNumber = @SalesOrderNumber) " +  
            "ORDER BY SOD.SalesOrderDetailID";  
  
        using (SqlConnection connection = new  
            SqlConnection("Data Source=(local); " +  
                          "Initial Catalog=AdventureWorks; " +  
                          "Integrated Security=SSPI"))  
        {  
  
            SqlCommand command =  
                new SqlCommand(sqlSalesOrderDetail, connection);  
  
            command.Parameters.Add(  
                new SqlParameter("SalesOrderNumber",  
                salesOrderNumber));  
  
            SqlDataAdapter salesOrderDetailAdapter = new  
                SqlDataAdapter(command);  
  
            salesOrderDetailAdapter.Fill(dsSalesOrder,  
                "SalesOrderDetail");  
        }  
    }  
}  
```  
  
```vb  
Imports System.Data.SqlClient  
Imports Microsoft.Reporting.WinForms  
  
Public Class Form1  
  
    Private Sub Form1_Load(ByVal sender As System.Object, _  
                        ByVal e As System.EventArgs) _  
                        Handles MyBase.Load  
  
        'Set the processing mode for the ReportViewer to Local  
        reportViewer1.ProcessingMode = ProcessingMode.Local  
  
        Dim localReport As LocalReport  
        localReport = reportViewer1.LocalReport  
  
        localReport.ReportEmbeddedResource = _  
            "ReportViewerIntro.Sales Order Detail.rdlc"  
  
        Dim dataset As New DataSet("Sales Order Detail")  
  
        Dim salesOrderNumber As String = "SO43661"  
  
        'Get the sales order data  
        GetSalesOrderData(salesOrderNumber, dataset)  
  
        'Create a report data source for the sales order data  
        Dim dsSalesOrder As New ReportDataSource()  
        dsSalesOrder.Name = "SalesOrder"  
        dsSalesOrder.Value = dataset.Tables("SalesOrder")  
  
        localReport.DataSources.Add(dsSalesOrder)  
  
        'Get the sales order detail data  
        GetSalesOrderDetailData(salesOrderNumber, dataset)  
  
        'Create a report data source for the sales   
        'order detail data  
        Dim dsSalesOrderDetail As New ReportDataSource()  
        dsSalesOrderDetail.Name = "SalesOrderDetail"  
        dsSalesOrderDetail.Value = _  
            dataset.Tables("SalesOrderDetail")  
  
        localReport.DataSources.Add(dsSalesOrderDetail)  
  
        'Create a report parameter for the sales order number   
        Dim rpSalesOrderNumber As New ReportParameter()  
        rpSalesOrderNumber.Name = "SalesOrderNumber"  
        rpSalesOrderNumber.Values.Add("SO43661")  
  
        'Set the report parameters for the report  
        Dim parameters() As ReportParameter = {rpSalesOrderNumber}  
        localReport.SetParameters(parameters)  
  
        'Refresh the report  
        reportViewer1.RefreshReport()  
  
    End Sub  
  
    Private Sub GetSalesOrderData(ByVal salesOrderNumber As String, _  
                               ByRef dsSalesOrder As DataSet)  
  
        Dim sqlSalesOrder As String = _  
            "SELECT SOH.SalesOrderNumber, S.Name AS Store, " & _  
            "       SOH.OrderDate, C.FirstName AS SalesFirstName, " & _  
            "       C.LastName AS SalesLastName, E.Title AS " & _  
            "       SalesTitle, SOH.PurchaseOrderNumber, " & _  
            "       SM.Name AS ShipMethod, BA.AddressLine1 " & _  
            "       AS BillAddress1, BA.AddressLine2 AS " & _  
            "       BillAddress2, BA.City AS BillCity, " & _  
            "       BA.PostalCode AS BillPostalCode, BSP.Name " & _  
            "       AS BillStateProvince, BCR.Name AS " & _  
            "       BillCountryRegion, SA.AddressLine1 AS " & _  
            "       ShipAddress1, SA.AddressLine2 AS " & _  
            "       ShipAddress2, SA.City AS ShipCity, " & _  
            "       SA.PostalCode AS ShipPostalCode, SSP.Name " & _  
            "       AS ShipStateProvince, SCR.Name AS " & _  
            "       ShipCountryRegion, CC.Phone AS CustPhone, " & _  
            "       CC.FirstName AS CustFirstName, CC.LastName " & _  
            "       AS CustLastName " & _  
            "FROM   Person.Address SA INNER JOIN " & _  
            "       Person.StateProvince SSP ON " & _  
            "       SA.StateProvinceID = SSP.StateProvinceID " & _  
            "       INNER JOIN Person.CountryRegion SCR ON " & _  
            "       SSP.CountryRegionCode = SCR.CountryRegionCode " & _  
            "       RIGHT OUTER JOIN Sales.SalesOrderHeader SOH " & _  
            "       LEFT OUTER JOIN  Person.Contact CC ON " & _  
            "       SOH.ContactID = CC.ContactID LEFT OUTER JOIN" & _  
            "       Person.Address BA INNER JOIN " & _  
            "       Person.StateProvince BSP ON " & _  
            "       BA.StateProvinceID = BSP.StateProvinceID " & _  
            "       INNER JOIN Person.CountryRegion BCR ON " & _  
            "       BSP.CountryRegionCode = " & _  
            "       BCR.CountryRegionCode ON SOH.BillToAddressID " & _  
            "       = BA.AddressID ON  SA.AddressID = " & _  
            "       SOH.ShipToAddressID LEFT OUTER JOIN " & _  
            "       Person.Contact C RIGHT OUTER JOIN " & _  
            "       HumanResources.Employee E ON C.ContactID = " & _  
            "       E.ContactID ON SOH.SalesPersonID = " & _  
            "       E.EmployeeID LEFT OUTER JOIN " & _  
            "       Purchasing.ShipMethod SM ON SOH.ShipMethodID " & _  
            "       = SM.ShipMethodID LEFT OUTER JOIN Sales.Store" & _  
            "        S ON SOH.CustomerID = S.CustomerID " & _  
            "WHERE  (SOH.SalesOrderNumber = @SalesOrderNumber)"  
  
        Using connection As New SqlConnection( _  
                      "Data Source=(local); " & _  
                      "Initial Catalog=AdventureWorks; " & _  
                      "Integrated Security=SSPI")  
  
            Dim command As New SqlCommand(sqlSalesOrder, connection)  
  
            Dim parameter As New SqlParameter("SalesOrderNumber", _  
                salesOrderNumber)  
            command.Parameters.Add(parameter)  
  
            Dim salesOrderAdapter As New SqlDataAdapter(command)  
  
            salesOrderAdapter.Fill(dsSalesOrder, "SalesOrder")  
  
        End Using  
  
    End Sub  
  
    Private Sub GetSalesOrderDetailData( _  
                           ByVal salesOrderNumber As String, _  
                           ByRef dsSalesOrder As DataSet)  
  
        Dim sqlSalesOrderDetail As String = _  
            "SELECT  SOD.SalesOrderDetailID, SOD.OrderQty, " & _  
            "        SOD.UnitPrice, CASE WHEN " & _  
            "        SOD.UnitPriceDiscount IS NULL THEN 0 " & _  
            "        ELSE SOD.UnitPriceDiscount END AS " & _  
            "        UnitPriceDiscount, SOD.LineTotal, " & _  
            "        SOD.CarrierTrackingNumber, " & _  
            "        SOD.SalesOrderID, P.Name, P.ProductNumber " & _  
            "FROM    Sales.SalesOrderDetail SOD INNER JOIN " & _  
            "        Production.Product P ON SOD.ProductID = " & _  
            "        P.ProductID INNER JOIN " & _  
            "        Sales.SalesOrderHeader SOH ON " & _  
            "        SOD.SalesOrderID = SOH.SalesOrderID " & _  
            "WHERE   (SOH.SalesOrderNumber = @SalesOrderNumber) " & _  
            "ORDER BY SOD.SalesOrderDetailID"  
  
        Using connection As New SqlConnection( _  
                      "Data Source=(local); " & _  
                      "Initial Catalog=AdventureWorks; " & _  
                      "Integrated Security=SSPI")  
  
            Dim command As New SqlCommand(sqlSalesOrderDetail, _  
                                          connection)  
  
            Dim parameter As New SqlParameter("SalesOrderNumber", _  
                salesOrderNumber)  
            command.Parameters.Add(parameter)  
  
            Dim salesOrderDetailAdapter As New SqlDataAdapter(command)  
  
            salesOrderDetailAdapter.Fill(dsSalesOrder, _  
                "SalesOrderDetail")  
  
        End Using  
  
    End Sub  
  
End Class  
```  
  
## <a name="see-also"></a><span data-ttu-id="eb245-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="eb245-142">See Also</span></span>  
 [<span data-ttu-id="eb245-143">Интеграция служб Reporting Services с помощью элементов управления ReportViewer</span><span class="sxs-lookup"><span data-stu-id="eb245-143">Integrating Reporting Services Using the ReportViewer Controls</span></span>](../application-integration/integrating-reporting-services-using-reportviewer-controls.md)  
  
  
