---
title: Обновление отчетов с использованием классов, созданных из RDL-схемы (учебник по службам SSRS) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- RDL [Reporting Services], generating
- RDL [Reporting Services], tutorials
- RDL [Reporting Services], serializing
ms.assetid: 8f81d48f-7ab9-4ef8-bce0-7d16d9a47fbd
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: f3972b8e1af6d50ccc6f5188c8f671fe333ebce8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656077"
---
# <a name="updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial"></a><span data-ttu-id="e5b91-102">Обновление отчетов с помощью классов, созданных из схемы языка определения отчетов (учебник по службам SSRS)</span><span class="sxs-lookup"><span data-stu-id="e5b91-102">Updating Reports Using Classes Generated from the RDL Schema (SSRS Tutorial)</span></span>
  <span data-ttu-id="e5b91-103">В этом учебнике показано, как использовать средство определения схемы XML (Xsd.exe) для создания классов, позволяющих сериализовать и десериализовать файлы определения отчета (RDL и RDLC) с помощью [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] <xref:System.Xml.Serialization.XmlSerializer> класса.</span><span class="sxs-lookup"><span data-stu-id="e5b91-103">This tutorial illustrates how to use the XML Schema Definition Tool (Xsd.exe) to generate classes that allow you to serialize and deserialize report definition files (.rdl and .rdlc) with the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="e5b91-104">Обзор учебника</span><span class="sxs-lookup"><span data-stu-id="e5b91-104">What You Will Learn</span></span>  
 <span data-ttu-id="e5b91-105">В ходе работы с этим учебником предстоит выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="e5b91-105">During the course of this tutorial, you will complete the following activities:</span></span>  
  
-   <span data-ttu-id="e5b91-106">Создайте приложение с помощью [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] шаблона проекта Консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="e5b91-106">Create an application using the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Console Application project template.</span></span>  
  
-   <span data-ttu-id="e5b91-107">Создание классов из схемы языка определения отчетов (RDL) с помощью средства **XSD** .</span><span class="sxs-lookup"><span data-stu-id="e5b91-107">Generate classes from the Report Definition Language (RDL) schema using the **xsd** tool.</span></span>  
  
-   <span data-ttu-id="e5b91-108">Подключиться к серверу отчетов и получить определение отчета.</span><span class="sxs-lookup"><span data-stu-id="e5b91-108">Connect to a report server and retrieve a report definition.</span></span>  
  
-   <span data-ttu-id="e5b91-109">Написать код для обновления файла определения отчета.</span><span class="sxs-lookup"><span data-stu-id="e5b91-109">Write code to update the report definition file.</span></span>  
  
-   <span data-ttu-id="e5b91-110">Сохранить обновленное определение отчета на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="e5b91-110">Save the updated report definition back to the report server.</span></span>  
  
-   <span data-ttu-id="e5b91-111">Выполнение приложения схемы языка определения отчетов (VB/C#).</span><span class="sxs-lookup"><span data-stu-id="e5b91-111">Run the RDL Schema Application (VB/C#).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e5b91-112">Образцы кода, приведенные в этом учебнике, могут не работать в отчетах, у которых нет описания.</span><span class="sxs-lookup"><span data-stu-id="e5b91-112">The code samples provided in this tutorial might fail for reports having no description.</span></span> <span data-ttu-id="e5b91-113">Происходит это потому, что у отчетов, для которых не задано описание, отсутствует свойство описания.</span><span class="sxs-lookup"><span data-stu-id="e5b91-113">The failure is because the description property does not exist for the reports with description not specified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5b91-114">Требования</span><span class="sxs-lookup"><span data-stu-id="e5b91-114">Requirements</span></span>  
 <span data-ttu-id="e5b91-115">Для работы с учебником необходимо наличие следующих компонентов.</span><span class="sxs-lookup"><span data-stu-id="e5b91-115">To complete the tutorial, you must have the following:</span></span>  
  
-   [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="e5b91-116">[!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5b91-116">[!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span>  
  
-   [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="e5b91-117">[!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5b91-117">[!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)].</span></span>  
  
-   <span data-ttu-id="e5b91-118">Необходимые разрешения для доступа к отчетам и публикации их в веб-службе сервера отчетов SQL Server на компьютере, на котором размещен сервер отчетов.</span><span class="sxs-lookup"><span data-stu-id="e5b91-118">Sufficient permissions to be able to access and publish reports to the Report Server Web service on the computer where your report server is located.</span></span>  
  
-   <span data-ttu-id="e5b91-119">Образец базы данных [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)], установленный на экземпляре [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5b91-119">The [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] sample database installed to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="e5b91-120">Отчет, установленный на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="e5b91-120">A report installed on your report server.</span></span> <span data-ttu-id="e5b91-121">Этот учебник основывается на образце отчета Company Sales 2012.</span><span class="sxs-lookup"><span data-stu-id="e5b91-121">This tutorial uses the sample report, Company Sales 2012.</span></span> <span data-ttu-id="e5b91-122">Дополнительные сведения об образцах отчетов см. в разделе [SQL Server Reporting Services примеров продуктов](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="e5b91-122">For more information about sample reports, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e5b91-123">Образцы не устанавливаются автоматически в процессе установки, но их можно установить в любое время.</span><span class="sxs-lookup"><span data-stu-id="e5b91-123">The samples are not installed automatically during setup, but you can install them at any time.</span></span> <span data-ttu-id="e5b91-124">Дополнительные сведения о примерах см. в разделе [SQL Server Product Samples](https://go.microsoft.com/fwlink/?LinkId=182887).</span><span class="sxs-lookup"><span data-stu-id="e5b91-124">For information about samples, see [SQL Server Product Samples](https://go.microsoft.com/fwlink/?LinkId=182887).</span></span>  
  
 <span data-ttu-id="e5b91-125">**Предполагаемое время выполнения учебника:** 30 минут</span><span class="sxs-lookup"><span data-stu-id="e5b91-125">**Estimated time to complete the tutorial:** 30 minutes</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="e5b91-126">Задания</span><span class="sxs-lookup"><span data-stu-id="e5b91-126">Tasks</span></span>  
 [<span data-ttu-id="e5b91-127">Урок 1. Создание проекта схемы языка определения отчетов в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e5b91-127">Lesson 1: Create the RDL Schema Visual Studio Project</span></span>](../../2014/tutorials/lesson-1-create-the-rdl-schema-visual-studio-project.md)  
  
 [<span data-ttu-id="e5b91-128">Урок 2. Формирование классов из схемы языка определения отчетов с помощью инструмента xsd</span><span class="sxs-lookup"><span data-stu-id="e5b91-128">Lesson 2: Generate Classes from the RDL Schema using the xsd Tool</span></span>](../../2014/tutorials/lesson-2-generate-classes-from-the-rdl-schema-using-the-xsd-tool.md)  
  
 [<span data-ttu-id="e5b91-129">Урок 3. Загрузка определения отчета с сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="e5b91-129">Lesson 3: Load a Report Definition from the Report Server</span></span>](../../2014/tutorials/lesson-3-load-a-report-definition-from-the-report-server.md)  
  
 [<span data-ttu-id="e5b91-130">Занятие 4: Обновление определения отчета программным способом</span><span class="sxs-lookup"><span data-stu-id="e5b91-130">Lesson 4: Update the Report Definition Programmatically</span></span>](../../2014/tutorials/lesson-4-update-the-report-definition-programmatically.md)  
  
 [<span data-ttu-id="e5b91-131">Занятие 5.: Публикация определения отчета на сервере отчетов</span><span class="sxs-lookup"><span data-stu-id="e5b91-131">Lesson 5: Publish the Report Definition to the Report Server</span></span>](../../2014/tutorials/lesson-5-publish-the-report-definition-to-the-report-server.md)  
  
 [<span data-ttu-id="e5b91-132">Занятие 6. Запуск приложения схемы языка определения отчетов &#40;VB-C&#35;&#41;</span><span class="sxs-lookup"><span data-stu-id="e5b91-132">Lesson 6: Run the RDL Schema Application &#40;VB-C&#35;&#41;</span></span>](../../2014/tutorials/lesson-6-run-the-rdl-schema-application-vb-csharp.md)  
  
## <a name="see-also"></a><span data-ttu-id="e5b91-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="e5b91-133">See Also</span></span>  
 [<span data-ttu-id="e5b91-134">Язык определения отчетов (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="e5b91-134">Report Definition Language &#40;SSRS&#41;</span></span>](../reporting-services/reports/report-definition-language-ssrs.md)  
  
  
