---
title: Создание нового Integration Services проекта | Документация Майкрософт
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
ms.assetid: 1e23f259-0401-4333-ab4f-89809aae63b1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f62d3ac2d33bb51a0ccc3b77d9f8b5ec0f52b345
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658334"
---
# <a name="create-a-new-integration-services-project"></a><span data-ttu-id="12cfd-102">Создание нового проекта служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="12cfd-102">Create a New Integration Services Project</span></span>
  <span data-ttu-id="12cfd-103">Данная процедура создает новый проект и новое решение служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="12cfd-103">This procedure creates a new project and a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] solution.</span></span>  
  
### <a name="to-create-a-new-integration-services-project"></a><span data-ttu-id="12cfd-104">Создание нового проекта служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="12cfd-104">To create a new Integration Services project</span></span>  
  
1.  <span data-ttu-id="12cfd-105">Откройте среду [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12cfd-105">Open [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="12cfd-106">В меню **Файл** выберите пункт **Создать**, а затем команду **Проект**.</span><span class="sxs-lookup"><span data-stu-id="12cfd-106">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="12cfd-107">В диалоговом окне **Создание проекта** на панели **Шаблоны** выберите шаблон **Проект служб Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="12cfd-107">In the **New Project** dialog box, in the **Templates** pane, select the **Integration Services Project** template.</span></span>  
  
     <span data-ttu-id="12cfd-108">Шаблон **Проект служб Integration Services** создает проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий единственный пустой пакет.</span><span class="sxs-lookup"><span data-stu-id="12cfd-108">The **Integration Services Project** template creates an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains a single, empty package.</span></span>  
  
4.  <span data-ttu-id="12cfd-109">(Необязательно) При необходимости измените имя и расположение проекта.</span><span class="sxs-lookup"><span data-stu-id="12cfd-109">(Optional) Edit the project name and the location.</span></span>  
  
     <span data-ttu-id="12cfd-110">Имя решения автоматически обновляется для соответствия с именем проекта.</span><span class="sxs-lookup"><span data-stu-id="12cfd-110">The solution name is automatically updated to match the project name.</span></span>  
  
5.  <span data-ttu-id="12cfd-111">Чтобы создать отдельную папку для файла решения, выберите **Создать каталог для решения**.</span><span class="sxs-lookup"><span data-stu-id="12cfd-111">To create a separate folder for the solution file, select **Create directory for solution**.</span></span> <span data-ttu-id="12cfd-112">Это параметр по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="12cfd-112">This is the default option.</span></span>  
  
6.  <span data-ttu-id="12cfd-113">Если на компьютере установлено программное обеспечение для системы управления версиями, выберите **Добавить в систему управления версиями**  , чтобы связать проект с этой системой управления версиями.</span><span class="sxs-lookup"><span data-stu-id="12cfd-113">If source control software is installed on the computer, select **Add to source control**  to associate the project with source control.</span></span>  
  
7.  <span data-ttu-id="12cfd-114">Если в качестве программного обеспечения для управления версиями используется [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe, откроется диалоговое окно **Вход в Visual SourceSafe** .</span><span class="sxs-lookup"><span data-stu-id="12cfd-114">If the source control software is [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe, the **Visual SourceSafe Login** dialog box opens.</span></span> <span data-ttu-id="12cfd-115">В окне **Вход в Visual SourceSafe**укажите имя пользователя, пароль и имя базы данных [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe.</span><span class="sxs-lookup"><span data-stu-id="12cfd-115">In **Visual SourceSafe Login**, provide a user name, a password, and the name of the [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe database.</span></span> <span data-ttu-id="12cfd-116">Нажмите кнопку **Обзор** , чтобы указать базу данных.</span><span class="sxs-lookup"><span data-stu-id="12cfd-116">Click **Browse** to locate the database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="12cfd-117">Чтобы просмотреть и изменить выбранный встраиваемый модуль управления версиями, а также настроить среду управления версиями, выберите пункт **Параметры** в меню **Сервис**, а затем разверните узел **Управление версиями**.</span><span class="sxs-lookup"><span data-stu-id="12cfd-117">To view and change the selected source control plug-in and to configure the source control environment, click **Options** on the **Tools** menu, and then expand the **Source Control** node.</span></span>  
  
8.  <span data-ttu-id="12cfd-118">Нажмите кнопку **ОК** , чтобы добавить решение в **проводник решения**r и добавить проект в решение.</span><span class="sxs-lookup"><span data-stu-id="12cfd-118">Click **OK** to add the solution to **Solution Explore**r and add the project to the solution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12cfd-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="12cfd-119">See Also</span></span>  
 <span data-ttu-id="12cfd-120">[Integration Services &#40;проектов&#41; SSIS](integration-services-ssis-projects-and-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="12cfd-120">[Integration Services &#40;SSIS&#41; Projects](integration-services-ssis-projects-and-solutions.md) </span></span>  
 [<span data-ttu-id="12cfd-121">Добавление или удаление проектом служб Integration Services из решения</span><span class="sxs-lookup"><span data-stu-id="12cfd-121">Add or Remove an Integration Services Project in a Solution</span></span>](../../2014/integration-services/add-or-remove-an-integration-services-project-in-a-solution.md)  
  
  
