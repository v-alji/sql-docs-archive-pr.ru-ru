---
title: Занятие 1. Подготовка к созданию пакета развертывания | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: b6fe283c-9856-4ba1-a497-e3912424fd18
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0deda2a81ddd86d4e40c1c546232b8056264508a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664337"
---
# <a name="lesson-1-preparing-to-create-the-deployment-bundle"></a><span data-ttu-id="0c46a-102">Урок 1. Подготовка к созданию пакета развертывания</span><span class="sxs-lookup"><span data-stu-id="0c46a-102">Lesson 1: Preparing to Create the Deployment Bundle</span></span>
  <span data-ttu-id="0c46a-103">На этом занятии требуется создать рабочие папки и переменные среды, поддерживающие данный учебник, создать проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , добавить в него несколько пакетов и необходимых файлов поддержки, а также выполнить настройку пакетов.</span><span class="sxs-lookup"><span data-stu-id="0c46a-103">In this lesson, you will create the working folders and environment variables that support the tutorial, create an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project, add several packages and their supporting files to the project, and implement configurations in packages.</span></span>  
  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="0c46a-104">развертывают пакеты на основе проектов; поэтому на первом этапе создания комплекта развертывания необходимо собрать все пакеты и зависимые от них модули в один проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0c46a-104">deploys packages on a project basis; therefore, as the first step in creating the deployment bundle, you must collect all the packages and package dependencies into one [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span> <span data-ttu-id="0c46a-105">Часто оказывается полезным включать в развернутые пакеты другие сведения: например, в проект можно добавить файл сведений, содержащий общую справку по данной группе пакетов.</span><span class="sxs-lookup"><span data-stu-id="0c46a-105">Frequently it is useful to include other information with the deployed packages: for example you will also add to the project a Readme file that provides basic documentation for this group of packages.</span></span>  
  
 <span data-ttu-id="0c46a-106">После добавления пакетов и файлов необходимо добавить настройки в те пакеты, которые еще не были настроены.</span><span class="sxs-lookup"><span data-stu-id="0c46a-106">After you have added the packages and files, you will add configurations to packages that do not already use configurations.</span></span> <span data-ttu-id="0c46a-107">Благодаря настройкам свойства и объекты пакетов получают обновления во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="0c46a-107">The configurations update properties of packages and package objects at run time.</span></span> <span data-ttu-id="0c46a-108">На одном из следующих занятий предстоит изменить значения этих настроек во время развертывания пакета в целях поддержки пакетов в целевой среде развертывания.</span><span class="sxs-lookup"><span data-stu-id="0c46a-108">In a later lesson, you will modify the values of these configurations during package deployment to support the packages in the deployed-to environment.</span></span>  
  
 <span data-ttu-id="0c46a-109">После добавления настроек пакеты следует открыть в конструкторе служб [!INCLUDE[ssIS](../includes/ssis-md.md)] — графическом приложении служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] для создания пакетов ETL — и изучить свойства, элементы и настройки пакетов, чтобы лучше понять проблемы, с которыми сталкивается процесс развертывания.</span><span class="sxs-lookup"><span data-stu-id="0c46a-109">After you have added the configurations, you should open the packages in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] graphical tool for building ETL packages, and examine the properties of packages and package elements as well as the package configurations to better understand the issues that the deployment needs to address.</span></span> <span data-ttu-id="0c46a-110">Если, например, один из пакетов извлекает данные из текстовых файлов, то для успешного выполнения развернутых пакетов необходимо обновить информацию о расположении файлов данных.</span><span class="sxs-lookup"><span data-stu-id="0c46a-110">For example, one of the packages extracts data from text files, so the location of the data files must be updated before the deployed packages will run successfully.</span></span>  
  
 <span data-ttu-id="0c46a-111">**Предполагаемое время выполнения данного занятия:** 1 час</span><span class="sxs-lookup"><span data-stu-id="0c46a-111">**Estimated time to complete this lesson:** 1 hour</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="0c46a-112">Задачи занятия</span><span class="sxs-lookup"><span data-stu-id="0c46a-112">Lesson Tasks</span></span>  
 <span data-ttu-id="0c46a-113">Это занятие содержит следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="0c46a-113">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="0c46a-114">Шаг 1. Создание рабочих папок и переменных среды</span><span class="sxs-lookup"><span data-stu-id="0c46a-114">Step 1: Creating Working Folders and Environment Variables</span></span>](../integration-services/lesson-1-1-creating-working-folders-and-environment-variables.md)  
  
-   [<span data-ttu-id="0c46a-115">Шаг 2. Создание проекта развертывания</span><span class="sxs-lookup"><span data-stu-id="0c46a-115">Step 2: Creating the Deployment Project</span></span>](../integration-services/lesson-1-2-creating-the-deployment-project.md)  
  
-   [<span data-ttu-id="0c46a-116">Шаг 3. Добавление пакетов и других файлов</span><span class="sxs-lookup"><span data-stu-id="0c46a-116">Step 3: Adding Packages and Other Files</span></span>](../integration-services/lesson-1-3-adding-packages-and-other-files.md)  
  
-   [<span data-ttu-id="0c46a-117">Шаг 4. Добавление конфигурации пакета</span><span class="sxs-lookup"><span data-stu-id="0c46a-117">Step 4: Adding Package Configurations</span></span>](../integration-services/lesson-1-4-adding-package-configurations.md)  
  
-   [<span data-ttu-id="0c46a-118">Шаг 5. Тестирование обновленных пакетов</span><span class="sxs-lookup"><span data-stu-id="0c46a-118">Step 5: Testing the Updated Packages</span></span>](../integration-services/lesson-1-5-testing-the-updated-packages.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="0c46a-119">Начало занятия</span><span class="sxs-lookup"><span data-stu-id="0c46a-119">Start the Lesson</span></span>  
 [<span data-ttu-id="0c46a-120">Шаг 1. Создание рабочих папок и переменных среды</span><span class="sxs-lookup"><span data-stu-id="0c46a-120">Step 1: Creating Working Folders and Environment Variables</span></span>](../integration-services/lesson-1-1-creating-working-folders-and-environment-variables.md)  
  
<span data-ttu-id="0c46a-121">![Значок Integration Services (маленький)](media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="0c46a-121">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="0c46a-122">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="0c46a-122">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="0c46a-123">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="0c46a-123">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="0c46a-124">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="0c46a-124">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
