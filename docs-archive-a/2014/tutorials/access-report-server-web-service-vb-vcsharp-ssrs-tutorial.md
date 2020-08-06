---
title: Доступ к веб-службе сервера отчетов с помощью Visual Basic или Visual C# (учебник по службам SSRS) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
dev_langs:
- VB
helpviewer_keywords:
- walkthroughs [Reporting Services]
- Reporting Services, Web service
- Web service [Reporting Services], tutorials
ms.assetid: cf688163-4ac0-475b-b6dd-6f2f05b553c6
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: 3dc2599b4fafe682d74089d637918e04db9ed219
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735685"
---
# <a name="accessing-the-report-server-web-service-using-visual-basic-or-visual-c-ssrs-tutorial"></a><span data-ttu-id="ce8e9-102">Доступ к веб-службе сервера отчетов на языке Visual Basic или Visual C# (учебник по службам SSAS)</span><span class="sxs-lookup"><span data-stu-id="ce8e9-102">Accessing the Report Server Web Service Using Visual Basic or Visual C# (SSRS Tutorial)</span></span>
  <span data-ttu-id="ce8e9-103">В следующем руководстве показано, как получить доступ к веб-службе сервера отчетов из приложения, созданного с помощью [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] или [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[csprcs](../includes/csprcs-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ce8e9-103">The following tutorial shows you how to access the Report Server Web service from an application created with [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] or [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[csprcs](../includes/csprcs-md.md)].</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="ce8e9-104">Обзор учебника</span><span class="sxs-lookup"><span data-stu-id="ce8e9-104">What You Will Learn</span></span>  
 <span data-ttu-id="ce8e9-105">В ходе работы с этим учебником предстоит выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="ce8e9-105">During the course of this tutorial, you will complete the following:</span></span>  
  
-   <span data-ttu-id="ce8e9-106">Создайте клиентское приложение, используя [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] шаблон проекта Консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="ce8e9-106">Create a client application using the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] Console Application project template.</span></span>  
  
-   <span data-ttu-id="ce8e9-107">Добавить веб-ссылку на веб-службу сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="ce8e9-107">Add a Web reference for the Report Server Web service.</span></span>  
  
-   <span data-ttu-id="ce8e9-108">Написать код для доступа к этой веб-службе.</span><span class="sxs-lookup"><span data-stu-id="ce8e9-108">Write code to access the Web service.</span></span>  
  
-   <span data-ttu-id="ce8e9-109">Выполнить созданное приложение командной строки в режиме отладки.</span><span class="sxs-lookup"><span data-stu-id="ce8e9-109">Run the console application in debug mode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce8e9-110">Требования</span><span class="sxs-lookup"><span data-stu-id="ce8e9-110">Requirements</span></span>  
 <span data-ttu-id="ce8e9-111">Для работы с учебником необходимо наличие следующих компонентов.</span><span class="sxs-lookup"><span data-stu-id="ce8e9-111">To complete the tutorial, you must have the following:</span></span>  
  
-   [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="ce8e9-112">[!INCLUDE[ssSQL11](../includes/sssql11-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce8e9-112">[!INCLUDE[ssSQL11](../includes/sssql11-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span>  
  
-   [!INCLUDE[msCoName](../includes/msconame-md.md)]<span data-ttu-id="ce8e9-113">[!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)]или аналогичный [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] — совместимый инструмент разработки.</span><span class="sxs-lookup"><span data-stu-id="ce8e9-113">[!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] or a similar [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]-compatible development tool.</span></span>  
  
-   <span data-ttu-id="ce8e9-114">Необходимые разрешения для доступа к веб-службе сервера отчетов [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] на компьютере, на котором размещен сервер отчетов.</span><span class="sxs-lookup"><span data-stu-id="ce8e9-114">Sufficient permissions to be able to access the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Report Server Web service on the computer where your report server is located.</span></span>  
  
-   <span data-ttu-id="ce8e9-115">Отчет, установленный на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="ce8e9-115">A report installed on your report server.</span></span> <span data-ttu-id="ce8e9-116">Этот учебник основывается на образце отчета Company Sales.</span><span class="sxs-lookup"><span data-stu-id="ce8e9-116">This tutorial uses the sample report, Company Sales.</span></span> <span data-ttu-id="ce8e9-117">Дополнительные сведения об образцах отчетов см. в разделе [SQL Server Reporting Services примеров продуктов](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="ce8e9-117">For more information about sample reports, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ce8e9-118">Образцы не устанавливаются автоматически в процессе установки, но их можно установить в любое время.</span><span class="sxs-lookup"><span data-stu-id="ce8e9-118">The samples are not installed automatically during setup, but you can install them at any time.</span></span> <span data-ttu-id="ce8e9-119">Дополнительные сведения о примерах см. в разделе [SQL Server Product Samples](https://go.microsoft.com/fwlink/?LinkId=182887).</span><span class="sxs-lookup"><span data-stu-id="ce8e9-119">For information about samples, see [SQL Server Product Samples](https://go.microsoft.com/fwlink/?LinkId=182887).</span></span>  
  
 <span data-ttu-id="ce8e9-120">**Предполагаемое время выполнения учебника:** 60 минут</span><span class="sxs-lookup"><span data-stu-id="ce8e9-120">**Estimated time to complete the tutorial:** 60 minutes</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="ce8e9-121">Задания</span><span class="sxs-lookup"><span data-stu-id="ce8e9-121">Tasks</span></span>  
 [<span data-ttu-id="ce8e9-122">Урок 1. Создание проекта клиентской веб-службы</span><span class="sxs-lookup"><span data-stu-id="ce8e9-122">Lesson 1: Creating the Web Service Client Project</span></span>](../../2014/tutorials/lesson-1-creating-the-web-service-client-project.md)  
  
 [<span data-ttu-id="ce8e9-123">Урок 2. Добавление веб-ссылки</span><span class="sxs-lookup"><span data-stu-id="ce8e9-123">Lesson 2: Adding a Web Reference</span></span>](../../2014/tutorials/lesson-2-adding-a-web-reference.md)  
  
 [<span data-ttu-id="ce8e9-124">Урок 3. Доступ к веб-службе</span><span class="sxs-lookup"><span data-stu-id="ce8e9-124">Lesson 3: Accessing the Web Service</span></span>](../../2014/tutorials/lesson-3-accessing-the-web-service.md)  
  
 [<span data-ttu-id="ce8e9-125">Занятие 4. Запуск приложения &#40;VB — VC&#35;&#41;</span><span class="sxs-lookup"><span data-stu-id="ce8e9-125">Lesson 4: Running the Application &#40;VB-VC&#35;&#41;</span></span>](../../2014/tutorials/lesson-4-running-the-application-vb-vcsharp.md)  
  
  
