---
title: Шаг 5. Тестирование обновленных пакетов | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 683e52e5-1c7e-49ab-9ffe-6a450a1c5776
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a075af2e030c8257d01abf5eba7d330b1cc8efe7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664346"
---
# <a name="step-5-testing-the-updated-packages"></a><span data-ttu-id="618a0-102">Шаг 5. Тестирование обновленных пакетов</span><span class="sxs-lookup"><span data-stu-id="618a0-102">Step 5: Testing the Updated Packages</span></span>
  <span data-ttu-id="618a0-103">Перед тем как перейти к следующему занятию, в котором вы создадите пакет развертывания, чтобы установить учебные пакеты на целевой компьютер, нужно проверить пакеты.</span><span class="sxs-lookup"><span data-stu-id="618a0-103">Before you go on to the next lesson, in which you will create the deployment bundle to use to install the tutorial packages on the destination computer, you should test the packages.</span></span> <span data-ttu-id="618a0-104">В этой задаче вы выполните пакеты DataTransfer.dtsx и LoadXMLData, которые добавлены в проект учебного развертывания и для которых было выполнено расширение конфигураций.</span><span class="sxs-lookup"><span data-stu-id="618a0-104">In this task, you will run the packages, DataTransfer.dtsx and LoadXMLData, that you added to the Deployment Tutorial project and then extended with configurations.</span></span>  
  
 <span data-ttu-id="618a0-105">По мере выполнения пакетов каждый исполняемый объект становится зеленым.</span><span class="sxs-lookup"><span data-stu-id="618a0-105">When the packages run, each executable in the package becomes a green color as it completes successfully.</span></span> <span data-ttu-id="618a0-106">Когда все исполняемые объекты станут зелеными, это будет значить, что пакет выполнен полностью.</span><span class="sxs-lookup"><span data-stu-id="618a0-106">When all executables are green, the package has completed successfully.</span></span> <span data-ttu-id="618a0-107">Просмотреть ход выполнения пакета на вкладке **Выполнение** .</span><span class="sxs-lookup"><span data-stu-id="618a0-107">You can also view the package execution progress on the **Progress** tab.</span></span>  
  
 <span data-ttu-id="618a0-108">Если выполнение пакетов завершилось неудачно, нужно исправить их, перед тем как перейти к следующему занятию.</span><span class="sxs-lookup"><span data-stu-id="618a0-108">If the packages do not run successfully, you must fix them before you go on to the next lesson.</span></span>  
  
### <a name="to-run-the-datatransfer-package"></a><span data-ttu-id="618a0-109">Выполнение пакета DataTransfer</span><span class="sxs-lookup"><span data-stu-id="618a0-109">To run the DataTransfer package</span></span>  
  
1.  <span data-ttu-id="618a0-110">В обозревателе решений выберите DataTransfer.dtsx.</span><span class="sxs-lookup"><span data-stu-id="618a0-110">In Solution Explorer, click DataTransfer.dtsx.</span></span>  
  
2.  <span data-ttu-id="618a0-111">В меню **Отладка** выберите пункт **Запустить отладку**.</span><span class="sxs-lookup"><span data-stu-id="618a0-111">On **Debug** menu, click **Start Debugging**.</span></span>  
  
3.  <span data-ttu-id="618a0-112">После окончания работы пакета выберите в меню **Отладка** пункт **Остановить отладку**.</span><span class="sxs-lookup"><span data-stu-id="618a0-112">After the package has completed running, on the **Debug** menu, click **Stop Debugging**.</span></span>  
  
### <a name="to-run-the-loadxmldata-package"></a><span data-ttu-id="618a0-113">Выполнение пакета LoadXMLData</span><span class="sxs-lookup"><span data-stu-id="618a0-113">To run the LoadXMLData package</span></span>  
  
1.  <span data-ttu-id="618a0-114">В обозревателе решений выберите LoadXMLData.dtsx.</span><span class="sxs-lookup"><span data-stu-id="618a0-114">In Solution Explorer, click LoadXMLData.dtsx.</span></span>  
  
2.  <span data-ttu-id="618a0-115">В меню **Отладка** выберите пункт **Запустить отладку**.</span><span class="sxs-lookup"><span data-stu-id="618a0-115">On **Debug** menu, click **Start Debugging**.</span></span>  
  
3.  <span data-ttu-id="618a0-116">После окончания работы пакета выберите в меню **Отладка** пункт **Остановить отладку**.</span><span class="sxs-lookup"><span data-stu-id="618a0-116">After the package has completed running, on the **Debug** menu, click **Stop Debugging**.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="618a0-117">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="618a0-117">Next Lesson</span></span>  
 [<span data-ttu-id="618a0-118">Занятие 2. Создание пакета развертывания</span><span class="sxs-lookup"><span data-stu-id="618a0-118">Lesson 2: Creating the Deployment Bundle</span></span>](../integration-services/lesson-2-create-the-deployment-bundle-in-ssis.md)  
  
<span data-ttu-id="618a0-119">![Значок Integration Services (маленький)](media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="618a0-119">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="618a0-120">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="618a0-120">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="618a0-121">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="618a0-121">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="618a0-122">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="618a0-122">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
