---
title: Занятие 2. Создание пакета развертывания | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: ab17289d-c3d4-4a5e-b7f5-4fea8ae21707
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 927bcd393e4b54e92971c197d93dcc1e2804dcd8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666123"
---
# <a name="lesson-2-creating-the-deployment-bundle"></a><span data-ttu-id="077ac-102">Занятие 2. Cоздание пакета развертывания</span><span class="sxs-lookup"><span data-stu-id="077ac-102">Lesson 2: Creating the Deployment Bundle</span></span>
  <span data-ttu-id="077ac-103">На [занятии 1: подготовка к созданию пакета развертывания](../integration-services/lesson-1-preparing-to-create-the-deployment-bundle.md)был создан проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , названный "Учебник по развертыванию", к нему были добавлены пакеты и вспомогательные файлы, а также выполнена настройка пакетов.</span><span class="sxs-lookup"><span data-stu-id="077ac-103">In [Lesson 1: Preparing to Create the Deployment Bundle](../integration-services/lesson-1-preparing-to-create-the-deployment-bundle.md), you created the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project named Deployment Tutorial, added the packages and supporting files to the project, and implemented configurations in packages.</span></span>  
  
 <span data-ttu-id="077ac-104">На этом занятии создается пакет развертывания, представляющий собой папку, в которой содержатся все элементы, необходимые для установки пакетов на другом компьютере.</span><span class="sxs-lookup"><span data-stu-id="077ac-104">In this lesson, you will create the deployment bundle, which is a folder that contains the items that you need to install packages on another computer.</span></span> <span data-ttu-id="077ac-105">В пакет развертывания необходимо включить манифест развертывания, копии пакетов и копии файлов поддержки из проекта «Учебник по развертыванию».</span><span class="sxs-lookup"><span data-stu-id="077ac-105">The deployment bundle will include a deployment manifest, copies of the packages, and copies of the supporting files from the Deployment Tutorial project.</span></span> <span data-ttu-id="077ac-106">В манифесте развертывания перечисляются пакеты, различные файлы и настройки из пакета развертывания.</span><span class="sxs-lookup"><span data-stu-id="077ac-106">The deployment manifest lists the packages, miscellaneous files, and configurations in the deployment bundle.</span></span>  
  
 <span data-ttu-id="077ac-107">Помимо этого будет проверен список файлов в пакете развертывания и содержимое манифеста.</span><span class="sxs-lookup"><span data-stu-id="077ac-107">You will also verify the file list in the deployment bundle and examine the contents of the manifest.</span></span>  
  
 <span data-ttu-id="077ac-108">**Предполагаемое время выполнения данного занятия:** 30 минут</span><span class="sxs-lookup"><span data-stu-id="077ac-108">**Estimated time to complete this lesson:** 30 minutes</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="077ac-109">Задачи занятия</span><span class="sxs-lookup"><span data-stu-id="077ac-109">Lesson Tasks</span></span>  
 <span data-ttu-id="077ac-110">Это занятие содержит следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="077ac-110">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="077ac-111">Шаг 1. Построение программы развертывания</span><span class="sxs-lookup"><span data-stu-id="077ac-111">Step 1: Building the Deployment Utility</span></span>](../integration-services/lesson-2-1-building-the-deployment-utility.md)  
  
-   [<span data-ttu-id="077ac-112">Шаг 2. Проверка пакета развертывания</span><span class="sxs-lookup"><span data-stu-id="077ac-112">Step 2: Verifying the Deployment Bundle</span></span>](../integration-services/lesson-2-2-verifying-the-deployment-bundle.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="077ac-113">Начало занятия</span><span class="sxs-lookup"><span data-stu-id="077ac-113">Start the Lesson</span></span>  
 [<span data-ttu-id="077ac-114">Шаг 1. Построение программы развертывания</span><span class="sxs-lookup"><span data-stu-id="077ac-114">Step 1: Building the Deployment Utility</span></span>](../integration-services/lesson-2-1-building-the-deployment-utility.md)  
  
<span data-ttu-id="077ac-115">![Значок Integration Services (маленький)](media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="077ac-115">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="077ac-116">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="077ac-116">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="077ac-117">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="077ac-117">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="077ac-118">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="077ac-118">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
