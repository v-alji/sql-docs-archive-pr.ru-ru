---
title: Занятие 3. Добавление ведения журнала | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 64cd24cc-ba8e-4bd7-b10b-6b80d8b04af6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 58fcc29759f19ad215a76a1b9ed9bf313b4c869c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658893"
---
# <a name="lesson-3-adding-logging"></a><span data-ttu-id="baeed-102">Урок 3. Добавление журнала</span><span class="sxs-lookup"><span data-stu-id="baeed-102">Lesson 3: Adding Logging</span></span>
  <span data-ttu-id="baeed-103">В [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] возможно ведение журналов, что позволяет отслеживать и устранять неполадки при выполнении пакетов, обеспечивая трассировку задач и событий контейнеров.</span><span class="sxs-lookup"><span data-stu-id="baeed-103">[!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] includes logging features that let you troubleshoot and monitor package execution by providing a trace of task and container events.</span></span> <span data-ttu-id="baeed-104">Эти возможности очень гибки. Они могут активироваться как на уровне пакетов, так и на уровне отдельных задач или контейнеров в пакете.</span><span class="sxs-lookup"><span data-stu-id="baeed-104">The logging features are flexible, and can be enabled at the package level or on individual tasks and containers within the package.</span></span> <span data-ttu-id="baeed-105">Можно выбрать события, которые будут заноситься в журнал, а также создать несколько журналов для одного пакета.</span><span class="sxs-lookup"><span data-stu-id="baeed-105">You can select which events you want to log, and create multiple logs against a single package.</span></span>  
  
 <span data-ttu-id="baeed-106">Ведение журнала обеспечивается регистратором.</span><span class="sxs-lookup"><span data-stu-id="baeed-106">Logging is provided by a log provider.</span></span> <span data-ttu-id="baeed-107">Каждый регистратор может сохранять данные журналов в разных форматах и на разных типах носителей.</span><span class="sxs-lookup"><span data-stu-id="baeed-107">Each log provider can write logging information to different formats and destination types.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="baeed-108">предоставляют следующие регистраторы:</span><span class="sxs-lookup"><span data-stu-id="baeed-108">provides the following log providers:</span></span>  
  
-   <span data-ttu-id="baeed-109">текстовый файл</span><span class="sxs-lookup"><span data-stu-id="baeed-109">Text file</span></span>  
  
-   [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)]  
  
-   <span data-ttu-id="baeed-110">Журнал событий Windows</span><span class="sxs-lookup"><span data-stu-id="baeed-110">Windows Event log</span></span>  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]  
  
-   <span data-ttu-id="baeed-111">XML-файл</span><span class="sxs-lookup"><span data-stu-id="baeed-111">XML file</span></span>  
  
 <span data-ttu-id="baeed-112">На этом занятии будет создана копия пакета, созданного на [Lesson 2: Adding Looping](lesson-2-adding-looping-with-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="baeed-112">In this lesson, you will create a copy of the package that you created in [Lesson 2: Adding Looping](lesson-2-adding-looping-with-ssis.md).</span></span> <span data-ttu-id="baeed-113">При работе с новым пакетом будет добавлено и настроено ведение журнала, позволяющее отслеживать отдельные события при выполнении пакета.</span><span class="sxs-lookup"><span data-stu-id="baeed-113">Working with this new package, you will then add and configure logging to monitor specific events during package execution.</span></span> <span data-ttu-id="baeed-114">Если вы не выполняли ни одно из предыдущих занятий, можно воспользоваться копией пакета из занятия 2, которая включена в учебник.</span><span class="sxs-lookup"><span data-stu-id="baeed-114">If you have not completed any of the previous lessons, you can also copy the completed Lesson 2 package that is included with the tutorial.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="baeed-115">Для выполнения упражнений этого учебника потребуется образец базы данных **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="baeed-115">This tutorial requires the **AdventureWorksDW2012** sample database.</span></span> <span data-ttu-id="baeed-116">Дополнительные сведения об установке и развертывании **AdventureWorksDW2012**см. [в Reporting Services примеров продуктов на сайте GitHub](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span><span class="sxs-lookup"><span data-stu-id="baeed-116">For more information about how to install and deploy **AdventureWorksDW2012**, [Reporting Services Product Samples on GitHub](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="baeed-117">Задачи занятия</span><span class="sxs-lookup"><span data-stu-id="baeed-117">Lesson Tasks</span></span>  
 <span data-ttu-id="baeed-118">Это занятие содержит следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="baeed-118">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="baeed-119">Шаг 1. Копирование пакета занятия 2</span><span class="sxs-lookup"><span data-stu-id="baeed-119">Step 1: Copying the Lesson 2 Package</span></span>](lesson-3-1-copying-the-lesson-2-package.md)  
  
-   [<span data-ttu-id="baeed-120">Шаг 2. Добавление и настройка ведения журнала</span><span class="sxs-lookup"><span data-stu-id="baeed-120">Step 2: Adding and Configuring Logging</span></span>](lesson-3-2-adding-and-configuring-logging.md)  
  
-   [<span data-ttu-id="baeed-121">Шаг 3. Проверка учебного пакета, созданного на занятии 3</span><span class="sxs-lookup"><span data-stu-id="baeed-121">Step 3: Testing the Lesson 3 Tutorial Package</span></span>](../integration-services/lesson-3-3-testing-the-lesson-3-tutorial-package.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="baeed-122">Начало занятия</span><span class="sxs-lookup"><span data-stu-id="baeed-122">Start the Lesson</span></span>  
 [<span data-ttu-id="baeed-123">Шаг 1. Копирование пакета занятия 2</span><span class="sxs-lookup"><span data-stu-id="baeed-123">Step 1: Copying the Lesson 2 Package</span></span>](lesson-3-1-copying-the-lesson-2-package.md)  
  
  
