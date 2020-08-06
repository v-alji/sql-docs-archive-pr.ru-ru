---
title: Занятие 2. Создание классов из RDL-схемы с помощью средства XSD | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a81c87f1-7977-4b30-b6ac-b38b3e2b6398
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: 2c5db118ad8f94afc72cea44b9a2489f2b4fd7f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734702"
---
# <a name="lesson-2-generate-classes-from-the-rdl-schema-using-the-xsd-tool"></a><span data-ttu-id="85329-102">Урок 2. Формирование классов из схемы языка определения отчетов с помощью инструмента xsd</span><span class="sxs-lookup"><span data-stu-id="85329-102">Lesson 2: Generate Classes from the RDL Schema using the xsd Tool</span></span>
  <span data-ttu-id="85329-103">После создания проекта в среде [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] следующим шагом является получение локальной копии схемы определения отчета и запуск средства определения XML-схемы (Xsd.exe).</span><span class="sxs-lookup"><span data-stu-id="85329-103">After you have created your [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] project, the next step is to retrieve a local copy of the report definition schema and run the XML Schema Definition Tool (Xsd.exe).</span></span>  
  
### <a name="to-generate-the-rdl-classes"></a><span data-ttu-id="85329-104">Формирование RDL-классов</span><span class="sxs-lookup"><span data-stu-id="85329-104">To generate the RDL classes</span></span>  
  
1.  <span data-ttu-id="85329-105">Откройте экземпляр [!INCLUDE[msCoName](../includes/msconame-md.md)] Internet Explorer (или аналогичный веб-браузер) и перейдите по следующему URL-адресу:</span><span class="sxs-lookup"><span data-stu-id="85329-105">Open an instance of [!INCLUDE[msCoName](../includes/msconame-md.md)] Internet Explorer (or equivalent Web browser) and navigate to the following URL:</span></span>  
  
    ```  
    https://schemas.microsoft.com/sqlserver/reporting/2010/01/reportdefinition/ReportDefinition.xsd  
    ```  
  
2.  <span data-ttu-id="85329-106">После открытия схемы языка определения отчетов в браузере перейдите в меню **файл** и выберите **Сохранить как**.</span><span class="sxs-lookup"><span data-stu-id="85329-106">Once the RDL schema has been opened in the browser, browse to the **File** menu, and select **Save As**.</span></span>  
  
3.  <span data-ttu-id="85329-107">Перейдите в папку, в которой был создан проект [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], и сохраните файл схемы под именем ReportDefinition.xsd.</span><span class="sxs-lookup"><span data-stu-id="85329-107">Browse to the location where you created your [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] project and save the schema with the file name ReportDefinition.xsd.</span></span>  
  
4.  <span data-ttu-id="85329-108">После сохранения файла откройте экземпляр [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] командной строки.</span><span class="sxs-lookup"><span data-stu-id="85329-108">After the file has been saved, open an instance of the [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] command prompt.</span></span> <span data-ttu-id="85329-109">Чтобы открыть экземпляр командной строки, в меню Пуск последовательно выберите пункты **все программы**, **Microsoft Visual Studio 2010**, **инструменты Visual Studio** и щелкните **Командная строка Visual Studio (2010)**.</span><span class="sxs-lookup"><span data-stu-id="85329-109">To open an instance of the command prompt, click the Start menu, point to **All Programs**, point to **Microsoft Visual Studio 2010**, point to **Visual Studio Tools** and click **Visual Studio Command Prompt (2010)**.</span></span>  
  
5.  <span data-ttu-id="85329-110">Перейдите в папку, в которой сохранен файл ReportDefinition.xsd:</span><span class="sxs-lookup"><span data-stu-id="85329-110">Change the current path to the location where you saved the ReportDefinition.xsd file:</span></span>  
  
     `CD\<ReportDefinition.xsd Path>`  
  
6.  <span data-ttu-id="85329-111">Создайте файл ReportDefinition.cs, содержащий классы для RDL-схемы, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="85329-111">Generate the ReportDefinition.cs file that contains the classes for the RDL schema with the following command:</span></span>  
  
     `xsd /c /n:SampleRDLSchema ReportDefinition.xsd`  
  
     <span data-ttu-id="85329-112">Для создания файла ReportDefinition.vb используйте команду:</span><span class="sxs-lookup"><span data-stu-id="85329-112">To generate a ReportDefinition.vb file use this command:</span></span>  
  
     `xsd /c /l:VB /n:SampleRDLSchema ReportDefinition.xsd`  
  
7.  <span data-ttu-id="85329-113">Добавьте файл ReportDefinition.xsd в проект.</span><span class="sxs-lookup"><span data-stu-id="85329-113">Add ReportDefinition.xsd your project.</span></span> <span data-ttu-id="85329-114">В меню **проект** выберите команду **Добавить существующий элемент**.</span><span class="sxs-lookup"><span data-stu-id="85329-114">From the **Project** menu, click **Add Existing Item**.</span></span> <span data-ttu-id="85329-115">Перейдите к расположению файла ReportDefinition. xsd, выберите ReportDefinition. xsd и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="85329-115">Browse to the location of the ReportDefinition.xsd file, select ReportDefinition.xsd, and click **Add**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="85329-116">После добавления файла ReportDefinition. xsd в проект вы увидите в **Обозреватель решений** что файл ReportDefinition.cs (VB) отсутствует.</span><span class="sxs-lookup"><span data-stu-id="85329-116">After you have added the ReportDefinition.xsd file to the project you will notice in **Solution Explorer** that the ReportDefinition.cs (.vb) file is not there.</span></span> <span data-ttu-id="85329-117">Чтобы отобразить файл, нажмите кнопку разворачивания или сворачивания рядом с файлом ReportDefinition.xsd.</span><span class="sxs-lookup"><span data-stu-id="85329-117">To display the file, click the expand/collapse button next to the ReportDefinition.xsd file.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="85329-118">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="85329-118">Next Lesson</span></span>  
 <span data-ttu-id="85329-119">На следующем занятии будет написан код для загрузки определения отчета с сервера отчетов с помощью классов, сформированных из RDL-схемы. </span><span class="sxs-lookup"><span data-stu-id="85329-119">In the next lesson, you will write code to load a report definition from a report server using the classes you generated from the RDL schema.</span></span> <span data-ttu-id="85329-120">См. [занятие 3. Загрузка определения отчета с сервера отчетов](../../2014/tutorials/lesson-3-load-a-report-definition-from-the-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="85329-120">See [Lesson 3: Load a Report Definition from the Report Server](../../2014/tutorials/lesson-3-load-a-report-definition-from-the-report-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85329-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="85329-121">See Also</span></span>  
 <span data-ttu-id="85329-122">[Обновление отчетов с использованием классов, созданных из учебника по схеме языка определения отчетов &#40;SSRS&#41;](../../2014/tutorials/updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="85329-122">[Updating Reports Using Classes Generated from the RDL Schema &#40;SSRS Tutorial&#41;](../../2014/tutorials/updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial.md) </span></span>  
 [<span data-ttu-id="85329-123">Язык определения отчетов (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="85329-123">Report Definition Language &#40;SSRS&#41;</span></span>](../reporting-services/reports/report-definition-language-ssrs.md)  
  
  
