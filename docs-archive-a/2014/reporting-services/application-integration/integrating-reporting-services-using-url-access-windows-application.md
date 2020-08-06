---
title: Использование доступа по URL-адресу в приложении Windows | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Windows applications [Reporting Services]
- Web Browser controls [Reporting Services]
- Windows Forms [Reporting Services]
- browser controls [Reporting Services]
- URL access [Reporting Services], Windows applications
ms.assetid: a4b222e5-0cbd-409c-92c4-046a674db8ac
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8f8b901481b1d6fcc3cdd8626b43cd3a69174c1a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735129"
---
# <a name="using-url-access-in-a-windows-application"></a><span data-ttu-id="2de33-102">Использование доступа по URL-адресу в приложении Windows</span><span class="sxs-lookup"><span data-stu-id="2de33-102">Using URL Access in a Windows Application</span></span>
  <span data-ttu-id="2de33-103">Доступ к серверу отчетов по URL-адресу оптимизирован для веб-среды, его также можно использовать для внедрения отчетов служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] в приложение [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="2de33-103">Although URL access to a report server is optimized for a Web environment, you can also use URL access to embed [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] reports into a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows application.</span></span> <span data-ttu-id="2de33-104">Однако для доступа по URL-адресу, в котором используется Windows Forms, по-прежнему необходимо применение технологии веб-браузера.</span><span class="sxs-lookup"><span data-stu-id="2de33-104">However, URL access that involves Windows Forms still requires that you use Web browser technology.</span></span> <span data-ttu-id="2de33-105">Для интеграции доступа по URL-адресу и Windows Forms можно использовать следующие сценарии.</span><span class="sxs-lookup"><span data-stu-id="2de33-105">You can use the following integration scenarios with URL access and Windows Forms:</span></span>  
  
-   <span data-ttu-id="2de33-106">Отображение отчета из приложения Windows Forms путем программного запуска веб-браузера.</span><span class="sxs-lookup"><span data-stu-id="2de33-106">Display a report from a Windows Form application by starting a Web browser programmatically.</span></span>  
  
-   <span data-ttu-id="2de33-107">Использование элемента управления <xref:System.Windows.Forms.WebBrowser> на форме Windows Forms для отображения отчета.</span><span class="sxs-lookup"><span data-stu-id="2de33-107">Use the <xref:System.Windows.Forms.WebBrowser> control on a Windows Form to display a report.</span></span>  
  
## <a name="starting-internet-explorer-from-a-windows-form"></a><span data-ttu-id="2de33-108">Запуск обозревателя Internet Explorer из формы Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2de33-108">Starting Internet Explorer from a Windows Form</span></span>  
 <span data-ttu-id="2de33-109">С помощью класса <xref:System.Diagnostics.Process> можно получить доступ к процессу, выполняющемуся на компьютере.</span><span class="sxs-lookup"><span data-stu-id="2de33-109">You can use the <xref:System.Diagnostics.Process> class to access a process that is running on a computer.</span></span> <span data-ttu-id="2de33-110"><xref:System.Diagnostics.Process>Класс является полезной [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] конструкцией для запуска, остановки, управления и мониторинга приложений.</span><span class="sxs-lookup"><span data-stu-id="2de33-110">The <xref:System.Diagnostics.Process> class is a useful [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] construct for starting, stopping, controlling, and monitoring applications.</span></span> <span data-ttu-id="2de33-111">Чтобы просмотреть определенный отчет в базе данных сервера отчетов, можно запустить процесс **IExplore**, передав URL-адрес отчета.</span><span class="sxs-lookup"><span data-stu-id="2de33-111">To view a specific report in your report server database, you can start the **IExplore** process, passing in the URL to the report.</span></span> <span data-ttu-id="2de33-112">С помощью следующего примера кода можно запустить обозреватель [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Explorer и передать определенный URL-адрес отчета, когда пользователь нажимает кнопку на форме Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="2de33-112">The following code example can be used to start [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Explorer and pass a specific report URL when the user clicks a button on a Windows Form.</span></span>  
  
```vb  
Private Sub viewReportButton_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles viewReportButton.Click  
   ' Build the URL access string based on values supplied by a user  
   Dim url As String = serverUrlTextBox.Text + "?" & reportPathTextBox.Text & _  
   "&rs:Command=Render" & "&rs:Format=HTML4.0"  
  
   ' If the user does not select the toolbar check box,  
   ' turn the toolbar off in the HTML Viewer  
   If toolbarCheckBox.Checked = False Then  
      url += "&rc:Toolbar=False"  
   End If  
   ' load report in the Web browser  
   Try  
      System.Diagnostics.Process.Start("IExplore", url)  
   Catch  
      MessageBox.Show("The system could not start the specified report using Internet Explorer.", _  
      "An error has occurred", MessageBoxButtons.OK, MessageBoxIcon.Error)  
   End Try  
End Sub 'viewReportButton_Click  
```  
  
```csharp  
// Sample click event for a Button control on a Windows Form  
private void viewReportButton_Click(object sender, System.EventArgs e)  
{  
   // Build the URL access string based on values supplied by a user  
   string url = serverUrlTextBox.Text + "?" + reportPathTextBox.Text +  
      "&rs:Command=Render" + "&rs:Format=HTML4.0";  
  
   // If the user does not check the toolbar check box,  
   // turn the toolbar off in the HTML Viewer  
   if (toolbarCheckBox.Checked == false)  
      url += "&rc:Toolbar=False";  
  
   // load report in the Web browser  
   try  
   {  
      System.Diagnostics.Process.Start("IExplore", url);  
   }  
  
   catch (Exception)  
   {  
      MessageBox.Show(  
         "The system could not open the specified report using Internet Explorer.",   
         "An error has occurred", MessageBoxButtons.OK, MessageBoxIcon.Error);  
   }  
}  
```  
  
## <a name="embedding-a-browser-control-on-a-windows-form"></a><span data-ttu-id="2de33-113">Внедрение элемента управления браузера в форму Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2de33-113">Embedding a Browser Control on a Windows Form</span></span>  
 <span data-ttu-id="2de33-114">Если не требуется просматривать отчет во внешнем веб-браузере, то можно обеспечить безукоризненное внедрение веб-браузера в форму Windows Forms с использованием элемента управления <xref:System.Windows.Forms.WebBrowser>.</span><span class="sxs-lookup"><span data-stu-id="2de33-114">If you do not want to view your report in an external Web browser, you can embed a Web browser seamlessly as part of your Windows Form using the <xref:System.Windows.Forms.WebBrowser> control.</span></span>  
  
###### <a name="to-add-the-webbrowser-control-to-your-windows-form"></a><span data-ttu-id="2de33-115">Добавление элемента управления WebBrowser в форму Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2de33-115">To add the WebBrowser control to your Windows Form</span></span>  
  
1.  <span data-ttu-id="2de33-116">Создайте новое приложение Windows в либо в, либо в [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csprcs](../../includes/csprcs-md.md)] [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2de33-116">Create a new Windows application in either [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csprcs](../../includes/csprcs-md.md)] or [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)].</span></span>  
  
2.  <span data-ttu-id="2de33-117">Перейдите к элементу управления <xref:System.Windows.Forms.WebBrowser> в диалоговом окне **Область элементов**.</span><span class="sxs-lookup"><span data-stu-id="2de33-117">Locate the <xref:System.Windows.Forms.WebBrowser> control in the **Toolbox** Dialog Box.</span></span>  
  
     <span data-ttu-id="2de33-118">Если окно **Область элементов** скрыто, его можно вызвать, выбрав в меню **Вид** пункт **Область элементов**.</span><span class="sxs-lookup"><span data-stu-id="2de33-118">If the **Toolbox** is not visible you can access it by clicking the **View** menu item and selecting **Toolbox**.</span></span>  
  
3.  <span data-ttu-id="2de33-119">Перетащите элемент управления <xref:System.Windows.Forms.WebBrowser> в область конструктора в Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="2de33-119">Drag the <xref:System.Windows.Forms.WebBrowser>control onto the design surface of your Windows Form.</span></span>  
  
     <span data-ttu-id="2de33-120">В форму будет добавлен элемент управления <xref:System.Windows.Forms.WebBrowser> с именем webBrowser1.</span><span class="sxs-lookup"><span data-stu-id="2de33-120">The <xref:System.Windows.Forms.WebBrowser>control named webBrowser1 is added to the Form</span></span>  
  
 <span data-ttu-id="2de33-121">Чтобы направить элемент управления <xref:System.Windows.Forms.WebBrowser> на URL-адрес, вызовите метод **Navigate**.</span><span class="sxs-lookup"><span data-stu-id="2de33-121">You direct the <xref:System.Windows.Forms.WebBrowser> control to a URL by calling its **Navigate** method.</span></span> <span data-ttu-id="2de33-122">Для элемента управления <xref:System.Windows.Forms.WebBrowser> можно назначить строку доступа по URL-адресу во время выполнения, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="2de33-122">You can assign a specific URL access string to your <xref:System.Windows.Forms.WebBrowser> control at run time as shown in the following example.</span></span>  
  
```vb  
Dim url As String = "http://localhost/reportserver?/" & _  
                    "AdventureWorks2012 Sample Reports/" & _  
                    "Company Sales&rs:Command=Render"  
WebBrowser1.Navigate(url)  
```  
  
```csharp  
string url = "http://localhost/reportserver?/" +  
             "AdventureWorks2012 Sample Reports/" +  
             "Company Sales&rs:Command=Render";  
webBrowser1.Navigate(url);  
```  
  
## <a name="see-also"></a><span data-ttu-id="2de33-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="2de33-123">See Also</span></span>  
 <span data-ttu-id="2de33-124">[Интеграция Reporting Services в приложения](../application-integration/integrating-reporting-services-into-applications.md) </span><span class="sxs-lookup"><span data-stu-id="2de33-124">[Integrating Reporting Services into Applications](../application-integration/integrating-reporting-services-into-applications.md) </span></span>  
 <span data-ttu-id="2de33-125">[Интеграция Reporting Services с использованием доступа по URL-адресу](integrating-reporting-services-using-url-access.md) </span><span class="sxs-lookup"><span data-stu-id="2de33-125">[Integrating Reporting Services Using URL Access](integrating-reporting-services-using-url-access.md) </span></span>  
 <span data-ttu-id="2de33-126">[Интеграция Reporting Services с помощью SOAP](integrating-reporting-services-using-soap.md) </span><span class="sxs-lookup"><span data-stu-id="2de33-126">[Integrating Reporting Services Using SOAP](integrating-reporting-services-using-soap.md) </span></span>  
 <span data-ttu-id="2de33-127">[Интеграция Reporting Services с помощью элементов управления ReportViewer](integrating-reporting-services-using-reportviewer-controls.md) </span><span class="sxs-lookup"><span data-stu-id="2de33-127">[Integrating Reporting Services Using the ReportViewer Controls](integrating-reporting-services-using-reportviewer-controls.md) </span></span>  
 [<span data-ttu-id="2de33-128">Доступ по URL-адресу (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="2de33-128">URL Access &#40;SSRS&#41;</span></span>](../url-access-ssrs.md)  
  
  
