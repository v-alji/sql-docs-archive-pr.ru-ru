---
title: Создание простого табличного отчета (учебник по службам SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- walkthroughs [Reporting Services]
- tutorials [Reporting Services]
- reports [Reporting Services], creating
ms.assetid: 3b539b4b-26f2-4c0b-b506-80f175679a46
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 02e0f42869a3bfa88e0c6646fd447968c8ba3a10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654059"
---
# <a name="create-a-basic-table-report-ssrs-tutorial"></a><span data-ttu-id="5273e-102">Создание простого табличного отчета (учебник по службам SSRS)</span><span class="sxs-lookup"><span data-stu-id="5273e-102">Create a Basic Table Report (SSRS Tutorial)</span></span>
  <span data-ttu-id="5273e-103">Этот учебник поможет создать простой табличный отчет на основе базы данных [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] с помощью конструктора отчетов.</span><span class="sxs-lookup"><span data-stu-id="5273e-103">This tutorial is designed to help you create a basic table report based on the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database using Report Designer.</span></span> <span data-ttu-id="5273e-104">Для создания отчетов также можно использовать построитель отчетов и мастер отчетов.</span><span class="sxs-lookup"><span data-stu-id="5273e-104">You can also use Report Builder or the Report Wizard to create reports.</span></span> <span data-ttu-id="5273e-105">В этом учебнике требуется создать проект отчета, указать сведения о соединении, определить запрос, добавить область данных таблицы и выполнить предварительный просмотр отчета.</span><span class="sxs-lookup"><span data-stu-id="5273e-105">In this tutorial, you will create a report project, set up connection information, define a query, add a Table data region, group and total some fields, and preview the report.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5273e-106">Для работы с этим учебником необходимо переключить службы [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] в собственный режим.</span><span class="sxs-lookup"><span data-stu-id="5273e-106">To complete this tutorial, you must be running [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] in native mode.</span></span> <span data-ttu-id="5273e-107">Если службы [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] работают в режиме интеграции с SharePoint, то шаги, в которых используются URL-адреса сервера отчетов, неприменимы.</span><span class="sxs-lookup"><span data-stu-id="5273e-107">If you are running [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] in SharePoint integrated mode, the steps that use report server URLs do not work.</span></span> <span data-ttu-id="5273e-108">Дополнительные сведения о [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] режимах см. в разделе [Reporting Services сервер отчетов](reporting-services-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="5273e-108">For more information about [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] modes, see [Reporting Services Report Server](reporting-services-report-server.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5273e-109">Требования</span><span class="sxs-lookup"><span data-stu-id="5273e-109">Requirements</span></span>  
 <span data-ttu-id="5273e-110">Для работы с этим учебником в системе должны быть установлены следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="5273e-110">Your system must have the following installed to use this tutorial:</span></span>  
  
-   [!INCLUDE[msCoName](../includes/msconame-md.md)]<span data-ttu-id="5273e-111">[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]ядро СУБД.</span><span class="sxs-lookup"><span data-stu-id="5273e-111">[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] database engine.</span></span>  
  
-   <span data-ttu-id="5273e-112">База данных [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5273e-112">The [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database.</span></span>  <span data-ttu-id="5273e-113">Дополнительные сведения см. в статье [Adventure Works for SQL Server 2012 (Adventure Works for SQL Server 2012)](https://go.microsoft.com/fwlink/?LinkId=245471) ( https://go.microsoft.com/fwlink/?LinkId=245471). .</span><span class="sxs-lookup"><span data-stu-id="5273e-113">For more information, see [Adventure Works for SQL Server 2012 (Adventure Works for SQL Server 2012)](https://go.microsoft.com/fwlink/?LinkId=245471) (https://go.microsoft.com/fwlink/?LinkId=245471)..</span></span> <span data-ttu-id="5273e-114">Дополнительные сведения о поддержке [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] образцов баз данных и примеров кода для [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] см. в разделе [Общие сведения о базах данных и](https://go.microsoft.com/fwlink/?LinkId=110391) примерах на веб-сайте CodePlex.</span><span class="sxs-lookup"><span data-stu-id="5273e-114">For more information about support for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] sample databases and sample code for [!INCLUDE[ssExpress](../includes/ssexpress-md.md)], see [Databases and Samples Overview](https://go.microsoft.com/fwlink/?LinkId=110391) on the CodePlex Web site.</span></span>  
  
-   [!INCLUDE[ssRSCurrent](../includes/ssrscurrent-md.md)]<span data-ttu-id="5273e-115">.</span><span class="sxs-lookup"><span data-stu-id="5273e-115">.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="5273e-116">[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5273e-116">[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
    > [!NOTE]  
    >  [!INCLUDE[ssNote64Samp](../includes/ssnote64samp-md.md)]  
  
 <span data-ttu-id="5273e-117">Для получения данных из базы данных [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] необходимо иметь разрешения только на чтение.</span><span class="sxs-lookup"><span data-stu-id="5273e-117">You must also have read-only permissions to retrieve data from the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="5273e-118">Задания</span><span class="sxs-lookup"><span data-stu-id="5273e-118">Tasks</span></span>  
 [<span data-ttu-id="5273e-119">Занятие 1. Создание проекта сервера отчетов (службы Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="5273e-119">Lesson 1: Creating a Report Server Project &#40;Reporting Services&#41;</span></span>](lesson-1-creating-a-report-server-project-reporting-services.md)  
  
 [<span data-ttu-id="5273e-120">Занятие 2. Задание информации о соединении (службы Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="5273e-120">Lesson 2: Specifying Connection Information &#40;Reporting Services&#41;</span></span>](lesson-2-specifying-connection-information-reporting-services.md)  
  
 [<span data-ttu-id="5273e-121">Занятие 3. Определение набора данных для табличного отчета (службы Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="5273e-121">Lesson 3: Defining a Dataset for the Table Report &#40;Reporting Services&#41;</span></span>](lesson-3-defining-a-dataset-for-the-table-report-reporting-services.md)  
  
 [<span data-ttu-id="5273e-122">Занятие 4. Добавление таблицы в отчет (службы Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="5273e-122">Lesson 4: Adding a Table to the Report &#40;Reporting Services&#41;</span></span>](lesson-4-adding-a-table-to-the-report-reporting-services.md)  
  
 [<span data-ttu-id="5273e-123">Занятие 5. Форматирование отчета (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="5273e-123">Lesson 5: Formatting a Report &#40;Reporting Services&#41;</span></span>](lesson-5-formatting-a-report-reporting-services.md)  
  
 [<span data-ttu-id="5273e-124">Занятие 6. Добавление группирования и итогов (службы Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="5273e-124">Lesson 6: Adding Grouping and Totals &#40;Reporting Services&#41;</span></span>](lesson-6-adding-grouping-and-totals-reporting-services.md)  
  
> [!NOTE]  
>  <span data-ttu-id="5273e-125">При просмотре учебников рекомендуется добавить кнопки **Далее** и **назад** на панель инструментов средства просмотра документов.</span><span class="sxs-lookup"><span data-stu-id="5273e-125">When reviewing tutorials, we recommend that you add **Next** and **Previous** buttons to the document viewer toolbar.</span></span> <span data-ttu-id="5273e-126">Дополнительные сведения см. в разделе</span><span class="sxs-lookup"><span data-stu-id="5273e-126">For more information, see.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5273e-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="5273e-127">See Also</span></span>  
 [<span data-ttu-id="5273e-128">Учебники по службам Reporting Services (SSRS)</span><span class="sxs-lookup"><span data-stu-id="5273e-128">Reporting Services Tutorials &#40;SSRS&#41;</span></span>](reporting-services-tutorials-ssrs.md)  
  
  
