---
title: Шаг 1. Копирование пакета развертывания | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: b6ef1e56-d278-4a24-afd3-68d8e0595cbb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 326a85a4d04fc22382457b4e2e919f81096ce989
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668435"
---
# <a name="step-1-copying-the-deployment-bundle"></a><span data-ttu-id="828e6-102">Шаг 1. Копирование пакета развертывания</span><span class="sxs-lookup"><span data-stu-id="828e6-102">Step 1: Copying the Deployment Bundle</span></span>
  <span data-ttu-id="828e6-103">В этой задаче требуется скопировать пакет развертывания на целевой компьютер.</span><span class="sxs-lookup"><span data-stu-id="828e6-103">In this task, you will copy the deployment bundle to the destination computer.</span></span>  
  
 <span data-ttu-id="828e6-104">Самый простой способ скопировать пакет развертывания на целевой компьютер включает создание общей папки на целевом компьютере, сопоставление соответствующего сетевого диска и копирование комплекта развертывания в эту общую папку.</span><span class="sxs-lookup"><span data-stu-id="828e6-104">The easiest way to copy the deployment bundle to the destination computer is to first create a public share on the destination computer, map a drive to the public share, and then copy the deployment bundle to the share.</span></span> <span data-ttu-id="828e6-105">Если сведения о создании и настройке общих папок или сопоставлении сетевых дисков отсутствуют, обратитесь к документации по операционной системе Windows.</span><span class="sxs-lookup"><span data-stu-id="828e6-105">If you do not know how to create and configure public folders or map drives, see the Windows documentation.</span></span>  
  
### <a name="to-copy-the-deployment-bundle"></a><span data-ttu-id="828e6-106">Копирование пакета развертывания</span><span class="sxs-lookup"><span data-stu-id="828e6-106">To copy the deployment bundle</span></span>  
  
1.  <span data-ttu-id="828e6-107">Найдите на своем компьютере комплект развертывания.</span><span class="sxs-lookup"><span data-stu-id="828e6-107">Locate the deployment bundle on your computer.</span></span>  
  
     <span data-ttu-id="828e6-108">Если используется размещение по умолчанию, комплект развертывания находится в учебнике по развертыванию в папке Bin\Deployment.</span><span class="sxs-lookup"><span data-stu-id="828e6-108">If you used the default location, the deployment bundle is the Bin\Deployment folder within the Deployment Tutorial folder.</span></span>  
  
2.  <span data-ttu-id="828e6-109">Щелкните правой кнопкой мыши папку "Развертывание", а затем выберите пункт меню **Копировать**.</span><span class="sxs-lookup"><span data-stu-id="828e6-109">Right-click the Deployment folder and click **Copy**.</span></span>  
  
3.  <span data-ttu-id="828e6-110">Найдите общую папку на целевом компьютере, куда будет производиться копирование, и щелкните **Вставить**.</span><span class="sxs-lookup"><span data-stu-id="828e6-110">Locate the public share to which you want to copy the folder on the target computer and click **Paste**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="828e6-111">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="828e6-111">Next Task in Lesson</span></span>  
 [<span data-ttu-id="828e6-112">Шаг 2. Запуск мастера установки пакета</span><span class="sxs-lookup"><span data-stu-id="828e6-112">Step 2: Running the Package Installation Wizard</span></span>](../integration-services/lesson-3-2-running-the-package-installation-wizard.md)  
  
<span data-ttu-id="828e6-113">![Значок Integration Services (маленький)](media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="828e6-113">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="828e6-114">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="828e6-114">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="828e6-115">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="828e6-115">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="828e6-116">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="828e6-116">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
