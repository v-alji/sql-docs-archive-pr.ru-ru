---
title: Занятие 1. Создание проекта RDL-схемы Visual Studio | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f420509c-51aa-4170-8c25-64c2954f4bb9
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: a8411e3f0458ccda8c291d5c86a4467bb051a263
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727526"
---
# <a name="lesson-1-create-the-rdl-schema-visual-studio-project"></a><span data-ttu-id="edb69-102">Урок 1. Создание проекта схемы языка определения отчетов в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="edb69-102">Lesson 1: Create the RDL Schema Visual Studio Project</span></span>
  <span data-ttu-id="edb69-103">В этом учебнике будет создано простое приложение командной строки.</span><span class="sxs-lookup"><span data-stu-id="edb69-103">For this tutorial, you will create a simple console application.</span></span> <span data-ttu-id="edb69-104">В этом учебнике предполагается, что вы разрабатываете в [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="edb69-104">This tutorial assumes you are developing in [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="edb69-105">Чтобы обращаться к веб-службе сервера отчетов, работающей на сервере [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] с дополнительными службами, необходимо добавить «_SQLExpress» к пути «ReportServer».</span><span class="sxs-lookup"><span data-stu-id="edb69-105">When accessing the Report Server Web service running on [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] with Advanced Services, you must append "_SQLExpress" to the "ReportServer" path.</span></span> <span data-ttu-id="edb69-106">Пример:</span><span class="sxs-lookup"><span data-stu-id="edb69-106">For example:</span></span>  
>   
>  `http://myserver/reportserver_sqlexpress/reportservice2010.asmx"`  
  
### <a name="to-create-the-web-service-proxy"></a><span data-ttu-id="edb69-107">Создание учетной записи-посредника веб-службы</span><span class="sxs-lookup"><span data-stu-id="edb69-107">To create the web service proxy</span></span>  
  
1.  <span data-ttu-id="edb69-108">Выберите **Пуск** , **Все программы**, Microsoft Visual Studio 2010, а затем **Средства Visual Studio**и **Командная строка Visual Studio 2010**.</span><span class="sxs-lookup"><span data-stu-id="edb69-108">From the **Start** menu, select **All Programs**, then Microsoft Visual Studio, then **Visual Studio Tools**, and then **Visual Studio 2010 Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="edb69-109">Если используется C#, в окне командной строки выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="edb69-109">In the command prompt window, run the following command if you are using C#:</span></span>  
  
    ```  
    wsdl /language:CS /n:"ReportService2010" http://<Server Name>/reportserver/reportservice2010.asmx?wsdl  
    ```  
  
     <span data-ttu-id="edb69-110">Если используется Visual Basic, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="edb69-110">If you are using Visual Basic, then run the following command:</span></span>  
  
    ```  
    wsdl /language:VB /n:"ReportService2010" http://<Server Name>/reportserver/reportservice2010.asmx?wsdl  
    ```  
  
     <span data-ttu-id="edb69-111">Команда создаст файл с расширением CS или VB.</span><span class="sxs-lookup"><span data-stu-id="edb69-111">This command generates a .cs or .vb file.</span></span> <span data-ttu-id="edb69-112">Этот файл следует добавить к приложению.</span><span class="sxs-lookup"><span data-stu-id="edb69-112">You will add this file to your application.</span></span>  
  
### <a name="to-create-a-console-application"></a><span data-ttu-id="edb69-113">Создание приложения командной строки</span><span class="sxs-lookup"><span data-stu-id="edb69-113">To create a console application</span></span>  
  
1.  <span data-ttu-id="edb69-114">В меню **Файл** выберите **Создать**, а затем **Проект** , чтобы открыть диалоговое окно **Новый проект** .</span><span class="sxs-lookup"><span data-stu-id="edb69-114">On the **File** menu, point to **New**, and then click **Project** to open the **New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="edb69-115">В панели слева в разделе **Установленные шаблоны**щелкните узел **Visual Basic** или **Visual C#** и выберите категорию типов проекта из раскрывшегося списка.</span><span class="sxs-lookup"><span data-stu-id="edb69-115">In the left pane, under **Installed Templates**, click either **Visual Basic** or the **Visual C#** node, and select a category of project types from the expanded list.</span></span>  
  
3.  <span data-ttu-id="edb69-116">Выберите тип проекта **Консольное приложение** .</span><span class="sxs-lookup"><span data-stu-id="edb69-116">Choose the **Console Application** project type.</span></span>  
  
4.  <span data-ttu-id="edb69-117">В поле **Name** введите имя проекта.</span><span class="sxs-lookup"><span data-stu-id="edb69-117">In the **Name** box, enter a name for your project.</span></span> <span data-ttu-id="edb69-118">Введите имя `SampleRDLSchema` .</span><span class="sxs-lookup"><span data-stu-id="edb69-118">Type the name `SampleRDLSchema`.</span></span>  
  
5.  <span data-ttu-id="edb69-119">В поле **Расположение** введите путь, по которому будет сохранен проект, или нажмите кнопку **Обзор** , чтобы перейти в эту папку.</span><span class="sxs-lookup"><span data-stu-id="edb69-119">In the **Location** box, type the path where you want to save your project, or click **Browse** to navigate to the folder.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]<span data-ttu-id="edb69-120">В обозреватель решений отображается свернутое представление проекта.</span><span class="sxs-lookup"><span data-stu-id="edb69-120">A collapsed view of your project appears in Solution Explorer.</span></span>  
  
7.  <span data-ttu-id="edb69-121">В меню **Проект** выберите пункт **Добавить существующий элемент**.</span><span class="sxs-lookup"><span data-stu-id="edb69-121">On the **Project** menu, click **Add Existing Item**.</span></span>  
  
8.  <span data-ttu-id="edb69-122">Перейдите в папку, где находится созданный файл CS или VB, выберите файл и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="edb69-122">Navigate to the location for the .cs or .vb file you generated, then select the file, and then click **Add**.</span></span>  
  
     <span data-ttu-id="edb69-123">Также для обеспечения работоспособности веб-ссылки необходимо добавить ссылку на пространство имен <xref:System.Web.Services>.</span><span class="sxs-lookup"><span data-stu-id="edb69-123">You will also need to add a reference to the <xref:System.Web.Services> namespace for your Web reference to work.</span></span>  
  
9. <span data-ttu-id="edb69-124">В меню Проект щелкните команду **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="edb69-124">On the Project menu, click **Add Reference**.</span></span>  
  
     <span data-ttu-id="edb69-125">В диалоговом окне **Добавить ссылку** на вкладке **.NET** выберите **System.Web.Services**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="edb69-125">In the **Add Reference** dialog box, in the **.NET** tab, select **System.Web.Services**, then click **OK**.</span></span>  
  
     <span data-ttu-id="edb69-126">Дополнительные сведения о подключении к веб-службе сервера отчетов см. в разделе [Создание приложений с помощью веб-службы и .NET Framework](../reporting-services/report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md).</span><span class="sxs-lookup"><span data-stu-id="edb69-126">For more information about how to connect to the Report Server Web service, see [Building Applications Using the Web Service and the .NET Framework](../reporting-services/report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md).</span></span>  
  
10. <span data-ttu-id="edb69-127">Раскройте узел проекта в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="edb69-127">In Solution Explorer, expand the project node.</span></span> <span data-ttu-id="edb69-128">К проекту будет добавлен файл кода с именем по умолчанию Program.cs (Module1.vb для [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="edb69-128">You will see a code file with the default name of Program.cs (Module1.vb for [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) has been added to your project.</span></span>  
  
11. <span data-ttu-id="edb69-129">Откройте файл Program.cs (Module1.vb для [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) и замените код следующим.</span><span class="sxs-lookup"><span data-stu-id="edb69-129">Open the Program.cs (Module1.vb for [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) file and replace the code with the following:</span></span>  
  
     <span data-ttu-id="edb69-130">Следующий код обеспечивает заглушки методов, которые будут использоваться для выполнения функций загрузки, обновления и сохранения.</span><span class="sxs-lookup"><span data-stu-id="edb69-130">The following code provides the method stubs we will use to implement the Load, Update and Save functionality.</span></span>  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.IO;  
    using System.Text;  
    using System.Xml;  
    using System.Xml.Serialization;  
    using ReportService2010;  
  
    namespace SampleRDLSchema  
    {  
        class ReportUpdater  
        {  
            ReportingService2010 _reportService;  
  
            static void Main(string[] args)  
            {  
                ReportUpdater reportUpdater = new ReportUpdater();  
                reportUpdater.UpdateReport();  
            }  
  
            private void UpdateReport()  
            {  
                try  
                {  
                    // Set up the Report Service connection  
                    _reportService = new ReportingService2010();  
                    _reportService.Credentials =  
                        System.Net.CredentialCache.DefaultCredentials;  
                    _reportService.Url =  
                       "http://<Server Name>/reportserver/" +  
                                       "reportservice2010.asmx";  
  
                    // Call the methods to update a report definition  
                    LoadReportDefinition();  
                    UpdateReportDefinition();  
                    PublishReportDefinition();  
                }  
                catch (Exception ex)  
                {  
                    System.Console.WriteLine(ex.Message);  
                }  
            }  
  
            private void LoadReportDefinition()  
            {  
                //Lesson 3: Load a report definition from the report   
                //          catalog  
            }  
  
            private void UpdateReportDefinition()  
            {  
                //Lesson 4: Update the report definition using the    
                //          classes generated from the RDL Schema  
            }  
  
            private void PublishReportDefinition()  
            {  
                //Lesson 5: Publish the updated report definition back   
                //          to the report catalog  
            }  
        }  
    }  
    ```  
  
    ```vb  
    Imports System  
    Imports System.Collections.Generic  
    Imports System.IO  
    Imports System.Text  
    Imports System.Xml  
    Imports System.Xml.Serialization  
    Imports ReportService2010  
  
    Namespace SampleRDLSchema  
  
        Module ReportUpdater  
  
            Private m_reportService As ReportingService2010  
  
            Public Sub Main(ByVal args As String())  
  
                Try  
                    'Set up the Report Service connection  
                    m_reportService = New ReportingService2010  
                    m_reportService.Credentials = _  
                        System.Net.CredentialCache.DefaultCredentials  
                    m_reportService.Url = _  
                        "http:// <Server Name>/reportserver/" & _  
                               "reportservice2010.asmx"  
  
                    'Call the methods to update a report definition  
                    LoadReportDefinition()  
                    UpdateReportDefinition()  
                    PublishReportDefinition()  
                Catch ex As Exception  
                    System.Console.WriteLine(ex.Message)  
                End Try  
  
            End Sub  
  
            Private Sub LoadReportDefinition()  
                'Lesson 3: Load a report definition from the report   
                '          catalog  
            End Sub  
  
            Private Sub UpdateReportDefinition()  
                'Lesson 4: Update the report definition using the   
                '          classes generated from the RDL Schema  
            End Sub  
  
            Private Sub PublishReportDefinition()  
                'Lesson 5: Publish the updated report definition back   
                '          to the report catalog  
            End Sub  
  
        End Module  
  
    End Namespace   
    ```  
  
## <a name="next-lesson"></a><span data-ttu-id="edb69-131">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="edb69-131">Next Lesson</span></span>  
 <span data-ttu-id="edb69-132">На следующем занятии предстоит использовать программу определения XML-схемы (Xsd.exe) для формирования классов из RDL-схемы и включения их в проект.</span><span class="sxs-lookup"><span data-stu-id="edb69-132">In the next lesson, you will use the XML Schema Definition Tool (Xsd.exe) to generate classes from the RDL schema and include them in your project.</span></span> <span data-ttu-id="edb69-133">См. [Lesson 2: Generate Classes from the RDL Schema using the xsd Tool](../../2014/tutorials/lesson-2-generate-classes-from-the-rdl-schema-using-the-xsd-tool.md).</span><span class="sxs-lookup"><span data-stu-id="edb69-133">See [Lesson 2: Generate Classes from the RDL Schema using the xsd Tool](../../2014/tutorials/lesson-2-generate-classes-from-the-rdl-schema-using-the-xsd-tool.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edb69-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="edb69-134">See Also</span></span>  
 <span data-ttu-id="edb69-135">[Обновление отчетов с использованием классов, созданных из учебника по схеме языка определения отчетов &#40;SSRS&#41;](../../2014/tutorials/updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="edb69-135">[Updating Reports Using Classes Generated from the RDL Schema &#40;SSRS Tutorial&#41;](../../2014/tutorials/updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial.md) </span></span>  
 [<span data-ttu-id="edb69-136">Язык определения отчетов (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="edb69-136">Report Definition Language &#40;SSRS&#41;</span></span>](../reporting-services/reports/report-definition-language-ssrs.md)  
  
  
