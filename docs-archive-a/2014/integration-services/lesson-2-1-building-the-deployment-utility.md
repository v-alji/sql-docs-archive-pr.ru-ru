---
title: Шаг 1. Построение программы развертывания | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 1ff4dcff-89b3-4b99-a725-5f7963e98abf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3d32dcbf4bfcf9758dfe58803b75094d1807aa90
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664331"
---
# <a name="step-1-building-the-deployment-utility"></a><span data-ttu-id="12fb4-102">Шаг 1. Построение программы развертывания</span><span class="sxs-lookup"><span data-stu-id="12fb4-102">Step 1: Building the Deployment Utility</span></span>
  <span data-ttu-id="12fb4-103">В этой задаче будет настроена и построена программа развертывания для проекта «Учебник по развертыванию».</span><span class="sxs-lookup"><span data-stu-id="12fb4-103">In this task, you will configure and build a deployment utility for the Deployment Tutorial project.</span></span>  
  
 <span data-ttu-id="12fb4-104">Прежде, чем можно будет создать программу развертывания, следует изменить свойства проекта «Учебник по развертыванию».</span><span class="sxs-lookup"><span data-stu-id="12fb4-104">Before you can build the deployment utility, you must modify the properties of the Deployment Tutorial project.</span></span> <span data-ttu-id="12fb4-105">Для настройки этих свойств будет использоваться диалоговое окно **Страницы свойств учебника по развертыванию** .</span><span class="sxs-lookup"><span data-stu-id="12fb4-105">You will use the **Deployment Tutorial Property Pages** dialog box to configure these properties.</span></span> <span data-ttu-id="12fb4-106">В нем нужно включить возможность обновления конфигураций во время развертывания и указать, что процесс построения создает программу развертывания.</span><span class="sxs-lookup"><span data-stu-id="12fb4-106">In this dialog box, you must enable the ability to update configurations during deployment and specify that the build process generates a deployment utility.</span></span> <span data-ttu-id="12fb4-107">После настройки свойств будет построен проект.</span><span class="sxs-lookup"><span data-stu-id="12fb4-107">After you set the properties, you will build the project.</span></span>  
  
 [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] <span data-ttu-id="12fb4-108">предоставляет ряд окон, которые можно использовать для отладки пакетов.</span><span class="sxs-lookup"><span data-stu-id="12fb4-108">provides a set of windows that you can use to debug packages.</span></span> <span data-ttu-id="12fb4-109">Можно просматривать сообщения об ошибках, предупреждения и информационные сообщения, отслеживать состояние пакетов во время выполнения и наблюдать ход и результаты процессов построения.</span><span class="sxs-lookup"><span data-stu-id="12fb4-109">You can view error, warning, and information messages, track about the status of packages at run time, or view the progress and results of build processes.</span></span> <span data-ttu-id="12fb4-110">В этом занятии окно «Вывод» будет использоваться для наблюдения за ходом и результатами построения программы развертывания.</span><span class="sxs-lookup"><span data-stu-id="12fb4-110">For this lesson, you will use the Output window to view the progress and results of building the deployment utility.</span></span>  
  
### <a name="to-set-the-deployment-utility-properties"></a><span data-ttu-id="12fb4-111">Установка свойств программы развертывания</span><span class="sxs-lookup"><span data-stu-id="12fb4-111">To set the deployment utility properties</span></span>  
  
1.  <span data-ttu-id="12fb4-112">Если среда [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] еще не открыта, нажмите кнопку **Пуск**, наведите указатель на пункт **Все программы**, затем на пункт **Microsoft SQL Server**и выберите **Среда Business Intelligence Development Studio**.</span><span class="sxs-lookup"><span data-stu-id="12fb4-112">If [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] is not already open, click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, and then click **Business Intelligence Development Studio**.</span></span>  
  
2.  <span data-ttu-id="12fb4-113">В меню **Файл** выберите пункт **Открыть**, щелкните **Проект или решение**, разверните папку **Deployment Tutorial** и нажмите кнопку **Открыть**, а затем дважды щелкните файл **Deployment Tutorial.sln**.</span><span class="sxs-lookup"><span data-stu-id="12fb4-113">On the **File** menu, click **Open**, click **Project/Solution**, click the **Deployment Tutorial** folder and click **Open**, and then double-click **Deployment Tutorial.sln**.</span></span>  
  
3.  <span data-ttu-id="12fb4-114">В обозревателе решений щелкните правой кнопкой мыши "Учебник по развертыванию" и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="12fb4-114">In Solution Explorer, right-click Deployment Tutorial and click **Properties**.</span></span>  
  
4.  <span data-ttu-id="12fb4-115">В диалоговом окне **Страницы свойств учебника по развертыванию** разверните узел "Свойства конфигурации" и выберите "Программа развертывания".</span><span class="sxs-lookup"><span data-stu-id="12fb4-115">In the **Deployment Tutorial Property Pages** dialog box, expand Configuration Properties, and click Deployment Utility.</span></span>  
  
5.  <span data-ttu-id="12fb4-116">В правой области диалогового окна **страницы свойств учебника по развертыванию** убедитесь, что для параметра задано значение `AllowConfigurationChanges` `true` , задано `CreateDeploymentUtility` значение, `true` а при необходимости — обновление значения по умолчанию `DeploymentOutputPath` .</span><span class="sxs-lookup"><span data-stu-id="12fb4-116">In the right pane of the **Deployment Tutorial Property Pages** dialog box, verify that `AllowConfigurationChanges` is set to `true`, set `CreateDeploymentUtility` to `true`, and optionally update the default value of `DeploymentOutputPath`.</span></span>  
  
6.  <span data-ttu-id="12fb4-117">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="12fb4-117">Click **OK**.</span></span>  
  
### <a name="to-build-the-deployment-utility"></a><span data-ttu-id="12fb4-118">Построение программы развертывания</span><span class="sxs-lookup"><span data-stu-id="12fb4-118">To build the deployment utility</span></span>  
  
1.  <span data-ttu-id="12fb4-119">В обозревателе решений нажмите **Учебник по развертыванию**.</span><span class="sxs-lookup"><span data-stu-id="12fb4-119">In Solution Explorer, click **Deployment Tutorial**.</span></span>  
  
2.  <span data-ttu-id="12fb4-120">В меню **Вид** выберите пункт **Вывод**.</span><span class="sxs-lookup"><span data-stu-id="12fb4-120">On the **View** menu, click **Output**.</span></span> <span data-ttu-id="12fb4-121">По умолчанию окно «Вывод» расположено в нижнем левом углу окна среды [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12fb4-121">By default, the Output window is located in the bottom left corner of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
3.  <span data-ttu-id="12fb4-122">В меню **Сборка** выберите пункт **Сборка учебника по развертыванию**.</span><span class="sxs-lookup"><span data-stu-id="12fb4-122">On the **Build** menu, click **Build Deployment Tutorial**.</span></span>  
  
4.  <span data-ttu-id="12fb4-123">В окне «Вывод» проверьте следующее.</span><span class="sxs-lookup"><span data-stu-id="12fb4-123">In the Output window, verify the following information:</span></span>  
  
     <span data-ttu-id="12fb4-124">Запущена сборка: проект служб SQL Server Integration Services: добавочная...</span><span class="sxs-lookup"><span data-stu-id="12fb4-124">Build started: SQL Integration Services project: Incremental ...</span></span>  
  
     <span data-ttu-id="12fb4-125">Создание программы развертывания...</span><span class="sxs-lookup"><span data-stu-id="12fb4-125">Creating deployment utility...</span></span>  
  
     <span data-ttu-id="12fb4-126">Программа развертывания создана.</span><span class="sxs-lookup"><span data-stu-id="12fb4-126">Deployment Utility created.</span></span>  
  
     <span data-ttu-id="12fb4-127">Построение завершено — 0 ошибок, 0 предупреждений</span><span class="sxs-lookup"><span data-stu-id="12fb4-127">Build complete -- 0 errors, 0 warnings</span></span>  
  
     <span data-ttu-id="12fb4-128">========== Сборка: 0 достигнуто, 0 сбоев, 1 обновленный, 0 пропущено ==========</span><span class="sxs-lookup"><span data-stu-id="12fb4-128">========== Build: 0 succeeded, 0 failed, 1 up-to-date, 0 skipped ==========</span></span>  
  
5.  <span data-ttu-id="12fb4-129">В меню **Файл** выберите пункт **Выход**.</span><span class="sxs-lookup"><span data-stu-id="12fb4-129">On the **File** menu, click **Exit**.</span></span> <span data-ttu-id="12fb4-130">Если программа предложит сохранить изменения объектов учебника по развертыванию, нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="12fb4-130">If prompted to save changes to Deployment Tutorial items, click **Yes**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="12fb4-131">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="12fb4-131">Next Task in Lesson</span></span>  
 [<span data-ttu-id="12fb4-132">Шаг 2. Проверка пакета развертывания</span><span class="sxs-lookup"><span data-stu-id="12fb4-132">Step 2: Verifying the Deployment Bundle</span></span>](../integration-services/lesson-2-2-verifying-the-deployment-bundle.md)  
  
<span data-ttu-id="12fb4-133">![Значок Integration Services (маленький)](media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="12fb4-133">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="12fb4-134">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="12fb4-134">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="12fb4-135">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="12fb4-135">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="12fb4-136">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="12fb4-136">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12fb4-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="12fb4-137">See Also</span></span>  
 [<span data-ttu-id="12fb4-138">Создание программы развертывания</span><span class="sxs-lookup"><span data-stu-id="12fb4-138">Create a Deployment Utility</span></span>](../../2014/integration-services/create-a-deployment-utility.md)  
  
  
