---
title: Добавление или удаление проекта Integration Services в решении | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- adding projects
- Integration Services projects, adding
- SQL Server Integration Services projects, adding
- SSIS projects, adding
- projects [Integration Services], adding
ms.assetid: f01f6475-b63c-41dc-82ac-b62162b3adf7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 49984c61047a6b716015bd72e518b73cb08b3226
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654471"
---
# <a name="add-or-remove-an-integration-services-project-in-a-solution"></a><span data-ttu-id="2ff1b-102">Добавление или удаление проектом служб Integration Services из решения</span><span class="sxs-lookup"><span data-stu-id="2ff1b-102">Add or Remove an Integration Services Project in a Solution</span></span>
  <span data-ttu-id="2ff1b-103">Следующие процедуры описывают способы добавления или удаления проекта служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] в решении.</span><span class="sxs-lookup"><span data-stu-id="2ff1b-103">The following procedures descibe how to add or remove an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project in a solution.</span></span>  
  
 <span data-ttu-id="2ff1b-104">Добавлять проекты к существующему решению и удалять их из него можно только тогда, когда решение отображается в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ff1b-104">You can only add a project to an existing solution, or remove a project from a solution, when the solution is visible in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="2ff1b-105">Если вы выбрали параметр **всегда показывать решение** в [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] , [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] будет отображать решение, даже если это решение содержит только один проект.</span><span class="sxs-lookup"><span data-stu-id="2ff1b-105">If you have selected the **Always show solution** option in [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] will display a solution even when that solution contains only one project.</span></span> <span data-ttu-id="2ff1b-106">В противном случае среда [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] будет отображать решение, только когда в нем более одного проекта.</span><span class="sxs-lookup"><span data-stu-id="2ff1b-106">Otherwise, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] will display a solution only when that solution contains more than one project.</span></span> <span data-ttu-id="2ff1b-107">Дополнительными могут быть проекты служб [!INCLUDE[ssIS](../includes/ssis-md.md)] или проекты других типов.</span><span class="sxs-lookup"><span data-stu-id="2ff1b-107">The additional projects can be either [!INCLUDE[ssIS](../includes/ssis-md.md)] projects or projects of other types.</span></span>  
  
## <a name="adding-an-integration-services-project"></a><span data-ttu-id="2ff1b-108">Добавление проекта служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="2ff1b-108">Adding an Integration Services Project</span></span>  
 <span data-ttu-id="2ff1b-109">При добавлении проекта можно создать новый пустой проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] или добавить проект, созданный для другого решения.</span><span class="sxs-lookup"><span data-stu-id="2ff1b-109">When you add a project, you can have [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] create a new, blank project, or you can add a project that you have already created for a different solution.</span></span> <span data-ttu-id="2ff1b-110">Добавить проект к существующему решению можно, только если решение отображается в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ff1b-110">You can only add a project to an existing solution when the solution is visible in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
#### <a name="to-add-a-new-integration-services-project-to-a-solution"></a><span data-ttu-id="2ff1b-111">Добавление нового проекта служб Integration Services к решению</span><span class="sxs-lookup"><span data-stu-id="2ff1b-111">To add a new Integration Services project to a solution</span></span>  
  
1.  <span data-ttu-id="2ff1b-112">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте решение, к которому нужно добавить новый проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , и выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="2ff1b-112">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the solution to which you want to add a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project, and do one of the following:</span></span>  
  
    -   <span data-ttu-id="2ff1b-113">Щелкните решение правой кнопкой, выберите пункт **Добавить**, а затем **Новый проект**.</span><span class="sxs-lookup"><span data-stu-id="2ff1b-113">Right-click the solution, click **Add**, and then click **New Project**.</span></span>  
  
    -   <span data-ttu-id="2ff1b-114">В меню **Файл** выберите пункт **Добавить**, затем щелкните **Создание проекта**.</span><span class="sxs-lookup"><span data-stu-id="2ff1b-114">On the **File** menu, point to **Add**, and then click **New Project**.</span></span>  
  
2.  <span data-ttu-id="2ff1b-115">В диалоговом окне **Добавить новый проект** щелкните **Проект служб Integration Services** на панели **Шаблоны** .</span><span class="sxs-lookup"><span data-stu-id="2ff1b-115">In the **Add New Project** dialog box, click **Integration Services Project** in the **Templates** pane.</span></span>  
  
3.  <span data-ttu-id="2ff1b-116">Дополнительно можно изменить имя и расположение проекта.</span><span class="sxs-lookup"><span data-stu-id="2ff1b-116">Optionally, edit the project name and location.</span></span>  
  
4.  <span data-ttu-id="2ff1b-117">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2ff1b-117">Click **OK**.</span></span>  
  
#### <a name="to-add-an-existing-integration-services-project-to-a-solution"></a><span data-ttu-id="2ff1b-118">Добавление существующего проекта служб Integration Services к решению</span><span class="sxs-lookup"><span data-stu-id="2ff1b-118">To add an existing Integration Services project to a solution</span></span>  
  
1.  <span data-ttu-id="2ff1b-119">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте решение, к которому нужно добавить существующий проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , и выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="2ff1b-119">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the solution to which you want to add an existing [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project, and do one of the following:</span></span>  
  
    -   <span data-ttu-id="2ff1b-120">Щелкните решение правой кнопкой мыши, выберите **Добавить**, а затем щелкните **Существующий проект**.</span><span class="sxs-lookup"><span data-stu-id="2ff1b-120">Right-click the solution, point to **Add**, and then click **Existing Project**.</span></span>  
  
    -   <span data-ttu-id="2ff1b-121">В меню **Файл** выберите **Добавить**, а затем — **Существующий проект**.</span><span class="sxs-lookup"><span data-stu-id="2ff1b-121">On the **File** menu, click **Add**, and then click **Existing Project**.</span></span>  
  
2.  <span data-ttu-id="2ff1b-122">В диалоговом окне **Добавление существующего проекта** выберите локальный проект, который нужно добавить, и щелкните **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="2ff1b-122">In the **Add Existing Project** dialog box, browse to locate the project you want to add, and then click **Open**.</span></span>  
  
3.  <span data-ttu-id="2ff1b-123">Проект будет добавлен в папку решений **Обозревателя решений**.</span><span class="sxs-lookup"><span data-stu-id="2ff1b-123">The project is added to the solution folder in **Solution Explorer**.</span></span>  
  
## <a name="removing-an-integration-services-project"></a><span data-ttu-id="2ff1b-124">Удаление проекта служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="2ff1b-124">Removing an Integration Services Project</span></span>  
 <span data-ttu-id="2ff1b-125">Удалить проект из решения можно, только если решение отображается в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ff1b-125">You can only remove a project from a solution when the solution is visible in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="2ff1b-126">После отображения решения можно удалить все проекты, кроме одного.</span><span class="sxs-lookup"><span data-stu-id="2ff1b-126">After the solution is visible, you can remove all except one project.</span></span> <span data-ttu-id="2ff1b-127">Когда остается только один проект, среда [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] больше не отображает папку решения и удалить последний проект становится невозможным.</span><span class="sxs-lookup"><span data-stu-id="2ff1b-127">As soon as only one project remains, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] no longer displays the solution folder and you cannot remove the last project.</span></span>  
  
#### <a name="to-remove-an-integration-services-project-from-a-solution"></a><span data-ttu-id="2ff1b-128">Удаление проекта служб Integration Services из решения</span><span class="sxs-lookup"><span data-stu-id="2ff1b-128">To remove an Integration Services project from a solution</span></span>  
  
1.  <span data-ttu-id="2ff1b-129">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]нужно открыть решение, из которого необходимо удалить проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2ff1b-129">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the solution from which you want to remove an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="2ff1b-130">В обозревателе решений щелкните правой кнопкой мыши проект и выберите команду **Выгрузить проект**.</span><span class="sxs-lookup"><span data-stu-id="2ff1b-130">In Solution Explorer, right-click the project, and then click **Unload Project**.</span></span>  
  
3.  <span data-ttu-id="2ff1b-131">Нажмите кнопку **ОК** для подтверждения удаления.</span><span class="sxs-lookup"><span data-stu-id="2ff1b-131">Click **OK** to confirm the removal.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ff1b-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="2ff1b-132">See Also</span></span>  
 <span data-ttu-id="2ff1b-133">[Integration Services &#40;проектов&#41; SSIS](integration-services-ssis-projects-and-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="2ff1b-133">[Integration Services &#40;SSIS&#41; Projects](integration-services-ssis-projects-and-solutions.md) </span></span>  
 [<span data-ttu-id="2ff1b-134">Создание нового проекта Integration Services</span><span class="sxs-lookup"><span data-stu-id="2ff1b-134">Create a New Integration Services Project</span></span>](../../2014/integration-services/create-a-new-integration-services-project.md)  
  
  
