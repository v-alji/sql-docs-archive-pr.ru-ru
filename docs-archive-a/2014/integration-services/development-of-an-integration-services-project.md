---
title: Разработка проекта Integration Services | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- projects [Integration Services], creating
- Integration Services projects, creating
- SQL Server Integration Services projects, creating
- SSIS projects, creating
ms.assetid: 6e90b016-36a5-415e-9440-a20199fffff0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: da648b3b09b25fa2a7b1cf886ad1bf770296f5ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667824"
---
# <a name="development-of-an-integration-services-project"></a><span data-ttu-id="940f2-102">Разработка проекта служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="940f2-102">Development of an Integration Services Project</span></span>
  <span data-ttu-id="940f2-103">Добавление пакетов [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] осуществляется в проекты.</span><span class="sxs-lookup"><span data-stu-id="940f2-103">You add [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages to projects.</span></span> <span data-ttu-id="940f2-104">Для создания проектов служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] и работы с ними необходимо установить среду [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="940f2-104">To create and work with [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projects, you must install the [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] environment.</span></span> <span data-ttu-id="940f2-105">Дополнительные сведения см. в статье [Установка служб Integration Services](install-windows/install-integration-services.md).</span><span class="sxs-lookup"><span data-stu-id="940f2-105">For more information, see [Install Integration Services](install-windows/install-integration-services.md).</span></span>  
  
 <span data-ttu-id="940f2-106">При создании нового проекта служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]отображается диалоговое окно **Создание проекта** с шаблоном **Проект служб Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="940f2-106">When you create a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], the **New Project** dialog box includes an **Integration Services Project** template.</span></span> <span data-ttu-id="940f2-107">Этот шаблон позволяет создать проект, в котором содержится единственный пакет.</span><span class="sxs-lookup"><span data-stu-id="940f2-107">This project template creates a new project that contains a single package.</span></span>  
  
## <a name="projects-and-solutions"></a><span data-ttu-id="940f2-108">Проекты и решения</span><span class="sxs-lookup"><span data-stu-id="940f2-108">Projects and Solutions</span></span>  
 <span data-ttu-id="940f2-109">Проекты сохраняются в решениях.</span><span class="sxs-lookup"><span data-stu-id="940f2-109">Projects are stored in solutions.</span></span> <span data-ttu-id="940f2-110">Можно сначала создать решение, затем добавить к решению проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="940f2-110">You can create a solution first and then add an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project to the solution.</span></span> <span data-ttu-id="940f2-111">Если не существует никаких решений, среда [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] автоматически создает для пользователя решение после того, как пользователь сначала создаст проект.</span><span class="sxs-lookup"><span data-stu-id="940f2-111">If no solution exists, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] automatically creates one for you when you first create the project.</span></span> <span data-ttu-id="940f2-112">Решение может содержать несколько проектов различного типа.</span><span class="sxs-lookup"><span data-stu-id="940f2-112">A solution can contain multiple projects of different types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="940f2-113">По умолчанию при создании нового проекта служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] в [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]решение на панели **Обозреватель решений** не отображается.</span><span class="sxs-lookup"><span data-stu-id="940f2-113">By default, when you create a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], the solution is not shown in the **Solution Explorer** pane.</span></span> <span data-ttu-id="940f2-114">Чтобы изменить это поведение по умолчанию, в меню **Сервис** выберите пункт **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="940f2-114">To change this default behavior, on the **Tools** menus, click **Options**.</span></span> <span data-ttu-id="940f2-115">В диалоговом окне **Параметры** последовательно раскройте элементы **Проекты и решения**, а затем щелкните **Общие**.</span><span class="sxs-lookup"><span data-stu-id="940f2-115">In the **Options** dialog box, expand **Projects and Solutions**, and then click **General**.</span></span> <span data-ttu-id="940f2-116">На странице **Общие** выберите **Всегда показывать решение**.</span><span class="sxs-lookup"><span data-stu-id="940f2-116">On the **General** page, select **Always show solution**.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="940f2-117">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="940f2-117">Related Tasks</span></span>  
  
-   [<span data-ttu-id="940f2-118">Создание нового проекта Integration Services</span><span class="sxs-lookup"><span data-stu-id="940f2-118">Create a New Integration Services Project</span></span>](../../2014/integration-services/create-a-new-integration-services-project.md)  
  
-   [<span data-ttu-id="940f2-119">Добавление элемента к проекту служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="940f2-119">Add an Item to an Integration Services Project</span></span>](../../2014/integration-services/add-an-item-to-an-integration-services-project.md)  
  
-   [<span data-ttu-id="940f2-120">Добавление или удаление проектом служб Integration Services из решения</span><span class="sxs-lookup"><span data-stu-id="940f2-120">Add or Remove an Integration Services Project in a Solution</span></span>](../../2014/integration-services/add-or-remove-an-integration-services-project-in-a-solution.md)  
  
  
