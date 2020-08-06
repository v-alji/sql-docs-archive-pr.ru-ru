---
title: Занятие 3. Установка пакетов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 87bc4d82-39d8-424f-886f-98cf1e4bb07a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9f8b58cee7bd8e16cd0ca2e726dc8e5eff2cfec5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658892"
---
# <a name="lesson-3-installing-packages"></a><span data-ttu-id="21798-102">Урок 3. Установка пакетов</span><span class="sxs-lookup"><span data-stu-id="21798-102">Lesson 3: Installing Packages</span></span>
  <span data-ttu-id="21798-103">На [занятии 2 "Создание пакета развертывания](../integration-services/lesson-2-create-the-deployment-bundle-in-ssis.md)" вы создали программу развертывания и создали пакет развертывания, содержащий элементы, которые необходимо установить на другом компьютере.</span><span class="sxs-lookup"><span data-stu-id="21798-103">In [Lesson 2: Creating the Deployment Bundle](../integration-services/lesson-2-create-the-deployment-bundle-in-ssis.md), you built a deployment utility and created the deployment bundle that contains the items that you must install packages on another computer.</span></span> <span data-ttu-id="21798-104">Вы также проверили список файлов в пакете развертывания и изучили содержимое файла манифеста, который был создан при сборке программы развертывания.</span><span class="sxs-lookup"><span data-stu-id="21798-104">You also verified the file list in the deployment bundle and examined the contents of the manifest file that was created when you built the deployment utility.</span></span>  
  
 <span data-ttu-id="21798-105">На этом занятии вы скопируете пакет развертывания на другой компьютер и запустите мастер установки пакета, чтобы установить пакеты, зависимости пакетов и вспомогательные файлы.</span><span class="sxs-lookup"><span data-stu-id="21798-105">In this lesson, you will copy the deployment bundle to the destination computer and then run the Package Installation Wizard to install the packages, package dependencies, and ancillary files on that computer.</span></span> <span data-ttu-id="21798-106">Пакеты будут установлены в **msdb** [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] базе данных msdb, а остальные элементы будут установлены в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="21798-106">The packages will be installed in the **msdb**[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database and the other items will be installed in the file system.</span></span> <span data-ttu-id="21798-107">После установки пакета вы проверите развертывание, выполнив пакеты из среды [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] при помощи программы выполнения пакетов.</span><span class="sxs-lookup"><span data-stu-id="21798-107">After you complete the package installation, you will test the deployment by running the packages from [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] using the Execute Package Utility.</span></span>  
  
 <span data-ttu-id="21798-108">**Предполагаемое время выполнения этого занятия:** 30 минут</span><span class="sxs-lookup"><span data-stu-id="21798-108">**Estimated time to complete this lesson:** 30 minutes</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="21798-109">Задачи занятия</span><span class="sxs-lookup"><span data-stu-id="21798-109">Lesson Tasks</span></span>  
 <span data-ttu-id="21798-110">Это занятие содержит следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="21798-110">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="21798-111">Шаг 1. Копирование пакета развертывания</span><span class="sxs-lookup"><span data-stu-id="21798-111">Step 1: Copying the Deployment Bundle</span></span>](../integration-services/lesson-3-1-copying-the-deployment-bundle.md)  
  
-   [<span data-ttu-id="21798-112">Шаг 2. Запуск мастера установки пакета</span><span class="sxs-lookup"><span data-stu-id="21798-112">Step 2: Running the Package Installation Wizard</span></span>](../integration-services/lesson-3-2-running-the-package-installation-wizard.md)  
  
-   [<span data-ttu-id="21798-113">Шаг 3. Тестирование развернутых пакетов</span><span class="sxs-lookup"><span data-stu-id="21798-113">Step 3: Testing the Deployed Packages</span></span>](../integration-services/lesson-3-3-testing-the-deployed-packages.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="21798-114">Начало занятия</span><span class="sxs-lookup"><span data-stu-id="21798-114">Start the Lesson</span></span>  
 [<span data-ttu-id="21798-115">Шаг 1. Копирование пакета развертывания</span><span class="sxs-lookup"><span data-stu-id="21798-115">Step 1: Copying the Deployment Bundle</span></span>](../integration-services/lesson-3-1-copying-the-deployment-bundle.md)  
  
<span data-ttu-id="21798-116">![Значок Integration Services (маленький)](media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="21798-116">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="21798-117">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="21798-117">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="21798-118">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="21798-118">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="21798-119">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="21798-119">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
