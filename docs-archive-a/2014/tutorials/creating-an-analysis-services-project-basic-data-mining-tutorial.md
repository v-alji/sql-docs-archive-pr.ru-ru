---
title: Создание проекта Analysis Services (учебник по интеллектуальному анализу данных — базовый) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 784c0401-0358-4117-9c85-4e8220ce71d9
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 83eb808bc7d18ebe715d309d9f911c010ee172d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655487"
---
# <a name="creating-an-analysis-services-project-basic-data-mining-tutorial"></a><span data-ttu-id="20f47-102">Создание проекта служб Analysis Services (учебник по интеллектуальному анализу данных — начальный уровень)</span><span class="sxs-lookup"><span data-stu-id="20f47-102">Creating an Analysis Services Project (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="20f47-103">Каждый [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] проект определяет объекты в одной [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] базе данных.</span><span class="sxs-lookup"><span data-stu-id="20f47-103">Each [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project defines the objects in a single [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="20f47-104">База данных [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] может содержать множество различных типов объектов</span><span class="sxs-lookup"><span data-stu-id="20f47-104">An [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database can contains many different types of objects</span></span>  
  
-   <span data-ttu-id="20f47-105">Многомерные модели (кубы)</span><span class="sxs-lookup"><span data-stu-id="20f47-105">Multidimensional models (cubes)</span></span>  
  
-   <span data-ttu-id="20f47-106">Структуры и модели интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="20f47-106">Mining structures and mining models</span></span>  
  
-   <span data-ttu-id="20f47-107">Вспомогательные объекты, такие как источники данных, представления источников данных и пользовательские сборки</span><span class="sxs-lookup"><span data-stu-id="20f47-107">Supporting objects such as data sources, data source views, and custom assemblies</span></span>  
  
 <span data-ttu-id="20f47-108">Обратите внимание, что для интеллектуального анализа данных куб **не** требуется.</span><span class="sxs-lookup"><span data-stu-id="20f47-108">Note that you **do not** require a cube to do data mining.</span></span> <span data-ttu-id="20f47-109">Если необходимо выполнить интеллектуальный анализ данных на уже существующем кубе, следует добавить модели интеллектуального анализа данных в тот проект, который использовался для построения куба.</span><span class="sxs-lookup"><span data-stu-id="20f47-109">If you need to perform data mining on an existing cube, you should add the data mining models to the same project you used to build the cube.</span></span> <span data-ttu-id="20f47-110">Тем не менее в большинстве случаев можно строить модели на источниках реляционных данных, таких как хранилище данных, и обеспечивать более высокую производительность, не прибегая к использованию куба.</span><span class="sxs-lookup"><span data-stu-id="20f47-110">However, for most purposes you can build your models on relational data sources, such as a data warehouse, and get better performance if a cube is not involved.</span></span>  
  
 <span data-ttu-id="20f47-111">В этом учебнике в качестве источника данных используется реляционное хранилище данных [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="20f47-111">In this tutorial you will use a relational data warehouse, [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)], as the data source.</span></span> <span data-ttu-id="20f47-112">Все объекты интеллектуального анализа данных будут развернуты в базе данных [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] с именем `BasicDataMining`, используемой только для интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="20f47-112">You will deploy all your data mining objects to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database named `BasicDataMining`, used just for data mining.</span></span>  
  
 <span data-ttu-id="20f47-113">По умолчанию службы [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] используют для новых проектов экземпляр **localhost** .</span><span class="sxs-lookup"><span data-stu-id="20f47-113">By default, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] uses the **localhost** instance for new projects.</span></span> <span data-ttu-id="20f47-114">Если необходимо использовать именованный экземпляр или другой сервер, то сначала создайте и откройте проект, а затем измените имя экземпляра.</span><span class="sxs-lookup"><span data-stu-id="20f47-114">If you are using a named instance or a different server, you must first create and open the project and then change the instance name.</span></span>  
  
 <span data-ttu-id="20f47-115">Дополнительные сведения о службах [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] см. в разделе [Creating an Analysis Services Project](../analysis-services/lesson-1-1-creating-an-analysis-services-project.md).</span><span class="sxs-lookup"><span data-stu-id="20f47-115">For more information about [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] projects, see [Creating an Analysis Services Project](../analysis-services/lesson-1-1-creating-an-analysis-services-project.md).</span></span>  
  
### <a name="to-create-an-analysis-services-project"></a><span data-ttu-id="20f47-116">Создание проекта служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="20f47-116">To create an Analysis Services project</span></span>  
  
1.  <span data-ttu-id="20f47-117">Откройте среду [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="20f47-117">Open [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="20f47-118">В меню **Файл** последовательно выберите команды **Создать**и **Проект**.</span><span class="sxs-lookup"><span data-stu-id="20f47-118">On the **File** menu, point to **New**, and then select **Project**.</span></span>  
  
3.  <span data-ttu-id="20f47-119">Убедитесь в том, что выбраны **Проекты бизнес-аналитики** на панели **Типы проектов** .</span><span class="sxs-lookup"><span data-stu-id="20f47-119">Verify that **Business Intelligence Projects** is selected in the **Project types** pane.</span></span>  
  
4.  <span data-ttu-id="20f47-120">На панели **Шаблоны** выберите **Проект многомерных данных и интеллектуального анализа данных служб Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="20f47-120">In the **Templates** pane, select **Analysis Services Multidimensional and Data Mining Project**.</span></span>  
  
5.  <span data-ttu-id="20f47-121">В поле **имя** введите имя нового проекта `BasicDataMining` .</span><span class="sxs-lookup"><span data-stu-id="20f47-121">In the **Name** box, name the new project `BasicDataMining`.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
### <a name="to-change-the-instance-where-data-mining-objects-are-stored"></a><span data-ttu-id="20f47-122">Изменение экземпляра, на котором хранятся объекты интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="20f47-122">To change the instance where data mining objects are stored</span></span>  
  
1.  <span data-ttu-id="20f47-123">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], в меню **Проект** выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="20f47-123">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], on the **Project** menu, select **Properties**.</span></span>  
  
2.  <span data-ttu-id="20f47-124">В левой части панели **Страницы свойств** в области **Свойства настройки**щелкните элемент **Развертывание**.</span><span class="sxs-lookup"><span data-stu-id="20f47-124">On the left side of the **Property Pages** pane, under **Configuration Properties**, click **Deployment**.</span></span>  
  
3.  <span data-ttu-id="20f47-125">В правой части панели **Страницы свойств** на панели **Целевой объект**, убедитесь в том, что именем **сервера** является **localhost**.</span><span class="sxs-lookup"><span data-stu-id="20f47-125">On the right side of the **Property Pages** pane, under **Target**, verify that the **Server** name is **localhost**.</span></span> <span data-ttu-id="20f47-126">Если используется другой экземпляр, введите имя этого экземпляра.</span><span class="sxs-lookup"><span data-stu-id="20f47-126">If you are using a different instance, type the name of the instance.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="20f47-127">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="20f47-127">Next Task in Lesson</span></span>  
 [<span data-ttu-id="20f47-128">Учебник по созданию источника данных &#40;Basic Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="20f47-128">Creating a Data Source &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-data-source-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="20f47-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="20f47-129">See Also</span></span>  
 <span data-ttu-id="20f47-130">[Сборка Analysis Services проектов &#40;SSDT&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/build-analysis-services-projects-ssdt) </span><span class="sxs-lookup"><span data-stu-id="20f47-130">[Build Analysis Services Projects &#40;SSDT&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/build-analysis-services-projects-ssdt) </span></span>  
 [<span data-ttu-id="20f47-131">Создание проекта служб Analysis Services (среда SSDT)</span><span class="sxs-lookup"><span data-stu-id="20f47-131">Create an Analysis Services Project &#40;SSDT&#41;</span></span>](https://docs.microsoft.com/analysis-services/multidimensional-models/create-an-analysis-services-project-ssdt)  
  
  
