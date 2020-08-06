---
title: Создание проекта Analysis Services | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 065fdc60-1791-4e27-9ed5-51d751b3f8c4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 50640dd7821943dfc3914326f7e8cba32253d307
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654568"
---
# <a name="creating-an-analysis-services-project"></a><span data-ttu-id="381c8-102">Создание проекта служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="381c8-102">Creating an Analysis Services Project</span></span>
  <span data-ttu-id="381c8-103">В следующей задаче используется [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] для создания нового [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] проекта с именем в `Analysis Services Tutorial` зависимости от [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] шаблона проекта.</span><span class="sxs-lookup"><span data-stu-id="381c8-103">In the following task, you use [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to create a new [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project named `Analysis Services Tutorial`, based on the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Project template.</span></span> <span data-ttu-id="381c8-104">*Проект* представляет собой коллекцию связанных объектов.</span><span class="sxs-lookup"><span data-stu-id="381c8-104">A *project* is a collection of related objects.</span></span> <span data-ttu-id="381c8-105">Проекты содержатся в решении, которое может включать несколько проектов.</span><span class="sxs-lookup"><span data-stu-id="381c8-105">Projects exist within a solution, which includes one or more projects.</span></span> <span data-ttu-id="381c8-106">Дополнительные сведения см. в разделе [Создание проекта служб Analysis Services (среда SSDT)](multidimensional-models/create-an-analysis-services-project-ssdt.md).</span><span class="sxs-lookup"><span data-stu-id="381c8-106">For more information, see [Create an Analysis Services Project &#40;SSDT&#41;](multidimensional-models/create-an-analysis-services-project-ssdt.md).</span></span>  
  
### <a name="to-create-a-new-analysis-services-project"></a><span data-ttu-id="381c8-107">Создание нового проекта служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="381c8-107">To create a new Analysis Services project</span></span>  
  
1.  <span data-ttu-id="381c8-108">Нажмите кнопку **Пуск**, укажите пункты **Все программы**, **Microsoft SQL Server 2012**и выберите пункт **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="381c8-108">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2012**, and then click **SQL Server Data Tools**.</span></span>  
  
     <span data-ttu-id="381c8-109">[!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Откроется среда разработки.</span><span class="sxs-lookup"><span data-stu-id="381c8-109">The [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] development environment opens.</span></span>  
  
2.  <span data-ttu-id="381c8-110">На начальной странице [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]нажмите кнопку **Создание проекта**.</span><span class="sxs-lookup"><span data-stu-id="381c8-110">On the Start page of [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], click **New Project**.</span></span>  
  
3.  <span data-ttu-id="381c8-111">В диалоговом окне **Создание проекта** в области **Установленные шаблоны** разверните пункт **Бизнес-аналитика**и выберите **Службы Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="381c8-111">In the **New Project** dialog box, in the **Installed Templates** pane, expand **Business Intelligence**, and then select **Analysis Services**.</span></span> <span data-ttu-id="381c8-112">Выберите шаблон **Проект многомерных данных и интеллектуального анализа данных служб Analysis Services** .</span><span class="sxs-lookup"><span data-stu-id="381c8-112">Choose the **Analysis Services Multidimensional and Data Mining Project** template.</span></span>  
  
     <span data-ttu-id="381c8-113">Обратите внимание, что имя проекта по умолчанию, расположение и имя решения по умолчанию генерируются в нижней части диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="381c8-113">Notice the default project name, location, and the default solution name are generated in the bottom of the dialog box.</span></span> <span data-ttu-id="381c8-114">По умолчанию для решения создается новый каталог.</span><span class="sxs-lookup"><span data-stu-id="381c8-114">By default, a new directory is created for the solution.</span></span>  
  
4.  <span data-ttu-id="381c8-115">Измените имя проекта на `Analysis Services Tutorial` , которое также изменяет поле **имя решения** , а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="381c8-115">Change the project Name to `Analysis Services Tutorial`, which also changes the **Solution name** box, and then click **OK**.</span></span>  
  
 <span data-ttu-id="381c8-116">Вы успешно создали `Analysis Services Tutorial` проект на основе шаблона **проекта Analysis Services многомерных данных и интеллектуального анализа** , в новом решении, которое также называется `Analysis Services Tutorial` .</span><span class="sxs-lookup"><span data-stu-id="381c8-116">You have successfully created the `Analysis Services Tutorial` project, based on the **Analysis Services Multidimensional and Data Mining Project** template, within a new solution that is also named `Analysis Services Tutorial`.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="381c8-117">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="381c8-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="381c8-118">Определение источника данных</span><span class="sxs-lookup"><span data-stu-id="381c8-118">Defining a Data Source</span></span>](lesson-1-2-defining-a-data-source.md)  
  
## <a name="see-also"></a><span data-ttu-id="381c8-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="381c8-119">See Also</span></span>  
 <span data-ttu-id="381c8-120">[Создание многомерных моделей с помощью SQL Server Data Tools &#40;SSDT&#41;](multidimensional-models/creating-multidimensional-models-using-sql-server-data-tools-ssdt.md) </span><span class="sxs-lookup"><span data-stu-id="381c8-120">[Creating Multidimensional Models Using SQL Server Data Tools &#40;SSDT&#41;](multidimensional-models/creating-multidimensional-models-using-sql-server-data-tools-ssdt.md) </span></span>  
 [<span data-ttu-id="381c8-121">Создание проекта служб Analysis Services (среда SSDT)</span><span class="sxs-lookup"><span data-stu-id="381c8-121">Create an Analysis Services Project &#40;SSDT&#41;</span></span>](multidimensional-models/create-an-analysis-services-project-ssdt.md)  
  
  
