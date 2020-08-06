---
title: Шаг 2. Создание проекта развертывания | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 59990fe2-7036-4e9c-8efc-6ece9e66eda7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ebfce8796f98628c2832c5ab7f4be665c7915d10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664359"
---
# <a name="step-2-creating-the-deployment-project"></a><span data-ttu-id="f937f-102">Шаг 2. Создание проекта развертывания</span><span class="sxs-lookup"><span data-stu-id="f937f-102">Step 2: Creating the Deployment Project</span></span>
  <span data-ttu-id="f937f-103">В службах [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]развертываемый модуль находится в проекте служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f937f-103">In [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], the deployable unit is an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span> <span data-ttu-id="f937f-104">Перед развертыванием пакетов нужно создать новый проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] и добавить в него все пакеты и вспомогательные файлы, которые нужно развертывать вместе с пакетами.</span><span class="sxs-lookup"><span data-stu-id="f937f-104">Before you can deploy packages, you must create a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project and add all the packages and any ancillary files that you want to deploy with the packages to that project.</span></span>  
  
### <a name="to-create-the-integration-services-project"></a><span data-ttu-id="f937f-105">Создание проекта служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="f937f-105">To create the Integration Services project</span></span>  
  
1.  <span data-ttu-id="f937f-106">Нажмите кнопку **Пуск**, наведите указатель на пункт **Все программы**, наведите указатель на пункт **Microsoft SQL Server**и выберите пункт **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="f937f-106">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, and then click **SQL ServerSQL Server Data Tools**.</span></span>  
  
2.  <span data-ttu-id="f937f-107">В меню **Файл** наведите указатель на пункт **Создать**и выберите пункт **Проект** , чтобы создать проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f937f-107">On the **File** menu, point to **New**, and then click **Project** to create a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span>  
  
3.  <span data-ttu-id="f937f-108">В диалоговом окне **Создание проекта** на панели **Шаблоны** выберите пункт **Проект служб SSIS** .</span><span class="sxs-lookup"><span data-stu-id="f937f-108">In the **New Project** dialog box, select **Integration Services Project** in the **Templates** pane.</span></span>  
  
4.  <span data-ttu-id="f937f-109">В поле **Имя** измените заданное по умолчанию имя на **Учебник по развертыванию**.</span><span class="sxs-lookup"><span data-stu-id="f937f-109">In the **Name** box, change the default name to **Deployment Tutorial**.</span></span> <span data-ttu-id="f937f-110">При необходимости снимите флажок **Создать каталог для решения** .</span><span class="sxs-lookup"><span data-stu-id="f937f-110">Optionally, clear the **Create directory for solution** check box.</span></span>  
  
5.  <span data-ttu-id="f937f-111">Примите расположение по умолчанию или нажмите кнопку **Обзор** , чтобы выбрать папку.</span><span class="sxs-lookup"><span data-stu-id="f937f-111">Accept the default location, or click **Browse** to locate the folder you want to use.</span></span>  
  
6.  <span data-ttu-id="f937f-112">В диалоговом окне **Расположение проекта** выберите папку и нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="f937f-112">In the **Project Location** dialog box, click the folder, and then click **Open**.</span></span>  
  
7.  <span data-ttu-id="f937f-113">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f937f-113">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="f937f-114">По умолчанию будет создан пустой пакет с именем Package.dtsx, который будет добавлен к проекту.</span><span class="sxs-lookup"><span data-stu-id="f937f-114">By default, an empty package, named Package.dtsx, is created and added to your project.</span></span> <span data-ttu-id="f937f-115">Однако вы не будете использовать этот пакет, вместо этого нужно добавить в проект существующий пакет.</span><span class="sxs-lookup"><span data-stu-id="f937f-115">However, you will not use this package; instead, you will add existing packages to the project.</span></span> <span data-ttu-id="f937f-116">Поскольку будут развернуты все пакеты в проекте, следует удалить файл Package.dtsx.</span><span class="sxs-lookup"><span data-stu-id="f937f-116">Because all the packages in a project will be included in the deployment, you should delete Package.dtsx.</span></span> <span data-ttu-id="f937f-117">Чтобы удалить файл, щелкните его правой кнопкой мыши и выберите пункт **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="f937f-117">To delete it, right-click it, and then click **Delete**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="f937f-118">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="f937f-118">Next Task in Lesson</span></span>  
 [<span data-ttu-id="f937f-119">Шаг 3. Добавление пакетов и других файлов</span><span class="sxs-lookup"><span data-stu-id="f937f-119">Step 3: Adding Packages and Other Files</span></span>](../integration-services/lesson-1-3-adding-packages-and-other-files.md)  
  
<span data-ttu-id="f937f-120">![Значок Integration Services (маленький)](media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="f937f-120">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="f937f-121">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="f937f-121">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="f937f-122">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="f937f-122">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="f937f-123">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="f937f-123">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f937f-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="f937f-124">See Also</span></span>  
 [<span data-ttu-id="f937f-125">Проекты служб Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="f937f-125">Integration Services &#40;SSIS&#41; Projects</span></span>](integration-services-ssis-projects-and-solutions.md)  
  
  
