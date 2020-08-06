---
title: Мастер развертывания Integration Services | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.deploymentwizard.f1
ms.assetid: f3d93e13-2d85-47ff-a913-cda4046491c4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9afdc529baa4546f126eb67456927e770cb345dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736569"
---
# <a name="integration-services-deployment-wizard"></a><span data-ttu-id="e75ff-102">Мастер развертывания служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="e75ff-102">Integration Services Deployment Wizard</span></span>
  <span data-ttu-id="e75ff-103">Мастер развертывания служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] разворачивает проекты в каталоге SSISDB на экземпляре [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] с помощью модели развертывания проектов.</span><span class="sxs-lookup"><span data-stu-id="e75ff-103">The [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Deployment Wizard deploys projects to the SSISDB catalog on a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance using the project deployment model.</span></span>  
  
 <span data-ttu-id="e75ff-104">Чтобы запустить [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Мастер развертывания из открытого проекта в, в [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] меню **проект** выберите пункт **развернуть** .</span><span class="sxs-lookup"><span data-stu-id="e75ff-104">To start the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Deployment Wizard from an open project in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], select **Deploy** from the **Project** menu.</span></span> <span data-ttu-id="e75ff-105">Чтобы запустить мастер в [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] , разверните узел **Integration Services каталоги**  >  **SSISDB** в обозревателе объектов, щелкните правой кнопкой мыши папку **проекты** и выберите пункт **развернуть проект**.</span><span class="sxs-lookup"><span data-stu-id="e75ff-105">To start the wizard in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], expand the **Integration Services Catalogs** > **SSISDB** node in Object Explorer, right-click the **Projects** folder, and then click **Deploy Project**.</span></span>  
  
 <span data-ttu-id="e75ff-106">Мастер состоит из следующих четырех шагов.</span><span class="sxs-lookup"><span data-stu-id="e75ff-106">The wizard proceeds through the following four steps.</span></span> <span data-ttu-id="e75ff-107">Нажмите кнопку **Далее** , чтобы перейти к следующему шагу или **назад** , чтобы вернуться к предыдущему шагу.</span><span class="sxs-lookup"><span data-stu-id="e75ff-107">Click **Next** to move to the next step, or **Previous** to return to the previous step.</span></span>  
  
1.  <span data-ttu-id="e75ff-108">**Выберите источник** — выберите [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] проект, который требуется развернуть.</span><span class="sxs-lookup"><span data-stu-id="e75ff-108">**Select Source** - Select the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that you want to deploy.</span></span>  
  
2.  <span data-ttu-id="e75ff-109">**Выберите назначение** — выберите назначение проекта.</span><span class="sxs-lookup"><span data-stu-id="e75ff-109">**Select Destination** - Select the project destination.</span></span>  
  
3.  <span data-ttu-id="e75ff-110">**Просмотр** . отображает параметры.</span><span class="sxs-lookup"><span data-stu-id="e75ff-110">**Review** - Displays your selections.</span></span>  
  
4.  <span data-ttu-id="e75ff-111">**Развертывание/результаты** — развертывает проект и отображает результаты.</span><span class="sxs-lookup"><span data-stu-id="e75ff-111">**Deploy/Results** - Deploys the project and displays the results.</span></span>  
  
## <a name="select-source"></a><span data-ttu-id="e75ff-112">Выбор источника</span><span class="sxs-lookup"><span data-stu-id="e75ff-112">Select Source</span></span>  
 <span data-ttu-id="e75ff-113">Чтобы развернуть созданный файл развертывания проекта, выберите **файл развертывания проекта** и введите путь к ISPAC-файлу или нажмите кнопку **Обзор** , чтобы найти его в [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] папке проекта.</span><span class="sxs-lookup"><span data-stu-id="e75ff-113">To deploy a project deployment file that you created, select **Project deployment file** and enter the path to the .ispac file or click **Browse** to find it in the [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] project folder.</span></span> <span data-ttu-id="e75ff-114">Для развертывания проекта, который находится в каталоге служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , выберите **Каталог служб Integration Services**, а затем введите имя сервера и путь к проекту в каталоге.</span><span class="sxs-lookup"><span data-stu-id="e75ff-114">To deploy a project that resides in the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] catalog, select **Integration Services catalog**, and then enter the server name and the path to the project in the catalog.</span></span>  
  
 <span data-ttu-id="e75ff-115">Если мастер запускается в среде [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], по умолчанию в качестве источника выбирается открытый проект, а этот шаг пропускается.</span><span class="sxs-lookup"><span data-stu-id="e75ff-115">If you start the wizard in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], then by default the wizard selects the open project as the source and skips this step.</span></span> <span data-ttu-id="e75ff-116">Чтобы вернуться к этому шагу и выбрать другой источник, нажмите кнопку **назад** или выберите **источник** на левой панели.</span><span class="sxs-lookup"><span data-stu-id="e75ff-116">To return to this step and select a different source, click **Previous** or click **Select Source** in the left pane.</span></span>  
  
## <a name="select-destination"></a><span data-ttu-id="e75ff-117">Выбор назначения</span><span class="sxs-lookup"><span data-stu-id="e75ff-117">Select Destination</span></span>  
 <span data-ttu-id="e75ff-118">Для выбора папки назначения проекта в каталоге [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] введите экземпляр [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] или нажмите кнопку **Обзор** , чтобы осуществить выбор из списка серверов.</span><span class="sxs-lookup"><span data-stu-id="e75ff-118">To select the destination folder for the project in the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] catalog, enter the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance or click **Browse** to select from a list of servers.</span></span> <span data-ttu-id="e75ff-119">Введите путь к проекту в SSISDB или нажмите кнопку **Обзор** , чтобы произвести выбор.</span><span class="sxs-lookup"><span data-stu-id="e75ff-119">Enter the project path in SSISDB or click **Browse** to select it.</span></span>  
  
 <span data-ttu-id="e75ff-120">Если мастер запускается в среде [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], по умолчанию мастер выбирает подключенный экземпляр сервера и вводит путь к выбранном проекту.</span><span class="sxs-lookup"><span data-stu-id="e75ff-120">If you start the wizard in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], then by default the wizard selects the connected server instance and enters the path to the selected project.</span></span> <span data-ttu-id="e75ff-121">Эти значения вы можете изменить для развертывания проекта в другое местоположение.</span><span class="sxs-lookup"><span data-stu-id="e75ff-121">You can change these values to deploy the project to a different location.</span></span>  
  
## <a name="review"></a><span data-ttu-id="e75ff-122">Просмотр</span><span class="sxs-lookup"><span data-stu-id="e75ff-122">Review</span></span>  
 <span data-ttu-id="e75ff-123">Мастер позволяет просмотреть выбранные параметры перед развертыванием проекта.</span><span class="sxs-lookup"><span data-stu-id="e75ff-123">The wizard allows you to review the settings you have selected before deploying the project.</span></span> <span data-ttu-id="e75ff-124">Вы можете изменить выбранные параметры, нажав кнопку **Назад**или кнопку любого из шагов на левой панели.</span><span class="sxs-lookup"><span data-stu-id="e75ff-124">You can change your selections by clicking **Previous**, or by clicking any of the steps in the left pane.</span></span>  
  
## <a name="deployresults"></a><span data-ttu-id="e75ff-125">Развертывание/результаты</span><span class="sxs-lookup"><span data-stu-id="e75ff-125">Deploy/Results</span></span>  
 <span data-ttu-id="e75ff-126">При нажатии кнопки **развернуть** на странице **Просмотр** проект развертывается, а на странице **результаты** отображается успех или неудача каждого действия.</span><span class="sxs-lookup"><span data-stu-id="e75ff-126">When you click **Deploy** from the **Review** page, the project is deployed and the **Results** page displays the success or failure of each action.</span></span> <span data-ttu-id="e75ff-127">Если действие не выполнено, нажмите кнопку **Ошибка** в столбце **Результат** для отображения описания ошибки.</span><span class="sxs-lookup"><span data-stu-id="e75ff-127">If the action fails, click the **Failed** in the **Result** column to display an explanation of the error.</span></span> <span data-ttu-id="e75ff-128">Нажмите кнопку **сохранить отчет...** , чтобы сохранить результаты в XML-файл.</span><span class="sxs-lookup"><span data-stu-id="e75ff-128">Click **Save Report...** to save the results to an XML file.</span></span>  
  
 <span data-ttu-id="e75ff-129">Нажмите кнопку **Закрыть**, чтобы выйти из мастера.</span><span class="sxs-lookup"><span data-stu-id="e75ff-129">Click **Close** to exit the wizard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e75ff-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="e75ff-130">See Also</span></span>  
 <span data-ttu-id="e75ff-131">[Развертывание проектов на сервере Integration Services](../../2014/integration-services/deploy-projects-to-integration-services-server.md) </span><span class="sxs-lookup"><span data-stu-id="e75ff-131">[Deploy Projects to Integration Services Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md) </span></span>  
 [<span data-ttu-id="e75ff-132">Развертывание проектов и пакетов</span><span class="sxs-lookup"><span data-stu-id="e75ff-132">Deployment of Projects and Packages</span></span>](packages/deploy-integration-services-ssis-projects-and-packages.md)  
  
  
